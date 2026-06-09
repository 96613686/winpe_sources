# WebAuthnScenarioHandler::PluginAuthenticator

- ea: `0x1800a76f8`
- end: `0x1800a84eb`
- name: `WebAuthnScenarioHandler::PluginAuthenticator`
- size: `3571`
- prototype: ``
- caller_count: `1`
- callee_count: `67`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009a410`

## callees

- `0x1800021d8`
- `0x180007f90`
- `0x18001687c`
- `0x18001c0d4`
- `0x18001df88`
- `0x1800205e4`
- `0x180021878`
- `0x180023bc8`
- `0x1800350b4`
- `0x180037f6c`
- `0x180038ee0`
- `0x18003a3c0`
- `0x18003a49c`
- `0x180041e70`
- `0x180043f2c`
- `0x180043f54`
- `0x180046820`
- `0x180048b70`
- `0x18004f5b4`
- `0x18005378c`
- `0x1800537a4`
- `0x180062fcc`
- `0x180063088`
- `0x180067fdc`
- `0x1800681f8`
- `0x18006b260`
- `0x18006f174`
- `0x18006f7b0`
- `0x180072974`
- `0x18007d358`
- `0x18007e064`
- `0x18007ed34`
- `0x180087784`
- `0x18008e458`
- `0x180096b84`
- `0x1800978bc`
- `0x18009c9f0`
- `0x18009ca7c`
- `0x18009cac0`
- `0x18009d5c0`
- `0x18009d5e4`
- `0x18009d608`
- `0x18009d630`
- `0x18009e01c`
- `0x18009e074`
- `0x18009e2c4`
- `0x18009fc18`
- `0x1800a0070`
- `0x1800a3170`
- `0x1800a3568`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7ece`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8490`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7ece`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8490`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a81b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a81b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a847c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a847c`

## string_xrefs

- `0x1800a7d51`: `onecore\ds\security\fido\webauthn\dll\webauthnscenario.cpp`
- `0x1800a80d8`: `onecore\ds\security\fido\webauthn\dll\webauthnscenario.cpp`
- `0x1800a8329`: `onecore\ds\security\fido\webauthn\dll\webauthnscenario.cpp`
- `0x1800a83b6`: `onecore\ds\security\fido\webauthn\dll\webauthnscenario.cpp`
- `0x1800a84d9`: `onecore\ds\security\fido\webauthn\dll\webauthnscenario.cpp`
- `0x1800a7d3f`: `Failed to get plugin authenticator info`
- `0x1800a80fd`: `PluginAuthenticatorMakeCredentialScenarioTest::reason::failed_to_sign_request_buffer`
- `0x1800a8132`: `PluginAuthenticatorGetAssertionScenarioTest::reason::failed_to_sign_request_buffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall WebAuthnScenarioHandler::PluginAuthenticator(__int64 a1, _QWORD *a2, __int64 a3)
{
  _DWORD *v5; // rcx
  _QWORD *v6; // r15
  const WCHAR **v7; // r14
  const unsigned __int16 *v8; // rdi
  char v9; // r13
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r13
  __int64 v13; // rax
  IID *v14; // rbx
  __int64 v15; // rax
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r13
  __int64 v21; // rax
  IID *v22; // rbx
  __int64 v23; // rax
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  const WCHAR *v29; // rdx
  unsigned int v30; // ebx
  char v31; // al
  __int64 v32; // r13
  unsigned int CredentialRequestForPlugins; // eax
  int v34; // r13d
  size_t v35; // rdi
  char *v36; // r12
  signed __int64 v37; // rcx
  char *v38; // rax
  size_t v39; // rbx
  IID *v40; // rax
  HLOCAL v41; // rcx
  unsigned int AssertionRequestForPlugins; // eax
  size_t v43; // rdi
  char *v44; // r12
  signed __int64 v45; // rcx
  char *v46; // rax
  size_t v47; // rbx
  bool v48; // zf
  unsigned __int64 v49; // rbx
  char *v50; // rdi
  char *v51; // rax
  size_t v52; // rbx
  const WCHAR *v53; // rdx
  const char *v54; // rdx
  const char *v55; // rax
  const char *v56; // rdx
  const char *v57; // rax
  __m128d v58; // xmm6
  __int64 v59; // rax
  DWORD dwHighDateTime; // edi
  DWORD dwLowDateTime; // ebx
  const WCHAR *v62; // rax
  _QWORD *v63; // rax
  int v64; // eax
  __int64 v65; // rax
  signed int v66; // eax
  __int64 v67; // rbx
  __int64 *v68; // rax
  int v69; // eax
  HLOCAL v70; // rcx
  int v71; // [rsp+28h] [rbp-E0h]
  int v72; // [rsp+28h] [rbp-E0h]
  char *v73; // [rsp+30h] [rbp-D8h]
  char *v74; // [rsp+30h] [rbp-D8h]
  char v75; // [rsp+48h] [rbp-C0h] BYREF
  char v76; // [rsp+49h] [rbp-BFh] BYREF
  IID *v77; // [rsp+50h] [rbp-B8h] BYREF
  void *v78; // [rsp+58h] [rbp-B0h] BYREF
  int v79; // [rsp+60h] [rbp-A8h] BYREF
  void *v80[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v81; // [rsp+78h] [rbp-90h]
  ULONG v82; // [rsp+80h] [rbp-88h] BYREF
  IID *v83; // [rsp+88h] [rbp-80h] BYREF
  __int64 v84; // [rsp+90h] [rbp-78h]
  HLOCAL v85; // [rsp+98h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-60h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-58h] BYREF
  void *v89[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v90; // [rsp+C8h] [rbp-40h] BYREF
  char v91; // [rsp+D8h] [rbp-30h]
  IID v92[2]; // [rsp+E8h] [rbp-20h] BYREF
  HLOCAL *p_hMem; // [rsp+108h] [rbp+0h] BYREF
  __int64 v94; // [rsp+110h] [rbp+8h] BYREF
  char v95; // [rsp+118h] [rbp+10h]
  _BYTE v96[56]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v97; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v98[56]; // [rsp+168h] [rbp+60h] BYREF
  _QWORD v99[2]; // [rsp+1A0h] [rbp+98h] BYREF
  char v100; // [rsp+1B0h] [rbp+A8h]
  _BYTE v101[32]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v102; // [rsp+1D8h] [rbp+D0h] BYREF
  __int128 v103; // [rsp+1E8h] [rbp+E0h]
  __int128 v104; // [rsp+1F8h] [rbp+F0h]
  __int128 v105; // [rsp+208h] [rbp+100h]
  _OWORD v106[2]; // [rsp+218h] [rbp+110h]
  _QWORD v107[4]; // [rsp+238h] [rbp+130h] BYREF
  _OWORD v108[2]; // [rsp+258h] [rbp+150h] BYREF
  _OWORD v109[2]; // [rsp+278h] [rbp+170h] BYREF
  __int128 v110; // [rsp+298h] [rbp+190h] BYREF
  __int64 v111; // [rsp+2A8h] [rbp+1A0h]
  __int64 v112; // [rsp+2B8h] [rbp+1B0h] BYREF
  int v113; // [rsp+2C0h] [rbp+1B8h]
  __int64 v114; // [rsp+2C4h] [rbp+1BCh]
  __int64 v115; // [rsp+2CCh] [rbp+1C4h]
  __int64 v116; // [rsp+2D4h] [rbp+1CCh]
  int v117; // [rsp+2DCh] [rbp+1D4h]
  __int64 v118; // [rsp+2E0h] [rbp+1D8h]
  char v119[32]; // [rsp+2E8h] [rbp+1E0h] BYREF
  char v120[32]; // [rsp+308h] [rbp+200h] BYREF
  char v121[32]; // [rsp+328h] [rbp+220h] BYREF
  __int128 v122; // [rsp+348h] [rbp+240h]
  __int64 v123; // [rsp+358h] [rbp+250h]
  __int64 v124; // [rsp+360h] [rbp+258h]
  __m128i si128; // [rsp+368h] [rbp+260h]
  int v126; // [rsp+378h] [rbp+270h]
  char v127; // [rsp+37Ch] [rbp+274h]
  __int16 v128; // [rsp+37Dh] [rbp+275h]
  char v129; // [rsp+37Fh] [rbp+277h]
  _BYTE v130[32]; // [rsp+388h] [rbp+280h] BYREF
  _QWORD v131[4]; // [rsp+3A8h] [rbp+2A0h] BYREF
  char v132[32]; // [rsp+3C8h] [rbp+2C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+450h] [rbp+348h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                          a2,
                          a3) )
  {
    v5 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
    if ( *v5 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v5,
        &byte_180187657,
        0);
  }
  else if ( (unsigned int)dword_1801AB110 > 4 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1801AB110,
      &word_180187696,
      0);
  }
  v6 = (_QWORD *)(a1 + 64);
  if ( *(_BYTE *)(a1 + 152) != 7 )
    std::_Throw_bad_variant_access();
  std::wstring::wstring(v131, a1 + 64);
  v7 = (const WCHAR **)(a1 + 96);
  std::wstring::wstring(v132, a1 + 96);
  WebAuthnScenarioHandler::GetSupportedPluginAuthenticators(v89, a1);
  std::_Tree<std::_Tmap_traits<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState,std::less<FidoCredProvHelper::Locations::PluginAuthenticator>,std::allocator<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>,0>>::find(
    v89,
    &v77,
    v131);
  if ( v77 != v89[0] && !LOBYTE(v77[6].Data1) )
  {
    std::wstring::wstring(v108, a1 + 64);
    std::wstring::wstring(v109, a1 + 96);
    std::vector<unsigned char>::vector<unsigned char>(&v110, *a2, *a2 + a2[1]);
    std::variant<Scenarios::Ngc,Scenarios::SyncedNgc,Scenarios::CtapHybridLinked,Scenarios::CtapHybridQr,Scenarios::CtapSecurityKey,Scenarios::LocationPicker,Scenarios::Error,Scenarios::CtapPluginAuthenticator,Scenarios::ConfirmationDialog,Scenarios::EnablementDialog>::operator=<Scenarios::EnablementDialog,0,0>(
      a1 + 64,
      (__int64)v108);
    NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v108);
    goto LABEL_10;
  }
  *(_QWORD *)&v102 = off_18014A9F0;
  *((_QWORD *)&v105 + 1) = &v102;
  WebAuthNAuthenticatorTestWrapper::Apply(a1 + 24, &v102);
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  v8 = &dword_18015030C;
  std::wstring::wstring(v119, &dword_18015030C);
  std::wstring::wstring(v120, &dword_18015030C);
  std::wstring::wstring(v121, &dword_18015030C);
  v122 = 0;
  v123 = 0;
  v124 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  PasskeyTelemetry::operator=(a1 + 384, &v112);
  PasskeyTelemetry::~PasskeyTelemetry((PasskeyTelemetry *)&v112);
  v84 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 312LL) + 56LL);
  v9 = **(_BYTE **)(v84 + 144);
  *(_OWORD *)v80 = 0;
  v81 = 0;
  v79 = 0;
  v78 = 0;
  v99[1] = &v78;
  v100 = 1;
  tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(v98);
  tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(v96);
  if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(a1 + 344) )
  {
    v10 = tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::watch_errors(
            a1 + 344,
            &v102);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::operator=(
      v98,
      v10);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(&v102);
  }
  else if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(a1 + 352) )
  {
    v11 = tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::watch_errors(
            a1 + 352,
            &v102);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator=(
      v96,
      v11);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(&v102);
  }
  else if ( v9 == 1 )
  {
    v12 = *(_QWORD *)(*(_QWORD *)a1 + 312LL);
    v13 = tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::start_and_watch_errors(
            a1 + 344,
            &v102);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::operator=(
      v98,
      v13);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(&v102);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(
      &v77,
      v99);
    v14 = v77;
    std::wstring::operator=(&v77[17], a1 + 96);
    std::wstring::operator=(&v14[19], a1 + 64);
    std::wstring::_Assign<unsigned short>(&v14[21], *(_QWORD *)(a1 + 48));
    BYTE2(v14[23].Data1) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl'::`2'::impl) )
    {
      v17 = &dword_18015030C;
      if ( *(_QWORD *)(v12 + 72) )
        v17 = *(const unsigned __int16 **)(v12 + 72);
      v18 = std::wstring::wstring(&v102, v17);
      std::wstring::operator=(v14[23].Data4, v18);
      std::wstring::_Tidy_deallocate(&v102);
      if ( *(_QWORD *)(v12 + 80) )
        v8 = *(const unsigned __int16 **)(v12 + 80);
      v16 = v8;
    }
    else
    {
      v15 = std::wstring::wstring(&v102, *(_QWORD *)(v12 + 72));
      std::wstring::operator=(v14[23].Data4, v15);
      std::wstring::_Tidy_deallocate(&v102);
      v16 = *(const unsigned __int16 **)(v12 + 80);
    }
    v19 = std::wstring::wstring(&v102, v16);
    std::wstring::operator=(v14[25].Data4, v19);
    std::wstring::_Tidy_deallocate(&v102);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::close(&v77);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(&v77);
  }
  else if ( v9 == 2 )
  {
    v20 = *(_QWORD *)(*(_QWORD *)a1 + 312LL);
    v21 = tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::start_and_watch_errors(
            a1 + 352,
            &v102);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator=(
      v96,
      v21);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(&v102);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(
      &v77,
      &v97);
    v22 = v77;
    std::wstring::operator=(&v77[17], a1 + 96);
    std::wstring::operator=(&v22[19], a1 + 64);
    std::wstring::_Assign<unsigned short>(&v22[21], *(_QWORD *)(a1 + 48));
    BYTE2(v22[23].Data1) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl'::`2'::impl) )
    {
      v25 = &dword_18015030C;
      if ( *(_QWORD *)(v20 + 72) )
        v25 = *(const unsigned __int16 **)(v20 + 72);
      v26 = std::wstring::wstring(&v102, v25);
      std::wstring::operator=(v22[23].Data4, v26);
      std::wstring::_Tidy_deallocate(&v102);
      if ( *(_QWORD *)(v20 + 80) )
        v8 = *(const unsigned __int16 **)(v20 + 80);
      v24 = v8;
    }
    else
    {
      v23 = std::wstring::wstring(&v102, *(_QWORD *)(v20 + 72));
      std::wstring::operator=(v22[23].Data4, v23);
      std::wstring::_Tidy_deallocate(&v102);
      v24 = *(const unsigned __int16 **)(v20 + 80);
    }
    v27 = std::wstring::wstring(&v102, v24);
    std::wstring::operator=(v22[25].Data4, v27);
    std::wstring::_Tidy_deallocate(&v102);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::close(&v77);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(&v77);
  }
  v28 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 312LL) + 64LL);
  v83 = (IID *)v28;
  v85 = 0;
  v90 = (unsigned __int64)&v85;
  v91 = 1;
  if ( *(_QWORD *)(a1 + 120) <= 7u )
    v29 = (const WCHAR *)(a1 + 96);
  else
    v29 = *v7;
  v30 = (unsigned int)CtapPluginGetAuthenticatorInfo(v28, v29, (char *)&v90 + 8) >> 31;
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v90);
  if ( (_BYTE)v30 )
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xD44,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
      (const char *)0x80004005LL,
      (int)"Failed to get plugin authenticator info",
      v73);
  v31 = *(_BYTE *)(a1 + 16);
  if ( v31 != 1 )
  {
    v32 = v84;
    if ( v31 )
      goto LABEL_68;
    CredentialRequestForPlugins = CtapCborEncodeMakeCredentialRequestForPlugins(
                                    *(struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST **)(a1 + 8),
                                    v71,
                                    (__int64)&v79,
                                    (__int64)&v78);
    if ( (int)HRESULT_FROM_CBOR_ERROR(CredentialRequestForPlugins) < 0 )
    {
      if ( v78 )
      {
        FidoFree(v78);
        v78 = 0;
      }
      goto LABEL_68;
    }
    v34 = v79;
    v35 = (unsigned int)(v79 - 1);
    v36 = (char *)v80[1];
    v37 = (char *)v80[1] - (char *)v80[0];
    if ( v35 < (char *)v80[1] - (char *)v80[0] )
    {
      v38 = (char *)v80[0] + (unsigned int)(v79 - 1);
LABEL_47:
      v80[1] = v38;
      goto LABEL_48;
    }
    if ( v35 > (char *)v80[1] - (char *)v80[0] )
    {
      if ( v35 <= v81 - (unsigned __int64)v80[0] )
      {
        v39 = v35 - v37;
        memset_0(v80[1], 0, v35 - v37);
        v38 = &v36[v39];
        goto LABEL_47;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v80, (unsigned int)(v79 - 1));
    }
LABEL_48:
    memcpy_0(v80[0], (char *)v78 + 1, v35);
    goto LABEL_67;
  }
  v40 = *(IID **)(a1 + 8);
  v77 = v40;
  v75 = 0;
  v92[0] = 0;
  if ( a2[1] )
  {
    v92[0] = v40[3];
    hMem = 0;
    p_hMem = &hMem;
    v94 = 0;
    v95 = 1;
    v90 = *(_OWORD *)a2;
    WebAuthNUI::CreateAllowListWithSingleCredential(&v90, &v94);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    v77[3] = *(IID *)hMem;
    v75 = 1;
    v41 = hMem;
    hMem = 0;
    if ( v41 )
      LocalFree(v41);
  }
  *(_QWORD *)&v102 = &v75;
  *((_QWORD *)&v102 + 1) = &v77;
  *(_QWORD *)&v103 = v92;
  BYTE8(v103) = 1;
  AssertionRequestForPlugins = CtapCborEncodeGetAssertionRequestForPlugins(
                                 (_DWORD)v77,
                                 (_DWORD)v85,
                                 *(_DWORD *)(v84 + 160),
                                 *(_QWORD *)(v84 + 168),
                                 v71,
                                 (__int64)&v79,
                                 (__int64)&v78);
  if ( (int)HRESULT_FROM_CBOR_ERROR(AssertionRequestForPlugins) < 0 )
  {
    v34 = 0;
    if ( v78 )
    {
      FidoFree(v78);
      v78 = 0;
    }
    goto LABEL_65;
  }
  v34 = v79;
  v43 = (unsigned int)(v79 - 1);
  v44 = (char *)v80[1];
  v45 = (char *)v80[1] - (char *)v80[0];
  if ( v43 < (char *)v80[1] - (char *)v80[0] )
  {
    v46 = (char *)v80[0] + (unsigned int)(v79 - 1);
LABEL_61:
    v80[1] = v46;
    goto LABEL_62;
  }
  if ( v43 > (char *)v80[1] - (char *)v80[0] )
  {
    if ( v43 <= v81 - (unsigned __int64)v80[0] )
    {
      v47 = v43 - v45;
      memset_0(v80[1], 0, v43 - v45);
      v46 = &v44[v47];
      goto LABEL_61;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v80, (unsigned int)(v79 - 1));
  }
LABEL_62:
  memcpy_0(v80[0], (char *)v78 + 1, v43);
LABEL_65:
  if ( v75 )
    v77[3] = v92[0];
LABEL_67:
  v48 = v34 == 0;
  v32 = v84;
  if ( !v48 )
    goto LABEL_76;
LABEL_68:
  v49 = (unsigned int)(*(_DWORD *)(v32 + 136) - 1);
  v50 = (char *)v80[1];
  if ( v49 < (char *)v80[1] - (char *)v80[0] )
  {
    v51 = (char *)v80[0] + (unsigned int)(*(_DWORD *)(v32 + 136) - 1);
LABEL_74:
    v80[1] = v51;
    goto LABEL_75;
  }
  if ( v49 > (char *)v80[1] - (char *)v80[0] )
  {
    if ( v49 <= v81 - (unsigned __int64)v80[0] )
    {
      v52 = v49 - ((char *)v80[1] - (char *)v80[0]);
      memset_0(v80[1], 0, v52);
      v51 = &v50[v52];
      goto LABEL_74;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
      v80,
      (unsigned int)(*(_DWORD *)(v32 + 136) - 1));
  }
LABEL_75:
  memcpy_0(v80[0], (const void *)(*(_QWORD *)(v32 + 144) + 1LL), (unsigned int)(*(_DWORD *)(v32 + 136) - 1));
LABEL_76:
  v82 = 0;
  pv = 0;
  *(_QWORD *)&v90 = &pv;
  BYTE8(v90) = 1;
  if ( *(_QWORD *)(a1 + 120) <= 7u )
    v53 = (const WCHAR *)(a1 + 96);
  else
    v53 = *v7;
  if ( (int)CtapPluginSignOperationRequest(
              (__int64)v83,
              v53,
              (UCHAR *)v80[0],
              LODWORD(v80[1]) - LODWORD(v80[0]),
              (UCHAR **)&pv,
              &v82) < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xDA3,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
      (const char *)0x80004005LL,
      (int)"Failed to sign the operation request",
      v74);
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v99[0] + 8LL) )
    {
      v55 = tip2::details::reason_string(
              (tip2::details *)"PluginAuthenticatorMakeCredentialScenarioTest::reason::failed_to_sign_request_buffer",
              v54);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v99[0] + 8LL, 2, v55);
    }
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v97 + 8) )
    {
      v57 = tip2::details::reason_string(
              (tip2::details *)"PluginAuthenticatorGetAssertionScenarioTest::reason::failed_to_sign_request_buffer",
              v56);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v97 + 8, 2, v57);
    }
  }
  std::vector<unsigned char>::vector<unsigned char>(v101, pv, (char *)pv + v82);
  v58 = 0;
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v99[0] + 8LL) )
  {
    v59 = v99[0];
LABEL_88:
    v58 = *(__m128d *)(v59 + 152);
    goto LABEL_89;
  }
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v97 + 8) )
  {
    v59 = v97;
    goto LABEL_88;
  }
LABEL_89:
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
  dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
  memset_0(&v102, 0, 0x58u);
  *((_QWORD *)&v102 + 1) = __PAIR64__(dwHighDateTime, dwLowDateTime);
  if ( *(_QWORD *)(a1 + 88) > 7u )
    v6 = (_QWORD *)*v6;
  *(_QWORD *)&v103 = v6;
  if ( *(_QWORD *)(a1 + 120) <= 7u )
    v62 = (const WCHAR *)(a1 + 96);
  else
    v62 = *v7;
  *((_QWORD *)&v103 + 1) = v62;
  *((_QWORD *)&v104 + 1) = *(_QWORD *)(a1 + 48);
  v83 = (IID *)a1;
  if ( *(char *)(a1 + 16) == -1 )
    std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_void__FidoCredProvHelper::VariantSerializer_std::back_insert_iterator_std::vector_enum_std::byte_std::allocator_enum_std::byte________::_2_::_lambda_1__std::variant_FidoCredProvHelper::Locations::Empty_FidoCredProvHelper::Locations::ThisPc_FidoCredProvHelper::Locations::QrCode_FidoCredProvHelper::Locations::SecurityKey_FidoCredProvHelper::Locations::LinkedDevice_FidoCredProvHelper::Locations::PluginAuthenticator_FidoCredProvHelper::Locations::SyncedAccount__const___1_();
  if ( *(_BYTE *)(a1 + 16) )
    WebAuthnScenarioHandler::PluginAuthenticator_::_2_::_lambda_6_::operator()(&v83, v107, *(_QWORD *)(a1 + 8));
  else
    std::wstring::wstring(v107, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL) + 16LL));
  v63 = v107;
  if ( v107[3] > 7u )
    v63 = (_QWORD *)v107[0];
  *(_QWORD *)&v104 = v63;
  *((void **)&v105 + 1) = v80[0];
  LODWORD(v106[0]) = LODWORD(v80[1]) - LODWORD(v80[0]);
  DWORD1(v106[0]) = **(unsigned __int8 **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 312LL) + 56LL) + 144LL);
  *(__m128d *)((char *)v106 + 8) = v58;
  v108[0] = v102;
  v108[1] = v103;
  v109[0] = v104;
  v109[1] = v105;
  v110 = v106[0];
  v111 = *(_OWORD *)&_mm_unpackhi_pd(v58, v58);
  v92[0] = *(IID *)(v32 + 16);
  v64 = CtapPluginInternal::PluginCacheUvContext(v92, (__int64)v108);
  if ( v64 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDEB,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
      (const char *)(unsigned int)v64,
      v72);
  v76 = 0;
  std::wstring::wstring(v130);
  if ( *(_QWORD *)(a1 + 120) > 7u )
    v7 = (const WCHAR **)*v7;
  if ( (int)CtapPluginInternal::GetAuthenticatorPackageFamilyName(
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 312LL) + 64LL),
              v7,
              v130) >= 0 )
  {
    v65 = std::wstring::wstring(&v102, v130);
    v66 = CtapSrvAllowAnotherOverlappingCaller(*(_QWORD *)(*(_QWORD *)a1 + 312LL), v65);
    if ( v66 > 0 )
      v66 = (unsigned __int16)v66 | 0x80070000;
    if ( v66 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDF4,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
        (const char *)(unsigned int)v66,
        v72);
    v76 = 1;
  }
  p_hMem = (HLOCAL *)&v76;
  v94 = a1;
  v95 = 1;
  v83 = v92;
  v67 = std::vector<unsigned char>::vector<unsigned char>(v92, v80);
  v68 = (__int64 *)std::vector<unsigned char>::vector<unsigned char>(&v102, v101);
  v69 = InvokePasskeyManager(a1, v68, v67, v131);
  if ( v69 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE03,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
      (const char *)(unsigned int)v69,
      v72);
  *(_BYTE *)(a1 + 160) = 1;
  if ( v76 )
    CtapSrvStopAllowingOverlappingCaller(*(struct _CTAPDEVICE_COMMAND_INFO **)(*(_QWORD *)a1 + 312LL));
  std::wstring::_Tidy_deallocate(v130);
  std::wstring::_Tidy_deallocate(v107);
  std::vector<unsigned char>::_Tidy(v101);
  if ( pv )
    CoTaskMemFree(pv);
  v70 = v85;
  v85 = 0;
  if ( v70 )
    LocalFree(v70);
  tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(v96);
  tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(v98);
  if ( v78 )
    FidoFree(v78);
  std::vector<unsigned char>::_Tidy(v80);
LABEL_10:
  std::_Tree_val<std::_Tree_simple_types<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>,void *>>>(
    v89,
    (__int64)v89);
  FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v131);
}

```

## disassembly

```asm
0x1800a76f8  mov     rax, rsp
0x1800a76fb  push    rbp
0x1800a76fc  push    rbx
0x1800a76fd  push    rsi
0x1800a76fe  push    rdi
0x1800a76ff  push    r12
0x1800a7701  push    r13
0x1800a7703  push    r14
0x1800a7705  push    r15
0x1800a7707  lea     rbp, [rax-348h]
0x1800a770e  sub     rsp, 408h
0x1800a7715  movaps  xmmword ptr [rax-58h], xmm6
0x1800a7719  mov     rax, cs:__security_cookie
0x1800a7720  xor     rax, rsp
0x1800a7723  mov     [rbp+340h+var_60], rax
0x1800a772a  mov     r12, rdx
0x1800a772d  mov     rsi, rcx
0x1800a7730  xor     ebx, ebx
0x1800a7732  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800a7739  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800a773e  test    al, al
0x1800a7740  jz      short loc_1800A7763
0x1800a7742  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800a7747  mov     rcx, [rax+10h]
0x1800a774b  mov     eax, [rcx]
0x1800a774d  cmp     eax, 4
0x1800a7750  jbe     short loc_1800A7784
0x1800a7752  xor     r8d, r8d
0x1800a7755  lea     rdx, byte_180187657
0x1800a775c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800a7761  jmp     short loc_1800A7784
0x1800a7763  mov     eax, cs:dword_1801AB110
0x1800a7769  cmp     eax, 4
0x1800a776c  jbe     short loc_1800A7784
0x1800a776e  xor     r8d, r8d
0x1800a7771  lea     rdx, word_180187696
0x1800a7778  lea     rcx, dword_1801AB110
0x1800a777f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800a7784  lea     r15, [rsi+40h]
0x1800a7788  cmp     byte ptr [r15+58h], 7
0x1800a778d  jnz     loc_1800A84D0
0x1800a7793  mov     rdx, r15
0x1800a7796  lea     rcx, [rbp+340h+var_A0]
0x1800a779d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a77a2  nop
0x1800a77a3  lea     r14, [r15+20h]
0x1800a77a7  mov     rdx, r14
0x1800a77aa  lea     rcx, [rbp+340h+var_80]
0x1800a77b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a77b6  nop
0x1800a77b7  mov     rdx, rsi
0x1800a77ba  lea     rcx, [rbp+340h+var_390]
0x1800a77be  call    WebAuthnScenarioHandler__GetSupportedPluginAuthenticators
0x1800a77c3  nop
0x1800a77c4  lea     r8, [rbp+340h+var_A0]
0x1800a77cb  lea     rdx, [rsp+440h+var_3F8]
0x1800a77d0  lea     rcx, [rbp+340h+var_390]
0x1800a77d4  call    ?find@?$_Tree@V?$_Tmap_traits@UPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@U?$less@UPluginAuthenticator@Locations@FidoCredProvHelper@@@std@@V?$allocator@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@@std@@@std@@@2@AEBUPluginAuthenticator@Locations@FidoCredProvHelper@@@Z; std::_Tree<std::_Tmap_traits<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState,std::less<FidoCredProvHelper::Locations::PluginAuthenticator>,std::allocator<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>,0>>::find(FidoCredProvHelper::Locations::PluginAuthenticator const &)
0x1800a77d9  mov     rax, [rsp+440h+var_3F8]
0x1800a77de  cmp     rax, [rbp+340h+var_390]
0x1800a77e2  jz      loc_1800A788B
0x1800a77e8  cmp     [rax+60h], bl
0x1800a77eb  jnz     loc_1800A788B
0x1800a77f1  mov     rdx, r15
0x1800a77f4  lea     rcx, [rbp+340h+var_1F0]
0x1800a77fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a7800  nop
0x1800a7801  mov     rdx, r14
0x1800a7804  lea     rcx, [rbp+340h+var_1D0]
0x1800a780b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a7810  nop
0x1800a7811  mov     rdx, [r12]
0x1800a7815  mov     r8, [r12+8]
0x1800a781a  add     r8, rdx
0x1800a781d  lea     rcx, [rbp+340h+var_1B0]
0x1800a7824  call    ??$?0U?$_Span_iterator@$$CBE@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@U?$_Span_iterator@$$CBE@1@0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(std::_Span_iterator<uchar const>,std::_Span_iterator<uchar const>,std::allocator<uchar> const &)
0x1800a7829  nop
0x1800a782a  lea     rdx, [rbp+340h+var_1F0]
0x1800a7831  mov     rcx, r15
0x1800a7834  call    ??$?4UEnablementDialog@Scenarios@@$0A@$0A@@?$variant@UNgc@Scenarios@@USyncedNgc@2@UCtapHybridLinked@2@UCtapHybridQr@2@UCtapSecurityKey@2@ULocationPicker@2@UError@2@UCtapPluginAuthenticator@2@UConfirmationDialog@2@UEnablementDialog@2@@std@@QEAAAEAV01@$$QEAUEnablementDialog@Scenarios@@@Z; std::variant<Scenarios::Ngc,Scenarios::SyncedNgc,Scenarios::CtapHybridLinked,Scenarios::CtapHybridQr,Scenarios::CtapSecurityKey,Scenarios::LocationPicker,Scenarios::Error,Scenarios::CtapPluginAuthenticator,Scenarios::ConfirmationDialog,Scenarios::EnablementDialog>::operator=<Scenarios::EnablementDialog,0,0>(Scenarios::EnablementDialog &&)
0x1800a7839  lea     rcx, [rbp+340h+var_1F0]; this
0x1800a7840  call    ??1CredUiAdditionalInfo@NgcUtils@@QEAA@XZ; NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo(void)
0x1800a7845  nop
0x1800a7846  lea     rdx, [rbp+340h+var_390]
0x1800a784a  lea     rcx, [rbp+340h+var_390]
0x1800a784e  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBUPluginAuthenticator@Locations@FidoCredProvHelper@@UPluginAuthenticatorState@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>,void *>>>(std::allocator<std::_Tree_node<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>,void *>> &)
0x1800a7853  nop
0x1800a7854  lea     rcx, [rbp+340h+var_A0]; this
0x1800a785b  call    ??1CreatedPasskeyInfo@FidoCredProvHelper@@QEAA@XZ; FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo(void)
0x1800a7860  mov     rcx, [rbp+340h+var_60]
0x1800a7867  xor     rcx, rsp; StackCookie
0x1800a786a  call    __security_check_cookie
0x1800a786f  movaps  xmm6, [rsp+440h+var_58+8]
0x1800a7877  add     rsp, 408h
0x1800a787e  pop     r15
0x1800a7880  pop     r14
0x1800a7882  pop     r13
0x1800a7884  pop     r12
0x1800a7886  pop     rdi
0x1800a7887  pop     rsi
0x1800a7888  pop     rbx
0x1800a7889  pop     rbp
0x1800a788a  retn
0x1800a788b  lea     rax, off_18014A9F0
0x1800a7892  mov     qword ptr [rbp+340h+var_270], rax
0x1800a7899  lea     rax, [rbp+340h+var_270]
0x1800a78a0  mov     [rbp+340h+var_238], rax
0x1800a78a7  lea     rcx, [rsi+18h]
0x1800a78ab  lea     rdx, [rbp+340h+var_270]
0x1800a78b2  call    ?Apply@WebAuthNAuthenticatorTestWrapper@@QEAAXV?$function@$$A6AXAEAUCommonWebAuthNTestParameters@@@Z@std@@@Z; WebAuthNAuthenticatorTestWrapper::Apply(std::function<void (CommonWebAuthNTestParameters &)>)
0x1800a78b7  mov     [rbp+340h+var_190], rbx
0x1800a78be  mov     [rbp+340h+var_188], ebx
0x1800a78c4  xor     eax, eax
0x1800a78c6  mov     [rbp+340h+var_184], rax
0x1800a78cd  mov     [rbp+340h+var_17C], rbx
0x1800a78d4  mov     [rbp+340h+var_174], rbx
0x1800a78db  mov     [rbp+340h+var_16C], ebx
0x1800a78e1  mov     [rbp+340h+var_168], rax
0x1800a78e8  lea     rdi, dword_18015030C
0x1800a78ef  mov     rdx, rdi
0x1800a78f2  lea     rcx, [rbp+340h+var_160]
0x1800a78f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a78fe  nop
0x1800a78ff  mov     rdx, rdi
0x1800a7902  lea     rcx, [rbp+340h+var_140]
0x1800a7909  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a790e  nop
0x1800a790f  mov     rdx, rdi
0x1800a7912  lea     rcx, [rbp+340h+var_120]
0x1800a7919  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a791e  xorps   xmm0, xmm0
0x1800a7921  movdqa  [rbp+340h+var_100], xmm0
0x1800a7929  mov     [rbp+340h+var_F0], rbx
0x1800a7930  mov     [rbp+340h+var_E8], rbx
0x1800a7937  movdqa  xmm0, cs:__xmm@00000003000000000000000000000000
0x1800a793f  movdqa  [rbp+340h+var_E0], xmm0
0x1800a7947  mov     [rbp+340h+var_D0], ebx
0x1800a794d  mov     [rbp+340h+var_CC], bl
0x1800a7953  xor     eax, eax
0x1800a7955  mov     [rbp+340h+var_CB], ax
0x1800a795c  mov     [rbp+340h+var_C9], al
0x1800a7962  lea     rcx, [rsi+180h]
0x1800a7969  lea     rdx, [rbp+340h+var_190]
0x1800a7970  call    ??4PasskeyTelemetry@@QEAAAEAU0@$$QEAU0@@Z; PasskeyTelemetry::operator=(PasskeyTelemetry &&)
0x1800a7975  lea     rcx, [rbp+340h+var_190]; this
0x1800a797c  call    ??1PasskeyTelemetry@@QEAA@XZ; PasskeyTelemetry::~PasskeyTelemetry(void)
0x1800a7981  mov     rax, [rsi]
0x1800a7984  mov     rcx, [rax+138h]
0x1800a798b  mov     rax, [rcx+38h]
0x1800a798f  mov     [rbp+340h+var_3B8], rax
0x1800a7993  mov     rax, [rax+90h]
0x1800a799a  mov     r13b, [rax]
0x1800a799d  xorps   xmm0, xmm0
0x1800a79a0  movdqu  xmmword ptr [rsp+440h+var_3E8+8], xmm0
0x1800a79a6  mov     [rsp+440h+var_3D0], rbx
0x1800a79ab  mov     dword ptr [rsp+440h+var_3E8], ebx
0x1800a79af  mov     [rsp+440h+var_3F0], rbx
0x1800a79b4  lea     rax, [rsp+440h+var_3F0]
0x1800a79b9  mov     [rbp+340h+var_2A0], rax
0x1800a79c0  mov     [rbp+340h+var_298], 1
0x1800a79c7  lea     rcx, [rbp+340h+var_2E0]
0x1800a79cb  call    ??0?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@QEAA@$$T@Z; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(std::nullptr_t)
0x1800a79d0  nop
0x1800a79d1  lea     rcx, [rbp+340h+var_320]
0x1800a79d5  call    ??0?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAA@$$T@Z; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(std::nullptr_t)
0x1800a79da  nop
0x1800a79db  lea     rbx, [rsi+158h]
0x1800a79e2  mov     rcx, rbx
0x1800a79e5  call    ??B?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(void)
0x1800a79ea  test    al, al
0x1800a79ec  jz      short loc_1800A7A1A
0x1800a79ee  lea     rdx, [rbp+340h+var_270]
0x1800a79f5  mov     rcx, rbx
0x1800a79f8  call    ?watch_errors@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::watch_errors(void)
0x1800a79fd  mov     rdx, rax
0x1800a7a00  lea     rcx, [rbp+340h+var_2E0]
0x1800a7a04  call    ??4?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@QEAAAEAV01@$$QEAV01@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::operator=(tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>> &&)
0x1800a7a09  lea     rcx, [rbp+340h+var_270]
0x1800a7a10  call    ??1?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(void)
0x1800a7a15  jmp     loc_1800A7CE3
0x1800a7a1a  lea     rbx, [rsi+160h]
0x1800a7a21  mov     rcx, rbx
0x1800a7a24  call    ??B?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(void)
0x1800a7a29  test    al, al
0x1800a7a2b  jz      short loc_1800A7A59
0x1800a7a2d  lea     rdx, [rbp+340h+var_270]
0x1800a7a34  mov     rcx, rbx
0x1800a7a37  call    ?watch_errors@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::watch_errors(void)
0x1800a7a3c  mov     rdx, rax
0x1800a7a3f  lea     rcx, [rbp+340h+var_320]
0x1800a7a43  call    ??4?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAAEAV01@$$QEAV01@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator=(tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>> &&)
0x1800a7a48  lea     rcx, [rbp+340h+var_270]
0x1800a7a4f  call    ??1?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(void)
0x1800a7a54  jmp     loc_1800A7CE3
0x1800a7a59  cmp     r13b, 1
0x1800a7a5d  jnz     loc_1800A7BA4
0x1800a7a63  mov     rax, [rsi]
0x1800a7a66  mov     r13, [rax+138h]
0x1800a7a6d  lea     rdx, [rbp+340h+var_270]
0x1800a7a74  lea     rcx, [rsi+158h]
0x1800a7a7b  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::start_and_watch_errors(void)
0x1800a7a80  mov     rdx, rax
0x1800a7a83  lea     rcx, [rbp+340h+var_2E0]
0x1800a7a87  call    ??4?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@QEAAAEAV01@$$QEAV01@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::operator=(tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>> &&)
0x1800a7a8c  lea     rcx, [rbp+340h+var_270]
0x1800a7a93  call    ??1?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(void)
0x1800a7a98  lea     rdx, [rbp+340h+var_2A8]
0x1800a7a9f  lea     rcx, [rsp+440h+var_3F8]
0x1800a7aa4  call    ??0?$test_data_control@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>,wil::err_returncode_policy> const &)
0x1800a7aa9  nop
0x1800a7aaa  mov     rbx, [rsp+440h+var_3F8]
0x1800a7aaf  lea     rcx, [rbx+110h]
0x1800a7ab6  mov     rdx, r14
0x1800a7ab9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800a7abe  lea     rcx, [rbx+130h]
0x1800a7ac5  mov     rdx, r15
0x1800a7ac8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800a7acd  lea     rcx, [rbx+150h]
0x1800a7ad4  mov     r8, [rsi+38h]
0x1800a7ad8  mov     rdx, [rsi+30h]
0x1800a7adc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a7ae1  mov     byte ptr [rbx+172h], 0
0x1800a7ae8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl(void)'::`2'::impl
0x1800a7aef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(void)
0x1800a7af4  lea     rcx, [rbp+340h+var_270]
0x1800a7afb  test    al, al
0x1800a7afd  jnz     short loc_1800A7B29
0x1800a7aff  mov     rdx, [r13+48h]
0x1800a7b03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a7b08  lea     rcx, [rbx+178h]
0x1800a7b0f  mov     rdx, rax
0x1800a7b12  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a7b17  lea     rcx, [rbp+340h+var_270]
0x1800a7b1e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7b23  mov     rdx, [r13+50h]
0x1800a7b27  jmp     short loc_1800A7B63
0x1800a7b29  mov     rdx, rdi
0x1800a7b2c  cmp     qword ptr [r13+48h], 0
0x1800a7b31  cmovnz  rdx, [r13+48h]
0x1800a7b36  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a7b3b  lea     rcx, [rbx+178h]
0x1800a7b42  mov     rdx, rax
0x1800a7b45  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a7b4a  lea     rcx, [rbp+340h+var_270]
0x1800a7b51  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7b56  cmp     qword ptr [r13+50h], 0
0x1800a7b5b  cmovnz  rdi, [r13+50h]
0x1800a7b60  mov     rdx, rdi
0x1800a7b63  lea     rcx, [rbp+340h+var_270]
0x1800a7b6a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a7b6f  mov     rdx, rax
0x1800a7b72  lea     rcx, [rbx+198h]
0x1800a7b79  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a7b7e  lea     rcx, [rbp+340h+var_270]
0x1800a7b85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7b8a  lea     rcx, [rsp+440h+var_3F8]
0x1800a7b8f  call    ?close@?$test_data_control@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::close(void)
0x1800a7b94  nop
0x1800a7b95  lea     rcx, [rsp+440h+var_3F8]
0x1800a7b9a  call    ??1?$test_data_control@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(void)
0x1800a7b9f  jmp     loc_1800A7CE3
0x1800a7ba4  cmp     r13b, 2
0x1800a7ba8  jnz     loc_1800A7CE3
0x1800a7bae  mov     rax, [rsi]
0x1800a7bb1  mov     r13, [rax+138h]
0x1800a7bb8  lea     rdx, [rbp+340h+var_270]
0x1800a7bbf  mov     rcx, rbx
0x1800a7bc2  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::start_and_watch_errors(void)
0x1800a7bc7  mov     rdx, rax
0x1800a7bca  lea     rcx, [rbp+340h+var_320]
0x1800a7bce  call    ??4?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAAEAV01@$$QEAV01@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator=(tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>> &&)
0x1800a7bd3  lea     rcx, [rbp+340h+var_270]
0x1800a7bda  call    ??1?$test_watcher@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(void)
0x1800a7bdf  lea     rdx, [rbp+340h+var_2E8]
0x1800a7be3  lea     rcx, [rsp+440h+var_3F8]
0x1800a7be8  call    ??0?$test_data_control@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_PluginAuthenticatorMakeCredentialScenarioTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>,wil::err_returncode_policy> const &)
0x1800a7bed  nop
0x1800a7bee  mov     rbx, [rsp+440h+var_3F8]
0x1800a7bf3  lea     rcx, [rbx+110h]
0x1800a7bfa  mov     rdx, r14
0x1800a7bfd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800a7c02  lea     rcx, [rbx+130h]
0x1800a7c09  mov     rdx, r15
0x1800a7c0c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800a7c11  lea     rcx, [rbx+150h]
0x1800a7c18  mov     r8, [rsi+38h]
0x1800a7c1c  mov     rdx, [rsi+30h]
0x1800a7c20  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a7c25  mov     byte ptr [rbx+172h], 0
0x1800a7c2c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl(void)'::`2'::impl
0x1800a7c33  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(void)
0x1800a7c38  lea     rcx, [rbp+340h+var_270]
0x1800a7c3f  test    al, al
0x1800a7c41  jnz     short loc_1800A7C6D
0x1800a7c43  mov     rdx, [r13+48h]
0x1800a7c47  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a7c4c  lea     rcx, [rbx+178h]
0x1800a7c53  mov     rdx, rax
0x1800a7c56  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a7c5b  lea     rcx, [rbp+340h+var_270]
  ... truncated ...
```
