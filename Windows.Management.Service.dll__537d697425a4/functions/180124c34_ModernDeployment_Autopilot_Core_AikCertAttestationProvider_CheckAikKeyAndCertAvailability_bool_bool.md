# ModernDeployment::Autopilot::Core::AikCertAttestationProvider::CheckAikKeyAndCertAvailability(bool &,bool &)

- ea: `0x180124c34`
- end: `0x1801250c2`
- name: `?CheckAikKeyAndCertAvailability@AikCertAttestationProvider@Core@Autopilot@ModernDeployment@@AEAAJAEA_N0@Z`
- size: `1166`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::AikCertAttestationProvider *__hidden this, bool *, bool *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180124490`
- `0x180125484`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180073768`
- `0x180080c10`
- `0x1800810f0`
- `0x180081150`
- `0x1800d238c`
- `0x180123edc`
- `0x1801243d0`
- `0x180124430`
- `0x180124c34`
- `0x180125420`
- `0x180126130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124e77`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124e77`
- `ncrypt!NCryptOpenKey` at `0x180124ebd`
- `ncrypt!NCryptOpenKey` at `0x180124ebd`
- `ncrypt!NCryptGetProperty` at `0x180124f91`
- `ncrypt!NCryptGetProperty` at `0x180124f91`
- `ncrypt!NCryptEnumKeys` at `0x180124e39`
- `ncrypt!NCryptEnumKeys` at `0x180124e39`
- `ncrypt!NCryptSetProperty` at `0x180124dad`
- `ncrypt!NCryptSetProperty` at `0x180124dad`
- `ncrypt!NCryptOpenStorageProvider` at `0x180124cfb`
- `ncrypt!NCryptOpenStorageProvider` at `0x180124cfb`

## string_xrefs

- `0x180124ca7`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`
- `0x180124d18`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`
- `0x180124d5a`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`
- `0x180125015`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`
- `0x18012507b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::AikCertAttestationProvider::CheckAikKeyAndCertAvailability(
        ModernDeployment::Autopilot::Core::AikCertAttestationProvider *this,
        bool *a2,
        bool *a3)
{
  bool *v5; // r8
  int IsAikKeyAndCertRequired; // eax
  unsigned int v7; // ebx
  bool v9; // r14
  SECURITY_STATUS v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r9
  SECURITY_STATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned int v19; // ebx
  int i; // edi
  unsigned int v21; // r12d
  SECURITY_STATUS v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned int v25; // edi
  SECURITY_STATUS Property; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  int dwFlags; // [rsp+20h] [rbp-98h]
  int dwFlagsa; // [rsp+20h] [rbp-98h]
  bool v31; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v32[7]; // [rsp+31h] [rbp-87h] BYREF
  PBYTE pbInput; // [rsp+38h] [rbp-80h] BYREF
  _QWORD *v34; // [rsp+40h] [rbp-78h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+48h] [rbp-70h] BYREF
  char v36; // [rsp+50h] [rbp-68h]
  PVOID ppEnumState; // [rsp+58h] [rbp-60h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+60h] [rbp-58h] BYREF
  DWORD pcbResult; // [rsp+68h] [rbp-50h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp-48h] BYREF
  _QWORD v41[2]; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v32[0] = 0;
    v31 = 0;
    IsAikKeyAndCertRequired = ModernDeployment::Autopilot::Core::IsAikKeyAndCertRequired(
                                (ModernDeployment::Autopilot::Core *)v32,
                                &v31,
                                v5);
    v7 = IsAikKeyAndCertRequired;
    if ( IsAikKeyAndCertRequired >= 0 )
    {
      v9 = v31;
      if ( v32[0] || v31 )
      {
        *a2 = 0;
        *a3 = 0;
        phProvider = 0;
        v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
        v12 = v10;
        if ( v10 >= 0 )
        {
          pbInput = 0;
          v13 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                  v11,
                  &pbInput);
          v14 = v13;
          if ( v13 >= 0 )
          {
            v15 = -1;
            do
              ++v15;
            while ( *(_WORD *)&pbInput[2 * v15] );
            v16 = NCryptSetProperty(phProvider, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", pbInput, 2 * v15, 0);
            v19 = v16;
            if ( v16 >= 0 )
            {
              ppEnumState = 0;
              for ( i = 0; i < 20; ++i )
              {
                v41[0] = 0;
                v34 = v41;
                ppKeyName = 0;
                v36 = 1;
                v21 = NCryptEnumKeys(phProvider, 0, &ppKeyName, &ppEnumState, 0x60u);
                wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>(&v34);
                if ( v21 == -2146893782 )
                  goto LABEL_41;
                if ( v21 )
                {
                  wil::details::in1diag3::Log_Hr(
                    retaddr,
                    (void *)0x1DE,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
                    (const char *)v21,
                    dwFlagsa);
LABEL_41:
                  wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>::reset(
                    v41,
                    0);
                  break;
                }
                if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)v41[0], L"Windows AIK") )
                {
                  wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>::reset(
                    v41,
                    0);
                  phKey = 0;
                  v22 = NCryptOpenKey(phProvider, &phKey, L"Windows AIK", 0, 0);
                  v25 = v22;
                  if ( v22 >= 0 )
                  {
                    *a2 = 1;
                    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
                      McGenEventWrite_EventWriteTransfer(v23, AutopilotAttestationAikKeyFound, v24, 1);
                    if ( v9 )
                    {
                      pcbResult = 0;
                      Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0);
                      if ( Property >= 0 && pcbResult )
                      {
                        *a3 = 1;
                        if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
                          McGenEventWrite_EventWriteTransfer(v27, AutopilotAttestationAikCertFound, v28, 1);
                      }
                      else if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
                      {
                        McTemplateU0q_EventWriteTransfer(
                          v27,
                          AutopilotAttestationAikCertNotFound,
                          (unsigned int)Property);
                      }
                      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
                      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
                      return 0;
                    }
                    else
                    {
                      *a3 = 1;
                      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
                      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
                      return 0;
                    }
                  }
                  else
                  {
                    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
                      McTemplateU0q_EventWriteTransfer(v23, AutopilotAttestationAikKeyOpenFailed, (unsigned int)v22);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
                    if ( v25 == -2146893807 )
                      return 0;
                    else
                      return v25;
                  }
                }
                wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>::reset(
                  v41,
                  0);
              }
              if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
                McGenEventWrite_EventWriteTransfer(v17, AutopilotAttestationAikKeyNotFound, v18, 1);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
              return 0;
            }
            else
            {
              if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
                McTemplateU0q_EventWriteTransfer(v17, AutopilotAttestationAikLocationFailed, (unsigned int)v16);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
              return v19;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B5,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
              (const char *)(unsigned int)v13,
              dwFlags);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
            return v14;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B1,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
            (const char *)(unsigned int)v10,
            dwFlags);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
          return v12;
        }
      }
      else
      {
        *a2 = 1;
        *a3 = 1;
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
        (const char *)(unsigned int)IsAikKeyAndCertRequired,
        dwFlags);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
      (const char *)0x80004001LL,
      dwFlags);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180124c34  mov     [rsp+arg_0], rbx
0x180124c39  mov     [rsp+arg_18], rsi
0x180124c3e  push    rdi
0x180124c3f  push    r12
0x180124c41  push    r13
0x180124c43  push    r14
0x180124c45  push    r15
0x180124c47  sub     rsp, 90h
0x180124c4e  mov     rax, cs:__security_cookie
0x180124c55  xor     rax, rsp
0x180124c58  mov     [rsp+0B8h+var_30], rax
0x180124c60  mov     rsi, r8
0x180124c63  mov     r15, rdx
0x180124c66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180124c6d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180124c72  xor     r13d, r13d
0x180124c75  test    al, al
0x180124c77  jz      loc_18012506B
0x180124c7d  mov     [rsp+0B8h+var_87], r13b
0x180124c82  mov     [rsp+0B8h+var_88], r13b
0x180124c87  lea     rdx, [rsp+0B8h+var_88]; bool *
0x180124c8c  lea     rcx, [rsp+0B8h+var_87]; this
0x180124c91  call    ?IsAikKeyAndCertRequired@Core@Autopilot@ModernDeployment@@YAJAEA_N0@Z; ModernDeployment::Autopilot::Core::IsAikKeyAndCertRequired(bool &,bool &)
0x180124c96  mov     ebx, eax
0x180124c98  test    eax, eax
0x180124c9a  jns     short loc_180124CBF
0x180124c9c  mov     rcx, [rsp+0B8h]; this
0x180124ca4  mov     r9d, eax; char *
0x180124ca7  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x180124cae  mov     edx, 1A2h; void *
0x180124cb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124cb8  mov     eax, ebx
0x180124cba  jmp     loc_180125094
0x180124cbf  mov     r14b, [rsp+0B8h+var_88]
0x180124cc4  cmp     [rsp+0B8h+var_87], r13b
0x180124cc9  jnz     short loc_180124CE1
0x180124ccb  test    r14b, r14b
0x180124cce  jnz     short loc_180124CE1
0x180124cd0  mov     ebx, 1
0x180124cd5  mov     [r15], bl
0x180124cd8  mov     [rsi], bl
0x180124cda  xor     eax, eax
0x180124cdc  jmp     loc_180125094
0x180124ce1  mov     [r15], r13b
0x180124ce4  mov     [rsi], r13b
0x180124ce7  mov     [rsp+0B8h+phProvider], r13
0x180124cec  xor     r8d, r8d; dwFlags
0x180124cef  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180124cf6  lea     rcx, [rsp+0B8h+phProvider]; phProvider
0x180124cfb  call    cs:__imp_NCryptOpenStorageProvider
0x180124d02  nop     dword ptr [rax+rax+00h]
0x180124d07  mov     ebx, eax
0x180124d09  test    eax, eax
0x180124d0b  jns     short loc_180124D3A
0x180124d0d  mov     rcx, [rsp+0B8h]; this
0x180124d15  mov     r9d, eax; char *
0x180124d18  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x180124d1f  mov     edx, 1B1h; void *
0x180124d24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124d29  lea     rcx, [rsp+0B8h+phProvider]
0x180124d2e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180124d33  mov     eax, ebx
0x180124d35  jmp     loc_180125094
0x180124d3a  mov     [rsp+0B8h+pbInput], r13
0x180124d3f  lea     rdx, [rsp+0B8h+pbInput]
0x180124d44  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180124d49  mov     ebx, eax
0x180124d4b  test    eax, eax
0x180124d4d  jns     short loc_180124D86
0x180124d4f  mov     rcx, [rsp+0B8h]; this
0x180124d57  mov     r9d, eax; char *
0x180124d5a  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x180124d61  mov     edx, 1B5h; void *
0x180124d66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124d6b  lea     rcx, [rsp+0B8h+pbInput]
0x180124d70  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180124d75  lea     rcx, [rsp+0B8h+phProvider]
0x180124d7a  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180124d7f  mov     eax, ebx
0x180124d81  jmp     loc_180125094
0x180124d86  mov     r8, [rsp+0B8h+pbInput]; pbInput
0x180124d8b  or      r9, 0FFFFFFFFFFFFFFFFh
0x180124d8f  inc     r9
0x180124d92  cmp     [r8+r9*2], r13w
0x180124d97  jnz     short loc_180124D8F
0x180124d99  add     r9d, r9d; cbInput
0x180124d9c  mov     [rsp+0B8h+dwFlags], r13d; dwFlags
0x180124da1  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x180124da8  mov     rcx, [rsp+0B8h+phProvider]; hObject
0x180124dad  call    cs:__imp_NCryptSetProperty
0x180124db4  nop     dword ptr [rax+rax+00h]
0x180124db9  mov     ebx, eax
0x180124dbb  test    eax, eax
0x180124dbd  jns     short loc_180124DF2
0x180124dbf  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180124dc6  jz      short loc_180124DD7
0x180124dc8  mov     r8d, eax
0x180124dcb  lea     rdx, AutopilotAttestationAikLocationFailed
0x180124dd2  call    McTemplateU0q_EventWriteTransfer
0x180124dd7  lea     rcx, [rsp+0B8h+pbInput]
0x180124ddc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180124de1  lea     rcx, [rsp+0B8h+phProvider]
0x180124de6  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180124deb  mov     eax, ebx
0x180124ded  jmp     loc_180125094
0x180124df2  mov     [rsp+0B8h+ppEnumState], r13
0x180124df7  mov     edi, r13d
0x180124dfa  mov     ebx, 1
0x180124dff  cmp     edi, 14h
0x180124e02  jge     loc_180125032
0x180124e08  mov     [rsp+0B8h+var_40], r13
0x180124e0d  lea     rax, [rsp+0B8h+var_40]
0x180124e12  mov     [rsp+0B8h+var_78], rax
0x180124e17  mov     [rsp+0B8h+ppKeyName], r13
0x180124e1c  mov     [rsp+0B8h+var_68], bl
0x180124e20  mov     [rsp+0B8h+dwFlags], 60h ; '`'; int
0x180124e28  lea     r9, [rsp+0B8h+ppEnumState]; ppEnumState
0x180124e2d  lea     r8, [rsp+0B8h+ppKeyName]; ppKeyName
0x180124e32  xor     edx, edx; pszScope
0x180124e34  mov     rcx, [rsp+0B8h+phProvider]; hProvider
0x180124e39  call    cs:__imp_NCryptEnumKeys
0x180124e40  nop     dword ptr [rax+rax+00h]
0x180124e45  mov     r12d, eax
0x180124e48  lea     rcx, [rsp+0B8h+var_78]
0x180124e4d  call    ??1?$out_param_t@V?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>(void)
0x180124e52  cmp     r12d, 8009002Ah
0x180124e59  jz      loc_180125026
0x180124e5f  test    r12d, r12d
0x180124e62  jnz     loc_18012500A
0x180124e68  lea     rdx, pszKeyName; "Windows AIK"
0x180124e6f  mov     rcx, [rsp+0B8h+var_40]
0x180124e74  mov     rcx, [rcx]
0x180124e77  call    cs:__imp__o__wcsicmp
0x180124e7e  nop     dword ptr [rax+rax+00h]
0x180124e83  xor     edx, edx
0x180124e85  lea     rcx, [rsp+0B8h+var_40]
0x180124e8a  test    eax, eax
0x180124e8c  jz      short loc_180124E9A
0x180124e8e  add     edi, ebx
0x180124e90  call    ?reset@?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@QEAAXPEAUNCryptKeyName@@@Z; wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>::reset(NCryptKeyName *)
0x180124e95  jmp     loc_180124DFF
0x180124e9a  call    ?reset@?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@QEAAXPEAUNCryptKeyName@@@Z; wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>::reset(NCryptKeyName *)
0x180124e9f  mov     [rsp+0B8h+phKey], r13
0x180124ea4  mov     [rsp+0B8h+dwFlags], r13d; dwFlags
0x180124ea9  xor     r9d, r9d; dwLegacyKeySpec
0x180124eac  lea     r8, pszKeyName; "Windows AIK"
0x180124eb3  lea     rdx, [rsp+0B8h+phKey]; phKey
0x180124eb8  mov     rcx, [rsp+0B8h+phProvider]; hProvider
0x180124ebd  call    cs:__imp_NCryptOpenKey
0x180124ec4  nop     dword ptr [rax+rax+00h]
0x180124ec9  mov     edi, eax
0x180124ecb  test    eax, eax
0x180124ecd  jns     short loc_180124F1A
0x180124ecf  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, bl
0x180124ed5  jz      short loc_180124EE6
0x180124ed7  mov     r8d, eax
0x180124eda  lea     rdx, AutopilotAttestationAikKeyOpenFailed
0x180124ee1  call    McTemplateU0q_EventWriteTransfer
0x180124ee6  lea     rcx, [rsp+0B8h+phKey]
0x180124eeb  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180124ef0  lea     rcx, [rsp+0B8h+pbInput]
0x180124ef5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180124efa  lea     rcx, [rsp+0B8h+phProvider]
0x180124eff  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180124f04  cmp     edi, 80090011h
0x180124f0a  jnz     short loc_180124F13
0x180124f0c  xor     eax, eax
0x180124f0e  jmp     loc_180125094
0x180124f13  mov     eax, edi
0x180124f15  jmp     loc_180125094
0x180124f1a  mov     [r15], bl
0x180124f1d  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180124f24  jz      short loc_180124F3F
0x180124f26  lea     rax, [rsp+0B8h+var_40]
0x180124f2b  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x180124f30  mov     r9d, ebx
0x180124f33  lea     rdx, AutopilotAttestationAikKeyFound
0x180124f3a  call    McGenEventWrite_EventWriteTransfer
0x180124f3f  test    r14b, r14b
0x180124f42  jnz     short loc_180124F6B
0x180124f44  mov     [rsi], bl
0x180124f46  lea     rcx, [rsp+0B8h+phKey]
0x180124f4b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180124f50  lea     rcx, [rsp+0B8h+pbInput]
0x180124f55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180124f5a  lea     rcx, [rsp+0B8h+phProvider]
0x180124f5f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180124f64  xor     eax, eax
0x180124f66  jmp     loc_180125094
0x180124f6b  mov     [rsp+0B8h+pcbResult], r13d
0x180124f70  mov     [rsp+0B8h+var_90], r13d; dwFlags
0x180124f75  lea     rax, [rsp+0B8h+pcbResult]
0x180124f7a  mov     qword ptr [rsp+0B8h+dwFlags], rax; pcbResult
0x180124f7f  xor     r9d, r9d; cbOutput
0x180124f82  xor     r8d, r8d; pbOutput
0x180124f85  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180124f8c  mov     rcx, [rsp+0B8h+phKey]; hObject
0x180124f91  call    cs:__imp_NCryptGetProperty
0x180124f98  nop     dword ptr [rax+rax+00h]
0x180124f9d  test    eax, eax
0x180124f9f  js      short loc_180124FCE
0x180124fa1  cmp     [rsp+0B8h+pcbResult], r13d
0x180124fa6  jbe     short loc_180124FCE
0x180124fa8  mov     [rsi], bl
0x180124faa  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180124fb1  jz      short loc_180124FE5
0x180124fb3  lea     rax, [rsp+0B8h+var_40]
0x180124fb8  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x180124fbd  mov     r9d, ebx
0x180124fc0  lea     rdx, AutopilotAttestationAikCertFound
0x180124fc7  call    McGenEventWrite_EventWriteTransfer
0x180124fcc  jmp     short loc_180124FE5
0x180124fce  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, bl
0x180124fd4  jz      short loc_180124FE5
0x180124fd6  mov     r8d, eax
0x180124fd9  lea     rdx, AutopilotAttestationAikCertNotFound
0x180124fe0  call    McTemplateU0q_EventWriteTransfer
0x180124fe5  lea     rcx, [rsp+0B8h+phKey]
0x180124fea  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180124fef  lea     rcx, [rsp+0B8h+pbInput]
0x180124ff4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180124ff9  lea     rcx, [rsp+0B8h+phProvider]
0x180124ffe  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180125003  xor     eax, eax
0x180125005  jmp     loc_180125094
0x18012500a  mov     rcx, [rsp+0B8h]; this
0x180125012  mov     r9d, r12d; char *
0x180125015  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012501c  mov     edx, 1DEh; void *
0x180125021  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180125026  xor     edx, edx
0x180125028  lea     rcx, [rsp+0B8h+var_40]
0x18012502d  call    ?reset@?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@QEAAXPEAUNCryptKeyName@@@Z; wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>::reset(NCryptKeyName *)
0x180125032  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, bl
0x180125038  jz      short loc_180125053
0x18012503a  lea     rax, [rsp+0B8h+var_40]
0x18012503f  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x180125044  mov     r9d, ebx
0x180125047  lea     rdx, AutopilotAttestationAikKeyNotFound
0x18012504e  call    McGenEventWrite_EventWriteTransfer
0x180125053  lea     rcx, [rsp+0B8h+pbInput]
0x180125058  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18012505d  lea     rcx, [rsp+0B8h+phProvider]
0x180125062  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180125067  xor     eax, eax
0x180125069  jmp     short loc_180125094
0x18012506b  mov     rcx, [rsp+0B8h]; this
0x180125073  mov     ebx, 80004001h
0x180125078  mov     r9d, ebx; char *
0x18012507b  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x180125082  mov     edx, 19Eh; void *
0x180125087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012508c  mov     eax, ebx
0x18012508e  jmp     short loc_180125094
0x180125090  mov     eax, [rsp+0B8h+pcbResult]
0x180125094  mov     rcx, [rsp+0B8h+var_30]
0x18012509c  xor     rcx, rsp; StackCookie
0x18012509f  call    __security_check_cookie
0x1801250a4  lea     r11, [rsp+0B8h+var_28]
0x1801250ac  mov     rbx, [r11+30h]
0x1801250b0  mov     rsi, [r11+48h]
0x1801250b4  mov     rsp, r11
0x1801250b7  pop     r15
0x1801250b9  pop     r14
0x1801250bb  pop     r13
0x1801250bd  pop     r12
0x1801250bf  pop     rdi
0x1801250c0  retn
```
