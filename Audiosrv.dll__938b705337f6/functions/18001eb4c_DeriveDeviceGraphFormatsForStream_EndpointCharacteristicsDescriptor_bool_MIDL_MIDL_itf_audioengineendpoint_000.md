# DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)

- ea: `0x18001eb4c`
- end: `0x18001f24f`
- name: `?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z`
- size: `1795`
- prototype: `__int64 __usercall@<rax>(struct EndpointCharacteristicsDescriptor *@<rcx>, bool@<dl>, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@<r8d>, enum _AUDCLNT_SHAREMODE@<r9d>, unsigned int, struct _GUID *, struct _GUID *, struct _GUID *, struct tWAVEFORMATEX *, struct tWAVEFORMATEX **, struct tWAVEFORMATEX **, struct tWAVEFORMATEX **, struct tWAVEFORMATEX **)`
- caller_count: `7`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d7b4`
- `0x180073990`
- `0x180078a08`
- `0x1800c1ca4`
- `0x1800f76f4`
- `0x1800f7e20`
- `0x1800f97a0`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x18001e1b8`
- `0x18001e850`
- `0x18001eb4c`
- `0x18001f258`
- `0x18001f6b0`
- `0x18001fa40`
- `0x180022fb0`
- `0x180029d8c`
- `0x18003cee0`
- `0x18003f11c`
- `0x180040938`
- `0x18004f728`
- `0x18005b174`
- `0x18006f318`
- `0x1800cf8c0`
- `0x1800d0740`
- `0x1800d074c`
- `0x1800d2588`
- `0x18011f588`
- `0x180143b30`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ecc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ecc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eeb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001efaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eeb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001efaf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ee50`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ee8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001efa0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ee50`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ee8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001efa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ed30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ed30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eda7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001edb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001edbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eda7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001edb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001edbd`

## string_xrefs

- `0x18001ee9e`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x18001ee76`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18001ef8a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18001f0b0`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DeriveDeviceGraphFormatsForStream(
        CEndpointCharacteristics **a1,
        char a2,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a3,
        enum _AUDCLNT_SHAREMODE a4,
        unsigned int a5,
        IAudioMediaType *a6,
        struct _GUID *a7,
        struct _GUID *a8,
        struct tWAVEFORMATEX *a9,
        struct tWAVEFORMATEX **a10,
        struct tWAVEFORMATEX **a11,
        struct tWAVEFORMATEX **a12,
        struct tWAVEFORMATEX **a13)
{
  struct tWAVEFORMATEX *v15; // rbx
  struct tWAVEFORMATEX *v16; // rdi
  signed int AudioMediaType; // esi
  struct _GUID *v18; // r13
  struct _RTL_CRITICAL_SECTION *v19; // r15
  unsigned int i; // r14d
  void *v21; // rsi
  __int64 v22; // r14
  struct tWAVEFORMATEX *v23; // rax
  struct tWAVEFORMATEX *v24; // rax
  struct tWAVEFORMATEX *v25; // rax
  struct tWAVEFORMATEX *v26; // rax
  struct tWAVEFORMATEX *v27; // rax
  unsigned int v28; // r14d
  int v30; // eax
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // rdx
  bool v34; // sf
  int v35; // eax
  const struct tWAVEFORMATEX *v36; // rax
  const struct tWAVEFORMATEX *v37; // rax
  const struct tWAVEFORMATEX *v38; // rax
  struct tWAVEFORMATEX **v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  struct tWAVEFORMATEX *v42; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  struct tWAVEFORMATEX *v45; // [rsp+58h] [rbp-A8h] BYREF
  struct IMMDevice *v46[2]; // [rsp+60h] [rbp-A0h] BYREF
  IAudioMediaType *ppIAudioMediaType[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID Buf2; // [rsp+80h] [rbp-80h] BYREF
  void *Buf1[2]; // [rsp+90h] [rbp-70h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+A0h] [rbp-60h] BYREF
  struct tWAVEFORMATEX **v51; // [rsp+B8h] [rbp-48h]
  struct tWAVEFORMATEX **v52; // [rsp+C0h] [rbp-40h]
  struct tWAVEFORMATEX **v53; // [rsp+C8h] [rbp-38h]
  struct tWAVEFORMATEX **v54; // [rsp+D0h] [rbp-30h]
  struct _GUID v55; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v56; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  ppIAudioMediaType[0] = a6;
  Buf1[0] = a8;
  v53 = a10;
  v52 = a11;
  v54 = a12;
  v51 = a13;
  pv = 0;
  v15 = 0;
  v42 = 0;
  v16 = 0;
  v45 = 0;
  Src = 0;
  if ( a4 == AUDCLNT_SHAREMODE_EXCLUSIVE )
  {
    AudioMediaType = CloneWaveFormat(a9, &v42);
    if ( AudioMediaType < 0 )
      goto LABEL_46;
    v46[0] = 0;
    wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>((char *)*a1 + 40, v46);
    if ( (unsigned int)IsSPDIFFormat(a9) && CEndpointCharacteristics::IsSPDIFEndpoint(*a1) )
      AudioMediaType = GetAcceptableSPDIFTypeForDevice(v46[0], a9, (struct tWAVEFORMATEX **)&pv, 0) != 0
                     ? 0x88890008
                     : 0;
    else
      AudioMediaType = CloneWaveFormat(a9, (struct tWAVEFORMATEX **)&pv);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v46);
    v34 = AudioMediaType < 0;
LABEL_33:
    if ( !v34 )
    {
      v15 = v42;
      AudioMediaType = CloneWaveFormat(v42, (struct tWAVEFORMATEX **)&Src);
      goto LABEL_15;
    }
LABEL_46:
    v15 = v42;
    goto LABEL_17;
  }
  if ( a3 == eOffloadConnector )
  {
    *(struct _GUID *)ppIAudioMediaType = *a7;
    AudioMediaType = DeriveOffloadConnectorFormatFromStreamFormat(
                       a1,
                       a9,
                       0,
                       (struct _GUID *)ppIAudioMediaType,
                       (struct tWAVEFORMATEX *)v39,
                       a5,
                       (struct tWAVEFORMATEX **)&pv);
    if ( AudioMediaType < 0 )
      goto LABEL_17;
    AudioMediaType = CloneWaveFormat((const struct tWAVEFORMATEX *)pv, &v45);
    v16 = v45;
    ConvertPCMWfxToIEEEFloat(v45);
    if ( AudioMediaType < 0 )
      goto LABEL_17;
    AudioMediaType = CloneWaveFormat(v16, &v42);
    v34 = AudioMediaType < 0;
    goto LABEL_33;
  }
  if ( a2 )
  {
    *(struct _GUID *)ppIAudioMediaType = *a8;
    *(struct _GUID *)Buf1 = *a7;
    Buf2 = *(struct _GUID *)&a6->lpVtbl;
    AudioMediaType = DeriveConnectorFormatFromStreamFormat(
                       a1,
                       a3,
                       (IAudioMediaType *)a9,
                       &Buf2,
                       (struct _GUID *)Buf1,
                       (struct _GUID *)ppIAudioMediaType,
                       1,
                       (struct tWAVEFORMATEX **)&pv);
    if ( AudioMediaType < 0 )
      goto LABEL_17;
    ppIAudioMediaType[0] = 0;
    v46[0] = 0;
    Buf1[0] = 0;
    *(_QWORD *)&Buf2.Data1 = 0;
    AudioMediaType = CreateAudioMediaType(
                       (const WAVEFORMATEX *)pv,
                       *((unsigned __int16 *)pv + 8) + 18,
                       ppIAudioMediaType);
    if ( AudioMediaType >= 0 )
    {
      v55 = *a7;
      AudioMediaType = EffectPack::DeriveDevicePipeFormatFromConnectorFormat(
                         a1[1],
                         &v55,
                         a3,
                         ppIAudioMediaType[0],
                         (struct IAudioMediaType **)v46);
      if ( AudioMediaType >= 0 )
      {
        v55 = *a7;
        AudioMediaType = EffectPack::DeriveMixFormatFromDevicePipeFormat(
                           a1[1],
                           &v55,
                           a3,
                           (struct IAudioMediaType *)v46[0],
                           (struct IAudioMediaType **)&Buf2,
                           (struct IAudioMediaType **)Buf1);
        if ( AudioMediaType >= 0 )
        {
          v36 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(struct IMMDevice *))v46[0]->lpVtbl->GetId)(v46[0]);
          AudioMediaType = CloneWaveFormat(v36, (struct tWAVEFORMATEX **)&Src);
          if ( AudioMediaType >= 0 )
          {
            v37 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&Buf2.Data1 + 40LL))(*(_QWORD *)&Buf2.Data1);
            AudioMediaType = CloneWaveFormat(v37, &v45);
            if ( AudioMediaType >= 0 )
            {
              if ( Buf1[0] )
                v38 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)Buf1[0] + 40LL))(Buf1[0]);
              else
                v38 = (const struct tWAVEFORMATEX *)Src;
              AudioMediaType = CloneWaveFormat(v38, &v42);
              v15 = v42;
            }
            v16 = v45;
          }
        }
      }
    }
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&Buf2);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(Buf1);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v46);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(ppIAudioMediaType);
LABEL_15:
    if ( AudioMediaType >= 0 )
    {
      v24 = (struct tWAVEFORMATEX *)pv;
      pv = 0;
      *v51 = v24;
      v25 = v15;
      v15 = 0;
      *v52 = v25;
      v26 = v16;
      v16 = 0;
      *v53 = v26;
      v27 = (struct tWAVEFORMATEX *)Src;
      Src = 0;
      *v54 = v27;
    }
    goto LABEL_17;
  }
  Buf2 = *a8;
  AudioMediaType = GetDeviceDefaults(
                     a1,
                     (unsigned int)a3,
                     &Buf2,
                     (struct tWAVEFORMATEX **)&pv,
                     (struct tWAVEFORMATEX **)&Src,
                     0,
                     0);
  if ( AudioMediaType >= 0 )
  {
    if ( (v18 = (struct _GUID *)ppIAudioMediaType[0],
          *(_OWORD *)ppIAudioMediaType = *(_OWORD *)ppIAudioMediaType[0],
          !EffectPack::CanProcessingModeBeParameterized(a1[1], (struct _GUID *)ppIAudioMediaType, a3))
      && memcmp_0(Buf1[0], &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u)
      || (*(struct _GUID *)ppIAudioMediaType = *v18,
          AudioMediaType = EffectPack::GetMixFormat(a1[1], a3, (struct _GUID *)ppIAudioMediaType, &v45),
          v16 = v45,
          AudioMediaType >= 0) )
    {
      ppIAudioMediaType[0] = (IAudioMediaType *)*a1;
      v15 = 0;
      v42 = 0;
      v19 = (struct _RTL_CRITICAL_SECTION *)&ppIAudioMediaType[0][1024];
      EnterCriticalSection((LPCRITICAL_SECTION)&ppIAudioMediaType[0][1024]);
      Buf1[0] = v19;
      v55 = 0;
      v56 = 0;
      Buf2 = *v18;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xA )
        {
          v28 = -2147023728;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BE2,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)0x80070490LL,
            v40);
          goto LABEL_27;
        }
        if ( !memcmp_0((char *)&unk_1801870E0 + 16 * i, &Buf2, 0x10u) )
          break;
      }
      v55 = (struct _GUID)PKEY_AudioEngine_SignalProcessingMode_Specific_StreamGroupFormat;
      v30 = 602;
      if ( a3 != eKeywordDetectorConnector )
        v30 = 2;
      v56 = i + v30;
      memset(&pvar, 0, sizeof(pvar));
      v31 = (*((__int64 (__fastcall **)(struct IAudioMediaTypeVtbl *, struct _GUID *, struct tagPROPVARIANT *))ppIAudioMediaType[0][9].lpVtbl->QueryInterface
             + 5))(
              ppIAudioMediaType[0][9].lpVtbl,
              &v55,
              &pvar);
      v28 = v31;
      if ( v31 < 0 )
      {
        v32 = (unsigned int)v31;
        v33 = 7141;
        goto LABEL_26;
      }
      if ( pvar.vt == 65 && (unsigned int)IsValidWfxBlob(&pvar) )
      {
        if ( (unsigned int)ValidateUncompressedWaveFormatEx((const struct tWAVEFORMATEX *)pvar.bstrblobVal.pData) )
        {
          v28 = -2004287480;
          v32 = 2290679816LL;
          v33 = 7145;
LABEL_26:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v33,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)v32,
            v40);
          PropVariantClear((PROPVARIANT *)&pvar);
LABEL_27:
          if ( v19 )
            LeaveCriticalSection(v19);
LABEL_29:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x339,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)v28,
            v41);
          goto LABEL_18;
        }
        v35 = CloneWaveFormat((const struct tWAVEFORMATEX *)pvar.bstrblobVal.pData, &v42);
        v28 = v35;
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BEB,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)(unsigned int)v35,
            v40);
          PropVariantClear((PROPVARIANT *)&pvar);
          if ( v19 )
            LeaveCriticalSection(v19);
          v15 = v42;
          goto LABEL_29;
        }
        v15 = v42;
      }
      PropVariantClear((PROPVARIANT *)&pvar);
      if ( v19 )
        LeaveCriticalSection(v19);
      if ( !v15 )
      {
        v21 = Src;
        v22 = *((unsigned __int16 *)Src + 8);
        v23 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(v22 + 18);
        v15 = v23;
        if ( v23 )
        {
          memcpy_0(v23, v21, v22 + 18);
          AudioMediaType = 0;
        }
        else
        {
          AudioMediaType = -2147024882;
        }
      }
      goto LABEL_15;
    }
  }
LABEL_17:
  v28 = AudioMediaType;
LABEL_18:
  CoTaskMemFree(Src);
  CoTaskMemFree(v16);
  CoTaskMemFree(v15);
  CoTaskMemFree(pv);
  return v28;
}

```

## disassembly

```asm
0x18001eb4c  mov     [rsp-8+arg_8], rbx
0x18001eb51  push    rbp
0x18001eb52  push    rsi
0x18001eb53  push    rdi
0x18001eb54  push    r12
0x18001eb56  push    r13
0x18001eb58  push    r14
0x18001eb5a  push    r15
0x18001eb5c  lea     rbp, [rsp-10h]
0x18001eb61  sub     rsp, 110h
0x18001eb68  mov     rax, cs:__security_cookie
0x18001eb6f  xor     rax, rsp
0x18001eb72  mov     [rbp+40h+var_40], rax
0x18001eb76  mov     r12d, r8d
0x18001eb79  mov     r14, rcx
0x18001eb7c  mov     rax, [rbp+40h+arg_28]
0x18001eb80  mov     [rsp+140h+ppIAudioMediaType], rax
0x18001eb85  mov     r13, [rbp+40h+arg_30]
0x18001eb8c  mov     rcx, [rbp+40h+arg_38]
0x18001eb93  mov     [rbp+40h+Buf1], rcx
0x18001eb97  mov     r15, [rbp+40h+arg_40]
0x18001eb9e  mov     r8, [rbp+40h+arg_48]
0x18001eba5  mov     [rbp+40h+var_78], r8
0x18001eba9  mov     r8, [rbp+40h+arg_50]
0x18001ebb0  mov     [rbp+40h+var_80], r8
0x18001ebb4  mov     r8, [rbp+40h+arg_58]
0x18001ebbb  mov     [rbp+40h+var_70], r8
0x18001ebbf  mov     r8, [rbp+40h+arg_60]
0x18001ebc6  mov     [rbp+40h+var_88], r8
0x18001ebca  xor     r8d, r8d; struct _GUID
0x18001ebcd  mov     [rsp+140h+pv], r8
0x18001ebd2  mov     ebx, r8d
0x18001ebd5  mov     [rsp+140h+var_100], rbx
0x18001ebda  mov     edi, r8d
0x18001ebdd  mov     [rsp+140h+var_E8], r8
0x18001ebe2  mov     [rsp+140h+Src], r8
0x18001ebe7  cmp     r9d, 1
0x18001ebeb  jz      loc_18001EFBF
0x18001ebf1  cmp     r12d, 1
0x18001ebf5  jz      loc_18001EEBF
0x18001ebfb  movaps  xmm0, xmmword ptr [rcx]
0x18001ebfe  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x18001ec01  test    dl, dl
0x18001ec03  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001ec06  jnz     loc_18001F0C6
0x18001ec0c  movdqa  [rbp+40h+Buf2], xmm0
0x18001ec11  mov     [rsp+140h+var_110], r8; __int64 *
0x18001ec16  mov     [rsp+140h+var_118], r8; __int64 *
0x18001ec1b  lea     rax, [rsp+140h+Src]
0x18001ec20  mov     [rsp+140h+var_120], rax; int
0x18001ec25  lea     r9, [rsp+140h+pv]; struct tWAVEFORMATEX **
0x18001ec2a  lea     r8, [rbp+40h+Buf2]; struct _GUID
0x18001ec2e  call    ?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z; GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)
0x18001ec33  mov     esi, eax
0x18001ec35  test    eax, eax
0x18001ec37  js      loc_18001ED95
0x18001ec3d  mov     r13, [rsp+140h+ppIAudioMediaType]
0x18001ec42  movaps  xmm0, xmmword ptr [r13+0]
0x18001ec47  movdqa  xmmword ptr [rsp+140h+ppIAudioMediaType], xmm0
0x18001ec4d  mov     r8d, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001ec50  lea     rdx, [rsp+140h+ppIAudioMediaType]; struct _GUID
0x18001ec55  mov     rcx, [r14+8]; this
0x18001ec59  call    ?CanProcessingModeBeParameterized@EffectPack@@QEAA_NU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::CanProcessingModeBeParameterized(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18001ec5e  test    al, al
0x18001ec60  jnz     short loc_18001EC7A
0x18001ec62  lea     r8d, [rdi+10h]; Size
0x18001ec66  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x18001ec6d  mov     rcx, [rbp+40h+Buf1]; Buf1
0x18001ec71  call    memcmp_0
0x18001ec76  test    eax, eax
0x18001ec78  jnz     short loc_18001ECAA
0x18001ec7a  movaps  xmm0, xmmword ptr [r13+0]
0x18001ec7f  movdqa  xmmword ptr [rsp+140h+ppIAudioMediaType], xmm0
0x18001ec85  lea     r9, [rsp+140h+var_E8]; struct tWAVEFORMATEX **
0x18001ec8a  lea     r8, [rsp+140h+ppIAudioMediaType]; struct _GUID
0x18001ec8f  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001ec92  mov     rcx, [r14+8]; this
0x18001ec96  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001ec9b  mov     esi, eax
0x18001ec9d  mov     rdi, [rsp+140h+var_E8]
0x18001eca2  test    eax, eax
0x18001eca4  js      loc_18001ED95
0x18001ecaa  mov     rax, [r14]
0x18001ecad  mov     [rsp+140h+ppIAudioMediaType], rax
0x18001ecb2  xor     ebx, ebx
0x18001ecb4  mov     [rsp+140h+var_100], rbx
0x18001ecb9  lea     r15, [rax+2000h]
0x18001ecc0  mov     rcx, r15; lpCriticalSection
0x18001ecc3  call    cs:__imp_EnterCriticalSection
0x18001ecc9  mov     [rbp+40h+Buf1], r15
0x18001eccd  xorps   xmm0, xmm0
0x18001ecd0  xor     eax, eax
0x18001ecd2  movups  xmmword ptr [rbp+40h+var_60.Data1], xmm0
0x18001ecd6  mov     [rbp+40h+var_50], eax
0x18001ecd9  movaps  xmm0, xmmword ptr [r13+0]
0x18001ecde  movdqa  [rbp+40h+Buf2], xmm0
0x18001ece3  xor     r14d, r14d
0x18001ece6  cmp     r14d, 0Ah
0x18001ecea  jnb     loc_18001F0A3
0x18001ecf0  mov     ecx, r14d
0x18001ecf3  shl     rcx, 4
0x18001ecf7  lea     rax, unk_1801870E0
0x18001ecfe  add     rcx, rax; Buf1
0x18001ed01  mov     r8d, 10h; Size
0x18001ed07  lea     rdx, [rbp+40h+Buf2]; Buf2
0x18001ed0b  call    memcmp_0
0x18001ed10  test    eax, eax
0x18001ed12  jz      loc_18001EDED
0x18001ed18  inc     r14d
0x18001ed1b  jmp     short loc_18001ECE6
0x18001ed1d  test    rbx, rbx
0x18001ed20  jnz     short loc_18001ED53
0x18001ed22  mov     rsi, [rsp+140h+Src]
0x18001ed27  movzx   r14d, word ptr [rsi+10h]
0x18001ed2c  lea     rcx, [r14+12h]; cb
0x18001ed30  call    cs:__imp_CoTaskMemAlloc
0x18001ed36  mov     rbx, rax
0x18001ed39  test    rax, rax
0x18001ed3c  jz      loc_18001EF4B
0x18001ed42  lea     r8, [r14+12h]; Size
0x18001ed46  mov     rdx, rsi; Src
0x18001ed49  mov     rcx, rax; void *
0x18001ed4c  call    memcpy_0
0x18001ed51  xor     esi, esi
0x18001ed53  test    esi, esi
0x18001ed55  js      short loc_18001ED95
0x18001ed57  mov     rax, [rsp+140h+pv]
0x18001ed5c  mov     [rsp+140h+pv], 0
0x18001ed65  mov     rcx, [rbp+40h+var_88]
0x18001ed69  mov     [rcx], rax
0x18001ed6c  mov     rax, rbx
0x18001ed6f  xor     ebx, ebx
0x18001ed71  mov     rcx, [rbp+40h+var_80]
0x18001ed75  mov     [rcx], rax
0x18001ed78  mov     rax, rdi
0x18001ed7b  xor     edi, edi
0x18001ed7d  mov     rcx, [rbp+40h+var_78]
0x18001ed81  mov     [rcx], rax
0x18001ed84  mov     rax, [rsp+140h+Src]
0x18001ed89  mov     [rsp+140h+Src], rbx
0x18001ed8e  mov     rcx, [rbp+40h+var_70]
0x18001ed92  mov     [rcx], rax
0x18001ed95  mov     r14d, esi
0x18001ed98  mov     rcx, [rsp+140h+Src]; pv
0x18001ed9d  call    cs:__imp_CoTaskMemFree
0x18001eda3  nop
0x18001eda4  mov     rcx, rdi; pv
0x18001eda7  call    cs:__imp_CoTaskMemFree
0x18001edad  nop
0x18001edae  mov     rcx, rbx; pv
0x18001edb1  call    cs:__imp_CoTaskMemFree
0x18001edb7  nop
0x18001edb8  mov     rcx, [rsp+140h+pv]; pv
0x18001edbd  call    cs:__imp_CoTaskMemFree
0x18001edc3  mov     eax, r14d
0x18001edc6  mov     rcx, [rbp+40h+var_40]
0x18001edca  xor     rcx, rsp; StackCookie
0x18001edcd  call    __security_check_cookie
0x18001edd2  mov     rbx, [rsp+140h+arg_8]
0x18001edda  add     rsp, 110h
0x18001ede1  pop     r15
0x18001ede3  pop     r14
0x18001ede5  pop     r13
0x18001ede7  pop     r12
0x18001ede9  pop     rdi
0x18001edea  pop     rsi
0x18001edeb  pop     rbp
0x18001edec  retn
0x18001eded  movups  xmm0, cs:PKEY_AudioEngine_SignalProcessingMode_Specific_StreamGroupFormat
0x18001edf4  movdqu  xmmword ptr [rbp+40h+var_60.Data1], xmm0
0x18001edf9  mov     eax, 25Ah
0x18001edfe  mov     ecx, 2
0x18001ee03  cmp     r12d, 3
0x18001ee07  cmovnz  eax, ecx
0x18001ee0a  add     eax, r14d
0x18001ee0d  mov     [rbp+40h+var_50], eax
0x18001ee10  xorps   xmm0, xmm0
0x18001ee13  xor     eax, eax
0x18001ee15  movups  xmmword ptr [rbp+40h+pvar], xmm0
0x18001ee19  mov     [rbp+40h+var_90], rax
0x18001ee1d  mov     rcx, [rsp+140h+ppIAudioMediaType]
0x18001ee22  mov     rcx, [rcx+48h]
0x18001ee26  mov     rax, [rcx]
0x18001ee29  lea     r8, [rbp+40h+pvar]
0x18001ee2d  lea     rdx, [rbp+40h+var_60]
0x18001ee31  mov     rax, [rax+28h]
0x18001ee35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee3a  mov     r14d, eax
0x18001ee3d  test    eax, eax
0x18001ee3f  js      short loc_18001EE6E
0x18001ee41  cmp     word ptr [rbp+40h+pvar], 41h ; 'A'
0x18001ee46  jz      loc_18001F04F
0x18001ee4c  lea     rcx, [rbp+40h+pvar]; pvar
0x18001ee50  call    cs:__imp_PropVariantClear
0x18001ee56  nop
0x18001ee57  test    r15, r15
0x18001ee5a  jz      loc_18001ED1D
0x18001ee60  mov     rcx, r15; lpCriticalSection
0x18001ee63  call    cs:__imp_LeaveCriticalSection
0x18001ee69  jmp     loc_18001ED1D
0x18001ee6e  mov     r9d, eax; char *
0x18001ee71  mov     edx, 1BE5h; void *
0x18001ee76  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18001ee7d  mov     rcx, [rbp+48h]; this
0x18001ee81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee86  nop
0x18001ee87  lea     rcx, [rbp+40h+pvar]; pvar
0x18001ee8b  call    cs:__imp_PropVariantClear
0x18001ee91  nop
0x18001ee92  test    r15, r15
0x18001ee95  jnz     short loc_18001EEB4
0x18001ee97  mov     rcx, [rbp+48h]; this
0x18001ee9b  mov     r9d, r14d; char *
0x18001ee9e  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001eea5  mov     edx, 339h; void *
0x18001eeaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eeaf  jmp     loc_18001ED98
0x18001eeb4  mov     rcx, r15; lpCriticalSection
0x18001eeb7  call    cs:__imp_LeaveCriticalSection
0x18001eebd  jmp     short loc_18001EE97
0x18001eebf  movaps  xmm0, xmmword ptr [r13+0]
0x18001eec4  movdqa  xmmword ptr [rsp+140h+ppIAudioMediaType], xmm0
0x18001eeca  lea     rax, [rsp+140h+pv]
0x18001eecf  mov     [rsp+140h+var_110], rax; struct tWAVEFORMATEX **
0x18001eed4  mov     eax, [rbp+40h+arg_20]
0x18001eed7  mov     dword ptr [rsp+140h+var_118], eax; unsigned int
0x18001eedb  lea     r9, [rsp+140h+ppIAudioMediaType]; struct _GUID
0x18001eee0  mov     rdx, r15; struct tWAVEFORMATEX *
0x18001eee3  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x18001eee6  call    ?DeriveOffloadConnectorFormatFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@PEAUtWAVEFORMATEX@@U_GUID@@22KPEAPEAU2@@Z; DeriveOffloadConnectorFormatFromStreamFormat(EndpointCharacteristicsDescriptor *,tWAVEFORMATEX *,_GUID,_GUID,_GUID,ulong,tWAVEFORMATEX * *)
0x18001eeeb  mov     esi, eax
0x18001eeed  test    eax, eax
0x18001eeef  js      loc_18001ED95
0x18001eef5  lea     rdx, [rsp+140h+var_E8]; struct tWAVEFORMATEX **
0x18001eefa  mov     rcx, [rsp+140h+pv]; Src
0x18001eeff  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001ef04  mov     esi, eax
0x18001ef06  mov     rdi, [rsp+140h+var_E8]
0x18001ef0b  mov     rcx, rdi; struct tWAVEFORMATEX *
0x18001ef0e  call    ?ConvertPCMWfxToIEEEFloat@@YAXPEAUtWAVEFORMATEX@@@Z; ConvertPCMWfxToIEEEFloat(tWAVEFORMATEX *)
0x18001ef13  test    esi, esi
0x18001ef15  js      loc_18001ED95
0x18001ef1b  lea     rdx, [rsp+140h+var_100]; struct tWAVEFORMATEX **
0x18001ef20  mov     rcx, rdi; Src
0x18001ef23  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001ef28  mov     esi, eax
0x18001ef2a  test    eax, eax
0x18001ef2c  js      loc_18001F045
0x18001ef32  lea     rdx, [rsp+140h+Src]; struct tWAVEFORMATEX **
0x18001ef37  mov     rbx, [rsp+140h+var_100]
0x18001ef3c  mov     rcx, rbx; Src
0x18001ef3f  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001ef44  mov     esi, eax
0x18001ef46  jmp     loc_18001ED53
0x18001ef4b  mov     esi, 8007000Eh
0x18001ef50  jmp     loc_18001ED53
0x18001ef55  lea     rcx, [rbp+40h+Buf2]
0x18001ef59  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ef5e  nop
0x18001ef5f  lea     rcx, [rbp+40h+Buf1]
0x18001ef63  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ef68  nop
0x18001ef69  lea     rcx, [rsp+140h+var_E0]
0x18001ef6e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ef73  nop
0x18001ef74  lea     rcx, [rsp+140h+ppIAudioMediaType]
0x18001ef79  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ef7e  jmp     loc_18001ED53
0x18001ef83  mov     rcx, [rbp+48h]; this
0x18001ef87  mov     r9d, eax; char *
0x18001ef8a  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18001ef91  mov     edx, 1BEBh; void *
0x18001ef96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef9b  nop
0x18001ef9c  lea     rcx, [rbp+40h+pvar]; pvar
0x18001efa0  call    cs:__imp_PropVariantClear
0x18001efa6  nop
0x18001efa7  test    r15, r15
0x18001efaa  jz      short loc_18001EFB5
0x18001efac  mov     rcx, r15; lpCriticalSection
0x18001efaf  call    cs:__imp_LeaveCriticalSection
0x18001efb5  mov     rbx, [rsp+140h+var_100]
0x18001efba  jmp     loc_18001EE97
0x18001efbf  lea     rdx, [rsp+140h+var_100]; struct tWAVEFORMATEX **
0x18001efc4  mov     rcx, r15; Src
0x18001efc7  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001efcc  mov     esi, eax
0x18001efce  test    eax, eax
0x18001efd0  js      short loc_18001F045
0x18001efd2  mov     [rsp+140h+var_E0], 0
0x18001efdb  mov     rcx, [r14]
0x18001efde  add     rcx, 28h ; '('
0x18001efe2  lea     rdx, [rsp+140h+var_E0]
0x18001efe7  call    ??$copy_to@VCAudioSession@@@?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAVCAudioSession@@@Z; wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(CAudioSession * *)
0x18001efec  mov     rcx, r15; struct tWAVEFORMATEX *
0x18001efef  call    ?IsSPDIFFormat@@YAHPEBUtWAVEFORMATEX@@@Z; IsSPDIFFormat(tWAVEFORMATEX const *)
0x18001eff4  test    eax, eax
0x18001eff6  jz      short loc_18001F025
0x18001eff8  mov     rcx, [r14]; this
0x18001effb  call    ?IsSPDIFEndpoint@CEndpointCharacteristics@@QEAA_NXZ; CEndpointCharacteristics::IsSPDIFEndpoint(void)
  ... truncated ...
```
