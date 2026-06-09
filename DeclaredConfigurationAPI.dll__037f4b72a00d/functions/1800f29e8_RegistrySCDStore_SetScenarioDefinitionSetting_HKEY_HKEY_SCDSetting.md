# RegistrySCDStore::SetScenarioDefinitionSetting(HKEY__ *,HKEY__ *,SCDSetting &)

- ea: `0x1800f29e8`
- end: `0x1800f32c7`
- name: `?SetScenarioDefinitionSetting@RegistrySCDStore@@AEAAJPEAUHKEY__@@0AEAVSCDSetting@@@Z`
- size: `2271`
- prototype: `int(RegistrySCDStore *__hidden this, HKEY, HKEY, struct SCDSetting *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f2730`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180013b44`
- `0x180014348`
- `0x1800143c8`
- `0x180018ac0`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x1800600bc`
- `0x1800ef2d8`
- `0x1800f2730`
- `0x1800f29e8`
- `0x1800f3448`
- `0x180100e3c`
- `0x18010136c`
- `0x18012d59c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800f3141`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800f3141`

## string_xrefs

- `0x1800f2d32`: `GetUriPath`
- `0x1800f2ca6`: `UriPath`
- `0x1800f2dbb`: `UriPath`
- `0x1800f2b1a`: `RegPath`
- `0x1800f2a34`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f2a84`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f2c53`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f2eef`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f2f86`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f30e0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f316b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f2ce4`: `UriPathOriginal`
- `0x1800f2dfc`: `UriPathOriginal`
- `0x1800f2d73`: `GetUriPathOriginal`
- `0x1800f3277`: `writeonly`
- `0x1800f3245`: `readonly`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RegistrySCDStore::SetScenarioDefinitionSetting(
        RegistrySCDStore *this,
        HKEY a2,
        HKEY a3,
        struct SCDSetting *a4)
{
  struct SCDSetting *v4; // rbx
  __int64 v8; // rdx
  unsigned int v9; // ebx
  const unsigned __int16 *v11; // rdx
  signed int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // r10
  __int64 v15; // rax
  __int64 v16; // rsi
  const unsigned __int16 *v17; // r9
  const unsigned __int16 *v18; // rdx
  __int64 v19; // rdi
  unsigned __int16 *v20; // rdx
  int v21; // esi
  __int64 v22; // rdx
  const unsigned __int16 *v23; // rdx
  __int64 v24; // rax
  const unsigned __int16 *v25; // rdi
  const unsigned __int16 *v26; // r9
  const unsigned __int16 *v27; // rdx
  const unsigned __int16 *v28; // r9
  const unsigned __int16 *v29; // rdx
  const unsigned __int16 *v30; // r9
  const unsigned __int16 *v31; // rdx
  const unsigned __int16 *v32; // r9
  const unsigned __int16 *v33; // rdx
  const unsigned __int16 *v34; // r9
  const unsigned __int16 *v35; // rdx
  const unsigned __int16 *v36; // r9
  const unsigned __int16 *v37; // rdx
  const unsigned __int16 *v38; // r9
  const unsigned __int16 *v39; // rdx
  __int64 v40; // rax
  _QWORD *v41; // rdx
  unsigned __int64 i; // rdi
  const unsigned __int16 *p_Src; // r9
  const unsigned __int16 *v44; // rdx
  int v45; // eax
  LPCWSTR **v46; // rcx
  const unsigned __int16 *v47; // r9
  const unsigned __int16 *v48; // rdx
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // r9
  const unsigned __int16 *v52; // rdx
  const unsigned __int16 *v53; // r9
  const unsigned __int16 *v54; // rdx
  __int64 v55; // rax
  const unsigned __int16 *v56; // r9
  const unsigned __int16 *v57; // rdx
  LSTATUS v58; // eax
  unsigned __int64 v59; // r9
  __int64 v60; // rdx
  int v61; // eax
  const unsigned __int16 *v62; // rdx
  __int64 v63; // rax
  const unsigned __int16 *v64; // r9
  const unsigned __int16 *v65; // rdx
  DWORD dwOptions; // [rsp+20h] [rbp-79h]
  char v67[8]; // [rsp+50h] [rbp-49h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-41h] BYREF
  __int64 v69; // [rsp+60h] [rbp-39h] BYREF
  LPCWSTR *Src; // [rsp+68h] [rbp-31h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-29h] BYREF
  char v72; // [rsp+78h] [rbp-21h]
  unsigned __int64 v73; // [rsp+80h] [rbp-19h]
  _BYTE v74[32]; // [rsp+88h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v4 = a4;
  if ( !a2 )
  {
    v8 = 997;
LABEL_3:
    v9 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
      (const char *)v9,
      dwOptions);
    return v9;
  }
  if ( !a3 )
  {
    v8 = 998;
    goto LABEL_3;
  }
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v11 = (const unsigned __int16 *)a4;
  else
    v11 = *(const unsigned __int16 **)a4;
  v12 = DCCDNUtil_SetRegistryDWORD(a3, v11, L"Provider", *(_DWORD *)(*((_QWORD *)a4 + 9) + 8LL));
  if ( v12 >= 0 )
  {
    v14 = *((_QWORD *)v4 + 9);
    switch ( *(_DWORD *)(v14 + 8) )
    {
      case 1:
        v24 = _RTDynamicCast_0(v14, 0, &SCDProvider `RTTI Type Descriptor', &SCDCspProvider `RTTI Type Descriptor', 0);
        v25 = (const unsigned __int16 *)v24;
        if ( !v24 )
        {
          v12 = -2147418113;
          v13 = 1011;
          goto LABEL_12;
        }
        v26 = (const unsigned __int16 *)(v24 + 232);
        if ( *(_QWORD *)(v24 + 256) > 7u )
          v26 = *(const unsigned __int16 **)v26;
        if ( *((_QWORD *)v4 + 3) <= 7u )
          v27 = (const unsigned __int16 *)v4;
        else
          v27 = *(const unsigned __int16 **)v4;
        v21 = DCCDNUtil_SetRegistryString(a3, v27, L"CspName", v26, 0);
        if ( v21 < 0 )
        {
          v22 = 1018;
          goto LABEL_49;
        }
        if ( *((_QWORD *)v25 + 4) )
        {
          v36 = v25 + 68;
          if ( *((_QWORD *)v25 + 20) > 7u )
            v36 = *(const unsigned __int16 **)v36;
          if ( *((_QWORD *)v4 + 3) <= 7u )
            v37 = (const unsigned __int16 *)v4;
          else
            v37 = *(const unsigned __int16 **)v4;
          v21 = DCCDNUtil_SetRegistryString(a3, v37, L"UriPath", v36, 0);
          if ( v21 < 0 )
          {
            v22 = 1027;
            goto LABEL_49;
          }
          v38 = v25 + 8;
          if ( *((_QWORD *)v25 + 5) > 7u )
            v38 = *(const unsigned __int16 **)v38;
          if ( *((_QWORD *)v4 + 3) <= 7u )
            v39 = (const unsigned __int16 *)v4;
          else
            v39 = *(const unsigned __int16 **)v4;
          v12 = DCCDNUtil_SetRegistryString(a3, v39, L"UriPathOriginal", v38, 0);
          if ( v12 < 0 )
          {
            v13 = 1033;
            goto LABEL_12;
          }
        }
        else
        {
          if ( *((_QWORD *)v25 + 8) )
          {
            v28 = v25 + 84;
            if ( *((_QWORD *)v25 + 24) > 7u )
              v28 = *(const unsigned __int16 **)v28;
            if ( *((_QWORD *)v4 + 3) <= 7u )
              v29 = (const unsigned __int16 *)v4;
            else
              v29 = *(const unsigned __int16 **)v4;
            v21 = DCCDNUtil_SetRegistryString(a3, v29, L"UriPath", v28, 0);
            if ( v21 < 0 )
            {
              v22 = 1044;
              goto LABEL_49;
            }
            v30 = v25 + 24;
            if ( *((_QWORD *)v25 + 9) > 7u )
              v30 = *(const unsigned __int16 **)v30;
            if ( *((_QWORD *)v4 + 3) <= 7u )
              v31 = (const unsigned __int16 *)v4;
            else
              v31 = *(const unsigned __int16 **)v4;
            v21 = DCCDNUtil_SetRegistryString(a3, v31, L"UriPathOriginal", v30, 0);
            if ( v21 < 0 )
            {
              v22 = 1050;
              goto LABEL_49;
            }
          }
          if ( *((_QWORD *)v25 + 12) )
          {
            v32 = v25 + 100;
            if ( *((_QWORD *)v25 + 28) > 7u )
              v32 = *(const unsigned __int16 **)v32;
            if ( *((_QWORD *)v4 + 3) <= 7u )
              v33 = (const unsigned __int16 *)v4;
            else
              v33 = *(const unsigned __int16 **)v4;
            v21 = DCCDNUtil_SetRegistryString(a3, v33, L"GetUriPath", v32, 0);
            if ( v21 < 0 )
            {
              v22 = 1060;
              goto LABEL_49;
            }
            v34 = v25 + 40;
            if ( *((_QWORD *)v25 + 13) > 7u )
              v34 = *(const unsigned __int16 **)v34;
            if ( *((_QWORD *)v4 + 3) <= 7u )
              v35 = (const unsigned __int16 *)v4;
            else
              v35 = *(const unsigned __int16 **)v4;
            v12 = DCCDNUtil_SetRegistryString(a3, v35, L"GetUriPathOriginal", v34, 0);
            if ( v12 < 0 )
            {
              v13 = 1066;
              goto LABEL_12;
            }
          }
        }
        break;
      case 2:
        v9 = -2147467263;
        v8 = 1104;
        goto LABEL_4;
      case 3:
        v15 = _RTDynamicCast_0(
                v14,
                0,
                &SCDProvider `RTTI Type Descriptor',
                &SCDRegistryProvider `RTTI Type Descriptor',
                0);
        v16 = v15;
        if ( !v15 )
        {
          v12 = -2147418113;
          v13 = 1074;
          goto LABEL_12;
        }
        v17 = (const unsigned __int16 *)(v15 + 16);
        if ( *(_QWORD *)(v15 + 40) > 7u )
          v17 = *(const unsigned __int16 **)v17;
        if ( *((_QWORD *)v4 + 3) <= 7u )
          v18 = (const unsigned __int16 *)v4;
        else
          v18 = *(const unsigned __int16 **)v4;
        v12 = DCCDNUtil_SetRegistryString(a3, v18, L"RegPath", v17, 0);
        if ( v12 < 0 )
        {
          v13 = 1081;
          goto LABEL_12;
        }
        v67[0] = 0;
        v19 = v16 + 232;
        if ( *((_QWORD *)v4 + 3) <= 7u )
          v20 = (unsigned __int16 *)v4;
        else
          v20 = *(unsigned __int16 **)v4;
        v21 = DCCDNUtil_SetRegistryStringWithBase64UriEncoding(a3, v20, dwOptions, (__int64)v67);
        if ( v21 < 0 )
        {
          v22 = 1090;
LABEL_49:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
            (const char *)(unsigned int)v21,
            dwOptions);
          return (unsigned int)v21;
        }
        if ( v67[0] )
        {
          if ( *(_QWORD *)(v19 + 24) > 7u )
            v19 = *(_QWORD *)v19;
          v23 = *((_QWORD *)v4 + 3) <= 7u ? (const unsigned __int16 *)v4 : *(const unsigned __int16 **)v4;
          v12 = DCCDNUtil_SetRegistryString(a3, v23, L"RegValueNameOriginal", (const unsigned __int16 *)v19, 0);
          if ( v12 < 0 )
          {
            v13 = 1099;
            goto LABEL_12;
          }
        }
        break;
      default:
        v12 = -2147418113;
        v13 = 1107;
        goto LABEL_12;
    }
    v40 = *((_QWORD *)v4 + 9);
    v41 = *(_QWORD **)(v40 + 112);
    if ( (__int64)(*(_QWORD *)(v40 + 120) - (_QWORD)v41) >> 5 )
    {
      std::wstring::wstring((__int64)&Src, v41);
      for ( i = 1;
            i < (__int64)(*(_QWORD *)(*((_QWORD *)v4 + 9) + 120LL) - *(_QWORD *)(*((_QWORD *)v4 + 9) + 112LL)) >> 5;
            ++i )
      {
        std::wstring::_Append<unsigned short>(&Src);
        std::wstring::_Append<unsigned short>(&Src);
      }
      p_Src = (const unsigned __int16 *)&Src;
      if ( v73 > 7 )
        p_Src = (const unsigned __int16 *)Src;
      if ( *((_QWORD *)v4 + 3) <= 7u )
        v44 = (const unsigned __int16 *)v4;
      else
        v44 = *(const unsigned __int16 **)v4;
      v45 = DCCDNUtil_SetRegistryString(a3, v44, L"ExcludeList", p_Src, 0);
      v12 = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x467,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
          (const char *)(unsigned int)v45,
          dwOptions);
        v46 = &Src;
LABEL_173:
        std::wstring::_Tidy_deallocate(v46);
        return (unsigned int)v12;
      }
      std::wstring::_Tidy_deallocate(&Src);
    }
    std::wstring::wstring((__int64)v74);
    if ( *((_QWORD *)v4 + 6) )
    {
      v47 = (const unsigned __int16 *)((char *)v4 + 32);
      if ( *((_QWORD *)v4 + 7) > 7u )
        v47 = *(const unsigned __int16 **)v47;
      v48 = *((_QWORD *)v4 + 3) <= 7u ? (const unsigned __int16 *)v4 : *(const unsigned __int16 **)v4;
      v49 = DCCDNUtil_SetRegistryString(a3, v48, L"Description", v47, 0);
      v12 = v49;
      if ( v49 < 0 )
      {
        v50 = 1138;
LABEL_116:
        v51 = (unsigned int)v49;
LABEL_117:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v50,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
          (const char *)v51,
          dwOptions);
LABEL_172:
        v46 = (LPCWSTR **)v74;
        goto LABEL_173;
      }
    }
    LODWORD(lpSubKey) = 0;
    v49 = ConvertSCDDataTypeToDCDataType(*((unsigned int *)v4 + 22), *((unsigned int *)v4 + 23), &lpSubKey);
    v12 = v49;
    if ( v49 < 0 )
    {
      v50 = 1145;
      goto LABEL_116;
    }
    if ( *((_QWORD *)v4 + 3) <= 7u )
      v52 = (const unsigned __int16 *)v4;
    else
      v52 = *(const unsigned __int16 **)v4;
    v49 = DCCDNUtil_SetRegistryDWORD(a3, v52, L"DataType", (unsigned int)lpSubKey);
    v12 = v49;
    if ( v49 < 0 )
    {
      v50 = 1152;
      goto LABEL_116;
    }
    if ( *((_DWORD *)v4 + 22) == 10 )
    {
      v53 = (const unsigned __int16 *)(*((_QWORD *)v4 + 12) + 16LL);
      if ( *(_QWORD *)(*((_QWORD *)v4 + 12) + 40LL) > 7u )
        v53 = *(const unsigned __int16 **)v53;
      if ( *((_QWORD *)v4 + 3) <= 7u )
        v54 = (const unsigned __int16 *)v4;
      else
        v54 = *(const unsigned __int16 **)v4;
      v49 = DCCDNUtil_SetRegistryString(a3, v54, L"ObjectType", v53, 0);
      v12 = v49;
      if ( v49 < 0 )
      {
        v50 = 1161;
        goto LABEL_116;
      }
      if ( *((_DWORD *)v4 + 23) == 20 )
      {
        v55 = _RTDynamicCast_0(
                *((_QWORD *)v4 + 12),
                0,
                &SCDObjectSchema `RTTI Type Descriptor',
                &SCDDynamicObjectSchema `RTTI Type Descriptor',
                0);
        if ( !v55 )
        {
          v12 = -2147418113;
          v51 = 2147549183LL;
          v50 = 1166;
          goto LABEL_117;
        }
        v56 = (const unsigned __int16 *)(v55 + 72);
        if ( *(_QWORD *)(v55 + 96) > 7u )
          v56 = *(const unsigned __int16 **)v56;
        v57 = *((_QWORD *)v4 + 3) <= 7u ? (const unsigned __int16 *)v4 : *(const unsigned __int16 **)v4;
        v49 = DCCDNUtil_SetRegistryString(a3, v57, L"ObjectId", v56, 0);
        v12 = v49;
        if ( v49 < 0 )
        {
          v50 = 1173;
          goto LABEL_116;
        }
      }
      lpSubKey = 0;
      Src = &lpSubKey;
      phkResult = 0;
      v72 = 1;
      v12 = DCStringCchPrintfAllStrings(&phkResult, L"Objects\\%s", 1);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&Src);
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49D,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
          (const char *)(unsigned int)v12,
          dwOptions);
LABEL_143:
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
        goto LABEL_172;
      }
      v69 = 0;
      Src = (LPCWSTR *)&v69;
      phkResult = 0;
      v72 = 1;
      v58 = RegCreateKeyExW(a2, lpSubKey, 0, 0, 0, 0x2011Fu, 0, &phkResult, 0);
      v12 = v58;
      if ( v58 > 0 )
        v12 = (unsigned __int16)v58 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&Src);
      if ( v12 < 0 )
      {
        v59 = (unsigned int)v12;
        v60 = 1193;
LABEL_148:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v60,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
          (const char *)v59,
          dwOptions);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
        goto LABEL_143;
      }
      v61 = RegistrySCDStore::SetScenarioDefinitionObject(this, a2, v69, *((_QWORD *)v4 + 12) + 48LL);
      v12 = v61;
      if ( v61 < 0 )
      {
        v59 = (unsigned int)v61;
        v60 = 1195;
        goto LABEL_148;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
    }
    else if ( *((_DWORD *)v4 + 22) == 11 )
    {
      v63 = _RTDynamicCast_0(
              *((_QWORD *)v4 + 12),
              0,
              &SCDObjectSchema `RTTI Type Descriptor',
              &SCDDynamicObjectSchema `RTTI Type Descriptor',
              0);
      v64 = (const unsigned __int16 *)(v63 + 72);
      if ( *(_QWORD *)(v63 + 96) > 7u )
        v64 = *(const unsigned __int16 **)v64;
      v65 = *((_QWORD *)v4 + 3) <= 7u ? (const unsigned __int16 *)v4 : *(const unsigned __int16 **)v4;
      v49 = DCCDNUtil_SetRegistryString(a3, v65, L"ObjectId", v64, 0);
      v12 = v49;
      if ( v49 < 0 )
      {
        v50 = 1205;
        goto LABEL_116;
      }
    }
    if ( *((_BYTE *)v4 + 64)
      && (*((_QWORD *)v4 + 3) <= 7u ? (v62 = (const unsigned __int16 *)v4) : (v62 = *(const unsigned __int16 **)v4),
          v49 = DCCDNUtil_SetRegistryDWORD(a3, v62, L"readonly", 1u),
          v12 = v49,
          v49 < 0) )
    {
      v50 = 1214;
    }
    else
    {
      if ( !*((_BYTE *)v4 + 65) )
        goto LABEL_171;
      if ( *((_QWORD *)v4 + 3) > 7u )
        v4 = *(struct SCDSetting **)v4;
      v49 = DCCDNUtil_SetRegistryDWORD(a3, (const unsigned __int16 *)v4, L"writeonly", 1u);
      v12 = v49;
      if ( v49 >= 0 )
      {
LABEL_171:
        v12 = 0;
        goto LABEL_172;
      }
      v50 = 1223;
    }
    goto LABEL_116;
  }
  v13 = 1004;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
    (const char *)(unsigned int)v12,
    dwOptions);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800f29e8  push    rbp
0x1800f29ea  push    rbx
0x1800f29eb  push    rsi
0x1800f29ec  push    rdi
0x1800f29ed  push    r12
0x1800f29ef  push    r13
0x1800f29f1  push    r14
0x1800f29f3  push    r15
0x1800f29f5  lea     rbp, [rsp-1Fh]
0x1800f29fa  sub     rsp, 0B8h
0x1800f2a01  mov     rax, cs:__security_cookie
0x1800f2a08  xor     rax, rsp
0x1800f2a0b  mov     [rbp+57h+var_48], rax
0x1800f2a0f  mov     rbx, r9
0x1800f2a12  mov     r14, r8
0x1800f2a15  mov     r15, rdx
0x1800f2a18  mov     r12, rcx
0x1800f2a1b  xor     r13d, r13d
0x1800f2a1e  test    rdx, rdx
0x1800f2a21  jnz     short loc_1800F2A47
0x1800f2a23  mov     edx, 3E5h; void *
0x1800f2a28  mov     ebx, 80070057h
0x1800f2a2d  mov     rcx, [rbp+5Fh]; this
0x1800f2a31  mov     r9d, ebx; char *
0x1800f2a34  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f2a3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f2a40  mov     eax, ebx
0x1800f2a42  jmp     loc_1800F32A7
0x1800f2a47  test    r14, r14
0x1800f2a4a  jnz     short loc_1800F2A53
0x1800f2a4c  mov     edx, 3E6h
0x1800f2a51  jmp     short loc_1800F2A28
0x1800f2a53  mov     rax, [r9+48h]
0x1800f2a57  cmp     qword ptr [r9+18h], 7
0x1800f2a5c  jbe     short loc_1800F2A63
0x1800f2a5e  mov     rdx, [r9]
0x1800f2a61  jmp     short loc_1800F2A66
0x1800f2a63  mov     rdx, rbx; unsigned __int16 *
0x1800f2a66  mov     r9d, [rax+8]; unsigned int
0x1800f2a6a  lea     r8, aProvider_0; "Provider"
0x1800f2a71  mov     rcx, r14; HKEY
0x1800f2a74  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800f2a79  mov     edi, eax
0x1800f2a7b  test    eax, eax
0x1800f2a7d  jns     short loc_1800F2A9C
0x1800f2a7f  mov     edx, 3ECh; void *
0x1800f2a84  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f2a8b  mov     r9d, edi; char *
0x1800f2a8e  mov     rcx, [rbp+5Fh]; this
0x1800f2a92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f2a97  jmp     loc_1800F32A5
0x1800f2a9c  mov     r10, [rbx+48h]
0x1800f2aa0  mov     ecx, [r10+8]
0x1800f2aa4  sub     ecx, 1
0x1800f2aa7  jz      loc_1800F2BE0
0x1800f2aad  sub     ecx, 1
0x1800f2ab0  jz      loc_1800F2BD1
0x1800f2ab6  cmp     ecx, 1
0x1800f2ab9  jz      short loc_1800F2AC7
0x1800f2abb  mov     edi, 8000FFFFh
0x1800f2ac0  mov     edx, 453h
0x1800f2ac5  jmp     short loc_1800F2A84
0x1800f2ac7  mov     [rsp+0F0h+dwOptions], r13d
0x1800f2acc  lea     r9, ??_R0?AVSCDRegistryProvider@@@8; SCDRegistryProvider `RTTI Type Descriptor'
0x1800f2ad3  lea     r8, ??_R0?AVSCDProvider@@@8; SCDProvider `RTTI Type Descriptor'
0x1800f2ada  xor     edx, edx
0x1800f2adc  mov     rcx, r10
0x1800f2adf  call    __RTDynamicCast_0
0x1800f2ae4  mov     rsi, rax
0x1800f2ae7  test    rax, rax
0x1800f2aea  jnz     short loc_1800F2AF8
0x1800f2aec  mov     edi, 8000FFFFh
0x1800f2af1  mov     edx, 432h
0x1800f2af6  jmp     short loc_1800F2A84
0x1800f2af8  lea     r9, [rax+10h]
0x1800f2afc  cmp     qword ptr [r9+18h], 7
0x1800f2b01  jbe     short loc_1800F2B06
0x1800f2b03  mov     r9, [r9]; unsigned __int16 *
0x1800f2b06  cmp     qword ptr [rbx+18h], 7
0x1800f2b0b  jbe     short loc_1800F2B12
0x1800f2b0d  mov     rdx, [rbx]
0x1800f2b10  jmp     short loc_1800F2B15
0x1800f2b12  mov     rdx, rbx; unsigned __int16 *
0x1800f2b15  mov     byte ptr [rsp+0F0h+dwOptions], r13b; bool
0x1800f2b1a  lea     r8, aRegpath_0; "RegPath"
0x1800f2b21  mov     rcx, r14; HKEY
0x1800f2b24  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800f2b29  mov     edi, eax
0x1800f2b2b  test    eax, eax
0x1800f2b2d  jns     short loc_1800F2B39
0x1800f2b2f  mov     edx, 439h
0x1800f2b34  jmp     loc_1800F2A84
0x1800f2b39  mov     [rbp+57h+var_A0], r13b
0x1800f2b3d  lea     rdi, [rsi+0E8h]
0x1800f2b44  cmp     qword ptr [rdi+18h], 7
0x1800f2b49  jbe     short loc_1800F2B50
0x1800f2b4b  mov     r9, [rdi]
0x1800f2b4e  jmp     short loc_1800F2B53
0x1800f2b50  mov     r9, rdi
0x1800f2b53  cmp     qword ptr [rbx+18h], 7
0x1800f2b58  jbe     short loc_1800F2B5F
0x1800f2b5a  mov     rdx, [rbx]
0x1800f2b5d  jmp     short loc_1800F2B62
0x1800f2b5f  mov     rdx, rbx
0x1800f2b62  lea     rax, [rbp+57h+var_A0]
0x1800f2b66  mov     qword ptr [rsp+0F0h+samDesired], rax
0x1800f2b6b  mov     rcx, r14
0x1800f2b6e  call    _DCCDNUtil_SetRegistryStringWithBase64UriEncoding
0x1800f2b73  mov     esi, eax
0x1800f2b75  test    eax, eax
0x1800f2b77  jns     short loc_1800F2B83
0x1800f2b79  mov     edx, 442h
0x1800f2b7e  jmp     loc_1800F2C53
0x1800f2b83  cmp     [rbp+57h+var_A0], r13b
0x1800f2b87  jz      loc_1800F2E1B
0x1800f2b8d  cmp     qword ptr [rdi+18h], 7
0x1800f2b92  jbe     short loc_1800F2B97
0x1800f2b94  mov     rdi, [rdi]
0x1800f2b97  cmp     qword ptr [rbx+18h], 7
0x1800f2b9c  jbe     short loc_1800F2BA3
0x1800f2b9e  mov     rdx, [rbx]
0x1800f2ba1  jmp     short loc_1800F2BA6
0x1800f2ba3  mov     rdx, rbx; unsigned __int16 *
0x1800f2ba6  mov     byte ptr [rsp+0F0h+dwOptions], r13b; bool
0x1800f2bab  mov     r9, rdi; unsigned __int16 *
0x1800f2bae  lea     r8, aRegvaluenameor; "RegValueNameOriginal"
0x1800f2bb5  mov     rcx, r14; HKEY
0x1800f2bb8  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800f2bbd  mov     edi, eax
0x1800f2bbf  test    eax, eax
0x1800f2bc1  jns     loc_1800F2E1B
0x1800f2bc7  mov     edx, 44Bh
0x1800f2bcc  jmp     loc_1800F2A84
0x1800f2bd1  mov     ebx, 80004001h
0x1800f2bd6  mov     edx, 450h
0x1800f2bdb  jmp     loc_1800F2A2D
0x1800f2be0  mov     [rsp+0F0h+dwOptions], r13d
0x1800f2be5  lea     r9, ??_R0?AVSCDCspProvider@@@8; SCDCspProvider `RTTI Type Descriptor'
0x1800f2bec  lea     r8, ??_R0?AVSCDProvider@@@8; SCDProvider `RTTI Type Descriptor'
0x1800f2bf3  xor     edx, edx
0x1800f2bf5  mov     rcx, r10
0x1800f2bf8  call    __RTDynamicCast_0
0x1800f2bfd  mov     rdi, rax
0x1800f2c00  test    rax, rax
0x1800f2c03  jnz     short loc_1800F2C14
0x1800f2c05  mov     edi, 8000FFFFh
0x1800f2c0a  mov     edx, 3F3h
0x1800f2c0f  jmp     loc_1800F2A84
0x1800f2c14  lea     r9, [rax+0E8h]
0x1800f2c1b  cmp     qword ptr [r9+18h], 7
0x1800f2c20  jbe     short loc_1800F2C25
0x1800f2c22  mov     r9, [r9]; unsigned __int16 *
0x1800f2c25  cmp     qword ptr [rbx+18h], 7
0x1800f2c2a  jbe     short loc_1800F2C31
0x1800f2c2c  mov     rdx, [rbx]
0x1800f2c2f  jmp     short loc_1800F2C34
0x1800f2c31  mov     rdx, rbx; unsigned __int16 *
0x1800f2c34  mov     byte ptr [rsp+0F0h+dwOptions], r13b; int
0x1800f2c39  lea     r8, aCspname_1; "CspName"
0x1800f2c40  mov     rcx, r14; HKEY
0x1800f2c43  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800f2c48  mov     esi, eax
0x1800f2c4a  test    eax, eax
0x1800f2c4c  jns     short loc_1800F2C6D
0x1800f2c4e  mov     edx, 3FAh; void *
0x1800f2c53  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f2c5a  mov     r9d, esi; char *
0x1800f2c5d  mov     rcx, [rbp+5Fh]; this
0x1800f2c61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f2c66  mov     eax, esi
0x1800f2c68  jmp     loc_1800F32A7
0x1800f2c6d  cmp     [rdi+20h], r13
0x1800f2c71  jnz     loc_1800F2D96
0x1800f2c77  cmp     [rdi+40h], r13
0x1800f2c7b  jz      loc_1800F2D03
0x1800f2c81  lea     r9, [rdi+0A8h]
0x1800f2c88  cmp     qword ptr [r9+18h], 7
0x1800f2c8d  jbe     short loc_1800F2C92
0x1800f2c8f  mov     r9, [r9]; unsigned __int16 *
0x1800f2c92  cmp     qword ptr [rbx+18h], 7
0x1800f2c97  jbe     short loc_1800F2C9E
0x1800f2c99  mov     rdx, [rbx]
0x1800f2c9c  jmp     short loc_1800F2CA1
0x1800f2c9e  mov     rdx, rbx; unsigned __int16 *
0x1800f2ca1  mov     byte ptr [rsp+0F0h+dwOptions], r13b; bool
0x1800f2ca6  lea     r8, aUripath_1; "UriPath"
0x1800f2cad  mov     rcx, r14; HKEY
0x1800f2cb0  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800f2cb5  mov     esi, eax
0x1800f2cb7  test    eax, eax
0x1800f2cb9  jns     short loc_1800F2CC2
0x1800f2cbb  mov     edx, 414h
0x1800f2cc0  jmp     short loc_1800F2C53
0x1800f2cc2  lea     r9, [rdi+30h]
0x1800f2cc6  cmp     qword ptr [r9+18h], 7
0x1800f2ccb  jbe     short loc_1800F2CD0
0x1800f2ccd  mov     r9, [r9]; unsigned __int16 *
0x1800f2cd0  cmp     qword ptr [rbx+18h], 7
0x1800f2cd5  jbe     short loc_1800F2CDC
0x1800f2cd7  mov     rdx, [rbx]
0x1800f2cda  jmp     short loc_1800F2CDF
0x1800f2cdc  mov     rdx, rbx; unsigned __int16 *
0x1800f2cdf  mov     byte ptr [rsp+0F0h+dwOptions], r13b; bool
0x1800f2ce4  lea     r8, aUripathorigina; "UriPathOriginal"
0x1800f2ceb  mov     rcx, r14; HKEY
0x1800f2cee  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800f2cf3  mov     esi, eax
0x1800f2cf5  test    eax, eax
0x1800f2cf7  jns     short loc_1800F2D03
0x1800f2cf9  mov     edx, 41Ah
0x1800f2cfe  jmp     loc_1800F2C53
0x1800f2d03  cmp     [rdi+60h], r13
0x1800f2d07  jz      loc_1800F2E1B
0x1800f2d0d  lea     r9, [rdi+0C8h]
0x1800f2d14  cmp     qword ptr [r9+18h], 7
0x1800f2d19  jbe     short loc_1800F2D1E
0x1800f2d1b  mov     r9, [r9]; unsigned __int16 *
0x1800f2d1e  cmp     qword ptr [rbx+18h], 7
0x1800f2d23  jbe     short loc_1800F2D2A
0x1800f2d25  mov     rdx, [rbx]
0x1800f2d28  jmp     short loc_1800F2D2D
0x1800f2d2a  mov     rdx, rbx; unsigned __int16 *
0x1800f2d2d  mov     byte ptr [rsp+0F0h+dwOptions], r13b; bool
0x1800f2d32  lea     r8, aGeturipath; "GetUriPath"
0x1800f2d39  mov     rcx, r14; HKEY
0x1800f2d3c  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800f2d41  mov     esi, eax
0x1800f2d43  test    eax, eax
0x1800f2d45  jns     short loc_1800F2D51
0x1800f2d47  mov     edx, 424h
0x1800f2d4c  jmp     loc_1800F2C53
0x1800f2d51  lea     r9, [rdi+50h]
0x1800f2d55  cmp     qword ptr [r9+18h], 7
0x1800f2d5a  jbe     short loc_1800F2D5F
0x1800f2d5c  mov     r9, [r9]; unsigned __int16 *
0x1800f2d5f  cmp     qword ptr [rbx+18h], 7
0x1800f2d64  jbe     short loc_1800F2D6B
0x1800f2d66  mov     rdx, [rbx]
0x1800f2d69  jmp     short loc_1800F2D6E
0x1800f2d6b  mov     rdx, rbx; unsigned __int16 *
0x1800f2d6e  mov     byte ptr [rsp+0F0h+dwOptions], r13b; bool
0x1800f2d73  lea     r8, aGeturipathorig; "GetUriPathOriginal"
0x1800f2d7a  mov     rcx, r14; HKEY
0x1800f2d7d  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800f2d82  mov     edi, eax
0x1800f2d84  test    eax, eax
0x1800f2d86  jns     loc_1800F2E1B
0x1800f2d8c  mov     edx, 42Ah
0x1800f2d91  jmp     loc_1800F2A84
0x1800f2d96  lea     r9, [rdi+88h]
0x1800f2d9d  cmp     qword ptr [r9+18h], 7
0x1800f2da2  jbe     short loc_1800F2DA7
0x1800f2da4  mov     r9, [r9]; unsigned __int16 *
0x1800f2da7  cmp     qword ptr [rbx+18h], 7
0x1800f2dac  jbe     short loc_1800F2DB3
0x1800f2dae  mov     rdx, [rbx]
0x1800f2db1  jmp     short loc_1800F2DB6
0x1800f2db3  mov     rdx, rbx; unsigned __int16 *
0x1800f2db6  mov     byte ptr [rsp+0F0h+dwOptions], r13b; bool
0x1800f2dbb  lea     r8, aUripath_1; "UriPath"
0x1800f2dc2  mov     rcx, r14; HKEY
0x1800f2dc5  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800f2dca  mov     esi, eax
0x1800f2dcc  test    eax, eax
0x1800f2dce  jns     short loc_1800F2DDA
0x1800f2dd0  mov     edx, 403h
0x1800f2dd5  jmp     loc_1800F2C53
0x1800f2dda  lea     r9, [rdi+10h]
0x1800f2dde  cmp     qword ptr [r9+18h], 7
0x1800f2de3  jbe     short loc_1800F2DE8
0x1800f2de5  mov     r9, [r9]; unsigned __int16 *
0x1800f2de8  cmp     qword ptr [rbx+18h], 7
0x1800f2ded  jbe     short loc_1800F2DF4
0x1800f2def  mov     rdx, [rbx]
0x1800f2df2  jmp     short loc_1800F2DF7
0x1800f2df4  mov     rdx, rbx; unsigned __int16 *
0x1800f2df7  mov     byte ptr [rsp+0F0h+dwOptions], r13b; bool
0x1800f2dfc  lea     r8, aUripathorigina; "UriPathOriginal"
0x1800f2e03  mov     rcx, r14; HKEY
0x1800f2e06  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800f2e0b  mov     edi, eax
0x1800f2e0d  test    eax, eax
0x1800f2e0f  jns     short loc_1800F2E1B
0x1800f2e11  mov     edx, 409h
0x1800f2e16  jmp     loc_1800F2A84
0x1800f2e1b  mov     rax, [rbx+48h]
0x1800f2e1f  mov     rdx, [rax+70h]
0x1800f2e23  mov     rcx, [rax+78h]
0x1800f2e27  sub     rcx, rdx
0x1800f2e2a  sar     rcx, 5
0x1800f2e2e  mov     esi, 1
0x1800f2e33  test    rcx, rcx
0x1800f2e36  jz      loc_1800F2F13
0x1800f2e3c  lea     rcx, [rbp+57h+Src]
0x1800f2e40  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800f2e45  nop
0x1800f2e46  mov     edi, esi
0x1800f2e48  mov     rax, [rbx+48h]
0x1800f2e4c  mov     rcx, [rax+78h]
0x1800f2e50  sub     rcx, [rax+70h]
  ... truncated ...
```
