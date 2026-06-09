# ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait(void)

- ea: `0x180119eac`
- end: `0x18011ac03`
- name: `?ExecuteProvidersBlockWait@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJXZ`
- size: `3415`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18011af40`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e43c`
- `0x18006e464`
- `0x18006e608`
- `0x18006e62c`
- `0x180077d0c`
- `0x180080c10`
- `0x1800810f0`
- `0x1800a1644`
- `0x18010b7e4`
- `0x180115b14`
- `0x180118a88`
- `0x180119350`
- `0x180119838`
- `0x180119eac`
- `0x18011ac0c`
- `0x18011c1e0`
- `0x18011e8d0`
- `0x18011ebd4`
- `0x18011ef0c`
- `0x18011f6a8`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180119fd6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011a22b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011a3f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011a58c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180119fd6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011a22b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011a3f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011a58c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180119f01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011a883`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011ab38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180119f01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011a883`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011ab38`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180119f7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180119f7b`

## string_xrefs

- `0x180119f36`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011a013`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011a08b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011a0f7`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011a158`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011ab93`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011abc2`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`

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
  int *v59; // [rsp+20h] [rbp-158h]
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
      (int)v59);
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
      (int)v59);
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
      (int)v59);
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
      (int)v59);
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
      (int)v59);
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
      (int)v59);
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
    {
      v59 = v87;
      McGenEventWrite_EventWriteTransfer(v15, AutopilotAttestationCancelled, v16, 1);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)0x80004004LL,
      (int)v59);
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
        (int)v59);
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
      (int)v59);
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
        (int)v59);
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
        (int)v59);
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
          (int)v59);
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
          (int)v59);
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
          (int)v59);
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
          (int)v59);
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
          (int)v59);
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
          (int)v59);
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
          (int)v59);
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
  {
    v59 = v88;
    McGenEventWrite_EventWriteTransfer(v33, AutopilotAttestationCancelled, v34, 1);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B7,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
    (const char *)0x80004004LL,
    (int)v59);
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v63);
  std::vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(&v81);
  v67 = 0;
  ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait_::_13_::_lambda_1_::operator()(v64);
  return 2147500036LL;
}

```

## disassembly

```asm
0x180119eac  mov     [rsp+arg_8], rbx
0x180119eb1  mov     [rsp+arg_10], rsi
0x180119eb6  push    rdi
0x180119eb7  push    r12
0x180119eb9  push    r13
0x180119ebb  push    r14
0x180119ebd  push    r15
0x180119ebf  sub     rsp, 150h
0x180119ec6  mov     rax, cs:__security_cookie
0x180119ecd  xor     rax, rsp
0x180119ed0  mov     [rsp+178h+var_38], rax
0x180119ed8  mov     rsi, rcx
0x180119edb  mov     [rsp+178h+var_D0], rcx
0x180119ee3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180119eea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180119eef  xor     r15d, r15d
0x180119ef2  test    al, al
0x180119ef4  jz      loc_18011ABB2
0x180119efa  lea     r14, [rsi+18h]
0x180119efe  mov     rcx, r14; SRWLock
0x180119f01  call    cs:__imp_AcquireSRWLockExclusive
0x180119f08  nop     dword ptr [rax+rax+00h]
0x180119f0d  mov     [rsp+178h+var_120], r14
0x180119f12  cmp     [rsi+30h], r15
0x180119f16  jz      loc_18011AB83
0x180119f1c  mov     rax, [rsi+50h]
0x180119f20  cmp     [rsi+48h], rax
0x180119f24  jnz     short loc_180119F58
0x180119f26  mov     rcx, [rsp+178h]; this
0x180119f2e  mov     ebx, 8000FFFFh
0x180119f33  mov     r9d, ebx; char *
0x180119f36  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180119f3d  mov     edx, 144h; void *
0x180119f42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119f47  lea     rcx, [rsp+178h+var_120]
0x180119f4c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180119f51  mov     eax, ebx
0x180119f53  jmp     loc_18011ABD5
0x180119f58  mov     rax, [rsi+60h]
0x180119f5c  cmp     rax, [rsi+68h]
0x180119f60  jz      short loc_180119F66
0x180119f62  mov     [rsi+68h], rax
0x180119f66  lea     rcx, [rsp+178h+var_120]
0x180119f6b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180119f70  mov     r12d, r15d
0x180119f73  lea     rcx, [rsp+178h+PerformanceCount]; lpPerformanceCount
0x180119f7b  call    cs:__imp_QueryPerformanceCounter
0x180119f82  nop     dword ptr [rax+rax+00h]
0x180119f87  mov     [rsp+178h+var_108], rsi
0x180119f8c  lea     rax, [rsp+178h+PerformanceCount]
0x180119f94  mov     [rsp+178h+var_100], rax
0x180119f99  mov     [rsp+178h+var_F8], r15d
0x180119fa1  mov     eax, [rsp+178h+var_B4]
0x180119fa8  mov     [rsp+178h+var_F4], eax
0x180119faf  mov     [rsp+178h+var_F0], 1
0x180119fb7  xorps   xmm0, xmm0
0x180119fba  movdqu  [rsp+178h+var_88], xmm0
0x180119fc3  mov     [rsp+178h+var_78], r15
0x180119fcb  mov     [rsp+178h+var_68], r15d
0x180119fd3  mov     rcx, r14; SRWLock
0x180119fd6  call    cs:__imp_AcquireSRWLockShared
0x180119fdd  nop     dword ptr [rax+rax+00h]
0x180119fe2  mov     [rsp+178h+var_98], r14
0x180119fea  mov     rcx, [rsi+30h]
0x180119fee  mov     rax, [rcx]
0x180119ff1  lea     rdx, [rsp+178h+var_68]
0x180119ff9  mov     rax, [rax+40h]
0x180119ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a002  mov     ebx, eax
0x18011a004  test    eax, eax
0x18011a006  jns     short loc_18011A05A
0x18011a008  mov     rcx, [rsp+178h]; this
0x18011a010  mov     r9d, eax; char *
0x18011a013  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011a01a  mov     edx, 161h; void *
0x18011a01f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a024  nop
0x18011a025  lea     rcx, [rsp+178h+var_98]
0x18011a02d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011a032  nop
0x18011a033  lea     rcx, [rsp+178h+var_88]
0x18011a03b  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x18011a040  nop
0x18011a041  mov     [rsp+178h+var_F0], r15b
0x18011a049  lea     rcx, [rsp+178h+var_108]
0x18011a04e  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x18011a053  mov     eax, ebx
0x18011a055  jmp     loc_18011ABD5
0x18011a05a  mov     [rsp+178h+var_9C], r15d
0x18011a062  mov     rcx, [rsi+30h]
0x18011a066  mov     rax, [rcx]
0x18011a069  lea     rdx, [rsp+178h+var_9C]
0x18011a071  mov     rax, [rax+30h]
0x18011a075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a07a  mov     ebx, eax
0x18011a07c  test    eax, eax
0x18011a07e  jns     short loc_18011A0D2
0x18011a080  mov     rcx, [rsp+178h]; this
0x18011a088  mov     r9d, eax; char *
0x18011a08b  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011a092  mov     edx, 164h; void *
0x18011a097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a09c  nop
0x18011a09d  lea     rcx, [rsp+178h+var_98]
0x18011a0a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011a0aa  nop
0x18011a0ab  lea     rcx, [rsp+178h+var_88]
0x18011a0b3  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x18011a0b8  nop
0x18011a0b9  mov     [rsp+178h+var_F0], r15b
0x18011a0c1  lea     rcx, [rsp+178h+var_108]
0x18011a0c6  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x18011a0cb  mov     eax, ebx
0x18011a0cd  jmp     loc_18011ABD5
0x18011a0d2  lea     rdx, [rsp+178h+var_88]
0x18011a0da  mov     ecx, [rsp+178h+var_9C]
0x18011a0e1  call    ?GetAttestationPhaseList@AttestationConfiguration@Core@Autopilot@ModernDeployment@@SAJW4AttestationPhase@234@AEAV?$vector@W4AttestationPhase@Core@Autopilot@ModernDeployment@@V?$allocator@W4AttestationPhase@Core@Autopilot@ModernDeployment@@@std@@@std@@@Z; ModernDeployment::Autopilot::Core::AttestationConfiguration::GetAttestationPhaseList(ModernDeployment::Autopilot::Core::AttestationPhase,std::vector<ModernDeployment::Autopilot::Core::AttestationPhase> &)
0x18011a0e6  mov     ebx, eax
0x18011a0e8  test    eax, eax
0x18011a0ea  jns     short loc_18011A13E
0x18011a0ec  mov     rcx, [rsp+178h]; this
0x18011a0f4  mov     r9d, eax; char *
0x18011a0f7  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011a0fe  mov     edx, 165h; void *
0x18011a103  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a108  nop
0x18011a109  lea     rcx, [rsp+178h+var_98]
0x18011a111  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011a116  nop
0x18011a117  lea     rcx, [rsp+178h+var_88]
0x18011a11f  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x18011a124  nop
0x18011a125  mov     [rsp+178h+var_F0], r15b
0x18011a12d  lea     rcx, [rsp+178h+var_108]
0x18011a132  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x18011a137  mov     eax, ebx
0x18011a139  jmp     loc_18011ABD5
0x18011a13e  lea     rcx, [rsp+178h+var_98]
0x18011a146  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011a14b  mov     [rsp+178h+var_128], r15b
0x18011a150  mov     r13, qword ptr [rsp+178h+var_88]
0x18011a158  lea     rdi, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011a15f  mov     [rsp+178h+var_E0], r13
0x18011a167  cmp     r13, qword ptr [rsp+178h+var_88+8]
0x18011a16f  jz      loc_18011AADD
0x18011a175  lea     rcx, [rsi+78h]
0x18011a179  lea     rdx, [rsp+178h+var_B0]
0x18011a181  call    ?get_token@cancellation_token_source@Concurrency@@QEBA?AVcancellation_token@2@XZ; Concurrency::cancellation_token_source::get_token(void)
0x18011a186  mov     rcx, rax; this
0x18011a189  call    ?is_canceled@cancellation_token@Concurrency@@QEBA_NXZ; Concurrency::cancellation_token::is_canceled(void)
0x18011a18e  mov     bl, al
0x18011a190  lea     rcx, [rsp+178h+var_B0]; this
0x18011a198  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18011a19d  nop
0x18011a19e  test    bl, bl
0x18011a1a0  jz      short loc_18011A20F
0x18011a1a2  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18011a1a9  jz      short loc_18011A1CA
0x18011a1ab  lea     rax, [rsp+178h+var_58]
0x18011a1b3  mov     qword ptr [rsp+178h+var_158], rax; int
0x18011a1b8  mov     r9d, 1
0x18011a1be  lea     rdx, AutopilotAttestationCancelled
0x18011a1c5  call    McGenEventWrite_EventWriteTransfer
0x18011a1ca  mov     rcx, [rsp+178h]; this
0x18011a1d2  mov     ebx, 80004004h
0x18011a1d7  mov     r9d, ebx; char *
0x18011a1da  mov     r8, rdi; unsigned int
0x18011a1dd  mov     edx, 16Fh; void *
0x18011a1e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a1e7  nop
0x18011a1e8  lea     rcx, [rsp+178h+var_88]
0x18011a1f0  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x18011a1f5  nop
0x18011a1f6  mov     [rsp+178h+var_F0], 0
0x18011a1fe  lea     rcx, [rsp+178h+var_108]
0x18011a203  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x18011a208  mov     eax, ebx
0x18011a20a  jmp     loc_18011ABD5
0x18011a20f  xor     ebx, ebx
0x18011a211  test    r12d, r12d
0x18011a214  js      loc_18011AADD
0x18011a21a  test    r15b, r15b
0x18011a21d  jnz     loc_18011AADD
0x18011a223  mov     [rsp+178h+var_110], rbx
0x18011a228  mov     rcx, r14; SRWLock
0x18011a22b  call    cs:__imp_AcquireSRWLockShared
0x18011a232  nop     dword ptr [rax+rax+00h]
0x18011a237  mov     [rsp+178h+var_120], r14
0x18011a23c  mov     [rsp+178h+var_90], rbx
0x18011a244  mov     rcx, [rsi+30h]
0x18011a248  mov     rax, [rcx]
0x18011a24b  mov     [rsp+178h+var_90], rbx
0x18011a253  lea     rdx, [rsp+178h+var_90]
0x18011a25b  mov     rax, [rax+60h]
0x18011a25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a264  mov     ebx, eax
0x18011a266  test    eax, eax
0x18011a268  jns     short loc_18011A2CE
0x18011a26a  mov     rcx, [rsp+178h]; this
0x18011a272  mov     r9d, eax; char *
0x18011a275  mov     r8, rdi; unsigned int
0x18011a278  mov     edx, 17Dh; void *
0x18011a27d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a282  nop
0x18011a283  lea     rcx, [rsp+178h+var_90]
0x18011a28b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18011a290  nop
0x18011a291  lea     rcx, [rsp+178h+var_120]
0x18011a296  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011a29b  nop
0x18011a29c  lea     rcx, [rsp+178h+var_110]
0x18011a2a1  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18011a2a6  nop
0x18011a2a7  lea     rcx, [rsp+178h+var_88]
0x18011a2af  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x18011a2b4  nop
0x18011a2b5  mov     [rsp+178h+var_F0], r15b
0x18011a2bd  lea     rcx, [rsp+178h+var_108]
0x18011a2c2  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x18011a2c7  mov     eax, ebx
0x18011a2c9  jmp     loc_18011ABD5
0x18011a2ce  mov     [rsp+178h+var_98], 0
0x18011a2da  mov     rcx, [rsp+178h+var_90]
0x18011a2e2  mov     rax, [rcx]
0x18011a2e5  mov     [rsp+178h+var_98], 0
0x18011a2f1  lea     r8, [rsp+178h+var_98]
0x18011a2f9  mov     edx, [r13+0]
0x18011a2fd  mov     rax, [rax+30h]
0x18011a301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a306  mov     ebx, eax
0x18011a308  test    eax, eax
0x18011a30a  jns     short loc_18011A389
0x18011a30c  cmp     eax, 8000000Bh
0x18011a311  jz      short loc_18011A385
0x18011a313  mov     rcx, [rsp+178h]; this
0x18011a31b  mov     r9d, eax; char *
0x18011a31e  mov     r8, rdi; unsigned int
0x18011a321  mov     edx, 187h; void *
0x18011a326  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a32b  nop
0x18011a32c  lea     rcx, [rsp+178h+var_98]
0x18011a334  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18011a339  nop
0x18011a33a  lea     rcx, [rsp+178h+var_90]
0x18011a342  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18011a347  nop
0x18011a348  lea     rcx, [rsp+178h+var_120]
0x18011a34d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011a352  nop
0x18011a353  lea     rcx, [rsp+178h+var_110]
0x18011a358  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18011a35d  nop
0x18011a35e  lea     rcx, [rsp+178h+var_88]
0x18011a366  call    ??1?$vector@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@V?$allocator@W4IdkKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@@std@@@std@@QEAA@XZ; std::vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>::~vector<ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType>(void)
0x18011a36b  nop
0x18011a36c  mov     [rsp+178h+var_F0], 0
0x18011a374  lea     rcx, [rsp+178h+var_108]
0x18011a379  call    _ModernDeployment__Autopilot__Core__AutopilotAttestationStateMachine__ExecuteProvidersBlockWait____13____lambda_1___operator__
0x18011a37e  mov     eax, ebx
0x18011a380  jmp     loc_18011ABD5
0x18011a385  xor     ebx, ebx
0x18011a387  jmp     short loc_18011A3AB
0x18011a389  mov     rbx, [rsp+178h+var_98]
0x18011a391  mov     [rsp+178h+var_110], rbx
0x18011a396  test    rbx, rbx
0x18011a399  jz      short loc_18011A3AB
0x18011a39b  mov     rax, [rbx]
0x18011a39e  mov     rcx, rbx
0x18011a3a1  mov     rax, [rax+8]
0x18011a3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a3aa  nop
0x18011a3ab  lea     rcx, [rsp+178h+var_98]
0x18011a3b3  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18011a3b8  nop
0x18011a3b9  lea     rcx, [rsp+178h+var_90]
0x18011a3c1  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18011a3c6  nop
0x18011a3c7  lea     rcx, [rsp+178h+var_120]
0x18011a3cc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011a3d1  mov     [rsp+178h+var_9C], 0EA60h
0x18011a3dc  mov     [rsp+178h+var_E8], 3
0x18011a3e7  mov     r13d, 1388h
0x18011a3ed  mov     [rsp+178h+var_D8], r13d
0x18011a3f5  mov     rcx, r14; SRWLock
0x18011a3f8  call    cs:__imp_AcquireSRWLockShared
0x18011a3ff  nop     dword ptr [rax+rax+00h]
0x18011a404  mov     [rsp+178h+var_120], r14
0x18011a409  test    rbx, rbx
0x18011a40c  jz      loc_18011A4C1
0x18011a412  mov     [rsp+178h+var_A0], 0
0x18011a41d  mov     rax, [rbx]
0x18011a420  lea     rdx, [rsp+178h+var_A0]
0x18011a428  mov     rcx, rbx
0x18011a42b  mov     rax, [rax+50h]
0x18011a42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a434  test    eax, eax
0x18011a436  js      short loc_18011A452
0x18011a438  mov     ecx, [rsp+178h+var_9C]
0x18011a43f  mov     eax, [rsp+178h+var_A0]
0x18011a446  test    eax, eax
  ... truncated ...
```
