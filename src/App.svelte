<script>
	let src = 'https://upload.wikimedia.org/wikipedia/commons/thumb/6/67/Rock-paper-scissors.svg/800px-Rock-paper-scissors.svg.png';
	let Rock = 'https://res.cloudinary.com/itsellej/image/upload/v1533400140/rock-paper-scissors/rock.png';
	let Paper = 'https://flyclipart.com/rock-paper-scissors-game-rock-paper-scissors-clipart-246511';
	let Scissors ='https://res.cloudinary.com/itsellej/image/upload/v1533400144/rock-paper-scissors/scissors.png';
	let name = 'Rock Paper Scissors';
	let R='Rock';
	let P='Paper';
	let S='Scissors';
	let inputvalue = 0;
	let playername = '';
	let computervalue = generateRandomIntegerInRange(1, 3);
function generateRandomIntegerInRange(min, max) 
  {
    return Math.floor(Math.random() * (max - min + 1)) + min;
  }

	function UserinputR()
	{inputvalue = 1;
	computervalue = generateRandomIntegerInRange(1, 3);}
	function UserinputP()
	{inputvalue = 2;
	computervalue = generateRandomIntegerInRange(1, 3);}
	function UserinputS()
	{inputvalue = 3;
	computervalue = generateRandomIntegerInRange(1, 3);}
	$: if (inputvalue == 1 & computervalue ==1 ) 
		{
			alert('Draw Game');
		}
	$: if (inputvalue == 1 & computervalue ==2 ) 
		{
			alert('You lost the game');
		}
	$: if (inputvalue == 1 & computervalue ==3 ) 
		{
			alert('You won the game');
		}
	$: if (inputvalue == 2 & computervalue ==1 ) 
		{
			alert('You won the game');
		}
	$: if (inputvalue == 2 & computervalue ==2 ) 
		{
			alert('Draw Game');
		}
	$: if (inputvalue == 2 & computervalue ==3 ) 
		{
			alert('You lost the game');
		}
	$: if (inputvalue == 3 & computervalue ==1 ) 
		{
			alert('You lost the game');
		}
	$: if (inputvalue == 3 & computervalue ==2 ) 
		{
			alert('You won the game');
		}
	$: if (inputvalue == 3 & computervalue ==3 ) 
		{
			alert('Draw Game');
		}

</script>

<img {src} alt="{name} game is loading.">
<p>Enter your name</p>

<style>
	p {
		color: Black;
		font-family: 'Times New Roman', cursive;
		font-size: 2em;
	}
		button:hover {
		background-position: 0;
		color: #aaa;
	}
</style>


<input bind:value={playername}>

<h1>Hello {playername}!</h1>
<h2> Welcome to the game </h2>
<button on:click ={UserinputR}>
	<img {Rock} alt="{R} is loading">
</button>
<button on:click ={UserinputP}>
	<img {Paper} alt="{P} is loading">
</button>
<button on:click ={UserinputS}>
	<img {Scissors} alt="{S} is loading">
</button>
{#if computervalue == 1}
	<p>Computer's input is Rock</p>
{:else if computervalue == 2}
	<p>Computer's input is Paper</p>
{:else}
	<p>Computer's input is Scissors</p>
{/if}






