# Application::Insert(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x1800d1bb0`
- end: `0x1800d2cc5`
- name: `?Insert@Application@@UEAAKPEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `4373`
- prototype: `unsigned int __fastcall(Application *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d914`
- `0x18001de0c`
- `0x1800295dc`
- `0x1800c1a1c`
- `0x1800d1bb0`
- `0x1800eb010`

## string_xrefs

- `0x1800d1c42`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d1cc1`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d1daf`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d1e36`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d1ebd`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d1f3b`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d1fba`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d20a8`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d2127`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d2221`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d2280`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d232e`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d23e8`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d2435`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d248d`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d24e5`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d253d`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d258a`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d25f0`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d2656`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d26bc`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d2722`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d277e`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800d1c51`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d1d2d`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d1dbe`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d1e45`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d1ecc`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d1f4a`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2026`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d20b7`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d219f`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2230`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d22c3`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d237c`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2814`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2861`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d28b9`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d291b`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d29eb`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2a66`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2acc`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2b3a`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2bda`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2c40`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800d2c98`: `TelCacheProvider::SetItemProperty failed [#%x]`

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
  _QWORD *v104; // rbx
  __int64 v105; // rdx
  __int64 *v106; // r8
  Application *v107; // rcx
  __int64 *v108; // rdx
  int v109; // eax
  __int64 *v110; // rdx
  int v111; // eax
  __int64 *v112; // rdx
  int v113; // eax
  __int64 *v114; // rdx
  int v115; // eax
  __int64 v116; // rdx
  __int64 *v117; // r8
  Application *v118; // rcx
  __int64 *v119; // r8
  Application *v120; // rcx
  __int64 *v121; // rdx
  int v122; // eax
  __int64 *v123; // rdx
  int v124; // eax
  __int64 (__fastcall *v125)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // r14
  _QWORD *v126; // rax
  __int64 *v127; // rdx
  int v128; // eax
  __int64 (__fastcall *v129)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // r14
  _QWORD *v130; // rax
  __int64 *v131; // rdx
  int v132; // eax
  __int64 *v133; // r8
  __int64 (__fastcall *v134)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v135; // rax
  __int64 *v136; // rdx
  int v137; // eax
  __int64 (__fastcall *v138)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v139; // rax
  __int64 *v140; // rdx
  int v141; // eax
  __int64 *v142; // rdx
  __int64 v144; // [rsp+20h] [rbp-48h]

  v2 = (char *)this + 16;
  v5 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v6 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  v7 = &Application::InventoryItemValueNameProgramId;
  if ( (unsigned __int64)qword_1801222E8 > 7 )
    v7 = (__int64 *)Application::InventoryItemValueNameProgramId;
  v8 = v5(a2, v7, v6);
  if ( v8 < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 1936, "TelCacheProvider::SetItemProperty failed [%#x]", v8);
    else
      AslLogCallPrintf(1, "Application::Insert", 1940, "TelCacheProvider::SetItemProperty failed [#%x]", v8);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v9 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v10 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 80LL))(v2);
    if ( v10[3] > 7u )
      v10 = (_QWORD *)*v10;
    v11 = &Application::InventoryItemValueNameProgramInstanceId;
    if ( (unsigned __int64)qword_180122308 > 7 )
      v11 = (__int64 *)Application::InventoryItemValueNameProgramInstanceId;
    v12 = v9(a2, v11, v10);
    if ( v12 < 0 )
    {
      v13 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v14 = 1950;
LABEL_23:
      LODWORD(v144) = v12;
      AslLogCallPrintf(1, "Application::Insert", v14, v13, v144);
    }
  }
  else if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 80LL))(v2) + 16) )
  {
    v15 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v16 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 80LL))(v2);
    if ( v16[3] > 7u )
      v16 = (_QWORD *)*v16;
    v17 = &Application::InventoryItemValueNameProgramInstanceId;
    if ( (unsigned __int64)qword_180122308 > 7 )
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
  if ( (unsigned __int64)qword_180122328 > 7 )
    v20 = (__int64 *)Application::InventoryItemValueNameName;
  v21 = v18(a2, v20, v19);
  if ( v21 < 0 )
  {
    LODWORD(v144) = v21;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 1972, "TelCacheProvider::SetItemProperty failed [%#x]", v144);
    else
      AslLogCallPrintf(1, "Application::Insert", 1976, "TelCacheProvider::SetItemProperty failed [#%x]", v144);
  }
  v22 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v23 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 32LL))(v2);
  if ( v23[3] > 7u )
    v23 = (_QWORD *)*v23;
  v24 = &Application::InventoryItemValueNameVersion;
  if ( (unsigned __int64)qword_180122348 > 7 )
    v24 = (__int64 *)Application::InventoryItemValueNameVersion;
  v25 = v22(a2, v24, v23);
  if ( v25 < 0 )
  {
    LODWORD(v144) = v25;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 1985, "TelCacheProvider::SetItemProperty failed [%#x]", v144);
    else
      AslLogCallPrintf(1, "Application::Insert", 1989, "TelCacheProvider::SetItemProperty failed [#%x]", v144);
  }
  v26 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v27 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 24LL))(v2);
  if ( v27[3] > 7u )
    v27 = (_QWORD *)*v27;
  v28 = &Application::InventoryItemValueNamePublisher;
  if ( (unsigned __int64)qword_180122368 > 7 )
    v28 = (__int64 *)Application::InventoryItemValueNamePublisher;
  v29 = v26(a2, v28, v27);
  if ( v29 < 0 )
  {
    LODWORD(v144) = v29;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 1998, "TelCacheProvider::SetItemProperty failed [%#x]", v144);
    else
      AslLogCallPrintf(1, "Application::Insert", 2002, "TelCacheProvider::SetItemProperty failed [#%x]", v144);
  }
  v30 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 152LL);
  v31 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 120LL))(v2);
  v32 = &Application::InventoryItemValueNameLanguage;
  if ( (unsigned __int64)qword_180122388 > 7 )
    v32 = (__int64 *)Application::InventoryItemValueNameLanguage;
  v33 = v30(a2, v32, v31);
  if ( v33 < 0 )
  {
    LODWORD(v144) = v33;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 2011, "TelCacheProvider::SetItemProperty failed [%#x]", v144);
    else
      AslLogCallPrintf(1, "Application::Insert", 2015, "TelCacheProvider::SetItemProperty failed [#%x]", v144);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v34 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v35 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 56LL))(v2);
    if ( v35[3] > 7u )
      v35 = (_QWORD *)*v35;
    v36 = &Application::InventoryItemValueNameInstallDate;
    if ( (unsigned __int64)qword_180122488 > 7 )
      v36 = (__int64 *)Application::InventoryItemValueNameInstallDate;
    v37 = v34(a2, v36, v35);
    if ( v37 < 0 )
    {
      v38 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v39 = 2024;
LABEL_68:
      LODWORD(v144) = v37;
      AslLogCallPrintf(1, "Application::Insert", v39, v38, v144);
    }
  }
  else if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 56LL))(v2) + 16) )
  {
    v40 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v41 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 56LL))(v2);
    if ( v41[3] > 7u )
      v41 = (_QWORD *)*v41;
    v42 = &Application::InventoryItemValueNameInstallDate;
    if ( (unsigned __int64)qword_180122488 > 7 )
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
  if ( (unsigned __int64)qword_1801223A8 > 7 )
    v45 = (__int64 *)Application::InventoryItemValueNameSource;
  v46 = v43(a2, v45, v44);
  if ( v46 < 0 )
  {
    LODWORD(v144) = v46;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 2045, "TelCacheProvider::SetItemProperty failed [%#x]", v144);
    else
      AslLogCallPrintf(1, "Application::Insert", 2049, "TelCacheProvider::SetItemProperty failed [#%x]", v144);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v47 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v48 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 72LL))(v2);
    if ( v48[3] > 7u )
      v48 = (_QWORD *)*v48;
    v49 = &Application::InventoryItemValueNameAppType;
    if ( (unsigned __int64)qword_180122588 > 7 )
      v49 = (__int64 *)Application::InventoryItemValueNameAppType;
    v50 = v47(a2, v49, v48);
    if ( v50 < 0 )
    {
      v51 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v52 = 2058;
LABEL_91:
      LODWORD(v144) = v50;
      AslLogCallPrintf(1, "Application::Insert", v52, v51, v144);
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
      if ( (unsigned __int64)qword_180122588 > 7 )
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
  if ( (unsigned __int64)qword_180122508 > 7 )
    v59 = (__int64 *)Application::InventoryItemValueNameRootDirPath;
  v60 = v57(a2, v59, v58);
  if ( v60 < 0 )
  {
    LODWORD(v144) = v60;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      AslLogCallPrintf(1, "Application::Insert", 2079, "TelCacheProvider::SetItemProperty failed [%#x]", v144);
    else
      AslLogCallPrintf(1, "Application::Insert", 2083, "TelCacheProvider::SetItemProperty failed [#%x]", v144);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v61 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_180122568 > 7 )
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
      LODWORD(v144) = v62;
      AslLogCallPrintf(1, "Application::Insert", v64, v63, v144);
    }
  }
  else if ( *((_BYTE *)this + 88) )
  {
    v65 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_180122568 > 7 )
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( *((_QWORD *)this + 41) > 7u )
      v66 = (_QWORD *)*v66;
    v67 = &Application::InventoryItemValueNameUserSid;
    if ( (unsigned __int64)qword_1801225A8 > 7 )
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
      LODWORD(v144) = v68;
      AslLogCallPrintf(1, "Application::Insert", v70, v69, v144);
    }
  }
  else if ( *((_QWORD *)this + 40) )
  {
    if ( *((_QWORD *)this + 41) > 7u )
      v66 = (_QWORD *)*v66;
    v71 = &Application::InventoryItemValueNameUserSid;
    if ( (unsigned __int64)qword_1801225A8 > 7 )
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v72 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_1801223C8 > 7 )
      v72 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v73 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v72);
    if ( v73 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2133, "TelCacheProvider::SetItemProperty failed [%#x]", v73);
    v74 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_180122468 > 7 )
      v74 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    v75 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
            a2,
            v74,
            *((unsigned __int8 *)this + 968));
    if ( v75 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2139, "TelCacheProvider::SetItemProperty failed [%#x]", v75);
    v76 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_1801224C8 > 7 )
      v76 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v77 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v76);
    if ( v77 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2145, "TelCacheProvider::SetItemProperty failed [%#x]", v77);
    v78 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_1801224E8 > 7 )
      v78 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v79 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v78);
    if ( v79 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2152, "TelCacheProvider::SetItemProperty failed [%#x]", v79);
    v80 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_1801224A8 > 7 )
      v80 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v81 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v80);
    if ( v81 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2158, "TelCacheProvider::SetItemProperty failed [%#x]", v81);
    v82 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_180122448 > 7 )
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
    if ( (unsigned __int64)qword_180122528 > 7 )
      v86 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    v87 = v84(a2, v86, v85);
    if ( v87 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2170, "TelCacheProvider::SetItemProperty failed [%#x]", v87);
    v88 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v89 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 88LL))(v2);
    if ( v89[3] > 7u )
      v89 = (_QWORD *)*v89;
    v90 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_180122548 > 7 )
      v90 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    v91 = v88(a2, v90, v89);
    if ( v91 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2177, "TelCacheProvider::SetItemProperty failed [%#x]", v91);
    v92 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v93 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 104LL))(v2);
    if ( v93[3] > 7u )
      v93 = (_QWORD *)*v93;
    v94 = &Application::InventoryItemValueNameMsiPackageCode;
    if ( (unsigned __int64)qword_180122408 > 7 )
      v94 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
    v95 = v92(a2, v94, v93);
    if ( v95 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2183, "TelCacheProvider::SetItemProperty failed [%#x]", v95);
    v96 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v97 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 96LL))(v2);
    if ( v97[3] > 7u )
      v97 = (_QWORD *)*v97;
    v98 = &Application::InventoryItemValueNameMsiProductCode;
    if ( (unsigned __int64)qword_1801223E8 > 7 )
      v98 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
    v99 = v96(a2, v98, v97);
    if ( v99 < 0 )
      AslLogCallPrintf(1, "Application::Insert", 2189, "TelCacheProvider::SetItemProperty failed [%#x]", v99);
    v100 = &Application::InventoryItemValueNameMsiInstallDate;
    if ( (unsigned __int64)qword_180122428 > 7 )
      v100 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
    v101 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
             a2,
             v100);
    if ( v101 < 0 )
    {
      v102 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v103 = 2195;
LABEL_259:
      LODWORD(v144) = v101;
      AslLogCallPrintf(1, "Application::Insert", v103, v102, v144);
    }
  }
  else
  {
    v104 = (_QWORD *)((char *)this + 336);
    v105 = *((_QWORD *)this + 44);
    if ( !v105 )
      goto LABEL_186;
    v106 = &Application::ApplicationSourceAppxPackage;
    if ( (unsigned __int64)qword_180121FE8 > 7 )
      v106 = (__int64 *)Application::ApplicationSourceAppxPackage;
    v107 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v104;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v107, v105, v106) )
    {
LABEL_186:
      v108 = &Application::InventoryItemValueNameStoreAppType;
      if ( (unsigned __int64)qword_1801223C8 > 7 )
        v108 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
      v109 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v108);
      if ( v109 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2206, "TelCacheProvider::SetItemProperty failed [#%x]", v109);
      v110 = &Application::InventoryItemValueNameInboxStoreApp;
      if ( (unsigned __int64)qword_180122468 > 7 )
        v110 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
      v111 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
               a2,
               v110,
               *((unsigned __int8 *)this + 968));
      if ( v111 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2212, "TelCacheProvider::SetItemProperty failed [#%x]", v111);
      v112 = &Application::InventoryItemValueNameManifestPath;
      if ( (unsigned __int64)qword_1801224C8 > 7 )
        v112 = (__int64 *)Application::InventoryItemValueNameManifestPath;
      v113 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v112);
      if ( v113 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2219, "TelCacheProvider::SetItemProperty failed [#%x]", v113);
      if ( *((_QWORD *)this + 119) )
      {
        v114 = &Application::InventoryItemValueNameBundleManifestPath;
        if ( (unsigned __int64)qword_1801224E8 > 7 )
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
      goto LABEL_216;
    v117 = &Application::ApplicationSourceAppxPackage;
    if ( (unsigned __int64)qword_180121FE8 > 7 )
      v117 = (__int64 *)Application::ApplicationSourceAppxPackage;
    v118 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v104;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v118, v116, v117) )
      goto LABEL_216;
    v119 = &Application::ApplicationSourceAppvPackage;
    if ( (unsigned __int64)qword_180121FC8 > 7 )
      v119 = (__int64 *)Application::ApplicationSourceAppvPackage;
    v120 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v104;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v120, *((_QWORD *)this + 44), v119) )
    {
LABEL_216:
      v121 = &Application::InventoryItemValueNamePackageFullName;
      if ( (unsigned __int64)qword_1801224A8 > 7 )
        v121 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
      v122 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v121);
      if ( v122 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2241, "TelCacheProvider::SetItemProperty failed [#%x]", v122);
    }
    if ( (unsigned __int8)std::operator!=<unsigned short>(
                            (char *)this + 336,
                            &Application::ApplicationSourceAppxPackage)
      && (unsigned __int8)std::operator!=<unsigned short>(
                            (char *)this + 336,
                            &Application::ApplicationSourceAppvPackage) )
    {
      v123 = &Application::InventoryItemValueNameHiddenArp;
      if ( (unsigned __int64)qword_180122448 > 7 )
        v123 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
      v124 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
               a2,
               v123,
               *((unsigned __int8 *)this + 700));
      if ( v124 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2251, "TelCacheProvider::SetItemProperty failed [#%x]", v124);
      v125 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
      v126 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 48LL))(v2);
      if ( v126[3] > 7u )
        v126 = (_QWORD *)*v126;
      v127 = &Application::InventoryItemValueNameUninstallString;
      if ( (unsigned __int64)qword_180122528 > 7 )
        v127 = (__int64 *)Application::InventoryItemValueNameUninstallString;
      v128 = v125(a2, v127, v126);
      if ( v128 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2258, "TelCacheProvider::SetItemProperty failed [#%x]", v128);
      v129 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
      v130 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 88LL))(v2);
      if ( v130[3] > 7u )
        v130 = (_QWORD *)*v130;
      v131 = &Application::InventoryItemValueNameArpRegistryKeyPath;
      if ( (unsigned __int64)qword_180122548 > 7 )
        v131 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
      v132 = v129(a2, v131, v130);
      if ( v132 < 0 )
        AslLogCallPrintf(1, "Application::Insert", 2265, "TelCacheProvider::SetItemProperty failed [#%x]", v132);
      v133 = &Application::ApplicationSourceMsi;
      if ( (unsigned __int64)qword_180121EA8 > 7 )
        v133 = (__int64 *)Application::ApplicationSourceMsi;
      if ( *((_QWORD *)this + 45) > 7u )
        v104 = (_QWORD *)*v104;
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v104, *((_QWORD *)this + 44), v133) )
      {
        v134 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
        v135 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 104LL))(v2);
        if ( v135[3] > 7u )
          v135 = (_QWORD *)*v135;
        v136 = &Application::InventoryItemValueNameMsiPackageCode;
        if ( (unsigned __int64)qword_180122408 > 7 )
          v136 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
        v137 = v134(a2, v136, v135);
        if ( v137 < 0 )
          AslLogCallPrintf(1, "Application::Insert", 2275, "TelCacheProvider::SetItemProperty failed [#%x]", v137);
        v138 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
        v139 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 96LL))(v2);
        if ( v139[3] > 7u )
          v139 = (_QWORD *)*v139;
        v140 = &Application::InventoryItemValueNameMsiProductCode;
        if ( (unsigned __int64)qword_1801223E8 > 7 )
          v140 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
        v141 = v138(a2, v140, v139);
        if ( v141 < 0 )
          AslLogCallPrintf(1, "Application::Insert", 2282, "TelCacheProvider::SetItemProperty failed [#%x]", v141);
        v142 = &Application::InventoryItemValueNameMsiInstallDate;
        if ( (unsigned __int64)qword_180122428 > 7 )
          v142 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
        v101 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
                 a2,
                 v142);
        if ( v101 < 0 )
        {
          v102 = "TelCacheProvider::SetItemProperty failed [#%x]";
          v103 = 2289;
          goto LABEL_259;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800d1bb0  push    rbx
0x1800d1bb2  push    rbp
0x1800d1bb3  push    rsi
0x1800d1bb4  push    rdi
0x1800d1bb5  push    r13
0x1800d1bb7  push    r14
0x1800d1bb9  push    r15
0x1800d1bbb  sub     rsp, 30h
0x1800d1bbf  mov     rax, [rdx]
0x1800d1bc2  lea     rsi, [rcx+10h]
0x1800d1bc6  mov     rbp, rcx
0x1800d1bc9  mov     rdi, rdx
0x1800d1bcc  mov     rcx, rsi
0x1800d1bcf  mov     rbx, [rax+88h]
0x1800d1bd6  mov     rax, [rsi]
0x1800d1bd9  mov     rax, [rax+10h]
0x1800d1bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1be2  mov     r15d, 7
0x1800d1be8  cmp     [rax+18h], r15
0x1800d1bec  jbe     short loc_1800D1BF1
0x1800d1bee  mov     rax, [rax]
0x1800d1bf1  cmp     cs:qword_1801222E8, r15
0x1800d1bf8  lea     rdx, ?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x1800d1bff  mov     r8, rax
0x1800d1c02  mov     rcx, rdi
0x1800d1c05  cmova   rdx, cs:?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x1800d1c0d  mov     rax, rbx
0x1800d1c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c15  lea     r13, aApplicationIns; "Application::Insert"
0x1800d1c1c  mov     ebx, eax
0x1800d1c1e  mov     r14d, 1
0x1800d1c24  test    eax, eax
0x1800d1c26  jns     short loc_1800D1C63
0x1800d1c28  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d1c2f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d1c34  mov     dword ptr [rsp+68h+var_48], ebx
0x1800d1c38  mov     rdx, r13
0x1800d1c3b  mov     ecx, r14d
0x1800d1c3e  test    al, al
0x1800d1c40  jz      short loc_1800D1C51
0x1800d1c42  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800d1c49  mov     r8d, 790h
0x1800d1c4f  jmp     short loc_1800D1C5E
0x1800d1c51  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800d1c58  mov     r8d, 794h
0x1800d1c5e  call    AslLogCallPrintf
0x1800d1c63  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d1c6a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d1c6f  mov     rcx, rsi
0x1800d1c72  test    al, al
0x1800d1c74  jz      short loc_1800D1CD0
0x1800d1c76  mov     rax, [rdi]
0x1800d1c79  mov     rbx, [rax+88h]
0x1800d1c80  mov     rax, [rsi]
0x1800d1c83  mov     rax, [rax+50h]
0x1800d1c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c8c  cmp     [rax+18h], r15
0x1800d1c90  jbe     short loc_1800D1C95
0x1800d1c92  mov     rax, [rax]
0x1800d1c95  cmp     cs:qword_180122308, r15
0x1800d1c9c  lea     rdx, ?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800d1ca3  mov     r8, rax
0x1800d1ca6  mov     rcx, rdi
0x1800d1ca9  cmova   rdx, cs:?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800d1cb1  mov     rax, rbx
0x1800d1cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1cb9  test    eax, eax
0x1800d1cbb  jns     loc_1800D1D49
0x1800d1cc1  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800d1cc8  mov     r8d, 79Eh
0x1800d1cce  jmp     short loc_1800D1D3A
0x1800d1cd0  mov     rax, [rsi]
0x1800d1cd3  mov     rax, [rax+50h]
0x1800d1cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1cdc  cmp     qword ptr [rax+10h], 0
0x1800d1ce1  jz      short loc_1800D1D49
0x1800d1ce3  mov     rax, [rdi]
0x1800d1ce6  mov     rcx, rsi
0x1800d1ce9  mov     rbx, [rax+88h]
0x1800d1cf0  mov     rax, [rsi]
0x1800d1cf3  mov     rax, [rax+50h]
0x1800d1cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1cfc  cmp     [rax+18h], r15
0x1800d1d00  jbe     short loc_1800D1D05
0x1800d1d02  mov     rax, [rax]
0x1800d1d05  cmp     cs:qword_180122308, r15
0x1800d1d0c  lea     rdx, ?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800d1d13  mov     r8, rax
0x1800d1d16  mov     rcx, rdi
0x1800d1d19  cmova   rdx, cs:?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800d1d21  mov     rax, rbx
0x1800d1d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d29  test    eax, eax
0x1800d1d2b  jns     short loc_1800D1D49
0x1800d1d2d  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800d1d34  mov     r8d, 7AAh
0x1800d1d3a  mov     rdx, r13
0x1800d1d3d  mov     dword ptr [rsp+68h+var_48], eax
0x1800d1d41  mov     ecx, r14d
0x1800d1d44  call    AslLogCallPrintf
0x1800d1d49  mov     rax, [rdi]
0x1800d1d4c  mov     rcx, rsi
0x1800d1d4f  mov     rbx, [rax+88h]
0x1800d1d56  mov     rax, [rsi]
0x1800d1d59  mov     rax, [rax+8]
0x1800d1d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d62  cmp     [rax+18h], r15
0x1800d1d66  jbe     short loc_1800D1D6B
0x1800d1d68  mov     rax, [rax]
0x1800d1d6b  cmp     cs:qword_180122328, r15
0x1800d1d72  lea     rdx, ?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x1800d1d79  mov     r8, rax
0x1800d1d7c  mov     rcx, rdi
0x1800d1d7f  cmova   rdx, cs:?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x1800d1d87  mov     rax, rbx
0x1800d1d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d8f  mov     ebx, eax
0x1800d1d91  test    eax, eax
0x1800d1d93  jns     short loc_1800D1DD0
0x1800d1d95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d1d9c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d1da1  mov     dword ptr [rsp+68h+var_48], ebx
0x1800d1da5  mov     rdx, r13
0x1800d1da8  mov     ecx, r14d
0x1800d1dab  test    al, al
0x1800d1dad  jz      short loc_1800D1DBE
0x1800d1daf  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800d1db6  mov     r8d, 7B4h
0x1800d1dbc  jmp     short loc_1800D1DCB
0x1800d1dbe  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800d1dc5  mov     r8d, 7B8h
0x1800d1dcb  call    AslLogCallPrintf
0x1800d1dd0  mov     rax, [rdi]
0x1800d1dd3  mov     rcx, rsi
0x1800d1dd6  mov     rbx, [rax+88h]
0x1800d1ddd  mov     rax, [rsi]
0x1800d1de0  mov     rax, [rax+20h]
0x1800d1de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1de9  cmp     [rax+18h], r15
0x1800d1ded  jbe     short loc_1800D1DF2
0x1800d1def  mov     rax, [rax]
0x1800d1df2  cmp     cs:qword_180122348, r15
0x1800d1df9  lea     rdx, ?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x1800d1e00  mov     r8, rax
0x1800d1e03  mov     rcx, rdi
0x1800d1e06  cmova   rdx, cs:?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x1800d1e0e  mov     rax, rbx
0x1800d1e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1e16  mov     ebx, eax
0x1800d1e18  test    eax, eax
0x1800d1e1a  jns     short loc_1800D1E57
0x1800d1e1c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d1e23  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d1e28  mov     dword ptr [rsp+68h+var_48], ebx
0x1800d1e2c  mov     rdx, r13
0x1800d1e2f  mov     ecx, r14d
0x1800d1e32  test    al, al
0x1800d1e34  jz      short loc_1800D1E45
0x1800d1e36  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800d1e3d  mov     r8d, 7C1h
0x1800d1e43  jmp     short loc_1800D1E52
0x1800d1e45  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800d1e4c  mov     r8d, 7C5h
0x1800d1e52  call    AslLogCallPrintf
0x1800d1e57  mov     rax, [rdi]
0x1800d1e5a  mov     rcx, rsi
0x1800d1e5d  mov     rbx, [rax+88h]
0x1800d1e64  mov     rax, [rsi]
0x1800d1e67  mov     rax, [rax+18h]
0x1800d1e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1e70  cmp     [rax+18h], r15
0x1800d1e74  jbe     short loc_1800D1E79
0x1800d1e76  mov     rax, [rax]
0x1800d1e79  cmp     cs:qword_180122368, r15
0x1800d1e80  lea     rdx, ?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x1800d1e87  mov     r8, rax
0x1800d1e8a  mov     rcx, rdi
0x1800d1e8d  cmova   rdx, cs:?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x1800d1e95  mov     rax, rbx
0x1800d1e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1e9d  mov     ebx, eax
0x1800d1e9f  test    eax, eax
0x1800d1ea1  jns     short loc_1800D1EDE
0x1800d1ea3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d1eaa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d1eaf  mov     dword ptr [rsp+68h+var_48], ebx
0x1800d1eb3  mov     rdx, r13
0x1800d1eb6  mov     ecx, r14d
0x1800d1eb9  test    al, al
0x1800d1ebb  jz      short loc_1800D1ECC
0x1800d1ebd  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800d1ec4  mov     r8d, 7CEh
0x1800d1eca  jmp     short loc_1800D1ED9
0x1800d1ecc  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800d1ed3  mov     r8d, 7D2h
0x1800d1ed9  call    AslLogCallPrintf
0x1800d1ede  mov     rax, [rdi]
0x1800d1ee1  mov     rcx, rsi
0x1800d1ee4  mov     rbx, [rax+98h]
0x1800d1eeb  mov     rax, [rsi]
0x1800d1eee  mov     rax, [rax+78h]
0x1800d1ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1ef7  cmp     cs:qword_180122388, r15
0x1800d1efe  lea     rdx, ?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x1800d1f05  mov     r8d, eax
0x1800d1f08  mov     rcx, rdi
0x1800d1f0b  cmova   rdx, cs:?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x1800d1f13  mov     rax, rbx
0x1800d1f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1f1b  mov     ebx, eax
0x1800d1f1d  test    eax, eax
0x1800d1f1f  jns     short loc_1800D1F5C
0x1800d1f21  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d1f28  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d1f2d  mov     dword ptr [rsp+68h+var_48], ebx
0x1800d1f31  mov     rdx, r13
0x1800d1f34  mov     ecx, r14d
0x1800d1f37  test    al, al
0x1800d1f39  jz      short loc_1800D1F4A
0x1800d1f3b  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800d1f42  mov     r8d, 7DBh
0x1800d1f48  jmp     short loc_1800D1F57
0x1800d1f4a  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800d1f51  mov     r8d, 7DFh
0x1800d1f57  call    AslLogCallPrintf
0x1800d1f5c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d1f63  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800d1f68  mov     rcx, rsi
0x1800d1f6b  test    al, al
0x1800d1f6d  jz      short loc_1800D1FC9
0x1800d1f6f  mov     rax, [rdi]
0x1800d1f72  mov     rbx, [rax+88h]
0x1800d1f79  mov     rax, [rsi]
0x1800d1f7c  mov     rax, [rax+38h]
0x1800d1f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1f85  cmp     [rax+18h], r15
0x1800d1f89  jbe     short loc_1800D1F8E
0x1800d1f8b  mov     rax, [rax]
0x1800d1f8e  cmp     cs:qword_180122488, r15
0x1800d1f95  lea     rdx, ?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800d1f9c  mov     r8, rax
0x1800d1f9f  mov     rcx, rdi
0x1800d1fa2  cmova   rdx, cs:?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800d1faa  mov     rax, rbx
0x1800d1fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1fb2  test    eax, eax
0x1800d1fb4  jns     loc_1800D2042
0x1800d1fba  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800d1fc1  mov     r8d, 7E8h
0x1800d1fc7  jmp     short loc_1800D2033
0x1800d1fc9  mov     rax, [rsi]
0x1800d1fcc  mov     rax, [rax+38h]
0x1800d1fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1fd5  cmp     qword ptr [rax+10h], 0
0x1800d1fda  jz      short loc_1800D2042
0x1800d1fdc  mov     rax, [rdi]
0x1800d1fdf  mov     rcx, rsi
0x1800d1fe2  mov     rbx, [rax+88h]
0x1800d1fe9  mov     rax, [rsi]
0x1800d1fec  mov     rax, [rax+38h]
0x1800d1ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1ff5  cmp     [rax+18h], r15
0x1800d1ff9  jbe     short loc_1800D1FFE
0x1800d1ffb  mov     rax, [rax]
0x1800d1ffe  cmp     cs:qword_180122488, r15
0x1800d2005  lea     rdx, ?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800d200c  mov     r8, rax
0x1800d200f  mov     rcx, rdi
0x1800d2012  cmova   rdx, cs:?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800d201a  mov     rax, rbx
0x1800d201d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2022  test    eax, eax
0x1800d2024  jns     short loc_1800D2042
0x1800d2026  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800d202d  mov     r8d, 7F3h
0x1800d2033  mov     rdx, r13
0x1800d2036  mov     dword ptr [rsp+68h+var_48], eax
0x1800d203a  mov     ecx, r14d
0x1800d203d  call    AslLogCallPrintf
0x1800d2042  mov     rax, [rdi]
0x1800d2045  mov     rcx, rsi
0x1800d2048  mov     rbx, [rax+88h]
0x1800d204f  mov     rax, [rsi]
0x1800d2052  mov     rax, [rax+40h]
0x1800d2056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d205b  cmp     [rax+18h], r15
0x1800d205f  jbe     short loc_1800D2064
0x1800d2061  mov     rax, [rax]
0x1800d2064  cmp     cs:qword_1801223A8, r15
0x1800d206b  lea     rdx, ?InventoryItemValueNameSource@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameSource
0x1800d2072  mov     r8, rax
0x1800d2075  mov     rcx, rdi
0x1800d2078  cmova   rdx, cs:?InventoryItemValueNameSource@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameSource
0x1800d2080  mov     rax, rbx
0x1800d2083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2088  mov     ebx, eax
0x1800d208a  test    eax, eax
0x1800d208c  jns     short loc_1800D20C9
0x1800d208e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800d2095  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
  ... truncated ...
```
