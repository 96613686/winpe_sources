# EffectPack::SetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,SpatialAudioSettings const *,bool)

- ea: `0x18008a0f4`
- end: `0x18008a99f`
- name: `?SetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@PEBUSpatialAudioSettings@@_N@Z`
- size: `2219`
- prototype: `__int64 __usercall@<rax>(EffectPack *__hidden this@<rcx>, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@<edx>, const struct tWAVEFORMATEX *@<r8>, const struct SpatialAudioSettings *@<r9>, bool)`
- caller_count: `6`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180089f38`
- `0x18008ba74`
- `0x180119ba0`
- `0x1801447e0`
- `0x180144adc`
- `0x18014a2c0`

## callees

- `0x180005210`
- `0x1800054c8`
- `0x180005590`
- `0x180008a2c`
- `0x18001280c`
- `0x1800202b0`
- `0x180040ec0`
- `0x1800413e0`
- `0x180061e64`
- `0x180072e10`
- `0x18008a0f4`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x18013fb4c`
- `0x180142de4`
- `0x180143508`
- `0x180144584`
- `0x180145634`
- `0x1801458a8`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a475`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a536`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a8f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a905`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a964`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a974`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a536`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a8f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a905`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a964`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a974`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008a5a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008a5a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a511`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a527`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a8d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a8e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a93f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a511`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a527`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a8d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a8e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a93f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a955`

## string_xrefs

- `0x18008a286`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008a4f2`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008a63c`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008a700`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008a784`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008a81a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008a884`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall EffectPack::SetDeviceFormatAndSpatialSettings(
        EffectPack *this,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a2,
        struct tWAVEFORMATEX *a3,
        const struct SpatialAudioSettings *a4,
        bool a5)
{
  const struct SpatialAudioSettings *v5; // r14
  struct tWAVEFORMATEX *p_Format; // rsi
  int v9; // r8d
  char *v10; // r9
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // eax
  int v14; // r8d
  char *v15; // r9
  int v16; // r8d
  int v17; // r9d
  struct _RTL_CRITICAL_SECTION *v18; // rdi
  int DeviceFormatAndSpatialSettings; // r15d
  void *v20; // rcx
  bool v21; // zf
  struct tWAVEFORMATEX *v22; // rcx
  int v24; // eax
  int AudioFormatForSpatialFormat; // eax
  struct WAVEFORMATEXTENSIBLE *v26; // rax
  bool v27; // cl
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  unsigned int v32; // esi
  int v33; // eax
  void *v34; // rcx
  struct tWAVEFORMATEX *v35; // rcx
  void *v36; // rcx
  struct tWAVEFORMATEX *v37; // rcx
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  struct SpatialAudioEncoderDescriptor **v41; // [rsp+30h] [rbp-D0h]
  bool v42; // [rsp+70h] [rbp-90h] BYREF
  char v43; // [rsp+71h] [rbp-8Fh] BYREF
  _WORD v44[3]; // [rsp+72h] [rbp-8Eh] BYREF
  struct tWAVEFORMATEX *v45; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  PROPVARIANT *p_DebugInfo; // [rsp+88h] [rbp-78h] BYREF
  WORD v48[2]; // [rsp+90h] [rbp-70h] BYREF
  int v49; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD nAvgBytesPerSec; // [rsp+98h] [rbp-68h] BYREF
  DWORD nSamplesPerSec; // [rsp+9Ch] [rbp-64h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-60h] BYREF
  char v53[8]; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID *p_pv; // [rsp+B0h] [rbp-50h] BYREF
  struct SpatialAudioSettings *v55; // [rsp+B8h] [rbp-48h] BYREF
  struct tWAVEFORMATEX **v56; // [rsp+C0h] [rbp-40h]
  int *v57; // [rsp+C8h] [rbp-38h]
  char v58; // [rsp+D0h] [rbp-30h]
  const wchar_t *v59; // [rsp+D8h] [rbp-28h] BYREF
  PROPVARIANT *v60; // [rsp+E0h] [rbp-20h] BYREF
  PROPVARIANT pvar[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v62; // [rsp+F8h] [rbp-8h]
  struct WAVEFORMATEXTENSIBLE v63; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v64[80]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v5 = a4;
  p_Format = a3;
  if ( a3 )
  {
    if ( a4 )
    {
      if ( a3->wFormatTag == 0xFFFE )
      {
        *(_OWORD *)pvar = *(_OWORD *)((char *)&a3[1].nSamplesPerSec + 2);
      }
      else
      {
        *(PROPVARIANT *)((char *)pvar + 4) = *(PROPVARIANT *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
        HIDWORD(pvar[1]) = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
        LODWORD(pvar[0]) = a3->wFormatTag;
      }
      if ( **((_DWORD **)this + 265) > 4u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 265), 16) )
      {
        v60 = pvar;
        nAvgBytesPerSec = p_Format->nAvgBytesPerSec;
        nSamplesPerSec = p_Format->nSamplesPerSec;
        v48[0] = p_Format->nChannels;
        v59 = L"WFEX";
        v44[0] = *((_WORD *)v10 + 34);
        *(_QWORD *)v53 = v10 + 12;
        v43 = *v10;
        p_DebugInfo = *(PROPVARIANT **)(*((_QWORD *)this + 198) + 48LL);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v9,
          (unsigned int)word_1801AB252,
          v9,
          (_DWORD)v10,
          (__int64)&p_DebugInfo,
          (__int64)&v43,
          (__int64)v53,
          (__int64)v44,
          (__int64)&v59,
          (__int64)v48,
          (__int64)&nSamplesPerSec,
          (__int64)&nAvgBytesPerSec,
          (__int64)&v60);
      }
      if ( *(_DWORD *)(*((_QWORD *)this + 198) + 236LL) )
      {
        LOBYTE(v38) = *(_DWORD *)v5 != 0;
        wil::details::in1diag3::Log_HrIfMsg(
          retaddr,
          (void *)0x22B3,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x80070032LL,
          v38,
          (bool)"Cannot enable spatial audio on a non-renderer endpoint",
          (const char *)v41);
        v5 = 0;
      }
    }
    else
    {
      if ( a3->wFormatTag == 0xFFFE )
      {
        *(_OWORD *)pvar = *(_OWORD *)((char *)&a3[1].nSamplesPerSec + 2);
      }
      else
      {
        *(PROPVARIANT *)((char *)pvar + 4) = *(PROPVARIANT *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
        HIDWORD(pvar[1]) = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
        LODWORD(pvar[0]) = a3->wFormatTag;
      }
      if ( **((_DWORD **)this + 265) > 4u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 265), 16) )
      {
        p_DebugInfo = pvar;
        nSamplesPerSec = p_Format->nAvgBytesPerSec;
        nAvgBytesPerSec = p_Format->nSamplesPerSec;
        v44[0] = p_Format->nChannels;
        *(_QWORD *)v53 = L"WFEX";
        v59 = *(const wchar_t **)(*((_QWORD *)this + 198) + 48LL);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v11,
          (unsigned int)&word_1801AB1D6,
          v11,
          v12,
          (__int64)&v59,
          (__int64)v53,
          (__int64)v44,
          (__int64)&nAvgBytesPerSec,
          (__int64)&nSamplesPerSec,
          (__int64)&p_DebugInfo);
      }
    }
  }
  else
  {
    v13 = **((_DWORD **)this + 265);
    if ( a4 )
    {
      if ( v13 > 4 && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 265), 16) )
      {
        v44[0] = *((_WORD *)v15 + 34);
        p_DebugInfo = (PROPVARIANT *)(v15 + 12);
        v43 = *v15;
        *(_QWORD *)v53 = *(_QWORD *)(*((_QWORD *)this + 198) + 48LL);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(
          v14,
          (unsigned int)word_1801AB132,
          v14,
          (_DWORD)v15,
          (__int64)v53,
          (__int64)&v43,
          (__int64)&p_DebugInfo,
          (__int64)v44);
      }
    }
    else if ( v13 > 4 && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 265), 16) )
    {
      p_DebugInfo = *(PROPVARIANT **)(*((_QWORD *)this + 198) + 48LL);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v16,
        (unsigned int)byte_1801AB195,
        v16,
        v17,
        (__int64)&p_DebugInfo);
    }
  }
  (*(void (__fastcall **)(__int64, LPCRITICAL_SECTION *, _QWORD))(*(_QWORD *)g_policyConfigInternal + 24LL))(
    g_policyConfigInternal,
    &lpCriticalSection,
    *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
  v18 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 198) + 0x2000LL);
  EnterCriticalSection(v18);
  p_DebugInfo = (PROPVARIANT *)&v18->DebugInfo;
  v45 = 0;
  pv = 0;
  p_pv = &pv;
  v55 = 0;
  LOBYTE(v56) = 1;
  pvar[0] = &v45;
  pvar[1] = 0;
  LOBYTE(v62) = 1;
  DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                     this,
                                     eHostProcessConnector,
                                     0,
                                     (struct tWAVEFORMATEX **)&pvar[1],
                                     &v55,
                                     0,
                                     0);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pvar);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( DeviceFormatAndSpatialSettings < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22E6,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)DeviceFormatAndSpatialSettings,
      v39);
LABEL_26:
    v20 = pv;
    v21 = pv == 0;
    pv = 0;
    if ( !v21 )
      CoTaskMemFree(v20);
    v22 = v45;
    v45 = 0;
    if ( v22 )
      CoTaskMemFree(v22);
    if ( v18 )
      LeaveCriticalSection(v18);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return (unsigned int)DeviceFormatAndSpatialSettings;
  }
  v49 = 0;
  *(_OWORD *)pvar = 0;
  v62 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64 *, PROPVARIANT *))(**(_QWORD **)(*((_QWORD *)this + 198) + 72LL) + 40LL))(
         *(_QWORD *)(*((_QWORD *)this + 198) + 72LL),
         PKEY_Endpoint_HWAudioEngine_Present,
         pvar) < 0
    || LOWORD(pvar[0]) != 11
    || (v24 = 1, !LOWORD(pvar[1])) )
  {
    v24 = 0;
  }
  v49 = v24;
  PropVariantClear(pvar);
  p_pv = (LPVOID *)this;
  v55 = (struct SpatialAudioSettings *)&pv;
  v56 = &v45;
  v57 = &v49;
  v58 = 1;
  pvar[0] = this;
  LOBYTE(pvar[1]) = 1;
  memset(&v63, 0, sizeof(v63));
  memset_0(v64, 0, 0x48u);
  v42 = 0;
  if ( !v5 )
  {
    v28 = *((_QWORD *)this + 198);
    if ( !p_Format )
    {
      CEndpointCharacteristics::ClearMixFormatCache(v28, 0);
      v33 = EffectPack::SetDeviceFormatSwAudioEngine((CEndpointCharacteristics **)this, a2, 0);
      v32 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2328,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v33,
          v39);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
          g_policyConfigInternal,
          *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
        v58 = 0;
        lambda_71ce65fa3fbbd27ce61e9a9a9578aff5_::operator()(&p_pv);
        goto LABEL_64;
      }
      goto LABEL_73;
    }
    if ( !*(_DWORD *)(v28 + 236)
      && EffectPack::GetSpatialFormatForAudioFormat(this, p_Format, (struct SpatialAudioSettings *)v64) >= 0 )
    {
      v5 = (const struct SpatialAudioSettings *)v64;
    }
    goto LABEL_50;
  }
  AudioFormatForSpatialFormat = EffectPack::GetAudioFormatForSpatialFormat(this, v5, v45, p_Format, &v63, &v42);
  DeviceFormatAndSpatialSettings = AudioFormatForSpatialFormat;
  if ( AudioFormatForSpatialFormat < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2314,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)AudioFormatForSpatialFormat,
      v39);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
      g_policyConfigInternal,
      *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
    v58 = 0;
    lambda_71ce65fa3fbbd27ce61e9a9a9578aff5_::operator()(&p_pv);
    goto LABEL_26;
  }
  v26 = &v63;
  v27 = v42;
  if ( !v42 )
    v26 = (struct WAVEFORMATEXTENSIBLE *)p_Format;
  p_Format = &v26->Format;
  if ( v26 )
  {
LABEL_50:
    CEndpointCharacteristics::ClearMixFormatCache(*((_QWORD *)this + 198), 0);
    if ( v49 )
    {
      v29 = CEndpointCharacteristics::SetDeviceFormatHwAudioEngine(*((CEndpointCharacteristics **)this + 198), p_Format);
      DeviceFormatAndSpatialSettings = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2331,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v29,
          v39);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
          g_policyConfigInternal,
          *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
        v58 = 0;
        lambda_71ce65fa3fbbd27ce61e9a9a9578aff5_::operator()(&p_pv);
        goto LABEL_26;
      }
    }
    (*(void (__fastcall **)(__int64, _QWORD, struct tWAVEFORMATEX *))(*(_QWORD *)g_policyConfigInternal + 40LL))(
      g_policyConfigInternal,
      *(_QWORD *)(*((_QWORD *)this + 198) + 48LL),
      p_Format);
    v30 = EffectPack::SetDeviceFormatSwAudioEngine((CEndpointCharacteristics **)this, a2, p_Format);
    DeviceFormatAndSpatialSettings = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2339,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v30,
        v39);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
        g_policyConfigInternal,
        *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
      v58 = 0;
      lambda_71ce65fa3fbbd27ce61e9a9a9578aff5_::operator()(&p_pv);
      goto LABEL_26;
    }
    if ( !v5 )
      goto LABEL_73;
    v27 = v42;
  }
  if ( !p_Format )
  {
    if ( v27 )
      goto LABEL_73;
    p_Format = v45;
  }
  v31 = CEndpointCharacteristics::SetSpatialAudioSettings(
          *((CEndpointCharacteristics **)this + 198),
          this,
          v5,
          p_Format,
          a5);
  v32 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2349,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v31,
      v40);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
      g_policyConfigInternal,
      *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
    v58 = 0;
    lambda_71ce65fa3fbbd27ce61e9a9a9578aff5_::operator()(&p_pv);
LABEL_64:
    v34 = pv;
    v21 = pv == 0;
    pv = 0;
    if ( !v21 )
      CoTaskMemFree(v34);
    v35 = v45;
    v21 = v45 == 0;
    v45 = 0;
    if ( !v21 )
      CoTaskMemFree(v35);
    if ( v18 )
      LeaveCriticalSection(v18);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return v32;
  }
LABEL_73:
  v58 = 0;
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
    g_policyConfigInternal,
    *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
  v36 = pv;
  pv = 0;
  if ( v36 )
    CoTaskMemFree(v36);
  v37 = v45;
  v45 = 0;
  if ( v37 )
    CoTaskMemFree(v37);
  if ( v18 )
    LeaveCriticalSection(v18);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x18008a0f4  push    rbp
0x18008a0f6  push    rbx
0x18008a0f7  push    rsi
0x18008a0f8  push    rdi
0x18008a0f9  push    r12
0x18008a0fb  push    r13
0x18008a0fd  push    r14
0x18008a0ff  push    r15
0x18008a101  lea     rbp, [rsp-98h]
0x18008a109  sub     rsp, 198h
0x18008a110  mov     rax, cs:__security_cookie
0x18008a117  xor     rax, rsp
0x18008a11a  mov     [rbp+0D0h+var_50], rax
0x18008a121  mov     r14, r9
0x18008a124  mov     rsi, r8
0x18008a127  mov     r12d, edx
0x18008a12a  mov     rbx, rcx
0x18008a12d  xor     r13d, r13d
0x18008a130  test    r8, r8
0x18008a133  jz      loc_18008A378
0x18008a139  mov     eax, 0FFFEh
0x18008a13e  test    r9, r9
0x18008a141  jz      loc_18008A29F
0x18008a147  cmp     [r8], ax
0x18008a14b  jnz     short loc_18008A159
0x18008a14d  movups  xmm0, xmmword ptr [r8+18h]
0x18008a152  movdqu  xmmword ptr [rbp+0D0h+pvar], xmm0
0x18008a157  jmp     short loc_18008A176
0x18008a159  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x18008a161  movsd   [rbp+0D0h+pvar+4], xmm0
0x18008a166  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x18008a16c  mov     dword ptr [rbp+0D0h+pvar+0Ch], eax
0x18008a16f  movzx   eax, word ptr [r8]
0x18008a173  mov     dword ptr [rbp+0D0h+pvar], eax
0x18008a176  mov     r8, [rcx+848h]
0x18008a17d  mov     eax, [r8]
0x18008a180  cmp     eax, 4
0x18008a183  jbe     loc_18008A24F
0x18008a189  mov     edx, 10h
0x18008a18e  mov     rcx, r8
0x18008a191  call    _tlgKeywordOn
0x18008a196  test    al, al
0x18008a198  jz      loc_18008A24F
0x18008a19e  lea     rax, [rbp+0D0h+pvar]
0x18008a1a2  mov     [rbp+0D0h+var_F0], rax
0x18008a1a6  mov     eax, [rsi+8]
0x18008a1a9  mov     [rbp+0D0h+var_138], eax
0x18008a1ac  mov     eax, [rsi+4]
0x18008a1af  mov     [rbp+0D0h+var_134], eax
0x18008a1b2  movzx   eax, word ptr [rsi+2]
0x18008a1b6  mov     [rbp+0D0h+var_140], ax
0x18008a1ba  lea     rax, aWfex; "WFEX"
0x18008a1c1  mov     [rbp+0D0h+var_F8], rax
0x18008a1c5  movzx   eax, word ptr [r9+44h]
0x18008a1ca  mov     [rsp+1D0h+var_15E], ax
0x18008a1cf  lea     rax, [r9+0Ch]
0x18008a1d3  mov     qword ptr [rbp+0D0h+var_128], rax
0x18008a1d7  mov     al, [r9]
0x18008a1da  mov     [rsp+1D0h+var_15F], al
0x18008a1de  mov     rax, [rbx+630h]
0x18008a1e5  mov     rcx, [rax+30h]
0x18008a1e9  mov     [rbp+0D0h+var_148], rcx
0x18008a1ed  lea     rax, [rbp+0D0h+var_F0]
0x18008a1f1  mov     [rsp+1D0h+var_170], rax
0x18008a1f6  lea     rax, [rbp+0D0h+var_138]
0x18008a1fa  mov     [rsp+1D0h+var_178], rax
0x18008a1ff  lea     rax, [rbp+0D0h+var_134]
0x18008a203  mov     [rsp+1D0h+var_180], rax
0x18008a208  lea     rax, [rbp+0D0h+var_140]
0x18008a20c  mov     [rsp+1D0h+var_188], rax
0x18008a211  lea     rax, [rbp+0D0h+var_F8]
0x18008a215  mov     [rsp+1D0h+var_190], rax
0x18008a21a  lea     rax, [rsp+1D0h+var_15E]
0x18008a21f  mov     [rsp+1D0h+var_198], rax
0x18008a224  lea     rax, [rbp+0D0h+var_128]
0x18008a228  mov     [rsp+1D0h+var_1A0], rax; char *
0x18008a22d  lea     rax, [rsp+1D0h+var_15F]
0x18008a232  mov     [rsp+1D0h+var_1A8], rax
0x18008a237  lea     rax, [rbp+0D0h+var_148]
0x18008a23b  mov     [rsp+1D0h+var_1B0], rax
0x18008a240  lea     rdx, word_1801AB252
0x18008a247  mov     rcx, r8
0x18008a24a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@U1@U4@U?$_tlgWrapperByVal@$03@@U5@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@36AEBU?$_tlgWrapperByVal@$03@@75@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008a24f  mov     rax, [rbx+630h]
0x18008a256  cmp     [rax+0ECh], r13d
0x18008a25d  jz      loc_18008A441
0x18008a263  cmp     [r14], r13d
0x18008a266  setnz   al
0x18008a269  mov     rcx, [rbp+0D8h]; this
0x18008a270  lea     rdx, aCannotEnableSp; "Cannot enable spatial audio on a non-re"...
0x18008a277  mov     [rsp+1D0h+var_1A8], rdx; bool
0x18008a27c  mov     byte ptr [rsp+1D0h+var_1B0], al; int
0x18008a280  mov     r9d, 80070032h; char *
0x18008a286  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18008a28d  mov     edx, 22B3h; void *
0x18008a292  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18008a297  mov     r14, r13
0x18008a29a  jmp     loc_18008A441
0x18008a29f  cmp     [r8], ax
0x18008a2a3  jnz     short loc_18008A2B1
0x18008a2a5  movups  xmm0, xmmword ptr [r8+18h]
0x18008a2aa  movdqu  xmmword ptr [rbp+0D0h+pvar], xmm0
0x18008a2af  jmp     short loc_18008A2CE
0x18008a2b1  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x18008a2b9  movsd   [rbp+0D0h+pvar+4], xmm0
0x18008a2be  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x18008a2c4  mov     dword ptr [rbp+0D0h+pvar+0Ch], eax
0x18008a2c7  movzx   eax, word ptr [r8]
0x18008a2cb  mov     dword ptr [rbp+0D0h+pvar], eax
0x18008a2ce  mov     r8, [rcx+848h]
0x18008a2d5  mov     eax, [r8]
0x18008a2d8  cmp     eax, 4
0x18008a2db  jbe     loc_18008A441
0x18008a2e1  mov     edx, 10h
0x18008a2e6  mov     rcx, r8
0x18008a2e9  call    _tlgKeywordOn
0x18008a2ee  test    al, al
0x18008a2f0  jz      loc_18008A441
0x18008a2f6  lea     rax, [rbp+0D0h+pvar]
0x18008a2fa  mov     [rbp+0D0h+var_148], rax
0x18008a2fe  mov     eax, [rsi+8]
0x18008a301  mov     [rbp+0D0h+var_134], eax
0x18008a304  mov     eax, [rsi+4]
0x18008a307  mov     [rbp+0D0h+var_138], eax
0x18008a30a  movzx   eax, word ptr [rsi+2]
0x18008a30e  mov     [rsp+1D0h+var_15E], ax
0x18008a313  lea     rax, aWfex; "WFEX"
0x18008a31a  mov     qword ptr [rbp+0D0h+var_128], rax
0x18008a31e  mov     rax, [rbx+630h]
0x18008a325  mov     rdx, [rax+30h]
0x18008a329  mov     [rbp+0D0h+var_F8], rdx
0x18008a32d  lea     rax, [rbp+0D0h+var_148]
0x18008a331  mov     [rsp+1D0h+var_188], rax
0x18008a336  lea     rax, [rbp+0D0h+var_134]
0x18008a33a  mov     [rsp+1D0h+var_190], rax
0x18008a33f  lea     rax, [rbp+0D0h+var_138]
0x18008a343  mov     [rsp+1D0h+var_198], rax
0x18008a348  lea     rax, [rsp+1D0h+var_15E]
0x18008a34d  mov     [rsp+1D0h+var_1A0], rax
0x18008a352  lea     rax, [rbp+0D0h+var_128]
0x18008a356  mov     [rsp+1D0h+var_1A8], rax
0x18008a35b  lea     rax, [rbp+0D0h+var_F8]
0x18008a35f  mov     [rsp+1D0h+var_1B0], rax
0x18008a364  lea     rdx, word_1801AB1D6
0x18008a36b  mov     rcx, r8
0x18008a36e  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008a373  jmp     loc_18008A441
0x18008a378  mov     r8, [rcx+848h]
0x18008a37f  mov     eax, [r8]
0x18008a382  test    r14, r14
0x18008a385  jz      short loc_18008A404
0x18008a387  cmp     eax, 4
0x18008a38a  jbe     loc_18008A441
0x18008a390  mov     edx, 10h
0x18008a395  mov     rcx, r8
0x18008a398  call    _tlgKeywordOn
0x18008a39d  test    al, al
0x18008a39f  jz      loc_18008A441
0x18008a3a5  movzx   eax, word ptr [r9+44h]
0x18008a3aa  mov     [rsp+1D0h+var_15E], ax
0x18008a3af  lea     rax, [r9+0Ch]
0x18008a3b3  mov     [rbp+0D0h+var_148], rax
0x18008a3b7  mov     al, [r9]
0x18008a3ba  mov     [rsp+1D0h+var_15F], al
0x18008a3be  mov     rax, [rbx+630h]
0x18008a3c5  mov     rdx, [rax+30h]
0x18008a3c9  mov     qword ptr [rbp+0D0h+var_128], rdx
0x18008a3cd  lea     rax, [rsp+1D0h+var_15E]
0x18008a3d2  mov     [rsp+1D0h+var_198], rax
0x18008a3d7  lea     rax, [rbp+0D0h+var_148]
0x18008a3db  mov     [rsp+1D0h+var_1A0], rax
0x18008a3e0  lea     rax, [rsp+1D0h+var_15F]
0x18008a3e5  mov     [rsp+1D0h+var_1A8], rax
0x18008a3ea  lea     rax, [rbp+0D0h+var_128]
0x18008a3ee  mov     [rsp+1D0h+var_1B0], rax
0x18008a3f3  lea     rdx, word_1801AB132
0x18008a3fa  mov     rcx, r8
0x18008a3fd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &)
0x18008a402  jmp     short loc_18008A441
0x18008a404  cmp     eax, 4
0x18008a407  jbe     short loc_18008A441
0x18008a409  mov     edx, 10h
0x18008a40e  mov     rcx, r8
0x18008a411  call    _tlgKeywordOn
0x18008a416  test    al, al
0x18008a418  jz      short loc_18008A441
0x18008a41a  mov     rax, [rbx+630h]
0x18008a421  mov     rdx, [rax+30h]
0x18008a425  mov     [rbp+0D0h+var_148], rdx
0x18008a429  lea     rax, [rbp+0D0h+var_148]
0x18008a42d  mov     [rsp+1D0h+var_1B0], rax
0x18008a432  lea     rdx, byte_1801AB195
0x18008a439  mov     rcx, r8
0x18008a43c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18008a441  mov     rcx, cs:?g_policyConfigInternal@@3V?$com_ptr_t@UIPolicyConfigInternal@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IPolicyConfigInternal,wil::err_returncode_policy> g_policyConfigInternal
0x18008a448  mov     rax, [rcx]
0x18008a44b  mov     r8, [rbx+630h]
0x18008a452  mov     r8, [r8+30h]
0x18008a456  lea     rdx, [rbp+0D0h+lpCriticalSection]
0x18008a45a  mov     rax, [rax+18h]
0x18008a45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a463  nop
0x18008a464  mov     rdi, [rbx+630h]
0x18008a46b  add     rdi, 2000h
0x18008a472  mov     rcx, rdi; lpCriticalSection
0x18008a475  call    cs:__imp_EnterCriticalSection
0x18008a47b  mov     [rbp+0D0h+var_148], rdi
0x18008a47f  mov     [rsp+1D0h+var_158], r13
0x18008a484  mov     [rbp+0D0h+pv], r13
0x18008a488  lea     rax, [rbp+0D0h+pv]
0x18008a48c  mov     [rbp+0D0h+var_120], rax
0x18008a490  mov     [rbp+0D0h+var_118], r13
0x18008a494  mov     byte ptr [rbp+0D0h+var_110], 1
0x18008a498  lea     rax, [rsp+1D0h+var_158]
0x18008a49d  mov     [rbp+0D0h+pvar], rax
0x18008a4a1  mov     [rbp+0D0h+pvar+8], r13
0x18008a4a5  mov     byte ptr [rbp+0D0h+var_D8], 1
0x18008a4a9  mov     [rsp+1D0h+var_1A0], r13; pv
0x18008a4ae  mov     [rsp+1D0h+var_1A8], r13; unsigned int *
0x18008a4b3  lea     rax, [rbp+0D0h+var_118]
0x18008a4b7  mov     [rsp+1D0h+var_1B0], rax; int
0x18008a4bc  lea     r9, [rbp+0D0h+pvar+8]; struct tWAVEFORMATEX **
0x18008a4c0  xor     r8d, r8d; int
0x18008a4c3  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18008a4c5  mov     rcx, rbx; this
0x18008a4c8  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x18008a4cd  mov     r15d, eax
0x18008a4d0  lea     rcx, [rbp+0D0h+pvar]
0x18008a4d4  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18008a4d9  nop
0x18008a4da  lea     rcx, [rbp+0D0h+var_120]
0x18008a4de  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18008a4e3  test    r15d, r15d
0x18008a4e6  jns     short loc_18008A554
0x18008a4e8  mov     rcx, [rbp+0D8h]; this
0x18008a4ef  mov     r9d, r15d; char *
0x18008a4f2  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18008a4f9  mov     edx, 22E6h; void *
0x18008a4fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a503  nop
0x18008a504  mov     rcx, [rbp+0D0h+pv]; pv
0x18008a508  test    rcx, rcx
0x18008a50b  mov     [rbp+0D0h+pv], r13
0x18008a50f  jz      short loc_18008A518
0x18008a511  call    cs:__imp_CoTaskMemFree
0x18008a517  nop
0x18008a518  mov     rcx, [rsp+1D0h+var_158]; pv
0x18008a51d  mov     [rsp+1D0h+var_158], r13
0x18008a522  test    rcx, rcx
0x18008a525  jz      short loc_18008A52E
0x18008a527  call    cs:__imp_CoTaskMemFree
0x18008a52d  nop
0x18008a52e  test    rdi, rdi
0x18008a531  jz      short loc_18008A53D
0x18008a533  mov     rcx, rdi; lpCriticalSection
0x18008a536  call    cs:__imp_LeaveCriticalSection
0x18008a53c  nop
0x18008a53d  mov     rcx, [rbp+0D0h+lpCriticalSection]; lpCriticalSection
0x18008a541  test    rcx, rcx
0x18008a544  jz      short loc_18008A54C
0x18008a546  call    cs:__imp_LeaveCriticalSection
0x18008a54c  mov     eax, r15d
0x18008a54f  jmp     loc_18008A97C
0x18008a554  mov     [rbp+0D0h+var_13C], r13d
0x18008a558  xorps   xmm0, xmm0
0x18008a55b  xor     eax, eax
0x18008a55d  movups  xmmword ptr [rbp+0D0h+pvar], xmm0
0x18008a561  mov     [rbp+0D0h+var_D8], rax
0x18008a565  mov     rax, [rbx+630h]
0x18008a56c  mov     rcx, [rax+48h]
0x18008a570  mov     rax, [rcx]
0x18008a573  lea     r8, [rbp+0D0h+pvar]
0x18008a577  lea     rdx, PKEY_Endpoint_HWAudioEngine_Present
0x18008a57e  mov     rax, [rax+28h]
0x18008a582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a587  test    eax, eax
0x18008a589  js      short loc_18008A59E
0x18008a58b  cmp     word ptr [rbp+0D0h+pvar], 0Bh
0x18008a590  jnz     short loc_18008A59E
0x18008a592  cmp     word ptr [rbp+0D0h+pvar+8], r13w
0x18008a597  mov     eax, 1
0x18008a59c  jnz     short loc_18008A5A1
0x18008a59e  mov     eax, r13d
0x18008a5a1  mov     [rbp+0D0h+var_13C], eax
0x18008a5a4  lea     rcx, [rbp+0D0h+pvar]; pvar
0x18008a5a8  call    cs:__imp_PropVariantClear
0x18008a5ae  mov     [rbp+0D0h+var_120], rbx
0x18008a5b2  lea     rax, [rbp+0D0h+pv]
0x18008a5b6  mov     [rbp+0D0h+var_118], rax
0x18008a5ba  lea     rax, [rsp+1D0h+var_158]
0x18008a5bf  mov     [rbp+0D0h+var_110], rax
0x18008a5c3  lea     rax, [rbp+0D0h+var_13C]
0x18008a5c7  mov     [rbp+0D0h+var_108], rax
0x18008a5cb  mov     [rbp+0D0h+var_100], 1
0x18008a5cf  mov     [rbp+0D0h+pvar], rbx
0x18008a5d3  mov     byte ptr [rbp+0D0h+pvar+8], 1
0x18008a5d7  xorps   xmm0, xmm0
0x18008a5da  xor     eax, eax
0x18008a5dc  movups  xmmword ptr [rbp+0D0h+var_D0.Format.wFormatTag], xmm0
0x18008a5e0  movups  xmmword ptr [rbp+0D0h+var_D0.Format.cbSize], xmm0
  ... truncated ...
```
