# _o___std_exception_copy_0

- ea: `0x1800027e2`
- end: `0x1800027e8`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003288`
- `0x18000339c`
- `0x18000a700`
- `0x18000a744`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800027e2`

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
0x1800027e2  jmp     cs:__imp__o___std_exception_copy
```
