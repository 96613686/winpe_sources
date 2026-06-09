# StringCopyWorkerW

- ea: `0x180005a50`
- end: `0x180005aa1`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005928`
- `0x1800059a8`

## callees

- `0x180005a50`

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
0x180005a50  xor     r10d, r10d
0x180005a53  mov     r8, rdx
0x180005a56  mov     eax, 7FFFFFFEh
0x180005a5b  test    rdx, rdx
0x180005a5e  jz      short loc_180005A82
0x180005a60  test    rax, rax
0x180005a63  jz      short loc_180005A82
0x180005a65  movzx   edx, word ptr [r9]
0x180005a69  test    dx, dx
0x180005a6c  jz      short loc_180005A82
0x180005a6e  mov     [rcx], dx
0x180005a71  add     r9, 2
0x180005a75  add     rcx, 2
0x180005a79  dec     rax
0x180005a7c  sub     r8, 1
0x180005a80  jnz     short loc_180005A60
0x180005a82  mov     rax, r8
0x180005a85  lea     rdx, [rcx-2]
0x180005a89  neg     rax
0x180005a8c  sbb     eax, eax
0x180005a8e  not     eax
0x180005a90  and     eax, 8007007Ah
0x180005a95  test    r8, r8
0x180005a98  cmovnz  rdx, rcx
0x180005a9c  mov     [rdx], r10w
0x180005aa0  retn
```
