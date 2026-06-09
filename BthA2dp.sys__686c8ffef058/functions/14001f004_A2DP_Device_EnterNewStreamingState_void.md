# A2DP_Device::EnterNewStreamingState(void)

- ea: `0x14001f004`
- end: `0x14001f2b2`
- name: `?EnterNewStreamingState@A2DP_Device@@AEAAXXZ`
- size: `686`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x140033620`

## callees

- `0x140006410`
- `0x1400077e0`
- `0x14000e240`
- `0x140013e84`
- `0x14001f004`
- `0x14001f2b8`
- `0x14001f390`
- `0x1400319ac`
- `0x140031b00`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001f271`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001f271`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14001f1b9`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14001f1b9`
- `ntoskrnl!KeSetTimer` at `0x14001f1e5`
- `ntoskrnl!KeSetTimer` at `0x14001f1e5`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001f06e`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001f17a`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001f06e`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001f17a`
- `ntoskrnl!KeSetEvent` at `0x14001f0c2`
- `ntoskrnl!KeSetEvent` at `0x14001f29a`
- `ntoskrnl!KeSetEvent` at `0x14001f0c2`
- `ntoskrnl!KeSetEvent` at `0x14001f29a`
- `ks!KsPinAttemptProcessing` at `0x14001f265`
- `ks!KsPinAttemptProcessing` at `0x14001f265`
- `btampm!BtaMpmUpdateSuspendStatus` at `0x14001f113`
- `btampm!BtaMpmUpdateSuspendStatus` at `0x14001f23b`
- `btampm!BtaMpmUpdateSuspendStatus` at `0x14001f113`
- `btampm!BtaMpmUpdateSuspendStatus` at `0x14001f23b`

## pseudocode

```c
void __fastcall A2DP_Device::EnterNewStreamingState(A2DP_Device *this, __int64 a2, __int64 a3)
{
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  struct _IO_WORKITEM *WorkItem; // rdi
  const char *v13; // r8
  __int64 v14; // rdx
  struct _KSPIN *v15; // rcx
  _QWORD *v16; // [rsp+20h] [rbp-18h] BYREF
  utl::_RefCountBase *v17; // [rsp+28h] [rbp-10h]

  v4 = *((_DWORD *)this + 708);
  if ( !v4 )
  {
    KeSetEvent((PRKEVENT)this + 124, 0, 0);
    return;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    A2dpRole::SetStreaming(*((A2dpRole **)this + 1), 1);
    A2DP_Device::SendSuspendOrStartResponse(this, 0, 0);
    A2DP_Device::SendSuspendOrStartResponse(this, 1, 0x31u);
    A2DP_Device::GetMPMContext(this, &v16);
    if ( v16 )
      BtaMpmUpdateSuspendStatus(*v16, 0, 1);
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    v15 = *(struct _KSPIN **)(*((_QWORD *)this + 1) + 32LL);
    if ( v15 )
      KsPinAttemptProcessing(v15, 1u);
    *((_QWORD *)this + 363) = KeQueryUnbiasedInterruptTime();
    A2DP_Device::LogStreamingStart(this);
    return;
  }
  v6 = v5 - 1;
  if ( !v6 )
    goto LABEL_24;
  v7 = v6 - 1;
  if ( !v7 )
  {
    A2DP_Device::LogStreamingInformation(this);
    WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)this + 48));
    if ( !WorkItem )
      return;
    v13 = "EnterNewStreamingState1";
    goto LABEL_23;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( *((_DWORD *)this + 750) != -1 )
      return;
    A2DP_Device::SetLastAvdtpActivity(this, 41, a3);
    v14 = 0;
    goto LABEL_20;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    KeSetEvent((PRKEVENT)this + 124, 0, 0);
    A2DP_Device::SendSuspendOrStartResponse(this, 1, 0);
    A2DP_Device::SendSuspendOrStartResponse(this, 0, 0x31u);
    A2DP_Device::GetMPMContext(this, &v16);
    if ( v16 )
      BtaMpmUpdateSuspendStatus(*v16, *((_BYTE *)this + 2837) == 0, 1);
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    return;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
LABEL_24:
    KeSetTimer(
      (PKTIMER)((char *)this + 2840),
      (LARGE_INTEGER)(-10000 * *((_DWORD *)this + 703)),
      (PKDPC)((char *)this + 2912));
    return;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( *((_DWORD *)this + 752) != -1 )
      return;
    A2DP_Device::SetLastAvdtpActivity(this, 33, a3);
    v14 = 1;
LABEL_20:
    (*((void (__fastcall **)(_QWORD, __int64))this + 57))(*((_QWORD *)this + 50), v14);
    return;
  }
  if ( v11 == 1 )
  {
    A2DP_Device::LogStreamingInformation(this);
    WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)this + 48));
    if ( WorkItem )
    {
      v13 = "EnterNewStreamingState2";
LABEL_23:
      A2DP_Device::AddRef(this, 4, v13);
      IoQueueWorkItemEx(WorkItem, A2DP_Device::StreamingStateWaitForDrainWorkerStatic, DelayedWorkQueue, this);
    }
  }
}

```

## disassembly

```asm
0x14001f004  mov     [rsp+arg_0], rbx
0x14001f009  push    rdi
0x14001f00a  sub     rsp, 30h
0x14001f00e  mov     rbx, rcx
0x14001f011  mov     ecx, [rcx+0B10h]
0x14001f017  test    ecx, ecx
0x14001f019  jz      loc_14001F28E
0x14001f01f  sub     ecx, 1
0x14001f022  jz      loc_14001F1F6
0x14001f028  sub     ecx, 1
0x14001f02b  jz      loc_14001F1CA
0x14001f031  sub     ecx, 1
0x14001f034  jz      loc_14001F16B
0x14001f03a  sub     ecx, 1
0x14001f03d  jz      loc_14001F137
0x14001f043  sub     ecx, 1
0x14001f046  jz      short loc_14001F0B6
0x14001f048  sub     ecx, 1
0x14001f04b  jz      loc_14001F1CA
0x14001f051  sub     ecx, 1
0x14001f054  jz      short loc_14001F092
0x14001f056  cmp     ecx, 1
0x14001f059  jnz     loc_14001F2A6
0x14001f05f  mov     rcx, rbx; this
0x14001f062  call    ?LogStreamingInformation@A2DP_Device@@AEBAXXZ; A2DP_Device::LogStreamingInformation(void)
0x14001f067  mov     rcx, [rbx+180h]; DeviceObject
0x14001f06e  call    cs:__imp_IoAllocateWorkItem
0x14001f075  nop     dword ptr [rax+rax+00h]
0x14001f07a  mov     rdi, rax
0x14001f07d  test    rax, rax
0x14001f080  jz      loc_14001F2A6
0x14001f086  lea     r8, aEnternewstream_0; "EnterNewStreamingState2"
0x14001f08d  jmp     loc_14001F199
0x14001f092  cmp     dword ptr [rbx+0BC0h], 0FFFFFFFFh
0x14001f099  jnz     loc_14001F2A6
0x14001f09f  mov     edx, 21h ; '!'
0x14001f0a4  mov     rcx, rbx
0x14001f0a7  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14001f0ac  mov     edx, 1
0x14001f0b1  jmp     loc_14001F153
0x14001f0b6  lea     rcx, [rbx+0BA0h]; Event
0x14001f0bd  xor     r8d, r8d; Wait
0x14001f0c0  xor     edx, edx; Increment
0x14001f0c2  call    cs:__imp_KeSetEvent
0x14001f0c9  nop     dword ptr [rax+rax+00h]
0x14001f0ce  xor     r8d, r8d; unsigned __int8
0x14001f0d1  mov     dl, 1; bool
0x14001f0d3  mov     rcx, rbx; this
0x14001f0d6  call    ?SendSuspendOrStartResponse@A2DP_Device@@AEAAX_NE@Z; A2DP_Device::SendSuspendOrStartResponse(bool,uchar)
0x14001f0db  mov     r8b, 31h ; '1'; unsigned __int8
0x14001f0de  xor     edx, edx; bool
0x14001f0e0  mov     rcx, rbx; this
0x14001f0e3  call    ?SendSuspendOrStartResponse@A2DP_Device@@AEAAX_NE@Z; A2DP_Device::SendSuspendOrStartResponse(bool,uchar)
0x14001f0e8  lea     rdx, [rsp+38h+var_18]
0x14001f0ed  mov     rcx, rbx
0x14001f0f0  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x14001f0f5  mov     rcx, [rsp+38h+var_18]
0x14001f0fa  test    rcx, rcx
0x14001f0fd  jz      short loc_14001F11F
0x14001f0ff  mov     rcx, [rcx]
0x14001f102  xor     edx, edx
0x14001f104  cmp     [rbx+0B15h], dl
0x14001f10a  mov     r8d, 1
0x14001f110  setz    dl
0x14001f113  call    cs:__imp_BtaMpmUpdateSuspendStatus
0x14001f11a  nop     dword ptr [rax+rax+00h]
0x14001f11f  mov     rcx, [rsp+38h+var_10]; this
0x14001f124  test    rcx, rcx
0x14001f127  jz      loc_14001F2A6
0x14001f12d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001f132  jmp     loc_14001F2A6
0x14001f137  cmp     dword ptr [rbx+0BB8h], 0FFFFFFFFh
0x14001f13e  jnz     loc_14001F2A6
0x14001f144  mov     edx, 29h ; ')'
0x14001f149  mov     rcx, rbx
0x14001f14c  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14001f151  xor     edx, edx
0x14001f153  mov     rax, [rbx+1C8h]
0x14001f15a  mov     rcx, [rbx+190h]
0x14001f161  call    _guard_dispatch_icall
0x14001f166  jmp     loc_14001F2A6
0x14001f16b  mov     rcx, rbx; this
0x14001f16e  call    ?LogStreamingInformation@A2DP_Device@@AEBAXXZ; A2DP_Device::LogStreamingInformation(void)
0x14001f173  mov     rcx, [rbx+180h]; DeviceObject
0x14001f17a  call    cs:__imp_IoAllocateWorkItem
0x14001f181  nop     dword ptr [rax+rax+00h]
0x14001f186  mov     rdi, rax
0x14001f189  test    rax, rax
0x14001f18c  jz      loc_14001F2A6
0x14001f192  lea     r8, aEnternewstream; "EnterNewStreamingState1"
0x14001f199  mov     edx, 4; __int16
0x14001f19e  mov     rcx, rbx; this
0x14001f1a1  call    ?AddRef@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::AddRef(short,char const *)
0x14001f1a6  mov     r9, rbx; Context
0x14001f1a9  lea     rdx, ?StreamingStateWaitForDrainWorkerStatic@A2DP_Device@@CAXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x14001f1b0  mov     r8d, 1; QueueType
0x14001f1b6  mov     rcx, rdi; IoWorkItem
0x14001f1b9  call    cs:__imp_IoQueueWorkItemEx
0x14001f1c0  nop     dword ptr [rax+rax+00h]
0x14001f1c5  jmp     loc_14001F2A6
0x14001f1ca  imul    eax, [rbx+0AFCh], 0FFFFD8F0h
0x14001f1d4  lea     r8, [rbx+0B60h]; Dpc
0x14001f1db  lea     rcx, [rbx+0B18h]; Timer
0x14001f1e2  movsxd  rdx, eax; DueTime
0x14001f1e5  call    cs:__imp_KeSetTimer
0x14001f1ec  nop     dword ptr [rax+rax+00h]
0x14001f1f1  jmp     loc_14001F2A6
0x14001f1f6  mov     rcx, [rbx+8]; this
0x14001f1fa  mov     dl, 1; bool
0x14001f1fc  call    ?SetStreaming@A2dpRole@@QEAAX_N@Z; A2dpRole::SetStreaming(bool)
0x14001f201  xor     r8d, r8d; unsigned __int8
0x14001f204  xor     edx, edx; bool
0x14001f206  mov     rcx, rbx; this
0x14001f209  call    ?SendSuspendOrStartResponse@A2DP_Device@@AEAAX_NE@Z; A2DP_Device::SendSuspendOrStartResponse(bool,uchar)
0x14001f20e  mov     r8b, 31h ; '1'; unsigned __int8
0x14001f211  mov     dl, 1; bool
0x14001f213  mov     rcx, rbx; this
0x14001f216  call    ?SendSuspendOrStartResponse@A2DP_Device@@AEAAX_NE@Z; A2DP_Device::SendSuspendOrStartResponse(bool,uchar)
0x14001f21b  lea     rdx, [rsp+38h+var_18]
0x14001f220  mov     rcx, rbx
0x14001f223  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x14001f228  mov     rcx, [rsp+38h+var_18]
0x14001f22d  test    rcx, rcx
0x14001f230  jz      short loc_14001F247
0x14001f232  mov     rcx, [rcx]
0x14001f235  xor     edx, edx
0x14001f237  lea     r8d, [rdx+1]
0x14001f23b  call    cs:__imp_BtaMpmUpdateSuspendStatus
0x14001f242  nop     dword ptr [rax+rax+00h]
0x14001f247  mov     rcx, [rsp+38h+var_10]; this
0x14001f24c  test    rcx, rcx
0x14001f24f  jz      short loc_14001F256
0x14001f251  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001f256  mov     rax, [rbx+8]
0x14001f25a  mov     rcx, [rax+20h]; Pin
0x14001f25e  test    rcx, rcx
0x14001f261  jz      short loc_14001F271
0x14001f263  mov     dl, 1; Asynchronous
0x14001f265  call    cs:__imp_KsPinAttemptProcessing
0x14001f26c  nop     dword ptr [rax+rax+00h]
0x14001f271  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14001f278  nop     dword ptr [rax+rax+00h]
0x14001f27d  mov     rcx, rbx; this
0x14001f280  mov     [rbx+0B58h], rax
0x14001f287  call    ?LogStreamingStart@A2DP_Device@@AEAAXXZ; A2DP_Device::LogStreamingStart(void)
0x14001f28c  jmp     short loc_14001F2A6
0x14001f28e  lea     rcx, [rbx+0BA0h]; Event
0x14001f295  xor     r8d, r8d; Wait
0x14001f298  xor     edx, edx; Increment
0x14001f29a  call    cs:__imp_KeSetEvent
0x14001f2a1  nop     dword ptr [rax+rax+00h]
0x14001f2a6  mov     rbx, [rsp+38h+arg_0]
0x14001f2ab  add     rsp, 30h
0x14001f2af  pop     rdi
0x14001f2b0  retn
```
