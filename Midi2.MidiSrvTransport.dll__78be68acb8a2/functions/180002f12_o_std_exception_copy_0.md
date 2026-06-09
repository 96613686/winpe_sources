# _o___std_exception_copy_0

- ea: `0x180002f12`
- end: `0x180002f18`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002ac8`
- `0x180002b34`
- `0x1800039dc`
- `0x180003af0`
- `0x18000d060`
- `0x18000d0a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002f12`

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
0x180002f12  jmp     cs:__imp__o___std_exception_copy
```
