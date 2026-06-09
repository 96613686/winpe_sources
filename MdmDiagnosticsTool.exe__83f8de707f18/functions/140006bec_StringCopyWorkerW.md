# StringCopyWorkerW

- ea: `0x140006bec`
- end: `0x140006c3d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003b00`
- `0x140006b08`
- `0x140006e34`

## callees

- `0x140006bec`

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
0x140006bec  xor     r10d, r10d
0x140006bef  mov     r8, rdx
0x140006bf2  mov     eax, 7FFFFFFEh
0x140006bf7  test    rdx, rdx
0x140006bfa  jz      short loc_140006C1E
0x140006bfc  test    rax, rax
0x140006bff  jz      short loc_140006C1E
0x140006c01  movzx   edx, word ptr [r9]
0x140006c05  test    dx, dx
0x140006c08  jz      short loc_140006C1E
0x140006c0a  mov     [rcx], dx
0x140006c0d  add     r9, 2
0x140006c11  add     rcx, 2
0x140006c15  dec     rax
0x140006c18  sub     r8, 1
0x140006c1c  jnz     short loc_140006BFC
0x140006c1e  mov     rax, r8
0x140006c21  lea     rdx, [rcx-2]
0x140006c25  neg     rax
0x140006c28  sbb     eax, eax
0x140006c2a  not     eax
0x140006c2c  and     eax, 8007007Ah
0x140006c31  test    r8, r8
0x140006c34  cmovnz  rdx, rcx
0x140006c38  mov     [rdx], r10w
0x140006c3c  retn
```
