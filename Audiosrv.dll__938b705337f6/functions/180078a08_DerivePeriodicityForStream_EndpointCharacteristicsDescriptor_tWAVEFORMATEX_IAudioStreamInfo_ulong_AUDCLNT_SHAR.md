# DerivePeriodicityForStream(EndpointCharacteristicsDescriptor *,tWAVEFORMATEX *,IAudioStreamInfo *,ulong,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID,_GUID,_GUID,bool,bool,__int64,__int64,IProcessSubmixProxy *,__int64 *,__int64 *,__int64 *)

- ea: `0x180078a08`
- end: `0x18007931e`
- name: `?DerivePeriodicityForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@PEAUtWAVEFORMATEX@@PEAUIAudioStreamInfo@@KW4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@1U_GUID@@55_N6_J7PEAUIProcessSubmixProxy@@PEA_J99@Z`
- size: `2326`
- prototype: `__int64 __usercall@<rax>(struct EndpointCharacteristicsDescriptor *@<rcx>, struct tWAVEFORMATEX *@<rdx>, struct IAudioStreamInfo *@<r8>, unsigned int@<r9d>, enum _AUDCLNT_SHAREMODE, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct tWAVEFORMATEX *, struct _GUID *, struct _GUID *, struct _GUID *, bool, bool, __int64, LPVOID, struct IProcessSubmixProxy *, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180073990`

## callees

- `0x1800088dc`
- `0x18000accc`
- `0x1800126bc`
- `0x18001eb4c`
- `0x18001f6b0`
- `0x1800423cc`
- `0x180045068`
- `0x180078a08`
- `0x1800d06d4`
- `0x1800e5924`
- `0x180121e04`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180078c41`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180078c41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800790f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007910c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079120`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007913a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079236`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007926e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007928f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800792b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800790f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007910c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079120`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007913a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079236`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007926e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007928f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800792b0`

## string_xrefs

- `0x180078b79`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180078ced`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180078f34`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800790cf`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DerivePeriodicityForStream(
        struct EndpointCharacteristicsDescriptor *a1,
        struct tWAVEFORMATEX *a2,
        struct IAudioStreamInfo *a3,
        int a4,
        enum _AUDCLNT_SHAREMODE pvData,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a6,
        struct tWAVEFORMATEX *a7,
        struct _GUID *a8,
        struct _GUID *a9,
        struct _GUID *a10,
        bool a11,
        bool a12,
        __int64 a13,
        int *a14,
        struct IProcessSubmixProxy *a15,
        struct tWAVEFORMATEX *a16,
        __int64 *pv,
        __int64 *a18)
{
  int *v19; // rbx
  struct tWAVEFORMATEX *v20; // rdi
  __int64 *v21; // r12
  struct IProcessSubmixProxy *v22; // rsi
  void (__fastcall *v23)(struct IProcessSubmixProxy *, int **); // rbx
  struct tWAVEFORMATEX *v24; // r14
  int SharedModeEnginePeriodicity; // eax
  unsigned int v26; // esi
  enum _AUDCLNT_SHAREMODE v28; // r15d
  double v29; // xmm6_8
  double v30; // xmm2_8
  double v31; // xmm3_8
  signed int nSamplesPerSec; // r11d
  double v33; // xmm7_8
  double v34; // xmm8_8
  unsigned int v35; // ebx
  signed int v36; // r12d
  signed int v37; // ebx
  __int64 v38; // rdx
  int MixFormat; // ebx
  unsigned int v40; // edx
  unsigned int v41; // r8d
  unsigned int v42; // esi
  unsigned int v43; // edx
  unsigned int v44; // r8d
  unsigned int v45; // r10d
  unsigned int v46; // edx
  unsigned int v47; // r8d
  unsigned int v48; // r9d
  unsigned int v49; // eax
  unsigned int v50; // r9d
  unsigned int v51; // r10d
  unsigned int v52; // ebx
  int v53; // edx
  int v54; // esi
  struct _GUID *v55; // rsi
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v56; // r15d
  __int64 *v57; // rcx
  void *v58; // rcx
  void *v59; // rcx
  int *v60; // rcx
  __int64 *v61; // rcx
  struct _GUID *v62; // r12
  __int64 v63; // rdx
  __int64 *v64; // rcx
  void *v65; // rcx
  void *v66; // rcx
  bool v67; // zf
  int *v68; // rcx
  __int64 v69; // rax
  __int64 *v70; // rcx
  void *v71; // rcx
  void *v72; // rcx
  int *v73; // rcx
  __int64 *v74; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  DWORD pcbData[4]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v78[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v79; // [rsp+90h] [rbp-70h] BYREF
  char v80; // [rsp+A0h] [rbp-60h]
  struct _GUID v81; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID *v82; // [rsp+C0h] [rbp-40h] BYREF
  struct tWAVEFORMATEX *v83; // [rsp+C8h] [rbp-38h] BYREF
  char v84; // [rsp+D0h] [rbp-30h]
  DWORD *v85; // [rsp+D8h] [rbp-28h] BYREF
  struct tWAVEFORMATEX *v86; // [rsp+E0h] [rbp-20h] BYREF
  char v87; // [rsp+E8h] [rbp-18h]
  __int64 **p_pv; // [rsp+F0h] [rbp-10h] BYREF
  struct tWAVEFORMATEX *v89; // [rsp+F8h] [rbp-8h] BYREF
  char v90; // [rsp+100h] [rbp+0h]
  int **v91; // [rsp+108h] [rbp+8h] BYREF
  struct tWAVEFORMATEX *v92; // [rsp+110h] [rbp+10h] BYREF
  char v93; // [rsp+118h] [rbp+18h]
  struct _GUID v94; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v19 = a14;
  v20 = a16;
  *(_QWORD *)&a16->wFormatTag = a14;
  v21 = pv;
  *pv = (__int64)v19;
  if ( pvData )
    return 0;
  if ( (a4 & 0x20000) == 0 || (v22 = a15) == 0 )
  {
    if ( (a4 & 1) != 0 )
    {
      if ( !v19 )
        *(_QWORD *)&v20->wFormatTag = a13;
      return 0;
    }
    pvData = AUDCLNT_SHAREMODE_SHARED;
    LODWORD(pv) = 0;
    LODWORD(a14) = 0;
    LODWORD(a16) = 0;
    *(struct _GUID *)v78 = *a8;
    pdwType = a11;
    v24 = a7;
    SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(
                                    *((_QWORD *)a1 + 1),
                                    (unsigned int)a6,
                                    a7,
                                    v78);
    v26 = SharedModeEnginePeriodicity;
    if ( SharedModeEnginePeriodicity < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51F,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)SharedModeEnginePeriodicity,
        pdwType);
      return v26;
    }
    v28 = pvData;
    v29 = (double)(int)pvData * 10000000.0;
    v30 = DOUBLE_0_5;
    *v21 = (unsigned int)(int)(v29 / (double)(int)v24->nSamplesPerSec + 0.5);
    if ( !v19 )
    {
      *(_QWORD *)&v20->wFormatTag = (unsigned int)(int)(v29 / (double)(int)v24->nSamplesPerSec + 0.5);
      goto LABEL_42;
    }
    pvData = AUDCLNT_SHAREMODE_SHARED;
    pcbData[0] = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
      L"SkipPeriodicityValidation",
      0x18u,
      0,
      &pvData,
      pcbData);
    if ( pvData )
      goto LABEL_41;
    v31 = (double)(int)v19;
    nSamplesPerSec = v24->nSamplesPerSec;
    v33 = DOUBLE_1_0e7;
    v34 = DOUBLE_0_5;
    v35 = (int)((double)nSamplesPerSec * (double)(int)v19 / 10000000.0 + 0.5);
    v36 = (int)a16;
    if ( v35 >= (unsigned int)pv
      && v35 <= (unsigned int)a14
      && (!(v35 % (unsigned int)a16) || v35 == v28 || v35 == (_DWORD)pv || v35 == (_DWORD)a14) )
    {
LABEL_38:
      if ( (*(unsigned __int8 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 152LL))(a3) && v35 < v28 )
      {
        v38 = 1391;
        goto LABEL_19;
      }
LABEL_41:
      v30 = DOUBLE_0_5;
LABEL_42:
      if ( a12 )
      {
        a16 = 0;
        a14 = 0;
        v78[0] = 0;
        *(_QWORD *)pcbData = 0;
        pv = 0;
        *(_QWORD *)&v79.Data1 = &a16;
        *(_QWORD *)v79.Data4 = 0;
        v80 = 1;
        v55 = a9;
        v81 = *a9;
        v56 = a6;
        MixFormat = EffectPack::GetMixFormat(*((EffectPack **)a1 + 1), a6, &v81, (struct tWAVEFORMATEX **)v79.Data4);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v79);
        if ( MixFormat < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x579,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)MixFormat,
            pdwType);
          v57 = pv;
          pv = 0;
          if ( v57 )
            CoTaskMemFree(v57);
          v58 = *(void **)pcbData;
          *(_QWORD *)pcbData = 0;
          if ( v58 )
            CoTaskMemFree(v58);
          v59 = v78[0];
          v78[0] = 0;
          if ( v59 )
            CoTaskMemFree(v59);
          v60 = a14;
          a14 = 0;
          if ( v60 )
            CoTaskMemFree(v60);
          v61 = (__int64 *)a16;
          a16 = 0;
LABEL_53:
          if ( v61 )
            CoTaskMemFree(v61);
          return (unsigned int)MixFormat;
        }
        v91 = &a14;
        v92 = 0;
        v93 = 1;
        p_pv = &pv;
        v89 = 0;
        v90 = 1;
        v85 = pcbData;
        v86 = 0;
        v87 = 1;
        v82 = v78;
        v83 = 0;
        v84 = 1;
        v62 = a8;
        v81 = *a8;
        v94 = *a10;
        v79 = *v55;
        MixFormat = DeriveDeviceGraphFormatsForStream(
                      a1,
                      0,
                      v56,
                      AUDCLNT_SHAREMODE_SHARED,
                      0,
                      &v79,
                      &v94,
                      &v81,
                      a16,
                      &v83,
                      &v86,
                      &v89,
                      &v92);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v82);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v85);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v91);
        if ( MixFormat < 0 )
        {
          v63 = 1402;
LABEL_57:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v63,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)MixFormat,
            pdwTypea);
          v64 = pv;
          pv = 0;
          if ( v64 )
            CoTaskMemFree(v64);
          v65 = *(void **)pcbData;
          *(_QWORD *)pcbData = 0;
          if ( v65 )
            CoTaskMemFree(v65);
          v66 = v78[0];
          v67 = v78[0] == 0;
          v78[0] = 0;
          if ( !v67 )
            CoTaskMemFree(v66);
          v68 = a14;
          a14 = 0;
          if ( v68 )
            CoTaskMemFree(v68);
          v61 = (__int64 *)a16;
          a16 = 0;
          goto LABEL_53;
        }
        pvData = AUDCLNT_SHAREMODE_SHARED;
        v79 = *v62;
        pdwTypea = 0;
        MixFormat = EffectPack::GetSharedModeEnginePeriodicity(*((_QWORD *)a1 + 1), (unsigned int)v56, a14, &v79);
        if ( MixFormat < 0 )
        {
          v63 = 1405;
          goto LABEL_57;
        }
        v30 = DOUBLE_0_5;
        v69 = (unsigned int)(int)((double)(int)pvData * 10000000.0 / (double)a14[1] + 0.5);
        if ( *(_QWORD *)&v20->wFormatTag - v69 > 5 * v69 / 100 )
        {
          MixFormat = -2004287448;
          v63 = 1408;
          goto LABEL_57;
        }
        v70 = pv;
        pv = 0;
        if ( v70 )
        {
          CoTaskMemFree(v70);
          v30 = DOUBLE_0_5;
        }
        v71 = *(void **)pcbData;
        *(_QWORD *)pcbData = 0;
        if ( v71 )
        {
          CoTaskMemFree(v71);
          v30 = DOUBLE_0_5;
        }
        v72 = v78[0];
        v78[0] = 0;
        if ( v72 )
        {
          CoTaskMemFree(v72);
          v30 = DOUBLE_0_5;
        }
        v73 = a14;
        a14 = 0;
        if ( v73 )
        {
          CoTaskMemFree(v73);
          v30 = DOUBLE_0_5;
        }
        v74 = (__int64 *)a16;
        a16 = 0;
        if ( v74 )
        {
          CoTaskMemFree(v74);
          v30 = DOUBLE_0_5;
        }
      }
      *a18 = (unsigned int)(int)(v29 / (double)(int)v24->nSamplesPerSec + v30);
      return 0;
    }
    v37 = a2->nSamplesPerSec;
    if ( v37 == nSamplesPerSec )
    {
      v38 = 1345;
LABEL_19:
      MixFormat = -2004287456;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)0x88890020LL,
        pdwType);
      return (unsigned int)MixFormat;
    }
    LODWORD(a14) = TranslateFrameCountBetweenSamplingRates(v28, nSamplesPerSec, v37);
    v42 = TranslateFrameCountBetweenSamplingRates(v36, v40, v41);
    LODWORD(a16) = TranslateFrameCountBetweenSamplingRates(v45, v43, v44);
    v49 = TranslateFrameCountBetweenSamplingRates(v48, v46, v47);
    v52 = (int)((double)v37 * v31 / 10000000.0 + 0.5);
    if ( v52 < (unsigned int)a16 || v52 > v49 )
    {
LABEL_27:
      v38 = 1365;
      goto LABEL_19;
    }
    v53 = v52 % v42;
    v54 = v52 / v42;
    if ( v53 )
    {
      if ( v52 != (_DWORD)a14 )
      {
        if ( v52 != (_DWORD)a16 )
        {
          if ( v52 != v49 )
            goto LABEL_27;
LABEL_33:
          v35 = v50;
          goto LABEL_37;
        }
LABEL_31:
        v35 = v51;
        goto LABEL_37;
      }
    }
    else if ( v52 != (_DWORD)a14 )
    {
      if ( v52 != (_DWORD)a16 )
      {
        if ( v52 != v49 )
        {
          v33 = DOUBLE_1_0e7;
          v34 = DOUBLE_0_5;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::GetImpl'::`2'::impl) )
            v35 = (int)(float)(o_ceilf_0(
                                 (float)(int)v52
                               / (float)((double)(int)((double)v36 * 10000000.0 / (double)(int)v24->nSamplesPerSec + 0.5)
                                       * (double)(int)a2->nSamplesPerSec
                                       / 10000000.0))
                             * (float)v36);
          else
            v35 = v36 * v54;
          goto LABEL_37;
        }
        goto LABEL_33;
      }
      goto LABEL_31;
    }
    v35 = v28;
LABEL_37:
    *(_QWORD *)&v20->wFormatTag = (unsigned int)(int)((double)(int)v35 * v33 / (double)(int)v24->nSamplesPerSec + v34);
    goto LABEL_38;
  }
  a14 = 0;
  v23 = *(void (__fastcall **)(struct IProcessSubmixProxy *, int **))(*(_QWORD *)a15 + 64LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&a14);
  v23(v22, &a14);
  *(_QWORD *)&v20->wFormatTag = (*(__int64 (__fastcall **)(int *))(*(_QWORD *)a14 + 128LL))(a14);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&a14);
  return 0;
}

```

## disassembly

```asm
0x180078a08  mov     rax, rsp
0x180078a0b  mov     [rax+8], rbx
0x180078a0f  mov     [rax+18h], r8
0x180078a13  mov     [rax+10h], rdx
0x180078a17  push    rbp
0x180078a18  push    rsi
0x180078a19  push    rdi
0x180078a1a  push    r12
0x180078a1c  push    r13
0x180078a1e  push    r14
0x180078a20  push    r15
0x180078a22  lea     rbp, [rsp-60h]
0x180078a27  sub     rsp, 160h
0x180078a2e  movaps  xmmword ptr [rax-48h], xmm6
0x180078a32  movaps  xmmword ptr [rax-58h], xmm7
0x180078a36  movaps  xmmword ptr [rax-68h], xmm8
0x180078a3b  mov     r13, rcx
0x180078a3e  mov     rbx, [rbp+90h+arg_68]
0x180078a45  mov     rdi, [rbp+90h+arg_78]
0x180078a4c  mov     [rdi], rbx
0x180078a4f  mov     r12, [rbp+90h+pv]
0x180078a56  mov     [r12], rbx
0x180078a5a  mov     eax, [rbp+90h+arg_20]
0x180078a60  xor     r15d, r15d
0x180078a63  test    eax, eax
0x180078a65  jnz     loc_1800792F2
0x180078a6b  bt      r9d, 11h
0x180078a70  jnb     short loc_180078AD4
0x180078a72  mov     rsi, [rbp+90h+arg_70]
0x180078a79  test    rsi, rsi
0x180078a7c  jz      short loc_180078AD4
0x180078a7e  mov     [rbp+90h+arg_68], r15
0x180078a85  mov     rax, [rsi]
0x180078a88  mov     rbx, [rax+40h]
0x180078a8c  lea     rcx, [rbp+90h+arg_68]
0x180078a93  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180078a98  lea     rdx, [rbp+90h+arg_68]
0x180078a9f  mov     rcx, rsi
0x180078aa2  mov     rax, rbx
0x180078aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078aaa  mov     rcx, [rbp+90h+arg_68]
0x180078ab1  mov     rax, [rcx]
0x180078ab4  mov     rax, [rax+80h]
0x180078abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ac0  mov     [rdi], rax
0x180078ac3  lea     rcx, [rbp+90h+arg_68]
0x180078aca  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180078acf  jmp     loc_1800792F2
0x180078ad4  test    eax, eax
0x180078ad6  jnz     loc_1800792F2
0x180078adc  test    r9b, 1
0x180078ae0  jnz     loc_1800792E3
0x180078ae6  mov     [rbp+90h+arg_20], r15d
0x180078aed  mov     dword ptr [rbp+90h+pv], r15d
0x180078af4  mov     dword ptr [rbp+90h+arg_68], r15d
0x180078afb  mov     dword ptr [rbp+90h+arg_78], r15d
0x180078b02  mov     rax, [rbp+90h+arg_38]
0x180078b09  movaps  xmm0, xmmword ptr [rax]
0x180078b0c  movdqa  xmmword ptr [rbp+90h+var_110], xmm0
0x180078b11  movzx   eax, [rbp+90h+arg_50]
0x180078b18  lea     rcx, [rbp+90h+arg_68]
0x180078b1f  mov     [rsp+190h+var_150], rcx
0x180078b24  lea     rcx, [rbp+90h+pv]
0x180078b2b  mov     [rsp+190h+var_158], rcx
0x180078b30  lea     rcx, [rbp+90h+arg_78]
0x180078b37  mov     [rsp+190h+pcbData], rcx
0x180078b3c  lea     rcx, [rbp+90h+arg_20]
0x180078b43  mov     [rsp+190h+pvData], rcx
0x180078b48  mov     dword ptr [rsp+190h+pdwType], eax; int
0x180078b4c  lea     r9, [rbp+90h+var_110]
0x180078b50  mov     r14, [rbp+90h+arg_30]
0x180078b57  mov     r8, r14
0x180078b5a  mov     edx, [rbp+90h+arg_28]
0x180078b60  mov     rcx, [r13+8]
0x180078b64  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x180078b69  mov     esi, eax
0x180078b6b  test    eax, eax
0x180078b6d  jns     short loc_180078B91
0x180078b6f  mov     rcx, [rbp+98h]; this
0x180078b76  mov     r9d, eax; char *
0x180078b79  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180078b80  mov     edx, 51Fh; void *
0x180078b85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078b8a  mov     eax, esi
0x180078b8c  jmp     loc_1800792F4
0x180078b91  mov     r15d, [rbp+90h+arg_20]
0x180078b98  xorps   xmm6, xmm6
0x180078b9b  cvtsi2sd xmm6, r15
0x180078ba0  mulsd   xmm6, cs:__real@416312d000000000
0x180078ba8  mov     eax, [r14+4]
0x180078bac  xorps   xmm0, xmm0
0x180078baf  cvtsi2sd xmm0, rax
0x180078bb4  movaps  xmm1, xmm6
0x180078bb7  divsd   xmm1, xmm0
0x180078bbb  movsd   xmm2, cs:__real@3fe0000000000000
0x180078bc3  addsd   xmm1, xmm2
0x180078bc7  cvttsd2si rax, xmm1
0x180078bcc  mov     [r12], rax
0x180078bd0  xor     r12d, r12d
0x180078bd3  test    rbx, rbx
0x180078bd6  jnz     short loc_180078BFC
0x180078bd8  mov     eax, [r14+4]
0x180078bdc  xorps   xmm0, xmm0
0x180078bdf  cvtsi2sd xmm0, rax
0x180078be4  movaps  xmm1, xmm6
0x180078be7  divsd   xmm1, xmm0
0x180078beb  addsd   xmm1, xmm2
0x180078bef  cvttsd2si rax, xmm1
0x180078bf4  mov     [rdi], rax
0x180078bf7  jmp     loc_180078EAF
0x180078bfc  mov     [rbp+90h+arg_20], r12d
0x180078c03  mov     [rsp+190h+var_120], 4
0x180078c0b  lea     rax, [rsp+190h+var_120]
0x180078c10  mov     [rsp+190h+pcbData], rax; pcbData
0x180078c15  lea     rax, [rbp+90h+arg_20]
0x180078c1c  mov     [rsp+190h+pvData], rax; pvData
0x180078c21  mov     [rsp+190h+pdwType], r12; int
0x180078c26  mov     r9d, 18h; dwFlags
0x180078c2c  lea     r8, aSkipperiodicit; "SkipPeriodicityValidation"
0x180078c33  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180078c3a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180078c41  call    cs:__imp_RegGetValueW
0x180078c47  cmp     [rbp+90h+arg_20], r12d
0x180078c4e  jnz     loc_180078EA7
0x180078c54  xorps   xmm3, xmm3
0x180078c57  cvtsi2sd xmm3, rbx
0x180078c5c  mov     r11d, [r14+4]
0x180078c60  xorps   xmm0, xmm0
0x180078c63  cvtsi2sd xmm0, r11
0x180078c68  mulsd   xmm0, xmm3
0x180078c6c  movsd   xmm7, cs:__real@416312d000000000
0x180078c74  divsd   xmm0, xmm7
0x180078c78  movsd   xmm8, cs:__real@3fe0000000000000
0x180078c81  addsd   xmm0, xmm8
0x180078c86  cvttsd2si rbx, xmm0
0x180078c8b  mov     r9d, dword ptr [rbp+90h+arg_68]
0x180078c92  mov     r12d, dword ptr [rbp+90h+arg_78]
0x180078c99  mov     r10d, dword ptr [rbp+90h+pv]
0x180078ca0  cmp     ebx, r10d
0x180078ca3  jb      short loc_180078CD4
0x180078ca5  cmp     ebx, r9d
0x180078ca8  ja      short loc_180078CD4
0x180078caa  xor     edx, edx
0x180078cac  mov     eax, ebx
0x180078cae  div     r12d
0x180078cb1  test    edx, edx
0x180078cb3  jz      loc_180078E7B
0x180078cb9  cmp     ebx, r15d
0x180078cbc  jz      loc_180078E7B
0x180078cc2  cmp     ebx, r10d
0x180078cc5  jz      loc_180078E7B
0x180078ccb  cmp     ebx, r9d
0x180078cce  jz      loc_180078E7B
0x180078cd4  mov     rbx, [rbp+90h+arg_8]
0x180078cdb  mov     ebx, [rbx+4]
0x180078cde  cmp     ebx, r11d
0x180078ce1  jnz     short loc_180078D0A
0x180078ce3  mov     edx, 541h; void *
0x180078ce8  mov     ebx, 88890020h
0x180078ced  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180078cf4  mov     r9d, ebx; char *
0x180078cf7  mov     rcx, [rbp+98h]; this
0x180078cfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078d03  mov     eax, ebx
0x180078d05  jmp     loc_1800792F4
0x180078d0a  mov     r8d, ebx; unsigned int
0x180078d0d  mov     edx, r11d; unsigned int
0x180078d10  mov     ecx, r15d; unsigned int
0x180078d13  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180078d18  mov     dword ptr [rbp+90h+arg_68], eax
0x180078d1e  mov     ecx, r12d; unsigned int
0x180078d21  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180078d26  mov     esi, eax
0x180078d28  mov     ecx, r10d; unsigned int
0x180078d2b  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180078d30  mov     dword ptr [rbp+90h+arg_78], eax
0x180078d36  mov     ecx, r9d; unsigned int
0x180078d39  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180078d3e  mov     r8d, eax
0x180078d41  xorps   xmm2, xmm2
0x180078d44  cvtsi2sd xmm2, rbx
0x180078d49  mulsd   xmm2, xmm3
0x180078d4d  divsd   xmm2, xmm7
0x180078d51  addsd   xmm2, xmm8
0x180078d56  cvttsd2si rbx, xmm2
0x180078d5b  mov     ecx, dword ptr [rbp+90h+arg_78]
0x180078d61  cmp     ebx, ecx
0x180078d63  jb      short loc_180078D88
0x180078d65  cmp     ebx, eax
0x180078d67  ja      short loc_180078D88
0x180078d69  xor     edx, edx
0x180078d6b  mov     eax, ebx
0x180078d6d  div     esi
0x180078d6f  mov     esi, eax
0x180078d71  mov     eax, dword ptr [rbp+90h+arg_68]
0x180078d77  test    edx, edx
0x180078d79  jz      short loc_180078D92
0x180078d7b  cmp     ebx, eax
0x180078d7d  jz      short loc_180078D96
0x180078d7f  cmp     ebx, ecx
0x180078d81  jz      short loc_180078DA2
0x180078d83  cmp     ebx, r8d
0x180078d86  jz      short loc_180078DAF
0x180078d88  mov     edx, 555h
0x180078d8d  jmp     loc_180078CE8
0x180078d92  cmp     ebx, eax
0x180078d94  jnz     short loc_180078D9E
0x180078d96  mov     ebx, r15d
0x180078d99  jmp     loc_180078E50
0x180078d9e  cmp     ebx, ecx
0x180078da0  jnz     short loc_180078DAA
0x180078da2  mov     ebx, r10d
0x180078da5  jmp     loc_180078E50
0x180078daa  cmp     ebx, r8d
0x180078dad  jnz     short loc_180078DB7
0x180078daf  mov     ebx, r9d
0x180078db2  jmp     loc_180078E50
0x180078db7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::GetImpl(void)'::`2'::impl
0x180078dbe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::__private_IsEnabled(void)
0x180078dc3  movsd   xmm7, cs:__real@416312d000000000
0x180078dcb  movsd   xmm8, cs:__real@3fe0000000000000
0x180078dd4  test    al, al
0x180078dd6  jz      short loc_180078E4A
0x180078dd8  mov     eax, ebx
0x180078dda  xorps   xmm0, xmm0
0x180078ddd  cvtsi2ss xmm0, rax
0x180078de2  xorps   xmm2, xmm2
0x180078de5  cvtsi2sd xmm2, r12
0x180078dea  mulsd   xmm2, xmm7
0x180078dee  mov     eax, [r14+4]
0x180078df2  xorps   xmm1, xmm1
0x180078df5  cvtsi2sd xmm1, rax
0x180078dfa  divsd   xmm2, xmm1
0x180078dfe  addsd   xmm2, xmm8
0x180078e03  cvttsd2si rax, xmm2
0x180078e08  xorps   xmm2, xmm2
0x180078e0b  cvtsi2sd xmm2, rax
0x180078e10  mov     rax, [rbp+90h+arg_8]
0x180078e17  mov     eax, [rax+4]
0x180078e1a  xorps   xmm1, xmm1
0x180078e1d  cvtsi2sd xmm1, rax
0x180078e22  mulsd   xmm2, xmm1
0x180078e26  divsd   xmm2, xmm7
0x180078e2a  cvtpd2ps xmm1, xmm2
0x180078e2e  divss   xmm0, xmm1; X
0x180078e32  call    _o_ceilf_0
0x180078e37  xorps   xmm1, xmm1
0x180078e3a  cvtsi2ss xmm1, r12
0x180078e3f  mulss   xmm0, xmm1
0x180078e43  cvttss2si rbx, xmm0
0x180078e48  jmp     short loc_180078E50
0x180078e4a  imul    esi, r12d
0x180078e4e  mov     ebx, esi
0x180078e50  mov     eax, ebx
0x180078e52  xorps   xmm1, xmm1
0x180078e55  cvtsi2sd xmm1, rax
0x180078e5a  mulsd   xmm1, xmm7
0x180078e5e  mov     eax, [r14+4]
0x180078e62  xorps   xmm0, xmm0
0x180078e65  cvtsi2sd xmm0, rax
0x180078e6a  divsd   xmm1, xmm0
0x180078e6e  addsd   xmm1, xmm8
0x180078e73  cvttsd2si rax, xmm1
0x180078e78  mov     [rdi], rax
0x180078e7b  mov     rcx, [rbp+90h+arg_10]
0x180078e82  mov     rax, [rcx]
0x180078e85  mov     rax, [rax+98h]
0x180078e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e91  xor     r12d, r12d
0x180078e94  test    al, al
0x180078e96  jz      short loc_180078EA7
0x180078e98  cmp     ebx, r15d
0x180078e9b  jnb     short loc_180078EA7
0x180078e9d  mov     edx, 56Fh
0x180078ea2  jmp     loc_180078CE8
0x180078ea7  movsd   xmm2, cs:__real@3fe0000000000000
0x180078eaf  cmp     [rbp+90h+arg_58], r12b
0x180078eb6  jz      loc_1800792BE
0x180078ebc  mov     [rbp+90h+arg_78], r12
0x180078ec3  mov     [rbp+90h+arg_68], r12
0x180078eca  mov     [rbp+90h+var_110], r12
0x180078ece  mov     qword ptr [rsp+190h+var_120], r12
0x180078ed3  mov     [rbp+90h+pv], r12
0x180078eda  lea     rax, [rbp+90h+arg_78]
0x180078ee1  mov     qword ptr [rbp+90h+var_100.Data1], rax
0x180078ee5  mov     qword ptr [rbp+90h+var_100.Data4], r12
0x180078ee9  mov     [rbp+90h+var_F0], 1
0x180078eed  mov     rsi, [rbp+90h+arg_40]
0x180078ef4  movaps  xmm0, xmmword ptr [rsi]
0x180078ef7  movdqa  xmmword ptr [rbp+90h+var_E0.Data1], xmm0
0x180078efc  lea     r9, [rbp+90h+var_100.Data4]; struct tWAVEFORMATEX **
0x180078f00  lea     r8, [rbp+90h+var_E0]; struct _GUID
0x180078f04  mov     r15d, [rbp+90h+arg_28]
0x180078f0b  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180078f0e  mov     rcx, [r13+8]; this
0x180078f12  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x180078f17  mov     ebx, eax
0x180078f19  lea     rcx, [rbp+90h+var_100]
0x180078f1d  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180078f22  test    ebx, ebx
  ... truncated ...
```
