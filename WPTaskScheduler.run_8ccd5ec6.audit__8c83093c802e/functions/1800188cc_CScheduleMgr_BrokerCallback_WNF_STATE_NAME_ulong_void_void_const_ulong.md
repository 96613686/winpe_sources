# CScheduleMgr::BrokerCallback(_WNF_STATE_NAME *,ulong,void *,void * const,ulong)

- ea: `0x1800188cc`
- end: `0x1800189fd`
- name: `?BrokerCallback@CScheduleMgr@@QEAAXPEAU_WNF_STATE_NAME@@KPEAXQEAXK@Z`
- size: `305`
- prototype: `void(CScheduleMgr *__hidden this, struct _WNF_STATE_NAME *, unsigned int, void *, void *const, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800187f0`

## callees

- `0x180005b10`
- `0x180005c30`
- `0x18000d080`
- `0x18000d740`
- `0x18000da60`
- `0x18000ea40`
- `0x180017a74`
- `0x1800188cc`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018916`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018916`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018936`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018936`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189ce`

## pseudocode

```c
void __fastcall CScheduleMgr::BrokerCallback(
        CScheduleMgr *this,
        struct _WNF_STATE_NAME *a2,
        __int64 a3,
        struct _GUID *a4,
        void *const a5)
{
  __int64 v7; // rcx
  __int64 v8; // r8
  CScheduleMgr *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r8
  struct _LIST_ENTRY v12; // [rsp+30h] [rbp-D0h] BYREF
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+150h] [rbp+50h] BYREF

  v12.Blink = &v12;
  v12.Flink = &v12;
  EnterCriticalSection(&CriticalSection);
  if ( (unsigned int)CScheduleMgr::ScheduleIsValid((CScheduleMgr *)&g_ScheduleMgr, (struct CSchedule *const)a4) )
  {
    if ( (byte_180030D06 & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(
        v7,
        (const EVENT_DESCRIPTOR *)BrokerFrameworkEventProcessingStart,
        v8,
        1u,
        &v14);
    TimeInfo::TimeInfo(&TimeZoneInformation);
    TimeInfo::LogTimeETW((TimeInfo *)&TimeZoneInformation);
    CSchedule::BrokerCallback(a4, (const struct TimeInfo *)&TimeZoneInformation, a2, a5);
    CScheduleMgr::ProcessExpired(v9, &v12, (struct CSchedule *)a4);
    if ( (byte_180030D06 & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(
        v10,
        (const EVENT_DESCRIPTOR *)BrokerFrameworkEventProcessingCompleted,
        v11,
        1u,
        &v14);
    LeaveCriticalSection(&CriticalSection);
    CScheduleMgr::DeleteExpiredWithWorker(&v12);
  }
  else
  {
    LeaveCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x1800188cc  mov     [rsp-8+arg_0], rbx
0x1800188d1  push    rbp
0x1800188d2  push    rsi
0x1800188d3  push    rdi
0x1800188d4  lea     rbp, [rsp-70h]
0x1800188d9  sub     rsp, 170h
0x1800188e0  mov     rax, cs:__security_cookie
0x1800188e7  xor     rax, rsp
0x1800188ea  mov     [rbp+80h+var_20], rax
0x1800188ee  mov     rsi, [rbp+80h+arg_20]
0x1800188f5  lea     rax, [rsp+180h+var_150]
0x1800188fa  mov     [rsp+180h+var_150.Blink], rax
0x1800188ff  lea     rcx, CriticalSection; lpCriticalSection
0x180018906  lea     rax, [rsp+180h+var_150]
0x18001890b  mov     rbx, r9
0x18001890e  mov     [rsp+180h+var_150.Flink], rax
0x180018913  mov     rdi, rdx
0x180018916  call    cs:__imp_EnterCriticalSection
0x18001891c  mov     rdx, rbx; struct CSchedule *
0x18001891f  lea     rcx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; this
0x180018926  call    ?ScheduleIsValid@CScheduleMgr@@AEAAHQEAVCSchedule@@@Z; CScheduleMgr::ScheduleIsValid(CSchedule * const)
0x18001892b  test    eax, eax
0x18001892d  jnz     short loc_180018941
0x18001892f  lea     rcx, CriticalSection; lpCriticalSection
0x180018936  call    cs:__imp_LeaveCriticalSection
0x18001893c  jmp     loc_1800189DE
0x180018941  test    cs:byte_180030D06, 4
0x180018948  jz      short loc_180018965
0x18001894a  lea     rax, [rbp+80h+var_30]
0x18001894e  mov     r9d, 1
0x180018954  lea     rdx, BrokerFrameworkEventProcessingStart
0x18001895b  mov     qword ptr [rsp+180h+var_160], rax
0x180018960  call    McGenEventWrite_EventWriteTransfer
0x180018965  lea     rcx, [rsp+180h+TimeZoneInformation]; lpTimeZoneInformation
0x18001896a  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x18001896f  lea     rcx, [rsp+180h+TimeZoneInformation]; this
0x180018974  call    ?LogTimeETW@TimeInfo@@QEBAXXZ; TimeInfo::LogTimeETW(void)
0x180018979  mov     eax, [rbp+80h+arg_28]
0x18001897f  lea     rdx, [rsp+180h+TimeZoneInformation]; struct TimeInfo *
0x180018984  mov     r9, rsi; void *
0x180018987  mov     [rsp+180h+var_160], eax; unsigned int
0x18001898b  mov     r8, rdi; struct _WNF_STATE_NAME *
0x18001898e  mov     rcx, rbx; this
0x180018991  call    ?BrokerCallback@CSchedule@@QEAAJAEBVTimeInfo@@PEAU_WNF_STATE_NAME@@QEAXK@Z; CSchedule::BrokerCallback(TimeInfo const &,_WNF_STATE_NAME *,void * const,ulong)
0x180018996  mov     r8, rbx; struct CSchedule *
0x180018999  lea     rdx, [rsp+180h+var_150]; struct _LIST_ENTRY *
0x18001899e  call    ?ProcessExpired@CScheduleMgr@@AEAAXPEAU_LIST_ENTRY@@PEAVCSchedule@@@Z; CScheduleMgr::ProcessExpired(_LIST_ENTRY *,CSchedule *)
0x1800189a3  test    cs:byte_180030D06, 4
0x1800189aa  jz      short loc_1800189C7
0x1800189ac  lea     rax, [rbp+80h+var_30]
0x1800189b0  mov     r9d, 1
0x1800189b6  lea     rdx, BrokerFrameworkEventProcessingCompleted
0x1800189bd  mov     qword ptr [rsp+180h+var_160], rax
0x1800189c2  call    McGenEventWrite_EventWriteTransfer
0x1800189c7  lea     rcx, CriticalSection; lpCriticalSection
0x1800189ce  call    cs:__imp_LeaveCriticalSection
0x1800189d4  lea     rcx, [rsp+180h+var_150]; struct _LIST_ENTRY *
0x1800189d9  call    ?DeleteExpiredWithWorker@CScheduleMgr@@CAXPEAU_LIST_ENTRY@@@Z; CScheduleMgr::DeleteExpiredWithWorker(_LIST_ENTRY *)
0x1800189de  mov     rcx, [rbp+80h+var_20]
0x1800189e2  xor     rcx, rsp; StackCookie
0x1800189e5  call    __security_check_cookie
0x1800189ea  mov     rbx, [rsp+180h+arg_0]
0x1800189f2  add     rsp, 170h
0x1800189f9  pop     rdi
0x1800189fa  pop     rsi
0x1800189fb  pop     rbp
0x1800189fc  retn
```
