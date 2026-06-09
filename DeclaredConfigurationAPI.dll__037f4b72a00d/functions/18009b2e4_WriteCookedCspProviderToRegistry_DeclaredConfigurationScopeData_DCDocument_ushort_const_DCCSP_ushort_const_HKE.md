# WriteCookedCspProviderToRegistry(DeclaredConfigurationScopeData *,DCDocument *,ushort const *,DCCSP *,ushort const *,HKEY__ *)

- ea: `0x18009b2e4`
- end: `0x18009badf`
- name: `?WriteCookedCspProviderToRegistry@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEBGPEAVDCCSP@@2PEAUHKEY__@@@Z`
- size: `2043`
- prototype: `int(struct DeclaredConfigurationScopeData *, struct DCDocument *, const unsigned __int16 *, struct DCCSP *, const unsigned __int16 *, HKEY)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009bae8`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180019208`
- `0x1800192b4`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18001db48`
- `0x18001dea8`
- `0x180056c10`
- `0x180086c10`
- `0x18009b2e4`
- `0x18009d6dc`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180100e3c`
- `0x18010136c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009b6bb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009b761`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009b6bb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009b761`
- `OLEAUT32!__imp_VariantInit` at `0x18009b524`
- `OLEAUT32!__imp_VariantInit` at `0x18009b524`
- `OLEAUT32!__imp_VariantClear` at `0x18009b595`
- `OLEAUT32!__imp_VariantClear` at `0x18009ba8c`
- `OLEAUT32!__imp_VariantClear` at `0x18009b595`
- `OLEAUT32!__imp_VariantClear` at `0x18009ba8c`

## string_xrefs

- `0x18009b503`: `UriCount`
- `0x18009b55c`: `UriCount`
- `0x18009b800`: `ResourceSuccessUri`
- `0x18009b8bc`: `ResourceFailureUri`
- `0x18009b978`: `ResourceInProgressUri`
- `0x18009b4cd`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009b5e7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009b6ec`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009b792`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009ba32`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009b3a8`: `WriteCookedURIToRegistry`
- `0x18009b3af`: `WriteCookedCspProviderToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WriteCookedCspProviderToRegistry(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 ***a4,
        unsigned __int16 *a5,
        HKEY hKey)
{
  struct DCCSP *v6; // r14
  int v8; // r13d
  const unsigned __int16 **v9; // rsi
  const unsigned __int16 **v10; // r14
  _QWORD *v11; // rax
  int v12; // r8d
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rax
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  signed int v19; // esi
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // rdx
  __int64 v23; // rdx
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // r8
  const unsigned __int16 *v26; // rdx
  int v27; // eax
  unsigned __int64 v28; // r9
  __int64 v29; // rdx
  const unsigned __int16 *v30; // rdx
  int v31; // eax
  const WCHAR *v32; // rdx
  LSTATUS v33; // eax
  LSTATUS v34; // eax
  const struct ResourceValidationUrisAndValues *v35; // rsi
  const struct ResourceValidationUrisAndValues *v36; // r15
  const unsigned __int16 *v37; // r9
  const unsigned __int16 *v38; // rdx
  int v39; // r14d
  const unsigned __int16 *v40; // r9
  const unsigned __int16 *v41; // rdx
  const unsigned __int16 *v42; // r9
  const unsigned __int16 *v43; // rdx
  const unsigned __int16 *v44; // r9
  const unsigned __int16 *v45; // rdx
  const unsigned __int16 *v46; // r9
  const unsigned __int16 *v47; // rdx
  const unsigned __int16 *v48; // r9
  const unsigned __int16 *v49; // rdx
  __int64 v50; // rdx
  int dwOptions; // [rsp+20h] [rbp-1C8h]
  int dwOptionsa; // [rsp+20h] [rbp-1C8h]
  int dwOptionsb; // [rsp+20h] [rbp-1C8h]
  int dwOptionsc; // [rsp+20h] [rbp-1C8h]
  int dwOptionsd; // [rsp+20h] [rbp-1C8h]
  int dwOptionse; // [rsp+20h] [rbp-1C8h]
  HKEY v57; // [rsp+50h] [rbp-198h] BYREF
  HKEY v58; // [rsp+58h] [rbp-190h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-188h] BYREF
  struct DCCSP *v60; // [rsp+78h] [rbp-170h]
  struct DeclaredConfigurationScopeData *v61; // [rsp+80h] [rbp-168h]
  LPCWSTR lpSubKey[3]; // [rsp+88h] [rbp-160h] BYREF
  unsigned __int64 v63; // [rsp+A0h] [rbp-148h]
  HKEY *v64; // [rsp+A8h] [rbp-140h] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp-138h] BYREF
  char v66; // [rsp+B8h] [rbp-130h]
  unsigned __int16 *v67[3]; // [rsp+D0h] [rbp-118h] BYREF
  unsigned __int64 v68; // [rsp+E8h] [rbp-100h]
  unsigned __int16 *v69[4]; // [rsp+F0h] [rbp-F8h] BYREF
  unsigned __int16 *v70[4]; // [rsp+110h] [rbp-D8h] BYREF
  unsigned __int16 *v71[4]; // [rsp+130h] [rbp-B8h] BYREF
  unsigned __int16 *v72[4]; // [rsp+150h] [rbp-98h] BYREF
  unsigned __int16 *v73[4]; // [rsp+170h] [rbp-78h] BYREF
  _BYTE v74[32]; // [rsp+190h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v6 = (struct DCCSP *)a4;
  v60 = (struct DCCSP *)a4;
  v61 = a1;
  v58 = (HKEY)a5;
  v8 = 1;
  v9 = a4[2];
  if ( v9 != a4[3] )
  {
    v10 = a4[3];
    do
    {
      v11 = std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&v64, v9);
      LODWORD(v57) = WriteCookedURIToRegistry(hKey, (__int64)v11, v12);
      if ( (int)v57 >= 0 )
      {
        ++v8;
      }
      else
      {
        Logger = CDeclaredConfigurationLogger::GetLogger();
        v14 = *v9;
        if ( *((_QWORD *)*v9 + 3) > 7u )
          v14 = *(const unsigned __int16 **)v14;
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          Logger,
          L"WriteCookedCspProviderToRegistry",
          L"WriteCookedURIToRegistry",
          v14,
          (int)v57);
      }
      v9 += 2;
    }
    while ( v9 != v10 );
    v6 = v60;
  }
  std::wstring::wstring((__int64)lpSubKey);
  try
  {
    v15 = std::wstring::wstring((__int64)v74, (__int64)L"cooked\\");
    v16 = std::operator+<unsigned short>(&v64, v15, v58);
    std::wstring::operator=(lpSubKey, v16);
    std::wstring::_Tidy_deallocate(&v64);
    std::wstring::_Tidy_deallocate(v74);
    v17 = (const unsigned __int16 *)lpSubKey;
    if ( v63 > 7 )
      v17 = lpSubKey[0];
    v18 = DCCDNUtil_SetRegistryDWORD(hKey, v17, L"ProviderType", 1u);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C99,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      dwOptions);
    std::wstring::_Tidy_deallocate(lpSubKey);
    return 2147942414LL;
  }
  v19 = v18;
  if ( v18 < 0 )
  {
LABEL_15:
    std::wstring::_Tidy_deallocate(lpSubKey);
    return (unsigned int)v19;
  }
  v21 = (const unsigned __int16 *)((char *)v6 + 88);
  if ( *((_QWORD *)v6 + 14) > 7u )
    v21 = *(const unsigned __int16 **)v21;
  v22 = (const unsigned __int16 *)lpSubKey;
  if ( v63 > 7 )
    v22 = lpSubKey[0];
  v19 = DCCDNUtil_SetRegistryString(hKey, v22, L"csp", v21, 0);
  if ( v19 < 0 )
  {
    v23 = 11429;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v19,
      dwOptionsa);
    goto LABEL_15;
  }
  v24 = (const unsigned __int16 *)lpSubKey;
  if ( v63 > 7 )
    v24 = lpSubKey[0];
  v19 = DCCDNUtil_SetRegistryDWORD(hKey, v24, L"UriCount", v8);
  if ( v19 < 0 )
  {
    v23 = 11435;
    goto LABEL_22;
  }
  VariantInit(&pvarg);
  pvarg.vt = 3;
  pvarg.lVal = v8;
  v25 = (const unsigned __int16 *)((char *)a2 + 96);
  if ( *((_QWORD *)a2 + 15) > 7u )
    v25 = *(const unsigned __int16 **)v25;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(struct DCDocument **)a2;
  v19 = DeclaredConfigurationStore_WriteResultData(
          v61,
          (const unsigned __int16 *)a2,
          v25,
          0,
          (const unsigned __int16 *)v58,
          0,
          L"UriCount",
          &pvarg);
  if ( v19 < 0 )
  {
LABEL_32:
    VariantClear(&pvarg);
    goto LABEL_15;
  }
  if ( *((_BYTE *)v6 + 80) )
  {
    v26 = (const unsigned __int16 *)lpSubKey;
    if ( v63 > 7 )
      v26 = lpSubKey[0];
    v27 = DCCDNUtil_SetRegistryDWORD(hKey, v26, L"atomicFlagNecessary", 1u);
    v19 = v27;
    if ( v27 < 0 )
    {
      v28 = (unsigned int)v27;
      v29 = 11462;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)v28,
        dwOptionsb);
      goto LABEL_32;
    }
    if ( *((_BYTE *)v6 + 80) )
    {
      v30 = (const unsigned __int16 *)lpSubKey;
      if ( v63 > 7 )
        v30 = lpSubKey[0];
      v31 = DCCDNUtil_SetRegistryDWORD(hKey, v30, L"oneTimeExecutionNodeNecessary", 1u);
      v19 = v31;
      if ( v31 < 0 )
      {
        v28 = (unsigned int)v31;
        v29 = 11471;
        goto LABEL_38;
      }
    }
  }
  if ( *((_QWORD *)v6 + 5) != *((_QWORD *)v6 + 6) )
  {
    v58 = 0;
    v64 = &v58;
    phkResult = 0;
    v66 = 1;
    v32 = (const WCHAR *)lpSubKey;
    if ( v63 > 7 )
      v32 = lpSubKey[0];
    v33 = RegCreateKeyExW(hKey, v32, 0, 0, 0, 0x20106u, 0, &phkResult, 0);
    v19 = v33;
    if ( v33 > 0 )
      v19 = (unsigned __int16)v33 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v64);
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CEB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v19,
        dwOptionsc);
LABEL_51:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
      goto LABEL_32;
    }
    v57 = 0;
    v64 = &v57;
    phkResult = 0;
    v66 = 1;
    v34 = RegCreateKeyExW(v58, L"resourceTracking", 0, 0, 0, 0x20106u, 0, &phkResult, 0);
    v19 = v34;
    if ( v34 > 0 )
      v19 = (unsigned __int16)v34 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v64);
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CF7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v19,
        dwOptionsd);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v57);
      goto LABEL_51;
    }
    v35 = (const struct ResourceValidationUrisAndValues *)*((_QWORD *)v6 + 5);
    v36 = (const struct ResourceValidationUrisAndValues *)*((_QWORD *)v6 + 6);
    while ( v35 != v36 )
    {
      ResourceValidationUrisAndValues::ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v67, v35);
      if ( v68 <= 7 )
      {
        v37 = (const unsigned __int16 *)v67;
        v38 = (const unsigned __int16 *)v67;
      }
      else
      {
        v37 = v67[0];
        v38 = v67[0];
      }
      v39 = DCCDNUtil_SetRegistryString(v57, v38, L"ResourceSuccessUri", v37, 0);
      if ( v39 < 0 )
      {
        v50 = 11518;
        goto LABEL_99;
      }
      if ( v69[2] )
      {
        v40 = (const unsigned __int16 *)v69;
        if ( v69[3] > (unsigned __int16 *)7 )
          v40 = v69[0];
        v41 = (const unsigned __int16 *)v67;
        if ( v68 > 7 )
          v41 = v67[0];
        v39 = DCCDNUtil_SetRegistryString(v57, v41, L"ResourceSuccessValues", v40, 0);
        if ( v39 < 0 )
        {
          v50 = 11526;
LABEL_99:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v50,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v39,
            dwOptionse);
          ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v67);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v57);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
          v19 = v39;
          goto LABEL_32;
        }
      }
      if ( v70[2] )
      {
        v42 = (const unsigned __int16 *)v70;
        if ( v70[3] > (unsigned __int16 *)7 )
          v42 = v70[0];
        v43 = (const unsigned __int16 *)v67;
        if ( v68 > 7 )
          v43 = v67[0];
        v39 = DCCDNUtil_SetRegistryString(v57, v43, L"ResourceFailureUri", v42, 0);
        if ( v39 < 0 )
        {
          v50 = 11535;
          goto LABEL_99;
        }
      }
      if ( v71[2] )
      {
        v44 = (const unsigned __int16 *)v71;
        if ( v71[3] > (unsigned __int16 *)7 )
          v44 = v71[0];
        v45 = (const unsigned __int16 *)v67;
        if ( v68 > 7 )
          v45 = v67[0];
        v39 = DCCDNUtil_SetRegistryString(v57, v45, L"ResourceFailureValues", v44, 0);
        if ( v39 < 0 )
        {
          v50 = 11544;
          goto LABEL_99;
        }
      }
      if ( v72[2] )
      {
        v46 = (const unsigned __int16 *)v72;
        if ( v72[3] > (unsigned __int16 *)7 )
          v46 = v72[0];
        v47 = (const unsigned __int16 *)v67;
        if ( v68 > 7 )
          v47 = v67[0];
        v39 = DCCDNUtil_SetRegistryString(v57, v47, L"ResourceInProgressUri", v46, 0);
        if ( v39 < 0 )
        {
          v50 = 11553;
          goto LABEL_99;
        }
      }
      if ( v73[2] )
      {
        v48 = (const unsigned __int16 *)v73;
        if ( v73[3] > (unsigned __int16 *)7 )
          v48 = v73[0];
        v49 = (const unsigned __int16 *)v67;
        if ( v68 > 7 )
          v49 = v67[0];
        v39 = DCCDNUtil_SetRegistryString(v57, v49, L"ResourceInProgressValues", v48, 0);
        if ( v39 < 0 )
        {
          v50 = 11562;
          goto LABEL_99;
        }
      }
      ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v67);
      v35 = (const struct ResourceValidationUrisAndValues *)((char *)v35 + 192);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v57);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
  }
  VariantClear(&pvarg);
  std::wstring::_Tidy_deallocate(lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x18009b2e4  mov     [rsp+arg_10], rbx
0x18009b2e9  push    rsi
0x18009b2ea  push    r12
0x18009b2ec  push    r13
0x18009b2ee  push    r14
0x18009b2f0  push    r15
0x18009b2f2  sub     rsp, 1C0h
0x18009b2f9  mov     rax, cs:__security_cookie
0x18009b300  xor     rax, rsp
0x18009b303  mov     [rsp+1E8h+var_38], rax
0x18009b30b  mov     r14, r9
0x18009b30e  mov     [rsp+1E8h+var_170], r9
0x18009b313  mov     r15, rdx
0x18009b316  mov     [rsp+1E8h+var_168], rcx
0x18009b31e  mov     r10, [rsp+1E8h+arg_20]
0x18009b326  mov     [rsp+1E8h+var_190], r10
0x18009b32b  mov     r12, [rsp+1E8h+hKey]
0x18009b333  mov     r13d, 1
0x18009b339  mov     rsi, [r9+10h]
0x18009b33d  mov     rax, [r9+18h]
0x18009b341  xor     ebx, ebx
0x18009b343  cmp     rsi, rax
0x18009b346  jz      loc_18009B3DA
0x18009b34c  mov     r14, rax
0x18009b34f  mov     r8d, [r15+114h]
0x18009b356  mov     rdx, rsi
0x18009b359  lea     rcx, [rsp+1E8h+var_140]
0x18009b361  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x18009b366  mov     [rsp+1E8h+lpSecurityAttributes], rbx
0x18009b36b  mov     [rsp+1E8h+samDesired], r8d; int
0x18009b370  mov     qword ptr [rsp+1E8h+dwOptions], rax; __int64
0x18009b375  xor     r9d, r9d
0x18009b378  mov     r8d, r13d
0x18009b37b  mov     rdx, r10
0x18009b37e  mov     rcx, r12; hKey
0x18009b381  call    ?WriteCookedURIToRegistry@@YAJPEAUHKEY__@@PEBGKEV?$shared_ptr@VDCURI@@@std@@W4DCManagementModel@@PEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z; WriteCookedURIToRegistry(HKEY__ *,ushort const *,ulong,uchar,std::shared_ptr<DCURI>,DCManagementModel,std::vector<std::pair<std::wstring,std::wstring>> *)
0x18009b386  mov     dword ptr [rsp+1E8h+var_198], eax
0x18009b38a  test    eax, eax
0x18009b38c  jns     short loc_18009B3C0
0x18009b38e  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18009b393  mov     r9, [rsi]
0x18009b396  cmp     qword ptr [r9+18h], 7
0x18009b39b  jbe     short loc_18009B3A0
0x18009b39d  mov     r9, [r9]; unsigned __int16 *
0x18009b3a0  mov     ecx, dword ptr [rsp+1E8h+var_198]
0x18009b3a4  mov     [rsp+1E8h+dwOptions], ecx; int
0x18009b3a8  lea     r8, aWritecookeduri_0; "WriteCookedURIToRegistry"
0x18009b3af  lea     rdx, aWritecookedcsp; "WriteCookedCspProviderToRegistry"
0x18009b3b6  mov     rcx, rax; this
0x18009b3b9  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18009b3be  jmp     short loc_18009B3C3
0x18009b3c0  inc     r13d
0x18009b3c3  add     rsi, 10h
0x18009b3c7  cmp     rsi, r14
0x18009b3ca  mov     r10, [rsp+1E8h+var_190]
0x18009b3cf  jnz     loc_18009B34F
0x18009b3d5  mov     r14, [rsp+1E8h+var_170]
0x18009b3da  lea     rcx, [rsp+1E8h+lpSubKey]
0x18009b3e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009b3e7  nop
0x18009b3e8  lea     rdx, aCooked_0; "cooked\\"
0x18009b3ef  lea     rcx, [rsp+1E8h+var_58]
0x18009b3f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009b3fc  nop
0x18009b3fd  mov     r8, [rsp+1E8h+var_190]
0x18009b402  mov     rdx, rax
0x18009b405  lea     rcx, [rsp+1E8h+var_140]
0x18009b40d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18009b412  mov     rdx, rax
0x18009b415  lea     rcx, [rsp+1E8h+lpSubKey]
0x18009b41d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009b422  lea     rcx, [rsp+1E8h+var_140]
0x18009b42a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b42f  nop
0x18009b430  lea     rcx, [rsp+1E8h+var_58]
0x18009b438  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b43d  nop
0x18009b43e  lea     rdx, [rsp+1E8h+lpSubKey]
0x18009b446  cmp     [rsp+1E8h+var_148], 7
0x18009b44f  cmova   rdx, [rsp+1E8h+lpSubKey]; unsigned __int16 *
0x18009b458  mov     r9d, 1; unsigned int
0x18009b45e  lea     r8, aProvidertype_0; "ProviderType"
0x18009b465  mov     rcx, r12; HKEY
0x18009b468  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009b46d  mov     esi, eax
0x18009b46f  test    eax, eax
0x18009b471  jns     short loc_18009B487
0x18009b473  lea     rcx, [rsp+1E8h+lpSubKey]
0x18009b47b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b480  mov     eax, esi
0x18009b482  jmp     loc_18009BAB6
0x18009b487  lea     r9, [r14+58h]
0x18009b48b  cmp     qword ptr [r9+18h], 7
0x18009b490  jbe     short loc_18009B495
0x18009b492  mov     r9, [r9]; unsigned __int16 *
0x18009b495  lea     rdx, [rsp+1E8h+lpSubKey]
0x18009b49d  cmp     [rsp+1E8h+var_148], 7
0x18009b4a6  cmova   rdx, [rsp+1E8h+lpSubKey]; unsigned __int16 *
0x18009b4af  mov     byte ptr [rsp+1E8h+dwOptions], bl; int
0x18009b4b3  lea     r8, aCsp_0; "csp"
0x18009b4ba  mov     rcx, r12; HKEY
0x18009b4bd  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18009b4c2  mov     esi, eax
0x18009b4c4  test    eax, eax
0x18009b4c6  jns     short loc_18009B4E6
0x18009b4c8  mov     edx, 2CA5h; void *
0x18009b4cd  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009b4d4  mov     r9d, esi; char *
0x18009b4d7  mov     rcx, [rsp+1E8h]; this
0x18009b4df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b4e4  jmp     short loc_18009B473
0x18009b4e6  lea     rdx, [rsp+1E8h+lpSubKey]
0x18009b4ee  cmp     [rsp+1E8h+var_148], 7
0x18009b4f7  cmova   rdx, [rsp+1E8h+lpSubKey]; unsigned __int16 *
0x18009b500  mov     r9d, r13d; unsigned int
0x18009b503  lea     r8, aUricount; "UriCount"
0x18009b50a  mov     rcx, r12; HKEY
0x18009b50d  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009b512  mov     esi, eax
0x18009b514  test    eax, eax
0x18009b516  jns     short loc_18009B51F
0x18009b518  mov     edx, 2CABh
0x18009b51d  jmp     short loc_18009B4CD
0x18009b51f  lea     rcx, [rsp+1E8h+pvarg]; pvarg
0x18009b524  call    cs:__imp_VariantInit
0x18009b52a  nop
0x18009b52b  mov     eax, 3
0x18009b530  mov     word ptr [rsp+1E8h+pvarg], ax
0x18009b535  mov     dword ptr [rsp+1E8h+pvarg+8], r13d
0x18009b53a  lea     r8, [r15+60h]
0x18009b53e  cmp     qword ptr [r8+18h], 7
0x18009b543  jbe     short loc_18009B548
0x18009b545  mov     r8, [r8]; unsigned __int16 *
0x18009b548  cmp     qword ptr [r15+18h], 7
0x18009b54d  jbe     short loc_18009B552
0x18009b54f  mov     r15, [r15]
0x18009b552  lea     rax, [rsp+1E8h+pvarg]
0x18009b557  mov     [rsp+1E8h+phkResult], rax; struct tagVARIANT *
0x18009b55c  lea     rax, aUricount; "UriCount"
0x18009b563  mov     [rsp+1E8h+lpSecurityAttributes], rax; lpValueName
0x18009b568  mov     qword ptr [rsp+1E8h+samDesired], rbx; unsigned __int16 *
0x18009b56d  mov     rax, [rsp+1E8h+var_190]
0x18009b572  mov     qword ptr [rsp+1E8h+dwOptions], rax; int
0x18009b577  xor     r9d, r9d; unsigned __int16 *
0x18009b57a  mov     rdx, r15; unsigned __int16 *
0x18009b57d  mov     rcx, [rsp+1E8h+var_168]; struct DeclaredConfigurationScopeData *
0x18009b585  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x18009b58a  mov     esi, eax
0x18009b58c  test    eax, eax
0x18009b58e  jns     short loc_18009B5A0
0x18009b590  lea     rcx, [rsp+1E8h+pvarg]; pvarg
0x18009b595  call    cs:__imp_VariantClear
0x18009b59b  jmp     loc_18009B473
0x18009b5a0  cmp     [r14+50h], bl
0x18009b5a4  jz      loc_18009B642
0x18009b5aa  lea     rdx, [rsp+1E8h+lpSubKey]
0x18009b5b2  cmp     [rsp+1E8h+var_148], 7
0x18009b5bb  cmova   rdx, [rsp+1E8h+lpSubKey]; unsigned __int16 *
0x18009b5c4  mov     r9d, 1; unsigned int
0x18009b5ca  lea     r8, aAtomicflagnece; "atomicFlagNecessary"
0x18009b5d1  mov     rcx, r12; HKEY
0x18009b5d4  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009b5d9  mov     esi, eax
0x18009b5db  test    eax, eax
0x18009b5dd  jns     short loc_18009B5FD
0x18009b5df  mov     r9d, eax; char *
0x18009b5e2  mov     edx, 2CC6h; void *
0x18009b5e7  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009b5ee  mov     rcx, [rsp+1E8h]; this
0x18009b5f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b5fb  jmp     short loc_18009B590
0x18009b5fd  cmp     [r14+50h], bl
0x18009b601  jz      short loc_18009B642
0x18009b603  lea     rdx, [rsp+1E8h+lpSubKey]
0x18009b60b  cmp     [rsp+1E8h+var_148], 7
0x18009b614  cmova   rdx, [rsp+1E8h+lpSubKey]; unsigned __int16 *
0x18009b61d  mov     r9d, 1; unsigned int
0x18009b623  lea     r8, aOnetimeexecuti; "oneTimeExecutionNodeNecessary"
0x18009b62a  mov     rcx, r12; HKEY
0x18009b62d  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009b632  mov     esi, eax
0x18009b634  test    eax, eax
0x18009b636  jns     short loc_18009B642
0x18009b638  mov     r9d, eax
0x18009b63b  mov     edx, 2CCFh
0x18009b640  jmp     short loc_18009B5E7
0x18009b642  mov     rax, [r14+30h]
0x18009b646  cmp     [r14+28h], rax
0x18009b64a  jz      loc_18009BA87
0x18009b650  mov     [rsp+1E8h+var_190], rbx
0x18009b655  lea     rax, [rsp+1E8h+var_190]
0x18009b65a  mov     [rsp+1E8h+var_140], rax
0x18009b662  mov     [rsp+1E8h+var_138], rbx
0x18009b66a  mov     [rsp+1E8h+var_130], 1
0x18009b672  lea     rdx, [rsp+1E8h+lpSubKey]
0x18009b67a  cmp     [rsp+1E8h+var_148], 7
0x18009b683  cmova   rdx, [rsp+1E8h+lpSubKey]; lpSubKey
0x18009b68c  mov     [rsp+1E8h+lpdwDisposition], rbx; lpdwDisposition
0x18009b691  lea     rax, [rsp+1E8h+var_138]
0x18009b699  mov     [rsp+1E8h+phkResult], rax; phkResult
0x18009b69e  mov     [rsp+1E8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18009b6a3  mov     r15d, 20106h
0x18009b6a9  mov     [rsp+1E8h+samDesired], r15d; samDesired
0x18009b6ae  mov     [rsp+1E8h+dwOptions], ebx; int
0x18009b6b2  xor     r9d, r9d; lpClass
0x18009b6b5  xor     r8d, r8d; Reserved
0x18009b6b8  mov     rcx, r12; hKey
0x18009b6bb  call    cs:__imp_RegCreateKeyExW
0x18009b6c1  mov     esi, eax
0x18009b6c3  test    eax, eax
0x18009b6c5  jle     short loc_18009B6D0
0x18009b6c7  movzx   esi, ax
0x18009b6ca  or      esi, 80070000h
0x18009b6d0  lea     rcx, [rsp+1E8h+var_140]
0x18009b6d8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009b6dd  test    esi, esi
0x18009b6df  jns     short loc_18009B70D
0x18009b6e1  mov     rcx, [rsp+1E8h]; this
0x18009b6e9  mov     r9d, esi; char *
0x18009b6ec  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009b6f3  mov     edx, 2CEBh; void *
0x18009b6f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b6fd  nop
0x18009b6fe  lea     rcx, [rsp+1E8h+var_190]
0x18009b703  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009b708  jmp     loc_18009B590
0x18009b70d  mov     [rsp+1E8h+var_198], rbx
0x18009b712  lea     rax, [rsp+1E8h+var_198]
0x18009b717  mov     [rsp+1E8h+var_140], rax
0x18009b71f  mov     [rsp+1E8h+var_138], rbx
0x18009b727  mov     [rsp+1E8h+var_130], 1
0x18009b72f  mov     [rsp+1E8h+lpdwDisposition], rbx; lpdwDisposition
0x18009b734  lea     rax, [rsp+1E8h+var_138]
0x18009b73c  mov     [rsp+1E8h+phkResult], rax; phkResult
0x18009b741  mov     [rsp+1E8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18009b746  mov     [rsp+1E8h+samDesired], r15d; samDesired
0x18009b74b  mov     [rsp+1E8h+dwOptions], ebx; int
0x18009b74f  xor     r9d, r9d; lpClass
0x18009b752  xor     r8d, r8d; Reserved
0x18009b755  lea     rdx, aResourcetracki; "resourceTracking"
0x18009b75c  mov     rcx, [rsp+1E8h+var_190]; hKey
0x18009b761  call    cs:__imp_RegCreateKeyExW
0x18009b767  mov     esi, eax
0x18009b769  test    eax, eax
0x18009b76b  jle     short loc_18009B776
0x18009b76d  movzx   esi, ax
0x18009b770  or      esi, 80070000h
0x18009b776  lea     rcx, [rsp+1E8h+var_140]
0x18009b77e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009b783  test    esi, esi
0x18009b785  jns     short loc_18009B7B3
0x18009b787  mov     rcx, [rsp+1E8h]; this
0x18009b78f  mov     r9d, esi; char *
0x18009b792  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009b799  mov     edx, 2CF7h; void *
0x18009b79e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b7a3  nop
0x18009b7a4  lea     rcx, [rsp+1E8h+var_198]
0x18009b7a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009b7ae  jmp     loc_18009B6FE
0x18009b7b3  mov     rsi, [r14+28h]
0x18009b7b7  mov     r15, [r14+30h]
0x18009b7bb  cmp     rsi, r15
0x18009b7be  jz      loc_18009BA71
0x18009b7c4  mov     rdx, rsi; struct ResourceValidationUrisAndValues *
0x18009b7c7  lea     rcx, [rsp+1E8h+var_118]; this
0x18009b7cf  call    ??0ResourceValidationUrisAndValues@@QEAA@AEBU0@@Z; ResourceValidationUrisAndValues::ResourceValidationUrisAndValues(ResourceValidationUrisAndValues const &)
0x18009b7d4  cmp     [rsp+1E8h+var_100], 7
0x18009b7dd  jbe     short loc_18009B7EC
0x18009b7df  mov     r9, [rsp+1E8h+var_118]
0x18009b7e7  mov     rdx, r9
0x18009b7ea  jmp     short loc_18009B7FC
0x18009b7ec  lea     r9, [rsp+1E8h+var_118]; unsigned __int16 *
0x18009b7f4  lea     rdx, [rsp+1E8h+var_118]; unsigned __int16 *
0x18009b7fc  mov     byte ptr [rsp+1E8h+dwOptions], bl; int
0x18009b800  lea     r8, aResourcesucces; "ResourceSuccessUri"
0x18009b807  mov     rcx, [rsp+1E8h+var_198]; HKEY
0x18009b80c  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18009b811  mov     r14d, eax
0x18009b814  test    eax, eax
0x18009b816  js      loc_18009BA2A
0x18009b81c  cmp     [rsp+1E8h+var_E8], rbx
0x18009b824  jz      short loc_18009B87A
0x18009b826  lea     r9, [rsp+1E8h+var_F8]
0x18009b82e  cmp     [rsp+1E8h+var_E0], 7
0x18009b837  cmova   r9, [rsp+1E8h+var_F8]; unsigned __int16 *
0x18009b840  lea     rdx, [rsp+1E8h+var_118]
0x18009b848  cmp     [rsp+1E8h+var_100], 7
0x18009b851  cmova   rdx, [rsp+1E8h+var_118]; unsigned __int16 *
0x18009b85a  mov     byte ptr [rsp+1E8h+dwOptions], bl; bool
0x18009b85e  lea     r8, aResourcesucces_0; "ResourceSuccessValues"
0x18009b865  mov     rcx, [rsp+1E8h+var_198]; HKEY
0x18009b86a  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18009b86f  mov     r14d, eax
0x18009b872  test    eax, eax
0x18009b874  js      loc_18009BA07
0x18009b87a  cmp     [rsp+1E8h+var_C8], rbx
0x18009b882  jz      short loc_18009B8D8
0x18009b884  lea     r9, [rsp+1E8h+var_D8]
0x18009b88c  cmp     [rsp+1E8h+var_C0], 7
  ... truncated ...
```
