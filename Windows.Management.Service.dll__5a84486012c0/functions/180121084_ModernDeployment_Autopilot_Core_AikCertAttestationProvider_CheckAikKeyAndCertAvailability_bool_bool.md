# ModernDeployment::Autopilot::Core::AikCertAttestationProvider::CheckAikKeyAndCertAvailability(bool &,bool &)

- ea: `0x180121084`
- end: `0x18012150d`
- name: `?CheckAikKeyAndCertAvailability@AikCertAttestationProvider@Core@Autopilot@ModernDeployment@@AEAAJAEA_N0@Z`
- size: `1161`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::AikCertAttestationProvider *__hidden this, bool *, bool *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180120900`
- `0x1801219bc`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x1800730b4`
- `0x1800801fc`
- `0x1800806b0`
- `0x180080708`
- `0x1800cff04`
- `0x180120364`
- `0x180120840`
- `0x1801208a4`
- `0x180121084`
- `0x18012185c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801212b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801212b7`
- `ncrypt!NCryptOpenKey` at `0x18012130a`
- `ncrypt!NCryptOpenKey` at `0x18012130a`
- `ncrypt!NCryptGetProperty` at `0x1801213d9`
- `ncrypt!NCryptGetProperty` at `0x1801213d9`
- `ncrypt!NCryptEnumKeys` at `0x18012127f`
- `ncrypt!NCryptEnumKeys` at `0x18012127f`
- `ncrypt!NCryptSetProperty` at `0x1801211f9`
- `ncrypt!NCryptSetProperty` at `0x1801211f9`
- `ncrypt!NCryptFreeBuffer` at `0x1801212d6`
- `ncrypt!NCryptFreeBuffer` at `0x1801212e6`
- `ncrypt!NCryptFreeBuffer` at `0x180121477`
- `ncrypt!NCryptFreeBuffer` at `0x1801212d6`
- `ncrypt!NCryptFreeBuffer` at `0x1801212e6`
- `ncrypt!NCryptFreeBuffer` at `0x180121477`
- `ncrypt!NCryptOpenStorageProvider` at `0x18012114d`
- `ncrypt!NCryptOpenStorageProvider` at `0x18012114d`

## string_xrefs

- `0x1801210f7`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`
- `0x180121164`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`
- `0x1801211a6`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`
- `0x180121457`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`
- `0x1801214c6`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\aikcertattestationprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::AikCertAttestationProvider::CheckAikKeyAndCertAvailability(
        ModernDeployment::Autopilot::Core::AikCertAttestationProvider *this,
        bool *a2,
        bool *a3)
{
  int IsAikKeyAndCertRequired; // eax
  unsigned int v6; // ebx
  char v8; // r14
  SECURITY_STATUS v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r9
  SECURITY_STATUS v15; // eax
  PVOID v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // ebx
  int i; // edi
  unsigned int v20; // r15d
  int v21; // eax
  SECURITY_STATUS v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned int v25; // edi
  SECURITY_STATUS Property; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  bool v29; // zf
  int dwFlags; // [rsp+20h] [rbp-98h]
  int dwFlagsa; // [rsp+20h] [rbp-98h]
  char v32; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v33[7]; // [rsp+31h] [rbp-87h] BYREF
  PBYTE pbInput; // [rsp+38h] [rbp-80h] BYREF
  PVOID *v35; // [rsp+40h] [rbp-78h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+48h] [rbp-70h] BYREF
  char v37; // [rsp+50h] [rbp-68h]
  PVOID ppEnumState; // [rsp+58h] [rbp-60h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+60h] [rbp-58h] BYREF
  DWORD pcbResult; // [rsp+68h] [rbp-50h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp-48h] BYREF
  PVOID pvInput[2]; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v33[0] = 0;
    v32 = 0;
    IsAikKeyAndCertRequired = ModernDeployment::Autopilot::Core::IsAikKeyAndCertRequired(v33, &v32);
    v6 = IsAikKeyAndCertRequired;
    if ( IsAikKeyAndCertRequired >= 0 )
    {
      v8 = v32;
      if ( v33[0] || v32 )
      {
        *a2 = 0;
        *a3 = 0;
        phProvider = 0;
        v9 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
        v11 = v9;
        if ( v9 >= 0 )
        {
          pbInput = 0;
          v12 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                  v10,
                  &pbInput);
          v13 = v12;
          if ( v12 >= 0 )
          {
            v14 = -1;
            do
              ++v14;
            while ( *(_WORD *)&pbInput[2 * v14] );
            v15 = NCryptSetProperty(phProvider, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", pbInput, 2 * v14, 0);
            v18 = v15;
            if ( v15 >= 0 )
            {
              ppEnumState = 0;
              for ( i = 0; i < 20; ++i )
              {
                pvInput[0] = 0;
                v35 = pvInput;
                ppKeyName = 0;
                v37 = 1;
                v20 = NCryptEnumKeys(phProvider, 0, &ppKeyName, &ppEnumState, 0x60u);
                wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>(&v35);
                if ( v20 == -2146893782 )
                  goto LABEL_44;
                if ( v20 )
                {
                  wil::details::in1diag3::Log_Hr(
                    retaddr,
                    (void *)0x1F9,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
                    (const char *)v20,
                    dwFlagsa);
LABEL_44:
                  v16 = pvInput[0];
                  v29 = pvInput[0] == 0;
                  pvInput[0] = 0;
                  if ( !v29 )
                    NCryptFreeBuffer(v16);
                  break;
                }
                v21 = _o__wcsicmp(*(_QWORD *)pvInput[0], L"Windows AIK");
                v16 = pvInput[0];
                pvInput[0] = 0;
                if ( !v21 )
                {
                  if ( v16 )
                    NCryptFreeBuffer(v16);
                  phKey = 0;
                  v22 = NCryptOpenKey(phProvider, &phKey, L"Windows AIK", 0, 0);
                  v25 = v22;
                  if ( v22 >= 0 )
                  {
                    *a2 = 1;
                    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
                      McGenEventWrite_EventWriteTransfer(v23, AutopilotAttestationAikKeyFound, v24, 1, pvInput);
                    if ( v8 )
                    {
                      pcbResult = 0;
                      Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0);
                      if ( Property >= 0 && pcbResult )
                      {
                        *a3 = 1;
                        if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
                          McGenEventWrite_EventWriteTransfer(v27, AutopilotAttestationAikCertFound, v28, 1, pvInput);
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
                if ( v16 )
                  NCryptFreeBuffer(v16);
              }
              if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
                McGenEventWrite_EventWriteTransfer(v16, AutopilotAttestationAikKeyNotFound, v17, 1, pvInput);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
              return 0;
            }
            else
            {
              if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
                McTemplateU0q_EventWriteTransfer(v16, AutopilotAttestationAikLocationFailed, (unsigned int)v15);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
              return v18;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D0,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
              (const char *)(unsigned int)v12,
              dwFlags);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
            return v13;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CC,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
            (const char *)(unsigned int)v9,
            dwFlags);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
          return v11;
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
        (void *)0x1BD,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
        (const char *)(unsigned int)IsAikKeyAndCertRequired,
        dwFlags);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\aikcertattestationprovider.cpp",
      (const char *)0x80004001LL,
      dwFlags);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180121084  mov     [rsp+arg_0], rbx
0x180121089  mov     [rsp+arg_18], rsi
0x18012108e  push    rdi
0x18012108f  push    r12
0x180121091  push    r13
0x180121093  push    r14
0x180121095  push    r15
0x180121097  sub     rsp, 90h
0x18012109e  mov     rax, cs:__security_cookie
0x1801210a5  xor     rax, rsp
0x1801210a8  mov     [rsp+0B8h+var_30], rax
0x1801210b0  mov     rsi, r8
0x1801210b3  mov     r12, rdx
0x1801210b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801210bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801210c2  xor     r13d, r13d
0x1801210c5  test    al, al
0x1801210c7  jz      loc_1801214B6
0x1801210cd  mov     [rsp+0B8h+var_87], r13b
0x1801210d2  mov     [rsp+0B8h+var_88], r13b
0x1801210d7  lea     rdx, [rsp+0B8h+var_88]
0x1801210dc  lea     rcx, [rsp+0B8h+var_87]
0x1801210e1  call    ModernDeployment__Autopilot__Core__IsAikKeyAndCertRequired
0x1801210e6  mov     ebx, eax
0x1801210e8  test    eax, eax
0x1801210ea  jns     short loc_18012110F
0x1801210ec  mov     rcx, [rsp+0B8h]; this
0x1801210f4  mov     r9d, eax; char *
0x1801210f7  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801210fe  mov     edx, 1BDh; void *
0x180121103  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121108  mov     eax, ebx
0x18012110a  jmp     loc_1801214DF
0x18012110f  mov     r14b, [rsp+0B8h+var_88]
0x180121114  cmp     [rsp+0B8h+var_87], r13b
0x180121119  jnz     short loc_180121132
0x18012111b  test    r14b, r14b
0x18012111e  jnz     short loc_180121132
0x180121120  mov     ebx, 1
0x180121125  mov     [r12], bl
0x180121129  mov     [rsi], bl
0x18012112b  xor     eax, eax
0x18012112d  jmp     loc_1801214DF
0x180121132  mov     [r12], r13b
0x180121136  mov     [rsi], r13b
0x180121139  mov     [rsp+0B8h+phProvider], r13
0x18012113e  xor     r8d, r8d; dwFlags
0x180121141  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180121148  lea     rcx, [rsp+0B8h+phProvider]; phProvider
0x18012114d  call    cs:__imp_NCryptOpenStorageProvider
0x180121153  mov     ebx, eax
0x180121155  test    eax, eax
0x180121157  jns     short loc_180121186
0x180121159  mov     rcx, [rsp+0B8h]; this
0x180121161  mov     r9d, eax; char *
0x180121164  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012116b  mov     edx, 1CCh; void *
0x180121170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121175  lea     rcx, [rsp+0B8h+phProvider]
0x18012117a  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18012117f  mov     eax, ebx
0x180121181  jmp     loc_1801214DF
0x180121186  mov     [rsp+0B8h+pbInput], r13
0x18012118b  lea     rdx, [rsp+0B8h+pbInput]
0x180121190  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180121195  mov     ebx, eax
0x180121197  test    eax, eax
0x180121199  jns     short loc_1801211D2
0x18012119b  mov     rcx, [rsp+0B8h]; this
0x1801211a3  mov     r9d, eax; char *
0x1801211a6  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801211ad  mov     edx, 1D0h; void *
0x1801211b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801211b7  lea     rcx, [rsp+0B8h+pbInput]
0x1801211bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801211c1  lea     rcx, [rsp+0B8h+phProvider]
0x1801211c6  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1801211cb  mov     eax, ebx
0x1801211cd  jmp     loc_1801214DF
0x1801211d2  mov     r8, [rsp+0B8h+pbInput]; pbInput
0x1801211d7  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801211db  inc     r9
0x1801211de  cmp     [r8+r9*2], r13w
0x1801211e3  jnz     short loc_1801211DB
0x1801211e5  add     r9d, r9d; cbInput
0x1801211e8  mov     [rsp+0B8h+dwFlags], r13d; dwFlags
0x1801211ed  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x1801211f4  mov     rcx, [rsp+0B8h+phProvider]; hObject
0x1801211f9  call    cs:__imp_NCryptSetProperty
0x1801211ff  mov     ebx, eax
0x180121201  test    eax, eax
0x180121203  jns     short loc_180121238
0x180121205  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18012120c  jz      short loc_18012121D
0x18012120e  mov     r8d, eax
0x180121211  lea     rdx, AutopilotAttestationAikLocationFailed
0x180121218  call    McTemplateU0q_EventWriteTransfer
0x18012121d  lea     rcx, [rsp+0B8h+pbInput]
0x180121222  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180121227  lea     rcx, [rsp+0B8h+phProvider]
0x18012122c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180121231  mov     eax, ebx
0x180121233  jmp     loc_1801214DF
0x180121238  mov     [rsp+0B8h+ppEnumState], r13
0x18012123d  mov     edi, r13d
0x180121240  mov     ebx, 1
0x180121245  cmp     edi, 14h
0x180121248  jge     loc_18012147D
0x18012124e  mov     [rsp+0B8h+pvInput], r13
0x180121253  lea     rax, [rsp+0B8h+pvInput]
0x180121258  mov     [rsp+0B8h+var_78], rax
0x18012125d  mov     [rsp+0B8h+ppKeyName], r13
0x180121262  mov     [rsp+0B8h+var_68], bl
0x180121266  mov     [rsp+0B8h+dwFlags], 60h ; '`'; int
0x18012126e  lea     r9, [rsp+0B8h+ppEnumState]; ppEnumState
0x180121273  lea     r8, [rsp+0B8h+ppKeyName]; ppKeyName
0x180121278  xor     edx, edx; pszScope
0x18012127a  mov     rcx, [rsp+0B8h+phProvider]; hProvider
0x18012127f  call    cs:__imp_NCryptEnumKeys
0x180121285  mov     r15d, eax
0x180121288  lea     rcx, [rsp+0B8h+var_78]
0x18012128d  call    ??1?$out_param_t@V?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>(void)
0x180121292  cmp     r15d, 8009002Ah
0x180121299  jz      loc_180121468
0x18012129f  test    r15d, r15d
0x1801212a2  jnz     loc_18012144C
0x1801212a8  lea     rdx, pszKeyName; "Windows AIK"
0x1801212af  mov     rcx, [rsp+0B8h+pvInput]
0x1801212b4  mov     rcx, [rcx]
0x1801212b7  call    cs:__imp__o__wcsicmp
0x1801212bd  mov     rcx, [rsp+0B8h+pvInput]; pvInput
0x1801212c2  mov     [rsp+0B8h+pvInput], r13
0x1801212c7  test    eax, eax
0x1801212c9  jz      short loc_1801212E1
0x1801212cb  add     edi, ebx
0x1801212cd  test    rcx, rcx
0x1801212d0  jz      loc_180121245
0x1801212d6  call    cs:__imp_NCryptFreeBuffer
0x1801212dc  jmp     loc_180121245
0x1801212e1  test    rcx, rcx
0x1801212e4  jz      short loc_1801212EC
0x1801212e6  call    cs:__imp_NCryptFreeBuffer
0x1801212ec  mov     [rsp+0B8h+phKey], r13
0x1801212f1  mov     [rsp+0B8h+dwFlags], r13d; dwFlags
0x1801212f6  xor     r9d, r9d; dwLegacyKeySpec
0x1801212f9  lea     r8, pszKeyName; "Windows AIK"
0x180121300  lea     rdx, [rsp+0B8h+phKey]; phKey
0x180121305  mov     rcx, [rsp+0B8h+phProvider]; hProvider
0x18012130a  call    cs:__imp_NCryptOpenKey
0x180121310  mov     edi, eax
0x180121312  test    eax, eax
0x180121314  jns     short loc_180121361
0x180121316  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, bl
0x18012131c  jz      short loc_18012132D
0x18012131e  mov     r8d, eax
0x180121321  lea     rdx, AutopilotAttestationAikKeyOpenFailed
0x180121328  call    McTemplateU0q_EventWriteTransfer
0x18012132d  lea     rcx, [rsp+0B8h+phKey]
0x180121332  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180121337  lea     rcx, [rsp+0B8h+pbInput]
0x18012133c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180121341  lea     rcx, [rsp+0B8h+phProvider]
0x180121346  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18012134b  cmp     edi, 80090011h
0x180121351  jnz     short loc_18012135A
0x180121353  xor     eax, eax
0x180121355  jmp     loc_1801214DF
0x18012135a  mov     eax, edi
0x18012135c  jmp     loc_1801214DF
0x180121361  mov     [r12], bl
0x180121365  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18012136c  jz      short loc_180121387
0x18012136e  lea     rax, [rsp+0B8h+pvInput]
0x180121373  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x180121378  mov     r9d, ebx
0x18012137b  lea     rdx, AutopilotAttestationAikKeyFound
0x180121382  call    McGenEventWrite_EventWriteTransfer
0x180121387  test    r14b, r14b
0x18012138a  jnz     short loc_1801213B3
0x18012138c  mov     [rsi], bl
0x18012138e  lea     rcx, [rsp+0B8h+phKey]
0x180121393  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180121398  lea     rcx, [rsp+0B8h+pbInput]
0x18012139d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801213a2  lea     rcx, [rsp+0B8h+phProvider]
0x1801213a7  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1801213ac  xor     eax, eax
0x1801213ae  jmp     loc_1801214DF
0x1801213b3  mov     [rsp+0B8h+pcbResult], r13d
0x1801213b8  mov     [rsp+0B8h+var_90], r13d; dwFlags
0x1801213bd  lea     rax, [rsp+0B8h+pcbResult]
0x1801213c2  mov     qword ptr [rsp+0B8h+dwFlags], rax; pcbResult
0x1801213c7  xor     r9d, r9d; cbOutput
0x1801213ca  xor     r8d, r8d; pbOutput
0x1801213cd  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x1801213d4  mov     rcx, [rsp+0B8h+phKey]; hObject
0x1801213d9  call    cs:__imp_NCryptGetProperty
0x1801213df  test    eax, eax
0x1801213e1  js      short loc_180121410
0x1801213e3  cmp     [rsp+0B8h+pcbResult], r13d
0x1801213e8  jbe     short loc_180121410
0x1801213ea  mov     [rsi], bl
0x1801213ec  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1801213f3  jz      short loc_180121427
0x1801213f5  lea     rax, [rsp+0B8h+pvInput]
0x1801213fa  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x1801213ff  mov     r9d, ebx
0x180121402  lea     rdx, AutopilotAttestationAikCertFound
0x180121409  call    McGenEventWrite_EventWriteTransfer
0x18012140e  jmp     short loc_180121427
0x180121410  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, bl
0x180121416  jz      short loc_180121427
0x180121418  mov     r8d, eax
0x18012141b  lea     rdx, AutopilotAttestationAikCertNotFound
0x180121422  call    McTemplateU0q_EventWriteTransfer
0x180121427  lea     rcx, [rsp+0B8h+phKey]
0x18012142c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180121431  lea     rcx, [rsp+0B8h+pbInput]
0x180121436  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18012143b  lea     rcx, [rsp+0B8h+phProvider]
0x180121440  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180121445  xor     eax, eax
0x180121447  jmp     loc_1801214DF
0x18012144c  mov     rcx, [rsp+0B8h]; this
0x180121454  mov     r9d, r15d; char *
0x180121457  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012145e  mov     edx, 1F9h; void *
0x180121463  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180121468  mov     rcx, [rsp+0B8h+pvInput]; pvInput
0x18012146d  test    rcx, rcx
0x180121470  mov     [rsp+0B8h+pvInput], r13
0x180121475  jz      short loc_18012147D
0x180121477  call    cs:__imp_NCryptFreeBuffer
0x18012147d  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, bl
0x180121483  jz      short loc_18012149E
0x180121485  lea     rax, [rsp+0B8h+pvInput]
0x18012148a  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x18012148f  mov     r9d, ebx
0x180121492  lea     rdx, AutopilotAttestationAikKeyNotFound
0x180121499  call    McGenEventWrite_EventWriteTransfer
0x18012149e  lea     rcx, [rsp+0B8h+pbInput]
0x1801214a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801214a8  lea     rcx, [rsp+0B8h+phProvider]
0x1801214ad  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1801214b2  xor     eax, eax
0x1801214b4  jmp     short loc_1801214DF
0x1801214b6  mov     rcx, [rsp+0B8h]; this
0x1801214be  mov     ebx, 80004001h
0x1801214c3  mov     r9d, ebx; char *
0x1801214c6  lea     r8, aOnecoreuapAdmi_52; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801214cd  mov     edx, 1B9h; void *
0x1801214d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801214d7  mov     eax, ebx
0x1801214d9  jmp     short loc_1801214DF
0x1801214db  mov     eax, [rsp+0B8h+pcbResult]
0x1801214df  mov     rcx, [rsp+0B8h+var_30]
0x1801214e7  xor     rcx, rsp; StackCookie
0x1801214ea  call    __security_check_cookie
0x1801214ef  lea     r11, [rsp+0B8h+var_28]
0x1801214f7  mov     rbx, [r11+30h]
0x1801214fb  mov     rsi, [r11+48h]
0x1801214ff  mov     rsp, r11
0x180121502  pop     r15
0x180121504  pop     r14
0x180121506  pop     r13
0x180121508  pop     r12
0x18012150a  pop     rdi
0x18012150b  retn
```
