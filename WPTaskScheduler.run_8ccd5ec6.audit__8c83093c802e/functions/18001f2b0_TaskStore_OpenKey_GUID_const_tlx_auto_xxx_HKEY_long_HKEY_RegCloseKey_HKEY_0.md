# TaskStore::OpenKey(_GUID const &,tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)

- ea: `0x18001f2b0`
- end: `0x18001f3e5`
- name: `?OpenKey@TaskStore@@AEAAJAEBU_GUID@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@Z`
- size: `309`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f3ec`
- `0x18001f4dc`
- `0x18001f59c`
- `0x18001f65c`
- `0x18001f7e0`
- `0x18001f87c`

## callees

- `0x18000f890`
- `0x18001e8b8`
- `0x18001f2b0`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f308`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f308`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f39e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f39e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f329`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f352`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f3b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f329`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f352`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f3b8`

## string_xrefs

- `0x18001f2fa`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\WP\TaskScheduler\Schedules`

## pseudocode

```c
__int64 __fastcall TaskStore::OpenKey(__int64 a1, GUIDParser *a2, __int64 a3)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  unsigned __int16 *v7; // r8
  unsigned __int64 v8; // r9
  unsigned int v9; // ebx
  bool v10; // cc
  HKEY *v12; // rax
  HKEY hKey[2]; // [rsp+50h] [rbp-78h] BYREF
  struct _GUID SubKey[5]; // [rsp+60h] [rbp-68h] BYREF

  hKey[0] = 0;
  phkResult = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(hKey);
  Key = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_szTaskSchedulerSchedulesRegPath, 0, 4u, phkResult);
  v9 = Key;
  v10 = Key <= 0;
  if ( Key )
    goto LABEL_2;
  if ( GUIDParser::StringFromGuid(a2, SubKey, v7, v8) )
  {
    v12 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(a3);
    Key = RegCreateKeyExW(hKey[0], (LPCWSTR)SubKey, 0, 0, 0, 3u, 0, v12, 0);
    v9 = Key;
    v10 = Key <= 0;
    if ( Key )
    {
LABEL_2:
      if ( !v10 )
        v9 = (unsigned __int16)Key | 0x80070000;
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      return v9;
    }
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return 0;
  }
  else
  {
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return 2147943759LL;
  }
}

```

## disassembly

```asm
0x18001f2b0  mov     r11, rsp
0x18001f2b3  mov     [r11+8], rbx
0x18001f2b7  mov     [r11+20h], rsi
0x18001f2bb  push    rdi
0x18001f2bc  sub     rsp, 0C0h
0x18001f2c3  mov     rax, cs:__security_cookie
0x18001f2ca  xor     rax, rsp
0x18001f2cd  mov     [rsp+0C8h+var_18], rax
0x18001f2d5  lea     rcx, [r11-78h]
0x18001f2d9  mov     qword ptr [r11-78h], 0
0x18001f2e1  mov     rsi, r8
0x18001f2e4  mov     rdi, rdx
0x18001f2e7  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f2ec  mov     r9d, 4; samDesired
0x18001f2f2  mov     [rsp+0C8h+phkResult], rax; phkResult
0x18001f2f7  xor     r8d, r8d; ulOptions
0x18001f2fa  lea     rdx, ?g_szTaskSchedulerSchedulesRegPath@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001f301  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f308  call    cs:__imp_RegOpenKeyExW
0x18001f30e  mov     ebx, eax
0x18001f310  test    eax, eax
0x18001f312  jz      short loc_18001F336
0x18001f314  jle     short loc_18001F31F
0x18001f316  movzx   ebx, ax
0x18001f319  or      ebx, 80070000h
0x18001f31f  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18001f324  test    rcx, rcx
0x18001f327  jz      short loc_18001F32F
0x18001f329  call    cs:__imp_RegCloseKey
0x18001f32f  mov     eax, ebx
0x18001f331  jmp     loc_18001F3C0
0x18001f336  lea     rdx, [rsp+0C8h+SubKey]; struct _GUID *
0x18001f33b  mov     rcx, rdi; this
0x18001f33e  call    ?StringFromGuid@GUIDParser@@YA_KPEBU_GUID@@PEAG_K@Z; GUIDParser::StringFromGuid(_GUID const *,ushort *,unsigned __int64)
0x18001f343  test    rax, rax
0x18001f346  jnz     short loc_18001F35F
0x18001f348  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18001f34d  test    rcx, rcx
0x18001f350  jz      short loc_18001F358
0x18001f352  call    cs:__imp_RegCloseKey
0x18001f358  mov     eax, 8007054Fh
0x18001f35d  jmp     short loc_18001F3C0
0x18001f35f  mov     rcx, rsi
0x18001f362  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f367  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18001f36c  lea     rdx, [rsp+0C8h+SubKey]; lpSubKey
0x18001f371  mov     [rsp+0C8h+lpdwDisposition], 0; lpdwDisposition
0x18001f37a  xor     r9d, r9d; lpClass
0x18001f37d  mov     [rsp+0C8h+var_90], rax; phkResult
0x18001f382  xor     r8d, r8d; Reserved
0x18001f385  mov     [rsp+0C8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001f38e  mov     [rsp+0C8h+samDesired], 3; samDesired
0x18001f396  mov     dword ptr [rsp+0C8h+phkResult], 0; dwOptions
0x18001f39e  call    cs:__imp_RegCreateKeyExW
0x18001f3a4  mov     ebx, eax
0x18001f3a6  test    eax, eax
0x18001f3a8  jnz     loc_18001F314
0x18001f3ae  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18001f3b3  test    rcx, rcx
0x18001f3b6  jz      short loc_18001F3BE
0x18001f3b8  call    cs:__imp_RegCloseKey
0x18001f3be  xor     eax, eax
0x18001f3c0  mov     rcx, [rsp+0C8h+var_18]
0x18001f3c8  xor     rcx, rsp; StackCookie
0x18001f3cb  call    __security_check_cookie
0x18001f3d0  lea     r11, [rsp+0C8h+var_8]
0x18001f3d8  mov     rbx, [r11+10h]
0x18001f3dc  mov     rsi, [r11+28h]
0x18001f3e0  mov     rsp, r11
0x18001f3e3  pop     rdi
0x18001f3e4  retn
```
