# _o___std_exception_copy_0

- ea: `0x180002aec`
- end: `0x180002af2`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180014b50`
- `0x180014d2c`
- `0x180014d70`
- `0x180014ddc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002aec`

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
0x180002aec  jmp     cs:__imp__o___std_exception_copy
```
