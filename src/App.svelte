<script>

</script>

<style>
  form {
    --text-color: #afafaf;
    max-width: 500px;
  }

  .field {
    width: 100%;
    position: relative;
    border-bottom: 2px dashed var(--text-color);
    margin: 4rem auto 1rem;
  }

  .label {
    color: var(--text-color);
    font-size: 1.2rem;
  }
  .strength {
    display: flex;
    height: 20px;
    width: 100%;
  }
  .bar-1 {
    background: linear-gradient(to right, red, orangered);
  }
  .bar-2 {
    background: linear-gradient(to right, orangered, yellow);
  }
  .bar-3 {
    background: linear-gradient(to right, yellow, yellowgreen);
  }
  .bar-4 {
    background: linear-gradient(to right, yellowgreen, green);
  }
  .bar {
    margin-right: 5px;
    height: 100%;
    width: 25%;
    transition: box-shadow 500ms;
    box-shadow: inset 0px 20px #1f1f1f;
  }
  .bar-shadow {
    box-shadow: none;
  }
  .label {
    z-index: -1;
    position: absolute;
    transform: translateY(-2rem);
    transform-origin: 0%;
    transition: transform 400ms;
  }
  .field:focus-within .label,
  .input:not(:placeholder-shown) + .label {
    transform: scale(0.8) translateY(-5rem);
  }

  .field::after {
    content: "";
    position: relative;
    display: block;
    height: 4px;
    width: 100%;
    background: #d16dff;
    transform: scaleX(0);
    transform-origin: 0%;
    /* left to right  */

    transition: transform 500ms ease;
    top: 2px;
  }

  .field:focus-within {
    border-color: transparent;
  }
  .field:focus-within::after {
    transform: scaleX(1);
  }

  .input {
    outline: none;
    border: none;
    overflow: hidden;
    margin: 0;
    padding: 0.25rem 0;
    background: none;
    color: white;
    font-size: 1.2rem;
    font-weight: bold;
  }

  .input:valid {
    color: yellowgreen;
  }
  .input:invalid {
    color: orangered;
  }
</style>

<main>
  <form>
    <div class="field">
      <input type="email" name="email" placeholder="" class="input" />
      <label for="email" class="label">Email</label>
    </div>

    <div class="field">
      <input type="password" name="password" placeholder="" class="input" />
      <label for="password" class="label">Password</label>
    </div>

    <div class="strength">
      <span class="bar bar-1" />
      <span class="bar bar-2" />
      <span class="bar bar-3" />
      <span class="bar bar-4" />

    </div>

    <ul>
      <li>Must be at least 6 characters</li>
      <li>Must contain a capital letter</li>
      <li>Must contain a number</li>
      <li>Must contain a special character</li>

    </ul>

  </form>
</main>
