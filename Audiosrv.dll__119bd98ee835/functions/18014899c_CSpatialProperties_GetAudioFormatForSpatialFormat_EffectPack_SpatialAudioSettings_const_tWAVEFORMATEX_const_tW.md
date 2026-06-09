# CSpatialProperties::GetAudioFormatForSpatialFormat(EffectPack *,SpatialAudioSettings const *,tWAVEFORMATEX const *,tWAVEFORMATEX const *,SpatialAudioRelatedGlobalSettings *,WAVEFORMATEXTENSIBLE *,bool *)

- ea: `0x18014899c`
- end: `0x1801493fd`
- name: `?GetAudioFormatForSpatialFormat@CSpatialProperties@@QEAAJPEAVEffectPack@@PEBUSpatialAudioSettings@@PEBUtWAVEFORMATEX@@2PEAUSpatialAudioRelatedGlobalSettings@@PEAUWAVEFORMATEXTENSIBLE@@PEA_N@Z`
- size: `2657`
- prototype: `__int64 __fastcall(CSpatialProperties *__hidden this, struct EffectPack *, const struct SpatialAudioSettings *, const struct tWAVEFORMATEX *, const struct tWAVEFORMATEX *, struct SpatialAudioRelatedGlobalSettings *, struct WAVEFORMATEXTENSIBLE *, bool *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180142de4`

## callees

- `0x180002b20`
- `0x1800039e4`
- `0x1800067dc`
- `0x18000726c`
- `0x18000743c`
- `0x180008a2c`
- `0x18001280c`
- `0x1800202b0`
- `0x180044ab0`
- `0x1800469a0`
- `0x18005cfb8`
- `0x180061e64`
- `0x180062b9c`
- `0x18006300c`
- `0x180068b28`
- `0x18006de80`
- `0x1800712b8`
- `0x180072e10`
- `0x18008af54`
- `0x1800b28c0`
- `0x1800b313c`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x18014899c`
- `0x180160690`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180148a6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180148a6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801493d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801493d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180148de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180148e25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180148de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180148e25`

## string_xrefs

- `0x180148a15`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x180148db6`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x180148f09`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x180148fdb`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x18014905d`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x1801490eb`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x180149159`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x1801491ca`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`
- `0x1801493bb`: `avcore\audiocore\server\lib\audioserviceutil\spatialproperties.cpp`

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
        (unsigned int)&word_1801AC08E,
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
            (unsigned int)byte_1801ABF51,
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
            (unsigned int)&word_1801ABF06,
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
              (unsigned int)byte_1801ABDA1,
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
              (unsigned int)byte_1801ABD4B,
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
              (unsigned int)word_1801ABE3A,
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
                (unsigned int)&byte_1801ABB67,
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
              (unsigned int)&byte_1801ABDF7,
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
            (unsigned int)&byte_1801AC047,
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
          (unsigned int)byte_1801ABEBD,
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
        (unsigned int)byte_1801ABE7B,
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
0x18014899c  push    rbp
0x18014899e  push    rbx
0x18014899f  push    rsi
0x1801489a0  push    rdi
0x1801489a1  push    r12
0x1801489a3  push    r13
0x1801489a5  push    r14
0x1801489a7  push    r15
0x1801489a9  lea     rbp, [rsp-1E38h]
0x1801489b1  mov     eax, 1F78h
0x1801489b6  call    _alloca_probe
0x1801489bb  sub     rsp, rax
0x1801489be  mov     rax, cs:__security_cookie
0x1801489c5  xor     rax, rsp
0x1801489c8  mov     [rbp+1E70h+var_50], rax
0x1801489cf  mov     r12, r9
0x1801489d2  mov     rbx, r8
0x1801489d5  mov     qword ptr [rbp+1E70h+var_1EC8], rbx
0x1801489d9  mov     [rbp+1E70h+var_1E78], rdx
0x1801489dd  mov     rdi, rcx
0x1801489e0  mov     r13, [rbp+1E70h+arg_20]
0x1801489e7  mov     rsi, [rbp+1E70h+arg_30]
0x1801489ee  mov     rax, [rbp+1E70h+arg_38]
0x1801489f5  mov     [rbp+1E70h+var_1E70], rax
0x1801489f9  xor     r14d, r14d
0x1801489fc  test    rax, rax
0x1801489ff  jnz     short loc_180148A26
0x180148a01  mov     edx, 0A5Bh; void *
0x180148a06  mov     ebx, 80004003h
0x180148a0b  mov     rcx, [rbp+1E78h]; this
0x180148a12  mov     r9d, ebx; char *
0x180148a15  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\server\\lib\\audiose"...
0x180148a1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148a21  jmp     loc_1801493D8
0x180148a26  mov     [rax], r14b
0x180148a29  test    rsi, rsi
0x180148a2c  jnz     short loc_180148A35
0x180148a2e  mov     edx, 0A5Dh
0x180148a33  jmp     short loc_180148A06
0x180148a35  xorps   xmm0, xmm0
0x180148a38  xor     eax, eax
0x180148a3a  movups  xmmword ptr [rsi], xmm0
0x180148a3d  movups  xmmword ptr [rsi+10h], xmm0
0x180148a41  mov     [rsi+20h], rax
0x180148a45  test    rbx, rbx
0x180148a48  jnz     short loc_180148A51
0x180148a4a  mov     edx, 0A62h
0x180148a4f  jmp     short loc_180148A06
0x180148a51  test    r13, r13
0x180148a54  jnz     short loc_180148A5D
0x180148a56  mov     edx, 0A63h
0x180148a5b  jmp     short loc_180148A06
0x180148a5d  cmp     [rbp+1E70h+arg_28], r14
0x180148a64  jnz     short loc_180148A6D
0x180148a66  mov     edx, 0A64h
0x180148a6b  jmp     short loc_180148A06
0x180148a6d  call    cs:__imp_EnterCriticalSection
0x180148a73  mov     qword ptr [rbp+1E70h+var_1E10], rdi
0x180148a77  mov     rax, [rdi+28h]
0x180148a7b  test    rax, rax
0x180148a7e  jz      loc_1801493AE
0x180148a84  cmp     [rdi+40h], r14
0x180148a88  jz      loc_1801493AE
0x180148a8e  cmp     cs:?g_ListOfSpatialTech@@3VCSpatialAudioTechnologies@@A, 9; CSpatialAudioTechnologies g_ListOfSpatialTech
0x180148a95  jbe     short loc_180148AA1
0x180148a97  mov     edx, 0A69h
0x180148a9c  jmp     loc_1801493B3
0x180148aa1  mov     r14, [rax+30h]
0x180148aa5  mov     byte ptr [rdi+5Bh], 1
0x180148aa9  xor     edx, edx; Val
0x180148aab  lea     r8d, [rdx+48h]; Size
0x180148aaf  lea     rcx, [rbp+1E70h+var_1E00]; void *
0x180148ab3  call    memset_0
0x180148ab8  mov     eax, [rbx]
0x180148aba  mov     [rbp+1E70h+var_1E00], eax
0x180148abd  lea     r15, [rbx+0Ch]
0x180148ac1  movups  xmm0, xmmword ptr [r15]
0x180148ac5  movdqu  [rbp+1E70h+var_1DF4], xmm0
0x180148aca  movdqu  [rbp+1E70h+var_1DE4], xmm0
0x180148ad2  mov     eax, [rbx+44h]
0x180148ad5  mov     [rbp+1E70h+var_1DBC], eax
0x180148adb  mov     rcx, [rdi+28h]; this
0x180148adf  call    ?FormFactor@CEndpointCharacteristics@@QEAA?AW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0003@@XZ; CEndpointCharacteristics::FormFactor(void)
0x180148ae4  mov     [rbp+1E70h+var_1EE0], eax
0x180148ae7  call    BlockSpatialAudioRegistryGates
0x180148aec  mov     [rbp+1E70h+var_1E88], eax
0x180148aef  mov     rcx, cs:?s_exclusiveModeListener@CSpatialProperties@@0V?$com_ptr_t@VCExclusiveModeListener@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<CExclusiveModeListener,wil::err_returncode_policy> CSpatialProperties::s_exclusiveModeListener
0x180148af6  call    GetSpatialRendererSelectionMode
0x180148afb  mov     r10d, eax
0x180148afe  mov     [rbp+1E70h+var_1E84], eax
0x180148b01  mov     rdx, r12; struct tWAVEFORMATEX *
0x180148b04  lea     rcx, [rbp+1E70h+var_1E50]; this
0x180148b08  call    ??0AudioFormatForLogging@@QEAA@PEBUtWAVEFORMATEX@@@Z; AudioFormatForLogging::AudioFormatForLogging(tWAVEFORMATEX const *)
0x180148b0d  mov     rdx, r13; struct tWAVEFORMATEX *
0x180148b10  lea     rcx, [rbp+1E70h+var_1E30]; this
0x180148b14  call    ??0AudioFormatForLogging@@QEAA@PEBUtWAVEFORMATEX@@@Z; AudioFormatForLogging::AudioFormatForLogging(tWAVEFORMATEX const *)
0x180148b19  mov     r8, [rdi+30h]
0x180148b1d  mov     ecx, [r8]
0x180148b20  cmp     ecx, 4
0x180148b23  jbe     loc_180148C90
0x180148b29  mov     edx, 10h
0x180148b2e  mov     rcx, r8
0x180148b31  call    _tlgKeywordOn
0x180148b36  test    al, al
0x180148b38  jz      loc_180148C90
0x180148b3e  movzx   eax, [rbp+1E70h+var_1E26]
0x180148b42  mov     [rbp+1E70h+var_1EA0], ax
0x180148b46  movzx   eax, [rbp+1E70h+var_1E28]
0x180148b4a  mov     [rbp+1E70h+var_1E9E], ax
0x180148b4e  lea     rax, [rbp+1E70h+var_1E24]
0x180148b52  mov     [rbp+1E70h+var_1E68], rax
0x180148b56  mov     eax, [rbp+1E70h+var_1E2C]
0x180148b59  mov     [rbp+1E70h+var_1E80], eax
0x180148b5c  mov     eax, [rbp+1E70h+var_1E14]
0x180148b5f  mov     [rbp+1E70h+var_1E7C], eax
0x180148b62  movzx   eax, [rbp+1E70h+var_1E30]
0x180148b66  mov     [rbp+1E70h+var_1E9C], ax
0x180148b6a  movzx   eax, [rbp+1E70h+var_1E46]
0x180148b6e  mov     [rbp+1E70h+var_1E9A], ax
0x180148b72  movzx   eax, [rbp+1E70h+var_1E48]
0x180148b76  mov     [rbp+1E70h+var_1E98], ax
0x180148b7a  lea     rax, [rbp+1E70h+var_1E44]
0x180148b7e  mov     [rbp+1E70h+var_1E60], rax
0x180148b82  mov     eax, [rbp+1E70h+var_1E4C]
0x180148b85  mov     dword ptr [rbp+1E70h+var_1ED8], eax
0x180148b88  mov     eax, [rbp+1E70h+var_1E34]
0x180148b8b  mov     [rbp+1E70h+var_1E94], eax
0x180148b8e  movzx   eax, [rbp+1E70h+var_1E50]
0x180148b92  mov     word ptr [rbp+1E70h+var_1ED0], ax
0x180148b96  mov     eax, [rbp+1E70h+var_1EE0]
0x180148b99  mov     [rbp+1E70h+var_1EE6], ax
0x180148b9d  mov     [rbp+1E70h+var_1EE4], r10w
0x180148ba2  movzx   eax, word ptr [rbx+44h]
0x180148ba6  mov     word ptr [rbp+1E70h+var_1EE0], ax
0x180148baa  mov     qword ptr [rbp+1E70h+var_1E90], r15
0x180148bae  mov     al, [rbx]
0x180148bb0  mov     [rbp+1E70h+var_1EE8], al
0x180148bb3  mov     eax, [rbp+1E70h+var_1E88]
0x180148bb6  mov     dword ptr [rbp+1E70h+pv], eax
0x180148bb9  mov     [rbp+1E70h+var_1EC0], r14
0x180148bbd  lea     rax, [rbp+1E70h+var_1EA0]
0x180148bc1  mov     [rsp+1FB0h+var_1F00], rax
0x180148bc9  lea     rax, [rbp+1E70h+var_1E9E]
0x180148bcd  mov     [rsp+1FB0h+var_1F08], rax
0x180148bd5  lea     rax, [rbp+1E70h+var_1E68]
0x180148bd9  mov     [rsp+1FB0h+var_1F10], rax
0x180148be1  lea     rax, [rbp+1E70h+var_1E80]
0x180148be5  mov     [rsp+1FB0h+var_1F18], rax
0x180148bed  lea     rax, [rbp+1E70h+var_1E7C]
0x180148bf1  mov     [rsp+1FB0h+var_1F20], rax
0x180148bf9  lea     rax, [rbp+1E70h+var_1E9C]
0x180148bfd  mov     [rsp+1FB0h+var_1F28], rax
0x180148c05  lea     rax, [rbp+1E70h+var_1E9A]
0x180148c09  mov     [rsp+1FB0h+var_1F30], rax
0x180148c11  lea     rax, [rbp+1E70h+var_1E98]
0x180148c15  mov     [rsp+1FB0h+var_1F38], rax
0x180148c1a  lea     rax, [rbp+1E70h+var_1E60]
0x180148c1e  mov     [rsp+1FB0h+var_1F40], rax
0x180148c23  lea     rax, [rbp+1E70h+var_1ED8]
0x180148c27  mov     [rsp+1FB0h+var_1F48], rax
0x180148c2c  lea     rax, [rbp+1E70h+var_1E94]
0x180148c30  mov     [rsp+1FB0h+var_1F50], rax
0x180148c35  lea     rax, [rbp+1E70h+var_1ED0]
0x180148c39  mov     [rsp+1FB0h+var_1F58], rax
0x180148c3e  lea     rax, [rbp+1E70h+var_1EE6]
0x180148c42  mov     [rsp+1FB0h+var_1F60], rax
0x180148c47  lea     rax, [rbp+1E70h+var_1EE4]
0x180148c4b  mov     [rsp+1FB0h+var_1F68], rax
0x180148c50  lea     rax, [rbp+1E70h+var_1EE0]
0x180148c54  mov     [rsp+1FB0h+var_1F70], rax
0x180148c59  lea     rax, [rbp+1E70h+var_1E90]
0x180148c5d  mov     [rsp+1FB0h+var_1F78], rax
0x180148c62  lea     rax, [rbp+1E70h+var_1EE8]
0x180148c66  mov     [rsp+1FB0h+var_1F80], rax
0x180148c6b  lea     rax, [rbp+1E70h+pv]
0x180148c6f  mov     [rsp+1FB0h+var_1F88], rax
0x180148c74  lea     rax, [rbp+1E70h+var_1EC0]
0x180148c78  mov     [rsp+1FB0h+var_1F90], rax; int
0x180148c7d  lea     rdx, word_1801AC08E
0x180148c84  mov     rcx, r8
0x180148c87  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@U5@U5@U5@U2@U2@U4@U5@U5@U5@U2@U2@U4@U5@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@77744677744677@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &)
0x180148c8c  mov     r10d, [rbp+1E70h+var_1E84]
0x180148c90  cmp     dword ptr [rbx], 0
0x180148c93  jnz     loc_180148E76
0x180148c99  mov     eax, 0FFFEh
0x180148c9e  test    r12, r12
0x180148ca1  jz      short loc_180148D03
0x180148ca3  cmp     [r12], ax
0x180148ca8  jnz     loc_180148E30
0x180148cae  lea     rcx, [r12+18h]
0x180148cb3  call    IsSpatialOnlyFormat
0x180148cb8  test    al, al
0x180148cba  jz      loc_180148E30
0x180148cc0  mov     r8, [rdi+30h]
0x180148cc4  mov     eax, [r8]
0x180148cc7  cmp     eax, 2
0x180148cca  jbe     short loc_180148CF9
0x180148ccc  mov     edx, 10h
0x180148cd1  mov     rcx, r8
0x180148cd4  call    _tlgKeywordOn
0x180148cd9  test    al, al
0x180148cdb  jz      short loc_180148CF9
0x180148cdd  mov     [rbp+1E70h+var_1EC0], r14
0x180148ce1  lea     rax, [rbp+1E70h+var_1EC0]
0x180148ce5  mov     [rsp+1FB0h+var_1F90], rax
0x180148cea  lea     rdx, byte_1801AC047
0x180148cf1  mov     rcx, r8
0x180148cf4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180148cf9  mov     edx, 0AA7h
0x180148cfe  jmp     loc_1801493A7
0x180148d03  cmp     [r13+0], ax
0x180148d08  jnz     loc_180148E30
0x180148d0e  lea     rcx, [r13+18h]
0x180148d12  call    IsSpatialOnlyFormat
0x180148d17  test    al, al
0x180148d19  jz      loc_180148E30
0x180148d1f  mov     r8, [rdi+30h]
0x180148d23  mov     eax, [r8]
0x180148d26  cmp     eax, 4
0x180148d29  jbe     short loc_180148D58
0x180148d2b  mov     edx, 10h
0x180148d30  mov     rcx, r8
0x180148d33  call    _tlgKeywordOn
0x180148d38  test    al, al
0x180148d3a  jz      short loc_180148D58
0x180148d3c  mov     [rbp+1E70h+var_1EC0], r14
0x180148d40  lea     rax, [rbp+1E70h+var_1EC0]
0x180148d44  mov     [rsp+1FB0h+var_1F90], rax
0x180148d49  lea     rdx, byte_1801ABEBD
0x180148d50  mov     rcx, r8
0x180148d53  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180148d58  mov     [rbp+1E70h+pv], 0
0x180148d60  lea     rax, [rbp+1E70h+pv]
0x180148d64  mov     [rbp+1E70h+var_1EC0], rax
0x180148d68  mov     [rbp+1E70h+var_1EC0+8], 0
0x180148d70  mov     byte ptr [rbp+1E70h+var_1EB0], 1
0x180148d74  mov     [rsp+1FB0h+var_1F80], 0; pv
0x180148d7d  mov     [rsp+1FB0h+var_1F88], 0; unsigned int *
0x180148d86  mov     [rsp+1FB0h+var_1F90], 0; int
0x180148d8f  lea     r9, [rbp+1E70h+var_1EC0+8]; struct tWAVEFORMATEX **
0x180148d93  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180148d95  lea     r8d, [rdx+1]; int
0x180148d99  mov     rcx, [rbp+1E70h+var_1E78]; this
0x180148d9d  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x180148da2  mov     ebx, eax
0x180148da4  lea     rcx, [rbp+1E70h+var_1EC0]
0x180148da8  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180148dad  test    ebx, ebx
0x180148daf  jns     short loc_180148DED
0x180148db1  mov     edx, 0AB4h; void *
0x180148db6  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\server\\lib\\audiose"...
0x180148dbd  mov     r9d, ebx; char *
0x180148dc0  mov     rcx, [rbp+1E78h]; this
0x180148dc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148dcc  nop
0x180148dcd  mov     rcx, [rbp+1E70h+pv]; pv
0x180148dd1  mov     [rbp+1E70h+pv], 0
0x180148dd9  test    rcx, rcx
0x180148ddc  jz      loc_1801493CF
0x180148de2  call    cs:__imp_CoTaskMemFree
0x180148de8  jmp     loc_1801493CF
0x180148ded  mov     rdx, [rbp+1E70h+pv]; struct tWAVEFORMATEX *
0x180148df1  mov     rcx, rsi; struct WAVEFORMATEXTENSIBLE *
0x180148df4  call    ?CopyToWaveFormatExtensible@@YAHPEAUWAVEFORMATEXTENSIBLE@@PEBUtWAVEFORMATEX@@@Z; CopyToWaveFormatExtensible(WAVEFORMATEXTENSIBLE *,tWAVEFORMATEX const *)
0x180148df9  test    eax, eax
0x180148dfb  jnz     short loc_180148E09
0x180148dfd  mov     ebx, 8000FFFFh
0x180148e02  mov     edx, 0AB5h
0x180148e07  jmp     short loc_180148DB6
0x180148e09  mov     rax, [rbp+1E70h+var_1E70]
0x180148e0d  mov     byte ptr [rax], 1
0x180148e10  mov     rcx, [rbp+1E70h+pv]; pv
0x180148e14  mov     [rbp+1E70h+pv], 0
0x180148e1c  test    rcx, rcx
0x180148e1f  jz      loc_18014932C
0x180148e25  call    cs:__imp_CoTaskMemFree
0x180148e2b  jmp     loc_18014932C
0x180148e30  mov     r8, [rdi+30h]
0x180148e34  mov     eax, [r8]
0x180148e37  cmp     eax, 4
0x180148e3a  jbe     loc_18014932C
0x180148e40  mov     edx, 10h
0x180148e45  mov     rcx, r8
0x180148e48  call    _tlgKeywordOn
0x180148e4d  test    al, al
0x180148e4f  jz      loc_18014932C
0x180148e55  mov     [rbp+1E70h+var_1EC0], r14
0x180148e59  lea     rax, [rbp+1E70h+var_1EC0]
0x180148e5d  mov     [rsp+1FB0h+var_1F90], rax
0x180148e62  lea     rdx, byte_1801ABE7B
0x180148e69  mov     rcx, r8
0x180148e6c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180148e71  jmp     loc_18014932C
0x180148e76  lea     r8, [rbp+1E70h+var_1E00]
0x180148e7a  mov     edx, r10d
0x180148e7d  lea     rcx, [rbp+1E70h+var_1EC0]
0x180148e81  call    GetPreferredSpatialAudioEncoderId
0x180148e86  movups  xmm1, xmmword ptr [rax]
0x180148e89  movq    rax, xmm1
0x180148e8e  cmp     rax, [r15]
  ... truncated ...
```
