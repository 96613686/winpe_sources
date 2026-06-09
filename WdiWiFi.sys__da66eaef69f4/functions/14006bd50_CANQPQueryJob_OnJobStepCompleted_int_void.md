# CANQPQueryJob::OnJobStepCompleted(int,void *)

- ea: `0x14006bd50`
- end: `0x14006c540`
- name: `?OnJobStepCompleted@CANQPQueryJob@@UEAAXHPEAX@Z`
- size: `2032`
- prototype: `void __fastcall(CJobBase *this, int, void *)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140010730`
- `0x140011ad4`
- `0x140011c5c`
- `0x1400122e0`
- `0x1400243b4`
- `0x1400259d8`
- `0x140025d38`
- `0x14002a604`
- `0x14002aa28`
- `0x14003b77c`
- `0x140043e3c`
- `0x14004864c`
- `0x1400488b8`
- `0x14006bd50`
- `0x14006c548`
- `0x140074844`
- `0x14008d6f0`
- `0x14009a5ec`
- `0x14009a6fc`
- `0x14009a830`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006bf53`
- `ntoskrnl!ExAllocatePool2` at `0x14006bf53`

## pseudocode

```c
void __fastcall CANQPQueryJob::OnJobStepCompleted(CJobBase *this, int a2, void *a3)
{
  int started; // edi
  int m_pJobCompletionCallback_high; // edx
  int v7; // r8d
  int v8; // r9d
  int v9; // r9d
  ActiveJobsList *v10; // rcx
  _WFC_JOB_TYPE m_JobType; // edx
  INotifyOperationStarted *v12; // rax
  int v13; // r9d
  int v14; // eax
  DeviceCommand *Pool2; // rax
  int v16; // edx
  int v17; // r8d
  IActivityId *v18; // rsi
  INotifyOperationStarted *v19; // rcx
  int v20; // eax
  int v21; // r9d
  INotifyOperationStarted *EventJobStarted; // rcx
  ActiveJobsList *m_pActiveJobsList; // rcx
  unsigned int v24; // r9d
  unsigned int v25; // edx
  int NextActionFrameDialogTokenFromIhv; // eax
  bool v27; // zf
  struct DeviceCommand *pThis; // rcx
  int CommandResult; // eax
  void (__fastcall ***v30)(void *, __int64); // rcx
  char v31; // al
  unsigned int v32; // r9d
  unsigned int m_ActivityId; // edx
  unsigned __int16 m_pDebugDeviceCommand; // r8
  unsigned __int8 *v35; // r9
  int v36; // r9d
  struct CBSSEntry *CachedBSSEntry; // rax
  int v38; // [rsp+20h] [rbp-50h]
  enum _WDF_EXECUTION_LEVEL v39; // [rsp+28h] [rbp-48h]
  struct TimerRegistrationContext **v40; // [rsp+38h] [rbp-38h]
  int v41; // [rsp+38h] [rbp-38h]
  unsigned int v42; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 *v43; // [rsp+68h] [rbp-8h] BYREF
  char v44; // [rsp+A8h] [rbp+38h] BYREF
  int v45; // [rsp+B8h] [rbp+48h] BYREF

  v45 = 0;
  started = a2;
  v44 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      100,
      (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  CANQPQueryJob::CheckAndMarkPendingJobs((CANQPQueryJob *)this, started, a3);
  if ( started )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v9 = 101;
      LODWORD(v40) = started;
LABEL_11:
      LOBYTE(m_pJobCompletionCallback_high) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        m_pJobCompletionCallback_high,
        v7,
        v9,
        (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
        (char)this,
        this->m_ActivityId,
        v40);
      goto LABEL_98;
    }
    goto LABEL_98;
  }
  if ( *((_BYTE *)&this[1].m_FailsafeJobStartedEvent.m_EventType + 4) )
  {
    started = -1073676276;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v9 = 102;
      LODWORD(v40) = -1073676276;
      goto LABEL_11;
    }
LABEL_98:
    if ( this[1].m_JobType == WiFiJobTypeInvalid )
      this[1].m_JobType = started;
    if ( CANQPQueryJob::CheckAndMarkPendingJobs((CANQPQueryJob *)this, 0, 0) )
    {
      this->OnJobCancelled(this);
      goto LABEL_104;
    }
    m_JobType = this[1].m_JobType;
LABEL_103:
    CANQPQueryJob::CleanupAndCompleteJob(this, m_JobType);
    goto LABEL_104;
  }
  m_pJobCompletionCallback_high = HIDWORD(this[1].m_pJobCompletionCallback);
  started = 0;
  if ( m_pJobCompletionCallback_high == 1 )
  {
    LOBYTE(v12) = (_BYTE)this + 40;
    if ( a3 != &this[5].m_FailsafeDeferJobStartEvent.m_EventType )
    {
      LOBYTE(v10) = (_BYTE)this - 96;
      if ( a3 != &this[1].m_FailsafeJobStartedEvent.m_SenderObject )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return;
        v13 = 103;
        LOBYTE(m_pJobCompletionCallback_high) = 2;
LABEL_23:
        WPP_RECORDER_SF_qDqqq(
          WPP_GLOBAL_Control->DeviceExtension,
          m_pJobCompletionCallback_high,
          v7,
          v13,
          v38,
          (char)this,
          this->m_ActivityId,
          (char)a3,
          (char)v10,
          (char)v12);
        goto LABEL_104;
      }
    }
    CachedBSSEntry = CANQPQueryJob::FindCachedBSSEntry((CANQPQueryJob *)this);
    if ( !CachedBSSEntry )
    {
      started = -1073676261;
      goto LABEL_98;
    }
    started = CANQPQueryJob::StartANQPQueryTask(this, CachedBSSEntry);
LABEL_95:
    if ( !started )
      goto LABEL_104;
    goto LABEL_98;
  }
  switch ( HIDWORD(this[1].m_pJobCompletionCallback) )
  {
    case 2:
      pThis = (struct DeviceCommand *)this[9].m_SerializedJobLink.pThis;
      v42 = 0;
      v43 = 0;
      if ( a3 != pThis )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return;
        LOBYTE(m_pJobCompletionCallback_high) = 2;
        WPP_RECORDER_SF_qDqq(
          WPP_GLOBAL_Control->DeviceExtension,
          m_pJobCompletionCallback_high,
          v7,
          104,
          v38,
          (char)this,
          this->m_ActivityId,
          (char)a3,
          (char)pThis);
        break;
      }
      started = CMessageHelper::GetStatusFromCommandResult(pThis, &v45);
      if ( started || (started = v45) != 0 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_98;
        v36 = 105;
        v41 = started;
      }
      else
      {
        CommandResult = DeviceCommand::get_CommandResult((DeviceCommand *)this[9].m_SerializedJobLink.pThis, &v42, &v43);
        started = CommandResult;
        if ( !CommandResult && v42 >= 0x31 )
        {
          NextActionFrameDialogTokenFromIhv = ParseWdiGetNextActionFrameDialogTokenFromIhv(
                                                v42 - 48,
                                                v43 + 48,
                                                &this[1].IOperationCompletionCallback::__vftable[341].OnJobStarted,
                                                &v44);
          started = NextActionFrameDialogTokenFromIhv;
          if ( NextActionFrameDialogTokenFromIhv )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
              goto LABEL_98;
            v9 = 107;
          }
          else
          {
            v30 = (void (__fastcall ***)(void *, __int64))this[9].m_SerializedJobLink.pThis;
            if ( v30 )
              (**v30)(v30, 1);
            v31 = v44;
            LOBYTE(this[10].m_ActivityId) = v44;
            this[9].m_SerializedJobLink.pThis = 0;
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(m_pJobCompletionCallback_high) = 4;
              WPP_RECORDER_SF_qDL(
                WPP_GLOBAL_Control->DeviceExtension,
                m_pJobCompletionCallback_high,
                v7,
                108,
                (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
                (char)this,
                this->m_ActivityId,
                v31);
            }
            v32 = 1000;
            if ( this[1].m_NdisPortNumber != 1 )
              v32 = 2000;
            m_ActivityId = this->m_ActivityId;
            *((_BYTE *)&this[1].m_FailsafeJobStartedEvent.m_EventType + 6) = 1;
            NextActionFrameDialogTokenFromIhv = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
                                                  this->m_pEventQueue,
                                                  m_ActivityId,
                                                  (struct ITimerCallback *)((unsigned __int64)&this[1].m_JobPriority
                                                                          & -(__int64)(this != 0)),
                                                  v32,
                                                  &this[1].m_pJobCompletionCallback,
                                                  v39,
                                                  0,
                                                  0,
                                                  (unsigned int *)&this[1].m_pJobCompletionCallback);
            started = NextActionFrameDialogTokenFromIhv;
            if ( NextActionFrameDialogTokenFromIhv )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                goto LABEL_98;
              v9 = 109;
            }
            else
            {
              m_pDebugDeviceCommand = (unsigned __int16)this[1].m_pDebugDeviceCommand;
              v35 = (unsigned __int8 *)&this[1].m_pSerializedJobList->m_pResetForPortCompletionCallback + 6;
              HIDWORD(this[1].m_pJobCompletionCallback) = 3;
              NextActionFrameDialogTokenFromIhv = CANQPQueryJob::BuildAndSendANQPRequestActionFrame(
                                                    this,
                                                    DOT11_PUBLIC_ACTION_FRAME_TYPE_GAS_INITIAL_REQUEST,
                                                    m_pDebugDeviceCommand,
                                                    v35,
                                                    1u);
              started = NextActionFrameDialogTokenFromIhv;
              if ( !NextActionFrameDialogTokenFromIhv )
                break;
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                goto LABEL_98;
              v9 = 110;
            }
          }
          goto LABEL_71;
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_95;
        v36 = 106;
        v41 = CommandResult;
      }
      LOBYTE(m_pJobCompletionCallback_high) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        m_pJobCompletionCallback_high,
        v7,
        v36,
        (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
        (char)this,
        this->m_ActivityId,
        v41);
      goto LABEL_95;
    case 4:
      m_pActiveJobsList = this[10].m_pActiveJobsList;
      if ( m_pActiveJobsList
        || this[10].EventJobStarted
        || *((_BYTE *)&this[1].m_FailsafeJobStartedEvent.m_EventType + 5) )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return;
        WPP_RECORDER_SF_qDqqqD(
          WPP_GLOBAL_Control->DeviceExtension,
          m_pJobCompletionCallback_high,
          v7,
          v8,
          v38,
          (char)this,
          this->m_ActivityId,
          (char)a3,
          (char)m_pActiveJobsList,
          (char)this[10].EventJobStarted,
          *((_BYTE *)&this[1].m_FailsafeJobStartedEvent.m_EventType + 5));
        break;
      }
      v24 = 1000;
      if ( this[1].m_NdisPortNumber != 1 )
        v24 = 2000;
      v25 = this->m_ActivityId;
      *((_BYTE *)&this[1].m_FailsafeJobStartedEvent.m_EventType + 6) = 1;
      NextActionFrameDialogTokenFromIhv = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
                                            this->m_pEventQueue,
                                            v25,
                                            (struct ITimerCallback *)((unsigned __int64)&this[1].m_JobPriority
                                                                    & -(__int64)(this != 0)),
                                            v24,
                                            &this[1].m_pJobCompletionCallback,
                                            v39,
                                            0,
                                            0,
                                            (unsigned int *)&this[1].m_pJobCompletionCallback);
      started = NextActionFrameDialogTokenFromIhv;
      if ( NextActionFrameDialogTokenFromIhv )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_98;
        v9 = 117;
      }
      else
      {
        v27 = HIWORD(this[1].m_FailsafeJobStartedEvent.m_EventType) == 0;
        HIWORD(this[1].m_FailsafeJobStartedEvent.m_EventType) = 0;
        HIDWORD(this[1].m_pJobCompletionCallback) = 3;
        NextActionFrameDialogTokenFromIhv = CANQPQueryJob::BuildAndSendANQPRequestActionFrame(
                                              this,
                                              DOT11_PUBLIC_ACTION_FRAME_TYPE_GAS_COMEBACK_REQUEST,
                                              0,
                                              0,
                                              !v27);
        started = NextActionFrameDialogTokenFromIhv;
        if ( !NextActionFrameDialogTokenFromIhv )
          break;
        HIDWORD(this[1].m_pDebugDeviceCommand) = 3;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_98;
        v9 = 118;
      }
LABEL_71:
      LODWORD(v40) = NextActionFrameDialogTokenFromIhv;
      goto LABEL_11;
    case 5:
    case 6:
      if ( this[10].m_pActiveJobsList )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return;
        LOBYTE(m_pJobCompletionCallback_high) = 4;
        WPP_RECORDER_SF_qDqq(
          WPP_GLOBAL_Control->DeviceExtension,
          m_pJobCompletionCallback_high,
          v7,
          111,
          v38,
          (char)this,
          this->m_ActivityId,
          (char)a3,
          (char)this[10].m_pActiveJobsList);
        break;
      }
      v14 = 4;
      if ( m_pJobCompletionCallback_high != 5 )
        v14 = 7;
      HIDWORD(this[1].m_pJobCompletionCallback) = v14;
      Pool2 = (DeviceCommand *)ExAllocatePool2(64, 184, 1198089303);
      v18 = &this->IActivityId;
      if ( Pool2 )
        v19 = (INotifyOperationStarted *)DeviceCommand::DeviceCommand(Pool2, v18->m_ActivityId);
      else
        v19 = 0;
      this[10].EventJobStarted = v19;
      if ( !v19 )
      {
        started = -1073741670;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v16,
            v17,
            115,
            (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
            (char)this,
            v18->m_ActivityId,
            -1073741670);
        }
LABEL_46:
        EventJobStarted = this[10].EventJobStarted;
        if ( !EventJobStarted )
          goto LABEL_98;
        ((void (__fastcall *)(INotifyOperationStarted *, __int64))EventJobStarted->OnOperationStarted)(
          EventJobStarted,
          1);
        this[10].EventJobStarted = 0;
        goto LABEL_95;
      }
      v20 = DeviceCommand::Initialize(
              (DeviceCommand *)v19,
              this->m_PortId,
              0x7Du,
              0x30u,
              (unsigned __int8 *)&this[10].m_pEventQueue);
      started = v20;
      if ( v20 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_42;
        v21 = 114;
      }
      else
      {
        v20 = CJobBase::QueueDeviceCommand(this, (struct DeviceCommand *)this[10].EventJobStarted);
        started = v20;
        if ( !v20 )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            return;
          LOBYTE(m_pJobCompletionCallback_high) = 4;
          WPP_RECORDER_SF_qDq(
            WPP_GLOBAL_Control->DeviceExtension,
            m_pJobCompletionCallback_high,
            v7,
            112,
            (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
            (char)this,
            v18->m_ActivityId,
            (char)this[10].EventJobStarted);
          break;
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        {
LABEL_42:
          if ( !started )
            break;
          goto LABEL_46;
        }
        v21 = 113;
      }
      LOBYTE(m_pJobCompletionCallback_high) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        m_pJobCompletionCallback_high,
        v7,
        v21,
        (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
        (char)this,
        v18->m_ActivityId,
        v20);
      goto LABEL_42;
    case 7:
      v10 = this[10].m_pActiveJobsList;
      if ( !v10 && !this[10].EventJobStarted )
      {
        m_JobType = WiFiJobTypeInvalid;
        goto LABEL_103;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return;
      v12 = this[10].EventJobStarted;
      v13 = 119;
      LOBYTE(m_pJobCompletionCallback_high) = 4;
      goto LABEL_23;
  }
LABEL_104:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(m_pJobCompletionCallback_high) = 5;
    LODWORD(v40) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      m_pJobCompletionCallback_high,
      v7,
      120,
      (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
      (char)this,
      this->m_ActivityId,
      v40);
  }
}

```

## disassembly

```asm
0x14006bd50  mov     [rsp-28h+arg_0], rbx
0x14006bd55  mov     [rsp-28h+arg_10], rsi
0x14006bd5a  push    rbp
0x14006bd5b  push    rdi
0x14006bd5c  push    r12
0x14006bd5e  push    r14
0x14006bd60  push    r15
0x14006bd62  mov     rbp, rsp
0x14006bd65  sub     rsp, 70h
0x14006bd69  xor     r14d, r14d
0x14006bd6c  mov     rsi, r8
0x14006bd6f  mov     [rbp+arg_18], r14d
0x14006bd73  mov     edi, edx
0x14006bd75  mov     [rbp+arg_8], r14b
0x14006bd79  mov     rbx, rcx
0x14006bd7c  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14006bd83  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006bd8a  lea     r12, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x14006bd91  jz      short loc_14006BDC9
0x14006bd93  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bd9a  cmp     byte ptr [rcx+29h], 5
0x14006bd9e  jnb     short loc_14006BDA7
0x14006bda0  cmp     [rcx+48h], r14w
0x14006bda5  jz      short loc_14006BDC9
0x14006bda7  mov     eax, [rbx+10h]
0x14006bdaa  mov     r9d, 64h ; 'd'
0x14006bdb0  mov     rcx, [rcx+40h]
0x14006bdb4  mov     dl, 5
0x14006bdb6  mov     dword ptr [rsp+70h+var_40], eax
0x14006bdba  mov     qword ptr [rsp+70h+var_48], rbx; enum _WDF_EXECUTION_LEVEL
0x14006bdbf  mov     [rsp+70h+var_50], r12
0x14006bdc4  call    WPP_RECORDER_SF_qD
0x14006bdc9  mov     r8, rsi; void *
0x14006bdcc  mov     edx, edi; int
0x14006bdce  mov     rcx, rbx; this
0x14006bdd1  call    ?CheckAndMarkPendingJobs@CANQPQueryJob@@AEAAEHPEAX@Z; CANQPQueryJob::CheckAndMarkPendingJobs(int,void *)
0x14006bdd6  test    edi, edi
0x14006bdd8  jz      short loc_14006BDF3
0x14006bdda  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006bde1  jz      loc_14006C4A4
0x14006bde7  mov     r9d, 65h ; 'e'
0x14006bded  mov     dword ptr [rsp+70h+var_38], edi
0x14006bdf1  jmp     short loc_14006BE1C
0x14006bdf3  cmp     [rbx+29Ch], r14b
0x14006bdfa  jz      short loc_14006BE44
0x14006bdfc  mov     edi, 0C001000Ch
0x14006be01  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006be08  jz      loc_14006C4A4
0x14006be0e  mov     r9d, 66h ; 'f'
0x14006be14  mov     dword ptr [rsp+70h+var_38], 0C001000Ch
0x14006be1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006be23  mov     dl, 2
0x14006be25  mov     eax, [rbx+10h]
0x14006be28  mov     dword ptr [rsp+70h+var_40], eax
0x14006be2c  mov     qword ptr [rsp+70h+var_48], rbx
0x14006be31  mov     rcx, [rcx+40h]
0x14006be35  mov     [rsp+70h+var_50], r12
0x14006be3a  call    WPP_RECORDER_SF_qDD
0x14006be3f  jmp     loc_14006C4A4
0x14006be44  mov     edx, [rbx+284h]
0x14006be4a  mov     edi, r14d
0x14006be4d  mov     ecx, edx
0x14006be4f  sub     ecx, 1
0x14006be52  jz      loc_14006C44D
0x14006be58  sub     ecx, 1
0x14006be5b  jz      loc_14006C210
0x14006be61  sub     ecx, 2
0x14006be64  jz      loc_14006C0C1
0x14006be6a  sub     ecx, 1
0x14006be6d  jz      short loc_14006BEE5
0x14006be6f  sub     ecx, 1
0x14006be72  jz      short loc_14006BEE5
0x14006be74  cmp     ecx, 1
0x14006be77  jnz     loc_14006C4E3
0x14006be7d  mov     rcx, [rbx+1450h]
0x14006be84  test    rcx, rcx
0x14006be87  jnz     short loc_14006BE99
0x14006be89  cmp     [rbx+1418h], r14
0x14006be90  jnz     short loc_14006BE99
0x14006be92  xor     edx, edx
0x14006be94  jmp     loc_14006C4DB
0x14006be99  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006bea0  jz      loc_14006C526
0x14006bea6  mov     rax, [rbx+1418h]
0x14006bead  mov     r9d, 77h ; 'w'
0x14006beb3  mov     dl, 4
0x14006beb5  mov     [rsp+70h+var_28], rax
0x14006beba  mov     eax, [rbx+10h]
0x14006bebd  mov     [rsp+70h+var_30], rcx
0x14006bec2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bec9  mov     [rsp+70h+var_38], rsi
0x14006bece  mov     dword ptr [rsp+70h+var_40], eax
0x14006bed2  mov     qword ptr [rsp+70h+var_48], rbx
0x14006bed7  mov     rcx, [rcx+40h]
0x14006bedb  call    WPP_RECORDER_SF_qDqqq
0x14006bee0  jmp     loc_14006C4E3
0x14006bee5  mov     rax, [rbx+1450h]
0x14006beec  test    rax, rax
0x14006beef  jz      short loc_14006BF31
0x14006bef1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006bef8  jz      loc_14006C526
0x14006befe  mov     r9d, 6Fh ; 'o'
0x14006bf04  mov     [rsp+70h+var_30], rax
0x14006bf09  mov     dl, 4
0x14006bf0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bf12  mov     eax, [rbx+10h]
0x14006bf15  mov     [rsp+70h+var_38], rsi
0x14006bf1a  mov     dword ptr [rsp+70h+var_40], eax
0x14006bf1e  mov     rcx, [rcx+40h]
0x14006bf22  mov     qword ptr [rsp+70h+var_48], rbx
0x14006bf27  call    WPP_RECORDER_SF_qDqq
0x14006bf2c  jmp     loc_14006C4E3
0x14006bf31  mov     eax, 4
0x14006bf36  cmp     edx, 5
0x14006bf39  mov     edx, 0B8h
0x14006bf3e  mov     r8d, 47696457h
0x14006bf44  lea     ecx, [rax+3]
0x14006bf47  cmovnz  eax, ecx
0x14006bf4a  lea     ecx, [rdx-78h]
0x14006bf4d  mov     [rbx+284h], eax
0x14006bf53  call    cs:__imp_ExAllocatePool2
0x14006bf5a  nop     dword ptr [rax+rax+00h]
0x14006bf5f  lea     rsi, [rbx+10h]
0x14006bf63  test    rax, rax
0x14006bf66  jz      short loc_14006BF77
0x14006bf68  mov     edx, [rsi]; unsigned int
0x14006bf6a  mov     rcx, rax; this
0x14006bf6d  call    ??0DeviceCommand@@QEAA@K@Z; DeviceCommand::DeviceCommand(ulong)
0x14006bf72  mov     rcx, rax
0x14006bf75  jmp     short loc_14006BF7A
0x14006bf77  mov     rcx, r14; this
0x14006bf7a  mov     [rbx+1418h], rcx
0x14006bf81  test    rcx, rcx
0x14006bf84  jz      loc_14006C057
0x14006bf8a  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x14006bf8e  lea     rax, [rbx+1420h]
0x14006bf95  mov     r9d, 30h ; '0'; unsigned int
0x14006bf9b  mov     [rsp+70h+var_50], rax; unsigned __int8 *
0x14006bfa0  lea     r8d, [r9+4Dh]; unsigned int
0x14006bfa4  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x14006bfa9  mov     edi, eax
0x14006bfab  test    eax, eax
0x14006bfad  jnz     short loc_14006C019
0x14006bfaf  mov     rdx, [rbx+1418h]; struct DeviceCommand *
0x14006bfb6  mov     rcx, rbx; this
0x14006bfb9  call    ?QueueDeviceCommand@CJobBase@@IEAAHPEAVDeviceCommand@@@Z; CJobBase::QueueDeviceCommand(DeviceCommand *)
0x14006bfbe  mov     edi, eax
0x14006bfc0  test    eax, eax
0x14006bfc2  jnz     short loc_14006C008
0x14006bfc4  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006bfcb  jz      loc_14006C526
0x14006bfd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bfd8  lea     r9d, [rax+70h]
0x14006bfdc  mov     rax, [rbx+1418h]
0x14006bfe3  mov     dl, 4
0x14006bfe5  mov     [rsp+70h+var_38], rax
0x14006bfea  mov     eax, [rsi]
0x14006bfec  mov     rcx, [rcx+40h]
0x14006bff0  mov     dword ptr [rsp+70h+var_40], eax
0x14006bff4  mov     qword ptr [rsp+70h+var_48], rbx
0x14006bff9  mov     [rsp+70h+var_50], r12
0x14006bffe  call    WPP_RECORDER_SF_qDq
0x14006c003  jmp     loc_14006C4E3
0x14006c008  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006c00f  jz      short loc_14006C04E
0x14006c011  mov     r9d, 71h ; 'q'
0x14006c017  jmp     short loc_14006C028
0x14006c019  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006c020  jz      short loc_14006C04E
0x14006c022  mov     r9d, 72h ; 'r'
0x14006c028  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c02f  mov     dl, 2
0x14006c031  mov     dword ptr [rsp+70h+var_38], eax
0x14006c035  mov     eax, [rsi]
0x14006c037  mov     dword ptr [rsp+70h+var_40], eax
0x14006c03b  mov     rcx, [rcx+40h]
0x14006c03f  mov     qword ptr [rsp+70h+var_48], rbx
0x14006c044  mov     [rsp+70h+var_50], r12
0x14006c049  call    WPP_RECORDER_SF_qDD
0x14006c04e  test    edi, edi
0x14006c050  jnz     short loc_14006C095
0x14006c052  jmp     loc_14006C4E3
0x14006c057  mov     edi, 0C000009Ah
0x14006c05c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006c063  jz      short loc_14006C095
0x14006c065  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c06c  mov     r9d, 73h ; 's'
0x14006c072  mov     eax, [rsi]
0x14006c074  mov     dl, 2
0x14006c076  mov     dword ptr [rsp+70h+var_38], 0C000009Ah
0x14006c07e  mov     dword ptr [rsp+70h+var_40], eax
0x14006c082  mov     rcx, [rcx+40h]
0x14006c086  mov     qword ptr [rsp+70h+var_48], rbx
0x14006c08b  mov     [rsp+70h+var_50], r12
0x14006c090  call    WPP_RECORDER_SF_qDD
0x14006c095  mov     rcx, [rbx+1418h]
0x14006c09c  test    rcx, rcx
0x14006c09f  jz      loc_14006C4A4
0x14006c0a5  mov     rax, [rcx]
0x14006c0a8  mov     edx, 1
0x14006c0ad  mov     rax, [rax]
0x14006c0b0  call    _guard_dispatch_icall
0x14006c0b5  mov     [rbx+1418h], r14
0x14006c0bc  jmp     loc_14006C499
0x14006c0c1  mov     rcx, [rbx+1450h]
0x14006c0c8  test    rcx, rcx
0x14006c0cb  jnz     loc_14006C1C1
0x14006c0d1  cmp     [rbx+1418h], r14
0x14006c0d8  jnz     loc_14006C1C1
0x14006c0de  cmp     [rbx+29Dh], r14b
0x14006c0e5  jnz     loc_14006C1C1
0x14006c0eb  cmp     dword ptr [rbx+238h], 1
0x14006c0f2  lea     rdx, [rbx+280h]
0x14006c0f9  mov     [rsp+70h+var_30], rdx; unsigned int *
0x14006c0fe  lea     rcx, [rbx+230h]
0x14006c105  mov     eax, 7D0h
0x14006c10a  mov     [rsp+70h+var_38], r14; struct TimerRegistrationContext **
0x14006c10f  mov     r9d, 3E8h
0x14006c115  mov     [rsp+70h+var_40], r14b; bool
0x14006c11a  cmovnz  r9d, eax; unsigned int
0x14006c11e  mov     [rsp+70h+var_50], rdx; void *
0x14006c123  mov     edx, [rbx+10h]; unsigned int
0x14006c126  mov     rax, rbx
0x14006c129  neg     rax
0x14006c12c  mov     byte ptr [rbx+29Eh], 1
0x14006c133  sbb     r8, r8
0x14006c136  and     r8, rcx; struct ITimerCallback *
0x14006c139  mov     rcx, [rbx+20h]; this
0x14006c13d  call    ?RegisterTimeoutCallbackWithLevelAndReuse@EventQueue@@QEAAHKPEAVITimerCallback@@KPEAXW4_WDF_EXECUTION_LEVEL@@_NPEAPEAVTimerRegistrationContext@@PEAI@Z; EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(ulong,ITimerCallback *,ulong,void *,_WDF_EXECUTION_LEVEL,bool,TimerRegistrationContext * *,uint *)
0x14006c142  mov     edi, eax
0x14006c144  test    eax, eax
0x14006c146  jz      short loc_14006C160
0x14006c148  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006c14f  jz      loc_14006C4A4
0x14006c155  mov     r9d, 75h ; 'u'
0x14006c15b  jmp     loc_14006C2C6
0x14006c160  movzx   ecx, word ptr [rbx+29Ah]
0x14006c167  test    cx, cx
0x14006c16a  mov     [rbx+29Ah], r14w
0x14006c172  mov     rcx, rbx; this
0x14006c175  mov     dword ptr [rbx+284h], 3
0x14006c17f  setnz   al
0x14006c182  xor     r8d, r8d; unsigned __int16
0x14006c185  xor     r9d, r9d; unsigned __int8 *
0x14006c188  mov     byte ptr [rsp+70h+var_50], al; unsigned __int8
0x14006c18c  lea     edx, [r8+0Ch]; enum _DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE
0x14006c190  call    ?BuildAndSendANQPRequestActionFrame@CANQPQueryJob@@AEAAHW4_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE@@GPEAEE@Z; CANQPQueryJob::BuildAndSendANQPRequestActionFrame(_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE,ushort,uchar *,uchar)
0x14006c195  mov     edi, eax
0x14006c197  test    eax, eax
0x14006c199  jz      loc_14006C4E3
0x14006c19f  mov     dword ptr [rbx+274h], 3
0x14006c1a9  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006c1b0  jz      loc_14006C4A4
0x14006c1b6  mov     r9d, 76h ; 'v'
0x14006c1bc  jmp     loc_14006C2C6
0x14006c1c1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006c1c8  jz      loc_14006C526
0x14006c1ce  movzx   eax, byte ptr [rbx+29Dh]
0x14006c1d5  mov     [rsp+70h+var_20], eax
0x14006c1d9  mov     rax, [rbx+1418h]
0x14006c1e0  mov     [rsp+70h+var_28], rax
0x14006c1e5  mov     eax, [rbx+10h]
0x14006c1e8  mov     [rsp+70h+var_30], rcx
0x14006c1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c1f4  mov     [rsp+70h+var_38], rsi
0x14006c1f9  mov     dword ptr [rsp+70h+var_40], eax
0x14006c1fd  mov     qword ptr [rsp+70h+var_48], rbx
0x14006c202  mov     rcx, [rcx+40h]
0x14006c206  call    WPP_RECORDER_SF_qDqqqD
0x14006c20b  jmp     loc_14006C4E3
0x14006c210  mov     rcx, [rbx+13D8h]; struct DeviceCommand *
0x14006c217  mov     [rbp+var_10], r14d
0x14006c21b  mov     [rbp+var_8], r14
0x14006c21f  cmp     rsi, rcx
0x14006c222  jz      short loc_14006C243
0x14006c224  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006c22b  jz      loc_14006C526
0x14006c231  mov     r9d, 68h ; 'h'
0x14006c237  mov     [rsp+70h+var_30], rcx
0x14006c23c  mov     dl, 2
0x14006c23e  jmp     loc_14006BF0B
0x14006c243  lea     rdx, [rbp+arg_18]; int *
0x14006c247  call    ?GetStatusFromCommandResult@CMessageHelper@@SAHPEAVDeviceCommand@@PEAH@Z; CMessageHelper::GetStatusFromCommandResult(DeviceCommand *,int *)
0x14006c24c  mov     edi, eax
0x14006c24e  test    eax, eax
0x14006c250  jnz     loc_14006C411
0x14006c256  mov     edi, [rbp+arg_18]
0x14006c259  test    edi, edi
0x14006c25b  jnz     loc_14006C411
0x14006c261  mov     rcx, [rbx+13D8h]; this
0x14006c268  lea     r8, [rbp+var_8]; unsigned __int8 **
0x14006c26c  lea     rdx, [rbp+var_10]; unsigned int *
0x14006c270  call    ?get_CommandResult@DeviceCommand@@QEAAHPEAKPEAPEAE@Z; DeviceCommand::get_CommandResult(ulong *,uchar * *)
0x14006c275  mov     edi, eax
0x14006c277  test    eax, eax
0x14006c279  jnz     loc_14006C3F8
0x14006c27f  mov     ecx, [rbp+var_10]
0x14006c282  cmp     ecx, 31h ; '1'
0x14006c285  jb      loc_14006C3F8
0x14006c28b  mov     r8, [rbx+200h]
  ... truncated ...
```
