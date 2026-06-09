# _o___std_exception_copy_0

- ea: `0x180003ff6`
- end: `0x180003ffc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180006010`
- `0x180006124`
- `0x180006168`
- `0x1800061d4`
- `0x180012044`
- `0x1800120b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003ff6`

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
0x180003ff6  jmp     cs:__imp__o___std_exception_copy
```
