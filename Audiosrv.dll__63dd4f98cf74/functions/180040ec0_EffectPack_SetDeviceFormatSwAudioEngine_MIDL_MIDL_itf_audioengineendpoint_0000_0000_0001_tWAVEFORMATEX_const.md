# EffectPack::SetDeviceFormatSwAudioEngine(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)

- ea: `0x180040ec0`
- end: `0x1800413d7`
- name: `?SetDeviceFormatSwAudioEngine@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z`
- size: `1303`
- prototype: `__int64 __fastcall(CEndpointCharacteristics **this, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, const struct tWAVEFORMATEX *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18008a0f4`

## callees

- `0x18001280c`
- `0x1800202b0`
- `0x18002240c`
- `0x180023100`
- `0x18003f83c`
- `0x180040ec0`
- `0x1800413e0`
- `0x180041440`
- `0x1800414d0`
- `0x180041620`
- `0x18007097c`
- `0x18008a9a8`
- `0x1800bb344`
- `0x1800bb410`
- `0x1800cbfcc`
- `0x18013e6c4`
- `0x180141b8c`
- `0x180145ad0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800413d0`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800413d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004117d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800412ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004138e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800413c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004117d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800412ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004138e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800413c4`

## string_xrefs

- `0x180040f16`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180040f6c`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18004104c`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
__int64 __fastcall EffectPack::SetDeviceFormatSwAudioEngine(
        CEndpointCharacteristics **this,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a2,
        const struct tWAVEFORMATEX *a3)
{
  int v5; // eax
  unsigned int DeviceFormatAndSpatialSettings; // esi
  int v8; // eax
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v9; // esi
  struct _GUID v10; // xmm6
  CEndpointCharacteristics *v11; // r15
  int v12; // edx
  unsigned int SharedModeEnginePeriodicityForTranslatedProcessingMode; // edi
  struct EffectPack *v14; // rdx
  int v15; // eax
  int v16; // eax
  void *v17; // rcx
  void *v18; // rcx
  int updated; // eax
  void *v20; // rcx
  _lambda_f3b092209076b90048129f7b4270089e_ *v21; // rax
  int v22; // eax
  void *v23; // rcx
  int v24; // eax
  int v25; // eax
  void *v26; // rcx
  int v27; // eax
  void *v28; // rcx
  void *v29; // rcx
  int v30; // [rsp+28h] [rbp-89h]
  int v31; // [rsp+28h] [rbp-89h]
  int v32; // [rsp+28h] [rbp-89h]
  int v33; // [rsp+28h] [rbp-89h]
  int v34; // [rsp+28h] [rbp-89h]
  int v35; // [rsp+28h] [rbp-89h]
  struct _GUID v36; // [rsp+58h] [rbp-59h] BYREF
  char v37; // [rsp+68h] [rbp-49h]
  EffectPack *v38; // [rsp+78h] [rbp-39h]
  char v39; // [rsp+80h] [rbp-31h]
  _BYTE v40[24]; // [rsp+88h] [rbp-29h] BYREF
  _BYTE v41[32]; // [rsp+A0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v43; // [rsp+120h] [rbp+6Fh] BYREF
  LPVOID pv; // [rsp+128h] [rbp+77h] BYREF
  __int64 v45; // [rsp+130h] [rbp+7Fh] BYREF

  v43 = a2;
  v38 = (EffectPack *)this;
  v39 = 1;
  if ( a3 )
  {
    v8 = ValidateUncompressedWaveFormatEx(a3);
    DeviceFormatAndSpatialSettings = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x218A,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v8,
        v30);
      CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
      return DeviceFormatAndSpatialSettings;
    }
    v36 = 0;
    EffectPack::GetDefaultConnectorProcessingModeConfiguration((EffectPack *)this, v43, &v36, 0, 0);
    v9 = v43;
    if ( (int)v43 >= (unsigned __int64)this[236] )
    {
      _o_terminate();
      JUMPOUT(0x1800413D6LL);
    }
    v10 = v36;
    v11 = this[198];
    v31 = *((_DWORD *)this + 474) + 24 * v43;
    SharedModeEnginePeriodicityForTranslatedProcessingMode = CEndpointCharacteristics::GetSharedModeEnginePeriodicityForTranslatedProcessingMode(
                                                               v11,
                                                               (unsigned int)v43,
                                                               a3,
                                                               &v36);
    if ( SharedModeEnginePeriodicityForTranslatedProcessingMode == -2004287480 )
    {
      v36 = v10;
      if ( CEndpointCharacteristics::ConnectorProbablySupportsFormat(v11, v9, &v36, a3) )
        SharedModeEnginePeriodicityForTranslatedProcessingMode = -2005139389;
    }
    DeviceFormatAndSpatialSettings = 0;
    if ( !AEError::DeviceInUse((AEError *)SharedModeEnginePeriodicityForTranslatedProcessingMode, v12) )
      DeviceFormatAndSpatialSettings = SharedModeEnginePeriodicityForTranslatedProcessingMode;
    if ( (DeviceFormatAndSpatialSettings & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20D5,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)DeviceFormatAndSpatialSettings,
        v31);
      if ( DeviceFormatAndSpatialSettings != -2004287480 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x219E,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)DeviceFormatAndSpatialSettings,
          v32);
        CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
        return DeviceFormatAndSpatialSettings;
      }
      v15 = CEndpointCharacteristics::TryAddFormat(this[198], v14, a3);
      DeviceFormatAndSpatialSettings = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2197,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v15,
          v32);
        CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
        return DeviceFormatAndSpatialSettings;
      }
      v36 = v10;
      v16 = EffectPack::ConfirmDeviceFormat((EffectPack *)this, a3, &v36, v43, 0);
      DeviceFormatAndSpatialSettings = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x219A,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v16,
          v33);
        CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
        return DeviceFormatAndSpatialSettings;
      }
    }
    pv = 0;
    *(_QWORD *)&v36.Data1 = &pv;
    *(_QWORD *)v36.Data4 = 0;
    v37 = 1;
    DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                       (EffectPack *)this,
                                       eHostProcessConnector,
                                       0,
                                       (struct tWAVEFORMATEX **)v36.Data4,
                                       0,
                                       0,
                                       0);
    if ( v37 )
    {
      v17 = **(void ***)&v36.Data1;
      **(_QWORD **)&v36.Data1 = *(_QWORD *)v36.Data4;
      if ( v17 )
        CoTaskMemFree(v17);
    }
    if ( (DeviceFormatAndSpatialSettings & 0x80000000) == 0 )
    {
      updated = CEndpointCharacteristics::UpdateDeviceFormatEPProperty(this[198], 0, v43, a3);
      DeviceFormatAndSpatialSettings = updated;
      if ( updated >= 0 )
      {
        v21 = _lambda_f3b092209076b90048129f7b4270089e_::_lambda_f3b092209076b90048129f7b4270089e_(
                (_lambda_f3b092209076b90048129f7b4270089e_ *)v40,
                (bool *)this,
                (const int *)&v43,
                (bool *)&pv);
        wil::scope_exit__lambda_a67354e5279dd348e2b8b7a19b53b9e3___(v41, v21);
        v22 = EffectPack::DeriveAndCacheMixFormatsForConnector((EffectPack *)this, eHostProcessConnector);
        DeviceFormatAndSpatialSettings = v22;
        if ( v22 >= 0 )
        {
          v24 = EffectPack::DeriveAndCacheMixFormatsForConnector((EffectPack *)this, eKeywordDetectorConnector);
          if ( v24 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x21B3,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
              (const char *)(unsigned int)v24,
              v34);
          v45 = 0;
          v25 = CEndpointCharacteristics::SetProcessingPeriod(this[198], &v45);
          DeviceFormatAndSpatialSettings = v25;
          if ( v25 >= 0 )
          {
            v36 = 0;
            EffectPack::GetDefaultConnectorProcessingModeConfiguration((EffectPack *)this, v43, &v36, 0, 0);
            v27 = EffectPack::ConfirmDeviceFormat((EffectPack *)this, a3, &v36, v43, 1);
            DeviceFormatAndSpatialSettings = v27;
            if ( v27 >= 0 )
            {
              v41[24] = 0;
              wil::details::lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___::_lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___(v41);
              v29 = pv;
              pv = 0;
              if ( v29 )
                CoTaskMemFree(v29);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x21C8,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
              (const char *)(unsigned int)v27,
              v35);
            wil::details::lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___::_lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___(v41);
            v28 = pv;
            pv = 0;
            if ( v28 )
              CoTaskMemFree(v28);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x21BC,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
              (const char *)(unsigned int)v25,
              v34);
            wil::details::lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___::_lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___(v41);
            v26 = pv;
            pv = 0;
            if ( v26 )
              CoTaskMemFree(v26);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x21AF,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)(unsigned int)v22,
            v34);
          wil::details::lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___::_lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___(v41);
          v23 = pv;
          pv = 0;
          if ( v23 )
            CoTaskMemFree(v23);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21A6,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)updated,
          v34);
        v20 = pv;
        pv = 0;
        if ( v20 )
          CoTaskMemFree(v20);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21A3,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)DeviceFormatAndSpatialSettings,
        v34);
      v18 = pv;
      pv = 0;
      if ( v18 )
        CoTaskMemFree(v18);
    }
    CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
    return DeviceFormatAndSpatialSettings;
  }
  v5 = CEndpointCharacteristics::UpdateDeviceFormatEPProperty(this[198], 0, a2, 0);
  DeviceFormatAndSpatialSettings = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2184,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v5,
      v30);
    CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
    return DeviceFormatAndSpatialSettings;
  }
  return 0;
}

```

## disassembly

```asm
0x180040ec0  mov     rax, rsp
0x180040ec3  mov     [rax+10h], edx
0x180040ec6  push    rbp
0x180040ec7  push    rbx
0x180040ec8  push    rsi
0x180040ec9  push    rdi
0x180040eca  push    r12
0x180040ecc  push    r14
0x180040ece  push    r15
0x180040ed0  lea     rbp, [rax-5Fh]
0x180040ed4  sub     rsp, 0D0h
0x180040edb  movaps  xmmword ptr [rax-48h], xmm6
0x180040edf  mov     r14, r8
0x180040ee2  mov     rbx, rcx
0x180040ee5  mov     [rbp+57h+var_90], rcx
0x180040ee9  mov     [rbp+57h+var_88], 1
0x180040eed  xor     r12d, r12d
0x180040ef0  test    r8, r8
0x180040ef3  jnz     short loc_180040F57
0x180040ef5  xor     r9d, r9d; struct tWAVEFORMATEX *
0x180040ef8  mov     r8d, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180040efb  xor     edx, edx; bool
0x180040efd  mov     rcx, [rcx+630h]; this
0x180040f04  call    ?UpdateDeviceFormatEPProperty@CEndpointCharacteristics@@QEAAJ_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::UpdateDeviceFormatEPProperty(bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)
0x180040f09  mov     esi, eax
0x180040f0b  test    eax, eax
0x180040f0d  jns     short loc_180040F53
0x180040f0f  mov     rcx, [rbp+5Fh]; this
0x180040f13  mov     r9d, eax; char *
0x180040f16  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180040f1d  mov     edx, 2184h; void *
0x180040f22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f27  nop
0x180040f28  xor     edx, edx
0x180040f2a  mov     rcx, [rbx+630h]
0x180040f31  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180040f36  nop
0x180040f37  mov     eax, esi
0x180040f39  movaps  xmm6, [rsp+100h+var_48+8]
0x180040f41  add     rsp, 0D0h
0x180040f48  pop     r15
0x180040f4a  pop     r14
0x180040f4c  pop     r12
0x180040f4e  pop     rdi
0x180040f4f  pop     rsi
0x180040f50  pop     rbx
0x180040f51  pop     rbp
0x180040f52  retn
0x180040f53  xor     eax, eax
0x180040f55  jmp     short loc_180040F39
0x180040f57  mov     rcx, r14; struct tWAVEFORMATEX *
0x180040f5a  call    ?ValidateUncompressedWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x180040f5f  mov     esi, eax
0x180040f61  test    eax, eax
0x180040f63  jns     short loc_180040F8F
0x180040f65  mov     rcx, [rbp+5Fh]; this
0x180040f69  mov     r9d, eax; char *
0x180040f6c  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180040f73  mov     edx, 218Ah; void *
0x180040f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f7d  nop
0x180040f7e  xor     edx, edx
0x180040f80  mov     rcx, [rbx+630h]
0x180040f87  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180040f8c  nop
0x180040f8d  jmp     short loc_180040F37
0x180040f8f  xorps   xmm0, xmm0
0x180040f92  movups  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x180040f96  mov     [rsp+100h+var_E0], r12; struct _GUID *
0x180040f9b  xor     r9d, r9d; struct _GUID *
0x180040f9e  lea     r8, [rbp+57h+var_B0]; struct _GUID *
0x180040fa2  mov     edx, [rbp+57h+arg_8]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180040fa5  mov     rcx, rbx; this
0x180040fa8  call    ?GetDefaultConnectorProcessingModeConfiguration@EffectPack@@QEAAXW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAU_GUID@@11@Z; EffectPack::GetDefaultConnectorProcessingModeConfiguration(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID *,_GUID *,_GUID *)
0x180040fad  movsxd  rsi, [rbp+57h+arg_8]
0x180040fb1  cmp     rsi, [rbx+760h]
0x180040fb8  jnb     loc_1800413D0
0x180040fbe  movaps  xmm6, xmmword ptr [rbp+57h+var_B0.Data1]
0x180040fc2  mov     r15, [rbx+630h]
0x180040fc9  lea     rcx, [rsi+rsi*2]
0x180040fcd  mov     rax, [rbx+768h]
0x180040fd4  lea     rdx, [rax+rcx*8]
0x180040fd8  mov     [rbp+57h+arg_0], r12d
0x180040fdc  movdqa  xmmword ptr [rbp+57h+var_B0.Data1], xmm6
0x180040fe1  mov     [rsp+48h], r12
0x180040fe6  mov     [rsp+100h+var_C0], r12
0x180040feb  mov     [rsp+100h+var_C8], r12
0x180040ff0  lea     rax, [rbp+57h+arg_0]
0x180040ff4  mov     [rsp+100h+var_D0], rax
0x180040ff9  mov     dword ptr [rsp+100h+var_D8], r12d
0x180040ffe  mov     [rsp+100h+var_E0], rdx; int
0x180041003  lea     r9, [rbp+57h+var_B0]
0x180041007  mov     r8, r14
0x18004100a  mov     edx, esi
0x18004100c  mov     rcx, r15
0x18004100f  call    ?GetSharedModeEnginePeriodicityForTranslatedProcessingMode@CEndpointCharacteristics@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@AEAVCAudioSignalProcessingModeMap@@W4PeriodicityType@@PEAI555@Z; CEndpointCharacteristics::GetSharedModeEnginePeriodicityForTranslatedProcessingMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,CAudioSignalProcessingModeMap &,PeriodicityType,uint *,uint *,uint *,uint *)
0x180041014  mov     edi, eax
0x180041016  cmp     eax, 88890008h
0x18004101b  jnz     short loc_18004103D
0x18004101d  movdqa  xmmword ptr [rbp+57h+var_B0.Data1], xmm6
0x180041022  mov     r9, r14; struct tWAVEFORMATEX *
0x180041025  lea     r8, [rbp+57h+var_B0]; struct _GUID
0x180041029  mov     edx, esi; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18004102b  mov     rcx, r15; this
0x18004102e  call    ?ConnectorProbablySupportsFormat@CEndpointCharacteristics@@QEAA_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::ConnectorProbablySupportsFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX const *)
0x180041033  mov     ecx, 887C0043h
0x180041038  test    al, al
0x18004103a  cmovnz  edi, ecx
0x18004103d  mov     ecx, edi; this
0x18004103f  call    ?DeviceInUse@AEError@@YA_NJ@Z; AEError::DeviceInUse(long)
0x180041044  mov     esi, r12d
0x180041047  test    al, al
0x180041049  cmovz   esi, edi
0x18004104c  lea     rdi, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180041053  test    esi, esi
0x180041055  jns     loc_18004112E
0x18004105b  mov     rcx, [rbp+5Fh]; this
0x18004105f  mov     r9d, esi; char *
0x180041062  mov     r8, rdi; unsigned int
0x180041065  mov     edx, 20D5h; void *
0x18004106a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004106f  cmp     esi, 88890008h
0x180041075  jnz     loc_180041105
0x18004107b  mov     r8, r14; struct tWAVEFORMATEX *
0x18004107e  mov     rcx, [rbx+630h]; this
0x180041085  call    ?TryAddFormat@CEndpointCharacteristics@@QEAAJPEAVEffectPack@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::TryAddFormat(EffectPack *,tWAVEFORMATEX const *)
0x18004108a  mov     esi, eax
0x18004108c  test    eax, eax
0x18004108e  jns     short loc_1800410B9
0x180041090  mov     rcx, [rbp+5Fh]; this
0x180041094  mov     r9d, eax; char *
0x180041097  mov     r8, rdi; unsigned int
0x18004109a  mov     edx, 2197h; void *
0x18004109f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800410a4  nop
0x1800410a5  xor     edx, edx
0x1800410a7  mov     rcx, [rbx+630h]
0x1800410ae  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x1800410b3  nop
0x1800410b4  jmp     loc_180040F37
0x1800410b9  movdqa  xmmword ptr [rbp+57h+var_B0.Data1], xmm6
0x1800410be  mov     dword ptr [rsp+100h+var_E0], r12d; int
0x1800410c3  mov     r9d, [rbp+57h+arg_8]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800410c7  lea     r8, [rbp+57h+var_B0]; struct _GUID *
0x1800410cb  mov     rdx, r14; struct tWAVEFORMATEX *
0x1800410ce  mov     rcx, rbx; this
0x1800410d1  call    ?ConfirmDeviceFormat@EffectPack@@AEAAJPEBUtWAVEFORMATEX@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@H@Z; EffectPack::ConfirmDeviceFormat(tWAVEFORMATEX const *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int)
0x1800410d6  mov     esi, eax
0x1800410d8  test    eax, eax
0x1800410da  jns     short loc_18004112E
0x1800410dc  mov     rcx, [rbp+5Fh]; this
0x1800410e0  mov     r9d, eax; char *
0x1800410e3  mov     r8, rdi; unsigned int
0x1800410e6  mov     edx, 219Ah; void *
0x1800410eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800410f0  nop
0x1800410f1  xor     edx, edx
0x1800410f3  mov     rcx, [rbx+630h]
0x1800410fa  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x1800410ff  nop
0x180041100  jmp     loc_180040F37
0x180041105  mov     rcx, [rbp+5Fh]; this
0x180041109  mov     r9d, esi; char *
0x18004110c  mov     r8, rdi; unsigned int
0x18004110f  mov     edx, 219Eh; void *
0x180041114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041119  nop
0x18004111a  xor     edx, edx
0x18004111c  mov     rcx, [rbx+630h]
0x180041123  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180041128  nop
0x180041129  jmp     loc_180040F37
0x18004112e  mov     [rbp+57h+pv], r12
0x180041132  lea     rax, [rbp+57h+pv]
0x180041136  mov     qword ptr [rbp+57h+var_B0.Data1], rax
0x18004113a  mov     qword ptr [rbp+57h+var_B0.Data4], r12
0x18004113e  mov     [rbp+57h+var_A0], 1
0x180041142  mov     [rsp+100h+var_D0], r12; pv
0x180041147  mov     [rsp+100h+var_D8], r12; unsigned int *
0x18004114c  mov     [rsp+100h+var_E0], r12; int
0x180041151  lea     r9, [rbp+57h+var_B0.Data4]; struct tWAVEFORMATEX **
0x180041155  xor     r8d, r8d; int
0x180041158  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18004115a  mov     rcx, rbx; this
0x18004115d  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x180041162  mov     esi, eax
0x180041164  cmp     [rbp+57h+var_A0], r12b
0x180041168  jz      short loc_180041183
0x18004116a  mov     r8, qword ptr [rbp+57h+var_B0.Data1]
0x18004116e  mov     rcx, [r8]; pv
0x180041171  mov     rdx, qword ptr [rbp+57h+var_B0.Data4]
0x180041175  mov     [r8], rdx
0x180041178  test    rcx, rcx
0x18004117b  jz      short loc_180041183
0x18004117d  call    cs:__imp_CoTaskMemFree
0x180041183  test    esi, esi
0x180041185  jns     short loc_1800411C4
0x180041187  mov     rcx, [rbp+5Fh]; this
0x18004118b  mov     r9d, esi; char *
0x18004118e  mov     r8, rdi; unsigned int
0x180041191  mov     edx, 21A3h; void *
0x180041196  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004119b  nop
0x18004119c  mov     rcx, [rbp+57h+pv]; pv
0x1800411a0  mov     [rbp+57h+pv], r12
0x1800411a4  test    rcx, rcx
0x1800411a7  jz      short loc_1800411B0
0x1800411a9  call    cs:__imp_CoTaskMemFree
0x1800411af  nop
0x1800411b0  xor     edx, edx
0x1800411b2  mov     rcx, [rbx+630h]
0x1800411b9  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x1800411be  nop
0x1800411bf  jmp     loc_180040F37
0x1800411c4  mov     r9, r14; struct tWAVEFORMATEX *
0x1800411c7  mov     r8d, [rbp+57h+arg_8]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800411cb  xor     edx, edx; bool
0x1800411cd  mov     rcx, [rbx+630h]; this
0x1800411d4  call    ?UpdateDeviceFormatEPProperty@CEndpointCharacteristics@@QEAAJ_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::UpdateDeviceFormatEPProperty(bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)
0x1800411d9  mov     esi, eax
0x1800411db  test    eax, eax
0x1800411dd  jns     short loc_18004121C
0x1800411df  mov     rcx, [rbp+5Fh]; this
0x1800411e3  mov     r9d, eax; char *
0x1800411e6  mov     r8, rdi; unsigned int
0x1800411e9  mov     edx, 21A6h; void *
0x1800411ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800411f3  nop
0x1800411f4  mov     rcx, [rbp+57h+pv]; pv
0x1800411f8  mov     [rbp+57h+pv], r12
0x1800411fc  test    rcx, rcx
0x1800411ff  jz      short loc_180041208
0x180041201  call    cs:__imp_CoTaskMemFree
0x180041207  nop
0x180041208  xor     edx, edx
0x18004120a  mov     rcx, [rbx+630h]
0x180041211  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180041216  nop
0x180041217  jmp     loc_180040F37
0x18004121c  lea     r9, [rbp+57h+pv]; bool *
0x180041220  lea     r8, [rbp+57h+arg_8]; int *
0x180041224  mov     rdx, rbx; bool *
0x180041227  lea     rcx, [rbp+57h+var_80]; this
0x18004122b  call    ??0_lambda_f3b092209076b90048129f7b4270089e_@@QEAA@AEA_NAEBH0@Z; _lambda_f3b092209076b90048129f7b4270089e_::_lambda_f3b092209076b90048129f7b4270089e_(bool &,int const &,bool &)
0x180041230  mov     rdx, rax
0x180041233  lea     rcx, [rbp+57h+var_68]
0x180041237  call    wil__scope_exit__lambda_a67354e5279dd348e2b8b7a19b53b9e3___
0x18004123c  nop
0x18004123d  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18004123f  mov     rcx, rbx; this
0x180041242  call    ?DeriveAndCacheMixFormatsForConnector@EffectPack@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::DeriveAndCacheMixFormatsForConnector(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x180041247  mov     esi, eax
0x180041249  test    eax, eax
0x18004124b  jns     short loc_180041294
0x18004124d  mov     rcx, [rbp+5Fh]; this
0x180041251  mov     r9d, eax; char *
0x180041254  mov     r8, rdi; unsigned int
0x180041257  mov     edx, 21AFh; void *
0x18004125c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041261  nop
0x180041262  lea     rcx, [rbp+57h+var_68]
0x180041266  call    wil__details__lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3______lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___
0x18004126b  nop
0x18004126c  mov     rcx, [rbp+57h+pv]; pv
0x180041270  mov     [rbp+57h+pv], r12
0x180041274  test    rcx, rcx
0x180041277  jz      short loc_180041280
0x180041279  call    cs:__imp_CoTaskMemFree
0x18004127f  nop
0x180041280  xor     edx, edx
0x180041282  mov     rcx, [rbx+630h]
0x180041289  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x18004128e  nop
0x18004128f  jmp     loc_180040F37
0x180041294  mov     edx, 3; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180041299  mov     rcx, rbx; this
0x18004129c  call    ?DeriveAndCacheMixFormatsForConnector@EffectPack@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::DeriveAndCacheMixFormatsForConnector(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x1800412a1  mov     rcx, [rbp+5Fh]; this
0x1800412a5  test    eax, eax
0x1800412a7  jns     short loc_1800412B9
0x1800412a9  mov     r9d, eax; char *
0x1800412ac  mov     r8, rdi; unsigned int
0x1800412af  mov     edx, 21B3h; void *
0x1800412b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800412b9  mov     [rbp+57h+arg_18], r12
0x1800412bd  lea     rdx, [rbp+57h+arg_18]; __int64 *
0x1800412c1  mov     rcx, [rbx+630h]; this
0x1800412c8  call    ?SetProcessingPeriod@CEndpointCharacteristics@@QEAAJAEB_J@Z; CEndpointCharacteristics::SetProcessingPeriod(__int64 const &)
0x1800412cd  mov     esi, eax
0x1800412cf  test    eax, eax
0x1800412d1  jns     short loc_18004131A
0x1800412d3  mov     rcx, [rbp+5Fh]; this
0x1800412d7  mov     r9d, eax; char *
0x1800412da  mov     r8, rdi; unsigned int
0x1800412dd  mov     edx, 21BCh; void *
0x1800412e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800412e7  nop
0x1800412e8  lea     rcx, [rbp+57h+var_68]
0x1800412ec  call    wil__details__lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3______lambda_call__lambda_a67354e5279dd348e2b8b7a19b53b9e3___
0x1800412f1  nop
  ... truncated ...
```
