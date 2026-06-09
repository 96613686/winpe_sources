# StringCopyWorkerW

- ea: `0x1400045e8`
- end: `0x140004639`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002bc0`
- `0x140004508`
- `0x140004694`

## callees

- `0x1400045e8`

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
0x1400045e8  xor     r10d, r10d
0x1400045eb  mov     r8, rdx
0x1400045ee  mov     eax, 7FFFFFFEh
0x1400045f3  test    rdx, rdx
0x1400045f6  jz      short loc_14000461A
0x1400045f8  test    rax, rax
0x1400045fb  jz      short loc_14000461A
0x1400045fd  movzx   edx, word ptr [r9]
0x140004601  test    dx, dx
0x140004604  jz      short loc_14000461A
0x140004606  mov     [rcx], dx
0x140004609  add     r9, 2
0x14000460d  add     rcx, 2
0x140004611  dec     rax
0x140004614  sub     r8, 1
0x140004618  jnz     short loc_1400045F8
0x14000461a  mov     rax, r8
0x14000461d  lea     rdx, [rcx-2]
0x140004621  neg     rax
0x140004624  sbb     eax, eax
0x140004626  not     eax
0x140004628  and     eax, 8007007Ah
0x14000462d  test    r8, r8
0x140004630  cmovnz  rdx, rcx
0x140004634  mov     [rdx], r10w
0x140004638  retn
```
