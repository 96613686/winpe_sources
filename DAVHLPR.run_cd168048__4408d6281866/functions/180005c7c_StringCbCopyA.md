# StringCbCopyA

- ea: `0x180005c7c`
- end: `0x180005cde`
- name: `StringCbCopyA`
- size: `98`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005450`

## callees

- `0x180005c7c`

## pseudocode

```c
HRESULT __stdcall StringCbCopyA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  __int64 v4; // rax
  STRSAFE_LPSTR v5; // rax

  if ( !cbDest )
    return -2147024809;
  if ( cbDest <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v4;
      --cbDest;
    }
    while ( cbDest );
    v5 = pszDest - 1;
    if ( cbDest )
      v5 = pszDest;
    *v5 = 0;
    return cbDest == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005c7c  test    rdx, rdx
0x180005c7f  jz      short loc_180005CD0
0x180005c81  cmp     rdx, 7FFFFFFFh
0x180005c88  jbe     short loc_180005C91
0x180005c8a  mov     eax, 80070057h
0x180005c8f  jmp     short loc_180005CDA
0x180005c91  mov     eax, 7FFFFFFEh
0x180005c96  test    rax, rax
0x180005c99  jz      short loc_180005CB5
0x180005c9b  mov     r9b, [r8]
0x180005c9e  test    r9b, r9b
0x180005ca1  jz      short loc_180005CB5
0x180005ca3  mov     [rcx], r9b
0x180005ca6  inc     r8
0x180005ca9  inc     rcx
0x180005cac  dec     rax
0x180005caf  sub     rdx, 1
0x180005cb3  jnz     short loc_180005C96
0x180005cb5  test    rdx, rdx
0x180005cb8  lea     rax, [rcx-1]
0x180005cbc  cmovnz  rax, rcx
0x180005cc0  neg     rdx
0x180005cc3  mov     byte ptr [rax], 0
0x180005cc6  sbb     eax, eax
0x180005cc8  not     eax
0x180005cca  and     eax, 8007007Ah
0x180005ccf  retn
0x180005cd0  mov     eax, 80070057h
0x180005cd5  test    rdx, rdx
0x180005cd8  jz      short locret_180005CDD
0x180005cda  mov     byte ptr [rcx], 0
0x180005cdd  retn
```
