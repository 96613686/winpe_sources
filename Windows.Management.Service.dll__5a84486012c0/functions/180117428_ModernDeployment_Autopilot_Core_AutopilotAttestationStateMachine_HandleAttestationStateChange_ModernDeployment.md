# ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::HandleAttestationStateChange(ModernDeployment::Autopilot::Core::AttestationResultState *)

- ea: `0x180117428`
- end: `0x180117740`
- name: `?HandleAttestationStateChange@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJPEAVAttestationResultState@234@@Z`
- size: `792`
- prototype: `int(ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *__hidden this, struct ModernDeployment::Autopilot::Core::AttestationResultState *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180115bbc`
- `0x1801166f8`
- `0x180119a00`

## callees

- `0x180067a54`
- `0x18006df20`
- `0x18006e0a8`
- `0x18006e0c8`
- `0x18007748c`
- `0x1800801fc`
- `0x1800ea37c`
- `0x1800fc62c`
- `0x180117428`
- `0x18011bb50`
- `0x18011c780`
- `0x18011c810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801174e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801174e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180117643`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180117643`

## string_xrefs

- `0x18011746b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x1801174a7`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x180117511`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011755a`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x1801175ce`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011760c`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x180117668`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x1801176d1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011770e`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`

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
0x180117428  mov     [rsp+arg_0], rbx
0x18011742d  mov     [rsp+arg_8], rsi
0x180117432  push    rdi
0x180117433  push    r12
0x180117435  push    r13
0x180117437  push    r14
0x180117439  push    r15
0x18011743b  sub     rsp, 30h
0x18011743f  mov     rdi, rdx
0x180117442  mov     r13, rcx
0x180117445  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18011744c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180117451  test    al, al
0x180117453  jz      loc_180117701
0x180117459  test    rdi, rdi
0x18011745c  jnz     short loc_180117483
0x18011745e  mov     rcx, [rsp+58h]; this
0x180117463  mov     ebx, 80004003h
0x180117468  mov     r9d, ebx; char *
0x18011746b  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117472  mov     edx, 24Ah; void *
0x180117477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011747c  mov     eax, ebx
0x18011747e  jmp     loc_180117727
0x180117483  mov     qword ptr [rsp+58h+var_38], 0; int
0x18011748c  lea     rdx, [rsp+58h+var_38]
0x180117491  mov     rcx, rdi
0x180117494  call    ?CloneAttestationResultState@AttestationHelpers@Core@Autopilot@ModernDeployment@@SAJPEAUIAttestationResultState@234@AEAV?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@@Z; ModernDeployment::Autopilot::Core::AttestationHelpers::CloneAttestationResultState(ModernDeployment::Autopilot::Core::IAttestationResultState *,wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy> &)
0x180117499  mov     ebx, eax
0x18011749b  test    eax, eax
0x18011749d  jns     short loc_1801174CA
0x18011749f  mov     rcx, [rsp+58h]; this
0x1801174a4  mov     r9d, eax; char *
0x1801174a7  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801174ae  mov     edx, 24Fh; void *
0x1801174b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801174b8  nop
0x1801174b9  lea     rcx, [rsp+58h+var_38]
0x1801174be  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x1801174c3  mov     eax, ebx
0x1801174c5  jmp     loc_180117727
0x1801174ca  xor     r14d, r14d
0x1801174cd  mov     dword ptr [rsp+58h+arg_10], r14d
0x1801174d2  xor     r15d, r15d
0x1801174d5  mov     [rsp+58h+arg_18], r15d
0x1801174da  lea     r12, [r13+18h]
0x1801174de  mov     rcx, r12; SRWLock
0x1801174e1  call    cs:__imp_AcquireSRWLockShared
0x1801174e7  mov     [rsp+58h+var_30], r12
0x1801174ec  mov     rcx, [r13+40h]; this
0x1801174f0  test    rcx, rcx
0x1801174f3  jz      loc_180117596
0x1801174f9  lea     rdx, [rsp+58h+arg_10]; enum ModernDeployment::Autopilot::Core::AttestationState *
0x1801174fe  call    ?get_AttestationState@AttestationResultState@Core@Autopilot@ModernDeployment@@UEAAJPEAW4AttestationState@234@@Z; ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationState(ModernDeployment::Autopilot::Core::AttestationState *)
0x180117503  mov     ebx, eax
0x180117505  test    eax, eax
0x180117507  jns     short loc_18011753E
0x180117509  mov     rcx, [rsp+58h]; this
0x18011750e  mov     r9d, eax; char *
0x180117511  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117518  mov     edx, 25Ah; void *
0x18011751d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117522  lea     rcx, [rsp+58h+var_30]
0x180117527  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011752c  nop
0x18011752d  lea     rcx, [rsp+58h+var_38]
0x180117532  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x180117537  mov     eax, ebx
0x180117539  jmp     loc_180117727
0x18011753e  lea     rdx, [rsp+58h+arg_18]; int *
0x180117543  mov     rcx, [r13+40h]; this
0x180117547  call    ?get_AttestationResult@AttestationResultState@Core@Autopilot@ModernDeployment@@UEAAJPEAJ@Z; ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationResult(long *)
0x18011754c  mov     ebx, eax
0x18011754e  test    eax, eax
0x180117550  jns     short loc_180117587
0x180117552  mov     rcx, [rsp+58h]; this
0x180117557  mov     r9d, eax; char *
0x18011755a  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117561  mov     edx, 25Bh; void *
0x180117566  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011756b  lea     rcx, [rsp+58h+var_30]
0x180117570  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180117575  nop
0x180117576  lea     rcx, [rsp+58h+var_38]
0x18011757b  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x180117580  mov     eax, ebx
0x180117582  jmp     loc_180117727
0x180117587  xor     sil, sil
0x18011758a  mov     r14d, dword ptr [rsp+58h+arg_10]
0x18011758f  mov     r15d, [rsp+58h+arg_18]
0x180117594  jmp     short loc_180117599
0x180117596  mov     sil, 1
0x180117599  lea     rcx, [rsp+58h+var_30]
0x18011759e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801175a3  mov     dword ptr [rsp+58h+arg_10], 0
0x1801175ab  mov     [rsp+58h+arg_18], 0
0x1801175b3  lea     rdx, [rsp+58h+arg_10]; enum ModernDeployment::Autopilot::Core::AttestationState *
0x1801175b8  mov     rcx, rdi; this
0x1801175bb  call    ?get_AttestationState@AttestationResultState@Core@Autopilot@ModernDeployment@@UEAAJPEAW4AttestationState@234@@Z; ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationState(ModernDeployment::Autopilot::Core::AttestationState *)
0x1801175c0  mov     ebx, eax
0x1801175c2  test    eax, eax
0x1801175c4  jns     short loc_1801175F1
0x1801175c6  mov     rcx, [rsp+58h]; this
0x1801175cb  mov     r9d, eax; char *
0x1801175ce  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801175d5  mov     edx, 266h; void *
0x1801175da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801175df  nop
0x1801175e0  lea     rcx, [rsp+58h+var_38]
0x1801175e5  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x1801175ea  mov     eax, ebx
0x1801175ec  jmp     loc_180117727
0x1801175f1  lea     rdx, [rsp+58h+arg_18]; int *
0x1801175f6  mov     rcx, rdi; this
0x1801175f9  call    ?get_AttestationResult@AttestationResultState@Core@Autopilot@ModernDeployment@@UEAAJPEAJ@Z; ModernDeployment::Autopilot::Core::AttestationResultState::get_AttestationResult(long *)
0x1801175fe  mov     ebx, eax
0x180117600  test    eax, eax
0x180117602  jns     short loc_18011762F
0x180117604  mov     rcx, [rsp+58h]; this
0x180117609  mov     r9d, eax; char *
0x18011760c  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117613  mov     edx, 267h; void *
0x180117618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011761d  nop
0x18011761e  lea     rcx, [rsp+58h+var_38]
0x180117623  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x180117628  mov     eax, ebx
0x18011762a  jmp     loc_180117727
0x18011762f  cmp     r14d, dword ptr [rsp+58h+arg_10]
0x180117634  jnz     short loc_18011763D
0x180117636  cmp     r15d, [rsp+58h+arg_18]
0x18011763b  jz      short loc_180117640
0x18011763d  mov     sil, 1
0x180117640  mov     rcx, r12; SRWLock
0x180117643  call    cs:__imp_AcquireSRWLockExclusive
0x180117649  mov     [rsp+58h+arg_10], r12
0x18011764e  lea     rdx, [r13+40h]
0x180117652  mov     rcx, rdi
0x180117655  call    ?CloneAttestationResultState@AttestationHelpers@Core@Autopilot@ModernDeployment@@SAJPEAUIAttestationResultState@234@AEAV?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@@Z; ModernDeployment::Autopilot::Core::AttestationHelpers::CloneAttestationResultState(ModernDeployment::Autopilot::Core::IAttestationResultState *,wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy> &)
0x18011765a  mov     ebx, eax
0x18011765c  test    eax, eax
0x18011765e  jns     short loc_180117696
0x180117660  mov     rcx, [rsp+58h]; this
0x180117665  mov     r9d, eax; char *
0x180117668  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011766f  mov     edx, 272h; void *
0x180117674  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117679  nop
0x18011767a  lea     rcx, [rsp+58h+arg_10]
0x18011767f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180117684  nop
0x180117685  lea     rcx, [rsp+58h+var_38]
0x18011768a  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x18011768f  mov     eax, ebx
0x180117691  jmp     loc_180117727
0x180117696  lea     rcx, [rsp+58h+arg_10]
0x18011769b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801176a0  test    sil, sil
0x1801176a3  jz      short loc_1801176F3
0x1801176a5  mov     rcx, [r13+20h]
0x1801176a9  mov     rcx, [rcx]
0x1801176ac  mov     [rsp+58h+arg_10], rcx
0x1801176b1  cmp     byte ptr [rcx+19h], 0
0x1801176b5  jnz     short loc_1801176F3
0x1801176b7  add     rcx, 30h ; '0'
0x1801176bb  mov     rdx, qword ptr [rsp+58h+var_38]
0x1801176c0  call    ??R?$_Func_class@JPEAUIDeploymentSessionHeartbeatRequestedEventArgs@Setup@Management@Windows@@@std@@QEBAJPEAUIDeploymentSessionHeartbeatRequestedEventArgs@Setup@Management@Windows@@@Z; std::_Func_class<long,Windows::Management::Setup::IDeploymentSessionHeartbeatRequestedEventArgs *>::operator()(Windows::Management::Setup::IDeploymentSessionHeartbeatRequestedEventArgs *)
0x1801176c5  test    eax, eax
0x1801176c7  jns     short loc_1801176E2
0x1801176c9  mov     rcx, [rsp+58h]; this
0x1801176ce  mov     r9d, eax; char *
0x1801176d1  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801176d8  mov     edx, 27Ah; void *
0x1801176dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801176e2  lea     rcx, [rsp+58h+arg_10]
0x1801176e7  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVMachineProvisioningProgressReporter@Setup@Management@Windows@@V?$shared_ptr@V?$AsyncEventSourceT@U?$ITypedEventHandler@PEAVMachineProvisioningProgressReporter@Setup@Management@Windows@@PEAVDeploymentSessionStateChangedEventArgs@234@@Foundation@Windows@@VGitEventSourceSupportsAgile@Internal@3@U?$InvokeModeOptions@$01@WRL@Microsoft@@$00Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Windows::Management::Setup::MachineProvisioningProgressReporter * const,std::shared_ptr<wil::AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::Management::Setup::MachineProvisioningProgressReporter *,Windows::Management::Setup::DeploymentSessionStateChangedEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy>>>>>,std::_Iterator_base0>::operator++(void)
0x1801176ec  mov     rcx, [rsp+58h+arg_10]
0x1801176f1  jmp     short loc_1801176B1
0x1801176f3  lea     rcx, [rsp+58h+var_38]
0x1801176f8  call    ??1?$com_ptr_t@VAttestationResultState@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationResultState,wil::err_returncode_policy>(void)
0x1801176fd  xor     eax, eax
0x1801176ff  jmp     short loc_180117727
0x180117701  mov     rcx, [rsp+58h]; this
0x180117706  mov     ebx, 80004001h
0x18011770b  mov     r9d, ebx; char *
0x18011770e  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117715  mov     edx, 249h; void *
0x18011771a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011771f  mov     eax, ebx
0x180117721  jmp     short loc_180117727
0x180117723  mov     eax, dword ptr [rsp+58h+arg_10]
0x180117727  mov     rbx, [rsp+58h+arg_0]
0x18011772c  mov     rsi, [rsp+58h+arg_8]
0x180117731  add     rsp, 30h
0x180117735  pop     r15
0x180117737  pop     r14
0x180117739  pop     r13
0x18011773b  pop     r12
0x18011773d  pop     rdi
0x18011773e  retn
```
