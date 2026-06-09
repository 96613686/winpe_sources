# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005384`
- end: `0x1800053c2`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `62`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180003470`
- `0x180005548`
- `0x180007880`
- `0x180007d70`
- `0x1800080f8`
- `0x1800083c0`
- `0x180008830`
- `0x180008980`
- `0x180008db0`
- `0x180008e10`
- `0x1800092d0`
- `0x180009340`

## callees

- `0x180005384`
- `0x18000542c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
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
0x180005384  sub     rsp, 38h
0x180005388  mov     rax, rdx
0x18000538b  test    rdx, rdx
0x18000538e  jz      short loc_1800053AB
0x180005390  cmp     rax, 7FFFFFFFh
0x180005396  jbe     short loc_18000539F
0x180005398  mov     edx, 80070057h; cchDest
0x18000539d  jmp     short loc_1800053B5
0x18000539f  mov     r9, r8; pszSrc
0x1800053a2  call    StringCopyWorkerW
0x1800053a7  mov     edx, eax
0x1800053a9  jmp     short loc_1800053BA
0x1800053ab  mov     edx, 80070057h
0x1800053b0  test    rax, rax
0x1800053b3  jz      short loc_1800053BA
0x1800053b5  xor     eax, eax
0x1800053b7  mov     [rcx], ax
0x1800053ba  mov     eax, edx
0x1800053bc  add     rsp, 38h
0x1800053c0  retn
```
