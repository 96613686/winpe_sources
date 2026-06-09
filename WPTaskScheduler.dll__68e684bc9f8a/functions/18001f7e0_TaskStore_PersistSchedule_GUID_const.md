# TaskStore::PersistSchedule(_GUID const &)

- ea: `0x18001f7e0`
- end: `0x18001f876`
- name: `?PersistSchedule@TaskStore@@QEAAJAEBU_GUID@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(CScheduleMgr **this, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800197f8`

## callees

- `0x1800192ec`
- `0x18001e5bc`
- `0x18001f2b0`
- `0x18001f7e0`
- `0x180020a2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f85e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f85e`

## pseudocode

```c
__int64 __fastcall TaskStore::PersistSchedule(CScheduleMgr **this, struct _GUID *a2)
{
  int Schedule; // ebx
  __int64 v5; // rdx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  struct _TASK_SCHEDULE *v8; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  Schedule = TaskStore::OpenKey((__int64)this, (GUIDParser *)a2, (__int64)&hKey);
  if ( Schedule >= 0 )
  {
    v8 = 0;
    Schedule = CScheduleMgr::GetSchedule(*this, a2, &v8, 0, 0);
    if ( Schedule >= 0 )
    {
      Schedule = anonymous_namespace_::EncodeKey__TASK_SCHEDULE_(&hKey, v5, v8);
      TaskSchedulerFreeSchedule(v8);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)Schedule;
}

```

## disassembly

```asm
0x18001f7e0  mov     rax, rsp
0x18001f7e3  mov     [rax+8], rbx
0x18001f7e7  mov     [rax+10h], rsi
0x18001f7eb  push    rdi
0x18001f7ec  sub     rsp, 30h
0x18001f7f0  mov     rdi, rdx
0x18001f7f3  mov     rsi, rcx
0x18001f7f6  mov     qword ptr [rax+18h], 0
0x18001f7fe  lea     r8, [rax+18h]
0x18001f802  call    ?OpenKey@TaskStore@@AEAAJAEBU_GUID@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@Z; TaskStore::OpenKey(_GUID const &,tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f807  mov     ebx, eax
0x18001f809  test    eax, eax
0x18001f80b  js      short loc_18001F854
0x18001f80d  mov     [rsp+38h+arg_18], 0
0x18001f816  mov     [rsp+38h+var_18], 0; struct _TASK_RUNTIME_DATA **
0x18001f81f  xor     r9d, r9d; struct _TASK_STATISTICS **
0x18001f822  lea     r8, [rsp+38h+arg_18]; struct _TASK_SCHEDULE **
0x18001f827  mov     rdx, rdi; struct _GUID *
0x18001f82a  mov     rcx, [rsi]; this
0x18001f82d  call    ?GetSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z; CScheduleMgr::GetSchedule(_GUID const *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)
0x18001f832  mov     ebx, eax
0x18001f834  test    eax, eax
0x18001f836  js      short loc_18001F854
0x18001f838  mov     r8, [rsp+38h+arg_18]
0x18001f83d  lea     rcx, [rsp+38h+hKey]
0x18001f842  call    _anonymous_namespace___EncodeKey__TASK_SCHEDULE_
0x18001f847  mov     ebx, eax
0x18001f849  mov     rcx, [rsp+38h+arg_18]
0x18001f84e  call    TaskSchedulerFreeSchedule
0x18001f853  nop
0x18001f854  mov     rcx, [rsp+38h+hKey]; hKey
0x18001f859  test    rcx, rcx
0x18001f85c  jz      short loc_18001F864
0x18001f85e  call    cs:__imp_RegCloseKey
0x18001f864  mov     eax, ebx
0x18001f866  mov     rbx, [rsp+38h+arg_0]
0x18001f86b  mov     rsi, [rsp+38h+arg_8]
0x18001f870  add     rsp, 30h
0x18001f874  pop     rdi
0x18001f875  retn
```
