
const Engine = Matter.Engine;
const World = Matter.World;
const Bodies = Matter.Bodies;
const Body = Matter.Body;

var world, engine;
var paperBall, ground;


function setup() {
	createCanvas(800, 700);

	engine = Engine.create();
	world = engine.world;

	//Create the Bodies Here.
	ground = new Ground(400,height,800,20)
	paperBall = new Garbage(100,100)
	leftBin = new Dustbin(505, 650, 20, 100)
	downBin = new Dustbin(550, 690, 100, 20)
	rightBin = new Dustbin(595, 650, 20, 100)
	Engine.run(engine);
  
}


function draw() {
  rectMode(CENTER);
  background(0);
  
  paperBall.display();
  ground.display();
  leftBin.display();
  rightBin.display();
  downBin.display();
 
  drawSprites();
 
}

function keyPressed(){
	if (keyCode === 32){
		Matter.Body.applyForce(paperBall.body,paperBall.body.position,{x:53,y:-57})
	}
}
