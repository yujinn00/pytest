# pytest

##### test_sample.py #####



import pytest

def test_file1_method1():
  x = 5
  y = 6
  assert x + 1 == y, "Test Failed"
  # assert x == y, "Test Failed"

def test_file1_method2():
  x = 5
  y = 6
  assert x + 1 == y, "Test Failed"

def test_file1_method3():
  # assert "hello" == "Hai"
  assert 4 == 4
  assert True
  # assert False



##### test_sample1.py #####



import pytest

@pytest.mark.set1
def test_file1_method1():
  assert True

@pytest.mark.set2
def test_file1_method2():
  assert True



##### test_sample2.py #####



import pytest

@pytest.mark.set1
def test_file1_method1():
  assert True

@pytest.mark.set1
def test_file1_method2():
  assert True



##### solution.py #####



def solution(s):
  return s.isdigit() and len(s) in (4, 6)



##### test_sample3.py #####



# parametrize 사용 O
import pytest
from solution import solution

@pytest.mark.parametrize("input1, output", [("a123", False), ("1234", True), ("b12345", False)])
def test_example(input1, output):
  assert solution(input1) == output, "Failed"

@pytest.mark.parametrize("input1, output", [("", False), ("aaaaaaaaaa", False)])
def test_check_inputsize(input1, output):
  assert solution(input1) == output, "Failed"



##### test_sample4.py #####



# parametrize 사용 X
import pytest
from solution import solution

def test_example1():
  assert solution("a123") == False, "Failed"

def test_example2():
  assert solution("1234") == True, "Failed"
  
def test_example3():
  assert solution("b12345") == False, "Failed"
