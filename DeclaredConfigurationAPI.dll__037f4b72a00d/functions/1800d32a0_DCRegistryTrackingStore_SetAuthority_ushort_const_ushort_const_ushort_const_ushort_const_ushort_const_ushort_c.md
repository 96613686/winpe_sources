# DCRegistryTrackingStore::SetAuthority(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,tagVARIANT *,bool)

- ea: `0x1800d32a0`
- end: `0x1800d3acc`
- name: `?SetAuthority@DCRegistryTrackingStore@@UEAAJPEBG00000KPEAUtagVARIANT@@_N@Z`
- size: `2092`
- prototype: `__int64 __fastcall(DCRegistryTrackingStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct tagVARIANT *, bool)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x180019d38`
- `0x18001bc98`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18001def8`
- `0x18004bc88`
- `0x1800600bc`
- `0x1800d1b94`
- `0x1800d32a0`
- `0x180100c90`
- `0x180100e3c`
- `0x180100fd8`
- `0x1801011cc`
- `0x18010136c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800d33f6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d35b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d35b8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800d3909`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800d3909`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800d38e2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800d38e2`

## string_xrefs

- `0x1800d330b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d3551`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d370f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d3a09`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DCRegistryTrackingStore::SetAuthority(
        DCRegistryTrackingStore *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        unsigned int a8,
        struct tagVARIANT *a9,
        bool a10)
{
  __int64 v13; // rdx
  signed int v14; // ebx
  char IsEnabled; // al
  __int64 v17; // r8
  __int64 v18; // r8
  char **v19; // r9
  _QWORD *v20; // rax
  int v21; // r9d
  char **v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  char **v25; // rax
  char **v26; // rcx
  char v27; // al
  char **v28; // rax
  __int64 v29; // rdx
  char **v30; // r9
  LSTATUS v31; // eax
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // rcx
  const wchar_t *v35; // r8
  int LBound; // eax
  int v37; // eax
  signed int v38; // esi
  const unsigned __int16 *v39; // r9
  const BYTE *pbVal; // r9
  const unsigned __int16 *bstrVal; // r9
  int dwOptions; // [rsp+20h] [rbp-308h]
  int dwOptionsa; // [rsp+20h] [rbp-308h]
  int dwOptionsb; // [rsp+20h] [rbp-308h]
  HKEY v45; // [rsp+50h] [rbp-2D8h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-2D0h] BYREF
  LONG plLbound; // [rsp+60h] [rbp-2C8h] BYREF
  void *p_lpSubKey; // [rsp+68h] [rbp-2C0h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-2B8h] BYREF
  char v50; // [rsp+78h] [rbp-2B0h]
  LONG plUbound; // [rsp+80h] [rbp-2A8h] BYREF
  char *v52[3]; // [rsp+88h] [rbp-2A0h] BYREF
  unsigned __int64 v53; // [rsp+A0h] [rbp-288h]
  char *v54[3]; // [rsp+A8h] [rbp-280h] BYREF
  unsigned __int64 v55; // [rsp+C0h] [rbp-268h]
  unsigned __int16 v56[264]; // [rsp+D0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl)
    && !a2 )
  {
    v13 = 51;
LABEL_4:
    v14 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)0x80070057LL,
      dwOptionsa);
    return (unsigned int)v14;
  }
  if ( !a3 )
  {
    v13 = 53;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v13 = 54;
    goto LABEL_4;
  }
  if ( !a5 )
  {
    v13 = 55;
    goto LABEL_4;
  }
  if ( !a6 )
  {
    v13 = 56;
    goto LABEL_4;
  }
  if ( !a7 )
  {
    v13 = 57;
    goto LABEL_4;
  }
  std::wstring::wstring((__int64)v54);
  std::wstring::wstring((__int64)v52);
  try
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
    v17 = -1;
    if ( IsEnabled )
    {
      do
        ++v17;
      while ( a3[v17] );
      std::wstring::_Assign<unsigned short>(v54, a3, (char *)v17);
      v19 = v54;
      if ( v55 > 7 )
        v19 = (char **)v54[0];
      v20 = (_QWORD *)std::wstring::end(v54, &plLbound, v18, v19);
      v22 = v54;
      if ( v55 > 7 )
        LODWORD(v22) = v54[0];
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)&plUbound,
        (_DWORD)v22,
        *v20,
        v21,
        *(__int64 *)&_o_towlower);
      std::wstring::operator=(v52, v54);
    }
    else
    {
      do
        ++v17;
      while ( a3[v17] );
      std::wstring::_Assign<unsigned short>(v52, a3, (char *)v17);
    }
    v25 = *(char ***)std::wstring::end(v52, &plLbound, v23, v24);
    v26 = v52;
    if ( v53 > 7 )
      v26 = (char **)v52[0];
    while ( v26 != v25 )
    {
      if ( *(_WORD *)v26 == 47 )
        *(_WORD *)v26 = 92;
      v26 = (char **)((char *)v26 + 2);
    }
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)0x8007000ELL,
      dwOptions);
    std::wstring::_Tidy_deallocate(v52);
    std::wstring::_Tidy_deallocate(v54);
    return 2147942414LL;
  }
  lpSubKey = 0;
  v27 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
  phkResult = 0;
  v50 = 1;
  if ( v27 )
  {
    v28 = v52;
    if ( v53 > 7 )
      v28 = (char **)v52[0];
    p_lpSubKey = &lpSubKey;
    v14 = DCStringCchPrintfAllStrings(&phkResult, qword_18018A5F0, 2, a2, v28);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( v14 < 0 )
    {
      v29 = 93;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)(unsigned int)v14,
        dwOptionsa);
LABEL_105:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
      std::wstring::_Tidy_deallocate(v52);
      std::wstring::_Tidy_deallocate(v54);
      return (unsigned int)v14;
    }
  }
  else
  {
    v30 = v52;
    if ( v53 > 7 )
      v30 = (char **)v52[0];
    p_lpSubKey = &lpSubKey;
    v14 = DCStringCchPrintfAllStrings(&phkResult, qword_18018A5E8, 1, v30);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( v14 < 0 )
    {
      v29 = 101;
      goto LABEL_43;
    }
  }
  v45 = 0;
  p_lpSubKey = &v45;
  phkResult = 0;
  v50 = 1;
  v31 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2011Fu, 0, &phkResult, 0);
  v14 = v31;
  if ( v31 > 0 )
    v14 = (unsigned __int16)v31 | 0x80070000;
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
  if ( v14 < 0 )
  {
    v32 = (unsigned int)v14;
    v33 = 114;
LABEL_104:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)v32,
      dwOptionsb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v45);
    goto LABEL_105;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    v35 = (const wchar_t *)v54;
    if ( v55 > 7 )
      v35 = (const wchar_t *)v54[0];
    LBound = DCRegistryTrackingStore::MapPMCspToRegistryProviderPathIfApply(
               v34,
               (__int64)a2,
               v35,
               (__int64)a4,
               (int)a5,
               &v45);
    v14 = LBound;
    if ( LBound < 0 )
    {
      v33 = 118;
LABEL_103:
      v32 = (unsigned int)LBound;
      goto LABEL_104;
    }
  }
  LBound = StringCchPrintfW(v56, 0x104u, L"%s\\%s", a4, a5);
  v14 = LBound;
  if ( LBound < 0 )
  {
    v33 = 128;
    goto LABEL_103;
  }
  LBound = DCCDNUtil_SetRegistryString(v45, v56, L"ducumentContext", a6, 0);
  v14 = LBound;
  if ( LBound < 0 )
  {
    v33 = 130;
    goto LABEL_103;
  }
  LBound = DCCDNUtil_SetRegistryString(v45, v56, L"ducumentVersion", a7, 0);
  v14 = LBound;
  if ( LBound < 0 )
  {
    v33 = 131;
    goto LABEL_103;
  }
  if ( !a9 )
    goto LABEL_98;
  v37 = DCCDNUtil_SetRegistryDWORD(v45, v56, L"typeStored", a8);
  v38 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)(unsigned int)v37,
      dwOptionsb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v45);
    v14 = v38;
    goto LABEL_105;
  }
  switch ( a8 )
  {
    case 1u:
      bstrVal = a9->bstrVal;
      if ( bstrVal )
      {
        LBound = DCCDNUtil_SetRegistryString(v45, v56, L"value", bstrVal, 0);
        v14 = LBound;
        if ( LBound < 0 )
        {
          v33 = 149;
          goto LABEL_103;
        }
      }
      else
      {
        LBound = DCCDNUtil_SetRegistryString(v45, v56, L"value", &word_180142E98, 0);
        v14 = LBound;
        if ( LBound < 0 )
        {
          v33 = 145;
          goto LABEL_103;
        }
      }
      goto LABEL_98;
    case 3u:
      plLbound = 0;
      plUbound = 0;
      LBound = SafeArrayGetLBound(a9->parray, 1u, &plLbound);
      v14 = LBound;
      if ( LBound < 0 )
      {
        v33 = 156;
        goto LABEL_103;
      }
      LBound = SafeArrayGetUBound(a9->parray, 1u, &plUbound);
      v14 = LBound;
      if ( LBound < 0 )
      {
        v33 = 157;
        goto LABEL_103;
      }
      LBound = DCCDNUtil_SetRegistryBinary(v45, v56, L"value", a9->pbVal, plUbound - plLbound + 1);
      v14 = LBound;
      if ( LBound < 0 )
      {
        v33 = 161;
        goto LABEL_103;
      }
      goto LABEL_98;
    case 4u:
      LBound = DCCDNUtil_SetRegistryDWORD(v45, v56, L"value", a9->lVal);
      v14 = LBound;
      if ( LBound < 0 )
      {
        v33 = 165;
        goto LABEL_103;
      }
      goto LABEL_98;
    case 5u:
      goto LABEL_98;
    case 6u:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        LBound = DCCDNUtil_SetRegistryQWORD(v45, v56, L"value", a9->llVal);
        v14 = LBound;
        if ( LBound < 0 )
        {
          v33 = 172;
          goto LABEL_103;
        }
        goto LABEL_98;
      }
      goto LABEL_73;
  }
  if ( a8 != 7 )
  {
    if ( a8 != 8 )
    {
LABEL_69:
      v14 = -2147418113;
      v32 = 2147549183LL;
      v33 = 206;
      goto LABEL_104;
    }
LABEL_73:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    {
      v39 = a9->bstrVal;
      if ( v39 )
      {
        LBound = DCCDNUtil_SetRegistryString(v45, v56, L"value", v39, 0);
        v14 = LBound;
        if ( LBound < 0 )
        {
          v33 = 186;
          goto LABEL_103;
        }
      }
      else
      {
        LBound = DCCDNUtil_SetRegistryString(v45, v56, L"value", &word_180142E98, 1);
        v14 = LBound;
        if ( LBound < 0 )
        {
          v33 = 182;
          goto LABEL_103;
        }
      }
      goto LABEL_98;
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    goto LABEL_69;
  pbVal = a9->pbVal;
  if ( pbVal )
  {
    LBound = DCCDNUtil_SetRegistryMultiString(v45, v56, L"value", pbVal);
    v14 = LBound;
    if ( LBound < 0 )
    {
      v33 = 201;
      goto LABEL_103;
    }
  }
  else
  {
    LBound = DCCDNUtil_SetRegistryMultiString(v45, v56, L"value", (const BYTE *)&dword_180154494);
    v14 = LBound;
    if ( LBound < 0 )
    {
      v33 = 197;
      goto LABEL_103;
    }
  }
LABEL_98:
  if ( a10 )
  {
    LBound = DCCDNUtil_SetRegistryString(v45, 0, L"authorityId", a4, 0);
    v14 = LBound;
    if ( LBound < 0 )
    {
      v33 = 214;
      goto LABEL_103;
    }
    LBound = DCCDNUtil_SetRegistryString(v45, 0, L"documentId", a5, 0);
    v14 = LBound;
    if ( LBound < 0 )
    {
      v33 = 215;
      goto LABEL_103;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v45);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
  std::wstring::_Tidy_deallocate(v52);
  std::wstring::_Tidy_deallocate(v54);
  return 0;
}

```

## disassembly

```asm
0x1800d32a0  push    rbx
0x1800d32a2  push    rsi
0x1800d32a3  push    rdi
0x1800d32a4  push    r12
0x1800d32a6  push    r13
0x1800d32a8  push    r14
0x1800d32aa  push    r15
0x1800d32ac  sub     rsp, 2F0h
0x1800d32b3  mov     rax, cs:__security_cookie
0x1800d32ba  xor     rax, rsp
0x1800d32bd  mov     [rsp+328h+var_48], rax
0x1800d32c5  mov     r14, r9
0x1800d32c8  mov     rbx, r8
0x1800d32cb  mov     rsi, rdx
0x1800d32ce  mov     r15, [rsp+328h+arg_20]
0x1800d32d6  mov     r12, [rsp+328h+arg_28]
0x1800d32de  mov     r13, [rsp+328h+arg_30]
0x1800d32e6  mov     rdi, [rsp+328h+arg_40]
0x1800d32ee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800d32f5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d32fa  test    al, al
0x1800d32fc  jz      short loc_1800D3329
0x1800d32fe  test    rsi, rsi
0x1800d3301  jnz     short loc_1800D3329
0x1800d3303  lea     edx, [rsi+33h]; void *
0x1800d3306  mov     ebx, 80070057h
0x1800d330b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d3312  mov     r9d, ebx; char *
0x1800d3315  mov     rcx, [rsp+328h]; this
0x1800d331d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3322  mov     eax, ebx
0x1800d3324  jmp     loc_1800D3AA9
0x1800d3329  test    rbx, rbx
0x1800d332c  jnz     short loc_1800D3333
0x1800d332e  lea     edx, [rbx+35h]
0x1800d3331  jmp     short loc_1800D3306
0x1800d3333  test    r14, r14
0x1800d3336  jnz     short loc_1800D333E
0x1800d3338  lea     edx, [r14+36h]
0x1800d333c  jmp     short loc_1800D3306
0x1800d333e  test    r15, r15
0x1800d3341  jnz     short loc_1800D3349
0x1800d3343  lea     edx, [r15+37h]
0x1800d3347  jmp     short loc_1800D3306
0x1800d3349  test    r12, r12
0x1800d334c  jnz     short loc_1800D3355
0x1800d334e  lea     edx, [r12+38h]
0x1800d3353  jmp     short loc_1800D3306
0x1800d3355  test    r13, r13
0x1800d3358  jnz     short loc_1800D3360
0x1800d335a  lea     edx, [r13+39h]
0x1800d335e  jmp     short loc_1800D3306
0x1800d3360  lea     rcx, [rsp+328h+var_280]
0x1800d3368  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d336d  nop
0x1800d336e  lea     rcx, [rsp+328h+var_2A0]
0x1800d3376  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d337b  nop
0x1800d337c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800d3383  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d3388  xor     ecx, ecx
0x1800d338a  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d338e  test    al, al
0x1800d3390  jz      loc_1800D3429
0x1800d3396  inc     r8
0x1800d3399  cmp     [rbx+r8*2], cx
0x1800d339e  jnz     short loc_1800D3396
0x1800d33a0  mov     rdx, rbx
0x1800d33a3  lea     rcx, [rsp+328h+var_280]
0x1800d33ab  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d33b0  lea     r9, [rsp+328h+var_280]
0x1800d33b8  cmp     [rsp+328h+var_268], 7
0x1800d33c1  cmova   r9, [rsp+328h+var_280]
0x1800d33ca  lea     rdx, [rsp+328h+plLbound]
0x1800d33cf  lea     rcx, [rsp+328h+var_280]
0x1800d33d7  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800d33dc  lea     rdx, [rsp+328h+var_280]
0x1800d33e4  cmp     [rsp+328h+var_268], 7
0x1800d33ed  cmova   rdx, [rsp+328h+var_280]
0x1800d33f6  mov     rcx, cs:__imp__o_towlower
0x1800d33fd  mov     qword ptr [rsp+328h+dwOptions], rcx
0x1800d3402  mov     r8, [rax]
0x1800d3405  lea     rcx, [rsp+328h+plUbound]
0x1800d340d  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x1800d3412  lea     rdx, [rsp+328h+var_280]
0x1800d341a  lea     rcx, [rsp+328h+var_2A0]
0x1800d3422  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800d3427  jmp     short loc_1800D3443
0x1800d3429  inc     r8
0x1800d342c  cmp     [rbx+r8*2], cx
0x1800d3431  jnz     short loc_1800D3429
0x1800d3433  mov     rdx, rbx
0x1800d3436  lea     rcx, [rsp+328h+var_2A0]
0x1800d343e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d3443  lea     rdx, [rsp+328h+plLbound]
0x1800d3448  lea     rcx, [rsp+328h+var_2A0]
0x1800d3450  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800d3455  mov     rax, [rax]
0x1800d3458  lea     rcx, [rsp+328h+var_2A0]
0x1800d3460  cmp     [rsp+328h+var_288], 7
0x1800d3469  cmova   rcx, [rsp+328h+var_2A0]
0x1800d3472  jmp     short loc_1800D3483
0x1800d3474  cmp     word ptr [rcx], 2Fh ; '/'
0x1800d3478  jnz     short loc_1800D347F
0x1800d347a  mov     word ptr [rcx], 5Ch ; '\'
0x1800d347f  add     rcx, 2
0x1800d3483  cmp     rcx, rax
0x1800d3486  jnz     short loc_1800D3474
0x1800d3488  xor     ebx, ebx
0x1800d348a  mov     [rsp+328h+lpSubKey], rbx
0x1800d348f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800d3496  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d349b  mov     [rsp+328h+var_2B8], rbx
0x1800d34a0  mov     [rsp+328h+var_2B0], 1
0x1800d34a5  test    al, al
0x1800d34a7  jz      short loc_1800D3501
0x1800d34a9  lea     rax, [rsp+328h+var_2A0]
0x1800d34b1  cmp     [rsp+328h+var_288], 7
0x1800d34ba  cmova   rax, [rsp+328h+var_2A0]
0x1800d34c3  lea     rcx, [rsp+328h+lpSubKey]
0x1800d34c8  mov     [rsp+328h+var_2C0], rcx
0x1800d34cd  mov     qword ptr [rsp+328h+dwOptions], rax
0x1800d34d2  mov     r9, rsi
0x1800d34d5  lea     r8d, [rbx+2]
0x1800d34d9  mov     rdx, cs:qword_18018A5F0
0x1800d34e0  lea     rcx, [rsp+328h+var_2B8]
0x1800d34e5  call    DCStringCchPrintfAllStrings
0x1800d34ea  mov     ebx, eax
0x1800d34ec  lea     rcx, [rsp+328h+var_2C0]
0x1800d34f1  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d34f6  xor     ecx, ecx
0x1800d34f8  test    ebx, ebx
0x1800d34fa  jns     short loc_1800D356D
0x1800d34fc  lea     edx, [rcx+5Dh]
0x1800d34ff  jmp     short loc_1800D3551
0x1800d3501  lea     r9, [rsp+328h+var_2A0]
0x1800d3509  cmp     [rsp+328h+var_288], 7
0x1800d3512  cmova   r9, [rsp+328h+var_2A0]
0x1800d351b  lea     rax, [rsp+328h+lpSubKey]
0x1800d3520  mov     [rsp+328h+var_2C0], rax
0x1800d3525  mov     r8d, 1
0x1800d352b  mov     rdx, cs:qword_18018A5E8
0x1800d3532  lea     rcx, [rsp+328h+var_2B8]
0x1800d3537  call    DCStringCchPrintfAllStrings
0x1800d353c  mov     ebx, eax
0x1800d353e  lea     rcx, [rsp+328h+var_2C0]
0x1800d3543  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d3548  xor     ecx, ecx
0x1800d354a  test    ebx, ebx
0x1800d354c  jns     short loc_1800D356D
0x1800d354e  lea     edx, [rcx+65h]; void *
0x1800d3551  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d3558  mov     r9d, ebx; char *
0x1800d355b  mov     rcx, [rsp+328h]; this
0x1800d3563  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3568  jmp     loc_1800D3A29
0x1800d356d  mov     [rsp+328h+var_2D8], rcx
0x1800d3572  lea     rax, [rsp+328h+var_2D8]
0x1800d3577  mov     [rsp+328h+var_2C0], rax
0x1800d357c  mov     [rsp+328h+var_2B8], rcx
0x1800d3581  mov     [rsp+328h+var_2B0], 1
0x1800d3586  mov     [rsp+328h+lpdwDisposition], rcx; lpdwDisposition
0x1800d358b  lea     rax, [rsp+328h+var_2B8]
0x1800d3590  mov     [rsp+328h+phkResult], rax; phkResult
0x1800d3595  mov     [rsp+328h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1800d359a  mov     [rsp+328h+samDesired], 2011Fh; samDesired
0x1800d35a2  mov     [rsp+328h+dwOptions], ecx; dwOptions
0x1800d35a6  xor     r9d, r9d; lpClass
0x1800d35a9  xor     r8d, r8d; Reserved
0x1800d35ac  mov     rdx, [rsp+328h+lpSubKey]; lpSubKey
0x1800d35b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d35b8  call    cs:__imp_RegCreateKeyExW
0x1800d35be  mov     ebx, eax
0x1800d35c0  test    eax, eax
0x1800d35c2  jle     short loc_1800D35CD
0x1800d35c4  movzx   ebx, ax
0x1800d35c7  or      ebx, 80070000h
0x1800d35cd  lea     rcx, [rsp+328h+var_2C0]
0x1800d35d2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d35d7  test    ebx, ebx
0x1800d35d9  jns     short loc_1800D35E8
0x1800d35db  mov     r9d, ebx
0x1800d35de  mov     edx, 72h ; 'r'
0x1800d35e3  jmp     loc_1800D3A09
0x1800d35e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800d35ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d35f4  test    al, al
0x1800d35f6  jz      short loc_1800D363C
0x1800d35f8  lea     r8, [rsp+328h+var_280]
0x1800d3600  cmp     [rsp+328h+var_268], 7
0x1800d3609  cmova   r8, [rsp+328h+var_280]
0x1800d3612  lea     rax, [rsp+328h+var_2D8]
0x1800d3617  mov     qword ptr [rsp+328h+samDesired], rax
0x1800d361c  mov     qword ptr [rsp+328h+dwOptions], r15
0x1800d3621  mov     r9, r14
0x1800d3624  mov     rdx, rsi
0x1800d3627  call    ?MapPMCspToRegistryProviderPathIfApply@DCRegistryTrackingStore@@AEAAJPEBG000AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; DCRegistryTrackingStore::MapPMCspToRegistryProviderPathIfApply(ushort const *,ushort const *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x1800d362c  mov     ebx, eax
0x1800d362e  test    eax, eax
0x1800d3630  jns     short loc_1800D363C
0x1800d3632  mov     edx, 76h ; 'v'
0x1800d3637  jmp     loc_1800D3A06
0x1800d363c  mov     qword ptr [rsp+328h+dwOptions], r15
0x1800d3641  mov     r9, r14
0x1800d3644  lea     r8, aSS; "%s\\%s"
0x1800d364b  mov     edx, 104h; unsigned __int64
0x1800d3650  lea     rcx, [rsp+328h+var_258]; unsigned __int16 *
0x1800d3658  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d365d  mov     ebx, eax
0x1800d365f  test    eax, eax
0x1800d3661  jns     short loc_1800D366D
0x1800d3663  mov     edx, 80h
0x1800d3668  jmp     loc_1800D3A06
0x1800d366d  mov     byte ptr [rsp+328h+dwOptions], 0; bool
0x1800d3672  mov     r9, r12; unsigned __int16 *
0x1800d3675  lea     r8, aDucumentcontex; "ducumentContext"
0x1800d367c  lea     rdx, [rsp+328h+var_258]; unsigned __int16 *
0x1800d3684  mov     rcx, [rsp+328h+var_2D8]; HKEY
0x1800d3689  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800d368e  mov     ebx, eax
0x1800d3690  xor     r12d, r12d
0x1800d3693  test    eax, eax
0x1800d3695  jns     short loc_1800D36A1
0x1800d3697  mov     edx, 82h
0x1800d369c  jmp     loc_1800D3A06
0x1800d36a1  mov     byte ptr [rsp+328h+dwOptions], r12b; int
0x1800d36a6  mov     r9, r13; unsigned __int16 *
0x1800d36a9  lea     r8, aDucumentversio; "ducumentVersion"
0x1800d36b0  lea     rdx, [rsp+328h+var_258]; unsigned __int16 *
0x1800d36b8  mov     rcx, [rsp+328h+var_2D8]; HKEY
0x1800d36bd  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800d36c2  mov     ebx, eax
0x1800d36c4  test    eax, eax
0x1800d36c6  jns     short loc_1800D36D2
0x1800d36c8  mov     edx, 83h
0x1800d36cd  jmp     loc_1800D3A06
0x1800d36d2  test    rdi, rdi
0x1800d36d5  jz      loc_1800D39AA
0x1800d36db  mov     ebx, [rsp+328h+arg_38]
0x1800d36e2  mov     r9d, ebx; unsigned int
0x1800d36e5  lea     r8, aTypestored; "typeStored"
0x1800d36ec  lea     rdx, [rsp+328h+var_258]; unsigned __int16 *
0x1800d36f4  mov     rcx, [rsp+328h+var_2D8]; HKEY
0x1800d36f9  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800d36fe  mov     esi, eax
0x1800d3700  test    eax, eax
0x1800d3702  jns     short loc_1800D3732
0x1800d3704  mov     rcx, [rsp+328h]; this
0x1800d370c  mov     r9d, eax; char *
0x1800d370f  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d3716  mov     edx, 88h; void *
0x1800d371b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3720  nop
0x1800d3721  lea     rcx, [rsp+328h+var_2D8]
0x1800d3726  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d372b  mov     ebx, esi
0x1800d372d  jmp     loc_1800D3A29
0x1800d3732  sub     ebx, 1
0x1800d3735  jz      loc_1800D395D
0x1800d373b  sub     ebx, 2
0x1800d373e  jz      loc_1800D38C7
0x1800d3744  sub     ebx, 1
0x1800d3747  jz      loc_1800D3896
0x1800d374d  sub     ebx, 1
0x1800d3750  jz      loc_1800D39AA
0x1800d3756  sub     ebx, 1
0x1800d3759  jz      short loc_1800D377B
0x1800d375b  sub     ebx, 1
0x1800d375e  jz      loc_1800D382C
0x1800d3764  cmp     ebx, 1
0x1800d3767  jz      short loc_1800D37BC
0x1800d3769  mov     ebx, 8000FFFFh
0x1800d376e  mov     r9d, ebx
0x1800d3771  mov     edx, 0CEh
0x1800d3776  jmp     loc_1800D3A09
0x1800d377b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800d3782  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d3787  test    al, al
0x1800d3789  jz      short loc_1800D37BC
0x1800d378b  mov     r9, [rdi+8]; unsigned __int64
0x1800d378f  lea     r8, aValue_0; "value"
0x1800d3796  lea     rdx, [rsp+328h+var_258]; unsigned __int16 *
0x1800d379e  mov     rcx, [rsp+328h+var_2D8]; HKEY
0x1800d37a3  call    ?DCCDNUtil_SetRegistryQWORD@@YAJPEAUHKEY__@@PEBG1_K@Z; DCCDNUtil_SetRegistryQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)
0x1800d37a8  mov     ebx, eax
0x1800d37aa  test    eax, eax
0x1800d37ac  jns     loc_1800D39AA
0x1800d37b2  mov     edx, 0ACh
0x1800d37b7  jmp     loc_1800D3A06
0x1800d37bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800d37c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d37c8  test    al, al
0x1800d37ca  jz      short loc_1800D382C
0x1800d37cc  mov     r9, [rdi+8]; unsigned __int16 *
0x1800d37d0  lea     r8, aValue_0; "value"
0x1800d37d7  lea     rdx, [rsp+328h+var_258]; unsigned __int16 *
0x1800d37df  mov     rcx, [rsp+328h+var_2D8]; HKEY
0x1800d37e4  test    r9, r9
0x1800d37e7  jnz     short loc_1800D380E
0x1800d37e9  mov     byte ptr [rsp+328h+dwOptions], 1; bool
  ... truncated ...
```
