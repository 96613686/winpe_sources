# File::Retrieve(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x1800c67e0`
- end: `0x1800c76c9`
- name: `?Retrieve@File@@UEAAKPEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `3817`
- prototype: `unsigned int __fastcall(File *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800c38e0`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000d914`
- `0x18000edf0`
- `0x1800295dc`
- `0x1800c67e0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800c7077`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800c7077`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800c744d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800c744d`

## string_xrefs

- `0x1800c6864`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c708f`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c7162`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c71f1`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c7285`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c7384`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c7466`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c74e1`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c7560`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c75f2`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800c767d`: `TelCacheProvider::GetItemProperty failed [%#x]`

## pseudocode

```c
__int64 __fastcall File::Retrieve(File *this, struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  __int64 v4; // rax
  __int64 *v5; // rdx
  int v6; // eax
  __int64 v7; // rdi
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 *v10; // rdx
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 *v14; // rdx
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 *v18; // rdx
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 *v22; // rdx
  int v23; // esi
  char *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 *v28; // rdx
  int v29; // esi
  char *v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 *v34; // rdx
  int v35; // esi
  char *v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 *v40; // rdx
  int v41; // esi
  char *v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r8
  __int64 v45; // rax
  __int64 *v46; // rdx
  int v47; // eax
  __int64 v48; // r8
  __int64 v49; // rax
  __int64 *v50; // rdx
  int v51; // esi
  char *v52; // rcx
  __int64 v53; // r8
  __int64 v54; // r8
  __int64 v55; // rax
  __int64 *v56; // rdx
  int v57; // esi
  char *v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r8
  __int64 v61; // rax
  __int64 *v62; // r14
  __int64 *v63; // rdx
  int v64; // esi
  int v65; // eax
  __int64 v66; // rax
  int v67; // eax
  __int64 v68; // rax
  __int64 *v69; // rdx
  int v70; // esi
  char *v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r8
  __int64 v74; // rax
  __int64 *v75; // rdx
  int v76; // eax
  __int64 v77; // r8
  __int64 v78; // rax
  __int64 *v79; // rdx
  int v80; // esi
  char *v81; // rcx
  __int64 v82; // r8
  __int64 v83; // rax
  __int64 *v84; // rdx
  int v85; // esi
  char *v86; // rcx
  __int64 v87; // r8
  __int64 v88; // r8
  __int64 v89; // rax
  __int64 *v90; // r14
  __int64 *v91; // rdx
  int v92; // esi
  __int64 v93; // rax
  __int64 v94; // rax
  int v95; // eax
  __int64 *v96; // rdx
  int v97; // esi
  __int64 v98; // r8
  __int64 *v99; // rdx
  int v100; // esi
  __int64 v101; // r8
  __int64 v102; // rax
  __int64 *v103; // rdx
  int v104; // esi
  char *v105; // rcx
  __int64 v106; // rax
  __int64 *v107; // rdx
  int v108; // eax
  int v110; // [rsp+30h] [rbp-D0h] BYREF
  int v111; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v112; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v113; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t String[520]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(String, 0, sizeof(String));
  v4 = *(_QWORD *)a2;
  v5 = &File::InventoryItemValueNameProgramId;
  v110 = 520;
  if ( (unsigned __int64)qword_1801217E8 > 7 )
    v5 = (__int64 *)File::InventoryItemValueNameProgramId;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v4 + 64))(
         a2,
         v5,
         String,
         &v110);
  v7 = -1;
  if ( v6 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 2861, "TelCacheProvider::GetItemProperty failed [%#x]", v6);
  }
  else
  {
    v8 = -1;
    do
      ++v8;
    while ( String[v8] );
    std::wstring::_Assign<unsigned short>((char *)this + 80, String, v8);
  }
  memset_0(String, 0, sizeof(String));
  v9 = *(_QWORD *)a2;
  v10 = &File::InventoryItemValueNameFileId;
  v110 = 520;
  if ( (unsigned __int64)qword_180121808 > 7 )
    v10 = (__int64 *)File::InventoryItemValueNameFileId;
  v11 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v9 + 64))(
          a2,
          v10,
          String,
          &v110);
  if ( v11 < 0 )
  {
    if ( v11 != -2147024894 )
      AslLogCallPrintf(1, "File::Retrieve", 2877, "TelCacheProvider::GetItemProperty failed [%#x]", v11);
  }
  else
  {
    v12 = -1;
    do
      ++v12;
    while ( String[v12] );
    std::wstring::_Assign<unsigned short>((char *)this + 112, String, v12);
  }
  memset_0(String, 0, sizeof(String));
  v13 = *(_QWORD *)a2;
  v14 = &File::InventoryItemValueNameFilePath;
  v110 = 520;
  if ( (unsigned __int64)qword_180121828 > 7 )
    v14 = (__int64 *)File::InventoryItemValueNameFilePath;
  v15 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v13 + 64))(
          a2,
          v14,
          String,
          &v110);
  if ( v15 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 2893, "TelCacheProvider::GetItemProperty failed [%#x]", v15);
  }
  else
  {
    v16 = -1;
    do
      ++v16;
    while ( String[v16] );
    std::wstring::_Assign<unsigned short>((char *)this + 16, String, v16);
  }
  memset_0(String, 0, sizeof(String));
  v17 = *(_QWORD *)a2;
  v18 = &File::InventoryItemValueNameName;
  v110 = 520;
  if ( (unsigned __int64)qword_180121868 > 7 )
    v18 = (__int64 *)File::InventoryItemValueNameName;
  v19 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v17 + 64))(
          a2,
          v18,
          String,
          &v110);
  if ( v19 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 2909, "TelCacheProvider::GetItemProperty failed [%#x]", v19);
  }
  else
  {
    v20 = -1;
    do
      ++v20;
    while ( String[v20] );
    std::wstring::_Assign<unsigned short>((char *)this + 208, String, v20);
  }
  memset_0(String, 0, sizeof(String));
  v21 = *(_QWORD *)a2;
  v22 = &File::InventoryItemValueNameOriginalFileName;
  v110 = 520;
  if ( (unsigned __int64)qword_180121888 > 7 )
    v22 = (__int64 *)File::InventoryItemValueNameOriginalFileName;
  v23 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v21 + 64))(
          a2,
          v22,
          String,
          &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v23 >= 0 )
    {
      v24 = (char *)this + 528;
      v25 = -1;
      do
        ++v25;
      while ( String[v25] );
LABEL_41:
      std::wstring::_Assign<unsigned short>(v24, String, v25);
      goto LABEL_45;
    }
    v26 = 2926;
    goto LABEL_44;
  }
  if ( v23 >= 0 )
  {
    v24 = (char *)this + 528;
    v25 = -1;
    do
      ++v25;
    while ( String[v25] );
    goto LABEL_41;
  }
  if ( v23 != -2147024894 )
  {
    v26 = 2938;
LABEL_44:
    AslLogCallPrintf(1, "File::Retrieve", v26, "TelCacheProvider::GetItemProperty failed [%#x]", v23);
  }
LABEL_45:
  memset_0(String, 0, sizeof(String));
  v27 = *(_QWORD *)a2;
  v28 = &File::InventoryItemValueNamePublisher;
  v110 = 520;
  if ( (unsigned __int64)qword_1801218A8 > 7 )
    v28 = (__int64 *)File::InventoryItemValueNamePublisher;
  v29 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v27 + 64))(
          a2,
          v28,
          String,
          &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v29 >= 0 )
    {
      v30 = (char *)this + 272;
      v31 = -1;
      do
        ++v31;
      while ( String[v31] );
LABEL_56:
      std::wstring::_Assign<unsigned short>(v30, String, v31);
      goto LABEL_60;
    }
    v32 = 2956;
    goto LABEL_59;
  }
  if ( v29 >= 0 )
  {
    v30 = (char *)this + 272;
    v31 = -1;
    do
      ++v31;
    while ( String[v31] );
    goto LABEL_56;
  }
  if ( v29 != -2147024894 )
  {
    v32 = 2968;
LABEL_59:
    AslLogCallPrintf(1, "File::Retrieve", v32, "TelCacheProvider::GetItemProperty failed [%#x]", v29);
  }
LABEL_60:
  memset_0(String, 0, sizeof(String));
  v33 = *(_QWORD *)a2;
  v34 = &File::InventoryItemValueNameProductName;
  v110 = 520;
  if ( (unsigned __int64)qword_180121968 > 7 )
    v34 = (__int64 *)File::InventoryItemValueNameProductName;
  v35 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v33 + 64))(
          a2,
          v34,
          String,
          &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v35 >= 0 )
    {
      v36 = (char *)this + 304;
      v37 = -1;
      do
        ++v37;
      while ( String[v37] );
LABEL_71:
      std::wstring::_Assign<unsigned short>(v36, String, v37);
      goto LABEL_75;
    }
    v38 = 2988;
    goto LABEL_74;
  }
  if ( v35 >= 0 )
  {
    v36 = (char *)this + 304;
    v37 = -1;
    do
      ++v37;
    while ( String[v37] );
    goto LABEL_71;
  }
  if ( v35 != -2147024894 )
  {
    v38 = 3000;
LABEL_74:
    AslLogCallPrintf(1, "File::Retrieve", v38, "TelCacheProvider::GetItemProperty failed [%#x]", v35);
  }
LABEL_75:
  memset_0(String, 0, sizeof(String));
  v39 = *(_QWORD *)a2;
  v40 = &File::InventoryItemValueNameBinProductVersion;
  v110 = 520;
  if ( (unsigned __int64)qword_1801219C8 > 7 )
    v40 = (__int64 *)File::InventoryItemValueNameBinProductVersion;
  v41 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v39 + 64))(
          a2,
          v40,
          String,
          &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v41 >= 0 )
    {
      v42 = (char *)this + 368;
      v43 = -1;
      do
        ++v43;
      while ( String[v43] );
LABEL_86:
      std::wstring::_Assign<unsigned short>(v42, String, v43);
      goto LABEL_90;
    }
    v44 = 3018;
    goto LABEL_89;
  }
  if ( v41 >= 0 )
  {
    v42 = (char *)this + 368;
    v43 = -1;
    do
      ++v43;
    while ( String[v43] );
    goto LABEL_86;
  }
  if ( v41 != -2147024894 )
  {
    v44 = 3030;
LABEL_89:
    AslLogCallPrintf(1, "File::Retrieve", v44, "TelCacheProvider::GetItemProperty failed [%#x]", v41);
  }
LABEL_90:
  memset_0(String, 0, sizeof(String));
  v45 = *(_QWORD *)a2;
  v46 = &File::InventoryItemValueNameLinkDate;
  v110 = 520;
  if ( (unsigned __int64)qword_1801219A8 > 7 )
    v46 = (__int64 *)File::InventoryItemValueNameLinkDate;
  v47 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v45 + 64))(
          a2,
          v46,
          String,
          &v110);
  if ( v47 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 3044, "TelCacheProvider::GetItemProperty failed [%#x]", v47);
  }
  else
  {
    v48 = -1;
    do
      ++v48;
    while ( String[v48] );
    std::wstring::_Assign<unsigned short>((char *)this + 560, String, v48);
  }
  memset_0(String, 0, sizeof(String));
  v49 = *(_QWORD *)a2;
  v50 = &File::InventoryItemValueNameProductVersion;
  v110 = 520;
  if ( (unsigned __int64)qword_180121988 > 7 )
    v50 = (__int64 *)File::InventoryItemValueNameProductVersion;
  v51 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v49 + 64))(
          a2,
          v50,
          String,
          &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v51 >= 0 )
    {
      v52 = (char *)this + 336;
      v53 = -1;
      do
        ++v53;
      while ( String[v53] );
LABEL_108:
      std::wstring::_Assign<unsigned short>(v52, String, v53);
      goto LABEL_112;
    }
    v54 = 3059;
    goto LABEL_111;
  }
  if ( v51 >= 0 )
  {
    v52 = (char *)this + 560;
    v53 = -1;
    do
      ++v53;
    while ( String[v53] );
    goto LABEL_108;
  }
  if ( v51 != -2147024894 )
  {
    v54 = 3071;
LABEL_111:
    AslLogCallPrintf(1, "File::Retrieve", v54, "TelCacheProvider::GetItemProperty failed [%#x]", v51);
  }
LABEL_112:
  memset_0(String, 0, sizeof(String));
  v55 = *(_QWORD *)a2;
  v56 = &File::InventoryItemValueNameVersion;
  v110 = 520;
  if ( (unsigned __int64)qword_1801218C8 > 7 )
    v56 = (__int64 *)File::InventoryItemValueNameVersion;
  v57 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v55 + 64))(
          a2,
          v56,
          String,
          &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v57 >= 0 )
    {
      v58 = (char *)this + 240;
      v59 = -1;
      do
        ++v59;
      while ( String[v59] );
LABEL_123:
      std::wstring::_Assign<unsigned short>(v58, String, v59);
      goto LABEL_127;
    }
    v60 = 3089;
    goto LABEL_126;
  }
  if ( v57 >= 0 )
  {
    v58 = (char *)this + 240;
    v59 = -1;
    do
      ++v59;
    while ( String[v59] );
    goto LABEL_123;
  }
  if ( v57 != -2147024894 )
  {
    v60 = 3101;
LABEL_126:
    AslLogCallPrintf(1, "File::Retrieve", v60, "TelCacheProvider::GetItemProperty failed [%#x]", v57);
  }
LABEL_127:
  v61 = *(_QWORD *)a2;
  v62 = &File::InventoryItemValueNameLanguage;
  v63 = &File::InventoryItemValueNameLanguage;
  v111 = 0;
  if ( (unsigned __int64)qword_1801218E8 > 7 )
    v63 = (__int64 *)File::InventoryItemValueNameLanguage;
  v64 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(v61 + 80))(
          a2,
          v63,
          &v111);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v64 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3116, "TelCacheProvider::GetItemProperty failed [%#x]", v64);
      goto LABEL_140;
    }
    goto LABEL_133;
  }
  if ( v64 >= 0 )
  {
LABEL_133:
    v65 = v111;
LABEL_138:
    *((_DWORD *)this + 198) = v65;
    goto LABEL_140;
  }
  memset_0(String, 0, sizeof(String));
  v66 = *(_QWORD *)a2;
  v110 = 520;
  if ( (unsigned __int64)qword_1801218E8 > 7 )
    v62 = (__int64 *)File::InventoryItemValueNameLanguage;
  v67 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v66 + 64))(
          a2,
          v62,
          String,
          &v110);
  if ( v67 >= 0 )
  {
    v65 = _o__wtoi(String);
    goto LABEL_138;
  }
  AslLogCallPrintf(1, "File::Retrieve", 3138, "TelCacheProvider::GetItemProperty failed [%#x]", v67);
LABEL_140:
  memset_0(String, 0, sizeof(String));
  v68 = *(_QWORD *)a2;
  v69 = &File::InventoryItemValueNameBinFileVersion;
  v110 = 520;
  if ( (unsigned __int64)qword_180121908 > 7 )
    v69 = (__int64 *)File::InventoryItemValueNameBinFileVersion;
  v70 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v68 + 64))(
          a2,
          v69,
          String,
          &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v70 >= 0 )
    {
      v71 = (char *)this + 176;
      v72 = -1;
      do
        ++v72;
      while ( String[v72] );
LABEL_151:
      std::wstring::_Assign<unsigned short>(v71, String, v72);
      goto LABEL_155;
    }
    v73 = 3157;
    goto LABEL_154;
  }
  if ( v70 >= 0 )
  {
    v71 = (char *)this + 176;
    v72 = -1;
    do
      ++v72;
    while ( String[v72] );
    goto LABEL_151;
  }
  if ( v70 != -2147024894 )
  {
    v73 = 3169;
LABEL_154:
    AslLogCallPrintf(1, "File::Retrieve", v73, "TelCacheProvider::GetItemProperty failed [%#x]", v70);
  }
LABEL_155:
  memset_0(String, 0, sizeof(String));
  v74 = *(_QWORD *)a2;
  v75 = &File::InventoryItemValueNameBinaryType;
  v110 = 520;
  if ( (unsigned __int64)qword_180121928 > 7 )
    v75 = (__int64 *)File::InventoryItemValueNameBinaryType;
  v76 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v74 + 64))(
          a2,
          v75,
          String,
          &v110);
  if ( v76 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 3186, "TelCacheProvider::GetItemProperty failed [%#x]", v76);
  }
  else
  {
    v77 = -1;
    do
      ++v77;
    while ( String[v77] );
    std::wstring::_Assign<unsigned short>((char *)this + 144, String, v77);
  }
  memset_0(String, 0, sizeof(String));
  v78 = *(_QWORD *)a2;
  v79 = &File::InventoryItemValueNameAppxPackageFullName;
  v110 = 520;
  if ( (unsigned __int64)qword_180121A48 > 7 )
    v79 = (__int64 *)File::InventoryItemValueNameAppxPackageFullName;
  v80 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v78 + 64))(
          a2,
          v79,
          String,
          &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v80 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3203, "TelCacheProvider::GetItemProperty failed [%#x]", v80);
      goto LABEL_174;
    }
    v81 = (char *)this + 656;
    v82 = -1;
    do
      ++v82;
    while ( String[v82] );
  }
  else
  {
    if ( v80 < 0 )
      goto LABEL_174;
    v81 = (char *)this + 656;
    v82 = -1;
    do
      ++v82;
    while ( String[v82] );
  }
  std::wstring::_Assign<unsigned short>(v81, String, v82);
LABEL_174:
  memset_0(String, 0, sizeof(String));
  v83 = *(_QWORD *)a2;
  v84 = &File::InventoryItemValueNameAppxPackageRelativeId;
  v110 = 520;
  if ( (unsigned __int64)qword_180121A68 > 7 )
    v84 = (__int64 *)File::InventoryItemValueNameAppxPackageRelativeId;
  v85 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v83 + 64))(
          a2,
          v84,
          String,
          &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v85 >= 0 )
    {
      v86 = (char *)this + 688;
      v87 = -1;
      do
        ++v87;
      while ( String[v87] );
LABEL_185:
      std::wstring::_Assign<unsigned short>(v86, String, v87);
      goto LABEL_189;
    }
    v88 = 3228;
    goto LABEL_188;
  }
  if ( v85 >= 0 )
  {
    v86 = (char *)this + 688;
    v87 = -1;
    do
      ++v87;
    while ( String[v87] );
    goto LABEL_185;
  }
  if ( v85 != -2147024894 )
  {
    v88 = 3240;
LABEL_188:
    AslLogCallPrintf(1, "File::Retrieve", v88, "TelCacheProvider::GetItemProperty failed [%#x]", v85);
  }
LABEL_189:
  v89 = *(_QWORD *)a2;
  v90 = &File::InventoryItemValueNameFileSize;
  v91 = &File::InventoryItemValueNameFileSize;
  v112 = 0;
  if ( (unsigned __int64)qword_180121948 > 7 )
    v91 = (__int64 *)File::InventoryItemValueNameFileSize;
  v92 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, __int64 *))(v89 + 72))(
          a2,
          v91,
          &v112);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v92 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3255, "TelCacheProvider::GetItemProperty failed [%#x]", v92);
      goto LABEL_202;
    }
    goto LABEL_195;
  }
  if ( v92 >= 0 )
  {
LABEL_195:
    v93 = v112;
LABEL_200:
    *((_QWORD *)this + 97) = v93;
    goto LABEL_202;
  }
  memset_0(String, 0, sizeof(String));
  v94 = *(_QWORD *)a2;
  v110 = 520;
  if ( (unsigned __int64)qword_180121948 > 7 )
    v90 = (__int64 *)File::InventoryItemValueNameFileSize;
  v95 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v94 + 64))(
          a2,
          v90,
          String,
          &v110);
  if ( v95 >= 0 )
  {
    v93 = _wtoi64(String);
    goto LABEL_200;
  }
  AslLogCallPrintf(1, "File::Retrieve", 3277, "TelCacheProvider::GetItemProperty failed [%#x]", v95);
LABEL_202:
  v96 = &File::InventoryItemValueNameIsPeFile;
  if ( (unsigned __int64)qword_1801219E8 > 7 )
    v96 = (__int64 *)File::InventoryItemValueNameIsPeFile;
  v97 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 48LL))(
          a2,
          v96,
          (char *)this + 796);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v97 >= 0 )
      goto LABEL_212;
    v98 = 3289;
    goto LABEL_211;
  }
  if ( v97 == -2147024894 )
  {
    *((_BYTE *)this + 796) = 1;
    goto LABEL_212;
  }
  if ( v97 < 0 )
  {
    v98 = 3301;
LABEL_211:
    AslLogCallPrintf(1, "File::Retrieve", v98, "TelCacheProvider::GetItemProperty failed [%#x]", v97);
  }
LABEL_212:
  v99 = &File::InventoryItemValueNameIsOsComponent;
  if ( (unsigned __int64)qword_180121A08 > 7 )
    v99 = (__int64 *)File::InventoryItemValueNameIsOsComponent;
  v100 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 48LL))(
           a2,
           v99,
           (char *)this + 797);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v100 >= 0 )
      goto LABEL_222;
    v101 = 3312;
    goto LABEL_221;
  }
  if ( v100 == -2147024894 )
  {
    *((_BYTE *)this + 797) = 0;
    goto LABEL_222;
  }
  if ( v100 < 0 )
  {
    v101 = 3324;
LABEL_221:
    AslLogCallPrintf(1, "File::Retrieve", v101, "TelCacheProvider::GetItemProperty failed [%#x]", v100);
  }
LABEL_222:
  memset_0(String, 0, sizeof(String));
  v102 = *(_QWORD *)a2;
  v103 = &File::InventoryItemValueNameSha256;
  v110 = 520;
  if ( (unsigned __int64)qword_180121A88 > 7 )
    v103 = (__int64 *)File::InventoryItemValueNameSha256;
  v104 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v102 + 64))(
           a2,
           v103,
           String,
           &v110);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v104 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3342, "TelCacheProvider::GetItemProperty failed [%#x]", v104);
      goto LABEL_234;
    }
    v105 = (char *)this + 720;
    do
      ++v7;
    while ( String[v7] );
  }
  else
  {
    if ( v104 < 0 )
      goto LABEL_234;
    v105 = (char *)this + 720;
    do
      ++v7;
    while ( String[v7] );
  }
  std::wstring::_Assign<unsigned short>(v105, String, v7);
LABEL_234:
  v106 = *(_QWORD *)a2;
  v107 = &File::InventoryItemValueNameUsn;
  v113 = 0;
  if ( (unsigned __int64)qword_180121A28 > 7 )
    v107 = (__int64 *)File::InventoryItemValueNameUsn;
  v108 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, __int64 *))(v106 + 8))(
           a2,
           v107,
           &v113);
  if ( v108 < 0 )
    AslLogCallPrintf(1, "File::Retrieve", 3363, "TelCacheProvider::GetItemProperty failed [%#x]", v108);
  else
    *((_QWORD *)this + 98) = v113;
  return 0;
}

```

## disassembly

```asm
0x1800c67e0  mov     [rsp-8+arg_10], rbx
0x1800c67e5  push    rbp
0x1800c67e6  push    rsi
0x1800c67e7  push    rdi
0x1800c67e8  push    r12
0x1800c67ea  push    r13
0x1800c67ec  push    r14
0x1800c67ee  push    r15
0x1800c67f0  lea     rbp, [rsp-370h]
0x1800c67f8  sub     rsp, 470h
0x1800c67ff  mov     rax, cs:__security_cookie
0x1800c6806  xor     rax, rsp
0x1800c6809  mov     [rbp+3A0h+var_40], rax
0x1800c6810  mov     r15, rdx
0x1800c6813  mov     rbx, rcx
0x1800c6816  xor     edx, edx; Val
0x1800c6818  lea     rcx, [rsp+4A0h+String]; void *
0x1800c681d  mov     r8d, 410h; Size
0x1800c6823  call    memset_0
0x1800c6828  mov     rax, [r15]
0x1800c682b  lea     rdx, ?InventoryItemValueNameProgramId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProgramId
0x1800c6832  cmp     cs:qword_1801217E8, 7
0x1800c683a  lea     r9, [rsp+4A0h+var_470]
0x1800c683f  lea     r8, [rsp+4A0h+String]
0x1800c6844  mov     [rsp+4A0h+var_470], 208h
0x1800c684c  cmova   rdx, cs:?InventoryItemValueNameProgramId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProgramId
0x1800c6854  mov     rcx, r15
0x1800c6857  mov     rax, [rax+40h]
0x1800c685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6860  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c6864  lea     r14, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x1800c686b  xor     r12d, r12d
0x1800c686e  lea     rsi, aFileRetrieve; "File::Retrieve"
0x1800c6875  mov     r13d, 1
0x1800c687b  test    eax, eax
0x1800c687d  js      short loc_1800C68A1
0x1800c687f  lea     rcx, [rbx+50h]
0x1800c6883  mov     r8, rdi
0x1800c6886  lea     rax, [rsp+4A0h+String]
0x1800c688b  inc     r8
0x1800c688e  cmp     [rax+r8*2], r12w
0x1800c6893  jnz     short loc_1800C688B
0x1800c6895  lea     rdx, [rsp+4A0h+String]
0x1800c689a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c689f  jmp     short loc_1800C68B9
0x1800c68a1  mov     r9, r14
0x1800c68a4  mov     [rsp+4A0h+var_480], eax
0x1800c68a8  mov     r8d, 0B2Dh
0x1800c68ae  mov     rdx, rsi
0x1800c68b1  mov     ecx, r13d
0x1800c68b4  call    AslLogCallPrintf
0x1800c68b9  xor     edx, edx; Val
0x1800c68bb  lea     rcx, [rsp+4A0h+String]; void *
0x1800c68c0  mov     r8d, 410h; Size
0x1800c68c6  call    memset_0
0x1800c68cb  mov     rax, [r15]
0x1800c68ce  lea     rdx, ?InventoryItemValueNameFileId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFileId
0x1800c68d5  cmp     cs:qword_180121808, 7
0x1800c68dd  lea     r9, [rsp+4A0h+var_470]
0x1800c68e2  lea     r8, [rsp+4A0h+String]
0x1800c68e7  mov     [rsp+4A0h+var_470], 208h
0x1800c68ef  cmova   rdx, cs:?InventoryItemValueNameFileId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFileId
0x1800c68f7  mov     rcx, r15
0x1800c68fa  mov     rax, [rax+40h]
0x1800c68fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6903  test    eax, eax
0x1800c6905  js      short loc_1800C6929
0x1800c6907  lea     rcx, [rbx+70h]
0x1800c690b  mov     r8, rdi
0x1800c690e  lea     rax, [rsp+4A0h+String]
0x1800c6913  inc     r8
0x1800c6916  cmp     [rax+r8*2], r12w
0x1800c691b  jnz     short loc_1800C6913
0x1800c691d  lea     rdx, [rsp+4A0h+String]
0x1800c6922  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c6927  jmp     short loc_1800C6948
0x1800c6929  cmp     eax, 80070002h
0x1800c692e  jz      short loc_1800C6948
0x1800c6930  mov     r9, r14
0x1800c6933  mov     [rsp+4A0h+var_480], eax
0x1800c6937  mov     r8d, 0B3Dh
0x1800c693d  mov     rdx, rsi
0x1800c6940  mov     ecx, r13d
0x1800c6943  call    AslLogCallPrintf
0x1800c6948  xor     edx, edx; Val
0x1800c694a  lea     rcx, [rsp+4A0h+String]; void *
0x1800c694f  mov     r8d, 410h; Size
0x1800c6955  call    memset_0
0x1800c695a  mov     rax, [r15]
0x1800c695d  lea     rdx, ?InventoryItemValueNameFilePath@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFilePath
0x1800c6964  cmp     cs:qword_180121828, 7
0x1800c696c  lea     r9, [rsp+4A0h+var_470]
0x1800c6971  lea     r8, [rsp+4A0h+String]
0x1800c6976  mov     [rsp+4A0h+var_470], 208h
0x1800c697e  cmova   rdx, cs:?InventoryItemValueNameFilePath@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFilePath
0x1800c6986  mov     rcx, r15
0x1800c6989  mov     rax, [rax+40h]
0x1800c698d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6992  test    eax, eax
0x1800c6994  js      short loc_1800C69B8
0x1800c6996  lea     rcx, [rbx+10h]
0x1800c699a  mov     r8, rdi
0x1800c699d  lea     rax, [rsp+4A0h+String]
0x1800c69a2  inc     r8
0x1800c69a5  cmp     [rax+r8*2], r12w
0x1800c69aa  jnz     short loc_1800C69A2
0x1800c69ac  lea     rdx, [rsp+4A0h+String]
0x1800c69b1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c69b6  jmp     short loc_1800C69D0
0x1800c69b8  mov     r9, r14
0x1800c69bb  mov     [rsp+4A0h+var_480], eax
0x1800c69bf  mov     r8d, 0B4Dh
0x1800c69c5  mov     rdx, rsi
0x1800c69c8  mov     ecx, r13d
0x1800c69cb  call    AslLogCallPrintf
0x1800c69d0  xor     edx, edx; Val
0x1800c69d2  lea     rcx, [rsp+4A0h+String]; void *
0x1800c69d7  mov     r8d, 410h; Size
0x1800c69dd  call    memset_0
0x1800c69e2  mov     rax, [r15]
0x1800c69e5  lea     rdx, ?InventoryItemValueNameName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameName
0x1800c69ec  cmp     cs:qword_180121868, 7
0x1800c69f4  lea     r9, [rsp+4A0h+var_470]
0x1800c69f9  lea     r8, [rsp+4A0h+String]
0x1800c69fe  mov     [rsp+4A0h+var_470], 208h
0x1800c6a06  cmova   rdx, cs:?InventoryItemValueNameName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameName
0x1800c6a0e  mov     rcx, r15
0x1800c6a11  mov     rax, [rax+40h]
0x1800c6a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6a1a  test    eax, eax
0x1800c6a1c  js      short loc_1800C6A43
0x1800c6a1e  lea     rcx, [rbx+0D0h]
0x1800c6a25  mov     r8, rdi
0x1800c6a28  lea     rax, [rsp+4A0h+String]
0x1800c6a2d  inc     r8
0x1800c6a30  cmp     [rax+r8*2], r12w
0x1800c6a35  jnz     short loc_1800C6A2D
0x1800c6a37  lea     rdx, [rsp+4A0h+String]
0x1800c6a3c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c6a41  jmp     short loc_1800C6A5B
0x1800c6a43  mov     r9, r14
0x1800c6a46  mov     [rsp+4A0h+var_480], eax
0x1800c6a4a  mov     r8d, 0B5Dh
0x1800c6a50  mov     rdx, rsi
0x1800c6a53  mov     ecx, r13d
0x1800c6a56  call    AslLogCallPrintf
0x1800c6a5b  xor     edx, edx; Val
0x1800c6a5d  lea     rcx, [rsp+4A0h+String]; void *
0x1800c6a62  mov     r8d, 410h; Size
0x1800c6a68  call    memset_0
0x1800c6a6d  mov     rax, [r15]
0x1800c6a70  lea     rdx, ?InventoryItemValueNameOriginalFileName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameOriginalFileName
0x1800c6a77  cmp     cs:qword_180121888, 7
0x1800c6a7f  lea     r9, [rsp+4A0h+var_470]
0x1800c6a84  lea     r8, [rsp+4A0h+String]
0x1800c6a89  mov     [rsp+4A0h+var_470], 208h
0x1800c6a91  cmova   rdx, cs:?InventoryItemValueNameOriginalFileName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameOriginalFileName
0x1800c6a99  mov     rcx, r15
0x1800c6a9c  mov     rax, [rax+40h]
0x1800c6aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6aa5  mov     esi, eax
0x1800c6aa7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800c6aae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800c6ab3  test    al, al
0x1800c6ab5  jz      short loc_1800C6ADE
0x1800c6ab7  test    esi, esi
0x1800c6ab9  js      short loc_1800C6AD6
0x1800c6abb  lea     rcx, [rbx+210h]
0x1800c6ac2  mov     r8, rdi
0x1800c6ac5  lea     rax, [rsp+4A0h+String]
0x1800c6aca  inc     r8
0x1800c6acd  cmp     [rax+r8*2], r12w
0x1800c6ad2  jnz     short loc_1800C6ACA
0x1800c6ad4  jmp     short loc_1800C6AFB
0x1800c6ad6  mov     r8d, 0B6Eh
0x1800c6adc  jmp     short loc_1800C6B15
0x1800c6ade  test    esi, esi
0x1800c6ae0  js      short loc_1800C6B07
0x1800c6ae2  lea     rcx, [rbx+210h]
0x1800c6ae9  mov     r8, rdi
0x1800c6aec  lea     rax, [rsp+4A0h+String]
0x1800c6af1  inc     r8
0x1800c6af4  cmp     [rax+r8*2], r12w
0x1800c6af9  jnz     short loc_1800C6AF1
0x1800c6afb  lea     rdx, [rsp+4A0h+String]
0x1800c6b00  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c6b05  jmp     short loc_1800C6B2B
0x1800c6b07  cmp     esi, 80070002h
0x1800c6b0d  jz      short loc_1800C6B2B
0x1800c6b0f  mov     r8d, 0B7Ah
0x1800c6b15  mov     r9, r14
0x1800c6b18  mov     [rsp+4A0h+var_480], esi
0x1800c6b1c  lea     rdx, aFileRetrieve; "File::Retrieve"
0x1800c6b23  mov     ecx, r13d
0x1800c6b26  call    AslLogCallPrintf
0x1800c6b2b  xor     edx, edx; Val
0x1800c6b2d  lea     rcx, [rsp+4A0h+String]; void *
0x1800c6b32  mov     r8d, 410h; Size
0x1800c6b38  call    memset_0
0x1800c6b3d  mov     rax, [r15]
0x1800c6b40  lea     rdx, ?InventoryItemValueNamePublisher@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNamePublisher
0x1800c6b47  cmp     cs:qword_1801218A8, 7
0x1800c6b4f  lea     r9, [rsp+4A0h+var_470]
0x1800c6b54  lea     r8, [rsp+4A0h+String]
0x1800c6b59  mov     [rsp+4A0h+var_470], 208h
0x1800c6b61  cmova   rdx, cs:?InventoryItemValueNamePublisher@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNamePublisher
0x1800c6b69  mov     rcx, r15
0x1800c6b6c  mov     rax, [rax+40h]
0x1800c6b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6b75  mov     esi, eax
0x1800c6b77  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800c6b7e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800c6b83  test    al, al
0x1800c6b85  jz      short loc_1800C6BAE
0x1800c6b87  test    esi, esi
0x1800c6b89  js      short loc_1800C6BA6
0x1800c6b8b  lea     rcx, [rbx+110h]
0x1800c6b92  mov     r8, rdi
0x1800c6b95  lea     rax, [rsp+4A0h+String]
0x1800c6b9a  inc     r8
0x1800c6b9d  cmp     [rax+r8*2], r12w
0x1800c6ba2  jnz     short loc_1800C6B9A
0x1800c6ba4  jmp     short loc_1800C6BCB
0x1800c6ba6  mov     r8d, 0B8Ch
0x1800c6bac  jmp     short loc_1800C6BE5
0x1800c6bae  test    esi, esi
0x1800c6bb0  js      short loc_1800C6BD7
0x1800c6bb2  lea     rcx, [rbx+110h]
0x1800c6bb9  mov     r8, rdi
0x1800c6bbc  lea     rax, [rsp+4A0h+String]
0x1800c6bc1  inc     r8
0x1800c6bc4  cmp     [rax+r8*2], r12w
0x1800c6bc9  jnz     short loc_1800C6BC1
0x1800c6bcb  lea     rdx, [rsp+4A0h+String]
0x1800c6bd0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c6bd5  jmp     short loc_1800C6BFB
0x1800c6bd7  cmp     esi, 80070002h
0x1800c6bdd  jz      short loc_1800C6BFB
0x1800c6bdf  mov     r8d, 0B98h
0x1800c6be5  mov     r9, r14
0x1800c6be8  mov     [rsp+4A0h+var_480], esi
0x1800c6bec  lea     rdx, aFileRetrieve; "File::Retrieve"
0x1800c6bf3  mov     ecx, r13d
0x1800c6bf6  call    AslLogCallPrintf
0x1800c6bfb  xor     edx, edx; Val
0x1800c6bfd  lea     rcx, [rsp+4A0h+String]; void *
0x1800c6c02  mov     r8d, 410h; Size
0x1800c6c08  call    memset_0
0x1800c6c0d  mov     rax, [r15]
0x1800c6c10  lea     rdx, ?InventoryItemValueNameProductName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProductName
0x1800c6c17  cmp     cs:qword_180121968, 7
0x1800c6c1f  lea     r9, [rsp+4A0h+var_470]
0x1800c6c24  lea     r8, [rsp+4A0h+String]
0x1800c6c29  mov     [rsp+4A0h+var_470], 208h
0x1800c6c31  cmova   rdx, cs:?InventoryItemValueNameProductName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProductName
0x1800c6c39  mov     rcx, r15
0x1800c6c3c  mov     rax, [rax+40h]
0x1800c6c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c45  mov     esi, eax
0x1800c6c47  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800c6c4e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800c6c53  test    al, al
0x1800c6c55  jz      short loc_1800C6C7E
0x1800c6c57  test    esi, esi
0x1800c6c59  js      short loc_1800C6C76
0x1800c6c5b  lea     rcx, [rbx+130h]
0x1800c6c62  mov     r8, rdi
0x1800c6c65  lea     rax, [rsp+4A0h+String]
0x1800c6c6a  inc     r8
0x1800c6c6d  cmp     [rax+r8*2], r12w
0x1800c6c72  jnz     short loc_1800C6C6A
0x1800c6c74  jmp     short loc_1800C6C9B
0x1800c6c76  mov     r8d, 0BACh
0x1800c6c7c  jmp     short loc_1800C6CB5
0x1800c6c7e  test    esi, esi
0x1800c6c80  js      short loc_1800C6CA7
0x1800c6c82  lea     rcx, [rbx+130h]
0x1800c6c89  mov     r8, rdi
0x1800c6c8c  lea     rax, [rsp+4A0h+String]
0x1800c6c91  inc     r8
0x1800c6c94  cmp     [rax+r8*2], r12w
0x1800c6c99  jnz     short loc_1800C6C91
0x1800c6c9b  lea     rdx, [rsp+4A0h+String]
0x1800c6ca0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c6ca5  jmp     short loc_1800C6CCB
0x1800c6ca7  cmp     esi, 80070002h
0x1800c6cad  jz      short loc_1800C6CCB
0x1800c6caf  mov     r8d, 0BB8h
0x1800c6cb5  mov     r9, r14
0x1800c6cb8  mov     [rsp+4A0h+var_480], esi
0x1800c6cbc  lea     rdx, aFileRetrieve; "File::Retrieve"
0x1800c6cc3  mov     ecx, r13d
0x1800c6cc6  call    AslLogCallPrintf
0x1800c6ccb  xor     edx, edx; Val
0x1800c6ccd  lea     rcx, [rsp+4A0h+String]; void *
0x1800c6cd2  mov     r8d, 410h; Size
0x1800c6cd8  call    memset_0
0x1800c6cdd  mov     rax, [r15]
0x1800c6ce0  lea     rdx, ?InventoryItemValueNameBinProductVersion@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameBinProductVersion
0x1800c6ce7  cmp     cs:qword_1801219C8, 7
  ... truncated ...
```
