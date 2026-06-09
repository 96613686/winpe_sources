# CAutoDestItemsFolder::CreateRelativePidl(_ITEMIDLIST_ABSOLUTE const *,bool,bool,uint,IPropertyStore *,_FILETIME *,IAutomaticDestinationList *,_ITEMID_CHILD * *)

- ea: `0x18032ec28`
- end: `0x18033040e`
- name: `?CreateRelativePidl@CAutoDestItemsFolder@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@_N1IPEAUIPropertyStore@@PEAU_FILETIME@@PEAUIAutomaticDestinationList@@PEAPEAU_ITEMID_CHILD@@@Z`
- size: `6118`
- prototype: `__int64 __usercall@<rax>(CAutoDestItemsFolder *__hidden this@<rcx>, const struct _ITEMIDLIST_ABSOLUTE *@<rdx>, bool@<r8b>, bool@<r9b>, unsigned int, struct IPropertyStore *, struct _FILETIME *, struct IAutomaticDestinationList *, struct _ITEMID_CHILD **)`
- caller_count: `2`
- callee_count: `51`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180332450`
- `0x1806183b0`

## callees

- `0x18000d354`
- `0x18000d3e0`
- `0x18000d6cc`
- `0x18000ee24`
- `0x18000ee84`
- `0x1800144c4`
- `0x1800432f0`
- `0x180048fb0`
- `0x18004bb30`
- `0x180054154`
- `0x18008af80`
- `0x1800d13a0`
- `0x1800d1410`
- `0x1800d98d0`
- `0x1800dd190`
- `0x1801034d4`
- `0x180121d30`
- `0x18013501c`
- `0x18017cf78`
- `0x18017ea40`
- `0x18018b6e0`
- `0x18018eac0`
- `0x1801a16d0`
- `0x1801f7e20`
- `0x1801f85b0`
- `0x1802199a0`
- `0x180232110`
- `0x180234e50`
- `0x18023b484`
- `0x180243d0c`
- `0x18026dc58`
- `0x180281cac`
- `0x180286e88`
- `0x18028da2c`
- `0x1802c8520`
- `0x1802f5d00`
- `0x1802f9e30`
- `0x18032ec28`
- `0x180338e18`
- `0x18034dff4`
- `0x1803582c0`
- `0x1803a4cb0`
- `0x1803b7c38`
- `0x1803b7c78`
- `0x1804e0ff8`
- `0x18060e39c`
- `0x18060ea18`
- `0x180615ee8`
- `0x18061acd8`
- `0x18061adc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ed2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f3e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f43b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f49b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f4ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f4f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f50b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f52b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f719`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f7f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f81f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fa5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fc4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fc80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fcc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fdec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fed1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ffbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ffcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180330046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180330056`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ed2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f3e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f43b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f49b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f4ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f4f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f50b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f52b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f719`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f7f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f81f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032f925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fa5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fc4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fc80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fcc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fdec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032fed1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ffbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ffcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180330046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180330056`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18032f6dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18032f6dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18032f641`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18032f64d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18032f9d5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180330116`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18033023e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180330253`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1803302d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18032f641`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18032f64d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18032f9d5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180330116`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18033023e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180330253`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1803302d3`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x18032f30c`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x18032f30c`
- `PROPSYS!PropVariantToStringAlloc` at `0x18032f9af`
- `PROPSYS!PropVariantToStringAlloc` at `0x18032f9af`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocGetPerceivedType` at `0x180330218`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocGetPerceivedType` at `0x180330218`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18032fdb1`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18032fdb1`

## string_xrefs

- `0x18032fd1a`: `local_path`
- `0x18032fb4b`: `is_local_recommendation`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall CAutoDestItemsFolder::CreateRelativePidl(
        CAutoDestItemsFolder *this,
        const ITEMIDLIST *a2,
        char a3,
        unsigned __int8 a4,
        LONG a5,
        struct IPropertyStore *a6,
        struct _FILETIME *a7,
        struct IAutomaticDestinationList *a8,
        struct _ITEMID_CHILD **a9)
{
  enum FOLDER_ENUM_MODE v9; // edi
  int v13; // eax
  int v14; // ebx
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  void *v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // edi
  __int64 v23; // rdx
  char v24; // r15
  int v25; // eax
  int v26; // ecx
  int v27; // eax
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  struct IPropertyStore *v31; // rdx
  PWSTR *v32; // rax
  HRESULT v33; // eax
  __int64 v34; // rax
  int v35; // eax
  int v36; // eax
  void *v37; // rcx
  int v38; // eax
  WCHAR *v39; // rbx
  int v40; // eax
  void *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  int v44; // eax
  __int64 v45; // rax
  __int64 **v46; // rdi
  HRESULT Instance; // eax
  __int64 *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, __int64); // rbx
  __int64 v52; // rax
  int v53; // eax
  WCHAR *v54; // rcx
  int v55; // eax
  int v56; // ecx
  void **v57; // rax
  const ITEMIDLIST *v58; // r14
  HRESULT v59; // eax
  __int64 v60; // rbx
  void (__fastcall *v61)(__int64, const PROPERTYKEY *, __int64); // rdi
  __int64 v62; // rax
  const unsigned __int16 *v63; // rdx
  PWSTR *v64; // rax
  HRESULT v65; // eax
  int v66; // eax
  int NamedPropertyStore; // eax
  int As; // eax
  __int64 v69; // rdx
  __int64 v70; // rax
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rax
  ITEMIDLIST *v74; // rcx
  LPVOID v75; // rcx
  void *v76; // rax
  void *v77; // rcx
  CAutoDestItemsFolder *v78; // rcx
  __int64 v79; // rax
  int v80; // eax
  __int64 v81; // rdx
  __int64 v82; // rax
  HRESULT v83; // eax
  __int64 v84; // rdx
  void *v85; // rcx
  HRESULT v86; // eax
  int v87; // ebx
  int v88; // eax
  void *v89; // rcx
  int v90; // eax
  __int64 v91; // rax
  int v92; // eax
  __int64 v93; // rdx
  void *v94; // rcx
  __int64 v95; // rax
  int v96; // eax
  int ThumbnailCacheId; // eax
  __int64 v98; // rdx
  HRESULT AsString; // eax
  wil::details::in1diag3 *v100; // rcx
  __int64 v101; // rdx
  unsigned __int16 **v102; // rax
  int v103; // eax
  HRESULT ItemID; // eax
  __int64 v105; // rdx
  unsigned int v106; // eax
  int v107; // ecx
  __int64 v108; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  struct INamedPropertyStore *v112; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v113; // [rsp+38h] [rbp-C8h]
  struct _ITEMID_CHILD **v114; // [rsp+40h] [rbp-C0h]
  struct IAutomaticDestinationList **v115; // [rsp+48h] [rbp-B8h] BYREF
  PERCEIVEDFLAG *v116; // [rsp+50h] [rbp-B0h]
  struct IPropertyStore **v117; // [rsp+58h] [rbp-A8h]
  enum FOLDER_ENUM_MODE *v118; // [rsp+60h] [rbp-A0h]
  LPVOID *p_pv; // [rsp+68h] [rbp-98h]
  char *v120; // [rsp+70h] [rbp-90h]
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  struct IPropertyStore *v122; // [rsp+80h] [rbp-80h] BYREF
  char v123[8]; // [rsp+88h] [rbp-78h] BYREF
  struct INamedPropertyStore *v124; // [rsp+90h] [rbp-70h] BYREF
  struct tagPROPVARIANT propvar; // [rsp+98h] [rbp-68h] BYREF
  struct INamedPropertyStore *v126[2]; // [rsp+B0h] [rbp-50h] BYREF
  PROPERTYKEY ppidl; // [rsp+C0h] [rbp-40h] BYREF
  struct INamedPropertyStore *v128; // [rsp+E0h] [rbp-20h] BYREF
  PCWSTR pszName; // [rsp+E8h] [rbp-18h] BYREF
  PERCEIVEDFLAG pflag[2]; // [rsp+F0h] [rbp-10h] BYREF
  LPCITEMIDLIST pidl; // [rsp+F8h] [rbp-8h] BYREF
  LPCWSTR pszStr1; // [rsp+100h] [rbp+0h] BYREF
  PCWSTR pszExt; // [rsp+108h] [rbp+8h] BYREF
  LPBC ppbc; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v135; // [rsp+118h] [rbp+18h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+120h] [rbp+20h] BYREF
  LPVOID v137; // [rsp+138h] [rbp+38h] BYREF
  LPVOID v138; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v139; // [rsp+148h] [rbp+48h] BYREF
  struct IShellFolder *v140; // [rsp+150h] [rbp+50h] BYREF
  __int64 v141; // [rsp+158h] [rbp+58h] BYREF
  LPVOID v142; // [rsp+160h] [rbp+60h] BYREF
  __int64 v143; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int64 v144; // [rsp+170h] [rbp+70h] BYREF
  struct _FILETIME v145; // [rsp+178h] [rbp+78h] BYREF
  enum FOLDER_ENUM_MODE v146; // [rsp+180h] [rbp+80h] BYREF
  void **v147; // [rsp+188h] [rbp+88h] BYREF
  char v148; // [rsp+190h] [rbp+90h]
  __int128 v149; // [rsp+198h] [rbp+98h]
  int v150; // [rsp+1A8h] [rbp+A8h]
  int v151; // [rsp+1ACh] [rbp+ACh]
  char v152; // [rsp+1B0h] [rbp+B0h]
  __int64 v153; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v9 = a4;
  v113 = a4;
  pidl = a2;
  v114 = a9;
  *a9 = 0;
  v122 = 0;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v122);
  v13 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromMemory(&v122);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB3,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)(unsigned int)v13,
      ppv);
    goto LABEL_268;
  }
  v146 = v9;
  pv = 0;
  *(_QWORD *)&pvar.vt = &pv;
  pvar.hVal.QuadPart = 0;
  *((_BYTE *)&pvar.decVal + 16) = 1;
  v14 = ConvertIDListEnumMode(v9, (const struct _ITEMIDLIST_ABSOLUTE *)a2, &pvar.pStream);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&pvar);
  if ( v14 < 0 )
  {
    v15 = (unsigned int)v14;
    v16 = 2742;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
      (const char *)v15,
      ppv);
    v17 = pv;
    pv = 0;
    goto LABEL_6;
  }
  ppidl = PKEY_DelegateIDList;
  v18 = wil::ShellItemPropertyStoreHelper::SetIDList<_tagpropertykey>(&v122, &ppidl, pv);
  v14 = v18;
  if ( v18 < 0 )
  {
    v15 = (unsigned int)v18;
    v16 = 2743;
    goto LABEL_5;
  }
  propvar.vt = 11;
  propvar.iVal = -1;
  if ( !a3 )
    propvar.iVal = 0;
  v19 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
          v122,
          &PKEY_Home_IsPinned,
          &propvar);
  v14 = v19;
  if ( v19 < 0 )
  {
    v15 = (unsigned int)v19;
    v16 = 2744;
    goto LABEL_5;
  }
  propvar.vt = 19;
  propvar.lVal = a5;
  v20 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
          v122,
          &PKEY_Home_SortOrder,
          &propvar);
  v14 = v20;
  if ( v20 < 0 )
  {
    v15 = (unsigned int)v20;
    v16 = 2745;
    goto LABEL_5;
  }
  propvar.vt = 19;
  propvar.lVal = v9 << 16;
  v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
          v122,
          &PKEY_SFGAOFlags,
          &propvar);
  v14 = v21;
  v22 = 0;
  if ( v21 >= 0 )
  {
    propvar.vt = 19;
    propvar.lVal = 0;
    v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
            v122,
            &PKEY_Home_GraphFileType,
            &propvar);
    v14 = v21;
    if ( v21 < 0 )
    {
      v23 = 2751;
      goto LABEL_18;
    }
    propvar.vt = 11;
    propvar.iVal = 0;
    v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
            v122,
            &PKEY_Home_Recommended,
            &propvar);
    v14 = v21;
    if ( v21 < 0 )
    {
      v23 = 2752;
      goto LABEL_18;
    }
    propvar.vt = 31;
    propvar.hVal.QuadPart = (LONGLONG)&WindowName;
    v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
            v122,
            &PKEY_MsGraph_RecommendationReason,
            &propvar);
    v14 = v21;
    if ( v21 < 0 )
    {
      v23 = 2753;
      goto LABEL_18;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FE_PI>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FE_PI>::GetImpl'::`2'::impl) )
    {
      propvar.vt = 31;
      propvar.hVal.QuadPart = (LONGLONG)&WindowName;
      v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int128 *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_MsGraph_WebAccountId,
              &propvar);
      v14 = v21;
      if ( v21 < 0 )
      {
        v23 = 2757;
        goto LABEL_18;
      }
      propvar.vt = 31;
      propvar.hVal.QuadPart = (LONGLONG)&WindowName;
      v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_MsGraph_SharedByEmail,
              &propvar);
      v14 = v21;
      if ( v21 < 0 )
      {
        v23 = 2758;
        goto LABEL_18;
      }
      propvar.vt = 31;
      propvar.hVal.QuadPart = (LONGLONG)&WindowName;
      v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_WebAccountID,
              &propvar);
      v14 = v21;
      if ( v21 < 0 )
      {
        v23 = 2759;
        goto LABEL_18;
      }
      propvar.vt = 31;
      propvar.hVal.QuadPart = (LONGLONG)&WindowName;
      v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_MsGraph_PrimaryActivityActorUpn,
              &propvar);
      v14 = v21;
      if ( v21 < 0 )
      {
        v23 = 2760;
        goto LABEL_18;
      }
      propvar.vt = 31;
      propvar.hVal.QuadPart = (LONGLONG)&WindowName;
      v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_MsGraph_PrimaryActivityActorDisplayName,
              &propvar);
      v14 = v21;
      if ( v21 < 0 )
      {
        v23 = 2761;
        goto LABEL_18;
      }
      propvar.vt = 31;
      propvar.hVal.QuadPart = (LONGLONG)&WindowName;
      v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_MsGraph_SharedByName,
              &propvar);
      v14 = v21;
      if ( v21 < 0 )
      {
        v23 = 2762;
        goto LABEL_18;
      }
      propvar.vt = 19;
      propvar.lVal = 0;
      v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_MsGraph_ActivityType,
              &propvar);
      v14 = v21;
      if ( v21 < 0 )
      {
        v23 = 2763;
        goto LABEL_18;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55730600>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55730600>::GetImpl'::`2'::impl) )
    {
      propvar.vt = 19;
      propvar.lVal = 0;
      v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_StorageProviderUserAccountKind,
              &propvar);
      v14 = v21;
      if ( v21 < 0 )
      {
        v23 = 2768;
        goto LABEL_18;
      }
    }
    v24 = 1;
    if ( !a6 )
    {
LABEL_48:
      v26 = *((_DWORD *)this + 26);
      if ( (unsigned int)(v26 - 1) <= 1 )
      {
        if ( a7 )
        {
          pvar.vt = 64;
          pvar.filetime = *a7;
          v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
                  v122,
                  &PKEY_DateAccessed,
                  &pvar);
          v14 = v21;
          if ( v21 < 0 )
          {
            v23 = 2878;
            goto LABEL_18;
          }
        }
      }
      else if ( !v26 && !a3 )
      {
        pvar.vt = 64;
        pvar.hVal.QuadPart = 0;
        v21 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
                v122,
                &PKEY_DateAccessed,
                &pvar);
        v14 = v21;
        if ( v21 < 0 )
        {
          v23 = 2886;
          goto LABEL_18;
        }
      }
      v56 = *((_DWORD *)this + 26);
      if ( !v56 )
      {
        v58 = pidl;
LABEL_163:
        if ( (unsigned int)(*((_DWORD *)this + 26) - 2) > 1 )
        {
LABEL_257:
          pszExt = 0;
          v140 = 0;
          ItemID = SHBindToFolderIDListParentEx(
                     0,
                     v58,
                     0,
                     &GUID_000214e6_0000_0000_c000_000000000046,
                     (void **)&v140,
                     (LPCITEMIDLIST *)&pszExt);
          v14 = ItemID;
          if ( ItemID < 0 )
          {
            v105 = 3153;
LABEL_259:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v105,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
              (const char *)(unsigned int)ItemID,
              ppva);
            wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v140);
            goto LABEL_235;
          }
          v106 = SHGetAttributesWithBindCtx(v140, (const struct _ITEMIDLIST_RELATIVE *)pszExt, 0, 0x20400000u);
          LOWORD(v115) = 19;
          v107 = v106 | 0x10000;
          if ( !v113 )
            v107 = v106;
          LODWORD(v116) = v107;
          ItemID = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct IAutomaticDestinationList ***))v122->lpVtbl->SetValue)(
                     v122,
                     &PKEY_SFGAOFlags,
                     &v115);
          v14 = ItemID;
          if ( ItemID < 0 )
          {
            v105 = 3158;
            goto LABEL_259;
          }
          ItemID = CItemIDFactory<NSITEM,203342025>::s_CreateItemID(v108, v122, v114, *((_QWORD *)this + 9));
          v14 = ItemID;
          if ( ItemID < 0 )
          {
            v105 = 3160;
            goto LABEL_259;
          }
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v140);
          wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            &pv,
            0);
LABEL_267:
          v14 = v22;
          goto LABEL_268;
        }
        v124 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v124);
        NamedPropertyStore = wil::PropertyStoreHelper::GetNamedPropertyStore((wil::PropertyStoreHelper *)&v122, &v124);
        v14 = NamedPropertyStore;
        if ( NamedPropertyStore < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB65,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)NamedPropertyStore,
            ppv);
LABEL_166:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v124);
          goto LABEL_19;
        }
        v112 = v124;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v112);
        v123[0] = 0;
        if ( *((_DWORD *)this + 26) != 3 )
          goto LABEL_176;
        strcpy((char *)&ppidl, "\v");
        *(_WORD *)ppidl.fmtid.Data4 = -1;
        As = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPERTYKEY *))v122->lpVtbl->SetValue)(
               v122,
               &PKEY_Home_Recommended,
               &ppidl);
        v14 = As;
        if ( As < 0 )
        {
          v69 = 2923;
LABEL_170:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v69,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)As,
            ppv);
LABEL_171:
          Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(&v112);
          goto LABEL_166;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_51721485>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_51721485>::GetImpl'::`2'::impl) )
        {
          As = wil::PropertyStoreHelperBase<INamedPropertyStore>::GetAsBoolean<unsigned short const *>(
                 &v112,
                 L"is_local_recommendation",
                 v123);
          v14 = As;
          if ( As == -2147023728 )
          {
            v123[0] = 0;
          }
          else if ( As < 0 )
          {
            v69 = 2927;
            goto LABEL_170;
          }
        }
        if ( !v123[0] )
        {
LABEL_176:
          LOWORD(ppidl.fmtid.Data1) = 19;
          *(_DWORD *)ppidl.fmtid.Data4 = 1;
          As = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPERTYKEY *))v122->lpVtbl->SetValue)(
                 v122,
                 &PKEY_Home_GraphFileType,
                 &ppidl);
          v14 = As;
          if ( As < 0 )
          {
            v69 = 2933;
            goto LABEL_170;
          }
          pidl = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56859762>::GetImpl'::`2'::impl) )
          {
            v73 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pidl);
            ppidl = PKEY_FileName;
            v71 = wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v122, &ppidl, v73);
            v14 = v71;
            if ( v71 < 0 )
            {
              v72 = 2938;
              goto LABEL_185;
            }
          }
          else
          {
            v70 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pidl);
            v71 = wil::PropertyStoreHelperBase<INamedPropertyStore>::GetAsString<unsigned short const *>(
                    &v112,
                    L"title",
                    v70);
            v14 = v71;
            if ( v71 < 0 )
            {
              v72 = 2942;
LABEL_185:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v72,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
                (const char *)(unsigned int)v71,
                ppv);
              v74 = (ITEMIDLIST *)pidl;
LABEL_186:
              if ( v74 )
                CoTaskMemFree(v74);
              goto LABEL_171;
            }
          }
          v75 = pv;
          pv = 0;
          v76 = (void *)ILAppendHiddenStringW(v75, 3203334184LL, pidl);
          v77 = pv;
          pv = v76;
          if ( v77 )
          {
            CoTaskMemFree(v77);
            v76 = pv;
          }
          ppidl = PKEY_DelegateIDList;
          v71 = wil::ShellItemPropertyStoreHelper::SetIDList<_tagpropertykey>(&v122, &ppidl, v76);
          v14 = v71;
          if ( v71 < 0 )
          {
            v72 = 2949;
            goto LABEL_185;
          }
          if ( pidl )
            CoTaskMemFree((LPVOID)pidl);
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56859762>::GetImpl'::`2'::impl)
          && CAutoDestItemsFolder::IsOneNoteApp(v78, (struct wil::NamedPropertyStoreHelper *)&v112) )
        {
          v24 = 0;
        }
        pszName = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56859762>::GetImpl'::`2'::impl) )
        {
          v82 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszName);
          ppidl = PKEY_ItemPathDisplay;
          v80 = wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v122, &ppidl, v82);
        }
        else
        {
          v79 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszName);
          v80 = wil::PropertyStoreHelperBase<INamedPropertyStore>::GetAsString<unsigned short const *>(
                  &v112,
                  L"local_path",
                  v79);
        }
        if ( v80 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xBB2,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)v80,
            ppv);
          goto LABEL_216;
        }
        if ( !*pszName || !v24 )
        {
LABEL_216:
          v90 = SetStorageProviderUIStatusPrimaryState(v122);
          if ( v90 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xC15,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
              (const char *)(unsigned int)v90,
              ppv);
          v135 = 0;
          v145 = 0;
          v144 = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56859762>::GetImpl'::`2'::impl) )
          {
            v95 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v135);
            ppidl = PKEY_ContentUri;
            v96 = wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v122, &ppidl, v95);
            v14 = v96;
            if ( v96 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC1D,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
                (const char *)(unsigned int)v96,
                ppv);
              if ( v135 )
                CoTaskMemFree(v135);
              if ( pszName )
                CoTaskMemFree((LPVOID)pszName);
              goto LABEL_234;
            }
          }
          else
          {
            v91 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v135);
            ppidl.fmtid = (GUID)PKEY_Home_WebUrl;
            ppidl.pid = 9;
            v92 = wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v122, &ppidl, v91);
            v14 = v92;
            if ( v92 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC21,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
                (const char *)(unsigned int)v92,
                ppv);
LABEL_221:
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v135);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszName);
LABEL_234:
              Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(&v112);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v124);
LABEL_235:
              wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
                &pv,
                0);
              goto LABEL_268;
            }
          }
          LOBYTE(v93) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorer_LaunchAndEnumerationPerfInefficiencies>::ReportUsage(
            &`wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorer_LaunchAndEnumerationPerfInefficiencies>::GetImpl'::`2'::impl,
            v93);
          ppidl = PKEY_DateModified;
          wil::PropertyStoreHelperBase<IPropertyStore>::GetAsFileTime<_tagpropertykey>(&v122, &ppidl, &v145);
          ppidl = PKEY_Size;
          wil::PropertyStoreHelperBase<IPropertyStore>::GetAsUInt64<_tagpropertykey>(&v122, &ppidl, &v144);
          pvar.vt = 0;
          ThumbnailCacheId = GraphFileThumbnailProvider::GetThumbnailCacheId(v135, v145, v144, &pvar);
          v14 = ThumbnailCacheId;
          if ( ThumbnailCacheId < 0 )
          {
            v98 = 3120;
LABEL_238:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v98,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
              (const char *)(unsigned int)ThumbnailCacheId,
              ppv);
LABEL_239:
            PropVariantClear((PROPVARIANT *)&pvar);
            goto LABEL_221;
          }
          ThumbnailCacheId = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
                               v122,
                               &PKEY_ThumbnailCacheId,
                               &pvar);
          v14 = ThumbnailCacheId;
          if ( ThumbnailCacheId < 0 )
          {
            v98 = 3121;
            goto LABEL_238;
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59111371>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59111371>::GetImpl'::`2'::impl)
            || (unsigned int)(*((_DWORD *)this + 26) - 2) > 1 )
          {
            goto LABEL_254;
          }
          LOWORD(v115) = 19;
          LODWORD(v116) = 1;
          ThumbnailCacheId = ((__int64 (__fastcall *)(struct IPropertyStore *, __int128 *, struct IAutomaticDestinationList ***))v122->lpVtbl->SetValue)(
                               v122,
                               &PKEY_Shell_ItemOfflineStatus,
                               &v115);
          v14 = ThumbnailCacheId;
          if ( ThumbnailCacheId < 0 )
          {
            v98 = 3128;
            goto LABEL_238;
          }
          pszExt = 0;
          LOWORD(ppidl.fmtid.Data1) = 0;
          AsString = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPERTYKEY *))v122->lpVtbl->GetValue)(
                       v122,
                       &PKEY_FileExtension,
                       &ppidl);
          v100 = retaddr;
          if ( AsString >= 0 )
          {
            v102 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszExt);
            AsString = wil::PropVariant::GetAsString((wil::PropVariant *)&ppidl, v102);
            v100 = retaddr;
            if ( AsString >= 0 )
            {
              LODWORD(ppbc) = 0;
              pflag[0] = 0;
              AsString = AssocGetPerceivedType(pszExt, (PERCEIVED *)&ppbc, pflag, 0);
              v100 = retaddr;
              if ( AsString >= 0 )
              {
                LOWORD(v115) = 3;
                LODWORD(v116) = (_DWORD)ppbc;
                v103 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct IAutomaticDestinationList ***))v122->lpVtbl->SetValue)(
                         v122,
                         &PKEY_PerceivedType,
                         &v115);
                v14 = v103;
                if ( v103 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xC47,
                    (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
                    (const char *)(unsigned int)v103,
                    ppv);
                  PropVariantClear((PROPVARIANT *)&ppidl);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszExt);
                  goto LABEL_239;
                }
                goto LABEL_253;
              }
              v101 = 3140;
            }
            else
            {
              v101 = 3136;
            }
          }
          else
          {
            v101 = 3134;
          }
          wil::details::in1diag3::_Log_Hr(
            v100,
            (void *)v101,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)AsString,
            ppv);
LABEL_253:
          PropVariantClear((PROPVARIANT *)&ppidl);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszExt);
LABEL_254:
          PropVariantClear((PROPVARIANT *)&pvar);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v135);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszName);
          Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(&v112);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v124);
          goto LABEL_257;
        }
        *(_QWORD *)pflag = 0;
        LOBYTE(v81) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorer_LaunchAndEnumerationPerfInefficiencies>::ReportUsage(
          &`wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorer_LaunchAndEnumerationPerfInefficiencies>::GetImpl'::`2'::impl,
          v81);
        ppbc = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppbc);
        v83 = CreateBindCtx(0, &ppbc);
        v14 = v83;
        if ( v83 < 0 )
        {
          v84 = 3002;
LABEL_206:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v84,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)v83,
            ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppbc);
          v85 = *(void **)pflag;
          *(_QWORD *)pflag = 0;
          if ( v85 )
            CoTaskMemFree(v85);
          v74 = (ITEMIDLIST *)pszName;
          goto LABEL_186;
        }
        *(_QWORD *)&ppidl.fmtid.Data1 = pflag;
        *(_QWORD *)ppidl.fmtid.Data4 = 0;
        LOBYTE(ppidl.pid) = 1;
        v86 = SHParseDisplayName(pszName, ppbc, (LPITEMIDLIST *)ppidl.fmtid.Data4, 0, 0);
        v87 = v86;
        if ( v86 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xBBB,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)v86,
            ppv);
        wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&ppidl);
        if ( v87 < 0 )
        {
LABEL_214:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppbc);
          v89 = *(void **)pflag;
          *(_QWORD *)pflag = 0;
          if ( v89 )
            CoTaskMemFree(v89);
          goto LABEL_216;
        }
        v115 = &a8;
        v116 = pflag;
        v117 = &v122;
        v118 = &v146;
        p_pv = &pv;
        v120 = v123;
        v88 = lambda_1d3c5a9ef38131f9a10f931761dc37f7_::operator()(&v115);
        if ( v88 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xBDD,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)v88,
            ppv);
          goto LABEL_214;
        }
        v83 = CItemIDFactory<NSITEM,203342025>::s_CreateItemID(retaddr, v122, v114, *((_QWORD *)this + 9));
        v14 = v83;
        if ( v83 < 0 )
        {
          v84 = 3039;
          goto LABEL_206;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppbc);
        v94 = *(void **)pflag;
        *(_QWORD *)pflag = 0;
        if ( v94 )
          CoTaskMemFree(v94);
        if ( pszName )
          CoTaskMemFree((LPVOID)pszName);
        Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(&v112);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v124);
        v41 = pv;
        pv = 0;
LABEL_92:
        if ( v41 )
          CoTaskMemFree(v41);
        goto LABEL_267;
      }
      pszStr1 = 0;
      if ( (unsigned int)(v56 - 2) <= 1 )
      {
        pvar.vt = 0;
        if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->GetValue)(
               v122,
               &PKEY_Kind,
               &pvar) >= 0 )
        {
          v64 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszStr1);
          *v64 = 0;
          v65 = pvar.vt ? PropVariantToStringAlloc((const PROPVARIANT *const)&pvar, v64) : -2147023728;
          if ( v65 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xB51,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
              (const char *)(unsigned int)v65,
              ppv);
        }
        PropVariantClear((PROPVARIANT *)&pvar);
        v58 = pidl;
      }
      else
      {
        if ( v56 != 1 )
        {
          v58 = pidl;
          goto LABEL_157;
        }
        v143 = 0;
        v57 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&v143);
        v58 = pidl;
        v59 = SHCreateItemFromIDList(pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, v57);
        v14 = v59;
        if ( v59 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB57,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)v59,
            ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v143);
          goto LABEL_141;
        }
        v60 = v143;
        if ( v143 )
        {
          v61 = *(void (__fastcall **)(__int64, const PROPERTYKEY *, __int64))(*(_QWORD *)v143 + 136LL);
          v62 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszStr1);
          v61(v60, &PKEY_Kind, v62);
          v22 = 0;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v143);
      }
      if ( pszStr1 && FrequentPlacesFolderHelpers::IsVideoOrImageKind(pszStr1, v63) )
      {
        pvar.vt = 11;
        pvar.iVal = 0;
LABEL_158:
        v66 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
                v122,
                &PKEY_IconsOnlyInTilesMode,
                &pvar);
        v14 = v66;
        if ( v66 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB5F,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)v66,
            ppv);
LABEL_141:
          if ( pszStr1 )
            CoTaskMemFree((LPVOID)pszStr1);
          goto LABEL_19;
        }
        if ( pszStr1 )
          CoTaskMemFree((LPVOID)pszStr1);
        goto LABEL_163;
      }
LABEL_157:
      pvar.vt = 11;
      pvar.iVal = -1;
      goto LABEL_158;
    }
    wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)&v124, a6);
    v126[0] = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v126);
    v25 = wil::PropertyStoreHelper::GetNamedPropertyStore((wil::PropertyStoreHelper *)&v124, v126);
    if ( v25 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAD9,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
        (const char *)(unsigned int)v25,
        ppv);
LABEL_47:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v126);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v124);
      goto LABEL_48;
    }
    if ( (unsigned int)(*((_DWORD *)this + 26) - 2) > 1 )
      goto LABEL_47;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56859762>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56859762>::GetImpl'::`2'::impl) )
    {
      v27 = CAutoDestItemsFolder::PopulateShellItemPropertyStoreFromGraphRecentItemNamedPropertyStore(
              this,
              v122,
              v126[0]);
      v14 = v27;
      if ( v27 >= 0 )
        goto LABEL_47;
      v28 = 2861;
      goto LABEL_57;
    }
    v27 = SHCopyPropertyStore(v122, (struct IPropertyStore *)v124);
    v14 = v27;
    if ( v27 < 0 )
    {
      v28 = 2784;
LABEL_57:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
        (const char *)(unsigned int)v27,
        ppv);
LABEL_58:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v126);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v124);
      goto LABEL_19;
    }
    v128 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v128);
    v29 = wil::PropertyStoreHelper::GetNamedPropertyStore((wil::PropertyStoreHelper *)&v122, &v128);
    v14 = v29;
    if ( v29 < 0 )
    {
      v30 = 2787;
LABEL_61:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
        (const char *)(unsigned int)v29,
        ppv);
LABEL_62:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v128);
      goto LABEL_58;
    }
    v29 = CopyNamedPropertyStore(v128, v126[0]);
    v14 = v29;
    if ( v29 < 0 )
    {
      v30 = 2788;
      goto LABEL_61;
    }
    if ( FrequentPlacesFolderHelpers::IsOneNoteApp(v122, v31) )
    {
      v145 = (struct _FILETIME)L".onetoc2";
      propvar.vt = 31;
      propvar.hVal.QuadPart = (LONGLONG)L".onetoc2";
      v29 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_FileExtension,
              &propvar);
      v14 = v29;
      if ( v29 < 0 )
      {
        v30 = 2796;
        goto LABEL_61;
      }
      propvar.vt = 31;
      propvar.hVal.QuadPart = (LONGLONG)L".onetoc2";
      v29 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_ItemType,
              &propvar);
      v14 = v29;
      if ( v29 < 0 )
      {
        v30 = 2797;
        goto LABEL_61;
      }
      v137 = 0;
      v32 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v137);
      propvar.vt = 31;
      propvar.hVal.QuadPart = (LONGLONG)L".onetoc2";
      v33 = PSFormatForDisplayAlloc(&PKEY_ItemType, (const PROPVARIANT *const)&propvar, PDFF_DEFAULT, v32);
      if ( v33 >= 0 )
      {
        propvar.vt = 31;
        propvar.hVal.QuadPart = (LONGLONG)v137;
        v36 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
                v122,
                &PKEY_ItemTypeText,
                &propvar);
        v14 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAF2,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)v36,
            ppv);
LABEL_78:
          v37 = v137;
          goto LABEL_79;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF0,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
          (const char *)(unsigned int)v33,
          ppv);
      }
      v138 = 0;
      v34 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v138);
      ppidl = PKEY_ItemNameDisplayWithoutExtension;
      v35 = wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v122, &ppidl, v34);
      v14 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAF6,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
          (const char *)(unsigned int)v35,
          ppv);
LABEL_74:
        if ( v138 )
          CoTaskMemFree(v138);
        goto LABEL_78;
      }
      pszExt = 0;
      v144 = (unsigned __int64)v138;
      v38 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const *,unsigned short const *>(
              &pszExt,
              &v144,
              &v145);
      v14 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAF9,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
          (const char *)(unsigned int)v38,
          ppv);
        if ( pszExt )
          CoTaskMemFree((LPVOID)pszExt);
        goto LABEL_74;
      }
      propvar.vt = 31;
      v39 = (WCHAR *)pszExt;
      propvar.hVal.QuadPart = (LONGLONG)pszExt;
      v40 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_FileName,
              &propvar);
      v22 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAFB,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
          (const char *)(unsigned int)v40,
          ppv);
        if ( v39 )
          CoTaskMemFree(v39);
        if ( v138 )
          CoTaskMemFree(v138);
        if ( v137 )
          CoTaskMemFree(v137);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v128);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v126);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v124);
        v41 = pv;
        pv = 0;
        goto LABEL_92;
      }
      v22 = 0;
      v24 = 0;
      if ( v39 )
        CoTaskMemFree(v39);
      if ( v138 )
        CoTaskMemFree(v138);
      if ( v137 )
        CoTaskMemFree(v137);
    }
    v139 = 0;
    v42 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v139);
    ppidl = PKEY_FileExtension;
    if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v122, &ppidl, v42) >= 0 )
    {
      v147 = &CFileExtension::`vftable';
      v148 = 0;
      v149 = 0;
      v150 = 0;
      v151 = -1;
      v152 = 0;
      v153 = 0;
      v43 = CFileExtension::SetExtensionOrProgId((CFileExtension *)&v147, v139);
      v14 = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB06,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
          (const char *)(unsigned int)v43,
          ppv);
LABEL_103:
        CFileExtension::~CFileExtension((CFileExtension *)&v147);
        v37 = v139;
LABEL_79:
        if ( v37 )
          CoTaskMemFree(v37);
        goto LABEL_62;
      }
      propvar.vt = 0;
      if ( CFileExtension::GetKindsAsPropvariant((CFileExtension *)&v147, &propvar) >= 0 )
      {
        v44 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
                v122,
                &PKEY_Kind,
                &propvar);
        v14 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB0B,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
            (const char *)(unsigned int)v44,
            ppv);
          PropVariantClear((PROPVARIANT *)&propvar);
          goto LABEL_103;
        }
      }
      PropVariantClear((PROPVARIANT *)&propvar);
      CFileExtension::~CFileExtension((CFileExtension *)&v147);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl'::`2'::impl) )
    {
LABEL_128:
      if ( v139 )
        CoTaskMemFree(v139);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v128);
      goto LABEL_47;
    }
    v142 = 0;
    v45 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v142);
    ppidl.fmtid = *(GUID *)&PKEY_StorageProviderFullyQualifiedId;
    ppidl.pid = 119;
    if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v122, &ppidl, v45) < 0 )
    {
LABEL_126:
      if ( v142 )
        CoTaskMemFree(v142);
      goto LABEL_128;
    }
    v46 = (__int64 **)((char *)this + 128);
    if ( !*((_QWORD *)this + 16) )
    {
      *v46 = 0;
      Instance = CoCreateInstance(
                   &GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe,
                   0,
                   1u,
                   &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64,
                   (LPVOID *)this + 16);
      v14 = Instance;
      if ( Instance < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB19,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
          (const char *)(unsigned int)Instance,
          ppv);
        if ( v142 )
          CoTaskMemFree(v142);
        if ( v139 )
          CoTaskMemFree(v139);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v128);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v126);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v124);
        v17 = pv;
        pv = 0;
        goto LABEL_6;
      }
    }
    v141 = 0;
    v48 = *v46;
    v49 = **v46;
    v22 = 0;
    v141 = 0;
    if ( (*(int (__fastcall **)(__int64 *, LPVOID, __int64 *))(v49 + 24))(v48, v142, &v141) < 0 )
    {
LABEL_125:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v141);
      goto LABEL_126;
    }
    pszStr1 = 0;
    v50 = v141;
    v51 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v141 + 56LL);
    v52 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszStr1);
    v53 = v51(v50, v52);
    v22 = 0;
    if ( v53 >= 0 )
    {
      v54 = (WCHAR *)pszStr1;
      if ( !pszStr1 )
        goto LABEL_123;
      pvar.vt = 31;
      pvar.hVal.QuadPart = (LONGLONG)pszStr1;
      v55 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, struct tagPROPVARIANT *))v122->lpVtbl->SetValue)(
              v122,
              &PKEY_WebAccountID,
              &pvar);
      if ( v55 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB23,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
          (const char *)(unsigned int)v55,
          ppv);
    }
    v54 = (WCHAR *)pszStr1;
LABEL_123:
    if ( v54 )
      CoTaskMemFree(v54);
    goto LABEL_125;
  }
  v23 = 2746;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\frequentplacesfolder.cpp",
    (const char *)(unsigned int)v21,
    ppv);
LABEL_19:
  v17 = pv;
  pv = 0;
LABEL_6:
  if ( v17 )
    CoTaskMemFree(v17);
LABEL_268:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v122);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18032ec28  mov     [rsp-8+arg_10], rbx
0x18032ec2d  push    rbp
0x18032ec2e  push    rsi
0x18032ec2f  push    rdi
0x18032ec30  push    r12
0x18032ec32  push    r13
0x18032ec34  push    r14
0x18032ec36  push    r15
0x18032ec38  lea     rbp, [rsp-0D0h]
0x18032ec40  sub     rsp, 1D0h
0x18032ec47  mov     rax, cs:__security_cookie
0x18032ec4e  xor     rax, rsp
0x18032ec51  mov     [rbp+100h+var_40], rax
0x18032ec58  movzx   edi, r9b
0x18032ec5c  mov     [rsp+200h+var_1C8], dil
0x18032ec61  mov     r12b, r8b
0x18032ec64  mov     rsi, rdx
0x18032ec67  mov     [rbp+100h+pidl], rdx
0x18032ec6b  mov     r13, rcx
0x18032ec6e  mov     r14, [rbp+100h+arg_28]
0x18032ec75  mov     rax, [rbp+100h+arg_40]
0x18032ec7c  mov     [rsp+200h+var_1C0], rax
0x18032ec81  xor     r15d, r15d
0x18032ec84  mov     [rax], r15
0x18032ec87  mov     [rbp+100h+var_180], r15
0x18032ec8b  lea     rcx, [rbp+100h+var_180]
0x18032ec8f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18032ec94  nop
0x18032ec95  lea     rcx, [rbp+100h+var_180]
0x18032ec99  call    ?InitFromMemory@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJXZ; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromMemory(void)
0x18032ec9e  mov     ebx, eax
0x18032eca0  test    eax, eax
0x18032eca2  jns     short loc_18032ECC4
0x18032eca4  mov     rcx, [rbp+108h]; this
0x18032ecab  mov     r9d, eax; char *
0x18032ecae  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\windows.storage\\fre"...
0x18032ecb5  mov     edx, 0AB3h; void *
0x18032ecba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032ecbf  jmp     loc_1803303D9
0x18032ecc4  mov     [rbp+100h+var_80], edi
0x18032ecca  mov     [rsp+200h+pv], r15
0x18032eccf  lea     rax, [rsp+200h+pv]
0x18032ecd4  mov     [rbp+100h+pvar], rax
0x18032ecd8  mov     [rbp+100h+var_D8], r15
0x18032ecdc  mov     [rbp+100h+var_D0], 1
0x18032ece0  lea     r8, [rbp+100h+var_D8]; struct _ITEMIDLIST_ABSOLUTE **
0x18032ece4  mov     rdx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x18032ece7  mov     ecx, edi; enum FOLDER_ENUM_MODE
0x18032ece9  call    ?ConvertIDListEnumMode@@YAJW4FOLDER_ENUM_MODE@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU2@@Z; ConvertIDListEnumMode(FOLDER_ENUM_MODE,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x18032ecee  mov     ebx, eax
0x18032ecf0  lea     rcx, [rbp+100h+pvar]
0x18032ecf4  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18032ecf9  test    ebx, ebx
0x18032ecfb  jns     short loc_18032ED37
0x18032ecfd  mov     r9d, ebx; char *
0x18032ed00  mov     edx, 0AB6h; void *
0x18032ed05  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\windows.storage\\fre"...
0x18032ed0c  mov     rcx, [rbp+108h]; this
0x18032ed13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032ed18  nop
0x18032ed19  mov     rcx, [rsp+200h+pv]; pv
0x18032ed1e  mov     [rsp+200h+pv], r15
0x18032ed23  test    rcx, rcx
0x18032ed26  jz      loc_1803303D9
0x18032ed2c  call    cs:__imp_CoTaskMemFree
0x18032ed32  jmp     loc_1803303D9
0x18032ed37  movups  xmm0, xmmword ptr cs:PKEY_DelegateIDList.fmtid.Data1
0x18032ed3e  movaps  xmmword ptr [rbp+100h+ppidl], xmm0
0x18032ed42  mov     eax, cs:PKEY_DelegateIDList.pid
0x18032ed48  mov     [rbp+100h+var_130], eax
0x18032ed4b  mov     r8, [rsp+200h+pv]
0x18032ed50  lea     rdx, [rbp+100h+ppidl]
0x18032ed54  lea     rcx, [rbp+100h+var_180]
0x18032ed58  call    ??$SetIDList@U_tagpropertykey@@@ShellItemPropertyStoreHelper@wil@@QEAAJU_tagpropertykey@@PEBU_ITEMIDLIST_ABSOLUTE@@@Z; wil::ShellItemPropertyStoreHelper::SetIDList<_tagpropertykey>(_tagpropertykey,_ITEMIDLIST_ABSOLUTE const *)
0x18032ed5d  mov     ebx, eax
0x18032ed5f  test    eax, eax
0x18032ed61  jns     short loc_18032ED6D
0x18032ed63  mov     r9d, eax
0x18032ed66  mov     edx, 0AB7h
0x18032ed6b  jmp     short loc_18032ED05
0x18032ed6d  mov     esi, 0Bh
0x18032ed72  mov     word ptr [rbp+100h+propvar], si
0x18032ed76  or      eax, 0FFFFFFFFh
0x18032ed79  test    r12b, r12b
0x18032ed7c  mov     word ptr [rbp+100h+var_160], ax
0x18032ed80  jnz     short loc_18032ED87
0x18032ed82  mov     word ptr [rbp+100h+var_160], r15w
0x18032ed87  mov     rcx, [rbp+100h+var_180]
0x18032ed8b  mov     rax, [rcx]
0x18032ed8e  lea     r8, [rbp+100h+propvar]
0x18032ed92  lea     rdx, PKEY_Home_IsPinned
0x18032ed99  mov     rax, [rax+30h]
0x18032ed9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032eda2  mov     ebx, eax
0x18032eda4  test    eax, eax
0x18032eda6  jns     short loc_18032EDB5
0x18032eda8  mov     r9d, eax
0x18032edab  mov     edx, 0AB8h
0x18032edb0  jmp     loc_18032ED05
0x18032edb5  mov     eax, 13h
0x18032edba  mov     word ptr [rbp+100h+propvar], ax
0x18032edbe  mov     eax, [rbp+100h+arg_20]
0x18032edc4  mov     dword ptr [rbp+100h+var_160], eax
0x18032edc7  mov     rcx, [rbp+100h+var_180]
0x18032edcb  mov     rax, [rcx]
0x18032edce  lea     r8, [rbp+100h+propvar]
0x18032edd2  lea     rdx, PKEY_Home_SortOrder
0x18032edd9  mov     rax, [rax+30h]
0x18032eddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032ede2  mov     ebx, eax
0x18032ede4  test    eax, eax
0x18032ede6  jns     short loc_18032EDF5
0x18032ede8  mov     r9d, eax
0x18032edeb  mov     edx, 0AB9h
0x18032edf0  jmp     loc_18032ED05
0x18032edf5  mov     r15d, 13h
0x18032edfb  mov     word ptr [rbp+100h+propvar], r15w
0x18032ee00  shl     edi, 10h
0x18032ee03  mov     dword ptr [rbp+100h+var_160], edi
0x18032ee06  mov     rcx, [rbp+100h+var_180]
0x18032ee0a  mov     rax, [rcx]
0x18032ee0d  lea     r8, [rbp+100h+propvar]
0x18032ee11  lea     rdx, PKEY_SFGAOFlags
0x18032ee18  mov     rax, [rax+30h]
0x18032ee1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032ee21  mov     ebx, eax
0x18032ee23  xor     edi, edi
0x18032ee25  test    eax, eax
0x18032ee27  jns     short loc_18032EE54
0x18032ee29  mov     edx, 0ABAh; void *
0x18032ee2e  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\windows.storage\\fre"...
0x18032ee35  mov     r9d, eax; char *
0x18032ee38  mov     rcx, [rbp+108h]; this
0x18032ee3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032ee44  nop
0x18032ee45  mov     rcx, [rsp+200h+pv]
0x18032ee4a  mov     [rsp+200h+pv], rdi
0x18032ee4f  jmp     loc_18032ED23
0x18032ee54  mov     word ptr [rbp+100h+propvar], r15w
0x18032ee59  mov     dword ptr [rbp+100h+var_160], edi
0x18032ee5c  mov     rcx, [rbp+100h+var_180]
0x18032ee60  mov     rax, [rcx]
0x18032ee63  lea     r8, [rbp+100h+propvar]
0x18032ee67  lea     rdx, PKEY_Home_GraphFileType
0x18032ee6e  mov     rax, [rax+30h]
0x18032ee72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032ee77  mov     ebx, eax
0x18032ee79  test    eax, eax
0x18032ee7b  jns     short loc_18032EE84
0x18032ee7d  mov     edx, 0ABFh
0x18032ee82  jmp     short loc_18032EE2E
0x18032ee84  mov     word ptr [rbp+100h+propvar], si
0x18032ee88  mov     word ptr [rbp+100h+var_160], di
0x18032ee8c  mov     rcx, [rbp+100h+var_180]
0x18032ee90  mov     rax, [rcx]
0x18032ee93  lea     r8, [rbp+100h+propvar]
0x18032ee97  lea     rdx, PKEY_Home_Recommended
0x18032ee9e  mov     rax, [rax+30h]
0x18032eea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032eea7  mov     ebx, eax
0x18032eea9  test    eax, eax
0x18032eeab  jns     short loc_18032EEB7
0x18032eead  mov     edx, 0AC0h
0x18032eeb2  jmp     loc_18032EE2E
0x18032eeb7  mov     r15d, 1Fh
0x18032eebd  mov     word ptr [rbp+100h+propvar], r15w
0x18032eec2  lea     rsi, WindowName
0x18032eec9  mov     [rbp+100h+var_160], rsi
0x18032eecd  mov     rcx, [rbp+100h+var_180]
0x18032eed1  mov     rax, [rcx]
0x18032eed4  lea     r8, [rbp+100h+propvar]
0x18032eed8  lea     rdx, PKEY_MsGraph_RecommendationReason
0x18032eedf  mov     rax, [rax+30h]
0x18032eee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032eee8  mov     ebx, eax
0x18032eeea  test    eax, eax
0x18032eeec  jns     short loc_18032EEF8
0x18032eeee  mov     edx, 0AC1h
0x18032eef3  jmp     loc_18032EE2E
0x18032eef8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FE_PI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FE_PI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FE_PI> `wil::Feature<__WilFeatureTraits_Feature_FE_PI>::GetImpl(void)'::`2'::impl
0x18032eeff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FE_PI@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FE_PI>::__private_IsEnabled(wil::ReportingKind)
0x18032ef04  test    al, al
0x18032ef06  jnz     short loc_18032EF57
0x18032ef08  mov     esi, 13h
0x18032ef0d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55730600@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55730600@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55730600> `wil::Feature<__WilFeatureTraits_Feature_55730600>::GetImpl(void)'::`2'::impl
0x18032ef14  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55730600@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55730600>::__private_IsEnabled(wil::ReportingKind)
0x18032ef19  test    al, al
0x18032ef1b  jz      loc_18032F0CA
0x18032ef21  mov     word ptr [rbp+100h+propvar], si
0x18032ef25  mov     dword ptr [rbp+100h+var_160], edi
0x18032ef28  mov     rcx, [rbp+100h+var_180]
0x18032ef2c  mov     rax, [rcx]
0x18032ef2f  lea     r8, [rbp+100h+propvar]
0x18032ef33  lea     rdx, PKEY_StorageProviderUserAccountKind
0x18032ef3a  mov     rax, [rax+30h]
0x18032ef3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032ef43  mov     ebx, eax
0x18032ef45  test    eax, eax
0x18032ef47  jns     loc_18032F0CA
0x18032ef4d  mov     edx, 0AD0h
0x18032ef52  jmp     loc_18032EE2E
0x18032ef57  mov     word ptr [rbp+100h+propvar], r15w
0x18032ef5c  mov     [rbp+100h+var_160], rsi
0x18032ef60  mov     rcx, [rbp+100h+var_180]
0x18032ef64  mov     rax, [rcx]
0x18032ef67  lea     r8, [rbp+100h+propvar]
0x18032ef6b  lea     rdx, PKEY_MsGraph_WebAccountId
0x18032ef72  mov     rax, [rax+30h]
0x18032ef76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032ef7b  mov     ebx, eax
0x18032ef7d  test    eax, eax
0x18032ef7f  jns     short loc_18032EF8B
0x18032ef81  mov     edx, 0AC5h
0x18032ef86  jmp     loc_18032EE2E
0x18032ef8b  mov     word ptr [rbp+100h+propvar], r15w
0x18032ef90  mov     [rbp+100h+var_160], rsi
0x18032ef94  mov     rcx, [rbp+100h+var_180]
0x18032ef98  mov     rax, [rcx]
0x18032ef9b  lea     r8, [rbp+100h+propvar]
0x18032ef9f  lea     rdx, PKEY_MsGraph_SharedByEmail
0x18032efa6  mov     rax, [rax+30h]
0x18032efaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032efaf  mov     ebx, eax
0x18032efb1  test    eax, eax
0x18032efb3  jns     short loc_18032EFBF
0x18032efb5  mov     edx, 0AC6h
0x18032efba  jmp     loc_18032EE2E
0x18032efbf  mov     word ptr [rbp+100h+propvar], r15w
0x18032efc4  mov     [rbp+100h+var_160], rsi
0x18032efc8  mov     rcx, [rbp+100h+var_180]
0x18032efcc  mov     rax, [rcx]
0x18032efcf  lea     r8, [rbp+100h+propvar]
0x18032efd3  lea     rdx, PKEY_WebAccountID
0x18032efda  mov     rax, [rax+30h]
0x18032efde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032efe3  mov     ebx, eax
0x18032efe5  test    eax, eax
0x18032efe7  jns     short loc_18032EFF3
0x18032efe9  mov     edx, 0AC7h
0x18032efee  jmp     loc_18032EE2E
0x18032eff3  mov     word ptr [rbp+100h+propvar], r15w
0x18032eff8  mov     [rbp+100h+var_160], rsi
0x18032effc  mov     rcx, [rbp+100h+var_180]
0x18032f000  mov     rax, [rcx]
0x18032f003  lea     r8, [rbp+100h+propvar]
0x18032f007  lea     rdx, PKEY_MsGraph_PrimaryActivityActorUpn
0x18032f00e  mov     rax, [rax+30h]
0x18032f012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032f017  mov     ebx, eax
0x18032f019  test    eax, eax
0x18032f01b  jns     short loc_18032F027
0x18032f01d  mov     edx, 0AC8h
0x18032f022  jmp     loc_18032EE2E
0x18032f027  mov     word ptr [rbp+100h+propvar], r15w
0x18032f02c  mov     [rbp+100h+var_160], rsi
0x18032f030  mov     rcx, [rbp+100h+var_180]
0x18032f034  mov     rax, [rcx]
0x18032f037  lea     r8, [rbp+100h+propvar]
0x18032f03b  lea     rdx, PKEY_MsGraph_PrimaryActivityActorDisplayName
0x18032f042  mov     rax, [rax+30h]
0x18032f046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032f04b  mov     ebx, eax
0x18032f04d  test    eax, eax
0x18032f04f  jns     short loc_18032F05B
0x18032f051  mov     edx, 0AC9h
0x18032f056  jmp     loc_18032EE2E
0x18032f05b  mov     word ptr [rbp+100h+propvar], r15w
0x18032f060  mov     [rbp+100h+var_160], rsi
0x18032f064  mov     rcx, [rbp+100h+var_180]
0x18032f068  mov     rax, [rcx]
0x18032f06b  lea     r8, [rbp+100h+propvar]
0x18032f06f  lea     rdx, PKEY_MsGraph_SharedByName
0x18032f076  mov     rax, [rax+30h]
0x18032f07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032f07f  mov     ebx, eax
0x18032f081  test    eax, eax
0x18032f083  jns     short loc_18032F08F
0x18032f085  mov     edx, 0ACAh
0x18032f08a  jmp     loc_18032EE2E
0x18032f08f  mov     esi, 13h
0x18032f094  mov     word ptr [rbp+100h+propvar], si
0x18032f098  mov     dword ptr [rbp+100h+var_160], edi
0x18032f09b  mov     rcx, [rbp+100h+var_180]
0x18032f09f  mov     rax, [rcx]
0x18032f0a2  lea     r8, [rbp+100h+propvar]
0x18032f0a6  lea     rdx, PKEY_MsGraph_ActivityType
0x18032f0ad  mov     rax, [rax+30h]
0x18032f0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032f0b6  mov     ebx, eax
0x18032f0b8  test    eax, eax
0x18032f0ba  jns     loc_18032EF0D
0x18032f0c0  mov     edx, 0ACBh
0x18032f0c5  jmp     loc_18032EE2E
0x18032f0ca  mov     r15b, 1
0x18032f0cd  lea     rsi, aOnecoreuapShel_23; "onecoreuap\\shell\\windows.storage\\fre"...
0x18032f0d4  test    r14, r14
0x18032f0d7  jz      short loc_18032F133
0x18032f0d9  mov     rdx, r14; struct IPropertyStore *
0x18032f0dc  lea     rcx, [rbp+100h+var_170]; this
0x18032f0e0  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
  ... truncated ...
```
