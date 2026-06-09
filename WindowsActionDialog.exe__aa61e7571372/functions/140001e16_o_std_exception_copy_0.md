# _o___std_exception_copy_0

- ea: `0x140001e16`
- end: `0x140001e1c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002f28`
- `0x14000303c`
- `0x140003080`
- `0x1400030ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140001e16`

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
0x140001e16  jmp     cs:__imp__o___std_exception_copy
```
