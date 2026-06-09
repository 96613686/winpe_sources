# CSpatialProperties::GetAudioFormatForSpatialFormat(EffectPack *,SpatialAudioSettings const *,tWAVEFORMATEX const *,tWAVEFORMATEX const *,SpatialAudioRelatedGlobalSettings *,WAVEFORMATEXTENSIBLE *,bool *)

- ea: `0x180147c8c`
- end: `0x1801486ed`
- name: `?GetAudioFormatForSpatialFormat@CSpatialProperties@@QEAAJPEAVEffectPack@@PEBUSpatialAudioSettings@@PEBUtWAVEFORMATEX@@2PEAUSpatialAudioRelatedGlobalSettings@@PEAUWAVEFORMATEXTENSIBLE@@PEA_N@Z`
- size: `2657`
- prototype: `__int64 __fastcall(CSpatialProperties *__hidden this, struct EffectPack *, const struct SpatialAudioSettings *, const struct tWAVEFORMATEX *, const struct tWAVEFORMATEX *, struct SpatialAudioRelatedGlobalSettings *, struct WAVEFORMATEXTENSIBLE *, bool *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801424d4`

## callees

- `0x180002914`
- `0x1800037d8`
- `0x1800065d0`
- `0x180007128`
- `0x1800072f8`
- `0x1800088dc`
- `0x1800126bc`
- `0x180020160`
- `0x180044f40`
- `0x180046e30`
- `0x18005d448`
- `0x1800622f4`
- `0x18006302c`
- `0x18006349c`
- `0x180068fb8`
- `0x18006e310`
- `0x1800717b8`
- `0x180073310`
- `0x18008aea8`
- `0x1800b45b0`
- `0x1800b4e2c`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x180147c8c`
- `0x18015f980`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180147d5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180147d5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801486c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801486c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801480d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180148115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801480d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180148115`

## string_xrefs

- `0x180147d05`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x1801480a6`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x1801481f9`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x1801482cb`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x18014834d`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x1801483db`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x180148449`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x1801484ba`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x1801486ab`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSpatialProperties::GetAudioFormatForSpatialFormat(
        CSpatialProperties *this,
        struct EffectPack *a2,
        const struct SpatialAudioSettings *a3,
        const struct tWAVEFORMATEX *a4,
        const struct tWAVEFORMATEX *a5,
        struct SpatialAudioRelatedGlobalSettings *a6,
        struct WAVEFORMATEXTENSIBLE *a7,
        bool *a8)
{
  int v11; // r13d
  __int64 v12; // rdx
  unsigned int DeviceFormatAndSpatialSettings; // ebx
  __int64 v14; // rax
  __int64 v15; // rdx
  struct tWAVEFORMATEX *v16; // r14
  struct tWAVEFORMATEX *v17; // r15
  unsigned int v18; // r10d
  int v19; // r8d
  int v20; // r9d
  int v21; // r8d
  int v22; // r9d
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rdx
  void *v26; // rcx
  void *v27; // rcx
  int v28; // r8d
  int v29; // r9d
  __m128i *PreferredSpatialAudioEncoderId; // rax
  __int64 v31; // r8
  int AsUInt32With; // eax
  int v33; // ebx
  int v34; // r8d
  int v35; // r9d
  __int64 v36; // r8
  int v37; // r8d
  int v38; // r9d
  int v39; // r8d
  int v40; // r9d
  int v41; // r8d
  int v42; // r9d
  int v43; // r8d
  int v44; // r9d
  WORD v45; // ax
  DWORD v46; // edx
  WORD v47; // cx
  int v48; // eax
  int v49; // r8d
  int v50; // r9d
  unsigned int v51; // r10d
  int v52; // r8d
  int v53; // r9d
  int v55; // [rsp+20h] [rbp-120h]
  int v56; // [rsp+20h] [rbp-120h]
  int v57; // [rsp+20h] [rbp-120h]
  LPVOID pv; // [rsp+C0h] [rbp-80h] BYREF
  _BYTE v59[2]; // [rsp+C8h] [rbp-78h] BYREF
  __int16 v60; // [rsp+CAh] [rbp-76h] BYREF
  _WORD v61[2]; // [rsp+CCh] [rbp-74h] BYREF
  enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0003 v62; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v63; // [rsp+D8h] [rbp-68h] BYREF
  int v64; // [rsp+E0h] [rbp-60h] BYREF
  int v65[2]; // [rsp+E8h] [rbp-58h] BYREF
  struct tWAVEFORMATEX *v66[2]; // [rsp+F0h] [rbp-50h] BYREF
  int v67; // [rsp+100h] [rbp-40h]
  __int16 v68; // [rsp+110h] [rbp-30h] BYREF
  __int16 v69; // [rsp+112h] [rbp-2Eh] BYREF
  __int16 v70; // [rsp+114h] [rbp-2Ch] BYREF
  __int16 v71; // [rsp+116h] [rbp-2Ah] BYREF
  _WORD v72[2]; // [rsp+118h] [rbp-28h] BYREF
  int v73; // [rsp+11Ch] [rbp-24h] BYREF
  int v74[2]; // [rsp+120h] [rbp-20h] BYREF
  int v75; // [rsp+128h] [rbp-18h]
  unsigned int SpatialRendererSelectionMode; // [rsp+12Ch] [rbp-14h]
  int v77; // [rsp+130h] [rbp-10h] BYREF
  int v78; // [rsp+134h] [rbp-Ch] BYREF
  EffectPack *v79; // [rsp+138h] [rbp-8h]
  bool *v80; // [rsp+140h] [rbp+0h]
  char *v81; // [rsp+148h] [rbp+8h] BYREF
  _QWORD v82[2]; // [rsp+150h] [rbp+10h] BYREF
  _WORD v83[2]; // [rsp+160h] [rbp+20h] BYREF
  int v84; // [rsp+164h] [rbp+24h]
  __int16 v85; // [rsp+168h] [rbp+28h]
  __int16 v86; // [rsp+16Ah] [rbp+2Ah]
  _BYTE v87[16]; // [rsp+16Ch] [rbp+2Ch] BYREF
  int v88; // [rsp+17Ch] [rbp+3Ch]
  _WORD v89[2]; // [rsp+180h] [rbp+40h] BYREF
  int v90; // [rsp+184h] [rbp+44h]
  __int16 v91; // [rsp+188h] [rbp+48h]
  __int16 v92; // [rsp+18Ah] [rbp+4Ah]
  char v93; // [rsp+18Ch] [rbp+4Ch] BYREF
  int v94; // [rsp+19Ch] [rbp+5Ch]
  __int128 v95; // [rsp+1A0h] [rbp+60h] BYREF
  _DWORD v96[3]; // [rsp+1B0h] [rbp+70h] BYREF
  __int128 v97; // [rsp+1BCh] [rbp+7Ch]
  __int128 v98; // [rsp+1CCh] [rbp+8Ch]
  int v99; // [rsp+1F4h] [rbp+B4h]
  _BYTE v100[7520]; // [rsp+200h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1FB8h] [rbp+1E78h]

  *(_QWORD *)v65 = a3;
  v79 = a2;
  v11 = (int)a5;
  v80 = a8;
  if ( a8 )
  {
    *a8 = 0;
    if ( !a7 )
    {
      v12 = 2653;
      goto LABEL_3;
    }
    *(_OWORD *)&a7->Format.wFormatTag = 0;
    *(_OWORD *)&a7->Format.cbSize = 0;
    *(_QWORD *)a7->SubFormat.Data4 = 0;
    if ( !a3 )
    {
      v12 = 2658;
      goto LABEL_3;
    }
    if ( !a5 )
    {
      v12 = 2659;
      goto LABEL_3;
    }
    if ( !a6 )
    {
      v12 = 2660;
      goto LABEL_3;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    *(_QWORD *)&v95 = this;
    v14 = *((_QWORD *)this + 5);
    if ( !v14 || !*((_QWORD *)this + 8) )
    {
      v15 = 2664;
      goto LABEL_94;
    }
    if ( (unsigned __int8)g_ListOfSpatialTech > 9u )
    {
      v15 = 2665;
LABEL_94:
      DeviceFormatAndSpatialSettings = -2147418113;
      goto LABEL_95;
    }
    v16 = *(struct tWAVEFORMATEX **)(v14 + 48);
    *((_BYTE *)this + 91) = 1;
    memset_0(v96, 0, 0x48u);
    v96[0] = *(_DWORD *)a3;
    v17 = (struct tWAVEFORMATEX *)((char *)a3 + 12);
    v97 = *(_OWORD *)((char *)a3 + 12);
    v98 = v97;
    v99 = *((_DWORD *)a3 + 17);
    v62 = CEndpointCharacteristics::FormFactor(*((CEndpointCharacteristics **)this + 5));
    v75 = BlockSpatialAudioRegistryGates();
    SpatialRendererSelectionMode = GetSpatialRendererSelectionMode(CSpatialProperties::s_exclusiveModeListener);
    AudioFormatForLogging::AudioFormatForLogging((AudioFormatForLogging *)v83, a4);
    AudioFormatForLogging::AudioFormatForLogging((AudioFormatForLogging *)v89, a5);
    if ( **((_DWORD **)this + 6) > 4u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
    {
      v68 = v92;
      v69 = v91;
      v81 = &v93;
      v77 = v90;
      v78 = v94;
      v70 = v89[0];
      v71 = v86;
      v72[0] = v85;
      v82[0] = v87;
      LODWORD(v63) = v84;
      v73 = v88;
      LOWORD(v64) = v83[0];
      v60 = v62;
      v61[0] = v18;
      LOWORD(v62) = *((_WORD *)a3 + 34);
      *(_QWORD *)v74 = (char *)a3 + 12;
      v59[0] = *(_BYTE *)a3;
      LODWORD(pv) = v75;
      v66[0] = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
        v19,
        (unsigned int)&unk_1801AAD33,
        v19,
        v20,
        (__int64)v66,
        (__int64)&pv,
        (__int64)v59,
        (__int64)v74,
        (__int64)&v62,
        (__int64)v61,
        (__int64)&v60,
        (__int64)&v64,
        (__int64)&v73,
        (__int64)&v63,
        (__int64)v82,
        (__int64)v72,
        (__int64)&v71,
        (__int64)&v70,
        (__int64)&v78,
        (__int64)&v77,
        (__int64)&v81,
        (__int64)&v69,
        (__int64)&v68);
      v18 = SpatialRendererSelectionMode;
    }
    if ( *(_DWORD *)a3 )
    {
      PreferredSpatialAudioEncoderId = (__m128i *)GetPreferredSpatialAudioEncoderId(v66, v18, v96);
      if ( PreferredSpatialAudioEncoderId->m128i_i64[0] != *(_QWORD *)&v17->wFormatTag
        || _mm_srli_si128(*PreferredSpatialAudioEncoderId, 8).m128i_u64[0] != *(_QWORD *)((char *)a3 + 20) )
      {
        if ( **((_DWORD **)this + 6) > 4u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
        {
          v95 = *(_OWORD *)GetPreferredSpatialAudioEncoderId(v82, v51, v96);
          *(_QWORD *)v65 = &v95;
          v66[0] = (struct tWAVEFORMATEX *)((char *)a3 + 12);
          *(_QWORD *)v74 = v16;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
            v53,
            (unsigned int)&unk_1801AABE2,
            v52,
            v53,
            (__int64)v74,
            (__int64)v66,
            (__int64)v65);
        }
        v15 = 2763;
        goto LABEL_92;
      }
      memset_0(v100, 0, 0x1D52u);
      v64 = 2;
      CPropertyStoreHelper::CPropertyStoreHelper((CPropertyStoreHelper *)&v63, *((struct IPropertyStore **)this + 7));
      *(_OWORD *)v66 = PKEY_Endpoint_PreferedPcmChannelCountForHrtf;
      v67 = 2;
      AsUInt32With = CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32WithDefault<_tagpropertykey>(
                       &v63,
                       v66,
                       v31,
                       &v64);
      DeviceFormatAndSpatialSettings = AsUInt32With;
      if ( AsUInt32With < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD6,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
          (const char *)(unsigned int)AsUInt32With,
          v55);
        if ( v63 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        goto LABEL_96;
      }
      memset(&pv, 9, 5);
      if ( a4 )
        v11 = 0;
      v33 = v75;
      v57 = v11;
      CSpatialProperties::EnumerateSpatialEncoders(this, v79, v96, SpatialRendererSelectionMode);
      if ( BYTE1(pv) == 9 )
      {
        if ( **((_DWORD **)this + 6) > 2u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
        {
          v66[0] = v17;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
            v34,
            (unsigned int)&unk_1801AACE8,
            v34,
            v35,
            (__int64)v66);
        }
        DeviceFormatAndSpatialSettings = -2147024846;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAE6,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
          (const char *)0x80070032LL,
          v57);
      }
      else
      {
        v36 = 834LL * BYTE1(pv);
        if ( !*(_DWORD *)&v100[v36 + 784] )
        {
          if ( **((_DWORD **)this + 6) > 2u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
          {
            v66[0] = v17;
            *(_QWORD *)v74 = v16;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
              v37,
              (unsigned int)&unk_1801AAC92,
              v37,
              v38,
              (__int64)v74,
              (__int64)v66);
          }
          DeviceFormatAndSpatialSettings = -2147009035;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAF4,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
            (const char *)0x80073DF5LL,
            v57);
          if ( v63 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
          goto LABEL_96;
        }
        if ( *(_BYTE *)a6 )
        {
          if ( **((_DWORD **)this + 6) > 2u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
          {
            v66[0] = v17;
            *(_QWORD *)v74 = v16;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
              v39,
              (unsigned int)&unk_1801AAAC2,
              v39,
              v40,
              (__int64)v74,
              (__int64)v66);
          }
          DeviceFormatAndSpatialSettings = -2147024846;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB00,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
            (const char *)0x80070032LL,
            v57);
        }
        else if ( *(_DWORD *)(*(_QWORD *)v65 + 68LL) == 1 && (v33 & 4) != 0 )
        {
          if ( **((_DWORD **)this + 6) > 2u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
          {
            *(_QWORD *)v65 = v16;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              v41,
              (unsigned int)&unk_1801AAA81,
              v41,
              v42,
              (__int64)v65);
          }
          DeviceFormatAndSpatialSettings = -2147024846;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB0C,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
            (const char *)0x80070032LL,
            v57);
        }
        else
        {
          if ( (v33 & 1) == 0 )
          {
            a7->Format.wFormatTag = -2;
            v45 = *(_WORD *)&v100[v36 + 828];
            a7->Format.nChannels = v45;
            v46 = *(_DWORD *)&v100[v36 + 804];
            a7->Format.nSamplesPerSec = v46;
            v47 = *(_WORD *)&v100[v36 + 830];
            a7->Format.wBitsPerSample = v47;
            v48 = (unsigned __int16)(v45 * (v47 >> 3));
            a7->Format.nBlockAlign = v48;
            a7->Format.nAvgBytesPerSec = v46 * v48;
            a7->Format.cbSize = 22;
            a7->dwChannelMask = *(_DWORD *)&v100[v36 + 808];
            a7->SubFormat = *(GUID *)&v100[v36 + 812];
            a7->Samples.wValidBitsPerSample = *(_WORD *)&v100[v36 + 832];
            AudioFormatForLogging::AudioFormatForLogging((AudioFormatForLogging *)v83, &a7->Format);
            if ( **((_DWORD **)this + 6) > 4u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
            {
              LOWORD(v62) = v86;
              v61[0] = v85;
              *(_QWORD *)v65 = v87;
              LODWORD(pv) = v84;
              v73 = v88;
              v60 = v83[0];
              v66[0] = v16;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
                v49,
                (unsigned int)&unk_1801AAB18,
                v49,
                v50,
                (__int64)v66,
                (__int64)&v60,
                (__int64)&v73,
                (__int64)&pv,
                (__int64)v65,
                (__int64)v61,
                (__int64)&v62);
            }
            *v80 = 1;
            if ( v63 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
            goto LABEL_87;
          }
          if ( **((_DWORD **)this + 6) > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
          {
            LODWORD(pv) = v33;
            *(_QWORD *)v65 = v16;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              v43,
              (unsigned int)&unk_1801AAB9F,
              v43,
              v44,
              (__int64)v65,
              (__int64)&pv);
          }
          DeviceFormatAndSpatialSettings = -2147024846;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB17,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
            (const char *)0x80070032LL,
            v57);
        }
      }
      if ( v63 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      goto LABEL_96;
    }
    if ( a4 )
    {
      if ( a4->wFormatTag == 0xFFFE && (unsigned __int8)IsSpatialOnlyFormat((char *)&a4[1].nSamplesPerSec + 2) )
      {
        if ( **((_DWORD **)this + 6) > 2u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
        {
          v66[0] = v16;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v21,
            (unsigned int)&unk_1801AAF6E,
            v21,
            v22,
            (__int64)v66);
        }
        v15 = 2727;
LABEL_92:
        DeviceFormatAndSpatialSettings = -2147024846;
LABEL_95:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
          (const char *)DeviceFormatAndSpatialSettings,
          v55);
        goto LABEL_96;
      }
    }
    else if ( a5->wFormatTag == 0xFFFE && (unsigned __int8)IsSpatialOnlyFormat((char *)&a5[1].nSamplesPerSec + 2) )
    {
      if ( **((_DWORD **)this + 6) > 4u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
      {
        v66[0] = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v23,
          (unsigned int)&unk_1801AAF25,
          v23,
          v24,
          (__int64)v66);
      }
      pv = 0;
      v66[0] = (struct tWAVEFORMATEX *)&pv;
      v66[1] = 0;
      LOBYTE(v67) = 1;
      DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                         (CEndpointCharacteristics **)v79,
                                         eHostProcessConnector,
                                         1,
                                         &v66[1],
                                         0,
                                         0,
                                         0);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v66);
      if ( (DeviceFormatAndSpatialSettings & 0x80000000) == 0 )
      {
        if ( (unsigned int)CopyToWaveFormatExtensible(a7, (const struct tWAVEFORMATEX *)pv) )
        {
          *v80 = 1;
          v27 = pv;
          pv = 0;
          if ( v27 )
            CoTaskMemFree(v27);
          goto LABEL_87;
        }
        DeviceFormatAndSpatialSettings = -2147418113;
        v25 = 2741;
      }
      else
      {
        v25 = 2740;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
        (const char *)DeviceFormatAndSpatialSettings,
        v56);
      v26 = pv;
      pv = 0;
      if ( v26 )
        CoTaskMemFree(v26);
      goto LABEL_96;
    }
    if ( **((_DWORD **)this + 6) > 4u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 6), 16) )
    {
      v66[0] = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v28,
        (unsigned int)&unk_1801AAC50,
        v28,
        v29,
        (__int64)v66);
    }
LABEL_87:
    DeviceFormatAndSpatialSettings = 0;
LABEL_96:
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    return DeviceFormatAndSpatialSettings;
  }
  v12 = 2651;
LABEL_3:
  DeviceFormatAndSpatialSettings = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\spatialproperties.cpp",
    (const char *)0x80004003LL,
    v55);
  return DeviceFormatAndSpatialSettings;
}

```

## disassembly

```asm
0x180147c8c  push    rbp
0x180147c8e  push    rbx
0x180147c8f  push    rsi
0x180147c90  push    rdi
0x180147c91  push    r12
0x180147c93  push    r13
0x180147c95  push    r14
0x180147c97  push    r15
0x180147c99  lea     rbp, [rsp-1E38h]
0x180147ca1  mov     eax, 1F78h
0x180147ca6  call    _alloca_probe
0x180147cab  sub     rsp, rax
0x180147cae  mov     rax, cs:__security_cookie
0x180147cb5  xor     rax, rsp
0x180147cb8  mov     [rbp+1E70h+var_50], rax
0x180147cbf  mov     r12, r9
0x180147cc2  mov     rbx, r8
0x180147cc5  mov     qword ptr [rbp+1E70h+var_1EC8], rbx
0x180147cc9  mov     [rbp+1E70h+var_1E78], rdx
0x180147ccd  mov     rdi, rcx
0x180147cd0  mov     r13, [rbp+1E70h+arg_20]
0x180147cd7  mov     rsi, [rbp+1E70h+arg_30]
0x180147cde  mov     rax, [rbp+1E70h+arg_38]
0x180147ce5  mov     [rbp+1E70h+var_1E70], rax
0x180147ce9  xor     r14d, r14d
0x180147cec  test    rax, rax
0x180147cef  jnz     short loc_180147D16
0x180147cf1  mov     edx, 0A5Bh; void *
0x180147cf6  mov     ebx, 80004003h
0x180147cfb  mov     rcx, [rbp+1E78h]; this
0x180147d02  mov     r9d, ebx; char *
0x180147d05  lea     r8, aAvcoreAudiocor_65; "avcore\\audiocore\\server\\lib\\audiose"...
0x180147d0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147d11  jmp     loc_1801486C8
0x180147d16  mov     [rax], r14b
0x180147d19  test    rsi, rsi
0x180147d1c  jnz     short loc_180147D25
0x180147d1e  mov     edx, 0A5Dh
0x180147d23  jmp     short loc_180147CF6
0x180147d25  xorps   xmm0, xmm0
0x180147d28  xor     eax, eax
0x180147d2a  movups  xmmword ptr [rsi], xmm0
0x180147d2d  movups  xmmword ptr [rsi+10h], xmm0
0x180147d31  mov     [rsi+20h], rax
0x180147d35  test    rbx, rbx
0x180147d38  jnz     short loc_180147D41
0x180147d3a  mov     edx, 0A62h
0x180147d3f  jmp     short loc_180147CF6
0x180147d41  test    r13, r13
0x180147d44  jnz     short loc_180147D4D
0x180147d46  mov     edx, 0A63h
0x180147d4b  jmp     short loc_180147CF6
0x180147d4d  cmp     [rbp+1E70h+arg_28], r14
0x180147d54  jnz     short loc_180147D5D
0x180147d56  mov     edx, 0A64h
0x180147d5b  jmp     short loc_180147CF6
0x180147d5d  call    cs:__imp_EnterCriticalSection
0x180147d63  mov     qword ptr [rbp+1E70h+var_1E10], rdi
0x180147d67  mov     rax, [rdi+28h]
0x180147d6b  test    rax, rax
0x180147d6e  jz      loc_18014869E
0x180147d74  cmp     [rdi+40h], r14
0x180147d78  jz      loc_18014869E
0x180147d7e  cmp     cs:?g_ListOfSpatialTech@@3VCSpatialAudioTechnologies@@A, 9; CSpatialAudioTechnologies g_ListOfSpatialTech
0x180147d85  jbe     short loc_180147D91
0x180147d87  mov     edx, 0A69h
0x180147d8c  jmp     loc_1801486A3
0x180147d91  mov     r14, [rax+30h]
0x180147d95  mov     byte ptr [rdi+5Bh], 1
0x180147d99  xor     edx, edx; Val
0x180147d9b  lea     r8d, [rdx+48h]; Size
0x180147d9f  lea     rcx, [rbp+1E70h+var_1E00]; void *
0x180147da3  call    memset_0
0x180147da8  mov     eax, [rbx]
0x180147daa  mov     [rbp+1E70h+var_1E00], eax
0x180147dad  lea     r15, [rbx+0Ch]
0x180147db1  movups  xmm0, xmmword ptr [r15]
0x180147db5  movdqu  [rbp+1E70h+var_1DF4], xmm0
0x180147dba  movdqu  [rbp+1E70h+var_1DE4], xmm0
0x180147dc2  mov     eax, [rbx+44h]
0x180147dc5  mov     [rbp+1E70h+var_1DBC], eax
0x180147dcb  mov     rcx, [rdi+28h]; this
0x180147dcf  call    ?FormFactor@CEndpointCharacteristics@@QEAA?AW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0003@@XZ; CEndpointCharacteristics::FormFactor(void)
0x180147dd4  mov     [rbp+1E70h+var_1EE0], eax
0x180147dd7  call    BlockSpatialAudioRegistryGates
0x180147ddc  mov     [rbp+1E70h+var_1E88], eax
0x180147ddf  mov     rcx, cs:?s_exclusiveModeListener@CSpatialProperties@@0V?$com_ptr_t@VCExclusiveModeListener@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<CExclusiveModeListener,wil::err_returncode_policy> CSpatialProperties::s_exclusiveModeListener
0x180147de6  call    GetSpatialRendererSelectionMode
0x180147deb  mov     r10d, eax
0x180147dee  mov     [rbp+1E70h+var_1E84], eax
0x180147df1  mov     rdx, r12; struct tWAVEFORMATEX *
0x180147df4  lea     rcx, [rbp+1E70h+var_1E50]; this
0x180147df8  call    ??0AudioFormatForLogging@@QEAA@PEBUtWAVEFORMATEX@@@Z; AudioFormatForLogging::AudioFormatForLogging(tWAVEFORMATEX const *)
0x180147dfd  mov     rdx, r13; struct tWAVEFORMATEX *
0x180147e00  lea     rcx, [rbp+1E70h+var_1E30]; this
0x180147e04  call    ??0AudioFormatForLogging@@QEAA@PEBUtWAVEFORMATEX@@@Z; AudioFormatForLogging::AudioFormatForLogging(tWAVEFORMATEX const *)
0x180147e09  mov     r8, [rdi+30h]
0x180147e0d  mov     ecx, [r8]
0x180147e10  cmp     ecx, 4
0x180147e13  jbe     loc_180147F80
0x180147e19  mov     edx, 10h
0x180147e1e  mov     rcx, r8
0x180147e21  call    _tlgKeywordOn
0x180147e26  test    al, al
0x180147e28  jz      loc_180147F80
0x180147e2e  movzx   eax, [rbp+1E70h+var_1E26]
0x180147e32  mov     [rbp+1E70h+var_1EA0], ax
0x180147e36  movzx   eax, [rbp+1E70h+var_1E28]
0x180147e3a  mov     [rbp+1E70h+var_1E9E], ax
0x180147e3e  lea     rax, [rbp+1E70h+var_1E24]
0x180147e42  mov     [rbp+1E70h+var_1E68], rax
0x180147e46  mov     eax, [rbp+1E70h+var_1E2C]
0x180147e49  mov     [rbp+1E70h+var_1E80], eax
0x180147e4c  mov     eax, [rbp+1E70h+var_1E14]
0x180147e4f  mov     [rbp+1E70h+var_1E7C], eax
0x180147e52  movzx   eax, [rbp+1E70h+var_1E30]
0x180147e56  mov     [rbp+1E70h+var_1E9C], ax
0x180147e5a  movzx   eax, [rbp+1E70h+var_1E46]
0x180147e5e  mov     [rbp+1E70h+var_1E9A], ax
0x180147e62  movzx   eax, [rbp+1E70h+var_1E48]
0x180147e66  mov     [rbp+1E70h+var_1E98], ax
0x180147e6a  lea     rax, [rbp+1E70h+var_1E44]
0x180147e6e  mov     [rbp+1E70h+var_1E60], rax
0x180147e72  mov     eax, [rbp+1E70h+var_1E4C]
0x180147e75  mov     dword ptr [rbp+1E70h+var_1ED8], eax
0x180147e78  mov     eax, [rbp+1E70h+var_1E34]
0x180147e7b  mov     [rbp+1E70h+var_1E94], eax
0x180147e7e  movzx   eax, [rbp+1E70h+var_1E50]
0x180147e82  mov     word ptr [rbp+1E70h+var_1ED0], ax
0x180147e86  mov     eax, [rbp+1E70h+var_1EE0]
0x180147e89  mov     [rbp+1E70h+var_1EE6], ax
0x180147e8d  mov     [rbp+1E70h+var_1EE4], r10w
0x180147e92  movzx   eax, word ptr [rbx+44h]
0x180147e96  mov     word ptr [rbp+1E70h+var_1EE0], ax
0x180147e9a  mov     qword ptr [rbp+1E70h+var_1E90], r15
0x180147e9e  mov     al, [rbx]
0x180147ea0  mov     [rbp+1E70h+var_1EE8], al
0x180147ea3  mov     eax, [rbp+1E70h+var_1E88]
0x180147ea6  mov     dword ptr [rbp+1E70h+pv], eax
0x180147ea9  mov     [rbp+1E70h+var_1EC0], r14
0x180147ead  lea     rax, [rbp+1E70h+var_1EA0]
0x180147eb1  mov     [rsp+1FB0h+var_1F00], rax
0x180147eb9  lea     rax, [rbp+1E70h+var_1E9E]
0x180147ebd  mov     [rsp+1FB0h+var_1F08], rax
0x180147ec5  lea     rax, [rbp+1E70h+var_1E68]
0x180147ec9  mov     [rsp+1FB0h+var_1F10], rax
0x180147ed1  lea     rax, [rbp+1E70h+var_1E80]
0x180147ed5  mov     [rsp+1FB0h+var_1F18], rax
0x180147edd  lea     rax, [rbp+1E70h+var_1E7C]
0x180147ee1  mov     [rsp+1FB0h+var_1F20], rax
0x180147ee9  lea     rax, [rbp+1E70h+var_1E9C]
0x180147eed  mov     [rsp+1FB0h+var_1F28], rax
0x180147ef5  lea     rax, [rbp+1E70h+var_1E9A]
0x180147ef9  mov     [rsp+1FB0h+var_1F30], rax
0x180147f01  lea     rax, [rbp+1E70h+var_1E98]
0x180147f05  mov     [rsp+1FB0h+var_1F38], rax
0x180147f0a  lea     rax, [rbp+1E70h+var_1E60]
0x180147f0e  mov     [rsp+1FB0h+var_1F40], rax
0x180147f13  lea     rax, [rbp+1E70h+var_1ED8]
0x180147f17  mov     [rsp+1FB0h+var_1F48], rax
0x180147f1c  lea     rax, [rbp+1E70h+var_1E94]
0x180147f20  mov     [rsp+1FB0h+var_1F50], rax
0x180147f25  lea     rax, [rbp+1E70h+var_1ED0]
0x180147f29  mov     [rsp+1FB0h+var_1F58], rax
0x180147f2e  lea     rax, [rbp+1E70h+var_1EE6]
0x180147f32  mov     [rsp+1FB0h+var_1F60], rax
0x180147f37  lea     rax, [rbp+1E70h+var_1EE4]
0x180147f3b  mov     [rsp+1FB0h+var_1F68], rax
0x180147f40  lea     rax, [rbp+1E70h+var_1EE0]
0x180147f44  mov     [rsp+1FB0h+var_1F70], rax
0x180147f49  lea     rax, [rbp+1E70h+var_1E90]
0x180147f4d  mov     [rsp+1FB0h+var_1F78], rax
0x180147f52  lea     rax, [rbp+1E70h+var_1EE8]
0x180147f56  mov     [rsp+1FB0h+var_1F80], rax
0x180147f5b  lea     rax, [rbp+1E70h+pv]
0x180147f5f  mov     [rsp+1FB0h+var_1F88], rax
0x180147f64  lea     rax, [rbp+1E70h+var_1EC0]
0x180147f68  mov     [rsp+1FB0h+var_1F90], rax; int
0x180147f6d  lea     rdx, unk_1801AAD33
0x180147f74  mov     rcx, r8
0x180147f77  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@U5@U5@U5@U2@U2@U4@U5@U5@U5@U2@U2@U4@U5@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@77744677744677@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &)
0x180147f7c  mov     r10d, [rbp+1E70h+var_1E84]
0x180147f80  cmp     dword ptr [rbx], 0
0x180147f83  jnz     loc_180148166
0x180147f89  mov     eax, 0FFFEh
0x180147f8e  test    r12, r12
0x180147f91  jz      short loc_180147FF3
0x180147f93  cmp     [r12], ax
0x180147f98  jnz     loc_180148120
0x180147f9e  lea     rcx, [r12+18h]
0x180147fa3  call    IsSpatialOnlyFormat
0x180147fa8  test    al, al
0x180147faa  jz      loc_180148120
0x180147fb0  mov     r8, [rdi+30h]
0x180147fb4  mov     eax, [r8]
0x180147fb7  cmp     eax, 2
0x180147fba  jbe     short loc_180147FE9
0x180147fbc  mov     edx, 10h
0x180147fc1  mov     rcx, r8
0x180147fc4  call    _tlgKeywordOn
0x180147fc9  test    al, al
0x180147fcb  jz      short loc_180147FE9
0x180147fcd  mov     [rbp+1E70h+var_1EC0], r14
0x180147fd1  lea     rax, [rbp+1E70h+var_1EC0]
0x180147fd5  mov     [rsp+1FB0h+var_1F90], rax
0x180147fda  lea     rdx, unk_1801AAF6E
0x180147fe1  mov     rcx, r8
0x180147fe4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180147fe9  mov     edx, 0AA7h
0x180147fee  jmp     loc_180148697
0x180147ff3  cmp     [r13+0], ax
0x180147ff8  jnz     loc_180148120
0x180147ffe  lea     rcx, [r13+18h]
0x180148002  call    IsSpatialOnlyFormat
0x180148007  test    al, al
0x180148009  jz      loc_180148120
0x18014800f  mov     r8, [rdi+30h]
0x180148013  mov     eax, [r8]
0x180148016  cmp     eax, 4
0x180148019  jbe     short loc_180148048
0x18014801b  mov     edx, 10h
0x180148020  mov     rcx, r8
0x180148023  call    _tlgKeywordOn
0x180148028  test    al, al
0x18014802a  jz      short loc_180148048
0x18014802c  mov     [rbp+1E70h+var_1EC0], r14
0x180148030  lea     rax, [rbp+1E70h+var_1EC0]
0x180148034  mov     [rsp+1FB0h+var_1F90], rax
0x180148039  lea     rdx, unk_1801AAF25
0x180148040  mov     rcx, r8
0x180148043  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180148048  mov     [rbp+1E70h+pv], 0
0x180148050  lea     rax, [rbp+1E70h+pv]
0x180148054  mov     [rbp+1E70h+var_1EC0], rax
0x180148058  mov     [rbp+1E70h+var_1EC0+8], 0
0x180148060  mov     byte ptr [rbp+1E70h+var_1EB0], 1
0x180148064  mov     [rsp+1FB0h+var_1F80], 0; pv
0x18014806d  mov     [rsp+1FB0h+var_1F88], 0; unsigned int *
0x180148076  mov     [rsp+1FB0h+var_1F90], 0; int
0x18014807f  lea     r9, [rbp+1E70h+var_1EC0+8]; struct tWAVEFORMATEX **
0x180148083  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180148085  lea     r8d, [rdx+1]; int
0x180148089  mov     rcx, [rbp+1E70h+var_1E78]; this
0x18014808d  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x180148092  mov     ebx, eax
0x180148094  lea     rcx, [rbp+1E70h+var_1EC0]
0x180148098  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18014809d  test    ebx, ebx
0x18014809f  jns     short loc_1801480DD
0x1801480a1  mov     edx, 0AB4h; void *
0x1801480a6  lea     r8, aAvcoreAudiocor_65; "avcore\\audiocore\\server\\lib\\audiose"...
0x1801480ad  mov     r9d, ebx; char *
0x1801480b0  mov     rcx, [rbp+1E78h]; this
0x1801480b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801480bc  nop
0x1801480bd  mov     rcx, [rbp+1E70h+pv]; pv
0x1801480c1  mov     [rbp+1E70h+pv], 0
0x1801480c9  test    rcx, rcx
0x1801480cc  jz      loc_1801486BF
0x1801480d2  call    cs:__imp_CoTaskMemFree
0x1801480d8  jmp     loc_1801486BF
0x1801480dd  mov     rdx, [rbp+1E70h+pv]; struct tWAVEFORMATEX *
0x1801480e1  mov     rcx, rsi; struct WAVEFORMATEXTENSIBLE *
0x1801480e4  call    ?CopyToWaveFormatExtensible@@YAHPEAUWAVEFORMATEXTENSIBLE@@PEBUtWAVEFORMATEX@@@Z; CopyToWaveFormatExtensible(WAVEFORMATEXTENSIBLE *,tWAVEFORMATEX const *)
0x1801480e9  test    eax, eax
0x1801480eb  jnz     short loc_1801480F9
0x1801480ed  mov     ebx, 8000FFFFh
0x1801480f2  mov     edx, 0AB5h
0x1801480f7  jmp     short loc_1801480A6
0x1801480f9  mov     rax, [rbp+1E70h+var_1E70]
0x1801480fd  mov     byte ptr [rax], 1
0x180148100  mov     rcx, [rbp+1E70h+pv]; pv
0x180148104  mov     [rbp+1E70h+pv], 0
0x18014810c  test    rcx, rcx
0x18014810f  jz      loc_18014861C
0x180148115  call    cs:__imp_CoTaskMemFree
0x18014811b  jmp     loc_18014861C
0x180148120  mov     r8, [rdi+30h]
0x180148124  mov     eax, [r8]
0x180148127  cmp     eax, 4
0x18014812a  jbe     loc_18014861C
0x180148130  mov     edx, 10h
0x180148135  mov     rcx, r8
0x180148138  call    _tlgKeywordOn
0x18014813d  test    al, al
0x18014813f  jz      loc_18014861C
0x180148145  mov     [rbp+1E70h+var_1EC0], r14
0x180148149  lea     rax, [rbp+1E70h+var_1EC0]
0x18014814d  mov     [rsp+1FB0h+var_1F90], rax
0x180148152  lea     rdx, unk_1801AAC50
0x180148159  mov     rcx, r8
0x18014815c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180148161  jmp     loc_18014861C
0x180148166  lea     r8, [rbp+1E70h+var_1E00]
0x18014816a  mov     edx, r10d
0x18014816d  lea     rcx, [rbp+1E70h+var_1EC0]
0x180148171  call    GetPreferredSpatialAudioEncoderId
0x180148176  movups  xmm1, xmmword ptr [rax]
0x180148179  movq    rax, xmm1
0x18014817e  cmp     rax, [r15]
  ... truncated ...
```
