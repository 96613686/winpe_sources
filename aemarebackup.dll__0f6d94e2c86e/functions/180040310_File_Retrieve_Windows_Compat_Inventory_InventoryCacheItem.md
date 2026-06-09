# File::Retrieve(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x180040310`
- end: `0x1800415aa`
- name: `?Retrieve@File@@UEAAKPEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `4762`
- prototype: `unsigned int __fastcall(File *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180037430`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18000712e`
- `0x180010640`
- `0x18002772c`
- `0x180040310`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180040e48`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180040e48`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800412f5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800412f5`

## string_xrefs

- `0x1800403f5`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800404c0`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040584`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18004064b`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040759`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040861`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040969`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040a71`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040b32`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040c78`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040d80`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040e61`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180040f65`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180041026`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800410c2`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18004122c`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18004130e`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18004138a`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18004140a`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18004149d`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x18004155c`: `TelCacheProvider::GetItemProperty failed [%#x]`

## pseudocode

```c
__int64 __fastcall File::Retrieve(File *this, struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  __int64 v4; // rax
  __int64 *v5; // rdx
  __int64 (__fastcall *v6)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *); // rax
  int v7; // eax
  __int64 v8; // r8
  unsigned __int64 v9; // rdi
  char **v10; // rcx
  unsigned __int64 v11; // rdx
  char *v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 *v15; // rdx
  int v16; // eax
  __int64 v17; // r8
  char **v18; // rcx
  unsigned __int64 v19; // rdx
  char *v20; // rsi
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 *v23; // rdx
  int v24; // eax
  __int64 v25; // r8
  char **v26; // rcx
  unsigned __int64 v27; // rdx
  char *v28; // rsi
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 *v31; // rdx
  int v32; // eax
  __int64 v33; // r8
  char **v34; // rcx
  unsigned __int64 v35; // rdx
  char *v36; // rsi
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 *v39; // rdx
  int v40; // ebx
  __int64 v41; // r8
  char *v42; // rcx
  unsigned __int64 v43; // rdx
  char *v44; // rsi
  __int64 v45; // rbx
  __int64 v46; // r8
  __int64 v47; // rax
  __int64 *v48; // rdx
  int v49; // ebx
  __int64 v50; // r8
  char *v51; // rcx
  unsigned __int64 v52; // rdx
  char *v53; // rsi
  __int64 v54; // rbx
  __int64 v55; // r8
  __int64 v56; // rax
  __int64 *v57; // rdx
  int v58; // ebx
  __int64 v59; // r8
  char *v60; // rcx
  unsigned __int64 v61; // rdx
  char *v62; // rsi
  __int64 v63; // rbx
  __int64 v64; // r8
  __int64 v65; // rax
  __int64 *v66; // rdx
  int v67; // ebx
  __int64 v68; // r8
  char *v69; // rcx
  unsigned __int64 v70; // rdx
  char *v71; // rsi
  __int64 v72; // rbx
  __int64 v73; // r8
  __int64 v74; // rax
  __int64 *v75; // rdx
  int v76; // eax
  __int64 v77; // r8
  char **v78; // rcx
  unsigned __int64 v79; // rdx
  char *v80; // rsi
  __int64 v81; // rbx
  __int64 v82; // rax
  __int64 *v83; // rdx
  int v84; // ebx
  __int64 v85; // r8
  char *v86; // rcx
  unsigned __int64 v87; // rdx
  char *v88; // rsi
  __int64 v89; // rbx
  __int64 v90; // r8
  char *v91; // rsi
  __int64 v92; // rbx
  __int64 v93; // rax
  __int64 *v94; // rdx
  int v95; // ebx
  __int64 v96; // r8
  char *v97; // rcx
  unsigned __int64 v98; // rdx
  char *v99; // rsi
  __int64 v100; // rbx
  __int64 v101; // r8
  __int64 v102; // rax
  __int64 *v103; // rsi
  __int64 *v104; // rdx
  int v105; // ebx
  int v106; // eax
  __int64 v107; // rax
  int v108; // eax
  __int64 v109; // rax
  __int64 *v110; // rdx
  int v111; // ebx
  __int64 v112; // r8
  char *v113; // rcx
  unsigned __int64 v114; // rdx
  char *v115; // rsi
  __int64 v116; // rbx
  __int64 v117; // r8
  __int64 v118; // rax
  __int64 *v119; // rdx
  int v120; // eax
  __int64 v121; // r8
  char **v122; // rcx
  unsigned __int64 v123; // rdx
  char *v124; // rsi
  __int64 v125; // rbx
  __int64 v126; // rax
  __int64 *v127; // rdx
  int v128; // ebx
  __int64 v129; // r8
  char *v130; // rcx
  unsigned __int64 v131; // rdx
  char *v132; // rsi
  __int64 v133; // rbx
  __int64 v134; // rax
  __int64 *v135; // rdx
  int v136; // ebx
  __int64 v137; // r8
  char *v138; // rcx
  unsigned __int64 v139; // rdx
  char *v140; // rsi
  __int64 v141; // rbx
  __int64 v142; // r8
  __int64 v143; // rax
  __int64 *v144; // rsi
  __int64 *v145; // rdx
  int v146; // ebx
  __int64 v147; // rax
  __int64 v148; // rax
  int v149; // eax
  __int64 *v150; // rdx
  int v151; // ebx
  __int64 v152; // r8
  __int64 *v153; // rdx
  int v154; // ebx
  __int64 v155; // r8
  __int64 v156; // rax
  __int64 *v157; // rdx
  int v158; // ebx
  __int64 v159; // r8
  char *v160; // rcx
  void *v161; // rsi
  __int64 v162; // rax
  __int64 *v163; // rdx
  int v164; // eax
  int v166; // [rsp+30h] [rbp-D0h] BYREF
  int v167; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v168; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v169; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Src[520]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(Src, 0, sizeof(Src));
  v4 = *(_QWORD *)a2;
  v5 = &File::InventoryItemValueNameProgramId;
  v166 = 520;
  v6 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v4 + 64);
  if ( (unsigned __int64)qword_18011B6A8 > 7 )
    v5 = (__int64 *)File::InventoryItemValueNameProgramId;
  v7 = v6(a2, v5, Src, &v166);
  v9 = -1;
  if ( v7 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 2861, "TelCacheProvider::GetItemProperty failed [%#x]", v7);
  }
  else
  {
    v10 = (char **)((char *)this + 80);
    v11 = -1;
    do
      ++v11;
    while ( Src[v11] );
    if ( v11 > *((_QWORD *)this + 13) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v10, v11, v8, Src);
    }
    else
    {
      if ( *((_QWORD *)this + 13) <= 7u )
        v12 = (char *)this + 80;
      else
        v12 = *v10;
      v13 = 2 * v11;
      *((_QWORD *)this + 12) = v11;
      memmove_0(v12, Src, 2 * v11);
      *(_WORD *)&v12[v13] = 0;
    }
  }
  memset_0(Src, 0, sizeof(Src));
  v14 = *(_QWORD *)a2;
  v15 = &File::InventoryItemValueNameFileId;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B6C8 > 7 )
    v15 = (__int64 *)File::InventoryItemValueNameFileId;
  v16 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v14 + 64))(
          a2,
          v15,
          Src,
          &v166);
  if ( v16 < 0 )
  {
    if ( v16 != -2147024894 )
      AslLogCallPrintf(1, "File::Retrieve", 2877, "TelCacheProvider::GetItemProperty failed [%#x]", v16);
  }
  else
  {
    v18 = (char **)((char *)this + 112);
    v19 = -1;
    do
      ++v19;
    while ( Src[v19] );
    if ( v19 > *((_QWORD *)this + 17) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v18,
        v19,
        v17,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 17) <= 7u )
        v20 = (char *)this + 112;
      else
        v20 = *v18;
      v21 = 2 * v19;
      *((_QWORD *)this + 16) = v19;
      memmove_0(v20, Src, 2 * v19);
      *(_WORD *)&v20[v21] = 0;
    }
  }
  memset_0(Src, 0, sizeof(Src));
  v22 = *(_QWORD *)a2;
  v23 = &File::InventoryItemValueNameFilePath;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B6E8 > 7 )
    v23 = (__int64 *)File::InventoryItemValueNameFilePath;
  v24 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v22 + 64))(
          a2,
          v23,
          Src,
          &v166);
  if ( v24 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 2893, "TelCacheProvider::GetItemProperty failed [%#x]", v24);
  }
  else
  {
    v26 = (char **)((char *)this + 16);
    v27 = -1;
    do
      ++v27;
    while ( Src[v27] );
    if ( v27 > *((_QWORD *)this + 5) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v26,
        v27,
        v25,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 5) <= 7u )
        v28 = (char *)this + 16;
      else
        v28 = *v26;
      v29 = 2 * v27;
      *((_QWORD *)this + 4) = v27;
      memmove_0(v28, Src, 2 * v27);
      *(_WORD *)&v28[v29] = 0;
    }
  }
  memset_0(Src, 0, sizeof(Src));
  v30 = *(_QWORD *)a2;
  v31 = &File::InventoryItemValueNameName;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B728 > 7 )
    v31 = (__int64 *)File::InventoryItemValueNameName;
  v32 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v30 + 64))(
          a2,
          v31,
          Src,
          &v166);
  if ( v32 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 2909, "TelCacheProvider::GetItemProperty failed [%#x]", v32);
  }
  else
  {
    v34 = (char **)((char *)this + 208);
    v35 = -1;
    do
      ++v35;
    while ( Src[v35] );
    if ( v35 > *((_QWORD *)this + 29) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v34,
        v35,
        v33,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 29) <= 7u )
        v36 = (char *)this + 208;
      else
        v36 = *v34;
      v37 = 2 * v35;
      *((_QWORD *)this + 28) = v35;
      memmove_0(v36, Src, 2 * v35);
      *(_WORD *)&v36[v37] = 0;
    }
  }
  memset_0(Src, 0, sizeof(Src));
  v38 = *(_QWORD *)a2;
  v39 = &File::InventoryItemValueNameOriginalFileName;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B748 > 7 )
    v39 = (__int64 *)File::InventoryItemValueNameOriginalFileName;
  v40 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v38 + 64))(
          a2,
          v39,
          Src,
          &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v40 >= 0 )
    {
      v42 = (char *)this + 528;
      v43 = -1;
      do
        ++v43;
      while ( Src[v43] );
      goto LABEL_56;
    }
    v46 = 2926;
LABEL_69:
    AslLogCallPrintf(1, "File::Retrieve", v46, "TelCacheProvider::GetItemProperty failed [%#x]", v40);
    goto LABEL_70;
  }
  if ( v40 < 0 )
  {
    if ( v40 == -2147024894 )
      goto LABEL_70;
    v46 = 2938;
    goto LABEL_69;
  }
  v42 = (char *)this + 528;
  v43 = -1;
  do
    ++v43;
  while ( Src[v43] );
LABEL_56:
  if ( v43 > *((_QWORD *)v42 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v42, v43, v41, Src);
  }
  else
  {
    if ( *((_QWORD *)v42 + 3) <= 7u )
      v44 = v42;
    else
      v44 = *(char **)v42;
    v45 = 2 * v43;
    *((_QWORD *)v42 + 2) = v43;
    memmove_0(v44, Src, 2 * v43);
    *(_WORD *)&v44[v45] = 0;
  }
LABEL_70:
  memset_0(Src, 0, sizeof(Src));
  v47 = *(_QWORD *)a2;
  v48 = &File::InventoryItemValueNamePublisher;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B768 > 7 )
    v48 = (__int64 *)File::InventoryItemValueNamePublisher;
  v49 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v47 + 64))(
          a2,
          v48,
          Src,
          &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v49 >= 0 )
    {
      v51 = (char *)this + 272;
      v52 = -1;
      do
        ++v52;
      while ( Src[v52] );
      goto LABEL_76;
    }
    v55 = 2956;
LABEL_89:
    AslLogCallPrintf(1, "File::Retrieve", v55, "TelCacheProvider::GetItemProperty failed [%#x]", v49);
    goto LABEL_90;
  }
  if ( v49 < 0 )
  {
    if ( v49 == -2147024894 )
      goto LABEL_90;
    v55 = 2968;
    goto LABEL_89;
  }
  v51 = (char *)this + 272;
  v52 = -1;
  do
    ++v52;
  while ( Src[v52] );
LABEL_76:
  if ( v52 > *((_QWORD *)v51 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v51, v52, v50, Src);
  }
  else
  {
    if ( *((_QWORD *)v51 + 3) <= 7u )
      v53 = v51;
    else
      v53 = *(char **)v51;
    v54 = 2 * v52;
    *((_QWORD *)v51 + 2) = v52;
    memmove_0(v53, Src, 2 * v52);
    *(_WORD *)&v53[v54] = 0;
  }
LABEL_90:
  memset_0(Src, 0, sizeof(Src));
  v56 = *(_QWORD *)a2;
  v57 = &File::InventoryItemValueNameProductName;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B828 > 7 )
    v57 = (__int64 *)File::InventoryItemValueNameProductName;
  v58 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v56 + 64))(
          a2,
          v57,
          Src,
          &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v58 >= 0 )
    {
      v60 = (char *)this + 304;
      v61 = -1;
      do
        ++v61;
      while ( Src[v61] );
      goto LABEL_96;
    }
    v64 = 2988;
LABEL_109:
    AslLogCallPrintf(1, "File::Retrieve", v64, "TelCacheProvider::GetItemProperty failed [%#x]", v58);
    goto LABEL_110;
  }
  if ( v58 < 0 )
  {
    if ( v58 == -2147024894 )
      goto LABEL_110;
    v64 = 3000;
    goto LABEL_109;
  }
  v60 = (char *)this + 304;
  v61 = -1;
  do
    ++v61;
  while ( Src[v61] );
LABEL_96:
  if ( v61 > *((_QWORD *)v60 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v60, v61, v59, Src);
  }
  else
  {
    if ( *((_QWORD *)v60 + 3) <= 7u )
      v62 = v60;
    else
      v62 = *(char **)v60;
    v63 = 2 * v61;
    *((_QWORD *)v60 + 2) = v61;
    memmove_0(v62, Src, 2 * v61);
    *(_WORD *)&v62[v63] = 0;
  }
LABEL_110:
  memset_0(Src, 0, sizeof(Src));
  v65 = *(_QWORD *)a2;
  v66 = &File::InventoryItemValueNameBinProductVersion;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B888 > 7 )
    v66 = (__int64 *)File::InventoryItemValueNameBinProductVersion;
  v67 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v65 + 64))(
          a2,
          v66,
          Src,
          &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v67 >= 0 )
    {
      v69 = (char *)this + 368;
      v70 = -1;
      do
        ++v70;
      while ( Src[v70] );
      goto LABEL_116;
    }
    v73 = 3018;
LABEL_129:
    AslLogCallPrintf(1, "File::Retrieve", v73, "TelCacheProvider::GetItemProperty failed [%#x]", v67);
    goto LABEL_130;
  }
  if ( v67 < 0 )
  {
    if ( v67 == -2147024894 )
      goto LABEL_130;
    v73 = 3030;
    goto LABEL_129;
  }
  v69 = (char *)this + 368;
  v70 = -1;
  do
    ++v70;
  while ( Src[v70] );
LABEL_116:
  if ( v70 > *((_QWORD *)v69 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v69, v70, v68, Src);
  }
  else
  {
    if ( *((_QWORD *)v69 + 3) <= 7u )
      v71 = v69;
    else
      v71 = *(char **)v69;
    v72 = 2 * v70;
    *((_QWORD *)v69 + 2) = v70;
    memmove_0(v71, Src, 2 * v70);
    *(_WORD *)&v71[v72] = 0;
  }
LABEL_130:
  memset_0(Src, 0, sizeof(Src));
  v74 = *(_QWORD *)a2;
  v75 = &File::InventoryItemValueNameLinkDate;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B868 > 7 )
    v75 = (__int64 *)File::InventoryItemValueNameLinkDate;
  v76 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v74 + 64))(
          a2,
          v75,
          Src,
          &v166);
  if ( v76 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 3044, "TelCacheProvider::GetItemProperty failed [%#x]", v76);
  }
  else
  {
    v78 = (char **)((char *)this + 560);
    v79 = -1;
    do
      ++v79;
    while ( Src[v79] );
    if ( v79 > *((_QWORD *)this + 73) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v78,
        v79,
        v77,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 73) <= 7u )
        v80 = (char *)this + 560;
      else
        v80 = *v78;
      v81 = 2 * v79;
      *((_QWORD *)this + 72) = v79;
      memmove_0(v80, Src, 2 * v79);
      *(_WORD *)&v80[v81] = 0;
    }
  }
  memset_0(Src, 0, sizeof(Src));
  v82 = *(_QWORD *)a2;
  v83 = &File::InventoryItemValueNameProductVersion;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B848 > 7 )
    v83 = (__int64 *)File::InventoryItemValueNameProductVersion;
  v84 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v82 + 64))(
          a2,
          v83,
          Src,
          &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v84 >= 0 )
    {
      v86 = (char *)this + 336;
      v87 = -1;
      do
        ++v87;
      while ( Src[v87] );
      if ( v87 <= *((_QWORD *)this + 45) )
      {
        if ( *((_QWORD *)this + 45) <= 7u )
          v88 = (char *)this + 336;
        else
          v88 = *(char **)v86;
        v89 = 2 * v87;
        *((_QWORD *)this + 44) = v87;
        memmove_0(v88, Src, 2 * v87);
        *(_WORD *)&v88[v89] = 0;
        goto LABEL_166;
      }
LABEL_162:
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v86,
        v87,
        v85,
        Src);
      goto LABEL_166;
    }
    v90 = 3059;
LABEL_165:
    AslLogCallPrintf(1, "File::Retrieve", v90, "TelCacheProvider::GetItemProperty failed [%#x]", v84);
    goto LABEL_166;
  }
  if ( v84 < 0 )
  {
    if ( v84 == -2147024894 )
      goto LABEL_166;
    v90 = 3071;
    goto LABEL_165;
  }
  v86 = (char *)this + 560;
  v87 = -1;
  do
    ++v87;
  while ( Src[v87] );
  if ( v87 > *((_QWORD *)this + 73) )
    goto LABEL_162;
  if ( *((_QWORD *)this + 73) <= 7u )
    v91 = (char *)this + 560;
  else
    v91 = *(char **)v86;
  v92 = 2 * v87;
  *((_QWORD *)this + 72) = v87;
  memmove_0(v91, Src, 2 * v87);
  *(_WORD *)&v91[v92] = 0;
LABEL_166:
  memset_0(Src, 0, sizeof(Src));
  v93 = *(_QWORD *)a2;
  v94 = &File::InventoryItemValueNameVersion;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B788 > 7 )
    v94 = (__int64 *)File::InventoryItemValueNameVersion;
  v95 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v93 + 64))(
          a2,
          v94,
          Src,
          &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v95 >= 0 )
    {
      v97 = (char *)this + 240;
      v98 = -1;
      do
        ++v98;
      while ( Src[v98] );
      goto LABEL_172;
    }
    v101 = 3089;
LABEL_185:
    AslLogCallPrintf(1, "File::Retrieve", v101, "TelCacheProvider::GetItemProperty failed [%#x]", v95);
    goto LABEL_186;
  }
  if ( v95 < 0 )
  {
    if ( v95 == -2147024894 )
      goto LABEL_186;
    v101 = 3101;
    goto LABEL_185;
  }
  v97 = (char *)this + 240;
  v98 = -1;
  do
    ++v98;
  while ( Src[v98] );
LABEL_172:
  if ( v98 > *((_QWORD *)v97 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v97, v98, v96, Src);
  }
  else
  {
    if ( *((_QWORD *)v97 + 3) <= 7u )
      v99 = v97;
    else
      v99 = *(char **)v97;
    v100 = 2 * v98;
    *((_QWORD *)v97 + 2) = v98;
    memmove_0(v99, Src, 2 * v98);
    *(_WORD *)&v99[v100] = 0;
  }
LABEL_186:
  v102 = *(_QWORD *)a2;
  v103 = &File::InventoryItemValueNameLanguage;
  v104 = &File::InventoryItemValueNameLanguage;
  v167 = 0;
  if ( (unsigned __int64)qword_18011B7A8 > 7 )
    v104 = (__int64 *)File::InventoryItemValueNameLanguage;
  v105 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(v102 + 80))(
           a2,
           v104,
           &v167);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v105 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3116, "TelCacheProvider::GetItemProperty failed [%#x]", v105);
      goto LABEL_199;
    }
    goto LABEL_192;
  }
  if ( v105 >= 0 )
  {
LABEL_192:
    v106 = v167;
LABEL_197:
    *((_DWORD *)this + 198) = v106;
    goto LABEL_199;
  }
  memset_0(Src, 0, sizeof(Src));
  v107 = *(_QWORD *)a2;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B7A8 > 7 )
    v103 = (__int64 *)File::InventoryItemValueNameLanguage;
  v108 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v107 + 64))(
           a2,
           v103,
           Src,
           &v166);
  if ( v108 >= 0 )
  {
    v106 = _o__wtoi(Src);
    goto LABEL_197;
  }
  AslLogCallPrintf(1, "File::Retrieve", 3138, "TelCacheProvider::GetItemProperty failed [%#x]", v108);
LABEL_199:
  memset_0(Src, 0, sizeof(Src));
  v109 = *(_QWORD *)a2;
  v110 = &File::InventoryItemValueNameBinFileVersion;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B7C8 > 7 )
    v110 = (__int64 *)File::InventoryItemValueNameBinFileVersion;
  v111 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v109 + 64))(
           a2,
           v110,
           Src,
           &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v111 >= 0 )
    {
      v113 = (char *)this + 176;
      v114 = -1;
      do
        ++v114;
      while ( Src[v114] );
      goto LABEL_205;
    }
    v117 = 3157;
LABEL_218:
    AslLogCallPrintf(1, "File::Retrieve", v117, "TelCacheProvider::GetItemProperty failed [%#x]", v111);
    goto LABEL_219;
  }
  if ( v111 < 0 )
  {
    if ( v111 == -2147024894 )
      goto LABEL_219;
    v117 = 3169;
    goto LABEL_218;
  }
  v113 = (char *)this + 176;
  v114 = -1;
  do
    ++v114;
  while ( Src[v114] );
LABEL_205:
  if ( v114 > *((_QWORD *)v113 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      v113,
      v114,
      v112,
      Src);
  }
  else
  {
    if ( *((_QWORD *)v113 + 3) <= 7u )
      v115 = v113;
    else
      v115 = *(char **)v113;
    v116 = 2 * v114;
    *((_QWORD *)v113 + 2) = v114;
    memmove_0(v115, Src, 2 * v114);
    *(_WORD *)&v115[v116] = 0;
  }
LABEL_219:
  memset_0(Src, 0, sizeof(Src));
  v118 = *(_QWORD *)a2;
  v119 = &File::InventoryItemValueNameBinaryType;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B7E8 > 7 )
    v119 = (__int64 *)File::InventoryItemValueNameBinaryType;
  v120 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v118 + 64))(
           a2,
           v119,
           Src,
           &v166);
  if ( v120 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 3186, "TelCacheProvider::GetItemProperty failed [%#x]", v120);
  }
  else
  {
    v122 = (char **)((char *)this + 144);
    v123 = -1;
    do
      ++v123;
    while ( Src[v123] );
    if ( v123 > *((_QWORD *)this + 21) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v122,
        v123,
        v121,
        Src);
    }
    else
    {
      if ( *((_QWORD *)this + 21) <= 7u )
        v124 = (char *)this + 144;
      else
        v124 = *v122;
      v125 = 2 * v123;
      *((_QWORD *)this + 20) = v123;
      memmove_0(v124, Src, 2 * v123);
      *(_WORD *)&v124[v125] = 0;
    }
  }
  memset_0(Src, 0, sizeof(Src));
  v126 = *(_QWORD *)a2;
  v127 = &File::InventoryItemValueNameAppxPackageFullName;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B908 > 7 )
    v127 = (__int64 *)File::InventoryItemValueNameAppxPackageFullName;
  v128 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v126 + 64))(
           a2,
           v127,
           Src,
           &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v128 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3203, "TelCacheProvider::GetItemProperty failed [%#x]", v128);
      goto LABEL_248;
    }
    v130 = (char *)this + 656;
    v131 = -1;
    do
      ++v131;
    while ( Src[v131] );
  }
  else
  {
    if ( v128 < 0 )
      goto LABEL_248;
    v130 = (char *)this + 656;
    v131 = -1;
    do
      ++v131;
    while ( Src[v131] );
  }
  if ( v131 > *((_QWORD *)v130 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      v130,
      v131,
      v129,
      Src);
  }
  else
  {
    if ( *((_QWORD *)v130 + 3) <= 7u )
      v132 = v130;
    else
      v132 = *(char **)v130;
    v133 = 2 * v131;
    *((_QWORD *)v130 + 2) = v131;
    memmove_0(v132, Src, 2 * v131);
    *(_WORD *)&v132[v133] = 0;
  }
LABEL_248:
  memset_0(Src, 0, sizeof(Src));
  v134 = *(_QWORD *)a2;
  v135 = &File::InventoryItemValueNameAppxPackageRelativeId;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B928 > 7 )
    v135 = (__int64 *)File::InventoryItemValueNameAppxPackageRelativeId;
  v136 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v134 + 64))(
           a2,
           v135,
           Src,
           &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v136 >= 0 )
    {
      v138 = (char *)this + 688;
      v139 = -1;
      do
        ++v139;
      while ( Src[v139] );
      goto LABEL_254;
    }
    v142 = 3228;
LABEL_267:
    AslLogCallPrintf(1, "File::Retrieve", v142, "TelCacheProvider::GetItemProperty failed [%#x]", v136);
    goto LABEL_268;
  }
  if ( v136 < 0 )
  {
    if ( v136 == -2147024894 )
      goto LABEL_268;
    v142 = 3240;
    goto LABEL_267;
  }
  v138 = (char *)this + 688;
  v139 = -1;
  do
    ++v139;
  while ( Src[v139] );
LABEL_254:
  if ( v139 > *((_QWORD *)v138 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      v138,
      v139,
      v137,
      Src);
  }
  else
  {
    if ( *((_QWORD *)v138 + 3) <= 7u )
      v140 = v138;
    else
      v140 = *(char **)v138;
    v141 = 2 * v139;
    *((_QWORD *)v138 + 2) = v139;
    memmove_0(v140, Src, 2 * v139);
    *(_WORD *)&v140[v141] = 0;
  }
LABEL_268:
  v143 = *(_QWORD *)a2;
  v144 = &File::InventoryItemValueNameFileSize;
  v145 = &File::InventoryItemValueNameFileSize;
  v168 = 0;
  if ( (unsigned __int64)qword_18011B808 > 7 )
    v145 = (__int64 *)File::InventoryItemValueNameFileSize;
  v146 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, __int64 *))(v143 + 72))(
           a2,
           v145,
           &v168);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v146 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3255, "TelCacheProvider::GetItemProperty failed [%#x]", v146);
      goto LABEL_281;
    }
    goto LABEL_274;
  }
  if ( v146 >= 0 )
  {
LABEL_274:
    v147 = v168;
LABEL_279:
    *((_QWORD *)this + 97) = v147;
    goto LABEL_281;
  }
  memset_0(Src, 0, sizeof(Src));
  v148 = *(_QWORD *)a2;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B808 > 7 )
    v144 = (__int64 *)File::InventoryItemValueNameFileSize;
  v149 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v148 + 64))(
           a2,
           v144,
           Src,
           &v166);
  if ( v149 >= 0 )
  {
    v147 = _wtoi64(Src);
    goto LABEL_279;
  }
  AslLogCallPrintf(1, "File::Retrieve", 3277, "TelCacheProvider::GetItemProperty failed [%#x]", v149);
LABEL_281:
  v150 = &File::InventoryItemValueNameIsPeFile;
  if ( (unsigned __int64)qword_18011B8A8 > 7 )
    v150 = (__int64 *)File::InventoryItemValueNameIsPeFile;
  v151 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 48LL))(
           a2,
           v150,
           (char *)this + 796);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v151 >= 0 )
      goto LABEL_291;
    v152 = 3289;
    goto LABEL_290;
  }
  if ( v151 == -2147024894 )
  {
    *((_BYTE *)this + 796) = 1;
    goto LABEL_291;
  }
  if ( v151 < 0 )
  {
    v152 = 3301;
LABEL_290:
    AslLogCallPrintf(1, "File::Retrieve", v152, "TelCacheProvider::GetItemProperty failed [%#x]", v151);
  }
LABEL_291:
  v153 = &File::InventoryItemValueNameIsOsComponent;
  if ( (unsigned __int64)qword_18011B8C8 > 7 )
    v153 = (__int64 *)File::InventoryItemValueNameIsOsComponent;
  v154 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 48LL))(
           a2,
           v153,
           (char *)this + 797);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v154 >= 0 )
      goto LABEL_301;
    v155 = 3312;
    goto LABEL_300;
  }
  if ( v154 == -2147024894 )
  {
    *((_BYTE *)this + 797) = 0;
    goto LABEL_301;
  }
  if ( v154 < 0 )
  {
    v155 = 3324;
LABEL_300:
    AslLogCallPrintf(1, "File::Retrieve", v155, "TelCacheProvider::GetItemProperty failed [%#x]", v154);
  }
LABEL_301:
  memset_0(Src, 0, sizeof(Src));
  v156 = *(_QWORD *)a2;
  v157 = &File::InventoryItemValueNameSha256;
  v166 = 520;
  if ( (unsigned __int64)qword_18011B948 > 7 )
    v157 = (__int64 *)File::InventoryItemValueNameSha256;
  v158 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v156 + 64))(
           a2,
           v157,
           Src,
           &v166);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v158 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3342, "TelCacheProvider::GetItemProperty failed [%#x]", v158);
      goto LABEL_318;
    }
    v160 = (char *)this + 720;
    do
      ++v9;
    while ( Src[v9] );
  }
  else
  {
    if ( v158 < 0 )
      goto LABEL_318;
    v160 = (char *)this + 720;
    do
      ++v9;
    while ( Src[v9] );
  }
  if ( v9 > *((_QWORD *)v160 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v160, v9, v159, Src);
  }
  else
  {
    if ( *((_QWORD *)v160 + 3) <= 7u )
      v161 = v160;
    else
      v161 = *(void **)v160;
    *((_QWORD *)v160 + 2) = v9;
    memmove_0(v161, Src, 2 * v9);
    *((_WORD *)v161 + v9) = 0;
  }
LABEL_318:
  v162 = *(_QWORD *)a2;
  v163 = &File::InventoryItemValueNameUsn;
  v169 = 0;
  if ( (unsigned __int64)qword_18011B8E8 > 7 )
    v163 = (__int64 *)File::InventoryItemValueNameUsn;
  v164 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, __int64 *))(v162 + 8))(
           a2,
           v163,
           &v169);
  if ( v164 < 0 )
    AslLogCallPrintf(1, "File::Retrieve", 3363, "TelCacheProvider::GetItemProperty failed [%#x]", v164);
  else
    *((_QWORD *)this + 98) = v169;
  return 0;
}

```

## disassembly

```asm
0x180040310  mov     [rsp-8+arg_10], rbx
0x180040315  push    rbp
0x180040316  push    rsi
0x180040317  push    rdi
0x180040318  push    r12
0x18004031a  push    r13
0x18004031c  push    r14
0x18004031e  push    r15
0x180040320  lea     rbp, [rsp-370h]
0x180040328  sub     rsp, 470h
0x18004032f  mov     rax, cs:__security_cookie
0x180040336  xor     rax, rsp
0x180040339  mov     [rbp+3A0h+var_40], rax
0x180040340  mov     r15, rdx
0x180040343  mov     r14, rcx
0x180040346  xor     edx, edx; Val
0x180040348  lea     rcx, [rsp+4A0h+Src]; void *
0x18004034d  mov     r8d, 410h; Size
0x180040353  call    memset_0
0x180040358  mov     rax, [r15]
0x18004035b  lea     rdx, ?InventoryItemValueNameProgramId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProgramId
0x180040362  mov     r13d, 7
0x180040368  mov     [rsp+4A0h+var_470], 208h
0x180040370  cmp     cs:qword_18011B6A8, r13
0x180040377  lea     r9, [rsp+4A0h+var_470]
0x18004037c  lea     r8, [rsp+4A0h+Src]
0x180040381  mov     rcx, r15
0x180040384  mov     rax, [rax+40h]
0x180040388  cmova   rdx, cs:?InventoryItemValueNameProgramId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProgramId
0x180040390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040395  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180040399  xor     r12d, r12d
0x18004039c  test    eax, eax
0x18004039e  js      short loc_1800403F5
0x1800403a0  lea     rcx, [r14+50h]
0x1800403a4  mov     rdx, rdi
0x1800403a7  lea     rax, [rsp+4A0h+Src]
0x1800403ac  inc     rdx
0x1800403af  cmp     [rax+rdx*2], r12w
0x1800403b4  jnz     short loc_1800403AC
0x1800403b6  cmp     rdx, [rcx+18h]
0x1800403ba  ja      short loc_1800403E9
0x1800403bc  cmp     [rcx+18h], r13
0x1800403c0  jbe     short loc_1800403C7
0x1800403c2  mov     rsi, [rcx]
0x1800403c5  jmp     short loc_1800403CA
0x1800403c7  mov     rsi, rcx
0x1800403ca  lea     rbx, [rdx+rdx]
0x1800403ce  mov     [rcx+10h], rdx
0x1800403d2  mov     r8, rbx; Size
0x1800403d5  lea     rdx, [rsp+4A0h+Src]; Src
0x1800403da  mov     rcx, rsi; void *
0x1800403dd  call    memmove_0
0x1800403e2  mov     [rbx+rsi], r12w
0x1800403e7  jmp     short loc_180040417
0x1800403e9  lea     r9, [rsp+4A0h+Src]
0x1800403ee  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800403f3  jmp     short loc_180040417
0x1800403f5  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x1800403fc  mov     [rsp+4A0h+var_480], eax
0x180040400  mov     r8d, 0B2Dh
0x180040406  lea     rdx, aFileRetrieve; "File::Retrieve"
0x18004040d  mov     ecx, 1
0x180040412  call    AslLogCallPrintf
0x180040417  xor     edx, edx; Val
0x180040419  lea     rcx, [rsp+4A0h+Src]; void *
0x18004041e  mov     r8d, 410h; Size
0x180040424  call    memset_0
0x180040429  mov     rax, [r15]
0x18004042c  lea     rdx, ?InventoryItemValueNameFileId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFileId
0x180040433  cmp     cs:qword_18011B6C8, r13
0x18004043a  lea     r9, [rsp+4A0h+var_470]
0x18004043f  lea     r8, [rsp+4A0h+Src]
0x180040444  mov     [rsp+4A0h+var_470], 208h
0x18004044c  cmova   rdx, cs:?InventoryItemValueNameFileId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFileId
0x180040454  mov     rcx, r15
0x180040457  mov     rax, [rax+40h]
0x18004045b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040460  test    eax, eax
0x180040462  js      short loc_1800404B9
0x180040464  lea     rcx, [r14+70h]
0x180040468  mov     rdx, rdi
0x18004046b  lea     rax, [rsp+4A0h+Src]
0x180040470  inc     rdx
0x180040473  cmp     [rax+rdx*2], r12w
0x180040478  jnz     short loc_180040470
0x18004047a  cmp     rdx, [rcx+18h]
0x18004047e  ja      short loc_1800404AD
0x180040480  cmp     [rcx+18h], r13
0x180040484  jbe     short loc_18004048B
0x180040486  mov     rsi, [rcx]
0x180040489  jmp     short loc_18004048E
0x18004048b  mov     rsi, rcx
0x18004048e  lea     rbx, [rdx+rdx]
0x180040492  mov     [rcx+10h], rdx
0x180040496  mov     r8, rbx; Size
0x180040499  lea     rdx, [rsp+4A0h+Src]; Src
0x18004049e  mov     rcx, rsi; void *
0x1800404a1  call    memmove_0
0x1800404a6  mov     [rsi+rbx], r12w
0x1800404ab  jmp     short loc_1800404E2
0x1800404ad  lea     r9, [rsp+4A0h+Src]
0x1800404b2  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800404b7  jmp     short loc_1800404E2
0x1800404b9  cmp     eax, 80070002h
0x1800404be  jz      short loc_1800404E2
0x1800404c0  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x1800404c7  mov     [rsp+4A0h+var_480], eax
0x1800404cb  mov     r8d, 0B3Dh
0x1800404d1  lea     rdx, aFileRetrieve; "File::Retrieve"
0x1800404d8  mov     ecx, 1
0x1800404dd  call    AslLogCallPrintf
0x1800404e2  xor     edx, edx; Val
0x1800404e4  lea     rcx, [rsp+4A0h+Src]; void *
0x1800404e9  mov     r8d, 410h; Size
0x1800404ef  call    memset_0
0x1800404f4  mov     rax, [r15]
0x1800404f7  lea     rdx, ?InventoryItemValueNameFilePath@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFilePath
0x1800404fe  cmp     cs:qword_18011B6E8, r13
0x180040505  lea     r9, [rsp+4A0h+var_470]
0x18004050a  lea     r8, [rsp+4A0h+Src]
0x18004050f  mov     [rsp+4A0h+var_470], 208h
0x180040517  cmova   rdx, cs:?InventoryItemValueNameFilePath@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFilePath
0x18004051f  mov     rcx, r15
0x180040522  mov     rax, [rax+40h]
0x180040526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004052b  test    eax, eax
0x18004052d  js      short loc_180040584
0x18004052f  lea     rcx, [r14+10h]
0x180040533  mov     rdx, rdi
0x180040536  lea     rax, [rsp+4A0h+Src]
0x18004053b  inc     rdx
0x18004053e  cmp     [rax+rdx*2], r12w
0x180040543  jnz     short loc_18004053B
0x180040545  cmp     rdx, [rcx+18h]
0x180040549  ja      short loc_180040578
0x18004054b  cmp     [rcx+18h], r13
0x18004054f  jbe     short loc_180040556
0x180040551  mov     rsi, [rcx]
0x180040554  jmp     short loc_180040559
0x180040556  mov     rsi, rcx
0x180040559  lea     rbx, [rdx+rdx]
0x18004055d  mov     [rcx+10h], rdx
0x180040561  mov     r8, rbx; Size
0x180040564  lea     rdx, [rsp+4A0h+Src]; Src
0x180040569  mov     rcx, rsi; void *
0x18004056c  call    memmove_0
0x180040571  mov     [rsi+rbx], r12w
0x180040576  jmp     short loc_1800405A6
0x180040578  lea     r9, [rsp+4A0h+Src]
0x18004057d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180040582  jmp     short loc_1800405A6
0x180040584  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x18004058b  mov     [rsp+4A0h+var_480], eax
0x18004058f  mov     r8d, 0B4Dh
0x180040595  lea     rdx, aFileRetrieve; "File::Retrieve"
0x18004059c  mov     ecx, 1
0x1800405a1  call    AslLogCallPrintf
0x1800405a6  xor     edx, edx; Val
0x1800405a8  lea     rcx, [rsp+4A0h+Src]; void *
0x1800405ad  mov     r8d, 410h; Size
0x1800405b3  call    memset_0
0x1800405b8  mov     rax, [r15]
0x1800405bb  lea     rdx, ?InventoryItemValueNameName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameName
0x1800405c2  cmp     cs:qword_18011B728, r13
0x1800405c9  lea     r9, [rsp+4A0h+var_470]
0x1800405ce  lea     r8, [rsp+4A0h+Src]
0x1800405d3  mov     [rsp+4A0h+var_470], 208h
0x1800405db  cmova   rdx, cs:?InventoryItemValueNameName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameName
0x1800405e3  mov     rcx, r15
0x1800405e6  mov     rax, [rax+40h]
0x1800405ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405ef  test    eax, eax
0x1800405f1  js      short loc_18004064B
0x1800405f3  lea     rcx, [r14+0D0h]
0x1800405fa  mov     rdx, rdi
0x1800405fd  lea     rax, [rsp+4A0h+Src]
0x180040602  inc     rdx
0x180040605  cmp     [rax+rdx*2], r12w
0x18004060a  jnz     short loc_180040602
0x18004060c  cmp     rdx, [rcx+18h]
0x180040610  ja      short loc_18004063F
0x180040612  cmp     [rcx+18h], r13
0x180040616  jbe     short loc_18004061D
0x180040618  mov     rsi, [rcx]
0x18004061b  jmp     short loc_180040620
0x18004061d  mov     rsi, rcx
0x180040620  lea     rbx, [rdx+rdx]
0x180040624  mov     [rcx+10h], rdx
0x180040628  mov     r8, rbx; Size
0x18004062b  lea     rdx, [rsp+4A0h+Src]; Src
0x180040630  mov     rcx, rsi; void *
0x180040633  call    memmove_0
0x180040638  mov     [rsi+rbx], r12w
0x18004063d  jmp     short loc_18004066D
0x18004063f  lea     r9, [rsp+4A0h+Src]
0x180040644  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180040649  jmp     short loc_18004066D
0x18004064b  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x180040652  mov     [rsp+4A0h+var_480], eax
0x180040656  mov     r8d, 0B5Dh
0x18004065c  lea     rdx, aFileRetrieve; "File::Retrieve"
0x180040663  mov     ecx, 1
0x180040668  call    AslLogCallPrintf
0x18004066d  xor     edx, edx; Val
0x18004066f  lea     rcx, [rsp+4A0h+Src]; void *
0x180040674  mov     r8d, 410h; Size
0x18004067a  call    memset_0
0x18004067f  mov     rax, [r15]
0x180040682  lea     rdx, ?InventoryItemValueNameOriginalFileName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameOriginalFileName
0x180040689  cmp     cs:qword_18011B748, r13
0x180040690  lea     r9, [rsp+4A0h+var_470]
0x180040695  lea     r8, [rsp+4A0h+Src]
0x18004069a  mov     [rsp+4A0h+var_470], 208h
0x1800406a2  cmova   rdx, cs:?InventoryItemValueNameOriginalFileName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameOriginalFileName
0x1800406aa  mov     rcx, r15
0x1800406ad  mov     rax, [rax+40h]
0x1800406b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406b6  mov     ebx, eax
0x1800406b8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800406bf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800406c4  test    al, al
0x1800406c6  jz      short loc_180040720
0x1800406c8  test    ebx, ebx
0x1800406ca  js      short loc_180040718
0x1800406cc  lea     rcx, [r14+210h]
0x1800406d3  mov     rdx, rdi
0x1800406d6  lea     rax, [rsp+4A0h+Src]
0x1800406db  inc     rdx
0x1800406de  cmp     [rax+rdx*2], r12w
0x1800406e3  jnz     short loc_1800406DB
0x1800406e5  cmp     rdx, [rcx+18h]
0x1800406e9  ja      short loc_18004073F
0x1800406eb  cmp     [rcx+18h], r13
0x1800406ef  jbe     short loc_1800406F6
0x1800406f1  mov     rsi, [rcx]
0x1800406f4  jmp     short loc_1800406F9
0x1800406f6  mov     rsi, rcx
0x1800406f9  lea     rbx, [rdx+rdx]
0x1800406fd  mov     [rcx+10h], rdx
0x180040701  mov     r8, rbx; Size
0x180040704  lea     rdx, [rsp+4A0h+Src]; Src
0x180040709  mov     rcx, rsi; void *
0x18004070c  call    memmove_0
0x180040711  mov     [rsi+rbx], r12w
0x180040716  jmp     short loc_180040775
0x180040718  mov     r8d, 0B6Eh
0x18004071e  jmp     short loc_180040759
0x180040720  test    ebx, ebx
0x180040722  js      short loc_18004074B
0x180040724  lea     rcx, [r14+210h]
0x18004072b  mov     rdx, rdi
0x18004072e  lea     rax, [rsp+4A0h+Src]
0x180040733  inc     rdx
0x180040736  cmp     [rax+rdx*2], r12w
0x18004073b  jnz     short loc_180040733
0x18004073d  jmp     short loc_1800406E5
0x18004073f  lea     r9, [rsp+4A0h+Src]
0x180040744  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180040749  jmp     short loc_180040775
0x18004074b  cmp     ebx, 80070002h
0x180040751  jz      short loc_180040775
0x180040753  mov     r8d, 0B7Ah
0x180040759  lea     r9, aTelcacheprovid_24; "TelCacheProvider::GetItemProperty faile"...
0x180040760  mov     [rsp+4A0h+var_480], ebx
0x180040764  lea     rdx, aFileRetrieve; "File::Retrieve"
0x18004076b  mov     ecx, 1
0x180040770  call    AslLogCallPrintf
0x180040775  xor     edx, edx; Val
0x180040777  lea     rcx, [rsp+4A0h+Src]; void *
0x18004077c  mov     r8d, 410h; Size
0x180040782  call    memset_0
0x180040787  mov     rax, [r15]
0x18004078a  lea     rdx, ?InventoryItemValueNamePublisher@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNamePublisher
0x180040791  cmp     cs:qword_18011B768, r13
0x180040798  lea     r9, [rsp+4A0h+var_470]
0x18004079d  lea     r8, [rsp+4A0h+Src]
0x1800407a2  mov     [rsp+4A0h+var_470], 208h
0x1800407aa  cmova   rdx, cs:?InventoryItemValueNamePublisher@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNamePublisher
0x1800407b2  mov     rcx, r15
0x1800407b5  mov     rax, [rax+40h]
0x1800407b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407be  mov     ebx, eax
0x1800407c0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800407c7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800407cc  test    al, al
0x1800407ce  jz      short loc_180040828
0x1800407d0  test    ebx, ebx
0x1800407d2  js      short loc_180040820
0x1800407d4  lea     rcx, [r14+110h]
0x1800407db  mov     rdx, rdi
0x1800407de  lea     rax, [rsp+4A0h+Src]
0x1800407e3  inc     rdx
0x1800407e6  cmp     [rax+rdx*2], r12w
0x1800407eb  jnz     short loc_1800407E3
0x1800407ed  cmp     rdx, [rcx+18h]
0x1800407f1  ja      short loc_180040847
0x1800407f3  cmp     [rcx+18h], r13
0x1800407f7  jbe     short loc_1800407FE
0x1800407f9  mov     rsi, [rcx]
  ... truncated ...
```
