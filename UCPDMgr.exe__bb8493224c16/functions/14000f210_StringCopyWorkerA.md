# StringCopyWorkerA

- ea: `0x14000f210`
- end: `0x14000f25a`
- name: `StringCopyWorkerA`
- size: `74`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000f210`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  STRSAFE_LPSTR v5; // r8
  __int64 v6; // rax
  signed __int64 v7; // r9
  char v8; // cl
  STRSAFE_LPSTR v9; // rcx
  HRESULT result; // eax

  v5 = pszDest;
  if ( cchDest )
  {
    v6 = 2147483646;
    v7 = pszSrc - pszDest;
    do
    {
      if ( !v6 )
        break;
      v8 = v5[v7];
      if ( !v8 )
        break;
      *v5 = v8;
      --v6;
      ++v5;
      --cchDest;
    }
    while ( cchDest );
  }
  v9 = v5 - 1;
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v9 = v5;
  *v9 = 0;
  return result;
}

```

## disassembly

```asm
0x14000f210  mov     r8, rcx
0x14000f213  test    rdx, rdx
0x14000f216  jz      short loc_14000F23C
0x14000f218  mov     eax, 7FFFFFFEh
0x14000f21d  sub     r9, rcx
0x14000f220  test    rax, rax
0x14000f223  jz      short loc_14000F23C
0x14000f225  mov     cl, [r9+r8]
0x14000f229  test    cl, cl
0x14000f22b  jz      short loc_14000F23C
0x14000f22d  mov     [r8], cl
0x14000f230  dec     rax
0x14000f233  inc     r8
0x14000f236  sub     rdx, 1
0x14000f23a  jnz     short loc_14000F220
0x14000f23c  mov     rax, rdx
0x14000f23f  lea     rcx, [r8-1]
0x14000f243  neg     rax
0x14000f246  sbb     eax, eax
0x14000f248  not     eax
0x14000f24a  and     eax, 8007007Ah
0x14000f24f  test    rdx, rdx
0x14000f252  cmovnz  rcx, r8
0x14000f256  mov     byte ptr [rcx], 0
0x14000f259  retn
```
