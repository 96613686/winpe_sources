# ServiceMainEntry(ulong,ushort * *)

- ea: `0x180021db0`
- end: `0x180021f55`
- name: `?ServiceMainEntry@@YAXKPEAPEAG@Z`
- size: `421`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800215c0`

## callees

- `0x18001af70`
- `0x180021790`
- `0x180021db0`
- `0x180022070`
- `0x1800238e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ec6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ec6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180021e04`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180021e04`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180021f0a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180021f0a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180021e6c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180021e6c`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180021e9f`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180021e9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServiceMainEntry(__int64 a1, unsigned __int16 **a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  signed int LastError; // eax
  bool v4; // sf
  signed int v5; // eax
  bool v6; // sf
  int ServiceRegistryStateKey; // eax
  unsigned __int64 v8; // rcx
  GUID SettingGuid; // [rsp+20h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9383a425320539f63aecec967f0bb423_Traceguids);
  v2 = RegisterServiceCtrlHandlerExW(L"DsmSvc", SvcCtrlHandler, 0);
  g_SvcStatusHandle = v2;
  if ( v2 )
    goto LABEL_9;
  LastError = GetLastError();
  v4 = LastError < 0;
  if ( LastError > 0 )
    v4 = 1;
  if ( !v4 )
  {
    v2 = g_SvcStatusHandle;
LABEL_9:
    g_SvcStatus.dwServiceType = 32;
    dword_180059DC8 = 0;
    SettingGuid = GUID_LOW_POWER_EPOCH;
    v5 = PowerSettingRegisterNotification(&SettingGuid, 1u, v2, &g_hPowerHandle);
    v6 = v5 < 0;
    if ( v5 > 0 )
      v6 = 1;
    if ( !v6 )
    {
      ServiceRegistryStateKey = GetServiceRegistryStateKey(g_SvcStatusHandle, 1, 131103, &g_hPersistentStateKey);
      if ( ServiceRegistryStateKey > 0 )
        v8 = (unsigned __int16)ServiceRegistryStateKey | 0x80070000;
      else
        v8 = (unsigned int)ServiceRegistryStateKey;
      if ( (v8 & 0x80000000) != 0LL )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_9383a425320539f63aecec967f0bb423_Traceguids,
            (unsigned int)ServiceRegistryStateKey);
      }
      else
      {
        CDsmCore::ServiceStart((CDsmCore *)v8);
        RegCloseKey(g_hPersistentStateKey);
        g_hPersistentStateKey = 0;
      }
      PowerSettingUnregisterNotification(g_hPowerHandle);
      g_hPowerHandle = 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9383a425320539f63aecec967f0bb423_Traceguids);
}

```

## disassembly

```asm
0x180021db0  push    rsi
0x180021db2  sub     rsp, 40h
0x180021db6  mov     rax, cs:__security_cookie
0x180021dbd  xor     rax, rsp
0x180021dc0  mov     [rsp+48h+var_18], rax
0x180021dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021dcc  lea     rsi, WPP_GLOBAL_Control
0x180021dd3  cmp     rcx, rsi
0x180021dd6  jz      short loc_180021DF3
0x180021dd8  test    byte ptr [rcx+1Ch], 1
0x180021ddc  jz      short loc_180021DF3
0x180021dde  mov     rcx, [rcx+10h]
0x180021de2  lea     r8, WPP_9383a425320539f63aecec967f0bb423_Traceguids
0x180021de9  mov     edx, 0Ch
0x180021dee  call    WPP_SF_
0x180021df3  xor     r8d, r8d; lpContext
0x180021df6  lea     rdx, ?SvcCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180021dfd  lea     rcx, ServiceName; "DsmSvc"
0x180021e04  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180021e0a  mov     cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x180021e11  test    rax, rax
0x180021e14  jnz     short loc_180021E37
0x180021e16  call    cs:__imp_GetLastError
0x180021e1c  test    eax, eax
0x180021e1e  jle     short loc_180021E2A
0x180021e20  movzx   eax, ax
0x180021e23  or      eax, 80070000h
0x180021e28  test    eax, eax
0x180021e2a  js      loc_180021F1B
0x180021e30  mov     rax, cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x180021e37  movups  xmm0, xmmword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x180021e3e  lea     r9, ?g_hPowerHandle@@3PEAXEA; RegistrationHandle
0x180021e45  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A, 20h ; ' '; _SERVICE_STATUS g_SvcStatus
0x180021e4f  mov     r8, rax; Recipient
0x180021e52  mov     cs:dword_180059DC8, 0
0x180021e5c  mov     edx, 1; Flags
0x180021e61  lea     rcx, [rsp+48h+SettingGuid]; SettingGuid
0x180021e66  movdqu  xmmword ptr [rsp+48h+SettingGuid.Data1], xmm0
0x180021e6c  call    cs:__imp_PowerSettingRegisterNotification
0x180021e72  test    eax, eax
0x180021e74  jle     short loc_180021E80
0x180021e76  movzx   eax, ax
0x180021e79  or      eax, 80070000h
0x180021e7e  test    eax, eax
0x180021e80  js      loc_180021F1B
0x180021e86  mov     rcx, cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x180021e8d  lea     r9, ?g_hPersistentStateKey@@3PEAUHKEY__@@EA; HKEY__ * g_hPersistentStateKey
0x180021e94  mov     edx, 1
0x180021e99  mov     r8d, 2001Fh
0x180021e9f  call    cs:__imp_GetServiceRegistryStateKey
0x180021ea5  test    eax, eax
0x180021ea7  jg      short loc_180021EAD
0x180021ea9  mov     ecx, eax
0x180021eab  jmp     short loc_180021EB6
0x180021ead  movzx   ecx, ax
0x180021eb0  or      ecx, 80070000h; this
0x180021eb6  test    ecx, ecx
0x180021eb8  js      short loc_180021ED9
0x180021eba  call    ?ServiceStart@CDsmCore@@QEAAXXZ; CDsmCore::ServiceStart(void)
0x180021ebf  mov     rcx, cs:?g_hPersistentStateKey@@3PEAUHKEY__@@EA; hKey
0x180021ec6  call    cs:__imp_RegCloseKey
0x180021ecc  mov     cs:?g_hPersistentStateKey@@3PEAUHKEY__@@EA, 0; HKEY__ * g_hPersistentStateKey
0x180021ed7  jmp     short loc_180021F03
0x180021ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ee0  cmp     rcx, rsi
0x180021ee3  jz      short loc_180021F03
0x180021ee5  test    byte ptr [rcx+1Ch], 4
0x180021ee9  jz      short loc_180021F03
0x180021eeb  mov     rcx, [rcx+10h]
0x180021eef  lea     r8, WPP_9383a425320539f63aecec967f0bb423_Traceguids
0x180021ef6  mov     edx, 0Dh
0x180021efb  mov     r9d, eax
0x180021efe  call    WPP_SF_d
0x180021f03  mov     rcx, cs:?g_hPowerHandle@@3PEAXEA; RegistrationHandle
0x180021f0a  call    cs:__imp_PowerSettingUnregisterNotification
0x180021f10  mov     cs:?g_hPowerHandle@@3PEAXEA, 0; void * g_hPowerHandle
0x180021f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f22  cmp     rcx, rsi
0x180021f25  jz      short loc_180021F42
0x180021f27  test    byte ptr [rcx+1Ch], 1
0x180021f2b  jz      short loc_180021F42
0x180021f2d  mov     rcx, [rcx+10h]
0x180021f31  lea     r8, WPP_9383a425320539f63aecec967f0bb423_Traceguids
0x180021f38  mov     edx, 0Eh
0x180021f3d  call    WPP_SF_
0x180021f42  mov     rcx, [rsp+48h+var_18]
0x180021f47  xor     rcx, rsp; StackCookie
0x180021f4a  call    __security_check_cookie
0x180021f4f  add     rsp, 40h
0x180021f53  pop     rsi
0x180021f54  retn
```
