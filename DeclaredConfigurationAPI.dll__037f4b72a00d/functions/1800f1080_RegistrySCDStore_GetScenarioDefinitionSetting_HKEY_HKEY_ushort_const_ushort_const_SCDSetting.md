# RegistrySCDStore::GetScenarioDefinitionSetting(HKEY__ *,HKEY__ *,ushort const *,ushort const *,SCDSetting &)

- ea: `0x1800f1080`
- end: `0x1800f1d07`
- name: `?GetScenarioDefinitionSetting@RegistrySCDStore@@AEAAJPEAUHKEY__@@0PEBG1AEAVSCDSetting@@@Z`
- size: `3207`
- prototype: `__int64 __fastcall(RegistrySCDStore *__hidden this, HKEY, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct SCDSetting *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f0d38`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x180018ac0`
- `0x180018ba4`
- `0x180019d38`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18001dfbc`
- `0x18004abf8`
- `0x1800600bc`
- `0x1800e8edc`
- `0x1800e8f54`
- `0x1800e8fd0`
- `0x1800e902c`
- `0x1800ef1d0`
- `0x1800f0d38`
- `0x1800f1080`
- `0x1800f32d0`
- `0x1801006c8`
- `0x180100ad8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f1b5c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f1b5c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800f17fe`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800f17fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f1a9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f1a9d`

## string_xrefs

- `0x1800f15e5`: `GetUriPath`
- `0x1800f1518`: `UriPath`
- `0x1800f12c4`: `RegPath`
- `0x1800f10db`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f11b3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1356`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1387`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f13ad`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1457`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1548`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1575`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1615`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1655`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f17a6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1858`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f18c6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1903`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f19a9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1a51`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1ac7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1bac`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f1be7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f14de`: `UriPathOriginal`
- `0x1800f15ab`: `GetUriPathOriginal`
- `0x1800f1c9b`: `writeonly`
- `0x1800f1c58`: `readonly`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall RegistrySCDStore::GetScenarioDefinitionSetting(
        RegistrySCDStore *this,
        HKEY a2,
        HKEY a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        char **a6)
{
  __int64 v8; // rdx
  signed int RegistryString; // ebx
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  int RegistryDWORD; // eax
  unsigned int v16; // r12d
  int v17; // eax
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  __int64 v21; // r8
  char **v22; // rbx
  wchar_t **v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 *v26; // r14
  _WORD **v27; // rcx
  char **v28; // rbx
  __int64 v29; // r8
  _WORD *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r8
  char **v34; // rbx
  __int64 v35; // r8
  __int64 v36; // rdx
  wchar_t *i; // rcx
  __int64 v38; // rbx
  wchar_t *v39; // rax
  unsigned int *v40; // rcx
  LPCWSTR *v41; // rcx
  char ***v42; // rbx
  __int64 v43; // r8
  _QWORD *v44; // rdi
  HKEY v45; // r14
  LSTATUS v46; // eax
  unsigned __int64 v47; // r9
  __int64 v48; // rdx
  int ScenarioDefinitionObject; // eax
  unsigned int *v50; // rcx
  int v51; // eax
  int v52; // eax
  int phkResult; // [rsp+20h] [rbp-C9h]
  unsigned int v55; // [rsp+30h] [rbp-B9h] BYREF
  unsigned int v56[2]; // [rsp+38h] [rbp-B1h] BYREF
  wchar_t *v57; // [rsp+40h] [rbp-A9h] BYREF
  _WORD *v58; // [rsp+48h] [rbp-A1h] BYREF
  _WORD *v59; // [rsp+50h] [rbp-99h] BYREF
  _WORD *v60; // [rsp+58h] [rbp-91h] BYREF
  _WORD *v61; // [rsp+60h] [rbp-89h] BYREF
  _WORD *v62; // [rsp+68h] [rbp-81h] BYREF
  char **v63; // [rsp+70h] [rbp-79h] BYREF
  std::_Ref_count_base *v64; // [rsp+78h] [rbp-71h]
  _WORD *v65; // [rsp+80h] [rbp-69h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-61h] BYREF
  _WORD *v67; // [rsp+90h] [rbp-59h] BYREF
  __int64 v68; // [rsp+98h] [rbp-51h] BYREF
  _WORD *v69; // [rsp+A0h] [rbp-49h] BYREF
  wchar_t *Context; // [rsp+A8h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-39h]
  RegistrySCDStore *v72; // [rsp+B8h] [rbp-31h]
  char ***p_lpSubKey; // [rsp+C0h] [rbp-29h] BYREF
  HKEY v74; // [rsp+C8h] [rbp-21h] BYREF
  char v75; // [rsp+D0h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+4Fh]

  hKey = a2;
  v72 = this;
  v60 = a5;
  if ( a2 )
  {
    if ( !a3 )
    {
      v8 = 522;
      goto LABEL_3;
    }
    if ( !a4 )
    {
      v8 = 523;
      goto LABEL_3;
    }
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    std::wstring::_Assign<unsigned short>(a6, a4, (char *)v11);
    v69 = 0;
    p_lpSubKey = (char ***)&v69;
    v74 = 0;
    v75 = 1;
    RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"Description", (unsigned __int16 **)&v74);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( RegistryString != -2147024894 )
    {
      if ( RegistryString < 0 )
      {
        v12 = (unsigned int)RegistryString;
        v13 = 539;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
          (const char *)v12,
          phkResult);
LABEL_165:
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v69);
        return (unsigned int)RegistryString;
      }
      v14 = -1;
      do
        ++v14;
      while ( v69[v14] );
      std::wstring::_Assign<unsigned short>(a6 + 4, v69, (char *)v14);
    }
    v56[0] = 0;
    RegistryDWORD = DCCDNUtil_GetRegistryDWORD(a3, a4, L"DataType", v56);
    RegistryString = RegistryDWORD;
    if ( RegistryDWORD < 0 )
    {
      v13 = 548;
LABEL_18:
      v12 = (unsigned int)RegistryDWORD;
      goto LABEL_19;
    }
    v55 = 0;
    LODWORD(v58) = 0;
    RegistryDWORD = ConvertDCDataTypeToSCDDataType(v56[0], &v55, &v58);
    RegistryString = RegistryDWORD;
    if ( RegistryDWORD < 0 )
    {
      v13 = 552;
      goto LABEL_18;
    }
    v16 = v55;
    *((_DWORD *)a6 + 22) = v55;
    *((_DWORD *)a6 + 23) = (_DWORD)v58;
    v55 = 0;
    v17 = DCCDNUtil_GetRegistryDWORD(a3, a4, L"Provider", &v55);
    if ( v17 < 0 )
    {
      if ( v17 == -2147024894 )
        goto LABEL_59;
      v68 = 0;
      p_lpSubKey = (char ***)&v68;
      v74 = 0;
      v75 = 1;
      RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"Provider", (unsigned __int16 **)&v74);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
      if ( RegistryString < 0 && RegistryString != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
          (const char *)(unsigned int)RegistryString,
          phkResult);
        v23 = (wchar_t **)&v68;
        goto LABEL_58;
      }
      v18 = 1;
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v68);
    }
    else
    {
      v18 = v55;
    }
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( !v20 )
      {
        RegistryString = -2147467263;
        v12 = 2147500033LL;
        v13 = 716;
        goto LABEL_19;
      }
      if ( v20 != 1 )
      {
        RegistryString = -2147418113;
        v12 = 2147549183LL;
        v13 = 719;
        goto LABEL_19;
      }
      v65 = 0;
      p_lpSubKey = (char ***)&v65;
      v74 = 0;
      v75 = 1;
      RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"RegPath", (unsigned __int16 **)&v74);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
      if ( RegistryString == -2147024894 )
      {
        if ( v16 == 10 )
          goto LABEL_34;
      }
      else if ( RegistryString >= 0 )
      {
LABEL_34:
        v67 = 0;
        p_lpSubKey = (char ***)&v67;
        v74 = 0;
        v75 = 1;
        RegistryString = DCCDNUtil_GetRegistryStringWithBase64UriDecoding(a3, a4, v21, &v74);
        wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
        if ( RegistryString == -2147024894 )
        {
          if ( v16 == 10 )
          {
LABEL_36:
            std::make_shared<SCDRegistryProvider,>(&v63);
            v22 = v63;
            if ( !v63 )
            {
              RegistryString = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2BE,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                (const char *)0x8007000ELL,
                phkResult);
              if ( v64 )
                std::_Ref_count_base::_Decref(v64);
              goto LABEL_44;
            }
            if ( v65 )
            {
              v24 = -1;
              do
                ++v24;
              while ( v65[v24] );
              std::wstring::_Assign<unsigned short>(v63 + 2, v65, (char *)v24);
            }
            if ( v67 )
            {
              v25 = -1;
              do
                ++v25;
              while ( v67[v25] );
              std::wstring::_Assign<unsigned short>(v22 + 29, v67, (char *)v25);
            }
            v26 = (__int64 *)(a6 + 9);
            std::shared_ptr<OsConfigSettingResult>::operator=(a6 + 9, &v63);
            if ( v64 )
              std::_Ref_count_base::_Decref(v64);
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v67);
            v27 = &v65;
LABEL_97:
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v27);
            v57 = 0;
            p_lpSubKey = (char ***)&v57;
            v74 = 0;
            v75 = 1;
            RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"ExcludeList", (unsigned __int16 **)&v74);
            wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
            if ( RegistryString != -2147024894 && RegistryString < 0 )
            {
              v36 = 738;
LABEL_100:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v36,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                (const char *)(unsigned int)RegistryString,
                phkResult);
LABEL_101:
              v23 = &v57;
              goto LABEL_58;
            }
            Context = 0;
            for ( i = v57; ; i = 0 )
            {
              v39 = wcstok_s(i, L",", &Context);
              if ( !v39 )
                break;
              v38 = *v26;
              std::wstring::wstring((__int64)&p_lpSubKey, (__int64)v39);
              std::vector<std::wstring>::push_back(v38 + 112, &p_lpSubKey);
              std::wstring::_Tidy_deallocate(&p_lpSubKey);
            }
            if ( v16 == 10 )
            {
              *(_QWORD *)v56 = 0;
              p_lpSubKey = (char ***)v56;
              v74 = 0;
              v75 = 1;
              RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"ObjectType", (unsigned __int16 **)&v74);
              wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
              if ( RegistryString < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2FA,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                  (const char *)(unsigned int)RegistryString,
                  phkResult);
LABEL_108:
                v40 = v56;
LABEL_109:
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v40);
                goto LABEL_101;
              }
              if ( (_DWORD)v58 == 20 )
              {
                v58 = 0;
                p_lpSubKey = (char ***)&v58;
                v74 = 0;
                v75 = 1;
                RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"ObjectId", (unsigned __int16 **)&v74);
                wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
                if ( RegistryString < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x303,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                    (const char *)(unsigned int)RegistryString,
                    phkResult);
LABEL_113:
                  v41 = (LPCWSTR *)&v58;
LABEL_114:
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v41);
                  goto LABEL_108;
                }
                std::make_shared<SCDDynamicObjectSchema,>(&p_lpSubKey);
                v42 = p_lpSubKey;
                if ( !p_lpSubKey )
                {
                  RegistryString = -2147024882;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x306,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                    (const char *)0x8007000ELL,
                    phkResult);
                  if ( v74 )
                    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v74);
                  goto LABEL_113;
                }
                v43 = -1;
                do
                  ++v43;
                while ( *(_WORD *)(*(_QWORD *)v56 + 2 * v43) );
                std::wstring::_Assign<unsigned short>((char **)p_lpSubKey + 2, *(const void **)v56, (char *)v43);
                do
                  ++v10;
                while ( v58[v10] );
                std::wstring::_Assign<unsigned short>((char **)v42 + 9, v58, (char *)v10);
                v44 = a6 + 12;
                std::shared_ptr<OsConfigSettingResult>::operator=(a6 + 12, &p_lpSubKey);
                if ( v74 )
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v74);
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v58);
              }
              else
              {
                std::make_shared<SCDObjectSchema,>(&p_lpSubKey);
                if ( !p_lpSubKey )
                {
                  RegistryString = -2147024882;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x30F,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                    (const char *)0x8007000ELL,
                    phkResult);
                  if ( v74 )
                    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v74);
                  goto LABEL_108;
                }
                do
                  ++v10;
                while ( *(_WORD *)(*(_QWORD *)v56 + 2 * v10) );
                std::wstring::_Assign<unsigned short>((char **)p_lpSubKey + 2, *(const void **)v56, (char *)v10);
                v44 = a6 + 12;
                std::shared_ptr<OsConfigSettingResult>::operator=(a6 + 12, &p_lpSubKey);
                if ( v74 )
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v74);
              }
              lpSubKey = 0;
              p_lpSubKey = (char ***)&lpSubKey;
              v74 = 0;
              v75 = 1;
              RegistryString = DCStringCchPrintfAllStrings(&v74, L"Objects\\%s", 1, *(_QWORD *)v56);
              wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
              if ( RegistryString < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x31B,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                  (const char *)(unsigned int)RegistryString,
                  phkResult);
LABEL_133:
                v41 = &lpSubKey;
                goto LABEL_114;
              }
              v63 = 0;
              p_lpSubKey = &v63;
              v74 = 0;
              v75 = 1;
              v45 = hKey;
              v46 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20119u, &v74);
              RegistryString = v46;
              if ( v46 > 0 )
                RegistryString = (unsigned __int16)v46 | 0x80070000;
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
              if ( RegistryString < 0 )
              {
                v47 = (unsigned int)RegistryString;
                v48 = 803;
LABEL_138:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v48,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                  (const char *)v47,
                  phkResult);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v63);
                goto LABEL_133;
              }
              ScenarioDefinitionObject = RegistrySCDStore::GetScenarioDefinitionObject(v72, v45, (HKEY)v63, *v44 + 48LL);
              RegistryString = ScenarioDefinitionObject;
              if ( ScenarioDefinitionObject < 0 )
              {
                v47 = (unsigned int)ScenarioDefinitionObject;
                v48 = 805;
                goto LABEL_138;
              }
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v63);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
              v50 = v56;
              goto LABEL_142;
            }
            if ( v16 != 11 || !v60 || (unsigned int)_o__wcsicmp(v60, L"2.0") )
            {
LABEL_156:
              v55 = 0;
              v51 = DCCDNUtil_GetRegistryDWORD(a3, a4, L"readonly", &v55);
              RegistryString = 0;
              if ( v51 != -2147024894 )
                RegistryString = v51;
              if ( RegistryString >= 0 )
              {
                *((_BYTE *)a6 + 64) = v55 != 0;
                v55 = 0;
                v52 = DCCDNUtil_GetRegistryDWORD(a3, a4, L"writeonly", &v55);
                RegistryString = 0;
                if ( v52 != -2147024894 )
                  RegistryString = v52;
                if ( RegistryString >= 0 )
                {
                  *((_BYTE *)a6 + 65) = v55 != 0;
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v57);
                  RegistryString = 0;
                  goto LABEL_165;
                }
                v36 = 846;
              }
              else
              {
                v36 = 833;
              }
              goto LABEL_100;
            }
            v60 = 0;
            p_lpSubKey = (char ***)&v60;
            v74 = 0;
            v75 = 1;
            RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"ObjectId", (unsigned __int16 **)&v74);
            wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
            if ( RegistryString >= 0 )
            {
              std::make_shared<SCDDynamicObjectSchema,>(&p_lpSubKey);
              if ( p_lpSubKey )
              {
                do
                  ++v10;
                while ( v60[v10] );
                std::wstring::_Assign<unsigned short>((char **)p_lpSubKey + 9, v60, (char *)v10);
                std::shared_ptr<OsConfigSettingResult>::operator=(a6 + 12, &p_lpSubKey);
                if ( v74 )
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v74);
                v50 = (unsigned int *)&v60;
LABEL_142:
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v50);
                goto LABEL_156;
              }
              RegistryString = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x331,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                (const char *)0x8007000ELL,
                phkResult);
              if ( v74 )
                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v74);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x32E,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
                (const char *)(unsigned int)RegistryString,
                phkResult);
            }
            v40 = (unsigned int *)&v60;
            goto LABEL_109;
          }
        }
        else if ( RegistryString >= 0 )
        {
          goto LABEL_36;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2BB,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
          (const char *)(unsigned int)RegistryString,
          phkResult);
LABEL_44:
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v67);
        goto LABEL_41;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
        (const char *)(unsigned int)RegistryString,
        phkResult);
LABEL_41:
      v23 = &v65;
LABEL_58:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v23);
      goto LABEL_165;
    }
LABEL_59:
    v62 = 0;
    p_lpSubKey = (char ***)&v62;
    v74 = 0;
    v75 = 1;
    RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"CspName", (unsigned __int16 **)&v74);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( RegistryString == -2147024894 )
    {
      if ( v16 == 10 )
      {
LABEL_61:
        v59 = 0;
        p_lpSubKey = (char ***)&v59;
        v74 = 0;
        v75 = 1;
        RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"UriPathOriginal", (unsigned __int16 **)&v74);
        wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
        if ( RegistryString == -2147024894
          && (p_lpSubKey = (char ***)&v59,
              v74 = 0,
              v75 = 1,
              RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"UriPath", (unsigned __int16 **)&v74),
              wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey),
              RegistryString == -2147024894)
          || RegistryString >= 0 )
        {
          v61 = 0;
          p_lpSubKey = (char ***)&v61;
          v74 = 0;
          v75 = 1;
          RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"GetUriPathOriginal", (unsigned __int16 **)&v74);
          wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
          if ( RegistryString == -2147024894
            && (p_lpSubKey = (char ***)&v61,
                v74 = 0,
                v75 = 1,
                RegistryString = DCCDNUtil_GetRegistryString(a3, a4, L"GetUriPath", (unsigned __int16 **)&v74),
                wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey),
                RegistryString == -2147024894)
            || RegistryString >= 0 )
          {
            std::make_shared<SCDCspProvider,>(&v63);
            v28 = v63;
            if ( v63 )
            {
              v29 = -1;
              do
                ++v29;
              while ( v62[v29] );
              std::wstring::_Assign<unsigned short>(v63 + 29, v62, (char *)v29);
              v30 = v61;
              if ( !v61 )
                goto LABEL_91;
              v31 = -1;
              do
                ++v31;
              while ( v61[v31] );
              if ( v31 )
              {
                if ( !v59 )
                  goto LABEL_90;
                v32 = -1;
                do
                  ++v32;
                while ( v59[v32] );
                if ( v32 )
                {
                  v33 = -1;
                  do
                    ++v33;
                  while ( v59[v33] );
                  std::wstring::_Assign<unsigned short>(v28 + 6, v59, (char *)v33);
                  v34 = v28 + 10;
                  v30 = v61;
                }
                else
                {
LABEL_90:
                  v34 = v28 + 10;
                }
              }
              else
              {
LABEL_91:
                v34 = v28 + 2;
                v30 = v59;
              }
              v35 = -1;
              do
                ++v35;
              while ( v30[v35] );
              std::wstring::_Assign<unsigned short>(v34, v30, (char *)v35);
              v26 = (__int64 *)(a6 + 9);
              std::shared_ptr<OsConfigSettingResult>::operator=(a6 + 9, &v63);
              if ( v64 )
                std::_Ref_count_base::_Decref(v64);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v61);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v59);
              v27 = &v62;
              goto LABEL_97;
            }
            RegistryString = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x28C,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
              (const char *)0x8007000ELL,
              phkResult);
            if ( v64 )
              std::_Ref_count_base::_Decref(v64);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x289,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
              (const char *)(unsigned int)RegistryString,
              phkResult);
          }
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v61);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x275,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
            (const char *)(unsigned int)RegistryString,
            phkResult);
        }
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v59);
LABEL_68:
        v23 = &v62;
        goto LABEL_58;
      }
    }
    else if ( RegistryString >= 0 )
    {
      goto LABEL_61;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x260,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
      (const char *)(unsigned int)RegistryString,
      phkResult);
    goto LABEL_68;
  }
  v8 = 521;
LABEL_3:
  RegistryString = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
    (const char *)0x80070057LL,
    phkResult);
  return (unsigned int)RegistryString;
}

```

## disassembly

```asm
0x1800f1080  push    rbp
0x1800f1082  push    rbx
0x1800f1083  push    rsi
0x1800f1084  push    rdi
0x1800f1085  push    r12
0x1800f1087  push    r13
0x1800f1089  push    r14
0x1800f108b  push    r15
0x1800f108d  lea     rbp, [rsp-0Fh]
0x1800f1092  sub     rsp, 0F8h
0x1800f1099  mov     rax, cs:__security_cookie
0x1800f10a0  xor     rax, rsp
0x1800f10a3  mov     [rbp+47h+var_50], rax
0x1800f10a7  mov     rsi, r9
0x1800f10aa  mov     r15, r8
0x1800f10ad  mov     [rbp+47h+hKey], rdx
0x1800f10b1  mov     [rbp+47h+var_78], rcx
0x1800f10b5  mov     rax, [rbp+47h+arg_20]
0x1800f10b9  mov     [rsp+130h+var_D8], rax
0x1800f10be  mov     r13, [rbp+47h+arg_28]
0x1800f10c2  xor     r14d, r14d
0x1800f10c5  test    rdx, rdx
0x1800f10c8  jnz     short loc_1800F10EC
0x1800f10ca  mov     edx, 209h; void *
0x1800f10cf  mov     ebx, 80070057h
0x1800f10d4  mov     rcx, [rbp+4Fh]; this
0x1800f10d8  mov     r9d, ebx; char *
0x1800f10db  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f10e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f10e7  jmp     loc_1800F1CE5
0x1800f10ec  test    r15, r15
0x1800f10ef  jnz     short loc_1800F10F8
0x1800f10f1  mov     edx, 20Ah
0x1800f10f6  jmp     short loc_1800F10CF
0x1800f10f8  test    rsi, rsi
0x1800f10fb  jnz     short loc_1800F1104
0x1800f10fd  mov     edx, 20Bh
0x1800f1102  jmp     short loc_1800F10CF
0x1800f1104  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f1108  mov     r8, rdi
0x1800f110b  inc     r8
0x1800f110e  cmp     [r9+r8*2], r14w
0x1800f1113  jnz     short loc_1800F110B
0x1800f1115  mov     rdx, rsi
0x1800f1118  mov     rcx, r13
0x1800f111b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800f1120  mov     [rbp+47h+var_90], r14
0x1800f1124  lea     rax, [rbp+47h+var_90]
0x1800f1128  mov     [rbp+47h+var_70], rax
0x1800f112c  mov     [rbp+47h+var_68], r14
0x1800f1130  mov     [rbp+47h+var_60], 1
0x1800f1134  lea     r9, [rbp+47h+var_68]; unsigned __int16 **
0x1800f1138  lea     r8, aDescription; "Description"
0x1800f113f  mov     rdx, rsi; unsigned __int16 *
0x1800f1142  mov     rcx, r15; HKEY
0x1800f1145  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800f114a  mov     ebx, eax
0x1800f114c  lea     rcx, [rbp+47h+var_70]
0x1800f1150  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800f1155  cmp     ebx, 80070002h
0x1800f115b  jz      short loc_1800F1185
0x1800f115d  test    ebx, ebx
0x1800f115f  jns     short loc_1800F116B
0x1800f1161  mov     r9d, ebx
0x1800f1164  mov     edx, 21Bh
0x1800f1169  jmp     short loc_1800F11AF
0x1800f116b  mov     rdx, [rbp+47h+var_90]
0x1800f116f  mov     r8, rdi
0x1800f1172  inc     r8
0x1800f1175  cmp     [rdx+r8*2], r14w
0x1800f117a  jnz     short loc_1800F1172
0x1800f117c  lea     rcx, [r13+20h]
0x1800f1180  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800f1185  mov     [rsp+130h+var_F8], r14d
0x1800f118a  lea     r9, [rsp+130h+var_F8]; unsigned int *
0x1800f118f  lea     r8, aDatatype_0; "DataType"
0x1800f1196  mov     rdx, rsi; unsigned __int16 *
0x1800f1199  mov     rcx, r15; HKEY
0x1800f119c  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800f11a1  mov     ebx, eax
0x1800f11a3  test    eax, eax
0x1800f11a5  jns     short loc_1800F11C4
0x1800f11a7  mov     edx, 224h; void *
0x1800f11ac  mov     r9d, eax; char *
0x1800f11af  mov     rcx, [rbp+4Fh]; this
0x1800f11b3  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f11ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f11bf  jmp     loc_1800F1CDC
0x1800f11c4  mov     [rsp+130h+var_100], r14d
0x1800f11c9  mov     dword ptr [rsp+130h+var_E8], r14d
0x1800f11ce  lea     r8, [rsp+130h+var_E8]
0x1800f11d3  lea     rdx, [rsp+130h+var_100]
0x1800f11d8  mov     ecx, [rsp+130h+var_F8]
0x1800f11dc  call    ?ConvertDCDataTypeToSCDDataType@@YAJW4DCScenarioSchemaDataType@@AEAW4SCD_SCHEMA_TYPE@@AEAW4SCD_SCHEMA_METATYPE@@@Z; ConvertDCDataTypeToSCDDataType(DCScenarioSchemaDataType,SCD_SCHEMA_TYPE &,SCD_SCHEMA_METATYPE &)
0x1800f11e1  mov     ebx, eax
0x1800f11e3  test    eax, eax
0x1800f11e5  jns     short loc_1800F11EE
0x1800f11e7  mov     edx, 228h
0x1800f11ec  jmp     short loc_1800F11AC
0x1800f11ee  mov     r12d, [rsp+130h+var_100]
0x1800f11f3  mov     [r13+58h], r12d
0x1800f11f7  mov     eax, dword ptr [rsp+130h+var_E8]
0x1800f11fb  mov     [r13+5Ch], eax
0x1800f11ff  mov     [rsp+130h+var_100], r14d
0x1800f1204  lea     r9, [rsp+130h+var_100]; unsigned int *
0x1800f1209  lea     r8, aProvider_0; "Provider"
0x1800f1210  mov     rdx, rsi; unsigned __int16 *
0x1800f1213  mov     rcx, r15; HKEY
0x1800f1216  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800f121b  test    eax, eax
0x1800f121d  js      short loc_1800F1225
0x1800f121f  mov     ebx, [rsp+130h+var_100]
0x1800f1223  jmp     short loc_1800F1283
0x1800f1225  cmp     eax, 80070002h
0x1800f122a  jz      loc_1800F1477
0x1800f1230  mov     [rbp+47h+var_98], r14
0x1800f1234  lea     rax, [rbp+47h+var_98]
0x1800f1238  mov     [rbp+47h+var_70], rax
0x1800f123c  mov     [rbp+47h+var_68], r14
0x1800f1240  mov     [rbp+47h+var_60], 1
0x1800f1244  lea     r9, [rbp+47h+var_68]; unsigned __int16 **
0x1800f1248  lea     r8, aProvider_0; "Provider"
0x1800f124f  mov     rdx, rsi; unsigned __int16 *
0x1800f1252  mov     rcx, r15; HKEY
0x1800f1255  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800f125a  mov     ebx, eax
0x1800f125c  lea     rcx, [rbp+47h+var_70]
0x1800f1260  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800f1265  test    ebx, ebx
0x1800f1267  jns     short loc_1800F1275
0x1800f1269  cmp     ebx, 80070002h
0x1800f126f  jnz     loc_1800F1450
0x1800f1275  mov     ebx, 1
0x1800f127a  lea     rcx, [rbp+47h+var_98]
0x1800f127e  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800f1283  sub     ebx, 1
0x1800f1286  jz      loc_1800F1477
0x1800f128c  sub     ebx, 1
0x1800f128f  jz      loc_1800F143E
0x1800f1295  cmp     ebx, 1
0x1800f1298  jz      short loc_1800F12AC
0x1800f129a  mov     ebx, 8000FFFFh
0x1800f129f  mov     r9d, ebx
0x1800f12a2  mov     edx, 2CFh
0x1800f12a7  jmp     loc_1800F11AF
0x1800f12ac  mov     [rbp+47h+var_B0], r14
0x1800f12b0  lea     rax, [rbp+47h+var_B0]
0x1800f12b4  mov     [rbp+47h+var_70], rax
0x1800f12b8  mov     [rbp+47h+var_68], r14
0x1800f12bc  mov     [rbp+47h+var_60], 1
0x1800f12c0  lea     r9, [rbp+47h+var_68]; unsigned __int16 **
0x1800f12c4  lea     r8, aRegpath_0; "RegPath"
0x1800f12cb  mov     rdx, rsi; unsigned __int16 *
0x1800f12ce  mov     rcx, r15; HKEY
0x1800f12d1  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800f12d6  mov     ebx, eax
0x1800f12d8  lea     rcx, [rbp+47h+var_70]
0x1800f12dc  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800f12e1  cmp     ebx, 80070002h
0x1800f12e7  jnz     loc_1800F1378
0x1800f12ed  cmp     r12d, 0Ah
0x1800f12f1  jnz     loc_1800F1380
0x1800f12f7  mov     [rbp+47h+var_A0], r14
0x1800f12fb  lea     rax, [rbp+47h+var_A0]
0x1800f12ff  mov     [rbp+47h+var_70], rax
0x1800f1303  mov     [rbp+47h+var_68], r14
0x1800f1307  mov     [rbp+47h+var_60], 1
0x1800f130b  lea     r9, [rbp+47h+var_68]
0x1800f130f  mov     rdx, rsi
0x1800f1312  mov     rcx, r15
0x1800f1315  call    _DCCDNUtil_GetRegistryStringWithBase64UriDecoding
0x1800f131a  mov     ebx, eax
0x1800f131c  lea     rcx, [rbp+47h+var_70]
0x1800f1320  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800f1325  cmp     ebx, 80070002h
0x1800f132b  jnz     short loc_1800F13A2
0x1800f132d  cmp     r12d, 0Ah
0x1800f1331  jnz     short loc_1800F13A6
0x1800f1333  lea     rcx, [rbp+47h+var_C0]
0x1800f1337  call    ??$make_shared@VSCDRegistryProvider@@$$V@std@@YA?AV?$shared_ptr@VSCDRegistryProvider@@@0@XZ; std::make_shared<SCDRegistryProvider,>(void)
0x1800f133c  nop
0x1800f133d  mov     rbx, [rbp+47h+var_C0]
0x1800f1341  test    rbx, rbx
0x1800f1344  jnz     loc_1800F13CA
0x1800f134a  mov     rcx, [rbp+4Fh]; this
0x1800f134e  mov     ebx, 8007000Eh
0x1800f1353  mov     r9d, ebx; char *
0x1800f1356  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f135d  mov     edx, 2BEh; void *
0x1800f1362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1367  nop
0x1800f1368  mov     rcx, [rbp+47h+var_B8]; this
0x1800f136c  test    rcx, rcx
0x1800f136f  jz      short loc_1800F13BF
0x1800f1371  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f1376  jmp     short loc_1800F13BF
0x1800f1378  test    ebx, ebx
0x1800f137a  jns     loc_1800F12F7
0x1800f1380  mov     rcx, [rbp+4Fh]; this
0x1800f1384  mov     r9d, ebx; char *
0x1800f1387  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f138e  mov     edx, 2AFh; void *
0x1800f1393  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1398  nop
0x1800f1399  lea     rcx, [rbp+47h+var_B0]
0x1800f139d  jmp     loc_1800F146D
0x1800f13a2  test    ebx, ebx
0x1800f13a4  jns     short loc_1800F1333
0x1800f13a6  mov     rcx, [rbp+4Fh]; this
0x1800f13aa  mov     r9d, ebx; char *
0x1800f13ad  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f13b4  mov     edx, 2BBh; void *
0x1800f13b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f13be  nop
0x1800f13bf  lea     rcx, [rbp+47h+var_A0]
0x1800f13c3  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800f13c8  jmp     short loc_1800F1399
0x1800f13ca  mov     rdx, [rbp+47h+var_B0]
0x1800f13ce  test    rdx, rdx
0x1800f13d1  jz      short loc_1800F13E9
0x1800f13d3  lea     rcx, [rbx+10h]
0x1800f13d7  mov     r8, rdi
0x1800f13da  inc     r8
0x1800f13dd  cmp     [rdx+r8*2], r14w
0x1800f13e2  jnz     short loc_1800F13DA
0x1800f13e4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800f13e9  mov     rdx, [rbp+47h+var_A0]
0x1800f13ed  test    rdx, rdx
0x1800f13f0  jz      short loc_1800F140B
0x1800f13f2  lea     rcx, [rbx+0E8h]
0x1800f13f9  mov     r8, rdi
0x1800f13fc  inc     r8
0x1800f13ff  cmp     [rdx+r8*2], r14w
0x1800f1404  jnz     short loc_1800F13FC
0x1800f1406  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800f140b  lea     r14, [r13+48h]
0x1800f140f  lea     rdx, [rbp+47h+var_C0]
0x1800f1413  mov     rcx, r14
0x1800f1416  call    ??4?$shared_ptr@VOsConfigSettingResult@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<OsConfigSettingResult>::operator=(std::shared_ptr<OsConfigSettingResult> const &)
0x1800f141b  nop
0x1800f141c  mov     rcx, [rbp+47h+var_B8]; this
0x1800f1420  test    rcx, rcx
0x1800f1423  jz      short loc_1800F142B
0x1800f1425  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f142a  nop
0x1800f142b  lea     rcx, [rbp+47h+var_A0]
0x1800f142f  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800f1434  nop
0x1800f1435  lea     rcx, [rbp+47h+var_B0]
0x1800f1439  jmp     loc_1800F1750
0x1800f143e  mov     ebx, 80004001h
0x1800f1443  mov     r9d, ebx
0x1800f1446  mov     edx, 2CCh
0x1800f144b  jmp     loc_1800F11AF
0x1800f1450  mov     rcx, [rbp+4Fh]; this
0x1800f1454  mov     r9d, ebx; char *
0x1800f1457  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f145e  mov     edx, 24Fh; void *
0x1800f1463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1468  nop
0x1800f1469  lea     rcx, [rbp+47h+var_98]
0x1800f146d  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800f1472  jmp     loc_1800F1CDC
0x1800f1477  mov     [rsp+130h+var_C8], r14
0x1800f147c  lea     rax, [rsp+130h+var_C8]
0x1800f1481  mov     [rbp+47h+var_70], rax
0x1800f1485  mov     [rbp+47h+var_68], r14
0x1800f1489  mov     [rbp+47h+var_60], 1
0x1800f148d  lea     r9, [rbp+47h+var_68]; unsigned __int16 **
0x1800f1491  lea     r8, aCspname_1; "CspName"
0x1800f1498  mov     rdx, rsi; unsigned __int16 *
0x1800f149b  mov     rcx, r15; HKEY
0x1800f149e  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800f14a3  mov     ebx, eax
0x1800f14a5  lea     rcx, [rbp+47h+var_70]
0x1800f14a9  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800f14ae  cmp     ebx, 80070002h
0x1800f14b4  jnz     loc_1800F1566
0x1800f14ba  cmp     r12d, 0Ah
0x1800f14be  jnz     loc_1800F156E
0x1800f14c4  mov     [rsp+130h+var_E0], r14
0x1800f14c9  lea     rax, [rsp+130h+var_E0]
0x1800f14ce  mov     [rbp+47h+var_70], rax
0x1800f14d2  mov     [rbp+47h+var_68], r14
0x1800f14d6  mov     [rbp+47h+var_60], 1
0x1800f14da  lea     r9, [rbp+47h+var_68]; unsigned __int16 **
0x1800f14de  lea     r8, aUripathorigina; "UriPathOriginal"
0x1800f14e5  mov     rdx, rsi; unsigned __int16 *
0x1800f14e8  mov     rcx, r15; HKEY
0x1800f14eb  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800f14f0  mov     ebx, eax
0x1800f14f2  lea     rcx, [rbp+47h+var_70]
0x1800f14f6  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800f14fb  cmp     ebx, 80070002h
0x1800f1501  jnz     short loc_1800F153D
0x1800f1503  lea     rax, [rsp+130h+var_E0]
0x1800f1508  mov     [rbp+47h+var_70], rax
0x1800f150c  mov     [rbp+47h+var_68], r14
0x1800f1510  mov     [rbp+47h+var_60], 1
0x1800f1514  lea     r9, [rbp+47h+var_68]; unsigned __int16 **
  ... truncated ...
```
