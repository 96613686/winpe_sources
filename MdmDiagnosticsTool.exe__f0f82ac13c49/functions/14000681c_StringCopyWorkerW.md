# StringCopyWorkerW

- ea: `0x14000681c`
- end: `0x14000686d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039ac`
- `0x14000673c`
- `0x140006a1c`

## callees

- `0x14000681c`

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
0x14000681c  xor     r10d, r10d
0x14000681f  mov     r8, rdx
0x140006822  mov     eax, 7FFFFFFEh
0x140006827  test    rdx, rdx
0x14000682a  jz      short loc_14000684E
0x14000682c  test    rax, rax
0x14000682f  jz      short loc_14000684E
0x140006831  movzx   edx, word ptr [r9]
0x140006835  test    dx, dx
0x140006838  jz      short loc_14000684E
0x14000683a  mov     [rcx], dx
0x14000683d  add     r9, 2
0x140006841  add     rcx, 2
0x140006845  dec     rax
0x140006848  sub     r8, 1
0x14000684c  jnz     short loc_14000682C
0x14000684e  mov     rax, r8
0x140006851  lea     rdx, [rcx-2]
0x140006855  neg     rax
0x140006858  sbb     eax, eax
0x14000685a  not     eax
0x14000685c  and     eax, 8007007Ah
0x140006861  test    r8, r8
0x140006864  cmovnz  rdx, rcx
0x140006868  mov     [rdx], r10w
0x14000686c  retn
```
