# CONFIG_HISTORY::ValidateAdminConfig(void)

- ea: `0x18000410c`
- end: `0x1800041e0`
- name: `?ValidateAdminConfig@CONFIG_HISTORY@@AEAAJXZ`
- size: `212`
- prototype: `__int64 __fastcall(CONFIG_HISTORY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004014`

## callees

- `0x18000410c`
- `0x18000a010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180004188`
- `iisutil!PuDbgPrintError` at `0x180004188`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800041bc`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800041bc`

## string_xrefs

- `0x180004181`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history.cxx`
- `0x180004164`: `Invalid administration.config. Failed to get moduleProviders section.\n`
- `0x180004170`: `CONFIG_HISTORY::ValidateAdminConfig`
- `0x180004195`: `administration.config`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CONFIG_HISTORY::ValidateAdminConfig(CONFIG_HISTORY *this)
{
  __int64 v1; // rcx
  signed int v2; // ebx
  __int64 v4; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *v5; // [rsp+58h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 4);
  v4 = 0;
  v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v1 + 24LL))(
         v1,
         L"moduleProviders",
         L"MACHINE",
         &v4,
         0,
         0);
  if ( v2 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
        1375,
        "CONFIG_HISTORY::ValidateAdminConfig",
        v2,
        "Invalid administration.config. Failed to get moduleProviders section.\n");
    v5 = L"administration.config";
    EVENT_LOG::LogEvent((APP_HOST_SERVICE *)((char *)g_pAppHostService + 136), 0xC0002334, 1u, &v5, v2);
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000410c  mov     r11, rsp
0x18000410f  push    rbx
0x180004110  sub     rsp, 40h
0x180004114  mov     rcx, [rcx+20h]
0x180004118  lea     r9, [r11+8]
0x18000411c  mov     qword ptr [r11+8], 0
0x180004124  lea     r8, aMachine; "MACHINE"
0x18000412b  mov     qword ptr [r11-20h], 0
0x180004133  lea     rdx, aModuleprovider; "moduleProviders"
0x18000413a  mov     qword ptr [r11-28h], 0
0x180004142  mov     rax, [rcx]
0x180004145  mov     rax, [rax+18h]
0x180004149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000414e  mov     ebx, eax
0x180004150  test    eax, eax
0x180004152  jns     short loc_1800041C2
0x180004154  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000415b  jz      short loc_18000418E
0x18000415d  mov     rcx, cs:g_pDebug
0x180004164  lea     rax, aInvalidAdminis; "Invalid administration.config. Failed t"...
0x18000416b  mov     [rsp+48h+var_20], rax
0x180004170  lea     r9, aConfigHistoryV_0; "CONFIG_HISTORY::ValidateAdminConfig"
0x180004177  mov     r8d, 55Fh
0x18000417d  mov     [rsp+48h+var_28], ebx
0x180004181  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180004188  call    cs:__imp_PuDbgPrintError
0x18000418e  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x180004195  lea     rax, aAdministration; "administration.config"
0x18000419c  add     rcx, 88h
0x1800041a3  mov     [rsp+48h+arg_8], rax
0x1800041a8  mov     r8d, 1
0x1800041ae  mov     [rsp+48h+var_28], ebx
0x1800041b2  lea     r9, [rsp+48h+arg_8]
0x1800041b7  mov     edx, 0C0002334h
0x1800041bc  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800041c2  mov     rcx, [rsp+48h+arg_0]
0x1800041c7  test    rcx, rcx
0x1800041ca  jz      short loc_1800041D8
0x1800041cc  mov     rax, [rcx]
0x1800041cf  mov     rax, [rax+10h]
0x1800041d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041d8  mov     eax, ebx
0x1800041da  add     rsp, 40h
0x1800041de  pop     rbx
0x1800041df  retn
```
