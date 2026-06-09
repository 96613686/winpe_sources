# _o___std_exception_destroy_0

- ea: `0x1800027ee`
- end: `0x1800027f4`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800035c4`
- `0x1800038a0`
- `0x18000a820`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x1800027ee`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_destroy_0()
{
  return __std_exception_destroy();
}

```

## disassembly

```asm
0x1800027ee  jmp     cs:__imp___std_exception_destroy
```
