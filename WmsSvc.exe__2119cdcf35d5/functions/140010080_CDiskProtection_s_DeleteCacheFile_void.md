# CDiskProtection::s_DeleteCacheFile(void)

- ea: `0x140010080`
- end: `0x140010273`
- name: `?s_DeleteCacheFile@CDiskProtection@@KAJXZ`
- size: `499`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x140009af0`
- `0x14000b700`
- `0x140013660`

## callees

- `0x140010080`
- `0x140015874`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1400101c0`
- `KERNEL32!DeleteFileW` at `0x1400101c0`
- `KERNEL32!SetFileAttributesW` at `0x1400100db`
- `KERNEL32!SetFileAttributesW` at `0x1400100db`
- `KERNEL32!GetLastError` at `0x1400100e9`
- `KERNEL32!GetLastError` at `0x1400100f8`
- `KERNEL32!GetLastError` at `0x1400101ca`
- `KERNEL32!GetLastError` at `0x1400100e9`
- `KERNEL32!GetLastError` at `0x1400100f8`
- `KERNEL32!GetLastError` at `0x1400101ca`
- `KERNEL32!IsDebuggerPresent` at `0x14001014c`
- `KERNEL32!IsDebuggerPresent` at `0x14001021e`
- `KERNEL32!IsDebuggerPresent` at `0x14001014c`
- `KERNEL32!IsDebuggerPresent` at `0x14001021e`
- `SHLWAPI!SHDeleteKeyW` at `0x14001024c`
- `SHLWAPI!SHDeleteKeyW` at `0x14001024c`

## string_xrefs

- `0x1400100b1`: `CDiskProtection::s_DeleteCacheFile\n`
- `0x14001011b`: `CDiskProtection::s_DeleteCacheFile`
- `0x1400101ed`: `CDiskProtection::s_DeleteCacheFile`
- `0x14001023e`: `SYSTEM\CurrentControlSet\Services\VCF\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CDiskProtection::s_DeleteCacheFile(void)
{
  unsigned __int64 v0; // rdx
  signed int CacheFilePath; // ebx
  signed int v2; // eax
  __int64 v3; // r9
  __int64 v4; // r8
  signed int LastError; // eax
  signed int v7; // [rsp+30h] [rbp-258h]
  signed int v8; // [rsp+38h] [rbp-250h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-248h] BYREF

  memset_0(FileName, 0, 0x208u);
  DEBUGMSG(L"CDiskProtection::s_DeleteCacheFile\n");
  CacheFilePath = CDiskProtection::s_VcfGetCacheFilePath(FileName, v0);
  if ( CacheFilePath >= 0 )
  {
    if ( SetFileAttributesW(FileName, 0x80u) )
    {
      if ( !DeleteFileW(FileName) )
      {
        LastError = GetLastError();
        CacheFilePath = LastError;
        if ( LastError > 0 )
          CacheFilePath = (unsigned __int16)LastError | 0x80070000;
        if ( CacheFilePath >= 0 )
          CacheFilePath = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          0x10D2u,
          L"CDiskProtection::s_DeleteCacheFile",
          L"CBRAEx",
          L"fSuccess",
          CacheFilePath);
        if ( IsDebuggerPresent() )
        {
          v3 = 4306;
          goto LABEL_10;
        }
        v4 = 4306;
LABEL_12:
        v7 = CacheFilePath;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v4,
          L"CDiskProtection::s_DeleteCacheFile",
          L"CBRAEx",
          L"fSuccess",
          v7);
        return (unsigned int)CacheFilePath;
      }
      SHDeleteKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\VCF\\Parameters");
    }
    else if ( GetLastError() != 2 )
    {
      v2 = GetLastError();
      CacheFilePath = v2;
      if ( v2 > 0 )
        CacheFilePath = (unsigned __int16)v2 | 0x80070000;
      if ( CacheFilePath >= 0 )
        CacheFilePath = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x10CFu,
        L"CDiskProtection::s_DeleteCacheFile",
        L"CBRAEx",
        L"fSuccess",
        CacheFilePath);
      if ( IsDebuggerPresent() )
      {
        v3 = 4303;
LABEL_10:
        v8 = CacheFilePath;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v3,
          L"CDiskProtection::s_DeleteCacheFile",
          L"CBRAEx",
          L"fSuccess",
          v8);
        return (unsigned int)CacheFilePath;
      }
      v4 = 4303;
      goto LABEL_12;
    }
    return 0;
  }
  return (unsigned int)CacheFilePath;
}

```

## disassembly

```asm
0x140010080  push    rbx
0x140010082  push    rbp
0x140010083  push    rsi
0x140010084  push    r14
0x140010086  sub     rsp, 268h
0x14001008d  mov     rax, cs:__security_cookie
0x140010094  xor     rax, rsp
0x140010097  mov     [rsp+288h+var_38], rax
0x14001009f  xor     edx, edx; Val
0x1400100a1  lea     rcx, [rsp+288h+FileName]; void *
0x1400100a6  mov     r8d, 208h; Size
0x1400100ac  call    memset_0
0x1400100b1  lea     rcx, aCdiskprotectio; "CDiskProtection::s_DeleteCacheFile\n"
0x1400100b8  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400100bd  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x1400100c2  call    ?s_VcfGetCacheFilePath@CDiskProtection@@KAJPEAG_K@Z; CDiskProtection::s_VcfGetCacheFilePath(ushort *,unsigned __int64)
0x1400100c7  mov     ebx, eax
0x1400100c9  test    eax, eax
0x1400100cb  js      loc_140010254
0x1400100d1  mov     edx, 80h; dwFileAttributes
0x1400100d6  lea     rcx, [rsp+288h+FileName]; lpFileName
0x1400100db  call    cs:__imp_SetFileAttributesW
0x1400100e1  test    eax, eax
0x1400100e3  jnz     loc_1400101BB
0x1400100e9  call    cs:__imp_GetLastError
0x1400100ef  cmp     eax, 2
0x1400100f2  jz      loc_140010252
0x1400100f8  call    cs:__imp_GetLastError
0x1400100fe  mov     ebx, eax
0x140010100  test    eax, eax
0x140010102  jle     short loc_14001010D
0x140010104  movzx   ebx, ax
0x140010107  or      ebx, 80070000h
0x14001010d  mov     eax, 80004005h
0x140010112  lea     r14, aCbraex; "CBRAEx"
0x140010119  test    ebx, ebx
0x14001011b  lea     rsi, aCdiskprotectio_0; "CDiskProtection::s_DeleteCacheFile"
0x140010122  lea     rbp, aFsuccess; "fSuccess"
0x140010129  mov     r9, r14; unsigned __int16 *
0x14001012c  cmovns  ebx, eax
0x14001012f  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010136  mov     [rsp+288h+var_260], ebx; int
0x14001013a  mov     r8, rsi; unsigned __int16 *
0x14001013d  mov     edx, 10CFh; unsigned int
0x140010142  mov     [rsp+288h+var_268], rbp; unsigned __int16 *
0x140010147  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001014c  call    cs:__imp_IsDebuggerPresent
0x140010152  test    eax, eax
0x140010154  jz      short loc_14001018C
0x140010156  mov     r9d, 10CFh
0x14001015c  mov     [rsp+288h+var_250], ebx
0x140010160  lea     r8, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010167  mov     [rsp+288h+var_258], rbp
0x14001016c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140010173  mov     qword ptr [rsp+288h+var_260], r14
0x140010178  mov     ecx, 2; unsigned __int8
0x14001017d  mov     [rsp+288h+var_268], rsi
0x140010182  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140010187  jmp     loc_140010254
0x14001018c  mov     r8d, 10CFh
0x140010192  mov     dword ptr [rsp+288h+var_258], ebx
0x140010196  lea     rdx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14001019d  mov     qword ptr [rsp+288h+var_260], rbp
0x1400101a2  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400101a9  mov     r9, rsi
0x1400101ac  mov     [rsp+288h+var_268], r14
0x1400101b1  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400101b6  jmp     loc_140010254
0x1400101bb  lea     rcx, [rsp+288h+FileName]; lpFileName
0x1400101c0  call    cs:__imp_DeleteFileW
0x1400101c6  test    eax, eax
0x1400101c8  jnz     short loc_14001023E
0x1400101ca  call    cs:__imp_GetLastError
0x1400101d0  mov     ebx, eax
0x1400101d2  test    eax, eax
0x1400101d4  jle     short loc_1400101DF
0x1400101d6  movzx   ebx, ax
0x1400101d9  or      ebx, 80070000h
0x1400101df  mov     eax, 80004005h
0x1400101e4  lea     r14, aCbraex; "CBRAEx"
0x1400101eb  test    ebx, ebx
0x1400101ed  lea     rsi, aCdiskprotectio_0; "CDiskProtection::s_DeleteCacheFile"
0x1400101f4  lea     rbp, aFsuccess; "fSuccess"
0x1400101fb  mov     r9, r14; unsigned __int16 *
0x1400101fe  cmovns  ebx, eax
0x140010201  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010208  mov     [rsp+288h+var_260], ebx; int
0x14001020c  mov     r8, rsi; unsigned __int16 *
0x14001020f  mov     edx, 10D2h; unsigned int
0x140010214  mov     [rsp+288h+var_268], rbp; unsigned __int16 *
0x140010219  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001021e  call    cs:__imp_IsDebuggerPresent
0x140010224  test    eax, eax
0x140010226  jz      short loc_140010233
0x140010228  mov     r9d, 10D2h
0x14001022e  jmp     loc_14001015C
0x140010233  mov     r8d, 10D2h
0x140010239  jmp     loc_140010192
0x14001023e  lea     rdx, ?s_szDriverParametersKeyName@CDiskProtection@@1QBGB; "SYSTEM\\CurrentControlSet\\Services\\VC"...
0x140010245  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001024c  call    cs:__imp_SHDeleteKeyW
0x140010252  xor     ebx, ebx
0x140010254  mov     eax, ebx
0x140010256  mov     rcx, [rsp+288h+var_38]
0x14001025e  xor     rcx, rsp; StackCookie
0x140010261  call    __security_check_cookie
0x140010266  add     rsp, 268h
0x14001026d  pop     r14
0x14001026f  pop     rsi
0x140010270  pop     rbp
0x140010271  pop     rbx
0x140010272  retn
```
