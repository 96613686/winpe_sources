# xpssig::sigdef::ParseSignDefinitionsStream(IStream *,__MIDL___MIDL_itf_win72Exps2Eio_0000_0025_0002,xpssig::sigdef::ISignatureDefinitionsReceiver *)

- ea: `0x1800d84fc`
- end: `0x1800d8afa`
- name: `?ParseSignDefinitionsStream@sigdef@xpssig@@YAXPEAUIStream@@W4__MIDL___MIDL_itf_win72Exps2Eio_0000_0025_0002@@PEAVISignatureDefinitionsReceiver@12@@Z`
- size: `1534`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d8b00`

## callees

- `0x18000310c`
- `0x180003ab8`
- `0x1800041b0`
- `0x180005664`
- `0x180005edc`
- `0x180009374`
- `0x180012450`
- `0x1800228a4`
- `0x180027214`
- `0x180031fa8`
- `0x180032344`
- `0x18003240c`
- `0x1800326b0`
- `0x1800326fc`
- `0x180032754`
- `0x18003ac50`
- `0x18009411c`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c1454`
- `0x1800c20c4`
- `0x1800cbe40`
- `0x1800d8418`
- `0x1800d84fc`
- `0x180134b70`
- `0x18013578c`
- `0x1801359ce`
- `0x18013bcc0`
- `0x180142104`
- `0x18019fd38`
- `0x1801a0568`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800d8921`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d8921`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d895f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d895f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d8590`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d8590`

## string_xrefs

- `0x1800d861d`: `http://schemas.microsoft.com/xps/2005/06/signature-definitions`
- `0x1800d8624`: `http://schemas.openxps.org/oxps/v1.0/signature-definitions`
- `0x1800d859c`: `CoCreateInstance fails for CLSID_SAXXMLReader60 class and IID_ISAXXMLReader interface`
- `0x1800d88ac`: `ISAXXMLReader::putContentHandler fails`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
void __fastcall xpssig::sigdef::ParseSignDefinitionsStream(__int64 a1, int a2, __int64 a3, int a4)
{
  const char *v7; // rdx
  HRESULT v8; // ebx
  unsigned int v9; // r8d
  win_musl::Formatter *v10; // rax
  const wchar_t *v11; // rax
  _DWORD *v12; // rax
  const char *v13; // rdx
  unsigned int v14; // r8d
  _DWORD *v15; // rdi
  const wchar_t *v16; // rcx
  __int64 v17; // rdx
  _DWORD *v18; // rbx
  void *v19; // r15
  win_scope::counted_strong_weak_base *v20; // rax
  win_scope::counted_strong_weak_base *v21; // r14
  __int64 v22; // rax
  _DWORD *v23; // rdi
  __int64 v24; // rdi
  __int64 *v25; // rdx
  __int64 v26; // rax
  _DWORD *v27; // rsi
  int v28; // edi
  win_musl::Formatter *v29; // rax
  const wchar_t *v30; // rax
  LPVOID v31; // r13
  BSTR v32; // rax
  BSTR v33; // r12
  OLECHAR *v34; // rdi
  int v35; // edi
  __int64 v36; // r12
  __int64 v37; // rax
  _QWORD *v38; // rdx
  win_musl::Formatter *v39; // rax
  const wchar_t *v40; // rax
  BSTR v41; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  char v44[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+5Ch] [rbp-A4h]
  _DWORD *v46; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h] BYREF
  void (__fastcall **v48)(_QWORD, _QWORD, _QWORD); // [rsp+70h] [rbp-90h] BYREF
  __int128 v49; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v50; // [rsp+88h] [rbp-78h]
  _QWORD v51[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v52[80]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+100h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+1A0h] [rbp+A0h] BYREF

  v45 = 0;
  ppv = 0;
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, (int)&DocPerf_Xps_LoadRequests_Start, a3, a4, &v54);
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &ppv,
    0);
  ppv = 0;
  v8 = CoCreateInstance(&CLSID_SAXXMLReader60, 0, 0x17u, &IID_ISAXXMLReader, &ppv);
  if ( v8 < 0 )
  {
    std::wstring::wstring(v51, L"CoCreateInstance fails for CLSID_SAXXMLReader60 class and IID_ISAXXMLReader interface");
    v10 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v52, v51);
    v11 = win_musl::Formatter::c_str(v10);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0xF6u,
      v8,
      (__int64)v11);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v12 = operator new(0x138u, v7, v9);
  v15 = v12;
  v46 = v12;
  if ( v12 )
  {
    *(_QWORD *)v12 = &xpssig::sigdef::SigDefsContentHandler::`vftable';
    v16 = L"http://schemas.openxps.org/oxps/v1.0/signature-definitions";
    if ( a2 != 1 )
      v16 = L"http://schemas.microsoft.com/xps/2005/06/signature-definitions";
    *((_QWORD *)v12 + 1) = v16;
    *((_QWORD *)v12 + 2) = a3;
    v12[6] = 0;
    xpssig::sigdef::SigDefElement::SigDefElement((xpssig::sigdef::SigDefElement *)(v12 + 8));
    v15[66] = 0;
    std::wstring::wstring(v15 + 68, v17);
    std::wstring::reserve();
    *(_QWORD *)v15 = &win_musl::UnknownOnlyLite<xpssig::sigdef::SigDefsContentHandler,win_mp_lib::type_list<ISAXContentHandler,win_mp_lib::type_list<IUnknown,win_mp_lib::null_type>>,win_mp_lib::null_type>::`vftable';
    v15[76] = 0;
    _InterlockedIncrement(&win_musl::g_comObjectInstanceCount);
  }
  else
  {
    v15 = 0;
  }
  v18 = 0;
  v50 = 0;
  if ( v15 )
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v15 + 8LL))(v15);
    v18 = v15;
    v50 = v15;
  }
  v19 = operator new(1u, v13, v14);
  v49 = 0;
  if ( v19 )
  {
    v20 = (win_scope::counted_strong_weak_base *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v21 = v20;
    if ( !v20 )
    {
      operator delete(v19);
      win_scope::report_policy_throw::report_init_failure();
    }
    *((_QWORD *)v20 + 1) = 0;
    *(_QWORD *)v20 = &win_scope::counted_strong_weak<win_musl::consumption::NullSaxErrorHandler *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
    *((_QWORD *)v20 + 2) = v19;
    *(_QWORD *)&v49 = v20;
    win_scope::counted_strong_weak_base::AddRef(v20);
    *((_QWORD *)&v49 + 1) = v19;
  }
  else
  {
    v19 = (void *)*((_QWORD *)&v49 + 1);
    v21 = (win_scope::counted_strong_weak_base *)v49;
  }
  v22 = win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(
          &v54,
          &v49);
  win_musl::UnknownOnly<win_musl::consumption::SaxErrorHandlerCom<win_scope::scope<win_musl::consumption::NullSaxErrorHandler *,win_scope::const_policies<win_scope::shared_policies>>,ISAXErrorHandler,win_musl::InnerCom<win_scope::scope<win_musl::consumption::NullSaxErrorHandler *,win_scope::const_policies<win_scope::shared_policies>>,ISAXErrorHandler,win_scope::report_policy_throw>>,win_mp_lib::type_list<ISAXErrorHandler,win_mp_lib::null_type>,win_mp_lib::null_type>::CreateInstance<win_scope::scope<win_musl::consumption::NullSaxErrorHandler *,win_scope::const_policies<win_scope::shared_policies>>>(
    &v46,
    v22);
  v23 = v46;
  win_scope::scope<xpsom::TXpsOMPage *,win_scope::const_policies<win_scope::com_policies>>::scope<xpsom::TXpsOMPage *,win_scope::const_policies<win_scope::com_policies>>(
    &v42,
    v46);
  v45 = 2;
  win_musl::consumption::SaxErrorHandler::SaxErrorHandler(&v48, &v42);
  v45 = 3;
  if ( v23 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v23 + 16LL))(v23);
  v47 = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v47,
    v18);
  v24 = win_musl::consumption::MarkupQuery::MarkupQuery(&v41, &v47);
  v25 = &qword_180229800;
  if ( a2 != 1 )
    v25 = &qword_1802297F0;
  win_musl::consumption::CreateMarkupQueryKnownNs<win_musl::sax::ns const *>(&v42, v25, v25 + 2);
  v45 = 7;
  win_musl::consumption::CreateMarkupCompatibilityFilter(&v54, &v42, v24, &v48);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v41 )
  {
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v48 )
  {
    (*((void (__fastcall **)(void (__fastcall **)(_QWORD, _QWORD, _QWORD)))*v48 + 2))(v48);
    v48 = 0;
  }
  v26 = win_musl::consumption::CreateSaxContentHandler<win_scope::scope<win_musl::consumption::MarkupCompatibility *,win_scope::const_policies<win_scope::shared_policies>>>(
          &v42,
          &v54);
  win_dox::XpsDocumentRelationshipCollection::GetInterface(v26, &v46);
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  v47 = 0;
  v51[0] = 13;
  v51[1] = a1;
  v27 = v46;
  v28 = (*(__int64 (__fastcall **)(LPVOID, _DWORD *))(*(_QWORD *)ppv + 80LL))(ppv, v46);
  if ( v28 < 0 )
  {
    std::wstring::wstring(v51, L"ISAXXMLReader::putContentHandler fails");
    v29 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v52, v51);
    v30 = win_musl::Formatter::c_str(v29);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x123u,
      v28,
      (__int64)v30);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v31 = ppv;
  v48 = *(void (__fastcall ***)(_QWORD, _QWORD, _QWORD))ppv;
  v32 = SysAllocString(L"prohibit-dtd");
  v33 = v32;
  v34 = 0;
  v41 = 0;
  if ( v32 )
  {
    v34 = v32;
    v41 = v32;
  }
  ((void (__fastcall **)(LPVOID, BSTR, __int64))v48)[4](v31, v32, 0xFFFFFFFFLL);
  if ( v33 )
    SysFreeString(v34);
  v51[2] = v47;
  v35 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 152LL))(ppv, v51);
  v36 = *(_QWORD *)&v54.Size;
  v41 = 0;
  win_musl::consumption::MarkupCompatibility::PutDocumentLocator(
    *(win_musl::consumption::MarkupCompatibility **)&v54.Size,
    (struct win_musl::consumption::SaxLocator *)&v41);
  if ( v41 )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v35 < 0 || (v35 = v18[66], v35 < 0) )
  {
    v38 = v18 + 68;
    if ( *((_QWORD *)v18 + 37) > 7u )
      v38 = (_QWORD *)*v38;
    std::wstring::wstring(v51, v38);
    v39 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v52, v51);
    v40 = win_musl::Formatter::c_str(v39);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x134u,
      v35,
      (__int64)v40);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v37 = win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(
          &v41,
          &ppv);
  win_musl::consumption::ValidateSaxEncoding(v37);
  if ( v27 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v54.Ptr && v36 )
    ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(&v54);
  if ( v21 && v19 )
    ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(&v49);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v18 + 16LL))(v18);
  xpssig::sigdef::LoadRequestsAutoEvent::~LoadRequestsAutoEvent((xpssig::sigdef::LoadRequestsAutoEvent *)v44);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x1800d84fc  push    rbp
0x1800d84fe  push    rbx
0x1800d84ff  push    rsi
0x1800d8500  push    rdi
0x1800d8501  push    r12
0x1800d8503  push    r13
0x1800d8505  push    r14
0x1800d8507  push    r15
0x1800d8509  lea     rbp, [rsp-0C8h]
0x1800d8511  sub     rsp, 1C8h
0x1800d8518  mov     rax, cs:__security_cookie
0x1800d851f  xor     rax, rsp
0x1800d8522  mov     [rbp+100h+var_50], rax
0x1800d8529  mov     rsi, r8
0x1800d852c  mov     r12d, edx
0x1800d852f  mov     r13, rcx
0x1800d8532  xor     r14d, r14d
0x1800d8535  mov     [rsp+200h+var_1A4], r14d
0x1800d853a  mov     [rsp+200h+var_1B0], r14
0x1800d853f  test    byte ptr cs:Microsoft_Windows_DocumentsEnableBits, 2
0x1800d8546  jz      short loc_1800D8561
0x1800d8548  lea     rax, [rbp+100h+var_60]
0x1800d854f  mov     [rsp+200h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x1800d8554  lea     rdx, DocPerf_Xps_LoadRequests_Start; int
0x1800d855b  call    McGenEventWrite_EventWriteTransfer
0x1800d8560  nop
0x1800d8561  xor     edx, edx
0x1800d8563  lea     rcx, [rsp+200h+var_1B0]
0x1800d8568  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1800d856d  mov     [rsp+200h+var_1B0], r14
0x1800d8572  lea     rax, [rsp+200h+var_1B0]
0x1800d8577  mov     [rsp+200h+ppv], rax; ppv
0x1800d857c  lea     r9, IID_ISAXXMLReader; riid
0x1800d8583  xor     edx, edx; pUnkOuter
0x1800d8585  lea     r8d, [rdx+17h]; dwClsContext
0x1800d8589  lea     rcx, CLSID_SAXXMLReader60; rclsid
0x1800d8590  call    cs:__imp_CoCreateInstance
0x1800d8596  mov     ebx, eax
0x1800d8598  test    eax, eax
0x1800d859a  jns     short loc_1800D85FC
0x1800d859c  lea     rdx, aCocreateinstan; "CoCreateInstance fails for CLSID_SAXXML"...
0x1800d85a3  lea     rcx, [rbp+100h+var_170]
0x1800d85a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d85ac  nop
0x1800d85ad  lea     rdx, [rbp+100h+var_170]
0x1800d85b1  lea     rcx, [rbp+100h+var_150]
0x1800d85b5  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800d85ba  nop
0x1800d85bb  mov     rcx, rax; this
0x1800d85be  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800d85c3  mov     [rsp+200h+var_1D0], rax; __int64
0x1800d85c8  mov     [rsp+200h+var_1D8], ebx; int
0x1800d85cc  mov     dword ptr [rsp+200h+ppv], 0F6h; unsigned int
0x1800d85d4  lea     r9, Src
0x1800d85db  lea     r8, aNoFilename; "(no filename)"
0x1800d85e2  lea     rcx, [rbp+100h+pExceptionObject]; this
0x1800d85e6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d85eb  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d85f2  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x1800d85f6  call    _CxxThrowException_0
0x1800d85fc  mov     ecx, 138h; unsigned __int64
0x1800d8601  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800d8606  mov     rdi, rax
0x1800d8609  mov     [rsp+200h+var_1A0], rax
0x1800d860e  test    rax, rax
0x1800d8611  jz      short loc_1800D867C
0x1800d8613  lea     rax, ??_7SigDefsContentHandler@sigdef@xpssig@@6B@; const xpssig::sigdef::SigDefsContentHandler::`vftable'
0x1800d861a  mov     [rdi], rax
0x1800d861d  lea     rax, ?gc_SignatureDefinitions@MsXps@XpsDocument@XmlNamespaceUris@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800d8624  lea     rcx, ?gc_SignatureDefinitions@OpenXps@XpsDocument@XmlNamespaceUris@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/si"...
0x1800d862b  cmp     r12d, 1
0x1800d862f  cmovnz  rcx, rax
0x1800d8633  mov     [rdi+8], rcx
0x1800d8637  mov     [rdi+10h], rsi
0x1800d863b  xor     esi, esi
0x1800d863d  mov     [rdi+18h], esi
0x1800d8640  lea     rcx, [rdi+20h]; this
0x1800d8644  call    ??0SigDefElement@sigdef@xpssig@@QEAA@XZ; xpssig::sigdef::SigDefElement::SigDefElement(void)
0x1800d8649  nop
0x1800d864a  mov     [rdi+108h], esi
0x1800d8650  lea     rcx, [rdi+110h]
0x1800d8657  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d865c  nop
0x1800d865d  call    ?reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x1800d8662  nop
0x1800d8663  lea     rax, ??_7?$UnknownOnlyLite@VSigDefsContentHandler@sigdef@xpssig@@V?$type_list@UISAXContentHandler@@V?$type_list@UIUnknown@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@Vnull_type@5@@win_musl@@6B@; const win_musl::UnknownOnlyLite<xpssig::sigdef::SigDefsContentHandler,win_mp_lib::type_list<ISAXContentHandler,win_mp_lib::type_list<IUnknown,win_mp_lib::null_type>>,win_mp_lib::null_type>::`vftable'
0x1800d866a  mov     [rdi], rax
0x1800d866d  mov     [rdi+130h], esi
0x1800d8673  lock inc cs:?g_comObjectInstanceCount@win_musl@@3JC; long volatile win_musl::g_comObjectInstanceCount
0x1800d867a  jmp     short loc_1800D8680
0x1800d867c  xor     esi, esi
0x1800d867e  mov     edi, esi
0x1800d8680  mov     rbx, rsi
0x1800d8683  mov     [rbp+100h+var_178], rbx
0x1800d8687  test    rdi, rdi
0x1800d868a  jz      short loc_1800D86A2
0x1800d868c  mov     rax, [rdi]
0x1800d868f  mov     rcx, rdi
0x1800d8692  mov     rax, [rax+8]
0x1800d8696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d869b  mov     rbx, rdi
0x1800d869e  mov     [rbp+100h+var_178], rbx
0x1800d86a2  mov     ecx, 1; unsigned __int64
0x1800d86a7  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800d86ac  mov     r15, rax
0x1800d86af  xorps   xmm0, xmm0
0x1800d86b2  movdqu  [rsp+200h+var_188], xmm0
0x1800d86b8  test    rax, rax
0x1800d86bb  jz      short loc_1800D8712
0x1800d86bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d86c4  mov     ecx, 18h; unsigned __int64
0x1800d86c9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d86ce  mov     r14, rax
0x1800d86d1  test    rax, rax
0x1800d86d4  jz      short loc_1800D86FF
0x1800d86d6  mov     qword ptr [rax+8], 0
0x1800d86de  lea     rax, ??_7?$counted_strong_weak@PEAVNullSaxErrorHandler@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::NullSaxErrorHandler *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x1800d86e5  mov     [r14], rax
0x1800d86e8  mov     [r14+10h], r15
0x1800d86ec  mov     qword ptr [rsp+200h+var_188], r14
0x1800d86f1  mov     rcx, r14; this
0x1800d86f4  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x1800d86f9  mov     qword ptr [rbp+100h+var_188+8], r15
0x1800d86fd  jmp     short loc_1800D871B
0x1800d86ff  mov     edx, 1
0x1800d8704  mov     rcx, r15; Block
0x1800d8707  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d870c  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x1800d8712  mov     r15, qword ptr [rbp+100h+var_188+8]
0x1800d8716  mov     r14, qword ptr [rsp+200h+var_188]
0x1800d871b  lea     rdx, [rsp+200h+var_188]
0x1800d8720  lea     rcx, [rbp+100h+var_60]
0x1800d8727  call    ??0?$scope@PEAV?$ReceiverStore@VXpsPageReceiver@win_dox@@$00@production_helper@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>> const &)
0x1800d872c  mov     rdx, rax
0x1800d872f  lea     rcx, [rsp+200h+var_1A0]
0x1800d8734  call    ??$CreateInstance@V?$scope@PEAVNullSaxErrorHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@?$UnknownOnly@V?$SaxErrorHandlerCom@V?$scope@PEAVNullSaxErrorHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UISAXErrorHandler@@V?$InnerCom@V?$scope@PEAVNullSaxErrorHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UISAXErrorHandler@@Ureport_policy_throw@2@@win_musl@@@consumption@win_musl@@V?$type_list@UISAXErrorHandler@@Vnull_type@win_mp_lib@@@win_mp_lib@@Vnull_type@5@@win_musl@@SA?AV?$scope@PEAV?$UnknownOnly@V?$SaxErrorHandlerCom@V?$scope@PEAVNullSaxErrorHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UISAXErrorHandler@@V?$InnerCom@V?$scope@PEAVNullSaxErrorHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UISAXErrorHandler@@Ureport_policy_throw@2@@win_musl@@@consumption@win_musl@@V?$type_list@UISAXErrorHandler@@Vnull_type@win_mp_lib@@@win_mp_lib@@Vnull_type@5@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVNullSaxErrorHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@3@@Z; win_musl::UnknownOnly<win_musl::consumption::SaxErrorHandlerCom<win_scope::scope<win_musl::consumption::NullSaxErrorHandler *,win_scope::const_policies<win_scope::shared_policies>>,ISAXErrorHandler,win_musl::InnerCom<win_scope::scope<win_musl::consumption::NullSaxErrorHandler *,win_scope::const_policies<win_scope::shared_policies>>,ISAXErrorHandler,win_scope::report_policy_throw>>,win_mp_lib::type_list<ISAXErrorHandler,win_mp_lib::null_type>,win_mp_lib::null_type>::CreateInstance<win_scope::scope<win_musl::consumption::NullSaxErrorHandler *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_musl::consumption::NullSaxErrorHandler *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800d8739  nop
0x1800d873a  mov     rdi, [rsp+200h+var_1A0]
0x1800d873f  mov     rdx, rdi
0x1800d8742  lea     rcx, [rsp+200h+var_1B8]
0x1800d8747  call    ??0?$scope@PEAVTXpsOMPage@xpsom@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVTXpsOMPage@xpsom@@@Z; win_scope::scope<xpsom::TXpsOMPage *,win_scope::const_policies<win_scope::com_policies>>::scope<xpsom::TXpsOMPage *,win_scope::const_policies<win_scope::com_policies>>(xpsom::TXpsOMPage *)
0x1800d874c  mov     [rsp+200h+var_1A4], 2
0x1800d8754  lea     rdx, [rsp+200h+var_1B8]
0x1800d8759  lea     rcx, [rsp+200h+var_190]
0x1800d875e  call    ??0SaxErrorHandler@consumption@win_musl@@QEAA@V?$scope@PEAUISAXErrorHandler@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::consumption::SaxErrorHandler::SaxErrorHandler(win_scope::scope<ISAXErrorHandler *,win_scope::const_policies<win_scope::com_policies>>)
0x1800d8763  mov     [rsp+200h+var_1A4], 3
0x1800d876b  test    rdi, rdi
0x1800d876e  jz      short loc_1800D8780
0x1800d8770  mov     rax, [rdi]
0x1800d8773  mov     rcx, rdi
0x1800d8776  mov     rax, [rax+10h]
0x1800d877a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d877f  nop
0x1800d8780  mov     [rsp+200h+var_198], rsi
0x1800d8785  mov     rdx, rbx
0x1800d8788  lea     rcx, [rsp+200h+var_198]
0x1800d878d  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1800d8792  lea     rdx, [rsp+200h+var_198]
0x1800d8797  lea     rcx, [rsp+200h+var_1C0]
0x1800d879c  call    ??0MarkupQuery@consumption@win_musl@@QEAA@V?$scope@PEAUIMarkupQuery@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::consumption::MarkupQuery::MarkupQuery(win_scope::scope<IMarkupQuery *,win_scope::const_policies<win_scope::com_policies>>)
0x1800d87a1  mov     rdi, rax
0x1800d87a4  lea     rax, qword_1802297F0
0x1800d87ab  lea     rdx, qword_180229800
0x1800d87b2  cmp     r12d, 1
0x1800d87b6  cmovnz  rdx, rax
0x1800d87ba  lea     r8, [rdx+10h]
0x1800d87be  lea     rcx, [rsp+200h+var_1B8]
0x1800d87c3  call    ??$CreateMarkupQueryKnownNs@PEBUns@sax@win_musl@@@consumption@win_musl@@YA?AVMarkupQuery@01@PEBUns@sax@1@0@Z; win_musl::consumption::CreateMarkupQueryKnownNs<win_musl::sax::ns const *>(win_musl::sax::ns const *,win_musl::sax::ns const *)
0x1800d87c8  mov     [rsp+200h+var_1A4], 7
0x1800d87d0  lea     r9, [rsp+200h+var_190]
0x1800d87d5  mov     r8, rdi
0x1800d87d8  lea     rdx, [rsp+200h+var_1B8]
0x1800d87dd  lea     rcx, [rbp+100h+var_60]
0x1800d87e4  call    ?CreateMarkupCompatibilityFilter@consumption@win_musl@@YA?AV?$scope@PEAVMarkupCompatibility@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEAVMarkupQuery@12@AEAVSaxContentHandler@12@AEAVSaxErrorHandler@12@@Z; win_musl::consumption::CreateMarkupCompatibilityFilter(win_musl::consumption::MarkupQuery &,win_musl::consumption::SaxContentHandler &,win_musl::consumption::SaxErrorHandler &)
0x1800d87e9  nop
0x1800d87ea  mov     rcx, [rsp+200h+var_1B8]
0x1800d87ef  test    rcx, rcx
0x1800d87f2  jz      short loc_1800D8801
0x1800d87f4  mov     rax, [rcx]
0x1800d87f7  mov     rax, [rax+10h]
0x1800d87fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8800  nop
0x1800d8801  mov     rcx, [rsp+200h+var_1C0]
0x1800d8806  test    rcx, rcx
0x1800d8809  jz      short loc_1800D881C
0x1800d880b  mov     rax, [rcx]
0x1800d880e  mov     rax, [rax+10h]
0x1800d8812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8817  mov     [rsp+200h+var_1C0], rsi
0x1800d881c  mov     rcx, [rsp+200h+var_190]
0x1800d8821  test    rcx, rcx
0x1800d8824  jz      short loc_1800D8837
0x1800d8826  mov     rax, [rcx]
0x1800d8829  mov     rax, [rax+10h]
0x1800d882d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8832  mov     [rsp+200h+var_190], rsi
0x1800d8837  lea     rdx, [rbp+100h+var_60]
0x1800d883e  lea     rcx, [rsp+200h+var_1B8]
0x1800d8843  call    ??$CreateSaxContentHandler@V?$scope@PEAVMarkupCompatibility@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@consumption@win_musl@@YA?AVSaxContentHandler@01@AEAV?$scope@PEAVMarkupCompatibility@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::consumption::CreateSaxContentHandler<win_scope::scope<win_musl::consumption::MarkupCompatibility *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_musl::consumption::MarkupCompatibility *,win_scope::const_policies<win_scope::shared_policies>> &)
0x1800d8848  nop
0x1800d8849  lea     rdx, [rsp+200h+var_1A0]
0x1800d884e  mov     rcx, rax
0x1800d8851  call    ?GetInterface@XpsDocumentRelationshipCollection@win_dox@@QEBA?AV?$scope@PEAUIXpsDocumentRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsDocumentRelationshipCollection::GetInterface(void)
0x1800d8856  nop
0x1800d8857  mov     rcx, [rsp+200h+var_1B8]
0x1800d885c  test    rcx, rcx
0x1800d885f  jz      short loc_1800D8872
0x1800d8861  mov     rax, [rcx]
0x1800d8864  mov     rax, [rax+10h]
0x1800d8868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d886d  mov     [rsp+200h+var_1B8], rsi
0x1800d8872  xorps   xmm0, xmm0
0x1800d8875  xor     eax, eax
0x1800d8877  mov     [rsp+200h+var_198], rax
0x1800d887c  movups  [rbp+100h+var_170], xmm0
0x1800d8880  mov     eax, 0Dh
0x1800d8885  mov     word ptr [rbp+100h+var_170], ax
0x1800d8889  mov     qword ptr [rbp+100h+var_170+8], r13
0x1800d888d  mov     rcx, [rsp+200h+var_1B0]
0x1800d8892  mov     rax, [rcx]
0x1800d8895  mov     rsi, [rsp+200h+var_1A0]
0x1800d889a  mov     rdx, rsi
0x1800d889d  mov     rax, [rax+50h]
0x1800d88a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d88a6  mov     edi, eax
0x1800d88a8  test    eax, eax
0x1800d88aa  jns     short loc_1800D890C
0x1800d88ac  lea     rdx, aIsaxxmlreaderP; "ISAXXMLReader::putContentHandler fails"
0x1800d88b3  lea     rcx, [rbp+100h+var_170]
0x1800d88b7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d88bc  nop
0x1800d88bd  lea     rdx, [rbp+100h+var_170]
0x1800d88c1  lea     rcx, [rbp+100h+var_150]
0x1800d88c5  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800d88ca  nop
0x1800d88cb  mov     rcx, rax; this
0x1800d88ce  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800d88d3  mov     [rsp+200h+var_1D0], rax; __int64
0x1800d88d8  mov     [rsp+200h+var_1D8], edi; int
0x1800d88dc  mov     dword ptr [rsp+200h+ppv], 123h; unsigned int
0x1800d88e4  lea     r9, Src
0x1800d88eb  lea     r8, aNoFilename; "(no filename)"
0x1800d88f2  lea     rcx, [rbp+100h+pExceptionObject]; this
0x1800d88f6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d88fb  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d8902  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x1800d8906  call    _CxxThrowException_0
0x1800d890c  mov     r13, [rsp+200h+var_1B0]
0x1800d8911  mov     rax, [r13+0]
0x1800d8915  mov     [rsp+200h+var_190], rax
0x1800d891a  lea     rcx, aProhibitDtd; "prohibit-dtd"
0x1800d8921  call    cs:__imp_SysAllocString
0x1800d8927  mov     r12, rax
0x1800d892a  xor     edi, edi
0x1800d892c  mov     [rsp+200h+var_1C0], rdi
0x1800d8931  test    rax, rax
0x1800d8934  jz      short loc_1800D893E
0x1800d8936  mov     rdi, rax
0x1800d8939  mov     [rsp+200h+var_1C0], rax
0x1800d893e  or      r8d, 0FFFFFFFFh
0x1800d8942  mov     rdx, r12
0x1800d8945  mov     rcx, r13
0x1800d8948  mov     rax, [rsp+200h+var_190]
0x1800d894d  mov     rax, [rax+20h]
0x1800d8951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8956  nop
0x1800d8957  test    r12, r12
0x1800d895a  jz      short loc_1800D8965
0x1800d895c  mov     rcx, rdi; bstrString
0x1800d895f  call    cs:__imp_SysFreeString
0x1800d8965  mov     rcx, [rsp+200h+var_1B0]
0x1800d896a  movups  xmm0, [rbp+100h+var_170]
0x1800d896e  movaps  [rbp+100h+var_170], xmm0
0x1800d8972  movsd   xmm1, [rsp+200h+var_198]
0x1800d8978  movsd   [rbp+100h+var_160], xmm1
0x1800d897d  mov     rax, [rcx]
0x1800d8980  lea     rdx, [rbp+100h+var_170]
0x1800d8984  mov     rax, [rax+98h]
0x1800d898b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8990  mov     edi, eax
0x1800d8992  mov     r12, qword ptr [rbp+100h+var_60.Size]
0x1800d8999  mov     [rsp+200h+var_1C0], 0
0x1800d89a2  lea     rdx, [rsp+200h+var_1C0]; struct win_musl::consumption::SaxLocator *
0x1800d89a7  mov     rcx, r12; this
0x1800d89aa  call    ?PutDocumentLocator@MarkupCompatibility@consumption@win_musl@@QEAAXAEAVSaxLocator@23@@Z; win_musl::consumption::MarkupCompatibility::PutDocumentLocator(win_musl::consumption::SaxLocator &)
0x1800d89af  nop
0x1800d89b0  mov     rcx, [rsp+200h+var_1C0]
0x1800d89b5  test    rcx, rcx
0x1800d89b8  jz      short loc_1800D89C7
0x1800d89ba  mov     rax, [rcx]
0x1800d89bd  mov     rax, [rax+10h]
0x1800d89c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d89c6  nop
0x1800d89c7  test    edi, edi
0x1800d89c9  js      loc_1800D8A90
0x1800d89cf  mov     edi, [rbx+108h]
0x1800d89d5  test    edi, edi
0x1800d89d7  js      loc_1800D8A90
0x1800d89dd  lea     rdx, [rsp+200h+var_1B0]
0x1800d89e2  lea     rcx, [rsp+200h+var_1C0]
  ... truncated ...
```
