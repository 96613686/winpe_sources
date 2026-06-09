# Task::~Task(void)

- ea: `0x140023bf4`
- end: `0x140023ce7`
- name: `??1Task@@UEAA@XZ`
- size: `243`
- prototype: `void __fastcall(Task *__hidden this)`
- caller_count: `19`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001efb8`
- `0x14001f170`
- `0x14001f1e8`
- `0x14001f268`
- `0x14001f2c8`
- `0x14001fd60`
- `0x14001fea8`
- `0x1400203f0`
- `0x1400235ec`
- `0x140068460`
- `0x14006fca8`
- `0x1400856ac`
- `0x1400a65c0`
- `0x1400a7ef0`
- `0x1400a7f64`
- `0x1400ab69c`
- `0x1400ab7cc`
- `0x1400ae608`
- `0x1400be314`

## callees

- `0x1400236f4`
- `0x140023bf4`
- `0x140023cf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140023c67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023ca4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023c67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023ca4`

## pseudocode

```c
void __fastcall Task::~Task(Task *this)
{
  unsigned int m_NotificationRegistrationToken; // edx
  unsigned int m_TimerRegistrationToken; // edx
  unsigned __int8 *m_OutputBuffer; // rcx
  unsigned __int8 *v5; // rcx

  m_NotificationRegistrationToken = this->m_NotificationRegistrationToken;
  this->IOperationCompletionCallback::__vftable = (Task_vtbl *)&Task::`vftable'{for `IOperationCompletionCallback'};
  this->IEventQueueCallback::__vftable = (IEventQueueCallback_vtbl *)&Task::`vftable'{for `IEventQueueCallback'};
  this->INotifyDeviceIndicationCallback::__vftable = (INotifyDeviceIndicationCallback_vtbl *)&Task::`vftable'{for `INotifyDeviceIndicationCallback'};
  this->ITimerCallback::__vftable = (ITimerCallback_vtbl *)&Task::`vftable'{for `ITimerCallback'};
  if ( m_NotificationRegistrationToken )
  {
    NotificationManager::DeregisterNotificationHandler(this->m_pNotificationManager, m_NotificationRegistrationToken);
    this->m_NotificationRegistrationToken = 0;
  }
  m_TimerRegistrationToken = this->m_TimerRegistrationToken;
  if ( m_TimerRegistrationToken )
  {
    EventQueue::DeregisterTimeoutCallback(this->m_pEventQueue, m_TimerRegistrationToken);
    this->m_TimerRegistrationToken = 0;
  }
  m_OutputBuffer = this->m_OutputBuffer;
  if ( m_OutputBuffer )
  {
    ExFreePoolWithTag(m_OutputBuffer, 0x47696457u);
    this->m_OutputBuffer = 0;
    this->m_OutputBufferLength = 0;
  }
  v5 = this->m_TaskDeviceCommand.m_OutputBuffer;
  this->m_TaskDeviceCommand.__vftable = (DeviceCommand_vtbl *)&DeviceCommand::`vftable';
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0x47696457u);
    this->m_TaskDeviceCommand.m_OutputBuffer = 0;
    this->m_TaskDeviceCommand.m_OutputBufferLength = 0;
  }
}

```

## disassembly

```asm
0x140023bf4  push    rbx
0x140023bf6  sub     rsp, 20h
0x140023bfa  mov     edx, [rcx+108h]; unsigned int
0x140023c00  lea     rax, ??_7Task@@6BIOperationCompletionCallback@@@; const Task::`vftable'{for `IOperationCompletionCallback'}
0x140023c07  mov     [rcx], rax
0x140023c0a  lea     rax, ??_7Task@@6BIEventQueueCallback@@@; const Task::`vftable'{for `IEventQueueCallback'}
0x140023c11  mov     [rcx+8], rax
0x140023c15  lea     rax, ??_7Task@@6BINotifyDeviceIndicationCallback@@@; const Task::`vftable'{for `INotifyDeviceIndicationCallback'}
0x140023c1c  mov     [rcx+10h], rax
0x140023c20  lea     rax, ??_7Task@@6BITimerCallback@@@; const Task::`vftable'{for `ITimerCallback'}
0x140023c27  mov     [rcx+18h], rax
0x140023c2b  mov     rbx, rcx
0x140023c2e  test    edx, edx
0x140023c30  jnz     loc_140023CCC
0x140023c36  mov     edx, [rbx+1BCh]; unsigned int
0x140023c3c  test    edx, edx
0x140023c3e  jz      short loc_140023C56
0x140023c40  mov     rcx, [rbx+0F0h]; this
0x140023c47  call    ?DeregisterTimeoutCallback@EventQueue@@QEAAHI@Z; EventQueue::DeregisterTimeoutCallback(uint)
0x140023c4c  mov     dword ptr [rbx+1BCh], 0
0x140023c56  mov     rcx, [rbx+1B0h]; P
0x140023c5d  test    rcx, rcx
0x140023c60  jz      short loc_140023C88
0x140023c62  mov     edx, 47696457h; Tag
0x140023c67  call    cs:__imp_ExFreePoolWithTag
0x140023c6e  nop     dword ptr [rax+rax+00h]
0x140023c73  mov     qword ptr [rbx+1B0h], 0
0x140023c7e  mov     dword ptr [rbx+1ACh], 0
0x140023c88  mov     rcx, [rbx+0D0h]; P
0x140023c8f  lea     rax, ??_7DeviceCommand@@6B@; const DeviceCommand::`vftable'
0x140023c96  mov     [rbx+38h], rax
0x140023c9a  test    rcx, rcx
0x140023c9d  jz      short loc_140023CC5
0x140023c9f  mov     edx, 47696457h; Tag
0x140023ca4  call    cs:__imp_ExFreePoolWithTag
0x140023cab  nop     dword ptr [rax+rax+00h]
0x140023cb0  mov     qword ptr [rbx+0D0h], 0
0x140023cbb  mov     dword ptr [rbx+0C8h], 0
0x140023cc5  add     rsp, 20h
0x140023cc9  pop     rbx
0x140023cca  retn
0x140023ccc  mov     rcx, [rcx+110h]; this
0x140023cd3  call    ?DeregisterNotificationHandler@NotificationManager@@QEAAHK@Z; NotificationManager::DeregisterNotificationHandler(ulong)
0x140023cd8  mov     dword ptr [rbx+108h], 0
0x140023ce2  jmp     loc_140023C36
```
