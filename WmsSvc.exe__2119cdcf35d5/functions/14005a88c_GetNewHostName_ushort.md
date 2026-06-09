# GetNewHostName(ushort * *)

- ea: `0x14005a88c`
- end: `0x14005ae68`
- name: `?GetNewHostName@@YAJPEAPEAG@Z`
- size: `1500`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x140021050`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005a88c`
- `0x14005b304`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14005a9c0`
- `ADVAPI32!RegGetValueW` at `0x14005aad7`
- `ADVAPI32!RegGetValueW` at `0x14005ab0a`
- `ADVAPI32!RegGetValueW` at `0x14005ac0c`
- `ADVAPI32!RegGetValueW` at `0x14005a9c0`
- `ADVAPI32!RegGetValueW` at `0x14005aad7`
- `ADVAPI32!RegGetValueW` at `0x14005ab0a`
- `ADVAPI32!RegGetValueW` at `0x14005ac0c`
- `ADVAPI32!RegCloseKey` at `0x14005ae2c`
- `ADVAPI32!RegCloseKey` at `0x14005ae2c`
- `ADVAPI32!RegOpenKeyW` at `0x14005a8d8`
- `ADVAPI32!RegOpenKeyW` at `0x14005a8d8`
- `KERNEL32!IsDebuggerPresent` at `0x14005a92c`
- `KERNEL32!IsDebuggerPresent` at `0x14005aa43`
- `KERNEL32!IsDebuggerPresent` at `0x14005ab7b`
- `KERNEL32!IsDebuggerPresent` at `0x14005aca6`
- `KERNEL32!IsDebuggerPresent` at `0x14005adb5`
- `KERNEL32!IsDebuggerPresent` at `0x14005a92c`
- `KERNEL32!IsDebuggerPresent` at `0x14005aa43`
- `KERNEL32!IsDebuggerPresent` at `0x14005ab7b`
- `KERNEL32!IsDebuggerPresent` at `0x14005aca6`
- `KERNEL32!IsDebuggerPresent` at `0x14005adb5`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ad5a`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ad5a`

## string_xrefs

- `0x14005a904`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005aa26`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005ab5e`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005ac89`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005ad9a`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005a8bc`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 __fastcall GetNewHostName(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rdi
  void *v3; // rsi
  unsigned __int16 *v4; // r13
  LSTATUS v5; // eax
  signed int v6; // ebx
  LSTATUS ValueW; // eax
  bool v8; // cc
  bool v9; // zf
  const unsigned __int16 *v10; // rax
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rax
  unsigned int pvData; // [rsp+28h] [rbp-38h]
  unsigned int pvDataa; // [rsp+28h] [rbp-38h]
  unsigned int pvDatab; // [rsp+28h] [rbp-38h]
  LPDWORD pcbData; // [rsp+30h] [rbp-30h]
  LPDWORD pcbDataa; // [rsp+30h] [rbp-30h]
  void *v23; // [rsp+40h] [rbp-20h]
  HKEY phkResult; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v25; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp-8h] BYREF
  DWORD v27; // [rsp+A8h] [rbp+48h] BYREF
  DWORD v28; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v29; // [rsp+B8h] [rbp+58h]

  phkResult = 0;
  v28 = 0;
  v27 = 0;
  v2 = 0;
  v26 = 0;
  v3 = 0;
  v25 = 0;
  v4 = 0;
  v5 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters", &phkResult);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x2B7u,
      L"GetNewHostName",
      L"CBRAEx",
      L"err == 0L",
      v6);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        695,
        L"GetNewHostName",
        L"CBRAEx",
        L"err == 0L",
        v6);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        695,
        L"GetNewHostName",
        L"CBRAEx",
        L"err == 0L",
        v6);
    v2 = 0;
    v3 = 0;
    goto LABEL_46;
  }
  ValueW = RegGetValueW(phkResult, 0, L"NV HostName", 2u, 0, 0, &v28);
  v6 = ValueW;
  if ( ValueW && ValueW != 234 )
    goto LABEL_10;
  v29 = (unsigned __int16 *)operator new(v28);
  v2 = v29;
  if ( !v29 )
  {
    v6 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x2BDu,
      L"GetNewHostName",
      L"CPR",
      L"pszHostName",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        701,
        L"GetNewHostName",
        L"CPR",
        L"pszHostName",
        -2147024882);
    }
    else
    {
      LODWORD(pcbData) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        701,
        L"GetNewHostName",
        L"CPR",
        L"pszHostName",
        pcbData);
    }
    v3 = 0;
    goto LABEL_45;
  }
  ValueW = RegGetValueW(phkResult, 0, L"NV HostName", 2u, 0, v29, &v28);
  v6 = ValueW;
  v8 = ValueW <= 0;
  if ( !ValueW )
  {
    ValueW = RegGetValueW(phkResult, 0, L"NV Domain", 2u, 0, 0, &v27);
    v6 = ValueW;
    if ( ValueW && ValueW != 234 )
    {
LABEL_10:
      v8 = ValueW <= 0;
      goto LABEL_11;
    }
    v23 = operator new(v27);
    v3 = v23;
    if ( !v23 )
    {
      v6 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        0x2C6u,
        L"GetNewHostName",
        L"CPR",
        L"pszDomain",
        -2147024882);
      v9 = !IsDebuggerPresent();
      v10 = L"pszDomain";
      if ( !v9 )
      {
        v11 = 710;
LABEL_24:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
          v11,
          L"GetNewHostName",
          L"CPR",
          v10,
          -2147024882);
LABEL_44:
        v3 = v23;
LABEL_45:
        v2 = v29;
        goto LABEL_46;
      }
      v12 = 710;
      goto LABEL_26;
    }
    ValueW = RegGetValueW(phkResult, 0, L"NV Domain", 2u, 0, v23, &v27);
    v6 = ValueW;
    v8 = ValueW <= 0;
    if ( !ValueW )
    {
      v6 = 0;
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)v23 + v13) );
      if ( v13 )
      {
        v14 = (unsigned int)((v27 + 2LL + (unsigned __int64)v28) >> 1);
        v15 = (unsigned __int16 *)operator new(saturated_mul(v14, 2u));
        v4 = v15;
        if ( !v15 )
        {
          v6 = -2147024882;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
            0x2D0u,
            L"GetNewHostName",
            L"CPR",
            L"pszHostNameFull",
            -2147024882);
          v9 = !IsDebuggerPresent();
          v10 = L"pszHostNameFull";
          if ( !v9 )
          {
            v11 = 720;
            goto LABEL_24;
          }
          v12 = 720;
LABEL_26:
          LODWORD(pcbDataa) = -2147024882;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
            v12,
            L"GetNewHostName",
            L"CPR",
            v10,
            pcbDataa);
          goto LABEL_44;
        }
        *v15 = 0;
        v6 = StringCchCatExW(v15, v14, v2, &v26, &v25, pvData);
        if ( v6 < 0 )
          goto LABEL_46;
        v6 = StringCchCatExW(v26, v25, L".", &v26, &v25, pvDataa);
        if ( v6 < 0 )
          goto LABEL_46;
        v6 = StringCchCatExW(v26, v25, (const unsigned __int16 *)v23, &v26, &v25, pvDatab);
        if ( v6 < 0 )
          goto LABEL_46;
        operator delete(v2);
        v2 = v4;
        v29 = v4;
      }
      v16 = SysAllocString(v2);
      *a1 = v16;
      v4 = 0;
      if ( v16 )
        goto LABEL_46;
      v6 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        0x2E3u,
        L"GetNewHostName",
        L"CPR",
        L"*pbstrHostNameNew",
        -2147024882);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
          739,
          L"GetNewHostName",
          L"CPR",
          L"*pbstrHostNameNew",
          -2147024882);
      }
      else
      {
        LODWORD(pcbDataa) = -2147024882;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
          739,
          L"GetNewHostName",
          L"CPR",
          L"*pbstrHostNameNew",
          pcbDataa);
      }
      v4 = 0;
      goto LABEL_44;
    }
  }
LABEL_11:
  if ( !v8 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
LABEL_46:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  operator delete(v2);
  operator delete(v3);
  operator delete(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14005a88c  mov     [rsp-38h+arg_0], rbx
0x14005a891  push    rbp
0x14005a892  push    rsi
0x14005a893  push    rdi
0x14005a894  push    r12
0x14005a896  push    r13
0x14005a898  push    r14
0x14005a89a  push    r15
0x14005a89c  mov     rbp, rsp
0x14005a89f  sub     rsp, 60h
0x14005a8a3  xor     r15d, r15d
0x14005a8a6  lea     r8, [rbp+phkResult]; phkResult
0x14005a8aa  mov     r14, rcx
0x14005a8ad  mov     [rbp+phkResult], r15
0x14005a8b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005a8b8  mov     [rbp+arg_10], r15d
0x14005a8bc  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x14005a8c3  mov     [rbp+arg_8], r15d
0x14005a8c7  mov     edi, r15d
0x14005a8ca  mov     [rbp+var_8], r15
0x14005a8ce  mov     esi, r15d
0x14005a8d1  mov     [rbp+var_10], r15
0x14005a8d5  mov     r13d, r15d
0x14005a8d8  call    cs:__imp_RegOpenKeyW
0x14005a8de  mov     ebx, eax
0x14005a8e0  test    eax, eax
0x14005a8e2  jz      loc_14005A997
0x14005a8e8  jle     short loc_14005A8F3
0x14005a8ea  movzx   ebx, ax
0x14005a8ed  or      ebx, 80070000h
0x14005a8f3  lea     rsi, aGetnewhostname; "GetNewHostName"
0x14005a8fa  mov     dword ptr [rsp+60h+pvData], ebx; int
0x14005a8fe  mov     r14d, 2B7h
0x14005a904  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005a90b  lea     r12, aErr0l; "err == 0L"
0x14005a912  mov     r8, rsi; unsigned __int16 *
0x14005a915  mov     edx, r14d; unsigned int
0x14005a918  mov     [rsp+60h+pdwType], r12; unsigned __int16 *
0x14005a91d  mov     rcx, rdi; unsigned __int16 *
0x14005a920  lea     r9, aCbraex; "CBRAEx"
0x14005a927  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005a92c  call    cs:__imp_IsDebuggerPresent
0x14005a932  test    eax, eax
0x14005a934  lea     rax, aCbraex; "CBRAEx"
0x14005a93b  jz      short loc_14005A969
0x14005a93d  mov     [rsp+60h+var_28], ebx
0x14005a941  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005a948  mov     [rsp+60h+pcbData], r12
0x14005a94d  mov     r9d, r14d
0x14005a950  mov     [rsp+60h+pvData], rax
0x14005a955  mov     r8, rdi
0x14005a958  mov     ecx, 2; unsigned __int8
0x14005a95d  mov     [rsp+60h+pdwType], rsi
0x14005a962  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005a967  jmp     short loc_14005A98C
0x14005a969  mov     dword ptr [rsp+60h+pcbData], ebx
0x14005a96d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005a974  mov     [rsp+60h+pvData], r12
0x14005a979  mov     r9, rsi
0x14005a97c  mov     r8d, r14d
0x14005a97f  mov     [rsp+60h+pdwType], rax
0x14005a984  mov     rdx, rdi
0x14005a987  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005a98c  mov     rdi, r13
0x14005a98f  mov     rsi, r13
0x14005a992  jmp     loc_14005AE23
0x14005a997  mov     rcx, [rbp+phkResult]; hkey
0x14005a99b  lea     rax, [rbp+arg_10]
0x14005a99f  mov     [rsp+60h+pcbData], rax; pcbData
0x14005a9a4  lea     r8, aNvHostname; "NV HostName"
0x14005a9ab  mov     r12d, 2
0x14005a9b1  mov     [rsp+60h+pvData], r15; pvData
0x14005a9b6  mov     r9d, r12d; dwFlags
0x14005a9b9  mov     [rsp+60h+pdwType], r15; pdwType
0x14005a9be  xor     edx, edx; lpSubKey
0x14005a9c0  call    cs:__imp_RegGetValueW
0x14005a9c6  mov     ebx, eax
0x14005a9c8  test    eax, eax
0x14005a9ca  jz      short loc_14005A9E9
0x14005a9cc  cmp     eax, 0EAh
0x14005a9d1  jz      short loc_14005A9E9
0x14005a9d3  test    eax, eax
0x14005a9d5  jle     loc_14005AE23
0x14005a9db  movzx   ebx, ax
0x14005a9de  or      ebx, 80070000h
0x14005a9e4  jmp     loc_14005AE23
0x14005a9e9  mov     ecx, [rbp+arg_10]; Size
0x14005a9ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005a9f1  mov     [rbp+arg_18], rax
0x14005a9f5  mov     rdi, rax
0x14005a9f8  test    rax, rax
0x14005a9fb  jnz     loc_14005AAB4
0x14005aa01  mov     r14d, 8007000Eh
0x14005aa07  lea     rax, aPszhostname; "pszHostName"
0x14005aa0e  lea     r15, aCpr; "CPR"
0x14005aa15  mov     dword ptr [rsp+60h+pvData], r14d; int
0x14005aa1a  lea     rsi, aGetnewhostname; "GetNewHostName"
0x14005aa21  mov     [rsp+60h+pdwType], rax; unsigned __int16 *
0x14005aa26  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005aa2d  mov     r9, r15; unsigned __int16 *
0x14005aa30  mov     r8, rsi; unsigned __int16 *
0x14005aa33  mov     rcx, rdi; unsigned __int16 *
0x14005aa36  mov     edx, 2BDh; unsigned int
0x14005aa3b  mov     ebx, r14d
0x14005aa3e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005aa43  call    cs:__imp_IsDebuggerPresent
0x14005aa49  test    eax, eax
0x14005aa4b  lea     rax, aPszhostname; "pszHostName"
0x14005aa52  jz      short loc_14005AA8B
0x14005aa54  mov     [rsp+60h+var_28], r14d
0x14005aa59  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005aa60  mov     [rsp+60h+pcbData], rax
0x14005aa65  mov     r9d, 2BDh
0x14005aa6b  mov     [rsp+60h+pvData], r15
0x14005aa70  mov     r8, rdi
0x14005aa73  mov     ecx, r12d; unsigned __int8
0x14005aa76  mov     [rsp+60h+pdwType], rsi
0x14005aa7b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005aa80  mov     rsi, r13
0x14005aa83  xor     r15d, r15d
0x14005aa86  jmp     loc_14005AE1F
0x14005aa8b  mov     dword ptr [rsp+60h+pcbData], r14d
0x14005aa90  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005aa97  mov     [rsp+60h+pvData], rax
0x14005aa9c  mov     r9, rsi
0x14005aa9f  mov     r8d, 2BDh
0x14005aaa5  mov     [rsp+60h+pdwType], r15
0x14005aaaa  mov     rdx, rdi
0x14005aaad  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005aab2  jmp     short loc_14005AA80
0x14005aab4  mov     rcx, [rbp+phkResult]; hkey
0x14005aab8  lea     rax, [rbp+arg_10]
0x14005aabc  mov     [rsp+60h+pcbData], rax; pcbData
0x14005aac1  lea     r8, aNvHostname; "NV HostName"
0x14005aac8  mov     [rsp+60h+pvData], rdi; pvData
0x14005aacd  mov     r9d, r12d; dwFlags
0x14005aad0  xor     edx, edx; lpSubKey
0x14005aad2  mov     [rsp+60h+pdwType], r15; pdwType
0x14005aad7  call    cs:__imp_RegGetValueW
0x14005aadd  mov     ebx, eax
0x14005aadf  test    eax, eax
0x14005aae1  jnz     loc_14005A9D5
0x14005aae7  mov     rcx, [rbp+phkResult]; hkey
0x14005aaeb  lea     rax, [rbp+arg_8]
0x14005aaef  mov     [rsp+60h+pcbData], rax; pcbData
0x14005aaf4  lea     r8, aNvDomain; "NV Domain"
0x14005aafb  mov     [rsp+60h+pvData], r15; pvData
0x14005ab00  mov     r9d, r12d; dwFlags
0x14005ab03  xor     edx, edx; lpSubKey
0x14005ab05  mov     [rsp+60h+pdwType], r15; pdwType
0x14005ab0a  call    cs:__imp_RegGetValueW
0x14005ab10  mov     ebx, eax
0x14005ab12  test    eax, eax
0x14005ab14  jz      short loc_14005AB21
0x14005ab16  cmp     eax, 0EAh
0x14005ab1b  jnz     loc_14005A9D3
0x14005ab21  mov     ecx, [rbp+arg_8]; Size
0x14005ab24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005ab29  mov     [rbp+var_20], rax
0x14005ab2d  mov     rsi, rax
0x14005ab30  test    rax, rax
0x14005ab33  jnz     loc_14005ABE9
0x14005ab39  mov     r14d, 8007000Eh
0x14005ab3f  lea     rax, aPszdomain; "pszDomain"
0x14005ab46  lea     r15, aCpr; "CPR"
0x14005ab4d  mov     dword ptr [rsp+60h+pvData], r14d; int
0x14005ab52  lea     rsi, aGetnewhostname; "GetNewHostName"
0x14005ab59  mov     [rsp+60h+pdwType], rax; unsigned __int16 *
0x14005ab5e  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005ab65  mov     r9, r15; unsigned __int16 *
0x14005ab68  mov     r8, rsi; unsigned __int16 *
0x14005ab6b  mov     rcx, rdi; unsigned __int16 *
0x14005ab6e  mov     edx, 2C6h; unsigned int
0x14005ab73  mov     ebx, r14d
0x14005ab76  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005ab7b  call    cs:__imp_IsDebuggerPresent
0x14005ab81  test    eax, eax
0x14005ab83  lea     rax, aPszdomain; "pszDomain"
0x14005ab8a  jz      short loc_14005ABC0
0x14005ab8c  mov     r9d, 2C6h
0x14005ab92  mov     [rsp+60h+var_28], r14d
0x14005ab97  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005ab9e  mov     [rsp+60h+pcbData], rax
0x14005aba3  mov     r8, rdi
0x14005aba6  mov     [rsp+60h+pvData], r15
0x14005abab  mov     ecx, r12d; unsigned __int8
0x14005abae  mov     [rsp+60h+pdwType], rsi
0x14005abb3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005abb8  xor     r15d, r15d
0x14005abbb  jmp     loc_14005AE1B
0x14005abc0  mov     r8d, 2C6h
0x14005abc6  mov     dword ptr [rsp+60h+pcbData], r14d
0x14005abcb  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005abd2  mov     [rsp+60h+pvData], rax
0x14005abd7  mov     r9, rsi
0x14005abda  mov     rdx, rdi
0x14005abdd  mov     [rsp+60h+pdwType], r15
0x14005abe2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005abe7  jmp     short loc_14005ABB8
0x14005abe9  mov     rcx, [rbp+phkResult]; hkey
0x14005abed  lea     rax, [rbp+arg_8]
0x14005abf1  mov     [rsp+60h+pcbData], rax; pcbData
0x14005abf6  lea     r8, aNvDomain; "NV Domain"
0x14005abfd  mov     [rsp+60h+pvData], rsi; unsigned int
0x14005ac02  mov     r9d, r12d; dwFlags
0x14005ac05  xor     edx, edx; lpSubKey
0x14005ac07  mov     [rsp+60h+pdwType], r15; pdwType
0x14005ac0c  call    cs:__imp_RegGetValueW
0x14005ac12  mov     ebx, eax
0x14005ac14  test    eax, eax
0x14005ac16  jnz     loc_14005A9D5
0x14005ac1c  or      r8, 0FFFFFFFFFFFFFFFFh
0x14005ac20  mov     ebx, r15d
0x14005ac23  mov     rax, r8
0x14005ac26  inc     rax
0x14005ac29  cmp     [rsi+rax*2], r15w
0x14005ac2e  jnz     short loc_14005AC26
0x14005ac30  test    rax, rax
0x14005ac33  jz      loc_14005AD57
0x14005ac39  mov     ecx, [rbp+arg_8]
0x14005ac3c  mov     rax, r12
0x14005ac3f  mov     ebx, [rbp+arg_10]
0x14005ac42  add     rcx, r12
0x14005ac45  add     rbx, rcx
0x14005ac48  shr     rbx, 1
0x14005ac4b  mov     ebx, ebx
0x14005ac4d  mul     rbx
0x14005ac50  cmovb   rax, r8
0x14005ac54  mov     rcx, rax; Size
0x14005ac57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005ac5c  mov     r13, rax
0x14005ac5f  test    rax, rax
0x14005ac62  jnz     short loc_14005ACCD
0x14005ac64  mov     r14d, 8007000Eh
0x14005ac6a  lea     rax, aPszhostnameful; "pszHostNameFull"
0x14005ac71  lea     r15, aCpr; "CPR"
0x14005ac78  mov     dword ptr [rsp+60h+pvData], r14d; int
0x14005ac7d  lea     rsi, aGetnewhostname; "GetNewHostName"
0x14005ac84  mov     [rsp+60h+pdwType], rax; unsigned __int16 *
0x14005ac89  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005ac90  mov     r9, r15; unsigned __int16 *
0x14005ac93  mov     r8, rsi; unsigned __int16 *
0x14005ac96  mov     rcx, rdi; unsigned __int16 *
0x14005ac99  mov     edx, 2D0h; unsigned int
0x14005ac9e  mov     ebx, r14d
0x14005aca1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005aca6  call    cs:__imp_IsDebuggerPresent
0x14005acac  test    eax, eax
0x14005acae  lea     rax, aPszhostnameful; "pszHostNameFull"
0x14005acb5  jz      short loc_14005ACC2
0x14005acb7  mov     r9d, 2D0h
0x14005acbd  jmp     loc_14005AB92
0x14005acc2  mov     r8d, 2D0h
0x14005acc8  jmp     loc_14005ABC6
0x14005accd  mov     [rax], r15w
0x14005acd1  lea     r9, [rbp+var_8]; unsigned __int16 **
0x14005acd5  lea     rax, [rbp+var_10]
0x14005acd9  mov     r8, rdi; unsigned __int16 *
0x14005acdc  mov     rdx, rbx; unsigned __int64
0x14005acdf  mov     [rsp+60h+pdwType], rax; unsigned __int64 *
0x14005ace4  mov     rcx, r13; unsigned __int16 *
0x14005ace7  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x14005acec  mov     ebx, eax
0x14005acee  test    eax, eax
0x14005acf0  js      loc_14005AE23
0x14005acf6  mov     rdx, [rbp+var_10]; unsigned __int64
0x14005acfa  lea     rax, [rbp+var_10]
0x14005acfe  mov     rcx, [rbp+var_8]; unsigned __int16 *
0x14005ad02  lea     r9, [rbp+var_8]; unsigned __int16 **
0x14005ad06  lea     r8, asc_1400D2EBC; "."
0x14005ad0d  mov     [rsp+60h+pdwType], rax; unsigned __int64 *
0x14005ad12  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x14005ad17  mov     ebx, eax
0x14005ad19  test    eax, eax
0x14005ad1b  js      loc_14005AE23
0x14005ad21  mov     rdx, [rbp+var_10]; unsigned __int64
0x14005ad25  lea     rax, [rbp+var_10]
0x14005ad29  mov     rcx, [rbp+var_8]; unsigned __int16 *
0x14005ad2d  lea     r9, [rbp+var_8]; unsigned __int16 **
0x14005ad31  mov     r8, rsi; unsigned __int16 *
0x14005ad34  mov     [rsp+60h+pdwType], rax; unsigned __int64 *
0x14005ad39  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x14005ad3e  mov     ebx, eax
0x14005ad40  test    eax, eax
0x14005ad42  js      loc_14005AE23
0x14005ad48  mov     rcx, rdi; Block
0x14005ad4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005ad50  mov     rdi, r13
0x14005ad53  mov     [rbp+arg_18], r13
0x14005ad57  mov     rcx, rdi; psz
0x14005ad5a  call    cs:__imp_SysAllocString
0x14005ad60  mov     [r14], rax
0x14005ad63  mov     r13, r15
0x14005ad66  test    rax, rax
0x14005ad69  jnz     loc_14005AE23
0x14005ad6f  mov     r14d, 8007000Eh
0x14005ad75  lea     rax, aPbstrhostnamen; "*pbstrHostNameNew"
0x14005ad7c  lea     r15, aCpr; "CPR"
0x14005ad83  mov     dword ptr [rsp+60h+pvData], r14d; int
0x14005ad88  lea     rsi, aGetnewhostname; "GetNewHostName"
  ... truncated ...
```
