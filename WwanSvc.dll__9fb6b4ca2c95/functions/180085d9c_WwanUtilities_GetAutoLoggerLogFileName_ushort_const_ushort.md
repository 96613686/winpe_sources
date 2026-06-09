# WwanUtilities::GetAutoLoggerLogFileName(ushort const *,ushort *)

- ea: `0x180085d9c`
- end: `0x180085f10`
- name: `?GetAutoLoggerLogFileName@WwanUtilities@@CAKPEBGPEAG@Z`
- size: `372`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180085904`
- `0x180085af8`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x18000f138`
- `0x180012300`
- `0x180085d9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085ee1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085e0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180085e01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180085e01`

## string_xrefs

- `0x180085e13`: `Failed to get system directory path. Error=0x%x`
- `0x180085ebf`: `Failed to use StringCchPrintf to construct the log file pathname. Error=0x%x`

## pseudocode

```c
__int64 __fastcall WwanUtilities::GetAutoLoggerLogFileName(const unsigned __int16 *LastError, unsigned __int16 *a2)
{
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v6[264]; // [rsp+240h] [rbp+140h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v6, 0, 0x208u);
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    if ( StringCchPrintfW(v6, 0x104u, L"%s%s%s", Buffer, L"\\LogFiles\\WMI\\", LastError) < 0 )
    {
      if ( (StringCchPrintfW(v6, 0x104u, L"%s%s%s", Buffer, L"\\LogFiles\\WMI\\", LastError) & 0x1FFF0000) == 0x70000 )
        LODWORD(LastError) = (unsigned __int16)StringCchPrintfW(
                                                 v6,
                                                 0x104u,
                                                 L"%s%s%s",
                                                 Buffer,
                                                 L"\\LogFiles\\WMI\\",
                                                 LastError);
      else
        LODWORD(LastError) = StringCchPrintfW(v6, 0x104u, L"%s%s%s", Buffer, L"\\LogFiles\\WMI\\", LastError);
      if ( (_DWORD)LastError )
        WwanLog::Error(
          "WwanUtilities::GetAutoLoggerLogFileName",
          0,
          L"Failed to use StringCchPrintf to construct the log file pathname. Error=0x%x",
          (unsigned int)LastError);
    }
    else
    {
      LODWORD(LastError) = 0;
    }
  }
  else
  {
    LastError = (const unsigned __int16 *)GetLastError();
    WwanLog::Error(
      "WwanUtilities::GetAutoLoggerLogFileName",
      0,
      L"Failed to get system directory path. Error=0x%x",
      LastError);
  }
  _o_wcscpy_s(a2, 260, v6);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180085d9c  mov     [rsp-8+arg_10], rbx
0x180085da1  mov     [rsp-8+arg_18], rsi
0x180085da6  push    rbp
0x180085da7  push    rdi
0x180085da8  push    r15
0x180085daa  lea     rbp, [rsp-360h]
0x180085db2  sub     rsp, 460h
0x180085db9  mov     rax, cs:__security_cookie
0x180085dc0  xor     rax, rsp
0x180085dc3  mov     [rbp+370h+var_20], rax
0x180085dca  mov     rdi, rdx
0x180085dcd  mov     rbx, rcx
0x180085dd0  mov     esi, 208h
0x180085dd5  lea     rcx, [rsp+470h+Buffer]; void *
0x180085dda  mov     r8d, esi; Size
0x180085ddd  xor     edx, edx; Val
0x180085ddf  call    memset_0
0x180085de4  mov     r8d, esi; Size
0x180085de7  lea     rcx, [rbp+370h+var_230]; void *
0x180085dee  xor     edx, edx; Val
0x180085df0  call    memset_0
0x180085df5  mov     esi, 104h
0x180085dfa  lea     rcx, [rsp+470h+Buffer]; lpBuffer
0x180085dff  mov     edx, esi; uSize
0x180085e01  call    cs:__imp_GetSystemDirectoryW
0x180085e07  test    eax, eax
0x180085e09  jnz     short loc_180085E22
0x180085e0b  call    cs:__imp_GetLastError
0x180085e11  mov     ebx, eax
0x180085e13  lea     r8, aFailedToGetSys; "Failed to get system directory path. Er"...
0x180085e1a  mov     r9d, eax
0x180085e1d  jmp     loc_180085EC6
0x180085e22  lea     r15, aLogfilesWmi; "\\LogFiles\\WMI\\"
0x180085e29  mov     [rsp+470h+var_448], rbx
0x180085e2e  lea     r9, [rsp+470h+Buffer]
0x180085e33  mov     [rsp+470h+var_450], r15
0x180085e38  lea     r8, aSSS_0; "%s%s%s"
0x180085e3f  mov     rdx, rsi; unsigned __int64
0x180085e42  lea     rcx, [rbp+370h+var_230]; unsigned __int16 *
0x180085e49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180085e4e  test    eax, eax
0x180085e50  js      short loc_180085E56
0x180085e52  xor     ebx, ebx
0x180085e54  jmp     short loc_180085ED4
0x180085e56  mov     [rsp+470h+var_448], rbx
0x180085e5b  lea     r9, [rsp+470h+Buffer]
0x180085e60  lea     r8, aSSS_0; "%s%s%s"
0x180085e67  mov     [rsp+470h+var_450], r15
0x180085e6c  mov     rdx, rsi; unsigned __int64
0x180085e6f  lea     rcx, [rbp+370h+var_230]; unsigned __int16 *
0x180085e76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180085e7b  and     eax, 1FFF0000h
0x180085e80  mov     [rsp+470h+var_448], rbx
0x180085e85  mov     [rsp+470h+var_450], r15
0x180085e8a  lea     r9, [rsp+470h+Buffer]
0x180085e8f  lea     r8, aSSS_0; "%s%s%s"
0x180085e96  mov     rdx, rsi; unsigned __int64
0x180085e99  lea     rcx, [rbp+370h+var_230]; unsigned __int16 *
0x180085ea0  cmp     eax, 70000h
0x180085ea5  jnz     short loc_180085EB1
0x180085ea7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180085eac  movzx   ebx, ax
0x180085eaf  jmp     short loc_180085EB8
0x180085eb1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180085eb6  mov     ebx, eax
0x180085eb8  test    ebx, ebx
0x180085eba  jz      short loc_180085ED4
0x180085ebc  mov     r9d, ebx
0x180085ebf  lea     r8, aFailedToUseStr; "Failed to use StringCchPrintf to constr"...
0x180085ec6  xor     edx, edx; struct _GUID *
0x180085ec8  lea     rcx, aWwanutilitiesG; "WwanUtilities::GetAutoLoggerLogFileName"
0x180085ecf  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180085ed4  lea     r8, [rbp+370h+var_230]
0x180085edb  mov     rdx, rsi
0x180085ede  mov     rcx, rdi
0x180085ee1  call    cs:__imp__o_wcscpy_s
0x180085ee7  mov     eax, ebx
0x180085ee9  mov     rcx, [rbp+370h+var_20]
0x180085ef0  xor     rcx, rsp; StackCookie
0x180085ef3  call    __security_check_cookie
0x180085ef8  lea     r11, [rsp+470h+var_10]
0x180085f00  mov     rbx, [r11+30h]
0x180085f04  mov     rsi, [r11+38h]
0x180085f08  mov     rsp, r11
0x180085f0b  pop     r15
0x180085f0d  pop     rdi
0x180085f0e  pop     rbp
0x180085f0f  retn
```
