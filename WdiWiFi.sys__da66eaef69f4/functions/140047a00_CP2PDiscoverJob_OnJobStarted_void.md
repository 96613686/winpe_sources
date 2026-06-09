# CP2PDiscoverJob::OnJobStarted(void)

- ea: `0x140047a00`
- end: `0x140047f4d`
- name: `?OnJobStarted@CP2PDiscoverJob@@UEAAXXZ`
- size: `1357`
- prototype: `void __fastcall(CP2PDiscoverJob *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004a7c`
- `0x140004c3c`
- `0x1400122e0`
- `0x1400125b8`
- `0x1400176b0`
- `0x14002aa28`
- `0x140047a00`
- `0x140047f54`
- `0x140048178`
- `0x1400489f0`
- `0x140048f54`
- `0x14007b15c`
- `0x1400b918c`
- `0x1400c9bb0`
- `0x1400ce318`
- `0x1400da4f0`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140047cb3`
- `ntoskrnl!RtlCompareMemory` at `0x140047cb3`

## pseudocode

```c
void __fastcall CP2PDiscoverJob::OnJobStarted(CP2PDiscoverJob *this, __int64 a2, int a3)
{
  CAdapter *m_pAdapter; // rsi
  int v5; // eax
  int v6; // edx
  CP2PDiscoverJob *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  int v10; // edi
  int v11; // r9d
  unsigned int *p_m_DeviceFilterCount; // rdi
  __int64 v13; // r10
  bool v14; // r9
  bool v15; // r8
  struct CBSSEntry *BSSEntryByGroupID; // rax
  unsigned int i; // esi
  char v18; // r12
  unsigned __int64 v19; // r14
  _DOT11_WFD_DISCOVER_DEVICE_FILTER *m_pDeviceFilterList; // rax
  unsigned int uSSIDLength; // ecx
  char v22; // r15
  _DOT11_WFD_DISCOVER_DEVICE_FILTER *v23; // r9
  _DOT11_WFD_DISCOVER_DEVICE_FILTER *v24; // rcx
  __int16 v25; // ax
  CBSSListManager *p_m_DevicePortBSSList; // rcx
  struct CBSSEntry *v27; // rax
  CAdapterPropertyCache *v28; // rax
  int started; // eax
  int v30; // [rsp+20h] [rbp-69h]
  unsigned int m_ActivityId; // [rsp+30h] [rbp-59h]
  char v32; // [rsp+38h] [rbp-51h]
  bool v33; // [rsp+60h] [rbp-29h] BYREF
  bool v34; // [rsp+61h] [rbp-28h] BYREF
  bool v35; // [rsp+62h] [rbp-27h] BYREF
  unsigned int v36; // [rsp+64h] [rbp-25h] BYREF
  struct _DOT11_WFD_GROUP_ID v37; // [rsp+68h] [rbp-21h] BYREF

  m_pAdapter = this->m_pAdapter;
  v36 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      48,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  CJobBase::NotifyStarted(this, 1076035585);
  v5 = NotificationManager::RegisterForNotifications(
         &this->m_pAdapter->m_NotificationManager,
         WiFiIndicationBssEntryList,
         0,
         this->m_PortId,
         &this->INotifyDeviceIndicationCallback,
         &this->m_ScanResultRegistration);
  v10 = v5;
  if ( v5 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v11 = 49;
      v32 = v5;
      m_ActivityId = this->m_ActivityId;
LABEL_45:
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        v8,
        v11,
        (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
        (char)this,
        m_ActivityId,
        v32);
    }
LABEL_46:
    CJobBase::CompleteJob(this, v10);
    goto LABEL_48;
  }
  p_m_DeviceFilterCount = &this->m_DeviceFilterCount;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDDDd(
      WPP_GLOBAL_Control->DeviceExtension,
      (*((unsigned __int8 *)this + 1152) >> 5) & 1,
      v8,
      v9,
      v30,
      (char)this,
      this->m_ActivityId,
      (*((_BYTE *)this + 1153) & 8) != 0,
      (*((_BYTE *)this + 1152) & 0x20) != 0,
      *p_m_DeviceFilterCount);
  if ( (*((_BYTE *)this + 1152) & 0x20) == 0 )
  {
    p_m_DeviceFilterCount = &this->m_DeviceFilterCount;
    if ( this->m_DeviceFilterCount == 1 )
    {
      v35 = 1;
      v34 = 1;
      v33 = 1;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 4;
        WPP_RECORDER_SF_qD_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          v8,
          51,
          (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
          (char)this,
          this->m_ActivityId,
          (__int64)this->m_pDeviceFilterList);
      }
      CP2PDiscoverJob::GetDiscoverySettingsFromBitmask(v7, this->m_pDeviceFilterList->ucBitmask, &v35, &v34, &v33);
      v14 = v34;
      v15 = v35;
      *(_DWORD *)this->m_TargetGroupID.DeviceAddress = *(_DWORD *)v13;
      *(_WORD *)&this->m_TargetGroupID.DeviceAddress[4] = *(_WORD *)(v13 + 4);
      *(_OWORD *)&this->m_TargetGroupID.SSID.uSSIDLength = *(_OWORD *)(v13 + 8);
      *(_OWORD *)&this->m_TargetGroupID.SSID.ucSSID[12] = *(_OWORD *)(v13 + 24);
      *(_DWORD *)&this->m_TargetGroupID.SSID.ucSSID[28] = *(_DWORD *)(v13 + 40);
      BSSEntryByGroupID = CBSSListManager::FindBSSEntryByGroupID(
                            &m_pAdapter->m_DevicePortBSSList,
                            &this->m_TargetGroupID,
                            v15,
                            v14,
                            v33);
      if ( BSSEntryByGroupID )
      {
        if ( BSSEntryByGroupID->m_CachedChannelInfoAvailable )
        {
          this->m_ChannelHintBandInfo.BandID = BSSEntryByGroupID->m_CachedBandID;
          this->m_ChannelHintChannelNumber = BSSEntryByGroupID->m_CachedChannelNumber;
          if ( BSSEntryByGroupID->m_CachedChannelInfoAvailable )
            *((_BYTE *)this + 1152) |= 0x20u;
        }
      }
    }
  }
  for ( i = 0; i < *p_m_DeviceFilterCount; ++i )
  {
    v18 = 1;
    *(_QWORD *)v37.DeviceAddress = 0;
    v19 = i;
    m_pDeviceFilterList = this->m_pDeviceFilterList;
    uSSIDLength = m_pDeviceFilterList[v19].GroupSSID.uSSIDLength;
    v37.SSID.uSSIDLength = uSSIDLength;
    *(_OWORD *)v37.SSID.ucSSID = *(_OWORD *)m_pDeviceFilterList[v19].GroupSSID.ucSSID;
    *(_OWORD *)&v37.SSID.ucSSID[16] = *(_OWORD *)&m_pDeviceFilterList[v19].GroupSSID.ucSSID[16];
    if ( uSSIDLength )
    {
      v22 = 1;
      if ( uSSIDLength != 7 || RtlCompareMemory(v37.SSID.ucSSID, "DIRECT-", 7u) != 7 )
        v18 = 0;
    }
    else
    {
      v22 = 0;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v23 = &this->m_pDeviceFilterList[v19];
      WPP_RECORDER_SF_dD_SSID__MAC_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v23 + 8,
        v23->ucBitmask,
        (_DWORD)v23,
        v30,
        i,
        v23->ucBitmask,
        (__int64)&v23->GroupSSID,
        (__int64)v23,
        v22,
        v18);
    }
    v24 = this->m_pDeviceFilterList;
    *(_DWORD *)v37.DeviceAddress = *(_DWORD *)v24[i].DeviceID;
    v25 = *(_WORD *)&v24[v19].DeviceID[4];
    p_m_DevicePortBSSList = &this->m_pAdapter->m_DevicePortBSSList;
    *(_WORD *)&v37.DeviceAddress[4] = v25;
    v27 = CBSSListManager::FindBSSEntryByGroupID(p_m_DevicePortBSSList, &v37, v18, v22, 1);
    if ( v27 )
    {
      v27->m_BeaconTime = 0;
      v27->m_ProbeResponseTime = 0;
      v27->m_RsnaAuthAlgosSupported = 0;
      v27->m_CachedChannelInfoAvailable = 0;
      *(_OWORD *)v27->m_GroupId.DeviceAddress = 0;
      *(_OWORD *)&v27->m_GroupId.SSID.ucSSID[4] = 0;
      *(_OWORD *)&v27->m_GroupId.SSID.ucSSID[16] = 0;
    }
  }
  v28 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
  if ( (unsigned int)CPropertyCache::GetPropertyULong(v28, 0x33u, &v36) || !v36 || (*((_BYTE *)this + 1153) & 8) != 0 )
  {
    started = CP2PDiscoverJob::TriggerDiscover(this);
    v10 = started;
    if ( !started )
    {
      this->m_DiscoverState = DiscoverStateWaitingForDiscoverCompletion;
      goto LABEL_48;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v11 = 56;
    goto LABEL_44;
  }
  started = CWfdChangeListenStateJob::Initialize(
              &this->m_ListenStateJob,
              this->m_pAdapter,
              this->COidJobBase::CJobBase::m_NdisPortNumber,
              WDI_P2P_LISTEN_STATE_OFF);
  v10 = started;
  if ( started )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v11 = 53;
LABEL_44:
    v32 = started;
    m_ActivityId = this->m_ActivityId;
    goto LABEL_45;
  }
  started = CJobBase::StartChildJob(this, &this->m_ListenStateJob);
  v10 = started;
  if ( started )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v11 = 54;
    goto LABEL_44;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      v8,
      55,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId);
  this->m_DiscoverState = DiscoverStateWaitingForToggleListenStateCompletion;
LABEL_48:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v8,
      57,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId,
      v10);
  }
}

```

## disassembly

```asm
0x140047a00  push    rbp
0x140047a02  push    rbx
0x140047a03  push    rsi
0x140047a04  push    rdi
0x140047a05  push    r12
0x140047a07  push    r13
0x140047a09  push    r14
0x140047a0b  push    r15
0x140047a0d  lea     rbp, [rsp-1Fh]
0x140047a12  sub     rsp, 0A8h
0x140047a19  mov     rax, cs:__security_cookie
0x140047a20  xor     rax, rsp
0x140047a23  mov     [rbp+57h+var_48], rax
0x140047a27  mov     rsi, [rcx+200h]
0x140047a2e  xor     r13d, r13d
0x140047a31  mov     [rbp+57h+var_7C], r13d
0x140047a35  mov     rbx, rcx
0x140047a38  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140047a3f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140047a46  lea     r15, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x140047a4d  jz      short loc_140047A85
0x140047a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140047a56  cmp     byte ptr [rcx+29h], 5
0x140047a5a  jnb     short loc_140047A63
0x140047a5c  cmp     [rcx+48h], r13w
0x140047a61  jz      short loc_140047A85
0x140047a63  mov     eax, [rbx+10h]
0x140047a66  mov     r9d, 30h ; '0'
0x140047a6c  mov     rcx, [rcx+40h]
0x140047a70  mov     dl, 5
0x140047a72  mov     [rsp+0E0h+var_B0], eax
0x140047a76  mov     [rsp+0E0h+var_B8], rbx
0x140047a7b  mov     [rsp+0E0h+var_C0], r15
0x140047a80  call    WPP_RECORDER_SF_qD
0x140047a85  mov     edx, 40230001h; int
0x140047a8a  mov     rcx, rbx; this
0x140047a8d  call    ?NotifyStarted@CJobBase@@IEAAXH@Z; CJobBase::NotifyStarted(int)
0x140047a92  mov     rcx, [rbx+200h]
0x140047a99  lea     rdx, [rbx+228h]
0x140047aa0  movzx   r9d, word ptr [rbx+34h]; unsigned __int16
0x140047aa5  lea     rax, [rbx+4ECh]
0x140047aac  xor     r8d, r8d; unsigned int
0x140047aaf  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x140047ab4  mov     [rsp+0E0h+var_C0], rdx; struct INotifyDeviceIndicationCallback *
0x140047ab9  add     rcx, 460h; this
0x140047ac0  lea     edx, [r8+3Eh]; enum _WDI_INDICATION_TYPE
0x140047ac4  call    ?RegisterForNotifications@NotificationManager@@QEAAHW4_WDI_INDICATION_TYPE@@KGPEAVINotifyDeviceIndicationCallback@@PEAK@Z; NotificationManager::RegisterForNotifications(_WDI_INDICATION_TYPE,ulong,ushort,INotifyDeviceIndicationCallback *,ulong *)
0x140047ac9  mov     edi, eax
0x140047acb  test    eax, eax
0x140047acd  jz      short loc_140047AF2
0x140047acf  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140047ad6  jz      loc_140047ED3
0x140047adc  mov     ecx, [rbx+10h]
0x140047adf  mov     r9d, 31h ; '1'
0x140047ae5  mov     dword ptr [rsp+0E0h+var_A8], eax
0x140047ae9  mov     [rsp+0E0h+var_B0], ecx
0x140047aed  jmp     loc_140047EB7
0x140047af2  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140047af9  lea     rdi, [rbx+498h]
0x140047b00  jz      short loc_140047B46
0x140047b02  movzx   ecx, byte ptr [rbx+481h]
0x140047b09  mov     eax, [rdi]
0x140047b0b  movzx   edx, byte ptr [rbx+480h]
0x140047b12  mov     [rsp+0E0h+var_98], eax
0x140047b16  mov     eax, [rbx+10h]
0x140047b19  shr     ecx, 3
0x140047b1c  and     ecx, 1
0x140047b1f  shr     edx, 5
0x140047b22  and     edx, 1
0x140047b25  mov     dword ptr [rsp+0E0h+var_A0], edx
0x140047b29  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x140047b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140047b34  mov     [rsp+0E0h+var_B0], eax
0x140047b38  mov     [rsp+0E0h+var_B8], rbx
0x140047b3d  mov     rcx, [rcx+40h]
0x140047b41  call    WPP_RECORDER_SF_qDDDd
0x140047b46  test    byte ptr [rbx+480h], 20h
0x140047b4d  jnz     loc_140047C56
0x140047b53  lea     rdi, [rbx+498h]
0x140047b5a  cmp     dword ptr [rdi], 1
0x140047b5d  jnz     loc_140047C56
0x140047b63  mov     [rbp+57h+var_7E], 1
0x140047b67  mov     [rbp+57h+var_7F], 1
0x140047b6b  mov     [rbp+57h+var_80], 1
0x140047b6f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140047b76  jz      short loc_140047BAD
0x140047b78  mov     rax, [rbx+4A0h]
0x140047b7f  mov     r9d, 33h ; '3'
0x140047b85  mov     rcx, cs:WPP_GLOBAL_Control
0x140047b8c  mov     dl, 4
0x140047b8e  mov     [rsp+0E0h+var_A8], rax
0x140047b93  mov     eax, [rbx+10h]
0x140047b96  mov     [rsp+0E0h+var_B0], eax
0x140047b9a  mov     rcx, [rcx+40h]
0x140047b9e  mov     [rsp+0E0h+var_B8], rbx
0x140047ba3  mov     [rsp+0E0h+var_C0], r15
0x140047ba8  call    WPP_RECORDER_SF_qD_MAC_
0x140047bad  mov     r10, [rbx+4A0h]
0x140047bb4  lea     rax, [rbp+57h+var_80]
0x140047bb8  lea     r9, [rbp+57h+var_7F]; bool *
0x140047bbc  mov     [rsp+0E0h+var_C0], rax; bool *
0x140047bc1  lea     r8, [rbp+57h+var_7E]; bool *
0x140047bc5  mov     dl, [r10+6]; unsigned __int8
0x140047bc9  call    ?GetDiscoverySettingsFromBitmask@CP2PDiscoverJob@@QEAAXEPEA_N00@Z; CP2PDiscoverJob::GetDiscoverySettingsFromBitmask(uchar,bool *,bool *,bool *)
0x140047bce  mov     eax, [r10]
0x140047bd1  lea     rdx, [rbx+270h]; struct _DOT11_WFD_GROUP_ID *
0x140047bd8  mov     r9b, [rbp+57h+var_7F]; bool
0x140047bdc  lea     rcx, [rsi+6F8h]; this
0x140047be3  mov     r8b, [rbp+57h+var_7E]; bool
0x140047be7  mov     [rdx], eax
0x140047be9  movzx   eax, word ptr [r10+4]
0x140047bee  mov     [rdx+4], ax
0x140047bf2  movups  xmm0, xmmword ptr [r10+8]
0x140047bf7  movups  xmmword ptr [rbx+278h], xmm0
0x140047bfe  movups  xmm1, xmmword ptr [r10+18h]
0x140047c03  movups  xmmword ptr [rbx+288h], xmm1
0x140047c0a  mov     eax, [r10+28h]
0x140047c0e  mov     [rbx+298h], eax
0x140047c14  mov     al, [rbp+57h+var_80]
0x140047c17  mov     byte ptr [rsp+0E0h+var_C0], al; bool
0x140047c1b  call    ?FindBSSEntryByGroupID@CBSSListManager@@QEAAPEAVCBSSEntry@@AEBU_DOT11_WFD_GROUP_ID@@_N11@Z; CBSSListManager::FindBSSEntryByGroupID(_DOT11_WFD_GROUP_ID const &,bool,bool,bool)
0x140047c20  test    rax, rax
0x140047c23  jz      short loc_140047C56
0x140047c25  cmp     [rax+270h], r13b
0x140047c2c  jz      short loc_140047C56
0x140047c2e  mov     ecx, [rax+26Ch]
0x140047c34  mov     [rbx+4A8h], ecx
0x140047c3a  mov     ecx, [rax+268h]
0x140047c40  mov     [rbx+4E8h], ecx
0x140047c46  cmp     [rax+270h], r13b
0x140047c4d  jz      short loc_140047C56
0x140047c4f  or      byte ptr [rbx+480h], 20h
0x140047c56  mov     esi, r13d
0x140047c59  cmp     [rdi], r13d
0x140047c5c  jbe     loc_140047DA9
0x140047c62  xor     eax, eax
0x140047c64  mov     r12b, 1
0x140047c67  mov     qword ptr [rbp+57h+var_78.DeviceAddress], rax
0x140047c6b  mov     eax, esi
0x140047c6d  imul    r14, rax, 2Ch ; ','
0x140047c71  mov     rax, [rbx+4A0h]
0x140047c78  mov     ecx, [rax+r14+8]
0x140047c7d  mov     [rbp+57h+var_78.SSID.uSSIDLength], ecx
0x140047c80  movups  xmm0, xmmword ptr [rax+r14+0Ch]
0x140047c86  movups  xmmword ptr [rbp+57h+var_78.SSID.ucSSID], xmm0
0x140047c8a  movups  xmm1, xmmword ptr [rax+r14+1Ch]
0x140047c90  movups  xmmword ptr [rbp+57h+var_78.SSID.ucSSID+10h], xmm1
0x140047c94  test    ecx, ecx
0x140047c96  jnz     short loc_140047C9D
0x140047c98  mov     r15b, r13b
0x140047c9b  jmp     short loc_140047CC8
0x140047c9d  mov     r15b, r12b
0x140047ca0  cmp     ecx, 7
0x140047ca3  jnz     short loc_140047CC5
0x140047ca5  mov     r8d, ecx; Length
0x140047ca8  lea     rdx, aDirect; "DIRECT-"
0x140047caf  lea     rcx, [rbp+57h+var_78.SSID.ucSSID]; Source1
0x140047cb3  call    cs:__imp_RtlCompareMemory
0x140047cba  nop     dword ptr [rax+rax+00h]
0x140047cbf  cmp     rax, 7
0x140047cc3  jz      short loc_140047CC8
0x140047cc5  mov     r12b, r13b
0x140047cc8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140047ccf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140047cd6  jz      short loc_140047D1E
0x140047cd8  mov     r9, [rbx+4A0h]
0x140047cdf  add     r9, r14
0x140047ce2  movzx   eax, r12b
0x140047ce6  mov     [rsp+0E0h+var_90], eax
0x140047cea  movzx   ecx, r15b
0x140047cee  mov     [rsp+0E0h+var_98], ecx
0x140047cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x140047cf9  lea     rdx, [r9+8]
0x140047cfd  movzx   r8d, byte ptr [r9+6]
0x140047d02  mov     [rsp+0E0h+var_A0], r9
0x140047d07  mov     [rsp+0E0h+var_A8], rdx
0x140047d0c  mov     rcx, [rcx+40h]
0x140047d10  mov     [rsp+0E0h+var_B0], r8d
0x140047d15  mov     dword ptr [rsp+0E0h+var_B8], esi
0x140047d19  call    WPP_RECORDER_SF_dD_SSID__MAC_DD
0x140047d1e  mov     rcx, [rbx+4A0h]
0x140047d25  lea     rdx, [rbp+57h+var_78]; struct _DOT11_WFD_GROUP_ID *
0x140047d29  mov     r9b, r15b; bool
0x140047d2c  mov     byte ptr [rsp+0E0h+var_C0], 1; bool
0x140047d31  mov     r8b, r12b; bool
0x140047d34  mov     eax, [rcx+r14]
0x140047d38  mov     dword ptr [rbp+57h+var_78.DeviceAddress], eax
0x140047d3b  movzx   eax, word ptr [rcx+r14+4]
0x140047d41  mov     rcx, [rbx+200h]
0x140047d48  add     rcx, 6F8h; this
0x140047d4f  mov     word ptr [rbp+57h+var_78.DeviceAddress+4], ax
0x140047d53  call    ?FindBSSEntryByGroupID@CBSSListManager@@QEAAPEAVCBSSEntry@@AEBU_DOT11_WFD_GROUP_ID@@_N11@Z; CBSSListManager::FindBSSEntryByGroupID(_DOT11_WFD_GROUP_ID const &,bool,bool,bool)
0x140047d58  test    rax, rax
0x140047d5b  jz      short loc_140047D91
0x140047d5d  mov     [rax+200h], r13
0x140047d64  xorps   xmm0, xmm0
0x140047d67  mov     [rax+1E8h], r13
0x140047d6e  mov     [rax+2C8h], r13d
0x140047d75  mov     [rax+270h], r13b
0x140047d7c  movups  xmmword ptr [rax+298h], xmm0
0x140047d83  movups  xmmword ptr [rax+2A8h], xmm0
0x140047d8a  movups  xmmword ptr [rax+2B4h], xmm0
0x140047d91  inc     esi
0x140047d93  cmp     esi, [rdi]
0x140047d95  jb      loc_140047C62
0x140047d9b  lea     r14, WPP_RECORDER_INITIALIZED
0x140047da2  lea     r15, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x140047da9  mov     rcx, [rbx+200h]
0x140047db0  add     rcx, 8
0x140047db4  mov     rax, [rcx]
0x140047db7  mov     rax, [rax+8]
0x140047dbb  call    _guard_dispatch_icall
0x140047dc0  lea     r8, [rbp+57h+var_7C]; unsigned int *
0x140047dc4  mov     edx, 33h ; '3'; unsigned int
0x140047dc9  mov     rcx, rax; this
0x140047dcc  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140047dd1  test    eax, eax
0x140047dd3  jnz     loc_140047E8F
0x140047dd9  cmp     [rbp+57h+var_7C], r13d
0x140047ddd  jz      loc_140047E8F
0x140047de3  test    byte ptr [rbx+481h], 8
0x140047dea  jnz     loc_140047E8F
0x140047df0  mov     r8d, [rbx+38h]; unsigned int
0x140047df4  lea     rsi, [rbx+5C0h]
0x140047dfb  mov     rdx, [rbx+200h]; struct CAdapter *
0x140047e02  mov     rcx, rsi; this
0x140047e05  xor     r9d, r9d; enum _WDI_P2P_LISTEN_STATE
0x140047e08  call    ?Initialize@CWfdChangeListenStateJob@@QEAAHPEAVCAdapter@@KW4_WDI_P2P_LISTEN_STATE@@@Z; CWfdChangeListenStateJob::Initialize(CAdapter *,ulong,_WDI_P2P_LISTEN_STATE)
0x140047e0d  mov     edi, eax
0x140047e0f  test    eax, eax
0x140047e11  jz      short loc_140047E2B
0x140047e13  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140047e1a  jz      loc_140047ED3
0x140047e20  mov     r9d, 35h ; '5'
0x140047e26  jmp     loc_140047EAC
0x140047e2b  mov     rdx, rsi; struct CJobBase *
0x140047e2e  mov     rcx, rbx; this
0x140047e31  call    ?StartChildJob@CJobBase@@IEAAHPEAV1@@Z; CJobBase::StartChildJob(CJobBase *)
0x140047e36  mov     edi, eax
0x140047e38  test    eax, eax
0x140047e3a  jz      short loc_140047E51
0x140047e3c  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140047e43  jz      loc_140047ED3
0x140047e49  mov     r9d, 36h ; '6'
0x140047e4f  jmp     short loc_140047EAC
0x140047e51  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140047e58  jz      short loc_140047E83
0x140047e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140047e61  mov     r9d, 37h ; '7'
0x140047e67  mov     eax, [rbx+10h]
0x140047e6a  mov     dl, 4
0x140047e6c  mov     [rsp+0E0h+var_B0], eax
0x140047e70  mov     [rsp+0E0h+var_B8], rbx
0x140047e75  mov     rcx, [rcx+40h]
0x140047e79  mov     [rsp+0E0h+var_C0], r15
0x140047e7e  call    WPP_RECORDER_SF_qD
0x140047e83  mov     dword ptr [rbx+238h], 1
0x140047e8d  jmp     short loc_140047EE9
0x140047e8f  mov     rcx, rbx; this
0x140047e92  call    ?TriggerDiscover@CP2PDiscoverJob@@QEAAHXZ; CP2PDiscoverJob::TriggerDiscover(void)
0x140047e97  mov     edi, eax
0x140047e99  test    eax, eax
0x140047e9b  jz      short loc_140047EDF
0x140047e9d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140047ea4  jz      short loc_140047ED3
0x140047ea6  mov     r9d, 38h ; '8'
0x140047eac  mov     dword ptr [rsp+0E0h+var_A8], eax
0x140047eb0  mov     eax, [rbx+10h]
0x140047eb3  mov     [rsp+0E0h+var_B0], eax
0x140047eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140047ebe  mov     dl, 2
0x140047ec0  mov     [rsp+0E0h+var_B8], rbx
0x140047ec5  mov     [rsp+0E0h+var_C0], r15
0x140047eca  mov     rcx, [rcx+40h]
0x140047ece  call    WPP_RECORDER_SF_qDD
0x140047ed3  mov     edx, edi; int
0x140047ed5  mov     rcx, rbx; this
0x140047ed8  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x140047edd  jmp     short loc_140047EE9
0x140047edf  mov     dword ptr [rbx+238h], 2
0x140047ee9  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140047ef0  jz      short loc_140047F2C
0x140047ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x140047ef9  cmp     byte ptr [rcx+29h], 5
0x140047efd  jnb     short loc_140047F06
0x140047eff  cmp     [rcx+48h], r13w
0x140047f04  jz      short loc_140047F2C
0x140047f06  mov     eax, [rbx+10h]
0x140047f09  mov     r9d, 39h ; '9'
0x140047f0f  mov     rcx, [rcx+40h]
0x140047f13  mov     dl, 5
0x140047f15  mov     dword ptr [rsp+0E0h+var_A8], edi
0x140047f19  mov     [rsp+0E0h+var_B0], eax
0x140047f1d  mov     [rsp+0E0h+var_B8], rbx
0x140047f22  mov     [rsp+0E0h+var_C0], r15
0x140047f27  call    WPP_RECORDER_SF_qDD
0x140047f2c  mov     rcx, [rbp+57h+var_48]
0x140047f30  xor     rcx, rsp; StackCookie
0x140047f33  call    __security_check_cookie
0x140047f38  add     rsp, 0A8h
  ... truncated ...
```
