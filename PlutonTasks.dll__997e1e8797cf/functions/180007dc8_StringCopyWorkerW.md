# StringCopyWorkerW

- ea: `0x180007dc8`
- end: `0x180007e19`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004084`
- `0x180007ca0`
- `0x180008284`

## callees

- `0x180007dc8`

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
0x180007dc8  xor     r10d, r10d
0x180007dcb  mov     r8, rdx
0x180007dce  mov     eax, 7FFFFFFEh
0x180007dd3  test    rdx, rdx
0x180007dd6  jz      short loc_180007DFA
0x180007dd8  test    rax, rax
0x180007ddb  jz      short loc_180007DFA
0x180007ddd  movzx   edx, word ptr [r9]
0x180007de1  test    dx, dx
0x180007de4  jz      short loc_180007DFA
0x180007de6  mov     [rcx], dx
0x180007de9  add     r9, 2
0x180007ded  add     rcx, 2
0x180007df1  dec     rax
0x180007df4  sub     r8, 1
0x180007df8  jnz     short loc_180007DD8
0x180007dfa  mov     rax, r8
0x180007dfd  lea     rdx, [rcx-2]
0x180007e01  neg     rax
0x180007e04  sbb     eax, eax
0x180007e06  not     eax
0x180007e08  and     eax, 8007007Ah
0x180007e0d  test    r8, r8
0x180007e10  cmovnz  rdx, rcx
0x180007e14  mov     [rdx], r10w
0x180007e18  retn
```
