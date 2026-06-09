# StringCopyWorkerW

- ea: `0x18000978c`
- end: `0x1800097dd`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007940`
- `0x1800096ac`
- `0x18000989c`

## callees

- `0x18000978c`

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
0x18000978c  xor     r10d, r10d
0x18000978f  mov     r8, rdx
0x180009792  mov     eax, 7FFFFFFEh
0x180009797  test    rdx, rdx
0x18000979a  jz      short loc_1800097BE
0x18000979c  test    rax, rax
0x18000979f  jz      short loc_1800097BE
0x1800097a1  movzx   edx, word ptr [r9]
0x1800097a5  test    dx, dx
0x1800097a8  jz      short loc_1800097BE
0x1800097aa  mov     [rcx], dx
0x1800097ad  add     r9, 2
0x1800097b1  add     rcx, 2
0x1800097b5  dec     rax
0x1800097b8  sub     r8, 1
0x1800097bc  jnz     short loc_18000979C
0x1800097be  mov     rax, r8
0x1800097c1  lea     rdx, [rcx-2]
0x1800097c5  neg     rax
0x1800097c8  sbb     eax, eax
0x1800097ca  not     eax
0x1800097cc  and     eax, 8007007Ah
0x1800097d1  test    r8, r8
0x1800097d4  cmovnz  rdx, rcx
0x1800097d8  mov     [rdx], r10w
0x1800097dc  retn
```
