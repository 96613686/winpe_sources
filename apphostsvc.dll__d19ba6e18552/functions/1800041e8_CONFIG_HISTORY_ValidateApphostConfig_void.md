# CONFIG_HISTORY::ValidateApphostConfig(void)

- ea: `0x1800041e8`
- end: `0x18000433e`
- name: `?ValidateApphostConfig@CONFIG_HISTORY@@AEAAJXZ`
- size: `342`
- prototype: `__int64 __fastcall(CONFIG_HISTORY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004014`

## callees

- `0x1800041e8`
- `0x18000a010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18000424c`
- `iisutil!PuDbgPrintError` at `0x1800042c7`
- `iisutil!PuDbgPrintError` at `0x18000424c`
- `iisutil!PuDbgPrintError` at `0x1800042c7`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800042fb`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800042fb`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180004208`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180004208`

## string_xrefs

- `0x180004245`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history.cxx`
- `0x1800042c0`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history.cxx`
- `0x180004271`: `system.applicationHost/configHistory`
- `0x180004228`: `GetDefaultNativeConfigurationSystem failed.\n`
- `0x180004234`: `CONFIG_HISTORY::ValidateApphostConfig`
- `0x1800042af`: `CONFIG_HISTORY::ValidateApphostConfig`
- `0x1800042a3`: `Invalid applicationHost.config. GetConfigSection() failed while reading configHistory section.\n`
- `0x1800042d4`: `applicationHost.config`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY::ValidateApphostConfig(CONFIG_HISTORY *this)
{
  signed int DefaultNativeConfigurationSystem; // ebx
  __int64 v3; // [rsp+50h] [rbp+8h] BYREF
  struct INativeConfigurationSystem *v4; // [rsp+58h] [rbp+10h] BYREF
  const unsigned __int16 *v5; // [rsp+60h] [rbp+18h] BYREF

  v4 = 0;
  v3 = 0;
  DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem(&v4);
  if ( DefaultNativeConfigurationSystem >= 0 )
  {
    DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v4 + 24LL))(
                                         v4,
                                         L"system.applicationHost/configHistory",
                                         L"MACHINE/WEBROOT/APPHOST",
                                         &v3,
                                         0,
                                         0);
    if ( DefaultNativeConfigurationSystem < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
          1453,
          "CONFIG_HISTORY::ValidateApphostConfig",
          DefaultNativeConfigurationSystem,
          "Invalid applicationHost.config. GetConfigSection() failed while reading configHistory section.\n");
      v5 = L"applicationHost.config";
      EVENT_LOG::LogEvent(
        (APP_HOST_SERVICE *)((char *)g_pAppHostService + 136),
        0xC0002334,
        1u,
        &v5,
        DefaultNativeConfigurationSystem);
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
      1439,
      "CONFIG_HISTORY::ValidateApphostConfig",
      DefaultNativeConfigurationSystem,
      "GetDefaultNativeConfigurationSystem failed.\n");
  }
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    v3 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)DefaultNativeConfigurationSystem;
}

```

## disassembly

```asm
0x1800041e8  mov     rax, rsp
0x1800041eb  mov     [rax+8], rcx
0x1800041ef  push    rbx
0x1800041f0  sub     rsp, 40h
0x1800041f4  lea     rcx, [rax+10h]
0x1800041f8  mov     qword ptr [rax+10h], 0
0x180004200  mov     qword ptr [rax+8], 0
0x180004208  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x18000420e  mov     ebx, eax
0x180004210  test    eax, eax
0x180004212  jns     short loc_180004257
0x180004214  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000421b  jz      loc_180004301
0x180004221  mov     rcx, cs:g_pDebug
0x180004228  lea     rax, aGetdefaultnati; "GetDefaultNativeConfigurationSystem fai"...
0x18000422f  mov     [rsp+48h+var_20], rax
0x180004234  lea     r9, aConfigHistoryV; "CONFIG_HISTORY::ValidateApphostConfig"
0x18000423b  mov     r8d, 59Fh
0x180004241  mov     dword ptr [rsp+48h+var_28], ebx
0x180004245  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000424c  call    cs:__imp_PuDbgPrintError
0x180004252  jmp     loc_180004301
0x180004257  mov     rcx, [rsp+48h+arg_8]
0x18000425c  lea     r9, [rsp+48h+arg_0]
0x180004261  mov     [rsp+48h+var_20], 0
0x18000426a  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180004271  lea     rdx, aSystemApplicat; "system.applicationHost/configHistory"
0x180004278  mov     [rsp+48h+var_28], 0
0x180004281  mov     rax, [rcx]
0x180004284  mov     rax, [rax+18h]
0x180004288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000428d  mov     ebx, eax
0x18000428f  test    eax, eax
0x180004291  jns     short loc_180004301
0x180004293  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000429a  jz      short loc_1800042CD
0x18000429c  mov     rcx, cs:g_pDebug
0x1800042a3  lea     rax, aInvalidApplica; "Invalid applicationHost.config. GetConf"...
0x1800042aa  mov     [rsp+48h+var_20], rax
0x1800042af  lea     r9, aConfigHistoryV; "CONFIG_HISTORY::ValidateApphostConfig"
0x1800042b6  mov     r8d, 5ADh
0x1800042bc  mov     dword ptr [rsp+48h+var_28], ebx
0x1800042c0  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800042c7  call    cs:__imp_PuDbgPrintError
0x1800042cd  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x1800042d4  lea     rax, aApplicationhos; "applicationHost.config"
0x1800042db  add     rcx, 88h
0x1800042e2  mov     [rsp+48h+arg_10], rax
0x1800042e7  mov     r8d, 1
0x1800042ed  mov     dword ptr [rsp+48h+var_28], ebx
0x1800042f1  lea     r9, [rsp+48h+arg_10]
0x1800042f6  mov     edx, 0C0002334h
0x1800042fb  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180004301  mov     rcx, [rsp+48h+arg_0]
0x180004306  test    rcx, rcx
0x180004309  jz      short loc_180004320
0x18000430b  mov     rax, [rcx]
0x18000430e  mov     rax, [rax+10h]
0x180004312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004317  mov     [rsp+48h+arg_0], 0
0x180004320  mov     rcx, [rsp+48h+arg_8]
0x180004325  test    rcx, rcx
0x180004328  jz      short loc_180004336
0x18000432a  mov     rax, [rcx]
0x18000432d  mov     rax, [rax+10h]
0x180004331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004336  mov     eax, ebx
0x180004338  add     rsp, 40h
0x18000433c  pop     rbx
0x18000433d  retn
```
