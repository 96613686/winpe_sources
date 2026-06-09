# _o___std_exception_copy_0

- ea: `0x140002d6e`
- end: `0x140002d74`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140007cd8`
- `0x140007dec`
- `0x140007e30`
- `0x140007e9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140002d6e`

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
0x140002d6e  jmp     cs:__imp__o___std_exception_copy
```
