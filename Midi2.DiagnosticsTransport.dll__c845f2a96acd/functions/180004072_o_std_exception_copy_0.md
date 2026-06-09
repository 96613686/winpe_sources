# _o___std_exception_copy_0

- ea: `0x180004072`
- end: `0x180004078`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004b3c`
- `0x180004c50`
- `0x18000c874`
- `0x18000c8b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180004072`

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
0x180004072  jmp     cs:__imp__o___std_exception_copy
```
