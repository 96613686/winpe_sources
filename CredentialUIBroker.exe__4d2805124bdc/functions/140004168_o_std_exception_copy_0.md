# _o___std_exception_copy_0

- ea: `0x140004168`
- end: `0x14000416e`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140003f00`
- `0x140003f6c`
- `0x140003fd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140004168`

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
0x140004168  jmp     cs:__imp__o___std_exception_copy
```
