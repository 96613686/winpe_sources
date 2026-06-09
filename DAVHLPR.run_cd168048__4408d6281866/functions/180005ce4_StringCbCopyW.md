# StringCbCopyW

- ea: `0x180005ce4`
- end: `0x180005d30`
- name: `StringCbCopyW`
- size: `76`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005450`

## callees

- `0x180003b60`
- `0x180005ce4`

## pseudocode

```c
HRESULT __stdcall StringCbCopyW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx

  if ( !(cbDest >> 1) )
    return -2147024809;
  if ( cbDest >> 1 <= 0x7FFFFFFF )
    return StringCopyWorkerW(pszDest, cbDest >> 1, 0, pszSrc, 0x7FFFFFFEu);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x180005ce4  sub     rsp, 38h
0x180005ce8  mov     rax, rdx
0x180005ceb  shr     rax, 1
0x180005cee  jz      short loc_180005D1A
0x180005cf0  cmp     rax, 7FFFFFFFh
0x180005cf6  jbe     short loc_180005CFF
0x180005cf8  mov     edx, 80070057h
0x180005cfd  jmp     short loc_180005D24
0x180005cff  mov     r9, r8; pszSrc
0x180005d02  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x180005d0b  xor     r8d, r8d; pcchNewDestLength
0x180005d0e  mov     rdx, rax; cchDest
0x180005d11  call    StringCopyWorkerW
0x180005d16  mov     edx, eax
0x180005d18  jmp     short loc_180005D29
0x180005d1a  mov     edx, 80070057h
0x180005d1f  test    rax, rax
0x180005d22  jz      short loc_180005D29
0x180005d24  xor     eax, eax
0x180005d26  mov     [rcx], ax
0x180005d29  mov     eax, edx
0x180005d2b  add     rsp, 38h
0x180005d2f  retn
```
