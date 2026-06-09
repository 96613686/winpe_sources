# CConnectJob::CheckAndUpdateCandidates(void)

- ea: `0x1400156a8`
- end: `0x140015dd1`
- name: `?CheckAndUpdateCandidates@CConnectJob@@AEAAHXZ`
- size: `1833`
- prototype: `__int64 __fastcall(CConnectJob *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140014828`
- `0x140015390`

## callees

- `0x140010730`
- `0x1400109f8`
- `0x1400122e0`
- `0x140013000`
- `0x1400156a8`
- `0x140015dd8`
- `0x140016d88`
- `0x1400297a0`
- `0x14002aa28`
- `0x14004ff88`
- `0x1400da680`

## pseudocode

```c
__int64 __fastcall CConnectJob::CheckAndUpdateCandidates(CConnectJob *this)
{
  CPortPropertyCache *m_pPortPropertyCache; // rsi
  CAdapterPropertyCache *v3; // rax
  struct _ROAM_CONTROL_PARAMETERS *RoamControlParameters; // r12
  unsigned int i; // edx
  CPort *v6; // rdi
  int v7; // edx
  int v8; // r8d
  __int64 v9; // r15
  int v10; // eax
  _ROAM_TRACELOGGING_DATA *v11; // rdx
  unsigned int m_CachedRank; // r8d
  unsigned int v13; // r14d
  _ROAM_TRACELOGGING_DATA *m_pRoamTraceLoggingData; // rax
  unsigned int m_TempBSSCandidateCount; // eax
  _ROAM_TRACELOGGING_DATA *v16; // rax
  _WDI_ROAM_CONFIGURATION_FLAGS m_RoamConfigFlags; // r9d
  CScanJob **p_m_pScanJob; // rcx
  char v20; // bp
  _WFC_CONNECT_SCAN_TYPE m_LastScanType; // r8d
  int v22; // eax
  unsigned int LinkQuality; // r10d
  CBSSEntry *v24; // r9
  int v25; // ecx
  _ROAM_TRACELOGGING_DATA *v26; // r8
  _ROAM_TRACELOGGING_DATA *v27; // rax
  int v28; // r8d
  int v29; // r9d
  PDEVICE_OBJECT v30; // rcx
  int v31; // r9d
  char v32[8]; // [rsp+38h] [rbp-50h]
  char v33; // [rsp+38h] [rbp-50h]
  char v34; // [rsp+48h] [rbp-40h]
  unsigned int v35; // [rsp+90h] [rbp+8h] BYREF
  unsigned __int8 *v36; // [rsp+98h] [rbp+10h] BYREF

  m_pPortPropertyCache = this->m_pPortPropertyCache;
  if ( !m_pPortPropertyCache )
  {
    m_pPortPropertyCache = this->m_pPropertyCacheDirectory->GetPortPropertyCache(
                             this->m_pPropertyCacheDirectory,
                             this->m_PortId);
    this->m_pPortPropertyCache = m_pPortPropertyCache;
  }
  v3 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
  RoamControlParameters = CConnectHelpers::GetRoamControlParameters(v3);
  for ( i = 0; i < 5; ++i )
  {
    v6 = this->m_pAdapter->m_pPortList[i];
    if ( v6 && v6->m_WfcPortId == this->m_PortId )
      goto LABEL_7;
  }
  v6 = 0;
LABEL_7:
  v9 = (__int64)v6->m_pPeerList->FindPeerByAssociationState(v6->m_pPeerList, dot11_assoc_state_auth_assoc);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      152,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  v10 = CConnectJob::PickCandidates(this, &this->m_ConnectionProfile);
  v13 = v10;
  if ( v10 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v13;
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      m_CachedRank,
      153,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v10);
    goto LABEL_19;
  }
  m_pRoamTraceLoggingData = v6->m_pRoamTraceLoggingData;
  if ( m_pRoamTraceLoggingData )
    m_pRoamTraceLoggingData->roamOccured = 1;
  m_TempBSSCandidateCount = this->m_TempBSSCandidateCount;
  if ( !m_TempBSSCandidateCount )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v11) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v11,
        m_CachedRank,
        154,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    this->m_ConnectCompletionStatus = WDI_ASSOC_STATUS_RESERVED_1;
    v16 = v6->m_pRoamTraceLoggingData;
    if ( v16 )
      v16->roamDebugCode = WdiRoamDebugCodeNoCandidatesFound;
    goto LABEL_19;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_qDL(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      m_CachedRank,
      155,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      m_TempBSSCandidateCount);
  }
  m_RoamConfigFlags = this->m_RoamConfigFlags;
  p_m_pScanJob = &this->m_pScanJob;
  if ( (m_RoamConfigFlags & 0x10) == 0 || (v20 = 1, *p_m_pScanJob) )
    v20 = 0;
  m_LastScanType = this->m_LastScanType;
  if ( m_LastScanType )
  {
    if ( m_LastScanType <= WfcConnectScanTypeChannelHint )
    {
      LODWORD(v11) = 20;
    }
    else
    {
      if ( m_LastScanType >= WfcConnectScanTypeFull )
        goto LABEL_41;
      v22 = 0;
      if ( *p_m_pScanJob )
        v22 = 20;
      LODWORD(v11) = v22;
    }
  }
  else
  {
    LODWORD(v11) = 0;
  }
  if ( (m_RoamConfigFlags & 1) != 0 )
  {
    v36 = 0;
    v35 = 0;
    if ( this->COidJobBase::m_NdisPortNumber
      || MEMORY[0xFFFFF78000000014] - v6->m_ullLastNloDiscoverTime >= 0x989680
      || !CPropertyCache::GetPropertyBooleanOrDefault(m_pPortPropertyCache, 0x80u, 1) )
    {
      if ( (unsigned int)CPropertyCache::GetPropertyBuffer(m_pPortPropertyCache, 0x48u, &v35, &v36) != -1073741436 )
        goto LABEL_41;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_60;
      v29 = 157;
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_60;
      v29 = 156;
    }
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      v28,
      v29,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId);
LABEL_60:
    this->m_TempBSSCandidateCount = 0;
    goto LABEL_41;
  }
  if ( !v20 )
  {
    LinkQuality = this->m_TempBSSCandidateList[0]->m_SignalInfo.LinkQuality;
    if ( LinkQuality < (int)v11 + RoamControlParameters->BetterAPRoamLinkQualityThreshold )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        v34 = (char)v11;
        LOBYTE(v11) = 5;
        WPP_RECORDER_SF_qDddd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v11,
          m_LastScanType,
          158,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          m_LastScanType,
          LinkQuality,
          v34);
      }
      goto LABEL_60;
    }
  }
LABEL_41:
  m_CachedRank = this->m_TempBSSCandidateCount;
  if ( !m_CachedRank || (this->m_RoamConfigFlags & 0x100) == 0 )
    goto LABEL_19;
  if ( !v9 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v13;
    v30 = WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_19;
    v31 = 162;
    LOBYTE(v11) = 5;
LABEL_93:
    WPP_RECORDER_SF_qD(
      v30->DeviceExtension,
      (_DWORD)v11,
      m_CachedRank,
      v31,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId);
    goto LABEL_19;
  }
  LODWORD(v11) = 0;
  do
  {
    v24 = this->m_TempBSSCandidateList[(unsigned int)v11];
    v25 = *(_DWORD *)(v9 + 1) - *(_DWORD *)v24->m_BssID;
    if ( !v25 )
      v25 = *(unsigned __int16 *)(v9 + 5) - *(unsigned __int16 *)&v24->m_BssID[4];
    if ( !v25 )
      break;
    LODWORD(v11) = (_DWORD)v11 + 1;
  }
  while ( (unsigned int)v11 < m_CachedRank );
  if ( !(_DWORD)v11 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v11) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v11,
        m_CachedRank,
        159,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    this->m_TempBSSCandidateCount = 0;
    v11 = v6->m_pRoamTraceLoggingData;
    if ( v11 )
    {
      v11->curPeerRank = this->m_TempBSSCandidateList[0]->m_CachedRawRank;
      v6->m_pRoamTraceLoggingData->roamDebugCode = WdiRoamDebugCodeNoBetterAPFound;
    }
    goto LABEL_19;
  }
  if ( !v20 )
  {
    if ( (unsigned int)v11 < m_CachedRank )
    {
      _mm_lfence();
      v26 = v6->m_pRoamTraceLoggingData;
      if ( v26 )
      {
        v26->curPeerRank = this->m_TempBSSCandidateList[(unsigned int)v11]->m_CachedRawRank;
        v6->m_pRoamTraceLoggingData->bestCandidateRank = this->m_TempBSSCandidateList[0]->m_CachedRank;
      }
      LODWORD(v11) = this->m_TempBSSCandidateList[(unsigned int)v11]->m_CachedRawRank;
      m_CachedRank = this->m_TempBSSCandidateList[0]->m_CachedRank;
      if ( m_CachedRank < (int)v11 + RoamControlParameters->APLinkQualitySignificantChangeBar )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          v33 = (char)v11;
          LOBYTE(v11) = 5;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v11,
            m_CachedRank,
            160,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (char)this,
            this->m_ActivityId,
            v33,
            m_CachedRank);
        }
        this->m_TempBSSCandidateCount = 0;
        v27 = v6->m_pRoamTraceLoggingData;
        if ( v27 )
          v27->roamDebugCode = WdiRoamDebugCodeBestCandidateNotBetterEnough;
      }
      goto LABEL_19;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v13;
    v30 = WPP_GLOBAL_Control;
    v31 = 161;
    LOBYTE(v11) = 2;
    goto LABEL_93;
  }
LABEL_19:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    *(_DWORD *)v32 = v13;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      m_CachedRank,
      163,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      *(_QWORD *)v32);
  }
  return v13;
}

```

## disassembly

```asm
0x1400156a8  mov     [rsp+arg_10], rbx
0x1400156ad  push    rbp
0x1400156ae  push    rsi
0x1400156af  push    rdi
0x1400156b0  push    r12
0x1400156b2  push    r13
0x1400156b4  push    r14
0x1400156b6  push    r15
0x1400156b8  sub     rsp, 50h
0x1400156bc  mov     rsi, [rcx+220h]
0x1400156c3  xor     r13d, r13d
0x1400156c6  mov     rbx, rcx
0x1400156c9  test    rsi, rsi
0x1400156cc  jnz     short loc_1400156EE
0x1400156ce  mov     rcx, [rcx+1F0h]
0x1400156d5  movzx   edx, word ptr [rbx+34h]
0x1400156d9  mov     rax, [rcx]
0x1400156dc  mov     rax, [rax]
0x1400156df  call    _guard_dispatch_icall
0x1400156e4  mov     rsi, rax
0x1400156e7  mov     [rbx+220h], rax
0x1400156ee  mov     rcx, [rbx+200h]
0x1400156f5  add     rcx, 8
0x1400156f9  mov     rax, [rcx]
0x1400156fc  mov     rax, [rax+8]
0x140015700  call    _guard_dispatch_icall
0x140015705  mov     rcx, rax; this
0x140015708  call    ?GetRoamControlParameters@CConnectHelpers@@SAPEAU_ROAM_CONTROL_PARAMETERS@@PEAVCAdapterPropertyCache@@@Z; CConnectHelpers::GetRoamControlParameters(CAdapterPropertyCache *)
0x14001570d  mov     r9, [rbx+200h]
0x140015714  mov     r12, rax
0x140015717  movzx   r8d, word ptr [rbx+34h]
0x14001571c  mov     edx, r13d
0x14001571f  cmp     edx, 5
0x140015722  jnb     loc_140015B43
0x140015728  mov     ecx, edx
0x14001572a  mov     rdi, [r9+rcx*8+1318h]
0x140015732  test    rdi, rdi
0x140015735  jz      loc_14001584F
0x14001573b  cmp     [rdi+64h], r8w
0x140015740  jnz     loc_14001584F
0x140015746  mov     rcx, [rdi+398h]
0x14001574d  mov     edx, 3
0x140015752  mov     rax, [rcx]
0x140015755  mov     rax, [rax+18h]
0x140015759  call    _guard_dispatch_icall
0x14001575e  mov     r15, rax
0x140015761  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140015768  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001576f  lea     rbp, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140015776  jz      short loc_140015794
0x140015778  mov     rcx, cs:WPP_GLOBAL_Control
0x14001577f  cmp     byte ptr [rcx+29h], 5
0x140015783  jnb     loc_140015C13
0x140015789  cmp     [rcx+48h], r13w
0x14001578e  jnz     loc_140015C13
0x140015794  lea     rdx, [rbx+3B8h]; struct _WFC_CONNECTION_PROFILE_PARAMETERS *
0x14001579b  mov     rcx, rbx; this
0x14001579e  call    ?PickCandidates@CConnectJob@@AEAAHPEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z; CConnectJob::PickCandidates(_WFC_CONNECTION_PROFILE_PARAMETERS *)
0x1400157a3  mov     r14d, eax
0x1400157a6  test    eax, eax
0x1400157a8  jnz     loc_1400158CF
0x1400157ae  mov     rax, [rdi+48h]
0x1400157b2  test    rax, rax
0x1400157b5  jz      short loc_1400157BA
0x1400157b7  mov     byte ptr [rax], 1
0x1400157ba  mov     eax, [rbx+26Ch]
0x1400157c0  test    eax, eax
0x1400157c2  jnz     loc_140015856
0x1400157c8  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400157cf  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400157d6  jz      short loc_1400157F4
0x1400157d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400157df  cmp     byte ptr [rcx+29h], 5
0x1400157e3  jnb     loc_140015C3A
0x1400157e9  cmp     [rcx+48h], r13w
0x1400157ee  jnz     loc_140015C3A
0x1400157f4  mov     dword ptr [rbx+250h], 1000001h
0x1400157fe  mov     rax, [rdi+48h]
0x140015802  test    rax, rax
0x140015805  jz      short loc_14001580E
0x140015807  mov     dword ptr [rax+24h], 5
0x14001580e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140015815  jz      short loc_140015833
0x140015817  mov     rcx, cs:WPP_GLOBAL_Control
0x14001581e  cmp     byte ptr [rcx+29h], 5
0x140015822  jnb     loc_140015A60
0x140015828  cmp     [rcx+48h], r13w
0x14001582d  jnz     loc_140015A60
0x140015833  mov     rbx, [rsp+88h+arg_10]
0x14001583b  mov     eax, r14d
0x14001583e  add     rsp, 50h
0x140015842  pop     r15
0x140015844  pop     r14
0x140015846  pop     r13
0x140015848  pop     r12
0x14001584a  pop     rdi
0x14001584b  pop     rsi
0x14001584c  pop     rbp
0x14001584d  retn
0x14001584f  inc     edx
0x140015851  jmp     loc_14001571F
0x140015856  lea     r11, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001585d  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140015864  jz      short loc_140015882
0x140015866  mov     rcx, cs:WPP_GLOBAL_Control
0x14001586d  cmp     byte ptr [rcx+29h], 5
0x140015871  jnb     loc_140015C61
0x140015877  cmp     [rcx+48h], r13w
0x14001587c  jnz     loc_140015C61
0x140015882  mov     r9d, [rbx+260h]
0x140015889  lea     rcx, [rbx+708h]
0x140015890  test    r9b, 10h
0x140015894  jnz     loc_140015C93
0x14001589a  mov     bpl, r13b
0x14001589d  mov     r8d, [rbx+6FCh]
0x1400158a4  test    r8d, r8d
0x1400158a7  jz      loc_140015A58
0x1400158ad  cmp     r8d, 2
0x1400158b1  jle     short loc_140015916
0x1400158b3  cmp     r8d, 4
0x1400158b7  jge     loc_140015947
0x1400158bd  cmp     [rcx], r13
0x1400158c0  mov     edx, 14h
0x1400158c5  mov     eax, r13d
0x1400158c8  cmovnz  eax, edx
0x1400158cb  mov     edx, eax
0x1400158cd  jmp     short loc_14001591B
0x1400158cf  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400158d6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400158dd  jz      loc_140015833
0x1400158e3  mov     ecx, [rbx+10h]
0x1400158e6  mov     r9d, 99h
0x1400158ec  mov     dword ptr [rsp+88h+var_50], r14d
0x1400158f1  mov     dl, 2
0x1400158f3  mov     [rsp+88h+var_58], ecx
0x1400158f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400158fe  mov     [rsp+88h+var_60], rbx
0x140015903  mov     [rsp+88h+var_68], rbp
0x140015908  mov     rcx, [rcx+40h]
0x14001590c  call    WPP_RECORDER_SF_qDD
0x140015911  jmp     loc_14001580E
0x140015916  mov     edx, 14h
0x14001591b  test    r9b, 1
0x14001591f  jnz     loc_140015B4B
0x140015925  test    bpl, bpl
0x140015928  jnz     short loc_140015947
0x14001592a  mov     rax, [rbx+278h]
0x140015931  mov     ecx, [r12]
0x140015935  add     ecx, edx
0x140015937  mov     r10d, [rax+1D4h]
0x14001593e  cmp     r10d, ecx
0x140015941  jb      loc_140015A20
0x140015947  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001594e  mov     r8d, [rbx+26Ch]
0x140015955  test    r8d, r8d
0x140015958  jz      loc_140015A14
0x14001595e  test    dword ptr [rbx+260h], 100h
0x140015968  jz      loc_140015A14
0x14001596e  test    r15, r15
0x140015971  jz      loc_140015DAA
0x140015977  mov     edx, r13d
0x14001597a  mov     ecx, [r15+1]
0x14001597e  mov     eax, edx
0x140015980  mov     r9, [rbx+rax*8+278h]
0x140015988  sub     ecx, [r9+1BCh]
0x14001598f  jnz     short loc_1400159A0
0x140015991  movzx   ecx, word ptr [r15+5]
0x140015996  movzx   eax, word ptr [r9+1C0h]
0x14001599e  sub     ecx, eax
0x1400159a0  test    ecx, ecx
0x1400159a2  jz      short loc_1400159AB
0x1400159a4  inc     edx
0x1400159a6  cmp     edx, r8d
0x1400159a9  jb      short loc_14001597A
0x1400159ab  test    edx, edx
0x1400159ad  jnz     short loc_140015A0F
0x1400159af  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400159b6  jz      short loc_1400159D4
0x1400159b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400159bf  cmp     byte ptr [rcx+29h], 5
0x1400159c3  jnb     loc_140015D17
0x1400159c9  cmp     [rcx+48h], r13w
0x1400159ce  jnz     loc_140015D17
0x1400159d4  lea     rbp, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x1400159db  mov     [rbx+26Ch], r13d
0x1400159e2  mov     rdx, [rdi+48h]
0x1400159e6  test    rdx, rdx
0x1400159e9  jz      loc_14001580E
0x1400159ef  mov     rax, [rbx+278h]
0x1400159f6  mov     ecx, [rax+254h]
0x1400159fc  mov     [rdx+38h], ecx
0x1400159ff  mov     rax, [rdi+48h]
0x140015a03  mov     dword ptr [rax+24h], 1
0x140015a0a  jmp     loc_14001580E
0x140015a0f  test    bpl, bpl
0x140015a12  jz      short loc_140015A8C
0x140015a14  lea     rbp, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140015a1b  jmp     loc_14001580E
0x140015a20  cmp     cs:WPP_RECORDER_INITIALIZED, r11; __annotation("TMF:",
0x140015a27  jz      short loc_140015A45
0x140015a29  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a30  cmp     byte ptr [rcx+29h], 5
0x140015a34  jnb     loc_140015CDB
0x140015a3a  cmp     [rcx+48h], r13w
0x140015a3f  jnz     loc_140015CDB
0x140015a45  lea     rsi, WPP_RECORDER_INITIALIZED
0x140015a4c  mov     [rbx+26Ch], r13d
0x140015a53  jmp     loc_14001594E
0x140015a58  mov     edx, r13d
0x140015a5b  jmp     loc_14001591B
0x140015a60  mov     eax, [rbx+10h]
0x140015a63  mov     r9d, 0A3h
0x140015a69  mov     rcx, [rcx+40h]
0x140015a6d  mov     dl, 5
0x140015a6f  mov     dword ptr [rsp+88h+var_50], r14d
0x140015a74  mov     [rsp+88h+var_58], eax
0x140015a78  mov     [rsp+88h+var_60], rbx
0x140015a7d  mov     [rsp+88h+var_68], rbp
0x140015a82  call    WPP_RECORDER_SF_qDD
0x140015a87  jmp     loc_140015833
0x140015a8c  cmp     edx, r8d
0x140015a8f  jnb     loc_140015BF2
0x140015a95  lfence
0x140015a98  mov     r8, [rdi+48h]
0x140015a9c  test    r8, r8
0x140015a9f  jz      short loc_140015AC9
0x140015aa1  mov     eax, edx
0x140015aa3  mov     rcx, [rbx+rax*8+278h]
0x140015aab  mov     eax, [rcx+254h]
0x140015ab1  mov     [r8+38h], eax
0x140015ab5  mov     rax, [rbx+278h]
0x140015abc  mov     rcx, [rdi+48h]
0x140015ac0  mov     eax, [rax+250h]
0x140015ac6  mov     [rcx+3Ch], eax
0x140015ac9  mov     eax, edx
0x140015acb  mov     rcx, [rbx+rax*8+278h]
0x140015ad3  mov     rax, [rbx+278h]
0x140015ada  mov     edx, [rcx+254h]
0x140015ae0  mov     ecx, [r12+0Ch]
0x140015ae5  mov     r8d, [rax+250h]
0x140015aec  add     ecx, edx
0x140015aee  cmp     r8d, ecx
0x140015af1  jnb     loc_140015A14
0x140015af7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140015afe  jz      short loc_140015B1C
0x140015b00  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b07  cmp     byte ptr [rcx+29h], 5
0x140015b0b  jnb     loc_140015D45
0x140015b11  cmp     [rcx+48h], r13w
0x140015b16  jnz     loc_140015D45
0x140015b1c  lea     rbp, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140015b23  mov     [rbx+26Ch], r13d
0x140015b2a  mov     rax, [rdi+48h]
0x140015b2e  test    rax, rax
0x140015b31  jz      loc_14001580E
0x140015b37  mov     dword ptr [rax+24h], 2
0x140015b3e  jmp     loc_14001580E
0x140015b43  mov     rdi, r13
0x140015b46  jmp     loc_140015746
0x140015b4b  mov     rax, 0FFFFF78000000014h
0x140015b55  mov     [rsp+88h+arg_8], r13
0x140015b5d  mov     [rsp+88h+arg_0], r13d
0x140015b65  mov     rax, [rax]
0x140015b68  cmp     [rbx+218h], r13d
0x140015b6f  jnz     short loc_140015B81
0x140015b71  sub     rax, [rdi+20h]
0x140015b75  cmp     rax, 989680h
0x140015b7b  jb      loc_140015CA4
0x140015b81  lea     r9, [rsp+88h+arg_8]; unsigned __int8 **
0x140015b89  mov     edx, 48h ; 'H'; unsigned int
0x140015b8e  lea     r8, [rsp+88h+arg_0]; unsigned int *
0x140015b96  mov     rcx, rsi; this
0x140015b99  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x140015b9e  cmp     eax, 0C0000184h
0x140015ba3  jnz     loc_140015947
0x140015ba9  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140015bb0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140015bb7  jz      loc_140015A4C
0x140015bbd  mov     r9d, 9Dh
0x140015bc3  mov     eax, [rbx+10h]
0x140015bc6  mov     dl, 4
0x140015bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140015bcf  mov     [rsp+88h+var_58], eax
0x140015bd3  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140015bda  mov     [rsp+88h+var_60], rbx
0x140015bdf  mov     [rsp+88h+var_68], rax
0x140015be4  mov     rcx, [rcx+40h]
0x140015be8  call    WPP_RECORDER_SF_qD
0x140015bed  jmp     loc_140015A4C
0x140015bf2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140015bf9  jz      loc_140015833
0x140015bff  mov     rcx, cs:WPP_GLOBAL_Control
0x140015c06  mov     r9d, 0A1h
0x140015c0c  mov     dl, 2
0x140015c0e  jmp     loc_140015D84
0x140015c13  mov     eax, [rbx+10h]
0x140015c16  mov     r9d, 98h
0x140015c1c  mov     rcx, [rcx+40h]
0x140015c20  mov     dl, 5
0x140015c22  mov     [rsp+88h+var_58], eax
  ... truncated ...
```
