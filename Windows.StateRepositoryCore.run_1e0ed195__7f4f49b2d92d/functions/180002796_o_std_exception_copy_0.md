# _o___std_exception_copy_0

- ea: `0x180002796`
- end: `0x18000279c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a50`
- `0x180002abc`
- `0x1800039b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002796`

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
0x180002796  jmp     cs:__imp__o___std_exception_copy
```
