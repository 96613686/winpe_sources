# ActiveJobsList::StartAddNewJob(CJobBase *,IOperationCompletionCallback *)

- ea: `0x140005888`
- end: `0x140005b0f`
- name: `?StartAddNewJob@ActiveJobsList@@QEAAHPEAVCJobBase@@PEAVIOperationCompletionCallback@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(ActiveJobsList *__hidden this, struct CJobBase *, struct IOperationCompletionCallback *)`
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004a7c`
- `0x140006b50`
- `0x1400278fc`
- `0x140045aa4`
- `0x14004b814`
- `0x14004ca0c`
- `0x140064268`
- `0x1400886f0`

## callees

- `0x140005888`
- `0x1400067b0`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400059cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400059cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000596f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000596f`

## pseudocode

```c
__int64 __fastcall ActiveJobsList::StartAddNewJob(
        ActiveJobsList *this,
        struct CJobBase *a2,
        struct IOperationCompletionCallback *a3)
{
  struct CJobBase *v4; // rdi
  INdisConversion *m_pNdisConversion; // rcx
  unsigned int v7; // ebx
  Event *p_m_FailsafeJobCompletionEvent; // rbx
  EventQueue *m_pEventQueue; // rdi
  CNdisSpinLock *m_pEventQueueLock; // rsi
  KIRQL v11; // al
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY *p_ListEntry; // rax
  char v14; // bl
  KIRQL OldIrql; // dl
  __int64 v17; // [rsp+28h] [rbp-50h]

  v4 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      12,
      (__int64)WPP_b165a5fed1903a28339a5652b438d090_Traceguids);
  }
  if ( !v4 || !a3 )
    goto LABEL_29;
  if ( !v4->m_AllowInLowPower )
  {
    m_pNdisConversion = v4->m_pNdisConversion;
    if ( m_pNdisConversion )
    {
      if ( !m_pNdisConversion->IsOperationalPowerState(m_pNdisConversion) )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a2,
            1,
            13,
            (__int64)WPP_b165a5fed1903a28339a5652b438d090_Traceguids);
        }
LABEL_11:
        v7 = -1073741436;
        goto LABEL_20;
      }
    }
  }
  v4->m_pActiveJobCompletionCallback = a3;
  p_m_FailsafeJobCompletionEvent = &v4->m_FailsafeJobCompletionEvent;
  a2 = (struct CJobBase *)((unsigned __int64)&this->IEventQueueCallback
                         & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  if ( !a2 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        10,
        (__int64)WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids,
        (_BYTE)v4 - 48,
        p_m_FailsafeJobCompletionEvent->m_ActivityId);
    }
LABEL_29:
    v7 = -1073741811;
    goto LABEL_20;
  }
  if ( v4->m_FailsafeJobCompletionEvent.m_IsPending )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        11,
        (__int64)WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids,
        (_BYTE)v4 - 48,
        p_m_FailsafeJobCompletionEvent->m_ActivityId);
    }
    goto LABEL_11;
  }
  v4->m_FailsafeJobCompletionEvent.m_EventType = WiFiEventAddActiveJob;
  v4->m_FailsafeJobCompletionEvent.m_pEventQueueCallback = (IEventQueueCallback *)a2;
  v4->m_FailsafeJobCompletionEvent.m_EventPayload = v4;
  v4->m_FailsafeJobCompletionEvent.m_SenderObject = 0;
  v4->m_FailsafeJobCompletionEvent.m_EventStatus = 0;
  m_pEventQueue = this->m_pEventQueue;
  m_pEventQueueLock = m_pEventQueue->m_pEventQueueLock;
  v11 = KeAcquireSpinLockRaiseToDpc(&m_pEventQueueLock->m_SpinLock.SpinLock);
  m_pEventQueueLock->m_IsLocked = 1;
  m_pEventQueueLock->m_SpinLock.OldIrql = v11;
  p_m_FailsafeJobCompletionEvent->m_IsPending = 1;
  Blink = m_pEventQueue->m_EventQueue.Blink;
  if ( Blink->Flink != &m_pEventQueue->m_EventQueue )
    __fastfail(3u);
  p_ListEntry = &p_m_FailsafeJobCompletionEvent->m_Link.ListEntry;
  v14 = 0;
  p_ListEntry->Flink = &m_pEventQueue->m_EventQueue;
  p_ListEntry->Blink = Blink;
  Blink->Flink = p_ListEntry;
  m_pEventQueue->m_EventQueue.Blink = p_ListEntry;
  if ( !m_pEventQueue->m_IsBeingProcessed )
  {
    v14 = 1;
    m_pEventQueue->m_EventQueueThreadHandle = KeGetCurrentThread();
    m_pEventQueue->m_IsBeingProcessed = 1;
  }
  OldIrql = m_pEventQueueLock->m_SpinLock.OldIrql;
  m_pEventQueueLock->m_IsLocked = 0;
  KeReleaseSpinLock(&m_pEventQueueLock->m_SpinLock.SpinLock, OldIrql);
  if ( v14 )
    EventQueue::ProcessEventQueueUntilEmpty(m_pEventQueue);
  v7 = 0;
LABEL_20:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v17) = v7;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      14,
      (__int64)WPP_b165a5fed1903a28339a5652b438d090_Traceguids,
      v17);
  }
  return v7;
}

```

## disassembly

```asm
0x140005888  push    rbx
0x14000588a  push    rbp
0x14000588b  push    rsi
0x14000588c  push    rdi
0x14000588d  push    r12
0x14000588f  push    r14
0x140005891  sub     rsp, 48h
0x140005895  mov     rbx, r8
0x140005898  mov     rdi, rdx
0x14000589b  mov     rsi, rcx
0x14000589e  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400058a5  xor     ebp, ebp
0x1400058a7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400058ae  lea     r12, WPP_b165a5fed1903a28339a5652b438d090_Traceguids
0x1400058b5  jz      short loc_1400058D2
0x1400058b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400058be  cmp     byte ptr [rcx+29h], 5
0x1400058c2  jnb     loc_140005AA7
0x1400058c8  cmp     [rcx+48h], bp
0x1400058cc  jnz     loc_140005AA7
0x1400058d2  test    rdi, rdi
0x1400058d5  jz      loc_140005A9D
0x1400058db  test    rbx, rbx
0x1400058de  jz      loc_140005A9D
0x1400058e4  cmp     [rdi+1FAh], bpl
0x1400058eb  jnz     short loc_140005920
0x1400058ed  mov     rcx, [rdi+1E8h]
0x1400058f4  test    rcx, rcx
0x1400058f7  jz      short loc_140005920
0x1400058f9  mov     rax, [rcx]
0x1400058fc  mov     rax, [rax+10h]
0x140005900  call    _guard_dispatch_icall
0x140005905  test    al, al
0x140005907  jnz     short loc_140005920
0x140005909  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140005910  jnz     loc_140005AC6
0x140005916  mov     ebx, 0C0000184h
0x14000591b  jmp     loc_1400059E9
0x140005920  mov     [rdi+1C0h], rbx
0x140005927  lea     rbx, [rdi+0D0h]
0x14000592e  mov     rax, rsi
0x140005931  lea     rcx, [rsi+8]
0x140005935  neg     rax
0x140005938  sbb     rdx, rdx
0x14000593b  and     rdx, rcx
0x14000593e  jz      loc_140005A65
0x140005944  cmp     [rbx+2Dh], bpl
0x140005948  jnz     loc_140005A24
0x14000594e  mov     dword ptr [rbx+10h], 4
0x140005955  mov     [rbx+8], rdx
0x140005959  mov     [rbx+20h], rdi
0x14000595d  mov     [rbx+18h], rbp
0x140005961  mov     [rbx+28h], ebp
0x140005964  mov     rdi, [rsi+10h]
0x140005968  mov     rsi, [rdi+20h]
0x14000596c  mov     rcx, rsi; SpinLock
0x14000596f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005976  nop     dword ptr [rax+rax+00h]
0x14000597b  mov     byte ptr [rsi+10h], 1
0x14000597f  lea     rcx, [rdi+40h]
0x140005983  mov     [rsi+8], al
0x140005986  mov     byte ptr [rbx+2Dh], 1
0x14000598a  mov     rdx, [rcx+8]
0x14000598e  cmp     [rdx], rcx
0x140005991  jnz     loc_140005A1D
0x140005997  lea     rax, [rbx+30h]
0x14000599b  mov     bl, bpl
0x14000599e  mov     [rax], rcx
0x1400059a1  mov     [rax+8], rdx
0x1400059a5  mov     [rdx], rax
0x1400059a8  mov     [rcx+8], rax
0x1400059ac  cmp     [rdi+30h], bpl
0x1400059b0  jnz     short loc_1400059C5
0x1400059b2  mov     rax, gs:188h
0x1400059bb  mov     bl, 1
0x1400059bd  mov     [rdi+50h], rax
0x1400059c1  mov     byte ptr [rdi+30h], 1
0x1400059c5  mov     dl, [rsi+8]; NewIrql
0x1400059c8  mov     rcx, rsi; SpinLock
0x1400059cb  mov     [rsi+10h], bpl
0x1400059cf  call    cs:__imp_KeReleaseSpinLock
0x1400059d6  nop     dword ptr [rax+rax+00h]
0x1400059db  test    bl, bl
0x1400059dd  jz      short loc_1400059E7
0x1400059df  mov     rcx, rdi; this
0x1400059e2  call    ?ProcessEventQueueUntilEmpty@EventQueue@@IEAAXXZ; EventQueue::ProcessEventQueueUntilEmpty(void)
0x1400059e7  mov     ebx, ebp
0x1400059e9  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400059f0  jz      short loc_140005A0D
0x1400059f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059f9  cmp     byte ptr [rcx+29h], 5
0x1400059fd  jnb     loc_140005AEC
0x140005a03  cmp     [rcx+48h], bp
0x140005a07  jnz     loc_140005AEC
0x140005a0d  mov     eax, ebx
0x140005a0f  add     rsp, 48h
0x140005a13  pop     r14
0x140005a15  pop     r12
0x140005a17  pop     rdi
0x140005a18  pop     rsi
0x140005a19  pop     rbp
0x140005a1a  pop     rbx
0x140005a1b  retn
0x140005a1d  mov     ecx, 3
0x140005a22  int     29h; Win8: RtlFailFast(ecx)
0x140005a24  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140005a2b  jz      loc_140005916
0x140005a31  mov     eax, [rbx]
0x140005a33  mov     r9d, 0Bh
0x140005a39  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a40  mov     dl, 2
0x140005a42  mov     [rsp+78h+var_48], eax
0x140005a46  lea     rax, WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids
0x140005a4d  mov     [rsp+78h+var_50], rbx
0x140005a52  mov     [rsp+78h+var_58], rax
0x140005a57  mov     rcx, [rcx+40h]
0x140005a5b  call    WPP_RECORDER_SF_qD
0x140005a60  jmp     loc_140005916
0x140005a65  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140005a6c  jz      short loc_140005A9D
0x140005a6e  mov     eax, [rbx]
0x140005a70  mov     r9d, 0Ah
0x140005a76  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a7d  mov     dl, 2
0x140005a7f  mov     [rsp+78h+var_48], eax
0x140005a83  lea     rax, WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids
0x140005a8a  mov     [rsp+78h+var_50], rbx
0x140005a8f  mov     [rsp+78h+var_58], rax
0x140005a94  mov     rcx, [rcx+40h]
0x140005a98  call    WPP_RECORDER_SF_qD
0x140005a9d  mov     ebx, 0C000000Dh
0x140005aa2  jmp     loc_1400059E9
0x140005aa7  mov     rcx, [rcx+40h]
0x140005aab  mov     r9d, 0Ch
0x140005ab1  mov     dl, 5
0x140005ab3  mov     [rsp+78h+var_58], r12
0x140005ab8  lea     r8d, [r9-0Bh]
0x140005abc  call    WPP_RECORDER_SF_
0x140005ac1  jmp     loc_1400058D2
0x140005ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x140005acd  mov     r9d, 0Dh
0x140005ad3  mov     dl, 2
0x140005ad5  mov     [rsp+78h+var_58], r12
0x140005ada  mov     rcx, [rcx+40h]
0x140005ade  lea     r8d, [r9-0Ch]
0x140005ae2  call    WPP_RECORDER_SF_
0x140005ae7  jmp     loc_140005916
0x140005aec  mov     rcx, [rcx+40h]
0x140005af0  mov     r9d, 0Eh
0x140005af6  mov     dword ptr [rsp+78h+var_50], ebx
0x140005afa  mov     dl, 5
0x140005afc  mov     [rsp+78h+var_58], r12
0x140005b01  lea     r8d, [r9-0Dh]
0x140005b05  call    WPP_RECORDER_SF_D
0x140005b0a  jmp     loc_140005A0D
```
