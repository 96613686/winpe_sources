# CreateAndIndexCombinedPathProperty(CFilterThread *,CFilterSink &,IPropertyStore *)

- ea: `0x1400133e0`
- end: `0x140013d0a`
- name: `?CreateAndIndexCombinedPathProperty@@YAJPEAVCFilterThread@@AEAVCFilterSink@@PEAUIPropertyStore@@@Z`
- size: `2346`
- prototype: `__int64 __fastcall(struct CFilterThread *, struct CFilterSink *, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `29`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140014c94`

## callees

- `0x140005240`
- `0x1400072f4`
- `0x140007330`
- `0x140009cf0`
- `0x14000a108`
- `0x14000a148`
- `0x14000cce4`
- `0x14000cd28`
- `0x14000d110`
- `0x14000dcb8`
- `0x14000eef0`
- `0x14000f1e0`
- `0x14001030c`
- `0x1400105c0`
- `0x1400133e0`
- `0x14001a024`
- `0x14001d53c`
- `0x140025994`
- `0x14003221c`
- `0x140032f70`
- `0x14003357c`
- `0x140033634`
- `0x14003376c`
- `0x140034008`
- `0x140034044`
- `0x14003c300`
- `0x140052308`
- `0x140064198`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013814`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013820`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14001382f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013bc1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013bcd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013bdc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013c51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013c5d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013c6c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013cbd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013cc9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013cd8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013814`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013820`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14001382f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013bc1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013bcd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013bdc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013c51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013c5d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013c6c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013cbd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013cc9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140013cd8`

## string_xrefs

- `0x14001359d`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`
- `0x140013647`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`
- `0x1400137f1`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`
- `0x140013a7a`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`
- `0x140013591`: `Folder path identified as non-semantic content: %ls\n`
- `0x1400137e5`: `Combined path property embedding generation skipped due to non-semantic content\n`
- `0x140013a6e`: `Combined path property processed\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CreateAndIndexCombinedPathProperty(
        struct CFilterThread *a1,
        struct CFilterSink *a2,
        struct IPropertyStore *a3)
{
  CFilterSink *v4; // r13
  bool v5; // si
  char v6; // r15
  char v7; // r12
  __int64 NonSemanticTextDetector; // rax
  __int64 v9; // r13
  __int64 v10; // rax
  __int64 v11; // r12
  char v12; // r15
  __int64 v13; // rax
  const wchar_t *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  const wchar_t *v17; // r9
  __int64 CodePointCount; // rdi
  __int64 v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  __int64 result; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rax
  int v27; // esi
  unsigned __int64 v28; // rcx
  _QWORD *v29; // rdi
  _QWORD *v30; // r12
  __int64 (__fastcall *v31)(__int64, __int64 *, __int128 *); // r9
  __int64 v32; // r10
  _BYTE *v33; // r15
  const char *v34; // r9
  __int64 v35; // rdx
  char v36; // [rsp+20h] [rbp-188h]
  char IsNonSemantic; // [rsp+21h] [rbp-187h]
  __int128 v38; // [rsp+30h] [rbp-178h] BYREF
  __int128 v39; // [rsp+40h] [rbp-168h] BYREF
  __int64 v40; // [rsp+50h] [rbp-158h]
  PROPVARIANT v41; // [rsp+58h] [rbp-150h] BYREF
  PROPVARIANT v42[2]; // [rsp+60h] [rbp-148h] BYREF
  PROPVARIANT v43[2]; // [rsp+70h] [rbp-138h] BYREF
  __int64 v44; // [rsp+80h] [rbp-128h]
  PROPVARIANT v45[2]; // [rsp+88h] [rbp-120h] BYREF
  __int64 v46; // [rsp+98h] [rbp-110h]
  _BYTE v47[8]; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-100h]
  __int64 v49; // [rsp+B0h] [rbp-F8h]
  __int64 v50; // [rsp+B8h] [rbp-F0h]
  __int64 v51; // [rsp+C0h] [rbp-E8h]
  PROPVARIANT pvar[2]; // [rsp+C8h] [rbp-E0h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-D0h]
  struct CFilterThread *v54; // [rsp+E0h] [rbp-C8h]
  _QWORD v55[3]; // [rsp+E8h] [rbp-C0h] BYREF
  _BYTE Src[16]; // [rsp+100h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+110h] [rbp-98h]
  FULLPROPSPEC v58; // [rsp+120h] [rbp-88h] BYREF
  __int64 v59[5]; // [rsp+140h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v55[2] = -2;
  try
  {
    v4 = a2;
    v55[0] = a2;
    v54 = a1;
    *(_OWORD *)v45 = 0;
    v46 = 0;
    *(_OWORD *)v43 = 0;
    v44 = 0;
    *(_OWORD *)pvar = 0;
    v53 = 0;
    v5 = ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a3->lpVtbl->GetValue)(
           a3,
           &PKEY_ItemFolderNameDisplay,
           v45) >= 0
      && LOWORD(v45[0]) == 31
      && v45[1];
    if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a3->lpVtbl->GetValue)(
           a3,
           &PKEY_ItemNameDisplayWithoutExtension,
           v43) < 0
      || LOWORD(v43[0]) != 31
      || (v6 = 1, !v43[1]) )
    {
      v6 = 0;
    }
    if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a3->lpVtbl->GetValue)(
           a3,
           &PKEY_ItemType,
           pvar) < 0
      || LOWORD(pvar[0]) != 31
      || (v7 = 1, !pvar[1]) )
    {
      v7 = 0;
    }
    v36 = v7;
    std::wstring::wstring(Src);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60480854>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60480854>::GetImpl'::`2'::impl) )
    {
      NonSemanticTextDetector = GetNonSemanticTextDetector();
      v42[0] = (PROPVARIANT)NonSemanticTextDetector;
      if ( v5 )
      {
        v41 = v45[1];
        v9 = -1;
        do
          ++v9;
        while ( *((_WORD *)v45[1] + v9) );
        *(PROPVARIANT *)&v38 = v45[1];
        *((_QWORD *)&v38 + 1) = v9;
        IsNonSemantic = NonSemanticTextDetector::IsNonSemantic(NonSemanticTextDetector, &v38);
        if ( IsNonSemantic )
        {
          SearchIndexerDebug::Verbose(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrdaemon.cxx\"",
            (const wchar_t *)0x1740,
            (unsigned int)L"Folder path identified as non-semantic content: %ls\n",
            (const wchar_t *)v45[1]);
        }
        else
        {
          v10 = std::wstring::wstring(v59, v45[1]);
          std::wstring::operator=(Src, v10);
          std::wstring::_Tidy_deallocate(v59);
        }
        NonSemanticTextDetector = (__int64)v42[0];
      }
      else
      {
        v41 = 0;
        IsNonSemantic = 0;
        v9 = 0;
      }
      v42[0] = 0;
      v11 = 0;
      if ( v6 )
      {
        v42[0] = v43[1];
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)v43[1] + v11) );
        *(PROPVARIANT *)&v38 = v43[1];
        *((_QWORD *)&v38 + 1) = v11;
        v12 = NonSemanticTextDetector::IsNonSemantic(NonSemanticTextDetector, &v38);
        if ( v12 )
        {
          SearchIndexerDebug::Verbose(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrdaemon.cxx\"",
            (const wchar_t *)0x174F,
            (unsigned int)L"File name identified as non-semantic content: %ls\n",
            (const wchar_t *)v43[1]);
        }
        else
        {
          v13 = std::wstring::wstring(&v58, v43[1]);
          v14 = &dword_14007696C;
          if ( v57 )
            v14 = L" ";
          std::operator+<wchar_t>(v59, v14, v13);
          std::wstring::_Append<wchar_t>(Src);
          std::wstring::_Tidy_deallocate(v59);
          std::wstring::_Tidy_deallocate(&v58);
        }
      }
      else
      {
        v12 = 0;
      }
      if ( v57 && v36 && *(_WORD *)pvar[1] )
      {
        v15 = std::wstring::wstring(&v58, (char *)pvar[1] + 2);
        std::operator+<wchar_t>(v59, L" ", v15);
        std::wstring::_Append<wchar_t>(Src);
        std::wstring::_Tidy_deallocate(v59);
        std::wstring::_Tidy_deallocate(&v58);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60581610>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60581610>::GetImpl'::`2'::impl) )
      {
        if ( IsNonSemantic )
        {
          *(_QWORD *)&v38 = v41;
          *((_QWORD *)&v38 + 1) = v9;
          CodePointCount = NonSemanticTextDetector::GetCodePointCount(&v38);
        }
        else
        {
          CodePointCount = 0;
        }
        if ( v12 )
        {
          *(PROPVARIANT *)&v38 = v42[0];
          *((_QWORD *)&v38 + 1) = v11;
          v19 = NonSemanticTextDetector::GetCodePointCount(&v38);
        }
        else
        {
          v19 = 0;
        }
        if ( !IsNonSemantic || (LOBYTE(v16) = 1, !v12) )
          LOBYTE(v16) = 0;
        SearchIndexerTelemetryAggregatedHigh::ReportNonSemanticTextDetection(v16, v19 + CodePointCount, 1);
      }
      if ( !v57 )
      {
        SearchIndexerDebug::Verbose(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrdaemon.cxx\"",
          (const wchar_t *)0x176E,
          (unsigned int)L"Combined path property embedding generation skipped due to non-semantic content\n",
          v17);
        std::wstring::_Tidy_deallocate(Src);
        PropVariantClear(pvar);
        PropVariantClear(v43);
        PropVariantClear(v45);
        return 0;
      }
      v4 = (CFilterSink *)v55[0];
    }
    else
    {
      if ( v5 )
      {
        v23 = std::wstring::wstring(&v58, v45[1]);
        v24 = std::operator+<wchar_t>(v59, v23, L" ");
        std::wstring::operator=(Src, v24);
        std::wstring::_Tidy_deallocate(v59);
        std::wstring::_Tidy_deallocate(&v58);
      }
      if ( v6 )
      {
        v25 = -1;
        do
          ++v25;
        while ( *((_WORD *)v43[1] + v25) );
        std::wstring::_Append<wchar_t>(Src);
      }
      if ( v7 && *(_WORD *)pvar[1] )
      {
        v26 = std::wstring::wstring(&v58, (char *)pvar[1] + 2);
        std::operator+<wchar_t>(v59, L" ", v26);
        std::wstring::_Append<wchar_t>(Src);
        std::wstring::_Tidy_deallocate(v59);
        std::wstring::_Tidy_deallocate(&v58);
      }
    }
    v27 = 0;
    *(_QWORD *)&v58.psProperty.ulKind = 1;
    v58.guidPropSet = PKEY_ItemNameDisplay.fmtid;
    v58.psProperty.propid = (PROPID)PKEY_ItemNameDisplay.pid;
    filter_pipeline::text_providers(*((_QWORD *)v54 + 48), &v39);
    __SET_PAIR__((unsigned __int64)v30, v28, v39);
    v29 = (_QWORD *)v39;
LABEL_61:
    if ( v29 == v30 )
    {
      if ( v28 )
      {
        ((void (*)(void))std::_Destroy_range<std::allocator<std::shared_ptr<text_filter_semantic_provider>>>)();
        std::_Deallocate<16>(v39, (v40 - v39) & 0xFFFFFFFFFFFFFFF0uLL);
        v39 = 0;
        v40 = 0;
      }
    }
    else
    {
      std::queue<embedding>::queue<embedding,std::deque<embedding>>(v47);
      try
      {
        (*(void (__fastcall **)(_QWORD, PROPVARIANT *))(*(_QWORD *)*v29 + 8LL))(*v29, &v41);
        v38 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v55);
        v33 = (_BYTE *)v31(v32, v59, &v38);
        if ( v47 != v33 )
        {
          std::deque<embedding>::_Tidy(v47);
          std::deque<embedding>::_Take_contents(v47, v33);
        }
        std::deque<embedding>::~deque<embedding>(v59);
        std::unique_ptr<single_sentence_embedding_provider>::~unique_ptr<single_sentence_embedding_provider>(&v41);
      }
      catch ( ... )
      {
        v35 = (unsigned int)wil::details::in1diag3::Log_CaughtException(
                              retaddr,
                              (void *)0x179C,
                              (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
                              v34);
        SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(2, v35);
        std::deque<embedding>::~deque<embedding>(v47);
        if ( (_QWORD)v39 )
        {
          std::_Destroy_range<std::allocator<std::shared_ptr<text_filter_semantic_provider>>>(
            v39,
            *((_QWORD *)&v39 + 1));
          std::_Deallocate<16>(v39, (v40 - v39) & 0xFFFFFFFFFFFFFFF0uLL);
          v39 = 0;
          v40 = 0;
        }
        std::wstring::_Tidy_deallocate(Src);
        PropVariantClear(pvar);
        PropVariantClear(v43);
        PropVariantClear(v45);
        return 2147750438LL;
      }
      while ( 1 )
      {
        if ( !v51 )
        {
          ++g_numberOfSpeciallyIndexedProperties;
          SearchIndexerDebug::Verbose(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrdaemon.cxx\"",
            (const wchar_t *)0x17B1,
            (unsigned int)L"Combined path property processed\n",
            (const wchar_t *)v34);
          std::deque<embedding>::~deque<embedding>(v47);
          v29 += 2;
          v28 = v39;
          goto LABEL_61;
        }
        embedding::embedding((embedding *)v59, *(const struct embedding **)(v48 + 8 * (v50 & (v49 - 1))));
        std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy(*(_QWORD *)(v48
                                                                                               + 8 * (v50 & (v49 - 1))));
        if ( --v51 )
          ++v50;
        else
          v50 = 0;
        v38 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, PROPVARIANT *))(*(_QWORD *)*v29 + 24LL))(*v29, v42);
        v27 = CFilterSink::AddEmbedding(v4, &v58, &v38, v59);
        if ( v27 < 0 )
          break;
        std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy(v59);
      }
      std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy(v59);
      std::deque<embedding>::~deque<embedding>(v47);
      if ( (_QWORD)v39 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<text_filter_semantic_provider>>>(v39, *((_QWORD *)&v39 + 1));
        std::_Deallocate<16>(v39, (v40 - v39) & 0xFFFFFFFFFFFFFFF0uLL);
        v39 = 0;
        v40 = 0;
      }
    }
    std::wstring::_Tidy_deallocate(Src);
    PropVariantClear(pvar);
    PropVariantClear(v43);
    PropVariantClear(v45);
    result = (unsigned int)v27;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x17B7, v20, v21);
  }
  return result;
}

```

## disassembly

```asm
0x1400133e0  mov     r11, rsp
0x1400133e3  push    rbx
0x1400133e4  push    rsi
0x1400133e5  push    rdi
0x1400133e6  push    r12
0x1400133e8  push    r13
0x1400133ea  push    r14
0x1400133ec  push    r15
0x1400133ee  sub     rsp, 170h
0x1400133f5  mov     qword ptr [r11-0B0h], 0FFFFFFFFFFFFFFFEh
0x140013400  mov     rax, cs:__security_cookie
0x140013407  xor     rax, rsp
0x14001340a  mov     [rsp+1A8h+var_40], rax
0x140013412  mov     rdi, r8
0x140013415  mov     r13, rdx
0x140013418  mov     [rsp+1A8h+var_C0], rdx
0x140013420  mov     [rsp+1A8h+var_C8], rcx
0x140013428  xorps   xmm0, xmm0
0x14001342b  xor     eax, eax
0x14001342d  movups  xmmword ptr [rsp+1A8h+var_120], xmm0
0x140013435  mov     [r11-110h], rax
0x14001343c  movups  xmmword ptr [rsp+1A8h+var_138], xmm0
0x140013441  mov     [r11-128h], rax
0x140013448  movups  xmmword ptr [rsp+1A8h+pvar], xmm0
0x140013450  mov     [r11-0D0h], rax
0x140013457  mov     rax, [r8]
0x14001345a  lea     r8, [r11-120h]
0x140013461  lea     rdx, PKEY_ItemFolderNameDisplay
0x140013468  mov     rcx, rdi
0x14001346b  mov     rax, [rax+28h]
0x14001346f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013474  xor     ebx, ebx
0x140013476  test    eax, eax
0x140013478  js      short loc_140013498
0x14001347a  cmp     word ptr [rsp+1A8h+var_120], 1Fh
0x140013483  jnz     short loc_140013498
0x140013485  cmp     [rsp+1A8h+var_120+8], rbx
0x14001348d  jz      short loc_140013498
0x14001348f  lea     r14d, [rbx+1]
0x140013493  mov     sil, r14b
0x140013496  jmp     short loc_1400134A1
0x140013498  mov     sil, bl
0x14001349b  mov     r14d, 1
0x1400134a1  mov     rax, [rdi]
0x1400134a4  lea     r8, [rsp+1A8h+var_138]
0x1400134a9  lea     rdx, PKEY_ItemNameDisplayWithoutExtension
0x1400134b0  mov     rcx, rdi
0x1400134b3  mov     rax, [rax+28h]
0x1400134b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400134bc  test    eax, eax
0x1400134be  js      short loc_1400134D2
0x1400134c0  cmp     word ptr [rsp+1A8h+var_138], 1Fh
0x1400134c6  jnz     short loc_1400134D2
0x1400134c8  cmp     [rsp+1A8h+var_138+8], rbx
0x1400134cd  mov     r15b, r14b
0x1400134d0  jnz     short loc_1400134D5
0x1400134d2  mov     r15b, bl
0x1400134d5  mov     rax, [rdi]
0x1400134d8  lea     r8, [rsp+1A8h+pvar]
0x1400134e0  lea     rdx, PKEY_ItemType
0x1400134e7  mov     rcx, rdi
0x1400134ea  mov     rax, [rax+28h]
0x1400134ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400134f3  test    eax, eax
0x1400134f5  js      short loc_14001350F
0x1400134f7  cmp     word ptr [rsp+1A8h+pvar], 1Fh
0x140013500  jnz     short loc_14001350F
0x140013502  cmp     [rsp+1A8h+pvar+8], rbx
0x14001350a  mov     r12b, r14b
0x14001350d  jnz     short loc_140013512
0x14001350f  mov     r12b, bl
0x140013512  mov     [rsp+1A8h+var_188], r12b
0x140013517  lea     rcx, [rsp+1A8h+Src]
0x14001351f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140013524  nop
0x140013525  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60480854@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60480854@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60480854> `wil::Feature<__WilFeatureTraits_Feature_60480854>::GetImpl(void)'::`2'::impl
0x14001352c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60480854@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60480854>::__private_IsEnabled(void)
0x140013531  test    al, al
0x140013533  jz      loc_14001383C
0x140013539  call    GetNonSemanticTextDetector
0x14001353e  mov     [rsp+1A8h+var_148], rax
0x140013543  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140013547  test    sil, sil
0x14001354a  jz      loc_1400135E4
0x140013550  mov     rcx, [rsp+1A8h+var_120+8]
0x140013558  mov     [rsp+1A8h+var_150], rcx
0x14001355d  mov     r13, rdi
0x140013560  inc     r13
0x140013563  cmp     [rcx+r13*2], bx
0x140013568  jnz     short loc_140013560
0x14001356a  mov     qword ptr [rsp+1A8h+var_178], rcx
0x14001356f  mov     qword ptr [rsp+1A8h+var_178+8], r13
0x140013574  lea     rdx, [rsp+1A8h+var_178]
0x140013579  mov     rcx, rax
0x14001357c  call    ?IsNonSemantic@NonSemanticTextDetector@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; NonSemanticTextDetector::IsNonSemantic(std::wstring_view)
0x140013581  mov     [rsp+1A8h+var_187], al
0x140013585  test    al, al
0x140013587  jz      short loc_1400135B0
0x140013589  mov     r9, [rsp+1A8h+var_120+8]; wchar_t *
0x140013591  lea     r8, aFolderPathIden; "Folder path identified as non-semantic "...
0x140013598  mov     edx, 1740h; wchar_t *
0x14001359d  lea     rcx, aOnecoreuapBase_54; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1400135a4  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1400135a9  mov     rax, [rsp+1A8h+var_148]
0x1400135ae  jmp     short loc_1400135F0
0x1400135b0  mov     rdx, [rsp+1A8h+var_120+8]
0x1400135b8  lea     rcx, [rsp+1A8h+var_68]
0x1400135c0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400135c5  mov     rdx, rax
0x1400135c8  lea     rcx, [rsp+1A8h+Src]
0x1400135d0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400135d5  lea     rcx, [rsp+1A8h+var_68]
0x1400135dd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400135e2  jmp     short loc_1400135A9
0x1400135e4  mov     [rsp+1A8h+var_150], rbx
0x1400135e9  mov     [rsp+1A8h+var_187], bl
0x1400135ed  mov     r13, rbx
0x1400135f0  mov     [rsp+1A8h+var_148], rbx
0x1400135f5  mov     r12, rbx
0x1400135f8  test    r15b, r15b
0x1400135fb  jz      loc_1400136D7
0x140013601  mov     rcx, [rsp+1A8h+var_138+8]
0x140013606  mov     [rsp+1A8h+var_148], rcx
0x14001360b  mov     r12, rdi
0x14001360e  inc     r12
0x140013611  cmp     [rcx+r12*2], bx
0x140013616  jnz     short loc_14001360E
0x140013618  mov     qword ptr [rsp+1A8h+var_178], rcx
0x14001361d  mov     qword ptr [rsp+1A8h+var_178+8], r12
0x140013622  lea     rdx, [rsp+1A8h+var_178]
0x140013627  mov     rcx, rax
0x14001362a  call    ?IsNonSemantic@NonSemanticTextDetector@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; NonSemanticTextDetector::IsNonSemantic(std::wstring_view)
0x14001362f  mov     r15b, al
0x140013632  test    al, al
0x140013634  jz      short loc_140013658
0x140013636  mov     r9, [rsp+1A8h+var_138+8]; wchar_t *
0x14001363b  lea     r8, aFileNameIdenti; "File name identified as non-semantic co"...
0x140013642  mov     edx, 174Fh; wchar_t *
0x140013647  lea     rcx, aOnecoreuapBase_54; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14001364e  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x140013653  jmp     loc_1400136DA
0x140013658  mov     rdx, [rsp+1A8h+var_138+8]
0x14001365d  lea     rcx, [rsp+1A8h+var_88]
0x140013665  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001366a  nop
0x14001366b  cmp     [rsp+1A8h+var_98], rbx
0x140013673  setz    cl
0x140013676  lea     rsi, asc_140079628; " "
0x14001367d  lea     rdx, dword_14007696C
0x140013684  test    cl, cl
0x140013686  cmovz   rdx, rsi
0x14001368a  mov     r8, rax
0x14001368d  lea     rcx, [rsp+1A8h+var_68]
0x140013695  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x14001369a  nop
0x14001369b  mov     r8, [rax+10h]
0x14001369f  cmp     qword ptr [rax+18h], 7
0x1400136a4  jbe     short loc_1400136A9
0x1400136a6  mov     rax, [rax]
0x1400136a9  mov     rdx, rax
0x1400136ac  lea     rcx, [rsp+1A8h+Src]; Src
0x1400136b4  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1400136b9  nop
0x1400136ba  lea     rcx, [rsp+1A8h+var_68]
0x1400136c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400136c7  nop
0x1400136c8  lea     rcx, [rsp+1A8h+var_88]
0x1400136d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400136d5  jmp     short loc_1400136E1
0x1400136d7  mov     r15b, bl
0x1400136da  lea     rsi, asc_140079628; " "
0x1400136e1  cmp     [rsp+1A8h+var_98], rbx
0x1400136e9  jz      short loc_14001375E
0x1400136eb  cmp     [rsp+1A8h+var_188], bl
0x1400136ef  jz      short loc_14001375E
0x1400136f1  mov     rdx, [rsp+1A8h+pvar+8]
0x1400136f9  cmp     [rdx], bx
0x1400136fc  jz      short loc_14001375E
0x1400136fe  add     rdx, 2
0x140013702  lea     rcx, [rsp+1A8h+var_88]
0x14001370a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001370f  nop
0x140013710  mov     r8, rax
0x140013713  mov     rdx, rsi
0x140013716  lea     rcx, [rsp+1A8h+var_68]
0x14001371e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x140013723  nop
0x140013724  mov     r8, [rax+10h]
0x140013728  cmp     qword ptr [rax+18h], 7
0x14001372d  jbe     short loc_140013732
0x14001372f  mov     rax, [rax]
0x140013732  mov     rdx, rax
0x140013735  lea     rcx, [rsp+1A8h+Src]; Src
0x14001373d  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140013742  nop
0x140013743  lea     rcx, [rsp+1A8h+var_68]
0x14001374b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140013750  nop
0x140013751  lea     rcx, [rsp+1A8h+var_88]
0x140013759  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001375e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60581610@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60581610@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60581610> `wil::Feature<__WilFeatureTraits_Feature_60581610>::GetImpl(void)'::`2'::impl
0x140013765  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60581610@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60581610>::__private_IsEnabled(void)
0x14001376a  test    al, al
0x14001376c  jz      short loc_1400137D7
0x14001376e  mov     sil, [rsp+1A8h+var_187]
0x140013773  test    sil, sil
0x140013776  jz      short loc_140013796
0x140013778  mov     rax, [rsp+1A8h+var_150]
0x14001377d  mov     qword ptr [rsp+1A8h+var_178], rax
0x140013782  mov     qword ptr [rsp+1A8h+var_178+8], r13
0x140013787  lea     rcx, [rsp+1A8h+var_178]
0x14001378c  call    ?GetCodePointCount@NonSemanticTextDetector@@SA_KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; NonSemanticTextDetector::GetCodePointCount(std::wstring_view)
0x140013791  mov     rdi, rax
0x140013794  jmp     short loc_140013799
0x140013796  mov     rdi, rbx
0x140013799  test    r15b, r15b
0x14001379c  jz      short loc_1400137B9
0x14001379e  mov     rax, [rsp+1A8h+var_148]
0x1400137a3  mov     qword ptr [rsp+1A8h+var_178], rax
0x1400137a8  mov     qword ptr [rsp+1A8h+var_178+8], r12
0x1400137ad  lea     rcx, [rsp+1A8h+var_178]
0x1400137b2  call    ?GetCodePointCount@NonSemanticTextDetector@@SA_KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; NonSemanticTextDetector::GetCodePointCount(std::wstring_view)
0x1400137b7  jmp     short loc_1400137BC
0x1400137b9  mov     rax, rbx
0x1400137bc  test    sil, sil
0x1400137bf  jz      short loc_1400137C9
0x1400137c1  test    r15b, r15b
0x1400137c4  mov     cl, r14b
0x1400137c7  jnz     short loc_1400137CB
0x1400137c9  mov     cl, bl
0x1400137cb  lea     rdx, [rax+rdi]
0x1400137cf  mov     r8d, r14d
0x1400137d2  call    ?ReportNonSemanticTextDetection@SearchIndexerTelemetryAggregatedHigh@@SAX_N_KW4NonSemanticTextDetectionContext@@@Z; SearchIndexerTelemetryAggregatedHigh::ReportNonSemanticTextDetection(bool,unsigned __int64,NonSemanticTextDetectionContext)
0x1400137d7  cmp     [rsp+1A8h+var_98], rbx
0x1400137df  jnz     loc_140013940
0x1400137e5  lea     r8, aCombinedPathPr_0; "Combined path property embedding genera"...
0x1400137ec  mov     edx, 176Eh; wchar_t *
0x1400137f1  lea     rcx, aOnecoreuapBase_54; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1400137f8  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1400137fd  nop
0x1400137fe  lea     rcx, [rsp+1A8h+Src]
0x140013806  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001380b  nop
0x14001380c  lea     rcx, [rsp+1A8h+pvar]; pvar
0x140013814  call    cs:__imp_PropVariantClear
0x14001381a  nop
0x14001381b  lea     rcx, [rsp+1A8h+var_138]; pvar
0x140013820  call    cs:__imp_PropVariantClear
0x140013826  nop
0x140013827  lea     rcx, [rsp+1A8h+var_120]; pvar
0x14001382f  call    cs:__imp_PropVariantClear
0x140013835  xor     eax, eax
0x140013837  jmp     loc_140013CE6
0x14001383c  test    sil, sil
0x14001383f  jz      short loc_14001389E
0x140013841  mov     rdx, [rsp+1A8h+var_120+8]
0x140013849  lea     rcx, [rsp+1A8h+var_88]
0x140013851  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140013856  nop
0x140013857  lea     rsi, asc_140079628; " "
0x14001385e  mov     r8, rsi
0x140013861  mov     rdx, rax
0x140013864  lea     rcx, [rsp+1A8h+var_68]
0x14001386c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x140013871  mov     rdx, rax
0x140013874  lea     rcx, [rsp+1A8h+Src]
0x14001387c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140013881  lea     rcx, [rsp+1A8h+var_68]
0x140013889  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001388e  nop
0x14001388f  lea     rcx, [rsp+1A8h+var_88]
0x140013897  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001389c  jmp     short loc_1400138A5
0x14001389e  lea     rsi, asc_140079628; " "
0x1400138a5  test    r15b, r15b
0x1400138a8  jz      short loc_1400138CC
0x1400138aa  mov     rdx, [rsp+1A8h+var_138+8]
0x1400138af  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400138b3  inc     rdi
0x1400138b6  cmp     [rdx+rdi*2], bx
0x1400138ba  jnz     short loc_1400138B3
0x1400138bc  mov     r8, rdi
0x1400138bf  lea     rcx, [rsp+1A8h+Src]; Src
0x1400138c7  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1400138cc  test    r12b, r12b
0x1400138cf  jz      short loc_140013948
0x1400138d1  mov     rdx, [rsp+1A8h+pvar+8]
0x1400138d9  cmp     [rdx], bx
0x1400138dc  jz      short loc_140013948
0x1400138de  add     rdx, 2
0x1400138e2  lea     rcx, [rsp+1A8h+var_88]
0x1400138ea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400138ef  nop
0x1400138f0  mov     r8, rax
0x1400138f3  mov     rdx, rsi
0x1400138f6  lea     rcx, [rsp+1A8h+var_68]
0x1400138fe  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x140013903  nop
0x140013904  mov     r8, [rax+10h]
0x140013908  cmp     qword ptr [rax+18h], 7
  ... truncated ...
```
