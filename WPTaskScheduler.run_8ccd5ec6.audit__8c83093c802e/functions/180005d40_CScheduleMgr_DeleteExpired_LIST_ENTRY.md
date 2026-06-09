# CScheduleMgr::DeleteExpired(_LIST_ENTRY *)

- ea: `0x180005d40`
- end: `0x180005e2c`
- name: `?DeleteExpired@CScheduleMgr@@CAXPEAU_LIST_ENTRY@@@Z`
- size: `236`
- prototype: `void __fastcall(struct _LIST_ENTRY *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005440`
- `0x1800185d4`
- `0x180018c94`
- `0x1800197f8`

## callees

- `0x180001ef0`
- `0x180002010`
- `0x180005d40`
- `0x180022010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005df6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005df6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005d59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005d59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e25`

## pseudocode

```c
void __fastcall CScheduleMgr::DeleteExpired(struct _LIST_ENTRY *a1)
{
  struct _LIST_ENTRY *v2; // rdx
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rax
  struct CSchedule *v5; // rbx
  struct CSchedule *v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rcx

  EnterCriticalSection(&CScheduleMgr::CritLockExpired);
  Flink = a1->Flink;
  if ( a1->Flink == a1 )
  {
    v5 = CScheduleMgr::ExpiredScheduleList;
  }
  else
  {
    do
    {
      Blink = Flink->Blink;
      v5 = (struct CSchedule *)Flink;
      v2 = Flink->Flink;
      Blink->Flink = Flink->Flink;
      v2->Blink = Blink;
      v6 = CScheduleMgr::ExpiredScheduleList;
      Flink->Flink = (struct _LIST_ENTRY *)CScheduleMgr::ExpiredScheduleList;
      Flink->Blink = (struct _LIST_ENTRY *)&CScheduleMgr::ExpiredScheduleList;
      *((_QWORD *)v6 + 1) = Flink;
      CScheduleMgr::ExpiredScheduleList = (struct CSchedule *)Flink;
      Flink = a1->Flink;
    }
    while ( a1->Flink != a1 );
  }
  if ( v5 != (struct CSchedule *)&CScheduleMgr::ExpiredScheduleList )
  {
    do
    {
      v7 = (_QWORD *)*((_QWORD *)v5 + 1);
      v8 = *(_QWORD *)v5;
      *v7 = *(_QWORD *)v5;
      *(_QWORD *)(v8 + 8) = v7;
      v9 = _InterlockedExchange64((volatile __int64 *)&DeletingSchedule, (__int64)v5);
      if ( v5 )
      {
        v10 = *((_QWORD *)v5 + 27);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
        CSchedule::Deinitialize(v5, (unsigned int)v2);
        CSchedule::~CSchedule((void **)v5);
        operator delete(v5);
      }
      _InterlockedExchange64((volatile __int64 *)&DeletingSchedule, v9);
      v5 = CScheduleMgr::ExpiredScheduleList;
    }
    while ( CScheduleMgr::ExpiredScheduleList != (struct CSchedule *)&CScheduleMgr::ExpiredScheduleList );
  }
  LeaveCriticalSection(&CScheduleMgr::CritLockExpired);
}

```

## disassembly

```asm
0x180005d40  mov     [rsp+arg_0], rbx
0x180005d45  mov     [rsp+arg_8], rsi
0x180005d4a  push    rdi
0x180005d4b  sub     rsp, 20h
0x180005d4f  mov     rdi, rcx
0x180005d52  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005d59  call    cs:__imp_EnterCriticalSection
0x180005d5f  mov     rcx, [rdi]
0x180005d62  lea     rsi, ?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180005d69  cmp     rcx, rdi
0x180005d6c  jz      short loc_180005DA2
0x180005d6e  mov     rax, [rcx+8]
0x180005d72  mov     rbx, rcx
0x180005d75  mov     rdx, [rcx]
0x180005d78  mov     [rax], rdx
0x180005d7b  mov     [rdx+8], rax
0x180005d7f  mov     rax, cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180005d86  mov     [rcx], rax
0x180005d89  mov     [rcx+8], rsi
0x180005d8d  mov     [rax+8], rcx
0x180005d91  mov     cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A, rcx; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180005d98  mov     rcx, [rdi]
0x180005d9b  cmp     rcx, rdi
0x180005d9e  jnz     short loc_180005D6E
0x180005da0  jmp     short loc_180005DA9
0x180005da2  mov     rbx, cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180005da9  cmp     rbx, rsi
0x180005dac  jz      short loc_180005E0F
0x180005dae  mov     rax, [rbx+8]
0x180005db2  mov     rdi, rbx
0x180005db5  mov     rcx, [rbx]
0x180005db8  mov     [rax], rcx
0x180005dbb  mov     [rcx+8], rax
0x180005dbf  xchg    rdi, cs:?DeletingSchedule@@3PEAVCSchedule@@EA; CSchedule * DeletingSchedule
0x180005dc6  test    rbx, rbx
0x180005dc9  jz      short loc_180005DFC
0x180005dcb  mov     rcx, [rbx+0D8h]
0x180005dd2  test    rcx, rcx
0x180005dd5  jz      short loc_180005DE3
0x180005dd7  mov     rax, [rcx]
0x180005dda  mov     rax, [rax+18h]
0x180005dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de3  mov     rcx, rbx; this
0x180005de6  call    ?Deinitialize@CSchedule@@QEAAXXZ; CSchedule::Deinitialize(void)
0x180005deb  mov     rcx, rbx; this
0x180005dee  call    ??1CSchedule@@QEAA@XZ; CSchedule::~CSchedule(void)
0x180005df3  mov     rcx, rbx
0x180005df6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005dfc  xchg    rdi, cs:?DeletingSchedule@@3PEAVCSchedule@@EA; CSchedule * DeletingSchedule
0x180005e03  mov     rbx, cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180005e0a  cmp     rbx, rsi
0x180005e0d  jnz     short loc_180005DAE
0x180005e0f  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CScheduleMgr::CritLockExpired
0x180005e16  mov     rbx, [rsp+28h+arg_0]
0x180005e1b  mov     rsi, [rsp+28h+arg_8]
0x180005e20  add     rsp, 20h
0x180005e24  pop     rdi
0x180005e25  jmp     cs:__imp_LeaveCriticalSection
```
