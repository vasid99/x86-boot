NASM := nasm

USR_DIR ?= .
SRC_DIR := $(USR_DIR)/src
OUT_DIR := $(USR_DIR)/output

all: $(OUT_DIR)/kernel.bin

clean:
	rm -rf $(OUT_DIR)

$(OUT_DIR)/kernel.bin: $(SRC_DIR)/kernel.asm
	mkdir -p $(OUT_DIR)
	$(NASM) -f bin -o $@ $^

run:
	qemu-system-x86_64 -drive file=$(OUT_DIR)/kernel.bin,format=raw
