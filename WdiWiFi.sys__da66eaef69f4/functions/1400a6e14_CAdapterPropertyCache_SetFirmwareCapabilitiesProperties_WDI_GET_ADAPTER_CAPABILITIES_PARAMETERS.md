# CAdapterPropertyCache::SetFirmwareCapabilitiesProperties(_WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS *)

- ea: `0x1400a6e14`
- end: `0x1400a7c6a`
- name: `?SetFirmwareCapabilitiesProperties@CAdapterPropertyCache@@QEAAHPEAU_WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS@@@Z`
- size: `3670`
- prototype: `__int64 __fastcall(CAdapterPropertyCache *__hidden this, struct _WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400a3478`

## callees

- `0x1400100f8`
- `0x1400101c8`
- `0x140010298`
- `0x140012214`
- `0x1400175f8`
- `0x1400176b0`
- `0x140017a90`
- `0x14001b84c`
- `0x140023ae0`
- `0x140034e04`
- `0x140034ec4`
- `0x140052178`
- `0x1400523f0`
- `0x1400524a4`
- `0x1400707e8`
- `0x140083b44`
- `0x1400a6e14`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400a73d8`
- `ntoskrnl!ExAllocatePool2` at `0x1400a746a`
- `ntoskrnl!ExAllocatePool2` at `0x1400a74ee`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7572`
- `ntoskrnl!ExAllocatePool2` at `0x1400a771f`
- `ntoskrnl!ExAllocatePool2` at `0x1400a78fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400a73d8`
- `ntoskrnl!ExAllocatePool2` at `0x1400a746a`
- `ntoskrnl!ExAllocatePool2` at `0x1400a74ee`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7572`
- `ntoskrnl!ExAllocatePool2` at `0x1400a771f`
- `ntoskrnl!ExAllocatePool2` at `0x1400a78fa`

## pseudocode

```c
__int64 __fastcall CAdapterPropertyCache::SetFirmwareCapabilitiesProperties(
        CAdapterPropertyCache *this,
        struct _WDI_GET_ADAPTER_CAPABILITIES_PARAMETERS *a2)
{
  unsigned int MaxCommandSize; // r8d
  int v5; // edx
  unsigned int v6; // edi
  int v7; // r9d
  int v8; // r8d
  unsigned int v9; // edi
  int v10; // eax
  int ConcurrentClientCount; // r9d
  int v12; // edx
  int v13; // edx
  __int64 v14; // r12
  _WDI_MAC_ADDRESS *pElements; // rax
  int v16; // edx
  CPropertyCache *v17; // rcx
  _WDI_STATION_ATTRIBUTES_CONTAINER *p_StationAttributes; // r12
  int Properties; // eax
  CPropertyCache *v20; // rcx
  int v21; // r9d
  unsigned __int8 *Pool2; // r12
  unsigned int k; // r15d
  __int64 v24; // r13
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  __int64 v29; // rax
  unsigned __int64 ElementCount; // kr00_8
  __int64 i; // rax
  unsigned __int64 v32; // rcx
  __int64 v33; // rax
  void *v34; // rcx
  int v35; // r8d
  unsigned __int64 v36; // rcx
  __int64 v37; // rax
  void *v38; // rcx
  unsigned __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 j; // r10
  int v43; // eax
  int v44; // r9d
  int PropertyListProperty; // eax
  int v46; // edx
  int v47; // r9d
  __int64 v48; // rax
  int v49; // edx
  unsigned __int8 *v50; // r9
  unsigned int v51; // r12d
  unsigned int v52; // ecx
  __int64 v53; // r10
  unsigned int v54; // ecx
  __int64 v55; // rax
  int v56; // edx
  CPropertyCache *Next; // rcx
  unsigned int v58; // eax
  int v59; // r8d
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  __int128 v64; // xmm0
  __int128 v65; // xmm1
  __int128 v66; // xmm0
  __int128 v67; // xmm1
  __int128 v68; // xmm0
  unsigned int v69; // eax
  struct _WFC_PROPERTY_LOAD_INFO *v70; // [rsp+28h] [rbp-D8h]
  struct _WFC_PROPERTY_LOAD_INFO *v71; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *v72; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v73; // [rsp+68h] [rbp-98h]
  CPropertyCache *v74; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v75[2]; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v76; // [rsp+80h] [rbp-80h]
  struct _WDI_TCP_OFFLOAD_CAPABILITIES_CONTAINER v77; // [rsp+90h] [rbp-70h] BYREF
  int v78; // [rsp+178h] [rbp+78h]
  __int64 v79; // [rsp+178h] [rbp+78h]
  unsigned int v80; // [rsp+178h] [rbp+78h]
  __int64 v81; // [rsp+180h] [rbp+80h]
  unsigned int v82; // [rsp+180h] [rbp+80h]
  CPropertyCache *v83; // [rsp+188h] [rbp+88h]
  CPropertyCache *v84; // [rsp+188h] [rbp+88h]

  MaxCommandSize = a2->CommunicationAttributes.CommunicationCapabilities.MaxCommandSize;
  v74 = 0;
  v6 = CPropertyCache::SetPropertyULong(this, 0x10u, MaxCommandSize);
  if ( !v6 )
  {
    v6 = CPropertyCache::SetPropertyULong(
           this,
           0x11u,
           a2->InterfaceAttributes.InterfaceCapabilities.MaxMultiCastListSize);
    if ( v6 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v6;
      v7 = 32;
      goto LABEL_4;
    }
    v6 = CPropertyCache::SetPropertyULong(this, 0x6Eu, a2->InterfaceAttributes.InterfaceCapabilities.BackFillSize);
    if ( v6 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v6;
      v7 = 33;
      goto LABEL_4;
    }
    v6 = CPropertyCache::SetPropertyBoolean(
           this,
           0x1Au,
           a2->InterfaceAttributes.InterfaceCapabilities.ActionFramesSupported);
    if ( v6 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v6;
      v7 = 34;
      goto LABEL_4;
    }
    v6 = CPropertyCache::SetPropertyBoolean(
           this,
           0x1Bu,
           a2->InterfaceAttributes.InterfaceCapabilities.MACAddressRandomization);
    if ( v6 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v6;
      v7 = 35;
      goto LABEL_4;
    }
    v6 = CPropertyCache::SetPropertyBoolean(
           this,
           0x1Cu,
           a2->InterfaceAttributes.InterfaceCapabilities.SupportsNonWdiOidRequests);
    if ( v6 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v6;
      v7 = 36;
      goto LABEL_4;
    }
    v9 = 4;
    if ( (*(_DWORD *)&a2->Optional & 8) != 0 )
    {
      v10 = 52;
      ConcurrentClientCount = a2->P2PAttributes.P2PCapabilities.ConcurrentClientCount;
      if ( !a2->P2PAttributes.P2PCapabilities.ConcurrentGOCount )
        v10 = 20;
      v9 = v10 | 0x40;
      if ( !(_BYTE)ConcurrentClientCount )
        v9 = v10;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_dddDDDd(
          WPP_GLOBAL_Control->DeviceExtension,
          a2->P2PAttributes.P2PCapabilities.ClientDiscoverabilitySupported,
          a2->P2PAttributes.P2PCapabilities.ServiceDiscoverySupported,
          ConcurrentClientCount);
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 4;
          WPP_RECORDER_SF__MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            v12,
            v8,
            38,
            (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
            (__int64)a2->P2PAttributes.P2PCapabilities.DeviceAddress);
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v13) = 4;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v13,
              v8,
              39,
              (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
              a2->P2PAttributes.InterfaceAddressList.ElementCount);
          }
        }
      }
      if ( a2->P2PAttributes.InterfaceAddressList.ElementCount )
      {
        v14 = 0;
        do
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            pElements = a2->P2PAttributes.InterfaceAddressList.pElements;
            v16 = (_DWORD)pElements + 6 * v14;
            LOBYTE(v16) = 4;
            WPP_RECORDER_SF_d_MAC_(
              WPP_GLOBAL_Control->DeviceExtension,
              v16,
              v8,
              40,
              (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
              v14,
              (__int64)&pElements[v14]);
          }
          v14 = (unsigned int)(v14 + 1);
        }
        while ( (unsigned int)v14 < a2->P2PAttributes.InterfaceAddressList.ElementCount );
      }
    }
    v6 = CPropertyCache::SetPropertyULong(this, 0x13u, v9);
    if ( v6 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v6;
      v7 = 41;
      goto LABEL_4;
    }
    v6 = CPropertyCache::SetPropertyBoolean(
           this,
           0x8Fu,
           a2->InterfaceAttributes.InterfaceCapabilities.BeaconReportsImplemented);
    if ( v6 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v6;
      v7 = 42;
      goto LABEL_4;
    }
    p_StationAttributes = &a2->StationAttributes;
    Properties = CPropertyCache::LoadProperties(
                   v17,
                   this,
                   0x38u,
                   (unsigned __int8 *)&a2->StationAttributes.StationCapabilities,
                   &stru_1400EE360,
                   0xDu,
                   0x91u);
    v6 = Properties;
    if ( Properties )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v6;
      v21 = 43;
LABEL_43:
      LODWORD(v70) = Properties;
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        1,
        v21,
        (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
        v70);
      return v6;
    }
    if ( (*(_DWORD *)&p_StationAttributes->Optional & 1) != 0 )
    {
      v6 = CPropertyCache::LoadProperties(
             v20,
             this,
             0x88u,
             (unsigned __int8 *)&a2->StationAttributes,
             &stru_1400EE348,
             1u,
             0x91u);
      if ( v6 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v6;
        v7 = 44;
        goto LABEL_4;
      }
    }
    if ( (*(_DWORD *)&p_StationAttributes->Optional & 2) != 0 )
    {
      v6 = CPropertyCache::LoadProperties(
             v20,
             this,
             0x88u,
             (unsigned __int8 *)&a2->StationAttributes,
             &stru_1400EE330,
             1u,
             0x91u);
      if ( v6 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v6;
        v7 = 45;
        goto LABEL_4;
      }
    }
    if ( (*(_DWORD *)&a2->Optional & 0x80u) != 0 )
    {
      Properties = CPropertyCache::LoadProperties(
                     v20,
                     this,
                     0x38u,
                     (unsigned __int8 *)&a2->PmCapabilities,
                     &stru_1400EE1E0,
                     0xEu,
                     0x91u);
      v6 = Properties;
      if ( Properties )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v6;
        v21 = 46;
        goto LABEL_43;
      }
    }
    v72 = 0;
    v73 = 0;
    if ( (*(_DWORD *)&a2->Optional & 0x20) == 0 )
    {
      Pool2 = 0;
      goto LABEL_58;
    }
    ElementCount = a2->BandInfo.ElementCount;
    v29 = 56 * ElementCount;
    *(_QWORD *)v75 = ElementCount;
    if ( !is_mul_ok(ElementCount, 0x38u) )
      v29 = -1;
    Pool2 = (unsigned __int8 *)ExAllocatePool2(64, v29, 1198089303);
    v76 = Pool2;
    for ( i = 0; ; i = (unsigned int)(v78 + 1) )
    {
      v78 = i;
      if ( (unsigned int)i >= a2->BandInfo.ElementCount )
        break;
      v81 = 56LL * (unsigned int)i;
      v83 = (CPropertyCache *)(80 * i);
      *(_DWORD *)&Pool2[v81] = a2->BandInfo.pElements[i].BandCapabilities.BandID;
      Pool2[v81 + 4] = a2->BandInfo.pElements[i].BandCapabilities.BandState;
      v32 = a2->BandInfo.pElements[i].ValidPhyTypes.ElementCount;
      *(_DWORD *)&Pool2[v81 + 8] = v32;
      v33 = 4 * v32;
      if ( !is_mul_ok(v32, 4u) )
        v33 = -1;
      v34 = (void *)ExAllocatePool2(64, v33, 1198089303);
      *(_QWORD *)&Pool2[v81 + 16] = v34;
      if ( !v34 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_60;
        v43 = *(_DWORD *)&Pool2[v81 + 8];
        v44 = 47;
        goto LABEL_97;
      }
      memmove(
        v34,
        *(const void **)((char *)&v83->m_PropertyTable + (unsigned __int64)a2->BandInfo.pElements),
        4LL * *(unsigned int *)&Pool2[v81 + 8]);
      v36 = *(unsigned int *)((char *)&v83[2].m_PropertyNameMax + (unsigned __int64)a2->BandInfo.pElements);
      *(_DWORD *)&Pool2[v81 + 24] = v36;
      v37 = 4 * v36;
      if ( !is_mul_ok(v36, 4u) )
        v37 = -1;
      v38 = (void *)ExAllocatePool2(64, v37, 1198089303);
      *(_QWORD *)&Pool2[v81 + 32] = v38;
      if ( !v38 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_60;
        v43 = *(_DWORD *)&Pool2[v81 + 24];
        v44 = 48;
        goto LABEL_97;
      }
      memmove(
        v38,
        *(const void **)((char *)&v83[2].m_PropertyTable + (unsigned __int64)a2->BandInfo.pElements),
        4LL * *(unsigned int *)&Pool2[v81 + 24]);
      v39 = *(unsigned int *)((char *)&v83[1].m_PropertyNameMax + (unsigned __int64)a2->BandInfo.pElements);
      *(_DWORD *)&Pool2[v81 + 40] = v39;
      v40 = 8 * v39;
      if ( !is_mul_ok(v39, 8u) )
        v40 = -1;
      v41 = ExAllocatePool2(64, v40, 1198089303);
      v35 = v81;
      *(_QWORD *)&Pool2[v81 + 48] = v41;
      if ( !v41 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_60;
        v43 = *(_DWORD *)&Pool2[v81 + 40];
        v44 = 49;
LABEL_97:
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          v35,
          v44,
          (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
          v43);
        goto LABEL_60;
      }
      for ( j = 0; (unsigned int)j < *(_DWORD *)&Pool2[v81 + 40]; j = (unsigned int)(j + 1) )
      {
        *(_DWORD *)(*(_QWORD *)&Pool2[v81 + 48] + 8 * j) = *(&(*(_WFC_PROPERTY_ENTRY **)((char *)&v83[1].m_PropertyTable
                                                                                       + (unsigned __int64)a2->BandInfo.pElements))->Name
                                                           + 2 * j);
        *(_DWORD *)(*(_QWORD *)&Pool2[v81 + 48] + 8 * j + 4) = *((_DWORD *)&(*(_WFC_PROPERTY_ENTRY **)((char *)&v83[1].m_PropertyTable + (unsigned __int64)a2->BandInfo.pElements))->Type
                                                               + 2 * j);
      }
    }
    if ( !Pool2 || !v75[0] )
    {
LABEL_58:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v70) = v6;
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          1,
          50,
          (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
          v70);
      }
LABEL_60:
      if ( !Pool2 )
        goto LABEL_70;
      goto LABEL_61;
    }
    PropertyListProperty = CPropertyCache::LoadPropertyListProperty(
                             this,
                             2u,
                             v75[0],
                             0x38u,
                             Pool2,
                             &stru_1400EE150,
                             6u,
                             6u);
    v6 = PropertyListProperty;
    if ( PropertyListProperty )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
LABEL_61:
        for ( k = 0; k < a2->BandInfo.ElementCount; ++k )
        {
          v24 = 56LL * k;
          v25 = *(void **)&Pool2[v24 + 16];
          if ( v25 )
            operator delete(v25);
          v26 = *(void **)&Pool2[v24 + 32];
          if ( v26 )
            operator delete(v26);
          v27 = *(void **)&Pool2[v24 + 48];
          if ( v27 )
            operator delete(v27);
        }
        operator delete(Pool2);
LABEL_70:
        if ( v72 )
          operator delete(v72);
        if ( v73 )
          operator delete(v73);
        return v6;
      }
      v47 = 51;
    }
    else
    {
      if ( (*(_DWORD *)&a2->Optional & 0x40) == 0 )
      {
        v72 = 0;
        goto LABEL_61;
      }
      v82 = a2->PhyInfo.ElementCount;
      v48 = 564LL * v82;
      if ( !is_mul_ok(v82, 0x234u) )
        v48 = -1;
      v50 = (unsigned __int8 *)ExAllocatePool2(64, v48, 1198089303);
      v72 = v50;
      if ( a2->PhyInfo.ElementCount )
      {
        v51 = 0;
        do
        {
          v79 = 564LL * v51;
          *(_DWORD *)&v50[v79] = a2->PhyInfo.pElements[v51].PhyCapabilities.PhyType;
          v50[v79 + 4] = a2->PhyInfo.pElements[v51].PhyCapabilities.SupportsCFPoll;
          *(_DWORD *)&v50[v79 + 8] = a2->PhyInfo.pElements[v51].PhyCapabilities.MPDUMaxLength;
          *(_DWORD *)&v50[v79 + 12] = a2->PhyInfo.pElements[v51].PhyCapabilities.TemperatureClass;
          *(_DWORD *)&v50[v79 + 16] = a2->PhyInfo.pElements[v51].PhyCapabilities.DiversitySupport;
          v52 = a2->PhyInfo.pElements[v51].TxPowerLevelList.ElementCount;
          *(_DWORD *)&v50[v79 + 20] = v52;
          memmove(&v50[v79 + 24], a2->PhyInfo.pElements[v51].TxPowerLevelList.pElements, 4LL * v52);
          v50 = v72;
          v53 = 0;
          v54 = a2->PhyInfo.pElements[v51].DataRateList.ElementCount;
          *(_DWORD *)&v72[v79 + 56] = v54;
          if ( v54 )
          {
            do
            {
              v72[564 * v51 + 60 + 4 * v53] = a2->PhyInfo.pElements[v51].DataRateList.pElements[v53].DataRateFlag;
              *(_WORD *)&v72[564 * v51 + 62 + 4 * v53] = a2->PhyInfo.pElements[v51].DataRateList.pElements[v53].DataRateValue;
              v53 = (unsigned int)(v53 + 1);
            }
            while ( (unsigned int)v53 < *(_DWORD *)&v72[564 * v51 + 56] );
          }
          ++v51;
        }
        while ( v51 < a2->PhyInfo.ElementCount );
        Pool2 = v76;
      }
      if ( !v50 || !v82 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v49) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v49,
            1,
            52,
            (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids);
        }
        goto LABEL_61;
      }
      PropertyListProperty = CPropertyCache::LoadPropertyListProperty(
                               this,
                               3u,
                               v82,
                               0x234u,
                               v50,
                               &stru_1400EE0A0,
                               7u,
                               8u);
      v6 = PropertyListProperty;
      if ( PropertyListProperty )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_61;
        v47 = 53;
        goto LABEL_103;
      }
      v55 = 4LL * v82;
      if ( !is_mul_ok(v82, 4u) )
        v55 = -1;
      v73 = (unsigned __int8 *)ExAllocatePool2(64, v55, 1198089303);
      if ( !v73 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v56) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v56,
            1,
            54,
            (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids);
        }
        v6 = -1073741670;
        goto LABEL_61;
      }
      PropertyListProperty = CPropertyCache::GetPropertyPropertyCacheList(this, 3u, &v74);
      v6 = PropertyListProperty;
      if ( PropertyListProperty )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_61;
        v47 = 55;
        goto LABEL_103;
      }
      Next = v74;
      v58 = 0;
      while ( 1 )
      {
        v84 = Next;
        v80 = v58;
        if ( !Next )
          break;
        PropertyListProperty = CPropertyCache::SetPropertyULong(Next, 7u, v58);
        v6 = PropertyListProperty;
        if ( PropertyListProperty )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            goto LABEL_61;
          v47 = 56;
          goto LABEL_103;
        }
        if ( v80 >= v82 )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v46) = 2;
            WPP_RECORDER_SF_Ld(
              WPP_GLOBAL_Control->DeviceExtension,
              v46,
              v59,
              57,
              (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
              v80,
              v82);
          }
          v6 = -1073676267;
          goto LABEL_61;
        }
        PropertyListProperty = CPropertyCache::GetPropertyULong(v84, 0, (unsigned int *)&v73[4 * v80]);
        v6 = PropertyListProperty;
        if ( PropertyListProperty )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            goto LABEL_61;
          v47 = 58;
          goto LABEL_103;
        }
        v58 = v80 + 1;
        Next = v84->Next;
      }
      PropertyListProperty = CPropertyCache::SetPropertyList(this, 4u, 4 * v82, v82, v73);
      v6 = PropertyListProperty;
      if ( !PropertyListProperty )
      {
        if ( (*(_DWORD *)&a2->Optional & 0x400) != 0 )
        {
          v60 = *(_OWORD *)&a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Transmit.Encapsulation;
          v61 = *(_OWORD *)&a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Transmit.UdpChecksum;
          *(_DWORD *)&v77.OffloadScope.LsoV2OffloadSupportedOnAllPorts = *(_DWORD *)&a2->TcpOffloadCapabilities.OffloadScope.LsoV2OffloadSupportedOnAllPorts;
          *(_OWORD *)&v77.ChecksumOffload.ipv4ChecksumOffload.IpV4Transmit.Encapsulation = v60;
          v62 = *(_OWORD *)&a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Receive.TcpOptionsSupported;
          *(_OWORD *)&v77.ChecksumOffload.ipv4ChecksumOffload.IpV4Transmit.UdpChecksum = v61;
          v63 = *(_OWORD *)&a2->TcpOffloadCapabilities.ChecksumOffload.ipv6ChecksumOffload.IpV6Transmit.Encapsulation;
          *(_OWORD *)&v77.ChecksumOffload.ipv4ChecksumOffload.IpV4Receive.TcpOptionsSupported = v62;
          v64 = *(_OWORD *)&a2->TcpOffloadCapabilities.ChecksumOffload.ipv6ChecksumOffload.IpV6Transmit.UdpChecksum;
          *(_OWORD *)&v77.ChecksumOffload.ipv6ChecksumOffload.IpV6Transmit.Encapsulation = v63;
          v65 = *(_OWORD *)&a2->TcpOffloadCapabilities.ChecksumOffload.ipv6ChecksumOffload.IpV6Receive.TcpChecksum;
          *(_OWORD *)&v77.ChecksumOffload.ipv6ChecksumOffload.IpV6Transmit.UdpChecksum = v64;
          v66 = *(_OWORD *)&a2->TcpOffloadCapabilities.LsoV1Capabilities.MinSegmentCount;
          *(_OWORD *)&v77.ChecksumOffload.ipv6ChecksumOffload.IpV6Receive.TcpChecksum = v65;
          v67 = *(_OWORD *)&a2->TcpOffloadCapabilities.LsoV2Capabilities.Ipv4LSO.MaxOffloadSizeV4;
          *(_OWORD *)&v77.LsoV1Capabilities.MinSegmentCount = v66;
          v68 = *(_OWORD *)&a2->TcpOffloadCapabilities.LsoV2Capabilities.Ipv6LSO.MinSegmentCountV6;
          *(_OWORD *)&v77.LsoV2Capabilities.Ipv4LSO.MaxOffloadSizeV4 = v67;
          *(_OWORD *)&v77.LsoV2Capabilities.Ipv6LSO.MinSegmentCountV6 = v68;
          PropertyListProperty = CAdapterPropertyCache::PopulateTcpOffloadCapabilities(this, &v77);
          v6 = PropertyListProperty;
          if ( PropertyListProperty )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
              goto LABEL_61;
            v47 = 60;
            goto LABEL_103;
          }
          if ( a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Receive.Encapsulation
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Transmit.Encapsulation
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv6ChecksumOffload.IpV6Receive.Encapsulation
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv6ChecksumOffload.IpV6Transmit.Encapsulation
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Receive.IpChecksum
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Receive.TcpChecksum
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Receive.UdpChecksum
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Transmit.IpChecksum
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Transmit.TcpChecksum
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv4ChecksumOffload.IpV4Transmit.UdpChecksum
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv6ChecksumOffload.IpV6Receive.TcpChecksum
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv6ChecksumOffload.IpV6Receive.UdpChecksum
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv6ChecksumOffload.IpV6Transmit.TcpChecksum
            || a2->TcpOffloadCapabilities.ChecksumOffload.ipv6ChecksumOffload.IpV6Transmit.UdpChecksum
            || a2->TcpOffloadCapabilities.LsoV1Capabilities.Encapsulation
            || a2->TcpOffloadCapabilities.LsoV2Capabilities.Ipv4LSO.EncapsulationV4
            || a2->TcpOffloadCapabilities.LsoV2Capabilities.Ipv6LSO.EncapsulationV6
            || a2->TcpOffloadCapabilities.ReceiveOffloadCapabilities.Ipv4Enabled )
          {
            CPropertyCache::SetPropertyBoolean(this, 0x89u, 1u);
          }
        }
        if ( (*(_DWORD *)&a2->Optional & 0x800) != 0 )
        {
          v69 = a2->SupportedGuids.ElementCount;
          if ( v69 )
          {
            PropertyListProperty = CPropertyCache::SetPropertyList(
                                     this,
                                     0x75u,
                                     28 * v69,
                                     a2->SupportedGuids.ElementCount,
                                     (unsigned __int8 *)a2->SupportedGuids.pElements);
            v6 = PropertyListProperty;
            if ( PropertyListProperty )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                v47 = 61;
                goto LABEL_103;
              }
            }
          }
        }
        goto LABEL_61;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_61;
      v47 = 59;
    }
LABEL_103:
    LODWORD(v71) = PropertyListProperty;
    LOBYTE(v46) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v46,
      1,
      v47,
      (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
      v71);
    goto LABEL_61;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v7 = 31;
LABEL_4:
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      v7,
      (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1400a6e14  mov     [rsp-8+arg_0], rbx
0x1400a6e19  push    rbp
0x1400a6e1a  push    rsi
0x1400a6e1b  push    rdi
0x1400a6e1c  push    r12
0x1400a6e1e  push    r13
0x1400a6e20  push    r14
0x1400a6e22  push    r15
0x1400a6e24  lea     rbp, [rsp-30h]
0x1400a6e29  sub     rsp, 130h
0x1400a6e30  mov     r8d, [rdx+8]; unsigned int
0x1400a6e34  mov     rbx, rdx
0x1400a6e37  mov     edx, 10h; unsigned int
0x1400a6e3c  mov     [rsp+160h+var_F0], 0
0x1400a6e45  mov     r13, rcx
0x1400a6e48  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x1400a6e4d  mov     edi, eax
0x1400a6e4f  test    eax, eax
0x1400a6e51  jz      short loc_1400A6E96
0x1400a6e53  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a6e5a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a6e61  jz      loc_1400A738E
0x1400a6e67  mov     r9d, 1Fh
0x1400a6e6d  lea     r15, WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids
0x1400a6e74  mov     r8d, 1
0x1400a6e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6e81  mov     dl, 2
0x1400a6e83  mov     [rsp+160h+var_140], r15
0x1400a6e88  mov     rcx, [rcx+40h]
0x1400a6e8c  call    WPP_RECORDER_SF_
0x1400a6e91  jmp     loc_1400A738E
0x1400a6e96  mov     r8d, [rbx+18h]; unsigned int
0x1400a6e9a  mov     edx, 11h; unsigned int
0x1400a6e9f  mov     rcx, r13; this
0x1400a6ea2  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x1400a6ea7  mov     edi, eax
0x1400a6ea9  test    eax, eax
0x1400a6eab  jz      short loc_1400A6EC9
0x1400a6ead  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a6eb4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a6ebb  jz      loc_1400A738E
0x1400a6ec1  mov     r9d, 20h ; ' '
0x1400a6ec7  jmp     short loc_1400A6E6D
0x1400a6ec9  movzx   r8d, word ptr [rbx+1Ch]; unsigned int
0x1400a6ece  mov     edx, 6Eh ; 'n'; unsigned int
0x1400a6ed3  mov     rcx, r13; this
0x1400a6ed6  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x1400a6edb  mov     edi, eax
0x1400a6edd  test    eax, eax
0x1400a6edf  jz      short loc_1400A6F00
0x1400a6ee1  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a6ee8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a6eef  jz      loc_1400A738E
0x1400a6ef5  mov     r9d, 21h ; '!'
0x1400a6efb  jmp     loc_1400A6E6D
0x1400a6f00  mov     r8b, [rbx+30h]; unsigned __int8
0x1400a6f04  mov     edx, 1Ah; unsigned int
0x1400a6f09  mov     rcx, r13; this
0x1400a6f0c  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x1400a6f11  mov     edi, eax
0x1400a6f13  test    eax, eax
0x1400a6f15  jz      short loc_1400A6F36
0x1400a6f17  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a6f1e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a6f25  jz      loc_1400A738E
0x1400a6f2b  mov     r9d, 22h ; '"'
0x1400a6f31  jmp     loc_1400A6E6D
0x1400a6f36  mov     r8b, [rbx+36h]; unsigned __int8
0x1400a6f3a  mov     edx, 1Bh; unsigned int
0x1400a6f3f  mov     rcx, r13; this
0x1400a6f42  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x1400a6f47  mov     edi, eax
0x1400a6f49  test    eax, eax
0x1400a6f4b  jz      short loc_1400A6F6C
0x1400a6f4d  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a6f54  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a6f5b  jz      loc_1400A738E
0x1400a6f61  mov     r9d, 23h ; '#'
0x1400a6f67  jmp     loc_1400A6E6D
0x1400a6f6c  mov     r8b, [rbx+44h]; unsigned __int8
0x1400a6f70  mov     edx, 1Ch; unsigned int
0x1400a6f75  mov     rcx, r13; this
0x1400a6f78  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x1400a6f7d  mov     edi, eax
0x1400a6f7f  test    eax, eax
0x1400a6f81  jz      short loc_1400A6FA2
0x1400a6f83  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a6f8a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a6f91  jz      loc_1400A738E
0x1400a6f97  mov     r9d, 24h ; '$'
0x1400a6f9d  jmp     loc_1400A6E6D
0x1400a6fa2  mov     eax, [rbx]
0x1400a6fa4  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400a6fab  lea     r15, WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids
0x1400a6fb2  mov     edi, 4
0x1400a6fb7  lea     r14d, [rdi-3]
0x1400a6fbb  test    al, 8
0x1400a6fbd  jz      loc_1400A7103
0x1400a6fc3  movzx   r10d, byte ptr [rbx+160h]
0x1400a6fcb  lea     eax, [rdi+30h]
0x1400a6fce  movzx   r9d, byte ptr [rbx+161h]
0x1400a6fd6  lea     ecx, [rdi+10h]
0x1400a6fd9  test    r10b, r10b
0x1400a6fdc  cmovz   eax, ecx
0x1400a6fdf  mov     edi, eax; __annotation("TMF:",
0x1400a6fe1  or      edi, 40h
0x1400a6fe4  test    r9b, r9b
0x1400a6fe7  cmovz   edi, eax
0x1400a6fea  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a6ff1  jz      loc_1400A70A7
0x1400a6ff7  movzx   eax, byte ptr [rbx+177h]
0x1400a6ffe  movzx   ecx, byte ptr [rbx+176h]
0x1400a7005  movzx   edx, byte ptr [rbx+175h]
0x1400a700c  movzx   r8d, byte ptr [rbx+168h]
0x1400a7014  mov     [rsp+160h+var_108], eax
0x1400a7018  mov     eax, [rbx+164h]
0x1400a701e  mov     [rsp+160h+var_110], ecx
0x1400a7022  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7029  mov     [rsp+160h+var_118], edx
0x1400a702d  mov     [rsp+160h+var_120], r8d
0x1400a7032  mov     [rsp+160h+var_128], eax
0x1400a7036  mov     rcx, [rcx+40h]
0x1400a703a  mov     [rsp+160h+var_130], r9d
0x1400a703f  mov     dword ptr [rsp+160h+var_138], r10d
0x1400a7044  call    WPP_RECORDER_SF_dddDDDd
0x1400a7049  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a7050  jz      short loc_1400A70A7
0x1400a7052  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7059  lea     rax, [rbx+178h]
0x1400a7060  mov     [rsp+160h+var_138], rax
0x1400a7065  lea     r9d, [r14+25h]
0x1400a7069  mov     dl, 4
0x1400a706b  mov     [rsp+160h+var_140], r15
0x1400a7070  mov     rcx, [rcx+40h]
0x1400a7074  call    WPP_RECORDER_SF__MAC_
0x1400a7079  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a7080  jz      short loc_1400A70A7
0x1400a7082  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7089  lea     r9d, [r14+26h]
0x1400a708d  mov     eax, [rbx+198h]
0x1400a7093  mov     dl, 4
0x1400a7095  mov     dword ptr [rsp+160h+var_138], eax
0x1400a7099  mov     [rsp+160h+var_140], r15
0x1400a709e  mov     rcx, [rcx+40h]
0x1400a70a2  call    WPP_RECORDER_SF_d
0x1400a70a7  mov     eax, [rbx+198h]
0x1400a70ad  test    eax, eax
0x1400a70af  jz      short loc_1400A7103
0x1400a70b1  xor     r12d, r12d
0x1400a70b4  test    eax, eax
0x1400a70b6  jz      short loc_1400A7103
0x1400a70b8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a70bf  jz      short loc_1400A70F7
0x1400a70c1  mov     rax, [rbx+1A0h]
0x1400a70c8  lea     rcx, [r12+r12*2]
0x1400a70cc  mov     r9d, 28h ; '('
0x1400a70d2  lea     rdx, [rax+rcx*2]
0x1400a70d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a70dd  mov     qword ptr [rsp+160h+var_130], rdx
0x1400a70e2  mov     dl, 4
0x1400a70e4  mov     dword ptr [rsp+160h+var_138], r12d
0x1400a70e9  mov     [rsp+160h+var_140], r15
0x1400a70ee  mov     rcx, [rcx+40h]
0x1400a70f2  call    WPP_RECORDER_SF_d_MAC_
0x1400a70f7  add     r12d, r14d
0x1400a70fa  cmp     r12d, [rbx+198h]
0x1400a7101  jb      short loc_1400A70B8
0x1400a7103  mov     r8d, edi; unsigned int
0x1400a7106  mov     edx, 13h; unsigned int
0x1400a710b  mov     rcx, r13; this
0x1400a710e  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x1400a7113  mov     edi, eax
0x1400a7115  test    eax, eax
0x1400a7117  jz      short loc_1400A7134
0x1400a7119  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a7120  jz      loc_1400A738E
0x1400a7126  mov     r9d, 29h ; ')'
0x1400a712c  mov     r8d, r14d
0x1400a712f  jmp     loc_1400A6E7A
0x1400a7134  mov     r8b, [rbx+4Ch]; unsigned __int8
0x1400a7138  mov     edx, 8Fh; unsigned int
0x1400a713d  mov     rcx, r13; this
0x1400a7140  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x1400a7145  mov     edi, eax
0x1400a7147  test    eax, eax
0x1400a7149  jz      short loc_1400A7160
0x1400a714b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a7152  jz      loc_1400A738E
0x1400a7158  mov     r9d, 2Ah ; '*'
0x1400a715e  jmp     short loc_1400A712C
0x1400a7160  mov     [rsp+160h+var_130], 91h; unsigned int
0x1400a7168  lea     rax, stru_1400EE360
0x1400a716f  lea     r12, [rbx+80h]
0x1400a7176  mov     dword ptr [rsp+160h+var_138], 0Dh; unsigned int
0x1400a717e  lea     r9, [r12+4]; unsigned __int8 *
0x1400a7183  mov     [rsp+160h+var_140], rax; struct _WFC_PROPERTY_LOAD_INFO *
0x1400a7188  mov     r8d, 38h ; '8'; unsigned int
0x1400a718e  mov     rdx, r13; struct CPropertyCache *
0x1400a7191  call    ?LoadProperties@CPropertyCache@@IEAAHPEAV1@IPEAEPEBU_WFC_PROPERTY_LOAD_INFO@@KI@Z; CPropertyCache::LoadProperties(CPropertyCache *,uint,uchar *,_WFC_PROPERTY_LOAD_INFO const *,ulong,uint)
0x1400a7196  mov     edi, eax
0x1400a7198  test    eax, eax
0x1400a719a  jz      short loc_1400A71D2
0x1400a719c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a71a3  jz      loc_1400A738E
0x1400a71a9  mov     r9d, 2Bh ; '+'
0x1400a71af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a71b6  mov     r8d, r14d
0x1400a71b9  mov     dword ptr [rsp+160h+var_138], eax
0x1400a71bd  mov     dl, 2
0x1400a71bf  mov     [rsp+160h+var_140], r15
0x1400a71c4  mov     rcx, [rcx+40h]
0x1400a71c8  call    WPP_RECORDER_SF_D
0x1400a71cd  jmp     loc_1400A738E
0x1400a71d2  mov     eax, [r12]
0x1400a71d6  test    r14b, al
0x1400a71d9  jz      short loc_1400A7223
0x1400a71db  mov     [rsp+160h+var_130], 91h; unsigned int
0x1400a71e3  lea     rax, stru_1400EE348
0x1400a71ea  mov     dword ptr [rsp+160h+var_138], r14d; unsigned int
0x1400a71ef  mov     r9, r12; unsigned __int8 *
0x1400a71f2  mov     r8d, 88h; unsigned int
0x1400a71f8  mov     [rsp+160h+var_140], rax; struct _WFC_PROPERTY_LOAD_INFO *
0x1400a71fd  mov     rdx, r13; struct CPropertyCache *
0x1400a7200  call    ?LoadProperties@CPropertyCache@@IEAAHPEAV1@IPEAEPEBU_WFC_PROPERTY_LOAD_INFO@@KI@Z; CPropertyCache::LoadProperties(CPropertyCache *,uint,uchar *,_WFC_PROPERTY_LOAD_INFO const *,ulong,uint)
0x1400a7205  mov     edi, eax
0x1400a7207  test    eax, eax
0x1400a7209  jz      short loc_1400A7223
0x1400a720b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a7212  jz      loc_1400A738E
0x1400a7218  mov     r9d, 2Ch ; ','
0x1400a721e  jmp     loc_1400A712C
0x1400a7223  mov     eax, [r12]
0x1400a7227  test    al, 2
0x1400a7229  jz      short loc_1400A7273
0x1400a722b  mov     [rsp+160h+var_130], 91h; unsigned int
0x1400a7233  lea     rax, stru_1400EE330
0x1400a723a  mov     dword ptr [rsp+160h+var_138], r14d; unsigned int
0x1400a723f  mov     r9, r12; unsigned __int8 *
0x1400a7242  mov     r8d, 88h; unsigned int
0x1400a7248  mov     [rsp+160h+var_140], rax; struct _WFC_PROPERTY_LOAD_INFO *
0x1400a724d  mov     rdx, r13; struct CPropertyCache *
0x1400a7250  call    ?LoadProperties@CPropertyCache@@IEAAHPEAV1@IPEAEPEBU_WFC_PROPERTY_LOAD_INFO@@KI@Z; CPropertyCache::LoadProperties(CPropertyCache *,uint,uchar *,_WFC_PROPERTY_LOAD_INFO const *,ulong,uint)
0x1400a7255  mov     edi, eax
0x1400a7257  test    eax, eax
0x1400a7259  jz      short loc_1400A7273
0x1400a725b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a7262  jz      loc_1400A738E
0x1400a7268  mov     r9d, 2Dh ; '-'
0x1400a726e  jmp     loc_1400A712C
0x1400a7273  mov     eax, [rbx]
0x1400a7275  test    al, al
0x1400a7277  jns     short loc_1400A72C8
0x1400a7279  mov     [rsp+160h+var_130], 91h; unsigned int
0x1400a7281  lea     rax, stru_1400EE1E0
0x1400a7288  mov     dword ptr [rsp+160h+var_138], 0Eh; unsigned int
0x1400a7290  lea     r9, [rbx+1F8h]; unsigned __int8 *
0x1400a7297  mov     r8d, 38h ; '8'; unsigned int
0x1400a729d  mov     [rsp+160h+var_140], rax; struct _WFC_PROPERTY_LOAD_INFO *
0x1400a72a2  mov     rdx, r13; struct CPropertyCache *
0x1400a72a5  call    ?LoadProperties@CPropertyCache@@IEAAHPEAV1@IPEAEPEBU_WFC_PROPERTY_LOAD_INFO@@KI@Z; CPropertyCache::LoadProperties(CPropertyCache *,uint,uchar *,_WFC_PROPERTY_LOAD_INFO const *,ulong,uint)
0x1400a72aa  mov     edi, eax
0x1400a72ac  test    eax, eax
0x1400a72ae  jz      short loc_1400A72C8
0x1400a72b0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a72b7  jz      loc_1400A738E
0x1400a72bd  mov     r9d, 2Eh ; '.'
0x1400a72c3  jmp     loc_1400A71AF
0x1400a72c8  xor     eax, eax
0x1400a72ca  mov     [rsp+160h+var_100], rax
0x1400a72cf  mov     [rsp+160h+var_F8], rax
0x1400a72d4  mov     eax, [rbx]
0x1400a72d6  test    al, 20h
0x1400a72d8  jnz     loc_1400A73AC
0x1400a72de  xor     r12d, r12d
0x1400a72e1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a72e8  jz      short loc_1400A730E
0x1400a72ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a72f1  mov     r9d, 32h ; '2'
0x1400a72f7  mov     dword ptr [rsp+160h+var_138], edi
0x1400a72fb  mov     r8d, r14d
0x1400a72fe  mov     dl, 2
0x1400a7300  mov     [rsp+160h+var_140], r15
0x1400a7305  mov     rcx, [rcx+40h]
0x1400a7309  call    WPP_RECORDER_SF_D
0x1400a730e  test    r12, r12
0x1400a7311  jz      short loc_1400A736A
0x1400a7313  xor     r15d, r15d
0x1400a7316  mov     rsi, r12
0x1400a7319  cmp     [rbx+1C8h], r15d
0x1400a7320  jbe     short loc_1400A7362
0x1400a7322  mov     eax, r15d
0x1400a7325  imul    r13, rax, 38h ; '8'
0x1400a7329  mov     rcx, [rsi+r13+10h]; void *
0x1400a732e  test    rcx, rcx
0x1400a7331  jz      short loc_1400A7338
0x1400a7333  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400a7338  mov     rcx, [rsi+r13+20h]; void *
0x1400a733d  test    rcx, rcx
0x1400a7340  jz      short loc_1400A7347
0x1400a7342  call    ??3@YAXPEAX@Z; operator delete(void *)
  ... truncated ...
```
