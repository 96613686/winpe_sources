# StringCchCopyA

- ea: `0x180014a40`
- end: `0x180014aa2`
- name: `StringCchCopyA`
- size: `98`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fd0`
- `0x180002f80`
- `0x180011b40`

## callees

- `0x180014a40`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  __int64 v4; // rax
  STRSAFE_LPSTR v5; // rax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    v5 = pszDest - 1;
    if ( cchDest )
      v5 = pszDest;
    *v5 = 0;
    return cchDest == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180014a40  test    rdx, rdx
0x180014a43  jz      short loc_180014A94
0x180014a45  cmp     rdx, 7FFFFFFFh
0x180014a4c  jbe     short loc_180014A55
0x180014a4e  mov     eax, 80070057h
0x180014a53  jmp     short loc_180014A9E
0x180014a55  mov     eax, 7FFFFFFEh
0x180014a5a  test    rax, rax
0x180014a5d  jz      short loc_180014A79
0x180014a5f  mov     r9b, [r8]
0x180014a62  test    r9b, r9b
0x180014a65  jz      short loc_180014A79
0x180014a67  mov     [rcx], r9b
0x180014a6a  inc     r8
0x180014a6d  inc     rcx
0x180014a70  dec     rax
0x180014a73  sub     rdx, 1
0x180014a77  jnz     short loc_180014A5A
0x180014a79  test    rdx, rdx
0x180014a7c  lea     rax, [rcx-1]
0x180014a80  cmovnz  rax, rcx
0x180014a84  neg     rdx
0x180014a87  mov     byte ptr [rax], 0
0x180014a8a  sbb     eax, eax
0x180014a8c  not     eax
0x180014a8e  and     eax, 8007007Ah
0x180014a93  retn
0x180014a94  mov     eax, 80070057h
0x180014a99  test    rdx, rdx
0x180014a9c  jz      short locret_180014AA1
0x180014a9e  mov     byte ptr [rcx], 0
0x180014aa1  retn
```
