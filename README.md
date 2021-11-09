# Pokedex

My second project as part of General Assembly’s Software Engineering Immersive Bootcamp was a pair-programming 2 day hack-a-thon. I worked alongside my coursemate Jason to build a PokéDex React app that acts as a web based pokedex based on the popular game/show Pokémon. 

View [here](https://pokereactdex.netlify.app/).

<img width="899" alt="Screenshot 2021-11-04 at 17 36 09" src="https://user-images.githubusercontent.com/87997491/140390517-7319341f-fd90-4676-a266-64f3dc6ef1a0.png">

# Code installation

* Clone or download the repo
* Install yarn in Terminal by typing: __yarn__
* Start server with __yarn start__

# Goal
  Application must :
* Consume a public API.
* Have several components.
* Be deployed online.

# Technology Used
* HTML5
* CSS3
* SASS
* JavaScript ES6
* React
* Insomnia
* Git
* GitHub
* Chrome dev tools

# Approach and Timeline
__Day 1__ <br />
We spent about an hour looking for a suitable API, something that was concise and straightforward but also contained plenty of info that we could have fun working with. We were delighted to find the pokemon API - we both enjoyed Pokemon as kids plus it didn’t require any authentication. We used insomnia to take a closer look at the data and explore endpoints.

<img width="894" alt="Screenshot 2021-11-04 at 17 39 46" src="https://user-images.githubusercontent.com/87997491/140391071-0c730a33-e28b-4ec7-8d7f-b0a1bccb8c4d.png">

We then began planning what we wanted our app to look like. We decided we wanted to have a search function and a filter function that allows users to filter the Pokemon by type e.g grass, poison, rock, etc. With this in mind, we began mapping out our data and building these functions.

```
return (
    <>
      <div className='main-part'>
        <Navbar filters={filters} setFilters={setFilters}/>
      
        <div className='pokemon-list'>
          {pokemon.length > 0 ?
        
            ( filters.type !== '' || filters.searchTerm !== '' ? filteredPokemon : pokemon ).map(item => {

              return (         
                <>
                  <div className={item.type[0]} >
                    <Link key={item.id} to={`/pokemon/${item.id}`}>                    
                      <p value={item.id}>No.{item.id}</p>
                      <p value={item.name.english}>{item.name.english}</p>
                      <img src={item.hires} alt='pokemon'/>                   
                    </Link>  
                  </div>   
                </>
              )
            })
            :
            <>
              {hasError ? 
                <h4>Oh! Something went wrong.</h4> 
                :
                <h4>Loading...</h4>}
            </>
            
          }
        </div>  
      </div>
    </>
  )
  ```
  We both worked on the components together using VSCode Live Share, building and styling each component as we went.

__Day 2__ <br />
We spent our final day building the individual Pokemon cards that display details about the Pokemon clicked such as their Japanese name, sprite, type, weight/height etc. On this page, users can also jump to next or previous evolutions if available. Another component included 'Who's that Pokemon?', which generated a random Pokemon from the database.

```
{pokemons.evolution.prev && pokemons.evolution.next  
                ?
                <div className="evolutions">
                  <div className="prev"> 
                    <Link to={`/pokemon/${pokemons.evolution.prev[0]}`}><button className='evolution'>Prev Evolution</button></Link>
                  </div>
                  <div className="next">
                    <Link to={`/pokemon/${pokemons.evolution.next[0][0]}`}><button className='evolution'>Next Evolution</button></Link>
                  </div>
                </div> 
                :
                pokemons.evolution.prev ?
                  <div className="evolutions">
                    <div className="prev"> 
                      <Link to={`/pokemon/${pokemons.evolution.prev[0]}`}><button className='evolution'> Prev Evolution</button></Link>
                    </div>
                  </div>
                  :
                  pokemons.evolution.next ?
                    <div className="evolutions">
                      <div className="next"> 
                        <Link to={`/pokemon/${pokemons.evolution.next[0][0]}`}><button className='evolution'> Next Evolution</button></Link>
                      </div>
                    </div>
                    :
                    <p>No Evolutions</p>
              }
```

__Styling__
We styled primarily using Sass, and used google font Press Start 2P to give an authentic 90’s video game look to the app. Using Sass, we were able to use the @each rule to easily style each of the 900 pokemons on the list page as per their first type according to their data.
```
$typeColours: (
  "Normal":#A8A77A,
  "Fire":#EE8130,
  "Water":#6390F0,
  "Grass":#7AC74C,
  "Electric":#F7D02C,
  "Ice":#96D9D6,
  "Fighting":#C22E28,
  "Poison":#A33EA1,
  "Ground":#E2BF65,
  "Flying":#A98FF3,
  "Psychic":#F95587,
  "Bug":#A6B91A,
  "Rock":#B6A136,
  "Ghost":#735797,
  "Dark":#705746,
  "Dragon":#6F35FC,
  "Steel":#B7B7CE,
  "Fairy":#D685AD
);
```

<img width="1427" alt="Screenshot 2021-11-04 at 17 47 48" src="https://user-images.githubusercontent.com/87997491/140392264-1d20d48e-4b85-431f-b629-c9b7de6e5a4e.png">

# Wins and Challenges
* We’re both very happy with how the app turned out - in style and functionality.
* Timing prevented us from adding extra bits such as a load more button at the bottom of the list page that allows you to load more results.

# Key Learnings
* This was my first time working in a pair. It was a lot of fun to bounce ideas off one another and work together to build something in the way we envisioned it. 
* ReactJs - This was my first React app. I put into practise for the first time my knowledge and understanding of hooks and state.





