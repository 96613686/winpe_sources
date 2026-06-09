# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::Invoke(HWND__ *)

- ea: `0x180023e60`
- end: `0x180023f27`
- name: `?Invoke@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@EEAAJPEAUHWND__@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180015c40`
- `0x180023e60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023ef4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023ef4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023e9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023e9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023eda`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023eda`
- `ext-ms-onecore-shellchromeapi-l1-1-1!Shell_RequestShutdown` at `0x180023f17`
- `ext-ms-onecore-shellchromeapi-l1-1-1!Shell_RequestShutdown` at `0x180023f17`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::Invoke(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *this,
        HWND a2)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  char v6; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = **((_DWORD **)this + 28);
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ResolutionOverride",
         0,
         0x20006u,
         &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    v4 = RegSetValueExW(hKey, L"Resolution", 0, 4u, (const BYTE *)&Data, 4u);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    RegCloseKey(hKey);
  }
  v6 = 0;
  PowerAndBatteryTelemetry::DynamicResolutionChanged<unsigned int &,bool>(&Data, &v6);
  if ( v3 >= 0 )
    return (unsigned int)Shell_RequestShutdown(1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180023e60  push    rbx
0x180023e62  sub     rsp, 30h
0x180023e66  mov     rax, [rcx+0E0h]
0x180023e6d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180023e74  mov     r9d, 20006h; samDesired
0x180023e7a  xor     r8d, r8d; ulOptions
0x180023e7d  mov     ecx, [rax]
0x180023e7f  lea     rax, [rsp+38h+hKey]
0x180023e84  mov     [rsp+38h+Data], ecx
0x180023e88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023e8f  mov     [rsp+38h+phkResult], rax; phkResult
0x180023e94  mov     [rsp+38h+hKey], 0
0x180023e9d  call    cs:__imp_RegOpenKeyExW
0x180023ea3  mov     ebx, eax
0x180023ea5  test    eax, eax
0x180023ea7  jle     short loc_180023EB2
0x180023ea9  movzx   ebx, ax
0x180023eac  or      ebx, 80070000h
0x180023eb2  test    ebx, ebx
0x180023eb4  js      short loc_180023EFA
0x180023eb6  mov     rcx, [rsp+38h+hKey]; hKey
0x180023ebb  lea     rax, [rsp+38h+Data]
0x180023ec0  mov     r9d, 4; dwType
0x180023ec6  lea     rdx, ValueName; "Resolution"
0x180023ecd  mov     [rsp+38h+cbData], r9d; cbData
0x180023ed2  xor     r8d, r8d; Reserved
0x180023ed5  mov     [rsp+38h+phkResult], rax; lpData
0x180023eda  call    cs:__imp_RegSetValueExW
0x180023ee0  mov     ebx, eax
0x180023ee2  test    eax, eax
0x180023ee4  jle     short loc_180023EEF
0x180023ee6  movzx   ebx, ax
0x180023ee9  or      ebx, 80070000h
0x180023eef  mov     rcx, [rsp+38h+hKey]; hKey
0x180023ef4  call    cs:__imp_RegCloseKey
0x180023efa  lea     rdx, [rsp+38h+arg_0]
0x180023eff  mov     [rsp+38h+arg_0], 0
0x180023f04  lea     rcx, [rsp+38h+Data]
0x180023f09  call    ??$DynamicResolutionChanged@AEAI_N@PowerAndBatteryTelemetry@@SAXAEAI$$QEA_N@Z; PowerAndBatteryTelemetry::DynamicResolutionChanged<uint &,bool>(uint &,bool &&)
0x180023f0e  test    ebx, ebx
0x180023f10  js      short loc_180023F1F
0x180023f12  mov     ecx, 1
0x180023f17  call    cs:__imp_Shell_RequestShutdown
0x180023f1d  mov     ebx, eax
0x180023f1f  mov     eax, ebx
0x180023f21  add     rsp, 30h
0x180023f25  pop     rbx
0x180023f26  retn
```
