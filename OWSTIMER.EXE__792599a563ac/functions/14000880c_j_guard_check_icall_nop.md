# j__guard_check_icall_nop

- ea: `0x14000880c`
- end: `0x140008813`
- name: `j__guard_check_icall_nop`
- size: `7`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140007ecc`
- `0x140008768`
- `0x1400087c0`

## callees

- `0x140006f10`

## pseudocode

```c
// attributes: thunk
void __fastcall j__guard_check_icall_nop()
{
  ;
}

```

## disassembly

```asm
0x14000880c  jmp     cs:__guard_check_icall_fptr
```
