# m7_ippsCopy_8u

- ea: `0x180024d24`
- end: `0x180024d34`
- name: `m7_ippsCopy_8u`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800387d8`
- `0x1800388c4`

## callees

- `0x180060f20`

## pseudocode

```c
__int64 __fastcall m7_ippsCopy_8u(const __m128i *a1, __m128i *a2, __int64 a3)
{
  m7_ownsCopy_8u(a1, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x180024d24  sub     rsp, 28h
0x180024d28  call    m7_ownsCopy_8u
0x180024d2d  xor     eax, eax
0x180024d2f  add     rsp, 28h
0x180024d33  retn
```
