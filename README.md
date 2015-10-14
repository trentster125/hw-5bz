# hw-5bz

class Player {
  float x, y;

  Player(float x) {
    this.x = x;
    this.y =y;
  }

  void draw(float y) {
    noStroke();
    fill(255);
    rect(x,this.y=y, 8, 35);
  }

  void move() {
    
    }
  }

class Ball {
  float x, y;
  float vx, vy;
  float size = 8;
  color c;

  Ball(float x, float y) {
    this.x = x;
    this.y = y;
    c = color(255);
    vx = random(5);
    vy = random(5);
  }

  void draw() {
    noStroke();
    fill(c);
    ellipse(x, y, size*2, size*2);
  }

  void move() {
    x += vx;
    y += vy;
    if (x < size || x > width-size) {
      vx = -vx;
    }
    if (y < size || y > height-size) {
      vy = -vy;
    }
  }
}

Ball b;
Player p;
Player p2;

void setup() {
  size(500, 500);
  colorMode(HSB); 
  b = new Ball(250,250);
  p = new Player(7);
  p2 = new Player(485);
}

void draw() {
  background(0);
  b.draw();
  b.move();
  p.draw(mouseY);
  p2.draw(mouseY-15);
}
