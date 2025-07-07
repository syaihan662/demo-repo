
import { useEffect, useState } from "react"

const Card = ({ title }) => {
  const [count, setCount] = useState(0)
  const [hasLiked, setHasLiked] = useState(false);

  useEffect(() => {
    console.log(`${title} has been Liked: ${hasLiked}`)
  }, [hasLiked])



  return (
    <div className="card" onClick={() => setCount(count + 1)}>
      <h2>{title} <br></br> {count || null}</h2>
      <button onClick={() => setHasLiked(!hasLiked)}>
        {hasLiked ? '❤️' : '🤍'}
      </button>
    </div>
  )
}

const App = () => {

  return (
    <div className="card-container">
      <Card title="Wednesday" rating={5} isCool={true} />
      <Card title="The King's Speech"/>
      <Card title="Attack on Titan"/>
    </div>

  )
}

export default App
