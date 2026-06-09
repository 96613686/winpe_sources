# EffectPack::SetDeviceFormatSwAudioEngine(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)

- ea: `0x180040d50`
- end: `0x1800412bf`
- name: `?SetDeviceFormatSwAudioEngine@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z`
- size: `1391`
- prototype: `__int64 __fastcall(EffectPack *__hidden this, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, const struct tWAVEFORMATEX *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18008a5f4`

## callees

- `0x1800126bc`
- `0x180020160`
- `0x1800222bc`
- `0x180022fb0`
- `0x18003f6cc`
- `0x180040d50`
- `0x1800412c8`
- `0x180041328`
- `0x1800413b8`
- `0x180041500`
- `0x1800423fc`
- `0x180070e7c`
- `0x1800cdfbc`
- `0x180141278`
- `0x180144e50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800412b8`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800412b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004100d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800412ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004100d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800412ac`

## string_xrefs

- `0x180040da6`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180040dfc`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180040edc`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  int v21; // eax
  int v22; // eax
  void *v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  void *v27; // rcx
  int v28; // eax
  int v29; // eax
  void *v30; // rcx
  void *v31; // rcx
  int v32; // [rsp+28h] [rbp-69h]
  int v33; // [rsp+28h] [rbp-69h]
  int v34; // [rsp+28h] [rbp-69h]
  int v35; // [rsp+28h] [rbp-69h]
  int v36; // [rsp+28h] [rbp-69h]
  int v37; // [rsp+28h] [rbp-69h]
  int v38; // [rsp+28h] [rbp-69h]
  int v39; // [rsp+28h] [rbp-69h]
  int v40; // [rsp+28h] [rbp-69h]
  struct _GUID v41; // [rsp+58h] [rbp-39h] BYREF
  char v42; // [rsp+68h] [rbp-29h]
  EffectPack *v43; // [rsp+78h] [rbp-19h]
  char v44; // [rsp+80h] [rbp-11h]
  EffectPack *v45; // [rsp+88h] [rbp-9h]
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 *v46; // [rsp+90h] [rbp-1h]
  LPVOID *p_pv; // [rsp+98h] [rbp+7h]
  __int128 v48; // [rsp+A0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v50; // [rsp+100h] [rbp+6Fh] BYREF
  LPVOID pv; // [rsp+108h] [rbp+77h] BYREF
  __int64 v52; // [rsp+110h] [rbp+7Fh] BYREF

  v50 = a2;
  v43 = (EffectPack *)this;
  v44 = 1;
  if ( a3 )
  {
    v8 = ValidateUncompressedWaveFormatEx(a3);
    DeviceFormatAndSpatialSettings = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x218B,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v8,
        v32);
      CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
      return DeviceFormatAndSpatialSettings;
    }
    v41 = 0;
    EffectPack::GetDefaultConnectorProcessingModeConfiguration((EffectPack *)this, v50, &v41, 0, 0);
    v9 = v50;
    if ( (int)v50 >= (unsigned __int64)this[236] )
    {
      _o_terminate();
      JUMPOUT(0x1800412BELL);
    }
    v10 = v41;
    v11 = this[198];
    v33 = *((_DWORD *)this + 474) + 24 * v50;
    SharedModeEnginePeriodicityForTranslatedProcessingMode = CEndpointCharacteristics::GetSharedModeEnginePeriodicityForTranslatedProcessingMode(
                                                               v11,
                                                               (unsigned int)v50,
                                                               a3,
                                                               &v41);
    if ( SharedModeEnginePeriodicityForTranslatedProcessingMode == -2004287480 )
    {
      v41 = v10;
      if ( CEndpointCharacteristics::ConnectorProbablySupportsFormat(v11, v9, &v41, a3) )
        SharedModeEnginePeriodicityForTranslatedProcessingMode = -2005139389;
    }
    DeviceFormatAndSpatialSettings = 0;
    if ( !AEError::DeviceInUse((AEError *)SharedModeEnginePeriodicityForTranslatedProcessingMode, v12) )
      DeviceFormatAndSpatialSettings = SharedModeEnginePeriodicityForTranslatedProcessingMode;
    if ( (DeviceFormatAndSpatialSettings & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20D6,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)DeviceFormatAndSpatialSettings,
        v33);
      if ( DeviceFormatAndSpatialSettings != -2004287480 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x219F,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)DeviceFormatAndSpatialSettings,
          v34);
        CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
        return DeviceFormatAndSpatialSettings;
      }
      v15 = CEndpointCharacteristics::TryAddFormat(this[198], v14, a3);
      DeviceFormatAndSpatialSettings = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2198,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v15,
          v34);
        CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
        return DeviceFormatAndSpatialSettings;
      }
      v41 = v10;
      v16 = EffectPack::ConfirmDeviceFormat((EffectPack *)this, a3, &v41, v50, 0);
      DeviceFormatAndSpatialSettings = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x219B,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v16,
          v35);
        CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
        return DeviceFormatAndSpatialSettings;
      }
    }
    pv = 0;
    *(_QWORD *)&v41.Data1 = &pv;
    *(_QWORD *)v41.Data4 = 0;
    v42 = 1;
    DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                       (EffectPack *)this,
                                       eHostProcessConnector,
                                       0,
                                       (struct tWAVEFORMATEX **)v41.Data4,
                                       0,
                                       0,
                                       0);
    if ( v42 )
    {
      v17 = **(void ***)&v41.Data1;
      **(_QWORD **)&v41.Data1 = *(_QWORD *)v41.Data4;
      if ( v17 )
        CoTaskMemFree(v17);
    }
    if ( (DeviceFormatAndSpatialSettings & 0x80000000) == 0 )
    {
      updated = CEndpointCharacteristics::UpdateDeviceFormatEPProperty(this[198], 0, v50, a3);
      DeviceFormatAndSpatialSettings = updated;
      if ( updated >= 0 )
      {
        v45 = (EffectPack *)this;
        v46 = &v50;
        p_pv = &pv;
        LOBYTE(v48) = 1;
        v21 = EffectPack::DeriveAndCacheMixFormatsForConnector((EffectPack *)this, eHostProcessConnector);
        DeviceFormatAndSpatialSettings = v21;
        if ( v21 >= 0 )
        {
          v24 = EffectPack::DeriveAndCacheMixFormatsForConnector((EffectPack *)this, eKeywordDetectorConnector);
          if ( v24 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x21B4,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
              (const char *)(unsigned int)v24,
              v36);
          v52 = 0;
          v25 = CEndpointCharacteristics::SetProcessingPeriod(this[198], &v52);
          DeviceFormatAndSpatialSettings = v25;
          if ( v25 >= 0 )
          {
            v41 = 0;
            EffectPack::GetDefaultConnectorProcessingModeConfiguration((EffectPack *)this, v50, &v41, 0, 0);
            v28 = EffectPack::ConfirmDeviceFormat((EffectPack *)this, a3, &v41, v50, 1);
            DeviceFormatAndSpatialSettings = v28;
            if ( v28 >= 0 )
            {
              v31 = pv;
              pv = 0;
              if ( v31 )
                CoTaskMemFree(v31);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x21C9,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
              (const char *)(unsigned int)v28,
              v39);
            v29 = CEndpointCharacteristics::UpdateDeviceFormatEPProperty(
                    this[198],
                    0,
                    v50,
                    (const struct tWAVEFORMATEX *)pv);
            if ( v29 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x21AC,
                (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
                (const char *)(unsigned int)v29,
                v40);
            v30 = pv;
            pv = 0;
            if ( v30 )
              CoTaskMemFree(v30);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x21BD,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
              (const char *)(unsigned int)v25,
              v36);
            v26 = CEndpointCharacteristics::UpdateDeviceFormatEPProperty(
                    this[198],
                    0,
                    v50,
                    (const struct tWAVEFORMATEX *)pv);
            if ( v26 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x21AC,
                (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
                (const char *)(unsigned int)v26,
                v38);
            v27 = pv;
            pv = 0;
            if ( v27 )
              CoTaskMemFree(v27);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x21B0,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)(unsigned int)v21,
            v36);
          v22 = CEndpointCharacteristics::UpdateDeviceFormatEPProperty(
                  this[198],
                  0,
                  v50,
                  (const struct tWAVEFORMATEX *)pv);
          if ( v22 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x21AC,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
              (const char *)(unsigned int)v22,
              v37);
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
          (void *)0x21A7,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)updated,
          v36);
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
        (void *)0x21A4,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)DeviceFormatAndSpatialSettings,
        v36);
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
      (void *)0x2185,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v5,
      v32);
    CEndpointCharacteristics::ClearMixFormatCache(this[198], 0);
    return DeviceFormatAndSpatialSettings;
  }
  return 0;
}

```

## disassembly

```asm
0x180040d50  mov     rax, rsp
0x180040d53  mov     [rax+10h], edx
0x180040d56  push    rbp
0x180040d57  push    rbx
0x180040d58  push    rsi
0x180040d59  push    rdi
0x180040d5a  push    r12
0x180040d5c  push    r14
0x180040d5e  push    r15
0x180040d60  lea     rbp, [rax-5Fh]
0x180040d64  sub     rsp, 0B0h
0x180040d6b  movaps  xmmword ptr [rax-48h], xmm6
0x180040d6f  mov     r14, r8
0x180040d72  mov     rbx, rcx
0x180040d75  mov     [rbp+57h+var_70], rcx
0x180040d79  mov     [rbp+57h+var_68], 1
0x180040d7d  xor     r12d, r12d
0x180040d80  test    r8, r8
0x180040d83  jnz     short loc_180040DE7
0x180040d85  xor     r9d, r9d; struct tWAVEFORMATEX *
0x180040d88  mov     r8d, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180040d8b  xor     edx, edx; bool
0x180040d8d  mov     rcx, [rcx+630h]; this
0x180040d94  call    ?UpdateDeviceFormatEPProperty@CEndpointCharacteristics@@QEAAJ_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::UpdateDeviceFormatEPProperty(bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)
0x180040d99  mov     esi, eax
0x180040d9b  test    eax, eax
0x180040d9d  jns     short loc_180040DE3
0x180040d9f  mov     rcx, [rbp+5Fh]; this
0x180040da3  mov     r9d, eax; char *
0x180040da6  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180040dad  mov     edx, 2185h; void *
0x180040db2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040db7  nop
0x180040db8  xor     edx, edx
0x180040dba  mov     rcx, [rbx+630h]
0x180040dc1  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180040dc6  nop
0x180040dc7  mov     eax, esi
0x180040dc9  movaps  xmm6, [rsp+0E0h+var_48+8]
0x180040dd1  add     rsp, 0B0h
0x180040dd8  pop     r15
0x180040dda  pop     r14
0x180040ddc  pop     r12
0x180040dde  pop     rdi
0x180040ddf  pop     rsi
0x180040de0  pop     rbx
0x180040de1  pop     rbp
0x180040de2  retn
0x180040de3  xor     eax, eax
0x180040de5  jmp     short loc_180040DC9
0x180040de7  mov     rcx, r14; struct tWAVEFORMATEX *
0x180040dea  call    ?ValidateUncompressedWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x180040def  mov     esi, eax
0x180040df1  test    eax, eax
0x180040df3  jns     short loc_180040E1F
0x180040df5  mov     rcx, [rbp+5Fh]; this
0x180040df9  mov     r9d, eax; char *
0x180040dfc  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180040e03  mov     edx, 218Bh; void *
0x180040e08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040e0d  nop
0x180040e0e  xor     edx, edx
0x180040e10  mov     rcx, [rbx+630h]
0x180040e17  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180040e1c  nop
0x180040e1d  jmp     short loc_180040DC7
0x180040e1f  xorps   xmm0, xmm0
0x180040e22  movups  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x180040e26  mov     [rsp+0E0h+var_C0], r12; struct _GUID *
0x180040e2b  xor     r9d, r9d; struct _GUID *
0x180040e2e  lea     r8, [rbp+57h+var_90]; struct _GUID *
0x180040e32  mov     edx, [rbp+57h+arg_8]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180040e35  mov     rcx, rbx; this
0x180040e38  call    ?GetDefaultConnectorProcessingModeConfiguration@EffectPack@@QEAAXW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAU_GUID@@11@Z; EffectPack::GetDefaultConnectorProcessingModeConfiguration(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID *,_GUID *,_GUID *)
0x180040e3d  movsxd  rsi, [rbp+57h+arg_8]
0x180040e41  cmp     rsi, [rbx+760h]
0x180040e48  jnb     loc_1800412B8
0x180040e4e  movaps  xmm6, xmmword ptr [rbp+57h+var_90.Data1]
0x180040e52  mov     r15, [rbx+630h]
0x180040e59  lea     rcx, [rsi+rsi*2]
0x180040e5d  mov     rax, [rbx+768h]
0x180040e64  lea     rdx, [rax+rcx*8]
0x180040e68  mov     [rbp+57h+arg_0], r12d
0x180040e6c  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm6
0x180040e71  mov     [rsp+48h], r12
0x180040e76  mov     [rsp+0E0h+var_A0], r12
0x180040e7b  mov     [rsp+0E0h+var_A8], r12
0x180040e80  lea     rax, [rbp+57h+arg_0]
0x180040e84  mov     [rsp+0E0h+var_B0], rax
0x180040e89  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x180040e8e  mov     [rsp+0E0h+var_C0], rdx; int
0x180040e93  lea     r9, [rbp+57h+var_90]
0x180040e97  mov     r8, r14
0x180040e9a  mov     edx, esi
0x180040e9c  mov     rcx, r15
0x180040e9f  call    ?GetSharedModeEnginePeriodicityForTranslatedProcessingMode@CEndpointCharacteristics@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@AEAVCAudioSignalProcessingModeMap@@W4PeriodicityType@@PEAI555@Z; CEndpointCharacteristics::GetSharedModeEnginePeriodicityForTranslatedProcessingMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,CAudioSignalProcessingModeMap &,PeriodicityType,uint *,uint *,uint *,uint *)
0x180040ea4  mov     edi, eax
0x180040ea6  cmp     eax, 88890008h
0x180040eab  jnz     short loc_180040ECD
0x180040ead  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm6
0x180040eb2  mov     r9, r14; struct tWAVEFORMATEX *
0x180040eb5  lea     r8, [rbp+57h+var_90]; struct _GUID
0x180040eb9  mov     edx, esi; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180040ebb  mov     rcx, r15; this
0x180040ebe  call    ?ConnectorProbablySupportsFormat@CEndpointCharacteristics@@QEAA_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::ConnectorProbablySupportsFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX const *)
0x180040ec3  mov     ecx, 887C0043h
0x180040ec8  test    al, al
0x180040eca  cmovnz  edi, ecx
0x180040ecd  mov     ecx, edi; this
0x180040ecf  call    ?DeviceInUse@AEError@@YA_NJ@Z; AEError::DeviceInUse(long)
0x180040ed4  mov     esi, r12d
0x180040ed7  test    al, al
0x180040ed9  cmovz   esi, edi
0x180040edc  lea     rdi, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180040ee3  test    esi, esi
0x180040ee5  jns     loc_180040FBE
0x180040eeb  mov     rcx, [rbp+5Fh]; this
0x180040eef  mov     r9d, esi; char *
0x180040ef2  mov     r8, rdi; unsigned int
0x180040ef5  mov     edx, 20D6h; void *
0x180040efa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040eff  cmp     esi, 88890008h
0x180040f05  jnz     loc_180040F95
0x180040f0b  mov     r8, r14; struct tWAVEFORMATEX *
0x180040f0e  mov     rcx, [rbx+630h]; this
0x180040f15  call    ?TryAddFormat@CEndpointCharacteristics@@QEAAJPEAVEffectPack@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::TryAddFormat(EffectPack *,tWAVEFORMATEX const *)
0x180040f1a  mov     esi, eax
0x180040f1c  test    eax, eax
0x180040f1e  jns     short loc_180040F49
0x180040f20  mov     rcx, [rbp+5Fh]; this
0x180040f24  mov     r9d, eax; char *
0x180040f27  mov     r8, rdi; unsigned int
0x180040f2a  mov     edx, 2198h; void *
0x180040f2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f34  nop
0x180040f35  xor     edx, edx
0x180040f37  mov     rcx, [rbx+630h]
0x180040f3e  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180040f43  nop
0x180040f44  jmp     loc_180040DC7
0x180040f49  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm6
0x180040f4e  mov     dword ptr [rsp+0E0h+var_C0], r12d; int
0x180040f53  mov     r9d, [rbp+57h+arg_8]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180040f57  lea     r8, [rbp+57h+var_90]; struct _GUID *
0x180040f5b  mov     rdx, r14; struct tWAVEFORMATEX *
0x180040f5e  mov     rcx, rbx; this
0x180040f61  call    ?ConfirmDeviceFormat@EffectPack@@AEAAJPEBUtWAVEFORMATEX@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@H@Z; EffectPack::ConfirmDeviceFormat(tWAVEFORMATEX const *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int)
0x180040f66  mov     esi, eax
0x180040f68  test    eax, eax
0x180040f6a  jns     short loc_180040FBE
0x180040f6c  mov     rcx, [rbp+5Fh]; this
0x180040f70  mov     r9d, eax; char *
0x180040f73  mov     r8, rdi; unsigned int
0x180040f76  mov     edx, 219Bh; void *
0x180040f7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f80  nop
0x180040f81  xor     edx, edx
0x180040f83  mov     rcx, [rbx+630h]
0x180040f8a  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180040f8f  nop
0x180040f90  jmp     loc_180040DC7
0x180040f95  mov     rcx, [rbp+5Fh]; this
0x180040f99  mov     r9d, esi; char *
0x180040f9c  mov     r8, rdi; unsigned int
0x180040f9f  mov     edx, 219Fh; void *
0x180040fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040fa9  nop
0x180040faa  xor     edx, edx
0x180040fac  mov     rcx, [rbx+630h]
0x180040fb3  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180040fb8  nop
0x180040fb9  jmp     loc_180040DC7
0x180040fbe  mov     [rbp+57h+pv], r12
0x180040fc2  lea     rax, [rbp+57h+pv]
0x180040fc6  mov     qword ptr [rbp+57h+var_90.Data1], rax
0x180040fca  mov     qword ptr [rbp+57h+var_90.Data4], r12
0x180040fce  mov     [rbp+57h+var_80], 1
0x180040fd2  mov     [rsp+0E0h+var_B0], r12; pv
0x180040fd7  mov     [rsp+0E0h+var_B8], r12; unsigned int *
0x180040fdc  mov     [rsp+0E0h+var_C0], r12; int
0x180040fe1  lea     r9, [rbp+57h+var_90.Data4]; struct tWAVEFORMATEX **
0x180040fe5  xor     r8d, r8d; int
0x180040fe8  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180040fea  mov     rcx, rbx; this
0x180040fed  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x180040ff2  mov     esi, eax
0x180040ff4  cmp     [rbp+57h+var_80], r12b
0x180040ff8  jz      short loc_180041013
0x180040ffa  mov     r8, qword ptr [rbp+57h+var_90.Data1]
0x180040ffe  mov     rcx, [r8]; pv
0x180041001  mov     rdx, qword ptr [rbp+57h+var_90.Data4]
0x180041005  mov     [r8], rdx
0x180041008  test    rcx, rcx
0x18004100b  jz      short loc_180041013
0x18004100d  call    cs:__imp_CoTaskMemFree
0x180041013  test    esi, esi
0x180041015  jns     short loc_180041054
0x180041017  mov     rcx, [rbp+5Fh]; this
0x18004101b  mov     r9d, esi; char *
0x18004101e  mov     r8, rdi; unsigned int
0x180041021  mov     edx, 21A4h; void *
0x180041026  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004102b  nop
0x18004102c  mov     rcx, [rbp+57h+pv]; pv
0x180041030  mov     [rbp+57h+pv], r12
0x180041034  test    rcx, rcx
0x180041037  jz      short loc_180041040
0x180041039  call    cs:__imp_CoTaskMemFree
0x18004103f  nop
0x180041040  xor     edx, edx
0x180041042  mov     rcx, [rbx+630h]
0x180041049  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x18004104e  nop
0x18004104f  jmp     loc_180040DC7
0x180041054  mov     r9, r14; struct tWAVEFORMATEX *
0x180041057  mov     r8d, [rbp+57h+arg_8]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18004105b  xor     edx, edx; bool
0x18004105d  mov     rcx, [rbx+630h]; this
0x180041064  call    ?UpdateDeviceFormatEPProperty@CEndpointCharacteristics@@QEAAJ_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::UpdateDeviceFormatEPProperty(bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)
0x180041069  mov     esi, eax
0x18004106b  test    eax, eax
0x18004106d  jns     short loc_1800410AC
0x18004106f  mov     rcx, [rbp+5Fh]; this
0x180041073  mov     r9d, eax; char *
0x180041076  mov     r8, rdi; unsigned int
0x180041079  mov     edx, 21A7h; void *
0x18004107e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041083  nop
0x180041084  mov     rcx, [rbp+57h+pv]; pv
0x180041088  mov     [rbp+57h+pv], r12
0x18004108c  test    rcx, rcx
0x18004108f  jz      short loc_180041098
0x180041091  call    cs:__imp_CoTaskMemFree
0x180041097  nop
0x180041098  xor     edx, edx
0x18004109a  mov     rcx, [rbx+630h]
0x1800410a1  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x1800410a6  nop
0x1800410a7  jmp     loc_180040DC7
0x1800410ac  mov     [rbp+57h+var_60], rbx
0x1800410b0  lea     rax, [rbp+57h+arg_8]
0x1800410b4  mov     [rbp+57h+var_58], rax
0x1800410b8  lea     rax, [rbp+57h+pv]
0x1800410bc  mov     [rbp+57h+var_50], rax
0x1800410c0  mov     byte ptr [rbp+57h+var_48], 1
0x1800410c4  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800410c6  mov     rcx, rbx; this
0x1800410c9  call    ?DeriveAndCacheMixFormatsForConnector@EffectPack@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::DeriveAndCacheMixFormatsForConnector(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x1800410ce  mov     esi, eax
0x1800410d0  test    eax, eax
0x1800410d2  jns     short loc_180041140
0x1800410d4  mov     rcx, [rbp+5Fh]; this
0x1800410d8  mov     r9d, eax; char *
0x1800410db  mov     r8, rdi; unsigned int
0x1800410de  mov     edx, 21B0h; void *
0x1800410e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800410e8  nop
0x1800410e9  mov     r9, [rbp+57h+pv]; struct tWAVEFORMATEX *
0x1800410ed  mov     r8d, [rbp+57h+arg_8]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800410f1  xor     edx, edx; bool
0x1800410f3  mov     rcx, [rbx+630h]; this
0x1800410fa  call    ?UpdateDeviceFormatEPProperty@CEndpointCharacteristics@@QEAAJ_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::UpdateDeviceFormatEPProperty(bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)
0x1800410ff  mov     rcx, [rbp+5Fh]; this
0x180041103  test    eax, eax
0x180041105  jns     short loc_180041118
0x180041107  mov     r9d, eax; char *
0x18004110a  mov     r8, rdi; unsigned int
0x18004110d  mov     edx, 21ACh; void *
0x180041112  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041117  nop
0x180041118  mov     rcx, [rbp+57h+pv]; pv
0x18004111c  mov     [rbp+57h+pv], r12
0x180041120  test    rcx, rcx
0x180041123  jz      short loc_18004112C
0x180041125  call    cs:__imp_CoTaskMemFree
0x18004112b  nop
0x18004112c  xor     edx, edx
0x18004112e  mov     rcx, [rbx+630h]
0x180041135  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x18004113a  nop
0x18004113b  jmp     loc_180040DC7
0x180041140  mov     edx, 3; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180041145  mov     rcx, rbx; this
0x180041148  call    ?DeriveAndCacheMixFormatsForConnector@EffectPack@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::DeriveAndCacheMixFormatsForConnector(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18004114d  mov     rcx, [rbp+5Fh]; this
0x180041151  test    eax, eax
0x180041153  jns     short loc_180041165
0x180041155  mov     r9d, eax; char *
0x180041158  mov     r8, rdi; unsigned int
0x18004115b  mov     edx, 21B4h; void *
0x180041160  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041165  mov     [rbp+57h+arg_18], r12
0x180041169  lea     rdx, [rbp+57h+arg_18]; __int64 *
0x18004116d  mov     rcx, [rbx+630h]; this
0x180041174  call    ?SetProcessingPeriod@CEndpointCharacteristics@@QEAAJAEB_J@Z; CEndpointCharacteristics::SetProcessingPeriod(__int64 const &)
0x180041179  mov     esi, eax
0x18004117b  test    eax, eax
0x18004117d  jns     short loc_1800411EB
0x18004117f  mov     rcx, [rbp+5Fh]; this
0x180041183  mov     r9d, eax; char *
  ... truncated ...
```
