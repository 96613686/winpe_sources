# CSetDefaultKeyJob::GetDeviceCommandData(void *,uint,uint *,uint *,uint,ulong *,ulong *,uchar * *)

- ea: `0x1400aede0`
- end: `0x1400af6d9`
- name: `?GetDeviceCommandData@CSetDefaultKeyJob@@UEAAHPEAXIPEAI1IPEAK2PEAPEAE@Z`
- size: `2297`
- prototype: `__int64 __usercall@<rax>(CSetDefaultKeyJob *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140010390`
- `0x1400109a0`
- `0x1400122e0`
- `0x140013000`
- `0x1400147e8`
- `0x14001a808`
- `0x14001a8e0`
- `0x14001aedc`
- `0x140021280`
- `0x140023ae0`
- `0x140024928`
- `0x1400297a0`
- `0x14002aa28`
- `0x140034e04`
- `0x14004b680`
- `0x14004b6c4`
- `0x14004f5e8`
- `0x14004ff88`
- `0x14008c9c8`
- `0x14008cc08`
- `0x1400ac754`
- `0x1400aede0`
- `0x1400b6014`
- `0x1400b6718`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400aeff1`
- `ntoskrnl!ExAllocatePool2` at `0x1400af3f2`
- `ntoskrnl!ExAllocatePool2` at `0x1400aeff1`
- `ntoskrnl!ExAllocatePool2` at `0x1400af3f2`

## pseudocode

```c
__int64 __fastcall CSetDefaultKeyJob::GetDeviceCommandData(
        CSetDefaultKeyJob *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int8 **a9)
{
  unsigned __int16 m_PortId; // dx
  CAdapter *m_pAdapter; // rcx
  int v15; // edx
  struct CPort *PortFromPortId; // r14
  __int64 *v17; // r8
  unsigned int *v18; // rcx
  int v19; // edx
  unsigned int v20; // eax
  unsigned int PropertyList; // esi
  int v22; // r9d
  unsigned int v23; // ecx
  int v24; // r15d
  struct DOT11_CONNECTION_INFO *CurrentConnectionInfo; // rax
  _QWORD *Pool2; // rax
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v27; // rsi
  int v28; // r9d
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int *v31; // rbx
  int v32; // r9d
  unsigned int v33; // edx
  unsigned int WdiSetAddCipherKeysToIhv; // eax
  int v35; // r9d
  void *v36; // rax
  void *v37; // rsi
  int v38; // ecx
  enum _WDI_P2P_SCAN_TYPE v39; // eax
  int v40; // r9d
  unsigned int v41; // edx
  _WORD *v42; // rcx
  unsigned int v43; // eax
  _ROAM_TRACELOGGING_DATA *m_pRoamTraceLoggingData; // rax
  struct CPortPropertyCache *PortPropertyCache; // rax
  unsigned __int8 PropertyBooleanOrDefault; // al
  struct CPortPropertyCache *v47; // rax
  __int128 v48; // xmm1
  int v49; // eax
  unsigned __int8 **v51; // [rsp+20h] [rbp-C1h]
  unsigned __int8 **v52; // [rsp+20h] [rbp-C1h]
  unsigned int m_ActivityId; // [rsp+30h] [rbp-B1h]
  __int64 v54; // [rsp+38h] [rbp-A9h]
  char v55; // [rsp+40h] [rbp-A1h]
  unsigned __int8 *v56[2]; // [rsp+70h] [rbp-71h] BYREF
  int v57; // [rsp+80h] [rbp-61h] BYREF
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v58; // [rsp+88h] [rbp-59h]
  char v59; // [rsp+90h] [rbp-51h]
  int v60; // [rsp+98h] [rbp-49h] BYREF
  void *v61; // [rsp+A0h] [rbp-41h]
  char v62; // [rsp+A8h] [rbp-39h]
  struct _DOT11_SSID v63; // [rsp+B0h] [rbp-31h] BYREF

  m_PortId = this->m_PortId;
  m_pAdapter = this->m_pAdapter;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  PortFromPortId = CAdapter::GetPortFromPortId(m_pAdapter, m_PortId);
  v17 = WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v15) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      (unsigned int)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      57,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId);
    v17 = WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids;
  }
  v18 = a5;
  *a4 = 0;
  *v18 = 0;
  v19 = *(unsigned __int8 *)a2;
  if ( (_BYTE)v19 != 0x80 || !*((_BYTE *)a2 + 1) || a2[1] < 0x18u )
  {
    PropertyList = -1073676267;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qDDddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        (unsigned int)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
        58,
        (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
        (char)this,
        this->m_ActivityId,
        128,
        1,
        24,
        v19,
        *((_BYTE *)a2 + 1),
        a2[1]);
    goto LABEL_75;
  }
  v20 = a2[10] + 22;
  *v18 = v20;
  if ( a3 < v20 )
  {
    PropertyList = -2147483643;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_75;
    v22 = 59;
    v55 = a3;
    goto LABEL_11;
  }
  *a4 = v20;
  v23 = *((_DWORD *)a2 + 1);
  if ( v23 > 3 )
  {
    if ( v23 - 4 <= 1 )
    {
      v24 = 3;
      if ( !*((_BYTE *)a2 + 18) )
      {
        CurrentConnectionInfo = CPort::GetCurrentConnectionInfo(PortFromPortId);
        if ( CurrentConnectionInfo )
        {
          CurrentConnectionInfo->CurrentConnectionFlags |= 4u;
          CPropertyCache::SetPropertyBuffer(
            &PortFromPortId->m_PortPropertyCache,
            0x27u,
            CurrentConnectionInfo->AvailableSize,
            (unsigned __int8 *)CurrentConnectionInfo);
        }
      }
    }
    else
    {
      if ( v23 - 6 > 1 )
      {
        PropertyList = -1073676267;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v20 = *((_DWORD *)a2 + 2);
          v22 = 60;
          v55 = *((_DWORD *)a2 + 1);
LABEL_11:
          LOBYTE(v19) = 2;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v19,
            (unsigned int)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
            v22,
            (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
            (char)this,
            this->m_ActivityId,
            v20,
            v55);
          goto LABEL_75;
        }
        goto LABEL_75;
      }
      v24 = 4;
    }
  }
  else
  {
    v24 = 2;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 4;
    WPP_RECORDER_SF_qDddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      (_DWORD)v17,
      61,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId,
      v24,
      *((_DWORD *)a2 + 2),
      *((_DWORD *)a2 + 1));
  }
  if ( !*((_BYTE *)a2 + 18) )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 264, 1198089303);
    if ( Pool2 )
    {
      v27 = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER *)(Pool2 + 1);
      *Pool2 = 1;
      `vector constructor iterator'(
        Pool2 + 1,
        0x100u,
        1u,
        (void *(*)(void *))_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER);
      v58 = v27;
    }
    else
    {
      v27 = 0;
      v58 = 0;
    }
    if ( !v27 )
    {
      PropertyList = -1073741670;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_77;
      v28 = 62;
      goto LABEL_31;
    }
    v57 = 1;
    *(_DWORD *)&v27->Optional &= ~1u;
    v58->CipherKeyTypeInfo.Direction = CDot11ToWabiConverter::MapP2PScanType(dot11_wfd_scan_type_auto);
    v58->CipherKeyTypeInfo.KeyType = v24;
    v58->CipherKeyTypeInfo.CipherAlgorithm = CDot11ToWabiConverter::MapCipherAlgorithm(*((enum _DOT11_CIPHER_ALGORITHM *)a2
                                                                                       + 2));
    v58->CipherKeyTypeInfo.Static = *((_BYTE *)a2 + 19);
    *(_DWORD *)&v58->Optional |= 2u;
    v58->CipherKeyID.CipherKeyID = *((_DWORD *)a2 + 1);
    *(_DWORD *)&v58->Optional &= ~8u;
    v29 = *(_DWORD *)&v58->Optional & 0xFFFFFFEF;
    v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v29;
    v29 &= ~0x20u;
    v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v29;
    v29 &= ~0x80u;
    v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v29;
    v29 &= ~0x40u;
    v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v29;
    v29 &= ~0x400u;
    v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v29;
    v30 = v29 & 0xFFFFFEFF;
    v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v30;
    LODWORD(v17) = *((_DWORD *)a2 + 2);
    if ( (_DWORD)v17 == 1 )
      goto LABEL_50;
    switch ( *((_DWORD *)a2 + 2) )
    {
      case 2:
        v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v30 | 4);
        v58->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(a2 + 11);
        *(_DWORD *)&v58->Optional |= 0x20u;
        v58->TKIPInfo.TKIPKey.ElementCount = a2[15];
        v58->TKIPInfo.TKIPKey.pElements = (unsigned __int8 *)(a2 + 19);
        v58->TKIPInfo.TKIPMIC.ElementCount = a2[17];
        v58->TKIPInfo.TKIPMIC.pElements = (unsigned __int8 *)a2 + *(unsigned int *)(a2 + 15) + 38;
        goto LABEL_51;
      case 4:
        v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v30 | 4);
        v58->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(a2 + 11);
        *(_DWORD *)&v58->Optional |= 8u;
        v58->CCMPKey.ElementCount = a2[15];
        v58->CCMPKey.pElements = (unsigned __int8 *)(a2 + 17);
        goto LABEL_51;
      case 5:
        goto LABEL_50;
      case 6:
        v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v30 | 4);
        v58->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(a2 + 11);
        *(_DWORD *)&v58->Optional |= 0x40u;
        v58->BIPKey.ElementCount = a2[15];
        v58->BIPKey.pElements = (unsigned __int8 *)(a2 + 17);
        goto LABEL_51;
      case 8:
        v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v30 | 4);
        v58->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(a2 + 11);
        *(_DWORD *)&v58->Optional |= 0x10u;
        v58->GCMPKey.ElementCount = a2[15];
        v58->GCMPKey.pElements = (unsigned __int8 *)(a2 + 17);
        goto LABEL_51;
      case 9:
        v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v30 | 4);
        v58->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(a2 + 11);
        *(_DWORD *)&v58->Optional |= 0x200u;
        v58->GCMP_256Key.ElementCount = a2[15];
        v58->GCMP_256Key.pElements = (unsigned __int8 *)(a2 + 17);
        goto LABEL_51;
    }
    v19 = *((_DWORD *)a2 + 2) - 12;
    if ( *((_DWORD *)a2 + 2) == 12 )
    {
      v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v30 | 4);
      v58->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(a2 + 11);
      *(_DWORD *)&v58->Optional |= 0x400u;
      v58->BIP_GMAC_256Key.ElementCount = a2[15];
      v58->BIP_GMAC_256Key.pElements = (unsigned __int8 *)(a2 + 17);
      goto LABEL_51;
    }
    if ( *((_DWORD *)a2 + 2) == 257 )
    {
LABEL_50:
      v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v30 | 0x80);
      v58->WEPKey.ElementCount = a2[10];
      v58->WEPKey.pElements = (unsigned __int8 *)(a2 + 11);
    }
    else
    {
      if ( (int)v17 > -1 )
      {
        PropertyList = -1073676267;
        goto LABEL_75;
      }
      v58->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v30 | 0x100);
      v58->IHVKey.ElementCount = a2[10];
      v58->IHVKey.pElements = (unsigned __int8 *)(a2 + 11);
    }
LABEL_51:
    v31 = a7;
    v32 = (int)a8;
    v33 = a6;
    v51 = a9;
    *a7 = 29;
    WdiSetAddCipherKeysToIhv = GenerateWdiSetAddCipherKeysToIhv(
                                 (unsigned int)&v57,
                                 v33,
                                 (unsigned int)this->m_pAdapter + 16376,
                                 v32,
                                 (__int64)v51);
    PropertyList = WdiSetAddCipherKeysToIhv;
    if ( WdiSetAddCipherKeysToIhv )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_75;
      v35 = 63;
      LODWORD(v54) = WdiSetAddCipherKeysToIhv;
      m_ActivityId = this->m_ActivityId;
      goto LABEL_54;
    }
LABEL_64:
    m_pRoamTraceLoggingData = PortFromPortId->m_pRoamTraceLoggingData;
    if ( m_pRoamTraceLoggingData && m_pRoamTraceLoggingData->taskOccured )
    {
      PortFromPortId->m_pRoamTraceLoggingData->setCipherKeysTime = MEMORY[0xFFFFF78000000014];
      CPort::TraceLoggingRoamFinished(PortFromPortId, 0);
    }
    PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
    PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(PortPropertyCache, 0x14u, 0);
    if ( *v31 == 29 )
    {
      if ( PropertyBooleanOrDefault )
      {
        LODWORD(a5) = 0;
        *(_OWORD *)v56 = 0;
        v47 = COidJobBase::GetPortPropertyCache(this);
        PropertyList = CPropertyCache::GetPropertyList(v47, 5u, (unsigned int *)&a5, (unsigned __int16 *)v56, &v56[1]);
        if ( !PropertyList )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = 4;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v19,
              PropertyList + 1,
              66,
              (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids);
          }
          v48 = *((_OWORD *)v56[1] + 1);
          v49 = *((_DWORD *)v56[1] + 8);
          *(_OWORD *)&v63.uSSIDLength = *(_OWORD *)v56[1];
          *(_OWORD *)&v63.ucSSID[12] = v48;
          *(_DWORD *)&v63.ucSSID[28] = v49;
          CPort::UnBlockSSIDFor11r(PortFromPortId, &v63, (enum _WFC_BLOCKED_REASON)v17);
        }
      }
    }
    goto LABEL_75;
  }
  v36 = (void *)ExAllocatePool2(64, 32, 1198089303);
  v37 = v36;
  if ( v36 )
  {
    `vector constructor iterator'(
      v36,
      0x20u,
      1u,
      (void *(*)(void *))_WDI_SET_DELETE_CIPHER_KEYS_CONTAINER::_WDI_SET_DELETE_CIPHER_KEYS_CONTAINER);
    v61 = v37;
  }
  else
  {
    v61 = 0;
  }
  if ( v61 )
  {
    v38 = *((_DWORD *)a2 + 1);
    v60 = 1;
    *((_DWORD *)v61 + 3) = v38;
    *((_DWORD *)v61 + 4) = CDot11ToWabiConverter::MapCipherAlgorithm(*((enum _DOT11_CIPHER_ALGORITHM *)a2 + 2));
    v39 = CDot11ToWabiConverter::MapP2PScanType(dot11_wfd_scan_type_auto);
    v40 = (int)a8;
    v41 = a6;
    *((_DWORD *)v61 + 5) = v39;
    *((_DWORD *)v61 + 7) = v24;
    *((_BYTE *)v61 + 24) = *((_BYTE *)a2 + 19);
    v42 = v61;
    *((_DWORD *)v61 + 1) = *((_DWORD *)a2 + 3);
    LOWORD(v39) = a2[8];
    v31 = a7;
    v42[4] = v39;
    v52 = a9;
    *v31 = 30;
    v43 = GenerateWdiSetDeleteCipherKeysToIhv(
            (unsigned int)&v60,
            v41,
            (unsigned int)this->m_pAdapter + 16376,
            v40,
            (__int64)v52);
    PropertyList = v43;
    if ( !v43 )
      goto LABEL_64;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v54) = v43;
      v35 = 65;
      m_ActivityId = this->m_ActivityId;
LABEL_54:
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        (_DWORD)v17,
        v35,
        (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
        (char)this,
        m_ActivityId,
        v54);
    }
  }
  else
  {
    PropertyList = -1073741670;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v28 = 64;
LABEL_31:
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        (_DWORD)v17,
        v28,
        (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
  }
LABEL_75:
  if ( v58 )
    _WDI_SET_ADD_CIPHER_KEYS_CONTAINER::`vector deleting destructor'(v58, 3u);
LABEL_77:
  if ( v61 )
    operator delete(v61);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v19) = 5;
    LODWORD(v54) = PropertyList;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      (_DWORD)v17,
      67,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId,
      v54);
  }
  ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(&v60);
  ArrayOfElements<_WDI_SET_ADD_CIPHER_KEYS_CONTAINER>::Cleanup(&v57);
  return PropertyList;
}

```

## disassembly

```asm
0x1400aede0  push    rbp
0x1400aede2  push    rbx
0x1400aede3  push    rsi
0x1400aede4  push    rdi
0x1400aede5  push    r12
0x1400aede7  push    r13
0x1400aede9  push    r14
0x1400aedeb  push    r15
0x1400aeded  lea     rbp, [rsp-7]
0x1400aedf2  sub     rsp, 0E8h
0x1400aedf9  xor     r12d, r12d
0x1400aedfc  mov     rbx, rdx
0x1400aedff  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x1400aee03  mov     rdi, rcx
0x1400aee06  mov     rcx, [rcx+200h]; this
0x1400aee0d  mov     rsi, r9
0x1400aee10  mov     r15d, r8d
0x1400aee13  mov     [rbp+3Fh+var_A0], r12d
0x1400aee17  mov     [rbp+3Fh+var_98], r12
0x1400aee1b  mov     [rbp+3Fh+var_90], r12b
0x1400aee1f  mov     [rbp+3Fh+var_88], r12d
0x1400aee23  mov     [rbp+3Fh+var_80], r12
0x1400aee27  mov     [rbp+3Fh+var_78], r12b
0x1400aee2b  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400aee30  mov     r14, rax
0x1400aee33  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400aee3a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400aee41  lea     r8, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x1400aee48  jz      short loc_1400AEE87
0x1400aee4a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aee51  cmp     byte ptr [rcx+29h], 5
0x1400aee55  jnb     short loc_1400AEE5E
0x1400aee57  cmp     [rcx+48h], r12w
0x1400aee5c  jz      short loc_1400AEE87
0x1400aee5e  mov     eax, [rdi+10h]
0x1400aee61  mov     r9d, 39h ; '9'
0x1400aee67  mov     rcx, [rcx+40h]
0x1400aee6b  mov     dl, 5
0x1400aee6d  mov     [rsp+120h+var_F0], eax
0x1400aee71  mov     [rsp+120h+var_F8], rdi
0x1400aee76  mov     [rsp+120h+var_100], r8
0x1400aee7b  call    WPP_RECORDER_SF_qD
0x1400aee80  lea     r8, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x1400aee87  mov     rcx, [rbp+3Fh+arg_20]
0x1400aee8b  mov     r10d, 18h
0x1400aee91  mov     [rsi], r12d
0x1400aee94  mov     [rcx], r12d
0x1400aee97  movzx   edx, byte ptr [rbx]
0x1400aee9a  cmp     dl, 80h
0x1400aee9d  jnz     loc_1400AF5E7
0x1400aeea3  cmp     byte ptr [rbx+1], 1
0x1400aeea7  jb      loc_1400AF5E7
0x1400aeead  cmp     [rbx+2], r10w
0x1400aeeb2  jb      loc_1400AF5E7
0x1400aeeb8  movzx   eax, word ptr [rbx+14h]
0x1400aeebc  add     eax, 16h
0x1400aeebf  mov     [rcx], eax
0x1400aeec1  cmp     r15d, eax
0x1400aeec4  jnb     short loc_1400AEF0D
0x1400aeec6  mov     esi, 80000005h
0x1400aeecb  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400aeed2  jz      loc_1400AF645
0x1400aeed8  lea     r9d, [r10+23h]
0x1400aeedc  mov     dword ptr [rsp+120h+var_E0], r15d
0x1400aeee1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aeee8  mov     dl, 2
0x1400aeeea  mov     dword ptr [rsp+120h+var_E8], eax
0x1400aeeee  mov     eax, [rdi+10h]
0x1400aeef1  mov     [rsp+120h+var_F0], eax
0x1400aeef5  mov     rcx, [rcx+40h]
0x1400aeef9  mov     [rsp+120h+var_F8], rdi
0x1400aeefe  mov     [rsp+120h+var_100], r8
0x1400aef03  call    WPP_RECORDER_SF_qDdd
0x1400aef08  jmp     loc_1400AF645
0x1400aef0d  mov     [rsi], eax
0x1400aef0f  mov     ecx, [rbx+4]
0x1400aef12  cmp     ecx, 3
0x1400aef15  ja      short loc_1400AEF1F
0x1400aef17  mov     r15d, 2
0x1400aef1d  jmp     short loc_1400AEF8B
0x1400aef1f  lea     eax, [rcx-4]
0x1400aef22  cmp     eax, 1
0x1400aef25  jbe     short loc_1400AEF58
0x1400aef27  lea     eax, [rcx-6]
0x1400aef2a  cmp     eax, 1
0x1400aef2d  jbe     short loc_1400AEF50
0x1400aef2f  mov     esi, 0C0010015h
0x1400aef34  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400aef3b  jz      loc_1400AF645
0x1400aef41  mov     eax, [rbx+8]
0x1400aef44  mov     r9d, 3Ch ; '<'
0x1400aef4a  mov     dword ptr [rsp+120h+var_E0], ecx
0x1400aef4e  jmp     short loc_1400AEEE1
0x1400aef50  mov     r15d, 4
0x1400aef56  jmp     short loc_1400AEF8B
0x1400aef58  mov     r15d, 3
0x1400aef5e  cmp     [rbx+12h], r12b
0x1400aef62  jnz     short loc_1400AEF8B
0x1400aef64  mov     rcx, r14; this
0x1400aef67  call    ?GetCurrentConnectionInfo@CPort@@QEAAPEAUDOT11_CONNECTION_INFO@@XZ; CPort::GetCurrentConnectionInfo(void)
0x1400aef6c  test    rax, rax
0x1400aef6f  jz      short loc_1400AEF8B
0x1400aef71  or      dword ptr [rax+8], 4
0x1400aef75  lea     rcx, [r14+3A8h]; this
0x1400aef7c  mov     r8d, [rax]; unsigned int
0x1400aef7f  lea     edx, [r15+24h]; unsigned int
0x1400aef83  mov     r9, rax; unsigned __int8 *
0x1400aef86  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEAE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar *)
0x1400aef8b  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400aef92  jz      short loc_1400AEFD7
0x1400aef94  mov     eax, [rbx+4]
0x1400aef97  mov     r9d, 3Dh ; '='
0x1400aef9d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aefa4  mov     dl, 4
0x1400aefa6  mov     [rsp+120h+var_D8], eax
0x1400aefaa  mov     eax, [rbx+8]
0x1400aefad  mov     dword ptr [rsp+120h+var_E0], eax
0x1400aefb1  mov     eax, [rdi+10h]
0x1400aefb4  mov     rcx, [rcx+40h]
0x1400aefb8  mov     dword ptr [rsp+120h+var_E8], r15d
0x1400aefbd  mov     [rsp+120h+var_F0], eax
0x1400aefc1  lea     rax, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x1400aefc8  mov     [rsp+120h+var_F8], rdi
0x1400aefcd  mov     [rsp+120h+var_100], rax
0x1400aefd2  call    WPP_RECORDER_SF_qDddd
0x1400aefd7  mov     ecx, 40h ; '@'
0x1400aefdc  mov     r8d, 47696457h
0x1400aefe2  cmp     [rbx+12h], r12b
0x1400aefe6  jnz     loc_1400AF3ED
0x1400aefec  mov     edx, 108h
0x1400aeff1  call    cs:__imp_ExAllocatePool2
0x1400aeff8  nop     dword ptr [rax+rax+00h]
0x1400aeffd  test    rax, rax
0x1400af000  jz      short loc_1400AF02B
0x1400af002  mov     ecx, 1
0x1400af007  lea     rsi, [rax+8]
0x1400af00b  mov     [rax], rcx
0x1400af00e  lea     r9, ??0_WDI_SET_ADD_CIPHER_KEYS_CONTAINER@@QEAA@XZ; void *(*)(void *)
0x1400af015  mov     r8d, ecx; unsigned __int64
0x1400af018  mov     edx, 100h; unsigned __int64
0x1400af01d  mov     rcx, rsi; void *
0x1400af020  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1400af025  mov     [rbp+3Fh+var_98], rsi
0x1400af029  jmp     short loc_1400AF032
0x1400af02b  mov     rsi, r12
0x1400af02e  mov     [rbp+3Fh+var_98], r12
0x1400af032  test    rsi, rsi
0x1400af035  jnz     short loc_1400AF07E
0x1400af037  mov     esi, 0C000009Ah
0x1400af03c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400af043  jz      loc_1400AF658
0x1400af049  mov     r9d, 3Eh ; '>'
0x1400af04f  mov     eax, [rdi+10h]
0x1400af052  mov     dl, 2
0x1400af054  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af05b  mov     [rsp+120h+var_F0], eax
0x1400af05f  lea     rax, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x1400af066  mov     [rsp+120h+var_F8], rdi
0x1400af06b  mov     [rsp+120h+var_100], rax
0x1400af070  mov     rcx, [rcx+40h]
0x1400af074  call    WPP_RECORDER_SF_qD
0x1400af079  jmp     loc_1400AF645
0x1400af07e  mov     [rbp+3Fh+var_A0], 1
0x1400af085  mov     ecx, 3; enum _DOT11_WFD_SCAN_TYPE
0x1400af08a  and     dword ptr [rsi], 0FFFFFFFEh
0x1400af08d  call    ?MapP2PScanType@CDot11ToWabiConverter@@SA?AW4_WDI_P2P_SCAN_TYPE@@W4_DOT11_WFD_SCAN_TYPE@@@Z; CDot11ToWabiConverter::MapP2PScanType(_DOT11_WFD_SCAN_TYPE)
0x1400af092  mov     rcx, [rbp+3Fh+var_98]
0x1400af096  mov     [rcx+14h], eax
0x1400af099  mov     rax, [rbp+3Fh+var_98]
0x1400af09d  mov     [rax+1Ch], r15d
0x1400af0a1  mov     ecx, [rbx+8]; enum _DOT11_CIPHER_ALGORITHM
0x1400af0a4  call    ?MapCipherAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_CIPHER_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@@Z; CDot11ToWabiConverter::MapCipherAlgorithm(_DOT11_CIPHER_ALGORITHM)
0x1400af0a9  mov     rcx, [rbp+3Fh+var_98]
0x1400af0ad  mov     [rcx+10h], eax
0x1400af0b0  mov     rax, [rbp+3Fh+var_98]
0x1400af0b4  mov     cl, [rbx+13h]
0x1400af0b7  mov     [rax+18h], cl
0x1400af0ba  mov     rax, [rbp+3Fh+var_98]
0x1400af0be  or      dword ptr [rax], 2
0x1400af0c1  mov     rax, [rbp+3Fh+var_98]
0x1400af0c5  mov     ecx, [rbx+4]
0x1400af0c8  mov     [rax+0Ch], ecx
0x1400af0cb  mov     rax, [rbp+3Fh+var_98]
0x1400af0cf  and     dword ptr [rax], 0FFFFFFF7h
0x1400af0d2  mov     rax, [rbp+3Fh+var_98]
0x1400af0d6  mov     ecx, [rax]
0x1400af0d8  and     ecx, 0FFFFFFEFh
0x1400af0db  mov     [rax], ecx
0x1400af0dd  and     ecx, 0FFFFFFDFh
0x1400af0e0  mov     rax, [rbp+3Fh+var_98]
0x1400af0e4  mov     [rax], ecx
0x1400af0e6  btr     ecx, 7
0x1400af0ea  mov     rax, [rbp+3Fh+var_98]
0x1400af0ee  mov     [rax], ecx
0x1400af0f0  and     ecx, 0FFFFFFBFh
0x1400af0f3  mov     rax, [rbp+3Fh+var_98]
0x1400af0f7  mov     [rax], ecx
0x1400af0f9  btr     ecx, 0Ah
0x1400af0fd  mov     rax, [rbp+3Fh+var_98]
0x1400af101  mov     [rax], ecx
0x1400af103  btr     ecx, 8
0x1400af107  mov     rax, [rbp+3Fh+var_98]
0x1400af10b  mov     [rax], ecx
0x1400af10d  mov     r8d, [rbx+8]
0x1400af111  mov     edx, r8d
0x1400af114  sub     edx, 1
0x1400af117  jz      loc_1400AF33F
0x1400af11d  sub     edx, 1
0x1400af120  jz      loc_1400AF2E7
0x1400af126  sub     edx, 2
0x1400af129  jz      loc_1400AF2AC
0x1400af12f  sub     edx, 1
0x1400af132  jz      loc_1400AF33F
0x1400af138  sub     edx, 1
0x1400af13b  jz      loc_1400AF268
0x1400af141  sub     edx, 2
0x1400af144  jz      loc_1400AF22A
0x1400af14a  sub     edx, 1
0x1400af14d  jz      loc_1400AF1E5
0x1400af153  sub     edx, 3
0x1400af156  jz      short loc_1400AF1A0
0x1400af158  cmp     edx, 0F5h
0x1400af15e  jz      loc_1400AF33F
0x1400af164  cmp     r8d, 0FFFFFFFFh
0x1400af168  jg      short loc_1400AF196
0x1400af16a  mov     rax, [rbp+3Fh+var_98]
0x1400af16e  bts     ecx, 8
0x1400af172  mov     [rax], ecx
0x1400af174  mov     rax, [rbp+3Fh+var_98]
0x1400af178  movzx   ecx, word ptr [rbx+14h]
0x1400af17c  mov     [rax+0B8h], ecx
0x1400af182  lea     rcx, [rbx+16h]
0x1400af186  mov     rax, [rbp+3Fh+var_98]
0x1400af18a  mov     [rax+0C0h], rcx
0x1400af191  jmp     loc_1400AF366
0x1400af196  mov     esi, 0C0010015h
0x1400af19b  jmp     loc_1400AF645
0x1400af1a0  mov     rax, [rbp+3Fh+var_98]
0x1400af1a4  or      ecx, 4
0x1400af1a7  mov     [rax], ecx
0x1400af1a9  mov     rcx, [rbp+3Fh+var_98]
0x1400af1ad  mov     eax, [rbx+16h]
0x1400af1b0  mov     [rcx+20h], eax
0x1400af1b3  movzx   eax, word ptr [rbx+1Ah]
0x1400af1b7  mov     [rcx+24h], ax
0x1400af1bb  mov     rax, [rbp+3Fh+var_98]
0x1400af1bf  bts     dword ptr [rax], 0Ah
0x1400af1c3  mov     rax, [rbp+3Fh+var_98]
0x1400af1c7  movzx   ecx, word ptr [rbx+1Eh]
0x1400af1cb  mov     [rax+0E8h], ecx
0x1400af1d1  lea     rcx, [rbx+22h]
0x1400af1d5  mov     rax, [rbp+3Fh+var_98]
0x1400af1d9  mov     [rax+0F0h], rcx
0x1400af1e0  jmp     loc_1400AF366
0x1400af1e5  mov     rax, [rbp+3Fh+var_98]
0x1400af1e9  or      ecx, 4
0x1400af1ec  mov     [rax], ecx
0x1400af1ee  mov     rcx, [rbp+3Fh+var_98]
0x1400af1f2  mov     eax, [rbx+16h]
0x1400af1f5  mov     [rcx+20h], eax
0x1400af1f8  movzx   eax, word ptr [rbx+1Ah]
0x1400af1fc  mov     [rcx+24h], ax
0x1400af200  mov     rax, [rbp+3Fh+var_98]
0x1400af204  bts     dword ptr [rax], 9
0x1400af208  mov     rax, [rbp+3Fh+var_98]
0x1400af20c  movzx   ecx, word ptr [rbx+1Eh]
0x1400af210  mov     [rax+0D0h], ecx
0x1400af216  lea     rcx, [rbx+22h]
0x1400af21a  mov     rax, [rbp+3Fh+var_98]
0x1400af21e  mov     [rax+0D8h], rcx
0x1400af225  jmp     loc_1400AF366
0x1400af22a  mov     rax, [rbp+3Fh+var_98]
0x1400af22e  or      ecx, 4
0x1400af231  mov     [rax], ecx
0x1400af233  mov     rcx, [rbp+3Fh+var_98]
0x1400af237  mov     eax, [rbx+16h]
0x1400af23a  mov     [rcx+20h], eax
0x1400af23d  movzx   eax, word ptr [rbx+1Ah]
0x1400af241  mov     [rcx+24h], ax
0x1400af245  mov     rax, [rbp+3Fh+var_98]
0x1400af249  or      dword ptr [rax], 10h
0x1400af24c  mov     rax, [rbp+3Fh+var_98]
0x1400af250  movzx   ecx, word ptr [rbx+1Eh]
0x1400af254  mov     [rax+40h], ecx
0x1400af257  lea     rcx, [rbx+22h]
0x1400af25b  mov     rax, [rbp+3Fh+var_98]
0x1400af25f  mov     [rax+48h], rcx
0x1400af263  jmp     loc_1400AF366
0x1400af268  mov     rax, [rbp+3Fh+var_98]
0x1400af26c  or      ecx, 4
0x1400af26f  mov     [rax], ecx
0x1400af271  mov     rcx, [rbp+3Fh+var_98]
0x1400af275  mov     eax, [rbx+16h]
0x1400af278  mov     [rcx+20h], eax
0x1400af27b  movzx   eax, word ptr [rbx+1Ah]
0x1400af27f  mov     [rcx+24h], ax
0x1400af283  mov     rax, [rbp+3Fh+var_98]
0x1400af287  or      dword ptr [rax], 40h
0x1400af28a  mov     rax, [rbp+3Fh+var_98]
0x1400af28e  movzx   ecx, word ptr [rbx+1Eh]
  ... truncated ...
```
