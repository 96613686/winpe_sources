# win_dox::CanvasSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::operator()(win_dox::XpsOMCanvas const &)

- ea: `0x18000b9e0`
- end: `0x18000bde5`
- name: `??R?$CanvasSender@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@win_dox@@QEAAXAEBVXpsOMCanvas@1@@Z`
- size: `1029`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cf398`

## callees

- `0x1800041b0`
- `0x18000b9e0`
- `0x18000bdec`
- `0x18000be60`
- `0x18000bf18`
- `0x18000c2b0`
- `0x18000c480`
- `0x18000c4bc`
- `0x18000c5a0`
- `0x18000c750`
- `0x18000c7b0`
- `0x18000c800`
- `0x18000cb80`
- `0x18000cc7c`
- `0x18000ccd0`
- `0x180012450`
- `0x180019170`
- `0x18001befc`
- `0x18001bfbc`
- `0x18001dc2c`
- `0x18001de3c`
- `0x18001df74`
- `0x18004ef78`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c1178`
- `0x1800c20c4`
- `0x1800c23cc`
- `0x1800d641c`
- `0x180115e04`
- `0x180134b70`
- `0x1801359ce`
- `0x1801a6a88`
- `0x1801a6dd8`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bcfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bda9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bcfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bda9`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall win_dox::CanvasSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::operator()(
        __int64 *a1,
        win_dox::XpsOMGlyphs *a2)
{
  __int64 v4; // rdx
  _QWORD *AccessibilityShortDescription; // rax
  _QWORD *AccessibilityLongDescription; // rax
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int128 v10; // xmm6
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  void *v15; // rbx
  win_musl::Formatter *v16; // rax
  const wchar_t *v17; // rax
  __int64 HyperlinkNavigateUri; // rax
  int v19; // edi
  __int64 v20; // rax
  _QWORD *AbsoluteUri; // rax
  _QWORD *Language; // rax
  __int64 v23; // rdx
  __int128 v24; // xmm6
  __int64 v25; // rdi
  __int64 v26; // rsi
  int Visuals; // eax
  __int64 v28; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B8h]
  _BYTE v30[16]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v31[3]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+80h] [rbp-88h]
  void *v33; // [rsp+90h] [rbp-78h]
  void *v34; // [rsp+98h] [rbp-70h]
  void *v35; // [rsp+A0h] [rbp-68h]
  __int16 v36; // [rsp+A8h] [rbp-60h]
  char v37; // [rsp+AAh] [rbp-5Eh]
  LPVOID v38[2]; // [rsp+B8h] [rbp-50h] BYREF
  LPVOID pv[4]; // [rsp+C8h] [rbp-40h] BYREF
  LPVOID v40[4]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v41[80]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+158h] [rbp+50h] BYREF

  if ( win_dox::XpsOMGlyphs::GetGlyphIndexCount(a2) )
  {
    LODWORD(pv[0]) = 2;
    win_musl::XpsElementMarkupProducer::SetAttribute<enum XPS_EDGE_MODE>(a1[1], v4, pv);
  }
  AccessibilityShortDescription = (_QWORD *)win_dox::XpsOMCanvas::GetAccessibilityShortDescription(a2, pv);
  win_dox::SendString<win_musl::CanvasMarkupProducer>(
    a1[1],
    win_musl::CanvasMarkupProducer::SetAutomationPropertiesName,
    *AccessibilityShortDescription);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  AccessibilityLongDescription = (_QWORD *)win_dox::XpsOMCanvas::GetAccessibilityLongDescription(a2, pv);
  win_dox::SendString<win_musl::CanvasMarkupProducer>(
    a1[1],
    win_musl::PathMarkupProducer::SetAutomationPropertiesHelpText,
    *AccessibilityLongDescription);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  v7 = a1[1];
  LODWORD(pv[0]) = win_dox::XpsOMVisual::GetOpacity(a2);
  if ( *(float *)pv != 1.0 )
    win_musl::XpsElementMarkupProducer::SetAttribute<float>(v7, L"Opacity", pv);
  v8 = a1[3];
  v9 = a1[2];
  v10 = *(_OWORD *)(a1 + 5);
  v28 = *a1;
  v29 = a1[1];
  v40[0] = v30;
  win_dox::XpsOMVisual::XpsOMVisual((win_dox::XpsOMVisual *)v30, a2);
  win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(
    v31,
    (char *)a2 + 16);
  v31[1] = v9;
  v31[2] = v8;
  v32 = v10;
  v33 = &win_musl::CanvasMarkupProducer::SetCanvasClip;
  v34 = &win_musl::CanvasMarkupProducer::SetCanvasRenderTransform;
  v35 = &win_musl::CanvasMarkupProducer::SetCanvasOpacityMask;
  v36 = 0;
  v37 = 0;
  LOBYTE(v36) = win_dox::CheckSendAttrTransform<win_dox::XpsOMCanvas,win_musl::CanvasMarkupProducer>(v30, v11, v12, v29);
  *(_OWORD *)v40 = v32;
  v37 = win_dox::CheckSendAttrGeometry<win_dox::XpsOMCanvas,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(
          v30,
          v13,
          v14,
          v29);
  win_dox::VisualAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer,win_dox::XpsOMCanvas>::CheckSendAttrOpacityMask(&v28);
  win_dox::XpsOMVisual::GetName(a2, v38);
  v15 = v38[0];
  if ( v38[0] && dword_180229818 != -1 )
  {
    if ( a1[4] )
    {
      std::wstring::wstring(v40, L"Name set for item in dictionary");
      v16 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v41, v40);
      v17 = win_musl::Formatter::c_str(v16);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0xA0Au,
        -2142108671,
        (__int64)v17);
      throw (SplException::THResultException *)pExceptionObject;
    }
    win_dox::SendName<win_musl::PathMarkupProducer>(a1[1], a1[3], v38[0]);
  }
  HyperlinkNavigateUri = win_dox::XpsOMVisual::GetHyperlinkNavigateUri(a2, v40);
  v19 = -1;
  if ( *(_QWORD *)xpsom::XpsOMCorePropertiesReceiver::SetVersion(HyperlinkNavigateUri, pv) )
    v19 = dword_180229818;
  if ( pv[0] )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
    pv[0] = 0;
  }
  if ( v40[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
  if ( v19 != -1 )
  {
    v20 = win_dox::XpsOMVisual::GetHyperlinkNavigateUri(a2, v40);
    AbsoluteUri = (_QWORD *)win_dox::Uri::GetAbsoluteUri(v20, pv);
    if ( AbsoluteUri[3] > 7u )
      AbsoluteUri = (_QWORD *)*AbsoluteUri;
    win_dox::SendString<win_musl::CanvasMarkupProducer>(
      a1[1],
      win_musl::PathMarkupProducer::SetNavigateUri,
      AbsoluteUri);
    std::wstring::_Tidy_deallocate(pv);
    if ( v40[0] )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
  }
  Language = (_QWORD *)win_dox::XpsOMVisual::GetLanguage(a2, v40);
  win_dox::SendLanguage<win_musl::GlyphsMarkupProducer>(a1[1], *Language);
  if ( v40[0] )
    CoTaskMemFree(v40[0]);
  win_dox::SendKey<win_musl::ImageBrushMarkupProducer>(a1[1], a1[4]);
  win_dox::SendDictionary<win_dox::XpsOMCanvas,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(
    *a1,
    a1[1],
    (_DWORD)a2,
    a1[2],
    *((_BYTE *)a1 + 40));
  if ( !v37 )
    win_dox::CheckSendElemGeometry<win_dox::XpsOMCanvas,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(
      v30,
      v23,
      v29,
      v33);
  win_dox::VisualAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer,win_dox::XpsOMCanvas>::CheckSendElemOpacityMask(&v28);
  v24 = *(_OWORD *)(a1 + 5);
  v25 = a1[3];
  v26 = a1[2];
  Visuals = win_dox::XpsOMCanvas::GetVisuals(a2, v40);
  *(_OWORD *)pv = v24;
  win_dox::SendVisualCollection<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(
    *a1,
    a1[1],
    Visuals,
    v26,
    v25,
    (__int64)pv);
  if ( v40[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
  if ( v15 )
    CoTaskMemFree(v15);
  win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v30);
}

```

## disassembly

```asm
0x18000b9e0  mov     rax, rsp
0x18000b9e3  mov     [rax+18h], rbx
0x18000b9e7  push    rbp
0x18000b9e8  push    rsi
0x18000b9e9  push    rdi
0x18000b9ea  push    r14
0x18000b9ec  push    r15
0x18000b9ee  lea     rbp, [rax-138h]
0x18000b9f5  sub     rsp, 210h
0x18000b9fc  movaps  xmmword ptr [rax-38h], xmm6
0x18000ba00  mov     rax, cs:__security_cookie
0x18000ba07  xor     rax, rsp
0x18000ba0a  mov     [rbp+130h+var_40], rax
0x18000ba11  mov     r15, rdx
0x18000ba14  mov     r14, rcx
0x18000ba17  mov     rcx, rdx; this
0x18000ba1a  call    ?GetGlyphIndexCount@XpsOMGlyphs@win_dox@@QEBAIXZ; win_dox::XpsOMGlyphs::GetGlyphIndexCount(void)
0x18000ba1f  test    eax, eax
0x18000ba21  jz      short loc_18000BA37
0x18000ba23  mov     dword ptr [rbp+130h+pv], 2
0x18000ba2a  lea     r8, [rbp+130h+pv]
0x18000ba2e  mov     rcx, [r14+8]
0x18000ba32  call    ??$SetAttribute@W4XPS_EDGE_MODE@@@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBW4XPS_EDGE_MODE@@@Z; win_musl::XpsElementMarkupProducer::SetAttribute<XPS_EDGE_MODE>(wchar_t const *,XPS_EDGE_MODE const &)
0x18000ba37  lea     rdx, [rbp+130h+pv]
0x18000ba3b  mov     rcx, r15
0x18000ba3e  call    ?GetAccessibilityShortDescription@XpsOMCanvas@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMCanvas::GetAccessibilityShortDescription(void)
0x18000ba43  nop
0x18000ba44  mov     r8, [rax]
0x18000ba47  lea     rdx, ?SetAutomationPropertiesName@CanvasMarkupProducer@win_musl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::CanvasMarkupProducer::SetAutomationPropertiesName(std::wstring const &)
0x18000ba4e  mov     rcx, [r14+8]
0x18000ba52  call    ??$SendString@VCanvasMarkupProducer@win_musl@@@win_dox@@YAXPEAVCanvasMarkupProducer@win_musl@@P812@EAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ZPEB_W@Z; win_dox::SendString<win_musl::CanvasMarkupProducer>(win_musl::CanvasMarkupProducer *,void (win_musl::CanvasMarkupProducer::*)(std::wstring const &),wchar_t const *)
0x18000ba57  nop
0x18000ba58  mov     rcx, [rbp+130h+pv]; pv
0x18000ba5c  test    rcx, rcx
0x18000ba5f  jz      short loc_18000BA67
0x18000ba61  call    cs:__imp_CoTaskMemFree
0x18000ba67  lea     rdx, [rbp+130h+pv]
0x18000ba6b  mov     rcx, r15
0x18000ba6e  call    ?GetAccessibilityLongDescription@XpsOMCanvas@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMCanvas::GetAccessibilityLongDescription(void)
0x18000ba73  nop
0x18000ba74  mov     r8, [rax]
0x18000ba77  lea     rdx, ?SetAutomationPropertiesHelpText@PathMarkupProducer@win_musl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::PathMarkupProducer::SetAutomationPropertiesHelpText(std::wstring const &)
0x18000ba7e  mov     rcx, [r14+8]
0x18000ba82  call    ??$SendString@VCanvasMarkupProducer@win_musl@@@win_dox@@YAXPEAVCanvasMarkupProducer@win_musl@@P812@EAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ZPEB_W@Z; win_dox::SendString<win_musl::CanvasMarkupProducer>(win_musl::CanvasMarkupProducer *,void (win_musl::CanvasMarkupProducer::*)(std::wstring const &),wchar_t const *)
0x18000ba87  nop
0x18000ba88  mov     rcx, [rbp+130h+pv]; pv
0x18000ba8c  test    rcx, rcx
0x18000ba8f  jz      short loc_18000BA97
0x18000ba91  call    cs:__imp_CoTaskMemFree
0x18000ba97  mov     rbx, [r14+8]
0x18000ba9b  mov     rcx, r15; this
0x18000ba9e  call    ?GetOpacity@XpsOMVisual@win_dox@@QEBAMXZ; win_dox::XpsOMVisual::GetOpacity(void)
0x18000baa3  movss   dword ptr [rbp+130h+pv], xmm0
0x18000baa8  ucomiss xmm0, cs:__real@3f800000
0x18000baaf  jp      short loc_18000BAB3
0x18000bab1  jz      short loc_18000BAC6
0x18000bab3  lea     r8, [rbp+130h+pv]
0x18000bab7  lea     rdx, ?gc_opacity@Attribute@Xps@win_musl@@3QB_WB; "Opacity"
0x18000babe  mov     rcx, rbx
0x18000bac1  call    ??$SetAttribute@M@XpsElementMarkupProducer@win_musl@@IEAAXPEB_WAEBM@Z; win_musl::XpsElementMarkupProducer::SetAttribute<float>(wchar_t const *,float const &)
0x18000bac6  mov     rdi, [r14+18h]
0x18000baca  mov     rbx, [r14+10h]
0x18000bace  movups  xmm6, xmmword ptr [r14+28h]
0x18000bad3  mov     rax, [r14]
0x18000bad6  mov     [rsp+230h+var_1F0], rax
0x18000badb  mov     rax, [r14+8]
0x18000badf  mov     [rsp+230h+var_1E8], rax
0x18000bae4  lea     rax, [rsp+230h+var_1E0]
0x18000bae9  mov     [rbp+130h+var_150], rax
0x18000baed  mov     rdx, r15; struct win_dox::XpsOMVisual *
0x18000baf0  lea     rcx, [rsp+230h+var_1E0]; this
0x18000baf5  call    ??0XpsOMVisual@win_dox@@QEAA@AEBV01@@Z; win_dox::XpsOMVisual::XpsOMVisual(win_dox::XpsOMVisual const &)
0x18000bafa  nop
0x18000bafb  lea     rdx, [r15+10h]
0x18000baff  lea     rcx, [rsp+230h+var_1D0]
0x18000bb04  call    ??0?$scope@PEAUIXpsOMCanvas@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>> const &)
0x18000bb09  nop
0x18000bb0a  mov     [rsp+230h+var_1C8], rbx
0x18000bb0f  mov     qword ptr [rsp+230h+var_1C0], rdi
0x18000bb14  movdqu  xmmword ptr [rsp+230h+var_1C0+8], xmm6
0x18000bb1a  lea     rax, ?SetCanvasClip@CanvasMarkupProducer@win_musl@@QEAA?AVGeometriesMarkupProducer@2@XZ; win_musl::CanvasMarkupProducer::SetCanvasClip(void)
0x18000bb21  mov     [rbp+130h+var_1A8], rax
0x18000bb25  lea     rax, ?SetCanvasRenderTransform@CanvasMarkupProducer@win_musl@@QEAA?AVTransformMarkupProducer@2@XZ; win_musl::CanvasMarkupProducer::SetCanvasRenderTransform(void)
0x18000bb2c  mov     [rbp+130h+var_1A0], rax
0x18000bb30  lea     rax, ?SetCanvasOpacityMask@CanvasMarkupProducer@win_musl@@QEAA?AVBrushMarkupProducer@2@XZ; win_musl::CanvasMarkupProducer::SetCanvasOpacityMask(void)
0x18000bb37  mov     [rbp+130h+var_198], rax
0x18000bb3b  mov     [rbp+130h+var_190], 0
0x18000bb41  mov     [rbp+130h+var_18E], 0
0x18000bb45  mov     r9, [rsp+230h+var_1E8]
0x18000bb4a  lea     rcx, [rsp+230h+var_1E0]
0x18000bb4f  call    ??$CheckSendAttrTransform@VXpsOMCanvas@win_dox@@VCanvasMarkupProducer@win_musl@@@win_dox@@YA_NAEBVXpsOMCanvas@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMMatrixTransform@0@XZPEAVCanvasMarkupProducer@win_musl@@P856@EAAXAEBUXpsMatrixTransform@0@@Z@Z; win_dox::CheckSendAttrTransform<win_dox::XpsOMCanvas,win_musl::CanvasMarkupProducer>(win_dox::XpsOMCanvas const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMCanvas::*)(void),win_dox::XpsOMMatrixTransform (win_dox::XpsOMCanvas::*)(void),win_musl::CanvasMarkupProducer *,void (win_musl::CanvasMarkupProducer::*)(win_dox::XpsMatrixTransform const &))
0x18000bb54  mov     byte ptr [rbp+130h+var_190], al
0x18000bb57  movups  xmm0, xmmword ptr [rsp+230h+var_1C0+8]
0x18000bb5c  movdqu  xmmword ptr [rbp+130h+var_150], xmm0
0x18000bb61  lea     rax, [rbp+130h+var_150]
0x18000bb65  mov     qword ptr [rsp+230h+var_208], rax
0x18000bb6a  mov     r9, [rsp+230h+var_1E8]
0x18000bb6f  lea     rcx, [rsp+230h+var_1E0]
0x18000bb74  call    ??$CheckSendAttrGeometry@VXpsOMCanvas@win_dox@@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VCanvasMarkupProducer@4@@win_dox@@YA_NAEBVXpsOMCanvas@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMGeometry@0@XZPEAVCanvasMarkupProducer@win_musl@@P856@EAAXAEBUXpsGeometries@0@@ZV?$OptimizerSettings@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@0@@Z; win_dox::CheckSendAttrGeometry<win_dox::XpsOMCanvas,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(win_dox::XpsOMCanvas const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMCanvas::*)(void),win_dox::XpsOMGeometry (win_dox::XpsOMCanvas::*)(void),win_musl::CanvasMarkupProducer *,void (win_musl::CanvasMarkupProducer::*)(win_dox::XpsGeometries const &),win_dox::OptimizerSettings<win_musl::PageBodyReceiverTraitsOnMarkupProducer>)
0x18000bb79  mov     [rbp+130h+var_18E], al
0x18000bb7c  lea     rcx, [rsp+230h+var_1F0]
0x18000bb81  call    ?CheckSendAttrOpacityMask@?$VisualAttrOrElemSender@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VCanvasMarkupProducer@2@VXpsOMCanvas@win_dox@@@win_dox@@QEAAXXZ; win_dox::VisualAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer,win_dox::XpsOMCanvas>::CheckSendAttrOpacityMask(void)
0x18000bb86  lea     rdx, [rbp+130h+var_180]
0x18000bb8a  mov     rcx, r15
0x18000bb8d  call    ?GetName@XpsOMVisual@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMVisual::GetName(void)
0x18000bb92  nop
0x18000bb93  mov     rbx, [rbp+130h+var_180]
0x18000bb97  test    rbx, rbx
0x18000bb9a  jz      loc_18000BC20
0x18000bba0  cmp     cs:dword_180229818, 0FFFFFFFFh
0x18000bba7  jz      short loc_18000BC20
0x18000bba9  cmp     qword ptr [r14+20h], 0
0x18000bbae  jz      short loc_18000BC10
0x18000bbb0  lea     rdx, aNameSetForItem; "Name set for item in dictionary"
0x18000bbb7  lea     rcx, [rbp+130h+var_150]
0x18000bbbb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000bbc0  nop
0x18000bbc1  lea     rdx, [rbp+130h+var_150]
0x18000bbc5  lea     rcx, [rbp+130h+var_130]
0x18000bbc9  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18000bbce  nop
0x18000bbcf  mov     rcx, rax; this
0x18000bbd2  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18000bbd7  mov     [rsp+230h+var_200], rax; __int64
0x18000bbdc  mov     [rsp+230h+var_208], 80520401h; int
0x18000bbe4  mov     [rsp+230h+var_210], 0A0Ah; unsigned int
0x18000bbec  lea     r8, Src
0x18000bbf3  mov     r9, r8
0x18000bbf6  lea     rcx, [rbp+130h+pExceptionObject]; this
0x18000bbfa  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000bbff  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000bc06  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x18000bc0a  call    _CxxThrowException_0
0x18000bc10  mov     r8, rbx
0x18000bc13  mov     rdx, [r14+18h]
0x18000bc17  mov     rcx, [r14+8]
0x18000bc1b  call    ??$SendName@VPathMarkupProducer@win_musl@@@win_dox@@YAXPEAVPathMarkupProducer@win_musl@@PEAV?$set@Vlpwstr_wrapper@xpsutil@@U?$less@Vlpwstr_wrapper@xpsutil@@@std@@V?$allocator@Vlpwstr_wrapper@xpsutil@@@4@@std@@PEB_W@Z; win_dox::SendName<win_musl::PathMarkupProducer>(win_musl::PathMarkupProducer *,std::set<xpsutil::lpwstr_wrapper> *,wchar_t const *)
0x18000bc20  lea     rdx, [rbp+130h+var_150]
0x18000bc24  mov     rcx, r15
0x18000bc27  call    ?GetHyperlinkNavigateUri@XpsOMVisual@win_dox@@QEBA?AVUri@2@XZ; win_dox::XpsOMVisual::GetHyperlinkNavigateUri(void)
0x18000bc2c  nop
0x18000bc2d  lea     rdx, [rbp+130h+pv]
0x18000bc31  mov     rcx, rax
0x18000bc34  call    ?SetVersion@XpsOMCorePropertiesReceiver@xpsom@@QEAA?AVXpsOMVersionReceiver@2@XZ; xpsom::XpsOMCorePropertiesReceiver::SetVersion(void)
0x18000bc39  or      edi, 0FFFFFFFFh
0x18000bc3c  cmp     qword ptr [rax], 0
0x18000bc40  cmovnz  edi, cs:dword_180229818
0x18000bc47  mov     rcx, [rbp+130h+pv]
0x18000bc4b  test    rcx, rcx
0x18000bc4e  jz      short loc_18000BC64
0x18000bc50  mov     rax, [rcx]
0x18000bc53  mov     rax, [rax+10h]
0x18000bc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc5c  mov     [rbp+130h+pv], 0
0x18000bc64  mov     rcx, [rbp+130h+var_150]
0x18000bc68  test    rcx, rcx
0x18000bc6b  jz      short loc_18000BC7A
0x18000bc6d  mov     rax, [rcx]
0x18000bc70  mov     rax, [rax+10h]
0x18000bc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc79  nop
0x18000bc7a  cmp     edi, 0FFFFFFFFh
0x18000bc7d  jz      short loc_18000BCD7
0x18000bc7f  lea     rdx, [rbp+130h+var_150]
0x18000bc83  mov     rcx, r15
0x18000bc86  call    ?GetHyperlinkNavigateUri@XpsOMVisual@win_dox@@QEBA?AVUri@2@XZ; win_dox::XpsOMVisual::GetHyperlinkNavigateUri(void)
0x18000bc8b  nop
0x18000bc8c  lea     rdx, [rbp+130h+pv]
0x18000bc90  mov     rcx, rax
0x18000bc93  call    ?GetAbsoluteUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; win_dox::Uri::GetAbsoluteUri(void)
0x18000bc98  nop
0x18000bc99  cmp     qword ptr [rax+18h], 7
0x18000bc9e  jbe     short loc_18000BCA3
0x18000bca0  mov     rax, [rax]
0x18000bca3  mov     r8, rax
0x18000bca6  lea     rdx, ?SetNavigateUri@PathMarkupProducer@win_musl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::PathMarkupProducer::SetNavigateUri(std::wstring const &)
0x18000bcad  mov     rcx, [r14+8]
0x18000bcb1  call    ??$SendString@VCanvasMarkupProducer@win_musl@@@win_dox@@YAXPEAVCanvasMarkupProducer@win_musl@@P812@EAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ZPEB_W@Z; win_dox::SendString<win_musl::CanvasMarkupProducer>(win_musl::CanvasMarkupProducer *,void (win_musl::CanvasMarkupProducer::*)(std::wstring const &),wchar_t const *)
0x18000bcb6  nop
0x18000bcb7  lea     rcx, [rbp+130h+pv]
0x18000bcbb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000bcc0  nop
0x18000bcc1  mov     rcx, [rbp+130h+var_150]
0x18000bcc5  test    rcx, rcx
0x18000bcc8  jz      short loc_18000BCD7
0x18000bcca  mov     rax, [rcx]
0x18000bccd  mov     rax, [rax+10h]
0x18000bcd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcd6  nop
0x18000bcd7  lea     rdx, [rbp+130h+var_150]
0x18000bcdb  mov     rcx, r15
0x18000bcde  call    ?GetLanguage@XpsOMVisual@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMVisual::GetLanguage(void)
0x18000bce3  nop
0x18000bce4  mov     rdx, [rax]
0x18000bce7  mov     rcx, [r14+8]
0x18000bceb  call    ??$SendLanguage@VGlyphsMarkupProducer@win_musl@@@win_dox@@YAXPEAVGlyphsMarkupProducer@win_musl@@PEB_W@Z; win_dox::SendLanguage<win_musl::GlyphsMarkupProducer>(win_musl::GlyphsMarkupProducer *,wchar_t const *)
0x18000bcf0  nop
0x18000bcf1  mov     rcx, [rbp+130h+var_150]; pv
0x18000bcf5  test    rcx, rcx
0x18000bcf8  jz      short loc_18000BD00
0x18000bcfa  call    cs:__imp_CoTaskMemFree
0x18000bd00  mov     rdx, [r14+20h]
0x18000bd04  mov     rcx, [r14+8]
0x18000bd08  call    ??$SendKey@VImageBrushMarkupProducer@win_musl@@@win_dox@@YAXPEAVImageBrushMarkupProducer@win_musl@@PEB_W@Z; win_dox::SendKey<win_musl::ImageBrushMarkupProducer>(win_musl::ImageBrushMarkupProducer *,wchar_t const *)
0x18000bd0d  mov     al, [r14+28h]
0x18000bd11  mov     byte ptr [rsp+230h+var_210], al
0x18000bd15  mov     r9, [r14+10h]
0x18000bd19  mov     r8, r15
0x18000bd1c  mov     rdx, [r14+8]
0x18000bd20  mov     rcx, [r14]
0x18000bd23  call    ??$SendDictionary@VXpsOMCanvas@win_dox@@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VCanvasMarkupProducer@4@@win_dox@@YAXAEBVMarkupSenderContext@0@PEAVCanvasMarkupProducer@win_musl@@AEBVXpsOMCanvas@0@PEAV?$set@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@U?$less@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@V?$allocator@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@3@@std@@_N@Z; win_dox::SendDictionary<win_dox::XpsOMCanvas,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(win_dox::MarkupSenderContext const &,win_musl::CanvasMarkupProducer *,win_dox::XpsOMCanvas const &,std::set<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>> *,bool)
0x18000bd28  cmp     [rbp+130h+var_18E], 0
0x18000bd2c  jnz     short loc_18000BD41
0x18000bd2e  mov     r9, [rbp+130h+var_1A8]
0x18000bd32  mov     r8, [rsp+230h+var_1E8]
0x18000bd37  lea     rcx, [rsp+230h+var_1E0]
0x18000bd3c  call    ??$CheckSendElemGeometry@VXpsOMCanvas@win_dox@@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VCanvasMarkupProducer@4@@win_dox@@YA_NAEBVXpsOMCanvas@0@P810@EBA?AVXpsOMGeometry@0@XZPEAVCanvasMarkupProducer@win_musl@@P834@EAA?AVGeometriesMarkupProducer@4@XZ@Z; win_dox::CheckSendElemGeometry<win_dox::XpsOMCanvas,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(win_dox::XpsOMCanvas const &,win_dox::XpsOMGeometry (win_dox::XpsOMCanvas::*)(void),win_musl::CanvasMarkupProducer *,win_musl::GeometriesMarkupProducer (win_musl::CanvasMarkupProducer::*)(void))
0x18000bd41  lea     rcx, [rsp+230h+var_1F0]
0x18000bd46  call    ?CheckSendElemOpacityMask@?$VisualAttrOrElemSender@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VCanvasMarkupProducer@2@VXpsOMCanvas@win_dox@@@win_dox@@QEAAXXZ; win_dox::VisualAttrOrElemSender<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer,win_dox::XpsOMCanvas>::CheckSendElemOpacityMask(void)
0x18000bd4b  movups  xmm6, xmmword ptr [r14+28h]
0x18000bd50  mov     rdi, [r14+18h]
0x18000bd54  mov     rsi, [r14+10h]
0x18000bd58  lea     rdx, [rbp+130h+var_150]
0x18000bd5c  mov     rcx, r15
0x18000bd5f  call    ?GetVisuals@XpsOMCanvas@win_dox@@QEBA?AV?$XpsOMResourceCollection@UIXpsOMVisualCollection@@@2@XZ; win_dox::XpsOMCanvas::GetVisuals(void)
0x18000bd64  nop
0x18000bd65  movdqu  xmmword ptr [rbp+130h+pv], xmm6
0x18000bd6a  lea     rcx, [rbp+130h+pv]
0x18000bd6e  mov     qword ptr [rsp+230h+var_208], rcx
0x18000bd73  mov     qword ptr [rsp+230h+var_210], rdi
0x18000bd78  mov     r9, rsi
0x18000bd7b  mov     r8, rax
0x18000bd7e  mov     rdx, [r14+8]
0x18000bd82  mov     rcx, [r14]
0x18000bd85  call    ??$SendVisualCollection@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VCanvasMarkupProducer@2@@win_dox@@YAXAEBVMarkupSenderContext@0@PEAVCanvasMarkupProducer@win_musl@@AEBV?$XpsOMResourceCollection@UIXpsOMVisualCollection@@@0@PEAV?$set@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@U?$less@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@V?$allocator@V?$dynamic_storage@V?$type_list@VXpsOMFontResource@win_dox@@V?$type_list@VXpsOMImageResource@win_dox@@V?$type_list@VXpsOMColorProfileResource@win_dox@@V?$type_list@VXpsOMRemoteDictionaryResource@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@3@@std@@PEAV?$set@Vlpwstr_wrapper@xpsutil@@U?$less@Vlpwstr_wrapper@xpsutil@@@std@@V?$allocator@Vlpwstr_wrapper@xpsutil@@@4@@6@V?$OptimizerSettings@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@0@@Z; win_dox::SendVisualCollection<win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(win_dox::MarkupSenderContext const &,win_musl::CanvasMarkupProducer *,win_dox::XpsOMResourceCollection<IXpsOMVisualCollection> const &,std::set<dynamic_storage<win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>,win_mp_lib::type_list<win_dox::XpsOMFontResource,win_mp_lib::type_list<win_dox::XpsOMImageResource,win_mp_lib::type_list<win_dox::XpsOMColorProfileResource,win_mp_lib::type_list<win_dox::XpsOMRemoteDictionaryResource,win_mp_lib::null_type>>>>>> *,std::set<xpsutil::lpwstr_wrapper> *,win_dox::OptimizerSettings<win_musl::PageBodyReceiverTraitsOnMarkupProducer>)
0x18000bd8a  nop
0x18000bd8b  mov     rcx, [rbp+130h+var_150]
0x18000bd8f  test    rcx, rcx
0x18000bd92  jz      short loc_18000BDA1
0x18000bd94  mov     rax, [rcx]
0x18000bd97  mov     rax, [rax+10h]
0x18000bd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bda0  nop
0x18000bda1  test    rbx, rbx
0x18000bda4  jz      short loc_18000BDB0
0x18000bda6  mov     rcx, rbx; pv
0x18000bda9  call    cs:__imp_CoTaskMemFree
0x18000bdaf  nop
0x18000bdb0  lea     rcx, [rsp+230h+var_1E0]; this
0x18000bdb5  call    ??1XpsOMSolidColorBrush@win_dox@@QEAA@XZ; win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush(void)
0x18000bdba  mov     rcx, [rbp+130h+var_40]
0x18000bdc1  xor     rcx, rsp; StackCookie
0x18000bdc4  call    __security_check_cookie
0x18000bdc9  lea     r11, [rsp+230h+var_20]
0x18000bdd1  mov     rbx, [r11+40h]
0x18000bdd5  movaps  xmm6, xmmword ptr [r11-10h]
0x18000bdda  mov     rsp, r11
0x18000bddd  pop     r15
0x18000bddf  pop     r14
0x18000bde1  pop     rdi
0x18000bde2  pop     rsi
0x18000bde3  pop     rbp
0x18000bde4  retn
```
