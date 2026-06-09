# DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)

- ea: `0x180076c10`
- end: `0x180078e24`
- name: `?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z`
- size: `8724`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `30`
- callee_count: `57`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005dacc`
- `0x180063350`
- `0x18006510c`
- `0x180068ba0`
- `0x18006abbc`
- `0x180072f9c`
- `0x180074890`
- `0x18007c000`
- `0x180080e90`
- `0x180081830`
- `0x1800882a0`
- `0x18008b42c`
- `0x1800933a0`
- `0x18009468c`
- `0x18009aecc`
- `0x1800a4358`
- `0x1800ac47c`
- `0x180113960`
- `0x18011440c`
- `0x18011f0d0`
- `0x18011f9e0`
- `0x18011ff70`
- `0x180120650`
- `0x180120cf0`
- `0x180121bfc`
- `0x1801223f0`
- `0x180123d20`
- `0x1801257b0`
- `0x180126110`
- `0x180126bc0`

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
- `0x180018a20`
- `0x180018ac0`
- `0x180018b30`
- `0x180019208`
- `0x18001924c`
- `0x1800192b4`
- `0x180019d38`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18001def8`
- `0x18001df28`
- `0x18001df78`
- `0x18004abf8`
- `0x18004b870`
- `0x18004cf10`
- `0x18004d1ac`
- `0x18004eb5c`
- `0x1800536a8`
- `0x180054814`
- `0x180054dc0`
- `0x180054e20`
- `0x180055198`
- `0x18005860c`
- `0x18005f8cc`
- `0x18005fa30`
- `0x18005fcf8`
- `0x1800725e0`
- `0x180076c10`
- `0x180081a94`
- `0x18008f070`
- `0x18008f874`
- `0x18008fc10`
- `0x180098fb4`
- `0x180099040`
- `0x18009fef0`
- `0x1800a1d80`
- `0x1800c0f2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077345`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800773e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077568`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077806`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007789c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800779fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077345`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800773e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077568`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077806`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007789c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800779fd`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180078294`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180078294`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800781c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800781c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800780e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007813e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180078899`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180078945`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800780e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007813e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180078899`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180078945`
- `OLEAUT32!__imp_SysAllocString` at `0x18007741c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800778d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18007741c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800778d8`
- `OLEAUT32!__imp_VariantInit` at `0x180076c66`
- `OLEAUT32!__imp_VariantInit` at `0x180077f3f`
- `OLEAUT32!__imp_VariantInit` at `0x180076c66`
- `OLEAUT32!__imp_VariantInit` at `0x180077f3f`
- `OLEAUT32!__imp_VariantClear` at `0x180076f5b`
- `OLEAUT32!__imp_VariantClear` at `0x1800783c2`
- `OLEAUT32!__imp_VariantClear` at `0x18007875e`
- `OLEAUT32!__imp_VariantClear` at `0x1800787b0`
- `OLEAUT32!__imp_VariantClear` at `0x18007898f`
- `OLEAUT32!__imp_VariantClear` at `0x1800789fd`
- `OLEAUT32!__imp_VariantClear` at `0x180078ad7`
- `OLEAUT32!__imp_VariantClear` at `0x180078b45`
- `OLEAUT32!__imp_VariantClear` at `0x180078bb3`
- `OLEAUT32!__imp_VariantClear` at `0x180078c21`
- `OLEAUT32!__imp_VariantClear` at `0x180078d23`
- `OLEAUT32!__imp_VariantClear` at `0x180078d91`
- `OLEAUT32!__imp_VariantClear` at `0x180076f5b`
- `OLEAUT32!__imp_VariantClear` at `0x1800783c2`
- `OLEAUT32!__imp_VariantClear` at `0x18007875e`
- `OLEAUT32!__imp_VariantClear` at `0x1800787b0`
- `OLEAUT32!__imp_VariantClear` at `0x18007898f`
- `OLEAUT32!__imp_VariantClear` at `0x1800789fd`
- `OLEAUT32!__imp_VariantClear` at `0x180078ad7`
- `OLEAUT32!__imp_VariantClear` at `0x180078b45`
- `OLEAUT32!__imp_VariantClear` at `0x180078bb3`
- `OLEAUT32!__imp_VariantClear` at `0x180078c21`
- `OLEAUT32!__imp_VariantClear` at `0x180078d23`
- `OLEAUT32!__imp_VariantClear` at `0x180078d91`

## string_xrefs

- `0x180077b53`: `osconfigscenario`
- `0x180077bb8`: `osconfigscenarioschema`
- `0x180077c2d`: `osconfigscenariosVersion`
- `0x180076e16`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007832a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180078a83`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180078ccf`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
__int64 __fastcall DeclaredConfigurationStore_GetPersistedDocument(
        struct DeclaredConfigurationScopeData *a1,
        HKEY a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  signed int EnrollmentIdSidStateDocIdKey; // esi
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r14
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  const unsigned __int16 *v17; // rdx
  __int64 v18; // r14
  __int64 v19; // rsi
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v24; // r14
  __int64 v25; // rsi
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  const unsigned __int16 *v29; // rdx
  __int64 v30; // r8
  const unsigned __int16 *v31; // rdx
  __int64 v32; // rbx
  _QWORD *v33; // r8
  const unsigned __int16 *v34; // rdx
  HKEY v35; // r12
  BYTE *v36; // r14
  LSTATUS v37; // eax
  signed int v38; // esi
  unsigned __int64 v39; // rsi
  unsigned __int64 v40; // rax
  BYTE *v41; // rax
  LSTATUS v42; // eax
  unsigned __int16 v43; // dx
  HKEY v44; // r12
  BYTE *v45; // r14
  LSTATUS v46; // eax
  signed int v47; // esi
  unsigned __int64 v48; // rsi
  unsigned __int64 v49; // rax
  BYTE *v50; // rax
  LSTATUS v51; // eax
  unsigned __int16 v52; // dx
  const unsigned __int16 *v53; // rdx
  HKEY v54; // r14
  __int64 v55; // r8
  const unsigned __int16 *v56; // rdx
  __int64 v57; // r8
  const unsigned __int16 *v58; // rdx
  __int64 v59; // r8
  const unsigned __int16 *v60; // rdx
  __int64 v61; // r8
  const unsigned __int16 *v62; // rdx
  __int64 v63; // r8
  const unsigned __int16 *v64; // rdx
  __int64 v65; // r8
  const unsigned __int16 *v66; // rdx
  const unsigned __int16 *v67; // rdx
  __int64 v68; // r8
  const unsigned __int16 *v69; // rdx
  __int64 v70; // r8
  const unsigned __int16 *v71; // rdx
  __int64 v72; // r8
  const unsigned __int16 *v73; // rdx
  const unsigned __int16 *v74; // rdx
  const OLECHAR *v75; // rdx
  __int64 v76; // r8
  _QWORD *v77; // rax
  const unsigned __int16 *v78; // rdx
  __int64 v79; // rdx
  const unsigned __int16 *v80; // rdx
  __int64 v81; // rdx
  const unsigned __int16 *v82; // rax
  int RegistryString; // r14d
  const WCHAR *v84; // rax
  LSTATUS v85; // ebx
  LSTATUS v86; // ebx
  const char *v87; // r9
  DWORD i; // ebx
  void *p_Block; // rcx
  DWORD v90; // ecx
  unsigned int v91; // eax
  int v92; // ebx
  __int64 v93; // r8
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // r8
  __int64 v97; // rax
  __int64 v98; // rax
  const unsigned __int16 *v99; // rax
  unsigned int v100; // ebx
  unsigned __int16 *v101; // rbx
  __int64 v102; // rax
  int PersistedDSCNativeProvider; // eax
  __int64 v104; // rbx
  int v105; // eax
  __int64 v106; // r8
  __int64 v107; // rax
  const WCHAR *v108; // rax
  HKEY v109; // rbx
  __int64 v110; // rax
  const unsigned __int16 *v111; // rax
  const WCHAR *v112; // rax
  LSTATUS v113; // eax
  __int64 v114; // rax
  _QWORD *v115; // rax
  int lpData; // [rsp+20h] [rbp-2B8h]
  int lpDataa; // [rsp+20h] [rbp-2B8h]
  int lpDatab; // [rsp+20h] [rbp-2B8h]
  int lpDatac; // [rsp+20h] [rbp-2B8h]
  int lpDatad; // [rsp+20h] [rbp-2B8h]
  int lpDatae; // [rsp+20h] [rbp-2B8h]
  int lpDataf; // [rsp+20h] [rbp-2B8h]
  int lpDatag; // [rsp+20h] [rbp-2B8h]
  int lpDatah; // [rsp+20h] [rbp-2B8h]
  int lpDatai; // [rsp+20h] [rbp-2B8h]
  int lpDataj; // [rsp+20h] [rbp-2B8h]
  void *Block; // [rsp+60h] [rbp-278h] BYREF
  DWORD v128; // [rsp+68h] [rbp-270h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-268h] BYREF
  DWORD lpcbData[2]; // [rsp+78h] [rbp-260h] BYREF
  unsigned __int16 *v131; // [rsp+80h] [rbp-258h] BYREF
  char v132; // [rsp+88h] [rbp-250h]
  DWORD cbData; // [rsp+8Ch] [rbp-24Ch] BYREF
  DWORD Type; // [rsp+90h] [rbp-248h] BYREF
  BYTE Data[4]; // [rsp+94h] [rbp-244h] BYREF
  HKEY v136; // [rsp+98h] [rbp-240h] BYREF
  const OLECHAR *v137; // [rsp+A0h] [rbp-238h] BYREF
  void *v138; // [rsp+A8h] [rbp-230h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-228h] BYREF
  HKEY v140; // [rsp+C8h] [rbp-210h] BYREF
  HKEY v141; // [rsp+D0h] [rbp-208h]
  HKEY v142; // [rsp+D8h] [rbp-200h] BYREF
  int v143[2]; // [rsp+E0h] [rbp-1F8h]
  DWORD cchValueName; // [rsp+E8h] [rbp-1F0h] BYREF
  HKEY v145; // [rsp+F0h] [rbp-1E8h] BYREF
  std::_Ref_count_base *v146; // [rsp+F8h] [rbp-1E0h]
  unsigned int v147[2]; // [rsp+100h] [rbp-1D8h] BYREF
  unsigned int v148; // [rsp+108h] [rbp-1D0h] BYREF
  int v149[2]; // [rsp+110h] [rbp-1C8h]
  VARIANTARG v150; // [rsp+118h] [rbp-1C0h] BYREF
  DWORD v151; // [rsp+130h] [rbp-1A8h] BYREF
  DWORD v152; // [rsp+134h] [rbp-1A4h] BYREF
  unsigned __int16 *v153[3]; // [rsp+138h] [rbp-1A0h] BYREF
  unsigned __int64 v154; // [rsp+150h] [rbp-188h]
  HKEY phkResult[2]; // [rsp+158h] [rbp-180h] BYREF
  __int64 v156; // [rsp+168h] [rbp-170h]
  std::_Ref_count_base *v157[2]; // [rsp+178h] [rbp-160h] BYREF
  unsigned __int16 *v158[4]; // [rsp+198h] [rbp-140h] BYREF
  _QWORD v159[4]; // [rsp+1B8h] [rbp-120h] BYREF
  _QWORD v160[4]; // [rsp+1D8h] [rbp-100h] BYREF
  _BYTE v161[32]; // [rsp+1F8h] [rbp-E0h] BYREF
  _BYTE v162[32]; // [rsp+218h] [rbp-C0h] BYREF
  _QWORD v163[4]; // [rsp+238h] [rbp-A0h] BYREF
  _OWORD v164[2]; // [rsp+258h] [rbp-80h] BYREF
  unsigned __int16 v165[16]; // [rsp+278h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  *(_QWORD *)v149 = a4;
  v145 = a2;
  *(_QWORD *)v143 = a1;
  VariantInit(&pvarg);
  v165[0] = 0;
  std::wstring::wstring((__int64)v158);
  std::wstring::wstring((__int64)v153);
  v148 = 0;
  v140 = 0;
  switch ( a6 )
  {
    case 1:
      try
      {
        v24 = std::wstring::wstring((__int64)v157, (__int64)L"raw");
        v25 = std::wstring::wstring((__int64)v164, (__int64)L"\\");
        v26 = std::wstring::wstring((__int64)phkResult, a3);
        v27 = std::operator+<unsigned short>(v160, v26, v25);
        v28 = std::operator+<unsigned short>(v159, v27, v24);
        std::wstring::operator=(v158, v28);
        std::wstring::_Tidy_deallocate(v159);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(phkResult);
        std::wstring::_Tidy_deallocate(v164);
        std::wstring::_Tidy_deallocate(v157);
        std::wstring::operator=(v153, v158);
        v141 = a2;
      }
      catch ( std::bad_alloc )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E21,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          lpDatag);
        goto LABEL_12;
      }
      break;
    case 2:
      try
      {
        v18 = std::wstring::wstring((__int64)v157, (__int64)L"cooked");
        v19 = std::wstring::wstring((__int64)v164, (__int64)L"\\");
        v20 = std::wstring::wstring((__int64)phkResult, a3);
        v21 = std::operator+<unsigned short>(v160, v20, v19);
        v22 = std::operator+<unsigned short>(v159, v21, v18);
        std::wstring::operator=(v158, v22);
        std::wstring::_Tidy_deallocate(v159);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(phkResult);
        std::wstring::_Tidy_deallocate(v164);
        std::wstring::_Tidy_deallocate(v157);
        std::wstring::operator=(v153, v158);
        v141 = a2;
      }
      catch ( std::bad_alloc )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E2E,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          lpDataf);
LABEL_12:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v140);
        std::wstring::_Tidy_deallocate(v153);
        std::wstring::_Tidy_deallocate(v158);
        VariantClear(&pvarg);
        return 2147942414LL;
      }
      break;
    case 3:
      try
      {
        v11 = std::wstring::wstring((__int64)v159, a3);
        std::wstring::operator=(v158, v11);
        std::wstring::_Tidy_deallocate(v159);
        v12 = std::wstring::wstring((__int64)v157, (__int64)L"cooked");
        v13 = std::wstring::wstring((__int64)v164, (__int64)L"\\");
        v14 = std::wstring::wstring((__int64)phkResult, a3);
        v15 = std::operator+<unsigned short>(v160, v14, v13);
        v16 = std::operator+<unsigned short>(v159, v15, v12);
        std::wstring::operator=(v153, v16);
        std::wstring::_Tidy_deallocate(v159);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(phkResult);
        std::wstring::_Tidy_deallocate(v164);
        std::wstring::_Tidy_deallocate(v157);
        phkResult[0] = (HKEY)&v140;
        phkResult[1] = 0;
        LOBYTE(v156) = 1;
        v17 = (const unsigned __int16 *)a5;
        if ( *(_QWORD *)(a5 + 24) > 7u )
          v17 = *(const unsigned __int16 **)a5;
        EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                         a1,
                                         v17,
                                         &phkResult[1],
                                         0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
      }
      catch ( std::bad_alloc )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E3B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          lpDatae);
        goto LABEL_224;
      }
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v10 = 7749;
        goto LABEL_10;
      }
      v141 = v140;
      break;
    default:
      EnrollmentIdSidStateDocIdKey = -2147418113;
      v10 = 7756;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
        lpDatah);
      goto LABEL_239;
  }
  v29 = (const unsigned __int16 *)v158;
  if ( v158[3] > (unsigned __int16 *)7 )
    v29 = v158[0];
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryDWORD(v145, v29, L"CspCount", &v148);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
LABEL_239:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v140);
    std::wstring::_Tidy_deallocate(v153);
    std::wstring::_Tidy_deallocate(v158);
    VariantClear(&pvarg);
    return (unsigned int)EnrollmentIdSidStateDocIdKey;
  }
  pvarg.vt = 3;
  if ( *(_QWORD *)(a5 + 120) <= 7u )
    v30 = a5 + 96;
  else
    v30 = *(_QWORD *)(a5 + 96);
  if ( *(_QWORD *)(a5 + 24) <= 7u )
    v31 = (const unsigned __int16 *)a5;
  else
    v31 = *(const unsigned __int16 **)a5;
  hKey = 0;
  if ( !a1 || !v31 || !v30 )
    goto LABEL_38;
  phkResult[1] = 0;
  LOBYTE(v156) = 1;
  phkResult[0] = (HKEY)&hKey;
  if ( *(_QWORD *)v149 )
    GetResultsContainerIdEnrollmentIdSidStateDocIdVersionKey(
      (_DWORD)a1,
      (_DWORD)v31,
      v30,
      v149[0],
      (__int64)&phkResult[1],
      0);
  else
    GetResultsEnrollmentIdSidStateDocIdVersionKey((_DWORD)a1, (_DWORD)v31, v30, (unsigned int)&phkResult[1], 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
  v131 = 0;
  if ( pvarg.vt == 3 )
  {
    *(_DWORD *)Data = 0;
    v128 = 4;
    lpcbData[0] = 4;
    if ( hKey && !RegQueryValueExW(hKey, L"state", 0, &v128, Data, lpcbData) && v128 == 4 )
    {
      pvarg.vt = 3;
      pvarg.lVal = *(_DWORD *)Data;
      goto LABEL_73;
    }
    goto LABEL_70;
  }
  if ( pvarg.vt == 5 )
    goto LABEL_62;
  if ( pvarg.vt != 8 )
  {
    if ( pvarg.vt != 20 )
    {
      if ( pvarg.vt != 8200 )
      {
        if ( pvarg.vt == 8209 )
        {
          v136 = 0;
          v128 = 0;
          if ( (int)DCGetRegistryBinary(hKey, 0, L"state", &v136, &v128) >= 0
            && (int)DCInlineSetBinaryToVariant(v136, v128) >= 0 )
          {
            std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v136);
LABEL_73:
            v32 = -1;
            goto LABEL_74;
          }
          std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v136);
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v131);
LABEL_38:
          v32 = -1;
          goto LABEL_39;
        }
        goto LABEL_70;
      }
LABEL_65:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        Block = 0;
        if ( DCCDNUtil_GetRegistryMultiString(hKey, v131, L"state", (unsigned __int16 **)&Block, &cchValueName) >= 0 )
        {
          pvarg.vt = 8200;
          MultiStringToSafeArray((OLECHAR *)Block, v43, &pvarg.parray);
          operator delete(Block);
          v32 = -1;
          goto LABEL_74;
        }
      }
LABEL_70:
      v32 = -1;
      goto LABEL_74;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    {
      Block = 0;
      v32 = -1;
      if ( (int)DCGetRegistryQWORD(hKey, v131, L"state", &Block) >= 0 )
      {
        pvarg.vt = 20;
        pvarg.llVal = (LONGLONG)Block;
      }
      goto LABEL_74;
    }
LABEL_62:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    {
      Block = 0;
      v32 = -1;
      if ( (int)DCGetRegistryQWORD(hKey, v131, L"state", &Block) >= 0 )
      {
        pvarg.vt = 5;
        pvarg.llVal = (LONGLONG)Block;
      }
      goto LABEL_74;
    }
    goto LABEL_65;
  }
  v35 = hKey;
  Type = 1;
  cbData = 0;
  if ( !hKey )
    goto LABEL_70;
  v36 = 0;
  v37 = RegQueryValueExW(hKey, L"state", 0, &Type, 0, &cbData);
  v38 = v37;
  if ( v37 )
  {
    if ( v37 > 0 )
      v38 = (unsigned __int16)v37 | 0x80070000;
    v32 = -1;
  }
  else
  {
    if ( Type != 1 )
      goto LABEL_70;
    v39 = ((unsigned __int64)cbData >> 1) + 1;
    v40 = 2 * v39;
    v32 = -1;
    if ( !is_mul_ok(v39, 2u) )
      v40 = -1;
    v41 = (BYTE *)operator new[](v40, (const struct std::nothrow_t *)std::nothrow);
    v36 = v41;
    if ( !v41 )
      goto LABEL_74;
    memset_0(v41, 0, v39);
    v42 = RegQueryValueExW(v35, L"state", 0, &Type, v36, &cbData);
    v38 = v42;
    if ( !v42 )
      goto LABEL_61;
    if ( v42 > 0 )
      v38 = (unsigned __int16)v42 | 0x80070000;
    operator delete(v36);
    v36 = 0;
  }
  if ( v38 >= 0 )
  {
LABEL_61:
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString((const OLECHAR *)v36);
    operator delete(v36);
  }
LABEL_74:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v131);
LABEL_39:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  *(_DWORD *)(a5 + 280) = pvarg.lVal;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    goto LABEL_121;
  pvarg.vt = 3;
  v33 = (_QWORD *)(a5 + 96);
  if ( *(_QWORD *)(a5 + 120) > 7u )
    v33 = (_QWORD *)*v33;
  if ( *(_QWORD *)(a5 + 24) <= 7u )
    v34 = (const unsigned __int16 *)a5;
  else
    v34 = *(const unsigned __int16 **)a5;
  hKey = 0;
  if ( *(_QWORD *)v143 && v34 && v33 )
  {
    phkResult[1] = 0;
    LOBYTE(v156) = 1;
    phkResult[0] = (HKEY)&hKey;
    if ( *(_QWORD *)v149 )
      GetResultsContainerIdEnrollmentIdSidStateDocIdVersionKey(
        v143[0],
        (_DWORD)v34,
        (_DWORD)v33,
        v149[0],
        (__int64)&phkResult[1],
        0);
    else
      GetResultsEnrollmentIdSidStateDocIdVersionKey(v143[0], (_DWORD)v34, (_DWORD)v33, (unsigned int)&phkResult[1], 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
    v131 = 0;
    if ( pvarg.vt == 3 )
    {
      *(_DWORD *)Data = 0;
      v128 = 4;
      lpcbData[0] = 4;
      if ( hKey && !RegQueryValueExW(hKey, L"stateInventory", 0, &v128, Data, lpcbData) && v128 == 4 )
      {
        pvarg.vt = 3;
        pvarg.lVal = *(_DWORD *)Data;
      }
      goto LABEL_91;
    }
    if ( pvarg.vt == 5 )
      goto LABEL_111;
    if ( pvarg.vt != 8 )
    {
      if ( pvarg.vt != 20 )
      {
        if ( pvarg.vt != 8200 )
        {
          if ( pvarg.vt == 8209 )
          {
            v136 = 0;
            v128 = 0;
            if ( (int)DCGetRegistryBinary(hKey, 0, L"stateInventory", &v136, &v128) >= 0 )
              DCInlineSetBinaryToVariant(v136, v128);
            std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v136);
          }
          goto LABEL_91;
        }
LABEL_114:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        {
          Block = 0;
          if ( DCCDNUtil_GetRegistryMultiString(
                 hKey,
                 v131,
                 L"stateInventory",
                 (unsigned __int16 **)&Block,
                 &cchValueName) >= 0 )
          {
            pvarg.vt = 8200;
            MultiStringToSafeArray((OLECHAR *)Block, v52, &pvarg.parray);
            operator delete(Block);
          }
        }
        goto LABEL_91;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        Block = 0;
        if ( (int)DCGetRegistryQWORD(hKey, v131, L"stateInventory", &Block) >= 0 )
        {
          pvarg.vt = 20;
LABEL_96:
          pvarg.llVal = (LONGLONG)Block;
          goto LABEL_91;
        }
        goto LABEL_91;
      }
LABEL_111:
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        goto LABEL_114;
      Block = 0;
      if ( (int)DCGetRegistryQWORD(hKey, v131, L"stateInventory", &Block) >= 0 )
      {
        pvarg.vt = 5;
        goto LABEL_96;
      }
LABEL_91:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v131);
      goto LABEL_92;
    }
    v44 = hKey;
    cbData = 1;
    Type = 0;
    if ( !hKey )
      goto LABEL_91;
    v45 = 0;
    v46 = RegQueryValueExW(hKey, L"stateInventory", 0, &cbData, 0, &Type);
    v47 = v46;
    if ( v46 )
    {
      if ( v46 > 0 )
        v47 = (unsigned __int16)v46 | 0x80070000;
    }
    else
    {
      if ( cbData != 1 )
        goto LABEL_91;
      v48 = ((unsigned __int64)Type >> 1) + 1;
      v49 = 2 * v48;
      if ( !is_mul_ok(v48, 2u) )
        v49 = -1;
      v50 = (BYTE *)operator new[](v49, (const struct std::nothrow_t *)std::nothrow);
      v45 = v50;
      if ( !v50 )
        goto LABEL_91;
      memset_0(v50, 0, v48);
      v51 = RegQueryValueExW(v44, L"stateInventory", 0, &cbData, v45, &Type);
      v47 = v51;
      if ( !v51 )
        goto LABEL_110;
      if ( v51 > 0 )
        v47 = (unsigned __int16)v51 | 0x80070000;
      operator delete(v45);
      v45 = 0;
    }
    if ( v47 < 0 )
      goto LABEL_91;
LABEL_110:
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString((const OLECHAR *)v45);
    operator delete(v45);
    goto LABEL_91;
  }
LABEL_92:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  *(_DWORD *)(a5 + 284) = pvarg.lVal;
LABEL_121:
  Block = 0;
  v53 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v53 = v153[0];
  v54 = v141;
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(v141, v53, L"schema", (unsigned __int16 **)&Block);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_239;
  v138 = Block;
  v55 = -1;
  do
    ++v55;
  while ( *((_WORD *)Block + v55) );
  std::wstring::_Assign<unsigned short>((char **)(a5 + 128), Block, (char *)v55);
  Block = 0;
  v56 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v56 = v153[0];
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(
                                   v54,
                                   v56,
                                   L"osdefinedscenario",
                                   (unsigned __int16 **)&Block);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_238;
  v131 = (unsigned __int16 *)Block;
  v57 = -1;
  do
    ++v57;
  while ( *((_WORD *)Block + v57) );
  std::wstring::_Assign<unsigned short>((char **)(a5 + 512), Block, (char *)v57);
  Block = 0;
  v58 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v58 = v153[0];
  if ( DCCDNUtil_GetRegistryString(v54, v58, L"osconfigscenario", (unsigned __int16 **)&Block) >= 0 )
  {
    v59 = -1;
    do
      ++v59;
    while ( *((_WORD *)Block + v59) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 544), Block, (char *)v59);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  Block = 0;
  v60 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v60 = v153[0];
  if ( DCCDNUtil_GetRegistryString(v54, v60, L"osconfigscenarioschema", (unsigned __int16 **)&Block) >= 0 )
  {
    v61 = -1;
    do
      ++v61;
    while ( *((_WORD *)Block + v61) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 576), Block, (char *)v61);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl'::`2'::impl) )
  {
    Block = 0;
    v62 = (const unsigned __int16 *)v153;
    if ( v154 > 7 )
      v62 = v153[0];
    if ( DCCDNUtil_GetRegistryString(v54, v62, L"osconfigscenariosVersion", (unsigned __int16 **)&Block) >= 0 )
    {
      v63 = -1;
      do
        ++v63;
      while ( *((_WORD *)Block + v63) );
      std::wstring::_Assign<unsigned short>((char **)(a5 + 688), Block, (char *)v63);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
    }
  }
  Block = 0;
  v64 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v64 = v153[0];
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(v54, v64, L"context", (unsigned __int16 **)&Block);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_237;
  hKey = (HKEY)Block;
  v65 = -1;
  do
    ++v65;
  while ( *((_WORD *)Block + v65) );
  std::wstring::_Assign<unsigned short>((char **)(a5 + 32), Block, (char *)v65);
  v128 = 0;
  DCCDNUtil_GetRegistryDWORD(v54, 0, L"operation", &v128);
  *(_DWORD *)(a5 + 272) = v128;
  v128 = 0;
  v66 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v66 = v153[0];
  DCCDNUtil_GetRegistryDWORD(v54, v66, L"behavior", &v128);
  *(_DWORD *)(a5 + 676) = v128;
  Block = 0;
  v67 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v67 = v153[0];
  if ( DCCDNUtil_GetRegistryString(v54, v67, L"downloadGUID", (unsigned __int16 **)&Block) >= 0 )
  {
    v68 = -1;
    do
      ++v68;
    while ( *((_WORD *)Block + v68) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 416), Block, (char *)v68);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  Block = 0;
  v69 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v69 = v153[0];
  if ( DCCDNUtil_GetRegistryString(v54, v69, L"downloadUrl", (unsigned __int16 **)&Block) >= 0 )
  {
    v70 = -1;
    do
      ++v70;
    while ( *((_WORD *)Block + v70) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 288), Block, (char *)v70);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  Block = 0;
  v71 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v71 = v153[0];
  if ( DCCDNUtil_GetRegistryString(v54, v71, L"downloadDestination", (unsigned __int16 **)&Block) >= 0 )
  {
    v72 = -1;
    do
      ++v72;
    while ( *((_WORD *)Block + v72) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 480), Block, (char *)v72);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  v128 = 0;
  v73 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v73 = v153[0];
  DCCDNUtil_GetRegistryDWORD(v54, v73, L"downloadRequest", &v128);
  *(_BYTE *)(a5 + 672) = v128 != 0;
  v137 = 0;
  phkResult[0] = (HKEY)&v137;
  phkResult[1] = 0;
  LOBYTE(v156) = 1;
  v74 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v74 = v153[0];
  DCCDNUtil_GetRegistryString(v54, v74, L"requestTimeStamp", (unsigned __int16 **)&phkResult[1]);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(phkResult);
  v75 = &word_180142E98;
  if ( v137 )
    v75 = v137;
  v76 = -1;
  do
    ++v76;
  while ( v75[v76] );
  std::wstring::_Assign<unsigned short>((char **)(a5 + 608), v75, (char *)v76);
  VariantInit(&v150);
  v150.vt = 8;
  v77 = (_QWORD *)(a5 + 96);
  if ( *(_QWORD *)(a5 + 120) > 7u )
    v77 = (_QWORD *)*v77;
  if ( *(_QWORD *)(a5 + 24) <= 7u )
    LODWORD(v78) = a5;
  else
    v78 = *(const unsigned __int16 **)a5;
  if ( (int)DeclaredConfigurationStore_ReadResultData(
              v143[0],
              (int)v78,
              (int)v77,
              v149[0],
              0,
              0,
              L"resultTimeStamp",
              (DWORD)&v150) >= 0 )
  {
    do
      ++v32;
    while ( *(_WORD *)(v150.llVal + 2 * v32) );
    std::wstring::_Assign<unsigned short>((char **)(a5 + 608), v150.bstrVal, (char *)v32);
  }
  LOBYTE(v79) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationParseJSONToDCDoc>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationParseJSONToDCDoc>::GetImpl'::`2'::impl,
    v79);
  v128 = 1;
  v80 = (const unsigned __int16 *)v153;
  if ( v154 > 7 )
    v80 = v153[0];
  DCCDNUtil_GetRegistryDWORD(v54, v80, L"model", &v128);
  *(_DWORD *)(a5 + 276) = v128;
  LOBYTE(v81) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::GetImpl'::`2'::impl,
    v81);
  Block = 0;
  v82 = (const unsigned __int16 *)std::wstring::c_str(v153);
  RegistryString = DCCDNUtil_GetRegistryString(v54, v82, L"originalDocStorageGuid", (unsigned __int16 **)&Block);
  if ( RegistryString < 0 )
  {
    RegistryString = 0;
  }
  else
  {
    std::wstring::operator=(a5 + 448, Block);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
  }
  if ( (*(_BYTE *)(a5 + 676) & 0x23) != 0 )
  {
    Block = 0;
    v136 = 0;
    phkResult[0] = (HKEY)&Block;
    phkResult[1] = 0;
    LOBYTE(v156) = 1;
    v84 = (const WCHAR *)std::wstring::c_str(v153);
    v85 = RegOpenKeyExW(v141, v84, 0, 0x20119u, &phkResult[1]);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
    if ( !v85 )
    {
      phkResult[0] = (HKEY)&v136;
      phkResult[1] = 0;
      LOBYTE(v156) = 1;
      v86 = RegOpenKeyExW((HKEY)Block, L"instanceDataList", 0, 0x20119u, &phkResult[1]);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
      if ( !v86 )
      {
        *(_DWORD *)Data = 0;
        Type = 0;
        cbData = 0;
        if ( !RegQueryInfoKeyW(v136, 0, 0, 0, 0, 0, 0, (LPDWORD)Data, &Type, &cbData, 0, 0) )
        {
          for ( i = 0; i < *(_DWORD *)Data; ++i )
          {
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              lpcbData,
              0,
              Type + 1,
              v87);
            if ( !*(_QWORD *)lpcbData )
            {
              EnrollmentIdSidStateDocIdKey = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1F8A,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
                (const char *)0x8007000ELL,
                lpDatai);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpcbData);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v136);
              p_Block = &Block;
              goto LABEL_236;
            }
            *(_OWORD *)phkResult = 0;
            v156 = 0;
            std::vector<unsigned char>::_Resize<std::_Value_init_tag>(phkResult, cbData + 1);
            v151 = 0;
            cchValueName = Type + 1;
            v152 = cbData + 1;
            if ( !RegEnumValueW(v136, i, *(LPWSTR *)lpcbData, &cchValueName, 0, &v151, (LPBYTE)phkResult[0], &v152) )
            {
              std::vector<unsigned char>::shrink_to_fit(phkResult);
              *(HKEY *)v147 = phkResult[0];
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<unsigned short *>(
                a5 + 256,
                v157,
                v147);
            }
            std::vector<unsigned char>::_Tidy(phkResult);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpcbData);
          }
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v136);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&Block);
  }
  v90 = 1;
  v128 = 1;
  v132 = 0;
  v91 = 0;
  while ( 1 )
  {
    lpcbData[0] = v91;
    if ( v91 >= v148 )
      break;
    v164[0] = 0;
    v92 = StringCchPrintfW(v165, 0xFu, L"CSP%d", v90);
    if ( v92 < 0 )
    {
      VariantClear(&v150);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v137);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v131);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v138);
      EnrollmentIdSidStateDocIdKey = v92;
      goto LABEL_239;
    }
    std::wstring::wstring((__int64)v159);
    std::wstring::wstring((__int64)v160);
    try
    {
      v93 = std::wstring::wstring((__int64)v161, (__int64)L"\\");
      v94 = std::operator+<unsigned short>(v162, v158, v93);
      v95 = std::operator+<unsigned short>(v157, v94, v165);
      std::wstring::operator=(v159, v95);
      std::wstring::_Tidy_deallocate(v157);
      std::wstring::_Tidy_deallocate(v162);
      std::wstring::_Tidy_deallocate(v161);
      v96 = std::wstring::wstring((__int64)v157, (__int64)L"\\");
      v97 = std::operator+<unsigned short>(v162, v153, v96);
      v98 = std::operator+<unsigned short>(v161, v97, v165);
      std::wstring::operator=(v160, v98);
      std::wstring::_Tidy_deallocate(v161);
      std::wstring::_Tidy_deallocate(v162);
      std::wstring::_Tidy_deallocate(v157);
      v147[0] = 0;
      v99 = (const unsigned __int16 *)std::wstring::c_str(v160);
      RegistryString = DCCDNUtil_GetRegistryDWORD(v141, v99, L"ProviderType", v147);
      v100 = v147[0];
      if ( RegistryString < 0 )
        v100 = 1;
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FBC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        lpDatad);
      std::wstring::_Tidy_deallocate(v160);
      std::wstring::_Tidy_deallocate(v159);
      VariantClear(&v150);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v137);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v131);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v138);
LABEL_224:
      EnrollmentIdSidStateDocIdKey = -2147024882;
      goto LABEL_239;
    }
    ++v128;
    if ( v100 == 1 )
    {
      *(_QWORD *)v147 = v161;
      v101 = (unsigned __int16 *)std::wstring::wstring((__int64)v161, v160);
      v102 = std::wstring::wstring((__int64)v162, v159);
      RegistryString = GetPersistedCSPProvider(
                         *(__int64 *)v143,
                         v145,
                         v141,
                         v102,
                         v101,
                         (__int64)v165,
                         (__int64 *)a5,
                         a6,
                         *(__int64 *)v149);
      v132 = 1;
      goto LABEL_223;
    }
    if ( v100 == 2 )
    {
      std::wstring::wstring((__int64)v161, v160);
      PersistedDSCNativeProvider = GetPersistedDSCNativeProvider(v143[0], a5, a6);
LABEL_221:
      RegistryString = PersistedDSCNativeProvider;
      goto LABEL_223;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    {
      if ( v100 != 3 )
        goto LABEL_223;
      v157[0] = (std::_Ref_count_base *)v161;
      v104 = std::wstring::wstring((__int64)v161, v160);
      v105 = std::wstring::wstring((__int64)v162, v159);
      PersistedDSCNativeProvider = GetPersistedRegistryProvider(
                                     v143[0],
                                     (_DWORD)v145,
                                     (_DWORD)v141,
                                     v105,
                                     v104,
                                     (__int64)v165,
                                     a5,
                                     a6,
                                     *(__int64 *)v149);
      goto LABEL_221;
    }
    RegistryString = -2147418113;
LABEL_223:
    std::wstring::_Tidy_deallocate(v160);
    std::wstring::_Tidy_deallocate(v159);
    v91 = lpcbData[0] + 1;
    v90 = v128;
  }
  if ( RegistryString < 0 )
  {
    VariantClear(&v150);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v137);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v131);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v138);
    EnrollmentIdSidStateDocIdKey = RegistryString;
    goto LABEL_239;
  }
  v142 = 0;
  v106 = std::wstring::wstring((__int64)v162, (__int64)L"\\");
  v107 = std::operator+<unsigned short>(v161, v158, v106);
  std::operator+<unsigned short>(v163, v107, L"Orchestration1");
  std::wstring::_Tidy_deallocate(v161);
  std::wstring::_Tidy_deallocate(v162);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v142,
    0);
  v108 = (const WCHAR *)std::wstring::c_str(v163);
  v109 = v141;
  if ( !RegOpenKeyExW(v141, v108, 0, 0x20119u, &v142) )
  {
    v110 = std::wstring::wstring((__int64)v159, v163);
    RegistryString = GetPersistedDSCNativeOrchestrator(v109, v110, a5);
  }
  if ( a6 == 3 )
    goto LABEL_252;
  lpcbData[0] = 0;
  v111 = (const unsigned __int16 *)std::wstring::c_str(v158);
  if ( DCCDNUtil_GetRegistryDWORD(v109, v111, L"PrecheckCount", lpcbData) < 0 || !lpcbData[0] )
  {
    RegistryString = 0;
    goto LABEL_252;
  }
  *(_QWORD *)lpcbData = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    lpcbData,
    0);
  v112 = (const WCHAR *)std::wstring::c_str(v158);
  v113 = RegOpenKeyExW(v109, v112, 0, 0x20119u, (PHKEY)lpcbData);
  EnrollmentIdSidStateDocIdKey = v113;
  if ( v113 )
  {
    if ( v113 > 0 )
      EnrollmentIdSidStateDocIdKey = (unsigned __int16)v113 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(lpcbData);
    std::wstring::_Tidy_deallocate(v163);
    p_Block = &v142;
LABEL_236:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(p_Block);
    VariantClear(&v150);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v137);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
LABEL_237:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v131);
LABEL_238:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v138);
    goto LABEL_239;
  }
  *(_OWORD *)v157 = 0;
  if ( v132 )
  {
    try
    {
      v114 = std::make_shared<DCCSPPrecheck,unsigned short * &,unsigned short * &>(
               &v145,
               *(_QWORD *)v143,
               *(_QWORD *)v143 + 8LL);
      std::shared_ptr<DCURI>::operator=(v157, v114);
      if ( v146 )
        std::_Ref_count_base::_Decref(v146);
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x202C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        lpDatac);
      goto LABEL_265;
    }
    if ( !v157[0] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2028,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        lpDataj);
      if ( v157[1] )
        goto LABEL_246;
      goto LABEL_247;
    }
    RegistryString = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, __int64))(*(_QWORD *)v157[0] + 24LL))(
                       v157[0],
                       *(_QWORD *)lpcbData,
                       1);
    if ( RegistryString >= 0 )
    {
      std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&v145, v157);
      try
      {
        std::vector<std::shared_ptr<DCProviderOrchestration>>::push_back(a5 + 232, &v145);
        if ( v146 )
          std::_Ref_count_base::_Decref(v146);
      }
      catch ( std::bad_alloc )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x203A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          lpDatab);
        goto LABEL_265;
      }
    }
    goto LABEL_249;
  }
  try
  {
    v115 = std::make_shared<DCNativeResourceInstallationPrecheck,unsigned short * &>(&v145, *(_QWORD **)v143);
    std::shared_ptr<DCURI>::operator=(v157, v115);
    if ( v146 )
      std::_Ref_count_base::_Decref(v146);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2048,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      lpDataa);
    goto LABEL_265;
  }
  if ( v157[0] )
  {
    RegistryString = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, __int64))(*(_QWORD *)v157[0] + 24LL))(
                       v157[0],
                       *(_QWORD *)lpcbData,
                       1);
    if ( RegistryString >= 0 )
    {
      std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&v145, v157);
      try
      {
        std::vector<std::shared_ptr<DCProviderOrchestration>>::push_back(a5 + 232, &v145);
        if ( v146 )
          std::_Ref_count_base::_Decref(v146);
      }
      catch ( std::bad_alloc )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2056,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          lpData);
LABEL_265:
        if ( v157[1] )
          std::_Ref_count_base::_Decref(v157[1]);
        RegistryString = -2147024882;
        goto LABEL_251;
      }
    }
LABEL_249:
    if ( v157[1] )
      std::_Ref_count_base::_Decref(v157[1]);
LABEL_251:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(lpcbData);
LABEL_252:
    std::wstring::_Tidy_deallocate(v163);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v142);
    VariantClear(&v150);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v137);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v131);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v138);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v140);
    std::wstring::_Tidy_deallocate(v153);
    std::wstring::_Tidy_deallocate(v158);
    VariantClear(&pvarg);
    return (unsigned int)RegistryString;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2044,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
    (const char *)0x8007000ELL,
    lpDataj);
  if ( v157[1] )
LABEL_246:
    std::_Ref_count_base::_Decref(v157[1]);
LABEL_247:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(lpcbData);
  std::wstring::_Tidy_deallocate(v163);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v142);
  VariantClear(&v150);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v137);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v131);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v138);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v140);
  std::wstring::_Tidy_deallocate(v153);
  std::wstring::_Tidy_deallocate(v158);
  VariantClear(&pvarg);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180076c10  push    rbx
0x180076c12  push    rsi
0x180076c13  push    rdi
0x180076c14  push    r12
0x180076c16  push    r13
0x180076c18  push    r14
0x180076c1a  push    r15
0x180076c1c  sub     rsp, 2A0h
0x180076c23  mov     rax, cs:__security_cookie
0x180076c2a  xor     rax, rsp
0x180076c2d  mov     [rsp+2D8h+var_40], rax
0x180076c35  mov     qword ptr [rsp+2D8h+var_1C8], r9
0x180076c3d  mov     rbx, r8
0x180076c40  mov     r13, rdx
0x180076c43  mov     [rsp+2D8h+var_1E8], rdx
0x180076c4b  mov     r12, rcx
0x180076c4e  mov     qword ptr [rsp+2D8h+var_1F8], rcx
0x180076c56  mov     r15, [rsp+2D8h+arg_20]
0x180076c5e  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x180076c66  call    cs:__imp_VariantInit
0x180076c6c  nop
0x180076c6d  xor     edi, edi
0x180076c6f  mov     [rsp+2D8h+var_60], di
0x180076c77  lea     rcx, [rsp+2D8h+var_140]
0x180076c7f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180076c84  nop
0x180076c85  lea     rcx, [rsp+2D8h+var_1A0]
0x180076c8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180076c92  nop
0x180076c93  mov     [rsp+2D8h+var_1D0], edi
0x180076c9a  mov     [rsp+2D8h+var_210], rdi
0x180076ca2  mov     eax, [rsp+2D8h+arg_28]
0x180076ca9  sub     eax, 1
0x180076cac  jz      loc_180076F89
0x180076cb2  sub     eax, 1
0x180076cb5  jz      loc_180076E4C
0x180076cbb  cmp     eax, 1
0x180076cbe  jz      short loc_180076CCF
0x180076cc0  mov     esi, 8000FFFFh
0x180076cc5  mov     edx, 1E4Ch
0x180076cca  jmp     loc_180076E16
0x180076ccf  mov     rdx, rbx
0x180076cd2  lea     rcx, [rsp+2D8h+var_120]
0x180076cda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076cdf  mov     rdx, rax
0x180076ce2  lea     rcx, [rsp+2D8h+var_140]
0x180076cea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180076cef  lea     rcx, [rsp+2D8h+var_120]
0x180076cf7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076cfc  lea     rdx, aCooked; "cooked"
0x180076d03  lea     rcx, [rsp+2D8h+var_160]
0x180076d0b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076d10  mov     r14, rax
0x180076d13  lea     rdx, StringValue; "\\"
0x180076d1a  lea     rcx, [rsp+2D8h+var_80]
0x180076d22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076d27  mov     rsi, rax
0x180076d2a  mov     rdx, rbx
0x180076d2d  lea     rcx, [rsp+2D8h+phkResult]
0x180076d35  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076d3a  nop
0x180076d3b  mov     r8, rsi
0x180076d3e  mov     rdx, rax
0x180076d41  lea     rcx, [rsp+2D8h+var_100]
0x180076d49  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180076d4e  nop
0x180076d4f  mov     r8, r14
0x180076d52  mov     rdx, rax
0x180076d55  lea     rcx, [rsp+2D8h+var_120]
0x180076d5d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180076d62  mov     rdx, rax
0x180076d65  lea     rcx, [rsp+2D8h+var_1A0]
0x180076d6d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180076d72  lea     rcx, [rsp+2D8h+var_120]
0x180076d7a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076d7f  nop
0x180076d80  lea     rcx, [rsp+2D8h+var_100]
0x180076d88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076d8d  nop
0x180076d8e  lea     rcx, [rsp+2D8h+phkResult]
0x180076d96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076d9b  nop
0x180076d9c  lea     rcx, [rsp+2D8h+var_80]
0x180076da4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076da9  nop
0x180076daa  lea     rcx, [rsp+2D8h+var_160]
0x180076db2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076db7  nop
0x180076db8  lea     rax, [rsp+2D8h+var_210]
0x180076dc0  mov     [rsp+2D8h+phkResult], rax
0x180076dc8  mov     [rsp+2D8h+phkResult+8], rdi
0x180076dd0  mov     r13d, 1
0x180076dd6  mov     byte ptr [rsp+2D8h+var_170], r13b
0x180076dde  mov     rdx, r15
0x180076de1  cmp     qword ptr [r15+18h], 7
0x180076de6  jbe     short loc_180076DEB
0x180076de8  mov     rdx, [r15]; unsigned __int16 *
0x180076deb  xor     r9d, r9d; int
0x180076dee  lea     r8, [rsp+2D8h+phkResult+8]; HKEY *
0x180076df6  mov     rcx, r12; struct DeclaredConfigurationScopeData *
0x180076df9  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180076dfe  mov     esi, eax
0x180076e00  lea     rcx, [rsp+2D8h+phkResult]
0x180076e08  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180076e0d  test    esi, esi
0x180076e0f  jns     short loc_180076E32
0x180076e11  mov     edx, 1E45h; void *
0x180076e16  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180076e1d  mov     r9d, esi; char *
0x180076e20  mov     rcx, [rsp+2D8h]; this
0x180076e28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076e2d  jmp     loc_1800789CB
0x180076e32  mov     rax, [rsp+2D8h+var_210]
0x180076e3a  mov     [rsp+2D8h+var_208], rax
0x180076e42  jmp     loc_180077067
0x180076e47  jmp     loc_180078799
0x180076e4c  lea     rdx, aCooked; "cooked"
0x180076e53  lea     rcx, [rsp+2D8h+var_160]
0x180076e5b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076e60  mov     r14, rax
0x180076e63  lea     rdx, StringValue; "\\"
0x180076e6a  lea     rcx, [rsp+2D8h+var_80]
0x180076e72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076e77  mov     rsi, rax
0x180076e7a  mov     rdx, rbx
0x180076e7d  lea     rcx, [rsp+2D8h+phkResult]
0x180076e85  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076e8a  nop
0x180076e8b  mov     r8, rsi
0x180076e8e  mov     rdx, rax
0x180076e91  lea     rcx, [rsp+2D8h+var_100]
0x180076e99  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180076e9e  nop
0x180076e9f  mov     r8, r14
0x180076ea2  mov     rdx, rax
0x180076ea5  lea     rcx, [rsp+2D8h+var_120]
0x180076ead  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180076eb2  mov     rdx, rax
0x180076eb5  lea     rcx, [rsp+2D8h+var_140]
0x180076ebd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180076ec2  lea     rcx, [rsp+2D8h+var_120]
0x180076eca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076ecf  nop
0x180076ed0  lea     rcx, [rsp+2D8h+var_100]
0x180076ed8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076edd  nop
0x180076ede  lea     rcx, [rsp+2D8h+phkResult]
0x180076ee6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076eeb  nop
0x180076eec  lea     rcx, [rsp+2D8h+var_80]
0x180076ef4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076ef9  nop
0x180076efa  lea     rcx, [rsp+2D8h+var_160]
0x180076f02  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076f07  lea     rdx, [rsp+2D8h+var_140]
0x180076f0f  lea     rcx, [rsp+2D8h+var_1A0]
0x180076f17  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180076f1c  mov     [rsp+2D8h+var_208], r13
0x180076f24  jmp     loc_180077061
0x180076f29  lea     rcx, [rsp+2D8h+var_210]
0x180076f31  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180076f36  nop
0x180076f37  lea     rcx, [rsp+2D8h+var_1A0]
0x180076f3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076f44  nop
0x180076f45  lea     rcx, [rsp+2D8h+var_140]
0x180076f4d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180076f52  nop
0x180076f53  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x180076f5b  call    cs:__imp_VariantClear
0x180076f61  mov     eax, 8007000Eh
0x180076f66  mov     rcx, [rsp+2D8h+var_40]
0x180076f6e  xor     rcx, rsp; StackCookie
0x180076f71  call    __security_check_cookie
0x180076f76  add     rsp, 2A0h
0x180076f7d  pop     r15
0x180076f7f  pop     r14
0x180076f81  pop     r13
0x180076f83  pop     r12
0x180076f85  pop     rdi
0x180076f86  pop     rsi
0x180076f87  pop     rbx
0x180076f88  retn
0x180076f89  lea     rdx, aRaw; "raw"
0x180076f90  lea     rcx, [rsp+2D8h+var_160]
0x180076f98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076f9d  mov     r14, rax
0x180076fa0  lea     rdx, StringValue; "\\"
0x180076fa7  lea     rcx, [rsp+2D8h+var_80]
0x180076faf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076fb4  mov     rsi, rax
0x180076fb7  mov     rdx, rbx
0x180076fba  lea     rcx, [rsp+2D8h+phkResult]
0x180076fc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076fc7  nop
0x180076fc8  mov     r8, rsi
0x180076fcb  mov     rdx, rax
0x180076fce  lea     rcx, [rsp+2D8h+var_100]
0x180076fd6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180076fdb  nop
0x180076fdc  mov     r8, r14
0x180076fdf  mov     rdx, rax
0x180076fe2  lea     rcx, [rsp+2D8h+var_120]
0x180076fea  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180076fef  mov     rdx, rax
0x180076ff2  lea     rcx, [rsp+2D8h+var_140]
0x180076ffa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180076fff  lea     rcx, [rsp+2D8h+var_120]
0x180077007  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007700c  nop
0x18007700d  lea     rcx, [rsp+2D8h+var_100]
0x180077015  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007701a  nop
0x18007701b  lea     rcx, [rsp+2D8h+phkResult]
0x180077023  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077028  nop
0x180077029  lea     rcx, [rsp+2D8h+var_80]
0x180077031  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077036  nop
0x180077037  lea     rcx, [rsp+2D8h+var_160]
0x18007703f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077044  lea     rdx, [rsp+2D8h+var_140]
0x18007704c  lea     rcx, [rsp+2D8h+var_1A0]
0x180077054  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180077059  mov     [rsp+2D8h+var_208], r13
0x180077061  mov     r13d, 1
0x180077067  lea     rdx, [rsp+2D8h+var_140]
0x18007706f  cmp     [rsp+2D8h+var_128], 7
0x180077078  cmova   rdx, [rsp+2D8h+var_140]; unsigned __int16 *
0x180077081  lea     r9, [rsp+2D8h+var_1D0]; unsigned int *
0x180077089  lea     r8, aCspcount_0; "CspCount"
0x180077090  mov     rcx, [rsp+2D8h+var_1E8]; HKEY
0x180077098  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18007709d  mov     esi, eax
0x18007709f  test    eax, eax
0x1800770a1  js      loc_1800789CB
0x1800770a7  mov     ebx, 3
0x1800770ac  mov     word ptr [rsp+2D8h+pvarg], bx
0x1800770b4  cmp     qword ptr [r15+78h], 7
0x1800770b9  jbe     short loc_1800770C1
0x1800770bb  mov     r8, [r15+60h]
0x1800770bf  jmp     short loc_1800770C5
0x1800770c1  lea     r8, [r15+60h]
0x1800770c5  cmp     qword ptr [r15+18h], 7
0x1800770ca  jbe     short loc_1800770D1
0x1800770cc  mov     rdx, [r15]
0x1800770cf  jmp     short loc_1800770D4
0x1800770d1  mov     rdx, r15
0x1800770d4  mov     [rsp+2D8h+hKey], rdi
0x1800770d9  test    r12, r12
0x1800770dc  jz      loc_180077231
0x1800770e2  test    rdx, rdx
0x1800770e5  jz      loc_180077231
0x1800770eb  test    r8, r8
0x1800770ee  jz      loc_180077231
0x1800770f4  mov     rax, qword ptr [rsp+2D8h+var_1C8]
0x1800770fc  mov     [rsp+2D8h+phkResult+8], rdi
0x180077104  mov     byte ptr [rsp+2D8h+var_170], r13b
0x18007710c  test    rax, rax
0x18007710f  jnz     short loc_180077134
0x180077111  lea     rax, [rsp+2D8h+hKey]
0x180077116  mov     [rsp+2D8h+phkResult], rax
0x18007711e  mov     dword ptr [rsp+2D8h+lpData], edi
0x180077122  lea     r9, [rsp+2D8h+phkResult+8]
0x18007712a  mov     rcx, r12
0x18007712d  call    GetResultsEnrollmentIdSidStateDocIdVersionKey
0x180077132  jmp     short loc_18007715D
0x180077134  lea     rcx, [rsp+2D8h+hKey]
0x180077139  mov     [rsp+2D8h+phkResult], rcx
0x180077141  mov     dword ptr [rsp+2D8h+lpcbData], edi
0x180077145  lea     rcx, [rsp+2D8h+phkResult+8]
0x18007714d  mov     [rsp+2D8h+lpData], rcx
0x180077152  mov     r9, rax
0x180077155  mov     rcx, r12
0x180077158  call    GetResultsContainerIdEnrollmentIdSidStateDocIdVersionKey
0x18007715d  lea     rcx, [rsp+2D8h+phkResult]
0x180077165  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007716a  mov     [rsp+2D8h+var_258], rdi
0x180077172  movzx   ecx, word ptr [rsp+2D8h+pvarg]
0x18007717a  sub     ecx, ebx
0x18007717c  jz      loc_180077521
0x180077182  sub     ecx, 2
0x180077185  jz      loc_180077437
0x18007718b  sub     ecx, ebx
0x18007718d  jz      loc_1800772FE
0x180077193  sub     ecx, 0Ch
0x180077196  jz      loc_18007729E
0x18007719c  sub     ecx, 1FF4h
0x1800771a2  jz      loc_180077498
0x1800771a8  cmp     ecx, 9
0x1800771ab  jnz     loc_180077582
0x1800771b1  mov     [rsp+2D8h+var_240], rdi
0x1800771b9  mov     [rsp+2D8h+var_270], edi
0x1800771bd  lea     rax, [rsp+2D8h+var_270]
0x1800771c2  mov     [rsp+2D8h+lpData], rax
0x1800771c7  lea     r9, [rsp+2D8h+var_240]
0x1800771cf  lea     r8, ValueName; "state"
0x1800771d6  xor     edx, edx
0x1800771d8  mov     rcx, [rsp+2D8h+hKey]
0x1800771dd  call    DCGetRegistryBinary
  ... truncated ...
```
