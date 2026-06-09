# StringCchCopyW

- ea: `0x180005568`
- end: `0x1800055d3`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c38`
- `0x18001fb10`
- `0x180033a1c`
- `0x180034c5c`
- `0x180035afc`
- `0x180035f4c`
- `0x180053cb8`
- `0x180054518`
- `0x1800589e0`

## callees

- `0x180005568`

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
0x180005568  xor     r10d, r10d
0x18000556b  mov     r9, rcx
0x18000556e  test    rdx, rdx
0x180005571  jz      short loc_1800055C4
0x180005573  cmp     rdx, 7FFFFFFFh
0x18000557a  jbe     short loc_180005583
0x18000557c  mov     eax, 80070057h
0x180005581  jmp     short loc_1800055CE
0x180005583  mov     eax, 7FFFFFFEh
0x180005588  test    rax, rax
0x18000558b  jz      short loc_1800055AB
0x18000558d  movzx   ecx, word ptr [r8]
0x180005591  test    cx, cx
0x180005594  jz      short loc_1800055AB
0x180005596  mov     [r9], cx
0x18000559a  add     r8, 2
0x18000559e  add     r9, 2
0x1800055a2  dec     rax
0x1800055a5  sub     rdx, 1
0x1800055a9  jnz     short loc_180005588
0x1800055ab  test    rdx, rdx
0x1800055ae  lea     rcx, [r9-2]
0x1800055b2  cmovnz  rcx, r9
0x1800055b6  neg     rdx
0x1800055b9  sbb     eax, eax
0x1800055bb  not     eax
0x1800055bd  and     eax, 8007007Ah
0x1800055c2  jmp     short loc_1800055CE
0x1800055c4  mov     eax, 80070057h
0x1800055c9  test    rdx, rdx
0x1800055cc  jz      short locret_1800055D2
0x1800055ce  mov     [rcx], r10w
0x1800055d2  retn
```
