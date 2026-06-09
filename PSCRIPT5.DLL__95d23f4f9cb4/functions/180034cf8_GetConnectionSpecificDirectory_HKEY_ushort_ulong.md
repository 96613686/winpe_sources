# GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)

- ea: `0x180034cf8`
- end: `0x180034dfb`
- name: `?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z`
- size: `259`
- prototype: `__int64 __fastcall(HKEY hkey, STRSAFE_LPWSTR pszDest, size_t cchDest)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180034518`
- `0x1800357a0`

## callees

- `0x18001fe90`
- `0x180034cf8`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180034dbe`
- `ADVAPI32!RegGetValueW` at `0x180034dbe`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180034d35`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180034d35`
- `KERNEL32!GetLastError` at `0x180034d3f`
- `KERNEL32!GetLastError` at `0x180034d3f`

## pseudocode

```c
__int64 __fastcall GetConnectionSpecificDirectory(HKEY hkey, BYTE *pszDest, size_t cchDest)
{
  size_t v3; // rdi
  signed int LastError; // eax
  int v7; // ebx
  __int64 v8; // rax
  LSTATUS ValueW; // eax
  DWORD pdwType; // [rsp+70h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF

  v3 = (unsigned int)cchDest;
  pdwType = 0;
  if ( GetPrinterDriverDirectoryW(0, 0, 1u, pszDest, 2 * cchDest, &pdwType) )
    goto LABEL_5;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_5:
    v7 = StringCchCatW((STRSAFE_LPWSTR)pszDest, v3, L"\\V4Connections\\");
    if ( v7 >= 0 )
    {
      pdwType = 0;
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&pszDest[2 * v8] );
      pcbData = 2 * (v3 - v8);
      ValueW = RegGetValueW(hkey, 0, L"ConnectionGUID", 2u, &pdwType, &pszDest[2 * v8], &pcbData);
      if ( ValueW )
      {
        if ( ValueW > 0 )
          return (unsigned __int16)ValueW | 0x80070000;
        else
          return (unsigned int)ValueW;
      }
      else if ( pdwType != 1 )
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180034cf8  mov     r11, rsp
0x180034cfb  mov     [r11+8], rbx
0x180034cff  mov     [r11+10h], rbp
0x180034d03  push    rsi
0x180034d04  push    rdi
0x180034d05  push    r14
0x180034d07  sub     rsp, 40h
0x180034d0b  mov     edi, r8d
0x180034d0e  mov     rbp, rcx
0x180034d11  lea     rcx, [r11+18h]
0x180034d15  xor     r14d, r14d
0x180034d18  mov     [r11-30h], rcx
0x180034d1c  mov     rsi, rdx
0x180034d1f  mov     r9, rdx; pDriverDirectory
0x180034d22  mov     [r11+18h], r14d
0x180034d26  lea     eax, [rdi+rdi]
0x180034d29  xor     edx, edx; pEnvironment
0x180034d2b  xor     ecx, ecx; pName
0x180034d2d  mov     [rsp+58h+cbBuf], eax; cbBuf
0x180034d31  lea     r8d, [r14+1]; Level
0x180034d35  call    cs:__imp_GetPrinterDriverDirectoryW
0x180034d3b  test    eax, eax
0x180034d3d  jnz     short loc_180034D5C
0x180034d3f  call    cs:__imp_GetLastError
0x180034d45  mov     ebx, eax
0x180034d47  test    eax, eax
0x180034d49  jle     short loc_180034D54
0x180034d4b  movzx   ebx, ax
0x180034d4e  or      ebx, 80070000h
0x180034d54  test    ebx, ebx
0x180034d56  js      loc_180034DE6
0x180034d5c  mov     rdx, rdi; cchDest
0x180034d5f  lea     r8, aV4connections; "\\V4Connections\\"
0x180034d66  mov     rcx, rsi; pszDest
0x180034d69  call    StringCchCatW
0x180034d6e  mov     ebx, eax
0x180034d70  test    eax, eax
0x180034d72  js      short loc_180034DE6
0x180034d74  mov     [rsp+58h+pdwType], r14d
0x180034d79  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034d7d  inc     rax
0x180034d80  cmp     [rsi+rax*2], r14w
0x180034d85  jnz     short loc_180034D7D
0x180034d87  sub     edi, eax
0x180034d89  lea     rcx, [rsp+58h+arg_18]
0x180034d8e  mov     [rsp+58h+pcbData], rcx; pcbData
0x180034d93  lea     rax, [rsi+rax*2]
0x180034d97  mov     [rsp+58h+pvData], rax; pvData
0x180034d9c  lea     r8, Value; "ConnectionGUID"
0x180034da3  lea     rax, [rsp+58h+pdwType]
0x180034da8  add     edi, edi
0x180034daa  mov     r9d, 2; dwFlags
0x180034db0  mov     qword ptr [rsp+58h+cbBuf], rax; pdwType
0x180034db5  xor     edx, edx; lpSubKey
0x180034db7  mov     [rsp+58h+arg_18], edi
0x180034dbb  mov     rcx, rbp; hkey
0x180034dbe  call    cs:__imp_RegGetValueW
0x180034dc4  test    eax, eax
0x180034dc6  jz      short loc_180034DD9
0x180034dc8  jg      short loc_180034DCE
0x180034dca  mov     ebx, eax
0x180034dcc  jmp     short loc_180034DE6
0x180034dce  movzx   ebx, ax
0x180034dd1  or      ebx, 80070000h
0x180034dd7  jmp     short loc_180034DE6
0x180034dd9  cmp     [rsp+58h+pdwType], 1
0x180034dde  mov     eax, 8000FFFFh
0x180034de3  cmovnz  ebx, eax
0x180034de6  mov     rbp, [rsp+58h+arg_8]
0x180034deb  mov     eax, ebx
0x180034ded  mov     rbx, [rsp+58h+arg_0]
0x180034df2  add     rsp, 40h
0x180034df6  pop     r14
0x180034df8  pop     rdi
0x180034df9  pop     rsi
0x180034dfa  retn
```
