# ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::PerformAttestation(ModernDeployment::Autopilot::Core::IAttestationConfiguration *)

- ea: `0x180117750`
- end: `0x180117c12`
- name: `?PerformAttestation@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@UEAAJPEAUIAttestationConfiguration@234@@Z`
- size: `1218`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *__hidden this, struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006e0a8`
- `0x180077384`
- `0x1800801fc`
- `0x1800806b0`
- `0x180080708`
- `0x180093a28`
- `0x180112420`
- `0x180115bbc`
- `0x1801166f8`
- `0x180117750`
- `0x180117e0c`
- `0x18011e1c0`
- `0x1801216b8`
- `0x180122fd8`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011785a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180117b63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011785a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180117b63`

## string_xrefs

- `0x18011779b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x1801177c8`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011780c`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011783b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011789e`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011793b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x1801179e8`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x180117ad8`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x180117b15`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x180117bce`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::PerformAttestation(
        RTL_SRWLOCK *this,
        struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *a2)
{
  int v5; // eax
  unsigned int v6; // ebx
  int Instance; // eax
  unsigned int v8; // edi
  PVOID Ptr; // rcx
  __int64 v10; // rcx
  int v11; // eax
  PVOID v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  PVOID v15; // rcx
  __int64 v16; // rcx
  int updated; // eax
  unsigned int v18; // ebx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // [rsp+20h] [rbp-78h]
  bool v28; // [rsp+30h] [rbp-68h] BYREF
  RTL_SRWLOCK *v29; // [rsp+38h] [rbp-60h] BYREF
  std::_Ref_count_base *v30[2]; // [rsp+40h] [rbp-58h] BYREF
  std::_Ref_count_base *v31[2]; // [rsp+50h] [rbp-48h] BYREF
  int v32; // [rsp+60h] [rbp-38h] BYREF
  std::_Ref_count_base *v33[2]; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)0x80004001LL,
      v27);
    return 2147500033LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)0x80070057LL,
      v27);
    return 2147942487LL;
  }
  v32 = 0;
  v5 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)(unsigned int)v5,
      v27);
    return v6;
  }
  if ( v32 != 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)0x80004001LL,
      v27);
    return 2147500033LL;
  }
  AcquireSRWLockExclusive(this + 3);
  v29 = this + 3;
  if ( (PVOID)((char *)this[10].Ptr - (char *)this[9].Ptr) < (PVOID)0x10 )
  {
    *(_OWORD *)v30 = 0;
    Instance = ModernDeployment::Autopilot::Core::TpmIsReadyProvider::CreateInstance(v30);
    v8 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
        (const char *)(unsigned int)Instance,
        v27);
      if ( v30[1] )
        std::_Ref_count_base::_Decref(v30[1]);
LABEL_37:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
      return v8;
    }
    Ptr = this[10].Ptr;
    if ( Ptr == this[11].Ptr )
    {
      std::vector<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider>>::_Emplace_reallocate<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &>(
        &this[9],
        this[10].Ptr,
        v30);
    }
    else
    {
      std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
        Ptr,
        v30);
      this[10].Ptr = (char *)this[10].Ptr + 16;
    }
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(v10, AutopilotAttestationStateMachineCreateProvider, 1);
    *(_OWORD *)v31 = 0;
    v11 = ModernDeployment::Autopilot::Core::AikCertAttestationProvider::CreateInstance(v31);
    v8 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
        (const char *)(unsigned int)v11,
        v27);
      if ( v31[1] )
        std::_Ref_count_base::_Decref(v31[1]);
      if ( v30[1] )
        std::_Ref_count_base::_Decref(v30[1]);
      goto LABEL_37;
    }
    v12 = this[10].Ptr;
    if ( v12 == this[11].Ptr )
    {
      std::vector<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider>>::_Emplace_reallocate<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &>(
        &this[9],
        this[10].Ptr,
        v31);
    }
    else
    {
      std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
        v12,
        v31);
      this[10].Ptr = (char *)this[10].Ptr + 16;
    }
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(v13, AutopilotAttestationStateMachineCreateProvider, 2);
    *(_OWORD *)v33 = 0;
    v14 = ModernDeployment::Autopilot::Core::MsaAttestationProvider::CreateInstance(v33);
    v8 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
        (const char *)(unsigned int)v14,
        v27);
      if ( v33[1] )
        std::_Ref_count_base::_Decref(v33[1]);
      if ( v31[1] )
        std::_Ref_count_base::_Decref(v31[1]);
      if ( v30[1] )
        std::_Ref_count_base::_Decref(v30[1]);
      goto LABEL_37;
    }
    v15 = this[10].Ptr;
    if ( v15 == this[11].Ptr )
    {
      std::vector<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider>>::_Emplace_reallocate<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &>(
        &this[9],
        this[10].Ptr,
        v33);
    }
    else
    {
      std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
        v15,
        v33);
      this[10].Ptr = (char *)this[10].Ptr + 16;
    }
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(v16, AutopilotAttestationStateMachineCreateProvider, 4);
    if ( v33[1] )
      std::_Ref_count_base::_Decref(v33[1]);
    if ( v31[1] )
      std::_Ref_count_base::_Decref(v31[1]);
    if ( v30[1] )
      std::_Ref_count_base::_Decref(v30[1]);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
  updated = ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::UpdateAttestationConfiguration(
              (ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *)this,
              a2);
  v18 = updated;
  if ( updated >= 0 )
  {
    v28 = 0;
    v19 = ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::DetermineOverallState(
            (ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *)this,
            0,
            &v28);
    v22 = v19;
    if ( v19 >= 0 )
    {
      if ( v28 )
      {
        if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(v20, AutopilotAttestationAlreadyComplete, v21, 1, v33);
        return 0;
      }
      else
      {
        AcquireSRWLockExclusive(this + 3);
        v29 = this + 3;
        if ( LOBYTE(this[7].Ptr) )
        {
          if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
            McGenEventWrite_EventWriteTransfer(v23, AutopilotAttestationAlreadyInProgress, v24, 1, v33);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
          return 0;
        }
        else
        {
          LOBYTE(this[7].Ptr) = 1;
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
          v25 = ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait((ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *)this);
          v26 = v25;
          if ( v25 >= 0 )
          {
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9F,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
              (const char *)(unsigned int)v25,
              v27);
            return v26;
          }
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
        (const char *)(unsigned int)v19,
        v27);
      return v22;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\autopilotattestationstatemachine.cpp",
      (const char *)(unsigned int)updated,
      v27);
    return v18;
  }
}

```

## disassembly

```asm
0x180117750  mov     [rsp+arg_10], rbx
0x180117755  mov     [rsp+arg_18], rsi
0x18011775a  push    rdi
0x18011775b  push    r14
0x18011775d  push    r15
0x18011775f  sub     rsp, 80h
0x180117766  mov     rax, cs:__security_cookie
0x18011776d  xor     rax, rsp
0x180117770  mov     [rsp+98h+var_20], rax
0x180117775  mov     r14, rdx
0x180117778  mov     rsi, rcx
0x18011777b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180117782  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180117787  test    al, al
0x180117789  jnz     short loc_1801177B3
0x18011778b  mov     rcx, [rsp+98h]; this
0x180117793  mov     ebx, 80004001h
0x180117798  mov     r9d, ebx; char *
0x18011779b  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801177a2  mov     edx, 58h ; 'X'; void *
0x1801177a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801177ac  mov     eax, ebx
0x1801177ae  jmp     loc_180117BEB
0x1801177b3  test    r14, r14
0x1801177b6  jnz     short loc_1801177DF
0x1801177b8  mov     rcx, [rsp+98h]; this
0x1801177c0  mov     ebx, 80070057h
0x1801177c5  mov     r9d, ebx; char *
0x1801177c8  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801177cf  lea     edx, [r14+59h]; void *
0x1801177d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801177d8  mov     eax, ebx
0x1801177da  jmp     loc_180117BEB
0x1801177df  mov     [rsp+98h+var_38], 0
0x1801177e7  mov     rax, [r14]
0x1801177ea  lea     rdx, [rsp+98h+var_38]
0x1801177ef  mov     rcx, r14
0x1801177f2  mov     rax, [rax+40h]
0x1801177f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801177fb  mov     ebx, eax
0x1801177fd  test    eax, eax
0x1801177ff  jns     short loc_180117824
0x180117801  mov     rcx, [rsp+98h]; this
0x180117809  mov     r9d, eax; char *
0x18011780c  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117813  mov     edx, 63h ; 'c'; void *
0x180117818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011781d  mov     eax, ebx
0x18011781f  jmp     loc_180117BEB
0x180117824  cmp     [rsp+98h+var_38], 1
0x180117829  jz      short loc_180117853
0x18011782b  mov     rcx, [rsp+98h]; this
0x180117833  mov     ebx, 80004001h
0x180117838  mov     r9d, ebx; char *
0x18011783b  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117842  mov     edx, 64h ; 'd'; void *
0x180117847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011784c  mov     eax, ebx
0x18011784e  jmp     loc_180117BEB
0x180117853  lea     r15, [rsi+18h]
0x180117857  mov     rcx, r15; SRWLock
0x18011785a  call    cs:__imp_AcquireSRWLockExclusive
0x180117860  mov     [rsp+98h+var_60], r15
0x180117865  lea     rbx, [rsi+48h]
0x180117869  mov     rax, [rbx+8]
0x18011786d  sub     rax, [rbx]
0x180117870  cmp     rax, 10h
0x180117874  jnb     loc_180117AB2
0x18011787a  xorps   xmm0, xmm0
0x18011787d  movdqu  xmmword ptr [rsp+98h+var_58], xmm0
0x180117883  lea     rcx, [rsp+98h+var_58]
0x180117888  call    ?CreateInstance@TpmIsReadyProvider@Core@Autopilot@ModernDeployment@@SAJAEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@Z; ModernDeployment::Autopilot::Core::TpmIsReadyProvider::CreateInstance(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> &)
0x18011788d  mov     edi, eax
0x18011788f  test    eax, eax
0x180117891  jns     short loc_1801178D1
0x180117893  mov     rcx, [rsp+98h]; this
0x18011789b  mov     r9d, eax; char *
0x18011789e  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801178a5  mov     edx, 6Eh ; 'n'; void *
0x1801178aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801178af  nop
0x1801178b0  mov     rcx, [rsp+98h+var_58+8]; this
0x1801178b5  test    rcx, rcx
0x1801178b8  jz      short loc_1801178C0
0x1801178ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801178bf  nop
0x1801178c0  lea     rcx, [rsp+98h+var_60]
0x1801178c5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801178ca  mov     eax, edi
0x1801178cc  jmp     loc_180117BEB
0x1801178d1  mov     rcx, [rbx+8]
0x1801178d5  cmp     rcx, [rbx+10h]
0x1801178d9  jz      short loc_1801178EC
0x1801178db  lea     rdx, [rsp+98h+var_58]
0x1801178e0  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x1801178e5  add     qword ptr [rbx+8], 10h
0x1801178ea  jmp     short loc_1801178FC
0x1801178ec  lea     r8, [rsp+98h+var_58]
0x1801178f1  mov     rdx, rcx
0x1801178f4  mov     rcx, rbx
0x1801178f7  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@?$vector@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@V?$allocator@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider>>::_Emplace_reallocate<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &>(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> * const,std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &)
0x1801178fc  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180117903  jz      short loc_180117917
0x180117905  mov     r8d, 1
0x18011790b  lea     rdx, AutopilotAttestationStateMachineCreateProvider
0x180117912  call    McTemplateU0q_EventWriteTransfer
0x180117917  xorps   xmm0, xmm0
0x18011791a  movdqu  xmmword ptr [rsp+98h+var_48], xmm0
0x180117920  lea     rcx, [rsp+98h+var_48]
0x180117925  call    ?CreateInstance@AikCertAttestationProvider@Core@Autopilot@ModernDeployment@@SAJAEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@Z; ModernDeployment::Autopilot::Core::AikCertAttestationProvider::CreateInstance(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> &)
0x18011792a  mov     edi, eax
0x18011792c  test    eax, eax
0x18011792e  jns     short loc_18011797E
0x180117930  mov     rcx, [rsp+98h]; this
0x180117938  mov     r9d, eax; char *
0x18011793b  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117942  mov     edx, 74h ; 't'; void *
0x180117947  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011794c  nop
0x18011794d  mov     rcx, [rsp+98h+var_48+8]; this
0x180117952  test    rcx, rcx
0x180117955  jz      short loc_18011795D
0x180117957  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011795c  nop
0x18011795d  mov     rcx, [rsp+98h+var_58+8]; this
0x180117962  test    rcx, rcx
0x180117965  jz      short loc_18011796D
0x180117967  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011796c  nop
0x18011796d  lea     rcx, [rsp+98h+var_60]
0x180117972  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180117977  mov     eax, edi
0x180117979  jmp     loc_180117BEB
0x18011797e  mov     rcx, [rbx+8]
0x180117982  cmp     rcx, [rbx+10h]
0x180117986  jz      short loc_180117999
0x180117988  lea     rdx, [rsp+98h+var_48]
0x18011798d  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180117992  add     qword ptr [rbx+8], 10h
0x180117997  jmp     short loc_1801179A9
0x180117999  lea     r8, [rsp+98h+var_48]
0x18011799e  mov     rdx, rcx
0x1801179a1  mov     rcx, rbx
0x1801179a4  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@?$vector@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@V?$allocator@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider>>::_Emplace_reallocate<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &>(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> * const,std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &)
0x1801179a9  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1801179b0  jz      short loc_1801179C4
0x1801179b2  mov     r8d, 2
0x1801179b8  lea     rdx, AutopilotAttestationStateMachineCreateProvider
0x1801179bf  call    McTemplateU0q_EventWriteTransfer
0x1801179c4  xorps   xmm0, xmm0
0x1801179c7  movdqu  xmmword ptr [rsp+98h+var_30], xmm0
0x1801179cd  lea     rcx, [rsp+98h+var_30]
0x1801179d2  call    ?CreateInstance@MsaAttestationProvider@Core@Autopilot@ModernDeployment@@SAJAEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@Z; ModernDeployment::Autopilot::Core::MsaAttestationProvider::CreateInstance(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> &)
0x1801179d7  mov     edi, eax
0x1801179d9  test    eax, eax
0x1801179db  jns     short loc_180117A3B
0x1801179dd  mov     rcx, [rsp+98h]; this
0x1801179e5  mov     r9d, eax; char *
0x1801179e8  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801179ef  mov     edx, 7Ah ; 'z'; void *
0x1801179f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801179f9  nop
0x1801179fa  mov     rcx, [rsp+98h+var_30+8]; this
0x1801179ff  test    rcx, rcx
0x180117a02  jz      short loc_180117A0A
0x180117a04  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180117a09  nop
0x180117a0a  mov     rcx, [rsp+98h+var_48+8]; this
0x180117a0f  test    rcx, rcx
0x180117a12  jz      short loc_180117A1A
0x180117a14  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180117a19  nop
0x180117a1a  mov     rcx, [rsp+98h+var_58+8]; this
0x180117a1f  test    rcx, rcx
0x180117a22  jz      short loc_180117A2A
0x180117a24  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180117a29  nop
0x180117a2a  lea     rcx, [rsp+98h+var_60]
0x180117a2f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180117a34  mov     eax, edi
0x180117a36  jmp     loc_180117BEB
0x180117a3b  mov     rcx, [rbx+8]
0x180117a3f  cmp     rcx, [rbx+10h]
0x180117a43  jz      short loc_180117A56
0x180117a45  lea     rdx, [rsp+98h+var_30]
0x180117a4a  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180117a4f  add     qword ptr [rbx+8], 10h
0x180117a54  jmp     short loc_180117A66
0x180117a56  lea     r8, [rsp+98h+var_30]
0x180117a5b  mov     rdx, rcx
0x180117a5e  mov     rcx, rbx
0x180117a61  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@?$vector@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@V?$allocator@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider>>::_Emplace_reallocate<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &>(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> * const,std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &)
0x180117a66  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180117a6d  jz      short loc_180117A82
0x180117a6f  mov     r8d, 4
0x180117a75  lea     rdx, AutopilotAttestationStateMachineCreateProvider
0x180117a7c  call    McTemplateU0q_EventWriteTransfer
0x180117a81  nop
0x180117a82  mov     rcx, [rsp+98h+var_30+8]; this
0x180117a87  test    rcx, rcx
0x180117a8a  jz      short loc_180117A92
0x180117a8c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180117a91  nop
0x180117a92  mov     rcx, [rsp+98h+var_48+8]; this
0x180117a97  test    rcx, rcx
0x180117a9a  jz      short loc_180117AA2
0x180117a9c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180117aa1  nop
0x180117aa2  mov     rcx, [rsp+98h+var_58+8]; this
0x180117aa7  test    rcx, rcx
0x180117aaa  jz      short loc_180117AB2
0x180117aac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180117ab1  nop
0x180117ab2  lea     rcx, [rsp+98h+var_60]
0x180117ab7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180117abc  mov     rdx, r14; struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *
0x180117abf  mov     rcx, rsi; this
0x180117ac2  call    ?UpdateAttestationConfiguration@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJPEAUIAttestationConfiguration@234@@Z; ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::UpdateAttestationConfiguration(ModernDeployment::Autopilot::Core::IAttestationConfiguration *)
0x180117ac7  mov     ebx, eax
0x180117ac9  test    eax, eax
0x180117acb  jns     short loc_180117AF0
0x180117acd  mov     rcx, [rsp+98h]; this
0x180117ad5  mov     r9d, eax; char *
0x180117ad8  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117adf  mov     edx, 82h; void *
0x180117ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117ae9  mov     eax, ebx
0x180117aeb  jmp     loc_180117BEB
0x180117af0  mov     [rsp+98h+var_68], 0
0x180117af5  lea     r8, [rsp+98h+var_68]; bool *
0x180117afa  xor     edx, edx; bool
0x180117afc  mov     rcx, rsi; this
0x180117aff  call    ?DetermineOverallState@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJ_NAEA_N@Z; ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::DetermineOverallState(bool,bool &)
0x180117b04  mov     ebx, eax
0x180117b06  test    eax, eax
0x180117b08  jns     short loc_180117B2D
0x180117b0a  mov     rcx, [rsp+98h]; this
0x180117b12  mov     r9d, eax; char *
0x180117b15  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117b1c  mov     edx, 88h; void *
0x180117b21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117b26  mov     eax, ebx
0x180117b28  jmp     loc_180117BEB
0x180117b2d  cmp     [rsp+98h+var_68], 0
0x180117b32  jz      short loc_180117B60
0x180117b34  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180117b3b  jz      short loc_180117B59
0x180117b3d  lea     rax, [rsp+98h+var_30]
0x180117b42  mov     qword ptr [rsp+98h+var_78], rax
0x180117b47  mov     r9d, 1
0x180117b4d  lea     rdx, AutopilotAttestationAlreadyComplete
0x180117b54  call    McGenEventWrite_EventWriteTransfer
0x180117b59  xor     eax, eax
0x180117b5b  jmp     loc_180117BEB
0x180117b60  mov     rcx, r15; SRWLock
0x180117b63  call    cs:__imp_AcquireSRWLockExclusive
0x180117b69  mov     [rsp+98h+var_60], r15
0x180117b6e  cmp     byte ptr [rsi+38h], 0
0x180117b72  jz      short loc_180117BA7
0x180117b74  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180117b7b  jz      short loc_180117B99
0x180117b7d  lea     rax, [rsp+98h+var_30]
0x180117b82  mov     qword ptr [rsp+98h+var_78], rax
0x180117b87  mov     r9d, 1
0x180117b8d  lea     rdx, AutopilotAttestationAlreadyInProgress
0x180117b94  call    McGenEventWrite_EventWriteTransfer
0x180117b99  lea     rcx, [rsp+98h+var_60]
0x180117b9e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180117ba3  xor     eax, eax
0x180117ba5  jmp     short loc_180117BEB
0x180117ba7  mov     byte ptr [rsi+38h], 1
0x180117bab  lea     rcx, [rsp+98h+var_60]
0x180117bb0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180117bb5  mov     rcx, rsi; this
0x180117bb8  call    ?ExecuteProvidersBlockWait@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJXZ; ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait(void)
0x180117bbd  mov     ebx, eax
0x180117bbf  test    eax, eax
0x180117bc1  jns     short loc_180117BE3
0x180117bc3  mov     rcx, [rsp+98h]; this
0x180117bcb  mov     r9d, eax; char *
0x180117bce  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x180117bd5  mov     edx, 9Fh; void *
0x180117bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117bdf  mov     eax, ebx
0x180117be1  jmp     short loc_180117BEB
0x180117be3  xor     eax, eax
0x180117be5  jmp     short loc_180117BEB
0x180117be7  mov     eax, [rsp+98h+var_38]
0x180117beb  mov     rcx, [rsp+98h+var_20]
0x180117bf0  xor     rcx, rsp; StackCookie
0x180117bf3  call    __security_check_cookie
0x180117bf8  lea     r11, [rsp+98h+var_18]
0x180117c00  mov     rbx, [r11+30h]
0x180117c04  mov     rsi, [r11+38h]
0x180117c08  mov     rsp, r11
0x180117c0b  pop     r15
0x180117c0d  pop     r14
0x180117c0f  pop     rdi
0x180117c10  retn
```
