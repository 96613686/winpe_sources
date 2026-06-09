# _o___std_exception_copy_0

- ea: `0x14000a287`
- end: `0x14000a28d`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001308`
- `0x1400025cc`
- `0x14000d3d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x14000a287`

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
0x14000a287  jmp     cs:__imp__o___std_exception_copy
```
