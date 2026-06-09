# __std_exception_copy_0

- ea: `0x140002038`
- end: `0x14000203e`
- name: `__std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x140007c98`
- `0x140007e74`
- `0x14000d0c4`
- `0x14000d118`
- `0x14000d4f8`
- `0x14000d53c`
- `0x14000e410`
- `0x1400113b4`
- `0x1400113f8`
- `0x140011454`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x140002038`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _std_exception_copy_0(__int64 a1)
{
  return __std_exception_copy(a1);
}

```

## disassembly

```asm
0x140002038  jmp     cs:__imp___std_exception_copy
```
