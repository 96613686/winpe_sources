# Application::Retrieve(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x18003e760`
- end: `0x1800402ff`
- name: `?Retrieve@Application@@UEAAKPEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `7071`
- prototype: `unsigned int __fastcall(Application *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800373b0`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18000712e`
- `0x18000fb60`
- `0x180010640`
- `0x180011fcc`
- `0x1800134b8`
- `0x180014a48`
- `0x18002756c`
- `0x18002772c`
- `0x18002b0b8`
- `0x180032ab8`
- `0x180032c60`
- `0x1800371c4`
- `0x18003e760`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003f762`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040044`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003f762`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040044`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003ecb6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003ecb6`

## string_xrefs

- `0x18003e849`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003e946`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003e9f3`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003eaa9`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003eb5f`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003ebce`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003ecc7`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003ed56`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003ee0e`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003eefe`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003efbd`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f0ab`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f1a6`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f314`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f3cc`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f431`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f4e9`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f5fe`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f6bf`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f77a`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003f834`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003fa07`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003fad3`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003fb8f`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003fbf2`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003fca8`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003fd5e`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003fee4`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18003ffa3`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040063`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18004016d`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040229`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800402c0`: `TelCacheProvider::GetItemProperty failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Application::Retrieve(Application *this, struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  __int64 *v4; // rdx
  int v5; // eax
  __int64 v6; // r8
  unsigned __int64 v7; // r14
  char **v8; // rcx
  unsigned __int64 v9; // rdx
  char *v10; // rdi
  __int64 v11; // rbx
  __int64 *v12; // rdx
  int v13; // ebx
  __int64 v14; // r8
  char *v15; // rcx
  unsigned __int64 v16; // rdx
  char *v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // r8
  __int64 *v20; // rdx
  int v21; // eax
  __int64 v22; // r8
  char **v23; // rcx
  unsigned __int64 v24; // rdx
  char *v25; // rdi
  __int64 v26; // rbx
  __int64 *v27; // rdx
  int v28; // eax
  __int64 v29; // r8
  char **v30; // rcx
  unsigned __int64 v31; // rdx
  char *v32; // rdi
  __int64 v33; // rbx
  __int64 *v34; // rdx
  int v35; // eax
  __int64 v36; // r8
  char **v37; // rcx
  unsigned __int64 v38; // rdx
  char *v39; // rdi
  __int64 v40; // rbx
  __int64 *v41; // rbx
  __int64 *v42; // rdx
  int v43; // edi
  unsigned __int8 IsEnabled; // al
  __int64 *v45; // rdx
  int v46; // ebx
  __int64 v47; // r8
  char *v48; // rcx
  unsigned __int64 v49; // rdx
  char *v50; // rdi
  int v51; // eax
  __int64 v52; // rbx
  __int64 v53; // r8
  __int64 *v54; // rdx
  int v55; // ebx
  __int64 v56; // r8
  char *v57; // rcx
  unsigned __int64 v58; // rdx
  char *v59; // rdi
  __int64 v60; // rbx
  __int64 *v61; // rdx
  int v62; // eax
  __int64 v63; // r8
  char **v64; // rcx
  unsigned __int64 v65; // rdx
  char *v66; // rdi
  __int64 v67; // rbx
  __int64 *v68; // rdx
  int v69; // eax
  __int64 v70; // r8
  const wchar_t *v71; // r12
  unsigned __int64 v72; // rdx
  wchar_t *v73; // rdi
  __int64 v74; // rbx
  unsigned __int8 v75; // al
  char *v76; // rcx
  __int64 *v77; // rdx
  int v78; // eax
  __int64 v79; // r8
  __int64 v80; // rcx
  __int64 *v81; // rdx
  __int64 *v82; // rdx
  int v83; // ebx
  unsigned __int64 v84; // r8
  __int64 v85; // rbx
  __int64 v86; // rdi
  unsigned __int64 v87; // r8
  __int64 v88; // rbx
  __int64 v89; // rdi
  __int64 *v90; // rdx
  int v91; // eax
  __int64 v92; // r8
  char **v93; // rcx
  unsigned __int64 v94; // rdx
  char *v95; // rdi
  __int64 v96; // rbx
  __int64 *v97; // rdx
  int v98; // eax
  __int64 v99; // r8
  char **v100; // rcx
  unsigned __int64 v101; // rdx
  char *v102; // rdi
  __int64 v103; // rbx
  __int64 *v104; // rdx
  int v105; // eax
  __int64 *v106; // rdx
  int v107; // eax
  __int64 v108; // r8
  char **v109; // rcx
  unsigned __int64 v110; // rdx
  char *v111; // rdi
  __int64 v112; // rbx
  size_t *v113; // rsi
  size_t v114; // r8
  const wchar_t *v115; // rdx
  const wchar_t *v116; // rcx
  __int64 *v117; // rdx
  int v118; // eax
  __int64 v119; // r8
  char **v120; // rcx
  unsigned __int64 v121; // rdx
  char *v122; // rdi
  __int64 v123; // rbx
  __int64 *v124; // rdx
  int v125; // eax
  __int64 v126; // r8
  char **v127; // rcx
  unsigned __int64 v128; // rdx
  char *v129; // rdi
  __int64 v130; // rbx
  __int64 *v131; // rbx
  __int64 *v132; // rdx
  bool v133; // al
  int v134; // eax
  __int64 *v135; // rdx
  int v136; // eax
  __int64 v137; // r8
  char **v138; // rcx
  unsigned __int64 v139; // rdx
  char *v140; // rdi
  __int64 v141; // rbx
  __int64 *v142; // rdx
  int v143; // eax
  __int64 v144; // r8
  char *v145; // rcx
  unsigned __int64 v146; // rdx
  char *v147; // rdi
  __int64 v148; // rbx
  __int64 v149; // r8
  size_t v150; // r8
  const wchar_t *v151; // rdx
  const wchar_t *v152; // rcx
  const wchar_t *v153; // rdx
  size_t v154; // r8
  const wchar_t *v155; // rcx
  __int64 *v156; // rdx
  __int64 *v157; // rdx
  int v158; // eax
  __int64 v159; // r8
  char **v160; // rcx
  unsigned __int64 v161; // rdx
  char *v162; // rdi
  __int64 v163; // rbx
  __int64 *v164; // rdx
  int v165; // eax
  __int64 v166; // r8
  char **v167; // rcx
  unsigned __int64 v168; // rdx
  char *v169; // rdi
  __int64 v170; // rbx
  __int64 *v171; // rdx
  int v172; // eax
  __int64 *v173; // rdx
  int v174; // eax
  __int64 v175; // r8
  char **v176; // rcx
  unsigned __int64 v177; // rdx
  char *v178; // rdi
  __int64 v179; // rbx
  __int64 *v180; // rdx
  int v181; // eax
  __int64 v182; // r8
  char **v183; // rcx
  unsigned __int64 v184; // rdx
  char *v185; // rdi
  __int64 v186; // rbx
  __int64 *v187; // rdx
  int v188; // eax
  __int64 v189; // r8
  char *v190; // rcx
  void *v191; // rdi
  __int64 v192; // r8
  __int64 *v193; // rdx
  int v194; // eax
  __int64 v195; // r8
  char **v196; // rcx
  unsigned __int64 v197; // rdx
  char *v198; // rdi
  __int64 v199; // rbx
  __int64 *v200; // rdx
  int v201; // eax
  __int64 v202; // r8
  char **v203; // rcx
  unsigned __int64 v204; // rdx
  char *v205; // rdi
  __int64 v206; // rbx
  __int64 *v207; // rbx
  __int64 *v208; // rdx
  bool v209; // al
  int v210; // eax
  const wchar_t *v211; // rdx
  size_t v212; // r8
  __int64 *v213; // rdx
  int v214; // eax
  __int64 v215; // r8
  char **v216; // rcx
  unsigned __int64 v217; // rdx
  char *v218; // rdi
  __int64 v219; // rbx
  __int64 *v220; // rdx
  int v221; // eax
  __int64 v222; // r8
  char **v223; // rcx
  unsigned __int64 v224; // rdx
  char *v225; // rdi
  __int64 v226; // rbx
  __int64 *v227; // rdx
  int v229; // [rsp+30h] [rbp-D0h] BYREF
  int v230; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v231; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v232; // [rsp+40h] [rbp-C0h]
  __int128 v233; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v234; // [rsp+60h] [rbp-A0h]
  _WORD Src[520]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(Src, 0, sizeof(Src));
  v229 = 520;
  v4 = &Application::InventoryItemValueNameProgramId;
  if ( (unsigned __int64)qword_18011B3A8 > 7 )
    v4 = (__int64 *)Application::InventoryItemValueNameProgramId;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         v4,
         Src,
         &v229);
  v7 = -1;
  if ( v5 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2334, "TelCacheProvider::GetItemProperty failed [%#x]", v5);
  }
  else
  {
    v8 = (char **)((char *)this + 56);
    v9 = -1;
    do
      ++v9;
    while ( Src[v9] );
    if ( v9 > *((_QWORD *)this + 10) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v8, v9, v6, Src);
    }
    else
    {
      if ( *((_QWORD *)this + 10) <= 7u )
        v10 = (char *)this + 56;
      else
        v10 = *v8;
      *((_QWORD *)this + 9) = v9;
      v11 = 2 * v9;
      memmove_0(v10, Src, 2 * v9);
      *(_WORD *)&v10[v11] = 0;
    }
  }
  v229 = 520;
  v12 = &Application::InventoryItemValueNameProgramInstanceId;
  if ( (unsigned __int64)qword_18011B3C8 > 7 )
    v12 = (__int64 *)Application::InventoryItemValueNameProgramInstanceId;
  v13 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v12,
          Src,
          &v229);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v13 >= 0 )
    {
      v15 = (char *)this + 400;
      v16 = -1;
      do
        ++v16;
      while ( Src[v16] );
      goto LABEL_19;
    }
    v19 = 2349;
LABEL_32:
    AslLogCallPrintf(1, "Application::Retrieve", v19, "TelCacheProvider::GetItemProperty failed [%#x]", v13);
    goto LABEL_33;
  }
  if ( v13 < 0 )
  {
    if ( v13 == -2147024894 )
      goto LABEL_33;
    v19 = 2361;
    goto LABEL_32;
  }
  v15 = (char *)this + 400;
  v16 = -1;
  do
    ++v16;
  while ( Src[v16] );
LABEL_19:
  if ( v16 > *((_QWORD *)v15 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v15, v16, v14, Src);
  }
  else
  {
    if ( *((_QWORD *)v15 + 3) <= 7u )
      v17 = v15;
    else
      v17 = *(char **)v15;
    *((_QWORD *)v15 + 2) = v16;
    v18 = 2 * v16;
    memmove_0(v17, Src, 2 * v16);
    *(_WORD *)&v17[v18] = 0;
  }
LABEL_33:
  v229 = 520;
  v20 = &Application::InventoryItemValueNameName;
  if ( (unsigned __int64)qword_18011B3E8 > 7 )
    v20 = (__int64 *)Application::InventoryItemValueNameName;
  v21 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v20,
          Src,
          &v229);
  if ( v21 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2376, "TelCacheProvider::GetItemProperty failed [%#x]", v21);
  }
  else
  {
    v23 = (char **)((char *)this + 96);
    v24 = -1;
    do
      ++v24;
    while ( Src[v24] );
    if ( v24 > *((_QWORD *)this + 15) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v23,
        v24,
        v22,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 15) <= 7u )
        v25 = (char *)this + 96;
      else
        v25 = *v23;
      *((_QWORD *)this + 14) = v24;
      v26 = 2 * v24;
      memmove_0(v25, Src, 2 * v24);
      *(_WORD *)&v25[v26] = 0;
    }
  }
  v229 = 520;
  v27 = &Application::InventoryItemValueNameVersion;
  if ( (unsigned __int64)qword_18011B408 > 7 )
    v27 = (__int64 *)Application::InventoryItemValueNameVersion;
  v28 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v27,
          Src,
          &v229);
  if ( v28 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2390, "TelCacheProvider::GetItemProperty failed [%#x]", v28);
  }
  else
  {
    v30 = (char **)((char *)this + 160);
    v31 = -1;
    do
      ++v31;
    while ( Src[v31] );
    if ( v31 > *((_QWORD *)this + 23) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v30,
        v31,
        v29,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 23) <= 7u )
        v32 = (char *)this + 160;
      else
        v32 = *v30;
      *((_QWORD *)this + 22) = v31;
      v33 = 2 * v31;
      memmove_0(v32, Src, 2 * v31);
      *(_WORD *)&v32[v33] = 0;
    }
  }
  v229 = 520;
  v34 = &Application::InventoryItemValueNamePublisher;
  if ( (unsigned __int64)qword_18011B428 > 7 )
    v34 = (__int64 *)Application::InventoryItemValueNamePublisher;
  v35 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v34,
          Src,
          &v229);
  if ( v35 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2404, "TelCacheProvider::GetItemProperty failed [%#x]", v35);
  }
  else
  {
    v37 = (char **)((char *)this + 128);
    v38 = -1;
    do
      ++v38;
    while ( Src[v38] );
    if ( v38 > *((_QWORD *)this + 19) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v37,
        v38,
        v36,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 19) <= 7u )
        v39 = (char *)this + 128;
      else
        v39 = *v37;
      *((_QWORD *)this + 18) = v38;
      v40 = 2 * v38;
      memmove_0(v39, Src, 2 * v38);
      *(_WORD *)&v39[v40] = 0;
    }
  }
  v41 = &Application::InventoryItemValueNameLanguage;
  v42 = &Application::InventoryItemValueNameLanguage;
  if ( (unsigned __int64)qword_18011B448 > 7 )
    v42 = (__int64 *)Application::InventoryItemValueNameLanguage;
  v43 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 80LL))(
          a2,
          v42,
          (char *)this + 464);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl);
  if ( v43 < 0 )
  {
    if ( IsEnabled )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2413, "TelCacheProvider::GetItemProperty failed [%#x]", v43);
    }
    else
    {
      v229 = 520;
      if ( (unsigned __int64)qword_18011B448 > 7 )
        v41 = (__int64 *)Application::InventoryItemValueNameLanguage;
      v51 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
              a2,
              v41,
              Src,
              &v229);
      if ( v51 < 0 )
        AslLogCallPrintf(1, "Application::Retrieve", 2430, "TelCacheProvider::GetItemProperty failed [%#x]", v51);
      else
        *((_DWORD *)this + 116) = _o__wtoi(Src);
    }
  }
  v229 = 520;
  v45 = &Application::InventoryItemValueNameInstallDate;
  if ( (unsigned __int64)qword_18011B548 > 7 )
    v45 = (__int64 *)Application::InventoryItemValueNameInstallDate;
  v46 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v45,
          Src,
          &v229);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v46 >= 0 )
    {
      v48 = (char *)this + 256;
      v49 = -1;
      do
        ++v49;
      while ( Src[v49] );
      goto LABEL_80;
    }
    v53 = 2447;
LABEL_98:
    AslLogCallPrintf(1, "Application::Retrieve", v53, "TelCacheProvider::GetItemProperty failed [%#x]", v46);
    goto LABEL_99;
  }
  if ( v46 < 0 )
  {
    if ( v46 == -2147024894 )
      goto LABEL_99;
    v53 = 2459;
    goto LABEL_98;
  }
  v48 = (char *)this + 256;
  v49 = -1;
  do
    ++v49;
  while ( Src[v49] );
LABEL_80:
  if ( v49 > *((_QWORD *)v48 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v48, v49, v47, Src);
  }
  else
  {
    if ( *((_QWORD *)v48 + 3) <= 7u )
      v50 = v48;
    else
      v50 = *(char **)v48;
    *((_QWORD *)v48 + 2) = v49;
    v52 = 2 * v49;
    memmove_0(v50, Src, 2 * v49);
    *(_WORD *)&v50[v52] = 0;
  }
LABEL_99:
  v229 = 520;
  v54 = &Application::InventoryItemValueNameAppType;
  if ( (unsigned __int64)qword_18011B648 > 7 )
    v54 = (__int64 *)Application::InventoryItemValueNameAppType;
  v55 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v54,
          Src,
          &v229);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v55 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2475, "TelCacheProvider::GetItemProperty failed [%#x]", v55);
      goto LABEL_117;
    }
    v57 = (char *)this + 368;
    v58 = -1;
    do
      ++v58;
    while ( Src[v58] );
  }
  else
  {
    v57 = (char *)this + 368;
    if ( v55 < 0 )
    {
      std::wstring::operator=(v57, Application::ApplicationTypeApplication);
      goto LABEL_117;
    }
    v58 = -1;
    do
      ++v58;
    while ( Src[v58] );
  }
  if ( v58 > *((_QWORD *)v57 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v57, v58, v56, Src);
  }
  else
  {
    if ( *((_QWORD *)v57 + 3) <= 7u )
      v59 = v57;
    else
      v59 = *(char **)v57;
    *((_QWORD *)v57 + 2) = v58;
    v60 = 2 * v58;
    memmove_0(v59, Src, 2 * v58);
    *(_WORD *)&v59[v60] = 0;
  }
LABEL_117:
  v229 = 520;
  v61 = &Application::InventoryItemValueNameRootDirPath;
  if ( (unsigned __int64)qword_18011B5C8 > 7 )
    v61 = (__int64 *)Application::InventoryItemValueNameRootDirPath;
  v62 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v61,
          Src,
          &v229);
  if ( v62 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2502, "TelCacheProvider::GetItemProperty failed [%#x]", v62);
  }
  else
  {
    v64 = (char **)((char *)this + 192);
    v65 = -1;
    do
      ++v65;
    while ( Src[v65] );
    if ( v65 > *((_QWORD *)this + 27) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v64,
        v65,
        v63,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 27) <= 7u )
        v66 = (char *)this + 192;
      else
        v66 = *v64;
      *((_QWORD *)this + 26) = v65;
      v67 = 2 * v65;
      memmove_0(v66, Src, 2 * v65);
      *(_WORD *)&v66[v67] = 0;
    }
  }
  v229 = 520;
  v68 = &Application::InventoryItemValueNameSource;
  if ( (unsigned __int64)qword_18011B468 > 7 )
    v68 = (__int64 *)Application::InventoryItemValueNameSource;
  v69 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v68,
          Src,
          &v229);
  v71 = (const wchar_t *)((char *)this + 336);
  if ( v69 < 0 )
  {
    AslLogCallPrintf(1, "Application::Retrieve", 2516, "TelCacheProvider::GetItemProperty failed [%#x]", v69);
  }
  else
  {
    v72 = -1;
    do
      ++v72;
    while ( Src[v72] );
    if ( v72 > *((_QWORD *)this + 45) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char *)this + 336,
        v72,
        v70,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 45) <= 7u )
        v73 = (wchar_t *)((char *)this + 336);
      else
        v73 = *(wchar_t **)v71;
      *((_QWORD *)this + 44) = v72;
      v74 = v72;
      memmove_0(v73, Src, 2 * v72);
      v73[v74] = 0;
    }
  }
  v75 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl);
  v76 = (char *)this + 336;
  if ( v75 )
  {
    if ( !(unsigned __int8)std::operator!=<unsigned short>(v76, &Application::ApplicationSourceAppxPackage) )
    {
      *((_BYTE *)this + 88) = 0;
      goto LABEL_156;
    }
    v230 = 0;
    v77 = &Application::InventoryItemValueNameSentDetailedInv;
    if ( (unsigned __int64)qword_18011B628 > 7 )
      v77 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
    v78 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
            a2,
            v77,
            &v230);
    if ( v78 < 0 )
    {
      *((_BYTE *)this + 88) = 0;
      v79 = 2532;
      v80 = 3;
      goto LABEL_155;
    }
LABEL_152:
    *((_BYTE *)this + 88) = v230 != 0;
    goto LABEL_156;
  }
  if ( !(unsigned __int8)std::operator!=<unsigned short>(v76, &Application::ApplicationSourceAppxPackage) )
    goto LABEL_156;
  v230 = 0;
  v81 = &Application::InventoryItemValueNameSentDetailedInv;
  if ( (unsigned __int64)qword_18011B628 > 7 )
    v81 = (__int64 *)Application::InventoryItemValueNameSentDetailedInv;
  v78 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
          a2,
          v81,
          &v230);
  if ( v78 >= 0 )
    goto LABEL_152;
  *((_BYTE *)this + 88) = 0;
  if ( v78 == -2147024894 )
    goto LABEL_156;
  v79 = 2557;
  v80 = 1;
LABEL_155:
  AslLogCallPrintf(v80, "Application::Retrieve", v79, "TelCacheProvider::GetItemProperty failed [%#x]", v78);
LABEL_156:
  v229 = 520;
  v82 = &Application::InventoryItemValueNameUserSid;
  if ( (unsigned __int64)qword_18011B668 > 7 )
    v82 = (__int64 *)Application::InventoryItemValueNameUserSid;
  v83 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          v82,
          Src,
          &v229);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v83 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2579, "TelCacheProvider::GetItemProperty failed [%#x]", v83);
      goto LABEL_174;
    }
    v233 = 0;
    v234 = 0;
    v84 = -1;
    do
      ++v84;
    while ( Src[v84] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v233, Src, v84);
    WstringContainerFromDelimitedString<std::vector<std::wstring>>(&v231, &v233);
    std::wstring::~wstring((char **)&v233);
    v85 = v231;
    v86 = v232;
    while ( v85 != v86 )
    {
      std::wstring::wstring((__int64)&v233, v85);
      Application::AddUserSid(this, (__int64)&v233);
      std::wstring::~wstring((char **)&v233);
      v85 += 32;
    }
  }
  else
  {
    if ( v83 < 0 )
      goto LABEL_174;
    v233 = 0;
    v234 = 0;
    v87 = -1;
    do
      ++v87;
    while ( Src[v87] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v233, Src, v87);
    WstringContainerFromDelimitedString<std::vector<std::wstring>>(&v231, &v233);
    std::wstring::~wstring((char **)&v233);
    v88 = v231;
    v89 = v232;
    while ( v88 != v89 )
    {
      std::wstring::wstring((__int64)&v233, v88);
      Application::AddUserSid(this, (__int64)&v233);
      std::wstring::~wstring((char **)&v233);
      v88 += 32;
    }
  }
  std::vector<std::wstring>::_Tidy(&v231);
LABEL_174:
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v229 = 520;
    v90 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_18011B588 > 7 )
      v90 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v91 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v90,
            Src,
            &v229);
    if ( v91 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2605, "TelCacheProvider::GetItemProperty failed [%#x]", v91);
    }
    else
    {
      v93 = (char **)((char *)this + 904);
      v94 = -1;
      do
        ++v94;
      while ( Src[v94] );
      if ( v94 > *((_QWORD *)this + 116) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v93,
          v94,
          v92,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 116) <= 7u )
          v95 = (char *)this + 904;
        else
          v95 = *v93;
        *((_QWORD *)this + 115) = v94;
        v96 = 2 * v94;
        memmove_0(v95, Src, 2 * v94);
        *(_WORD *)&v95[v96] = 0;
      }
    }
    v229 = 520;
    v97 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_18011B5A8 > 7 )
      v97 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v98 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
            a2,
            v97,
            Src,
            &v229);
    if ( v98 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2616, "TelCacheProvider::GetItemProperty failed [%#x]", v98);
    }
    else
    {
      v100 = (char **)((char *)this + 936);
      v101 = -1;
      do
        ++v101;
      while ( Src[v101] );
      if ( v101 > *((_QWORD *)this + 120) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v100,
          v101,
          v99,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 120) <= 7u )
          v102 = (char *)this + 936;
        else
          v102 = *v100;
        *((_QWORD *)this + 119) = v101;
        v103 = 2 * v101;
        memmove_0(v102, Src, 2 * v101);
        *(_WORD *)&v102[v103] = 0;
      }
    }
    v230 = 0;
    v104 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_18011B528 > 7 )
      v104 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    v105 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
             a2,
             v104,
             &v230);
    if ( v105 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2627, "TelCacheProvider::GetItemProperty failed [%#x]", v105);
    else
      *((_BYTE *)this + 968) = v230 != 0;
    v229 = 520;
    v106 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_18011B488 > 7 )
      v106 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v107 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v106,
             Src,
             &v229);
    if ( v107 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2639, "TelCacheProvider::GetItemProperty failed [%#x]", v107);
    }
    else
    {
      v109 = (char **)((char *)this + 808);
      v110 = -1;
      do
        ++v110;
      while ( Src[v110] );
      if ( v110 > *((_QWORD *)this + 104) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v109,
          v110,
          v108,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 104) <= 7u )
          v111 = (char *)this + 808;
        else
          v111 = *v109;
        *((_QWORD *)this + 103) = v110;
        v112 = 2 * v110;
        memmove_0(v111, Src, 2 * v110);
        *(_WORD *)&v111[v112] = 0;
      }
    }
    v113 = (size_t *)((char *)this + 352);
    goto LABEL_271;
  }
  v113 = (size_t *)((char *)this + 352);
  v114 = *((_QWORD *)this + 44);
  if ( !v114 )
    goto LABEL_224;
  v115 = (const wchar_t *)&Application::ApplicationSourceAppxPackage;
  if ( (unsigned __int64)qword_18011B0A8 > 7 )
    v115 = Application::ApplicationSourceAppxPackage;
  v116 = (const wchar_t *)((char *)this + 336);
  if ( *((_QWORD *)this + 45) > 7u )
    v116 = *(const wchar_t **)v71;
  if ( v114 == qword_18011B0A0 && !wmemcmp(v116, v115, v114) )
  {
LABEL_224:
    v229 = 520;
    v117 = &Application::InventoryItemValueNameManifestPath;
    if ( (unsigned __int64)qword_18011B588 > 7 )
      v117 = (__int64 *)Application::InventoryItemValueNameManifestPath;
    v118 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v117,
             Src,
             &v229);
    if ( v118 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2656, "TelCacheProvider::GetItemProperty failed [%#x]", v118);
    }
    else
    {
      v120 = (char **)((char *)this + 904);
      v121 = -1;
      do
        ++v121;
      while ( Src[v121] );
      if ( v121 > *((_QWORD *)this + 116) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v120,
          v121,
          v119,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 116) <= 7u )
          v122 = (char *)this + 904;
        else
          v122 = *v120;
        *((_QWORD *)this + 115) = v121;
        v123 = 2 * v121;
        memmove_0(v122, Src, 2 * v121);
        *(_WORD *)&v122[v123] = 0;
      }
    }
    v229 = 520;
    v124 = &Application::InventoryItemValueNameBundleManifestPath;
    if ( (unsigned __int64)qword_18011B5A8 > 7 )
      v124 = (__int64 *)Application::InventoryItemValueNameBundleManifestPath;
    v125 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v124,
             Src,
             &v229);
    if ( v125 < 0 )
    {
      if ( v125 != -2147024894 )
        AslLogCallPrintf(1, "Application::Retrieve", 2668, "TelCacheProvider::GetItemProperty failed [%#x]", v125);
    }
    else
    {
      v127 = (char **)((char *)this + 936);
      v128 = -1;
      do
        ++v128;
      while ( Src[v128] );
      if ( v128 > *((_QWORD *)this + 120) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v127,
          v128,
          v126,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 120) <= 7u )
          v129 = (char *)this + 936;
        else
          v129 = *v127;
        *((_QWORD *)this + 119) = v128;
        v130 = 2 * v128;
        memmove_0(v129, Src, 2 * v128);
        *(_WORD *)&v129[v130] = 0;
      }
    }
    v230 = 0;
    v131 = &Application::InventoryItemValueNameInboxStoreApp;
    v132 = &Application::InventoryItemValueNameInboxStoreApp;
    if ( (unsigned __int64)qword_18011B528 > 7 )
      v132 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
    if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
           a2,
           v132,
           &v230) < 0 )
    {
      v229 = 520;
      if ( (unsigned __int64)qword_18011B528 > 7 )
        v131 = (__int64 *)Application::InventoryItemValueNameInboxStoreApp;
      v134 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
               a2,
               v131,
               Src,
               &v229);
      if ( v134 < 0 )
      {
        AslLogCallPrintf(1, "Application::Retrieve", 2696, "TelCacheProvider::GetItemProperty failed [%#x]", v134);
        goto LABEL_259;
      }
      v133 = (unsigned int)_o__wcsicmp(L"true", Src) == 0;
    }
    else
    {
      v133 = v230 != 0;
    }
    *((_BYTE *)this + 968) = v133;
LABEL_259:
    v229 = 520;
    v135 = &Application::InventoryItemValueNameStoreAppType;
    if ( (unsigned __int64)qword_18011B488 > 7 )
      v135 = (__int64 *)Application::InventoryItemValueNameStoreAppType;
    v136 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v135,
             Src,
             &v229);
    if ( v136 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2709, "TelCacheProvider::GetItemProperty failed [%#x]", v136);
    }
    else
    {
      v138 = (char **)((char *)this + 808);
      v139 = -1;
      do
        ++v139;
      while ( Src[v139] );
      if ( v139 > *((_QWORD *)this + 104) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v138,
          v139,
          v137,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 104) <= 7u )
          v140 = (char *)this + 808;
        else
          v140 = *v138;
        *((_QWORD *)this + 103) = v139;
        v141 = 2 * v139;
        memmove_0(v140, Src, 2 * v139);
        *(_WORD *)&v140[v141] = 0;
      }
    }
  }
LABEL_271:
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v229 = 520;
    v142 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_18011B568 > 7 )
      v142 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v143 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v142,
             Src,
             &v229);
    if ( v143 >= 0 )
    {
      v145 = (char *)this + 744;
      v146 = -1;
      do
        ++v146;
      while ( Src[v146] );
      goto LABEL_277;
    }
    v149 = 2725;
    goto LABEL_306;
  }
  v150 = *v113;
  if ( !*v113 )
    goto LABEL_298;
  v151 = (const wchar_t *)&Application::ApplicationSourceAppxPackage;
  if ( (unsigned __int64)qword_18011B0A8 > 7 )
    v151 = Application::ApplicationSourceAppxPackage;
  v152 = (const wchar_t *)((char *)this + 336);
  if ( *((_QWORD *)this + 45) > 7u )
    v152 = *(const wchar_t **)v71;
  if ( v150 == qword_18011B0A0 && !wmemcmp(v152, v151, v150) )
    goto LABEL_298;
  v153 = (const wchar_t *)&Application::ApplicationSourceAppvPackage;
  if ( (unsigned __int64)qword_18011B088 > 7 )
    v153 = Application::ApplicationSourceAppvPackage;
  v154 = *((_QWORD *)this + 44);
  v155 = *((_QWORD *)this + 45) <= 7u ? (const wchar_t *)((char *)this + 336) : *(const wchar_t **)v71;
  if ( v154 == qword_18011B080 && (!v154 || !wmemcmp(v155, v153, v154)) )
  {
LABEL_298:
    v229 = 520;
    v156 = &Application::InventoryItemValueNamePackageFullName;
    if ( (unsigned __int64)qword_18011B568 > 7 )
      v156 = (__int64 *)Application::InventoryItemValueNamePackageFullName;
    v143 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v156,
             Src,
             &v229);
    if ( v143 >= 0 )
    {
      v145 = (char *)this + 744;
      v146 = -1;
      do
        ++v146;
      while ( Src[v146] );
LABEL_277:
      if ( v146 > *((_QWORD *)v145 + 3) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v145,
          v146,
          v144,
          Src);
      }
      else
      {
        if ( *((_QWORD *)v145 + 3) <= 7u )
          v147 = v145;
        else
          v147 = *(char **)v145;
        *((_QWORD *)v145 + 2) = v146;
        v148 = 2 * v146;
        memmove_0(v147, Src, 2 * v146);
        *(_WORD *)&v147[v148] = 0;
      }
      goto LABEL_307;
    }
    v149 = 2742;
LABEL_306:
    AslLogCallPrintf(1, "Application::Retrieve", v149, "TelCacheProvider::GetItemProperty failed [%#x]", v143);
  }
LABEL_307:
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v229 = 520;
    v157 = &Application::InventoryItemValueNameUninstallString;
    if ( (unsigned __int64)qword_18011B5E8 > 7 )
      v157 = (__int64 *)Application::InventoryItemValueNameUninstallString;
    v158 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v157,
             Src,
             &v229);
    if ( v158 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2758, "TelCacheProvider::GetItemProperty failed [%#x]", v158);
    }
    else
    {
      v160 = (char **)((char *)this + 224);
      v161 = -1;
      do
        ++v161;
      while ( Src[v161] );
      if ( v161 > *((_QWORD *)this + 31) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v160,
          v161,
          v159,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 31) <= 7u )
          v162 = (char *)this + 224;
        else
          v162 = *v160;
        *((_QWORD *)this + 30) = v161;
        v163 = 2 * v161;
        memmove_0(v162, Src, 2 * v161);
        *(_WORD *)&v162[v163] = 0;
      }
    }
    v229 = 520;
    v164 = &Application::InventoryItemValueNameArpRegistryKeyPath;
    if ( (unsigned __int64)qword_18011B608 > 7 )
      v164 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
    v165 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v164,
             Src,
             &v229);
    if ( v165 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2769, "TelCacheProvider::GetItemProperty failed [%#x]", v165);
    }
    else
    {
      v167 = (char **)((char *)this + 432);
      v168 = -1;
      do
        ++v168;
      while ( Src[v168] );
      if ( v168 > *((_QWORD *)this + 57) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v167,
          v168,
          v166,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 57) <= 7u )
          v169 = (char *)this + 432;
        else
          v169 = *v167;
        *((_QWORD *)this + 56) = v168;
        v170 = 2 * v168;
        memmove_0(v169, Src, 2 * v168);
        *(_WORD *)&v169[v170] = 0;
      }
    }
    v230 = 0;
    v171 = &Application::InventoryItemValueNameHiddenArp;
    if ( (unsigned __int64)qword_18011B508 > 7 )
      v171 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
    v172 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
             a2,
             v171,
             &v230);
    if ( v172 < 0 )
      AslLogCallPrintf(1, "Application::Retrieve", 2780, "TelCacheProvider::GetItemProperty failed [%#x]", v172);
    else
      *((_BYTE *)this + 700) = v230 != 0;
    v229 = 520;
    v173 = &Application::InventoryItemValueNameMsiInstallDate;
    if ( (unsigned __int64)qword_18011B4E8 > 7 )
      v173 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
    v174 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v173,
             Src,
             &v229);
    if ( v174 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2791, "TelCacheProvider::GetItemProperty failed [%#x]", v174);
    }
    else
    {
      v176 = (char **)((char *)this + 568);
      v177 = -1;
      do
        ++v177;
      while ( Src[v177] );
      if ( v177 > *((_QWORD *)this + 74) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v176,
          v177,
          v175,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 74) <= 7u )
          v178 = (char *)this + 568;
        else
          v178 = *v176;
        *((_QWORD *)this + 73) = v177;
        v179 = 2 * v177;
        memmove_0(v178, Src, 2 * v177);
        *(_WORD *)&v178[v179] = 0;
      }
    }
    v229 = 520;
    v180 = &Application::InventoryItemValueNameMsiPackageCode;
    if ( (unsigned __int64)qword_18011B4C8 > 7 )
      v180 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
    v181 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v180,
             Src,
             &v229);
    if ( v181 < 0 )
    {
      AslLogCallPrintf(1, "Application::Retrieve", 2802, "TelCacheProvider::GetItemProperty failed [%#x]", v181);
    }
    else
    {
      v183 = (char **)((char *)this + 632);
      v184 = -1;
      do
        ++v184;
      while ( Src[v184] );
      if ( v184 > *((_QWORD *)this + 82) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v183,
          v184,
          v182,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 82) <= 7u )
          v185 = (char *)this + 632;
        else
          v185 = *v183;
        *((_QWORD *)this + 81) = v184;
        v186 = 2 * v184;
        memmove_0(v185, Src, 2 * v184);
        *(_WORD *)&v185[v186] = 0;
      }
    }
    v229 = 520;
    v187 = &Application::InventoryItemValueNameMsiProductCode;
    if ( (unsigned __int64)qword_18011B4A8 > 7 )
      v187 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
    v188 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v187,
             Src,
             &v229);
    if ( v188 >= 0 )
    {
      v190 = (char *)this + 600;
      do
        ++v7;
      while ( Src[v7] );
      goto LABEL_366;
    }
    v192 = 2813;
    goto LABEL_453;
  }
  if ( !(unsigned __int8)std::operator!=<unsigned short>((char *)this + 336, &Application::ApplicationSourceAppxPackage)
    || !(unsigned __int8)std::operator!=<unsigned short>((char *)this + 336, &Application::ApplicationSourceAppvPackage) )
  {
    return 0;
  }
  v229 = 520;
  v193 = &Application::InventoryItemValueNameUninstallString;
  if ( (unsigned __int64)qword_18011B5E8 > 7 )
    v193 = (__int64 *)Application::InventoryItemValueNameUninstallString;
  v194 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
           a2,
           v193,
           Src,
           &v229);
  if ( v194 < 0 )
  {
    if ( v194 != -2147024894 )
      AslLogCallPrintf(1, "Application::Retrieve", 2830, "TelCacheProvider::GetItemProperty failed [%#x]", v194);
  }
  else
  {
    v196 = (char **)((char *)this + 224);
    v197 = -1;
    do
      ++v197;
    while ( Src[v197] );
    if ( v197 > *((_QWORD *)this + 31) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v196,
        v197,
        v195,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 31) <= 7u )
        v198 = (char *)this + 224;
      else
        v198 = *v196;
      *((_QWORD *)this + 30) = v197;
      v199 = 2 * v197;
      memmove_0(v198, Src, 2 * v197);
      *(_WORD *)&v198[v199] = 0;
    }
  }
  v229 = 520;
  v200 = &Application::InventoryItemValueNameArpRegistryKeyPath;
  if ( (unsigned __int64)qword_18011B608 > 7 )
    v200 = (__int64 *)Application::InventoryItemValueNameArpRegistryKeyPath;
  v201 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
           a2,
           v200,
           Src,
           &v229);
  if ( v201 < 0 )
  {
    if ( v201 != -2147024894 )
      AslLogCallPrintf(1, "Application::Retrieve", 2842, "TelCacheProvider::GetItemProperty failed [%#x]", v201);
  }
  else
  {
    v203 = (char **)((char *)this + 432);
    v204 = -1;
    do
      ++v204;
    while ( Src[v204] );
    if ( v204 > *((_QWORD *)this + 57) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v203,
        v204,
        v202,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 57) <= 7u )
        v205 = (char *)this + 432;
      else
        v205 = *v203;
      *((_QWORD *)this + 56) = v204;
      v206 = 2 * v204;
      memmove_0(v205, Src, 2 * v204);
      *(_WORD *)&v205[v206] = 0;
    }
  }
  v230 = 0;
  v207 = &Application::InventoryItemValueNameHiddenArp;
  v208 = &Application::InventoryItemValueNameHiddenArp;
  if ( (unsigned __int64)qword_18011B508 > 7 )
    v208 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
  if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(*(_QWORD *)a2 + 80LL))(
         a2,
         v208,
         &v230) >= 0 )
  {
    v209 = v230 != 0;
LABEL_408:
    *((_BYTE *)this + 700) = v209;
    goto LABEL_411;
  }
  v229 = 520;
  if ( (unsigned __int64)qword_18011B508 > 7 )
    v207 = (__int64 *)Application::InventoryItemValueNameHiddenArp;
  v210 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
           a2,
           v207,
           Src,
           &v229);
  if ( v210 >= 0 )
  {
    v209 = (unsigned int)_o__wcsicmp(L"true", Src) == 0;
    goto LABEL_408;
  }
  if ( v210 != -2147024894 )
    AslLogCallPrintf(1, "Application::Retrieve", 2871, "TelCacheProvider::GetItemProperty failed [%#x]", v210);
LABEL_411:
  v211 = (const wchar_t *)&Application::ApplicationSourceMsi;
  if ( (unsigned __int64)qword_18011AF68 > 7 )
    v211 = Application::ApplicationSourceMsi;
  v212 = *((_QWORD *)this + 44);
  if ( *((_QWORD *)this + 45) > 7u )
    v71 = *(const wchar_t **)v71;
  if ( v212 == qword_18011AF60 && (!v212 || !wmemcmp(v71, v211, v212)) )
  {
    v229 = 520;
    v213 = &Application::InventoryItemValueNameMsiInstallDate;
    if ( (unsigned __int64)qword_18011B4E8 > 7 )
      v213 = (__int64 *)Application::InventoryItemValueNameMsiInstallDate;
    v214 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v213,
             Src,
             &v229);
    if ( v214 < 0 )
    {
      if ( v214 != -2147024894 )
        AslLogCallPrintf(1, "Application::Retrieve", 2886, "TelCacheProvider::GetItemProperty failed [%#x]", v214);
    }
    else
    {
      v216 = (char **)((char *)this + 568);
      v217 = -1;
      do
        ++v217;
      while ( Src[v217] );
      if ( v217 > *((_QWORD *)this + 74) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v216,
          v217,
          v215,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 74) <= 7u )
          v218 = (char *)this + 568;
        else
          v218 = *v216;
        *((_QWORD *)this + 73) = v217;
        v219 = 2 * v217;
        memmove_0(v218, Src, 2 * v217);
        *(_WORD *)&v218[v219] = 0;
      }
    }
    v229 = 520;
    v220 = &Application::InventoryItemValueNameMsiPackageCode;
    if ( (unsigned __int64)qword_18011B4C8 > 7 )
      v220 = (__int64 *)Application::InventoryItemValueNameMsiPackageCode;
    v221 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v220,
             Src,
             &v229);
    if ( v221 < 0 )
    {
      if ( v221 != -2147024894 )
        AslLogCallPrintf(1, "Application::Retrieve", 2897, "TelCacheProvider::GetItemProperty failed [%#x]", v221);
    }
    else
    {
      v223 = (char **)((char *)this + 632);
      v224 = -1;
      do
        ++v224;
      while ( Src[v224] );
      if ( v224 > *((_QWORD *)this + 82) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v223,
          v224,
          v222,
          Src);
      }
      else
      {
        if ( *((_QWORD *)this + 82) <= 7u )
          v225 = (char *)this + 632;
        else
          v225 = *v223;
        *((_QWORD *)this + 81) = v224;
        v226 = 2 * v224;
        memmove_0(v225, Src, 2 * v224);
        *(_WORD *)&v225[v226] = 0;
      }
    }
    v229 = 520;
    v227 = &Application::InventoryItemValueNameMsiProductCode;
    if ( (unsigned __int64)qword_18011B4A8 > 7 )
      v227 = (__int64 *)Application::InventoryItemValueNameMsiProductCode;
    v188 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, _WORD *, int *))(*(_QWORD *)a2 + 64LL))(
             a2,
             v227,
             Src,
             &v229);
    if ( v188 >= 0 )
    {
      v190 = (char *)this + 600;
      do
        ++v7;
      while ( Src[v7] );
LABEL_366:
      if ( v7 > *((_QWORD *)v190 + 3) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v190,
          v7,
          v189,
          Src);
      }
      else
      {
        if ( *((_QWORD *)v190 + 3) <= 7u )
          v191 = v190;
        else
          v191 = *(void **)v190;
        *((_QWORD *)v190 + 2) = v7;
        memmove_0(v191, Src, 2 * v7);
        *((_WORD *)v191 + v7) = 0;
      }
      return 0;
    }
    if ( v188 == -2147024894 )
      return 0;
    v192 = 2908;
LABEL_453:
    AslLogCallPrintf(1, "Application::Retrieve", v192, "TelCacheProvider::GetItemProperty failed [%#x]", v188);
  }
  return 0;
}

```

## disassembly

```asm
0x18003e760  mov     [rsp-8+arg_10], rbx
0x18003e765  push    rbp
0x18003e766  push    rsi
0x18003e767  push    rdi
0x18003e768  push    r12
0x18003e76a  push    r13
0x18003e76c  push    r14
0x18003e76e  push    r15
0x18003e770  lea     rbp, [rsp-390h]
0x18003e778  sub     rsp, 490h
0x18003e77f  mov     rax, cs:__security_cookie
0x18003e786  xor     rax, rsp
0x18003e789  mov     [rbp+3C0h+var_40], rax
0x18003e790  mov     r13, rdx
0x18003e793  mov     r15, rcx
0x18003e796  xor     r12d, r12d
0x18003e799  xor     edx, edx; Val
0x18003e79b  mov     r8d, 410h; Size
0x18003e7a1  lea     rcx, [rsp+4C0h+Src]; void *
0x18003e7a6  call    memset_0
0x18003e7ab  mov     [rsp+4C0h+var_490], 208h
0x18003e7b3  mov     rax, [r13+0]
0x18003e7b7  lea     rdx, ?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x18003e7be  lea     esi, [r12+7]
0x18003e7c3  cmp     cs:qword_18011B3A8, rsi
0x18003e7ca  cmova   rdx, cs:?InventoryItemValueNameProgramId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramId
0x18003e7d2  lea     r9, [rsp+4C0h+var_490]
0x18003e7d7  lea     r8, [rsp+4C0h+Src]
0x18003e7dc  mov     rcx, r13
0x18003e7df  mov     rax, [rax+40h]
0x18003e7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7e8  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003e7ec  test    eax, eax
0x18003e7ee  js      short loc_18003E845
0x18003e7f0  lea     rcx, [r15+38h]
0x18003e7f4  lea     rax, [rsp+4C0h+Src]
0x18003e7f9  mov     rdx, r14
0x18003e7fc  inc     rdx
0x18003e7ff  cmp     [rax+rdx*2], r12w
0x18003e804  jnz     short loc_18003E7FC
0x18003e806  cmp     rdx, [rcx+18h]
0x18003e80a  ja      short loc_18003E839
0x18003e80c  cmp     [rcx+18h], rsi
0x18003e810  jbe     short loc_18003E817
0x18003e812  mov     rdi, [rcx]
0x18003e815  jmp     short loc_18003E81A
0x18003e817  mov     rdi, rcx
0x18003e81a  mov     [rcx+10h], rdx
0x18003e81e  lea     rbx, [rdx+rdx]
0x18003e822  mov     r8, rbx; Size
0x18003e825  lea     rdx, [rsp+4C0h+Src]; Src
0x18003e82a  mov     rcx, rdi; void *
0x18003e82d  call    memmove_0
0x18003e832  mov     [rdi+rbx], r12w
0x18003e837  jmp     short loc_18003E867
0x18003e839  lea     r9, [rsp+4C0h+Src]
0x18003e83e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003e843  jmp     short loc_18003E867
0x18003e845  mov     [rsp+4C0h+var_4A0], eax
0x18003e849  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x18003e850  mov     r8d, 91Eh
0x18003e856  lea     rdx, aApplicationRet; "Application::Retrieve"
0x18003e85d  mov     ecx, 1
0x18003e862  call    AslLogCallPrintf
0x18003e867  mov     [rsp+4C0h+var_490], 208h
0x18003e86f  mov     rax, [r13+0]
0x18003e873  lea     rdx, ?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x18003e87a  cmp     cs:qword_18011B3C8, rsi
0x18003e881  cmova   rdx, cs:?InventoryItemValueNameProgramInstanceId@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameProgramInstanceId
0x18003e889  lea     r9, [rsp+4C0h+var_490]
0x18003e88e  lea     r8, [rsp+4C0h+Src]
0x18003e893  mov     rcx, r13
0x18003e896  mov     rax, [rax+40h]
0x18003e89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e89f  mov     ebx, eax
0x18003e8a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003e8a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003e8ad  test    al, al
0x18003e8af  jz      short loc_18003E909
0x18003e8b1  test    ebx, ebx
0x18003e8b3  js      short loc_18003E901
0x18003e8b5  lea     rcx, [r15+190h]
0x18003e8bc  lea     rax, [rsp+4C0h+Src]
0x18003e8c1  mov     rdx, r14
0x18003e8c4  inc     rdx
0x18003e8c7  cmp     [rax+rdx*2], r12w
0x18003e8cc  jnz     short loc_18003E8C4
0x18003e8ce  cmp     rdx, [rcx+18h]
0x18003e8d2  ja      short loc_18003E928
0x18003e8d4  cmp     [rcx+18h], rsi
0x18003e8d8  jbe     short loc_18003E8DF
0x18003e8da  mov     rdi, [rcx]
0x18003e8dd  jmp     short loc_18003E8E2
0x18003e8df  mov     rdi, rcx
0x18003e8e2  mov     [rcx+10h], rdx
0x18003e8e6  lea     rbx, [rdx+rdx]
0x18003e8ea  mov     r8, rbx; Size
0x18003e8ed  lea     rdx, [rsp+4C0h+Src]; Src
0x18003e8f2  mov     rcx, rdi; void *
0x18003e8f5  call    memmove_0
0x18003e8fa  mov     [rdi+rbx], r12w
0x18003e8ff  jmp     short loc_18003E95E
0x18003e901  mov     r8d, 92Dh
0x18003e907  jmp     short loc_18003E942
0x18003e909  test    ebx, ebx
0x18003e90b  js      short loc_18003E934
0x18003e90d  lea     rcx, [r15+190h]
0x18003e914  lea     rax, [rsp+4C0h+Src]
0x18003e919  mov     rdx, r14
0x18003e91c  inc     rdx
0x18003e91f  cmp     [rax+rdx*2], r12w
0x18003e924  jnz     short loc_18003E91C
0x18003e926  jmp     short loc_18003E8CE
0x18003e928  lea     r9, [rsp+4C0h+Src]
0x18003e92d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003e932  jmp     short loc_18003E95E
0x18003e934  cmp     ebx, 80070002h
0x18003e93a  jz      short loc_18003E95E
0x18003e93c  mov     r8d, 939h
0x18003e942  mov     [rsp+4C0h+var_4A0], ebx
0x18003e946  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x18003e94d  lea     rdx, aApplicationRet; "Application::Retrieve"
0x18003e954  mov     ecx, 1
0x18003e959  call    AslLogCallPrintf
0x18003e95e  mov     [rsp+4C0h+var_490], 208h
0x18003e966  mov     rax, [r13+0]
0x18003e96a  lea     rdx, ?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x18003e971  cmp     cs:qword_18011B3E8, rsi
0x18003e978  cmova   rdx, cs:?InventoryItemValueNameName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameName
0x18003e980  lea     r9, [rsp+4C0h+var_490]
0x18003e985  lea     r8, [rsp+4C0h+Src]
0x18003e98a  mov     rcx, r13
0x18003e98d  mov     rax, [rax+40h]
0x18003e991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e996  test    eax, eax
0x18003e998  js      short loc_18003E9EF
0x18003e99a  lea     rcx, [r15+60h]
0x18003e99e  lea     rax, [rsp+4C0h+Src]
0x18003e9a3  mov     rdx, r14
0x18003e9a6  inc     rdx
0x18003e9a9  cmp     [rax+rdx*2], r12w
0x18003e9ae  jnz     short loc_18003E9A6
0x18003e9b0  cmp     rdx, [rcx+18h]
0x18003e9b4  ja      short loc_18003E9E3
0x18003e9b6  cmp     [rcx+18h], rsi
0x18003e9ba  jbe     short loc_18003E9C1
0x18003e9bc  mov     rdi, [rcx]
0x18003e9bf  jmp     short loc_18003E9C4
0x18003e9c1  mov     rdi, rcx
0x18003e9c4  mov     [rcx+10h], rdx
0x18003e9c8  lea     rbx, [rdx+rdx]
0x18003e9cc  mov     r8, rbx; Size
0x18003e9cf  lea     rdx, [rsp+4C0h+Src]; Src
0x18003e9d4  mov     rcx, rdi; void *
0x18003e9d7  call    memmove_0
0x18003e9dc  mov     [rdi+rbx], r12w
0x18003e9e1  jmp     short loc_18003EA11
0x18003e9e3  lea     r9, [rsp+4C0h+Src]
0x18003e9e8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003e9ed  jmp     short loc_18003EA11
0x18003e9ef  mov     [rsp+4C0h+var_4A0], eax
0x18003e9f3  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x18003e9fa  mov     r8d, 948h
0x18003ea00  lea     rdx, aApplicationRet; "Application::Retrieve"
0x18003ea07  mov     ecx, 1
0x18003ea0c  call    AslLogCallPrintf
0x18003ea11  mov     [rsp+4C0h+var_490], 208h
0x18003ea19  mov     rax, [r13+0]
0x18003ea1d  lea     rdx, ?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x18003ea24  cmp     cs:qword_18011B408, rsi
0x18003ea2b  cmova   rdx, cs:?InventoryItemValueNameVersion@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameVersion
0x18003ea33  lea     r9, [rsp+4C0h+var_490]
0x18003ea38  lea     r8, [rsp+4C0h+Src]
0x18003ea3d  mov     rcx, r13
0x18003ea40  mov     rax, [rax+40h]
0x18003ea44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea49  test    eax, eax
0x18003ea4b  js      short loc_18003EAA5
0x18003ea4d  lea     rcx, [r15+0A0h]
0x18003ea54  lea     rax, [rsp+4C0h+Src]
0x18003ea59  mov     rdx, r14
0x18003ea5c  inc     rdx
0x18003ea5f  cmp     [rax+rdx*2], r12w
0x18003ea64  jnz     short loc_18003EA5C
0x18003ea66  cmp     rdx, [rcx+18h]
0x18003ea6a  ja      short loc_18003EA99
0x18003ea6c  cmp     [rcx+18h], rsi
0x18003ea70  jbe     short loc_18003EA77
0x18003ea72  mov     rdi, [rcx]
0x18003ea75  jmp     short loc_18003EA7A
0x18003ea77  mov     rdi, rcx
0x18003ea7a  mov     [rcx+10h], rdx
0x18003ea7e  lea     rbx, [rdx+rdx]
0x18003ea82  mov     r8, rbx; Size
0x18003ea85  lea     rdx, [rsp+4C0h+Src]; Src
0x18003ea8a  mov     rcx, rdi; void *
0x18003ea8d  call    memmove_0
0x18003ea92  mov     [rdi+rbx], r12w
0x18003ea97  jmp     short loc_18003EAC7
0x18003ea99  lea     r9, [rsp+4C0h+Src]
0x18003ea9e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003eaa3  jmp     short loc_18003EAC7
0x18003eaa5  mov     [rsp+4C0h+var_4A0], eax
0x18003eaa9  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x18003eab0  mov     r8d, 956h
0x18003eab6  lea     rdx, aApplicationRet; "Application::Retrieve"
0x18003eabd  mov     ecx, 1
0x18003eac2  call    AslLogCallPrintf
0x18003eac7  mov     [rsp+4C0h+var_490], 208h
0x18003eacf  mov     rax, [r13+0]
0x18003ead3  lea     rdx, ?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x18003eada  cmp     cs:qword_18011B428, rsi
0x18003eae1  cmova   rdx, cs:?InventoryItemValueNamePublisher@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNamePublisher
0x18003eae9  lea     r9, [rsp+4C0h+var_490]
0x18003eaee  lea     r8, [rsp+4C0h+Src]
0x18003eaf3  mov     rcx, r13
0x18003eaf6  mov     rax, [rax+40h]
0x18003eafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eaff  test    eax, eax
0x18003eb01  js      short loc_18003EB5B
0x18003eb03  lea     rcx, [r15+80h]
0x18003eb0a  lea     rax, [rsp+4C0h+Src]
0x18003eb0f  mov     rdx, r14
0x18003eb12  inc     rdx
0x18003eb15  cmp     [rax+rdx*2], r12w
0x18003eb1a  jnz     short loc_18003EB12
0x18003eb1c  cmp     rdx, [rcx+18h]
0x18003eb20  ja      short loc_18003EB4F
0x18003eb22  cmp     [rcx+18h], rsi
0x18003eb26  jbe     short loc_18003EB2D
0x18003eb28  mov     rdi, [rcx]
0x18003eb2b  jmp     short loc_18003EB30
0x18003eb2d  mov     rdi, rcx
0x18003eb30  mov     [rcx+10h], rdx
0x18003eb34  lea     rbx, [rdx+rdx]
0x18003eb38  mov     r8, rbx; Size
0x18003eb3b  lea     rdx, [rsp+4C0h+Src]; Src
0x18003eb40  mov     rcx, rdi; void *
0x18003eb43  call    memmove_0
0x18003eb48  mov     [rdi+rbx], r12w
0x18003eb4d  jmp     short loc_18003EB7D
0x18003eb4f  lea     r9, [rsp+4C0h+Src]
0x18003eb54  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003eb59  jmp     short loc_18003EB7D
0x18003eb5b  mov     [rsp+4C0h+var_4A0], eax
0x18003eb5f  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x18003eb66  mov     r8d, 964h
0x18003eb6c  lea     rdx, aApplicationRet; "Application::Retrieve"
0x18003eb73  mov     ecx, 1
0x18003eb78  call    AslLogCallPrintf
0x18003eb7d  mov     rax, [r13+0]
0x18003eb81  lea     rbx, ?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x18003eb88  mov     rdx, rbx
0x18003eb8b  cmp     cs:qword_18011B448, rsi
0x18003eb92  cmova   rdx, cs:?InventoryItemValueNameLanguage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameLanguage
0x18003eb9a  lea     rsi, [r15+1D0h]
0x18003eba1  mov     r8, rsi
0x18003eba4  mov     rcx, r13
0x18003eba7  mov     rax, [rax+50h]
0x18003ebab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebb0  mov     edi, eax
0x18003ebb2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003ebb9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003ebbe  test    edi, edi
0x18003ebc0  jns     short loc_18003EBEC
0x18003ebc2  test    al, al
0x18003ebc4  jz      loc_18003EC76
0x18003ebca  mov     [rsp+4C0h+var_4A0], edi
0x18003ebce  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x18003ebd5  mov     r8d, 96Dh
0x18003ebdb  lea     rdx, aApplicationRet; "Application::Retrieve"
0x18003ebe2  mov     ecx, 1
0x18003ebe7  call    AslLogCallPrintf
0x18003ebec  xor     edi, edi
0x18003ebee  mov     [rsp+4C0h+var_490], 208h
0x18003ebf6  mov     rax, [r13+0]
0x18003ebfa  lea     rdx, ?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x18003ec01  mov     esi, 7
0x18003ec06  cmp     cs:qword_18011B548, rsi
0x18003ec0d  cmova   rdx, cs:?InventoryItemValueNameInstallDate@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::InventoryItemValueNameInstallDate
0x18003ec15  lea     r9, [rsp+4C0h+var_490]
0x18003ec1a  lea     r8, [rsp+4C0h+Src]
0x18003ec1f  mov     rcx, r13
0x18003ec22  mov     rax, [rax+40h]
0x18003ec26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec2b  mov     ebx, eax
0x18003ec2d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003ec34  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003ec39  test    al, al
0x18003ec3b  jz      loc_18003ED17
0x18003ec41  test    ebx, ebx
0x18003ec43  js      loc_18003ED0F
0x18003ec49  lea     rcx, [r15+100h]
0x18003ec50  lea     rax, [rsp+4C0h+Src]
0x18003ec55  mov     rdx, r14
0x18003ec58  inc     rdx
0x18003ec5b  cmp     [rax+rdx*2], di
0x18003ec5f  jnz     short loc_18003EC58
0x18003ec61  cmp     rdx, [rcx+18h]
0x18003ec65  ja      loc_18003ED38
  ... truncated ...
```
