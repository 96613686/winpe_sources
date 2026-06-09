# CEventNotificationService::AddUrlAcl(ushort *,ushort *)

- ea: `0x140016d50`
- end: `0x14001751e`
- name: `?AddUrlAcl@CEventNotificationService@@UEAAJPEAG0@Z`
- size: `1998`
- prototype: `__int64 __fastcall(CEventNotificationService *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x1400033e8`
- `0x140016d50`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006c590`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x140016ecb`
- `ADVAPI32!LookupAccountNameW` at `0x140017064`
- `ADVAPI32!LookupAccountNameW` at `0x140016ecb`
- `ADVAPI32!LookupAccountNameW` at `0x140017064`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14001710f`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14001710f`
- `KERNEL32!LocalFree` at `0x1400174ec`
- `KERNEL32!LocalFree` at `0x1400174ec`
- `KERNEL32!GetLastError` at `0x140016ed9`
- `KERNEL32!GetLastError` at `0x140017072`
- `KERNEL32!GetLastError` at `0x14001711d`
- `KERNEL32!GetLastError` at `0x14001744c`
- `KERNEL32!GetLastError` at `0x140016ed9`
- `KERNEL32!GetLastError` at `0x140017072`
- `KERNEL32!GetLastError` at `0x14001711d`
- `KERNEL32!GetLastError` at `0x14001744c`
- `KERNEL32!IsDebuggerPresent` at `0x140016df6`
- `KERNEL32!IsDebuggerPresent` at `0x140016e94`
- `KERNEL32!IsDebuggerPresent` at `0x140016f42`
- `KERNEL32!IsDebuggerPresent` at `0x140017017`
- `KERNEL32!IsDebuggerPresent` at `0x1400170c9`
- `KERNEL32!IsDebuggerPresent` at `0x140017174`
- `KERNEL32!IsDebuggerPresent` at `0x140017255`
- `KERNEL32!IsDebuggerPresent` at `0x1400172d0`
- `KERNEL32!IsDebuggerPresent` at `0x14001737a`
- `KERNEL32!IsDebuggerPresent` at `0x140017423`
- `KERNEL32!IsDebuggerPresent` at `0x1400174a7`
- `KERNEL32!IsDebuggerPresent` at `0x140016df6`
- `KERNEL32!IsDebuggerPresent` at `0x140016e94`
- `KERNEL32!IsDebuggerPresent` at `0x140016f42`
- `KERNEL32!IsDebuggerPresent` at `0x140017017`
- `KERNEL32!IsDebuggerPresent` at `0x1400170c9`
- `KERNEL32!IsDebuggerPresent` at `0x140017174`
- `KERNEL32!IsDebuggerPresent` at `0x140017255`
- `KERNEL32!IsDebuggerPresent` at `0x1400172d0`
- `KERNEL32!IsDebuggerPresent` at `0x14001737a`
- `KERNEL32!IsDebuggerPresent` at `0x140017423`
- `KERNEL32!IsDebuggerPresent` at `0x1400174a7`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x140017325`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x140017325`

## string_xrefs

- `0x140016dc9`: `CEventNotificationService::AddUrlAcl`
- `0x140016e67`: `CEventNotificationService::AddUrlAcl`
- `0x140016f15`: `CEventNotificationService::AddUrlAcl`
- `0x140016fee`: `CEventNotificationService::AddUrlAcl`
- `0x140017095`: `CEventNotificationService::AddUrlAcl`
- `0x140017140`: `CEventNotificationService::AddUrlAcl`
- `0x14001722c`: `CEventNotificationService::AddUrlAcl`
- `0x1400172a3`: `CEventNotificationService::AddUrlAcl`
- `0x140017359`: `CEventNotificationService::AddUrlAcl`
- `0x1400173f6`: `CEventNotificationService::AddUrlAcl`
- `0x14001746f`: `CEventNotificationService::AddUrlAcl`
- `0x140016f02`: `pbSid`
- `0x140016f4a`: `pbSid`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::AddUrlAcl(
        CEventNotificationService *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  void *v5; // r13
  int v6; // ebx
  unsigned int v7; // r12d
  bool v8; // zf
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // r15
  const unsigned __int16 *v11; // rax
  __int64 v12; // r9
  __int64 v13; // r8
  void *v14; // r15
  void *ReferencedDomainName; // rax
  signed int v16; // eax
  __int64 v17; // r9
  signed int v18; // eax
  LPWSTR v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned __int64 v22; // rbx
  void *v23; // rax
  int v24; // eax
  signed int v25; // eax
  signed int LastError; // eax
  PSID_NAME_USE peUse; // [rsp+30h] [rbp-48h]
  PSID_NAME_USE peUsea; // [rsp+30h] [rbp-48h]
  int v30; // [rsp+38h] [rbp-40h]
  __int64 cbSid; // [rsp+40h] [rbp-38h] BYREF
  void *Block; // [rsp+48h] [rbp-30h]
  LPWSTR StringSid; // [rsp+50h] [rbp-28h] BYREF
  void *v34; // [rsp+58h] [rbp-20h]
  __int128 pConfigInformation; // [rsp+60h] [rbp-18h] BYREF
  DWORD cchReferencedDomainName; // [rsp+D8h] [rbp+60h] BYREF

  Block = 0;
  cchReferencedDomainName = 0;
  v34 = 0;
  StringSid = 0;
  v5 = 0;
  cbSid = 0x800000000LL;
  pConfigInformation = 0;
  v6 = CUserManagement::s_VerifyAccessLevelEx(1u, 0);
  if ( v6 < 0 )
    goto LABEL_73;
  if ( !a2 )
  {
    v7 = 2694;
    v6 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xA86u,
      L"CEventNotificationService::AddUrlAcl",
      L"CBRAEx",
      L"bstrUrl != 0",
      -2147024809);
    v8 = !IsDebuggerPresent();
    v9 = L"bstrUrl != 0";
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v7 = 2695;
    v6 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xA87u,
      L"CEventNotificationService::AddUrlAcl",
      L"CBRAEx",
      L"bstrUsername != 0",
      -2147024809);
    v8 = !IsDebuggerPresent();
    v9 = L"bstrUsername != 0";
LABEL_4:
    if ( v8 )
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v7,
        L"CEventNotificationService::AddUrlAcl",
        L"CBRAEx",
        v9,
        -2147024809);
    else
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v7,
        L"CEventNotificationService::AddUrlAcl",
        L"CBRAEx",
        v9,
        -2147024809,
        cbSid);
LABEL_73:
    v14 = 0;
    goto LABEL_74;
  }
  if ( LookupAccountNameW(0, a3, 0, (LPDWORD)&cbSid, 0, &cchReferencedDomainName, (PSID_NAME_USE)&cbSid + 1)
    || GetLastError() != 122 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xA8Eu,
      L"CEventNotificationService::AddUrlAcl",
      L"CBRAEx",
      L"!fSuccess && GetLastError() == 122L",
      v6);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2702,
        L"CEventNotificationService::AddUrlAcl",
        L"CBRAEx",
        L"!fSuccess && GetLastError() == 122L",
        v6,
        cbSid);
    }
    else
    {
      LODWORD(peUse) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2702,
        L"CEventNotificationService::AddUrlAcl",
        L"CBRAEx",
        L"!fSuccess && GetLastError() == 122L",
        peUse);
    }
    goto LABEL_73;
  }
  v5 = operator new((unsigned int)cbSid);
  if ( !v5 )
  {
    v10 = L"CPR";
    v6 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xA91u,
      L"CEventNotificationService::AddUrlAcl",
      L"CPR",
      L"pbSid",
      -2147024882);
    v8 = !IsDebuggerPresent();
    v11 = L"pbSid";
    if ( !v8 )
    {
      v12 = 2705;
LABEL_14:
      v30 = -2147024882;
      peUsea = (PSID_NAME_USE)v11;
LABEL_15:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v12,
        L"CEventNotificationService::AddUrlAcl",
        v10,
        peUsea,
        v30);
LABEL_19:
      v14 = Block;
      goto LABEL_74;
    }
    v13 = 2705;
    goto LABEL_17;
  }
  ReferencedDomainName = operator new(saturated_mul(cchReferencedDomainName, 2u));
  v34 = ReferencedDomainName;
  if ( !ReferencedDomainName )
  {
    v10 = L"CPR";
    v6 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xA94u,
      L"CEventNotificationService::AddUrlAcl",
      L"CPR",
      L"pszDomain",
      -2147024882);
    v8 = !IsDebuggerPresent();
    v11 = L"pszDomain";
    if ( !v8 )
    {
      v12 = 2708;
      goto LABEL_14;
    }
    v13 = 2708;
LABEL_17:
    LODWORD(peUse) = -2147024882;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v13,
      L"CEventNotificationService::AddUrlAcl",
      L"CPR",
      v11,
      peUse);
    goto LABEL_19;
  }
  if ( !LookupAccountNameW(
          0,
          a3,
          v5,
          (LPDWORD)&cbSid,
          (LPWSTR)ReferencedDomainName,
          &cchReferencedDomainName,
          (PSID_NAME_USE)&cbSid + 1) )
  {
    v16 = GetLastError();
    v6 = v16;
    if ( v16 > 0 )
      v6 = (unsigned __int16)v16 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xA97u,
      L"CEventNotificationService::AddUrlAcl",
      L"CBRAEx",
      L"fSuccess",
      v6);
    if ( !IsDebuggerPresent() )
    {
      LODWORD(peUse) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2711,
        L"CEventNotificationService::AddUrlAcl",
        L"CBRAEx",
        L"fSuccess",
        peUse);
      goto LABEL_19;
    }
    v17 = 2711;
    goto LABEL_31;
  }
  if ( !ConvertSidToStringSidW(v5, &StringSid) )
  {
    v18 = GetLastError();
    v6 = v18;
    if ( v18 > 0 )
      v6 = (unsigned __int16)v18 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xA9Au,
      L"CEventNotificationService::AddUrlAcl",
      L"CBRAEx",
      L"fSuccess",
      v6);
    if ( !IsDebuggerPresent() )
    {
      LODWORD(peUse) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2714,
        L"CEventNotificationService::AddUrlAcl",
        L"CBRAEx",
        L"fSuccess",
        peUse);
      goto LABEL_19;
    }
    v17 = 2714;
LABEL_31:
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v17,
      L"CEventNotificationService::AddUrlAcl",
      L"CBRAEx",
      L"fSuccess",
      v6);
    goto LABEL_19;
  }
  v19 = StringSid;
  if ( !StringSid )
  {
    v6 = -2147024809;
LABEL_63:
    v10 = L"CHRA";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xA9Du,
      L"CEventNotificationService::AddUrlAcl",
      L"CHRA",
      L"hr",
      v6);
    if ( !IsDebuggerPresent() )
    {
      LODWORD(peUse) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2717,
        L"CEventNotificationService::AddUrlAcl",
        L"CHRA",
        L"hr",
        peUse);
      goto LABEL_19;
    }
    v12 = 2717;
LABEL_53:
    v30 = v6;
    peUsea = (PSID_NAME_USE)L"hr";
    goto LABEL_15;
  }
  v20 = 0x7FFFFFFF;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v20;
  }
  while ( v20 );
  v6 = v20 == 0 ? 0x80070057 : 0;
  v21 = (0x7FFFFFFF - v20) & -(__int64)(v20 != 0);
  if ( !v20 )
    goto LABEL_63;
  v22 = v21 + 16;
  v23 = operator new(saturated_mul(v21 + 16, 2u));
  Block = v23;
  if ( !v23 )
  {
    v10 = L"CPR";
    v6 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xAA1u,
      L"CEventNotificationService::AddUrlAcl",
      L"CPR",
      L"pszSddl",
      -2147024882);
    v8 = !IsDebuggerPresent();
    v11 = L"pszSddl";
    if ( !v8 )
    {
      v12 = 2721;
      goto LABEL_14;
    }
    v13 = 2721;
    goto LABEL_17;
  }
  v24 = StringCchPrintfW((unsigned __int16 *)v23, v22, L"D:(A;;GX;;;%s)", StringSid);
  v6 = v24;
  if ( v24 < 0 )
  {
    v10 = L"CHRA";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xAA4u,
      L"CEventNotificationService::AddUrlAcl",
      L"CHRA",
      L"hr",
      v24);
    if ( !IsDebuggerPresent() )
    {
      LODWORD(peUse) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2724,
        L"CEventNotificationService::AddUrlAcl",
        L"CHRA",
        L"hr",
        peUse);
      goto LABEL_19;
    }
    v12 = 2724;
    goto LABEL_53;
  }
  v14 = Block;
  *((_QWORD *)&pConfigInformation + 1) = Block;
  *(_QWORD *)&pConfigInformation = a2;
  v25 = HttpSetServiceConfiguration(0, HttpServiceConfigUrlAclInfo, &pConfigInformation, 0x10u, 0);
  if ( v25 )
  {
    if ( v25 > 0 )
      v6 = (unsigned __int16)v25 | 0x80070000;
    else
      v6 = v25;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xAB2u,
      L"CEventNotificationService::AddUrlAcl",
      L"CBRAEx",
      L"ulStatus == 0L",
      v6);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2738,
        L"CEventNotificationService::AddUrlAcl",
        L"CBRAEx",
        L"ulStatus == 0L",
        v6);
    }
    else
    {
      LODWORD(peUse) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2738,
        L"CEventNotificationService::AddUrlAcl",
        L"CBRAEx",
        L"ulStatus == 0L",
        peUse);
    }
  }
LABEL_74:
  LocalFree(StringSid);
  operator delete(v14);
  operator delete(v5);
  operator delete(v34);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140016d50  push    rbp
0x140016d52  push    rbx
0x140016d53  push    rsi
0x140016d54  push    rdi
0x140016d55  push    r12
0x140016d57  push    r13
0x140016d59  push    r14
0x140016d5b  push    r15
0x140016d5d  mov     rbp, rsp
0x140016d60  sub     rsp, 78h
0x140016d64  xor     r14d, r14d
0x140016d67  mov     [rbp+var_34], 8
0x140016d6e  mov     rsi, rdx
0x140016d71  mov     [rbp+Block], r14
0x140016d75  xor     edx, edx
0x140016d77  mov     [rbp+arg_18], r14d
0x140016d7b  xorps   xmm0, xmm0
0x140016d7e  mov     [rbp+var_20], r14
0x140016d82  mov     rdi, r8
0x140016d85  mov     [rbp+StringSid], r14
0x140016d89  mov     r13d, r14d
0x140016d8c  mov     [rbp+cbSid], r14d
0x140016d90  lea     ecx, [rdx+1]
0x140016d93  movdqu  [rbp+pConfigInformation], xmm0
0x140016d98  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x140016d9d  mov     ebx, eax
0x140016d9f  test    eax, eax
0x140016da1  js      loc_1400174E5
0x140016da7  test    rsi, rsi
0x140016daa  jnz     loc_140016E49
0x140016db0  mov     r15d, 80070057h
0x140016db6  lea     rax, aBstrurl0; "bstrUrl != 0"
0x140016dbd  lea     r14, aCbraex; "CBRAEx"
0x140016dc4  mov     dword ptr [rsp+78h+cchReferencedDomainName], r15d; int
0x140016dc9  lea     rsi, aCeventnotifica_46; "CEventNotificationService::AddUrlAcl"
0x140016dd0  mov     [rsp+78h+ReferencedDomainName], rax; unsigned __int16 *
0x140016dd5  mov     r12d, 0A86h
0x140016ddb  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140016de2  mov     r9, r14; unsigned __int16 *
0x140016de5  mov     r8, rsi; unsigned __int16 *
0x140016de8  mov     edx, r12d; unsigned int
0x140016deb  mov     rcx, rdi; unsigned __int16 *
0x140016dee  mov     ebx, r15d
0x140016df1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140016df6  call    cs:__imp_IsDebuggerPresent
0x140016dfc  test    eax, eax
0x140016dfe  lea     rax, aBstrurl0; "bstrUrl != 0"
0x140016e05  jz      short loc_140016E37
0x140016e07  mov     [rsp+78h+var_40], r15d
0x140016e0c  mov     r9d, r12d
0x140016e0f  mov     [rsp+78h+peUse], rax
0x140016e14  mov     [rsp+78h+cchReferencedDomainName], r14
0x140016e19  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140016e20  mov     r8, rdi
0x140016e23  mov     [rsp+78h+ReferencedDomainName], rsi
0x140016e28  mov     ecx, 2; unsigned __int8
0x140016e2d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140016e32  jmp     loc_1400174E5
0x140016e37  mov     dword ptr [rsp+78h+peUse], r15d
0x140016e3c  mov     r8d, r12d
0x140016e3f  mov     [rsp+78h+cchReferencedDomainName], rax
0x140016e44  jmp     loc_1400174CE
0x140016e49  test    rdi, rdi
0x140016e4c  jnz     short loc_140016EA8
0x140016e4e  mov     r15d, 80070057h
0x140016e54  lea     rax, aBstrusername0; "bstrUsername != 0"
0x140016e5b  lea     r14, aCbraex; "CBRAEx"
0x140016e62  mov     dword ptr [rsp+78h+cchReferencedDomainName], r15d; int
0x140016e67  lea     rsi, aCeventnotifica_46; "CEventNotificationService::AddUrlAcl"
0x140016e6e  mov     [rsp+78h+ReferencedDomainName], rax; unsigned __int16 *
0x140016e73  mov     r12d, 0A87h
0x140016e79  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140016e80  mov     r9, r14; unsigned __int16 *
0x140016e83  mov     r8, rsi; unsigned __int16 *
0x140016e86  mov     edx, r12d; unsigned int
0x140016e89  mov     rcx, rdi; unsigned __int16 *
0x140016e8c  mov     ebx, r15d
0x140016e8f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140016e94  call    cs:__imp_IsDebuggerPresent
0x140016e9a  test    eax, eax
0x140016e9c  lea     rax, aBstrusername0; "bstrUsername != 0"
0x140016ea3  jmp     loc_140016E05
0x140016ea8  lea     rax, [rbp+var_34]
0x140016eac  xor     r8d, r8d; Sid
0x140016eaf  mov     [rsp+78h+peUse], rax; peUse
0x140016eb4  lea     r9, [rbp+cbSid]; cbSid
0x140016eb8  lea     rax, [rbp+arg_18]
0x140016ebc  mov     rdx, rdi; lpAccountName
0x140016ebf  mov     [rsp+78h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140016ec4  xor     ecx, ecx; lpSystemName
0x140016ec6  mov     [rsp+78h+ReferencedDomainName], r14; ReferencedDomainName
0x140016ecb  call    cs:__imp_LookupAccountNameW
0x140016ed1  test    eax, eax
0x140016ed3  jnz     loc_14001744C
0x140016ed9  call    cs:__imp_GetLastError
0x140016edf  cmp     eax, 7Ah ; 'z'
0x140016ee2  jnz     loc_14001744C
0x140016ee8  mov     ecx, [rbp+cbSid]; Size
0x140016eeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016ef0  mov     r13, rax
0x140016ef3  test    rax, rax
0x140016ef6  jnz     loc_140016FAC
0x140016efc  mov     r14d, 8007000Eh
0x140016f02  lea     rax, aPbsid; "pbSid"
0x140016f09  lea     r15, aCpr; "CPR"
0x140016f10  mov     dword ptr [rsp+78h+cchReferencedDomainName], r14d; int
0x140016f15  lea     rsi, aCeventnotifica_46; "CEventNotificationService::AddUrlAcl"
0x140016f1c  mov     [rsp+78h+ReferencedDomainName], rax; unsigned __int16 *
0x140016f21  mov     r12d, 0A91h
0x140016f27  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140016f2e  mov     r9, r15; unsigned __int16 *
0x140016f31  mov     r8, rsi; unsigned __int16 *
0x140016f34  mov     edx, r12d; unsigned int
0x140016f37  mov     rcx, rdi; unsigned __int16 *
0x140016f3a  mov     ebx, r14d
0x140016f3d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140016f42  call    cs:__imp_IsDebuggerPresent
0x140016f48  test    eax, eax
0x140016f4a  lea     rax, aPbsid; "pbSid"
0x140016f51  jz      short loc_140016F7F
0x140016f53  mov     r9d, r12d
0x140016f56  lea     ecx, [r13+2]; unsigned __int8
0x140016f5a  mov     [rsp+78h+var_40], r14d
0x140016f5f  mov     [rsp+78h+peUse], rax
0x140016f64  mov     [rsp+78h+cchReferencedDomainName], r15
0x140016f69  mov     r8, rdi
0x140016f6c  mov     [rsp+78h+ReferencedDomainName], rsi
0x140016f71  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140016f78  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140016f7d  jmp     short loc_140016FA3
0x140016f7f  mov     r8d, r12d
0x140016f82  mov     dword ptr [rsp+78h+peUse], r14d
0x140016f87  mov     [rsp+78h+cchReferencedDomainName], rax
0x140016f8c  mov     [rsp+78h+ReferencedDomainName], r15
0x140016f91  mov     r9, rsi
0x140016f94  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140016f9b  mov     rdx, rdi
0x140016f9e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140016fa3  mov     r15, [rbp+Block]
0x140016fa7  jmp     loc_1400174E8
0x140016fac  mov     ecx, [rbp+arg_18]
0x140016faf  mov     r12d, 2
0x140016fb5  mov     eax, r12d
0x140016fb8  mul     rcx
0x140016fbb  lea     rcx, [r12-3]
0x140016fc0  cmovb   rax, rcx
0x140016fc4  mov     rcx, rax; Size
0x140016fc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016fcc  mov     [rbp+var_20], rax
0x140016fd0  test    rax, rax
0x140016fd3  jnz     short loc_140017041
0x140016fd5  mov     r14d, 8007000Eh
0x140016fdb  lea     rax, aPszdomain; "pszDomain"
0x140016fe2  lea     r15, aCpr; "CPR"
0x140016fe9  mov     dword ptr [rsp+78h+cchReferencedDomainName], r14d; int
0x140016fee  lea     rsi, aCeventnotifica_46; "CEventNotificationService::AddUrlAcl"
0x140016ff5  mov     [rsp+78h+ReferencedDomainName], rax; unsigned __int16 *
0x140016ffa  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140017001  mov     r9, r15; unsigned __int16 *
0x140017004  mov     r8, rsi; unsigned __int16 *
0x140017007  mov     rcx, rdi; unsigned __int16 *
0x14001700a  mov     edx, 0A94h; unsigned int
0x14001700f  mov     ebx, r14d
0x140017012  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140017017  call    cs:__imp_IsDebuggerPresent
0x14001701d  test    eax, eax
0x14001701f  lea     rax, aPszdomain; "pszDomain"
0x140017026  jz      short loc_140017036
0x140017028  mov     r9d, 0A94h
0x14001702e  mov     ecx, r12d
0x140017031  jmp     loc_140016F5A
0x140017036  mov     r8d, 0A94h
0x14001703c  jmp     loc_140016F82
0x140017041  lea     rcx, [rbp+var_34]
0x140017045  mov     r8, r13; Sid
0x140017048  mov     [rsp+78h+peUse], rcx; peUse
0x14001704d  lea     r9, [rbp+cbSid]; cbSid
0x140017051  lea     rcx, [rbp+arg_18]
0x140017055  mov     rdx, rdi; lpAccountName
0x140017058  mov     [rsp+78h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x14001705d  xor     ecx, ecx; lpSystemName
0x14001705f  mov     [rsp+78h+ReferencedDomainName], rax; ReferencedDomainName
0x140017064  call    cs:__imp_LookupAccountNameW
0x14001706a  test    eax, eax
0x14001706c  jnz     loc_140017108
0x140017072  call    cs:__imp_GetLastError
0x140017078  mov     ebx, eax
0x14001707a  test    eax, eax
0x14001707c  jle     short loc_140017087
0x14001707e  movzx   ebx, ax
0x140017081  or      ebx, 80070000h
0x140017087  mov     eax, 80004005h
0x14001708c  lea     r14, aCbraex; "CBRAEx"
0x140017093  test    ebx, ebx
0x140017095  lea     rsi, aCeventnotifica_46; "CEventNotificationService::AddUrlAcl"
0x14001709c  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400170a3  mov     r9, r14; unsigned __int16 *
0x1400170a6  cmovns  ebx, eax
0x1400170a9  lea     r15, aFsuccess; "fSuccess"
0x1400170b0  mov     dword ptr [rsp+78h+cchReferencedDomainName], ebx; int
0x1400170b4  mov     r8, rsi; unsigned __int16 *
0x1400170b7  mov     edx, 0A97h; unsigned int
0x1400170bc  mov     [rsp+78h+ReferencedDomainName], r15; unsigned __int16 *
0x1400170c1  mov     rcx, rdi; unsigned __int16 *
0x1400170c4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400170c9  call    cs:__imp_IsDebuggerPresent
0x1400170cf  test    eax, eax
0x1400170d1  jz      short loc_1400170EF
0x1400170d3  mov     r9d, 0A97h
0x1400170d9  mov     [rsp+78h+var_40], ebx
0x1400170dd  mov     ecx, r12d
0x1400170e0  mov     [rsp+78h+peUse], r15
0x1400170e5  mov     [rsp+78h+cchReferencedDomainName], r14
0x1400170ea  jmp     loc_140016F69
0x1400170ef  mov     dword ptr [rsp+78h+peUse], ebx
0x1400170f3  mov     r8d, 0A97h
0x1400170f9  mov     [rsp+78h+cchReferencedDomainName], r15
0x1400170fe  mov     [rsp+78h+ReferencedDomainName], r14
0x140017103  jmp     loc_140016F91
0x140017108  lea     rdx, [rbp+StringSid]; StringSid
0x14001710c  mov     rcx, r13; Sid
0x14001710f  call    cs:__imp_ConvertSidToStringSidW
0x140017115  test    eax, eax
0x140017117  jnz     loc_1400171A2
0x14001711d  call    cs:__imp_GetLastError
0x140017123  mov     ebx, eax
0x140017125  test    eax, eax
0x140017127  jle     short loc_140017132
0x140017129  movzx   ebx, ax
0x14001712c  or      ebx, 80070000h
0x140017132  mov     eax, 80004005h
0x140017137  lea     r14, aCbraex; "CBRAEx"
0x14001713e  test    ebx, ebx
0x140017140  lea     rsi, aCeventnotifica_46; "CEventNotificationService::AddUrlAcl"
0x140017147  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001714e  mov     r9, r14; unsigned __int16 *
0x140017151  cmovns  ebx, eax
0x140017154  lea     r15, aFsuccess; "fSuccess"
0x14001715b  mov     dword ptr [rsp+78h+cchReferencedDomainName], ebx; int
0x14001715f  mov     r8, rsi; unsigned __int16 *
0x140017162  mov     edx, 0A9Ah; unsigned int
0x140017167  mov     [rsp+78h+ReferencedDomainName], r15; unsigned __int16 *
0x14001716c  mov     rcx, rdi; unsigned __int16 *
0x14001716f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140017174  call    cs:__imp_IsDebuggerPresent
0x14001717a  test    eax, eax
0x14001717c  jz      short loc_140017189
0x14001717e  mov     r9d, 0A9Ah
0x140017184  jmp     loc_1400170D9
0x140017189  mov     dword ptr [rsp+78h+peUse], ebx
0x14001718d  mov     r8d, 0A9Ah
0x140017193  mov     [rsp+78h+cchReferencedDomainName], r15
0x140017198  mov     [rsp+78h+ReferencedDomainName], r14
0x14001719d  jmp     loc_140016F91
0x1400171a2  mov     rax, [rbp+StringSid]
0x1400171a6  test    rax, rax
0x1400171a9  jz      loc_1400173E6
0x1400171af  mov     edx, 7FFFFFFFh
0x1400171b4  mov     ecx, edx
0x1400171b6  cmp     [rax], r14w
0x1400171ba  jz      short loc_1400171C5
0x1400171bc  add     rax, r12
0x1400171bf  sub     rcx, 1
0x1400171c3  jnz     short loc_1400171B6
0x1400171c5  mov     rax, rcx
0x1400171c8  neg     rax
0x1400171cb  mov     rax, rcx
0x1400171ce  sbb     ebx, ebx
0x1400171d0  sub     rdx, rcx
0x1400171d3  not     ebx
0x1400171d5  and     ebx, 80070057h
0x1400171db  neg     rax
0x1400171de  sbb     r8, r8
0x1400171e1  and     r8, rdx
0x1400171e4  test    rcx, rcx
0x1400171e7  jz      loc_1400173EB
0x1400171ed  lea     rbx, [r8+10h]
0x1400171f1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400171f8  mov     rax, r12
0x1400171fb  mul     rbx
0x1400171fe  cmovb   rax, rcx
0x140017202  mov     rcx, rax; Size
0x140017205  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001720a  mov     [rbp+Block], rax
0x14001720e  test    rax, rax
0x140017211  jnz     short loc_14001727C
0x140017213  mov     r14d, 8007000Eh
0x140017219  lea     rax, aPszsddl; "pszSddl"
0x140017220  lea     r15, aCpr; "CPR"
0x140017227  mov     dword ptr [rsp+78h+cchReferencedDomainName], r14d; int
0x14001722c  lea     rsi, aCeventnotifica_46; "CEventNotificationService::AddUrlAcl"
0x140017233  mov     [rsp+78h+ReferencedDomainName], rax; unsigned __int16 *
0x140017238  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001723f  mov     r9, r15; unsigned __int16 *
0x140017242  mov     r8, rsi; unsigned __int16 *
0x140017245  mov     rcx, rdi; unsigned __int16 *
0x140017248  mov     edx, 0AA1h; unsigned int
0x14001724d  mov     ebx, r14d
0x140017250  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140017255  call    cs:__imp_IsDebuggerPresent
  ... truncated ...
```
