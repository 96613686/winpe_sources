# CBtAudioResourceManagerBase::GetDefaultPrimaryProfileRenderSaDeviceParams(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,SaDeviceParams * *)

- ea: `0x1800f76f4`
- end: `0x1800f7e18`
- name: `?GetDefaultPrimaryProfileRenderSaDeviceParams@CBtAudioResourceManagerBase@@IEAAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUSaDeviceParams@@@Z`
- size: `1828`
- prototype: `int(CBtAudioResourceManagerBase *__hidden this, struct EndpointCharacteristicsDescriptor *, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct SaDeviceParams **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f64d4`

## callees

- `0x1800088dc`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18001df60`
- `0x18001eb4c`
- `0x180025d64`
- `0x180045068`
- `0x18004a38c`
- `0x18005b03c`
- `0x1800618c0`
- `0x180073310`
- `0x1800cf8c0`
- `0x1800f76f4`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f78d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f78eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f78ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7917`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7dc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7df0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f78d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f78eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f78ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7917`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7dc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7df0`

## string_xrefs

- `0x1800f77a6`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f78b6`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CBtAudioResourceManagerBase::GetDefaultPrimaryProfileRenderSaDeviceParams(
        CBtAudioResourceManagerBase *this,
        struct EndpointCharacteristicsDescriptor *a2,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a3,
        struct SaDeviceParams **a4)
{
  int v8; // eax
  int SharedModeEnginePeriodicity; // ebx
  __int64 v11; // rdx
  void *v12; // rcx
  void *v13; // rcx
  struct tWAVEFORMATEX *v14; // rcx
  bool v15; // zf
  struct tWAVEFORMATEX *v16; // rcx
  struct tWAVEFORMATEX *v17; // rbx
  _DWORD *v18; // r8
  int v19; // r8d
  int v20; // r9d
  unsigned int wFormatTag; // ecx
  _DWORD *v22; // r8
  int v23; // r8d
  int v24; // r9d
  _DWORD *v25; // r8
  int v26; // r8d
  int v27; // r9d
  struct tWAVEFORMATEX *v28; // rbx
  _DWORD *v29; // r8
  int v30; // r8d
  int v31; // r9d
  unsigned int v32; // ecx
  _DWORD *v33; // r8
  int v34; // r8d
  int v35; // r9d
  _DWORD *v36; // r8
  int v37; // r8d
  int v38; // r9d
  __int64 v39; // rbx
  struct tWAVEFORMATEX *v40; // rbx
  __int64 v41; // rdi
  struct tWAVEFORMATEX *Src; // rsi
  void *v43; // rcx
  void *v44; // rcx
  struct tWAVEFORMATEX *v45; // rcx
  struct tWAVEFORMATEX *v46; // rcx
  int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+80h] [rbp-80h] BYREF
  DWORD nSamplesPerSec; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD nAvgBytesPerSec; // [rsp+88h] [rbp-78h] BYREF
  struct tWAVEFORMATEX *v51; // [rsp+90h] [rbp-70h] BYREF
  struct tWAVEFORMATEX *v52; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v54; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID *p_pv; // [rsp+B0h] [rbp-50h] BYREF
  struct tWAVEFORMATEX *v56; // [rsp+B8h] [rbp-48h] BYREF
  char v57; // [rsp+C0h] [rbp-40h]
  struct tWAVEFORMATEX **v58; // [rsp+C8h] [rbp-38h] BYREF
  struct tWAVEFORMATEX *v59; // [rsp+D0h] [rbp-30h] BYREF
  char v60; // [rsp+D8h] [rbp-28h]
  struct tWAVEFORMATEX **v61; // [rsp+E0h] [rbp-20h] BYREF
  struct tWAVEFORMATEX *v62; // [rsp+E8h] [rbp-18h] BYREF
  char v63; // [rsp+F0h] [rbp-10h]
  struct _GUID v64; // [rsp+100h] [rbp+0h] BYREF
  struct _GUID v65; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID v66; // [rsp+120h] [rbp+20h] BYREF
  void *v67; // [rsp+130h] [rbp+30h] BYREF
  struct tWAVEFORMATEX *v68; // [rsp+138h] [rbp+38h] BYREF
  char v69; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v66 = GUID_00000000_0000_0000_0000_000000000000;
  v64 = GUID_00000000_0000_0000_0000_000000000000;
  v65 = GUID_00000000_0000_0000_0000_000000000000;
  v8 = DeriveAudioProcessingModeConfiguration(0, 0, 0, a2);
  SharedModeEnginePeriodicity = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
      (const char *)(unsigned int)v8,
      0);
    return (unsigned int)SharedModeEnginePeriodicity;
  }
  v51 = 0;
  v52 = 0;
  v54 = 0;
  pv = 0;
  v61 = &v51;
  v62 = 0;
  v63 = 1;
  v58 = &v52;
  v59 = 0;
  v60 = 1;
  p_pv = &pv;
  v56 = 0;
  v57 = 1;
  v67 = &v54;
  v68 = 0;
  v69 = 1;
  SharedModeEnginePeriodicity = DeriveDeviceGraphFormatsForStream(
                                  a2,
                                  0,
                                  a3,
                                  AUDCLNT_SHAREMODE_SHARED,
                                  0,
                                  &v65,
                                  &v64,
                                  &v66,
                                  0,
                                  &v68,
                                  &v56,
                                  &v59,
                                  &v62);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v67);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v58);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v61);
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v11 = 641;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
      (const char *)(unsigned int)SharedModeEnginePeriodicity,
      v47);
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    v13 = v54;
    v54 = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    v14 = v52;
    v15 = v52 == 0;
    v52 = 0;
    if ( !v15 )
      CoTaskMemFree(v14);
    v16 = v51;
    v51 = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    return (unsigned int)SharedModeEnginePeriodicity;
  }
  v17 = v52;
  if ( v52 )
  {
    wFormatTag = v52->wFormatTag;
    if ( (_WORD)wFormatTag == 0xFFFE )
    {
      v25 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v25 > 4u && (unsigned __int8)tlgKeywordOn(v25, 16896) )
      {
        nSamplesPerSec = *(_DWORD *)&v17[1].nChannels;
        *(_QWORD *)&v65.Data1 = (char *)v17 + 24;
        nAvgBytesPerSec = v52->nAvgBytesPerSec;
        LODWORD(v67) = v52->nSamplesPerSec;
        LOWORD(v48) = v52->nChannels;
        *(_QWORD *)&v64.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v26,
          (unsigned int)&unk_1801A36C7,
          v26,
          v27,
          (__int64)&v64,
          (__int64)&v48,
          (__int64)&v67,
          (__int64)&nAvgBytesPerSec,
          (__int64)&v65,
          (__int64)&nSamplesPerSec);
      }
    }
    else
    {
      *(_QWORD *)&v64.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v64.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v64.Data1 = wFormatTag;
      v22 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v22 > 4u && (unsigned __int8)tlgKeywordOn(v22, 16896) )
      {
        v67 = &v64;
        nAvgBytesPerSec = v52->nAvgBytesPerSec;
        nSamplesPerSec = v52->nSamplesPerSec;
        LOWORD(v48) = v52->nChannels;
        *(_QWORD *)&v65.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v23,
          (unsigned int)&unk_1801A3766,
          v23,
          v24,
          (__int64)&v65,
          (__int64)&v48,
          (__int64)&nSamplesPerSec,
          (__int64)&nAvgBytesPerSec,
          (__int64)&v67);
      }
    }
  }
  else
  {
    v18 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v18 > 4u && (unsigned __int8)tlgKeywordOn(v18, 16896) )
    {
      v48 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&unk_1801A37F8,
        v19,
        v20,
        (__int64)&v48);
    }
  }
  v28 = v51;
  if ( v51 )
  {
    v32 = v51->wFormatTag;
    if ( (_WORD)v32 == 0xFFFE )
    {
      v36 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v36 > 4u && (unsigned __int8)tlgKeywordOn(v36, 16896) )
      {
        LODWORD(v67) = *(_DWORD *)&v28[1].nChannels;
        *(_QWORD *)&v64.Data1 = (char *)v28 + 24;
        nSamplesPerSec = v51->nAvgBytesPerSec;
        nAvgBytesPerSec = v51->nSamplesPerSec;
        LOWORD(v48) = v51->nChannels;
        *(_QWORD *)&v65.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v37,
          (unsigned int)&unk_1801A3540,
          v37,
          v38,
          (__int64)&v65,
          (__int64)&v48,
          (__int64)&nAvgBytesPerSec,
          (__int64)&nSamplesPerSec,
          (__int64)&v64,
          (__int64)&v67);
      }
    }
    else
    {
      *(_QWORD *)&v66.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v66.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v66.Data1 = v32;
      v33 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v33 > 4u && (unsigned __int8)tlgKeywordOn(v33, 16896) )
      {
        *(_QWORD *)&v64.Data1 = &v66;
        LODWORD(v67) = v51->nAvgBytesPerSec;
        nSamplesPerSec = v51->nSamplesPerSec;
        LOWORD(v48) = v51->nChannels;
        *(_QWORD *)&v65.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v34,
          (unsigned int)&unk_1801A35DE,
          v34,
          v35,
          (__int64)&v65,
          (__int64)&v48,
          (__int64)&nSamplesPerSec,
          (__int64)&v67,
          (__int64)&v64);
      }
    }
  }
  else
  {
    v29 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v29 > 4u && (unsigned __int8)tlgKeywordOn(v29, 16896) )
    {
      LODWORD(v67) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)&unk_1801A366F,
        v30,
        v31,
        (__int64)&v67);
    }
  }
  v48 = 0;
  nSamplesPerSec = 0;
  LODWORD(v67) = 0;
  nAvgBytesPerSec = 0;
  v39 = *((_QWORD *)a2 + 1);
  v66 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, struct _GUID *))(*(_QWORD *)this
                                                                                                  + 128LL))(
                           this,
                           &v64);
  v47 = 0;
  SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(v39, (unsigned int)a3, v51, &v66);
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v11 = 647;
    goto LABEL_6;
  }
  v40 = v51;
  v41 = (unsigned int)(int)((double)v48 * 10000000.0 / (double)(int)v51->nSamplesPerSec + 0.5);
  Src = v52;
  v66 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, struct _GUID *))(*(_QWORD *)this
                                                                                                  + 128LL))(
                           this,
                           &v65);
  v64 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, void **))(*(_QWORD *)this + 128LL))(
                           this,
                           &v67);
  SharedModeEnginePeriodicity = DeriveSaDeviceParametersForStream(
                                  a2,
                                  AUDCLNT_SHAREMODE_SHARED,
                                  a3,
                                  &v64,
                                  &v66,
                                  v40,
                                  Src,
                                  v41,
                                  a4);
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v11 = 659;
    goto LABEL_6;
  }
  v43 = pv;
  pv = 0;
  if ( v43 )
    CoTaskMemFree(v43);
  v44 = v54;
  v54 = 0;
  if ( v44 )
    CoTaskMemFree(v44);
  v45 = v52;
  v52 = 0;
  if ( v45 )
    CoTaskMemFree(v45);
  v46 = v51;
  v51 = 0;
  if ( v46 )
    CoTaskMemFree(v46);
  return 0;
}

```

## disassembly

```asm
0x1800f76f4  push    rbp
0x1800f76f6  push    rbx
0x1800f76f7  push    rsi
0x1800f76f8  push    rdi
0x1800f76f9  push    r12
0x1800f76fb  push    r13
0x1800f76fd  push    r14
0x1800f76ff  push    r15
0x1800f7701  lea     rbp, [rsp-58h]
0x1800f7706  sub     rsp, 158h
0x1800f770d  mov     rax, cs:__security_cookie
0x1800f7714  xor     rax, rsp
0x1800f7717  mov     [rbp+90h+var_48], rax
0x1800f771b  mov     r13, r9
0x1800f771e  mov     r15d, r8d
0x1800f7721  mov     r14, rdx
0x1800f7724  mov     r12, rcx
0x1800f7727  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800f772e  movdqu  xmmword ptr [rbp+90h+var_70.Data1], xmm0
0x1800f7733  movdqu  xmmword ptr [rbp+90h+var_90.Data1], xmm0
0x1800f7738  movdqu  xmmword ptr [rbp+90h+var_80.Data1], xmm0
0x1800f773d  xor     edi, edi
0x1800f773f  mov     [rsp+190h+var_118], rdi
0x1800f7744  mov     [rsp+190h+var_120], rdi
0x1800f7749  lea     rax, [rbp+90h+var_80]
0x1800f774d  mov     [rsp+190h+var_128], rax
0x1800f7752  lea     rax, [rbp+90h+var_90]
0x1800f7756  mov     [rsp+190h+var_130], rax
0x1800f775b  lea     rax, [rbp+90h+var_70]
0x1800f775f  mov     [rsp+190h+var_138], rax
0x1800f7764  mov     [rsp+190h+var_140], rdi
0x1800f7769  mov     dword ptr [rsp+190h+var_148], 1
0x1800f7771  mov     dword ptr [rsp+190h+var_150], edi
0x1800f7775  mov     [rsp+190h+var_158], rdi
0x1800f777a  mov     dword ptr [rsp+190h+Src], r8d
0x1800f777f  mov     dword ptr [rsp+190h+var_168], edi
0x1800f7783  mov     dword ptr [rsp+190h+var_170], edi; int
0x1800f7787  mov     r9, rdx
0x1800f778a  xor     r8d, r8d
0x1800f778d  xor     edx, edx
0x1800f778f  xor     ecx, ecx
0x1800f7791  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x1800f7796  mov     ebx, eax
0x1800f7798  test    eax, eax
0x1800f779a  jns     short loc_1800F77BE
0x1800f779c  mov     rcx, [rbp+98h]; this
0x1800f77a3  mov     r9d, eax; char *
0x1800f77a6  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f77ad  mov     edx, 270h; void *
0x1800f77b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f77b7  mov     eax, ebx
0x1800f77b9  jmp     loc_1800F7DF8
0x1800f77be  mov     [rbp+90h+var_100], rdi
0x1800f77c2  mov     [rbp+90h+var_F8], rdi
0x1800f77c6  mov     [rbp+90h+var_E8], rdi
0x1800f77ca  mov     [rbp+90h+pv], rdi
0x1800f77ce  lea     rax, [rbp+90h+var_100]
0x1800f77d2  mov     [rbp+90h+var_B0], rax
0x1800f77d6  mov     [rbp+90h+var_A8], rdi
0x1800f77da  mov     [rbp+90h+var_A0], 1
0x1800f77de  lea     rax, [rbp+90h+var_F8]
0x1800f77e2  mov     [rbp+90h+var_C8], rax
0x1800f77e6  mov     [rbp+90h+var_C0], rdi
0x1800f77ea  mov     [rbp+90h+var_B8], 1
0x1800f77ee  lea     rax, [rbp+90h+pv]
0x1800f77f2  mov     [rbp+90h+var_E0], rax
0x1800f77f6  mov     [rbp+90h+var_D8], rdi
0x1800f77fa  mov     [rbp+90h+var_D0], 1
0x1800f77fe  lea     rax, [rbp+90h+var_E8]
0x1800f7802  mov     [rbp+90h+var_60], rax
0x1800f7806  mov     [rbp+90h+var_58], rdi
0x1800f780a  mov     [rbp+90h+var_50], 1
0x1800f780e  movaps  xmm0, xmmword ptr [rbp+90h+var_70.Data1]
0x1800f7812  movdqa  xmmword ptr [rbp+90h+var_70.Data1], xmm0
0x1800f7817  movaps  xmm1, xmmword ptr [rbp+90h+var_90.Data1]
0x1800f781b  movdqa  xmmword ptr [rbp+90h+var_90.Data1], xmm1
0x1800f7820  movaps  xmm0, xmmword ptr [rbp+90h+var_80.Data1]
0x1800f7824  movdqa  xmmword ptr [rbp+90h+var_80.Data1], xmm0
0x1800f7829  lea     rax, [rbp+90h+var_A8]
0x1800f782d  mov     [rsp+190h+var_130], rax; struct tWAVEFORMATEX **
0x1800f7832  lea     rax, [rbp+90h+var_C0]
0x1800f7836  mov     [rsp+190h+var_138], rax; struct tWAVEFORMATEX **
0x1800f783b  lea     rax, [rbp+90h+var_D8]
0x1800f783f  mov     [rsp+190h+var_140], rax; struct tWAVEFORMATEX **
0x1800f7844  lea     rax, [rbp+90h+var_58]
0x1800f7848  mov     [rsp+190h+var_148], rax; struct tWAVEFORMATEX **
0x1800f784d  mov     [rsp+190h+var_150], rdi; struct tWAVEFORMATEX *
0x1800f7852  lea     rax, [rbp+90h+var_70]
0x1800f7856  mov     [rsp+190h+var_158], rax; struct _GUID *
0x1800f785b  lea     rax, [rbp+90h+var_90]
0x1800f785f  mov     [rsp+190h+Src], rax; struct _GUID *
0x1800f7864  lea     rax, [rbp+90h+var_80]
0x1800f7868  mov     [rsp+190h+var_168], rax; struct _GUID *
0x1800f786d  mov     dword ptr [rsp+190h+var_170], edi; int
0x1800f7871  xor     r9d, r9d; enum _AUDCLNT_SHAREMODE
0x1800f7874  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800f7877  xor     edx, edx; bool
0x1800f7879  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x1800f787c  call    ?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z; DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)
0x1800f7881  mov     ebx, eax
0x1800f7883  lea     rcx, [rbp+90h+var_60]
0x1800f7887  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f788c  nop
0x1800f788d  lea     rcx, [rbp+90h+var_E0]
0x1800f7891  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f7896  nop
0x1800f7897  lea     rcx, [rbp+90h+var_C8]
0x1800f789b  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f78a0  nop
0x1800f78a1  lea     rcx, [rbp+90h+var_B0]
0x1800f78a5  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f78aa  test    ebx, ebx
0x1800f78ac  jns     short loc_1800F7922
0x1800f78ae  mov     edx, 281h; void *
0x1800f78b3  mov     r9d, ebx; char *
0x1800f78b6  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f78bd  mov     rcx, [rbp+98h]; this
0x1800f78c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f78c9  nop
0x1800f78ca  mov     rcx, [rbp+90h+pv]; pv
0x1800f78ce  mov     [rbp+90h+pv], rdi
0x1800f78d2  test    rcx, rcx
0x1800f78d5  jz      short loc_1800F78DE
0x1800f78d7  call    cs:__imp_CoTaskMemFree
0x1800f78dd  nop
0x1800f78de  mov     rcx, [rbp+90h+var_E8]; pv
0x1800f78e2  mov     [rbp+90h+var_E8], rdi
0x1800f78e6  test    rcx, rcx
0x1800f78e9  jz      short loc_1800F78F2
0x1800f78eb  call    cs:__imp_CoTaskMemFree
0x1800f78f1  nop
0x1800f78f2  mov     rcx, [rbp+90h+var_F8]; pv
0x1800f78f6  test    rcx, rcx
0x1800f78f9  mov     [rbp+90h+var_F8], rdi
0x1800f78fd  jz      short loc_1800F7906
0x1800f78ff  call    cs:__imp_CoTaskMemFree
0x1800f7905  nop
0x1800f7906  mov     rcx, [rbp+90h+var_100]; pv
0x1800f790a  mov     [rbp+90h+var_100], rdi
0x1800f790e  test    rcx, rcx
0x1800f7911  jz      loc_1800F77B7
0x1800f7917  call    cs:__imp_CoTaskMemFree
0x1800f791d  jmp     loc_1800F77B7
0x1800f7922  mov     eax, 0FFFEh
0x1800f7927  mov     esi, 4200h
0x1800f792c  mov     rbx, [rbp+90h+var_F8]
0x1800f7930  test    rbx, rbx
0x1800f7933  jnz     short loc_1800F797C
0x1800f7935  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f793a  mov     r8, [rax+8]
0x1800f793e  mov     eax, [r8]
0x1800f7941  cmp     eax, 4
0x1800f7944  jbe     loc_1800F7ACF
0x1800f794a  mov     edx, esi
0x1800f794c  mov     rcx, r8
0x1800f794f  call    _tlgKeywordOn
0x1800f7954  test    al, al
0x1800f7956  jz      loc_1800F7ACF
0x1800f795c  mov     [rbp+90h+var_110], edi
0x1800f795f  lea     rax, [rbp+90h+var_110]
0x1800f7963  mov     [rsp+190h+var_170], rax
0x1800f7968  lea     rdx, unk_1801A37F8
0x1800f796f  mov     rcx, r8
0x1800f7972  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800f7977  jmp     loc_1800F7ACF
0x1800f797c  movzx   ecx, word ptr [rbx]
0x1800f797f  cmp     cx, ax
0x1800f7982  jz      loc_1800F7A35
0x1800f7988  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x1800f7990  movsd   qword ptr [rbp+90h+var_90.Data2], xmm0
0x1800f7995  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x1800f799b  mov     dword ptr [rbp+90h+var_90.Data4+4], eax
0x1800f799e  mov     [rbp+90h+var_90.Data1], ecx
0x1800f79a1  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f79a6  mov     r8, [rax+8]
0x1800f79aa  mov     eax, [r8]
0x1800f79ad  cmp     eax, 4
0x1800f79b0  jbe     loc_1800F7ACF
0x1800f79b6  mov     rdx, rsi
0x1800f79b9  mov     rcx, r8
0x1800f79bc  call    _tlgKeywordOn
0x1800f79c1  test    al, al
0x1800f79c3  jz      loc_1800F7ACF
0x1800f79c9  lea     rax, [rbp+90h+var_90]
0x1800f79cd  mov     [rbp+90h+var_60], rax
0x1800f79d1  mov     rax, [rbp+90h+var_F8]
0x1800f79d5  mov     ecx, [rax+8]
0x1800f79d8  mov     [rbp+90h+var_108], ecx
0x1800f79db  mov     ecx, [rax+4]
0x1800f79de  mov     [rbp+90h+var_10C], ecx
0x1800f79e1  movzx   ecx, word ptr [rax+2]
0x1800f79e5  mov     word ptr [rbp+90h+var_110], cx
0x1800f79e9  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x1800f79f0  mov     qword ptr [rbp+90h+var_80.Data1], rax
0x1800f79f4  lea     rax, [rbp+90h+var_60]
0x1800f79f8  mov     [rsp+190h+var_150], rax
0x1800f79fd  lea     rax, [rbp+90h+var_108]
0x1800f7a01  mov     [rsp+190h+var_158], rax
0x1800f7a06  lea     rax, [rbp+90h+var_10C]
0x1800f7a0a  mov     [rsp+190h+Src], rax
0x1800f7a0f  lea     rax, [rbp+90h+var_110]
0x1800f7a13  mov     [rsp+190h+var_168], rax
0x1800f7a18  lea     rax, [rbp+90h+var_80]
0x1800f7a1c  mov     [rsp+190h+var_170], rax
0x1800f7a21  lea     rdx, unk_1801A3766
0x1800f7a28  mov     rcx, r8
0x1800f7a2b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800f7a30  jmp     loc_1800F7ACF
0x1800f7a35  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f7a3a  mov     r8, [rax+8]
0x1800f7a3e  mov     eax, [r8]
0x1800f7a41  cmp     eax, 4
0x1800f7a44  jbe     loc_1800F7ACF
0x1800f7a4a  mov     rdx, rsi
0x1800f7a4d  mov     rcx, r8
0x1800f7a50  call    _tlgKeywordOn
0x1800f7a55  test    al, al
0x1800f7a57  jz      short loc_1800F7ACF
0x1800f7a59  mov     eax, [rbx+14h]
0x1800f7a5c  mov     [rbp+90h+var_10C], eax
0x1800f7a5f  lea     rax, [rbx+18h]
0x1800f7a63  mov     qword ptr [rbp+90h+var_80.Data1], rax
0x1800f7a67  mov     rax, [rbp+90h+var_F8]
0x1800f7a6b  mov     ecx, [rax+8]
0x1800f7a6e  mov     [rbp+90h+var_108], ecx
0x1800f7a71  mov     ecx, [rax+4]
0x1800f7a74  mov     dword ptr [rbp+90h+var_60], ecx
0x1800f7a77  movzx   ecx, word ptr [rax+2]
0x1800f7a7b  mov     word ptr [rbp+90h+var_110], cx
0x1800f7a7f  lea     rax, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x1800f7a86  mov     qword ptr [rbp+90h+var_90.Data1], rax
0x1800f7a8a  lea     rax, [rbp+90h+var_10C]
0x1800f7a8e  mov     [rsp+190h+var_148], rax
0x1800f7a93  lea     rax, [rbp+90h+var_80]
0x1800f7a97  mov     [rsp+190h+var_150], rax
0x1800f7a9c  lea     rax, [rbp+90h+var_108]
0x1800f7aa0  mov     [rsp+190h+var_158], rax
0x1800f7aa5  lea     rax, [rbp+90h+var_60]
0x1800f7aa9  mov     [rsp+190h+Src], rax
0x1800f7aae  lea     rax, [rbp+90h+var_110]
0x1800f7ab2  mov     [rsp+190h+var_168], rax
0x1800f7ab7  lea     rax, [rbp+90h+var_90]
0x1800f7abb  mov     [rsp+190h+var_170], rax
0x1800f7ac0  lea     rdx, unk_1801A36C7
0x1800f7ac7  mov     rcx, r8
0x1800f7aca  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800f7acf  mov     rbx, [rbp+90h+var_100]
0x1800f7ad3  test    rbx, rbx
0x1800f7ad6  jnz     short loc_1800F7B20
0x1800f7ad8  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f7add  mov     r8, [rax+8]
0x1800f7ae1  mov     eax, [r8]
0x1800f7ae4  cmp     eax, 4
0x1800f7ae7  jbe     loc_1800F7C78
0x1800f7aed  mov     rdx, rsi
0x1800f7af0  mov     rcx, r8
0x1800f7af3  call    _tlgKeywordOn
0x1800f7af8  test    al, al
0x1800f7afa  jz      loc_1800F7C78
0x1800f7b00  mov     dword ptr [rbp+90h+var_60], edi
0x1800f7b03  lea     rax, [rbp+90h+var_60]
0x1800f7b07  mov     [rsp+190h+var_170], rax
0x1800f7b0c  lea     rdx, unk_1801A366F
0x1800f7b13  mov     rcx, r8
0x1800f7b16  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800f7b1b  jmp     loc_1800F7C78
0x1800f7b20  movzx   ecx, word ptr [rbx]
0x1800f7b23  mov     eax, 0FFFEh
0x1800f7b28  cmp     cx, ax
0x1800f7b2b  jz      loc_1800F7BDE
0x1800f7b31  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x1800f7b39  movsd   qword ptr [rbp+90h+var_70.Data2], xmm0
0x1800f7b3e  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x1800f7b44  mov     dword ptr [rbp+90h+var_70.Data4+4], eax
0x1800f7b47  mov     [rbp+90h+var_70.Data1], ecx
0x1800f7b4a  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f7b4f  mov     r8, [rax+8]
0x1800f7b53  mov     eax, [r8]
0x1800f7b56  cmp     eax, 4
0x1800f7b59  jbe     loc_1800F7C78
0x1800f7b5f  mov     rdx, rsi
0x1800f7b62  mov     rcx, r8
0x1800f7b65  call    _tlgKeywordOn
0x1800f7b6a  test    al, al
0x1800f7b6c  jz      loc_1800F7C78
0x1800f7b72  lea     rax, [rbp+90h+var_70]
0x1800f7b76  mov     qword ptr [rbp+90h+var_90.Data1], rax
0x1800f7b7a  mov     rax, [rbp+90h+var_100]
0x1800f7b7e  mov     ecx, [rax+8]
0x1800f7b81  mov     dword ptr [rbp+90h+var_60], ecx
0x1800f7b84  mov     ecx, [rax+4]
0x1800f7b87  mov     [rbp+90h+var_10C], ecx
0x1800f7b8a  movzx   ecx, word ptr [rax+2]
0x1800f7b8e  mov     word ptr [rbp+90h+var_110], cx
0x1800f7b92  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x1800f7b99  mov     qword ptr [rbp+90h+var_80.Data1], rax
0x1800f7b9d  lea     rax, [rbp+90h+var_90]
0x1800f7ba1  mov     [rsp+190h+var_150], rax
0x1800f7ba6  lea     rax, [rbp+90h+var_60]
0x1800f7baa  mov     [rsp+190h+var_158], rax
  ... truncated ...
```
