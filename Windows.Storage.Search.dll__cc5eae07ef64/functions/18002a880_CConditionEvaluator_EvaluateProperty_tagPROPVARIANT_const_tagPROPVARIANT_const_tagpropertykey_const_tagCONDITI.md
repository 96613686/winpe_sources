# CConditionEvaluator::_EvaluateProperty(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,int *,int *)

- ea: `0x18002a880`
- end: `0x18002b731`
- name: `?_EvaluateProperty@CConditionEvaluator@@AEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAH4@Z`
- size: `3761`
- prototype: `__int64 __usercall@<rax>(CConditionEvaluator *__hidden this@<rcx>, const struct tagPROPVARIANT *@<rdx>, const struct tagPROPVARIANT *@<r8>, const struct _tagpropertykey *@<r9>, tagCONDITION_OPERATION, struct ICondition *, int, int *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029fa0`

## callees

- `0x18002a880`
- `0x18002b760`
- `0x18002c2c0`
- `0x18002ca30`
- `0x18002ca9c`
- `0x18002cc90`
- `0x18002cd00`
- `0x18003bde0`
- `0x180046860`
- `0x180068598`
- `0x18006b9cc`
- `0x180071dc0`
- `0x180072cdc`
- `0x180092ddc`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ae97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ae97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ab9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002acb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ab9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002acb4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ab31`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ac83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002acaa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002aef1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b02b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b0fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b122`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b2df`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b40d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ab31`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ac83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002acaa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002aef1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b02b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b0fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b122`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b2df`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b40d`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18002a95b`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18002a95b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002b3bd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002b512`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002b3bd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002b512`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002ab81`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002ad31`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002ab81`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002ad31`
- `PROPSYS!PropVariantGetElementCount` at `0x18002a9bb`
- `PROPSYS!PropVariantGetElementCount` at `0x18002a9bb`
- `PROPSYS!PSFormatForDisplay` at `0x18002aa8d`
- `PROPSYS!PSFormatForDisplay` at `0x18002ae4b`
- `PROPSYS!PSFormatForDisplay` at `0x18002aa8d`
- `PROPSYS!PSFormatForDisplay` at `0x18002ae4b`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18002b369`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18002b4ea`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18002b369`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18002b4ea`
- `PROPSYS!PSGetPropertyDescription` at `0x18002ac08`
- `PROPSYS!PSGetPropertyDescription` at `0x18002ac08`
- `PROPSYS!PropVariantCompareEx` at `0x18002b237`
- `PROPSYS!PropVariantCompareEx` at `0x18002b237`
- `PROPSYS!PropVariantChangeType` at `0x18002acfc`
- `PROPSYS!PropVariantChangeType` at `0x18002ad5b`
- `PROPSYS!PropVariantChangeType` at `0x18002b148`
- `PROPSYS!PropVariantChangeType` at `0x18002b18c`
- `PROPSYS!PropVariantChangeType` at `0x18002b276`
- `PROPSYS!PropVariantChangeType` at `0x18002b656`
- `PROPSYS!PropVariantChangeType` at `0x18002acfc`
- `PROPSYS!PropVariantChangeType` at `0x18002ad5b`
- `PROPSYS!PropVariantChangeType` at `0x18002b148`
- `PROPSYS!PropVariantChangeType` at `0x18002b18c`
- `PROPSYS!PropVariantChangeType` at `0x18002b276`
- `PROPSYS!PropVariantChangeType` at `0x18002b656`

## pseudocode

```c
__int64 __fastcall CConditionEvaluator::_EvaluateProperty(
        CConditionEvaluator *this,
        PROPVARIANT *a2,
        PROPVARIANT *a3,
        struct _tagpropertykey *a4,
        tagCONDITION_OPERATION a5,
        struct ICondition *a6,
        unsigned int a7,
        int *a8,
        int *a9)
{
  PROPDESC_FORMAT_FLAGS v9; // r14d
  PROPVARIANT *v10; // r12
  CConditionEvaluator *v11; // rdi
  struct IConditionVtbl *v12; // rax
  unsigned int InputLocale; // r15d
  int v14; // ebx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, LPCWSTR *); // rbx
  struct IConditionVtbl *v17; // rax
  int v18; // ebx
  const struct _GUID *v19; // r8
  __int64 v20; // r12
  int v21; // r14d
  int v22; // esi
  HRESULT Instance; // edi
  PROPDESC_FORMAT_FLAGS v24; // r8d
  __int64 v25; // rax
  bool v26; // zf
  SIZE_T v27; // rbx
  void *v28; // rax
  CConditionEvaluator *v29; // r12
  enum tagCONDITION_OPERATION v30; // r13d
  struct IConditionVtbl *lpVtbl; // rax
  __int64 result; // rax
  __int64 v33; // r8
  __int64 v34; // rax
  PROPVARIANT *v35; // rbx
  int v36; // ebx
  int v37; // ebx
  __int64 v38; // r8
  HRESULT v39; // eax
  PROPVARIANT *v40; // r8
  __int64 v41; // r12
  int v42; // esi
  int v43; // ebx
  HRESULT v44; // edi
  int v45; // r14d
  PROPDESC_FORMAT_FLAGS v46; // r8d
  __int64 v47; // rax
  __int64 v48; // rdi
  void *v49; // rax
  CConditionEvaluator *v50; // r12
  enum tagCONDITION_OPERATION v51; // r13d
  int v52; // r14d
  int v53; // esi
  int *v54; // rcx
  __int64 v55; // rax
  PROPVARIANT *p_ppropvarDest; // rbx
  int v57; // r14d
  int v58; // ebx
  int v59; // ebx
  HRESULT v60; // eax
  PROPVARIANT *v61; // rcx
  __int64 v62; // r14
  int *v63; // r15
  PROPVARIANT *v64; // rsi
  PKA_FLAGS v65; // ebx
  VARTYPE v66; // ax
  VARTYPE v67; // r9
  const PROPVARIANT *v68; // rdi
  int v69; // eax
  unsigned int v70; // esi
  int v71; // eax
  int *v72; // r12
  __int64 v73; // rsi
  int *v74; // r15
  PKA_FLAGS v75; // ebx
  HRESULT v76; // ebx
  PROPDESC_FORMAT_FLAGS pdfFlags; // [rsp+80h] [rbp-80h] BYREF
  PROPVARIANT *propvarSrc; // [rsp+88h] [rbp-78h]
  PROPERTYKEY *propkey; // [rsp+90h] [rbp-70h]
  int *v80; // [rsp+98h] [rbp-68h]
  LPCWSTR pszStr1; // [rsp+A0h] [rbp-60h] BYREF
  struct tagPROPVARIANT ppropvarDest; // [rsp+A8h] [rbp-58h] BYREF
  CConditionEvaluator *v83; // [rsp+C0h] [rbp-40h]
  PROPVARIANT pvar[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v85; // [rsp+D8h] [rbp-28h]
  PROPVARIANT v86[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v87; // [rsp+F0h] [rbp-10h]
  int *v88; // [rsp+F8h] [rbp-8h]
  PROPVARIANT *propvar; // [rsp+100h] [rbp+0h]
  LPCWSTR lpName; // [rsp+108h] [rbp+8h] BYREF
  int v91[4]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR pwszText[1024]; // [rsp+120h] [rbp+20h] BYREF

  v9 = PDFF_DEFAULT;
  v10 = a3;
  v11 = this;
  v88 = a9;
  v80 = a8;
  propkey = a4;
  propvar = a3;
  propvarSrc = a2;
  v83 = this;
  pdfFlags = PDFF_DEFAULT;
  if ( a5 == COP_APPLICATION_SPECIFIC )
  {
    lpVtbl = a6->lpVtbl;
    pszStr1 = 0;
    result = ((__int64 (__fastcall *)(struct ICondition *, LPCWSTR *))lpVtbl->GetValueType)(a6, &pszStr1);
    if ( (int)result < 0 )
      return result;
    if ( pszStr1 )
    {
      v33 = -1;
      do
        ++v33;
      while ( pszStr1[v33] );
      if ( StrCmpNICW(pszStr1, L"System.StructuredQueryType.AnyBitsSet", v33) )
      {
        v38 = -1;
        do
          ++v38;
        while ( pszStr1[v38] );
        if ( !StrCmpNICW(pszStr1, L"System.StructuredQueryType.AllBitsSet", v38) )
          v9 = PDFF_FILENAME;
      }
      else
      {
        v9 = PDFF_FILENAME|PDFF_PREFIXNAME;
      }
      pdfFlags = v9;
      CoTaskMemFree((LPVOID)pszStr1);
    }
  }
  v12 = a6->lpVtbl;
  InputLocale = 0;
  *(_QWORD *)v91 = 0;
  v14 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, int *))v12->QueryInterface)(
          a6,
          &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
          v91);
  if ( v14 >= 0 )
  {
    v15 = *(_QWORD *)v91;
    lpName = 0;
    v16 = *(__int64 (__fastcall **)(__int64, LPCWSTR *))(**(_QWORD **)v91 + 120LL);
    CoTaskMemFree(0);
    v14 = v16(v15, &lpName);
    if ( v14 >= 0 )
    {
      InputLocale = LocaleNameToLCID(lpName, 0);
      if ( InputLocale == 4096 )
        InputLocale = 127;
    }
    CoTaskMemFree((LPVOID)lpName);
    v11 = v83;
  }
  if ( *(_QWORD *)v91 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v91 + 16LL))(*(_QWORD *)v91);
  if ( v14 < 0 )
    InputLocale = CConditionEvaluator::_GetInputLocale(v11);
  v17 = a6->lpVtbl;
  v18 = 0;
  pszStr1 = 0;
  ((void (__fastcall *)(struct ICondition *, LPCWSTR *))v17->GetValueType)(a6, &pszStr1);
  if ( !PropVariantGetElementCount(v10) )
  {
    memset(&ppropvarDest, 0, sizeof(ppropvarDest));
    if ( a5 == COP_IMPLICIT )
    {
      Instance = 1;
      goto LABEL_54;
    }
    if ( (unsigned int)(a5 - 7) > 6 )
    {
      v73 = *((_QWORD *)v11 + 6);
      if ( pszStr1 && !StrCmpICW(pszStr1, L"System.StructuredQueryType.SortKeyDescription") )
      {
        Instance = SortKeyCompareValues((const struct tagPROPVARIANT *)propvarSrc, &ppropvarDest, a5, a7, v80);
        goto LABEL_54;
      }
      if ( v9 )
      {
        v59 = BitwiseCompareValues(propvarSrc, &ppropvarDest, (unsigned int)v9, a7, v80);
        goto LABEL_118;
      }
      v59 = _SimpleOpCompareValues(propvarSrc, (PROPVARIANT *)&ppropvarDest, a5, a7, v80);
      if ( v59 < 0 )
        goto LABEL_118;
      if ( *v80 )
        goto LABEL_118;
      v74 = v88;
      if ( !v88 || !v73 || (GetPropertyTypeFlags(propkey, PDTF_ISINNATE) & 2) != 0 )
        goto LABEL_118;
      if ( a7 )
      {
        if ( a5 != COP_NOTEQUAL )
          goto LABEL_118;
      }
      else if ( a5 != COP_EQUAL )
      {
        goto LABEL_118;
      }
      v75 = PKA_APPEND;
      lpName = 0;
      if ( (GetPropertyTypeFlags(propkey, PDTF_MULTIPLEVALUES) & 1) == 0 || !*(_WORD *)propvarSrc )
        v75 = PKA_SET;
      v76 = PSCreateSimplePropertyChange(
              v75,
              propkey,
              propvarSrc,
              &GUID_f917bc8a_1bba_4478_a245_1bde03eb9431,
              (void **)&lpName);
      if ( v76 >= 0 )
      {
        v76 = (*(__int64 (__fastcall **)(__int64, LPCWSTR))(*(_QWORD *)v73 + 48LL))(v73, lpName);
        (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)lpName + 16LL))(lpName);
      }
      Instance = v76;
      *v74 = v76 >= 0;
      goto LABEL_54;
    }
    v41 = *((_QWORD *)v11 + 4);
    v42 = *((_DWORD *)v11 + 7);
    v43 = *((_DWORD *)v11 + 6);
    *v80 = 0;
    if ( !InputLocale )
      InputLocale = CConditionEvaluator::_GetInputLocale(v11);
    v87 = 0;
    v44 = 0;
    *(_OWORD *)v86 = 0;
    if ( *(_WORD *)propvarSrc != 31 && *(_WORD *)propvarSrc != 8 )
    {
      v44 = PropVariantChangeType(v86, propvarSrc, 0, 0x1Fu);
      if ( v44 < 0 )
        goto LABEL_117;
      propvarSrc = v86;
    }
    v45 = 0;
    if ( !v43 )
      goto LABEL_107;
    if ( v42 || propkey->pid != 10 )
      goto LABEL_78;
    v55 = *(_QWORD *)&propkey->fmtid.Data1 - *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1;
    if ( *(_QWORD *)&propkey->fmtid.Data1 == *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 )
      v55 = *(_QWORD *)propkey->fmtid.Data4 - *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4;
    if ( v55 )
    {
LABEL_78:
      pdfFlags = PDFF_DEFAULT;
      if ( v41
        && (*(int (__fastcall **)(__int64, PROPERTYKEY *, PROPDESC_FORMAT_FLAGS *))(*(_QWORD *)v41 + 24LL))(
             v41,
             propkey,
             &pdfFlags) >= 0 )
      {
        v46 = pdfFlags;
      }
      else
      {
        v46 = PDFF_ALWAYSKB;
        pdfFlags = PDFF_ALWAYSKB;
      }
      v44 = PSFormatForDisplay(propkey, (const PROPVARIANT *const)&ppropvarDest, v46, pwszText, 0x400u);
      if ( (int)(v44 + 0x80000000) >= 0 && v44 != -2147024774 )
        goto LABEL_117;
      v85 = 0;
      v47 = -1;
      *(_OWORD *)pvar = 0;
      do
        v26 = pwszText[++v47] == 0;
      while ( !v26 );
      v48 = 2 * v47 + 2;
      v49 = CoTaskMemAlloc(v48);
      pvar[1] = v49;
      if ( !v49 )
      {
        v44 = -2147024882;
        goto LABEL_117;
      }
      memcpy_s(v49, v48, pwszText, v48);
      v50 = v83;
      LOWORD(pvar[0]) = 31;
      v44 = 0;
      v51 = a5;
      v45 = _LikeOpCompareValuesWorker(propvarSrc, pvar, a5, InputLocale, *((_DWORD *)v83 + 18));
      PropVariantClear(pvar);
    }
    else
    {
LABEL_107:
      v51 = a5;
      v50 = v83;
    }
    if ( v45 )
      goto LABEL_203;
    if ( v43
      && (v42 && (unsigned int)operator==(propkey, &PKEY_ItemNameDisplay) || !(unsigned int)ShouldSearchRawValue(propkey)) )
    {
      goto LABEL_114;
    }
    p_ppropvarDest = (PROPVARIANT *)&ppropvarDest;
    v85 = 0;
    *(_OWORD *)pvar = 0;
    if ( ppropvarDest.vt != 31 && ppropvarDest.vt != 8 )
    {
      v60 = PropVariantChangeType(pvar, (const PROPVARIANT *const)&ppropvarDest, 0, 0x1Fu);
      v61 = pvar;
      if ( v60 < 0 )
        v61 = (PROPVARIANT *)&ppropvarDest;
      p_ppropvarDest = v61;
    }
    v57 = _LikeOpCompareValuesWorker(propvarSrc, p_ppropvarDest, v51, InputLocale, *((_DWORD *)v50 + 18));
    PropVariantClear(pvar);
    if ( v57 )
    {
LABEL_203:
      if ( a7 )
        goto LABEL_115;
    }
    else
    {
LABEL_114:
      if ( !a7 )
      {
LABEL_115:
        v58 = 0;
LABEL_116:
        *v80 = v58;
LABEL_117:
        PropVariantClear(v86);
        v59 = v44;
LABEL_118:
        Instance = v59;
        goto LABEL_54;
      }
    }
    v58 = 1;
    goto LABEL_116;
  }
  if ( (*(_WORD *)v10 & 0x3000) != 0 )
  {
    lpName = 0;
    Instance = CMultipleValues_CreateInstance(v10, propkey, v19, (void **)&lpName);
    if ( Instance < 0 )
      goto LABEL_54;
    v91[0] = 0;
    Instance = (*(__int64 (__fastcall **)(LPCWSTR, int *))(*(_QWORD *)lpName + 96LL))(lpName, v91);
    if ( Instance < 0 )
    {
LABEL_101:
      (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)lpName + 16LL))(lpName);
      goto LABEL_54;
    }
    v52 = 0;
    v53 = 0;
    while ( 1 )
    {
      if ( v52 || v53 >= v91[0] )
        goto LABEL_101;
      v87 = 0;
      *(_OWORD *)v86 = 0;
      Instance = (*(__int64 (__fastcall **)(LPCWSTR, _QWORD, PROPVARIANT *))(*(_QWORD *)lpName + 88LL))(
                   lpName,
                   (unsigned int)v53,
                   v86);
      if ( Instance >= 0 )
        break;
LABEL_100:
      ++v53;
      if ( Instance < 0 )
        goto LABEL_101;
    }
    v54 = v88;
    if ( v53 )
      v54 = 0;
    Instance = CConditionEvaluator::FilterConditionCompareValues(
                 v83,
                 propvarSrc,
                 v86,
                 propkey,
                 a5,
                 *((_DWORD *)v83 + 6),
                 *((_DWORD *)v83 + 7),
                 *((_QWORD *)v83 + 4),
                 a7,
                 *((_QWORD *)v83 + 6),
                 pdfFlags,
                 pszStr1,
                 InputLocale,
                 v80,
                 v54);
    if ( Instance < 0 )
    {
LABEL_99:
      PropVariantClear(v86);
      goto LABEL_100;
    }
    if ( *v80 )
    {
      if ( !a7 )
      {
LABEL_98:
        v52 = 1;
        goto LABEL_99;
      }
    }
    else if ( a7 )
    {
      goto LABEL_98;
    }
    v52 = 0;
    goto LABEL_99;
  }
  if ( a5 == COP_IMPLICIT )
  {
    Instance = 1;
    goto LABEL_54;
  }
  if ( (unsigned int)(a5 - 7) > 6 )
  {
    v62 = *((_QWORD *)v11 + 6);
    if ( pszStr1 && !StrCmpICW(pszStr1, L"System.StructuredQueryType.SortKeyDescription") )
    {
      Instance = SortKeyCompareValues(
                   (const struct tagPROPVARIANT *)propvarSrc,
                   (const struct tagPROPVARIANT *)v10,
                   a5,
                   a7,
                   v80);
      goto LABEL_54;
    }
    if ( pdfFlags )
    {
      Instance = BitwiseCompareValues(propvarSrc, v10, (unsigned int)pdfFlags, a7, v80);
      goto LABEL_54;
    }
    v63 = v80;
    v64 = propvarSrc;
    *v80 = 0;
    v65 = PKA_APPEND;
    v66 = *(_WORD *)v10;
    v67 = *(_WORD *)v64;
    if ( *(_WORD *)v64 != *(_WORD *)v10 && (!v67 || !v66) )
    {
      v70 = a7;
      if ( a7 )
      {
        if ( a5 != COP_EQUAL )
        {
          Instance = 0;
          goto LABEL_157;
        }
      }
      else if ( a5 != COP_NOTEQUAL )
      {
        goto LABEL_156;
      }
      *v63 = 1;
LABEL_156:
      Instance = 0;
      if ( *v63 )
        goto LABEL_54;
LABEL_157:
      v72 = v88;
      if ( !v88 || !v62 || (GetPropertyTypeFlags(propkey, PDTF_ISINNATE) & 2) != 0 )
        goto LABEL_54;
      if ( v70 )
      {
        if ( a5 != COP_NOTEQUAL )
          goto LABEL_54;
      }
      else if ( a5 != COP_EQUAL )
      {
        goto LABEL_54;
      }
      lpName = 0;
      if ( (GetPropertyTypeFlags(propkey, PDTF_MULTIPLEVALUES) & 1) == 0 || !*(_WORD *)propvarSrc )
        v65 = PKA_SET;
      Instance = PSCreateSimplePropertyChange(
                   v65,
                   propkey,
                   propvarSrc,
                   &GUID_f917bc8a_1bba_4478_a245_1bde03eb9431,
                   (void **)&lpName);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, LPCWSTR))(*(_QWORD *)v62 + 48LL))(v62, lpName);
        (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)lpName + 16LL))(lpName);
      }
      *v72 = Instance >= 0;
      goto LABEL_54;
    }
    v68 = v64;
    memset(&ppropvarDest, 0, sizeof(ppropvarDest));
    if ( v67 != v66 && v66 != 1 && v67 != 1 )
    {
      if ( PropVariantChangeType((PROPVARIANT *)&ppropvarDest, v10, 0, v67) < 0 )
      {
        v68 = (const PROPVARIANT *)&ppropvarDest;
        if ( PropVariantChangeType((PROPVARIANT *)&ppropvarDest, v64, 0, *(_WORD *)v10) < 0 )
          v68 = v64;
      }
      else
      {
        v10 = (PROPVARIANT *)&ppropvarDest;
      }
    }
    v69 = PropVariantCompareEx(v10, v68, PVCU_DEFAULT, 0);
    *v63 = 0;
    switch ( a5 )
    {
      case COP_EQUAL:
        v70 = a7;
        if ( v69 )
          break;
        goto LABEL_171;
      case COP_NOTEQUAL:
        v70 = a7;
        if ( v69 )
        {
          if ( a7 )
            goto LABEL_172;
          goto LABEL_154;
        }
        break;
      case COP_LESSTHAN:
        v70 = a7;
        if ( v69 < 0 )
        {
          if ( a7 )
            goto LABEL_172;
LABEL_154:
          v71 = 1;
LABEL_155:
          *v63 = v71;
          PropVariantClear((PROPVARIANT *)&ppropvarDest);
          goto LABEL_156;
        }
        break;
      case COP_GREATERTHAN:
        v70 = a7;
        if ( v69 > 0 )
        {
          if ( a7 )
            goto LABEL_172;
          goto LABEL_154;
        }
        break;
      case COP_LESSTHANOREQUAL:
        v70 = a7;
        if ( v69 <= 0 )
        {
          if ( a7 )
            goto LABEL_172;
          goto LABEL_154;
        }
        break;
      case COP_GREATERTHANOREQUAL:
        v70 = a7;
        if ( v69 >= 0 )
        {
LABEL_171:
          if ( v70 )
            goto LABEL_172;
          goto LABEL_154;
        }
        break;
      default:
        PropVariantClear((PROPVARIANT *)&ppropvarDest);
        Instance = -2147024809;
        goto LABEL_54;
    }
    if ( v70 )
      goto LABEL_154;
LABEL_172:
    v71 = 0;
    goto LABEL_155;
  }
  v20 = *((_QWORD *)v11 + 4);
  v21 = *((_DWORD *)v11 + 7);
  v22 = *((_DWORD *)v11 + 6);
  *v80 = 0;
  if ( !InputLocale )
    InputLocale = CConditionEvaluator::_GetInputLocale(v11);
  Instance = 0;
  memset(&ppropvarDest, 0, sizeof(ppropvarDest));
  if ( *(_WORD *)propvarSrc != 31 && *(_WORD *)propvarSrc != 8 )
  {
    Instance = PropVariantChangeType((PROPVARIANT *)&ppropvarDest, propvarSrc, 0, 0x1Fu);
    if ( Instance < 0 )
      goto LABEL_53;
    propvarSrc = (PROPVARIANT *)&ppropvarDest;
  }
  if ( !v22 )
    goto LABEL_41;
  if ( v21 || propkey->pid != 10 )
    goto LABEL_21;
  v34 = *(_QWORD *)&propkey->fmtid.Data1 - *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1;
  if ( *(_QWORD *)&propkey->fmtid.Data1 == *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 )
    v34 = *(_QWORD *)propkey->fmtid.Data4 - *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4;
  if ( v34 )
  {
LABEL_21:
    pdfFlags = PDFF_DEFAULT;
    if ( v20
      && (*(int (__fastcall **)(__int64, PROPERTYKEY *, PROPDESC_FORMAT_FLAGS *))(*(_QWORD *)v20 + 24LL))(
           v20,
           propkey,
           &pdfFlags) >= 0 )
    {
      v24 = pdfFlags;
    }
    else
    {
      v24 = PDFF_ALWAYSKB;
      pdfFlags = PDFF_ALWAYSKB;
    }
    Instance = PSFormatForDisplay(propkey, propvar, v24, pwszText, 0x400u);
    if ( (int)(Instance + 0x80000000) >= 0 && Instance != -2147024774 )
      goto LABEL_53;
    v85 = 0;
    v25 = -1;
    *(_OWORD *)pvar = 0;
    do
      v26 = pwszText[++v25] == 0;
    while ( !v26 );
    v27 = 2 * v25 + 2;
    v28 = CoTaskMemAlloc(v27);
    pvar[1] = v28;
    if ( !v28 )
    {
      Instance = -2147024882;
      goto LABEL_53;
    }
    if ( v27 )
      memcpy_0(v28, pwszText, v27);
    v29 = v83;
    LOWORD(pvar[0]) = 31;
    Instance = 0;
    v30 = a5;
    v18 = _LikeOpCompareValuesWorker(propvarSrc, pvar, a5, InputLocale, *((_DWORD *)v83 + 18));
    PropVariantClear(pvar);
  }
  else
  {
LABEL_41:
    v30 = a5;
    v29 = v83;
  }
  if ( v18 )
    goto LABEL_224;
  if ( !v22 )
    goto LABEL_228;
  if ( !v21 || !(unsigned int)operator==(propkey, &PKEY_ItemNameDisplay) )
  {
    pdfFlags = PDFF_DEFAULT;
    lpName = 0;
    if ( PSGetPropertyDescription(propkey, &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, (void **)&lpName) >= 0 )
    {
      (*(void (__fastcall **)(LPCWSTR, __int64, PROPDESC_FORMAT_FLAGS *))(*(_QWORD *)lpName + 64LL))(
        lpName,
        1024,
        &pdfFlags);
      (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)lpName + 16LL))(lpName);
    }
    if ( (pdfFlags & 0x400) != 0 )
    {
LABEL_228:
      v35 = propvar;
      v87 = 0;
      *(_OWORD *)v86 = 0;
      if ( *(_WORD *)propvar != 31 && *(_WORD *)propvar != 8 )
      {
        v39 = PropVariantChangeType(v86, propvar, 0, 0x1Fu);
        v40 = v86;
        if ( v39 < 0 )
          v40 = v35;
        v35 = v40;
      }
      v36 = _LikeOpCompareValuesWorker(propvarSrc, v35, v30, InputLocale, *((_DWORD *)v29 + 18));
      PropVariantClear(v86);
      if ( v36 )
      {
LABEL_224:
        if ( a7 )
          goto LABEL_51;
LABEL_103:
        v37 = 1;
        goto LABEL_52;
      }
    }
  }
  if ( a7 )
    goto LABEL_103;
LABEL_51:
  v37 = 0;
LABEL_52:
  *v80 = v37;
LABEL_53:
  PropVariantClear((PROPVARIANT *)&ppropvarDest);
LABEL_54:
  CoTaskMemFree((LPVOID)pszStr1);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002a880  push    rbp
0x18002a882  push    rbx
0x18002a883  push    rsi
0x18002a884  push    rdi
0x18002a885  push    r12
0x18002a887  push    r13
0x18002a889  push    r14
0x18002a88b  lea     rbp, [rsp-840h]
0x18002a893  sub     rsp, 940h
0x18002a89a  mov     rax, cs:__security_cookie
0x18002a8a1  xor     rax, rsp
0x18002a8a4  mov     [rbp+870h+var_50], rax
0x18002a8ab  mov     rax, [rbp+870h+arg_40]
0x18002a8b2  xor     r14d, r14d
0x18002a8b5  mov     r13d, [rbp+870h+arg_20]
0x18002a8bc  mov     r12, r8
0x18002a8bf  mov     rsi, [rbp+870h+arg_28]
0x18002a8c6  mov     rdi, rcx
0x18002a8c9  mov     [rbp+870h+var_878], rax
0x18002a8cd  mov     ebx, 2
0x18002a8d2  mov     rax, [rbp+870h+arg_38]
0x18002a8d9  mov     [rbp+870h+var_8D8], rax
0x18002a8dd  mov     [rbp+870h+propkey], r9
0x18002a8e1  mov     [rbp+870h+propvar], r8
0x18002a8e5  mov     [rbp+870h+propvarSrc], rdx
0x18002a8e9  mov     [rbp+870h+var_8B0], rcx
0x18002a8ed  mov     [rbp+870h+pdfFlags], r14d
0x18002a8f1  cmp     r13d, 0Eh
0x18002a8f5  jz      loc_18002AB3C
0x18002a8fb  mov     rax, [rsi]
0x18002a8fe  lea     r8, [rbp+870h+var_860]
0x18002a902  mov     [rsp+970h+var_38], r15
0x18002a90a  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18002a911  xor     r15d, r15d
0x18002a914  mov     rcx, rsi
0x18002a917  mov     qword ptr [rbp+870h+var_860], r15
0x18002a91b  mov     rax, [rax]
0x18002a91e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a923  mov     ebx, eax
0x18002a925  test    eax, eax
0x18002a927  js      short loc_18002A982
0x18002a929  mov     rdi, qword ptr [rbp+870h+var_860]
0x18002a92d  xor     ecx, ecx; pv
0x18002a92f  mov     [rbp+870h+lpName], r15
0x18002a933  mov     rax, [rdi]
0x18002a936  mov     rbx, [rax+78h]
0x18002a93a  call    cs:__imp_CoTaskMemFree
0x18002a940  lea     rdx, [rbp+870h+lpName]
0x18002a944  mov     rcx, rdi
0x18002a947  mov     rax, rbx
0x18002a94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a94f  mov     ebx, eax
0x18002a951  test    eax, eax
0x18002a953  js      short loc_18002A974
0x18002a955  mov     rcx, [rbp+870h+lpName]; lpName
0x18002a959  xor     edx, edx; dwFlags
0x18002a95b  call    cs:__imp_LocaleNameToLCID
0x18002a961  mov     r15d, eax
0x18002a964  mov     eax, 7Fh
0x18002a969  cmp     r15d, 1000h
0x18002a970  cmovz   r15d, eax
0x18002a974  mov     rcx, [rbp+870h+lpName]; pv
0x18002a978  call    cs:__imp_CoTaskMemFree
0x18002a97e  mov     rdi, [rbp+870h+var_8B0]
0x18002a982  mov     rcx, qword ptr [rbp+870h+var_860]
0x18002a986  test    rcx, rcx
0x18002a989  jz      short loc_18002A997
0x18002a98b  mov     rax, [rcx]
0x18002a98e  mov     rax, [rax+10h]
0x18002a992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a997  test    ebx, ebx
0x18002a999  js      loc_18002B549
0x18002a99f  mov     rax, [rsi]
0x18002a9a2  lea     rdx, [rbp+870h+pszStr1]
0x18002a9a6  xor     ebx, ebx
0x18002a9a8  mov     rcx, rsi
0x18002a9ab  mov     [rbp+870h+pszStr1], rbx
0x18002a9af  mov     rax, [rax+58h]
0x18002a9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9b8  mov     rcx, r12; propvar
0x18002a9bb  call    cs:__imp_PropVariantGetElementCount
0x18002a9c1  test    eax, eax
0x18002a9c3  jz      loc_18002AD84
0x18002a9c9  mov     eax, 3000h
0x18002a9ce  test    [r12], ax
0x18002a9d3  jnz     loc_18002AF0B
0x18002a9d9  test    r13d, r13d
0x18002a9dc  jz      loc_18002B050
0x18002a9e2  lea     eax, [r13-7]
0x18002a9e6  cmp     eax, 6
0x18002a9e9  ja      loc_18002B1DA
0x18002a9ef  mov     rax, [rbp+870h+var_8D8]
0x18002a9f3  mov     r12, [rdi+20h]
0x18002a9f7  mov     r14d, [rdi+1Ch]
0x18002a9fb  mov     esi, [rdi+18h]
0x18002a9fe  mov     [rax], ebx
0x18002aa00  test    r15d, r15d
0x18002aa03  jz      loc_18002B6E8
0x18002aa09  mov     rcx, [rbp+870h+propvarSrc]
0x18002aa0d  xor     eax, eax
0x18002aa0f  mov     [rbp+870h+var_8B8], rax
0x18002aa13  mov     r13d, 1Fh
0x18002aa19  xorps   xmm0, xmm0
0x18002aa1c  mov     edi, ebx
0x18002aa1e  movups  xmmword ptr [rbp+870h+ppropvarDest], xmm0
0x18002aa22  movzx   eax, word ptr [rcx]
0x18002aa25  cmp     ax, r13w
0x18002aa29  jnz     loc_18002ACE5
0x18002aa2f  test    esi, esi
0x18002aa31  jz      loc_18002ABC8
0x18002aa37  mov     rcx, [rbp+870h+propkey]
0x18002aa3b  test    r14d, r14d
0x18002aa3e  jnz     short loc_18002AA4A
0x18002aa40  cmp     dword ptr [rcx+10h], 0Ah
0x18002aa44  jz      loc_18002ABA8
0x18002aa4a  mov     [rbp+870h+pdfFlags], ebx
0x18002aa4d  test    r12, r12
0x18002aa50  jz      loc_18002AEFC
0x18002aa56  mov     rax, [r12]
0x18002aa5a  lea     r8, [rbp+870h+pdfFlags]
0x18002aa5e  mov     rdx, rcx
0x18002aa61  mov     rcx, r12
0x18002aa64  mov     rax, [rax+18h]
0x18002aa68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa6d  test    eax, eax
0x18002aa6f  js      loc_18002AEFC
0x18002aa75  mov     r8d, [rbp+870h+pdfFlags]; pdfFlags
0x18002aa79  mov     rdx, [rbp+870h+propvar]; propvar
0x18002aa7d  lea     r9, [rbp+870h+pwszText]; pwszText
0x18002aa81  mov     rcx, [rbp+870h+propkey]; propkey
0x18002aa85  mov     [rsp+970h+cchText], 400h; cchText
0x18002aa8d  call    cs:__imp_PSFormatForDisplay
0x18002aa93  mov     ecx, 80000000h
0x18002aa98  mov     edi, eax
0x18002aa9a  add     eax, ecx
0x18002aa9c  test    ecx, eax
0x18002aa9e  jz      loc_18002AD73
0x18002aaa4  xor     eax, eax
0x18002aaa6  lea     rcx, [rbp+870h+pwszText]
0x18002aaaa  xorps   xmm0, xmm0
0x18002aaad  mov     [rbp+870h+var_898], rax
0x18002aab1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002aab8  movups  xmmword ptr [rbp+870h+pvar], xmm0
0x18002aabc  nop     dword ptr [rax+00h]
0x18002aac0  cmp     [rcx+rax*2+2], bx
0x18002aac5  lea     rax, [rax+1]
0x18002aac9  jnz     short loc_18002AAC0
0x18002aacb  lea     rbx, ds:2[rax*2]
0x18002aad3  mov     rcx, rbx; cb
0x18002aad6  call    cs:__imp_CoTaskMemAlloc
0x18002aadc  mov     [rbp+870h+pvar+8], rax
0x18002aae0  test    rax, rax
0x18002aae3  jz      loc_18002B6F8
0x18002aae9  test    rbx, rbx
0x18002aaec  jz      short loc_18002AAFD
0x18002aaee  mov     r8, rbx; Size
0x18002aaf1  lea     rdx, [rbp+870h+pwszText]; Src
0x18002aaf5  mov     rcx, rax; void *
0x18002aaf8  call    memcpy_0
0x18002aafd  mov     r12, [rbp+870h+var_8B0]
0x18002ab01  lea     rdx, [rbp+870h+pvar]; PROPVARIANT *
0x18002ab05  mov     rcx, [rbp+870h+propvarSrc]; propvarIn
0x18002ab09  mov     r9d, r15d; Locale
0x18002ab0c  mov     word ptr [rbp+870h+pvar], r13w
0x18002ab11  xor     edi, edi
0x18002ab13  mov     r13d, [rbp+870h+arg_20]
0x18002ab1a  mov     r8d, r13d; enum tagCONDITION_OPERATION
0x18002ab1d  mov     eax, [r12+48h]
0x18002ab22  mov     [rsp+970h+cchText], eax; unsigned int
0x18002ab26  call    ?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z; _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)
0x18002ab2b  lea     rcx, [rbp+870h+pvar]; pvar
0x18002ab2f  mov     ebx, eax
0x18002ab31  call    cs:__imp_PropVariantClear
0x18002ab37  jmp     loc_18002ABDB
0x18002ab3c  mov     rax, [rsi]
0x18002ab3f  lea     rdx, [rbp+870h+pszStr1]
0x18002ab43  mov     rcx, rsi
0x18002ab46  mov     [rbp+870h+pszStr1], r14
0x18002ab4a  mov     rax, [rax+58h]
0x18002ab4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab53  test    eax, eax
0x18002ab55  js      loc_18002ACC4
0x18002ab5b  mov     rcx, [rbp+870h+pszStr1]; pszStr1
0x18002ab5f  test    rcx, rcx
0x18002ab62  jz      loc_18002A8FB
0x18002ab68  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18002ab6f  nop
0x18002ab70  inc     r8; nChar
0x18002ab73  cmp     [rcx+r8*2], r14w
0x18002ab78  jnz     short loc_18002AB70
0x18002ab7a  lea     rdx, pszStr2; "System.StructuredQueryType.AnyBitsSet"
0x18002ab81  call    cs:__imp_StrCmpNICW
0x18002ab87  test    eax, eax
0x18002ab89  jnz     loc_18002AD15
0x18002ab8f  mov     r14d, 3
0x18002ab95  mov     rcx, [rbp+870h+pszStr1]; pv
0x18002ab99  mov     [rbp+870h+pdfFlags], r14d
0x18002ab9d  call    cs:__imp_CoTaskMemFree
0x18002aba3  jmp     loc_18002A8FB
0x18002aba8  mov     rax, [rcx]
0x18002abab  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18002abb2  jnz     short loc_18002ABBF
0x18002abb4  mov     rax, [rcx+8]
0x18002abb8  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data4
0x18002abbf  test    rax, rax
0x18002abc2  jnz     loc_18002AA4A
0x18002abc8  test    edi, edi
0x18002abca  js      loc_18002ACA6
0x18002abd0  mov     r13d, [rbp+870h+arg_20]
0x18002abd7  mov     r12, [rbp+870h+var_8B0]
0x18002abdb  test    ebx, ebx
0x18002abdd  jnz     loc_18002B71F
0x18002abe3  test    esi, esi
0x18002abe5  jz      short loc_18002AC44
0x18002abe7  test    r14d, r14d
0x18002abea  jnz     loc_18002B702
0x18002abf0  mov     rcx, [rbp+870h+propkey]; propkey
0x18002abf4  lea     r8, [rbp+870h+lpName]; ppv
0x18002abf8  xor     eax, eax
0x18002abfa  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x18002ac01  mov     [rbp+870h+pdfFlags], eax
0x18002ac04  mov     [rbp+870h+lpName], rax
0x18002ac08  call    cs:__imp_PSGetPropertyDescription
0x18002ac0e  test    eax, eax
0x18002ac10  js      short loc_18002AC3B
0x18002ac12  mov     rcx, [rbp+870h+lpName]
0x18002ac16  lea     r8, [rbp+870h+pdfFlags]
0x18002ac1a  mov     edx, 400h
0x18002ac1f  mov     rax, [rcx]
0x18002ac22  mov     rax, [rax+40h]
0x18002ac26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac2b  mov     rcx, [rbp+870h+lpName]
0x18002ac2f  mov     rax, [rcx]
0x18002ac32  mov     rax, [rax+10h]
0x18002ac36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac3b  test    [rbp+870h+pdfFlags], 400h
0x18002ac42  jz      short loc_18002AC91
0x18002ac44  mov     rbx, [rbp+870h+propvar]
0x18002ac48  xor     eax, eax
0x18002ac4a  mov     [rbp+870h+var_880], rax
0x18002ac4e  xorps   xmm0, xmm0
0x18002ac51  movups  xmmword ptr [rbp+870h+var_890], xmm0
0x18002ac55  movzx   eax, word ptr [rbx]
0x18002ac58  cmp     ax, 1Fh
0x18002ac5c  jnz     loc_18002AD42
0x18002ac62  mov     eax, [r12+48h]
0x18002ac67  mov     r9d, r15d; Locale
0x18002ac6a  mov     rcx, [rbp+870h+propvarSrc]; propvarIn
0x18002ac6e  mov     r8d, r13d; enum tagCONDITION_OPERATION
0x18002ac71  mov     rdx, rbx; PROPVARIANT *
0x18002ac74  mov     [rsp+970h+cchText], eax; unsigned int
0x18002ac78  call    ?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z; _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)
0x18002ac7d  lea     rcx, [rbp+870h+var_890]; pvar
0x18002ac81  mov     ebx, eax
0x18002ac83  call    cs:__imp_PropVariantClear
0x18002ac89  test    ebx, ebx
0x18002ac8b  jnz     loc_18002B71F
0x18002ac91  cmp     [rbp+870h+arg_30], 0
0x18002ac98  jnz     loc_18002B05A
0x18002ac9e  xor     ebx, ebx
0x18002aca0  mov     rax, [rbp+870h+var_8D8]
0x18002aca4  mov     [rax], ebx
0x18002aca6  lea     rcx, [rbp+870h+ppropvarDest]; pvar
0x18002acaa  call    cs:__imp_PropVariantClear
0x18002acb0  mov     rcx, [rbp+870h+pszStr1]; pv
0x18002acb4  call    cs:__imp_CoTaskMemFree
0x18002acba  mov     r15, [rsp+970h+var_38]
0x18002acc2  mov     eax, edi
0x18002acc4  mov     rcx, [rbp+870h+var_50]
0x18002accb  xor     rcx, rsp; StackCookie
0x18002acce  call    __security_check_cookie
0x18002acd3  add     rsp, 940h
0x18002acda  pop     r14
0x18002acdc  pop     r13
0x18002acde  pop     r12
0x18002ace0  pop     rdi
0x18002ace1  pop     rsi
0x18002ace2  pop     rbx
0x18002ace3  pop     rbp
0x18002ace4  retn
0x18002ace5  cmp     ax, 8
0x18002ace9  jz      loc_18002AA2F
0x18002acef  mov     rdx, rcx; propvarSrc
0x18002acf2  mov     r9d, r13d; vt
0x18002acf5  lea     rcx, [rbp+870h+ppropvarDest]; ppropvarDest
0x18002acf9  xor     r8d, r8d; flags
0x18002acfc  call    cs:__imp_PropVariantChangeType
0x18002ad02  mov     edi, eax
0x18002ad04  test    eax, eax
0x18002ad06  js      short loc_18002ACA6
0x18002ad08  lea     rax, [rbp+870h+ppropvarDest]
0x18002ad0c  mov     [rbp+870h+propvarSrc], rax
0x18002ad10  jmp     loc_18002AA2F
0x18002ad15  mov     rcx, [rbp+870h+pszStr1]; pszStr1
0x18002ad19  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18002ad20  inc     r8; nChar
0x18002ad23  cmp     [rcx+r8*2], r14w
0x18002ad28  jnz     short loc_18002AD20
0x18002ad2a  lea     rdx, aSystemStructur_0; "System.StructuredQueryType.AllBitsSet"
0x18002ad31  call    cs:__imp_StrCmpNICW
  ... truncated ...
```
