# _o___std_exception_copy_0

- ea: `0x18000319e`
- end: `0x1800031a4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003340`
- `0x1800033ac`
- `0x180003418`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000319e`

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
0x18000319e  jmp     cs:__imp__o___std_exception_copy
```
