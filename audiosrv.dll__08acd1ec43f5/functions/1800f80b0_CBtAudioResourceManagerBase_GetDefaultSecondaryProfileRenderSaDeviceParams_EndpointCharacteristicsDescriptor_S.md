# CBtAudioResourceManagerBase::GetDefaultSecondaryProfileRenderSaDeviceParams(EndpointCharacteristicsDescriptor *,SaDeviceParams * *)

- ea: `0x1800f80b0`
- end: `0x1800f87a8`
- name: `?GetDefaultSecondaryProfileRenderSaDeviceParams@CBtAudioResourceManagerBase@@IEAAJPEAUEndpointCharacteristicsDescriptor@@PEAPEAUSaDeviceParams@@@Z`
- size: `1784`
- prototype: `int(CBtAudioResourceManagerBase *__hidden this, struct EndpointCharacteristicsDescriptor *, struct SaDeviceParams **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f75c8`

## callees

- `0x180008a2c`
- `0x18001280c`
- `0x18001b520`
- `0x18001e0b0`
- `0x18001ec9c`
- `0x180044bd8`
- `0x180049efc`
- `0x18005abac`
- `0x180061430`
- `0x180072e10`
- `0x1800cd8d0`
- `0x1800f80b0`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f826a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f827e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f874c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f826a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f827e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f874c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8774`

## string_xrefs

- `0x1800f8221`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CBtAudioResourceManagerBase::GetDefaultSecondaryProfileRenderSaDeviceParams(
        CBtAudioResourceManagerBase *this,
        struct EndpointCharacteristicsDescriptor *a2,
        struct SaDeviceParams **a3)
{
  struct _GUID v6; // xmm6
  struct _GUID *v7; // rax
  int SharedModeEnginePeriodicity; // ebx
  __int64 v9; // rdx
  void *v10; // rcx
  void *v11; // rcx
  struct tWAVEFORMATEX *v12; // rcx
  bool v13; // zf
  struct tWAVEFORMATEX *v14; // rcx
  struct tWAVEFORMATEX *v16; // rbx
  _DWORD *v17; // r8
  int v18; // r8d
  int v19; // r9d
  unsigned int wFormatTag; // ecx
  _DWORD *v21; // r8
  int v22; // r8d
  int v23; // r9d
  _DWORD *v24; // r8
  int v25; // r8d
  int v26; // r9d
  struct tWAVEFORMATEX *v27; // rbx
  _DWORD *v28; // r8
  int v29; // r8d
  int v30; // r9d
  unsigned int v31; // ecx
  _DWORD *v32; // r8
  int v33; // r8d
  int v34; // r9d
  _DWORD *v35; // r8
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // rbx
  struct tWAVEFORMATEX *v39; // rbx
  __int64 v40; // rdi
  struct tWAVEFORMATEX *Src; // rsi
  void *v42; // rcx
  void *v43; // rcx
  struct tWAVEFORMATEX *v44; // rcx
  struct tWAVEFORMATEX *v45; // rcx
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+70h] [rbp-90h] BYREF
  DWORD nSamplesPerSec; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD nAvgBytesPerSec; // [rsp+78h] [rbp-88h] BYREF
  struct tWAVEFORMATEX *v50; // [rsp+80h] [rbp-80h] BYREF
  struct tWAVEFORMATEX *v51; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v53; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID v54; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID *v55; // [rsp+B0h] [rbp-50h] BYREF
  struct tWAVEFORMATEX *v56; // [rsp+B8h] [rbp-48h] BYREF
  char v57; // [rsp+C0h] [rbp-40h]
  LPVOID *p_pv; // [rsp+C8h] [rbp-38h] BYREF
  struct tWAVEFORMATEX *v59; // [rsp+D0h] [rbp-30h] BYREF
  char v60; // [rsp+D8h] [rbp-28h]
  struct tWAVEFORMATEX **v61; // [rsp+E0h] [rbp-20h] BYREF
  struct tWAVEFORMATEX *v62; // [rsp+E8h] [rbp-18h] BYREF
  char v63; // [rsp+F0h] [rbp-10h]
  struct tWAVEFORMATEX **v64; // [rsp+F8h] [rbp-8h] BYREF
  struct tWAVEFORMATEX *v65; // [rsp+100h] [rbp+0h] BYREF
  char v66; // [rsp+108h] [rbp+8h]
  struct _GUID v67; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v68[2]; // [rsp+120h] [rbp+20h] BYREF
  struct _GUID v69; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v70[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v71[16]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v50 = 0;
  v51 = 0;
  v53 = 0;
  pv = 0;
  v64 = &v50;
  v65 = 0;
  v66 = 1;
  v61 = &v51;
  v62 = 0;
  v63 = 1;
  p_pv = &pv;
  v59 = 0;
  v60 = 1;
  v55 = &v53;
  v56 = 0;
  v57 = 1;
  v6 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, _QWORD *))(*(_QWORD *)this + 136LL))(
                          this,
                          v68);
  v7 = (struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, _BYTE *))(*(_QWORD *)this + 136LL))(
                         this,
                         v71);
  v69 = v6;
  v67 = *v7;
  v54 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, _BYTE *))(*(_QWORD *)this + 136LL))(
                           this,
                           v70);
  SharedModeEnginePeriodicity = DeriveDeviceGraphFormatsForStream(
                                  a2,
                                  0,
                                  eHostProcessConnector,
                                  AUDCLNT_SHAREMODE_SHARED,
                                  0,
                                  &v54,
                                  &v67,
                                  &v69,
                                  0,
                                  &v56,
                                  &v59,
                                  &v62,
                                  &v65);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v55);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v61);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v64);
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v9 = 594;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
      (const char *)(unsigned int)SharedModeEnginePeriodicity,
      v46);
    v10 = pv;
    pv = 0;
    if ( v10 )
      CoTaskMemFree(v10);
    v11 = v53;
    v53 = 0;
    if ( v11 )
      CoTaskMemFree(v11);
    v12 = v51;
    v13 = v51 == 0;
    v51 = 0;
    if ( !v13 )
      CoTaskMemFree(v12);
    v14 = v50;
    v50 = 0;
    if ( v14 )
      CoTaskMemFree(v14);
    return (unsigned int)SharedModeEnginePeriodicity;
  }
  v16 = v51;
  if ( v51 )
  {
    wFormatTag = v51->wFormatTag;
    if ( (_WORD)wFormatTag == 0xFFFE )
    {
      v24 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v24 > 4u && (unsigned __int8)tlgKeywordOn(v24, 16896) )
      {
        nSamplesPerSec = *(_DWORD *)&v16[1].nChannels;
        *(_QWORD *)&v54.Data1 = (char *)v16 + 24;
        nAvgBytesPerSec = v51->nAvgBytesPerSec;
        LODWORD(v68[0]) = v51->nSamplesPerSec;
        LOWORD(v47) = v51->nChannels;
        *(_QWORD *)&v67.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)byte_1801A4C21,
          v25,
          v26,
          (__int64)&v67,
          (__int64)&v47,
          (__int64)v68,
          (__int64)&nAvgBytesPerSec,
          (__int64)&v54,
          (__int64)&nSamplesPerSec);
      }
    }
    else
    {
      *(_QWORD *)&v67.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v67.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v67.Data1 = wFormatTag;
      v21 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v21 > 4u && (unsigned __int8)tlgKeywordOn(v21, 16896) )
      {
        v68[0] = &v67;
        nAvgBytesPerSec = v51->nAvgBytesPerSec;
        nSamplesPerSec = v51->nSamplesPerSec;
        LOWORD(v47) = v51->nChannels;
        *(_QWORD *)&v54.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v22,
          (unsigned int)word_1801A4CC2,
          v22,
          v23,
          (__int64)&v54,
          (__int64)&v47,
          (__int64)&nSamplesPerSec,
          (__int64)&nAvgBytesPerSec,
          (__int64)v68);
      }
    }
  }
  else
  {
    v17 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v17 > 4u && (unsigned __int8)tlgKeywordOn(v17, 16896) )
    {
      v47 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v18,
        (unsigned int)&word_1801A4D56,
        v18,
        v19,
        (__int64)&v47);
    }
  }
  v27 = v50;
  if ( v50 )
  {
    v31 = v50->wFormatTag;
    if ( (_WORD)v31 == 0xFFFE )
    {
      v35 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v35 > 4u && (unsigned __int8)tlgKeywordOn(v35, 16896) )
      {
        LODWORD(v68[0]) = *(_DWORD *)&v27[1].nChannels;
        *(_QWORD *)&v67.Data1 = (char *)v27 + 24;
        nSamplesPerSec = v50->nAvgBytesPerSec;
        nAvgBytesPerSec = v50->nSamplesPerSec;
        LOWORD(v47) = v50->nChannels;
        *(_QWORD *)&v54.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v36,
          (unsigned int)&dword_1801A4A94,
          v36,
          v37,
          (__int64)&v54,
          (__int64)&v47,
          (__int64)&nAvgBytesPerSec,
          (__int64)&nSamplesPerSec,
          (__int64)&v67,
          (__int64)v68);
      }
    }
    else
    {
      *(_QWORD *)&v69.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v69.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v69.Data1 = v31;
      v32 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v32 > 4u && (unsigned __int8)tlgKeywordOn(v32, 16896) )
      {
        *(_QWORD *)&v67.Data1 = &v69;
        LODWORD(v68[0]) = v50->nAvgBytesPerSec;
        nSamplesPerSec = v50->nSamplesPerSec;
        LOWORD(v47) = v50->nChannels;
        *(_QWORD *)&v54.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v33,
          (unsigned int)&dword_1801A4B34,
          v33,
          v34,
          (__int64)&v54,
          (__int64)&v47,
          (__int64)&nSamplesPerSec,
          (__int64)v68,
          (__int64)&v67);
      }
    }
  }
  else
  {
    v28 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v28 > 4u && (unsigned __int8)tlgKeywordOn(v28, 16896) )
    {
      LODWORD(v68[0]) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v29,
        (unsigned int)&byte_1801A4BC7,
        v29,
        v30,
        (__int64)v68);
    }
  }
  v47 = 0;
  nSamplesPerSec = 0;
  LODWORD(v68[0]) = 0;
  nAvgBytesPerSec = 0;
  v38 = *((_QWORD *)a2 + 1);
  v69 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, _BYTE *))(*(_QWORD *)this + 136LL))(
                           this,
                           v70);
  v46 = 0;
  SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(v38, 0, v50, &v69);
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v9 = 600;
    goto LABEL_3;
  }
  v39 = v50;
  v40 = (unsigned int)(int)((double)v47 * 10000000.0 / (double)(int)v50->nSamplesPerSec + 0.5);
  Src = v51;
  v69 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, _BYTE *))(*(_QWORD *)this + 136LL))(
                           this,
                           v70);
  v67 = *(struct _GUID *)(*(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, _BYTE *))(*(_QWORD *)this + 136LL))(
                           this,
                           v71);
  SharedModeEnginePeriodicity = DeriveSaDeviceParametersForStream(
                                  a2,
                                  AUDCLNT_SHAREMODE_SHARED,
                                  eHostProcessConnector,
                                  &v67,
                                  &v69,
                                  v39,
                                  Src,
                                  v40,
                                  a3);
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v9 = 612;
    goto LABEL_3;
  }
  v42 = pv;
  pv = 0;
  if ( v42 )
    CoTaskMemFree(v42);
  v43 = v53;
  v53 = 0;
  if ( v43 )
    CoTaskMemFree(v43);
  v44 = v51;
  v51 = 0;
  if ( v44 )
    CoTaskMemFree(v44);
  v45 = v50;
  v50 = 0;
  if ( v45 )
    CoTaskMemFree(v45);
  return 0;
}

```

## disassembly

```asm
0x1800f80b0  mov     rax, rsp
0x1800f80b3  mov     [rax+20h], rbx
0x1800f80b7  push    rbp
0x1800f80b8  push    rsi
0x1800f80b9  push    rdi
0x1800f80ba  push    r12
0x1800f80bc  push    r13
0x1800f80be  push    r14
0x1800f80c0  push    r15
0x1800f80c2  lea     rbp, [rsp-80h]
0x1800f80c7  sub     rsp, 180h
0x1800f80ce  movaps  xmmword ptr [rax-48h], xmm6
0x1800f80d2  mov     rax, cs:__security_cookie
0x1800f80d9  xor     rax, rsp
0x1800f80dc  mov     [rbp+0B0h+var_50], rax
0x1800f80e0  mov     r12, r8
0x1800f80e3  mov     r15, rdx
0x1800f80e6  mov     r14, rcx
0x1800f80e9  xor     r13d, r13d
0x1800f80ec  mov     [rbp+0B0h+var_130], r13
0x1800f80f0  mov     [rbp+0B0h+var_128], r13
0x1800f80f4  mov     [rbp+0B0h+var_118], r13
0x1800f80f8  mov     [rbp+0B0h+pv], r13
0x1800f80fc  lea     rax, [rbp+0B0h+var_130]
0x1800f8100  mov     [rbp+0B0h+var_B8], rax
0x1800f8104  mov     [rbp+0B0h+var_B0], r13
0x1800f8108  mov     [rbp+0B0h+var_A8], 1
0x1800f810c  lea     rax, [rbp+0B0h+var_128]
0x1800f8110  mov     [rbp+0B0h+var_D0], rax
0x1800f8114  mov     [rbp+0B0h+var_C8], r13
0x1800f8118  mov     [rbp+0B0h+var_C0], 1
0x1800f811c  lea     rax, [rbp+0B0h+pv]
0x1800f8120  mov     [rbp+0B0h+var_E8], rax
0x1800f8124  mov     [rbp+0B0h+var_E0], r13
0x1800f8128  mov     [rbp+0B0h+var_D8], 1
0x1800f812c  lea     rax, [rbp+0B0h+var_118]
0x1800f8130  mov     [rbp+0B0h+var_100], rax
0x1800f8134  mov     [rbp+0B0h+var_F8], r13
0x1800f8138  mov     [rbp+0B0h+var_F0], 1
0x1800f813c  mov     rax, [rcx]
0x1800f813f  lea     rdx, [rbp+0B0h+var_90]
0x1800f8143  mov     rax, [rax+88h]
0x1800f814a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f814f  movups  xmm6, xmmword ptr [rax]
0x1800f8152  mov     rax, [r14]
0x1800f8155  lea     rdx, [rbp+0B0h+var_60]
0x1800f8159  mov     rcx, r14
0x1800f815c  mov     rax, [rax+88h]
0x1800f8163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8168  movdqu  xmmword ptr [rbp+0B0h+var_80.Data1], xmm6
0x1800f816d  movups  xmm0, xmmword ptr [rax]
0x1800f8170  movdqu  xmmword ptr [rbp+0B0h+var_A0.Data1], xmm0
0x1800f8175  mov     rax, [r14]
0x1800f8178  lea     rdx, [rbp+0B0h+var_70]
0x1800f817c  mov     rcx, r14
0x1800f817f  mov     rax, [rax+88h]
0x1800f8186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f818b  movups  xmm0, xmmword ptr [rax]
0x1800f818e  movdqu  xmmword ptr [rbp+0B0h+var_110.Data1], xmm0
0x1800f8193  lea     rax, [rbp+0B0h+var_B0]
0x1800f8197  mov     [rsp+1B0h+var_150], rax; struct tWAVEFORMATEX **
0x1800f819c  lea     rax, [rbp+0B0h+var_C8]
0x1800f81a0  mov     [rsp+1B0h+var_158], rax; struct tWAVEFORMATEX **
0x1800f81a5  lea     rax, [rbp+0B0h+var_E0]
0x1800f81a9  mov     [rsp+1B0h+var_160], rax; struct tWAVEFORMATEX **
0x1800f81ae  lea     rax, [rbp+0B0h+var_F8]
0x1800f81b2  mov     [rsp+1B0h+var_168], rax; struct tWAVEFORMATEX **
0x1800f81b7  mov     [rsp+1B0h+var_170], r13; struct tWAVEFORMATEX *
0x1800f81bc  lea     rax, [rbp+0B0h+var_80]
0x1800f81c0  mov     [rsp+1B0h+var_178], rax; struct _GUID *
0x1800f81c5  lea     rax, [rbp+0B0h+var_A0]
0x1800f81c9  mov     [rsp+1B0h+Src], rax; struct _GUID *
0x1800f81ce  lea     rax, [rbp+0B0h+var_110]
0x1800f81d2  mov     [rsp+1B0h+var_188], rax; struct _GUID *
0x1800f81d7  mov     dword ptr [rsp+1B0h+var_190], r13d; int
0x1800f81dc  xor     r9d, r9d; enum _AUDCLNT_SHAREMODE
0x1800f81df  xor     r8d, r8d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800f81e2  xor     edx, edx; bool
0x1800f81e4  mov     rcx, r15; struct EndpointCharacteristicsDescriptor *
0x1800f81e7  call    ?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z; DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)
0x1800f81ec  mov     ebx, eax
0x1800f81ee  lea     rcx, [rbp+0B0h+var_100]
0x1800f81f2  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f81f7  nop
0x1800f81f8  lea     rcx, [rbp+0B0h+var_E8]
0x1800f81fc  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f8201  nop
0x1800f8202  lea     rcx, [rbp+0B0h+var_D0]
0x1800f8206  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f820b  nop
0x1800f820c  lea     rcx, [rbp+0B0h+var_B8]
0x1800f8210  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f8215  test    ebx, ebx
0x1800f8217  jns     short loc_1800F828B
0x1800f8219  mov     edx, 252h; void *
0x1800f821e  mov     r9d, ebx; char *
0x1800f8221  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f8228  mov     rcx, [rbp+0B8h]; this
0x1800f822f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8234  nop
0x1800f8235  mov     rcx, [rbp+0B0h+pv]; pv
0x1800f8239  mov     [rbp+0B0h+pv], r13
0x1800f823d  test    rcx, rcx
0x1800f8240  jz      short loc_1800F8249
0x1800f8242  call    cs:__imp_CoTaskMemFree
0x1800f8248  nop
0x1800f8249  mov     rcx, [rbp+0B0h+var_118]; pv
0x1800f824d  mov     [rbp+0B0h+var_118], r13
0x1800f8251  test    rcx, rcx
0x1800f8254  jz      short loc_1800F825D
0x1800f8256  call    cs:__imp_CoTaskMemFree
0x1800f825c  nop
0x1800f825d  mov     rcx, [rbp+0B0h+var_128]; pv
0x1800f8261  test    rcx, rcx
0x1800f8264  mov     [rbp+0B0h+var_128], r13
0x1800f8268  jz      short loc_1800F8271
0x1800f826a  call    cs:__imp_CoTaskMemFree
0x1800f8270  nop
0x1800f8271  mov     rcx, [rbp+0B0h+var_130]; pv
0x1800f8275  mov     [rbp+0B0h+var_130], r13
0x1800f8279  test    rcx, rcx
0x1800f827c  jz      short loc_1800F8284
0x1800f827e  call    cs:__imp_CoTaskMemFree
0x1800f8284  mov     eax, ebx
0x1800f8286  jmp     loc_1800F877C
0x1800f828b  mov     esi, 0FFFEh
0x1800f8290  mov     edi, 4200h
0x1800f8295  mov     rbx, [rbp+0B0h+var_128]
0x1800f8299  test    rbx, rbx
0x1800f829c  jnz     short loc_1800F82E8
0x1800f829e  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f82a3  mov     r8, [rax+8]
0x1800f82a7  mov     eax, [r8]
0x1800f82aa  cmp     eax, 4
0x1800f82ad  jbe     loc_1800F8447
0x1800f82b3  mov     edx, edi
0x1800f82b5  mov     rcx, r8
0x1800f82b8  call    _tlgKeywordOn
0x1800f82bd  test    al, al
0x1800f82bf  jz      loc_1800F8447
0x1800f82c5  mov     [rsp+1B0h+var_140], r13d
0x1800f82ca  lea     rax, [rsp+1B0h+var_140]
0x1800f82cf  mov     [rsp+1B0h+var_190], rax
0x1800f82d4  lea     rdx, word_1801A4D56
0x1800f82db  mov     rcx, r8
0x1800f82de  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800f82e3  jmp     loc_1800F8447
0x1800f82e8  movzx   ecx, word ptr [rbx]
0x1800f82eb  cmp     cx, si
0x1800f82ee  jz      loc_1800F83A7
0x1800f82f4  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x1800f82fc  movsd   qword ptr [rbp+0B0h+var_A0.Data2], xmm0
0x1800f8301  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x1800f8307  mov     dword ptr [rbp+0B0h+var_A0.Data4+4], eax
0x1800f830a  mov     [rbp+0B0h+var_A0.Data1], ecx
0x1800f830d  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f8312  mov     r8, [rax+8]
0x1800f8316  mov     eax, [r8]
0x1800f8319  cmp     eax, 4
0x1800f831c  jbe     loc_1800F8447
0x1800f8322  mov     rdx, rdi
0x1800f8325  mov     rcx, r8
0x1800f8328  call    _tlgKeywordOn
0x1800f832d  test    al, al
0x1800f832f  jz      loc_1800F8447
0x1800f8335  lea     rax, [rbp+0B0h+var_A0]
0x1800f8339  mov     [rbp+0B0h+var_90], rax
0x1800f833d  mov     rax, [rbp+0B0h+var_128]
0x1800f8341  mov     ecx, [rax+8]
0x1800f8344  mov     [rsp+1B0h+var_138], ecx
0x1800f8348  mov     ecx, [rax+4]
0x1800f834b  mov     [rsp+1B0h+var_13C], ecx
0x1800f834f  movzx   ecx, word ptr [rax+2]
0x1800f8353  mov     word ptr [rsp+1B0h+var_140], cx
0x1800f8358  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x1800f835f  mov     qword ptr [rbp+0B0h+var_110.Data1], rax
0x1800f8363  lea     rax, [rbp+0B0h+var_90]
0x1800f8367  mov     [rsp+1B0h+var_170], rax
0x1800f836c  lea     rax, [rsp+1B0h+var_138]
0x1800f8371  mov     [rsp+1B0h+var_178], rax
0x1800f8376  lea     rax, [rsp+1B0h+var_13C]
0x1800f837b  mov     [rsp+1B0h+Src], rax
0x1800f8380  lea     rax, [rsp+1B0h+var_140]
0x1800f8385  mov     [rsp+1B0h+var_188], rax
0x1800f838a  lea     rax, [rbp+0B0h+var_110]
0x1800f838e  mov     [rsp+1B0h+var_190], rax
0x1800f8393  lea     rdx, word_1801A4CC2
0x1800f839a  mov     rcx, r8
0x1800f839d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800f83a2  jmp     loc_1800F8447
0x1800f83a7  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f83ac  mov     r8, [rax+8]
0x1800f83b0  mov     eax, [r8]
0x1800f83b3  cmp     eax, 4
0x1800f83b6  jbe     loc_1800F8447
0x1800f83bc  mov     rdx, rdi
0x1800f83bf  mov     rcx, r8
0x1800f83c2  call    _tlgKeywordOn
0x1800f83c7  test    al, al
0x1800f83c9  jz      short loc_1800F8447
0x1800f83cb  mov     eax, [rbx+14h]
0x1800f83ce  mov     [rsp+1B0h+var_13C], eax
0x1800f83d2  lea     rax, [rbx+18h]
0x1800f83d6  mov     qword ptr [rbp+0B0h+var_110.Data1], rax
0x1800f83da  mov     rax, [rbp+0B0h+var_128]
0x1800f83de  mov     ecx, [rax+8]
0x1800f83e1  mov     [rsp+1B0h+var_138], ecx
0x1800f83e5  mov     ecx, [rax+4]
0x1800f83e8  mov     dword ptr [rbp+0B0h+var_90], ecx
0x1800f83eb  movzx   ecx, word ptr [rax+2]
0x1800f83ef  mov     word ptr [rsp+1B0h+var_140], cx
0x1800f83f4  lea     rax, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x1800f83fb  mov     qword ptr [rbp+0B0h+var_A0.Data1], rax
0x1800f83ff  lea     rax, [rsp+1B0h+var_13C]
0x1800f8404  mov     [rsp+1B0h+var_168], rax
0x1800f8409  lea     rax, [rbp+0B0h+var_110]
0x1800f840d  mov     [rsp+1B0h+var_170], rax
0x1800f8412  lea     rax, [rsp+1B0h+var_138]
0x1800f8417  mov     [rsp+1B0h+var_178], rax
0x1800f841c  lea     rax, [rbp+0B0h+var_90]
0x1800f8420  mov     [rsp+1B0h+Src], rax
0x1800f8425  lea     rax, [rsp+1B0h+var_140]
0x1800f842a  mov     [rsp+1B0h+var_188], rax
0x1800f842f  lea     rax, [rbp+0B0h+var_A0]
0x1800f8433  mov     [rsp+1B0h+var_190], rax
0x1800f8438  lea     rdx, byte_1801A4C21
0x1800f843f  mov     rcx, r8
0x1800f8442  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800f8447  mov     rbx, [rbp+0B0h+var_130]
0x1800f844b  test    rbx, rbx
0x1800f844e  jnz     short loc_1800F8499
0x1800f8450  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f8455  mov     r8, [rax+8]
0x1800f8459  mov     eax, [r8]
0x1800f845c  cmp     eax, 4
0x1800f845f  jbe     loc_1800F85F6
0x1800f8465  mov     rdx, rdi
0x1800f8468  mov     rcx, r8
0x1800f846b  call    _tlgKeywordOn
0x1800f8470  test    al, al
0x1800f8472  jz      loc_1800F85F6
0x1800f8478  mov     dword ptr [rbp+0B0h+var_90], r13d
0x1800f847c  lea     rax, [rbp+0B0h+var_90]
0x1800f8480  mov     [rsp+1B0h+var_190], rax
0x1800f8485  lea     rdx, byte_1801A4BC7
0x1800f848c  mov     rcx, r8
0x1800f848f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800f8494  jmp     loc_1800F85F6
0x1800f8499  movzx   ecx, word ptr [rbx]
0x1800f849c  cmp     cx, si
0x1800f849f  jz      loc_1800F8556
0x1800f84a5  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x1800f84ad  movsd   qword ptr [rbp+0B0h+var_80.Data2], xmm0
0x1800f84b2  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x1800f84b8  mov     dword ptr [rbp+0B0h+var_80.Data4+4], eax
0x1800f84bb  mov     [rbp+0B0h+var_80.Data1], ecx
0x1800f84be  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f84c3  mov     r8, [rax+8]
0x1800f84c7  mov     eax, [r8]
0x1800f84ca  cmp     eax, 4
0x1800f84cd  jbe     loc_1800F85F6
0x1800f84d3  mov     rdx, rdi
0x1800f84d6  mov     rcx, r8
0x1800f84d9  call    _tlgKeywordOn
0x1800f84de  test    al, al
0x1800f84e0  jz      loc_1800F85F6
0x1800f84e6  lea     rax, [rbp+0B0h+var_80]
0x1800f84ea  mov     qword ptr [rbp+0B0h+var_A0.Data1], rax
0x1800f84ee  mov     rax, [rbp+0B0h+var_130]
0x1800f84f2  mov     ecx, [rax+8]
0x1800f84f5  mov     dword ptr [rbp+0B0h+var_90], ecx
0x1800f84f8  mov     ecx, [rax+4]
0x1800f84fb  mov     [rsp+1B0h+var_13C], ecx
0x1800f84ff  movzx   ecx, word ptr [rax+2]
0x1800f8503  mov     word ptr [rsp+1B0h+var_140], cx
0x1800f8508  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x1800f850f  mov     qword ptr [rbp+0B0h+var_110.Data1], rax
0x1800f8513  lea     rax, [rbp+0B0h+var_A0]
0x1800f8517  mov     [rsp+1B0h+var_170], rax
0x1800f851c  lea     rax, [rbp+0B0h+var_90]
0x1800f8520  mov     [rsp+1B0h+var_178], rax
0x1800f8525  lea     rax, [rsp+1B0h+var_13C]
0x1800f852a  mov     [rsp+1B0h+Src], rax
0x1800f852f  lea     rax, [rsp+1B0h+var_140]
0x1800f8534  mov     [rsp+1B0h+var_188], rax
0x1800f8539  lea     rax, [rbp+0B0h+var_110]
0x1800f853d  mov     [rsp+1B0h+var_190], rax
0x1800f8542  lea     rdx, dword_1801A4B34
0x1800f8549  mov     rcx, r8
0x1800f854c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800f8551  jmp     loc_1800F85F6
0x1800f8556  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f855b  mov     r8, [rax+8]
0x1800f855f  mov     eax, [r8]
0x1800f8562  cmp     eax, 4
0x1800f8565  jbe     loc_1800F85F6
0x1800f856b  mov     rdx, rdi
0x1800f856e  mov     rcx, r8
0x1800f8571  call    _tlgKeywordOn
0x1800f8576  test    al, al
  ... truncated ...
```
