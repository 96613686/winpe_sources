# StringCchCopyW

- ea: `0x180005d38`
- end: `0x180005d81`
- name: `StringCchCopyW`
- size: `73`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003570`
- `0x180005450`
- `0x180005a70`

## callees

- `0x180003b60`
- `0x180005d38`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerW(pszDest, cchDest, 0, pszSrc, 0x7FFFFFFEu);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x180005d38  sub     rsp, 38h
0x180005d3c  mov     rax, rdx
0x180005d3f  test    rdx, rdx
0x180005d42  jz      short loc_180005D6B
0x180005d44  cmp     rax, 7FFFFFFFh
0x180005d4a  jbe     short loc_180005D53
0x180005d4c  mov     edx, 80070057h; cchDest
0x180005d51  jmp     short loc_180005D75
0x180005d53  mov     r9, r8; pszSrc
0x180005d56  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x180005d5f  xor     r8d, r8d; pcchNewDestLength
0x180005d62  call    StringCopyWorkerW
0x180005d67  mov     edx, eax
0x180005d69  jmp     short loc_180005D7A
0x180005d6b  mov     edx, 80070057h
0x180005d70  test    rax, rax
0x180005d73  jz      short loc_180005D7A
0x180005d75  xor     eax, eax
0x180005d77  mov     [rcx], ax
0x180005d7a  mov     eax, edx
0x180005d7c  add     rsp, 38h
0x180005d80  retn
```
