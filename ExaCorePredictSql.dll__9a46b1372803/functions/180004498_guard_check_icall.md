# _guard_check_icall

- ea: `0x180004498`
- end: `0x18000449f`
- name: `_guard_check_icall`
- size: `7`
- prototype: `void __fastcall(uintptr_t Target)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a94`
- `0x180003b00`
- `0x180003c2c`
- `0x180003fd0`
- `0x180004278`
- `0x1800048b8`
- `0x180004910`

## callees

- `0x180002aa0`

## pseudocode

```c
// attributes: thunk
void __fastcall guard_check_icall(uintptr_t Target)
{
  ;
}

```

## disassembly

```asm
0x180004498  jmp     cs:__guard_check_icall_fptr
```
