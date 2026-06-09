# _o___std_exception_copy_0

- ea: `0x1800164f6`
- end: `0x1800164fc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007708`
- `0x1800139f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800164f6`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall o___std_exception_copy_0(__int64 a1, __int64 a2)
{
  return _o___std_exception_copy(a1, a2);
}

```

## disassembly

```asm
0x1800164f6  jmp     cs:__imp__o___std_exception_copy
```
