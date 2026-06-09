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
  __int64 v12; // r8
  __int64 *v13; // rdx
  int v14; // eax
  __int64 v15; // r8
  __int64 *v16; // rdx
  int v17; // eax
  __int64 v18; // r8
  __int64 *v19; // rdx
  int v20; // eax
  __int64 v21; // r8
  __int64 *v22; // r15
  __int64 *v23; // rdx
  int v24; // esi
  int v25; // eax
  __int64 *v26; // rdx
  int v27; // esi
  __int64 v28; // r8
  __int64 v29; // r8
  __int64 v30; // r8
  __int64 *v31; // rdx
  int v32; // esi
  __int64 v33; // r8
  char *v34; // rcx
  __int64 v35; // r8
  __int64 *v36; // rdx
  int v37; // eax
  __int64 v38; // r8
  __int64 *v39; // rdx
  int v40; // eax
  _QWORD *v41; // r12
  __int64 v42; // r8
  char IsEnabled; // al
  char *v44; // rcx
  __int64 *v45; // rdx
  int v46; // eax
  __int64 v47; // r8
  __int64 v48; // rcx
  __int64 *v49; // rdx
  __int64 *v50; // rdx
  int v51; // esi
  __int64 v52; // rsi
  __int64 v53; // r15
  __int64 v54; // rsi
  __int64 v55; // r15
  __int64 *v56; // rdx
  int v57; // eax
  __int64 v58; // r8
  __int64 *v59; // rdx
  int v60; // eax
  __int64 v61; // r8
  __int64 *v62; // rdx
  int v63; // eax
  __int64 *v64; // rdx
  int v65; // eax
  __int64 v66; // r8
  _QWORD *v67; // r15
  __int64 v68; // rdx
  __int64 *v69; // r8
  Application *v70; // rcx
  __int64 *v71; // rdx
  int v72; // eax
  __int64 v73; // r8
  __int64 *v74; // rdx
  int v75; // eax
  __int64 v76; // r8
  __int64 *v77; // rsi
  __int64 *v78; // rdx
  bool v79; // al
  int v80; // eax
  __int64 *v81; // rdx
  int v82; // eax
  __int64 v83; // r8
  __int64 *v84; // rdx
  int v85; // eax
  __int64 v86; // r8
  __int64 *v87; // rdx
  int v88; // eax
  __int64 v89; // r8
  __int64 v90; // r8
  __int64 *v91; // r8
  Application *v92; // rcx
  __int64 *v93; // r8
  Application *v94; // rcx
  __int64 *v95; // rdx
  __int64 v96; // r8
  __int64 *v97; // rdx
  int v98; // eax
  __int64 v99; // r8
  __int64 *v100; // rdx
  int v101; // eax
  __int64 *v102; // rdx
  int v103; // eax
  __int64 v104; // r8
  __int64 *v105; // rdx
  int v106; // eax
  __int64 v107; // r8
  __int64 *v108; // rdx
  int v109; // eax
  __int64 v110; // r8
  __int64 *v111; // rdx
  int v112; // eax
  __int64 v113; // r8
  __int64 *v114; // rdx
  int v115; // eax
  __int64 v116; // r8
  __int64 *v117; // rsi
  __int64 *v118; // rdx
  bool v119; // al
  int v120; // eax
  __int64 *v121; // r8
  __int64 *v122; // rdx
  int v123; // eax
  __int64 v124; // r8
  __int64 *v125; // rdx
  int v126; // eax
  __int64 v127; // r8
  __int64 *v128; // rdx
  int v130; // [rsp+30h] [rbp-D0h] BYREF
  int v131; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v132; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v133; // [rsp+40h] [rbp-C0h]
  _BYTE v134[32]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v135[520]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(v135, 0, sizeof(v135));
  v130 = 520;
  v4 = &Application::InventoryItemValueNameProgramId;
  if ( (unsigned __int64)qword_1801222E8 > 7 )
    v4 = (__int64 *)Application::InventoryItemValueNameProgramId;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         v4,
         v135,
         &v130);
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
    while ( v135[v7] );
    std::wstring::_Assign<unsigned short>((char *)this + 56, v135);
  }
  v130 = 520;
  v8 = &Application::InventoryItemValueNameProgramInstanceId;
  if ( (unsigned __int64)qword_180122308 > 7 )
    v8 = (__int64 *)Application::InventoryItemValueNameProgramInstanceId;
  v9 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         v8,
         v135,
         &v130);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v9 >= 0 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v135[v10] );
LABEL_19:
      std::wstring::_Assign<unsigned short>((char *)this + 400, v135);
      goto LABEL_23;
    }
    v11 = 2349;
    goto LABEL_22;
  }
  if ( v9 >= 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v135[v12] );
    goto LABEL_19;
  }
  if ( v9 != -2147024894 )
  {
    v11 = 2361;
LABEL_22:
    AslLogCallPrintf(1, "Application::Retrieve", v11, "TelCacheProvider::GetItemProperty failed [%#x]", v9);
  }
LABEL_23:
  v130 = 520;
  v13 = &Application::InventoryItemValueNameName;
  if ( (unsigned __int64)qword_180122328 > 7 )
    v13 = (__int64 *)Application::InventoryItemValueNameName;
  v14 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v13,
          v135,
          &v130);
  if ( v14 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2376, "TelCacheProvider::GetItemProperty failed [%#x]", v14);
  }
  else
  {
    v15 = -1;
    do
      ++v15;
    while ( v135[v15] );
    std::wstring::_Assign<unsigned short>((char *)this + 96, v135);
  }
  v130 = 520;
  v16 = &Application::InventoryItemValueNameVersion;
  if ( (unsigned __int64)qword_180122348 > 7 )
    v16 = (__int64 *)Application::InventoryItemValueNameVersion;
  v17 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v16,
          v135,
          &v130);
  if ( v17 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2390, "TelCacheProvider::GetItemProperty failed [%#x]", v17);
  }
  else
  {
    v18 = -1;
    do
      ++v18;
    while ( v135[v18] );
    std::wstring::_Assign<unsigned short>((char *)this + 160, v135);
  }
  v130 = 520;
  v19 = &Application::InventoryItemValueNamePublisher;
  if ( (unsigned __int64)qword_180122368 > 7 )
    v19 = (__int64 *)Application::InventoryItemValueNamePublisher;
  v20 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v19,
          v135,
          &v130);
  if ( v20 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2404, "TelCacheProvider::GetItemProperty failed [%#x]", v20);
  }
  else
  {
    v21 = -1;
    do
      ++v21;
    while ( v135[v21] );
    std::wstring::_Assign<unsigned short>((char *)this + 128, v135);
  }
  v22 = &Application::InventoryItemValueNameLanguage;
  v23 = &Application::InventoryItemValueNameLanguage;
  if ( (unsigned __int64)qword_180122388 > 7 )
    v23 = (__int64 *)Application::InventoryItemValueNameLanguage;
  v24 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 80LL))(
          a2,
          v23,
          (char *)this + 464);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v24 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2413, "TelCacheProvider::GetItemProperty failed [%#x]", v24);
  }
  else if ( v24 < 0 )
  {
    v130 = 520;
    if ( (unsigned __int64)qword_180122388 > 7 )
      v22 = (__int64 *)Application::InventoryItemValueNameLanguage;
    v25 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v22,
            v135,
            &v130);
    if ( v25 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2430, "TelCacheProvider::GetItemProperty failed [%#x]", v25);
    else
      *((_DWORD *)this + 116) = _o__wtoi(v135);
  }
  v130 = 520;
  v26 = &Application::InventoryItemValueNameInstallDate;
  if ( (unsigned __int64)qword_180122488 > 7 )
    v26 = (__int64 *)Application::InventoryItemValueNameInstallDate;
  v27 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v26,
          v135,
          &v130);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v27 >= 0 )
    {
      v28 = -1;
      do
        ++v28;
      while ( v135[v28] );
LABEL_66:
      std::wstring::_Assign<unsigned short>((char *)this + 256, v135);
      goto LABEL_70;
    }
    v29 = 2447;
    goto LABEL_69;
  }
  if ( v27 >= 0 )
  {
    v30 = -1;
    do
      ++v30;
    while ( v135[v30] );
    goto LABEL_66;
  }
  if ( v27 != -2147024894 )
  {
    v29 = 2459;
LABEL_69:
    AslLogCallPrintf(1, "Application::Retrieve", v29, "TelCacheProvider::GetItemProperty failed [%#x]", v27);
  }
LABEL_70:
  v130 = 520;
  v31 = &Application::InventoryItemValueNameAppType;
  if ( (unsigned __int64)qword_180122588 > 7 )
    v31 = (__int64 *)Application::InventoryItemValueNameAppType;
  v32 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v31,
          v135,
          &v130);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v32 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2475, "TelCacheProvider::GetItemProperty failed [%#x]", v32);
      goto LABEL_83;
    }
    v33 = -1;
    do
      ++v33;
    while ( v135[v33] );
    v34 = (char *)this + 368;
    goto LABEL_81;
  }
  v34 = (char *)this + 368;
  if ( v32 >= 0 )
  {
    v35 = -1;
    do
      ++v35;
    while ( v135[v35] );
LABEL_81:
    std::wstring::_Assign<unsigned short>(v34, v135);
    goto LABEL_83;
  }
  std::wstring::operator=(v34);
LABEL_83:
  v130 = 520;
  v36 = &Application::InventoryItemValueNameRootDirPath;
  if ( (unsigned __int64)qword_180122508 > 7 )
    v36 = (__int64 *)Application::InventoryItemValueNameRootDirPath;
  v37 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v36,
          v135,
          &v130);
  if ( v37 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2502, "TelCacheProvider::GetItemProperty failed [%#x]", v37);
  }
  else
  {
    v38 = -1;
    do
      ++v38;
    while ( v135[v38] );
    std::wstring::_Assign<unsigned short>((char *)this + 192, v135);
  }
  v130 = 520;
  v39 = &Application::InventoryItemValueNameSource;
  if ( (unsigned __int64)qword_1801223A8 > 7 )
    v39 = (__int64 *)Application::InventoryItemValueNameSource;
  v40 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v39,
          v135,
          &v130);
  v41 = (_QWORD *)((char *)this + 336);
  if ( v40 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2516, "TelCacheProvider::GetItemProperty failed [%#x]", v40);
  }
  else
  {
    v42 = -1;
    do
      ++v42;
    while ( v135[v42] );
    std::wstring::_Assign<unsigned short>((char *)this + 336, v135);
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl);
  v44 = (char *)this + 336;
  if ( IsEnabled )
  {
    if ( !(unsigned __int8)std::operator!=<unsigned short>(v44, &Application::ApplicationSourceAppxPackage) )
    {
      *((_BYTE *)this + 88) = 0;
      goto LABEL_112;
    }
    v131 = 0;
    v45 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_180122568 > 7 )
      v45 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
    v46 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
            a2,
            v45,
            &v131);
    if ( v46 < 0 )
    {
      *((_BYTE *)this + 88) = 0;
      v47 = 2532;
      v48 = 3;
      goto LABEL_111;
    }
LABEL_108:
    *((_BYTE *)this + 88) = v131 != 0;
    goto LABEL_112;
  }
  if ( !(unsigned __int8)std::operator!=<unsigned short>(v44, &Application::ApplicationSourceAppxPackage) )
    goto LABEL_112;
  v131 = 0;
  v49 = &Application::InventoryItemValueNameSentDetailedInv;
  if ( (unsigned __int64)qword_180122568 > 7 )
    v49 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
  v46 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
          a2,
          v49,
          &v131);
  if ( v46 >= 0 )
    goto LABEL_108;
  *((_BYTE *)this + 88) = 0;
  if ( v46 == -2147024894 )
    goto LABEL_112;
  v47 = 2557;
  v48 = 1;
LABEL_111:
  AslLogCallPrintf(v48, "Application::Retrieve", v47, "TelCacheProvider::GetItemProperty failed [%#x]", v46);
LABEL_112:
  v130 = 520;
  v50 = &Application::InventoryItemValueNameUserSid;
  if ( (unsigned __int64)qword_1801225A8 > 7 )
    v50 = (__int64 *)Application::InventoryItemValueNameUserSid;
  v51 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v50,
          v135,
          &v130);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v51 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2579, "TelCacheProvider::GetItemProperty failed [%#x]", v51);
      goto LABEL_126;
    }
    VectorFromDelimitedString(&v132, v135);
    v52 = v132;
    v53 = v133;
    while ( v52 != v53 )
    {
      std::wstring::wstring(v134, v52);
      Application::AddUserSid(this, v134);
      std::wstring::_Tidy_deallocate(v134);
      v52 += 32;
    }
  }
  else
  {
    if ( v51 < 0 )
      goto LABEL_126;
    VectorFromDelimitedString(&v132, v135);
    v54 = v132;
    v55 = v133;
    while ( v54 != v55 )
    {
      std::wstring::wstring(v134, v54);
      Application::AddUserSid(this, v134);
      std::wstring::_Tidy_deallocate(v134);
      v54 += 32;
    }
  }
  std::vector<std::wstring>::_Tidy(&v132);
LABEL_126:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v130 = 520;
    v56 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_1801224C8 > 7 )
      v56 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v57 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v56,
            v135,
            &v130);
    if ( v57 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2605, "TelCacheProvider::GetItemProperty failed [%#x]", v57);
    }
    else
    {
      v58 = -1;
      do
        ++v58;
      while ( v135[v58] );
      std::wstring::_Assign<unsigned short>((char *)this + 904, v135);
    }
    v130 = 520;
    v59 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_1801224E8 > 7 )
      v59 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v60 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v59,
            v135,
            &v130);
    if ( v60 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2616, "TelCacheProvider::GetItemProperty failed [%#x]", v60);
    }
    else
    {
      v61 = -1;
      do
        ++v61;
      while ( v135[v61] );
      std::wstring::_Assign<unsigned short>((char *)this + 936, v135);
    }
    v131 = 0;
    v62 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_180122468 > 7 )
      v62 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    v63 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
            a2,
            v62,
            &v131);
    if ( v63 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2627, "TelCacheProvider::GetItemProperty failed [%#x]", v63);
    else
      *((_BYTE *)this + 968) = v131 != 0;
    v130 = 520;
    v64 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_1801223C8 > 7 )
      v64 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v65 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v64,
            v135,
            &v130);
    if ( v65 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2639, "TelCacheProvider::GetItemProperty failed [%#x]", v65);
    }
    else
    {
      v66 = -1;
      do
        ++v66;
      while ( v135[v66] );
      std::wstring::_Assign<unsigned short>((char *)this + 808, v135);
    }
    v67 = (_QWORD *)((char *)this + 352);
    goto LABEL_193;
  }
  v67 = (_QWORD *)((char *)this + 352);
  v68 = *((_QWORD *)this + 44);
  if ( !v68 )
    goto LABEL_161;
  v69 = &Application::ApplicationSourceAppxPackage;
  if ( (unsigned __int64)qword_180121FE8 > 7 )
    v69 = (__int64 *)Application::ApplicationSourceAppxPackage;
  v70 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v41;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v70, v68, v69) )
  {
LABEL_161:
    v130 = 520;
    v71 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_1801224C8 > 7 )
      v71 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v72 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v71,
            v135,
            &v130);
    if ( v72 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2656, "TelCacheProvider::GetItemProperty failed [%#x]", v72);
    }
    else
    {
      v73 = -1;
      do
        ++v73;
      while ( v135[v73] );
      std::wstring::_Assign<unsigned short>((char *)this + 904, v135);
    }
    v130 = 520;
    v74 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_1801224E8 > 7 )
      v74 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v75 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v74,
            v135,
            &v130);
    if ( v75 < 0 )
    {
      if ( v75 != -2147024894 )
        AslLogCallPrintf(1, "Application::Retrieve", 2668, "TelCacheProvider::GetItemProperty failed [%#x]", v75);
    }
    else
    {
      v76 = -1;
      do
        ++v76;
      while ( v135[v76] );
      std::wstring::_Assign<unsigned short>((char *)this + 936, v135);
    }
    v131 = 0;
    v77 = &Application::InventoryItemValueNameInboxStoreApp;
    v78 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_180122468 > 7 )
      v78 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
           a2,
           v78,
           &v131) < 0 )
    {
      v130 = 520;
      if ( (unsigned __int64)qword_180122468 > 7 )
        v77 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
      v80 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
              a2,
              v77,
              v135,
              &v130);
      if ( v80 < 0 )
      {
        AslLogCallPrintf(1, "Application::Retrieve", 2696, "TelCacheProvider::GetItemProperty failed [%#x]", v80);
        goto LABEL_186;
      }
      v79 = (unsigned int)_o__wcsicmp(L"true", v135) == 0;
    }
    else
    {
      v79 = v131 != 0;
    }
    *((_BYTE *)this + 968) = v79;
LABEL_186:
    v130 = 520;
    v81 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_1801223C8 > 7 )
      v81 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v82 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v81,
            v135,
            &v130);
    if ( v82 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2709, "TelCacheProvider::GetItemProperty failed [%#x]", v82);
    }
    else
    {
      v83 = -1;
      do
        ++v83;
      while ( v135[v83] );
      std::wstring::_Assign<unsigned short>((char *)this + 808, v135);
    }
  }
LABEL_193:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v130 = 520;
    v84 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_1801224A8 > 7 )
      v84 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v85 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v84,
            v135,
            &v130);
    if ( v85 >= 0 )
    {
      v86 = -1;
      do
        ++v86;
      while ( v135[v86] );
LABEL_199:
      std::wstring::_Assign<unsigned short>((char *)this + 744, v135);
      goto LABEL_200;
    }
    v90 = 2725;
LABEL_208:
    AslLogCallPrintf(1, "Application::Retrieve", v90, "TelCacheProvider::GetItemProperty failed [%#x]", v85);
    goto LABEL_200;
  }
  if ( !*v67 )
    goto LABEL_222;
  v91 = &Application::ApplicationSourceAppxPackage;
  if ( (unsigned __int64)qword_180121FE8 > 7 )
    v91 = (__int64 *)Application::ApplicationSourceAppxPackage;
  v92 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v41;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v92, *v67, v91) )
    goto LABEL_222;
  v93 = &Application::ApplicationSourceAppvPackage;
  if ( (unsigned __int64)qword_180121FC8 > 7 )
    v93 = (__int64 *)Application::ApplicationSourceAppvPackage;
  v94 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v41;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v94, *((_QWORD *)this + 44), v93) )
  {
LABEL_222:
    v130 = 520;
    v95 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_1801224A8 > 7 )
      v95 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v85 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v95,
            v135,
            &v130);
    if ( v85 >= 0 )
    {
      v96 = -1;
      do
        ++v96;
      while ( v135[v96] );
      goto LABEL_199;
    }
    v90 = 2742;
    goto LABEL_208;
  }
LABEL_200:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v130 = 520;
    v87 = &Application::InventoryItemValueNameUninstallString;
    if ( (unsigned __int64)qword_180122528 > 7 )
      v87 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    v88 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v87,
            v135,
            &v130);
    if ( v88 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2758, "TelCacheProvider::GetItemProperty failed [%#x]", v88);
    }
    else
    {
      v89 = -1;
      do
        ++v89;
      while ( v135[v89] );
      std::wstring::_Assign<unsigned short>((char *)this + 224, v135);
    }
    v130 = 520;
    v97 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_180122548 > 7 )
      v97 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    v98 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v97,
            v135,
            &v130);
    if ( v98 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2769, "TelCacheProvider::GetItemProperty failed [%#x]", v98);
    }
    else
    {
      v99 = -1;
      do
        ++v99;
      while ( v135[v99] );
      std::wstring::_Assign<unsigned short>((char *)this + 432, v135);
    }
    v131 = 0;
    v100 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_180122448 > 7 )
      v100 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
    v101 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
             a2,
             v100,
             &v131);
    if ( v101 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2780, "TelCacheProvider::GetItemProperty failed [%#x]", v101);
    else
      *((_BYTE *)this + 700) = v131 != 0;
    v130 = 520;
    v102 = &Application::InventoryItemValueNameMsiInstallDate;
    if ( (unsigned __int64)qword_180122428 > 7 )
      v102 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
    v103 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v102,
             v135,
             &v130);
    if ( v103 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2791, "TelCacheProvider::GetItemProperty failed [%#x]", v103);
    }
    else
    {
      v104 = -1;
      do
        ++v104;
      while ( v135[v104] );
      std::wstring::_Assign<unsigned short>((char *)this + 568, v135);
    }
    v130 = 520;
    v105 = &Application::InventoryItemValueNameMsiPackageCode;
    if ( (unsigned __int64)qword_180122408 > 7 )
      v105 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
    v106 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v105,
             v135,
             &v130);
    if ( v106 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2802, "TelCacheProvider::GetItemProperty failed [%#x]", v106);
    }
    else
    {
      v107 = -1;
      do
        ++v107;
      while ( v135[v107] );
      std::wstring::_Assign<unsigned short>((char *)this + 632, v135);
    }
    v130 = 520;
    v108 = &Application::InventoryItemValueNameMsiProductCode;
    if ( (unsigned __int64)qword_1801223E8 > 7 )
      v108 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
    v109 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v108,
             v135,
             &v130);
    if ( v109 >= 0 )
    {
      do
        ++v6;
      while ( v135[v6] );
LABEL_316:
      std::wstring::_Assign<unsigned short>((char *)this + 600, v135);
      return 0;
    }
    v110 = 2813;
    goto LABEL_319;
  }
  if ( (unsigned __int8)std::operator!=<unsigned short>((char *)this + 336, &Application::ApplicationSourceAppxPackage)
    && (unsigned __int8)std::operator!=<unsigned short>((char *)this + 336, &Application::ApplicationSourceAppvPackage) )
  {
    v130 = 520;
    v111 = &Application::InventoryItemValueNameUninstallString;
    if ( (unsigned __int64)qword_180122528 > 7 )
      v111 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    v112 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v111,
             v135,
             &v130);
    if ( v112 < 0 )
    {
      if ( v112 != -2147024894 )
        AslLogCallPrintf(1, "Application::Retrieve", 2830, "TelCacheProvider::GetItemProperty failed [%#x]", v112);
    }
    else
    {
      v113 = -1;
      do
        ++v113;
      while ( v135[v113] );
      std::wstring::_Assign<unsigned short>((char *)this + 224, v135);
    }
    v130 = 520;
    v114 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_180122548 > 7 )
      v114 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    v115 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v114,
             v135,
             &v130);
    if ( v115 < 0 )
    {
      if ( v115 != -2147024894 )
        AslLogCallPrintf(1, "Application::Retrieve", 2842, "TelCacheProvider::GetItemProperty failed [%#x]", v115);
    }
    else
    {
      v116 = -1;
      do
        ++v116;
      while ( v135[v116] );
      std::wstring::_Assign<unsigned short>((char *)this + 432, v135);
    }
    v131 = 0;
    v117 = &Application::InventoryItemValueNameHiddenArp;
    v118 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_180122448 > 7 )
      v118 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
           a2,
           v118,
           &v131) < 0 )
    {
      v130 = 520;
      if ( (unsigned __int64)qword_180122448 > 7 )
        v117 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
      v120 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
               a2,
               v117,
               v135,
               &v130);
      if ( v120 < 0 )
      {
        if ( v120 != -2147024894 )
          AslLogCallPrintf(1, "Application::Retrieve", 2871, "TelCacheProvider::GetItemProperty failed [%#x]", v120);
LABEL_291:
        v121 = &Application::ApplicationSourceMsi;
        if ( (unsigned __int64)qword_180121EA8 > 7 )
          v121 = (__int64 *)Application::ApplicationSourceMsi;
        if ( *((_QWORD *)this + 45) > 7u )
          v41 = (_QWORD *)*v41;
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v41, *((_QWORD *)this + 44), v121) )
        {
          v130 = 520;
          v122 = &Application::InventoryItemValueNameMsiInstallDate;
          if ( (unsigned __int64)qword_180122428 > 7 )
            v122 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
          v123 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v122,
                   v135,
                   &v130);
          if ( v123 < 0 )
          {
            if ( v123 != -2147024894 )
              AslLogCallPrintf(1, "Application::Retrieve", 2886, "TelCacheProvider::GetItemProperty failed [%#x]", v123);
          }
          else
          {
            v124 = -1;
            do
              ++v124;
            while ( v135[v124] );
            std::wstring::_Assign<unsigned short>((char *)this + 568, v135);
          }
          v130 = 520;
          v125 = &Application::InventoryItemValueNameMsiPackageCode;
          if ( (unsigned __int64)qword_180122408 > 7 )
            v125 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
          v126 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v125,
                   v135,
                   &v130);
          if ( v126 < 0 )
          {
            if ( v126 != -2147024894 )
              AslLogCallPrintf(1, "Application::Retrieve", 2897, "TelCacheProvider::GetItemProperty failed [%#x]", v126);
          }
          else
          {
            v127 = -1;
            do
              ++v127;
            while ( v135[v127] );
            std::wstring::_Assign<unsigned short>((char *)this + 632, v135);
          }
          v130 = 520;
          v128 = &Application::InventoryItemValueNameMsiProductCode;
          if ( (unsigned __int64)qword_1801223E8 > 7 )
            v128 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
          v109 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v128,
                   v135,
                   &v130);
          if ( v109 >= 0 )
          {
            do
              ++v6;
            while ( v135[v6] );
            goto LABEL_316;
          }
          if ( v109 == -2147024894 )
            return 0;
          v110 = 2908;
LABEL_319:
          AslLogCallPrintf(1, "Application::Retrieve", v110, "TelCacheProvider::GetItemProperty failed [%#x]", v109);
          return 0;
        }
        return 0;
      }
      v119 = (unsigned int)_o__wcsicmp(L"true", v135) == 0;
    }
    else
    {
      v119 = v131 != 0;
    }
    *((_BYTE *)this + 700) = v119;
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
