# _o___std_exception_copy_0

- ea: `0x180002046`
- end: `0x18000204c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180006f30`
- `0x180007044`
- `0x180009b48`
- `0x180009b8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002046`

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
0x180002046  jmp     cs:__imp__o___std_exception_copy
```
