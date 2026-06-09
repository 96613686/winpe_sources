# EmitPropertyStoreContent(wchar_t const *,int,CFilterSink &,unsigned __int64 &,unsigned __int64 &,IUrlAccessor *,IBindCtx *,CFilterThread *,int,int,IOpLockStatus *)

- ea: `0x140014c94`
- end: `0x1400155e1`
- name: `?EmitPropertyStoreContent@@YAJPEB_WHAEAVCFilterSink@@AEA_K2PEAUIUrlAccessor@@PEAUIBindCtx@@PEAVCFilterThread@@HHPEAUIOpLockStatus@@@Z`
- size: `2381`
- prototype: `__int64 __usercall@<rax>(const wchar_t *@<rcx>, int@<edx>, struct CFilterSink *@<r8>, unsigned __int64 *@<r9>, unsigned __int64 *, struct IUrlAccessor *, struct IBindCtx *, struct CFilterThread *, int, int, struct IOpLockStatus *)`
- caller_count: `2`
- callee_count: `32`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x140005240`
- `0x1400061ec`
- `0x14000cce4`
- `0x14000d7dc`
- `0x14000e898`
- `0x14000fd60`
- `0x14001139c`
- `0x14001263c`
- `0x1400128f8`
- `0x140012c80`
- `0x140012e1c`
- `0x1400133e0`
- `0x140014c94`
- `0x14001cbf0`
- `0x14001cf94`
- `0x14001f0c0`
- `0x14001f90c`
- `0x14001fbbc`
- `0x140021af4`
- `0x140025760`
- `0x14002581c`
- `0x140028044`
- `0x140029080`
- `0x140033530`
- `0x14003376c`
- `0x1400339d0`
- `0x140033cf8`
- `0x140033db0`
- `0x1400344e4`
- `0x14003942c`
- `0x14004debc`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140014f79`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140015169`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1400151a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1400153e0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140015557`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140015583`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140014f79`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140015169`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1400151a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1400153e0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140015557`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140015583`

## string_xrefs

- `0x140014d39`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrdaemon.cxx`
- `0x140014e3f`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrdaemon.cxx`
- `0x140014e90`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrdaemon.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall EmitPropertyStoreContent(
        wchar_t *a1,
        unsigned int a2,
        struct CFilterSink *a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5,
        struct IUrlAccessor *a6,
        struct IBindCtx *a7,
        struct IPluginResourceManager **a8,
        int a9,
        int a10,
        struct IOpLockStatus *a11)
{
  struct IUrlAccessor *v13; // r15
  int FilterHostWrapper; // eax
  int v15; // esi
  bool v16; // zf
  struct IFilterHost *v17; // rbx
  int v18; // eax
  int v19; // r8d
  int v20; // edi
  __int64 v21; // rcx
  unsigned int v22; // eax
  char v23; // di
  int v24; // eax
  wchar_t *bstrVal; // r15
  int v26; // eax
  unsigned __int64 QuadPart; // rdi
  int IsSemanticIndexingActive; // eax
  int v29; // eax
  int v30; // eax
  PROPVARIANT v31; // rdi
  int v32; // eax
  struct tagPROPVARIANT *p_pvar; // rdx
  unsigned __int64 v34; // r15
  int v35; // eax
  struct IFilterHost *v36; // rbx
  int v37; // r8d
  char v38; // r15
  unsigned int v39; // r14d
  bool v40; // sf
  int v41; // eax
  int v42; // edi
  int v43; // r8d
  char v44; // di
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  const struct _GUID *v48; // [rsp+28h] [rbp-D8h]
  char v49; // [rsp+40h] [rbp-C0h]
  struct IPropertyStore *v50; // [rsp+48h] [rbp-B8h] BYREF
  struct IFilterHost *v51; // [rsp+50h] [rbp-B0h] BYREF
  int v52; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v53; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v54; // [rsp+60h] [rbp-A0h]
  wchar_t *v55; // [rsp+68h] [rbp-98h] BYREF
  struct IUrlAccessor *v56; // [rsp+70h] [rbp-90h]
  struct CFilterThread *v57; // [rsp+78h] [rbp-88h]
  struct IOpLockStatus *v58; // [rsp+80h] [rbp-80h]
  unsigned __int64 *v59; // [rsp+88h] [rbp-78h]
  __int64 v60; // [rsp+90h] [rbp-70h] BYREF
  PROPVARIANT v61[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  wchar_t **v64; // [rsp+B8h] [rbp-48h]
  char v65; // [rsp+C0h] [rbp-40h]
  struct tagPROPVARIANT pvar; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v67; // [rsp+E0h] [rbp-20h]
  struct _tagpropertykey Buf1; // [rsp+F0h] [rbp-10h] BYREF
  GUID v69; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v70[80]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v63 = -2;
  v59 = a4;
  v54 = a2;
  v55 = a1;
  v13 = a6;
  v56 = a6;
  v57 = (struct CFilterThread *)a8;
  v58 = a11;
  v64 = &v55;
  v65 = 1;
  v51 = 0;
  FilterHostWrapper = GetFilterHostWrapper((struct CFilterThread *)a8, a1, &v51);
  v15 = FilterHostWrapper;
  if ( FilterHostWrapper < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x187E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
      (const char *)(unsigned int)FilterHostWrapper,
      v46);
    v16 = v51 == 0;
    goto LABEL_53;
  }
  v50 = 0;
  v17 = v51;
  v18 = BindToPropertyHandler(v55, a2 == 0, a6, a7, v51, v48, (IBindCtx *)&v50);
  v15 = v18;
  if ( v18 == -2147467263 )
  {
    TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&v50);
    v20 = 0;
LABEL_109:
    if ( v17 )
      winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v51);
    return (unsigned int)v20;
  }
  if ( v18 >= 0 )
    v15 = CheckIfShouldExit((struct CFilterThread *)a8, a9, v19, v58);
  v69 = 0;
  *(_QWORD *)&Buf1.fmtid.Data1 = 0;
  if ( v17 )
  {
    *(_DWORD *)&pvar.vt = 2123;
    pvar.hVal.QuadPart = (LONGLONG)"onecoreuap\\Internal\\BuildMetadata\\cppwinrt\\winrt\\base.h";
    pvar.bstrblobVal.pData = 0;
    v22 = (**(__int64 (__fastcall ***)(struct IFilterHost *, __int64 *, struct _tagpropertykey *))v17)(
            v17,
            &winrt::impl::guid_v<IPersist>,
            &Buf1);
    winrt::check_hresult(&v52, v22, &pvar);
    v21 = *(_QWORD *)&Buf1.fmtid.Data1;
  }
  else
  {
    v21 = 0;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v21 + 24LL))(v21, &v69);
  winrt::com_ptr<ITextFilter>::unconditional_release_ref(&Buf1);
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1892,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
      (const char *)(unsigned int)v20,
      v47);
LABEL_108:
    TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&v50);
    goto LABEL_109;
  }
  Buf1.fmtid = v69;
  PluginSignalHelper::PluginSignalHelper((PluginSignalHelper *)v70, a8[47], &Buf1.fmtid, v55);
  PluginSignalHelper::Start((PluginSignalHelper *)v70, 1);
  v23 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl)
    && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56143448>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56143448>::GetImpl'::`2'::impl) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( v15 >= 0 && v50 )
    {
      v24 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v50->lpVtbl->GetValue)(
              v50,
              &PKEY_FileExtension,
              &pvar);
      if ( v24 >= 0 )
      {
        if ( pvar.vt == 31 )
        {
          bstrVal = pvar.bstrVal;
          if ( pvar.hVal.QuadPart )
          {
            v26 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))v50->lpVtbl->GetValue)(
                    v50,
                    &PKEY_Size,
                    &pvar);
            if ( v26 >= 0 )
            {
              QuadPart = pvar.uhVal.QuadPart;
              IsSemanticIndexingActive = GetIsSemanticIndexingActive((const wchar_t *)retaddr);
              SemanticSearchTelemetryAggregated::ReportExtensionUsage(IsSemanticIndexingActive != 0, bstrVal, QuadPart);
              v23 = 0;
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x18A7,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
                (const char *)(unsigned int)v26,
                v47);
            }
          }
          v13 = v56;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18A2,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
          (const char *)(unsigned int)v24,
          v47);
      }
    }
    PropVariantClear((PROPVARIANT *)&pvar);
  }
  *(_OWORD *)v61 = 0;
  v62 = 0;
  if ( v15 >= 0 && v50 )
  {
    v29 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v50->lpVtbl->GetValue)(
            v50,
            &PKEY_FileExtension,
            v61);
    if ( v29 >= 0 )
    {
      if ( LOWORD(v61[0]) == 31 && v61[1] )
      {
        std::wstring::wstring(&pvar, v61[1]);
        v30 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v50->lpVtbl->GetValue)(
                v50,
                &PKEY_Size,
                v61);
        if ( v30 >= 0 )
        {
          v31 = v61[1];
          v32 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v50->lpVtbl->GetValue)(
                  v50,
                  &PKEY_Media_Duration,
                  v61);
          if ( v32 >= 0 )
          {
            if ( LOWORD(v61[0]) )
            {
              p_pvar = &pvar;
              if ( v67 > 7 )
                p_pvar = *(struct tagPROPVARIANT **)&pvar.vt;
              SearchIndexerTelemetryAggregated::ReportExtensionUsageWithDuration(
                (unsigned __int64)v31,
                &p_pvar->vt,
                (unsigned __int64)v61[1] / 0x23C34600);
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x18BC,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
              (const char *)(unsigned int)v32,
              v47);
          }
          v23 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x18B9,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
            (const char *)(unsigned int)v30,
            v47);
        }
        std::wstring::_Tidy_deallocate(&pvar);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x18B4,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
        (const char *)(unsigned int)v29,
        v47);
    }
  }
  v49 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56280500>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56280500>::GetImpl'::`2'::impl) )
  {
    std::wstring::wstring(&pvar, *((_QWORD *)a3 + 138));
    v23 = IsSemanticPropertyIndexingApplicableOnUrl(&pvar);
    v49 = v23;
    std::wstring::_Tidy_deallocate(&pvar);
  }
  if ( (*((_DWORD *)a3 + 422) & 0x40000) == 0 )
  {
    v20 = 0;
    v53 = 0;
    if ( v15 >= 0 )
    {
      v15 = ((__int64 (__fastcall *)(struct IPropertyStore *, unsigned int *))v50->lpVtbl->GetCount)(v50, &v53);
      if ( v15 >= 0 )
        v15 = CheckIfShouldExit((struct CFilterThread *)a8, a9, v37, v58);
    }
    v60 = 0;
    ((void (__fastcall *)(struct IUrlAccessor *, GUID *, __int64 *))v13->lpVtbl->QueryInterface)(
      v13,
      &GUID_5cc51041_c8d2_41d7_bca3_9e9e286297dc,
      &v60);
    v38 = 0;
    v39 = 0;
    if ( v15 < 0 )
    {
LABEL_105:
      if ( v15 != 1 )
        v20 = v15;
      TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&v60);
      PropVariantClear(v61);
      PluginSignalHelper::~PluginSignalHelper((PluginSignalHelper *)v70);
      goto LABEL_108;
    }
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v15 == 266761 || v39 >= v53 )
        {
LABEL_104:
          v17 = v51;
          goto LABEL_105;
        }
        memset(&Buf1, 0, sizeof(Buf1));
        if ( ((int (__fastcall *)(struct IPropertyStore *, _QWORD, struct _tagpropertykey *))v50->lpVtbl->GetAt)(
               v50,
               v39,
               &Buf1) >= 0
          && (Buf1.pid != PKEY_ItemFolderNameDisplay.pid || memcmp_0(&Buf1, &PKEY_ItemFolderNameDisplay, 0x10u)) )
        {
          if ( (unsigned int)IsColumnOrInInvertedIndex(&Buf1) )
          {
            v52 = 1;
            if ( !v60 )
              break;
            v40 = (*(int (__fastcall **)(__int64, struct _tagpropertykey *, int *))(*(_QWORD *)v60 + 168LL))(
                    v60,
                    &Buf1,
                    &v52) < 0;
            v41 = 1;
            if ( v40 )
              v41 = v52;
            if ( v41 )
              break;
          }
        }
        v15 = 0;
LABEL_81:
        ++v39;
      }
      memset(&pvar, 0, sizeof(pvar));
      v42 = ((__int64 (__fastcall *)(struct IPropertyStore *, struct _tagpropertykey *, struct tagPROPVARIANT *))v50->lpVtbl->GetValue)(
              v50,
              &Buf1,
              &pvar);
      v15 = CheckIfShouldExit((struct CFilterThread *)a8, a9, v43, v58);
      if ( v15 < 0 )
        goto LABEL_103;
      v15 = 0;
      if ( v42 < 0 )
      {
        v20 = 0;
        PropVariantClear((PROPVARIANT *)&pvar);
        goto LABEL_81;
      }
      if ( Buf1.pid != 2 || memcmp_0(&Buf1, PKEY_Search_ContentSnippet, 0x10u) )
        break;
      if ( (*((_DWORD *)a3 + 422) & 0x10000) == 0 && v54 )
      {
        ETWLog::Log(L"Did NOT process ContentSnippet for %s, Indexing Content: %d, has file IFilter: %d", v55, v54, 1);
        v15 = v42;
LABEL_102:
        PluginSignalHelper::Ack((PluginSignalHelper *)v70);
        goto LABEL_103;
      }
      v15 = ProcessContentSnippet(&pvar, a3, v59, a5);
      ETWLog::Log(
        L"Processed ContentSnippet for %s, Indexing Content: %d, has file IFilter: %d",
        v55,
        v54,
        (*((_WORD *)a3 + 845) & 1) == 0);
LABEL_101:
      if ( v15 >= 0 )
        goto LABEL_102;
LABEL_103:
      PropVariantClear((PROPVARIANT *)&pvar);
      ++v39;
      v20 = 0;
      if ( v15 < 0 )
        goto LABEL_104;
    }
    v15 = ComputePropertyChunk(a3, &Buf1, (struct CComPropVariant *)&pvar, v59, a5);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56280500>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56280500>::GetImpl'::`2'::impl) )
      {
        v44 = v49;
        if ( v49 && v15 >= 0 )
          v15 = ComputeSemanticPropertyChunk((struct CFilterThread *)a8, a3, &Buf1, (struct CComPropVariant *)&pvar);
LABEL_97:
        if ( !v38 && v44 )
        {
          if ( v15 < 0 )
            goto LABEL_103;
          v38 = 1;
          v15 = CreateAndIndexCombinedPathProperty((struct CFilterThread *)a8, a3, v50);
        }
        goto LABEL_101;
      }
      CURL::ParseAccessType((struct CFilterSink *)((char *)a3 + 1072));
      if ( !*((_WORD *)a3 + 756) && v15 >= 0 )
        v15 = ComputeSemanticPropertyChunk((struct CFilterThread *)a8, a3, &Buf1, (struct CComPropVariant *)&pvar);
    }
    v44 = v49;
    goto LABEL_97;
  }
  v34 = 0;
  while ( v15 >= 0 )
  {
    memset(&pvar, 0, sizeof(pvar));
    v35 = ((__int64 (__fastcall *)(struct IPropertyStore *, char *, struct tagPROPVARIANT *))v50->lpVtbl->GetValue)(
            v50,
            (char *)&xmmword_140098560 + 20 * v34,
            &pvar);
    if ( v35 >= 0 )
    {
      v15 = ComputePropertyChunk(
              a3,
              (const struct _tagpropertykey *)&xmmword_140098560 + v34,
              (struct CComPropVariant *)&pvar,
              v59,
              a5);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
        goto LABEL_62;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56280500>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56280500>::GetImpl'::`2'::impl) )
      {
        if ( !v23 )
          goto LABEL_62;
      }
      else
      {
        CURL::ParseAccessType((struct CFilterSink *)((char *)a3 + 1072));
        if ( *((_WORD *)a3 + 756) )
          goto LABEL_62;
      }
      if ( v15 >= 0 )
      {
        v15 = ComputeSemanticPropertyChunk(
                v57,
                a3,
                (const struct _tagpropertykey *)&xmmword_140098560 + v34,
                (struct CComPropVariant *)&pvar);
LABEL_62:
        if ( v15 >= 0 )
          PluginSignalHelper::Ack((PluginSignalHelper *)v70);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x18DF,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
        (const char *)(unsigned int)v35,
        v47);
    }
    PropVariantClear((PROPVARIANT *)&pvar);
    ++v34;
    v23 = v49;
    if ( v34 >= 0xA )
      break;
  }
  v36 = v51;
  if ( v49 && v15 >= 0 )
    v15 = CreateAndIndexCombinedPathProperty(v57, a3, v50);
  PropVariantClear(v61);
  PluginSignalHelper::~PluginSignalHelper((PluginSignalHelper *)v70);
  TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&v50);
  v16 = v36 == 0;
LABEL_53:
  if ( !v16 )
    winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v51);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140014c94  mov     rax, rsp
0x140014c97  push    rbp
0x140014c98  push    rsi
0x140014c99  push    rdi
0x140014c9a  push    r12
0x140014c9c  push    r13
0x140014c9e  push    r14
0x140014ca0  push    r15
0x140014ca2  lea     rbp, [rsp-80h]
0x140014ca7  sub     rsp, 180h
0x140014cae  mov     [rbp+0B0h+var_100], 0FFFFFFFFFFFFFFFEh
0x140014cb6  mov     [rax+20h], rbx
0x140014cba  mov     rax, cs:__security_cookie
0x140014cc1  xor     rax, rsp
0x140014cc4  mov     [rbp+0B0h+var_40], rax
0x140014cc8  mov     [rbp+0B0h+var_128], r9
0x140014ccc  mov     r13, r8
0x140014ccf  mov     r14d, edx
0x140014cd2  mov     [rsp+1B0h+var_150], edx
0x140014cd6  mov     [rsp+1B0h+var_148], rcx
0x140014cdb  mov     r15, [rbp+0B0h+arg_28]
0x140014ce2  mov     [rsp+1B0h+var_140], r15
0x140014ce7  mov     rdi, [rbp+0B0h+arg_30]
0x140014cee  mov     r12, [rbp+0B0h+arg_38]
0x140014cf5  mov     [rsp+1B0h+var_138], r12
0x140014cfa  mov     rax, [rbp+0B0h+arg_50]
0x140014d01  mov     [rbp+0B0h+var_130], rax
0x140014d05  xor     ebx, ebx
0x140014d07  lea     rax, [rsp+1B0h+var_148]
0x140014d0c  mov     [rbp+0B0h+var_F8], rax
0x140014d10  mov     [rbp+0B0h+var_F0], 1
0x140014d14  mov     [rsp+1B0h+var_160], rbx
0x140014d19  lea     r8, [rsp+1B0h+var_160]; struct IFilterHost **
0x140014d1e  mov     rdx, rcx; wchar_t *
0x140014d21  mov     rcx, r12; struct CFilterThread *
0x140014d24  call    ?GetFilterHostWrapper@@YAJPEAVCFilterThread@@PEB_WPEAPEAUIFilterHost@@@Z; GetFilterHostWrapper(CFilterThread *,wchar_t const *,IFilterHost * *)
0x140014d29  mov     esi, eax
0x140014d2b  test    eax, eax
0x140014d2d  jns     short loc_140014D55
0x140014d2f  mov     rcx, [rbp+0B8h]; this
0x140014d36  mov     r9d, eax; char *
0x140014d39  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140014d40  mov     edx, 187Eh; void *
0x140014d45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014d4a  nop
0x140014d4b  cmp     [rsp+1B0h+var_160], rbx
0x140014d50  jmp     loc_1400151C4
0x140014d55  mov     [rsp+1B0h+var_168], rbx
0x140014d5a  mov     rbx, [rsp+1B0h+var_160]
0x140014d5f  test    r14d, r14d
0x140014d62  setz    dl; bool
0x140014d65  lea     rax, [rsp+1B0h+var_168]
0x140014d6a  mov     [rsp+1B0h+var_180], rax; void **
0x140014d6f  mov     [rsp+1B0h+var_190], rbx; int
0x140014d74  mov     r9, rdi; struct IBindCtx *
0x140014d77  mov     r8, r15; struct IUrlAccessor *
0x140014d7a  mov     rcx, [rsp+1B0h+var_148]; this
0x140014d7f  call    ?BindToPropertyHandler@@YAJPEB_W_NPEAUIUrlAccessor@@PEAUIBindCtx@@PEAUIFilterHost@@AEBU_GUID@@PEAPEAX@Z; BindToPropertyHandler(wchar_t const *,bool,IUrlAccessor *,IBindCtx *,IFilterHost *,_GUID const &,void * *)
0x140014d84  mov     esi, eax
0x140014d86  cmp     eax, 80004001h
0x140014d8b  jnz     short loc_140014D9F
0x140014d8d  lea     rcx, [rsp+1B0h+var_168]
0x140014d92  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x140014d97  nop
0x140014d98  xor     edi, edi
0x140014d9a  jmp     loc_14001559F
0x140014d9f  xor     r14d, r14d
0x140014da2  test    eax, eax
0x140014da4  js      short loc_140014DBA
0x140014da6  mov     r9, [rbp+0B0h+var_130]; struct IOpLockStatus *
0x140014daa  mov     edx, [rbp+0B0h+arg_40]; int
0x140014db0  mov     rcx, r12; struct CFilterThread *
0x140014db3  call    ?CheckIfShouldExit@@YAJPEAVCFilterThread@@HHPEAUIOpLockStatus@@@Z; CheckIfShouldExit(CFilterThread *,int,int,IOpLockStatus *)
0x140014db8  mov     esi, eax
0x140014dba  xorps   xmm0, xmm0
0x140014dbd  movups  [rbp+0B0h+var_A0], xmm0
0x140014dc1  mov     qword ptr [rbp+0B0h+Buf1], r14
0x140014dc5  test    rbx, rbx
0x140014dc8  jnz     short loc_140014DCF
0x140014dca  mov     rcx, r14
0x140014dcd  jmp     short loc_140014E16
0x140014dcf  mov     dword ptr [rbp+0B0h+pvar], 84Bh
0x140014dd6  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\cp"...
0x140014ddd  mov     [rbp+0B0h+pvar+8], rax
0x140014de1  mov     [rbp+0B0h+var_D8], r14
0x140014de5  mov     rax, [rbx]
0x140014de8  lea     r8, [rbp+0B0h+Buf1]
0x140014dec  lea     rdx, ??$guid_v@UIPersist@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IPersist>
0x140014df3  mov     rcx, rbx
0x140014df6  mov     rax, [rax]
0x140014df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014dfe  lea     r8, [rbp+0B0h+pvar]
0x140014e02  mov     edx, eax
0x140014e04  lea     rcx, [rsp+1B0h+var_158]
0x140014e09  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140014e0e  mov     rcx, qword ptr [rbp+0B0h+Buf1]
0x140014e12  mov     qword ptr [rbp+0B0h+Buf1], rcx
0x140014e16  mov     rax, [rcx]
0x140014e19  lea     rdx, [rbp+0B0h+var_A0]
0x140014e1d  mov     rax, [rax+18h]
0x140014e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e26  mov     edi, eax
0x140014e28  lea     rcx, [rbp+0B0h+Buf1]
0x140014e2c  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x140014e31  test    edi, edi
0x140014e33  jns     short loc_140014E55
0x140014e35  mov     rcx, [rbp+0B8h]; this
0x140014e3c  mov     r9d, edi; char *
0x140014e3f  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140014e46  mov     edx, 1892h; void *
0x140014e4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014e50  jmp     loc_140015594
0x140014e55  movaps  xmm0, [rbp+0B0h+var_A0]
0x140014e59  movdqa  [rbp+0B0h+Buf1], xmm0
0x140014e5e  mov     r9, [rsp+1B0h+var_148]; wchar_t *
0x140014e63  lea     r8, [rbp+0B0h+Buf1]; struct _GUID
0x140014e67  mov     rdx, [r12+178h]; struct IPluginResourceManager *
0x140014e6f  lea     rcx, [rbp+0B0h+var_90]; this
0x140014e73  call    ??0PluginSignalHelper@@QEAA@PEAUIPluginResourceManager@@U_GUID@@PEB_W@Z; PluginSignalHelper::PluginSignalHelper(IPluginResourceManager *,_GUID,wchar_t const *)
0x140014e78  nop
0x140014e79  mov     dl, 1; bool
0x140014e7b  lea     rcx, [rbp+0B0h+var_90]; this
0x140014e7f  call    ?Start@PluginSignalHelper@@QEAAX_N@Z; PluginSignalHelper::Start(bool)
0x140014e84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x140014e8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x140014e90  lea     r14, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140014e97  xor     edi, edi
0x140014e99  test    al, al
0x140014e9b  jz      loc_140014F7F
0x140014ea1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56143448@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56143448@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56143448> `wil::Feature<__WilFeatureTraits_Feature_56143448>::GetImpl(void)'::`2'::impl
0x140014ea8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56143448@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56143448>::__private_IsEnabled(void)
0x140014ead  test    al, al
0x140014eaf  jnz     loc_140014F7F
0x140014eb5  xorps   xmm0, xmm0
0x140014eb8  xor     eax, eax
0x140014eba  movups  xmmword ptr [rbp+0B0h+pvar], xmm0
0x140014ebe  mov     [rbp+0B0h+var_D8], rax
0x140014ec2  test    esi, esi
0x140014ec4  js      loc_140014F75
0x140014eca  mov     rcx, [rsp+1B0h+var_168]
0x140014ecf  test    rcx, rcx
0x140014ed2  jz      loc_140014F75
0x140014ed8  mov     rax, [rcx]
0x140014edb  lea     r8, [rbp+0B0h+pvar]
0x140014edf  lea     rdx, PKEY_FileExtension
0x140014ee6  mov     rax, [rax+28h]
0x140014eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014eef  mov     rcx, [rbp+0B8h]; this
0x140014ef6  test    eax, eax
0x140014ef8  jns     short loc_140014F0C
0x140014efa  mov     r9d, eax; char *
0x140014efd  mov     r8, r14; unsigned int
0x140014f00  mov     edx, 18A2h; void *
0x140014f05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140014f0a  jmp     short loc_140014F75
0x140014f0c  cmp     word ptr [rbp+0B0h+pvar], 1Fh
0x140014f11  jnz     short loc_140014F75
0x140014f13  mov     r15, [rbp+0B0h+pvar+8]
0x140014f17  test    r15, r15
0x140014f1a  jz      short loc_140014F70
0x140014f1c  mov     rcx, [rsp+1B0h+var_168]
0x140014f21  mov     rax, [rcx]
0x140014f24  lea     r8, [rbp+0B0h+pvar]
0x140014f28  lea     rdx, PKEY_Size
0x140014f2f  mov     rax, [rax+28h]
0x140014f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f38  mov     rcx, [rbp+0B8h]; this
0x140014f3f  test    eax, eax
0x140014f41  jns     short loc_140014F55
0x140014f43  mov     r9d, eax; char *
0x140014f46  mov     r8, r14; unsigned int
0x140014f49  mov     edx, 18A7h; void *
0x140014f4e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140014f53  jmp     short loc_140014F70
0x140014f55  mov     rdi, [rbp+0B0h+pvar+8]
0x140014f59  call    ?GetIsSemanticIndexingActive@@YAHXZ; GetIsSemanticIndexingActive(void)
0x140014f5e  test    eax, eax
0x140014f60  setnz   cl; bool
0x140014f63  mov     r8, rdi; unsigned __int64
0x140014f66  mov     rdx, r15; wchar_t *
0x140014f69  call    ?ReportExtensionUsage@SemanticSearchTelemetryAggregated@@SAX_NPEA_W_K@Z; SemanticSearchTelemetryAggregated::ReportExtensionUsage(bool,wchar_t *,unsigned __int64)
0x140014f6e  xor     edi, edi
0x140014f70  mov     r15, [rsp+1B0h+var_140]
0x140014f75  lea     rcx, [rbp+0B0h+pvar]; pvar
0x140014f79  call    cs:__imp_PropVariantClear
0x140014f7f  xorps   xmm0, xmm0
0x140014f82  xor     eax, eax
0x140014f84  movups  xmmword ptr [rbp+0B0h+var_118], xmm0
0x140014f88  mov     [rbp+0B0h+var_108], rax
0x140014f8c  test    esi, esi
0x140014f8e  js      loc_1400150AF
0x140014f94  mov     rcx, [rsp+1B0h+var_168]
0x140014f99  test    rcx, rcx
0x140014f9c  jz      loc_1400150AF
0x140014fa2  mov     rax, [rcx]
0x140014fa5  lea     r8, [rbp+0B0h+var_118]
0x140014fa9  lea     rdx, PKEY_FileExtension
0x140014fb0  mov     rax, [rax+28h]
0x140014fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014fb9  mov     rcx, [rbp+0B8h]; this
0x140014fc0  test    eax, eax
0x140014fc2  jns     short loc_140014FD9
0x140014fc4  mov     r9d, eax; char *
0x140014fc7  mov     r8, r14; unsigned int
0x140014fca  mov     edx, 18B4h; void *
0x140014fcf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140014fd4  jmp     loc_1400150AF
0x140014fd9  cmp     word ptr [rbp+0B0h+var_118], 1Fh
0x140014fde  jnz     loc_1400150AF
0x140014fe4  mov     rdx, [rbp+0B0h+var_118+8]
0x140014fe8  test    rdx, rdx
0x140014feb  jz      loc_1400150AF
0x140014ff1  lea     rcx, [rbp+0B0h+pvar]
0x140014ff5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140014ffa  nop
0x140014ffb  mov     rcx, [rsp+1B0h+var_168]
0x140015000  mov     rax, [rcx]
0x140015003  lea     r8, [rbp+0B0h+var_118]
0x140015007  lea     rdx, PKEY_Size
0x14001500e  mov     rax, [rax+28h]
0x140015012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015017  mov     rcx, [rbp+0B8h]; this
0x14001501e  test    eax, eax
0x140015020  jns     short loc_140015034
0x140015022  mov     r9d, eax; char *
0x140015025  mov     r8, r14; unsigned int
0x140015028  mov     edx, 18B9h; void *
0x14001502d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140015032  jmp     short loc_1400150A6
0x140015034  mov     rdi, [rbp+0B0h+var_118+8]
0x140015038  mov     rcx, [rsp+1B0h+var_168]
0x14001503d  mov     rax, [rcx]
0x140015040  lea     r8, [rbp+0B0h+var_118]
0x140015044  lea     rdx, PKEY_Media_Duration
0x14001504b  mov     rax, [rax+28h]
0x14001504f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015054  mov     rcx, [rbp+0B8h]; this
0x14001505b  xor     edx, edx
0x14001505d  test    eax, eax
0x14001505f  jns     short loc_140015073
0x140015061  mov     r9d, eax; char *
0x140015064  mov     r8, r14; unsigned int
0x140015067  mov     edx, 18BCh; void *
0x14001506c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140015071  jmp     short loc_1400150A4
0x140015073  cmp     word ptr [rbp+0B0h+var_118], dx
0x140015077  jz      short loc_1400150A4
0x140015079  mov     rax, 0E5109EC205D7BEA7h
0x140015083  mul     [rbp+0B0h+var_118+8]
0x140015087  mov     r8, rdx
0x14001508a  shr     r8, 1Dh; unsigned __int64
0x14001508e  lea     rdx, [rbp+0B0h+pvar]
0x140015092  cmp     [rbp+0B0h+var_D0], 7
0x140015097  cmova   rdx, [rbp+0B0h+pvar]; wchar_t *
0x14001509c  mov     rcx, rdi; unsigned __int64
0x14001509f  call    ?ReportExtensionUsageWithDuration@SearchIndexerTelemetryAggregated@@SAX_KPEA_W0@Z; SearchIndexerTelemetryAggregated::ReportExtensionUsageWithDuration(unsigned __int64,wchar_t *,unsigned __int64)
0x1400150a4  xor     edi, edi
0x1400150a6  lea     rcx, [rbp+0B0h+pvar]
0x1400150aa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400150af  mov     [rsp+1B0h+var_170], dil
0x1400150b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56280500@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56280500@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56280500> `wil::Feature<__WilFeatureTraits_Feature_56280500>::GetImpl(void)'::`2'::impl
0x1400150bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56280500@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56280500>::__private_IsEnabled(void)
0x1400150c0  test    al, al
0x1400150c2  jz      short loc_1400150ED
0x1400150c4  mov     rdx, [r13+450h]
0x1400150cb  lea     rcx, [rbp+0B0h+pvar]
0x1400150cf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400150d4  lea     rcx, [rbp+0B0h+pvar]
0x1400150d8  call    ?IsSemanticPropertyIndexingApplicableOnUrl@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; IsSemanticPropertyIndexingApplicableOnUrl(std::wstring const &)
0x1400150dd  mov     dil, al
0x1400150e0  mov     [rsp+1B0h+var_170], al
0x1400150e4  lea     rcx, [rbp+0B0h+pvar]
0x1400150e8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400150ed  test    dword ptr [r13+698h], 40000h
0x1400150f8  jz      loc_140015269
0x1400150fe  xor     r12d, r12d
0x140015101  mov     r15d, r12d
0x140015104  mov     rbx, [rbp+0B0h+arg_20]
0x14001510b  test    esi, esi
0x14001510d  js      short loc_14001517D
0x14001510f  xorps   xmm0, xmm0
0x140015112  xor     eax, eax
0x140015114  movups  xmmword ptr [rbp+0B0h+pvar], xmm0
0x140015118  mov     [rbp+0B0h+var_D8], rax
0x14001511c  mov     rcx, [rsp+1B0h+var_168]
0x140015121  lea     rax, [r15+r15*4]
0x140015125  lea     rdx, xmmword_140098560
0x14001512c  lea     r12, [rdx+rax*4]
0x140015130  mov     rax, [rcx]
0x140015133  lea     r8, [rbp+0B0h+pvar]
0x140015137  mov     rdx, r12
0x14001513a  mov     rax, [rax+28h]
0x14001513e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015143  mov     rcx, [rbp+0B8h]; this
0x14001514a  test    eax, eax
0x14001514c  jns     loc_1400151D9
0x140015152  mov     r9d, eax; char *
0x140015155  mov     r8, r14; unsigned int
0x140015158  mov     edx, 18DFh; void *
0x14001515d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
  ... truncated ...
```
