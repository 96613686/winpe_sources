# StringCchCopyNA

- ea: `0x18000cb08`
- end: `0x18000cb4b`
- name: `StringCchCopyNA`
- size: `67`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bf68`

## callees

- `0x18000cb08`
- `0x18000cb54`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)
{
  HRESULT result; // eax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF && cchToCopy <= 0x7FFFFFFE )
    return StringCopyWorkerA(pszDest, cchDest, (size_t *)pszSrc, pszSrc, cchToCopy);
  result = -2147024809;
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x18000cb08  sub     rsp, 38h
0x18000cb0c  test    rdx, rdx
0x18000cb0f  jz      short loc_18000CB39
0x18000cb11  cmp     rdx, 7FFFFFFFh
0x18000cb18  jbe     short loc_18000CB21
0x18000cb1a  mov     eax, 80070057h
0x18000cb1f  jmp     short loc_18000CB43
0x18000cb21  cmp     r9, 7FFFFFFEh
0x18000cb28  ja      short loc_18000CB1A
0x18000cb2a  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x18000cb2f  mov     r9, r8; pszSrc
0x18000cb32  call    StringCopyWorkerA
0x18000cb37  jmp     short loc_18000CB46
0x18000cb39  mov     eax, 80070057h
0x18000cb3e  test    rdx, rdx
0x18000cb41  jz      short loc_18000CB46
0x18000cb43  mov     byte ptr [rcx], 0
0x18000cb46  add     rsp, 38h
0x18000cb4a  retn
```
