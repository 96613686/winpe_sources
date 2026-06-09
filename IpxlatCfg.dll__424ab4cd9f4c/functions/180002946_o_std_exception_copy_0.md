# _o___std_exception_copy_0

- ea: `0x180002946`
- end: `0x18000294c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180003db0`
- `0x180003f8c`
- `0x18000ed18`
- `0x18000efdc`
- `0x18000f030`
- `0x18000f074`
- `0x18000f0e0`
- `0x18000f124`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002946`

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
0x180002946  jmp     cs:__imp__o___std_exception_copy
```
