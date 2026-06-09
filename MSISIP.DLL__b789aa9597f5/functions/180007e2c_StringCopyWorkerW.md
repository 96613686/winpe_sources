# StringCopyWorkerW

- ea: `0x180007e2c`
- end: `0x180007e7d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007254`
- `0x180007910`
- `0x180007b28`

## callees

- `0x180007e2c`

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
0x180007e2c  xor     r10d, r10d
0x180007e2f  mov     r8, rdx
0x180007e32  mov     eax, 7FFFFFFEh
0x180007e37  test    rdx, rdx
0x180007e3a  jz      short loc_180007E5E
0x180007e3c  test    rax, rax
0x180007e3f  jz      short loc_180007E5E
0x180007e41  movzx   edx, word ptr [r9]
0x180007e45  test    dx, dx
0x180007e48  jz      short loc_180007E5E
0x180007e4a  mov     [rcx], dx
0x180007e4d  add     r9, 2
0x180007e51  add     rcx, 2
0x180007e55  dec     rax
0x180007e58  sub     r8, 1
0x180007e5c  jnz     short loc_180007E3C
0x180007e5e  mov     rax, r8
0x180007e61  lea     rdx, [rcx-2]
0x180007e65  neg     rax
0x180007e68  sbb     eax, eax
0x180007e6a  not     eax
0x180007e6c  and     eax, 8007007Ah
0x180007e71  test    r8, r8
0x180007e74  cmovnz  rdx, rcx
0x180007e78  mov     [rdx], r10w
0x180007e7c  retn
```
