# ReceiveQueue::ReturnUrbToPool(_URB *)

- ea: `0x1400025e4`
- end: `0x140002730`
- name: `?ReturnUrbToPool@ReceiveQueue@@AEAAXPEAU_URB@@@Z`
- size: `332`
- prototype: `void __fastcall(ReceiveQueue *__hidden this, struct _URB *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001f44`
- `0x140002234`

## callees

- `0x14000187c`
- `0x1400025c0`
- `0x1400025e4`
- `0x140002a94`
- `0x14000c9fc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002606`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002606`
- `ntoskrnl!ExFreePool` at `0x1400026e4`
- `ntoskrnl!ExFreePool` at `0x1400026e4`

## pseudocode

```c
void __fastcall ReceiveQueue::ReturnUrbToPool(ReceiveQueue *this, struct _URB *a2)
{
  unsigned __int64 *v2; // rsi
  KIRQL v5; // al
  void *ConfigurationHandle; // rcx
  unsigned __int8 v7; // r14
  int v8; // ecx
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  struct wil::details::kspin_lock_saved_irql v12; // [rsp+50h] [rbp-10h] BYREF
  PVOID P; // [rsp+80h] [rbp+20h] BYREF

  v2 = (unsigned __int64 *)((char *)this + 40);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
  ConfigurationHandle = a2->UrbSelectInterface.ConfigurationHandle;
  v7 = v5;
  P = a2;
  if ( ConfigurationHandle == *((void **)this + 3) )
  {
    v8 = *((_DWORD *)this + 18);
    if ( v8 )
      *((_DWORD *)this + 18) = v8 - 1;
    else
      MicrosoftTelemetryAssertTriggeredMsgKM("Pending interrupt transfer count underrun.");
  }
  else
  {
    if ( ConfigurationHandle != *((void **)this + 4) )
      MicrosoftTelemetryAssertTriggeredMsgKM("Unknown pipe handle in URB.");
    v9 = *((_DWORD *)this + 19);
    if ( v9 )
      *((_DWORD *)this + 19) = v9 - 1;
    else
      MicrosoftTelemetryAssertTriggeredMsgKM("Pending bulk transfer count underrun.");
  }
  if ( !utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::push_back(
          (__int64 *)this + 6,
          (__int64 *)&P) )
  {
    LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      v11,
      *(_QWORD *)(*((_QWORD *)this + 1) + 8LL),
      2,
      1,
      22,
      (__int64)WPP_86e0affdec483798a987f478d619ae67_Traceguids,
      **((_QWORD **)this + 1));
    MicrosoftTelemetryAssertTriggeredMsgKM("Failed to return URB to pool.");
  }
  if ( P )
    ExFreePool(P);
  if ( v2 )
  {
    v12.spinLock = v2;
    v12.savedIrql = v7;
    wil::details::kspin_lock_saved_irql::Release(&v12);
  }
}

```

## disassembly

```asm
0x1400025e4  mov     [rsp-18h+arg_8], rbx
0x1400025e9  mov     [rsp-18h+arg_10], rsi
0x1400025ee  push    rbp
0x1400025ef  push    rdi
0x1400025f0  push    r14
0x1400025f2  mov     rbp, rsp
0x1400025f5  sub     rsp, 60h
0x1400025f9  lea     rsi, [rcx+28h]
0x1400025fd  mov     rdi, rcx
0x140002600  mov     rcx, rsi; SpinLock
0x140002603  mov     rbx, rdx
0x140002606  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000260d  nop     dword ptr [rax+rax+00h]
0x140002612  mov     rcx, [rbx+18h]
0x140002616  mov     r14b, al
0x140002619  mov     [rbp+P], rbx
0x14000261d  cmp     rcx, [rdi+18h]
0x140002621  jnz     short loc_14000263F
0x140002623  mov     ecx, [rdi+48h]
0x140002626  test    ecx, ecx
0x140002628  jz      short loc_140002631
0x14000262a  dec     ecx
0x14000262c  mov     [rdi+48h], ecx
0x14000262f  jmp     short loc_14000266B
0x140002631  lea     rcx, aPendingInterru; __annotation("Debug", "TelemetryAssert", "false", "Pending interrupt transfer count underrun.")
0x140002638  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14000263d  jmp     short loc_14000266B
0x14000263f  cmp     rcx, [rdi+20h]
0x140002643  jz      short loc_140002651
0x140002645  lea     rcx, aUnknownPipeHan; __annotation("Debug", "TelemetryAssert", "urb->UrbBulkOrInterruptTransfer.PipeHandle == m_bulkInPipe", "Unknown pipe handle in URB.")
0x14000264c  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140002651  mov     eax, [rdi+4Ch]
0x140002654  test    eax, eax
0x140002656  jz      short loc_14000265F
0x140002658  dec     eax
0x14000265a  mov     [rdi+4Ch], eax
0x14000265d  jmp     short loc_14000266B
0x14000265f  lea     rcx, aPendingBulkTra; __annotation("Debug", "TelemetryAssert", "false", "Pending bulk transfer count underrun.")
0x140002666  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14000266b  lea     rcx, [rdi+30h]
0x14000266f  lea     rdx, [rbp+P]
0x140002673  call    ?push_back@?$vector@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@V?$allocator@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@2@@Z; utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::push_back(utl::unique_ptr<_URB,utl::default_delete<_URB>> &&)
0x140002678  test    al, al
0x14000267a  jnz     short loc_1400026DB
0x14000267c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002683  mov     eax, [rcx+2Ch]
0x140002686  test    al, 1
0x140002688  jz      short loc_140002694
0x14000268a  cmp     byte ptr [rcx+29h], 2
0x14000268e  jb      short loc_140002694
0x140002690  mov     dl, 1
0x140002692  jmp     short loc_140002696
0x140002694  xor     dl, dl
0x140002696  mov     r9, [rdi+8]
0x14000269a  mov     rcx, [rcx+18h]
0x14000269e  mov     rax, [r9]
0x1400026a1  mov     r9, [r9+8]
0x1400026a5  mov     [rsp+60h+var_20], rax
0x1400026aa  lea     rax, WPP_86e0affdec483798a987f478d619ae67_Traceguids
0x1400026b1  mov     [rsp+60h+var_28], rax
0x1400026b6  mov     [rsp+60h+var_30], 16h
0x1400026bd  mov     [rsp+60h+var_38], 1
0x1400026c5  mov     [rsp+60h+var_40], 2
0x1400026ca  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400026cf  lea     rcx, aFailedToReturn; __annotation("Debug", "TelemetryAssert", "false", "Failed to return URB to pool.")
0x1400026d6  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400026db  mov     rcx, [rbp+P]; P
0x1400026df  test    rcx, rcx
0x1400026e2  jz      short loc_1400026F0
0x1400026e4  call    cs:__imp_ExFreePool
0x1400026eb  nop     dword ptr [rax+rax+00h]
0x1400026f0  test    rsi, rsi
0x1400026f3  jz      short loc_14000271A
0x1400026f5  mov     eax, dword ptr [rbp+var_10+9]
0x1400026f8  lea     rcx, [rbp+var_10]; struct wil::details::kspin_lock_saved_irql *
0x1400026fc  mov     dword ptr [rbp+var_10+9], eax
0x1400026ff  movzx   eax, word ptr [rbp+var_10+0Dh]
0x140002703  mov     word ptr [rbp+var_10+0Dh], ax
0x140002707  mov     al, byte ptr [rbp+var_10+0Fh]
0x14000270a  mov     byte ptr [rbp+var_10+0Fh], al
0x14000270d  mov     [rbp+var_10.spinLock], rsi
0x140002711  mov     [rbp+var_10.savedIrql], r14b
0x140002715  call    ?Release@kspin_lock_saved_irql@details@wil@@SAXAEBU123@@Z; wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &)
0x14000271a  lea     r11, [rsp+60h+var_s0]
0x14000271f  mov     rbx, [r11+28h]
0x140002723  mov     rsi, [r11+30h]
0x140002727  mov     rsp, r11
0x14000272a  pop     r14
0x14000272c  pop     rdi
0x14000272d  pop     rbp
0x14000272e  retn
```
