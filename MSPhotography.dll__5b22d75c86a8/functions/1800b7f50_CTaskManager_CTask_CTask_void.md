# CTaskManager::CTask::~CTask(void)

- ea: `0x1800b7f50`
- end: `0x1800b7fd5`
- name: `??1CTask@CTaskManager@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(CTaskManager::CTask *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800b7fdc`

## callees

- `0x1800b7f50`
- `0x1800b8090`
- `0x1800b8124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b7fc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b7fc1`

## pseudocode

```c
void __fastcall CTaskManager::CTask::~CTask(CTaskManager::CTask *this, unsigned int a2)
{
  __int64 i; // rax
  __int64 v4; // rdi
  CTaskManager::CTask::TASK_THREAD_INFO *v5; // [rsp+30h] [rbp+8h]

  for ( i = *((_QWORD *)this + 22); i; i = *((_QWORD *)this + 22) )
  {
    v4 = *(_QWORD *)(*((_QWORD *)this + 22) + 16LL);
    v5 = (CTaskManager::CTask::TASK_THREAD_INFO *)*((_QWORD *)this + 22);
    if ( v5 )
      CTaskManager::CTask::TASK_THREAD_INFO::`scalar deleting destructor'(v5, a2);
    *((_QWORD *)this + 22) = v4;
  }
  *((_QWORD *)this + 13) = &vt::ITaskWorkIdSequencer::`vftable';
  vt::CTaskStatusEvent::~CTaskStatusEvent((CTaskManager::CTask *)((char *)this + 48));
  if ( *(_BYTE *)this )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_BYTE *)this = 0;
  }
}

```

## disassembly

```asm
0x1800b7f50  mov     [rsp+arg_8], rbx
0x1800b7f55  push    rdi
0x1800b7f56  sub     rsp, 20h
0x1800b7f5a  mov     rax, [rcx+0B0h]
0x1800b7f61  mov     rbx, rcx
0x1800b7f64  jmp     short loc_1800B7F9F
0x1800b7f66  mov     rax, [rbx+0B0h]
0x1800b7f6d  mov     rdi, [rax+10h]
0x1800b7f71  mov     rax, [rbx+0B0h]
0x1800b7f78  mov     [rsp+28h+arg_0], rax
0x1800b7f7d  mov     rax, [rsp+28h+arg_0]
0x1800b7f82  test    rax, rax
0x1800b7f85  jz      short loc_1800B7F91
0x1800b7f87  mov     rcx, [rsp+28h+arg_0]; this
0x1800b7f8c  call    ??_GTASK_THREAD_INFO@CTask@CTaskManager@@QEAAPEAXI@Z; CTaskManager::CTask::TASK_THREAD_INFO::`scalar deleting destructor'(uint)
0x1800b7f91  mov     [rbx+0B0h], rdi
0x1800b7f98  mov     rax, [rbx+0B0h]
0x1800b7f9f  test    rax, rax
0x1800b7fa2  jnz     short loc_1800B7F66
0x1800b7fa4  lea     rax, ??_7ITaskWorkIdSequencer@vt@@6B@; const vt::ITaskWorkIdSequencer::`vftable'
0x1800b7fab  lea     rcx, [rbx+30h]; this
0x1800b7faf  mov     [rbx+68h], rax
0x1800b7fb3  call    ??1CTaskStatusEvent@vt@@QEAA@XZ; vt::CTaskStatusEvent::~CTaskStatusEvent(void)
0x1800b7fb8  cmp     byte ptr [rbx], 0
0x1800b7fbb  jz      short loc_1800B7FCA
0x1800b7fbd  lea     rcx, [rbx+8]; lpCriticalSection
0x1800b7fc1  call    cs:__imp_DeleteCriticalSection
0x1800b7fc7  mov     byte ptr [rbx], 0
0x1800b7fca  mov     rbx, [rsp+28h+arg_8]
0x1800b7fcf  add     rsp, 20h
0x1800b7fd3  pop     rdi
0x1800b7fd4  retn
```
