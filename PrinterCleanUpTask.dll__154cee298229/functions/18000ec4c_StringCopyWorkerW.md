# StringCopyWorkerW

- ea: `0x18000ec4c`
- end: `0x18000ec9d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bb7c`
- `0x18000ebd0`
- `0x18000ed40`

## callees

- `0x18000ec4c`

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
0x18000ec4c  xor     r10d, r10d
0x18000ec4f  mov     r8, rdx
0x18000ec52  mov     eax, 7FFFFFFEh
0x18000ec57  test    rdx, rdx
0x18000ec5a  jz      short loc_18000EC7E
0x18000ec5c  test    rax, rax
0x18000ec5f  jz      short loc_18000EC7E
0x18000ec61  movzx   edx, word ptr [r9]
0x18000ec65  test    dx, dx
0x18000ec68  jz      short loc_18000EC7E
0x18000ec6a  mov     [rcx], dx
0x18000ec6d  add     r9, 2
0x18000ec71  add     rcx, 2
0x18000ec75  dec     rax
0x18000ec78  sub     r8, 1
0x18000ec7c  jnz     short loc_18000EC5C
0x18000ec7e  mov     rax, r8
0x18000ec81  lea     rdx, [rcx-2]
0x18000ec85  neg     rax
0x18000ec88  sbb     eax, eax
0x18000ec8a  not     eax
0x18000ec8c  and     eax, 8007007Ah
0x18000ec91  test    r8, r8
0x18000ec94  cmovnz  rdx, rcx
0x18000ec98  mov     [rdx], r10w
0x18000ec9c  retn
```
