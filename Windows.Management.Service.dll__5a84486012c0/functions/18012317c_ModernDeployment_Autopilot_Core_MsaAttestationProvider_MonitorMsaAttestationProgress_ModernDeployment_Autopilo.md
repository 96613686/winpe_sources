# ModernDeployment::Autopilot::Core::MsaAttestationProvider::MonitorMsaAttestationProgress(ModernDeployment::Autopilot::Core::AttestationPhase,Concurrency::cancellation_token_source &,std::function<long (ModernDeployment::Autopilot::Core::AttestationProviderResult const &)>,ModernDeployment::Autopilot::Core::AttestationProviderResult &)

- ea: `0x18012317c`
- end: `0x1801236f6`
- name: `?MonitorMsaAttestationProgress@MsaAttestationProvider@Core@Autopilot@ModernDeployment@@AEAAJW4AttestationPhase@234@AEAVcancellation_token_source@Concurrency@@V?$function@$$A6AJAEBUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@Z@std@@AEAUAttestationProviderResult@234@@Z`
- size: `1402`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801229fc`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007748c`
- `0x1800801fc`
- `0x1800806b0`
- `0x180080708`
- `0x180115388`
- `0x18011af64`
- `0x18011c1ec`
- `0x18011c270`
- `0x18011c298`
- `0x18011c4a4`
- `0x180122f1c`
- `0x18012317c`
- `0x180123f80`
- `0x180124030`
- `0x180124294`
- `0x1801246a4`
- `0x1801fa010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1801233fa`
- `ntdll!RtlPublishWnfStateData` at `0x1801233fa`

## string_xrefs

- `0x1801231e0`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x1801232ca`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x18012339a`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x180123417`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x1801234d7`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x1801234f3`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x18012359c`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x1801235b8`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x180123642`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`
- `0x18012365e`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\msaattestationprovider.cpp`

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
    *(_QWORD *)v49 = off_18020F9B8;
    v50 = a1;
    v51 = a4;
    v52 = v49;
    *(_QWORD *)v48 = &v53;
    v53 = off_18020F9E8;
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
        McGenEventWrite_EventWriteTransfer(v24, AutopilotAttestationMsaCancelled, v25, 1, v59);
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
        McGenEventWrite_EventWriteTransfer(v24, AutopilotAttestationMsaTimeout, v25, 1, v59);
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
0x18012317c  mov     [rsp+arg_8], rbx
0x180123181  push    rsi
0x180123182  push    rdi
0x180123183  push    r12
0x180123185  push    r14
0x180123187  push    r15
0x180123189  sub     rsp, 1F0h
0x180123190  mov     rax, cs:__security_cookie
0x180123197  xor     rax, rsp
0x18012319a  mov     [rsp+218h+var_38], rax
0x1801231a2  mov     rsi, r9
0x1801231a5  mov     r12, r8
0x1801231a8  mov     r15d, edx
0x1801231ab  mov     rbx, rcx
0x1801231ae  mov     r14, [rsp+218h+arg_20]
0x1801231b6  mov     [rsp+218h+var_160], r9
0x1801231be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801231c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801231ca  xor     edi, edi
0x1801231cc  test    al, al
0x1801231ce  jnz     short loc_180123216
0x1801231d0  mov     rcx, [rsp+218h]; this
0x1801231d8  mov     ebx, 80004001h
0x1801231dd  mov     r9d, ebx; char *
0x1801231e0  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801231e7  lea     edx, [rdi+4Fh]; void *
0x1801231ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801231ef  nop
0x1801231f0  mov     rcx, [rsi+38h]
0x1801231f4  test    rcx, rcx
0x1801231f7  jz      short loc_18012320F
0x1801231f9  mov     rdx, [rcx]
0x1801231fc  mov     rax, [rdx+20h]
0x180123200  cmp     rcx, rsi
0x180123203  setnz   dl
0x180123206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012320b  mov     [rsi+38h], rdi
0x18012320f  mov     eax, ebx
0x180123211  jmp     loc_1801236CE
0x180123216  lea     rcx, [rsp+218h+var_148]
0x18012321e  call    ??0?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x180123223  nop
0x180123224  lea     rax, [rsp+218h+var_1E0]
0x180123229  mov     qword ptr [rsp+218h+var_48], rax
0x180123231  lea     rax, off_18020F9B8
0x180123238  mov     qword ptr [rsp+218h+var_1E0], rax
0x18012323d  mov     [rsp+218h+var_1D8], rbx
0x180123242  mov     [rsp+218h+var_1D0], rsi
0x180123247  lea     rax, [rsp+218h+var_1E0]
0x18012324c  mov     [rsp+218h+var_1A8], rax
0x180123251  lea     rax, [rsp+218h+var_1A0]
0x180123256  mov     qword ptr [rsp+218h+var_1E8], rax
0x18012325b  lea     rax, off_18020F9E8
0x180123262  mov     [rsp+218h+var_1A0], rax
0x180123267  mov     [rsp+218h+var_198], r15d
0x18012326f  lea     rax, [rsp+218h+var_1A0]
0x180123274  mov     [rsp+218h+var_168], rax
0x18012327c  call    ?GetMsaTriggerWnfName@AttestationConfigHelper@Core@Autopilot@ModernDeployment@@SA?AU_WNF_STATE_NAME@@XZ; ModernDeployment::Autopilot::Core::AttestationConfigHelper::GetMsaTriggerWnfName(void)
0x180123281  mov     rbx, rax
0x180123284  call    ?IsTestModeEnabled@AttestationConfigHelper@Core@Autopilot@ModernDeployment@@SA_NXZ; ModernDeployment::Autopilot::Core::AttestationConfigHelper::IsTestModeEnabled(void)
0x180123289  mov     rdx, cs:WNF_MSA_TPM_SERVER_CLIENT_KEY_STATE_UPDATED
0x180123290  test    al, al
0x180123292  cmovnz  rdx, cs:WNF_PROV_AUTOPILOT_TEST_MSA_KEY_STATE_UPDATE
0x18012329a  lea     rax, [rsp+218h+var_1E0]
0x18012329f  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x1801232a4  lea     r9, [rsp+218h+var_1A0]
0x1801232a9  mov     r8, rbx
0x1801232ac  lea     rcx, [rsp+218h+var_148]
0x1801232b4  call    ?Initialize@?$WnfAttestationHelper@I@Core@Autopilot@ModernDeployment@@QEAAJU_WNF_STATE_NAME@@0V?$function@$$A6A_NAEBI@Z@std@@V?$function@$$A6A?AW4AttestationState@Core@Autopilot@ModernDeployment@@AEBI@Z@7@@Z; ModernDeployment::Autopilot::Core::WnfAttestationHelper<uint>::Initialize(_WNF_STATE_NAME,_WNF_STATE_NAME,std::function<bool (uint const &)>,std::function<ModernDeployment::Autopilot::Core::AttestationState (uint const &)>)
0x1801232b9  mov     ebx, eax
0x1801232bb  test    eax, eax
0x1801232bd  jns     short loc_180123310
0x1801232bf  mov     rcx, [rsp+218h]; this
0x1801232c7  mov     r9d, eax; char *
0x1801232ca  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801232d1  mov     edx, 87h; void *
0x1801232d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801232db  nop
0x1801232dc  lea     rcx, [rsp+218h+var_148]
0x1801232e4  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x1801232e9  nop
0x1801232ea  mov     rcx, [rsi+38h]
0x1801232ee  test    rcx, rcx
0x1801232f1  jz      short loc_180123309
0x1801232f3  mov     rax, [rcx]
0x1801232f6  cmp     rcx, rsi
0x1801232f9  setnz   dl
0x1801232fc  mov     rax, [rax+20h]
0x180123300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123305  mov     [rsi+38h], rdi
0x180123309  mov     eax, ebx
0x18012330b  jmp     loc_1801236CE
0x180123310  call    ?GetAdjustedTimeoutMs@AttestationConfigHelper@Core@Autopilot@ModernDeployment@@SAKK@Z; ModernDeployment::Autopilot::Core::AttestationConfigHelper::GetAdjustedTimeoutMs(ulong)
0x180123315  mov     r10d, eax
0x180123318  mov     qword ptr [rsp+218h+var_158], rdi
0x180123320  mov     [rsp+218h+var_1E8], edi
0x180123324  lea     rdx, [rsp+218h+var_48]
0x18012332c  mov     rcx, r12
0x18012332f  call    ?get_token@cancellation_token_source@Concurrency@@QEBA?AVcancellation_token@2@XZ; Concurrency::cancellation_token_source::get_token(void)
0x180123334  lea     rcx, [rsp+218h+var_1E8]
0x180123339  mov     qword ptr [rsp+218h+var_1F8], rcx; int
0x18012333e  lea     r9, [rsp+218h+var_158]
0x180123346  mov     r8, rax
0x180123349  mov     edx, r10d
0x18012334c  lea     rcx, [rsp+218h+var_148]
0x180123354  call    ?WaitForCompletion@?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAAJKVcancellation_token@Concurrency@@AEAUMsaTpmKeyState@3Windows@Microsoft@@AEAW4AttestationState@234@@Z; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::WaitForCompletion(ulong,Concurrency::cancellation_token,Microsoft::Windows::Autopilot::MsaTpmKeyState &,ModernDeployment::Autopilot::Core::AttestationState &)
0x180123359  mov     ebx, eax
0x18012335b  test    eax, eax
0x18012335d  js      loc_180123475
0x180123363  mov     [r14+8], r15d
0x180123367  mov     dword ptr [r14+4], 2
0x18012336f  mov     eax, [rsp+218h+var_1E8]
0x180123373  mov     [r14+0Ch], eax
0x180123377  mov     [r14], edi
0x18012337a  cmp     [rsi+38h], rdi
0x18012337e  jz      short loc_1801233AB
0x180123380  mov     rdx, r14
0x180123383  mov     rcx, rsi
0x180123386  call    ??R?$_Func_class@_N$$V@std@@QEBA_NXZ; std::_Func_class<bool,>::operator()(void)
0x18012338b  mov     rcx, [rsp+218h]; this
0x180123393  test    eax, eax
0x180123395  jns     short loc_1801233AB
0x180123397  mov     r9d, eax; char *
0x18012339a  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801233a1  mov     edx, 9Dh; void *
0x1801233a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801233ab  cmp     [rsp+218h+var_158], 4
0x1801233b3  jnz     short loc_180123423
0x1801233b5  mov     [rsp+218h+var_1E8], edi
0x1801233b9  lea     rdx, [rsp+218h+var_1E8]; enum Microsoft::Windows::Autopilot::TpmKeyStateServer *
0x1801233be  call    ?CheckMsaTpmKeyState@MsaAttestationProvider@Core@Autopilot@ModernDeployment@@AEAAJAEAW4TpmKeyStateServer@3Windows@Microsoft@@@Z; ModernDeployment::Autopilot::Core::MsaAttestationProvider::CheckMsaTpmKeyState(Microsoft::Windows::Autopilot::TpmKeyStateServer &)
0x1801233c3  mov     rcx, [rsp+218h]
0x1801233cb  test    eax, eax
0x1801233cd  jns     short loc_1801233D6
0x1801233cf  mov     edx, 0A4h
0x1801233d4  jmp     short loc_180123414
0x1801233d6  cmp     [rsp+218h+var_1E8], 4
0x1801233db  jz      short loc_180123423
0x1801233dd  call    ?GetMsaKeyStateWnfName@AttestationConfigHelper@Core@Autopilot@ModernDeployment@@SA?AU_WNF_STATE_NAME@@XZ; ModernDeployment::Autopilot::Core::AttestationConfigHelper::GetMsaKeyStateWnfName(void)
0x1801233e2  mov     qword ptr [rsp+218h+var_1F8], rdi; int
0x1801233e7  mov     r9d, 4
0x1801233ed  lea     r8, [rsp+218h+var_158]
0x1801233f5  xor     edx, edx
0x1801233f7  mov     rcx, rax
0x1801233fa  call    cs:__imp_RtlPublishWnfStateData
0x180123400  or      eax, 10000000h
0x180123405  mov     rcx, [rsp+218h]; this
0x18012340d  jge     short loc_180123423
0x18012340f  mov     edx, 0A7h; void *
0x180123414  mov     r9d, eax; char *
0x180123417  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012341e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180123423  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18012342a  jz      short loc_180123441
0x18012342c  mov     r8d, [rsp+218h+var_158]
0x180123434  lea     rdx, AutopilotAttestationMsaCompleted
0x18012343b  call    McTemplateU0q_EventWriteTransfer
0x180123440  nop
0x180123441  lea     rcx, [rsp+218h+var_148]
0x180123449  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x18012344e  nop
0x18012344f  mov     rcx, [rsi+38h]
0x180123453  test    rcx, rcx
0x180123456  jz      short loc_18012346E
0x180123458  mov     rax, [rcx]
0x18012345b  cmp     rcx, rsi
0x18012345e  setnz   dl
0x180123461  mov     rax, [rax+20h]
0x180123465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012346a  mov     [rsi+38h], rdi
0x18012346e  xor     eax, eax
0x180123470  jmp     loc_1801236CE
0x180123475  mov     r15d, 80004004h
0x18012347b  cmp     ebx, r15d
0x18012347e  jnz     loc_18012353A
0x180123484  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18012348b  jz      short loc_1801234AC
0x18012348d  lea     rax, [rsp+218h+var_48]
0x180123495  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x18012349a  mov     r9d, 1
0x1801234a0  lea     rdx, AutopilotAttestationMsaCancelled
0x1801234a7  call    McGenEventWrite_EventWriteTransfer
0x1801234ac  mov     [r14], r15d
0x1801234af  mov     dword ptr [r14+4], 3
0x1801234b7  cmp     [rsi+38h], rdi
0x1801234bb  jz      short loc_1801234E8
0x1801234bd  mov     rdx, r14
0x1801234c0  mov     rcx, rsi
0x1801234c3  call    ??R?$_Func_class@_N$$V@std@@QEBA_NXZ; std::_Func_class<bool,>::operator()(void)
0x1801234c8  mov     rcx, [rsp+218h]; this
0x1801234d0  test    eax, eax
0x1801234d2  jns     short loc_1801234E8
0x1801234d4  mov     r9d, eax; char *
0x1801234d7  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801234de  mov     edx, 0B5h; void *
0x1801234e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801234e8  mov     rcx, [rsp+218h]; this
0x1801234f0  mov     r9d, r15d; char *
0x1801234f3  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801234fa  mov     edx, 0B8h; void *
0x1801234ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123504  nop
0x180123505  lea     rcx, [rsp+218h+var_148]
0x18012350d  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x180123512  nop
0x180123513  mov     rcx, [rsi+38h]
0x180123517  test    rcx, rcx
0x18012351a  jz      short loc_180123532
0x18012351c  mov     rdx, [rcx]
0x18012351f  mov     rax, [rdx+20h]
0x180123523  cmp     rcx, rsi
0x180123526  setnz   dl
0x180123529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012352e  mov     [rsi+38h], rdi
0x180123532  mov     eax, r15d
0x180123535  jmp     loc_1801236CE
0x18012353a  mov     r15d, 800705B4h
0x180123540  cmp     ebx, r15d
0x180123543  jnz     loc_1801235FF
0x180123549  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180123550  jz      short loc_180123571
0x180123552  lea     rax, [rsp+218h+var_48]
0x18012355a  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x18012355f  mov     r9d, 1
0x180123565  lea     rdx, AutopilotAttestationMsaTimeout
0x18012356c  call    McGenEventWrite_EventWriteTransfer
0x180123571  mov     [r14], r15d
0x180123574  mov     dword ptr [r14+4], 3
0x18012357c  cmp     [rsi+38h], rdi
0x180123580  jz      short loc_1801235AD
0x180123582  mov     rdx, r14
0x180123585  mov     rcx, rsi
0x180123588  call    ??R?$_Func_class@_N$$V@std@@QEBA_NXZ; std::_Func_class<bool,>::operator()(void)
0x18012358d  mov     rcx, [rsp+218h]; this
0x180123595  test    eax, eax
0x180123597  jns     short loc_1801235AD
0x180123599  mov     r9d, eax; char *
0x18012359c  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801235a3  mov     edx, 0C2h; void *
0x1801235a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801235ad  mov     rcx, [rsp+218h]; this
0x1801235b5  mov     r9d, r15d; char *
0x1801235b8  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801235bf  mov     edx, 0C5h; void *
0x1801235c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801235c9  nop
0x1801235ca  lea     rcx, [rsp+218h+var_148]
0x1801235d2  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x1801235d7  nop
0x1801235d8  mov     rcx, [rsi+38h]
0x1801235dc  test    rcx, rcx
0x1801235df  jz      short loc_1801235F7
0x1801235e1  mov     rdx, [rcx]
0x1801235e4  mov     rax, [rdx+20h]
0x1801235e8  cmp     rcx, rsi
0x1801235eb  setnz   dl
0x1801235ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801235f3  mov     [rsi+38h], rdi
0x1801235f7  mov     eax, r15d
0x1801235fa  jmp     loc_1801236CE
0x1801235ff  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180123606  jz      short loc_180123617
0x180123608  mov     r8d, ebx
0x18012360b  lea     rdx, AutopilotAttestationMsaError
0x180123612  call    McTemplateU0q_EventWriteTransfer
0x180123617  mov     [r14], ebx
0x18012361a  mov     dword ptr [r14+4], 3
0x180123622  cmp     [rsi+38h], rdi
0x180123626  jz      short loc_180123653
0x180123628  mov     rdx, r14
0x18012362b  mov     rcx, rsi
0x18012362e  call    ??R?$_Func_class@_N$$V@std@@QEBA_NXZ; std::_Func_class<bool,>::operator()(void)
0x180123633  mov     rcx, [rsp+218h]; this
0x18012363b  test    eax, eax
0x18012363d  jns     short loc_180123653
0x18012363f  mov     r9d, eax; char *
0x180123642  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x180123649  mov     edx, 0CFh; void *
0x18012364e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180123653  mov     rcx, [rsp+218h]; this
0x18012365b  mov     r9d, ebx; char *
0x18012365e  lea     r8, aOnecoreuapAdmi_126; "onecoreuap\\admin\\moderndeployment\\au"...
0x180123665  mov     edx, 0D2h; void *
0x18012366a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012366f  nop
0x180123670  lea     rcx, [rsp+218h+var_148]
0x180123678  call    ??1?$WnfAttestationHelper@UMsaTpmKeyState@Autopilot@Windows@Microsoft@@@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>::~WnfAttestationHelper<Microsoft::Windows::Autopilot::MsaTpmKeyState>(void)
0x18012367d  nop
0x18012367e  mov     rcx, [rsi+38h]
0x180123682  test    rcx, rcx
0x180123685  jz      short loc_18012369D
0x180123687  mov     rax, [rcx]
0x18012368a  cmp     rcx, rsi
0x18012368d  setnz   dl
0x180123690  mov     rax, [rax+20h]
0x180123694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123699  mov     [rsi+38h], rdi
0x18012369d  mov     eax, ebx
0x18012369f  jmp     short loc_1801236CE
0x1801236a1  mov     rbx, [rsp+218h+var_160]
  ... truncated ...
```
