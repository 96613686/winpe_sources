# DeclaredConfiguration_PopulateUriMapFromSingleDoc(DeclaredConfigurationScopeData *,ushort const *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x18008b42c`
- end: `0x18008bb6a`
- name: `?DeclaredConfiguration_PopulateUriMapFromSingleDoc@@YAJPEAUDeclaredConfigurationScopeData@@PEBGAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1854`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007f018`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x1800117dc`
- `0x180011fe0`
- `0x1800143c8`
- `0x18001440c`
- `0x180018ac0`
- `0x180018cc4`
- `0x180019270`
- `0x1800192b4`
- `0x180019d38`
- `0x18001bc98`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18001d37c`
- `0x18001dea8`
- `0x18004bc88`
- `0x18004ec50`
- `0x1800546f0`
- `0x18005ec48`
- `0x18005eeb8`
- `0x1800725e0`
- `0x180076c10`
- `0x18008b42c`
- `0x18009ff30`
- `0x180100ad8`
- `0x18012d59c`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008b839`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008b868`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008b839`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008b868`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18008ba9d`

## string_xrefs

- `0x18008b781`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18008b4a6`: `DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey:Failed to get the doc registry key`
- `0x18008b4ad`: `DeclaredConfiguration_PopulateUriMapFromSingleDoc`
- `0x18008b519`: `DeclaredConfiguration_PopulateUriMapFromSingleDoc`
- `0x18008b5ff`: `DeclaredConfiguration_PopulateUriMapFromSingleDoc`
- `0x18008b6b5`: `DeclaredConfiguration_PopulateUriMapFromSingleDoc`
- `0x18008b512`: `DCCDNUtil_GetRegistryString:Failed to get the most recent version`
- `0x18008b5f8`: `DeclaredConfigurationStore_GetPersistedDocument:Failed to retrieve the persisted document`
- `0x18008b6ae`: `DCGetEnrollmentIdSidStateDocIdVersionKey:Failed to get doc version key`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall DeclaredConfiguration_PopulateUriMapFromSingleDoc(
        struct DeclaredConfigurationScopeData *a1,
        const unsigned __int16 *a2,
        _QWORD *a3)
{
  int EnrollmentIdSidStateDocIdKey; // ebx
  int v6; // ecx
  void **p_Block; // rbx
  int RegistryString; // eax
  int v10; // ecx
  int v11; // esi
  __int64 v12; // r8
  _WORD *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r8
  int PersistedDocument; // eax
  int v17; // ecx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // rdx
  int v20; // ecx
  int v21; // r14d
  unsigned __int16 *v22; // r15
  unsigned __int16 *v23; // rax
  __int64 v24; // r13
  int v25; // eax
  __int64 *v26; // r12
  __int64 *v27; // rax
  _QWORD *v28; // rcx
  _QWORD *v29; // rcx
  _QWORD *v30; // rax
  _WORD *v31; // rdx
  __int64 v32; // r8
  const unsigned __int16 *v33; // rcx
  int v34; // eax
  __int64 v35; // r14
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  _BYTE *v39; // rcx
  unsigned __int16 **v40; // r14
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // r8
  _QWORD *v47; // r9
  _QWORD *v48; // rax
  int v49; // r9d
  _QWORD *v50; // rdx
  const char *v51; // r9
  int v52; // [rsp+20h] [rbp-7C8h]
  void *Block; // [rsp+30h] [rbp-7B8h] BYREF
  HKEY v54; // [rsp+38h] [rbp-7B0h] BYREF
  int v55; // [rsp+40h] [rbp-7A8h]
  __int64 v56; // [rsp+48h] [rbp-7A0h] BYREF
  HKEY *v57; // [rsp+50h] [rbp-798h] BYREF
  HKEY v58; // [rsp+58h] [rbp-790h] BYREF
  char v59; // [rsp+60h] [rbp-788h]
  __int64 v60; // [rsp+68h] [rbp-780h]
  _QWORD *v61; // [rsp+70h] [rbp-778h]
  __int64 *j; // [rsp+78h] [rbp-770h]
  unsigned __int16 *i; // [rsp+80h] [rbp-768h]
  void **v64; // [rsp+88h] [rbp-760h]
  char v65; // [rsp+90h] [rbp-758h]
  _QWORD v66[3]; // [rsp+98h] [rbp-750h] BYREF
  char v67[8]; // [rsp+B0h] [rbp-738h] BYREF
  char v68; // [rsp+B8h] [rbp-730h] BYREF
  _QWORD v69[3]; // [rsp+C0h] [rbp-728h] BYREF
  unsigned __int64 v70; // [rsp+D8h] [rbp-710h]
  unsigned __int16 *v71[3]; // [rsp+E0h] [rbp-708h] BYREF
  unsigned __int64 v72; // [rsp+F8h] [rbp-6F0h]
  _BYTE v73[32]; // [rsp+100h] [rbp-6E8h] BYREF
  _BYTE v74[32]; // [rsp+120h] [rbp-6C8h] BYREF
  _BYTE v75[32]; // [rsp+140h] [rbp-6A8h] BYREF
  _BYTE v76[32]; // [rsp+160h] [rbp-688h] BYREF
  _BYTE v77[32]; // [rsp+180h] [rbp-668h] BYREF
  unsigned __int16 *v78[4]; // [rsp+1A0h] [rbp-648h] BYREF
  char v79[32]; // [rsp+1C0h] [rbp-628h] BYREF
  char *v80; // [rsp+1E0h] [rbp-608h] BYREF
  unsigned __int16 *v81[9]; // [rsp+200h] [rbp-5E8h] BYREF
  unsigned __int16 *v82; // [rsp+248h] [rbp-5A0h]
  _QWORD v83[3]; // [rsp+3A0h] [rbp-448h] BYREF
  unsigned __int64 v84; // [rsp+3B8h] [rbp-430h]
  _BYTE v85[752]; // [rsp+490h] [rbp-358h] BYREF
  unsigned __int16 v86[16]; // [rsp+780h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7E8h] [rbp+0h]

  v61 = a3;
  Block = 0;
  v54 = 0;
  v57 = &v54;
  v58 = 0;
  v59 = 1;
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(a1, a2, &v58, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v57);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( byte_180189FC1 < 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v6,
        (unsigned int)OrchestratorGenericFailure,
        (unsigned int)L"DeclaredConfiguration_PopulateUriMapFromSingleDoc",
        (unsigned int)L"DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey:Failed to get the doc registry key",
        EnrollmentIdSidStateDocIdKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
    return (unsigned int)EnrollmentIdSidStateDocIdKey;
  }
  p_Block = &Block;
  v64 = &Block;
  v65 = 1;
  RegistryString = DCCDNUtil_GetRegistryString(v54, 0, L"MostRecentVersion", (unsigned __int16 **)&Block);
  v11 = RegistryString;
  if ( RegistryString < 0 )
  {
    if ( byte_180189FC1 < 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v10,
        (unsigned int)OrchestratorGenericFailure,
        (unsigned int)L"DeclaredConfiguration_PopulateUriMapFromSingleDoc",
        (unsigned int)L"DCCDNUtil_GetRegistryString:Failed to get the most recent version",
        RegistryString);
    goto LABEL_8;
  }
  DCDocument::DCDocument((DCDocument *)v78);
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  std::wstring::_Assign<unsigned short>((char **)v78, a2, (char *)v12);
  v13 = (_WORD *)*((_QWORD *)a1 + 1);
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  std::wstring::_Assign<unsigned short>(&v80, v13, (char *)v14);
  v15 = -1;
  do
    ++v15;
  while ( *((_WORD *)Block + v15) );
  std::wstring::_Assign<unsigned short>((char **)v81, Block, (char *)v15);
  DCDocument::DCDocument((DCDocument *)v85);
  PersistedDocument = DeclaredConfigurationStore_GetPersistedDocument(a1, v54, (__int64)Block, 0, (__int64)v78, 1);
  v11 = PersistedDocument;
  if ( PersistedDocument < 0 )
  {
    if ( byte_180189FC1 < 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v17,
        (unsigned int)OrchestratorGenericFailure,
        (unsigned int)L"DeclaredConfiguration_PopulateUriMapFromSingleDoc",
        (unsigned int)L"DeclaredConfigurationStore_GetPersistedDocument:Failed to retrieve the persisted document",
        PersistedDocument);
LABEL_18:
    DCDocument::~DCDocument((DCDocument *)v85);
    DCDocument::~DCDocument((DCDocument *)v78);
LABEL_8:
    operator delete(Block);
    Block = 0;
    goto LABEL_34;
  }
  v56 = 0;
  v57 = (HKEY *)&v56;
  v58 = 0;
  v59 = 1;
  v18 = (const unsigned __int16 *)v81;
  if ( v81[3] > (unsigned __int16 *)7 )
    v18 = v81[0];
  v19 = (const unsigned __int16 *)v78;
  if ( v78[3] > (unsigned __int16 *)7 )
    v19 = v78[0];
  v11 = DCGetEnrollmentIdSidStateDocIdVersionKey(a1, v19, v18, &v58, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v57);
  if ( v11 < 0 )
  {
    if ( byte_180189FC1 < 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v20,
        (unsigned int)OrchestratorGenericFailure,
        (unsigned int)L"DeclaredConfiguration_PopulateUriMapFromSingleDoc",
        (unsigned int)L"DCGetEnrollmentIdSidStateDocIdVersionKey:Failed to get doc version key",
        v11);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
    goto LABEL_18;
  }
  v21 = 0;
  v86[0] = 0;
  std::vector<ConfigDoc>::vector<ConfigDoc>(v66);
  v22 = v81[8];
  v23 = v82;
  for ( i = v82; ; v23 = i )
  {
    if ( v22 == v23 )
      goto LABEL_32;
    if ( (***(unsigned int (__fastcall ****)(_QWORD))v22)(*(_QWORD *)v22) == 1 )
      break;
LABEL_63:
    v22 += 8;
  }
  v24 = _RTDynamicCast_0(*(_QWORD *)v22, 0, &DCProvider `RTTI Type Descriptor', &DCCSP `RTTI Type Descriptor', 0);
  v55 = v21 + 1;
  v25 = StringCchPrintfW(v86, 0xFu, L"CSP%d", (unsigned int)(v21 + 1));
  v11 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5428,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v25,
      v52);
LABEL_32:
    std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v66);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
    DCDocument::~DCDocument((DCDocument *)v85);
    DCDocument::~DCDocument((DCDocument *)v78);
    operator delete(Block);
    goto LABEL_33;
  }
  v26 = *(__int64 **)(v24 + 16);
  v27 = *(__int64 **)(v24 + 24);
  for ( j = v27; ; v27 = j )
  {
    if ( v26 == v27 )
    {
      v21 = v55;
      goto LABEL_63;
    }
    v28 = v83;
    if ( v84 > 7 )
      v28 = (_QWORD *)v83[0];
    if ( (unsigned int)_o__wcsicmp(v28, L"msftinventory") )
    {
      v29 = v83;
      if ( v84 > 7 )
        v29 = (_QWORD *)v83[0];
      if ( (unsigned int)_o__wcsicmp(v29, L"msftonetime") && !*(_BYTE *)(v24 + 81) )
      {
        std::wstring::wstring((__int64)v71);
        std::wstring::wstring((__int64)v69);
        v30 = (_QWORD *)(v24 + 88);
        if ( *(_QWORD *)(v24 + 112) > 7u )
          v30 = (_QWORD *)*v30;
        v31 = (_WORD *)v30 + 2;
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        try
        {
          std::wstring::_Assign<unsigned short>((char **)v71, v31, (char *)v32);
          v33 = (const unsigned __int16 *)v71;
          if ( v72 > 7 )
            v33 = v71[0];
          v34 = DCDoesCspNeedPrefix(v33);
          v35 = *v26;
          v60 = *v26;
          if ( v34 )
          {
            v40 = v71;
            if ( v72 > 7 )
              v40 = (unsigned __int16 **)v71[0];
            v41 = std::operator+<unsigned short>(v77, L"./", v79);
            v42 = std::operator+<unsigned short>(v76, v41, L"/");
            v43 = std::operator+<unsigned short>(v73, v42, v40);
            v44 = std::operator+<unsigned short>(v74, v43, L"/");
            v45 = std::operator+<unsigned short>(v75, v44, v60);
            std::wstring::operator=(v69, v45);
            std::wstring::_Tidy_deallocate(v75);
            std::wstring::_Tidy_deallocate(v74);
            std::wstring::_Tidy_deallocate(v73);
            std::wstring::_Tidy_deallocate(v76);
            v39 = v77;
          }
          else
          {
            v36 = std::operator+<unsigned short>(v75, L"./", v71);
            v37 = std::operator+<unsigned short>(v74, v36, L"/");
            v38 = std::operator+<unsigned short>(v73, v37, v35);
            std::wstring::operator=(v69, v38);
            std::wstring::_Tidy_deallocate(v73);
            std::wstring::_Tidy_deallocate(v74);
            v39 = v75;
          }
          std::wstring::_Tidy_deallocate(v39);
          v47 = v69;
          if ( v70 > 7 )
            v47 = (_QWORD *)v69[0];
          v48 = (_QWORD *)std::wstring::end(v69, v67, v46, v47);
          v50 = v69;
          if ( v70 > 7 )
            LODWORD(v50) = v69[0];
          std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
            (unsigned int)&v68,
            (_DWORD)v50,
            *v48,
            v49,
            *(__int64 *)&_o_towlower);
          std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring &,std::wstring &>(
            v61,
            (__int64)&v57,
            v69,
            (__int64)v78);
          std::wstring::_Tidy_deallocate(v69);
          std::wstring::_Tidy_deallocate(v71);
        }
        catch ( ... )
        {
          v55 = wil::details::in1diag3::Return_CaughtException(
                  retaddr,
                  (void *)0x5444,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconf"
                                "igurationapi.cpp",
                  v51);
          std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v66);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
          DCDocument::~DCDocument((DCDocument *)v85);
          DCDocument::~DCDocument((DCDocument *)v78);
          p_Block = v64;
          operator delete(*v64);
          v11 = v55;
LABEL_33:
          *p_Block = 0;
LABEL_34:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
          return (unsigned int)v11;
        }
      }
    }
    v26 += 2;
  }
}

```

## disassembly

```asm
0x18008b42c  push    rbx
0x18008b42e  push    rsi
0x18008b42f  push    rdi
0x18008b430  push    r12
0x18008b432  push    r13
0x18008b434  push    r14
0x18008b436  push    r15
0x18008b438  sub     rsp, 7B0h
0x18008b43f  mov     rax, cs:__security_cookie
0x18008b446  xor     rax, rsp
0x18008b449  mov     [rsp+7E8h+var_48], rax
0x18008b451  mov     [rsp+7E8h+var_778], r8
0x18008b456  mov     r14, rdx
0x18008b459  mov     r15, rcx
0x18008b45c  xor     edi, edi
0x18008b45e  mov     [rsp+7E8h+Block], rdi
0x18008b463  mov     [rsp+7E8h+var_7B0], rdi
0x18008b468  lea     rax, [rsp+7E8h+var_7B0]
0x18008b46d  mov     [rsp+7E8h+var_798], rax
0x18008b472  mov     [rsp+7E8h+var_790], rdi
0x18008b477  mov     [rsp+7E8h+var_788], 1
0x18008b47c  xor     r9d, r9d; int
0x18008b47f  lea     r8, [rsp+7E8h+var_790]; HKEY *
0x18008b484  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x18008b489  mov     ebx, eax
0x18008b48b  lea     rcx, [rsp+7E8h+var_798]
0x18008b490  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008b495  test    ebx, ebx
0x18008b497  jns     short loc_18008B4D2
0x18008b499  cmp     cs:byte_180189FC1, dil
0x18008b4a0  jge     short loc_18008B4C1
0x18008b4a2  mov     [rsp+7E8h+var_7C8], ebx
0x18008b4a6  lea     r9, aDeclaredconfig_227; "DeclaredConfigurationStore_GetEnrollmen"...
0x18008b4ad  lea     r8, aDeclaredconfig_139; "DeclaredConfiguration_PopulateUriMapFro"...
0x18008b4b4  lea     rdx, OrchestratorGenericFailure
0x18008b4bb  call    McTemplateU0zzd_EventWriteTransfer
0x18008b4c0  nop
0x18008b4c1  lea     rcx, [rsp+7E8h+var_7B0]
0x18008b4c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008b4cb  mov     eax, ebx
0x18008b4cd  jmp     loc_18008B7DF
0x18008b4d2  lea     rbx, [rsp+7E8h+Block]
0x18008b4d7  mov     [rsp+7E8h+var_760], rbx
0x18008b4df  mov     [rsp+7E8h+var_758], 1
0x18008b4e7  lea     r9, [rsp+7E8h+Block]; unsigned __int16 **
0x18008b4ec  lea     r8, aMostrecentvers; "MostRecentVersion"
0x18008b4f3  xor     edx, edx; unsigned __int16 *
0x18008b4f5  mov     rcx, [rsp+7E8h+var_7B0]; HKEY
0x18008b4fa  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18008b4ff  mov     esi, eax
0x18008b501  test    eax, eax
0x18008b503  jns     short loc_18008B541
0x18008b505  cmp     cs:byte_180189FC1, dil
0x18008b50c  jge     short loc_18008B52D
0x18008b50e  mov     [rsp+7E8h+var_7C8], eax
0x18008b512  lea     r9, aDccdnutilGetre_14; "DCCDNUtil_GetRegistryString:Failed to g"...
0x18008b519  lea     r8, aDeclaredconfig_139; "DeclaredConfiguration_PopulateUriMapFro"...
0x18008b520  lea     rdx, OrchestratorGenericFailure
0x18008b527  call    McTemplateU0zzd_EventWriteTransfer
0x18008b52c  nop
0x18008b52d  mov     rcx, [rsp+7E8h+Block]; Block
0x18008b532  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008b537  mov     [rsp+7E8h+Block], rdi
0x18008b53c  jmp     loc_18008B7D3
0x18008b541  lea     rcx, [rsp+7E8h+var_648]; this
0x18008b549  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x18008b54e  nop
0x18008b54f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008b553  mov     r8, rsi
0x18008b556  inc     r8
0x18008b559  cmp     [r14+r8*2], di
0x18008b55e  jnz     short loc_18008B556
0x18008b560  mov     rdx, r14
0x18008b563  lea     rcx, [rsp+7E8h+var_648]
0x18008b56b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008b570  mov     rdx, [r15+8]
0x18008b574  mov     r8, rsi
0x18008b577  inc     r8
0x18008b57a  cmp     [rdx+r8*2], di
0x18008b57f  jnz     short loc_18008B577
0x18008b581  lea     rcx, [rsp+7E8h+var_608]
0x18008b589  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008b58e  mov     rdx, [rsp+7E8h+Block]
0x18008b593  mov     r8, rsi
0x18008b596  inc     r8
0x18008b599  cmp     [rdx+r8*2], di
0x18008b59e  jnz     short loc_18008B596
0x18008b5a0  lea     rcx, [rsp+7E8h+var_5E8]
0x18008b5a8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008b5ad  lea     rcx, [rsp+7E8h+var_358]; this
0x18008b5b5  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x18008b5ba  nop
0x18008b5bb  mov     [rsp+7E8h+var_7C0], 1
0x18008b5c3  lea     rax, [rsp+7E8h+var_648]
0x18008b5cb  mov     qword ptr [rsp+7E8h+var_7C8], rax
0x18008b5d0  xor     r9d, r9d
0x18008b5d3  mov     r8, [rsp+7E8h+Block]
0x18008b5d8  mov     rdx, [rsp+7E8h+var_7B0]
0x18008b5dd  mov     rcx, r15
0x18008b5e0  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x18008b5e5  mov     esi, eax
0x18008b5e7  test    eax, eax
0x18008b5e9  jns     short loc_18008B633
0x18008b5eb  cmp     cs:byte_180189FC1, dil
0x18008b5f2  jge     short loc_18008B613
0x18008b5f4  mov     [rsp+7E8h+var_7C8], eax
0x18008b5f8  lea     r9, aDeclaredconfig_130; "DeclaredConfigurationStore_GetPersisted"...
0x18008b5ff  lea     r8, aDeclaredconfig_139; "DeclaredConfiguration_PopulateUriMapFro"...
0x18008b606  lea     rdx, OrchestratorGenericFailure
0x18008b60d  call    McTemplateU0zzd_EventWriteTransfer
0x18008b612  nop
0x18008b613  lea     rcx, [rsp+7E8h+var_358]; this
0x18008b61b  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18008b620  nop
0x18008b621  lea     rcx, [rsp+7E8h+var_648]; this
0x18008b629  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18008b62e  jmp     loc_18008B52D
0x18008b633  mov     [rsp+7E8h+var_7A0], rdi
0x18008b638  lea     rax, [rsp+7E8h+var_7A0]
0x18008b63d  mov     [rsp+7E8h+var_798], rax
0x18008b642  mov     [rsp+7E8h+var_790], rdi
0x18008b647  mov     [rsp+7E8h+var_788], 1
0x18008b64c  lea     r8, [rsp+7E8h+var_5E8]
0x18008b654  cmp     [rsp+7E8h+var_5D0], 7
0x18008b65d  cmova   r8, [rsp+7E8h+var_5E8]; unsigned __int16 *
0x18008b666  lea     rdx, [rsp+7E8h+var_648]
0x18008b66e  cmp     [rsp+7E8h+var_630], 7
0x18008b677  cmova   rdx, [rsp+7E8h+var_648]; unsigned __int16 *
0x18008b680  mov     [rsp+7E8h+var_7C8], edi; int
0x18008b684  lea     r9, [rsp+7E8h+var_790]; HKEY *
0x18008b689  mov     rcx, r15; struct DeclaredConfigurationScopeData *
0x18008b68c  call    ?DCGetEnrollmentIdSidStateDocIdVersionKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBG1PEAPEAUHKEY__@@H@Z; DCGetEnrollmentIdSidStateDocIdVersionKey(DeclaredConfigurationScopeData *,ushort const *,ushort const *,HKEY__ * *,int)
0x18008b691  mov     esi, eax
0x18008b693  lea     rcx, [rsp+7E8h+var_798]
0x18008b698  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008b69d  test    esi, esi
0x18008b69f  jns     short loc_18008B6D8
0x18008b6a1  cmp     cs:byte_180189FC1, dil
0x18008b6a8  jge     short loc_18008B6C9
0x18008b6aa  mov     [rsp+7E8h+var_7C8], esi
0x18008b6ae  lea     r9, aDcgetenrollmen_0; "DCGetEnrollmentIdSidStateDocIdVersionKe"...
0x18008b6b5  lea     r8, aDeclaredconfig_139; "DeclaredConfiguration_PopulateUriMapFro"...
0x18008b6bc  lea     rdx, OrchestratorGenericFailure
0x18008b6c3  call    McTemplateU0zzd_EventWriteTransfer
0x18008b6c8  nop
0x18008b6c9  lea     rcx, [rsp+7E8h+var_7A0]
0x18008b6ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008b6d3  jmp     loc_18008B613
0x18008b6d8  mov     r14d, edi
0x18008b6db  mov     [rsp+7E8h+var_68], di
0x18008b6e3  lea     rcx, [rsp+7E8h+var_750]
0x18008b6eb  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x18008b6f0  nop
0x18008b6f1  mov     r15, [rsp+7E8h+var_5A8]
0x18008b6f9  mov     rax, [rsp+7E8h+var_5A0]
0x18008b701  mov     [rsp+7E8h+var_768], rax
0x18008b709  cmp     r15, rax
0x18008b70c  jz      loc_18008B793
0x18008b712  mov     rcx, [r15]
0x18008b715  mov     rax, [rcx]
0x18008b718  mov     rax, [rax]
0x18008b71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b720  cmp     eax, 1
0x18008b723  jnz     loc_18008BB58
0x18008b729  mov     [rsp+7E8h+var_7C8], edi; int
0x18008b72d  lea     r9, ??_R0?AVDCCSP@@@8; DCCSP `RTTI Type Descriptor'
0x18008b734  lea     r8, ??_R0?AVDCProvider@@@8; DCProvider `RTTI Type Descriptor'
0x18008b73b  xor     edx, edx
0x18008b73d  mov     rcx, [r15]
0x18008b740  call    __RTDynamicCast_0
0x18008b745  mov     r13, rax
0x18008b748  inc     r14d
0x18008b74b  mov     [rsp+7E8h+var_7A8], r14d
0x18008b750  mov     r9d, r14d
0x18008b753  lea     r8, aCspD; "CSP%d"
0x18008b75a  mov     edx, 0Fh; unsigned __int64
0x18008b75f  lea     rcx, [rsp+7E8h+var_68]; unsigned __int16 *
0x18008b767  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008b76c  mov     esi, eax
0x18008b76e  test    eax, eax
0x18008b770  jns     loc_18008B802
0x18008b776  mov     rcx, [rsp+7E8h]; this
0x18008b77e  mov     r9d, eax; char *
0x18008b781  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18008b788  mov     edx, 5428h; void *
0x18008b78d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b792  nop
0x18008b793  lea     rcx, [rsp+7E8h+var_750]
0x18008b79b  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x18008b7a0  nop
0x18008b7a1  lea     rcx, [rsp+7E8h+var_7A0]
0x18008b7a6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008b7ab  nop
0x18008b7ac  lea     rcx, [rsp+7E8h+var_358]; this
0x18008b7b4  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18008b7b9  nop
0x18008b7ba  lea     rcx, [rsp+7E8h+var_648]; this
0x18008b7c2  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18008b7c7  nop
0x18008b7c8  mov     rcx, [rbx]; Block
0x18008b7cb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008b7d0  mov     [rbx], rdi
0x18008b7d3  lea     rcx, [rsp+7E8h+var_7B0]
0x18008b7d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008b7dd  mov     eax, esi
0x18008b7df  mov     rcx, [rsp+7E8h+var_48]
0x18008b7e7  xor     rcx, rsp; StackCookie
0x18008b7ea  call    __security_check_cookie
0x18008b7ef  add     rsp, 7B0h
0x18008b7f6  pop     r15
0x18008b7f8  pop     r14
0x18008b7fa  pop     r13
0x18008b7fc  pop     r12
0x18008b7fe  pop     rdi
0x18008b7ff  pop     rsi
0x18008b800  pop     rbx
0x18008b801  retn
0x18008b802  mov     r12, [r13+10h]
0x18008b806  mov     rax, [r13+18h]
0x18008b80a  mov     [rsp+7E8h+var_770], rax
0x18008b80f  cmp     r12, rax
0x18008b812  jz      loc_18008BB53
0x18008b818  lea     rcx, [rsp+7E8h+var_448]
0x18008b820  cmp     [rsp+7E8h+var_430], 7
0x18008b829  cmova   rcx, [rsp+7E8h+var_448]
0x18008b832  lea     rdx, aMsftinventory; "msftinventory"
0x18008b839  call    cs:__imp__o__wcsicmp
0x18008b83f  test    eax, eax
0x18008b841  jz      loc_18008BAF5
0x18008b847  lea     rcx, [rsp+7E8h+var_448]
0x18008b84f  cmp     [rsp+7E8h+var_430], 7
0x18008b858  cmova   rcx, [rsp+7E8h+var_448]
0x18008b861  lea     rdx, aMsftonetime; "msftonetime"
0x18008b868  call    cs:__imp__o__wcsicmp
0x18008b86e  test    eax, eax
0x18008b870  jz      loc_18008BAF5
0x18008b876  cmp     [r13+51h], dil
0x18008b87a  jnz     loc_18008BAF5
0x18008b880  lea     rcx, [rsp+7E8h+var_708]
0x18008b888  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008b88d  nop
0x18008b88e  lea     rcx, [rsp+7E8h+var_728]
0x18008b896  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008b89b  nop
0x18008b89c  lea     rax, [r13+58h]
0x18008b8a0  cmp     qword ptr [r13+70h], 7
0x18008b8a5  jbe     short loc_18008B8AA
0x18008b8a7  mov     rax, [rax]
0x18008b8aa  lea     rdx, [rax+4]
0x18008b8ae  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008b8b2  inc     r8
0x18008b8b5  cmp     [rdx+r8*2], di
0x18008b8ba  jnz     short loc_18008B8B2
0x18008b8bc  lea     rcx, [rsp+7E8h+var_708]
0x18008b8c4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008b8c9  lea     rcx, [rsp+7E8h+var_708]
0x18008b8d1  cmp     [rsp+7E8h+var_6F0], 7
0x18008b8da  cmova   rcx, [rsp+7E8h+var_708]; unsigned __int16 *
0x18008b8e3  call    ?DCDoesCspNeedPrefix@@YAHPEBG@Z; DCDoesCspNeedPrefix(ushort const *)
0x18008b8e8  mov     r14, [r12]
0x18008b8ec  mov     [rsp+7E8h+var_780], r14
0x18008b8f1  lea     rdx, asc_180142BE8; "./"
0x18008b8f8  test    eax, eax
0x18008b8fa  jnz     short loc_18008B976
0x18008b8fc  lea     r8, [rsp+7E8h+var_708]
0x18008b904  lea     rcx, [rsp+7E8h+var_6A8]
0x18008b90c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18008b911  nop
0x18008b912  lea     r8, asc_18013EB9C; "/"
0x18008b919  mov     rdx, rax
0x18008b91c  lea     rcx, [rsp+7E8h+var_6C8]
0x18008b924  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18008b929  nop
0x18008b92a  mov     r8, r14
0x18008b92d  mov     rdx, rax
0x18008b930  lea     rcx, [rsp+7E8h+var_6E8]
0x18008b938  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18008b93d  mov     rdx, rax
0x18008b940  lea     rcx, [rsp+7E8h+var_728]
0x18008b948  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008b94d  lea     rcx, [rsp+7E8h+var_6E8]
0x18008b955  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008b95a  nop
0x18008b95b  lea     rcx, [rsp+7E8h+var_6C8]
0x18008b963  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008b968  nop
0x18008b969  lea     rcx, [rsp+7E8h+var_6A8]
0x18008b971  jmp     loc_18008BA4F
0x18008b976  lea     r14, [rsp+7E8h+var_708]
0x18008b97e  cmp     [rsp+7E8h+var_6F0], 7
0x18008b987  cmova   r14, [rsp+7E8h+var_708]
0x18008b990  lea     r8, [rsp+7E8h+var_628]
0x18008b998  lea     rcx, [rsp+7E8h+var_668]
0x18008b9a0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18008b9a5  nop
0x18008b9a6  lea     r8, asc_18013EB9C; "/"
0x18008b9ad  mov     rdx, rax
0x18008b9b0  lea     rcx, [rsp+7E8h+var_688]
0x18008b9b8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18008b9bd  nop
  ... truncated ...
```
