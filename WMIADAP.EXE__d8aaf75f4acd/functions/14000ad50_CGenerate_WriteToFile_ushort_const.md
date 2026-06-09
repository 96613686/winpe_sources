# CGenerate::WriteToFile(ushort const *)

- ea: `0x14000ad50`
- end: `0x14000ae83`
- name: `?WriteToFile@CGenerate@@AEAAJPEBG@Z`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x14000a460`
- `0x14000a614`
- `0x14000b9c8`

## callees

- `0x14000ad50`
- `0x140014ad0`
- `0x140014b90`

## import_xrefs

- `msvcrt!wcslen` at `0x14000ad98`
- `msvcrt!wcslen` at `0x14000ada4`
- `msvcrt!wcslen` at `0x14000ad98`
- `msvcrt!wcslen` at `0x14000ada4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ae39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ae39`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000ae09`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000ae09`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000ae2f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000ae2f`

## pseudocode

```c
__int64 __fastcall CGenerate::WriteToFile(HANDLE *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  DWORD v5; // r14d
  int v6; // edx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rax
  void *v9; // rsp
  const void *v10; // rdx
  signed int LastError; // eax
  __int64 v13; // [rsp+0h] [rbp-40h] BYREF
  CHAR MultiByteStr[4]; // [rsp+40h] [rbp+0h] BYREF

  if ( (char *)this[13] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && a2 )
  {
    v4 = 0;
    *(_DWORD *)MultiByteStr = 0;
    v5 = wcslen(a2);
    v6 = 2 * wcslen(a2);
    v7 = v6 + 17LL;
    if ( v7 <= v6 + 2LL )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
    try
    {
      v9 = alloca(v8);
      if ( &v13 == (__int64 *)-64LL )
      {
        v10 = 0;
      }
      else
      {
        MultiByteStr[0] = 0;
        v10 = (const void *)((unsigned __int64)MultiByteStr
                           & -(__int64)(WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, v6 + 2, 0, 0) != 0));
      }
      if ( WriteFile(this[13], v10, v5, (LPDWORD)MultiByteStr, 0) )
      {
        if ( v5 != *(_DWORD *)MultiByteStr )
          v4 = -2147467259;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    catch ( ... )
    {
      return (unsigned int)-2147418113;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x14000ad50  push    rbp
0x14000ad52  push    rbx
0x14000ad53  push    rsi
0x14000ad54  push    rdi
0x14000ad55  push    r14
0x14000ad57  push    r15
0x14000ad59  sub     rsp, 58h
0x14000ad5d  lea     rbp, [rsp+40h]
0x14000ad62  mov     rax, cs:__security_cookie
0x14000ad69  xor     rax, rbp
0x14000ad6c  mov     [rbp+40h+var_38], rax
0x14000ad70  mov     rdi, rdx
0x14000ad73  mov     r15, rcx
0x14000ad76  mov     rax, [rcx+68h]
0x14000ad7a  dec     rax
0x14000ad7d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000ad81  ja      loc_14000AE63
0x14000ad87  test    rdx, rdx
0x14000ad8a  jz      loc_14000AE63
0x14000ad90  xor     ebx, ebx
0x14000ad92  mov     dword ptr [rbp+40h+MultiByteStr], ebx
0x14000ad95  mov     rcx, rdx; String
0x14000ad98  call    cs:__imp_wcslen
0x14000ad9e  mov     r14, rax
0x14000ada1  mov     rcx, rdi; String
0x14000ada4  call    cs:__imp_wcslen
0x14000adaa  lea     edx, [rax+rax]
0x14000adad  movsxd  rcx, edx
0x14000adb0  add     rcx, 2
0x14000adb4  lea     rax, [rcx+0Fh]
0x14000adb8  cmp     rax, rcx
0x14000adbb  ja      short loc_14000ADC7
0x14000adbd  mov     rax, 0FFFFFFFFFFFFFF0h
0x14000adc7  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000adcb  call    _alloca_probe
0x14000add0  sub     rsp, rax
0x14000add3  lea     rsi, [rsp+80h+MultiByteStr]
0x14000add8  test    rsi, rsi
0x14000addb  jz      short loc_14000AE19
0x14000addd  mov     byte ptr [rsi], 0
0x14000ade0  lea     eax, [rdx+2]
0x14000ade3  mov     [rsp+80h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x14000adec  mov     [rsp+80h+lpDefaultChar], 0; lpDefaultChar
0x14000adf5  mov     [rsp+80h+cbMultiByte], eax; cbMultiByte
0x14000adf9  mov     [rsp+80h+lpMultiByteStr], rsi; lpMultiByteStr
0x14000adfe  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000ae02  mov     r8, rdi; lpWideCharStr
0x14000ae05  xor     edx, edx; dwFlags
0x14000ae07  xor     ecx, ecx; CodePage
0x14000ae09  call    cs:__imp_WideCharToMultiByte
0x14000ae0f  neg     eax
0x14000ae11  sbb     rdx, rdx
0x14000ae14  and     rdx, rsi
0x14000ae17  jmp     short loc_14000AE1B
0x14000ae19  xor     edx, edx; lpBuffer
0x14000ae1b  mov     [rsp+80h+lpMultiByteStr], 0; lpOverlapped
0x14000ae24  lea     r9, [rbp+40h+MultiByteStr]; lpNumberOfBytesWritten
0x14000ae28  mov     r8d, r14d; nNumberOfBytesToWrite
0x14000ae2b  mov     rcx, [r15+68h]; hFile
0x14000ae2f  call    cs:__imp_WriteFile
0x14000ae35  test    eax, eax
0x14000ae37  jnz     short loc_14000AE50
0x14000ae39  call    cs:__imp_GetLastError
0x14000ae3f  mov     ebx, eax
0x14000ae41  test    eax, eax
0x14000ae43  jle     short loc_14000AE5C
0x14000ae45  movzx   ebx, ax
0x14000ae48  or      ebx, 80070000h
0x14000ae4e  jmp     short loc_14000AE5C
0x14000ae50  mov     eax, 80004005h
0x14000ae55  cmp     r14d, dword ptr [rbp+40h+MultiByteStr]
0x14000ae59  cmovnz  ebx, eax
0x14000ae5c  jmp     short loc_14000AE68
0x14000ae5e  mov     ebx, dword ptr [rbp+40h+MultiByteStr]
0x14000ae61  jmp     short loc_14000AE68
0x14000ae63  mov     ebx, 80070057h
0x14000ae68  mov     eax, ebx
0x14000ae6a  mov     rcx, [rbp+40h+var_38]
0x14000ae6e  xor     rcx, rbp; StackCookie
0x14000ae71  call    __security_check_cookie
0x14000ae76  lea     rsp, [rbp+18h]
0x14000ae7a  pop     r15
0x14000ae7c  pop     r14
0x14000ae7e  pop     rdi
0x14000ae7f  pop     rsi
0x14000ae80  pop     rbx
0x14000ae81  pop     rbp
0x14000ae82  retn
```
