# EffectPack::SetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,SpatialAudioSettings const *,bool)

- ea: `0x18008a5f4`
- end: `0x18008ae9f`
- name: `?SetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@PEBUSpatialAudioSettings@@_N@Z`
- size: `2219`
- prototype: `__int64 __usercall@<rax>(EffectPack *__hidden this@<rcx>, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@<edx>, const struct tWAVEFORMATEX *@<r8>, const struct SpatialAudioSettings *@<r9>, bool)`
- caller_count: `6`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008a438`
- `0x18008b9c8`
- `0x180119950`
- `0x180143dd0`
- `0x1801440cc`
- `0x1801495b0`

## callees

- `0x180005004`
- `0x1800052bc`
- `0x180005384`
- `0x1800088dc`
- `0x1800126bc`
- `0x180020160`
- `0x180040d50`
- `0x1800412c8`
- `0x1800622f4`
- `0x180073310`
- `0x18008a5f4`
- `0x1800c5050`
- `0x1800c512c`
- `0x1800c52bc`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x1801424d4`
- `0x180142bf8`
- `0x180143c74`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a975`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008aa36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008aa46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008adf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ae05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ae64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ae74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008aa36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008aa46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008adf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ae05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ae64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ae74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008aaa8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008aaa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008aa11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008aa27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008add0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ade6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ae3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ae55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008aa11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008aa27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008add0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ade6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ae3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ae55`

## string_xrefs

- `0x18008a786`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008a9f2`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008ab3c`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008ac00`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008ac84`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008ad1a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18008ad84`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
          (unsigned int)&unk_1801A99BC,
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
          (void *)0x22B4,
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
          (unsigned int)&unk_1801A9812,
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
          (unsigned int)&unk_1801A98DB,
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
        (unsigned int)&unk_1801A97D1,
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
      (void *)0x22E7,
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
  if ( (*(int (__fastcall **)(_QWORD, void *, PROPVARIANT *))(**(_QWORD **)(*((_QWORD *)this + 198) + 72LL) + 40LL))(
         *(_QWORD *)(*((_QWORD *)this + 198) + 72LL),
         &PKEY_Endpoint_HWAudioEngine_Present,
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
          (void *)0x2329,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v33,
          v39);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
          g_policyConfigInternal,
          *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
        v58 = 0;
        lambda_33c05186dc393f8f69b04e289ffb191a_::operator()(&p_pv);
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
      (void *)0x2315,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)AudioFormatForSpatialFormat,
      v39);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
      g_policyConfigInternal,
      *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
    v58 = 0;
    lambda_33c05186dc393f8f69b04e289ffb191a_::operator()(&p_pv);
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
          (void *)0x2332,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)v29,
          v39);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
          g_policyConfigInternal,
          *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
        v58 = 0;
        lambda_33c05186dc393f8f69b04e289ffb191a_::operator()(&p_pv);
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
        (void *)0x233A,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v30,
        v39);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
        g_policyConfigInternal,
        *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
      v58 = 0;
      lambda_33c05186dc393f8f69b04e289ffb191a_::operator()(&p_pv);
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
      (void *)0x234A,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v31,
      v40);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_policyConfigInternal + 32LL))(
      g_policyConfigInternal,
      *(_QWORD *)(*((_QWORD *)this + 198) + 48LL));
    v58 = 0;
    lambda_33c05186dc393f8f69b04e289ffb191a_::operator()(&p_pv);
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
0x18008a5f4  push    rbp
0x18008a5f6  push    rbx
0x18008a5f7  push    rsi
0x18008a5f8  push    rdi
0x18008a5f9  push    r12
0x18008a5fb  push    r13
0x18008a5fd  push    r14
0x18008a5ff  push    r15
0x18008a601  lea     rbp, [rsp-98h]
0x18008a609  sub     rsp, 198h
0x18008a610  mov     rax, cs:__security_cookie
0x18008a617  xor     rax, rsp
0x18008a61a  mov     [rbp+0D0h+var_50], rax
0x18008a621  mov     r14, r9
0x18008a624  mov     rsi, r8
0x18008a627  mov     r12d, edx
0x18008a62a  mov     rbx, rcx
0x18008a62d  xor     r13d, r13d
0x18008a630  test    r8, r8
0x18008a633  jz      loc_18008A878
0x18008a639  mov     eax, 0FFFEh
0x18008a63e  test    r9, r9
0x18008a641  jz      loc_18008A79F
0x18008a647  cmp     [r8], ax
0x18008a64b  jnz     short loc_18008A659
0x18008a64d  movups  xmm0, xmmword ptr [r8+18h]
0x18008a652  movdqu  xmmword ptr [rbp+0D0h+pvar], xmm0
0x18008a657  jmp     short loc_18008A676
0x18008a659  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x18008a661  movsd   [rbp+0D0h+pvar+4], xmm0
0x18008a666  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x18008a66c  mov     dword ptr [rbp+0D0h+pvar+0Ch], eax
0x18008a66f  movzx   eax, word ptr [r8]
0x18008a673  mov     dword ptr [rbp+0D0h+pvar], eax
0x18008a676  mov     r8, [rcx+848h]
0x18008a67d  mov     eax, [r8]
0x18008a680  cmp     eax, 4
0x18008a683  jbe     loc_18008A74F
0x18008a689  mov     edx, 10h
0x18008a68e  mov     rcx, r8
0x18008a691  call    _tlgKeywordOn
0x18008a696  test    al, al
0x18008a698  jz      loc_18008A74F
0x18008a69e  lea     rax, [rbp+0D0h+pvar]
0x18008a6a2  mov     [rbp+0D0h+var_F0], rax
0x18008a6a6  mov     eax, [rsi+8]
0x18008a6a9  mov     [rbp+0D0h+var_138], eax
0x18008a6ac  mov     eax, [rsi+4]
0x18008a6af  mov     [rbp+0D0h+var_134], eax
0x18008a6b2  movzx   eax, word ptr [rsi+2]
0x18008a6b6  mov     [rbp+0D0h+var_140], ax
0x18008a6ba  lea     rax, aWfex; "WFEX"
0x18008a6c1  mov     [rbp+0D0h+var_F8], rax
0x18008a6c5  movzx   eax, word ptr [r9+44h]
0x18008a6ca  mov     [rsp+1D0h+var_15E], ax
0x18008a6cf  lea     rax, [r9+0Ch]
0x18008a6d3  mov     qword ptr [rbp+0D0h+var_128], rax
0x18008a6d7  mov     al, [r9]
0x18008a6da  mov     [rsp+1D0h+var_15F], al
0x18008a6de  mov     rax, [rbx+630h]
0x18008a6e5  mov     rcx, [rax+30h]
0x18008a6e9  mov     [rbp+0D0h+var_148], rcx
0x18008a6ed  lea     rax, [rbp+0D0h+var_F0]
0x18008a6f1  mov     [rsp+1D0h+var_170], rax
0x18008a6f6  lea     rax, [rbp+0D0h+var_138]
0x18008a6fa  mov     [rsp+1D0h+var_178], rax
0x18008a6ff  lea     rax, [rbp+0D0h+var_134]
0x18008a703  mov     [rsp+1D0h+var_180], rax
0x18008a708  lea     rax, [rbp+0D0h+var_140]
0x18008a70c  mov     [rsp+1D0h+var_188], rax
0x18008a711  lea     rax, [rbp+0D0h+var_F8]
0x18008a715  mov     [rsp+1D0h+var_190], rax
0x18008a71a  lea     rax, [rsp+1D0h+var_15E]
0x18008a71f  mov     [rsp+1D0h+var_198], rax
0x18008a724  lea     rax, [rbp+0D0h+var_128]
0x18008a728  mov     [rsp+1D0h+var_1A0], rax; char *
0x18008a72d  lea     rax, [rsp+1D0h+var_15F]
0x18008a732  mov     [rsp+1D0h+var_1A8], rax
0x18008a737  lea     rax, [rbp+0D0h+var_148]
0x18008a73b  mov     [rsp+1D0h+var_1B0], rax
0x18008a740  lea     rdx, unk_1801A99BC
0x18008a747  mov     rcx, r8
0x18008a74a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@U1@U4@U?$_tlgWrapperByVal@$03@@U5@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@36AEBU?$_tlgWrapperByVal@$03@@75@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008a74f  mov     rax, [rbx+630h]
0x18008a756  cmp     [rax+0ECh], r13d
0x18008a75d  jz      loc_18008A941
0x18008a763  cmp     [r14], r13d
0x18008a766  setnz   al
0x18008a769  mov     rcx, [rbp+0D8h]; this
0x18008a770  lea     rdx, aCannotEnableSp; "Cannot enable spatial audio on a non-re"...
0x18008a777  mov     [rsp+1D0h+var_1A8], rdx; bool
0x18008a77c  mov     byte ptr [rsp+1D0h+var_1B0], al; int
0x18008a780  mov     r9d, 80070032h; char *
0x18008a786  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18008a78d  mov     edx, 22B4h; void *
0x18008a792  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18008a797  mov     r14, r13
0x18008a79a  jmp     loc_18008A941
0x18008a79f  cmp     [r8], ax
0x18008a7a3  jnz     short loc_18008A7B1
0x18008a7a5  movups  xmm0, xmmword ptr [r8+18h]
0x18008a7aa  movdqu  xmmword ptr [rbp+0D0h+pvar], xmm0
0x18008a7af  jmp     short loc_18008A7CE
0x18008a7b1  movsd   xmm0, qword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data2
0x18008a7b9  movsd   [rbp+0D0h+pvar+4], xmm0
0x18008a7be  mov     eax, dword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data4+4
0x18008a7c4  mov     dword ptr [rbp+0D0h+pvar+0Ch], eax
0x18008a7c7  movzx   eax, word ptr [r8]
0x18008a7cb  mov     dword ptr [rbp+0D0h+pvar], eax
0x18008a7ce  mov     r8, [rcx+848h]
0x18008a7d5  mov     eax, [r8]
0x18008a7d8  cmp     eax, 4
0x18008a7db  jbe     loc_18008A941
0x18008a7e1  mov     edx, 10h
0x18008a7e6  mov     rcx, r8
0x18008a7e9  call    _tlgKeywordOn
0x18008a7ee  test    al, al
0x18008a7f0  jz      loc_18008A941
0x18008a7f6  lea     rax, [rbp+0D0h+pvar]
0x18008a7fa  mov     [rbp+0D0h+var_148], rax
0x18008a7fe  mov     eax, [rsi+8]
0x18008a801  mov     [rbp+0D0h+var_134], eax
0x18008a804  mov     eax, [rsi+4]
0x18008a807  mov     [rbp+0D0h+var_138], eax
0x18008a80a  movzx   eax, word ptr [rsi+2]
0x18008a80e  mov     [rsp+1D0h+var_15E], ax
0x18008a813  lea     rax, aWfex; "WFEX"
0x18008a81a  mov     qword ptr [rbp+0D0h+var_128], rax
0x18008a81e  mov     rax, [rbx+630h]
0x18008a825  mov     rdx, [rax+30h]
0x18008a829  mov     [rbp+0D0h+var_F8], rdx
0x18008a82d  lea     rax, [rbp+0D0h+var_148]
0x18008a831  mov     [rsp+1D0h+var_188], rax
0x18008a836  lea     rax, [rbp+0D0h+var_134]
0x18008a83a  mov     [rsp+1D0h+var_190], rax
0x18008a83f  lea     rax, [rbp+0D0h+var_138]
0x18008a843  mov     [rsp+1D0h+var_198], rax
0x18008a848  lea     rax, [rsp+1D0h+var_15E]
0x18008a84d  mov     [rsp+1D0h+var_1A0], rax
0x18008a852  lea     rax, [rbp+0D0h+var_128]
0x18008a856  mov     [rsp+1D0h+var_1A8], rax
0x18008a85b  lea     rax, [rbp+0D0h+var_F8]
0x18008a85f  mov     [rsp+1D0h+var_1B0], rax
0x18008a864  lea     rdx, unk_1801A9812
0x18008a86b  mov     rcx, r8
0x18008a86e  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008a873  jmp     loc_18008A941
0x18008a878  mov     r8, [rcx+848h]
0x18008a87f  mov     eax, [r8]
0x18008a882  test    r14, r14
0x18008a885  jz      short loc_18008A904
0x18008a887  cmp     eax, 4
0x18008a88a  jbe     loc_18008A941
0x18008a890  mov     edx, 10h
0x18008a895  mov     rcx, r8
0x18008a898  call    _tlgKeywordOn
0x18008a89d  test    al, al
0x18008a89f  jz      loc_18008A941
0x18008a8a5  movzx   eax, word ptr [r9+44h]
0x18008a8aa  mov     [rsp+1D0h+var_15E], ax
0x18008a8af  lea     rax, [r9+0Ch]
0x18008a8b3  mov     [rbp+0D0h+var_148], rax
0x18008a8b7  mov     al, [r9]
0x18008a8ba  mov     [rsp+1D0h+var_15F], al
0x18008a8be  mov     rax, [rbx+630h]
0x18008a8c5  mov     rdx, [rax+30h]
0x18008a8c9  mov     qword ptr [rbp+0D0h+var_128], rdx
0x18008a8cd  lea     rax, [rsp+1D0h+var_15E]
0x18008a8d2  mov     [rsp+1D0h+var_198], rax
0x18008a8d7  lea     rax, [rbp+0D0h+var_148]
0x18008a8db  mov     [rsp+1D0h+var_1A0], rax
0x18008a8e0  lea     rax, [rsp+1D0h+var_15F]
0x18008a8e5  mov     [rsp+1D0h+var_1A8], rax
0x18008a8ea  lea     rax, [rbp+0D0h+var_128]
0x18008a8ee  mov     [rsp+1D0h+var_1B0], rax
0x18008a8f3  lea     rdx, unk_1801A98DB
0x18008a8fa  mov     rcx, r8
0x18008a8fd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &)
0x18008a902  jmp     short loc_18008A941
0x18008a904  cmp     eax, 4
0x18008a907  jbe     short loc_18008A941
0x18008a909  mov     edx, 10h
0x18008a90e  mov     rcx, r8
0x18008a911  call    _tlgKeywordOn
0x18008a916  test    al, al
0x18008a918  jz      short loc_18008A941
0x18008a91a  mov     rax, [rbx+630h]
0x18008a921  mov     rdx, [rax+30h]
0x18008a925  mov     [rbp+0D0h+var_148], rdx
0x18008a929  lea     rax, [rbp+0D0h+var_148]
0x18008a92d  mov     [rsp+1D0h+var_1B0], rax
0x18008a932  lea     rdx, unk_1801A97D1
0x18008a939  mov     rcx, r8
0x18008a93c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18008a941  mov     rcx, cs:?g_policyConfigInternal@@3V?$com_ptr_t@UIPolicyConfigInternal@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IPolicyConfigInternal,wil::err_returncode_policy> g_policyConfigInternal
0x18008a948  mov     rax, [rcx]
0x18008a94b  mov     r8, [rbx+630h]
0x18008a952  mov     r8, [r8+30h]
0x18008a956  lea     rdx, [rbp+0D0h+lpCriticalSection]
0x18008a95a  mov     rax, [rax+18h]
0x18008a95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a963  nop
0x18008a964  mov     rdi, [rbx+630h]
0x18008a96b  add     rdi, 2000h
0x18008a972  mov     rcx, rdi; lpCriticalSection
0x18008a975  call    cs:__imp_EnterCriticalSection
0x18008a97b  mov     [rbp+0D0h+var_148], rdi
0x18008a97f  mov     [rsp+1D0h+var_158], r13
0x18008a984  mov     [rbp+0D0h+pv], r13
0x18008a988  lea     rax, [rbp+0D0h+pv]
0x18008a98c  mov     [rbp+0D0h+var_120], rax
0x18008a990  mov     [rbp+0D0h+var_118], r13
0x18008a994  mov     byte ptr [rbp+0D0h+var_110], 1
0x18008a998  lea     rax, [rsp+1D0h+var_158]
0x18008a99d  mov     [rbp+0D0h+pvar], rax
0x18008a9a1  mov     [rbp+0D0h+pvar+8], r13
0x18008a9a5  mov     byte ptr [rbp+0D0h+var_D8], 1
0x18008a9a9  mov     [rsp+1D0h+var_1A0], r13; pv
0x18008a9ae  mov     [rsp+1D0h+var_1A8], r13; unsigned int *
0x18008a9b3  lea     rax, [rbp+0D0h+var_118]
0x18008a9b7  mov     [rsp+1D0h+var_1B0], rax; int
0x18008a9bc  lea     r9, [rbp+0D0h+pvar+8]; struct tWAVEFORMATEX **
0x18008a9c0  xor     r8d, r8d; int
0x18008a9c3  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18008a9c5  mov     rcx, rbx; this
0x18008a9c8  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x18008a9cd  mov     r15d, eax
0x18008a9d0  lea     rcx, [rbp+0D0h+pvar]
0x18008a9d4  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18008a9d9  nop
0x18008a9da  lea     rcx, [rbp+0D0h+var_120]
0x18008a9de  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18008a9e3  test    r15d, r15d
0x18008a9e6  jns     short loc_18008AA54
0x18008a9e8  mov     rcx, [rbp+0D8h]; this
0x18008a9ef  mov     r9d, r15d; char *
0x18008a9f2  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18008a9f9  mov     edx, 22E7h; void *
0x18008a9fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008aa03  nop
0x18008aa04  mov     rcx, [rbp+0D0h+pv]; pv
0x18008aa08  test    rcx, rcx
0x18008aa0b  mov     [rbp+0D0h+pv], r13
0x18008aa0f  jz      short loc_18008AA18
0x18008aa11  call    cs:__imp_CoTaskMemFree
0x18008aa17  nop
0x18008aa18  mov     rcx, [rsp+1D0h+var_158]; pv
0x18008aa1d  mov     [rsp+1D0h+var_158], r13
0x18008aa22  test    rcx, rcx
0x18008aa25  jz      short loc_18008AA2E
0x18008aa27  call    cs:__imp_CoTaskMemFree
0x18008aa2d  nop
0x18008aa2e  test    rdi, rdi
0x18008aa31  jz      short loc_18008AA3D
0x18008aa33  mov     rcx, rdi; lpCriticalSection
0x18008aa36  call    cs:__imp_LeaveCriticalSection
0x18008aa3c  nop
0x18008aa3d  mov     rcx, [rbp+0D0h+lpCriticalSection]; lpCriticalSection
0x18008aa41  test    rcx, rcx
0x18008aa44  jz      short loc_18008AA4C
0x18008aa46  call    cs:__imp_LeaveCriticalSection
0x18008aa4c  mov     eax, r15d
0x18008aa4f  jmp     loc_18008AE7C
0x18008aa54  mov     [rbp+0D0h+var_13C], r13d
0x18008aa58  xorps   xmm0, xmm0
0x18008aa5b  xor     eax, eax
0x18008aa5d  movups  xmmword ptr [rbp+0D0h+pvar], xmm0
0x18008aa61  mov     [rbp+0D0h+var_D8], rax
0x18008aa65  mov     rax, [rbx+630h]
0x18008aa6c  mov     rcx, [rax+48h]
0x18008aa70  mov     rax, [rcx]
0x18008aa73  lea     r8, [rbp+0D0h+pvar]
0x18008aa77  lea     rdx, PKEY_Endpoint_HWAudioEngine_Present
0x18008aa7e  mov     rax, [rax+28h]
0x18008aa82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aa87  test    eax, eax
0x18008aa89  js      short loc_18008AA9E
0x18008aa8b  cmp     word ptr [rbp+0D0h+pvar], 0Bh
0x18008aa90  jnz     short loc_18008AA9E
0x18008aa92  cmp     word ptr [rbp+0D0h+pvar+8], r13w
0x18008aa97  mov     eax, 1
0x18008aa9c  jnz     short loc_18008AAA1
0x18008aa9e  mov     eax, r13d
0x18008aaa1  mov     [rbp+0D0h+var_13C], eax
0x18008aaa4  lea     rcx, [rbp+0D0h+pvar]; pvar
0x18008aaa8  call    cs:__imp_PropVariantClear
0x18008aaae  mov     [rbp+0D0h+var_120], rbx
0x18008aab2  lea     rax, [rbp+0D0h+pv]
0x18008aab6  mov     [rbp+0D0h+var_118], rax
0x18008aaba  lea     rax, [rsp+1D0h+var_158]
0x18008aabf  mov     [rbp+0D0h+var_110], rax
0x18008aac3  lea     rax, [rbp+0D0h+var_13C]
0x18008aac7  mov     [rbp+0D0h+var_108], rax
0x18008aacb  mov     [rbp+0D0h+var_100], 1
0x18008aacf  mov     [rbp+0D0h+pvar], rbx
0x18008aad3  mov     byte ptr [rbp+0D0h+pvar+8], 1
0x18008aad7  xorps   xmm0, xmm0
0x18008aada  xor     eax, eax
0x18008aadc  movups  xmmword ptr [rbp+0D0h+var_D0.Format.wFormatTag], xmm0
0x18008aae0  movups  xmmword ptr [rbp+0D0h+var_D0.Format.cbSize], xmm0
  ... truncated ...
```
