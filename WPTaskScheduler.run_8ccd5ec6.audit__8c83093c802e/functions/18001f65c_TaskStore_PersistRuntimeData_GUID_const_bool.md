# TaskStore::PersistRuntimeData(_GUID const &,bool)

- ea: `0x18001f65c`
- end: `0x18001f7da`
- name: `?PersistRuntimeData@TaskStore@@QEAAJAEBU_GUID@@_N@Z`
- size: `382`
- prototype: `int(TaskStore *__hidden this, const struct _GUID *, bool)`
- caller_count: `11`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800025b0`
- `0x180005440`
- `0x180005e40`
- `0x1800074e0`
- `0x18000ef3c`
- `0x180017a74`
- `0x180017c04`
- `0x180018314`
- `0x1800185d4`
- `0x180018c94`
- `0x1800197f8`

## callees

- `0x18000c700`
- `0x18000e634`
- `0x1800192ec`
- `0x18001e48c`
- `0x18001f2b0`
- `0x18001f65c`
- `0x18001f9e0`
- `0x1800209f8`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f74d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f7ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f74d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f7ae`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001f776`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001f776`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskStore::PersistRuntimeData(CScheduleMgr **this, struct _GUID *a2, char a3)
{
  int Schedule; // ebx
  __int64 v8; // rdx
  FILETIME *v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // rcx
  HKEY hKey; // [rsp+30h] [rbp-49h] BYREF
  FILETIME *lpFileTime; // [rsp+38h] [rbp-41h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-39h] BYREF
  struct _SYSTEMTIME v15; // [rsp+50h] [rbp-29h] BYREF
  struct _SYSTEMTIME v16; // [rsp+80h] [rbp+7h] BYREF

  *(_QWORD *)&SystemTime.wYear = 0;
  hKey = 0;
  Schedule = TaskStore::OpenKey((__int64)this, (GUIDParser *)a2, (__int64)&hKey);
  if ( Schedule < 0
    || (lpFileTime = 0,
        Schedule = CScheduleMgr::GetSchedule(*this, a2, 0, 0, (struct _TASK_RUNTIME_DATA **)&lpFileTime),
        Schedule < 0) )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)Schedule;
  }
  else
  {
    v9 = lpFileTime;
    if ( lpFileTime )
    {
      if ( a3
        && (TimeValue::Set(&v15, (const struct _FILETIME *)&SystemTime),
            TimeValue::Set(&v16, v9),
            (unsigned int)operator==(&v16, &v15)) )
      {
        TaskSchedulerFreeRunTime(v9);
        if ( hKey )
          RegCloseKey(hKey);
        return 1;
      }
      else
      {
        v10 = anonymous_namespace_::EncodeKey__TASK_RUNTIME_DATA_(&hKey, v8, v9);
        SystemTime = 0;
        FileTimeToSystemTime(v9, &SystemTime);
        if ( (byte_180030D09 & 0x20) != 0 )
          McTemplateU0jyq_EventWriteTransfer(v11, PersistingLastNextRunTime, a2, &SystemTime, v10);
        TaskSchedulerFreeRunTime(v9);
        if ( hKey )
          RegCloseKey(hKey);
        return v10;
      }
    }
    else
    {
      if ( hKey )
        RegCloseKey(hKey);
      return 2147500037LL;
    }
  }
}

```

## disassembly

```asm
0x18001f65c  mov     [rsp-8+arg_10], rbx
0x18001f661  mov     [rsp-8+arg_18], rsi
0x18001f666  push    rbp
0x18001f667  push    rdi
0x18001f668  push    r14
0x18001f66a  lea     rbp, [rsp-47h]
0x18001f66f  sub     rsp, 0C0h
0x18001f676  mov     rax, cs:__security_cookie
0x18001f67d  xor     rax, rsp
0x18001f680  mov     [rbp+57h+var_20], rax
0x18001f684  mov     dil, r8b
0x18001f687  mov     rsi, rdx
0x18001f68a  mov     r14, rcx
0x18001f68d  mov     qword ptr [rbp+57h+SystemTime.wYear], 0
0x18001f695  mov     [rbp+57h+hKey], 0
0x18001f69d  lea     r8, [rbp+57h+hKey]
0x18001f6a1  call    ?OpenKey@TaskStore@@AEAAJAEBU_GUID@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@Z; TaskStore::OpenKey(_GUID const &,tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f6a6  mov     ebx, eax
0x18001f6a8  test    eax, eax
0x18001f6aa  jns     short loc_18001F6C2
0x18001f6ac  mov     rcx, [rbp+57h+hKey]; hKey
0x18001f6b0  test    rcx, rcx
0x18001f6b3  jz      short loc_18001F6BB
0x18001f6b5  call    cs:__imp_RegCloseKey
0x18001f6bb  mov     eax, ebx
0x18001f6bd  jmp     loc_18001F7B6
0x18001f6c2  mov     [rbp+57h+lpFileTime], 0
0x18001f6ca  lea     rax, [rbp+57h+lpFileTime]
0x18001f6ce  mov     [rsp+0D0h+var_B0], rax; struct _TASK_RUNTIME_DATA **
0x18001f6d3  xor     r9d, r9d; struct _TASK_STATISTICS **
0x18001f6d6  xor     r8d, r8d; struct _TASK_SCHEDULE **
0x18001f6d9  mov     rdx, rsi; struct _GUID *
0x18001f6dc  mov     rcx, [r14]; this
0x18001f6df  call    ?GetSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z; CScheduleMgr::GetSchedule(_GUID const *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)
0x18001f6e4  mov     ebx, eax
0x18001f6e6  test    eax, eax
0x18001f6e8  js      short loc_18001F6AC
0x18001f6ea  mov     rbx, [rbp+57h+lpFileTime]
0x18001f6ee  test    rbx, rbx
0x18001f6f1  jnz     short loc_18001F70C
0x18001f6f3  mov     rcx, [rbp+57h+hKey]; hKey
0x18001f6f7  test    rcx, rcx
0x18001f6fa  jz      short loc_18001F702
0x18001f6fc  call    cs:__imp_RegCloseKey
0x18001f702  mov     eax, 80004005h
0x18001f707  jmp     loc_18001F7B6
0x18001f70c  test    dil, dil
0x18001f70f  jz      short loc_18001F75A
0x18001f711  lea     rdx, [rbp+57h+SystemTime]; struct _FILETIME *
0x18001f715  lea     rcx, [rbp+57h+var_80]; lpSystemTime
0x18001f719  call    ?Set@TimeValue@@QEAAHAEBU_FILETIME@@@Z; TimeValue::Set(_FILETIME const &)
0x18001f71e  mov     rdx, rbx; struct _FILETIME *
0x18001f721  lea     rcx, [rbp+57h+var_50]; lpSystemTime
0x18001f725  call    ?Set@TimeValue@@QEAAHAEBU_FILETIME@@@Z; TimeValue::Set(_FILETIME const &)
0x18001f72a  lea     rdx, [rbp+57h+var_80]
0x18001f72e  lea     rcx, [rbp+57h+var_50]
0x18001f732  call    ??8@YAHAEBVTimeValue@@0@Z; operator==(TimeValue const &,TimeValue const &)
0x18001f737  test    eax, eax
0x18001f739  jz      short loc_18001F75A
0x18001f73b  mov     rcx, rbx; void *
0x18001f73e  call    TaskSchedulerFreeRunTime
0x18001f743  nop
0x18001f744  mov     rcx, [rbp+57h+hKey]; hKey
0x18001f748  test    rcx, rcx
0x18001f74b  jz      short loc_18001F753
0x18001f74d  call    cs:__imp_RegCloseKey
0x18001f753  mov     eax, 1
0x18001f758  jmp     short loc_18001F7B6
0x18001f75a  mov     r8, rbx
0x18001f75d  lea     rcx, [rbp+57h+hKey]
0x18001f761  call    _anonymous_namespace___EncodeKey__TASK_RUNTIME_DATA_
0x18001f766  mov     edi, eax
0x18001f768  xorps   xmm0, xmm0
0x18001f76b  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001f76f  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x18001f773  mov     rcx, rbx; lpFileTime
0x18001f776  call    cs:__imp_FileTimeToSystemTime
0x18001f77c  test    cs:byte_180030D09, 20h
0x18001f783  jz      short loc_18001F79C
0x18001f785  mov     dword ptr [rsp+0D0h+var_B0], edi
0x18001f789  lea     r9, [rbp+57h+SystemTime]
0x18001f78d  mov     r8, rsi
0x18001f790  lea     rdx, PersistingLastNextRunTime
0x18001f797  call    McTemplateU0jyq_EventWriteTransfer
0x18001f79c  mov     rcx, rbx; void *
0x18001f79f  call    TaskSchedulerFreeRunTime
0x18001f7a4  nop
0x18001f7a5  mov     rcx, [rbp+57h+hKey]; hKey
0x18001f7a9  test    rcx, rcx
0x18001f7ac  jz      short loc_18001F7B4
0x18001f7ae  call    cs:__imp_RegCloseKey
0x18001f7b4  mov     eax, edi
0x18001f7b6  mov     rcx, [rbp+57h+var_20]
0x18001f7ba  xor     rcx, rsp; StackCookie
0x18001f7bd  call    __security_check_cookie
0x18001f7c2  lea     r11, [rsp+0D0h+var_10]
0x18001f7ca  mov     rbx, [r11+30h]
0x18001f7ce  mov     rsi, [r11+38h]
0x18001f7d2  mov     rsp, r11
0x18001f7d5  pop     r14
0x18001f7d7  pop     rdi
0x18001f7d8  pop     rbp
0x18001f7d9  retn
```
