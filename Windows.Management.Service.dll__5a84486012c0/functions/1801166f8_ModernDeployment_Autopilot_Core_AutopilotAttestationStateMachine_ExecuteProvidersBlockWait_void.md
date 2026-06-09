# ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait(void)

- ea: `0x1801166f8`
- end: `0x18011741f`
- name: `?ExecuteProvidersBlockWait@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJXZ`
- size: `3367`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180117750`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006defc`
- `0x18006df20`
- `0x18006e0a8`
- `0x18006e0c8`
- `0x18007748c`
- `0x1800801fc`
- `0x1800806b0`
- `0x1800a00c4`
- `0x18010839c`
- `0x180112560`
- `0x180115304`
- `0x180115bbc`
- `0x180116090`
- `0x1801166f8`
- `0x180117428`
- `0x180118938`
- `0x18011af64`
- `0x18011b1f8`
- `0x18011b510`
- `0x18011bca0`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180116816`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180116a65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180116c2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180116dba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180116816`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180116a65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180116c2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180116dba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011674d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801170ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011735a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011674d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801170ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011735a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801167c1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801167c1`

## string_xrefs

- `0x18011677c`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011684d`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x1801168c5`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x180116931`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x180116992`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x1801173af`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x1801173de`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait(
        RTL_SRWLOCK *this)
{
  bool v2; // r15
  PVOID Ptr; // rax
  int v5; // r12d
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  int AttestationPhaseList; // eax
  unsigned int v11; // ebx
  unsigned int *v12; // r13
  Concurrency::cancellation_token *token; // rax
  bool is_canceled; // bl
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // ebx
  RTL_SRWLOCK *v24; // rbx
  int v25; // r13d
  unsigned int v26; // ecx
  int v27; // eax
  int v28; // ecx
  _QWORD *v29; // r13
  _QWORD *v30; // rax
  Concurrency::cancellation_token *v31; // rax
  bool v32; // bl
  __int64 v33; // rcx
  __int64 v34; // r8
  int v35; // eax
  int v36; // eax
  int v37; // eax
  unsigned int v38; // ebx
  int v39; // eax
  unsigned int v40; // ebx
  int v41; // eax
  unsigned int v42; // ebx
  int v43; // eax
  int v44; // ecx
  unsigned int v45; // ebx
  __int64 *v46; // rdx
  unsigned int v47; // r15d
  RTL_SRWLOCK *v48; // rbx
  _QWORD *v49; // rdx
  int v50; // eax
  unsigned int v51; // ebx
  int v52; // eax
  unsigned int v53; // ebx
  int v54; // eax
  unsigned int v55; // ebx
  int v56; // eax
  int v57; // eax
  unsigned int v58; // ebx
  int v59; // [rsp+20h] [rbp-158h]
  bool v60; // [rsp+50h] [rbp-128h] BYREF
  RTL_SRWLOCK *v61; // [rsp+58h] [rbp-120h] BYREF
  struct ModernDeployment::Autopilot::Core::AttestationResultState *v62; // [rsp+60h] [rbp-118h] BYREF
  RTL_SRWLOCK *v63; // [rsp+68h] [rbp-110h] BYREF
  _QWORD v64[2]; // [rsp+70h] [rbp-108h] BYREF
  int v65; // [rsp+80h] [rbp-F8h]
  int v66; // [rsp+84h] [rbp-F4h]
  char v67; // [rsp+88h] [rbp-F0h]
  int v68; // [rsp+90h] [rbp-E8h]
  unsigned int *v69; // [rsp+98h] [rbp-E0h]
  int v70; // [rsp+A0h] [rbp-D8h]
  int v71; // [rsp+A4h] [rbp-D4h] BYREF
  RTL_SRWLOCK *v72; // [rsp+A8h] [rbp-D0h]
  __int128 v73; // [rsp+B0h] [rbp-C8h] BYREF
  RTL_SRWLOCK *v74; // [rsp+C0h] [rbp-B8h]
  char v75[8]; // [rsp+C8h] [rbp-B0h] BYREF
  char v76[8]; // [rsp+D0h] [rbp-A8h] BYREF
  unsigned int v77; // [rsp+D8h] [rbp-A0h] BYREF
  unsigned int v78; // [rsp+DCh] [rbp-9Ch] BYREF
  RTL_SRWLOCK *v79; // [rsp+E0h] [rbp-98h] BYREF
  __int64 *v80; // [rsp+E8h] [rbp-90h] BYREF
  __int128 v81; // [rsp+F0h] [rbp-88h] BYREF
  __int64 v82; // [rsp+100h] [rbp-78h]
  int v83; // [rsp+108h] [rbp-70h] BYREF
  int v84; // [rsp+10Ch] [rbp-6Ch] BYREF
  int v85; // [rsp+110h] [rbp-68h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+118h] [rbp-60h] BYREF
  int v87[4]; // [rsp+120h] [rbp-58h] BYREF
  int v88[2]; // [rsp+130h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v72 = this;
  v2 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)0x80004001LL,
      v59);
    return 2147500033LL;
  }
  AcquireSRWLockExclusive(this + 3);
  v61 = this + 3;
  if ( !this[6].Ptr )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)0x8000FFFFLL,
      v59);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
    return 2147549183LL;
  }
  if ( this[9].Ptr == this[10].Ptr )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)0x8000FFFFLL,
      v59);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
    return 2147549183LL;
  }
  Ptr = this[12].Ptr;
  if ( Ptr != this[13].Ptr )
    this[13].Ptr = Ptr;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
  v5 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v64[0] = this;
  v64[1] = &PerformanceCount;
  v65 = 0;
  v66 = HIDWORD(v74);
  v67 = 1;
  v81 = 0;
  v82 = 0;
  v85 = 0;
  AcquireSRWLockShared(this + 3);
  v79 = this + 3;
  v6 = (*(__int64 (__fastcall **)(PVOID, int *))(*(_QWORD *)this[6].Ptr + 64LL))(this[6].Ptr, &v85);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x161,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)(unsigned int)v6,
      v59);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v79);
    std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
    v67 = 0;
    ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
    return v7;
  }
  v78 = 0;
  v8 = (*(__int64 (__fastcall **)(PVOID, unsigned int *))(*(_QWORD *)this[6].Ptr + 48LL))(this[6].Ptr, &v78);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)(unsigned int)v8,
      v59);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v79);
    std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
    v67 = 0;
    ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
    return v9;
  }
  AttestationPhaseList = ModernDeployment::Autopilot::Core::AttestationConfiguration::GetAttestationPhaseList(v78, &v81);
  v11 = AttestationPhaseList;
  if ( AttestationPhaseList < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)(unsigned int)AttestationPhaseList,
      v59);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v79);
    std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
    v67 = 0;
    ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
    return v11;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v79);
  v60 = 0;
  v12 = (unsigned int *)v81;
LABEL_14:
  v69 = v12;
  if ( v12 == *((unsigned int **)&v81 + 1) )
    goto LABEL_81;
  token = (Concurrency::cancellation_token *)Concurrency::cancellation_token_source::get_token(&this[15], v75);
  is_canceled = Concurrency::cancellation_token::is_canceled(token);
  pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)v75);
  if ( is_canceled )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(v15, AutopilotAttestationCancelled, v16, 1, v87);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)0x80004004LL,
      v59);
    std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
    v67 = 0;
    ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
    return 2147500036LL;
  }
  if ( v5 < 0 || v2 )
  {
LABEL_81:
    v57 = ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::DetermineOverallState(
            (ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *)this,
            1,
            &v60);
    v58 = v57;
    if ( v57 >= 0 )
    {
      AcquireSRWLockExclusive(this + 3);
      *(_QWORD *)v88 = this + 3;
      LOBYTE(this[7].Ptr) = 0;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v88);
      std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
      v67 = 0;
      ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x217,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
        (const char *)(unsigned int)v57,
        v59);
      std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
      v67 = 0;
      ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
      return v58;
    }
  }
  v63 = 0;
  AcquireSRWLockShared(this + 3);
  v61 = this + 3;
  v80 = 0;
  v17 = (__int64 *)this[6].Ptr;
  v18 = *v17;
  v80 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v18 + 96))(v17, &v80);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)(unsigned int)v19,
      v59);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v80);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
    std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
    v67 = 0;
    ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
    return v20;
  }
  v79 = 0;
  v21 = *v80;
  v79 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, RTL_SRWLOCK **))(v21 + 48))(v80, *v12, &v79);
  v23 = v22;
  if ( v22 >= 0 )
  {
    v24 = v79;
    v63 = v79;
    if ( v79 )
      (*((void (__fastcall **)(RTL_SRWLOCK *))v79->Ptr + 1))(v79);
  }
  else
  {
    if ( v22 != -2147483637 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
        (const char *)(unsigned int)v22,
        v59);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v79);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v80);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
      std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
      v67 = 0;
      ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
      return v23;
    }
    v24 = 0;
  }
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v79);
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v80);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
  v78 = 60000;
  v68 = 3;
  v25 = 5000;
  v70 = 5000;
  AcquireSRWLockShared(this + 3);
  v61 = this + 3;
  if ( v24 )
  {
    v77 = 0;
    if ( (*((int (__fastcall **)(RTL_SRWLOCK *, unsigned int *))v24->Ptr + 10))(v24, &v77) >= 0 )
    {
      v26 = v78;
      if ( v77 )
        v26 = v77;
      v78 = v26;
    }
    v83 = 0;
    v27 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, int *))v24->Ptr + 8))(v24, &v83);
    v28 = v68;
    if ( v27 >= 0 )
      v28 = v83;
    v68 = v28;
    v84 = 0;
    if ( (*((int (__fastcall **)(RTL_SRWLOCK *, int *))v24->Ptr + 12))(v24, &v84) >= 0 )
      v25 = v84;
    v70 = v25;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
  v29 = this[9].Ptr;
  v30 = this[10].Ptr;
  for ( *(_QWORD *)v88 = v30; ; v30 = *(_QWORD **)v88 )
  {
    if ( v29 == v30 )
      goto LABEL_78;
    v31 = (Concurrency::cancellation_token *)Concurrency::cancellation_token_source::get_token(&this[15], v76);
    v32 = Concurrency::cancellation_token::is_canceled(v31);
    pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)v76);
    if ( v32 )
      break;
    AcquireSRWLockShared(this + 3);
    v61 = this + 3;
    v35 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 8LL))(*v29);
    if ( (v35 & *v69) == 0 || (v36 = (**(__int64 (__fastcall ***)(_QWORD))*v29)(*v29), v36 != v85) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
      goto LABEL_80;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
    *(_OWORD *)v87 = 0;
    v37 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v29 + 16LL))(*v29, v87);
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CB,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
        (const char *)(unsigned int)v37,
        v59);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
      std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
      v67 = 0;
      ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
      return v38;
    }
    v5 = v87[0];
    v71 = v87[0];
    if ( v87[1] != 2 )
    {
      v62 = 0;
      v39 = ModernDeployment::Autopilot::Core::AttestationHelpers::CreateAttestationResultState(
              (unsigned int)v87[3],
              (unsigned int)v87[0],
              &v62);
      v40 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DC,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)(unsigned int)v39,
          v59);
        wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(&v62);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
        std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
        v67 = 0;
        ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
        return v40;
      }
      v41 = ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::HandleAttestationStateChange(
              (ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *)this,
              v62);
      v42 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DD,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)(unsigned int)v41,
          v59);
        wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(&v62);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
        std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
        v67 = 0;
        ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
        return v42;
      }
      v77 = 0;
      v61 = 0;
      v43 = ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProviderWithRetry(
              (_DWORD)this,
              (_DWORD)v29,
              *v69,
              v78,
              v68,
              v70,
              (__int64)&v71,
              (__int64)&v77,
              (__int64)&v61);
      v45 = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EA,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)(unsigned int)v43,
          v59);
        wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(&v62);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
        std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
        v67 = 0;
        ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
        return v45;
      }
      v5 = v71;
      if ( v71 >= 0 )
      {
        if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) == 0 )
          goto LABEL_62;
        v46 = AutopilotAttestationProviderPhaseCompleteSucceeded;
LABEL_59:
        v47 = v77;
        v48 = v61;
        McTemplateU0dqxq_EventWriteTransfer(v44, (_DWORD)v46, v71, *v69, (char)v61, v77);
      }
      else
      {
        if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        {
          v46 = AutopilotAttestationProviderPhaseCompleteFailed;
          goto LABEL_59;
        }
LABEL_62:
        v47 = v77;
        v48 = v61;
      }
      AcquireSRWLockExclusive(this + 3);
      v61 = this + 3;
      LODWORD(v73) = *v69;
      DWORD1(v73) = v5;
      *((_QWORD *)&v73 + 1) = v47;
      v74 = v48;
      v49 = this[13].Ptr;
      if ( v49 == this[14].Ptr )
      {
        std::vector<ModernDeployment::Autopilot::Core::AttestationPhaseResult>::_Emplace_reallocate<ModernDeployment::Autopilot::Core::AttestationPhaseResult>(
          &this[12],
          v49,
          &v73);
      }
      else
      {
        *(_OWORD *)v49 = v73;
        v49[2] = v48;
        this[13].Ptr = (char *)this[13].Ptr + 24;
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
      v50 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v29 + 16LL))(*v29, v87);
      v51 = v50;
      if ( v50 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x204,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)(unsigned int)v50,
          v59);
        wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(&v62);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
        std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
        v67 = 0;
        ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
        return v51;
      }
      v52 = ModernDeployment::Autopilot::Core::AttestationHelpers::CreateAttestationResultState(
              (unsigned int)v87[3],
              (unsigned int)v87[0],
              &v62);
      v53 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x209,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)(unsigned int)v52,
          v59);
        wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(&v62);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
        std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
        v67 = 0;
        ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
        return v53;
      }
      v54 = ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::HandleAttestationStateChange(
              (ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *)this,
              v62);
      v55 = v54;
      if ( v54 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20B,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)(unsigned int)v54,
          v59);
        wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(&v62);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
        std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
        v67 = 0;
        ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
        return v55;
      }
      v56 = ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::DetermineOverallState(
              (ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *)this,
              1,
              &v60);
      if ( v56 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x20E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)(unsigned int)v56,
          v59);
      v2 = v60;
      if ( v5 < 0 || v60 )
      {
        wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(&v62);
LABEL_78:
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
        v12 = v69 + 1;
        goto LABEL_14;
      }
      wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(&v62);
    }
LABEL_80:
    v29 += 2;
  }
  if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v33, AutopilotAttestationCancelled, v34, 1, v88);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B7,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
    (const char *)0x80004004LL,
    v59);
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
  std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
  v67 = 0;
  ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
  return 2147500036LL;
}

```

## disassembly

```asm
0x1801166f8  mov     [rsp+arg_8], rbx
0x1801166fd  mov     [rsp+arg_10], rsi
0x180116702  push    rdi
0x180116703  push    r12
0x180116705  push    r13
0x180116707  push    r14
0x180116709  push    r15
0x18011670b  sub     rsp, 150h
0x180116712  mov     rax, cs:__security_cookie
0x180116719  xor     rax, rsp
0x18011671c  mov     [rsp+178h+var_38], rax
0x180116724  mov     rsi, rcx
0x180116727  mov     [rsp+178h+var_D0], rcx
0x18011672f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180116736  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18011673b  xor     r15d, r15d
0x18011673e  test    al, al
0x180116740  jz      loc_1801173CE
0x180116746  lea     r14, [rsi+18h]
0x18011674a  mov     rcx, r14; SRWLock
0x18011674d  call    cs:__imp_AcquireSRWLockExclusive
0x180116753  mov     [rsp+178h+var_120], r14
0x180116758  cmp     [rsi+30h], r15
0x18011675c  jz      loc_18011739F
0x180116762  mov     rax, [rsi+50h]
0x180116766  cmp     [rsi+48h], rax
0x18011676a  jnz     short loc_18011679E
0x18011676c  mov     rcx, [rsp+178h]; this
0x180116774  mov     ebx, 8000FFFFh
0x180116779  mov     r9d, ebx; char *
0x18011677c  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180116783  mov     edx, 144h; void *
0x180116788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011678d  lea     rcx, [rsp+178h+var_120]
0x180116792  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180116797  mov     eax, ebx
0x180116799  jmp     loc_1801173F1
0x18011679e  mov     rax, [rsi+60h]
0x1801167a2  cmp     rax, [rsi+68h]
0x1801167a6  jz      short loc_1801167AC
0x1801167a8  mov     [rsi+68h], rax
0x1801167ac  lea     rcx, [rsp+178h+var_120]
0x1801167b1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801167b6  mov     r12d, r15d
0x1801167b9  lea     rcx, [rsp+178h+PerformanceCount]; lpPerformanceCount
0x1801167c1  call    cs:__imp_QueryPerformanceCounter
0x1801167c7  mov     [rsp+178h+var_108], rsi
0x1801167cc  lea     rax, [rsp+178h+PerformanceCount]
0x1801167d4  mov     [rsp+178h+var_100], rax
0x1801167d9  mov     [rsp+178h+var_F8], r15d
0x1801167e1  mov     eax, [rsp+178h+var_B4]
0x1801167e8  mov     [rsp+178h+var_F4], eax
0x1801167ef  mov     [rsp+178h+var_F0], 1
0x1801167f7  xorps   xmm0, xmm0
0x1801167fa  movdqu  [rsp+178h+var_88], xmm0
0x180116803  mov     [rsp+178h+var_78], r15
0x18011680b  mov     [rsp+178h+var_68], r15d
0x180116813  mov     rcx, r14; SRWLock
0x180116816  call    cs:__imp_AcquireSRWLockShared
0x18011681c  mov     [rsp+178h+var_98], r14
0x180116824  mov     rcx, [rsi+30h]
0x180116828  mov     rax, [rcx]
0x18011682b  lea     rdx, [rsp+178h+var_68]
0x180116833  mov     rax, [rax+40h]
0x180116837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011683c  mov     ebx, eax
0x18011683e  test    eax, eax
0x180116840  jns     short loc_180116894
0x180116842  mov     rcx, [rsp+178h]; this
0x18011684a  mov     r9d, eax; char *
0x18011684d  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180116854  mov     edx, 161h; void *
0x180116859  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011685e  nop
0x18011685f  lea     rcx, [rsp+178h+var_98]
0x180116867  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011686c  nop
0x18011686d  lea     rcx, [rsp+178h+var_88]
0x180116875  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x18011687a  nop
0x18011687b  mov     [rsp+178h+var_F0], r15b
0x180116883  lea     rcx, [rsp+178h+var_108]
0x180116888  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x18011688d  mov     eax, ebx
0x18011688f  jmp     loc_1801173F1
0x180116894  mov     [rsp+178h+var_9C], r15d
0x18011689c  mov     rcx, [rsi+30h]
0x1801168a0  mov     rax, [rcx]
0x1801168a3  lea     rdx, [rsp+178h+var_9C]
0x1801168ab  mov     rax, [rax+30h]
0x1801168af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801168b4  mov     ebx, eax
0x1801168b6  test    eax, eax
0x1801168b8  jns     short loc_18011690C
0x1801168ba  mov     rcx, [rsp+178h]; this
0x1801168c2  mov     r9d, eax; char *
0x1801168c5  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801168cc  mov     edx, 164h; void *
0x1801168d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801168d6  nop
0x1801168d7  lea     rcx, [rsp+178h+var_98]
0x1801168df  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801168e4  nop
0x1801168e5  lea     rcx, [rsp+178h+var_88]
0x1801168ed  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x1801168f2  nop
0x1801168f3  mov     [rsp+178h+var_F0], r15b
0x1801168fb  lea     rcx, [rsp+178h+var_108]
0x180116900  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x180116905  mov     eax, ebx
0x180116907  jmp     loc_1801173F1
0x18011690c  lea     rdx, [rsp+178h+var_88]
0x180116914  mov     ecx, [rsp+178h+var_9C]
0x18011691b  call    ?GetAttestationPhaseList@AttestationConfiguration@Core@Autopilot@ModernDeployment@@SAJW4AttestationPhase@234@AEAV?$vector@W4AttestationPhase@Core@Autopilot@ModernDeployment@@V?$allocator@W4AttestationPhase@Core@Autopilot@ModernDeployment@@@std@@@std@@@Z; ModernDeployment::Autopilot::Core::AttestationConfiguration::GetAttestationPhaseList(ModernDeployment::Autopilot::Core::AttestationPhase,std::vector<ModernDeployment::Autopilot::Core::AttestationPhase> &)
0x180116920  mov     ebx, eax
0x180116922  test    eax, eax
0x180116924  jns     short loc_180116978
0x180116926  mov     rcx, [rsp+178h]; this
0x18011692e  mov     r9d, eax; char *
0x180116931  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180116938  mov     edx, 165h; void *
0x18011693d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116942  nop
0x180116943  lea     rcx, [rsp+178h+var_98]
0x18011694b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180116950  nop
0x180116951  lea     rcx, [rsp+178h+var_88]
0x180116959  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x18011695e  nop
0x18011695f  mov     [rsp+178h+var_F0], r15b
0x180116967  lea     rcx, [rsp+178h+var_108]
0x18011696c  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x180116971  mov     eax, ebx
0x180116973  jmp     loc_1801173F1
0x180116978  lea     rcx, [rsp+178h+var_98]
0x180116980  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180116985  mov     [rsp+178h+var_128], r15b
0x18011698a  mov     r13, qword ptr [rsp+178h+var_88]
0x180116992  lea     rdi, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180116999  mov     [rsp+178h+var_E0], r13
0x1801169a1  cmp     r13, qword ptr [rsp+178h+var_88+8]
0x1801169a9  jz      loc_1801172FF
0x1801169af  lea     rcx, [rsi+78h]
0x1801169b3  lea     rdx, [rsp+178h+var_B0]
0x1801169bb  call    ?get_token@cancellation_token_source@Concurrency@@QEBA?AVcancellation_token@2@XZ; Concurrency::cancellation_token_source::get_token(void)
0x1801169c0  mov     rcx, rax; this
0x1801169c3  call    ?is_canceled@cancellation_token@Concurrency@@QEBA_NXZ; Concurrency::cancellation_token::is_canceled(void)
0x1801169c8  mov     bl, al
0x1801169ca  lea     rcx, [rsp+178h+var_B0]; this
0x1801169d2  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801169d7  nop
0x1801169d8  test    bl, bl
0x1801169da  jz      short loc_180116A49
0x1801169dc  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1801169e3  jz      short loc_180116A04
0x1801169e5  lea     rax, [rsp+178h+var_58]
0x1801169ed  mov     qword ptr [rsp+178h+var_158], rax; int
0x1801169f2  mov     r9d, 1
0x1801169f8  lea     rdx, AutopilotAttestationCancelled
0x1801169ff  call    McGenEventWrite_EventWriteTransfer
0x180116a04  mov     rcx, [rsp+178h]; this
0x180116a0c  mov     ebx, 80004004h
0x180116a11  mov     r9d, ebx; char *
0x180116a14  mov     r8, rdi; unsigned int
0x180116a17  mov     edx, 16Fh; void *
0x180116a1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116a21  nop
0x180116a22  lea     rcx, [rsp+178h+var_88]
0x180116a2a  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x180116a2f  nop
0x180116a30  mov     [rsp+178h+var_F0], 0
0x180116a38  lea     rcx, [rsp+178h+var_108]
0x180116a3d  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x180116a42  mov     eax, ebx
0x180116a44  jmp     loc_1801173F1
0x180116a49  xor     ebx, ebx
0x180116a4b  test    r12d, r12d
0x180116a4e  js      loc_1801172FF
0x180116a54  test    r15b, r15b
0x180116a57  jnz     loc_1801172FF
0x180116a5d  mov     [rsp+178h+var_110], rbx
0x180116a62  mov     rcx, r14; SRWLock
0x180116a65  call    cs:__imp_AcquireSRWLockShared
0x180116a6b  mov     [rsp+178h+var_120], r14
0x180116a70  mov     [rsp+178h+var_90], rbx
0x180116a78  mov     rcx, [rsi+30h]
0x180116a7c  mov     rax, [rcx]
0x180116a7f  mov     [rsp+178h+var_90], rbx
0x180116a87  lea     rdx, [rsp+178h+var_90]
0x180116a8f  mov     rax, [rax+60h]
0x180116a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116a98  mov     ebx, eax
0x180116a9a  test    eax, eax
0x180116a9c  jns     short loc_180116B02
0x180116a9e  mov     rcx, [rsp+178h]; this
0x180116aa6  mov     r9d, eax; char *
0x180116aa9  mov     r8, rdi; unsigned int
0x180116aac  mov     edx, 17Dh; void *
0x180116ab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116ab6  nop
0x180116ab7  lea     rcx, [rsp+178h+var_90]
0x180116abf  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180116ac4  nop
0x180116ac5  lea     rcx, [rsp+178h+var_120]
0x180116aca  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180116acf  nop
0x180116ad0  lea     rcx, [rsp+178h+var_110]
0x180116ad5  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180116ada  nop
0x180116adb  lea     rcx, [rsp+178h+var_88]
0x180116ae3  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x180116ae8  nop
0x180116ae9  mov     [rsp+178h+var_F0], r15b
0x180116af1  lea     rcx, [rsp+178h+var_108]
0x180116af6  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x180116afb  mov     eax, ebx
0x180116afd  jmp     loc_1801173F1
0x180116b02  mov     [rsp+178h+var_98], 0
0x180116b0e  mov     rcx, [rsp+178h+var_90]
0x180116b16  mov     rax, [rcx]
0x180116b19  mov     [rsp+178h+var_98], 0
0x180116b25  lea     r8, [rsp+178h+var_98]
0x180116b2d  mov     edx, [r13+0]
0x180116b31  mov     rax, [rax+30h]
0x180116b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116b3a  mov     ebx, eax
0x180116b3c  test    eax, eax
0x180116b3e  jns     short loc_180116BBD
0x180116b40  cmp     eax, 8000000Bh
0x180116b45  jz      short loc_180116BB9
0x180116b47  mov     rcx, [rsp+178h]; this
0x180116b4f  mov     r9d, eax; char *
0x180116b52  mov     r8, rdi; unsigned int
0x180116b55  mov     edx, 187h; void *
0x180116b5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116b5f  nop
0x180116b60  lea     rcx, [rsp+178h+var_98]
0x180116b68  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180116b6d  nop
0x180116b6e  lea     rcx, [rsp+178h+var_90]
0x180116b76  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180116b7b  nop
0x180116b7c  lea     rcx, [rsp+178h+var_120]
0x180116b81  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180116b86  nop
0x180116b87  lea     rcx, [rsp+178h+var_110]
0x180116b8c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180116b91  nop
0x180116b92  lea     rcx, [rsp+178h+var_88]
0x180116b9a  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x180116b9f  nop
0x180116ba0  mov     [rsp+178h+var_F0], 0
0x180116ba8  lea     rcx, [rsp+178h+var_108]
0x180116bad  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x180116bb2  mov     eax, ebx
0x180116bb4  jmp     loc_1801173F1
0x180116bb9  xor     ebx, ebx
0x180116bbb  jmp     short loc_180116BDF
0x180116bbd  mov     rbx, [rsp+178h+var_98]
0x180116bc5  mov     [rsp+178h+var_110], rbx
0x180116bca  test    rbx, rbx
0x180116bcd  jz      short loc_180116BDF
0x180116bcf  mov     rax, [rbx]
0x180116bd2  mov     rcx, rbx
0x180116bd5  mov     rax, [rax+8]
0x180116bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116bde  nop
0x180116bdf  lea     rcx, [rsp+178h+var_98]
0x180116be7  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180116bec  nop
0x180116bed  lea     rcx, [rsp+178h+var_90]
0x180116bf5  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180116bfa  nop
0x180116bfb  lea     rcx, [rsp+178h+var_120]
0x180116c00  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180116c05  mov     [rsp+178h+var_9C], 0EA60h
0x180116c10  mov     [rsp+178h+var_E8], 3
0x180116c1b  mov     r13d, 1388h
0x180116c21  mov     [rsp+178h+var_D8], r13d
0x180116c29  mov     rcx, r14; SRWLock
0x180116c2c  call    cs:__imp_AcquireSRWLockShared
0x180116c32  mov     [rsp+178h+var_120], r14
0x180116c37  test    rbx, rbx
0x180116c3a  jz      loc_180116CEF
0x180116c40  mov     [rsp+178h+var_A0], 0
0x180116c4b  mov     rax, [rbx]
0x180116c4e  lea     rdx, [rsp+178h+var_A0]
0x180116c56  mov     rcx, rbx
0x180116c59  mov     rax, [rax+50h]
0x180116c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116c62  test    eax, eax
0x180116c64  js      short loc_180116C80
0x180116c66  mov     ecx, [rsp+178h+var_9C]
0x180116c6d  mov     eax, [rsp+178h+var_A0]
0x180116c74  test    eax, eax
0x180116c76  cmovnz  ecx, eax
0x180116c79  mov     [rsp+178h+var_9C], ecx
0x180116c80  mov     [rsp+178h+var_70], 0
0x180116c8b  mov     rax, [rbx]
0x180116c8e  lea     rdx, [rsp+178h+var_70]
  ... truncated ...
```
