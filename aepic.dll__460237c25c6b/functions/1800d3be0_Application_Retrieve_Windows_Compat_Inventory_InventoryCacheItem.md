# Application::Retrieve(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x1800d3be0`
- end: `0x1800d510a`
- name: `?Retrieve@Application@@UEAAKPEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `5418`
- prototype: `unsigned int __fastcall(Application *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800d0d80`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000d914`
- `0x18000edf0`
- `0x18000faac`
- `0x18001c5f0`
- `0x18001de0c`
- `0x18002248c`
- `0x1800295dc`
- `0x1800c1a1c`
- `0x1800c3478`
- `0x1800d0c84`
- `0x1800d3be0`
- `0x1800d5518`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d4800`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d4ed0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d4800`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d4ed0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800d3f64`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800d3f64`

## string_xrefs

- `0x1800d3c61`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d3f7a`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d403a`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d40bc`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4173`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d41f6`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d42ee`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d43a0`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4497`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4517`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d457b`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d45fb`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d46d1`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d475b`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4817`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d489a`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d49ba`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4abe`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4b3c`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4ba0`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4c1e`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4c9c`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4dab`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4e30`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4ef5`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d4fb8`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d503c`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800d50cb`: `TelCacheProvider::GetItemProperty failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Application::Retrieve(Application *this, struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  __int64 *v4; // rdx
  int v5; // eax
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 *v8; // rdx
  int v9; // esi
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 *v12; // rdx
  int v13; // eax
  __int64 v14; // r8
  __int64 *v15; // rdx
  int v16; // eax
  __int64 v17; // r8
  __int64 *v18; // rdx
  int v19; // eax
  __int64 v20; // r8
  __int64 *v21; // r15
  __int64 *v22; // rdx
  int v23; // esi
  int v24; // eax
  __int64 *v25; // rdx
  int v26; // esi
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 *v29; // rdx
  int v30; // esi
  __int64 v31; // r8
  char *v32; // rcx
  __int64 *v33; // rdx
  int v34; // eax
  __int64 v35; // r8
  __int64 *v36; // rdx
  int v37; // eax
  _QWORD *v38; // r12
  __int64 v39; // r8
  char IsEnabled; // al
  char *v41; // rcx
  __int64 *v42; // rdx
  int v43; // eax
  __int64 v44; // r8
  __int64 v45; // rcx
  __int64 *v46; // rdx
  __int64 *v47; // rdx
  int v48; // esi
  __int64 v49; // rsi
  __int64 v50; // r15
  __int64 v51; // rsi
  __int64 v52; // r15
  __int64 *v53; // rdx
  int v54; // eax
  __int64 v55; // r8
  __int64 *v56; // rdx
  int v57; // eax
  __int64 v58; // r8
  __int64 *v59; // rdx
  int v60; // eax
  __int64 *v61; // rdx
  int v62; // eax
  __int64 v63; // r8
  _QWORD *v64; // r15
  __int64 v65; // rdx
  __int64 *v66; // r8
  Application *v67; // rcx
  __int64 *v68; // rdx
  int v69; // eax
  __int64 v70; // r8
  __int64 *v71; // rdx
  int v72; // eax
  __int64 v73; // r8
  __int64 *v74; // rsi
  __int64 *v75; // rdx
  bool v76; // al
  int v77; // eax
  __int64 *v78; // rdx
  int v79; // eax
  __int64 v80; // r8
  __int64 *v81; // rdx
  int v82; // eax
  __int64 v83; // r8
  __int64 *v84; // rdx
  int v85; // eax
  __int64 v86; // r8
  __int64 v87; // r8
  __int64 *v88; // r8
  Application *v89; // rcx
  __int64 *v90; // r8
  Application *v91; // rcx
  __int64 *v92; // rdx
  __int64 *v93; // rdx
  int v94; // eax
  __int64 v95; // r8
  __int64 *v96; // rdx
  int v97; // eax
  __int64 *v98; // rdx
  int v99; // eax
  __int64 v100; // r8
  __int64 *v101; // rdx
  int v102; // eax
  __int64 v103; // r8
  __int64 *v104; // rdx
  int v105; // eax
  __int64 v106; // r8
  __int64 *v107; // rdx
  int v108; // eax
  __int64 v109; // r8
  __int64 *v110; // rdx
  int v111; // eax
  __int64 v112; // r8
  __int64 *v113; // rsi
  __int64 *v114; // rdx
  bool v115; // al
  int v116; // eax
  __int64 *v117; // r8
  __int64 *v118; // rdx
  int v119; // eax
  __int64 v120; // r8
  __int64 *v121; // rdx
  int v122; // eax
  __int64 v123; // r8
  __int64 *v124; // rdx
  int v126; // [rsp+30h] [rbp-D0h] BYREF
  int v127; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v128; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v129; // [rsp+40h] [rbp-C0h]
  _BYTE v130[32]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v131[520]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(v131, 0, sizeof(v131));
  v126 = 520;
  v4 = &Application::InventoryItemValueNameProgramId;
  if ( (unsigned __int64)qword_1801222E8 > 7 )
    v4 = (__int64 *)Application::InventoryItemValueNameProgramId;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         v4,
         v131,
         &v126);
  v6 = -1;
  if ( v5 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2334, "TelCacheProvider::GetItemProperty failed [%#x]", v5);
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( v131[v7] );
    std::wstring::_Assign<unsigned short>((char *)this + 56, v131, v7);
  }
  v126 = 520;
  v8 = &Application::InventoryItemValueNameProgramInstanceId;
  if ( (unsigned __int64)qword_180122308 > 7 )
    v8 = (__int64 *)Application::InventoryItemValueNameProgramInstanceId;
  v9 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         v8,
         v131,
         &v126);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v9 >= 0 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v131[v10] );
LABEL_19:
      std::wstring::_Assign<unsigned short>((char *)this + 400, v131, v10);
      goto LABEL_23;
    }
    v11 = 2349;
    goto LABEL_22;
  }
  if ( v9 >= 0 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v131[v10] );
    goto LABEL_19;
  }
  if ( v9 != -2147024894 )
  {
    v11 = 2361;
LABEL_22:
    AslLogCallPrintf(1, "Application::Retrieve", v11, "TelCacheProvider::GetItemProperty failed [%#x]", v9);
  }
LABEL_23:
  v126 = 520;
  v12 = &Application::InventoryItemValueNameName;
  if ( (unsigned __int64)qword_180122328 > 7 )
    v12 = (__int64 *)Application::InventoryItemValueNameName;
  v13 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v12,
          v131,
          &v126);
  if ( v13 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2376, "TelCacheProvider::GetItemProperty failed [%#x]", v13);
  }
  else
  {
    v14 = -1;
    do
      ++v14;
    while ( v131[v14] );
    std::wstring::_Assign<unsigned short>((char *)this + 96, v131, v14);
  }
  v126 = 520;
  v15 = &Application::InventoryItemValueNameVersion;
  if ( (unsigned __int64)qword_180122348 > 7 )
    v15 = (__int64 *)Application::InventoryItemValueNameVersion;
  v16 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v15,
          v131,
          &v126);
  if ( v16 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2390, "TelCacheProvider::GetItemProperty failed [%#x]", v16);
  }
  else
  {
    v17 = -1;
    do
      ++v17;
    while ( v131[v17] );
    std::wstring::_Assign<unsigned short>((char *)this + 160, v131, v17);
  }
  v126 = 520;
  v18 = &Application::InventoryItemValueNamePublisher;
  if ( (unsigned __int64)qword_180122368 > 7 )
    v18 = (__int64 *)Application::InventoryItemValueNamePublisher;
  v19 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v18,
          v131,
          &v126);
  if ( v19 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2404, "TelCacheProvider::GetItemProperty failed [%#x]", v19);
  }
  else
  {
    v20 = -1;
    do
      ++v20;
    while ( v131[v20] );
    std::wstring::_Assign<unsigned short>((char *)this + 128, v131, v20);
  }
  v21 = &Application::InventoryItemValueNameLanguage;
  v22 = &Application::InventoryItemValueNameLanguage;
  if ( (unsigned __int64)qword_180122388 > 7 )
    v22 = (__int64 *)Application::InventoryItemValueNameLanguage;
  v23 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 80LL))(
          a2,
          v22,
          (char *)this + 464);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v23 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2413, "TelCacheProvider::GetItemProperty failed [%#x]", v23);
  }
  else if ( v23 < 0 )
  {
    v126 = 520;
    if ( (unsigned __int64)qword_180122388 > 7 )
      v21 = (__int64 *)Application::InventoryItemValueNameLanguage;
    v24 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v21,
            v131,
            &v126);
    if ( v24 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2430, "TelCacheProvider::GetItemProperty failed [%#x]", v24);
    else
      *((_DWORD *)this + 116) = _o__wtoi(v131);
  }
  v126 = 520;
  v25 = &Application::InventoryItemValueNameInstallDate;
  if ( (unsigned __int64)qword_180122488 > 7 )
    v25 = (__int64 *)Application::InventoryItemValueNameInstallDate;
  v26 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v25,
          v131,
          &v126);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v26 >= 0 )
    {
      v27 = -1;
      do
        ++v27;
      while ( v131[v27] );
LABEL_66:
      std::wstring::_Assign<unsigned short>((char *)this + 256, v131, v27);
      goto LABEL_70;
    }
    v28 = 2447;
    goto LABEL_69;
  }
  if ( v26 >= 0 )
  {
    v27 = -1;
    do
      ++v27;
    while ( v131[v27] );
    goto LABEL_66;
  }
  if ( v26 != -2147024894 )
  {
    v28 = 2459;
LABEL_69:
    AslLogCallPrintf(1, "Application::Retrieve", v28, "TelCacheProvider::GetItemProperty failed [%#x]", v26);
  }
LABEL_70:
  v126 = 520;
  v29 = &Application::InventoryItemValueNameAppType;
  if ( (unsigned __int64)qword_180122588 > 7 )
    v29 = (__int64 *)Application::InventoryItemValueNameAppType;
  v30 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v29,
          v131,
          &v126);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v30 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2475, "TelCacheProvider::GetItemProperty failed [%#x]", v30);
      goto LABEL_83;
    }
    v31 = -1;
    do
      ++v31;
    while ( v131[v31] );
    v32 = (char *)this + 368;
    goto LABEL_81;
  }
  v32 = (char *)this + 368;
  if ( v30 >= 0 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v131[v31] );
LABEL_81:
    std::wstring::_Assign<unsigned short>(v32, v131, v31);
    goto LABEL_83;
  }
  std::wstring::operator=(v32, Application::ApplicationTypeApplication);
LABEL_83:
  v126 = 520;
  v33 = &Application::InventoryItemValueNameRootDirPath;
  if ( (unsigned __int64)qword_180122508 > 7 )
    v33 = (__int64 *)Application::InventoryItemValueNameRootDirPath;
  v34 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v33,
          v131,
          &v126);
  if ( v34 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2502, "TelCacheProvider::GetItemProperty failed [%#x]", v34);
  }
  else
  {
    v35 = -1;
    do
      ++v35;
    while ( v131[v35] );
    std::wstring::_Assign<unsigned short>((char *)this + 192, v131, v35);
  }
  v126 = 520;
  v36 = &Application::InventoryItemValueNameSource;
  if ( (unsigned __int64)qword_1801223A8 > 7 )
    v36 = (__int64 *)Application::InventoryItemValueNameSource;
  v37 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v36,
          v131,
          &v126);
  v38 = (_QWORD *)((char *)this + 336);
  if ( v37 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2516, "TelCacheProvider::GetItemProperty failed [%#x]", v37);
  }
  else
  {
    v39 = -1;
    do
      ++v39;
    while ( v131[v39] );
    std::wstring::_Assign<unsigned short>((char *)this + 336, v131, v39);
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl);
  v41 = (char *)this + 336;
  if ( IsEnabled )
  {
    if ( !(unsigned __int8)std::operator!=<unsigned short>(v41, &Application::ApplicationSourceAppxPackage) )
    {
      *((_BYTE *)this + 88) = 0;
      goto LABEL_112;
    }
    v127 = 0;
    v42 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_180122568 > 7 )
      v42 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
    v43 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
            a2,
            v42,
            &v127);
    if ( v43 < 0 )
    {
      *((_BYTE *)this + 88) = 0;
      v44 = 2532;
      v45 = 3;
      goto LABEL_111;
    }
LABEL_108:
    *((_BYTE *)this + 88) = v127 != 0;
    goto LABEL_112;
  }
  if ( !(unsigned __int8)std::operator!=<unsigned short>(v41, &Application::ApplicationSourceAppxPackage) )
    goto LABEL_112;
  v127 = 0;
  v46 = &Application::InventoryItemValueNameSentDetailedInv;
  if ( (unsigned __int64)qword_180122568 > 7 )
    v46 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
  v43 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
          a2,
          v46,
          &v127);
  if ( v43 >= 0 )
    goto LABEL_108;
  *((_BYTE *)this + 88) = 0;
  if ( v43 == -2147024894 )
    goto LABEL_112;
  v44 = 2557;
  v45 = 1;
LABEL_111:
  AslLogCallPrintf(v45, "Application::Retrieve", v44, "TelCacheProvider::GetItemProperty failed [%#x]", v43);
LABEL_112:
  v126 = 520;
  v47 = &Application::InventoryItemValueNameUserSid;
  if ( (unsigned __int64)qword_1801225A8 > 7 )
    v47 = (__int64 *)Application::InventoryItemValueNameUserSid;
  v48 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v47,
          v131,
          &v126);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v48 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2579, "TelCacheProvider::GetItemProperty failed [%#x]", v48);
      goto LABEL_126;
    }
    VectorFromDelimitedString(&v128, v131);
    v49 = v128;
    v50 = v129;
    while ( v49 != v50 )
    {
      std::wstring::wstring(v130, v49);
      Application::AddUserSid(this, v130);
      std::wstring::_Tidy_deallocate(v130);
      v49 += 32;
    }
  }
  else
  {
    if ( v48 < 0 )
      goto LABEL_126;
    VectorFromDelimitedString(&v128, v131);
    v51 = v128;
    v52 = v129;
    while ( v51 != v52 )
    {
      std::wstring::wstring(v130, v51);
      Application::AddUserSid(this, v130);
      std::wstring::_Tidy_deallocate(v130);
      v51 += 32;
    }
  }
  std::vector<std::wstring>::_Tidy(&v128);
LABEL_126:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v126 = 520;
    v53 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_1801224C8 > 7 )
      v53 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v54 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v53,
            v131,
            &v126);
    if ( v54 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2605, "TelCacheProvider::GetItemProperty failed [%#x]", v54);
    }
    else
    {
      v55 = -1;
      do
        ++v55;
      while ( v131[v55] );
      std::wstring::_Assign<unsigned short>((char *)this + 904, v131, v55);
    }
    v126 = 520;
    v56 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_1801224E8 > 7 )
      v56 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v57 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v56,
            v131,
            &v126);
    if ( v57 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2616, "TelCacheProvider::GetItemProperty failed [%#x]", v57);
    }
    else
    {
      v58 = -1;
      do
        ++v58;
      while ( v131[v58] );
      std::wstring::_Assign<unsigned short>((char *)this + 936, v131, v58);
    }
    v127 = 0;
    v59 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_180122468 > 7 )
      v59 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    v60 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
            a2,
            v59,
            &v127);
    if ( v60 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2627, "TelCacheProvider::GetItemProperty failed [%#x]", v60);
    else
      *((_BYTE *)this + 968) = v127 != 0;
    v126 = 520;
    v61 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_1801223C8 > 7 )
      v61 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v62 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v61,
            v131,
            &v126);
    if ( v62 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2639, "TelCacheProvider::GetItemProperty failed [%#x]", v62);
    }
    else
    {
      v63 = -1;
      do
        ++v63;
      while ( v131[v63] );
      std::wstring::_Assign<unsigned short>((char *)this + 808, v131, v63);
    }
    v64 = (_QWORD *)((char *)this + 352);
    goto LABEL_193;
  }
  v64 = (_QWORD *)((char *)this + 352);
  v65 = *((_QWORD *)this + 44);
  if ( !v65 )
    goto LABEL_161;
  v66 = &Application::ApplicationSourceAppxPackage;
  if ( (unsigned __int64)qword_180121FE8 > 7 )
    v66 = (__int64 *)Application::ApplicationSourceAppxPackage;
  v67 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v38;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v67, v65, v66, qword_180121FE0) )
  {
LABEL_161:
    v126 = 520;
    v68 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_1801224C8 > 7 )
      v68 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v69 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v68,
            v131,
            &v126);
    if ( v69 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2656, "TelCacheProvider::GetItemProperty failed [%#x]", v69);
    }
    else
    {
      v70 = -1;
      do
        ++v70;
      while ( v131[v70] );
      std::wstring::_Assign<unsigned short>((char *)this + 904, v131, v70);
    }
    v126 = 520;
    v71 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_1801224E8 > 7 )
      v71 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v72 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v71,
            v131,
            &v126);
    if ( v72 < 0 )
    {
      if ( v72 != -2147024894 )
        AslLogCallPrintf(1, "Application::Retrieve", 2668, "TelCacheProvider::GetItemProperty failed [%#x]", v72);
    }
    else
    {
      v73 = -1;
      do
        ++v73;
      while ( v131[v73] );
      std::wstring::_Assign<unsigned short>((char *)this + 936, v131, v73);
    }
    v127 = 0;
    v74 = &Application::InventoryItemValueNameInboxStoreApp;
    v75 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_180122468 > 7 )
      v75 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
           a2,
           v75,
           &v127) < 0 )
    {
      v126 = 520;
      if ( (unsigned __int64)qword_180122468 > 7 )
        v74 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
      v77 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
              a2,
              v74,
              v131,
              &v126);
      if ( v77 < 0 )
      {
        AslLogCallPrintf(1, "Application::Retrieve", 2696, "TelCacheProvider::GetItemProperty failed [%#x]", v77);
        goto LABEL_186;
      }
      v76 = (unsigned int)_o__wcsicmp(L"true", v131) == 0;
    }
    else
    {
      v76 = v127 != 0;
    }
    *((_BYTE *)this + 968) = v76;
LABEL_186:
    v126 = 520;
    v78 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_1801223C8 > 7 )
      v78 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v79 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v78,
            v131,
            &v126);
    if ( v79 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2709, "TelCacheProvider::GetItemProperty failed [%#x]", v79);
    }
    else
    {
      v80 = -1;
      do
        ++v80;
      while ( v131[v80] );
      std::wstring::_Assign<unsigned short>((char *)this + 808, v131, v80);
    }
  }
LABEL_193:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v126 = 520;
    v81 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_1801224A8 > 7 )
      v81 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v82 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v81,
            v131,
            &v126);
    if ( v82 >= 0 )
    {
      v83 = -1;
      do
        ++v83;
      while ( v131[v83] );
LABEL_199:
      std::wstring::_Assign<unsigned short>((char *)this + 744, v131, v83);
      goto LABEL_200;
    }
    v87 = 2725;
LABEL_208:
    AslLogCallPrintf(1, "Application::Retrieve", v87, "TelCacheProvider::GetItemProperty failed [%#x]", v82);
    goto LABEL_200;
  }
  if ( !*v64 )
    goto LABEL_222;
  v88 = &Application::ApplicationSourceAppxPackage;
  if ( (unsigned __int64)qword_180121FE8 > 7 )
    v88 = (__int64 *)Application::ApplicationSourceAppxPackage;
  v89 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v38;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v89, *v64, v88, qword_180121FE0) )
    goto LABEL_222;
  v90 = &Application::ApplicationSourceAppvPackage;
  if ( (unsigned __int64)qword_180121FC8 > 7 )
    v90 = (__int64 *)Application::ApplicationSourceAppvPackage;
  v91 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v38;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                          v91,
                          *((_QWORD *)this + 44),
                          v90,
                          qword_180121FC0) )
  {
LABEL_222:
    v126 = 520;
    v92 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_1801224A8 > 7 )
      v92 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v82 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v92,
            v131,
            &v126);
    if ( v82 >= 0 )
    {
      v83 = -1;
      do
        ++v83;
      while ( v131[v83] );
      goto LABEL_199;
    }
    v87 = 2742;
    goto LABEL_208;
  }
LABEL_200:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v126 = 520;
    v84 = &Application::InventoryItemValueNameUninstallString;
    if ( (unsigned __int64)qword_180122528 > 7 )
      v84 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    v85 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v84,
            v131,
            &v126);
    if ( v85 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2758, "TelCacheProvider::GetItemProperty failed [%#x]", v85);
    }
    else
    {
      v86 = -1;
      do
        ++v86;
      while ( v131[v86] );
      std::wstring::_Assign<unsigned short>((char *)this + 224, v131, v86);
    }
    v126 = 520;
    v93 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_180122548 > 7 )
      v93 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    v94 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v93,
            v131,
            &v126);
    if ( v94 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2769, "TelCacheProvider::GetItemProperty failed [%#x]", v94);
    }
    else
    {
      v95 = -1;
      do
        ++v95;
      while ( v131[v95] );
      std::wstring::_Assign<unsigned short>((char *)this + 432, v131, v95);
    }
    v127 = 0;
    v96 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_180122448 > 7 )
      v96 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
    v97 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
            a2,
            v96,
            &v127);
    if ( v97 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2780, "TelCacheProvider::GetItemProperty failed [%#x]", v97);
    else
      *((_BYTE *)this + 700) = v127 != 0;
    v126 = 520;
    v98 = &Application::InventoryItemValueNameMsiInstallDate;
    if ( (unsigned __int64)qword_180122428 > 7 )
      v98 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
    v99 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v98,
            v131,
            &v126);
    if ( v99 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2791, "TelCacheProvider::GetItemProperty failed [%#x]", v99);
    }
    else
    {
      v100 = -1;
      do
        ++v100;
      while ( v131[v100] );
      std::wstring::_Assign<unsigned short>((char *)this + 568, v131, v100);
    }
    v126 = 520;
    v101 = &Application::InventoryItemValueNameMsiPackageCode;
    if ( (unsigned __int64)qword_180122408 > 7 )
      v101 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
    v102 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v101,
             v131,
             &v126);
    if ( v102 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2802, "TelCacheProvider::GetItemProperty failed [%#x]", v102);
    }
    else
    {
      v103 = -1;
      do
        ++v103;
      while ( v131[v103] );
      std::wstring::_Assign<unsigned short>((char *)this + 632, v131, v103);
    }
    v126 = 520;
    v104 = &Application::InventoryItemValueNameMsiProductCode;
    if ( (unsigned __int64)qword_1801223E8 > 7 )
      v104 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
    v105 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v104,
             v131,
             &v126);
    if ( v105 >= 0 )
    {
      do
        ++v6;
      while ( v131[v6] );
LABEL_316:
      std::wstring::_Assign<unsigned short>((char *)this + 600, v131, v6);
      return 0;
    }
    v106 = 2813;
    goto LABEL_319;
  }
  if ( (unsigned __int8)std::operator!=<unsigned short>((char *)this + 336, &Application::ApplicationSourceAppxPackage)
    && (unsigned __int8)std::operator!=<unsigned short>((char *)this + 336, &Application::ApplicationSourceAppvPackage) )
  {
    v126 = 520;
    v107 = &Application::InventoryItemValueNameUninstallString;
    if ( (unsigned __int64)qword_180122528 > 7 )
      v107 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    v108 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v107,
             v131,
             &v126);
    if ( v108 < 0 )
    {
      if ( v108 != -2147024894 )
        AslLogCallPrintf(1, "Application::Retrieve", 2830, "TelCacheProvider::GetItemProperty failed [%#x]", v108);
    }
    else
    {
      v109 = -1;
      do
        ++v109;
      while ( v131[v109] );
      std::wstring::_Assign<unsigned short>((char *)this + 224, v131, v109);
    }
    v126 = 520;
    v110 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_180122548 > 7 )
      v110 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    v111 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v110,
             v131,
             &v126);
    if ( v111 < 0 )
    {
      if ( v111 != -2147024894 )
        AslLogCallPrintf(1, "Application::Retrieve", 2842, "TelCacheProvider::GetItemProperty failed [%#x]", v111);
    }
    else
    {
      v112 = -1;
      do
        ++v112;
      while ( v131[v112] );
      std::wstring::_Assign<unsigned short>((char *)this + 432, v131, v112);
    }
    v127 = 0;
    v113 = &Application::InventoryItemValueNameHiddenArp;
    v114 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_180122448 > 7 )
      v114 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
           a2,
           v114,
           &v127) < 0 )
    {
      v126 = 520;
      if ( (unsigned __int64)qword_180122448 > 7 )
        v113 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
      v116 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
               a2,
               v113,
               v131,
               &v126);
      if ( v116 < 0 )
      {
        if ( v116 != -2147024894 )
          AslLogCallPrintf(1, "Application::Retrieve", 2871, "TelCacheProvider::GetItemProperty failed [%#x]", v116);
LABEL_291:
        v117 = &Application::ApplicationSourceMsi;
        if ( (unsigned __int64)qword_180121EA8 > 7 )
          v117 = (__int64 *)Application::ApplicationSourceMsi;
        if ( *((_QWORD *)this + 45) > 7u )
          v38 = (_QWORD *)*v38;
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                v38,
                                *((_QWORD *)this + 44),
                                v117,
                                qword_180121EA0) )
        {
          v126 = 520;
          v118 = &Application::InventoryItemValueNameMsiInstallDate;
          if ( (unsigned __int64)qword_180122428 > 7 )
            v118 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
          v119 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v118,
                   v131,
                   &v126);
          if ( v119 < 0 )
          {
            if ( v119 != -2147024894 )
              AslLogCallPrintf(1, "Application::Retrieve", 2886, "TelCacheProvider::GetItemProperty failed [%#x]", v119);
          }
          else
          {
            v120 = -1;
            do
              ++v120;
            while ( v131[v120] );
            std::wstring::_Assign<unsigned short>((char *)this + 568, v131, v120);
          }
          v126 = 520;
          v121 = &Application::InventoryItemValueNameMsiPackageCode;
          if ( (unsigned __int64)qword_180122408 > 7 )
            v121 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
          v122 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v121,
                   v131,
                   &v126);
          if ( v122 < 0 )
          {
            if ( v122 != -2147024894 )
              AslLogCallPrintf(1, "Application::Retrieve", 2897, "TelCacheProvider::GetItemProperty failed [%#x]", v122);
          }
          else
          {
            v123 = -1;
            do
              ++v123;
            while ( v131[v123] );
            std::wstring::_Assign<unsigned short>((char *)this + 632, v131, v123);
          }
          v126 = 520;
          v124 = &Application::InventoryItemValueNameMsiProductCode;
          if ( (unsigned __int64)qword_1801223E8 > 7 )
            v124 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
          v105 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v124,
                   v131,
                   &v126);
          if ( v105 >= 0 )
          {
            do
              ++v6;
            while ( v131[v6] );
            goto LABEL_316;
          }
          if ( v105 == -2147024894 )
            return 0;
          v106 = 2908;
LABEL_319:
          AslLogCallPrintf(1, "Application::Retrieve", v106, "TelCacheProvider::GetItemProperty failed [%#x]", v105);
          return 0;
        }
        return 0;
      }
      v115 = (unsigned int)_o__wcsicmp(L"true", v131) == 0;
    }
    else
    {
      v115 = v127 != 0;
    }
    *((_BYTE *)this + 700) = v115;
    goto LABEL_291;
  }
  return 0;
}

```

## disassembly

```asm
0x1800d3be0  mov     [rsp-8+arg_10], rbx
0x1800d3be5  push    rbp
0x1800d3be6  push    rsi
0x1800d3be7  push    rdi
0x1800d3be8  push    r12
0x1800d3bea  push    r13
0x1800d3bec  push    r14
0x1800d3bee  push    r15
0x1800d3bf0  lea     rbp, [rsp-390h]
0x1800d3bf8  sub     rsp, 490h
0x1800d3bff  mov     rax, cs:__security_cookie
0x1800d3c06  xor     rax, rsp
0x1800d3c09  mov     [rbp+3C0h+var_40], rax
0x1800d3c10  mov     r14, rdx
0x1800d3c13  mov     rbx, rcx
0x1800d3c16  xor     edx, edx; Val
0x1800d3c18  mov     r8d, 410h; Size
0x1800d3c1e  lea     rcx, [rsp+4C0h+var_450]; void *
0x1800d3c23  call    memset_0
0x1800d3c28  mov     esi, 208h
0x1800d3c2d  mov     [rsp+4C0h+var_490], esi
0x1800d3c31  mov     rax, [r14]
0x1800d3c34  lea     rdx, ?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x1800d3c3b  cmp     cs:qword_1801222E8, 7
0x1800d3c43  cmova   rdx, cs:?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x1800d3c4b  lea     r9, [rsp+4C0h+var_490]
0x1800d3c50  lea     r8, [rsp+4C0h+var_450]
0x1800d3c55  mov     rcx, r14
0x1800d3c58  mov     rax, [rax+40h]
0x1800d3c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3c61  lea     r15, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x1800d3c68  lea     r12, aApplicationRet; "Application::Retrieve"
0x1800d3c6f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800d3c73  xor     r13d, r13d
0x1800d3c76  test    eax, eax
0x1800d3c78  js      short loc_1800D3C9C
0x1800d3c7a  lea     rax, [rsp+4C0h+var_450]
0x1800d3c7f  mov     r8, rdi
0x1800d3c82  inc     r8
0x1800d3c85  cmp     [rax+r8*2], r13w
0x1800d3c8a  jnz     short loc_1800D3C82
0x1800d3c8c  lea     rcx, [rbx+38h]
0x1800d3c90  lea     rdx, [rsp+4C0h+var_450]
0x1800d3c95  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d3c9a  jmp     short loc_1800D3CB6
0x1800d3c9c  mov     [rsp+4C0h+var_4A0], eax
0x1800d3ca0  mov     r9, r15
0x1800d3ca3  mov     r8d, 91Eh
0x1800d3ca9  mov     rdx, r12
0x1800d3cac  mov     ecx, 1
0x1800d3cb1  call    AslLogCallPrintf
0x1800d3cb6  mov     [rsp+4C0h+var_490], esi
0x1800d3cba  mov     rax, [r14]
0x1800d3cbd  lea     rdx, ?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800d3cc4  cmp     cs:qword_180122308, 7
0x1800d3ccc  cmova   rdx, cs:?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800d3cd4  lea     r9, [rsp+4C0h+var_490]
0x1800d3cd9  lea     r8, [rsp+4C0h+var_450]
0x1800d3cde  mov     rcx, r14
0x1800d3ce1  mov     rax, [rax+40h]
0x1800d3ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3cea  mov     esi, eax
0x1800d3cec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d3cf3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d3cf8  test    al, al
0x1800d3cfa  jz      short loc_1800D3D1C
0x1800d3cfc  test    esi, esi
0x1800d3cfe  js      short loc_1800D3D14
0x1800d3d00  lea     rax, [rsp+4C0h+var_450]
0x1800d3d05  mov     r8, rdi
0x1800d3d08  inc     r8
0x1800d3d0b  cmp     [rax+r8*2], r13w
0x1800d3d10  jnz     short loc_1800D3D08
0x1800d3d12  jmp     short loc_1800D3D32
0x1800d3d14  mov     r8d, 92Dh
0x1800d3d1a  jmp     short loc_1800D3D53
0x1800d3d1c  test    esi, esi
0x1800d3d1e  js      short loc_1800D3D45
0x1800d3d20  lea     rax, [rsp+4C0h+var_450]
0x1800d3d25  mov     r8, rdi
0x1800d3d28  inc     r8
0x1800d3d2b  cmp     [rax+r8*2], r13w
0x1800d3d30  jnz     short loc_1800D3D28
0x1800d3d32  lea     rcx, [rbx+190h]
0x1800d3d39  lea     rdx, [rsp+4C0h+var_450]
0x1800d3d3e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d3d43  jmp     short loc_1800D3D67
0x1800d3d45  cmp     esi, 80070002h
0x1800d3d4b  jz      short loc_1800D3D67
0x1800d3d4d  mov     r8d, 939h
0x1800d3d53  mov     [rsp+4C0h+var_4A0], esi
0x1800d3d57  mov     r9, r15
0x1800d3d5a  mov     rdx, r12
0x1800d3d5d  mov     ecx, 1
0x1800d3d62  call    AslLogCallPrintf
0x1800d3d67  mov     esi, 208h
0x1800d3d6c  mov     [rsp+4C0h+var_490], esi
0x1800d3d70  mov     rax, [r14]
0x1800d3d73  lea     rdx, ?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x1800d3d7a  cmp     cs:qword_180122328, 7
0x1800d3d82  cmova   rdx, cs:?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x1800d3d8a  lea     r9, [rsp+4C0h+var_490]
0x1800d3d8f  lea     r8, [rsp+4C0h+var_450]
0x1800d3d94  mov     rcx, r14
0x1800d3d97  mov     rax, [rax+40h]
0x1800d3d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3da0  test    eax, eax
0x1800d3da2  js      short loc_1800D3DC6
0x1800d3da4  lea     rax, [rsp+4C0h+var_450]
0x1800d3da9  mov     r8, rdi
0x1800d3dac  inc     r8
0x1800d3daf  cmp     [rax+r8*2], r13w
0x1800d3db4  jnz     short loc_1800D3DAC
0x1800d3db6  lea     rcx, [rbx+60h]
0x1800d3dba  lea     rdx, [rsp+4C0h+var_450]
0x1800d3dbf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d3dc4  jmp     short loc_1800D3DE0
0x1800d3dc6  mov     [rsp+4C0h+var_4A0], eax
0x1800d3dca  mov     r9, r15
0x1800d3dcd  mov     r8d, 948h
0x1800d3dd3  mov     rdx, r12
0x1800d3dd6  mov     ecx, 1
0x1800d3ddb  call    AslLogCallPrintf
0x1800d3de0  mov     [rsp+4C0h+var_490], esi
0x1800d3de4  mov     rax, [r14]
0x1800d3de7  lea     rdx, ?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x1800d3dee  cmp     cs:qword_180122348, 7
0x1800d3df6  cmova   rdx, cs:?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x1800d3dfe  lea     r9, [rsp+4C0h+var_490]
0x1800d3e03  lea     r8, [rsp+4C0h+var_450]
0x1800d3e08  mov     rcx, r14
0x1800d3e0b  mov     rax, [rax+40h]
0x1800d3e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3e14  test    eax, eax
0x1800d3e16  js      short loc_1800D3E3D
0x1800d3e18  lea     rax, [rsp+4C0h+var_450]
0x1800d3e1d  mov     r8, rdi
0x1800d3e20  inc     r8
0x1800d3e23  cmp     [rax+r8*2], r13w
0x1800d3e28  jnz     short loc_1800D3E20
0x1800d3e2a  lea     rcx, [rbx+0A0h]
0x1800d3e31  lea     rdx, [rsp+4C0h+var_450]
0x1800d3e36  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d3e3b  jmp     short loc_1800D3E57
0x1800d3e3d  mov     [rsp+4C0h+var_4A0], eax
0x1800d3e41  mov     r9, r15
0x1800d3e44  mov     r8d, 956h
0x1800d3e4a  mov     rdx, r12
0x1800d3e4d  mov     ecx, 1
0x1800d3e52  call    AslLogCallPrintf
0x1800d3e57  mov     [rsp+4C0h+var_490], esi
0x1800d3e5b  mov     rax, [r14]
0x1800d3e5e  lea     rdx, ?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x1800d3e65  cmp     cs:qword_180122368, 7
0x1800d3e6d  cmova   rdx, cs:?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x1800d3e75  lea     r9, [rsp+4C0h+var_490]
0x1800d3e7a  lea     r8, [rsp+4C0h+var_450]
0x1800d3e7f  mov     rcx, r14
0x1800d3e82  mov     rax, [rax+40h]
0x1800d3e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3e8b  test    eax, eax
0x1800d3e8d  js      short loc_1800D3EB4
0x1800d3e8f  lea     rax, [rsp+4C0h+var_450]
0x1800d3e94  mov     r8, rdi
0x1800d3e97  inc     r8
0x1800d3e9a  cmp     [rax+r8*2], r13w
0x1800d3e9f  jnz     short loc_1800D3E97
0x1800d3ea1  lea     rcx, [rbx+80h]
0x1800d3ea8  lea     rdx, [rsp+4C0h+var_450]
0x1800d3ead  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d3eb2  jmp     short loc_1800D3ECE
0x1800d3eb4  mov     [rsp+4C0h+var_4A0], eax
0x1800d3eb8  mov     r9, r15
0x1800d3ebb  mov     r8d, 964h
0x1800d3ec1  mov     rdx, r12
0x1800d3ec4  mov     ecx, 1
0x1800d3ec9  call    AslLogCallPrintf
0x1800d3ece  mov     rax, [r14]
0x1800d3ed1  lea     r15, ?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x1800d3ed8  mov     rdx, r15
0x1800d3edb  cmp     cs:qword_180122388, 7
0x1800d3ee3  cmova   rdx, cs:?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x1800d3eeb  lea     r12, [rbx+1D0h]
0x1800d3ef2  mov     r8, r12
0x1800d3ef5  mov     rcx, r14
0x1800d3ef8  mov     rax, [rax+50h]
0x1800d3efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3f01  mov     esi, eax
0x1800d3f03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d3f0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d3f0f  test    al, al
0x1800d3f11  jz      short loc_1800D3F23
0x1800d3f13  test    esi, esi
0x1800d3f15  jns     short loc_1800D3F92
0x1800d3f17  mov     [rsp+4C0h+var_4A0], esi
0x1800d3f1b  mov     r8d, 96Dh
0x1800d3f21  jmp     short loc_1800D3F7A
0x1800d3f23  test    esi, esi
0x1800d3f25  jns     short loc_1800D3F92
0x1800d3f27  mov     [rsp+4C0h+var_490], 208h
0x1800d3f2f  mov     rax, [r14]
0x1800d3f32  cmp     cs:qword_180122388, 7
0x1800d3f3a  cmova   r15, cs:?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x1800d3f42  lea     r9, [rsp+4C0h+var_490]
0x1800d3f47  lea     r8, [rsp+4C0h+var_450]
0x1800d3f4c  mov     rdx, r15
0x1800d3f4f  mov     rcx, r14
0x1800d3f52  mov     rax, [rax+40h]
0x1800d3f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3f5b  test    eax, eax
0x1800d3f5d  js      short loc_1800D3F70
0x1800d3f5f  lea     rcx, [rsp+4C0h+var_450]
0x1800d3f64  call    cs:__imp__o__wtoi
0x1800d3f6a  mov     [r12], eax
0x1800d3f6e  jmp     short loc_1800D3F92
0x1800d3f70  mov     [rsp+4C0h+var_4A0], eax
0x1800d3f74  mov     r8d, 97Eh
0x1800d3f7a  lea     r9, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x1800d3f81  lea     rdx, aApplicationRet; "Application::Retrieve"
0x1800d3f88  mov     ecx, 1
0x1800d3f8d  call    AslLogCallPrintf
0x1800d3f92  mov     r15d, 208h
0x1800d3f98  mov     [rsp+4C0h+var_490], r15d
0x1800d3f9d  mov     rax, [r14]
0x1800d3fa0  lea     rdx, ?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800d3fa7  cmp     cs:qword_180122488, 7
0x1800d3faf  cmova   rdx, cs:?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800d3fb7  lea     r9, [rsp+4C0h+var_490]
0x1800d3fbc  lea     r8, [rsp+4C0h+var_450]
0x1800d3fc1  mov     rcx, r14
0x1800d3fc4  mov     rax, [rax+40h]
0x1800d3fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3fcd  mov     esi, eax
0x1800d3fcf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d3fd6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d3fdb  test    al, al
0x1800d3fdd  jz      short loc_1800D3FFF
0x1800d3fdf  test    esi, esi
0x1800d3fe1  js      short loc_1800D3FF7
0x1800d3fe3  lea     rax, [rsp+4C0h+var_450]
0x1800d3fe8  mov     r8, rdi
0x1800d3feb  inc     r8
0x1800d3fee  cmp     [rax+r8*2], r13w
0x1800d3ff3  jnz     short loc_1800D3FEB
0x1800d3ff5  jmp     short loc_1800D4015
0x1800d3ff7  mov     r8d, 98Fh
0x1800d3ffd  jmp     short loc_1800D4036
0x1800d3fff  test    esi, esi
0x1800d4001  js      short loc_1800D4028
0x1800d4003  lea     rax, [rsp+4C0h+var_450]
0x1800d4008  mov     r8, rdi
0x1800d400b  inc     r8
0x1800d400e  cmp     [rax+r8*2], r13w
0x1800d4013  jnz     short loc_1800D400B
0x1800d4015  lea     rcx, [rbx+100h]
0x1800d401c  lea     rdx, [rsp+4C0h+var_450]
0x1800d4021  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d4026  jmp     short loc_1800D4052
0x1800d4028  cmp     esi, 80070002h
0x1800d402e  jz      short loc_1800D4052
0x1800d4030  mov     r8d, 99Bh
0x1800d4036  mov     [rsp+4C0h+var_4A0], esi
0x1800d403a  lea     r9, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x1800d4041  lea     rdx, aApplicationRet; "Application::Retrieve"
0x1800d4048  mov     ecx, 1
0x1800d404d  call    AslLogCallPrintf
0x1800d4052  mov     [rsp+4C0h+var_490], r15d
0x1800d4057  mov     rax, [r14]
0x1800d405a  lea     rdx, ?InventoryItemValueNameAppType@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameAppType
0x1800d4061  cmp     cs:qword_180122588, 7
0x1800d4069  cmova   rdx, cs:?InventoryItemValueNameAppType@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameAppType
0x1800d4071  lea     r9, [rsp+4C0h+var_490]
0x1800d4076  lea     r8, [rsp+4C0h+var_450]
0x1800d407b  mov     rcx, r14
0x1800d407e  mov     rax, [rax+40h]
0x1800d4082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4087  mov     esi, eax
0x1800d4089  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d4090  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d4095  test    al, al
0x1800d4097  jz      short loc_1800D40DC
0x1800d4099  test    esi, esi
0x1800d409b  js      short loc_1800D40B8
0x1800d409d  lea     rax, [rsp+4C0h+var_450]
0x1800d40a2  mov     r8, rdi
0x1800d40a5  inc     r8
0x1800d40a8  cmp     [rax+r8*2], r13w
0x1800d40ad  jnz     short loc_1800D40A5
0x1800d40af  lea     rcx, [rbx+170h]
0x1800d40b6  jmp     short loc_1800D40F9
0x1800d40b8  mov     [rsp+4C0h+var_4A0], esi
0x1800d40bc  lea     r9, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x1800d40c3  mov     r8d, 9ABh
0x1800d40c9  lea     rdx, aApplicationRet; "Application::Retrieve"
0x1800d40d0  mov     ecx, 1
0x1800d40d5  call    AslLogCallPrintf
0x1800d40da  jmp     short loc_1800D4111
0x1800d40dc  lea     rcx, [rbx+170h]
0x1800d40e3  test    esi, esi
0x1800d40e5  js      short loc_1800D4105
  ... truncated ...
```
