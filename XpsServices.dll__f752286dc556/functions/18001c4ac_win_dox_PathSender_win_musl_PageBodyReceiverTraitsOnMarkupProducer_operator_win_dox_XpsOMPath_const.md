# win_dox::PathSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::operator()(win_dox::XpsOMPath const &)

- ea: `0x18001c4ac`
- end: `0x18001d70c`
- name: `??R?$PathSender@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@win_dox@@QEAAXAEBVXpsOMPath@1@@Z`
- size: `4704`
- prototype: ``
- caller_count: `1`
- callee_count: `75`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004eec0`

## callees

- `0x180005664`
- `0x18000c368`
- `0x18000c480`
- `0x18000cb80`
- `0x180012450`
- `0x180019170`
- `0x18001be18`
- `0x18001befc`
- `0x18001bfbc`
- `0x18001c094`
- `0x18001c278`
- `0x18001c348`
- `0x18001c4ac`
- `0x18001d714`
- `0x18001d740`
- `0x18001dacc`
- `0x18001db88`
- `0x18001dbdc`
- `0x18001dc2c`
- `0x18001dd14`
- `0x18001ddec`
- `0x18001de3c`
- `0x18001df14`
- `0x18001df74`
- `0x18001dfc4`
- `0x18001e024`
- `0x18001e184`
- `0x18001e25c`
- `0x18001e2ac`
- `0x18001e300`
- `0x18001e354`
- `0x18001e3a4`
- `0x18001e3f4`
- `0x18001e6c0`
- `0x18001eb7c`
- `0x18002073c`
- `0x18002dbe0`
- `0x180081c74`
- `0x180081cc0`
- `0x180082020`
- `0x180082090`
- `0x180082614`
- `0x180094378`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c1178`
- `0x1800c12a8`
- `0x1800c1454`
- `0x1800c20c4`
- `0x1800c23cc`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ccf1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ceff`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ccf1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ceff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c7bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ca8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cadf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ce72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ceb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c7bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ca8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cadf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ce72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ceb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
void __fastcall win_dox::PathSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::operator()(
        __int64 a1,
        win_dox::XpsOMVisual *a2)
{
  __int64 v4; // rbx
  __int64 StrokeDashes; // rax
  __int64 v6; // rbx
  __int64 v7; // rdx
  char v8; // r15
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rdi
  void *v18; // rbx
  __int64 HyperlinkNavigateUri; // rax
  int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rsi
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rsi
  __m128i v26; // xmm6
  __int64 v27; // rsi
  __int128 *v28; // rdi
  __int8 v29; // si
  win_musl::PathMarkupProducer *v30; // r14
  __int64 v31; // rdx
  __int64 v32; // rdi
  __int64 v33; // r8
  char v34; // al
  __int64 v35; // rdi
  win_musl::PathMarkupProducer *v36; // r14
  __int64 v37; // rsi
  _QWORD *Language; // rax
  __int64 v39; // rsi
  __int64 v40; // rdx
  __int64 v41; // rdx
  _QWORD **Interface; // rax
  void (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // rsi
  void (__fastcall **v44)(_QWORD, GUID *, __int64 *); // r14
  __int64 v45; // rcx
  _QWORD **v46; // rax
  void (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // rsi
  void (__fastcall **v48)(_QWORD, GUID *, __int64 *); // r14
  __int64 v49; // rcx
  unsigned int v50; // eax
  int v51; // edx
  const char *v52; // r8
  unsigned int v53; // r9d
  char v54; // al
  char v55; // cl
  int v56; // eax
  int v57; // edx
  const char *v58; // r8
  unsigned int v59; // r9d
  char v60; // al
  char v61; // cl
  struct win_dox::XpsOMBrush *v62; // rcx
  __int64 StaticResource; // rsi
  __int64 v64; // rsi
  __int64 v65; // rax
  _QWORD *AbsoluteUri; // rax
  win_musl::Formatter *v67; // rax
  const wchar_t *v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rdi
  float Opacity; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v72; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-B0h] BYREF
  struct win_dox::XpsOMBrush *v74; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v75; // [rsp+68h] [rbp-A0h] BYREF
  __m128i v76; // [rsp+78h] [rbp-90h] BYREF
  win_musl::PathMarkupProducer *v77; // [rsp+88h] [rbp-80h] BYREF
  __int128 *v78; // [rsp+90h] [rbp-78h] BYREF
  win_musl::PathMarkupProducer *v79; // [rsp+98h] [rbp-70h] BYREF
  __int64 v80; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v81; // [rsp+A8h] [rbp-60h]
  __int64 v82; // [rsp+B0h] [rbp-58h]
  __int128 *v83; // [rsp+B8h] [rbp-50h] BYREF
  win_musl::PathMarkupProducer *v84; // [rsp+C0h] [rbp-48h]
  _BYTE v85[16]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v86; // [rsp+D8h] [rbp-30h] BYREF
  __int128 *v87; // [rsp+E0h] [rbp-28h]
  __int64 v88; // [rsp+E8h] [rbp-20h]
  __m128i v89; // [rsp+F0h] [rbp-18h]
  void *v90; // [rsp+100h] [rbp-8h]
  void *v91; // [rsp+108h] [rbp+0h]
  void *v92; // [rsp+110h] [rbp+8h]
  __int16 v93; // [rsp+118h] [rbp+10h]
  char v94; // [rsp+11Ah] [rbp+12h]
  __int16 v95; // [rsp+120h] [rbp+18h]
  char v96; // [rsp+122h] [rbp+1Ah]
  __int128 *v97; // [rsp+128h] [rbp+20h]
  LPVOID v98; // [rsp+130h] [rbp+28h] BYREF
  __int128 v99; // [rsp+138h] [rbp+30h] BYREF
  __int128 v100; // [rsp+148h] [rbp+40h]
  _BYTE v101[76]; // [rsp+158h] [rbp+50h] BYREF
  char v102; // [rsp+1A4h] [rbp+9Ch]
  _QWORD v103[3]; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int64 v104; // [rsp+1C0h] [rbp+B8h]
  _BYTE v105[40]; // [rsp+1C8h] [rbp+C0h] BYREF
  _BYTE v106[24]; // [rsp+1F0h] [rbp+E8h] BYREF
  char v107; // [rsp+208h] [rbp+100h]
  _BYTE pExceptionObject[76]; // [rsp+218h] [rbp+110h] BYREF
  char v109; // [rsp+264h] [rbp+15Ch]
  _BYTE v110[72]; // [rsp+2B8h] [rbp+1B0h] BYREF
  char v111; // [rsp+300h] [rbp+1F8h]

  v4 = *(_QWORD *)(a1 + 8);
  Opacity = win_dox::XpsOMVisual::GetOpacity(a2);
  if ( Opacity != 1.0 )
    win_musl::XpsElementMarkupProducer::SetAttribute<float>(v4, L"Opacity", &Opacity);
  StrokeDashes = win_dox::XpsOMPath::GetStrokeDashes(a2, &pv);
  win_dox::SendDashArray<win_musl::PathMarkupProducer>(*(_QWORD *)(a1 + 8), StrokeDashes);
  if ( pv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  v6 = *(_QWORD *)(a1 + 8);
  Opacity = COERCE_FLOAT(win_dox::XpsOMPath::GetStrokeDashCap(a2));
  v8 = 1;
  if ( LODWORD(Opacity) != 1 )
    win_musl::XpsElementMarkupProducer::SetAttribute<enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0006>(
      v6,
      v7,
      &Opacity);
  v9 = *(_QWORD *)(a1 + 8);
  Opacity = win_dox::XpsOMPath::GetStrokeDashOffset(a2);
  if ( Opacity != 0.0 )
    win_musl::XpsElementMarkupProducer::SetAttribute<float>(v9, L"StrokeDashOffset", &Opacity);
  v10 = *(_QWORD *)(a1 + 8);
  Opacity = COERCE_FLOAT(win_dox::XpsOMPath::GetStrokeStartLineCap(a2));
  if ( LODWORD(Opacity) != 1 )
    win_musl::XpsElementMarkupProducer::SetAttribute<enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005>(
      v10,
      L"StrokeStartLineCap",
      &Opacity);
  v11 = *(_QWORD *)(a1 + 8);
  Opacity = COERCE_FLOAT(win_dox::XpsOMPath::GetStrokeEndLineCap(a2));
  if ( LODWORD(Opacity) != 1 )
    win_musl::XpsElementMarkupProducer::SetAttribute<enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005>(
      v11,
      L"StrokeEndLineCap",
      &Opacity);
  v12 = *(_QWORD *)(a1 + 8);
  Opacity = COERCE_FLOAT(win_dox::XpsOMPath::GetStrokeLineJoin(a2));
  if ( LODWORD(Opacity) != 1 )
    win_musl::XpsElementMarkupProducer::SetAttribute<enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007>(
      v12,
      v13,
      &Opacity);
  v14 = *(_QWORD *)(a1 + 8);
  Opacity = win_dox::XpsOMPath::GetStrokeMiterLimit(a2);
  if ( Opacity != 10.0 )
    win_musl::XpsElementMarkupProducer::SetAttribute<float>(v14, L"StrokeMiterLimit", &Opacity);
  v15 = *(_QWORD *)(a1 + 8);
  Opacity = win_dox::XpsOMPath::GetStrokeThickness(a2);
  if ( Opacity != 1.0 )
    win_musl::XpsElementMarkupProducer::SetAttribute<float>(v15, L"StrokeThickness", &Opacity);
  v16 = *(_QWORD *)(a1 + 8);
  if ( (unsigned int)win_dox::XpsOMPath::GetSnapsToPixels(a2) )
  {
    LOBYTE(v72) = 1;
    win_musl::XpsElementMarkupProducer::SetAttribute<bool>(v16, L"SnapsToDevicePixels", &v72);
  }
  win_dox::XpsOMVisual::GetName(a2, &v98);
  v17 = -1;
  v18 = v98;
  if ( v98 && dword_180229818 != -1 )
  {
    if ( *(_QWORD *)(a1 + 32) )
    {
      std::wstring::wstring(v103, L"Name set for item in dictionary");
      v67 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v105, v103);
      v68 = win_musl::Formatter::c_str(v67);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x994u,
        -2142108671,
        (__int64)v68);
      throw (SplException::THResultException *)pExceptionObject;
    }
    win_dox::SendName<win_musl::PathMarkupProducer>(*(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 24), v98);
  }
  HyperlinkNavigateUri = win_dox::XpsOMVisual::GetHyperlinkNavigateUri(a2, &v75);
  v20 = -1;
  if ( *(_QWORD *)xpsom::XpsOMCorePropertiesReceiver::SetVersion(HyperlinkNavigateUri, &pv) )
    v20 = dword_180229818;
  if ( pv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    pv = 0;
  }
  if ( v75 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
  if ( v20 != -1 )
  {
    v65 = win_dox::XpsOMVisual::GetHyperlinkNavigateUri(a2, &pv);
    AbsoluteUri = (_QWORD *)win_dox::Uri::GetAbsoluteUri(v65, v103);
    if ( AbsoluteUri[3] > 7u )
      AbsoluteUri = (_QWORD *)*AbsoluteUri;
    win_dox::SendString<win_musl::GlyphsMarkupProducer>(
      *(_QWORD *)(a1 + 8),
      win_musl::PathMarkupProducer::SetNavigateUri,
      AbsoluteUri);
    std::wstring::_Tidy_deallocate(v103);
    if ( pv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  }
  v21 = *(_QWORD *)win_dox::XpsOMPath::GetAccessibilityShortDescription(a2, &pv);
  if ( v21 )
  {
    v22 = *(_QWORD *)(a1 + 8);
    v99 = 0;
    v100 = 0;
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(v21 + 2 * v23) );
    std::wstring::_Construct<1,wchar_t const *>(&v99);
    win_musl::CanvasMarkupProducer::SetAutomationPropertiesName(v22, &v99);
    if ( *((_QWORD *)&v100 + 1) > 7u )
      std::_Deallocate<16>(v99, 2LL * *((_QWORD *)&v100 + 1) + 2);
  }
  if ( pv )
    CoTaskMemFree(pv);
  v24 = *(_QWORD *)win_dox::XpsOMPath::GetAccessibilityLongDescription(a2, &pv);
  if ( v24 )
  {
    v25 = *(_QWORD *)(a1 + 8);
    v99 = 0;
    v100 = 0;
    do
      ++v17;
    while ( *(_WORD *)(v24 + 2 * v17) );
    std::wstring::_Construct<1,wchar_t const *>(&v99);
    win_musl::PathMarkupProducer::SetAutomationPropertiesHelpText(v25, &v99);
    if ( *((_QWORD *)&v100 + 1) > 7u )
      std::_Deallocate<16>(v99, 2LL * *((_QWORD *)&v100 + 1) + 2);
  }
  if ( pv )
    CoTaskMemFree(pv);
  v76 = *(__m128i *)(a1 + 40);
  v26 = v76;
  v27 = *(_QWORD *)(a1 + 24);
  v28 = *(__int128 **)(a1 + 16);
  v83 = *(__int128 **)a1;
  v84 = *(win_musl::PathMarkupProducer **)(a1 + 8);
  v79 = (win_musl::PathMarkupProducer *)v85;
  win_dox::XpsOMVisual::XpsOMVisual((win_dox::XpsOMVisual *)v85, a2);
  v86 = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v86,
    *((_QWORD *)a2 + 2));
  v87 = v28;
  v88 = v27;
  v89.m128i_i8[0] = _mm_cvtsi128_si32(v26);
  *(__int64 *)((char *)v89.m128i_i64 + 1) = *(__int64 *)((char *)v76.m128i_i64 + 1);
  *(__int32 *)((char *)&v89.m128i_i32[2] + 1) = *(__int32 *)((char *)&v76.m128i_i32[2] + 1);
  *(__int16 *)((char *)&v89.m128i_i16[6] + 1) = *(__int16 *)((char *)&v76.m128i_i16[6] + 1);
  v89.m128i_i8[15] = _mm_cvtsi128_si32(_mm_srli_si128(v26, 15));
  v90 = &win_musl::PathMarkupProducer::SetPathClip;
  v91 = &win_musl::PathMarkupProducer::SetPathRenderTransform;
  v92 = &win_musl::PathMarkupProducer::SetPathOpacityMask;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v76.m128i_i8[0] = v89.m128i_i8[0];
  v76.m128i_i8[15] = v89.m128i_i8[15];
  v96 = win_dox::CheckSendAttrGeometry<win_dox::XpsOMPath,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer>(
          (unsigned int)v85,
          (unsigned int)win_dox::XpsOMPath::GetGeometryLookup,
          (unsigned int)&win_dox::XpsOMPath::GetGeometry,
          (_DWORD)v84,
          (__int64)win_musl::PathMarkupProducer::SetData,
          (__int64)&v76);
  v29 = v89.m128i_i8[0];
  v78 = v87;
  v30 = v84;
  v77 = v84;
  v97 = v83;
  win_dox::XpsOMPath::GetFillBrush(v85, &v76);
  v32 = *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(&v76, &pv);
  if ( pv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  if ( !v32 )
  {
    if ( v76.m128i_i64[1] )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76.m128i_i64[1] + 16LL))(v76.m128i_i64[1]);
      v76.m128i_i64[1] = 0;
    }
    if ( v76.m128i_i64[0] )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76.m128i_i64[0] + 16LL))(v76.m128i_i64[0]);
    v34 = 1;
    v35 = -1;
    goto LABEL_52;
  }
  win_dox::XpsOMPath::GetFillBrushLookup(v85, &v74);
  v35 = -1;
  if ( v74 && dword_180229818 != -1 && (!v29 || !win_dox::CanInlineBrush((win_dox *)&v76, v74)) )
  {
    v102 = 0;
    StaticResource = win_dox::MakeStaticResource(v103);
    if ( v102 == 2 )
    {
      v102 = 0;
      std::wstring::_Tidy_deallocate(v101);
    }
    else if ( v102 == 1 )
    {
      v102 = 0;
      dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>(v101);
    }
    std::wstring::wstring(v101, StaticResource);
    v102 = 2;
    if ( v104 > 7 )
      std::_Deallocate<16>(v103[0], 2 * v104 + 2);
    win_musl::PathMarkupProducer::SetFill(v30, (const struct win_dox::XpsBrush *)v101);
    dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>(v101);
    v62 = v74;
    if ( !v74 )
      goto LABEL_127;
    goto LABEL_126;
  }
  v75 = 0;
  Interface = (_QWORD **)win_dox::StartSendBase<IByteSender>::GetInterface(&v76, &pv);
  v43 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*Interface;
  v44 = (void (__fastcall **)(_QWORD, GUID *, __int64 *))**Interface;
  v45 = v75;
  v75 = 0;
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  v75 = 0;
  (*v44)(v43, &GUID_a06f9f05_3be9_4763_98a8_094fc672e488, &v75);
  if ( pv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  if ( v75 )
  {
    pv = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &pv,
      v75);
    win_dox::XpsOMSolidColorBrush::XpsOMSolidColorBrush(&v80, &pv);
    Opacity = 0.0;
    SetErrorInfo(0, 0);
    v56 = (*(__int64 (__fastcall **)(__int64, float *))(*(_QWORD *)v81 + 40LL))(v81, &Opacity);
    if ( v56 < 0 )
      SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v56, v57, v58, v59);
    if ( Opacity != 1.0 )
    {
      if ( v82 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
        v82 = 0;
      }
      win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v80);
      if ( v75 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
        v75 = 0;
      }
      goto LABEL_78;
    }
    v107 = 0;
    win_dox::XpsOMSolidColorBrush::GetColor(&v80, v105);
    v111 = 0;
    *(_QWORD *)&v99 = v97;
    *((_QWORD *)&v99 + 1) = v110;
    *(_QWORD *)&v100 = v78;
    v78 = &v99;
    dynamic_storage_visitor<win_dox::XpsOMToModelColor,void>::operator()<win_mp_lib::type_list<win_dox::XpsOMSRgbColor,win_mp_lib::type_list<win_dox::XpsOMScRgbColor,win_mp_lib::type_list<win_dox::XpsOMContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsOMSRgbColor,win_mp_lib::type_list<win_dox::XpsOMScRgbColor,win_mp_lib::type_list<win_dox::XpsOMContextColor,win_mp_lib::null_type>>>>(
      &v78,
      v105);
    v109 = 0;
    v102 = 1;
    win_dox::XpsColor::XpsColor((win_dox::XpsColor *)v101, (const struct win_dox::XpsColor *)v110);
    if ( v109 == 2 )
    {
      v109 = 0;
      std::wstring::`scalar deleting destructor'(pExceptionObject);
    }
    dynamic_storage<win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>::operator=(
      pExceptionObject,
      v101);
    v60 = v102;
    if ( v102 == 2 )
    {
      dynamic_storage<win_mp_lib::null_type,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>::set<std::wstring>(
        pExceptionObject,
        v101);
      v60 = v102;
    }
    if ( v60 == 2 )
    {
      v102 = 0;
      std::wstring::_Tidy_deallocate(v101);
    }
    else
    {
      if ( v60 != 1 )
        goto LABEL_119;
      v102 = 0;
      dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>(v101);
    }
    if ( v102 == 1 )
    {
      v102 = 0;
      dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>(v101);
    }
LABEL_119:
    win_musl::PathMarkupProducer::SetFill(v77, (const struct win_dox::XpsBrush *)pExceptionObject);
    dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>(pExceptionObject);
    dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>(v110);
    v61 = v107;
    if ( (unsigned __int8)(v107 - 2) <= 1u )
      goto LABEL_120;
    if ( v107 == 1 )
    {
      v107 = 0;
      win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v106);
      v61 = v107;
    }
    if ( v61 == 2 )
    {
LABEL_120:
      v107 = 0;
    }
    else if ( v61 == 1 )
    {
      v107 = 0;
      win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v106);
      if ( v107 == 1 )
      {
        v107 = 0;
        win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v106);
      }
    }
    if ( v82 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
      v82 = 0;
    }
    win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v80);
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    v62 = v74;
    if ( !v74 )
      goto LABEL_127;
LABEL_126:
    CoTaskMemFree(v62);
    v74 = 0;
LABEL_127:
    win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v76);
    v34 = 1;
    goto LABEL_52;
  }
LABEL_78:
  if ( v74 )
  {
    CoTaskMemFree(v74);
    v74 = 0;
  }
  win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v76);
  v34 = 0;
LABEL_52:
  LOBYTE(v95) = v34;
  LOBYTE(v93) = win_dox::CheckSendAttrTransform<win_dox::XpsOMPath,win_musl::PathMarkupProducer>(v85, v31, v33, v84);
  v76 = v89;
  v94 = win_dox::CheckSendAttrGeometry<win_dox::XpsOMPath,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer>(
          (unsigned int)v85,
          (unsigned int)win_dox::XpsOMPage::GetLanguage,
          (unsigned int)&win_dox::XpsOMVisual::GetClipGeometry,
          (_DWORD)v84,
          (__int64)win_musl::CanvasMarkupProducer::SetClip,
          (__int64)&v76);
  win_dox::VisualAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer,win_dox::XpsOMPath>::CheckSendAttrOpacityMask(&v83);
  LOBYTE(v72) = v89.m128i_i8[0];
  v97 = v87;
  v36 = v84;
  v79 = v84;
  v78 = v83;
  win_dox::XpsOMPath::GetStrokeBrush(v85, &v76);
  v37 = *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(&v76, &v77);
  if ( v77 )
    (*(void (__fastcall **)(win_musl::PathMarkupProducer *))(*(_QWORD *)v77 + 16LL))(v77);
  if ( !v37 )
  {
    if ( v76.m128i_i64[1] )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76.m128i_i64[1] + 16LL))(v76.m128i_i64[1]);
      v76.m128i_i64[1] = 0;
    }
    if ( v76.m128i_i64[0] )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76.m128i_i64[0] + 16LL))(v76.m128i_i64[0]);
    goto LABEL_59;
  }
  win_dox::XpsOMPath::GetStrokeBrushLookup(v85, &v74);
  if ( v74 && dword_180229818 != -1 && (!(_BYTE)v72 || !win_dox::CanInlineBrush((win_dox *)&v76, v74)) )
  {
    v102 = 0;
    v64 = win_dox::MakeStaticResource(v103);
    if ( v102 == 2 )
    {
      v102 = 0;
      std::wstring::_Tidy_deallocate(v101);
    }
    else if ( v102 == 1 )
    {
      v102 = 0;
      dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>(v101);
    }
    std::wstring::wstring(v101, v64);
    v102 = 2;
    if ( v104 > 7 )
      std::_Deallocate<16>(v103[0], 2 * v104 + 2);
    win_musl::PathMarkupProducer::SetStroke(v36, (const struct win_dox::XpsBrush *)v101);
    dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>(v101);
LABEL_103:
    if ( v74 )
    {
      CoTaskMemFree(v74);
      v74 = 0;
    }
    win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v76);
    goto LABEL_59;
  }
  v75 = 0;
  v46 = (_QWORD **)win_dox::StartSendBase<IByteSender>::GetInterface(&v76, &v77);
  v47 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*v46;
  v48 = (void (__fastcall **)(_QWORD, GUID *, __int64 *))**v46;
  v49 = v75;
  v75 = 0;
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  v75 = 0;
  (*v48)(v47, &GUID_a06f9f05_3be9_4763_98a8_094fc672e488, &v75);
  if ( v77 )
    (*(void (__fastcall **)(win_musl::PathMarkupProducer *))(*(_QWORD *)v77 + 16LL))(v77);
  if ( v75 )
  {
    pv = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &pv,
      v75);
    win_dox::XpsOMSolidColorBrush::XpsOMSolidColorBrush(&v80, &pv);
    Opacity = 0.0;
    SetErrorInfo(0, 0);
    v50 = (*(__int64 (__fastcall **)(__int64, float *))(*(_QWORD *)v81 + 40LL))(v81, &Opacity);
    SplException::ThrowFromHRErrorInfo((SplException *)v50, v51, v52, v53);
    if ( Opacity == 1.0 )
    {
      v107 = 0;
      win_dox::XpsOMSolidColorBrush::GetColor(&v80, v105);
      v111 = 0;
      *(_QWORD *)&v99 = v78;
      *((_QWORD *)&v99 + 1) = v110;
      *(_QWORD *)&v100 = v97;
      v77 = (win_musl::PathMarkupProducer *)&v99;
      dynamic_storage_visitor<win_dox::XpsOMToModelColor,void>::operator()<win_mp_lib::type_list<win_dox::XpsOMSRgbColor,win_mp_lib::type_list<win_dox::XpsOMScRgbColor,win_mp_lib::type_list<win_dox::XpsOMContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsOMSRgbColor,win_mp_lib::type_list<win_dox::XpsOMScRgbColor,win_mp_lib::type_list<win_dox::XpsOMContextColor,win_mp_lib::null_type>>>>(
        &v77,
        v105);
      v109 = 0;
      v102 = 1;
      win_dox::XpsColor::XpsColor((win_dox::XpsColor *)v101, (const struct win_dox::XpsColor *)v110);
      if ( v109 == 2 )
        dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>::reset(pExceptionObject);
      dynamic_storage<win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>::operator=(
        pExceptionObject,
        v101);
      v54 = v102;
      if ( v102 == 2 )
      {
        dynamic_storage<win_mp_lib::null_type,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>::set<std::wstring>(
          pExceptionObject,
          v101);
        v54 = v102;
      }
      if ( v54 == 2 )
      {
        v102 = 0;
        std::wstring::_Tidy_deallocate(v101);
      }
      else
      {
        if ( v54 != 1 )
        {
LABEL_97:
          win_musl::PathMarkupProducer::SetStroke(v79, (const struct win_dox::XpsBrush *)pExceptionObject);
          dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsColor,win_mp_lib::null_type>>>(pExceptionObject);
          dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>(v110);
          v55 = v107;
          if ( (unsigned __int8)(v107 - 2) <= 1u )
            goto LABEL_98;
          if ( v107 == 1 )
          {
            v107 = 0;
            win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v106);
            v55 = v107;
          }
          if ( v55 == 2 )
          {
LABEL_98:
            v107 = 0;
          }
          else if ( v55 == 1 )
          {
            v107 = 0;
            win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v106);
            if ( v107 == 1 )
            {
              v107 = 0;
              win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v106);
            }
          }
          if ( v82 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
            v82 = 0;
          }
          win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v80);
          if ( v75 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
            v75 = 0;
          }
          goto LABEL_103;
        }
        v102 = 0;
        dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>(v101);
      }
      if ( v102 == 1 )
      {
        v102 = 0;
        dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>,win_mp_lib::type_list<win_dox::XpsSRGBColor,win_mp_lib::type_list<win_dox::XpsScRGBColor,win_mp_lib::type_list<win_dox::XpsContextColor,win_mp_lib::null_type>>>>(v101);
      }
      goto LABEL_97;
    }
    if ( v82 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
      v82 = 0;
    }
    win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v80);
    if ( v75 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
  }
  if ( v74 )
  {
    CoTaskMemFree(v74);
    v74 = 0;
  }
  win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v76);
  v8 = 0;
LABEL_59:
  HIBYTE(v95) = v8;
  Language = (_QWORD *)win_dox::XpsOMVisual::GetLanguage(a2, &v79);
  v39 = *(_QWORD *)(a1 + 8);
  std::wstring::wstring(&v99, *Language);
  if ( v40 )
  {
    do
      ++v35;
    while ( *(_WORD *)(v40 + 2 * v35) );
    std::wstring::_Assign<wchar_t>(&v99, v40, v35);
    win_musl::XpsElementMarkupProducer::SetAttribute<win_dox::XpsLanguage>(v39, v69, &v99);
  }
  std::wstring::_Tidy_deallocate(&v99);
  if ( v79 )
    CoTaskMemFree(v79);
  v41 = *(_QWORD *)(a1 + 32);
  if ( v41 )
  {
    v70 = *(_QWORD *)(a1 + 8);
    std::wstring::wstring(v103, v41);
    win_musl::XpsElementMarkupProducer::SetAttribute<std::wstring>(v70, L"x:Key", v103);
    std::wstring::_Tidy_deallocate(v103);
  }
  if ( !v94 )
    win_dox::CheckSendElemGeometry<win_dox::XpsOMPath,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer>(
      v85,
      &win_dox::XpsOMVisual::GetClipGeometryLocal,
      v84,
      v90);
  win_dox::VisualAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer,win_dox::XpsOMPath>::CheckSendElemOpacityMask(&v83);
  win_dox::PathAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::CheckSendElemFill(&v83);
  win_dox::PathAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::CheckSendElemStroke(&v83);
  if ( !v96 )
    win_dox::CheckSendElemGeometry<win_dox::XpsOMPath,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer>(
      v85,
      &win_dox::XpsOMPath::GetGeometryLocal,
      v84,
      &win_musl::PathMarkupProducer::SetPathData);
  win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v85);
  if ( v18 )
    CoTaskMemFree(v18);
}

```

## disassembly

```asm
0x18001c4ac  mov     rax, rsp
0x18001c4af  mov     [rax+18h], rbx
0x18001c4b3  push    rbp
0x18001c4b4  push    rsi
0x18001c4b5  push    rdi
0x18001c4b6  push    r12
0x18001c4b8  push    r13
0x18001c4ba  push    r14
0x18001c4bc  push    r15
0x18001c4be  lea     rbp, [rax-258h]
0x18001c4c5  sub     rsp, 320h
0x18001c4cc  movaps  xmmword ptr [rax-48h], xmm6
0x18001c4d0  mov     rax, cs:__security_cookie
0x18001c4d7  xor     rax, rsp
0x18001c4da  mov     [rbp+250h+var_50], rax
0x18001c4e1  mov     r13, rdx
0x18001c4e4  mov     r12, rcx
0x18001c4e7  xor     r14d, r14d
0x18001c4ea  mov     rbx, [rcx+8]
0x18001c4ee  mov     rcx, rdx; this
0x18001c4f1  call    ?GetOpacity@XpsOMVisual@win_dox@@QEBAMXZ; win_dox::XpsOMVisual::GetOpacity(void)
0x18001c4f6  movss   dword ptr [rsp+350h+var_310], xmm0
0x18001c4fc  ucomiss xmm0, cs:__real@3f800000
0x18001c503  jp      loc_18001D3D6
0x18001c509  jnz     loc_18001D3D6
0x18001c50f  lea     rdx, [rsp+350h+pv]
0x18001c514  mov     rcx, r13
0x18001c517  call    ?GetStrokeDashes@XpsOMPath@win_dox@@QEBA?AV?$XpsOMPodStructCollection@UIXpsOMDashCollection@@@2@XZ; win_dox::XpsOMPath::GetStrokeDashes(void)
0x18001c51c  nop
0x18001c51d  mov     rdx, rax
0x18001c520  mov     rcx, [r12+8]
0x18001c525  call    ??$SendDashArray@VPathMarkupProducer@win_musl@@@win_dox@@YAXPEAVPathMarkupProducer@win_musl@@AEBV?$XpsOMPodStructCollection@UIXpsOMDashCollection@@@0@@Z; win_dox::SendDashArray<win_musl::PathMarkupProducer>(win_musl::PathMarkupProducer *,win_dox::XpsOMPodStructCollection<IXpsOMDashCollection> const &)
0x18001c52a  nop
0x18001c52b  mov     rcx, [rsp+350h+pv]
0x18001c530  test    rcx, rcx
0x18001c533  jz      short loc_18001C542
0x18001c535  mov     rax, [rcx]
0x18001c538  mov     rax, [rax+10h]
0x18001c53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c541  nop
0x18001c542  mov     rbx, [r12+8]
0x18001c547  mov     rcx, r13; this
0x18001c54a  call    ?GetStrokeDashCap@XpsOMPath@win_dox@@QEBA?AW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0006@@XZ; win_dox::XpsOMPath::GetStrokeDashCap(void)
0x18001c54f  mov     dword ptr [rsp+350h+var_310], eax
0x18001c553  mov     r15d, 1
0x18001c559  cmp     eax, r15d
0x18001c55c  jnz     loc_18001D3EF
0x18001c562  mov     rbx, [r12+8]
0x18001c567  mov     rcx, r13; this
0x18001c56a  call    ?GetStrokeDashOffset@XpsOMPath@win_dox@@QEBAMXZ; win_dox::XpsOMPath::GetStrokeDashOffset(void)
0x18001c56f  movss   dword ptr [rsp+350h+var_310], xmm0
0x18001c575  ucomiss xmm0, cs:__real@00000000
0x18001c57c  jp      loc_18001D401
0x18001c582  jnz     loc_18001D401
0x18001c588  mov     rbx, [r12+8]
0x18001c58d  mov     rcx, r13; this
0x18001c590  call    ?GetStrokeStartLineCap@XpsOMPath@win_dox@@QEBA?AW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@XZ; win_dox::XpsOMPath::GetStrokeStartLineCap(void)
0x18001c595  mov     dword ptr [rsp+350h+var_310], eax
0x18001c599  cmp     eax, r15d
0x18001c59c  jz      short loc_18001C5B2
0x18001c59e  lea     r8, [rsp+350h+var_310]
0x18001c5a3  lea     rdx, ?gc_strokeStartLineCap@Attribute@Xps@win_musl@@3QB_WB; "StrokeStartLineCap"
0x18001c5aa  mov     rcx, rbx
0x18001c5ad  call    ??$SetAttribute@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@@Z; win_musl::XpsElementMarkupProducer::SetAttribute<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005>(wchar_t const *,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005 const &)
0x18001c5b2  mov     rbx, [r12+8]
0x18001c5b7  mov     rcx, r13; this
0x18001c5ba  call    ?GetStrokeEndLineCap@XpsOMPath@win_dox@@QEBA?AW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@XZ; win_dox::XpsOMPath::GetStrokeEndLineCap(void)
0x18001c5bf  mov     dword ptr [rsp+350h+var_310], eax
0x18001c5c3  cmp     eax, r15d
0x18001c5c6  jz      short loc_18001C5DC
0x18001c5c8  lea     r8, [rsp+350h+var_310]
0x18001c5cd  lea     rdx, ?gc_strokeEndLineCap@Attribute@Xps@win_musl@@3QB_WB; "StrokeEndLineCap"
0x18001c5d4  mov     rcx, rbx
0x18001c5d7  call    ??$SetAttribute@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@@Z; win_musl::XpsElementMarkupProducer::SetAttribute<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005>(wchar_t const *,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005 const &)
0x18001c5dc  mov     rbx, [r12+8]
0x18001c5e1  mov     rcx, r13; this
0x18001c5e4  call    ?GetStrokeLineJoin@XpsOMPath@win_dox@@QEBA?AW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007@@XZ; win_dox::XpsOMPath::GetStrokeLineJoin(void)
0x18001c5e9  mov     dword ptr [rsp+350h+var_310], eax
0x18001c5ed  cmp     eax, r15d
0x18001c5f0  jz      short loc_18001C5FF
0x18001c5f2  lea     r8, [rsp+350h+var_310]
0x18001c5f7  mov     rcx, rbx
0x18001c5fa  call    ??$SetAttribute@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007@@@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007@@@Z; win_musl::XpsElementMarkupProducer::SetAttribute<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007>(wchar_t const *,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007 const &)
0x18001c5ff  mov     rbx, [r12+8]
0x18001c604  mov     rcx, r13; this
0x18001c607  call    ?GetStrokeMiterLimit@XpsOMPath@win_dox@@QEBAMXZ; win_dox::XpsOMPath::GetStrokeMiterLimit(void)
0x18001c60c  movss   dword ptr [rsp+350h+var_310], xmm0
0x18001c612  ucomiss xmm0, cs:__real@41200000
0x18001c619  jp      loc_18001D41A
0x18001c61f  jnz     loc_18001D41A
0x18001c625  mov     rbx, [r12+8]
0x18001c62a  mov     rcx, r13; this
0x18001c62d  call    ?GetStrokeThickness@XpsOMPath@win_dox@@QEBAMXZ; win_dox::XpsOMPath::GetStrokeThickness(void)
0x18001c632  movss   dword ptr [rsp+350h+var_310], xmm0
0x18001c638  ucomiss xmm0, cs:__real@3f800000
0x18001c63f  jp      short loc_18001C643
0x18001c641  jz      short loc_18001C657
0x18001c643  lea     r8, [rsp+350h+var_310]
0x18001c648  lea     rdx, ?gc_strokeThickness@Attribute@Xps@win_musl@@3QB_WB; "StrokeThickness"
0x18001c64f  mov     rcx, rbx
0x18001c652  call    ??$SetAttribute@M@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBM@Z; win_musl::XpsElementMarkupProducer::SetAttribute<float>(wchar_t const *,float const &)
0x18001c657  mov     rbx, [r12+8]
0x18001c65c  mov     rcx, r13; this
0x18001c65f  call    ?GetSnapsToPixels@XpsOMPath@win_dox@@QEBAHXZ; win_dox::XpsOMPath::GetSnapsToPixels(void)
0x18001c664  test    eax, eax
0x18001c666  jnz     loc_18001D433
0x18001c66c  lea     rdx, [rbp+250h+var_228]
0x18001c670  mov     rcx, r13
0x18001c673  call    ?GetName@XpsOMVisual@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMVisual::GetName(void)
0x18001c678  nop
0x18001c679  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001c67d  mov     rbx, [rbp+250h+var_228]
0x18001c681  test    rbx, rbx
0x18001c684  jz      short loc_18001C692
0x18001c686  cmp     cs:dword_180229818, edi
0x18001c68c  jnz     loc_18001D451
0x18001c692  lea     rdx, [rsp+350h+var_2F0]
0x18001c697  mov     rcx, r13
0x18001c69a  call    ?GetHyperlinkNavigateUri@XpsOMVisual@win_dox@@QEBA?AVUri@2@XZ; win_dox::XpsOMVisual::GetHyperlinkNavigateUri(void)
0x18001c69f  nop
0x18001c6a0  lea     rdx, [rsp+350h+pv]
0x18001c6a5  mov     rcx, rax
0x18001c6a8  call    ?SetVersion@XpsOMCorePropertiesReceiver@xpsom@@QEAA?AVXpsOMVersionReceiver@2@XZ; xpsom::XpsOMCorePropertiesReceiver::SetVersion(void)
0x18001c6ad  mov     esi, edi
0x18001c6af  cmp     [rax], r14
0x18001c6b2  cmovnz  esi, cs:dword_180229818
0x18001c6b9  mov     rcx, [rsp+350h+pv]
0x18001c6be  test    rcx, rcx
0x18001c6c1  jz      short loc_18001C6D4
0x18001c6c3  mov     rax, [rcx]
0x18001c6c6  mov     rax, [rax+10h]
0x18001c6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6cf  mov     [rsp+350h+pv], r14
0x18001c6d4  mov     rcx, [rsp+350h+var_2F0]
0x18001c6d9  test    rcx, rcx
0x18001c6dc  jnz     loc_18001CB14
0x18001c6e2  cmp     esi, edi
0x18001c6e4  jnz     loc_18001D370
0x18001c6ea  lea     rdx, [rsp+350h+pv]
0x18001c6ef  mov     rcx, r13
0x18001c6f2  call    ?GetAccessibilityShortDescription@XpsOMPath@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMPath::GetAccessibilityShortDescription(void)
0x18001c6f7  nop
0x18001c6f8  mov     rdx, [rax]
0x18001c6fb  test    rdx, rdx
0x18001c6fe  jz      short loc_18001C746
0x18001c700  mov     rsi, [r12+8]
0x18001c705  xorps   xmm0, xmm0
0x18001c708  movups  [rbp+250h+var_220], xmm0
0x18001c70c  xorps   xmm1, xmm1
0x18001c70f  movdqu  [rbp+250h+var_210], xmm1
0x18001c714  mov     r8, rdi
0x18001c717  inc     r8
0x18001c71a  cmp     [rdx+r8*2], r14w
0x18001c71f  jnz     short loc_18001C717
0x18001c721  lea     rcx, [rbp+250h+var_220]
0x18001c725  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001c72a  nop
0x18001c72b  lea     rdx, [rbp+250h+var_220]
0x18001c72f  mov     rcx, rsi
0x18001c732  call    ?SetAutomationPropertiesName@CanvasMarkupProducer@win_musl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::CanvasMarkupProducer::SetAutomationPropertiesName(std::wstring const &)
0x18001c737  nop
0x18001c738  mov     rdx, qword ptr [rbp+250h+var_210+8]
0x18001c73c  cmp     rdx, 7
0x18001c740  ja      loc_18001D4DE
0x18001c746  mov     rcx, [rsp+350h+pv]; pv
0x18001c74b  test    rcx, rcx
0x18001c74e  jz      short loc_18001C756
0x18001c750  call    cs:__imp_CoTaskMemFree
0x18001c756  lea     rdx, [rsp+350h+pv]
0x18001c75b  mov     rcx, r13
0x18001c75e  call    ?GetAccessibilityLongDescription@XpsOMPath@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMPath::GetAccessibilityLongDescription(void)
0x18001c763  nop
0x18001c764  mov     rdx, [rax]
0x18001c767  test    rdx, rdx
0x18001c76a  jz      short loc_18001C7B2
0x18001c76c  mov     rsi, [r12+8]
0x18001c771  xorps   xmm0, xmm0
0x18001c774  movups  [rbp+250h+var_220], xmm0
0x18001c778  xorps   xmm1, xmm1
0x18001c77b  movdqu  [rbp+250h+var_210], xmm1
0x18001c780  inc     rdi
0x18001c783  cmp     [rdx+rdi*2], r14w
0x18001c788  jnz     short loc_18001C780
0x18001c78a  mov     r8, rdi
0x18001c78d  lea     rcx, [rbp+250h+var_220]
0x18001c791  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001c796  nop
0x18001c797  lea     rdx, [rbp+250h+var_220]
0x18001c79b  mov     rcx, rsi
0x18001c79e  call    ?SetAutomationPropertiesHelpText@PathMarkupProducer@win_musl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::PathMarkupProducer::SetAutomationPropertiesHelpText(std::wstring const &)
0x18001c7a3  nop
0x18001c7a4  mov     rdx, qword ptr [rbp+250h+var_210+8]
0x18001c7a8  cmp     rdx, 7
0x18001c7ac  ja      loc_18001D4F4
0x18001c7b2  mov     rcx, [rsp+350h+pv]; pv
0x18001c7b7  test    rcx, rcx
0x18001c7ba  jz      short loc_18001C7C2
0x18001c7bc  call    cs:__imp_CoTaskMemFree
0x18001c7c2  movups  xmm6, xmmword ptr [r12+28h]
0x18001c7c8  movaps  [rsp+350h+var_2E8+8], xmm6
0x18001c7cd  mov     rsi, [r12+18h]
0x18001c7d2  mov     rdi, [r12+10h]
0x18001c7d7  movd    r14d, xmm6
0x18001c7dc  mov     rax, [r12]
0x18001c7e0  mov     [rbp+250h+var_2A0], rax
0x18001c7e4  mov     rax, [r12+8]
0x18001c7e9  mov     [rbp+250h+var_298], rax
0x18001c7ed  lea     rax, [rbp+250h+var_290]
0x18001c7f1  mov     [rbp+250h+var_2C0], rax
0x18001c7f5  mov     rdx, r13; struct win_dox::XpsOMVisual *
0x18001c7f8  lea     rcx, [rbp+250h+var_290]; this
0x18001c7fc  call    ??0XpsOMVisual@win_dox@@QEAA@AEBV01@@Z; win_dox::XpsOMVisual::XpsOMVisual(win_dox::XpsOMVisual const &)
0x18001c801  nop
0x18001c802  mov     [rbp+250h+var_280], 0
0x18001c80a  mov     rdx, [r13+10h]
0x18001c80e  lea     rcx, [rbp+250h+var_280]
0x18001c812  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x18001c817  nop
0x18001c818  mov     [rbp+250h+var_278], rdi
0x18001c81c  mov     [rbp+250h+var_270], rsi
0x18001c820  mov     [rbp+250h+var_268], r14b
0x18001c824  movsd   xmm0, qword ptr [rsp+350h+var_2E8+9]
0x18001c82a  movsd   [rbp+250h+var_267], xmm0
0x18001c82f  mov     edx, [rsp+350h+var_2D7]
0x18001c833  mov     [rbp+250h+var_25F], edx
0x18001c836  movzx   ecx, [rsp+350h+var_2D3]
0x18001c83b  mov     [rbp+250h+var_25B], cx
0x18001c83f  psrldq  xmm6, 0Fh
0x18001c844  movd    eax, xmm6
0x18001c848  mov     [rbp+250h+var_259], al
0x18001c84b  lea     r8, ?SetPathClip@PathMarkupProducer@win_musl@@QEAA?AVGeometriesMarkupProducer@2@XZ; win_musl::PathMarkupProducer::SetPathClip(void)
0x18001c852  mov     [rbp+250h+var_258], r8
0x18001c856  lea     r8, ?SetPathRenderTransform@PathMarkupProducer@win_musl@@QEAA?AVTransformMarkupProducer@2@XZ; win_musl::PathMarkupProducer::SetPathRenderTransform(void)
0x18001c85d  mov     [rbp+250h+var_250], r8
0x18001c861  lea     r8, ?SetPathOpacityMask@PathMarkupProducer@win_musl@@QEAA?AVBrushMarkupProducer@2@XZ; win_musl::PathMarkupProducer::SetPathOpacityMask(void)
0x18001c868  mov     [rbp+250h+var_248], r8
0x18001c86c  xor     r8d, r8d
0x18001c86f  mov     [rbp+250h+var_240], r8w
0x18001c874  mov     [rbp+250h+var_23E], r8b
0x18001c878  mov     [rbp+250h+var_238], r8w
0x18001c87d  mov     [rbp+250h+var_236], r8b
0x18001c881  mov     byte ptr [rsp+350h+var_2E8+8], r14b
0x18001c886  movsd   qword ptr [rsp+350h+var_2E8+9], xmm0
0x18001c88c  mov     [rsp+350h+var_2D7], edx
0x18001c890  mov     [rsp+350h+var_2D3], cx
0x18001c895  mov     [rsp+350h+var_2D1], al
0x18001c899  lea     rax, [rsp+350h+var_2E8+8]
0x18001c89e  mov     qword ptr [rsp+350h+var_328], rax
0x18001c8a3  lea     rax, ?SetData@PathMarkupProducer@win_musl@@QEAAXAEBUXpsGeometries@win_dox@@@Z; win_musl::PathMarkupProducer::SetData(win_dox::XpsGeometries const &)
0x18001c8aa  mov     qword ptr [rsp+350h+var_330], rax
0x18001c8af  mov     r9, [rbp+250h+var_298]
0x18001c8b3  lea     r8, ?GetGeometry@XpsOMPath@win_dox@@QEBA?AVXpsOMGeometry@2@XZ; win_dox::XpsOMPath::GetGeometry(void)
0x18001c8ba  lea     rdx, ?GetGeometryLookup@XpsOMPath@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMPath::GetGeometryLookup(void)
0x18001c8c1  lea     rcx, [rbp+250h+var_290]
0x18001c8c5  call    ??$CheckSendAttrGeometry@VXpsOMPath@win_dox@@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VPathMarkupProducer@4@@win_dox@@YA_NAEBVXpsOMPath@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMGeometry@0@XZPEAVPathMarkupProducer@win_musl@@P856@EAAXAEBUXpsGeometries@0@@ZV?$OptimizerSettings@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@0@@Z; win_dox::CheckSendAttrGeometry<win_dox::XpsOMPath,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer>(win_dox::XpsOMPath const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMPath::*)(void),win_dox::XpsOMGeometry (win_dox::XpsOMPath::*)(void),win_musl::PathMarkupProducer *,void (win_musl::PathMarkupProducer::*)(win_dox::XpsGeometries const &),win_dox::OptimizerSettings<win_musl::PageBodyReceiverTraitsOnMarkupProducer>)
0x18001c8ca  mov     [rbp+250h+var_236], al
0x18001c8cd  mov     sil, [rbp+250h+var_268]
0x18001c8d1  mov     rax, [rbp+250h+var_278]
0x18001c8d5  mov     [rbp+250h+var_2C8], rax
0x18001c8d9  mov     r14, [rbp+250h+var_298]
0x18001c8dd  mov     [rbp+250h+var_2D0], r14
0x18001c8e1  mov     rax, [rbp+250h+var_2A0]
0x18001c8e5  mov     [rbp+250h+var_230], rax
0x18001c8e9  lea     rdx, [rsp+350h+var_2E8+8]
0x18001c8ee  lea     rcx, [rbp+250h+var_290]
0x18001c8f2  call    ?GetFillBrush@XpsOMPath@win_dox@@QEBA?AVXpsOMBrush@2@XZ; win_dox::XpsOMPath::GetFillBrush(void)
0x18001c8f7  nop
0x18001c8f8  lea     rdx, [rsp+350h+pv]
0x18001c8fd  lea     rcx, [rsp+350h+var_2E8+8]
0x18001c902  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18001c907  mov     rdi, [rax]
0x18001c90a  mov     rcx, [rsp+350h+pv]
0x18001c90f  test    rcx, rcx
0x18001c912  jnz     loc_18001CB25
0x18001c918  test    rdi, rdi
0x18001c91b  jnz     loc_18001CB47
0x18001c921  mov     rcx, [rsp+78h]
0x18001c926  test    rcx, rcx
0x18001c929  jz      short loc_18001C93C
0x18001c92b  mov     rax, [rcx]
0x18001c92e  mov     rax, [rax+10h]
0x18001c932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c937  mov     [rsp+78h], rdi
0x18001c93c  mov     rcx, qword ptr [rsp+350h+var_2E8+8]
0x18001c941  test    rcx, rcx
0x18001c944  jnz     loc_18001CE8C
0x18001c94a  mov     al, r15b
0x18001c94d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001c951  mov     byte ptr [rbp+250h+var_238], al
0x18001c954  mov     r9, [rbp+250h+var_298]
0x18001c958  lea     rcx, [rbp+250h+var_290]
0x18001c95c  call    ??$CheckSendAttrTransform@VXpsOMPath@win_dox@@VPathMarkupProducer@win_musl@@@win_dox@@YA_NAEBVXpsOMPath@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMMatrixTransform@0@XZPEAVPathMarkupProducer@win_musl@@P856@EAAXAEBUXpsMatrixTransform@0@@Z@Z; win_dox::CheckSendAttrTransform<win_dox::XpsOMPath,win_musl::PathMarkupProducer>(win_dox::XpsOMPath const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMPath::*)(void),win_dox::XpsOMMatrixTransform (win_dox::XpsOMPath::*)(void),win_musl::PathMarkupProducer *,void (win_musl::PathMarkupProducer::*)(win_dox::XpsMatrixTransform const &))
0x18001c961  mov     byte ptr [rbp+250h+var_240], al
0x18001c964  mov     al, [rbp+250h+var_268]
0x18001c967  mov     byte ptr [rsp+350h+var_2E8+8], al
0x18001c96b  movsd   xmm0, [rbp+250h+var_267]
0x18001c970  movsd   qword ptr [rsp+350h+var_2E8+9], xmm0
0x18001c976  mov     eax, [rbp+250h+var_25F]
0x18001c979  mov     [rsp+350h+var_2D7], eax
0x18001c97d  movzx   eax, [rbp+250h+var_25B]
  ... truncated ...
```
