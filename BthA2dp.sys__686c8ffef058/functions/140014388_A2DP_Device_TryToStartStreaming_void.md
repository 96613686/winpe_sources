# A2DP_Device::TryToStartStreaming(void)

- ea: `0x140014388`
- end: `0x1400144d2`
- name: `?TryToStartStreaming@A2DP_Device@@AEAAXXZ`
- size: `330`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140033530`
- `0x140034300`
- `0x14003db00`

## callees

- `0x140006410`
- `0x140014388`
- `0x14001f2b8`
- `0x14001f444`
- `0x140033620`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400144bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400144bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001439f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001439f`
- `ks!KsPinAttemptProcessing` at `0x140014448`
- `ks!KsPinAttemptProcessing` at `0x140014448`
- `btampm!BtaMpmUpdateSuspendStatus` at `0x140014473`
- `btampm!BtaMpmUpdateSuspendStatus` at `0x140014473`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x1400144a9`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x1400144a9`

## pseudocode

```c
void __fastcall A2DP_Device::TryToStartStreaming(KSPIN_LOCK *this)
{
  KSPIN_LOCK *v1; // rdi
  KIRQL v3; // al
  KSPIN_LOCK v4; // rdx
  KIRQL v5; // si
  __int64 v6; // rdx
  struct _KSPIN *v7; // rcx
  _QWORD *v8; // [rsp+20h] [rbp-38h] BYREF
  utl::_RefCountBase *v9; // [rsp+28h] [rbp-30h]

  v1 = this + 87;
  v3 = KeAcquireSpinLockRaiseToDpc(this + 87);
  v4 = this[1];
  *((_BYTE *)this + 2838) = 1;
  v5 = v3;
  if ( !v4 || !*(_BYTE *)(v4 + 90) || !*((_BYTE *)this + 2836) && !*(_BYTE *)(v4 + 89) || !*((_BYTE *)this + 2837) )
    goto LABEL_21;
  if ( *((_DWORD *)this + 708) == 1 )
  {
    v7 = *(struct _KSPIN **)(v4 + 32);
    if ( v7 )
      KsPinAttemptProcessing(v7, 1u);
    A2DP_Device::GetMPMContext(this, &v8);
    if ( v8 )
      BtaMpmUpdateSuspendStatus(*v8, 0, 1);
    if ( v9 )
      utl::_RefCountBase::_DecStrong(v9);
    goto LABEL_20;
  }
  if ( *((_DWORD *)this + 708) == 2 || *((_DWORD *)this + 708) == 3 )
  {
    A2DP_Device::SetStreamingState(this, 1);
LABEL_20:
    A2DP_Device::CompletePinStateCompletionContexts(this, this + 109);
    goto LABEL_21;
  }
  if ( (unsigned int)(*((_DWORD *)this + 708) - 5) <= 1 )
  {
    v6 = 7;
    if ( *((_DWORD *)this + 752) != -1 )
      v6 = 1;
    A2DP_Device::SetStreamingState(this, v6);
  }
LABEL_21:
  if ( this[410] )
    SleepstudyHelper_ComponentActive();
  KeReleaseSpinLock(v1, v5);
}

```

## disassembly

```asm
0x140014388  push    rbx
0x14001438a  push    rsi
0x14001438b  push    rdi
0x14001438c  push    r14
0x14001438e  sub     rsp, 38h
0x140014392  lea     rdi, [rcx+2B8h]
0x140014399  mov     rbx, rcx
0x14001439c  mov     rcx, rdi; SpinLock
0x14001439f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400143a6  nop     dword ptr [rax+rax+00h]
0x1400143ab  mov     rdx, [rbx+8]
0x1400143af  mov     r14d, 1
0x1400143b5  mov     [rbx+0B16h], r14b
0x1400143bc  mov     sil, al
0x1400143bf  test    rdx, rdx
0x1400143c2  jz      loc_14001449D
0x1400143c8  cmp     byte ptr [rdx+5Ah], 0
0x1400143cc  jz      loc_14001449D
0x1400143d2  cmp     byte ptr [rbx+0B14h], 0
0x1400143d9  jnz     short loc_1400143E5
0x1400143db  cmp     byte ptr [rdx+59h], 0
0x1400143df  jz      loc_14001449D
0x1400143e5  cmp     byte ptr [rbx+0B15h], 0
0x1400143ec  jz      loc_14001449D
0x1400143f2  mov     ecx, [rbx+0B10h]
0x1400143f8  sub     ecx, r14d
0x1400143fb  jz      short loc_14001443C
0x1400143fd  sub     ecx, r14d
0x140014400  jz      short loc_14001442F
0x140014402  sub     ecx, r14d
0x140014405  jz      short loc_14001442F
0x140014407  sub     ecx, 2
0x14001440a  jz      short loc_140014415
0x14001440c  cmp     ecx, r14d
0x14001440f  jnz     loc_14001449D
0x140014415  cmp     dword ptr [rbx+0BC0h], 0FFFFFFFFh
0x14001441c  mov     edx, 7
0x140014421  mov     rcx, rbx
0x140014424  cmovnz  edx, r14d
0x140014428  call    ?SetStreamingState@A2DP_Device@@AEAAXW4StreamingState@@@Z; A2DP_Device::SetStreamingState(StreamingState)
0x14001442d  jmp     short loc_14001449D
0x14001442f  mov     edx, r14d
0x140014432  mov     rcx, rbx
0x140014435  call    ?SetStreamingState@A2DP_Device@@AEAAXW4StreamingState@@@Z; A2DP_Device::SetStreamingState(StreamingState)
0x14001443a  jmp     short loc_14001448E
0x14001443c  mov     rcx, [rdx+20h]; Pin
0x140014440  test    rcx, rcx
0x140014443  jz      short loc_140014454
0x140014445  mov     dl, r14b; Asynchronous
0x140014448  call    cs:__imp_KsPinAttemptProcessing
0x14001444f  nop     dword ptr [rax+rax+00h]
0x140014454  lea     rdx, [rsp+58h+var_38]
0x140014459  mov     rcx, rbx
0x14001445c  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x140014461  mov     rcx, [rsp+58h+var_38]
0x140014466  test    rcx, rcx
0x140014469  jz      short loc_14001447F
0x14001446b  mov     rcx, [rcx]
0x14001446e  mov     r8d, r14d
0x140014471  xor     edx, edx
0x140014473  call    cs:__imp_BtaMpmUpdateSuspendStatus
0x14001447a  nop     dword ptr [rax+rax+00h]
0x14001447f  mov     rcx, [rsp+58h+var_30]; this
0x140014484  test    rcx, rcx
0x140014487  jz      short loc_14001448E
0x140014489  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001448e  lea     rdx, [rbx+368h]
0x140014495  mov     rcx, rbx
0x140014498  call    ?CompletePinStateCompletionContexts@A2DP_Device@@QEAAXAEAV?$vector@V?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@V?$allocator@V?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@@2@@utl@@@Z; A2DP_Device::CompletePinStateCompletionContexts(utl::vector<utl::shared_ptr<wil::details::kernel_event_t<1>>,utl::allocator<utl::shared_ptr<wil::details::kernel_event_t<1>>>> &)
0x14001449d  mov     rcx, [rbx+0CD0h]
0x1400144a4  test    rcx, rcx
0x1400144a7  jz      short loc_1400144B5
0x1400144a9  call    cs:__imp_SleepstudyHelper_ComponentActive
0x1400144b0  nop     dword ptr [rax+rax+00h]
0x1400144b5  mov     dl, sil; NewIrql
0x1400144b8  mov     rcx, rdi; SpinLock
0x1400144bb  call    cs:__imp_KeReleaseSpinLock
0x1400144c2  nop     dword ptr [rax+rax+00h]
0x1400144c7  add     rsp, 38h
0x1400144cb  pop     r14
0x1400144cd  pop     rdi
0x1400144ce  pop     rsi
0x1400144cf  pop     rbx
0x1400144d0  retn
```
