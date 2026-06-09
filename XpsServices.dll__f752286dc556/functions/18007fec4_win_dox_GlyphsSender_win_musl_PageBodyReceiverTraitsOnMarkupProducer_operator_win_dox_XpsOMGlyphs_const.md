# win_dox::GlyphsSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::operator()(win_dox::XpsOMGlyphs const &)

- ea: `0x18007fec4`
- end: `0x18008058a`
- name: `??R?$GlyphsSender@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@win_dox@@QEAAXAEBVXpsOMGlyphs@1@@Z`
- size: `1734`
- prototype: ``
- caller_count: `1`
- callee_count: `56`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004fa94`

## callees

- `0x18000b828`
- `0x18000bdec`
- `0x18000c1f8`
- `0x18000c480`
- `0x18000c5a0`
- `0x18000c7b0`
- `0x18000cb80`
- `0x180012450`
- `0x18001befc`
- `0x18001bfbc`
- `0x18001dc2c`
- `0x18001de3c`
- `0x18001df74`
- `0x18001e6c0`
- `0x180020814`
- `0x180021e94`
- `0x18002484c`
- `0x18002bfb8`
- `0x18002cd88`
- `0x18002d034`
- `0x18003c7f8`
- `0x18004ddd0`
- `0x18007fe2c`
- `0x18007fec4`
- `0x180080590`
- `0x1800805ec`
- `0x180080648`
- `0x1800810e4`
- `0x1800812dc`
- `0x180081330`
- `0x180081380`
- `0x1800813d0`
- `0x180081420`
- `0x180081894`
- `0x1800a7a00`
- `0x1800b76e8`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c1178`
- `0x1800c20c4`
- `0x1800c23cc`
- `0x1800c2680`
- `0x1800c4d4c`
- `0x1800cd1bc`
- `0x1800d4154`
- `0x1800d6bd8`
- `0x1800d6d34`
- `0x1800d70fc`
- `0x1801016e8`
- `0x180102004`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18007ffae`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18007ffae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080325`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800804d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080526`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080535`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080325`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800804d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080526`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080535`

## string_xrefs

- `0x180080178`: `FontRenderingEmSize`
- `0x1800801f0`: `IsSideways`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall win_dox::GlyphsSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::operator()(
        __int64 *a1,
        win_dox::XpsOMGlyphs *a2)
{
  int v4; // ebx
  unsigned int FontFaceIndex; // edi
  __int64 v6; // rbx
  __int64 PartName; // rax
  __int64 v8; // r8
  __int64 v9; // rbx
  void *v10; // rdi
  win_musl::Formatter *v11; // rax
  const wchar_t *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rdx
  void *v20; // rbx
  win_musl::Formatter *v21; // rax
  const wchar_t *v22; // rax
  _QWORD *DeviceFontName; // rax
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 HyperlinkNavigateUri; // rax
  int v31; // r15d
  __int64 v32; // rax
  _QWORD *AbsoluteUri; // rax
  _QWORD *Language; // rax
  __int64 v35; // rdx
  int v36[2]; // [rsp+28h] [rbp-D8h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  char v38[8]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v39[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+74h] [rbp-8Ch]
  _BYTE v42[16]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h]
  LPVOID v44; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v45; // [rsp+98h] [rbp-68h] BYREF
  int v46[2]; // [rsp+A0h] [rbp-60h] BYREF
  win_musl::GlyphsMarkupProducer *v47; // [rsp+A8h] [rbp-58h]
  int v48[6]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h]
  char v50; // [rsp+D8h] [rbp-28h]
  void *v51; // [rsp+D9h] [rbp-27h]
  int v52; // [rsp+E1h] [rbp-1Fh]
  __int16 v53; // [rsp+E5h] [rbp-1Bh]
  char v54; // [rsp+E7h] [rbp-19h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  char v56; // [rsp+100h] [rbp+0h]
  char v57; // [rsp+102h] [rbp+2h]
  char v58; // [rsp+108h] [rbp+8h]
  _BYTE Src[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v61[80]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v62[160]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v63[2]; // [rsp+240h] [rbp+140h] BYREF

  win_dox::XpsOMGlyphs::GetFontResource(a2, v42);
  v4 = -1;
  if ( *(_QWORD *)win_dox::XpsPageRelationshipReceiver::GetInterface(v42, &pv) )
    v4 = dword_180229460;
  if ( pv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  if ( v4 != -1 )
  {
    FontFaceIndex = win_dox::XpsOMGlyphs::GetFontFaceIndex(a2);
    v6 = *a1;
    PartName = win_dox::XpsOMPart::GetPartName(v42, v39);
    win_dox::MarkupSenderContext::GetPartRef(v6, Src, PartName);
    win_dox::consumption_helper::XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>::~XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>((win_dox::OpcUri *)v39);
    if ( (FontFaceIndex & 0x8000u) == 0 )
    {
      memset(v63, 0, sizeof(v63));
      if ( (unsigned int)_o__itow_s(FontFaceIndex, v63, 16) )
      {
        win_musl::DebugLogHelper("(no filename)", &::Src, 2299, 1024, -2147418113, L"Unexpected failure in _itow_s!");
        std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Program has entered an unexpected state");
        throw (std::logic_error *)pExceptionObject;
      }
      std::wstring::_Append<wchar_t>(Src);
      v8 = -1;
      do
        ++v8;
      while ( *((_WORD *)v63 + v8) );
      std::wstring::_Append<wchar_t>(Src);
    }
    win_musl::GlyphsMarkupProducer::SetFontUri(a1[1], Src);
    v9 = a1[2];
    if ( v9 )
    {
      pExceptionObject[24] = 4;
      win_dox::XpsOMSignatureBlockResource::XpsOMSignatureBlockResource(
        (win_dox::XpsOMSignatureBlockResource *)pExceptionObject,
        (const struct win_dox::XpsOMSignatureBlockResource *)v42);
      std::_Tree<std::_Tset_traits<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>,std::less<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>>,std::allocator<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>>,0>>::insert<0,0>(
        v9,
        v39,
        pExceptionObject);
      dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>((win_dox::XpsOMSolidColorBrush *)pExceptionObject);
    }
    std::wstring::_Tidy_deallocate(Src);
  }
  win_dox::XpsOMGlyphs::GetUnicodeString(a2, &v44);
  v10 = v44;
  if ( !v44 && !win_dox::XpsOMGlyphs::GetGlyphIndexCount(a2) )
  {
    std::wstring::wstring(Src, L"Either UnicodeString or GlyphIndices must be present");
    v11 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v61, Src);
    v12 = win_musl::Formatter::c_str(v11);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)v62,
      0x910u,
      -2142109438,
      (__int64)v12);
    throw (SplException::THResultException *)v62;
  }
  win_dox::SendString<win_musl::GlyphsMarkupProducer>(a1[1], win_musl::GlyphsMarkupProducer::SetUnicodeString, v10);
  win_dox::SendGlyphIndices<win_musl::GlyphsMarkupProducer>(a1[1], a2);
  v13 = a1[1];
  LODWORD(pv) = win_dox::XpsOMGlyphs::GetBidiLevel(a2);
  if ( (_DWORD)pv )
    win_musl::XpsElementMarkupProducer::SetAttribute<unsigned int>(v13, v14, &pv);
  v15 = a1[1];
  LODWORD(pv) = win_dox::XpsOMGlyphs::GetFontRenderingEmSize(a2);
  win_musl::XpsElementMarkupProducer::SetAttribute<float>(v15, L"FontRenderingEmSize", &pv);
  win_dox::XpsOMGlyphs::GetOrigin(a2);
  LODWORD(pv) = v40;
  win_musl::XpsElementMarkupProducer::SetAttribute<float>(a1[1], L"OriginX", &pv);
  LODWORD(pv) = v41;
  win_musl::XpsElementMarkupProducer::SetAttribute<float>(a1[1], L"OriginY", &pv);
  v16 = a1[1];
  if ( (unsigned int)win_dox::XpsOMGlyphs::GetIsSideways(a2) )
  {
    v38[0] = 1;
    win_musl::XpsElementMarkupProducer::SetAttribute<bool>(v16, L"IsSideways", v38);
  }
  v17 = a1[1];
  LODWORD(pv) = win_dox::XpsOMVisual::GetOpacity(a2);
  if ( *(float *)&pv != 1.0 )
    win_musl::XpsElementMarkupProducer::SetAttribute<float>(v17, L"Opacity", &pv);
  v18 = a1[1];
  LODWORD(pv) = win_dox::XpsOMGlyphs::GetStyleSimulations(a2);
  if ( (_DWORD)pv != 1 )
    win_musl::XpsElementMarkupProducer::SetAttribute<enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0004>(
      v18,
      v19,
      &pv);
  win_dox::XpsOMVisual::GetName(a2, &v45);
  v20 = v45;
  if ( v45 && dword_180229818 != -1 )
  {
    if ( a1[4] )
    {
      std::wstring::wstring(Src, L"Name set for item in dictionary");
      v21 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v61, Src);
      v22 = win_musl::Formatter::c_str(v21);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)v62,
        0x935u,
        -2142108671,
        (__int64)v22);
      throw (SplException::THResultException *)v62;
    }
    win_dox::SendName<win_musl::PathMarkupProducer>(a1[1], a1[3], v45);
  }
  DeviceFontName = (_QWORD *)win_dox::XpsOMGlyphs::GetDeviceFontName(a2, &pv);
  win_dox::SendString<win_musl::GlyphsMarkupProducer>(
    a1[1],
    win_musl::GlyphsMarkupProducer::SetDeviceFontName,
    *DeviceFontName);
  if ( pv )
    CoTaskMemFree(pv);
  win_dox::SendCaretStops<win_musl::GlyphsMarkupProducer>(a1[1], a2);
  *(_OWORD *)v39 = *(_OWORD *)(a1 + 5);
  *(_QWORD *)v36 = a1[3];
  win_dox::GlyphsAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::GlyphsAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>(
    v46,
    *a1,
    a1[1],
    a2,
    a1[2]);
  v58 = win_dox::CheckSendAttrBrush<win_dox::XpsOMGlyphs,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::GlyphsMarkupProducer>(
          v46[0],
          (int)v48,
          v24,
          v25,
          v47,
          v36[0],
          v49,
          v50);
  v56 = win_dox::CheckSendAttrTransform<win_dox::XpsOMCanvas,win_musl::CanvasMarkupProducer>(v48, v26, v27, v47);
  LOBYTE(v39[0]) = v50;
  *(LPVOID *)((char *)v39 + 1) = v51;
  *(_DWORD *)((char *)&v39[1] + 1) = v52;
  *(_WORD *)((char *)&v39[1] + 5) = v53;
  HIBYTE(v39[1]) = v54;
  v57 = win_dox::CheckSendAttrGeometry<win_dox::XpsOMGlyphs,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::GlyphsMarkupProducer>(
          v48,
          v28,
          v29,
          v47);
  win_dox::VisualAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer,win_dox::XpsOMPath>::CheckSendAttrOpacityMask(v46);
  HyperlinkNavigateUri = win_dox::XpsOMVisual::GetHyperlinkNavigateUri(a2, v39);
  v31 = -1;
  if ( *(_QWORD *)xpsom::XpsOMCorePropertiesReceiver::SetVersion(HyperlinkNavigateUri, &pv) )
    v31 = dword_180229818;
  if ( pv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    pv = 0;
  }
  if ( v39[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39[0] + 16LL))(v39[0]);
  if ( v31 != -1 )
  {
    v32 = win_dox::XpsOMVisual::GetHyperlinkNavigateUri(a2, v39);
    AbsoluteUri = (_QWORD *)win_dox::Uri::GetAbsoluteUri(v32, Src);
    if ( AbsoluteUri[3] > 7u )
      AbsoluteUri = (_QWORD *)*AbsoluteUri;
    win_dox::SendString<win_musl::GlyphsMarkupProducer>(
      a1[1],
      win_musl::PathMarkupProducer::SetNavigateUri,
      AbsoluteUri);
    std::wstring::_Tidy_deallocate(Src);
    if ( v39[0] )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39[0] + 16LL))(v39[0]);
  }
  Language = (_QWORD *)win_dox::XpsOMVisual::GetLanguage(a2, v39);
  win_dox::SendLanguage<win_musl::GlyphsMarkupProducer>(a1[1], *Language);
  if ( v39[0] )
    CoTaskMemFree(v39[0]);
  win_dox::SendKey<win_musl::GlyphsMarkupProducer>(a1[1], a1[4]);
  if ( !v57 )
    win_dox::CheckSendElemGeometry<win_dox::XpsOMCanvas,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(
      v48,
      v35,
      v47,
      v55);
  win_dox::VisualAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::GlyphsMarkupProducer,win_dox::XpsOMGlyphs>::CheckSendElemOpacityMask(v46);
  win_dox::GlyphsAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::CheckSendElemFill(v46);
  win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v48);
  if ( v20 )
    CoTaskMemFree(v20);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)v42);
}

```

## disassembly

```asm
0x18007fec4  mov     [rsp-8+arg_10], rbx
0x18007fec9  mov     [rsp-8+arg_18], rsi
0x18007fece  push    rbp
0x18007fecf  push    rdi
0x18007fed0  push    r12
0x18007fed2  push    r14
0x18007fed4  push    r15
0x18007fed6  lea     rbp, [rsp-170h]
0x18007fede  sub     rsp, 270h
0x18007fee5  mov     rax, cs:__security_cookie
0x18007feec  xor     rax, rsp
0x18007feef  mov     [rbp+190h+var_30], rax
0x18007fef6  mov     r14, rdx
0x18007fef9  mov     rsi, rcx
0x18007fefc  xor     r12d, r12d
0x18007feff  lea     rdx, [rsp+290h+var_218]
0x18007ff04  mov     rcx, r14
0x18007ff07  call    ?GetFontResource@XpsOMGlyphs@win_dox@@QEBA?AVXpsOMFontResource@2@XZ; win_dox::XpsOMGlyphs::GetFontResource(void)
0x18007ff0c  nop
0x18007ff0d  lea     rdx, [rsp+290h+pv]
0x18007ff12  lea     rcx, [rsp+290h+var_218]
0x18007ff17  call    ?GetInterface@XpsPageRelationshipReceiver@win_dox@@QEBA?AV?$scope@PEAUIXpsPageRelationshipReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsPageRelationshipReceiver::GetInterface(void)
0x18007ff1c  or      ebx, 0FFFFFFFFh
0x18007ff1f  cmp     [rax], r12
0x18007ff22  cmovnz  ebx, cs:dword_180229460
0x18007ff29  mov     rcx, [rsp+290h+pv]
0x18007ff2e  test    rcx, rcx
0x18007ff31  jz      short loc_18007FF40
0x18007ff33  mov     rax, [rcx]
0x18007ff36  mov     rax, [rax+10h]
0x18007ff3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ff3f  nop
0x18007ff40  cmp     ebx, 0FFFFFFFFh
0x18007ff43  jz      loc_180080095
0x18007ff49  mov     rcx, r14; this
0x18007ff4c  call    ?GetFontFaceIndex@XpsOMGlyphs@win_dox@@QEBAFXZ; win_dox::XpsOMGlyphs::GetFontFaceIndex(void)
0x18007ff51  movsx   edi, ax
0x18007ff54  mov     rbx, [rsi]
0x18007ff57  lea     rdx, [rsp+290h+var_240]
0x18007ff5c  lea     rcx, [rsp+290h+var_218]
0x18007ff61  call    ?GetPartName@XpsOMPart@win_dox@@QEBA?AVOpcPartUri@2@XZ; win_dox::XpsOMPart::GetPartName(void)
0x18007ff66  nop
0x18007ff67  mov     r8, rax
0x18007ff6a  lea     rdx, [rbp+190h+Src]
0x18007ff6e  mov     rcx, rbx
0x18007ff71  call    ?GetPartRef@MarkupSenderContext@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVOpcPartUri@2@@Z; win_dox::MarkupSenderContext::GetPartRef(win_dox::OpcPartUri const &)
0x18007ff76  nop
0x18007ff77  lea     rcx, [rsp+290h+var_240]; this
0x18007ff7c  call    ??1?$XpsDocumentRelationshipSender@VXpsProducerConsumptionClientTraits@xps_production@win_dox@@@consumption_helper@win_dox@@QEAA@XZ; win_dox::consumption_helper::XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>::~XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>(void)
0x18007ff81  test    di, di
0x18007ff84  js      loc_180080047
0x18007ff8a  xorps   xmm0, xmm0
0x18007ff8d  movups  [rbp+190h+var_50], xmm0
0x18007ff94  movups  [rbp+190h+var_40], xmm0
0x18007ff9b  mov     ecx, edi
0x18007ff9d  mov     r9d, 0Ah
0x18007ffa3  lea     r8d, [r9+6]
0x18007ffa7  lea     rdx, [rbp+190h+var_50]
0x18007ffae  call    cs:__imp__o__itow_s
0x18007ffb4  test    eax, eax
0x18007ffb6  jz      short loc_18008000C
0x18007ffb8  lea     rax, aUnexpectedFail; "Unexpected failure in _itow_s!"
0x18007ffbf  mov     qword ptr [rsp+290h+var_268], rax
0x18007ffc4  mov     dword ptr [rsp+290h+var_270], 8000FFFFh
0x18007ffcc  mov     r9d, 400h
0x18007ffd2  mov     r8d, 8FBh
0x18007ffd8  lea     rdx, Src
0x18007ffdf  lea     rcx, aNoFilename; "(no filename)"
0x18007ffe6  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18007ffeb  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x18007fff2  lea     rcx, [rbp+190h+pExceptionObject]; this
0x18007fff6  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18007fffb  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180080002  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x180080006  call    _CxxThrowException_0
0x18008000c  mov     r8d, 1
0x180080012  lea     rdx, asc_1801ECF6C; "#"
0x180080019  lea     rcx, [rbp+190h+Src]; Src
0x18008001d  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180080022  lea     rax, [rbp+190h+var_50]
0x180080029  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008002d  inc     r8
0x180080030  cmp     [rax+r8*2], r12w
0x180080035  jnz     short loc_18008002D
0x180080037  lea     rdx, [rbp+190h+var_50]
0x18008003e  lea     rcx, [rbp+190h+Src]; Src
0x180080042  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180080047  lea     rdx, [rbp+190h+Src]
0x18008004b  mov     rcx, [rsi+8]
0x18008004f  call    ?SetFontUri@GlyphsMarkupProducer@win_musl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::GlyphsMarkupProducer::SetFontUri(std::wstring const &)
0x180080054  mov     rbx, [rsi+10h]
0x180080058  test    rbx, rbx
0x18008005b  jz      short loc_18008008C
0x18008005d  mov     [rbp+190h+var_148], 4
0x180080061  lea     rdx, [rsp+290h+var_218]; struct win_dox::XpsOMSignatureBlockResource *
0x180080066  lea     rcx, [rbp+190h+pExceptionObject]; this
0x18008006a  call    ??0XpsOMSignatureBlockResource@win_dox@@QEAA@AEBV01@@Z; win_dox::XpsOMSignatureBlockResource::XpsOMSignatureBlockResource(win_dox::XpsOMSignatureBlockResource const &)
0x18008006f  nop
0x180080070  lea     r8, [rbp+190h+pExceptionObject]
0x180080074  lea     rdx, [rsp+290h+var_240]
0x180080079  mov     rcx, rbx
0x18008007c  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@U?$less@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@V?$allocator@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@@std@@_N@1@$$QEAV?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@Z; std::_Tree<std::_Tset_traits<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>,std::less<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>>,std::allocator<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>>,0>>::insert<0,0>(dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>> &&)
0x180080081  nop
0x180080082  lea     rcx, [rbp+190h+pExceptionObject]; this
0x180080086  call    ??1?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>::~dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>(void)
0x18008008b  nop
0x18008008c  lea     rcx, [rbp+190h+Src]
0x180080090  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080095  lea     rdx, [rbp+190h+var_200]
0x180080099  mov     rcx, r14
0x18008009c  call    ?GetUnicodeString@XpsOMGlyphs@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMGlyphs::GetUnicodeString(void)
0x1800800a1  nop
0x1800800a2  mov     rdi, [rbp+190h+var_200]
0x1800800a6  test    rdi, rdi
0x1800800a9  jnz     short loc_180080121
0x1800800ab  mov     rcx, r14; this
0x1800800ae  call    ?GetGlyphIndexCount@XpsOMGlyphs@win_dox@@QEBAIXZ; win_dox::XpsOMGlyphs::GetGlyphIndexCount(void)
0x1800800b3  test    eax, eax
0x1800800b5  jnz     short loc_180080121
0x1800800b7  lea     rdx, aEitherUnicodes; "Either UnicodeString or GlyphIndices mu"...
0x1800800be  lea     rcx, [rbp+190h+Src]
0x1800800c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800800c7  nop
0x1800800c8  lea     rdx, [rbp+190h+Src]
0x1800800cc  lea     rcx, [rbp+190h+var_140]
0x1800800d0  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800800d5  nop
0x1800800d6  mov     rcx, rax; this
0x1800800d9  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800800de  mov     [rsp+290h+var_260], rax; __int64
0x1800800e3  mov     [rsp+290h+var_268], 80520102h; int
0x1800800eb  mov     dword ptr [rsp+290h+var_270], 910h; unsigned int
0x1800800f3  lea     r9, Src
0x1800800fa  lea     r8, Src
0x180080101  lea     rcx, [rbp+190h+var_F0]; this
0x180080108  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008010d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180080114  lea     rcx, [rbp+190h+var_F0]; pExceptionObject
0x18008011b  call    _CxxThrowException_0
0x180080121  mov     r8, rdi
0x180080124  lea     rdx, ?SetUnicodeString@GlyphsMarkupProducer@win_musl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::GlyphsMarkupProducer::SetUnicodeString(std::wstring const &)
0x18008012b  mov     rcx, [rsi+8]
0x18008012f  call    ??$SendString@VGlyphsMarkupProducer@win_musl@@@win_dox@@YAXPEAVGlyphsMarkupProducer@win_musl@@P812@EAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ZPEB_W@Z; win_dox::SendString<win_musl::GlyphsMarkupProducer>(win_musl::GlyphsMarkupProducer *,void (win_musl::GlyphsMarkupProducer::*)(std::wstring const &),wchar_t const *)
0x180080134  mov     rdx, r14
0x180080137  mov     rcx, [rsi+8]
0x18008013b  call    ??$SendGlyphIndices@VGlyphsMarkupProducer@win_musl@@@win_dox@@YAXPEAVGlyphsMarkupProducer@win_musl@@AEBVXpsOMGlyphs@0@@Z; win_dox::SendGlyphIndices<win_musl::GlyphsMarkupProducer>(win_musl::GlyphsMarkupProducer *,win_dox::XpsOMGlyphs const &)
0x180080140  mov     rbx, [rsi+8]
0x180080144  mov     rcx, r14; this
0x180080147  call    ?GetBidiLevel@XpsOMGlyphs@win_dox@@QEBAIXZ; win_dox::XpsOMGlyphs::GetBidiLevel(void)
0x18008014c  mov     dword ptr [rsp+290h+pv], eax
0x180080150  test    eax, eax
0x180080152  jz      short loc_180080161
0x180080154  lea     r8, [rsp+290h+pv]
0x180080159  mov     rcx, rbx
0x18008015c  call    ??$SetAttribute@I@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBI@Z; win_musl::XpsElementMarkupProducer::SetAttribute<uint>(wchar_t const *,uint const &)
0x180080161  mov     rbx, [rsi+8]
0x180080165  mov     rcx, r14; this
0x180080168  call    ?GetFontRenderingEmSize@XpsOMGlyphs@win_dox@@QEBAMXZ; win_dox::XpsOMGlyphs::GetFontRenderingEmSize(void)
0x18008016d  movss   dword ptr [rsp+290h+pv], xmm0
0x180080173  lea     r8, [rsp+290h+pv]
0x180080178  lea     rdx, ?gc_fontRenderingEmSize@Attribute@Xps@win_musl@@3QB_WB; "FontRenderingEmSize"
0x18008017f  mov     rcx, rbx
0x180080182  call    ??$SetAttribute@M@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBM@Z; win_musl::XpsElementMarkupProducer::SetAttribute<float>(wchar_t const *,float const &)
0x180080187  lea     rdx, [rsp+290h+var_220]
0x18008018c  mov     rcx, r14; this
0x18008018f  call    ?GetOrigin@XpsOMGlyphs@win_dox@@QEBA?AU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0017@@XZ; win_dox::XpsOMGlyphs::GetOrigin(void)
0x180080194  movss   xmm0, [rsp+290h+var_220]
0x18008019a  movss   dword ptr [rsp+290h+pv], xmm0
0x1800801a0  lea     r8, [rsp+290h+pv]
0x1800801a5  lea     rdx, ?gc_originX@Attribute@Xps@win_musl@@3QB_WB; "OriginX"
0x1800801ac  mov     rcx, [rsi+8]
0x1800801b0  call    ??$SetAttribute@M@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBM@Z; win_musl::XpsElementMarkupProducer::SetAttribute<float>(wchar_t const *,float const &)
0x1800801b5  movss   xmm0, [rsp+290h+var_21C]
0x1800801bb  movss   dword ptr [rsp+290h+pv], xmm0
0x1800801c1  lea     r8, [rsp+290h+pv]
0x1800801c6  lea     rdx, ?gc_originY@Attribute@Xps@win_musl@@3QB_WB; "OriginY"
0x1800801cd  mov     rcx, [rsi+8]
0x1800801d1  call    ??$SetAttribute@M@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBM@Z; win_musl::XpsElementMarkupProducer::SetAttribute<float>(wchar_t const *,float const &)
0x1800801d6  mov     rbx, [rsi+8]
0x1800801da  mov     rcx, r14; this
0x1800801dd  call    ?GetIsSideways@XpsOMGlyphs@win_dox@@QEBAHXZ; win_dox::XpsOMGlyphs::GetIsSideways(void)
0x1800801e2  test    eax, eax
0x1800801e4  jz      short loc_1800801FF
0x1800801e6  mov     [rsp+290h+var_248], 1
0x1800801eb  lea     r8, [rsp+290h+var_248]
0x1800801f0  lea     rdx, ?gc_isSideways@Attribute@Xps@win_musl@@3QB_WB; "IsSideways"
0x1800801f7  mov     rcx, rbx
0x1800801fa  call    ??$SetAttribute@_N@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEB_N@Z; win_musl::XpsElementMarkupProducer::SetAttribute<bool>(wchar_t const *,bool const &)
0x1800801ff  mov     rbx, [rsi+8]
0x180080203  mov     rcx, r14; this
0x180080206  call    ?GetOpacity@XpsOMVisual@win_dox@@QEBAMXZ; win_dox::XpsOMVisual::GetOpacity(void)
0x18008020b  movss   dword ptr [rsp+290h+pv], xmm0
0x180080211  ucomiss xmm0, cs:__real@3f800000
0x180080218  jp      short loc_18008021C
0x18008021a  jz      short loc_180080230
0x18008021c  lea     r8, [rsp+290h+pv]
0x180080221  lea     rdx, ?gc_opacity@Attribute@Xps@win_musl@@3QB_WB; "Opacity"
0x180080228  mov     rcx, rbx
0x18008022b  call    ??$SetAttribute@M@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBM@Z; win_musl::XpsElementMarkupProducer::SetAttribute<float>(wchar_t const *,float const &)
0x180080230  mov     rbx, [rsi+8]
0x180080234  mov     rcx, r14; this
0x180080237  call    ?GetStyleSimulations@XpsOMGlyphs@win_dox@@QEBA?AW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0004@@XZ; win_dox::XpsOMGlyphs::GetStyleSimulations(void)
0x18008023c  mov     dword ptr [rsp+290h+pv], eax
0x180080240  cmp     eax, 1
0x180080243  jz      short loc_180080252
0x180080245  lea     r8, [rsp+290h+pv]
0x18008024a  mov     rcx, rbx
0x18008024d  call    ??$SetAttribute@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0004@@@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBW4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0004@@@Z; win_musl::XpsElementMarkupProducer::SetAttribute<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0004>(wchar_t const *,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0004 const &)
0x180080252  lea     rdx, [rbp+190h+var_1F8]
0x180080256  mov     rcx, r14
0x180080259  call    ?GetName@XpsOMVisual@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMVisual::GetName(void)
0x18008025e  nop
0x18008025f  mov     rbx, [rbp+190h+var_1F8]
0x180080263  test    rbx, rbx
0x180080266  jz      loc_1800802F9
0x18008026c  cmp     cs:dword_180229818, 0FFFFFFFFh
0x180080273  jz      loc_1800802F9
0x180080279  cmp     [rsi+20h], r12
0x18008027d  jz      short loc_1800802E9
0x18008027f  lea     rdx, aNameSetForItem; "Name set for item in dictionary"
0x180080286  lea     rcx, [rbp+190h+Src]
0x18008028a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008028f  nop
0x180080290  lea     rdx, [rbp+190h+Src]
0x180080294  lea     rcx, [rbp+190h+var_140]
0x180080298  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18008029d  nop
0x18008029e  mov     rcx, rax; this
0x1800802a1  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800802a6  mov     [rsp+290h+var_260], rax; __int64
0x1800802ab  mov     [rsp+290h+var_268], 80520401h; int
0x1800802b3  mov     dword ptr [rsp+290h+var_270], 935h; unsigned int
0x1800802bb  lea     r9, Src
0x1800802c2  lea     r8, Src
0x1800802c9  lea     rcx, [rbp+190h+var_F0]; this
0x1800802d0  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800802d5  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800802dc  lea     rcx, [rbp+190h+var_F0]; pExceptionObject
0x1800802e3  call    _CxxThrowException_0
0x1800802e9  mov     r8, rbx
0x1800802ec  mov     rdx, [rsi+18h]
0x1800802f0  mov     rcx, [rsi+8]
0x1800802f4  call    ??$SendName@VPathMarkupProducer@win_musl@@@win_dox@@YAXPEAVPathMarkupProducer@win_musl@@PEAV?$set@Vlpwstr_wrapper@xpsutil@@U?$less@Vlpwstr_wrapper@xpsutil@@@std@@V?$allocator@Vlpwstr_wrapper@xpsutil@@@4@@std@@PEB_W@Z; win_dox::SendName<win_musl::PathMarkupProducer>(win_musl::PathMarkupProducer *,std::set<xpsutil::lpwstr_wrapper> *,wchar_t const *)
0x1800802f9  lea     rdx, [rsp+290h+pv]
0x1800802fe  mov     rcx, r14
0x180080301  call    ?GetDeviceFontName@XpsOMGlyphs@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMGlyphs::GetDeviceFontName(void)
0x180080306  nop
0x180080307  mov     r8, [rax]
0x18008030a  lea     rdx, ?SetDeviceFontName@GlyphsMarkupProducer@win_musl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::GlyphsMarkupProducer::SetDeviceFontName(std::wstring const &)
0x180080311  mov     rcx, [rsi+8]
0x180080315  call    ??$SendString@VGlyphsMarkupProducer@win_musl@@@win_dox@@YAXPEAVGlyphsMarkupProducer@win_musl@@P812@EAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ZPEB_W@Z; win_dox::SendString<win_musl::GlyphsMarkupProducer>(win_musl::GlyphsMarkupProducer *,void (win_musl::GlyphsMarkupProducer::*)(std::wstring const &),wchar_t const *)
0x18008031a  nop
0x18008031b  mov     rcx, [rsp+290h+pv]; pv
0x180080320  test    rcx, rcx
0x180080323  jz      short loc_18008032B
0x180080325  call    cs:__imp_CoTaskMemFree
0x18008032b  mov     rdx, r14
0x18008032e  mov     rcx, [rsi+8]
0x180080332  call    ??$SendCaretStops@VGlyphsMarkupProducer@win_musl@@@win_dox@@YAXPEAVGlyphsMarkupProducer@win_musl@@AEBVXpsOMGlyphs@0@@Z; win_dox::SendCaretStops<win_musl::GlyphsMarkupProducer>(win_musl::GlyphsMarkupProducer *,win_dox::XpsOMGlyphs const &)
0x180080337  movups  xmm0, xmmword ptr [rsi+28h]
0x18008033b  movdqu  xmmword ptr [rsp+290h+var_240], xmm0
0x180080341  lea     rax, [rsp+290h+var_240]
0x180080346  mov     [rsp+290h+var_260], rax
0x18008034b  mov     rax, [rsi+18h]
0x18008034f  mov     qword ptr [rsp+290h+var_268], rax; int
0x180080354  mov     rax, [rsi+10h]
0x180080358  mov     [rsp+290h+var_270], rax
0x18008035d  mov     r9, r14
0x180080360  mov     r8, [rsi+8]
0x180080364  mov     rdx, [rsi]
0x180080367  lea     rcx, [rbp+190h+var_1F0]
0x18008036b  call    ??0?$GlyphsAttrOrElemSender@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@win_dox@@QEAA@AEBVMarkupSenderContext@1@PEAVGlyphsMarkupProducer@win_musl@@AEBVXpsOMGlyphs@1@PEAV?$set@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@U?$less@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@V?$allocator@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@3@@std@@PEAV?$set@Vlpwstr_wrapper@xpsutil@@U?$less@Vlpwstr_wrapper@xpsutil@@@std@@V?$allocator@Vlpwstr_wrapper@xpsutil@@@4@@7@V?$OptimizerSettings@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@1@@Z; win_dox::GlyphsAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::GlyphsAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>(win_dox::MarkupSenderContext const &,win_musl::GlyphsMarkupProducer *,win_dox::XpsOMGlyphs const &,std::set<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>> *,std::set<xpsutil::lpwstr_wrapper> *,win_dox::OptimizerSettings<win_musl::PageBodyReceiverTraitsOnMarkupProducer>)
0x180080370  nop
0x180080371  mov     al, [rbp+190h+var_1B8]
0x180080374  mov     [rsp+290h+var_258], al; char
0x180080378  mov     rax, [rbp+190h+var_1C8]
0x18008037c  mov     [rsp+290h+var_260], rax; __int64
0x180080381  mov     rax, [rbp+190h+var_1E8]
0x180080385  mov     [rsp+290h+var_270], rax; win_musl::GlyphsMarkupProducer *
0x18008038a  lea     rdx, [rbp+190h+var_1E0]; int
0x18008038e  mov     rcx, qword ptr [rbp+190h+var_1F0]; int
0x180080392  call    ??$CheckSendAttrBrush@VXpsOMGlyphs@win_dox@@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VGlyphsMarkupProducer@4@@win_dox@@YA_NAEBVMarkupSenderContext@0@AEBVXpsOMGlyphs@0@P820@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP820@EBA?AVXpsOMBrush@0@XZPEAVGlyphsMarkupProducer@win_musl@@P867@EAAXAEBUXpsBrush@0@@ZPEAV?$set@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@U?$less@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@V?$allocator@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@3@@std@@_N@Z; win_dox::CheckSendAttrBrush<win_dox::XpsOMGlyphs,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::GlyphsMarkupProducer>(win_dox::MarkupSenderContext const &,win_dox::XpsOMGlyphs const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMGlyphs::*)(void),win_dox::XpsOMBrush (win_dox::XpsOMGlyphs::*)(void),win_musl::GlyphsMarkupProducer *,void (win_musl::GlyphsMarkupProducer::*)(win_dox::XpsBrush const &),std::set<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>> *,bool)
0x180080397  mov     [rbp+190h+var_188], al
0x18008039a  mov     r9, [rbp+190h+var_1E8]
0x18008039e  lea     rcx, [rbp+190h+var_1E0]
0x1800803a2  call    ??$CheckSendAttrTransform@VXpsOMCanvas@win_dox@@VCanvasMarkupProducer@win_musl@@@win_dox@@YA_NAEBVXpsOMCanvas@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMMatrixTransform@0@XZPEAVCanvasMarkupProducer@win_musl@@P856@EAAXAEBUXpsMatrixTransform@0@@Z@Z; win_dox::CheckSendAttrTransform<win_dox::XpsOMCanvas,win_musl::CanvasMarkupProducer>(win_dox::XpsOMCanvas const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMCanvas::*)(void),win_dox::XpsOMMatrixTransform (win_dox::XpsOMCanvas::*)(void),win_musl::CanvasMarkupProducer *,void (win_musl::CanvasMarkupProducer::*)(win_dox::XpsMatrixTransform const &))
0x1800803a7  mov     [rbp+190h+var_190], al
0x1800803aa  mov     al, [rbp+190h+var_1B8]
0x1800803ad  mov     byte ptr [rsp+290h+var_240], al
0x1800803b1  movsd   xmm0, [rbp+190h+var_1B7]
0x1800803b6  movsd   [rsp+290h+var_240+1], xmm0
0x1800803bc  mov     eax, [rbp+190h+var_1AF]
0x1800803bf  mov     dword ptr [rsp+290h+var_240+9], eax
0x1800803c3  movzx   eax, [rbp+190h+var_1AB]
0x1800803c7  mov     word ptr [rsp+290h+var_240+0Dh], ax
0x1800803cc  mov     al, [rbp+190h+var_1A9]
0x1800803cf  mov     byte ptr [rsp+290h+var_240+0Fh], al
0x1800803d3  lea     rax, [rsp+290h+var_240]
0x1800803d8  mov     qword ptr [rsp+290h+var_268], rax
0x1800803dd  mov     r9, [rbp+190h+var_1E8]
  ... truncated ...
```
