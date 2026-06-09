# _o___std_exception_copy_0

- ea: `0x18000a0ce`
- end: `0x18000a0d4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a290`
- `0x18000a2fc`
- `0x18000a368`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000a0ce`

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
0x18000a0ce  jmp     cs:__imp__o___std_exception_copy
```
