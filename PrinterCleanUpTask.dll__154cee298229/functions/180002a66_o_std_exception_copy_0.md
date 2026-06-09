# _o___std_exception_copy_0

- ea: `0x180002a66`
- end: `0x180002a6c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800037c8`
- `0x180007340`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002a66`

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
0x180002a66  jmp     cs:__imp__o___std_exception_copy
```
