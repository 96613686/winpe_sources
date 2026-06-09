# _o___std_exception_copy_0

- ea: `0x180002cc6`
- end: `0x180002ccc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f54`
- `0x180003068`
- `0x180005814`
- `0x180005858`
- `0x18000f700`
- `0x18000f754`
- `0x18000f7d0`
- `0x18000f814`
- `0x18000f874`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002cc6`

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
0x180002cc6  jmp     cs:__imp__o___std_exception_copy
```
