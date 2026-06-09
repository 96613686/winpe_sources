# CBtAudioResourceManagerBase::GetDefaultPrimaryProfileRenderSaDeviceParams(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,SaDeviceParams * *)

- ea: `0x1800f7984`
- end: `0x1800f80a8`
- name: `?GetDefaultPrimaryProfileRenderSaDeviceParams@CBtAudioResourceManagerBase@@IEAAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUSaDeviceParams@@@Z`
- size: `1828`
- prototype: `int(CBtAudioResourceManagerBase *__hidden this, struct EndpointCharacteristicsDescriptor *, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct SaDeviceParams **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f6764`

## callees

- `0x180008a2c`
- `0x18001280c`
- `0x18001b520`
- `0x18001e0b0`
- `0x18001ec9c`
- `0x180025eb4`
- `0x180044bd8`
- `0x180049efc`
- `0x18005abac`
- `0x180061430`
- `0x180072e10`
- `0x1800cd8d0`
- `0x1800f7984`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7b7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7b8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7ba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8058`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f806c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7b7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7b8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7ba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8058`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f806c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8080`

## string_xrefs

- `0x1800f7a36`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f7b46`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CBtAudioResourceManagerBase::GetDefaultPrimaryProfileRenderSaDeviceParams(
        CBtAudioResourceManagerBase *this,
        CEndpointCharacteristics **a2,
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
  CEndpointCharacteristics *v39; // rbx
  struct tWAVEFORMATEX *v40; // rbx
  __int64 v41; // rdi
  struct tWAVEFORMATEX *Src; // rsi
  void *v43; // rcx
  void *v44; // rcx
  struct tWAVEFORMATEX *v45; // rcx
  struct tWAVEFORMATEX *v46; // rcx
  int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+80h] [rbp-80h] BYREF
  DWORD nSamplesPerSec; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD nAvgBytesPerSec; // [rsp+88h] [rbp-78h] BYREF
  struct tWAVEFORMATEX *v52; // [rsp+90h] [rbp-70h] BYREF
  struct tWAVEFORMATEX *v53; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v55; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID *p_pv; // [rsp+B0h] [rbp-50h] BYREF
  struct tWAVEFORMATEX *v57; // [rsp+B8h] [rbp-48h] BYREF
  char v58; // [rsp+C0h] [rbp-40h]
  struct tWAVEFORMATEX **v59; // [rsp+C8h] [rbp-38h] BYREF
  struct tWAVEFORMATEX *v60; // [rsp+D0h] [rbp-30h] BYREF
  char v61; // [rsp+D8h] [rbp-28h]
  struct tWAVEFORMATEX **v62; // [rsp+E0h] [rbp-20h] BYREF
  struct tWAVEFORMATEX *v63; // [rsp+E8h] [rbp-18h] BYREF
  char v64; // [rsp+F0h] [rbp-10h]
  struct _GUID v65; // [rsp+100h] [rbp+0h] BYREF
  struct _GUID v66; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID v67; // [rsp+120h] [rbp+20h] BYREF
  void *v68; // [rsp+130h] [rbp+30h] BYREF
  struct tWAVEFORMATEX *v69; // [rsp+138h] [rbp+38h] BYREF
  char v70; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v67 = GUID_00000000_0000_0000_0000_000000000000;
  v65 = GUID_00000000_0000_0000_0000_000000000000;
  v66 = GUID_00000000_0000_0000_0000_000000000000;
  v8 = DeriveAudioProcessingModeConfiguration(0, 0, 0, a2, 0, 0, a3, 0, 0, 1, 0, &v67, &v65, &v66, 0, 0);
  SharedModeEnginePeriodicity = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
      (const char *)(unsigned int)v8,
      v47);
    return (unsigned int)SharedModeEnginePeriodicity;
  }
  v52 = 0;
  v53 = 0;
  v55 = 0;
  pv = 0;
  v62 = &v52;
  v63 = 0;
  v64 = 1;
  v59 = &v53;
  v60 = 0;
  v61 = 1;
  p_pv = &pv;
  v57 = 0;
  v58 = 1;
  v68 = &v55;
  v69 = 0;
  v70 = 1;
  SharedModeEnginePeriodicity = DeriveDeviceGraphFormatsForStream(
                                  a2,
                                  0,
                                  a3,
                                  AUDCLNT_SHAREMODE_SHARED,
                                  0,
                                  (IAudioMediaType *)&v66,
                                  &v65,
                                  &v67,
                                  0,
                                  &v69,
                                  &v57,
                                  &v60,
                                  &v63);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v68);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v59);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v62);
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v11 = 641;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
      (const char *)(unsigned int)SharedModeEnginePeriodicity,
      v48);
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    v13 = v55;
    v55 = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    v14 = v53;
    v15 = v53 == 0;
    v53 = 0;
    if ( !v15 )
      CoTaskMemFree(v14);
    v16 = v52;
    v52 = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    return (unsigned int)SharedModeEnginePeriodicity;
  }
  v17 = v53;
  if ( v53 )
  {
    wFormatTag = v53->wFormatTag;
    if ( (_WORD)wFormatTag == 0xFFFE )
    {
      v25 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v25 > 4u && (unsigned __int8)tlgKeywordOn(v25, 16896) )
      {
        nSamplesPerSec = *(_DWORD *)&v17[1].nChannels;
        *(_QWORD *)&v66.Data1 = (char *)v17 + 24;
        nAvgBytesPerSec = v53->nAvgBytesPerSec;
        LODWORD(v68) = v53->nSamplesPerSec;
        LOWORD(v49) = v53->nChannels;
        *(_QWORD *)&v65.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v26,
          (unsigned int)word_1801A490A,
          v26,
          v27,
          (__int64)&v65,
          (__int64)&v49,
          (__int64)&v68,
          (__int64)&nAvgBytesPerSec,
          (__int64)&v66,
          (__int64)&nSamplesPerSec);
      }
    }
    else
    {
      *(_QWORD *)&v65.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v65.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v65.Data1 = wFormatTag;
      v22 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v22 > 4u && (unsigned __int8)tlgKeywordOn(v22, 16896) )
      {
        v68 = &v65;
        nAvgBytesPerSec = v53->nAvgBytesPerSec;
        nSamplesPerSec = v53->nSamplesPerSec;
        LOWORD(v49) = v53->nChannels;
        *(_QWORD *)&v66.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v23,
          (unsigned int)byte_1801A49A9,
          v23,
          v24,
          (__int64)&v66,
          (__int64)&v49,
          (__int64)&nSamplesPerSec,
          (__int64)&nAvgBytesPerSec,
          (__int64)&v68);
      }
    }
  }
  else
  {
    v18 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v18 > 4u && (unsigned __int8)tlgKeywordOn(v18, 16896) )
    {
      v49 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)byte_1801A4A3B,
        v19,
        v20,
        (__int64)&v49);
    }
  }
  v28 = v52;
  if ( v52 )
  {
    v32 = v52->wFormatTag;
    if ( (_WORD)v32 == 0xFFFE )
    {
      v36 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v36 > 4u && (unsigned __int8)tlgKeywordOn(v36, 16896) )
      {
        LODWORD(v68) = *(_DWORD *)&v28[1].nChannels;
        *(_QWORD *)&v65.Data1 = (char *)v28 + 24;
        nSamplesPerSec = v52->nAvgBytesPerSec;
        nAvgBytesPerSec = v52->nSamplesPerSec;
        LOWORD(v49) = v52->nChannels;
        *(_QWORD *)&v66.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v37,
          (unsigned int)byte_1801A4783,
          v37,
          v38,
          (__int64)&v66,
          (__int64)&v49,
          (__int64)&nAvgBytesPerSec,
          (__int64)&nSamplesPerSec,
          (__int64)&v65,
          (__int64)&v68);
      }
    }
    else
    {
      *(_QWORD *)&v67.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v67.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v67.Data1 = v32;
      v33 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v33 > 4u && (unsigned __int8)tlgKeywordOn(v33, 16896) )
      {
        *(_QWORD *)&v65.Data1 = &v67;
        LODWORD(v68) = v52->nAvgBytesPerSec;
        nSamplesPerSec = v52->nSamplesPerSec;
        LOWORD(v49) = v52->nChannels;
        *(_QWORD *)&v66.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v34,
          (unsigned int)byte_1801A4821,
          v34,
          v35,
          (__int64)&v66,
          (__int64)&v49,
          (__int64)&nSamplesPerSec,
          (__int64)&v68,
          (__int64)&v65);
      }
    }
  }
  else
  {
    v29 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v29 > 4u && (unsigned __int8)tlgKeywordOn(v29, 16896) )
    {
      LODWORD(v68) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)word_1801A48B2,
        v30,
        v31,
        (__int64)&v68);
    }
  }
  v49 = 0;
  nSamplesPerSec = 0;
  LODWORD(v68) = 0;
  nAvgBytesPerSec = 0;
  v39 = a2[1];
  v67 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, struct _GUID *))(*(_QWORD *)this
                                                                                                  + 128LL))(
                           this,
                           &v65);
  v48 = 0;
  SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(v39, (unsigned int)a3, v52, &v67);
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v11 = 647;
    goto LABEL_6;
  }
  v40 = v52;
  v41 = (unsigned int)(int)((double)v49 * 10000000.0 / (double)(int)v52->nSamplesPerSec + 0.5);
  Src = v53;
  v67 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, struct _GUID *))(*(_QWORD *)this
                                                                                                  + 128LL))(
                           this,
                           &v66);
  v65 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, void **))(*(_QWORD *)this + 128LL))(
                           this,
                           &v68);
  SharedModeEnginePeriodicity = DeriveSaDeviceParametersForStream(
                                  (struct EndpointCharacteristicsDescriptor *)a2,
                                  AUDCLNT_SHAREMODE_SHARED,
                                  a3,
                                  &v65,
                                  &v67,
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
  v44 = v55;
  v55 = 0;
  if ( v44 )
    CoTaskMemFree(v44);
  v45 = v53;
  v53 = 0;
  if ( v45 )
    CoTaskMemFree(v45);
  v46 = v52;
  v52 = 0;
  if ( v46 )
    CoTaskMemFree(v46);
  return 0;
}

```

## disassembly

```asm
0x1800f7984  push    rbp
0x1800f7986  push    rbx
0x1800f7987  push    rsi
0x1800f7988  push    rdi
0x1800f7989  push    r12
0x1800f798b  push    r13
0x1800f798d  push    r14
0x1800f798f  push    r15
0x1800f7991  lea     rbp, [rsp-58h]
0x1800f7996  sub     rsp, 158h
0x1800f799d  mov     rax, cs:__security_cookie
0x1800f79a4  xor     rax, rsp
0x1800f79a7  mov     [rbp+90h+var_48], rax
0x1800f79ab  mov     r13, r9
0x1800f79ae  mov     r15d, r8d
0x1800f79b1  mov     r14, rdx
0x1800f79b4  mov     r12, rcx
0x1800f79b7  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800f79be  movdqu  xmmword ptr [rbp+90h+var_70.Data1], xmm0
0x1800f79c3  movdqu  xmmword ptr [rbp+90h+var_90.Data1], xmm0
0x1800f79c8  movdqu  xmmword ptr [rbp+90h+var_80.Data1], xmm0
0x1800f79cd  xor     edi, edi
0x1800f79cf  mov     [rsp+190h+var_118], rdi
0x1800f79d4  mov     [rsp+190h+var_120], rdi
0x1800f79d9  lea     rax, [rbp+90h+var_80]
0x1800f79dd  mov     [rsp+190h+var_128], rax
0x1800f79e2  lea     rax, [rbp+90h+var_90]
0x1800f79e6  mov     [rsp+190h+var_130], rax
0x1800f79eb  lea     rax, [rbp+90h+var_70]
0x1800f79ef  mov     [rsp+190h+var_138], rax
0x1800f79f4  mov     [rsp+190h+var_140], rdi
0x1800f79f9  mov     dword ptr [rsp+190h+var_148], 1
0x1800f7a01  mov     dword ptr [rsp+190h+var_150], edi
0x1800f7a05  mov     [rsp+190h+var_158], rdi
0x1800f7a0a  mov     dword ptr [rsp+190h+Src], r8d
0x1800f7a0f  mov     dword ptr [rsp+190h+var_168], edi
0x1800f7a13  mov     dword ptr [rsp+190h+var_170], edi; int
0x1800f7a17  mov     r9, rdx
0x1800f7a1a  xor     r8d, r8d
0x1800f7a1d  xor     edx, edx
0x1800f7a1f  xor     ecx, ecx
0x1800f7a21  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x1800f7a26  mov     ebx, eax
0x1800f7a28  test    eax, eax
0x1800f7a2a  jns     short loc_1800F7A4E
0x1800f7a2c  mov     rcx, [rbp+98h]; this
0x1800f7a33  mov     r9d, eax; char *
0x1800f7a36  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f7a3d  mov     edx, 270h; void *
0x1800f7a42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7a47  mov     eax, ebx
0x1800f7a49  jmp     loc_1800F8088
0x1800f7a4e  mov     [rbp+90h+var_100], rdi
0x1800f7a52  mov     [rbp+90h+var_F8], rdi
0x1800f7a56  mov     [rbp+90h+var_E8], rdi
0x1800f7a5a  mov     [rbp+90h+pv], rdi
0x1800f7a5e  lea     rax, [rbp+90h+var_100]
0x1800f7a62  mov     [rbp+90h+var_B0], rax
0x1800f7a66  mov     [rbp+90h+var_A8], rdi
0x1800f7a6a  mov     [rbp+90h+var_A0], 1
0x1800f7a6e  lea     rax, [rbp+90h+var_F8]
0x1800f7a72  mov     [rbp+90h+var_C8], rax
0x1800f7a76  mov     [rbp+90h+var_C0], rdi
0x1800f7a7a  mov     [rbp+90h+var_B8], 1
0x1800f7a7e  lea     rax, [rbp+90h+pv]
0x1800f7a82  mov     [rbp+90h+var_E0], rax
0x1800f7a86  mov     [rbp+90h+var_D8], rdi
0x1800f7a8a  mov     [rbp+90h+var_D0], 1
0x1800f7a8e  lea     rax, [rbp+90h+var_E8]
0x1800f7a92  mov     [rbp+90h+var_60], rax
0x1800f7a96  mov     [rbp+90h+var_58], rdi
0x1800f7a9a  mov     [rbp+90h+var_50], 1
0x1800f7a9e  movaps  xmm0, xmmword ptr [rbp+90h+var_70.Data1]
0x1800f7aa2  movdqa  xmmword ptr [rbp+90h+var_70.Data1], xmm0
0x1800f7aa7  movaps  xmm1, xmmword ptr [rbp+90h+var_90.Data1]
0x1800f7aab  movdqa  xmmword ptr [rbp+90h+var_90.Data1], xmm1
0x1800f7ab0  movaps  xmm0, xmmword ptr [rbp+90h+var_80.Data1]
0x1800f7ab4  movdqa  xmmword ptr [rbp+90h+var_80.Data1], xmm0
0x1800f7ab9  lea     rax, [rbp+90h+var_A8]
0x1800f7abd  mov     [rsp+190h+var_130], rax; struct tWAVEFORMATEX **
0x1800f7ac2  lea     rax, [rbp+90h+var_C0]
0x1800f7ac6  mov     [rsp+190h+var_138], rax; struct tWAVEFORMATEX **
0x1800f7acb  lea     rax, [rbp+90h+var_D8]
0x1800f7acf  mov     [rsp+190h+var_140], rax; struct tWAVEFORMATEX **
0x1800f7ad4  lea     rax, [rbp+90h+var_58]
0x1800f7ad8  mov     [rsp+190h+var_148], rax; struct tWAVEFORMATEX **
0x1800f7add  mov     [rsp+190h+var_150], rdi; struct tWAVEFORMATEX *
0x1800f7ae2  lea     rax, [rbp+90h+var_70]
0x1800f7ae6  mov     [rsp+190h+var_158], rax; struct _GUID *
0x1800f7aeb  lea     rax, [rbp+90h+var_90]
0x1800f7aef  mov     [rsp+190h+Src], rax; struct _GUID *
0x1800f7af4  lea     rax, [rbp+90h+var_80]
0x1800f7af8  mov     [rsp+190h+var_168], rax; struct _GUID *
0x1800f7afd  mov     dword ptr [rsp+190h+var_170], edi; int
0x1800f7b01  xor     r9d, r9d; enum _AUDCLNT_SHAREMODE
0x1800f7b04  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800f7b07  xor     edx, edx; bool
0x1800f7b09  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x1800f7b0c  call    ?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z; DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)
0x1800f7b11  mov     ebx, eax
0x1800f7b13  lea     rcx, [rbp+90h+var_60]
0x1800f7b17  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f7b1c  nop
0x1800f7b1d  lea     rcx, [rbp+90h+var_E0]
0x1800f7b21  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f7b26  nop
0x1800f7b27  lea     rcx, [rbp+90h+var_C8]
0x1800f7b2b  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f7b30  nop
0x1800f7b31  lea     rcx, [rbp+90h+var_B0]
0x1800f7b35  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f7b3a  test    ebx, ebx
0x1800f7b3c  jns     short loc_1800F7BB2
0x1800f7b3e  mov     edx, 281h; void *
0x1800f7b43  mov     r9d, ebx; char *
0x1800f7b46  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f7b4d  mov     rcx, [rbp+98h]; this
0x1800f7b54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7b59  nop
0x1800f7b5a  mov     rcx, [rbp+90h+pv]; pv
0x1800f7b5e  mov     [rbp+90h+pv], rdi
0x1800f7b62  test    rcx, rcx
0x1800f7b65  jz      short loc_1800F7B6E
0x1800f7b67  call    cs:__imp_CoTaskMemFree
0x1800f7b6d  nop
0x1800f7b6e  mov     rcx, [rbp+90h+var_E8]; pv
0x1800f7b72  mov     [rbp+90h+var_E8], rdi
0x1800f7b76  test    rcx, rcx
0x1800f7b79  jz      short loc_1800F7B82
0x1800f7b7b  call    cs:__imp_CoTaskMemFree
0x1800f7b81  nop
0x1800f7b82  mov     rcx, [rbp+90h+var_F8]; pv
0x1800f7b86  test    rcx, rcx
0x1800f7b89  mov     [rbp+90h+var_F8], rdi
0x1800f7b8d  jz      short loc_1800F7B96
0x1800f7b8f  call    cs:__imp_CoTaskMemFree
0x1800f7b95  nop
0x1800f7b96  mov     rcx, [rbp+90h+var_100]; pv
0x1800f7b9a  mov     [rbp+90h+var_100], rdi
0x1800f7b9e  test    rcx, rcx
0x1800f7ba1  jz      loc_1800F7A47
0x1800f7ba7  call    cs:__imp_CoTaskMemFree
0x1800f7bad  jmp     loc_1800F7A47
0x1800f7bb2  mov     eax, 0FFFEh
0x1800f7bb7  mov     esi, 4200h
0x1800f7bbc  mov     rbx, [rbp+90h+var_F8]
0x1800f7bc0  test    rbx, rbx
0x1800f7bc3  jnz     short loc_1800F7C0C
0x1800f7bc5  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f7bca  mov     r8, [rax+8]
0x1800f7bce  mov     eax, [r8]
0x1800f7bd1  cmp     eax, 4
0x1800f7bd4  jbe     loc_1800F7D5F
0x1800f7bda  mov     edx, esi
0x1800f7bdc  mov     rcx, r8
0x1800f7bdf  call    _tlgKeywordOn
0x1800f7be4  test    al, al
0x1800f7be6  jz      loc_1800F7D5F
0x1800f7bec  mov     [rbp+90h+var_110], edi
0x1800f7bef  lea     rax, [rbp+90h+var_110]
0x1800f7bf3  mov     [rsp+190h+var_170], rax
0x1800f7bf8  lea     rdx, byte_1801A4A3B
0x1800f7bff  mov     rcx, r8
0x1800f7c02  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800f7c07  jmp     loc_1800F7D5F
0x1800f7c0c  movzx   ecx, word ptr [rbx]
0x1800f7c0f  cmp     cx, ax
0x1800f7c12  jz      loc_1800F7CC5
0x1800f7c18  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x1800f7c20  movsd   qword ptr [rbp+90h+var_90.Data2], xmm0
0x1800f7c25  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x1800f7c2b  mov     dword ptr [rbp+90h+var_90.Data4+4], eax
0x1800f7c2e  mov     [rbp+90h+var_90.Data1], ecx
0x1800f7c31  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f7c36  mov     r8, [rax+8]
0x1800f7c3a  mov     eax, [r8]
0x1800f7c3d  cmp     eax, 4
0x1800f7c40  jbe     loc_1800F7D5F
0x1800f7c46  mov     rdx, rsi
0x1800f7c49  mov     rcx, r8
0x1800f7c4c  call    _tlgKeywordOn
0x1800f7c51  test    al, al
0x1800f7c53  jz      loc_1800F7D5F
0x1800f7c59  lea     rax, [rbp+90h+var_90]
0x1800f7c5d  mov     [rbp+90h+var_60], rax
0x1800f7c61  mov     rax, [rbp+90h+var_F8]
0x1800f7c65  mov     ecx, [rax+8]
0x1800f7c68  mov     [rbp+90h+var_108], ecx
0x1800f7c6b  mov     ecx, [rax+4]
0x1800f7c6e  mov     [rbp+90h+var_10C], ecx
0x1800f7c71  movzx   ecx, word ptr [rax+2]
0x1800f7c75  mov     word ptr [rbp+90h+var_110], cx
0x1800f7c79  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x1800f7c80  mov     qword ptr [rbp+90h+var_80.Data1], rax
0x1800f7c84  lea     rax, [rbp+90h+var_60]
0x1800f7c88  mov     [rsp+190h+var_150], rax
0x1800f7c8d  lea     rax, [rbp+90h+var_108]
0x1800f7c91  mov     [rsp+190h+var_158], rax
0x1800f7c96  lea     rax, [rbp+90h+var_10C]
0x1800f7c9a  mov     [rsp+190h+Src], rax
0x1800f7c9f  lea     rax, [rbp+90h+var_110]
0x1800f7ca3  mov     [rsp+190h+var_168], rax
0x1800f7ca8  lea     rax, [rbp+90h+var_80]
0x1800f7cac  mov     [rsp+190h+var_170], rax
0x1800f7cb1  lea     rdx, byte_1801A49A9
0x1800f7cb8  mov     rcx, r8
0x1800f7cbb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800f7cc0  jmp     loc_1800F7D5F
0x1800f7cc5  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f7cca  mov     r8, [rax+8]
0x1800f7cce  mov     eax, [r8]
0x1800f7cd1  cmp     eax, 4
0x1800f7cd4  jbe     loc_1800F7D5F
0x1800f7cda  mov     rdx, rsi
0x1800f7cdd  mov     rcx, r8
0x1800f7ce0  call    _tlgKeywordOn
0x1800f7ce5  test    al, al
0x1800f7ce7  jz      short loc_1800F7D5F
0x1800f7ce9  mov     eax, [rbx+14h]
0x1800f7cec  mov     [rbp+90h+var_10C], eax
0x1800f7cef  lea     rax, [rbx+18h]
0x1800f7cf3  mov     qword ptr [rbp+90h+var_80.Data1], rax
0x1800f7cf7  mov     rax, [rbp+90h+var_F8]
0x1800f7cfb  mov     ecx, [rax+8]
0x1800f7cfe  mov     [rbp+90h+var_108], ecx
0x1800f7d01  mov     ecx, [rax+4]
0x1800f7d04  mov     dword ptr [rbp+90h+var_60], ecx
0x1800f7d07  movzx   ecx, word ptr [rax+2]
0x1800f7d0b  mov     word ptr [rbp+90h+var_110], cx
0x1800f7d0f  lea     rax, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x1800f7d16  mov     qword ptr [rbp+90h+var_90.Data1], rax
0x1800f7d1a  lea     rax, [rbp+90h+var_10C]
0x1800f7d1e  mov     [rsp+190h+var_148], rax
0x1800f7d23  lea     rax, [rbp+90h+var_80]
0x1800f7d27  mov     [rsp+190h+var_150], rax
0x1800f7d2c  lea     rax, [rbp+90h+var_108]
0x1800f7d30  mov     [rsp+190h+var_158], rax
0x1800f7d35  lea     rax, [rbp+90h+var_60]
0x1800f7d39  mov     [rsp+190h+Src], rax
0x1800f7d3e  lea     rax, [rbp+90h+var_110]
0x1800f7d42  mov     [rsp+190h+var_168], rax
0x1800f7d47  lea     rax, [rbp+90h+var_90]
0x1800f7d4b  mov     [rsp+190h+var_170], rax
0x1800f7d50  lea     rdx, word_1801A490A
0x1800f7d57  mov     rcx, r8
0x1800f7d5a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800f7d5f  mov     rbx, [rbp+90h+var_100]
0x1800f7d63  test    rbx, rbx
0x1800f7d66  jnz     short loc_1800F7DB0
0x1800f7d68  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f7d6d  mov     r8, [rax+8]
0x1800f7d71  mov     eax, [r8]
0x1800f7d74  cmp     eax, 4
0x1800f7d77  jbe     loc_1800F7F08
0x1800f7d7d  mov     rdx, rsi
0x1800f7d80  mov     rcx, r8
0x1800f7d83  call    _tlgKeywordOn
0x1800f7d88  test    al, al
0x1800f7d8a  jz      loc_1800F7F08
0x1800f7d90  mov     dword ptr [rbp+90h+var_60], edi
0x1800f7d93  lea     rax, [rbp+90h+var_60]
0x1800f7d97  mov     [rsp+190h+var_170], rax
0x1800f7d9c  lea     rdx, word_1801A48B2
0x1800f7da3  mov     rcx, r8
0x1800f7da6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800f7dab  jmp     loc_1800F7F08
0x1800f7db0  movzx   ecx, word ptr [rbx]
0x1800f7db3  mov     eax, 0FFFEh
0x1800f7db8  cmp     cx, ax
0x1800f7dbb  jz      loc_1800F7E6E
0x1800f7dc1  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x1800f7dc9  movsd   qword ptr [rbp+90h+var_70.Data2], xmm0
0x1800f7dce  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x1800f7dd4  mov     dword ptr [rbp+90h+var_70.Data4+4], eax
0x1800f7dd7  mov     [rbp+90h+var_70.Data1], ecx
0x1800f7dda  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f7ddf  mov     r8, [rax+8]
0x1800f7de3  mov     eax, [r8]
0x1800f7de6  cmp     eax, 4
0x1800f7de9  jbe     loc_1800F7F08
0x1800f7def  mov     rdx, rsi
0x1800f7df2  mov     rcx, r8
0x1800f7df5  call    _tlgKeywordOn
0x1800f7dfa  test    al, al
0x1800f7dfc  jz      loc_1800F7F08
0x1800f7e02  lea     rax, [rbp+90h+var_70]
0x1800f7e06  mov     qword ptr [rbp+90h+var_90.Data1], rax
0x1800f7e0a  mov     rax, [rbp+90h+var_100]
0x1800f7e0e  mov     ecx, [rax+8]
0x1800f7e11  mov     dword ptr [rbp+90h+var_60], ecx
0x1800f7e14  mov     ecx, [rax+4]
0x1800f7e17  mov     [rbp+90h+var_10C], ecx
0x1800f7e1a  movzx   ecx, word ptr [rax+2]
0x1800f7e1e  mov     word ptr [rbp+90h+var_110], cx
0x1800f7e22  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x1800f7e29  mov     qword ptr [rbp+90h+var_80.Data1], rax
0x1800f7e2d  lea     rax, [rbp+90h+var_90]
0x1800f7e31  mov     [rsp+190h+var_150], rax
0x1800f7e36  lea     rax, [rbp+90h+var_60]
0x1800f7e3a  mov     [rsp+190h+var_158], rax
  ... truncated ...
```
