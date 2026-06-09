# StringCopyWorkerW

- ea: `0x180006bc4`
- end: `0x180006c15`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a9c`
- `0x180006af0`

## callees

- `0x180006bc4`

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
0x180006bc4  xor     r10d, r10d
0x180006bc7  mov     r8, rdx
0x180006bca  mov     eax, 7FFFFFFEh
0x180006bcf  test    rdx, rdx
0x180006bd2  jz      short loc_180006BF6
0x180006bd4  test    rax, rax
0x180006bd7  jz      short loc_180006BF6
0x180006bd9  movzx   edx, word ptr [r9]
0x180006bdd  test    dx, dx
0x180006be0  jz      short loc_180006BF6
0x180006be2  mov     [rcx], dx
0x180006be5  add     r9, 2
0x180006be9  add     rcx, 2
0x180006bed  dec     rax
0x180006bf0  sub     r8, 1
0x180006bf4  jnz     short loc_180006BD4
0x180006bf6  mov     rax, r8
0x180006bf9  lea     rdx, [rcx-2]
0x180006bfd  neg     rax
0x180006c00  sbb     eax, eax
0x180006c02  not     eax
0x180006c04  and     eax, 8007007Ah
0x180006c09  test    r8, r8
0x180006c0c  cmovnz  rdx, rcx
0x180006c10  mov     [rdx], r10w
0x180006c14  retn
```
