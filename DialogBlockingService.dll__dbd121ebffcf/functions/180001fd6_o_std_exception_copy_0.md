# _o___std_exception_copy_0

- ea: `0x180001fd6`
- end: `0x180001fdc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180003a40`
- `0x180003b54`
- `0x180003b98`
- `0x180003c04`
- `0x18000972c`
- `0x180009780`
- `0x1800097c4`
- `0x180009824`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001fd6`

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
0x180001fd6  jmp     cs:__imp__o___std_exception_copy
```
