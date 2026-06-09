# _o___std_exception_copy_0

- ea: `0x180001f06`
- end: `0x180001f0c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002aa8`
- `0x180002bbc`
- `0x180005ee4`
- `0x180005f50`
- `0x180006614`
- `0x180006658`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001f06`

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
0x180001f06  jmp     cs:__imp__o___std_exception_copy
```
