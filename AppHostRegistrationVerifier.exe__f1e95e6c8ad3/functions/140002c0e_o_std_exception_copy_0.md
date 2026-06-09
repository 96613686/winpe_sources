# _o___std_exception_copy_0

- ea: `0x140002c0e`
- end: `0x140002c14`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400044e0`
- `0x140007a2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140002c0e`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall o___std_exception_copy_0(__int64 a1)
{
  return _o___std_exception_copy(a1);
}

```

## disassembly

```asm
0x140002c0e  jmp     cs:__imp__o___std_exception_copy
```
