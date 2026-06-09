# _o___std_exception_copy_0

- ea: `0x180002196`
- end: `0x18000219c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800046ec`
- `0x1800048c8`
- `0x180004934`
- `0x1800049a0`
- `0x180004f80`
- `0x180004fc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002196`

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
0x180002196  jmp     cs:__imp__o___std_exception_copy
```
