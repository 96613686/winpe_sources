# ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::PerformAttestation(ModernDeployment::Autopilot::Core::IAttestationConfiguration *)

- ea: `0x18011af40`
- end: `0x18011b40e`
- name: `?PerformAttestation@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@UEAAJPEAUIAttestationConfiguration@234@@Z`
- size: `1230`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine *__hidden this, struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e608`
- `0x180077c04`
- `0x180080c10`
- `0x1800810f0`
- `0x180081150`
- `0x180094ce0`
- `0x1801159d0`
- `0x180119350`
- `0x180119eac`
- `0x18011af40`
- `0x18011b610`
- `0x180121c70`
- `0x180125274`
- `0x180126b28`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011b04a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011b359`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011b04a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011b359`

## string_xrefs

- `0x18011af8b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011afb8`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011affc`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011b02b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011b094`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011b131`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011b1de`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011b2ce`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011b30b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`
- `0x18011b3ca`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\autopilotattestationstatemachine.cpp`

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
          McGenEventWrite_EventWriteTransfer(v20, AutopilotAttestationAlreadyComplete, v21, 1);
        return 0;
      }
      else
      {
        AcquireSRWLockExclusive(this + 3);
        v29 = this + 3;
        if ( LOBYTE(this[7].Ptr) )
        {
          if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
            McGenEventWrite_EventWriteTransfer(v23, AutopilotAttestationAlreadyInProgress, v24, 1);
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
0x18011af40  mov     [rsp+arg_10], rbx
0x18011af45  mov     [rsp+arg_18], rsi
0x18011af4a  push    rdi
0x18011af4b  push    r14
0x18011af4d  push    r15
0x18011af4f  sub     rsp, 80h
0x18011af56  mov     rax, cs:__security_cookie
0x18011af5d  xor     rax, rsp
0x18011af60  mov     [rsp+98h+var_20], rax
0x18011af65  mov     r14, rdx
0x18011af68  mov     rsi, rcx
0x18011af6b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18011af72  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18011af77  test    al, al
0x18011af79  jnz     short loc_18011AFA3
0x18011af7b  mov     rcx, [rsp+98h]; this
0x18011af83  mov     ebx, 80004001h
0x18011af88  mov     r9d, ebx; char *
0x18011af8b  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011af92  mov     edx, 58h ; 'X'; void *
0x18011af97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011af9c  mov     eax, ebx
0x18011af9e  jmp     loc_18011B3E7
0x18011afa3  test    r14, r14
0x18011afa6  jnz     short loc_18011AFCF
0x18011afa8  mov     rcx, [rsp+98h]; this
0x18011afb0  mov     ebx, 80070057h
0x18011afb5  mov     r9d, ebx; char *
0x18011afb8  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011afbf  lea     edx, [r14+59h]; void *
0x18011afc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011afc8  mov     eax, ebx
0x18011afca  jmp     loc_18011B3E7
0x18011afcf  mov     [rsp+98h+var_38], 0
0x18011afd7  mov     rax, [r14]
0x18011afda  lea     rdx, [rsp+98h+var_38]
0x18011afdf  mov     rcx, r14
0x18011afe2  mov     rax, [rax+40h]
0x18011afe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011afeb  mov     ebx, eax
0x18011afed  test    eax, eax
0x18011afef  jns     short loc_18011B014
0x18011aff1  mov     rcx, [rsp+98h]; this
0x18011aff9  mov     r9d, eax; char *
0x18011affc  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011b003  mov     edx, 63h ; 'c'; void *
0x18011b008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011b00d  mov     eax, ebx
0x18011b00f  jmp     loc_18011B3E7
0x18011b014  cmp     [rsp+98h+var_38], 1
0x18011b019  jz      short loc_18011B043
0x18011b01b  mov     rcx, [rsp+98h]; this
0x18011b023  mov     ebx, 80004001h
0x18011b028  mov     r9d, ebx; char *
0x18011b02b  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011b032  mov     edx, 64h ; 'd'; void *
0x18011b037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011b03c  mov     eax, ebx
0x18011b03e  jmp     loc_18011B3E7
0x18011b043  lea     r15, [rsi+18h]
0x18011b047  mov     rcx, r15; SRWLock
0x18011b04a  call    cs:__imp_AcquireSRWLockExclusive
0x18011b051  nop     dword ptr [rax+rax+00h]
0x18011b056  mov     [rsp+98h+var_60], r15
0x18011b05b  lea     rbx, [rsi+48h]
0x18011b05f  mov     rax, [rbx+8]
0x18011b063  sub     rax, [rbx]
0x18011b066  cmp     rax, 10h
0x18011b06a  jnb     loc_18011B2A8
0x18011b070  xorps   xmm0, xmm0
0x18011b073  movdqu  xmmword ptr [rsp+98h+var_58], xmm0
0x18011b079  lea     rcx, [rsp+98h+var_58]
0x18011b07e  call    ?CreateInstance@TpmIsReadyProvider@Core@Autopilot@ModernDeployment@@SAJAEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@Z; ModernDeployment::Autopilot::Core::TpmIsReadyProvider::CreateInstance(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> &)
0x18011b083  mov     edi, eax
0x18011b085  test    eax, eax
0x18011b087  jns     short loc_18011B0C7
0x18011b089  mov     rcx, [rsp+98h]; this
0x18011b091  mov     r9d, eax; char *
0x18011b094  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011b09b  mov     edx, 6Eh ; 'n'; void *
0x18011b0a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011b0a5  nop
0x18011b0a6  mov     rcx, [rsp+98h+var_58+8]; this
0x18011b0ab  test    rcx, rcx
0x18011b0ae  jz      short loc_18011B0B6
0x18011b0b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011b0b5  nop
0x18011b0b6  lea     rcx, [rsp+98h+var_60]
0x18011b0bb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011b0c0  mov     eax, edi
0x18011b0c2  jmp     loc_18011B3E7
0x18011b0c7  mov     rcx, [rbx+8]
0x18011b0cb  cmp     rcx, [rbx+10h]
0x18011b0cf  jz      short loc_18011B0E2
0x18011b0d1  lea     rdx, [rsp+98h+var_58]
0x18011b0d6  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18011b0db  add     qword ptr [rbx+8], 10h
0x18011b0e0  jmp     short loc_18011B0F2
0x18011b0e2  lea     r8, [rsp+98h+var_58]
0x18011b0e7  mov     rdx, rcx
0x18011b0ea  mov     rcx, rbx
0x18011b0ed  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@?$vector@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@V?$allocator@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider>>::_Emplace_reallocate<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &>(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> * const,std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &)
0x18011b0f2  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18011b0f9  jz      short loc_18011B10D
0x18011b0fb  mov     r8d, 1
0x18011b101  lea     rdx, AutopilotAttestationStateMachineCreateProvider
0x18011b108  call    McTemplateU0q_EventWriteTransfer
0x18011b10d  xorps   xmm0, xmm0
0x18011b110  movdqu  xmmword ptr [rsp+98h+var_48], xmm0
0x18011b116  lea     rcx, [rsp+98h+var_48]
0x18011b11b  call    ?CreateInstance@AikCertAttestationProvider@Core@Autopilot@ModernDeployment@@SAJAEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@Z; ModernDeployment::Autopilot::Core::AikCertAttestationProvider::CreateInstance(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> &)
0x18011b120  mov     edi, eax
0x18011b122  test    eax, eax
0x18011b124  jns     short loc_18011B174
0x18011b126  mov     rcx, [rsp+98h]; this
0x18011b12e  mov     r9d, eax; char *
0x18011b131  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011b138  mov     edx, 74h ; 't'; void *
0x18011b13d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011b142  nop
0x18011b143  mov     rcx, [rsp+98h+var_48+8]; this
0x18011b148  test    rcx, rcx
0x18011b14b  jz      short loc_18011B153
0x18011b14d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011b152  nop
0x18011b153  mov     rcx, [rsp+98h+var_58+8]; this
0x18011b158  test    rcx, rcx
0x18011b15b  jz      short loc_18011B163
0x18011b15d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011b162  nop
0x18011b163  lea     rcx, [rsp+98h+var_60]
0x18011b168  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011b16d  mov     eax, edi
0x18011b16f  jmp     loc_18011B3E7
0x18011b174  mov     rcx, [rbx+8]
0x18011b178  cmp     rcx, [rbx+10h]
0x18011b17c  jz      short loc_18011B18F
0x18011b17e  lea     rdx, [rsp+98h+var_48]
0x18011b183  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18011b188  add     qword ptr [rbx+8], 10h
0x18011b18d  jmp     short loc_18011B19F
0x18011b18f  lea     r8, [rsp+98h+var_48]
0x18011b194  mov     rdx, rcx
0x18011b197  mov     rcx, rbx
0x18011b19a  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@?$vector@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@V?$allocator@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider>>::_Emplace_reallocate<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &>(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> * const,std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &)
0x18011b19f  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18011b1a6  jz      short loc_18011B1BA
0x18011b1a8  mov     r8d, 2
0x18011b1ae  lea     rdx, AutopilotAttestationStateMachineCreateProvider
0x18011b1b5  call    McTemplateU0q_EventWriteTransfer
0x18011b1ba  xorps   xmm0, xmm0
0x18011b1bd  movdqu  xmmword ptr [rsp+98h+var_30], xmm0
0x18011b1c3  lea     rcx, [rsp+98h+var_30]
0x18011b1c8  call    ?CreateInstance@MsaAttestationProvider@Core@Autopilot@ModernDeployment@@SAJAEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@Z; ModernDeployment::Autopilot::Core::MsaAttestationProvider::CreateInstance(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> &)
0x18011b1cd  mov     edi, eax
0x18011b1cf  test    eax, eax
0x18011b1d1  jns     short loc_18011B231
0x18011b1d3  mov     rcx, [rsp+98h]; this
0x18011b1db  mov     r9d, eax; char *
0x18011b1de  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011b1e5  mov     edx, 7Ah ; 'z'; void *
0x18011b1ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011b1ef  nop
0x18011b1f0  mov     rcx, [rsp+98h+var_30+8]; this
0x18011b1f5  test    rcx, rcx
0x18011b1f8  jz      short loc_18011B200
0x18011b1fa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011b1ff  nop
0x18011b200  mov     rcx, [rsp+98h+var_48+8]; this
0x18011b205  test    rcx, rcx
0x18011b208  jz      short loc_18011B210
0x18011b20a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011b20f  nop
0x18011b210  mov     rcx, [rsp+98h+var_58+8]; this
0x18011b215  test    rcx, rcx
0x18011b218  jz      short loc_18011B220
0x18011b21a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011b21f  nop
0x18011b220  lea     rcx, [rsp+98h+var_60]
0x18011b225  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011b22a  mov     eax, edi
0x18011b22c  jmp     loc_18011B3E7
0x18011b231  mov     rcx, [rbx+8]
0x18011b235  cmp     rcx, [rbx+10h]
0x18011b239  jz      short loc_18011B24C
0x18011b23b  lea     rdx, [rsp+98h+var_30]
0x18011b240  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18011b245  add     qword ptr [rbx+8], 10h
0x18011b24a  jmp     short loc_18011B25C
0x18011b24c  lea     r8, [rsp+98h+var_30]
0x18011b251  mov     rdx, rcx
0x18011b254  mov     rcx, rbx
0x18011b257  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@?$vector@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@V?$allocator@V?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UIAttestationProvider@Core@Autopilot@ModernDeployment@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider>>::_Emplace_reallocate<std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &>(std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> * const,std::shared_ptr<ModernDeployment::Autopilot::Core::IAttestationProvider> const &)
0x18011b25c  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18011b263  jz      short loc_18011B278
0x18011b265  mov     r8d, 4
0x18011b26b  lea     rdx, AutopilotAttestationStateMachineCreateProvider
0x18011b272  call    McTemplateU0q_EventWriteTransfer
0x18011b277  nop
0x18011b278  mov     rcx, [rsp+98h+var_30+8]; this
0x18011b27d  test    rcx, rcx
0x18011b280  jz      short loc_18011B288
0x18011b282  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011b287  nop
0x18011b288  mov     rcx, [rsp+98h+var_48+8]; this
0x18011b28d  test    rcx, rcx
0x18011b290  jz      short loc_18011B298
0x18011b292  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011b297  nop
0x18011b298  mov     rcx, [rsp+98h+var_58+8]; this
0x18011b29d  test    rcx, rcx
0x18011b2a0  jz      short loc_18011B2A8
0x18011b2a2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011b2a7  nop
0x18011b2a8  lea     rcx, [rsp+98h+var_60]
0x18011b2ad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011b2b2  mov     rdx, r14; struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *
0x18011b2b5  mov     rcx, rsi; this
0x18011b2b8  call    ?UpdateAttestationConfiguration@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJPEAUIAttestationConfiguration@234@@Z; ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::UpdateAttestationConfiguration(ModernDeployment::Autopilot::Core::IAttestationConfiguration *)
0x18011b2bd  mov     ebx, eax
0x18011b2bf  test    eax, eax
0x18011b2c1  jns     short loc_18011B2E6
0x18011b2c3  mov     rcx, [rsp+98h]; this
0x18011b2cb  mov     r9d, eax; char *
0x18011b2ce  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011b2d5  mov     edx, 82h; void *
0x18011b2da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011b2df  mov     eax, ebx
0x18011b2e1  jmp     loc_18011B3E7
0x18011b2e6  mov     [rsp+98h+var_68], 0
0x18011b2eb  lea     r8, [rsp+98h+var_68]; bool *
0x18011b2f0  xor     edx, edx; bool
0x18011b2f2  mov     rcx, rsi; this
0x18011b2f5  call    ?DetermineOverallState@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJ_NAEA_N@Z; ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::DetermineOverallState(bool,bool &)
0x18011b2fa  mov     ebx, eax
0x18011b2fc  test    eax, eax
0x18011b2fe  jns     short loc_18011B323
0x18011b300  mov     rcx, [rsp+98h]; this
0x18011b308  mov     r9d, eax; char *
0x18011b30b  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011b312  mov     edx, 88h; void *
0x18011b317  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011b31c  mov     eax, ebx
0x18011b31e  jmp     loc_18011B3E7
0x18011b323  cmp     [rsp+98h+var_68], 0
0x18011b328  jz      short loc_18011B356
0x18011b32a  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18011b331  jz      short loc_18011B34F
0x18011b333  lea     rax, [rsp+98h+var_30]
0x18011b338  mov     qword ptr [rsp+98h+var_78], rax
0x18011b33d  mov     r9d, 1
0x18011b343  lea     rdx, AutopilotAttestationAlreadyComplete
0x18011b34a  call    McGenEventWrite_EventWriteTransfer
0x18011b34f  xor     eax, eax
0x18011b351  jmp     loc_18011B3E7
0x18011b356  mov     rcx, r15; SRWLock
0x18011b359  call    cs:__imp_AcquireSRWLockExclusive
0x18011b360  nop     dword ptr [rax+rax+00h]
0x18011b365  mov     [rsp+98h+var_60], r15
0x18011b36a  cmp     byte ptr [rsi+38h], 0
0x18011b36e  jz      short loc_18011B3A3
0x18011b370  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18011b377  jz      short loc_18011B395
0x18011b379  lea     rax, [rsp+98h+var_30]
0x18011b37e  mov     qword ptr [rsp+98h+var_78], rax
0x18011b383  mov     r9d, 1
0x18011b389  lea     rdx, AutopilotAttestationAlreadyInProgress
0x18011b390  call    McGenEventWrite_EventWriteTransfer
0x18011b395  lea     rcx, [rsp+98h+var_60]
0x18011b39a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011b39f  xor     eax, eax
0x18011b3a1  jmp     short loc_18011B3E7
0x18011b3a3  mov     byte ptr [rsi+38h], 1
0x18011b3a7  lea     rcx, [rsp+98h+var_60]
0x18011b3ac  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011b3b1  mov     rcx, rsi; this
0x18011b3b4  call    ?ExecuteProvidersBlockWait@AutopilotAttestationStateMachine@Core@Autopilot@ModernDeployment@@AEAAJXZ; ModernDeployment::Autopilot::Core::AutopilotAttestationStateMachine::ExecuteProvidersBlockWait(void)
0x18011b3b9  mov     ebx, eax
0x18011b3bb  test    eax, eax
0x18011b3bd  jns     short loc_18011B3DF
0x18011b3bf  mov     rcx, [rsp+98h]; this
0x18011b3c7  mov     r9d, eax; char *
0x18011b3ca  lea     r8, aOnecoreuapAdmi_74; "onecoreuap\\admin\\moderndeployment\\au"...
0x18011b3d1  mov     edx, 9Fh; void *
0x18011b3d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011b3db  mov     eax, ebx
0x18011b3dd  jmp     short loc_18011B3E7
0x18011b3df  xor     eax, eax
0x18011b3e1  jmp     short loc_18011B3E7
0x18011b3e3  mov     eax, [rsp+98h+var_38]
0x18011b3e7  mov     rcx, [rsp+98h+var_20]
0x18011b3ec  xor     rcx, rsp; StackCookie
0x18011b3ef  call    __security_check_cookie
0x18011b3f4  lea     r11, [rsp+98h+var_18]
0x18011b3fc  mov     rbx, [r11+30h]
0x18011b400  mov     rsi, [r11+38h]
0x18011b404  mov     rsp, r11
0x18011b407  pop     r15
0x18011b409  pop     r14
0x18011b40b  pop     rdi
  ... truncated ...
```
