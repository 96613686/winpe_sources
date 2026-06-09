# GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)

- ea: `0x18001f3a8`
- end: `0x18001f7fa`
- name: `?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z`
- size: `1106`
- prototype: `int(struct EndpointCharacteristicsDescriptor *, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct _GUID *__struct_ptr, struct tWAVEFORMATEX **, struct tWAVEFORMATEX **, __int64 *, __int64 *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e0b0`
- `0x18001ec9c`
- `0x18001fb90`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x18001e9a0`
- `0x18001f3a8`
- `0x18001f800`
- `0x180020d2c`
- `0x180038b64`
- `0x180038f90`
- `0x18003d040`
- `0x180053f48`
- `0x180054d3c`
- `0x180061d20`
- `0x1800b5a54`
- `0x1800ce750`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f57b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f57b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7e1`

## string_xrefs

- `0x18001f413`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f4ce`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f58d`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f64b`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f72d`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001f7a9`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

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
                            `wil::Feature<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::GetImpl'::`2'::impl,
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
                           `wil::Feature<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::GetImpl'::`2'::impl,
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
0x18001f3a8  push    rbp
0x18001f3aa  push    rbx
0x18001f3ab  push    rsi
0x18001f3ac  push    rdi
0x18001f3ad  push    r12
0x18001f3af  push    r13
0x18001f3b1  push    r14
0x18001f3b3  push    r15
0x18001f3b5  mov     rbp, rsp
0x18001f3b8  sub     rsp, 68h
0x18001f3bc  mov     r14, r9
0x18001f3bf  mov     r13, r8
0x18001f3c2  mov     r12d, edx
0x18001f3c5  mov     rsi, rcx
0x18001f3c8  xor     r15d, r15d
0x18001f3cb  test    r9, r9
0x18001f3ce  jz      short loc_18001F3D3
0x18001f3d0  mov     [r9], r15
0x18001f3d3  mov     rbx, [rbp+pv]
0x18001f3d7  test    rbx, rbx
0x18001f3da  jz      short loc_18001F3DF
0x18001f3dc  mov     [rbx], r15
0x18001f3df  mov     r8, [rbp+arg_28]; __int64 *
0x18001f3e3  mov     r9, [rbp+arg_30]; __int64 *
0x18001f3e7  test    r9, r9
0x18001f3ea  jnz     short loc_18001F3F7
0x18001f3ec  test    r8, r8
0x18001f3ef  jnz     short loc_18001F3F7
0x18001f3f1  lea     rdi, [rcx+8]
0x18001f3f5  jmp     short loc_18001F42F
0x18001f3f7  lea     rdi, [rcx+8]
0x18001f3fb  xor     edx, edx; int
0x18001f3fd  mov     rcx, [rdi]; this
0x18001f400  call    ?GetProcessingPeriod@EffectPack@@QEAAJHPEA_J0@Z; EffectPack::GetProcessingPeriod(int,__int64 *,__int64 *)
0x18001f405  mov     r15d, eax
0x18001f408  test    eax, eax
0x18001f40a  jns     short loc_18001F42C
0x18001f40c  mov     rcx, [rbp+40h]; this
0x18001f410  mov     r9d, eax; char *
0x18001f413  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f41a  mov     edx, 0CA0h; void *
0x18001f41f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f424  mov     eax, r15d
0x18001f427  jmp     loc_18001F7E9
0x18001f42c  xor     r15d, r15d
0x18001f42f  mov     [rbp+pv], r15
0x18001f433  test    r14, r14
0x18001f436  jz      loc_18001F5CD
0x18001f43c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch> `wil::Feature<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::GetImpl(void)'::`2'::impl
0x18001f443  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::__private_IsEnabled(void)
0x18001f448  test    al, al
0x18001f44a  jz      loc_18001F525
0x18001f450  mov     [rbp+arg_18], r15
0x18001f454  lea     r8, [rbp+arg_18]; void **
0x18001f458  lea     rdx, _GUID_655e6959_84d5_43a4_b383_39d8f3094d70; struct _GUID *
0x18001f45f  mov     rcx, [rsi]; this
0x18001f462  call    ?TryGetCustomResourceManagerService@CEndpointCharacteristics@@QEAAJAEBU_GUID@@PEAPEAX@Z; CEndpointCharacteristics::TryGetCustomResourceManagerService(_GUID const &,void * *)
0x18001f467  mov     rcx, [rbp+arg_18]
0x18001f46b  test    rcx, rcx
0x18001f46e  jz      loc_18001F518
0x18001f474  mov     [rbp+arg_30], r15
0x18001f478  movaps  xmm0, xmmword ptr [r13+0]
0x18001f47d  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f482  mov     rax, [rcx]
0x18001f485  lea     rdx, [rbp+arg_30]
0x18001f489  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001f48e  lea     r9, [rbp+var_38]
0x18001f492  mov     r8d, r12d
0x18001f495  mov     rdx, rsi
0x18001f498  mov     rax, [rax+30h]
0x18001f49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4a1  mov     rcx, [rbp+arg_30]
0x18001f4a5  test    rcx, rcx
0x18001f4a8  jz      short loc_18001F50E
0x18001f4aa  mov     rax, [rcx]
0x18001f4ad  mov     rax, [rax+28h]
0x18001f4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4b6  mov     rcx, rax; Src
0x18001f4b9  mov     rdx, r14; struct tWAVEFORMATEX **
0x18001f4bc  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001f4c1  mov     edi, eax
0x18001f4c3  test    eax, eax
0x18001f4c5  jns     short loc_18001F50E
0x18001f4c7  mov     rcx, [rbp+40h]; this
0x18001f4cb  mov     r9d, eax; char *
0x18001f4ce  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f4d5  mov     edx, 0CB4h; void *
0x18001f4da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f4df  nop
0x18001f4e0  lea     rcx, [rbp+arg_30]
0x18001f4e4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f4e9  nop
0x18001f4ea  lea     rcx, [rbp+arg_18]
0x18001f4ee  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f4f3  nop
0x18001f4f4  mov     rcx, [rbp+pv]; pv
0x18001f4f8  mov     [rbp+pv], r15
0x18001f4fc  test    rcx, rcx
0x18001f4ff  jz      short loc_18001F507
0x18001f501  call    cs:__imp_CoTaskMemFree
0x18001f507  mov     eax, edi
0x18001f509  jmp     loc_18001F7E9
0x18001f50e  lea     rcx, [rbp+arg_30]
0x18001f512  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f517  nop
0x18001f518  lea     rcx, [rbp+arg_18]
0x18001f51c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f521  lea     rdi, [rsi+8]
0x18001f525  cmp     [r14], r15
0x18001f528  jnz     loc_18001F5CD
0x18001f52e  lea     rdi, [rsi+8]
0x18001f532  lea     rax, [rbp+pv]
0x18001f536  mov     [rbp+var_28], rax
0x18001f53a  mov     [rbp+var_20], r15
0x18001f53e  mov     [rbp+var_18], 1
0x18001f542  movaps  xmm0, xmmword ptr [r13+0]
0x18001f547  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f54c  lea     r9, [rbp+var_20]; struct tWAVEFORMATEX **
0x18001f550  lea     r8, [rbp+var_38]; struct _GUID
0x18001f554  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f557  mov     rcx, [rdi]; this
0x18001f55a  call    ?GetConnectorFormatForProcessingMode@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetConnectorFormatForProcessingMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001f55f  mov     r15d, eax
0x18001f562  cmp     [rbp+var_18], 0
0x18001f566  jz      short loc_18001F581
0x18001f568  mov     r8, [rbp+var_28]
0x18001f56c  mov     rcx, [r8]; pv
0x18001f56f  mov     rdx, [rbp+var_20]
0x18001f573  mov     [r8], rdx
0x18001f576  test    rcx, rcx
0x18001f579  jz      short loc_18001F581
0x18001f57b  call    cs:__imp_CoTaskMemFree
0x18001f581  test    r15d, r15d
0x18001f584  jns     short loc_18001F5BF
0x18001f586  mov     rcx, [rbp+40h]; this
0x18001f58a  mov     r9d, r15d; char *
0x18001f58d  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f594  mov     edx, 0CBBh; void *
0x18001f599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f59e  nop
0x18001f59f  mov     rcx, [rbp+pv]; pv
0x18001f5a3  mov     [rbp+pv], 0
0x18001f5ab  test    rcx, rcx
0x18001f5ae  jz      loc_18001F424
0x18001f5b4  call    cs:__imp_CoTaskMemFree
0x18001f5ba  jmp     loc_18001F424
0x18001f5bf  mov     rax, [rbp+pv]
0x18001f5c3  xor     r15d, r15d
0x18001f5c6  mov     [rbp+pv], r15
0x18001f5ca  mov     [r14], rax
0x18001f5cd  test    rbx, rbx
0x18001f5d0  jz      loc_18001F7D4
0x18001f5d6  movaps  xmm0, xmmword ptr [r13+0]
0x18001f5db  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f5e0  mov     r8d, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f5e3  lea     rdx, [rbp+var_38]; struct _GUID
0x18001f5e7  mov     rcx, [rdi]; this
0x18001f5ea  call    ?CanProcessingModeBeParameterized@EffectPack@@QEAA_NU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::CanProcessingModeBeParameterized(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18001f5ef  test    al, al
0x18001f5f1  jnz     loc_18001F69B
0x18001f5f7  mov     r8d, 10h; Size
0x18001f5fd  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x18001f604  mov     rcx, r13; Buf1
0x18001f607  call    memcmp_0
0x18001f60c  test    eax, eax
0x18001f60e  jnz     short loc_18001F622
0x18001f610  xor     r8d, r8d
0x18001f613  mov     edx, r12d
0x18001f616  mov     rcx, [rdi]
0x18001f619  call    ?CanBuildProcessingModesOnRawConnector@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@@Z; EffectPack::CanBuildProcessingModesOnRawConnector(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration)
0x18001f61e  test    eax, eax
0x18001f620  jnz     short loc_18001F69B
0x18001f622  movaps  xmm0, xmmword ptr [r13+0]
0x18001f627  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f62c  mov     r9, rbx; struct tWAVEFORMATEX **
0x18001f62f  lea     r8, [rbp+var_38]; struct _GUID
0x18001f633  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f636  mov     rcx, [rsi]; this
0x18001f639  call    ?TryGetDevicePipeFormat@CEndpointCharacteristics@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::TryGetDevicePipeFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001f63e  mov     edi, eax
0x18001f640  test    eax, eax
0x18001f642  jns     short loc_18001F661
0x18001f644  mov     rcx, [rbp+40h]; this
0x18001f648  mov     r9d, eax; char *
0x18001f64b  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f652  mov     edx, 0CE1h; void *
0x18001f657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f65c  jmp     loc_18001F4F4
0x18001f661  cmp     [rbx], r15
0x18001f664  jnz     loc_18001F7D4
0x18001f66a  movaps  xmm0, xmmword ptr [r13+0]
0x18001f66f  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f674  mov     r9, rbx; struct tWAVEFORMATEX **
0x18001f677  lea     r8, [rbp+var_38]; struct _GUID
0x18001f67b  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f67e  mov     rcx, [rsi+8]; this
0x18001f682  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001f687  mov     ebx, eax
0x18001f689  test    eax, eax
0x18001f68b  jns     loc_18001F7D4
0x18001f691  mov     edx, 0CE8h
0x18001f696  jmp     loc_18001F7A9
0x18001f69b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch> `wil::Feature<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::GetImpl(void)'::`2'::impl
0x18001f6a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_A2dpAptxAdaptiveLosslessModeSwitch>::__private_IsEnabled(void)
0x18001f6a7  test    al, al
0x18001f6a9  jz      loc_18001F77D
0x18001f6af  mov     [rbp+arg_18], r15
0x18001f6b3  lea     r8, [rbp+arg_18]; void **
0x18001f6b7  lea     rdx, _GUID_655e6959_84d5_43a4_b383_39d8f3094d70; struct _GUID *
0x18001f6be  mov     rcx, [rsi]; this
0x18001f6c1  call    ?TryGetCustomResourceManagerService@CEndpointCharacteristics@@QEAAJAEBU_GUID@@PEAPEAX@Z; CEndpointCharacteristics::TryGetCustomResourceManagerService(_GUID const &,void * *)
0x18001f6c6  mov     rcx, [rbp+arg_18]
0x18001f6ca  test    rcx, rcx
0x18001f6cd  jz      loc_18001F774
0x18001f6d3  mov     [rbp+arg_30], r15
0x18001f6d7  movaps  xmm0, xmmword ptr [r13+0]
0x18001f6dc  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f6e1  mov     rax, [rcx]
0x18001f6e4  lea     rdx, [rbp+arg_30]
0x18001f6e8  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001f6ed  lea     r9, [rbp+var_38]
0x18001f6f1  mov     r8d, r12d
0x18001f6f4  mov     rdx, rsi
0x18001f6f7  mov     rax, [rax+28h]
0x18001f6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f700  mov     rcx, [rbp+arg_30]
0x18001f704  test    rcx, rcx
0x18001f707  jz      short loc_18001F76A
0x18001f709  mov     rax, [rcx]
0x18001f70c  mov     rax, [rax+28h]
0x18001f710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f715  mov     rcx, rax; Src
0x18001f718  mov     rdx, rbx; struct tWAVEFORMATEX **
0x18001f71b  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001f720  mov     esi, eax
0x18001f722  test    eax, eax
0x18001f724  jns     short loc_18001F76A
0x18001f726  mov     rcx, [rbp+40h]; this
0x18001f72a  mov     r9d, eax; char *
0x18001f72d  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f734  mov     edx, 0CD1h; void *
0x18001f739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f73e  nop
0x18001f73f  lea     rcx, [rbp+arg_30]
0x18001f743  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f748  nop
0x18001f749  lea     rcx, [rbp+arg_18]
0x18001f74d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f752  nop
0x18001f753  mov     rcx, [rbp+pv]; pv
0x18001f757  mov     [rbp+pv], r15
0x18001f75b  test    rcx, rcx
0x18001f75e  jz      short loc_18001F766
0x18001f760  call    cs:__imp_CoTaskMemFree
0x18001f766  mov     eax, esi
0x18001f768  jmp     short loc_18001F7E9
0x18001f76a  lea     rcx, [rbp+arg_30]
0x18001f76e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f773  nop
0x18001f774  lea     rcx, [rbp+arg_18]
0x18001f778  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f77d  cmp     [rbx], r15
0x18001f780  jnz     short loc_18001F7D4
0x18001f782  movaps  xmm0, xmmword ptr [r13+0]
0x18001f787  movdqa  xmmword ptr [rbp+var_38.Data1], xmm0
0x18001f78c  mov     r9, rbx; struct tWAVEFORMATEX **
0x18001f78f  lea     r8, [rbp+var_38]; struct _GUID
0x18001f793  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001f796  mov     rcx, [rdi]; this
0x18001f799  call    ?GetDevicePipeFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetDevicePipeFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001f79e  mov     ebx, eax
0x18001f7a0  test    eax, eax
0x18001f7a2  jns     short loc_18001F7D4
0x18001f7a4  mov     edx, 0CDBh; void *
0x18001f7a9  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001f7b0  mov     r9d, ebx; char *
0x18001f7b3  mov     rcx, [rbp+40h]; this
0x18001f7b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f7bc  nop
0x18001f7bd  mov     rcx, [rbp+pv]; pv
0x18001f7c1  mov     [rbp+pv], r15
0x18001f7c5  test    rcx, rcx
0x18001f7c8  jz      short loc_18001F7D0
0x18001f7ca  call    cs:__imp_CoTaskMemFree
0x18001f7d0  mov     eax, ebx
0x18001f7d2  jmp     short loc_18001F7E9
0x18001f7d4  mov     rcx, [rbp+pv]; pv
0x18001f7d8  mov     [rbp+pv], r15
0x18001f7dc  test    rcx, rcx
0x18001f7df  jz      short loc_18001F7E7
0x18001f7e1  call    cs:__imp_CoTaskMemFree
0x18001f7e7  xor     eax, eax
0x18001f7e9  add     rsp, 68h
0x18001f7ed  pop     r15
0x18001f7ef  pop     r14
0x18001f7f1  pop     r13
0x18001f7f3  pop     r12
0x18001f7f5  pop     rdi
0x18001f7f6  pop     rsi
0x18001f7f7  pop     rbx
  ... truncated ...
```
