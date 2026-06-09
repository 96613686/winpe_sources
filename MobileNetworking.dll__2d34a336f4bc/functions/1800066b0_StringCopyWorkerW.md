# StringCopyWorkerW

- ea: `0x1800066b0`
- end: `0x1800066fa`
- name: `StringCopyWorkerW`
- size: `74`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800065f0`
- `0x180006630`
- `0x180006bf0`

## callees

- `0x1800066b0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // rax
  STRSAFE_LPWSTR v7; // r8
  HRESULT result; // eax

  for ( i = 2147483646; cchDest; --cchDest )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v7 = pszDest - 1;
  result = -2147024774;
  if ( cchDest )
  {
    v7 = pszDest;
    result = 0;
  }
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x1800066b0  mov     r10, rcx
0x1800066b3  mov     eax, 7FFFFFFEh
0x1800066b8  test    rdx, rdx
0x1800066bb  jz      short loc_1800066E0
0x1800066bd  test    rax, rax
0x1800066c0  jz      short loc_1800066E0
0x1800066c2  movzx   ecx, word ptr [r9]
0x1800066c6  test    cx, cx
0x1800066c9  jz      short loc_1800066E0
0x1800066cb  mov     [r10], cx
0x1800066cf  add     r9, 2
0x1800066d3  add     r10, 2
0x1800066d7  dec     rax
0x1800066da  sub     rdx, 1
0x1800066de  jnz     short loc_1800066BD
0x1800066e0  xor     ecx, ecx
0x1800066e2  lea     r8, [r10-2]
0x1800066e6  test    rdx, rdx
0x1800066e9  mov     eax, 8007007Ah
0x1800066ee  cmovnz  r8, r10
0x1800066f2  cmovnz  eax, ecx
0x1800066f5  mov     [r8], cx
0x1800066f9  retn
```
