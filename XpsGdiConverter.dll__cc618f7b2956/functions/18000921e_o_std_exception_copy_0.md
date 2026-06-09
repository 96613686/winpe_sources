# _o___std_exception_copy_0

- ea: `0x18000921e`
- end: `0x180009224`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a840`
- `0x18003715c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000921e`

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
0x18000921e  jmp     cs:__imp__o___std_exception_copy
```
