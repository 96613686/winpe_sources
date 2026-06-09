# StringCchCopyW

- ea: `0x180007380`
- end: `0x1800073b7`
- name: `StringCchCopyW`
- size: `55`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b0ec`

## callees

- `0x180007380`
- `0x1800075e0`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT result; // eax
  size_t v4; // [rsp+20h] [rbp-18h]

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerW_0(pszDest, cchDest, (size_t *)pszSrc, pszSrc, v4);
  result = -2147024809;
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x180007380  sub     rsp, 38h
0x180007384  test    rdx, rdx
0x180007387  jz      short loc_1800073A6
0x180007389  cmp     rdx, 7FFFFFFFh
0x180007390  ja      short loc_18000739F
0x180007392  mov     r9, r8; pszSrc
0x180007395  call    StringCopyWorkerW_0
0x18000739a  add     rsp, 38h
0x18000739e  retn
0x18000739f  mov     eax, 80070057h
0x1800073a4  jmp     short loc_1800073B0
0x1800073a6  mov     eax, 80070057h
0x1800073ab  test    rdx, rdx
0x1800073ae  jz      short loc_18000739A
0x1800073b0  xor     edx, edx
0x1800073b2  mov     [rcx], dx
0x1800073b5  jmp     short loc_18000739A
```
