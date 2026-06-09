# RemoteTextAppIntegration_ToPdu::Initialize(Windows::System::RemoteDesktop::Input::IRemoteTextConnectionDataHandler *,_GUID)

- ea: `0x180045f84`
- end: `0x18004736f`
- name: `?Initialize@RemoteTextAppIntegration_ToPdu@@QEAAXPEAUIRemoteTextConnectionDataHandler@Input@RemoteDesktop@System@Windows@@U_GUID@@@Z`
- size: `5099`
- prototype: `void __fastcall(RemoteTextAppIntegration_ToPdu *__hidden this, struct Windows::System::RemoteDesktop::Input::IRemoteTextConnectionDataHandler *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036a80`

## callees

- `0x180002240`
- `0x180002270`
- `0x180004190`
- `0x180012030`
- `0x180012074`
- `0x18004541c`
- `0x1800454b8`
- `0x180045554`
- `0x1800455f0`
- `0x18004568c`
- `0x180045728`
- `0x1800457c4`
- `0x180045860`
- `0x1800458fc`
- `0x180045998`
- `0x180045a34`
- `0x180045ad0`
- `0x180045b6c`
- `0x180045f84`
- `0x18004f32c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004603a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004603a`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180045fc2`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180045fc2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046057`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046057`

## string_xrefs

- `0x1800470ca`: `onecore\internal\sdk\inc\wil\opensource/wil/com.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
void __fastcall RemoteTextAppIntegration_ToPdu::Initialize(
        RemoteTextAppIntegration_ToPdu *this,
        struct Windows::System::RemoteDesktop::Input::IRemoteTextConnectionDataHandler *a2,
        struct _GUID *a3)
{
  int AgileReference; // eax
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rbx
  void (__fastcall *v15)(__int64, HSTRING_HEADER *, char *); // rdi
  char *v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD *, RemoteTextAppIntegration_ToPdu *); // r15
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD *, char *); // r15
  _QWORD *v25; // rax
  _QWORD *v26; // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD *, char *); // r15
  _QWORD *v30; // rax
  _QWORD *v31; // rbx
  int v32; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, _QWORD *, char *); // r15
  _QWORD *v35; // rax
  _QWORD *v36; // rbx
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, _QWORD *, char *); // r15
  _QWORD *v40; // rax
  _QWORD *v41; // rbx
  int v42; // eax
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, _QWORD *, char *); // r15
  _QWORD *v45; // rax
  _QWORD *v46; // rbx
  int v47; // eax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, _QWORD *, char *); // r15
  _QWORD *v50; // rax
  _QWORD *v51; // rbx
  int v52; // eax
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, _QWORD *, char *); // r15
  _QWORD *v55; // rax
  _QWORD *v56; // rbx
  int v57; // eax
  __int64 v58; // rdi
  __int64 (__fastcall *v59)(__int64, _QWORD *, char *); // r15
  _QWORD *v60; // rax
  _QWORD *v61; // rbx
  int v62; // eax
  __int64 v63; // rdi
  __int64 (__fastcall *v64)(__int64, _QWORD *, char *); // r15
  _QWORD *v65; // rax
  _QWORD *v66; // rbx
  int v67; // eax
  __int64 v68; // rdi
  __int64 (__fastcall *v69)(__int64, _QWORD *, char *); // r15
  _QWORD *v70; // rax
  _QWORD *v71; // rbx
  int v72; // eax
  __int64 v73; // rdi
  __int64 (__fastcall *v74)(__int64, _QWORD *, char *); // r15
  _QWORD *v75; // rax
  _QWORD *v76; // rbx
  int v77; // eax
  __int64 v78; // rdi
  __int64 (__fastcall *v79)(__int64, _QWORD *, char *); // r15
  _QWORD *v80; // rax
  _QWORD *v81; // rbx
  int v82; // eax
  __int64 v83; // rdi
  __int64 (__fastcall *v84)(__int64, _QWORD *, char *); // r15
  _QWORD *v85; // rax
  _QWORD *v86; // rbx
  int v87; // eax
  __int64 v88; // rdi
  __int64 (__fastcall *v89)(__int64, _QWORD *, char *); // r15
  _QWORD *v90; // rax
  _QWORD *v91; // rbx
  int v92; // eax
  __int64 v93; // rdi
  __int64 (__fastcall *v94)(__int64, _QWORD *, char *); // r15
  _QWORD *v95; // rax
  _QWORD *v96; // rbx
  int v97; // eax
  __int64 v98; // rdi
  __int64 (__fastcall *v99)(__int64, _QWORD *, char *); // r15
  _QWORD *v100; // rax
  _QWORD *v101; // rbx
  int v102; // eax
  __int64 v103; // rdi
  __int64 (__fastcall *v104)(__int64, _QWORD *, char *); // r15
  _QWORD *v105; // rax
  _QWORD *v106; // rbx
  int v107; // eax
  __int64 v108; // rdi
  __int64 (__fastcall *v109)(__int64, _QWORD *, char *); // r15
  _QWORD *v110; // rax
  _QWORD *v111; // rbx
  int v112; // eax
  __int64 v113; // rdi
  __int64 (__fastcall *v114)(__int64, _QWORD, char *); // rbx
  _QWORD *v115; // rax
  int v116; // eax
  __int64 v117; // rdi
  __int64 (__fastcall *v118)(__int64, _QWORD, char *); // rbx
  _QWORD *v119; // rax
  int v120; // eax
  __int64 v121; // rdi
  __int64 (__fastcall *v122)(__int64, _QWORD, char *); // rbx
  _QWORD *v123; // rax
  int v124; // eax
  __int64 v125; // rdi
  __int64 (__fastcall *v126)(__int64, _QWORD, char *); // rbx
  _QWORD *v127; // rax
  int v128; // eax
  __int64 v129; // rdi
  __int64 (__fastcall *v130)(__int64, _QWORD, char *); // rbx
  _QWORD *v131; // rax
  int v132; // eax
  __int64 v133; // rdi
  __int64 (__fastcall *v134)(__int64, _QWORD, char *); // rbx
  _QWORD *v135; // rax
  int v136; // eax
  __int64 v137; // rdi
  __int64 (__fastcall *v138)(__int64, _QWORD, char *); // rbx
  _QWORD *v139; // rax
  int v140; // eax
  __int64 v141; // rdi
  __int64 (__fastcall *v142)(__int64, _QWORD, char *); // rbx
  _QWORD *v143; // rax
  int v144; // eax
  __int64 v145; // rdi
  __int64 (__fastcall *v146)(__int64, _QWORD, char *); // rbx
  _QWORD *v147; // rax
  int v148; // eax
  __int64 v149; // rdi
  __int64 (__fastcall *v150)(__int64, _QWORD, char *); // rbx
  _QWORD *v151; // rax
  int v152; // eax
  __int64 v153; // rdi
  __int64 (__fastcall *v154)(__int64, _QWORD, char *); // rbx
  _QWORD *v155; // rax
  int v156; // eax
  __int64 v157; // rdi
  __int64 (__fastcall *v158)(__int64, _QWORD, char *); // rbx
  _QWORD *v159; // rax
  int v160; // eax
  _QWORD *v161; // [rsp+20h] [rbp-40h] BYREF
  __int64 v162; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v161 = 0;
  AgileReference = RoGetAgileReference(0, &GUID_099ffbc8_8bcb_41b5_b056_57e77021bf1b, a2, &v161);
  if ( AgileReference < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x72B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/com.h",
      (const char *)(unsigned int)AgileReference,
      (int)v161);
  v6 = v161;
  v7 = 0;
  v161 = 0;
  v8 = *((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = v6;
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v7 = v161;
  }
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  v162 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(
         L"Windows.UI.Internal.Text.Remote.RemoteTextAppIntegration",
         0x38u,
         &hstringHeader,
         &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
LABEL_176:
    wil::details::in1diag3::_Throw_Hr(
      v13,
      (void *)0x49,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v161);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_e43158d1_8fc2_4ddc_9b23_7dcd37aeec1f, &v162);
  v13 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_176;
  string = 0;
  v14 = v162;
  v15 = *(void (__fastcall **)(__int64, HSTRING_HEADER *, char *))(*(_QWORD *)v162 + 48LL);
  v16 = (char *)this + 264;
  v17 = *((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  *(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *a3;
  v15(v14, &hstringHeader, (char *)this + 264);
  v18 = *(_QWORD *)v16;
  v19 = *(__int64 (__fastcall **)(__int64, _QWORD *, RemoteTextAppIntegration_ToPdu *))(**(_QWORD **)v16 + 64LL);
  v20 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v20;
  if ( v20 )
  {
    *v20 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v20 + 3) = 1;
    *v20 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextKeyTransitionedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v21[2] = this;
    v21[3] = RemoteTextAppIntegration_ToPdu::OnKeyTransitioned;
    *v21 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextKeyTransitionedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyTransitionedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyTransitionedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextKeyTransitionedEventArgs *>,_lambda_f4a1295c0cfb20176d787f15aa255d3d_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyTransitionedEventArgs *>::`vftable';
  }
  else
  {
    v21 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v21;
  v22 = v19(v18, v21, this);
  if ( v22 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v22,
      (int)v161);
  if ( v21 )
    (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
  v23 = *(_QWORD *)v16;
  v24 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 80LL);
  v25 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v25;
  if ( v25 )
  {
    *v25 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v25 + 3) = 1;
    *v25 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v26[2] = this;
    v26[3] = RemoteTextAppIntegration_ToPdu::OnHostOperationAcknowledged;
    *v26 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextHostOperationAcknowledgedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextHostOperationAcknowledgedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *>,_lambda_5a448bf274695e84378b4186f9e06f5d_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextHostOperationAcknowledgedEventArgs *>::`vftable';
  }
  else
  {
    v26 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v26;
  v27 = v24(v23, v26, (char *)this + 8);
  if ( v27 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v27,
      (int)v161);
  if ( v26 )
    (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
  v28 = *(_QWORD *)v16;
  v29 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 96LL);
  v30 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v31 = v30;
  if ( v30 )
  {
    *v30 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v30 + 3) = 1;
    *v30 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextCharacterGeneratedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v31[2] = this;
    v31[3] = RemoteTextAppIntegration_ToPdu::OnCharacterGenerated;
    *v31 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextCharacterGeneratedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextCharacterGeneratedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCharacterGeneratedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextCharacterGeneratedEventArgs *>,_lambda_97c7cd3ed3477c3de4a2abdfbd3a2a2f_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCharacterGeneratedEventArgs *>::`vftable';
  }
  else
  {
    v31 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v31;
  v32 = v29(v28, v31, (char *)this + 16);
  if ( v32 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v32,
      (int)v161);
  if ( v31 )
    (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
  v33 = *(_QWORD *)v16;
  v34 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 112LL);
  v35 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v36 = v35;
  if ( v35 )
  {
    *v35 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v35 + 3) = 1;
    *v35 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusNavigatingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v36[2] = this;
    v36[3] = RemoteTextAppIntegration_ToPdu::OnFocusNavigating;
    *v36 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextFocusNavigatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusNavigatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusNavigatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusNavigatingEventArgs *>,_lambda_bdf1a5dc2a72afac61c7dc63c6119ef1_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusNavigatingEventArgs *>::`vftable';
  }
  else
  {
    v36 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v36;
  v37 = v34(v33, v36, (char *)this + 24);
  if ( v37 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v37,
      (int)v161);
  if ( v36 )
    (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
  v38 = *(_QWORD *)v16;
  v39 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 128LL);
  v40 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v41 = v40;
  if ( v40 )
  {
    *v40 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v40 + 3) = 1;
    *v40 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusDepartedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v41[2] = this;
    v41[3] = RemoteTextAppIntegration_ToPdu::OnFocusDeparted;
    *v41 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextFocusDepartedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusDepartedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusDepartedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusDepartedEventArgs *>,_lambda_314f27c2251652a69f5008c7f508a96e_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusDepartedEventArgs *>::`vftable';
  }
  else
  {
    v41 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v41;
  v42 = v39(v38, v41, (char *)this + 32);
  if ( v42 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v42,
      (int)v161);
  if ( v41 )
    (*(void (__fastcall **)(_QWORD *))(*v41 + 16LL))(v41);
  v43 = *(_QWORD *)v16;
  v44 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 144LL);
  v45 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v46 = v45;
  if ( v45 )
  {
    *v45 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v45 + 3) = 1;
    *v45 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextEnableWindowRequestedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v46[2] = this;
    v46[3] = RemoteTextAppIntegration_ToPdu::OnEnableWindowRequested;
    *v46 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextEnableWindowRequestedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextEnableWindowRequestedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextEnableWindowRequestedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextEnableWindowRequestedEventArgs *>,_lambda_5fdcebb8490a9087c7e134b46411f198_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextEnableWindowRequestedEventArgs *>::`vftable';
  }
  else
  {
    v46 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v46;
  v47 = v44(v43, v46, (char *)this + 40);
  if ( v47 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v47,
      (int)v161);
  if ( v46 )
    (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
  v48 = *(_QWORD *)v16;
  v49 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 160LL);
  v50 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v51 = v50;
  if ( v50 )
  {
    *v50 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v50 + 3) = 1;
    *v50 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextDisableWindowRequestedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v51[2] = this;
    v51[3] = RemoteTextAppIntegration_ToPdu::OnDisableWindowRequested;
    *v51 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextDisableWindowRequestedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextDisableWindowRequestedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextDisableWindowRequestedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextDisableWindowRequestedEventArgs *>,_lambda_31a0ff3b01f8ec146269cb56f9039588_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextDisableWindowRequestedEventArgs *>::`vftable';
  }
  else
  {
    v51 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v51;
  v52 = v49(v48, v51, (char *)this + 48);
  if ( v52 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v52,
      (int)v161);
  if ( v51 )
    (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
  v53 = *(_QWORD *)v16;
  v54 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 176LL);
  v55 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v56 = v55;
  if ( v55 )
  {
    *v55 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v55 + 3) = 1;
    *v55 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextActivationStateRequestedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v56[2] = this;
    v56[3] = RemoteTextAppIntegration_ToPdu::OnActivationStateRequested;
    *v56 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextActivationStateRequestedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextActivationStateRequestedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextActivationStateRequestedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextActivationStateRequestedEventArgs *>,_lambda_c735c0358cdc83988191c74f0408662b_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextActivationStateRequestedEventArgs *>::`vftable';
  }
  else
  {
    v56 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v56;
  v57 = v54(v53, v56, (char *)this + 56);
  if ( v57 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v57,
      (int)v161);
  if ( v56 )
    (*(void (__fastcall **)(_QWORD *))(*v56 + 16LL))(v56);
  v58 = *(_QWORD *)v16;
  v59 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 192LL);
  v60 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v61 = v60;
  if ( v60 )
  {
    *v60 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v60 + 3) = 1;
    *v60 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v61[2] = this;
    v61[3] = RemoteTextAppIntegration_ToPdu::OnNonComponentUIHostDetected;
    *v61 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextNonComponentUIHostDetectedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextNonComponentUIHostDetectedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,_lambda_c7cebfaf0f020bc3fa9246cb61d3c9aa_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextNonComponentUIHostDetectedEventArgs *>::`vftable';
  }
  else
  {
    v61 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v61;
  v62 = v59(v58, v61, (char *)this + 64);
  if ( v62 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v62,
      (int)v161);
  if ( v61 )
    (*(void (__fastcall **)(_QWORD *))(*v61 + 16LL))(v61);
  v63 = *(_QWORD *)v16;
  v64 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 208LL);
  v65 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v66 = v65;
  if ( v65 )
  {
    *v65 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v65 + 3) = 1;
    *v65 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextKeyEventPayloadStartingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v66[2] = this;
    v66[3] = RemoteTextAppIntegration_ToPdu::OnKeyEventPayloadStarting;
    *v66 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextKeyEventPayloadStartingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadStartingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadStartingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextKeyEventPayloadStartingEventArgs *>,_lambda_c2b9abcc2025cd9c521bca5d1d8866ca_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadStartingEventArgs *>::`vftable';
  }
  else
  {
    v66 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v66;
  v67 = v64(v63, v66, (char *)this + 72);
  if ( v67 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v67,
      (int)v161);
  if ( v66 )
    (*(void (__fastcall **)(_QWORD *))(*v66 + 16LL))(v66);
  v68 = *(_QWORD *)v16;
  v69 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 224LL);
  v70 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v71 = v70;
  if ( v70 )
  {
    *v70 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v70 + 3) = 1;
    *v70 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextKeyEventPayloadCompletedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v71[2] = this;
    v71[3] = RemoteTextAppIntegration_ToPdu::OnKeyEventPayloadCompleted;
    *v71 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextKeyEventPayloadCompletedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextKeyEventPayloadCompletedEventArgs *>,_lambda_e32cd8d788d14c5540c23fa05eaf6c74_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs *>::`vftable';
  }
  else
  {
    v71 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v71;
  v72 = v69(v68, v71, (char *)this + 80);
  if ( v72 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v72,
      (int)v161);
  if ( v71 )
    (*(void (__fastcall **)(_QWORD *))(*v71 + 16LL))(v71);
  v73 = *(_QWORD *)v16;
  v74 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 240LL);
  v75 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v76 = v75;
  if ( v75 )
  {
    *v75 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v75 + 3) = 1;
    *v75 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextUpdatingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v76[2] = this;
    v76[3] = RemoteTextAppIntegration_ToPdu::OnTextUpdating;
    *v76 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextTextUpdatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextUpdatingEventArgs *>,_lambda_d1ab304ff01179ad38b9aa4818b93c9f_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs *>::`vftable';
  }
  else
  {
    v76 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v76;
  v77 = v74(v73, v76, (char *)this + 88);
  if ( v77 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v77,
      (int)v161);
  if ( v76 )
    (*(void (__fastcall **)(_QWORD *))(*v76 + 16LL))(v76);
  v78 = *(_QWORD *)v16;
  v79 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 256LL);
  v80 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v81 = v80;
  if ( v80 )
  {
    *v80 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v80 + 3) = 1;
    *v80 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v81[2] = this;
    v81[3] = RemoteTextAppIntegration_ToPdu::OnTextAndSelectionUpdating;
    *v81 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextTextAndSelectionUpdatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextTextAndSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>,_lambda_fc34677ceb914158761e14abc4f81fd4_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextTextAndSelectionUpdatingEventArgs *>::`vftable';
  }
  else
  {
    v81 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v81;
  v82 = v79(v78, v81, (char *)this + 96);
  if ( v82 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v82,
      (int)v161);
  if ( v81 )
    (*(void (__fastcall **)(_QWORD *))(*v81 + 16LL))(v81);
  v83 = *(_QWORD *)v16;
  v84 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 272LL);
  v85 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v86 = v85;
  if ( v85 )
  {
    *v85 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v85 + 3) = 1;
    *v85 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextSelectionUpdatingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v86[2] = this;
    v86[3] = RemoteTextAppIntegration_ToPdu::OnSelectionUpdating;
    *v86 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextSelectionUpdatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextSelectionUpdatingEventArgs *>,_lambda_07c0e56743ffd7e05866c0792a4f5695_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextSelectionUpdatingEventArgs *>::`vftable';
  }
  else
  {
    v86 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v86;
  v87 = v84(v83, v86, (char *)this + 104);
  if ( v87 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v87,
      (int)v161);
  if ( v86 )
    (*(void (__fastcall **)(_QWORD *))(*v86 + 16LL))(v86);
  v88 = *(_QWORD *)v16;
  v89 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 288LL);
  v90 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v91 = v90;
  if ( v90 )
  {
    *v90 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v90 + 3) = 1;
    *v90 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFormatUpdatingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v91[2] = this;
    v91[3] = RemoteTextAppIntegration_ToPdu::OnFormatUpdating;
    *v91 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextFormatUpdatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextFormatUpdatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFormatUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFormatUpdatingEventArgs *>,_lambda_38b0297ef42acc2bb588675898337f66_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFormatUpdatingEventArgs *>::`vftable';
  }
  else
  {
    v91 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v91;
  v92 = v89(v88, v91, (char *)this + 112);
  if ( v92 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v92,
      (int)v161);
  if ( v91 )
    (*(void (__fastcall **)(_QWORD *))(*v91 + 16LL))(v91);
  v93 = *(_QWORD *)v16;
  v94 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 304LL);
  v95 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v96 = v95;
  if ( v95 )
  {
    *v95 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v95 + 3) = 1;
    *v95 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextCompositionUpdatingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v96[2] = this;
    v96[3] = RemoteTextAppIntegration_ToPdu::OnCompositionUpdating;
    *v96 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextCompositionUpdatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextCompositionUpdatingEventArgs *>,_lambda_7065d59a3be50cb07582d564022b7f91_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *>::`vftable';
  }
  else
  {
    v96 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v96;
  v97 = v94(v93, v96, (char *)this + 120);
  if ( v97 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v97,
      (int)v161);
  if ( v96 )
    (*(void (__fastcall **)(_QWORD *))(*v96 + 16LL))(v96);
  v98 = *(_QWORD *)v16;
  v99 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 320LL);
  v100 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v101 = v100;
  if ( v100 )
  {
    *v100 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v100 + 3) = 1;
    *v100 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextCompositionInfoUpdatingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v101[2] = this;
    v101[3] = RemoteTextAppIntegration_ToPdu::OnCompositionInfoUpdating;
    *v101 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextCompositionInfoUpdatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextCompositionInfoUpdatingEventArgs *>,_lambda_ded93986f0ac489d010f5933d4d306de_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *>::`vftable';
  }
  else
  {
    v101 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v101;
  v102 = v99(v98, v101, (char *)this + 128);
  if ( v102 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v102,
      (int)v161);
  if ( v101 )
    (*(void (__fastcall **)(_QWORD *))(*v101 + 16LL))(v101);
  v103 = *(_QWORD *)v16;
  v104 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 336LL);
  v105 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v106 = v105;
  if ( v105 )
  {
    *v105 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v105 + 3) = 1;
    *v105 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v106[2] = this;
    v106[3] = RemoteTextAppIntegration_ToPdu::OnReconversionCandidatesUpdating;
    *v106 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextReconversionCandidatesUpdatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextReconversionCandidatesUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>,_lambda_4223d34871e01ffa446a89c6e4b2af04_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
  }
  else
  {
    v106 = 0;
  }
  hstringHeader.Reserved.Reserved1 = v106;
  v107 = v104(v103, v106, (char *)this + 136);
  if ( v107 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v107,
      (int)v161);
  if ( v106 )
    (*(void (__fastcall **)(_QWORD *))(*v106 + 16LL))(v106);
  v108 = *(_QWORD *)v16;
  v109 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(**(_QWORD **)v16 + 352LL);
  v110 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v111 = v110;
  if ( v110 )
  {
    *v110 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
    *((_DWORD *)v110 + 3) = 1;
    *v110 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextInputLocaleUpdatingEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v111[2] = this;
    v111[3] = RemoteTextAppIntegration_ToPdu::OnInputLocaleUpdating;
    *v111 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextInputLocaleUpdatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextInputLocaleUpdatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextInputLocaleUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextInputLocaleUpdatingEventArgs *>,_lambda_e068e3a0ff4e9f58d966ad051cd156fb_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextInputLocaleUpdatingEventArgs *>::`vftable';
  }
  else
  {
    v111 = 0;
  }
  v161 = v111;
  v112 = v109(v108, v111, (char *)this + 144);
  if ( v112 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v112,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&v161);
  v113 = *(_QWORD *)v16;
  v114 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 368LL);
  v115 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextInputProfileUpdatingEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextInputProfileUpdatingEventArgs *>(
                     &v161,
                     this);
  v116 = v114(v113, *v115, (char *)this + 152);
  if ( v116 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v116,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&v161);
  v117 = *(_QWORD *)v16;
  v118 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 384LL);
  v119 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFeatureModeUpdatingEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFeatureModeUpdatingEventArgs *>(
                     &v161,
                     this);
  v120 = v118(v117, *v119, (char *)this + 160);
  if ( v120 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v120,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&v161);
  v121 = *(_QWORD *)v16;
  v122 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 400LL);
  v123 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextConversionModeUpdatingEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextConversionModeUpdatingEventArgs *>(
                     &hstringHeader,
                     this);
  v124 = v122(v121, *v123, (char *)this + 168);
  if ( v124 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v124,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&hstringHeader);
  v125 = *(_QWORD *)v16;
  v126 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 416LL);
  v127 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextOperationCompletedEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextOperationCompletedEventArgs *>(
                     &v161,
                     this);
  v128 = v126(v125, *v127, (char *)this + 176);
  if ( v128 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v128,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&v161);
  v129 = *(_QWORD *)v16;
  v130 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 432LL);
  v131 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextErrorReportedEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextErrorReportedEventArgs *>(
                     &hstringHeader,
                     this);
  v132 = v130(v129, *v131, (char *)this + 184);
  if ( v132 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v132,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&hstringHeader);
  v133 = *(_QWORD *)v16;
  v134 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 448LL);
  v135 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextUndoPendingKeyEventsAcknowledgedEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextUndoPendingKeyEventsAcknowledgedEventArgs *>(
                     &v161,
                     this);
  v136 = v134(v133, *v135, (char *)this + 192);
  if ( v136 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v136,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&v161);
  v137 = *(_QWORD *)v16;
  v138 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 464LL);
  v139 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextEnabledInputProfilesUpdatingEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextEnabledInputProfilesUpdatingEventArgs *>(
                     &hstringHeader,
                     this);
  v140 = v138(v137, *v139, (char *)this + 200);
  if ( v140 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v140,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&hstringHeader);
  v141 = *(_QWORD *)v16;
  v142 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 480LL);
  v143 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReregistrationRequestedEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextReregistrationRequestedEventArgs *>(
                     &v161,
                     this);
  v144 = v142(v141, *v143, (char *)this + 208);
  if ( v144 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v144,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&v161);
  v145 = *(_QWORD *)v16;
  v146 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 496LL);
  v147 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextRemoteIntegrationStatusChangedEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextRemoteIntegrationStatusChangedEventArgs *>(
                     &hstringHeader,
                     this);
  v148 = v146(v145, *v147, (char *)this + 216);
  if ( v148 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v148,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&hstringHeader);
  v149 = *(_QWORD *)v16;
  v150 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 512LL);
  v151 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextOccludingInputViewsChangedEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs *>(
                     &v161,
                     this);
  v152 = v150(v149, *v151, (char *)this + 224);
  if ( v152 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v152,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&v161);
  v153 = *(_QWORD *)v16;
  v154 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 528LL);
  v155 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextVersionReportingEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextVersionReportingEventArgs *>(
                     &hstringHeader,
                     this);
  v156 = v154(v153, *v155, (char *)this + 232);
  if ( v156 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v156,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&hstringHeader);
  v157 = *(_QWORD *)v16;
  v158 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)v16 + 544LL);
  v159 = (_QWORD *)Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextClientOptionsChangedEventArgs *>,RemoteTextAppIntegration_ToPdu,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextClientOptionsChangedEventArgs *>(
                     &v161,
                     this);
  v160 = v158(v157, *v159, (char *)this + 240);
  if ( v160 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v160,
      (int)v161);
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextTextAndSelectionUpdatingEventArgs *>>(&v161);
  wil::com_ptr_t<IMessageSessionPrivate,wil::err_exception_policy>::~com_ptr_t<IMessageSessionPrivate,wil::err_exception_policy>(&v162);
}

```

## disassembly

```asm
0x180045f84  push    rbp
0x180045f86  push    rbx
0x180045f87  push    rsi
0x180045f88  push    rdi
0x180045f89  push    r13
0x180045f8b  push    r14
0x180045f8d  push    r15
0x180045f8f  mov     rbp, rsp
0x180045f92  sub     rsp, 60h
0x180045f96  mov     rax, cs:__security_cookie
0x180045f9d  xor     rax, rsp
0x180045fa0  mov     [rbp+var_10], rax
0x180045fa4  mov     r15, r8
0x180045fa7  mov     rsi, rcx
0x180045faa  mov     [rbp+var_40], 0
0x180045fb2  lea     r9, [rbp+var_40]
0x180045fb6  mov     r8, rdx
0x180045fb9  lea     rdx, _GUID_099ffbc8_8bcb_41b5_b056_57e77021bf1b
0x180045fc0  xor     ecx, ecx
0x180045fc2  call    cs:__imp_RoGetAgileReference
0x180045fc8  mov     rcx, [rbp+38h]; this
0x180045fcc  test    eax, eax
0x180045fce  js      loc_1800470C7
0x180045fd4  mov     rax, [rbp+var_40]
0x180045fd8  xor     ecx, ecx
0x180045fda  mov     [rbp+var_40], rcx
0x180045fde  mov     rdx, [rsi+100h]
0x180045fe5  mov     [rsi+100h], rax
0x180045fec  test    rdx, rdx
0x180045fef  jz      short loc_180046004
0x180045ff1  mov     rax, [rdx]
0x180045ff4  mov     rcx, rdx
0x180045ff7  mov     rax, [rax+10h]
0x180045ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046000  mov     rcx, [rbp+var_40]
0x180046004  test    rcx, rcx
0x180046007  jz      short loc_180046016
0x180046009  mov     rax, [rcx]
0x18004600c  mov     rax, [rax+10h]
0x180046010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046015  nop
0x180046016  mov     [rbp+var_38], 0
0x18004601e  mov     [rbp+string], 0
0x180046026  lea     r9, [rbp+string]; string
0x18004602a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004602e  mov     edx, 38h ; '8'; length
0x180046033  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Text_Remote_RemoteTextAppIntegration@@3QBGB; "Windows.UI.Internal.Text.Remote.RemoteT"...
0x18004603a  call    cs:__imp_WindowsCreateStringReference
0x180046040  test    eax, eax
0x180046042  js      loc_1800470DC
0x180046048  lea     r8, [rbp+var_38]
0x18004604c  lea     rdx, _GUID_e43158d1_8fc2_4ddc_9b23_7dcd37aeec1f
0x180046053  mov     rcx, [rbp+string]
0x180046057  call    cs:__imp_RoGetActivationFactory
0x18004605d  mov     rcx, [rbp+38h]
0x180046061  test    eax, eax
0x180046063  js      loc_1800470E4
0x180046069  mov     [rbp+string], 0
0x180046071  mov     rbx, [rbp+var_38]
0x180046075  mov     rax, [rbx]
0x180046078  mov     rdi, [rax+30h]
0x18004607c  lea     r14, [rsi+108h]
0x180046083  mov     rcx, [r14]
0x180046086  mov     qword ptr [r14], 0
0x18004608d  test    rcx, rcx
0x180046090  jz      short loc_18004609F
0x180046092  mov     rax, [rcx]
0x180046095  mov     rax, [rax+10h]
0x180046099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004609e  nop
0x18004609f  movaps  xmm0, xmmword ptr [r15]
0x1800460a3  movdqa  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x1800460a8  mov     r8, r14
0x1800460ab  lea     rdx, [rbp+hstringHeader]
0x1800460af  mov     rcx, rbx
0x1800460b2  mov     rax, rdi
0x1800460b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460ba  mov     rdi, [r14]
0x1800460bd  mov     rax, [rdi]
0x1800460c0  mov     r15, [rax+40h]
0x1800460c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800460cb  mov     ecx, 20h ; ' '; unsigned __int64
0x1800460d0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800460d5  mov     rbx, rax
0x1800460d8  mov     r13d, 1
0x1800460de  test    rax, rax
0x1800460e1  jz      short loc_18004612F
0x1800460e3  lea     rax, ??_7?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextReconversionCandidatesUpdatingEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable'
0x1800460ea  mov     [rbx], rax
0x1800460ed  mov     [rbx+0Ch], r13d
0x1800460f1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextKeyTransitionedEventArgs@23456@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextKeyTransitionedEventArgs *>>::`vftable'
0x1800460f8  mov     [rbx], rax
0x1800460fb  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180046102  test    rcx, rcx
0x180046105  jz      short loc_180046114
0x180046107  mov     rax, [rcx]
0x18004610a  mov     rax, [rax+8]
0x18004610e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046113  nop
0x180046114  mov     [rbx+10h], rsi
0x180046118  lea     rax, ?OnKeyTransitioned@RemoteTextAppIntegration_ToPdu@@QEAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextKeyTransitionedEventArgs@34567@@Z; RemoteTextAppIntegration_ToPdu::OnKeyTransitioned(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyTransitionedEventArgs *)
0x18004611f  mov     [rbx+18h], rax
0x180046123  lea     rax, ??_7?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextKeyTransitionedEventArgs@23456@@Foundation@Windows@@V_lambda_f4a1295c0cfb20176d787f15aa255d3d_@@$0?0PEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextKeyTransitionedEventArgs@67893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextAppIntegration@23456@@Internal@Foundation@Windows@@U?$AggregateType@PEAVRemoteTextKeyTransitionedEventArgs@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextKeyTransitionedEventArgs@23456@@234@@Foundation@Windows@@EAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextKeyTransitionedEventArgs@56783@@Z@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextKeyTransitionedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyTransitionedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyTransitionedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextKeyTransitionedEventArgs *>,_lambda_f4a1295c0cfb20176d787f15aa255d3d_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextKeyTransitionedEventArgs *>::`vftable'
0x18004612a  mov     [rbx], rax
0x18004612d  jmp     short loc_180046131
0x18004612f  xor     ebx, ebx
0x180046131  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x180046135  mov     r8, rsi
0x180046138  mov     rdx, rbx
0x18004613b  mov     rcx, rdi
0x18004613e  mov     rax, r15
0x180046141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046146  mov     rcx, [rbp+38h]; this
0x18004614a  test    eax, eax
0x18004614c  js      loc_1800470F9
0x180046152  test    rbx, rbx
0x180046155  jz      short loc_180046167
0x180046157  mov     rax, [rbx]
0x18004615a  mov     rcx, rbx
0x18004615d  mov     rax, [rax+10h]
0x180046161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046166  nop
0x180046167  mov     rdi, [r14]
0x18004616a  mov     rax, [rdi]
0x18004616d  mov     r15, [rax+50h]
0x180046171  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180046178  mov     ecx, 20h ; ' '; unsigned __int64
0x18004617d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180046182  mov     rbx, rax
0x180046185  test    rax, rax
0x180046188  jz      short loc_1800461D6
0x18004618a  lea     rax, ??_7?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextReconversionCandidatesUpdatingEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable'
0x180046191  mov     [rbx], rax
0x180046194  mov     [rbx+0Ch], r13d
0x180046198  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextHostOperationAcknowledgedEventArgs@23456@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *>>::`vftable'
0x18004619f  mov     [rbx], rax
0x1800461a2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800461a9  test    rcx, rcx
0x1800461ac  jz      short loc_1800461BB
0x1800461ae  mov     rax, [rcx]
0x1800461b1  mov     rax, [rax+8]
0x1800461b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461ba  nop
0x1800461bb  mov     [rbx+10h], rsi
0x1800461bf  lea     rax, ?OnHostOperationAcknowledged@RemoteTextAppIntegration_ToPdu@@QEAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextHostOperationAcknowledgedEventArgs@34567@@Z; RemoteTextAppIntegration_ToPdu::OnHostOperationAcknowledged(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextHostOperationAcknowledgedEventArgs *)
0x1800461c6  mov     [rbx+18h], rax
0x1800461ca  lea     rax, ??_7?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextHostOperationAcknowledgedEventArgs@23456@@Foundation@Windows@@V_lambda_5a448bf274695e84378b4186f9e06f5d_@@$0?0PEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextHostOperationAcknowledgedEventArgs@67893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextAppIntegration@23456@@Internal@Foundation@Windows@@U?$AggregateType@PEAVRemoteTextHostOperationAcknowledgedEventArgs@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextHostOperationAcknowledgedEventArgs@23456@@234@@Foundation@Windows@@EAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextHostOperationAcknowledgedEventArgs@56783@@Z@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextHostOperationAcknowledgedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextHostOperationAcknowledgedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *>,_lambda_5a448bf274695e84378b4186f9e06f5d_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextHostOperationAcknowledgedEventArgs *>::`vftable'
0x1800461d1  mov     [rbx], rax
0x1800461d4  jmp     short loc_1800461D8
0x1800461d6  xor     ebx, ebx
0x1800461d8  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x1800461dc  lea     r8, [rsi+8]
0x1800461e0  mov     rdx, rbx
0x1800461e3  mov     rcx, rdi
0x1800461e6  mov     rax, r15
0x1800461e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461ee  mov     rcx, [rbp+38h]; this
0x1800461f2  test    eax, eax
0x1800461f4  js      loc_18004710E
0x1800461fa  test    rbx, rbx
0x1800461fd  jz      short loc_18004620F
0x1800461ff  mov     rax, [rbx]
0x180046202  mov     rcx, rbx
0x180046205  mov     rax, [rax+10h]
0x180046209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004620e  nop
0x18004620f  mov     rdi, [r14]
0x180046212  mov     rax, [rdi]
0x180046215  mov     r15, [rax+60h]
0x180046219  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180046220  mov     ecx, 20h ; ' '; unsigned __int64
0x180046225  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004622a  mov     rbx, rax
0x18004622d  test    rax, rax
0x180046230  jz      short loc_18004627E
0x180046232  lea     rax, ??_7?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextReconversionCandidatesUpdatingEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable'
0x180046239  mov     [rbx], rax
0x18004623c  mov     [rbx+0Ch], r13d
0x180046240  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextCharacterGeneratedEventArgs@23456@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextCharacterGeneratedEventArgs *>>::`vftable'
0x180046247  mov     [rbx], rax
0x18004624a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180046251  test    rcx, rcx
0x180046254  jz      short loc_180046263
0x180046256  mov     rax, [rcx]
0x180046259  mov     rax, [rax+8]
0x18004625d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046262  nop
0x180046263  mov     [rbx+10h], rsi
0x180046267  lea     rax, ?OnCharacterGenerated@RemoteTextAppIntegration_ToPdu@@QEAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextCharacterGeneratedEventArgs@34567@@Z; RemoteTextAppIntegration_ToPdu::OnCharacterGenerated(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCharacterGeneratedEventArgs *)
0x18004626e  mov     [rbx+18h], rax
0x180046272  lea     rax, ??_7?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextCharacterGeneratedEventArgs@23456@@Foundation@Windows@@V_lambda_97c7cd3ed3477c3de4a2abdfbd3a2a2f_@@$0?0PEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextCharacterGeneratedEventArgs@67893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextAppIntegration@23456@@Internal@Foundation@Windows@@U?$AggregateType@PEAVRemoteTextCharacterGeneratedEventArgs@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextCharacterGeneratedEventArgs@23456@@234@@Foundation@Windows@@EAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextCharacterGeneratedEventArgs@56783@@Z@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextCharacterGeneratedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextCharacterGeneratedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCharacterGeneratedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextCharacterGeneratedEventArgs *>,_lambda_97c7cd3ed3477c3de4a2abdfbd3a2a2f_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCharacterGeneratedEventArgs *>::`vftable'
0x180046279  mov     [rbx], rax
0x18004627c  jmp     short loc_180046280
0x18004627e  xor     ebx, ebx
0x180046280  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x180046284  lea     r8, [rsi+10h]
0x180046288  mov     rdx, rbx
0x18004628b  mov     rcx, rdi
0x18004628e  mov     rax, r15
0x180046291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046296  mov     rcx, [rbp+38h]; this
0x18004629a  test    eax, eax
0x18004629c  js      loc_180047123
0x1800462a2  test    rbx, rbx
0x1800462a5  jz      short loc_1800462B7
0x1800462a7  mov     rax, [rbx]
0x1800462aa  mov     rcx, rbx
0x1800462ad  mov     rax, [rax+10h]
0x1800462b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800462b6  nop
0x1800462b7  mov     rdi, [r14]
0x1800462ba  mov     rax, [rdi]
0x1800462bd  mov     r15, [rax+70h]
0x1800462c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800462c8  mov     ecx, 20h ; ' '; unsigned __int64
0x1800462cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800462d2  mov     rbx, rax
0x1800462d5  test    rax, rax
0x1800462d8  jz      short loc_180046326
0x1800462da  lea     rax, ??_7?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextReconversionCandidatesUpdatingEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable'
0x1800462e1  mov     [rbx], rax
0x1800462e4  mov     [rbx+0Ch], r13d
0x1800462e8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextFocusNavigatingEventArgs@23456@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusNavigatingEventArgs *>>::`vftable'
0x1800462ef  mov     [rbx], rax
0x1800462f2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800462f9  test    rcx, rcx
0x1800462fc  jz      short loc_18004630B
0x1800462fe  mov     rax, [rcx]
0x180046301  mov     rax, [rax+8]
0x180046305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004630a  nop
0x18004630b  mov     [rbx+10h], rsi
0x18004630f  lea     rax, ?OnFocusNavigating@RemoteTextAppIntegration_ToPdu@@QEAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextFocusNavigatingEventArgs@34567@@Z; RemoteTextAppIntegration_ToPdu::OnFocusNavigating(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusNavigatingEventArgs *)
0x180046316  mov     [rbx+18h], rax
0x18004631a  lea     rax, ??_7?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextFocusNavigatingEventArgs@23456@@Foundation@Windows@@V_lambda_bdf1a5dc2a72afac61c7dc63c6119ef1_@@$0?0PEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextFocusNavigatingEventArgs@67893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextAppIntegration@23456@@Internal@Foundation@Windows@@U?$AggregateType@PEAVRemoteTextFocusNavigatingEventArgs@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextFocusNavigatingEventArgs@23456@@234@@Foundation@Windows@@EAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextFocusNavigatingEventArgs@56783@@Z@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextFocusNavigatingEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusNavigatingEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusNavigatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusNavigatingEventArgs *>,_lambda_bdf1a5dc2a72afac61c7dc63c6119ef1_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusNavigatingEventArgs *>::`vftable'
0x180046321  mov     [rbx], rax
0x180046324  jmp     short loc_180046328
0x180046326  xor     ebx, ebx
0x180046328  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x18004632c  lea     r8, [rsi+18h]
0x180046330  mov     rdx, rbx
0x180046333  mov     rcx, rdi
0x180046336  mov     rax, r15
0x180046339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004633e  mov     rcx, [rbp+38h]; this
0x180046342  test    eax, eax
0x180046344  js      loc_180047138
0x18004634a  test    rbx, rbx
0x18004634d  jz      short loc_18004635F
0x18004634f  mov     rax, [rbx]
0x180046352  mov     rcx, rbx
0x180046355  mov     rax, [rax+10h]
0x180046359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004635e  nop
0x18004635f  mov     rdi, [r14]
0x180046362  mov     rax, [rdi]
0x180046365  mov     r15, [rax+80h]
0x18004636c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180046373  mov     ecx, 20h ; ' '; unsigned __int64
0x180046378  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004637d  mov     rbx, rax
0x180046380  test    rax, rax
0x180046383  jz      short loc_1800463D1
0x180046385  lea     rax, ??_7?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextReconversionCandidatesUpdatingEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable'
0x18004638c  mov     [rbx], rax
0x18004638f  mov     [rbx+0Ch], r13d
0x180046393  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextFocusDepartedEventArgs@23456@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusDepartedEventArgs *>>::`vftable'
0x18004639a  mov     [rbx], rax
0x18004639d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800463a4  test    rcx, rcx
0x1800463a7  jz      short loc_1800463B6
0x1800463a9  mov     rax, [rcx]
0x1800463ac  mov     rax, [rax+8]
0x1800463b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463b5  nop
0x1800463b6  mov     [rbx+10h], rsi
0x1800463ba  lea     rax, ?OnFocusDeparted@RemoteTextAppIntegration_ToPdu@@QEAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextFocusDepartedEventArgs@34567@@Z; RemoteTextAppIntegration_ToPdu::OnFocusDeparted(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusDepartedEventArgs *)
0x1800463c1  mov     [rbx+18h], rax
0x1800463c5  lea     rax, ??_7?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextFocusDepartedEventArgs@23456@@Foundation@Windows@@V_lambda_314f27c2251652a69f5008c7f508a96e_@@$0?0PEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextFocusDepartedEventArgs@67893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextAppIntegration@23456@@Internal@Foundation@Windows@@U?$AggregateType@PEAVRemoteTextFocusDepartedEventArgs@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextFocusDepartedEventArgs@23456@@234@@Foundation@Windows@@EAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@3@PEAUIRemoteTextFocusDepartedEventArgs@56783@@Z@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Remote::RemoteTextFocusDepartedEventArgs *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusDepartedEventArgs *>>::*)(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusDepartedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusDepartedEventArgs *>,_lambda_314f27c2251652a69f5008c7f508a96e_,-1,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextFocusDepartedEventArgs *>::`vftable'
0x1800463cc  mov     [rbx], rax
0x1800463cf  jmp     short loc_1800463D3
0x1800463d1  xor     ebx, ebx
0x1800463d3  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x1800463d7  lea     r8, [rsi+20h]
0x1800463db  mov     rdx, rbx
0x1800463de  mov     rcx, rdi
0x1800463e1  mov     rax, r15
0x1800463e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463e9  mov     rcx, [rbp+38h]; this
0x1800463ed  test    eax, eax
0x1800463ef  js      loc_18004714D
0x1800463f5  test    rbx, rbx
0x1800463f8  jz      short loc_18004640A
0x1800463fa  mov     rax, [rbx]
0x1800463fd  mov     rcx, rbx
0x180046400  mov     rax, [rax+10h]
0x180046404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046409  nop
0x18004640a  mov     rdi, [r14]
0x18004640d  mov     rax, [rdi]
  ... truncated ...
```
