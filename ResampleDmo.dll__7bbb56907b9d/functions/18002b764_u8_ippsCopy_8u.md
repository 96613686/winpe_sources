# u8_ippsCopy_8u

- ea: `0x18002b764`
- end: `0x18002b774`
- name: `u8_ippsCopy_8u`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800406c0`
- `0x1800407c0`

## callees

- `0x180044170`

## pseudocode

```c
__int64 __fastcall u8_ippsCopy_8u(const __m128i *a1, __m128i *a2, __int64 a3)
{
  u8_ownsCopy_8u(a1, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x18002b764  sub     rsp, 28h
0x18002b768  call    u8_ownsCopy_8u
0x18002b76d  xor     eax, eax
0x18002b76f  add     rsp, 28h
0x18002b773  retn
```
