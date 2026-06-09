# CSpatialProperties::ProcessPropertyChange(EffectPack *,_tagpropertykey const &,SpatialAudioRelatedGlobalSettings *,tWAVEFORMATEX const *,int *)

- ea: `0x18008ba74`
- end: `0x18008c4cf`
- name: `?ProcessPropertyChange@CSpatialProperties@@QEAAXPEAVEffectPack@@AEBU_tagpropertykey@@PEAUSpatialAudioRelatedGlobalSettings@@PEBUtWAVEFORMATEX@@PEAH@Z`
- size: `2651`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct EffectPack *this, const struct _tagpropertykey *, struct SpatialAudioRelatedGlobalSettings *, struct tWAVEFORMATEX *, int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024ee4`

## callees

- `0x180006df4`
- `0x180006eb8`
- `0x180006f68`
- `0x1800070f8`
- `0x18000726c`
- `0x180007708`
- `0x1800202b0`
- `0x180045d24`
- `0x180061e64`
- `0x180062b9c`
- `0x18006de80`
- `0x180072e10`
- `0x18008a0f4`
- `0x18008ba74`
- `0x18008c4d8`
- `0x1800b28c0`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1800ce750`
- `0x18014a2c0`
- `0x18014b1d0`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008bbdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008bfa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c242`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008bbdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008bfa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c242`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008bc2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c012`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c2ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c492`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008bc2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c012`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c2ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c492`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008c49d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008c49d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008be30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c1cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c1db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008be30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c1cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c1db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c33e`

## string_xrefs

- `0x18008baf3`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  struct _RTL_CRITICAL_SECTION *v45; // rcx
  int v46; // eax
  struct tWAVEFORMATEX *v47; // r9
  struct tWAVEFORMATEX *v48; // rsi
  int v49; // r8d
  int v50; // r9d
  int v51; // r8d
  int v52; // r9d
  int v53; // r8d
  int v54; // r9d
  int v55; // [rsp+20h] [rbp-F0h]
  _WORD v56[2]; // [rsp+90h] [rbp-80h] BYREF
  LONG v57; // [rsp+94h] [rbp-7Ch] BYREF
  __int16 v58; // [rsp+98h] [rbp-78h] BYREF
  struct tWAVEFORMATEX *v59; // [rsp+A0h] [rbp-70h] BYREF
  __int16 v60; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-60h] BYREF
  int v62; // [rsp+B8h] [rbp-58h] BYREF
  DWORD SpatialRendererSelectionMode; // [rsp+BCh] [rbp-54h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-50h] BYREF
  struct tWAVEFORMATEX *p_Buf1; // [rsp+C8h] [rbp-48h] BYREF
  __int128 Buf2; // [rsp+D0h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+E0h] [rbp-30h] BYREF
  __int64 v68; // [rsp+F0h] [rbp-20h]
  _BYTE *v69; // [rsp+F8h] [rbp-18h] BYREF
  __int128 Buf1; // [rsp+100h] [rbp-10h] BYREF
  int v71; // [rsp+11Ch] [rbp+Ch]
  _WORD v72[2]; // [rsp+120h] [rbp+10h] BYREF
  int v73; // [rsp+124h] [rbp+14h]
  __int16 v74; // [rsp+128h] [rbp+18h]
  __int16 v75; // [rsp+12Ah] [rbp+1Ah]
  _BYTE v76[16]; // [rsp+12Ch] [rbp+1Ch] BYREF
  DWORD v77; // [rsp+13Ch] [rbp+2Ch]
  WAVEFORMATEXTENSIBLE v78; // [rsp+140h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+A8h]

  *(_OWORD *)pvar = 0;
  v68 = 0;
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
      v55);
    goto LABEL_103;
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
      v56[0] = pvar[1];
      if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u )
      {
        if ( (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
        {
          v57 = LOWORD(pvar[0]);
          LOBYTE(v58) = HIBYTE(v56[0]);
          LOBYTE(v56[0]) = v12;
          v59 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)&word_1801ACA7E,
            v12,
            v13,
            (__int64)&v59,
            (__int64)v56,
            (__int64)&v58,
            (__int64)&v57);
        }
      }
    }
    memset(&v78, 0, sizeof(v78));
    EnterCriticalSection(lpCriticalSection);
    if ( !LODWORD(lpCriticalSection[192].OwningThread) )
    {
      LODWORD(lpCriticalSection[192].OwningThread) = 1;
      v14 = *(__m128i *)&lpCriticalSection[192].DebugInfo;
      Buf2 = *(_OWORD *)((char *)&lpCriticalSection[2].LockSemaphore + 4);
      LODWORD(v59) = lpCriticalSection[2].OwningThread;
      RecursionCount = lpCriticalSection[2].RecursionCount;
      v57 = RecursionCount;
      SpatialRendererSelectionMode = GetSpatialRendererSelectionMode(CSpatialProperties::s_exclusiveModeListener);
      BYTE2(lpCriticalSection[2].LockCount) = *(_BYTE *)a4 != 0;
      LeaveCriticalSection(lpCriticalSection);
      CSpatialProperties::SetSpatialAudioSettingsInternal((CSpatialProperties *)lpCriticalSection, this, 1, a5, &v78);
      if ( HIDWORD(lpCriticalSection[192].OwningThread) == 1 )
      {
        pv = 0;
        DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                           this,
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
          if ( !v78.Format.wFormatTag )
          {
            AudioFormatForLogging::AudioFormatForLogging((AudioFormatForLogging *)&Buf1, v17);
            HIDWORD(lpCriticalSection[192].OwningThread) = 3;
            if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
              && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, (unsigned int)(v19 + 16)) )
            {
              v56[0] = WORD5(Buf1);
              v58 = WORD4(Buf1);
              pv = (char *)&Buf1 + 12;
              LODWORD(v61) = DWORD1(Buf1);
              v62 = v71;
              v60 = Buf1;
              p_Buf1 = v11;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
                v21,
                (unsigned int)&word_1801ACB1E,
                v20,
                v21,
                (__int64)&p_Buf1,
                (__int64)&v60,
                (__int64)&v62,
                (__int64)&v61,
                (__int64)&pv,
                (__int64)&v58,
                (__int64)v56);
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
            v61 = 2048;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
              v22,
              (unsigned int)word_1801ACAC2,
              v22,
              v23,
              (__int64)&v61,
              (__int64)&p_Buf1,
              (__int64)&pv);
          }
          HIDWORD(lpCriticalSection[192].OwningThread) = 2;
          CSpatialProperties::SetSpatialAudioSettingsInternal(
            (CSpatialProperties *)lpCriticalSection,
            this,
            1,
            a5,
            &v78);
        }
        if ( v18 )
          CoTaskMemFree(v18);
        RecursionCount = v57;
      }
      if ( v78.Format.wFormatTag )
      {
        if ( !CSpatialProperties::SetDesiredFormat(lpCriticalSection, this, &v78, 1) && a5 )
        {
          AudioFormatForLogging::AudioFormatForLogging((AudioFormatForLogging *)v72, a5);
          if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 2u
            && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
          {
            v69 = v76;
            LODWORD(p_Buf1) = v77;
            v60 = v75;
            v56[0] = v74;
            LODWORD(pv) = v73;
            v58 = v72[0];
            *(_QWORD *)&Buf2 = &v78.SubFormat;
            SpatialRendererSelectionMode = v78.dwChannelMask;
            LOWORD(v62) = v78.Samples.wValidBitsPerSample;
            LOWORD(v61) = v78.Format.wBitsPerSample;
            LODWORD(v59) = v78.Format.nSamplesPerSec;
            LOWORD(v57) = v78.Format.nChannels;
            *(_QWORD *)&Buf1 = v11;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              v24,
              (unsigned int)&dword_1801AC884,
              v24,
              v25,
              (__int64)&Buf1,
              (__int64)&v57,
              (__int64)&v59,
              (__int64)&v61,
              (__int64)&v62,
              (__int64)&SpatialRendererSelectionMode,
              (__int64)&Buf2,
              (__int64)&v58,
              (__int64)&pv,
              (__int64)v56,
              (__int64)&v60,
              (__int64)&p_Buf1,
              (__int64)&v69);
          }
          CSpatialProperties::SetSpatialAudioSettingsInternal(
            (CSpatialProperties *)lpCriticalSection,
            this,
            0,
            a5,
            &v78);
        }
      }
      else
      {
        EnterCriticalSection(lpCriticalSection);
        Buf1 = *(_OWORD *)((char *)&lpCriticalSection[2].LockSemaphore + 4);
        OwningThread = (int)lpCriticalSection[2].OwningThread;
        v27 = OwningThread != (_DWORD)v59
           || lpCriticalSection[2].RecursionCount != RecursionCount
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
            (unsigned int)qword_1801AC858,
            v28,
            v29,
            (__int64)&Buf1);
        }
        if ( !HIBYTE(lpCriticalSection[2].LockCount) )
        {
          v59 = 0;
          v30 = EffectPack::GetDeviceFormatAndSpatialSettings(this, eHostProcessConnector, 0, &v59, 0, 0, 0);
          v31 = a5;
          v32 = v59;
          if ( v30 >= 0 )
            v31 = v59;
          if ( !OwningThread
            && !SpatialRendererSelectionMode
            && v31
            && v31->wFormatTag == 0xFFFE
            && (unsigned __int8)IsSpatialOnlyFormat((char *)&v31[1].nSamplesPerSec + 2) )
          {
            v59 = 0;
            v33 = EffectPack::GetDeviceFormatAndSpatialSettings(this, eHostProcessConnector, 1, &v59, 0, 0, 0);
            v34 = v59;
            if ( v33 >= 0 )
            {
              AudioFormatForLogging::AudioFormatForLogging((AudioFormatForLogging *)v72, v59);
              if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
                && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
              {
                LOWORD(v57) = v75;
                LOWORD(v61) = v74;
                *(_QWORD *)&Buf1 = v76;
                LODWORD(v59) = v73;
                SpatialRendererSelectionMode = v77;
                LOWORD(v62) = v72[0];
                *(_QWORD *)&Buf2 = v11;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
                  v35,
                  (unsigned int)byte_1801AC9BB,
                  v35,
                  v36,
                  (__int64)&Buf2,
                  (__int64)&v62,
                  (__int64)&SpatialRendererSelectionMode,
                  (__int64)&v59,
                  (__int64)&Buf1,
                  (__int64)&v61,
                  (__int64)&v57);
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
        v59 = 0;
        if ( v37 == 3
          && **(_DWORD **)&lpCriticalSection[1].LockCount > 2u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
        {
          LOWORD(v57) = lpCriticalSection[192].OwningThread;
          *(_QWORD *)&Buf1 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>>(
            v38,
            (unsigned int)&unk_1801AC968,
            v38,
            v39,
            (__int64)&Buf1,
            (__int64)&v57);
        }
        EnterCriticalSection(lpCriticalSection);
        *(_QWORD *)&Buf2 = lpCriticalSection;
        v40 = (int)lpCriticalSection[192].OwningThread;
        if ( !v40 )
          goto LABEL_77;
        v41 = v40 - 1;
        if ( v41 )
          break;
LABEL_80:
        LODWORD(lpCriticalSection[192].OwningThread) = 0;
LABEL_81:
        v45 = lpCriticalSection;
        if ( !LODWORD(lpCriticalSection[192].OwningThread) )
          goto LABEL_102;
        LeaveCriticalSection(lpCriticalSection);
        v46 = EffectPack::GetDeviceFormatAndSpatialSettings(this, eHostProcessConnector, 0, &v59, 0, 0, 0);
        v47 = a5;
        v48 = v59;
        if ( v46 >= 0 )
          v47 = v59;
        CSpatialProperties::SetSpatialAudioSettingsInternal((CSpatialProperties *)lpCriticalSection, this, 0, v47, &v78);
        if ( v48 )
          CoTaskMemFree(v48);
        if ( (unsigned __int16)++v37 >= 5u )
          goto LABEL_103;
      }
      v42 = v41 - 1;
      if ( !v42 )
      {
        if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
        {
          LOWORD(v57) = lpCriticalSection[192].OwningThread;
          LOWORD(v61) = v37;
          *(_QWORD *)&Buf1 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
            v51,
            (unsigned int)&unk_1801AC738,
            v51,
            v52,
            (__int64)&Buf1,
            (__int64)&v61,
            (__int64)&v57);
        }
        LODWORD(lpCriticalSection[192].OwningThread) = 0;
        CSpatialProperties::SignalSpatialRelatedChange(
          *(_DWORD **)&lpCriticalSection[1].LockCount,
          (__int64)lpCriticalSection[1].OwningThread,
          4);
        goto LABEL_81;
      }
      if ( v42 == 1 )
      {
        if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
          && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
        {
          LOWORD(v57) = lpCriticalSection[192].OwningThread;
          LOWORD(v61) = v37;
          *(_QWORD *)&Buf1 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
            v49,
            (unsigned int)&word_1801AC796,
            v49,
            v50,
            (__int64)&Buf1,
            (__int64)&v61,
            (__int64)&v57);
        }
        LODWORD(lpCriticalSection[192].OwningThread) = 1;
        goto LABEL_81;
      }
      CSpatialProperties::SignalSpatialRelatedChange(
        *(_DWORD **)&lpCriticalSection[1].LockCount,
        (__int64)lpCriticalSection[1].OwningThread,
        5);
LABEL_77:
      if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 2u
        && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
      {
        LOWORD(v57) = lpCriticalSection[192].OwningThread;
        LOWORD(v61) = v37;
        *(_QWORD *)&Buf1 = v11;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
          v43,
          (unsigned int)&dword_1801AC7F4,
          v43,
          v44,
          (__int64)&Buf1,
          (__int64)&v61,
          (__int64)&v57);
      }
      goto LABEL_80;
    }
    if ( **(_DWORD **)&lpCriticalSection[1].LockCount > 4u
      && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&lpCriticalSection[1].LockCount, 16) )
    {
      LOBYTE(v56[0]) = lpCriticalSection[192].OwningThread;
      *(_QWORD *)&Buf1 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        v53,
        (unsigned int)&word_1801ACA2E,
        v53,
        v54,
        (__int64)&Buf1,
        (__int64)v56);
    }
    if ( LODWORD(lpCriticalSection[192].OwningThread) == 1 )
      LODWORD(lpCriticalSection[192].OwningThread) = 2;
    v45 = lpCriticalSection;
LABEL_102:
    LeaveCriticalSection(v45);
  }
LABEL_103:
  PropVariantClear(pvar);
}

```

## disassembly

```asm
0x18008ba74  mov     rax, rsp
0x18008ba77  mov     [rax+18h], rbx
0x18008ba7b  push    rbp
0x18008ba7c  push    rsi
0x18008ba7d  push    rdi
0x18008ba7e  push    r12
0x18008ba80  push    r13
0x18008ba82  push    r14
0x18008ba84  push    r15
0x18008ba86  lea     rbp, [rsp-70h]
0x18008ba8b  sub     rsp, 180h
0x18008ba92  movaps  xmmword ptr [rax-48h], xmm6
0x18008ba96  mov     rax, cs:__security_cookie
0x18008ba9d  xor     rax, rsp
0x18008baa0  mov     [rbp+0A0h+var_48], rax
0x18008baa4  mov     rdi, r9
0x18008baa7  mov     r14, rdx
0x18008baaa  mov     rbx, rcx
0x18008baad  mov     r13, [rbp+0A0h+arg_20]
0x18008bab4  mov     r12, [rbp+0A0h+arg_28]
0x18008babb  xorps   xmm0, xmm0
0x18008babe  xor     eax, eax
0x18008bac0  movups  xmmword ptr [rbp+0A0h+pvar], xmm0
0x18008bac4  mov     [rbp+0A0h+var_C0], rax
0x18008bac8  xor     esi, esi
0x18008baca  mov     [r12], esi
0x18008bace  mov     r15, [rcx+28h]
0x18008bad2  test    r15, r15
0x18008bad5  jz      short loc_18008BAE0
0x18008bad7  cmp     [rcx+40h], rsi
0x18008badb  mov     al, sil
0x18008bade  jnz     short loc_18008BAE2
0x18008bae0  mov     al, 1
0x18008bae2  mov     rcx, [rbp+0A8h]; this
0x18008bae9  test    al, al
0x18008baeb  jz      short loc_18008BB09
0x18008baed  mov     r9d, 8000FFFFh; char *
0x18008baf3  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\server\\lib\\audiose"...
0x18008bafa  mov     edx, 7AAh; void *
0x18008baff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008bb04  jmp     loc_18008C499
0x18008bb09  mov     rax, [r8]
0x18008bb0c  cmp     rax, qword ptr cs:PKEY_SpatialAudio_Signaling_Key.fmtid.Data1
0x18008bb13  jnz     loc_18008C499
0x18008bb19  mov     rax, [r8+8]
0x18008bb1d  cmp     rax, qword ptr cs:PKEY_SpatialAudio_Signaling_Key.fmtid.Data4
0x18008bb24  jnz     loc_18008C499
0x18008bb2a  cmp     dword ptr [r8+10h], 2
0x18008bb2f  jnz     loc_18008C499
0x18008bb35  mov     r15, [r15+30h]
0x18008bb39  mov     rcx, [rbx+38h]
0x18008bb3d  mov     rax, [rcx]
0x18008bb40  lea     r8, [rbp+0A0h+pvar]
0x18008bb44  lea     rdx, PKEY_SpatialAudio_Signaling_Key
0x18008bb4b  mov     rax, [rax+28h]
0x18008bb4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bb54  test    eax, eax
0x18008bb56  js      short loc_18008BBC7
0x18008bb58  movzx   r8d, word ptr [rbp+0A0h+pvar+8]
0x18008bb5d  mov     [rbp+0A0h+var_120], r8w
0x18008bb62  mov     r9, [rbx+30h]
0x18008bb66  mov     eax, [r9]
0x18008bb69  cmp     eax, 4
0x18008bb6c  jbe     short loc_18008BBC7
0x18008bb6e  mov     edx, 10h
0x18008bb73  mov     rcx, r9
0x18008bb76  call    _tlgKeywordOn
0x18008bb7b  test    al, al
0x18008bb7d  jz      short loc_18008BBC7
0x18008bb7f  movzx   eax, word ptr [rbp+0A0h+pvar]
0x18008bb83  mov     [rbp+0A0h+var_11C], eax
0x18008bb86  mov     al, byte ptr [rbp+0A0h+var_120+1]
0x18008bb89  mov     byte ptr [rbp+0A0h+var_118], al
0x18008bb8c  mov     byte ptr [rbp+0A0h+var_120], r8b
0x18008bb90  mov     [rbp+0A0h+var_110], r15
0x18008bb94  lea     rax, [rbp+0A0h+var_11C]
0x18008bb98  mov     [rsp+1B0h+var_178], rax
0x18008bb9d  lea     rax, [rbp+0A0h+var_118]
0x18008bba1  mov     [rsp+1B0h+var_180], rax
0x18008bba6  lea     rax, [rbp+0A0h+var_120]
0x18008bbaa  mov     [rsp+1B0h+var_188], rax
0x18008bbaf  lea     rax, [rbp+0A0h+var_110]
0x18008bbb3  mov     [rsp+1B0h+var_190], rax
0x18008bbb8  lea     rdx, word_1801ACA7E
0x18008bbbf  mov     rcx, r9
0x18008bbc2  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18008bbc7  xorps   xmm0, xmm0
0x18008bbca  xor     eax, eax
0x18008bbcc  movups  xmmword ptr [rbp+0A0h+var_70.Format.wFormatTag], xmm0
0x18008bbd0  movups  xmmword ptr [rbp+0A0h+var_70.Format.cbSize], xmm0
0x18008bbd4  mov     qword ptr [rbp+0A0h+var_70.SubFormat.Data4], rax
0x18008bbd8  mov     rcx, rbx; lpCriticalSection
0x18008bbdb  call    cs:__imp_EnterCriticalSection
0x18008bbe1  cmp     [rbx+1E10h], esi
0x18008bbe7  jnz     loc_18008C431
0x18008bbed  mov     dword ptr [rbx+1E10h], 1
0x18008bbf7  movups  xmm6, xmmword ptr [rbx+1E00h]
0x18008bbfe  movups  xmm0, xmmword ptr [rbx+6Ch]
0x18008bc02  movdqu  [rbp+0A0h+Buf2], xmm0
0x18008bc07  mov     eax, [rbx+60h]
0x18008bc0a  mov     dword ptr [rbp+0A0h+var_110], eax
0x18008bc0d  mov     esi, [rbx+5Ch]
0x18008bc10  mov     [rbp+0A0h+var_11C], esi
0x18008bc13  mov     rcx, cs:?s_exclusiveModeListener@CSpatialProperties@@0V?$com_ptr_t@VCExclusiveModeListener@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<CExclusiveModeListener,wil::err_returncode_policy> CSpatialProperties::s_exclusiveModeListener
0x18008bc1a  call    GetSpatialRendererSelectionMode
0x18008bc1f  mov     [rbp+0A0h+var_F4], eax
0x18008bc22  cmp     byte ptr [rdi], 0
0x18008bc25  setnz   cl
0x18008bc28  mov     [rbx+5Ah], cl
0x18008bc2b  mov     rcx, rbx; lpCriticalSection
0x18008bc2e  call    cs:__imp_LeaveCriticalSection
0x18008bc34  lea     rax, [rbp+0A0h+var_70]
0x18008bc38  mov     [rsp+1B0h+var_190], rax; struct WAVEFORMATEXTENSIBLE *
0x18008bc3d  mov     r9, r13; struct tWAVEFORMATEX *
0x18008bc40  mov     r8b, 1; bool
0x18008bc43  mov     rdx, r14; struct EffectPack *
0x18008bc46  mov     rcx, rbx; this
0x18008bc49  call    ?SetSpatialAudioSettingsInternal@CSpatialProperties@@AEAAJPEAVEffectPack@@_NPEBUtWAVEFORMATEX@@PEAUWAVEFORMATEXTENSIBLE@@@Z; CSpatialProperties::SetSpatialAudioSettingsInternal(EffectPack *,bool,tWAVEFORMATEX const *,WAVEFORMATEXTENSIBLE *)
0x18008bc4e  cmp     dword ptr [rbx+1E14h], 1
0x18008bc55  jnz     loc_18008BE39
0x18008bc5b  xor     eax, eax
0x18008bc5d  mov     [rbp+0A0h+pv], rax
0x18008bc61  mov     [rsp+1B0h+var_180], rax; pv
0x18008bc66  mov     [rsp+1B0h+var_188], rax; unsigned int *
0x18008bc6b  mov     [rsp+1B0h+var_190], rax; struct SpatialAudioSettings **
0x18008bc70  lea     r9, [rbp+0A0h+pv]; struct tWAVEFORMATEX **
0x18008bc74  xor     r8d, r8d; int
0x18008bc77  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18008bc79  mov     rcx, r14; this
0x18008bc7c  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x18008bc81  mov     rdi, r13
0x18008bc84  mov     rsi, [rbp+0A0h+pv]
0x18008bc88  test    eax, eax
0x18008bc8a  cmovns  rdi, rsi
0x18008bc8e  lea     r8, [rbx+1E18h]; struct WAVEFORMATEXTENSIBLE *
0x18008bc95  xor     r9d, r9d; bool
0x18008bc98  mov     rdx, r14; this
0x18008bc9b  mov     rcx, rbx; lpCriticalSection
0x18008bc9e  call    ?SetDesiredFormat@CSpatialProperties@@AEAA_NPEAVEffectPack@@AEBUWAVEFORMATEXTENSIBLE@@_N@Z; CSpatialProperties::SetDesiredFormat(EffectPack *,WAVEFORMATEXTENSIBLE const &,bool)
0x18008bca3  xor     r10d, r10d
0x18008bca6  test    al, al
0x18008bca8  jz      loc_18008BD8E
0x18008bcae  cmp     [rbp+0A0h+var_70.Format.wFormatTag], r10w
0x18008bcb3  jnz     loc_18008BE24
0x18008bcb9  mov     rdx, rdi; struct tWAVEFORMATEX *
0x18008bcbc  lea     rcx, [rbp+0A0h+Buf1]; this
0x18008bcc0  call    ??0AudioFormatForLogging@@QEAA@PEBUtWAVEFORMATEX@@@Z; AudioFormatForLogging::AudioFormatForLogging(tWAVEFORMATEX const *)
0x18008bcc5  mov     dword ptr [rbx+1E14h], 3
0x18008bccf  mov     r9, [rbx+30h]
0x18008bcd3  mov     eax, [r9]
0x18008bcd6  cmp     eax, 4
0x18008bcd9  jbe     loc_18008BD74
0x18008bcdf  lea     edx, [r10+10h]
0x18008bce3  mov     rcx, r9
0x18008bce6  call    _tlgKeywordOn
0x18008bceb  test    al, al
0x18008bced  jz      loc_18008BD74
0x18008bcf3  movzx   eax, word ptr [rbp+0A0h+Buf1+0Ah]
0x18008bcf7  mov     [rbp+0A0h+var_120], ax
0x18008bcfb  movzx   eax, word ptr [rbp+0A0h+Buf1+8]
0x18008bcff  mov     [rbp+0A0h+var_118], ax
0x18008bd03  lea     rax, [rbp+0A0h+Buf1+0Ch]
0x18008bd07  mov     [rbp+0A0h+pv], rax
0x18008bd0b  mov     eax, dword ptr [rbp+0A0h+Buf1+4]
0x18008bd0e  mov     dword ptr [rbp+0A0h+var_100], eax
0x18008bd11  mov     eax, [rbp+0A0h+var_94]
0x18008bd14  mov     [rbp+0A0h+var_F8], eax
0x18008bd17  movzx   eax, word ptr [rbp+0A0h+Buf1]
0x18008bd1b  mov     [rbp+0A0h+var_108], ax
0x18008bd1f  mov     [rbp+0A0h+var_E8], r15
0x18008bd23  lea     rax, [rbp+0A0h+var_120]
0x18008bd27  mov     [rsp+1B0h+var_160], rax
0x18008bd2c  lea     rax, [rbp+0A0h+var_118]
0x18008bd30  mov     [rsp+1B0h+var_168], rax
0x18008bd35  lea     rax, [rbp+0A0h+pv]
0x18008bd39  mov     [rsp+1B0h+var_170], rax
0x18008bd3e  lea     rax, [rbp+0A0h+var_100]
0x18008bd42  mov     [rsp+1B0h+var_178], rax
0x18008bd47  lea     rax, [rbp+0A0h+var_F8]
0x18008bd4b  mov     [rsp+1B0h+var_180], rax
0x18008bd50  lea     rax, [rbp+0A0h+var_108]
0x18008bd54  mov     [rsp+1B0h+var_188], rax
0x18008bd59  lea     rax, [rbp+0A0h+var_E8]
0x18008bd5d  mov     [rsp+1B0h+var_190], rax
0x18008bd62  lea     rdx, word_1801ACB1E
0x18008bd69  mov     rcx, r9
0x18008bd6c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByRef@$0BA@@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByRef@$0BA@@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &)
0x18008bd71  xor     r10d, r10d
0x18008bd74  mov     byte ptr [rsp+1B0h+var_190], r10b; bool
0x18008bd79  xor     r9d, r9d; struct SpatialAudioSettings *
0x18008bd7c  mov     r8, rdi; struct tWAVEFORMATEX *
0x18008bd7f  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18008bd81  mov     rcx, r14; this
0x18008bd84  call    ?SetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@PEBUSpatialAudioSettings@@_N@Z; EffectPack::SetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,SpatialAudioSettings const *,bool)
0x18008bd89  jmp     loc_18008BE21
0x18008bd8e  mov     r8, [rbx+30h]
0x18008bd92  mov     eax, [r8]
0x18008bd95  cmp     eax, 2
0x18008bd98  jbe     short loc_18008BDFD
0x18008bd9a  mov     rdx, 400000000010h
0x18008bda4  mov     rcx, r8
0x18008bda7  call    _tlgKeywordOn
0x18008bdac  test    al, al
0x18008bdae  jz      short loc_18008BDFD
0x18008bdb0  mov     [rbp+0A0h+pv], r15
0x18008bdb4  mov     rax, [r14+620h]
0x18008bdbb  movups  xmm0, xmmword ptr [rax]
0x18008bdbe  movdqu  [rbp+0A0h+Buf1], xmm0
0x18008bdc3  lea     rax, [rbp+0A0h+Buf1]
0x18008bdc7  mov     [rbp+0A0h+var_E8], rax
0x18008bdcb  mov     [rbp+0A0h+var_100], 800h
0x18008bdd3  lea     rax, [rbp+0A0h+pv]
0x18008bdd7  mov     [rsp+1B0h+var_180], rax
0x18008bddc  lea     rax, [rbp+0A0h+var_E8]
0x18008bde0  mov     [rsp+1B0h+var_188], rax
0x18008bde5  lea     rax, [rbp+0A0h+var_100]
0x18008bde9  mov     [rsp+1B0h+var_190], rax
0x18008bdee  lea     rdx, word_1801ACAC2
0x18008bdf5  mov     rcx, r8
0x18008bdf8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x18008bdfd  mov     dword ptr [rbx+1E14h], 2
0x18008be07  lea     rax, [rbp+0A0h+var_70]
0x18008be0b  mov     [rsp+1B0h+var_190], rax; struct WAVEFORMATEXTENSIBLE *
0x18008be10  mov     r9, r13; struct tWAVEFORMATEX *
0x18008be13  mov     r8b, 1; bool
0x18008be16  mov     rdx, r14; struct EffectPack *
0x18008be19  mov     rcx, rbx; this
0x18008be1c  call    ?SetSpatialAudioSettingsInternal@CSpatialProperties@@AEAAJPEAVEffectPack@@_NPEBUtWAVEFORMATEX@@PEAUWAVEFORMATEXTENSIBLE@@@Z; CSpatialProperties::SetSpatialAudioSettingsInternal(EffectPack *,bool,tWAVEFORMATEX const *,WAVEFORMATEXTENSIBLE *)
0x18008be21  xor     r10d, r10d
0x18008be24  test    rsi, rsi
0x18008be27  jz      loc_18008BFA0
0x18008be2d  mov     rcx, rsi; pv
0x18008be30  call    cs:__imp_CoTaskMemFree
0x18008be36  mov     esi, [rbp+0A0h+var_11C]
0x18008be39  xor     r10d, r10d
0x18008be3c  mov     rcx, rbx; lpCriticalSection
0x18008be3f  cmp     [rbp+0A0h+var_70.Format.wFormatTag], r10w
0x18008be44  jz      loc_18008BFA8
0x18008be4a  mov     r9b, 1; bool
0x18008be4d  lea     r8, [rbp+0A0h+var_70]; struct WAVEFORMATEXTENSIBLE *
0x18008be51  mov     rdx, r14; this
0x18008be54  call    ?SetDesiredFormat@CSpatialProperties@@AEAA_NPEAVEffectPack@@AEBUWAVEFORMATEXTENSIBLE@@_N@Z; CSpatialProperties::SetDesiredFormat(EffectPack *,WAVEFORMATEXTENSIBLE const &,bool)
0x18008be59  xor     r12d, r12d
0x18008be5c  test    al, al
0x18008be5e  jnz     loc_18008C1E1
0x18008be64  test    r13, r13
0x18008be67  jz      loc_18008C1E1
0x18008be6d  mov     rdx, r13; struct tWAVEFORMATEX *
0x18008be70  lea     rcx, [rbp+0A0h+var_90]; this
0x18008be74  call    ??0AudioFormatForLogging@@QEAA@PEBUtWAVEFORMATEX@@@Z; AudioFormatForLogging::AudioFormatForLogging(tWAVEFORMATEX const *)
0x18008be79  mov     r8, [rbx+30h]
0x18008be7d  mov     eax, [r8]
0x18008be80  cmp     eax, 2
0x18008be83  jbe     loc_18008BF81
0x18008be89  lea     edx, [r12+10h]
0x18008be8e  mov     rcx, r8
0x18008be91  call    _tlgKeywordOn
0x18008be96  test    al, al
0x18008be98  jz      loc_18008BF81
0x18008be9e  lea     rax, [rbp+0A0h+var_84]
0x18008bea2  mov     [rbp+0A0h+var_B8], rax
0x18008bea6  mov     eax, [rbp+0A0h+var_74]
0x18008bea9  mov     dword ptr [rbp+0A0h+var_E8], eax
0x18008beac  movzx   eax, [rbp+0A0h+var_86]
0x18008beb0  mov     [rbp+0A0h+var_108], ax
0x18008beb4  movzx   eax, [rbp+0A0h+var_88]
0x18008beb8  mov     [rbp+0A0h+var_120], ax
0x18008bebc  mov     eax, [rbp+0A0h+var_8C]
0x18008bebf  mov     dword ptr [rbp+0A0h+pv], eax
0x18008bec2  movzx   eax, [rbp+0A0h+var_90]
0x18008bec6  mov     [rbp+0A0h+var_118], ax
0x18008beca  lea     rax, [rbp+0A0h+var_70.SubFormat]
0x18008bece  mov     qword ptr [rbp+0A0h+Buf2], rax
0x18008bed2  mov     eax, [rbp+0A0h+var_70.dwChannelMask]
0x18008bed5  mov     [rbp+0A0h+var_F4], eax
0x18008bed8  movzx   eax, word ptr [rbp+0A0h+var_70.Samples]
0x18008bedc  mov     word ptr [rbp+0A0h+var_F8], ax
0x18008bee0  movzx   eax, [rbp+0A0h+var_70.Format.wBitsPerSample]
0x18008bee4  mov     word ptr [rbp+0A0h+var_100], ax
0x18008bee8  mov     eax, [rbp+0A0h+var_70.Format.nSamplesPerSec]
0x18008beeb  mov     dword ptr [rbp+0A0h+var_110], eax
0x18008beee  movzx   eax, [rbp+0A0h+var_70.Format.nChannels]
0x18008bef2  mov     word ptr [rbp+0A0h+var_11C], ax
0x18008bef6  mov     qword ptr [rbp+0A0h+Buf1], r15
0x18008befa  lea     rax, [rbp+0A0h+var_B8]
0x18008befe  mov     [rsp+1B0h+var_130], rax
0x18008bf06  lea     rax, [rbp+0A0h+var_E8]
0x18008bf0a  mov     [rsp+1B0h+var_138], rax
0x18008bf0f  lea     rax, [rbp+0A0h+var_108]
0x18008bf13  mov     [rsp+1B0h+var_140], rax
0x18008bf18  lea     rax, [rbp+0A0h+var_120]
0x18008bf1c  mov     [rsp+1B0h+var_148], rax
0x18008bf21  lea     rax, [rbp+0A0h+pv]
0x18008bf25  mov     [rsp+1B0h+var_150], rax
0x18008bf2a  lea     rax, [rbp+0A0h+var_118]
0x18008bf2e  mov     [rsp+1B0h+var_158], rax
0x18008bf33  lea     rax, [rbp+0A0h+Buf2]
0x18008bf37  mov     [rsp+1B0h+var_160], rax
0x18008bf3c  lea     rax, [rbp+0A0h+var_F4]
0x18008bf40  mov     [rsp+1B0h+var_168], rax
  ... truncated ...
```
