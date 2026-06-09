# StringCopyWorkerW

- ea: `0x140005d70`
- end: `0x140005dc1`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005bf0`
- `0x140005c44`

## callees

- `0x140005d70`

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
0x140005d70  xor     r10d, r10d
0x140005d73  mov     r8, rdx
0x140005d76  mov     eax, 7FFFFFFEh
0x140005d7b  test    rdx, rdx
0x140005d7e  jz      short loc_140005DA2
0x140005d80  test    rax, rax
0x140005d83  jz      short loc_140005DA2
0x140005d85  movzx   edx, word ptr [r9]
0x140005d89  test    dx, dx
0x140005d8c  jz      short loc_140005DA2
0x140005d8e  mov     [rcx], dx
0x140005d91  add     r9, 2
0x140005d95  add     rcx, 2
0x140005d99  dec     rax
0x140005d9c  sub     r8, 1
0x140005da0  jnz     short loc_140005D80
0x140005da2  mov     rax, r8
0x140005da5  lea     rdx, [rcx-2]
0x140005da9  neg     rax
0x140005dac  sbb     eax, eax
0x140005dae  not     eax
0x140005db0  and     eax, 8007007Ah
0x140005db5  test    r8, r8
0x140005db8  cmovnz  rdx, rcx
0x140005dbc  mov     [rdx], r10w
0x140005dc0  retn
```
