# DeviceCommandScheduler::OnActiveCommandCompleteHandler(int,bool)

- ea: `0x140003a78`
- end: `0x140003e8c`
- name: `?OnActiveCommandCompleteHandler@DeviceCommandScheduler@@IEAAXH_N@Z`
- size: `1044`
- prototype: `void __fastcall(DeviceCommandScheduler *__hidden this, int, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400036a0`
- `0x14000462c`

## callees

- `0x140003a78`
- `0x14000462c`
- `0x1400067b0`
- `0x14000bf04`
- `0x140023ae0`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140003bae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003bae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003b4e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003b4e`
- `ntoskrnl!ExAllocatePool2` at `0x140003cf1`
- `ntoskrnl!ExAllocatePool2` at `0x140003cf1`

## pseudocode

```c
void __fastcall DeviceCommandScheduler::OnActiveCommandCompleteHandler(
        DeviceCommandScheduler *this,
        struct _LIST_ENTRY *Flink,
        char a3)
{
  int v4; // ebp
  DeviceCommand *m_pActiveDeviceCommand; // rcx
  DeviceCommand *v7; // r14
  IOperationCompletionCallback *m_pCompletionCallback; // r12
  Event *p_m_FailsafeCompletionEvent; // rbx
  EventQueue *m_pEventQueue; // rdi
  char v11; // r15
  CNdisSpinLock *m_pEventQueueLock; // rbp
  KIRQL v13; // al
  struct _LIST_ENTRY *Blink; // rdx
  _CPP_LIST_ENTRY *p_m_Link; // rax
  char v16; // bl
  KIRQL OldIrql; // dl
  TimerRegistrationContext *m_pTimerRegistrationContext; // rbx
  int v19; // edx
  char v20; // r8
  Event *Pool2; // rax
  _LIST_ENTRY *p_m_DeviceCommandQueue; // rcx
  __int64 v23; // [rsp+28h] [rbp-60h]

  v4 = (int)Flink;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(Flink) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Flink,
      1,
      20,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids);
  }
  m_pActiveDeviceCommand = this->m_pActiveDeviceCommand;
  if ( m_pActiveDeviceCommand )
  {
    m_pActiveDeviceCommand->m_IsPending = 0;
    m_pActiveDeviceCommand->m_DebugCommandSubmitTime = MEMORY[0xFFFFF78000000014];
    v7 = this->m_pActiveDeviceCommand;
    this->m_pActiveDeviceCommand = 0;
    this->m_pActiveDeviceCommandId = 0;
    if ( !a3 )
    {
      m_pCompletionCallback = v7->m_pCompletionCallback;
      p_m_FailsafeCompletionEvent = &v7->m_FailsafeCompletionEvent;
      m_pEventQueue = this->m_pEventQueue;
      if ( v7 == (DeviceCommand *)-16LL )
      {
        Pool2 = (Event *)ExAllocatePool2(64, 72, 1198089303);
        if ( !Pool2 || (p_m_FailsafeCompletionEvent = Event::Event(Pool2, 0, 0)) == 0 )
        {
          v4 = -1073741670;
          goto LABEL_16;
        }
        v11 = 1;
      }
      else
      {
        v11 = 0;
      }
      if ( m_pEventQueue )
      {
        if ( !p_m_FailsafeCompletionEvent->m_IsPending )
        {
          p_m_FailsafeCompletionEvent->m_EventType = WiFiEventDeferredOperationCompletion;
          p_m_FailsafeCompletionEvent->m_pEventQueueCallback = m_pEventQueue;
          p_m_FailsafeCompletionEvent->m_EventPayload = (void *)m_pCompletionCallback;
          p_m_FailsafeCompletionEvent->m_SenderObject = v7;
          p_m_FailsafeCompletionEvent->m_EventStatus = v4;
          m_pEventQueueLock = m_pEventQueue->m_pEventQueueLock;
          v13 = KeAcquireSpinLockRaiseToDpc(&m_pEventQueueLock->m_SpinLock.SpinLock);
          m_pEventQueueLock->m_IsLocked = 1;
          m_pEventQueueLock->m_SpinLock.OldIrql = v13;
          p_m_FailsafeCompletionEvent->m_IsPending = 1;
          Blink = m_pEventQueue->m_EventQueue.Blink;
          if ( Blink->Flink == &m_pEventQueue->m_EventQueue )
          {
            p_m_Link = &p_m_FailsafeCompletionEvent->m_Link;
            v16 = 0;
            p_m_Link->ListEntry.Flink = &m_pEventQueue->m_EventQueue;
            p_m_Link->ListEntry.Blink = Blink;
            Blink->Flink = &p_m_Link->ListEntry;
            m_pEventQueue->m_EventQueue.Blink = &p_m_Link->ListEntry;
            if ( !m_pEventQueue->m_IsBeingProcessed )
            {
              v16 = 1;
              m_pEventQueue->m_EventQueueThreadHandle = KeGetCurrentThread();
              m_pEventQueue->m_IsBeingProcessed = 1;
            }
            OldIrql = m_pEventQueueLock->m_SpinLock.OldIrql;
            m_pEventQueueLock->m_IsLocked = 0;
            KeReleaseSpinLock(&m_pEventQueueLock->m_SpinLock.SpinLock, OldIrql);
            if ( v16 )
              EventQueue::ProcessEventQueueUntilEmpty(m_pEventQueue);
            v4 = 0;
            goto LABEL_16;
          }
LABEL_33:
          __fastfail(3u);
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(Flink) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Flink,
            a3,
            11,
            (__int64)WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids,
            (char)p_m_FailsafeCompletionEvent,
            p_m_FailsafeCompletionEvent->m_ActivityId);
        }
        v4 = -1073741436;
      }
      else
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(Flink) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Flink,
            a3,
            10,
            (__int64)WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids,
            (char)p_m_FailsafeCompletionEvent,
            p_m_FailsafeCompletionEvent->m_ActivityId);
        }
        v4 = -1073741811;
      }
      if ( p_m_FailsafeCompletionEvent && v11 )
        operator delete(p_m_FailsafeCompletionEvent);
LABEL_16:
      m_pTimerRegistrationContext = this->m_pTimerRegistrationContext;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(Flink) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Flink,
          1,
          35,
          (__int64)WPP_36443c01cfd9316cbec14010038208e6_Traceguids);
      }
      if ( m_pTimerRegistrationContext->m_pTimer->CancelTimer(m_pTimerRegistrationContext->m_pTimer) )
      {
        m_pTimerRegistrationContext->m_State = TimerRegistrationStateDone;
      }
      else
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        {
LABEL_24:
          DeviceCommandScheduler::OnIssueNextCommandHandler(this);
          goto LABEL_25;
        }
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v19) = 5;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v19,
            v20,
            20,
            (__int64)WPP_1ba47c57908f329c91e294622455b729_Traceguids,
            (char)m_pTimerRegistrationContext,
            m_pTimerRegistrationContext->m_ActivityId);
        }
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LODWORD(v23) = 0;
        LOBYTE(v19) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          1,
          36,
          (__int64)WPP_36443c01cfd9316cbec14010038208e6_Traceguids,
          v23);
      }
      goto LABEL_24;
    }
    p_m_DeviceCommandQueue = &this->m_DeviceCommandQueue;
    Flink = this->m_DeviceCommandQueue.Flink;
    if ( Flink->Blink == &this->m_DeviceCommandQueue )
    {
      v7->m_Link.ListEntry.Flink = Flink;
      v7->m_Link.ListEntry.Blink = p_m_DeviceCommandQueue;
      Flink->Blink = &v7->m_Link.ListEntry;
      p_m_DeviceCommandQueue->Flink = &v7->m_Link.ListEntry;
      goto LABEL_16;
    }
    goto LABEL_33;
  }
LABEL_25:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v23) = v4;
    LOBYTE(Flink) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Flink,
      1,
      21,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
      v23);
  }
}

```

## disassembly

```asm
0x140003a78  push    rbx
0x140003a7a  push    rbp
0x140003a7b  push    rsi
0x140003a7c  push    rdi
0x140003a7d  push    r12
0x140003a7f  push    r13
0x140003a81  push    r14
0x140003a83  push    r15
0x140003a85  sub     rsp, 48h
0x140003a89  mov     bl, r8b
0x140003a8c  mov     ebp, edx
0x140003a8e  mov     rsi, rcx
0x140003a91  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003a98  xor     r13d, r13d
0x140003a9b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140003aa2  lea     r14, WPP_2b7c372e88823a80955d729bf23dceec_Traceguids
0x140003aa9  mov     dil, 5
0x140003aac  jz      short loc_140003ACA
0x140003aae  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ab5  cmp     [rcx+29h], dil
0x140003ab9  jnb     loc_140003DEF
0x140003abf  cmp     [rcx+48h], r13w
0x140003ac4  jnz     loc_140003DEF
0x140003aca  mov     rcx, [rsi+28h]
0x140003ace  test    rcx, rcx
0x140003ad1  jz      loc_140003C55
0x140003ad7  mov     [rcx+0A6h], r13b
0x140003ade  mov     rax, 0FFFFF78000000014h
0x140003ae8  mov     rax, [rax]
0x140003aeb  mov     [rcx+0B0h], rax
0x140003af2  mov     r14, [rsi+28h]
0x140003af6  mov     [rsi+28h], r13
0x140003afa  mov     [rsi+38h], r13d
0x140003afe  test    bl, bl
0x140003b00  jnz     loc_140003DC7
0x140003b06  mov     r12, [r14+58h]
0x140003b0a  lea     rbx, [r14+10h]
0x140003b0e  mov     rdi, [rsi+20h]
0x140003b12  test    rbx, rbx
0x140003b15  jz      loc_140003CE3
0x140003b1b  mov     r15b, r13b
0x140003b1e  test    rdi, rdi
0x140003b21  jz      loc_140003D64
0x140003b27  cmp     [rbx+2Dh], r13b
0x140003b2b  jnz     loc_140003D49
0x140003b31  mov     dword ptr [rbx+10h], 1
0x140003b38  mov     [rbx+8], rdi
0x140003b3c  mov     [rbx+20h], r12
0x140003b40  mov     [rbx+18h], r14
0x140003b44  mov     [rbx+28h], ebp
0x140003b47  mov     rbp, [rdi+20h]
0x140003b4b  mov     rcx, rbp; SpinLock
0x140003b4e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003b55  nop     dword ptr [rax+rax+00h]
0x140003b5a  mov     byte ptr [rbp+10h], 1
0x140003b5e  lea     rcx, [rdi+40h]
0x140003b62  mov     [rbp+8], al
0x140003b65  mov     byte ptr [rbx+2Dh], 1
0x140003b69  mov     rdx, [rcx+8]
0x140003b6d  cmp     [rdx], rcx
0x140003b70  jnz     loc_140003CDC
0x140003b76  lea     rax, [rbx+30h]
0x140003b7a  mov     bl, r13b
0x140003b7d  mov     [rax], rcx
0x140003b80  mov     [rax+8], rdx
0x140003b84  mov     [rdx], rax
0x140003b87  mov     [rcx+8], rax
0x140003b8b  cmp     [rdi+30h], r13b
0x140003b8f  jnz     short loc_140003BA4
0x140003b91  mov     rax, gs:188h
0x140003b9a  mov     bl, 1
0x140003b9c  mov     [rdi+50h], rax
0x140003ba0  mov     byte ptr [rdi+30h], 1
0x140003ba4  mov     dl, [rbp+8]; NewIrql
0x140003ba7  mov     rcx, rbp; SpinLock
0x140003baa  mov     [rbp+10h], r13b
0x140003bae  call    cs:__imp_KeReleaseSpinLock
0x140003bb5  nop     dword ptr [rax+rax+00h]
0x140003bba  test    bl, bl
0x140003bbc  jz      short loc_140003BC6
0x140003bbe  mov     rcx, rdi; this
0x140003bc1  call    ?ProcessEventQueueUntilEmpty@EventQueue@@IEAAXXZ; EventQueue::ProcessEventQueueUntilEmpty(void)
0x140003bc6  mov     ebp, r13d
0x140003bc9  lea     r15, WPP_RECORDER_INITIALIZED
0x140003bd0  mov     dil, 5
0x140003bd3  mov     rbx, [rsi+0C0h]
0x140003bda  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003be1  lea     r14, WPP_36443c01cfd9316cbec14010038208e6_Traceguids
0x140003be8  jz      short loc_140003C06
0x140003bea  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bf1  cmp     [rcx+29h], dil
0x140003bf5  jnb     loc_140003D1F
0x140003bfb  cmp     [rcx+48h], r13w
0x140003c00  jnz     loc_140003D1F
0x140003c06  mov     rcx, [rbx+30h]
0x140003c0a  mov     rax, [rcx]
0x140003c0d  mov     rax, [rax+18h]
0x140003c11  call    _guard_dispatch_icall
0x140003c16  test    al, al
0x140003c18  jz      short loc_140003C8C
0x140003c1a  mov     dword ptr [rbx+2Ch], 3
0x140003c21  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003c28  jz      short loc_140003C46
0x140003c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c31  cmp     [rcx+29h], dil
0x140003c35  jnb     loc_140003E43
0x140003c3b  cmp     [rcx+48h], r13w
0x140003c40  jnz     loc_140003E43
0x140003c46  mov     rcx, rsi; this
0x140003c49  call    ?OnIssueNextCommandHandler@DeviceCommandScheduler@@IEAAXXZ; DeviceCommandScheduler::OnIssueNextCommandHandler(void)
0x140003c4e  lea     r14, WPP_2b7c372e88823a80955d729bf23dceec_Traceguids
0x140003c55  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003c5c  jz      short loc_140003C7A
0x140003c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c65  cmp     [rcx+29h], dil
0x140003c69  jnb     loc_140003E68
0x140003c6f  cmp     [rcx+48h], r13w
0x140003c74  jnz     loc_140003E68
0x140003c7a  add     rsp, 48h
0x140003c7e  pop     r15
0x140003c80  pop     r14
0x140003c82  pop     r13
0x140003c84  pop     r12
0x140003c86  pop     rdi
0x140003c87  pop     rsi
0x140003c88  pop     rbp
0x140003c89  pop     rbx
0x140003c8a  retn
0x140003c8c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003c93  jz      short loc_140003C46
0x140003c95  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c9c  cmp     [rcx+29h], dil
0x140003ca0  jnb     short loc_140003CAD
0x140003ca2  cmp     [rcx+48h], r13w
0x140003ca7  jz      loc_140003C21
0x140003cad  mov     eax, [rbx+8]
0x140003cb0  mov     r9d, 14h
0x140003cb6  mov     rcx, [rcx+40h]
0x140003cba  mov     dl, dil
0x140003cbd  mov     [rsp+88h+var_58], eax
0x140003cc1  lea     rax, WPP_1ba47c57908f329c91e294622455b729_Traceguids
0x140003cc8  mov     [rsp+88h+var_60], rbx
0x140003ccd  mov     [rsp+88h+var_68], rax
0x140003cd2  call    WPP_RECORDER_SF_qD
0x140003cd7  jmp     loc_140003C21
0x140003cdc  mov     ecx, 3
0x140003ce1  int     29h; Win8: RtlFailFast(ecx)
0x140003ce3  mov     edx, 48h ; 'H'
0x140003ce8  mov     r8d, 47696457h
0x140003cee  lea     ecx, [rdx-8]
0x140003cf1  call    cs:__imp_ExAllocatePool2
0x140003cf8  nop     dword ptr [rax+rax+00h]
0x140003cfd  test    rax, rax
0x140003d00  jz      short loc_140003D3F
0x140003d02  xor     r8d, r8d; unsigned int
0x140003d05  xor     edx, edx; bool
0x140003d07  mov     rcx, rax; this
0x140003d0a  call    ??0Event@@QEAA@_NK@Z; Event::Event(bool,ulong)
0x140003d0f  mov     rbx, rax
0x140003d12  test    rax, rax
0x140003d15  jz      short loc_140003D3F
0x140003d17  mov     r15b, 1
0x140003d1a  jmp     loc_140003B1E
0x140003d1f  mov     rcx, [rcx+40h]
0x140003d23  mov     r9d, 23h ; '#'
0x140003d29  mov     dl, dil
0x140003d2c  mov     [rsp+88h+var_68], r14
0x140003d31  lea     r8d, [r9-22h]
0x140003d35  call    WPP_RECORDER_SF_
0x140003d3a  jmp     loc_140003C06
0x140003d3f  mov     ebp, 0C000009Ah
0x140003d44  jmp     loc_140003BD0
0x140003d49  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003d50  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003d57  jnz     loc_140003E0F
0x140003d5d  mov     ebp, 0C0000184h
0x140003d62  jmp     short loc_140003DA8
0x140003d64  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003d6b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003d72  jz      short loc_140003DA3
0x140003d74  mov     eax, [rbx]
0x140003d76  mov     r9d, 0Ah
0x140003d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d83  mov     dl, 2
0x140003d85  mov     [rsp+88h+var_58], eax
0x140003d89  lea     rax, WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids
0x140003d90  mov     [rsp+88h+var_60], rbx
0x140003d95  mov     [rsp+88h+var_68], rax
0x140003d9a  mov     rcx, [rcx+40h]
0x140003d9e  call    WPP_RECORDER_SF_qD
0x140003da3  mov     ebp, 0C000000Dh
0x140003da8  test    rbx, rbx
0x140003dab  jz      loc_140003BC9
0x140003db1  test    r15b, r15b
0x140003db4  jz      loc_140003BC9
0x140003dba  mov     rcx, rbx; void *
0x140003dbd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003dc2  jmp     loc_140003BC9
0x140003dc7  lea     rcx, [rsi+40h]
0x140003dcb  mov     rdx, [rcx]
0x140003dce  cmp     [rdx+8], rcx
0x140003dd2  jnz     loc_140003CDC
0x140003dd8  lea     rax, [r14+68h]
0x140003ddc  mov     [rax], rdx
0x140003ddf  mov     [rax+8], rcx
0x140003de3  mov     [rdx+8], rax
0x140003de7  mov     [rcx], rax
0x140003dea  jmp     loc_140003BD3
0x140003def  mov     rcx, [rcx+40h]
0x140003df3  mov     r9d, 14h
0x140003df9  mov     dl, dil
0x140003dfc  mov     [rsp+88h+var_68], r14
0x140003e01  lea     r8d, [r9-13h]
0x140003e05  call    WPP_RECORDER_SF_
0x140003e0a  jmp     loc_140003ACA
0x140003e0f  mov     eax, [rbx]
0x140003e11  mov     r9d, 0Bh
0x140003e17  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e1e  mov     dl, 2
0x140003e20  mov     [rsp+88h+var_58], eax
0x140003e24  lea     rax, WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids
0x140003e2b  mov     [rsp+88h+var_60], rbx
0x140003e30  mov     [rsp+88h+var_68], rax
0x140003e35  mov     rcx, [rcx+40h]
0x140003e39  call    WPP_RECORDER_SF_qD
0x140003e3e  jmp     loc_140003D5D
0x140003e43  mov     rcx, [rcx+40h]
0x140003e47  mov     r9d, 24h ; '$'
0x140003e4d  mov     dword ptr [rsp+88h+var_60], r13d
0x140003e52  mov     dl, dil
0x140003e55  mov     [rsp+88h+var_68], r14
0x140003e5a  lea     r8d, [r9-23h]
0x140003e5e  call    WPP_RECORDER_SF_D
0x140003e63  jmp     loc_140003C46
0x140003e68  mov     rcx, [rcx+40h]
0x140003e6c  mov     r9d, 15h
0x140003e72  mov     dword ptr [rsp+88h+var_60], ebp
0x140003e76  mov     dl, dil
0x140003e79  mov     [rsp+88h+var_68], r14
0x140003e7e  lea     r8d, [r9-14h]
0x140003e82  call    WPP_RECORDER_SF_D
0x140003e87  jmp     loc_140003C7A
```
