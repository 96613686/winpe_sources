# StringCopyWorkerW

- ea: `0x140005ca0`
- end: `0x140005cf1`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003fc0`
- `0x140005bc0`
- `0x140005e34`

## callees

- `0x140005ca0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v5; // r8
  __int64 i; // rax
  STRSAFE_LPWSTR v7; // rdx
  HRESULT result; // eax

  v5 = cchDest;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v7 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x140005ca0  xor     r10d, r10d
0x140005ca3  mov     r8, rdx
0x140005ca6  mov     eax, 7FFFFFFEh
0x140005cab  test    rdx, rdx
0x140005cae  jz      short loc_140005CD2
0x140005cb0  test    rax, rax
0x140005cb3  jz      short loc_140005CD2
0x140005cb5  movzx   edx, word ptr [r9]
0x140005cb9  test    dx, dx
0x140005cbc  jz      short loc_140005CD2
0x140005cbe  mov     [rcx], dx
0x140005cc1  add     r9, 2
0x140005cc5  add     rcx, 2
0x140005cc9  dec     rax
0x140005ccc  sub     r8, 1
0x140005cd0  jnz     short loc_140005CB0
0x140005cd2  mov     rax, r8
0x140005cd5  lea     rdx, [rcx-2]
0x140005cd9  neg     rax
0x140005cdc  sbb     eax, eax
0x140005cde  not     eax
0x140005ce0  and     eax, 8007007Ah
0x140005ce5  test    r8, r8
0x140005ce8  cmovnz  rdx, rcx
0x140005cec  mov     [rdx], r10w
0x140005cf0  retn
```
