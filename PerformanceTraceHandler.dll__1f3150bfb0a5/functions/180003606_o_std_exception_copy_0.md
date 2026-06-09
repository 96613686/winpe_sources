# _o___std_exception_copy_0

- ea: `0x180003606`
- end: `0x18000360c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004524`
- `0x180009850`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003606`

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
0x180003606  jmp     cs:__imp__o___std_exception_copy
```
