# _o___std_exception_copy_0

- ea: `0x180002516`
- end: `0x18000251c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003dd8`
- `0x180003eec`
- `0x18000a844`
- `0x18000a888`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002516`

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
0x180002516  jmp     cs:__imp__o___std_exception_copy
```
