# OrchestrateNextBootAsAudit

- ea: `0x180048210`
- end: `0x1800482ff`
- name: `OrchestrateNextBootAsAudit`
- size: `239`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180028e74`

## callees

- `0x180048210`
- `0x1800488e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800482b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800482b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180048274`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180048274`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800482a2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800482a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800482af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800482af`

## pseudocode

```c
signed int OrchestrateNextBootAsAudit()
{
  LSTATUS v0; // ebx
  HKEY v1; // rdx
  HKEY v2; // rcx
  const unsigned __int16 *v3; // r8
  signed int result; // eax
  signed int LastError; // eax
  bool v6; // sf
  DWORD v7; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  Data = 1;
  hKey = 0;
  v7 = 0;
  v0 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status", 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &v7);
  if ( !v0 )
  {
    v0 = RegSetValueExW(hKey, L"AuditBoot", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  SetLastError(v0);
  if ( !v0 )
    return OrchestrateUpdateImageState(v2, v1, v3);
  LastError = GetLastError();
  v6 = LastError < 0;
  if ( LastError > 0 )
    v6 = 1;
  if ( !v6 )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180048210  mov     [rsp+arg_0], ecx
0x180048214  mov     r11, rsp
0x180048217  push    rbx
0x180048218  sub     rsp, 50h
0x18004821c  lea     rax, [r11+8]
0x180048220  mov     [rsp+58h+Data], 1
0x180048228  mov     [r11-18h], rax
0x18004822c  lea     r9, Class; lpClass
0x180048233  lea     rax, [r11+18h]
0x180048237  mov     qword ptr [r11+18h], 0
0x18004823f  mov     [r11-20h], rax
0x180048243  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x18004824a  mov     qword ptr [r11-28h], 0
0x180048252  xor     r8d, r8d; Reserved
0x180048255  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18004825d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180048264  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18004826c  mov     [rsp+58h+arg_0], 0
0x180048274  call    cs:__imp_RegCreateKeyExW
0x18004827a  mov     ebx, eax
0x18004827c  test    eax, eax
0x18004827e  jnz     short loc_1800482B5
0x180048280  mov     rcx, [rsp+58h+hKey]; hKey
0x180048285  lea     r9d, [rax+4]; dwType
0x180048289  lea     rax, [rsp+58h+Data]
0x18004828e  mov     [rsp+58h+samDesired], r9d; cbData
0x180048293  xor     r8d, r8d; Reserved
0x180048296  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18004829b  lea     rdx, aAuditboot; "AuditBoot"
0x1800482a2  call    cs:__imp_RegSetValueExW
0x1800482a8  mov     rcx, [rsp+58h+hKey]; hKey
0x1800482ad  mov     ebx, eax
0x1800482af  call    cs:__imp_RegCloseKey
0x1800482b5  mov     ecx, ebx; dwErrCode
0x1800482b7  call    cs:__imp_SetLastError
0x1800482bd  test    ebx, ebx
0x1800482bf  jnz     short loc_1800482CB
0x1800482c1  add     rsp, 50h
0x1800482c5  pop     rbx
0x1800482c6  jmp     ?OrchestrateUpdateImageState@@YAJPEAUHKEY__@@0PEBG@Z; OrchestrateUpdateImageState(HKEY__ *,HKEY__ *,ushort const *)
0x1800482cb  call    cs:__imp_GetLastError
0x1800482d1  mov     ebx, 80070000h
0x1800482d6  test    eax, eax
0x1800482d8  jle     short loc_1800482E1
0x1800482da  movzx   eax, ax
0x1800482dd  or      eax, ebx
0x1800482df  test    eax, eax
0x1800482e1  jns     short loc_1800482F4
0x1800482e3  call    cs:__imp_GetLastError
0x1800482e9  test    eax, eax
0x1800482eb  jle     short loc_1800482F9
0x1800482ed  movzx   eax, ax
0x1800482f0  or      eax, ebx
0x1800482f2  jmp     short loc_1800482F9
0x1800482f4  mov     eax, 80004005h
0x1800482f9  add     rsp, 50h
0x1800482fd  pop     rbx
0x1800482fe  retn
```
