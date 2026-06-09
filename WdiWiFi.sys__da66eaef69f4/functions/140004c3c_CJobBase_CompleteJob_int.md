# CJobBase::CompleteJob(int)

- ea: `0x140004c3c`
- end: `0x140004f25`
- name: `?CompleteJob@CJobBase@@IEAAHH@Z`
- size: `745`
- prototype: `__int64 __fastcall(CJobBase *__hidden this, int)`
- caller_count: `113`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000f25c`
- `0x140011710`
- `0x1400119b0`
- `0x1400143d8`
- `0x14001ba80`
- `0x14001bb70`
- `0x1400208a4`
- `0x1400298b0`
- `0x14002a240`
- `0x14002b0b0`
- `0x14002c000`
- `0x14002c360`
- `0x14002c9f0`
- `0x14002cdf0`
- `0x14002d3f4`
- `0x14002eec4`
- `0x140044d00`
- `0x140044f50`
- `0x140046030`
- `0x1400471a0`
- `0x140047a00`
- `0x140048af0`
- `0x1400490d0`
- `0x140051b18`
- `0x140053c68`
- `0x140055340`
- `0x140055580`
- `0x1400583c0`
- `0x140059a70`
- `0x14005a690`
- `0x14005a780`
- `0x14005ba20`
- `0x140060890`
- `0x1400618f0`
- `0x1400619e0`
- `0x140061c00`
- `0x140062110`
- `0x140066b64`
- `0x140069090`
- `0x140069900`
- `0x14006b0d0`
- `0x14006b1c0`
- `0x14006b680`
- `0x14006c8c0`
- `0x14006c9b0`
- `0x14006cbb0`
- `0x14006d350`
- `0x14006d7d0`
- `0x14006e0b0`
- `0x14006ead0`

## callees

- `0x140004c3c`
- `0x1400067b0`
- `0x14000bf04`
- `0x1400122e0`
- `0x140023ae0`
- `0x14002aa28`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004d49`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004d49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004ce8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004ce8`
- `ntoskrnl!ExAllocatePool2` at `0x140004df0`
- `ntoskrnl!ExAllocatePool2` at `0x140004df0`

## pseudocode

```c
__int64 __fastcall CJobBase::CompleteJob(CJobBase *this, int a2, int a3)
{
  int v3; // r15d
  IOperationCompletionCallback *m_pJobCompletionCallback; // r14
  Event *p_m_FailsafeJobCompletionEvent; // rdi
  EventQueue *m_pEventQueue; // rbx
  char v8; // bp
  CNdisSpinLock *m_pEventQueueLock; // rbp
  KIRQL v10; // al
  struct _LIST_ENTRY *Blink; // rdx
  _CPP_LIST_ENTRY *p_m_Link; // rax
  char v13; // di
  KIRQL OldIrql; // dl
  unsigned int v15; // ebx
  Event *Pool2; // rax
  __int64 v18; // [rsp+38h] [rbp-50h]

  v3 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      60,
      (__int64)WPP_cd20a4d0a85c3838a9154e434950069a_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  if ( this->m_State == WiFiJobStateStartOrContinue )
  {
    m_pJobCompletionCallback = this->m_pJobCompletionCallback;
    p_m_FailsafeJobCompletionEvent = &this->m_FailsafeJobCompletionEvent;
    m_pEventQueue = this->m_pEventQueue;
    this->m_State = WiFiJobStateInit;
    if ( this == (CJobBase *)-208LL )
    {
      Pool2 = (Event *)ExAllocatePool2(64, 72, 1198089303);
      if ( !Pool2 || (p_m_FailsafeJobCompletionEvent = Event::Event(Pool2, 0, 0)) == 0 )
      {
        v15 = -1073741670;
        goto LABEL_15;
      }
      v8 = 1;
    }
    else
    {
      v8 = 0;
    }
    if ( m_pEventQueue )
    {
      if ( !p_m_FailsafeJobCompletionEvent->m_IsPending )
      {
        p_m_FailsafeJobCompletionEvent->m_EventType = WiFiEventDeferredOperationCompletion;
        p_m_FailsafeJobCompletionEvent->m_pEventQueueCallback = m_pEventQueue;
        p_m_FailsafeJobCompletionEvent->m_EventPayload = (void *)m_pJobCompletionCallback;
        p_m_FailsafeJobCompletionEvent->m_SenderObject = this;
        p_m_FailsafeJobCompletionEvent->m_EventStatus = v3;
        m_pEventQueueLock = m_pEventQueue->m_pEventQueueLock;
        v10 = KeAcquireSpinLockRaiseToDpc(&m_pEventQueueLock->m_SpinLock.SpinLock);
        m_pEventQueueLock->m_IsLocked = 1;
        m_pEventQueueLock->m_SpinLock.OldIrql = v10;
        p_m_FailsafeJobCompletionEvent->m_IsPending = 1;
        Blink = m_pEventQueue->m_EventQueue.Blink;
        if ( Blink->Flink != &m_pEventQueue->m_EventQueue )
          __fastfail(3u);
        p_m_Link = &p_m_FailsafeJobCompletionEvent->m_Link;
        v13 = 0;
        p_m_Link->ListEntry.Flink = &m_pEventQueue->m_EventQueue;
        p_m_Link->ListEntry.Blink = Blink;
        Blink->Flink = &p_m_Link->ListEntry;
        m_pEventQueue->m_EventQueue.Blink = &p_m_Link->ListEntry;
        if ( !m_pEventQueue->m_IsBeingProcessed )
        {
          v13 = 1;
          m_pEventQueue->m_EventQueueThreadHandle = KeGetCurrentThread();
          m_pEventQueue->m_IsBeingProcessed = 1;
        }
        OldIrql = m_pEventQueueLock->m_SpinLock.OldIrql;
        m_pEventQueueLock->m_IsLocked = 0;
        KeReleaseSpinLock(&m_pEventQueueLock->m_SpinLock.SpinLock, OldIrql);
        if ( v13 )
          EventQueue::ProcessEventQueueUntilEmpty(m_pEventQueue);
        v15 = 0;
        goto LABEL_15;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          a3,
          11,
          (__int64)WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids,
          (char)p_m_FailsafeJobCompletionEvent,
          p_m_FailsafeJobCompletionEvent->m_ActivityId);
      }
      v15 = -1073741436;
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          a3,
          10,
          (__int64)WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids,
          (char)p_m_FailsafeJobCompletionEvent,
          p_m_FailsafeJobCompletionEvent->m_ActivityId);
      }
      v15 = -1073741811;
    }
    if ( p_m_FailsafeJobCompletionEvent && v8 )
      operator delete(p_m_FailsafeJobCompletionEvent);
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        61,
        (__int64)WPP_cd20a4d0a85c3838a9154e434950069a_Traceguids,
        (char)this,
        this->m_ActivityId,
        this->m_State);
    }
    v15 = -1073741436;
  }
LABEL_15:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v18) = v15;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      this->m_ActivityId,
      62,
      (__int64)WPP_cd20a4d0a85c3838a9154e434950069a_Traceguids,
      (char)this,
      this->m_ActivityId,
      v18);
  }
  return v15;
}

```

## disassembly

```asm
0x140004c3c  push    rbx
0x140004c3e  push    rbp
0x140004c3f  push    rsi
0x140004c40  push    rdi
0x140004c41  push    r12
0x140004c43  push    r13
0x140004c45  push    r14
0x140004c47  push    r15
0x140004c49  sub     rsp, 48h
0x140004c4d  mov     r15d, edx
0x140004c50  mov     rsi, rcx
0x140004c53  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004c5a  xor     r12d, r12d
0x140004c5d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140004c64  lea     rdi, WPP_cd20a4d0a85c3838a9154e434950069a_Traceguids
0x140004c6b  jz      short loc_140004C89
0x140004c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c74  cmp     byte ptr [rcx+29h], 5
0x140004c78  jnb     loc_140004E98
0x140004c7e  cmp     [rcx+48h], r12w
0x140004c83  jnz     loc_140004E98
0x140004c89  mov     eax, [rsi+40h]
0x140004c8c  cmp     eax, 1
0x140004c8f  jnz     loc_140004D9D
0x140004c95  mov     r14, [rsi+80h]
0x140004c9c  lea     rdi, [rsi+0D0h]
0x140004ca3  mov     rbx, [rsi+20h]
0x140004ca7  mov     [rsi+40h], r12d
0x140004cab  test    rdi, rdi
0x140004cae  jz      loc_140004DE2
0x140004cb4  mov     bpl, r12b
0x140004cb7  test    rbx, rbx
0x140004cba  jz      loc_140004E3C
0x140004cc0  cmp     [rdi+2Dh], r12b
0x140004cc4  jnz     loc_140004E28
0x140004cca  mov     dword ptr [rdi+10h], 1
0x140004cd1  mov     [rdi+8], rbx
0x140004cd5  mov     [rdi+20h], r14
0x140004cd9  mov     [rdi+18h], rsi
0x140004cdd  mov     [rdi+28h], r15d
0x140004ce1  mov     rbp, [rbx+20h]
0x140004ce5  mov     rcx, rbp; SpinLock
0x140004ce8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004cef  nop     dword ptr [rax+rax+00h]
0x140004cf4  mov     byte ptr [rbp+10h], 1
0x140004cf8  lea     rcx, [rbx+40h]
0x140004cfc  mov     [rbp+8], al
0x140004cff  mov     byte ptr [rdi+2Dh], 1
0x140004d03  mov     rdx, [rcx+8]
0x140004d07  cmp     [rdx], rcx
0x140004d0a  jnz     loc_140004DB1
0x140004d10  lea     rax, [rdi+30h]
0x140004d14  mov     dil, r12b
0x140004d17  mov     [rax], rcx
0x140004d1a  mov     [rax+8], rdx
0x140004d1e  mov     [rdx], rax
0x140004d21  mov     [rcx+8], rax
0x140004d25  cmp     [rbx+30h], r12b
0x140004d29  jnz     short loc_140004D3F
0x140004d2b  mov     rax, gs:188h
0x140004d34  mov     dil, 1
0x140004d37  mov     [rbx+50h], rax
0x140004d3b  mov     byte ptr [rbx+30h], 1
0x140004d3f  mov     dl, [rbp+8]; NewIrql
0x140004d42  mov     rcx, rbp; SpinLock
0x140004d45  mov     [rbp+10h], r12b
0x140004d49  call    cs:__imp_KeReleaseSpinLock
0x140004d50  nop     dword ptr [rax+rax+00h]
0x140004d55  test    dil, dil
0x140004d58  jz      short loc_140004D62
0x140004d5a  mov     rcx, rbx; this
0x140004d5d  call    ?ProcessEventQueueUntilEmpty@EventQueue@@IEAAXXZ; EventQueue::ProcessEventQueueUntilEmpty(void)
0x140004d62  mov     ebx, r12d
0x140004d65  lea     rdi, WPP_cd20a4d0a85c3838a9154e434950069a_Traceguids
0x140004d6c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140004d73  jz      short loc_140004D89
0x140004d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d7c  cmp     byte ptr [rcx+29h], 5
0x140004d80  jnb     short loc_140004DB8
0x140004d82  cmp     [rcx+48h], r12w
0x140004d87  jnz     short loc_140004DB8
0x140004d89  mov     eax, ebx
0x140004d8b  add     rsp, 48h
0x140004d8f  pop     r15
0x140004d91  pop     r14
0x140004d93  pop     r13
0x140004d95  pop     r12
0x140004d97  pop     rdi
0x140004d98  pop     rsi
0x140004d99  pop     rbp
0x140004d9a  pop     rbx
0x140004d9b  retn
0x140004d9d  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140004da4  jnz     loc_140004EBF
0x140004daa  mov     ebx, 0C0000184h
0x140004daf  jmp     short loc_140004D6C
0x140004db1  mov     ecx, 3
0x140004db6  int     29h; Win8: RtlFailFast(ecx)
0x140004db8  mov     r8d, [rsi+10h]
0x140004dbc  mov     r9d, 3Eh ; '>'
0x140004dc2  mov     rcx, [rcx+40h]
0x140004dc6  mov     dl, 5
0x140004dc8  mov     dword ptr [rsp+88h+var_50], ebx
0x140004dcc  mov     [rsp+88h+var_58], r8d
0x140004dd1  mov     [rsp+88h+var_60], rsi
0x140004dd6  mov     [rsp+88h+var_68], rdi
0x140004ddb  call    WPP_RECORDER_SF_qDD
0x140004de0  jmp     short loc_140004D89
0x140004de2  mov     edx, 48h ; 'H'
0x140004de7  mov     r8d, 47696457h
0x140004ded  lea     ecx, [rdx-8]
0x140004df0  call    cs:__imp_ExAllocatePool2
0x140004df7  nop     dword ptr [rax+rax+00h]
0x140004dfc  test    rax, rax
0x140004dff  jz      short loc_140004E1E
0x140004e01  xor     r8d, r8d; unsigned int
0x140004e04  xor     edx, edx; bool
0x140004e06  mov     rcx, rax; this
0x140004e09  call    ??0Event@@QEAA@_NK@Z; Event::Event(bool,ulong)
0x140004e0e  mov     rdi, rax
0x140004e11  test    rax, rax
0x140004e14  jz      short loc_140004E1E
0x140004e16  mov     bpl, 1
0x140004e19  jmp     loc_140004CB7
0x140004e1e  mov     ebx, 0C000009Ah
0x140004e23  jmp     loc_140004D65
0x140004e28  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140004e2f  jnz     loc_140004EF1
0x140004e35  mov     ebx, 0C0000184h
0x140004e3a  jmp     short loc_140004E79
0x140004e3c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140004e43  jz      short loc_140004E74
0x140004e45  mov     eax, [rdi]
0x140004e47  mov     r9d, 0Ah
0x140004e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e54  mov     dl, 2
0x140004e56  mov     [rsp+88h+var_58], eax
0x140004e5a  lea     rax, WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids
0x140004e61  mov     [rsp+88h+var_60], rdi
0x140004e66  mov     [rsp+88h+var_68], rax
0x140004e6b  mov     rcx, [rcx+40h]
0x140004e6f  call    WPP_RECORDER_SF_qD
0x140004e74  mov     ebx, 0C000000Dh
0x140004e79  test    rdi, rdi
0x140004e7c  jz      loc_140004D65
0x140004e82  test    bpl, bpl
0x140004e85  jz      loc_140004D65
0x140004e8b  mov     rcx, rdi; void *
0x140004e8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004e93  jmp     loc_140004D65
0x140004e98  mov     eax, [rsi+10h]
0x140004e9b  mov     r9d, 3Ch ; '<'
0x140004ea1  mov     rcx, [rcx+40h]
0x140004ea5  mov     dl, 5
0x140004ea7  mov     [rsp+88h+var_58], eax
0x140004eab  mov     [rsp+88h+var_60], rsi
0x140004eb0  mov     [rsp+88h+var_68], rdi
0x140004eb5  call    WPP_RECORDER_SF_qD
0x140004eba  jmp     loc_140004C89
0x140004ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ec6  mov     r9d, 3Dh ; '='
0x140004ecc  mov     dword ptr [rsp+88h+var_50], eax
0x140004ed0  mov     dl, 2
0x140004ed2  mov     eax, [rsi+10h]
0x140004ed5  mov     [rsp+88h+var_58], eax
0x140004ed9  mov     rcx, [rcx+40h]
0x140004edd  mov     [rsp+88h+var_60], rsi
0x140004ee2  mov     [rsp+88h+var_68], rdi
0x140004ee7  call    WPP_RECORDER_SF_qDD
0x140004eec  jmp     loc_140004DAA
0x140004ef1  mov     eax, [rdi]
0x140004ef3  mov     r9d, 0Bh
0x140004ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f00  mov     dl, 2
0x140004f02  mov     [rsp+88h+var_58], eax
0x140004f06  lea     rax, WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids
0x140004f0d  mov     [rsp+88h+var_60], rdi
0x140004f12  mov     [rsp+88h+var_68], rax
0x140004f17  mov     rcx, [rcx+40h]
0x140004f1b  call    WPP_RECORDER_SF_qD
0x140004f20  jmp     loc_140004E35
```
