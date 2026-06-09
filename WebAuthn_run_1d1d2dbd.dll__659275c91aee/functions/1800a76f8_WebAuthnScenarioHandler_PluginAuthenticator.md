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
void __fastcall WebAuthnScenarioHandler::PluginAuthenticator(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // rcx
  _QWORD *v5; // r15
  const WCHAR **v6; // r14
  const unsigned __int16 *v7; // rdi
  char v8; // r13
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // r13
  __int64 v12; // rax
  IID *v13; // rbx
  __int64 v14; // rax
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r13
  __int64 v20; // rax
  IID *v21; // rbx
  __int64 v22; // rax
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  const WCHAR *v28; // rdx
  unsigned int v29; // ebx
  char v30; // al
  __int64 v31; // r13
  unsigned int CredentialRequestForPlugins; // eax
  int v33; // r13d
  size_t v34; // rdi
  char *v35; // r12
  signed __int64 v36; // rcx
  char *v37; // rax
  size_t v38; // rbx
  IID *v39; // rax
  HLOCAL v40; // rcx
  unsigned int AssertionRequestForPlugins; // eax
  size_t v42; // rdi
  char *v43; // r12
  signed __int64 v44; // rcx
  char *v45; // rax
  size_t v46; // rbx
  bool v47; // zf
  unsigned __int64 v48; // rbx
  char *v49; // rdi
  char *v50; // rax
  size_t v51; // rbx
  const WCHAR *v52; // rdx
  const char *v53; // rdx
  const char *v54; // rax
  const char *v55; // rdx
  const char *v56; // rax
  __m128d v57; // xmm6
  __int64 v58; // rax
  DWORD dwHighDateTime; // edi
  DWORD dwLowDateTime; // ebx
  const WCHAR *v61; // rax
  _QWORD *v62; // rax
  int v63; // eax
  __int64 v64; // rax
  signed int v65; // eax
  __int64 v66; // rbx
  __int64 *v67; // rax
  int v68; // eax
  HLOCAL v69; // rcx
  int v70; // [rsp+28h] [rbp-E0h]
  int v71; // [rsp+28h] [rbp-E0h]
  char *v72; // [rsp+30h] [rbp-D8h]
  char *v73; // [rsp+30h] [rbp-D8h]
  char v74; // [rsp+48h] [rbp-C0h] BYREF
  char v75; // [rsp+49h] [rbp-BFh] BYREF
  IID *v76; // [rsp+50h] [rbp-B8h] BYREF
  void *v77; // [rsp+58h] [rbp-B0h] BYREF
  int v78; // [rsp+60h] [rbp-A8h] BYREF
  void *v79[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v80; // [rsp+78h] [rbp-90h]
  ULONG v81; // [rsp+80h] [rbp-88h] BYREF
  IID *v82; // [rsp+88h] [rbp-80h] BYREF
  __int64 v83; // [rsp+90h] [rbp-78h]
  HLOCAL v84; // [rsp+98h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-60h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v88[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v89; // [rsp+C8h] [rbp-40h] BYREF
  char v90; // [rsp+D8h] [rbp-30h]
  IID v91[2]; // [rsp+E8h] [rbp-20h] BYREF
  HLOCAL *p_hMem; // [rsp+108h] [rbp+0h] BYREF
  __int64 v93; // [rsp+110h] [rbp+8h] BYREF
  char v94; // [rsp+118h] [rbp+10h]
  _BYTE v95[56]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v96; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v97[56]; // [rsp+168h] [rbp+60h] BYREF
  _QWORD v98[2]; // [rsp+1A0h] [rbp+98h] BYREF
  char v99; // [rsp+1B0h] [rbp+A8h]
  _BYTE v100[32]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v101; // [rsp+1D8h] [rbp+D0h] BYREF
  __int128 v102; // [rsp+1E8h] [rbp+E0h]
  __int128 v103; // [rsp+1F8h] [rbp+F0h]
  __int128 v104; // [rsp+208h] [rbp+100h]
  _OWORD v105[2]; // [rsp+218h] [rbp+110h]
  _QWORD v106[4]; // [rsp+238h] [rbp+130h] BYREF
  _OWORD v107[2]; // [rsp+258h] [rbp+150h] BYREF
  _OWORD v108[2]; // [rsp+278h] [rbp+170h] BYREF
  __int128 v109; // [rsp+298h] [rbp+190h] BYREF
  __int64 v110; // [rsp+2A8h] [rbp+1A0h]
  __int64 v111; // [rsp+2B8h] [rbp+1B0h] BYREF
  int v112; // [rsp+2C0h] [rbp+1B8h]
  __int64 v113; // [rsp+2C4h] [rbp+1BCh]
  __int64 v114; // [rsp+2CCh] [rbp+1C4h]
  __int64 v115; // [rsp+2D4h] [rbp+1CCh]
  int v116; // [rsp+2DCh] [rbp+1D4h]
  __int64 v117; // [rsp+2E0h] [rbp+1D8h]
  char v118[32]; // [rsp+2E8h] [rbp+1E0h] BYREF
  char v119[32]; // [rsp+308h] [rbp+200h] BYREF
  char v120[32]; // [rsp+328h] [rbp+220h] BYREF
  __int128 v121; // [rsp+348h] [rbp+240h]
  __int64 v122; // [rsp+358h] [rbp+250h]
  __int64 v123; // [rsp+360h] [rbp+258h]
  __m128i si128; // [rsp+368h] [rbp+260h]
  int v125; // [rsp+378h] [rbp+270h]
  char v126; // [rsp+37Ch] [rbp+274h]
  __int16 v127; // [rsp+37Dh] [rbp+275h]
  char v128; // [rsp+37Fh] [rbp+277h]
  _BYTE v129[32]; // [rsp+388h] [rbp+280h] BYREF
  _QWORD v130[4]; // [rsp+3A8h] [rbp+2A0h] BYREF
  char v131[32]; // [rsp+3C8h] [rbp+2C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+450h] [rbp+348h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
  {
    v4 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
    if ( *v4 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v4,
        &unk_180187657,
        0);
  }
  else if ( (unsigned int)dword_1801AB110 > 4 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1801AB110,
      &unk_180187696,
      0);
  }
  v5 = (_QWORD *)(a1 + 64);
  if ( *(_BYTE *)(a1 + 152) != 7 )
    std::_Throw_bad_variant_access();
  std::wstring::wstring(v130, a1 + 64);
  v6 = (const WCHAR **)(a1 + 96);
  std::wstring::wstring(v131, a1 + 96);
  WebAuthnScenarioHandler::GetSupportedPluginAuthenticators(v88, a1);
  std::_Tree<std::_Tmap_traits<FidoCredProvHelper::Locations::PluginAuthenticator,PluginAuthenticatorState,std::less<FidoCredProvHelper::Locations::PluginAuthenticator>,std::allocator<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>,0>>::find(
    v88,
    &v76,
    v130);
  if ( v76 != (IID *)v88[0] && !LOBYTE(v76[6].Data1) )
  {
    std::wstring::wstring(v107, a1 + 64);
    std::wstring::wstring(v108, a1 + 96);
    std::vector<unsigned char>::vector<unsigned char>(&v109, *a2, *a2 + a2[1]);
    std::variant<Scenarios::Ngc,Scenarios::SyncedNgc,Scenarios::CtapHybridLinked,Scenarios::CtapHybridQr,Scenarios::CtapSecurityKey,Scenarios::LocationPicker,Scenarios::Error,Scenarios::CtapPluginAuthenticator,Scenarios::ConfirmationDialog,Scenarios::EnablementDialog>::operator=<Scenarios::EnablementDialog,0,0>(
      a1 + 64,
      v107);
    NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v107);
    goto LABEL_10;
  }
  *(_QWORD *)&v101 = off_18014A9F0;
  *((_QWORD *)&v104 + 1) = &v101;
  WebAuthNAuthenticatorTestWrapper::Apply(a1 + 24, &v101);
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  v7 = &word_18015030C;
  std::wstring::wstring(v118, &word_18015030C);
  std::wstring::wstring(v119, &word_18015030C);
  std::wstring::wstring(v120, &word_18015030C);
  v121 = 0;
  v122 = 0;
  v123 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v125 = 0;
  v126 = 0;
  v127 = 0;
  v128 = 0;
  PasskeyTelemetry::operator=(a1 + 384, &v111);
  PasskeyTelemetry::~PasskeyTelemetry((PasskeyTelemetry *)&v111);
  v83 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 312LL) + 56LL);
  v8 = **(_BYTE **)(v83 + 144);
  *(_OWORD *)v79 = 0;
  v80 = 0;
  v78 = 0;
  v77 = 0;
  v98[1] = &v77;
  v99 = 1;
  tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(v97);
  tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(v95);
  if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(a1 + 344) )
  {
    v9 = tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::watch_errors(
           a1 + 344,
           &v101);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::operator=(
      v97,
      v9);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(&v101);
  }
  else if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(a1 + 352) )
  {
    v10 = tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::watch_errors(
            a1 + 352,
            &v101);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator=(
      v95,
      v10);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(&v101);
  }
  else if ( v8 == 1 )
  {
    v11 = *(_QWORD *)(*(_QWORD *)a1 + 312LL);
    v12 = tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::start_and_watch_errors(
            a1 + 344,
            &v101);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::operator=(
      v97,
      v12);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(&v101);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(
      &v76,
      v98);
    v13 = v76;
    std::wstring::operator=(&v76[17], a1 + 96);
    std::wstring::operator=(&v13[19], a1 + 64);
    std::wstring::_Assign<unsigned short>(&v13[21], *(_QWORD *)(a1 + 48));
    BYTE2(v13[23].Data1) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl'::`2'::impl) )
    {
      v16 = &word_18015030C;
      if ( *(_QWORD *)(v11 + 72) )
        v16 = *(const unsigned __int16 **)(v11 + 72);
      v17 = std::wstring::wstring(&v101, v16);
      std::wstring::operator=(v13[23].Data4, v17);
      std::wstring::_Tidy_deallocate(&v101);
      if ( *(_QWORD *)(v11 + 80) )
        v7 = *(const unsigned __int16 **)(v11 + 80);
      v15 = v7;
    }
    else
    {
      v14 = std::wstring::wstring(&v101, *(_QWORD *)(v11 + 72));
      std::wstring::operator=(v13[23].Data4, v14);
      std::wstring::_Tidy_deallocate(&v101);
      v15 = *(const unsigned __int16 **)(v11 + 80);
    }
    v18 = std::wstring::wstring(&v101, v15);
    std::wstring::operator=(v13[25].Data4, v18);
    std::wstring::_Tidy_deallocate(&v101);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::close(&v76);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(&v76);
  }
  else if ( v8 == 2 )
  {
    v19 = *(_QWORD *)(*(_QWORD *)a1 + 312LL);
    v20 = tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::start_and_watch_errors(
            a1 + 352,
            &v101);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator=(
      v95,
      v20);
    tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(&v101);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(
      &v76,
      &v96);
    v21 = v76;
    std::wstring::operator=(&v76[17], a1 + 96);
    std::wstring::operator=(&v21[19], a1 + 64);
    std::wstring::_Assign<unsigned short>(&v21[21], *(_QWORD *)(a1 + 48));
    BYTE2(v21[23].Data1) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl'::`2'::impl) )
    {
      v24 = &word_18015030C;
      if ( *(_QWORD *)(v19 + 72) )
        v24 = *(const unsigned __int16 **)(v19 + 72);
      v25 = std::wstring::wstring(&v101, v24);
      std::wstring::operator=(v21[23].Data4, v25);
      std::wstring::_Tidy_deallocate(&v101);
      if ( *(_QWORD *)(v19 + 80) )
        v7 = *(const unsigned __int16 **)(v19 + 80);
      v23 = v7;
    }
    else
    {
      v22 = std::wstring::wstring(&v101, *(_QWORD *)(v19 + 72));
      std::wstring::operator=(v21[23].Data4, v22);
      std::wstring::_Tidy_deallocate(&v101);
      v23 = *(const unsigned __int16 **)(v19 + 80);
    }
    v26 = std::wstring::wstring(&v101, v23);
    std::wstring::operator=(v21[25].Data4, v26);
    std::wstring::_Tidy_deallocate(&v101);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::close(&v76);
    tip2::test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_data_control<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(&v76);
  }
  v27 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 312LL) + 64LL);
  v82 = (IID *)v27;
  v84 = 0;
  v89 = (unsigned __int64)&v84;
  v90 = 1;
  if ( *(_QWORD *)(a1 + 120) <= 7u )
    v28 = (const WCHAR *)(a1 + 96);
  else
    v28 = *v6;
  v29 = (unsigned int)CtapPluginGetAuthenticatorInfo(v27, v28, (char *)&v89 + 8) >> 31;
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v89);
  if ( (_BYTE)v29 )
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xD44,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
      (const char *)0x80004005LL,
      (int)"Failed to get plugin authenticator info",
      v72);
  v30 = *(_BYTE *)(a1 + 16);
  if ( v30 != 1 )
  {
    v31 = v83;
    if ( v30 )
      goto LABEL_68;
    CredentialRequestForPlugins = CtapCborEncodeMakeCredentialRequestForPlugins(
                                    *(struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST **)(a1 + 8),
                                    v70,
                                    (__int64)&v78,
                                    (__int64)&v77);
    if ( (int)HRESULT_FROM_CBOR_ERROR(CredentialRequestForPlugins) < 0 )
    {
      if ( v77 )
      {
        FidoFree(v77);
        v77 = 0;
      }
      goto LABEL_68;
    }
    v33 = v78;
    v34 = (unsigned int)(v78 - 1);
    v35 = (char *)v79[1];
    v36 = (char *)v79[1] - (char *)v79[0];
    if ( v34 < (char *)v79[1] - (char *)v79[0] )
    {
      v37 = (char *)v79[0] + (unsigned int)(v78 - 1);
LABEL_47:
      v79[1] = v37;
      goto LABEL_48;
    }
    if ( v34 > (char *)v79[1] - (char *)v79[0] )
    {
      if ( v34 <= v80 - (unsigned __int64)v79[0] )
      {
        v38 = v34 - v36;
        memset_0(v79[1], 0, v34 - v36);
        v37 = &v35[v38];
        goto LABEL_47;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v79, (unsigned int)(v78 - 1));
    }
LABEL_48:
    memcpy_0(v79[0], (char *)v77 + 1, v34);
    goto LABEL_67;
  }
  v39 = *(IID **)(a1 + 8);
  v76 = v39;
  v74 = 0;
  v91[0] = 0;
  if ( a2[1] )
  {
    v91[0] = v39[3];
    hMem = 0;
    p_hMem = &hMem;
    v93 = 0;
    v94 = 1;
    v89 = *(_OWORD *)a2;
    WebAuthNUI::CreateAllowListWithSingleCredential(&v89, &v93);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    v76[3] = *(IID *)hMem;
    v74 = 1;
    v40 = hMem;
    hMem = 0;
    if ( v40 )
      LocalFree(v40);
  }
  *(_QWORD *)&v101 = &v74;
  *((_QWORD *)&v101 + 1) = &v76;
  *(_QWORD *)&v102 = v91;
  BYTE8(v102) = 1;
  AssertionRequestForPlugins = CtapCborEncodeGetAssertionRequestForPlugins(
                                 (_DWORD)v76,
                                 (_DWORD)v84,
                                 *(_DWORD *)(v83 + 160),
                                 *(_QWORD *)(v83 + 168),
                                 v70,
                                 (__int64)&v78,
                                 (__int64)&v77);
  if ( (int)HRESULT_FROM_CBOR_ERROR(AssertionRequestForPlugins) < 0 )
  {
    v33 = 0;
    if ( v77 )
    {
      FidoFree(v77);
      v77 = 0;
    }
    goto LABEL_65;
  }
  v33 = v78;
  v42 = (unsigned int)(v78 - 1);
  v43 = (char *)v79[1];
  v44 = (char *)v79[1] - (char *)v79[0];
  if ( v42 < (char *)v79[1] - (char *)v79[0] )
  {
    v45 = (char *)v79[0] + (unsigned int)(v78 - 1);
LABEL_61:
    v79[1] = v45;
    goto LABEL_62;
  }
  if ( v42 > (char *)v79[1] - (char *)v79[0] )
  {
    if ( v42 <= v80 - (unsigned __int64)v79[0] )
    {
      v46 = v42 - v44;
      memset_0(v79[1], 0, v42 - v44);
      v45 = &v43[v46];
      goto LABEL_61;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v79, (unsigned int)(v78 - 1));
  }
LABEL_62:
  memcpy_0(v79[0], (char *)v77 + 1, v42);
LABEL_65:
  if ( v74 )
    v76[3] = v91[0];
LABEL_67:
  v47 = v33 == 0;
  v31 = v83;
  if ( !v47 )
    goto LABEL_76;
LABEL_68:
  v48 = (unsigned int)(*(_DWORD *)(v31 + 136) - 1);
  v49 = (char *)v79[1];
  if ( v48 < (char *)v79[1] - (char *)v79[0] )
  {
    v50 = (char *)v79[0] + (unsigned int)(*(_DWORD *)(v31 + 136) - 1);
LABEL_74:
    v79[1] = v50;
    goto LABEL_75;
  }
  if ( v48 > (char *)v79[1] - (char *)v79[0] )
  {
    if ( v48 <= v80 - (unsigned __int64)v79[0] )
    {
      v51 = v48 - ((char *)v79[1] - (char *)v79[0]);
      memset_0(v79[1], 0, v51);
      v50 = &v49[v51];
      goto LABEL_74;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
      v79,
      (unsigned int)(*(_DWORD *)(v31 + 136) - 1));
  }
LABEL_75:
  memcpy_0(v79[0], (const void *)(*(_QWORD *)(v31 + 144) + 1LL), (unsigned int)(*(_DWORD *)(v31 + 136) - 1));
LABEL_76:
  v81 = 0;
  pv = 0;
  *(_QWORD *)&v89 = &pv;
  BYTE8(v89) = 1;
  if ( *(_QWORD *)(a1 + 120) <= 7u )
    v52 = (const WCHAR *)(a1 + 96);
  else
    v52 = *v6;
  if ( (int)CtapPluginSignOperationRequest(
              (__int64)v82,
              v52,
              (UCHAR *)v79[0],
              LODWORD(v79[1]) - LODWORD(v79[0]),
              (UCHAR **)&pv,
              &v81) < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xDA3,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
      (const char *)0x80004005LL,
      (int)"Failed to sign the operation request",
      v73);
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v98[0] + 8LL) )
    {
      v54 = tip2::details::reason_string(
              (tip2::details *)"PluginAuthenticatorMakeCredentialScenarioTest::reason::failed_to_sign_request_buffer",
              v53);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v98[0] + 8LL, 2, v54);
    }
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v96 + 8) )
    {
      v56 = tip2::details::reason_string(
              (tip2::details *)"PluginAuthenticatorGetAssertionScenarioTest::reason::failed_to_sign_request_buffer",
              v55);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v96 + 8, 2, v56);
    }
  }
  std::vector<unsigned char>::vector<unsigned char>(v100, pv, (char *)pv + v81);
  v57 = 0;
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v98[0] + 8LL) )
  {
    v58 = v98[0];
LABEL_88:
    v57 = *(__m128d *)(v58 + 152);
    goto LABEL_89;
  }
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v96 + 8) )
  {
    v58 = v96;
    goto LABEL_88;
  }
LABEL_89:
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
  dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
  memset_0(&v101, 0, 0x58u);
  *((_QWORD *)&v101 + 1) = __PAIR64__(dwHighDateTime, dwLowDateTime);
  if ( *(_QWORD *)(a1 + 88) > 7u )
    v5 = (_QWORD *)*v5;
  *(_QWORD *)&v102 = v5;
  if ( *(_QWORD *)(a1 + 120) <= 7u )
    v61 = (const WCHAR *)(a1 + 96);
  else
    v61 = *v6;
  *((_QWORD *)&v102 + 1) = v61;
  *((_QWORD *)&v103 + 1) = *(_QWORD *)(a1 + 48);
  v82 = (IID *)a1;
  if ( *(char *)(a1 + 16) == -1 )
    std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_void__FidoCredProvHelper::VariantSerializer_std::back_insert_iterator_std::vector_enum_std::byte_std::allocator_enum_std::byte________::_2_::_lambda_1__std::variant_FidoCredProvHelper::Locations::Empty_FidoCredProvHelper::Locations::ThisPc_FidoCredProvHelper::Locations::QrCode_FidoCredProvHelper::Locations::SecurityKey_FidoCredProvHelper::Locations::LinkedDevice_FidoCredProvHelper::Locations::PluginAuthenticator_FidoCredProvHelper::Locations::SyncedAccount__const___1_();
  if ( *(_BYTE *)(a1 + 16) )
    WebAuthnScenarioHandler::PluginAuthenticator_::_2_::_lambda_6_::operator()(&v82, v106, *(_QWORD *)(a1 + 8));
  else
    std::wstring::wstring(v106, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL) + 16LL));
  v62 = v106;
  if ( v106[3] > 7u )
    v62 = (_QWORD *)v106[0];
  *(_QWORD *)&v103 = v62;
  *((void **)&v104 + 1) = v79[0];
  LODWORD(v105[0]) = LODWORD(v79[1]) - LODWORD(v79[0]);
  DWORD1(v105[0]) = **(unsigned __int8 **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 312LL) + 56LL) + 144LL);
  *(__m128d *)((char *)v105 + 8) = v57;
  v107[0] = v101;
  v107[1] = v102;
  v108[0] = v103;
  v108[1] = v104;
  v109 = v105[0];
  v110 = *(_OWORD *)&_mm_unpackhi_pd(v57, v57);
  v91[0] = *(IID *)(v31 + 16);
  v63 = CtapPluginInternal::PluginCacheUvContext(v91, (__int64)v107);
  if ( v63 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDEB,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
      (const char *)(unsigned int)v63,
      v71);
  v75 = 0;
  std::wstring::wstring(v129);
  if ( *(_QWORD *)(a1 + 120) > 7u )
    v6 = (const WCHAR **)*v6;
  if ( (int)CtapPluginInternal::GetAuthenticatorPackageFamilyName(
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 312LL) + 64LL),
              v6,
              v129) >= 0 )
  {
    v64 = std::wstring::wstring(&v101, v129);
    v65 = CtapSrvAllowAnotherOverlappingCaller(*(_QWORD *)(*(_QWORD *)a1 + 312LL), v64);
    if ( v65 > 0 )
      v65 = (unsigned __int16)v65 | 0x80070000;
    if ( v65 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDF4,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
        (const char *)(unsigned int)v65,
        v71);
    v75 = 1;
  }
  p_hMem = (HLOCAL *)&v75;
  v93 = a1;
  v94 = 1;
  v82 = v91;
  v66 = std::vector<unsigned char>::vector<unsigned char>(v91, v79);
  v67 = (__int64 *)std::vector<unsigned char>::vector<unsigned char>(&v101, v100);
  v68 = InvokePasskeyManager(a1, v67, v66, v130);
  if ( v68 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE03,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnscenario.cpp",
      (const char *)(unsigned int)v68,
      v71);
  *(_BYTE *)(a1 + 160) = 1;
  if ( v75 )
    CtapSrvStopAllowingOverlappingCaller(*(struct _CTAPDEVICE_COMMAND_INFO **)(*(_QWORD *)a1 + 312LL));
  std::wstring::_Tidy_deallocate(v129);
  std::wstring::_Tidy_deallocate(v106);
  std::vector<unsigned char>::_Tidy(v100);
  if ( pv )
    CoTaskMemFree(pv);
  v69 = v84;
  v84 = 0;
  if ( v69 )
    LocalFree(v69);
  tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>(v95);
  tip2::test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>::~test_watcher<tip2::details::merged_data<_tip_PluginAuthenticatorMakeCredentialScenarioTest,_tip_PluginAuthenticatorMakeCredentialScenarioTest>>(v97);
  if ( v77 )
    FidoFree(v77);
  std::vector<unsigned char>::_Tidy(v79);
LABEL_10:
  std::_Tree_val<std::_Tree_simple_types<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<FidoCredProvHelper::Locations::PluginAuthenticator const,PluginAuthenticatorState>,void *>>>(
    v88,
    v88);
  FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v130);
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
0x1800a7755  lea     rdx, unk_180187657
0x1800a775c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800a7761  jmp     short loc_1800A7784
0x1800a7763  mov     eax, cs:dword_1801AB110
0x1800a7769  cmp     eax, 4
0x1800a776c  jbe     short loc_1800A7784
0x1800a776e  xor     r8d, r8d
0x1800a7771  lea     rdx, unk_180187696
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
0x1800a78e8  lea     rdi, word_18015030C
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
