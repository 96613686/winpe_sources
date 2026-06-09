# ModernDeployment::Autopilot::Core::MsaAttestationProvider::MonitorMsaAttestationProgress(ModernDeployment::Autopilot::Core::AttestationPhase,Concurrency::cancellation_token_source &,std::function<long (ModernDeployment::Autopilot::Core::AttestationProviderResult const &)>,ModernDeployment::Autopilot::Core::AttestationProviderResult &)

- ea: `0x180126cd0`
- end: `0x180127251`
- name: `?MonitorMsaAttestationProgress@MsaAttestationProvider@Core@Autopilot@ModernDeployment@@AEAAJW4AttestationPhase@234@AEAVcancellation_token_source@Concurrency@@V?$function@$$A6AJAEBUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@Z@std@@AEAUAttestationProviderResult@234@@Z`
- size: `1409`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180126528`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077d0c`
- `0x180080c10`
- `0x1800810f0`
- `0x180081150`
- `0x180118b14`
- `0x18011e8d0`
- `0x18011fbfc`
- `0x18011fc80`
- `0x18011fca8`
- `0x18011fec0`
- `0x180126a6c`
- `0x180126cd0`
- `0x180127b20`
- `0x180127bd4`
- `0x180127e64`
- `0x180128298`
- `0x180200010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180126f4e`
- `ntdll!RtlPublishWnfStateData` at `0x180126f4e`

## string_xrefs

- `0x180126d34`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x180126e1e`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x180126eee`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x180126f71`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x180127031`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x18012704d`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x1801270f6`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x180127112`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x18012719c`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x1801271b8`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ModernDeployment::Autopilot::Core::MsaAttestationProvider::MonitorMsaAttestationProgress(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 *a4,
        unsigned int *a5)
{
  const char *v9; // r9
  __int64 *v10; // rcx
  __int64 v11; // rdx
  __int64 result; // rax
  ULONG v13; // ebx
  bool IsTestModeEnabled; // al
  int v15; // edx
  int v16; // eax
  unsigned int v17; // ecx
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 *v20; // rcx
  __int64 token; // rax
  unsigned int v22; // r10d
  int v23; // eax
  ModernDeployment::Autopilot::Core::MsaAttestationProvider *v24; // rcx
  __int64 v25; // r8
  unsigned int v26; // ebx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  struct _WNF_STATE_NAME MsaKeyStateWnfName; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  int v33; // eax
  __int64 *v34; // rcx
  __int64 v35; // rdx
  int v36; // eax
  __int64 *v37; // rcx
  __int64 v38; // rdx
  int v39; // eax
  __int64 v40; // rdx
  __int64 *v41; // rcx
  __int64 *v42; // rbx
  __int64 *v43; // rcx
  __int64 v44; // rdx
  int v45; // [rsp+20h] [rbp-1F8h]
  int v46; // [rsp+20h] [rbp-1F8h]
  int *v47; // [rsp+20h] [rbp-1F8h]
  int v48[2]; // [rsp+30h] [rbp-1E8h] BYREF
  int v49[2]; // [rsp+38h] [rbp-1E0h] BYREF
  __int64 v50; // [rsp+40h] [rbp-1D8h]
  __int64 *v51; // [rsp+48h] [rbp-1D0h]
  int *v52; // [rsp+70h] [rbp-1A8h]
  __int64 (__fastcall **v53)(); // [rsp+78h] [rbp-1A0h] BYREF
  unsigned int v54; // [rsp+80h] [rbp-198h]
  __int64 (__fastcall ***v55)(); // [rsp+B0h] [rbp-168h]
  __int64 *v56; // [rsp+B8h] [rbp-160h]
  unsigned int v57[4]; // [rsp+C0h] [rbp-158h] BYREF
  _BYTE v58[256]; // [rsp+D0h] [rbp-148h] BYREF
  int v59[2]; // [rsp+1D0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  try
  {
    v56 = a4;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
        (const char *)0x80004001LL,
        v45);
      v10 = (__int64 *)a4[7];
      if ( v10 )
      {
        v11 = *v10;
        LOBYTE(v11) = v10 != a4;
        (*(void (__fastcall **)(__int64 *, __int64))(*v10 + 32))(v10, v11);
        a4[7] = 0;
      }
      return 2147500033LL;
    }
    ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(v58);
    *(_QWORD *)v59 = v49;
    *(_QWORD *)v49 = off_1802159B8;
    v50 = a1;
    v51 = a4;
    v52 = v49;
    *(_QWORD *)v48 = &v53;
    v53 = off_1802159E8;
    v54 = a2;
    v55 = &v53;
    v13 = ModernDeployment::Autopilot::Core::AttestationConfigHelper::GetMsaTriggerWnfName().Data[0];
    IsTestModeEnabled = ModernDeployment::Autopilot::Core::AttestationConfigHelper::IsTestModeEnabled();
    v15 = WNF_MSA_TPM_SERVER_CLIENT_KEY_STATE_UPDATED;
    if ( IsTestModeEnabled )
      v15 = WNF_PROV_AUTOPILOT_TEST_MSA_KEY_STATE_UPDATE;
    v16 = ModernDeployment::Autopilot::Core::WnfAttestationHelper<unsigned int>::Initialize(
            (unsigned int)v58,
            v15,
            v13,
            (unsigned int)&v53,
            (__int64)v49);
    v18 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
        (const char *)(unsigned int)v16,
        v46);
      ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(v58);
      v20 = (__int64 *)a4[7];
      if ( v20 )
      {
        LOBYTE(v19) = v20 != a4;
        (*(void (__fastcall **)(__int64 *, __int64))(*v20 + 32))(v20, v19);
        a4[7] = 0;
      }
      return v18;
    }
    ModernDeployment::Autopilot::Core::AttestationConfigHelper::GetAdjustedTimeoutMs(v17);
    *(_QWORD *)v57 = 0;
    v48[0] = 0;
    token = Concurrency::cancellation_token_source::get_token(a3, v59);
    v47 = v48;
    v23 = ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(
            v58,
            v22,
            token,
            v57);
    v26 = v23;
    if ( v23 >= 0 )
    {
      a5[2] = a2;
      a5[1] = 2;
      a5[3] = v48[0];
      *a5 = 0;
      if ( a4[7] )
      {
        v27 = std::_Func_class<bool,>::operator()(a4, a5);
        v24 = retaddr;
        if ( v27 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x9D,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
            (const char *)(unsigned int)v27,
            (int)v48);
      }
      if ( v57[0] != 4 )
        goto LABEL_23;
      v48[0] = 0;
      v28 = ModernDeployment::Autopilot::Core::MsaAttestationProvider::CheckMsaTpmKeyState(
              v24,
              (enum Microsoft::Windows::Autopilot::TpmKeyStateServer *)v48);
      v24 = retaddr;
      if ( v28 >= 0 )
      {
        if ( v48[0] == 4 )
          goto LABEL_23;
        MsaKeyStateWnfName = ModernDeployment::Autopilot::Core::AttestationConfigHelper::GetMsaKeyStateWnfName();
        LODWORD(v47) = 0;
        v28 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RtlPublishWnfStateData)(
                MsaKeyStateWnfName,
                0,
                v57,
                4)
            | 0x10000000;
        v24 = retaddr;
        if ( v28 >= 0 )
          goto LABEL_23;
        v29 = 167;
      }
      else
      {
        v29 = 164;
      }
      wil::details::in1diag3::_Log_Hr(
        v24,
        (void *)v29,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
        (const char *)(unsigned int)v28,
        (int)v47);
LABEL_23:
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v24, AutopilotAttestationMsaCompleted, v57[0]);
      ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(v58);
      v32 = (__int64 *)a4[7];
      if ( v32 )
      {
        LOBYTE(v31) = v32 != a4;
        (*(void (__fastcall **)(__int64 *, __int64))(*v32 + 32))(v32, v31);
        a4[7] = 0;
      }
      return 0;
    }
    if ( v23 == -2147467260 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        v47 = v59;
        McGenEventWrite_EventWriteTransfer(v24, AutopilotAttestationMsaCancelled, v25, 1);
      }
      *a5 = -2147467260;
      a5[1] = 3;
      if ( a4[7] )
      {
        v33 = std::_Func_class<bool,>::operator()(a4, a5);
        if ( v33 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xB5,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
            (const char *)(unsigned int)v33,
            (int)v47);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
        (const char *)0x80004004LL,
        (int)v47);
      ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(v58);
      v34 = (__int64 *)a4[7];
      if ( v34 )
      {
        v35 = *v34;
        LOBYTE(v35) = v34 != a4;
        (*(void (__fastcall **)(__int64 *, __int64))(*v34 + 32))(v34, v35);
        a4[7] = 0;
      }
      result = 2147500036LL;
    }
    else if ( v23 == -2147023436 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        v47 = v59;
        McGenEventWrite_EventWriteTransfer(v24, AutopilotAttestationMsaTimeout, v25, 1);
      }
      *a5 = -2147023436;
      a5[1] = 3;
      if ( a4[7] )
      {
        v36 = std::_Func_class<bool,>::operator()(a4, a5);
        if ( v36 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xC2,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
            (const char *)(unsigned int)v36,
            (int)v47);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
        (const char *)0x800705B4LL,
        (int)v47);
      ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(v58);
      v37 = (__int64 *)a4[7];
      if ( v37 )
      {
        v38 = *v37;
        LOBYTE(v38) = v37 != a4;
        (*(void (__fastcall **)(__int64 *, __int64))(*v37 + 32))(v37, v38);
        a4[7] = 0;
      }
      result = 2147943860LL;
    }
    else
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0q_EventWriteTransfer(v24, AutopilotAttestationMsaError, (unsigned int)v23);
      *a5 = v26;
      a5[1] = 3;
      if ( a4[7] )
      {
        v39 = std::_Func_class<bool,>::operator()(a4, a5);
        if ( v39 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xCF,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
            (const char *)(unsigned int)v39,
            (int)v48);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
        (const char *)v26,
        (int)v47);
      ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(v58);
      v41 = (__int64 *)a4[7];
      if ( v41 )
      {
        LOBYTE(v40) = v41 != a4;
        (*(void (__fastcall **)(__int64 *, __int64))(*v41 + 32))(v41, v40);
        a4[7] = 0;
      }
      result = v26;
    }
  }
  catch ( ... )
  {
    v48[0] = wil::details::in1diag3::Return_CaughtException(
               retaddr,
               (void *)0xD5,
               (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\msaattestationprovider.cpp",
               v9);
    v42 = v56;
    v43 = (__int64 *)v56[7];
    if ( v43 )
    {
      LOBYTE(v44) = v43 != v56;
      (*(void (__fastcall **)(__int64 *, __int64))(*v43 + 32))(v43, v44);
      v42[7] = 0;
    }
    return (unsigned int)v48[0];
  }
  return result;
}

```

## disassembly

```asm
0x180126cd0  mov     [rsp+arg_8], rbx
0x180126cd5  push    rsi
0x180126cd6  push    rdi
0x180126cd7  push    r12
0x180126cd9  push    r14
0x180126cdb  push    r15
0x180126cdd  sub     rsp, 1F0h
0x180126ce4  mov     rax, cs:__security_cookie
0x180126ceb  xor     rax, rsp
0x180126cee  mov     [rsp+218h+var_38], rax
0x180126cf6  mov     rsi, r9
0x180126cf9  mov     r12, r8
0x180126cfc  mov     r15d, edx
0x180126cff  mov     rbx, rcx
0x180126d02  mov     r14, [rsp+218h+arg_20]
0x180126d0a  mov     [rsp+218h+var_160], r9
0x180126d12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180126d19  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180126d1e  xor     edi, edi
0x180126d20  test    al, al
0x180126d22  jnz     short loc_180126D6A
0x180126d24  mov     rcx, [rsp+218h]; this
0x180126d2c  mov     ebx, 80004001h
0x180126d31  mov     r9d, ebx; char *
0x180126d34  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x180126d3b  lea     edx, [rdi+4Fh]; void *
0x180126d3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126d43  nop
0x180126d44  mov     rcx, [rsi+38h]
0x180126d48  test    rcx, rcx
0x180126d4b  jz      short loc_180126D63
0x180126d4d  mov     rdx, [rcx]
0x180126d50  mov     rax, [rdx+20h]
0x180126d54  cmp     rcx, rsi
0x180126d57  setnz   dl
0x180126d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126d5f  mov     [rsi+38h], rdi
0x180126d63  mov     eax, ebx
0x180126d65  jmp     loc_180127228
0x180126d6a  lea     rcx, [rsp+218h+var_148]
0x180126d72  call    ??0?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x180126d77  nop
0x180126d78  lea     rax, [rsp+218h+var_1E0]
0x180126d7d  mov     qword ptr [rsp+218h+var_48], rax
0x180126d85  lea     rax, off_1802159B8
0x180126d8c  mov     qword ptr [rsp+218h+var_1E0], rax
0x180126d91  mov     [rsp+218h+var_1D8], rbx
0x180126d96  mov     [rsp+218h+var_1D0], rsi
0x180126d9b  lea     rax, [rsp+218h+var_1E0]
0x180126da0  mov     [rsp+218h+var_1A8], rax
0x180126da5  lea     rax, [rsp+218h+var_1A0]
0x180126daa  mov     qword ptr [rsp+218h+var_1E8], rax
0x180126daf  lea     rax, off_1802159E8
0x180126db6  mov     [rsp+218h+var_1A0], rax
0x180126dbb  mov     [rsp+218h+var_198], r15d
0x180126dc3  lea     rax, [rsp+218h+var_1A0]
0x180126dc8  mov     [rsp+218h+var_168], rax
0x180126dd0  call    ?GetMsaTriggerWnfName@AttestationConfigHelper@Core@Autopilot@ModernDeployment@@SA?AU_WNF_STATE_NAME@@XZ; ModernDeployment::Autopilot::Core::AttestationConfigHelper::GetMsaTriggerWnfName(void)
0x180126dd5  mov     rbx, rax
0x180126dd8  call    ?IsTestModeEnabled@AttestationConfigHelper@Core@Autopilot@ModernDeployment@@SA_NXZ; ModernDeployment::Autopilot::Core::AttestationConfigHelper::IsTestModeEnabled(void)
0x180126ddd  mov     rdx, cs:WNF_MSA_TPM_SERVER_CLIENT_KEY_STATE_UPDATED
0x180126de4  test    al, al
0x180126de6  cmovnz  rdx, cs:WNF_PROV_AUTOPILOT_TEST_MSA_KEY_STATE_UPDATE
0x180126dee  lea     rax, [rsp+218h+var_1E0]
0x180126df3  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x180126df8  lea     r9, [rsp+218h+var_1A0]
0x180126dfd  mov     r8, rbx
0x180126e00  lea     rcx, [rsp+218h+var_148]
0x180126e08  call    ?Initialize@?$WnfAttestationHelper@I@Core@Autopilot@ModernDeployment@@QEAAJU_WNF_STATE_NAME@@0V?$function@$$A6A_NAEBI@Z@std@@V?$function@$$A6A?AW4AttestationState@Core@Autopilot@ModernDeployment@@AEBI@Z@7@@Z; ModernDeployment::Autopilot::Core::WnfAttestationHelper<uint>::Initialize(_WNF_STATE_NAME,_WNF_STATE_NAME,std::function<bool (uint const &)>,std::function<ModernDeployment::Autopilot::Core::AttestationState (uint const &)>)
0x180126e0d  mov     ebx, eax
0x180126e0f  test    eax, eax
0x180126e11  jns     short loc_180126E64
0x180126e13  mov     rcx, [rsp+218h]; this
0x180126e1b  mov     r9d, eax; char *
0x180126e1e  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x180126e25  mov     edx, 87h; void *
0x180126e2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126e2f  nop
0x180126e30  lea     rcx, [rsp+218h+var_148]
0x180126e38  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x180126e3d  nop
0x180126e3e  mov     rcx, [rsi+38h]
0x180126e42  test    rcx, rcx
0x180126e45  jz      short loc_180126E5D
0x180126e47  mov     rax, [rcx]
0x180126e4a  cmp     rcx, rsi
0x180126e4d  setnz   dl
0x180126e50  mov     rax, [rax+20h]
0x180126e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126e59  mov     [rsi+38h], rdi
0x180126e5d  mov     eax, ebx
0x180126e5f  jmp     loc_180127228
0x180126e64  call    ?GetAdjustedTimeoutMs@AttestationConfigHelper@Core@Autopilot@ModernDeployment@@SAKK@Z; ModernDeployment::Autopilot::Core::AttestationConfigHelper::GetAdjustedTimeoutMs(ulong)
0x180126e69  mov     r10d, eax
0x180126e6c  mov     qword ptr [rsp+218h+var_158], rdi
0x180126e74  mov     [rsp+218h+var_1E8], edi
0x180126e78  lea     rdx, [rsp+218h+var_48]
0x180126e80  mov     rcx, r12
0x180126e83  call    ?get_token@cancellation_token_source@Concurrency@@QEBA?AVcancellation_token@2@XZ; Concurrency::cancellation_token_source::get_token(void)
0x180126e88  lea     rcx, [rsp+218h+var_1E8]
0x180126e8d  mov     qword ptr [rsp+218h+var_1F8], rcx; int
0x180126e92  lea     r9, [rsp+218h+var_158]
0x180126e9a  mov     r8, rax
0x180126e9d  mov     edx, r10d
0x180126ea0  lea     rcx, [rsp+218h+var_148]
0x180126ea8  call    ?WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@3Windows@Microsoft@@AEAW4AttestationState@234@@Z; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)
0x180126ead  mov     ebx, eax
0x180126eaf  test    eax, eax
0x180126eb1  js      loc_180126FCF
0x180126eb7  mov     [r14+8], r15d
0x180126ebb  mov     dword ptr [r14+4], 2
0x180126ec3  mov     eax, [rsp+218h+var_1E8]
0x180126ec7  mov     [r14+0Ch], eax
0x180126ecb  mov     [r14], edi
0x180126ece  cmp     [rsi+38h], rdi
0x180126ed2  jz      short loc_180126EFF
0x180126ed4  mov     rdx, r14
0x180126ed7  mov     rcx, rsi
0x180126eda  call    ??R?$_Func_class@_N$$V@std@@QEBA_NXZ; std::_Func_class<bool,>::operator()(void)
0x180126edf  mov     rcx, [rsp+218h]; this
0x180126ee7  test    eax, eax
0x180126ee9  jns     short loc_180126EFF
0x180126eeb  mov     r9d, eax; char *
0x180126eee  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x180126ef5  mov     edx, 9Dh; void *
0x180126efa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180126eff  cmp     [rsp+218h+var_158], 4
0x180126f07  jnz     short loc_180126F7D
0x180126f09  mov     [rsp+218h+var_1E8], edi
0x180126f0d  lea     rdx, [rsp+218h+var_1E8]; enum Microsoft::Windows::Autopilot::TpmKeyStateServer *
0x180126f12  call    ?CheckMsaTpmKeyState@MsaAttestationProvider@Core@Autopilot@ModernDeployment@@AEAAJAEAW4TpmKeyStateServer@3Windows@Microsoft@@@Z; ModernDeployment::Autopilot::Core::MsaAttestationProvider::CheckMsaTpmKeyState(Microsoft::Windows::Autopilot::TpmKeyStateServer &)
0x180126f17  mov     rcx, [rsp+218h]
0x180126f1f  test    eax, eax
0x180126f21  jns     short loc_180126F2A
0x180126f23  mov     edx, 0A4h
0x180126f28  jmp     short loc_180126F6E
0x180126f2a  cmp     [rsp+218h+var_1E8], 4
0x180126f2f  jz      short loc_180126F7D
0x180126f31  call    ?GetMsaKeyStateWnfName@AttestationConfigHelper@Core@Autopilot@ModernDeployment@@SA?AU_WNF_STATE_NAME@@XZ; ModernDeployment::Autopilot::Core::AttestationConfigHelper::GetMsaKeyStateWnfName(void)
0x180126f36  mov     qword ptr [rsp+218h+var_1F8], rdi; int
0x180126f3b  mov     r9d, 4
0x180126f41  lea     r8, [rsp+218h+var_158]
0x180126f49  xor     edx, edx
0x180126f4b  mov     rcx, rax
0x180126f4e  call    cs:__imp_RtlPublishWnfStateData
0x180126f55  nop     dword ptr [rax+rax+00h]
0x180126f5a  or      eax, 10000000h
0x180126f5f  mov     rcx, [rsp+218h]; this
0x180126f67  jge     short loc_180126F7D
0x180126f69  mov     edx, 0A7h; void *
0x180126f6e  mov     r9d, eax; char *
0x180126f71  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x180126f78  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180126f7d  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180126f84  jz      short loc_180126F9B
0x180126f86  mov     r8d, [rsp+218h+var_158]
0x180126f8e  lea     rdx, AutopilotAttestationMsaCompleted
0x180126f95  call    McTemplateU0q_EventWriteTransfer
0x180126f9a  nop
0x180126f9b  lea     rcx, [rsp+218h+var_148]
0x180126fa3  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x180126fa8  nop
0x180126fa9  mov     rcx, [rsi+38h]
0x180126fad  test    rcx, rcx
0x180126fb0  jz      short loc_180126FC8
0x180126fb2  mov     rax, [rcx]
0x180126fb5  cmp     rcx, rsi
0x180126fb8  setnz   dl
0x180126fbb  mov     rax, [rax+20h]
0x180126fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126fc4  mov     [rsi+38h], rdi
0x180126fc8  xor     eax, eax
0x180126fca  jmp     loc_180127228
0x180126fcf  mov     r15d, 80004004h
0x180126fd5  cmp     ebx, r15d
0x180126fd8  jnz     loc_180127094
0x180126fde  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180126fe5  jz      short loc_180127006
0x180126fe7  lea     rax, [rsp+218h+var_48]
0x180126fef  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x180126ff4  mov     r9d, 1
0x180126ffa  lea     rdx, AutopilotAttestationMsaCancelled
0x180127001  call    McGenEventWrite_EventWriteTransfer
0x180127006  mov     [r14], r15d
0x180127009  mov     dword ptr [r14+4], 3
0x180127011  cmp     [rsi+38h], rdi
0x180127015  jz      short loc_180127042
0x180127017  mov     rdx, r14
0x18012701a  mov     rcx, rsi
0x18012701d  call    ??R?$_Func_class@_N$$V@std@@QEBA_NXZ; std::_Func_class<bool,>::operator()(void)
0x180127022  mov     rcx, [rsp+218h]; this
0x18012702a  test    eax, eax
0x18012702c  jns     short loc_180127042
0x18012702e  mov     r9d, eax; char *
0x180127031  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x180127038  mov     edx, 0B5h; void *
0x18012703d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180127042  mov     rcx, [rsp+218h]; this
0x18012704a  mov     r9d, r15d; char *
0x18012704d  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x180127054  mov     edx, 0B8h; void *
0x180127059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012705e  nop
0x18012705f  lea     rcx, [rsp+218h+var_148]
0x180127067  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x18012706c  nop
0x18012706d  mov     rcx, [rsi+38h]
0x180127071  test    rcx, rcx
0x180127074  jz      short loc_18012708C
0x180127076  mov     rdx, [rcx]
0x180127079  mov     rax, [rdx+20h]
0x18012707d  cmp     rcx, rsi
0x180127080  setnz   dl
0x180127083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127088  mov     [rsi+38h], rdi
0x18012708c  mov     eax, r15d
0x18012708f  jmp     loc_180127228
0x180127094  mov     r15d, 800705B4h
0x18012709a  cmp     ebx, r15d
0x18012709d  jnz     loc_180127159
0x1801270a3  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1801270aa  jz      short loc_1801270CB
0x1801270ac  lea     rax, [rsp+218h+var_48]
0x1801270b4  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x1801270b9  mov     r9d, 1
0x1801270bf  lea     rdx, AutopilotAttestationMsaTimeout
0x1801270c6  call    McGenEventWrite_EventWriteTransfer
0x1801270cb  mov     [r14], r15d
0x1801270ce  mov     dword ptr [r14+4], 3
0x1801270d6  cmp     [rsi+38h], rdi
0x1801270da  jz      short loc_180127107
0x1801270dc  mov     rdx, r14
0x1801270df  mov     rcx, rsi
0x1801270e2  call    ??R?$_Func_class@_N$$V@std@@QEBA_NXZ; std::_Func_class<bool,>::operator()(void)
0x1801270e7  mov     rcx, [rsp+218h]; this
0x1801270ef  test    eax, eax
0x1801270f1  jns     short loc_180127107
0x1801270f3  mov     r9d, eax; char *
0x1801270f6  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801270fd  mov     edx, 0C2h; void *
0x180127102  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180127107  mov     rcx, [rsp+218h]; this
0x18012710f  mov     r9d, r15d; char *
0x180127112  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x180127119  mov     edx, 0C5h; void *
0x18012711e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180127123  nop
0x180127124  lea     rcx, [rsp+218h+var_148]
0x18012712c  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x180127131  nop
0x180127132  mov     rcx, [rsi+38h]
0x180127136  test    rcx, rcx
0x180127139  jz      short loc_180127151
0x18012713b  mov     rdx, [rcx]
0x18012713e  mov     rax, [rdx+20h]
0x180127142  cmp     rcx, rsi
0x180127145  setnz   dl
0x180127148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012714d  mov     [rsi+38h], rdi
0x180127151  mov     eax, r15d
0x180127154  jmp     loc_180127228
0x180127159  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180127160  jz      short loc_180127171
0x180127162  mov     r8d, ebx
0x180127165  lea     rdx, AutopilotAttestationMsaError
0x18012716c  call    McTemplateU0q_EventWriteTransfer
0x180127171  mov     [r14], ebx
0x180127174  mov     dword ptr [r14+4], 3
0x18012717c  cmp     [rsi+38h], rdi
0x180127180  jz      short loc_1801271AD
0x180127182  mov     rdx, r14
0x180127185  mov     rcx, rsi
0x180127188  call    ??R?$_Func_class@_N$$V@std@@QEBA_NXZ; std::_Func_class<bool,>::operator()(void)
0x18012718d  mov     rcx, [rsp+218h]; this
0x180127195  test    eax, eax
0x180127197  jns     short loc_1801271AD
0x180127199  mov     r9d, eax; char *
0x18012719c  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801271a3  mov     edx, 0CFh; void *
0x1801271a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801271ad  mov     rcx, [rsp+218h]; this
0x1801271b5  mov     r9d, ebx; char *
0x1801271b8  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801271bf  mov     edx, 0D2h; void *
0x1801271c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801271c9  nop
0x1801271ca  lea     rcx, [rsp+218h+var_148]
0x1801271d2  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x1801271d7  nop
0x1801271d8  mov     rcx, [rsi+38h]
0x1801271dc  test    rcx, rcx
0x1801271df  jz      short loc_1801271F7
0x1801271e1  mov     rax, [rcx]
0x1801271e4  cmp     rcx, rsi
0x1801271e7  setnz   dl
0x1801271ea  mov     rax, [rax+20h]
0x1801271ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801271f3  mov     [rsi+38h], rdi
0x1801271f7  mov     eax, ebx
0x1801271f9  jmp     short loc_180127228
  ... truncated ...
```
