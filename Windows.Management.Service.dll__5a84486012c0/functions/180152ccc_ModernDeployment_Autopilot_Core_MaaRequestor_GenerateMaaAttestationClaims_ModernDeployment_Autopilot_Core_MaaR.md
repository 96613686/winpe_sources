# ModernDeployment::Autopilot::Core::MaaRequestor::GenerateMaaAttestationClaims(ModernDeployment::Autopilot::Core::MaaRequestor::MaaRequestInfo const &,ModernDeployment::Autopilot::Core::MaaRequestKeys &,ModernDeployment::Autopilot::Core::MaaRequestor::MaaResponseInfo &)

- ea: `0x180152ccc`
- end: `0x180153149`
- name: `?GenerateMaaAttestationClaims@MaaRequestor@Core@Autopilot@ModernDeployment@@QEAAJAEBVMaaRequestInfo@1234@AEAVMaaRequestKeys@234@AEAVMaaResponseInfo@1234@@Z`
- size: `1149`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::MaaRequestor *__hidden this, const struct ModernDeployment::Autopilot::Core::MaaRequestor::MaaRequestInfo *, struct ModernDeployment::Autopilot::Core::MaaRequestKeys *, struct ModernDeployment::Autopilot::Core::MaaRequestor::MaaResponseInfo *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18012f7f8`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18008019c`
- `0x1800801fc`
- `0x1800814a8`
- `0x18008943c`
- `0x18008982c`
- `0x18008dc94`
- `0x18008dd00`
- `0x180150430`
- `0x180152ccc`
- `0x180153174`
- `0x1801532f8`
- `0x1801533e0`
- `0x18015352c`
- `0x180153750`
- `0x1801546cc`
- `0x18019f59c`
- `0x18019f6b4`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180152e45`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180152f0e`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180152f9a`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180153037`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801530ba`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801530dc`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180152e45`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180152f0e`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180152f9a`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180153037`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801530ba`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801530dc`

## string_xrefs

- `0x180152d19`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180152d8b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180152dc8`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180152e31`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180152efa`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180152f7b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180153018`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x18015309b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180153105`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180152f52`: `OpenSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=38 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::MaaRequestor::GenerateMaaAttestationClaims(
        ModernDeployment::Autopilot::Core::MaaRequestor *this,
        const struct ModernDeployment::Autopilot::Core::MaaRequestor::MaaRequestInfo *a2,
        struct ModernDeployment::Autopilot::Core::MaaRequestKeys *a3,
        struct ModernDeployment::Autopilot::Core::MaaRequestor::MaaResponseInfo *a4)
{
  int v9; // eax
  ModernDeployment::Autopilot::Core::MaaRequestor *v10; // rcx
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // ebx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // ebx
  int v20; // eax
  __int64 v21; // rcx
  int Report; // eax
  __int64 v23; // rcx
  int v24; // [rsp+20h] [rbp-98h]
  int v25; // [rsp+24h] [rbp-94h] BYREF
  __int64 v26; // [rsp+28h] [rbp-90h] BYREF
  _BYTE v27[80]; // [rsp+30h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
      (const char *)0x80004001LL,
      v24);
    return 2147500033LL;
  }
  v25 = 0;
  Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(
    (Microsoft::Windows::Autopilot::ScopedTsmLogger *)v27,
    L"MicrosoftAzureAttestation",
    L"GenerateMaaAttestationClaims",
    &v25);
  if ( *((_QWORD *)a2 + 6) && *((_QWORD *)a2 + 2) )
  {
    if ( !*((_BYTE *)a3 + 488) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
        (const char *)0x80070057LL,
        v24);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v27);
      return 2147942487LL;
    }
    v9 = ModernDeployment::Autopilot::Core::MaaRequestor::SetAttestationDllDirectory();
    v11 = v9;
    v25 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
        (const char *)(unsigned int)v9,
        v24);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v27);
      return v11;
    }
    BYTE1(v24) = 1;
    v12 = ModernDeployment::Autopilot::Core::MaaRequestor::InitializeAttestationApis(v10);
    v14 = v12;
    v25 = v12;
    if ( v12 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0dz_EventWriteTransfer(
          v13,
          AutopilotMaaAttestationPhaseFailure,
          (unsigned int)v12,
          L"InitializeAttestationApis");
        v14 = v25;
      }
      if ( v14 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
          (const char *)(unsigned int)v14,
          v24);
LABEL_14:
      SetDllDirectoryW(0);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v27);
      return (unsigned int)v14;
    }
    std::wstring::operator=((char *)this + 72, a2);
    if ( std::wstring::find((char *)this + 72, L"attest/Tpm", 0) == -1 )
    {
      if ( *(_WORD *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 72)
                    + 2LL * *((_QWORD *)this + 11)
                    - 2) != 47 )
        std::wstring::push_back((char *)this + 72);
      std::wstring::append((char *)this + 72, L"attest/Tpm?api-version=2022-08-01");
    }
    v15 = ModernDeployment::Autopilot::Core::MaaRequestor::PopulateKeyInfo(this, a3);
    v14 = v15;
    v25 = v15;
    if ( v15 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0dz_EventWriteTransfer(v16, AutopilotMaaAttestationPhaseFailure, (unsigned int)v15, L"PopulateKeys");
        v14 = v25;
      }
      if ( v14 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
          (const char *)(unsigned int)v14,
          v24);
      goto LABEL_14;
    }
    v26 = 0;
    v17 = ModernDeployment::Autopilot::Core::MaaRequestor::OpenSession(this, a2, &v26);
    v19 = v17;
    v25 = v17;
    if ( v17 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0dz_EventWriteTransfer(v18, AutopilotMaaAttestationPhaseFailure, (unsigned int)v17, L"OpenSession");
        v19 = v25;
      }
      if ( v19 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
          (const char *)(unsigned int)v19,
          v24);
LABEL_42:
      __1__unique_storage_U__resource_policy__KP6AJ_K__E_1_AttestationCloseSession__YAJ0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
      SetDllDirectoryW(0);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v27);
      return (unsigned int)v19;
    }
    std::wstring::operator=((char *)this + 104, (char *)a2 + 120);
    std::wstring::operator=((char *)this + 136, (char *)a2 + 88);
    v20 = ModernDeployment::Autopilot::Core::MaaRequestor::PerformAttestation(this, &v26);
    v19 = v20;
    v25 = v20;
    if ( v20 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0dz_EventWriteTransfer(
          v21,
          AutopilotMaaAttestationPhaseFailure,
          (unsigned int)v20,
          L"PerformAttestation");
        v19 = v25;
      }
      if ( v19 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x57,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
          (const char *)(unsigned int)v19,
          v24);
      goto LABEL_42;
    }
    Report = ModernDeployment::Autopilot::Core::MaaRequestor::GetReport(this, &v26, a4);
    v19 = Report;
    v25 = Report;
    if ( Report < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0dz_EventWriteTransfer(v23, AutopilotMaaAttestationPhaseFailure, (unsigned int)Report, L"GetReport");
        v19 = v25;
      }
      if ( v19 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
          (const char *)(unsigned int)v19,
          v24);
      goto LABEL_42;
    }
    __1__unique_storage_U__resource_policy__KP6AJ_K__E_1_AttestationCloseSession__YAJ0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
    SetDllDirectoryW(0);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v27);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
      (const char *)0x80070057LL,
      v24);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v27);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180152ccc  push    rbx
0x180152cce  push    rsi
0x180152ccf  push    rdi
0x180152cd0  push    r14
0x180152cd2  push    r15
0x180152cd4  sub     rsp, 90h
0x180152cdb  mov     rax, cs:__security_cookie
0x180152ce2  xor     rax, rsp
0x180152ce5  mov     [rsp+0B8h+var_38], rax
0x180152ced  mov     r15, r9
0x180152cf0  mov     r14, r8
0x180152cf3  mov     rsi, rdx
0x180152cf6  mov     rdi, rcx
0x180152cf9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180152d00  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180152d05  test    al, al
0x180152d07  jnz     short loc_180152D31
0x180152d09  mov     rcx, [rsp+0B8h]; this
0x180152d11  mov     ebx, 80004001h
0x180152d16  mov     r9d, ebx; char *
0x180152d19  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180152d20  mov     edx, 1Fh; void *
0x180152d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180152d2a  mov     eax, ebx
0x180152d2c  jmp     loc_180153129
0x180152d31  mov     [rsp+0B8h+var_94], 0
0x180152d39  lea     r9, [rsp+0B8h+var_94]; int *
0x180152d3e  lea     r8, aGeneratemaaatt; "GenerateMaaAttestationClaims"
0x180152d45  lea     rdx, aMicrosoftazure; "MicrosoftAzureAttestation"
0x180152d4c  lea     rcx, [rsp+0B8h+var_88]; this
0x180152d51  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x180152d56  nop
0x180152d57  cmp     qword ptr [rsi+30h], 0
0x180152d5c  jz      loc_1801530F1
0x180152d62  cmp     qword ptr [rsi+10h], 0
0x180152d67  jz      loc_1801530F1
0x180152d6d  cmp     byte ptr [r14+1E8h], 0
0x180152d75  jnz     short loc_180152DAE
0x180152d77  mov     ebx, 80070057h
0x180152d7c  mov     [rsp+0B8h+var_94], ebx
0x180152d80  mov     rcx, [rsp+0B8h]; this
0x180152d88  mov     r9d, ebx; char *
0x180152d8b  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180152d92  mov     edx, 26h ; '&'; void *
0x180152d97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180152d9c  nop
0x180152d9d  lea     rcx, [rsp+0B8h+var_88]; this
0x180152da2  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180152da7  mov     eax, ebx
0x180152da9  jmp     loc_180153129
0x180152dae  call    ?SetAttestationDllDirectory@MaaRequestor@Core@Autopilot@ModernDeployment@@KAJXZ; ModernDeployment::Autopilot::Core::MaaRequestor::SetAttestationDllDirectory(void)
0x180152db3  mov     ebx, eax
0x180152db5  mov     [rsp+0B8h+var_94], eax
0x180152db9  test    eax, eax
0x180152dbb  jns     short loc_180152DEB
0x180152dbd  mov     rcx, [rsp+0B8h]; this
0x180152dc5  mov     r9d, eax; char *
0x180152dc8  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180152dcf  mov     edx, 29h ; ')'; void *
0x180152dd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180152dd9  nop
0x180152dda  lea     rcx, [rsp+0B8h+var_88]; this
0x180152ddf  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180152de4  mov     eax, ebx
0x180152de6  jmp     loc_180153129
0x180152deb  mov     [rsp+0B8h+var_97], 1
0x180152df0  call    ?InitializeAttestationApis@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJXZ; ModernDeployment::Autopilot::Core::MaaRequestor::InitializeAttestationApis(void)
0x180152df5  mov     ebx, eax
0x180152df7  mov     [rsp+0B8h+var_94], eax
0x180152dfb  test    eax, eax
0x180152dfd  jns     short loc_180152E5D
0x180152dff  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180152e06  jz      short loc_180152E22
0x180152e08  lea     r9, aInitializeatte_0; "InitializeAttestationApis"
0x180152e0f  mov     r8d, eax
0x180152e12  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180152e19  call    McTemplateU0dz_EventWriteTransfer
0x180152e1e  mov     ebx, [rsp+0B8h+var_94]
0x180152e22  test    ebx, ebx
0x180152e24  jns     short loc_180152E43
0x180152e26  mov     rcx, [rsp+0B8h]; this
0x180152e2e  mov     r9d, ebx; char *
0x180152e31  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180152e38  mov     edx, 32h ; '2'; void *
0x180152e3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180152e42  nop
0x180152e43  xor     ecx, ecx; lpPathName
0x180152e45  call    cs:__imp_SetDllDirectoryW
0x180152e4b  nop
0x180152e4c  lea     rcx, [rsp+0B8h+var_88]; this
0x180152e51  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180152e56  mov     eax, ebx
0x180152e58  jmp     loc_180153129
0x180152e5d  lea     rbx, [rdi+48h]
0x180152e61  mov     rdx, rsi
0x180152e64  mov     rcx, rbx
0x180152e67  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180152e6c  xor     r8d, r8d
0x180152e6f  lea     rdx, aAttestTpm; "attest/Tpm"
0x180152e76  mov     rcx, rbx
0x180152e79  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180152e7e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180152e82  jnz     short loc_180152EB3
0x180152e84  mov     rcx, rbx
0x180152e87  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180152e8c  mov     rcx, [rbx+10h]
0x180152e90  mov     edx, 2Fh ; '/'
0x180152e95  cmp     [rax+rcx*2-2], dx
0x180152e9a  jz      short loc_180152EA4
0x180152e9c  mov     rcx, rbx
0x180152e9f  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180152ea4  lea     rdx, aAttestTpmApiVe; "attest/Tpm?api-version=2022-08-01"
0x180152eab  mov     rcx, rbx
0x180152eae  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180152eb3  mov     rdx, r14; struct ModernDeployment::Autopilot::Core::MaaRequestKeys *
0x180152eb6  mov     rcx, rdi; this
0x180152eb9  call    ?PopulateKeyInfo@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEAVMaaRequestKeys@234@@Z; ModernDeployment::Autopilot::Core::MaaRequestor::PopulateKeyInfo(ModernDeployment::Autopilot::Core::MaaRequestKeys &)
0x180152ebe  mov     ebx, eax
0x180152ec0  mov     [rsp+0B8h+var_94], eax
0x180152ec4  test    eax, eax
0x180152ec6  jns     short loc_180152F26
0x180152ec8  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180152ecf  jz      short loc_180152EEB
0x180152ed1  lea     r9, aPopulatekeys; "PopulateKeys"
0x180152ed8  mov     r8d, eax
0x180152edb  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180152ee2  call    McTemplateU0dz_EventWriteTransfer
0x180152ee7  mov     ebx, [rsp+0B8h+var_94]
0x180152eeb  test    ebx, ebx
0x180152eed  jns     short loc_180152F0C
0x180152eef  mov     rcx, [rsp+0B8h]; this
0x180152ef7  mov     r9d, ebx; char *
0x180152efa  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180152f01  mov     edx, 46h ; 'F'; void *
0x180152f06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180152f0b  nop
0x180152f0c  xor     ecx, ecx; lpPathName
0x180152f0e  call    cs:__imp_SetDllDirectoryW
0x180152f14  nop
0x180152f15  lea     rcx, [rsp+0B8h+var_88]; this
0x180152f1a  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180152f1f  mov     eax, ebx
0x180152f21  jmp     loc_180153129
0x180152f26  mov     [rsp+0B8h+var_90], 0
0x180152f2f  lea     r8, [rsp+0B8h+var_90]
0x180152f34  mov     rdx, rsi
0x180152f37  mov     rcx, rdi
0x180152f3a  call    ?OpenSession@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEBVMaaRequestInfo@1234@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x180152f3f  mov     ebx, eax
0x180152f41  mov     [rsp+0B8h+var_94], eax
0x180152f45  test    eax, eax
0x180152f47  jns     short loc_180152FB2
0x180152f49  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180152f50  jz      short loc_180152F6C
0x180152f52  lea     r9, aOpensession; "OpenSession"
0x180152f59  mov     r8d, eax
0x180152f5c  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180152f63  call    McTemplateU0dz_EventWriteTransfer
0x180152f68  mov     ebx, [rsp+0B8h+var_94]
0x180152f6c  test    ebx, ebx
0x180152f6e  jns     short loc_180152F8D
0x180152f70  mov     rcx, [rsp+0B8h]; this
0x180152f78  mov     r9d, ebx; char *
0x180152f7b  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180152f82  mov     edx, 4Eh ; 'N'; void *
0x180152f87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180152f8c  nop
0x180152f8d  lea     rcx, [rsp+0B8h+var_90]
0x180152f92  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180152f97  nop
0x180152f98  xor     ecx, ecx; lpPathName
0x180152f9a  call    cs:__imp_SetDllDirectoryW
0x180152fa0  nop
0x180152fa1  lea     rcx, [rsp+0B8h+var_88]; this
0x180152fa6  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180152fab  mov     eax, ebx
0x180152fad  jmp     loc_180153129
0x180152fb2  lea     rdx, [rsi+78h]
0x180152fb6  lea     rcx, [rdi+68h]
0x180152fba  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180152fbf  lea     rdx, [rsi+58h]
0x180152fc3  lea     rcx, [rdi+88h]
0x180152fca  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180152fcf  lea     rdx, [rsp+0B8h+var_90]
0x180152fd4  mov     rcx, rdi
0x180152fd7  call    ?PerformAttestation@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x180152fdc  mov     ebx, eax
0x180152fde  mov     [rsp+0B8h+var_94], eax
0x180152fe2  test    eax, eax
0x180152fe4  jns     short loc_18015304F
0x180152fe6  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180152fed  jz      short loc_180153009
0x180152fef  lea     r9, aPerformattesta; "PerformAttestation"
0x180152ff6  mov     r8d, eax
0x180152ff9  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180153000  call    McTemplateU0dz_EventWriteTransfer
0x180153005  mov     ebx, [rsp+0B8h+var_94]
0x180153009  test    ebx, ebx
0x18015300b  jns     short loc_18015302A
0x18015300d  mov     rcx, [rsp+0B8h]; this
0x180153015  mov     r9d, ebx; char *
0x180153018  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015301f  mov     edx, 57h ; 'W'; void *
0x180153024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180153029  nop
0x18015302a  lea     rcx, [rsp+0B8h+var_90]
0x18015302f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180153034  nop
0x180153035  xor     ecx, ecx; lpPathName
0x180153037  call    cs:__imp_SetDllDirectoryW
0x18015303d  nop
0x18015303e  lea     rcx, [rsp+0B8h+var_88]; this
0x180153043  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180153048  mov     eax, ebx
0x18015304a  jmp     loc_180153129
0x18015304f  mov     r8, r15
0x180153052  lea     rdx, [rsp+0B8h+var_90]
0x180153057  mov     rcx, rdi
0x18015305a  call    ?GetReport@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVMaaResponseInfo@1234@@Z
0x18015305f  mov     ebx, eax
0x180153061  mov     [rsp+0B8h+var_94], eax
0x180153065  test    eax, eax
0x180153067  jns     short loc_1801530CF
0x180153069  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180153070  jz      short loc_18015308C
0x180153072  lea     r9, aGetreport; "GetReport"
0x180153079  mov     r8d, eax
0x18015307c  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180153083  call    McTemplateU0dz_EventWriteTransfer
0x180153088  mov     ebx, [rsp+0B8h+var_94]
0x18015308c  test    ebx, ebx
0x18015308e  jns     short loc_1801530AD
0x180153090  mov     rcx, [rsp+0B8h]; this
0x180153098  mov     r9d, ebx; char *
0x18015309b  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801530a2  mov     edx, 5Eh ; '^'; void *
0x1801530a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801530ac  nop
0x1801530ad  lea     rcx, [rsp+0B8h+var_90]
0x1801530b2  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801530b7  nop
0x1801530b8  xor     ecx, ecx; lpPathName
0x1801530ba  call    cs:__imp_SetDllDirectoryW
0x1801530c0  nop
0x1801530c1  lea     rcx, [rsp+0B8h+var_88]; this
0x1801530c6  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801530cb  mov     eax, ebx
0x1801530cd  jmp     short loc_180153129
0x1801530cf  lea     rcx, [rsp+0B8h+var_90]
0x1801530d4  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801530d9  nop
0x1801530da  xor     ecx, ecx; lpPathName
0x1801530dc  call    cs:__imp_SetDllDirectoryW
0x1801530e2  nop
0x1801530e3  lea     rcx, [rsp+0B8h+var_88]; this
0x1801530e8  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801530ed  xor     eax, eax
0x1801530ef  jmp     short loc_180153129
0x1801530f1  mov     ebx, 80070057h
0x1801530f6  mov     [rsp+0B8h+var_94], ebx
0x1801530fa  mov     rcx, [rsp+0B8h]; this
0x180153102  mov     r9d, ebx; char *
0x180153105  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015310c  mov     edx, 25h ; '%'; void *
0x180153111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180153116  nop
0x180153117  lea     rcx, [rsp+0B8h+var_88]; this
0x18015311c  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180153121  mov     eax, ebx
0x180153123  jmp     short loc_180153129
0x180153125  mov     eax, [rsp+0B8h+var_94]
0x180153129  mov     rcx, [rsp+0B8h+var_38]
0x180153131  xor     rcx, rsp; StackCookie
0x180153134  call    __security_check_cookie
0x180153139  add     rsp, 90h
0x180153140  pop     r15
0x180153142  pop     r14
0x180153144  pop     rdi
0x180153145  pop     rsi
0x180153146  pop     rbx
0x180153147  retn
```
