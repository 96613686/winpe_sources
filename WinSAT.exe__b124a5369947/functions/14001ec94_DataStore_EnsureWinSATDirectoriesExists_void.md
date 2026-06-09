# DataStore::EnsureWinSATDirectoriesExists(void)

- ea: `0x14001ec94`
- end: `0x14001ee46`
- name: `?EnsureWinSATDirectoriesExists@DataStore@@SAJXZ`
- size: `434`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001a54c`

## callees

- `0x14001ec94`
- `0x14001f940`
- `0x140113220`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001ecce`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001ecce`
- `KERNEL32!GetLastError` at `0x14001ed2b`
- `KERNEL32!GetLastError` at `0x14001ed98`
- `KERNEL32!GetLastError` at `0x14001ee01`
- `KERNEL32!GetLastError` at `0x14001ed2b`
- `KERNEL32!GetLastError` at `0x14001ed98`
- `KERNEL32!GetLastError` at `0x14001ee01`
- `KERNEL32!CreateDirectoryW` at `0x14001ed21`
- `KERNEL32!CreateDirectoryW` at `0x14001ed8e`
- `KERNEL32!CreateDirectoryW` at `0x14001edf7`
- `KERNEL32!CreateDirectoryW` at `0x14001ed21`
- `KERNEL32!CreateDirectoryW` at `0x14001ed8e`
- `KERNEL32!CreateDirectoryW` at `0x14001edf7`

## pseudocode

```c
__int64 DataStore::EnsureWinSATDirectoriesExists(void)
{
  signed int v0; // ebx
  DWORD LastError; // eax
  bool v2; // sf
  DWORD v3; // eax
  bool v4; // sf
  DWORD v5; // eax
  WCHAR PathName[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Dst[264]; // [rsp+240h] [rbp-228h] BYREF

  if ( ExpandEnvironmentStringsW(L"%WINDIR%", Dst, 0x103u) )
  {
    v0 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", Dst, L"Performance");
    if ( v0 >= 0 )
    {
      if ( CreateDirectoryW(PathName, 0) )
        goto LABEL_10;
      LastError = GetLastError();
      v0 = 0;
      if ( LastError != 183 )
        v0 = LastError;
      v2 = v0 < 0;
      if ( v0 > 0 )
      {
        v0 = (unsigned __int16)v0 | 0x80070000;
        v2 = v0 < 0;
      }
      if ( !v2 )
      {
LABEL_10:
        v0 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s\\%s", Dst, L"Performance", L"WinSAT");
        if ( v0 >= 0 )
        {
          if ( CreateDirectoryW(PathName, 0) )
            goto LABEL_27;
          v3 = GetLastError();
          v0 = 0;
          if ( v3 != 183 )
            v0 = v3;
          v4 = v0 < 0;
          if ( v0 > 0 )
          {
            v0 = (unsigned __int16)v0 | 0x80070000;
            v4 = v0 < 0;
          }
          if ( !v4 )
          {
LABEL_27:
            if ( !App::s_isAxeMode )
            {
              v0 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", Dst, L"Performance\\WinSAT\\DataStore");
              if ( v0 >= 0 && !CreateDirectoryW(PathName, 0) )
              {
                v5 = GetLastError();
                v0 = 0;
                if ( v5 != 183 )
                  v0 = v5;
                if ( v0 > 0 )
                  return (unsigned __int16)v0 | 0x80070000;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14001ec94  mov     [rsp+arg_0], rbx
0x14001ec99  mov     [rsp+arg_8], rbp
0x14001ec9e  push    r14
0x14001eca0  sub     rsp, 460h
0x14001eca7  mov     rax, cs:__security_cookie
0x14001ecae  xor     rax, rsp
0x14001ecb1  mov     [rsp+468h+var_18], rax
0x14001ecb9  mov     r8d, 103h; nSize
0x14001ecbf  lea     rdx, [rsp+468h+Dst]; lpDst
0x14001ecc7  lea     rcx, Src; "%WINDIR%"
0x14001ecce  call    cs:__imp_ExpandEnvironmentStringsW
0x14001ecd4  test    eax, eax
0x14001ecd6  jnz     short loc_14001ECE2
0x14001ecd8  mov     ebx, 80004005h
0x14001ecdd  jmp     loc_14001EE1E
0x14001ece2  mov     r14d, 104h
0x14001ece8  lea     rbp, aPerformance; "Performance"
0x14001ecef  mov     edx, r14d; unsigned __int64
0x14001ecf2  mov     [rsp+468h+var_448], rbp
0x14001ecf7  lea     r9, [rsp+468h+Dst]
0x14001ecff  lea     r8, aSS_0; "%s\\%s"
0x14001ed06  lea     rcx, [rsp+468h+PathName]; unsigned __int16 *
0x14001ed0b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001ed10  mov     ebx, eax
0x14001ed12  test    eax, eax
0x14001ed14  js      loc_14001EE1E
0x14001ed1a  xor     edx, edx; lpSecurityAttributes
0x14001ed1c  lea     rcx, [rsp+468h+PathName]; lpPathName
0x14001ed21  call    cs:__imp_CreateDirectoryW
0x14001ed27  test    eax, eax
0x14001ed29  jnz     short loc_14001ED50
0x14001ed2b  call    cs:__imp_GetLastError
0x14001ed31  xor     ebx, ebx
0x14001ed33  cmp     eax, 0B7h
0x14001ed38  cmovnz  ebx, eax
0x14001ed3b  test    ebx, ebx
0x14001ed3d  jle     short loc_14001ED4A
0x14001ed3f  movzx   ebx, bx
0x14001ed42  or      ebx, 80070000h
0x14001ed48  test    ebx, ebx
0x14001ed4a  js      loc_14001EE1E
0x14001ed50  lea     rax, aWinsat_2; "WinSAT"
0x14001ed57  mov     rdx, r14; unsigned __int64
0x14001ed5a  mov     [rsp+468h+var_440], rax
0x14001ed5f  lea     r9, [rsp+468h+Dst]
0x14001ed67  lea     r8, aSSS_0; "%s\\%s\\%s"
0x14001ed6e  mov     [rsp+468h+var_448], rbp
0x14001ed73  lea     rcx, [rsp+468h+PathName]; unsigned __int16 *
0x14001ed78  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001ed7d  mov     ebx, eax
0x14001ed7f  test    eax, eax
0x14001ed81  js      loc_14001EE1E
0x14001ed87  xor     edx, edx; lpSecurityAttributes
0x14001ed89  lea     rcx, [rsp+468h+PathName]; lpPathName
0x14001ed8e  call    cs:__imp_CreateDirectoryW
0x14001ed94  test    eax, eax
0x14001ed96  jnz     short loc_14001EDB9
0x14001ed98  call    cs:__imp_GetLastError
0x14001ed9e  xor     ebx, ebx
0x14001eda0  cmp     eax, 0B7h
0x14001eda5  cmovnz  ebx, eax
0x14001eda8  test    ebx, ebx
0x14001edaa  jle     short loc_14001EDB7
0x14001edac  movzx   ebx, bx
0x14001edaf  or      ebx, 80070000h
0x14001edb5  test    ebx, ebx
0x14001edb7  js      short loc_14001EE1E
0x14001edb9  cmp     cs:?s_isAxeMode@App@@2_NA, 0; bool App::s_isAxeMode
0x14001edc0  jnz     short loc_14001EE1E
0x14001edc2  lea     rax, aPerformanceWin; "Performance\\WinSAT\\DataStore"
0x14001edc9  mov     rdx, r14; unsigned __int64
0x14001edcc  lea     r9, [rsp+468h+Dst]
0x14001edd4  mov     [rsp+468h+var_448], rax
0x14001edd9  lea     r8, aSS_0; "%s\\%s"
0x14001ede0  lea     rcx, [rsp+468h+PathName]; unsigned __int16 *
0x14001ede5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001edea  mov     ebx, eax
0x14001edec  test    eax, eax
0x14001edee  js      short loc_14001EE1E
0x14001edf0  xor     edx, edx; lpSecurityAttributes
0x14001edf2  lea     rcx, [rsp+468h+PathName]; lpPathName
0x14001edf7  call    cs:__imp_CreateDirectoryW
0x14001edfd  test    eax, eax
0x14001edff  jnz     short loc_14001EE1E
0x14001ee01  call    cs:__imp_GetLastError
0x14001ee07  xor     ebx, ebx
0x14001ee09  cmp     eax, 0B7h
0x14001ee0e  cmovnz  ebx, eax
0x14001ee11  test    ebx, ebx
0x14001ee13  jle     short loc_14001EE1E
0x14001ee15  movzx   ebx, bx
0x14001ee18  or      ebx, 80070000h
0x14001ee1e  mov     eax, ebx
0x14001ee20  mov     rcx, [rsp+468h+var_18]
0x14001ee28  xor     rcx, rsp; StackCookie
0x14001ee2b  call    __security_check_cookie
0x14001ee30  lea     r11, [rsp+468h+var_8]
0x14001ee38  mov     rbx, [r11+10h]
0x14001ee3c  mov     rbp, [r11+18h]
0x14001ee40  mov     rsp, r11
0x14001ee43  pop     r14
0x14001ee45  retn
```
