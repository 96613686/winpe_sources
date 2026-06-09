# IssueTaskResult

- ea: `0x1400180c8`
- end: `0x14001810a`
- name: `IssueTaskResult`
- size: `66`
- prototype: `__int64 __fastcall(struct TASK_PAYLOAD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140017d70`
- `0x140018014`
- `0x140018068`

## callees

- `0x140017498`
- `0x140017be4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400180d8`
- `KERNEL32!EnterCriticalSection` at `0x1400180d8`
- `KERNEL32!LeaveCriticalSection` at `0x1400180fc`
- `KERNEL32!LeaveCriticalSection` at `0x1400180fc`

## pseudocode

```c
__int64 __fastcall IssueTaskResult(struct TASK_PAYLOAD *a1)
{
  void *TaskServerHandle; // rax
  void *v3; // rdx

  EnterCriticalSection(&TaskLock);
  TaskServerHandle = (void *)GetTaskServerHandle(2u);
  LODWORD(a1) = WriteTaskPipe(TaskServerHandle, v3, a1);
  LeaveCriticalSection(&TaskLock);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x1400180c8  push    rbx
0x1400180ca  sub     rsp, 20h
0x1400180ce  mov     rbx, rcx
0x1400180d1  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x1400180d8  call    cs:__imp_EnterCriticalSection
0x1400180de  mov     ecx, 2; unsigned int
0x1400180e3  call    ?GetTaskServerHandle@@YAPEAXI@Z; GetTaskServerHandle(uint)
0x1400180e8  mov     rcx, rax; void *
0x1400180eb  mov     r8, rbx; struct TASK_PAYLOAD *
0x1400180ee  call    ?WriteTaskPipe@@YAHPEAX0PEBUTASK_PAYLOAD@@@Z; WriteTaskPipe(void *,void *,TASK_PAYLOAD const *)
0x1400180f3  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x1400180fa  mov     ebx, eax
0x1400180fc  call    cs:__imp_LeaveCriticalSection
0x140018102  mov     eax, ebx
0x140018104  add     rsp, 20h
0x140018108  pop     rbx
0x140018109  retn
```
