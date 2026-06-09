# _o___std_exception_copy_0

- ea: `0x180004f02`
- end: `0x180004f08`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005ba0`
- `0x180005cb4`
- `0x18000b614`
- `0x18000b658`
- `0x18000f8b0`
- `0x18000f8f4`
- `0x18002aa14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180004f02`

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
0x180004f02  jmp     cs:__imp__o___std_exception_copy
```
