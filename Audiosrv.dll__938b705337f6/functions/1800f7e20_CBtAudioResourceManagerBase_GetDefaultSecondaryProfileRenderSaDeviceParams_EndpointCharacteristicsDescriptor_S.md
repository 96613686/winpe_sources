# CBtAudioResourceManagerBase::GetDefaultSecondaryProfileRenderSaDeviceParams(EndpointCharacteristicsDescriptor *,SaDeviceParams * *)

- ea: `0x1800f7e20`
- end: `0x1800f8518`
- name: `?GetDefaultSecondaryProfileRenderSaDeviceParams@CBtAudioResourceManagerBase@@IEAAJPEAUEndpointCharacteristicsDescriptor@@PEAPEAUSaDeviceParams@@@Z`
- size: `1784`
- prototype: `int(CBtAudioResourceManagerBase *__hidden this, struct EndpointCharacteristicsDescriptor *, struct SaDeviceParams **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f7338`

## callees

- `0x1800088dc`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18001df60`
- `0x18001eb4c`
- `0x180045068`
- `0x18004a38c`
- `0x18005b03c`
- `0x1800618c0`
- `0x180073310`
- `0x1800cf8c0`
- `0x1800f7e20`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7fc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7fda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f84a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f84bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f84d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f84e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7fc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7fda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f84a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f84bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f84d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f84e4`

## string_xrefs

- `0x1800f7f91`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`

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
          (unsigned int)&unk_1801A39DE,
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
          (unsigned int)&unk_1801A3A7F,
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
        (unsigned int)&unk_1801A3B13,
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
          (unsigned int)&unk_1801A3851,
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
          (unsigned int)&unk_1801A38F1,
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
        (unsigned int)&unk_1801A3984,
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
0x1800f7e20  mov     rax, rsp
0x1800f7e23  mov     [rax+20h], rbx
0x1800f7e27  push    rbp
0x1800f7e28  push    rsi
0x1800f7e29  push    rdi
0x1800f7e2a  push    r12
0x1800f7e2c  push    r13
0x1800f7e2e  push    r14
0x1800f7e30  push    r15
0x1800f7e32  lea     rbp, [rsp-80h]
0x1800f7e37  sub     rsp, 180h
0x1800f7e3e  movaps  xmmword ptr [rax-48h], xmm6
0x1800f7e42  mov     rax, cs:__security_cookie
0x1800f7e49  xor     rax, rsp
0x1800f7e4c  mov     [rbp+0B0h+var_50], rax
0x1800f7e50  mov     r12, r8
0x1800f7e53  mov     r15, rdx
0x1800f7e56  mov     r14, rcx
0x1800f7e59  xor     r13d, r13d
0x1800f7e5c  mov     [rbp+0B0h+var_130], r13
0x1800f7e60  mov     [rbp+0B0h+var_128], r13
0x1800f7e64  mov     [rbp+0B0h+var_118], r13
0x1800f7e68  mov     [rbp+0B0h+pv], r13
0x1800f7e6c  lea     rax, [rbp+0B0h+var_130]
0x1800f7e70  mov     [rbp+0B0h+var_B8], rax
0x1800f7e74  mov     [rbp+0B0h+var_B0], r13
0x1800f7e78  mov     [rbp+0B0h+var_A8], 1
0x1800f7e7c  lea     rax, [rbp+0B0h+var_128]
0x1800f7e80  mov     [rbp+0B0h+var_D0], rax
0x1800f7e84  mov     [rbp+0B0h+var_C8], r13
0x1800f7e88  mov     [rbp+0B0h+var_C0], 1
0x1800f7e8c  lea     rax, [rbp+0B0h+pv]
0x1800f7e90  mov     [rbp+0B0h+var_E8], rax
0x1800f7e94  mov     [rbp+0B0h+var_E0], r13
0x1800f7e98  mov     [rbp+0B0h+var_D8], 1
0x1800f7e9c  lea     rax, [rbp+0B0h+var_118]
0x1800f7ea0  mov     [rbp+0B0h+var_100], rax
0x1800f7ea4  mov     [rbp+0B0h+var_F8], r13
0x1800f7ea8  mov     [rbp+0B0h+var_F0], 1
0x1800f7eac  mov     rax, [rcx]
0x1800f7eaf  lea     rdx, [rbp+0B0h+var_90]
0x1800f7eb3  mov     rax, [rax+88h]
0x1800f7eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7ebf  movups  xmm6, xmmword ptr [rax]
0x1800f7ec2  mov     rax, [r14]
0x1800f7ec5  lea     rdx, [rbp+0B0h+var_60]
0x1800f7ec9  mov     rcx, r14
0x1800f7ecc  mov     rax, [rax+88h]
0x1800f7ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7ed8  movdqu  xmmword ptr [rbp+0B0h+var_80.Data1], xmm6
0x1800f7edd  movups  xmm0, xmmword ptr [rax]
0x1800f7ee0  movdqu  xmmword ptr [rbp+0B0h+var_A0.Data1], xmm0
0x1800f7ee5  mov     rax, [r14]
0x1800f7ee8  lea     rdx, [rbp+0B0h+var_70]
0x1800f7eec  mov     rcx, r14
0x1800f7eef  mov     rax, [rax+88h]
0x1800f7ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7efb  movups  xmm0, xmmword ptr [rax]
0x1800f7efe  movdqu  xmmword ptr [rbp+0B0h+var_110.Data1], xmm0
0x1800f7f03  lea     rax, [rbp+0B0h+var_B0]
0x1800f7f07  mov     [rsp+1B0h+var_150], rax; struct tWAVEFORMATEX **
0x1800f7f0c  lea     rax, [rbp+0B0h+var_C8]
0x1800f7f10  mov     [rsp+1B0h+var_158], rax; struct tWAVEFORMATEX **
0x1800f7f15  lea     rax, [rbp+0B0h+var_E0]
0x1800f7f19  mov     [rsp+1B0h+var_160], rax; struct tWAVEFORMATEX **
0x1800f7f1e  lea     rax, [rbp+0B0h+var_F8]
0x1800f7f22  mov     [rsp+1B0h+var_168], rax; struct tWAVEFORMATEX **
0x1800f7f27  mov     [rsp+1B0h+var_170], r13; struct tWAVEFORMATEX *
0x1800f7f2c  lea     rax, [rbp+0B0h+var_80]
0x1800f7f30  mov     [rsp+1B0h+var_178], rax; struct _GUID *
0x1800f7f35  lea     rax, [rbp+0B0h+var_A0]
0x1800f7f39  mov     [rsp+1B0h+Src], rax; struct _GUID *
0x1800f7f3e  lea     rax, [rbp+0B0h+var_110]
0x1800f7f42  mov     [rsp+1B0h+var_188], rax; struct _GUID *
0x1800f7f47  mov     dword ptr [rsp+1B0h+var_190], r13d; int
0x1800f7f4c  xor     r9d, r9d; enum _AUDCLNT_SHAREMODE
0x1800f7f4f  xor     r8d, r8d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800f7f52  xor     edx, edx; bool
0x1800f7f54  mov     rcx, r15; struct EndpointCharacteristicsDescriptor *
0x1800f7f57  call    ?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z; DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)
0x1800f7f5c  mov     ebx, eax
0x1800f7f5e  lea     rcx, [rbp+0B0h+var_100]
0x1800f7f62  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f7f67  nop
0x1800f7f68  lea     rcx, [rbp+0B0h+var_E8]
0x1800f7f6c  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f7f71  nop
0x1800f7f72  lea     rcx, [rbp+0B0h+var_D0]
0x1800f7f76  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f7f7b  nop
0x1800f7f7c  lea     rcx, [rbp+0B0h+var_B8]
0x1800f7f80  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800f7f85  test    ebx, ebx
0x1800f7f87  jns     short loc_1800F7FFB
0x1800f7f89  mov     edx, 252h; void *
0x1800f7f8e  mov     r9d, ebx; char *
0x1800f7f91  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f7f98  mov     rcx, [rbp+0B8h]; this
0x1800f7f9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7fa4  nop
0x1800f7fa5  mov     rcx, [rbp+0B0h+pv]; pv
0x1800f7fa9  mov     [rbp+0B0h+pv], r13
0x1800f7fad  test    rcx, rcx
0x1800f7fb0  jz      short loc_1800F7FB9
0x1800f7fb2  call    cs:__imp_CoTaskMemFree
0x1800f7fb8  nop
0x1800f7fb9  mov     rcx, [rbp+0B0h+var_118]; pv
0x1800f7fbd  mov     [rbp+0B0h+var_118], r13
0x1800f7fc1  test    rcx, rcx
0x1800f7fc4  jz      short loc_1800F7FCD
0x1800f7fc6  call    cs:__imp_CoTaskMemFree
0x1800f7fcc  nop
0x1800f7fcd  mov     rcx, [rbp+0B0h+var_128]; pv
0x1800f7fd1  test    rcx, rcx
0x1800f7fd4  mov     [rbp+0B0h+var_128], r13
0x1800f7fd8  jz      short loc_1800F7FE1
0x1800f7fda  call    cs:__imp_CoTaskMemFree
0x1800f7fe0  nop
0x1800f7fe1  mov     rcx, [rbp+0B0h+var_130]; pv
0x1800f7fe5  mov     [rbp+0B0h+var_130], r13
0x1800f7fe9  test    rcx, rcx
0x1800f7fec  jz      short loc_1800F7FF4
0x1800f7fee  call    cs:__imp_CoTaskMemFree
0x1800f7ff4  mov     eax, ebx
0x1800f7ff6  jmp     loc_1800F84EC
0x1800f7ffb  mov     esi, 0FFFEh
0x1800f8000  mov     edi, 4200h
0x1800f8005  mov     rbx, [rbp+0B0h+var_128]
0x1800f8009  test    rbx, rbx
0x1800f800c  jnz     short loc_1800F8058
0x1800f800e  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f8013  mov     r8, [rax+8]
0x1800f8017  mov     eax, [r8]
0x1800f801a  cmp     eax, 4
0x1800f801d  jbe     loc_1800F81B7
0x1800f8023  mov     edx, edi
0x1800f8025  mov     rcx, r8
0x1800f8028  call    _tlgKeywordOn
0x1800f802d  test    al, al
0x1800f802f  jz      loc_1800F81B7
0x1800f8035  mov     [rsp+1B0h+var_140], r13d
0x1800f803a  lea     rax, [rsp+1B0h+var_140]
0x1800f803f  mov     [rsp+1B0h+var_190], rax
0x1800f8044  lea     rdx, unk_1801A3B13
0x1800f804b  mov     rcx, r8
0x1800f804e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800f8053  jmp     loc_1800F81B7
0x1800f8058  movzx   ecx, word ptr [rbx]
0x1800f805b  cmp     cx, si
0x1800f805e  jz      loc_1800F8117
0x1800f8064  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x1800f806c  movsd   qword ptr [rbp+0B0h+var_A0.Data2], xmm0
0x1800f8071  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x1800f8077  mov     dword ptr [rbp+0B0h+var_A0.Data4+4], eax
0x1800f807a  mov     [rbp+0B0h+var_A0.Data1], ecx
0x1800f807d  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f8082  mov     r8, [rax+8]
0x1800f8086  mov     eax, [r8]
0x1800f8089  cmp     eax, 4
0x1800f808c  jbe     loc_1800F81B7
0x1800f8092  mov     rdx, rdi
0x1800f8095  mov     rcx, r8
0x1800f8098  call    _tlgKeywordOn
0x1800f809d  test    al, al
0x1800f809f  jz      loc_1800F81B7
0x1800f80a5  lea     rax, [rbp+0B0h+var_A0]
0x1800f80a9  mov     [rbp+0B0h+var_90], rax
0x1800f80ad  mov     rax, [rbp+0B0h+var_128]
0x1800f80b1  mov     ecx, [rax+8]
0x1800f80b4  mov     [rsp+1B0h+var_138], ecx
0x1800f80b8  mov     ecx, [rax+4]
0x1800f80bb  mov     [rsp+1B0h+var_13C], ecx
0x1800f80bf  movzx   ecx, word ptr [rax+2]
0x1800f80c3  mov     word ptr [rsp+1B0h+var_140], cx
0x1800f80c8  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x1800f80cf  mov     qword ptr [rbp+0B0h+var_110.Data1], rax
0x1800f80d3  lea     rax, [rbp+0B0h+var_90]
0x1800f80d7  mov     [rsp+1B0h+var_170], rax
0x1800f80dc  lea     rax, [rsp+1B0h+var_138]
0x1800f80e1  mov     [rsp+1B0h+var_178], rax
0x1800f80e6  lea     rax, [rsp+1B0h+var_13C]
0x1800f80eb  mov     [rsp+1B0h+Src], rax
0x1800f80f0  lea     rax, [rsp+1B0h+var_140]
0x1800f80f5  mov     [rsp+1B0h+var_188], rax
0x1800f80fa  lea     rax, [rbp+0B0h+var_110]
0x1800f80fe  mov     [rsp+1B0h+var_190], rax
0x1800f8103  lea     rdx, unk_1801A3A7F
0x1800f810a  mov     rcx, r8
0x1800f810d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800f8112  jmp     loc_1800F81B7
0x1800f8117  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f811c  mov     r8, [rax+8]
0x1800f8120  mov     eax, [r8]
0x1800f8123  cmp     eax, 4
0x1800f8126  jbe     loc_1800F81B7
0x1800f812c  mov     rdx, rdi
0x1800f812f  mov     rcx, r8
0x1800f8132  call    _tlgKeywordOn
0x1800f8137  test    al, al
0x1800f8139  jz      short loc_1800F81B7
0x1800f813b  mov     eax, [rbx+14h]
0x1800f813e  mov     [rsp+1B0h+var_13C], eax
0x1800f8142  lea     rax, [rbx+18h]
0x1800f8146  mov     qword ptr [rbp+0B0h+var_110.Data1], rax
0x1800f814a  mov     rax, [rbp+0B0h+var_128]
0x1800f814e  mov     ecx, [rax+8]
0x1800f8151  mov     [rsp+1B0h+var_138], ecx
0x1800f8155  mov     ecx, [rax+4]
0x1800f8158  mov     dword ptr [rbp+0B0h+var_90], ecx
0x1800f815b  movzx   ecx, word ptr [rax+2]
0x1800f815f  mov     word ptr [rsp+1B0h+var_140], cx
0x1800f8164  lea     rax, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x1800f816b  mov     qword ptr [rbp+0B0h+var_A0.Data1], rax
0x1800f816f  lea     rax, [rsp+1B0h+var_13C]
0x1800f8174  mov     [rsp+1B0h+var_168], rax
0x1800f8179  lea     rax, [rbp+0B0h+var_110]
0x1800f817d  mov     [rsp+1B0h+var_170], rax
0x1800f8182  lea     rax, [rsp+1B0h+var_138]
0x1800f8187  mov     [rsp+1B0h+var_178], rax
0x1800f818c  lea     rax, [rbp+0B0h+var_90]
0x1800f8190  mov     [rsp+1B0h+Src], rax
0x1800f8195  lea     rax, [rsp+1B0h+var_140]
0x1800f819a  mov     [rsp+1B0h+var_188], rax
0x1800f819f  lea     rax, [rbp+0B0h+var_A0]
0x1800f81a3  mov     [rsp+1B0h+var_190], rax
0x1800f81a8  lea     rdx, unk_1801A39DE
0x1800f81af  mov     rcx, r8
0x1800f81b2  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800f81b7  mov     rbx, [rbp+0B0h+var_130]
0x1800f81bb  test    rbx, rbx
0x1800f81be  jnz     short loc_1800F8209
0x1800f81c0  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f81c5  mov     r8, [rax+8]
0x1800f81c9  mov     eax, [r8]
0x1800f81cc  cmp     eax, 4
0x1800f81cf  jbe     loc_1800F8366
0x1800f81d5  mov     rdx, rdi
0x1800f81d8  mov     rcx, r8
0x1800f81db  call    _tlgKeywordOn
0x1800f81e0  test    al, al
0x1800f81e2  jz      loc_1800F8366
0x1800f81e8  mov     dword ptr [rbp+0B0h+var_90], r13d
0x1800f81ec  lea     rax, [rbp+0B0h+var_90]
0x1800f81f0  mov     [rsp+1B0h+var_190], rax
0x1800f81f5  lea     rdx, unk_1801A3984
0x1800f81fc  mov     rcx, r8
0x1800f81ff  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800f8204  jmp     loc_1800F8366
0x1800f8209  movzx   ecx, word ptr [rbx]
0x1800f820c  cmp     cx, si
0x1800f820f  jz      loc_1800F82C6
0x1800f8215  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x1800f821d  movsd   qword ptr [rbp+0B0h+var_80.Data2], xmm0
0x1800f8222  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x1800f8228  mov     dword ptr [rbp+0B0h+var_80.Data4+4], eax
0x1800f822b  mov     [rbp+0B0h+var_80.Data1], ecx
0x1800f822e  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f8233  mov     r8, [rax+8]
0x1800f8237  mov     eax, [r8]
0x1800f823a  cmp     eax, 4
0x1800f823d  jbe     loc_1800F8366
0x1800f8243  mov     rdx, rdi
0x1800f8246  mov     rcx, r8
0x1800f8249  call    _tlgKeywordOn
0x1800f824e  test    al, al
0x1800f8250  jz      loc_1800F8366
0x1800f8256  lea     rax, [rbp+0B0h+var_80]
0x1800f825a  mov     qword ptr [rbp+0B0h+var_A0.Data1], rax
0x1800f825e  mov     rax, [rbp+0B0h+var_130]
0x1800f8262  mov     ecx, [rax+8]
0x1800f8265  mov     dword ptr [rbp+0B0h+var_90], ecx
0x1800f8268  mov     ecx, [rax+4]
0x1800f826b  mov     [rsp+1B0h+var_13C], ecx
0x1800f826f  movzx   ecx, word ptr [rax+2]
0x1800f8273  mov     word ptr [rsp+1B0h+var_140], cx
0x1800f8278  lea     rax, aWaveformatex; "WAVEFORMATEX"
0x1800f827f  mov     qword ptr [rbp+0B0h+var_110.Data1], rax
0x1800f8283  lea     rax, [rbp+0B0h+var_A0]
0x1800f8287  mov     [rsp+1B0h+var_170], rax
0x1800f828c  lea     rax, [rbp+0B0h+var_90]
0x1800f8290  mov     [rsp+1B0h+var_178], rax
0x1800f8295  lea     rax, [rsp+1B0h+var_13C]
0x1800f829a  mov     [rsp+1B0h+Src], rax
0x1800f829f  lea     rax, [rsp+1B0h+var_140]
0x1800f82a4  mov     [rsp+1B0h+var_188], rax
0x1800f82a9  lea     rax, [rbp+0B0h+var_110]
0x1800f82ad  mov     [rsp+1B0h+var_190], rax
0x1800f82b2  lea     rdx, unk_1801A38F1
0x1800f82b9  mov     rcx, r8
0x1800f82bc  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800f82c1  jmp     loc_1800F8366
0x1800f82c6  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f82cb  mov     r8, [rax+8]
0x1800f82cf  mov     eax, [r8]
0x1800f82d2  cmp     eax, 4
0x1800f82d5  jbe     loc_1800F8366
0x1800f82db  mov     rdx, rdi
0x1800f82de  mov     rcx, r8
0x1800f82e1  call    _tlgKeywordOn
0x1800f82e6  test    al, al
  ... truncated ...
```
