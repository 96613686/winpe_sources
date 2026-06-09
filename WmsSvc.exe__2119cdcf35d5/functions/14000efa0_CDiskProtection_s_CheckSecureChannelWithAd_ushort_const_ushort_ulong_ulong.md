# CDiskProtection::s_CheckSecureChannelWithAd(ushort const *,ushort *,ulong,ulong)

- ea: `0x14000efa0`
- end: `0x14000f65e`
- name: `?s_CheckSecureChannelWithAd@CDiskProtection@@KAJPEBGPEAGKK@Z`
- size: `1726`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x14000e89c`

## callees

- `0x140005518`
- `0x14000efa0`
- `0x140013dec`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x14000efda`
- `ADVAPI32!OpenSCManagerW` at `0x14000efda`
- `ADVAPI32!OpenServiceW` at `0x14000f0bb`
- `ADVAPI32!OpenServiceW` at `0x14000f0bb`
- `ADVAPI32!QueryServiceStatus` at `0x14000f1ea`
- `ADVAPI32!QueryServiceStatus` at `0x14000f1ea`
- `ADVAPI32!CloseServiceHandle` at `0x14000f613`
- `ADVAPI32!CloseServiceHandle` at `0x14000f61d`
- `ADVAPI32!CloseServiceHandle` at `0x14000f613`
- `ADVAPI32!CloseServiceHandle` at `0x14000f61d`
- `KERNEL32!Sleep` at `0x14000f1d9`
- `KERNEL32!Sleep` at `0x14000f1d9`
- `KERNEL32!GetLastError` at `0x14000efed`
- `KERNEL32!GetLastError` at `0x14000f0ce`
- `KERNEL32!GetLastError` at `0x14000f56e`
- `KERNEL32!GetLastError` at `0x14000efed`
- `KERNEL32!GetLastError` at `0x14000f0ce`
- `KERNEL32!GetLastError` at `0x14000f56e`
- `KERNEL32!IsDebuggerPresent` at `0x14000f046`
- `KERNEL32!IsDebuggerPresent` at `0x14000f127`
- `KERNEL32!IsDebuggerPresent` at `0x14000f29e`
- `KERNEL32!IsDebuggerPresent` at `0x14000f3ed`
- `KERNEL32!IsDebuggerPresent` at `0x14000f459`
- `KERNEL32!IsDebuggerPresent` at `0x14000f4c7`
- `KERNEL32!IsDebuggerPresent` at `0x14000f52b`
- `KERNEL32!IsDebuggerPresent` at `0x14000f5b5`
- `KERNEL32!IsDebuggerPresent` at `0x14000f046`
- `KERNEL32!IsDebuggerPresent` at `0x14000f127`
- `KERNEL32!IsDebuggerPresent` at `0x14000f29e`
- `KERNEL32!IsDebuggerPresent` at `0x14000f3ed`
- `KERNEL32!IsDebuggerPresent` at `0x14000f459`
- `KERNEL32!IsDebuggerPresent` at `0x14000f4c7`
- `KERNEL32!IsDebuggerPresent` at `0x14000f52b`
- `KERNEL32!IsDebuggerPresent` at `0x14000f5b5`
- `NETAPI32!I_NetLogonControl2` at `0x14000f247`
- `NETAPI32!I_NetLogonControl2` at `0x14000f247`
- `NETAPI32!NetApiBufferFree` at `0x14000f204`
- `NETAPI32!NetApiBufferFree` at `0x14000f352`
- `NETAPI32!NetApiBufferFree` at `0x14000f62f`
- `NETAPI32!NetApiBufferFree` at `0x14000f204`
- `NETAPI32!NetApiBufferFree` at `0x14000f352`
- `NETAPI32!NetApiBufferFree` at `0x14000f62f`

## string_xrefs

- `0x14000f105`: `hService != 0`
- `0x14000f1c8`: `CDiskProtection::s_CheckSecureChannelWithAd - Wait before attempting retry.\n`
- `0x14000f401`: `nlInfo2->netlog2_pdc_connection_status is set to access denied`
- `0x14000f4ab`: `hrTemp`
- `0x14000f4cf`: `hrTemp`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_CheckSecureChannelWithAd(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  SC_HANDLE v2; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  SC_HANDLE v5; // rax
  signed int v6; // eax
  signed int v7; // esi
  const unsigned __int16 *v8; // r15
  signed int v9; // eax
  LPBYTE v10; // rcx
  __int64 v11; // r8
  int v12; // eax
  unsigned int v13; // esi
  bool v14; // zf
  const unsigned __int16 *v15; // rax
  signed int v16; // eax
  const unsigned __int16 *v18; // [rsp+28h] [rbp-61h]
  __int64 v19; // [rsp+30h] [rbp-59h]
  const unsigned __int16 *v20; // [rsp+30h] [rbp-59h]
  __int64 v21; // [rsp+38h] [rbp-51h]
  LPBYTE v22; // [rsp+40h] [rbp-49h] BYREF
  int v23; // [rsp+48h] [rbp-41h]
  LPVOID Buffer; // [rsp+50h] [rbp-39h]
  SC_HANDLE hSCObject; // [rsp+58h] [rbp-31h]
  const unsigned __int16 *v26; // [rsp+60h] [rbp-29h]
  BYTE Data[8]; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int16 *v28; // [rsp+70h] [rbp-19h]
  SC_HANDLE v29; // [rsp+78h] [rbp-11h]
  _SERVICE_STATUS ServiceStatus; // [rsp+80h] [rbp-9h] BYREF

  v28 = a2;
  v26 = a1;
  v2 = OpenSCManagerW(0, 0, 1u);
  v29 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x142Du,
      L"CDiskProtection::s_CheckSecureChannelWithAd",
      L"CBRAEx",
      L"hScManager != 0",
      v4);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        5165,
        L"CDiskProtection::s_CheckSecureChannelWithAd",
        L"CBRAEx",
        L"hScManager != 0",
        v4);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        5165,
        L"CDiskProtection::s_CheckSecureChannelWithAd",
        L"CBRAEx",
        L"hScManager != 0",
        v4);
    return (unsigned int)v4;
  }
  Buffer = 0;
  v5 = OpenServiceW(v2, L"netlogon", 4u);
  hSCObject = v5;
  if ( !v5 )
  {
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x1432u,
      L"CDiskProtection::s_CheckSecureChannelWithAd",
      L"CBRAEx",
      L"hService != 0",
      v4);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        5170,
        L"CDiskProtection::s_CheckSecureChannelWithAd",
        L"CBRAEx",
        L"hService != 0",
        v4);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        5170,
        L"CDiskProtection::s_CheckSecureChannelWithAd",
        L"CBRAEx",
        L"hService != 0",
        v4);
    goto LABEL_73;
  }
  v7 = 0;
  v23 = 30;
  v8 = L"CBRAEx";
  v4 = -2147023107;
  while ( 1 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( v7 < 0 )
    {
      CDiskProtection::s_RefreshDhcpIpAddress();
      DEBUGMSG(L"CDiskProtection::s_CheckSecureChannelWithAd - Wait before attempting retry.\n");
      Sleep(0x1388u);
      v5 = hSCObject;
    }
    if ( !QueryServiceStatus(v5, &ServiceStatus) )
    {
      v16 = GetLastError();
      v4 = v16;
      if ( v16 > 0 )
        v4 = (unsigned __int16)v16 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      v13 = 5196;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x144Cu,
        L"CDiskProtection::s_CheckSecureChannelWithAd",
        L"CBRAEx",
        L"fSuccess",
        v4);
      v14 = !IsDebuggerPresent();
      v15 = L"fSuccess";
LABEL_67:
      if ( v14 )
      {
        LODWORD(v19) = v4;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v13,
          L"CDiskProtection::s_CheckSecureChannelWithAd",
          v8,
          v15,
          v19);
        goto LABEL_72;
      }
      LODWORD(v21) = v4;
      v20 = v15;
      v18 = v8;
LABEL_69:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v13,
        L"CDiskProtection::s_CheckSecureChannelWithAd",
        v18,
        v20,
        v21,
        v22);
      goto LABEL_72;
    }
    if ( Buffer )
    {
      NetApiBufferFree(Buffer);
      Buffer = 0;
    }
    *(_QWORD *)Data = v26;
    v22 = 0;
    if ( ServiceStatus.dwCurrentState != 4 )
    {
      v7 = -2147023104;
      goto LABEL_49;
    }
    v9 = I_NetLogonControl2(0, 0xAu, 2u, Data, &v22);
    v7 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      goto LABEL_28;
    }
    v10 = v22;
    if ( !v22 )
    {
      v7 = -2147418113;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x1408u,
        L"CDiskProtection::s_VerifyTrustedDomainSecureChannel",
        L"CBRAEx",
        L"pNetlogonInfo != 0",
        -2147418113);
      if ( IsDebuggerPresent() )
      {
        LODWORD(v21) = -2147418113;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          5128,
          L"CDiskProtection::s_VerifyTrustedDomainSecureChannel",
          L"CBRAEx",
          L"pNetlogonInfo != 0",
          v21);
      }
      else
      {
        LODWORD(v19) = -2147418113;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          5128,
          L"CDiskProtection::s_VerifyTrustedDomainSecureChannel",
          L"CBRAEx",
          L"pNetlogonInfo != 0",
          v19);
      }
LABEL_28:
      v10 = v22;
      goto LABEL_43;
    }
    if ( (*v22 & 0x80u) != 0 )
    {
      v7 = *((_DWORD *)v22 + 1);
      if ( v7 == 5 )
      {
        v7 = 0;
      }
      else if ( v7 )
      {
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
      }
      else if ( *((_QWORD *)v22 + 1) )
      {
        v7 = 0;
        Buffer = v22;
        v10 = 0;
        v22 = 0;
      }
      else
      {
        v7 = -2147023107;
      }
    }
    else
    {
      v7 = -2147023288;
    }
LABEL_43:
    if ( v10 )
      NetApiBufferFree(v10);
    if ( v7 >= 0 )
      break;
LABEL_49:
    if ( !--v23 )
    {
      v4 = v7;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x147Bu,
        L"CDiskProtection::s_CheckSecureChannelWithAd",
        L"CHRA",
        L"hrTemp",
        v7);
      if ( IsDebuggerPresent() )
      {
        LODWORD(v21) = v7;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          5243,
          L"CDiskProtection::s_CheckSecureChannelWithAd",
          L"CHRA",
          L"hrTemp",
          v21,
          v22);
      }
      else
      {
        LODWORD(v19) = v7;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          5243,
          L"CDiskProtection::s_CheckSecureChannelWithAd",
          L"CHRA",
          L"hrTemp",
          v19);
      }
      goto LABEL_72;
    }
    v5 = hSCObject;
  }
  if ( *((_DWORD *)Buffer + 1) == 5 )
  {
    v13 = 5210;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      5210,
      L"CDiskProtection::s_CheckSecureChannelWithAd",
      L"nlInfo2->netlog2_pdc_connection_status is set to access denied");
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x145Au,
      L"CDiskProtection::s_CheckSecureChannelWithAd",
      L"CBRLAEx",
      L"pNetlogonInfo->netlog2_pdc_connection_status != 5L",
      -2147023107);
    if ( !IsDebuggerPresent() )
    {
      LODWORD(v19) = -2147023107;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        5210,
        L"CDiskProtection::s_CheckSecureChannelWithAd",
        L"CBRLAEx",
        L"pNetlogonInfo->netlog2_pdc_connection_status != 5L",
        v19);
      goto LABEL_72;
    }
    LODWORD(v21) = -2147023107;
    v20 = L"pNetlogonInfo->netlog2_pdc_connection_status != 5L";
    v18 = L"CBRLAEx";
    goto LABEL_69;
  }
  if ( *((_DWORD *)Buffer + 4) )
  {
    v7 = -2147023108;
    goto LABEL_49;
  }
  v11 = *((_QWORD *)Buffer + 1);
  if ( *(_WORD *)v11 == 92 && *(_WORD *)(v11 + 2) == 92 )
    v11 += 4;
  v12 = StringCchCopyW(v28, 0x104u, (const unsigned __int16 *)v11);
  v4 = v12;
  if ( v12 < 0 )
  {
    v8 = L"CHRA";
    v13 = 5231;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x146Fu,
      L"CDiskProtection::s_CheckSecureChannelWithAd",
      L"CHRA",
      L"hr",
      v12);
    v14 = !IsDebuggerPresent();
    v15 = L"hr";
    goto LABEL_67;
  }
LABEL_72:
  CloseServiceHandle(hSCObject);
LABEL_73:
  CloseServiceHandle(v29);
  if ( Buffer )
    NetApiBufferFree(Buffer);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000efa0  mov     [rsp-8+arg_10], rbx
0x14000efa5  push    rbp
0x14000efa6  push    rsi
0x14000efa7  push    rdi
0x14000efa8  push    r12
0x14000efaa  push    r13
0x14000efac  push    r14
0x14000efae  push    r15
0x14000efb0  lea     rbp, [rsp-27h]
0x14000efb5  sub     rsp, 0B0h
0x14000efbc  mov     rax, cs:__security_cookie
0x14000efc3  xor     rax, rsp
0x14000efc6  mov     [rbp+57h+var_40], rax
0x14000efca  mov     [rbp+57h+var_70], rdx
0x14000efce  xor     edx, edx; lpDatabaseName
0x14000efd0  mov     [rbp+57h+var_80], rcx
0x14000efd4  xor     ecx, ecx; lpMachineName
0x14000efd6  lea     r8d, [rdx+1]; dwDesiredAccess
0x14000efda  call    cs:__imp_OpenSCManagerW
0x14000efe0  mov     [rbp+57h+var_68], rax
0x14000efe4  test    rax, rax
0x14000efe7  jnz     loc_14000F0A7
0x14000efed  call    cs:__imp_GetLastError
0x14000eff3  mov     ebx, eax
0x14000eff5  test    eax, eax
0x14000eff7  jle     short loc_14000F002
0x14000eff9  movzx   ebx, ax
0x14000effc  or      ebx, 80070000h
0x14000f002  mov     esi, 80004005h
0x14000f007  lea     r15, aCbraex; "CBRAEx"
0x14000f00e  test    ebx, ebx
0x14000f010  lea     rdi, aCdiskprotectio_19; "CDiskProtection::s_CheckSecureChannelWi"...
0x14000f017  lea     r14, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000f01e  mov     r9, r15; unsigned __int16 *
0x14000f021  cmovns  ebx, esi
0x14000f024  lea     r12, aHscmanager0; "hScManager != 0"
0x14000f02b  mov     esi, 142Dh
0x14000f030  mov     [rsp+0E0h+var_B8], ebx; int
0x14000f034  mov     edx, esi; unsigned int
0x14000f036  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x14000f03b  mov     r8, rdi; unsigned __int16 *
0x14000f03e  mov     rcx, r14; unsigned __int16 *
0x14000f041  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000f046  call    cs:__imp_IsDebuggerPresent
0x14000f04c  test    eax, eax
0x14000f04e  jz      short loc_14000F07F
0x14000f050  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14000f054  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000f05b  mov     [rsp+0E0h+var_B0], r12
0x14000f060  mov     r9d, esi
0x14000f063  mov     qword ptr [rsp+0E0h+var_B8], r15
0x14000f068  mov     r8, r14
0x14000f06b  mov     ecx, 2; unsigned __int8
0x14000f070  mov     [rsp+0E0h+var_C0], rdi
0x14000f075  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000f07a  jmp     loc_14000F635
0x14000f07f  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x14000f083  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000f08a  mov     qword ptr [rsp+0E0h+var_B8], r12
0x14000f08f  mov     r9, rdi
0x14000f092  mov     r8d, esi
0x14000f095  mov     [rsp+0E0h+var_C0], r15
0x14000f09a  mov     rdx, r14
0x14000f09d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000f0a2  jmp     loc_14000F635
0x14000f0a7  xor     ecx, ecx
0x14000f0a9  lea     rdx, ServiceName; "netlogon"
0x14000f0b0  mov     [rbp+57h+Buffer], rcx
0x14000f0b4  lea     r8d, [rcx+4]; dwDesiredAccess
0x14000f0b8  mov     rcx, rax; hSCManager
0x14000f0bb  call    cs:__imp_OpenServiceW
0x14000f0c1  mov     [rbp+57h+hSCObject], rax
0x14000f0c5  test    rax, rax
0x14000f0c8  jnz     loc_14000F188
0x14000f0ce  call    cs:__imp_GetLastError
0x14000f0d4  mov     ebx, eax
0x14000f0d6  test    eax, eax
0x14000f0d8  jle     short loc_14000F0E3
0x14000f0da  movzx   ebx, ax
0x14000f0dd  or      ebx, 80070000h
0x14000f0e3  mov     esi, 80004005h
0x14000f0e8  lea     r15, aCbraex; "CBRAEx"
0x14000f0ef  test    ebx, ebx
0x14000f0f1  lea     rdi, aCdiskprotectio_19; "CDiskProtection::s_CheckSecureChannelWi"...
0x14000f0f8  lea     r14, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000f0ff  mov     r9, r15; unsigned __int16 *
0x14000f102  cmovns  ebx, esi
0x14000f105  lea     r12, aHservice0; "hService != 0"
0x14000f10c  mov     esi, 1432h
0x14000f111  mov     [rsp+0E0h+var_B8], ebx; int
0x14000f115  mov     edx, esi; unsigned int
0x14000f117  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x14000f11c  mov     r8, rdi; unsigned __int16 *
0x14000f11f  mov     rcx, r14; unsigned __int16 *
0x14000f122  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000f127  call    cs:__imp_IsDebuggerPresent
0x14000f12d  test    eax, eax
0x14000f12f  jz      short loc_14000F160
0x14000f131  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14000f135  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000f13c  mov     [rsp+0E0h+var_B0], r12
0x14000f141  mov     r9d, esi
0x14000f144  mov     qword ptr [rsp+0E0h+var_B8], r15
0x14000f149  mov     r8, r14
0x14000f14c  mov     ecx, 2; unsigned __int8
0x14000f151  mov     [rsp+0E0h+var_C0], rdi
0x14000f156  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000f15b  jmp     loc_14000F619
0x14000f160  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x14000f164  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000f16b  mov     qword ptr [rsp+0E0h+var_B8], r12
0x14000f170  mov     r9, rdi
0x14000f173  mov     r8d, esi
0x14000f176  mov     [rsp+0E0h+var_C0], r15
0x14000f17b  mov     rdx, r14
0x14000f17e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000f183  jmp     loc_14000F619
0x14000f188  xor     esi, esi
0x14000f18a  mov     [rbp+57h+var_98], 1Eh
0x14000f191  mov     edi, 80070000h
0x14000f196  lea     r15, aCbraex; "CBRAEx"
0x14000f19d  lea     r14, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000f1a4  mov     ebx, 800706FDh
0x14000f1a9  lea     r12, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000f1b0  lea     r13d, [rsi+2]
0x14000f1b4  xorps   xmm0, xmm0
0x14000f1b7  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x14000f1bb  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x14000f1bf  test    esi, esi
0x14000f1c1  jns     short loc_14000F1E3
0x14000f1c3  call    ?s_RefreshDhcpIpAddress@CDiskProtection@@KAJXZ; CDiskProtection::s_RefreshDhcpIpAddress(void)
0x14000f1c8  lea     rcx, aCdiskprotectio_137; "CDiskProtection::s_CheckSecureChannelWi"...
0x14000f1cf  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000f1d4  mov     ecx, 1388h; dwMilliseconds
0x14000f1d9  call    cs:__imp_Sleep
0x14000f1df  mov     rax, [rbp+57h+hSCObject]
0x14000f1e3  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x14000f1e7  mov     rcx, rax; hService
0x14000f1ea  call    cs:__imp_QueryServiceStatus
0x14000f1f0  test    eax, eax
0x14000f1f2  jz      loc_14000F56E
0x14000f1f8  mov     rax, [rbp+57h+Buffer]
0x14000f1fc  test    rax, rax
0x14000f1ff  jz      short loc_14000F210
0x14000f201  mov     rcx, rax; Buffer
0x14000f204  call    cs:__imp_NetApiBufferFree
0x14000f20a  xor     ecx, ecx
0x14000f20c  mov     [rbp+57h+Buffer], rcx
0x14000f210  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 4
0x14000f214  mov     rax, [rbp+57h+var_80]
0x14000f218  mov     qword ptr [rbp+57h+Data], rax
0x14000f21c  mov     [rbp+57h+var_A0], 0
0x14000f224  jz      short loc_14000F230
0x14000f226  mov     esi, 80070700h
0x14000f22b  jmp     loc_14000F375
0x14000f230  lea     rax, [rbp+57h+var_A0]
0x14000f234  mov     r8d, r13d; QueryLevel
0x14000f237  lea     r9, [rbp+57h+Data]; Data
0x14000f23b  mov     [rsp+0E0h+var_C0], rax; Buffer
0x14000f240  mov     edx, 0Ah; FunctionCode
0x14000f245  xor     ecx, ecx; ServerName
0x14000f247  call    cs:__imp_I_NetLogonControl2
0x14000f24d  mov     esi, eax
0x14000f24f  test    eax, eax
0x14000f251  jz      short loc_14000F263
0x14000f253  jle     short loc_14000F25A
0x14000f255  movzx   esi, ax
0x14000f258  or      esi, edi
0x14000f25a  mov     rcx, [rbp+57h+var_A0]
0x14000f25e  jmp     loc_14000F34D
0x14000f263  mov     rcx, [rbp+57h+var_A0]
0x14000f267  test    rcx, rcx
0x14000f26a  jnz     loc_14000F311
0x14000f270  mov     eax, 8000FFFFh
0x14000f275  lea     r8, aCdiskprotectio_154; "CDiskProtection::s_VerifyTrustedDomainS"...
0x14000f27c  mov     [rsp+0E0h+var_B8], eax; int
0x14000f280  mov     esi, eax
0x14000f282  lea     rax, aPnetlogoninfo0; "pNetlogonInfo != 0"
0x14000f289  mov     r9, r15; unsigned __int16 *
0x14000f28c  mov     edx, 1408h; unsigned int
0x14000f291  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x14000f296  mov     rcx, r14; unsigned __int16 *
0x14000f299  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000f29e  call    cs:__imp_IsDebuggerPresent
0x14000f2a4  test    eax, eax
0x14000f2a6  lea     rax, aPnetlogoninfo0; "pNetlogonInfo != 0"
0x14000f2ad  jz      short loc_14000F2E6
0x14000f2af  mov     dword ptr [rsp+0E0h+var_A8], esi
0x14000f2b3  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000f2ba  mov     [rsp+0E0h+var_B0], rax
0x14000f2bf  mov     r9d, 1408h
0x14000f2c5  lea     rax, aCdiskprotectio_154; "CDiskProtection::s_VerifyTrustedDomainS"...
0x14000f2cc  mov     qword ptr [rsp+0E0h+var_B8], r15
0x14000f2d1  mov     r8, r14
0x14000f2d4  mov     [rsp+0E0h+var_C0], rax
0x14000f2d9  mov     ecx, r13d; unsigned __int8
0x14000f2dc  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000f2e1  jmp     loc_14000F25A
0x14000f2e6  mov     dword ptr [rsp+0E0h+var_B0], esi
0x14000f2ea  lea     r9, aCdiskprotectio_154; "CDiskProtection::s_VerifyTrustedDomainS"...
0x14000f2f1  mov     qword ptr [rsp+0E0h+var_B8], rax
0x14000f2f6  mov     r8d, 1408h
0x14000f2fc  mov     rdx, r14
0x14000f2ff  mov     [rsp+0E0h+var_C0], r15
0x14000f304  mov     rcx, r12; unsigned __int16 *
0x14000f307  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000f30c  jmp     loc_14000F25A
0x14000f311  test    byte ptr [rcx], 80h
0x14000f314  jnz     short loc_14000F31D
0x14000f316  mov     esi, 80070648h
0x14000f31b  jmp     short loc_14000F34D
0x14000f31d  mov     esi, [rcx+4]
0x14000f320  cmp     esi, 5
0x14000f323  jnz     short loc_14000F329
0x14000f325  xor     esi, esi
0x14000f327  jmp     short loc_14000F34D
0x14000f329  test    esi, esi
0x14000f32b  jz      short loc_14000F336
0x14000f32d  jle     short loc_14000F34D
0x14000f32f  movzx   esi, si
0x14000f332  or      esi, edi
0x14000f334  jmp     short loc_14000F34D
0x14000f336  cmp     qword ptr [rcx+8], 0
0x14000f33b  jnz     short loc_14000F341
0x14000f33d  mov     esi, ebx
0x14000f33f  jmp     short loc_14000F34D
0x14000f341  xor     esi, esi
0x14000f343  mov     [rbp+57h+Buffer], rcx
0x14000f347  xor     ecx, ecx; Buffer
0x14000f349  mov     [rbp+57h+var_A0], rcx
0x14000f34d  test    rcx, rcx
0x14000f350  jz      short loc_14000F358
0x14000f352  call    cs:__imp_NetApiBufferFree
0x14000f358  test    esi, esi
0x14000f35a  js      short loc_14000F375
0x14000f35c  mov     rax, [rbp+57h+Buffer]
0x14000f360  cmp     dword ptr [rax+4], 5
0x14000f364  jz      loc_14000F401
0x14000f36a  cmp     dword ptr [rax+10h], 0
0x14000f36e  jz      short loc_14000F388
0x14000f370  mov     esi, 800706FCh
0x14000f375  add     [rbp+57h+var_98], 0FFFFFFFFh
0x14000f379  jz      loc_14000F490
0x14000f37f  mov     rax, [rbp+57h+hSCObject]
0x14000f383  jmp     loc_14000F1B4
0x14000f388  mov     r8, [rax+8]
0x14000f38c  mov     eax, 5Ch ; '\'
0x14000f391  cmp     ax, [r8]
0x14000f395  jnz     short loc_14000F3A2
0x14000f397  cmp     ax, [r8+2]
0x14000f39c  jnz     short loc_14000F3A2
0x14000f39e  add     r8, 4; unsigned __int16 *
0x14000f3a2  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x14000f3a6  mov     edx, 104h; unsigned __int64
0x14000f3ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000f3b0  mov     ebx, eax
0x14000f3b2  test    eax, eax
0x14000f3b4  jns     loc_14000F60F
0x14000f3ba  mov     [rsp+0E0h+var_B8], eax; int
0x14000f3be  lea     r15, aChra; "CHRA"
0x14000f3c5  lea     rax, aHr; "hr"
0x14000f3cc  mov     esi, 146Fh
0x14000f3d1  lea     rdi, aCdiskprotectio_19; "CDiskProtection::s_CheckSecureChannelWi"...
0x14000f3d8  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x14000f3dd  mov     r9, r15; unsigned __int16 *
0x14000f3e0  mov     r8, rdi; unsigned __int16 *
0x14000f3e3  mov     edx, esi; unsigned int
0x14000f3e5  mov     rcx, r14; unsigned __int16 *
0x14000f3e8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000f3ed  call    cs:__imp_IsDebuggerPresent
0x14000f3f3  test    eax, eax
0x14000f3f5  lea     rax, aHr; "hr"
0x14000f3fc  jmp     loc_14000F5C4
0x14000f401  lea     rax, aNlinfo2Netlog2; "nlInfo2->netlog2_pdc_connection_status "...
0x14000f408  mov     esi, 145Ah
0x14000f40d  mov     qword ptr [rsp+0E0h+var_B8], rax
0x14000f412  lea     rdi, aCdiskprotectio_19; "CDiskProtection::s_CheckSecureChannelWi"...
0x14000f419  mov     r9d, esi
0x14000f41c  mov     [rsp+0E0h+var_C0], rdi
0x14000f421  mov     r8, r14
0x14000f424  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14000f42b  mov     ecx, 4; unsigned __int8
0x14000f430  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000f435  lea     r15, aPnetlogoninfoN; "pNetlogonInfo->netlog2_pdc_connection_s"...
0x14000f43c  mov     [rsp+0E0h+var_B8], ebx; int
0x14000f440  lea     r9, aCbrlaex; "CBRLAEx"
0x14000f447  mov     [rsp+0E0h+var_C0], r15; unsigned __int16 *
0x14000f44c  mov     r8, rdi; unsigned __int16 *
0x14000f44f  mov     edx, esi; unsigned int
0x14000f451  mov     rcx, r14; unsigned __int16 *
0x14000f454  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000f459  call    cs:__imp_IsDebuggerPresent
0x14000f45f  test    eax, eax
0x14000f461  lea     rax, aCbrlaex; "CBRLAEx"
0x14000f468  jz      short loc_14000F47D
0x14000f46a  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14000f46e  mov     [rsp+0E0h+var_B0], r15
0x14000f473  mov     qword ptr [rsp+0E0h+var_B8], rax
0x14000f478  jmp     loc_14000F5D4
0x14000f47d  mov     dword ptr [rsp+0E0h+var_B0], ebx
  ... truncated ...
```
