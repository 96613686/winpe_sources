# StringCopyWorkerW

- ea: `0x140006650`
- end: `0x1400066a1`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000190c`
- `0x140004214`
- `0x140006970`

## callees

- `0x140006650`

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
0x140006650  xor     r10d, r10d
0x140006653  mov     r8, rdx
0x140006656  mov     eax, 7FFFFFFEh
0x14000665b  test    rdx, rdx
0x14000665e  jz      short loc_140006682
0x140006660  test    rax, rax
0x140006663  jz      short loc_140006682
0x140006665  movzx   edx, word ptr [r9]
0x140006669  test    dx, dx
0x14000666c  jz      short loc_140006682
0x14000666e  mov     [rcx], dx
0x140006671  add     r9, 2
0x140006675  add     rcx, 2
0x140006679  dec     rax
0x14000667c  sub     r8, 1
0x140006680  jnz     short loc_140006660
0x140006682  mov     rax, r8
0x140006685  lea     rdx, [rcx-2]
0x140006689  neg     rax
0x14000668c  sbb     eax, eax
0x14000668e  not     eax
0x140006690  and     eax, 8007007Ah
0x140006695  test    r8, r8
0x140006698  cmovnz  rdx, rcx
0x14000669c  mov     [rdx], r10w
0x1400066a0  retn
```
