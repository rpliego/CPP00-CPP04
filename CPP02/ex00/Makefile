NAME = OCCF

CC = c++
FLAGS = -Wall -Wextra -Werror -g -fsanitize=address -std=c++98

SRC_DIR = src/
OBJ_DIR = obj/
INC_DIR = inc/

SRCS = $(SRC_DIR)main.cpp $(SRC_DIR)Fixed.cpp
OBJS = $(SRCS:$(SRC_DIR)%.cpp=$(OBJ_DIR)%.o)

all: $(NAME)

$(NAME): $(OBJS) inc/Fixed.hpp
	$(CC) $(FLAGS) -o $(NAME) $(OBJS)

$(OBJ_DIR)%.o: $(SRC_DIR)%.cpp | $(OBJ_DIR)
	$(CC) $(FLAGS) -I $(INC_DIR) -c $< -o $@

$(OBJ_DIR):
	mkdir -p $(OBJ_DIR)

clean:
	rm -rf $(OBJ_DIR)

fclean: clean
	rm -f $(NAME)

re: fclean all

.PHONY: all clean fclean re
