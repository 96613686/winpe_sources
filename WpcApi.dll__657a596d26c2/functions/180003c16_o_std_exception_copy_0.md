# _o___std_exception_copy_0

- ea: `0x180003c16`
- end: `0x180003c1c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180005ad4`
- `0x180005c44`
- `0x180005d58`
- `0x180005d9c`
- `0x180005e08`
- `0x18001b204`
- `0x180020f18`
- `0x18002107c`
- `0x180022610`
- `0x18002267c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003c16`

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
0x180003c16  jmp     cs:__imp__o___std_exception_copy
```
