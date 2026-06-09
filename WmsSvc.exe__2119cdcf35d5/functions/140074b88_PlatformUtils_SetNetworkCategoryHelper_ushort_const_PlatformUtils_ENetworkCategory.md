# PlatformUtils::SetNetworkCategoryHelper(ushort const *,PlatformUtils::ENetworkCategory)

- ea: `0x140074b88`
- end: `0x140074ea6`
- name: `?SetNetworkCategoryHelper@PlatformUtils@@YAJPEBGW4ENetworkCategory@1@@Z`
- size: `798`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140074eac`

## callees

- `0x1400033e8`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140074b88`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x140074c4f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140074c99`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140074c4f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140074c99`
- `KERNEL32!CopyFileW` at `0x140074cd5`
- `KERNEL32!CopyFileW` at `0x140074cd5`
- `KERNEL32!GetLastError` at `0x140074cfd`
- `KERNEL32!GetLastError` at `0x140074d8e`
- `KERNEL32!GetLastError` at `0x140074dbd`
- `KERNEL32!GetLastError` at `0x140074cfd`
- `KERNEL32!GetLastError` at `0x140074d8e`
- `KERNEL32!GetLastError` at `0x140074dbd`
- `KERNEL32!IsDebuggerPresent` at `0x140074d58`
- `KERNEL32!IsDebuggerPresent` at `0x140074e20`
- `KERNEL32!IsDebuggerPresent` at `0x140074d58`
- `KERNEL32!IsDebuggerPresent` at `0x140074e20`

## string_xrefs

- `0x140074d34`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x140074dff`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x140074cec`: `PlatformUtils::SetNetworkCategoryHelper - completed\n`
- `0x140074c64`: `%%windir%%\System32\NetworkList\Icons\%s_%s`
- `0x140074c1d`: `%%windir%%\System32\NetworkList\Icons\StockIcons\%s_%s`

## pseudocode

```c
__int64 __fastcall PlatformUtils::SetNetworkCategoryHelper(__int64 a1)
{
  __int64 v2; // rdi
  signed int v3; // ebx
  signed int v4; // eax
  const unsigned __int16 *v5; // r12
  unsigned int v6; // r15d
  signed int v7; // eax
  unsigned int v8; // r12d
  signed int LastError; // eax
  signed int v11; // [rsp+30h] [rbp-D0h]
  signed int v12; // [rsp+30h] [rbp-D0h]
  signed int v13; // [rsp+38h] [rbp-C8h]
  signed int v14; // [rsp+38h] [rbp-C8h]
  WCHAR Src[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR NewFileName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR Dst[264]; // [rsp+460h] [rbp+360h] BYREF

  memset_0(Src, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  memset_0(NewFileName, 0, 0x208u);
  DEBUGMSG(L"PlatformUtils::SetNetworkCategoryHelper - started\n");
  v2 = 0;
  while ( 1 )
  {
    v3 = StringCchPrintfW(
           Src,
           0x104u,
           L"%%windir%%\\System32\\NetworkList\\Icons\\StockIcons\\%s_%s",
           L"office",
           off_14009C6E0[v2]);
    if ( v3 < 0 )
    {
      v8 = 617;
LABEL_25:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
        v8,
        L"PlatformUtils::SetNetworkCategoryHelper",
        L"CHRA",
        L"hr",
        v3);
      if ( IsDebuggerPresent() )
      {
        v14 = v3;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
          v8,
          L"PlatformUtils::SetNetworkCategoryHelper",
          L"CHRA",
          L"hr",
          v14);
      }
      else
      {
        v12 = v3;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
          v8,
          L"PlatformUtils::SetNetworkCategoryHelper",
          L"CHRA",
          L"hr",
          v12);
      }
      return (unsigned int)v3;
    }
    if ( ExpandEnvironmentStringsW(Src, Dst, 0x104u) - 1 > 0x103 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v5 = L"dwResult != 0 && dwResult <= (sizeof(*RtlpNumberOf(szSourceFile)))";
      v6 = 620;
      goto LABEL_12;
    }
    v3 = StringCchPrintfW(Src, 0x104u, L"%%windir%%\\System32\\NetworkList\\Icons\\%s_%s", a1, off_14009C6E0[v2]);
    if ( v3 < 0 )
    {
      v8 = 628;
      goto LABEL_25;
    }
    if ( ExpandEnvironmentStringsW(Src, NewFileName, 0x104u) - 1 > 0x103 )
      break;
    DEBUGMSG(L"PlatformUtils::SetNetworkCategoryHelper - szSourceFile: %s, szTragetFile: %s\n", Dst, NewFileName);
    if ( !CopyFileW(Dst, NewFileName, 0) )
    {
      v4 = GetLastError();
      v3 = v4;
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      v5 = L"fSuccess";
      v6 = 635;
      goto LABEL_12;
    }
    if ( (unsigned __int64)++v2 >= 4 )
    {
      DEBUGMSG(L"PlatformUtils::SetNetworkCategoryHelper - completed\n");
      return (unsigned int)v3;
    }
  }
  v7 = GetLastError();
  v3 = v7;
  if ( v7 > 0 )
    v3 = (unsigned __int16)v7 | 0x80070000;
  v5 = L"dwResult != 0 && dwResult <= (sizeof(*RtlpNumberOf(szTargetFile)))";
  v6 = 631;
LABEL_12:
  if ( v3 >= 0 )
    v3 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
    v6,
    L"PlatformUtils::SetNetworkCategoryHelper",
    L"CBRAEx",
    v5,
    v3);
  if ( IsDebuggerPresent() )
  {
    v13 = v3;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
      v6,
      L"PlatformUtils::SetNetworkCategoryHelper",
      L"CBRAEx",
      v5,
      v13);
  }
  else
  {
    v11 = v3;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
      v6,
      L"PlatformUtils::SetNetworkCategoryHelper",
      L"CBRAEx",
      v5,
      v11);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140074b88  mov     [rsp-8+arg_8], rbx
0x140074b8d  mov     [rsp-8+arg_10], rsi
0x140074b92  push    rbp
0x140074b93  push    rdi
0x140074b94  push    r12
0x140074b96  push    r14
0x140074b98  push    r15
0x140074b9a  lea     rbp, [rsp-580h]
0x140074ba2  sub     rsp, 680h
0x140074ba9  mov     rax, cs:__security_cookie
0x140074bb0  xor     rax, rsp
0x140074bb3  mov     [rbp+5A0h+var_30], rax
0x140074bba  mov     rsi, rcx
0x140074bbd  mov     ebx, 208h
0x140074bc2  mov     r8d, ebx; Size
0x140074bc5  lea     rcx, [rsp+6A0h+Src]; void *
0x140074bca  xor     edx, edx; Val
0x140074bcc  call    memset_0
0x140074bd1  mov     r8d, ebx; Size
0x140074bd4  lea     rcx, [rbp+5A0h+Dst]; void *
0x140074bdb  xor     edx, edx; Val
0x140074bdd  call    memset_0
0x140074be2  mov     r8d, ebx; Size
0x140074be5  lea     rcx, [rbp+5A0h+NewFileName]; void *
0x140074bec  xor     edx, edx; Val
0x140074bee  call    memset_0
0x140074bf3  lea     rcx, aPlatformutilsS_2; "PlatformUtils::SetNetworkCategoryHelper"...
0x140074bfa  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140074bff  mov     r14d, 104h
0x140074c05  xor     edi, edi
0x140074c07  lea     r12d, [r14-1]
0x140074c0b  mov     r9, cs:off_14009C6C8; "office"
0x140074c12  lea     r15, off_14009C6E0; "16.bin"
0x140074c19  mov     rax, [r15+rdi*8]
0x140074c1d  lea     r8, aWindirSystem32; "%%windir%%\\System32\\NetworkList\\Icon"...
0x140074c24  mov     rdx, r14; unsigned __int64
0x140074c27  mov     [rsp+6A0h+var_680], rax
0x140074c2c  lea     rcx, [rsp+6A0h+Src]; unsigned __int16 *
0x140074c31  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140074c36  mov     ebx, eax
0x140074c38  test    eax, eax
0x140074c3a  js      loc_140074DE4
0x140074c40  mov     r8d, r14d; nSize
0x140074c43  lea     rdx, [rbp+5A0h+Dst]; lpDst
0x140074c4a  lea     rcx, [rsp+6A0h+Src]; lpSrc
0x140074c4f  call    cs:__imp_ExpandEnvironmentStringsW
0x140074c55  dec     eax
0x140074c57  cmp     eax, r12d
0x140074c5a  ja      loc_140074DBD
0x140074c60  mov     rax, [r15+rdi*8]
0x140074c64  lea     r8, aWindirSystem32_0; "%%windir%%\\System32\\NetworkList\\Icon"...
0x140074c6b  mov     r9, rsi
0x140074c6e  mov     [rsp+6A0h+var_680], rax
0x140074c73  mov     rdx, r14; unsigned __int64
0x140074c76  lea     rcx, [rsp+6A0h+Src]; unsigned __int16 *
0x140074c7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140074c80  mov     ebx, eax
0x140074c82  test    eax, eax
0x140074c84  js      loc_140074DB5
0x140074c8a  mov     r8d, r14d; nSize
0x140074c8d  lea     rdx, [rbp+5A0h+NewFileName]; lpDst
0x140074c94  lea     rcx, [rsp+6A0h+Src]; lpSrc
0x140074c99  call    cs:__imp_ExpandEnvironmentStringsW
0x140074c9f  dec     eax
0x140074ca1  cmp     eax, r12d
0x140074ca4  ja      loc_140074D8E
0x140074caa  lea     r8, [rbp+5A0h+NewFileName]
0x140074cb1  lea     rdx, [rbp+5A0h+Dst]
0x140074cb8  lea     rcx, aPlatformutilsS_6; "PlatformUtils::SetNetworkCategoryHelper"...
0x140074cbf  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140074cc4  xor     r8d, r8d; bFailIfExists
0x140074cc7  lea     rdx, [rbp+5A0h+NewFileName]; lpNewFileName
0x140074cce  lea     rcx, [rbp+5A0h+Dst]; lpExistingFileName
0x140074cd5  call    cs:__imp_CopyFileW
0x140074cdb  test    eax, eax
0x140074cdd  jz      short loc_140074CFD
0x140074cdf  inc     rdi
0x140074ce2  cmp     rdi, 4
0x140074ce6  jb      loc_140074C0B
0x140074cec  lea     rcx, aPlatformutilsS; "PlatformUtils::SetNetworkCategoryHelper"...
0x140074cf3  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140074cf8  jmp     loc_140074E79
0x140074cfd  call    cs:__imp_GetLastError
0x140074d03  mov     ebx, eax
0x140074d05  test    eax, eax
0x140074d07  jle     short loc_140074D12
0x140074d09  movzx   ebx, ax
0x140074d0c  or      ebx, 80070000h
0x140074d12  lea     r12, aFsuccess; "fSuccess"
0x140074d19  mov     r15d, 27Bh
0x140074d1f  mov     eax, 80004005h
0x140074d24  lea     r14, aCbraex; "CBRAEx"
0x140074d2b  test    ebx, ebx
0x140074d2d  lea     rsi, aPlatformutilsS_3; "PlatformUtils::SetNetworkCategoryHelper"
0x140074d34  lea     rdi, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x140074d3b  mov     r9, r14; unsigned __int16 *
0x140074d3e  cmovns  ebx, eax
0x140074d41  mov     r8, rsi; unsigned __int16 *
0x140074d44  mov     [rsp+6A0h+var_678], ebx; int
0x140074d48  mov     edx, r15d; unsigned int
0x140074d4b  mov     rcx, rdi; unsigned __int16 *
0x140074d4e  mov     [rsp+6A0h+var_680], r12; unsigned __int16 *
0x140074d53  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140074d58  call    cs:__imp_IsDebuggerPresent
0x140074d5e  test    eax, eax
0x140074d60  jz      short loc_140074D78
0x140074d62  mov     [rsp+6A0h+var_668], ebx
0x140074d66  mov     r9d, r15d
0x140074d69  mov     [rsp+6A0h+var_670], r12
0x140074d6e  mov     qword ptr [rsp+6A0h+var_678], r14
0x140074d73  jmp     loc_140074E3B
0x140074d78  mov     dword ptr [rsp+6A0h+var_670], ebx
0x140074d7c  mov     r8d, r15d
0x140074d7f  mov     qword ptr [rsp+6A0h+var_678], r12
0x140074d84  mov     [rsp+6A0h+var_680], r14
0x140074d89  jmp     loc_140074E67
0x140074d8e  call    cs:__imp_GetLastError
0x140074d94  mov     ebx, eax
0x140074d96  test    eax, eax
0x140074d98  jle     short loc_140074DA3
0x140074d9a  movzx   ebx, ax
0x140074d9d  or      ebx, 80070000h
0x140074da3  lea     r12, aDwresult0Dwres; "dwResult != 0 && dwResult <= (sizeof(*R"...
0x140074daa  mov     r15d, 277h
0x140074db0  jmp     loc_140074D1F
0x140074db5  mov     r12d, 274h
0x140074dbb  jmp     short loc_140074DEA
0x140074dbd  call    cs:__imp_GetLastError
0x140074dc3  mov     ebx, eax
0x140074dc5  test    eax, eax
0x140074dc7  jle     short loc_140074DD2
0x140074dc9  movzx   ebx, ax
0x140074dcc  or      ebx, 80070000h
0x140074dd2  lea     r12, aDwresult0Dwres_0; "dwResult != 0 && dwResult <= (sizeof(*R"...
0x140074dd9  mov     r15d, 26Ch
0x140074ddf  jmp     loc_140074D1F
0x140074de4  mov     r12d, 269h
0x140074dea  lea     r15, aChra; "CHRA"
0x140074df1  mov     [rsp+6A0h+var_678], ebx; int
0x140074df5  lea     rsi, aPlatformutilsS_3; "PlatformUtils::SetNetworkCategoryHelper"
0x140074dfc  mov     r9, r15; unsigned __int16 *
0x140074dff  lea     rdi, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x140074e06  mov     r8, rsi; unsigned __int16 *
0x140074e09  lea     r14, aHr; "hr"
0x140074e10  mov     rcx, rdi; unsigned __int16 *
0x140074e13  mov     edx, r12d; unsigned int
0x140074e16  mov     [rsp+6A0h+var_680], r14; unsigned __int16 *
0x140074e1b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140074e20  call    cs:__imp_IsDebuggerPresent
0x140074e26  test    eax, eax
0x140074e28  jz      short loc_140074E56
0x140074e2a  mov     [rsp+6A0h+var_668], ebx
0x140074e2e  mov     r9d, r12d
0x140074e31  mov     [rsp+6A0h+var_670], r14
0x140074e36  mov     qword ptr [rsp+6A0h+var_678], r15
0x140074e3b  mov     r8, rdi
0x140074e3e  mov     [rsp+6A0h+var_680], rsi
0x140074e43  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140074e4a  mov     ecx, 2; unsigned __int8
0x140074e4f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140074e54  jmp     short loc_140074E79
0x140074e56  mov     dword ptr [rsp+6A0h+var_670], ebx
0x140074e5a  mov     r8d, r12d
0x140074e5d  mov     qword ptr [rsp+6A0h+var_678], r14
0x140074e62  mov     [rsp+6A0h+var_680], r15
0x140074e67  mov     r9, rsi
0x140074e6a  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140074e71  mov     rdx, rdi
0x140074e74  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140074e79  mov     eax, ebx
0x140074e7b  mov     rcx, [rbp+5A0h+var_30]
0x140074e82  xor     rcx, rsp; StackCookie
0x140074e85  call    __security_check_cookie
0x140074e8a  lea     r11, [rsp+6A0h+var_20]
0x140074e92  mov     rbx, [r11+38h]
0x140074e96  mov     rsi, [r11+40h]
0x140074e9a  mov     rsp, r11
0x140074e9d  pop     r15
0x140074e9f  pop     r14
0x140074ea1  pop     r12
0x140074ea3  pop     rdi
0x140074ea4  pop     rbp
0x140074ea5  retn
```
