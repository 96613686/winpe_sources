# _o___std_exception_copy_0

- ea: `0x180005d26`
- end: `0x180005d2c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180009bd8`
- `0x180011f4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180005d26`

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
0x180005d26  jmp     cs:__imp__o___std_exception_copy
```
