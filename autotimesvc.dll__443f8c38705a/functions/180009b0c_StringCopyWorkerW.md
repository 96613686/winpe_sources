# StringCopyWorkerW

- ea: `0x180009b0c`
- end: `0x180009b5d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000603c`
- `0x1800099e4`
- `0x180009f48`

## callees

- `0x180009b0c`

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
0x180009b0c  xor     r10d, r10d
0x180009b0f  mov     r8, rdx
0x180009b12  mov     eax, 7FFFFFFEh
0x180009b17  test    rdx, rdx
0x180009b1a  jz      short loc_180009B3E
0x180009b1c  test    rax, rax
0x180009b1f  jz      short loc_180009B3E
0x180009b21  movzx   edx, word ptr [r9]
0x180009b25  test    dx, dx
0x180009b28  jz      short loc_180009B3E
0x180009b2a  mov     [rcx], dx
0x180009b2d  add     r9, 2
0x180009b31  add     rcx, 2
0x180009b35  dec     rax
0x180009b38  sub     r8, 1
0x180009b3c  jnz     short loc_180009B1C
0x180009b3e  mov     rax, r8
0x180009b41  lea     rdx, [rcx-2]
0x180009b45  neg     rax
0x180009b48  sbb     eax, eax
0x180009b4a  not     eax
0x180009b4c  and     eax, 8007007Ah
0x180009b51  test    r8, r8
0x180009b54  cmovnz  rdx, rcx
0x180009b58  mov     [rdx], r10w
0x180009b5c  retn
```
