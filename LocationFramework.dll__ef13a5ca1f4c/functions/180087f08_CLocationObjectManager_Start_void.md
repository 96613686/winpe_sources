# CLocationObjectManager::Start(void)

- ea: `0x180087f08`
- end: `0x180088a2a`
- name: `?Start@CLocationObjectManager@@KAJXZ`
- size: `2850`
- prototype: `__int64(void)`
- caller_count: `193`
- callee_count: `30`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ca00`
- `0x18000ca60`
- `0x18001a4a4`
- `0x18001c908`
- `0x180022100`
- `0x180024c38`
- `0x180025900`
- `0x180025bec`
- `0x1800276a8`
- `0x180027ca8`
- `0x18002812c`
- `0x180028950`
- `0x180028ae0`
- `0x1800295ac`
- `0x1800297e8`
- `0x180029a94`
- `0x18002a50c`
- `0x18002a618`
- `0x18002a9d4`
- `0x18002eae4`
- `0x18003d0c0`
- `0x18003fefc`
- `0x18004575c`
- `0x180045878`
- `0x180045990`
- `0x180045aac`
- `0x180045bc8`
- `0x180045ce4`
- `0x180055050`
- `0x18005518c`
- `0x18005a5d8`
- `0x18005a72c`
- `0x18005a868`
- `0x18005a96c`
- `0x18005b73c`
- `0x18005c4dc`
- `0x18005c818`
- `0x18005e6ec`
- `0x18005f588`
- `0x180060b48`
- `0x18006158c`
- `0x180062ae0`
- `0x1800636a8`
- `0x180063f5c`
- `0x18006515c`
- `0x1800690f0`
- `0x180069abc`
- `0x18006a280`
- `0x18006a690`
- `0x18006af30`

## callees

- `0x18000c974`
- `0x18000dc00`
- `0x180011688`
- `0x180012398`
- `0x18001be08`
- `0x180021450`
- `0x180022568`
- `0x180022df8`
- `0x180023604`
- `0x18003b92c`
- `0x18004c784`
- `0x1800659d0`
- `0x180087f08`
- `0x18008f4b4`
- `0x18008f804`
- `0x1800932d0`
- `0x180098ccc`
- `0x18009e69c`
- `0x18009ead0`
- `0x18009ebc8`
- `0x1800a1f08`
- `0x1800a2d98`
- `0x1800a4760`
- `0x1800a6a18`
- `0x1800a728c`
- `0x1800a98c0`
- `0x1800bd5cc`
- `0x1800d70e8`
- `0x1800d7410`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087fae`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x180087f9c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x180087f9c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800889c1`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800889c1`

## string_xrefs

- `0x180088a14`: `onecoreuap\drivers\MobilePC\Location\Product\Core\Framework\inc\temp_wil.h`
- `0x180088a0d`: `wil_temp::condition_variable_sleep`
- `0x1800887af`: `CLocationComponentHelper::AutoCreateLocationComponent(&pCreateSingleton)`
- `0x1800888d8`: `CLocationComponentHelper::AutoCreateLocationComponent(&pCivicAddrAdapter)`
- `0x1800887fd`: `CLocationComponentHelper::AutoCreateLocationComponent(&pLpm)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 CLocationObjectManager::Start(void)
{
  int SettingValueDWORD; // eax
  __int64 result; // rax
  const char *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rax
  std::_Ref_count_base *v5; // rbx
  __int64 v6; // rax
  std::_Ref_count_base *v7; // rbx
  __int64 v8; // rax
  std::_Ref_count_base *v9; // rbx
  __int64 v10; // rax
  std::_Ref_count_base *v11; // rbx
  __int64 v12; // rax
  std::_Ref_count_base *v13; // rbx
  __int64 v14; // rax
  std::_Ref_count_base *v15; // rbx
  __int64 v16; // rax
  std::_Ref_count_base *v17; // rbx
  __int64 v18; // rax
  std::_Ref_count_base *v19; // rbx
  std::_Ref_count_base *v20; // rbx
  __m128i v21; // xmm6
  __int64 v22; // rax
  std::_Ref_count_base *v23; // rbx
  __int64 v24; // rax
  std::_Ref_count_base *v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int LocationComponent; // eax
  __int64 v29; // rcx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // eax
  char *v35; // [rsp+20h] [rbp-78h]
  char *v36; // [rsp+28h] [rbp-70h]
  char *v37; // [rsp+28h] [rbp-70h]
  int v38; // [rsp+30h] [rbp-68h]
  const char *v39; // [rsp+38h] [rbp-60h]
  std::_Ref_count_base *v40[2]; // [rsp+40h] [rbp-58h] BYREF
  PCRITICAL_SECTION CriticalSection[2]; // [rsp+50h] [rbp-48h] BYREF
  std::_Ref_count_base *v42[2]; // [rsp+60h] [rbp-38h] BYREF
  __int64 v43; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+0h]

  CriticalSection[0] = 0;
  wil::EnterCriticalSection(CriticalSection, &stru_1801E4420);
  LODWORD(v43) = 0;
  SettingValueDWORD = LocationRegistryHelper::GetSettingValueDWORD(512, L"HlkModeEnabled", 0, &v43);
  if ( SettingValueDWORD >= 0 && (_DWORD)v43 == 1 )
  {
    dword_1801E4448 = 4;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(CriticalSection);
    return 2147500036LL;
  }
  try
  {
    while ( dword_1801E4448 == 2 )
    {
      if ( !SleepConditionVariableCS(&ConditionVariable, CriticalSection[0], 0xFFFFFFFF) && GetLastError() != 1460 )
        wil::details::in1diag5::_FailFast_Unexpected(
          retaddr,
          (void *)0xD,
          (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Core\\Framework\\inc\\temp_wil.h",
          "wil_temp::condition_variable_sleep",
          "::GetLastError() != ERROR_TIMEOUT",
          v37);
    }
    if ( dword_1801E4448 == 1 )
      goto LABEL_121;
    if ( dword_1801E4448 == 2 )
    {
      v2 = "Leaving Start, but are in stopping state";
      v3 = 278;
    }
    else
    {
      if ( (unsigned int)(dword_1801E4448 - 3) <= 1 || !dword_1801E4448 )
      {
        *(_OWORD *)v42 = 0;
        v4 = std::make_shared<CLocationUserInfoHelper,>(v40);
        v42[0] = *(std::_Ref_count_base **)v4;
        v5 = *(std::_Ref_count_base **)(v4 + 8);
        v42[1] = v5;
        *(_QWORD *)v4 = 0;
        *(_QWORD *)(v4 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E42A8,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E42A8 + 8LL))(qword_1801E42A8) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            (char *)&xmmword_1801E42B0 + 8,
            &qword_1801E42A8);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E42A8, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v5 )
          std::_Ref_count_base::_Decref(v5);
        *(_OWORD *)v42 = 0;
        v6 = std::make_shared<CLocationActiveCollection,>(v40);
        v42[0] = *(std::_Ref_count_base **)v6;
        v7 = *(std::_Ref_count_base **)(v6 + 8);
        v42[1] = v7;
        *(_QWORD *)v6 = 0;
        *(_QWORD *)(v6 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E42C8,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E42C8 + 8LL))(qword_1801E42C8) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            (char *)&xmmword_1801E42D0 + 8,
            &qword_1801E42C8);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E42C8, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v7 )
          std::_Ref_count_base::_Decref(v7);
        *(_OWORD *)v42 = 0;
        v8 = std::make_shared<CVisitsEngine,>(v40);
        v42[0] = *(std::_Ref_count_base **)v8;
        v9 = *(std::_Ref_count_base **)(v8 + 8);
        v42[1] = v9;
        *(_QWORD *)v8 = 0;
        *(_QWORD *)(v8 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E4388,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4388 + 8LL))(qword_1801E4388) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            (char *)&xmmword_1801E4390 + 8,
            &qword_1801E4388);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E4388, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v9 )
          std::_Ref_count_base::_Decref(v9);
        *(_OWORD *)v42 = 0;
        v10 = std::make_shared<CLocationConfiguration,>(v40);
        v42[0] = *(std::_Ref_count_base **)v10;
        v11 = *(std::_Ref_count_base **)(v10 + 8);
        v42[1] = v11;
        *(_QWORD *)v10 = 0;
        *(_QWORD *)(v10 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E4308,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4308 + 8LL))(qword_1801E4308) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            &xmmword_1801E4310 + 1,
            &qword_1801E4308);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E4308, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v11 )
          std::_Ref_count_base::_Decref(v11);
        *(_OWORD *)v42 = 0;
        v12 = std::make_shared<CLocationUploader,>(v40);
        v42[0] = *(std::_Ref_count_base **)v12;
        v13 = *(std::_Ref_count_base **)(v12 + 8);
        v42[1] = v13;
        *(_QWORD *)v12 = 0;
        *(_QWORD *)(v12 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E4288,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4288 + 8LL))(qword_1801E4288) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            (char *)&xmmword_1801E4290 + 8,
            &qword_1801E4288);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E4288, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v13 )
          std::_Ref_count_base::_Decref(v13);
        *(_OWORD *)v42 = 0;
        v14 = std::make_shared<CLocationSavedPositions,>(v40);
        v42[0] = *(std::_Ref_count_base **)v14;
        v15 = *(std::_Ref_count_base **)(v14 + 8);
        v42[1] = v15;
        *(_QWORD *)v14 = 0;
        *(_QWORD *)(v14 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E4328,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4328 + 8LL))(qword_1801E4328) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            (char *)&xmmword_1801E4330 + 8,
            &qword_1801E4328);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E4328, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v15 )
          std::_Ref_count_base::_Decref(v15);
        *(_OWORD *)v42 = 0;
        v16 = std::make_shared<CLocationUIHandler,>(v40);
        v42[0] = *(std::_Ref_count_base **)v16;
        v17 = *(std::_Ref_count_base **)(v16 + 8);
        v42[1] = v17;
        *(_QWORD *)v16 = 0;
        *(_QWORD *)(v16 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E4348,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4348 + 8LL))(qword_1801E4348) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            (char *)&xmmword_1801E4350 + 8,
            &qword_1801E4348);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E4348, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
        *(_OWORD *)v42 = 0;
        v18 = std::make_shared<LocationSignalManager,>(v40);
        v42[0] = *(std::_Ref_count_base **)v18;
        v19 = *(std::_Ref_count_base **)(v18 + 8);
        v42[1] = v19;
        *(_QWORD *)v18 = 0;
        *(_QWORD *)(v18 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E4368,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4368 + 8LL))(qword_1801E4368) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            (char *)&xmmword_1801E4370 + 8,
            &qword_1801E4368);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E4368, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v19 )
          std::_Ref_count_base::_Decref(v19);
        *(_OWORD *)v42 = 0;
        std::make_shared<LocationBroker,>(v42);
        v20 = v42[1];
        if ( v42[1] )
        {
          _InterlockedIncrement((volatile signed __int32 *)v42[1] + 2);
          v20 = v42[1];
        }
        v21 = *(__m128i *)v42;
        *(_OWORD *)v40 = *(_OWORD *)v42;
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E43A8,
          v40);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E43A8 + 8LL))(qword_1801E43A8) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            (char *)&xmmword_1801E43B0 + 8,
            &qword_1801E43A8);
          *(_OWORD *)v40 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E43A8, v40);
          if ( v40[1] )
            std::_Ref_count_base::_Decref(v40[1]);
        }
        if ( v20 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)_mm_srli_si128(v21, 8).m128i_i64[0]);
        if ( v42[1] )
          std::_Ref_count_base::_Decref(v42[1]);
        *(_OWORD *)v42 = 0;
        v22 = std::make_shared<CLocationOverrideManager,>(v40);
        v42[0] = *(std::_Ref_count_base **)v22;
        v23 = *(std::_Ref_count_base **)(v22 + 8);
        v42[1] = v23;
        *(_QWORD *)v22 = 0;
        *(_QWORD *)(v22 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &xmmword_1801E43C8,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)xmmword_1801E43C8 + 8LL))(xmmword_1801E43C8) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            &MEMORY[0x1801E43D0] + 1,
            &xmmword_1801E43C8);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&xmmword_1801E43C8, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v23 )
          std::_Ref_count_base::_Decref(v23);
        *(_OWORD *)v42 = 0;
        v24 = std::make_shared<CUserOverrideVisitEngine,>(v40);
        v42[0] = *(std::_Ref_count_base **)v24;
        v25 = *(std::_Ref_count_base **)(v24 + 8);
        v42[1] = v25;
        *(_QWORD *)v24 = 0;
        *(_QWORD *)(v24 + 8) = 0;
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
          &qword_1801E43E8,
          v42);
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)qword_1801E43E8 + 8LL))(qword_1801E43E8) < 0 )
        {
          __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01_AEBV01__Z(
            (char *)&xmmword_1801E43F0 + 8,
            &qword_1801E43E8);
          *(_OWORD *)v42 = 0;
          std::shared_ptr<ILocationSignalManager>::operator=(&qword_1801E43E8, v42);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        if ( v25 )
          std::_Ref_count_base::_Decref(v25);
        dword_1801E4448 = 1;
        CMigrationHandler::HandleDeviceMigration();
        v40[0] = 0;
        CLocationComponentHelper::AutoCreateLocationComponentImpl<IGnssAdapter>(v26, v40);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v40);
        v40[0] = 0;
        LocationComponent = CLocationComponentHelper::AutoCreateLocationComponentImpl<IGeofenceManager>(v27, v40);
        if ( LocationComponent < 0 )
        {
          LODWORD(v37) = LocationComponent;
          wil::details::in1diag5::_Log_Hr(
            retaddr,
            (void *)0x168,
            (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
            "CLocationObjectManager::Start",
            "CLocationComponentHelper::AutoCreateLocationComponent(&pCreateSingleton)",
            v37,
            v38);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v40);
        v43 = 0;
        v30 = CLocationComponentHelper::AutoCreateLocationComponentImpl<ILocationPermissionManager>(v29, &v43);
        if ( v30 < 0 )
        {
          LODWORD(v37) = v30;
          wil::details::in1diag5::_Log_Hr(
            retaddr,
            (void *)0x16E,
            (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
            "CLocationObjectManager::Start",
            "CLocationComponentHelper::AutoCreateLocationComponent(&pLpm)",
            v37,
            v38);
        }
        if ( v43 )
        {
          v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 80LL))(v43);
          if ( v31 < 0 )
          {
            LODWORD(v37) = v31;
            wil::details::in1diag5::_Log_Hr(
              retaddr,
              (void *)0x171,
              (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
              "CLocationObjectManager::Start",
              "pLpm->RecalculateState()",
              v37,
              v38);
          }
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
        v40[0] = 0;
        if ( (int)LocationHelper::CreateLocationComponent<ILocationPalMisc>(v32, v40) >= 0 )
        {
          LODWORD(v43) = 256;
          if ( (*(int (__fastcall **)(std::_Ref_count_base *, __int64 *))(*(_QWORD *)v40[0] + 64LL))(v40[0], &v43) >= 0
            && (((_DWORD)v43 - 2) & 0xFFFFFFFD) == 0 )
          {
            v42[0] = 0;
            v34 = CLocationComponentHelper::AutoCreateLocationComponentImpl<ILocationCivicAddrAdapter>(v33, v42);
            if ( v34 < 0 )
            {
              LODWORD(v37) = v34;
              wil::details::in1diag5::_Log_Hr(
                retaddr,
                (void *)0x17F,
                (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
                "CLocationObjectManager::Start",
                "CLocationComponentHelper::AutoCreateLocationComponent(&pCivicAddrAdapter)",
                v37,
                v38);
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v42);
          }
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v40);
        if ( qword_1801E4308 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4308 + 16LL))(qword_1801E4308);
        if ( qword_1801E4288 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4288 + 16LL))(qword_1801E4288);
        if ( qword_1801E42C8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1801E42C8 + 16LL))(qword_1801E42C8);
        if ( qword_1801E4388 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4388 + 16LL))(qword_1801E4388);
        if ( qword_1801E4348 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4348 + 16LL))(qword_1801E4348);
        if ( qword_1801E4368 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1801E4368 + 16LL))(qword_1801E4368);
        if ( qword_1801E43A8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1801E43A8 + 16LL))(qword_1801E43A8);
        WakeAllConditionVariable(&ConditionVariable);
        goto LABEL_121;
      }
      v2 = "Leaving Start, but are in an unknown state";
      v3 = 431;
    }
    LODWORD(v37) = -2147418113;
    wil::details::in1diag5::Log_HrMsg(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
      "CLocationObjectManager::Start",
      "E_UNEXPECTED",
      v37,
      (__int64)v2,
      v39);
LABEL_121:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(CriticalSection);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag5::Return_CaughtException(
                           retaddr,
                           (void *)0x1B4,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
                           "CLocationObjectManager::Start",
                           v35,
                           v36);
  }
  return result;
}

```

## disassembly

```asm
0x180087f08  mov     r11, rsp
0x180087f0b  mov     [r11+8], rbx
0x180087f0f  mov     [r11+10h], rsi
0x180087f13  push    rdi
0x180087f14  sub     rsp, 90h
0x180087f1b  movaps  xmmword ptr [r11-18h], xmm6
0x180087f20  mov     rax, cs:__security_cookie
0x180087f27  xor     rax, rsp
0x180087f2a  mov     [rsp+98h+var_20], rax
0x180087f2f  xor     edi, edi
0x180087f31  mov     [r11-48h], rdi
0x180087f35  lea     rdx, stru_1801E4420
0x180087f3c  lea     rcx, [r11-48h]
0x180087f40  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180087f45  nop
0x180087f46  mov     dword ptr [rsp+98h+var_28], edi
0x180087f4a  lea     r9, [rsp+98h+var_28]
0x180087f4f  xor     r8d, r8d
0x180087f52  lea     rdx, aHlkmodeenabled; "HlkModeEnabled"
0x180087f59  mov     ecx, 200h
0x180087f5e  call    ?GetSettingValueDWORD@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEBGKPEAK@Z; LocationRegistryHelper::GetSettingValueDWORD(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ushort const *,ulong,ulong *)
0x180087f63  test    eax, eax
0x180087f65  js      short loc_180087FBF
0x180087f67  cmp     dword ptr [rsp+98h+var_28], 1
0x180087f6c  jnz     short loc_180087FBF
0x180087f6e  mov     cs:dword_1801E4448, 4
0x180087f78  lea     rcx, [rsp+98h+CriticalSection]
0x180087f7d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180087f82  mov     eax, 80004004h
0x180087f87  jmp     loc_1800889DA
0x180087f8c  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180087f90  mov     rdx, [rsp+98h+CriticalSection]; CriticalSection
0x180087f95  lea     rcx, ConditionVariable; ConditionVariable
0x180087f9c  call    cs:__imp_SleepConditionVariableCS
0x180087fa2  test    eax, eax
0x180087fa4  jnz     short loc_180087FBF
0x180087fa6  mov     rbx, [rsp+98h]
0x180087fae  call    cs:__imp_GetLastError
0x180087fb4  cmp     eax, 5B4h
0x180087fb9  jnz     loc_180088A01
0x180087fbf  mov     ecx, cs:dword_1801E4448
0x180087fc5  cmp     ecx, 2
0x180087fc8  jz      short loc_180087F8C
0x180087fca  cmp     ecx, 1
0x180087fcd  jz      loc_1800889C8
0x180087fd3  cmp     ecx, 2
0x180087fd6  jnz     short loc_18008801D
0x180087fd8  lea     rax, aLeavingStartBu_0; "Leaving Start, but are in stopping stat"...
0x180087fdf  mov     edx, 116h; void *
0x180087fe4  mov     [rsp+98h+var_68], rax; __int64
0x180087fe9  mov     dword ptr [rsp+98h+var_70], 8000FFFFh; char *
0x180087ff1  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x180087ff8  lea     r8, aOnecoreuapDriv_64; "onecoreuap\\drivers\\mobilepc\\location"...
0x180087fff  lea     r9, aClocationobjec_0; "CLocationObjectManager::Start"
0x180088006  mov     [rsp+98h+var_78], rax; char *
0x18008800b  mov     rcx, [rsp+98h]; this
0x180088013  call    ?Log_HrMsg@in1diag5@details@wil@@YAJPEAXIPEBD11J1ZZ; wil::details::in1diag5::Log_HrMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x180088018  jmp     loc_1800889C8
0x18008801d  lea     eax, [rcx-3]
0x180088020  cmp     eax, 1
0x180088023  jbe     short loc_180088037
0x180088025  test    ecx, ecx
0x180088027  jz      short loc_180088037
0x180088029  lea     rax, aLeavingStartBu; "Leaving Start, but are in an unknown st"...
0x180088030  mov     edx, 1AFh
0x180088035  jmp     short loc_180087FE4
0x180088037  xorps   xmm0, xmm0
0x18008803a  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x18008803f  lea     rcx, [rsp+98h+var_58]
0x180088044  call    ??$make_shared@VCLocationUserInfoHelper@@$$V@std@@YA?AV?$shared_ptr@VCLocationUserInfoHelper@@@0@XZ; std::make_shared<CLocationUserInfoHelper,>(void)
0x180088049  mov     rcx, [rax]
0x18008804c  mov     [rsp+98h+var_38], rcx
0x180088051  mov     rbx, [rax+8]
0x180088055  mov     [rsp+98h+var_38+8], rbx
0x18008805a  mov     [rax], rdi
0x18008805d  mov     [rax+8], rdi
0x180088061  mov     rcx, [rsp+98h+var_58+8]; this
0x180088066  test    rcx, rcx
0x180088069  jz      short loc_180088070
0x18008806b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088070  lea     rdx, [rsp+98h+var_38]
0x180088075  lea     rsi, qword_1801E42A8
0x18008807c  mov     rcx, rsi
0x18008807f  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x180088084  mov     rcx, cs:qword_1801E42A8
0x18008808b  mov     rax, [rcx]
0x18008808e  mov     rax, [rax+8]
0x180088092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088097  test    eax, eax
0x180088099  jns     short loc_1800880D0
0x18008809b  mov     rdx, rsi
0x18008809e  lea     rcx, xmmword_1801E42B0+8
0x1800880a5  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x1800880aa  xorps   xmm0, xmm0
0x1800880ad  movdqu  xmmword ptr [rsp+98h+var_38], xmm0
0x1800880b3  lea     rdx, [rsp+98h+var_38]
0x1800880b8  mov     rcx, rsi
0x1800880bb  call    ??4?$shared_ptr@VILocationSignalManager@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ILocationSignalManager>::operator=(std::shared_ptr<ILocationSignalManager> &&)
0x1800880c0  mov     rcx, [rsp+98h+var_38+8]; this
0x1800880c5  test    rcx, rcx
0x1800880c8  jz      short loc_1800880D0
0x1800880ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800880cf  nop
0x1800880d0  test    rbx, rbx
0x1800880d3  jz      short loc_1800880DD
0x1800880d5  mov     rcx, rbx; this
0x1800880d8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800880dd  xorps   xmm0, xmm0
0x1800880e0  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x1800880e5  lea     rcx, [rsp+98h+var_58]
0x1800880ea  call    ??$make_shared@VCLocationActiveCollection@@$$V@std@@YA?AV?$shared_ptr@VCLocationActiveCollection@@@0@XZ; std::make_shared<CLocationActiveCollection,>(void)
0x1800880ef  mov     rcx, [rax]
0x1800880f2  mov     [rsp+98h+var_38], rcx
0x1800880f7  mov     rbx, [rax+8]
0x1800880fb  mov     [rsp+98h+var_38+8], rbx
0x180088100  mov     [rax], rdi
0x180088103  mov     [rax+8], rdi
0x180088107  mov     rcx, [rsp+98h+var_58+8]; this
0x18008810c  test    rcx, rcx
0x18008810f  jz      short loc_180088116
0x180088111  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088116  lea     rdx, [rsp+98h+var_38]
0x18008811b  lea     rsi, qword_1801E42C8
0x180088122  mov     rcx, rsi
0x180088125  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x18008812a  mov     rcx, cs:qword_1801E42C8
0x180088131  mov     rax, [rcx]
0x180088134  mov     rax, [rax+8]
0x180088138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008813d  test    eax, eax
0x18008813f  jns     short loc_180088176
0x180088141  mov     rdx, rsi
0x180088144  lea     rcx, xmmword_1801E42D0+8
0x18008814b  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x180088150  xorps   xmm0, xmm0
0x180088153  movdqu  xmmword ptr [rsp+98h+var_38], xmm0
0x180088159  lea     rdx, [rsp+98h+var_38]
0x18008815e  mov     rcx, rsi
0x180088161  call    ??4?$shared_ptr@VILocationSignalManager@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ILocationSignalManager>::operator=(std::shared_ptr<ILocationSignalManager> &&)
0x180088166  mov     rcx, [rsp+98h+var_38+8]; this
0x18008816b  test    rcx, rcx
0x18008816e  jz      short loc_180088176
0x180088170  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088175  nop
0x180088176  test    rbx, rbx
0x180088179  jz      short loc_180088183
0x18008817b  mov     rcx, rbx; this
0x18008817e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088183  xorps   xmm0, xmm0
0x180088186  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x18008818b  lea     rcx, [rsp+98h+var_58]
0x180088190  call    ??$make_shared@VCVisitsEngine@@$$V@std@@YA?AV?$shared_ptr@VCVisitsEngine@@@0@XZ; std::make_shared<CVisitsEngine,>(void)
0x180088195  mov     rcx, [rax]
0x180088198  mov     [rsp+98h+var_38], rcx
0x18008819d  mov     rbx, [rax+8]
0x1800881a1  mov     [rsp+98h+var_38+8], rbx
0x1800881a6  mov     [rax], rdi
0x1800881a9  mov     [rax+8], rdi
0x1800881ad  mov     rcx, [rsp+98h+var_58+8]; this
0x1800881b2  test    rcx, rcx
0x1800881b5  jz      short loc_1800881BC
0x1800881b7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800881bc  lea     rdx, [rsp+98h+var_38]
0x1800881c1  lea     rsi, qword_1801E4388
0x1800881c8  mov     rcx, rsi
0x1800881cb  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x1800881d0  mov     rcx, cs:qword_1801E4388
0x1800881d7  mov     rax, [rcx]
0x1800881da  mov     rax, [rax+8]
0x1800881de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800881e3  test    eax, eax
0x1800881e5  jns     short loc_18008821C
0x1800881e7  mov     rdx, rsi
0x1800881ea  lea     rcx, xmmword_1801E4390+8
0x1800881f1  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x1800881f6  xorps   xmm0, xmm0
0x1800881f9  movdqu  xmmword ptr [rsp+98h+var_38], xmm0
0x1800881ff  lea     rdx, [rsp+98h+var_38]
0x180088204  mov     rcx, rsi
0x180088207  call    ??4?$shared_ptr@VILocationSignalManager@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ILocationSignalManager>::operator=(std::shared_ptr<ILocationSignalManager> &&)
0x18008820c  mov     rcx, [rsp+98h+var_38+8]; this
0x180088211  test    rcx, rcx
0x180088214  jz      short loc_18008821C
0x180088216  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008821b  nop
0x18008821c  test    rbx, rbx
0x18008821f  jz      short loc_180088229
0x180088221  mov     rcx, rbx; this
0x180088224  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088229  xorps   xmm0, xmm0
0x18008822c  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x180088231  lea     rcx, [rsp+98h+var_58]
0x180088236  call    ??$make_shared@VCLocationConfiguration@@$$V@std@@YA?AV?$shared_ptr@VCLocationConfiguration@@@0@XZ; std::make_shared<CLocationConfiguration,>(void)
0x18008823b  mov     rcx, [rax]
0x18008823e  mov     [rsp+98h+var_38], rcx
0x180088243  mov     rbx, [rax+8]
0x180088247  mov     [rsp+98h+var_38+8], rbx
0x18008824c  mov     [rax], rdi
0x18008824f  mov     [rax+8], rdi
0x180088253  mov     rcx, [rsp+98h+var_58+8]; this
0x180088258  test    rcx, rcx
0x18008825b  jz      short loc_180088262
0x18008825d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088262  lea     rdx, [rsp+98h+var_38]
0x180088267  lea     rsi, qword_1801E4308
0x18008826e  mov     rcx, rsi
0x180088271  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x180088276  mov     rcx, cs:qword_1801E4308
0x18008827d  mov     rax, [rcx]
0x180088280  mov     rax, [rax+8]
0x180088284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088289  test    eax, eax
0x18008828b  jns     short loc_1800882C2
0x18008828d  mov     rdx, rsi
0x180088290  lea     rcx, xmmword_1801E4310+8
0x180088297  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x18008829c  xorps   xmm0, xmm0
0x18008829f  movdqu  xmmword ptr [rsp+98h+var_38], xmm0
0x1800882a5  lea     rdx, [rsp+98h+var_38]
0x1800882aa  mov     rcx, rsi
0x1800882ad  call    ??4?$shared_ptr@VILocationSignalManager@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ILocationSignalManager>::operator=(std::shared_ptr<ILocationSignalManager> &&)
0x1800882b2  mov     rcx, [rsp+98h+var_38+8]; this
0x1800882b7  test    rcx, rcx
0x1800882ba  jz      short loc_1800882C2
0x1800882bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800882c1  nop
0x1800882c2  test    rbx, rbx
0x1800882c5  jz      short loc_1800882CF
0x1800882c7  mov     rcx, rbx; this
0x1800882ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800882cf  xorps   xmm0, xmm0
0x1800882d2  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x1800882d7  lea     rcx, [rsp+98h+var_58]
0x1800882dc  call    ??$make_shared@VCLocationUploader@@$$V@std@@YA?AV?$shared_ptr@VCLocationUploader@@@0@XZ; std::make_shared<CLocationUploader,>(void)
0x1800882e1  mov     rcx, [rax]
0x1800882e4  mov     [rsp+98h+var_38], rcx
0x1800882e9  mov     rbx, [rax+8]
0x1800882ed  mov     [rsp+98h+var_38+8], rbx
0x1800882f2  mov     [rax], rdi
0x1800882f5  mov     [rax+8], rdi
0x1800882f9  mov     rcx, [rsp+98h+var_58+8]; this
0x1800882fe  test    rcx, rcx
0x180088301  jz      short loc_180088308
0x180088303  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088308  lea     rdx, [rsp+98h+var_38]
0x18008830d  lea     rsi, qword_1801E4288
0x180088314  mov     rcx, rsi
0x180088317  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x18008831c  mov     rcx, cs:qword_1801E4288
0x180088323  mov     rax, [rcx]
0x180088326  mov     rax, [rax+8]
0x18008832a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008832f  test    eax, eax
0x180088331  jns     short loc_180088368
0x180088333  mov     rdx, rsi
0x180088336  lea     rcx, xmmword_1801E4290+8
0x18008833d  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x180088342  xorps   xmm0, xmm0
0x180088345  movdqu  xmmword ptr [rsp+98h+var_38], xmm0
0x18008834b  lea     rdx, [rsp+98h+var_38]
0x180088350  mov     rcx, rsi
0x180088353  call    ??4?$shared_ptr@VILocationSignalManager@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ILocationSignalManager>::operator=(std::shared_ptr<ILocationSignalManager> &&)
0x180088358  mov     rcx, [rsp+98h+var_38+8]; this
0x18008835d  test    rcx, rcx
0x180088360  jz      short loc_180088368
0x180088362  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088367  nop
0x180088368  test    rbx, rbx
0x18008836b  jz      short loc_180088375
0x18008836d  mov     rcx, rbx; this
0x180088370  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088375  xorps   xmm0, xmm0
0x180088378  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x18008837d  lea     rcx, [rsp+98h+var_58]
0x180088382  call    ??$make_shared@VCLocationSavedPositions@@$$V@std@@YA?AV?$shared_ptr@VCLocationSavedPositions@@@0@XZ; std::make_shared<CLocationSavedPositions,>(void)
0x180088387  mov     rcx, [rax]
0x18008838a  mov     [rsp+98h+var_38], rcx
0x18008838f  mov     rbx, [rax+8]
0x180088393  mov     [rsp+98h+var_38+8], rbx
0x180088398  mov     [rax], rdi
0x18008839b  mov     [rax+8], rdi
0x18008839f  mov     rcx, [rsp+98h+var_58+8]; this
0x1800883a4  test    rcx, rcx
0x1800883a7  jz      short loc_1800883AE
0x1800883a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800883ae  lea     rdx, [rsp+98h+var_38]
0x1800883b3  lea     rsi, qword_1801E4328
0x1800883ba  mov     rcx, rsi
0x1800883bd  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x1800883c2  mov     rcx, cs:qword_1801E4328
0x1800883c9  mov     rax, [rcx]
0x1800883cc  mov     rax, [rax+8]
0x1800883d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800883d5  test    eax, eax
0x1800883d7  jns     short loc_18008840E
0x1800883d9  mov     rdx, rsi
0x1800883dc  lea     rcx, xmmword_1801E4330+8
0x1800883e3  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@AEBV01@@Z
0x1800883e8  xorps   xmm0, xmm0
0x1800883eb  movdqu  xmmword ptr [rsp+98h+var_38], xmm0
  ... truncated ...
```
