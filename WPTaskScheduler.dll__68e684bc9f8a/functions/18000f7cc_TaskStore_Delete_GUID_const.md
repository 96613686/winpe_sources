# TaskStore::Delete(_GUID const &)

- ea: `0x18000f7cc`
- end: `0x18000f888`
- name: `?Delete@TaskStore@@QEAAJAEBU_GUID@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(TaskStore *this, struct _GUID *)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180002150`
- `0x180002d90`
- `0x180005440`
- `0x180005e40`
- `0x1800074e0`
- `0x18000da60`

## callees

- `0x18000f7cc`
- `0x18000f890`
- `0x18001e8b8`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f81d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f81d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f85f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f85f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000f840`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000f840`

## string_xrefs

- `0x18000f80f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\WP\TaskScheduler\Schedules`

## pseudocode

```c
__int64 __fastcall TaskStore::Delete(TaskStore *this, struct _GUID *a2)
{
  HKEY *phkResult; // rax
  LSTATUS v4; // eax
  unsigned __int16 *v5; // r8
  unsigned __int64 v6; // r9
  unsigned int v7; // ebx
  bool v8; // cc
  HKEY hKey; // [rsp+30h] [rbp-78h] BYREF
  struct _GUID SubKey[5]; // [rsp+40h] [rbp-68h] BYREF

  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_szTaskSchedulerSchedulesRegPath, 0, 1u, phkResult);
  v7 = v4;
  v8 = v4 <= 0;
  if ( !v4 )
  {
    GUIDParser::StringFromGuid((GUIDParser *)a2, SubKey, v5, v6);
    v4 = RegDeleteKeyW(hKey, (LPCWSTR)SubKey);
    v7 = v4;
    v8 = v4 <= 0;
  }
  if ( !v8 )
    v7 = (unsigned __int16)v4 | 0x80070000;
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18000f7cc  mov     [rsp+arg_0], rbx
0x18000f7d1  push    rdi
0x18000f7d2  sub     rsp, 0A0h
0x18000f7d9  mov     rax, cs:__security_cookie
0x18000f7e0  xor     rax, rsp
0x18000f7e3  mov     [rsp+0A8h+var_18], rax
0x18000f7eb  lea     rcx, [rsp+0A8h+hKey]
0x18000f7f0  mov     [rsp+0A8h+hKey], 0
0x18000f7f9  mov     rdi, rdx
0x18000f7fc  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18000f801  mov     r9d, 1; samDesired
0x18000f807  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18000f80c  xor     r8d, r8d; ulOptions
0x18000f80f  lea     rdx, ?g_szTaskSchedulerSchedulesRegPath@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000f816  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f81d  call    cs:__imp_RegOpenKeyExW
0x18000f823  mov     ebx, eax
0x18000f825  test    eax, eax
0x18000f827  jnz     short loc_18000F84A
0x18000f829  lea     rdx, [rsp+0A8h+SubKey]; struct _GUID *
0x18000f82e  mov     rcx, rdi; this
0x18000f831  call    ?StringFromGuid@GUIDParser@@YA_KPEBU_GUID@@PEAG_K@Z; GUIDParser::StringFromGuid(_GUID const *,ushort *,unsigned __int64)
0x18000f836  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18000f83b  lea     rdx, [rsp+0A8h+SubKey]; lpSubKey
0x18000f840  call    cs:__imp_RegDeleteKeyW
0x18000f846  mov     ebx, eax
0x18000f848  test    eax, eax
0x18000f84a  jle     short loc_18000F855
0x18000f84c  movzx   ebx, ax
0x18000f84f  or      ebx, 80070000h
0x18000f855  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18000f85a  test    rcx, rcx
0x18000f85d  jz      short loc_18000F865
0x18000f85f  call    cs:__imp_RegCloseKey
0x18000f865  mov     eax, ebx
0x18000f867  mov     rcx, [rsp+0A8h+var_18]
0x18000f86f  xor     rcx, rsp; StackCookie
0x18000f872  call    __security_check_cookie
0x18000f877  mov     rbx, [rsp+0A8h+arg_0]
0x18000f87f  add     rsp, 0A0h
0x18000f886  pop     rdi
0x18000f887  retn
```
