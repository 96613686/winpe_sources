# StringCopyWorkerW

- ea: `0x14000f1b0`
- end: `0x14000f202`
- name: `StringCopyWorkerW`
- size: `82`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000f1b0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  STRSAFE_LPWSTR v5; // r8
  __int64 v6; // rax
  signed __int64 v7; // r9
  wchar_t v8; // cx
  STRSAFE_LPWSTR v9; // rcx
  HRESULT result; // eax

  v5 = pszDest;
  if ( cchDest )
  {
    v6 = 2147483646;
    v7 = (char *)pszSrc - (char *)pszDest;
    do
    {
      if ( !v6 )
        break;
      v8 = *(STRSAFE_LPWSTR)((char *)v5 + v7);
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
0x14000f1b0  xor     r10d, r10d
0x14000f1b3  mov     r8, rcx
0x14000f1b6  test    rdx, rdx
0x14000f1b9  jz      short loc_14000F1E3
0x14000f1bb  mov     eax, 7FFFFFFEh
0x14000f1c0  sub     r9, rcx
0x14000f1c3  test    rax, rax
0x14000f1c6  jz      short loc_14000F1E3
0x14000f1c8  movzx   ecx, word ptr [r9+r8]
0x14000f1cd  test    cx, cx
0x14000f1d0  jz      short loc_14000F1E3
0x14000f1d2  mov     [r8], cx
0x14000f1d6  dec     rax
0x14000f1d9  add     r8, 2
0x14000f1dd  sub     rdx, 1
0x14000f1e1  jnz     short loc_14000F1C3
0x14000f1e3  mov     rax, rdx
0x14000f1e6  lea     rcx, [r8-2]
0x14000f1ea  neg     rax
0x14000f1ed  sbb     eax, eax
0x14000f1ef  not     eax
0x14000f1f1  and     eax, 8007007Ah
0x14000f1f6  test    rdx, rdx
0x14000f1f9  cmovnz  rcx, r8
0x14000f1fd  mov     [rcx], r10w
0x14000f201  retn
```
