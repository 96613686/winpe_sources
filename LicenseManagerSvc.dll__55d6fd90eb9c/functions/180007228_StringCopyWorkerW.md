# StringCopyWorkerW

- ea: `0x180007228`
- end: `0x180007279`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ac8`
- `0x180002d38`

## callees

- `0x180007228`

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
0x180007228  xor     r10d, r10d
0x18000722b  mov     r8, rdx
0x18000722e  mov     eax, 7FFFFFFEh
0x180007233  test    rdx, rdx
0x180007236  jz      short loc_18000725A
0x180007238  test    rax, rax
0x18000723b  jz      short loc_18000725A
0x18000723d  movzx   edx, word ptr [r9]
0x180007241  test    dx, dx
0x180007244  jz      short loc_18000725A
0x180007246  mov     [rcx], dx
0x180007249  add     r9, 2
0x18000724d  add     rcx, 2
0x180007251  dec     rax
0x180007254  sub     r8, 1
0x180007258  jnz     short loc_180007238
0x18000725a  mov     rax, r8
0x18000725d  lea     rdx, [rcx-2]
0x180007261  neg     rax
0x180007264  sbb     eax, eax
0x180007266  not     eax
0x180007268  and     eax, 8007007Ah
0x18000726d  test    r8, r8
0x180007270  cmovnz  rdx, rcx
0x180007274  mov     [rdx], r10w
0x180007278  retn
```
