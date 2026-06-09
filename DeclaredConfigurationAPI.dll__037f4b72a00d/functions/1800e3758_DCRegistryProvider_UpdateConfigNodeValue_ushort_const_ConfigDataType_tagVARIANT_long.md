# DCRegistryProvider::UpdateConfigNodeValue(ushort const *,ConfigDataType,tagVARIANT,long *)

- ea: `0x1800e3758`
- end: `0x1800e40b1`
- name: `?UpdateConfigNodeValue@DCRegistryProvider@@QEAAJPEBGW4ConfigDataType@@UtagVARIANT@@PEAJ@Z`
- size: `2393`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800e4848`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x1800143c8`
- `0x180018ac0`
- `0x180019270`
- `0x1800192f8`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18004babc`
- `0x1800e306c`
- `0x1800e3758`
- `0x1800e40b8`
- `0x1800e419c`
- `0x1800e4290`
- `0x1800e4374`
- `0x1800e453c`
- `0x1800e4620`
- `0x1800e472c`
- `0x180100c90`
- `0x180100e3c`
- `0x180100fd8`
- `0x1801011cc`
- `0x18010136c`
- `0x180102c48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e39d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e3af9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e39d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e3af9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800e3c6f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800e3c6f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800e3c46`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800e3c46`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800e3ca2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800e3ca2`

## string_xrefs

- `0x1800e37b1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e383e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e390c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e3a0a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DCRegistryProvider::UpdateConfigNodeValue(_QWORD *a1, __int64 a2, int a3, __int64 a4, _DWORD *a5)
{
  __int64 v7; // rdx
  HRESULT LBound; // r14d
  int v10; // ecx
  _QWORD *v11; // rdi
  int v12; // ecx
  int v13; // eax
  const WCHAR *v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  const WCHAR *v19; // rdx
  int v20; // eax
  int v21; // r14d
  const unsigned __int16 *v22; // r8
  int v23; // ecx
  _QWORD *v24; // rax
  __int64 *v25; // rdx
  _QWORD *v26; // rax
  __int64 *v27; // rdx
  int v28; // r15d
  DWORD v29; // r15d
  const unsigned __int16 *v30; // r8
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  const unsigned __int16 *v33; // r14
  const unsigned __int16 *v34; // r8
  int v35; // edx
  int v36; // ecx
  __int64 v37; // r14
  const unsigned __int16 *v38; // r8
  int v39; // edx
  int v40; // ecx
  _QWORD *v41; // rax
  _QWORD *v42; // rax
  const unsigned __int16 *v43; // r8
  _QWORD *v44; // rax
  _QWORD *v45; // rax
  int v46; // ecx
  _QWORD *v47; // rdi
  _QWORD *v48; // rax
  int dwOptions; // [rsp+20h] [rbp-168h]
  int dwOptionsa; // [rsp+20h] [rbp-168h]
  int dwOptionsb; // [rsp+20h] [rbp-168h]
  int dwOptionsc; // [rsp+20h] [rbp-168h]
  char dwOptionsd; // [rsp+20h] [rbp-168h]
  char dwOptionse; // [rsp+20h] [rbp-168h]
  __int64 samDesired; // [rsp+28h] [rbp-160h]
  __int64 samDesireda; // [rsp+28h] [rbp-160h]
  char lpSecurityAttributes; // [rsp+30h] [rbp-158h]
  char v58; // [rsp+50h] [rbp-138h] BYREF
  int v59; // [rsp+54h] [rbp-134h] BYREF
  int v60; // [rsp+58h] [rbp-130h] BYREF
  __int64 v61; // [rsp+60h] [rbp-128h] BYREF
  HKEY v62; // [rsp+68h] [rbp-120h] BYREF
  void *ppvData; // [rsp+70h] [rbp-118h] BYREF
  LONG plUbound; // [rsp+78h] [rbp-110h] BYREF
  LONG plLbound; // [rsp+7Ch] [rbp-10Ch] BYREF
  int *v66; // [rsp+80h] [rbp-108h]
  char *v67; // [rsp+88h] [rbp-100h]
  __int64 *v68; // [rsp+90h] [rbp-F8h]
  int *v69; // [rsp+98h] [rbp-F0h]
  _QWORD *v70; // [rsp+A0h] [rbp-E8h]
  char v71; // [rsp+A8h] [rbp-E0h]
  unsigned __int16 *v72[3]; // [rsp+B0h] [rbp-D8h] BYREF
  unsigned __int64 v73; // [rsp+C8h] [rbp-C0h]
  LPCWSTR lpSubKey[3]; // [rsp+D0h] [rbp-B8h] BYREF
  unsigned __int64 v75; // [rsp+E8h] [rbp-A0h]
  _BYTE v76[32]; // [rsp+F0h] [rbp-98h] BYREF
  HKEY *v77; // [rsp+110h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+118h] [rbp-70h] BYREF
  char v79; // [rsp+120h] [rbp-68h]
  _BYTE v80[32]; // [rsp+130h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  ppvData = a1;
  v61 = a2;
  v60 = a3;
  v59 = 0;
  v58 = 0;
  if ( !a2 )
  {
    v7 = 397;
LABEL_3:
    LBound = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)0x80070057LL,
      dwOptionsa);
    return (unsigned int)LBound;
  }
  if ( !a5 )
  {
    v7 = 398;
    goto LABEL_3;
  }
  *a5 = 0;
  v66 = &v59;
  v67 = &v58;
  v68 = &v61;
  v69 = &v60;
  v70 = a1;
  v71 = 1;
  if ( a3 == 8 )
  {
    LBound = -2147024809;
    v59 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)0x80070057LL,
      dwOptionsa);
LABEL_9:
    if ( v59 < 0 && !v58 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
    {
      v11 = a1 + 1;
      if ( v11[3] > 7u )
        v11 = (_QWORD *)*v11;
      McTemplateU0zqzd_EventWriteTransfer(
        v10,
        (unsigned int)EnterpriseDiagnosticsRegistryProviderSetValueFailure,
        v61,
        v60,
        (__int64)v11,
        v59);
    }
    return (unsigned int)LBound;
  }
  std::wstring::wstring((__int64)v76);
  std::wstring::wstring((__int64)lpSubKey);
  std::wstring::wstring((__int64)v72);
  v13 = DCRegistryProvider::ParseFullRegPathUri(v12, v61, (unsigned int)v76, (unsigned int)lpSubKey, (__int64)v72);
  LBound = v13;
  v59 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)(unsigned int)v13,
      dwOptionsb);
LABEL_17:
    std::wstring::_Tidy_deallocate(v72);
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::wstring::_Tidy_deallocate(v76);
    goto LABEL_9;
  }
  v62 = 0;
  if ( (unsigned int)std::wstring::compare(v76, L"device") )
  {
    try
    {
      v17 = std::operator+<unsigned short>(v80, v76, L"\\");
      v18 = std::operator+<unsigned short>(&v77, v17, lpSubKey);
      std::wstring::operator=(lpSubKey, v18);
      std::wstring::_Tidy_deallocate(&v77);
      std::wstring::_Tidy_deallocate(v80);
      v77 = &v62;
      phkResult = 0;
      v79 = 1;
      v19 = (const WCHAR *)lpSubKey;
      if ( v75 > 7 )
        v19 = lpSubKey[0];
      v20 = RegCreateKeyExW(HKEY_USERS, v19, 0, 0, 0, 0x2011Fu, 0, &phkResult, 0);
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v59 = v20;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v77);
    }
    catch ( std::bad_alloc )
    {
      v59 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
        (const char *)0x8007000ELL,
        dwOptions);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(lpSubKey);
      std::wstring::_Tidy_deallocate(v76);
      if ( v59 < 0 && !v58 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      {
        v48 = (char *)ppvData + 8;
        if ( *((_QWORD *)ppvData + 4) > 7u )
          v48 = (_QWORD *)*v48;
        McTemplateU0zqzd_EventWriteTransfer(
          v59,
          (unsigned int)EnterpriseDiagnosticsRegistryProviderSetValueFailure,
          v61,
          v60,
          (__int64)v48,
          v59);
      }
      return 2147942414LL;
    }
    LBound = v59;
    if ( v59 < 0 )
    {
      v16 = 457;
      goto LABEL_25;
    }
  }
  else
  {
    v77 = &v62;
    phkResult = 0;
    v79 = 1;
    v14 = (const WCHAR *)lpSubKey;
    if ( v75 > 7 )
      v14 = lpSubKey[0];
    v15 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 0, 0, 0x2011Fu, 0, &phkResult, 0);
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v59 = v15;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v77);
    LBound = v59;
    if ( v59 < 0 )
    {
      v16 = 434;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
        (const char *)(unsigned int)LBound,
        dwOptionsc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
      goto LABEL_17;
    }
  }
  if ( v60 > 6 )
  {
    switch ( v60 )
    {
      case 7:
        ppvData = 0;
        SafeArrayToMultiString(*(SAFEARRAY **)(a4 + 8), 0, (unsigned __int16 **)&ppvData, 0);
        v33 = (const unsigned __int16 *)ppvData;
        v43 = (const unsigned __int16 *)v72;
        if ( v73 > 7 )
          v43 = v72[0];
        v59 = DCCDNUtil_SetRegistryMultiString(v62, 0, v43, (const BYTE *)ppvData);
        SafeArrayToMultiString(*(SAFEARRAY **)(a4 + 8), 0x7Cu, (unsigned __int16 **)&ppvData, 0);
        if ( v59 < 0 )
        {
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) == 0 )
            goto LABEL_106;
          v36 = v59;
          goto LABEL_103;
        }
LABEL_97:
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
        {
          v44 = a1 + 1;
          if ( a1[4] > 7u )
            v44 = (_QWORD *)*v44;
          McTemplateU0zqzz_EventWriteTransfer(v36, v35, v61, v60, (__int64)v33, (__int64)v44);
        }
        goto LABEL_107;
      case 8:
      case 9:
        goto LABEL_41;
      case 11:
        goto LABEL_83;
    }
    if ( (unsigned int)(v60 - 12) > 1 )
      goto LABEL_41;
LABEL_78:
    v33 = *(const unsigned __int16 **)(a4 + 8);
    v34 = (const unsigned __int16 *)v72;
    if ( v73 > 7 )
      v34 = v72[0];
    v36 = DCCDNUtil_SetRegistryString(v62, 0, v34, v33, v60 == 12);
    v59 = v36;
    if ( v36 < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) == 0 )
        goto LABEL_106;
LABEL_103:
      v45 = a1 + 1;
      if ( a1[4] > 7u )
        v45 = (_QWORD *)*v45;
      McTemplateU0zqzzd_EventWriteTransfer(v36, v35, v61, v60, (__int64)v33, (__int64)v45, v36);
      goto LABEL_106;
    }
    goto LABEL_97;
  }
  switch ( v60 )
  {
    case 6:
      plLbound = 0;
      plUbound = 0;
      LBound = SafeArrayGetLBound(*(SAFEARRAY **)(a4 + 8), 1u, &plLbound);
      v59 = LBound;
      if ( LBound < 0 )
      {
        v16 = 538;
        goto LABEL_25;
      }
      LBound = SafeArrayGetUBound(*(SAFEARRAY **)(a4 + 8), 1u, &plUbound);
      v59 = LBound;
      if ( LBound < 0 )
      {
        v16 = 540;
        goto LABEL_25;
      }
      v28 = plUbound - plLbound;
      ppvData = 0;
      LBound = SafeArrayAccessData(*(SAFEARRAY **)(a4 + 8), &ppvData);
      v59 = LBound;
      if ( LBound < 0 )
      {
        v16 = 547;
        goto LABEL_25;
      }
      v29 = v28 + 1;
      v30 = (const unsigned __int16 *)v72;
      if ( v73 > 7 )
        v30 = v72[0];
      v23 = DCCDNUtil_SetRegistryBinary(v62, 0, v30, (const BYTE *)ppvData, v29);
      v59 = v23;
      if ( v23 >= 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) == 0 )
          goto LABEL_107;
        v31 = a1 + 1;
        if ( a1[4] > 7u )
          v31 = (_QWORD *)*v31;
        samDesired = (__int64)v31;
        dwOptionsd = v29;
        v25 = EnterpriseDiagnosticsRegistryProviderSetBinaryValueSuccess;
        goto LABEL_50;
      }
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      {
        v32 = a1 + 1;
        if ( a1[4] > 7u )
          v32 = (_QWORD *)*v32;
        lpSecurityAttributes = v23;
        samDesireda = (__int64)v32;
        dwOptionse = v29;
        v27 = EnterpriseDiagnosticsRegistryProviderSetBinaryValueFailure;
        goto LABEL_72;
      }
LABEL_106:
      v58 = 1;
      goto LABEL_107;
    case 0:
LABEL_43:
      v21 = *(_DWORD *)(a4 + 8);
      v22 = (const unsigned __int16 *)v72;
      if ( v73 > 7 )
        v22 = v72[0];
      v23 = DCCDNUtil_SetRegistryDWORD(v62, 0, v22, v21);
      v59 = v23;
      if ( v23 >= 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) == 0 )
          goto LABEL_107;
        v24 = a1 + 1;
        if ( a1[4] > 7u )
          v24 = (_QWORD *)*v24;
        samDesired = (__int64)v24;
        dwOptionsd = v21;
        v25 = EnterpriseDiagnosticsRegistryProviderSetIntValueSuccess;
LABEL_50:
        McTemplateU0zqqz_EventWriteTransfer(v23, (_DWORD)v25, v61, v60, dwOptionsd, samDesired);
        goto LABEL_107;
      }
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      {
        v26 = a1 + 1;
        if ( a1[4] > 7u )
          v26 = (_QWORD *)*v26;
        lpSecurityAttributes = v23;
        samDesireda = (__int64)v26;
        dwOptionse = v21;
        v27 = EnterpriseDiagnosticsRegistryProviderSetIntValueFailure;
LABEL_72:
        McTemplateU0zqqzd_EventWriteTransfer(v23, (_DWORD)v27, v61, v60, dwOptionse, samDesireda, lpSecurityAttributes);
        goto LABEL_106;
      }
      goto LABEL_106;
    case 1:
      goto LABEL_78;
    case 2:
LABEL_83:
      v37 = *(_QWORD *)(a4 + 8);
      v38 = (const unsigned __int16 *)v72;
      if ( v73 > 7 )
        v38 = v72[0];
      v40 = DCCDNUtil_SetRegistryQWORD(v62, 0, v38, *(_QWORD *)(a4 + 8));
      v59 = v40;
      if ( v40 >= 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
        {
          v41 = a1 + 1;
          if ( a1[4] > 7u )
            v41 = (_QWORD *)*v41;
          McTemplateU0zqxz_EventWriteTransfer(v40, v39, v61, v60, v37, (__int64)v41);
        }
        goto LABEL_107;
      }
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      {
        v42 = a1 + 1;
        if ( a1[4] > 7u )
          v42 = (_QWORD *)*v42;
        McTemplateU0zqxzd_EventWriteTransfer(v40, v39, v61, v60, v37, (__int64)v42, v40);
      }
      goto LABEL_106;
    case 3:
    case 4:
      v59 = -2147467263;
      goto LABEL_107;
    case 5:
      goto LABEL_43;
  }
LABEL_41:
  v59 = -2147418113;
LABEL_107:
  LBound = v59;
  if ( v59 < 0 )
  {
    v16 = 580;
    goto LABEL_25;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
  std::wstring::_Tidy_deallocate(v72);
  std::wstring::_Tidy_deallocate(lpSubKey);
  std::wstring::_Tidy_deallocate(v76);
  if ( v59 < 0 && !v58 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
  {
    v47 = a1 + 1;
    if ( v47[3] > 7u )
      v47 = (_QWORD *)*v47;
    McTemplateU0zqzd_EventWriteTransfer(
      v46,
      (unsigned int)EnterpriseDiagnosticsRegistryProviderSetValueFailure,
      v61,
      v60,
      (__int64)v47,
      v59);
  }
  return 0;
}

```

## disassembly

```asm
0x1800e3758  push    rbx
0x1800e375a  push    rdi
0x1800e375b  push    r13
0x1800e375d  push    r14
0x1800e375f  push    r15
0x1800e3761  sub     rsp, 160h
0x1800e3768  mov     rax, cs:__security_cookie
0x1800e376f  xor     rax, rsp
0x1800e3772  mov     [rsp+188h+var_38], rax
0x1800e377a  mov     r13, r9
0x1800e377d  mov     rdi, rcx
0x1800e3780  mov     [rsp+188h+ppvData], rcx
0x1800e3785  mov     [rsp+188h+var_128], rdx
0x1800e378a  mov     dword ptr [rsp+188h+var_134+4], r8d
0x1800e378f  mov     rax, [rsp+188h+arg_20]
0x1800e3797  xor     ebx, ebx
0x1800e3799  mov     dword ptr [rsp+188h+var_134], ebx
0x1800e379d  mov     [rsp+188h+var_138], bl
0x1800e37a1  test    rdx, rdx
0x1800e37a4  jnz     short loc_1800E37D0
0x1800e37a6  mov     edx, 18Dh; void *
0x1800e37ab  mov     r14d, 80070057h
0x1800e37b1  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e37b8  mov     r9d, r14d; char *
0x1800e37bb  mov     rcx, [rsp+188h]; this
0x1800e37c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e37c8  mov     eax, r14d
0x1800e37cb  jmp     loc_1800E4091
0x1800e37d0  test    rax, rax
0x1800e37d3  jnz     short loc_1800E37DC
0x1800e37d5  mov     edx, 18Eh
0x1800e37da  jmp     short loc_1800E37AB
0x1800e37dc  mov     [rax], ebx
0x1800e37de  lea     rax, [rsp+188h+var_134]
0x1800e37e3  mov     [rsp+188h+var_108], rax
0x1800e37eb  lea     rax, [rsp+188h+var_138]
0x1800e37f0  mov     [rsp+188h+var_100], rax
0x1800e37f8  lea     rax, [rsp+188h+var_128]
0x1800e37fd  mov     [rsp+188h+var_F8], rax
0x1800e3805  lea     rax, [rsp+188h+var_134+4]
0x1800e380a  mov     [rsp+188h+var_F0], rax
0x1800e3812  mov     [rsp+188h+var_E8], rdi
0x1800e381a  mov     [rsp+188h+var_E0], 1
0x1800e3822  cmp     r8d, 8
0x1800e3826  jnz     short loc_1800E38A5
0x1800e3828  mov     r14d, 80070057h
0x1800e382e  mov     dword ptr [rsp+188h+var_134], r14d
0x1800e3833  mov     rcx, [rsp+188h]; this
0x1800e383b  mov     r9d, r14d; char *
0x1800e383e  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e3845  mov     edx, 19Ch; void *
0x1800e384a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e384f  nop
0x1800e3850  mov     eax, dword ptr [rsp+188h+var_134]
0x1800e3854  test    eax, eax
0x1800e3856  jns     loc_1800E37C8
0x1800e385c  cmp     [rsp+188h+var_138], bl
0x1800e3860  jnz     loc_1800E37C8
0x1800e3866  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1800e386d  jz      loc_1800E37C8
0x1800e3873  add     rdi, 8
0x1800e3877  cmp     qword ptr [rdi+18h], 7
0x1800e387c  jbe     short loc_1800E3881
0x1800e387e  mov     rdi, [rdi]
0x1800e3881  mov     [rsp+188h+samDesired], eax
0x1800e3885  mov     qword ptr [rsp+188h+dwOptions], rdi
0x1800e388a  mov     r9d, dword ptr [rsp+188h+var_134+4]
0x1800e388f  mov     r8, [rsp+188h+var_128]
0x1800e3894  lea     rdx, EnterpriseDiagnosticsRegistryProviderSetValueFailure
0x1800e389b  call    McTemplateU0zqzd_EventWriteTransfer
0x1800e38a0  jmp     loc_1800E37C8
0x1800e38a5  lea     rcx, [rsp+188h+var_98]
0x1800e38ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e38b2  nop
0x1800e38b3  lea     rcx, [rsp+188h+lpSubKey]
0x1800e38bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e38c0  nop
0x1800e38c1  lea     rcx, [rsp+188h+var_D8]
0x1800e38c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e38ce  nop
0x1800e38cf  lea     rax, [rsp+188h+var_D8]
0x1800e38d7  mov     qword ptr [rsp+188h+dwOptions], rax; int
0x1800e38dc  lea     r9, [rsp+188h+lpSubKey]
0x1800e38e4  lea     r8, [rsp+188h+var_98]
0x1800e38ec  mov     rdx, [rsp+188h+var_128]
0x1800e38f1  call    ?ParseFullRegPathUri@DCRegistryProvider@@AEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; DCRegistryProvider::ParseFullRegPathUri(ushort const *,std::wstring &,std::wstring &,std::wstring &)
0x1800e38f6  mov     r14d, eax
0x1800e38f9  mov     dword ptr [rsp+188h+var_134], eax
0x1800e38fd  test    eax, eax
0x1800e38ff  jns     short loc_1800E394C
0x1800e3901  mov     rcx, [rsp+188h]; this
0x1800e3909  mov     r9d, eax; char *
0x1800e390c  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e3913  mov     edx, 1A3h; void *
0x1800e3918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e391d  nop
0x1800e391e  lea     rcx, [rsp+188h+var_D8]
0x1800e3926  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e392b  nop
0x1800e392c  lea     rcx, [rsp+188h+lpSubKey]
0x1800e3934  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3939  nop
0x1800e393a  lea     rcx, [rsp+188h+var_98]
0x1800e3942  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3947  jmp     loc_1800E3850
0x1800e394c  mov     [rsp+188h+var_120], rbx
0x1800e3951  lea     rdx, aDevice_4; "device"
0x1800e3958  lea     rcx, [rsp+188h+var_98]
0x1800e3960  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800e3965  test    eax, eax
0x1800e3967  jnz     loc_1800E3A31
0x1800e396d  lea     rax, [rsp+188h+var_120]
0x1800e3972  mov     [rsp+188h+var_78], rax
0x1800e397a  mov     [rsp+188h+var_70], rbx
0x1800e3982  mov     [rsp+188h+var_68], 1
0x1800e398a  lea     rdx, [rsp+188h+lpSubKey]
0x1800e3992  cmp     [rsp+188h+var_A0], 7
0x1800e399b  cmova   rdx, [rsp+188h+lpSubKey]; lpSubKey
0x1800e39a4  mov     [rsp+188h+lpdwDisposition], rbx; lpdwDisposition
0x1800e39a9  lea     rax, [rsp+188h+var_70]
0x1800e39b1  mov     [rsp+188h+phkResult], rax; phkResult
0x1800e39b6  mov     [rsp+188h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800e39bb  mov     [rsp+188h+samDesired], 2011Fh; samDesired
0x1800e39c3  mov     [rsp+188h+dwOptions], ebx; int
0x1800e39c7  xor     r9d, r9d; lpClass
0x1800e39ca  xor     r8d, r8d; Reserved
0x1800e39cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e39d4  call    cs:__imp_RegCreateKeyExW
0x1800e39da  test    eax, eax
0x1800e39dc  jle     short loc_1800E39E6
0x1800e39de  movzx   eax, ax
0x1800e39e1  or      eax, 80070000h
0x1800e39e6  mov     dword ptr [rsp+188h+var_134], eax
0x1800e39ea  lea     rcx, [rsp+188h+var_78]
0x1800e39f2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800e39f7  mov     r14d, dword ptr [rsp+188h+var_134]
0x1800e39fc  test    r14d, r14d
0x1800e39ff  jns     loc_1800E3B30
0x1800e3a05  mov     edx, 1B2h; void *
0x1800e3a0a  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e3a11  mov     r9d, r14d; char *
0x1800e3a14  mov     rcx, [rsp+188h]; this
0x1800e3a1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3a21  nop
0x1800e3a22  lea     rcx, [rsp+188h+var_120]
0x1800e3a27  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e3a2c  jmp     loc_1800E391E
0x1800e3a31  lea     r8, StringValue; "\\"
0x1800e3a38  lea     rdx, [rsp+188h+var_98]
0x1800e3a40  lea     rcx, [rsp+188h+var_58]
0x1800e3a48  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800e3a4d  nop
0x1800e3a4e  lea     r8, [rsp+188h+lpSubKey]
0x1800e3a56  mov     rdx, rax
0x1800e3a59  lea     rcx, [rsp+188h+var_78]
0x1800e3a61  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800e3a66  mov     rdx, rax
0x1800e3a69  lea     rcx, [rsp+188h+lpSubKey]
0x1800e3a71  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e3a76  lea     rcx, [rsp+188h+var_78]
0x1800e3a7e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3a83  nop
0x1800e3a84  lea     rcx, [rsp+188h+var_58]
0x1800e3a8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3a91  nop
0x1800e3a92  lea     rax, [rsp+188h+var_120]
0x1800e3a97  mov     [rsp+188h+var_78], rax
0x1800e3a9f  mov     [rsp+188h+var_70], rbx
0x1800e3aa7  mov     [rsp+188h+var_68], 1
0x1800e3aaf  lea     rdx, [rsp+188h+lpSubKey]
0x1800e3ab7  cmp     [rsp+188h+var_A0], 7
0x1800e3ac0  cmova   rdx, [rsp+188h+lpSubKey]; lpSubKey
0x1800e3ac9  mov     [rsp+188h+lpdwDisposition], rbx; lpdwDisposition
0x1800e3ace  lea     rax, [rsp+188h+var_70]
0x1800e3ad6  mov     [rsp+188h+phkResult], rax; phkResult
0x1800e3adb  mov     [rsp+188h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800e3ae0  mov     [rsp+188h+samDesired], 2011Fh; samDesired
0x1800e3ae8  mov     [rsp+188h+dwOptions], ebx; dwOptions
0x1800e3aec  xor     r9d, r9d; lpClass
0x1800e3aef  xor     r8d, r8d; Reserved
0x1800e3af2  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800e3af9  call    cs:__imp_RegCreateKeyExW
0x1800e3aff  test    eax, eax
0x1800e3b01  jle     short loc_1800E3B0B
0x1800e3b03  movzx   eax, ax
0x1800e3b06  or      eax, 80070000h
0x1800e3b0b  mov     dword ptr [rsp+188h+var_134], eax
0x1800e3b0f  lea     rcx, [rsp+188h+var_78]
0x1800e3b17  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800e3b1c  mov     r14d, dword ptr [rsp+188h+var_134]
0x1800e3b21  test    r14d, r14d
0x1800e3b24  jns     short loc_1800E3B30
0x1800e3b26  mov     edx, 1C9h
0x1800e3b2b  jmp     loc_1800E3A0A
0x1800e3b30  mov     edx, dword ptr [rsp+188h+var_134+4]
0x1800e3b34  cmp     edx, 6
0x1800e3b37  jg      loc_1800E3D6F
0x1800e3b3d  jz      loc_1800E3C30
0x1800e3b43  mov     ecx, edx
0x1800e3b45  test    edx, edx
0x1800e3b47  jz      short loc_1800E3B84
0x1800e3b49  sub     ecx, 1
0x1800e3b4c  jz      loc_1800E3D9F
0x1800e3b52  sub     ecx, 1
0x1800e3b55  jz      loc_1800E3DF6
0x1800e3b5b  sub     ecx, 1
0x1800e3b5e  jz      short loc_1800E3B77
0x1800e3b60  sub     ecx, 1
0x1800e3b63  jz      short loc_1800E3B77
0x1800e3b65  cmp     ecx, 1
0x1800e3b68  jz      short loc_1800E3B84
0x1800e3b6a  mov     dword ptr [rsp+188h+var_134], 8000FFFFh
0x1800e3b72  jmp     loc_1800E3F78
0x1800e3b77  mov     dword ptr [rsp+188h+var_134], 80004001h
0x1800e3b7f  jmp     loc_1800E3F78
0x1800e3b84  mov     r14d, [r13+8]
0x1800e3b88  lea     r8, [rsp+188h+var_D8]
0x1800e3b90  cmp     [rsp+188h+var_C0], 7
0x1800e3b99  cmova   r8, [rsp+188h+var_D8]; unsigned __int16 *
0x1800e3ba2  mov     r9d, r14d; unsigned int
0x1800e3ba5  xor     edx, edx; unsigned __int16 *
0x1800e3ba7  mov     rcx, [rsp+188h+var_120]; HKEY
0x1800e3bac  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800e3bb1  mov     ecx, eax
0x1800e3bb3  mov     dword ptr [rsp+188h+var_134], eax
0x1800e3bb7  test    eax, eax
0x1800e3bb9  js      short loc_1800E3BFB
0x1800e3bbb  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x1800e3bc2  jz      loc_1800E3F78
0x1800e3bc8  lea     rax, [rdi+8]
0x1800e3bcc  cmp     qword ptr [rax+18h], 7
0x1800e3bd1  jbe     short loc_1800E3BD6
0x1800e3bd3  mov     rax, [rax]
0x1800e3bd6  mov     qword ptr [rsp+188h+samDesired], rax
0x1800e3bdb  mov     [rsp+188h+dwOptions], r14d
0x1800e3be0  lea     rdx, EnterpriseDiagnosticsRegistryProviderSetIntValueSuccess
0x1800e3be7  mov     r8, [rsp+188h+var_128]
0x1800e3bec  mov     r9d, dword ptr [rsp+188h+var_134+4]
0x1800e3bf1  call    McTemplateU0zqqz_EventWriteTransfer
0x1800e3bf6  jmp     loc_1800E3F78
0x1800e3bfb  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1800e3c02  jz      loc_1800E3F73
0x1800e3c08  lea     rax, [rdi+8]
0x1800e3c0c  cmp     qword ptr [rax+18h], 7
0x1800e3c11  jbe     short loc_1800E3C16
0x1800e3c13  mov     rax, [rax]
0x1800e3c16  mov     dword ptr [rsp+188h+lpSecurityAttributes], ecx
0x1800e3c1a  mov     qword ptr [rsp+188h+samDesired], rax
0x1800e3c1f  mov     [rsp+188h+dwOptions], r14d
0x1800e3c24  lea     rdx, EnterpriseDiagnosticsRegistryProviderSetIntValueFailure
0x1800e3c2b  jmp     loc_1800E3D5B
0x1800e3c30  mov     [rsp+188h+plLbound], ebx
0x1800e3c34  mov     [rsp+188h+plUbound], ebx
0x1800e3c38  lea     r8, [rsp+188h+plLbound]; plLbound
0x1800e3c3d  mov     edx, 1; nDim
0x1800e3c42  mov     rcx, [r13+8]; psa
0x1800e3c46  call    cs:__imp_SafeArrayGetLBound
0x1800e3c4c  mov     r14d, eax
0x1800e3c4f  mov     dword ptr [rsp+188h+var_134], eax
0x1800e3c53  test    eax, eax
0x1800e3c55  jns     short loc_1800E3C61
0x1800e3c57  mov     edx, 21Ah
0x1800e3c5c  jmp     loc_1800E3A0A
0x1800e3c61  lea     r8, [rsp+188h+plUbound]; plUbound
0x1800e3c66  mov     edx, 1; nDim
0x1800e3c6b  mov     rcx, [r13+8]; psa
0x1800e3c6f  call    cs:__imp_SafeArrayGetUBound
0x1800e3c75  mov     r14d, eax
0x1800e3c78  mov     dword ptr [rsp+188h+var_134], eax
0x1800e3c7c  test    eax, eax
0x1800e3c7e  jns     short loc_1800E3C8A
0x1800e3c80  mov     edx, 21Ch
0x1800e3c85  jmp     loc_1800E3A0A
0x1800e3c8a  mov     r15d, [rsp+188h+plUbound]
0x1800e3c8f  sub     r15d, [rsp+188h+plLbound]
0x1800e3c94  mov     [rsp+188h+ppvData], rbx
0x1800e3c99  lea     rdx, [rsp+188h+ppvData]; ppvData
0x1800e3c9e  mov     rcx, [r13+8]; psa
0x1800e3ca2  call    cs:__imp_SafeArrayAccessData
0x1800e3ca8  mov     r14d, eax
0x1800e3cab  mov     dword ptr [rsp+188h+var_134], eax
0x1800e3caf  test    eax, eax
0x1800e3cb1  jns     short loc_1800E3CBD
0x1800e3cb3  mov     edx, 223h
0x1800e3cb8  jmp     loc_1800E3A0A
0x1800e3cbd  inc     r15d
0x1800e3cc0  lea     r8, [rsp+188h+var_D8]
0x1800e3cc8  cmp     [rsp+188h+var_C0], 7
0x1800e3cd1  cmova   r8, [rsp+188h+var_D8]; unsigned __int16 *
0x1800e3cda  mov     [rsp+188h+dwOptions], r15d; unsigned int
0x1800e3cdf  mov     r9, [rsp+188h+ppvData]; void *
0x1800e3ce4  xor     edx, edx; unsigned __int16 *
0x1800e3ce6  mov     rcx, [rsp+188h+var_120]; HKEY
0x1800e3ceb  call    ?DCCDNUtil_SetRegistryBinary@@YAJPEAUHKEY__@@PEBG1PEAXK@Z; DCCDNUtil_SetRegistryBinary(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x1800e3cf0  mov     ecx, eax
0x1800e3cf2  mov     dword ptr [rsp+188h+var_134], eax
0x1800e3cf6  test    eax, eax
0x1800e3cf8  js      short loc_1800E3D2B
0x1800e3cfa  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x1800e3d01  jz      loc_1800E3F78
  ... truncated ...
```
