# CVisitsEngine::Finalize(void)

- ea: `0x18012aff0`
- end: `0x18012ba8b`
- name: `?Finalize@CVisitsEngine@@UEAAJXZ`
- size: `2715`
- prototype: `__int64 __fastcall(CVisitsEngine *__hidden this)`
- caller_count: `0`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c974`
- `0x180012398`
- `0x180019704`
- `0x18001bb40`
- `0x18001be08`
- `0x18001cca4`
- `0x180021450`
- `0x1800234ec`
- `0x180023cd4`
- `0x180023ebc`
- `0x1800240b4`
- `0x180024440`
- `0x1800244ac`
- `0x180027594`
- `0x1800277ec`
- `0x180028434`
- `0x180028f28`
- `0x18003a940`
- `0x18003b92c`
- `0x18003dda0`
- `0x180048374`
- `0x180066340`
- `0x18007d420`
- `0x180081638`
- `0x180081864`
- `0x180081f78`
- `0x180087f08`
- `0x1800894cc`
- `0x18009514c`
- `0x18009a388`
- `0x18009c310`
- `0x18009e9c0`
- `0x1800a2a4c`
- `0x1800a98c0`
- `0x1800cccc0`
- `0x1800e9238`
- `0x18012a0b0`
- `0x18012ad8c`
- `0x18012aff0`
- `0x18015e010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012b3db`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012b4ee`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012b592`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012b7e1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012b3db`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012b4ee`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012b592`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012b7e1`

## string_xrefs

- `0x18012b9ec`: `m_wifiCoarseMovementSubscription.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(coarseMovementWnfStateName), LocationHelper2::CreateWeakWnfCallback(weakFromThis, [this](const void* pBuffer, ULONG length) { if (length != sizeof(WIFICOARSEMOVEINFO) || pBuffer == nullptr) { return; } const auto* pWifiCoarseMoveInfo = static_cast<const WIFICOARSEMOVEINFO*>(pBuffer); m_commonData->put_WifiCoarseMoveData((PWIFICOARSEMOVEINFO)pWifiCoarseMoveInfo); OnEventHappened(VisitsExternalEvent::Interesti`
- `0x18012b29a`: `LocationSignalManagerHelper::CreateCoalescedFunction(interestingSignalsFn, coalesceWindowMs, fnCookie, registerFn)`
- `0x18012b971`: `wifiAdapter->get_CoarseMovementWNFEvent((PULONG64)&coarseMovementWnfStateName)`
- `0x18012b72c`: `LocationSignalManagerHelper::CreateCoalescedFunction(activeClientsFn, coalesceWindowMs, fnCookie, registerFn)`
- `0x18012b141`: `m_permissionChangeSubscription.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_LFS_CLIENT_RECALCULATE_PERMISSIONS), LocationHelper2::CreateWeakWnfCallback(weakFromThis, [this](const void* , ULONG ) { OnPermissionChange(); }))`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CVisitsEngine::Finalize(CVisitsEngine *this)
{
  CVisitsEngine *v1; // r14
  int VisitsCommonData; // ebx
  int CurrentGlobalPermission; // eax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  int v7; // eax
  std::_Ref_count_base *v8; // rsi
  unsigned __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // r12
  int v13; // eax
  _QWORD *v14; // r15
  _QWORD *v15; // r13
  __int64 v16; // r13
  __int64 v17; // r12
  __int64 v18; // r15
  __int64 v19; // r14
  __int64 v20; // rsi
  std::_Ref_count_base *v21; // rbx
  int v22; // edi
  int v23; // eax
  __int64 v24; // rbx
  _QWORD *v25; // rax
  _QWORD *v26; // rcx
  _QWORD *v27; // r8
  int v28; // edi
  int v29; // ebx
  int v30; // eax
  int v31; // r9d
  int DelayedCallback; // eax
  __int64 v33; // rbx
  _QWORD *v34; // rax
  _QWORD *v35; // rcx
  _QWORD *v36; // r8
  __int64 v37; // rbx
  __int64 v38; // rax
  _QWORD *v39; // rdi
  __int64 v40; // rbx
  _QWORD *v41; // rdx
  _QWORD *v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  int v46; // eax
  std::_Ref_count_base *v47; // r12
  __int64 v48; // rsi
  int v49; // edi
  int v50; // ebx
  int v51; // eax
  __int64 v52; // rbx
  _QWORD *v53; // rax
  _QWORD *v54; // rcx
  _QWORD *v55; // r8
  __int64 v56; // rax
  __int64 v57; // rbx
  __int64 v58; // rax
  int v59; // eax
  const char *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rax
  int v64; // eax
  wil::details *v66; // [rsp+28h] [rbp-D8h]
  int v67; // [rsp+30h] [rbp-D0h]
  __int64 v68; // [rsp+40h] [rbp-C0h]
  _BYTE *v69; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v70; // [rsp+58h] [rbp-A8h]
  __int64 v71; // [rsp+60h] [rbp-A0h] BYREF
  char *v72; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v73; // [rsp+70h] [rbp-90h]
  std::_Ref_count_base *v74[2]; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v75[2]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v76[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v77; // [rsp+A8h] [rbp-58h] BYREF
  CVisitsEngine *v78; // [rsp+B0h] [rbp-50h]
  _BYTE v79[64]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v80[64]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v81[64]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v82[64]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v83; // [rsp+1C0h] [rbp+C0h] BYREF
  std::_Ref_count_base *v84[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  void **v85; // [rsp+1E0h] [rbp+E0h] BYREF
  void (__fastcall *v86)(CVisitsEngine *__hidden); // [rsp+1E8h] [rbp+E8h]
  int v87; // [rsp+1F0h] [rbp+F0h]
  int v88; // [rsp+1F4h] [rbp+F4h]
  CVisitsEngine *v89; // [rsp+1F8h] [rbp+F8h]
  CVisitsEngine *v90; // [rsp+200h] [rbp+100h]
  void ***v91; // [rsp+218h] [rbp+118h]
  _BYTE *v92; // [rsp+220h] [rbp+120h] BYREF
  __int64 (__fastcall **v93)(); // [rsp+230h] [rbp+130h] BYREF
  CVisitsEngine *v94; // [rsp+238h] [rbp+138h]
  __int64 (__fastcall ***v95)(); // [rsp+268h] [rbp+168h]
  wil::details::in1diag5 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v1 = this;
  v78 = this;
  if ( (unsigned int)dword_1801DDF30 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_1801DDF30,
      (unsigned __int8 *)byte_1801B6185);
  v77 = 0;
  wil::EnterCriticalSection(&v77, (char *)v1 + 56);
  VisitsCommonData = CVisitsCommonData::CreateVisitsCommonData((char *)v1 + 40);
  if ( VisitsCommonData < 0 )
    goto LABEL_45;
  CurrentGlobalPermission = CLocationPrivileges::GetCurrentGlobalPermission((int *)v1 + 64);
  if ( CurrentGlobalPermission < 0
    || (*((_DWORD *)v1 + 65) = CVisitsEngine::GetCurrentClientProfile(v1),
        CurrentGlobalPermission = CVisitsEngine::RecalculateMonitoringState(v1, 0),
        CurrentGlobalPermission < 0) )
  {
    VisitsCommonData = CurrentGlobalPermission;
LABEL_45:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v77);
    return (unsigned int)VisitsCommonData;
  }
  *(_OWORD *)v76 = 0;
  v4 = std::enable_shared_from_this<CVisitsState>::shared_from_this((char *)v1 + 8, v75);
  std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v76, v4);
  if ( v75[1] )
    std::_Ref_count_base::_Decref(v75[1]);
  v93 = off_180167F88;
  v94 = v1;
  v95 = &v93;
  v5 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v84, v76);
  v6 = LocationHelper2::CreateWeakWnfCallback<CVisitsEngine>(v79, v5, &v93);
  v71 = WNF_LFS_CLIENT_RECALCULATE_PERMISSIONS;
  v7 = LocationWnfSubscribe_Impl::SubscribeToWnfState((char *)v1 + 160, &v71, v6);
  if ( v7 < 0 )
  {
    LODWORD(v66) = v7;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\visitsengine\\locationvisitsengine.cpp",
      "CVisitsEngine::Finalize",
      "m_permissionChangeSubscription.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_LFS_CLIENT_RECALCULATE_"
      "PERMISSIONS), LocationHelper2::CreateWeakWnfCallback(weakFromThis, [this](const void* , ULONG ) { OnPermissionChange(); }))",
      (const char *)v66,
      v67);
  }
  *(_OWORD *)v75 = 0;
  v71 = 0;
  wil::EnterCriticalSection(&v71, &stru_1801E4420);
  if ( !dword_1801E4448 )
    CLocationObjectManager::Start();
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v71);
  CLocationObjectManager::GetSignalMan(&CLocationObjectManager::s_instance, v75);
  *(_OWORD *)v84 = 0;
  std::weak_ptr<ILocationUIHandler>::lock(v75, v84);
  v8 = v84[0];
  if ( v84[0] )
  {
    v9 = (unsigned int)CVisitsEngine::Finalize_::_29_::_lambda_2_::operator()();
    v85 = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CVisitsEngine::*)(enum VisitsExternalEvent),CVisitsEngine *,enum VisitsExternalEvent>,void,>::`vftable';
    v86 = (void (__fastcall *)(CVisitsEngine *__hidden))&CVisitsEngine::OnEventHappened;
    v87 = 0;
    v88 = HIDWORD(v75[1]);
    LODWORD(v89) = 2;
    v90 = v1;
    v91 = &v85;
    v10 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v74, v76);
    LocationHelper2::CreateWeakCallback<CVisitsEngine>(v82, v10, &v85);
    v95 = 0;
    *(_OWORD *)v74 = 0;
    v11 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
            v79,
            v82);
    v12 = (unsigned int)v9;
    v69 = (_BYTE *)v9;
    v13 = LocationSignalManagerHelper::CreateCoalescedFunction(v11, (unsigned int)v9, v74, &v93);
    if ( v13 >= 0 )
    {
      v71 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v8 + 64LL))(v8);
      v16 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v8 + 56LL))(v8);
      v17 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v8 + 40LL))(v8);
      v18 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v8 + 48LL))(v8);
      v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v8 + 72LL))(v8);
      v20 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v8 + 80LL))(v8);
      v21 = v84[0];
      v22 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v84[0] + 104LL))(v84[0]);
      LODWORD(v21) = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v21 + 96LL))(v21);
      v23 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
              v79,
              &v93);
      v68 = v16;
      v15 = (_QWORD *)((char *)v78 + 464);
      LocationSignalManagerHelper::RegisterForMultipleSignals<SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>>(
        v23,
        (_DWORD)v78 + 464,
        (_DWORD)v21,
        v22,
        v20,
        v19,
        v18,
        v17,
        v68,
        v71);
      v1 = v78;
      v14 = (_QWORD *)((char *)v78 + 448);
      if ( *((_QWORD *)v78 + 57) == 0x7FFFFFFFFFFFFFFLL )
        std::_Xlength_error("list too long");
      v24 = *v14;
      v72 = (char *)v78 + 448;
      v73 = 0;
      v25 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
      std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(v25 + 2, v74);
      ++v14[1];
      v26 = *(_QWORD **)(v24 + 8);
      *v27 = v24;
      v27[1] = v26;
      v73 = 0;
      *(_QWORD *)(v24 + 8) = v27;
      *v26 = v27;
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>(&v72);
      v8 = v84[0];
      v12 = (unsigned __int64)v69;
    }
    else
    {
      LODWORD(v66) = v13;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\visitsengine\\locationvisitsengine.cpp",
        "CVisitsEngine::Finalize",
        "LocationSignalManagerHelper::CreateCoalescedFunction(interestingSignalsFn, coalesceWindowMs, fnCookie, registerFn)",
        (const char *)v66,
        v67);
      v14 = (_QWORD *)((char *)v1 + 448);
      v15 = (_QWORD *)((char *)v1 + 464);
    }
    v85 = (void **)off_180160D00;
    v91 = &v85;
    std::shared_ptr<CVisitsCommonData>::reset(v74);
    std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(&v93);
    v69 = v79;
    v28 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
            v79,
            &v85);
    v29 = *(_DWORD *)(*((_QWORD *)v1 + 5) + 8LL);
    v30 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
            v81,
            v82);
    DelayedCallback = LocationHelper2::CreateDelayedCallback(v30, v29, v28, v31, (__int64)v74, (__int64)&v93);
    if ( DelayedCallback < 0 )
    {
      LODWORD(v66) = DelayedCallback;
      wil::details::in1diag5::Log_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\visitsengine\\locationvisitsengine.cpp",
        "CVisitsEngine::Finalize",
        "hrInt",
        (const char *)v66,
        v67);
    }
    else
    {
      if ( v14[1] == 0x7FFFFFFFFFFFFFFLL )
        std::_Xlength_error("list too long");
      v33 = *v14;
      v69 = v14;
      v70 = 0;
      v34 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
      std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(v34 + 2, v74);
      ++v14[1];
      v35 = *(_QWORD **)(v33 + 8);
      *v36 = v33;
      v36[1] = v35;
      v70 = 0;
      *(_QWORD *)(v33 + 8) = v36;
      *v35 = v36;
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>(&v69);
      v37 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v8 + 144LL))(v8);
      v38 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
              v79,
              &v93);
      v39 = (_QWORD *)SignalValue<bool>::Register(v37, &v72, v38);
      if ( v15[1] == 0x7FFFFFFFFFFFFFFLL )
        std::_Xlength_error("list too long");
      v40 = *v15;
      v69 = v15;
      v70 = 0;
      v41 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
      v41[2] = 0;
      v41[3] = 0;
      v41[2] = *v39;
      v41[3] = v39[1];
      *v39 = 0;
      v39[1] = 0;
      ++v15[1];
      v42 = *(_QWORD **)(v40 + 8);
      *v41 = v40;
      v41[1] = v42;
      v70 = 0;
      *(_QWORD *)(v40 + 8) = v41;
      *v42 = v41;
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>(&v69);
      if ( v73 )
        std::_Ref_count_base::_Decref(v73);
    }
    std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(&v85);
    v85 = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CVisitsEngine::*)(void),CVisitsEngine *>,void,>::`vftable';
    v86 = CVisitsEngine::OnClientsUpdated;
    v87 = 0;
    v88 = HIDWORD(v75[1]);
    v89 = v1;
    v91 = &v85;
    v43 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(&v72, v76);
    LocationHelper2::CreateWeakCallback<CVisitsEngine>(v81, v43, &v85);
    std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
      v79,
      v81);
    v44 = std::function_long___cdecl_void__::function_long___cdecl_void____CVisitsEngine::Finalize_::_39_::_lambda_4__0_(
            v80,
            v79);
    ResettableTimer::BindCallback((char *)v1 + 304, v44);
    std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(v79);
    std::shared_ptr<CVisitsCommonData>::reset(v74);
    std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(&v93);
    v45 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
            v80,
            v81);
    v46 = LocationSignalManagerHelper::CreateCoalescedFunction(v45, v12, v74, &v93);
    if ( v46 >= 0 )
    {
      v48 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v8 + 168LL))(v8);
      v47 = v84[0];
      v49 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v84[0] + 160LL))(v84[0]);
      v50 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v47 + 152LL))(v47);
      v51 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
              v80,
              &v93);
      LocationSignalManagerHelper::RegisterForMultipleSignals<SignalValue<bool>,SignalValue<bool>,SignalValue<bool>>(
        v51,
        (_DWORD)v15,
        v50,
        v49,
        v48);
      if ( v14[1] == 0x7FFFFFFFFFFFFFFLL )
        std::_Xlength_error("list too long");
      v52 = *v14;
      v69 = v14;
      v70 = 0;
      v53 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
      std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(v53 + 2, v74);
      ++v14[1];
      v54 = *(_QWORD **)(v52 + 8);
      *v55 = v52;
      v55[1] = v54;
      v70 = 0;
      *(_QWORD *)(v52 + 8) = v55;
      *v54 = v55;
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>(&v69);
    }
    else
    {
      LODWORD(v66) = v46;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\visitsengine\\locationvisitsengine.cpp",
        "CVisitsEngine::Finalize",
        "LocationSignalManagerHelper::CreateCoalescedFunction(activeClientsFn, coalesceWindowMs, fnCookie, registerFn)",
        (const char *)v66,
        v67);
      v47 = v84[0];
    }
    std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(v81);
    v85 = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CVisitsEngine::*)(void),CVisitsEngine *>,void,>::`vftable';
    v86 = CVisitsEngine::OnAirplaneModeUpdated;
    v87 = 0;
    v88 = HIDWORD(v75[1]);
    v89 = v1;
    v91 = &v85;
    v56 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(&v72, v76);
    LocationHelper2::CreateWeakCallback<CVisitsEngine>(v79, v56, &v85);
    v57 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v47 + 176LL))(v47);
    v58 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
            v80,
            v79);
    LocationSignalManagerHelper::RegisterForMultipleSignals<SignalValue<bool>,>(v58, v15, v57);
    std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(v79);
    if ( v74[1] )
      std::_Ref_count_base::_Decref(v74[1]);
    std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(&v93);
    std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(v82);
  }
  if ( v84[1] )
    std::_Ref_count_base::_Decref(v84[1]);
  if ( v75[1] )
    std::_Ref_count_base::_Decwref(v75[1]);
  v83 = 0;
  LocationHelper::CreateLocationComponent(0x21u, (__int64)&GUID_cc3501e4_5c29_4d65_87d0_051859a9706c, (__int64)&v83);
  v92 = 0;
  v59 = (*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v83 + 80LL))(v83, &v92);
  VisitsCommonData = v59;
  if ( v59 < 0 )
  {
    LODWORD(v66) = v59;
    v60 = "wifiAdapter->get_CoarseMovementWNFEvent((PULONG64)&coarseMovementWnfStateName)";
    v61 = 198;
    goto LABEL_43;
  }
  v93 = off_180160D30;
  v94 = v1;
  v95 = &v93;
  v62 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v75, v76);
  v63 = LocationHelper2::CreateWeakWnfCallback<CVisitsEngine>(v80, v62, &v93);
  v69 = v92;
  v64 = LocationWnfSubscribe_Impl::SubscribeToWnfState((char *)v1 + 208, &v69, v63);
  VisitsCommonData = v64;
  if ( v64 < 0 )
  {
    LODWORD(v66) = v64;
    v60 = "m_wifiCoarseMovementSubscription.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(coarseMovementWnfStat"
          "eName), LocationHelper2::CreateWeakWnfCallback(weakFromThis, [this](const void* pBuffer, ULONG length) { if (l"
          "ength != sizeof(WIFICOARSEMOVEINFO) || pBuffer == nullptr) { return; } const auto* pWifiCoarseMoveInfo = stati"
          "c_cast<const WIFICOARSEMOVEINFO*>(pBuffer); m_commonData->put_WifiCoarseMoveData((PWIFICOARSEMOVEINFO)pWifiCoa"
          "rseMoveInfo); OnEventHappened(VisitsExternalEvent::InterestingSignal); }))";
    v61 = 213;
LABEL_43:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v61,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\visitsengine\\locationvisitsengine.cpp",
      "CVisitsEngine::Finalize",
      v60,
      v66,
      v67);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v83);
    if ( v76[1] )
      std::_Ref_count_base::_Decwref(v76[1]);
    goto LABEL_45;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v83);
  if ( v76[1] )
    std::_Ref_count_base::_Decwref(v76[1]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v77);
  return 0;
}

```

## disassembly

```asm
0x18012aff0  push    rbp
0x18012aff2  push    rbx
0x18012aff3  push    rsi
0x18012aff4  push    rdi
0x18012aff5  push    r12
0x18012aff7  push    r13
0x18012aff9  push    r14
0x18012affb  push    r15
0x18012affd  lea     rbp, [rsp-188h]
0x18012b005  sub     rsp, 288h
0x18012b00c  mov     rax, cs:__security_cookie
0x18012b013  xor     rax, rsp
0x18012b016  mov     [rbp+1C0h+var_50], rax
0x18012b01d  mov     r14, rcx
0x18012b020  mov     [rbp+1C0h+var_210], rcx
0x18012b024  mov     eax, cs:dword_1801DDF30
0x18012b02a  cmp     eax, 5
0x18012b02d  jbe     short loc_18012B042
0x18012b02f  lea     rdx, byte_1801B6185
0x18012b036  lea     rcx, dword_1801DDF30
0x18012b03d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18012b042  xor     edi, edi
0x18012b044  mov     [rbp+1C0h+var_218], rdi
0x18012b048  lea     rdx, [r14+38h]
0x18012b04c  lea     rcx, [rbp+1C0h+var_218]
0x18012b050  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18012b055  nop
0x18012b056  lea     rcx, [r14+28h]
0x18012b05a  call    ?CreateVisitsCommonData@CVisitsCommonData@@SAJAEAV?$shared_ptr@VCVisitsCommonData@@@std@@@Z; CVisitsCommonData::CreateVisitsCommonData(std::shared_ptr<CVisitsCommonData> &)
0x18012b05f  mov     ebx, eax
0x18012b061  test    eax, eax
0x18012b063  js      loc_18012BA34
0x18012b069  lea     rcx, [r14+100h]; int *
0x18012b070  call    ?GetCurrentGlobalPermission@CLocationPrivileges@@SAJPEAH@Z; CLocationPrivileges::GetCurrentGlobalPermission(int *)
0x18012b075  test    eax, eax
0x18012b077  jns     short loc_18012B080
0x18012b079  mov     ebx, eax
0x18012b07b  jmp     loc_18012BA34
0x18012b080  mov     rcx, r14
0x18012b083  call    ?GetCurrentClientProfile@CVisitsEngine@@AEAA?AW4VisitClientProfile@@XZ; CVisitsEngine::GetCurrentClientProfile(void)
0x18012b088  mov     [r14+104h], eax
0x18012b08f  xor     edx, edx; bool
0x18012b091  mov     rcx, r14; this
0x18012b094  call    ?RecalculateMonitoringState@CVisitsEngine@@AEAAJ_N@Z; CVisitsEngine::RecalculateMonitoringState(bool)
0x18012b099  test    eax, eax
0x18012b09b  js      short loc_18012B079
0x18012b09d  xorps   xmm0, xmm0
0x18012b0a0  movups  xmmword ptr [rbp+1C0h+var_228], xmm0
0x18012b0a4  lea     rcx, [r14+8]
0x18012b0a8  lea     rdx, [rbp+1C0h+var_238]
0x18012b0ac  call    ?shared_from_this@?$enable_shared_from_this@VCVisitsState@@@std@@QEAA?AV?$shared_ptr@VCVisitsState@@@2@XZ; std::enable_shared_from_this<CVisitsState>::shared_from_this(void)
0x18012b0b1  mov     rdx, rax
0x18012b0b4  lea     rcx, [rbp+1C0h+var_228]
0x18012b0b8  call    ??0?$weak_ptr@USignalState@?$SignalValue@_N@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(std::weak_ptr<SignalValue<bool>::SignalState> const &)
0x18012b0bd  nop
0x18012b0be  mov     rcx, [rbp+1C0h+var_238+8]; this
0x18012b0c2  test    rcx, rcx
0x18012b0c5  jz      short loc_18012B0CC
0x18012b0c7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012b0cc  lea     rax, off_180167F88
0x18012b0d3  mov     [rbp+1C0h+var_90], rax
0x18012b0da  mov     [rbp+1C0h+var_88], r14
0x18012b0e1  lea     rax, [rbp+1C0h+var_90]
0x18012b0e8  mov     [rbp+1C0h+var_58], rax
0x18012b0ef  lea     rdx, [rbp+1C0h+var_228]
0x18012b0f3  lea     rcx, [rbp+1C0h+var_F8]
0x18012b0fa  call    ??0?$weak_ptr@USignalState@?$SignalValue@_N@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(std::weak_ptr<SignalValue<bool>::SignalState> const &)
0x18012b0ff  lea     r8, [rbp+1C0h+var_90]
0x18012b106  mov     rdx, rax
0x18012b109  lea     rcx, [rbp+1C0h+var_200]
0x18012b10d  call    ??$CreateWeakWnfCallback@VCVisitsEngine@@@LocationHelper2@@SA?AV?$function@$$A6AXPEBXK@Z@std@@V?$weak_ptr@VCVisitsEngine@@@2@V12@@Z; LocationHelper2::CreateWeakWnfCallback<CVisitsEngine>(std::weak_ptr<CVisitsEngine>,std::function<void (void const *,ulong)>)
0x18012b112  mov     rcx, cs:WNF_LFS_CLIENT_RECALCULATE_PERMISSIONS
0x18012b119  mov     [rsp+2C0h+var_260], rcx
0x18012b11e  lea     rcx, [r14+0A0h]
0x18012b125  mov     r8, rax
0x18012b128  lea     rdx, [rsp+2C0h+var_260]
0x18012b12d  call    ?SubscribeToWnfState@LocationWnfSubscribe_Impl@@QEAAJAEBULOC_WNF_STATE_NAME@@V?$function@$$A6AXPEBXK@Z@std@@@Z; LocationWnfSubscribe_Impl::SubscribeToWnfState(LOC_WNF_STATE_NAME const &,std::function<void (void const *,ulong)>)
0x18012b132  mov     rcx, [rbp+1C8h]; this
0x18012b139  test    eax, eax
0x18012b13b  jns     short loc_18012B165
0x18012b13d  mov     dword ptr [rsp+2C0h+var_298], eax; char *
0x18012b141  lea     rax, aMPermissioncha; "m_permissionChangeSubscription.Subscrib"...
0x18012b148  mov     [rsp+2C0h+var_2A0], rax; char *
0x18012b14d  lea     r9, aCvisitsengineF; "CVisitsEngine::Finalize"
0x18012b154  lea     r8, aOnecoreuapDriv_69; "onecoreuap\\drivers\\mobilepc\\location"...
0x18012b15b  mov     edx, 54h ; 'T'; void *
0x18012b160  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18012b165  xorps   xmm0, xmm0
0x18012b168  movups  xmmword ptr [rbp+1C0h+var_238], xmm0
0x18012b16c  mov     [rsp+2C0h+var_260], rdi
0x18012b171  lea     rdx, stru_1801E4420
0x18012b178  lea     rcx, [rsp+2C0h+var_260]
0x18012b17d  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18012b182  nop
0x18012b183  cmp     cs:dword_1801E4448, edi
0x18012b189  jnz     short loc_18012B191
0x18012b18b  call    ?Start@CLocationObjectManager@@KAJXZ; CLocationObjectManager::Start(void)
0x18012b190  nop
0x18012b191  lea     rcx, [rsp+2C0h+var_260]
0x18012b196  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18012b19b  lea     rdx, [rbp+1C0h+var_238]
0x18012b19f  lea     rcx, ?s_instance@CLocationObjectManager@@1V1@A; CLocationObjectManager CLocationObjectManager::s_instance
0x18012b1a6  call    ?GetSignalMan@CLocationObjectManager@@QEBA?AV?$weak_ptr@VILocationSignalManager@@@std@@XZ; CLocationObjectManager::GetSignalMan(void)
0x18012b1ab  nop
0x18012b1ac  xorps   xmm0, xmm0
0x18012b1af  movups  xmmword ptr [rbp+1C0h+var_F8], xmm0
0x18012b1b6  lea     rdx, [rbp+1C0h+var_F8]
0x18012b1bd  lea     rcx, [rbp+1C0h+var_238]
0x18012b1c1  call    ?lock@?$weak_ptr@VILocationUIHandler@@@std@@QEBA?AV?$shared_ptr@VILocationUIHandler@@@2@XZ; std::weak_ptr<ILocationUIHandler>::lock(void)
0x18012b1c6  nop
0x18012b1c7  mov     rsi, [rbp+1C0h+var_F8]
0x18012b1ce  test    rsi, rsi
0x18012b1d1  jz      loc_18012B907
0x18012b1d7  call    _CVisitsEngine__Finalize____29____lambda_2___operator__
0x18012b1dc  mov     ebx, eax
0x18012b1de  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8CVisitsEngine@@EAAXW4VisitsExternalEvent@@@ZPEAV3@W44@@std@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CVisitsEngine::*)(VisitsExternalEvent),CVisitsEngine *,VisitsExternalEvent>,void,>::`vftable'
0x18012b1e5  mov     [rbp+1C0h+var_E0], rax
0x18012b1ec  lea     rax, ?OnEventHappened@CVisitsEngine@@AEAAXW4VisitsExternalEvent@@@Z; CVisitsEngine::OnEventHappened(VisitsExternalEvent)
0x18012b1f3  mov     [rbp+1C0h+var_D8], rax
0x18012b1fa  mov     [rbp+1C0h+var_D0], edi
0x18012b200  mov     ecx, dword ptr [rbp+1C0h+var_238+0Ch]
0x18012b203  mov     [rbp+1C0h+var_CC], ecx
0x18012b209  mov     dword ptr [rbp+1C0h+var_C8], 2
0x18012b213  mov     [rbp+1C0h+var_C0], r14
0x18012b21a  lea     rax, [rbp+1C0h+var_E0]
0x18012b221  mov     [rbp+1C0h+var_A8], rax
0x18012b228  lea     rdx, [rbp+1C0h+var_228]
0x18012b22c  lea     rcx, [rsp+2C0h+var_248]
0x18012b231  call    ??0?$weak_ptr@USignalState@?$SignalValue@_N@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(std::weak_ptr<SignalValue<bool>::SignalState> const &)
0x18012b236  lea     r8, [rbp+1C0h+var_E0]
0x18012b23d  mov     rdx, rax
0x18012b240  lea     rcx, [rbp+1C0h+var_140]
0x18012b247  call    ??$CreateWeakCallback@VCVisitsEngine@@@LocationHelper2@@SA?AV?$function@$$A6AXXZ@std@@V?$weak_ptr@VCVisitsEngine@@@2@V12@@Z; LocationHelper2::CreateWeakCallback<CVisitsEngine>(std::weak_ptr<CVisitsEngine>,std::function<void (void)>)
0x18012b24c  nop
0x18012b24d  mov     [rbp+1C0h+var_58], rdi
0x18012b254  xorps   xmm1, xmm1
0x18012b257  movdqu  xmmword ptr [rsp+2C0h+var_248], xmm1
0x18012b25d  lea     rdx, [rbp+1C0h+var_140]
0x18012b264  lea     rcx, [rbp+1C0h+var_200]
0x18012b268  call    ??0?$function@$$A6AXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@Z@std@@QEAA@AEBV01@@Z; std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>(std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)> const &)
0x18012b26d  mov     r12d, ebx
0x18012b270  mov     [rsp+2C0h+var_270], rbx
0x18012b275  lea     r9, [rbp+1C0h+var_90]
0x18012b27c  lea     r8, [rsp+2C0h+var_248]
0x18012b281  mov     edx, ebx
0x18012b283  mov     rcx, rax
0x18012b286  call    ?CreateCoalescedFunction@LocationSignalManagerHelper@@SAJV?$function@$$A6AXXZ@std@@_KAEAV?$shared_ptr@VLocationCallOnExit@@@3@AEAV23@@Z; LocationSignalManagerHelper::CreateCoalescedFunction(std::function<void (void)>,unsigned __int64,std::shared_ptr<LocationCallOnExit> &,std::function<void (void)> &)
0x18012b28b  mov     rcx, [rbp+1C8h]; this
0x18012b292  test    eax, eax
0x18012b294  jns     short loc_18012B2D1
0x18012b296  mov     dword ptr [rsp+2C0h+var_298], eax; char *
0x18012b29a  lea     rax, aLocationsignal_0; "LocationSignalManagerHelper::CreateCoal"...
0x18012b2a1  mov     [rsp+2C0h+var_2A0], rax; char *
0x18012b2a6  lea     r9, aCvisitsengineF; "CVisitsEngine::Finalize"
0x18012b2ad  lea     r8, aOnecoreuapDriv_69; "onecoreuap\\drivers\\mobilepc\\location"...
0x18012b2b4  mov     edx, 68h ; 'h'; void *
0x18012b2b9  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18012b2be  lea     r15, [r14+1C0h]
0x18012b2c5  lea     r13, [r14+1D0h]
0x18012b2cc  jmp     loc_18012B444
0x18012b2d1  mov     rax, [rsi]
0x18012b2d4  mov     rcx, rsi
0x18012b2d7  mov     rax, [rax+40h]
0x18012b2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b2e0  mov     [rsp+2C0h+var_260], rax
0x18012b2e5  mov     rcx, [rsi]
0x18012b2e8  mov     rax, [rcx+38h]
0x18012b2ec  mov     rcx, rsi
0x18012b2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b2f4  mov     r13, rax
0x18012b2f7  mov     rcx, [rsi]
0x18012b2fa  mov     rax, [rcx+28h]
0x18012b2fe  mov     rcx, rsi
0x18012b301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b306  mov     r12, rax
0x18012b309  mov     rcx, [rsi]
0x18012b30c  mov     rax, [rcx+30h]
0x18012b310  mov     rcx, rsi
0x18012b313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b318  mov     r15, rax
0x18012b31b  mov     rcx, [rsi]
0x18012b31e  mov     rax, [rcx+48h]
0x18012b322  mov     rcx, rsi
0x18012b325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b32a  mov     r14, rax
0x18012b32d  mov     rcx, [rsi]
0x18012b330  mov     rax, [rcx+50h]
0x18012b334  mov     rcx, rsi
0x18012b337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b33c  mov     rsi, rax
0x18012b33f  mov     rbx, [rbp+1C0h+var_F8]
0x18012b346  mov     rcx, [rbx]
0x18012b349  mov     rax, [rcx+68h]
0x18012b34d  mov     rcx, rbx
0x18012b350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b355  mov     rdi, rax
0x18012b358  mov     rcx, [rbx]
0x18012b35b  mov     rax, [rcx+60h]
0x18012b35f  mov     rcx, rbx
0x18012b362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b367  mov     rbx, rax
0x18012b36a  lea     rdx, [rbp+1C0h+var_90]
0x18012b371  lea     rcx, [rbp+1C0h+var_200]
0x18012b375  call    ??0?$function@$$A6AXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@Z@std@@QEAA@AEBV01@@Z; std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>(std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)> const &)
0x18012b37a  mov     rdx, [rbp+1C0h+var_210]
0x18012b37e  add     rdx, 1D0h
0x18012b385  mov     rcx, [rsp+2C0h+var_260]
0x18012b38a  mov     [rsp+2C0h+var_278], rcx
0x18012b38f  mov     [rsp+2C0h+var_280], r13
0x18012b394  mov     [rsp+2C0h+var_288], r12
0x18012b399  mov     qword ptr [rsp+2C0h+var_290], r15; int
0x18012b39e  mov     [rsp+2C0h+var_298], r14
0x18012b3a3  mov     [rsp+2C0h+var_2A0], rsi
0x18012b3a8  mov     r9, rdi
0x18012b3ab  mov     r8, rbx
0x18012b3ae  mov     r13, rdx
0x18012b3b1  mov     rcx, rax
0x18012b3b4  call    ??$RegisterForMultipleSignals@V?$SignalValue@_N@@V1@V1@V1@V1@V1@V1@V1@@LocationSignalManagerHelper@@SAXV?$function@$$A6AXXZ@std@@AEAV?$list@V?$shared_ptr@VLocationCallOnExit@@@std@@V?$allocator@V?$shared_ptr@VLocationCallOnExit@@@std@@@2@@2@AEAV?$SignalValue@_N@@2222222@Z; LocationSignalManagerHelper::RegisterForMultipleSignals<SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>,SignalValue<bool>>(std::function<void (void)>,std::list<std::shared_ptr<LocationCallOnExit>> &,SignalValue<bool> &,SignalValue<bool> &,SignalValue<bool> &,SignalValue<bool> &,SignalValue<bool> &,SignalValue<bool> &,SignalValue<bool> &,SignalValue<bool> &)
0x18012b3b9  mov     r14, [rbp+1C0h+var_210]
0x18012b3bd  lea     r15, [r14+1C0h]
0x18012b3c4  mov     rax, 7FFFFFFFFFFFFFFh
0x18012b3ce  cmp     [r15+8], rax
0x18012b3d2  jnz     short loc_18012B3E2
0x18012b3d4  lea     rcx, aListTooLong; "list too long"
0x18012b3db  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18012b3e2  mov     rbx, [r15]
0x18012b3e5  mov     [rsp+2C0h+var_258], r15
0x18012b3ea  mov     [rsp+2C0h+var_250], 0
0x18012b3f3  mov     ecx, 20h ; ' '
0x18012b3f8  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18012b3fd  mov     r8, rax
0x18012b400  lea     rcx, [rax+10h]
0x18012b404  lea     rdx, [rsp+2C0h+var_248]
0x18012b409  call    ??0?$shared_ptr@UGEOFENCE_DISTANCE@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(std::shared_ptr<GEOFENCE_DISTANCE> const &)
0x18012b40e  nop
0x18012b40f  inc     qword ptr [r15+8]
0x18012b413  mov     rcx, [rbx+8]
0x18012b417  mov     [r8], rbx
0x18012b41a  mov     [r8+8], rcx
0x18012b41e  mov     [rsp+2C0h+var_250], 0
0x18012b427  mov     [rbx+8], r8
0x18012b42b  mov     [rcx], r8
0x18012b42e  lea     rcx, [rsp+2C0h+var_258]
0x18012b433  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@VILocationSingletonComponent@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ILocationSingletonComponent>,void *>>>(void)
0x18012b438  mov     rsi, [rbp+1C0h+var_F8]
0x18012b43f  mov     r12, [rsp+2C0h+var_270]
0x18012b444  lea     rax, off_180160D00
0x18012b44b  mov     [rbp+1C0h+var_E0], rax
0x18012b452  lea     rax, [rbp+1C0h+var_E0]
0x18012b459  mov     [rbp+1C0h+var_A8], rax
0x18012b460  lea     rcx, [rsp+2C0h+var_248]
0x18012b465  call    ?reset@?$shared_ptr@VCVisitsCommonData@@@std@@QEAAXXZ; std::shared_ptr<CVisitsCommonData>::reset(void)
0x18012b46a  lea     rcx, [rbp+1C0h+var_90]
0x18012b471  call    ?_Tidy@?$_Func_class@XW4ActivityType@CLocationActivityDetector@@_N@std@@IEAAXXZ; std::_Func_class<void,CLocationActivityDetector::ActivityType,bool>::_Tidy(void)
0x18012b476  lea     rax, [rbp+1C0h+var_200]
0x18012b47a  mov     [rsp+2C0h+var_270], rax
0x18012b47f  lea     rdx, [rbp+1C0h+var_E0]
0x18012b486  lea     rcx, [rbp+1C0h+var_200]
0x18012b48a  call    ??0?$function@$$A6AXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@Z@std@@QEAA@AEBV01@@Z; std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>(std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)> const &)
0x18012b48f  mov     rdi, rax
0x18012b492  mov     rcx, [r14+28h]
0x18012b496  mov     ebx, [rcx+8]
0x18012b499  lea     rdx, [rbp+1C0h+var_140]
0x18012b4a0  lea     rcx, [rbp+1C0h+var_180]
0x18012b4a4  call    ??0?$function@$$A6AXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@Z@std@@QEAA@AEBV01@@Z; std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>(std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)> const &)
0x18012b4a9  nop
0x18012b4aa  lea     rcx, [rbp+1C0h+var_90]
0x18012b4b1  mov     [rsp+2C0h+var_298], rcx
0x18012b4b6  lea     rcx, [rsp+2C0h+var_248]
0x18012b4bb  mov     [rsp+2C0h+var_2A0], rcx
0x18012b4c0  mov     r8, rdi
0x18012b4c3  mov     edx, ebx
0x18012b4c5  mov     rcx, rax
0x18012b4c8  call    ?CreateDelayedCallback@LocationHelper2@@SAJV?$function@$$A6AXXZ@std@@KV?$function@$$A6A_NXZ@3@_NAEAV?$shared_ptr@VLocationCallOnExit@@@3@AEAV23@@Z; LocationHelper2::CreateDelayedCallback(std::function<void (void)>,ulong,std::function<bool (void)>,bool,std::shared_ptr<LocationCallOnExit> &,std::function<void (void)> &)
0x18012b4cd  xor     edi, edi
0x18012b4cf  test    eax, eax
0x18012b4d1  js      loc_18012B611
0x18012b4d7  mov     rax, 7FFFFFFFFFFFFFFh
0x18012b4e1  cmp     [r15+8], rax
0x18012b4e5  jnz     short loc_18012B4F5
0x18012b4e7  lea     rcx, aListTooLong; "list too long"
0x18012b4ee  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18012b4f5  mov     rbx, [r15]
0x18012b4f8  mov     [rsp+2C0h+var_270], r15
0x18012b4fd  mov     [rsp+2C0h+var_268], rdi
0x18012b502  mov     ecx, 20h ; ' '
0x18012b507  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18012b50c  mov     r8, rax
0x18012b50f  lea     rcx, [rax+10h]
0x18012b513  lea     rdx, [rsp+2C0h+var_248]
0x18012b518  call    ??0?$shared_ptr@UGEOFENCE_DISTANCE@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(std::shared_ptr<GEOFENCE_DISTANCE> const &)
0x18012b51d  nop
0x18012b51e  inc     qword ptr [r15+8]
0x18012b522  mov     rcx, [rbx+8]
0x18012b526  mov     [r8], rbx
0x18012b529  mov     [r8+8], rcx
0x18012b52d  mov     [rsp+2C0h+var_268], rdi
0x18012b532  mov     [rbx+8], r8
0x18012b536  mov     [rcx], r8
0x18012b539  lea     rcx, [rsp+2C0h+var_270]
  ... truncated ...
```
