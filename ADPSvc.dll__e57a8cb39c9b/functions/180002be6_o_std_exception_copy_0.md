# _o___std_exception_copy_0

- ea: `0x180002be6`
- end: `0x180002bec`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1800045d8`
- `0x1800046ec`
- `0x180004758`
- `0x180004790`
- `0x1800047d4`
- `0x18000c278`
- `0x1800134a4`
- `0x1800136b8`
- `0x180013718`
- `0x180025dbc`
- `0x180025e14`
- `0x18003052c`
- `0x18003058c`
- `0x1800305f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002be6`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x180002be6  jmp     cs:__imp__o___std_exception_copy
```
