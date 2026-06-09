# CConnectJob::FillConnectRoamTaskParameters(_WDI_CONNECT_PARAMETERS_CONTAINER *,ArrayOfElements<_WDI_CONNECT_BSS_ENTRY_CONTAINER> *,bool)

- ea: `0x14001de34`
- end: `0x14001e6ee`
- name: `?FillConnectRoamTaskParameters@CConnectJob@@AEAAHPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@@PEAU?$ArrayOfElements@U_WDI_CONNECT_BSS_ENTRY_CONTAINER@@@@_N@Z`
- size: `2234`
- prototype: `__int64 __fastcall(COidJobBase *this, void *)`
- caller_count: `2`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001d764`
- `0x14001d9a4`

## callees

- `0x1400109f8`
- `0x1400122e0`
- `0x140013000`
- `0x1400147e8`
- `0x1400176b0`
- `0x14001a808`
- `0x14001a850`
- `0x14001a8e0`
- `0x14001dda0`
- `0x14001de34`
- `0x14001e6f4`
- `0x140021280`
- `0x1400226dc`
- `0x140023b08`
- `0x1400297a0`
- `0x140034e04`
- `0x140034ec4`
- `0x1400489f0`
- `0x14004ff88`
- `0x140052bcc`
- `0x140054d50`
- `0x14005a17c`
- `0x14005f628`
- `0x14007dda0`
- `0x1400c2908`
- `0x1400da4f0`
- `0x1400da680`
- `0x1400da740`
- `0x1400dac80`

## pseudocode

```c
__int64 __fastcall CConnectJob::FillConnectRoamTaskParameters(COidJobBase *this, void **a2, __int64 a3, char a4)
{
  int v7; // edx
  CPort *v8; // r13
  int v9; // edx
  unsigned int AdapterCapabilitiesFromPropertyCache; // ebx
  int v11; // r8d
  int v12; // r9d
  char v13; // r15
  unsigned int i; // ebx
  unsigned int *p_m_OnJobStartCalled; // r8
  __int64 v16; // rcx
  int v17; // edx
  int v18; // r8d
  unsigned int j; // edi
  unsigned int v20; // r8d
  struct _LIST_ENTRY *Blink; // rax
  unsigned int uSSIDLength; // r8d
  unsigned __int8 *ucSSID; // rdx
  struct _LIST_ENTRY *v24; // r8
  char *v25; // rdx
  int Flink_low; // edi
  CPropertyCache *p_m_PortPropertyCache; // r13
  struct _LIST_ENTRY *v28; // rbx
  int pThis_low; // r12d
  IOperationCompletionCallback *m_pActiveJobCompletionCallback; // rbx
  int v31; // edx
  int v32; // r8d
  char pThis; // al
  unsigned int v34; // edi
  unsigned int k; // r10d
  enum _WDI_AUTH_ALGORITHM v36; // eax
  int v37; // r10d
  __int64 v38; // r9
  unsigned int *v39; // rdi
  int v40; // edx
  int v41; // r8d
  __int16 m_pNdisConversion; // ax
  int v43; // r9d
  unsigned int m; // r10d
  enum _WDI_CIPHER_ALGORITHM v45; // eax
  int v46; // r10d
  __int64 v47; // r9
  unsigned int *v48; // rdi
  unsigned int n; // r10d
  enum _WDI_CIPHER_ALGORITHM v50; // eax
  int v51; // r10d
  __int64 v52; // r9
  unsigned int v53; // edi
  int m_pAdapter_low; // r15d
  _OID_HANDLER_ENTRY *m_pHandlerInfo; // rbx
  unsigned int m_DisallowedBssidCount; // ebx
  __int64 m_NdisPortNumber_low; // rdi
  unsigned __int8 *v58; // r15
  CAdapter *m_pAdapter; // rax
  char v60; // r15
  unsigned int m_JobPriority; // ebx
  struct CPortPropertyCache *PortPropertyCache; // rax
  struct CPortPropertyCache *v63; // rax
  int PropertyULong; // eax
  int v65; // edx
  int v66; // r8d
  struct CAdapter *v67; // rdx
  CPort *v68; // rdi
  int v69; // edx
  char v70; // bl
  unsigned int v71; // eax
  struct CBSSEntry **v73; // [rsp+28h] [rbp-61h]
  unsigned int m_ActivityId; // [rsp+30h] [rbp-59h]
  char v75[8]; // [rsp+38h] [rbp-51h]
  unsigned int v76; // [rsp+50h] [rbp-39h] BYREF
  char v77; // [rsp+54h] [rbp-35h]
  unsigned __int8 *v78; // [rsp+58h] [rbp-31h] BYREF
  struct _DOT11_ADAPTER_CAPABILITIES *v79; // [rsp+60h] [rbp-29h] BYREF
  CPort *PortFromPortId; // [rsp+68h] [rbp-21h]
  __int64 v81; // [rsp+70h] [rbp-19h]
  struct _DOT11_SSID v82; // [rsp+78h] [rbp-11h] BYREF

  v77 = a4;
  v81 = a3;
  PortFromPortId = CAdapter::GetPortFromPortId(this->m_pAdapter, this->m_PortId);
  v76 = 0;
  v8 = PortFromPortId;
  v78 = 0;
  v79 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      267,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
  }
  memset(a2, 0, 0x128u);
  *(_OWORD *)a3 = 0;
  *(_QWORD *)(a3 + 16) = 0;
  *((_BYTE *)a2 + 5) = this[1].m_DeferHint;
  *((_BYTE *)a2 + 6) = this[1].m_AllowInLowPower;
  *((_BYTE *)a2 + 7) = this[1].m_JobAbortedBeforeAddSerializedJobList;
  *((_BYTE *)a2 + 8) = *(&this[1].m_JobAbortedBeforeAddSerializedJobList + 1);
  AdapterCapabilitiesFromPropertyCache = CConnectHelpers::GetAdapterCapabilitiesFromPropertyCache(
                                           this->m_pAdapter,
                                           &v79);
  if ( AdapterCapabilitiesFromPropertyCache )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v12 = 268;
      *(_DWORD *)v75 = AdapterCapabilitiesFromPropertyCache;
      m_ActivityId = this->m_ActivityId;
      goto LABEL_85;
    }
    return AdapterCapabilitiesFromPropertyCache;
  }
  *((_BYTE *)a2 + 20) = v79->BSSTransitionSupported == dot11_tri_state_true;
  if ( (this[1].CJobBase::m_NdisPortNumber & 0x10) != 0 )
    *((_DWORD *)a2 + 4) = 1;
  AdapterCapabilitiesFromPropertyCache = ArrayOfElements<ArrayOfElements<unsigned char>>::AllocateElements(
                                           a2 + 3,
                                           LOWORD(this[1].m_FailsafeDeferJobOperationCompletedEvent.m_Link.ListEntry.Flink),
                                           0);
  if ( AdapterCapabilitiesFromPropertyCache )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return AdapterCapabilitiesFromPropertyCache;
    v12 = 269;
LABEL_13:
    *(_DWORD *)v75 = AdapterCapabilitiesFromPropertyCache;
    goto LABEL_84;
  }
  v13 = 0;
  for ( i = 0; ; ++i )
  {
    p_m_OnJobStartCalled = (unsigned int *)&this[1].m_OnJobStartCalled;
    if ( i >= *(_DWORD *)&this[1].m_OnJobStartCalled )
      break;
    v16 = *((_QWORD *)&this[1].m_pActiveJobsList + i);
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16) )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 4;
        WPP_RECORDER_SF_qD_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          v18,
          270,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          *((_QWORD *)&this[1].m_pActiveJobsList + i) + 444LL);
      }
      v13 = 1;
      p_m_OnJobStartCalled = (unsigned int *)&this[1].m_OnJobStartCalled;
      *((_BYTE *)a2 + 5) = 1;
      break;
    }
  }
  for ( j = 0; j < *((_DWORD *)a2 + 6); ++j )
  {
    if ( v13 )
    {
      v20 = *p_m_OnJobStartCalled;
      Blink = this[1].m_FailsafeDeferJobOperationCompletedEvent.m_Link.ListEntry.Blink;
      memset(&v82, 0, sizeof(v82));
      CConnectHelpers::RemapSSID(
        (struct _DOT11_SSID *)Blink + j,
        (struct CBSSEntry **const)&this[1].m_pActiveJobsList,
        v20,
        &v82);
      uSSIDLength = v82.uSSIDLength;
      ucSSID = v82.ucSSID;
    }
    else
    {
      v24 = this[1].m_FailsafeDeferJobOperationCompletedEvent.m_Link.ListEntry.Blink;
      v25 = (char *)&v24->Flink + 4;
      uSSIDLength = *((_DWORD *)&v24->Flink + 9 * j);
      ucSSID = (unsigned __int8 *)&v25[36 * j];
    }
    AdapterCapabilitiesFromPropertyCache = ArrayOfElements<unsigned char>::SimpleSet(
                                             (__int64)a2[4] + 24 * j,
                                             ucSSID,
                                             uSSIDLength);
    if ( AdapterCapabilitiesFromPropertyCache )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return AdapterCapabilitiesFromPropertyCache;
      v12 = 271;
      *(_DWORD *)v75 = AdapterCapabilitiesFromPropertyCache;
LABEL_84:
      m_ActivityId = this->m_ActivityId;
LABEL_85:
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v11,
        v12,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        m_ActivityId,
        *(_QWORD *)v75);
LABEL_86:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LODWORD(v73) = AdapterCapabilitiesFromPropertyCache;
        LOBYTE(v9) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          1,
          279,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          v73);
      }
      return AdapterCapabilitiesFromPropertyCache;
    }
    p_m_OnJobStartCalled = (unsigned int *)&this[1].m_OnJobStartCalled;
  }
  Flink_low = LOWORD(this[1].m_ActiveJobLink.ListEntry.Flink);
  p_m_PortPropertyCache = &v8->m_PortPropertyCache;
  if ( (_WORD)Flink_low )
  {
    v28 = this[1].m_ActiveJobLink.ListEntry.Blink;
    ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(a2 + 7);
    *((_BYTE *)a2 + 72) = 0;
    *((_DWORD *)a2 + 14) = Flink_low;
    a2[8] = v28;
    pThis_low = LOWORD(this[1].m_ActiveJobLink.pThis);
    m_pActiveJobCompletionCallback = this[1].m_pActiveJobCompletionCallback;
    ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(a2 + 10);
    *((_BYTE *)a2 + 96) = 0;
    *((_DWORD *)a2 + 20) = pThis_low;
    a2[11] = (void *)m_pActiveJobCompletionCallback;
    pThis = (char)this[1].m_FailsafeDeferJobOperationCompletedEvent.m_Link.pThis;
    *(_DWORD *)a2 |= 1u;
    *((_BYTE *)a2 + 48) = pThis;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v31) = 4;
      WPP_RECORDER_SF_qDddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v31,
        v32,
        272,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        *((_DWORD *)a2 + 14),
        pThis,
        pThis_low);
    }
  }
  if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(p_m_PortPropertyCache, 0x85u, &v76, &v78) )
  {
    v34 = v76;
    if ( v76 )
    {
      ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(a2 + 34);
      a2[35] = v78;
      *((_BYTE *)a2 + 288) = 0;
      *((_DWORD *)a2 + 68) = v34;
      *(_DWORD *)a2 |= 0x20u;
    }
  }
  AdapterCapabilitiesFromPropertyCache = ArrayOfElements<enum _WDI_AUTH_ALGORITHM>::AllocateElements(
                                           a2 + 13,
                                           LOWORD(this[1].m_SerializedJobLink.ListEntry.Flink),
                                           0);
  if ( AdapterCapabilitiesFromPropertyCache )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return AdapterCapabilitiesFromPropertyCache;
    v12 = 273;
    goto LABEL_13;
  }
  for ( k = 0; k < *((_DWORD *)a2 + 26); k = v37 + 1 )
  {
    v36 = CDot11ToWabiConverter::MapAuthAlgorithm(*((enum _DOT11_AUTH_ALGORITHM *)&this[1].m_SerializedJobLink.ListEntry.Blink->Flink
                                                  + k));
    *((_DWORD *)a2[14] + v38) = v36;
    if ( *((_DWORD *)&this[1].m_SerializedJobLink.ListEntry.Blink->Flink + v38) == 10 && (*(_DWORD *)a2 & 0x20) == 0 )
    {
      AdapterCapabilitiesFromPropertyCache = -1073741436;
      goto LABEL_86;
    }
  }
  v39 = (unsigned int *)(a2 + 16);
  AdapterCapabilitiesFromPropertyCache = ArrayOfElements<enum _WDI_CIPHER_ALGORITHM>::AllocateElements(
                                           a2 + 16,
                                           LOWORD(this[1].m_SerializedJobLink.pThis),
                                           0);
  if ( AdapterCapabilitiesFromPropertyCache )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return AdapterCapabilitiesFromPropertyCache;
    m_pNdisConversion = (__int16)this[1].m_SerializedJobLink.pThis;
    v43 = 274;
    goto LABEL_48;
  }
  for ( m = 0; m < *v39; *((_DWORD *)a2[17] + v47) = v45 )
  {
    v45 = CDot11ToWabiConverter::MapCipherAlgorithm(*((enum _DOT11_CIPHER_ALGORITHM *)&this[1].m_pSerializedJobCompletionCallback->CJobBase::__vftable
                                                    + m));
    m = v46 + 1;
  }
  v48 = (unsigned int *)(a2 + 19);
  AdapterCapabilitiesFromPropertyCache = ArrayOfElements<enum _WDI_CIPHER_ALGORITHM>::AllocateElements(
                                           a2 + 19,
                                           LOWORD(this[1].m_pNdisConversion),
                                           0);
  if ( AdapterCapabilitiesFromPropertyCache )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return AdapterCapabilitiesFromPropertyCache;
    m_pNdisConversion = (__int16)this[1].m_pNdisConversion;
    v43 = 275;
LABEL_48:
    LOBYTE(v40) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v40,
      v41,
      v43,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      m_pNdisConversion,
      AdapterCapabilitiesFromPropertyCache);
    goto LABEL_86;
  }
  for ( n = 0; n < *v48; *((_DWORD *)a2[20] + v52) = v50 )
  {
    v50 = CDot11ToWabiConverter::MapCipherAlgorithm(*((enum _DOT11_CIPHER_ALGORITHM *)&this[1].m_pPropertyCacheDirectory->CJobBase::__vftable
                                                    + n));
    n = v51 + 1;
  }
  if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(p_m_PortPropertyCache, 0xEu, &v76, &v78) )
  {
    v53 = v76;
    if ( v76 )
    {
      ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(a2 + 22);
      a2[23] = v78;
      *((_BYTE *)a2 + 192) = 0;
      *((_DWORD *)a2 + 44) = v53;
      *(_DWORD *)a2 |= 2u;
    }
  }
  m_pAdapter_low = LOWORD(this[1].m_pAdapter);
  if ( (_WORD)m_pAdapter_low )
  {
    m_pHandlerInfo = this[1].m_pHandlerInfo;
    ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(a2 + 31);
    *((_DWORD *)a2 + 62) = m_pAdapter_low;
    *((_BYTE *)a2 + 264) = 0;
    a2[32] = m_pHandlerInfo;
    *(_DWORD *)a2 |= 0x10u;
  }
  m_DisallowedBssidCount = 0;
  m_NdisPortNumber_low = LOWORD(this[1].m_NdisPortNumber);
  v58 = 0;
  if ( !LOBYTE(this[9].m_pDebugChildJob) && v79->MBOSupported == dot11_tri_state_true )
  {
    m_pAdapter = this->m_pAdapter;
    m_DisallowedBssidCount = m_pAdapter->m_ExtStaBSSList.m_DisallowedBssidCount;
    v58 = m_pAdapter->m_ExtStaBSSList.m_DisallowedBssidList[0];
  }
  if ( m_DisallowedBssidCount + (_DWORD)m_NdisPortNumber_low )
  {
    ArrayOfElements<_WDI_MAC_ADDRESS>::AllocateElements(
      (__int64)(a2 + 28),
      m_DisallowedBssidCount + m_NdisPortNumber_low,
      0);
    *(_DWORD *)a2 |= 8u;
    if ( (_WORD)m_NdisPortNumber_low )
      memmove(a2[29], this[1].m_pPortPropertyCache, 6 * m_NdisPortNumber_low);
    if ( m_DisallowedBssidCount )
      memmove((char *)a2[29] + 6 * m_NdisPortNumber_low, v58, 6LL * m_DisallowedBssidCount);
  }
  *(_DWORD *)a2 &= ~4u;
  v60 = v77;
  if ( v77 )
  {
    m_JobPriority = this[1].m_JobPriority;
    v76 = m_JobPriority;
    PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
    if ( CPropertyCache::GetPropertyBooleanOrDefault(PortPropertyCache, 0x51u, 0) )
    {
      v63 = COidJobBase::GetPortPropertyCache(this);
      PropertyULong = CPropertyCache::GetPropertyULong(v63, 0x53u, &v76);
      if ( PropertyULong || (m_JobPriority = v76, v76 == 0xFFFF) )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          *(_DWORD *)v75 = PropertyULong;
          LOBYTE(v65) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v65,
            v66,
            276,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (char)this,
            this->m_ActivityId,
            *(_QWORD *)v75);
        }
        m_JobPriority = this[1].m_JobPriority;
      }
    }
    *((_DWORD *)a2 + 3) = m_JobPriority;
  }
  v67 = this->m_pAdapter;
  v76 = 0;
  v68 = PortFromPortId;
  CConnectHelpers::GetSupportedAssociationMethods(
    PortFromPortId,
    v67,
    (struct _WFC_CONNECTION_PROFILE_PARAMETERS *)&this[1].m_FailsafeDeferJobOperationCompletedEvent.m_Link,
    &v76);
  if ( v60
    && CPropertyCache::GetPropertyBooleanOrDefault(p_m_PortPropertyCache, 0x14u, 0)
    && !CConnectHelpers::IsIMDAssocForFTRoamRequired(
          (enum _WDI_ASSOC_STATUS)this[1].m_JobPriority,
          (enum _WDI_ROAM_CONFIGURATION_FLAGS)this[1].CJobBase::m_NdisPortNumber) )
  {
    v70 = 1;
  }
  else
  {
    v70 = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v69) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v69,
        1,
        277,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
    }
  }
  v71 = CConnectHelpers::FillConnectBSSEntryTLV(
          v68,
          (unsigned int *)&this[1].m_OnJobStartCalled,
          (struct CBSSEntry **)&this[1].m_pActiveJobsList,
          v81,
          1,
          v70);
  AdapterCapabilitiesFromPropertyCache = v71;
  if ( !v71 )
    goto LABEL_86;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v12 = 278;
    *(_DWORD *)v75 = v71;
    goto LABEL_84;
  }
  return AdapterCapabilitiesFromPropertyCache;
}

```

## disassembly

```asm
0x14001de34  mov     [rsp-8+arg_18], rbx
0x14001de39  push    rbp
0x14001de3a  push    rsi
0x14001de3b  push    rdi
0x14001de3c  push    r12
0x14001de3e  push    r13
0x14001de40  push    r14
0x14001de42  push    r15
0x14001de44  lea     rbp, [rsp-27h]
0x14001de49  sub     rsp, 0B0h
0x14001de50  mov     rax, cs:__security_cookie
0x14001de57  xor     rax, rsp
0x14001de5a  mov     [rbp+57h+var_40], rax
0x14001de5e  mov     rbx, r8
0x14001de61  mov     [rbp+57h+var_8C], r9b
0x14001de65  mov     r14, rdx
0x14001de68  mov     [rbp+57h+var_70], rbx
0x14001de6c  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x14001de70  mov     rsi, rcx
0x14001de73  mov     rcx, [rcx+200h]; this
0x14001de7a  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x14001de7f  xor     r12d, r12d
0x14001de82  mov     [rbp+57h+var_78], rax
0x14001de86  mov     [rbp+57h+var_90], r12d
0x14001de8a  mov     r13, rax
0x14001de8d  mov     [rbp+57h+var_88], r12
0x14001de91  mov     [rbp+57h+var_80], r12
0x14001de95  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001de9c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dea3  lea     r15, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001deaa  jz      short loc_14001DEDC
0x14001deac  mov     rcx, cs:WPP_GLOBAL_Control
0x14001deb3  cmp     byte ptr [rcx+29h], 5
0x14001deb7  jnb     short loc_14001DEC0
0x14001deb9  cmp     [rcx+48h], r12w
0x14001debe  jz      short loc_14001DEDC
0x14001dec0  mov     rcx, [rcx+40h]
0x14001dec4  mov     r9d, 10Bh
0x14001deca  mov     r8d, 1
0x14001ded0  mov     [rsp+0E0h+var_C0], r15
0x14001ded5  mov     dl, 5
0x14001ded7  call    WPP_RECORDER_SF_
0x14001dedc  xor     edx, edx; Val
0x14001dede  mov     r8d, 128h; Size
0x14001dee4  mov     rcx, r14; void *
0x14001dee7  call    memset
0x14001deec  xor     eax, eax
0x14001deee  lea     rdx, [rbp+57h+var_80]; struct _DOT11_ADAPTER_CAPABILITIES **
0x14001def2  xorps   xmm0, xmm0
0x14001def5  movups  xmmword ptr [rbx], xmm0
0x14001def8  mov     [rbx+10h], rax
0x14001defc  mov     al, [rsi+421h]
0x14001df02  mov     [r14+5], al
0x14001df06  mov     al, [rsi+422h]
0x14001df0c  mov     [r14+6], al
0x14001df10  mov     al, [rsi+423h]
0x14001df16  mov     [r14+7], al
0x14001df1a  mov     al, [rsi+424h]
0x14001df20  mov     [r14+8], al
0x14001df24  mov     rcx, [rsi+200h]; struct CAdapter *
0x14001df2b  call    ?GetAdapterCapabilitiesFromPropertyCache@CConnectHelpers@@SAHPEAVCAdapter@@PEAPEAU_DOT11_ADAPTER_CAPABILITIES@@@Z; CConnectHelpers::GetAdapterCapabilitiesFromPropertyCache(CAdapter *,_DOT11_ADAPTER_CAPABILITIES * *)
0x14001df30  mov     ebx, eax
0x14001df32  test    eax, eax
0x14001df34  jz      short loc_14001DF60
0x14001df36  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001df3d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001df44  jz      loc_14001E67E
0x14001df4a  mov     ecx, [rsi+10h]
0x14001df4d  mov     r9d, 10Ch
0x14001df53  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14001df57  mov     dword ptr [rsp+0E0h+var_B0], ecx
0x14001df5b  jmp     loc_14001E61E
0x14001df60  mov     rax, [rbp+57h+var_80]
0x14001df64  cmp     dword ptr [rax+1A4h], 1
0x14001df6b  setz    al
0x14001df6e  mov     [r14+14h], al
0x14001df72  mov     eax, [rsi+260h]
0x14001df78  test    al, 10h
0x14001df7a  jz      short loc_14001DF84
0x14001df7c  mov     dword ptr [r14+10h], 1
0x14001df84  movzx   edx, word ptr [rsi+3B8h]
0x14001df8b  lea     rcx, [r14+18h]
0x14001df8f  xor     r8d, r8d
0x14001df92  call    ?AllocateElements@?$ArrayOfElements@U?$ArrayOfElements@E@@@@QEAAHI_K@Z; ArrayOfElements<ArrayOfElements<uchar>>::AllocateElements(uint,unsigned __int64)
0x14001df97  xor     ecx, ecx
0x14001df99  mov     ebx, eax
0x14001df9b  test    eax, eax
0x14001df9d  jz      short loc_14001DFC2
0x14001df9f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001dfa6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dfad  jz      loc_14001E67E
0x14001dfb3  mov     r9d, 10Dh
0x14001dfb9  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14001dfbd  jmp     loc_14001E617
0x14001dfc2  mov     r15b, cl
0x14001dfc5  mov     ebx, ecx
0x14001dfc7  lea     r8, [rsi+26Ch]
0x14001dfce  cmp     ebx, [r8]
0x14001dfd1  jnb     loc_14001E05A
0x14001dfd7  mov     edi, ebx
0x14001dfd9  mov     rcx, [rsi+rdi*8+278h]
0x14001dfe1  mov     rax, [rcx]
0x14001dfe4  mov     rax, [rax+20h]
0x14001dfe8  call    _guard_dispatch_icall
0x14001dfed  xor     ecx, ecx
0x14001dfef  test    al, al
0x14001dff1  jnz     short loc_14001DFF7
0x14001dff3  inc     ebx
0x14001dff5  jmp     short loc_14001DFC7
0x14001dff7  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001dffe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e005  jz      short loc_14001E04C
0x14001e007  mov     rax, [rsi+rdi*8+278h]
0x14001e00f  mov     r9d, 10Eh
0x14001e015  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e01c  add     rax, 1BCh
0x14001e022  mov     qword ptr [rsp+0E0h+var_A8], rax
0x14001e027  mov     dl, 4
0x14001e029  mov     eax, [rsi+10h]
0x14001e02c  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14001e030  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001e037  mov     rcx, [rcx+40h]
0x14001e03b  mov     [rsp+0E0h+var_B8], rsi
0x14001e040  mov     [rsp+0E0h+var_C0], rax
0x14001e045  call    WPP_RECORDER_SF_qD_MAC_
0x14001e04a  xor     ecx, ecx
0x14001e04c  mov     r15b, 1
0x14001e04f  lea     r8, [rsi+26Ch]
0x14001e056  mov     [r14+5], r15b
0x14001e05a  mov     edi, ecx
0x14001e05c  cmp     edi, [r14+18h]
0x14001e060  jnb     loc_14001E10B
0x14001e066  mov     eax, edi
0x14001e068  lea     r9, [rax+rax*8]
0x14001e06c  lea     rbx, [rax+rax*2]
0x14001e070  test    r15b, r15b
0x14001e073  jz      short loc_14001E0AD
0x14001e075  mov     r8d, [r8]; unsigned int
0x14001e078  lea     rdx, [rsi+278h]; struct CBSSEntry **
0x14001e07f  xor     eax, eax
0x14001e081  xorps   xmm0, xmm0
0x14001e084  mov     dword ptr [rbp+57h+var_68.ucSSID+1Ch], eax
0x14001e087  mov     rax, [rsi+3C0h]
0x14001e08e  movups  xmmword ptr [rbp+57h+var_68.uSSIDLength], xmm0
0x14001e092  movups  xmmword ptr [rbp+57h+var_68.ucSSID+0Ch], xmm0
0x14001e096  lea     rcx, [rax+r9*4]; struct _DOT11_SSID *
0x14001e09a  lea     r9, [rbp+57h+var_68]; struct _DOT11_SSID *
0x14001e09e  call    ?RemapSSID@CConnectHelpers@@SAHAEAU_DOT11_SSID@@QEAPEAVCBSSEntry@@K0@Z; CConnectHelpers::RemapSSID(_DOT11_SSID &,CBSSEntry * * const,ulong,_DOT11_SSID &)
0x14001e0a3  mov     r8d, [rbp+57h+var_68.uSSIDLength]
0x14001e0a7  lea     rdx, [rbp+57h+var_68.ucSSID]
0x14001e0ab  jmp     short loc_14001E0C0
0x14001e0ad  mov     r8, [rsi+3C0h]
0x14001e0b4  lea     rdx, [r8+4]
0x14001e0b8  mov     r8d, [r8+r9*4]
0x14001e0bc  lea     rdx, [rdx+r9*4]
0x14001e0c0  mov     rax, [r14+20h]
0x14001e0c4  lea     rcx, [rax+rbx*8]
0x14001e0c8  call    ?SimpleSet@?$ArrayOfElements@E@@QEAAHPEBEI_K@Z; ArrayOfElements<uchar>::SimpleSet(uchar const *,uint,unsigned __int64)
0x14001e0cd  mov     ebx, eax
0x14001e0cf  test    eax, eax
0x14001e0d1  jnz     short loc_14001E0E1
0x14001e0d3  inc     edi
0x14001e0d5  lea     r8, [rsi+26Ch]
0x14001e0dc  jmp     loc_14001E05C
0x14001e0e1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001e0e8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e0ef  jz      loc_14001E67E
0x14001e0f5  mov     r9d, 10Fh
0x14001e0fb  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14001e0ff  lea     r15, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001e106  jmp     loc_14001E617
0x14001e10b  movzx   edi, word ptr [rsi+3D0h]
0x14001e112  add     r13, 3A8h
0x14001e119  test    di, di
0x14001e11c  jz      loc_14001E1CC
0x14001e122  mov     rbx, [rsi+3D8h]
0x14001e129  lea     r15, [r14+38h]
0x14001e12d  mov     rcx, r15
0x14001e130  call    ?Cleanup@?$ArrayOfElements@W4_WDI_BAND_ID@@@@QEAAXXZ; ArrayOfElements<_WDI_BAND_ID>::Cleanup(void)
0x14001e135  mov     [r15+10h], r12b
0x14001e139  lea     rcx, [r14+50h]
0x14001e13d  mov     [r15], edi
0x14001e140  mov     [r15+8], rbx
0x14001e144  movzx   r12d, word ptr [rsi+3E0h]
0x14001e14c  mov     rbx, [rsi+3E8h]
0x14001e153  call    ?Cleanup@?$ArrayOfElements@W4_WDI_BAND_ID@@@@QEAAXXZ; ArrayOfElements<_WDI_BAND_ID>::Cleanup(void)
0x14001e158  mov     byte ptr [r14+60h], 0
0x14001e15d  mov     [r14+50h], r12d
0x14001e161  mov     [r14+58h], rbx
0x14001e165  movzx   eax, byte ptr [rsi+3C8h]
0x14001e16c  or      dword ptr [r14], 1
0x14001e170  mov     [r14+30h], al
0x14001e174  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001e17b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001e182  jz      short loc_14001E1C9
0x14001e184  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e18b  mov     r9d, 110h
0x14001e191  mov     [rsp+0E0h+var_98], r12d
0x14001e196  mov     dl, 4
0x14001e198  mov     dword ptr [rsp+0E0h+var_A0], eax
0x14001e19c  mov     eax, [r15]
0x14001e19f  lea     r15, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001e1a6  mov     rcx, [rcx+40h]
0x14001e1aa  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14001e1ae  mov     eax, [rsi+10h]
0x14001e1b1  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14001e1b5  mov     [rsp+0E0h+var_B8], rsi
0x14001e1ba  mov     [rsp+0E0h+var_C0], r15
0x14001e1bf  call    WPP_RECORDER_SF_qDddd
0x14001e1c4  xor     r12d, r12d
0x14001e1c7  jmp     short loc_14001E1D3
0x14001e1c9  xor     r12d, r12d
0x14001e1cc  lea     r15, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001e1d3  lea     r9, [rbp+57h+var_88]; unsigned __int8 **
0x14001e1d7  mov     edx, 85h; unsigned int
0x14001e1dc  lea     r8, [rbp+57h+var_90]; unsigned int *
0x14001e1e0  mov     rcx, r13; this
0x14001e1e3  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x14001e1e8  test    eax, eax
0x14001e1ea  jnz     short loc_14001E214
0x14001e1ec  mov     edi, [rbp+57h+var_90]
0x14001e1ef  test    edi, edi
0x14001e1f1  jz      short loc_14001E214
0x14001e1f3  lea     rbx, [r14+110h]
0x14001e1fa  mov     rcx, rbx
0x14001e1fd  call    ?Cleanup@?$ArrayOfElements@W4_WDI_BAND_ID@@@@QEAAXXZ; ArrayOfElements<_WDI_BAND_ID>::Cleanup(void)
0x14001e202  mov     rax, [rbp+57h+var_88]
0x14001e206  mov     [rbx+8], rax
0x14001e20a  mov     [rbx+10h], r12b
0x14001e20e  mov     [rbx], edi
0x14001e210  or      dword ptr [r14], 20h
0x14001e214  movzx   edx, word ptr [rsi+3F0h]
0x14001e21b  lea     rcx, [r14+68h]
0x14001e21f  xor     r8d, r8d
0x14001e222  call    ?AllocateElements@?$ArrayOfElements@W4_WDI_AUTH_ALGORITHM@@@@QEAAHI_K@Z; ArrayOfElements<_WDI_AUTH_ALGORITHM>::AllocateElements(uint,unsigned __int64)
0x14001e227  mov     ebx, eax
0x14001e229  test    eax, eax
0x14001e22b  jz      short loc_14001E24C
0x14001e22d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001e234  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e23b  jz      loc_14001E67E
0x14001e241  mov     r9d, 111h
0x14001e247  jmp     loc_14001DFB9
0x14001e24c  mov     r10d, r12d
0x14001e24f  cmp     r10d, [r14+68h]
0x14001e253  jnb     short loc_14001E294
0x14001e255  mov     rcx, [rsi+3F8h]
0x14001e25c  mov     r9d, r10d
0x14001e25f  mov     ecx, [rcx+r9*4]; enum _DOT11_AUTH_ALGORITHM
0x14001e263  call    ?MapAuthAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_AUTH_ALGORITHM@@W4_DOT11_AUTH_ALGORITHM@@@Z; CDot11ToWabiConverter::MapAuthAlgorithm(_DOT11_AUTH_ALGORITHM)
0x14001e268  mov     rcx, [r14+70h]
0x14001e26c  mov     [rcx+r9*4], eax
0x14001e270  mov     rax, [rsi+3F8h]
0x14001e277  cmp     dword ptr [rax+r9*4], 0Ah
0x14001e27c  jnz     short loc_14001E285
0x14001e27e  mov     eax, [r14]
0x14001e281  test    al, 20h
0x14001e283  jz      short loc_14001E28A
0x14001e285  inc     r10d
0x14001e288  jmp     short loc_14001E24F
0x14001e28a  mov     ebx, 0C0000184h
0x14001e28f  jmp     loc_14001E63A
0x14001e294  movzx   edx, word ptr [rsi+400h]
0x14001e29b  lea     rdi, [r14+80h]
0x14001e2a2  mov     rcx, rdi
0x14001e2a5  xor     r8d, r8d
0x14001e2a8  call    ?AllocateElements@?$ArrayOfElements@W4_WDI_CIPHER_ALGORITHM@@@@QEAAHI_K@Z; ArrayOfElements<_WDI_CIPHER_ALGORITHM>::AllocateElements(uint,unsigned __int64)
0x14001e2ad  mov     ebx, eax
0x14001e2af  test    eax, eax
0x14001e2b1  jz      short loc_14001E304
0x14001e2b3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001e2ba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e2c1  jz      loc_14001E67E
0x14001e2c7  movzx   eax, word ptr [rsi+400h]
0x14001e2ce  mov     r9d, 112h
0x14001e2d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e2db  mov     dl, 2
0x14001e2dd  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x14001e2e1  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14001e2e5  mov     eax, [rsi+10h]
0x14001e2e8  mov     rcx, [rcx+40h]
0x14001e2ec  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14001e2f0  mov     [rsp+0E0h+var_B8], rsi
0x14001e2f5  mov     [rsp+0E0h+var_C0], r15
0x14001e2fa  call    WPP_RECORDER_SF_qDdd
0x14001e2ff  jmp     loc_14001E63A
0x14001e304  mov     r10d, r12d
0x14001e307  cmp     [rdi], r12d
0x14001e30a  jbe     short loc_14001E332
0x14001e30c  mov     rcx, [rsi+408h]
0x14001e313  mov     r9d, r10d
0x14001e316  mov     ecx, [rcx+r9*4]; enum _DOT11_CIPHER_ALGORITHM
0x14001e31a  call    ?MapCipherAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_CIPHER_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@@Z; CDot11ToWabiConverter::MapCipherAlgorithm(_DOT11_CIPHER_ALGORITHM)
0x14001e31f  mov     rcx, [r14+88h]
0x14001e326  inc     r10d
0x14001e329  mov     [rcx+r9*4], eax
0x14001e32d  cmp     r10d, [rdi]
0x14001e330  jb      short loc_14001E30C
0x14001e332  movzx   edx, word ptr [rsi+410h]
0x14001e339  lea     rdi, [r14+98h]
  ... truncated ...
```
