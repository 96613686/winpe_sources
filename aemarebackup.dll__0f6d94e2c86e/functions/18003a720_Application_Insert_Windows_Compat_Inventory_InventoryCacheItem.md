# Application::Insert(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x18003a720`
- end: `0x18003b84b`
- name: `?Insert@Application@@UEAAKPEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `4395`
- prototype: `unsigned int __fastcall(Application *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18002772c`
- `0x18002b0b8`
- `0x180032ab8`
- `0x18003a720`
- `0x18004c020`
- `0x1800ec010`

## string_xrefs

- `0x18003a7b2`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003a831`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003a91f`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003a9a6`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003aa2d`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003aaab`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003ab2a`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003ac18`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003ac97`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003ad91`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003adf0`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003ae9e`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003af58`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003afa5`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003affd`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003b055`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003b0ad`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003b0fa`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003b160`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003b1c6`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003b22c`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003b292`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003b2ee`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x18003a7c1`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003a89d`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003a92e`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003a9b5`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003aa3c`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003aaba`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003ab96`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003ac27`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003ad0f`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003ada0`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003ae33`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003aeec`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b388`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b3d5`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b42d`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b48f`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b566`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b5e1`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b647`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b6b5`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b760`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b7c6`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x18003b81e`: `TelCacheProvider::SetItemProperty failed [#%x]`

## pseudocode

```c
__int64 __fastcall Application::Insert(Application *this, struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  char *v2; // rsi
  __int64 (__fastcall *v5)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v6; // rax
  __int64 *v7; // rdx
  int v8; // ebx
  __int64 (__fastcall *v9)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v10; // rax
  __int64 *v11; // rdx
  int v12; // eax
  const char *v13; // r9
  __int64 v14; // r8
  __int64 (__fastcall *v15)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v16; // rax
  __int64 *v17; // rdx
  __int64 (__fastcall *v18)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v19; // rax
  __int64 *v20; // rdx
  int v21; // ebx
  __int64 (__fastcall *v22)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v23; // rax
  __int64 *v24; // rdx
  int v25; // ebx
  __int64 (__fastcall *v26)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v27; // rax
  __int64 *v28; // rdx
  int v29; // ebx
  __int64 (__fastcall *v30)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD); // rbx
  unsigned int v31; // eax
  __int64 *v32; // rdx
  int v33; // ebx
  __int64 (__fastcall *v34)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v35; // rax
  __int64 *v36; // rdx
  int v37; // eax
  const char *v38; // r9
  __int64 v39; // r8
  __int64 (__fastcall *v40)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v41; // rax
  __int64 *v42; // rdx
  __int64 (__fastcall *v43)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v44; // rax
  __int64 *v45; // rdx
  int v46; // ebx
  __int64 (__fastcall *v47)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v48; // rax
  __int64 *v49; // rdx
  int v50; // eax
  const char *v51; // r9
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 (__fastcall *v54)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v55; // rax
  __int64 *v56; // rdx
  __int64 (__fastcall *v57)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v58; // rax
  __int64 *v59; // rdx
  int v60; // ebx
  __int64 *v61; // rdx
  int v62; // eax
  const char *v63; // r9
  __int64 v64; // r8
  __int64 *v65; // rdx
  _QWORD *v66; // rbx
  __int64 *v67; // rdx
  int v68; // eax
  const char *v69; // r9
  __int64 v70; // r8
  __int64 *v71; // rdx
  __int64 *v72; // rdx
  int v73; // eax
  __int64 *v74; // rdx
  int v75; // eax
  __int64 *v76; // rdx
  int v77; // eax
  __int64 *v78; // rdx
  int v79; // eax
  __int64 *v80; // rdx
  int v81; // eax
  __int64 *v82; // rdx
  int v83; // eax
  __int64 (__fastcall *v84)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v85; // rax
  __int64 *v86; // rdx
  int v87; // eax
  __int64 (__fastcall *v88)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v89; // rax
  __int64 *v90; // rdx
  int v91; // eax
  __int64 (__fastcall *v92)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v93; // rax
  __int64 *v94; // rdx
  int v95; // eax
  __int64 (__fastcall *v96)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v97; // rax
  __int64 *v98; // rdx
  int v99; // eax
  __int64 *v100; // rdx
  int v101; // eax
  const char *v102; // r9
  __int64 v103; // r8
  const wchar_t *v104; // rbx
  size_t v105; // r8
  const wchar_t *v106; // rdx
  const wchar_t *v107; // rcx
  __int64 *v108; // rdx
  int v109; // eax
  __int64 *v110; // rdx
  int v111; // eax
  __int64 *v112; // rdx
  int v113; // eax
  __int64 *v114; // rdx
  int v115; // eax
  size_t v116; // r8
  const wchar_t *v117; // rdx
  const wchar_t *v118; // rcx
  const wchar_t *v119; // rdx
  size_t v120; // r8
  const wchar_t *v121; // rcx
  __int64 *v122; // rdx
  int v123; // eax
  __int64 *v124; // rdx
  int v125; // eax
  __int64 (__fastcall *v126)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // r14
  _QWORD *v127; // rax
  __int64 *v128; // rdx
  int v129; // eax
  __int64 (__fastcall *v130)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // r14
  _QWORD *v131; // rax
  __int64 *v132; // rdx
  int v133; // eax
  const wchar_t *v134; // rdx
  size_t v135; // r8
  __int64 (__fastcall *v136)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v137; // rax
  __int64 *v138; // rdx
  int v139; // eax
  __int64 (__fastcall *v140)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v141; // rax
  __int64 *v142; // rdx
  int v143; // eax
  __int64 *v144; // rdx
  __int64 v146; // [rsp+20h] [rbp-48h]

  v2 = (char *)this + 16;
  v5 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v6 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  v7 = &Application::InventoryItemValueNameProgramId;
  if ( (unsigned __int64)qword_18011B3A8 > 7 )
    v7 = (__int64 *)Application::InventoryItemValueNameProgramId;
  v8 = v5(a2, v7, v6);
  if ( v8 < 0 )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 1936, "TelCacheProvider::SetItemProperty failed [%#x]", v8);
    else
      AslLogCallPrintf(1, "Application::Insert", 1940, "TelCacheProvider::SetItemProperty failed [#%x]", v8);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v9 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v10 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 80LL))(v2);
    if ( v10[3] > 7u )
      v10 = (_QWORD *)*v10;
    v11 = &Application::InventoryItemValueNameProgramInstanceId;
    if ( (unsigned __int64)qword_18011B3C8 > 7 )
      v11 = (__int64 *)Application::InventoryItemValueNameProgramInstanceId;
    v12 = v9(a2, v11, v10);
    if ( v12 < 0 )
    {
      v13 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v14 = 1950;
LABEL_23:
      LODWORD(v146) = v12;
      AslLogCallPrintf(1, "Application::Insert", v14, v13, v146);
    }
  }
  else if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 80LL))(v2) + 16) )
  {
    v15 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v16 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 80LL))(v2);
    if ( v16[3] > 7u )
      v16 = (_QWORD *)*v16;
    v17 = &Application::InventoryItemValueNameProgramInstanceId;
    if ( (unsigned __int64)qword_18011B3C8 > 7 )
      v17 = (__int64 *)Application::InventoryItemValueNameProgramInstanceId;
    v12 = v15(a2, v17, v16);
    if ( v12 < 0 )
    {
      v13 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v14 = 1962;
      goto LABEL_23;
    }
  }
  v18 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v19 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  if ( v19[3] > 7u )
    v19 = (_QWORD *)*v19;
  v20 = &Application::InventoryItemValueNameName;
  if ( (unsigned __int64)qword_18011B3E8 > 7 )
    v20 = (__int64 *)Application::InventoryItemValueNameName;
  v21 = v18(a2, v20, v19);
  if ( v21 < 0 )
  {
    LODWORD(v146) = v21;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 1972, "TelCacheProvider::SetItemProperty failed [%#x]", v146);
    else
      AslLogCallPrintf(1, "Application::Insert", 1976, "TelCacheProvider::SetItemProperty failed [#%x]", v146);
  }
  v22 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v23 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 32LL))(v2);
  if ( v23[3] > 7u )
    v23 = (_QWORD *)*v23;
  v24 = &Application::InventoryItemValueNameVersion;
  if ( (unsigned __int64)qword_18011B408 > 7 )
    v24 = (__int64 *)Application::InventoryItemValueNameVersion;
  v25 = v22(a2, v24, v23);
  if ( v25 < 0 )
  {
    LODWORD(v146) = v25;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 1985, "TelCacheProvider::SetItemProperty failed [%#x]", v146);
    else
      AslLogCallPrintf(1, "Application::Insert", 1989, "TelCacheProvider::SetItemProperty failed [#%x]", v146);
  }
  v26 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v27 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 24LL))(v2);
  if ( v27[3] > 7u )
    v27 = (_QWORD *)*v27;
  v28 = &Application::InventoryItemValueNamePublisher;
  if ( (unsigned __int64)qword_18011B428 > 7 )
    v28 = (__int64 *)Application::InventoryItemValueNamePublisher;
  v29 = v26(a2, v28, v27);
  if ( v29 < 0 )
  {
    LODWORD(v146) = v29;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 1998, "TelCacheProvider::SetItemProperty failed [%#x]", v146);
    else
      AslLogCallPrintf(1, "Application::Insert", 2002, "TelCacheProvider::SetItemProperty failed [#%x]", v146);
  }
  v30 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 152LL);
  v31 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 120LL))(v2);
  v32 = &Application::InventoryItemValueNameLanguage;
  if ( (unsigned __int64)qword_18011B448 > 7 )
    v32 = (__int64 *)Application::InventoryItemValueNameLanguage;
  v33 = v30(a2, v32, v31);
  if ( v33 < 0 )
  {
    LODWORD(v146) = v33;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 2011, "TelCacheProvider::SetItemProperty failed [%#x]", v146);
    else
      AslLogCallPrintf(1, "Application::Insert", 2015, "TelCacheProvider::SetItemProperty failed [#%x]", v146);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v34 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v35 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 56LL))(v2);
    if ( v35[3] > 7u )
      v35 = (_QWORD *)*v35;
    v36 = &Application::InventoryItemValueNameInstallDate;
    if ( (unsigned __int64)qword_18011B548 > 7 )
      v36 = (__int64 *)Application::InventoryItemValueNameInstallDate;
    v37 = v34(a2, v36, v35);
    if ( v37 < 0 )
    {
      v38 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v39 = 2024;
LABEL_68:
      LODWORD(v146) = v37;
      AslLogCallPrintf(1, "Application::Insert", v39, v38, v146);
    }
  }
  else if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 56LL))(v2) + 16) )
  {
    v40 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v41 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 56LL))(v2);
    if ( v41[3] > 7u )
      v41 = (_QWORD *)*v41;
    v42 = &Application::InventoryItemValueNameInstallDate;
    if ( (unsigned __int64)qword_18011B548 > 7 )
      v42 = (__int64 *)Application::InventoryItemValueNameInstallDate;
    v37 = v40(a2, v42, v41);
    if ( v37 < 0 )
    {
      v38 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v39 = 2035;
      goto LABEL_68;
    }
  }
  v43 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v44 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 64LL))(v2);
  if ( v44[3] > 7u )
    v44 = (_QWORD *)*v44;
  v45 = &Application::InventoryItemValueNameSource;
  if ( (unsigned __int64)qword_18011B468 > 7 )
    v45 = (__int64 *)Application::InventoryItemValueNameSource;
  v46 = v43(a2, v45, v44);
  if ( v46 < 0 )
  {
    LODWORD(v146) = v46;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 2045, "TelCacheProvider::SetItemProperty failed [%#x]", v146);
    else
      AslLogCallPrintf(1, "Application::Insert", 2049, "TelCacheProvider::SetItemProperty failed [#%x]", v146);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v47 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v48 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 72LL))(v2);
    if ( v48[3] > 7u )
      v48 = (_QWORD *)*v48;
    v49 = &Application::InventoryItemValueNameAppType;
    if ( (unsigned __int64)qword_18011B648 > 7 )
      v49 = (__int64 *)Application::InventoryItemValueNameAppType;
    v50 = v47(a2, v49, v48);
    if ( v50 < 0 )
    {
      v51 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v52 = 2058;
LABEL_91:
      LODWORD(v146) = v50;
      AslLogCallPrintf(1, "Application::Insert", v52, v51, v146);
    }
  }
  else
  {
    v53 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 72LL))(v2);
    if ( (unsigned __int8)std::operator!=<unsigned short>(v53, Application::ApplicationTypeApplication) )
    {
      v54 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
      v55 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 72LL))(v2);
      if ( v55[3] > 7u )
        v55 = (_QWORD *)*v55;
      v56 = &Application::InventoryItemValueNameAppType;
      if ( (unsigned __int64)qword_18011B648 > 7 )
        v56 = (__int64 *)Application::InventoryItemValueNameAppType;
      v50 = v54(a2, v56, v55);
      if ( v50 < 0 )
      {
        v51 = "TelCacheProvider::SetItemProperty failed [#%x]";
        v52 = 2069;
        goto LABEL_91;
      }
    }
  }
  v57 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v58 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 40LL))(v2);
  if ( v58[3] > 7u )
    v58 = (_QWORD *)*v58;
  v59 = &Application::InventoryItemValueNameRootDirPath;
  if ( (unsigned __int64)qword_18011B5C8 > 7 )
    v59 = (__int64 *)Application::InventoryItemValueNameRootDirPath;
  v60 = v57(a2, v59, v58);
  if ( v60 < 0 )
  {
    LODWORD(v146) = v60;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 2079, "TelCacheProvider::SetItemProperty failed [%#x]", v146);
    else
      AslLogCallPrintf(1, "Application::Insert", 2083, "TelCacheProvider::SetItemProperty failed [#%x]", v146);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v61 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_18011B628 > 7 )
      v61 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
    v62 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
            a2,
            v61,
            *((unsigned __int8 *)this + 88));
    if ( v62 < 0 )
    {
      v63 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v64 = 2092;
LABEL_110:
      LODWORD(v146) = v62;
      AslLogCallPrintf(1, "Application::Insert", v64, v63, v146);
    }
  }
  else if ( *((_BYTE *)this + 88) )
  {
    v65 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_18011B628 > 7 )
      v65 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
    v62 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
            a2,
            v65,
            *((unsigned __int8 *)this + 88));
    if ( v62 < 0 )
    {
      v63 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v64 = 2103;
      goto LABEL_110;
    }
  }
  v66 = (_QWORD *)((char *)this + 304);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( *((_QWORD *)this + 41) > 7u )
      v66 = (_QWORD *)*v66;
    v67 = &Application::InventoryItemValueNameUserSid;
    if ( (unsigned __int64)qword_18011B668 > 7 )
      v67 = (__int64 *)Application::InventoryItemValueNameUserSid;
    v68 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v67,
            v66);
    if ( v68 < 0 )
    {
      v69 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v70 = 2113;
LABEL_125:
      LODWORD(v146) = v68;
      AslLogCallPrintf(1, "Application::Insert", v70, v69, v146);
    }
  }
  else if ( *((_QWORD *)this + 40) )
  {
    if ( *((_QWORD *)this + 41) > 7u )
      v66 = (_QWORD *)*v66;
    v71 = &Application::InventoryItemValueNameUserSid;
    if ( (unsigned __int64)qword_18011B668 > 7 )
      v71 = (__int64 *)Application::InventoryItemValueNameUserSid;
    v68 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v71,
            v66);
    if ( v68 < 0 )
    {
      v69 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v70 = 2123;
      goto LABEL_125;
    }
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v72 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_18011B488 > 7 )
      v72 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v73 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v72);
    if ( v73 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2133, "TelCacheProvider::SetItemProperty failed [%#x]", v73);
    v74 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_18011B528 > 7 )
      v74 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    v75 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
            a2,
            v74,
            *((unsigned __int8 *)this + 968));
    if ( v75 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2139, "TelCacheProvider::SetItemProperty failed [%#x]", v75);
    v76 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_18011B588 > 7 )
      v76 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v77 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v76);
    if ( v77 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2145, "TelCacheProvider::SetItemProperty failed [%#x]", v77);
    v78 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_18011B5A8 > 7 )
      v78 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v79 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v78);
    if ( v79 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2152, "TelCacheProvider::SetItemProperty failed [%#x]", v79);
    v80 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_18011B568 > 7 )
      v80 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v81 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v80);
    if ( v81 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2158, "TelCacheProvider::SetItemProperty failed [%#x]", v81);
    v82 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_18011B508 > 7 )
      v82 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
    v83 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
            a2,
            v82,
            *((unsigned __int8 *)this + 700));
    if ( v83 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2164, "TelCacheProvider::SetItemProperty failed [%#x]", v83);
    v84 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v85 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 48LL))(v2);
    if ( v85[3] > 7u )
      v85 = (_QWORD *)*v85;
    v86 = &Application::InventoryItemValueNameUninstallString;
    if ( (unsigned __int64)qword_18011B5E8 > 7 )
      v86 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    v87 = v84(a2, v86, v85);
    if ( v87 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2170, "TelCacheProvider::SetItemProperty failed [%#x]", v87);
    v88 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v89 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 88LL))(v2);
    if ( v89[3] > 7u )
      v89 = (_QWORD *)*v89;
    v90 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_18011B608 > 7 )
      v90 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    v91 = v88(a2, v90, v89);
    if ( v91 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2177, "TelCacheProvider::SetItemProperty failed [%#x]", v91);
    v92 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v93 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 104LL))(v2);
    if ( v93[3] > 7u )
      v93 = (_QWORD *)*v93;
    v94 = &Application::InventoryItemValueNameMsiPackageCode;
    if ( (unsigned __int64)qword_18011B4C8 > 7 )
      v94 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
    v95 = v92(a2, v94, v93);
    if ( v95 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2183, "TelCacheProvider::SetItemProperty failed [%#x]", v95);
    v96 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v97 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 96LL))(v2);
    if ( v97[3] > 7u )
      v97 = (_QWORD *)*v97;
    v98 = &Application::InventoryItemValueNameMsiProductCode;
    if ( (unsigned __int64)qword_18011B4A8 > 7 )
      v98 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
    v99 = v96(a2, v98, v97);
    if ( v99 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2189, "TelCacheProvider::SetItemProperty failed [%#x]", v99);
    v100 = &Application::InventoryItemValueNameMsiInstallDate;
    if ( (unsigned __int64)qword_18011B4E8 > 7 )
      v100 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
    v101 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
             a2,
             v100);
    if ( v101 < 0 )
    {
      v102 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v103 = 2195;
LABEL_263:
      LODWORD(v146) = v101;
      AslLogCallPrintf(1, "Application::Insert", v103, v102, v146);
    }
  }
  else
  {
    v104 = (const wchar_t *)((char *)this + 336);
    v105 = *((_QWORD *)this + 44);
    if ( !v105 )
      goto LABEL_186;
    v106 = (const wchar_t *)&Application::ApplicationSourceAppxPackage;
    v107 = (const wchar_t *)((char *)this + 336);
    if ( (unsigned __int64)qword_18011B0A8 > 7 )
      v106 = Application::ApplicationSourceAppxPackage;
    if ( *((_QWORD *)this + 45) > 7u )
      v107 = *(const wchar_t **)v104;
    if ( v105 == qword_18011B0A0 && !wmemcmp(v107, v106, v105) )
    {
LABEL_186:
      v108 = &Application::InventoryItemValueNameStoreAppType;
      if ( (unsigned __int64)qword_18011B488 > 7 )
        v108 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
      v109 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v108);
      if ( v109 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2206, "TelCacheProvider::SetItemProperty failed [#%x]", v109);
      v110 = &Application::InventoryItemValueNameInboxStoreApp;
      if ( (unsigned __int64)qword_18011B528 > 7 )
        v110 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
      v111 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
               a2,
               v110,
               *((unsigned __int8 *)this + 968));
      if ( v111 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2212, "TelCacheProvider::SetItemProperty failed [#%x]", v111);
      v112 = &Application::InventoryItemValueNameManifestPath;
      if ( (unsigned __int64)qword_18011B588 > 7 )
        v112 = (__int64 *)Application::InventoryItemValueNameManifestPath;
      v113 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v112);
      if ( v113 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2219, "TelCacheProvider::SetItemProperty failed [#%x]", v113);
      if ( *((_QWORD *)this + 119) )
      {
        v114 = &Application::InventoryItemValueNameBundleManifestPath;
        if ( (unsigned __int64)qword_18011B5A8 > 7 )
          v114 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
        v115 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
                 a2,
                 v114);
        if ( v115 < 0 )
          AslLogCallPrintf(1, "Application::Insert", 2229, "TelCacheProvider::SetItemProperty failed [#%x]", v115);
      }
    }
    v116 = *((_QWORD *)this + 44);
    if ( !v116 )
      goto LABEL_218;
    v117 = (const wchar_t *)&Application::ApplicationSourceAppxPackage;
    v118 = (const wchar_t *)((char *)this + 336);
    if ( (unsigned __int64)qword_18011B0A8 > 7 )
      v117 = Application::ApplicationSourceAppxPackage;
    if ( *((_QWORD *)this + 45) > 7u )
      v118 = *(const wchar_t **)v104;
    if ( v116 == qword_18011B0A0 && !wmemcmp(v118, v117, v116) )
      goto LABEL_218;
    v119 = (const wchar_t *)&Application::ApplicationSourceAppvPackage;
    v120 = *((_QWORD *)this + 44);
    if ( (unsigned __int64)qword_18011B088 > 7 )
      v119 = Application::ApplicationSourceAppvPackage;
    v121 = *((_QWORD *)this + 45) <= 7u ? (const wchar_t *)((char *)this + 336) : *(const wchar_t **)v104;
    if ( v120 == qword_18011B080 && (!v120 || !wmemcmp(v121, v119, v120)) )
    {
LABEL_218:
      v122 = &Application::InventoryItemValueNamePackageFullName;
      if ( (unsigned __int64)qword_18011B568 > 7 )
        v122 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
      v123 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v122);
      if ( v123 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2241, "TelCacheProvider::SetItemProperty failed [#%x]", v123);
    }
    if ( (unsigned __int8)std::operator!=<unsigned short>(
                            (char *)this + 336,
                            &Application::ApplicationSourceAppxPackage)
      && (unsigned __int8)std::operator!=<unsigned short>(
                            (char *)this + 336,
                            &Application::ApplicationSourceAppvPackage) )
    {
      v124 = &Application::InventoryItemValueNameHiddenArp;
      if ( (unsigned __int64)qword_18011B508 > 7 )
        v124 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
      v125 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
               a2,
               v124,
               *((unsigned __int8 *)this + 700));
      if ( v125 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2251, "TelCacheProvider::SetItemProperty failed [#%x]", v125);
      v126 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
      v127 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 48LL))(v2);
      if ( v127[3] > 7u )
        v127 = (_QWORD *)*v127;
      v128 = &Application::InventoryItemValueNameUninstallString;
      if ( (unsigned __int64)qword_18011B5E8 > 7 )
        v128 = (__int64 *)Application::InventoryItemValueNameUninstallString;
      v129 = v126(a2, v128, v127);
      if ( v129 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2258, "TelCacheProvider::SetItemProperty failed [#%x]", v129);
      v130 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
      v131 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 88LL))(v2);
      if ( v131[3] > 7u )
        v131 = (_QWORD *)*v131;
      v132 = &Application::InventoryItemValueNameArpRegistryKeyPath;
      if ( (unsigned __int64)qword_18011B608 > 7 )
        v132 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
      v133 = v130(a2, v132, v131);
      if ( v133 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2265, "TelCacheProvider::SetItemProperty failed [#%x]", v133);
      v134 = (const wchar_t *)&Application::ApplicationSourceMsi;
      v135 = *((_QWORD *)this + 44);
      if ( (unsigned __int64)qword_18011AF68 > 7 )
        v134 = Application::ApplicationSourceMsi;
      if ( *((_QWORD *)this + 45) > 7u )
        v104 = *(const wchar_t **)v104;
      if ( v135 == qword_18011AF60 && (!v135 || !wmemcmp(v104, v134, v135)) )
      {
        v136 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
        v137 = (_QWORD *)(*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v2 + 104LL))(v2, v134);
        if ( v137[3] > 7u )
          v137 = (_QWORD *)*v137;
        v138 = &Application::InventoryItemValueNameMsiPackageCode;
        if ( (unsigned __int64)qword_18011B4C8 > 7 )
          v138 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
        v139 = v136(a2, v138, v137);
        if ( v139 < 0 )
          AslLogCallPrintf(1, "Application::Insert", 2275, "TelCacheProvider::SetItemProperty failed [#%x]", v139);
        v140 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
        v141 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 96LL))(v2);
        if ( v141[3] > 7u )
          v141 = (_QWORD *)*v141;
        v142 = &Application::InventoryItemValueNameMsiProductCode;
        if ( (unsigned __int64)qword_18011B4A8 > 7 )
          v142 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
        v143 = v140(a2, v142, v141);
        if ( v143 < 0 )
          AslLogCallPrintf(1, "Application::Insert", 2282, "TelCacheProvider::SetItemProperty failed [#%x]", v143);
        v144 = &Application::InventoryItemValueNameMsiInstallDate;
        if ( (unsigned __int64)qword_18011B4E8 > 7 )
          v144 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
        v101 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
                 a2,
                 v144);
        if ( v101 < 0 )
        {
          v102 = "TelCacheProvider::SetItemProperty failed [#%x]";
          v103 = 2289;
          goto LABEL_263;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003a720  push    rbx
0x18003a722  push    rbp
0x18003a723  push    rsi
0x18003a724  push    rdi
0x18003a725  push    r13
0x18003a727  push    r14
0x18003a729  push    r15
0x18003a72b  sub     rsp, 30h
0x18003a72f  mov     rax, [rdx]
0x18003a732  lea     rsi, [rcx+10h]
0x18003a736  mov     rbp, rcx
0x18003a739  mov     rdi, rdx
0x18003a73c  mov     rcx, rsi
0x18003a73f  mov     rbx, [rax+88h]
0x18003a746  mov     rax, [rsi]
0x18003a749  mov     rax, [rax+10h]
0x18003a74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a752  mov     r15d, 7
0x18003a758  cmp     [rax+18h], r15
0x18003a75c  jbe     short loc_18003A761
0x18003a75e  mov     rax, [rax]
0x18003a761  cmp     cs:qword_18011B3A8, r15
0x18003a768  lea     rdx, ?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x18003a76f  mov     r8, rax
0x18003a772  mov     rcx, rdi
0x18003a775  cmova   rdx, cs:?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x18003a77d  mov     rax, rbx
0x18003a780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a785  lea     r13, aApplicationIns; "Application::Insert"
0x18003a78c  mov     ebx, eax
0x18003a78e  mov     r14d, 1
0x18003a794  test    eax, eax
0x18003a796  jns     short loc_18003A7D3
0x18003a798  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003a79f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003a7a4  mov     dword ptr [rsp+68h+var_48], ebx
0x18003a7a8  mov     rdx, r13
0x18003a7ab  mov     ecx, r14d
0x18003a7ae  test    al, al
0x18003a7b0  jz      short loc_18003A7C1
0x18003a7b2  lea     r9, aTelcacheprovid_25; "TelCacheProvider::SetItemProperty faile"...
0x18003a7b9  mov     r8d, 790h
0x18003a7bf  jmp     short loc_18003A7CE
0x18003a7c1  lea     r9, aTelcacheprovid_7; "TelCacheProvider::SetItemProperty faile"...
0x18003a7c8  mov     r8d, 794h
0x18003a7ce  call    AslLogCallPrintf
0x18003a7d3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003a7da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003a7df  mov     rcx, rsi
0x18003a7e2  test    al, al
0x18003a7e4  jz      short loc_18003A840
0x18003a7e6  mov     rax, [rdi]
0x18003a7e9  mov     rbx, [rax+88h]
0x18003a7f0  mov     rax, [rsi]
0x18003a7f3  mov     rax, [rax+50h]
0x18003a7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7fc  cmp     [rax+18h], r15
0x18003a800  jbe     short loc_18003A805
0x18003a802  mov     rax, [rax]
0x18003a805  cmp     cs:qword_18011B3C8, r15
0x18003a80c  lea     rdx, ?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x18003a813  mov     r8, rax
0x18003a816  mov     rcx, rdi
0x18003a819  cmova   rdx, cs:?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x18003a821  mov     rax, rbx
0x18003a824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a829  test    eax, eax
0x18003a82b  jns     loc_18003A8B9
0x18003a831  lea     r9, aTelcacheprovid_25; "TelCacheProvider::SetItemProperty faile"...
0x18003a838  mov     r8d, 79Eh
0x18003a83e  jmp     short loc_18003A8AA
0x18003a840  mov     rax, [rsi]
0x18003a843  mov     rax, [rax+50h]
0x18003a847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a84c  cmp     qword ptr [rax+10h], 0
0x18003a851  jz      short loc_18003A8B9
0x18003a853  mov     rax, [rdi]
0x18003a856  mov     rcx, rsi
0x18003a859  mov     rbx, [rax+88h]
0x18003a860  mov     rax, [rsi]
0x18003a863  mov     rax, [rax+50h]
0x18003a867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a86c  cmp     [rax+18h], r15
0x18003a870  jbe     short loc_18003A875
0x18003a872  mov     rax, [rax]
0x18003a875  cmp     cs:qword_18011B3C8, r15
0x18003a87c  lea     rdx, ?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x18003a883  mov     r8, rax
0x18003a886  mov     rcx, rdi
0x18003a889  cmova   rdx, cs:?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x18003a891  mov     rax, rbx
0x18003a894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a899  test    eax, eax
0x18003a89b  jns     short loc_18003A8B9
0x18003a89d  lea     r9, aTelcacheprovid_7; "TelCacheProvider::SetItemProperty faile"...
0x18003a8a4  mov     r8d, 7AAh
0x18003a8aa  mov     rdx, r13
0x18003a8ad  mov     dword ptr [rsp+68h+var_48], eax
0x18003a8b1  mov     ecx, r14d
0x18003a8b4  call    AslLogCallPrintf
0x18003a8b9  mov     rax, [rdi]
0x18003a8bc  mov     rcx, rsi
0x18003a8bf  mov     rbx, [rax+88h]
0x18003a8c6  mov     rax, [rsi]
0x18003a8c9  mov     rax, [rax+8]
0x18003a8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8d2  cmp     [rax+18h], r15
0x18003a8d6  jbe     short loc_18003A8DB
0x18003a8d8  mov     rax, [rax]
0x18003a8db  cmp     cs:qword_18011B3E8, r15
0x18003a8e2  lea     rdx, ?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x18003a8e9  mov     r8, rax
0x18003a8ec  mov     rcx, rdi
0x18003a8ef  cmova   rdx, cs:?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x18003a8f7  mov     rax, rbx
0x18003a8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8ff  mov     ebx, eax
0x18003a901  test    eax, eax
0x18003a903  jns     short loc_18003A940
0x18003a905  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003a90c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003a911  mov     dword ptr [rsp+68h+var_48], ebx
0x18003a915  mov     rdx, r13
0x18003a918  mov     ecx, r14d
0x18003a91b  test    al, al
0x18003a91d  jz      short loc_18003A92E
0x18003a91f  lea     r9, aTelcacheprovid_25; "TelCacheProvider::SetItemProperty faile"...
0x18003a926  mov     r8d, 7B4h
0x18003a92c  jmp     short loc_18003A93B
0x18003a92e  lea     r9, aTelcacheprovid_7; "TelCacheProvider::SetItemProperty faile"...
0x18003a935  mov     r8d, 7B8h
0x18003a93b  call    AslLogCallPrintf
0x18003a940  mov     rax, [rdi]
0x18003a943  mov     rcx, rsi
0x18003a946  mov     rbx, [rax+88h]
0x18003a94d  mov     rax, [rsi]
0x18003a950  mov     rax, [rax+20h]
0x18003a954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a959  cmp     [rax+18h], r15
0x18003a95d  jbe     short loc_18003A962
0x18003a95f  mov     rax, [rax]
0x18003a962  cmp     cs:qword_18011B408, r15
0x18003a969  lea     rdx, ?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x18003a970  mov     r8, rax
0x18003a973  mov     rcx, rdi
0x18003a976  cmova   rdx, cs:?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x18003a97e  mov     rax, rbx
0x18003a981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a986  mov     ebx, eax
0x18003a988  test    eax, eax
0x18003a98a  jns     short loc_18003A9C7
0x18003a98c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003a993  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003a998  mov     dword ptr [rsp+68h+var_48], ebx
0x18003a99c  mov     rdx, r13
0x18003a99f  mov     ecx, r14d
0x18003a9a2  test    al, al
0x18003a9a4  jz      short loc_18003A9B5
0x18003a9a6  lea     r9, aTelcacheprovid_25; "TelCacheProvider::SetItemProperty faile"...
0x18003a9ad  mov     r8d, 7C1h
0x18003a9b3  jmp     short loc_18003A9C2
0x18003a9b5  lea     r9, aTelcacheprovid_7; "TelCacheProvider::SetItemProperty faile"...
0x18003a9bc  mov     r8d, 7C5h
0x18003a9c2  call    AslLogCallPrintf
0x18003a9c7  mov     rax, [rdi]
0x18003a9ca  mov     rcx, rsi
0x18003a9cd  mov     rbx, [rax+88h]
0x18003a9d4  mov     rax, [rsi]
0x18003a9d7  mov     rax, [rax+18h]
0x18003a9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9e0  cmp     [rax+18h], r15
0x18003a9e4  jbe     short loc_18003A9E9
0x18003a9e6  mov     rax, [rax]
0x18003a9e9  cmp     cs:qword_18011B428, r15
0x18003a9f0  lea     rdx, ?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x18003a9f7  mov     r8, rax
0x18003a9fa  mov     rcx, rdi
0x18003a9fd  cmova   rdx, cs:?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x18003aa05  mov     rax, rbx
0x18003aa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa0d  mov     ebx, eax
0x18003aa0f  test    eax, eax
0x18003aa11  jns     short loc_18003AA4E
0x18003aa13  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003aa1a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003aa1f  mov     dword ptr [rsp+68h+var_48], ebx
0x18003aa23  mov     rdx, r13
0x18003aa26  mov     ecx, r14d
0x18003aa29  test    al, al
0x18003aa2b  jz      short loc_18003AA3C
0x18003aa2d  lea     r9, aTelcacheprovid_25; "TelCacheProvider::SetItemProperty faile"...
0x18003aa34  mov     r8d, 7CEh
0x18003aa3a  jmp     short loc_18003AA49
0x18003aa3c  lea     r9, aTelcacheprovid_7; "TelCacheProvider::SetItemProperty faile"...
0x18003aa43  mov     r8d, 7D2h
0x18003aa49  call    AslLogCallPrintf
0x18003aa4e  mov     rax, [rdi]
0x18003aa51  mov     rcx, rsi
0x18003aa54  mov     rbx, [rax+98h]
0x18003aa5b  mov     rax, [rsi]
0x18003aa5e  mov     rax, [rax+78h]
0x18003aa62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa67  cmp     cs:qword_18011B448, r15
0x18003aa6e  lea     rdx, ?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x18003aa75  mov     r8d, eax
0x18003aa78  mov     rcx, rdi
0x18003aa7b  cmova   rdx, cs:?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x18003aa83  mov     rax, rbx
0x18003aa86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa8b  mov     ebx, eax
0x18003aa8d  test    eax, eax
0x18003aa8f  jns     short loc_18003AACC
0x18003aa91  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003aa98  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003aa9d  mov     dword ptr [rsp+68h+var_48], ebx
0x18003aaa1  mov     rdx, r13
0x18003aaa4  mov     ecx, r14d
0x18003aaa7  test    al, al
0x18003aaa9  jz      short loc_18003AABA
0x18003aaab  lea     r9, aTelcacheprovid_25; "TelCacheProvider::SetItemProperty faile"...
0x18003aab2  mov     r8d, 7DBh
0x18003aab8  jmp     short loc_18003AAC7
0x18003aaba  lea     r9, aTelcacheprovid_7; "TelCacheProvider::SetItemProperty faile"...
0x18003aac1  mov     r8d, 7DFh
0x18003aac7  call    AslLogCallPrintf
0x18003aacc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003aad3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003aad8  mov     rcx, rsi
0x18003aadb  test    al, al
0x18003aadd  jz      short loc_18003AB39
0x18003aadf  mov     rax, [rdi]
0x18003aae2  mov     rbx, [rax+88h]
0x18003aae9  mov     rax, [rsi]
0x18003aaec  mov     rax, [rax+38h]
0x18003aaf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aaf5  cmp     [rax+18h], r15
0x18003aaf9  jbe     short loc_18003AAFE
0x18003aafb  mov     rax, [rax]
0x18003aafe  cmp     cs:qword_18011B548, r15
0x18003ab05  lea     rdx, ?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x18003ab0c  mov     r8, rax
0x18003ab0f  mov     rcx, rdi
0x18003ab12  cmova   rdx, cs:?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x18003ab1a  mov     rax, rbx
0x18003ab1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab22  test    eax, eax
0x18003ab24  jns     loc_18003ABB2
0x18003ab2a  lea     r9, aTelcacheprovid_25; "TelCacheProvider::SetItemProperty faile"...
0x18003ab31  mov     r8d, 7E8h
0x18003ab37  jmp     short loc_18003ABA3
0x18003ab39  mov     rax, [rsi]
0x18003ab3c  mov     rax, [rax+38h]
0x18003ab40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab45  cmp     qword ptr [rax+10h], 0
0x18003ab4a  jz      short loc_18003ABB2
0x18003ab4c  mov     rax, [rdi]
0x18003ab4f  mov     rcx, rsi
0x18003ab52  mov     rbx, [rax+88h]
0x18003ab59  mov     rax, [rsi]
0x18003ab5c  mov     rax, [rax+38h]
0x18003ab60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab65  cmp     [rax+18h], r15
0x18003ab69  jbe     short loc_18003AB6E
0x18003ab6b  mov     rax, [rax]
0x18003ab6e  cmp     cs:qword_18011B548, r15
0x18003ab75  lea     rdx, ?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x18003ab7c  mov     r8, rax
0x18003ab7f  mov     rcx, rdi
0x18003ab82  cmova   rdx, cs:?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x18003ab8a  mov     rax, rbx
0x18003ab8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab92  test    eax, eax
0x18003ab94  jns     short loc_18003ABB2
0x18003ab96  lea     r9, aTelcacheprovid_7; "TelCacheProvider::SetItemProperty faile"...
0x18003ab9d  mov     r8d, 7F3h
0x18003aba3  mov     rdx, r13
0x18003aba6  mov     dword ptr [rsp+68h+var_48], eax
0x18003abaa  mov     ecx, r14d
0x18003abad  call    AslLogCallPrintf
0x18003abb2  mov     rax, [rdi]
0x18003abb5  mov     rcx, rsi
0x18003abb8  mov     rbx, [rax+88h]
0x18003abbf  mov     rax, [rsi]
0x18003abc2  mov     rax, [rax+40h]
0x18003abc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abcb  cmp     [rax+18h], r15
0x18003abcf  jbe     short loc_18003ABD4
0x18003abd1  mov     rax, [rax]
0x18003abd4  cmp     cs:qword_18011B468, r15
0x18003abdb  lea     rdx, ?InventoryItemValueNameSource@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameSource
0x18003abe2  mov     r8, rax
0x18003abe5  mov     rcx, rdi
0x18003abe8  cmova   rdx, cs:?InventoryItemValueNameSource@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameSource
0x18003abf0  mov     rax, rbx
0x18003abf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abf8  mov     ebx, eax
0x18003abfa  test    eax, eax
0x18003abfc  jns     short loc_18003AC39
0x18003abfe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003ac05  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
  ... truncated ...
```
