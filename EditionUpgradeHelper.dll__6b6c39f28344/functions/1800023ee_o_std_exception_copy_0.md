# _o___std_exception_copy_0

- ea: `0x1800023ee`
- end: `0x1800023f4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800021ac`
- `0x180002218`
- `0x180002284`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800023ee`

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
0x1800023ee  jmp     cs:__imp__o___std_exception_copy
```
