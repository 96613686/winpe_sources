# CSpatialProperties::ProcessPropertyChange(EffectPack *,_tagpropertykey const &,SpatialAudioRelatedGlobalSettings *,tWAVEFORMATEX const *,int *)

- ea: `0x18008b9c8`
- end: `0x18008c423`
- name: `?ProcessPropertyChange@CSpatialProperties@@QEAAXPEAVEffectPack@@AEBU_tagpropertykey@@PEAUSpatialAudioRelatedGlobalSettings@@PEBUtWAVEFORMATEX@@PEAH@Z`
- size: `2651`
- prototype: `void __usercall(LPCRITICAL_SECTION lpCriticalSection@<rcx>, struct EffectPack *this@<rdx>, const struct _tagpropertykey *@<r8>, struct SpatialAudioRelatedGlobalSettings *@<r9>, const struct tWAVEFORMATEX *, int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024d94`

## callees

- `0x180006cb0`
- `0x180006d74`
- `0x180006e24`
- `0x180006fb4`
- `0x180007128`
- `0x1800075c4`
- `0x180020160`
- `0x1800461b4`
- `0x1800622f4`
- `0x18006302c`
- `0x18006e310`
- `0x180073310`
- `0x18008a5f4`
- `0x18008b9c8`
- `0x18008c42c`
- `0x1800b45b0`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x1800d0740`
- `0x1801495b0`
- `0x18014a4c0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008bb2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008befc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008bb2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008befc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c196`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008bb82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008bf66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c240`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c3e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008bb82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008bf66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c240`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c3e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008c3f1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008c3f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bd84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c12f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bd84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c12f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c292`

## string_xrefs

- `0x18008ba47`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSpatialProperties::ProcessPropertyChange(
        LPCRITICAL_SECTION lpCriticalSection,
        struct EffectPack *this,
        const struct _tagpropertykey *a3,
        struct SpatialAudioRelatedGlobalSettings *a4,
        struct tWAVEFORMATEX *a5,
        int *a6)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r15
  char v10; // al
  struct tWAVEFORMATEX *v11; // r15
  int v12; // r8d
  int v13; // r9d
  __m128i v14; // xmm6
  LONG RecursionCount; // esi
  int DeviceFormatAndSpatialSettings; // eax
  struct tWAVEFORMATEX *v17; // rdi
  void *v18; // rsi
  BOOL v19; // r10d
  int v20; // r8d
  int v21; // r9d
  int v22; // r8d
  int v23; // r9d
  int v24; // r8d
  int v25; // r9d
  int OwningThread; // edi
  BOOL v27; // eax
  int v28; // r8d
  int v29; // r9d
  int v30; // eax
  struct tWAVEFORMATEX *v31; // rcx
  struct tWAVEFORMATEX *v32; // rsi
  int v33; // eax
  struct tWAVEFORMATEX *v34; // rdi
  int v35; // r8d
  int v36; // r9d
  __int16 v37; // di
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // r8
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  struct _RTL_CRITICAL_SECTION *v46; // rcx
  int v47; // eax
  struct tWAVEFORMATEX *v48; // r9
  struct tWAVEFORMATEX *v49; // rsi
  int v50; // r8d
  int v51; // r9d
  _DWORD *v52; // r8
  int v53; // r9d
  int v54; // r8d
  int v55; // r9d
  int v56; // [rsp+20h] [rbp-F0h]
  _WORD v57[2]; // [rsp+90h] [rbp-80h] BYREF
  LONG v58; // [rsp+94h] [rbp-7Ch] BYREF
  __int16 v59; // [rsp+98h] [rbp-78h] BYREF
  struct tWAVEFORMATEX *v60; // [rsp+A0h] [rbp-70h] BYREF
  __int16 v61; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-60h] BYREF
  int v63; // [rsp+B8h] [rbp-58h] BYREF
  DWORD SpatialRendererSelectionMode; // [rsp+BCh] [rbp-54h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-50h] BYREF
  struct tWAVEFORMATEX *p_Buf1; // [rsp+C8h] [rbp-48h] BYREF
  __int128 Buf2; // [rsp+D0h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+E0h] [rbp-30h] BYREF
  __int64 v69; // [rsp+F0h] [rbp-20h]
  _BYTE *v70; // [rsp+F8h] [rbp-18h] BYREF
  __int128 Buf1; // [rsp+100h] [rbp-10h] BYREF
  int v72; // [rsp+11Ch] [rbp+Ch]
  _WORD v73[2]; // [rsp+120h] [rbp+10h] BYREF
  int v74; // [rsp+124h] [rbp+14h]
  __int16 v75; // [rsp+128h] [rbp+18h]
  __int16 v76; // [rsp+12Ah] [rbp+1Ah]
  _BYTE v77[16]; // [rsp+12Ch] [rbp+1Ch] BYREF
  DWORD v78; // [rsp+13Ch] [rbp+2Ch]
  WAVEFORMATEXTENSIBLE v79; // [rsp+140h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+A8h]

  *(_OWORD *)pvar = 0;
  v69 = 0;
  *a6 = 0;
  DebugInfo = lpCriticalSection[1].DebugInfo;
  if ( !DebugInfo || (v10 = 0, !lpCriticalSection[1].LockSemaphore) )
    v10 = 1;
  if ( v10 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7AA,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
      (const char *)0x8000FFFFLL,
      v56);
    goto LABEL_102;
  }
  if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_SpatialAudio_Signaling_Key.fmtid.Data1
    && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_SpatialAudio_Signaling_Key.fmtid.Data4
    && a3->pid == 2 )
  {
    v11 = *(struct tWAVEFORMATEX **)&DebugInfo[1].Type;
    if ( (*(int (__fastcall **)(HANDLE, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)lpCriticalSection[1].OwningThread
                                                                                      + 40LL))(
           lpCriticalSection[1].OwningThread,
           &PKEY_SpatialAudio_Signaling_Key,
           pvar) >= 0 )
    {
      v57[0] = pvar[1];
      if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u )
      {
        if ( (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
        {
          v58 = LOWORD(pvar[0]);
          LOBYTE(v59) = HIBYTE(v57[0]);
          LOBYTE(v57[0]) = v12;
          v60 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)&unk_1801AB913,
            v12,
            v13,
            (__int64)&v60,
            (__int64)v57,
            (__int64)&v59,
            (__int64)&v58);
        }
      }
    }
    memset(&v79, 0, sizeof(v79));
    EnterCriticalSection(lpCriticalSection);
    if ( !LODWORD(lpCriticalSection[192].OwningThread) )
    {
      LODWORD(lpCriticalSection[192].OwningThread) = 1;
      v14 = *(__m128i *)&lpCriticalSection[192].DebugInfo;
      Buf2 = *(_OWORD *)((char *)&lpCriticalSection[2].LockSemaphore + 4);
      LODWORD(v60) = lpCriticalSection[2].OwningThread;
      RecursionCount = lpCriticalSection[2].RecursionCount;
      v58 = RecursionCount;
      SpatialRendererSelectionMode = GetSpatialRendererSelectionMode(CSpatialProperties::s_exclusiveModeListener);
      BYTE2(lpCriticalSection[2].LockCount) = *(_BYTE *)a4 != 0;
      LeaveCriticalSection(lpCriticalSection);
      CSpatialProperties::SetSpatialAudioSettingsInternal((CSpatialProperties *)lpCriticalSection, this, 1, a5, &v79);
      if ( HIDWORD(lpCriticalSection[192].OwningThread) == 1 )
      {
        pv = 0;
        DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                           (CEndpointCharacteristics **)this,
                                           eHostProcessConnector,
                                           0,
                                           (struct tWAVEFORMATEX **)&pv,
                                           0,
                                           0,
                                           0);
        v17 = a5;
        v18 = pv;
        if ( DeviceFormatAndSpatialSettings >= 0 )
          v17 = (struct tWAVEFORMATEX *)pv;
        if ( CSpatialProperties::SetDesiredFormat(
               lpCriticalSection,
               this,
               (const struct WAVEFORMATEXTENSIBLE *)&lpCriticalSection[192].LockSemaphore,
               0) )
        {
          if ( !v79.Format.wFormatTag )
          {
            AudioFormatForLogging::AudioFormatForLogging((AudioFormatForLogging *)&Buf1, v17);
            HIDWORD(lpCriticalSection[192].OwningThread) = 3;
            if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
              && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, (unsigned int)(v19 + 16)) )
            {
              v57[0] = WORD5(Buf1);
              v59 = WORD4(Buf1);
              pv = (char *)&Buf1 + 12;
              LODWORD(v62) = DWORD1(Buf1);
              v63 = v72;
              v61 = Buf1;
              p_Buf1 = v11;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
                v21,
                (unsigned int)&unk_1801AB737,
                v20,
                v21,
                (__int64)&p_Buf1,
                (__int64)&v61,
                (__int64)&v63,
                (__int64)&v62,
                (__int64)&pv,
                (__int64)&v59,
                (__int64)v57);
              LOBYTE(v19) = 0;
            }
            EffectPack::SetDeviceFormatAndSpatialSettings(this, eHostProcessConnector, v17, 0, v19);
          }
        }
        else
        {
          if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 2u
            && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 0x400000000010LL) )
          {
            pv = v11;
            Buf1 = *(_OWORD *)*((_QWORD *)this + 196);
            p_Buf1 = (struct tWAVEFORMATEX *)&Buf1;
            v62 = 2048;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
              v22,
              (unsigned int)&unk_1801AB6DB,
              v22,
              v23,
              (__int64)&v62,
              (__int64)&p_Buf1,
              (__int64)&pv);
          }
          HIDWORD(lpCriticalSection[192].OwningThread) = 2;
          CSpatialProperties::SetSpatialAudioSettingsInternal(
            (CSpatialProperties *)lpCriticalSection,
            this,
            1,
            a5,
            &v79);
        }
        if ( v18 )
          CoTaskMemFree(v18);
        RecursionCount = v58;
      }
      if ( v79.Format.wFormatTag )
      {
        if ( !CSpatialProperties::SetDesiredFormat(lpCriticalSection, this, &v79, 1) && a5 )
        {
          AudioFormatForLogging::AudioFormatForLogging((AudioFormatForLogging *)v73, a5);
          if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 2u
            && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
          {
            v70 = v77;
            LODWORD(p_Buf1) = v78;
            v61 = v76;
            v57[0] = v75;
            LODWORD(pv) = v74;
            v59 = v73[0];
            *(_QWORD *)&Buf2 = &v79.SubFormat;
            SpatialRendererSelectionMode = v79.dwChannelMask;
            LOWORD(v63) = v79.Samples.wValidBitsPerSample;
            LOWORD(v62) = v79.Format.wBitsPerSample;
            LODWORD(v60) = v79.Format.nSamplesPerSec;
            LOWORD(v58) = v79.Format.nChannels;
            *(_QWORD *)&Buf1 = v11;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              v24,
              (unsigned int)&unk_1801AB7DF,
              v24,
              v25,
              (__int64)&Buf1,
              (__int64)&v58,
              (__int64)&v60,
              (__int64)&v62,
              (__int64)&v63,
              (__int64)&SpatialRendererSelectionMode,
              (__int64)&Buf2,
              (__int64)&v59,
              (__int64)&pv,
              (__int64)v57,
              (__int64)&v61,
              (__int64)&p_Buf1,
              (__int64)&v70);
          }
          CSpatialProperties::SetSpatialAudioSettingsInternal(
            (CSpatialProperties *)lpCriticalSection,
            this,
            0,
            a5,
            &v79);
        }
      }
      else
      {
        EnterCriticalSection(lpCriticalSection);
        Buf1 = *(_OWORD *)((char *)&lpCriticalSection[2].LockSemaphore + 4);
        OwningThread = (int)lpCriticalSection[2].OwningThread;
        v27 = *(_QWORD *)&lpCriticalSection[2].RecursionCount != __PAIR64__((unsigned int)v60, RecursionCount)
           || OwningThread && memcmp_0(&Buf1, &Buf2, 0x10u)
           || (PRTL_CRITICAL_SECTION_DEBUG)v14.m128i_i64[0] != lpCriticalSection[192].DebugInfo
           || _mm_srli_si128(v14, 8).m128i_u64[0] != *(_QWORD *)&lpCriticalSection[192].LockCount;
        *a6 = v27;
        LeaveCriticalSection(lpCriticalSection);
        if ( *a6
          && **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
        {
          *(_QWORD *)&Buf1 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v28,
            (unsigned int)&unk_1801AB7B3,
            v28,
            v29,
            (__int64)&Buf1);
        }
        if ( !HIBYTE(lpCriticalSection[2].LockCount) )
        {
          v60 = 0;
          v30 = EffectPack::GetDeviceFormatAndSpatialSettings(
                  (CEndpointCharacteristics **)this,
                  eHostProcessConnector,
                  0,
                  &v60,
                  0,
                  0,
                  0);
          v31 = a5;
          v32 = v60;
          if ( v30 >= 0 )
            v31 = v60;
          if ( !OwningThread
            && !SpatialRendererSelectionMode
            && v31
            && v31->wFormatTag == 0xFFFE
            && (unsigned __int8)IsSpatialOnlyFormat((char *)&v31[1].nSamplesPerSec + 2) )
          {
            v60 = 0;
            v33 = EffectPack::GetDeviceFormatAndSpatialSettings(
                    (CEndpointCharacteristics **)this,
                    eHostProcessConnector,
                    1,
                    &v60,
                    0,
                    0,
                    0);
            v34 = v60;
            if ( v33 >= 0 )
            {
              AudioFormatForLogging::AudioFormatForLogging((AudioFormatForLogging *)v73, v60);
              if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
                && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
              {
                LOWORD(v58) = v76;
                LOWORD(v62) = v75;
                *(_QWORD *)&Buf1 = v77;
                LODWORD(v60) = v74;
                SpatialRendererSelectionMode = v78;
                LOWORD(v63) = v73[0];
                *(_QWORD *)&Buf2 = v11;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
                  v35,
                  (unsigned int)&unk_1801AB5AC,
                  v35,
                  v36,
                  (__int64)&Buf2,
                  (__int64)&v63,
                  (__int64)&SpatialRendererSelectionMode,
                  (__int64)&v60,
                  (__int64)&Buf1,
                  (__int64)&v62,
                  (__int64)&v58);
              }
              EffectPack::SetDeviceFormatAndSpatialSettings(this, eHostProcessConnector, v34, 0, 0);
            }
            if ( v34 )
              CoTaskMemFree(v34);
          }
          if ( v32 )
            CoTaskMemFree(v32);
        }
      }
      v37 = 0;
      while ( 1 )
      {
        v60 = 0;
        if ( v37 == 3
          && **(_DWORD **)&lpCriticalSection[1].LockCount > 2u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
        {
          LOWORD(v58) = lpCriticalSection[192].OwningThread;
          *(_QWORD *)&Buf1 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>>(
            v38,
            (unsigned int)&unk_1801AB559,
            v38,
            v39,
            (__int64)&Buf1,
            (__int64)&v58);
        }
        EnterCriticalSection(lpCriticalSection);
        *(_QWORD *)&Buf2 = lpCriticalSection;
        v41 = (int)lpCriticalSection[192].OwningThread;
        if ( !v41 )
          goto LABEL_76;
        v42 = v41 - 1;
        if ( v42 )
          break;
LABEL_79:
        LODWORD(lpCriticalSection[192].OwningThread) = 0;
LABEL_80:
        v46 = lpCriticalSection;
        if ( !LODWORD(lpCriticalSection[192].OwningThread) )
          goto LABEL_101;
        LeaveCriticalSection(lpCriticalSection);
        v47 = EffectPack::GetDeviceFormatAndSpatialSettings(
                (CEndpointCharacteristics **)this,
                eHostProcessConnector,
                0,
                &v60,
                0,
                0,
                0);
        v48 = a5;
        v49 = v60;
        if ( v47 >= 0 )
          v48 = v60;
        CSpatialProperties::SetSpatialAudioSettingsInternal((CSpatialProperties *)lpCriticalSection, this, 0, v48, &v79);
        if ( v49 )
          CoTaskMemFree(v49);
        if ( (unsigned __int16)++v37 >= 5u )
          goto LABEL_102;
      }
      v43 = v42 - 1;
      if ( !v43 )
      {
        v52 = *(_DWORD **)&lpCriticalSection[1].LockCount;
        if ( *v52 > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
        {
          LOWORD(v58) = lpCriticalSection[192].OwningThread;
          LOWORD(v62) = v37;
          *(_QWORD *)&Buf1 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
            (_DWORD)v52,
            (unsigned int)&unk_1801AB61F,
            (_DWORD)v52,
            v53,
            (__int64)&Buf1,
            (__int64)&v62,
            (__int64)&v58);
        }
        LODWORD(lpCriticalSection[192].OwningThread) = 0;
        LOBYTE(v52) = 4;
        CSpatialProperties::SignalSpatialRelatedChange(
          *(_QWORD *)&lpCriticalSection[1].LockCount,
          lpCriticalSection[1].OwningThread,
          v52);
        goto LABEL_80;
      }
      if ( v43 == 1 )
      {
        if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
        {
          LOWORD(v58) = lpCriticalSection[192].OwningThread;
          LOWORD(v62) = v37;
          *(_QWORD *)&Buf1 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
            v50,
            (unsigned int)&unk_1801AB67D,
            v50,
            v51,
            (__int64)&Buf1,
            (__int64)&v62,
            (__int64)&v58);
        }
        LODWORD(lpCriticalSection[192].OwningThread) = 1;
        goto LABEL_80;
      }
      LOBYTE(v40) = 5;
      CSpatialProperties::SignalSpatialRelatedChange(
        *(_QWORD *)&lpCriticalSection[1].LockCount,
        lpCriticalSection[1].OwningThread,
        v40);
LABEL_76:
      if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 2u
        && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
      {
        LOWORD(v58) = lpCriticalSection[192].OwningThread;
        LOWORD(v62) = v37;
        *(_QWORD *)&Buf1 = v11;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
          v44,
          (unsigned int)&unk_1801AB4B1,
          v44,
          v45,
          (__int64)&Buf1,
          (__int64)&v62,
          (__int64)&v58);
      }
      goto LABEL_79;
    }
    if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
      && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
    {
      LOBYTE(v57[0]) = lpCriticalSection[192].OwningThread;
      *(_QWORD *)&Buf1 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        v54,
        (unsigned int)&unk_1801AB8C3,
        v54,
        v55,
        (__int64)&Buf1,
        (__int64)v57);
    }
    if ( LODWORD(lpCriticalSection[192].OwningThread) == 1 )
      LODWORD(lpCriticalSection[192].OwningThread) = 2;
    v46 = lpCriticalSection;
LABEL_101:
    LeaveCriticalSection(v46);
  }
LABEL_102:
  PropVariantClear(pvar);
}

```

## disassembly

```asm
0x18008b9c8  mov     rax, rsp
0x18008b9cb  mov     [rax+18h], rbx
0x18008b9cf  push    rbp
0x18008b9d0  push    rsi
0x18008b9d1  push    rdi
0x18008b9d2  push    r12
0x18008b9d4  push    r13
0x18008b9d6  push    r14
0x18008b9d8  push    r15
0x18008b9da  lea     rbp, [rsp-70h]
0x18008b9df  sub     rsp, 180h
0x18008b9e6  movaps  xmmword ptr [rax-48h], xmm6
0x18008b9ea  mov     rax, cs:__security_cookie
0x18008b9f1  xor     rax, rsp
0x18008b9f4  mov     [rbp+0A0h+var_48], rax
0x18008b9f8  mov     rdi, r9
0x18008b9fb  mov     r14, rdx
0x18008b9fe  mov     rbx, rcx
0x18008ba01  mov     r13, [rbp+0A0h+arg_20]
0x18008ba08  mov     r12, [rbp+0A0h+arg_28]
0x18008ba0f  xorps   xmm0, xmm0
0x18008ba12  xor     eax, eax
0x18008ba14  movups  xmmword ptr [rbp+0A0h+pvar], xmm0
0x18008ba18  mov     [rbp+0A0h+var_C0], rax
0x18008ba1c  xor     esi, esi
0x18008ba1e  mov     [r12], esi
0x18008ba22  mov     r15, [rcx+28h]
0x18008ba26  test    r15, r15
0x18008ba29  jz      short loc_18008BA34
0x18008ba2b  cmp     [rcx+40h], rsi
0x18008ba2f  mov     al, sil
0x18008ba32  jnz     short loc_18008BA36
0x18008ba34  mov     al, 1
0x18008ba36  mov     rcx, [rbp+0A8h]; this
0x18008ba3d  test    al, al
0x18008ba3f  jz      short loc_18008BA5D
0x18008ba41  mov     r9d, 8000FFFFh; char *
0x18008ba47  lea     r8, aAvcoreAudiocor_65; "avcore\\audiocore\\server\\lib\\audiose"...
0x18008ba4e  mov     edx, 7AAh; void *
0x18008ba53  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008ba58  jmp     loc_18008C3ED
0x18008ba5d  mov     rax, [r8]
0x18008ba60  cmp     rax, qword ptr cs:PKEY_SpatialAudio_Signaling_Key.fmtid.Data1
0x18008ba67  jnz     loc_18008C3ED
0x18008ba6d  mov     rax, [r8+8]
0x18008ba71  cmp     rax, qword ptr cs:PKEY_SpatialAudio_Signaling_Key.fmtid.Data4
0x18008ba78  jnz     loc_18008C3ED
0x18008ba7e  cmp     dword ptr [r8+10h], 2
0x18008ba83  jnz     loc_18008C3ED
0x18008ba89  mov     r15, [r15+30h]
0x18008ba8d  mov     rcx, [rbx+38h]
0x18008ba91  mov     rax, [rcx]
0x18008ba94  lea     r8, [rbp+0A0h+pvar]
0x18008ba98  lea     rdx, PKEY_SpatialAudio_Signaling_Key
0x18008ba9f  mov     rax, [rax+28h]
0x18008baa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008baa8  test    eax, eax
0x18008baaa  js      short loc_18008BB1B
0x18008baac  movzx   r8d, word ptr [rbp+0A0h+pvar+8]
0x18008bab1  mov     [rbp+0A0h+var_120], r8w
0x18008bab6  mov     r9, [rbx+30h]
0x18008baba  mov     eax, [r9]
0x18008babd  cmp     eax, 4
0x18008bac0  jbe     short loc_18008BB1B
0x18008bac2  mov     edx, 10h
0x18008bac7  mov     rcx, r9
0x18008baca  call    _tlgKeywordOn
0x18008bacf  test    al, al
0x18008bad1  jz      short loc_18008BB1B
0x18008bad3  movzx   eax, word ptr [rbp+0A0h+pvar]
0x18008bad7  mov     [rbp+0A0h+var_11C], eax
0x18008bada  mov     al, byte ptr [rbp+0A0h+var_120+1]
0x18008badd  mov     byte ptr [rbp+0A0h+var_118], al
0x18008bae0  mov     byte ptr [rbp+0A0h+var_120], r8b
0x18008bae4  mov     [rbp+0A0h+var_110], r15
0x18008bae8  lea     rax, [rbp+0A0h+var_11C]
0x18008baec  mov     [rsp+1B0h+var_178], rax
0x18008baf1  lea     rax, [rbp+0A0h+var_118]
0x18008baf5  mov     [rsp+1B0h+var_180], rax
0x18008bafa  lea     rax, [rbp+0A0h+var_120]
0x18008bafe  mov     [rsp+1B0h+var_188], rax
0x18008bb03  lea     rax, [rbp+0A0h+var_110]
0x18008bb07  mov     [rsp+1B0h+var_190], rax
0x18008bb0c  lea     rdx, unk_1801AB913
0x18008bb13  mov     rcx, r9
0x18008bb16  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18008bb1b  xorps   xmm0, xmm0
0x18008bb1e  xor     eax, eax
0x18008bb20  movups  xmmword ptr [rbp+0A0h+var_70.Format.wFormatTag], xmm0
0x18008bb24  movups  xmmword ptr [rbp+0A0h+var_70.Format.cbSize], xmm0
0x18008bb28  mov     qword ptr [rbp+0A0h+var_70.SubFormat.Data4], rax
0x18008bb2c  mov     rcx, rbx; lpCriticalSection
0x18008bb2f  call    cs:__imp_EnterCriticalSection
0x18008bb35  cmp     [rbx+1E10h], esi
0x18008bb3b  jnz     loc_18008C385
0x18008bb41  mov     dword ptr [rbx+1E10h], 1
0x18008bb4b  movups  xmm6, xmmword ptr [rbx+1E00h]
0x18008bb52  movups  xmm0, xmmword ptr [rbx+6Ch]
0x18008bb56  movdqu  [rbp+0A0h+Buf2], xmm0
0x18008bb5b  mov     eax, [rbx+60h]
0x18008bb5e  mov     dword ptr [rbp+0A0h+var_110], eax
0x18008bb61  mov     esi, [rbx+5Ch]
0x18008bb64  mov     [rbp+0A0h+var_11C], esi
0x18008bb67  mov     rcx, cs:?s_exclusiveModeListener@CSpatialProperties@@0V?$com_ptr_t@VCExclusiveModeListener@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<CExclusiveModeListener,wil::err_returncode_policy> CSpatialProperties::s_exclusiveModeListener
0x18008bb6e  call    GetSpatialRendererSelectionMode
0x18008bb73  mov     [rbp+0A0h+var_F4], eax
0x18008bb76  cmp     byte ptr [rdi], 0
0x18008bb79  setnz   cl
0x18008bb7c  mov     [rbx+5Ah], cl
0x18008bb7f  mov     rcx, rbx; lpCriticalSection
0x18008bb82  call    cs:__imp_LeaveCriticalSection
0x18008bb88  lea     rax, [rbp+0A0h+var_70]
0x18008bb8c  mov     [rsp+1B0h+var_190], rax; struct WAVEFORMATEXTENSIBLE *
0x18008bb91  mov     r9, r13; struct tWAVEFORMATEX *
0x18008bb94  mov     r8b, 1; bool
0x18008bb97  mov     rdx, r14; struct EffectPack *
0x18008bb9a  mov     rcx, rbx; this
0x18008bb9d  call    ?SetSpatialAudioSettingsInternal@CSpatialProperties@@AEAAJPEAVEffectPack@@_NPEBUtWAVEFORMATEX@@PEAUWAVEFORMATEXTENSIBLE@@@Z; CSpatialProperties::SetSpatialAudioSettingsInternal(EffectPack *,bool,tWAVEFORMATEX const *,WAVEFORMATEXTENSIBLE *)
0x18008bba2  cmp     dword ptr [rbx+1E14h], 1
0x18008bba9  jnz     loc_18008BD8D
0x18008bbaf  xor     eax, eax
0x18008bbb1  mov     [rbp+0A0h+pv], rax
0x18008bbb5  mov     [rsp+1B0h+var_180], rax; pv
0x18008bbba  mov     [rsp+1B0h+var_188], rax; unsigned int *
0x18008bbbf  mov     [rsp+1B0h+var_190], rax; struct SpatialAudioSettings **
0x18008bbc4  lea     r9, [rbp+0A0h+pv]; struct tWAVEFORMATEX **
0x18008bbc8  xor     r8d, r8d; int
0x18008bbcb  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18008bbcd  mov     rcx, r14; this
0x18008bbd0  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x18008bbd5  mov     rdi, r13
0x18008bbd8  mov     rsi, [rbp+0A0h+pv]
0x18008bbdc  test    eax, eax
0x18008bbde  cmovns  rdi, rsi
0x18008bbe2  lea     r8, [rbx+1E18h]; struct WAVEFORMATEXTENSIBLE *
0x18008bbe9  xor     r9d, r9d; bool
0x18008bbec  mov     rdx, r14; this
0x18008bbef  mov     rcx, rbx; lpCriticalSection
0x18008bbf2  call    ?SetDesiredFormat@CSpatialProperties@@AEAA_NPEAVEffectPack@@AEBUWAVEFORMATEXTENSIBLE@@_N@Z; CSpatialProperties::SetDesiredFormat(EffectPack *,WAVEFORMATEXTENSIBLE const &,bool)
0x18008bbf7  xor     r10d, r10d
0x18008bbfa  test    al, al
0x18008bbfc  jz      loc_18008BCE2
0x18008bc02  cmp     [rbp+0A0h+var_70.Format.wFormatTag], r10w
0x18008bc07  jnz     loc_18008BD78
0x18008bc0d  mov     rdx, rdi; struct tWAVEFORMATEX *
0x18008bc10  lea     rcx, [rbp+0A0h+Buf1]; this
0x18008bc14  call    ??0AudioFormatForLogging@@QEAA@PEBUtWAVEFORMATEX@@@Z; AudioFormatForLogging::AudioFormatForLogging(tWAVEFORMATEX const *)
0x18008bc19  mov     dword ptr [rbx+1E14h], 3
0x18008bc23  mov     r9, [rbx+30h]
0x18008bc27  mov     eax, [r9]
0x18008bc2a  cmp     eax, 4
0x18008bc2d  jbe     loc_18008BCC8
0x18008bc33  lea     edx, [r10+10h]
0x18008bc37  mov     rcx, r9
0x18008bc3a  call    _tlgKeywordOn
0x18008bc3f  test    al, al
0x18008bc41  jz      loc_18008BCC8
0x18008bc47  movzx   eax, word ptr [rbp+0A0h+Buf1+0Ah]
0x18008bc4b  mov     [rbp+0A0h+var_120], ax
0x18008bc4f  movzx   eax, word ptr [rbp+0A0h+Buf1+8]
0x18008bc53  mov     [rbp+0A0h+var_118], ax
0x18008bc57  lea     rax, [rbp+0A0h+Buf1+0Ch]
0x18008bc5b  mov     [rbp+0A0h+pv], rax
0x18008bc5f  mov     eax, dword ptr [rbp+0A0h+Buf1+4]
0x18008bc62  mov     dword ptr [rbp+0A0h+var_100], eax
0x18008bc65  mov     eax, [rbp+0A0h+var_94]
0x18008bc68  mov     [rbp+0A0h+var_F8], eax
0x18008bc6b  movzx   eax, word ptr [rbp+0A0h+Buf1]
0x18008bc6f  mov     [rbp+0A0h+var_108], ax
0x18008bc73  mov     [rbp+0A0h+var_E8], r15
0x18008bc77  lea     rax, [rbp+0A0h+var_120]
0x18008bc7b  mov     [rsp+1B0h+var_160], rax
0x18008bc80  lea     rax, [rbp+0A0h+var_118]
0x18008bc84  mov     [rsp+1B0h+var_168], rax
0x18008bc89  lea     rax, [rbp+0A0h+pv]
0x18008bc8d  mov     [rsp+1B0h+var_170], rax
0x18008bc92  lea     rax, [rbp+0A0h+var_100]
0x18008bc96  mov     [rsp+1B0h+var_178], rax
0x18008bc9b  lea     rax, [rbp+0A0h+var_F8]
0x18008bc9f  mov     [rsp+1B0h+var_180], rax
0x18008bca4  lea     rax, [rbp+0A0h+var_108]
0x18008bca8  mov     [rsp+1B0h+var_188], rax
0x18008bcad  lea     rax, [rbp+0A0h+var_E8]
0x18008bcb1  mov     [rsp+1B0h+var_190], rax
0x18008bcb6  lea     rdx, unk_1801AB737
0x18008bcbd  mov     rcx, r9
0x18008bcc0  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &)
0x18008bcc5  xor     r10d, r10d
0x18008bcc8  mov     byte ptr [rsp+1B0h+var_190], r10b; bool
0x18008bccd  xor     r9d, r9d; struct SpatialAudioSettings *
0x18008bcd0  mov     r8, rdi; struct tWAVEFORMATEX *
0x18008bcd3  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18008bcd5  mov     rcx, r14; this
0x18008bcd8  call    ?SetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@PEBUSpatialAudioSettings@@_N@Z; EffectPack::SetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,SpatialAudioSettings const *,bool)
0x18008bcdd  jmp     loc_18008BD75
0x18008bce2  mov     r8, [rbx+30h]
0x18008bce6  mov     eax, [r8]
0x18008bce9  cmp     eax, 2
0x18008bcec  jbe     short loc_18008BD51
0x18008bcee  mov     rdx, 400000000010h
0x18008bcf8  mov     rcx, r8
0x18008bcfb  call    _tlgKeywordOn
0x18008bd00  test    al, al
0x18008bd02  jz      short loc_18008BD51
0x18008bd04  mov     [rbp+0A0h+pv], r15
0x18008bd08  mov     rax, [r14+620h]
0x18008bd0f  movups  xmm0, xmmword ptr [rax]
0x18008bd12  movdqu  [rbp+0A0h+Buf1], xmm0
0x18008bd17  lea     rax, [rbp+0A0h+Buf1]
0x18008bd1b  mov     [rbp+0A0h+var_E8], rax
0x18008bd1f  mov     [rbp+0A0h+var_100], 800h
0x18008bd27  lea     rax, [rbp+0A0h+pv]
0x18008bd2b  mov     [rsp+1B0h+var_180], rax
0x18008bd30  lea     rax, [rbp+0A0h+var_E8]
0x18008bd34  mov     [rsp+1B0h+var_188], rax
0x18008bd39  lea     rax, [rbp+0A0h+var_100]
0x18008bd3d  mov     [rsp+1B0h+var_190], rax
0x18008bd42  lea     rdx, unk_1801AB6DB
0x18008bd49  mov     rcx, r8
0x18008bd4c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x18008bd51  mov     dword ptr [rbx+1E14h], 2
0x18008bd5b  lea     rax, [rbp+0A0h+var_70]
0x18008bd5f  mov     [rsp+1B0h+var_190], rax; struct WAVEFORMATEXTENSIBLE *
0x18008bd64  mov     r9, r13; struct tWAVEFORMATEX *
0x18008bd67  mov     r8b, 1; bool
0x18008bd6a  mov     rdx, r14; struct EffectPack *
0x18008bd6d  mov     rcx, rbx; this
0x18008bd70  call    ?SetSpatialAudioSettingsInternal@CSpatialProperties@@AEAAJPEAVEffectPack@@_NPEBUtWAVEFORMATEX@@PEAUWAVEFORMATEXTENSIBLE@@@Z; CSpatialProperties::SetSpatialAudioSettingsInternal(EffectPack *,bool,tWAVEFORMATEX const *,WAVEFORMATEXTENSIBLE *)
0x18008bd75  xor     r10d, r10d
0x18008bd78  test    rsi, rsi
0x18008bd7b  jz      loc_18008BEF4
0x18008bd81  mov     rcx, rsi; pv
0x18008bd84  call    cs:__imp_CoTaskMemFree
0x18008bd8a  mov     esi, [rbp+0A0h+var_11C]
0x18008bd8d  xor     r10d, r10d
0x18008bd90  mov     rcx, rbx; lpCriticalSection
0x18008bd93  cmp     [rbp+0A0h+var_70.Format.wFormatTag], r10w
0x18008bd98  jz      loc_18008BEFC
0x18008bd9e  mov     r9b, 1; bool
0x18008bda1  lea     r8, [rbp+0A0h+var_70]; struct WAVEFORMATEXTENSIBLE *
0x18008bda5  mov     rdx, r14; this
0x18008bda8  call    ?SetDesiredFormat@CSpatialProperties@@AEAA_NPEAVEffectPack@@AEBUWAVEFORMATEXTENSIBLE@@_N@Z; CSpatialProperties::SetDesiredFormat(EffectPack *,WAVEFORMATEXTENSIBLE const &,bool)
0x18008bdad  xor     r12d, r12d
0x18008bdb0  test    al, al
0x18008bdb2  jnz     loc_18008C135
0x18008bdb8  test    r13, r13
0x18008bdbb  jz      loc_18008C135
0x18008bdc1  mov     rdx, r13; struct tWAVEFORMATEX *
0x18008bdc4  lea     rcx, [rbp+0A0h+var_90]; this
0x18008bdc8  call    ??0AudioFormatForLogging@@QEAA@PEBUtWAVEFORMATEX@@@Z; AudioFormatForLogging::AudioFormatForLogging(tWAVEFORMATEX const *)
0x18008bdcd  mov     r8, [rbx+30h]
0x18008bdd1  mov     eax, [r8]
0x18008bdd4  cmp     eax, 2
0x18008bdd7  jbe     loc_18008BED5
0x18008bddd  lea     edx, [r12+10h]
0x18008bde2  mov     rcx, r8
0x18008bde5  call    _tlgKeywordOn
0x18008bdea  test    al, al
0x18008bdec  jz      loc_18008BED5
0x18008bdf2  lea     rax, [rbp+0A0h+var_84]
0x18008bdf6  mov     [rbp+0A0h+var_B8], rax
0x18008bdfa  mov     eax, [rbp+0A0h+var_74]
0x18008bdfd  mov     dword ptr [rbp+0A0h+var_E8], eax
0x18008be00  movzx   eax, [rbp+0A0h+var_86]
0x18008be04  mov     [rbp+0A0h+var_108], ax
0x18008be08  movzx   eax, [rbp+0A0h+var_88]
0x18008be0c  mov     [rbp+0A0h+var_120], ax
0x18008be10  mov     eax, [rbp+0A0h+var_8C]
0x18008be13  mov     dword ptr [rbp+0A0h+pv], eax
0x18008be16  movzx   eax, [rbp+0A0h+var_90]
0x18008be1a  mov     [rbp+0A0h+var_118], ax
0x18008be1e  lea     rax, [rbp+0A0h+var_70.SubFormat]
0x18008be22  mov     qword ptr [rbp+0A0h+Buf2], rax
0x18008be26  mov     eax, [rbp+0A0h+var_70.dwChannelMask]
0x18008be29  mov     [rbp+0A0h+var_F4], eax
0x18008be2c  movzx   eax, word ptr [rbp+0A0h+var_70.Samples]
0x18008be30  mov     word ptr [rbp+0A0h+var_F8], ax
0x18008be34  movzx   eax, [rbp+0A0h+var_70.Format.wBitsPerSample]
0x18008be38  mov     word ptr [rbp+0A0h+var_100], ax
0x18008be3c  mov     eax, [rbp+0A0h+var_70.Format.nSamplesPerSec]
0x18008be3f  mov     dword ptr [rbp+0A0h+var_110], eax
0x18008be42  movzx   eax, [rbp+0A0h+var_70.Format.nChannels]
0x18008be46  mov     word ptr [rbp+0A0h+var_11C], ax
0x18008be4a  mov     qword ptr [rbp+0A0h+Buf1], r15
0x18008be4e  lea     rax, [rbp+0A0h+var_B8]
0x18008be52  mov     [rsp+1B0h+var_130], rax
0x18008be5a  lea     rax, [rbp+0A0h+var_E8]
0x18008be5e  mov     [rsp+1B0h+var_138], rax
0x18008be63  lea     rax, [rbp+0A0h+var_108]
0x18008be67  mov     [rsp+1B0h+var_140], rax
0x18008be6c  lea     rax, [rbp+0A0h+var_120]
0x18008be70  mov     [rsp+1B0h+var_148], rax
0x18008be75  lea     rax, [rbp+0A0h+pv]
0x18008be79  mov     [rsp+1B0h+var_150], rax
0x18008be7e  lea     rax, [rbp+0A0h+var_118]
0x18008be82  mov     [rsp+1B0h+var_158], rax
0x18008be87  lea     rax, [rbp+0A0h+Buf2]
0x18008be8b  mov     [rsp+1B0h+var_160], rax
0x18008be90  lea     rax, [rbp+0A0h+var_F4]
0x18008be94  mov     [rsp+1B0h+var_168], rax
  ... truncated ...
```
