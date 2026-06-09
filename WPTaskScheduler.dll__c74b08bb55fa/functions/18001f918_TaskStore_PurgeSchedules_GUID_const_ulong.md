# TaskStore::PurgeSchedules(_GUID const *,ulong)

- ea: `0x18001f918`
- end: `0x18001f9d9`
- name: `?PurgeSchedules@TaskStore@@QEAAJPEBU_GUID@@K@Z`
- size: `193`
- prototype: `__int64 __fastcall(TaskStore *this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018a04`

## callees

- `0x18000f890`
- `0x18001e8b8`
- `0x18001f918`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f962`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f983`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f983`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9b8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001f9a8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001f9a8`

## string_xrefs

- `0x18001f954`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\WP\TaskScheduler\Schedules`

## pseudocode

```c
__int64 __fastcall TaskStore::PurgeSchedules(TaskStore *this, const struct _GUID *a2)
{
  HKEY *phkResult; // rax
  LSTATUS v3; // eax
  unsigned __int16 *v4; // r8
  unsigned __int64 v5; // r9
  unsigned int v6; // ebx
  HKEY hKey[2]; // [rsp+30h] [rbp-78h] BYREF
  struct _GUID SubKey[5]; // [rsp+40h] [rbp-68h] BYREF

  hKey[0] = 0;
  phkResult = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(hKey);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_szTaskSchedulerSchedulesRegPath, 0, 1u, phkResult);
  v6 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v6 = (unsigned __int16)v3 | 0x80070000;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return v6;
  }
  else
  {
    GUIDParser::StringFromGuid((GUIDParser *)&s_ScheduleCleanupList, SubKey, v4, v5);
    RegDeleteKeyW(hKey[0], (LPCWSTR)SubKey);
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x18001f918  push    rbx
0x18001f91a  sub     rsp, 0A0h
0x18001f921  mov     rax, cs:__security_cookie
0x18001f928  xor     rax, rsp
0x18001f92b  mov     [rsp+0A8h+var_18], rax
0x18001f933  lea     rcx, [rsp+0A8h+hKey]
0x18001f938  mov     [rsp+0A8h+hKey], 0
0x18001f941  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f946  mov     r9d, 1; samDesired
0x18001f94c  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18001f951  xor     r8d, r8d; ulOptions
0x18001f954  lea     rdx, ?g_szTaskSchedulerSchedulesRegPath@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001f95b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f962  call    cs:__imp_RegOpenKeyExW
0x18001f968  mov     ebx, eax
0x18001f96a  test    eax, eax
0x18001f96c  jz      short loc_18001F98D
0x18001f96e  jle     short loc_18001F979
0x18001f970  movzx   ebx, ax
0x18001f973  or      ebx, 80070000h
0x18001f979  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001f97e  test    rcx, rcx
0x18001f981  jz      short loc_18001F989
0x18001f983  call    cs:__imp_RegCloseKey
0x18001f989  mov     eax, ebx
0x18001f98b  jmp     short loc_18001F9C0
0x18001f98d  lea     rdx, [rsp+0A8h+SubKey]; struct _GUID *
0x18001f992  lea     rcx, ?s_ScheduleCleanupList@@3PAU_GUID@@A; this
0x18001f999  call    ?StringFromGuid@GUIDParser@@YA_KPEBU_GUID@@PEAG_K@Z; GUIDParser::StringFromGuid(_GUID const *,ushort *,unsigned __int64)
0x18001f99e  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001f9a3  lea     rdx, [rsp+0A8h+SubKey]; lpSubKey
0x18001f9a8  call    cs:__imp_RegDeleteKeyW
0x18001f9ae  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001f9b3  test    rcx, rcx
0x18001f9b6  jz      short loc_18001F9BE
0x18001f9b8  call    cs:__imp_RegCloseKey
0x18001f9be  xor     eax, eax
0x18001f9c0  mov     rcx, [rsp+0A8h+var_18]
0x18001f9c8  xor     rcx, rsp; StackCookie
0x18001f9cb  call    __security_check_cookie
0x18001f9d0  add     rsp, 0A0h
0x18001f9d7  pop     rbx
0x18001f9d8  retn
```
