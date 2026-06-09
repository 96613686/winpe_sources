# CScheduleMgr::DeleteExpiredWithWorker(_LIST_ENTRY *)

- ea: `0x18000d740`
- end: `0x18000d7e2`
- name: `?DeleteExpiredWithWorker@CScheduleMgr@@CAXPEAU_LIST_ENTRY@@@Z`
- size: `162`
- prototype: `void __fastcall(struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800188cc`
- `0x1800196e0`

## callees

- `0x18000d740`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d7da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d7da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000d779`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000d779`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d7d1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d7d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d75b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d75b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d78e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d78e`

## pseudocode

```c
void __fastcall CScheduleMgr::DeleteExpiredWithWorker(struct _LIST_ENTRY *a1)
{
  struct _LIST_ENTRY *i; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v4; // rbx
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *Flink; // rcx
  struct CSchedule *v7; // rax

  if ( a1->Flink != a1 )
  {
    EnterCriticalSection(&CScheduleMgr::CritLockExpired);
    for ( i = a1->Flink; a1->Flink != a1; i = a1->Flink )
    {
      Blink = i->Blink;
      Flink = i->Flink;
      Blink->Flink = i->Flink;
      Flink->Blink = Blink;
      v7 = CScheduleMgr::ExpiredScheduleList;
      i->Flink = (struct _LIST_ENTRY *)CScheduleMgr::ExpiredScheduleList;
      i->Blink = (struct _LIST_ENTRY *)&CScheduleMgr::ExpiredScheduleList;
      *((_QWORD *)v7 + 1) = i;
      CScheduleMgr::ExpiredScheduleList = (struct CSchedule *)i;
    }
    ThreadpoolWork = CreateThreadpoolWork(CScheduleMgr::DeleteExpiredWorker, 0, &ThreadpoolCallBackEnvironment);
    v4 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v4);
    }
    LeaveCriticalSection(&CScheduleMgr::CritLockExpired);
  }
}

```

## disassembly

```asm
0x18000d740  push    rbx
0x18000d742  sub     rsp, 20h
0x18000d746  mov     rbx, rcx
0x18000d749  cmp     [rcx], rcx
0x18000d74c  jnz     short loc_18000D754
0x18000d74e  add     rsp, 20h
0x18000d752  pop     rbx
0x18000d753  retn
0x18000d754  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d75b  call    cs:__imp_EnterCriticalSection
0x18000d761  mov     rdx, [rbx]
0x18000d764  cmp     rdx, rbx
0x18000d767  jnz     short loc_18000D796
0x18000d769  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18000d770  xor     edx, edx; pv
0x18000d772  lea     rcx, ?DeleteExpiredWorker@CScheduleMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000d779  call    cs:__imp_CreateThreadpoolWork
0x18000d77f  mov     rbx, rax
0x18000d782  test    rax, rax
0x18000d785  jnz     short loc_18000D7CE
0x18000d787  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d78e  call    cs:__imp_LeaveCriticalSection
0x18000d794  jmp     short loc_18000D74E
0x18000d796  lea     r8, ?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x18000d79d  mov     rax, [rdx+8]
0x18000d7a1  mov     rcx, [rdx]
0x18000d7a4  mov     [rax], rcx
0x18000d7a7  mov     [rcx+8], rax
0x18000d7ab  mov     rax, cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x18000d7b2  mov     [rdx], rax
0x18000d7b5  mov     [rdx+8], r8
0x18000d7b9  mov     [rax+8], rdx
0x18000d7bd  mov     cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A, rdx; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x18000d7c4  mov     rdx, [rbx]
0x18000d7c7  cmp     rdx, rbx
0x18000d7ca  jnz     short loc_18000D79D
0x18000d7cc  jmp     short loc_18000D769
0x18000d7ce  mov     rcx, rbx; pwk
0x18000d7d1  call    cs:__imp_SubmitThreadpoolWork
0x18000d7d7  mov     rcx, rbx; pwk
0x18000d7da  call    cs:__imp_CloseThreadpoolWork
0x18000d7e0  jmp     short loc_18000D787
```
