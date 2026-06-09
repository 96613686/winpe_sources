# Application::Insert(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x1800fd490`
- end: `0x1800fe5a5`
- name: `?Insert@Application@@UEAAKPEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `4373`
- prototype: `unsigned int __fastcall(Application *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180012950`
- `0x1800197d4`
- `0x180046510`
- `0x180046f38`
- `0x1800fd490`
- `0x180130010`

## string_xrefs

- `0x1800fd522`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fd5a1`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fd68f`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fd716`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fd79d`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fd81b`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fd89a`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fd988`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fda07`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fdb01`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fdb60`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fdc0e`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fdcc8`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fdd15`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fdd6d`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fddc5`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fde1d`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fde6a`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fded0`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fdf36`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fdf9c`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fe002`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fe05e`: `TelCacheProvider::SetItemProperty failed [%#x]`
- `0x1800fd531`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fd60d`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fd69e`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fd725`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fd7ac`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fd82a`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fd906`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fd997`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fda7f`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fdb10`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fdba3`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fdc5c`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe0f4`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe141`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe199`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe1fb`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe2cb`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe346`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe3ac`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe41a`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe4ba`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe520`: `TelCacheProvider::SetItemProperty failed [#%x]`
- `0x1800fe578`: `TelCacheProvider::SetItemProperty failed [#%x]`

## pseudocode

```c
__int64 __fastcall Application::Insert(Application *this, struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  char *v2; // rsi
  __int64 (__fastcall *v5)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v6; // rax
  __int64 *v7; // rdx
  int v8; // ebx
  const char *v9; // r9
  int v10; // r8d
  __int64 (__fastcall *v11)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v12; // rax
  __int64 *v13; // rdx
  int v14; // eax
  const char *v15; // r9
  int v16; // r8d
  __int64 (__fastcall *v17)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v18; // rax
  __int64 *v19; // rdx
  __int64 (__fastcall *v20)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v21; // rax
  __int64 *v22; // rdx
  int v23; // ebx
  const char *v24; // r9
  int v25; // r8d
  __int64 (__fastcall *v26)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v27; // rax
  __int64 *v28; // rdx
  int v29; // ebx
  const char *v30; // r9
  int v31; // r8d
  __int64 (__fastcall *v32)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v33; // rax
  __int64 *v34; // rdx
  int v35; // ebx
  const char *v36; // r9
  int v37; // r8d
  __int64 (__fastcall *v38)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD); // rbx
  unsigned int v39; // eax
  __int64 *v40; // rdx
  int v41; // ebx
  const char *v42; // r9
  int v43; // r8d
  __int64 (__fastcall *v44)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v45; // rax
  __int64 *v46; // rdx
  int v47; // eax
  const char *v48; // r9
  int v49; // r8d
  __int64 (__fastcall *v50)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v51; // rax
  __int64 *v52; // rdx
  __int64 (__fastcall *v53)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v54; // rax
  __int64 *v55; // rdx
  int v56; // ebx
  const char *v57; // r9
  int v58; // r8d
  __int64 (__fastcall *v59)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v60; // rax
  __int64 *v61; // rdx
  int v62; // eax
  const char *v63; // r9
  int v64; // r8d
  __int64 v65; // rax
  __int64 (__fastcall *v66)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v67; // rax
  __int64 *v68; // rdx
  __int64 (__fastcall *v69)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v70; // rax
  __int64 *v71; // rdx
  int v72; // ebx
  const char *v73; // r9
  int v74; // r8d
  __int64 *v75; // rdx
  int v76; // eax
  const char *v77; // r9
  int v78; // r8d
  __int64 *v79; // rdx
  _QWORD *v80; // rbx
  __int64 *v81; // rdx
  int v82; // eax
  const char *v83; // r9
  int v84; // r8d
  __int64 *v85; // rdx
  __int64 *v86; // rdx
  __int64 *v87; // rdx
  __int64 *v88; // rdx
  __int64 *v89; // rdx
  __int64 *v90; // rdx
  __int64 *v91; // rdx
  int (__fastcall *v92)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v93; // rax
  __int64 *v94; // rdx
  int (__fastcall *v95)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v96; // rax
  __int64 *v97; // rdx
  int (__fastcall *v98)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v99; // rax
  __int64 *v100; // rdx
  int (__fastcall *v101)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v102; // rax
  __int64 *v103; // rdx
  __int64 *v104; // rdx
  const char *v105; // r9
  int v106; // r8d
  _QWORD *v107; // rbx
  __int64 v108; // rdx
  __int64 *v109; // r8
  Application *v110; // rcx
  __int64 *v111; // rdx
  int v112; // eax
  __int64 *v113; // rdx
  int v114; // eax
  __int64 *v115; // rdx
  int v116; // eax
  __int64 *v117; // rdx
  int v118; // eax
  __int64 v119; // rdx
  __int64 *v120; // r8
  Application *v121; // rcx
  __int64 *v122; // r8
  Application *v123; // rcx
  __int64 *v124; // rdx
  int v125; // eax
  __int64 *v126; // rdx
  int v127; // eax
  __int64 (__fastcall *v128)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // r14
  _QWORD *v129; // rax
  __int64 *v130; // rdx
  int v131; // eax
  __int64 (__fastcall *v132)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // r14
  _QWORD *v133; // rax
  __int64 *v134; // rdx
  int v135; // eax
  __int64 *v136; // r8
  int (__fastcall *v137)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v138; // rax
  __int64 *v139; // rdx
  int (__fastcall *v140)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *); // rbx
  _QWORD *v141; // rax
  __int64 *v142; // rdx
  __int64 *v143; // rdx
  int v145; // [rsp+20h] [rbp-48h]

  v2 = (char *)this + 16;
  v5 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v6 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  v7 = &Application::InventoryItemValueNameProgramId;
  if ( (unsigned __int64)qword_180182A78 > 7 )
    v7 = (__int64 *)Application::InventoryItemValueNameProgramId;
  v8 = v5(a2, v7, v6);
  if ( v8 < 0 )
  {
    v145 = v8;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      v9 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v10 = 1936;
    }
    else
    {
      v9 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v10 = 1940;
    }
    AslLogCallPrintf(1, (unsigned int)"Application::Insert", v10, (_DWORD)v9);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v11 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v12 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 80LL))(v2);
    if ( v12[3] > 7u )
      v12 = (_QWORD *)*v12;
    v13 = &Application::InventoryItemValueNameProgramInstanceId;
    if ( (unsigned __int64)qword_180182A98 > 7 )
      v13 = (__int64 *)Application::InventoryItemValueNameProgramInstanceId;
    v14 = v11(a2, v13, v12);
    if ( v14 < 0 )
    {
      v15 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v16 = 1950;
LABEL_24:
      v145 = v14;
      AslLogCallPrintf(1, (unsigned int)"Application::Insert", v16, (_DWORD)v15);
    }
  }
  else if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 80LL))(v2) + 16) )
  {
    v17 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v18 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 80LL))(v2);
    if ( v18[3] > 7u )
      v18 = (_QWORD *)*v18;
    v19 = &Application::InventoryItemValueNameProgramInstanceId;
    if ( (unsigned __int64)qword_180182A98 > 7 )
      v19 = (__int64 *)Application::InventoryItemValueNameProgramInstanceId;
    v14 = v17(a2, v19, v18);
    if ( v14 < 0 )
    {
      v15 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v16 = 1962;
      goto LABEL_24;
    }
  }
  v20 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v21 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  if ( v21[3] > 7u )
    v21 = (_QWORD *)*v21;
  v22 = &Application::InventoryItemValueNameName;
  if ( (unsigned __int64)qword_180182AB8 > 7 )
    v22 = (__int64 *)Application::InventoryItemValueNameName;
  v23 = v20(a2, v22, v21);
  if ( v23 < 0 )
  {
    v145 = v23;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      v24 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v25 = 1972;
    }
    else
    {
      v24 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v25 = 1976;
    }
    AslLogCallPrintf(1, (unsigned int)"Application::Insert", v25, (_DWORD)v24);
  }
  v26 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v27 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 32LL))(v2);
  if ( v27[3] > 7u )
    v27 = (_QWORD *)*v27;
  v28 = &Application::InventoryItemValueNameVersion;
  if ( (unsigned __int64)qword_180182AD8 > 7 )
    v28 = (__int64 *)Application::InventoryItemValueNameVersion;
  v29 = v26(a2, v28, v27);
  if ( v29 < 0 )
  {
    v145 = v29;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      v30 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v31 = 1985;
    }
    else
    {
      v30 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v31 = 1989;
    }
    AslLogCallPrintf(1, (unsigned int)"Application::Insert", v31, (_DWORD)v30);
  }
  v32 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v33 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 24LL))(v2);
  if ( v33[3] > 7u )
    v33 = (_QWORD *)*v33;
  v34 = &Application::InventoryItemValueNamePublisher;
  if ( (unsigned __int64)qword_180182AF8 > 7 )
    v34 = (__int64 *)Application::InventoryItemValueNamePublisher;
  v35 = v32(a2, v34, v33);
  if ( v35 < 0 )
  {
    v145 = v35;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      v36 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v37 = 1998;
    }
    else
    {
      v36 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v37 = 2002;
    }
    AslLogCallPrintf(1, (unsigned int)"Application::Insert", v37, (_DWORD)v36);
  }
  v38 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 152LL);
  v39 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 120LL))(v2);
  v40 = &Application::InventoryItemValueNameLanguage;
  if ( (unsigned __int64)qword_180182B18 > 7 )
    v40 = (__int64 *)Application::InventoryItemValueNameLanguage;
  v41 = v38(a2, v40, v39);
  if ( v41 < 0 )
  {
    v145 = v41;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      v42 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v43 = 2011;
    }
    else
    {
      v42 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v43 = 2015;
    }
    AslLogCallPrintf(1, (unsigned int)"Application::Insert", v43, (_DWORD)v42);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v44 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v45 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 56LL))(v2);
    if ( v45[3] > 7u )
      v45 = (_QWORD *)*v45;
    v46 = &Application::InventoryItemValueNameInstallDate;
    if ( (unsigned __int64)qword_180182C18 > 7 )
      v46 = (__int64 *)Application::InventoryItemValueNameInstallDate;
    v47 = v44(a2, v46, v45);
    if ( v47 < 0 )
    {
      v48 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v49 = 2024;
LABEL_73:
      v145 = v47;
      AslLogCallPrintf(1, (unsigned int)"Application::Insert", v49, (_DWORD)v48);
    }
  }
  else if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 56LL))(v2) + 16) )
  {
    v50 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v51 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 56LL))(v2);
    if ( v51[3] > 7u )
      v51 = (_QWORD *)*v51;
    v52 = &Application::InventoryItemValueNameInstallDate;
    if ( (unsigned __int64)qword_180182C18 > 7 )
      v52 = (__int64 *)Application::InventoryItemValueNameInstallDate;
    v47 = v50(a2, v52, v51);
    if ( v47 < 0 )
    {
      v48 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v49 = 2035;
      goto LABEL_73;
    }
  }
  v53 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v54 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 64LL))(v2);
  if ( v54[3] > 7u )
    v54 = (_QWORD *)*v54;
  v55 = &Application::InventoryItemValueNameSource;
  if ( (unsigned __int64)qword_180182B38 > 7 )
    v55 = (__int64 *)Application::InventoryItemValueNameSource;
  v56 = v53(a2, v55, v54);
  if ( v56 < 0 )
  {
    v145 = v56;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      v57 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v58 = 2045;
    }
    else
    {
      v57 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v58 = 2049;
    }
    AslLogCallPrintf(1, (unsigned int)"Application::Insert", v58, (_DWORD)v57);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v59 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v60 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 72LL))(v2);
    if ( v60[3] > 7u )
      v60 = (_QWORD *)*v60;
    v61 = &Application::InventoryItemValueNameAppType;
    if ( (unsigned __int64)qword_180182D18 > 7 )
      v61 = (__int64 *)Application::InventoryItemValueNameAppType;
    v62 = v59(a2, v61, v60);
    if ( v62 < 0 )
    {
      v63 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v64 = 2058;
LABEL_97:
      v145 = v62;
      AslLogCallPrintf(1, (unsigned int)"Application::Insert", v64, (_DWORD)v63);
    }
  }
  else
  {
    v65 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 72LL))(v2);
    if ( (unsigned __int8)std::operator!=<unsigned short>(v65, Application::ApplicationTypeApplication) )
    {
      v66 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
      v67 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 72LL))(v2);
      if ( v67[3] > 7u )
        v67 = (_QWORD *)*v67;
      v68 = &Application::InventoryItemValueNameAppType;
      if ( (unsigned __int64)qword_180182D18 > 7 )
        v68 = (__int64 *)Application::InventoryItemValueNameAppType;
      v62 = v66(a2, v68, v67);
      if ( v62 < 0 )
      {
        v63 = "TelCacheProvider::SetItemProperty failed [#%x]";
        v64 = 2069;
        goto LABEL_97;
      }
    }
  }
  v69 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
  v70 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 40LL))(v2);
  if ( v70[3] > 7u )
    v70 = (_QWORD *)*v70;
  v71 = &Application::InventoryItemValueNameRootDirPath;
  if ( (unsigned __int64)qword_180182C98 > 7 )
    v71 = (__int64 *)Application::InventoryItemValueNameRootDirPath;
  v72 = v69(a2, v71, v70);
  if ( v72 < 0 )
  {
    v145 = v72;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      v73 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v74 = 2079;
    }
    else
    {
      v73 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v74 = 2083;
    }
    AslLogCallPrintf(1, (unsigned int)"Application::Insert", v74, (_DWORD)v73);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v75 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_180182CF8 > 7 )
      v75 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
    v76 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
            a2,
            v75,
            *((unsigned __int8 *)this + 88));
    if ( v76 < 0 )
    {
      v77 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v78 = 2092;
LABEL_117:
      v145 = v76;
      AslLogCallPrintf(1, (unsigned int)"Application::Insert", v78, (_DWORD)v77);
    }
  }
  else if ( *((_BYTE *)this + 88) )
  {
    v79 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_180182CF8 > 7 )
      v79 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
    v76 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
            a2,
            v79,
            *((unsigned __int8 *)this + 88));
    if ( v76 < 0 )
    {
      v77 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v78 = 2103;
      goto LABEL_117;
    }
  }
  v80 = (_QWORD *)((char *)this + 304);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( *((_QWORD *)this + 41) > 7u )
      v80 = (_QWORD *)*v80;
    v81 = &Application::InventoryItemValueNameUserSid;
    if ( (unsigned __int64)qword_180182D38 > 7 )
      v81 = (__int64 *)Application::InventoryItemValueNameUserSid;
    v82 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v81,
            v80);
    if ( v82 < 0 )
    {
      v83 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v84 = 2113;
LABEL_132:
      v145 = v82;
      AslLogCallPrintf(1, (unsigned int)"Application::Insert", v84, (_DWORD)v83);
    }
  }
  else if ( *((_QWORD *)this + 40) )
  {
    if ( *((_QWORD *)this + 41) > 7u )
      v80 = (_QWORD *)*v80;
    v85 = &Application::InventoryItemValueNameUserSid;
    if ( (unsigned __int64)qword_180182D38 > 7 )
      v85 = (__int64 *)Application::InventoryItemValueNameUserSid;
    v82 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v85,
            v80);
    if ( v82 < 0 )
    {
      v83 = "TelCacheProvider::SetItemProperty failed [#%x]";
      v84 = 2123;
      goto LABEL_132;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v86 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_180182B58 > 7 )
      v86 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
           a2,
           v86) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2133,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v87 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_180182BF8 > 7 )
      v87 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
           a2,
           v87,
           *((unsigned __int8 *)this + 968)) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2139,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v88 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_180182C58 > 7 )
      v88 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
           a2,
           v88) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2145,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v89 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_180182C78 > 7 )
      v89 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
           a2,
           v89) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2152,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v90 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_180182C38 > 7 )
      v90 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
           a2,
           v90) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2158,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v91 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_180182BD8 > 7 )
      v91 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
           a2,
           v91,
           *((unsigned __int8 *)this + 700)) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2164,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v92 = *(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v93 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 48LL))(v2);
    if ( v93[3] > 7u )
      v93 = (_QWORD *)*v93;
    v94 = &Application::InventoryItemValueNameUninstallString;
    if ( (unsigned __int64)qword_180182CB8 > 7 )
      v94 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    if ( v92(a2, v94, v93) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2170,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v95 = *(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v96 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 88LL))(v2);
    if ( v96[3] > 7u )
      v96 = (_QWORD *)*v96;
    v97 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_180182CD8 > 7 )
      v97 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( v95(a2, v97, v96) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2177,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v98 = *(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v99 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 104LL))(v2);
    if ( v99[3] > 7u )
      v99 = (_QWORD *)*v99;
    v100 = &Application::InventoryItemValueNameMsiPackageCode;
    if ( (unsigned __int64)qword_180182B98 > 7 )
      v100 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
    if ( v98(a2, v100, v99) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2183,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v101 = *(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
    v102 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 96LL))(v2);
    if ( v102[3] > 7u )
      v102 = (_QWORD *)*v102;
    v103 = &Application::InventoryItemValueNameMsiProductCode;
    if ( (unsigned __int64)qword_180182B78 > 7 )
      v103 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
    if ( v101(a2, v103, v102) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Application::Insert",
        2189,
        (unsigned int)"TelCacheProvider::SetItemProperty failed [%#x]");
    v104 = &Application::InventoryItemValueNameMsiInstallDate;
    if ( (unsigned __int64)qword_180182BB8 > 7 )
      v104 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
           a2,
           v104) < 0 )
    {
      v105 = "TelCacheProvider::SetItemProperty failed [%#x]";
      v106 = 2195;
LABEL_266:
      AslLogCallPrintf(1, (unsigned int)"Application::Insert", v106, (_DWORD)v105);
    }
  }
  else
  {
    v107 = (_QWORD *)((char *)this + 336);
    v108 = *((_QWORD *)this + 44);
    if ( !v108 )
      goto LABEL_193;
    v109 = &Application::ApplicationSourceAppxPackage;
    if ( (unsigned __int64)qword_180182778 > 7 )
      v109 = (__int64 *)Application::ApplicationSourceAppxPackage;
    v110 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v107;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v110, v108, v109, qword_180182770, v145) )
    {
LABEL_193:
      v111 = &Application::InventoryItemValueNameStoreAppType;
      if ( (unsigned __int64)qword_180182B58 > 7 )
        v111 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
      v112 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v111);
      if ( v112 < 0 )
      {
        v145 = v112;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Insert",
          2206,
          (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
      }
      v113 = &Application::InventoryItemValueNameInboxStoreApp;
      if ( (unsigned __int64)qword_180182BF8 > 7 )
        v113 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
      v114 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
               a2,
               v113,
               *((unsigned __int8 *)this + 968));
      if ( v114 < 0 )
      {
        v145 = v114;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Insert",
          2212,
          (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
      }
      v115 = &Application::InventoryItemValueNameManifestPath;
      if ( (unsigned __int64)qword_180182C58 > 7 )
        v115 = (__int64 *)Application::InventoryItemValueNameManifestPath;
      v116 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v115);
      if ( v116 < 0 )
      {
        v145 = v116;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Insert",
          2219,
          (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
      }
      if ( *((_QWORD *)this + 119) )
      {
        v117 = &Application::InventoryItemValueNameBundleManifestPath;
        if ( (unsigned __int64)qword_180182C78 > 7 )
          v117 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
        v118 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
                 a2,
                 v117);
        if ( v118 < 0 )
        {
          v145 = v118;
          AslLogCallPrintf(
            1,
            (unsigned int)"Application::Insert",
            2229,
            (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
        }
      }
    }
    v119 = *((_QWORD *)this + 44);
    if ( !v119 )
      goto LABEL_223;
    v120 = &Application::ApplicationSourceAppxPackage;
    if ( (unsigned __int64)qword_180182778 > 7 )
      v120 = (__int64 *)Application::ApplicationSourceAppxPackage;
    v121 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v107;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v121, v119, v120, qword_180182770, v145) )
      goto LABEL_223;
    v122 = &Application::ApplicationSourceAppvPackage;
    if ( (unsigned __int64)qword_180182758 > 7 )
      v122 = (__int64 *)Application::ApplicationSourceAppvPackage;
    v123 = *((_QWORD *)this + 45) <= 7u ? (Application *)((char *)this + 336) : (Application *)*v107;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                            v123,
                            *((_QWORD *)this + 44),
                            v122,
                            qword_180182750,
                            v145) )
    {
LABEL_223:
      v124 = &Application::InventoryItemValueNamePackageFullName;
      if ( (unsigned __int64)qword_180182C38 > 7 )
        v124 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
      v125 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v124);
      if ( v125 < 0 )
      {
        v145 = v125;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Insert",
          2241,
          (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
      }
    }
    if ( (unsigned __int8)std::operator!=<unsigned short>(
                            (char *)this + 336,
                            &Application::ApplicationSourceAppxPackage)
      && (unsigned __int8)std::operator!=<unsigned short>(
                            (char *)this + 336,
                            &Application::ApplicationSourceAppvPackage) )
    {
      v126 = &Application::InventoryItemValueNameHiddenArp;
      if ( (unsigned __int64)qword_180182BD8 > 7 )
        v126 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
      v127 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
               a2,
               v126,
               *((unsigned __int8 *)this + 700));
      if ( v127 < 0 )
      {
        v145 = v127;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Insert",
          2251,
          (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
      }
      v128 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
      v129 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 48LL))(v2);
      if ( v129[3] > 7u )
        v129 = (_QWORD *)*v129;
      v130 = &Application::InventoryItemValueNameUninstallString;
      if ( (unsigned __int64)qword_180182CB8 > 7 )
        v130 = (__int64 *)Application::InventoryItemValueNameUninstallString;
      v131 = v128(a2, v130, v129);
      if ( v131 < 0 )
      {
        v145 = v131;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Insert",
          2258,
          (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
      }
      v132 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
      v133 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 88LL))(v2);
      if ( v133[3] > 7u )
        v133 = (_QWORD *)*v133;
      v134 = &Application::InventoryItemValueNameArpRegistryKeyPath;
      if ( (unsigned __int64)qword_180182CD8 > 7 )
        v134 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
      v135 = v132(a2, v134, v133);
      if ( v135 < 0 )
      {
        v145 = v135;
        AslLogCallPrintf(
          1,
          (unsigned int)"Application::Insert",
          2265,
          (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
      }
      v136 = &Application::ApplicationSourceMsi;
      if ( (unsigned __int64)qword_180182638 > 7 )
        v136 = (__int64 *)Application::ApplicationSourceMsi;
      if ( *((_QWORD *)this + 45) > 7u )
        v107 = (_QWORD *)*v107;
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                              v107,
                              *((_QWORD *)this + 44),
                              v136,
                              qword_180182630,
                              v145) )
      {
        v137 = *(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
        v138 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 104LL))(v2);
        if ( v138[3] > 7u )
          v138 = (_QWORD *)*v138;
        v139 = &Application::InventoryItemValueNameMsiPackageCode;
        if ( (unsigned __int64)qword_180182B98 > 7 )
          v139 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
        if ( v137(a2, v139, v138) < 0 )
          AslLogCallPrintf(
            1,
            (unsigned int)"Application::Insert",
            2275,
            (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
        v140 = *(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _QWORD *))(*(_QWORD *)a2 + 136LL);
        v141 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 96LL))(v2);
        if ( v141[3] > 7u )
          v141 = (_QWORD *)*v141;
        v142 = &Application::InventoryItemValueNameMsiProductCode;
        if ( (unsigned __int64)qword_180182B78 > 7 )
          v142 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
        if ( v140(a2, v142, v141) < 0 )
          AslLogCallPrintf(
            1,
            (unsigned int)"Application::Insert",
            2282,
            (unsigned int)"TelCacheProvider::SetItemProperty failed [#%x]");
        v143 = &Application::InventoryItemValueNameMsiInstallDate;
        if ( (unsigned __int64)qword_180182BB8 > 7 )
          v143 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
        if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *))(*(_QWORD *)a2 + 136LL))(
               a2,
               v143) < 0 )
        {
          v105 = "TelCacheProvider::SetItemProperty failed [#%x]";
          v106 = 2289;
          goto LABEL_266;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800fd490  push    rbx
0x1800fd492  push    rbp
0x1800fd493  push    rsi
0x1800fd494  push    rdi
0x1800fd495  push    r13
0x1800fd497  push    r14
0x1800fd499  push    r15
0x1800fd49b  sub     rsp, 30h
0x1800fd49f  mov     rax, [rdx]
0x1800fd4a2  lea     rsi, [rcx+10h]
0x1800fd4a6  mov     rbp, rcx
0x1800fd4a9  mov     rdi, rdx
0x1800fd4ac  mov     rcx, rsi
0x1800fd4af  mov     rbx, [rax+88h]
0x1800fd4b6  mov     rax, [rsi]
0x1800fd4b9  mov     rax, [rax+10h]
0x1800fd4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd4c2  mov     r15d, 7
0x1800fd4c8  cmp     [rax+18h], r15
0x1800fd4cc  jbe     short loc_1800FD4D1
0x1800fd4ce  mov     rax, [rax]
0x1800fd4d1  cmp     cs:qword_180182A78, r15
0x1800fd4d8  lea     rdx, ?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x1800fd4df  mov     r8, rax
0x1800fd4e2  mov     rcx, rdi
0x1800fd4e5  cmova   rdx, cs:?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x1800fd4ed  mov     rax, rbx
0x1800fd4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd4f5  lea     r13, aApplicationIns; "Application::Insert"
0x1800fd4fc  mov     ebx, eax
0x1800fd4fe  mov     r14d, 1
0x1800fd504  test    eax, eax
0x1800fd506  jns     short loc_1800FD543
0x1800fd508  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800fd50f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800fd514  mov     [rsp+68h+var_48], ebx
0x1800fd518  mov     rdx, r13
0x1800fd51b  mov     ecx, r14d
0x1800fd51e  test    al, al
0x1800fd520  jz      short loc_1800FD531
0x1800fd522  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800fd529  mov     r8d, 790h
0x1800fd52f  jmp     short loc_1800FD53E
0x1800fd531  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800fd538  mov     r8d, 794h
0x1800fd53e  call    AslLogCallPrintf
0x1800fd543  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800fd54a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800fd54f  mov     rcx, rsi
0x1800fd552  test    al, al
0x1800fd554  jz      short loc_1800FD5B0
0x1800fd556  mov     rax, [rdi]
0x1800fd559  mov     rbx, [rax+88h]
0x1800fd560  mov     rax, [rsi]
0x1800fd563  mov     rax, [rax+50h]
0x1800fd567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd56c  cmp     [rax+18h], r15
0x1800fd570  jbe     short loc_1800FD575
0x1800fd572  mov     rax, [rax]
0x1800fd575  cmp     cs:qword_180182A98, r15
0x1800fd57c  lea     rdx, ?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800fd583  mov     r8, rax
0x1800fd586  mov     rcx, rdi
0x1800fd589  cmova   rdx, cs:?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800fd591  mov     rax, rbx
0x1800fd594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd599  test    eax, eax
0x1800fd59b  jns     loc_1800FD629
0x1800fd5a1  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800fd5a8  mov     r8d, 79Eh
0x1800fd5ae  jmp     short loc_1800FD61A
0x1800fd5b0  mov     rax, [rsi]
0x1800fd5b3  mov     rax, [rax+50h]
0x1800fd5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd5bc  cmp     qword ptr [rax+10h], 0
0x1800fd5c1  jz      short loc_1800FD629
0x1800fd5c3  mov     rax, [rdi]
0x1800fd5c6  mov     rcx, rsi
0x1800fd5c9  mov     rbx, [rax+88h]
0x1800fd5d0  mov     rax, [rsi]
0x1800fd5d3  mov     rax, [rax+50h]
0x1800fd5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd5dc  cmp     [rax+18h], r15
0x1800fd5e0  jbe     short loc_1800FD5E5
0x1800fd5e2  mov     rax, [rax]
0x1800fd5e5  cmp     cs:qword_180182A98, r15
0x1800fd5ec  lea     rdx, ?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800fd5f3  mov     r8, rax
0x1800fd5f6  mov     rcx, rdi
0x1800fd5f9  cmova   rdx, cs:?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x1800fd601  mov     rax, rbx
0x1800fd604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd609  test    eax, eax
0x1800fd60b  jns     short loc_1800FD629
0x1800fd60d  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800fd614  mov     r8d, 7AAh
0x1800fd61a  mov     rdx, r13
0x1800fd61d  mov     [rsp+68h+var_48], eax
0x1800fd621  mov     ecx, r14d
0x1800fd624  call    AslLogCallPrintf
0x1800fd629  mov     rax, [rdi]
0x1800fd62c  mov     rcx, rsi
0x1800fd62f  mov     rbx, [rax+88h]
0x1800fd636  mov     rax, [rsi]
0x1800fd639  mov     rax, [rax+8]
0x1800fd63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd642  cmp     [rax+18h], r15
0x1800fd646  jbe     short loc_1800FD64B
0x1800fd648  mov     rax, [rax]
0x1800fd64b  cmp     cs:qword_180182AB8, r15
0x1800fd652  lea     rdx, ?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x1800fd659  mov     r8, rax
0x1800fd65c  mov     rcx, rdi
0x1800fd65f  cmova   rdx, cs:?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x1800fd667  mov     rax, rbx
0x1800fd66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd66f  mov     ebx, eax
0x1800fd671  test    eax, eax
0x1800fd673  jns     short loc_1800FD6B0
0x1800fd675  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800fd67c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800fd681  mov     [rsp+68h+var_48], ebx
0x1800fd685  mov     rdx, r13
0x1800fd688  mov     ecx, r14d
0x1800fd68b  test    al, al
0x1800fd68d  jz      short loc_1800FD69E
0x1800fd68f  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800fd696  mov     r8d, 7B4h
0x1800fd69c  jmp     short loc_1800FD6AB
0x1800fd69e  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800fd6a5  mov     r8d, 7B8h
0x1800fd6ab  call    AslLogCallPrintf
0x1800fd6b0  mov     rax, [rdi]
0x1800fd6b3  mov     rcx, rsi
0x1800fd6b6  mov     rbx, [rax+88h]
0x1800fd6bd  mov     rax, [rsi]
0x1800fd6c0  mov     rax, [rax+20h]
0x1800fd6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd6c9  cmp     [rax+18h], r15
0x1800fd6cd  jbe     short loc_1800FD6D2
0x1800fd6cf  mov     rax, [rax]
0x1800fd6d2  cmp     cs:qword_180182AD8, r15
0x1800fd6d9  lea     rdx, ?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x1800fd6e0  mov     r8, rax
0x1800fd6e3  mov     rcx, rdi
0x1800fd6e6  cmova   rdx, cs:?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x1800fd6ee  mov     rax, rbx
0x1800fd6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd6f6  mov     ebx, eax
0x1800fd6f8  test    eax, eax
0x1800fd6fa  jns     short loc_1800FD737
0x1800fd6fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800fd703  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800fd708  mov     [rsp+68h+var_48], ebx
0x1800fd70c  mov     rdx, r13
0x1800fd70f  mov     ecx, r14d
0x1800fd712  test    al, al
0x1800fd714  jz      short loc_1800FD725
0x1800fd716  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800fd71d  mov     r8d, 7C1h
0x1800fd723  jmp     short loc_1800FD732
0x1800fd725  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800fd72c  mov     r8d, 7C5h
0x1800fd732  call    AslLogCallPrintf
0x1800fd737  mov     rax, [rdi]
0x1800fd73a  mov     rcx, rsi
0x1800fd73d  mov     rbx, [rax+88h]
0x1800fd744  mov     rax, [rsi]
0x1800fd747  mov     rax, [rax+18h]
0x1800fd74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd750  cmp     [rax+18h], r15
0x1800fd754  jbe     short loc_1800FD759
0x1800fd756  mov     rax, [rax]
0x1800fd759  cmp     cs:qword_180182AF8, r15
0x1800fd760  lea     rdx, ?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x1800fd767  mov     r8, rax
0x1800fd76a  mov     rcx, rdi
0x1800fd76d  cmova   rdx, cs:?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x1800fd775  mov     rax, rbx
0x1800fd778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd77d  mov     ebx, eax
0x1800fd77f  test    eax, eax
0x1800fd781  jns     short loc_1800FD7BE
0x1800fd783  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800fd78a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800fd78f  mov     [rsp+68h+var_48], ebx
0x1800fd793  mov     rdx, r13
0x1800fd796  mov     ecx, r14d
0x1800fd799  test    al, al
0x1800fd79b  jz      short loc_1800FD7AC
0x1800fd79d  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800fd7a4  mov     r8d, 7CEh
0x1800fd7aa  jmp     short loc_1800FD7B9
0x1800fd7ac  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800fd7b3  mov     r8d, 7D2h
0x1800fd7b9  call    AslLogCallPrintf
0x1800fd7be  mov     rax, [rdi]
0x1800fd7c1  mov     rcx, rsi
0x1800fd7c4  mov     rbx, [rax+98h]
0x1800fd7cb  mov     rax, [rsi]
0x1800fd7ce  mov     rax, [rax+78h]
0x1800fd7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd7d7  cmp     cs:qword_180182B18, r15
0x1800fd7de  lea     rdx, ?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x1800fd7e5  mov     r8d, eax
0x1800fd7e8  mov     rcx, rdi
0x1800fd7eb  cmova   rdx, cs:?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x1800fd7f3  mov     rax, rbx
0x1800fd7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd7fb  mov     ebx, eax
0x1800fd7fd  test    eax, eax
0x1800fd7ff  jns     short loc_1800FD83C
0x1800fd801  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800fd808  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800fd80d  mov     [rsp+68h+var_48], ebx
0x1800fd811  mov     rdx, r13
0x1800fd814  mov     ecx, r14d
0x1800fd817  test    al, al
0x1800fd819  jz      short loc_1800FD82A
0x1800fd81b  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800fd822  mov     r8d, 7DBh
0x1800fd828  jmp     short loc_1800FD837
0x1800fd82a  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800fd831  mov     r8d, 7DFh
0x1800fd837  call    AslLogCallPrintf
0x1800fd83c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800fd843  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800fd848  mov     rcx, rsi
0x1800fd84b  test    al, al
0x1800fd84d  jz      short loc_1800FD8A9
0x1800fd84f  mov     rax, [rdi]
0x1800fd852  mov     rbx, [rax+88h]
0x1800fd859  mov     rax, [rsi]
0x1800fd85c  mov     rax, [rax+38h]
0x1800fd860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd865  cmp     [rax+18h], r15
0x1800fd869  jbe     short loc_1800FD86E
0x1800fd86b  mov     rax, [rax]
0x1800fd86e  cmp     cs:qword_180182C18, r15
0x1800fd875  lea     rdx, ?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800fd87c  mov     r8, rax
0x1800fd87f  mov     rcx, rdi
0x1800fd882  cmova   rdx, cs:?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800fd88a  mov     rax, rbx
0x1800fd88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd892  test    eax, eax
0x1800fd894  jns     loc_1800FD922
0x1800fd89a  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetItemProperty faile"...
0x1800fd8a1  mov     r8d, 7E8h
0x1800fd8a7  jmp     short loc_1800FD913
0x1800fd8a9  mov     rax, [rsi]
0x1800fd8ac  mov     rax, [rax+38h]
0x1800fd8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd8b5  cmp     qword ptr [rax+10h], 0
0x1800fd8ba  jz      short loc_1800FD922
0x1800fd8bc  mov     rax, [rdi]
0x1800fd8bf  mov     rcx, rsi
0x1800fd8c2  mov     rbx, [rax+88h]
0x1800fd8c9  mov     rax, [rsi]
0x1800fd8cc  mov     rax, [rax+38h]
0x1800fd8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd8d5  cmp     [rax+18h], r15
0x1800fd8d9  jbe     short loc_1800FD8DE
0x1800fd8db  mov     rax, [rax]
0x1800fd8de  cmp     cs:qword_180182C18, r15
0x1800fd8e5  lea     rdx, ?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800fd8ec  mov     r8, rax
0x1800fd8ef  mov     rcx, rdi
0x1800fd8f2  cmova   rdx, cs:?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x1800fd8fa  mov     rax, rbx
0x1800fd8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd902  test    eax, eax
0x1800fd904  jns     short loc_1800FD922
0x1800fd906  lea     r9, aTelcacheprovid_5; "TelCacheProvider::SetItemProperty faile"...
0x1800fd90d  mov     r8d, 7F3h
0x1800fd913  mov     rdx, r13
0x1800fd916  mov     [rsp+68h+var_48], eax
0x1800fd91a  mov     ecx, r14d
0x1800fd91d  call    AslLogCallPrintf
0x1800fd922  mov     rax, [rdi]
0x1800fd925  mov     rcx, rsi
0x1800fd928  mov     rbx, [rax+88h]
0x1800fd92f  mov     rax, [rsi]
0x1800fd932  mov     rax, [rax+40h]
0x1800fd936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd93b  cmp     [rax+18h], r15
0x1800fd93f  jbe     short loc_1800FD944
0x1800fd941  mov     rax, [rax]
0x1800fd944  cmp     cs:qword_180182B38, r15
0x1800fd94b  lea     rdx, ?InventoryItemValueNameSource@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameSource
0x1800fd952  mov     r8, rax
0x1800fd955  mov     rcx, rdi
0x1800fd958  cmova   rdx, cs:?InventoryItemValueNameSource@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameSource
0x1800fd960  mov     rax, rbx
0x1800fd963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd968  mov     ebx, eax
0x1800fd96a  test    eax, eax
0x1800fd96c  jns     short loc_1800FD9A9
0x1800fd96e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800fd975  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
  ... truncated ...
```
