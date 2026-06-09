# Task::OnStartTaskHandler(void)

- ea: `0x140029bc0`
- end: `0x140029f8c`
- name: `?OnStartTaskHandler@Task@@IEAAXXZ`
- size: `972`
- prototype: `void __fastcall(Task *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140029ba0`

## callees

- `0x1400122e0`
- `0x140029bc0`
- `0x140029f94`
- `0x14002a0c4`
- `0x14002aa28`
- `0x14002ace4`
- `0x140034e04`
- `0x140034ec4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140029cf3`
- `ntoskrnl!ExAllocatePool2` at `0x140029cf3`

## pseudocode

```c
void __fastcall Task::OnStartTaskHandler(Task *this, __int64 a2, struct _LIST_ENTRY *Blink)
{
  DeviceCommand *p_m_TaskDeviceCommand; // rdi
  unsigned int m_CommandToken; // r15d
  unsigned __int16 m_PortId; // bp
  NotificationManager *m_pNotificationManager; // r14
  INotifyDeviceIndicationCallback *v8; // rcx
  unsigned __int64 v9; // rdi
  __int64 Pool2; // rax
  _QWORD *v11; // rax
  unsigned int v12; // eax
  int started; // edi
  int v14; // r9d
  __int64 v15; // [rsp+28h] [rbp-50h]
  unsigned int m_ActivityId; // [rsp+30h] [rbp-48h]
  __int64 v17; // [rsp+38h] [rbp-40h]

  p_m_TaskDeviceCommand = &this->m_TaskDeviceCommand;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      (_DWORD)Blink,
      21,
      (__int64)WPP_afb7539b75cc35590d3638ae95cbb18d_Traceguids,
      (_BYTE)this + 56,
      this->m_TaskDeviceCommand.m_ActivityId);
  }
  m_CommandToken = p_m_TaskDeviceCommand->m_CommandToken;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        (_DWORD)Blink,
        23,
        (__int64)WPP_afb7539b75cc35590d3638ae95cbb18d_Traceguids,
        (char)p_m_TaskDeviceCommand,
        p_m_TaskDeviceCommand->m_ActivityId,
        0);
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        (_DWORD)Blink,
        24,
        (__int64)WPP_afb7539b75cc35590d3638ae95cbb18d_Traceguids,
        (char)p_m_TaskDeviceCommand,
        p_m_TaskDeviceCommand->m_ActivityId);
    }
  }
  m_PortId = p_m_TaskDeviceCommand->m_PortId;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v17) = 0;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      (_DWORD)Blink,
      26,
      (__int64)WPP_afb7539b75cc35590d3638ae95cbb18d_Traceguids,
      (char)p_m_TaskDeviceCommand,
      p_m_TaskDeviceCommand->m_ActivityId,
      v17);
  }
  m_pNotificationManager = this->m_pNotificationManager;
  v8 = &this->INotifyDeviceIndicationCallback;
  v9 = (unsigned __int64)&this->INotifyDeviceIndicationCallback & -(__int64)(this != 0);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v8 = (INotifyDeviceIndicationCallback *)WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        16,
        (__int64)WPP_f7acfb2b6a34352e2d9bcc04dacb58ee_Traceguids);
  }
  if ( !v9 || this == (Task *)-264LL )
  {
    started = -1073741811;
  }
  else
  {
    Pool2 = ExAllocatePool2(64, 48, 1198089303);
    v8 = (INotifyDeviceIndicationCallback *)Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 4) = 0;
      *(_DWORD *)(Pool2 + 8) = m_CommandToken;
      *(_WORD *)(Pool2 + 12) = m_PortId;
      *(_QWORD *)(Pool2 + 16) = v9;
      v11 = (_QWORD *)(Pool2 + 24);
      if ( v11 )
      {
        v11[1] = v11;
        *v11 = v11;
        v11[2] = v8;
      }
      v12 = _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      if ( !v12 )
        v12 = _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      LODWORD(v8->__vftable) = v12;
      this->m_NotificationRegistrationToken = v12;
      Blink = m_pNotificationManager->m_NotificationRegistrationList.Blink;
      if ( Blink->Flink != &m_pNotificationManager->m_NotificationRegistrationList )
        __fastfail(3u);
      started = 0;
      v8[3].__vftable = (INotifyDeviceIndicationCallback_vtbl *)&m_pNotificationManager->m_NotificationRegistrationList;
      v8[4].__vftable = (INotifyDeviceIndicationCallback_vtbl *)Blink;
      Blink->Flink = (struct _LIST_ENTRY *)&v8[3];
      m_pNotificationManager->m_NotificationRegistrationList.Blink = (struct _LIST_ENTRY *)&v8[3];
    }
    else
    {
      started = -1073741670;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v8 = (INotifyDeviceIndicationCallback *)WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LODWORD(v15) = started;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        17,
        (__int64)WPP_f7acfb2b6a34352e2d9bcc04dacb58ee_Traceguids,
        v15);
    }
  }
  if ( started )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v14 = 33;
LABEL_48:
      m_ActivityId = this->m_ActivityId;
      goto LABEL_49;
    }
  }
  else
  {
    started = EventQueue::StartTimer((EventQueue *)v8, this->m_pTimerRegistrationContext, this->m_RelativeTimeoutInMSec);
    if ( started )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v14 = 34;
        m_ActivityId = this->m_ActivityId;
LABEL_49:
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          (_DWORD)Blink,
          v14,
          (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
          (char)this,
          m_ActivityId);
      }
    }
    else
    {
      this->m_bTimerStopped = 0;
      started = Task::IssueDeviceCommandToCommandScheduler(this);
      if ( !started )
      {
        this->m_IsDeviceCommandPending = 1;
        return;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v14 = 35;
        goto LABEL_48;
      }
    }
  }
  Task::OnTaskCompletedHandler(this, started, 0, 0);
}

```

## disassembly

```asm
0x140029bc0  push    rbx
0x140029bc2  push    rbp
0x140029bc3  push    rsi
0x140029bc4  push    rdi
0x140029bc5  push    r12
0x140029bc7  push    r14
0x140029bc9  push    r15
0x140029bcb  sub     rsp, 40h
0x140029bcf  mov     rbx, rcx
0x140029bd2  lea     rdi, [rcx+38h]
0x140029bd6  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029bdd  xor     r12d, r12d
0x140029be0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029be7  lea     r14, WPP_afb7539b75cc35590d3638ae95cbb18d_Traceguids
0x140029bee  jz      short loc_140029C0C
0x140029bf0  mov     rcx, cs:WPP_GLOBAL_Control
0x140029bf7  cmp     byte ptr [rcx+29h], 5
0x140029bfb  jnb     loc_140029EA0
0x140029c01  cmp     [rcx+48h], r12w
0x140029c06  jnz     loc_140029EA0
0x140029c0c  mov     r15d, [rdi+0A0h]
0x140029c13  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029c1a  jz      short loc_140029C5D
0x140029c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029c23  cmp     byte ptr [rcx+29h], 5
0x140029c27  jnb     loc_140029EC7
0x140029c2d  cmp     [rcx+48h], r12w
0x140029c32  jnz     loc_140029EC7
0x140029c38  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029c3f  jz      short loc_140029C5D
0x140029c41  mov     rcx, cs:WPP_GLOBAL_Control
0x140029c48  cmp     byte ptr [rcx+29h], 5
0x140029c4c  jnb     loc_140029E4F
0x140029c52  cmp     [rcx+48h], r12w
0x140029c57  jnz     loc_140029E4F
0x140029c5d  movzx   ebp, word ptr [rdi+0A4h]
0x140029c64  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029c6b  jz      short loc_140029C89
0x140029c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140029c74  cmp     byte ptr [rcx+29h], 5
0x140029c78  jnb     loc_140029E23
0x140029c7e  cmp     [rcx+48h], r12w
0x140029c83  jnz     loc_140029E23
0x140029c89  mov     r14, [rbx+110h]
0x140029c90  lea     rcx, [rbx+10h]
0x140029c94  mov     rax, rbx
0x140029c97  neg     rax
0x140029c9a  sbb     rdi, rdi
0x140029c9d  and     rdi, rcx
0x140029ca0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029ca7  lea     rax, WPP_f7acfb2b6a34352e2d9bcc04dacb58ee_Traceguids
0x140029cae  jz      short loc_140029CCC
0x140029cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140029cb7  cmp     byte ptr [rcx+29h], 5
0x140029cbb  jnb     loc_140029EF3
0x140029cc1  cmp     [rcx+48h], r12w
0x140029cc6  jnz     loc_140029EF3
0x140029ccc  test    rdi, rdi
0x140029ccf  jz      loc_140029E19
0x140029cd5  lea     rsi, [rbx+108h]
0x140029cdc  test    rsi, rsi
0x140029cdf  jz      loc_140029E19
0x140029ce5  mov     edx, 30h ; '0'
0x140029cea  mov     r8d, 47696457h
0x140029cf0  lea     ecx, [rdx+10h]
0x140029cf3  call    cs:__imp_ExAllocatePool2
0x140029cfa  nop     dword ptr [rax+rax+00h]
0x140029cff  mov     rcx, rax
0x140029d02  test    rax, rax
0x140029d05  jz      loc_140029DE9
0x140029d0b  mov     [rax+4], r12d
0x140029d0f  mov     [rax+8], r15d
0x140029d13  mov     [rax+0Ch], bp
0x140029d17  mov     [rax+10h], rdi
0x140029d1b  add     rax, 18h
0x140029d1f  jz      short loc_140029D2C
0x140029d21  mov     [rax+8], rax
0x140029d25  mov     [rax], rax
0x140029d28  mov     [rax+10h], rcx
0x140029d2c  mov     eax, 1
0x140029d31  lock xadd dword ptr cs:WPP_MAIN_CB.Queue+20h, eax
0x140029d39  add     eax, 1
0x140029d3c  jz      loc_140029F12
0x140029d42  mov     [rcx], eax
0x140029d44  lea     rdx, [r14+18h]
0x140029d48  mov     [rsi], eax
0x140029d4a  mov     r8, [rdx+8]
0x140029d4e  cmp     [r8], rdx
0x140029d51  jnz     loc_140029E12
0x140029d57  lea     rax, [rcx+18h]
0x140029d5b  mov     edi, r12d
0x140029d5e  mov     [rax], rdx
0x140029d61  mov     [rax+8], r8
0x140029d65  mov     [r8], rax
0x140029d68  mov     [rdx+8], rax
0x140029d6c  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029d73  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029d7a  jz      short loc_140029D98
0x140029d7c  mov     rcx, cs:WPP_GLOBAL_Control; this
0x140029d83  cmp     byte ptr [rcx+29h], 5
0x140029d87  jnb     loc_140029E76
0x140029d8d  cmp     [rcx+48h], r12w
0x140029d92  jnz     loc_140029E76
0x140029d98  test    edi, edi
0x140029d9a  jnz     short loc_140029DF3
0x140029d9c  mov     r8d, [rbx+1CCh]; unsigned int
0x140029da3  mov     rdx, [rbx+1C0h]; struct TimerRegistrationContext *
0x140029daa  call    ?StartTimer@EventQueue@@QEAAHPEAVTimerRegistrationContext@@K@Z; EventQueue::StartTimer(TimerRegistrationContext *,ulong)
0x140029daf  mov     edi, eax
0x140029db1  test    eax, eax
0x140029db3  jnz     loc_140029F2E
0x140029db9  mov     rcx, rbx; this
0x140029dbc  mov     [rbx+1C8h], r12b
0x140029dc3  call    ?IssueDeviceCommandToCommandScheduler@Task@@IEAAHXZ; Task::IssueDeviceCommandToCommandScheduler(void)
0x140029dc8  mov     edi, eax
0x140029dca  test    eax, eax
0x140029dcc  jnz     loc_140029F4A
0x140029dd2  mov     byte ptr [rbx+1A8h], 1
0x140029dd9  add     rsp, 40h
0x140029ddd  pop     r15
0x140029ddf  pop     r14
0x140029de1  pop     r12
0x140029de3  pop     rdi
0x140029de4  pop     rsi
0x140029de5  pop     rbp
0x140029de6  pop     rbx
0x140029de7  retn
0x140029de9  mov     edi, 0C000009Ah
0x140029dee  jmp     loc_140029D6C
0x140029df3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029dfa  jnz     loc_140029F26
0x140029e00  xor     r9d, r9d; unsigned __int8 *
0x140029e03  xor     r8d, r8d; unsigned int
0x140029e06  mov     edx, edi; int
0x140029e08  mov     rcx, rbx; this
0x140029e0b  call    ?OnTaskCompletedHandler@Task@@IEAAXHKPEAE@Z; Task::OnTaskCompletedHandler(int,ulong,uchar *)
0x140029e10  jmp     short loc_140029DD9
0x140029e12  mov     ecx, 3
0x140029e17  int     29h; Win8: RtlFailFast(ecx)
0x140029e19  mov     edi, 0C000000Dh
0x140029e1e  jmp     loc_140029D6C
0x140029e23  mov     eax, [rdi+8]
0x140029e26  mov     r9d, 1Ah
0x140029e2c  mov     rcx, [rcx+40h]
0x140029e30  mov     dl, 5
0x140029e32  mov     dword ptr [rsp+78h+var_40], r12d
0x140029e37  mov     [rsp+78h+var_48], eax
0x140029e3b  mov     [rsp+78h+var_50], rdi
0x140029e40  mov     [rsp+78h+var_58], r14
0x140029e45  call    WPP_RECORDER_SF_qDD
0x140029e4a  jmp     loc_140029C89
0x140029e4f  mov     eax, [rdi+8]
0x140029e52  mov     r9d, 18h
0x140029e58  mov     rcx, [rcx+40h]
0x140029e5c  mov     dl, 5
0x140029e5e  mov     [rsp+78h+var_48], eax
0x140029e62  mov     [rsp+78h+var_50], rdi
0x140029e67  mov     [rsp+78h+var_58], r14
0x140029e6c  call    WPP_RECORDER_SF_qD
0x140029e71  jmp     loc_140029C5D
0x140029e76  mov     rcx, [rcx+40h]
0x140029e7a  lea     rax, WPP_f7acfb2b6a34352e2d9bcc04dacb58ee_Traceguids
0x140029e81  mov     r9d, 11h
0x140029e87  mov     dword ptr [rsp+78h+var_50], edi
0x140029e8b  mov     dl, 5
0x140029e8d  mov     [rsp+78h+var_58], rax
0x140029e92  lea     r8d, [r9-10h]
0x140029e96  call    WPP_RECORDER_SF_D
0x140029e9b  jmp     loc_140029D98
0x140029ea0  mov     eax, [rdi+8]
0x140029ea3  mov     r9d, 15h
0x140029ea9  mov     rcx, [rcx+40h]
0x140029ead  mov     dl, 5
0x140029eaf  mov     [rsp+78h+var_48], eax
0x140029eb3  mov     [rsp+78h+var_50], rdi
0x140029eb8  mov     [rsp+78h+var_58], r14
0x140029ebd  call    WPP_RECORDER_SF_qD
0x140029ec2  jmp     loc_140029C0C
0x140029ec7  mov     eax, [rdi+8]
0x140029eca  mov     r9d, 17h
0x140029ed0  mov     rcx, [rcx+40h]
0x140029ed4  mov     dl, 5
0x140029ed6  mov     dword ptr [rsp+78h+var_40], r12d
0x140029edb  mov     [rsp+78h+var_48], eax
0x140029edf  mov     [rsp+78h+var_50], rdi
0x140029ee4  mov     [rsp+78h+var_58], r14
0x140029ee9  call    WPP_RECORDER_SF_qDD
0x140029eee  jmp     loc_140029C38
0x140029ef3  mov     rcx, [rcx+40h]
0x140029ef7  mov     r9d, 10h
0x140029efd  mov     dl, 5
0x140029eff  mov     [rsp+78h+var_58], rax
0x140029f04  lea     r8d, [r9-0Fh]
0x140029f08  call    WPP_RECORDER_SF_
0x140029f0d  jmp     loc_140029CCC
0x140029f12  mov     eax, 1
0x140029f17  lock xadd dword ptr cs:WPP_MAIN_CB.Queue+20h, eax
0x140029f1f  inc     eax
0x140029f21  jmp     loc_140029D42
0x140029f26  mov     r9d, 21h ; '!'
0x140029f2c  jmp     short loc_140029F5D
0x140029f2e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029f35  jz      loc_140029E00
0x140029f3b  mov     ecx, [rbx+20h]
0x140029f3e  mov     r9d, 22h ; '"'
0x140029f44  mov     [rsp+78h+var_48], ecx
0x140029f48  jmp     short loc_140029F64
0x140029f4a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029f51  jz      loc_140029E00
0x140029f57  mov     r9d, 23h ; '#'
0x140029f5d  mov     eax, [rbx+20h]
0x140029f60  mov     [rsp+78h+var_48], eax
0x140029f64  mov     rcx, cs:WPP_GLOBAL_Control
0x140029f6b  lea     rax, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x140029f72  mov     [rsp+78h+var_50], rbx
0x140029f77  mov     dl, 2
0x140029f79  mov     [rsp+78h+var_58], rax
0x140029f7e  mov     rcx, [rcx+40h]
0x140029f82  call    WPP_RECORDER_SF_qD
0x140029f87  jmp     loc_140029E00
```
