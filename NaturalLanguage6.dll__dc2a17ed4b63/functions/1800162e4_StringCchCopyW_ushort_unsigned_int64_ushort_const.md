# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800162e4`
- end: `0x180016321`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dd64`
- `0x1800146f0`
- `0x180016ea0`
- `0x18003bd7c`
- `0x18003dcd0`
- `0x180041dc8`
- `0x1800437d8`
- `0x180049b2c`
- `0x18004aa70`
- `0x18004c248`
- `0x18004c3b0`
- `0x18004c460`
- `0x180053550`
- `0x180053820`
- `0x180054a98`
- `0x18005b074`
- `0x18005d9f4`
- `0x18005da80`
- `0x180066238`
- `0x18006cdf4`
- `0x180071838`
- `0x180073834`
- `0x180074070`
- `0x180098848`
- `0x180098f8c`

## callees

- `0x1800162e4`
- `0x180016328`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF )
    {
      v3 = -2147024809;
      *a1 = 0;
    }
    else
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x1800162e4  sub     rsp, 38h
0x1800162e8  mov     rax, rdx
0x1800162eb  test    rdx, rdx
0x1800162ee  jz      short loc_180016310
0x1800162f0  cmp     rax, 7FFFFFFFh
0x1800162f6  ja      short loc_180016309
0x1800162f8  mov     r9, r8; pszSrc
0x1800162fb  call    StringCopyWorkerW
0x180016300  mov     edx, eax
0x180016302  mov     eax, edx
0x180016304  add     rsp, 38h
0x180016308  retn
0x180016309  mov     edx, 80070057h
0x18001630e  jmp     short loc_18001631A
0x180016310  mov     edx, 80070057h
0x180016315  test    rax, rax
0x180016318  jz      short loc_180016302
0x18001631a  xor     eax, eax
0x18001631c  mov     [rcx], ax
0x18001631f  jmp     short loc_180016302
```
