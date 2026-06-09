# A2DP_Device::TryToPauseStreaming(bool)

- ea: `0x14001ebfc`
- end: `0x14001ed25`
- name: `?TryToPauseStreaming@A2DP_Device@@AEAAX_N@Z`
- size: `297`
- prototype: `void __fastcall(A2DP_Device *__hidden this, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140033440`
- `0x140034300`
- `0x14003d9f0`

## callees

- `0x140006410`
- `0x14001ebfc`
- `0x14001f2b8`
- `0x14001f444`
- `0x140033620`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001ec9b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ec9b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ec14`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ec14`
- `btampm!BtaMpmUpdateSuspendStatus` at `0x14001ecdc`
- `btampm!BtaMpmUpdateSuspendStatus` at `0x14001ecdc`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14001ec89`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14001ec89`

## pseudocode

```c
void __fastcall A2DP_Device::TryToPauseStreaming(KSPIN_LOCK *this, char a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // al
  __int64 v6; // rdx
  KIRQL v7; // bp
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  KSPIN_LOCK v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // [rsp+20h] [rbp-38h] BYREF
  utl::_RefCountBase *v15; // [rsp+28h] [rbp-30h]

  v2 = this + 87;
  v5 = KeAcquireSpinLockRaiseToDpc(this + 87);
  *((_BYTE *)this + 2838) = 0;
  v7 = v5;
  LOBYTE(v6) = a2 && *((_DWORD *)this + 703);
  v8 = *((_DWORD *)this + 708);
  if ( !v8 )
  {
LABEL_11:
    A2DP_Device::CompletePinStateCompletionContexts(this, this + 112);
    goto LABEL_12;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v13 = ((unsigned __int8)v6 ^ 1u) + 2;
    goto LABEL_22;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 3;
    if ( v11 )
    {
      if ( v11 != 1 )
        goto LABEL_12;
      A2DP_Device::SetStreamingState(this, 5);
    }
    else
    {
      A2DP_Device::GetMPMContext(this, &v14);
      if ( v14 )
        BtaMpmUpdateSuspendStatus(*v14, *((_BYTE *)this + 2837) == 0, 1);
      if ( v15 )
        utl::_RefCountBase::_DecStrong(v15);
    }
    goto LABEL_11;
  }
  if ( !(_BYTE)v6 )
  {
    v13 = 3;
LABEL_22:
    A2DP_Device::SetStreamingState(this, v13);
  }
LABEL_12:
  v12 = this[410];
  if ( v12 )
    SleepstudyHelper_ComponentInactive(v12, v6);
  KeReleaseSpinLock(v2, v7);
}

```

## disassembly

```asm
0x14001ebfc  push    rbx
0x14001ebfe  push    rbp
0x14001ebff  push    rsi
0x14001ec00  push    rdi
0x14001ec01  sub     rsp, 38h
0x14001ec05  lea     rsi, [rcx+2B8h]
0x14001ec0c  mov     rdi, rcx
0x14001ec0f  mov     rcx, rsi; SpinLock
0x14001ec12  mov     bl, dl
0x14001ec14  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ec1b  nop     dword ptr [rax+rax+00h]
0x14001ec20  mov     byte ptr [rdi+0B16h], 0
0x14001ec27  mov     bpl, al
0x14001ec2a  test    bl, bl
0x14001ec2c  jz      short loc_14001EC3B
0x14001ec2e  cmp     dword ptr [rdi+0AFCh], 0
0x14001ec35  jz      short loc_14001EC3B
0x14001ec37  mov     dl, 1
0x14001ec39  jmp     short loc_14001EC3D
0x14001ec3b  xor     dl, dl
0x14001ec3d  mov     ecx, [rdi+0B10h]
0x14001ec43  test    ecx, ecx
0x14001ec45  jz      short loc_14001EC6E
0x14001ec47  sub     ecx, 1
0x14001ec4a  jz      loc_14001ED0F
0x14001ec50  sub     ecx, 1
0x14001ec53  jz      loc_14001ED00
0x14001ec59  sub     ecx, 3
0x14001ec5c  jz      short loc_14001ECB1
0x14001ec5e  cmp     ecx, 1
0x14001ec61  jnz     short loc_14001EC7D
0x14001ec63  lea     edx, [rcx+4]
0x14001ec66  mov     rcx, rdi
0x14001ec69  call    ?SetStreamingState@A2DP_Device@@AEAAXW4StreamingState@@@Z; A2DP_Device::SetStreamingState(StreamingState)
0x14001ec6e  lea     rdx, [rdi+380h]
0x14001ec75  mov     rcx, rdi
0x14001ec78  call    ?CompletePinStateCompletionContexts@A2DP_Device@@QEAAXAEAV?$vector@V?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@V?$allocator@V?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@@2@@utl@@@Z; A2DP_Device::CompletePinStateCompletionContexts(utl::vector<utl::shared_ptr<wil::details::kernel_event_t<1>>,utl::allocator<utl::shared_ptr<wil::details::kernel_event_t<1>>>> &)
0x14001ec7d  mov     rcx, [rdi+0CD0h]
0x14001ec84  test    rcx, rcx
0x14001ec87  jz      short loc_14001EC95
0x14001ec89  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x14001ec90  nop     dword ptr [rax+rax+00h]
0x14001ec95  mov     dl, bpl; NewIrql
0x14001ec98  mov     rcx, rsi; SpinLock
0x14001ec9b  call    cs:__imp_KeReleaseSpinLock
0x14001eca2  nop     dword ptr [rax+rax+00h]
0x14001eca7  add     rsp, 38h
0x14001ecab  pop     rdi
0x14001ecac  pop     rsi
0x14001ecad  pop     rbp
0x14001ecae  pop     rbx
0x14001ecaf  retn
0x14001ecb1  lea     rdx, [rsp+58h+var_38]
0x14001ecb6  mov     rcx, rdi
0x14001ecb9  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x14001ecbe  mov     rcx, [rsp+58h+var_38]
0x14001ecc3  test    rcx, rcx
0x14001ecc6  jz      short loc_14001ECE8
0x14001ecc8  mov     rcx, [rcx]
0x14001eccb  xor     edx, edx
0x14001eccd  cmp     [rdi+0B15h], dl
0x14001ecd3  mov     r8d, 1
0x14001ecd9  setz    dl
0x14001ecdc  call    cs:__imp_BtaMpmUpdateSuspendStatus
0x14001ece3  nop     dword ptr [rax+rax+00h]
0x14001ece8  mov     rcx, [rsp+58h+var_30]; this
0x14001eced  test    rcx, rcx
0x14001ecf0  jz      loc_14001EC6E
0x14001ecf6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001ecfb  jmp     loc_14001EC6E
0x14001ed00  test    dl, dl
0x14001ed02  jnz     loc_14001EC7D
0x14001ed08  mov     edx, 3
0x14001ed0d  jmp     short loc_14001ED18
0x14001ed0f  movzx   edx, dl
0x14001ed12  xor     edx, 1
0x14001ed15  add     edx, 2
0x14001ed18  mov     rcx, rdi
0x14001ed1b  call    ?SetStreamingState@A2DP_Device@@AEAAXW4StreamingState@@@Z; A2DP_Device::SetStreamingState(StreamingState)
0x14001ed20  jmp     loc_14001EC7D
```
