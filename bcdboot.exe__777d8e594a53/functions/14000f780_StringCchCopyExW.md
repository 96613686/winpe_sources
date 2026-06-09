# StringCchCopyExW

- ea: `0x14000f780`
- end: `0x14000f82f`
- name: `StringCchCopyExW`
- size: `175`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f50c`

## callees

- `0x14000f780`

## pseudocode

```c
HRESULT __stdcall StringCchCopyExW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        STRSAFE_LPCWSTR pszSrc,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  HRESULT result; // eax
  __int64 v11; // rcx
  size_t v12; // r8
  STRSAFE_LPWSTR v13; // rax
  __int64 v14; // r9
  STRSAFE_LPWSTR v15; // rcx
  __int64 v16; // rdx
  size_t v17; // r10

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v11 = 2147483646;
    v12 = cchDest;
    v13 = pszDest;
    v14 = 0;
    do
    {
      if ( !v11 )
        break;
      if ( !*pszSrc )
        break;
      *v13++ = *pszSrc++;
      --v11;
      ++v14;
      --v12;
    }
    while ( v12 );
    v15 = v13 - 1;
    v16 = v14 - 1;
    if ( v12 )
    {
      v15 = v13;
      v16 = v14;
    }
    v17 = cchDest - v16;
    *v15 = 0;
    result = v12 == 0 ? 0x8007007A : 0;
    if ( ppszDestEnd )
      *ppszDestEnd = &pszDest[v16];
    if ( pcchRemaining )
      *pcchRemaining = v17;
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
0x14000f780  push    rbx
0x14000f782  push    rsi
0x14000f783  push    rdi
0x14000f784  xor     esi, esi
0x14000f786  mov     rdi, r9
0x14000f789  mov     r11, r8
0x14000f78c  mov     r10, rdx
0x14000f78f  mov     rbx, rcx
0x14000f792  test    rdx, rdx
0x14000f795  jz      loc_14000F81E
0x14000f79b  cmp     rdx, 7FFFFFFFh
0x14000f7a2  jbe     short loc_14000F7AB
0x14000f7a4  mov     eax, 80070057h
0x14000f7a9  jmp     short loc_14000F828
0x14000f7ab  mov     ecx, 7FFFFFFEh
0x14000f7b0  mov     r8, r10
0x14000f7b3  mov     rax, rbx
0x14000f7b6  mov     r9, rsi
0x14000f7b9  test    rcx, rcx
0x14000f7bc  jz      short loc_14000F7DE
0x14000f7be  movzx   edx, word ptr [r11]
0x14000f7c2  test    dx, dx
0x14000f7c5  jz      short loc_14000F7DE
0x14000f7c7  mov     [rax], dx
0x14000f7ca  add     r11, 2
0x14000f7ce  add     rax, 2
0x14000f7d2  dec     rcx
0x14000f7d5  inc     r9
0x14000f7d8  sub     r8, 1
0x14000f7dc  jnz     short loc_14000F7B9
0x14000f7de  test    r8, r8
0x14000f7e1  lea     rcx, [rax-2]
0x14000f7e5  lea     rdx, [r9-1]
0x14000f7e9  cmovnz  rcx, rax
0x14000f7ed  cmovnz  rdx, r9
0x14000f7f1  neg     r8
0x14000f7f4  sbb     eax, eax
0x14000f7f6  sub     r10, rdx
0x14000f7f9  not     eax
0x14000f7fb  mov     [rcx], si
0x14000f7fe  and     eax, 8007007Ah
0x14000f803  lea     rcx, [rbx+rdx*2]
0x14000f807  test    rdi, rdi
0x14000f80a  jz      short loc_14000F80F
0x14000f80c  mov     [rdi], rcx
0x14000f80f  mov     rcx, [rsp+18h+pcchRemaining]
0x14000f814  test    rcx, rcx
0x14000f817  jz      short loc_14000F82B
0x14000f819  mov     [rcx], r10
0x14000f81c  jmp     short loc_14000F82B
0x14000f81e  mov     eax, 80070057h
0x14000f823  test    r10, r10
0x14000f826  jz      short loc_14000F82B
0x14000f828  mov     [rcx], si
0x14000f82b  pop     rdi
0x14000f82c  pop     rsi
0x14000f82d  pop     rbx
0x14000f82e  retn
```
