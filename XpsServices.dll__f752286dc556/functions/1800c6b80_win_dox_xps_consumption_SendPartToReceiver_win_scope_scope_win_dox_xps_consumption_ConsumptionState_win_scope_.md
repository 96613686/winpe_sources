# win_dox::xps_consumption::SendPartToReceiver(win_scope::scope<win_dox::xps_consumption::ConsumptionState *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,win_dox::XpsPackageRelationshipReceiver &,win_dox::OpcPartUri &,win_musl::Model::Relationship const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,__MIDL___MIDL_itf_msopc_0000_0002_0002,win_dox::OpcPartContent &)

- ea: `0x1800c6b80`
- end: `0x1800c7c7a`
- name: `?SendPartToReceiver@xps_consumption@win_dox@@YAXV?$scope@PEAVConsumptionState@xps_consumption@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@AEAVXpsPackageRelationshipReceiver@2@AEAVOpcPartUri@2@AEBVRelationship@Model@win_musl@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@AEAVOpcPartContent@2@@Z`
- size: `4346`
- prototype: ``
- caller_count: `1`
- callee_count: `46`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018f110`

## callees

- `0x18000310c`
- `0x180003ab8`
- `0x1800041b0`
- `0x180012450`
- `0x18001e634`
- `0x1800228a4`
- `0x180025bc0`
- `0x18002728c`
- `0x180027ebc`
- `0x180028138`
- `0x18003ac50`
- `0x18003c7f8`
- `0x18005d680`
- `0x18005ed5c`
- `0x180064718`
- `0x18007e43c`
- `0x1800886b4`
- `0x180088a18`
- `0x18009e764`
- `0x1800a2f94`
- `0x1800ac64c`
- `0x1800ad46c`
- `0x1800b08ac`
- `0x1800b1798`
- `0x1800b76e8`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c20c4`
- `0x1800c40b8`
- `0x1800c58c0`
- `0x1800c5da0`
- `0x1800c5dd8`
- `0x1800c6b80`
- `0x1800c8ac4`
- `0x1800ca4bc`
- `0x1800cabd8`
- `0x1800cbe40`
- `0x1800ef660`
- `0x18010f260`
- `0x180119878`
- `0x180134b70`
- `0x18013578c`
- `0x1801359ce`
- `0x180193374`
- `0x1801941dc`
- `0x1801c7010`

## string_xrefs

- `0x1800c6c65`: `http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail`
- `0x1800c6f11`: `http://schemas.openxmlformats.org/package/2006/relationships/metadata/core-properties`
- `0x1800c70a3`: `http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/origin`
- `0x1800c6eb7`: `http://schemas.microsoft.com/xps/2005/06/discard-control`
- `0x1800c7499`: `http://schemas.microsoft.com/xps/2005/06/discard-control`
- `0x1800c757b`: `http://schemas.microsoft.com/xps/2005/06/discard-control`
- `0x1800c6ee4`: `http://schemas.openxps.org/oxps/v1.0/discard-control`
- `0x1800c750a`: `http://schemas.openxps.org/oxps/v1.0/discard-control`
- `0x1800c6c0b`: `http://schemas.microsoft.com/xps/2005/06/fixedrepresentation`
- `0x1800c7908`: `http://schemas.microsoft.com/xps/2005/06/fixedrepresentation`
- `0x1800c79ea`: `http://schemas.microsoft.com/xps/2005/06/fixedrepresentation`
- `0x1800c6c38`: `http://schemas.openxps.org/oxps/v1.0/fixedrepresentation`
- `0x1800c7979`: `http://schemas.openxps.org/oxps/v1.0/fixedrepresentation`
- `0x1800c7430`: `Very Unexpected - GetPackageType must return Open or MS XPS`
- `0x1800c78a1`: `Very Unexpected - GetPackageType must return Open or MS XPS`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
void __fastcall win_dox::xps_consumption::SendPartToReceiver(
        __int64 a1,
        win_dox::XpsPackageRelationshipReceiver *a2,
        struct win_dox::OpcPartUri *a3,
        const wchar_t *a4,
        wchar_t *a5,
        enum __MIDL___MIDL_itf_msopc_0000_0002_0002 a6,
        __int64 a7)
{
  struct win_dox::OpcPartUri *v8; // r12
  const wchar_t *v11; // r14
  __int64 *v12; // rcx
  const wchar_t *v13; // rcx
  __int64 *v14; // rcx
  __int64 v15; // rax
  __int64 Bytes; // rax
  const struct win_dox::ByteCollection *XpsByteCollection; // rbx
  const struct win_dox::Uri *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  const struct win_dox::ByteCollection *v21; // rbx
  const struct win_dox::Uri *v22; // rax
  win_musl::Formatter *v23; // rax
  const wchar_t *v24; // rax
  __int64 *v25; // rcx
  __int64 *v26; // rcx
  __int64 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  const struct win_dox::ByteCollection *v30; // rbx
  const struct win_dox::Uri *v31; // rax
  win_musl::Formatter *v32; // rax
  const wchar_t *v33; // rax
  __int64 *v34; // rcx
  __int64 v35; // rax
  win_musl::Formatter *v36; // rax
  const wchar_t *v37; // rax
  const struct win_musl::ContentType *v38; // rdx
  win_musl::Formatter *v39; // rax
  const wchar_t *v40; // rax
  __int64 Relationships; // rax
  const char *v42; // rdx
  unsigned int v43; // r8d
  __int64 v44; // rax
  __int64 v45; // r10
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  const struct win_dox::ByteCollection *v49; // rbx
  const struct win_dox::Uri *v50; // rax
  win_dox::xps_consumption::ConsumptionState *v51; // rcx
  unsigned int v52; // eax
  __int64 *v53; // rcx
  __int64 *v54; // rcx
  __int64 *v55; // rcx
  bool v56; // zf
  __int64 v57; // rax
  __int64 v58; // rax
  unsigned int v59; // eax
  unsigned int v60; // r8d
  int *v61; // r13
  __int64 *v62; // rcx
  void **v63; // r15
  const struct win_dox::ByteCollection *v64; // rbx
  _QWORD *v65; // r14
  __int64 v66; // rax
  const struct win_dox::Uri *v67; // rax
  win_musl::Formatter *v68; // rax
  const wchar_t *v69; // rax
  win_dox::xps_consumption::ConsumptionState *v70; // rcx
  unsigned int PackageType; // eax
  __int64 *v72; // rcx
  __int64 *v73; // rcx
  __int64 *v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  const char *v77; // rdx
  unsigned int v78; // r8d
  win_dox::OpcPartUri *v79; // rbx
  win_dox::XpsPackageRelationshipReceiver *v80; // r14
  win_scope::counted_strong_weak_base *v81; // rax
  win_scope::counted_strong_weak_base *v82; // r14
  __int64 v83; // rax
  const struct win_dox::Uri *PartReference; // rax
  bool v85[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct win_dox::OpcPartUri *v86; // [rsp+48h] [rbp-B8h] BYREF
  void **v87; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v88; // [rsp+58h] [rbp-A8h]
  __int64 v89; // [rsp+60h] [rbp-A0h] BYREF
  void **v90; // [rsp+68h] [rbp-98h] BYREF
  __int64 v91; // [rsp+70h] [rbp-90h]
  __int128 v92; // [rsp+78h] [rbp-88h] BYREF
  __int128 v93; // [rsp+88h] [rbp-78h] BYREF
  win_dox::XpsPackageRelationshipReceiver *v94; // [rsp+98h] [rbp-68h] BYREF
  __int64 v95; // [rsp+A0h] [rbp-60h]
  int v96; // [rsp+A8h] [rbp-58h]
  void **v97; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v98; // [rsp+B8h] [rbp-48h]
  __int64 v99; // [rsp+C0h] [rbp-40h]
  _BYTE v100[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v102[128]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v103[80]; // [rsp+210h] [rbp+110h] BYREF

  v8 = a3;
  v86 = a3;
  v94 = a2;
  v11 = a5;
  v99 = a1;
  *(_QWORD *)&v93 = a7;
  win_musl::ContentTypeFromStdString(v102, a5);
  LODWORD(v89) = 2;
  v96 = 2;
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v12 = (__int64 *)a4;
  else
    v12 = *(__int64 **)a4;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                          v12,
                          *((_QWORD *)a4 + 2),
                          L"http://schemas.microsoft.com/xps/2005/06/fixedrepresentation",
                          60)
    || (*((_QWORD *)a4 + 3) <= 7u ? (v13 = a4) : (v13 = *(const wchar_t **)a4),
        (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                           v13,
                           *((_QWORD *)a4 + 2),
                           L"http://schemas.openxps.org/oxps/v1.0/fixedrepresentation",
                           56)) )
  {
    v70 = *(win_dox::xps_consumption::ConsumptionState **)(a1 + 8);
    if ( *((_DWORD *)v70 + 94) == 255 )
    {
      if ( *((_QWORD *)a4 + 3) <= 7u )
        v74 = (__int64 *)a4;
      else
        v74 = *(__int64 **)a4;
      v56 = (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                               v74,
                               *((_QWORD *)a4 + 2),
                               L"http://schemas.microsoft.com/xps/2005/06/fixedrepresentation",
                               60) == 0;
      v75 = *(_QWORD *)(a1 + 8);
      if ( v56 )
      {
        v85[0] = 0;
        *(_DWORD *)(v75 + 376) = 1;
        win_dox::XpsPackageRelationshipReceiver::SetPackageType(a2, 1, v85);
        if ( !v85[0] )
        {
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::THResultException *)pExceptionObject,
            0xFFu,
            -2142109432,
            (__int64)L"XPS document type not supported");
          throw (SplException::THResultException *)pExceptionObject;
        }
        v8 = v86;
      }
      else
      {
        *(_DWORD *)(v75 + 376) = 0;
        win_dox::XpsPackageRelationshipReceiver::SetPackageType(a2, 0, v85);
      }
    }
    else
    {
      PackageType = win_dox::xps_consumption::ConsumptionState::GetPackageType(v70);
      if ( PackageType )
      {
        if ( PackageType != 1 )
        {
          win_musl::DebugLogHelper(
            "(no filename)",
            &Src,
            226,
            1024,
            -2147418113,
            L"Very Unexpected - GetPackageType must return Open or MS XPS");
          std::logic_error::logic_error((std::logic_error *)v100, "Program has entered an unexpected state");
          throw (std::logic_error *)v100;
        }
        if ( *((_QWORD *)a4 + 3) <= 7u )
          v72 = (__int64 *)a4;
        else
          v72 = *(__int64 **)a4;
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                                v72,
                                *((_QWORD *)a4 + 2),
                                L"http://schemas.microsoft.com/xps/2005/06/fixedrepresentation",
                                60) )
        {
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::THResultException *)pExceptionObject,
            0xDEu,
            -2142109680,
            (__int64)L"Unexpected relationship type");
          throw (SplException::THResultException *)pExceptionObject;
        }
      }
      else
      {
        if ( *((_QWORD *)a4 + 3) <= 7u )
          v73 = (__int64 *)a4;
        else
          v73 = *(__int64 **)a4;
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                                v73,
                                *((_QWORD *)a4 + 2),
                                L"http://schemas.openxps.org/oxps/v1.0/fixedrepresentation",
                                56) )
        {
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::THResultException *)pExceptionObject,
            0xD5u,
            -2142109680,
            (__int64)L"Unexpected relationship type");
          throw (SplException::THResultException *)pExceptionObject;
        }
      }
    }
    v76 = win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Get__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer_();
    if ( !(unsigned __int8)operator==(v102, v76) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x11Bu,
        -2142109688,
        (__int64)L"Relationship target does not have expected content type for Document Sequence");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v79 = (win_dox::OpcPartUri *)operator new(0x30u, v77, v78);
    v87 = (void **)v79;
    if ( v79 )
    {
      v80 = (win_dox::XpsPackageRelationshipReceiver *)win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(
                                                         &v93,
                                                         a1);
      v94 = v80;
      win_dox::OpcPartUri::OpcPartUri(v79, v8);
      win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(
        (char *)v79 + 24,
        v80);
      win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(
        (char *)v79 + 40,
        a7);
      if ( *(_QWORD *)v80 && *((_QWORD *)v80 + 1) )
      {
        ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(v80);
        *(_QWORD *)v80 = 0;
        *((_QWORD *)v80 + 1) = 0;
      }
    }
    else
    {
      v79 = 0;
    }
    v92 = 0;
    v94 = v79;
    if ( v79 )
    {
      v81 = (win_scope::counted_strong_weak_base *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v82 = v81;
      if ( !v81 )
      {
        win_scope::close_delete::close<win_dox::xps_consumption::XpsDocumentSequenceContentImpl>(&v94);
        win_scope::report_policy_throw::report_init_failure();
      }
      *((_QWORD *)v81 + 1) = 0;
      *(_QWORD *)v81 = &win_scope::counted_strong_weak<win_dox::xps_consumption::XpsDocumentSequenceContentImpl *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
      *((_QWORD *)v81 + 2) = v79;
      *(_QWORD *)&v92 = v81;
      win_scope::counted_strong_weak_base::AddRef(v81);
      *((_QWORD *)&v92 + 1) = v79;
    }
    else
    {
      v79 = (win_dox::OpcPartUri *)*((_QWORD *)&v92 + 1);
      v82 = (win_scope::counted_strong_weak_base *)v92;
    }
    v83 = win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(
            v100,
            &v92);
    win_dox::CreateInstanceFromInner<IXpsDocumentSequenceContent,win_scope::scope<win_dox::xps_consumption::XpsDocumentSequenceContentImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
      &v86,
      v83);
    PartReference = (const struct win_dox::Uri *)win_dox::xps_consumption::MakePartReference(&v94, a1, a4 + 16, v8);
    win_dox::XpsPackageRelationshipReceiver::SetDocumentSequence(
      a2,
      PartReference,
      a6,
      (const struct win_dox::XpsDocumentSequenceContent *)&v86);
    if ( v94 )
      (*(void (__fastcall **)(win_dox::XpsPackageRelationshipReceiver *))(*(_QWORD *)v94 + 16LL))(v94);
    if ( v86 )
      (*(void (__fastcall **)(struct win_dox::OpcPartUri *))(*(_QWORD *)v86 + 16LL))(v86);
    if ( v82 && v79 )
      ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(&v92);
    win_musl::ContentType::~ContentType((win_musl::ContentType *)v102);
    if ( *(_QWORD *)a1 && *(_QWORD *)(a1 + 8) )
    {
      ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(a1);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
  else
  {
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v14 = (__int64 *)a4;
    else
      v14 = *(__int64 **)a4;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                            v14,
                            *((_QWORD *)a4 + 2),
                            L"http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail",
                            79) )
    {
      v15 = win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Get__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer_();
      if ( (unsigned __int8)operator==(v102, v15 + 720) )
      {
        Bytes = win_dox::OpcPartContent::GetBytes(a7, &v90);
        XpsByteCollection = (const struct win_dox::ByteCollection *)win_dox::xps_consumption::MakeXpsByteCollection(
                                                                      &v87,
                                                                      a1,
                                                                      Bytes);
        v18 = (const struct win_dox::Uri *)win_dox::xps_consumption::MakePartReference(&v86, a1, a4 + 16, v8);
        win_dox::XpsPackageRelationshipReceiver::SetJpegThumbnail(a2, v18, a6, XpsByteCollection);
        if ( v86 )
        {
          (*(void (__fastcall **)(struct win_dox::OpcPartUri *))(*(_QWORD *)v86 + 16LL))(v86);
          v86 = 0;
        }
        v87 = &win_dox::OpcRelationshipCollection::`vftable';
        if ( v88 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
          v88 = 0;
        }
        v90 = &win_dox::OpcRelationshipCollection::`vftable';
        if ( v91 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      }
      else
      {
        v19 = win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Get__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer_();
        if ( !(unsigned __int8)operator==(v102, v19 + 840) )
        {
          std::wstring::wstring(v100, L"Relationship target does not have expected content type for Thumbnail");
          v23 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v103, v100);
          v24 = win_musl::Formatter::c_str(v23);
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::THResultException *)pExceptionObject,
            0x13Au,
            -2142109688,
            (__int64)v24);
          throw (SplException::THResultException *)pExceptionObject;
        }
        v20 = win_dox::OpcPartContent::GetBytes(a7, &v90);
        v21 = (const struct win_dox::ByteCollection *)win_dox::xps_consumption::MakeXpsByteCollection(&v87, a1, v20);
        v22 = (const struct win_dox::Uri *)win_dox::xps_consumption::MakePartReference(&v86, a1, a4 + 16, v8);
        win_dox::XpsPackageRelationshipReceiver::SetPngThumbnail(a2, v22, a6, v21);
        if ( v86 )
        {
          (*(void (__fastcall **)(struct win_dox::OpcPartUri *))(*(_QWORD *)v86 + 16LL))(v86);
          v86 = 0;
        }
        v87 = &win_dox::OpcRelationshipCollection::`vftable';
        if ( v88 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
          v88 = 0;
        }
        v90 = &win_dox::OpcRelationshipCollection::`vftable';
        if ( v91 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      }
LABEL_49:
      win_musl::ContentType::~ContentType((win_musl::ContentType *)v102);
      if ( *(_QWORD *)a1 )
      {
        if ( *(_QWORD *)(a1 + 8) )
        {
          ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(a1);
          *(_QWORD *)a1 = 0;
          *(_QWORD *)(a1 + 8) = 0;
        }
      }
      return;
    }
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v25 = (__int64 *)a4;
    else
      v25 = *(__int64 **)a4;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                            v25,
                            *((_QWORD *)a4 + 2),
                            L"http://schemas.microsoft.com/xps/2005/06/discard-control",
                            56)
      || (*((_QWORD *)a4 + 3) <= 7u ? (v26 = (__int64 *)a4) : (v26 = *(__int64 **)a4),
          (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                             v26,
                             *((_QWORD *)a4 + 2),
                             L"http://schemas.openxps.org/oxps/v1.0/discard-control",
                             52)) )
    {
      v51 = *(win_dox::xps_consumption::ConsumptionState **)(a1 + 8);
      if ( *((_DWORD *)v51 + 94) == 255 )
      {
        if ( *((_QWORD *)a4 + 3) <= 7u )
          v55 = (__int64 *)a4;
        else
          v55 = *(__int64 **)a4;
        v56 = (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                                 v55,
                                 *((_QWORD *)a4 + 2),
                                 L"http://schemas.microsoft.com/xps/2005/06/discard-control",
                                 56) == 0;
        v57 = *(_QWORD *)(a1 + 8);
        if ( v56 )
        {
          v85[0] = 0;
          *(_DWORD *)(v57 + 376) = 1;
          win_dox::XpsPackageRelationshipReceiver::SetPackageType(a2, 1, v85);
          if ( !v85[0] )
          {
            win_musl::detail::ThrowBuilder<SplException::THResultException>(
              (SplException::THResultException *)pExceptionObject,
              0x175u,
              -2142109432,
              (__int64)L"XPS document type not supported");
            throw (SplException::THResultException *)pExceptionObject;
          }
        }
        else
        {
          *(_DWORD *)(v57 + 376) = 0;
          win_dox::XpsPackageRelationshipReceiver::SetPackageType(a2, 0, v85);
        }
      }
      else
      {
        v52 = win_dox::xps_consumption::ConsumptionState::GetPackageType(v51);
        if ( v52 )
        {
          if ( v52 != 1 )
          {
            win_musl::DebugLogHelper(
              "(no filename)",
              &Src,
              345,
              1024,
              -2147418113,
              L"Very Unexpected - GetPackageType must return Open or MS XPS");
            std::logic_error::logic_error((std::logic_error *)v100, "Program has entered an unexpected state");
            throw (std::logic_error *)v100;
          }
          if ( *((_QWORD *)a4 + 3) <= 7u )
            v53 = (__int64 *)a4;
          else
            v53 = *(__int64 **)a4;
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                                  v53,
                                  *((_QWORD *)a4 + 2),
                                  L"http://schemas.microsoft.com/xps/2005/06/discard-control",
                                  56) )
          {
            win_musl::detail::ThrowBuilder<SplException::THResultException>(
              (SplException::THResultException *)pExceptionObject,
              0x155u,
              -2142109680,
              (__int64)L"Unexpected relationship type");
            throw (SplException::THResultException *)pExceptionObject;
          }
        }
        else
        {
          if ( *((_QWORD *)a4 + 3) <= 7u )
            v54 = (__int64 *)a4;
          else
            v54 = *(__int64 **)a4;
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                                  v54,
                                  *((_QWORD *)a4 + 2),
                                  L"http://schemas.openxps.org/oxps/v1.0/discard-control",
                                  52) )
          {
            win_musl::detail::ThrowBuilder<SplException::THResultException>(
              (SplException::THResultException *)pExceptionObject,
              0x14Cu,
              -2142109680,
              (__int64)L"Unexpected relationship type");
            throw (SplException::THResultException *)pExceptionObject;
          }
        }
      }
      v58 = win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Get__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer_();
      if ( !(unsigned __int8)operator==(v102, v58 + 600) )
      {
        std::wstring::wstring(v100, L"Relationship target does not have expected content type");
        v68 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v103, v100);
        v69 = win_musl::Formatter::c_str(v68);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::THResultException *)pExceptionObject,
          0x1AAu,
          -2142109688,
          (__int64)v69);
        throw (SplException::THResultException *)pExceptionObject;
      }
      v59 = win_dox::xps_consumption::ConsumptionState::GetPackageType(*(win_dox::xps_consumption::ConsumptionState **)(a1 + 8));
      v61 = (int *)qword_1802297D0;
      if ( v59 )
        v61 = &dword_1802297E0;
      v62 = &qword_1802297C0;
      if ( v59 )
        v62 = (__int64 *)qword_1802297D0;
      *(_QWORD *)&v92 = v62;
      v63 = (void **)operator new(0x48u, qword_1802297D0, v60);
      v87 = v63;
      if ( v63 )
      {
        v64 = (const struct win_dox::ByteCollection *)win_dox::OpcPartContent::GetBytes(v93, &v90);
        LODWORD(v89) = 3;
        v96 = 3;
        v65 = (_QWORD *)win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(
                          v100,
                          a1);
        *(_QWORD *)&v93 = v65;
        win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v63, v86);
        win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(
          v63 + 3,
          v65);
        win_dox::ByteCollection::ByteCollection((win_dox::ByteCollection *)(v63 + 5), v64);
        v63[7] = (void *)v92;
        v63[8] = v61;
        if ( *v65 && v65[1] )
        {
          ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(v65);
          *v65 = 0;
          v65[1] = 0;
        }
      }
      else
      {
        v63 = 0;
      }
      *(_QWORD *)&v92 = v63;
      v93 = 0;
      win_scope::detail::scope_helper<win_dox::xps_consumption::XpsPartReferenceCollection<IXpsDiscardCollection,win_musl::Model::Discard> *,win_scope::const_policies<win_scope::shared_policies>>::construct_acquire<win_dox::xps_consumption::XpsPartReferenceCollection<IXpsDiscardCollection,win_musl::Model::Discard> *,win_scope::const_policies<win_scope::shared_policies>,win_dox::xps_consumption::XpsPartReferenceCollection<IXpsDiscardCollection,win_musl::Model::Discard> *>(
        &v93,
        &v92);
      if ( (v89 & 1) != 0 )
      {
        v90 = &win_dox::OpcRelationshipCollection::`vftable';
        if ( v91 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
          v91 = 0;
        }
      }
      v66 = win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(
              &v87,
              &v93);
      win_dox::CreateInstanceFromInner<IXpsDiscardCollection,win_scope::scope<win_dox::xps_consumption::XpsPartReferenceCollection<IXpsDiscardCollection,win_musl::Model::Discard> *,win_scope::const_policies<win_scope::shared_policies>>>(
        &v89,
        v66);
      v67 = (const struct win_dox::Uri *)win_dox::xps_consumption::MakePartReference(&v92, a1, a4 + 16, v86);
      win_dox::XpsPackageRelationshipReceiver::SetDiscardControl(
        v94,
        v67,
        a6,
        (const struct win_dox::XpsDiscardCollection *)&v89);
      if ( (_QWORD)v92 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v92 + 16LL))(v92);
      if ( v89 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      if ( (_QWORD)v93 && *((_QWORD *)&v93 + 1) )
        ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(&v93);
      win_musl::ContentType::~ContentType((win_musl::ContentType *)v102);
      goto LABEL_132;
    }
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v27 = (__int64 *)a4;
    else
      v27 = *(__int64 **)a4;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                            v27,
                            *((_QWORD *)a4 + 2),
                            L"http://schemas.openxmlformats.org/package/2006/relationships/metadata/core-properties",
                            85) )
    {
      v28 = win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Get__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer_();
      if ( !(unsigned __int8)operator==(v102, v28 + 120) )
      {
        std::wstring::wstring(v100, L"Relationship target does not have expected content type for CoreProperties");
        v32 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v103, v100);
        v33 = win_musl::Formatter::c_str(v32);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::THResultException *)pExceptionObject,
          0x1BEu,
          -2142109688,
          (__int64)v33);
        throw (SplException::THResultException *)pExceptionObject;
      }
      v29 = win_dox::OpcPartContent::GetBytes(a7, &v90);
      v30 = (const struct win_dox::ByteCollection *)win_dox::xps_consumption::MakeXpsByteCollection(&v87, a1, v29);
      v31 = (const struct win_dox::Uri *)win_dox::xps_consumption::MakePartReference(&v86, a1, a4 + 16, v8);
      win_dox::XpsPackageRelationshipReceiver::SetCoreProperties(a2, v31, a6, v30);
      if ( v86 )
      {
        (*(void (__fastcall **)(struct win_dox::OpcPartUri *))(*(_QWORD *)v86 + 16LL))(v86);
        v86 = 0;
      }
      v87 = &win_dox::OpcRelationshipCollection::`vftable';
      if ( v88 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
        v88 = 0;
      }
      v90 = &win_dox::OpcRelationshipCollection::`vftable';
      if ( v91 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      goto LABEL_49;
    }
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v34 = (__int64 *)a4;
    else
      v34 = *(__int64 **)a4;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                            v34,
                            *((_QWORD *)a4 + 2),
                            L"http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/origin",
                            85) )
    {
      v35 = win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Get__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer_();
      if ( !(unsigned __int8)operator==(v102, v35 + 360) )
      {
        std::wstring::wstring(v100, L"Relationship target does not have expected content type");
        v36 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v103, v100);
        v37 = win_musl::Formatter::c_str(v36);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::THResultException *)pExceptionObject,
          0x1CDu,
          -2142109688,
          (__int64)v37);
        throw (SplException::THResultException *)pExceptionObject;
      }
LABEL_58:
      win_musl::ContentType::~ContentType((win_musl::ContentType *)v102);
LABEL_132:
      if ( *(_QWORD *)a1 && *(_QWORD *)(a1 + 8) )
      {
        ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(a1);
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 8) = 0;
      }
      return;
    }
    if ( !win_dox::XpsPackageRelationshipReceiver::SupportsCustomPayload(a2) )
    {
      std::wstring::wstring(v100, L"Unexpected relationship type");
      v39 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v103, v100);
      v40 = win_musl::Formatter::c_str(v39);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1D6u,
        -2142109680,
        (__int64)v40);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( win_dox::xps_consumption::IsStrictlyXpsContentType((win_dox::xps_consumption *)v102, v38) )
      goto LABEL_58;
    Relationships = win_dox::OpcPartContent::GetRelationships(a7, &v93);
    win_dox::CreateSenderBase<IOpcRelationshipCollection>::CreateSender(Relationships, &v97);
    *(_QWORD *)&v93 = &win_dox::OpcRelationshipCollection::`vftable';
    if ( *((_QWORD *)&v93 + 1) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v93 + 1) + 16LL))(*((_QWORD *)&v93 + 1));
      *((_QWORD *)&v93 + 1) = 0;
    }
    v94 = (win_dox::XpsPackageRelationshipReceiver *)operator new(0x38u, v42, v43);
    if ( v94 )
    {
      v44 = win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(
              &v90,
              a1);
      v46 = win_dox::xps_consumption::XpsRelationshipSender<win_dox::XpsCustomPartRelationshipReceiver>::XpsRelationshipSender<win_dox::XpsCustomPartRelationshipReceiver>(
              v45,
              v8,
              v44,
              &v97);
    }
    else
    {
      v46 = 0;
    }
    win_scope::scope<win_dox::xps_consumption::XpsRelationshipSender<win_dox::XpsCustomPartRelationshipReceiver> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::xps_consumption::XpsRelationshipSender<win_dox::XpsCustomPartRelationshipReceiver> *,win_scope::const_policies<win_scope::shared_policies>>(
      &v87,
      v46);
    v47 = win_scope::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::production_helper::ReceiverStore<win_dox::XpsPageReceiver,1> *,win_scope::const_policies<win_scope::shared_policies>>(
            &v92,
            &v87);
    win_dox::CreateInstanceFromInner<IXpsCustomPartRelationshipSender,win_scope::scope<win_dox::xps_consumption::XpsRelationshipSender<win_dox::XpsCustomPartRelationshipReceiver> *,win_scope::const_policies<win_scope::shared_policies>>>(
      &v89,
      v47);
    v48 = win_dox::OpcPartContent::GetBytes(a7, &v90);
    v49 = (const struct win_dox::ByteCollection *)win_dox::xps_consumption::MakeXpsByteCollection(&v94, a1, v48);
    if ( *((_QWORD *)a5 + 3) > 7u )
      v11 = *(const wchar_t **)a5;
    v50 = (const struct win_dox::Uri *)win_dox::xps_consumption::MakePartReference(&v86, a1, a4 + 16, v8);
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const wchar_t **)a4;
    win_dox::XpsPackageRelationshipReceiver::AddCustomRelationship(
      a2,
      a4,
      v50,
      a6,
      v11,
      v49,
      (const struct win_dox::XpsCustomPartRelationshipSender *)&v89,
      v85);
    if ( v86 )
    {
      (*(void (__fastcall **)(struct win_dox::OpcPartUri *))(*(_QWORD *)v86 + 16LL))(v86);
      v86 = 0;
    }
    v94 = (win_dox::XpsPackageRelationshipReceiver *)&win_dox::OpcRelationshipCollection::`vftable';
    if ( v95 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      v95 = 0;
    }
    v90 = &win_dox::OpcRelationshipCollection::`vftable';
    if ( v91 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    if ( v89 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
    if ( v87 && v88 )
      ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(&v87);
    v97 = &win_dox::OpcRelationshipCollection::`vftable';
    if ( v98 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
      v98 = 0;
    }
    win_musl::ContentType::~ContentType((win_musl::ContentType *)v102);
    if ( *(_QWORD *)a1 && *(_QWORD *)(a1 + 8) )
    {
      ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(a1);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
}

```

## disassembly

```asm
0x1800c6b80  push    rbp
0x1800c6b82  push    rbx
0x1800c6b83  push    rsi
0x1800c6b84  push    rdi
0x1800c6b85  push    r12
0x1800c6b87  push    r13
0x1800c6b89  push    r14
0x1800c6b8b  push    r15
0x1800c6b8d  lea     rbp, [rsp-178h]
0x1800c6b95  sub     rsp, 278h
0x1800c6b9c  mov     rax, cs:__security_cookie
0x1800c6ba3  xor     rax, rsp
0x1800c6ba6  mov     [rbp+1B0h+var_50], rax
0x1800c6bad  mov     rsi, r9
0x1800c6bb0  mov     r12, r8
0x1800c6bb3  mov     [rsp+2B0h+var_268], r8
0x1800c6bb8  mov     r15, rdx
0x1800c6bbb  mov     [rbp+1B0h+var_218], rdx
0x1800c6bbf  mov     rdi, rcx
0x1800c6bc2  mov     r14, [rbp+1B0h+arg_20]
0x1800c6bc9  mov     [rbp+1B0h+var_1F0], rcx
0x1800c6bcd  mov     r13, [rbp+1B0h+arg_30]
0x1800c6bd4  mov     qword ptr [rbp+1B0h+var_228], r13
0x1800c6bd8  xor     ebx, ebx
0x1800c6bda  mov     [rbp+1B0h+var_208], ebx
0x1800c6bdd  mov     rdx, r14
0x1800c6be0  lea     rcx, [rbp+1B0h+var_120]
0x1800c6be7  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c6bec  lea     eax, [rbx+2]
0x1800c6bef  mov     dword ptr [rsp+2B0h+var_250], eax
0x1800c6bf3  mov     [rbp+1B0h+var_208], eax
0x1800c6bf6  cmp     qword ptr [rsi+18h], 7
0x1800c6bfb  jbe     short loc_1800C6C02
0x1800c6bfd  mov     rcx, [rsi]
0x1800c6c00  jmp     short loc_1800C6C05
0x1800c6c02  mov     rcx, rsi
0x1800c6c05  mov     r9d, 3Ch ; '<'
0x1800c6c0b  lea     r8, ?gc_ReachPackageStartPart@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800c6c12  mov     rdx, [rsi+10h]
0x1800c6c16  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800c6c1b  test    al, al
0x1800c6c1d  jnz     loc_1800C787A
0x1800c6c23  cmp     qword ptr [rsi+18h], 7
0x1800c6c28  jbe     short loc_1800C6C2F
0x1800c6c2a  mov     rcx, [rsi]
0x1800c6c2d  jmp     short loc_1800C6C32
0x1800c6c2f  mov     rcx, rsi
0x1800c6c32  mov     r9d, 38h ; '8'
0x1800c6c38  lea     r8, ?gc_ReachPackageStartPart@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/fi"...
0x1800c6c3f  mov     rdx, [rsi+10h]
0x1800c6c43  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800c6c48  test    al, al
0x1800c6c4a  jnz     loc_1800C787A
0x1800c6c50  cmp     qword ptr [rsi+18h], 7
0x1800c6c55  jbe     short loc_1800C6C5C
0x1800c6c57  mov     rcx, [rsi]
0x1800c6c5a  jmp     short loc_1800C6C5F
0x1800c6c5c  mov     rcx, rsi
0x1800c6c5f  mov     r9d, 4Fh ; 'O'
0x1800c6c65  lea     r8, ?gc_Thumbnail@PackageWide@RelationshipTypes@win_musl@@3QB_WB; "http://schemas.openxmlformats.org/packa"...
0x1800c6c6c  mov     rdx, [rsi+10h]
0x1800c6c70  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800c6c75  test    al, al
0x1800c6c77  jz      loc_1800C6EA2
0x1800c6c7d  call    win_musl__InitOnceSingleton_win_dox__xps_consumption__ContentTypes__Store__win_dox__xps_consumption__ContentTypes__InitOnce____2___UniqueIdentifier___Get__win_dox__xps_consumption__ContentTypes__InitOnce____2___Initializer_
0x1800c6c82  lea     rdx, [rax+2D0h]
0x1800c6c89  lea     rcx, [rbp+1B0h+var_120]
0x1800c6c90  call    ??8@YA_NAEBUContentType@win_musl@@0@Z; operator==(win_musl::ContentType const &,win_musl::ContentType const &)
0x1800c6c95  test    al, al
0x1800c6c97  jz      loc_1800C6D5C
0x1800c6c9d  lea     rdx, [rsp+2B0h+var_248]
0x1800c6ca2  mov     rcx, r13
0x1800c6ca5  call    ?GetBytes@OpcPartContent@win_dox@@QEBA?AVByteCollection@2@XZ; win_dox::OpcPartContent::GetBytes(void)
0x1800c6caa  nop
0x1800c6cab  mov     r8, rax
0x1800c6cae  mov     rdx, rdi
0x1800c6cb1  lea     rcx, [rsp+2B0h+var_260]
0x1800c6cb6  call    ?MakeXpsByteCollection@xps_consumption@win_dox@@YA?AVByteCollection@2@AEBV?$scope@PEAVConsumptionState@xps_consumption@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@AEBV32@@Z; win_dox::xps_consumption::MakeXpsByteCollection(win_scope::scope<win_dox::xps_consumption::ConsumptionState *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>> const &,win_dox::ByteCollection const &)
0x1800c6cbb  mov     rbx, rax
0x1800c6cbe  lea     r8, [rsi+20h]
0x1800c6cc2  mov     r9, r12
0x1800c6cc5  mov     rdx, rdi
0x1800c6cc8  lea     rcx, [rsp+2B0h+var_268]
0x1800c6ccd  call    ?MakePartReference@xps_consumption@win_dox@@YA?AVUri@2@AEBV?$scope@PEAVConsumptionState@xps_consumption@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@AEBV32@AEBVOpcPartUri@2@@Z; win_dox::xps_consumption::MakePartReference(win_scope::scope<win_dox::xps_consumption::ConsumptionState *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>> const &,win_dox::Uri const &,win_dox::OpcPartUri const &)
0x1800c6cd2  nop
0x1800c6cd3  mov     r9, rbx; struct win_dox::ByteCollection *
0x1800c6cd6  mov     r8d, [rbp+1B0h+arg_28]; enum __MIDL___MIDL_itf_msopc_0000_0002_0002
0x1800c6cdd  mov     rdx, rax; struct win_dox::Uri *
0x1800c6ce0  mov     rcx, r15; this
0x1800c6ce3  call    ?SetJpegThumbnail@XpsPackageRelationshipReceiver@win_dox@@QEAAXAEBVUri@2@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@AEBVByteCollection@2@@Z; win_dox::XpsPackageRelationshipReceiver::SetJpegThumbnail(win_dox::Uri const &,__MIDL___MIDL_itf_msopc_0000_0002_0002,win_dox::ByteCollection const &)
0x1800c6ce8  nop
0x1800c6ce9  mov     rcx, [rsp+2B0h+var_268]
0x1800c6cee  xor     r14d, r14d
0x1800c6cf1  test    rcx, rcx
0x1800c6cf4  jz      short loc_1800C6D07
0x1800c6cf6  mov     rax, [rcx]
0x1800c6cf9  mov     rax, [rax+10h]
0x1800c6cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6d02  mov     [rsp+2B0h+var_268], r14
0x1800c6d07  lea     rbx, ??_7OpcRelationshipCollection@win_dox@@6B@; const win_dox::OpcRelationshipCollection::`vftable'
0x1800c6d0e  mov     [rsp+2B0h+var_260], rbx
0x1800c6d13  mov     rcx, [rsp+2B0h+var_258]
0x1800c6d18  test    rcx, rcx
0x1800c6d1b  jz      short loc_1800C6D2E
0x1800c6d1d  mov     rax, [rcx]
0x1800c6d20  mov     rax, [rax+10h]
0x1800c6d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6d29  mov     [rsp+2B0h+var_258], r14
0x1800c6d2e  mov     [rsp+2B0h+var_248], rbx
0x1800c6d33  mov     rcx, [rsp+2B0h+var_240]
0x1800c6d38  test    rcx, rcx
0x1800c6d3b  jz      short loc_1800C6D4A
0x1800c6d3d  mov     rax, [rcx]
0x1800c6d40  mov     rax, [rax+10h]
0x1800c6d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6d49  nop
0x1800c6d4a  lea     rcx, [rbp+1B0h+var_120]; this
0x1800c6d51  call    ??1ContentType@win_musl@@QEAA@XZ; win_musl::ContentType::~ContentType(void)
0x1800c6d56  nop
0x1800c6d57  jmp     loc_1800C7000
0x1800c6d5c  call    win_musl__InitOnceSingleton_win_dox__xps_consumption__ContentTypes__Store__win_dox__xps_consumption__ContentTypes__InitOnce____2___UniqueIdentifier___Get__win_dox__xps_consumption__ContentTypes__InitOnce____2___Initializer_
0x1800c6d61  lea     rdx, [rax+348h]
0x1800c6d68  lea     rcx, [rbp+1B0h+var_120]
0x1800c6d6f  call    ??8@YA_NAEBUContentType@win_musl@@0@Z; operator==(win_musl::ContentType const &,win_musl::ContentType const &)
0x1800c6d74  test    al, al
0x1800c6d76  jz      loc_1800C6E3B
0x1800c6d7c  lea     rdx, [rsp+2B0h+var_248]
0x1800c6d81  mov     rcx, r13
0x1800c6d84  call    ?GetBytes@OpcPartContent@win_dox@@QEBA?AVByteCollection@2@XZ; win_dox::OpcPartContent::GetBytes(void)
0x1800c6d89  nop
0x1800c6d8a  mov     r8, rax
0x1800c6d8d  mov     rdx, rdi
0x1800c6d90  lea     rcx, [rsp+2B0h+var_260]
0x1800c6d95  call    ?MakeXpsByteCollection@xps_consumption@win_dox@@YA?AVByteCollection@2@AEBV?$scope@PEAVConsumptionState@xps_consumption@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@AEBV32@@Z; win_dox::xps_consumption::MakeXpsByteCollection(win_scope::scope<win_dox::xps_consumption::ConsumptionState *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>> const &,win_dox::ByteCollection const &)
0x1800c6d9a  mov     rbx, rax
0x1800c6d9d  lea     r8, [rsi+20h]
0x1800c6da1  mov     r9, r12
0x1800c6da4  mov     rdx, rdi
0x1800c6da7  lea     rcx, [rsp+2B0h+var_268]
0x1800c6dac  call    ?MakePartReference@xps_consumption@win_dox@@YA?AVUri@2@AEBV?$scope@PEAVConsumptionState@xps_consumption@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@AEBV32@AEBVOpcPartUri@2@@Z; win_dox::xps_consumption::MakePartReference(win_scope::scope<win_dox::xps_consumption::ConsumptionState *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>> const &,win_dox::Uri const &,win_dox::OpcPartUri const &)
0x1800c6db1  nop
0x1800c6db2  mov     r9, rbx; struct win_dox::ByteCollection *
0x1800c6db5  mov     r8d, [rbp+1B0h+arg_28]; enum __MIDL___MIDL_itf_msopc_0000_0002_0002
0x1800c6dbc  mov     rdx, rax; struct win_dox::Uri *
0x1800c6dbf  mov     rcx, r15; this
0x1800c6dc2  call    ?SetPngThumbnail@XpsPackageRelationshipReceiver@win_dox@@QEAAXAEBVUri@2@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@AEBVByteCollection@2@@Z; win_dox::XpsPackageRelationshipReceiver::SetPngThumbnail(win_dox::Uri const &,__MIDL___MIDL_itf_msopc_0000_0002_0002,win_dox::ByteCollection const &)
0x1800c6dc7  nop
0x1800c6dc8  mov     rcx, [rsp+2B0h+var_268]
0x1800c6dcd  xor     r14d, r14d
0x1800c6dd0  test    rcx, rcx
0x1800c6dd3  jz      short loc_1800C6DE6
0x1800c6dd5  mov     rax, [rcx]
0x1800c6dd8  mov     rax, [rax+10h]
0x1800c6ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6de1  mov     [rsp+2B0h+var_268], r14
0x1800c6de6  lea     rbx, ??_7OpcRelationshipCollection@win_dox@@6B@; const win_dox::OpcRelationshipCollection::`vftable'
0x1800c6ded  mov     [rsp+2B0h+var_260], rbx
0x1800c6df2  mov     rcx, [rsp+2B0h+var_258]
0x1800c6df7  test    rcx, rcx
0x1800c6dfa  jz      short loc_1800C6E0D
0x1800c6dfc  mov     rax, [rcx]
0x1800c6dff  mov     rax, [rax+10h]
0x1800c6e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e08  mov     [rsp+2B0h+var_258], r14
0x1800c6e0d  mov     [rsp+2B0h+var_248], rbx
0x1800c6e12  mov     rcx, [rsp+2B0h+var_240]
0x1800c6e17  test    rcx, rcx
0x1800c6e1a  jz      short loc_1800C6E29
0x1800c6e1c  mov     rax, [rcx]
0x1800c6e1f  mov     rax, [rax+10h]
0x1800c6e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e28  nop
0x1800c6e29  lea     rcx, [rbp+1B0h+var_120]; this
0x1800c6e30  call    ??1ContentType@win_musl@@QEAA@XZ; win_musl::ContentType::~ContentType(void)
0x1800c6e35  nop
0x1800c6e36  jmp     loc_1800C7000
0x1800c6e3b  lea     rdx, aRelationshipTa_4; "Relationship target does not have expec"...
0x1800c6e42  lea     rcx, [rbp+1B0h+var_1E8]
0x1800c6e46  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c6e4b  nop
0x1800c6e4c  lea     rdx, [rbp+1B0h+var_1E8]
0x1800c6e50  lea     rcx, [rbp+1B0h+var_A0]
0x1800c6e57  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800c6e5c  nop
0x1800c6e5d  mov     rcx, rax; this
0x1800c6e60  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800c6e65  mov     [rsp+2B0h+var_280], rax; __int64
0x1800c6e6a  mov     dword ptr [rsp+2B0h+var_288], 80520008h; int
0x1800c6e72  mov     dword ptr [rsp+2B0h+var_290], 13Ah; unsigned int
0x1800c6e7a  lea     r9, Src
0x1800c6e81  lea     r8, aNoFilename; "(no filename)"
0x1800c6e88  lea     rcx, [rbp+1B0h+pExceptionObject]; this
0x1800c6e8c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c6e91  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c6e98  lea     rcx, [rbp+1B0h+pExceptionObject]; pExceptionObject
0x1800c6e9c  call    _CxxThrowException_0
0x1800c6ea2  cmp     qword ptr [rsi+18h], 7
0x1800c6ea7  jbe     short loc_1800C6EAE
0x1800c6ea9  mov     rcx, [rsi]
0x1800c6eac  jmp     short loc_1800C6EB1
0x1800c6eae  mov     rcx, rsi
0x1800c6eb1  mov     r9d, 38h ; '8'
0x1800c6eb7  lea     r8, ?gc_DiscardControl@MsXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x1800c6ebe  mov     rdx, [rsi+10h]
0x1800c6ec2  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800c6ec7  test    al, al
0x1800c6ec9  jnz     loc_1800C7401
0x1800c6ecf  cmp     qword ptr [rsi+18h], 7
0x1800c6ed4  jbe     short loc_1800C6EDB
0x1800c6ed6  mov     rcx, [rsi]
0x1800c6ed9  jmp     short loc_1800C6EDE
0x1800c6edb  mov     rcx, rsi
0x1800c6ede  mov     r9d, 34h ; '4'
0x1800c6ee4  lea     r8, ?gc_DiscardControl@OpenXps@XpsDocument@RelationshipTypes@win_musl@@2QB_WB; "http://schemas.openxps.org/oxps/v1.0/di"...
0x1800c6eeb  mov     rdx, [rsi+10h]
0x1800c6eef  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800c6ef4  test    al, al
0x1800c6ef6  jnz     loc_1800C7401
0x1800c6efc  cmp     qword ptr [rsi+18h], 7
0x1800c6f01  jbe     short loc_1800C6F08
0x1800c6f03  mov     rcx, [rsi]
0x1800c6f06  jmp     short loc_1800C6F0B
0x1800c6f08  mov     rcx, rsi
0x1800c6f0b  mov     r9d, 55h ; 'U'
0x1800c6f11  lea     r8, ?gc_CoreProperties@PackageWide@RelationshipTypes@win_musl@@3QB_WB; "http://schemas.openxmlformats.org/packa"...
0x1800c6f18  mov     rdx, [rsi+10h]
0x1800c6f1c  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800c6f21  test    al, al
0x1800c6f23  jz      loc_1800C708E
0x1800c6f29  call    win_musl__InitOnceSingleton_win_dox__xps_consumption__ContentTypes__Store__win_dox__xps_consumption__ContentTypes__InitOnce____2___UniqueIdentifier___Get__win_dox__xps_consumption__ContentTypes__InitOnce____2___Initializer_
0x1800c6f2e  lea     rdx, [rax+78h]
0x1800c6f32  lea     rcx, [rbp+1B0h+var_120]
0x1800c6f39  call    ??8@YA_NAEBUContentType@win_musl@@0@Z; operator==(win_musl::ContentType const &,win_musl::ContentType const &)
0x1800c6f3e  test    al, al
0x1800c6f40  jz      loc_1800C7027
0x1800c6f46  lea     rdx, [rsp+2B0h+var_248]
0x1800c6f4b  mov     rcx, r13
0x1800c6f4e  call    ?GetBytes@OpcPartContent@win_dox@@QEBA?AVByteCollection@2@XZ; win_dox::OpcPartContent::GetBytes(void)
0x1800c6f53  nop
0x1800c6f54  mov     r8, rax
0x1800c6f57  mov     rdx, rdi
0x1800c6f5a  lea     rcx, [rsp+2B0h+var_260]
0x1800c6f5f  call    ?MakeXpsByteCollection@xps_consumption@win_dox@@YA?AVByteCollection@2@AEBV?$scope@PEAVConsumptionState@xps_consumption@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@AEBV32@@Z; win_dox::xps_consumption::MakeXpsByteCollection(win_scope::scope<win_dox::xps_consumption::ConsumptionState *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>> const &,win_dox::ByteCollection const &)
0x1800c6f64  mov     rbx, rax
0x1800c6f67  lea     r8, [rsi+20h]
0x1800c6f6b  mov     r9, r12
0x1800c6f6e  mov     rdx, rdi
0x1800c6f71  lea     rcx, [rsp+2B0h+var_268]
0x1800c6f76  call    ?MakePartReference@xps_consumption@win_dox@@YA?AVUri@2@AEBV?$scope@PEAVConsumptionState@xps_consumption@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@AEBV32@AEBVOpcPartUri@2@@Z; win_dox::xps_consumption::MakePartReference(win_scope::scope<win_dox::xps_consumption::ConsumptionState *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>> const &,win_dox::Uri const &,win_dox::OpcPartUri const &)
0x1800c6f7b  nop
0x1800c6f7c  mov     r9, rbx; struct win_dox::ByteCollection *
0x1800c6f7f  mov     r8d, [rbp+1B0h+arg_28]; enum __MIDL___MIDL_itf_msopc_0000_0002_0002
0x1800c6f86  mov     rdx, rax; struct win_dox::Uri *
0x1800c6f89  mov     rcx, r15; this
0x1800c6f8c  call    ?SetCoreProperties@XpsPackageRelationshipReceiver@win_dox@@QEAAXAEBVUri@2@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@AEBVByteCollection@2@@Z; win_dox::XpsPackageRelationshipReceiver::SetCoreProperties(win_dox::Uri const &,__MIDL___MIDL_itf_msopc_0000_0002_0002,win_dox::ByteCollection const &)
0x1800c6f91  nop
0x1800c6f92  mov     rcx, [rsp+2B0h+var_268]
0x1800c6f97  xor     r14d, r14d
0x1800c6f9a  test    rcx, rcx
0x1800c6f9d  jz      short loc_1800C6FB0
0x1800c6f9f  mov     rax, [rcx]
0x1800c6fa2  mov     rax, [rax+10h]
0x1800c6fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6fab  mov     [rsp+2B0h+var_268], r14
0x1800c6fb0  lea     rbx, ??_7OpcRelationshipCollection@win_dox@@6B@; const win_dox::OpcRelationshipCollection::`vftable'
0x1800c6fb7  mov     [rsp+2B0h+var_260], rbx
0x1800c6fbc  mov     rcx, [rsp+2B0h+var_258]
0x1800c6fc1  test    rcx, rcx
0x1800c6fc4  jz      short loc_1800C6FD7
0x1800c6fc6  mov     rax, [rcx]
0x1800c6fc9  mov     rax, [rax+10h]
0x1800c6fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6fd2  mov     [rsp+2B0h+var_258], r14
0x1800c6fd7  mov     [rsp+2B0h+var_248], rbx
0x1800c6fdc  mov     rcx, [rsp+2B0h+var_240]
0x1800c6fe1  test    rcx, rcx
0x1800c6fe4  jz      short loc_1800C6FF3
0x1800c6fe6  mov     rax, [rcx]
0x1800c6fe9  mov     rax, [rax+10h]
0x1800c6fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6ff2  nop
0x1800c6ff3  lea     rcx, [rbp+1B0h+var_120]; this
0x1800c6ffa  call    ??1ContentType@win_musl@@QEAA@XZ; win_musl::ContentType::~ContentType(void)
0x1800c6fff  nop
0x1800c7000  cmp     [rdi], r14
0x1800c7003  jz      loc_1800C7C31
0x1800c7009  cmp     [rdi+8], r14
0x1800c700d  jz      loc_1800C7C31
0x1800c7013  mov     rcx, rdi
0x1800c7016  call    ??$close@PEAV?$DefaultContentHandler@V?$XmlParser@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@consumption@win_musl@@@consumption@win_musl@@@?$counted_strong@U?$const_policies@U?$types_6@Uclose_delete@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAV?$DefaultContentHandler@V?$XmlParser@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@consumption@win_musl@@@consumption@win_musl@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_delete,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::close<win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>>> *>(win_scope::counted_store<win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>>> *> *)
0x1800c701b  mov     [rdi], r14
0x1800c701e  mov     [rdi+8], r14
0x1800c7022  jmp     loc_1800C7C31
0x1800c7027  lea     rdx, aRelationshipTa_3; "Relationship target does not have expec"...
0x1800c702e  lea     rcx, [rbp+1B0h+var_1E8]
0x1800c7032  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c7037  nop
0x1800c7038  lea     rdx, [rbp+1B0h+var_1E8]
0x1800c703c  lea     rcx, [rbp+1B0h+var_A0]
0x1800c7043  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
  ... truncated ...
```
