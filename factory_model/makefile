# 编译器和编译选项
CC = gcc
CFLAGS = -Wall -g
LDFLAGS =

# 源文件目录和生成文件目录
SRC_DIR = src
OBJ_DIR = obj
BIN_DIR = test

# 所有C源文件
C_SRCS = $(wildcard $(SRC_DIR)/*.c)

# 目标文件列表（对应每个C源文件）
C_OBJS = $(patsubst $(SRC_DIR)/%.c, $(OBJ_DIR)/%.o, $(C_SRCS))

# 目标可执行文件
TARGET = ./test_pragram
SRC_BIN = $(BIN_DIR)/test.c
# 默认目标：构建可执行文件
all: create_directory $(TARGET)

# 生成可执行文件
$(TARGET): $(C_OBJS)
	$(CC) $(CFLAGS) $(SRC_BIN) $(LDFLAGS) -o $@ $^

# 生成目标文件（C源文件）
$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c
	$(CC) $(CFLAGS) -c -o $@ $<

create_directory:
	mkdir -p $(OBJ_DIR)

# 清理生成的文件
clean:
	rm -rf $(OBJ_DIR) $(TARGET) 

# 指定伪目标，防止文件名与目标名冲突
.PHONY: all clean create_directory
