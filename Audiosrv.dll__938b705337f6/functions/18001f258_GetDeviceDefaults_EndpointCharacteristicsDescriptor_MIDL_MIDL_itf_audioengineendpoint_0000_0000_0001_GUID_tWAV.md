# GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)

- ea: `0x18001f258`
- end: `0x18001f6aa`
- name: `?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z`
- size: `1106`
- prototype: `int(struct EndpointCharacteristicsDescriptor *, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct _GUID *__struct_ptr, struct tWAVEFORMATEX **, struct tWAVEFORMATEX **, __int64 *, __int64 *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001df60`
- `0x18001eb4c`
- `0x18001fa40`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x18001e850`
- `0x18001f258`
- `0x18001f6b0`
- `0x180020bdc`
- `0x180038a04`
- `0x180038e30`
- `0x18003cee0`
- `0x1800543d8`
- `0x1800551cc`
- `0x1800621b0`
- `0x1800b75a4`
- `0x1800d0740`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f3b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f42b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f464`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f67a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f691`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f3b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f42b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f464`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f67a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f691`

## string_xrefs

- `0x18001f2c3`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f37e`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f43d`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f4fb`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f5dd`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f659`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetDeviceDefaults(
        EffectPack **a1,
        __int64 a2,
        struct _GUID *a3,
        struct tWAVEFORMATEX **a4,
        struct tWAVEFORMATEX **pv,
        __int64 *a6,
        __int64 *a7)
{
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v9; // r12d
  struct tWAVEFORMATEX **v11; // rbx
  __int64 *v12; // r8
  EffectPack **v13; // rdi
  int ProcessingPeriod; // eax
  unsigned int ConnectorFormatForProcessingMode; // r15d
  const struct tWAVEFORMATEX *v17; // rax
  int v18; // eax
  unsigned int v19; // edi
  struct tWAVEFORMATEX **v20; // rcx
  void *v21; // rcx
  struct tWAVEFORMATEX **v22; // rcx
  struct tWAVEFORMATEX *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  int DevicePipeFormat; // eax
  int MixFormat; // ebx
  __int64 v28; // rdx
  const struct tWAVEFORMATEX *v29; // rax
  int v30; // eax
  unsigned int v31; // esi
  struct tWAVEFORMATEX **v32; // rcx
  struct tWAVEFORMATEX **v33; // rcx
  struct tWAVEFORMATEX **v34; // rcx
  __int64 **v35; // [rsp+20h] [rbp-48h]
  struct _GUID v36; // [rsp+30h] [rbp-38h] BYREF
  void **p_pv; // [rsp+40h] [rbp-28h]
  struct tWAVEFORMATEX *v38; // [rsp+48h] [rbp-20h] BYREF
  char v39; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  void *v41; // [rsp+C8h] [rbp+60h] BYREF

  v9 = (int)a2;
  if ( a4 )
    *a4 = 0;
  v11 = pv;
  if ( pv )
    *pv = 0;
  v12 = a6;
  if ( a7 || a6 )
  {
    v13 = a1 + 1;
    ProcessingPeriod = EffectPack::GetProcessingPeriod(a1[1], 0, a6, a7);
    ConnectorFormatForProcessingMode = ProcessingPeriod;
    if ( ProcessingPeriod < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCA0,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
        (const char *)(unsigned int)ProcessingPeriod,
        (int)v35);
      return ConnectorFormatForProcessingMode;
    }
  }
  else
  {
    v13 = a1 + 1;
  }
  pv = 0;
  if ( a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::__private_IsEnabled(
                            &`wil::Feature<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::GetImpl'::`2'::impl,
                            a2,
                            v12) )
    {
      v41 = 0;
      CEndpointCharacteristics::TryGetCustomResourceManagerService(
        *a1,
        &GUID_655e6959_84d5_43a4_b383_39d8f3094d70,
        &v41);
      if ( v41 )
      {
        a7 = 0;
        v36 = *a3;
        v35 = &a7;
        (*(void (__fastcall **)(void *, EffectPack **, _QWORD, struct _GUID *))(*(_QWORD *)v41 + 48LL))(
          v41,
          a1,
          (unsigned int)v9,
          &v36);
        if ( a7 )
        {
          v17 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(__int64 *))(*a7 + 40))(a7);
          v18 = CloneWaveFormat(v17, a4);
          v19 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCB4,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
              (const char *)(unsigned int)v18,
              (int)&a7);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&a7);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
LABEL_17:
            v20 = pv;
            pv = 0;
            if ( v20 )
              CoTaskMemFree(v20);
            return v19;
          }
        }
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&a7);
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
      v13 = a1 + 1;
    }
    if ( !*a4 )
    {
      v13 = a1 + 1;
      p_pv = (void **)&pv;
      v38 = 0;
      v39 = 1;
      v36 = *a3;
      ConnectorFormatForProcessingMode = EffectPack::GetConnectorFormatForProcessingMode(a1[1], v9, &v36, &v38);
      if ( v39 )
      {
        v21 = *p_pv;
        *p_pv = v38;
        if ( v21 )
          CoTaskMemFree(v21);
      }
      if ( (ConnectorFormatForProcessingMode & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCBB,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
          (const char *)ConnectorFormatForProcessingMode,
          (int)v35);
        v22 = pv;
        pv = 0;
        if ( v22 )
          CoTaskMemFree(v22);
        return ConnectorFormatForProcessingMode;
      }
      v23 = (struct tWAVEFORMATEX *)pv;
      pv = 0;
      *a4 = v23;
    }
  }
  if ( !v11 )
  {
LABEL_54:
    v34 = pv;
    pv = 0;
    if ( v34 )
      CoTaskMemFree(v34);
    return 0;
  }
  v36 = *a3;
  if ( !EffectPack::CanProcessingModeBeParameterized(*v13, &v36, v9)
    && (memcmp_0(a3, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u)
     || !(unsigned int)EffectPack::CanBuildProcessingModesOnRawConnector(*v13, (unsigned int)v9, 0)) )
  {
    v36 = *a3;
    DevicePipeFormat = CEndpointCharacteristics::TryGetDevicePipeFormat(*a1, v9, &v36, v11);
    v19 = DevicePipeFormat;
    if ( DevicePipeFormat < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCE1,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
        (const char *)(unsigned int)DevicePipeFormat,
        (int)v35);
      goto LABEL_17;
    }
    if ( !*v11 )
    {
      v36 = *a3;
      MixFormat = EffectPack::GetMixFormat(a1[1], v9, &v36, v11);
      if ( MixFormat < 0 )
      {
        v28 = 3304;
LABEL_51:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v28,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
          (const char *)(unsigned int)MixFormat,
          (int)v35);
        v33 = pv;
        pv = 0;
        if ( v33 )
          CoTaskMemFree(v33);
        return (unsigned int)MixFormat;
      }
    }
    goto LABEL_54;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::__private_IsEnabled(
                           &`wil::Feature<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::GetImpl'::`2'::impl,
                           v24,
                           v25) )
  {
LABEL_48:
    if ( !*v11 )
    {
      v36 = *a3;
      MixFormat = EffectPack::GetDevicePipeFormat(*v13, v9, &v36, v11);
      if ( MixFormat < 0 )
      {
        v28 = 3291;
        goto LABEL_51;
      }
    }
    goto LABEL_54;
  }
  v41 = 0;
  CEndpointCharacteristics::TryGetCustomResourceManagerService(*a1, &GUID_655e6959_84d5_43a4_b383_39d8f3094d70, &v41);
  if ( !v41 )
  {
LABEL_47:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
    goto LABEL_48;
  }
  a7 = 0;
  v36 = *a3;
  v35 = &a7;
  (*(void (__fastcall **)(void *, EffectPack **, _QWORD, struct _GUID *))(*(_QWORD *)v41 + 40LL))(
    v41,
    a1,
    (unsigned int)v9,
    &v36);
  if ( !a7
    || (v29 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(__int64 *))(*a7 + 40))(a7),
        v30 = CloneWaveFormat(v29, v11),
        v31 = v30,
        v30 >= 0) )
  {
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&a7);
    goto LABEL_47;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCD1,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
    (const char *)(unsigned int)v30,
    (int)&a7);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&a7);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
  v32 = pv;
  pv = 0;
  if ( v32 )
    CoTaskMemFree(v32);
  return v31;
}

```

## disassembly

```asm
0x18001f258  push    rbp
0x18001f25a  push    rbx
0x18001f25b  push    rsi
0x18001f25c  push    rdi
0x18001f25d  push    r12
0x18001f25f  push    r13
0x18001f261  push    r14
0x18001f263  push    r15
0x18001f265  mov     rbp, rsp
0x18001f268  sub     rsp, 68h
0x18001f26c  mov     r14, r9
0x18001f26f  mov     r13, r8
0x18001f272  mov     r12d, edx
0x18001f275  mov     rsi, rcx
0x18001f278  xor     r15d, r15d
0x18001f27b  test    r9, r9
0x18001f27e  jz      short loc_18001F283
0x18001f280  mov     [r9], r15
0x18001f283  mov     rbx, [rbp+pv]
0x18001f287  test    rbx, rbx
0x18001f28a  jz      short loc_18001F28F
0x18001f28c  mov     [rbx], r15
0x18001f28f  mov     r8, [rbp+arg_28]; __int64 *
0x18001f293  mov     r9, [rbp+arg_30]; __int64 *
0x18001f297  test    r9, r9
0x18001f29a  jnz     short loc_18001F2A7
0x18001f29c  test    r8, r8
0x18001f29f  jnz     short loc_18001F2A7
0x18001f2a1  lea     rdi, [rcx+8]
0x18001f2a5  jmp     short loc_18001F2DF
0x18001f2a7  lea     rdi, [rcx+8]
0x18001f2ab  xor     edx, edx; int
0x18001f2ad  mov     rcx, [rdi]; this
0x18001f2b0  call    ?GetProcessingPeriod@EffectPack@@QEAAJHPEA_J0@Z; EffectPack::GetProcessingPeriod(int,__int64 *,__int64 *)
0x18001f2b5  mov     r15d, eax
0x18001f2b8  test    eax, eax
0x18001f2ba  jns     short loc_18001F2DC
0x18001f2bc  mov     rcx, [rbp+40h]; this
0x18001f2c0  mov     r9d, eax; char *
0x18001f2c3  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f2ca  mov     edx, 0CA0h; void *
0x18001f2cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f2d4  mov     eax, r15d
0x18001f2d7  jmp     loc_18001F699
0x18001f2dc  xor     r15d, r15d
0x18001f2df  mov     [rbp+pv], r15
0x18001f2e3  test    r14, r14
0x18001f2e6  jz      loc_18001F47D
0x18001f2ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch> `wil::Feature<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::GetImpl(void)'::`2'::impl
0x18001f2f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::__private_IsEnabled(void)
0x18001f2f8  test    al, al
0x18001f2fa  jz      loc_18001F3D5
0x18001f300  mov     [rbp+arg_18], r15
0x18001f304  lea     r8, [rbp+arg_18]; void **
0x18001f308  lea     rdx, _GUID_655e6959_84d5_43a4_b383_39d8f3094d70; struct _GUID *
0x18001f30f  mov     rcx, [rsi]; this
0x18001f312  call    ?TryGetCustomResourceManagerService@CEndpointCharacteristics@@QEAAJAEBU_GUID@@PEAPEAX@Z; CEndpointCharacteristics::TryGetCustomResourceManagerService(_GUID const &,void * *)
0x18001f317  mov     rcx, [rbp+arg_18]
0x18001f31b  test    rcx, rcx
0x18001f31e  jz      loc_18001F3C8
0x18001f324  mov     [rbp+arg_30], r15
0x18001f328  movaps  xmm0, xmmword ptr [r13+0]
0x18001f32d  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f332  mov     rax, [rcx]
0x18001f335  lea     rdx, [rbp+arg_30]
0x18001f339  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001f33e  lea     r9, [rbp+var_38]
0x18001f342  mov     r8d, r12d
0x18001f345  mov     rdx, rsi
0x18001f348  mov     rax, [rax+30h]
0x18001f34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f351  mov     rcx, [rbp+arg_30]
0x18001f355  test    rcx, rcx
0x18001f358  jz      short loc_18001F3BE
0x18001f35a  mov     rax, [rcx]
0x18001f35d  mov     rax, [rax+28h]
0x18001f361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f366  mov     rcx, rax; Src
0x18001f369  mov     rdx, r14; struct tWAVEFORMATEX **
0x18001f36c  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001f371  mov     edi, eax
0x18001f373  test    eax, eax
0x18001f375  jns     short loc_18001F3BE
0x18001f377  mov     rcx, [rbp+40h]; this
0x18001f37b  mov     r9d, eax; char *
0x18001f37e  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f385  mov     edx, 0CB4h; void *
0x18001f38a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f38f  nop
0x18001f390  lea     rcx, [rbp+arg_30]
0x18001f394  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f399  nop
0x18001f39a  lea     rcx, [rbp+arg_18]
0x18001f39e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f3a3  nop
0x18001f3a4  mov     rcx, [rbp+pv]; pv
0x18001f3a8  mov     [rbp+pv], r15
0x18001f3ac  test    rcx, rcx
0x18001f3af  jz      short loc_18001F3B7
0x18001f3b1  call    cs:__imp_CoTaskMemFree
0x18001f3b7  mov     eax, edi
0x18001f3b9  jmp     loc_18001F699
0x18001f3be  lea     rcx, [rbp+arg_30]
0x18001f3c2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f3c7  nop
0x18001f3c8  lea     rcx, [rbp+arg_18]
0x18001f3cc  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f3d1  lea     rdi, [rsi+8]
0x18001f3d5  cmp     [r14], r15
0x18001f3d8  jnz     loc_18001F47D
0x18001f3de  lea     rdi, [rsi+8]
0x18001f3e2  lea     rax, [rbp+pv]
0x18001f3e6  mov     [rbp+var_28], rax
0x18001f3ea  mov     [rbp+var_20], r15
0x18001f3ee  mov     [rbp+var_18], 1
0x18001f3f2  movaps  xmm0, xmmword ptr [r13+0]
0x18001f3f7  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f3fc  lea     r9, [rbp+var_20]; struct tWAVEFORMATEX **
0x18001f400  lea     r8, [rbp+var_38]; struct _GUID
0x18001f404  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f407  mov     rcx, [rdi]; this
0x18001f40a  call    ?GetConnectorFormatForProcessingMode@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetConnectorFormatForProcessingMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001f40f  mov     r15d, eax
0x18001f412  cmp     [rbp+var_18], 0
0x18001f416  jz      short loc_18001F431
0x18001f418  mov     r8, [rbp+var_28]
0x18001f41c  mov     rcx, [r8]; pv
0x18001f41f  mov     rdx, [rbp+var_20]
0x18001f423  mov     [r8], rdx
0x18001f426  test    rcx, rcx
0x18001f429  jz      short loc_18001F431
0x18001f42b  call    cs:__imp_CoTaskMemFree
0x18001f431  test    r15d, r15d
0x18001f434  jns     short loc_18001F46F
0x18001f436  mov     rcx, [rbp+40h]; this
0x18001f43a  mov     r9d, r15d; char *
0x18001f43d  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f444  mov     edx, 0CBBh; void *
0x18001f449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f44e  nop
0x18001f44f  mov     rcx, [rbp+pv]; pv
0x18001f453  mov     [rbp+pv], 0
0x18001f45b  test    rcx, rcx
0x18001f45e  jz      loc_18001F2D4
0x18001f464  call    cs:__imp_CoTaskMemFree
0x18001f46a  jmp     loc_18001F2D4
0x18001f46f  mov     rax, [rbp+pv]
0x18001f473  xor     r15d, r15d
0x18001f476  mov     [rbp+pv], r15
0x18001f47a  mov     [r14], rax
0x18001f47d  test    rbx, rbx
0x18001f480  jz      loc_18001F684
0x18001f486  movaps  xmm0, xmmword ptr [r13+0]
0x18001f48b  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f490  mov     r8d, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f493  lea     rdx, [rbp+var_38]; struct _GUID
0x18001f497  mov     rcx, [rdi]; this
0x18001f49a  call    ?CanProcessingModeBeParameterized@EffectPack@@QEAA_NU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::CanProcessingModeBeParameterized(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18001f49f  test    al, al
0x18001f4a1  jnz     loc_18001F54B
0x18001f4a7  mov     r8d, 10h; Size
0x18001f4ad  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x18001f4b4  mov     rcx, r13; Buf1
0x18001f4b7  call    memcmp_0
0x18001f4bc  test    eax, eax
0x18001f4be  jnz     short loc_18001F4D2
0x18001f4c0  xor     r8d, r8d
0x18001f4c3  mov     edx, r12d
0x18001f4c6  mov     rcx, [rdi]
0x18001f4c9  call    ?CanBuildProcessingModesOnRawConnector@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@@Z; EffectPack::CanBuildProcessingModesOnRawConnector(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration)
0x18001f4ce  test    eax, eax
0x18001f4d0  jnz     short loc_18001F54B
0x18001f4d2  movaps  xmm0, xmmword ptr [r13+0]
0x18001f4d7  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f4dc  mov     r9, rbx; struct tWAVEFORMATEX **
0x18001f4df  lea     r8, [rbp+var_38]; struct _GUID
0x18001f4e3  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f4e6  mov     rcx, [rsi]; this
0x18001f4e9  call    ?TryGetDevicePipeFormat@CEndpointCharacteristics@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::TryGetDevicePipeFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001f4ee  mov     edi, eax
0x18001f4f0  test    eax, eax
0x18001f4f2  jns     short loc_18001F511
0x18001f4f4  mov     rcx, [rbp+40h]; this
0x18001f4f8  mov     r9d, eax; char *
0x18001f4fb  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f502  mov     edx, 0CE1h; void *
0x18001f507  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f50c  jmp     loc_18001F3A4
0x18001f511  cmp     [rbx], r15
0x18001f514  jnz     loc_18001F684
0x18001f51a  movaps  xmm0, xmmword ptr [r13+0]
0x18001f51f  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f524  mov     r9, rbx; struct tWAVEFORMATEX **
0x18001f527  lea     r8, [rbp+var_38]; struct _GUID
0x18001f52b  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f52e  mov     rcx, [rsi+8]; this
0x18001f532  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001f537  mov     ebx, eax
0x18001f539  test    eax, eax
0x18001f53b  jns     loc_18001F684
0x18001f541  mov     edx, 0CE8h
0x18001f546  jmp     loc_18001F659
0x18001f54b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch> `wil::Feature<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::GetImpl(void)'::`2'::impl
0x18001f552  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::__private_IsEnabled(void)
0x18001f557  test    al, al
0x18001f559  jz      loc_18001F62D
0x18001f55f  mov     [rbp+arg_18], r15
0x18001f563  lea     r8, [rbp+arg_18]; void **
0x18001f567  lea     rdx, _GUID_655e6959_84d5_43a4_b383_39d8f3094d70; struct _GUID *
0x18001f56e  mov     rcx, [rsi]; this
0x18001f571  call    ?TryGetCustomResourceManagerService@CEndpointCharacteristics@@QEAAJAEBU_GUID@@PEAPEAX@Z; CEndpointCharacteristics::TryGetCustomResourceManagerService(_GUID const &,void * *)
0x18001f576  mov     rcx, [rbp+arg_18]
0x18001f57a  test    rcx, rcx
0x18001f57d  jz      loc_18001F624
0x18001f583  mov     [rbp+arg_30], r15
0x18001f587  movaps  xmm0, xmmword ptr [r13+0]
0x18001f58c  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f591  mov     rax, [rcx]
0x18001f594  lea     rdx, [rbp+arg_30]
0x18001f598  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001f59d  lea     r9, [rbp+var_38]
0x18001f5a1  mov     r8d, r12d
0x18001f5a4  mov     rdx, rsi
0x18001f5a7  mov     rax, [rax+28h]
0x18001f5ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5b0  mov     rcx, [rbp+arg_30]
0x18001f5b4  test    rcx, rcx
0x18001f5b7  jz      short loc_18001F61A
0x18001f5b9  mov     rax, [rcx]
0x18001f5bc  mov     rax, [rax+28h]
0x18001f5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5c5  mov     rcx, rax; Src
0x18001f5c8  mov     rdx, rbx; struct tWAVEFORMATEX **
0x18001f5cb  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001f5d0  mov     esi, eax
0x18001f5d2  test    eax, eax
0x18001f5d4  jns     short loc_18001F61A
0x18001f5d6  mov     rcx, [rbp+40h]; this
0x18001f5da  mov     r9d, eax; char *
0x18001f5dd  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f5e4  mov     edx, 0CD1h; void *
0x18001f5e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f5ee  nop
0x18001f5ef  lea     rcx, [rbp+arg_30]
0x18001f5f3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f5f8  nop
0x18001f5f9  lea     rcx, [rbp+arg_18]
0x18001f5fd  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f602  nop
0x18001f603  mov     rcx, [rbp+pv]; pv
0x18001f607  mov     [rbp+pv], r15
0x18001f60b  test    rcx, rcx
0x18001f60e  jz      short loc_18001F616
0x18001f610  call    cs:__imp_CoTaskMemFree
0x18001f616  mov     eax, esi
0x18001f618  jmp     short loc_18001F699
0x18001f61a  lea     rcx, [rbp+arg_30]
0x18001f61e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f623  nop
0x18001f624  lea     rcx, [rbp+arg_18]
0x18001f628  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f62d  cmp     [rbx], r15
0x18001f630  jnz     short loc_18001F684
0x18001f632  movaps  xmm0, xmmword ptr [r13+0]
0x18001f637  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f63c  mov     r9, rbx; struct tWAVEFORMATEX **
0x18001f63f  lea     r8, [rbp+var_38]; struct _GUID
0x18001f643  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f646  mov     rcx, [rdi]; this
0x18001f649  call    ?GetDevicePipeFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetDevicePipeFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001f64e  mov     ebx, eax
0x18001f650  test    eax, eax
0x18001f652  jns     short loc_18001F684
0x18001f654  mov     edx, 0CDBh; void *
0x18001f659  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f660  mov     r9d, ebx; char *
0x18001f663  mov     rcx, [rbp+40h]; this
0x18001f667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f66c  nop
0x18001f66d  mov     rcx, [rbp+pv]; pv
0x18001f671  mov     [rbp+pv], r15
0x18001f675  test    rcx, rcx
0x18001f678  jz      short loc_18001F680
0x18001f67a  call    cs:__imp_CoTaskMemFree
0x18001f680  mov     eax, ebx
0x18001f682  jmp     short loc_18001F699
0x18001f684  mov     rcx, [rbp+pv]; pv
0x18001f688  mov     [rbp+pv], r15
0x18001f68c  test    rcx, rcx
0x18001f68f  jz      short loc_18001F697
0x18001f691  call    cs:__imp_CoTaskMemFree
0x18001f697  xor     eax, eax
0x18001f699  add     rsp, 68h
0x18001f69d  pop     r15
0x18001f69f  pop     r14
0x18001f6a1  pop     r13
0x18001f6a3  pop     r12
0x18001f6a5  pop     rdi
0x18001f6a6  pop     rsi
0x18001f6a7  pop     rbx
  ... truncated ...
```
