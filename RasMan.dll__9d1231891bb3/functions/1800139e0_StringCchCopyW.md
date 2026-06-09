# StringCchCopyW

- ea: `0x1800139e0`
- end: `0x180013a4d`
- name: `StringCchCopyW`
- size: `109`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f80`
- `0x180011b40`
- `0x180024990`

## callees

- `0x1800139e0`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  __int64 v4; // rax
  STRSAFE_LPWSTR v5; // rax
  HRESULT result; // eax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -2147024809;
    *pszDest = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    v5 = v3 - 1;
    if ( cchDest )
      v5 = v3;
    *v5 = 0;
    result = -2147024774;
    if ( cchDest )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800139e0  mov     r9, rcx
0x1800139e3  test    rdx, rdx
0x1800139e6  jz      short loc_180013A3C
0x1800139e8  cmp     rdx, 7FFFFFFFh
0x1800139ef  ja      short loc_180013A35
0x1800139f1  mov     eax, 7FFFFFFEh
0x1800139f6  test    rax, rax
0x1800139f9  jz      short loc_180013A19
0x1800139fb  movzx   ecx, word ptr [r8]
0x1800139ff  test    cx, cx
0x180013a02  jz      short loc_180013A19
0x180013a04  mov     [r9], cx
0x180013a08  add     r8, 2
0x180013a0c  add     r9, 2
0x180013a10  dec     rax
0x180013a13  sub     rdx, 1
0x180013a17  jnz     short loc_1800139F6
0x180013a19  test    rdx, rdx
0x180013a1c  lea     rax, [r9-2]
0x180013a20  cmovnz  rax, r9
0x180013a24  xor     ecx, ecx
0x180013a26  test    rdx, rdx
0x180013a29  mov     [rax], cx
0x180013a2c  mov     eax, 8007007Ah
0x180013a31  cmovnz  eax, ecx
0x180013a34  retn
0x180013a35  mov     eax, 80070057h
0x180013a3a  jmp     short loc_180013A46
0x180013a3c  mov     eax, 80070057h
0x180013a41  test    rdx, rdx
0x180013a44  jz      short locret_180013A34
0x180013a46  xor     ecx, ecx
0x180013a48  mov     [r9], cx
0x180013a4c  retn
```
