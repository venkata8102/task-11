from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
from selenium.webdriver.common.by import By
import time
driver_path = '/path/to/chromedriver'  # Update this to the path of your ChromeDriver
driver = webdriver.Chrome(executable_path=driver_path)
driver.get('https://jqueryui.com/droppable/')
time.sleep(3)
driver.switch_to.frame(driver.find_element(By.XPATH, "//iframe[@class='demo-frame']"))
draggable = driver.find_element(By.ID, "draggable")
droppable = driver.find_element(By.ID, "droppable")
actions = ActionChains(driver)
actions.drag_and_drop(draggable, droppable).perform()
time.sleep(5)
driver.quit()
