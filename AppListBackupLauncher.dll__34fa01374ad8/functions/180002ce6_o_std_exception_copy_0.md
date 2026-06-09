# _o___std_exception_copy_0

- ea: `0x180002ce6`
- end: `0x180002cec`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ec8`
- `0x1800050a4`
- `0x180005110`
- `0x18000517c`
- `0x18000569c`
- `0x1800056e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002ce6`

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
0x180002ce6  jmp     cs:__imp__o___std_exception_copy
```
