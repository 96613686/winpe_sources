# Application::Retrieve(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x180036560`
- end: `0x180037a71`
- name: `?Retrieve@Application@@UEAAKPEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `5393`
- prototype: `__int64 __fastcall(Application *this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800f93e0`

## callees

- `0x18000ddb8`
- `0x1800118d0`
- `0x180012950`
- `0x180018a60`
- `0x1800197d4`
- `0x18001e0d0`
- `0x180036560`
- `0x1800404c4`
- `0x180045480`
- `0x180046510`
- `0x180046f38`
- `0x180052f28`
- `0x180059920`
- `0x18005a8bc`
- `0x1800f92d0`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003718e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037840`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003718e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037840`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800368db`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800368db`

## string_xrefs

- `0x1800365ec`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800368f1`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800369ad`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180036a2d`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180036adf`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180036b5f`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180036c57`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180036d27`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180036e33`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180036eb0`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180036f14`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180036f91`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180037064`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800370eb`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800371a5`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180037225`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003733f`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180037441`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800374bc`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180037520`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003759b`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180037616`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180037720`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800377a2`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180037865`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180037925`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800379a6`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180037a32`: `TelCacheProvider::GetItemProperty failed [%#x]`

## pseudocode

```c
__int64 __fastcall Application::Retrieve(Application *this, struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  __int64 *v4; // rdx
  int v5; // eax
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 *v8; // rdx
  int v9; // esi
  __int64 v10; // r8
  int v11; // r8d
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
  int v25; // r8d
  int v26; // eax
  __int64 *v27; // rdx
  int v28; // esi
  __int64 v29; // r8
  int v30; // r8d
  __int64 v31; // r8
  __int64 *v32; // rdx
  int v33; // esi
  __int64 v34; // r8
  char *v35; // rcx
  __int64 v36; // r8
  __int64 *v37; // rdx
  int v38; // eax
  __int64 v39; // r8
  __int64 *v40; // rdx
  int v41; // eax
  _QWORD *v42; // r12
  __int64 v43; // r8
  char IsEnabled; // al
  char *v45; // rcx
  __int64 *v46; // rdx
  int v47; // eax
  int v48; // r8d
  int v49; // ecx
  __int64 *v50; // rdx
  __int64 *v51; // rdx
  int v52; // esi
  __int64 v53; // rsi
  __int64 v54; // r15
  __int64 v55; // rsi
  __int64 v56; // r15
  __int64 *v57; // rdx
  int v58; // eax
  __int64 v59; // r8
  __int64 *v60; // rdx
  int v61; // eax
  __int64 v62; // r8
  __int64 *v63; // rdx
  int v64; // eax
  __int64 *v65; // rdx
  int v66; // eax
  __int64 v67; // r8
  _QWORD *v68; // r15
  __int64 v69; // rdx
  __int64 *v70; // r8
  Application *v71; // rcx
  __int64 *v72; // rdx
  int v73; // eax
  __int64 v74; // r8
  __int64 *v75; // rdx
  int v76; // eax
  __int64 v77; // r8
  __int64 *v78; // rsi
  __int64 *v79; // rdx
  bool v80; // al
  int v81; // eax
  __int64 *v82; // rdx
  int v83; // eax
  __int64 v84; // r8
  __int64 *v85; // rdx
  int v86; // eax
  __int64 v87; // r8
  __int64 *v88; // rdx
  __int64 v89; // r8
  int v90; // r8d
  __int64 *v91; // r8
  Application *v92; // rcx
  __int64 *v93; // r8
  Application *v94; // rcx
  __int64 *v95; // rdx
  __int64 v96; // r8
  __int64 *v97; // rdx
  __int64 v98; // r8
  __int64 *v99; // rdx
  __int64 *v100; // rdx
  __int64 v101; // r8
  __int64 *v102; // rdx
  __int64 v103; // r8
  __int64 *v104; // rdx
  int v105; // r8d
  __int64 *v106; // rdx
  int v107; // eax
  __int64 v108; // r8
  __int64 *v109; // rdx
  int v110; // eax
  __int64 v111; // r8
  __int64 *v112; // rsi
  __int64 *v113; // rdx
  bool v114; // al
  int v115; // eax
  __int64 *v116; // r8
  __int64 *v117; // rdx
  int v118; // eax
  __int64 v119; // r8
  __int64 *v120; // rdx
  int v121; // eax
  __int64 v122; // r8
  __int64 *v123; // rdx
  int v124; // eax
  int v126; // [rsp+28h] [rbp-E0h]
  int v127; // [rsp+28h] [rbp-E0h]
  int v128; // [rsp+28h] [rbp-E0h]
  int v129; // [rsp+38h] [rbp-D0h] BYREF
  int v130; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v131; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v132; // [rsp+48h] [rbp-C0h]
  __int64 v133; // [rsp+58h] [rbp-B0h]
  _BYTE v134[40]; // [rsp+60h] [rbp-A8h] BYREF
  _WORD v135[520]; // [rsp+88h] [rbp-80h] BYREF

  v133 = -2;
  memset_0(v135, 0, sizeof(v135));
  v129 = 520;
  v4 = &Application::InventoryItemValueNameProgramId;
  if ( (unsigned __int64)qword_180182A78 > 7 )
    v4 = (__int64 *)Application::InventoryItemValueNameProgramId;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         v4,
         v135,
         &v129);
  v6 = -1;
  if ( v5 < 0 )
  {
    v126 = v5;
    AslLogCallPrintf(
      1,
      (unsigned int)"Application::Retrieve",
      2334,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( v135[v7] );
    std::wstring::_Assign<unsigned short>((char *)this + 56, v135);
  }
  v129 = 520;
  v8 = &Application::InventoryItemValueNameProgramInstanceId;
  if ( (unsigned __int64)qword_180182A98 > 7 )
    v8 = (__int64 *)Application::InventoryItemValueNameProgramInstanceId;
  v9 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         v8,
         v135,
         &v129);
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
    v126 = v9;
    AslLogCallPrintf(
      1,
      (unsigned int)"Application::Retrieve",
      v11,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_23:
  v129 = 520;
  v13 = &Application::InventoryItemValueNameName;
  if ( (unsigned __int64)qword_180182AB8 > 7 )
    v13 = (__int64 *)Application::InventoryItemValueNameName;
  v14 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v13,
          v135,
          &v129);
  if ( v14 < 0 )
  {
    v126 = v14;
    AslLogCallPrintf(
      1,
      (unsigned int)"Application::Retrieve",
      2376,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
  else
  {
    v15 = -1;
    do
      ++v15;
    while ( v135[v15] );
    std::wstring::_Assign<unsigned short>((char *)this + 96, v135);
  }
  v129 = 520;
  v16 = &Application::InventoryItemValueNameVersion;
  if ( (unsigned __int64)qword_180182AD8 > 7 )
    v16 = (__int64 *)Application::InventoryItemValueNameVersion;
  v17 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v16,
          v135,
          &v129);
  if ( v17 < 0 )
  {
    v126 = v17;
    AslLogCallPrintf(
      1,
      (unsigned int)"Application::Retrieve",
      2390,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
  else
  {
    v18 = -1;
    do
      ++v18;
    while ( v135[v18] );
    std::wstring::_Assign<unsigned short>((char *)this + 160, v135);
  }
  v129 = 520;
  v19 = &Application::InventoryItemValueNamePublisher;
  if ( (unsigned __int64)qword_180182AF8 > 7 )
    v19 = (__int64 *)Application::InventoryItemValueNamePublisher;
  v20 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v19,
          v135,
          &v129);
  if ( v20 < 0 )
  {
    v126 = v20;
    AslLogCallPrintf(
      1,
      (unsigned int)"Application::Retrieve",
      2404,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
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
  if ( (unsigned __int64)qword_180182B18 > 7 )
    v23 = (__int64 *)Application::InventoryItemValueNameLanguage;
  v24 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 80LL))(
          a2,
          v23,
          (char *)this + 464);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v24 >= 0 )
      goto LABEL_56;
    v126 = v24;
    v25 = 2413;
  }
  else
  {
    if ( v24 >= 0 )
      goto LABEL_56;
    v129 = 520;
    if ( (unsigned __int64)qword_180182B18 > 7 )
      v22 = (__int64 *)Application::InventoryItemValueNameLanguage;
    v26 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v22,
            v135,
            &v129);
    if ( v26 >= 0 )
    {
      *((_DWORD *)this + 116) = _o__wtoi(v135);
      goto LABEL_56;
    }
    v126 = v26;
    v25 = 2430;
  }
  AslLogCallPrintf(
    1,
    (unsigned int)"Application::Retrieve",
    v25,
    (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
LABEL_56:
  v129 = 520;
  v27 = &Application::InventoryItemValueNameInstallDate;
  if ( (unsigned __int64)qword_180182C18 > 7 )
    v27 = (__int64 *)Application::InventoryItemValueNameInstallDate;
  v28 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v27,
          v135,
          &v129);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v28 >= 0 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v135[v29] );
LABEL_67:
      std::wstring::_Assign<unsigned short>((char *)this + 256, v135);
      goto LABEL_71;
    }
    v30 = 2447;
    goto LABEL_70;
  }
  if ( v28 >= 0 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v135[v31] );
    goto LABEL_67;
  }
  if ( v28 != -2147024894 )
  {
    v30 = 2459;
LABEL_70:
    v126 = v28;
    AslLogCallPrintf(
      1,
      (unsigned int)"Application::Retrieve",
      v30,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_71:
  v129 = 520;
  v32 = &Application::InventoryItemValueNameAppType;
  if ( (unsigned __int64)qword_180182D18 > 7 )
    v32 = (__int64 *)Application::InventoryItemValueNameAppType;
  v33 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v32,
          v135,
          &v129);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v33 < 0 )
    {
      v126 = v33;
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2475,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
      goto LABEL_84;
    }
    v34 = -1;
    do
      ++v34;
    while ( v135[v34] );
    v35 = (char *)this + 368;
    goto LABEL_82;
  }
  v35 = (char *)this + 368;
  if ( v33 >= 0 )
  {
    v36 = -1;
    do
      ++v36;
    while ( v135[v36] );
LABEL_82:
    std::wstring::_Assign<unsigned short>(v35, v135);
    goto LABEL_84;
  }
  std::wstring::operator=(v35, Application::ApplicationTypeApplication);
LABEL_84:
  v129 = 520;
  v37 = &Application::InventoryItemValueNameRootDirPath;
  if ( (unsigned __int64)qword_180182C98 > 7 )
    v37 = (__int64 *)Application::InventoryItemValueNameRootDirPath;
  v38 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v37,
          v135,
          &v129);
  if ( v38 < 0 )
  {
    v126 = v38;
    AslLogCallPrintf(
      1,
      (unsigned int)"Application::Retrieve",
      2502,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
  else
  {
    v39 = -1;
    do
      ++v39;
    while ( v135[v39] );
    std::wstring::_Assign<unsigned short>((char *)this + 192, v135);
  }
  v129 = 520;
  v40 = &Application::InventoryItemValueNameSource;
  if ( (unsigned __int64)qword_180182B38 > 7 )
    v40 = (__int64 *)Application::InventoryItemValueNameSource;
  v41 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v40,
          v135,
          &v129);
  v42 = (_QWORD *)((char *)this + 336);
  if ( v41 < 0 )
  {
    v126 = v41;
    AslLogCallPrintf(
      1,
      (unsigned int)"Application::Retrieve",
      2516,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
  else
  {
    v43 = -1;
    do
      ++v43;
    while ( v135[v43] );
    std::wstring::_Assign<unsigned short>((char *)this + 336, v135);
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl);
  v45 = (char *)this + 336;
  if ( IsEnabled )
  {
    if ( !(unsigned __int8)std::operator!=<unsigned short>(v45, &Application::ApplicationSourceAppxPackage) )
    {
      *((_BYTE *)this + 88) = 0;
      goto LABEL_113;
    }
    v130 = 0;
    v46 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_180182CF8 > 7 )
      v46 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
    v47 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
            a2,
            v46,
            &v130);
    if ( v47 < 0 )
    {
      *((_BYTE *)this + 88) = 0;
      v48 = 2532;
      v49 = 3;
      goto LABEL_112;
    }
LABEL_109:
    *((_BYTE *)this + 88) = v130 != 0;
    goto LABEL_113;
  }
  if ( !(unsigned __int8)std::operator!=<unsigned short>(v45, &Application::ApplicationSourceAppxPackage) )
    goto LABEL_113;
  v130 = 0;
  v50 = &Application::InventoryItemValueNameSentDetailedInv;
  if ( (unsigned __int64)qword_180182CF8 > 7 )
    v50 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
  v47 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
          a2,
          v50,
          &v130);
  if ( v47 >= 0 )
    goto LABEL_109;
  *((_BYTE *)this + 88) = 0;
  if ( v47 == -2147024894 )
    goto LABEL_113;
  v48 = 2557;
  v49 = 1;
LABEL_112:
  v126 = v47;
  AslLogCallPrintf(
    v49,
    (unsigned int)"Application::Retrieve",
    v48,
    (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
LABEL_113:
  v129 = 520;
  v51 = &Application::InventoryItemValueNameUserSid;
  if ( (unsigned __int64)qword_180182D38 > 7 )
    v51 = (__int64 *)Application::InventoryItemValueNameUserSid;
  v52 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v51,
          v135,
          &v129);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v52 < 0 )
    {
      v126 = v52;
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2579,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
      goto LABEL_127;
    }
    std::wstring::wstring(v134, v135);
    WstringContainerFromDelimitedString<std::vector<std::wstring>>((__int64)&v131);
    std::wstring::~wstring(v134);
    v53 = v131;
    v54 = v132;
    while ( v53 != v54 )
    {
      std::wstring::wstring(v134, v53);
      Application::AddUserSid(this, v134);
      std::wstring::~wstring(v134);
      v53 += 32;
    }
  }
  else
  {
    if ( v52 < 0 )
      goto LABEL_127;
    std::wstring::wstring(v134, v135);
    WstringContainerFromDelimitedString<std::vector<std::wstring>>((__int64)&v131);
    std::wstring::~wstring(v134);
    v55 = v131;
    v56 = v132;
    while ( v55 != v56 )
    {
      std::wstring::wstring(v134, v55);
      Application::AddUserSid(this, v134);
      std::wstring::~wstring(v134);
      v55 += 32;
    }
  }
  std::vector<std::wstring>::_Tidy(&v131);
LABEL_127:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v129 = 520;
    v57 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_180182C58 > 7 )
      v57 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v58 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v57,
            v135,
            &v129);
    if ( v58 < 0 )
    {
      v126 = v58;
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2605,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      v59 = -1;
      do
        ++v59;
      while ( v135[v59] );
      std::wstring::_Assign<unsigned short>((char *)this + 904, v135);
    }
    v129 = 520;
    v60 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_180182C78 > 7 )
      v60 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v61 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v60,
            v135,
            &v129);
    if ( v61 < 0 )
    {
      v126 = v61;
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2616,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      v62 = -1;
      do
        ++v62;
      while ( v135[v62] );
      std::wstring::_Assign<unsigned short>((char *)this + 936, v135);
    }
    v130 = 0;
    v63 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_180182BF8 > 7 )
      v63 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    v64 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
            a2,
            v63,
            &v130);
    if ( v64 < 0 )
    {
      v126 = v64;
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2627,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      *((_BYTE *)this + 968) = v130 != 0;
    }
    v129 = 520;
    v65 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_180182B58 > 7 )
      v65 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v66 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v65,
            v135,
            &v129);
    if ( v66 < 0 )
    {
      v126 = v66;
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2639,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      v67 = -1;
      do
        ++v67;
      while ( v135[v67] );
      std::wstring::_Assign<unsigned short>((char *)this + 808, v135);
    }
    v68 = (_QWORD *)((char *)this + 352);
    goto LABEL_194;
  }
  v68 = (_QWORD *)((char *)this + 352);
  v69 = *((_QWORD *)this + 44);
  if ( !v69 )
    goto LABEL_162;
  v70 = &Application::ApplicationSourceAppxPackage;
  if ( (unsigned __int64)qword_180182778 > 7 )
    v70 = (__int64 *)Application::ApplicationSourceAppxPackage;
  v71 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v42;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v71, v69, v70, qword_180182770, v126) )
  {
LABEL_162:
    v129 = 520;
    v72 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_180182C58 > 7 )
      v72 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v73 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v72,
            v135,
            &v129);
    if ( v73 < 0 )
    {
      v126 = v73;
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2656,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      v74 = -1;
      do
        ++v74;
      while ( v135[v74] );
      std::wstring::_Assign<unsigned short>((char *)this + 904, v135);
    }
    v129 = 520;
    v75 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_180182C78 > 7 )
      v75 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v76 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v75,
            v135,
            &v129);
    if ( v76 < 0 )
    {
      if ( v76 != -2147024894 )
      {
        v126 = v76;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Retrieve",
          2668,
          (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
      }
    }
    else
    {
      v77 = -1;
      do
        ++v77;
      while ( v135[v77] );
      std::wstring::_Assign<unsigned short>((char *)this + 936, v135);
    }
    v130 = 0;
    v78 = &Application::InventoryItemValueNameInboxStoreApp;
    v79 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_180182BF8 > 7 )
      v79 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
           a2,
           v79,
           &v130) < 0 )
    {
      v129 = 520;
      if ( (unsigned __int64)qword_180182BF8 > 7 )
        v78 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
      v81 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
              a2,
              v78,
              v135,
              &v129);
      if ( v81 < 0 )
      {
        v126 = v81;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Retrieve",
          2696,
          (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
        goto LABEL_187;
      }
      v80 = (unsigned int)_o__wcsicmp(L"true", v135) == 0;
    }
    else
    {
      v80 = v130 != 0;
    }
    *((_BYTE *)this + 968) = v80;
LABEL_187:
    v129 = 520;
    v82 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_180182B58 > 7 )
      v82 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v83 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v82,
            v135,
            &v129);
    if ( v83 < 0 )
    {
      v126 = v83;
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2709,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      v84 = -1;
      do
        ++v84;
      while ( v135[v84] );
      std::wstring::_Assign<unsigned short>((char *)this + 808, v135);
    }
  }
LABEL_194:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v129 = 520;
    v85 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_180182C38 > 7 )
      v85 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v86 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v85,
            v135,
            &v129);
    if ( v86 >= 0 )
    {
      v87 = -1;
      do
        ++v87;
      while ( v135[v87] );
LABEL_200:
      std::wstring::_Assign<unsigned short>((char *)this + 744, v135);
      goto LABEL_201;
    }
    v90 = 2725;
LABEL_209:
    v126 = v86;
    AslLogCallPrintf(
      1,
      (unsigned int)"Application::Retrieve",
      v90,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    goto LABEL_201;
  }
  if ( !*v68 )
    goto LABEL_223;
  v91 = &Application::ApplicationSourceAppxPackage;
  if ( (unsigned __int64)qword_180182778 > 7 )
    v91 = (__int64 *)Application::ApplicationSourceAppxPackage;
  v92 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v42;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v92, *v68, v91, qword_180182770, v126) )
    goto LABEL_223;
  v93 = &Application::ApplicationSourceAppvPackage;
  if ( (unsigned __int64)qword_180182758 > 7 )
    v93 = (__int64 *)Application::ApplicationSourceAppvPackage;
  v94 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v42;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                          v94,
                          *((_QWORD *)this + 44),
                          v93,
                          qword_180182750,
                          v126) )
  {
LABEL_223:
    v129 = 520;
    v95 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_180182C38 > 7 )
      v95 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v86 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v95,
            v135,
            &v129);
    if ( v86 >= 0 )
    {
      v96 = -1;
      do
        ++v96;
      while ( v135[v96] );
      goto LABEL_200;
    }
    v90 = 2742;
    goto LABEL_209;
  }
LABEL_201:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v129 = 520;
    v88 = &Application::InventoryItemValueNameUninstallString;
    if ( (unsigned __int64)qword_180182CB8 > 7 )
      v88 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
           a2,
           v88,
           v135,
           &v129) < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2758,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      v89 = -1;
      do
        ++v89;
      while ( v135[v89] );
      std::wstring::_Assign<unsigned short>((char *)this + 224, v135);
    }
    v129 = 520;
    v97 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_180182CD8 > 7 )
      v97 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
           a2,
           v97,
           v135,
           &v129) < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2769,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      v98 = -1;
      do
        ++v98;
      while ( v135[v98] );
      std::wstring::_Assign<unsigned short>((char *)this + 432, v135);
    }
    v130 = 0;
    v99 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_180182BD8 > 7 )
      v99 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
           a2,
           v99,
           &v130) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2780,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    else
      *((_BYTE *)this + 700) = v130 != 0;
    v129 = 520;
    v100 = &Application::InventoryItemValueNameMsiInstallDate;
    if ( (unsigned __int64)qword_180182BB8 > 7 )
      v100 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
           a2,
           v100,
           v135,
           &v129) < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2791,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      v101 = -1;
      do
        ++v101;
      while ( v135[v101] );
      std::wstring::_Assign<unsigned short>((char *)this + 568, v135);
    }
    v129 = 520;
    v102 = &Application::InventoryItemValueNameMsiPackageCode;
    if ( (unsigned __int64)qword_180182B98 > 7 )
      v102 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
           a2,
           v102,
           v135,
           &v129) < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Retrieve",
        2802,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
    else
    {
      v103 = -1;
      do
        ++v103;
      while ( v135[v103] );
      std::wstring::_Assign<unsigned short>((char *)this + 632, v135);
    }
    v129 = 520;
    v104 = &Application::InventoryItemValueNameMsiProductCode;
    if ( (unsigned __int64)qword_180182B78 > 7 )
      v104 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
           a2,
           v104,
           v135,
           &v129) >= 0 )
    {
      do
        ++v6;
      while ( v135[v6] );
LABEL_317:
      std::wstring::_Assign<unsigned short>((char *)this + 600, v135);
      return 0;
    }
    v105 = 2813;
    goto LABEL_320;
  }
  if ( (unsigned __int8)std::operator!=<unsigned short>((char *)this + 336, &Application::ApplicationSourceAppxPackage)
    && (unsigned __int8)std::operator!=<unsigned short>((char *)this + 336, &Application::ApplicationSourceAppvPackage) )
  {
    v129 = 520;
    v106 = &Application::InventoryItemValueNameUninstallString;
    if ( (unsigned __int64)qword_180182CB8 > 7 )
      v106 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    v107 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v106,
             v135,
             &v129);
    if ( v107 < 0 )
    {
      if ( v107 != -2147024894 )
      {
        v126 = v107;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Retrieve",
          2830,
          (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
      }
    }
    else
    {
      v108 = -1;
      do
        ++v108;
      while ( v135[v108] );
      std::wstring::_Assign<unsigned short>((char *)this + 224, v135);
    }
    v129 = 520;
    v109 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_180182CD8 > 7 )
      v109 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    v110 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v109,
             v135,
             &v129);
    if ( v110 < 0 )
    {
      if ( v110 != -2147024894 )
      {
        v126 = v110;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Retrieve",
          2842,
          (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
      }
    }
    else
    {
      v111 = -1;
      do
        ++v111;
      while ( v135[v111] );
      std::wstring::_Assign<unsigned short>((char *)this + 432, v135);
    }
    v130 = 0;
    v112 = &Application::InventoryItemValueNameHiddenArp;
    v113 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_180182BD8 > 7 )
      v113 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
           a2,
           v113,
           &v130) < 0 )
    {
      v129 = 520;
      if ( (unsigned __int64)qword_180182BD8 > 7 )
        v112 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
      v115 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
               a2,
               v112,
               v135,
               &v129);
      if ( v115 < 0 )
      {
        if ( v115 != -2147024894 )
        {
          v126 = v115;
          AslLogCallPrintf(
            1,
            (unsigned int)"Application::Retrieve",
            2871,
            (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
        }
LABEL_292:
        v116 = &Application::ApplicationSourceMsi;
        if ( (unsigned __int64)qword_180182638 > 7 )
          v116 = (__int64 *)Application::ApplicationSourceMsi;
        if ( *((_QWORD *)this + 45) > 7u )
          v42 = (_QWORD *)*v42;
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                v42,
                                *((_QWORD *)this + 44),
                                v116,
                                qword_180182630,
                                v126) )
        {
          v129 = 520;
          v117 = &Application::InventoryItemValueNameMsiInstallDate;
          if ( (unsigned __int64)qword_180182BB8 > 7 )
            v117 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
          v118 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v117,
                   v135,
                   &v129);
          if ( v118 < 0 )
          {
            if ( v118 != -2147024894 )
            {
              v127 = v118;
              AslLogCallPrintf(
                1,
                (unsigned int)"Application::Retrieve",
                2886,
                (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
            }
          }
          else
          {
            v119 = -1;
            do
              ++v119;
            while ( v135[v119] );
            std::wstring::_Assign<unsigned short>((char *)this + 568, v135);
          }
          v129 = 520;
          v120 = &Application::InventoryItemValueNameMsiPackageCode;
          if ( (unsigned __int64)qword_180182B98 > 7 )
            v120 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
          v121 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *, int))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v120,
                   v135,
                   &v129,
                   v127);
          if ( v121 < 0 )
          {
            if ( v121 != -2147024894 )
            {
              v128 = v121;
              AslLogCallPrintf(
                1,
                (unsigned int)"Application::Retrieve",
                2897,
                (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
            }
          }
          else
          {
            v122 = -1;
            do
              ++v122;
            while ( v135[v122] );
            std::wstring::_Assign<unsigned short>((char *)this + 632, v135);
          }
          v129 = 520;
          v123 = &Application::InventoryItemValueNameMsiProductCode;
          if ( (unsigned __int64)qword_180182B78 > 7 )
            v123 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
          v124 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *, int))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v123,
                   v135,
                   &v129,
                   v128);
          if ( v124 >= 0 )
          {
            do
              ++v6;
            while ( v135[v6] );
            goto LABEL_317;
          }
          if ( v124 == -2147024894 )
            return 0;
          v105 = 2908;
LABEL_320:
          AslLogCallPrintf(
            1,
            (unsigned int)"Application::Retrieve",
            v105,
            (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
          return 0;
        }
        return 0;
      }
      v114 = (unsigned int)_o__wcsicmp(L"true", v135) == 0;
    }
    else
    {
      v114 = v130 != 0;
    }
    *((_BYTE *)this + 700) = v114;
    goto LABEL_292;
  }
  return 0;
}

```

## disassembly

```asm
0x180036560  mov     rax, rsp
0x180036563  push    rbp
0x180036564  push    rsi
0x180036565  push    rdi
0x180036566  push    r12
0x180036568  push    r13
0x18003656a  push    r14
0x18003656c  push    r15
0x18003656e  lea     rbp, [rax-3D8h]
0x180036575  sub     rsp, 4A0h
0x18003657c  mov     [rsp+4D0h+var_480], 0FFFFFFFFFFFFFFFEh
0x180036585  mov     [rax+18h], rbx
0x180036589  mov     rax, cs:__security_cookie
0x180036590  xor     rax, rsp
0x180036593  mov     [rbp+3D0h+var_40], rax
0x18003659a  mov     r14, rdx
0x18003659d  mov     rbx, rcx
0x1800365a0  xor     r13d, r13d
0x1800365a3  xor     edx, edx; Val
0x1800365a5  mov     r8d, 410h; Size
0x1800365ab  lea     rcx, [rbp+3D0h+var_450]; void *
0x1800365af  call    memset_0
0x1800365b4  mov     esi, 208h
0x1800365b9  mov     dword ptr [rsp+4D0h+var_4A0], esi
0x1800365bd  mov     rax, [r14]
0x1800365c0  lea     rdx, ?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x1800365c7  cmp     cs:qword_180182A78, 7
0x1800365cf  cmova   rdx, cs:?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x1800365d7  lea     r9, [rsp+4D0h+var_4A0]
0x1800365dc  lea     r8, [rbp+3D0h+var_450]
0x1800365e0  mov     rcx, r14
0x1800365e3  mov     rax, [rax+40h]
0x1800365e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365ec  lea     r15, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x1800365f3  lea     r12, aApplicationRet; "Application::Retrieve"
0x1800365fa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800365fe  test    eax, eax
0x180036600  js      short loc_180036622
0x180036602  lea     rax, [rbp+3D0h+var_450]
0x180036606  mov     r8, rdi
0x180036609  inc     r8
0x18003660c  cmp     [rax+r8*2], r13w
0x180036611  jnz     short loc_180036609
0x180036613  lea     rcx, [rbx+38h]
0x180036617  lea     rdx, [rbp+3D0h+var_450]
0x18003661b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180036620  jmp     short loc_18003663C
0x180036622  mov     [rsp+20h], eax
0x180036626  mov     r9, r15
0x180036629  mov     r8d, 91Eh
0x18003662f  mov     rdx, r12
0x180036632  mov     ecx, 1
0x180036637  call    AslLogCallPrintf
0x18003663c  mov     dword ptr [rsp+4D0h+var_4A0], esi
0x180036640  mov     rax, [r14]
0x180036643  lea     rdx, ?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x18003664a  cmp     cs:qword_180182A98, 7
0x180036652  cmova   rdx, cs:?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x18003665a  lea     r9, [rsp+4D0h+var_4A0]
0x18003665f  lea     r8, [rbp+3D0h+var_450]
0x180036663  mov     rcx, r14
0x180036666  mov     rax, [rax+40h]
0x18003666a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003666f  mov     esi, eax
0x180036671  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180036678  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003667d  test    al, al
0x18003667f  jz      short loc_1800366A0
0x180036681  test    esi, esi
0x180036683  js      short loc_180036698
0x180036685  lea     rax, [rbp+3D0h+var_450]
0x180036689  mov     r8, rdi
0x18003668c  inc     r8
0x18003668f  cmp     [rax+r8*2], r13w
0x180036694  jnz     short loc_18003668C
0x180036696  jmp     short loc_1800366B5
0x180036698  mov     r8d, 92Dh
0x18003669e  jmp     short loc_1800366D5
0x1800366a0  test    esi, esi
0x1800366a2  js      short loc_1800366C7
0x1800366a4  lea     rax, [rbp+3D0h+var_450]
0x1800366a8  mov     r8, rdi
0x1800366ab  inc     r8
0x1800366ae  cmp     [rax+r8*2], r13w
0x1800366b3  jnz     short loc_1800366AB
0x1800366b5  lea     rcx, [rbx+190h]
0x1800366bc  lea     rdx, [rbp+3D0h+var_450]
0x1800366c0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800366c5  jmp     short loc_1800366E9
0x1800366c7  cmp     esi, 80070002h
0x1800366cd  jz      short loc_1800366E9
0x1800366cf  mov     r8d, 939h
0x1800366d5  mov     [rsp+20h], esi
0x1800366d9  mov     r9, r15
0x1800366dc  mov     rdx, r12
0x1800366df  mov     ecx, 1
0x1800366e4  call    AslLogCallPrintf
0x1800366e9  mov     esi, 208h
0x1800366ee  mov     dword ptr [rsp+4D0h+var_4A0], esi
0x1800366f2  mov     rax, [r14]
0x1800366f5  lea     rdx, ?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x1800366fc  cmp     cs:qword_180182AB8, 7
0x180036704  cmova   rdx, cs:?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x18003670c  lea     r9, [rsp+4D0h+var_4A0]
0x180036711  lea     r8, [rbp+3D0h+var_450]
0x180036715  mov     rcx, r14
0x180036718  mov     rax, [rax+40h]
0x18003671c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036721  test    eax, eax
0x180036723  js      short loc_180036745
0x180036725  lea     rax, [rbp+3D0h+var_450]
0x180036729  mov     r8, rdi
0x18003672c  inc     r8
0x18003672f  cmp     [rax+r8*2], r13w
0x180036734  jnz     short loc_18003672C
0x180036736  lea     rcx, [rbx+60h]
0x18003673a  lea     rdx, [rbp+3D0h+var_450]
0x18003673e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180036743  jmp     short loc_18003675F
0x180036745  mov     [rsp+20h], eax
0x180036749  mov     r9, r15
0x18003674c  mov     r8d, 948h
0x180036752  mov     rdx, r12
0x180036755  mov     ecx, 1
0x18003675a  call    AslLogCallPrintf
0x18003675f  mov     dword ptr [rsp+4D0h+var_4A0], esi
0x180036763  mov     rax, [r14]
0x180036766  lea     rdx, ?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x18003676d  cmp     cs:qword_180182AD8, 7
0x180036775  cmova   rdx, cs:?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x18003677d  lea     r9, [rsp+4D0h+var_4A0]
0x180036782  lea     r8, [rbp+3D0h+var_450]
0x180036786  mov     rcx, r14
0x180036789  mov     rax, [rax+40h]
0x18003678d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036792  test    eax, eax
0x180036794  js      short loc_1800367B9
0x180036796  lea     rax, [rbp+3D0h+var_450]
0x18003679a  mov     r8, rdi
0x18003679d  inc     r8
0x1800367a0  cmp     [rax+r8*2], r13w
0x1800367a5  jnz     short loc_18003679D
0x1800367a7  lea     rcx, [rbx+0A0h]
0x1800367ae  lea     rdx, [rbp+3D0h+var_450]
0x1800367b2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800367b7  jmp     short loc_1800367D3
0x1800367b9  mov     [rsp+20h], eax
0x1800367bd  mov     r9, r15
0x1800367c0  mov     r8d, 956h
0x1800367c6  mov     rdx, r12
0x1800367c9  mov     ecx, 1
0x1800367ce  call    AslLogCallPrintf
0x1800367d3  mov     dword ptr [rsp+4D0h+var_4A0], esi
0x1800367d7  mov     rax, [r14]
0x1800367da  lea     rdx, ?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x1800367e1  cmp     cs:qword_180182AF8, 7
0x1800367e9  cmova   rdx, cs:?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x1800367f1  lea     r9, [rsp+4D0h+var_4A0]
0x1800367f6  lea     r8, [rbp+3D0h+var_450]
0x1800367fa  mov     rcx, r14
0x1800367fd  mov     rax, [rax+40h]
0x180036801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036806  test    eax, eax
0x180036808  js      short loc_18003682D
0x18003680a  lea     rax, [rbp+3D0h+var_450]
0x18003680e  mov     r8, rdi
0x180036811  inc     r8
0x180036814  cmp     [rax+r8*2], r13w
0x180036819  jnz     short loc_180036811
0x18003681b  lea     rcx, [rbx+80h]
0x180036822  lea     rdx, [rbp+3D0h+var_450]
0x180036826  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003682b  jmp     short loc_180036847
0x18003682d  mov     [rsp+20h], eax
0x180036831  mov     r9, r15
0x180036834  mov     r8d, 964h
0x18003683a  mov     rdx, r12
0x18003683d  mov     ecx, 1
0x180036842  call    AslLogCallPrintf
0x180036847  mov     rax, [r14]
0x18003684a  lea     r15, ?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x180036851  mov     rdx, r15
0x180036854  cmp     cs:qword_180182B18, 7
0x18003685c  cmova   rdx, cs:?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x180036864  lea     r12, [rbx+1D0h]
0x18003686b  mov     r8, r12
0x18003686e  mov     rcx, r14
0x180036871  mov     rax, [rax+50h]
0x180036875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003687a  mov     esi, eax
0x18003687c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180036883  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180036888  test    al, al
0x18003688a  jz      short loc_18003689C
0x18003688c  test    esi, esi
0x18003688e  jns     short loc_180036909
0x180036890  mov     [rsp+20h], esi
0x180036894  mov     r8d, 96Dh
0x18003689a  jmp     short loc_1800368F1
0x18003689c  test    esi, esi
0x18003689e  jns     short loc_180036909
0x1800368a0  mov     dword ptr [rsp+4D0h+var_4A0], 208h
0x1800368a8  mov     rax, [r14]
0x1800368ab  cmp     cs:qword_180182B18, 7
0x1800368b3  cmova   r15, cs:?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x1800368bb  lea     r9, [rsp+4D0h+var_4A0]
0x1800368c0  lea     r8, [rbp+3D0h+var_450]
0x1800368c4  mov     rdx, r15
0x1800368c7  mov     rcx, r14
0x1800368ca  mov     rax, [rax+40h]
0x1800368ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368d3  test    eax, eax
0x1800368d5  js      short loc_1800368E7
0x1800368d7  lea     rcx, [rbp+3D0h+var_450]
0x1800368db  call    cs:__imp__o__wtoi
0x1800368e1  mov     [r12], eax
0x1800368e5  jmp     short loc_180036909
0x1800368e7  mov     [rsp+20h], eax
0x1800368eb  mov     r8d, 97Eh
0x1800368f1  lea     r9, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x1800368f8  lea     rdx, aApplicationRet; "Application::Retrieve"
0x1800368ff  mov     ecx, 1
0x180036904  call    AslLogCallPrintf
0x180036909  mov     r15d, 208h
0x18003690f  mov     dword ptr [rsp+4D0h+var_4A0], r15d
0x180036914  mov     rax, [r14]
0x180036917  lea     rdx, ?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x18003691e  cmp     cs:qword_180182C18, 7
0x180036926  cmova   rdx, cs:?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x18003692e  lea     r9, [rsp+4D0h+var_4A0]
0x180036933  lea     r8, [rbp+3D0h+var_450]
0x180036937  mov     rcx, r14
0x18003693a  mov     rax, [rax+40h]
0x18003693e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036943  mov     esi, eax
0x180036945  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003694c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180036951  test    al, al
0x180036953  jz      short loc_180036974
0x180036955  test    esi, esi
0x180036957  js      short loc_18003696C
0x180036959  lea     rax, [rbp+3D0h+var_450]
0x18003695d  mov     r8, rdi
0x180036960  inc     r8
0x180036963  cmp     [rax+r8*2], r13w
0x180036968  jnz     short loc_180036960
0x18003696a  jmp     short loc_180036989
0x18003696c  mov     r8d, 98Fh
0x180036972  jmp     short loc_1800369A9
0x180036974  test    esi, esi
0x180036976  js      short loc_18003699B
0x180036978  lea     rax, [rbp+3D0h+var_450]
0x18003697c  mov     r8, rdi
0x18003697f  inc     r8
0x180036982  cmp     [rax+r8*2], r13w
0x180036987  jnz     short loc_18003697F
0x180036989  lea     rcx, [rbx+100h]
0x180036990  lea     rdx, [rbp+3D0h+var_450]
0x180036994  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180036999  jmp     short loc_1800369C5
0x18003699b  cmp     esi, 80070002h
0x1800369a1  jz      short loc_1800369C5
0x1800369a3  mov     r8d, 99Bh
0x1800369a9  mov     [rsp+20h], esi
0x1800369ad  lea     r9, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x1800369b4  lea     rdx, aApplicationRet; "Application::Retrieve"
0x1800369bb  mov     ecx, 1
0x1800369c0  call    AslLogCallPrintf
0x1800369c5  mov     dword ptr [rsp+4D0h+var_4A0], r15d
0x1800369ca  mov     rax, [r14]
0x1800369cd  lea     rdx, ?InventoryItemValueNameAppType@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameAppType
0x1800369d4  cmp     cs:qword_180182D18, 7
0x1800369dc  cmova   rdx, cs:?InventoryItemValueNameAppType@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameAppType
0x1800369e4  lea     r9, [rsp+4D0h+var_4A0]
0x1800369e9  lea     r8, [rbp+3D0h+var_450]
0x1800369ed  mov     rcx, r14
0x1800369f0  mov     rax, [rax+40h]
0x1800369f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369f9  mov     esi, eax
0x1800369fb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180036a02  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180036a07  test    al, al
0x180036a09  jz      short loc_180036A4D
0x180036a0b  test    esi, esi
0x180036a0d  js      short loc_180036A29
0x180036a0f  lea     rax, [rbp+3D0h+var_450]
0x180036a13  mov     r8, rdi
0x180036a16  inc     r8
0x180036a19  cmp     [rax+r8*2], r13w
0x180036a1e  jnz     short loc_180036A16
0x180036a20  lea     rcx, [rbx+170h]
0x180036a27  jmp     short loc_180036A69
0x180036a29  mov     [rsp+20h], esi
0x180036a2d  lea     r9, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x180036a34  mov     r8d, 9ABh
0x180036a3a  lea     rdx, aApplicationRet; "Application::Retrieve"
0x180036a41  mov     ecx, 1
0x180036a46  call    AslLogCallPrintf
0x180036a4b  jmp     short loc_180036A80
0x180036a4d  lea     rcx, [rbx+170h]
  ... truncated ...
```
