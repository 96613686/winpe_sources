# _o___std_exception_copy_0

- ea: `0x180001eae`
- end: `0x180001eb4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002374`
- `0x1800023e0`
- `0x18000244c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001eae`

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
0x180001eae  jmp     cs:__imp__o___std_exception_copy
```
