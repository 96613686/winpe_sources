# DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)

- ea: `0x18001ec9c`
- end: `0x18001f39f`
- name: `?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z`
- size: `1795`
- prototype: `__int64 __usercall@<rax>(struct EndpointCharacteristicsDescriptor *@<rcx>, bool@<dl>, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@<r8d>, enum _AUDCLNT_SHAREMODE@<r9d>, unsigned int, struct _GUID *, struct _GUID *, struct _GUID *, struct tWAVEFORMATEX *, struct tWAVEFORMATEX **, struct tWAVEFORMATEX **, struct tWAVEFORMATEX **, struct tWAVEFORMATEX **)`
- caller_count: `7`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d904`
- `0x180073490`
- `0x180078510`
- `0x1800c0154`
- `0x1800f7984`
- `0x1800f80b0`
- `0x1800f9a30`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x18001e308`
- `0x18001e9a0`
- `0x18001ec9c`
- `0x18001f3a8`
- `0x18001f800`
- `0x18001fb90`
- `0x180023100`
- `0x180029eec`
- `0x18003d040`
- `0x18003f28c`
- `0x180040aa8`
- `0x18004f298`
- `0x18005ace4`
- `0x18006ee18`
- `0x1800cd8d0`
- `0x1800ce750`
- `0x1800ce75c`
- `0x1800d0598`
- `0x18011f7d8`
- `0x180144440`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ee13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ee13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001efb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f007`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f0ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001efb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f007`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f0ff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001efa0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001efdb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f0f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001efa0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001efdb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f0f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ee80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ee80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eeed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eeed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef0d`

## string_xrefs

- `0x18001efee`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x18001efc6`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18001f0da`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18001f200`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
            (void *)0x1BE1,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)0x80070490LL,
            v40);
          goto LABEL_27;
        }
        if ( !memcmp_0(&qword_180188140[2 * i], &Buf2, 0x10u) )
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
        v33 = 7140;
        goto LABEL_26;
      }
      if ( pvar.vt == 65 && (unsigned int)IsValidWfxBlob(&pvar) )
      {
        if ( (unsigned int)ValidateUncompressedWaveFormatEx((const struct tWAVEFORMATEX *)pvar.bstrblobVal.pData) )
        {
          v28 = -2004287480;
          v32 = 2290679816LL;
          v33 = 7144;
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
            (void *)0x1BEA,
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
0x18001ec9c  mov     [rsp-8+arg_8], rbx
0x18001eca1  push    rbp
0x18001eca2  push    rsi
0x18001eca3  push    rdi
0x18001eca4  push    r12
0x18001eca6  push    r13
0x18001eca8  push    r14
0x18001ecaa  push    r15
0x18001ecac  lea     rbp, [rsp-10h]
0x18001ecb1  sub     rsp, 110h
0x18001ecb8  mov     rax, cs:__security_cookie
0x18001ecbf  xor     rax, rsp
0x18001ecc2  mov     [rbp+40h+var_40], rax
0x18001ecc6  mov     r12d, r8d
0x18001ecc9  mov     r14, rcx
0x18001eccc  mov     rax, [rbp+40h+arg_28]
0x18001ecd0  mov     [rsp+140h+ppIAudioMediaType], rax
0x18001ecd5  mov     r13, [rbp+40h+arg_30]
0x18001ecdc  mov     rcx, [rbp+40h+arg_38]
0x18001ece3  mov     [rbp+40h+Buf1], rcx
0x18001ece7  mov     r15, [rbp+40h+arg_40]
0x18001ecee  mov     r8, [rbp+40h+arg_48]
0x18001ecf5  mov     [rbp+40h+var_78], r8
0x18001ecf9  mov     r8, [rbp+40h+arg_50]
0x18001ed00  mov     [rbp+40h+var_80], r8
0x18001ed04  mov     r8, [rbp+40h+arg_58]
0x18001ed0b  mov     [rbp+40h+var_70], r8
0x18001ed0f  mov     r8, [rbp+40h+arg_60]
0x18001ed16  mov     [rbp+40h+var_88], r8
0x18001ed1a  xor     r8d, r8d; struct _GUID
0x18001ed1d  mov     [rsp+140h+pv], r8
0x18001ed22  mov     ebx, r8d
0x18001ed25  mov     [rsp+140h+var_100], rbx
0x18001ed2a  mov     edi, r8d
0x18001ed2d  mov     [rsp+140h+var_E8], r8
0x18001ed32  mov     [rsp+140h+Src], r8
0x18001ed37  cmp     r9d, 1
0x18001ed3b  jz      loc_18001F10F
0x18001ed41  cmp     r12d, 1
0x18001ed45  jz      loc_18001F00F
0x18001ed4b  movaps  xmm0, xmmword ptr [rcx]
0x18001ed4e  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x18001ed51  test    dl, dl
0x18001ed53  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001ed56  jnz     loc_18001F216
0x18001ed5c  movdqa  [rbp+40h+Buf2], xmm0
0x18001ed61  mov     [rsp+140h+var_110], r8; __int64 *
0x18001ed66  mov     [rsp+140h+var_118], r8; __int64 *
0x18001ed6b  lea     rax, [rsp+140h+Src]
0x18001ed70  mov     [rsp+140h+var_120], rax; int
0x18001ed75  lea     r9, [rsp+140h+pv]; struct tWAVEFORMATEX **
0x18001ed7a  lea     r8, [rbp+40h+Buf2]; struct _GUID
0x18001ed7e  call    ?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z; GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)
0x18001ed83  mov     esi, eax
0x18001ed85  test    eax, eax
0x18001ed87  js      loc_18001EEE5
0x18001ed8d  mov     r13, [rsp+140h+ppIAudioMediaType]
0x18001ed92  movaps  xmm0, xmmword ptr [r13+0]
0x18001ed97  movdqa  xmmword ptr [rsp+140h+ppIAudioMediaType], xmm0
0x18001ed9d  mov     r8d, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001eda0  lea     rdx, [rsp+140h+ppIAudioMediaType]; struct _GUID
0x18001eda5  mov     rcx, [r14+8]; this
0x18001eda9  call    ?CanProcessingModeBeParameterized@EffectPack@@QEAA_NU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::CanProcessingModeBeParameterized(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18001edae  test    al, al
0x18001edb0  jnz     short loc_18001EDCA
0x18001edb2  lea     r8d, [rdi+10h]; Size
0x18001edb6  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x18001edbd  mov     rcx, [rbp+40h+Buf1]; Buf1
0x18001edc1  call    memcmp_0
0x18001edc6  test    eax, eax
0x18001edc8  jnz     short loc_18001EDFA
0x18001edca  movaps  xmm0, xmmword ptr [r13+0]
0x18001edcf  movdqa  xmmword ptr [rsp+140h+ppIAudioMediaType], xmm0
0x18001edd5  lea     r9, [rsp+140h+var_E8]; struct tWAVEFORMATEX **
0x18001edda  lea     r8, [rsp+140h+ppIAudioMediaType]; struct _GUID
0x18001eddf  mov     edx, r12d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001ede2  mov     rcx, [r14+8]; this
0x18001ede6  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001edeb  mov     esi, eax
0x18001eded  mov     rdi, [rsp+140h+var_E8]
0x18001edf2  test    eax, eax
0x18001edf4  js      loc_18001EEE5
0x18001edfa  mov     rax, [r14]
0x18001edfd  mov     [rsp+140h+ppIAudioMediaType], rax
0x18001ee02  xor     ebx, ebx
0x18001ee04  mov     [rsp+140h+var_100], rbx
0x18001ee09  lea     r15, [rax+2000h]
0x18001ee10  mov     rcx, r15; lpCriticalSection
0x18001ee13  call    cs:__imp_EnterCriticalSection
0x18001ee19  mov     [rbp+40h+Buf1], r15
0x18001ee1d  xorps   xmm0, xmm0
0x18001ee20  xor     eax, eax
0x18001ee22  movups  xmmword ptr [rbp+40h+var_60.Data1], xmm0
0x18001ee26  mov     [rbp+40h+var_50], eax
0x18001ee29  movaps  xmm0, xmmword ptr [r13+0]
0x18001ee2e  movdqa  [rbp+40h+Buf2], xmm0
0x18001ee33  xor     r14d, r14d
0x18001ee36  cmp     r14d, 0Ah
0x18001ee3a  jnb     loc_18001F1F3
0x18001ee40  mov     ecx, r14d
0x18001ee43  shl     rcx, 4
0x18001ee47  lea     rax, qword_180188140
0x18001ee4e  add     rcx, rax; Buf1
0x18001ee51  mov     r8d, 10h; Size
0x18001ee57  lea     rdx, [rbp+40h+Buf2]; Buf2
0x18001ee5b  call    memcmp_0
0x18001ee60  test    eax, eax
0x18001ee62  jz      loc_18001EF3D
0x18001ee68  inc     r14d
0x18001ee6b  jmp     short loc_18001EE36
0x18001ee6d  test    rbx, rbx
0x18001ee70  jnz     short loc_18001EEA3
0x18001ee72  mov     rsi, [rsp+140h+Src]
0x18001ee77  movzx   r14d, word ptr [rsi+10h]
0x18001ee7c  lea     rcx, [r14+12h]; cb
0x18001ee80  call    cs:__imp_CoTaskMemAlloc
0x18001ee86  mov     rbx, rax
0x18001ee89  test    rax, rax
0x18001ee8c  jz      loc_18001F09B
0x18001ee92  lea     r8, [r14+12h]; Size
0x18001ee96  mov     rdx, rsi; Src
0x18001ee99  mov     rcx, rax; void *
0x18001ee9c  call    memcpy_0
0x18001eea1  xor     esi, esi
0x18001eea3  test    esi, esi
0x18001eea5  js      short loc_18001EEE5
0x18001eea7  mov     rax, [rsp+140h+pv]
0x18001eeac  mov     [rsp+140h+pv], 0
0x18001eeb5  mov     rcx, [rbp+40h+var_88]
0x18001eeb9  mov     [rcx], rax
0x18001eebc  mov     rax, rbx
0x18001eebf  xor     ebx, ebx
0x18001eec1  mov     rcx, [rbp+40h+var_80]
0x18001eec5  mov     [rcx], rax
0x18001eec8  mov     rax, rdi
0x18001eecb  xor     edi, edi
0x18001eecd  mov     rcx, [rbp+40h+var_78]
0x18001eed1  mov     [rcx], rax
0x18001eed4  mov     rax, [rsp+140h+Src]
0x18001eed9  mov     [rsp+140h+Src], rbx
0x18001eede  mov     rcx, [rbp+40h+var_70]
0x18001eee2  mov     [rcx], rax
0x18001eee5  mov     r14d, esi
0x18001eee8  mov     rcx, [rsp+140h+Src]; pv
0x18001eeed  call    cs:__imp_CoTaskMemFree
0x18001eef3  nop
0x18001eef4  mov     rcx, rdi; pv
0x18001eef7  call    cs:__imp_CoTaskMemFree
0x18001eefd  nop
0x18001eefe  mov     rcx, rbx; pv
0x18001ef01  call    cs:__imp_CoTaskMemFree
0x18001ef07  nop
0x18001ef08  mov     rcx, [rsp+140h+pv]; pv
0x18001ef0d  call    cs:__imp_CoTaskMemFree
0x18001ef13  mov     eax, r14d
0x18001ef16  mov     rcx, [rbp+40h+var_40]
0x18001ef1a  xor     rcx, rsp; StackCookie
0x18001ef1d  call    __security_check_cookie
0x18001ef22  mov     rbx, [rsp+140h+arg_8]
0x18001ef2a  add     rsp, 110h
0x18001ef31  pop     r15
0x18001ef33  pop     r14
0x18001ef35  pop     r13
0x18001ef37  pop     r12
0x18001ef39  pop     rdi
0x18001ef3a  pop     rsi
0x18001ef3b  pop     rbp
0x18001ef3c  retn
0x18001ef3d  movups  xmm0, cs:PKEY_AudioEngine_SignalProcessingMode_Specific_StreamGroupFormat
0x18001ef44  movdqu  xmmword ptr [rbp+40h+var_60.Data1], xmm0
0x18001ef49  mov     eax, 25Ah
0x18001ef4e  mov     ecx, 2
0x18001ef53  cmp     r12d, 3
0x18001ef57  cmovnz  eax, ecx
0x18001ef5a  add     eax, r14d
0x18001ef5d  mov     [rbp+40h+var_50], eax
0x18001ef60  xorps   xmm0, xmm0
0x18001ef63  xor     eax, eax
0x18001ef65  movups  xmmword ptr [rbp+40h+pvar], xmm0
0x18001ef69  mov     [rbp+40h+var_90], rax
0x18001ef6d  mov     rcx, [rsp+140h+ppIAudioMediaType]
0x18001ef72  mov     rcx, [rcx+48h]
0x18001ef76  mov     rax, [rcx]
0x18001ef79  lea     r8, [rbp+40h+pvar]
0x18001ef7d  lea     rdx, [rbp+40h+var_60]
0x18001ef81  mov     rax, [rax+28h]
0x18001ef85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef8a  mov     r14d, eax
0x18001ef8d  test    eax, eax
0x18001ef8f  js      short loc_18001EFBE
0x18001ef91  cmp     word ptr [rbp+40h+pvar], 41h ; 'A'
0x18001ef96  jz      loc_18001F19F
0x18001ef9c  lea     rcx, [rbp+40h+pvar]; pvar
0x18001efa0  call    cs:__imp_PropVariantClear
0x18001efa6  nop
0x18001efa7  test    r15, r15
0x18001efaa  jz      loc_18001EE6D
0x18001efb0  mov     rcx, r15; lpCriticalSection
0x18001efb3  call    cs:__imp_LeaveCriticalSection
0x18001efb9  jmp     loc_18001EE6D
0x18001efbe  mov     r9d, eax; char *
0x18001efc1  mov     edx, 1BE4h; void *
0x18001efc6  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18001efcd  mov     rcx, [rbp+48h]; this
0x18001efd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001efd6  nop
0x18001efd7  lea     rcx, [rbp+40h+pvar]; pvar
0x18001efdb  call    cs:__imp_PropVariantClear
0x18001efe1  nop
0x18001efe2  test    r15, r15
0x18001efe5  jnz     short loc_18001F004
0x18001efe7  mov     rcx, [rbp+48h]; this
0x18001efeb  mov     r9d, r14d; char *
0x18001efee  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001eff5  mov     edx, 339h; void *
0x18001effa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001efff  jmp     loc_18001EEE8
0x18001f004  mov     rcx, r15; lpCriticalSection
0x18001f007  call    cs:__imp_LeaveCriticalSection
0x18001f00d  jmp     short loc_18001EFE7
0x18001f00f  movaps  xmm0, xmmword ptr [r13+0]
0x18001f014  movdqa  xmmword ptr [rsp+140h+ppIAudioMediaType], xmm0
0x18001f01a  lea     rax, [rsp+140h+pv]
0x18001f01f  mov     [rsp+140h+var_110], rax; struct tWAVEFORMATEX **
0x18001f024  mov     eax, [rbp+40h+arg_20]
0x18001f027  mov     dword ptr [rsp+140h+var_118], eax; unsigned int
0x18001f02b  lea     r9, [rsp+140h+ppIAudioMediaType]; struct _GUID
0x18001f030  mov     rdx, r15; struct tWAVEFORMATEX *
0x18001f033  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x18001f036  call    ?DeriveOffloadConnectorFormatFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@PEAUtWAVEFORMATEX@@U_GUID@@22KPEAPEAU2@@Z; DeriveOffloadConnectorFormatFromStreamFormat(EndpointCharacteristicsDescriptor *,tWAVEFORMATEX *,_GUID,_GUID,_GUID,ulong,tWAVEFORMATEX * *)
0x18001f03b  mov     esi, eax
0x18001f03d  test    eax, eax
0x18001f03f  js      loc_18001EEE5
0x18001f045  lea     rdx, [rsp+140h+var_E8]; struct tWAVEFORMATEX **
0x18001f04a  mov     rcx, [rsp+140h+pv]; Src
0x18001f04f  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001f054  mov     esi, eax
0x18001f056  mov     rdi, [rsp+140h+var_E8]
0x18001f05b  mov     rcx, rdi; struct tWAVEFORMATEX *
0x18001f05e  call    ?ConvertPCMWfxToIEEEFloat@@YAXPEAUtWAVEFORMATEX@@@Z; ConvertPCMWfxToIEEEFloat(tWAVEFORMATEX *)
0x18001f063  test    esi, esi
0x18001f065  js      loc_18001EEE5
0x18001f06b  lea     rdx, [rsp+140h+var_100]; struct tWAVEFORMATEX **
0x18001f070  mov     rcx, rdi; Src
0x18001f073  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001f078  mov     esi, eax
0x18001f07a  test    eax, eax
0x18001f07c  js      loc_18001F195
0x18001f082  lea     rdx, [rsp+140h+Src]; struct tWAVEFORMATEX **
0x18001f087  mov     rbx, [rsp+140h+var_100]
0x18001f08c  mov     rcx, rbx; Src
0x18001f08f  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001f094  mov     esi, eax
0x18001f096  jmp     loc_18001EEA3
0x18001f09b  mov     esi, 8007000Eh
0x18001f0a0  jmp     loc_18001EEA3
0x18001f0a5  lea     rcx, [rbp+40h+Buf2]
0x18001f0a9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f0ae  nop
0x18001f0af  lea     rcx, [rbp+40h+Buf1]
0x18001f0b3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f0b8  nop
0x18001f0b9  lea     rcx, [rsp+140h+var_E0]
0x18001f0be  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f0c3  nop
0x18001f0c4  lea     rcx, [rsp+140h+ppIAudioMediaType]
0x18001f0c9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001f0ce  jmp     loc_18001EEA3
0x18001f0d3  mov     rcx, [rbp+48h]; this
0x18001f0d7  mov     r9d, eax; char *
0x18001f0da  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18001f0e1  mov     edx, 1BEAh; void *
0x18001f0e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f0eb  nop
0x18001f0ec  lea     rcx, [rbp+40h+pvar]; pvar
0x18001f0f0  call    cs:__imp_PropVariantClear
0x18001f0f6  nop
0x18001f0f7  test    r15, r15
0x18001f0fa  jz      short loc_18001F105
0x18001f0fc  mov     rcx, r15; lpCriticalSection
0x18001f0ff  call    cs:__imp_LeaveCriticalSection
0x18001f105  mov     rbx, [rsp+140h+var_100]
0x18001f10a  jmp     loc_18001EFE7
0x18001f10f  lea     rdx, [rsp+140h+var_100]; struct tWAVEFORMATEX **
0x18001f114  mov     rcx, r15; Src
0x18001f117  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001f11c  mov     esi, eax
0x18001f11e  test    eax, eax
0x18001f120  js      short loc_18001F195
0x18001f122  mov     [rsp+140h+var_E0], 0
0x18001f12b  mov     rcx, [r14]
0x18001f12e  add     rcx, 28h ; '('
0x18001f132  lea     rdx, [rsp+140h+var_E0]
0x18001f137  call    ??$copy_to@VCAudioSession@@@?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAVCAudioSession@@@Z; wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(CAudioSession * *)
0x18001f13c  mov     rcx, r15; struct tWAVEFORMATEX *
0x18001f13f  call    ?IsSPDIFFormat@@YAHPEBUtWAVEFORMATEX@@@Z; IsSPDIFFormat(tWAVEFORMATEX const *)
0x18001f144  test    eax, eax
0x18001f146  jz      short loc_18001F175
0x18001f148  mov     rcx, [r14]; this
0x18001f14b  call    ?IsSPDIFEndpoint@CEndpointCharacteristics@@QEAA_NXZ; CEndpointCharacteristics::IsSPDIFEndpoint(void)
  ... truncated ...
```
