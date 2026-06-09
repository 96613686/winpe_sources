# _o___std_exception_copy_0

- ea: `0x180001eb6`
- end: `0x180001ebc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000199c`
- `0x180001a08`
- `0x180001a74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001eb6`

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
0x180001eb6  jmp     cs:__imp__o___std_exception_copy
```
