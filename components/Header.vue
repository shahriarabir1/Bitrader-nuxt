<template>
    <div>
        <div class="lightdark-switch" @click="toggleTheme">
            <span class="switch-btn" id="btnSwitch">
                <nuxt-image width="0" height="0" sizes="100vw"
                    :src="theme === 'dark' ? '/images/icon/sun.svg' : '/images/icon/moon.svg'" alt="light-dark-switchbtn"
                    class="swtich-icon" />
            </span>
        </div>
        <header class="header-section" :class="headerClass ? headerClass : 'bg-color-3'" @scroll="isSticky">
            <div class="header-bottom">
                <div class="container">
                    <div class="header-wrapper">
                        <div class="logo">
                            <NuxtLink to="/">
                                <img class="dark" src="/images/logo/logo.png" alt="logo" />
                            </NuxtLink>
                        </div>
                        <div class="menu-area">
                            <ul :class="`menu menu--style1 ${menu ? 'active' : ''}`">
                                <li class="megamenu menu-item-has-children">
                                    <NuxtLink scroll="false" to="/#0" @click="toggleActive">Demos</NuxtLink>

                                    <ul class="submenu">
                                        <li>
                                            <div class="home-showcase">
                                                <div
                                                    class="row g-4 row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5">
                                                    <div class="col order-first">
                                                        <div class="home-showcase__item">
                                                            <div class="home-showcase__image">
                                                                <img src="images/demo/1.png" alt="home-showcase" />
                                                                <div class="home-showcase__buttons">
                                                                    <NuxtLink
                                                                        :to="{ pathname: '/', query: { theme: 'light' } }"
                                                                        class="trk-btn trk-btn--primary home-showcase__buttons-item mt-3">
                                                                        <span>Preview</span>
                                                                    </NuxtLink>
                                                                </div>
                                                            </div>
                                                            <h3 class="home-showcase__title">
                                                                <NuxtLink
                                                                    :to="{ pathname: '/', query: { theme: 'light' } }">
                                                                    Stock Trading
                                                                </NuxtLink>
                                                            </h3>
                                                        </div>
                                                    </div>
                                                    <div class="col">
                                                        <div class="home-showcase__item">
                                                            <div class="home-showcase__image">
                                                                <img src="images/demo/1-dark.png" alt="home-showcase" />
                                                                <div class="home-showcase__buttons">
                                                                    <NuxtLink
                                                                        :to="{ pathname: '/', query: { theme: 'dark' } }"
                                                                        class="trk-btn trk-btn--primary home-showcase__buttons-item mt-3">
                                                                        <span>Preview</span>
                                                                    </NuxtLink>
                                                                </div>
                                                            </div>
                                                            <h3 class="home-showcase__title">
                                                                <NuxtLink :to="{ pathname: '/', query: { theme: 'dark' } }">
                                                                    Stock Trading Dark
                                                                </NuxtLink>
                                                            </h3>
                                                        </div>
                                                    </div>

                                                    <!-- Crypto Trading Light -->
                                                    <div class="col">
                                                        <div class="home-showcase__item">
                                                            <div class="home-showcase__image">
                                                                <img src="images/demo/2.png" alt="home-showcase" />
                                                                <div class="home-showcase__buttons">
                                                                    <NuxtLink
                                                                        :to="{ pathname: '/index-2', query: { theme: 'light' } }"
                                                                        class="trk-btn trk-btn--primary home-showcase__buttons-item mt-3">
                                                                        <span>Preview</span>
                                                                    </NuxtLink>
                                                                </div>
                                                            </div>
                                                            <h3 class="home-showcase__title">
                                                                <NuxtLink
                                                                    :to="{ pathname: '/index-2', query: { theme: 'light' } }">
                                                                    Crypto Trading
                                                                </NuxtLink>
                                                            </h3>
                                                        </div>
                                                    </div>

                                                    <!-- Crypto Trading Dark -->
                                                    <div class="col">
                                                        <div class="home-showcase__item">
                                                            <div class="home-showcase__image">
                                                                <img src="images/demo/2-dark.png" alt="home-showcase" />
                                                                <div class="home-showcase__buttons">
                                                                    <NuxtLink
                                                                        :to="{ pathname: '/index-2', query: { theme: 'dark' } }"
                                                                        class="trk-btn trk-btn--primary home-showcase__buttons-item mt-3">
                                                                        <span>Preview</span>
                                                                    </NuxtLink>
                                                                </div>
                                                            </div>
                                                            <h3 class="home-showcase__title">
                                                                <NuxtLink
                                                                    :to="{ pathname: '/index-2', query: { theme: 'dark' } }">
                                                                    Crypto Trading Dark
                                                                </NuxtLink>
                                                            </h3>
                                                        </div>
                                                    </div>

                                                    <!-- Forex Trading Light -->
                                                    <div class="col">
                                                        <div class="home-showcase__item">
                                                            <div class="home-showcase__image">
                                                                <img src="images/demo/3.png" alt="home-showcase" />
                                                                <div class="home-showcase__buttons">
                                                                    <NuxtLink
                                                                        :to="{ pathname: '/index-3', query: { theme: 'light' } }"
                                                                        class="trk-btn trk-btn--primary home-showcase__buttons-item mt-3">
                                                                        <span>Preview</span>
                                                                    </NuxtLink>
                                                                </div>
                                                            </div>
                                                            <h3 class="home-showcase__title">
                                                                <NuxtLink
                                                                    :to="{ pathname: '/index-3', query: { theme: 'light' } }">
                                                                    Forex Trading
                                                                </NuxtLink>
                                                            </h3>
                                                        </div>
                                                    </div>

                                                    <!-- Forex Trading Dark -->
                                                    <div class="col">
                                                        <div class="home-showcase__item">
                                                            <div class="home-showcase__image">
                                                                <img src="images/demo/3-dark.png" alt="home-showcase" />
                                                                <div class="home-showcase__buttons">
                                                                    <NuxtLink
                                                                        :to="{ pathname: '/index-3', query: { theme: 'dark' } }"
                                                                        class="trk-btn trk-btn--primary home-showcase__buttons-item mt-3">
                                                                        <span>Preview</span>
                                                                    </NuxtLink>
                                                                </div>
                                                            </div>
                                                            <h3 class="home-showcase__title">
                                                                <NuxtLink
                                                                    :to="{ pathname: '/index-3', query: { theme: 'dark' } }">
                                                                    Forex Trading Dark
                                                                </NuxtLink>
                                                            </h3>
                                                        </div>
                                                    </div>
                                                    <div class="col order-last">
                                                        <div class="home-showcase__item">
                                                            <div class="home-showcase__image">
                                                                <img src="images/demo/new.png" alt="home-showcase" />
                                                            </div>
                                                            <h3 class="home-showcase__title">
                                                                <NuxtLink scroll: false to="/#0">New Demos</NuxtLink>
                                                            </h3>
                                                        </div>
                                                    </div>
                                                </div>
                                            </div>
                                        </li>
                                    </ul>
                                </li>
                                <li class="menu-item-has-children">
                                    <NuxtLink to="/services" @click="toggleActive">Services</NuxtLink>
                                    <ul class="submenu">
                                        <li>
                                            <NuxtLink to="/services">Services</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/service-details">Services Details</NuxtLink>
                                        </li>
                                    </ul>
                                </li>
                                <li class="menu-item-has-children">
                                    <NuxtLink scroll="false" to="/#0" @click="toggleActive">About</NuxtLink>
                                    <ul class="submenu">
                                        <li>
                                            <NuxtLink to="/about">About Us</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/price">Price</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/team">Team</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/team-2">Team 2</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/team-details">Team Details</NuxtLink>
                                        </li>
                                    </ul>
                                </li>
                                <li class="menu-item-has-children">
                                    <NuxtLink scroll="false" to="/#0" @click="toggleActive">Pages</NuxtLink>
                                    <ul class="submenu">
                                        <li>
                                            <NuxtLink to="/blogs">Blogs</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/blog-sidebar">Blog - Side Bar</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/blog-details">Blog Details</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/signup">Sign Up</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/signup-2">Sign Up 2</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/signin">Sign In</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/signin-2">Sign In 2</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/forgot-pass">Reset Password</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/forgot-pass-2">Reset Password 2</NuxtLink>
                                        </li>
                                        <li>
                                            <NuxtLink to="/404">404 Error</NuxtLink>
                                        </li>
                                    </ul>
                                </li>
                                <li>
                                    <NuxtLink to="contact">Contact Us</NuxtLink>
                                </li>
                            </ul>
                        </div>
                        <div class="header-action">
                            <div class="menu-area">
                                <div class="header-btn">
                                    <NuxtLink to="signup" class="trk-btn trk-btn--border trk-btn--primary">
                                        <span>Join Now</span>
                                    </NuxtLink>
                                </div>
                                <div :class="`header-bar d-lg-none header-bar--style1 ${menu ? 'active' : ''}`"
                                    @click="toggleMenu">
                                    <span></span>
                                    <span></span>
                                    <span></span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </header>

    </div>
</template>

<script>
export default {
    setup() {


        return {}
    }
}
</script>

<style lang="scss" scoped></style>