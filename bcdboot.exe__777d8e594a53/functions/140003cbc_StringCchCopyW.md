# StringCchCopyW

- ea: `0x140003cbc`
- end: `0x140003d27`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140009bdc`
- `0x14000c024`
- `0x14000f344`
- `0x14000f50c`
- `0x140013278`

## callees

- `0x140003cbc`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  HRESULT result; // eax
  __int64 v5; // rax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v5;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x140003cbc  xor     r10d, r10d
0x140003cbf  mov     r9, rcx
0x140003cc2  test    rdx, rdx
0x140003cc5  jz      short loc_140003D18
0x140003cc7  cmp     rdx, 7FFFFFFFh
0x140003cce  jbe     short loc_140003CD7
0x140003cd0  mov     eax, 80070057h
0x140003cd5  jmp     short loc_140003D22
0x140003cd7  mov     eax, 7FFFFFFEh
0x140003cdc  test    rax, rax
0x140003cdf  jz      short loc_140003CFF
0x140003ce1  movzx   ecx, word ptr [r8]
0x140003ce5  test    cx, cx
0x140003ce8  jz      short loc_140003CFF
0x140003cea  mov     [r9], cx
0x140003cee  add     r8, 2
0x140003cf2  add     r9, 2
0x140003cf6  dec     rax
0x140003cf9  sub     rdx, 1
0x140003cfd  jnz     short loc_140003CDC
0x140003cff  test    rdx, rdx
0x140003d02  lea     rcx, [r9-2]
0x140003d06  cmovnz  rcx, r9
0x140003d0a  neg     rdx
0x140003d0d  sbb     eax, eax
0x140003d0f  not     eax
0x140003d11  and     eax, 8007007Ah
0x140003d16  jmp     short loc_140003D22
0x140003d18  mov     eax, 80070057h
0x140003d1d  test    rdx, rdx
0x140003d20  jz      short locret_140003D26
0x140003d22  mov     [rcx], r10w
0x140003d26  retn
```
