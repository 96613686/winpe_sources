# StringCchCopyW

- ea: `0x18000da50`
- end: `0x18000dabc`
- name: `StringCchCopyW`
- size: `108`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011ea8`
- `0x180016318`

## callees

- `0x18000da50`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  __int64 v4; // rax
  HRESULT result; // eax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -2147024809;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x8007007A : 0;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x18000da50  xor     r10d, r10d
0x18000da53  mov     r9, rcx
0x18000da56  test    rdx, rdx
0x18000da59  jz      short loc_18000DAB0
0x18000da5b  cmp     rdx, 7FFFFFFFh
0x18000da62  ja      short loc_18000DAA9
0x18000da64  mov     eax, 7FFFFFFEh
0x18000da69  test    rax, rax
0x18000da6c  jz      short loc_18000DA8C
0x18000da6e  movzx   ecx, word ptr [r8]
0x18000da72  test    cx, cx
0x18000da75  jz      short loc_18000DA8C
0x18000da77  mov     [r9], cx
0x18000da7b  add     r8, 2
0x18000da7f  add     r9, 2
0x18000da83  dec     rax
0x18000da86  sub     rdx, 1
0x18000da8a  jnz     short loc_18000DA69
0x18000da8c  test    rdx, rdx
0x18000da8f  lea     rcx, [r9-2]
0x18000da93  cmovnz  rcx, r9
0x18000da97  neg     rdx
0x18000da9a  sbb     eax, eax
0x18000da9c  not     eax
0x18000da9e  and     eax, 8007007Ah
0x18000daa3  mov     [rcx], r10w
0x18000daa7  retn
0x18000daa9  mov     eax, 80070057h
0x18000daae  jmp     short loc_18000DAA3
0x18000dab0  mov     eax, 80070057h
0x18000dab5  test    rdx, rdx
0x18000dab8  jz      short locret_18000DAA7
0x18000daba  jmp     short loc_18000DAA3
```
