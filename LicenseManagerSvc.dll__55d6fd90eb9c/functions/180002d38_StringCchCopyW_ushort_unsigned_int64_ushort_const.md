# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180002d38`
- end: `0x180002d75`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002908`
- `0x18000542c`
- `0x18000cc78`

## callees

- `0x180002d38`
- `0x180007228`

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
0x180002d38  sub     rsp, 38h
0x180002d3c  mov     rax, rdx
0x180002d3f  test    rdx, rdx
0x180002d42  jz      short loc_180002D5F
0x180002d44  cmp     rax, 7FFFFFFFh
0x180002d4a  jbe     short loc_180002D53
0x180002d4c  mov     edx, 80070057h; cchDest
0x180002d51  jmp     short loc_180002D69
0x180002d53  mov     r9, r8; pszSrc
0x180002d56  call    StringCopyWorkerW
0x180002d5b  mov     edx, eax
0x180002d5d  jmp     short loc_180002D6E
0x180002d5f  mov     edx, 80070057h
0x180002d64  test    rax, rax
0x180002d67  jz      short loc_180002D6E
0x180002d69  xor     eax, eax
0x180002d6b  mov     [rcx], ax
0x180002d6e  mov     eax, edx
0x180002d70  add     rsp, 38h
0x180002d74  retn
```
