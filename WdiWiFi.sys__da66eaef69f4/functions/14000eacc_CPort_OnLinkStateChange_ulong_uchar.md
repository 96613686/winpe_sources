# CPort::OnLinkStateChange(ulong,uchar *)

- ea: `0x14000eacc`
- end: `0x14000f05a`
- name: `?OnLinkStateChange@CPort@@QEAAXKPEAE@Z`
- size: `1422`
- prototype: `void __fastcall(CPort *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x14000e2c0`

## callees

- `0x14000cfd4`
- `0x14000d3e0`
- `0x14000d4b0`
- `0x14000d79c`
- `0x14000e270`
- `0x14000eacc`
- `0x14000f060`
- `0x1400100f8`
- `0x140010390`
- `0x140010730`
- `0x140010830`
- `0x1400109a0`
- `0x140010b20`
- `0x140010c38`
- `0x1400176b0`
- `0x140028f1c`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`
- `0x14006ab80`
- `0x14008db18`
- `0x1400da4f0`
- `0x1400da680`

## pseudocode

```c
void __fastcall CPort::OnLinkStateChange(CPort *this, int a2, unsigned __int8 *a3)
{
  int v4; // edi
  _TLV_CONTEXT *p_m_TlvContext; // r8
  int v7; // r8d
  int v8; // edi
  unsigned int v9; // r12d
  int PropertyULong; // eax
  int v11; // edx
  unsigned int v12; // r8d
  char v13; // di
  int v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  CConnectedPeer *v17; // rax
  int v18; // edx
  struct CConnectedPeer *v19; // r14
  _WFC_PORT_TYPE m_WfcPortType; // edx
  __int64 v21; // r13
  CBSSListManager *v22; // r13
  CBSSEntry *BSSEntry; // rax
  CBSSEntry *v24; // rdi
  struct DOT11_CONNECTION_INFO *CurrentConnectionInfo; // rax
  enum _DOT11_BAND_ID v26; // eax
  unsigned int *v27; // r8
  unsigned int LinkQuality; // eax
  int v29; // edx
  int v30; // r8d
  int v31; // r8d
  enum _WDI_ROAM_CONFIGURATION_FLAGS RoamConfig; // eax
  enum _WDI_ASSOC_STATUS v33; // r8d
  int v34; // r8d
  int m_WfcPortId; // edx
  __int64 v36; // [rsp+28h] [rbp-48h]
  unsigned __int8 v37[4]; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v38; // [rsp+44h] [rbp-2Ch] BYREF
  int v39; // [rsp+48h] [rbp-28h]
  unsigned int v40[4]; // [rsp+50h] [rbp-20h] BYREF
  int v41; // [rsp+60h] [rbp-10h]

  v4 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      155,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  p_m_TlvContext = &this->m_pAdapter->m_TlvContext;
  v41 = 0;
  *(_OWORD *)v40 = 0;
  v39 = ParseWdiIndicationLinkStateChangeFromIhv((unsigned int)(v4 - 48), a3 + 48, p_m_TlvContext, v40);
  v8 = v39;
  if ( !v39 )
  {
    v9 = (unsigned __int8)v41;
    v38 = 0;
    PropertyULong = CPropertyCache::GetPropertyULong(&this->m_PortPropertyCache, 2u, &v38);
    v12 = v40[2];
    if ( PropertyULong || (v13 = 0, v40[2] != v38) )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 4;
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v40[2],
          157,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          this->m_WfcPortId,
          v40[2]);
        v12 = v40[2];
      }
      CPropertyCache::SetPropertyULong(&this->m_PortPropertyCache, 2u, v12);
      v13 = 1;
    }
    v14 = CPropertyCache::GetPropertyULong(&this->m_PortPropertyCache, 3u, &v38);
    v16 = v40[3];
    if ( v14 || v40[3] != v38 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 4;
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          v40[3],
          158,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          this->m_WfcPortId,
          v40[3]);
        v16 = v40[3];
      }
      CPropertyCache::SetPropertyULong(&this->m_PortPropertyCache, 3u, v16);
    }
    else if ( !v13 )
    {
      goto LABEL_9;
    }
    CPort::UpdateLinkState(this);
LABEL_9:
    if ( LOBYTE(v40[0]) == 0xFF && *(unsigned int *)((char *)v40 + 1) == -1 && BYTE1(v40[1]) == 0xFF )
      v17 = this->m_pPeerList->FindPeerByAssociationState(this->m_pPeerList, 3);
    else
      v17 = this->m_pPeerList->FindPeerByAddress(this->m_pPeerList, v40);
    v19 = v17;
    if ( !v17 )
      goto LABEL_22;
    m_WfcPortType = this->m_WfcPortType;
    v21 = 1784;
    if ( m_WfcPortType != WfcPortTypeWFDRole )
      v21 = 1384;
    v22 = (CBSSListManager *)((char *)this->m_pAdapter + v21);
    BSSEntry = CBSSListManager::FindBSSEntry(
                 v22,
                 (const unsigned __int8 (*)[6])v17->m_MacAddress,
                 &v17->m_SSID,
                 m_WfcPortType == WfcPortTypeExtSTA);
    v24 = BSSEntry;
    if ( BSSEntry )
    {
      CBSSEntry::OnLinkQualityUpdate(BSSEntry, v9, v22);
      CurrentConnectionInfo = CPort::GetCurrentConnectionInfo(this);
      if ( CurrentConnectionInfo )
      {
        if ( CurrentConnectionInfo->NumLinks )
        {
          CurrentConnectionInfo->LinkInfo[0].Rssi = v24->m_SignalInfo.Rssi;
          CurrentConnectionInfo->LinkInfo[0].ChannelCenterFrequencyMhz = v24->m_CachedChannelCenterFrequency;
          v26 = CWabiToDot11Converter::MapBandID(v24->m_BssChannelInfo.BandId);
          v27[34] = v26;
          v27[35] = v24->m_BssChannelInfo.Channel;
          LinkQuality = v9;
          if ( (unsigned __int8)(v9 - 1) > 0x63u )
            LinkQuality = v24->m_SignalInfo.LinkQuality;
          v27[22] = LinkQuality;
          if ( (unsigned int)CPropertyCache::SetPropertyBuffer(
                               &this->m_PortPropertyCache,
                               0x27u,
                               *v27,
                               (unsigned __int8 *)v27)
            && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v29) = 4;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v29,
              1,
              159,
              (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
          }
        }
      }
    }
    v37[0] = 0;
    if ( !(unsigned int)CPropertyCache::GetPropertyUchar(&this->m_PortPropertyCache, 4u, v37) && (_BYTE)v9 == v37[0] )
      goto LABEL_22;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      m_WfcPortId = this->m_WfcPortId;
      LOBYTE(m_WfcPortId) = 4;
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        m_WfcPortId,
        v30,
        160,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        v9);
    }
    CPropertyCache::SetPropertyUchar(&this->m_PortPropertyCache, 4u, v9);
    v19->m_LinkQuality = v9;
    CPort::UpdateLinkQuality(this, v19);
    CPort::CheckAndNotifyLinkDegradedStatus(this, v9);
    if ( CPort::DetermineIfSwitchToBetterAPNeeded(this, v19) )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 4;
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          v31,
          161,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          this->m_WfcPortId,
          v9);
      }
      RoamConfig = CConnectHelpers::GetRoamConfig(WfcRoamConnectTriggerToFindBetterAP_BestEffort);
      v8 = CPort::TriggerWdiInitiatedRoam(this, WfcRoamConnectTriggerToFindBetterAP_BestEffort, v33, RoamConfig);
      if ( v8 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            v34,
            162,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            (char)this,
            this->m_WfcPortId);
        }
        v8 = 0;
      }
    }
    else
    {
LABEL_22:
      v8 = v39;
    }
    goto LABEL_23;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return;
  WPP_RECORDER_SF_qD(
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    v7,
    156,
    (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
    (char)this,
    this->m_WfcPortId);
LABEL_23:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v36) = v8;
    LOBYTE(v18) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      1,
      163,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v36);
  }
}

```

## disassembly

```asm
0x14000eacc  mov     [rsp-38h+arg_18], rbx
0x14000ead1  push    rbp
0x14000ead2  push    rsi
0x14000ead3  push    rdi
0x14000ead4  push    r12
0x14000ead6  push    r13
0x14000ead8  push    r14
0x14000eada  push    r15
0x14000eadc  mov     rbp, rsp
0x14000eadf  sub     rsp, 70h
0x14000eae3  mov     rax, cs:__security_cookie
0x14000eaea  xor     rax, rsp
0x14000eaed  mov     [rbp+var_8], rax
0x14000eaf1  mov     rsi, r8
0x14000eaf4  mov     edi, edx
0x14000eaf6  mov     rbx, rcx
0x14000eaf9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000eb00  xor     r13d, r13d
0x14000eb03  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000eb0a  lea     r15, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14000eb11  jnz     loc_14000ED40
0x14000eb17  mov     r8, [rbx+58h]
0x14000eb1b  lea     rdx, [rsi+30h]
0x14000eb1f  xorps   xmm0, xmm0
0x14000eb22  lea     ecx, [rdi-30h]
0x14000eb25  xor     eax, eax
0x14000eb27  lea     r9, [rbp+var_20]
0x14000eb2b  add     r8, 3FF8h
0x14000eb32  mov     [rbp+var_10], eax
0x14000eb35  movups  xmmword ptr [rbp+var_20], xmm0
0x14000eb39  call    ParseWdiIndicationLinkStateChangeFromIhv
0x14000eb3e  mov     [rbp+var_28], eax
0x14000eb41  mov     edi, eax
0x14000eb43  test    eax, eax
0x14000eb45  jnz     loc_14000EF1F
0x14000eb4b  movzx   r12d, byte ptr [rbp+var_10]
0x14000eb50  lea     esi, [rax+2]
0x14000eb53  lea     r15, [rbx+3A8h]
0x14000eb5a  mov     [rbp+var_2C], r13d
0x14000eb5e  mov     edx, esi; unsigned int
0x14000eb60  lea     r8, [rbp+var_2C]; unsigned int *
0x14000eb64  mov     rcx, r15; this
0x14000eb67  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x14000eb6c  mov     r8d, [rbp+var_20+8]
0x14000eb70  test    eax, eax
0x14000eb72  jnz     loc_14000EDCE
0x14000eb78  mov     dil, r13b
0x14000eb7b  cmp     r8d, [rbp+var_2C]
0x14000eb7f  jnz     loc_14000EDCE
0x14000eb85  lea     r14, WPP_RECORDER_INITIALIZED
0x14000eb8c  lea     r8, [rbp+var_2C]; unsigned int *
0x14000eb90  mov     edx, 3; unsigned int
0x14000eb95  mov     rcx, r15; this
0x14000eb98  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x14000eb9d  mov     r8d, [rbp+var_20+0Ch]
0x14000eba1  test    eax, eax
0x14000eba3  jnz     loc_14000ED79
0x14000eba9  cmp     r8d, [rbp+var_2C]
0x14000ebad  jnz     loc_14000ED79
0x14000ebb3  test    dil, dil
0x14000ebb6  jz      short loc_14000EBC0
0x14000ebb8  mov     rcx, rbx; this
0x14000ebbb  call    ?UpdateLinkState@CPort@@QEAAXXZ; CPort::UpdateLinkState(void)
0x14000ebc0  mov     al, 0FFh
0x14000ebc2  cmp     byte ptr [rbp+var_20], al
0x14000ebc5  jz      loc_14000EFA0
0x14000ebcb  mov     rcx, [rbx+398h]
0x14000ebd2  lea     rdx, [rbp+var_20]
0x14000ebd6  mov     rax, [rcx]
0x14000ebd9  mov     rax, [rax+10h]
0x14000ebdd  call    _guard_dispatch_icall
0x14000ebe2  mov     r14, rax
0x14000ebe5  test    rax, rax
0x14000ebe8  jz      loc_14000ECE5
0x14000ebee  mov     edx, [rbx+68h]
0x14000ebf1  lea     r8, [r14+20h]; struct _DOT11_SSID *
0x14000ebf5  cmp     edx, 8
0x14000ebf8  mov     eax, 568h
0x14000ebfd  mov     r13d, 6F8h
0x14000ec03  cmovnz  r13d, eax
0x14000ec07  add     r13, [rbx+58h]
0x14000ec0b  cmp     edx, 1
0x14000ec0e  mov     rcx, r13; this
0x14000ec11  lea     rdx, [r14+1]; unsigned __int8 (*)[6]
0x14000ec15  setz    r9b; bool
0x14000ec19  call    ?FindBSSEntry@CBSSListManager@@QEAAPEAVCBSSEntry@@AEAY05$$CBEQEAU_DOT11_SSID@@_N@Z; CBSSListManager::FindBSSEntry(uchar const (&)[6],_DOT11_SSID * const,bool)
0x14000ec1e  mov     rdi, rax
0x14000ec21  test    rax, rax
0x14000ec24  jz      loc_14000F02D
0x14000ec2a  mov     r8, r13; struct CBSSListManager *
0x14000ec2d  mov     dl, r12b; unsigned __int8
0x14000ec30  mov     rcx, rax; this
0x14000ec33  call    ?OnLinkQualityUpdate@CBSSEntry@@QEAAXEPEAVCBSSListManager@@@Z; CBSSEntry::OnLinkQualityUpdate(uchar,CBSSListManager *)
0x14000ec38  mov     rcx, rbx; this
0x14000ec3b  call    ?GetCurrentConnectionInfo@CPort@@QEAAPEAUDOT11_CONNECTION_INFO@@XZ; CPort::GetCurrentConnectionInfo(void)
0x14000ec40  xor     r13d, r13d
0x14000ec43  mov     r8, rax
0x14000ec46  test    rax, rax
0x14000ec49  jz      short loc_14000ECB7
0x14000ec4b  cmp     [rax+68h], r13d
0x14000ec4f  jbe     short loc_14000ECB7
0x14000ec51  mov     ecx, [rdi+1D0h]
0x14000ec57  mov     [rax+94h], ecx
0x14000ec5d  mov     ecx, [rdi+278h]
0x14000ec63  mov     [rax+90h], ecx
0x14000ec69  mov     ecx, [rdi+20Ch]; enum _WDI_BAND_ID
0x14000ec6f  call    ?MapBandID@CWabiToDot11Converter@@SA?AW4_DOT11_BAND_ID@@W4_WDI_BAND_ID@@@Z; CWabiToDot11Converter::MapBandID(_WDI_BAND_ID)
0x14000ec74  mov     [r8+88h], eax
0x14000ec7b  mov     eax, [rdi+208h]
0x14000ec81  mov     [r8+8Ch], eax
0x14000ec88  lea     eax, [r12-1]
0x14000ec8d  cmp     al, 63h ; 'c'
0x14000ec8f  mov     eax, r12d
0x14000ec92  ja      loc_14000EE2A
0x14000ec98  mov     [r8+58h], eax
0x14000ec9c  mov     r9, r8; unsigned __int8 *
0x14000ec9f  mov     r8d, [r8]; unsigned int
0x14000eca2  mov     edx, 27h ; '''; unsigned int
0x14000eca7  mov     rcx, r15; this
0x14000ecaa  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEAE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar *)
0x14000ecaf  test    eax, eax
0x14000ecb1  jnz     loc_14000EFEA
0x14000ecb7  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000ecbe  lea     r8, [rbp+var_30]; unsigned __int8 *
0x14000ecc2  mov     [rbp+var_30], r13b
0x14000ecc6  mov     edx, 4; unsigned int
0x14000eccb  mov     rcx, r15; this
0x14000ecce  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x14000ecd3  test    eax, eax
0x14000ecd5  jnz     loc_14000EE35
0x14000ecdb  cmp     r12b, [rbp+var_30]
0x14000ecdf  jnz     loc_14000EE35
0x14000ece5  mov     edi, [rbp+var_28]
0x14000ece8  lea     r14, WPP_RECORDER_INITIALIZED
0x14000ecef  lea     r15, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14000ecf6  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000ecfd  jz      short loc_14000ED1B
0x14000ecff  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed06  cmp     byte ptr [rcx+29h], 5
0x14000ed0a  jnb     loc_14000F035
0x14000ed10  cmp     [rcx+48h], r13w
0x14000ed15  jnz     loc_14000F035
0x14000ed1b  mov     rcx, [rbp+var_8]
0x14000ed1f  xor     rcx, rsp; StackCookie
0x14000ed22  call    __security_check_cookie
0x14000ed27  mov     rbx, [rsp+70h+arg_18]
0x14000ed2f  add     rsp, 70h
0x14000ed33  pop     r15
0x14000ed35  pop     r14
0x14000ed37  pop     r13
0x14000ed39  pop     r12
0x14000ed3b  pop     rdi
0x14000ed3c  pop     rsi
0x14000ed3d  pop     rbp
0x14000ed3e  retn
0x14000ed40  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed47  cmp     byte ptr [rcx+29h], 5
0x14000ed4b  jnb     short loc_14000ED58
0x14000ed4d  cmp     [rcx+48h], r13w
0x14000ed52  jz      loc_14000EB17
0x14000ed58  mov     rcx, [rcx+40h]
0x14000ed5c  mov     r9d, 9Bh
0x14000ed62  mov     r8d, 1
0x14000ed68  mov     [rsp+70h+var_50], r15
0x14000ed6d  mov     dl, 5
0x14000ed6f  call    WPP_RECORDER_SF_
0x14000ed74  jmp     loc_14000EB17
0x14000ed79  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000ed80  jz      short loc_14000EDBC
0x14000ed82  movzx   eax, word ptr [rbx+64h]
0x14000ed86  mov     r9d, 9Eh
0x14000ed8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed93  mov     dl, 4
0x14000ed95  mov     [rsp+70h+var_38], r8d
0x14000ed9a  mov     [rsp+70h+var_40], eax
0x14000ed9e  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14000eda5  mov     [rsp+70h+var_48], rbx
0x14000edaa  mov     rcx, [rcx+40h]
0x14000edae  mov     [rsp+70h+var_50], rax
0x14000edb3  call    WPP_RECORDER_SF_qDL
0x14000edb8  mov     r8d, [rbp+var_20+0Ch]; unsigned int
0x14000edbc  mov     edx, 3; unsigned int
0x14000edc1  mov     rcx, r15; this
0x14000edc4  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14000edc9  jmp     loc_14000EBB8
0x14000edce  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000edd5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000eddc  jz      short loc_14000EE18
0x14000edde  movzx   eax, word ptr [rbx+64h]
0x14000ede2  mov     r9d, 9Dh
0x14000ede8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edef  mov     dl, 4
0x14000edf1  mov     [rsp+70h+var_38], r8d
0x14000edf6  mov     [rsp+70h+var_40], eax
0x14000edfa  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14000ee01  mov     [rsp+70h+var_48], rbx
0x14000ee06  mov     rcx, [rcx+40h]
0x14000ee0a  mov     [rsp+70h+var_50], rax
0x14000ee0f  call    WPP_RECORDER_SF_qDL
0x14000ee14  mov     r8d, [rbp+var_20+8]; unsigned int
0x14000ee18  mov     edx, esi; unsigned int
0x14000ee1a  mov     rcx, r15; this
0x14000ee1d  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14000ee22  mov     dil, 1
0x14000ee25  jmp     loc_14000EB8C
0x14000ee2a  mov     eax, [rdi+1D4h]
0x14000ee30  jmp     loc_14000EC98
0x14000ee35  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14000ee3c  jnz     loc_14000EF65
0x14000ee42  mov     r8b, r12b; unsigned __int8
0x14000ee45  mov     edx, 4; unsigned int
0x14000ee4a  mov     rcx, r15; this
0x14000ee4d  call    ?SetPropertyUchar@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyUchar(ulong,uchar)
0x14000ee52  mov     rdx, r14; struct CConnectedPeer *
0x14000ee55  mov     [r14+0Ch], r12b
0x14000ee59  mov     rcx, rbx; this
0x14000ee5c  call    ?UpdateLinkQuality@CPort@@QEAAXPEAVCConnectedPeer@@@Z; CPort::UpdateLinkQuality(CConnectedPeer *)
0x14000ee61  mov     edx, r12d; unsigned int
0x14000ee64  mov     rcx, rbx; this
0x14000ee67  call    ?CheckAndNotifyLinkDegradedStatus@CPort@@QEAAXK@Z; CPort::CheckAndNotifyLinkDegradedStatus(ulong)
0x14000ee6c  mov     rdx, r14; struct CConnectedPeer *
0x14000ee6f  mov     rcx, rbx; this
0x14000ee72  call    ?DetermineIfSwitchToBetterAPNeeded@CPort@@QEAA_NPEAVCConnectedPeer@@@Z; CPort::DetermineIfSwitchToBetterAPNeeded(CConnectedPeer *)
0x14000ee77  test    al, al
0x14000ee79  jz      loc_14000ECE5
0x14000ee7f  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ee86  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000ee8d  lea     r15, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14000ee94  jz      short loc_14000EEC5
0x14000ee96  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee9d  mov     r9d, 0A1h
0x14000eea3  movzx   eax, word ptr [rbx+64h]
0x14000eea7  mov     dl, 4
0x14000eea9  mov     [rsp+70h+var_38], r12d
0x14000eeae  mov     [rsp+70h+var_40], eax
0x14000eeb2  mov     rcx, [rcx+40h]
0x14000eeb6  mov     [rsp+70h+var_48], rbx
0x14000eebb  mov     [rsp+70h+var_50], r15
0x14000eec0  call    WPP_RECORDER_SF_qDL
0x14000eec5  mov     ecx, esi; enum _WFC_ROAM_CONNECT_TRIGGER
0x14000eec7  call    ?GetRoamConfig@CConnectHelpers@@SA?AW4_WDI_ROAM_CONFIGURATION_FLAGS@@W4_WFC_ROAM_CONNECT_TRIGGER@@@Z; CConnectHelpers::GetRoamConfig(_WFC_ROAM_CONNECT_TRIGGER)
0x14000eecc  mov     r9d, eax; enum _WDI_ROAM_CONFIGURATION_FLAGS
0x14000eecf  mov     rcx, rbx; this
0x14000eed2  mov     edx, esi; enum _WFC_ROAM_CONNECT_TRIGGER
0x14000eed4  call    ?TriggerWdiInitiatedRoam@CPort@@QEAAHW4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ASSOC_STATUS@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@@Z; CPort::TriggerWdiInitiatedRoam(_WFC_ROAM_CONNECT_TRIGGER,_WDI_ASSOC_STATUS,_WDI_ROAM_CONFIGURATION_FLAGS)
0x14000eed9  mov     edi, eax
0x14000eedb  test    eax, eax
0x14000eedd  jz      loc_14000ECF6
0x14000eee3  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000eeea  jz      short loc_14000EF17
0x14000eeec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eef3  mov     r9d, 0A2h
0x14000eef9  movzx   eax, word ptr [rbx+64h]
0x14000eefd  mov     dl, sil
0x14000ef00  mov     [rsp+70h+var_40], eax
0x14000ef04  mov     [rsp+70h+var_48], rbx
0x14000ef09  mov     rcx, [rcx+40h]
0x14000ef0d  mov     [rsp+70h+var_50], r15
0x14000ef12  call    WPP_RECORDER_SF_qD
0x14000ef17  mov     edi, r13d
0x14000ef1a  jmp     loc_14000ECF6
0x14000ef1f  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ef26  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000ef2d  jz      loc_14000ED1B
0x14000ef33  movzx   ecx, word ptr [rbx+64h]
0x14000ef37  mov     r9d, 9Ch
0x14000ef3d  mov     [rsp+70h+var_40], ecx
0x14000ef41  mov     edx, 2
0x14000ef46  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef4d  mov     [rsp+70h+var_48], rbx
0x14000ef52  mov     [rsp+70h+var_50], r15
0x14000ef57  mov     rcx, [rcx+40h]
0x14000ef5b  call    WPP_RECORDER_SF_qD
0x14000ef60  jmp     loc_14000ECF6
0x14000ef65  movzx   edx, word ptr [rbx+64h]
0x14000ef69  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14000ef70  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef77  mov     r9d, 0A0h
0x14000ef7d  mov     [rsp+70h+var_38], r12d
0x14000ef82  mov     [rsp+70h+var_40], edx
0x14000ef86  mov     dl, 4
0x14000ef88  mov     [rsp+70h+var_48], rbx
0x14000ef8d  mov     rcx, [rcx+40h]
0x14000ef91  mov     [rsp+70h+var_50], rax
0x14000ef96  call    WPP_RECORDER_SF_qDL
0x14000ef9b  jmp     loc_14000EE42
0x14000efa0  cmp     byte ptr [rbp+var_20+1], al
0x14000efa3  jnz     loc_14000EBCB
0x14000efa9  cmp     byte ptr [rbp+var_20+2], al
0x14000efac  jnz     loc_14000EBCB
0x14000efb2  cmp     byte ptr [rbp+var_20+3], al
0x14000efb5  jnz     loc_14000EBCB
0x14000efbb  cmp     byte ptr [rbp+var_20+4], al
0x14000efbe  jnz     loc_14000EBCB
0x14000efc4  cmp     byte ptr [rbp+var_20+5], al
0x14000efc7  jnz     loc_14000EBCB
0x14000efcd  mov     rcx, [rbx+398h]
0x14000efd4  mov     edx, 3
0x14000efd9  mov     rax, [rcx]
0x14000efdc  mov     rax, [rax+18h]
  ... truncated ...
```
