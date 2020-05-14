<script>
	// Hmm semicolons aren't mandatory...I like
	let user = {name: "Mary", age: 40, member: false}
	let isAdmin = false

	const toggleMember = () => {user.member = !user.member}

	$: isAdmin = user.name === "John" // put a little reactivity on isAdmin to user.name
</script>

<main>
	<span class="heading1">Hello {user.name}!</span>

	<span class="subtitle">{#if isAdmin} (Admin){:else if user.member} (Member) {/if}</span>

	<div>
		<input type="text" bind:value={user.name}>
		<button on:click={toggleMember}>Toggle Member</button>
	</div>

	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
		to learn how to build Svelte apps.</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	span.heading1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 2.8em;
		font-weight: 200;
	}

	span.subtitle {
		font-size: 0.9em;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>