# StringCchCatW

- ea: `0x1800048b0`
- end: `0x180004920`
- name: `StringCchCatW`
- size: `112`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003570`

## callees

- `0x180003b60`
- `0x1800048b0`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // r8
  STRSAFE_LPWSTR v4; // rax

  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  v3 = cchDest;
  v4 = pszDest;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  if ( v3 )
    return StringCopyWorkerW(&pszDest[cchDest - v3], v3, 0, L"\\a", 0x7FFFFFFEu);
  else
    return -2147024809;
}

```

## disassembly

```asm
0x1800048b0  sub     rsp, 38h
0x1800048b4  lea     rax, [rdx-1]
0x1800048b8  cmp     rax, 7FFFFFFEh
0x1800048be  ja      short loc_180004912
0x1800048c0  mov     r8, rdx
0x1800048c3  mov     rax, rcx
0x1800048c6  cmp     word ptr [rax], 0
0x1800048ca  jz      short loc_1800048D6
0x1800048cc  add     rax, 2
0x1800048d0  sub     r8, 1
0x1800048d4  jnz     short loc_1800048C6
0x1800048d6  xor     eax, eax
0x1800048d8  mov     r10, rdx
0x1800048db  sub     r10, r8
0x1800048de  mov     r9d, 80070057h
0x1800048e4  test    r8, r8
0x1800048e7  cmovz   r10, rax
0x1800048eb  cmovnz  r9d, eax
0x1800048ef  jz      short loc_180004918
0x1800048f1  sub     rdx, r10; cchDest
0x1800048f4  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x1800048fd  lea     rcx, [rcx+r10*2]; pszDest
0x180004901  xor     r8d, r8d; pcchNewDestLength
0x180004904  lea     r9, aA; "\\a"
0x18000490b  call    StringCopyWorkerW
0x180004910  jmp     short loc_18000491B
0x180004912  mov     r9d, 80070057h
0x180004918  mov     eax, r9d
0x18000491b  add     rsp, 38h
0x18000491f  retn
```
