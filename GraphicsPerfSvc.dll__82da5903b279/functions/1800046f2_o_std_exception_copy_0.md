# _o___std_exception_copy_0

- ea: `0x1800046f2`
- end: `0x1800046f8`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800058b4`
- `0x18000e50c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800046f2`

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
0x1800046f2  jmp     cs:__imp__o___std_exception_copy
```
