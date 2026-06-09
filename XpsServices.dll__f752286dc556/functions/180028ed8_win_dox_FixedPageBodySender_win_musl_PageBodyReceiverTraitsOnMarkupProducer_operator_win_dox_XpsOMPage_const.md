# win_dox::FixedPageBodySender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::operator()(win_dox::XpsOMPage const &)

- ea: `0x180028ed8`
- end: `0x1800296f2`
- name: `??R?$FixedPageBodySender@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@win_dox@@QEAAXAEBVXpsOMPage@1@@Z`
- size: `2074`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180054360`

## callees

- `0x18000b774`
- `0x18000b8e0`
- `0x18000cb80`
- `0x180012450`
- `0x18001ba5c`
- `0x18001befc`
- `0x18001e634`
- `0x180020814`
- `0x180021e94`
- `0x180028ed8`
- `0x1800296f8`
- `0x1800297c4`
- `0x18002b0bc`
- `0x18002eeec`
- `0x18004eb30`
- `0x18004ef78`
- `0x18004f2c0`
- `0x18004fb4c`
- `0x18005017c`
- `0x180097f24`
- `0x1800b2db0`
- `0x1800b4a34`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c12a8`
- `0x1800c13e0`
- `0x1800c20c4`
- `0x1800cd1bc`
- `0x1800cdc74`
- `0x1800cfd3c`
- `0x1800faf84`
- `0x1800fc204`
- `0x18010cda8`
- `0x1801133a8`
- `0x180134b70`
- `0x1801359ce`
- `0x1801a680c`
- `0x1801a7b7c`
- `0x1801a7d40`
- `0x1801a90e4`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x180028f16`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180028f48`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180028f79`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180028f16`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180028f48`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180028f79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029183`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029183`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall win_dox::FixedPageBodySender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::operator()(
        int *a1,
        __int64 a2)
{
  int v4; // eax
  int v5; // edx
  const char *v6; // r8
  unsigned int v7; // r9d
  int v8; // eax
  int v9; // edx
  const char *v10; // r8
  unsigned int v11; // r9d
  int v12; // eax
  int v13; // edx
  const char *v14; // r8
  unsigned int v15; // r9d
  __int32 v16; // xmm5_4
  float v17; // xmm1_4
  float v18; // xmm2_4
  _QWORD *Name; // rax
  _QWORD *Language; // rax
  const struct win_dox::OpcPartUri *PartName; // rax
  int v22; // ebx
  __int64 v23; // rbx
  int v24; // eax
  win_musl::XpsElementMarkupProducer *v25; // rcx
  __int64 v26; // rbx
  int Visuals; // eax
  LPVOID v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  win_musl::Formatter *v34; // rax
  const wchar_t *v35; // rax
  win_musl::Formatter *v36; // rax
  const wchar_t *v37; // rax
  win_musl::Formatter *v38; // rax
  const wchar_t *v39; // rax
  LPVOID pv; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int64 v42; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v43[3]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v44[3]; // [rsp+78h] [rbp-90h] BYREF
  int v45; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v46[24]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v47; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v48; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-38h] BYREF
  int v50; // [rsp+D8h] [rbp-30h]
  __int128 v51; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v52[7]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v53; // [rsp+130h] [rbp+28h]
  __int64 v54; // [rsp+140h] [rbp+38h]
  _BYTE v55[96]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+1B8h] [rbp+B0h] BYREF

  v41 = 0;
  SetErrorInfo(0, 0);
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a2 + 8) + 56LL))(*(_QWORD *)(a2 + 8), &v41);
  if ( v4 < 0 )
    SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v4, v5, v6, v7);
  v48 = 0;
  SetErrorInfo(0, 0);
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a2 + 8) + 88LL))(*(_QWORD *)(a2 + 8), &v48);
  if ( v8 < 0 )
    SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v8, v9, v10, v11);
  v47 = 0;
  SetErrorInfo(0, 0);
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a2 + 8) + 72LL))(*(_QWORD *)(a2 + 8), &v47);
  if ( v12 < 0 )
    SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v12, v13, v14, v15);
  if ( *((float *)&v48 + 2) < 0.0 || *((float *)&v48 + 3) < 0.0 || *(float *)&v48 > 0.0 || *((float *)&v48 + 1) > 0.0 )
  {
    std::wstring::wstring(&v49, L"(M3.7)(M3.8) Invalid BleedBox value");
    v38 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v52, &v49);
    v39 = win_musl::Formatter::c_str(v38);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0xA53u,
      -2142109692,
      (__int64)v39);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *((float *)&v48 + 2) < 0.0
    || *((float *)&v48 + 3) < 0.0
    || (COERCE_FLOAT(v16 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]),
        *((float *)&v48 + 2) < (float)(COERCE_FLOAT(v48 & v16) + *(float *)&v41))
    || *((float *)&v48 + 3) < (float)(COERCE_FLOAT(DWORD1(v48) & v16) + *((float *)&v41 + 1)) )
  {
    std::wstring::wstring(&v49, L"(M3.9)(M3.10) BleedBox out of sync with page dimensions");
    v36 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v52, &v49);
    v37 = win_musl::Formatter::c_str(v36);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0xA5Cu,
      -2142108407,
      (__int64)v37);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *(float *)&v47 < 0.0
    || *((float *)&v47 + 1) < 0.0
    || *((float *)&v47 + 2) < 0.0
    || *((float *)&v47 + 3) < 0.0
    || (float)(*(float *)&v41 - *(float *)&v47) < *((float *)&v47 + 2)
    || (float)(*((float *)&v41 + 1) - *((float *)&v47 + 1)) < *((float *)&v47 + 3) )
  {
    std::wstring::wstring(&v49, L"(M3.11)(M3.12)(M3.13)(M3.14) Invalid ContentBox value");
    v34 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v52, &v49);
    v35 = win_musl::Formatter::c_str(v34);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0xA64u,
      -2142109685,
      (__int64)v35);
    throw (SplException::THResultException *)pExceptionObject;
  }
  LODWORD(pv) = HIDWORD(v41);
  win_musl::XpsElementMarkupProducer::SetAttribute<float>(*((_QWORD *)a1 + 1), L"Height", &pv);
  LODWORD(pv) = v41;
  win_musl::XpsElementMarkupProducer::SetAttribute<float>(*((_QWORD *)a1 + 1), L"Width", &pv);
  if ( *(float *)&v47 != 0.0
    || *((float *)&v47 + 1) != 0.0
    || (v17 = *(float *)&v41, *((float *)&v47 + 2) != *(float *)&v41)
    || (v18 = *((float *)&v41 + 1), *((float *)&v47 + 3) != *((float *)&v41 + 1)) )
  {
    win_musl::XpsElementMarkupProducer::SetAttribute<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019>(
      *((_QWORD *)a1 + 1),
      L"ContentBox",
      &v47);
    v18 = *((float *)&v41 + 1);
    v17 = *(float *)&v41;
  }
  if ( *(float *)&v48 != 0.0
    || *((float *)&v48 + 1) != 0.0
    || *((float *)&v48 + 2) != v17
    || *((float *)&v48 + 3) != v18 )
  {
    win_musl::XpsElementMarkupProducer::SetAttribute<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019>(
      *((_QWORD *)a1 + 1),
      L"BleedBox",
      &v48);
  }
  *(_OWORD *)&v44[1] = 0;
  std::_Tree<std::_Tset_traits<win_scope::scope<win_musl::UnknownOnly<xpsom::TXpsOMFontResource,win_mp_lib::type_list<IXpsOMFontResource,win_mp_lib::type_list<win_dox::IXpsOMFontProperties,win_mp_lib::type_list<IXpsOMResource,win_mp_lib::type_list<IXpsOMPart,win_mp_lib::null_type>>>>,xpsutil::XpsOMObject> *,win_scope::const_policies<win_scope::com_policies>>,std::less<win_scope::scope<win_musl::UnknownOnly<xpsom::TXpsOMFontResource,win_mp_lib::type_list<IXpsOMFontResource,win_mp_lib::type_list<win_dox::IXpsOMFontProperties,win_mp_lib::type_list<IXpsOMResource,win_mp_lib::type_list<IXpsOMPart,win_mp_lib::null_type>>>>,xpsutil::XpsOMObject> *,win_scope::const_policies<win_scope::com_policies>>>,std::allocator<win_scope::scope<win_musl::UnknownOnly<xpsom::TXpsOMFontResource,win_mp_lib::type_list<IXpsOMFontResource,win_mp_lib::type_list<win_dox::IXpsOMFontProperties,win_mp_lib::type_list<IXpsOMResource,win_mp_lib::type_list<IXpsOMPart,win_mp_lib::null_type>>>>,xpsutil::XpsOMObject> *,win_scope::const_policies<win_scope::com_policies>>>,0>>::_Alloc_sentinel_and_proxy(&v44[1]);
  Name = (_QWORD *)win_dox::XpsOMPage::GetName(a2, &pv);
  win_dox::SendName<win_musl::FixedPageBodyMarkupProducer>(*((_QWORD *)a1 + 1), &v44[1], *Name);
  if ( pv )
    CoTaskMemFree(pv);
  Language = (_QWORD *)win_dox::XpsOMPage::GetLanguage(a2, &pv);
  win_dox::SendLanguage<win_musl::FixedPageBodyMarkupProducer>(*((_QWORD *)a1 + 1), *Language);
  if ( pv )
    CoTaskMemFree(pv);
  PartName = (const struct win_dox::OpcPartUri *)win_dox::XpsOMPart::GetPartName(a2, &v42);
  v45 = *a1;
  win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v46, PartName);
  if ( v43[1] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v43[1] + 16LL))(v43[1]);
    v43[1] = 0;
  }
  win_dox::OpcUri::~OpcUri((win_dox::OpcUri *)&v42);
  if ( *((_BYTE *)a1 + 24) )
  {
    win_dox::XpsOMPage::GetDictionary(a2, &pv);
    v22 = -1;
    if ( *(_QWORD *)xpsom::XpsOMCorePropertiesReceiver::SetVersion(&pv, v44) )
      v22 = dword_180229438;
    if ( v44[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v44[0] + 16LL))(v44[0]);
    if ( v22 == -1 )
    {
      win_musl::FixedPageBodyMarkupProducer::SetResources(*((_QWORD *)a1 + 1), v55);
      win_musl::XpsElementMarkupProducer::AddChildElementWithContext<win_musl::ResourceDictionaryMarkupProducer>(
        v55,
        pExceptionObject);
      win_dox::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>(
        &v49,
        a2,
        pExceptionObject);
      win_musl::XpsElementMarkupProducer::Close((win_musl::XpsElementMarkupProducer *)v55);
      v26 = *((_QWORD *)a1 + 2);
      Visuals = win_dox::XpsOMPage::GetVisuals(a2, v44);
      LOBYTE(v42) = 1;
      v43[0] = &v49;
      win_dox::SendVisualCollection<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::FixedPageBodyMarkupProducer>(
        (unsigned int)&v45,
        *((_QWORD *)a1 + 1),
        Visuals,
        v26,
        (__int64)&v44[1],
        (__int64)&v42);
      win_dox::Uri::~Uri((win_dox::Uri *)v44);
      std::_Tree<std::_Tmap_traits<win_dox::XpsOMGeometry,xpsutil::lpwstr_wrapper,win_dox::geometry_compare,std::allocator<std::pair<win_dox::XpsOMGeometry const,xpsutil::lpwstr_wrapper>>,0>>::~_Tree<std::_Tmap_traits<win_dox::XpsOMGeometry,xpsutil::lpwstr_wrapper,win_dox::geometry_compare,std::allocator<std::pair<win_dox::XpsOMGeometry const,xpsutil::lpwstr_wrapper>>,0>>(&v49);
      win_musl::XpsElementMarkupProducer::~XpsElementMarkupProducer((win_musl::XpsElementMarkupProducer *)pExceptionObject);
      v25 = (win_musl::XpsElementMarkupProducer *)v55;
    }
    else
    {
      win_dox::SendDictionary<win_dox::XpsOMPage,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::FixedPageBodyMarkupProducer>(
        (unsigned int)&v45,
        *((_QWORD *)a1 + 1),
        a2,
        *((_QWORD *)a1 + 2),
        1);
      win_musl::FixedPageBodyMarkupProducer::AddCanvas(*((_QWORD *)a1 + 1), v52);
      win_musl::XpsElementMarkupProducer::AddChildElementWithContext<win_musl::ResourcesMarkupProducer>(
        v52,
        v55,
        L"Canvas.Resources");
      win_musl::XpsElementMarkupProducer::AddChildElementWithContext<win_musl::ResourceDictionaryMarkupProducer>(
        v55,
        pExceptionObject);
      win_dox::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>(
        &v49,
        a2,
        pExceptionObject);
      win_musl::XpsElementMarkupProducer::Close((win_musl::XpsElementMarkupProducer *)v55);
      v23 = *((_QWORD *)a1 + 2);
      v24 = win_dox::XpsOMPage::GetVisuals(a2, v44);
      LOBYTE(v42) = 1;
      v43[0] = &v49;
      win_dox::SendVisualCollection<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(
        (unsigned int)&v45,
        (unsigned int)v52,
        v24,
        v23,
        (__int64)&v44[1],
        (__int64)&v42);
      win_dox::Uri::~Uri((win_dox::Uri *)v44);
      win_musl::XpsElementMarkupProducer::Close((win_musl::XpsElementMarkupProducer *)v52);
      std::_Tree<std::_Tmap_traits<win_dox::XpsOMGeometry,xpsutil::lpwstr_wrapper,win_dox::geometry_compare,std::allocator<std::pair<win_dox::XpsOMGeometry const,xpsutil::lpwstr_wrapper>>,0>>::~_Tree<std::_Tmap_traits<win_dox::XpsOMGeometry,xpsutil::lpwstr_wrapper,win_dox::geometry_compare,std::allocator<std::pair<win_dox::XpsOMGeometry const,xpsutil::lpwstr_wrapper>>,0>>(&v49);
      win_musl::XpsElementMarkupProducer::~XpsElementMarkupProducer((win_musl::XpsElementMarkupProducer *)pExceptionObject);
      win_musl::XpsElementMarkupProducer::~XpsElementMarkupProducer((win_musl::XpsElementMarkupProducer *)v55);
      v25 = (win_musl::XpsElementMarkupProducer *)v52;
    }
    win_musl::XpsElementMarkupProducer::~XpsElementMarkupProducer(v25);
    v28 = pv;
  }
  else
  {
    win_dox::SendDictionary<win_dox::XpsOMPage,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::FixedPageBodyMarkupProducer>(
      (unsigned int)&v45,
      *((_QWORD *)a1 + 1),
      a2,
      *((_QWORD *)a1 + 2),
      0);
    v29 = *((_QWORD *)a1 + 2);
    v30 = win_dox::XpsOMPage::GetVisuals(a2, v44);
    LOBYTE(v42) = 0;
    v43[0] = 0;
    v52[0] = &v45;
    v52[1] = *((_QWORD *)a1 + 1);
    v52[2] = &win_musl::FixedPageBodyMarkupProducer::AddGlyphs;
    v52[3] = &win_musl::FixedPageBodyMarkupProducer::AddPath;
    v52[4] = win_musl::FixedPageBodyMarkupProducer::AddCanvas;
    v52[5] = v29;
    v52[6] = &v44[1];
    v53 = v42;
    v54 = 0;
    v49 = v30;
    v50 = 0;
    v51 = 0;
    win_dox::XpsOMIterator<win_dox::XpsOMInterfaceCollection<IXpsOMVisualCollection>,win_dox::XpsOMVisual>::MoveNext(&v49);
    v42 = 0;
    LODWORD(v43[0]) = -1;
    *(_OWORD *)&v43[1] = 0;
    while ( v50 != -1 )
    {
      v31 = win_dox::XpsOMIterator<win_dox::XpsOMInterfaceCollection<IXpsOMSignatureBlockResourceCollection>,win_dox::XpsOMSignatureBlockResource>::operator*(&v49);
      win_dox::QueryInterfaceAndVisit<win_mp_lib::type_list<IXpsOMGlyphs,win_mp_lib::type_list<IXpsOMPath,win_mp_lib::type_list<IXpsOMCanvas,win_mp_lib::null_type>>>,win_dox::VisualAdder<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::FixedPageBodyMarkupProducer>,win_dox::XpsOMVisual>::operator()(
        v32,
        v52,
        v31);
      win_dox::XpsOMIterator<win_dox::XpsOMInterfaceCollection<IXpsOMVisualCollection>,win_dox::XpsOMVisual>::MoveNext(&v49);
    }
    win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v43[1]);
    win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v51);
    v28 = (LPVOID)v44[0];
  }
  if ( v28 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
  win_dox::consumption_helper::XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>::~XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>((win_dox::OpcUri *)v46);
  std::_Tree_val<std::_Tree_simple_types<xpsutil::lpwstr_wrapper>>::_Erase_tree<std::allocator<std::_Tree_node<xpsutil::lpwstr_wrapper,void *>>>(
    &v44[1],
    &v44[1],
    *(_QWORD *)(v44[1] + 8LL));
  return std::_Deallocate<16>(v44[1], 40);
}

```

## disassembly

```asm
0x180028ed8  mov     rax, rsp
0x180028edb  mov     [rax+18h], rbx
0x180028edf  push    rbp
0x180028ee0  push    rsi
0x180028ee1  push    rdi
0x180028ee2  lea     rbp, [rax-188h]
0x180028ee9  sub     rsp, 270h
0x180028ef0  movaps  xmmword ptr [rax-28h], xmm6
0x180028ef4  mov     rax, cs:__security_cookie
0x180028efb  xor     rax, rsp
0x180028efe  mov     [rbp+180h+var_30], rax
0x180028f05  mov     rsi, rdx
0x180028f08  mov     rdi, rcx
0x180028f0b  xor     eax, eax
0x180028f0d  mov     qword ptr [rsp+280h+var_238], rax
0x180028f12  xor     edx, edx; perrinfo
0x180028f14  xor     ecx, ecx; dwReserved
0x180028f16  call    cs:__imp_SetErrorInfo
0x180028f1c  mov     rcx, [rsi+8]
0x180028f20  mov     rax, [rcx]
0x180028f23  lea     rdx, [rsp+280h+var_238]
0x180028f28  mov     rax, [rax+38h]
0x180028f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f31  test    eax, eax
0x180028f33  jns     short loc_180028F3D
0x180028f35  mov     ecx, eax; this
0x180028f37  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
0x180028f3d  xorps   xmm0, xmm0
0x180028f40  movups  [rbp+180h+var_1C8], xmm0
0x180028f44  xor     edx, edx; perrinfo
0x180028f46  xor     ecx, ecx; dwReserved
0x180028f48  call    cs:__imp_SetErrorInfo
0x180028f4e  mov     rcx, [rsi+8]
0x180028f52  mov     rax, [rcx]
0x180028f55  lea     rdx, [rbp+180h+var_1C8]
0x180028f59  mov     rax, [rax+58h]
0x180028f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f62  test    eax, eax
0x180028f64  jns     short loc_180028F6E
0x180028f66  mov     ecx, eax; this
0x180028f68  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
0x180028f6e  xorps   xmm0, xmm0
0x180028f71  movups  [rbp+180h+var_1D8], xmm0
0x180028f75  xor     edx, edx; perrinfo
0x180028f77  xor     ecx, ecx; dwReserved
0x180028f79  call    cs:__imp_SetErrorInfo
0x180028f7f  mov     rcx, [rsi+8]
0x180028f83  mov     rax, [rcx]
0x180028f86  lea     rdx, [rbp+180h+var_1D8]
0x180028f8a  mov     rax, [rax+48h]
0x180028f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f93  test    eax, eax
0x180028f95  jns     short loc_180028F9F
0x180028f97  mov     ecx, eax; this
0x180028f99  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
0x180028f9f  xorps   xmm6, xmm6
0x180028fa2  movss   xmm3, dword ptr [rbp+180h+var_1C8+8]
0x180028fa7  comiss  xmm6, xmm3
0x180028faa  ja      loc_180029688
0x180028fb0  movss   xmm4, dword ptr [rbp+180h+var_1C8+0Ch]
0x180028fb5  comiss  xmm6, xmm4
0x180028fb8  ja      loc_180029688
0x180028fbe  movss   xmm1, dword ptr [rbp+180h+var_1C8]
0x180028fc3  comiss  xmm6, xmm1
0x180028fc6  jb      loc_180029688
0x180028fcc  movss   xmm0, dword ptr [rbp+180h+var_1C8+4]
0x180028fd1  comiss  xmm6, xmm0
0x180028fd4  jb      loc_180029688
0x180028fda  comiss  xmm6, xmm3
0x180028fdd  ja      loc_18002961E
0x180028fe3  comiss  xmm6, xmm4
0x180028fe6  ja      loc_18002961E
0x180028fec  movdqa  xmm5, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180028ff4  andps   xmm1, xmm5
0x180028ff7  movss   xmm2, dword ptr [rsp+280h+var_238]
0x180028ffd  addss   xmm1, xmm2
0x180029001  comiss  xmm3, xmm1
0x180029004  jb      loc_18002961E
0x18002900a  andps   xmm0, xmm5
0x18002900d  movss   xmm1, dword ptr [rsp+280h+var_238+4]
0x180029013  addss   xmm0, xmm1
0x180029017  comiss  xmm4, xmm0
0x18002901a  jb      loc_18002961E
0x180029020  comiss  xmm6, dword ptr [rbp+180h+var_1D8]
0x180029024  ja      loc_1800295B4
0x18002902a  comiss  xmm6, dword ptr [rbp+180h+var_1D8+4]
0x18002902e  ja      loc_1800295B4
0x180029034  comiss  xmm6, dword ptr [rbp+180h+var_1D8+8]
0x180029038  ja      loc_1800295B4
0x18002903e  comiss  xmm6, dword ptr [rbp+180h+var_1D8+0Ch]
0x180029042  ja      loc_1800295B4
0x180029048  subss   xmm2, dword ptr [rbp+180h+var_1D8]
0x18002904d  comiss  xmm2, dword ptr [rbp+180h+var_1D8+8]
0x180029051  jb      loc_1800295B4
0x180029057  movaps  xmm0, xmm1
0x18002905a  subss   xmm0, dword ptr [rbp+180h+var_1D8+4]
0x18002905f  comiss  xmm0, dword ptr [rbp+180h+var_1D8+0Ch]
0x180029063  jb      loc_1800295B4
0x180029069  movss   dword ptr [rsp+280h+pv], xmm1
0x18002906f  lea     r8, [rsp+280h+pv]
0x180029074  lea     rdx, ?gc_height@Attribute@Xps@win_musl@@3QB_WB; "Height"
0x18002907b  mov     rcx, [rdi+8]
0x18002907f  call    ??$SetAttribute@M@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBM@Z; win_musl::XpsElementMarkupProducer::SetAttribute<float>(wchar_t const *,float const &)
0x180029084  movss   xmm0, dword ptr [rsp+280h+var_238]
0x18002908a  movss   dword ptr [rsp+280h+pv], xmm0
0x180029090  lea     r8, [rsp+280h+pv]
0x180029095  lea     rdx, ?gc_width@Attribute@Xps@win_musl@@3QB_WB; "Width"
0x18002909c  mov     rcx, [rdi+8]
0x1800290a0  call    ??$SetAttribute@M@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBM@Z; win_musl::XpsElementMarkupProducer::SetAttribute<float>(wchar_t const *,float const &)
0x1800290a5  movss   xmm0, dword ptr [rbp+180h+var_1D8]
0x1800290aa  ucomiss xmm0, xmm6
0x1800290ad  jp      short loc_1800290E1
0x1800290af  jnz     short loc_1800290E1
0x1800290b1  movss   xmm0, dword ptr [rbp+180h+var_1D8+4]
0x1800290b6  ucomiss xmm0, xmm6
0x1800290b9  jp      short loc_1800290E1
0x1800290bb  jnz     short loc_1800290E1
0x1800290bd  movss   xmm1, dword ptr [rsp+280h+var_238]
0x1800290c3  movss   xmm0, dword ptr [rbp+180h+var_1D8+8]
0x1800290c8  ucomiss xmm0, xmm1
0x1800290cb  jp      short loc_1800290E1
0x1800290cd  jnz     short loc_1800290E1
0x1800290cf  movss   xmm2, dword ptr [rsp+280h+var_238+4]
0x1800290d5  movss   xmm0, dword ptr [rbp+180h+var_1D8+0Ch]
0x1800290da  ucomiss xmm0, xmm2
0x1800290dd  jp      short loc_1800290E1
0x1800290df  jz      short loc_180029101
0x1800290e1  lea     r8, [rbp+180h+var_1D8]
0x1800290e5  lea     rdx, ?gc_contentBox@Attribute@Xps@win_musl@@3QB_WB; "ContentBox"
0x1800290ec  mov     rcx, [rdi+8]
0x1800290f0  call    ??$SetAttribute@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019@@@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019@@@Z; win_musl::XpsElementMarkupProducer::SetAttribute<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019>(wchar_t const *,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019 const &)
0x1800290f5  movss   xmm2, dword ptr [rsp+280h+var_238+4]
0x1800290fb  movss   xmm1, dword ptr [rsp+280h+var_238]
0x180029101  movss   xmm0, dword ptr [rbp+180h+var_1C8]
0x180029106  ucomiss xmm0, xmm6
0x180029109  jp      short loc_180029131
0x18002910b  jnz     short loc_180029131
0x18002910d  movss   xmm0, dword ptr [rbp+180h+var_1C8+4]
0x180029112  ucomiss xmm0, xmm6
0x180029115  jp      short loc_180029131
0x180029117  jnz     short loc_180029131
0x180029119  movss   xmm0, dword ptr [rbp+180h+var_1C8+8]
0x18002911e  ucomiss xmm0, xmm1
0x180029121  jp      short loc_180029131
0x180029123  jnz     short loc_180029131
0x180029125  movss   xmm0, dword ptr [rbp+180h+var_1C8+0Ch]
0x18002912a  ucomiss xmm0, xmm2
0x18002912d  jp      short loc_180029131
0x18002912f  jz      short loc_180029145
0x180029131  lea     r8, [rbp+180h+var_1C8]
0x180029135  lea     rdx, ?gc_bleedBox@Attribute@Xps@win_musl@@3QB_WB; "BleedBox"
0x18002913c  mov     rcx, [rdi+8]
0x180029140  call    ??$SetAttribute@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019@@@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019@@@Z; win_musl::XpsElementMarkupProducer::SetAttribute<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019>(wchar_t const *,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0019 const &)
0x180029145  xorps   xmm0, xmm0
0x180029148  movdqu  xmmword ptr [rsp+280h+var_210+8], xmm0
0x18002914e  lea     rcx, [rsp+280h+var_210+8]
0x180029153  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@V?$scope@PEAV?$UnknownOnly@VTXpsOMFontResource@xpsom@@V?$type_list@UIXpsOMFontResource@@V?$type_list@UIXpsOMFontProperties@win_dox@@V?$type_list@UIXpsOMResource@@V?$type_list@UIXpsOMPart@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@VXpsOMObject@xpsutil@@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@U?$less@V?$scope@PEAV?$UnknownOnly@VTXpsOMFontResource@xpsom@@V?$type_list@UIXpsOMFontResource@@V?$type_list@UIXpsOMFontProperties@win_dox@@V?$type_list@UIXpsOMResource@@V?$type_list@UIXpsOMPart@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@VXpsOMObject@xpsutil@@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@std@@V?$allocator@V?$scope@PEAV?$UnknownOnly@VTXpsOMFontResource@xpsom@@V?$type_list@UIXpsOMFontResource@@V?$type_list@UIXpsOMFontProperties@win_dox@@V?$type_list@UIXpsOMResource@@V?$type_list@UIXpsOMPart@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@VXpsOMObject@xpsutil@@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<win_scope::scope<win_musl::UnknownOnly<xpsom::TXpsOMFontResource,win_mp_lib::type_list<IXpsOMFontResource,win_mp_lib::type_list<win_dox::IXpsOMFontProperties,win_mp_lib::type_list<IXpsOMResource,win_mp_lib::type_list<IXpsOMPart,win_mp_lib::null_type>>>>,xpsutil::XpsOMObject> *,win_scope::const_policies<win_scope::com_policies>>,std::less<win_scope::scope<win_musl::UnknownOnly<xpsom::TXpsOMFontResource,win_mp_lib::type_list<IXpsOMFontResource,win_mp_lib::type_list<win_dox::IXpsOMFontProperties,win_mp_lib::type_list<IXpsOMResource,win_mp_lib::type_list<IXpsOMPart,win_mp_lib::null_type>>>>,xpsutil::XpsOMObject> *,win_scope::const_policies<win_scope::com_policies>>>,std::allocator<win_scope::scope<win_musl::UnknownOnly<xpsom::TXpsOMFontResource,win_mp_lib::type_list<IXpsOMFontResource,win_mp_lib::type_list<win_dox::IXpsOMFontProperties,win_mp_lib::type_list<IXpsOMResource,win_mp_lib::type_list<IXpsOMPart,win_mp_lib::null_type>>>>,xpsutil::XpsOMObject> *,win_scope::const_policies<win_scope::com_policies>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180029158  nop
0x180029159  lea     rdx, [rsp+280h+pv]
0x18002915e  mov     rcx, rsi
0x180029161  call    ?GetName@XpsOMPage@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMPage::GetName(void)
0x180029166  nop
0x180029167  mov     r8, [rax]
0x18002916a  lea     rdx, [rsp+280h+var_210+8]
0x18002916f  mov     rcx, [rdi+8]
0x180029173  call    ??$SendName@VFixedPageBodyMarkupProducer@win_musl@@@win_dox@@YAXPEAVFixedPageBodyMarkupProducer@win_musl@@PEAV?$set@Vlpwstr_wrapper@xpsutil@@U?$less@Vlpwstr_wrapper@xpsutil@@@std@@V?$allocator@Vlpwstr_wrapper@xpsutil@@@4@@std@@PEB_W@Z; win_dox::SendName<win_musl::FixedPageBodyMarkupProducer>(win_musl::FixedPageBodyMarkupProducer *,std::set<xpsutil::lpwstr_wrapper> *,wchar_t const *)
0x180029178  nop
0x180029179  mov     rcx, [rsp+280h+pv]; pv
0x18002917e  test    rcx, rcx
0x180029181  jz      short loc_180029189
0x180029183  call    cs:__imp_CoTaskMemFree
0x180029189  lea     rdx, [rsp+280h+pv]
0x18002918e  mov     rcx, rsi
0x180029191  call    ?GetLanguage@XpsOMPage@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMPage::GetLanguage(void)
0x180029196  nop
0x180029197  mov     rdx, [rax]
0x18002919a  mov     rcx, [rdi+8]
0x18002919e  call    ??$SendLanguage@VFixedPageBodyMarkupProducer@win_musl@@@win_dox@@YAXPEAVFixedPageBodyMarkupProducer@win_musl@@PEB_W@Z; win_dox::SendLanguage<win_musl::FixedPageBodyMarkupProducer>(win_musl::FixedPageBodyMarkupProducer *,wchar_t const *)
0x1800291a3  nop
0x1800291a4  mov     rcx, [rsp+280h+pv]; pv
0x1800291a9  test    rcx, rcx
0x1800291ac  jz      short loc_1800291B4
0x1800291ae  call    cs:__imp_CoTaskMemFree
0x1800291b4  lea     rdx, [rsp+280h+var_238+8]
0x1800291b9  mov     rcx, rsi
0x1800291bc  call    ?GetPartName@XpsOMPart@win_dox@@QEBA?AVOpcPartUri@2@XZ; win_dox::XpsOMPart::GetPartName(void)
0x1800291c1  nop
0x1800291c2  mov     ecx, [rdi]
0x1800291c4  mov     [rbp+180h+var_1F8], ecx
0x1800291c7  mov     rdx, rax; struct win_dox::OpcPartUri *
0x1800291ca  lea     rcx, [rbp+180h+var_1F0]; this
0x1800291ce  call    ??0OpcPartUri@win_dox@@QEAA@AEBV01@@Z; win_dox::OpcPartUri::OpcPartUri(win_dox::OpcPartUri const &)
0x1800291d3  nop
0x1800291d4  mov     rcx, qword ptr [rsp+280h+var_228+8]
0x1800291d9  test    rcx, rcx
0x1800291dc  jz      short loc_1800291F3
0x1800291de  mov     rax, [rcx]
0x1800291e1  mov     rax, [rax+10h]
0x1800291e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291ea  mov     qword ptr [rsp+280h+var_228+8], 0
0x1800291f3  lea     rcx, [rsp+280h+var_238+8]; this
0x1800291f8  call    ??1OpcUri@win_dox@@QEAA@XZ; win_dox::OpcUri::~OpcUri(void)
0x1800291fd  cmp     byte ptr [rdi+18h], 0
0x180029201  jz      loc_180029430
0x180029207  lea     rdx, [rsp+280h+pv]
0x18002920c  mov     rcx, rsi
0x18002920f  call    ?GetDictionary@XpsOMPage@win_dox@@QEBA?AVXpsOMDictionary@2@XZ; win_dox::XpsOMPage::GetDictionary(void)
0x180029214  nop
0x180029215  lea     rdx, [rsp+280h+var_210]
0x18002921a  lea     rcx, [rsp+280h+pv]
0x18002921f  call    ?SetVersion@XpsOMCorePropertiesReceiver@xpsom@@QEAA?AVXpsOMVersionReceiver@2@XZ; xpsom::XpsOMCorePropertiesReceiver::SetVersion(void)
0x180029224  or      ebx, 0FFFFFFFFh
0x180029227  cmp     qword ptr [rax], 0
0x18002922b  cmovnz  ebx, cs:dword_180229438
0x180029232  mov     rcx, qword ptr [rsp+280h+var_210]
0x180029237  test    rcx, rcx
0x18002923a  jz      short loc_180029249
0x18002923c  mov     rax, [rcx]
0x18002923f  mov     rax, [rax+10h]
0x180029243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029248  nop
0x180029249  cmp     ebx, 0FFFFFFFFh
0x18002924c  jz      loc_18002935C
0x180029252  mov     byte ptr [rsp+280h+var_260], 1
0x180029257  mov     r9, [rdi+10h]
0x18002925b  mov     r8, rsi
0x18002925e  mov     rdx, [rdi+8]
0x180029262  lea     rcx, [rbp+180h+var_1F8]
0x180029266  call    ??$SendDictionary@VXpsOMPage@win_dox@@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VFixedPageBodyMarkupProducer@4@@win_dox@@YAXAEBVMarkupSenderContext@0@PEAVFixedPageBodyMarkupProducer@win_musl@@AEBVXpsOMPage@0@PEAV?$set@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@U?$less@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@V?$allocator@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@3@@std@@_N@Z; win_dox::SendDictionary<win_dox::XpsOMPage,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::FixedPageBodyMarkupProducer>(win_dox::MarkupSenderContext const &,win_musl::FixedPageBodyMarkupProducer *,win_dox::XpsOMPage const &,std::set<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>> *,bool)
0x18002926b  lea     rdx, [rbp+180h+var_190]
0x18002926f  mov     rcx, [rdi+8]
0x180029273  call    ?AddCanvas@FixedPageBodyMarkupProducer@win_musl@@QEAA?AVCanvasMarkupProducer@2@XZ; win_musl::FixedPageBodyMarkupProducer::AddCanvas(void)
0x180029278  nop
0x180029279  lea     r8, ?gc_canvasResources@Element@Xps@win_musl@@3QB_WB; "Canvas.Resources"
0x180029280  lea     rdx, [rbp+180h+var_130]
0x180029284  lea     rcx, [rbp+180h+var_190]
0x180029288  call    ??$AddChildElementWithContext@VResourcesMarkupProducer@win_musl@@@XpsElementMarkupProducer@win_musl@@IEAA?AVResourcesMarkupProducer@1@PEB_W@Z; win_musl::XpsElementMarkupProducer::AddChildElementWithContext<win_musl::ResourcesMarkupProducer>(wchar_t const *)
0x18002928d  nop
0x18002928e  lea     rdx, [rbp+180h+pExceptionObject]
0x180029295  lea     rcx, [rbp+180h+var_130]
0x180029299  call    ??$AddChildElementWithContext@VResourceDictionaryMarkupProducer@win_musl@@@XpsElementMarkupProducer@win_musl@@IEAA?AVResourceDictionaryMarkupProducer@1@XZ; win_musl::XpsElementMarkupProducer::AddChildElementWithContext<win_musl::ResourceDictionaryMarkupProducer>(void)
0x18002929e  nop
0x18002929f  lea     r8, [rbp+180h+pExceptionObject]
0x1800292a6  mov     rdx, rsi
0x1800292a9  lea     rcx, [rbp+180h+var_1B8]
0x1800292ad  call    ??0?$ResourceFinder@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@win_dox@@QEAA@AEBVXpsOMPage@1@PEAVResourceDictionaryMarkupProducer@win_musl@@@Z; win_dox::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>(win_dox::XpsOMPage const &,win_musl::ResourceDictionaryMarkupProducer *)
0x1800292b2  nop
0x1800292b3  lea     rcx, [rbp+180h+var_130]; this
0x1800292b7  call    ?Close@XpsElementMarkupProducer@win_musl@@QEAAXXZ; win_musl::XpsElementMarkupProducer::Close(void)
0x1800292bc  mov     rbx, [rdi+10h]
0x1800292c0  lea     rdx, [rsp+280h+var_210]
0x1800292c5  mov     rcx, rsi
0x1800292c8  call    ?GetVisuals@XpsOMPage@win_dox@@QEBA?AV?$XpsOMResourceCollection@UIXpsOMVisualCollection@@@2@XZ; win_dox::XpsOMPage::GetVisuals(void)
0x1800292cd  nop
0x1800292ce  mov     byte ptr [rsp+280h+var_238+8], 1
0x1800292d3  mov     ecx, dword ptr [rsp+280h+var_238+9]
0x1800292d7  mov     dword ptr [rsp+280h+var_238+9], ecx
0x1800292db  movzx   ecx, word ptr [rsp+280h+var_238+0Dh]
0x1800292e0  mov     word ptr [rsp+280h+var_238+0Dh], cx
0x1800292e5  mov     cl, byte ptr [rsp+280h+var_238+0Fh]
0x1800292e9  mov     byte ptr [rsp+280h+var_238+0Fh], cl
0x1800292ed  lea     rcx, [rbp+180h+var_1B8]
0x1800292f1  mov     qword ptr [rsp+280h+var_228], rcx
0x1800292f6  lea     rcx, [rsp+280h+var_238+8]
0x1800292fb  mov     qword ptr [rsp+280h+var_258], rcx
0x180029300  lea     rcx, [rsp+280h+var_210+8]
0x180029305  mov     qword ptr [rsp+280h+var_260], rcx
0x18002930a  mov     r9, rbx
0x18002930d  mov     r8, rax
0x180029310  lea     rdx, [rbp+180h+var_190]
0x180029314  lea     rcx, [rbp+180h+var_1F8]
0x180029318  call    ??$SendVisualCollection@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VCanvasMarkupProducer@2@@win_dox@@YAXAEBVMarkupSenderContext@0@PEAVCanvasMarkupProducer@win_musl@@AEBV?$XpsOMResourceCollection@UIXpsOMVisualCollection@@@0@PEAV?$set@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@U?$less@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@V?$allocator@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@3@@std@@PEAV?$set@Vlpwstr_wrapper@xpsutil@@U?$less@Vlpwstr_wrapper@xpsutil@@@std@@V?$allocator@Vlpwstr_wrapper@xpsutil@@@4@@6@V?$OptimizerSettings@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@0@@Z; win_dox::SendVisualCollection<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(win_dox::MarkupSenderContext const &,win_musl::CanvasMarkupProducer *,win_dox::XpsOMResourceCollection<IXpsOMVisualCollection> const &,std::set<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>> *,std::set<xpsutil::lpwstr_wrapper> *,win_dox::OptimizerSettings<win_musl::PageBodyReceiverTraitsOnMarkupProducer>)
0x18002931d  nop
0x18002931e  lea     rcx, [rsp+280h+var_210]; this
0x180029323  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x180029328  lea     rcx, [rbp+180h+var_190]; this
0x18002932c  call    ?Close@XpsElementMarkupProducer@win_musl@@QEAAXXZ; win_musl::XpsElementMarkupProducer::Close(void)
0x180029331  nop
0x180029332  lea     rcx, [rbp+180h+var_1B8]
0x180029336  call    ??1?$_Tree@V?$_Tmap_traits@VXpsOMGeometry@win_dox@@Vlpwstr_wrapper@xpsutil@@Ugeometry_compare@2@V?$allocator@U?$pair@$$CBVXpsOMGeometry@win_dox@@Vlpwstr_wrapper@xpsutil@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<win_dox::XpsOMGeometry,xpsutil::lpwstr_wrapper,win_dox::geometry_compare,std::allocator<std::pair<win_dox::XpsOMGeometry const,xpsutil::lpwstr_wrapper>>,0>>::~_Tree<std::_Tmap_traits<win_dox::XpsOMGeometry,xpsutil::lpwstr_wrapper,win_dox::geometry_compare,std::allocator<std::pair<win_dox::XpsOMGeometry const,xpsutil::lpwstr_wrapper>>,0>>(void)
0x18002933b  nop
0x18002933c  lea     rcx, [rbp+180h+pExceptionObject]; this
0x180029343  call    ??1XpsElementMarkupProducer@win_musl@@QEAA@XZ; win_musl::XpsElementMarkupProducer::~XpsElementMarkupProducer(void)
0x180029348  nop
0x180029349  lea     rcx, [rbp+180h+var_130]; this
0x18002934d  call    ??1XpsElementMarkupProducer@win_musl@@QEAA@XZ; win_musl::XpsElementMarkupProducer::~XpsElementMarkupProducer(void)
0x180029352  nop
0x180029353  lea     rcx, [rbp+180h+var_190]
0x180029357  jmp     loc_180029420
0x18002935c  lea     rdx, [rbp+180h+var_130]
0x180029360  mov     rcx, [rdi+8]
0x180029364  call    ?SetResources@FixedPageBodyMarkupProducer@win_musl@@QEAA?AVResourcesMarkupProducer@2@XZ; win_musl::FixedPageBodyMarkupProducer::SetResources(void)
0x180029369  nop
0x18002936a  lea     rdx, [rbp+180h+pExceptionObject]
0x180029371  lea     rcx, [rbp+180h+var_130]
0x180029375  call    ??$AddChildElementWithContext@VResourceDictionaryMarkupProducer@win_musl@@@XpsElementMarkupProducer@win_musl@@IEAA?AVResourceDictionaryMarkupProducer@1@XZ; win_musl::XpsElementMarkupProducer::AddChildElementWithContext<win_musl::ResourceDictionaryMarkupProducer>(void)
0x18002937a  nop
0x18002937b  lea     r8, [rbp+180h+pExceptionObject]
0x180029382  mov     rdx, rsi
0x180029385  lea     rcx, [rbp+180h+var_1B8]
  ... truncated ...
```
