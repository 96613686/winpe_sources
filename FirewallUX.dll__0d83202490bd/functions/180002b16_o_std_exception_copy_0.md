# _o___std_exception_copy_0

- ea: `0x180002b16`
- end: `0x180002b1c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180004e78`
- `0x180004f8c`
- `0x180004ff8`
- `0x180005510`
- `0x180005554`
- `0x18000eef0`
- `0x18000ef5c`
- `0x180015f60`
- `0x180015fb4`
- `0x180016030`
- `0x180016090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002b16`

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
0x180002b16  jmp     cs:__imp__o___std_exception_copy
```
