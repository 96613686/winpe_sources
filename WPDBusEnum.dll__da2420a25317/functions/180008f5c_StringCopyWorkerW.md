# StringCopyWorkerW

- ea: `0x180008f5c`
- end: `0x180008fad`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d32c`

## callees

- `0x180008f5c`

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
0x180008f5c  xor     r10d, r10d
0x180008f5f  mov     r8, rdx
0x180008f62  mov     eax, 7FFFFFFEh
0x180008f67  test    rdx, rdx
0x180008f6a  jz      short loc_180008F8E
0x180008f6c  test    rax, rax
0x180008f6f  jz      short loc_180008F8E
0x180008f71  movzx   edx, word ptr [r9]
0x180008f75  test    dx, dx
0x180008f78  jz      short loc_180008F8E
0x180008f7a  mov     [rcx], dx
0x180008f7d  add     r9, 2
0x180008f81  add     rcx, 2
0x180008f85  dec     rax
0x180008f88  sub     r8, 1
0x180008f8c  jnz     short loc_180008F6C
0x180008f8e  mov     rax, r8
0x180008f91  lea     rdx, [rcx-2]
0x180008f95  neg     rax
0x180008f98  sbb     eax, eax
0x180008f9a  not     eax
0x180008f9c  and     eax, 8007007Ah
0x180008fa1  test    r8, r8
0x180008fa4  cmovnz  rdx, rcx
0x180008fa8  mov     [rdx], r10w
0x180008fac  retn
```
