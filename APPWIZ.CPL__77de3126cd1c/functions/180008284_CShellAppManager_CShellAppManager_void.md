# CShellAppManager::CShellAppManager(void)

- ea: `0x180008284`
- end: `0x1800083d8`
- name: `??0CShellAppManager@@QEAA@XZ`
- size: `340`
- prototype: `CShellAppManager *__fastcall(CShellAppManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180008800`

## callees

- `0x180008284`
- `0x18004fb80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800082ad`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800082ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800082e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800082e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008332`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008332`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008371`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008371`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800083b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800083b3`

## string_xrefs

- `0x1800082da`: `Software\Policies\Microsoft\Windows\Installer\Terminal Server`
- `0x180008305`: `Software\Policies\Microsoft\Windows\Installer\Terminal Server`

## pseudocode

```c
CShellAppManager *__fastcall CShellAppManager::CShellAppManager(CShellAppManager *this)
{
  LSTATUS v2; // eax
  int Data; // [rsp+70h] [rbp+18h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CShellAppManager::`vftable';
  _InterlockedIncrement(&g_cRefThisDll);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( (unsigned int)IsTerminalServicesRunning() )
  {
    hKey = 0;
    v2 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows\\Installer\\Terminal Server",
           0,
           3u,
           &hKey);
    if ( v2 == 2 )
      v2 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows\\Installer\\Terminal Server",
             0,
             0,
             0,
             3u,
             0,
             &hKey,
             0);
    if ( !v2 )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"EnableAdminRemote", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 || Data != 1 )
      {
        Data = 1;
        if ( !RegSetValueExW(hKey, L"EnableAdminRemote", 0, 4u, (const BYTE *)&Data, 4u) )
          *((_DWORD *)this + 16) = 1;
      }
      RegCloseKey(hKey);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180008284  push    rbp
0x180008286  push    rbx
0x180008287  mov     rbp, rsp
0x18000828a  sub     rsp, 58h
0x18000828e  lea     rax, ??_7CShellAppManager@@6B@; const CShellAppManager::`vftable'
0x180008295  mov     dword ptr [rcx+8], 1
0x18000829c  mov     [rcx], rax
0x18000829f  mov     rbx, rcx
0x1800082a2  lock inc cs:g_cRefThisDll
0x1800082a9  add     rcx, 18h; lpCriticalSection
0x1800082ad  call    cs:__imp_InitializeCriticalSection
0x1800082b3  call    IsTerminalServicesRunning
0x1800082b8  test    eax, eax
0x1800082ba  jz      loc_1800083CE
0x1800082c0  lea     rax, [rbp+hKey]
0x1800082c4  mov     [rbp+hKey], 0
0x1800082cc  mov     r9d, 3; samDesired
0x1800082d2  mov     [rsp+58h+phkResult], rax; phkResult
0x1800082d7  xor     r8d, r8d; ulOptions
0x1800082da  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x1800082e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800082e8  call    cs:__imp_RegOpenKeyExW
0x1800082ee  cmp     eax, 2
0x1800082f1  jnz     short loc_180008338
0x1800082f3  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800082fc  lea     rax, [rbp+hKey]
0x180008300  mov     [rsp+58h+var_20], rax; phkResult
0x180008305  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x18000830c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180008315  xor     r9d, r9d; lpClass
0x180008318  mov     [rsp+58h+samDesired], 3; samDesired
0x180008320  xor     r8d, r8d; Reserved
0x180008323  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000832a  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x180008332  call    cs:__imp_RegCreateKeyExW
0x180008338  test    eax, eax
0x18000833a  jnz     loc_1800083CE
0x180008340  mov     rcx, [rbp+hKey]; hKey
0x180008344  lea     r9, [rbp+Type]; lpType
0x180008348  mov     [rbp+Type], eax
0x18000834b  lea     rdx, ValueName; "EnableAdminRemote"
0x180008352  mov     [rbp+Data], eax
0x180008355  xor     r8d, r8d; lpReserved
0x180008358  lea     rax, [rbp+cbData]
0x18000835c  mov     [rbp+cbData], 4
0x180008363  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x180008368  lea     rax, [rbp+Data]
0x18000836c  mov     [rsp+58h+phkResult], rax; lpData
0x180008371  call    cs:__imp_RegQueryValueExW
0x180008377  test    eax, eax
0x180008379  jnz     short loc_180008387
0x18000837b  cmp     [rbp+Type], 4
0x18000837f  jnz     short loc_180008387
0x180008381  cmp     [rbp+Data], 1
0x180008385  jz      short loc_1800083C4
0x180008387  mov     rcx, [rbp+hKey]; hKey
0x18000838b  lea     rax, [rbp+Data]
0x18000838f  mov     [rsp+58h+samDesired], 4; cbData
0x180008397  lea     rdx, ValueName; "EnableAdminRemote"
0x18000839e  mov     r9d, 4; dwType
0x1800083a4  mov     [rsp+58h+phkResult], rax; lpData
0x1800083a9  xor     r8d, r8d; Reserved
0x1800083ac  mov     [rbp+Data], 1
0x1800083b3  call    cs:__imp_RegSetValueExW
0x1800083b9  test    eax, eax
0x1800083bb  jnz     short loc_1800083C4
0x1800083bd  mov     dword ptr [rbx+40h], 1
0x1800083c4  mov     rcx, [rbp+hKey]; hKey
0x1800083c8  call    cs:__imp_RegCloseKey
0x1800083ce  mov     rax, rbx
0x1800083d1  add     rsp, 58h
0x1800083d5  pop     rbx
0x1800083d6  pop     rbp
0x1800083d7  retn
```
