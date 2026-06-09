# StringCopyWorkerW

- ea: `0x180005218`
- end: `0x180005269`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800050ac`
- `0x180005128`

## callees

- `0x180005218`

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
0x180005218  xor     r10d, r10d
0x18000521b  mov     r8, rdx
0x18000521e  mov     eax, 7FFFFFFEh
0x180005223  test    rdx, rdx
0x180005226  jz      short loc_18000524A
0x180005228  test    rax, rax
0x18000522b  jz      short loc_18000524A
0x18000522d  movzx   edx, word ptr [r9]
0x180005231  test    dx, dx
0x180005234  jz      short loc_18000524A
0x180005236  mov     [rcx], dx
0x180005239  add     r9, 2
0x18000523d  add     rcx, 2
0x180005241  dec     rax
0x180005244  sub     r8, 1
0x180005248  jnz     short loc_180005228
0x18000524a  mov     rax, r8
0x18000524d  lea     rdx, [rcx-2]
0x180005251  neg     rax
0x180005254  sbb     eax, eax
0x180005256  not     eax
0x180005258  and     eax, 8007007Ah
0x18000525d  test    r8, r8
0x180005260  cmovnz  rdx, rcx
0x180005264  mov     [rdx], r10w
0x180005268  retn
```
