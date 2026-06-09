# CtapPluginSetAuthenticatorState

- ea: `0x180118b14`
- end: `0x180119c7a`
- name: `CtapPluginSetAuthenticatorState`
- size: `4454`
- prototype: ``
- caller_count: `2`
- callee_count: `48`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a0ddc`
- `0x1800db6b8`

## callees

- `0x1800021d8`
- `0x180003d08`
- `0x18001cd78`
- `0x18001df88`
- `0x18001ee7c`
- `0x1800205e4`
- `0x180021878`
- `0x1800222d8`
- `0x18002a2f0`
- `0x1800328b8`
- `0x180036da4`
- `0x180037f6c`
- `0x18003988c`
- `0x1800398d8`
- `0x18003a3c0`
- `0x18003a9e8`
- `0x18003ee60`
- `0x18004177c`
- `0x18004349c`
- `0x180043f2c`
- `0x1800467e0`
- `0x180046820`
- `0x18004f5b4`
- `0x180050e10`
- `0x180066b34`
- `0x18006f174`
- `0x18006f750`
- `0x180072974`
- `0x180087784`
- `0x180092a90`
- `0x1800933e8`
- `0x1800934c8`
- `0x180095b10`
- `0x18009e13c`
- `0x1800b2720`
- `0x1800b29f8`
- `0x1800b3104`
- `0x1800b5810`
- `0x1800b715c`
- `0x18010d430`
- `0x180118b14`
- `0x18011c42c`
- `0x18011e2fc`
- `0x18011e678`
- `0x18011f848`
- `0x18011f978`
- `0x180122144`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119754`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180119754`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180119444`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180119444`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180119233`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180119233`
- `ntdll!RtlPublishWnfStateData` at `0x180119bdf`
- `ntdll!RtlPublishWnfStateData` at `0x180119bdf`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180119bbd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180119bbd`

## string_xrefs

- `0x180118cf7`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118de7`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118e7b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118f64`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118ff7`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119123`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119248`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801193ce`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119510`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119639`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011982d`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119904`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801199f3`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119b43`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119bf7`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118d53`: `WebAuthNPluginSetAuthenticatorStateTest::reason::invalid_parameters`
- `0x180118ed0`: `WebAuthNPluginSetAuthenticatorStateTest::reason::invalid_parameters`
- `0x18011905f`: `WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_creation_failed`
- `0x18011908f`: `WebAuthNPluginSetAuthenticatorStateTest::reason::user_cancelled`
- `0x180118bf8`: `WebAuthNPluginSetAuthenticatorStateTest::reason::decoding_failed`
- `0x180119454`: `WebAuthNPluginSetAuthenticatorStateTest::reason::clsid_not_found`
- `0x1801195aa`: `WebAuthNPluginSetAuthenticatorStateTest::reason::plugin_name_retrieval_failed`
- `0x180119179`: `WebAuthNPluginSetAuthenticatorStateTest::reason::save_to_local_device_toggle_failed`
- `0x180119296`: `WebAuthNPluginSetAuthenticatorStateTest::reason::save_to_local_device_toggle_failed`
- `0x18011933f`: `WebAuthNPluginSetAuthenticatorStateTest::reason::registry_access_failed`
- `0x180119774`: `WebAuthNPluginSetAuthenticatorStateTest::reason::registry_access_failed`
- `0x180119962`: `WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_deletion_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CtapPluginSetAuthenticatorState(void *a1, __int128 *a2, __int64 a3, int a4, int a5)
{
  _DWORD *v7; // rcx
  const char *v8; // rdx
  unsigned int v9; // edi
  const char *v10; // rax
  signed int v11; // eax
  int v12; // r8d
  int v13; // r9d
  void *v14; // rdx
  int *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  const char *v18; // r9
  __int64 result; // rax
  BYTE *v20; // rdi
  char v21; // r12
  int v22; // r13d
  const char *v23; // rax
  const char *v24; // rdx
  char v25; // r8
  int v26; // r8d
  int v27; // r9d
  int *v28; // rcx
  void *v29; // rdx
  int v30; // r8d
  int v31; // r9d
  int *v32; // rcx
  void *v33; // rdx
  __int64 v34; // r13
  LPCWSTR *v35; // r12
  __int64 v36; // rdi
  const char *v37; // rax
  char v38; // r8
  int v39; // r8d
  int v40; // r9d
  int *v41; // rcx
  void *v42; // rdx
  int v43; // r8d
  int v44; // r9d
  int *v45; // rcx
  void *v46; // rdx
  void *v47; // r13
  const char *v48; // rdx
  int UvPubKey; // edi
  const char *v50; // rax
  const char *v51; // rdx
  const char *v52; // rax
  int v53; // r8d
  int v54; // r9d
  int *v55; // rcx
  void *v56; // rdx
  const char *v57; // rdx
  int UserRegPath; // edi
  const char *v59; // rax
  int v60; // r8d
  int v61; // r9d
  int *v62; // rcx
  void *v63; // rdx
  unsigned int v64; // eax
  const char *v65; // rdx
  int v66; // edi
  const char *v67; // rax
  int v68; // r8d
  int v69; // r9d
  int *v70; // rcx
  void *v71; // rdx
  const char *v72; // rdx
  int UserPluginAuthenticatorsRegKey; // edi
  const char *v74; // rax
  int v75; // r8d
  int v76; // r9d
  int *v77; // rcx
  void *v78; // rdx
  HKEY *v79; // rax
  const char *v80; // rdx
  int v81; // edi
  const char *v82; // rax
  int v83; // r8d
  int v84; // r9d
  int *v85; // rcx
  unsigned int v86; // eax
  void *v87; // rdx
  bool v88; // sf
  const char *v89; // rdx
  int PluginAuthenticatorName; // edi
  const char *v91; // rax
  int v92; // r8d
  int v93; // r9d
  int *v94; // rcx
  void *v95; // rdx
  _QWORD *v96; // rax
  const char *v97; // rdx
  int v98; // edi
  const char *v99; // rax
  __int64 v100; // r9
  int v101; // r8d
  int v102; // r9d
  int *v103; // rcx
  unsigned int v104; // eax
  void *v105; // rdx
  bool v106; // sf
  int v107; // eax
  BYTE *v108; // rdi
  int v109; // eax
  const char *v110; // rdx
  const char *v111; // rax
  int v112; // r8d
  int v113; // r9d
  int *v114; // rcx
  void *v115; // rdx
  char *v116; // rax
  signed __int64 v117; // r9
  int v118; // r8d
  int v119; // edx
  int v120; // eax
  __int64 v121; // rax
  const char *v122; // r9
  int v123; // eax
  const char *v124; // rdx
  const char *v125; // rax
  _DWORD *v126; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-288h]
  int lpDataa; // [rsp+20h] [rbp-288h]
  int lpDatab; // [rsp+20h] [rbp-288h]
  BYTE Data[8]; // [rsp+30h] [rbp-278h] BYREF
  void *v131; // [rsp+38h] [rbp-270h] BYREF
  HKEY v132; // [rsp+40h] [rbp-268h] BYREF
  HKEY v133; // [rsp+48h] [rbp-260h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-258h] BYREF
  BYTE *v135; // [rsp+58h] [rbp-250h] BYREF
  _QWORD *v136; // [rsp+60h] [rbp-248h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-240h] BYREF
  DWORD Type[4]; // [rsp+70h] [rbp-238h] BYREF
  _BYTE v139[56]; // [rsp+80h] [rbp-228h] BYREF
  __int64 v140; // [rsp+B8h] [rbp-1F0h]
  _BYTE v141[16]; // [rsp+C0h] [rbp-1E8h] BYREF
  __int128 v142; // [rsp+D0h] [rbp-1D8h] BYREF
  _BYTE v143[64]; // [rsp+E0h] [rbp-1C8h] BYREF
  char v144; // [rsp+120h] [rbp-188h]
  _BYTE v145[32]; // [rsp+130h] [rbp-178h] BYREF
  _QWORD v146[4]; // [rsp+150h] [rbp-158h] BYREF
  char v147; // [rsp+170h] [rbp-138h]
  _BYTE v148[96]; // [rsp+190h] [rbp-118h] BYREF
  _QWORD v149[4]; // [rsp+1F0h] [rbp-B8h] BYREF
  GUID pclsid; // [rsp+210h] [rbp-98h] BYREF
  _BYTE v151[32]; // [rsp+220h] [rbp-88h] BYREF
  _BYTE v152[32]; // [rsp+240h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  try
  {
    *(_QWORD *)Type = a3;
    v131 = a1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v7 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( *v7 > 4u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v7,
          &unk_18018CD5C,
          0);
    }
    else if ( (unsigned int)dword_1801AB110 > 4 )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1801AB110,
        &unk_18018CD8F,
        0);
    }
    hKey = 0;
    v142 = *a2;
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::open_helper(
      &hKey,
      &v142);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::ensure_data(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>((struct wil::details::IFailureCallback *)v139);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&hKey);
    v135 = 0;
    v9 = CtapCborDecodePluginAuthenticatorStateList(a5, a4, (unsigned int)&v135, 0, 0);
    if ( !v9 )
      goto LABEL_20;
    v10 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::decoding_failed",
            v8);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 4, v10);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      if ( **(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16) <= 3u )
        goto LABEL_18;
      v11 = CtapCborErrorToWin32Error(v9);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v14 = &unk_18018CC2A;
      LODWORD(v15) = v12;
    }
    else
    {
      if ( (unsigned int)dword_1801AB110 <= 3 )
        goto LABEL_18;
      v11 = CtapCborErrorToWin32Error(v9);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v14 = &unk_18018CCEA;
      v15 = &dword_1801AB110;
    }
    *(_DWORD *)Data = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (_DWORD)v15,
      (_DWORD)v14,
      v12,
      v13,
      (__int64)Data);
LABEL_18:
    v16 = CtapCborErrorToWin32Error(v9);
    if ( v16 )
    {
      v17 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x6AB,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)v16,
              lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
      return v17;
    }
LABEL_20:
    v20 = v135;
    if ( !v135 || (v21 = 0, !*((_QWORD *)v135 + 1)) )
      v21 = 1;
    v22 = *(_DWORD *)v135;
    v23 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::invalid_parameters",
            v8);
    if ( v25 )
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 2, v23);
    if ( v21 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
      {
        v28 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v28 > 3 )
        {
          v29 = &unk_18018CC94;
LABEL_31:
          *(_DWORD *)Data = -2147467261;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v28,
            (_DWORD)v29,
            v26,
            v27,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v29 = &unk_18018CB14;
        v28 = &dword_1801AB110;
        goto LABEL_31;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6BF,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80004003LL,
        lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
      return 2147500035LL;
    }
    if ( v22 != 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
      {
        v32 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v32 > 3 )
        {
          v33 = &unk_18018CABB;
LABEL_39:
          *(_DWORD *)Data = -2147024809;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v32,
            (_DWORD)v33,
            v30,
            v31,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v33 = &unk_18018CBC9;
        v32 = &dword_1801AB110;
        goto LABEL_39;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6CF,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80070057LL,
        lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
      return 2147942487LL;
    }
    v34 = **((_QWORD **)v20 + 1);
    v136 = (_QWORD *)v34;
    v35 = (LPCWSTR *)(v34 + 8);
    *(_QWORD *)&v142 = v34 + 8;
    v36 = *(_QWORD *)(v34 + 8);
    v37 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::invalid_parameters",
            v24);
    if ( v38 )
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 2, v37);
    if ( !v34 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
      {
        v41 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v41 > 3 )
        {
          v42 = &unk_18018CB72;
LABEL_49:
          *(_DWORD *)Data = -2147467261;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v41,
            (_DWORD)v42,
            v39,
            v40,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v42 = &unk_18018C9FD;
        v41 = &dword_1801AB110;
        goto LABEL_49;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E4,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80004003LL,
        lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
      return 2147500035LL;
    }
    if ( !v36 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
      {
        v45 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v45 > 3 )
        {
          v46 = &unk_18018C9A6;
LABEL_57:
          *(_DWORD *)Data = -2147467261;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v45,
            (_DWORD)v46,
            v43,
            v44,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v46 = &unk_18018CA5C;
        v45 = &dword_1801AB110;
        goto LABEL_57;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F4,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80004003LL,
        lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
      return 2147500035LL;
    }
    v135 = (BYTE *)(v34 + 40);
    v47 = v131;
    if ( *(_DWORD *)v135 != 1 )
      goto LABEL_93;
    lpData = 0;
    UvPubKey = CtapPluginGetUvPubKey(v131, *(_QWORD *)Type, *v35, 0);
    if ( UvPubKey < 0 )
    {
      v50 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_creation_failed",
              v48);
      if ( UvPubKey != -2146893770 )
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 7, v50);
      v52 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::user_cancelled",
              v51);
      if ( UvPubKey == -2146893770 )
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 13, v52);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
      {
        v55 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v55 > 3 )
        {
          v56 = &unk_18018C8A6;
LABEL_70:
          *(_DWORD *)Data = UvPubKey;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v55,
            (_DWORD)v56,
            v53,
            v54,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v56 = &unk_18018C949;
        v55 = &dword_1801AB110;
        goto LABEL_70;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x70E,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)UvPubKey,
          lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
      return (unsigned int)UvPubKey;
    }
    hKey = 0;
    UserRegPath = GetUserRegPath(v47, &hKey);
    if ( UserRegPath < 0 )
    {
      v59 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::save_to_local_device_toggle_failed",
              v57);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 10, v59);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
      {
        v62 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v62 > 3 )
        {
          v63 = &unk_18018C8FB;
LABEL_80:
          *(_DWORD *)Data = UserRegPath;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v62,
            (_DWORD)v63,
            v60,
            v61,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v63 = &unk_18018C75E;
        v62 = &dword_1801AB110;
        goto LABEL_80;
      }
LABEL_92:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_93:
      v133 = 0;
      UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(v47, &v133);
      if ( UserPluginAuthenticatorsRegKey < 0 )
      {
        v74 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::registry_access_failed",
                v72);
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 9, v74);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
        {
          v77 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v77 > 3 )
          {
            v78 = &unk_18018C65D;
LABEL_99:
            LODWORD(v131) = UserPluginAuthenticatorsRegKey;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v77,
              (_DWORD)v78,
              v75,
              v76,
              (__int64)&v131);
          }
        }
        else if ( (unsigned int)dword_1801AB110 > 3 )
        {
          v78 = &unk_18018C5F4;
          v77 = &dword_1801AB110;
          goto LABEL_99;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x75B,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
            lpData);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v133);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
        return (unsigned int)UserPluginAuthenticatorsRegKey;
      }
      v132 = 0;
      v79 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v132);
      v81 = RegOpenKeyExW(v133, *v35, 0, 0xF003Fu, v79);
      if ( v81 )
      {
        v82 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::clsid_not_found",
                v80);
        if ( v81 == 2 )
          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 5, v82);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
        {
          v85 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v85 > 3 )
          {
            if ( v81 > 0 )
              v86 = (unsigned __int16)v81 | 0x80070000;
            else
              v86 = v81;
            v87 = &unk_18018C712;
LABEL_117:
            LODWORD(v131) = v86;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v85,
              (_DWORD)v87,
              v83,
              v84,
              (__int64)&v131);
          }
        }
        else if ( (unsigned int)dword_1801AB110 > 3 )
        {
          if ( v81 > 0 )
            v86 = (unsigned __int16)v81 | 0x80070000;
          else
            v86 = v81;
          v87 = &unk_18018C6BE;
          v85 = &dword_1801AB110;
          goto LABEL_117;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        {
          v88 = v81 < 0;
          if ( v81 > 0 )
          {
            v81 = (unsigned __int16)v81 | 0x80070000;
            v88 = v81 < 0;
          }
          if ( v88 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x777,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)v81,
              lpDataa);
        }
        else if ( v81 > 0 )
        {
          v81 = (unsigned __int16)v81 | 0x80070000;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v132);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v133);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
        return (unsigned int)v81;
      }
      std::wstring::wstring(v149);
      PluginAuthenticatorName = CtapPluginInternal::GetPluginAuthenticatorName(v132, v149);
      if ( PluginAuthenticatorName < 0 )
      {
        v91 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::plugin_name_retrieval_failed",
                v89);
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 11, v91);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
        {
          v94 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v94 > 3 )
          {
            v95 = &unk_18018C4F8;
LABEL_132:
            LODWORD(v131) = PluginAuthenticatorName;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v94,
              (_DWORD)v95,
              v92,
              v93,
              (__int64)&v131);
          }
        }
        else if ( (unsigned int)dword_1801AB110 > 3 )
        {
          v95 = &unk_18018C496;
          v94 = &dword_1801AB110;
          goto LABEL_132;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x792,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)PluginAuthenticatorName,
            lpDataa);
        std::wstring::_Tidy_deallocate(v149);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v132);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v133);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
        return (unsigned int)PluginAuthenticatorName;
      }
      v96 = v149;
      if ( v149[3] > 7u )
        v96 = (_QWORD *)v149[0];
      *v136 = v96;
      std::wstring::wstring(v151, v149);
      std::wstring::wstring(v152, *v35);
      FidoCredProvHelper::Locations::PluginAuthenticator::PluginAuthenticator(v143, v151);
      v144 = 5;
      FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v151);
      v98 = RegSetValueExW(v132, L"State", 0, 4u, v135, 4u);
      if ( v98 )
      {
        v99 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::registry_access_failed",
                v97);
        tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v140 + 8, 9, v99, v100);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
        {
          v103 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v103 <= 3 )
            goto LABEL_151;
          if ( v98 > 0 )
            v104 = (unsigned __int16)v98 | 0x80070000;
          else
            v104 = v98;
          v105 = &unk_18018C5A7;
        }
        else
        {
          if ( (unsigned int)dword_1801AB110 <= 3 )
            goto LABEL_151;
          if ( v98 > 0 )
            v104 = (unsigned __int16)v98 | 0x80070000;
          else
            v104 = v98;
          v105 = &unk_18018C552;
          v103 = &dword_1801AB110;
        }
        LODWORD(v131) = v104;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v103,
          (_DWORD)v105,
          v101,
          v102,
          (__int64)&v131);
LABEL_151:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        {
          v106 = v98 < 0;
          if ( v98 > 0 )
          {
            v98 = (unsigned __int16)v98 | 0x80070000;
            v106 = v98 < 0;
          }
          if ( v106 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7B5,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)v98,
              lpDatab);
        }
        else if ( v98 > 0 )
        {
          v98 = (unsigned __int16)v98 | 0x80070000;
        }
LABEL_173:
        std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v143);
        std::wstring::_Tidy_deallocate(v149);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v132);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v133);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
        return (unsigned int)v98;
      }
      LODWORD(v131) = 1;
      v107 = wil::reg::set_value_nothrow<unsigned int>(v132, 0, L"StateToggled", &v131);
      if ( v107 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7BD,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)v107,
          lpDatab);
      CredentialAuthenticatorCache::ClearAuthenticator(v47, v143);
      v108 = v135;
      if ( !*(_DWORD *)v135 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
          v109 = CtapPluginDeleteUvKey(v47);
        else
          v109 = CtapPluginDeleteUvKeyOld(v47, *v35);
        v98 = v109;
        if ( v109 < 0 )
        {
          v111 = tip2::details::reason_string(
                   (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_deletion_failed",
                   v110);
          tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v140 + 8, 8, v111, (unsigned int)v98);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
          {
            v114 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
            if ( (unsigned int)*v114 <= 3 )
              goto LABEL_171;
            v115 = &unk_18018C394;
          }
          else
          {
            if ( (unsigned int)dword_1801AB110 <= 3 )
              goto LABEL_171;
            v115 = &unk_18018C337;
            v114 = &dword_1801AB110;
          }
          LODWORD(v131) = v98;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v114,
            (_DWORD)v115,
            v112,
            v113,
            (__int64)&v131);
LABEL_171:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7DD,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)v98,
              lpDatab);
          goto LABEL_173;
        }
        wil::impersonate_token(&v136, v47);
        WebAuthNSyncCheckEnableSaveLocalDevice();
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v136);
        v108 = v135;
      }
      try
      {
        GetPasskeyLocationVariantFromRegistry(v145, v47);
        if ( *(_DWORD *)v108 == 1 )
        {
          std::variant<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::operator=(
            v145,
            v143);
          v121 = FidoCredProvHelper::PasskeyLocationSelectionOutput::PasskeyLocationSelectionOutput(
                   (FidoCredProvHelper::PasskeyLocationSelectionOutput *)v148,
                   (const struct FidoCredProvHelper::PasskeyLocationSelectionOutput *)v145);
          SavePasskeyLocationVariantToRegistry(v47, v121);
        }
        else if ( v147 == (__int64)v144 )
        {
          if ( v147 != 5 )
            std::_Throw_bad_variant_access();
          v116 = (char *)v146;
          if ( v146[3] > 7u )
            v116 = (char *)v146[0];
          v117 = (char *)*v35 - v116;
          do
          {
            v118 = *(unsigned __int16 *)&v116[v117];
            v119 = *(unsigned __int16 *)v116 - v118;
            if ( v119 )
              break;
            v116 += 2;
          }
          while ( v118 );
          if ( !v119 )
          {
            v120 = ResetPasskeyLocationVariantInRegistry(v47);
            if ( v120 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x7F0,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)(unsigned int)v120,
                lpDatab);
          }
        }
        FidoCredProvHelper::PasskeyLocationSelectionOutput::~PasskeyLocationSelectionOutput((FidoCredProvHelper::PasskeyLocationSelectionOutput *)v145);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x7FB,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          v122);
        v125 = tip2::details::reason_string(
                 (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::failed_to_set_last_used",
                 v124);
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 12, v125);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
        {
          v126 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( *v126 > 4u )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              v126,
              &unk_18018C442,
              0);
        }
        else if ( (unsigned int)dword_1801AB110 > 4 )
        {
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1801AB110,
            &unk_18018C3E9,
            0);
        }
        v35 = (LPCWSTR *)v142;
      }
      pclsid = 0;
      CLSIDFromString(*v35, &pclsid);
      v123 = RtlPublishWnfStateData(WNF_WEBA_PLUGIN_STATE_CHANGED, 0, &pclsid, 16) | 0x10000000;
      if ( v123 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x80C,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)v123,
          0);
      std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v143);
      std::wstring::_Tidy_deallocate(v149);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v132);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v133);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v139);
      return 0;
    }
    *(_DWORD *)Data = 0;
    Type[0] = 4;
    cbData = 4;
    v64 = RegQueryValueExW(hKey, L"LocalToggleEnabledByUser", 0, Type, Data, &cbData);
    if ( v64 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x72E,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)v64,
        lpData);
    if ( *(_DWORD *)Data )
      goto LABEL_92;
    wil::impersonate_token(v141, v47);
    LODWORD(v131) = 0;
    v66 = wil::reg::set_value_nothrow<unsigned int>(hKey, 0, L"LocalToggleStatus", &v131);
    if ( v66 < 0 )
    {
      v67 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::save_to_local_device_toggle_failed",
              v65);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v140 + 8, 10, v67);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
      {
        v70 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v70 > 3 )
        {
          v71 = &unk_18018C831;
LABEL_90:
          LODWORD(v131) = v66;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v70,
            (_DWORD)v71,
            v68,
            v69,
            (__int64)&v131);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v71 = &unk_18018C7B4;
        v70 = &dword_1801AB110;
        goto LABEL_90;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v141);
    goto LABEL_92;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x810,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x180118b14  push    rbx
0x180118b16  push    rsi
0x180118b17  push    rdi
0x180118b18  push    r12
0x180118b1a  push    r13
0x180118b1c  push    r14
0x180118b1e  push    r15
0x180118b20  sub     rsp, 270h
0x180118b27  mov     rax, cs:__security_cookie
0x180118b2e  xor     rax, rsp
0x180118b31  mov     [rsp+2A8h+var_48], rax
0x180118b39  mov     rsi, r9
0x180118b3c  mov     qword ptr [rsp+2A8h+Type], r8
0x180118b41  mov     rdi, rdx
0x180118b44  mov     [rsp+2A8h+var_270], rcx
0x180118b49  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180118b50  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x180118b55  xor     ebx, ebx
0x180118b57  test    al, al
0x180118b59  jz      loc_180118C69
0x180118b5f  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x180118b64  mov     rcx, [rax+10h]
0x180118b68  mov     eax, [rcx]
0x180118b6a  cmp     eax, 4
0x180118b6d  jbe     short loc_180118B7E
0x180118b6f  xor     r8d, r8d
0x180118b72  lea     rdx, unk_18018CD5C
0x180118b79  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180118b7e  lea     r15, dword_1801AB110
0x180118b85  mov     [rsp+2A8h+hKey], rbx
0x180118b8a  movups  xmm0, xmmword ptr [rdi]
0x180118b8d  movdqu  [rsp+2A8h+var_1D8], xmm0
0x180118b96  lea     rdx, [rsp+2A8h+var_1D8]
0x180118b9e  lea     rcx, [rsp+2A8h+hKey]
0x180118ba3  call    ?open_helper@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@AEAA_NPEAU_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::open_helper(_GUID *)
0x180118ba8  lea     rcx, [rsp+2A8h+hKey]
0x180118bad  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::ensure_data(void)
0x180118bb2  mov     rdx, rax
0x180118bb5  lea     rcx, [rsp+2A8h+var_228]; struct wil::details::IFailureCallback *
0x180118bbd  call    ??0?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy> &)
0x180118bc2  lea     rcx, [rsp+2A8h+hKey]
0x180118bc7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(void)
0x180118bcc  nop
0x180118bcd  mov     [rsp+2A8h+var_250], rbx
0x180118bd2  mov     [rsp+2A8h+lpData], rbx; unsigned int
0x180118bd7  xor     r9d, r9d
0x180118bda  lea     r8, [rsp+2A8h+var_250]
0x180118bdf  mov     rdx, rsi
0x180118be2  mov     ecx, [rsp+2A8h+arg_20]
0x180118be9  call    CtapCborDecodePluginAuthenticatorStateList
0x180118bee  mov     edi, eax
0x180118bf0  test    eax, eax
0x180118bf2  jz      loc_180118D1E
0x180118bf8  lea     rcx, aWebauthnplugin_118; "WebAuthNPluginSetAuthenticatorStateTest"...
0x180118bff  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180118c04  mov     r8, rax
0x180118c07  mov     edx, 4
0x180118c0c  mov     rcx, [rsp+2A8h+var_1F0]
0x180118c14  add     rcx, 8
0x180118c18  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180118c1d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180118c24  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x180118c29  test    al, al
0x180118c2b  jz      short loc_180118C96
0x180118c2d  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x180118c32  mov     r8, [rax+10h]
0x180118c36  mov     eax, [r8]
0x180118c39  mov     esi, 3
0x180118c3e  cmp     eax, esi
0x180118c40  jbe     loc_180118CDB
0x180118c46  mov     ecx, edi
0x180118c48  call    CtapCborErrorToWin32Error
0x180118c4d  mov     r14d, 80070000h
0x180118c53  test    eax, eax
0x180118c55  jle     short loc_180118C5D
0x180118c57  movzx   eax, ax
0x180118c5a  or      eax, r14d
0x180118c5d  lea     rdx, unk_18018CC2A
0x180118c64  mov     rcx, r8
0x180118c67  jmp     short loc_180118CC6
0x180118c69  mov     eax, cs:dword_1801AB110
0x180118c6f  cmp     eax, 4
0x180118c72  jbe     loc_180118B7E
0x180118c78  xor     r8d, r8d
0x180118c7b  lea     rdx, unk_18018CD8F
0x180118c82  lea     r15, dword_1801AB110
0x180118c89  mov     rcx, r15
0x180118c8c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180118c91  jmp     loc_180118B85
0x180118c96  mov     eax, cs:dword_1801AB110
0x180118c9c  mov     esi, 3
0x180118ca1  cmp     eax, esi
0x180118ca3  jbe     short loc_180118CDB
0x180118ca5  mov     ecx, edi
0x180118ca7  call    CtapCborErrorToWin32Error
0x180118cac  mov     r14d, 80070000h
0x180118cb2  test    eax, eax
0x180118cb4  jle     short loc_180118CBC
0x180118cb6  movzx   eax, ax
0x180118cb9  or      eax, r14d
0x180118cbc  lea     rdx, unk_18018CCEA
0x180118cc3  mov     rcx, r15
0x180118cc6  mov     dword ptr [rsp+2A8h+Data], eax
0x180118cca  lea     rax, [rsp+2A8h+Data]
0x180118ccf  mov     [rsp+2A8h+lpData], rax
0x180118cd4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180118cd9  jmp     short loc_180118CE1
0x180118cdb  mov     r14d, 80070000h
0x180118ce1  mov     ecx, edi
0x180118ce3  call    CtapCborErrorToWin32Error
0x180118ce8  test    eax, eax
0x180118cea  jz      short loc_180118D29
0x180118cec  mov     rcx, [rsp+2A8h]; this
0x180118cf4  mov     r9d, eax; char *
0x180118cf7  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180118cfe  mov     edx, 6ABh; void *
0x180118d03  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180118d08  mov     ebx, eax
0x180118d0a  lea     rcx, [rsp+2A8h+var_228]
0x180118d12  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(void)
0x180118d17  mov     eax, ebx
0x180118d19  jmp     loc_180119C50
0x180118d1e  mov     esi, 3
0x180118d23  mov     r14d, 80070000h
0x180118d29  mov     rdi, [rsp+2A8h+var_250]
0x180118d2e  test    rdi, rdi
0x180118d31  jz      short loc_180118D3C
0x180118d33  cmp     [rdi+8], rbx
0x180118d37  mov     r12b, bl
0x180118d3a  jnz     short loc_180118D3F
0x180118d3c  mov     r12b, 1
0x180118d3f  mov     r13d, [rdi]
0x180118d42  test    r12b, r12b
0x180118d45  jnz     short loc_180118D50
0x180118d47  cmp     r13d, 1
0x180118d4b  mov     r8b, bl
0x180118d4e  jz      short loc_180118D53
0x180118d50  mov     r8b, 1
0x180118d53  lea     rcx, aWebauthnplugin_73; "WebAuthNPluginSetAuthenticatorStateTest"...
0x180118d5a  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180118d5f  test    r8b, r8b
0x180118d62  jz      short loc_180118D7D
0x180118d64  mov     edx, 2
0x180118d69  mov     rcx, [rsp+2A8h+var_1F0]
0x180118d71  add     rcx, 8
0x180118d75  mov     r8, rax
0x180118d78  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180118d7d  test    r12b, r12b
0x180118d80  jz      loc_180118E10
0x180118d86  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180118d8d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x180118d92  test    al, al
0x180118d94  jz      short loc_180118DAE
0x180118d96  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x180118d9b  mov     rcx, [rax+10h]
0x180118d9f  mov     eax, [rcx]
0x180118da1  cmp     eax, esi
0x180118da3  jbe     short loc_180118DD9
0x180118da5  lea     rdx, unk_18018CC94
0x180118dac  jmp     short loc_180118DC2
0x180118dae  mov     eax, cs:dword_1801AB110
0x180118db4  cmp     eax, esi
0x180118db6  jbe     short loc_180118DD9
0x180118db8  lea     rdx, unk_18018CB14
0x180118dbf  mov     rcx, r15
0x180118dc2  lea     rax, [rsp+2A8h+Data]
0x180118dc7  mov     [rsp+2A8h+lpData], rax; int
0x180118dcc  mov     dword ptr [rsp+2A8h+Data], 80004003h
0x180118dd4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180118dd9  mov     rcx, [rsp+2A8h]; this
0x180118de1  mov     r9d, 80004003h; char *
0x180118de7  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180118dee  mov     edx, 6BFh; void *
0x180118df3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118df8  nop
0x180118df9  lea     rcx, [rsp+2A8h+var_228]
0x180118e01  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(void)
0x180118e06  mov     eax, 80004003h
0x180118e0b  jmp     loc_180119C50
0x180118e10  cmp     r13d, 1
0x180118e14  jz      loc_180118EA4
0x180118e1a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180118e21  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x180118e26  test    al, al
0x180118e28  jz      short loc_180118E42
0x180118e2a  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x180118e2f  mov     rcx, [rax+10h]
0x180118e33  mov     eax, [rcx]
0x180118e35  cmp     eax, esi
0x180118e37  jbe     short loc_180118E6D
0x180118e39  lea     rdx, unk_18018CABB
0x180118e40  jmp     short loc_180118E56
0x180118e42  mov     eax, cs:dword_1801AB110
0x180118e48  cmp     eax, esi
0x180118e4a  jbe     short loc_180118E6D
0x180118e4c  lea     rdx, unk_18018CBC9
0x180118e53  mov     rcx, r15
0x180118e56  lea     rax, [rsp+2A8h+Data]
0x180118e5b  mov     [rsp+2A8h+lpData], rax; int
0x180118e60  mov     dword ptr [rsp+2A8h+Data], 80070057h
0x180118e68  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180118e6d  mov     rcx, [rsp+2A8h]; this
0x180118e75  mov     r9d, 80070057h; char *
0x180118e7b  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180118e82  mov     edx, 6CFh; void *
0x180118e87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118e8c  nop
0x180118e8d  lea     rcx, [rsp+2A8h+var_228]
0x180118e95  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(void)
0x180118e9a  mov     eax, 80070057h
0x180118e9f  jmp     loc_180119C50
0x180118ea4  mov     rax, [rdi+8]
0x180118ea8  mov     r13, [rax]
0x180118eab  mov     [rsp+2A8h+var_248], r13
0x180118eb0  lea     r12, [r13+8]
0x180118eb4  mov     qword ptr [rsp+2A8h+var_1D8], r12
0x180118ebc  mov     rdi, [r12]
0x180118ec0  test    r13, r13
0x180118ec3  jz      short loc_180118ECD
0x180118ec5  test    rdi, rdi
0x180118ec8  mov     r8b, bl
0x180118ecb  jnz     short loc_180118ED0
0x180118ecd  mov     r8b, 1
0x180118ed0  lea     rcx, aWebauthnplugin_73; "WebAuthNPluginSetAuthenticatorStateTest"...
0x180118ed7  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180118edc  test    r8b, r8b
0x180118edf  jz      short loc_180118EFA
0x180118ee1  mov     edx, 2
0x180118ee6  mov     rcx, [rsp+2A8h+var_1F0]
0x180118eee  add     rcx, 8
0x180118ef2  mov     r8, rax
0x180118ef5  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180118efa  test    r13, r13
0x180118efd  jnz     loc_180118F8D
0x180118f03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180118f0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x180118f0f  test    al, al
0x180118f11  jz      short loc_180118F2B
0x180118f13  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x180118f18  mov     rcx, [rax+10h]
0x180118f1c  mov     eax, [rcx]
0x180118f1e  cmp     eax, esi
0x180118f20  jbe     short loc_180118F56
0x180118f22  lea     rdx, unk_18018CB72
0x180118f29  jmp     short loc_180118F3F
0x180118f2b  mov     eax, cs:dword_1801AB110
0x180118f31  cmp     eax, esi
0x180118f33  jbe     short loc_180118F56
0x180118f35  lea     rdx, unk_18018C9FD
0x180118f3c  mov     rcx, r15
0x180118f3f  lea     rax, [rsp+2A8h+Data]
0x180118f44  mov     [rsp+2A8h+lpData], rax; int
0x180118f49  mov     dword ptr [rsp+2A8h+Data], 80004003h
0x180118f51  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180118f56  mov     rcx, [rsp+2A8h]; this
0x180118f5e  mov     r9d, 80004003h; char *
0x180118f64  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180118f6b  mov     edx, 6E4h; void *
0x180118f70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118f75  nop
0x180118f76  lea     rcx, [rsp+2A8h+var_228]
0x180118f7e  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(void)
0x180118f83  mov     eax, 80004003h
0x180118f88  jmp     loc_180119C50
0x180118f8d  test    rdi, rdi
0x180118f90  jnz     loc_180119020
0x180118f96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180118f9d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x180118fa2  test    al, al
0x180118fa4  jz      short loc_180118FBE
0x180118fa6  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x180118fab  mov     rcx, [rax+10h]
0x180118faf  mov     eax, [rcx]
0x180118fb1  cmp     eax, esi
0x180118fb3  jbe     short loc_180118FE9
0x180118fb5  lea     rdx, unk_18018C9A6
0x180118fbc  jmp     short loc_180118FD2
0x180118fbe  mov     eax, cs:dword_1801AB110
0x180118fc4  cmp     eax, esi
0x180118fc6  jbe     short loc_180118FE9
0x180118fc8  lea     rdx, unk_18018CA5C
0x180118fcf  mov     rcx, r15
0x180118fd2  lea     rax, [rsp+2A8h+Data]
0x180118fd7  mov     [rsp+2A8h+lpData], rax; int
0x180118fdc  mov     dword ptr [rsp+2A8h+Data], 80004003h
0x180118fe4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180118fe9  mov     rcx, [rsp+2A8h]; this
0x180118ff1  mov     r9d, 80004003h; char *
0x180118ff7  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180118ffe  mov     edx, 6F4h; void *
0x180119003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119008  nop
0x180119009  lea     rcx, [rsp+2A8h+var_228]
0x180119011  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(void)
0x180119016  mov     eax, 80004003h
0x18011901b  jmp     loc_180119C50
0x180119020  lea     rax, [r13+28h]
0x180119024  mov     [rsp+2A8h+var_250], rax
0x180119029  mov     r13, [rsp+2A8h+var_270]
0x18011902e  cmp     dword ptr [rax], 1
  ... truncated ...
```
