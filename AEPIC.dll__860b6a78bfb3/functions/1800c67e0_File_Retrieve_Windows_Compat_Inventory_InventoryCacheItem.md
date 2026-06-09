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
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 *v29; // rdx
  int v30; // esi
  char *v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r8
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 *v36; // rdx
  int v37; // esi
  char *v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r8
  __int64 v41; // r8
  __int64 v42; // rax
  __int64 *v43; // rdx
  int v44; // esi
  char *v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r8
  __int64 v48; // r8
  __int64 v49; // rax
  __int64 *v50; // rdx
  int v51; // eax
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 *v54; // rdx
  int v55; // esi
  char *v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r8
  __int64 v59; // r8
  __int64 v60; // rax
  __int64 *v61; // rdx
  int v62; // esi
  char *v63; // rcx
  __int64 v64; // r8
  __int64 v65; // r8
  __int64 v66; // r8
  __int64 v67; // rax
  __int64 *v68; // r14
  __int64 *v69; // rdx
  int v70; // esi
  int v71; // eax
  __int64 v72; // rax
  int v73; // eax
  __int64 v74; // rax
  __int64 *v75; // rdx
  int v76; // esi
  char *v77; // rcx
  __int64 v78; // r8
  __int64 v79; // r8
  __int64 v80; // r8
  __int64 v81; // rax
  __int64 *v82; // rdx
  int v83; // eax
  __int64 v84; // r8
  __int64 v85; // rax
  __int64 *v86; // rdx
  int v87; // esi
  char *v88; // rcx
  __int64 v89; // r8
  __int64 v90; // r8
  __int64 v91; // rax
  __int64 *v92; // rdx
  int v93; // esi
  char *v94; // rcx
  __int64 v95; // r8
  __int64 v96; // r8
  __int64 v97; // r8
  __int64 v98; // rax
  __int64 *v99; // r14
  __int64 *v100; // rdx
  int v101; // esi
  __int64 v102; // rax
  __int64 v103; // rax
  int v104; // eax
  __int64 *v105; // rdx
  int v106; // esi
  __int64 v107; // r8
  __int64 *v108; // rdx
  int v109; // esi
  __int64 v110; // r8
  __int64 v111; // rax
  __int64 *v112; // rdx
  int v113; // esi
  char *v114; // rcx
  __int64 v115; // rax
  __int64 *v116; // rdx
  int v117; // eax
  int v119; // [rsp+30h] [rbp-D0h] BYREF
  int v120; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v121; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v122; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t String[520]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(String, 0, sizeof(String));
  v4 = *(_QWORD *)a2;
  v5 = &File::InventoryItemValueNameProgramId;
  v119 = 520;
  if ( (unsigned __int64)qword_1801217E8 > 7 )
    v5 = (__int64 *)File::InventoryItemValueNameProgramId;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v4 + 64))(
         a2,
         v5,
         String,
         &v119);
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
    std::wstring::_Assign<unsigned short>((char *)this + 80, String);
  }
  memset_0(String, 0, sizeof(String));
  v9 = *(_QWORD *)a2;
  v10 = &File::InventoryItemValueNameFileId;
  v119 = 520;
  if ( (unsigned __int64)qword_180121808 > 7 )
    v10 = (__int64 *)File::InventoryItemValueNameFileId;
  v11 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v9 + 64))(
          a2,
          v10,
          String,
          &v119);
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
    std::wstring::_Assign<unsigned short>((char *)this + 112, String);
  }
  memset_0(String, 0, sizeof(String));
  v13 = *(_QWORD *)a2;
  v14 = &File::InventoryItemValueNameFilePath;
  v119 = 520;
  if ( (unsigned __int64)qword_180121828 > 7 )
    v14 = (__int64 *)File::InventoryItemValueNameFilePath;
  v15 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v13 + 64))(
          a2,
          v14,
          String,
          &v119);
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
    std::wstring::_Assign<unsigned short>((char *)this + 16, String);
  }
  memset_0(String, 0, sizeof(String));
  v17 = *(_QWORD *)a2;
  v18 = &File::InventoryItemValueNameName;
  v119 = 520;
  if ( (unsigned __int64)qword_180121868 > 7 )
    v18 = (__int64 *)File::InventoryItemValueNameName;
  v19 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v17 + 64))(
          a2,
          v18,
          String,
          &v119);
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
    std::wstring::_Assign<unsigned short>((char *)this + 208, String);
  }
  memset_0(String, 0, sizeof(String));
  v21 = *(_QWORD *)a2;
  v22 = &File::InventoryItemValueNameOriginalFileName;
  v119 = 520;
  if ( (unsigned __int64)qword_180121888 > 7 )
    v22 = (__int64 *)File::InventoryItemValueNameOriginalFileName;
  v23 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v21 + 64))(
          a2,
          v22,
          String,
          &v119);
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
      std::wstring::_Assign<unsigned short>(v24, String);
      goto LABEL_45;
    }
    v26 = 2926;
    goto LABEL_44;
  }
  if ( v23 >= 0 )
  {
    v24 = (char *)this + 528;
    v27 = -1;
    do
      ++v27;
    while ( String[v27] );
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
  v28 = *(_QWORD *)a2;
  v29 = &File::InventoryItemValueNamePublisher;
  v119 = 520;
  if ( (unsigned __int64)qword_1801218A8 > 7 )
    v29 = (__int64 *)File::InventoryItemValueNamePublisher;
  v30 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v28 + 64))(
          a2,
          v29,
          String,
          &v119);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v30 >= 0 )
    {
      v31 = (char *)this + 272;
      v32 = -1;
      do
        ++v32;
      while ( String[v32] );
LABEL_56:
      std::wstring::_Assign<unsigned short>(v31, String);
      goto LABEL_60;
    }
    v33 = 2956;
    goto LABEL_59;
  }
  if ( v30 >= 0 )
  {
    v31 = (char *)this + 272;
    v34 = -1;
    do
      ++v34;
    while ( String[v34] );
    goto LABEL_56;
  }
  if ( v30 != -2147024894 )
  {
    v33 = 2968;
LABEL_59:
    AslLogCallPrintf(1, "File::Retrieve", v33, "TelCacheProvider::GetItemProperty failed [%#x]", v30);
  }
LABEL_60:
  memset_0(String, 0, sizeof(String));
  v35 = *(_QWORD *)a2;
  v36 = &File::InventoryItemValueNameProductName;
  v119 = 520;
  if ( (unsigned __int64)qword_180121968 > 7 )
    v36 = (__int64 *)File::InventoryItemValueNameProductName;
  v37 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v35 + 64))(
          a2,
          v36,
          String,
          &v119);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v37 >= 0 )
    {
      v38 = (char *)this + 304;
      v39 = -1;
      do
        ++v39;
      while ( String[v39] );
LABEL_71:
      std::wstring::_Assign<unsigned short>(v38, String);
      goto LABEL_75;
    }
    v40 = 2988;
    goto LABEL_74;
  }
  if ( v37 >= 0 )
  {
    v38 = (char *)this + 304;
    v41 = -1;
    do
      ++v41;
    while ( String[v41] );
    goto LABEL_71;
  }
  if ( v37 != -2147024894 )
  {
    v40 = 3000;
LABEL_74:
    AslLogCallPrintf(1, "File::Retrieve", v40, "TelCacheProvider::GetItemProperty failed [%#x]", v37);
  }
LABEL_75:
  memset_0(String, 0, sizeof(String));
  v42 = *(_QWORD *)a2;
  v43 = &File::InventoryItemValueNameBinProductVersion;
  v119 = 520;
  if ( (unsigned __int64)qword_1801219C8 > 7 )
    v43 = (__int64 *)File::InventoryItemValueNameBinProductVersion;
  v44 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v42 + 64))(
          a2,
          v43,
          String,
          &v119);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v44 >= 0 )
    {
      v45 = (char *)this + 368;
      v46 = -1;
      do
        ++v46;
      while ( String[v46] );
LABEL_86:
      std::wstring::_Assign<unsigned short>(v45, String);
      goto LABEL_90;
    }
    v47 = 3018;
    goto LABEL_89;
  }
  if ( v44 >= 0 )
  {
    v45 = (char *)this + 368;
    v48 = -1;
    do
      ++v48;
    while ( String[v48] );
    goto LABEL_86;
  }
  if ( v44 != -2147024894 )
  {
    v47 = 3030;
LABEL_89:
    AslLogCallPrintf(1, "File::Retrieve", v47, "TelCacheProvider::GetItemProperty failed [%#x]", v44);
  }
LABEL_90:
  memset_0(String, 0, sizeof(String));
  v49 = *(_QWORD *)a2;
  v50 = &File::InventoryItemValueNameLinkDate;
  v119 = 520;
  if ( (unsigned __int64)qword_1801219A8 > 7 )
    v50 = (__int64 *)File::InventoryItemValueNameLinkDate;
  v51 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v49 + 64))(
          a2,
          v50,
          String,
          &v119);
  if ( v51 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 3044, "TelCacheProvider::GetItemProperty failed [%#x]", v51);
  }
  else
  {
    v52 = -1;
    do
      ++v52;
    while ( String[v52] );
    std::wstring::_Assign<unsigned short>((char *)this + 560, String);
  }
  memset_0(String, 0, sizeof(String));
  v53 = *(_QWORD *)a2;
  v54 = &File::InventoryItemValueNameProductVersion;
  v119 = 520;
  if ( (unsigned __int64)qword_180121988 > 7 )
    v54 = (__int64 *)File::InventoryItemValueNameProductVersion;
  v55 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v53 + 64))(
          a2,
          v54,
          String,
          &v119);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v55 >= 0 )
    {
      v56 = (char *)this + 336;
      v57 = -1;
      do
        ++v57;
      while ( String[v57] );
LABEL_108:
      std::wstring::_Assign<unsigned short>(v56, String);
      goto LABEL_112;
    }
    v58 = 3059;
    goto LABEL_111;
  }
  if ( v55 >= 0 )
  {
    v56 = (char *)this + 560;
    v59 = -1;
    do
      ++v59;
    while ( String[v59] );
    goto LABEL_108;
  }
  if ( v55 != -2147024894 )
  {
    v58 = 3071;
LABEL_111:
    AslLogCallPrintf(1, "File::Retrieve", v58, "TelCacheProvider::GetItemProperty failed [%#x]", v55);
  }
LABEL_112:
  memset_0(String, 0, sizeof(String));
  v60 = *(_QWORD *)a2;
  v61 = &File::InventoryItemValueNameVersion;
  v119 = 520;
  if ( (unsigned __int64)qword_1801218C8 > 7 )
    v61 = (__int64 *)File::InventoryItemValueNameVersion;
  v62 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v60 + 64))(
          a2,
          v61,
          String,
          &v119);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v62 >= 0 )
    {
      v63 = (char *)this + 240;
      v64 = -1;
      do
        ++v64;
      while ( String[v64] );
LABEL_123:
      std::wstring::_Assign<unsigned short>(v63, String);
      goto LABEL_127;
    }
    v65 = 3089;
    goto LABEL_126;
  }
  if ( v62 >= 0 )
  {
    v63 = (char *)this + 240;
    v66 = -1;
    do
      ++v66;
    while ( String[v66] );
    goto LABEL_123;
  }
  if ( v62 != -2147024894 )
  {
    v65 = 3101;
LABEL_126:
    AslLogCallPrintf(1, "File::Retrieve", v65, "TelCacheProvider::GetItemProperty failed [%#x]", v62);
  }
LABEL_127:
  v67 = *(_QWORD *)a2;
  v68 = &File::InventoryItemValueNameLanguage;
  v69 = &File::InventoryItemValueNameLanguage;
  v120 = 0;
  if ( (unsigned __int64)qword_1801218E8 > 7 )
    v69 = (__int64 *)File::InventoryItemValueNameLanguage;
  v70 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(v67 + 80))(
          a2,
          v69,
          &v120);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v70 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3116, "TelCacheProvider::GetItemProperty failed [%#x]", v70);
      goto LABEL_140;
    }
    goto LABEL_133;
  }
  if ( v70 >= 0 )
  {
LABEL_133:
    v71 = v120;
LABEL_138:
    *((_DWORD *)this + 198) = v71;
    goto LABEL_140;
  }
  memset_0(String, 0, sizeof(String));
  v72 = *(_QWORD *)a2;
  v119 = 520;
  if ( (unsigned __int64)qword_1801218E8 > 7 )
    v68 = (__int64 *)File::InventoryItemValueNameLanguage;
  v73 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v72 + 64))(
          a2,
          v68,
          String,
          &v119);
  if ( v73 >= 0 )
  {
    v71 = _o__wtoi(String);
    goto LABEL_138;
  }
  AslLogCallPrintf(1, "File::Retrieve", 3138, "TelCacheProvider::GetItemProperty failed [%#x]", v73);
LABEL_140:
  memset_0(String, 0, sizeof(String));
  v74 = *(_QWORD *)a2;
  v75 = &File::InventoryItemValueNameBinFileVersion;
  v119 = 520;
  if ( (unsigned __int64)qword_180121908 > 7 )
    v75 = (__int64 *)File::InventoryItemValueNameBinFileVersion;
  v76 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v74 + 64))(
          a2,
          v75,
          String,
          &v119);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v76 >= 0 )
    {
      v77 = (char *)this + 176;
      v78 = -1;
      do
        ++v78;
      while ( String[v78] );
LABEL_151:
      std::wstring::_Assign<unsigned short>(v77, String);
      goto LABEL_155;
    }
    v79 = 3157;
    goto LABEL_154;
  }
  if ( v76 >= 0 )
  {
    v77 = (char *)this + 176;
    v80 = -1;
    do
      ++v80;
    while ( String[v80] );
    goto LABEL_151;
  }
  if ( v76 != -2147024894 )
  {
    v79 = 3169;
LABEL_154:
    AslLogCallPrintf(1, "File::Retrieve", v79, "TelCacheProvider::GetItemProperty failed [%#x]", v76);
  }
LABEL_155:
  memset_0(String, 0, sizeof(String));
  v81 = *(_QWORD *)a2;
  v82 = &File::InventoryItemValueNameBinaryType;
  v119 = 520;
  if ( (unsigned __int64)qword_180121928 > 7 )
    v82 = (__int64 *)File::InventoryItemValueNameBinaryType;
  v83 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v81 + 64))(
          a2,
          v82,
          String,
          &v119);
  if ( v83 < 0 )
  {
    AslLogCallPrintf(1, "File::Retrieve", 3186, "TelCacheProvider::GetItemProperty failed [%#x]", v83);
  }
  else
  {
    v84 = -1;
    do
      ++v84;
    while ( String[v84] );
    std::wstring::_Assign<unsigned short>((char *)this + 144, String);
  }
  memset_0(String, 0, sizeof(String));
  v85 = *(_QWORD *)a2;
  v86 = &File::InventoryItemValueNameAppxPackageFullName;
  v119 = 520;
  if ( (unsigned __int64)qword_180121A48 > 7 )
    v86 = (__int64 *)File::InventoryItemValueNameAppxPackageFullName;
  v87 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v85 + 64))(
          a2,
          v86,
          String,
          &v119);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v87 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3203, "TelCacheProvider::GetItemProperty failed [%#x]", v87);
      goto LABEL_174;
    }
    v88 = (char *)this + 656;
    v89 = -1;
    do
      ++v89;
    while ( String[v89] );
  }
  else
  {
    if ( v87 < 0 )
      goto LABEL_174;
    v88 = (char *)this + 656;
    v90 = -1;
    do
      ++v90;
    while ( String[v90] );
  }
  std::wstring::_Assign<unsigned short>(v88, String);
LABEL_174:
  memset_0(String, 0, sizeof(String));
  v91 = *(_QWORD *)a2;
  v92 = &File::InventoryItemValueNameAppxPackageRelativeId;
  v119 = 520;
  if ( (unsigned __int64)qword_180121A68 > 7 )
    v92 = (__int64 *)File::InventoryItemValueNameAppxPackageRelativeId;
  v93 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v91 + 64))(
          a2,
          v92,
          String,
          &v119);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v93 >= 0 )
    {
      v94 = (char *)this + 688;
      v95 = -1;
      do
        ++v95;
      while ( String[v95] );
LABEL_185:
      std::wstring::_Assign<unsigned short>(v94, String);
      goto LABEL_189;
    }
    v96 = 3228;
    goto LABEL_188;
  }
  if ( v93 >= 0 )
  {
    v94 = (char *)this + 688;
    v97 = -1;
    do
      ++v97;
    while ( String[v97] );
    goto LABEL_185;
  }
  if ( v93 != -2147024894 )
  {
    v96 = 3240;
LABEL_188:
    AslLogCallPrintf(1, "File::Retrieve", v96, "TelCacheProvider::GetItemProperty failed [%#x]", v93);
  }
LABEL_189:
  v98 = *(_QWORD *)a2;
  v99 = &File::InventoryItemValueNameFileSize;
  v100 = &File::InventoryItemValueNameFileSize;
  v121 = 0;
  if ( (unsigned __int64)qword_180121948 > 7 )
    v100 = (__int64 *)File::InventoryItemValueNameFileSize;
  v101 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, __int64 *))(v98 + 72))(
           a2,
           v100,
           &v121);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v101 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3255, "TelCacheProvider::GetItemProperty failed [%#x]", v101);
      goto LABEL_202;
    }
    goto LABEL_195;
  }
  if ( v101 >= 0 )
  {
LABEL_195:
    v102 = v121;
LABEL_200:
    *((_QWORD *)this + 97) = v102;
    goto LABEL_202;
  }
  memset_0(String, 0, sizeof(String));
  v103 = *(_QWORD *)a2;
  v119 = 520;
  if ( (unsigned __int64)qword_180121948 > 7 )
    v99 = (__int64 *)File::InventoryItemValueNameFileSize;
  v104 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v103 + 64))(
           a2,
           v99,
           String,
           &v119);
  if ( v104 >= 0 )
  {
    v102 = _wtoi64(String);
    goto LABEL_200;
  }
  AslLogCallPrintf(1, "File::Retrieve", 3277, "TelCacheProvider::GetItemProperty failed [%#x]", v104);
LABEL_202:
  v105 = &File::InventoryItemValueNameIsPeFile;
  if ( (unsigned __int64)qword_1801219E8 > 7 )
    v105 = (__int64 *)File::InventoryItemValueNameIsPeFile;
  v106 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 48LL))(
           a2,
           v105,
           (char *)this + 796);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v106 >= 0 )
      goto LABEL_212;
    v107 = 3289;
    goto LABEL_211;
  }
  if ( v106 == -2147024894 )
  {
    *((_BYTE *)this + 796) = 1;
    goto LABEL_212;
  }
  if ( v106 < 0 )
  {
    v107 = 3301;
LABEL_211:
    AslLogCallPrintf(1, "File::Retrieve", v107, "TelCacheProvider::GetItemProperty failed [%#x]", v106);
  }
LABEL_212:
  v108 = &File::InventoryItemValueNameIsOsComponent;
  if ( (unsigned __int64)qword_180121A08 > 7 )
    v108 = (__int64 *)File::InventoryItemValueNameIsOsComponent;
  v109 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 48LL))(
           a2,
           v108,
           (char *)this + 797);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v109 >= 0 )
      goto LABEL_222;
    v110 = 3312;
    goto LABEL_221;
  }
  if ( v109 == -2147024894 )
  {
    *((_BYTE *)this + 797) = 0;
    goto LABEL_222;
  }
  if ( v109 < 0 )
  {
    v110 = 3324;
LABEL_221:
    AslLogCallPrintf(1, "File::Retrieve", v110, "TelCacheProvider::GetItemProperty failed [%#x]", v109);
  }
LABEL_222:
  memset_0(String, 0, sizeof(String));
  v111 = *(_QWORD *)a2;
  v112 = &File::InventoryItemValueNameSha256;
  v119 = 520;
  if ( (unsigned __int64)qword_180121A88 > 7 )
    v112 = (__int64 *)File::InventoryItemValueNameSha256;
  v113 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v111 + 64))(
           a2,
           v112,
           String,
           &v119);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v113 < 0 )
    {
      AslLogCallPrintf(1, "File::Retrieve", 3342, "TelCacheProvider::GetItemProperty failed [%#x]", v113);
      goto LABEL_234;
    }
    v114 = (char *)this + 720;
    do
      ++v7;
    while ( String[v7] );
  }
  else
  {
    if ( v113 < 0 )
      goto LABEL_234;
    v114 = (char *)this + 720;
    do
      ++v7;
    while ( String[v7] );
  }
  std::wstring::_Assign<unsigned short>(v114, String);
LABEL_234:
  v115 = *(_QWORD *)a2;
  v116 = &File::InventoryItemValueNameUsn;
  v122 = 0;
  if ( (unsigned __int64)qword_180121A28 > 7 )
    v116 = (__int64 *)File::InventoryItemValueNameUsn;
  v117 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, __int64 *))(v115 + 8))(
           a2,
           v116,
           &v122);
  if ( v117 < 0 )
    AslLogCallPrintf(1, "File::Retrieve", 3363, "TelCacheProvider::GetItemProperty failed [%#x]", v117);
  else
    *((_QWORD *)this + 98) = v122;
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
