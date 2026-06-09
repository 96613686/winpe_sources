# CEventNotificationService::StoreRemoteManagementProperty(__MIDL___MIDL_itf_wmssvc_0000_0000_0031,ushort *,__MIDL___MIDL_itf_wmssvc_0000_0000_0032,tagVARIANT)

- ea: `0x140025c30`
- end: `0x140026291`
- name: `?StoreRemoteManagementProperty@CEventNotificationService@@UEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0031@@PEAGW4__MIDL___MIDL_itf_wmssvc_0000_0000_0032@@UtagVARIANT@@@Z`
- size: `1633`
- prototype: `__int64 __fastcall(__int64, int, const WCHAR *, unsigned int, VARIANT *varIn)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400016b8`
- `0x140025c30`
- `0x14002897c`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006296c`
- `0x14006379c`
- `0x14006c590`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140026261`
- `ADVAPI32!RegCloseKey` at `0x140026278`
- `ADVAPI32!RegCloseKey` at `0x140026261`
- `ADVAPI32!RegCloseKey` at `0x140026278`
- `ADVAPI32!RegCreateKeyExW` at `0x140025d7a`
- `ADVAPI32!RegCreateKeyExW` at `0x140025e1c`
- `ADVAPI32!RegCreateKeyExW` at `0x140025d7a`
- `ADVAPI32!RegCreateKeyExW` at `0x140025e1c`
- `ADVAPI32!RegSetValueExW` at `0x1400261b7`
- `ADVAPI32!RegSetValueExW` at `0x1400261b7`
- `KERNEL32!IsDebuggerPresent` at `0x140025cd4`
- `KERNEL32!IsDebuggerPresent` at `0x140025dc9`
- `KERNEL32!IsDebuggerPresent` at `0x140025e6b`
- `KERNEL32!IsDebuggerPresent` at `0x140025f04`
- `KERNEL32!IsDebuggerPresent` at `0x140025faf`
- `KERNEL32!IsDebuggerPresent` at `0x140026049`
- `KERNEL32!IsDebuggerPresent` at `0x1400260e0`
- `KERNEL32!IsDebuggerPresent` at `0x140026150`
- `KERNEL32!IsDebuggerPresent` at `0x14002620c`
- `KERNEL32!IsDebuggerPresent` at `0x140025cd4`
- `KERNEL32!IsDebuggerPresent` at `0x140025dc9`
- `KERNEL32!IsDebuggerPresent` at `0x140025e6b`
- `KERNEL32!IsDebuggerPresent` at `0x140025f04`
- `KERNEL32!IsDebuggerPresent` at `0x140025faf`
- `KERNEL32!IsDebuggerPresent` at `0x140026049`
- `KERNEL32!IsDebuggerPresent` at `0x1400260e0`
- `KERNEL32!IsDebuggerPresent` at `0x140026150`
- `KERNEL32!IsDebuggerPresent` at `0x14002620c`
- `PROPSYS!VariantToUInt32` at `0x140026182`
- `PROPSYS!VariantToUInt32` at `0x140026182`

## string_xrefs

- `0x140025caa`: `CEventNotificationService::StoreRemoteManagementProperty`
- `0x140025d9c`: `CEventNotificationService::StoreRemoteManagementProperty`
- `0x140025e3e`: `CEventNotificationService::StoreRemoteManagementProperty`
- `0x140025edb`: `CEventNotificationService::StoreRemoteManagementProperty`
- `0x140025f7a`: `CEventNotificationService::StoreRemoteManagementProperty`
- `0x140026014`: `CEventNotificationService::StoreRemoteManagementProperty`
- `0x1400260ab`: `CEventNotificationService::StoreRemoteManagementProperty`
- `0x14002611b`: `CEventNotificationService::StoreRemoteManagementProperty`
- `0x1400261df`: `CEventNotificationService::StoreRemoteManagementProperty`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::StoreRemoteManagementProperty(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        unsigned int a4,
        VARIANT *varIn)
{
  unsigned __int16 *v5; // r13
  unsigned int v9; // ecx
  int v10; // ebx
  bool v11; // zf
  const unsigned __int16 *v12; // rax
  __int64 v13; // r9
  const WCHAR *v14; // rdx
  LSTATUS v15; // eax
  __int64 v16; // r8
  LSTATUS v17; // eax
  LONGLONG llVal; // rbx
  HKEY v19; // rax
  const unsigned __int16 *v20; // r9
  unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // r12
  __int64 v23; // r9
  const unsigned __int16 *bstrVal; // rcx
  const WCHAR *v25; // rax
  LSTATUS v26; // eax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-48h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesa; // [rsp+30h] [rbp-48h]
  PHKEY phkResult; // [rsp+38h] [rbp-40h]
  HKEY v31; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int16 *v32; // [rsp+58h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-18h] BYREF
  ULONG pulRet; // [rsp+D8h] [rbp+60h] BYREF

  v5 = 0;
  hKey = 0;
  v31 = 0;
  pulRet = 0;
  v32 = 0;
  v9 = 2;
  if ( a4 != 2 )
    v9 = 1;
  v10 = CUserManagement::s_VerifyAccessLevelEx(v9, 0);
  if ( v10 < 0 )
    goto LABEL_68;
  if ( !a3 )
  {
    v10 = -2147467261;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xB1Au,
      L"CEventNotificationService::StoreRemoteManagementProperty",
      L"CBRAEx",
      L"bstrRemoteHostName",
      -2147467261);
    v11 = !IsDebuggerPresent();
    v12 = L"bstrRemoteHostName";
    if ( v11 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2842,
        L"CEventNotificationService::StoreRemoteManagementProperty",
        L"CBRAEx",
        L"bstrRemoteHostName",
        -2147467261);
      goto LABEL_68;
    }
    LODWORD(phkResult) = -2147467261;
    v13 = 2842;
LABEL_7:
    lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)v12;
LABEL_8:
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v13,
      L"CEventNotificationService::StoreRemoteManagementProperty",
      L"CBRAEx",
      lpSecurityAttributes,
      phkResult);
    goto LABEL_68;
  }
  if ( CEventNotificationService::m_sShutdownInProgress )
  {
    v10 = -2147023781;
    goto LABEL_68;
  }
  v14 = L"Software\\Microsoft\\Windows MultiPoint Server\\Managed Servers";
  if ( a2 )
    v14 = L"Software\\Microsoft\\Windows MultiPoint Server\\Managed By Servers";
  v15 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v10 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xB1Eu,
      L"CEventNotificationService::StoreRemoteManagementProperty",
      L"CBRAEx",
      L"err == 0L",
      v10);
    if ( IsDebuggerPresent() )
    {
      LODWORD(phkResult) = v10;
      v13 = 2846;
      lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)L"err == 0L";
      goto LABEL_8;
    }
    v16 = 2846;
LABEL_67:
    LODWORD(lpSecurityAttributesa) = v10;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v16,
      L"CEventNotificationService::StoreRemoteManagementProperty",
      L"CBRAEx",
      L"err == 0L",
      lpSecurityAttributesa);
    goto LABEL_68;
  }
  v17 = RegCreateKeyExW(hKey, a3, 0, 0, 0, 0xF003Fu, 0, &v31, 0);
  v10 = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xB21u,
      L"CEventNotificationService::StoreRemoteManagementProperty",
      L"CBRAEx",
      L"err == 0L",
      v10);
    if ( IsDebuggerPresent() )
    {
      LODWORD(phkResult) = v10;
      v13 = 2849;
      lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)L"err == 0L";
      goto LABEL_8;
    }
    v16 = 2849;
    goto LABEL_67;
  }
  switch ( a4 )
  {
    case 0u:
      if ( !a2 )
        goto LABEL_59;
      v22 = L"eType == WRMT_Manager";
      v10 = -2147024809;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0xB38u,
        L"CEventNotificationService::StoreRemoteManagementProperty",
        L"CBRAEx",
        L"eType == WRMT_Manager",
        -2147024809);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(lpSecurityAttributesa) = -2147024809;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          2872,
          L"CEventNotificationService::StoreRemoteManagementProperty",
          L"CBRAEx",
          L"eType == WRMT_Manager",
          lpSecurityAttributesa);
        goto LABEL_68;
      }
      v23 = 2872;
      goto LABEL_41;
    case 2u:
    case 4u:
      if ( varIn->vt == 8 && (bstrVal = varIn->bstrVal) != 0 )
      {
        if ( !a2 )
        {
          v10 = WmsEncrypt(bstrVal, &v32);
          if ( v10 < 0 )
          {
            v5 = v32;
            goto LABEL_68;
          }
          v19 = (HKEY)CEventNotificationService::s_RemoteManagementPropertyValueName(a4);
          v5 = v32;
          v21 = v32;
LABEL_38:
          v10 = RegUtil::SetStringValue((RegUtil *)v31, v19, v21, v20);
          goto LABEL_68;
        }
        v22 = L"eType == WRMT_Manager";
        v10 = -2147024809;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          0xB28u,
          L"CEventNotificationService::StoreRemoteManagementProperty",
          L"CBRAEx",
          L"eType == WRMT_Manager",
          -2147024809);
        if ( !IsDebuggerPresent() )
        {
          LODWORD(lpSecurityAttributesa) = -2147024809;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            2856,
            L"CEventNotificationService::StoreRemoteManagementProperty",
            L"CBRAEx",
            L"eType == WRMT_Manager",
            lpSecurityAttributesa);
          goto LABEL_68;
        }
        v23 = 2856;
      }
      else
      {
        v22 = L"varSetting.vt == VT_BSTR && varSetting.bstrVal != 0";
        v10 = -2147024809;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          0xB27u,
          L"CEventNotificationService::StoreRemoteManagementProperty",
          L"CBRAEx",
          L"varSetting.vt == VT_BSTR && varSetting.bstrVal != 0",
          -2147024809);
        if ( !IsDebuggerPresent() )
        {
          LODWORD(lpSecurityAttributesa) = -2147024809;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            2855,
            L"CEventNotificationService::StoreRemoteManagementProperty",
            L"CBRAEx",
            L"varSetting.vt == VT_BSTR && varSetting.bstrVal != 0",
            lpSecurityAttributesa);
          goto LABEL_68;
        }
        v23 = 2855;
      }
LABEL_41:
      LODWORD(phkResult) = -2147024809;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v23,
        L"CEventNotificationService::StoreRemoteManagementProperty",
        L"CBRAEx",
        v22,
        phkResult);
      goto LABEL_68;
    case 5u:
      if ( varIn->vt == 8 )
      {
        llVal = varIn->llVal;
        if ( llVal )
        {
          v19 = (HKEY)CEventNotificationService::s_RemoteManagementPropertyValueName(5);
          v21 = (unsigned __int16 *)llVal;
          goto LABEL_38;
        }
      }
      v22 = L"varSetting.vt == VT_BSTR && varSetting.bstrVal != 0";
      v10 = -2147024809;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0xB32u,
        L"CEventNotificationService::StoreRemoteManagementProperty",
        L"CBRAEx",
        L"varSetting.vt == VT_BSTR && varSetting.bstrVal != 0",
        -2147024809);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(lpSecurityAttributesa) = -2147024809;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          2866,
          L"CEventNotificationService::StoreRemoteManagementProperty",
          L"CBRAEx",
          L"varSetting.vt == VT_BSTR && varSetting.bstrVal != 0",
          lpSecurityAttributesa);
        goto LABEL_68;
      }
      v23 = 2866;
      goto LABEL_41;
  }
  if ( a4 != 6 )
  {
    v10 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xB43u,
      L"CEventNotificationService::StoreRemoteManagementProperty",
      L"CBRAEx",
      L"0",
      -2147024809);
    v11 = !IsDebuggerPresent();
    v12 = L"0";
    if ( v11 )
    {
      LODWORD(lpSecurityAttributesa) = -2147024809;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        2883,
        L"CEventNotificationService::StoreRemoteManagementProperty",
        L"CBRAEx",
        L"0",
        lpSecurityAttributesa);
      goto LABEL_68;
    }
    LODWORD(phkResult) = -2147024809;
    v13 = 2883;
    goto LABEL_7;
  }
LABEL_59:
  v10 = VariantToUInt32(varIn, &pulRet);
  if ( v10 >= 0 )
  {
    v25 = (const WCHAR *)CEventNotificationService::s_RemoteManagementPropertyValueName(a4);
    v26 = RegSetValueExW(v31, v25, 0, 4u, (const BYTE *)&pulRet, 4u);
    if ( v26 )
    {
      if ( v26 > 0 )
        v10 = (unsigned __int16)v26 | 0x80070000;
      else
        v10 = v26;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0xB3Fu,
        L"CEventNotificationService::StoreRemoteManagementProperty",
        L"CBRAEx",
        L"err == 0L",
        v10);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = v10;
        v13 = 2879;
        lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)L"err == 0L";
        goto LABEL_8;
      }
      v16 = 2879;
      goto LABEL_67;
    }
  }
LABEL_68:
  operator delete(v5);
  if ( v31 )
  {
    RegCloseKey(v31);
    v31 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140025c30  push    rbp
0x140025c32  push    rbx
0x140025c33  push    rsi
0x140025c34  push    rdi
0x140025c35  push    r12
0x140025c37  push    r13
0x140025c39  push    r14
0x140025c3b  push    r15
0x140025c3d  mov     rbp, rsp
0x140025c40  sub     rsp, 78h
0x140025c44  xor     r13d, r13d
0x140025c47  mov     [rbp+hKey], 0
0x140025c4f  mov     esi, edx
0x140025c51  mov     [rbp+var_28], 0
0x140025c59  xor     edx, edx
0x140025c5b  mov     [rbp+pulRet], 0
0x140025c62  mov     edi, r9d
0x140025c65  mov     [rbp+var_20], r13
0x140025c69  lea     r12d, [r13+2]
0x140025c6d  mov     r14, r8
0x140025c70  mov     ecx, r12d
0x140025c73  cmp     r9d, r12d
0x140025c76  jz      short loc_140025C7B
0x140025c78  lea     ecx, [rdx+1]
0x140025c7b  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x140025c80  mov     ebx, eax
0x140025c82  test    eax, eax
0x140025c84  js      loc_140026250
0x140025c8a  test    r14, r14
0x140025c8d  jnz     loc_140025D23
0x140025c93  lea     rax, aBstrremotehost; "bstrRemoteHostName"
0x140025c9a  mov     ebx, 80004003h
0x140025c9f  lea     r14, aCbraex; "CBRAEx"
0x140025ca6  mov     [rsp+78h+samDesired], ebx; int
0x140025caa  lea     rsi, aCeventnotifica_181; "CEventNotificationService::StoreRemoteM"...
0x140025cb1  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned __int16 *
0x140025cb6  mov     r15d, 0B1Ah
0x140025cbc  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140025cc3  mov     r9, r14; unsigned __int16 *
0x140025cc6  mov     r8, rsi; unsigned __int16 *
0x140025cc9  mov     edx, r15d; unsigned int
0x140025ccc  mov     rcx, rdi; unsigned __int16 *
0x140025ccf  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140025cd4  call    cs:__imp_IsDebuggerPresent
0x140025cda  test    eax, eax
0x140025cdc  lea     rax, aBstrremotehost; "bstrRemoteHostName"
0x140025ce3  jz      short loc_140025D12
0x140025ce5  mov     dword ptr [rsp+78h+phkResult], ebx
0x140025ce9  mov     r9d, r15d
0x140025cec  mov     [rsp+78h+lpSecurityAttributes], rax
0x140025cf1  mov     ecx, r12d; unsigned __int8
0x140025cf4  mov     qword ptr [rsp+78h+samDesired], r14
0x140025cf9  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140025d00  mov     r8, rdi
0x140025d03  mov     qword ptr [rsp+78h+dwOptions], rsi
0x140025d08  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140025d0d  jmp     loc_140026250
0x140025d12  mov     dword ptr [rsp+78h+lpSecurityAttributes], ebx
0x140025d16  mov     r8d, r15d
0x140025d19  mov     qword ptr [rsp+78h+samDesired], rax
0x140025d1e  jmp     loc_140026239
0x140025d23  cmp     cs:?m_sShutdownInProgress@CEventNotificationService@@2HA, r13d; int CEventNotificationService::m_sShutdownInProgress
0x140025d2a  jz      short loc_140025D36
0x140025d2c  mov     ebx, 8007045Bh
0x140025d31  jmp     loc_140026250
0x140025d36  mov     [rsp+78h+lpdwDisposition], r13; lpdwDisposition
0x140025d3b  lea     rax, aSoftwareMicros_2; "Software\\Microsoft\\Windows MultiPoint"...
0x140025d42  test    esi, esi
0x140025d44  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows MultiPoint"...
0x140025d4b  mov     r15d, 0F003Fh
0x140025d51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140025d58  cmovnz  rdx, rax; lpSubKey
0x140025d5c  lea     rax, [rbp+hKey]
0x140025d60  mov     [rsp+78h+phkResult], rax; phkResult
0x140025d65  xor     r9d, r9d; lpClass
0x140025d68  mov     [rsp+78h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140025d6d  xor     r8d, r8d; Reserved
0x140025d70  mov     [rsp+78h+samDesired], r15d; samDesired
0x140025d75  mov     [rsp+78h+dwOptions], r13d; dwOptions
0x140025d7a  call    cs:__imp_RegCreateKeyExW
0x140025d80  mov     ebx, eax
0x140025d82  test    eax, eax
0x140025d84  jz      short loc_140025DF2
0x140025d86  jle     short loc_140025D91
0x140025d88  movzx   ebx, ax
0x140025d8b  or      ebx, 80070000h
0x140025d91  lea     r14, aCbraex; "CBRAEx"
0x140025d98  mov     [rsp+78h+samDesired], ebx; int
0x140025d9c  lea     rsi, aCeventnotifica_181; "CEventNotificationService::StoreRemoteM"...
0x140025da3  mov     r9, r14; unsigned __int16 *
0x140025da6  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140025dad  mov     r8, rsi; unsigned __int16 *
0x140025db0  lea     r15, aErr0l; "err == 0L"
0x140025db7  mov     rcx, rdi; unsigned __int16 *
0x140025dba  mov     edx, 0B1Eh; unsigned int
0x140025dbf  mov     qword ptr [rsp+78h+dwOptions], r15; unsigned __int16 *
0x140025dc4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140025dc9  call    cs:__imp_IsDebuggerPresent
0x140025dcf  test    eax, eax
0x140025dd1  jz      short loc_140025DE7
0x140025dd3  mov     dword ptr [rsp+78h+phkResult], ebx
0x140025dd7  mov     r9d, 0B1Eh
0x140025ddd  mov     [rsp+78h+lpSecurityAttributes], r15
0x140025de2  jmp     loc_140025CF1
0x140025de7  mov     r8d, 0B1Eh
0x140025ded  jmp     loc_140026230
0x140025df2  mov     rcx, [rbp+hKey]; hKey
0x140025df6  lea     rax, [rbp+var_28]
0x140025dfa  mov     [rsp+78h+lpdwDisposition], r13; lpdwDisposition
0x140025dff  xor     r9d, r9d; lpClass
0x140025e02  mov     [rsp+78h+phkResult], rax; phkResult
0x140025e07  xor     r8d, r8d; Reserved
0x140025e0a  mov     [rsp+78h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140025e0f  mov     rdx, r14; lpSubKey
0x140025e12  mov     [rsp+78h+samDesired], r15d; samDesired
0x140025e17  mov     [rsp+78h+dwOptions], r13d; dwOptions
0x140025e1c  call    cs:__imp_RegCreateKeyExW
0x140025e22  mov     ebx, eax
0x140025e24  test    eax, eax
0x140025e26  jz      short loc_140025E94
0x140025e28  jle     short loc_140025E33
0x140025e2a  movzx   ebx, ax
0x140025e2d  or      ebx, 80070000h
0x140025e33  lea     r14, aCbraex; "CBRAEx"
0x140025e3a  mov     [rsp+78h+samDesired], ebx; int
0x140025e3e  lea     rsi, aCeventnotifica_181; "CEventNotificationService::StoreRemoteM"...
0x140025e45  mov     r9, r14; unsigned __int16 *
0x140025e48  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140025e4f  mov     r8, rsi; unsigned __int16 *
0x140025e52  lea     r15, aErr0l; "err == 0L"
0x140025e59  mov     rcx, rdi; unsigned __int16 *
0x140025e5c  mov     edx, 0B21h; unsigned int
0x140025e61  mov     qword ptr [rsp+78h+dwOptions], r15; unsigned __int16 *
0x140025e66  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140025e6b  call    cs:__imp_IsDebuggerPresent
0x140025e71  test    eax, eax
0x140025e73  jz      short loc_140025E89
0x140025e75  mov     dword ptr [rsp+78h+phkResult], ebx
0x140025e79  mov     r9d, 0B21h
0x140025e7f  mov     [rsp+78h+lpSecurityAttributes], r15
0x140025e84  jmp     loc_140025CF1
0x140025e89  mov     r8d, 0B21h
0x140025e8f  jmp     loc_140026230
0x140025e94  mov     ecx, edi
0x140025e96  test    edi, edi
0x140025e98  jz      loc_14002610A
0x140025e9e  sub     ecx, r12d
0x140025ea1  jz      loc_140025FE8
0x140025ea7  sub     ecx, r12d
0x140025eaa  jz      loc_140025FE8
0x140025eb0  sub     ecx, 1
0x140025eb3  jz      loc_140025F3A
0x140025eb9  cmp     ecx, 1
0x140025ebc  jz      loc_14002617A
0x140025ec2  mov     r15d, 80070057h
0x140025ec8  lea     rax, a0; "0"
0x140025ecf  lea     r14, aCbraex; "CBRAEx"
0x140025ed6  mov     [rsp+78h+samDesired], r15d; int
0x140025edb  lea     rsi, aCeventnotifica_181; "CEventNotificationService::StoreRemoteM"...
0x140025ee2  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned __int16 *
0x140025ee7  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140025eee  mov     r9, r14; unsigned __int16 *
0x140025ef1  mov     r8, rsi; unsigned __int16 *
0x140025ef4  mov     rcx, rdi; unsigned __int16 *
0x140025ef7  mov     edx, 0B43h; unsigned int
0x140025efc  mov     ebx, r15d
0x140025eff  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140025f04  call    cs:__imp_IsDebuggerPresent
0x140025f0a  test    eax, eax
0x140025f0c  lea     rax, a0; "0"
0x140025f13  jz      short loc_140025F25
0x140025f15  mov     dword ptr [rsp+78h+phkResult], r15d
0x140025f1a  mov     r9d, 0B43h
0x140025f20  jmp     loc_140025CEC
0x140025f25  mov     dword ptr [rsp+78h+lpSecurityAttributes], r15d
0x140025f2a  mov     r8d, 0B43h
0x140025f30  mov     qword ptr [rsp+78h+samDesired], rax
0x140025f35  jmp     loc_140026239
0x140025f3a  mov     rax, [rbp+varIn]
0x140025f3e  cmp     word ptr [rax], 8
0x140025f42  jnz     short loc_140025F6D
0x140025f44  mov     rbx, [rax+8]
0x140025f48  test    rbx, rbx
0x140025f4b  jz      short loc_140025F6D
0x140025f4d  mov     ecx, 5
0x140025f52  call    ?s_RemoteManagementPropertyValueName@CEventNotificationService@@SAPEBGW4__MIDL___MIDL_itf_wmssvc_0000_0000_0032@@@Z; CEventNotificationService::s_RemoteManagementPropertyValueName(__MIDL___MIDL_itf_wmssvc_0000_0000_0032)
0x140025f57  mov     r8, rbx; unsigned __int16 *
0x140025f5a  mov     rcx, [rbp+var_28]; this
0x140025f5e  mov     rdx, rax; HKEY
0x140025f61  call    ?SetStringValue@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z; RegUtil::SetStringValue(HKEY__ *,ushort const *,ushort const *)
0x140025f66  mov     ebx, eax
0x140025f68  jmp     loc_140026250
0x140025f6d  mov     r15d, 80070057h
0x140025f73  lea     r14, aCbraex; "CBRAEx"
0x140025f7a  lea     rsi, aCeventnotifica_181; "CEventNotificationService::StoreRemoteM"...
0x140025f81  mov     [rsp+78h+samDesired], r15d; int
0x140025f86  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140025f8d  mov     r9, r14; unsigned __int16 *
0x140025f90  lea     r12, aVarsettingVtVt; "varSetting.vt == VT_BSTR && varSetting."...
0x140025f97  mov     r8, rsi; unsigned __int16 *
0x140025f9a  mov     rcx, rdi; unsigned __int16 *
0x140025f9d  mov     qword ptr [rsp+78h+dwOptions], r12; unsigned __int16 *
0x140025fa2  mov     edx, 0B32h; unsigned int
0x140025fa7  mov     ebx, r15d
0x140025faa  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140025faf  call    cs:__imp_IsDebuggerPresent
0x140025fb5  test    eax, eax
0x140025fb7  jz      short loc_140025FD3
0x140025fb9  mov     r9d, 0B32h
0x140025fbf  mov     dword ptr [rsp+78h+phkResult], r15d
0x140025fc4  mov     ecx, 2
0x140025fc9  mov     [rsp+78h+lpSecurityAttributes], r12
0x140025fce  jmp     loc_140025CF4
0x140025fd3  mov     dword ptr [rsp+78h+lpSecurityAttributes], r15d
0x140025fd8  mov     r8d, 0B32h
0x140025fde  mov     qword ptr [rsp+78h+samDesired], r12
0x140025fe3  jmp     loc_140026239
0x140025fe8  mov     rax, [rbp+varIn]
0x140025fec  cmp     word ptr [rax], 8
0x140025ff0  jnz     loc_14002609E
0x140025ff6  mov     rcx, [rax+8]; unsigned __int16 *
0x140025ffa  test    rcx, rcx
0x140025ffd  jz      loc_14002609E
0x140026003  test    esi, esi
0x140026005  jz      short loc_140026073
0x140026007  mov     r15d, 80070057h
0x14002600d  lea     r14, aCbraex; "CBRAEx"
0x140026014  lea     rsi, aCeventnotifica_181; "CEventNotificationService::StoreRemoteM"...
0x14002601b  mov     [rsp+78h+samDesired], r15d; int
0x140026020  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140026027  mov     r9, r14; unsigned __int16 *
0x14002602a  lea     r12, aEtypeWrmtManag; "eType == WRMT_Manager"
0x140026031  mov     r8, rsi; unsigned __int16 *
0x140026034  mov     rcx, rdi; unsigned __int16 *
0x140026037  mov     qword ptr [rsp+78h+dwOptions], r12; unsigned __int16 *
0x14002603c  mov     edx, 0B28h; unsigned int
0x140026041  mov     ebx, r15d
0x140026044  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140026049  call    cs:__imp_IsDebuggerPresent
0x14002604f  test    eax, eax
0x140026051  jz      short loc_14002605E
0x140026053  mov     r9d, 0B28h
0x140026059  jmp     loc_140025FBF
0x14002605e  mov     dword ptr [rsp+78h+lpSecurityAttributes], r15d
0x140026063  mov     r8d, 0B28h
0x140026069  mov     qword ptr [rsp+78h+samDesired], r12
0x14002606e  jmp     loc_140026239
0x140026073  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x140026077  call    ?WmsEncrypt@@YAJPEBGPEAPEAG@Z; WmsEncrypt(ushort const *,ushort * *)
0x14002607c  mov     ebx, eax
0x14002607e  test    eax, eax
0x140026080  js      short loc_140026095
0x140026082  mov     ecx, edi
0x140026084  call    ?s_RemoteManagementPropertyValueName@CEventNotificationService@@SAPEBGW4__MIDL___MIDL_itf_wmssvc_0000_0000_0032@@@Z; CEventNotificationService::s_RemoteManagementPropertyValueName(__MIDL___MIDL_itf_wmssvc_0000_0000_0032)
0x140026089  mov     r13, [rbp+var_20]
0x14002608d  mov     r8, r13
0x140026090  jmp     loc_140025F5A
0x140026095  mov     r13, [rbp+var_20]
0x140026099  jmp     loc_140026250
0x14002609e  mov     r15d, 80070057h
0x1400260a4  lea     r14, aCbraex; "CBRAEx"
0x1400260ab  lea     rsi, aCeventnotifica_181; "CEventNotificationService::StoreRemoteM"...
0x1400260b2  mov     [rsp+78h+samDesired], r15d; int
0x1400260b7  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400260be  mov     r9, r14; unsigned __int16 *
0x1400260c1  lea     r12, aVarsettingVtVt; "varSetting.vt == VT_BSTR && varSetting."...
0x1400260c8  mov     r8, rsi; unsigned __int16 *
0x1400260cb  mov     rcx, rdi; unsigned __int16 *
0x1400260ce  mov     qword ptr [rsp+78h+dwOptions], r12; unsigned __int16 *
0x1400260d3  mov     edx, 0B27h; unsigned int
0x1400260d8  mov     ebx, r15d
0x1400260db  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400260e0  call    cs:__imp_IsDebuggerPresent
0x1400260e6  test    eax, eax
0x1400260e8  jz      short loc_1400260F5
0x1400260ea  mov     r9d, 0B27h
0x1400260f0  jmp     loc_140025FBF
0x1400260f5  mov     dword ptr [rsp+78h+lpSecurityAttributes], r15d
0x1400260fa  mov     r8d, 0B27h
0x140026100  mov     qword ptr [rsp+78h+samDesired], r12
0x140026105  jmp     loc_140026239
0x14002610a  test    esi, esi
0x14002610c  jz      short loc_14002617A
0x14002610e  mov     r15d, 80070057h
0x140026114  lea     r14, aCbraex; "CBRAEx"
0x14002611b  lea     rsi, aCeventnotifica_181; "CEventNotificationService::StoreRemoteM"...
0x140026122  mov     [rsp+78h+samDesired], r15d; int
0x140026127  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14002612e  mov     r9, r14; unsigned __int16 *
0x140026131  lea     r12, aEtypeWrmtManag; "eType == WRMT_Manager"
0x140026138  mov     r8, rsi; unsigned __int16 *
0x14002613b  mov     rcx, rdi; unsigned __int16 *
0x14002613e  mov     qword ptr [rsp+78h+dwOptions], r12; unsigned __int16 *
0x140026143  mov     edx, 0B38h; unsigned int
0x140026148  mov     ebx, r15d
0x14002614b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140026150  call    cs:__imp_IsDebuggerPresent
0x140026156  test    eax, eax
0x140026158  jz      short loc_140026165
0x14002615a  mov     r9d, 0B38h
  ... truncated ...
```
