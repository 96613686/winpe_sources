# win_musl::BindReceiverMembers<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList>(win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> *,xpsom::PathBuilder const &)

- ea: `0x18008d228`
- end: `0x18008dd8e`
- name: `??$BindReceiverMembers@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@@win_musl@@YAXPEAU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@0@AEBVPathBuilder@xpsom@@@Z`
- size: `2918`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180164340`

## callees

- `0x18008d228`
- `0x18008dea0`
- `0x18008dfa4`
- `0x18008e2c8`
- `0x18008e3cc`
- `0x18008e4d8`
- `0x18008e5e4`
- `0x18008e6f0`
- `0x18008e904`
- `0x18008eb14`
- `0x18008ec20`
- `0x1800901b0`
- `0x180090740`
- `0x18009084c`
- `0x180090a64`
- `0x180090c7c`
- `0x180090d88`
- `0x180090e94`
- `0x1800e5e20`
- `0x1800e5f28`
- `0x1800e6034`
- `0x18010672c`
- `0x18010bc48`
- `0x18010bca0`

## string_xrefs

- `0x18008dd09`: `http://www.w3.org/XML/1998/namespace`
- `0x18008d490`: `Path.Stroke`
- `0x18008d241`: `Path.RenderTransform`
- `0x18008d489`: `Path.RenderTransform`
- `0x18008d384`: `Path.OpacityMask`
- `0x18008d2fe`: `Path.Clip`
- `0x18008d516`: `Path.Data`
- `0x18008d40a`: `Path.Fill`
- `0x18008d293`: `http://schemas.microsoft.com/xps/2005/06`

## pseudocode

```c
__int64 __fastcall ___BindReceiverMembers_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z__win_musl__YAXPEAU__MemberBindings_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___0_AEBVPathBuilder_xpsom___Z(
        _QWORD *a1)
{
  unsigned __int64 v2; // rax
  const wchar_t *v3; // rax
  const wchar_t *v4; // rcx
  bool v5; // zf
  const wchar_t *v6; // rdi
  const wchar_t *v7; // rcx
  const wchar_t *v8; // rdx
  const wchar_t *v9; // rax
  const wchar_t *v10; // rcx
  bool v11; // zf
  const wchar_t *v12; // rcx
  const wchar_t *v13; // rdx
  const wchar_t *v14; // rax
  const wchar_t *v15; // rcx
  bool v16; // zf
  const wchar_t *v17; // rcx
  const wchar_t *v18; // rdx
  const wchar_t *v19; // rax
  const wchar_t *v20; // rcx
  bool v21; // zf
  const wchar_t *v22; // rcx
  const wchar_t *v23; // rdx
  const wchar_t *v24; // rax
  const wchar_t *v25; // rcx
  bool v26; // zf
  const wchar_t *v27; // rcx
  const wchar_t *v28; // rdx
  const wchar_t *v29; // rax
  const wchar_t *v30; // rcx
  bool v31; // zf
  const wchar_t *v32; // rcx
  __int128 *v33; // rax
  __int128 v34; // xmm0
  __int128 *v35; // rax
  __int128 v36; // xmm0
  const wchar_t *v37; // rax
  const wchar_t *v38; // rcx
  __int128 *v39; // rax
  __int128 v40; // xmm0
  const wchar_t *v41; // rax
  const wchar_t *v42; // rcx
  const wchar_t *v43; // rax
  const wchar_t *v44; // rcx
  __int128 v45; // xmm0
  const wchar_t *v46; // rax
  const wchar_t *v47; // rcx
  __int128 v48; // xmm0
  const wchar_t *v49; // rax
  const wchar_t *v50; // rcx
  __int128 v51; // xmm0
  const wchar_t *v52; // rax
  const wchar_t *v53; // rcx
  __int128 v54; // xmm0
  __int128 *v55; // rax
  __int128 v56; // xmm0
  const wchar_t *v57; // rax
  const wchar_t *v58; // rcx
  __int128 v59; // xmm0
  const wchar_t *v60; // rax
  const wchar_t *v61; // rcx
  __int128 v62; // xmm0
  const wchar_t *v63; // rax
  const wchar_t *v64; // rcx
  __int128 v65; // xmm0
  const wchar_t *v66; // rax
  const wchar_t *v67; // rcx
  __int128 v68; // xmm0
  const wchar_t *v69; // rax
  const wchar_t *v70; // rcx
  __int128 v71; // xmm0
  const wchar_t *v72; // rax
  const wchar_t *v73; // rcx
  __int128 v74; // xmm0
  const wchar_t *v75; // rax
  const wchar_t *v76; // rcx
  __int128 v77; // xmm0
  const wchar_t *v78; // rax
  const wchar_t *v79; // rcx
  const wchar_t *v80; // rax
  const wchar_t *v81; // rcx
  __int128 v82; // xmm0
  const wchar_t *v83; // rax
  const wchar_t *v84; // rcx
  const wchar_t *v85; // rax
  const wchar_t *v86; // rcx
  bool v87; // zf
  const wchar_t *v88; // rcx
  const wchar_t *v89; // rdx
  __int64 v90; // rax
  _OWORD v92[2]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v93; // [rsp+40h] [rbp-39h] BYREF
  __int128 v94; // [rsp+50h] [rbp-29h]
  __int128 v95; // [rsp+60h] [rbp-19h]
  __int128 v96; // [rsp+70h] [rbp-9h] BYREF
  __int128 v97; // [rsp+80h] [rbp+7h]
  __int128 v98; // [rsp+90h] [rbp+17h]

  v2 = 0x8E38E38E38E38E39uLL * ((__int64)(a1[1] - *a1) >> 3);
  a1[6] = v2;
  a1[5] = v2;
  v3 = (const wchar_t *)word_1801DE15A;
  while ( 1 )
  {
    v4 = v3--;
    v5 = *v3 == 0;
    if ( *v3 )
      break;
    if ( v3 == L"Path.RenderTransform" )
    {
      v5 = *v3 == 0;
      break;
    }
  }
  v6 = (const wchar_t *)word_1801DFA92;
  if ( !v5 )
    v3 = v4;
  v7 = (const wchar_t *)word_1801DFA92;
  do
    v8 = v7--;
  while ( !*v7 && v7 != L"http://schemas.microsoft.com/xps/2005/06" );
  v5 = *v7 == 0;
  *((_QWORD *)&v92[0] + 1) = v3;
  *(_QWORD *)&v92[0] = L"Path.RenderTransform";
  if ( !v5 )
    v7 = v8;
  v94 = v92[0];
  *((_QWORD *)&v93 + 1) = v7;
  *(_QWORD *)&v92[0] = &xpsom::PathBuilder::SetPathRenderTransform;
  *(_QWORD *)&v93 = L"http://schemas.microsoft.com/xps/2005/06";
  v95 = 0;
  DWORD2(v92[0]) = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParsePage_xpsom::MsXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_xpsom::TransformBuilder_(
    a1,
    &v93,
    v92);
  v9 = (const wchar_t *)&dword_1801DE19C;
  while ( 1 )
  {
    v10 = v9--;
    v11 = *v9 == 0;
    if ( *v9 )
      break;
    if ( v9 == L"Path.Clip" )
    {
      v11 = *v9 == 0;
      break;
    }
  }
  if ( !v11 )
    v9 = v10;
  v12 = (const wchar_t *)word_1801DFA92;
  do
    v13 = v12--;
  while ( !*v12 && v12 != L"http://schemas.microsoft.com/xps/2005/06" );
  v5 = *v12 == 0;
  *((_QWORD *)&v92[0] + 1) = v9;
  *(_QWORD *)&v92[0] = L"Path.Clip";
  if ( !v5 )
    v12 = v13;
  v94 = v92[0];
  *((_QWORD *)&v93 + 1) = v12;
  *(_QWORD *)&v92[0] = &xpsom::PathBuilder::SetPathClip;
  *(_QWORD *)&v93 = L"http://schemas.microsoft.com/xps/2005/06";
  v95 = 0;
  DWORD2(v92[0]) = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParsePage_xpsom::MsXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_xpsom::GeometriesBuilder_(
    a1,
    &v93,
    v92);
  v14 = (const wchar_t *)word_1801DE182;
  while ( 1 )
  {
    v15 = v14--;
    v16 = *v14 == 0;
    if ( *v14 )
      break;
    if ( v14 == L"Path.OpacityMask" )
    {
      v16 = *v14 == 0;
      break;
    }
  }
  if ( !v16 )
    v14 = v15;
  v17 = (const wchar_t *)word_1801DFA92;
  do
    v18 = v17--;
  while ( !*v17 && v17 != L"http://schemas.microsoft.com/xps/2005/06" );
  v5 = *v17 == 0;
  *((_QWORD *)&v92[0] + 1) = v14;
  *(_QWORD *)&v92[0] = L"Path.OpacityMask";
  if ( !v5 )
    v17 = v18;
  v94 = v92[0];
  *((_QWORD *)&v93 + 1) = v17;
  *(_QWORD *)&v92[0] = &xpsom::PathBuilder::SetPathOpacityMask;
  *(_QWORD *)&v93 = L"http://schemas.microsoft.com/xps/2005/06";
  v95 = 0;
  DWORD2(v92[0]) = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParsePage_xpsom::MsXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_xpsom::BrushBuilder_(
    a1,
    &v93,
    v92);
  v19 = (const wchar_t *)&dword_1801DE1CC;
  while ( 1 )
  {
    v20 = v19--;
    v21 = *v19 == 0;
    if ( *v19 )
      break;
    if ( v19 == L"Path.Fill" )
    {
      v21 = *v19 == 0;
      break;
    }
  }
  if ( !v21 )
    v19 = v20;
  v22 = (const wchar_t *)word_1801DFA92;
  do
    v23 = v22--;
  while ( !*v22 && v22 != L"http://schemas.microsoft.com/xps/2005/06" );
  v5 = *v22 == 0;
  *((_QWORD *)&v92[0] + 1) = v19;
  *(_QWORD *)&v92[0] = L"Path.Fill";
  if ( !v5 )
    v22 = v23;
  v94 = v92[0];
  *((_QWORD *)&v93 + 1) = v22;
  *(_QWORD *)&v92[0] = &xpsom::PathBuilder::SetPathFill;
  *(_QWORD *)&v93 = L"http://schemas.microsoft.com/xps/2005/06";
  v95 = 0;
  DWORD2(v92[0]) = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParsePage_xpsom::MsXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_xpsom::BrushBuilder_(
    a1,
    &v93,
    v92);
  v24 = L"Path.RenderTransform";
  while ( 1 )
  {
    v25 = v24--;
    v26 = *v24 == 0;
    if ( *v24 )
      break;
    if ( v24 == L"Path.Stroke" )
    {
      v26 = *v24 == 0;
      break;
    }
  }
  if ( !v26 )
    v24 = v25;
  v27 = (const wchar_t *)word_1801DFA92;
  do
    v28 = v27--;
  while ( !*v27 && v27 != L"http://schemas.microsoft.com/xps/2005/06" );
  v5 = *v27 == 0;
  *((_QWORD *)&v92[0] + 1) = v24;
  *(_QWORD *)&v92[0] = L"Path.Stroke";
  if ( !v5 )
    v27 = v28;
  v94 = v92[0];
  *((_QWORD *)&v93 + 1) = v27;
  *(_QWORD *)&v92[0] = &xpsom::PathBuilder::SetPathStroke;
  *(_QWORD *)&v93 = L"http://schemas.microsoft.com/xps/2005/06";
  v95 = 0;
  DWORD2(v92[0]) = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParsePage_xpsom::MsXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_xpsom::BrushBuilder_(
    a1,
    &v93,
    v92);
  v29 = (const wchar_t *)&dword_1801DE1B4;
  while ( 1 )
  {
    v30 = v29--;
    v31 = *v29 == 0;
    if ( *v29 )
      break;
    if ( v29 == L"Path.Data" )
    {
      v31 = *v29 == 0;
      break;
    }
  }
  if ( !v31 )
    v29 = v30;
  do
    v32 = v6--;
  while ( !*v6 && v6 != L"http://schemas.microsoft.com/xps/2005/06" );
  v5 = *v6 == 0;
  *((_QWORD *)&v92[0] + 1) = v29;
  *(_QWORD *)&v92[0] = L"Path.Data";
  if ( !v5 )
    v6 = v32;
  v94 = v92[0];
  *(_QWORD *)&v92[0] = &xpsom::PathBuilder::SetPathData;
  v95 = 0;
  *(_QWORD *)&v93 = L"http://schemas.microsoft.com/xps/2005/06";
  *((_QWORD *)&v93 + 1) = v6;
  DWORD2(v92[0]) = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParsePage_xpsom::MsXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_xpsom::GeometriesBuilder_(
    a1,
    &v93,
    v92);
  a1[6] = 0x8E38E38E38E38E39uLL * ((__int64)(a1[1] - *a1) >> 3);
  v33 = (__int128 *)win_musl::sax::local_name::make<wchar_t,26>(v92);
  v34 = v33[1];
  v93 = *v33;
  v95 = 0;
  v94 = v34;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::AutomationPropertiesBuilder_xpsom::TXpsOMPath__std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___(
    a1,
    &v93,
    xpsom::AutomationPropertiesBuilder<xpsom::TXpsOMPath>::SetAutomationPropertiesName);
  v35 = (__int128 *)win_musl::sax::local_name::make<wchar_t,30>(v92);
  v36 = v35[1];
  v93 = *v35;
  v95 = 0;
  v94 = v36;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::AutomationPropertiesBuilder_xpsom::TXpsOMPath__std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___(
    a1,
    &v93,
    xpsom::AutomationPropertiesBuilder<xpsom::TXpsOMPath>::SetAutomationPropertiesHelpText);
  v37 = (const wchar_t *)word_1801DDFC2;
  do
    v38 = v37--;
  while ( !*v37 && v37 != L"Name" );
  v5 = *v37 == 0;
  *(_QWORD *)&v92[0] = L"Name";
  if ( !v5 )
    v37 = v38;
  *((_QWORD *)&v92[0] + 1) = v37;
  v93 = 0;
  v94 = v92[0];
  v95 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::VisualElementBuilder_xpsom::TXpsOMPath__std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___(
    a1,
    &v93,
    xpsom::VisualElementBuilder<xpsom::TXpsOMPath>::SetName,
    xps_validation::StringValidateST_Name);
  v39 = (__int128 *)win_musl::sax::local_name::make<wchar_t,22>(v92);
  v40 = v39[1];
  v93 = *v39;
  v95 = 0;
  v94 = v40;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::VisualElementBuilder_xpsom::TXpsOMPath__std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___(
    a1,
    &v93,
    xpsom::VisualElementBuilder<xpsom::TXpsOMPath>::SetNavigateUri,
    0);
  v41 = (const wchar_t *)&GUID_95a9435e_12bb_461b_8e7f_c6adb04cd96a;
  do
    v42 = v41--;
  while ( !*v41 && v41 != L"Opacity" );
  v5 = *v41 == 0;
  *(_QWORD *)&v92[0] = L"Opacity";
  if ( !v5 )
    v41 = v42;
  *((_QWORD *)&v92[0] + 1) = v41;
  v93 = 0;
  v94 = v92[0];
  v95 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::VisualElementBuilder_xpsom::TXpsOMPath__float_(
    a1,
    &v93);
  v43 = L"{StaticResource ";
  do
    v44 = v43--;
  while ( v43 != L"OpacityMask" && !*v43 );
  v5 = *v43 == 0;
  *(_QWORD *)&v92[0] = L"OpacityMask";
  if ( !v5 )
    v43 = v44;
  *((_QWORD *)&v92[0] + 1) = v43;
  v93 = 0;
  v45 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetOpacityMask;
  HIDWORD(v92[0]) = HIDWORD(v43);
  v94 = v45;
  DWORD2(v92[0]) = 0;
  v95 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___(
    a1,
    &v93,
    v92);
  v46 = L"Data";
  do
    v47 = v46--;
  while ( v46 != L"StrokeDashArray" && !*v46 );
  v5 = *v46 == 0;
  *(_QWORD *)&v92[0] = L"StrokeDashArray";
  if ( !v5 )
    v46 = v47;
  *((_QWORD *)&v92[0] + 1) = v46;
  v93 = 0;
  v48 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetStrokeDashArray;
  HIDWORD(v92[0]) = HIDWORD(v46);
  v94 = v48;
  DWORD2(v92[0]) = 0;
  v95 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_std::vector_float_std::allocator_float____const___(
    a1,
    &v93,
    v92);
  v49 = (const wchar_t *)&dword_1801DE28C;
  do
    v50 = v49--;
  while ( !*v49 && v49 != L"StrokeDashCap" );
  v5 = *v49 == 0;
  *(_QWORD *)&v92[0] = L"StrokeDashCap";
  if ( !v5 )
    v49 = v50;
  *((_QWORD *)&v92[0] + 1) = v49;
  v93 = 0;
  v51 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetStrokeDashCap;
  HIDWORD(v92[0]) = HIDWORD(v49);
  v94 = v51;
  DWORD2(v92[0]) = 0;
  v95 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_enum___MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0006_(
    a1,
    &v93,
    v92);
  v52 = (const wchar_t *)word_1801DE302;
  do
    v53 = v52--;
  while ( !*v52 && v52 != L"StrokeDashOffset" );
  v5 = *v52 == 0;
  *(_QWORD *)&v92[0] = L"StrokeDashOffset";
  if ( !v5 )
    v52 = v53;
  *((_QWORD *)&v92[0] + 1) = v52;
  v93 = 0;
  v54 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetStrokeDashOffset;
  HIDWORD(v92[0]) = HIDWORD(v52);
  v94 = v54;
  DWORD2(v92[0]) = 0;
  v95 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_float_(
    a1,
    &v93,
    v92);
  v55 = (__int128 *)win_musl::sax::local_name::make<wchar_t,19>(&v93);
  DWORD2(v92[0]) = 0;
  v56 = v55[1];
  v96 = *v55;
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetStrokeStartLineCap;
  v98 = 0;
  v97 = v56;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_enum___MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005_(
    a1,
    &v96,
    v92);
  v57 = (const wchar_t *)word_1801DBF8A;
  do
    v58 = v57--;
  while ( !*v57 && v57 != L"StrokeEndLineCap" );
  v5 = *v57 == 0;
  *(_QWORD *)&v92[0] = L"StrokeEndLineCap";
  if ( !v5 )
    v57 = v58;
  *((_QWORD *)&v92[0] + 1) = v57;
  v96 = 0;
  v59 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetStrokeEndLineCap;
  HIDWORD(v92[0]) = HIDWORD(v57);
  v97 = v59;
  DWORD2(v92[0]) = 0;
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_enum___MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005_(
    a1,
    &v96,
    v92);
  v60 = (const wchar_t *)&word_1801DE22E;
  do
    v61 = v60--;
  while ( !*v60 && v60 != L"StrokeLineJoin" );
  v5 = *v60 == 0;
  *(_QWORD *)&v92[0] = L"StrokeLineJoin";
  if ( !v5 )
    v60 = v61;
  *((_QWORD *)&v92[0] + 1) = v60;
  v96 = 0;
  v62 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetStrokeLineJoin;
  HIDWORD(v92[0]) = HIDWORD(v60);
  v97 = v62;
  DWORD2(v92[0]) = 0;
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_enum___MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007_(
    a1,
    &v96,
    v92);
  v63 = (const wchar_t *)word_1801DE252;
  do
    v64 = v63--;
  while ( !*v63 && v63 != L"StrokeMiterLimit" );
  v5 = *v63 == 0;
  *(_QWORD *)&v92[0] = L"StrokeMiterLimit";
  if ( !v5 )
    v63 = v64;
  *((_QWORD *)&v92[0] + 1) = v63;
  v96 = 0;
  v65 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetStrokeMiterLimit;
  HIDWORD(v92[0]) = HIDWORD(v63);
  v97 = v65;
  DWORD2(v92[0]) = 0;
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_float_(
    a1,
    &v96,
    v92);
  v66 = L"StrokeEndLineCap";
  do
    v67 = v66--;
  while ( v66 != L"StrokeThickness" && !*v66 );
  v5 = *v66 == 0;
  *(_QWORD *)&v92[0] = L"StrokeThickness";
  if ( !v5 )
    v66 = v67;
  *((_QWORD *)&v92[0] + 1) = v66;
  v96 = 0;
  v68 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetStrokeThickness;
  HIDWORD(v92[0]) = HIDWORD(v66);
  v97 = v68;
  DWORD2(v92[0]) = 0;
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_float_(
    a1,
    &v96,
    v92);
  v69 = L"StyleSimulations";
  do
    v70 = v69--;
  while ( !*v69 && v69 != L"SnapsToDevicePixels" );
  v5 = *v69 == 0;
  *(_QWORD *)&v92[0] = L"SnapsToDevicePixels";
  if ( !v5 )
    v69 = v70;
  *((_QWORD *)&v92[0] + 1) = v69;
  v96 = 0;
  v71 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetSnapToDevicePixels;
  HIDWORD(v92[0]) = HIDWORD(v69);
  v97 = v71;
  DWORD2(v92[0]) = 0;
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_bool_(
    a1,
    &v96,
    v92);
  v72 = (const wchar_t *)&word_1801DDD26;
  do
    v73 = v72--;
  while ( !*v72 && v72 != L"Stroke" );
  v5 = *v72 == 0;
  *(_QWORD *)&v92[0] = L"Stroke";
  if ( !v5 )
    v72 = v73;
  *((_QWORD *)&v92[0] + 1) = v72;
  v96 = 0;
  v74 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetStroke;
  HIDWORD(v92[0]) = HIDWORD(v72);
  v97 = v74;
  DWORD2(v92[0]) = 0;
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::MsXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_win_dox::XpsBrush_const___(
    a1,
    &v96,
    v92);
  v75 = (const wchar_t *)word_1801DE20A;
  do
    v76 = v75--;
  while ( !*v75 && v75 != L"Data" );
  v5 = *v75 == 0;
  *(_QWORD *)&v92[0] = L"Data";
  if ( !v5 )
    v75 = v76;
  *((_QWORD *)&v92[0] + 1) = v75;
  v96 = 0;
  v77 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetData;
  HIDWORD(v92[0]) = HIDWORD(v75);
  v97 = v77;
  DWORD2(v92[0]) = 0;
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_win_dox::XpsGeometries_const___(
    a1,
    &v96,
    v92);
  v78 = (const wchar_t *)word_1801DE1DA;
  do
    v79 = v78--;
  while ( !*v78 && v78 != L"Clip" );
  v5 = *v78 == 0;
  *(_QWORD *)&v92[0] = L"Clip";
  if ( !v5 )
    v78 = v79;
  *((_QWORD *)&v92[0] + 1) = v78;
  v96 = 0;
  v97 = v92[0];
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::VisualElementBuilder_xpsom::TXpsOMPath__win_dox::XpsGeometries_const___(
    a1,
    &v96);
  v80 = (const wchar_t *)word_1801DDD12;
  do
    v81 = v80--;
  while ( !*v80 && v80 != L"Fill" );
  v5 = *v80 == 0;
  *(_QWORD *)&v92[0] = L"Fill";
  if ( !v5 )
    v80 = v81;
  *((_QWORD *)&v92[0] + 1) = v80;
  v96 = 0;
  v82 = v92[0];
  *(_QWORD *)&v92[0] = xpsom::PathBuilder::SetFill;
  HIDWORD(v92[0]) = HIDWORD(v80);
  v97 = v82;
  DWORD2(v92[0]) = 0;
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::MsXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::PathBuilder_win_dox::XpsBrush_const___(
    a1,
    &v96,
    v92);
  v83 = L"Viewbox";
  do
    v84 = v83--;
  while ( v83 != L"RenderTransform" && !*v83 );
  v5 = *v83 == 0;
  *(_QWORD *)&v92[0] = L"RenderTransform";
  if ( !v5 )
    v83 = v84;
  *((_QWORD *)&v92[0] + 1) = v83;
  v96 = 0;
  v97 = v92[0];
  v98 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::VisualElementBuilder_xpsom::TXpsOMPath__win_dox::XpsMatrixTransform_const___(
    a1,
    &v96);
  v85 = (const wchar_t *)word_1801DDF02;
  while ( 1 )
  {
    v86 = v85--;
    v87 = *v85 == 0;
    if ( *v85 )
      break;
    if ( v85 == L"lang" )
    {
      v87 = *v85 == 0;
      break;
    }
  }
  if ( !v87 )
    v85 = v86;
  v88 = (const wchar_t *)word_1801DC99A;
  do
    v89 = v88--;
  while ( !*v88 && v88 != L"http://www.w3.org/XML/1998/namespace" );
  v5 = *v88 == 0;
  *(_QWORD *)&v92[0] = L"lang";
  if ( !v5 )
    v88 = v89;
  *((_QWORD *)&v92[0] + 1) = v85;
  v94 = v92[0];
  *((_QWORD *)&v93 + 1) = v88;
  *(_QWORD *)&v93 = L"http://www.w3.org/XML/1998/namespace";
  v95 = 0;
  win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::VisualElementBuilder_xpsom::TXpsOMPath__win_dox::XpsLanguage_const___(
    a1,
    &v93,
    L"http://www.w3.org/XML/1998/namespace",
    L"lang");
  v90 = win_musl::sax::qualified_name::make<wchar_t,64,wchar_t,4>(&v96);
  return win_musl::BindMemberOfReceiver_win_musl::MemberBindings_win_musl::MemberSetterOnReceiver__win_musl::ParseRemoteDictionaryResource_xpsom::OpenXpsBuilderTraits__::_2_::PageBodyReceiverTraitsWithTypeList_win_musl::sax::qualified_name_win_musl::sax::wchar_range____xpsom::VisualElementBuilder_xpsom::TXpsOMPath__std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___(
           a1,
           v90,
           xpsom::VisualElementBuilder<xpsom::TXpsOMGlyphs>::SetKey,
           xps_validation::StringValidateST_NUName);
}

```

## disassembly

```asm
0x18008d228  push    rbp
0x18008d22a  push    rbx
0x18008d22b  push    rsi
0x18008d22c  push    rdi
0x18008d22d  push    r14
0x18008d22f  push    r15
0x18008d231  lea     rbp, [rsp-2Fh]
0x18008d236  sub     rsp, 0A8h
0x18008d23d  mov     rax, [rcx+8]
0x18008d241  lea     r8, ?gc_pathRenderTransform@Element@Xps@win_musl@@3QB_WB; "Path.RenderTransform"
0x18008d248  sub     rax, [rcx]
0x18008d24b  mov     r15, 8E38E38E38E38E39h
0x18008d255  sar     rax, 3
0x18008d259  mov     rbx, rcx
0x18008d25c  imul    rax, r15
0x18008d260  xor     esi, esi
0x18008d262  mov     [rcx+30h], rax
0x18008d266  mov     [rcx+28h], rax
0x18008d26a  lea     rax, word_1801DE15A
0x18008d271  mov     rcx, rax
0x18008d274  add     rax, 0FFFFFFFFFFFFFFFEh
0x18008d278  cmp     [rax], si
0x18008d27b  jnz     short loc_18008D285
0x18008d27d  cmp     rax, r8
0x18008d280  jnz     short loc_18008D271
0x18008d282  cmp     [rax], si
0x18008d285  lea     rdi, word_1801DFA92
0x18008d28c  cmovnz  rax, rcx
0x18008d290  mov     rcx, rdi
0x18008d293  lea     r14, ?gc_FixedPage@MsXps@XpsDocument@XmlNamespaceUris@win_musl@@2QB_WB; "http://schemas.microsoft.com/xps/2005/0"...
0x18008d29a  mov     rdx, rcx
0x18008d29d  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18008d2a1  cmp     [rcx], si
0x18008d2a4  jnz     short loc_18008D2AB
0x18008d2a6  cmp     rcx, r14
0x18008d2a9  jnz     short loc_18008D29A
0x18008d2ab  cmp     [rcx], si
0x18008d2ae  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18008d2b2  lea     rax, ?SetPathRenderTransform@PathBuilder@xpsom@@QEAA?AVTransformBuilder@2@XZ; xpsom::PathBuilder::SetPathRenderTransform(void)
0x18008d2b9  mov     qword ptr [rbp+57h+var_B0], r8
0x18008d2bd  cmovnz  rcx, rdx
0x18008d2c1  movaps  xmm0, [rbp+57h+var_B0]
0x18008d2c5  lea     r8, [rbp+57h+var_B0]
0x18008d2c9  movdqu  [rbp+57h+var_80], xmm0
0x18008d2ce  mov     qword ptr [rbp+57h+var_90+8], rcx
0x18008d2d2  lea     rdx, [rbp+57h+var_90]
0x18008d2d6  xorps   xmm0, xmm0
0x18008d2d9  mov     qword ptr [rbp+57h+var_B0], rax
0x18008d2dd  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x18008d2e0  mov     rcx, rbx
0x18008d2e3  mov     qword ptr [rbp+57h+var_90], r14
0x18008d2e7  movdqu  [rbp+57h+var_70], xmm0
0x18008d2ec  mov     dword ptr [rbp+57h+var_B0+8], esi
0x18008d2ef  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x18008d2f2  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParsePage_xpsom__MsXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__PathBuilder_xpsom__TransformBuilder_
0x18008d2f7  lea     rax, dword_1801DE19C
0x18008d2fe  lea     r8, ?gc_pathClip@Element@Xps@win_musl@@3QB_WB; "Path.Clip"
0x18008d305  mov     rcx, rax
0x18008d308  add     rax, 0FFFFFFFFFFFFFFFEh
0x18008d30c  cmp     [rax], si
0x18008d30f  jnz     short loc_18008D319
0x18008d311  cmp     rax, r8
0x18008d314  jnz     short loc_18008D305
0x18008d316  cmp     [rax], si
0x18008d319  cmovnz  rax, rcx
0x18008d31d  mov     rcx, rdi
0x18008d320  mov     rdx, rcx
0x18008d323  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18008d327  cmp     [rcx], si
0x18008d32a  jnz     short loc_18008D331
0x18008d32c  cmp     rcx, r14
0x18008d32f  jnz     short loc_18008D320
0x18008d331  cmp     [rcx], si
0x18008d334  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18008d338  lea     rax, ?SetPathClip@PathBuilder@xpsom@@QEAA?AVGeometriesBuilder@2@XZ; xpsom::PathBuilder::SetPathClip(void)
0x18008d33f  mov     qword ptr [rbp+57h+var_B0], r8
0x18008d343  cmovnz  rcx, rdx
0x18008d347  movaps  xmm0, [rbp+57h+var_B0]
0x18008d34b  lea     r8, [rbp+57h+var_B0]
0x18008d34f  movdqu  [rbp+57h+var_80], xmm0
0x18008d354  mov     qword ptr [rbp+57h+var_90+8], rcx
0x18008d358  lea     rdx, [rbp+57h+var_90]
0x18008d35c  xorps   xmm0, xmm0
0x18008d35f  mov     qword ptr [rbp+57h+var_B0], rax
0x18008d363  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x18008d366  mov     rcx, rbx
0x18008d369  mov     qword ptr [rbp+57h+var_90], r14
0x18008d36d  movdqu  [rbp+57h+var_70], xmm0
0x18008d372  mov     dword ptr [rbp+57h+var_B0+8], esi
0x18008d375  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x18008d378  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParsePage_xpsom__MsXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__PathBuilder_xpsom__GeometriesBuilder_
0x18008d37d  lea     rax, word_1801DE182
0x18008d384  lea     r8, ?gc_pathOpacityMask@Element@Xps@win_musl@@3QB_WB; "Path.OpacityMask"
0x18008d38b  mov     rcx, rax
0x18008d38e  add     rax, 0FFFFFFFFFFFFFFFEh
0x18008d392  cmp     [rax], si
0x18008d395  jnz     short loc_18008D39F
0x18008d397  cmp     rax, r8
0x18008d39a  jnz     short loc_18008D38B
0x18008d39c  cmp     [rax], si
0x18008d39f  cmovnz  rax, rcx
0x18008d3a3  mov     rcx, rdi
0x18008d3a6  mov     rdx, rcx
0x18008d3a9  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18008d3ad  cmp     [rcx], si
0x18008d3b0  jnz     short loc_18008D3B7
0x18008d3b2  cmp     rcx, r14
0x18008d3b5  jnz     short loc_18008D3A6
0x18008d3b7  cmp     [rcx], si
0x18008d3ba  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18008d3be  lea     rax, ?SetPathOpacityMask@PathBuilder@xpsom@@QEAA?AVBrushBuilder@2@XZ; xpsom::PathBuilder::SetPathOpacityMask(void)
0x18008d3c5  mov     qword ptr [rbp+57h+var_B0], r8
0x18008d3c9  cmovnz  rcx, rdx
0x18008d3cd  movaps  xmm0, [rbp+57h+var_B0]
0x18008d3d1  lea     r8, [rbp+57h+var_B0]
0x18008d3d5  movdqu  [rbp+57h+var_80], xmm0
0x18008d3da  mov     qword ptr [rbp+57h+var_90+8], rcx
0x18008d3de  lea     rdx, [rbp+57h+var_90]
0x18008d3e2  xorps   xmm0, xmm0
0x18008d3e5  mov     qword ptr [rbp+57h+var_B0], rax
0x18008d3e9  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x18008d3ec  mov     rcx, rbx
0x18008d3ef  mov     qword ptr [rbp+57h+var_90], r14
0x18008d3f3  movdqu  [rbp+57h+var_70], xmm0
0x18008d3f8  mov     dword ptr [rbp+57h+var_B0+8], esi
0x18008d3fb  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x18008d3fe  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParsePage_xpsom__MsXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__PathBuilder_xpsom__BrushBuilder_
0x18008d403  lea     rax, dword_1801DE1CC
0x18008d40a  lea     r8, ?gc_pathFill@Element@Xps@win_musl@@3QB_WB; "Path.Fill"
0x18008d411  mov     rcx, rax
0x18008d414  add     rax, 0FFFFFFFFFFFFFFFEh
0x18008d418  cmp     [rax], si
0x18008d41b  jnz     short loc_18008D425
0x18008d41d  cmp     rax, r8
0x18008d420  jnz     short loc_18008D411
0x18008d422  cmp     [rax], si
0x18008d425  cmovnz  rax, rcx
0x18008d429  mov     rcx, rdi
0x18008d42c  mov     rdx, rcx
0x18008d42f  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18008d433  cmp     [rcx], si
0x18008d436  jnz     short loc_18008D43D
0x18008d438  cmp     rcx, r14
0x18008d43b  jnz     short loc_18008D42C
0x18008d43d  cmp     [rcx], si
0x18008d440  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18008d444  lea     rax, ?SetPathFill@PathBuilder@xpsom@@QEAA?AVBrushBuilder@2@XZ; xpsom::PathBuilder::SetPathFill(void)
0x18008d44b  mov     qword ptr [rbp+57h+var_B0], r8
0x18008d44f  cmovnz  rcx, rdx
0x18008d453  movaps  xmm0, [rbp+57h+var_B0]
0x18008d457  lea     r8, [rbp+57h+var_B0]
0x18008d45b  movdqu  [rbp+57h+var_80], xmm0
0x18008d460  mov     qword ptr [rbp+57h+var_90+8], rcx
0x18008d464  lea     rdx, [rbp+57h+var_90]
0x18008d468  xorps   xmm0, xmm0
0x18008d46b  mov     qword ptr [rbp+57h+var_B0], rax
0x18008d46f  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x18008d472  mov     rcx, rbx
0x18008d475  mov     qword ptr [rbp+57h+var_90], r14
0x18008d479  movdqu  [rbp+57h+var_70], xmm0
0x18008d47e  mov     dword ptr [rbp+57h+var_B0+8], esi
0x18008d481  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x18008d484  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParsePage_xpsom__MsXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__PathBuilder_xpsom__BrushBuilder_
0x18008d489  lea     rax, ?gc_pathRenderTransform@Element@Xps@win_musl@@3QB_WB; "Path.RenderTransform"
0x18008d490  lea     r8, ?gc_pathStroke@Element@Xps@win_musl@@3QB_WB; "Path.Stroke"
0x18008d497  mov     rcx, rax
0x18008d49a  add     rax, 0FFFFFFFFFFFFFFFEh
0x18008d49e  cmp     [rax], si
0x18008d4a1  jnz     short loc_18008D4AB
0x18008d4a3  cmp     rax, r8
0x18008d4a6  jnz     short loc_18008D497
0x18008d4a8  cmp     [rax], si
0x18008d4ab  cmovnz  rax, rcx
0x18008d4af  mov     rcx, rdi
0x18008d4b2  mov     rdx, rcx
0x18008d4b5  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18008d4b9  cmp     [rcx], si
0x18008d4bc  jnz     short loc_18008D4C3
0x18008d4be  cmp     rcx, r14
0x18008d4c1  jnz     short loc_18008D4B2
0x18008d4c3  cmp     [rcx], si
0x18008d4c6  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18008d4ca  lea     rax, ?SetPathStroke@PathBuilder@xpsom@@QEAA?AVBrushBuilder@2@XZ; xpsom::PathBuilder::SetPathStroke(void)
0x18008d4d1  mov     qword ptr [rbp+57h+var_B0], r8
0x18008d4d5  cmovnz  rcx, rdx
0x18008d4d9  movaps  xmm0, [rbp+57h+var_B0]
0x18008d4dd  lea     r8, [rbp+57h+var_B0]
0x18008d4e1  movdqu  [rbp+57h+var_80], xmm0
0x18008d4e6  mov     qword ptr [rbp+57h+var_90+8], rcx
0x18008d4ea  lea     rdx, [rbp+57h+var_90]
0x18008d4ee  xorps   xmm0, xmm0
0x18008d4f1  mov     qword ptr [rbp+57h+var_B0], rax
0x18008d4f5  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x18008d4f8  mov     rcx, rbx
0x18008d4fb  mov     qword ptr [rbp+57h+var_90], r14
0x18008d4ff  movdqu  [rbp+57h+var_70], xmm0
0x18008d504  mov     dword ptr [rbp+57h+var_B0+8], esi
0x18008d507  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x18008d50a  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParsePage_xpsom__MsXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__PathBuilder_xpsom__BrushBuilder_
0x18008d50f  lea     rax, dword_1801DE1B4
0x18008d516  lea     rdx, ?gc_pathData@Element@Xps@win_musl@@3QB_WB; "Path.Data"
0x18008d51d  mov     rcx, rax
0x18008d520  add     rax, 0FFFFFFFFFFFFFFFEh
0x18008d524  cmp     [rax], si
0x18008d527  jnz     short loc_18008D531
0x18008d529  cmp     rax, rdx
0x18008d52c  jnz     short loc_18008D51D
0x18008d52e  cmp     [rax], si
0x18008d531  cmovnz  rax, rcx
0x18008d535  mov     rcx, rdi
0x18008d538  add     rdi, 0FFFFFFFFFFFFFFFEh
0x18008d53c  cmp     [rdi], si
0x18008d53f  jnz     short loc_18008D546
0x18008d541  cmp     rdi, r14
0x18008d544  jnz     short loc_18008D535
0x18008d546  cmp     [rdi], si
0x18008d549  lea     r8, [rbp+57h+var_B0]
0x18008d54d  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18008d551  lea     rax, ?SetPathData@PathBuilder@xpsom@@QEAA?AVGeometriesBuilder@2@XZ; xpsom::PathBuilder::SetPathData(void)
0x18008d558  mov     qword ptr [rbp+57h+var_B0], rdx
0x18008d55c  cmovnz  rdi, rcx
0x18008d560  movaps  xmm0, [rbp+57h+var_B0]
0x18008d564  lea     rdx, [rbp+57h+var_90]
0x18008d568  movdqu  [rbp+57h+var_80], xmm0
0x18008d56d  mov     qword ptr [rbp+57h+var_B0], rax
0x18008d571  mov     rcx, rbx
0x18008d574  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x18008d577  xorps   xmm0, xmm0
0x18008d57a  movdqu  [rbp+57h+var_70], xmm0
0x18008d57f  mov     qword ptr [rbp+57h+var_90], r14
0x18008d583  mov     qword ptr [rbp+57h+var_90+8], rdi
0x18008d587  mov     dword ptr [rbp+57h+var_B0+8], esi
0x18008d58a  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x18008d58d  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParsePage_xpsom__MsXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__PathBuilder_xpsom__GeometriesBuilder_
0x18008d592  mov     rax, [rbx+8]
0x18008d596  lea     rcx, [rbp+57h+var_B0]
0x18008d59a  sub     rax, [rbx]
0x18008d59d  sar     rax, 3
0x18008d5a1  imul    rax, r15
0x18008d5a5  mov     [rbx+30h], rax
0x18008d5a9  call    ??$make@_W$0BK@@local_name@sax@win_musl@@SA?AU012@AEAY0BK@$$CB_W@Z; win_musl::sax::local_name::make<wchar_t,26>(wchar_t const (&)[26])
0x18008d5ae  lea     r8, ?SetAutomationPropertiesName@?$AutomationPropertiesBuilder@VTXpsOMPath@xpsom@@@xpsom@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsom::AutomationPropertiesBuilder<xpsom::TXpsOMPath>::SetAutomationPropertiesName(std::wstring const &)
0x18008d5b5  mov     rcx, rbx
0x18008d5b8  lea     rdx, [rbp+57h+var_90]
0x18008d5bc  movups  xmm1, xmmword ptr [rax]
0x18008d5bf  movups  xmm0, xmmword ptr [rax+10h]
0x18008d5c3  movups  [rbp+57h+var_90], xmm1
0x18008d5c7  xorps   xmm1, xmm1
0x18008d5ca  movdqu  [rbp+57h+var_70], xmm1
0x18008d5cf  movups  [rbp+57h+var_80], xmm0
0x18008d5d3  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParseRemoteDictionaryResource_xpsom__OpenXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__AutomationPropertiesBuilder_xpsom__TXpsOMPath__std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t____const___
0x18008d5d8  lea     rcx, [rbp+57h+var_B0]
0x18008d5dc  call    ??$make@_W$0BO@@local_name@sax@win_musl@@SA?AU012@AEAY0BO@$$CB_W@Z; win_musl::sax::local_name::make<wchar_t,30>(wchar_t const (&)[30])
0x18008d5e1  lea     r8, ?SetAutomationPropertiesHelpText@?$AutomationPropertiesBuilder@VTXpsOMPath@xpsom@@@xpsom@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsom::AutomationPropertiesBuilder<xpsom::TXpsOMPath>::SetAutomationPropertiesHelpText(std::wstring const &)
0x18008d5e8  mov     rcx, rbx
0x18008d5eb  lea     rdx, [rbp+57h+var_90]
0x18008d5ef  movups  xmm1, xmmword ptr [rax]
0x18008d5f2  movups  xmm0, xmmword ptr [rax+10h]
0x18008d5f6  movups  [rbp+57h+var_90], xmm1
0x18008d5fa  xorps   xmm1, xmm1
0x18008d5fd  movdqu  [rbp+57h+var_70], xmm1
0x18008d602  movups  [rbp+57h+var_80], xmm0
0x18008d606  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParseRemoteDictionaryResource_xpsom__OpenXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__AutomationPropertiesBuilder_xpsom__TXpsOMPath__std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t____const___
0x18008d60b  lea     rax, word_1801DDFC2
0x18008d612  lea     rdx, ?gc_name@Attribute@Xps@win_musl@@3QB_WB; "Name"
0x18008d619  mov     rcx, rax
0x18008d61c  add     rax, 0FFFFFFFFFFFFFFFEh
0x18008d620  cmp     [rax], si
0x18008d623  jnz     short loc_18008D62A
0x18008d625  cmp     rax, rdx
0x18008d628  jnz     short loc_18008D619
0x18008d62a  cmp     [rax], si
0x18008d62d  lea     r9, ?StringValidateST_Name@xps_validation@@YA_NAEBUwchar_range@sax@win_musl@@@Z; xps_validation::StringValidateST_Name(win_musl::sax::wchar_range const &)
0x18008d634  xorps   xmm0, xmm0
0x18008d637  mov     qword ptr [rbp+57h+var_B0], rdx
0x18008d63b  cmovnz  rax, rcx
0x18008d63f  lea     r8, ?SetName@?$VisualElementBuilder@VTXpsOMPath@xpsom@@@xpsom@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsom::VisualElementBuilder<xpsom::TXpsOMPath>::SetName(std::wstring const &)
0x18008d646  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18008d64a  lea     rdx, [rbp+57h+var_90]
0x18008d64e  movdqu  [rbp+57h+var_90], xmm0
0x18008d653  mov     rcx, rbx
0x18008d656  movaps  xmm0, [rbp+57h+var_B0]
0x18008d65a  xorps   xmm1, xmm1
0x18008d65d  movdqu  [rbp+57h+var_80], xmm0
0x18008d662  movdqu  [rbp+57h+var_70], xmm1
0x18008d667  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParseRemoteDictionaryResource_xpsom__OpenXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__VisualElementBuilder_xpsom__TXpsOMPath__std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t____const___
0x18008d66c  lea     rcx, [rbp+57h+var_B0]
0x18008d670  call    ??$make@_W$0BG@@local_name@sax@win_musl@@SA?AU012@AEAY0BG@$$CB_W@Z; win_musl::sax::local_name::make<wchar_t,22>(wchar_t const (&)[22])
0x18008d675  xor     r9d, r9d
0x18008d678  lea     r8, ?SetNavigateUri@?$VisualElementBuilder@VTXpsOMPath@xpsom@@@xpsom@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsom::VisualElementBuilder<xpsom::TXpsOMPath>::SetNavigateUri(std::wstring const &)
0x18008d67f  lea     rdx, [rbp+57h+var_90]
0x18008d683  mov     rcx, rbx
0x18008d686  movups  xmm1, xmmword ptr [rax]
0x18008d689  movups  xmm0, xmmword ptr [rax+10h]
0x18008d68d  movups  [rbp+57h+var_90], xmm1
0x18008d691  xorps   xmm1, xmm1
0x18008d694  movdqu  [rbp+57h+var_70], xmm1
0x18008d699  movups  [rbp+57h+var_80], xmm0
0x18008d69d  call    win_musl__BindMemberOfReceiver_win_musl__MemberBindings_win_musl__MemberSetterOnReceiver__win_musl__ParseRemoteDictionaryResource_xpsom__OpenXpsBuilderTraits_____2___PageBodyReceiverTraitsWithTypeList_win_musl__sax__qualified_name_win_musl__sax__wchar_range____xpsom__VisualElementBuilder_xpsom__TXpsOMPath__std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t____const___
0x18008d6a2  lea     rax, _GUID_95a9435e_12bb_461b_8e7f_c6adb04cd96a
  ... truncated ...
```
