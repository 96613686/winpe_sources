# StringCopyWorkerW

- ea: `0x18000c0a8`
- end: `0x18000c0f9`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ef8`
- `0x18000bf80`
- `0x18000c49c`

## callees

- `0x18000c0a8`

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
0x18000c0a8  xor     r10d, r10d
0x18000c0ab  mov     r8, rdx
0x18000c0ae  mov     eax, 7FFFFFFEh
0x18000c0b3  test    rdx, rdx
0x18000c0b6  jz      short loc_18000C0DA
0x18000c0b8  test    rax, rax
0x18000c0bb  jz      short loc_18000C0DA
0x18000c0bd  movzx   edx, word ptr [r9]
0x18000c0c1  test    dx, dx
0x18000c0c4  jz      short loc_18000C0DA
0x18000c0c6  mov     [rcx], dx
0x18000c0c9  add     r9, 2
0x18000c0cd  add     rcx, 2
0x18000c0d1  dec     rax
0x18000c0d4  sub     r8, 1
0x18000c0d8  jnz     short loc_18000C0B8
0x18000c0da  mov     rax, r8
0x18000c0dd  lea     rdx, [rcx-2]
0x18000c0e1  neg     rax
0x18000c0e4  sbb     eax, eax
0x18000c0e6  not     eax
0x18000c0e8  and     eax, 8007007Ah
0x18000c0ed  test    r8, r8
0x18000c0f0  cmovnz  rdx, rcx
0x18000c0f4  mov     [rdx], r10w
0x18000c0f8  retn
```
