# CEventNotificationService::GetRemoteManagementCredential(__MIDL___MIDL_itf_wmssvc_0000_0000_0002,ushort * *,ushort * *)

- ea: `0x14001a290`
- end: `0x14001a72c`
- name: `?GetRemoteManagementCredential@CEventNotificationService@@UEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0002@@PEAPEAG1@Z`
- size: `1180`
- prototype: `__int64 __fastcall(__int64, unsigned int, BSTR *, BSTR *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400016b8`
- `0x14001a290`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140061a0c`
- `0x1400633fc`
- `0x14006c590`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14001a370`
- `ADVAPI32!RegCloseKey` at `0x14001a370`
- `ADVAPI32!RegCreateKeyExW` at `0x14001a5af`
- `ADVAPI32!RegCreateKeyExW` at `0x14001a5af`
- `KERNEL32!IsDebuggerPresent` at `0x14001a322`
- `KERNEL32!IsDebuggerPresent` at `0x14001a3fc`
- `KERNEL32!IsDebuggerPresent` at `0x14001a47c`
- `KERNEL32!IsDebuggerPresent` at `0x14001a510`
- `KERNEL32!IsDebuggerPresent` at `0x14001a602`
- `KERNEL32!IsDebuggerPresent` at `0x14001a706`
- `KERNEL32!IsDebuggerPresent` at `0x14001a322`
- `KERNEL32!IsDebuggerPresent` at `0x14001a3fc`
- `KERNEL32!IsDebuggerPresent` at `0x14001a47c`
- `KERNEL32!IsDebuggerPresent` at `0x14001a510`
- `KERNEL32!IsDebuggerPresent` at `0x14001a602`
- `KERNEL32!IsDebuggerPresent` at `0x14001a706`
- `OLEAUT32!__imp_SysAllocString` at `0x14001a4b7`
- `OLEAUT32!__imp_SysAllocString` at `0x14001a4b7`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14001a690`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14001a690`
- `OLEAUT32!__imp_SysFreeString` at `0x14001a359`
- `OLEAUT32!__imp_SysFreeString` at `0x14001a359`

## string_xrefs

- `0x14001a2ed`: `CEventNotificationService::GetRemoteManagementCredential`
- `0x14001a3cf`: `CEventNotificationService::GetRemoteManagementCredential`
- `0x14001a44f`: `CEventNotificationService::GetRemoteManagementCredential`
- `0x14001a4e3`: `CEventNotificationService::GetRemoteManagementCredential`
- `0x14001a5d1`: `CEventNotificationService::GetRemoteManagementCredential`
- `0x14001a6d9`: `CEventNotificationService::GetRemoteManagementCredential`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::GetRemoteManagementCredential(
        __int64 a1,
        unsigned int a2,
        BSTR *a3,
        BSTR *a4)
{
  unsigned __int16 *v4; // r13
  int v8; // ebx
  OLECHAR *v9; // rcx
  unsigned int v11; // r12d
  bool v12; // zf
  const unsigned __int16 *v13; // rax
  const OLECHAR *v14; // rcx
  unsigned int v15; // r12d
  bool v16; // zf
  const unsigned __int16 *v17; // rax
  LSTATUS v18; // eax
  const wchar_t *v19; // r8
  int StringValue; // eax
  unsigned int v21; // esi
  OLECHAR *v22; // rdi
  BSTR v23; // r14
  __int64 v24; // rdx
  OLECHAR *v25; // rcx
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-39h]
  PHKEY phkResult; // [rsp+38h] [rbp-31h]
  unsigned int v28; // [rsp+50h] [rbp-19h] BYREF
  BSTR v29; // [rsp+58h] [rbp-11h]
  unsigned __int16 *v30; // [rsp+60h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-1h] BYREF
  OLECHAR *strIn; // [rsp+70h] [rbp+7h] BYREF

  v4 = 0;
  hKey = 0;
  v30 = 0;
  strIn = 0;
  v28 = 0;
  v8 = CUserManagement::s_VerifyAccessLevelEx(3u, 0);
  if ( v8 < 0 )
    goto LABEL_5;
  if ( a2 > 1 )
  {
    v8 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x817u,
      L"CEventNotificationService::GetRemoteManagementCredential",
      L"CBRAEx",
      L"eType == WSAT_ManagementAccount || eType == WSAT_ControlAccount",
      -2147024809);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2071,
        L"CEventNotificationService::GetRemoteManagementCredential",
        L"CBRAEx",
        L"eType == WSAT_ManagementAccount || eType == WSAT_ControlAccount",
        -2147024809);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2071,
        L"CEventNotificationService::GetRemoteManagementCredential",
        L"CBRAEx",
        L"eType == WSAT_ManagementAccount || eType == WSAT_ControlAccount",
        -2147024809);
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v11 = 2072;
    v8 = -2147467261;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x818u,
      L"CEventNotificationService::GetRemoteManagementCredential",
      L"CBRAEx",
      L"pbstrUsername",
      -2147467261);
    v12 = !IsDebuggerPresent();
    v13 = L"pbstrUsername";
    goto LABEL_13;
  }
  if ( !a4 )
  {
    v11 = 2073;
    v8 = -2147467261;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x819u,
      L"CEventNotificationService::GetRemoteManagementCredential",
      L"CBRAEx",
      L"pbstrPassword",
      -2147467261);
    v12 = !IsDebuggerPresent();
    v13 = L"pbstrPassword";
LABEL_13:
    if ( v12 )
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v11,
        L"CEventNotificationService::GetRemoteManagementCredential",
        L"CBRAEx",
        v13,
        -2147467261);
    else
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v11,
        L"CEventNotificationService::GetRemoteManagementCredential",
        L"CBRAEx",
        v13,
        -2147467261);
    goto LABEL_5;
  }
  if ( CEventNotificationService::m_sShutdownInProgress )
  {
    v8 = -2147023781;
LABEL_5:
    v9 = 0;
    goto LABEL_6;
  }
  v14 = L"WmsManagement";
  if ( a2 )
    v14 = L"WmsControl";
  v29 = SysAllocString(v14);
  if ( !v29 )
  {
    v15 = 2082;
    v8 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x822u,
      L"CEventNotificationService::GetRemoteManagementCredential",
      L"CPR",
      L"bstrUserName",
      -2147024882);
    v16 = !IsDebuggerPresent();
    v17 = L"bstrUserName";
    goto LABEL_24;
  }
  v18 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows MultiPoint Server",
          0,
          0,
          0,
          0x20019u,
          0,
          &hKey,
          0);
  v8 = v18;
  if ( v18 )
  {
    if ( v18 > 0 )
      v8 = (unsigned __int16)v18 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x829u,
      L"CEventNotificationService::GetRemoteManagementCredential",
      L"CBRAEx",
      L"err == 0L",
      v8);
    if ( IsDebuggerPresent() )
    {
      LODWORD(phkResult) = v8;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2089,
        L"CEventNotificationService::GetRemoteManagementCredential",
        L"CBRAEx",
        L"err == 0L",
        phkResult);
    }
    else
    {
      LODWORD(lpSecurityAttributes) = v8;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2089,
        L"CEventNotificationService::GetRemoteManagementCredential",
        L"CBRAEx",
        L"err == 0L",
        lpSecurityAttributes);
    }
    goto LABEL_26;
  }
  v19 = L"WmsManagementAccountPassword";
  if ( a2 )
    v19 = (const wchar_t *)&stru_1400B4478;
  StringValue = RegUtil::GetStringValue(0, hKey, v19, &v30);
  v4 = v30;
  v8 = StringValue;
  if ( StringValue < 0 )
    goto LABEL_26;
  v8 = WmsDecrypt(v30, &strIn, &v28);
  if ( v8 < 0 )
    goto LABEL_26;
  v21 = v28;
  v22 = strIn;
  v23 = SysAllocStringLen(strIn, v28 - 1);
  if ( v22 && v21 )
  {
    v24 = v21;
    v25 = v22;
    do
    {
      *(_BYTE *)v25 = 0;
      v25 = (OLECHAR *)((char *)v25 + 1);
      --v24;
    }
    while ( v24 );
  }
  operator delete(v22);
  if ( !v23 )
  {
    v15 = 2101;
    v8 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x835u,
      L"CEventNotificationService::GetRemoteManagementCredential",
      L"CPR",
      L"bstrUnencryptedPassword",
      -2147024882);
    v16 = !IsDebuggerPresent();
    v17 = L"bstrUnencryptedPassword";
LABEL_24:
    if ( v16 )
    {
      LODWORD(lpSecurityAttributes) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v15,
        L"CEventNotificationService::GetRemoteManagementCredential",
        L"CPR",
        v17,
        lpSecurityAttributes);
    }
    else
    {
      LODWORD(phkResult) = -2147024882;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v15,
        L"CEventNotificationService::GetRemoteManagementCredential",
        L"CPR",
        v17,
        phkResult);
    }
LABEL_26:
    v9 = v29;
    goto LABEL_6;
  }
  *a3 = v29;
  v9 = 0;
  *a4 = v23;
LABEL_6:
  SysFreeString(v9);
  operator delete(v4);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001a290  push    rbp
0x14001a292  push    rbx
0x14001a293  push    rsi
0x14001a294  push    rdi
0x14001a295  push    r12
0x14001a297  push    r13
0x14001a299  push    r14
0x14001a29b  push    r15
0x14001a29d  lea     rbp, [rsp-1Fh]
0x14001a2a2  sub     rsp, 88h
0x14001a2a9  xor     r13d, r13d
0x14001a2ac  mov     [rbp+57h+hKey], 0
0x14001a2b4  mov     edi, edx
0x14001a2b6  mov     [rbp+57h+var_60], r13
0x14001a2ba  xor     edx, edx
0x14001a2bc  mov     [rbp+57h+strIn], r13
0x14001a2c0  mov     r15, r9
0x14001a2c3  mov     [rbp+57h+var_70], r13d
0x14001a2c7  mov     r12, r8
0x14001a2ca  lea     ecx, [rdx+3]
0x14001a2cd  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x14001a2d2  mov     ebx, eax
0x14001a2d4  test    eax, eax
0x14001a2d6  js      short loc_14001A356
0x14001a2d8  cmp     edi, 1
0x14001a2db  jbe     loc_14001A3B1
0x14001a2e1  mov     ebx, 80070057h
0x14001a2e6  lea     r14, aCbraex; "CBRAEx"
0x14001a2ed  lea     rsi, aCeventnotifica_102; "CEventNotificationService::GetRemoteMan"...
0x14001a2f4  mov     [rsp+0C0h+samDesired], ebx; int
0x14001a2f8  mov     r15d, 817h
0x14001a2fe  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001a305  lea     r12, aEtypeWsatManag; "eType == WSAT_ManagementAccount || eTyp"...
0x14001a30c  mov     r9, r14; unsigned __int16 *
0x14001a30f  mov     r8, rsi; unsigned __int16 *
0x14001a312  mov     qword ptr [rsp+0C0h+dwOptions], r12; unsigned __int16 *
0x14001a317  mov     edx, r15d; unsigned int
0x14001a31a  mov     rcx, rdi; unsigned __int16 *
0x14001a31d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001a322  call    cs:__imp_IsDebuggerPresent
0x14001a328  test    eax, eax
0x14001a32a  jz      short loc_14001A38C
0x14001a32c  mov     dword ptr [rsp+0C0h+phkResult], ebx
0x14001a330  mov     r9d, r15d
0x14001a333  mov     [rsp+0C0h+lpSecurityAttributes], r12
0x14001a338  mov     qword ptr [rsp+0C0h+samDesired], r14
0x14001a33d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001a344  mov     r8, rdi
0x14001a347  mov     qword ptr [rsp+0C0h+dwOptions], rsi
0x14001a34c  mov     ecx, 2; unsigned __int8
0x14001a351  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001a356  mov     rcx, r13; bstrString
0x14001a359  call    cs:__imp_SysFreeString
0x14001a35f  mov     rcx, r13; Block
0x14001a362  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001a367  mov     rcx, [rbp+57h+hKey]; hKey
0x14001a36b  test    rcx, rcx
0x14001a36e  jz      short loc_14001A376
0x14001a370  call    cs:__imp_RegCloseKey
0x14001a376  mov     eax, ebx
0x14001a378  add     rsp, 88h
0x14001a37f  pop     r15
0x14001a381  pop     r14
0x14001a383  pop     r13
0x14001a385  pop     r12
0x14001a387  pop     rdi
0x14001a388  pop     rsi
0x14001a389  pop     rbx
0x14001a38a  pop     rbp
0x14001a38b  retn
0x14001a38c  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], ebx
0x14001a390  mov     r8d, r15d
0x14001a393  mov     qword ptr [rsp+0C0h+samDesired], r12
0x14001a398  mov     r9, rsi
0x14001a39b  mov     qword ptr [rsp+0C0h+dwOptions], r14
0x14001a3a0  mov     rdx, rdi
0x14001a3a3  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14001a3aa  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14001a3af  jmp     short loc_14001A356
0x14001a3b1  test    r12, r12
0x14001a3b4  jnz     short loc_14001A431
0x14001a3b6  mov     r15d, 80004003h
0x14001a3bc  lea     rax, aPbstrusername_0; "pbstrUsername"
0x14001a3c3  lea     r14, aCbraex; "CBRAEx"
0x14001a3ca  mov     [rsp+0C0h+samDesired], r15d; int
0x14001a3cf  lea     rsi, aCeventnotifica_102; "CEventNotificationService::GetRemoteMan"...
0x14001a3d6  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned __int16 *
0x14001a3db  mov     r12d, 818h
0x14001a3e1  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001a3e8  mov     r9, r14; unsigned __int16 *
0x14001a3eb  mov     r8, rsi; unsigned __int16 *
0x14001a3ee  mov     edx, r12d; unsigned int
0x14001a3f1  mov     rcx, rdi; unsigned __int16 *
0x14001a3f4  mov     ebx, r15d
0x14001a3f7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001a3fc  call    cs:__imp_IsDebuggerPresent
0x14001a402  test    eax, eax
0x14001a404  lea     rax, aPbstrusername_0; "pbstrUsername"
0x14001a40b  jz      short loc_14001A41F
0x14001a40d  mov     dword ptr [rsp+0C0h+phkResult], r15d
0x14001a412  mov     r9d, r12d
0x14001a415  mov     [rsp+0C0h+lpSecurityAttributes], rax
0x14001a41a  jmp     loc_14001A338
0x14001a41f  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], r15d
0x14001a424  mov     r8d, r12d
0x14001a427  mov     qword ptr [rsp+0C0h+samDesired], rax
0x14001a42c  jmp     loc_14001A398
0x14001a431  test    r15, r15
0x14001a434  jnz     short loc_14001A490
0x14001a436  mov     r15d, 80004003h
0x14001a43c  lea     rax, aPbstrpassword; "pbstrPassword"
0x14001a443  lea     r14, aCbraex; "CBRAEx"
0x14001a44a  mov     [rsp+0C0h+samDesired], r15d; int
0x14001a44f  lea     rsi, aCeventnotifica_102; "CEventNotificationService::GetRemoteMan"...
0x14001a456  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned __int16 *
0x14001a45b  mov     r12d, 819h
0x14001a461  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001a468  mov     r9, r14; unsigned __int16 *
0x14001a46b  mov     r8, rsi; unsigned __int16 *
0x14001a46e  mov     edx, r12d; unsigned int
0x14001a471  mov     rcx, rdi; unsigned __int16 *
0x14001a474  mov     ebx, r15d
0x14001a477  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001a47c  call    cs:__imp_IsDebuggerPresent
0x14001a482  test    eax, eax
0x14001a484  lea     rax, aPbstrpassword; "pbstrPassword"
0x14001a48b  jmp     loc_14001A40B
0x14001a490  cmp     cs:?m_sShutdownInProgress@CEventNotificationService@@2HA, r13d; int CEventNotificationService::m_sShutdownInProgress
0x14001a497  jz      short loc_14001A4A3
0x14001a499  mov     ebx, 8007045Bh
0x14001a49e  jmp     loc_14001A356
0x14001a4a3  lea     rax, aWmscontrol; "WmsControl"
0x14001a4aa  test    edi, edi
0x14001a4ac  lea     rcx, aWmsmanagement; "WmsManagement"
0x14001a4b3  cmovnz  rcx, rax; psz
0x14001a4b7  call    cs:__imp_SysAllocString
0x14001a4bd  mov     [rbp+57h+var_68], rax
0x14001a4c1  test    rax, rax
0x14001a4c4  jnz     loc_14001A57B
0x14001a4ca  mov     r14d, 8007000Eh
0x14001a4d0  lea     rax, aBstrusername; "bstrUserName"
0x14001a4d7  lea     r15, aCpr; "CPR"
0x14001a4de  mov     [rsp+0C0h+samDesired], r14d; int
0x14001a4e3  lea     rsi, aCeventnotifica_102; "CEventNotificationService::GetRemoteMan"...
0x14001a4ea  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned __int16 *
0x14001a4ef  mov     r12d, 822h
0x14001a4f5  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001a4fc  mov     r9, r15; unsigned __int16 *
0x14001a4ff  mov     r8, rsi; unsigned __int16 *
0x14001a502  mov     edx, r12d; unsigned int
0x14001a505  mov     rcx, rdi; unsigned __int16 *
0x14001a508  mov     ebx, r14d
0x14001a50b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001a510  call    cs:__imp_IsDebuggerPresent
0x14001a516  test    eax, eax
0x14001a518  lea     rax, aBstrusername; "bstrUserName"
0x14001a51f  jz      short loc_14001A555
0x14001a521  mov     dword ptr [rsp+0C0h+phkResult], r14d
0x14001a526  mov     r9d, r12d
0x14001a529  mov     [rsp+0C0h+lpSecurityAttributes], rax
0x14001a52e  mov     qword ptr [rsp+0C0h+samDesired], r15
0x14001a533  mov     r8, rdi
0x14001a536  mov     qword ptr [rsp+0C0h+dwOptions], rsi
0x14001a53b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001a542  mov     ecx, 2; unsigned __int8
0x14001a547  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001a54c  mov     rcx, [rbp+57h+var_68]
0x14001a550  jmp     loc_14001A359
0x14001a555  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], r14d
0x14001a55a  mov     r8d, r12d
0x14001a55d  mov     qword ptr [rsp+0C0h+samDesired], rax
0x14001a562  mov     qword ptr [rsp+0C0h+dwOptions], r15
0x14001a567  mov     r9, rsi
0x14001a56a  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14001a571  mov     rdx, rdi
0x14001a574  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14001a579  jmp     short loc_14001A54C
0x14001a57b  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x14001a580  lea     rax, [rbp+57h+hKey]
0x14001a584  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14001a589  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows MultiPoint"...
0x14001a590  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x14001a595  xor     r9d, r9d; lpClass
0x14001a598  mov     [rsp+0C0h+samDesired], 20019h; samDesired
0x14001a5a0  xor     r8d, r8d; Reserved
0x14001a5a3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001a5aa  mov     [rsp+0C0h+dwOptions], r13d; dwOptions
0x14001a5af  call    cs:__imp_RegCreateKeyExW
0x14001a5b5  mov     ebx, eax
0x14001a5b7  test    eax, eax
0x14001a5b9  jz      short loc_14001A638
0x14001a5bb  jle     short loc_14001A5C6
0x14001a5bd  movzx   ebx, ax
0x14001a5c0  or      ebx, 80070000h
0x14001a5c6  lea     r14, aCbraex; "CBRAEx"
0x14001a5cd  mov     [rsp+0C0h+samDesired], ebx; int
0x14001a5d1  lea     rsi, aCeventnotifica_102; "CEventNotificationService::GetRemoteMan"...
0x14001a5d8  mov     r15d, 829h
0x14001a5de  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001a5e5  mov     r9, r14; unsigned __int16 *
0x14001a5e8  lea     r12, aErr0l; "err == 0L"
0x14001a5ef  mov     r8, rsi; unsigned __int16 *
0x14001a5f2  mov     edx, r15d; unsigned int
0x14001a5f5  mov     qword ptr [rsp+0C0h+dwOptions], r12; unsigned __int16 *
0x14001a5fa  mov     rcx, rdi; unsigned __int16 *
0x14001a5fd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001a602  call    cs:__imp_IsDebuggerPresent
0x14001a608  test    eax, eax
0x14001a60a  jz      short loc_14001A622
0x14001a60c  mov     dword ptr [rsp+0C0h+phkResult], ebx
0x14001a610  mov     r9d, r15d
0x14001a613  mov     [rsp+0C0h+lpSecurityAttributes], r12
0x14001a618  mov     qword ptr [rsp+0C0h+samDesired], r14
0x14001a61d  jmp     loc_14001A533
0x14001a622  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], ebx
0x14001a626  mov     r8d, r15d
0x14001a629  mov     qword ptr [rsp+0C0h+samDesired], r12
0x14001a62e  mov     qword ptr [rsp+0C0h+dwOptions], r14
0x14001a633  jmp     loc_14001A567
0x14001a638  mov     rdx, [rbp+57h+hKey]
0x14001a63c  lea     rax, stru_1400B4478
0x14001a643  test    edi, edi
0x14001a645  lea     r8, aWmsmanagementa; "WmsManagementAccountPassword"
0x14001a64c  lea     r9, [rbp+57h+var_60]
0x14001a650  cmovnz  r8, rax
0x14001a654  xor     ecx, ecx
0x14001a656  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x14001a65b  mov     r13, [rbp+57h+var_60]
0x14001a65f  mov     ebx, eax
0x14001a661  test    eax, eax
0x14001a663  js      loc_14001A54C
0x14001a669  lea     r8, [rbp+57h+var_70]; unsigned int *
0x14001a66d  mov     rcx, r13; unsigned __int16 *
0x14001a670  lea     rdx, [rbp+57h+strIn]; unsigned __int16 **
0x14001a674  call    ?WmsDecrypt@@YAJPEBGPEAPEAGPEAK@Z; WmsDecrypt(ushort const *,ushort * *,ulong *)
0x14001a679  mov     ebx, eax
0x14001a67b  test    eax, eax
0x14001a67d  js      loc_14001A54C
0x14001a683  mov     esi, [rbp+57h+var_70]
0x14001a686  mov     rdi, [rbp+57h+strIn]
0x14001a68a  mov     rcx, rdi; strIn
0x14001a68d  lea     edx, [rsi-1]; ui
0x14001a690  call    cs:__imp_SysAllocStringLen
0x14001a696  mov     r14, rax
0x14001a699  test    rdi, rdi
0x14001a69c  jz      short loc_14001A6B3
0x14001a69e  test    esi, esi
0x14001a6a0  jz      short loc_14001A6B3
0x14001a6a2  mov     edx, esi
0x14001a6a4  mov     rcx, rdi
0x14001a6a7  mov     byte ptr [rcx], 0
0x14001a6aa  inc     rcx
0x14001a6ad  sub     rdx, 1
0x14001a6b1  jnz     short loc_14001A6A7
0x14001a6b3  mov     rcx, rdi; Block
0x14001a6b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001a6bb  test    r14, r14
0x14001a6be  jnz     short loc_14001A71A
0x14001a6c0  mov     r14d, 8007000Eh
0x14001a6c6  lea     rax, aBstrunencrypte; "bstrUnencryptedPassword"
0x14001a6cd  lea     r15, aCpr; "CPR"
0x14001a6d4  mov     [rsp+0C0h+samDesired], r14d; int
0x14001a6d9  lea     rsi, aCeventnotifica_102; "CEventNotificationService::GetRemoteMan"...
0x14001a6e0  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned __int16 *
0x14001a6e5  mov     r12d, 835h
0x14001a6eb  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001a6f2  mov     r9, r15; unsigned __int16 *
0x14001a6f5  mov     r8, rsi; unsigned __int16 *
0x14001a6f8  mov     edx, r12d; unsigned int
0x14001a6fb  mov     rcx, rdi; unsigned __int16 *
0x14001a6fe  mov     ebx, r14d
0x14001a701  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001a706  call    cs:__imp_IsDebuggerPresent
0x14001a70c  test    eax, eax
0x14001a70e  lea     rax, aBstrunencrypte; "bstrUnencryptedPassword"
0x14001a715  jmp     loc_14001A51F
0x14001a71a  mov     rcx, [rbp+57h+var_68]
0x14001a71e  mov     [r12], rcx
0x14001a722  xor     ecx, ecx
0x14001a724  mov     [r15], r14
0x14001a727  jmp     loc_14001A359
```
