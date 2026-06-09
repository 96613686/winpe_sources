# DeviceCommandScheduler::ProcessCtlPlaneSendCommandCompleteEvent(ulong,_WFC_MESSAGE_METADATA *,IWdiMessageMemoryManager *)

- ea: `0x1400034dc`
- end: `0x14000369a`
- name: `?ProcessCtlPlaneSendCommandCompleteEvent@DeviceCommandScheduler@@IEAAXKPEAU_WFC_MESSAGE_METADATA@@PEAVIWdiMessageMemoryManager@@@Z`
- size: `446`
- prototype: `void __fastcall(DeviceCommandScheduler *__hidden this, unsigned int, struct _WFC_MESSAGE_METADATA *, struct IWdiMessageMemoryManager *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003470`

## callees

- `0x1400034dc`
- `0x1400036a0`
- `0x140012214`
- `0x140017a90`
- `0x140034e04`
- `0x140034ec4`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140003685`
- `ntoskrnl!DbgPrintEx` at `0x140003685`

## string_xrefs

- `0x14000367a`: `HungCommand id %d finally returned, drop it\n`

## pseudocode

```c
void __fastcall DeviceCommandScheduler::ProcessCtlPlaneSendCommandCompleteEvent(
        DeviceCommandScheduler *this,
        unsigned int a2,
        struct _WFC_MESSAGE_METADATA *a3,
        struct IWdiMessageMemoryManager *a4)
{
  unsigned int v6; // ebp
  EventQueue *m_pEventQueue; // rcx
  unsigned int m_HungCommandToken; // eax
  __int64 v10; // [rsp+28h] [rbp-50h]

  v6 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      26,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids);
  }
  m_pEventQueue = this->m_pEventQueue;
  LOBYTE(a2) = 4;
  if ( m_pEventQueue->m_HungResetRecoveryIterations
    && (*((_DWORD *)a3 + 2) & 4) == 0
    && (++m_pEventQueue->m_CountCommandsToLe,
        this->m_pEventQueue->m_HungAtWdiCommandPasses == m_pEventQueue->m_CountCommandsToLe) )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        27,
        (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
        a3->MessageId,
        a3->MessageType);
    }
  }
  else if ( this->m_pAdapter->m_lResetRecovery > 0
         && (m_HungCommandToken = this->m_HungCommandToken) != 0
         && a3->Message.TransactionId == m_HungCommandToken )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        28,
        (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
        this->m_HungCommandToken);
    DbgPrintEx(0, 0, "HungCommand id %d finally returned, drop it\n", this->m_HungCommandToken);
    this->m_HungCommandToken = 0;
  }
  else
  {
    DeviceCommandScheduler::CompleteSendCommand_PostHangCheck(this, v6, a3);
  }
  if ( a4 )
    a4->FreeMemory(a4, (unsigned __int8 *)a3);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v10) = 0;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      29,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
      v10);
  }
}

```

## disassembly

```asm
0x1400034dc  push    rbx
0x1400034de  push    rbp
0x1400034df  push    rsi
0x1400034e0  push    rdi
0x1400034e1  push    r12
0x1400034e3  push    r14
0x1400034e5  push    r15
0x1400034e7  sub     rsp, 40h
0x1400034eb  mov     rsi, r9
0x1400034ee  mov     rdi, r8
0x1400034f1  mov     ebp, edx
0x1400034f3  mov     rbx, rcx
0x1400034f6  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400034fd  xor     r14d, r14d
0x140003500  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140003507  lea     r12, WPP_2b7c372e88823a80955d729bf23dceec_Traceguids
0x14000350e  jz      short loc_14000352C
0x140003510  mov     rcx, cs:WPP_GLOBAL_Control
0x140003517  cmp     byte ptr [rcx+29h], 5
0x14000351b  jnb     loc_1400035C1
0x140003521  cmp     [rcx+48h], r14w
0x140003526  jnz     loc_1400035C1
0x14000352c  mov     rcx, [rbx+20h]
0x140003530  mov     dl, 4
0x140003532  cmp     [rcx+10h], r14d
0x140003536  jnz     loc_1400035E0
0x14000353c  mov     rax, [rbx+0B0h]
0x140003543  cmp     [rax+15C8h], r14d
0x14000354a  jg      loc_14000363A
0x140003550  mov     r8, rdi; struct _WFC_MESSAGE_METADATA *
0x140003553  mov     edx, ebp; unsigned int
0x140003555  mov     rcx, rbx; this
0x140003558  call    ?CompleteSendCommand_PostHangCheck@DeviceCommandScheduler@@IEAAXKPEAU_WFC_MESSAGE_METADATA@@@Z; DeviceCommandScheduler::CompleteSendCommand_PostHangCheck(ulong,_WFC_MESSAGE_METADATA *)
0x14000355d  test    rsi, rsi
0x140003560  jz      short loc_140003573
0x140003562  mov     rax, [rsi]
0x140003565  mov     rdx, rdi
0x140003568  mov     rcx, rsi
0x14000356b  mov     rax, [rax]
0x14000356e  call    _guard_dispatch_icall
0x140003573  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000357a  jz      short loc_140003590
0x14000357c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003583  cmp     byte ptr [rcx+29h], 5
0x140003587  jnb     short loc_1400035A0
0x140003589  cmp     [rcx+48h], r14w
0x14000358e  jnz     short loc_1400035A0
0x140003590  add     rsp, 40h
0x140003594  pop     r15
0x140003596  pop     r14
0x140003598  pop     r12
0x14000359a  pop     rdi
0x14000359b  pop     rsi
0x14000359c  pop     rbp
0x14000359d  pop     rbx
0x14000359e  retn
0x1400035a0  mov     rcx, [rcx+40h]
0x1400035a4  mov     r9d, 1Dh
0x1400035aa  mov     dword ptr [rsp+78h+var_50], r14d
0x1400035af  mov     dl, 5
0x1400035b1  mov     [rsp+78h+var_58], r12
0x1400035b6  lea     r8d, [r9-1Ch]
0x1400035ba  call    WPP_RECORDER_SF_D
0x1400035bf  jmp     short loc_140003590
0x1400035c1  mov     rcx, [rcx+40h]
0x1400035c5  mov     r9d, 1Ah
0x1400035cb  mov     dl, 5
0x1400035cd  mov     [rsp+78h+var_58], r12
0x1400035d2  lea     r8d, [r9-19h]
0x1400035d6  call    WPP_RECORDER_SF_
0x1400035db  jmp     loc_14000352C
0x1400035e0  mov     eax, [rdi+8]
0x1400035e3  test    dl, al
0x1400035e5  jnz     loc_14000353C
0x1400035eb  inc     dword ptr [rcx+18h]
0x1400035ee  mov     rax, [rbx+20h]
0x1400035f2  mov     ecx, [rcx+18h]
0x1400035f5  cmp     [rax+14h], ecx
0x1400035f8  jnz     loc_14000353C
0x1400035fe  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003605  jz      loc_14000355D
0x14000360b  mov     eax, [rdi+0Ch]
0x14000360e  mov     r9d, 1Bh
0x140003614  mov     rcx, cs:WPP_GLOBAL_Control
0x14000361b  mov     dl, 2
0x14000361d  mov     [rsp+78h+var_48], eax
0x140003621  mov     eax, [rdi]
0x140003623  mov     dword ptr [rsp+78h+var_50], eax
0x140003627  mov     rcx, [rcx+40h]
0x14000362b  mov     [rsp+78h+var_58], r12
0x140003630  call    WPP_RECORDER_SF_Ld
0x140003635  jmp     loc_14000355D
0x14000363a  mov     eax, [rbx+34h]
0x14000363d  test    eax, eax
0x14000363f  jz      loc_140003550
0x140003645  cmp     [rdi+28h], eax
0x140003648  jnz     loc_140003550
0x14000364e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003655  jz      short loc_140003676
0x140003657  mov     rcx, cs:WPP_GLOBAL_Control
0x14000365e  mov     r9d, 1Ch
0x140003664  mov     dword ptr [rsp+78h+var_50], eax
0x140003668  mov     [rsp+78h+var_58], r12
0x14000366d  mov     rcx, [rcx+40h]
0x140003671  call    WPP_RECORDER_SF_d
0x140003676  mov     r9d, [rbx+34h]
0x14000367a  lea     r8, Format; "HungCommand id %d finally returned, dro"...
0x140003681  xor     edx, edx; Level
0x140003683  xor     ecx, ecx; ComponentId
0x140003685  call    cs:__imp_DbgPrintEx
0x14000368c  nop     dword ptr [rax+rax+00h]
0x140003691  mov     [rbx+34h], r14d
0x140003695  jmp     loc_14000355D
```
