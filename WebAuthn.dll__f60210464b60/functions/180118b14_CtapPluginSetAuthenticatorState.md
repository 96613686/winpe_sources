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
  __int64 v11; // rdx
  __int64 v12; // r8
  signed int v13; // eax
  int v14; // r8d
  int v15; // r9d
  __int16 *v16; // rdx
  int *v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // ebx
  const char *v20; // r9
  __int64 result; // rax
  BYTE *v22; // rdi
  char v23; // r12
  int v24; // r13d
  const char *v25; // rax
  const char *v26; // rdx
  __int64 v27; // r8
  int v28; // r8d
  int v29; // r9d
  int *v30; // rcx
  int *v31; // rdx
  int v32; // r8d
  int v33; // r9d
  int *v34; // rcx
  char *v35; // rdx
  __int64 v36; // r13
  LPCWSTR *v37; // r12
  __int64 v38; // rdi
  const char *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  int v42; // r8d
  int v43; // r9d
  int *v44; // rcx
  __int16 *v45; // rdx
  int v46; // r8d
  int v47; // r9d
  int *v48; // rcx
  __int16 *v49; // rdx
  void *v50; // r13
  const char *v51; // rdx
  int UvPubKey; // edi
  const char *v53; // rax
  const char *v54; // rdx
  const char *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  int v58; // r8d
  int v59; // r9d
  int *v60; // rcx
  __int16 *v61; // rdx
  const char *v62; // rdx
  int UserRegPath; // edi
  const char *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r8
  int v67; // r8d
  int v68; // r9d
  int *v69; // rcx
  __int16 *v70; // rdx
  unsigned int v71; // eax
  const char *v72; // rdx
  int v73; // edi
  const char *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // r8
  int v77; // r8d
  int v78; // r9d
  int *v79; // rcx
  int *v80; // rdx
  const char *v81; // rdx
  int UserPluginAuthenticatorsRegKey; // edi
  const char *v83; // rax
  __int64 v84; // rdx
  __int64 v85; // r8
  int v86; // r8d
  int v87; // r9d
  int *v88; // rcx
  int *v89; // rdx
  HKEY *v90; // rax
  const char *v91; // rdx
  int v92; // edi
  const char *v93; // rax
  __int64 v94; // rdx
  __int64 v95; // r8
  int v96; // r8d
  int v97; // r9d
  int *v98; // rcx
  unsigned int v99; // eax
  __int16 *v100; // rdx
  bool v101; // sf
  const char *v102; // rdx
  int PluginAuthenticatorName; // edi
  const char *v104; // rax
  __int64 v105; // rdx
  __int64 v106; // r8
  int v107; // r8d
  int v108; // r9d
  int *v109; // rcx
  __int16 *v110; // rdx
  _QWORD *v111; // rax
  const char *v112; // rdx
  int v113; // edi
  const char *v114; // rax
  __int64 v115; // r9
  __int64 v116; // rdx
  __int64 v117; // r8
  int v118; // r8d
  int v119; // r9d
  int *v120; // rcx
  unsigned int v121; // eax
  __int16 *v122; // rdx
  bool v123; // sf
  int v124; // eax
  BYTE *v125; // rdi
  int v126; // eax
  const char *v127; // rdx
  const char *v128; // rax
  __int64 v129; // rdx
  __int64 v130; // r8
  int v131; // r8d
  int v132; // r9d
  int *v133; // rcx
  int *v134; // rdx
  char *v135; // rax
  signed __int64 v136; // r9
  int v137; // r8d
  int v138; // edx
  int v139; // eax
  __int64 v140; // rax
  const char *v141; // r9
  int v142; // eax
  const char *v143; // rdx
  const char *v144; // rax
  __int64 v145; // rdx
  __int64 v146; // r8
  _DWORD *v147; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-288h]
  int lpDataa; // [rsp+20h] [rbp-288h]
  int lpDatab; // [rsp+20h] [rbp-288h]
  BYTE Data[8]; // [rsp+30h] [rbp-278h] BYREF
  void *v152; // [rsp+38h] [rbp-270h] BYREF
  HKEY v153; // [rsp+40h] [rbp-268h] BYREF
  HKEY v154; // [rsp+48h] [rbp-260h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-258h] BYREF
  BYTE *v156; // [rsp+58h] [rbp-250h] BYREF
  _QWORD *v157; // [rsp+60h] [rbp-248h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-240h] BYREF
  DWORD Type[4]; // [rsp+70h] [rbp-238h] BYREF
  _BYTE v160[56]; // [rsp+80h] [rbp-228h] BYREF
  __int64 v161; // [rsp+B8h] [rbp-1F0h]
  _BYTE v162[16]; // [rsp+C0h] [rbp-1E8h] BYREF
  __int128 v163; // [rsp+D0h] [rbp-1D8h] BYREF
  _BYTE v164[64]; // [rsp+E0h] [rbp-1C8h] BYREF
  char v165; // [rsp+120h] [rbp-188h]
  _BYTE v166[32]; // [rsp+130h] [rbp-178h] BYREF
  _QWORD v167[4]; // [rsp+150h] [rbp-158h] BYREF
  char v168; // [rsp+170h] [rbp-138h]
  _BYTE v169[96]; // [rsp+190h] [rbp-118h] BYREF
  _QWORD v170[4]; // [rsp+1F0h] [rbp-B8h] BYREF
  GUID pclsid; // [rsp+210h] [rbp-98h] BYREF
  _BYTE v172[32]; // [rsp+220h] [rbp-88h] BYREF
  _BYTE v173[32]; // [rsp+240h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  try
  {
    *(_QWORD *)Type = a3;
    v152 = a1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            a2,
                            a3) )
    {
      v7 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( *v7 > 4u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v7,
          &dword_18018CD5C,
          0);
    }
    else if ( (unsigned int)dword_1801AB110 > 4 )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1801AB110,
        &byte_18018CD8F,
        0);
    }
    hKey = 0;
    v163 = *a2;
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::open_helper(
      &hKey,
      &v163);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::ensure_data(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>((struct wil::details::IFailureCallback *)v160);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&hKey);
    v156 = 0;
    v9 = CtapCborDecodePluginAuthenticatorStateList(a5, a4, (unsigned int)&v156, 0, 0);
    if ( !v9 )
      goto LABEL_20;
    v10 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::decoding_failed",
            v8);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 4, v10);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v11,
                            v12) )
    {
      if ( **(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16) <= 3u )
        goto LABEL_18;
      v13 = CtapCborErrorToWin32Error(v9);
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      v16 = word_18018CC2A;
      LODWORD(v17) = v14;
    }
    else
    {
      if ( (unsigned int)dword_1801AB110 <= 3 )
        goto LABEL_18;
      v13 = CtapCborErrorToWin32Error(v9);
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      v16 = word_18018CCEA;
      v17 = &dword_1801AB110;
    }
    *(_DWORD *)Data = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (_DWORD)v17,
      (_DWORD)v16,
      v14,
      v15,
      (__int64)Data);
LABEL_18:
    v18 = CtapCborErrorToWin32Error(v9);
    if ( v18 )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x6AB,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)v18,
              lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
      return v19;
    }
LABEL_20:
    v22 = v156;
    if ( !v156 || (v23 = 0, !*((_QWORD *)v156 + 1)) )
      v23 = 1;
    v24 = *(_DWORD *)v156;
    v25 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::invalid_parameters",
            v8);
    if ( (_BYTE)v27 )
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 2, v25);
    if ( v23 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v26,
                              v27) )
      {
        v30 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v30 > 3 )
        {
          v31 = &dword_18018CC94;
LABEL_31:
          *(_DWORD *)Data = -2147467261;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v30,
            (_DWORD)v31,
            v28,
            v29,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v31 = &dword_18018CB14;
        v30 = &dword_1801AB110;
        goto LABEL_31;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6BF,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80004003LL,
        lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
      return 2147500035LL;
    }
    if ( v24 != 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v26,
                              v27) )
      {
        v34 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v34 > 3 )
        {
          v35 = byte_18018CABB;
LABEL_39:
          *(_DWORD *)Data = -2147024809;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v34,
            (_DWORD)v35,
            v32,
            v33,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v35 = byte_18018CBC9;
        v34 = &dword_1801AB110;
        goto LABEL_39;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6CF,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80070057LL,
        lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
      return 2147942487LL;
    }
    v36 = **((_QWORD **)v22 + 1);
    v157 = (_QWORD *)v36;
    v37 = (LPCWSTR *)(v36 + 8);
    *(_QWORD *)&v163 = v36 + 8;
    v38 = *(_QWORD *)(v36 + 8);
    v39 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::invalid_parameters",
            v26);
    if ( (_BYTE)v41 )
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 2, v39);
    if ( !v36 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v40,
                              v41) )
      {
        v44 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v44 > 3 )
        {
          v45 = word_18018CB72;
LABEL_49:
          *(_DWORD *)Data = -2147467261;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v44,
            (_DWORD)v45,
            v42,
            v43,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v45 = (__int16 *)byte_18018C9FD;
        v44 = &dword_1801AB110;
        goto LABEL_49;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E4,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80004003LL,
        lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
      return 2147500035LL;
    }
    if ( !v38 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v40,
                              v41) )
      {
        v48 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v48 > 3 )
        {
          v49 = &word_18018C9A6;
LABEL_57:
          *(_DWORD *)Data = -2147467261;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v48,
            (_DWORD)v49,
            v46,
            v47,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v49 = (__int16 *)&dword_18018CA5C;
        v48 = &dword_1801AB110;
        goto LABEL_57;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F4,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80004003LL,
        lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
      return 2147500035LL;
    }
    v156 = (BYTE *)(v36 + 40);
    v50 = v152;
    if ( *(_DWORD *)v156 != 1 )
      goto LABEL_93;
    lpData = 0;
    UvPubKey = CtapPluginGetUvPubKey(v152, *(_QWORD *)Type, *v37, 0);
    if ( UvPubKey < 0 )
    {
      v53 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_creation_failed",
              v51);
      if ( UvPubKey != -2146893770 )
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 7, v53);
      v55 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::user_cancelled",
              v54);
      if ( UvPubKey == -2146893770 )
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 13, v55);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v56,
                              v57) )
      {
        v60 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v60 > 3 )
        {
          v61 = &word_18018C8A6;
LABEL_70:
          *(_DWORD *)Data = UvPubKey;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v60,
            (_DWORD)v61,
            v58,
            v59,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v61 = (__int16 *)byte_18018C949;
        v60 = &dword_1801AB110;
        goto LABEL_70;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x70E,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)UvPubKey,
          lpData);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
      return (unsigned int)UvPubKey;
    }
    hKey = 0;
    UserRegPath = GetUserRegPath(v50, &hKey);
    if ( UserRegPath < 0 )
    {
      v64 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::save_to_local_device_toggle_failed",
              v62);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 10, v64);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v65,
                              v66) )
      {
        v69 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v69 > 3 )
        {
          v70 = (__int16 *)byte_18018C8FB;
LABEL_80:
          *(_DWORD *)Data = UserRegPath;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v69,
            (_DWORD)v70,
            v67,
            v68,
            (__int64)Data);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v70 = &word_18018C75E;
        v69 = &dword_1801AB110;
        goto LABEL_80;
      }
LABEL_92:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_93:
      v154 = 0;
      UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey((__int64)v50, (__int64)&v154);
      if ( UserPluginAuthenticatorsRegKey < 0 )
      {
        v83 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::registry_access_failed",
                v81);
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 9, v83);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                v84,
                                v85) )
        {
          v88 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v88 > 3 )
          {
            v89 = (int *)byte_18018C65D;
LABEL_99:
            LODWORD(v152) = UserPluginAuthenticatorsRegKey;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v88,
              (_DWORD)v89,
              v86,
              v87,
              (__int64)&v152);
          }
        }
        else if ( (unsigned int)dword_1801AB110 > 3 )
        {
          v89 = &dword_18018C5F4;
          v88 = &dword_1801AB110;
          goto LABEL_99;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x75B,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
            lpData);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v154);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
        return (unsigned int)UserPluginAuthenticatorsRegKey;
      }
      v153 = 0;
      v90 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v153);
      v92 = RegOpenKeyExW(v154, *v37, 0, 0xF003Fu, v90);
      if ( v92 )
      {
        v93 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::clsid_not_found",
                v91);
        if ( v92 == 2 )
          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 5, v93);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                v94,
                                v95) )
        {
          v98 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v98 > 3 )
          {
            if ( v92 > 0 )
              v99 = (unsigned __int16)v92 | 0x80070000;
            else
              v99 = v92;
            v100 = word_18018C712;
LABEL_117:
            LODWORD(v152) = v99;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v98,
              (_DWORD)v100,
              v96,
              v97,
              (__int64)&v152);
          }
        }
        else if ( (unsigned int)dword_1801AB110 > 3 )
        {
          if ( v92 > 0 )
            v99 = (unsigned __int16)v92 | 0x80070000;
          else
            v99 = v92;
          v100 = &word_18018C6BE;
          v98 = &dword_1801AB110;
          goto LABEL_117;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        {
          v101 = v92 < 0;
          if ( v92 > 0 )
          {
            v92 = (unsigned __int16)v92 | 0x80070000;
            v101 = v92 < 0;
          }
          if ( v101 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x777,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)v92,
              lpDataa);
        }
        else if ( v92 > 0 )
        {
          v92 = (unsigned __int16)v92 | 0x80070000;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v153);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v154);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
        return (unsigned int)v92;
      }
      std::wstring::wstring(v170);
      PluginAuthenticatorName = CtapPluginInternal::GetPluginAuthenticatorName(v153, v170);
      if ( PluginAuthenticatorName < 0 )
      {
        v104 = tip2::details::reason_string(
                 (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::plugin_name_retrieval_failed",
                 v102);
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 11, v104);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                v105,
                                v106) )
        {
          v109 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v109 > 3 )
          {
            v110 = (__int16 *)&unk_18018C4F8;
LABEL_132:
            LODWORD(v152) = PluginAuthenticatorName;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v109,
              (_DWORD)v110,
              v107,
              v108,
              (__int64)&v152);
          }
        }
        else if ( (unsigned int)dword_1801AB110 > 3 )
        {
          v110 = &word_18018C496;
          v109 = &dword_1801AB110;
          goto LABEL_132;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x792,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)PluginAuthenticatorName,
            lpDataa);
        std::wstring::_Tidy_deallocate(v170);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v153);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v154);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
        return (unsigned int)PluginAuthenticatorName;
      }
      v111 = v170;
      if ( v170[3] > 7u )
        v111 = (_QWORD *)v170[0];
      *v157 = v111;
      std::wstring::wstring(v172, v170);
      std::wstring::wstring(v173, *v37);
      FidoCredProvHelper::Locations::PluginAuthenticator::PluginAuthenticator(v164);
      v165 = 5;
      FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v172);
      v113 = RegSetValueExW(v153, L"State", 0, 4u, v156, 4u);
      if ( v113 )
      {
        v114 = tip2::details::reason_string(
                 (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::registry_access_failed",
                 v112);
        tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v161 + 8, 9, v114, v115);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                v116,
                                v117) )
        {
          v120 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v120 <= 3 )
            goto LABEL_151;
          if ( v113 > 0 )
            v121 = (unsigned __int16)v113 | 0x80070000;
          else
            v121 = v113;
          v122 = (__int16 *)&byte_18018C5A7;
        }
        else
        {
          if ( (unsigned int)dword_1801AB110 <= 3 )
            goto LABEL_151;
          if ( v113 > 0 )
            v121 = (unsigned __int16)v113 | 0x80070000;
          else
            v121 = v113;
          v122 = word_18018C552;
          v120 = &dword_1801AB110;
        }
        LODWORD(v152) = v121;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v120,
          (_DWORD)v122,
          v118,
          v119,
          (__int64)&v152);
LABEL_151:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        {
          v123 = v113 < 0;
          if ( v113 > 0 )
          {
            v113 = (unsigned __int16)v113 | 0x80070000;
            v123 = v113 < 0;
          }
          if ( v123 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7B5,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)v113,
              lpDatab);
        }
        else if ( v113 > 0 )
        {
          v113 = (unsigned __int16)v113 | 0x80070000;
        }
LABEL_173:
        std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v164);
        std::wstring::_Tidy_deallocate(v170);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v153);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v154);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
        return (unsigned int)v113;
      }
      LODWORD(v152) = 1;
      v124 = wil::reg::set_value_nothrow<unsigned int>(v153, 0, L"StateToggled", &v152);
      if ( v124 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7BD,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)v124,
          lpDatab);
      CredentialAuthenticatorCache::ClearAuthenticator(v50, v164);
      v125 = v156;
      if ( !*(_DWORD *)v156 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
          v126 = CtapPluginDeleteUvKey(v50);
        else
          v126 = CtapPluginDeleteUvKeyOld(v50, *v37);
        v113 = v126;
        if ( v126 < 0 )
        {
          v128 = tip2::details::reason_string(
                   (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_deletion_failed",
                   v127);
          tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v161 + 8, 8, v128, (unsigned int)v113);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                  v129,
                                  v130) )
          {
            v133 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
            if ( (unsigned int)*v133 <= 3 )
              goto LABEL_171;
            v134 = &dword_18018C394;
          }
          else
          {
            if ( (unsigned int)dword_1801AB110 <= 3 )
              goto LABEL_171;
            v134 = (int *)&byte_18018C337;
            v133 = &dword_1801AB110;
          }
          LODWORD(v152) = v113;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v133,
            (_DWORD)v134,
            v131,
            v132,
            (__int64)&v152);
LABEL_171:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7DD,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)v113,
              lpDatab);
          goto LABEL_173;
        }
        wil::impersonate_token(&v157, v50);
        WebAuthNSyncCheckEnableSaveLocalDevice();
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v157);
        v125 = v156;
      }
      try
      {
        GetPasskeyLocationVariantFromRegistry(v166, v50);
        if ( *(_DWORD *)v125 == 1 )
        {
          std::variant<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::operator=(
            v166,
            v164);
          v140 = FidoCredProvHelper::PasskeyLocationSelectionOutput::PasskeyLocationSelectionOutput(
                   (FidoCredProvHelper::PasskeyLocationSelectionOutput *)v169,
                   (const struct FidoCredProvHelper::PasskeyLocationSelectionOutput *)v166);
          SavePasskeyLocationVariantToRegistry(v50, v140);
        }
        else if ( v168 == (__int64)v165 )
        {
          if ( v168 != 5 )
            std::_Throw_bad_variant_access();
          v135 = (char *)v167;
          if ( v167[3] > 7u )
            v135 = (char *)v167[0];
          v136 = (char *)*v37 - v135;
          do
          {
            v137 = *(unsigned __int16 *)&v135[v136];
            v138 = *(unsigned __int16 *)v135 - v137;
            if ( v138 )
              break;
            v135 += 2;
          }
          while ( v137 );
          if ( !v138 )
          {
            v139 = ResetPasskeyLocationVariantInRegistry(v50);
            if ( v139 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x7F0,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)(unsigned int)v139,
                lpDatab);
          }
        }
        FidoCredProvHelper::PasskeyLocationSelectionOutput::~PasskeyLocationSelectionOutput((FidoCredProvHelper::PasskeyLocationSelectionOutput *)v166);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x7FB,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          v141);
        v144 = tip2::details::reason_string(
                 (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::failed_to_set_last_used",
                 v143);
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 12, v144);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                v145,
                                v146) )
        {
          v147 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( *v147 > 4u )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              v147,
              word_18018C442,
              0);
        }
        else if ( (unsigned int)dword_1801AB110 > 4 )
        {
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1801AB110,
            byte_18018C3E9,
            0);
        }
        v37 = (LPCWSTR *)v163;
      }
      pclsid = 0;
      CLSIDFromString(*v37, &pclsid);
      v142 = RtlPublishWnfStateData(WNF_WEBA_PLUGIN_STATE_CHANGED, 0, &pclsid, 16) | 0x10000000;
      if ( v142 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x80C,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)v142,
          0);
      std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v164);
      std::wstring::_Tidy_deallocate(v170);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v153);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v154);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>(v160);
      return 0;
    }
    *(_DWORD *)Data = 0;
    Type[0] = 4;
    cbData = 4;
    v71 = RegQueryValueExW(hKey, L"LocalToggleEnabledByUser", 0, Type, Data, &cbData);
    if ( v71 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x72E,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)v71,
        lpData);
    if ( *(_DWORD *)Data )
      goto LABEL_92;
    wil::impersonate_token(v162, v50);
    LODWORD(v152) = 0;
    v73 = wil::reg::set_value_nothrow<unsigned int>(hKey, 0, L"LocalToggleStatus", &v152);
    if ( v73 < 0 )
    {
      v74 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::save_to_local_device_toggle_failed",
              v72);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v161 + 8, 10, v74);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v75,
                              v76) )
      {
        v79 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v79 > 3 )
        {
          v80 = (int *)byte_18018C831;
LABEL_90:
          LODWORD(v152) = v73;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v79,
            (_DWORD)v80,
            v77,
            v78,
            (__int64)&v152);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v80 = &dword_18018C7B4;
        v79 = &dword_1801AB110;
        goto LABEL_90;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v162);
    goto LABEL_92;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x810,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                           v20);
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
0x180118b72  lea     rdx, dword_18018CD5C
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
0x180118c5d  lea     rdx, word_18018CC2A
0x180118c64  mov     rcx, r8
0x180118c67  jmp     short loc_180118CC6
0x180118c69  mov     eax, cs:dword_1801AB110
0x180118c6f  cmp     eax, 4
0x180118c72  jbe     loc_180118B7E
0x180118c78  xor     r8d, r8d
0x180118c7b  lea     rdx, byte_18018CD8F
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
0x180118cbc  lea     rdx, word_18018CCEA
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
0x180118da5  lea     rdx, dword_18018CC94
0x180118dac  jmp     short loc_180118DC2
0x180118dae  mov     eax, cs:dword_1801AB110
0x180118db4  cmp     eax, esi
0x180118db6  jbe     short loc_180118DD9
0x180118db8  lea     rdx, dword_18018CB14
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
0x180118e39  lea     rdx, byte_18018CABB
0x180118e40  jmp     short loc_180118E56
0x180118e42  mov     eax, cs:dword_1801AB110
0x180118e48  cmp     eax, esi
0x180118e4a  jbe     short loc_180118E6D
0x180118e4c  lea     rdx, byte_18018CBC9
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
0x180118f22  lea     rdx, word_18018CB72
0x180118f29  jmp     short loc_180118F3F
0x180118f2b  mov     eax, cs:dword_1801AB110
0x180118f31  cmp     eax, esi
0x180118f33  jbe     short loc_180118F56
0x180118f35  lea     rdx, byte_18018C9FD
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
0x180118fb5  lea     rdx, word_18018C9A6
0x180118fbc  jmp     short loc_180118FD2
0x180118fbe  mov     eax, cs:dword_1801AB110
0x180118fc4  cmp     eax, esi
0x180118fc6  jbe     short loc_180118FE9
0x180118fc8  lea     rdx, dword_18018CA5C
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
