# _o___std_exception_copy_0

- ea: `0x180003922`
- end: `0x180003928`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180004500`
- `0x180004614`
- `0x18000c748`
- `0x18000c7b4`
- `0x18000cdc8`
- `0x18000ce0c`
- `0x18000cfa4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003922`

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
0x180003922  jmp     cs:__imp__o___std_exception_copy
```
