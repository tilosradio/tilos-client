<style>
nav {
  border-bottom: 1px solid rgba(170, 30, 30, 0.1);
  font-weight: 300;
  padding: 0 1em;
}

.menu {
  display: flex;
  margin: 0;
  padding: 0;
}

.menu > li {
  padding: 0 10px;
}

li {
  list-style-type: none;
}

.menu-sub {
  display: block;
  margin: 0;
  padding: 0;
}

.selected {
  position: relative;
  display: inline-block;
}

.selected::after {
  position: absolute;
  content: '';
  width: calc(100% - 1em);
  height: 2px;
  background-color: rgb(170, 30, 30);
  display: block;
  bottom: -1px;
}

a {
  text-decoration: none;
  padding: 5px;
  display: block;
}
</style>

<script>
import { format } from 'date-fns';

const archiveLink = `archive/${format(new Date(), 'yyyy-MM-dd')}`;

export let segment;
</script>

<nav>
  <ul class="menu">
    <li>
      <a class="{segment === undefined ? 'selected' : ''}" href=".">Médiatár</a>
      <ul class="menu-sub">
        <li>
          <a
            class="{segment === 'archive' ? 'selected' : ''}"
            href="{archiveLink}"
            rel="prefetch"
            data-testid="navigation-archive">
            Archívum
          </a>
        </li>
        <li>
          <a
            class="{segment === 'shows?type=speech' ? 'selected' : ''}"
            href="shows?type=speech"
            rel="prefetch">
            Beszélgetős
          </a>
        </li>
        <li>
          <a
            class="{segment === 'shows?type=music' ? 'selected' : ''}"
            href="shows?type=music">
            Zenei
          </a>
        </li>
        <li>
          <a href="#0">Podcast</a>
          <ul class="menu-sub">
            <li><a href="">Zenei</a></li>
            <li><a href="">Beszélgetős</a></li>
            <li><a href="">Mese</a></li>
          </ul>
        </li>
      </ul>
    </li>
    <li>
      <a href="#0">Mi</a>
      <ul class="menu-sub">
        <li><a href="">A Tilos Rádió története</a></li>
        <li><a href="">Tilos Kulturális Alapítvány</a></li>
        <li><a href="">Műsorkészítők</a></li>
        <li><a href="">Kapcsolat</a></li>
      </ul>
    </li>
    <li>
      <a href="#0">Magazin</a>
      <ul class="menu-sub">
        <li><a href="">Sajtó</a></li>
        <li><a href="">Maraton</a></li>
        <li><a href="">Tematikus napok</a></li>
      </ul>
    </li>
    <li>
      <a href="#0">Támogatás</a>
      <ul class="menu-sub">
        <li><a href="">Támogatási formák</a></li>
        <li><a href="">Tilos Támogatói Tagkártya</a></li>
        <li><a href="">Adó 1%</a></li>
      </ul>
    </li>
    <li>
      <a
        class="{segment === 'shows' ? 'selected' : ''}"
        href="shows"
        rel="prefetch">
        Műsorok
      </a>
    </li>
  </ul>
</nav>
