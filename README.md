# pingpong

from pygame import *
'''Required classes'''


#parent class for sprites
class GameSprite(sprite.Sprite):
   def __init__(self, player_image, player_x, player_y, player_speed, wight, height):
       super().__init__()
       self.image = transform.scale(image.load(player_image), (wight, height)) #e.g. 55,55 - parameters
       self.speed = player_speed
       self.rect = self.image.get_rect()
       self.rect.x = player_x
       self.rect.y = player_y


   def reset(self):
       window.blit(self.image, (self.rect.x, self.rect.y))

class player(GameSprite):
  def update_r(self):
      keys = key.get_pressed()
      if keys[K_UP] and self.rect.y > 5:
      self.rect.y -= self.speed
      if keys[K_DOWN] and self.rect.y < win_height - 80:
      self.rect.y +=self.speeed
  def update_l(self):
  keys = key.get_pressed()
  if keys[K_w] and self.rect.y > 5:
    self.rect.y -= self.speed
  if keys[K_s] and self.rect.y < win_hieght - 80:
        self.rect.y += self.speed


#game scene:
