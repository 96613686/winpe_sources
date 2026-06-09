# CScheduleMgr::Deinitialize(void)

- ea: `0x18000ef3c`
- end: `0x18000f0b7`
- name: `?Deinitialize@CScheduleMgr@@QEAAXXZ`
- size: `379`
- prototype: `void __fastcall(CScheduleMgr *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015b08`

## callees

- `0x180001ea0`
- `0x18000ef3c`
- `0x18000f3f4`
- `0x18001f65c`
- `0x18001f87c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f037`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f037`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f025`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000ef57`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f06c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000ef57`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f06c`

## pseudocode

```c
void __fastcall CScheduleMgr::Deinitialize(CScheduleMgr *this)
{
  __int64 v1; // rdx
  _QWORD *v2; // rax
  struct CSchedule *v3; // rcx
  struct _GUID *v4; // rdi
  __int64 *v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rax
  __int64 v8; // rbx
  __int64 i; // rax

  if ( qword_180030BF0 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(qword_180030BF0);
    qword_180030BF0 = 0;
  }
  EnterCriticalSection(&CScheduleMgr::CritLockExpired);
  while ( 1 )
  {
    v3 = CScheduleMgr::ExpiredScheduleList;
    if ( CScheduleMgr::ExpiredScheduleList == (struct CSchedule *)&CScheduleMgr::ExpiredScheduleList )
      break;
    v1 = *(_QWORD *)CScheduleMgr::ExpiredScheduleList;
    v2 = (_QWORD *)*((_QWORD *)CScheduleMgr::ExpiredScheduleList + 1);
    *v2 = *(_QWORD *)CScheduleMgr::ExpiredScheduleList;
    *(_QWORD *)(v1 + 8) = v2;
    CSchedule::DestroySchedule(v3, 1);
  }
  LeaveCriticalSection(&CScheduleMgr::CritLockExpired);
  EnterCriticalSection(&CriticalSection);
  while ( 1 )
  {
    v5 = (__int64 *)g_ScheduleMgr;
    if ( (_UNKNOWN *)g_ScheduleMgr == &g_ScheduleMgr )
      break;
    v4 = (struct _GUID *)g_ScheduleMgr;
    if ( qword_180030AC8 && (*(_BYTE *)(g_ScheduleMgr + 44LL) & 1) != 0 )
    {
      TaskStore::PersistStatistics(qword_180030AC8, (const struct _GUID *)(g_ScheduleMgr + 16LL));
      TaskStore::PersistRuntimeData(qword_180030AC8, v4 + 1, 0);
      v5 = (__int64 *)g_ScheduleMgr;
    }
    v6 = *v5;
    v7 = (_QWORD *)v5[1];
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    CSchedule::DestroySchedule((struct CSchedule *)v4, 0);
  }
  LeaveCriticalSection(&CriticalSection);
  if ( qword_180030AC8 )
  {
    operator delete(qword_180030AC8);
    qword_180030AC8 = 0;
  }
  if ( *((_QWORD *)&xmmword_180030BE0 + 1) )
  {
    v8 = *(_QWORD *)xmmword_180030BE0;
    while ( v8 != (_QWORD)xmmword_180030BE0 )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion(**(_QWORD **)(v8 + 40));
      if ( !*(_BYTE *)(v8 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v8 + 16) + 25LL) )
        {
          for ( i = *(_QWORD *)(v8 + 8); !*(_BYTE *)(i + 25) && v8 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v8 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>>::_Min();
        }
        v8 = i;
      }
    }
  }
}

```

## disassembly

```asm
0x18000ef3c  mov     [rsp+arg_0], rbx
0x18000ef41  mov     [rsp+arg_8], rbp
0x18000ef46  push    rdi
0x18000ef47  sub     rsp, 20h
0x18000ef4b  mov     rcx, cs:qword_180030BF0
0x18000ef52  test    rcx, rcx
0x18000ef55  jz      short loc_18000EF68
0x18000ef57  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000ef5d  mov     cs:qword_180030BF0, 0
0x18000ef68  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ef6f  call    cs:__imp_EnterCriticalSection
0x18000ef75  lea     rbx, ?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x18000ef7c  jmp     short loc_18000EF93
0x18000ef7e  mov     rdx, [rcx]
0x18000ef81  mov     rax, [rcx+8]
0x18000ef85  mov     [rax], rdx
0x18000ef88  mov     [rdx+8], rax
0x18000ef8c  mov     dl, 1; bool
0x18000ef8e  call    ?DestroySchedule@CSchedule@@SAXPEAV1@_N@Z; CSchedule::DestroySchedule(CSchedule *,bool)
0x18000ef93  mov     rcx, cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; this
0x18000ef9a  cmp     rcx, rbx
0x18000ef9d  jnz     short loc_18000EF7E
0x18000ef9f  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000efa6  call    cs:__imp_LeaveCriticalSection
0x18000efac  lea     rcx, CriticalSection; lpCriticalSection
0x18000efb3  call    cs:__imp_EnterCriticalSection
0x18000efb9  lea     rbp, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x18000efc0  jmp     short loc_18000F012
0x18000efc2  mov     rcx, cs:qword_180030AC8; this
0x18000efc9  mov     rdi, rax
0x18000efcc  test    rcx, rcx
0x18000efcf  jz      short loc_18000EFFA
0x18000efd1  test    byte ptr [rax+2Ch], 1
0x18000efd5  jz      short loc_18000EFFA
0x18000efd7  lea     rdx, [rax+10h]; struct _GUID *
0x18000efdb  call    ?PersistStatistics@TaskStore@@QEAAJAEBU_GUID@@@Z; TaskStore::PersistStatistics(_GUID const &)
0x18000efe0  mov     rcx, cs:qword_180030AC8; this
0x18000efe7  lea     rdx, [rdi+10h]; struct _GUID *
0x18000efeb  xor     r8d, r8d; bool
0x18000efee  call    ?PersistRuntimeData@TaskStore@@QEAAJAEBU_GUID@@_N@Z; TaskStore::PersistRuntimeData(_GUID const &,bool)
0x18000eff3  mov     rax, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x18000effa  mov     rdx, [rax]
0x18000effd  mov     rcx, rdi; this
0x18000f000  mov     rax, [rax+8]
0x18000f004  mov     [rax], rdx
0x18000f007  mov     [rdx+8], rax
0x18000f00b  xor     edx, edx; bool
0x18000f00d  call    ?DestroySchedule@CSchedule@@SAXPEAV1@_N@Z; CSchedule::DestroySchedule(CSchedule *,bool)
0x18000f012  mov     rax, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x18000f019  cmp     rax, rbp
0x18000f01c  jnz     short loc_18000EFC2
0x18000f01e  lea     rcx, CriticalSection; lpCriticalSection
0x18000f025  call    cs:__imp_LeaveCriticalSection
0x18000f02b  mov     rcx, cs:qword_180030AC8
0x18000f032  test    rcx, rcx
0x18000f035  jz      short loc_18000F048
0x18000f037  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f03d  mov     cs:qword_180030AC8, 0
0x18000f048  cmp     qword ptr cs:xmmword_180030BE0+8, 0
0x18000f050  jz      short loc_18000F0A7
0x18000f052  mov     rbx, qword ptr cs:xmmword_180030BE0
0x18000f059  mov     rbx, [rbx]
0x18000f05c  cmp     rbx, qword ptr cs:xmmword_180030BE0
0x18000f063  jz      short loc_18000F0A7
0x18000f065  mov     rcx, [rbx+28h]
0x18000f069  mov     rcx, [rcx]
0x18000f06c  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000f072  cmp     byte ptr [rbx+19h], 0
0x18000f076  jnz     short loc_18000F05C
0x18000f078  mov     rcx, [rbx+10h]
0x18000f07c  cmp     byte ptr [rcx+19h], 0
0x18000f080  jnz     short loc_18000F089
0x18000f082  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>>::_Min(std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *)
0x18000f087  jmp     short loc_18000F0A2
0x18000f089  mov     rax, [rbx+8]
0x18000f08d  jmp     short loc_18000F09C
0x18000f08f  cmp     rbx, [rax+10h]
0x18000f093  jnz     short loc_18000F0A2
0x18000f095  mov     rbx, rax
0x18000f098  mov     rax, [rax+8]
0x18000f09c  cmp     byte ptr [rax+19h], 0
0x18000f0a0  jz      short loc_18000F08F
0x18000f0a2  mov     rbx, rax
0x18000f0a5  jmp     short loc_18000F05C
0x18000f0a7  mov     rbx, [rsp+28h+arg_0]
0x18000f0ac  mov     rbp, [rsp+28h+arg_8]
0x18000f0b1  add     rsp, 20h
0x18000f0b5  pop     rdi
0x18000f0b6  retn
```
