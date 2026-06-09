# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18000ebec`
- end: `0x18000ec37`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `75`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ea78`
- `0x18000eb40`
- `0x18000f6a4`

## callees

- `0x18000ebec`
- `0x18000ec78`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(unsigned __int16 *a1, size_t a2, size_t *a3, size_t cchToCopy)
{
  unsigned int v4; // edx

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || cchToCopy > 0x7FFFFFFE )
    {
      v4 = -2147024809;
      *a1 = 0;
    }
    else
    {
      return (unsigned int)StringCopyWorkerW_0(a1, a2, a3, (STRSAFE_PCNZWCH)a3, cchToCopy);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18000ebec  sub     rsp, 38h
0x18000ebf0  mov     rax, rdx
0x18000ebf3  test    rdx, rdx
0x18000ebf6  jz      short loc_18000EC21
0x18000ebf8  cmp     rax, 7FFFFFFFh
0x18000ebfe  jbe     short loc_18000EC07
0x18000ec00  mov     edx, 80070057h; cchDest
0x18000ec05  jmp     short loc_18000EC2B
0x18000ec07  cmp     r9, 7FFFFFFEh
0x18000ec0e  ja      short loc_18000EC00
0x18000ec10  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x18000ec15  mov     r9, r8; pszSrc
0x18000ec18  call    StringCopyWorkerW_0
0x18000ec1d  mov     edx, eax
0x18000ec1f  jmp     short loc_18000EC30
0x18000ec21  mov     edx, 80070057h
0x18000ec26  test    rax, rax
0x18000ec29  jz      short loc_18000EC30
0x18000ec2b  xor     eax, eax
0x18000ec2d  mov     [rcx], ax
0x18000ec30  mov     eax, edx
0x18000ec32  add     rsp, 38h
0x18000ec36  retn
```
