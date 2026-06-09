# ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::HandleAttestationStateChange(ModernDeployment::Autopilot::Core::AttestationResultState *)

- ea: `0x18011ac0c`
- end: `0x18011af30`
- name: `?HandleAttestationStateChange@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJPEAVAttestationResultState@234@@Z`
- size: `804`
- prototype: `int(ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *__hidden this, struct ModernDeployment::Autopilot::Core::AttestationResultState *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180119350`
- `0x180119eac`
- `0x18011d270`

## callees

- `0x180067e54`
- `0x18006e464`
- `0x18006e608`
- `0x18006e62c`
- `0x180077d0c`
- `0x180080c10`
- `0x1800ecf44`
- `0x1800ff724`
- `0x18011ac0c`
- `0x18011f554`
- `0x180120190`
- `0x180120220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011acc5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18011acc5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011ae2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011ae2d`

## string_xrefs

- `0x18011ac4f`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011ac8b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011acfb`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011ad44`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011adb8`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011adf6`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011ae58`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011aec1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011aefe`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::HandleAttestationStateChange(
        ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *this,
        struct ModernDeployment::Autopilot::Core::AttestationResultState *a2)
{
  const char *v4; // r9
  __int64 result; // rax
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // r14d
  int v9; // r15d
  ModernDeployment::Autopilot::Core::AttestationResultState *v10; // rcx
  int AttestationState; // eax
  unsigned int v12; // ebx
  int AttestationResult; // eax
  unsigned int v14; // ebx
  char v15; // si
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // eax
  unsigned int v21; // ebx
  char *v22; // rcx
  int v23; // eax
  int v24[2]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v25[6]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char *v27; // [rsp+70h] [rbp+18h] BYREF
  int v28; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      if ( !a2 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24A,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)0x80004003LL,
          v24[0]);
        return 2147500035LL;
      }
      *(_QWORD *)v24 = 0;
      v6 = ModernDeployment::Autopilot::Core::AttestationHelpers::CloneAttestationResultState(a2, v24);
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24F,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)(unsigned int)v6,
          v24[0]);
        wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(v24);
        return v7;
      }
      v8 = 0;
      LODWORD(v27) = 0;
      v9 = 0;
      v28 = 0;
      AcquireSRWLockShared((PSRWLOCK)this + 3);
      v25[0] = (char *)this + 24;
      v10 = (ModernDeployment::Autopilot::Core::AttestationResultState *)*((_QWORD *)this + 8);
      if ( v10 )
      {
        AttestationState = ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationState(
                             v10,
                             (enum ModernDeployment::Autopilot::Core::AttestationState *)&v27);
        v12 = AttestationState;
        if ( AttestationState < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25A,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
            (const char *)(unsigned int)AttestationState,
            v24[0]);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v25);
          wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(v24);
          return v12;
        }
        AttestationResult = ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationResult(
                              *((ModernDeployment::Autopilot::Core::AttestationResultState **)this + 8),
                              &v28);
        v14 = AttestationResult;
        if ( AttestationResult < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25B,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
            (const char *)(unsigned int)AttestationResult,
            v24[0]);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v25);
          wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(v24);
          return v14;
        }
        v15 = 0;
        v8 = (int)v27;
        v9 = v28;
      }
      else
      {
        v15 = 1;
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v25);
      LODWORD(v27) = 0;
      v28 = 0;
      v16 = ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationState(
              a2,
              (enum ModernDeployment::Autopilot::Core::AttestationState *)&v27);
      v17 = v16;
      if ( v16 >= 0 )
      {
        v18 = ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationResult(a2, &v28);
        v19 = v18;
        if ( v18 >= 0 )
        {
          if ( v8 != (_DWORD)v27 || v9 != v28 )
            v15 = 1;
          AcquireSRWLockExclusive((PSRWLOCK)this + 3);
          v27 = (char *)this + 24;
          v20 = ModernDeployment::Autopilot::Core::AttestationHelpers::CloneAttestationResultState(
                  a2,
                  (char *)this + 64);
          v21 = v20;
          if ( v20 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
            if ( v15 )
            {
              v22 = (char *)**((_QWORD **)this + 4);
              v27 = v22;
              while ( !v22[25] )
              {
                v23 = std::_Func_class<long,Windows::Management::Setup::IDeploymentSessionHeartbeatRequestedEventArgs *>::operator()(
                        v22 + 48,
                        *(_QWORD *)v24);
                if ( v23 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x27A,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattesta"
                                  "tionstatemachine.cpp",
                    (const char *)(unsigned int)v23,
                    v24[0]);
                std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Windows::Management::Setup::MachineProvisioningProgressReporter * const,std::shared_ptr<wil::AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::Management::Setup::MachineProvisioningProgressReporter *,Windows::Management::Setup::DeploymentSessionStateChangedEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy>>>>>,std::_Iterator_base0>::operator++(&v27);
                v22 = v27;
              }
            }
            wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(v24);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x272,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
              (const char *)(unsigned int)v20,
              v24[0]);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
            wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(v24);
            result = v21;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x267,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
            (const char *)(unsigned int)v18,
            v24[0]);
          wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(v24);
          result = v19;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x266,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
          (const char *)(unsigned int)v16,
          v24[0]);
        wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(v24);
        result = v17;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
        (const char *)0x80004001LL,
        v24[0]);
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    LODWORD(v27) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x280,
                     (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattest"
                                   "ationstatemachine.cpp",
                     v4);
    return (unsigned int)v27;
  }
  return result;
}

```

## disassembly

```asm
0x18011ac0c  mov     [rsp+arg_0], rbx
0x18011ac11  mov     [rsp+arg_8], rsi
0x18011ac16  push    rdi
0x18011ac17  push    r12
0x18011ac19  push    r13
0x18011ac1b  push    r14
0x18011ac1d  push    r15
0x18011ac1f  sub     rsp, 30h
0x18011ac23  mov     rdi, rdx
0x18011ac26  mov     r13, rcx
0x18011ac29  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18011ac30  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18011ac35  test    al, al
0x18011ac37  jz      loc_18011AEF1
0x18011ac3d  test    rdi, rdi
0x18011ac40  jnz     short loc_18011AC67
0x18011ac42  mov     rcx, [rsp+58h]; this
0x18011ac47  mov     ebx, 80004003h
0x18011ac4c  mov     r9d, ebx; char *
0x18011ac4f  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011ac56  mov     edx, 24Ah; void *
0x18011ac5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ac60  mov     eax, ebx
0x18011ac62  jmp     loc_18011AF17
0x18011ac67  mov     qword ptr [rsp+58h+var_38], 0; int
0x18011ac70  lea     rdx, [rsp+58h+var_38]
0x18011ac75  mov     rcx, rdi
0x18011ac78  call    ?CloneAttestationResultState@AttestationHelpers@Core@Autopilot@ModernDeployment@@SAJPEAUIAttestationResultState@234@AEAV?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@@Z; ModernDeployment::Autopilot::Core::AttestationHelpers::CloneAttestationResultState(ModernDeployment::Autopilot::Core::IAttestationResultState *,wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy> &)
0x18011ac7d  mov     ebx, eax
0x18011ac7f  test    eax, eax
0x18011ac81  jns     short loc_18011ACAE
0x18011ac83  mov     rcx, [rsp+58h]; this
0x18011ac88  mov     r9d, eax; char *
0x18011ac8b  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011ac92  mov     edx, 24Fh; void *
0x18011ac97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ac9c  nop
0x18011ac9d  lea     rcx, [rsp+58h+var_38]
0x18011aca2  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x18011aca7  mov     eax, ebx
0x18011aca9  jmp     loc_18011AF17
0x18011acae  xor     r14d, r14d
0x18011acb1  mov     dword ptr [rsp+58h+arg_10], r14d
0x18011acb6  xor     r15d, r15d
0x18011acb9  mov     [rsp+58h+arg_18], r15d
0x18011acbe  lea     r12, [r13+18h]
0x18011acc2  mov     rcx, r12; SRWLock
0x18011acc5  call    cs:__imp_AcquireSRWLockShared
0x18011accc  nop     dword ptr [rax+rax+00h]
0x18011acd1  mov     [rsp+58h+var_30], r12
0x18011acd6  mov     rcx, [r13+40h]; this
0x18011acda  test    rcx, rcx
0x18011acdd  jz      loc_18011AD80
0x18011ace3  lea     rdx, [rsp+58h+arg_10]; enum ModernDeployment::Autopilot::Core::AttestationState *
0x18011ace8  call    ?get_AttestationState@AttestationResultState@Core@Autopilot@ModernDeployment@@UEAAJPEAW4AttestationState@234@@Z; ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationState(ModernDeployment::Autopilot::Core::AttestationState *)
0x18011aced  mov     ebx, eax
0x18011acef  test    eax, eax
0x18011acf1  jns     short loc_18011AD28
0x18011acf3  mov     rcx, [rsp+58h]; this
0x18011acf8  mov     r9d, eax; char *
0x18011acfb  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011ad02  mov     edx, 25Ah; void *
0x18011ad07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ad0c  lea     rcx, [rsp+58h+var_30]
0x18011ad11  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011ad16  nop
0x18011ad17  lea     rcx, [rsp+58h+var_38]
0x18011ad1c  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x18011ad21  mov     eax, ebx
0x18011ad23  jmp     loc_18011AF17
0x18011ad28  lea     rdx, [rsp+58h+arg_18]; int *
0x18011ad2d  mov     rcx, [r13+40h]; this
0x18011ad31  call    ?get_AttestationResult@AttestationResultState@Core@Autopilot@ModernDeployment@@UEAAJPEAJ@Z; ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationResult(long *)
0x18011ad36  mov     ebx, eax
0x18011ad38  test    eax, eax
0x18011ad3a  jns     short loc_18011AD71
0x18011ad3c  mov     rcx, [rsp+58h]; this
0x18011ad41  mov     r9d, eax; char *
0x18011ad44  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011ad4b  mov     edx, 25Bh; void *
0x18011ad50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ad55  lea     rcx, [rsp+58h+var_30]
0x18011ad5a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011ad5f  nop
0x18011ad60  lea     rcx, [rsp+58h+var_38]
0x18011ad65  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x18011ad6a  mov     eax, ebx
0x18011ad6c  jmp     loc_18011AF17
0x18011ad71  xor     sil, sil
0x18011ad74  mov     r14d, dword ptr [rsp+58h+arg_10]
0x18011ad79  mov     r15d, [rsp+58h+arg_18]
0x18011ad7e  jmp     short loc_18011AD83
0x18011ad80  mov     sil, 1
0x18011ad83  lea     rcx, [rsp+58h+var_30]
0x18011ad88  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011ad8d  mov     dword ptr [rsp+58h+arg_10], 0
0x18011ad95  mov     [rsp+58h+arg_18], 0
0x18011ad9d  lea     rdx, [rsp+58h+arg_10]; enum ModernDeployment::Autopilot::Core::AttestationState *
0x18011ada2  mov     rcx, rdi; this
0x18011ada5  call    ?get_AttestationState@AttestationResultState@Core@Autopilot@ModernDeployment@@UEAAJPEAW4AttestationState@234@@Z; ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationState(ModernDeployment::Autopilot::Core::AttestationState *)
0x18011adaa  mov     ebx, eax
0x18011adac  test    eax, eax
0x18011adae  jns     short loc_18011ADDB
0x18011adb0  mov     rcx, [rsp+58h]; this
0x18011adb5  mov     r9d, eax; char *
0x18011adb8  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011adbf  mov     edx, 266h; void *
0x18011adc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011adc9  nop
0x18011adca  lea     rcx, [rsp+58h+var_38]
0x18011adcf  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x18011add4  mov     eax, ebx
0x18011add6  jmp     loc_18011AF17
0x18011addb  lea     rdx, [rsp+58h+arg_18]; int *
0x18011ade0  mov     rcx, rdi; this
0x18011ade3  call    ?get_AttestationResult@AttestationResultState@Core@Autopilot@ModernDeployment@@UEAAJPEAJ@Z; ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationResult(long *)
0x18011ade8  mov     ebx, eax
0x18011adea  test    eax, eax
0x18011adec  jns     short loc_18011AE19
0x18011adee  mov     rcx, [rsp+58h]; this
0x18011adf3  mov     r9d, eax; char *
0x18011adf6  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011adfd  mov     edx, 267h; void *
0x18011ae02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ae07  nop
0x18011ae08  lea     rcx, [rsp+58h+var_38]
0x18011ae0d  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x18011ae12  mov     eax, ebx
0x18011ae14  jmp     loc_18011AF17
0x18011ae19  cmp     r14d, dword ptr [rsp+58h+arg_10]
0x18011ae1e  jnz     short loc_18011AE27
0x18011ae20  cmp     r15d, [rsp+58h+arg_18]
0x18011ae25  jz      short loc_18011AE2A
0x18011ae27  mov     sil, 1
0x18011ae2a  mov     rcx, r12; SRWLock
0x18011ae2d  call    cs:__imp_AcquireSRWLockExclusive
0x18011ae34  nop     dword ptr [rax+rax+00h]
0x18011ae39  mov     [rsp+58h+arg_10], r12
0x18011ae3e  lea     rdx, [r13+40h]
0x18011ae42  mov     rcx, rdi
0x18011ae45  call    ?CloneAttestationResultState@AttestationHelpers@Core@Autopilot@ModernDeployment@@SAJPEAUIAttestationResultState@234@AEAV?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@@Z; ModernDeployment::Autopilot::Core::AttestationHelpers::CloneAttestationResultState(ModernDeployment::Autopilot::Core::IAttestationResultState *,wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy> &)
0x18011ae4a  mov     ebx, eax
0x18011ae4c  test    eax, eax
0x18011ae4e  jns     short loc_18011AE86
0x18011ae50  mov     rcx, [rsp+58h]; this
0x18011ae55  mov     r9d, eax; char *
0x18011ae58  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011ae5f  mov     edx, 272h; void *
0x18011ae64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ae69  nop
0x18011ae6a  lea     rcx, [rsp+58h+arg_10]
0x18011ae6f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011ae74  nop
0x18011ae75  lea     rcx, [rsp+58h+var_38]
0x18011ae7a  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x18011ae7f  mov     eax, ebx
0x18011ae81  jmp     loc_18011AF17
0x18011ae86  lea     rcx, [rsp+58h+arg_10]
0x18011ae8b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011ae90  test    sil, sil
0x18011ae93  jz      short loc_18011AEE3
0x18011ae95  mov     rcx, [r13+20h]
0x18011ae99  mov     rcx, [rcx]
0x18011ae9c  mov     [rsp+58h+arg_10], rcx
0x18011aea1  cmp     byte ptr [rcx+19h], 0
0x18011aea5  jnz     short loc_18011AEE3
0x18011aea7  add     rcx, 30h ; '0'
0x18011aeab  mov     rdx, qword ptr [rsp+58h+var_38]
0x18011aeb0  call    ??R?$_Func_class@JPEAUIDeploymentSessionHeartbeatRequestedEventArgs@Setup@Management@Windows@@@std@@QEBAJPEAUIDeploymentSessionHeartbeatRequestedEventArgs@Setup@Management@Windows@@@Z; std::_Func_class<long,Windows::Management::Setup::IDeploymentSessionHeartbeatRequestedEventArgs *>::operator()(Windows::Management::Setup::IDeploymentSessionHeartbeatRequestedEventArgs *)
0x18011aeb5  test    eax, eax
0x18011aeb7  jns     short loc_18011AED2
0x18011aeb9  mov     rcx, [rsp+58h]; this
0x18011aebe  mov     r9d, eax; char *
0x18011aec1  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011aec8  mov     edx, 27Ah; void *
0x18011aecd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18011aed2  lea     rcx, [rsp+58h+arg_10]
0x18011aed7  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVMachineProvisioningProgressReporter@Setup@Management@Windows@@V?$shared_ptr@V?$AsyncEventSourceT@U?$ITypedEventHandler@PEAVMachineProvisioningProgressReporter@Setup@Management@Windows@@PEAVDeploymentSessionStateChangedEventArgs@234@@Foundation@Windows@@VGitEventSourceSupportsAgile@Internal@3@U?$InvokeModeOptions@$01@WRL@Microsoft@@$00Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Windows::Management::Setup::MachineProvisioningProgressReporter * const,std::shared_ptr<wil::AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::Management::Setup::MachineProvisioningProgressReporter *,Windows::Management::Setup::DeploymentSessionStateChangedEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy>>>>>,std::_Iterator_base0>::operator++(void)
0x18011aedc  mov     rcx, [rsp+58h+arg_10]
0x18011aee1  jmp     short loc_18011AEA1
0x18011aee3  lea     rcx, [rsp+58h+var_38]
0x18011aee8  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x18011aeed  xor     eax, eax
0x18011aeef  jmp     short loc_18011AF17
0x18011aef1  mov     rcx, [rsp+58h]; this
0x18011aef6  mov     ebx, 80004001h
0x18011aefb  mov     r9d, ebx; char *
0x18011aefe  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011af05  mov     edx, 249h; void *
0x18011af0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011af0f  mov     eax, ebx
0x18011af11  jmp     short loc_18011AF17
0x18011af13  mov     eax, dword ptr [rsp+58h+arg_10]
0x18011af17  mov     rbx, [rsp+58h+arg_0]
0x18011af1c  mov     rsi, [rsp+58h+arg_8]
0x18011af21  add     rsp, 30h
0x18011af25  pop     r15
0x18011af27  pop     r14
0x18011af29  pop     r13
0x18011af2b  pop     r12
0x18011af2d  pop     rdi
0x18011af2e  retn
```
