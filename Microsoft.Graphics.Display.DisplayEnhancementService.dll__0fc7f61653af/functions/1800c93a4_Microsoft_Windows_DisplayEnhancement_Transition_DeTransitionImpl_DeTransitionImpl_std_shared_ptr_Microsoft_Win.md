# Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl::DeTransitionImpl(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapter> const &,ulong,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::BrightnessAdapter>,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Coordinator::DeColorAdapter>,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup>,std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Occlusion::OcclusionAdapter,std::default_delete<Microsoft::Windows::DisplayEnhancement::Occlusion::OcclusionAdapter>>)

- ea: `0x1800c93a4`
- end: `0x1800c9984`
- name: `??0DeTransitionImpl@Transition@DisplayEnhancement@Windows@Microsoft@@QEAA@AEBV?$shared_ptr@VMonitorAdapter@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@@std@@KV?$shared_ptr@VBrightnessAdapter@Coordinator@DisplayEnhancement@Windows@Microsoft@@@6@V?$shared_ptr@VDeColorAdapter@Coordinator@DisplayEnhancement@Windows@Microsoft@@@6@V?$shared_ptr@VDeManagementServerSettingsGroup@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@6@V?$unique_ptr@VOcclusionAdapter@Occlusion@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@VOcclusionAdapter@Occlusion@DisplayEnhancement@Windows@Microsoft@@@std@@@6@@Z`
- size: `1504`
- prototype: `__int64 __usercall@<rax>(char@<cl>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c8928`
- `0x1800c8af4`

## callees

- `0x180005860`
- `0x1800058bc`
- `0x180009f68`
- `0x18000eca0`
- `0x18000f778`
- `0x18000fb14`
- `0x180011704`
- `0x180011fe8`
- `0x180013138`
- `0x180013578`
- `0x18001c3ac`
- `0x18001c894`
- `0x18001edd0`
- `0x180031254`
- `0x18005c75c`
- `0x180063c54`
- `0x18009830c`
- `0x1800c2ed0`
- `0x1800c93a4`
- `0x1800ce430`
- `0x1800cf220`
- `0x1800d2b04`
- `0x1800ed010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x1800c95aa`
- `msvcp_win!_Xtime_get_ticks` at `0x1800c95aa`

## string_xrefs

- `0x1800c95f1`: `onecoreuap\drivers\mobilepc\displayenhancement\service\detransition\lib\detransition.cpp`
- `0x1800c9630`: `onecoreuap\drivers\mobilepc\displayenhancement\service\detransition\lib\detransition.cpp`
- `0x1800c995d`: `onecoreuap\drivers\mobilepc\displayenhancement\service\detransition\lib\detransition.cpp`
- `0x1800c9972`: `onecoreuap\drivers\mobilepc\displayenhancement\service\detransition\lib\detransition.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl::DeTransitionImpl(
        __int64 a1,
        _QWORD *a2,
        int a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 *a7)
{
  char v11; // r15
  char v12; // al
  __int64 v13; // rax
  __int64 v14; // rax
  char v15; // al
  char v16; // al
  _DWORD *v17; // rsi
  std::_Ref_count_base *v18; // rcx
  _DWORD *v19; // rdi
  std::_Ref_count_base *v20; // rcx
  __int64 *Shared; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  std::_Ref_count_base *v24; // rcx
  __int64 v25; // rax
  __int64 *v26; // rax
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  std::_Ref_count_base *v33; // rcx
  std::_Ref_count_base *v34; // rcx
  std::_Ref_count_base *v35; // rcx
  int v37; // [rsp+20h] [rbp-C1h]
  const char *v38; // [rsp+30h] [rbp-B1h]
  const char *v39; // [rsp+30h] [rbp-B1h]
  int v40; // [rsp+40h] [rbp-A1h]
  _DWORD *v41; // [rsp+60h] [rbp-81h] BYREF
  std::_Ref_count_base *v42; // [rsp+68h] [rbp-79h]
  __int64 *v43; // [rsp+70h] [rbp-71h]
  _DWORD *v44; // [rsp+78h] [rbp-69h]
  _QWORD *v45; // [rsp+80h] [rbp-61h]
  __int64 v46; // [rsp+88h] [rbp-59h]
  _QWORD *v47; // [rsp+90h] [rbp-51h]
  _QWORD *v48; // [rsp+98h] [rbp-49h]
  _QWORD *v49; // [rsp+A0h] [rbp-41h]
  __int64 v50; // [rsp+A8h] [rbp-39h]
  _QWORD v51[6]; // [rsp+B0h] [rbp-31h] BYREF
  __int16 v52; // [rsp+E0h] [rbp-1h]
  int v53; // [rsp+E2h] [rbp+1h]
  __int16 v54; // [rsp+E6h] [rbp+5h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v45 = a4;
  v46 = a1;
  v47 = a4;
  v48 = a5;
  v49 = a6;
  v43 = a7;
  v50 = (__int64)a7;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)a1 = &Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl::`vftable';
  *(_QWORD *)(a1 + 32) = 0;
  v11 = 1;
  *(_BYTE *)(a1 + 44) = 1;
  Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::CreateUnsupportedCausation(a1 + 56);
  Microsoft::Windows::DisplayEnhancement::Foundation::ColorConfiguration::CreateEmptyColorConfig(a1 + 104);
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  std::list<std::wstring>::list<std::wstring>(a1 + 240);
  *(_DWORD *)(a1 + 256) = 0;
  *(_OWORD *)(a1 + 264) = 0;
  *(_OWORD *)(a1 + 280) = 0;
  *(_DWORD *)(a1 + 296) = 1061997773;
  *(_DWORD *)(a1 + 300) = 1065353216;
  *(_BYTE *)(a1 + 324) = *a5 != 0;
  *(_BYTE *)(a1 + 325) = *a4 != 0;
  if ( *a4 || (v12 = 0, *a5) )
    v12 = 1;
  *(_BYTE *)(a1 + 326) = v12;
  *(_BYTE *)(a1 + 327) = 0;
  *(_DWORD *)(a1 + 328) = a3;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 336,
    a4);
  *(_QWORD *)(a1 + 352) = 0;
  *(_QWORD *)(a1 + 360) = 0;
  v13 = a5[1];
  if ( v13 )
    _InterlockedAdd((volatile signed __int32 *)(v13 + 8), 1u);
  *(_QWORD *)(a1 + 352) = *a5;
  *(_QWORD *)(a1 + 360) = a5[1];
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 368,
    a6);
  *(_QWORD *)(a1 + 384) = 0;
  *(_QWORD *)(a1 + 392) = 0;
  *(_QWORD *)(a1 + 400) = 0;
  *(_QWORD *)(a1 + 408) = 0;
  *(_QWORD *)(a1 + 416) = 0;
  *(_QWORD *)(a1 + 424) = 0;
  v14 = *v43;
  *v43 = 0;
  *(_QWORD *)(a1 + 432) = v14;
  *(_QWORD *)(a1 + 440) = 0;
  *(_QWORD *)(a1 + 448) = 0;
  *(_BYTE *)(a1 + 456) = 0;
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 72LL))(*a2, a1 + 464);
  *(_BYTE *)(a1 + 480) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 32LL))(*a2);
  *(_QWORD *)(a1 + 488) = _Xtime_get_ticks();
  *(_QWORD *)(a1 + 496) = 0;
  if ( *(_BYTE *)(a1 + 325) || (v15 = 1, *(_BYTE *)(a1 + 324)) )
    v15 = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xD8,
    (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\detransition\\lib\\detransition.cpp",
    (const char *)0x80070057LL,
    v15,
    (bool)"DeTransition object wasn't setup to transition brightness or color",
    v38);
  if ( !*(_BYTE *)(a1 + 325) || (v16 = 1, !*(_BYTE *)(a1 + 324)) )
    v16 = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xDB,
    (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\detransition\\lib\\detransition.cpp",
    (const char *)0x80070057LL,
    v16,
    (bool)"DeTransition object doing both brightness and color transitions at the same time isn't supported",
    v39);
  v17 = operator new(0x78u);
  v44 = v17;
  *(_OWORD *)v17 = 0;
  v17[2] = 1;
  v17[3] = 1;
  *(_QWORD *)v17 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableImpl>::`vftable';
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    &v41,
    a1 + 464);
  Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableImpl::TransitionTableImpl((_BYTE)v17 + 16);
  *(_QWORD *)(a1 + 208) = v17 + 4;
  v18 = *(std::_Ref_count_base **)(a1 + 216);
  *(_QWORD *)(a1 + 216) = v17;
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v19 = operator new(0x58u);
  v41 = v19;
  *(_OWORD *)v19 = 0;
  v19[2] = 1;
  v19[3] = 1;
  *(_QWORD *)v19 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::Transition::ColorTransitionTable>::`vftable';
  Microsoft::Windows::DisplayEnhancement::Transition::ColorTransitionTable::ColorTransitionTable((Microsoft::Windows::DisplayEnhancement::Transition::ColorTransitionTable *)(v19 + 4));
  *(_QWORD *)(a1 + 224) = v19 + 4;
  v20 = *(std::_Ref_count_base **)(a1 + 232);
  *(_QWORD *)(a1 + 232) = v19;
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  if ( *a6 && *(_BYTE *)(a1 + 326) )
  {
    if ( *(_BYTE *)(a1 + 325) )
    {
      Shared = (__int64 *)Microsoft::Windows::DisplayEnhancement::SliderAnimation::SliderAnimator::MakeShared(
                            &v41,
                            a1 + 464,
                            a6);
      v22 = *Shared;
      v23 = Shared[1];
      *Shared = 0;
      Shared[1] = 0;
      *(_QWORD *)(a1 + 392) = v22;
      v24 = *(std::_Ref_count_base **)(a1 + 400);
      *(_QWORD *)(a1 + 400) = v23;
      if ( v24 )
        std::_Ref_count_base::_Decref(v24);
      if ( v42 )
        std::_Ref_count_base::_Decref(v42);
    }
    v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*a6 + 32LL))(*a6, v51);
    v26 = (__int64 *)Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(&v41, v25);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (_QWORD *)(a1 + 408),
      v26);
    if ( v42 )
      std::_Ref_count_base::_Decref(v42);
    std::wstring::_Tidy_deallocate(v51);
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(a1 + 424, 1);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\detransition\\lib\\detransition.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v37);
  v53 = 0;
  v54 = 0;
  v51[0] = &Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::c_specification;
  v51[1] = a1 + 8;
  v52 = 257;
  v51[2] = Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::EvtLogMachineExceptionThunk;
  v51[3] = Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::EvtLogEventEnqueueThunk;
  v51[4] = Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::EvtLogTransitionThunk;
  v51[5] = Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::EvtMachineDestroyedThunk;
  v28 = SmFx::StateMachineEngine::StateMachineEngineImpl::MakeAndInitialize(
          (const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *)v51,
          (struct SmFx::StateMachineEngine::StateMachineEngineImpl **)(a1 + 8));
  if ( v28 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\detransition\\lib\\detransition.cpp",
      (const char *)(unsigned int)v28,
      v37);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v11 = 0;
  }
  if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*a6 + 24LL))(*a6, v51);
    v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29, v30, v31);
    WPP_RECORDER_AND_TRACE_SF_sSq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      4,
      14,
      19,
      &WPP_de69e3c62df43b1320ec01fdb34902cb_Traceguids,
      v40,
      v32,
      a1);
    std::wstring::_Tidy_deallocate(v51);
  }
  v33 = (std::_Ref_count_base *)v45[1];
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  v34 = (std::_Ref_count_base *)a5[1];
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  v35 = (std::_Ref_count_base *)a6[1];
  if ( v35 )
    std::_Ref_count_base::_Decref(v35);
  std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Occlusion::OcclusionAdapter>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::Occlusion::OcclusionAdapter>(v43);
  return a1;
}

```

## disassembly

```asm
0x1800c93a4  mov     [rsp-8+arg_10], rbx
0x1800c93a9  push    rbp
0x1800c93aa  push    rsi
0x1800c93ab  push    rdi
0x1800c93ac  push    r12
0x1800c93ae  push    r13
0x1800c93b0  push    r14
0x1800c93b2  push    r15
0x1800c93b4  lea     rbp, [rsp-0Fh]
0x1800c93b9  sub     rsp, 0F0h
0x1800c93c0  mov     rax, cs:__security_cookie
0x1800c93c7  xor     rax, rsp
0x1800c93ca  mov     [rbp+3Fh+var_38], rax
0x1800c93ce  mov     rbx, r9
0x1800c93d1  mov     [rbp+3Fh+var_A0], rbx
0x1800c93d5  mov     edi, r8d
0x1800c93d8  mov     rsi, rdx
0x1800c93db  mov     r14, rcx
0x1800c93de  mov     [rbp+3Fh+var_98], rcx
0x1800c93e2  mov     [rbp+3Fh+var_90], rbx
0x1800c93e6  mov     r13, [rbp+3Fh+arg_20]
0x1800c93ea  mov     [rbp+3Fh+var_88], r13
0x1800c93ee  mov     r12, [rbp+3Fh+arg_28]
0x1800c93f2  mov     [rbp+3Fh+var_80], r12
0x1800c93f6  mov     rax, [rbp+3Fh+arg_30]
0x1800c93fa  mov     [rbp+3Fh+var_B0], rax
0x1800c93fe  mov     [rbp+3Fh+var_78], rax
0x1800c9402  xor     eax, eax
0x1800c9404  mov     [rcx+8], rax
0x1800c9408  mov     [rcx+10h], rax
0x1800c940c  mov     [rcx+18h], rax
0x1800c9410  lea     rax, ??_7DeTransitionImpl@Transition@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl::`vftable'
0x1800c9417  mov     [rcx], rax
0x1800c941a  xor     eax, eax
0x1800c941c  mov     [rcx+20h], rax
0x1800c9420  lea     r15d, [rax+1]
0x1800c9424  mov     [rcx+2Ch], r15b
0x1800c9428  add     rcx, 38h ; '8'
0x1800c942c  call    ?CreateUnsupportedCausation@BrightnessCausation@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AU12345@XZ; Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::CreateUnsupportedCausation(void)
0x1800c9431  nop
0x1800c9432  lea     rcx, [r14+68h]
0x1800c9436  call    ?CreateEmptyColorConfig@ColorConfiguration@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AU12345@XZ; Microsoft::Windows::DisplayEnhancement::Foundation::ColorConfiguration::CreateEmptyColorConfig(void)
0x1800c943b  nop
0x1800c943c  xor     eax, eax
0x1800c943e  mov     [r14+0D0h], rax
0x1800c9445  mov     [r14+0D8h], rax
0x1800c944c  mov     [r14+0E0h], rax
0x1800c9453  mov     [r14+0E8h], rax
0x1800c945a  lea     rcx, [r14+0F0h]
0x1800c9461  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x1800c9466  nop
0x1800c9467  xor     ecx, ecx
0x1800c9469  mov     [r14+100h], ecx
0x1800c9470  xorps   xmm0, xmm0
0x1800c9473  movups  xmmword ptr [r14+108h], xmm0
0x1800c947b  movups  xmmword ptr [r14+118h], xmm0
0x1800c9483  mov     dword ptr [r14+128h], 3F4CCCCDh
0x1800c948e  mov     dword ptr [r14+12Ch], 3F800000h
0x1800c9499  cmp     [r13+0], rcx
0x1800c949d  setnz   al
0x1800c94a0  mov     [r14+144h], al
0x1800c94a7  cmp     [rbx], rcx
0x1800c94aa  setnz   al
0x1800c94ad  mov     [r14+145h], al
0x1800c94b4  cmp     [rbx], rcx
0x1800c94b7  jnz     short loc_1800C94C1
0x1800c94b9  cmp     [r13+0], rcx
0x1800c94bd  mov     al, cl
0x1800c94bf  jz      short loc_1800C94C4
0x1800c94c1  mov     al, r15b
0x1800c94c4  mov     [r14+146h], al
0x1800c94cb  mov     [r14+147h], cl
0x1800c94d2  mov     [r14+148h], edi
0x1800c94d9  lea     rcx, [r14+150h]
0x1800c94e0  mov     rdx, rbx
0x1800c94e3  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x1800c94e8  nop
0x1800c94e9  xor     ebx, ebx
0x1800c94eb  mov     [r14+160h], rbx
0x1800c94f2  mov     [r14+168h], rbx
0x1800c94f9  mov     rax, [r13+8]
0x1800c94fd  test    rax, rax
0x1800c9500  jz      short loc_1800C9507
0x1800c9502  lock add [rax+8], r15d
0x1800c9507  mov     rax, [r13+0]
0x1800c950b  mov     [r14+160h], rax
0x1800c9512  mov     rax, [r13+8]
0x1800c9516  mov     [r14+168h], rax
0x1800c951d  lea     rcx, [r14+170h]
0x1800c9524  mov     rdx, r12
0x1800c9527  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x1800c952c  nop
0x1800c952d  mov     [r14+180h], rbx
0x1800c9534  mov     [r14+188h], rbx
0x1800c953b  mov     [r14+190h], rbx
0x1800c9542  lea     rax, [r14+198h]
0x1800c9549  mov     [rax], rbx
0x1800c954c  mov     [rax+8], rbx
0x1800c9550  mov     [r14+1A8h], rbx
0x1800c9557  mov     rcx, [rbp+3Fh+var_B0]
0x1800c955b  mov     rax, [rcx]
0x1800c955e  mov     [rcx], rbx
0x1800c9561  mov     [r14+1B0h], rax
0x1800c9568  mov     [r14+1B8h], rbx
0x1800c956f  mov     [r14+1C0h], rbx
0x1800c9576  mov     [r14+1C8h], bl
0x1800c957d  mov     rcx, [rsi]
0x1800c9580  lea     rdx, [r14+1D0h]
0x1800c9587  mov     rax, [rcx]
0x1800c958a  mov     rax, [rax+48h]
0x1800c958e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9593  nop
0x1800c9594  mov     rcx, [rsi]
0x1800c9597  mov     rax, [rcx]
0x1800c959a  mov     rax, [rax+20h]
0x1800c959e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c95a3  mov     [r14+1E0h], al
0x1800c95aa  call    cs:__imp__Xtime_get_ticks
0x1800c95b0  mov     [r14+1E8h], rax
0x1800c95b7  mov     [r14+1F0h], rbx
0x1800c95be  cmp     [r14+145h], bl
0x1800c95c5  jnz     short loc_1800C95D3
0x1800c95c7  cmp     [r14+144h], bl
0x1800c95ce  mov     al, r15b
0x1800c95d1  jz      short loc_1800C95D5
0x1800c95d3  mov     al, bl
0x1800c95d5  mov     rcx, [rbp+47h]; this
0x1800c95d9  lea     rdx, aDetransitionOb; "DeTransition object wasn't setup to tra"...
0x1800c95e0  mov     qword ptr [rsp+120h+var_F8], rdx; bool
0x1800c95e5  mov     [rsp+120h+var_100], al; char
0x1800c95e9  mov     edi, 80070057h
0x1800c95ee  mov     r9d, edi; char *
0x1800c95f1  lea     r8, aOnecoreuapDriv_25; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800c95f8  mov     edx, 0D8h; void *
0x1800c95fd  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800c9602  cmp     [r14+145h], bl
0x1800c9609  jz      short loc_1800C9617
0x1800c960b  cmp     [r14+144h], bl
0x1800c9612  mov     al, r15b
0x1800c9615  jnz     short loc_1800C9619
0x1800c9617  mov     al, bl
0x1800c9619  mov     rcx, [rbp+47h]; this
0x1800c961d  lea     rdx, aDetransitionOb_0; "DeTransition object doing both brightne"...
0x1800c9624  mov     qword ptr [rsp+120h+var_F8], rdx; bool
0x1800c9629  mov     [rsp+120h+var_100], al; int
0x1800c962d  mov     r9d, edi; char *
0x1800c9630  lea     r8, aOnecoreuapDriv_25; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800c9637  mov     edx, 0DBh; void *
0x1800c963c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800c9641  mov     edi, ebx
0x1800c9643  cmp     [r14+145h], bl
0x1800c964a  setz    dil
0x1800c964e  mov     ecx, 78h ; 'x'; Size
0x1800c9653  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c9658  mov     rsi, rax
0x1800c965b  mov     [rbp+3Fh+var_A8], rax
0x1800c965f  xorps   xmm0, xmm0
0x1800c9662  movups  xmmword ptr [rax], xmm0
0x1800c9665  mov     [rax+8], r15d
0x1800c9669  mov     [rax+0Ch], r15d
0x1800c966d  lea     rax, ??_7?$_Ref_count_obj2@VTransitionTableImpl@Transition@DisplayEnhancement@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableImpl>::`vftable'
0x1800c9674  mov     [rsi], rax
0x1800c9677  lea     rbx, [rsi+10h]
0x1800c967b  lea     rdx, [r14+1D0h]
0x1800c9682  lea     rcx, [rsp+120h+var_C0]
0x1800c9687  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x1800c968c  mov     r9, rax
0x1800c968f  mov     r8d, [r14+148h]
0x1800c9696  mov     edx, edi
0x1800c9698  mov     rcx, rbx; char
0x1800c969b  call    ??0TransitionTableImpl@Transition@DisplayEnhancement@Windows@Microsoft@@QEAA@W4TransitionTableType@1234@IV?$shared_ptr@VBrightnessCapabilityWrapper@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableImpl::TransitionTableImpl(Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableType,uint,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper>)
0x1800c96a0  nop
0x1800c96a1  mov     [r14+0D0h], rbx
0x1800c96a8  mov     rcx, [r14+0D8h]; this
0x1800c96af  mov     [r14+0D8h], rsi
0x1800c96b6  xor     esi, esi
0x1800c96b8  test    rcx, rcx
0x1800c96bb  jz      short loc_1800C96C2
0x1800c96bd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c96c2  mov     ecx, 58h ; 'X'; Size
0x1800c96c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c96cc  mov     rdi, rax
0x1800c96cf  mov     [rsp+120h+var_C0], rax
0x1800c96d4  xorps   xmm0, xmm0
0x1800c96d7  movups  xmmword ptr [rax], xmm0
0x1800c96da  mov     [rax+8], r15d
0x1800c96de  mov     [rax+0Ch], r15d
0x1800c96e2  lea     rax, ??_7?$_Ref_count_obj2@VColorTransitionTable@Transition@DisplayEnhancement@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::Transition::ColorTransitionTable>::`vftable'
0x1800c96e9  mov     [rdi], rax
0x1800c96ec  lea     rbx, [rdi+10h]
0x1800c96f0  mov     rcx, rbx; this
0x1800c96f3  call    ??0ColorTransitionTable@Transition@DisplayEnhancement@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::DisplayEnhancement::Transition::ColorTransitionTable::ColorTransitionTable(void)
0x1800c96f8  nop
0x1800c96f9  mov     [r14+0E0h], rbx
0x1800c9700  mov     rcx, [r14+0E8h]; this
0x1800c9707  mov     [r14+0E8h], rdi
0x1800c970e  test    rcx, rcx
0x1800c9711  jz      short loc_1800C9718
0x1800c9713  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9718  cmp     [r12], rsi
0x1800c971c  jz      loc_1800C97D0
0x1800c9722  cmp     [r14+146h], sil
0x1800c9729  jz      loc_1800C97D0
0x1800c972f  cmp     [r14+145h], sil
0x1800c9736  jz      short loc_1800C9787
0x1800c9738  mov     r8, r12
0x1800c973b  lea     rdx, [r14+1D0h]
0x1800c9742  lea     rcx, [rsp+120h+var_C0]
0x1800c9747  call    ?MakeShared@SliderAnimator@SliderAnimation@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VSliderAnimator@SliderAnimation@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_ptr@VBrightnessCapabilityWrapper@Foundation@DisplayEnhancement@Windows@Microsoft@@@7@AEBV?$shared_ptr@VDeManagementServerSettingsGroup@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@7@@Z; Microsoft::Windows::DisplayEnhancement::SliderAnimation::SliderAnimator::MakeShared(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup> const &)
0x1800c974c  mov     rcx, [rax]
0x1800c974f  mov     rdx, [rax+8]
0x1800c9753  mov     [rax], rsi
0x1800c9756  mov     [rax+8], rsi
0x1800c975a  mov     [r14+188h], rcx
0x1800c9761  mov     rcx, [r14+190h]; this
0x1800c9768  mov     [r14+190h], rdx
0x1800c976f  test    rcx, rcx
0x1800c9772  jz      short loc_1800C9779
0x1800c9774  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9779  mov     rcx, [rbp+3Fh+var_B8]; this
0x1800c977d  test    rcx, rcx
0x1800c9780  jz      short loc_1800C9787
0x1800c9782  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9787  mov     rcx, [r12]
0x1800c978b  mov     rax, [rcx]
0x1800c978e  lea     rdx, [rbp+3Fh+var_70]
0x1800c9792  mov     rax, [rax+20h]
0x1800c9796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c979b  nop
0x1800c979c  mov     rdx, rax
0x1800c979f  lea     rcx, [rsp+120h+var_C0]
0x1800c97a4  call    ?GetOrMakeShared@DesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(std::wstring const &)
0x1800c97a9  mov     rdx, rax
0x1800c97ac  lea     rcx, [r14+198h]
0x1800c97b3  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x1800c97b8  mov     rcx, [rbp+3Fh+var_B8]; this
0x1800c97bc  test    rcx, rcx
0x1800c97bf  jz      short loc_1800C97C7
0x1800c97c1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c97c6  nop
0x1800c97c7  lea     rcx, [rbp+3Fh+var_70]
0x1800c97cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c97d0  mov     edx, r15d
0x1800c97d3  lea     rcx, [r14+1A8h]
0x1800c97da  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800c97df  mov     rcx, [rbp+47h]; this
0x1800c97e3  test    eax, eax
0x1800c97e5  js      loc_1800C996F
0x1800c97eb  mov     [rbp+3Fh+var_3E], esi
0x1800c97ee  mov     [rbp+3Fh+var_3A], si
0x1800c97f2  lea     rax, ?c_specification@?$TransitionTimerStateMachine@VDeTransitionImpl@Transition@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Transition@DisplayEnhancement@Windows@Microsoft@@0USTATE_MACHINE_SPECIFICATION@SmFx@@B; SmFx::STATE_MACHINE_SPECIFICATION const Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::c_specification
0x1800c97f9  mov     [rbp+3Fh+var_70], rax
0x1800c97fd  lea     rdx, [r14+8]; struct SmFx::StateMachineEngine::StateMachineEngineImpl **
0x1800c9801  mov     [rbp+3Fh+var_68], rdx
0x1800c9805  mov     [rbp+3Fh+var_40], 101h
0x1800c980b  lea     rax, ?EvtLogMachineExceptionThunk@?$TransitionTimerStateMachine@VDeTransitionImpl@Transition@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Transition@DisplayEnhancement@Windows@Microsoft@@CAXPEAXW4MachineException@SmFx@@GG@Z; Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::EvtLogMachineExceptionThunk(void *,SmFx::MachineException,ushort,ushort)
0x1800c9812  mov     [rbp+3Fh+var_60], rax
0x1800c9816  lea     rax, ?EvtLogEventEnqueueThunk@?$TransitionTimerStateMachine@VDeTransitionImpl@Transition@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Transition@DisplayEnhancement@Windows@Microsoft@@CAXPEAXG@Z; Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::EvtLogEventEnqueueThunk(void *,ushort)
0x1800c981d  mov     [rbp+3Fh+var_58], rax
0x1800c9821  lea     rax, ?EvtLogTransitionThunk@?$TransitionTimerStateMachine@VDeTransitionImpl@Transition@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Transition@DisplayEnhancement@Windows@Microsoft@@CAXPEAXW4TransitionType@SmFx@@GGG@Z; Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::EvtLogTransitionThunk(void *,SmFx::TransitionType,ushort,ushort,ushort)
0x1800c9828  mov     [rbp+3Fh+var_50], rax
0x1800c982c  lea     rax, ?EvtMachineDestroyedThunk@?$TransitionTimerStateMachine@VDeTransitionImpl@Transition@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Transition@DisplayEnhancement@Windows@Microsoft@@CAXPEAX@Z; Microsoft::Windows::DisplayEnhancement::Transition::GeneratedStateMachines::TransitionTimerStateMachine<Microsoft::Windows::DisplayEnhancement::Transition::DeTransitionImpl>::EvtMachineDestroyedThunk(void *)
0x1800c9833  mov     [rbp+3Fh+var_48], rax
0x1800c9837  lea     rcx, [rbp+3Fh+var_70]; struct SmFx::STATE_MACHINE_ENGINE_CONFIG *
0x1800c983b  call    ?MakeAndInitialize@StateMachineEngineImpl@StateMachineEngine@SmFx@@SAJAEBUSTATE_MACHINE_ENGINE_CONFIG@3@PEAPEAV123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::MakeAndInitialize(SmFx::STATE_MACHINE_ENGINE_CONFIG const &,SmFx::StateMachineEngine::StateMachineEngineImpl * *)
0x1800c9840  mov     rcx, [rbp+47h]; this
0x1800c9844  test    eax, eax
0x1800c9846  js      loc_1800C995A
0x1800c984c  lea     rcx, WPP_GLOBAL_Control
0x1800c9853  mov     rax, cs:WPP_GLOBAL_Control
0x1800c985a  cmp     rax, rcx
0x1800c985d  jz      short loc_1800C986E
0x1800c985f  test    dword ptr [rax+1Ch], 2000h
0x1800c9866  jz      short loc_1800C986E
0x1800c9868  cmp     byte ptr [rax+19h], 4
0x1800c986c  jnb     short loc_1800C9871
0x1800c986e  mov     r15b, sil
0x1800c9871  lea     rax, WPP_RECORDER_INITIALIZED
0x1800c9878  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800c987f  setnz   bl
0x1800c9882  test    r15b, r15b
0x1800c9885  jnz     short loc_1800C988B
0x1800c9887  test    bl, bl
0x1800c9889  jz      short loc_1800C98F5
0x1800c988b  mov     rcx, [r12]
0x1800c988f  mov     rax, [rcx]
0x1800c9892  lea     rdx, [rbp+3Fh+var_70]
0x1800c9896  mov     rax, [rax+18h]
0x1800c989a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c989f  mov     rcx, rax
0x1800c98a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c98a7  mov     qword ptr [rsp+120h+var_D0], r14; char
0x1800c98ac  mov     [rsp+120h+var_D8], rax; __int64
0x1800c98b1  lea     rax, WPP_de69e3c62df43b1320ec01fdb34902cb_Traceguids
0x1800c98b8  mov     [rsp+120h+MessageGuid], rax; MessageGuid
0x1800c98bd  mov     word ptr [rsp+120h+var_F0], 13h; __int16
0x1800c98c4  mov     dword ptr [rsp+120h+var_F8], 0Eh; int
0x1800c98cc  mov     [rsp+120h+var_100], 4; char
0x1800c98d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c98d8  mov     r9, [rcx+28h]
  ... truncated ...
```
