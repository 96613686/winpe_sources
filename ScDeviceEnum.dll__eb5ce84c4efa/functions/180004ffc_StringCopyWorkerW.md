# StringCopyWorkerW

- ea: `0x180004ffc`
- end: `0x18000504d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003328`
- `0x180004f1c`
- `0x180005110`

## callees

- `0x180004ffc`

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
0x180004ffc  xor     r10d, r10d
0x180004fff  mov     r8, rdx
0x180005002  mov     eax, 7FFFFFFEh
0x180005007  test    rdx, rdx
0x18000500a  jz      short loc_18000502E
0x18000500c  test    rax, rax
0x18000500f  jz      short loc_18000502E
0x180005011  movzx   edx, word ptr [r9]
0x180005015  test    dx, dx
0x180005018  jz      short loc_18000502E
0x18000501a  mov     [rcx], dx
0x18000501d  add     r9, 2
0x180005021  add     rcx, 2
0x180005025  dec     rax
0x180005028  sub     r8, 1
0x18000502c  jnz     short loc_18000500C
0x18000502e  mov     rax, r8
0x180005031  lea     rdx, [rcx-2]
0x180005035  neg     rax
0x180005038  sbb     eax, eax
0x18000503a  not     eax
0x18000503c  and     eax, 8007007Ah
0x180005041  test    r8, r8
0x180005044  cmovnz  rdx, rcx
0x180005048  mov     [rdx], r10w
0x18000504c  retn
```
