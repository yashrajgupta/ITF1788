SHELL = /bin/sh
OBJ = $(patsubst %.cpp,%,$(wildcard *.cpp))
TESTRESULT = $(patsubst %.cpp,%.run,$(wildcard *.cpp))
CXX ?= g++

.PHONY : all
all : $(OBJ) $(TESTRESULT)

% : %.cpp
	$(CXX) -o "$@" "$<" -lgaol -lgdtoa -lcrlibm  -lboost_unit_test_framework

%.run : %
	@echo
	@echo "[$<]"
	@"./$<" || true
	@touch "$@"
