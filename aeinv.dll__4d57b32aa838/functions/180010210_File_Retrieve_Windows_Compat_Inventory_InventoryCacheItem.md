# File::Retrieve(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x180010210`
- end: `0x1800110f9`
- name: `?Retrieve@File@@UEAAKPEAVInventoryCacheItem@Inventory@Compat@Windows@@@Z`
- size: `3817`
- prototype: `unsigned int __fastcall(File *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011100`

## callees

- `0x180010210`
- `0x1800197d4`
- `0x180045480`
- `0x180046f38`
- `0x180059920`
- `0x18005a8bc`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180010aa7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180010aa7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180010e7d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180010e7d`

## string_xrefs

- `0x180010294`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180010abf`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180010b92`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180010c21`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180010cb5`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180010db4`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180010e96`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180010f11`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180010f90`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x180011022`: `TelCacheProvider::GetItemProperty failed [%#x]`
- `0x1800110ad`: `TelCacheProvider::GetItemProperty failed [%#x]`

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
  int v26; // r8d
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 *v29; // rdx
  int v30; // esi
  char *v31; // rcx
  __int64 v32; // r8
  int v33; // r8d
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 *v36; // rdx
  int v37; // esi
  char *v38; // rcx
  __int64 v39; // r8
  int v40; // r8d
  __int64 v41; // r8
  __int64 v42; // rax
  __int64 *v43; // rdx
  int v44; // esi
  char *v45; // rcx
  __int64 v46; // r8
  int v47; // r8d
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
  int v58; // r8d
  __int64 v59; // r8
  __int64 v60; // rax
  __int64 *v61; // rdx
  int v62; // esi
  char *v63; // rcx
  __int64 v64; // r8
  int v65; // r8d
  __int64 v66; // r8
  __int64 v67; // rax
  __int64 *v68; // r14
  __int64 *v69; // rdx
  int v70; // esi
  int v71; // r8d
  int v72; // eax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 *v75; // rdx
  int v76; // esi
  char *v77; // rcx
  __int64 v78; // r8
  int v79; // r8d
  __int64 v80; // r8
  __int64 v81; // rax
  __int64 *v82; // rdx
  __int64 v83; // r8
  __int64 v84; // rax
  __int64 *v85; // rdx
  int v86; // esi
  char *v87; // rcx
  __int64 v88; // r8
  __int64 v89; // r8
  __int64 v90; // rax
  __int64 *v91; // rdx
  int v92; // esi
  char *v93; // rcx
  __int64 v94; // r8
  int v95; // r8d
  __int64 v96; // r8
  __int64 v97; // rax
  __int64 *v98; // r14
  __int64 *v99; // rdx
  int v100; // esi
  int v101; // r8d
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 *v104; // rdx
  int v105; // esi
  int v106; // r8d
  __int64 *v107; // rdx
  int v108; // esi
  int v109; // r8d
  __int64 v110; // rax
  __int64 *v111; // rdx
  int v112; // esi
  char *v113; // rcx
  __int64 v114; // rax
  __int64 *v115; // rdx
  int v117; // [rsp+20h] [rbp-E0h]
  int v118; // [rsp+20h] [rbp-E0h]
  int v119; // [rsp+20h] [rbp-E0h]
  int v120; // [rsp+20h] [rbp-E0h]
  int v121; // [rsp+20h] [rbp-E0h]
  int v122; // [rsp+20h] [rbp-E0h]
  int v123; // [rsp+20h] [rbp-E0h]
  int v124; // [rsp+20h] [rbp-E0h]
  int v125; // [rsp+20h] [rbp-E0h]
  int v126; // [rsp+20h] [rbp-E0h]
  int v127; // [rsp+20h] [rbp-E0h]
  int v128; // [rsp+30h] [rbp-D0h] BYREF
  int v129; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v130; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v131; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t String[520]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(String, 0, sizeof(String));
  v4 = *(_QWORD *)a2;
  v5 = &File::InventoryItemValueNameProgramId;
  v128 = 520;
  if ( (unsigned __int64)qword_180182D78 > 7 )
    v5 = (__int64 *)File::InventoryItemValueNameProgramId;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v4 + 64))(
         a2,
         v5,
         String,
         &v128);
  v7 = -1;
  if ( v6 < 0 )
  {
    v117 = v6;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      2861,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
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
  v128 = 520;
  if ( (unsigned __int64)qword_180182D98 > 7 )
    v10 = (__int64 *)File::InventoryItemValueNameFileId;
  v11 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v9 + 64))(
          a2,
          v10,
          String,
          &v128,
          v117);
  if ( v11 < 0 )
  {
    if ( v11 != -2147024894 )
    {
      v118 = v11;
      AslLogCallPrintf(
        1,
        (unsigned int)"File::Retrieve",
        2877,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
    }
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
  v128 = 520;
  if ( (unsigned __int64)qword_180182DB8 > 7 )
    v14 = (__int64 *)File::InventoryItemValueNameFilePath;
  v15 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v13 + 64))(
          a2,
          v14,
          String,
          &v128,
          v118);
  if ( v15 < 0 )
  {
    v119 = v15;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      2893,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
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
  v128 = 520;
  if ( (unsigned __int64)qword_180182DF8 > 7 )
    v18 = (__int64 *)File::InventoryItemValueNameName;
  v19 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v17 + 64))(
          a2,
          v18,
          String,
          &v128,
          v119);
  if ( v19 < 0 )
  {
    v120 = v19;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      2909,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
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
  v128 = 520;
  if ( (unsigned __int64)qword_180182E18 > 7 )
    v22 = (__int64 *)File::InventoryItemValueNameOriginalFileName;
  v23 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v21 + 64))(
          a2,
          v22,
          String,
          &v128,
          v120);
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
    v121 = v23;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v26,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_45:
  memset_0(String, 0, sizeof(String));
  v28 = *(_QWORD *)a2;
  v29 = &File::InventoryItemValueNamePublisher;
  v128 = 520;
  if ( (unsigned __int64)qword_180182E38 > 7 )
    v29 = (__int64 *)File::InventoryItemValueNamePublisher;
  v30 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v28 + 64))(
          a2,
          v29,
          String,
          &v128,
          v121);
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
    v122 = v30;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v33,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_60:
  memset_0(String, 0, sizeof(String));
  v35 = *(_QWORD *)a2;
  v36 = &File::InventoryItemValueNameProductName;
  v128 = 520;
  if ( (unsigned __int64)qword_180182EF8 > 7 )
    v36 = (__int64 *)File::InventoryItemValueNameProductName;
  v37 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v35 + 64))(
          a2,
          v36,
          String,
          &v128,
          v122);
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
    v123 = v37;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v40,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_75:
  memset_0(String, 0, sizeof(String));
  v42 = *(_QWORD *)a2;
  v43 = &File::InventoryItemValueNameBinProductVersion;
  v128 = 520;
  if ( (unsigned __int64)qword_180182F58 > 7 )
    v43 = (__int64 *)File::InventoryItemValueNameBinProductVersion;
  v44 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v42 + 64))(
          a2,
          v43,
          String,
          &v128,
          v123);
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
    v124 = v44;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v47,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_90:
  memset_0(String, 0, sizeof(String));
  v49 = *(_QWORD *)a2;
  v50 = &File::InventoryItemValueNameLinkDate;
  v128 = 520;
  if ( (unsigned __int64)qword_180182F38 > 7 )
    v50 = (__int64 *)File::InventoryItemValueNameLinkDate;
  v51 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v49 + 64))(
          a2,
          v50,
          String,
          &v128,
          v124);
  if ( v51 < 0 )
  {
    v125 = v51;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      3044,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
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
  v128 = 520;
  if ( (unsigned __int64)qword_180182F18 > 7 )
    v54 = (__int64 *)File::InventoryItemValueNameProductVersion;
  v55 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v53 + 64))(
          a2,
          v54,
          String,
          &v128,
          v125);
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
    v126 = v55;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v58,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_112:
  memset_0(String, 0, sizeof(String));
  v60 = *(_QWORD *)a2;
  v61 = &File::InventoryItemValueNameVersion;
  v128 = 520;
  if ( (unsigned __int64)qword_180182E58 > 7 )
    v61 = (__int64 *)File::InventoryItemValueNameVersion;
  v62 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v60 + 64))(
          a2,
          v61,
          String,
          &v128,
          v126);
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
    v127 = v62;
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v65,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_127:
  v67 = *(_QWORD *)a2;
  v68 = &File::InventoryItemValueNameLanguage;
  v69 = &File::InventoryItemValueNameLanguage;
  v129 = 0;
  if ( (unsigned __int64)qword_180182E78 > 7 )
    v69 = (__int64 *)File::InventoryItemValueNameLanguage;
  v70 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, int *))(v67 + 80))(
          a2,
          v69,
          &v129);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v70 < 0 )
    {
      memset_0(String, 0, sizeof(String));
      v73 = *(_QWORD *)a2;
      v128 = 520;
      if ( (unsigned __int64)qword_180182E78 > 7 )
        v68 = (__int64 *)File::InventoryItemValueNameLanguage;
      if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *, int))(v73 + 64))(
             a2,
             v68,
             String,
             &v128,
             v127) < 0 )
      {
        v71 = 3138;
        goto LABEL_140;
      }
      v72 = _o__wtoi(String);
LABEL_138:
      *((_DWORD *)this + 198) = v72;
      goto LABEL_141;
    }
LABEL_133:
    v72 = v129;
    goto LABEL_138;
  }
  if ( v70 >= 0 )
    goto LABEL_133;
  v71 = 3116;
LABEL_140:
  AslLogCallPrintf(
    1,
    (unsigned int)"File::Retrieve",
    v71,
    (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
LABEL_141:
  memset_0(String, 0, sizeof(String));
  v74 = *(_QWORD *)a2;
  v75 = &File::InventoryItemValueNameBinFileVersion;
  v128 = 520;
  if ( (unsigned __int64)qword_180182E98 > 7 )
    v75 = (__int64 *)File::InventoryItemValueNameBinFileVersion;
  v76 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v74 + 64))(
          a2,
          v75,
          String,
          &v128);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v76 >= 0 )
    {
      v77 = (char *)this + 176;
      v78 = -1;
      do
        ++v78;
      while ( String[v78] );
LABEL_152:
      std::wstring::_Assign<unsigned short>(v77, String);
      goto LABEL_156;
    }
    v79 = 3157;
    goto LABEL_155;
  }
  if ( v76 >= 0 )
  {
    v77 = (char *)this + 176;
    v80 = -1;
    do
      ++v80;
    while ( String[v80] );
    goto LABEL_152;
  }
  if ( v76 != -2147024894 )
  {
    v79 = 3169;
LABEL_155:
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v79,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_156:
  memset_0(String, 0, sizeof(String));
  v81 = *(_QWORD *)a2;
  v82 = &File::InventoryItemValueNameBinaryType;
  v128 = 520;
  if ( (unsigned __int64)qword_180182EB8 > 7 )
    v82 = (__int64 *)File::InventoryItemValueNameBinaryType;
  if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v81 + 64))(
         a2,
         v82,
         String,
         &v128) < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      3186,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
  else
  {
    v83 = -1;
    do
      ++v83;
    while ( String[v83] );
    std::wstring::_Assign<unsigned short>((char *)this + 144, String);
  }
  memset_0(String, 0, sizeof(String));
  v84 = *(_QWORD *)a2;
  v85 = &File::InventoryItemValueNameAppxPackageFullName;
  v128 = 520;
  if ( (unsigned __int64)qword_180182FD8 > 7 )
    v85 = (__int64 *)File::InventoryItemValueNameAppxPackageFullName;
  v86 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v84 + 64))(
          a2,
          v85,
          String,
          &v128);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v86 < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"File::Retrieve",
        3203,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
      goto LABEL_175;
    }
    v87 = (char *)this + 656;
    v88 = -1;
    do
      ++v88;
    while ( String[v88] );
  }
  else
  {
    if ( v86 < 0 )
      goto LABEL_175;
    v87 = (char *)this + 656;
    v89 = -1;
    do
      ++v89;
    while ( String[v89] );
  }
  std::wstring::_Assign<unsigned short>(v87, String);
LABEL_175:
  memset_0(String, 0, sizeof(String));
  v90 = *(_QWORD *)a2;
  v91 = &File::InventoryItemValueNameAppxPackageRelativeId;
  v128 = 520;
  if ( (unsigned __int64)qword_180182FF8 > 7 )
    v91 = (__int64 *)File::InventoryItemValueNameAppxPackageRelativeId;
  v92 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v90 + 64))(
          a2,
          v91,
          String,
          &v128);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v92 >= 0 )
    {
      v93 = (char *)this + 688;
      v94 = -1;
      do
        ++v94;
      while ( String[v94] );
LABEL_186:
      std::wstring::_Assign<unsigned short>(v93, String);
      goto LABEL_190;
    }
    v95 = 3228;
    goto LABEL_189;
  }
  if ( v92 >= 0 )
  {
    v93 = (char *)this + 688;
    v96 = -1;
    do
      ++v96;
    while ( String[v96] );
    goto LABEL_186;
  }
  if ( v92 != -2147024894 )
  {
    v95 = 3240;
LABEL_189:
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v95,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_190:
  v97 = *(_QWORD *)a2;
  v98 = &File::InventoryItemValueNameFileSize;
  v99 = &File::InventoryItemValueNameFileSize;
  v130 = 0;
  if ( (unsigned __int64)qword_180182ED8 > 7 )
    v99 = (__int64 *)File::InventoryItemValueNameFileSize;
  v100 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, __int64 *))(v97 + 72))(
           a2,
           v99,
           &v130);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v100 < 0 )
    {
      memset_0(String, 0, sizeof(String));
      v103 = *(_QWORD *)a2;
      v128 = 520;
      if ( (unsigned __int64)qword_180182ED8 > 7 )
        v98 = (__int64 *)File::InventoryItemValueNameFileSize;
      if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v103 + 64))(
             a2,
             v98,
             String,
             &v128) < 0 )
      {
        v101 = 3277;
        goto LABEL_203;
      }
      v102 = _wtoi64(String);
LABEL_201:
      *((_QWORD *)this + 97) = v102;
      goto LABEL_204;
    }
LABEL_196:
    v102 = v130;
    goto LABEL_201;
  }
  if ( v100 >= 0 )
    goto LABEL_196;
  v101 = 3255;
LABEL_203:
  AslLogCallPrintf(
    1,
    (unsigned int)"File::Retrieve",
    v101,
    (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
LABEL_204:
  v104 = &File::InventoryItemValueNameIsPeFile;
  if ( (unsigned __int64)qword_180182F78 > 7 )
    v104 = (__int64 *)File::InventoryItemValueNameIsPeFile;
  v105 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 48LL))(
           a2,
           v104,
           (char *)this + 796);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v105 >= 0 )
      goto LABEL_214;
    v106 = 3289;
    goto LABEL_213;
  }
  if ( v105 == -2147024894 )
  {
    *((_BYTE *)this + 796) = 1;
    goto LABEL_214;
  }
  if ( v105 < 0 )
  {
    v106 = 3301;
LABEL_213:
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v106,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_214:
  v107 = &File::InventoryItemValueNameIsOsComponent;
  if ( (unsigned __int64)qword_180182F98 > 7 )
    v107 = (__int64 *)File::InventoryItemValueNameIsOsComponent;
  v108 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, char *))(*(_QWORD *)a2 + 48LL))(
           a2,
           v107,
           (char *)this + 797);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v108 >= 0 )
      goto LABEL_224;
    v109 = 3312;
    goto LABEL_223;
  }
  if ( v108 == -2147024894 )
  {
    *((_BYTE *)this + 797) = 0;
    goto LABEL_224;
  }
  if ( v108 < 0 )
  {
    v109 = 3324;
LABEL_223:
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      v109,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  }
LABEL_224:
  memset_0(String, 0, sizeof(String));
  v110 = *(_QWORD *)a2;
  v111 = &File::InventoryItemValueNameSha256;
  v128 = 520;
  if ( (unsigned __int64)qword_180183018 > 7 )
    v111 = (__int64 *)File::InventoryItemValueNameSha256;
  v112 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, wchar_t *, int *))(v110 + 64))(
           a2,
           v111,
           String,
           &v128);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( v112 < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"File::Retrieve",
        3342,
        (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
      goto LABEL_236;
    }
    v113 = (char *)this + 720;
    do
      ++v7;
    while ( String[v7] );
  }
  else
  {
    if ( v112 < 0 )
      goto LABEL_236;
    v113 = (char *)this + 720;
    do
      ++v7;
    while ( String[v7] );
  }
  std::wstring::_Assign<unsigned short>(v113, String);
LABEL_236:
  v114 = *(_QWORD *)a2;
  v115 = &File::InventoryItemValueNameUsn;
  v131 = 0;
  if ( (unsigned __int64)qword_180182FB8 > 7 )
    v115 = (__int64 *)File::InventoryItemValueNameUsn;
  if ( (*(int (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, __int64 *, __int64 *))(v114 + 8))(
         a2,
         v115,
         &v131) < 0 )
    AslLogCallPrintf(
      1,
      (unsigned int)"File::Retrieve",
      3363,
      (unsigned int)"TelCacheProvider::GetItemProperty failed [%#x]");
  else
    *((_QWORD *)this + 98) = v131;
  return 0;
}

```

## disassembly

```asm
0x180010210  mov     [rsp-8+arg_10], rbx
0x180010215  push    rbp
0x180010216  push    rsi
0x180010217  push    rdi
0x180010218  push    r12
0x18001021a  push    r13
0x18001021c  push    r14
0x18001021e  push    r15
0x180010220  lea     rbp, [rsp-370h]
0x180010228  sub     rsp, 470h
0x18001022f  mov     rax, cs:__security_cookie
0x180010236  xor     rax, rsp
0x180010239  mov     [rbp+3A0h+var_40], rax
0x180010240  mov     r15, rdx
0x180010243  mov     rbx, rcx
0x180010246  xor     edx, edx; Val
0x180010248  lea     rcx, [rsp+4A0h+String]; void *
0x18001024d  mov     r8d, 410h; Size
0x180010253  call    memset_0
0x180010258  mov     rax, [r15]
0x18001025b  lea     rdx, ?InventoryItemValueNameProgramId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProgramId
0x180010262  cmp     cs:qword_180182D78, 7
0x18001026a  lea     r9, [rsp+4A0h+var_470]
0x18001026f  lea     r8, [rsp+4A0h+String]
0x180010274  mov     [rsp+4A0h+var_470], 208h
0x18001027c  cmova   rdx, cs:?InventoryItemValueNameProgramId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProgramId
0x180010284  mov     rcx, r15
0x180010287  mov     rax, [rax+40h]
0x18001028b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010290  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010294  lea     r14, aTelcacheprovid_21; "TelCacheProvider::GetItemProperty faile"...
0x18001029b  xor     r12d, r12d
0x18001029e  lea     rsi, aFileRetrieve; "File::Retrieve"
0x1800102a5  mov     r13d, 1
0x1800102ab  test    eax, eax
0x1800102ad  js      short loc_1800102D1
0x1800102af  lea     rcx, [rbx+50h]
0x1800102b3  mov     r8, rdi
0x1800102b6  lea     rax, [rsp+4A0h+String]
0x1800102bb  inc     r8
0x1800102be  cmp     [rax+r8*2], r12w
0x1800102c3  jnz     short loc_1800102BB
0x1800102c5  lea     rdx, [rsp+4A0h+String]
0x1800102ca  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800102cf  jmp     short loc_1800102E9
0x1800102d1  mov     r9, r14
0x1800102d4  mov     [rsp+4A0h+var_480], eax
0x1800102d8  mov     r8d, 0B2Dh
0x1800102de  mov     rdx, rsi
0x1800102e1  mov     ecx, r13d
0x1800102e4  call    AslLogCallPrintf
0x1800102e9  xor     edx, edx; Val
0x1800102eb  lea     rcx, [rsp+4A0h+String]; void *
0x1800102f0  mov     r8d, 410h; Size
0x1800102f6  call    memset_0
0x1800102fb  mov     rax, [r15]
0x1800102fe  lea     rdx, ?InventoryItemValueNameFileId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFileId
0x180010305  cmp     cs:qword_180182D98, 7
0x18001030d  lea     r9, [rsp+4A0h+var_470]
0x180010312  lea     r8, [rsp+4A0h+String]
0x180010317  mov     [rsp+4A0h+var_470], 208h
0x18001031f  cmova   rdx, cs:?InventoryItemValueNameFileId@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFileId
0x180010327  mov     rcx, r15
0x18001032a  mov     rax, [rax+40h]
0x18001032e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010333  test    eax, eax
0x180010335  js      short loc_180010359
0x180010337  lea     rcx, [rbx+70h]
0x18001033b  mov     r8, rdi
0x18001033e  lea     rax, [rsp+4A0h+String]
0x180010343  inc     r8
0x180010346  cmp     [rax+r8*2], r12w
0x18001034b  jnz     short loc_180010343
0x18001034d  lea     rdx, [rsp+4A0h+String]
0x180010352  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010357  jmp     short loc_180010378
0x180010359  cmp     eax, 80070002h
0x18001035e  jz      short loc_180010378
0x180010360  mov     r9, r14
0x180010363  mov     [rsp+4A0h+var_480], eax
0x180010367  mov     r8d, 0B3Dh
0x18001036d  mov     rdx, rsi
0x180010370  mov     ecx, r13d
0x180010373  call    AslLogCallPrintf
0x180010378  xor     edx, edx; Val
0x18001037a  lea     rcx, [rsp+4A0h+String]; void *
0x18001037f  mov     r8d, 410h; Size
0x180010385  call    memset_0
0x18001038a  mov     rax, [r15]
0x18001038d  lea     rdx, ?InventoryItemValueNameFilePath@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFilePath
0x180010394  cmp     cs:qword_180182DB8, 7
0x18001039c  lea     r9, [rsp+4A0h+var_470]
0x1800103a1  lea     r8, [rsp+4A0h+String]
0x1800103a6  mov     [rsp+4A0h+var_470], 208h
0x1800103ae  cmova   rdx, cs:?InventoryItemValueNameFilePath@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameFilePath
0x1800103b6  mov     rcx, r15
0x1800103b9  mov     rax, [rax+40h]
0x1800103bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103c2  test    eax, eax
0x1800103c4  js      short loc_1800103E8
0x1800103c6  lea     rcx, [rbx+10h]
0x1800103ca  mov     r8, rdi
0x1800103cd  lea     rax, [rsp+4A0h+String]
0x1800103d2  inc     r8
0x1800103d5  cmp     [rax+r8*2], r12w
0x1800103da  jnz     short loc_1800103D2
0x1800103dc  lea     rdx, [rsp+4A0h+String]
0x1800103e1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800103e6  jmp     short loc_180010400
0x1800103e8  mov     r9, r14
0x1800103eb  mov     [rsp+4A0h+var_480], eax
0x1800103ef  mov     r8d, 0B4Dh
0x1800103f5  mov     rdx, rsi
0x1800103f8  mov     ecx, r13d
0x1800103fb  call    AslLogCallPrintf
0x180010400  xor     edx, edx; Val
0x180010402  lea     rcx, [rsp+4A0h+String]; void *
0x180010407  mov     r8d, 410h; Size
0x18001040d  call    memset_0
0x180010412  mov     rax, [r15]
0x180010415  lea     rdx, ?InventoryItemValueNameName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameName
0x18001041c  cmp     cs:qword_180182DF8, 7
0x180010424  lea     r9, [rsp+4A0h+var_470]
0x180010429  lea     r8, [rsp+4A0h+String]
0x18001042e  mov     [rsp+4A0h+var_470], 208h
0x180010436  cmova   rdx, cs:?InventoryItemValueNameName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameName
0x18001043e  mov     rcx, r15
0x180010441  mov     rax, [rax+40h]
0x180010445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001044a  test    eax, eax
0x18001044c  js      short loc_180010473
0x18001044e  lea     rcx, [rbx+0D0h]
0x180010455  mov     r8, rdi
0x180010458  lea     rax, [rsp+4A0h+String]
0x18001045d  inc     r8
0x180010460  cmp     [rax+r8*2], r12w
0x180010465  jnz     short loc_18001045D
0x180010467  lea     rdx, [rsp+4A0h+String]
0x18001046c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010471  jmp     short loc_18001048B
0x180010473  mov     r9, r14
0x180010476  mov     [rsp+4A0h+var_480], eax
0x18001047a  mov     r8d, 0B5Dh
0x180010480  mov     rdx, rsi
0x180010483  mov     ecx, r13d
0x180010486  call    AslLogCallPrintf
0x18001048b  xor     edx, edx; Val
0x18001048d  lea     rcx, [rsp+4A0h+String]; void *
0x180010492  mov     r8d, 410h; Size
0x180010498  call    memset_0
0x18001049d  mov     rax, [r15]
0x1800104a0  lea     rdx, ?InventoryItemValueNameOriginalFileName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameOriginalFileName
0x1800104a7  cmp     cs:qword_180182E18, 7
0x1800104af  lea     r9, [rsp+4A0h+var_470]
0x1800104b4  lea     r8, [rsp+4A0h+String]
0x1800104b9  mov     [rsp+4A0h+var_470], 208h
0x1800104c1  cmova   rdx, cs:?InventoryItemValueNameOriginalFileName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameOriginalFileName
0x1800104c9  mov     rcx, r15
0x1800104cc  mov     rax, [rax+40h]
0x1800104d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104d5  mov     esi, eax
0x1800104d7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800104de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800104e3  test    al, al
0x1800104e5  jz      short loc_18001050E
0x1800104e7  test    esi, esi
0x1800104e9  js      short loc_180010506
0x1800104eb  lea     rcx, [rbx+210h]
0x1800104f2  mov     r8, rdi
0x1800104f5  lea     rax, [rsp+4A0h+String]
0x1800104fa  inc     r8
0x1800104fd  cmp     [rax+r8*2], r12w
0x180010502  jnz     short loc_1800104FA
0x180010504  jmp     short loc_18001052B
0x180010506  mov     r8d, 0B6Eh
0x18001050c  jmp     short loc_180010545
0x18001050e  test    esi, esi
0x180010510  js      short loc_180010537
0x180010512  lea     rcx, [rbx+210h]
0x180010519  mov     r8, rdi
0x18001051c  lea     rax, [rsp+4A0h+String]
0x180010521  inc     r8
0x180010524  cmp     [rax+r8*2], r12w
0x180010529  jnz     short loc_180010521
0x18001052b  lea     rdx, [rsp+4A0h+String]
0x180010530  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010535  jmp     short loc_18001055B
0x180010537  cmp     esi, 80070002h
0x18001053d  jz      short loc_18001055B
0x18001053f  mov     r8d, 0B7Ah
0x180010545  mov     r9, r14
0x180010548  mov     [rsp+4A0h+var_480], esi
0x18001054c  lea     rdx, aFileRetrieve; "File::Retrieve"
0x180010553  mov     ecx, r13d
0x180010556  call    AslLogCallPrintf
0x18001055b  xor     edx, edx; Val
0x18001055d  lea     rcx, [rsp+4A0h+String]; void *
0x180010562  mov     r8d, 410h; Size
0x180010568  call    memset_0
0x18001056d  mov     rax, [r15]
0x180010570  lea     rdx, ?InventoryItemValueNamePublisher@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNamePublisher
0x180010577  cmp     cs:qword_180182E38, 7
0x18001057f  lea     r9, [rsp+4A0h+var_470]
0x180010584  lea     r8, [rsp+4A0h+String]
0x180010589  mov     [rsp+4A0h+var_470], 208h
0x180010591  cmova   rdx, cs:?InventoryItemValueNamePublisher@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNamePublisher
0x180010599  mov     rcx, r15
0x18001059c  mov     rax, [rax+40h]
0x1800105a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105a5  mov     esi, eax
0x1800105a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800105ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800105b3  test    al, al
0x1800105b5  jz      short loc_1800105DE
0x1800105b7  test    esi, esi
0x1800105b9  js      short loc_1800105D6
0x1800105bb  lea     rcx, [rbx+110h]
0x1800105c2  mov     r8, rdi
0x1800105c5  lea     rax, [rsp+4A0h+String]
0x1800105ca  inc     r8
0x1800105cd  cmp     [rax+r8*2], r12w
0x1800105d2  jnz     short loc_1800105CA
0x1800105d4  jmp     short loc_1800105FB
0x1800105d6  mov     r8d, 0B8Ch
0x1800105dc  jmp     short loc_180010615
0x1800105de  test    esi, esi
0x1800105e0  js      short loc_180010607
0x1800105e2  lea     rcx, [rbx+110h]
0x1800105e9  mov     r8, rdi
0x1800105ec  lea     rax, [rsp+4A0h+String]
0x1800105f1  inc     r8
0x1800105f4  cmp     [rax+r8*2], r12w
0x1800105f9  jnz     short loc_1800105F1
0x1800105fb  lea     rdx, [rsp+4A0h+String]
0x180010600  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010605  jmp     short loc_18001062B
0x180010607  cmp     esi, 80070002h
0x18001060d  jz      short loc_18001062B
0x18001060f  mov     r8d, 0B98h
0x180010615  mov     r9, r14
0x180010618  mov     [rsp+4A0h+var_480], esi
0x18001061c  lea     rdx, aFileRetrieve; "File::Retrieve"
0x180010623  mov     ecx, r13d
0x180010626  call    AslLogCallPrintf
0x18001062b  xor     edx, edx; Val
0x18001062d  lea     rcx, [rsp+4A0h+String]; void *
0x180010632  mov     r8d, 410h; Size
0x180010638  call    memset_0
0x18001063d  mov     rax, [r15]
0x180010640  lea     rdx, ?InventoryItemValueNameProductName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProductName
0x180010647  cmp     cs:qword_180182EF8, 7
0x18001064f  lea     r9, [rsp+4A0h+var_470]
0x180010654  lea     r8, [rsp+4A0h+String]
0x180010659  mov     [rsp+4A0h+var_470], 208h
0x180010661  cmova   rdx, cs:?InventoryItemValueNameProductName@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameProductName
0x180010669  mov     rcx, r15
0x18001066c  mov     rax, [rax+40h]
0x180010670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010675  mov     esi, eax
0x180010677  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18001067e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180010683  test    al, al
0x180010685  jz      short loc_1800106AE
0x180010687  test    esi, esi
0x180010689  js      short loc_1800106A6
0x18001068b  lea     rcx, [rbx+130h]
0x180010692  mov     r8, rdi
0x180010695  lea     rax, [rsp+4A0h+String]
0x18001069a  inc     r8
0x18001069d  cmp     [rax+r8*2], r12w
0x1800106a2  jnz     short loc_18001069A
0x1800106a4  jmp     short loc_1800106CB
0x1800106a6  mov     r8d, 0BACh
0x1800106ac  jmp     short loc_1800106E5
0x1800106ae  test    esi, esi
0x1800106b0  js      short loc_1800106D7
0x1800106b2  lea     rcx, [rbx+130h]
0x1800106b9  mov     r8, rdi
0x1800106bc  lea     rax, [rsp+4A0h+String]
0x1800106c1  inc     r8
0x1800106c4  cmp     [rax+r8*2], r12w
0x1800106c9  jnz     short loc_1800106C1
0x1800106cb  lea     rdx, [rsp+4A0h+String]
0x1800106d0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800106d5  jmp     short loc_1800106FB
0x1800106d7  cmp     esi, 80070002h
0x1800106dd  jz      short loc_1800106FB
0x1800106df  mov     r8d, 0BB8h
0x1800106e5  mov     r9, r14
0x1800106e8  mov     [rsp+4A0h+var_480], esi
0x1800106ec  lea     rdx, aFileRetrieve; "File::Retrieve"
0x1800106f3  mov     ecx, r13d
0x1800106f6  call    AslLogCallPrintf
0x1800106fb  xor     edx, edx; Val
0x1800106fd  lea     rcx, [rsp+4A0h+String]; void *
0x180010702  mov     r8d, 410h; Size
0x180010708  call    memset_0
0x18001070d  mov     rax, [r15]
0x180010710  lea     rdx, ?InventoryItemValueNameBinProductVersion@File@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::InventoryItemValueNameBinProductVersion
0x180010717  cmp     cs:qword_180182F58, 7
  ... truncated ...
```
