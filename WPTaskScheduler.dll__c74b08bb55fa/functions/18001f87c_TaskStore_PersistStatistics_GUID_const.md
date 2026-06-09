# TaskStore::PersistStatistics(_GUID const &)

- ea: `0x18001f87c`
- end: `0x18001f912`
- name: `?PersistStatistics@TaskStore@@QEAAJAEBU_GUID@@@Z`
- size: `150`
- prototype: `int(TaskStore *__hidden this, const struct _GUID *)`
- caller_count: `9`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800025b0`
- `0x180005e40`
- `0x1800074e0`
- `0x18000ef3c`
- `0x180017a74`
- `0x180017c04`
- `0x180018314`
- `0x1800185d4`
- `0x180018c94`

## callees

- `0x1800192ec`
- `0x18001e6ec`
- `0x18001f2b0`
- `0x18001f87c`
- `0x180020a48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f8fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f8fa`

## pseudocode

```c
__int64 __fastcall TaskStore::PersistStatistics(CScheduleMgr **this, struct _GUID *a2)
{
  int Schedule; // ebx
  __int64 v5; // rdx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  struct _TASK_STATISTICS *v8; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  Schedule = TaskStore::OpenKey((__int64)this, (GUIDParser *)a2, (__int64)&hKey);
  if ( Schedule >= 0 )
  {
    v8 = 0;
    Schedule = CScheduleMgr::GetSchedule(*this, a2, 0, &v8, 0);
    if ( Schedule >= 0 )
    {
      Schedule = anonymous_namespace_::EncodeKey__TASK_STATISTICS_(&hKey, v5, v8);
      TaskSchedulerFreeScheduleStatistics(v8);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)Schedule;
}

```

## disassembly

```asm
0x18001f87c  mov     rax, rsp
0x18001f87f  mov     [rax+8], rbx
0x18001f883  mov     [rax+10h], rsi
0x18001f887  push    rdi
0x18001f888  sub     rsp, 30h
0x18001f88c  mov     rdi, rdx
0x18001f88f  mov     rsi, rcx
0x18001f892  mov     qword ptr [rax+18h], 0
0x18001f89a  lea     r8, [rax+18h]
0x18001f89e  call    ?OpenKey@TaskStore@@AEAAJAEBU_GUID@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@Z; TaskStore::OpenKey(_GUID const &,tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f8a3  mov     ebx, eax
0x18001f8a5  test    eax, eax
0x18001f8a7  js      short loc_18001F8F0
0x18001f8a9  mov     [rsp+38h+arg_18], 0
0x18001f8b2  mov     [rsp+38h+var_18], 0; struct _TASK_RUNTIME_DATA **
0x18001f8bb  lea     r9, [rsp+38h+arg_18]; struct _TASK_STATISTICS **
0x18001f8c0  xor     r8d, r8d; struct _TASK_SCHEDULE **
0x18001f8c3  mov     rdx, rdi; struct _GUID *
0x18001f8c6  mov     rcx, [rsi]; this
0x18001f8c9  call    ?GetSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z; CScheduleMgr::GetSchedule(_GUID const *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)
0x18001f8ce  mov     ebx, eax
0x18001f8d0  test    eax, eax
0x18001f8d2  js      short loc_18001F8F0
0x18001f8d4  mov     r8, [rsp+38h+arg_18]
0x18001f8d9  lea     rcx, [rsp+38h+hKey]
0x18001f8de  call    _anonymous_namespace___EncodeKey__TASK_STATISTICS_
0x18001f8e3  mov     ebx, eax
0x18001f8e5  mov     rcx, [rsp+38h+arg_18]
0x18001f8ea  call    TaskSchedulerFreeScheduleStatistics
0x18001f8ef  nop
0x18001f8f0  mov     rcx, [rsp+38h+hKey]; hKey
0x18001f8f5  test    rcx, rcx
0x18001f8f8  jz      short loc_18001F900
0x18001f8fa  call    cs:__imp_RegCloseKey
0x18001f900  mov     eax, ebx
0x18001f902  mov     rbx, [rsp+38h+arg_0]
0x18001f907  mov     rsi, [rsp+38h+arg_8]
0x18001f90c  add     rsp, 30h
0x18001f910  pop     rdi
0x18001f911  retn
```
