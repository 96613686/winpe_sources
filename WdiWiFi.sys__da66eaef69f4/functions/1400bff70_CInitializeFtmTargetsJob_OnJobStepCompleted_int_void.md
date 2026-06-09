# CInitializeFtmTargetsJob::OnJobStepCompleted(int,void *)

- ea: `0x1400bff70`
- end: `0x1400c02be`
- name: `?OnJobStepCompleted@CInitializeFtmTargetsJob@@UEAAXHPEAX@Z`
- size: `846`
- prototype: `void __fastcall(CInitializeFtmTargetsJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140004c3c`
- `0x140010730`
- `0x1400122e0`
- `0x140021848`
- `0x140023ae0`
- `0x14002aa28`
- `0x1400beae8`
- `0x1400bf49c`
- `0x1400bff70`
- `0x1400c0808`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400c00a1`
- `ntoskrnl!ExAllocatePool2` at `0x1400c00a1`

## pseudocode

```c
void __fastcall CInitializeFtmTargetsJob::OnJobStepCompleted(CInitializeFtmTargetsJob *this, int a2, void *a3)
{
  int v3; // edi
  int v5; // r9d
  CChannelListManager *Pool2; // rax
  struct CChannelListManager *v7; // rax
  struct CChannelListManager *v8; // rsi
  int v9; // edx
  int v10; // r8d
  CScanJob *m_pScanJob; // rcx
  int started; // eax
  int v13; // edx
  int v14; // r8d
  __int64 v15; // [rsp+38h] [rbp-40h]

  v3 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      71,
      (__int64)WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  if ( this->m_IsCancelled )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        72,
        (__int64)WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids,
        (char)this,
        this->m_ActivityId,
        this->m_JobState);
    }
    v3 = -1073676276;
    goto LABEL_40;
  }
  if ( this->m_JobState != PrepareFtmTargetsJobStateWaitingForListUpdateJobCompletion )
  {
    if ( this->m_JobState != PrepareFtmTargetsJobStateWaitingForScanJobCompletion )
      goto LABEL_40;
    if ( v3 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v5 = 77;
LABEL_17:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        v5,
        (__int64)WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids,
        (char)this,
        this->m_ActivityId,
        v3);
      goto LABEL_40;
    }
    goto LABEL_23;
  }
  if ( v3 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_40;
    v5 = 73;
    goto LABEL_17;
  }
  Pool2 = (CChannelListManager *)ExAllocatePool2(64, 2692, 1198089303);
  if ( Pool2 && (v7 = CChannelListManager::CChannelListManager(Pool2), (v8 = v7) != 0) )
  {
    CInitializeFtmTargetsJob::GetChannelListForFtmScan(this, v7);
    if ( !v8->m_ChannelList24GHzCount && !v8->m_ChannelList5GHzCount )
    {
      operator delete(v8);
LABEL_23:
      m_pScanJob = this->m_pScanJob;
      if ( m_pScanJob )
      {
        ((void (__fastcall *)(CScanJob *, __int64, void *))m_pScanJob->~CScanJob)(m_pScanJob, 1, a3);
        this->m_pScanJob = 0;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (_DWORD)a3,
          78,
          (__int64)WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids,
          (char)this,
          this->m_ActivityId);
      }
      v3 = CInitializeFtmTargetsJob::InitializeTargets(this);
      if ( v3 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            (_DWORD)a3,
            79,
            (__int64)WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids,
            (char)this,
            this->m_ActivityId);
        }
      }
      else
      {
        this->m_JobState = PrepareFtmTargetsJobStateComplete;
      }
      goto LABEL_40;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v10,
        75,
        (__int64)WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    started = CInitializeFtmTargetsJob::StartScanJob(this, v8);
    v3 = started;
    if ( started && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        76,
        (__int64)WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids,
        (char)this,
        this->m_ActivityId,
        started);
    }
    operator delete(v8);
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        74,
        (__int64)WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    v3 = -1073741670;
  }
LABEL_40:
  if ( this->m_JobState == PrepareFtmTargetsJobStateComplete || v3 )
    CJobBase::CompleteJob(this, v3, (int)a3);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v15) = v3;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      80,
      (__int64)WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids,
      (char)this,
      this->m_ActivityId,
      v15);
  }
}

```

## disassembly

```asm
0x1400bff70  push    rbx
0x1400bff72  push    rbp
0x1400bff73  push    rsi
0x1400bff74  push    rdi
0x1400bff75  push    r14
0x1400bff77  push    r15
0x1400bff79  sub     rsp, 48h
0x1400bff7d  mov     edi, edx
0x1400bff7f  mov     rbx, rcx
0x1400bff82  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400bff89  xor     ebp, ebp
0x1400bff8b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bff92  lea     r15, WPP_b47de703a3333e382a4d60368ddb6ca8_Traceguids
0x1400bff99  jz      short loc_1400BFFD0
0x1400bff9b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bffa2  cmp     byte ptr [rcx+29h], 5
0x1400bffa6  jnb     short loc_1400BFFAE
0x1400bffa8  cmp     [rcx+48h], bp
0x1400bffac  jz      short loc_1400BFFD0
0x1400bffae  mov     eax, [rbx+10h]
0x1400bffb1  mov     r9d, 47h ; 'G'
0x1400bffb7  mov     rcx, [rcx+40h]
0x1400bffbb  mov     dl, 5
0x1400bffbd  mov     [rsp+78h+var_48], eax
0x1400bffc1  mov     [rsp+78h+var_50], rbx
0x1400bffc6  mov     [rsp+78h+var_58], r15
0x1400bffcb  call    WPP_RECORDER_SF_qD
0x1400bffd0  cmp     [rbx+238h], bpl
0x1400bffd7  jz      short loc_1400C001F
0x1400bffd9  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400bffe0  jz      short loc_1400C0015
0x1400bffe2  mov     eax, [rbx+200h]
0x1400bffe8  mov     r9d, 48h ; 'H'
0x1400bffee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfff5  mov     dl, 4
0x1400bfff7  mov     dword ptr [rsp+78h+var_40], eax
0x1400bfffb  mov     eax, [rbx+10h]
0x1400bfffe  mov     [rsp+78h+var_48], eax
0x1400c0002  mov     rcx, [rcx+40h]
0x1400c0006  mov     [rsp+78h+var_50], rbx
0x1400c000b  mov     [rsp+78h+var_58], r15
0x1400c0010  call    WPP_RECORDER_SF_qDL
0x1400c0015  mov     edi, 0C001000Ch
0x1400c001a  jmp     loc_1400C0257
0x1400c001f  mov     ecx, [rbx+200h]
0x1400c0025  sub     ecx, 1
0x1400c0028  jz      short loc_1400C004E
0x1400c002a  cmp     ecx, 1
0x1400c002d  jnz     loc_1400C0257
0x1400c0033  test    edi, edi
0x1400c0035  jz      loc_1400C00EF
0x1400c003b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400c0042  jz      loc_1400C0257
0x1400c0048  lea     r9d, [rcx+4Ch]
0x1400c004c  jmp     short loc_1400C0065
0x1400c004e  test    edi, edi
0x1400c0050  jz      short loc_1400C0091
0x1400c0052  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400c0059  jz      loc_1400C0257
0x1400c005f  mov     r9d, 49h ; 'I'
0x1400c0065  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c006c  mov     dl, 2
0x1400c006e  mov     eax, [rbx+10h]
0x1400c0071  mov     dword ptr [rsp+78h+var_40], edi
0x1400c0075  mov     [rsp+78h+var_48], eax
0x1400c0079  mov     rcx, [rcx+40h]
0x1400c007d  mov     [rsp+78h+var_50], rbx
0x1400c0082  mov     [rsp+78h+var_58], r15
0x1400c0087  call    WPP_RECORDER_SF_qDL
0x1400c008c  jmp     loc_1400C0257
0x1400c0091  mov     edx, 0A84h
0x1400c0096  mov     ecx, 40h ; '@'
0x1400c009b  mov     r8d, 47696457h
0x1400c00a1  call    cs:__imp_ExAllocatePool2
0x1400c00a8  nop     dword ptr [rax+rax+00h]
0x1400c00ad  test    rax, rax
0x1400c00b0  jz      loc_1400C0220
0x1400c00b6  mov     rcx, rax; this
0x1400c00b9  call    ??0CChannelListManager@@QEAA@XZ; CChannelListManager::CChannelListManager(void)
0x1400c00be  mov     rsi, rax
0x1400c00c1  test    rax, rax
0x1400c00c4  jz      loc_1400C0220
0x1400c00ca  mov     rdx, rax; struct CChannelListManager *
0x1400c00cd  mov     rcx, rbx; this
0x1400c00d0  call    ?GetChannelListForFtmScan@CInitializeFtmTargetsJob@@AEAAXPEAVCChannelListManager@@@Z; CInitializeFtmTargetsJob::GetChannelListForFtmScan(CChannelListManager *)
0x1400c00d5  cmp     [rsi+28h], ebp
0x1400c00d8  jnz     loc_1400C019D
0x1400c00de  cmp     [rsi+54h], ebp
0x1400c00e1  jnz     loc_1400C019D
0x1400c00e7  mov     rcx, rsi; void *
0x1400c00ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c00ef  mov     rcx, [rbx+538h]
0x1400c00f6  test    rcx, rcx
0x1400c00f9  jz      short loc_1400C0113
0x1400c00fb  mov     rax, [rcx]
0x1400c00fe  mov     edx, 1
0x1400c0103  mov     rax, [rax+28h]
0x1400c0107  call    _guard_dispatch_icall
0x1400c010c  mov     [rbx+538h], rbp
0x1400c0113  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400c011a  jz      short loc_1400C0145
0x1400c011c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0123  mov     r9d, 4Eh ; 'N'
0x1400c0129  mov     eax, [rbx+10h]
0x1400c012c  mov     dl, 4
0x1400c012e  mov     [rsp+78h+var_48], eax
0x1400c0132  mov     [rsp+78h+var_50], rbx
0x1400c0137  mov     rcx, [rcx+40h]
0x1400c013b  mov     [rsp+78h+var_58], r15
0x1400c0140  call    WPP_RECORDER_SF_qD
0x1400c0145  mov     rcx, rbx; this
0x1400c0148  call    ?InitializeTargets@CInitializeFtmTargetsJob@@AEAAHXZ; CInitializeFtmTargetsJob::InitializeTargets(void)
0x1400c014d  mov     edi, eax
0x1400c014f  test    eax, eax
0x1400c0151  jz      short loc_1400C018E
0x1400c0153  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400c015a  jz      loc_1400C0257
0x1400c0160  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0167  mov     r9d, 4Fh ; 'O'
0x1400c016d  mov     eax, [rbx+10h]
0x1400c0170  mov     dl, 2
0x1400c0172  mov     [rsp+78h+var_48], eax
0x1400c0176  mov     [rsp+78h+var_50], rbx
0x1400c017b  mov     rcx, [rcx+40h]
0x1400c017f  mov     [rsp+78h+var_58], r15
0x1400c0184  call    WPP_RECORDER_SF_qD
0x1400c0189  jmp     loc_1400C0257
0x1400c018e  mov     dword ptr [rbx+200h], 3
0x1400c0198  jmp     loc_1400C0257
0x1400c019d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400c01a4  jz      short loc_1400C01CF
0x1400c01a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c01ad  mov     r9d, 4Bh ; 'K'
0x1400c01b3  mov     eax, [rbx+10h]
0x1400c01b6  mov     dl, 4
0x1400c01b8  mov     [rsp+78h+var_48], eax
0x1400c01bc  mov     [rsp+78h+var_50], rbx
0x1400c01c1  mov     rcx, [rcx+40h]
0x1400c01c5  mov     [rsp+78h+var_58], r15
0x1400c01ca  call    WPP_RECORDER_SF_qD
0x1400c01cf  mov     rdx, rsi; struct CChannelListManager *
0x1400c01d2  mov     rcx, rbx; this
0x1400c01d5  call    ?StartScanJob@CInitializeFtmTargetsJob@@AEAAHPEAVCChannelListManager@@@Z; CInitializeFtmTargetsJob::StartScanJob(CChannelListManager *)
0x1400c01da  mov     edi, eax
0x1400c01dc  test    eax, eax
0x1400c01de  jz      short loc_1400C0216
0x1400c01e0  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400c01e7  jz      short loc_1400C0216
0x1400c01e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c01f0  mov     r9d, 4Ch ; 'L'
0x1400c01f6  mov     dword ptr [rsp+78h+var_40], eax
0x1400c01fa  mov     dl, 2
0x1400c01fc  mov     eax, [rbx+10h]
0x1400c01ff  mov     [rsp+78h+var_48], eax
0x1400c0203  mov     rcx, [rcx+40h]
0x1400c0207  mov     [rsp+78h+var_50], rbx
0x1400c020c  mov     [rsp+78h+var_58], r15
0x1400c0211  call    WPP_RECORDER_SF_qDL
0x1400c0216  mov     rcx, rsi; void *
0x1400c0219  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c021e  jmp     short loc_1400C0257
0x1400c0220  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400c0227  jz      short loc_1400C0252
0x1400c0229  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0230  mov     r9d, 4Ah ; 'J'
0x1400c0236  mov     eax, [rbx+10h]
0x1400c0239  mov     dl, 2
0x1400c023b  mov     [rsp+78h+var_48], eax
0x1400c023f  mov     [rsp+78h+var_50], rbx
0x1400c0244  mov     rcx, [rcx+40h]
0x1400c0248  mov     [rsp+78h+var_58], r15
0x1400c024d  call    WPP_RECORDER_SF_qD
0x1400c0252  mov     edi, 0C000009Ah
0x1400c0257  cmp     dword ptr [rbx+200h], 3
0x1400c025e  jz      short loc_1400C0264
0x1400c0260  test    edi, edi
0x1400c0262  jz      short loc_1400C026E
0x1400c0264  mov     edx, edi; int
0x1400c0266  mov     rcx, rbx; this
0x1400c0269  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x1400c026e  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400c0275  jz      short loc_1400C02B0
0x1400c0277  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c027e  cmp     byte ptr [rcx+29h], 5
0x1400c0282  jnb     short loc_1400C028A
0x1400c0284  cmp     [rcx+48h], bp
0x1400c0288  jz      short loc_1400C02B0
0x1400c028a  mov     eax, [rbx+10h]
0x1400c028d  mov     r9d, 50h ; 'P'
0x1400c0293  mov     rcx, [rcx+40h]
0x1400c0297  mov     dl, 5
0x1400c0299  mov     dword ptr [rsp+78h+var_40], edi
0x1400c029d  mov     [rsp+78h+var_48], eax
0x1400c02a1  mov     [rsp+78h+var_50], rbx
0x1400c02a6  mov     [rsp+78h+var_58], r15
0x1400c02ab  call    WPP_RECORDER_SF_qDD
0x1400c02b0  add     rsp, 48h
0x1400c02b4  pop     r15
0x1400c02b6  pop     r14
0x1400c02b8  pop     rdi
0x1400c02b9  pop     rsi
0x1400c02ba  pop     rbp
0x1400c02bb  pop     rbx
0x1400c02bc  retn
```
