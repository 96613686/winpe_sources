# StringCopyWorkerW

- ea: `0x140007224`
- end: `0x140007275`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400056e8`
- `0x1400070fc`
- `0x140007338`

## callees

- `0x140007224`

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
0x140007224  xor     r10d, r10d
0x140007227  mov     r8, rdx
0x14000722a  mov     eax, 7FFFFFFEh
0x14000722f  test    rdx, rdx
0x140007232  jz      short loc_140007256
0x140007234  test    rax, rax
0x140007237  jz      short loc_140007256
0x140007239  movzx   edx, word ptr [r9]
0x14000723d  test    dx, dx
0x140007240  jz      short loc_140007256
0x140007242  mov     [rcx], dx
0x140007245  add     r9, 2
0x140007249  add     rcx, 2
0x14000724d  dec     rax
0x140007250  sub     r8, 1
0x140007254  jnz     short loc_140007234
0x140007256  mov     rax, r8
0x140007259  lea     rdx, [rcx-2]
0x14000725d  neg     rax
0x140007260  sbb     eax, eax
0x140007262  not     eax
0x140007264  and     eax, 8007007Ah
0x140007269  test    r8, r8
0x14000726c  cmovnz  rdx, rcx
0x140007270  mov     [rdx], r10w
0x140007274  retn
```
