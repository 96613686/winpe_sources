# CCreateMacOidJob::OnJobStepCompleted(int,void *)

- ea: `0x140046030`
- end: `0x1400464c9`
- name: `?OnJobStepCompleted@CCreateMacOidJob@@UEAAXHPEAX@Z`
- size: `1177`
- prototype: `void __fastcall(CCreateMacOidJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004c3c`
- `0x1400100f8`
- `0x1400122e0`
- `0x14002aa28`
- `0x14002c5d8`
- `0x14002e878`
- `0x14002eb94`
- `0x140030d54`
- `0x140034e04`
- `0x140046030`
- `0x1400464d0`
- `0x1400aa910`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400461bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400461bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004610e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004610e`
- `NDIS!NdisMFreePort` at `0x140046363`
- `NDIS!NdisMFreePort` at `0x140046363`

## pseudocode

```c
void __fastcall CCreateMacOidJob::OnJobStepCompleted(CCreateMacOidJob *this, int a2, _DWORD *InformationBuffer)
{
  int v3; // esi
  CNdisSpinLock *m_ISpinLockDelayActivation; // rbx
  CAdapter *m_pAdapter; // rdx
  __int64 v7; // rcx
  CAdapter *v8; // rcx
  CNdisSpinLock *v9; // rcx
  KIRQL OldIrql; // dl
  int v11; // ebx
  struct CPort *PortFromNdisPortNumber; // rsi
  CAdapter *v13; // rcx
  struct CPort *v14; // rbp
  int v15; // edx
  int v16; // r8d
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  _NDIS_OID_REQUEST *m_pOidRequest; // rdx
  __int16 v21; // cx
  NDIS_STATUS v22; // eax
  int v23; // edx
  int v24; // eax
  int v25; // edx
  int v26; // edx
  int v27; // [rsp+20h] [rbp-68h]
  __int64 v28; // [rsp+38h] [rbp-50h]

  v3 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)InformationBuffer,
      218,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  if ( this->m_CreatePortOidState != CreatePortOidStateWaitingForCreatePortChildJob )
  {
    if ( this->m_CreatePortOidState == CreatePortOidStateWaitingForWorkItemCallback )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (_DWORD)InformationBuffer,
          225,
          (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
          (char)this,
          this->m_ActivityId,
          v3);
      }
      if ( !v3 )
      {
        if ( !this->m_pPortToRecreate )
        {
          m_ISpinLockDelayActivation = this->m_pAdapter->m_ISpinLockDelayActivation;
          m_ISpinLockDelayActivation->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_ISpinLockDelayActivation->m_SpinLock.SpinLock);
          m_ISpinLockDelayActivation->m_IsLocked = 1;
          m_pAdapter = this->m_pAdapter;
          v7 = 0;
          do
          {
            if ( !m_pAdapter->m_NdisPortNumToActivate[v7] )
            {
              m_pAdapter->m_NdisPortNumToActivate[v7] = this->m_CreatedNdisPortNumber;
              goto LABEL_18;
            }
            v7 = (unsigned int)(v7 + 1);
          }
          while ( (int)v7 < 5 );
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(m_pAdapter) = 2;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)m_pAdapter,
              1,
              226,
              (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
          }
LABEL_18:
          v8 = this->m_pAdapter;
          if ( !v8->m_bActivateWorkerActive )
          {
            v8->m_pWorkItemActivatePort->QueueWorkItem(v8->m_pWorkItemActivatePort);
            this->m_pAdapter->m_bActivateWorkerActive = 1;
          }
          v9 = this->m_pAdapter->m_ISpinLockDelayActivation;
          OldIrql = v9->m_SpinLock.OldIrql;
          v9->m_IsLocked = 0;
          KeReleaseSpinLock(&v9->m_SpinLock.SpinLock, OldIrql);
        }
        goto LABEL_49;
      }
    }
    else
    {
      v3 = 65537;
    }
    goto LABEL_47;
  }
  v11 = v3;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)InformationBuffer,
      219,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  if ( v3 )
    goto LABEL_31;
  PortFromNdisPortNumber = CAdapter::GetPortFromNdisPortNumber(this->m_pAdapter, this->m_CreatedNdisPortNumber);
  v14 = CAdapter::GetPortFromNdisPortNumber(v13, 0);
  CPropertyCache::SetPropertyULong(
    &PortFromNdisPortNumber->m_PortPropertyCache,
    0x50u,
    this->m_Dot11MacParamsOpmodeMask);
  if ( this->m_CreatedNdisPortNumber && (v14->m_State & 0x43) != 0 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        v16,
        220,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    goto LABEL_32;
  }
  v17 = CPort::Restart(PortFromNdisPortNumber);
  v3 = v17;
  if ( !v17 )
  {
LABEL_31:
    if ( !v11 )
    {
LABEL_32:
      m_pOidRequest = this->m_pOidRequest;
      InformationBuffer = m_pOidRequest->DATA.QUERY_INFORMATION.InformationBuffer;
      InformationBuffer[1] = this->m_CreatedNdisPortNumber;
      v21 = *(_WORD *)&this->m_CreatePortChildJob.m_CreatePortIndicationParameters.PortAttributes.MacAddress.Address[4];
      InformationBuffer[2] = *(_DWORD *)this->m_CreatePortChildJob.m_CreatePortIndicationParameters.PortAttributes.MacAddress.Address;
      *((_WORD *)InformationBuffer + 6) = v21;
      m_pOidRequest->DATA.METHOD_INFORMATION.BytesWritten = 16;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qDD_MAC_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)m_pOidRequest,
          (_DWORD)InformationBuffer,
          (_DWORD)InformationBuffer + 8,
          v27,
          (char)this,
          this->m_ActivityId,
          InformationBuffer[1],
          (__int64)(InformationBuffer + 2),
          16);
      v3 = v11;
      goto LABEL_40;
    }
    v3 = v11;
  }
  else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      v19,
      221,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v17);
  }
  v22 = NdisMFreePort(this->m_pAdapter->m_MiniportAdapterHandle, this->m_CreatedNdisPortNumber);
  if ( v22 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v28) = v22;
    LOBYTE(v23) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      (_DWORD)InformationBuffer,
      223,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v28);
  }
  this->m_CreatedNdisPortNumber = -1;
LABEL_40:
  this->m_OidIsCompleted = 1;
  if ( !this->m_pPortToRecreate )
    CAdapter::CompleteOidRequest(this->m_pAdapter, this->m_pOidRequest, v3);
  if ( v3 )
    goto LABEL_47;
  v24 = EventQueue::DeferToWorkItem(this->m_pEventQueue, this, &this->m_AsyncCallbackEvent);
  v3 = v24;
  if ( v24 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v28) = v24;
      LOBYTE(v25) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        (_DWORD)InformationBuffer,
        224,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v28);
    }
    goto LABEL_47;
  }
  v3 = CJobBase::SetPending(this);
  this->m_CreatePortOidState = CreatePortOidStateWaitingForWorkItemCallback;
  if ( v3 )
  {
LABEL_47:
    if ( !this->m_OidIsCompleted )
    {
      CAdapter::CompleteOidRequest(this->m_pAdapter, this->m_pOidRequest, v3);
      this->m_OidIsCompleted = 1;
    }
LABEL_49:
    CJobBase::CompleteJob(this, v3, (int)InformationBuffer);
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v26) = 5;
    LODWORD(v28) = v3;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v26,
      (_DWORD)InformationBuffer,
      227,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v28);
  }
}

```

## disassembly

```asm
0x140046030  push    rbx
0x140046032  push    rbp
0x140046033  push    rsi
0x140046034  push    rdi
0x140046035  push    r12
0x140046037  push    r14
0x140046039  push    r15
0x14004603b  sub     rsp, 50h
0x14004603f  mov     esi, edx
0x140046041  mov     rdi, rcx
0x140046044  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004604b  xor     r14d, r14d
0x14004604e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140046055  lea     r12, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x14004605c  jz      short loc_140046094
0x14004605e  mov     rcx, cs:WPP_GLOBAL_Control
0x140046065  cmp     byte ptr [rcx+29h], 5
0x140046069  jnb     short loc_140046072
0x14004606b  cmp     [rcx+48h], r14w
0x140046070  jz      short loc_140046094
0x140046072  mov     eax, [rdi+10h]
0x140046075  mov     r9d, 0DAh
0x14004607b  mov     rcx, [rcx+40h]
0x14004607f  mov     dl, 5
0x140046081  mov     [rsp+88h+var_58], eax
0x140046085  mov     [rsp+88h+var_60], rdi
0x14004608a  mov     [rsp+88h+var_68], r12
0x14004608f  call    WPP_RECORDER_SF_qD
0x140046094  mov     ecx, [rdi+130Ch]
0x14004609a  sub     ecx, 1
0x14004609d  jz      loc_1400461CE
0x1400460a3  cmp     ecx, 1
0x1400460a6  jz      short loc_1400460B2
0x1400460a8  mov     esi, 10001h
0x1400460ad  jmp     loc_140046446
0x1400460b2  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400460b9  jz      short loc_1400460E8
0x1400460bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400460c2  mov     r9d, 0E1h
0x1400460c8  mov     eax, [rdi+10h]
0x1400460cb  mov     dl, 4
0x1400460cd  mov     dword ptr [rsp+88h+var_50], esi
0x1400460d1  mov     [rsp+88h+var_58], eax
0x1400460d5  mov     rcx, [rcx+40h]
0x1400460d9  mov     [rsp+88h+var_60], rdi
0x1400460de  mov     [rsp+88h+var_68], r12
0x1400460e3  call    WPP_RECORDER_SF_qDD
0x1400460e8  test    esi, esi
0x1400460ea  jnz     loc_140046446
0x1400460f0  cmp     [rdi+1318h], r14
0x1400460f7  jnz     loc_14004646C
0x1400460fd  mov     rax, [rdi+200h]
0x140046104  mov     rbx, [rax+3FB0h]
0x14004610b  mov     rcx, rbx; SpinLock
0x14004610e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140046115  nop     dword ptr [rax+rax+00h]
0x14004611a  mov     [rbx+8], al
0x14004611d  mov     byte ptr [rbx+10h], 1
0x140046121  mov     rdx, [rdi+200h]
0x140046128  mov     ecx, r14d
0x14004612b  cmp     [rdx+rcx*4+3FCCh], r14d
0x140046133  jz      short loc_14004616A
0x140046135  inc     ecx
0x140046137  cmp     ecx, 5
0x14004613a  jl      short loc_14004612B
0x14004613c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140046143  jz      short loc_140046177
0x140046145  mov     rcx, cs:WPP_GLOBAL_Control
0x14004614c  mov     r9d, 0E2h
0x140046152  mov     r8d, 1
0x140046158  mov     [rsp+88h+var_68], r12
0x14004615d  mov     dl, 2
0x14004615f  mov     rcx, [rcx+40h]
0x140046163  call    WPP_RECORDER_SF_
0x140046168  jmp     short loc_140046177
0x14004616a  mov     eax, [rdi+1310h]
0x140046170  mov     [rdx+rcx*4+3FCCh], eax
0x140046177  mov     rcx, [rdi+200h]
0x14004617e  cmp     [rcx+3FF1h], r14b
0x140046185  jnz     short loc_1400461A8
0x140046187  mov     rcx, [rcx+3FE8h]
0x14004618e  mov     rax, [rcx]
0x140046191  mov     rax, [rax+10h]
0x140046195  call    _guard_dispatch_icall
0x14004619a  mov     rax, [rdi+200h]
0x1400461a1  mov     byte ptr [rax+3FF1h], 1
0x1400461a8  mov     rax, [rdi+200h]
0x1400461af  mov     rcx, [rax+3FB0h]; SpinLock
0x1400461b6  mov     dl, [rcx+8]; NewIrql
0x1400461b9  mov     [rcx+10h], r14b
0x1400461bd  call    cs:__imp_KeReleaseSpinLock
0x1400461c4  nop     dword ptr [rax+rax+00h]
0x1400461c9  jmp     loc_14004646C
0x1400461ce  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400461d5  mov     ebx, esi
0x1400461d7  jz      short loc_140046206
0x1400461d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400461e0  mov     r9d, 0DBh
0x1400461e6  mov     eax, [rdi+10h]
0x1400461e9  mov     dl, 4
0x1400461eb  mov     dword ptr [rsp+88h+var_50], esi
0x1400461ef  mov     [rsp+88h+var_58], eax
0x1400461f3  mov     rcx, [rcx+40h]
0x1400461f7  mov     [rsp+88h+var_60], rdi
0x1400461fc  mov     [rsp+88h+var_68], r12
0x140046201  call    WPP_RECORDER_SF_qDD
0x140046206  test    esi, esi
0x140046208  jnz     loc_1400462DC
0x14004620e  mov     rcx, [rdi+200h]; this
0x140046215  mov     edx, [rdi+1310h]; unsigned int
0x14004621b  call    ?GetPortFromNdisPortNumber@CAdapter@@QEAAPEAVCPort@@K@Z; CAdapter::GetPortFromNdisPortNumber(ulong)
0x140046220  xor     edx, edx; unsigned int
0x140046222  mov     rsi, rax
0x140046225  call    ?GetPortFromNdisPortNumber@CAdapter@@QEAAPEAVCPort@@K@Z; CAdapter::GetPortFromNdisPortNumber(ulong)
0x14004622a  mov     r8d, [rdi+1308h]; unsigned int
0x140046231  lea     rcx, [rsi+3A8h]; this
0x140046238  mov     edx, 50h ; 'P'; unsigned int
0x14004623d  mov     rbp, rax
0x140046240  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x140046245  mov     eax, [rdi+1310h]
0x14004624b  test    eax, eax
0x14004624d  jz      short loc_140046292
0x14004624f  mov     ecx, [rbp+368h]
0x140046255  test    cl, 43h
0x140046258  jz      short loc_140046292
0x14004625a  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140046261  jz      short loc_1400462E0
0x140046263  mov     rcx, cs:WPP_GLOBAL_Control
0x14004626a  mov     r9d, 0DCh
0x140046270  mov     dword ptr [rsp+88h+var_50], eax
0x140046274  mov     dl, 4
0x140046276  mov     eax, [rdi+10h]
0x140046279  mov     [rsp+88h+var_58], eax
0x14004627d  mov     rcx, [rcx+40h]
0x140046281  mov     [rsp+88h+var_60], rdi
0x140046286  mov     [rsp+88h+var_68], r12
0x14004628b  call    WPP_RECORDER_SF_qDD
0x140046290  jmp     short loc_1400462E0
0x140046292  mov     rcx, rsi; this
0x140046295  call    ?Restart@CPort@@QEAAHXZ; CPort::Restart(void)
0x14004629a  mov     esi, eax
0x14004629c  test    eax, eax
0x14004629e  jz      short loc_1400462DC
0x1400462a0  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400462a7  jz      loc_140046352
0x1400462ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400462b4  mov     r9d, 0DDh
0x1400462ba  mov     dword ptr [rsp+88h+var_50], eax
0x1400462be  mov     dl, 2
0x1400462c0  mov     eax, [rdi+10h]
0x1400462c3  mov     [rsp+88h+var_58], eax
0x1400462c7  mov     rcx, [rcx+40h]
0x1400462cb  mov     [rsp+88h+var_60], rdi
0x1400462d0  mov     [rsp+88h+var_68], r12
0x1400462d5  call    WPP_RECORDER_SF_qDD
0x1400462da  jmp     short loc_140046352
0x1400462dc  test    ebx, ebx
0x1400462de  jnz     short loc_140046350
0x1400462e0  mov     rdx, [rdi+210h]
0x1400462e7  mov     eax, [rdi+1310h]
0x1400462ed  mov     r8, [rdx+28h]
0x1400462f1  mov     [r8+4], eax
0x1400462f5  lea     r9, [r8+8]
0x1400462f9  mov     eax, [rdi+12B4h]
0x1400462ff  movzx   ecx, word ptr [rdi+12B8h]
0x140046306  mov     [r9], eax
0x140046309  mov     eax, 10h
0x14004630e  mov     [r9+4], cx
0x140046313  mov     [rdx+3Ch], eax
0x140046316  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004631d  jz      short loc_14004634C
0x14004631f  mov     rcx, cs:WPP_GLOBAL_Control
0x140046326  mov     [rsp+88h+var_40], eax
0x14004632a  mov     eax, [r8+4]
0x14004632e  mov     [rsp+88h+var_48], r9
0x140046333  mov     rcx, [rcx+40h]
0x140046337  mov     dword ptr [rsp+88h+var_50], eax
0x14004633b  mov     eax, [rdi+10h]
0x14004633e  mov     [rsp+88h+var_58], eax
0x140046342  mov     [rsp+88h+var_60], rdi
0x140046347  call    WPP_RECORDER_SF_qDD_MAC_d
0x14004634c  mov     esi, ebx
0x14004634e  jmp     short loc_1400463B3
0x140046350  mov     esi, ebx
0x140046352  mov     rcx, [rdi+200h]
0x140046359  mov     edx, [rdi+1310h]; PortNumber
0x14004635f  mov     rcx, [rcx+58h]; NdisMiniportHandle
0x140046363  call    cs:__imp_NdisMFreePort
0x14004636a  nop     dword ptr [rax+rax+00h]
0x14004636f  test    eax, eax
0x140046371  jz      short loc_1400463A9
0x140046373  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004637a  jz      short loc_1400463A9
0x14004637c  mov     rcx, cs:WPP_GLOBAL_Control
0x140046383  mov     r9d, 0DFh
0x140046389  mov     dword ptr [rsp+88h+var_50], eax
0x14004638d  mov     dl, 2
0x14004638f  mov     eax, [rdi+10h]
0x140046392  mov     [rsp+88h+var_58], eax
0x140046396  mov     rcx, [rcx+40h]
0x14004639a  mov     [rsp+88h+var_60], rdi
0x14004639f  mov     [rsp+88h+var_68], r12
0x1400463a4  call    WPP_RECORDER_SF_qDD
0x1400463a9  mov     dword ptr [rdi+1310h], 0FFFFFFFFh
0x1400463b3  mov     byte ptr [rdi+1314h], 1
0x1400463ba  cmp     [rdi+1318h], r14
0x1400463c1  jnz     short loc_1400463D9
0x1400463c3  mov     rdx, [rdi+210h]; struct _NDIS_OID_REQUEST *
0x1400463ca  mov     r8d, esi; int
0x1400463cd  mov     rcx, [rdi+200h]; this
0x1400463d4  call    ?CompleteOidRequest@CAdapter@@QEAAXPEAU_NDIS_OID_REQUEST@@H@Z; CAdapter::CompleteOidRequest(_NDIS_OID_REQUEST *,int)
0x1400463d9  test    esi, esi
0x1400463db  jnz     short loc_140046446
0x1400463dd  mov     rcx, [rdi+20h]; this
0x1400463e1  lea     r8, [rdi+12C0h]; struct Event *
0x1400463e8  mov     rdx, rdi; struct IOperationCompletionCallback *
0x1400463eb  call    ?DeferToWorkItem@EventQueue@@QEAAHPEAVIOperationCompletionCallback@@PEAVEvent@@@Z; EventQueue::DeferToWorkItem(IOperationCompletionCallback *,Event *)
0x1400463f0  mov     esi, eax
0x1400463f2  test    eax, eax
0x1400463f4  jz      short loc_14004642E
0x1400463f6  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400463fd  jz      short loc_140046446
0x1400463ff  mov     ecx, [rdi+10h]
0x140046402  mov     r9d, 0E0h
0x140046408  mov     dword ptr [rsp+88h+var_50], eax
0x14004640c  mov     dl, 2
0x14004640e  mov     [rsp+88h+var_58], ecx
0x140046412  mov     rcx, cs:WPP_GLOBAL_Control
0x140046419  mov     [rsp+88h+var_60], rdi
0x14004641e  mov     [rsp+88h+var_68], r12
0x140046423  mov     rcx, [rcx+40h]
0x140046427  call    WPP_RECORDER_SF_qDD
0x14004642c  jmp     short loc_140046446
0x14004642e  mov     rcx, rdi; this
0x140046431  call    ?SetPending@CJobBase@@IEAAHXZ; CJobBase::SetPending(void)
0x140046436  mov     esi, eax
0x140046438  mov     dword ptr [rdi+130Ch], 2
0x140046442  test    eax, eax
0x140046444  jz      short loc_140046476
0x140046446  cmp     [rdi+1314h], r14b
0x14004644d  jnz     short loc_14004646C
0x14004644f  mov     rdx, [rdi+210h]; struct _NDIS_OID_REQUEST *
0x140046456  mov     r8d, esi; int
0x140046459  mov     rcx, [rdi+200h]; this
0x140046460  call    ?CompleteOidRequest@CAdapter@@QEAAXPEAU_NDIS_OID_REQUEST@@H@Z; CAdapter::CompleteOidRequest(_NDIS_OID_REQUEST *,int)
0x140046465  mov     byte ptr [rdi+1314h], 1
0x14004646c  mov     edx, esi; int
0x14004646e  mov     rcx, rdi; this
0x140046471  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x140046476  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004647d  jz      short loc_1400464B9
0x14004647f  mov     rcx, cs:WPP_GLOBAL_Control
0x140046486  cmp     byte ptr [rcx+29h], 5
0x14004648a  jnb     short loc_140046493
0x14004648c  cmp     [rcx+48h], r14w
0x140046491  jz      short loc_1400464B9
0x140046493  mov     eax, [rdi+10h]
0x140046496  mov     r9d, 0E3h
0x14004649c  mov     rcx, [rcx+40h]
0x1400464a0  mov     dl, 5
0x1400464a2  mov     dword ptr [rsp+88h+var_50], esi
0x1400464a6  mov     [rsp+88h+var_58], eax
0x1400464aa  mov     [rsp+88h+var_60], rdi
0x1400464af  mov     [rsp+88h+var_68], r12
0x1400464b4  call    WPP_RECORDER_SF_qDD
0x1400464b9  add     rsp, 50h
0x1400464bd  pop     r15
0x1400464bf  pop     r14
0x1400464c1  pop     r12
0x1400464c3  pop     rdi
0x1400464c4  pop     rsi
0x1400464c5  pop     rbp
0x1400464c6  pop     rbx
0x1400464c7  retn
```
