# StringCopyWorkerW

- ea: `0x180013670`
- end: `0x1800136c1`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800135a0`
- `0x1800135ec`

## callees

- `0x180013670`

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
0x180013670  xor     r10d, r10d
0x180013673  mov     r8, rdx
0x180013676  mov     eax, 7FFFFFFEh
0x18001367b  test    rdx, rdx
0x18001367e  jz      short loc_1800136A2
0x180013680  test    rax, rax
0x180013683  jz      short loc_1800136A2
0x180013685  movzx   edx, word ptr [r9]
0x180013689  test    dx, dx
0x18001368c  jz      short loc_1800136A2
0x18001368e  mov     [rcx], dx
0x180013691  add     r9, 2
0x180013695  add     rcx, 2
0x180013699  dec     rax
0x18001369c  sub     r8, 1
0x1800136a0  jnz     short loc_180013680
0x1800136a2  mov     rax, r8
0x1800136a5  lea     rdx, [rcx-2]
0x1800136a9  neg     rax
0x1800136ac  sbb     eax, eax
0x1800136ae  not     eax
0x1800136b0  and     eax, 8007007Ah
0x1800136b5  test    r8, r8
0x1800136b8  cmovnz  rdx, rcx
0x1800136bc  mov     [rdx], r10w
0x1800136c0  retn
```
