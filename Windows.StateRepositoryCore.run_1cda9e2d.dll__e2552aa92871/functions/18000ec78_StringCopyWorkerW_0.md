# StringCopyWorkerW_0

- ea: `0x18000ec78`
- end: `0x18000ecc9`
- name: `StringCopyWorkerW_0`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e78c`
- `0x18000ebec`

## callees

- `0x18000ec78`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r8
  STRSAFE_LPWSTR v7; // rdx
  HRESULT result; // eax

  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v7 = pszDest - 1;
  result = i == 0 ? 0x8007007A : 0;
  if ( i )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x18000ec78  xor     r10d, r10d
0x18000ec7b  mov     r8, rdx
0x18000ec7e  test    rdx, rdx
0x18000ec81  jz      short loc_18000ECAA
0x18000ec83  mov     rax, [rsp+cchToCopy]
0x18000ec88  test    rax, rax
0x18000ec8b  jz      short loc_18000ECAA
0x18000ec8d  movzx   edx, word ptr [r9]
0x18000ec91  test    dx, dx
0x18000ec94  jz      short loc_18000ECAA
0x18000ec96  mov     [rcx], dx
0x18000ec99  add     r9, 2
0x18000ec9d  add     rcx, 2
0x18000eca1  dec     rax
0x18000eca4  sub     r8, 1
0x18000eca8  jnz     short loc_18000EC88
0x18000ecaa  mov     rax, r8
0x18000ecad  lea     rdx, [rcx-2]
0x18000ecb1  neg     rax
0x18000ecb4  sbb     eax, eax
0x18000ecb6  not     eax
0x18000ecb8  and     eax, 8007007Ah
0x18000ecbd  test    r8, r8
0x18000ecc0  cmovnz  rdx, rcx
0x18000ecc4  mov     [rdx], r10w
0x18000ecc8  retn
```
