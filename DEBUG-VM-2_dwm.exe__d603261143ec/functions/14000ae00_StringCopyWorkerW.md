# StringCopyWorkerW

- ea: `0x14000ae00`
- end: `0x14000ae51`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140007e14`
- `0x14000ad20`
- `0x14000b060`

## callees

- `0x14000ae00`

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
0x14000ae00  xor     r10d, r10d
0x14000ae03  mov     r8, rdx
0x14000ae06  mov     eax, 7FFFFFFEh
0x14000ae0b  test    rdx, rdx
0x14000ae0e  jz      short loc_14000AE32
0x14000ae10  test    rax, rax
0x14000ae13  jz      short loc_14000AE32
0x14000ae15  movzx   edx, word ptr [r9]
0x14000ae19  test    dx, dx
0x14000ae1c  jz      short loc_14000AE32
0x14000ae1e  mov     [rcx], dx
0x14000ae21  add     r9, 2
0x14000ae25  add     rcx, 2
0x14000ae29  dec     rax
0x14000ae2c  sub     r8, 1
0x14000ae30  jnz     short loc_14000AE10
0x14000ae32  mov     rax, r8
0x14000ae35  lea     rdx, [rcx-2]
0x14000ae39  neg     rax
0x14000ae3c  sbb     eax, eax
0x14000ae3e  not     eax
0x14000ae40  and     eax, 8007007Ah
0x14000ae45  test    r8, r8
0x14000ae48  cmovnz  rdx, rcx
0x14000ae4c  mov     [rdx], r10w
0x14000ae50  retn
```
