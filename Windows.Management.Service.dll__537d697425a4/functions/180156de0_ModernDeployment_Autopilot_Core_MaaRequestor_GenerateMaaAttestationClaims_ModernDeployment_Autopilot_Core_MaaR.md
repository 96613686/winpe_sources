# ModernDeployment::Autopilot::Core::MaaRequestor::GenerateMaaAttestationClaims(ModernDeployment::Autopilot::Core::MaaRequestor::MaaRequestInfo const &,ModernDeployment::Autopilot::Core::MaaRequestKeys &,ModernDeployment::Autopilot::Core::MaaRequestor::MaaResponseInfo &)

- ea: `0x180156de0`
- end: `0x180157281`
- name: `?GenerateMaaAttestationClaims@MaaRequestor@Core@Autopilot@ModernDeployment@@QEAAJAEBVMaaRequestInfo@1234@AEAVMaaRequestKeys@234@AEAVMaaResponseInfo@1234@@Z`
- size: `1185`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::MaaRequestor *__hidden this, const struct ModernDeployment::Autopilot::Core::MaaRequestor::MaaRequestInfo *, struct ModernDeployment::Autopilot::Core::MaaRequestKeys *, struct ModernDeployment::Autopilot::Core::MaaRequestor::MaaResponseInfo *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180133578`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180080bac`
- `0x180080c10`
- `0x180081f38`
- `0x18008a314`
- `0x18008a67c`
- `0x18008ed78`
- `0x18008edec`
- `0x180154490`
- `0x180156de0`
- `0x1801572ac`
- `0x18015743c`
- `0x18015752c`
- `0x180157684`
- `0x1801578a8`
- `0x18015880c`
- `0x1801a4a04`
- `0x1801a4b1c`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180156f59`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180157028`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801570ba`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18015715d`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801571e6`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18015720e`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180156f59`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180157028`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801570ba`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18015715d`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1801571e6`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18015720e`

## string_xrefs

- `0x180156e2d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180156e9f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180156edc`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180156f45`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180157014`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x18015709b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x18015713e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x1801571c7`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x18015723d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180157072`: `OpenSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
0x180156de0  push    rbx
0x180156de2  push    rsi
0x180156de3  push    rdi
0x180156de4  push    r14
0x180156de6  push    r15
0x180156de8  sub     rsp, 90h
0x180156def  mov     rax, cs:__security_cookie
0x180156df6  xor     rax, rsp
0x180156df9  mov     [rsp+0B8h+var_38], rax
0x180156e01  mov     r15, r9
0x180156e04  mov     r14, r8
0x180156e07  mov     rsi, rdx
0x180156e0a  mov     rdi, rcx
0x180156e0d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180156e14  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180156e19  test    al, al
0x180156e1b  jnz     short loc_180156E45
0x180156e1d  mov     rcx, [rsp+0B8h]; this
0x180156e25  mov     ebx, 80004001h
0x180156e2a  mov     r9d, ebx; char *
0x180156e2d  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180156e34  mov     edx, 1Fh; void *
0x180156e39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180156e3e  mov     eax, ebx
0x180156e40  jmp     loc_180157261
0x180156e45  mov     [rsp+0B8h+var_94], 0
0x180156e4d  lea     r9, [rsp+0B8h+var_94]; int *
0x180156e52  lea     r8, aGeneratemaaatt; "GenerateMaaAttestationClaims"
0x180156e59  lea     rdx, aMicrosoftazure; "MicrosoftAzureAttestation"
0x180156e60  lea     rcx, [rsp+0B8h+var_88]; this
0x180156e65  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x180156e6a  nop
0x180156e6b  cmp     qword ptr [rsi+30h], 0
0x180156e70  jz      loc_180157229
0x180156e76  cmp     qword ptr [rsi+10h], 0
0x180156e7b  jz      loc_180157229
0x180156e81  cmp     byte ptr [r14+1E8h], 0
0x180156e89  jnz     short loc_180156EC2
0x180156e8b  mov     ebx, 80070057h
0x180156e90  mov     [rsp+0B8h+var_94], ebx
0x180156e94  mov     rcx, [rsp+0B8h]; this
0x180156e9c  mov     r9d, ebx; char *
0x180156e9f  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180156ea6  mov     edx, 26h ; '&'; void *
0x180156eab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180156eb0  nop
0x180156eb1  lea     rcx, [rsp+0B8h+var_88]; this
0x180156eb6  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180156ebb  mov     eax, ebx
0x180156ebd  jmp     loc_180157261
0x180156ec2  call    ?SetAttestationDllDirectory@MaaRequestor@Core@Autopilot@ModernDeployment@@KAJXZ; ModernDeployment::Autopilot::Core::MaaRequestor::SetAttestationDllDirectory(void)
0x180156ec7  mov     ebx, eax
0x180156ec9  mov     [rsp+0B8h+var_94], eax
0x180156ecd  test    eax, eax
0x180156ecf  jns     short loc_180156EFF
0x180156ed1  mov     rcx, [rsp+0B8h]; this
0x180156ed9  mov     r9d, eax; char *
0x180156edc  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180156ee3  mov     edx, 29h ; ')'; void *
0x180156ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180156eed  nop
0x180156eee  lea     rcx, [rsp+0B8h+var_88]; this
0x180156ef3  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180156ef8  mov     eax, ebx
0x180156efa  jmp     loc_180157261
0x180156eff  mov     [rsp+0B8h+var_97], 1
0x180156f04  call    ?InitializeAttestationApis@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJXZ; ModernDeployment::Autopilot::Core::MaaRequestor::InitializeAttestationApis(void)
0x180156f09  mov     ebx, eax
0x180156f0b  mov     [rsp+0B8h+var_94], eax
0x180156f0f  test    eax, eax
0x180156f11  jns     short loc_180156F77
0x180156f13  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180156f1a  jz      short loc_180156F36
0x180156f1c  lea     r9, aInitializeatte_0; "InitializeAttestationApis"
0x180156f23  mov     r8d, eax
0x180156f26  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180156f2d  call    McTemplateU0dz_EventWriteTransfer
0x180156f32  mov     ebx, [rsp+0B8h+var_94]
0x180156f36  test    ebx, ebx
0x180156f38  jns     short loc_180156F57
0x180156f3a  mov     rcx, [rsp+0B8h]; this
0x180156f42  mov     r9d, ebx; char *
0x180156f45  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180156f4c  mov     edx, 32h ; '2'; void *
0x180156f51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180156f56  nop
0x180156f57  xor     ecx, ecx; lpPathName
0x180156f59  call    cs:__imp_SetDllDirectoryW
0x180156f60  nop     dword ptr [rax+rax+00h]
0x180156f65  nop
0x180156f66  lea     rcx, [rsp+0B8h+var_88]; this
0x180156f6b  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180156f70  mov     eax, ebx
0x180156f72  jmp     loc_180157261
0x180156f77  lea     rbx, [rdi+48h]
0x180156f7b  mov     rdx, rsi
0x180156f7e  mov     rcx, rbx
0x180156f81  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180156f86  xor     r8d, r8d
0x180156f89  lea     rdx, aAttestTpm; "attest/Tpm"
0x180156f90  mov     rcx, rbx
0x180156f93  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180156f98  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180156f9c  jnz     short loc_180156FCD
0x180156f9e  mov     rcx, rbx
0x180156fa1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180156fa6  mov     rcx, [rbx+10h]
0x180156faa  mov     edx, 2Fh ; '/'
0x180156faf  cmp     [rax+rcx*2-2], dx
0x180156fb4  jz      short loc_180156FBE
0x180156fb6  mov     rcx, rbx
0x180156fb9  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180156fbe  lea     rdx, aAttestTpmApiVe; "attest/Tpm?api-version=2022-08-01"
0x180156fc5  mov     rcx, rbx
0x180156fc8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180156fcd  mov     rdx, r14; struct ModernDeployment::Autopilot::Core::MaaRequestKeys *
0x180156fd0  mov     rcx, rdi; this
0x180156fd3  call    ?PopulateKeyInfo@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEAVMaaRequestKeys@234@@Z; ModernDeployment::Autopilot::Core::MaaRequestor::PopulateKeyInfo(ModernDeployment::Autopilot::Core::MaaRequestKeys &)
0x180156fd8  mov     ebx, eax
0x180156fda  mov     [rsp+0B8h+var_94], eax
0x180156fde  test    eax, eax
0x180156fe0  jns     short loc_180157046
0x180156fe2  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180156fe9  jz      short loc_180157005
0x180156feb  lea     r9, aPopulatekeys; "PopulateKeys"
0x180156ff2  mov     r8d, eax
0x180156ff5  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180156ffc  call    McTemplateU0dz_EventWriteTransfer
0x180157001  mov     ebx, [rsp+0B8h+var_94]
0x180157005  test    ebx, ebx
0x180157007  jns     short loc_180157026
0x180157009  mov     rcx, [rsp+0B8h]; this
0x180157011  mov     r9d, ebx; char *
0x180157014  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015701b  mov     edx, 46h ; 'F'; void *
0x180157020  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180157025  nop
0x180157026  xor     ecx, ecx; lpPathName
0x180157028  call    cs:__imp_SetDllDirectoryW
0x18015702f  nop     dword ptr [rax+rax+00h]
0x180157034  nop
0x180157035  lea     rcx, [rsp+0B8h+var_88]; this
0x18015703a  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18015703f  mov     eax, ebx
0x180157041  jmp     loc_180157261
0x180157046  mov     [rsp+0B8h+var_90], 0
0x18015704f  lea     r8, [rsp+0B8h+var_90]
0x180157054  mov     rdx, rsi
0x180157057  mov     rcx, rdi
0x18015705a  call    ?OpenSession@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEBVMaaRequestInfo@1234@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x18015705f  mov     ebx, eax
0x180157061  mov     [rsp+0B8h+var_94], eax
0x180157065  test    eax, eax
0x180157067  jns     short loc_1801570D8
0x180157069  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180157070  jz      short loc_18015708C
0x180157072  lea     r9, aOpensession; "OpenSession"
0x180157079  mov     r8d, eax
0x18015707c  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180157083  call    McTemplateU0dz_EventWriteTransfer
0x180157088  mov     ebx, [rsp+0B8h+var_94]
0x18015708c  test    ebx, ebx
0x18015708e  jns     short loc_1801570AD
0x180157090  mov     rcx, [rsp+0B8h]; this
0x180157098  mov     r9d, ebx; char *
0x18015709b  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801570a2  mov     edx, 4Eh ; 'N'; void *
0x1801570a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801570ac  nop
0x1801570ad  lea     rcx, [rsp+0B8h+var_90]
0x1801570b2  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801570b7  nop
0x1801570b8  xor     ecx, ecx; lpPathName
0x1801570ba  call    cs:__imp_SetDllDirectoryW
0x1801570c1  nop     dword ptr [rax+rax+00h]
0x1801570c6  nop
0x1801570c7  lea     rcx, [rsp+0B8h+var_88]; this
0x1801570cc  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801570d1  mov     eax, ebx
0x1801570d3  jmp     loc_180157261
0x1801570d8  lea     rdx, [rsi+78h]
0x1801570dc  lea     rcx, [rdi+68h]
0x1801570e0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801570e5  lea     rdx, [rsi+58h]
0x1801570e9  lea     rcx, [rdi+88h]
0x1801570f0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801570f5  lea     rdx, [rsp+0B8h+var_90]
0x1801570fa  mov     rcx, rdi
0x1801570fd  call    ?PerformAttestation@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x180157102  mov     ebx, eax
0x180157104  mov     [rsp+0B8h+var_94], eax
0x180157108  test    eax, eax
0x18015710a  jns     short loc_18015717B
0x18015710c  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180157113  jz      short loc_18015712F
0x180157115  lea     r9, aPerformattesta; "PerformAttestation"
0x18015711c  mov     r8d, eax
0x18015711f  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x180157126  call    McTemplateU0dz_EventWriteTransfer
0x18015712b  mov     ebx, [rsp+0B8h+var_94]
0x18015712f  test    ebx, ebx
0x180157131  jns     short loc_180157150
0x180157133  mov     rcx, [rsp+0B8h]; this
0x18015713b  mov     r9d, ebx; char *
0x18015713e  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180157145  mov     edx, 57h ; 'W'; void *
0x18015714a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015714f  nop
0x180157150  lea     rcx, [rsp+0B8h+var_90]
0x180157155  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18015715a  nop
0x18015715b  xor     ecx, ecx; lpPathName
0x18015715d  call    cs:__imp_SetDllDirectoryW
0x180157164  nop     dword ptr [rax+rax+00h]
0x180157169  nop
0x18015716a  lea     rcx, [rsp+0B8h+var_88]; this
0x18015716f  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180157174  mov     eax, ebx
0x180157176  jmp     loc_180157261
0x18015717b  mov     r8, r15
0x18015717e  lea     rdx, [rsp+0B8h+var_90]
0x180157183  mov     rcx, rdi
0x180157186  call    ?GetReport@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVMaaResponseInfo@1234@@Z
0x18015718b  mov     ebx, eax
0x18015718d  mov     [rsp+0B8h+var_94], eax
0x180157191  test    eax, eax
0x180157193  jns     short loc_180157201
0x180157195  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18015719c  jz      short loc_1801571B8
0x18015719e  lea     r9, aGetreport; "GetReport"
0x1801571a5  mov     r8d, eax
0x1801571a8  lea     rdx, AutopilotMaaAttestationPhaseFailure
0x1801571af  call    McTemplateU0dz_EventWriteTransfer
0x1801571b4  mov     ebx, [rsp+0B8h+var_94]
0x1801571b8  test    ebx, ebx
0x1801571ba  jns     short loc_1801571D9
0x1801571bc  mov     rcx, [rsp+0B8h]; this
0x1801571c4  mov     r9d, ebx; char *
0x1801571c7  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801571ce  mov     edx, 5Eh ; '^'; void *
0x1801571d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801571d8  nop
0x1801571d9  lea     rcx, [rsp+0B8h+var_90]
0x1801571de  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801571e3  nop
0x1801571e4  xor     ecx, ecx; lpPathName
0x1801571e6  call    cs:__imp_SetDllDirectoryW
0x1801571ed  nop     dword ptr [rax+rax+00h]
0x1801571f2  nop
0x1801571f3  lea     rcx, [rsp+0B8h+var_88]; this
0x1801571f8  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801571fd  mov     eax, ebx
0x1801571ff  jmp     short loc_180157261
0x180157201  lea     rcx, [rsp+0B8h+var_90]
0x180157206  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@_E$1?AttestationCloseSession@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18015720b  nop
0x18015720c  xor     ecx, ecx; lpPathName
0x18015720e  call    cs:__imp_SetDllDirectoryW
0x180157215  nop     dword ptr [rax+rax+00h]
0x18015721a  nop
0x18015721b  lea     rcx, [rsp+0B8h+var_88]; this
0x180157220  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180157225  xor     eax, eax
0x180157227  jmp     short loc_180157261
0x180157229  mov     ebx, 80070057h
0x18015722e  mov     [rsp+0B8h+var_94], ebx
0x180157232  mov     rcx, [rsp+0B8h]; this
0x18015723a  mov     r9d, ebx; char *
0x18015723d  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180157244  mov     edx, 25h ; '%'; void *
0x180157249  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015724e  nop
0x18015724f  lea     rcx, [rsp+0B8h+var_88]; this
0x180157254  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180157259  mov     eax, ebx
0x18015725b  jmp     short loc_180157261
0x18015725d  mov     eax, [rsp+0B8h+var_94]
0x180157261  mov     rcx, [rsp+0B8h+var_38]
0x180157269  xor     rcx, rsp; StackCookie
0x18015726c  call    __security_check_cookie
0x180157271  add     rsp, 90h
0x180157278  pop     r15
0x18015727a  pop     r14
0x18015727c  pop     rdi
0x18015727d  pop     rsi
0x18015727e  pop     rbx
0x18015727f  retn
```
