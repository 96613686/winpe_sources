# TaskStore::Persist(_GUID const &)

- ea: `0x18001f3ec`
- end: `0x18001f4d3`
- name: `?Persist@TaskStore@@QEAAJAEBU_GUID@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(CScheduleMgr **this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180006410`

## callees

- `0x1800192ec`
- `0x18001e48c`
- `0x18001e5bc`
- `0x18001e6ec`
- `0x18001f2b0`
- `0x18001f3ec`
- `0x1800209f8`
- `0x180020a2c`
- `0x180020a48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f4be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f4be`

## pseudocode

```c
__int64 __fastcall TaskStore::Persist(CScheduleMgr **this, const struct _GUID *a2)
{
  int Schedule; // ebx
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  struct _TASK_RUNTIME_DATA *v8; // rdi
  struct _TASK_STATISTICS *v9; // rdi
  struct _TASK_RUNTIME_DATA *v11; // [rsp+30h] [rbp-10h] BYREF
  struct _TASK_STATISTICS *v12; // [rsp+38h] [rbp-8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  struct _TASK_SCHEDULE *v14; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  Schedule = TaskStore::OpenKey(this, a2, &hKey);
  if ( Schedule >= 0 )
  {
    v14 = 0;
    v12 = 0;
    v11 = 0;
    Schedule = CScheduleMgr::GetSchedule(*this, a2, &v14, &v12, &v11);
    if ( Schedule >= 0 )
    {
      v6 = anonymous_namespace_::EncodeKey__TASK_SCHEDULE_(&hKey, v5, v14);
      Schedule = v6;
      v8 = v11;
      if ( v11 )
      {
        if ( v6 >= 0 )
          Schedule = anonymous_namespace_::EncodeKey__TASK_RUNTIME_DATA_(&hKey, v7, v11);
        TaskSchedulerFreeRunTime(v8);
      }
      v9 = v12;
      if ( v12 )
      {
        if ( Schedule >= 0 )
          Schedule = anonymous_namespace_::EncodeKey__TASK_STATISTICS_(&hKey, v7, v12);
        TaskSchedulerFreeScheduleStatistics(v9);
      }
      TaskSchedulerFreeSchedule(v14);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)Schedule;
}

```

## disassembly

```asm
0x18001f3ec  mov     [rsp-18h+arg_0], rbx
0x18001f3f1  push    rbp
0x18001f3f2  push    rsi
0x18001f3f3  push    rdi
0x18001f3f4  mov     rbp, rsp
0x18001f3f7  sub     rsp, 40h
0x18001f3fb  mov     rdi, rdx
0x18001f3fe  mov     rsi, rcx
0x18001f401  mov     [rbp+hKey], 0
0x18001f409  lea     r8, [rbp+hKey]
0x18001f40d  call    ?OpenKey@TaskStore@@AEAAJAEBU_GUID@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@Z; TaskStore::OpenKey(_GUID const &,tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f412  mov     ebx, eax
0x18001f414  test    eax, eax
0x18001f416  js      loc_18001F4B5
0x18001f41c  mov     [rbp+arg_18], 0
0x18001f424  mov     [rbp+var_8], 0
0x18001f42c  mov     [rbp+var_10], 0
0x18001f434  lea     rax, [rbp+var_10]
0x18001f438  mov     [rsp+40h+var_20], rax; struct _TASK_RUNTIME_DATA **
0x18001f43d  lea     r9, [rbp+var_8]; struct _TASK_STATISTICS **
0x18001f441  lea     r8, [rbp+arg_18]; struct _TASK_SCHEDULE **
0x18001f445  mov     rdx, rdi; struct _GUID *
0x18001f448  mov     rcx, [rsi]; this
0x18001f44b  call    ?GetSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z; CScheduleMgr::GetSchedule(_GUID const *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)
0x18001f450  mov     ebx, eax
0x18001f452  test    eax, eax
0x18001f454  js      short loc_18001F4B5
0x18001f456  mov     r8, [rbp+arg_18]
0x18001f45a  lea     rcx, [rbp+hKey]
0x18001f45e  call    _anonymous_namespace___EncodeKey__TASK_SCHEDULE_
0x18001f463  mov     ebx, eax
0x18001f465  mov     rdi, [rbp+var_10]
0x18001f469  test    rdi, rdi
0x18001f46c  jz      short loc_18001F488
0x18001f46e  test    eax, eax
0x18001f470  js      short loc_18001F480
0x18001f472  mov     r8, rdi
0x18001f475  lea     rcx, [rbp+hKey]
0x18001f479  call    _anonymous_namespace___EncodeKey__TASK_RUNTIME_DATA_
0x18001f47e  mov     ebx, eax
0x18001f480  mov     rcx, rdi; void *
0x18001f483  call    TaskSchedulerFreeRunTime
0x18001f488  mov     rdi, [rbp+var_8]
0x18001f48c  test    rdi, rdi
0x18001f48f  jz      short loc_18001F4AB
0x18001f491  test    ebx, ebx
0x18001f493  js      short loc_18001F4A3
0x18001f495  mov     r8, rdi
0x18001f498  lea     rcx, [rbp+hKey]
0x18001f49c  call    _anonymous_namespace___EncodeKey__TASK_STATISTICS_
0x18001f4a1  mov     ebx, eax
0x18001f4a3  mov     rcx, rdi
0x18001f4a6  call    TaskSchedulerFreeScheduleStatistics
0x18001f4ab  mov     rcx, [rbp+arg_18]
0x18001f4af  call    TaskSchedulerFreeSchedule
0x18001f4b4  nop
0x18001f4b5  mov     rcx, [rbp+hKey]; hKey
0x18001f4b9  test    rcx, rcx
0x18001f4bc  jz      short loc_18001F4C4
0x18001f4be  call    cs:__imp_RegCloseKey
0x18001f4c4  mov     eax, ebx
0x18001f4c6  mov     rbx, [rsp+40h+arg_0]
0x18001f4cb  add     rsp, 40h
0x18001f4cf  pop     rdi
0x18001f4d0  pop     rsi
0x18001f4d1  pop     rbp
0x18001f4d2  retn
```
