# StringCopyWorkerA

- ea: `0x180006b74`
- end: `0x180006bbd`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800057a8`

## callees

- `0x180006b74`

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
0x180006b74  mov     r8, rcx
0x180006b77  mov     eax, 7FFFFFFEh
0x180006b7c  test    rdx, rdx
0x180006b7f  jz      short loc_180006B9F
0x180006b81  test    rax, rax
0x180006b84  jz      short loc_180006B9F
0x180006b86  mov     cl, [r9]
0x180006b89  test    cl, cl
0x180006b8b  jz      short loc_180006B9F
0x180006b8d  mov     [r8], cl
0x180006b90  inc     r9
0x180006b93  inc     r8
0x180006b96  dec     rax
0x180006b99  sub     rdx, 1
0x180006b9d  jnz     short loc_180006B81
0x180006b9f  mov     rax, rdx
0x180006ba2  lea     rcx, [r8-1]
0x180006ba6  neg     rax
0x180006ba9  sbb     eax, eax
0x180006bab  not     eax
0x180006bad  and     eax, 8007007Ah
0x180006bb2  test    rdx, rdx
0x180006bb5  cmovnz  rcx, r8
0x180006bb9  mov     byte ptr [rcx], 0
0x180006bbc  retn
```
