# winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::StartCheckForModelsAvailability$_ResumeCoro$1

- ea: `0x18018ee80`
- end: `0x18018f764`
- name: `winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::StartCheckForModelsAvailability$_ResumeCoro$1`
- size: `2276`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `41`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18018ee70`
- `0x18018f7a0`

## callees

- `0x18004e5d8`
- `0x180054730`
- `0x1800555f0`
- `0x180055ac4`
- `0x18008a124`
- `0x18009a33c`
- `0x1800cf39c`
- `0x1800d3584`
- `0x1800d3c34`
- `0x1800d3c74`
- `0x1800d3fd4`
- `0x1800d567c`
- `0x1800e2374`
- `0x1800e95f0`
- `0x1800ecb40`
- `0x1800efd10`
- `0x1800f0584`
- `0x1800fd4d0`
- `0x18010a494`
- `0x1801244c0`
- `0x1801249b0`
- `0x18013dd98`
- `0x180182c10`
- `0x180185eac`
- `0x1801861c8`
- `0x1801862e0`
- `0x180186434`
- `0x1801866d4`
- `0x180186784`
- `0x180186c48`
- `0x180187400`
- `0x180189b2c`
- `0x18018ebac`
- `0x18018ecc8`
- `0x18018ed0c`
- `0x18018ee80`
- `0x180190b88`
- `0x180191078`
- `0x180191aac`
- `0x180191b38`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18018efb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18018efb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18018ef6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18018efa9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18018ef6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18018efa9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18018ef42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18018ef42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018f252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018f51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018f252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018f51f`

## string_xrefs

- `0x18018f193`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x18018f267`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x18018f296`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x18018f2c5`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x18018f41d`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x18018f534`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x18018f563`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x18018f592`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x18018f1c4`: `"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp"`
- `0x18018f451`: `"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp"`
- `0x18018f1b8`: `SemanticSearchConfigValidator: WSAIFabricSvc setup failed.`
- `0x18018f445`: `SemanticSearchConfigValidator: WSAIFabricSvc setup failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::StartCheckForModelsAvailability__ResumeCoro_1(
        char *Block)
{
  char *v2; // rdi
  _QWORD *v3; // rax
  RTL_SRWLOCK *v4; // r13
  _QWORD *v5; // r15
  void *v6; // rdx
  __int64 v7; // rax
  HKEY v8; // rcx
  __int64 v9; // rcx
  __int64 *v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // r12
  _QWORD *v13; // rbx
  int v14; // eax
  const wchar_t *v15; // r9
  unsigned int v16; // r15d
  __int64 v17; // rcx
  char IsEnabled; // bl
  bool SemanticIndexEncryptionStatus; // al
  __int64 v20; // rcx
  DWORD LastError; // eax
  const char *v22; // r9
  const char *v23; // r9
  _QWORD *v24; // r12
  _QWORD *v25; // rbx
  int v26; // eax
  const wchar_t *v27; // r9
  __int64 v28; // rcx
  char v29; // bl
  bool v30; // al
  __int64 v31; // rcx
  DWORD v32; // eax
  const char *v33; // r9
  const char *v34; // r9
  unsigned int v35; // r15d
  const wchar_t *v36; // [rsp+20h] [rbp-F8h]
  unsigned int v37; // [rsp+20h] [rbp-F8h]
  unsigned int v38; // [rsp+20h] [rbp-F8h]
  char v39; // [rsp+30h] [rbp-E8h]
  char v40; // [rsp+30h] [rbp-E8h]
  wil::details **v41; // [rsp+40h] [rbp-D8h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  switch ( *((_WORD *)Block + 16) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_67;
    case 2:
      v2 = Block + 40;
      *((_QWORD *)Block + 5) = 0;
      v3 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::ensure_data(Block + 40);
      tip2::details::shared_data<0,0,0>::start(*v3 + 8LL, Block + 648);
      v4 = (RTL_SRWLOCK *)*((_QWORD *)Block + 3);
      *((_QWORD *)Block + 84) = v4;
      v5 = Block + 48;
      winrt::implements<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager,winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager>::get_strong(
        v4,
        Block + 48);
      *((_QWORD *)Block + 7) = 0;
      AcquireSRWLockShared(v4 + 7);
      v41 = (wil::details **)&v4[4];
      if ( !(unsigned __int8)_is_signaled___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NXZ(&v4[4]) )
      {
        tip2::tip_test<tip2::details::merged_data<_tip_SqliteOpenDbTest,_tip_SqliteOpenDbTest>>::complete(v2);
        if ( v4 != (RTL_SRWLOCK *)-56LL )
          ReleaseSRWLockShared(v4 + 7);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 56);
        if ( *v5 )
          winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::factory_implementation::SemanticSearchConfigManager>::unconditional_release_ref(Block + 48);
LABEL_7:
        wil::com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>(v2);
        goto LABEL_67;
      }
      if ( v4 != (RTL_SRWLOCK *)-56LL )
        ReleaseSRWLockShared(v4 + 7);
      AcquireSRWLockExclusive(v4 + 7);
      *((_QWORD *)Block + 8) = v4 + 7;
      if ( !(unsigned __int8)_is_signaled___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NXZ(v41) )
      {
        tip2::tip_test<tip2::details::merged_data<_tip_SqliteOpenDbTest,_tip_SqliteOpenDbTest>>::complete(v2);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(Block + 64);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 56);
        if ( *v5 )
          winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::factory_implementation::SemanticSearchConfigManager>::unconditional_release_ref(Block + 48);
        goto LABEL_7;
      }
      wil::details::ResetEvent(*v41, v6);
      v7 = _SetEvent_scope_exit___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_XZ(
             v41,
             Block + 72);
      __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
        Block + 56,
        v7);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 72);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(Block + 64);
      *((_DWORD *)Block + 166) = 18;
      WSearchRegSetKeyValue(
        v8,
        L"SOFTWARE\\Microsoft\\Windows Search\\SemanticIndexer",
        L"SemanticIndexingStatus",
        4u,
        Block + 664,
        4u);
      winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::SetSemanticIndexingStatus(
        *((_QWORD *)Block + 3),
        18);
      Block[80] = 0;
      *((_WORD *)Block + 16) = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v9, Block);
      return;
    case 4:
      v10 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::ensure_data(Block + 40);
      *((_QWORD *)Block + 12) = &tip2::test_watcher<tip2::details::merged_data<_tip_LexicalDbEncryptionTest,_tip_LexicalDbEncryptionTest>>::`vftable';
      wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
        (wil::details::ThreadFailureCallbackHolder *)(Block + 104),
        (struct wil::details::IFailureCallback *)(Block + 96),
        0,
        1);
      v11 = *v10;
      *((_QWORD *)Block + 19) = *v10;
      if ( v11 )
        _InterlockedAdd((volatile signed __int32 *)(v11 + 280), 1u);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55745486>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55745486>::GetImpl'::`2'::impl) )
      {
        v12 = Block + 160;
        *((_QWORD *)Block + 20) = 0;
        v13 = Block + 168;
        CreateSemanticSearchServices(Block + 168);
        Block[176] = 0;
        v14 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v13 + 24LL))(*v13, Block + 176);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x83,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
            (const char *)(unsigned int)v14,
            (int)v36);
        if ( Block[176] )
        {
          v17 = *v13;
          if ( *v13 )
          {
            *v12 = v17;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
          }
          wil::com_ptr_t<ISearchManager,wil::err_returncode_policy>::~com_ptr_t<ISearchManager,wil::err_returncode_policy>(Block + 168);
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54620742>::GetImpl'::`2'::impl);
          SemanticIndexEncryptionStatus = GetSemanticIndexEncryptionStatus();
          if ( !IsEnabled && SemanticIndexEncryptionStatus )
          {
            CRegistry::CRegistry(
              (CRegistry *)(Block + 192),
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows Search",
              0x2001Fu,
              v36);
            LastError = GetLastError();
            if ( LastError )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0xA1,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
                (const char *)LastError,
                v37);
            if ( !(unsigned int)CRegistry::SetValue((CRegistry *)(Block + 192), L"ClearSemanticTextIndex", 1u) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0xA2,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
                v22);
            if ( !(unsigned int)CRegistry::SetValue((CRegistry *)(Block + 192), L"ClearSemanticImageIndex", 1u) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0xA3,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
                v23);
            CRegistry::~CRegistry((CRegistry *)(Block + 192));
          }
          winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::ConstructSemanticIndexStoreOptions(
            v20,
            Block + 384);
          winrt::com_ptr<IIndexerSemanticSearchServices>::as<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices>(
            Block + 160,
            Block + 392);
          v39 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchServices<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices>::AreSemanticSearchModelsAvailable(
                  Block + 392,
                  Block + 384);
          if ( v39 )
          {
            winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchServices<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices>::SetPreferredSemanticIndexOptions(
              Block + 392,
              Block + 384);
            v16 = 0;
          }
          else
          {
            v16 = 2;
          }
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::operator->(
                                  Block + 40,
                                  Block + 400)
                   + 272LL) = v39;
          tip2::test_data_control<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::~test_data_control<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>(Block + 400);
          tip2::tip_test<tip2::details::merged_data<_tip_SqliteOpenDbTest,_tip_SqliteOpenDbTest>>::complete(Block + 40);
          _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)(Block + 392));
          _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)(Block + 384));
          if ( *v12 )
            winrt::com_ptr<IURL>::unconditional_release_ref(Block + 160);
        }
        else
        {
          tip2::tip_test<tip2::details::merged_data<_tip_SqliteOpenDbTest,_tip_SqliteOpenDbTest>>::complete(Block + 40);
          SearchIndexerTrace::Error(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\semanticsearchconfigmanager.cpp\"",
            (const wchar_t *)0x88,
            (unsigned int)L"SemanticSearchConfigValidator: WSAIFabricSvc setup failed.",
            v15);
          v16 = 13;
          wil::com_ptr_t<ISearchManager,wil::err_returncode_policy>::~com_ptr_t<ISearchManager,wil::err_returncode_policy>(Block + 168);
        }
        winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::SetSemanticIndexingStatus(
          *((_QWORD *)Block + 3),
          v16);
LABEL_64:
        tip2::test_watcher<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::~test_watcher<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>(Block + 96);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 56);
        if ( *((_QWORD *)Block + 6) )
          ((void (*)(void))winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::factory_implementation::SemanticSearchConfigManager>::unconditional_release_ref)();
        goto LABEL_66;
      }
      v24 = Block + 408;
      *((_QWORD *)Block + 51) = 0;
      v25 = Block + 416;
      CreateSemanticSearchServices(Block + 416);
      Block[424] = 0;
      v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 24LL))(*v25);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
          (const char *)(unsigned int)v26,
          (int)v36);
      if ( Block[424] )
      {
        v28 = *v25;
        if ( *v25 )
        {
          *v24 = v28;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
        }
        wil::com_ptr_t<ISearchManager,wil::err_returncode_policy>::~com_ptr_t<ISearchManager,wil::err_returncode_policy>(Block + 416);
        v29 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54620742>::GetImpl'::`2'::impl);
        v30 = GetSemanticIndexEncryptionStatus();
        if ( !v29 && v30 )
        {
          CRegistry::CRegistry(
            (CRegistry *)(Block + 432),
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows Search",
            0x2001Fu,
            v36);
          v32 = GetLastError();
          if ( v32 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0xE5,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
              (const char *)v32,
              v38);
          if ( !(unsigned int)CRegistry::SetValue((CRegistry *)(Block + 432), L"ClearSemanticTextIndex", 1u) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xE6,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
              v33);
          if ( !(unsigned int)CRegistry::SetValue((CRegistry *)(Block + 432), L"ClearSemanticImageIndex", 1u) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xE7,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
              v34);
          CRegistry::~CRegistry((CRegistry *)(Block + 432));
        }
        winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::ConstructSemanticIndexStoreOptions(
          v31,
          Block + 624);
        winrt::com_ptr<IIndexerSemanticSearchServices>::as<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices>(
          Block + 408,
          Block + 632);
        v40 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchServices<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices>::AreSemanticSearchModelsAvailable(
                Block + 632,
                Block + 624);
        if ( v40 )
        {
          winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchServices<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices>::SetPreferredSemanticIndexOptions(
            Block + 632,
            Block + 624);
          v35 = 0;
        }
        else
        {
          v35 = 2;
        }
        winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::SetSemanticIndexingStatus(
          *((_QWORD *)Block + 84),
          v35);
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::operator->(
                                Block + 40,
                                Block + 640)
                 + 272LL) = v40;
        tip2::test_data_control<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::~test_data_control<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>(Block + 640);
        tip2::tip_test<tip2::details::merged_data<_tip_SqliteOpenDbTest,_tip_SqliteOpenDbTest>>::complete(Block + 40);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)(Block + 632));
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)(Block + 624));
        if ( *v24 )
          winrt::com_ptr<IURL>::unconditional_release_ref(v24);
        goto LABEL_64;
      }
      tip2::tip_test<tip2::details::merged_data<_tip_SqliteOpenDbTest,_tip_SqliteOpenDbTest>>::complete(Block + 40);
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\semanticsearchconfigmanager.cpp\"",
        (const wchar_t *)0xCE,
        (unsigned int)L"SemanticSearchConfigValidator: WSAIFabricSvc setup failed.",
        v27);
      winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::SetSemanticIndexingStatus(
        *((_QWORD *)Block + 84),
        13);
      wil::com_ptr_t<ISearchManager,wil::err_returncode_policy>::~com_ptr_t<ISearchManager,wil::err_returncode_policy>(Block + 416);
      tip2::test_watcher<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::~test_watcher<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>(Block + 96);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 56);
      if ( *((_QWORD *)Block + 6) )
        ((void (*)(void))winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::factory_implementation::SemanticSearchConfigManager>::unconditional_release_ref)();
LABEL_66:
      wil::com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>(Block + 40);
LABEL_67:
      if ( *((_WORD *)Block + 17) )
        operator delete(Block);
      return;
    case 5:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 56);
      if ( *((_QWORD *)Block + 6) )
        ((void (*)(void))winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::factory_implementation::SemanticSearchConfigManager>::unconditional_release_ref)();
      goto LABEL_66;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18018ee80  mov     r11, rsp
0x18018ee83  mov     [r11+10h], rbx
0x18018ee87  mov     [r11+18h], rsi
0x18018ee8b  mov     [r11+8], rcx
0x18018ee8f  push    rdi
0x18018ee90  push    r12
0x18018ee92  push    r13
0x18018ee94  push    r14
0x18018ee96  push    r15
0x18018ee98  sub     rsp, 0F0h
0x18018ee9f  mov     rax, cs:__security_cookie
0x18018eea6  xor     rax, rsp
0x18018eea9  mov     [rsp+118h+var_38], rax
0x18018eeb1  mov     r14, rcx
0x18018eeb4  mov     [rsp+118h+var_D0], rcx
0x18018eeb9  movzx   eax, word ptr [r14+20h]
0x18018eebe  mov     [rsp+118h+var_C0], ax
0x18018eec3  mov     edi, 1
0x18018eec8  add     ax, di
0x18018eecb  cmp     ax, 6; switch 7 cases
0x18018eecf  ja      def_18018EEEA; jumptable 000000018018EEEA default case, cases 1,2
0x18018eed5  movsx   rax, ax
0x18018eed9  lea     rdx, __ImageBase
0x18018eee0  mov     ecx, ds:(jpt_18018EEEA - 180000000h)[rdx+rax*4]
0x18018eee7  add     rcx, rdx
0x18018eeea  jmp     rcx; switch jump
0x18018eeec  xor     esi, esi; jumptable 000000018018EEEA case 4
0x18018eeee  jmp     loc_18018F6FE
0x18018eef3  lea     rdi, [r14+28h]; jumptable 000000018018EEEA case 3
0x18018eef7  xor     esi, esi
0x18018eef9  mov     [rdi], rsi
0x18018eefc  mov     rcx, rdi
0x18018eeff  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AsyncIsAvailableCallTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AsyncIsAvailableCallTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::ensure_data(void)
0x18018ef04  lea     rdx, [r14+288h]
0x18018ef0b  mov     rcx, [rax]
0x18018ef0e  add     rcx, 8
0x18018ef12  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18018ef17  nop
0x18018ef18  mov     r13, [r14+18h]
0x18018ef1c  mov     [r14+2A0h], r13
0x18018ef23  lea     r15, [r14+30h]
0x18018ef27  mov     rdx, r15
0x18018ef2a  mov     rcx, r13
0x18018ef2d  call    ?get_strong@?$implements@USemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@U13456@@winrt@@QEAA?AU?$com_ptr@USemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager,winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager>::get_strong(void)
0x18018ef32  nop
0x18018ef33  lea     r12, [r14+38h]
0x18018ef37  mov     [r12], rsi
0x18018ef3b  lea     rbx, [r13+38h]
0x18018ef3f  mov     rcx, rbx; SRWLock
0x18018ef42  call    cs:__imp_AcquireSRWLockShared
0x18018ef48  lea     rax, [r13+20h]
0x18018ef4c  mov     [rsp+118h+var_D8], rax
0x18018ef51  mov     rcx, rax
0x18018ef54  call    ?is_signaled@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NXZ
0x18018ef59  test    al, al
0x18018ef5b  jnz     short loc_18018EFA1
0x18018ef5d  mov     rcx, rdi
0x18018ef60  call    ?complete@?$tip_test@V?$merged_data@U_tip_SqliteOpenDbTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_SqliteOpenDbTest,_tip_SqliteOpenDbTest>>::complete(void)
0x18018ef65  test    rbx, rbx
0x18018ef68  jz      short loc_18018EF74
0x18018ef6a  mov     rcx, rbx; SRWLock
0x18018ef6d  call    cs:__imp_ReleaseSRWLockShared
0x18018ef73  nop
0x18018ef74  mov     rcx, r12
0x18018ef77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018ef7c  nop
0x18018ef7d  mov     rax, [r15]
0x18018ef80  mov     [rsp+118h+var_E0], rax
0x18018ef85  test    rax, rax
0x18018ef88  jz      short loc_18018EF93
0x18018ef8a  mov     rcx, r15
0x18018ef8d  call    ?unconditional_release_ref@?$com_ptr@USemanticSearchConfigManager@factory_implementation@SemanticSearch@Indexer@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::factory_implementation::SemanticSearchConfigManager>::unconditional_release_ref(void)
0x18018ef92  nop
0x18018ef93  mov     rcx, rdi
0x18018ef96  call    ??1?$com_ptr_t@V?$merged_data@U_tip_AsyncIsAvailableCallTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>(void)
0x18018ef9b  nop
0x18018ef9c  jmp     loc_18018F6FE
0x18018efa1  test    rbx, rbx
0x18018efa4  jz      short loc_18018EFAF
0x18018efa6  mov     rcx, rbx; SRWLock
0x18018efa9  call    cs:__imp_ReleaseSRWLockShared
0x18018efaf  mov     rcx, rbx; SRWLock
0x18018efb2  call    cs:__imp_AcquireSRWLockExclusive
0x18018efb8  lea     r13, [r14+40h]
0x18018efbc  mov     [r13+0], rbx
0x18018efc0  mov     rbx, [rsp+118h+var_D8]
0x18018efc5  mov     rcx, rbx
0x18018efc8  call    ?is_signaled@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NXZ
0x18018efcd  test    al, al
0x18018efcf  jnz     short loc_18018F00F
0x18018efd1  mov     rcx, rdi
0x18018efd4  call    ?complete@?$tip_test@V?$merged_data@U_tip_SqliteOpenDbTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_SqliteOpenDbTest,_tip_SqliteOpenDbTest>>::complete(void)
0x18018efd9  mov     rcx, r13
0x18018efdc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18018efe1  nop
0x18018efe2  mov     rcx, r12
0x18018efe5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018efea  nop
0x18018efeb  mov     rax, [r15]
0x18018efee  mov     [rsp+118h+var_E0], rax
0x18018eff3  test    rax, rax
0x18018eff6  jz      short loc_18018F001
0x18018eff8  mov     rcx, r15
0x18018effb  call    ?unconditional_release_ref@?$com_ptr@USemanticSearchConfigManager@factory_implementation@SemanticSearch@Indexer@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::factory_implementation::SemanticSearchConfigManager>::unconditional_release_ref(void)
0x18018f000  nop
0x18018f001  mov     rcx, rdi
0x18018f004  call    ??1?$com_ptr_t@V?$merged_data@U_tip_AsyncIsAvailableCallTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>(void)
0x18018f009  nop
0x18018f00a  jmp     loc_18018F6FE
0x18018f00f  mov     rcx, [rbx]; this
0x18018f012  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x18018f017  lea     rdx, [r14+48h]
0x18018f01b  mov     rcx, rbx
0x18018f01e  call    ?SetEvent_scope_exit@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x18018f023  mov     rdx, rax
0x18018f026  mov     rcx, r12
0x18018f029  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18018f02e  lea     rcx, [r14+48h]
0x18018f032  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018f037  mov     rcx, r13
0x18018f03a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18018f03f  nop
0x18018f040  lea     rax, [r14+298h]
0x18018f047  mov     r15d, 12h
0x18018f04d  mov     [rax], r15d
0x18018f050  lea     ebx, [r15-0Eh]
0x18018f054  mov     [rsp+118h+var_F0], ebx; unsigned int
0x18018f058  mov     [rsp+118h+var_F8], rax; void *
0x18018f05d  mov     r9d, ebx; unsigned int
0x18018f060  lea     r8, aSemanticindexi; "SemanticIndexingStatus"
0x18018f067  lea     rdx, aSoftwareMicros_24; "SOFTWARE\\Microsoft\\Windows Search\\Se"...
0x18018f06e  call    ?WSearchRegSetKeyValue@@YAJPEAUHKEY__@@PEB_W1KPEBXK@Z; WSearchRegSetKeyValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,void const *,ulong)
0x18018f073  nop
0x18018f074  mov     edx, r15d
0x18018f077  mov     rcx, [r14+18h]
0x18018f07b  call    ?SetSemanticIndexingStatus@SemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@AEAAXW4SemanticIndexingStatus@@@Z; winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::SetSemanticIndexingStatus(SemanticIndexingStatus)
0x18018f080  mov     [r14+50h], sil
0x18018f084  mov     [r14+20h], bx
0x18018f089  mov     rdx, r14
0x18018f08c  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18018f091  jmp     loc_18018F719
0x18018f096  lea     rcx, [r14+38h]; jumptable 000000018018EEEA case 6
0x18018f09a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018f09f  nop
0x18018f0a0  lea     rcx, [r14+30h]
0x18018f0a4  mov     rax, [rcx]
0x18018f0a7  mov     [rsp+118h+var_E0], rax
0x18018f0ac  xor     esi, esi
0x18018f0ae  test    rax, rax
0x18018f0b1  jz      short loc_18018F0B9
0x18018f0b3  call    ?unconditional_release_ref@?$com_ptr@USemanticSearchConfigManager@factory_implementation@SemanticSearch@Indexer@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::factory_implementation::SemanticSearchConfigManager>::unconditional_release_ref(void)
0x18018f0b8  nop
0x18018f0b9  lea     rcx, [r14+28h]
0x18018f0bd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_AsyncIsAvailableCallTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>,wil::err_returncode_policy>(void)
0x18018f0c2  nop
0x18018f0c3  jmp     loc_18018F6FE
0x18018f0c8  lea     r15, [r14+28h]; jumptable 000000018018EEEA case 5
0x18018f0cc  mov     [rsp+118h+var_B0], r15
0x18018f0d1  mov     rcx, r15
0x18018f0d4  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AsyncIsAvailableCallTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AsyncIsAvailableCallTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AsyncIsAvailableCallTest,_tip_AsyncIsAvailableCallTest>>::ensure_data(void)
0x18018f0d9  mov     rbx, rax
0x18018f0dc  lea     r13, [r14+60h]
0x18018f0e0  mov     [rsp+118h+var_E0], r13
0x18018f0e5  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_LexicalDbEncryptionTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_LexicalDbEncryptionTest,_tip_LexicalDbEncryptionTest>>::`vftable'
0x18018f0ec  mov     [r13+0], rax
0x18018f0f0  lea     rcx, [r14+68h]; this
0x18018f0f4  mov     r9b, dil; bool
0x18018f0f7  xor     r8d, r8d; struct wil::CallContextInfo *
0x18018f0fa  mov     rdx, r13; struct wil::details::IFailureCallback *
0x18018f0fd  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18018f102  mov     rax, [rbx]
0x18018f105  mov     [r14+98h], rax
0x18018f10c  xor     esi, esi
0x18018f10e  test    rax, rax
0x18018f111  jz      short loc_18018F11A
0x18018f113  lock add [rax+118h], edi
0x18018f11a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55745486@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55745486@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55745486> `wil::Feature<__WilFeatureTraits_Feature_55745486>::GetImpl(void)'::`2'::impl
0x18018f121  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55745486@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55745486>::__private_IsEnabled(void)
0x18018f126  test    al, al
0x18018f128  jz      loc_18018F3D0
0x18018f12e  mov     r15d, 12h
0x18018f134  mov     al, sil
0x18018f137  mov     [rsp+118h+var_E7], al
0x18018f13b  cmp     al, 3
0x18018f13d  jnb     loc_18018F3BF
0x18018f143  lea     r12, [r14+0A0h]
0x18018f14a  mov     [rsp+118h+var_D8], r12
0x18018f14f  mov     [r12], rsi
0x18018f153  lea     rbx, [r14+0A8h]
0x18018f15a  mov     rcx, rbx
0x18018f15d  call    ?CreateSemanticSearchServices@@YA?AV?$com_ptr_t@UIIndexerSemanticSearchServices@@Uerr_exception_policy@wil@@@wil@@XZ; CreateSemanticSearchServices(void)
0x18018f162  nop
0x18018f163  lea     r15, [r14+0B0h]
0x18018f16a  mov     [r15], sil
0x18018f16d  mov     rcx, [rbx]
0x18018f170  mov     [rsp+118h+var_B8], rcx
0x18018f175  mov     rax, [rcx]
0x18018f178  mov     rdx, r15
0x18018f17b  mov     rax, [rax+18h]
0x18018f17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f184  mov     rcx, [rsp+118h]; this
0x18018f18c  test    eax, eax
0x18018f18e  jns     short loc_18018F1A4
0x18018f190  mov     r9d, eax; char *
0x18018f193  lea     r8, aOnecoreuapBase_159; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18018f19a  mov     edx, 83h; void *
0x18018f19f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18018f1a4  mov     al, [r15]
0x18018f1a7  mov     [rsp+118h+var_E6], al
0x18018f1ab  test    al, al
0x18018f1ad  jnz     short loc_18018F1E4
0x18018f1af  lea     rcx, [r14+28h]
0x18018f1b3  call    ?complete@?$tip_test@V?$merged_data@U_tip_SqliteOpenDbTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_SqliteOpenDbTest,_tip_SqliteOpenDbTest>>::complete(void)
0x18018f1b8  lea     r8, aSemanticsearch_2; "SemanticSearchConfigValidator: WSAIFabr"...
0x18018f1bf  mov     edx, 88h; wchar_t *
0x18018f1c4  lea     rcx, aOnecoreuapBase_60; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18018f1cb  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18018f1d0  mov     r15d, 0Dh
0x18018f1d6  mov     rcx, rbx
0x18018f1d9  call    ??1?$com_ptr_t@UISearchManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISearchManager,wil::err_returncode_policy>::~com_ptr_t<ISearchManager,wil::err_returncode_policy>(void)
0x18018f1de  nop
0x18018f1df  jmp     loc_18018F3BF
0x18018f1e4  mov     rcx, [rbx]
0x18018f1e7  mov     [rsp+118h+var_B8], rcx
0x18018f1ec  test    rcx, rcx
0x18018f1ef  jz      short loc_18018F202
0x18018f1f1  mov     [r12], rcx
0x18018f1f5  mov     rax, [rcx]
0x18018f1f8  mov     rax, [rax+8]
0x18018f1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f201  nop
0x18018f202  mov     rcx, rbx
0x18018f205  call    ??1?$com_ptr_t@UISearchManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISearchManager,wil::err_returncode_policy>::~com_ptr_t<ISearchManager,wil::err_returncode_policy>(void)
0x18018f20a  nop
0x18018f20b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54620742@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54620742@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742> `wil::Feature<__WilFeatureTraits_Feature_54620742>::GetImpl(void)'::`2'::impl
0x18018f212  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54620742@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742>::__private_IsEnabled(void)
0x18018f217  mov     bl, al
0x18018f219  call    ?GetSemanticIndexEncryptionStatus@@YA_NXZ; GetSemanticIndexEncryptionStatus(void)
0x18018f21e  test    bl, bl
0x18018f220  jnz     loc_18018F2DF
0x18018f226  test    al, al
0x18018f228  jz      loc_18018F2DF
0x18018f22e  lea     rbx, [r14+0C0h]
0x18018f235  mov     r9d, 2001Fh; unsigned int
0x18018f23b  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x18018f242  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18018f249  mov     rcx, rbx; this
0x18018f24c  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEB_WK1@Z; CRegistry::CRegistry(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x18018f251  nop
0x18018f252  call    cs:__imp_GetLastError
0x18018f258  mov     rcx, [rsp+118h]; this
0x18018f260  test    eax, eax
0x18018f262  jz      short loc_18018F278
0x18018f264  mov     r9d, eax; char *
0x18018f267  lea     r8, aOnecoreuapBase_159; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18018f26e  mov     edx, 0A1h; void *
0x18018f273  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18018f278  mov     r8d, edi; unsigned int
0x18018f27b  lea     rdx, aClearsemantict; "ClearSemanticTextIndex"
0x18018f282  mov     rcx, rbx; this
0x18018f285  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x18018f28a  mov     rcx, [rsp+118h]; this
0x18018f292  test    eax, eax
0x18018f294  jnz     short loc_18018F2A7
0x18018f296  lea     r8, aOnecoreuapBase_159; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18018f29d  mov     edx, 0A2h; void *
0x18018f2a2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18018f2a7  mov     r8d, edi; unsigned int
0x18018f2aa  lea     rdx, aClearsemantici; "ClearSemanticImageIndex"
0x18018f2b1  mov     rcx, rbx; this
0x18018f2b4  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x18018f2b9  mov     rcx, [rsp+118h]; this
0x18018f2c1  test    eax, eax
0x18018f2c3  jnz     short loc_18018F2D7
0x18018f2c5  lea     r8, aOnecoreuapBase_159; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18018f2cc  mov     edx, 0A3h; void *
0x18018f2d1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18018f2d7  mov     rcx, rbx; this
0x18018f2da  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18018f2df  lea     r13, [r14+180h]
0x18018f2e6  mov     rdx, r13
0x18018f2e9  call    ?ConstructSemanticIndexStoreOptions@SemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@QEAA?AUSemanticIndexStoreOptions@3456@XZ; winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::ConstructSemanticIndexStoreOptions(void)
0x18018f2ee  nop
0x18018f2ef  lea     rbx, [r14+188h]
0x18018f2f6  mov     rdx, rbx
0x18018f2f9  mov     rcx, r12
0x18018f2fc  call    ??$as@UISemanticSearchServices@SemanticSearch@Indexer@Windows@winrt@@@?$com_ptr@UIIndexerSemanticSearchServices@@@winrt@@QEBA?A_PXZ
0x18018f301  nop
0x18018f302  mov     rdx, r13
0x18018f305  mov     rcx, rbx
0x18018f308  call    ?AreSemanticSearchModelsAvailable@?$consume_Windows_Indexer_SemanticSearch_ISemanticSearchServices@UISemanticSearchServices@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@AEBUSemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@3@@Z; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchServices<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices>::AreSemanticSearchModelsAvailable(winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions const &)
0x18018f30d  mov     [rsp+118h+var_E8], al
0x18018f311  test    al, al
0x18018f313  jz      short loc_18018F325
0x18018f315  mov     rdx, r13
0x18018f318  mov     rcx, rbx
0x18018f31b  call    ?SetPreferredSemanticIndexOptions@?$consume_Windows_Indexer_SemanticSearch_ISemanticSearchServices@UISemanticSearchServices@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@AEBUSemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@3@@Z; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchServices<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices>::SetPreferredSemanticIndexOptions(winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions const &)
0x18018f320  mov     r15d, esi
0x18018f323  jmp     short loc_18018F32B
0x18018f325  mov     r15d, 2
  ... truncated ...
```
