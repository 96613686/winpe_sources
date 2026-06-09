# CStartAPJob::QueryNextCommandInfo(ulong,void * *,_WFC_DEVICE_COMMAND_TYPE *,uint *,ulong *,uchar * *)

- ea: `0x1400d0460`
- end: `0x1400d0eda`
- name: `?QueryNextCommandInfo@CStartAPJob@@MEAAHKPEAPEAXPEAW4_WFC_DEVICE_COMMAND_TYPE@@PEAIPEAKPEAPEAE@Z`
- size: `2682`
- prototype: `__int64 __fastcall(CStartAPJob *__hidden this, unsigned int, void **, enum _WFC_DEVICE_COMMAND_TYPE *, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400101c8`
- `0x140010730`
- `0x1400109f8`
- `0x140010b20`
- `0x140012214`
- `0x1400122e0`
- `0x1400147e8`
- `0x1400174e8`
- `0x1400176b0`
- `0x14001f750`
- `0x140024928`
- `0x1400297a0`
- `0x14002aa28`
- `0x14004c5b4`
- `0x14005360c`
- `0x140061328`
- `0x140065338`
- `0x14008d600`
- `0x1400cefec`
- `0x1400cf0e4`
- `0x1400d0460`

## pseudocode

```c
__int64 __fastcall CStartAPJob::QueryNextCommandInfo(
        CStartAPJob *this,
        int a2,
        void **a3,
        enum _WFC_DEVICE_COMMAND_TYPE *a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        unsigned __int8 **a7)
{
  int v10; // r8d
  CPropertyCache *v11; // r14
  __int64 *v12; // rdx
  unsigned int *v13; // rax
  unsigned int *v14; // r15
  unsigned __int8 **v15; // r12
  int PropertyList; // eax
  int v17; // edx
  int v18; // r8d
  unsigned int v19; // ecx
  int v20; // r9d
  unsigned __int8 *v21; // rcx
  _WDI_TASK_START_AP_PARAMETERS *p_m_TaskParameters; // r13
  unsigned int PropertyUchar; // eax
  int v24; // edx
  int v25; // r8d
  unsigned int v26; // ebx
  int v27; // r9d
  unsigned int PropertyULong; // eax
  enum _WDI_AUTH_ALGORITHM v29; // esi
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  char v33; // bl
  CStartAPJob *i; // rcx
  _WDI_AUTH_ALGORITHM v35; // edx
  enum _WDI_CIPHER_ALGORITHM *pElements; // r9
  unsigned int ElementCount; // r8d
  enum _WDI_CIPHER_ALGORITHM *v38; // r9
  unsigned int v39; // r8d
  CStartAPJob *v40; // rcx
  int PropertyBuffer; // eax
  int v42; // edx
  __int64 v43; // r8
  unsigned __int64 v44; // rsi
  unsigned __int8 *v45; // rbx
  __int64 v46; // rdx
  unsigned int v47; // ecx
  unsigned int v48; // eax
  int v49; // ecx
  unsigned int j; // r12d
  unsigned __int8 *v51; // r10
  unsigned int *v52; // r14
  _WDI_AP_BAND_CHANNEL_LIST_CONTAINER *v53; // rdx
  __int64 v54; // r15
  int v55; // eax
  enum _WDI_BAND_ID v56; // eax
  int Elements; // eax
  _WDI_AP_BAND_CHANNEL_LIST_CONTAINER *v58; // r9
  unsigned __int8 *v59; // r10
  int v60; // eax
  int v61; // r9d
  int v62; // edx
  int v63; // r8d
  char v65; // [rsp+28h] [rbp-40h]
  unsigned int v66; // [rsp+30h] [rbp-38h]
  unsigned int m_ActivityId; // [rsp+30h] [rbp-38h]
  __int64 v68; // [rsp+38h] [rbp-30h]
  char v69; // [rsp+38h] [rbp-30h]
  char v70; // [rsp+40h] [rbp-28h]
  unsigned __int8 *v71; // [rsp+50h] [rbp-18h] BYREF
  struct CPortPropertyCache *PortPropertyCache; // [rsp+58h] [rbp-10h]
  int v73; // [rsp+B0h] [rbp+48h] BYREF
  int v74; // [rsp+B8h] [rbp+50h]
  _WDI_AP_BAND_CHANNEL_LIST_CONTAINER *v75; // [rsp+C0h] [rbp+58h] BYREF
  unsigned __int8 *v76; // [rsp+C8h] [rbp+60h] BYREF

  v74 = a2;
  PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
  v71 = 0;
  v11 = PortPropertyCache;
  LODWORD(v75) = 0;
  LOWORD(v73) = 0;
  LODWORD(v76) = 0;
  v12 = WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v12,
      v10,
      10,
      (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  v13 = (unsigned int *)a5;
  v14 = a6;
  v15 = a7;
  *a3 = 0;
  *a4 = WfcDeviceCommandTypeTask;
  *v13 = 14;
  *v14 = 0;
  *v15 = 0;
  a5 = 0;
  if ( this->m_LegacyAP )
  {
    PropertyList = CPropertyCache::GetPropertyList(v11, 5u, (unsigned int *)&v75, (unsigned __int16 *)&v73, &a5);
    if ( PropertyList || (_DWORD)v75 != 36 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return (unsigned int)-1073741436;
      v20 = 11;
      goto LABEL_117;
    }
    v19 = *(_DWORD *)a5;
    this->m_TaskParameters.DesiredSSID.pElements = a5 + 4;
  }
  else
  {
    PropertyList = CPropertyCache::GetPropertyBuffer(v11, 0x39u, (unsigned int *)&v75, &a5);
    if ( PropertyList || (_DWORD)v75 != 44 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return (unsigned int)-1073741436;
      v20 = 12;
      goto LABEL_117;
    }
    v21 = a5;
    this->m_TaskParameters.DesiredSSID.pElements = a5 + 12;
    v19 = *((_DWORD *)v21 + 2);
  }
  p_m_TaskParameters = &this->m_TaskParameters;
  this->m_TaskParameters.DesiredSSID.ElementCount = v19;
  CPropertyCache::GetPropertyULong(v11, 0x41u, &this->m_TaskParameters.StaticParameters.BeaconPeriod);
  PropertyUchar = CPropertyCache::GetPropertyUchar(
                    v11,
                    0x44u,
                    &this->m_TaskParameters.StaticParameters.DataRateSupport802_11b);
  v26 = PropertyUchar;
  if ( !PropertyUchar )
  {
    PropertyULong = CPropertyCache::GetPropertyULong(v11, 0x42u, &this->m_TaskParameters.StaticParameters.DTIMPeriod);
    v26 = PropertyULong;
    if ( PropertyULong )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v26;
      v27 = 14;
      goto LABEL_21;
    }
    v29 = WDI_AUTH_ALGO_RSNA_PSK;
    PropertyList = CPropertyCache::GetPropertyList(
                     v11,
                     7u,
                     (unsigned int *)&v75,
                     (unsigned __int16 *)&v73,
                     (unsigned __int8 **)&this->m_TaskParameters.AuthenticationAlgorithms.pElements);
    v30 = (unsigned __int16)v73;
    this->m_TaskParameters.AuthenticationAlgorithms.ElementCount = (unsigned __int16)v73;
    if ( PropertyList || !v30 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return (unsigned int)-1073741436;
      v20 = 15;
    }
    else
    {
      PropertyList = CPropertyCache::GetPropertyList(
                       v11,
                       9u,
                       (unsigned int *)&v75,
                       (unsigned __int16 *)&v73,
                       (unsigned __int8 **)&this->m_TaskParameters.UnicastCipherAlgorithms.pElements);
      v31 = (unsigned __int16)v73;
      this->m_TaskParameters.UnicastCipherAlgorithms.ElementCount = (unsigned __int16)v73;
      if ( PropertyList || !v31 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return (unsigned int)-1073741436;
        v20 = 16;
      }
      else
      {
        PropertyList = CPropertyCache::GetPropertyList(
                         v11,
                         8u,
                         (unsigned int *)&v75,
                         (unsigned __int16 *)&v73,
                         (unsigned __int8 **)&this->m_TaskParameters.MulticastCipherAlgorithms.pElements);
        v32 = (unsigned __int16)v73;
        this->m_TaskParameters.MulticastCipherAlgorithms.ElementCount = (unsigned __int16)v73;
        if ( !PropertyList && v32 )
        {
          PropertyULong = CPropertyCache::GetPropertyULong(v11, 0x18u, (unsigned int *)&v76);
          v26 = PropertyULong;
          if ( PropertyULong )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
              return v26;
            v27 = 18;
            goto LABEL_21;
          }
          v33 = (char)v76;
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v24) = 4;
            WPP_RECORDER_SF_DD(
              WPP_GLOBAL_Control->DeviceExtension,
              v24,
              1,
              19,
              (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
              (char)v76,
              this->CDeviceCommandOidJobBase::COidJobBase::m_NdisPortNumber);
          }
          if ( (v33 & 0x20) != 0 )
          {
            for ( i = 0;
                  (unsigned __int16)i < this->m_TaskParameters.AuthenticationAlgorithms.ElementCount;
                  LOWORD(i) = (_WORD)i + 1 )
            {
              v35 = this->m_TaskParameters.AuthenticationAlgorithms.pElements[(unsigned __int16)i];
              if ( v35 == WDI_AUTH_ALGO_RSNA_PSK )
              {
                v29 = WDI_AUTH_ALGO_RSNA_PSK;
                break;
              }
              if ( v35 == WDI_AUTH_ALGO_80211_OPEN )
                v29 = WDI_AUTH_ALGO_80211_OPEN;
            }
            pElements = this->m_TaskParameters.MulticastCipherAlgorithms.pElements;
            ElementCount = this->m_TaskParameters.MulticastCipherAlgorithms.ElementCount;
            this->m_authAlgoList[0] = v29;
            this->m_TaskParameters.AuthenticationAlgorithms.ElementCount = 1;
            this->m_TaskParameters.AuthenticationAlgorithms.pElements = this->m_authAlgoList;
            this->m_multicastCipherAlgoList[0] = CStartAPJob::GetCipherForGO(i, v29, ElementCount, pElements);
            v38 = this->m_TaskParameters.UnicastCipherAlgorithms.pElements;
            v39 = this->m_TaskParameters.UnicastCipherAlgorithms.ElementCount;
            this->m_TaskParameters.MulticastCipherAlgorithms.pElements = this->m_multicastCipherAlgoList;
            this->m_TaskParameters.MulticastCipherAlgorithms.ElementCount = 1;
            this->m_unicastCipherAlgoList[0] = CStartAPJob::GetCipherForGO(v40, v29, v39, v38);
            this->m_TaskParameters.UnicastCipherAlgorithms.ElementCount = 1;
            this->m_TaskParameters.UnicastCipherAlgorithms.pElements = this->m_unicastCipherAlgoList;
          }
          PropertyBuffer = CPropertyCache::GetPropertyBuffer(v11, 0x40u, (unsigned int *)&v75, &v71);
          v44 = (unsigned int)v75;
          if ( PropertyBuffer || (unsigned int)v75 < 4 )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v42) = 4;
              WPP_RECORDER_SF_qDdd(
                WPP_GLOBAL_Control->DeviceExtension,
                v42,
                v43,
                20,
                (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                (char)this,
                this->m_ActivityId,
                PropertyBuffer,
                (char)v75);
            }
            goto LABEL_103;
          }
          v45 = v71;
          LODWORD(v46) = v71[1];
          if ( (_DWORD)v46 == 1 )
          {
            if ( (unsigned int)v75 < 0xA || !v71[8] )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v46) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v46,
                  v43,
                  22,
                  (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                  (char)this,
                  this->m_ActivityId);
              }
              goto LABEL_103;
            }
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
              goto LABEL_87;
            v61 = 21;
            v70 = v71[8];
            v69 = v71[7];
            m_ActivityId = this->m_ActivityId;
            v65 = (char)this;
          }
          else
          {
            if ( v71[1] != 2 )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v46) = 2;
                WPP_RECORDER_SF_qDDd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v46,
                  v43,
                  31,
                  (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                  (char)this,
                  this->m_ActivityId,
                  0,
                  v71[1]);
              }
              goto LABEL_103;
            }
            if ( (unsigned int)v75 < 0x18 )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v46) = 2;
                WPP_RECORDER_SF_Ld(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v46,
                  v43,
                  30,
                  (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                  (char)v75,
                  24);
              }
              goto LABEL_103;
            }
            this->m_TaskParameters.StaticParameters.AcceptNonP2PClients = v71[9];
            this->m_TaskParameters.StaticParameters.MustUseSpecifiedChannels = v45[10];
            v46 = *((unsigned int *)v45 + 3);
            if ( (_DWORD)v46
              && (v47 = *((_DWORD *)v45 + 4), v47 >= 0x18)
              && (v48 = *((_DWORD *)v45 + 5), v48 >= 8)
              && (unsigned int)v44 >= v47 + v48 )
            {
              if ( !(unsigned int)ArrayOfElements<_WDI_AP_BAND_CHANNEL_LIST_CONTAINER>::AllocateElements(
                                    &this->m_TaskParameters.APBandChannelList,
                                    v46,
                                    0) )
              {
                v49 = *((_DWORD *)v45 + 4);
                LODWORD(a5) = v49;
                if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v46) = 4;
                  WPP_RECORDER_SF_qDL(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v46,
                    v43,
                    23,
                    (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                    (char)this,
                    this->m_ActivityId,
                    *((_DWORD *)v45 + 3));
                  v49 = (int)a5;
                }
                for ( j = 0; j < *((_DWORD *)v45 + 3); ++j )
                {
                  v46 = (unsigned int)(v49 + 8);
                  v51 = &v45[v49];
                  v76 = v51;
                  v52 = (unsigned int *)(v51 + 4);
                  if ( (unsigned int)v44 < (unsigned int)v46 )
                    goto LABEL_75;
                  v43 = *v52;
                  if ( v44 < v46 + 4 * v43 )
                  {
                    LOBYTE(v49) = (_BYTE)a5;
LABEL_75:
                    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                    {
                      if ( (unsigned int)v44 >= (unsigned int)v46 )
                        v60 = 4 * *v52;
                      else
                        LOBYTE(v60) = 0;
                      LOBYTE(v46) = 2;
                      WPP_RECORDER_SF_ddddd(
                        WPP_GLOBAL_Control->DeviceExtension,
                        v46,
                        v43,
                        24,
                        (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                        j,
                        v44,
                        v49,
                        8,
                        v60);
                    }
LABEL_80:
                    if ( j < *((_DWORD *)v45 + 3) )
                      goto LABEL_82;
                    break;
                  }
                  v53 = this->m_TaskParameters.APBandChannelList.pElements;
                  v54 = j;
                  v75 = v53;
                  v73 = 4 * v43;
                  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  {
                    if ( (_DWORD)v43 )
                      v55 = *((_DWORD *)v51 + 2);
                    else
                      LOBYTE(v55) = 0;
                    LOBYTE(v53) = 4;
                    WPP_RECORDER_SF_dddd(
                      WPP_GLOBAL_Control->DeviceExtension,
                      (_DWORD)v53,
                      v43,
                      25,
                      (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                      j,
                      *(_DWORD *)v51,
                      v43,
                      v55);
                    v51 = v76;
                  }
                  v56 = CDot11ToWabiConverter::MapBandID(*(enum _DOT11_BAND_ID *)v51);
                  *(_DWORD *)(v54 * 32 + v46 + 4) = v56;
                  if ( *v52 )
                  {
                    Elements = ArrayOfElements<unsigned int>::AllocateElements(v54 * 32 + v46 + 8, *v52, 0);
                    if ( Elements )
                    {
                      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                      {
                        LOBYTE(v46) = 2;
                        WPP_RECORDER_SF_Ld(
                          WPP_GLOBAL_Control->DeviceExtension,
                          v46,
                          v43,
                          26,
                          (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                          *v52,
                          Elements);
                      }
                      goto LABEL_80;
                    }
                    v58 = v75;
                    v43 = 0;
                    if ( *v52 )
                    {
                      v59 = v76;
                      do
                      {
                        v58[v54].ChannelList.pElements[v43] = *(_DWORD *)&v59[4 * v43 + 8];
                        v43 = (unsigned int)(v43 + 1);
                      }
                      while ( (unsigned int)v43 < *v52 );
                    }
                    *(_DWORD *)&v58[v54].Optional |= 1u;
                  }
                  v49 = v73 + (_DWORD)a5 + 8;
                  LODWORD(a5) = v49;
                }
                *(_DWORD *)&p_m_TaskParameters->Optional |= 2u;
LABEL_82:
                v11 = PortPropertyCache;
                LODWORD(v14) = (_DWORD)a6;
                v15 = a7;
              }
            }
            else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v46) = 2;
              WPP_RECORDER_SF_dddd(
                WPP_GLOBAL_Control->DeviceExtension,
                v46,
                v43,
                27,
                (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                v44,
                *((_DWORD *)v45 + 3),
                *((_DWORD *)v45 + 4),
                *((_DWORD *)v45 + 5));
            }
            if ( !v45[8] )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v46) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v46,
                  v43,
                  29,
                  (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                  (char)this,
                  this->m_ActivityId);
              }
              goto LABEL_103;
            }
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            {
LABEL_87:
              *(_DWORD *)&p_m_TaskParameters->Optional |= 1u;
              this->m_TaskParameters.AdvertisedOperatingChannel.OperatingClass = v45[7];
              this->m_TaskParameters.AdvertisedOperatingChannel.ChannelNumber = v45[8];
              *(_WORD *)this->m_TaskParameters.AdvertisedOperatingChannel.CountryOrRegionString = *((_WORD *)v45 + 2);
              this->m_TaskParameters.AdvertisedOperatingChannel.CountryOrRegionString[2] = v45[6];
LABEL_103:
              if ( !(unsigned int)CPropertyCache::SetPropertyBoolean(
                                    v11,
                                    0x45u,
                                    this->m_TaskParameters.StaticParameters.AcceptNonP2PClients) )
              {
                PropertyULong = GenerateWdiTaskStartApToIhv(
                                  (int)this + 1080,
                                  v74,
                                  (unsigned int)this->m_pAdapter + 16376,
                                  (_DWORD)v14,
                                  (__int64)v15);
                v26 = PropertyULong;
                if ( !PropertyULong || *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                  return v26;
                v27 = 33;
LABEL_21:
                LODWORD(v68) = PropertyULong;
                v66 = this->m_ActivityId;
                goto LABEL_17;
              }
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v62) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v62,
                  v63,
                  32,
                  (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
                  (char)this,
                  this->m_ActivityId);
              }
              return (unsigned int)-1073741436;
            }
            v61 = 28;
            v70 = v45[8];
            v69 = v45[7];
            m_ActivityId = this->m_ActivityId;
            v65 = (char)this;
          }
          LOBYTE(v46) = 4;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v46,
            v43,
            v61,
            (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
            v65,
            m_ActivityId,
            v69,
            v70);
          goto LABEL_87;
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return (unsigned int)-1073741436;
        v20 = 17;
      }
    }
LABEL_117:
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      v18,
      v20,
      (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
      (char)this,
      this->m_ActivityId,
      PropertyList);
    return (unsigned int)-1073741436;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v27 = 13;
    LODWORD(v68) = PropertyUchar;
    v66 = this->m_ActivityId;
LABEL_17:
    LOBYTE(v24) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v24,
      v25,
      v27,
      (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
      (char)this,
      v66,
      v68);
  }
  return v26;
}

```

## disassembly

```asm
0x1400d0460  mov     [rsp-40h+arg_8], edx
0x1400d0464  push    rbp
0x1400d0465  push    rbx
0x1400d0466  push    rsi
0x1400d0467  push    rdi
0x1400d0468  push    r12
0x1400d046a  push    r13
0x1400d046c  push    r14
0x1400d046e  push    r15
0x1400d0470  mov     rbp, rsp
0x1400d0473  sub     rsp, 68h
0x1400d0477  mov     rbx, r9
0x1400d047a  mov     rsi, r8
0x1400d047d  mov     rdi, rcx
0x1400d0480  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400d0485  xor     r13d, r13d
0x1400d0488  mov     [rbp+var_10], rax
0x1400d048c  mov     [rbp+var_18], r13
0x1400d0490  mov     r14, rax
0x1400d0493  mov     dword ptr [rbp+arg_10], r13d
0x1400d0497  mov     word ptr [rbp+arg_0], r13w
0x1400d049c  mov     dword ptr [rbp+arg_18], r13d
0x1400d04a0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d04a7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d04ae  lea     rdx, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x1400d04b5  jz      short loc_1400D04ED
0x1400d04b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d04be  cmp     byte ptr [rcx+29h], 5
0x1400d04c2  jnb     short loc_1400D04CB
0x1400d04c4  cmp     [rcx+48h], r13w
0x1400d04c9  jz      short loc_1400D04ED
0x1400d04cb  mov     eax, [rdi+10h]
0x1400d04ce  mov     r9d, 0Ah
0x1400d04d4  mov     rcx, [rcx+40h]
0x1400d04d8  mov     [rsp+68h+var_38], eax
0x1400d04dc  mov     [rsp+68h+var_40], rdi
0x1400d04e1  mov     [rsp+68h+var_48], rdx
0x1400d04e6  mov     dl, 5
0x1400d04e8  call    WPP_RECORDER_SF_qD
0x1400d04ed  mov     rax, [rbp+arg_20]
0x1400d04f1  lea     r8, [rbp+arg_10]; unsigned int *
0x1400d04f5  mov     r15, [rbp+arg_28]
0x1400d04f9  mov     rcx, r14; this
0x1400d04fc  mov     r12, [rbp+arg_30]
0x1400d0500  mov     [rsi], r13
0x1400d0503  mov     dword ptr [rbx], 2
0x1400d0509  mov     dword ptr [rax], 0Eh
0x1400d050f  mov     [r15], r13d
0x1400d0512  mov     [r12], r13
0x1400d0516  mov     [rbp+arg_20], r13
0x1400d051a  cmp     [rdi+430h], r13b
0x1400d0521  jz      short loc_1400D0576
0x1400d0523  lea     rax, [rbp+arg_20]
0x1400d0527  mov     edx, 5; unsigned int
0x1400d052c  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x1400d0530  mov     [rsp+68h+var_48], rax; unsigned __int8 **
0x1400d0535  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400d053a  test    eax, eax
0x1400d053c  jnz     short loc_1400D0557
0x1400d053e  cmp     dword ptr [rbp+arg_10], 24h ; '$'
0x1400d0542  jnz     short loc_1400D0557
0x1400d0544  mov     rax, [rbp+arg_20]
0x1400d0548  mov     ecx, [rax]
0x1400d054a  add     rax, 4
0x1400d054e  mov     [rdi+448h], rax
0x1400d0555  jmp     short loc_1400D05A8
0x1400d0557  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d055e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d0565  jz      loc_1400D0EC1
0x1400d056b  mov     r9d, 0Bh
0x1400d0571  jmp     loc_1400D0E93
0x1400d0576  lea     r9, [rbp+arg_20]; unsigned __int8 **
0x1400d057a  mov     edx, 39h ; '9'; unsigned int
0x1400d057f  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400d0584  test    eax, eax
0x1400d0586  jnz     loc_1400D0E7D
0x1400d058c  cmp     dword ptr [rbp+arg_10], 2Ch ; ','
0x1400d0590  jnz     loc_1400D0E7D
0x1400d0596  mov     rcx, [rbp+arg_20]
0x1400d059a  lea     rax, [rcx+0Ch]
0x1400d059e  mov     [rdi+448h], rax
0x1400d05a5  mov     ecx, [rcx+8]
0x1400d05a8  lea     r13, [rdi+438h]
0x1400d05af  mov     edx, 41h ; 'A'; unsigned int
0x1400d05b4  mov     [r13+8], ecx
0x1400d05b8  lea     r8, [r13+20h]; unsigned int *
0x1400d05bc  mov     rcx, r14; this
0x1400d05bf  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400d05c4  lea     r8, [r13+29h]; unsigned __int8 *
0x1400d05c8  mov     edx, 44h ; 'D'; unsigned int
0x1400d05cd  mov     rcx, r14; this
0x1400d05d0  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x1400d05d5  mov     ebx, eax
0x1400d05d7  test    eax, eax
0x1400d05d9  jz      short loc_1400D0628
0x1400d05db  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d05e2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d05e9  jz      loc_1400D0EC6
0x1400d05ef  mov     ecx, [rdi+10h]
0x1400d05f2  mov     r9d, 0Dh
0x1400d05f8  mov     dword ptr [rsp+68h+var_30], eax
0x1400d05fc  mov     [rsp+68h+var_38], ecx
0x1400d0600  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0607  lea     rax, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x1400d060e  mov     [rsp+68h+var_40], rdi
0x1400d0613  mov     dl, 2
0x1400d0615  mov     [rsp+68h+var_48], rax
0x1400d061a  mov     rcx, [rcx+40h]
0x1400d061e  call    WPP_RECORDER_SF_qDD
0x1400d0623  jmp     loc_1400D0EC6
0x1400d0628  lea     r8, [r13+24h]; unsigned int *
0x1400d062c  mov     edx, 42h ; 'B'; unsigned int
0x1400d0631  mov     rcx, r14; this
0x1400d0634  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400d0639  mov     ebx, eax
0x1400d063b  test    eax, eax
0x1400d063d  jz      short loc_1400D0666
0x1400d063f  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d0646  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d064d  jz      loc_1400D0EC6
0x1400d0653  mov     r9d, 0Eh
0x1400d0659  mov     dword ptr [rsp+68h+var_30], eax
0x1400d065d  mov     eax, [rdi+10h]
0x1400d0660  mov     [rsp+68h+var_38], eax
0x1400d0664  jmp     short loc_1400D0600
0x1400d0666  lea     rax, [r13+38h]
0x1400d066a  mov     esi, 7
0x1400d066f  mov     edx, esi; unsigned int
0x1400d0671  mov     [rsp+68h+var_48], rax; unsigned __int8 **
0x1400d0676  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x1400d067a  mov     rcx, r14; this
0x1400d067d  lea     r8, [rbp+arg_10]; unsigned int *
0x1400d0681  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400d0686  movzx   ecx, word ptr [rbp+arg_0]
0x1400d068a  mov     [rdi+468h], ecx
0x1400d0690  test    eax, eax
0x1400d0692  jnz     loc_1400D0E65
0x1400d0698  test    ecx, ecx
0x1400d069a  jz      loc_1400D0E65
0x1400d06a0  lea     rax, [r13+68h]
0x1400d06a4  mov     rcx, r14; this
0x1400d06a7  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x1400d06ab  mov     [rsp+68h+var_48], rax; unsigned __int8 **
0x1400d06b0  lea     r8, [rbp+arg_10]; unsigned int *
0x1400d06b4  lea     edx, [rsi+2]; unsigned int
0x1400d06b7  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400d06bc  movzx   ecx, word ptr [rbp+arg_0]
0x1400d06c0  mov     [rdi+498h], ecx
0x1400d06c6  test    eax, eax
0x1400d06c8  jnz     loc_1400D0E4D
0x1400d06ce  test    ecx, ecx
0x1400d06d0  jz      loc_1400D0E4D
0x1400d06d6  lea     rax, [r13+50h]
0x1400d06da  mov     rcx, r14; this
0x1400d06dd  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x1400d06e1  mov     [rsp+68h+var_48], rax; unsigned __int8 **
0x1400d06e6  lea     r8, [rbp+arg_10]; unsigned int *
0x1400d06ea  lea     edx, [rsi+1]; unsigned int
0x1400d06ed  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400d06f2  movzx   ecx, word ptr [rbp+arg_0]
0x1400d06f6  mov     [rdi+480h], ecx
0x1400d06fc  test    eax, eax
0x1400d06fe  jnz     loc_1400D0E35
0x1400d0704  test    ecx, ecx
0x1400d0706  jz      loc_1400D0E35
0x1400d070c  lea     r8, [rbp+arg_18]; unsigned int *
0x1400d0710  mov     rcx, r14; this
0x1400d0713  lea     edx, [rsi+11h]; unsigned int
0x1400d0716  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400d071b  mov     ebx, eax
0x1400d071d  test    eax, eax
0x1400d071f  jz      short loc_1400D073E
0x1400d0721  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d0728  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d072f  jz      loc_1400D0EC6
0x1400d0735  lea     r9d, [rsi+0Bh]
0x1400d0739  jmp     loc_1400D0659
0x1400d073e  mov     ebx, dword ptr [rbp+arg_18]; __annotation("TMF:",
0x1400d0741  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d0748  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d074f  mov     r10d, 1
0x1400d0755  jz      short loc_1400D0790
0x1400d0757  mov     eax, [rdi+218h]
0x1400d075d  lea     r9d, [r10+12h]
0x1400d0761  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0768  mov     r8d, r10d
0x1400d076b  mov     [rsp+68h+var_38], eax
0x1400d076f  mov     dl, 4
0x1400d0771  lea     rax, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x1400d0778  mov     dword ptr [rsp+68h+var_40], ebx
0x1400d077c  mov     [rsp+68h+var_48], rax
0x1400d0781  mov     rcx, [rcx+40h]
0x1400d0785  call    WPP_RECORDER_SF_DD
0x1400d078a  mov     r10d, 1
0x1400d0790  test    bl, 20h
0x1400d0793  jz      loc_1400D0844
0x1400d0799  mov     r9, [rdi+470h]
0x1400d07a0  xor     ecx, ecx; this
0x1400d07a2  mov     r8d, [rdi+468h]
0x1400d07a9  movzx   eax, cx
0x1400d07ac  cmp     eax, r8d
0x1400d07af  jnb     short loc_1400D07CF
0x1400d07b1  movzx   eax, cx
0x1400d07b4  mov     edx, [r9+rax*4]
0x1400d07b8  cmp     edx, 7
0x1400d07bb  jz      short loc_1400D07CA
0x1400d07bd  cmp     edx, r10d
0x1400d07c0  cmovz   esi, r10d
0x1400d07c4  add     cx, r10w
0x1400d07c8  jmp     short loc_1400D07A9
0x1400d07ca  mov     esi, 7
0x1400d07cf  mov     r9, [rdi+488h]; enum _WDI_CIPHER_ALGORITHM *
0x1400d07d6  lea     rax, [rdi+4D0h]
0x1400d07dd  mov     r8d, [rdi+480h]; unsigned int
0x1400d07e4  lea     rbx, [rdi+4D8h]
0x1400d07eb  mov     [rax], esi
0x1400d07ed  mov     edx, esi; enum _WDI_AUTH_ALGORITHM
0x1400d07ef  mov     [rdi+468h], r10d
0x1400d07f6  mov     [rdi+470h], rax
0x1400d07fd  call    ?GetCipherForGO@CStartAPJob@@IEAA?AW4_WDI_CIPHER_ALGORITHM@@W4_WDI_AUTH_ALGORITHM@@IPEAW42@@Z; CStartAPJob::GetCipherForGO(_WDI_AUTH_ALGORITHM,uint,_WDI_CIPHER_ALGORITHM *)
0x1400d0802  mov     [rbx], eax
0x1400d0804  mov     edx, esi; enum _WDI_AUTH_ALGORITHM
0x1400d0806  mov     r9, [rdi+4A0h]; enum _WDI_CIPHER_ALGORITHM *
0x1400d080d  mov     r8d, [rdi+498h]; unsigned int
0x1400d0814  mov     [rdi+488h], rbx
0x1400d081b  lea     rbx, [rdi+4D4h]
0x1400d0822  mov     dword ptr [rdi+480h], 1
0x1400d082c  call    ?GetCipherForGO@CStartAPJob@@IEAA?AW4_WDI_CIPHER_ALGORITHM@@W4_WDI_AUTH_ALGORITHM@@IPEAW42@@Z; CStartAPJob::GetCipherForGO(_WDI_AUTH_ALGORITHM,uint,_WDI_CIPHER_ALGORITHM *)
0x1400d0831  mov     [rbx], eax
0x1400d0833  mov     dword ptr [rdi+498h], 1
0x1400d083d  mov     [rdi+4A0h], rbx
0x1400d0844  lea     r9, [rbp+var_18]; unsigned __int8 **
0x1400d0848  mov     edx, 40h ; '@'; unsigned int
0x1400d084d  lea     r8, [rbp+arg_10]; unsigned int *
0x1400d0851  mov     rcx, r14; this
0x1400d0854  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400d0859  mov     esi, dword ptr [rbp+arg_10]
0x1400d085c  test    eax, eax
0x1400d085e  jnz     loc_1400D0D50
0x1400d0864  cmp     esi, 4
0x1400d0867  jb      loc_1400D0D50
0x1400d086d  mov     rbx, [rbp+var_18]
0x1400d0871  movzx   edx, byte ptr [rbx+1]
0x1400d0875  mov     ecx, edx
0x1400d0877  sub     ecx, 1
0x1400d087a  jz      loc_1400D0CBE
0x1400d0880  cmp     ecx, 1
0x1400d0883  jz      short loc_1400D08D4
0x1400d0885  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d088c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400d0893  lea     rbx, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x1400d089a  jz      loc_1400D0D9F
0x1400d08a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d08a7  lea     r9d, [rax+1Fh]
0x1400d08ab  mov     dword ptr [rsp+68h+var_28], edx
0x1400d08af  mov     dl, 2
0x1400d08b1  mov     dword ptr [rsp+68h+var_30], eax
0x1400d08b5  mov     eax, [rdi+10h]
0x1400d08b8  mov     rcx, [rcx+40h]
0x1400d08bc  mov     [rsp+68h+var_38], eax
0x1400d08c0  mov     [rsp+68h+var_40], rdi
0x1400d08c5  mov     [rsp+68h+var_48], rbx
0x1400d08ca  call    WPP_RECORDER_SF_qDDd
0x1400d08cf  jmp     loc_1400D0D9F
0x1400d08d4  cmp     esi, 18h
0x1400d08d7  jb      loc_1400D0C75
0x1400d08dd  mov     al, [rbx+9]
0x1400d08e0  mov     [rdi+462h], al
0x1400d08e6  mov     al, [rbx+0Ah]
0x1400d08e9  mov     [rdi+463h], al
0x1400d08ef  mov     edx, [rbx+0Ch]
0x1400d08f2  test    edx, edx
0x1400d08f4  jz      loc_1400D0BE4
0x1400d08fa  mov     ecx, [rbx+10h]
0x1400d08fd  cmp     ecx, 18h
0x1400d0900  jb      loc_1400D0BE4
0x1400d0906  mov     eax, [rbx+14h]
0x1400d0909  cmp     eax, 8
0x1400d090c  jb      loc_1400D0BE4
0x1400d0912  add     eax, ecx
0x1400d0914  cmp     esi, eax
0x1400d0916  jb      loc_1400D0BE4
0x1400d091c  lea     rcx, [r13+80h]
0x1400d0923  xor     r8d, r8d
0x1400d0926  call    ?AllocateElements@?$ArrayOfElements@U_WDI_AP_BAND_CHANNEL_LIST_CONTAINER@@@@QEAAHI_K@Z; ArrayOfElements<_WDI_AP_BAND_CHANNEL_LIST_CONTAINER>::AllocateElements(uint,unsigned __int64)
0x1400d092b  test    eax, eax
0x1400d092d  jnz     loc_1400D0B54
0x1400d0933  mov     ecx, [rbx+10h]
0x1400d0936  mov     dword ptr [rbp+arg_20], ecx
0x1400d0939  lea     r9, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d0940  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x1400d0947  jz      short loc_1400D0988
0x1400d0949  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0950  lea     r9d, [rax+17h]
0x1400d0954  mov     eax, [rbx+0Ch]
0x1400d0957  lea     r15, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x1400d095e  mov     dword ptr [rsp+68h+var_30], eax
0x1400d0962  mov     dl, 4
0x1400d0964  mov     eax, [rdi+10h]
0x1400d0967  mov     rcx, [rcx+40h]
  ... truncated ...
```
