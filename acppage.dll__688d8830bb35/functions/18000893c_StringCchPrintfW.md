# StringCchPrintfW

- ea: `0x18000893c`
- end: `0x1800089c0`
- name: `StringCchPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038a8`
- `0x180003c4c`
- `0x18000b4d0`
- `0x18000b6a8`

## callees

- `0x18000893c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000897b`
- `msvcrt!_vsnwprintf` at `0x18000897b`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  HRESULT v4; // edx
  size_t v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = cchDest - 1;
    v6 = _vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
    if ( v6 < 0 || v6 > v5 )
    {
      v4 = -2147024774;
      pszDest[v5] = 0;
    }
    else
    {
      v4 = 0;
      if ( v6 == v5 )
        pszDest[v5] = 0;
    }
  }
  else
  {
    v4 = -2147024809;
    *pszDest = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18000893c  mov     [rsp+arg_10], r8
0x180008941  mov     qword ptr [rsp+Args], r9
0x180008946  push    rbx
0x180008947  push    rdi
0x180008948  sub     rsp, 38h
0x18000894c  mov     rax, rdx
0x18000894f  mov     rdi, rcx
0x180008952  test    rdx, rdx
0x180008955  jz      short loc_1800089A8
0x180008957  cmp     rax, 7FFFFFFFh
0x18000895d  jbe     short loc_180008966
0x18000895f  mov     edx, 80070057h
0x180008964  jmp     short loc_1800089B2
0x180008966  lea     rbx, [rdx-1]
0x18000896a  mov     [rsp+48h+var_28], 0
0x180008973  mov     rdx, rbx; BufferCount
0x180008976  lea     r9, [rsp+48h+Args]; Args
0x18000897b  call    cs:__imp__vsnwprintf
0x180008981  test    eax, eax
0x180008983  js      short loc_18000899B
0x180008985  cdqe
0x180008987  cmp     rax, rbx
0x18000898a  ja      short loc_18000899B
0x18000898c  xor     edx, edx
0x18000898e  cmp     rax, rbx
0x180008991  jnz     short loc_1800089B7
0x180008993  xor     eax, eax
0x180008995  mov     [rdi+rbx*2], ax
0x180008999  jmp     short loc_1800089B7
0x18000899b  xor     eax, eax
0x18000899d  mov     edx, 8007007Ah
0x1800089a2  mov     [rdi+rbx*2], ax
0x1800089a6  jmp     short loc_1800089B7
0x1800089a8  mov     edx, 80070057h
0x1800089ad  test    rax, rax
0x1800089b0  jz      short loc_1800089B7
0x1800089b2  xor     ecx, ecx
0x1800089b4  mov     [rdi], cx
0x1800089b7  mov     eax, edx
0x1800089b9  add     rsp, 38h
0x1800089bd  pop     rdi
0x1800089be  pop     rbx
0x1800089bf  retn
```
