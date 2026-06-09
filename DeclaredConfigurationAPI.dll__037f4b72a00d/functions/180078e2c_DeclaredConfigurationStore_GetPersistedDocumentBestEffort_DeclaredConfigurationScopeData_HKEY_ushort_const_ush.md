# DeclaredConfigurationStore_GetPersistedDocumentBestEffort(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)

- ea: `0x180078e2c`
- end: `0x18007ab63`
- name: `?DeclaredConfigurationStore_GetPersistedDocumentBestEffort@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z`
- size: `7479`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bbaa0`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x18000bf4c`
- `0x18000c8f4`
- `0x1800117dc`
- `0x180011fe0`
- `0x180014348`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x18001924c`
- `0x1800192b4`
- `0x180019d38`
- `0x18001ce5c`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18001def8`
- `0x18004b870`
- `0x18004eb5c`
- `0x180053720`
- `0x180054814`
- `0x18005860c`
- `0x18005f8cc`
- `0x18005fa30`
- `0x18005fcf8`
- `0x180078e2c`
- `0x18008f070`
- `0x18008fc10`
- `0x180098fb4`
- `0x180099040`
- `0x18009fef0`
- `0x1800a1d80`
- `0x1800c0f2c`
- `0x1800ca8f4`
- `0x1801006c8`
- `0x1801007e8`
- `0x180100ad8`
- `0x180102a34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007a569`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007a569`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800792cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079369`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079525`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079811`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800798b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079a2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a068`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a0f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a284`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800792cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079369`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079525`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079811`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800798b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079a2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a068`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a0f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a284`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18007a61d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18007a61d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007a53a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007a53a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a46b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a4c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a46b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a4c7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800793a4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800798ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18007a13a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800793a4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800798ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18007a13a`
- `OLEAUT32!__imp_VariantInit` at `0x180078e7a`
- `OLEAUT32!__imp_VariantInit` at `0x180079e74`
- `OLEAUT32!__imp_VariantInit` at `0x180078e7a`
- `OLEAUT32!__imp_VariantInit` at `0x180079e74`
- `OLEAUT32!__imp_VariantClear` at `0x180078ff3`
- `OLEAUT32!__imp_VariantClear` at `0x18007a6f9`
- `OLEAUT32!__imp_VariantClear` at `0x18007aa71`
- `OLEAUT32!__imp_VariantClear` at `0x18007aaa4`
- `OLEAUT32!__imp_VariantClear` at `0x18007aaf9`
- `OLEAUT32!__imp_VariantClear` at `0x18007ab35`
- `OLEAUT32!__imp_VariantClear` at `0x180078ff3`
- `OLEAUT32!__imp_VariantClear` at `0x18007a6f9`
- `OLEAUT32!__imp_VariantClear` at `0x18007aa71`
- `OLEAUT32!__imp_VariantClear` at `0x18007aaa4`
- `OLEAUT32!__imp_VariantClear` at `0x18007aaf9`
- `OLEAUT32!__imp_VariantClear` at `0x18007ab35`

## string_xrefs

- `0x180079b56`: `osconfigscenario`
- `0x180079bbf`: `osconfigscenarioschema`
- `0x180079c38`: `osconfigscenariosVersion`
- `0x18007a720`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
__int64 __fastcall DeclaredConfigurationStore_GetPersistedDocumentBestEffort(
        __int64 a1,
        HKEY a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  const unsigned __int16 *v13; // rdx
  int RegistryDWORD; // eax
  int RegistryString; // ebx
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // rdx
  int RegistryMultiString; // ebx
  int v23; // edi
  HKEY v24; // rsi
  OLECHAR *v25; // r14
  LSTATUS v26; // eax
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // rax
  BYTE *v29; // rax
  BYTE *v30; // rdi
  LSTATUS v31; // eax
  __int64 v32; // rdx
  LSTATUS v33; // eax
  LONG v34; // eax
  _QWORD *v35; // r8
  __int64 v36; // rdx
  HKEY v37; // rbx
  OLECHAR *v38; // r14
  LSTATUS v39; // eax
  unsigned __int64 v40; // rdi
  unsigned __int64 v41; // rax
  BYTE *v42; // rax
  BYTE *v43; // rsi
  LSTATUS v44; // eax
  __int64 v45; // rdx
  LSTATUS v46; // eax
  LONG v47; // eax
  __int64 v48; // rsi
  __int64 v49; // r8
  const unsigned __int16 *v50; // rdx
  HKEY v51; // rdi
  __int64 v52; // r8
  const unsigned __int16 *v53; // rdx
  __int64 v54; // r8
  const unsigned __int16 *v55; // rdx
  __int64 v56; // r8
  const unsigned __int16 *v57; // rdx
  __int64 v58; // r8
  const unsigned __int16 *v59; // rdx
  const unsigned __int16 *v60; // rdx
  __int64 v61; // r8
  const unsigned __int16 *v62; // rdx
  __int64 v63; // r8
  const unsigned __int16 *v64; // rdx
  __int64 v65; // r8
  const unsigned __int16 *v66; // rdx
  _QWORD *v67; // rax
  __int64 v68; // rdx
  HKEY v69; // rsi
  OLECHAR *v70; // r14
  LSTATUS v71; // eax
  signed int v72; // ebx
  unsigned __int64 v73; // rbx
  unsigned __int64 v74; // rax
  BYTE *v75; // rax
  BYTE *v76; // rdi
  LSTATUS v77; // eax
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // rdx
  const unsigned __int16 *v81; // rdx
  HKEY v82; // r13
  __int64 v83; // rdx
  const unsigned __int16 *v84; // rdx
  int v85; // edi
  const WCHAR *v86; // rdx
  LSTATUS v87; // ebx
  LSTATUS v88; // ebx
  DWORD i; // esi
  __int64 v90; // r14
  HKEY v91; // rax
  WCHAR *v92; // rbx
  DWORD v93; // ecx
  unsigned int v94; // esi
  unsigned int j; // r14d
  __int64 v96; // r8
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // r8
  __int64 v100; // rax
  __int64 v101; // rax
  unsigned __int16 *v102; // rdx
  DWORD v103; // ebx
  unsigned __int16 *v104; // rbx
  __int64 v105; // r9
  int PersistedCSPProvider; // eax
  __int64 v107; // rax
  __int64 v108; // rbx
  int v109; // eax
  int lpData; // [rsp+20h] [rbp-268h]
  int lpDataa; // [rsp+20h] [rbp-268h]
  int lpDatab; // [rsp+20h] [rbp-268h]
  void *Block; // [rsp+60h] [rbp-228h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-220h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-21Ch] BYREF
  HKEY v116; // [rsp+70h] [rbp-218h] BYREF
  DWORD cbData; // [rsp+78h] [rbp-210h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-208h] BYREF
  DWORD cchValueName[2]; // [rsp+88h] [rbp-200h] BYREF
  HKEY v120; // [rsp+90h] [rbp-1F8h] BYREF
  HKEY v121; // [rsp+98h] [rbp-1F0h] BYREF
  DWORD lpcbData[2]; // [rsp+A0h] [rbp-1E8h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-1E0h] BYREF
  unsigned __int16 *v124; // [rsp+C0h] [rbp-1C8h] BYREF
  VARIANTARG v125; // [rsp+C8h] [rbp-1C0h] BYREF
  unsigned int v126; // [rsp+E0h] [rbp-1A8h] BYREF
  int v127[2]; // [rsp+E8h] [rbp-1A0h]
  __int64 v128; // [rsp+F0h] [rbp-198h] BYREF
  HKEY v129; // [rsp+F8h] [rbp-190h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+100h] [rbp-188h] BYREF
  unsigned __int64 v131; // [rsp+118h] [rbp-170h]
  HKEY phkResult[2]; // [rsp+120h] [rbp-168h] BYREF
  __int64 v133; // [rsp+130h] [rbp-158h]
  unsigned __int16 *v134[4]; // [rsp+140h] [rbp-148h] BYREF
  unsigned __int16 v135[4]; // [rsp+160h] [rbp-128h] BYREF
  unsigned __int64 v136; // [rsp+178h] [rbp-110h]
  _BYTE v137[32]; // [rsp+180h] [rbp-108h] BYREF
  _QWORD v138[4]; // [rsp+1A0h] [rbp-E8h] BYREF
  _BYTE v139[32]; // [rsp+1C0h] [rbp-C8h] BYREF
  _BYTE v140[32]; // [rsp+1E0h] [rbp-A8h] BYREF
  _OWORD v141[2]; // [rsp+200h] [rbp-88h] BYREF
  unsigned __int16 v142[16]; // [rsp+220h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v121 = a2;
  *(_QWORD *)v127 = a1;
  VariantInit(&pvarg);
  v142[0] = 0;
  std::wstring::wstring((__int64)v134);
  std::wstring::wstring((__int64)lpSubKey);
  try
  {
    v126 = 0;
    v128 = 0;
    v8 = std::wstring::wstring((__int64)v140, (__int64)L"raw");
    v9 = std::wstring::wstring((__int64)v141, (__int64)L"\\");
    v10 = std::wstring::wstring((__int64)phkResult, a3);
    v11 = std::operator+<unsigned short>(v135, v10, v9);
    v12 = std::operator+<unsigned short>(v138, v11, v8);
    std::wstring::operator=(v134, v12);
    std::wstring::_Tidy_deallocate(v138);
    std::wstring::_Tidy_deallocate(v135);
    std::wstring::_Tidy_deallocate(phkResult);
    std::wstring::_Tidy_deallocate(v141);
    std::wstring::_Tidy_deallocate(v140);
    std::wstring::operator=(lpSubKey, v134);
    v13 = (const unsigned __int16 *)v134;
    if ( v134[3] > (unsigned __int16 *)7 )
      v13 = v134[0];
    RegistryDWORD = DCCDNUtil_GetRegistryDWORD(a2, v13, L"CspCount", &v126);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C4D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      lpDataa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v128);
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::wstring::_Tidy_deallocate(v134);
    VariantClear(&pvarg);
    return 2147942414LL;
  }
  RegistryString = RegistryDWORD;
  if ( RegistryDWORD < 0 )
    goto LABEL_6;
  v120 = 0;
  v17 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v17 = lpSubKey[0];
  RegistryString = DCCDNUtil_GetRegistryString(a2, v17, L"schema", (unsigned __int16 **)&v120);
  if ( RegistryString < 0 )
  {
LABEL_6:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v128);
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::wstring::_Tidy_deallocate(v134);
    VariantClear(&pvarg);
    return (unsigned int)RegistryString;
  }
  v129 = v120;
  v124 = 0;
  v18 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v18 = lpSubKey[0];
  RegistryString = DCCDNUtil_GetRegistryString(a2, v18, L"context", &v124);
  if ( RegistryString < 0 )
    goto LABEL_297;
  v19 = -1;
  do
    ++v19;
  while ( v124[v19] );
  std::wstring::_Assign<unsigned short>((char **)(a5 + 32), v124, (char *)v19);
  pvarg.vt = 3;
  if ( *(_QWORD *)(a5 + 120) <= 7u )
    v20 = a5 + 96;
  else
    v20 = *(_QWORD *)(a5 + 96);
  if ( *(_QWORD *)(a5 + 24) <= 7u )
    v21 = a5;
  else
    v21 = *(_QWORD *)a5;
  hKey = 0;
  if ( a1 && v21 && v20 )
  {
    phkResult[0] = (HKEY)&hKey;
    phkResult[1] = 0;
    LOBYTE(v133) = 1;
    GetResultsEnrollmentIdSidStateDocIdVersionKey(a1, v21, v20, (unsigned int)&phkResult[1], 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
    v116 = 0;
    if ( pvarg.vt != 3 )
    {
      if ( pvarg.vt == 5 )
        goto LABEL_60;
      if ( pvarg.vt != 8 )
      {
        if ( pvarg.vt != 20 )
        {
          if ( pvarg.vt != 8200 )
          {
            if ( pvarg.vt == 8209 )
            {
              *(_QWORD *)cchValueName = 0;
              cValues = 0;
              RegistryMultiString = DCGetRegistryBinary(hKey, 0, L"state", cchValueName, &cValues);
              if ( RegistryMultiString >= 0 )
              {
                RegistryMultiString = DCInlineSetBinaryToVariant(*(void **)cchValueName, cValues, (__int64)&pvarg);
                if ( RegistryMultiString >= 0 )
                {
                  std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(cchValueName);
LABEL_78:
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
                  RegistryMultiString = 0;
                  v23 = -2147024809;
                  goto LABEL_80;
                }
              }
              std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(cchValueName);
              goto LABEL_32;
            }
LABEL_66:
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
            RegistryMultiString = -2147418113;
            goto LABEL_33;
          }
          goto LABEL_63;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        {
          Block = 0;
          RegistryMultiString = DCGetRegistryQWORD(hKey, v116, L"state", &Block);
          if ( RegistryMultiString >= 0 )
          {
            pvarg.vt = 20;
            pvarg.llVal = (LONGLONG)Block;
            goto LABEL_78;
          }
          goto LABEL_32;
        }
LABEL_60:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        {
          Block = 0;
          RegistryMultiString = DCGetRegistryQWORD(hKey, v116, L"state", &Block);
          if ( RegistryMultiString >= 0 )
          {
            pvarg.vt = 5;
            pvarg.llVal = (LONGLONG)Block;
            goto LABEL_78;
          }
          goto LABEL_32;
        }
LABEL_63:
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          goto LABEL_66;
        Block = 0;
        RegistryMultiString = DCCDNUtil_GetRegistryMultiString(
                                hKey,
                                (const unsigned __int16 *)v116,
                                L"state",
                                (unsigned __int16 **)&Block,
                                cchValueName);
        if ( RegistryMultiString >= 0 )
        {
          pvarg.vt = 8200;
          MultiStringToSafeArray((OLECHAR *)Block, v32, &pvarg.parray);
          operator delete(Block);
          goto LABEL_78;
        }
LABEL_32:
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
LABEL_33:
        v23 = -2147024809;
        goto LABEL_80;
      }
      v24 = hKey;
      Type = 1;
      cbData = 0;
      if ( hKey )
      {
        v25 = 0;
        v26 = RegQueryValueExW(hKey, L"state", 0, &Type, 0, &cbData);
        RegistryMultiString = v26;
        if ( v26 )
        {
          if ( v26 > 0 )
            RegistryMultiString = (unsigned __int16)v26 | 0x80070000;
          goto LABEL_54;
        }
        if ( Type == 1 )
        {
          v27 = ((unsigned __int64)cbData >> 1) + 1;
          v28 = 2 * v27;
          if ( !is_mul_ok(v27, 2u) )
            v28 = -1;
          v29 = (BYTE *)operator new[](v28, (const struct std::nothrow_t *)std::nothrow);
          v30 = v29;
          if ( v29 )
          {
            memset_0(v29, 0, v27);
            v31 = RegQueryValueExW(v24, L"state", 0, &Type, v30, &cbData);
            RegistryMultiString = v31;
            if ( !v31 )
            {
              v25 = (OLECHAR *)v30;
              goto LABEL_57;
            }
            if ( v31 > 0 )
              RegistryMultiString = (unsigned __int16)v31 | 0x80070000;
            operator delete(v30);
LABEL_54:
            if ( RegistryMultiString < 0 )
              goto LABEL_45;
LABEL_57:
            pvarg.vt = 8;
            pvarg.llVal = (LONGLONG)SysAllocString(v25);
            operator delete(v25);
            goto LABEL_78;
          }
          RegistryMultiString = -2147024882;
        }
        else
        {
          RegistryMultiString = -2147418113;
        }
LABEL_45:
        v23 = -2147024809;
LABEL_59:
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
        goto LABEL_80;
      }
LABEL_58:
      v23 = -2147024809;
      RegistryMultiString = -2147024809;
      goto LABEL_59;
    }
    Type = 0;
    cValues = 4;
    lpcbData[0] = 4;
    if ( !hKey )
      goto LABEL_58;
    v33 = RegQueryValueExW(hKey, L"state", 0, &cValues, (LPBYTE)&Type, lpcbData);
    RegistryMultiString = v33;
    if ( v33 )
    {
      if ( v33 > 0 )
        RegistryMultiString = (unsigned __int16)v33 | 0x80070000;
      v34 = 0;
      if ( RegistryMultiString < 0 )
        goto LABEL_75;
    }
    else
    {
      if ( cValues != 4 )
      {
        RegistryMultiString = -2147418113;
LABEL_75:
        v23 = -2147024809;
        goto LABEL_59;
      }
      v34 = Type;
    }
    pvarg.vt = 3;
    pvarg.lVal = v34;
    goto LABEL_78;
  }
  v23 = -2147024809;
  RegistryMultiString = -2147024809;
LABEL_80:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( RegistryMultiString >= 0 )
    *(_DWORD *)(a5 + 280) = pvarg.lVal;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    pvarg.vt = 3;
    v35 = (_QWORD *)(a5 + 96);
    if ( *(_QWORD *)(a5 + 120) > 7u )
      v35 = (_QWORD *)*v35;
    if ( *(_QWORD *)(a5 + 24) <= 7u )
      v36 = a5;
    else
      v36 = *(_QWORD *)a5;
    hKey = 0;
    if ( !*(_QWORD *)v127 || !v36 || !v35 )
      goto LABEL_100;
    phkResult[0] = (HKEY)&hKey;
    phkResult[1] = 0;
    LOBYTE(v133) = 1;
    GetResultsEnrollmentIdSidStateDocIdVersionKey(v127[0], v36, (_DWORD)v35, (unsigned int)&phkResult[1], 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
    v116 = 0;
    if ( pvarg.vt == 3 )
    {
      Type = 0;
      cValues = 4;
      lpcbData[0] = 4;
      if ( hKey )
      {
        v46 = RegQueryValueExW(hKey, L"stateInventory", 0, &cValues, (LPBYTE)&Type, lpcbData);
        v23 = v46;
        if ( v46 )
        {
          if ( v46 > 0 )
            v23 = (unsigned __int16)v46 | 0x80070000;
          v47 = 0;
          if ( v23 < 0 )
            goto LABEL_99;
        }
        else
        {
          if ( cValues != 4 )
          {
            v23 = -2147418113;
            goto LABEL_99;
          }
          v47 = Type;
        }
        pvarg.vt = 3;
        pvarg.lVal = v47;
        goto LABEL_143;
      }
LABEL_99:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
      goto LABEL_100;
    }
    if ( pvarg.vt == 5 )
      goto LABEL_126;
    if ( pvarg.vt != 8 )
    {
      if ( pvarg.vt != 20 )
      {
        if ( pvarg.vt != 8200 )
        {
          if ( pvarg.vt == 8209 )
          {
            *(_QWORD *)cchValueName = 0;
            cValues = 0;
            v23 = DCGetRegistryBinary(hKey, 0, L"stateInventory", cchValueName, &cValues);
            if ( v23 >= 0 )
            {
              v23 = DCInlineSetBinaryToVariant(*(void **)cchValueName, cValues, (__int64)&pvarg);
              if ( v23 >= 0 )
              {
                std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(cchValueName);
LABEL_143:
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
                v23 = 0;
LABEL_100:
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                if ( v23 >= 0 )
                  *(_DWORD *)(a5 + 284) = pvarg.lVal;
                goto LABEL_144;
              }
            }
            std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(cchValueName);
            goto LABEL_99;
          }
LABEL_132:
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
          v23 = -2147418113;
          goto LABEL_100;
        }
LABEL_129:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        {
          Block = 0;
          v23 = DCCDNUtil_GetRegistryMultiString(
                  hKey,
                  (const unsigned __int16 *)v116,
                  L"stateInventory",
                  (unsigned __int16 **)&Block,
                  cchValueName);
          if ( v23 >= 0 )
          {
            pvarg.vt = 8200;
            MultiStringToSafeArray((OLECHAR *)Block, v45, &pvarg.parray);
            operator delete(Block);
            goto LABEL_143;
          }
          goto LABEL_99;
        }
        goto LABEL_132;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        Block = 0;
        v23 = DCGetRegistryQWORD(hKey, v116, L"stateInventory", &Block);
        if ( v23 < 0 )
          goto LABEL_99;
        pvarg.vt = 20;
        goto LABEL_107;
      }
LABEL_126:
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        goto LABEL_129;
      Block = 0;
      v23 = DCGetRegistryQWORD(hKey, v116, L"stateInventory", &Block);
      if ( v23 < 0 )
        goto LABEL_99;
      pvarg.vt = 5;
LABEL_107:
      pvarg.llVal = (LONGLONG)Block;
      goto LABEL_143;
    }
    v37 = hKey;
    cbData = 1;
    Type = 0;
    if ( !hKey )
      goto LABEL_99;
    v38 = 0;
    v39 = RegQueryValueExW(hKey, L"stateInventory", 0, &cbData, 0, &Type);
    v23 = v39;
    if ( v39 )
    {
      if ( v39 > 0 )
        v23 = (unsigned __int16)v39 | 0x80070000;
    }
    else
    {
      if ( cbData != 1 )
      {
        v23 = -2147418113;
        goto LABEL_99;
      }
      v40 = ((unsigned __int64)Type >> 1) + 1;
      v41 = 2 * v40;
      if ( !is_mul_ok(v40, 2u) )
        v41 = -1;
      v42 = (BYTE *)operator new[](v41, (const struct std::nothrow_t *)std::nothrow);
      v43 = v42;
      if ( !v42 )
      {
        v23 = -2147024882;
        goto LABEL_99;
      }
      memset_0(v42, 0, v40);
      v44 = RegQueryValueExW(v37, L"stateInventory", 0, &cbData, v43, &Type);
      v23 = v44;
      if ( !v44 )
      {
        v38 = (OLECHAR *)v43;
        goto LABEL_125;
      }
      if ( v44 > 0 )
        v23 = (unsigned __int16)v44 | 0x80070000;
      operator delete(v43);
    }
    if ( v23 < 0 )
      goto LABEL_99;
LABEL_125:
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(v38);
    operator delete(v38);
    goto LABEL_143;
  }
LABEL_144:
  v48 = -1;
  v49 = -1;
  do
    ++v49;
  while ( *((_WORD *)v120 + v49) );
  std::wstring::_Assign<unsigned short>((char **)(a5 + 128), v120, (char *)v49);
  Block = 0;
  v50 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v50 = lpSubKey[0];
  v51 = v121;
  if ( DCCDNUtil_GetRegistryString(v121, v50, L"osdefinedscenario", (unsigned __int16 **)&Block) >= 0 )
  {
    v52 = -1;
    do
      ++v52;
    while ( *((_WORD *)Block + v52) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 512), Block, (char *)v52);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  Block = 0;
  v53 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v53 = lpSubKey[0];
  if ( DCCDNUtil_GetRegistryString(v51, v53, L"osconfigscenario", (unsigned __int16 **)&Block) >= 0 )
  {
    v54 = -1;
    do
      ++v54;
    while ( *((_WORD *)Block + v54) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 544), Block, (char *)v54);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  Block = 0;
  v55 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v55 = lpSubKey[0];
  if ( DCCDNUtil_GetRegistryString(v51, v55, L"osconfigscenarioschema", (unsigned __int16 **)&Block) >= 0 )
  {
    v56 = -1;
    do
      ++v56;
    while ( *((_WORD *)Block + v56) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 576), Block, (char *)v56);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl'::`2'::impl) )
  {
    Block = 0;
    v57 = (const unsigned __int16 *)lpSubKey;
    if ( v131 > 7 )
      v57 = lpSubKey[0];
    if ( DCCDNUtil_GetRegistryString(v51, v57, L"osconfigscenariosVersion", (unsigned __int16 **)&Block) >= 0 )
    {
      v58 = -1;
      do
        ++v58;
      while ( *((_WORD *)Block + v58) );
      std::wstring::_Assign<unsigned short>((char **)(a5 + 688), Block, (char *)v58);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
    }
  }
  cValues = 0;
  if ( DCCDNUtil_GetRegistryDWORD(v51, 0, L"operation", &cValues) >= 0 )
    *(_DWORD *)(a5 + 272) = cValues;
  cValues = 0;
  v59 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v59 = lpSubKey[0];
  if ( DCCDNUtil_GetRegistryDWORD(v51, v59, L"behavior", &cValues) >= 0 )
    *(_DWORD *)(a5 + 676) = cValues;
  Block = 0;
  v60 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v60 = lpSubKey[0];
  if ( DCCDNUtil_GetRegistryString(v51, v60, L"downloadGUID", (unsigned __int16 **)&Block) >= 0 )
  {
    v61 = -1;
    do
      ++v61;
    while ( *((_WORD *)Block + v61) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 416), Block, (char *)v61);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  Block = 0;
  v62 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v62 = lpSubKey[0];
  if ( DCCDNUtil_GetRegistryString(v51, v62, L"downloadUrl", (unsigned __int16 **)&Block) >= 0 )
  {
    v63 = -1;
    do
      ++v63;
    while ( *((_WORD *)Block + v63) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 288), Block, (char *)v63);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  Block = 0;
  v64 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v64 = lpSubKey[0];
  if ( DCCDNUtil_GetRegistryString(v51, v64, L"downloadDestination", (unsigned __int16 **)&Block) >= 0 )
  {
    v65 = -1;
    do
      ++v65;
    while ( *((_WORD *)Block + v65) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 480), Block, (char *)v65);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  cValues = 0;
  v66 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v66 = lpSubKey[0];
  if ( DCCDNUtil_GetRegistryDWORD(v51, v66, L"downloadRequest", &cValues) >= 0 )
    *(_BYTE *)(a5 + 672) = cValues != 0;
  VariantInit(&v125);
  v125.vt = 8;
  v67 = (_QWORD *)(a5 + 96);
  if ( *(_QWORD *)(a5 + 120) > 7u )
    v67 = (_QWORD *)*v67;
  if ( *(_QWORD *)(a5 + 24) <= 7u )
    v68 = a5;
  else
    v68 = *(_QWORD *)a5;
  v116 = 0;
  if ( !*(_QWORD *)v127 || !v68 || !v67 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v116);
    goto LABEL_251;
  }
  phkResult[0] = (HKEY)&v116;
  phkResult[1] = 0;
  LOBYTE(v133) = 1;
  GetResultsEnrollmentIdSidStateDocIdVersionKey(v127[0], v68, (_DWORD)v67, (unsigned int)&phkResult[1], 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
  hKey = 0;
  if ( v125.vt != 3 )
  {
    if ( v125.vt == 5 )
      goto LABEL_236;
    if ( v125.vt != 8 )
    {
      if ( v125.vt != 20 )
      {
        if ( v125.vt != 8200 )
        {
          if ( v125.vt == 8209 )
          {
            v120 = 0;
            cValues = 0;
            if ( (int)DCGetRegistryBinary(v116, 0, L"resultTimeStamp", &v120, &cValues) >= 0
              && (int)DCInlineSetBinaryToVariant(v120, cValues, (__int64)&v125) >= 0 )
            {
              std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v120);
              goto LABEL_246;
            }
            std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v120);
          }
          goto LABEL_249;
        }
LABEL_239:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        {
          Block = 0;
          if ( DCCDNUtil_GetRegistryMultiString(
                 v116,
                 (const unsigned __int16 *)hKey,
                 L"resultTimeStamp",
                 (unsigned __int16 **)&Block,
                 cchValueName) >= 0 )
          {
            v125.vt = 8200;
            MultiStringToSafeArray((OLECHAR *)Block, v78, &v125.parray);
            operator delete(Block);
            goto LABEL_246;
          }
        }
        goto LABEL_249;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        Block = 0;
        if ( (int)DCGetRegistryQWORD(v116, hKey, L"resultTimeStamp", &Block) >= 0 )
        {
          v125.vt = 20;
          v125.llVal = (LONGLONG)Block;
          goto LABEL_246;
        }
        goto LABEL_249;
      }
LABEL_236:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        Block = 0;
        if ( (int)DCGetRegistryQWORD(v116, hKey, L"resultTimeStamp", &Block) >= 0 )
        {
          v125.vt = 5;
          v125.llVal = (LONGLONG)Block;
          goto LABEL_246;
        }
        goto LABEL_249;
      }
      goto LABEL_239;
    }
    v69 = v116;
    cbData = 1;
    Type = 0;
    if ( !v116 )
    {
LABEL_233:
      v48 = -1;
      goto LABEL_249;
    }
    v70 = 0;
    v71 = RegQueryValueExW(v116, L"resultTimeStamp", 0, &cbData, 0, &Type);
    v72 = v71;
    if ( v71 )
    {
      if ( v71 > 0 )
        v72 = (unsigned __int16)v71 | 0x80070000;
    }
    else
    {
      if ( cbData != 1 )
        goto LABEL_233;
      v73 = ((unsigned __int64)Type >> 1) + 1;
      v74 = 2 * v73;
      if ( !is_mul_ok(v73, 2u) )
        v74 = -1;
      v75 = (BYTE *)operator new[](v74, (const struct std::nothrow_t *)std::nothrow);
      v76 = v75;
      if ( !v75 )
        goto LABEL_233;
      memset_0(v75, 0, v73);
      v77 = RegQueryValueExW(v69, L"resultTimeStamp", 0, &cbData, v76, &Type);
      v72 = v77;
      if ( !v77 )
      {
        v70 = (OLECHAR *)v76;
        goto LABEL_235;
      }
      if ( v77 > 0 )
        v72 = (unsigned __int16)v77 | 0x80070000;
      operator delete(v76);
    }
    if ( v72 < 0 )
      goto LABEL_233;
LABEL_235:
    v125.vt = 8;
    v125.llVal = (LONGLONG)SysAllocString(v70);
    operator delete(v70);
    v48 = -1;
    goto LABEL_246;
  }
  Type = 0;
  cValues = 4;
  lpcbData[0] = 4;
  if ( v116 && !RegQueryValueExW(v116, L"resultTimeStamp", 0, &cValues, (LPBYTE)&Type, lpcbData) && cValues == 4 )
  {
    v125.vt = 3;
    v125.lVal = Type;
LABEL_246:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v116);
    v79 = -1;
    do
      ++v79;
    while ( *(_WORD *)(v125.llVal + 2 * v79) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 608), v125.bstrVal, (char *)v79);
    goto LABEL_251;
  }
LABEL_249:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v116);
LABEL_251:
  LOBYTE(v80) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationParseJSONToDCDoc>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationParseJSONToDCDoc>::GetImpl'::`2'::impl,
    v80);
  cValues = 1;
  v81 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v81 = lpSubKey[0];
  v82 = v121;
  if ( DCCDNUtil_GetRegistryDWORD(v121, v81, L"model", &cValues) >= 0 )
    *(_DWORD *)(a5 + 276) = cValues;
  LOBYTE(v83) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::GetImpl'::`2'::impl,
    v83);
  v121 = 0;
  v84 = (const unsigned __int16 *)lpSubKey;
  if ( v131 > 7 )
    v84 = lpSubKey[0];
  v85 = DCCDNUtil_GetRegistryString(v82, v84, L"originalDocStorageGuid", (unsigned __int16 **)&v121);
  if ( v85 >= 0 )
  {
    do
      ++v48;
    while ( *((_WORD *)v121 + v48) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 448), v121, (char *)v48);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v121);
  }
  if ( (*(_BYTE *)(a5 + 676) & 3) != 0 )
  {
    Block = 0;
    v120 = 0;
    phkResult[0] = (HKEY)&Block;
    phkResult[1] = 0;
    LOBYTE(v133) = 1;
    v86 = (const WCHAR *)lpSubKey;
    if ( v131 > 7 )
      v86 = lpSubKey[0];
    v87 = RegOpenKeyExW(v82, v86, 0, 0x20119u, &phkResult[1]);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
    if ( !v87 )
    {
      phkResult[0] = (HKEY)&v120;
      phkResult[1] = 0;
      LOBYTE(v133) = 1;
      v88 = RegOpenKeyExW((HKEY)Block, L"instanceDataList", 0, 0x20119u, &phkResult[1]);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
      if ( !v88 )
      {
        cValues = 0;
        cbData = 0;
        Type = 0;
        if ( !RegQueryInfoKeyW(v120, 0, 0, 0, 0, 0, 0, &cValues, &cbData, &Type, 0, 0) )
        {
          for ( i = 0; i < cValues; ++i )
          {
            v90 = cbData + 1;
            v91 = (HKEY)LocalAlloc(0, 2 * v90 + 2);
            v92 = (WCHAR *)v91;
            if ( v91 )
            {
              *(_WORD *)v91 = 0;
              *((_WORD *)v91 + v90) = 0;
            }
            v121 = v91;
            if ( !v91 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5D6F,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
                (const char *)0x8007000ELL,
                lpDatab);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v121);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v120);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&Block);
              goto LABEL_296;
            }
            *(_OWORD *)phkResult = 0;
            v133 = 0;
            v93 = Type;
            if ( Type != -1 )
            {
              std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(phkResult, Type + 1);
              v93 = Type;
            }
            LODWORD(v116) = 0;
            cchValueName[0] = cbData + 1;
            LODWORD(hKey) = v93 + 1;
            if ( !RegEnumValueW(v120, i, v92, cchValueName, 0, (LPDWORD)&v116, (LPBYTE)phkResult[0], (LPDWORD)&hKey) )
            {
              std::vector<unsigned char>::shrink_to_fit(phkResult);
              *(HKEY *)lpcbData = phkResult[0];
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<unsigned short *>(
                a5 + 256,
                v141,
                lpcbData);
            }
            std::vector<unsigned char>::_Tidy(phkResult);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v121);
          }
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v120);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&Block);
  }
  v94 = 1;
  for ( j = 0; j < v126; ++j )
  {
    v141[0] = 0;
    RegistryString = StringCchPrintfW(v142, 0xFu, L"CSP%d", v94);
    if ( RegistryString < 0 )
    {
      VariantClear(&v125);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v124);
      goto LABEL_297;
    }
    std::wstring::wstring((__int64)v138);
    std::wstring::wstring((__int64)v135);
    try
    {
      v96 = std::wstring::wstring((__int64)v137, (__int64)L"\\");
      v97 = std::operator+<unsigned short>(v139, v134, v96);
      v98 = std::operator+<unsigned short>(v140, v97, v142);
      std::wstring::operator=(v138, v98);
      std::wstring::_Tidy_deallocate(v140);
      std::wstring::_Tidy_deallocate(v139);
      std::wstring::_Tidy_deallocate(v137);
      v99 = std::wstring::wstring((__int64)v140, (__int64)L"\\");
      v100 = std::operator+<unsigned short>(v139, lpSubKey, v99);
      v101 = std::operator+<unsigned short>(v137, v100, v142);
      std::wstring::operator=(v135, v101);
      std::wstring::_Tidy_deallocate(v137);
      std::wstring::_Tidy_deallocate(v139);
      std::wstring::_Tidy_deallocate(v140);
      lpcbData[0] = 0;
      ++v94;
      v102 = *(unsigned __int16 **)v135;
      if ( v136 <= 7 )
        v102 = v135;
      v85 = DCCDNUtil_GetRegistryDWORD(v82, v102, L"ProviderType", lpcbData);
      v103 = lpcbData[0];
      if ( v85 < 0 )
        v103 = 1;
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D9F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        lpData);
      std::wstring::_Tidy_deallocate(v135);
      std::wstring::_Tidy_deallocate(v138);
LABEL_296:
      VariantClear(&v125);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v124);
      RegistryString = -2147024882;
LABEL_297:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v129);
      goto LABEL_6;
    }
    if ( v103 == 1 )
    {
      v121 = (HKEY)v137;
      v104 = (unsigned __int16 *)std::wstring::wstring((__int64)v137, v135);
      v105 = std::wstring::wstring((__int64)v139, v138);
      PersistedCSPProvider = GetPersistedCSPProvider(
                               *(__int64 *)v127,
                               v82,
                               v82,
                               v105,
                               v104,
                               (__int64)v142,
                               (__int64 *)a5,
                               1,
                               0);
LABEL_293:
      v85 = PersistedCSPProvider;
      goto LABEL_295;
    }
    if ( v103 == 2 )
    {
      v107 = std::wstring::wstring((__int64)v137, v135);
      PersistedCSPProvider = GetPersistedDSCNativeProvider(*(__int64 *)v127, v82, v107, (__int64)v142, (__int64 *)a5, 1);
      goto LABEL_293;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    {
      if ( v103 != 3 )
        goto LABEL_295;
      v121 = (HKEY)v137;
      v108 = std::wstring::wstring((__int64)v137, v135);
      v109 = std::wstring::wstring((__int64)v139, v138);
      PersistedCSPProvider = GetPersistedRegistryProvider(
                               v127[0],
                               (_DWORD)v82,
                               (_DWORD)v82,
                               v109,
                               v108,
                               (__int64)v142,
                               a5,
                               1,
                               0);
      goto LABEL_293;
    }
    v85 = -2147418113;
LABEL_295:
    std::wstring::_Tidy_deallocate(v135);
    std::wstring::_Tidy_deallocate(v138);
  }
  VariantClear(&v125);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v124);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v129);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v128);
  std::wstring::_Tidy_deallocate(lpSubKey);
  std::wstring::_Tidy_deallocate(v134);
  VariantClear(&pvarg);
  return (unsigned int)v85;
}

```

## disassembly

```asm
0x180078e2c  push    rbx
0x180078e2e  push    rsi
0x180078e2f  push    rdi
0x180078e30  push    r12
0x180078e32  push    r13
0x180078e34  push    r14
0x180078e36  push    r15
0x180078e38  sub     rsp, 250h
0x180078e3f  mov     rax, cs:__security_cookie
0x180078e46  xor     rax, rsp
0x180078e49  mov     [rsp+288h+var_48], rax
0x180078e51  mov     rsi, r8
0x180078e54  mov     r13, rdx
0x180078e57  mov     [rsp+288h+var_1F0], rdx
0x180078e5f  mov     r12, rcx
0x180078e62  mov     qword ptr [rsp+288h+var_1A0], rcx
0x180078e6a  mov     r15, qword ptr [rsp+288h+arg_20]
0x180078e72  lea     rcx, [rsp+288h+pvarg]; pvarg
0x180078e7a  call    cs:__imp_VariantInit
0x180078e80  nop
0x180078e81  xor     r14d, r14d
0x180078e84  mov     [rsp+288h+var_68], r14w
0x180078e8d  lea     rcx, [rsp+288h+var_148]
0x180078e95  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180078e9a  nop
0x180078e9b  lea     rcx, [rsp+288h+lpSubKey]
0x180078ea3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180078ea8  nop
0x180078ea9  mov     [rsp+288h+var_1A8], r14d
0x180078eb1  mov     [rsp+288h+var_198], r14
0x180078eb9  lea     rdx, aRaw; "raw"
0x180078ec0  lea     rcx, [rsp+288h+var_A8]
0x180078ec8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180078ecd  mov     rdi, rax
0x180078ed0  lea     rdx, StringValue; "\\"
0x180078ed7  lea     rcx, [rsp+288h+var_88]
0x180078edf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180078ee4  mov     rbx, rax
0x180078ee7  mov     rdx, rsi
0x180078eea  lea     rcx, [rsp+288h+phkResult]
0x180078ef2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180078ef7  nop
0x180078ef8  mov     r8, rbx
0x180078efb  mov     rdx, rax
0x180078efe  lea     rcx, [rsp+288h+var_128]
0x180078f06  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180078f0b  nop
0x180078f0c  mov     r8, rdi
0x180078f0f  mov     rdx, rax
0x180078f12  lea     rcx, [rsp+288h+var_E8]
0x180078f1a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180078f1f  mov     rdx, rax
0x180078f22  lea     rcx, [rsp+288h+var_148]
0x180078f2a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180078f2f  lea     rcx, [rsp+288h+var_E8]
0x180078f37  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078f3c  nop
0x180078f3d  lea     rcx, [rsp+288h+var_128]
0x180078f45  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078f4a  nop
0x180078f4b  lea     rcx, [rsp+288h+phkResult]
0x180078f53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078f58  nop
0x180078f59  lea     rcx, [rsp+288h+var_88]
0x180078f61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078f66  nop
0x180078f67  lea     rcx, [rsp+288h+var_A8]
0x180078f6f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078f74  lea     rdx, [rsp+288h+var_148]
0x180078f7c  lea     rcx, [rsp+288h+lpSubKey]
0x180078f84  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180078f89  nop
0x180078f8a  lea     rdx, [rsp+288h+var_148]
0x180078f92  cmp     [rsp+288h+var_130], 7
0x180078f9b  cmova   rdx, [rsp+288h+var_148]; unsigned __int16 *
0x180078fa4  lea     r9, [rsp+288h+var_1A8]; unsigned int *
0x180078fac  lea     r8, aCspcount_0; "CspCount"
0x180078fb3  mov     rcx, r13; HKEY
0x180078fb6  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180078fbb  mov     ebx, eax
0x180078fbd  test    eax, eax
0x180078fbf  jns     short loc_180079000
0x180078fc1  lea     rcx, [rsp+288h+var_198]
0x180078fc9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180078fce  nop
0x180078fcf  lea     rcx, [rsp+288h+lpSubKey]
0x180078fd7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078fdc  nop
0x180078fdd  lea     rcx, [rsp+288h+var_148]
0x180078fe5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078fea  nop
0x180078feb  lea     rcx, [rsp+288h+pvarg]; pvarg
0x180078ff3  call    cs:__imp_VariantClear
0x180078ff9  mov     eax, ebx
0x180078ffb  jmp     loc_18007AB40
0x180079000  mov     [rsp+288h+var_1F8], r14
0x180079008  lea     rdx, [rsp+288h+lpSubKey]
0x180079010  cmp     [rsp+288h+var_170], 7
0x180079019  cmova   rdx, [rsp+288h+lpSubKey]; unsigned __int16 *
0x180079022  lea     r9, [rsp+288h+var_1F8]; unsigned __int16 **
0x18007902a  lea     r8, aSchema; "schema"
0x180079031  mov     rcx, r13; HKEY
0x180079034  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180079039  mov     ebx, eax
0x18007903b  test    eax, eax
0x18007903d  js      short loc_180078FC1
0x18007903f  mov     rax, [rsp+288h+var_1F8]
0x180079047  mov     [rsp+288h+var_190], rax
0x18007904f  mov     [rsp+288h+var_1C8], r14
0x180079057  lea     rdx, [rsp+288h+lpSubKey]
0x18007905f  cmp     [rsp+288h+var_170], 7
0x180079068  cmova   rdx, [rsp+288h+lpSubKey]; unsigned __int16 *
0x180079071  lea     r9, [rsp+288h+var_1C8]; unsigned __int16 **
0x180079079  lea     r8, aContext_1; "context"
0x180079080  mov     rcx, r13; HKEY
0x180079083  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180079088  mov     ebx, eax
0x18007908a  xor     r13d, r13d
0x18007908d  test    eax, eax
0x18007908f  js      loc_18007AA8A
0x180079095  mov     rdx, [rsp+288h+var_1C8]
0x18007909d  mov     [rsp+288h+var_1C8], rdx
0x1800790a5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800790a9  mov     r8, rdi
0x1800790ac  inc     r8
0x1800790af  cmp     [rdx+r8*2], r13w
0x1800790b4  jnz     short loc_1800790AC
0x1800790b6  lea     rcx, [r15+20h]
0x1800790ba  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800790bf  mov     esi, 3
0x1800790c4  mov     word ptr [rsp+288h+pvarg], si
0x1800790cc  cmp     qword ptr [r15+78h], 7
0x1800790d1  jbe     short loc_1800790D9
0x1800790d3  mov     r8, [r15+60h]
0x1800790d7  jmp     short loc_1800790DD
0x1800790d9  lea     r8, [r15+60h]
0x1800790dd  cmp     qword ptr [r15+18h], 7
0x1800790e2  jbe     short loc_1800790E9
0x1800790e4  mov     rdx, [r15]
0x1800790e7  jmp     short loc_1800790EC
0x1800790e9  mov     rdx, r15
0x1800790ec  mov     [rsp+288h+hKey], r13
0x1800790f4  test    r12, r12
0x1800790f7  jz      loc_180079593
0x1800790fd  test    rdx, rdx
0x180079100  jz      loc_180079593
0x180079106  test    r8, r8
0x180079109  jz      loc_180079593
0x18007910f  lea     rax, [rsp+288h+hKey]
0x180079117  mov     [rsp+288h+phkResult], rax
0x18007911f  mov     [rsp+288h+phkResult+8], r13
0x180079127  mov     r14d, 1
0x18007912d  mov     byte ptr [rsp+288h+var_158], r14b
0x180079135  mov     dword ptr [rsp+288h+lpData], r13d
0x18007913a  lea     r9, [rsp+288h+phkResult+8]
0x180079142  mov     rcx, r12
0x180079145  call    GetResultsEnrollmentIdSidStateDocIdVersionKey
0x18007914a  lea     rcx, [rsp+288h+phkResult]
0x180079152  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180079157  mov     [rsp+288h+var_218], r13
0x18007915c  movzx   ecx, word ptr [rsp+288h+pvarg]
0x180079164  sub     ecx, esi
0x180079166  jz      loc_1800794D6
0x18007916c  sub     ecx, 2
0x18007916f  jz      loc_1800793DC
0x180079175  sub     ecx, esi
0x180079177  jz      loc_18007928C
0x18007917d  sub     ecx, 0Ch
0x180079180  jz      loc_18007922A
0x180079186  sub     ecx, 1FF4h
0x18007918c  jz      loc_18007943E
0x180079192  cmp     ecx, 9
0x180079195  jnz     loc_1800794C1
0x18007919b  mov     qword ptr [rsp+288h+cchValueName], r13
0x1800791a3  mov     [rsp+288h+cValues], r13d
0x1800791a8  lea     rax, [rsp+288h+cValues]
0x1800791ad  mov     [rsp+288h+lpData], rax
0x1800791b2  lea     r9, [rsp+288h+cchValueName]
0x1800791ba  lea     r8, ValueName; "state"
0x1800791c1  xor     edx, edx
0x1800791c3  mov     rcx, [rsp+288h+hKey]
0x1800791cb  call    DCGetRegistryBinary
0x1800791d0  mov     ebx, eax
0x1800791d2  test    eax, eax
0x1800791d4  jns     short loc_1800791F9
0x1800791d6  lea     rcx, [rsp+288h+cchValueName]
0x1800791de  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x1800791e3  nop
0x1800791e4  lea     rcx, [rsp+288h+var_218]
0x1800791e9  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800791ee  nop
0x1800791ef  mov     edi, 80070057h
0x1800791f4  jmp     loc_1800795A0
0x1800791f9  lea     r8, [rsp+288h+pvarg]
0x180079201  mov     edx, [rsp+288h+cValues]; Size
0x180079205  mov     rcx, qword ptr [rsp+288h+cchValueName]; Src
0x18007920d  call    DCInlineSetBinaryToVariant
0x180079212  mov     ebx, eax
0x180079214  lea     rcx, [rsp+288h+cchValueName]
0x18007921c  test    eax, eax
0x18007921e  js      short loc_1800791DE
0x180079220  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x180079225  jmp     loc_18007956E
0x18007922a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x180079231  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x180079236  test    al, al
0x180079238  jz      loc_1800793DC
0x18007923e  mov     [rsp+288h+Block], r13
0x180079243  lea     r9, [rsp+288h+Block]
0x180079248  lea     r8, ValueName; "state"
0x18007924f  mov     rdx, [rsp+288h+var_218]
0x180079254  mov     rcx, [rsp+288h+hKey]
0x18007925c  call    DCGetRegistryQWORD
0x180079261  mov     ebx, eax
0x180079263  test    eax, eax
0x180079265  js      loc_1800791E4
0x18007926b  mov     r12d, 14h
0x180079271  mov     word ptr [rsp+288h+pvarg], r12w
0x18007927a  mov     rax, [rsp+288h+Block]
0x18007927f  mov     qword ptr [rsp+288h+pvarg+8], rax
0x180079287  jmp     loc_180079574
0x18007928c  mov     rsi, [rsp+288h+hKey]
0x180079294  mov     [rsp+288h+Type], r14d
0x180079299  mov     [rsp+288h+cbData], r13d
0x18007929e  test    rsi, rsi
0x1800792a1  jz      loc_1800793C5
0x1800792a7  mov     r14, r13
0x1800792aa  lea     rax, [rsp+288h+cbData]
0x1800792af  mov     [rsp+288h+lpcbData], rax; lpcbData
0x1800792b4  mov     [rsp+288h+lpData], r13; lpData
0x1800792b9  lea     r9, [rsp+288h+Type]; lpType
0x1800792be  xor     r8d, r8d; lpReserved
0x1800792c1  lea     rdx, ValueName; "state"
0x1800792c8  mov     rcx, rsi; hKey
0x1800792cb  call    cs:__imp_RegQueryValueExW
0x1800792d1  mov     ebx, eax
0x1800792d3  test    eax, eax
0x1800792d5  jz      short loc_1800792EB
0x1800792d7  jle     loc_180079388
0x1800792dd  movzx   ebx, ax
0x1800792e0  or      ebx, 80070000h
0x1800792e6  jmp     loc_180079388
0x1800792eb  cmp     [rsp+288h+Type], 1
0x1800792f0  jz      short loc_180079307
0x1800792f2  mov     ebx, 8000FFFFh
0x1800792f7  mov     edi, 80070057h
0x1800792fc  mov     r14d, 1
0x180079302  jmp     loc_1800793CC
0x180079307  mov     ebx, [rsp+288h+cbData]
0x18007930b  shr     rbx, 1
0x18007930e  inc     rbx
0x180079311  mov     eax, 2
0x180079316  mul     rbx
0x180079319  cmovb   rax, rdi
0x18007931d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180079324  mov     rcx, rax; unsigned __int64
0x180079327  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007932c  mov     rdi, rax
0x18007932f  test    rax, rax
0x180079332  jnz     short loc_18007933B
0x180079334  mov     ebx, 8007000Eh
0x180079339  jmp     short loc_1800792F7
0x18007933b  mov     r8, rbx; Size
0x18007933e  xor     edx, edx; Val
0x180079340  mov     rcx, rdi; void *
0x180079343  call    memset_0
0x180079348  lea     rax, [rsp+288h+cbData]
0x18007934d  mov     [rsp+288h+lpcbData], rax; lpcbData
0x180079352  mov     [rsp+288h+lpData], rdi; lpData
0x180079357  lea     r9, [rsp+288h+Type]; lpType
0x18007935c  xor     r8d, r8d; lpReserved
0x18007935f  lea     rdx, ValueName; "state"
0x180079366  mov     rcx, rsi; hKey
0x180079369  call    cs:__imp_RegQueryValueExW
0x18007936f  mov     ebx, eax
0x180079371  test    eax, eax
0x180079373  jz      short loc_180079391
0x180079375  jle     short loc_180079380
0x180079377  movzx   ebx, ax
0x18007937a  or      ebx, 80070000h
0x180079380  mov     rcx, rdi; Block
0x180079383  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180079388  test    ebx, ebx
0x18007938a  jns     short loc_180079394
0x18007938c  jmp     loc_1800792F7
0x180079391  mov     r14, rdi
0x180079394  mov     eax, 8
0x180079399  mov     word ptr [rsp+288h+pvarg], ax
0x1800793a1  mov     rcx, r14; psz
0x1800793a4  call    cs:__imp_SysAllocString
0x1800793aa  mov     qword ptr [rsp+288h+pvarg+8], rax
0x1800793b2  mov     rcx, r14; Block
0x1800793b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800793ba  mov     r14d, 1
0x1800793c0  jmp     loc_18007956E
0x1800793c5  mov     edi, 80070057h
0x1800793ca  mov     ebx, edi
0x1800793cc  lea     rcx, [rsp+288h+var_218]
0x1800793d1  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800793d6  nop
  ... truncated ...
```
