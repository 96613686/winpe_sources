# DerivePeriodicityForStream(EndpointCharacteristicsDescriptor *,tWAVEFORMATEX *,IAudioStreamInfo *,ulong,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID,_GUID,_GUID,bool,bool,__int64,__int64,IProcessSubmixProxy *,__int64 *,__int64 *,__int64 *)

- ea: `0x180078510`
- end: `0x180078e26`
- name: `?DerivePeriodicityForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@PEAUtWAVEFORMATEX@@PEAUIAudioStreamInfo@@KW4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@1U_GUID@@55_N6_J7PEAUIProcessSubmixProxy@@PEA_J99@Z`
- size: `2326`
- prototype: `__int64 __usercall@<rax>(struct EndpointCharacteristicsDescriptor *@<rcx>, struct tWAVEFORMATEX *@<rdx>, struct IAudioStreamInfo *@<r8>, unsigned int@<r9d>, enum _AUDCLNT_SHAREMODE, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct tWAVEFORMATEX *, struct _GUID *, struct _GUID *, struct _GUID *, bool, bool, __int64, LPVOID, struct IProcessSubmixProxy *, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180073490`

## callees

- `0x180008a2c`
- `0x18000ae1c`
- `0x18001280c`
- `0x18001ec9c`
- `0x18001f800`
- `0x1800424ec`
- `0x180044bd8`
- `0x180078510`
- `0x1800ce6e4`
- `0x1800e51a4`
- `0x180122054`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180078749`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180078749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078a77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078aa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078ac3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078bfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078c28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078c42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078a77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078aa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078ac3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078bfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078c28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078c42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078db8`

## string_xrefs

- `0x180078681`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800787f5`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180078a3c`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180078bd7`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

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
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::GetImpl'::`2'::impl) )
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
0x180078510  mov     rax, rsp
0x180078513  mov     [rax+8], rbx
0x180078517  mov     [rax+18h], r8
0x18007851b  mov     [rax+10h], rdx
0x18007851f  push    rbp
0x180078520  push    rsi
0x180078521  push    rdi
0x180078522  push    r12
0x180078524  push    r13
0x180078526  push    r14
0x180078528  push    r15
0x18007852a  lea     rbp, [rsp-60h]
0x18007852f  sub     rsp, 160h
0x180078536  movaps  xmmword ptr [rax-48h], xmm6
0x18007853a  movaps  xmmword ptr [rax-58h], xmm7
0x18007853e  movaps  xmmword ptr [rax-68h], xmm8
0x180078543  mov     r13, rcx
0x180078546  mov     rbx, [rbp+90h+arg_68]
0x18007854d  mov     rdi, [rbp+90h+arg_78]
0x180078554  mov     [rdi], rbx
0x180078557  mov     r12, [rbp+90h+pv]
0x18007855e  mov     [r12], rbx
0x180078562  mov     eax, [rbp+90h+arg_20]
0x180078568  xor     r15d, r15d
0x18007856b  test    eax, eax
0x18007856d  jnz     loc_180078DFA
0x180078573  bt      r9d, 11h
0x180078578  jnb     short loc_1800785DC
0x18007857a  mov     rsi, [rbp+90h+arg_70]
0x180078581  test    rsi, rsi
0x180078584  jz      short loc_1800785DC
0x180078586  mov     [rbp+90h+arg_68], r15
0x18007858d  mov     rax, [rsi]
0x180078590  mov     rbx, [rax+40h]
0x180078594  lea     rcx, [rbp+90h+arg_68]
0x18007859b  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800785a0  lea     rdx, [rbp+90h+arg_68]
0x1800785a7  mov     rcx, rsi
0x1800785aa  mov     rax, rbx
0x1800785ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800785b2  mov     rcx, [rbp+90h+arg_68]
0x1800785b9  mov     rax, [rcx]
0x1800785bc  mov     rax, [rax+80h]
0x1800785c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800785c8  mov     [rdi], rax
0x1800785cb  lea     rcx, [rbp+90h+arg_68]
0x1800785d2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800785d7  jmp     loc_180078DFA
0x1800785dc  test    eax, eax
0x1800785de  jnz     loc_180078DFA
0x1800785e4  test    r9b, 1
0x1800785e8  jnz     loc_180078DEB
0x1800785ee  mov     [rbp+90h+arg_20], r15d
0x1800785f5  mov     dword ptr [rbp+90h+pv], r15d
0x1800785fc  mov     dword ptr [rbp+90h+arg_68], r15d
0x180078603  mov     dword ptr [rbp+90h+arg_78], r15d
0x18007860a  mov     rax, [rbp+90h+arg_38]
0x180078611  movaps  xmm0, xmmword ptr [rax]
0x180078614  movdqa  xmmword ptr [rbp+90h+var_110], xmm0
0x180078619  movzx   eax, [rbp+90h+arg_50]
0x180078620  lea     rcx, [rbp+90h+arg_68]
0x180078627  mov     [rsp+190h+var_150], rcx
0x18007862c  lea     rcx, [rbp+90h+pv]
0x180078633  mov     [rsp+190h+var_158], rcx
0x180078638  lea     rcx, [rbp+90h+arg_78]
0x18007863f  mov     [rsp+190h+pcbData], rcx
0x180078644  lea     rcx, [rbp+90h+arg_20]
0x18007864b  mov     [rsp+190h+pvData], rcx
0x180078650  mov     dword ptr [rsp+190h+pdwType], eax; int
0x180078654  lea     r9, [rbp+90h+var_110]
0x180078658  mov     r14, [rbp+90h+arg_30]
0x18007865f  mov     r8, r14
0x180078662  mov     edx, [rbp+90h+arg_28]
0x180078668  mov     rcx, [r13+8]
0x18007866c  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x180078671  mov     esi, eax
0x180078673  test    eax, eax
0x180078675  jns     short loc_180078699
0x180078677  mov     rcx, [rbp+98h]; this
0x18007867e  mov     r9d, eax; char *
0x180078681  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180078688  mov     edx, 51Fh; void *
0x18007868d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078692  mov     eax, esi
0x180078694  jmp     loc_180078DFC
0x180078699  mov     r15d, [rbp+90h+arg_20]
0x1800786a0  xorps   xmm6, xmm6
0x1800786a3  cvtsi2sd xmm6, r15
0x1800786a8  mulsd   xmm6, cs:__real@416312d000000000
0x1800786b0  mov     eax, [r14+4]
0x1800786b4  xorps   xmm0, xmm0
0x1800786b7  cvtsi2sd xmm0, rax
0x1800786bc  movaps  xmm1, xmm6
0x1800786bf  divsd   xmm1, xmm0
0x1800786c3  movsd   xmm2, cs:__real@3fe0000000000000
0x1800786cb  addsd   xmm1, xmm2
0x1800786cf  cvttsd2si rax, xmm1
0x1800786d4  mov     [r12], rax
0x1800786d8  xor     r12d, r12d
0x1800786db  test    rbx, rbx
0x1800786de  jnz     short loc_180078704
0x1800786e0  mov     eax, [r14+4]
0x1800786e4  xorps   xmm0, xmm0
0x1800786e7  cvtsi2sd xmm0, rax
0x1800786ec  movaps  xmm1, xmm6
0x1800786ef  divsd   xmm1, xmm0
0x1800786f3  addsd   xmm1, xmm2
0x1800786f7  cvttsd2si rax, xmm1
0x1800786fc  mov     [rdi], rax
0x1800786ff  jmp     loc_1800789B7
0x180078704  mov     [rbp+90h+arg_20], r12d
0x18007870b  mov     [rsp+190h+var_120], 4
0x180078713  lea     rax, [rsp+190h+var_120]
0x180078718  mov     [rsp+190h+pcbData], rax; pcbData
0x18007871d  lea     rax, [rbp+90h+arg_20]
0x180078724  mov     [rsp+190h+pvData], rax; pvData
0x180078729  mov     [rsp+190h+pdwType], r12; int
0x18007872e  mov     r9d, 18h; dwFlags
0x180078734  lea     r8, aSkipperiodicit; "SkipPeriodicityValidation"
0x18007873b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180078742  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180078749  call    cs:__imp_RegGetValueW
0x18007874f  cmp     [rbp+90h+arg_20], r12d
0x180078756  jnz     loc_1800789AF
0x18007875c  xorps   xmm3, xmm3
0x18007875f  cvtsi2sd xmm3, rbx
0x180078764  mov     r11d, [r14+4]
0x180078768  xorps   xmm0, xmm0
0x18007876b  cvtsi2sd xmm0, r11
0x180078770  mulsd   xmm0, xmm3
0x180078774  movsd   xmm7, cs:__real@416312d000000000
0x18007877c  divsd   xmm0, xmm7
0x180078780  movsd   xmm8, cs:__real@3fe0000000000000
0x180078789  addsd   xmm0, xmm8
0x18007878e  cvttsd2si rbx, xmm0
0x180078793  mov     r9d, dword ptr [rbp+90h+arg_68]
0x18007879a  mov     r12d, dword ptr [rbp+90h+arg_78]
0x1800787a1  mov     r10d, dword ptr [rbp+90h+pv]
0x1800787a8  cmp     ebx, r10d
0x1800787ab  jb      short loc_1800787DC
0x1800787ad  cmp     ebx, r9d
0x1800787b0  ja      short loc_1800787DC
0x1800787b2  xor     edx, edx
0x1800787b4  mov     eax, ebx
0x1800787b6  div     r12d
0x1800787b9  test    edx, edx
0x1800787bb  jz      loc_180078983
0x1800787c1  cmp     ebx, r15d
0x1800787c4  jz      loc_180078983
0x1800787ca  cmp     ebx, r10d
0x1800787cd  jz      loc_180078983
0x1800787d3  cmp     ebx, r9d
0x1800787d6  jz      loc_180078983
0x1800787dc  mov     rbx, [rbp+90h+arg_8]
0x1800787e3  mov     ebx, [rbx+4]
0x1800787e6  cmp     ebx, r11d
0x1800787e9  jnz     short loc_180078812
0x1800787eb  mov     edx, 541h; void *
0x1800787f0  mov     ebx, 88890020h
0x1800787f5  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800787fc  mov     r9d, ebx; char *
0x1800787ff  mov     rcx, [rbp+98h]; this
0x180078806  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007880b  mov     eax, ebx
0x18007880d  jmp     loc_180078DFC
0x180078812  mov     r8d, ebx; unsigned int
0x180078815  mov     edx, r11d; unsigned int
0x180078818  mov     ecx, r15d; unsigned int
0x18007881b  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180078820  mov     dword ptr [rbp+90h+arg_68], eax
0x180078826  mov     ecx, r12d; unsigned int
0x180078829  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x18007882e  mov     esi, eax
0x180078830  mov     ecx, r10d; unsigned int
0x180078833  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180078838  mov     dword ptr [rbp+90h+arg_78], eax
0x18007883e  mov     ecx, r9d; unsigned int
0x180078841  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180078846  mov     r8d, eax
0x180078849  xorps   xmm2, xmm2
0x18007884c  cvtsi2sd xmm2, rbx
0x180078851  mulsd   xmm2, xmm3
0x180078855  divsd   xmm2, xmm7
0x180078859  addsd   xmm2, xmm8
0x18007885e  cvttsd2si rbx, xmm2
0x180078863  mov     ecx, dword ptr [rbp+90h+arg_78]
0x180078869  cmp     ebx, ecx
0x18007886b  jb      short loc_180078890
0x18007886d  cmp     ebx, eax
0x18007886f  ja      short loc_180078890
0x180078871  xor     edx, edx
0x180078873  mov     eax, ebx
0x180078875  div     esi
0x180078877  mov     esi, eax
0x180078879  mov     eax, dword ptr [rbp+90h+arg_68]
0x18007887f  test    edx, edx
0x180078881  jz      short loc_18007889A
0x180078883  cmp     ebx, eax
0x180078885  jz      short loc_18007889E
0x180078887  cmp     ebx, ecx
0x180078889  jz      short loc_1800788AA
0x18007888b  cmp     ebx, r8d
0x18007888e  jz      short loc_1800788B7
0x180078890  mov     edx, 555h
0x180078895  jmp     loc_1800787F0
0x18007889a  cmp     ebx, eax
0x18007889c  jnz     short loc_1800788A6
0x18007889e  mov     ebx, r15d
0x1800788a1  jmp     loc_180078958
0x1800788a6  cmp     ebx, ecx
0x1800788a8  jnz     short loc_1800788B2
0x1800788aa  mov     ebx, r10d
0x1800788ad  jmp     loc_180078958
0x1800788b2  cmp     ebx, r8d
0x1800788b5  jnz     short loc_1800788BF
0x1800788b7  mov     ebx, r9d
0x1800788ba  jmp     loc_180078958
0x1800788bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::GetImpl(void)'::`2'::impl
0x1800788c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PeriodicityForMismatchedStreamFormats>::__private_IsEnabled(void)
0x1800788cb  movsd   xmm7, cs:__real@416312d000000000
0x1800788d3  movsd   xmm8, cs:__real@3fe0000000000000
0x1800788dc  test    al, al
0x1800788de  jz      short loc_180078952
0x1800788e0  mov     eax, ebx
0x1800788e2  xorps   xmm0, xmm0
0x1800788e5  cvtsi2ss xmm0, rax
0x1800788ea  xorps   xmm2, xmm2
0x1800788ed  cvtsi2sd xmm2, r12
0x1800788f2  mulsd   xmm2, xmm7
0x1800788f6  mov     eax, [r14+4]
0x1800788fa  xorps   xmm1, xmm1
0x1800788fd  cvtsi2sd xmm1, rax
0x180078902  divsd   xmm2, xmm1
0x180078906  addsd   xmm2, xmm8
0x18007890b  cvttsd2si rax, xmm2
0x180078910  xorps   xmm2, xmm2
0x180078913  cvtsi2sd xmm2, rax
0x180078918  mov     rax, [rbp+90h+arg_8]
0x18007891f  mov     eax, [rax+4]
0x180078922  xorps   xmm1, xmm1
0x180078925  cvtsi2sd xmm1, rax
0x18007892a  mulsd   xmm2, xmm1
0x18007892e  divsd   xmm2, xmm7
0x180078932  cvtpd2ps xmm1, xmm2
0x180078936  divss   xmm0, xmm1; X
0x18007893a  call    _o_ceilf_0
0x18007893f  xorps   xmm1, xmm1
0x180078942  cvtsi2ss xmm1, r12
0x180078947  mulss   xmm0, xmm1
0x18007894b  cvttss2si rbx, xmm0
0x180078950  jmp     short loc_180078958
0x180078952  imul    esi, r12d
0x180078956  mov     ebx, esi
0x180078958  mov     eax, ebx
0x18007895a  xorps   xmm1, xmm1
0x18007895d  cvtsi2sd xmm1, rax
0x180078962  mulsd   xmm1, xmm7
0x180078966  mov     eax, [r14+4]
0x18007896a  xorps   xmm0, xmm0
0x18007896d  cvtsi2sd xmm0, rax
0x180078972  divsd   xmm1, xmm0
0x180078976  addsd   xmm1, xmm8
0x18007897b  cvttsd2si rax, xmm1
0x180078980  mov     [rdi], rax
0x180078983  mov     rcx, [rbp+90h+arg_10]
0x18007898a  mov     rax, [rcx]
0x18007898d  mov     rax, [rax+98h]
0x180078994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078999  xor     r12d, r12d
0x18007899c  test    al, al
0x18007899e  jz      short loc_1800789AF
0x1800789a0  cmp     ebx, r15d
0x1800789a3  jnb     short loc_1800789AF
0x1800789a5  mov     edx, 56Fh
0x1800789aa  jmp     loc_1800787F0
0x1800789af  movsd   xmm2, cs:__real@3fe0000000000000
0x1800789b7  cmp     [rbp+90h+arg_58], r12b
0x1800789be  jz      loc_180078DC6
0x1800789c4  mov     [rbp+90h+arg_78], r12
0x1800789cb  mov     [rbp+90h+arg_68], r12
0x1800789d2  mov     [rbp+90h+var_110], r12
0x1800789d6  mov     qword ptr [rsp+190h+var_120], r12
0x1800789db  mov     [rbp+90h+pv], r12
0x1800789e2  lea     rax, [rbp+90h+arg_78]
0x1800789e9  mov     qword ptr [rbp+90h+var_100.Data1], rax
0x1800789ed  mov     qword ptr [rbp+90h+var_100.Data4], r12
0x1800789f1  mov     [rbp+90h+var_F0], 1
0x1800789f5  mov     rsi, [rbp+90h+arg_40]
0x1800789fc  movaps  xmm0, xmmword ptr [rsi]
0x1800789ff  movdqa  xmmword ptr [rbp+90h+var_E0.Data1], xmm0
0x180078a04  lea     r9, [rbp+90h+var_100.Data4]; struct tWAVEFORMATEX **
0x180078a08  lea     r8, [rbp+90h+var_E0]; struct _GUID
0x180078a0c  mov     r15d, [rbp+90h+arg_28]
0x180078a13  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180078a16  mov     rcx, [r13+8]; this
0x180078a1a  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x180078a1f  mov     ebx, eax
0x180078a21  lea     rcx, [rbp+90h+var_100]
0x180078a25  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180078a2a  test    ebx, ebx
  ... truncated ...
```
