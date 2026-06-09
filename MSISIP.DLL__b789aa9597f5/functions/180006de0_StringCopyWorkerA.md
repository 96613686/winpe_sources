# StringCopyWorkerA

- ea: `0x180006de0`
- end: `0x180006e29`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ca4`
- `0x18000b3e8`

## callees

- `0x180006de0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // rax
  STRSAFE_LPSTR v7; // rcx
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
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180006de0  mov     r8, rcx
0x180006de3  mov     eax, 7FFFFFFEh
0x180006de8  test    rdx, rdx
0x180006deb  jz      short loc_180006E0B
0x180006ded  test    rax, rax
0x180006df0  jz      short loc_180006E0B
0x180006df2  mov     cl, [r9]
0x180006df5  test    cl, cl
0x180006df7  jz      short loc_180006E0B
0x180006df9  mov     [r8], cl
0x180006dfc  inc     r9
0x180006dff  inc     r8
0x180006e02  dec     rax
0x180006e05  sub     rdx, 1
0x180006e09  jnz     short loc_180006DED
0x180006e0b  mov     rax, rdx
0x180006e0e  lea     rcx, [r8-1]
0x180006e12  neg     rax
0x180006e15  sbb     eax, eax
0x180006e17  not     eax
0x180006e19  and     eax, 8007007Ah
0x180006e1e  test    rdx, rdx
0x180006e21  cmovnz  rcx, r8
0x180006e25  mov     byte ptr [rcx], 0
0x180006e28  retn
```
