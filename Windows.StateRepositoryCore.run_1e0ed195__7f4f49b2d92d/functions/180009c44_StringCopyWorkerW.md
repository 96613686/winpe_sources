# StringCopyWorkerW

- ea: `0x180009c44`
- end: `0x180009c95`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009ad8`
- `0x180009b54`

## callees

- `0x180009c44`

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
0x180009c44  xor     r10d, r10d
0x180009c47  mov     r8, rdx
0x180009c4a  mov     eax, 7FFFFFFEh
0x180009c4f  test    rdx, rdx
0x180009c52  jz      short loc_180009C76
0x180009c54  test    rax, rax
0x180009c57  jz      short loc_180009C76
0x180009c59  movzx   edx, word ptr [r9]
0x180009c5d  test    dx, dx
0x180009c60  jz      short loc_180009C76
0x180009c62  mov     [rcx], dx
0x180009c65  add     r9, 2
0x180009c69  add     rcx, 2
0x180009c6d  dec     rax
0x180009c70  sub     r8, 1
0x180009c74  jnz     short loc_180009C54
0x180009c76  mov     rax, r8
0x180009c79  lea     rdx, [rcx-2]
0x180009c7d  neg     rax
0x180009c80  sbb     eax, eax
0x180009c82  not     eax
0x180009c84  and     eax, 8007007Ah
0x180009c89  test    r8, r8
0x180009c8c  cmovnz  rdx, rcx
0x180009c90  mov     [rdx], r10w
0x180009c94  retn
```
