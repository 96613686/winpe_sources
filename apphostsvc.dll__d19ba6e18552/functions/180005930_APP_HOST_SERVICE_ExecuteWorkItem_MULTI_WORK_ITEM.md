# APP_HOST_SERVICE::ExecuteWorkItem(MULTI_WORK_ITEM *)

- ea: `0x180005930`
- end: `0x180005a3d`
- name: `?ExecuteWorkItem@APP_HOST_SERVICE@@UEAAJPEAVMULTI_WORK_ITEM@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(APP_HOST_SERVICE *__hidden this, struct MULTI_WORK_ITEM *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005930`
- `0x180005a44`
- `0x180006274`
- `0x1800063a0`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x1800059df`
- `iisutil!PuDbgPrintError` at `0x180005a2f`
- `iisutil!PuDbgPrintError` at `0x1800059df`
- `iisutil!PuDbgPrintError` at `0x180005a2f`

## string_xrefs

- `0x1800059cf`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180005a28`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180005a0b`: `Executing work item on APP_HOST_SERVICE failed\n`
- `0x180005a17`: `APP_HOST_SERVICE::ExecuteWorkItem`
- `0x1800059c1`: `APP_HOST_SERVICE::PauseServiceWorkItem`
- `0x18000598e`: `APP_HOST_SERVICE::ContinueServiceWorkItem`

## pseudocode

```c
__int64 __fastcall APP_HOST_SERVICE::ExecuteWorkItem(HANDLE *this, struct MULTI_WORK_ITEM *a2)
{
  int started; // ebx

  switch ( *((_QWORD *)a2 + 2) )
  {
    case 1LL:
      started = APP_HOST_SERVICE::StartServiceWorkItem(this);
      goto LABEL_15;
    case 2LL:
      started = 0;
      APP_HOST_SERVICE::StopServiceWorkItem((APP_HOST_SERVICE *)this);
      return (unsigned int)started;
    case 3LL:
      started = APP_HOST_SERVICE::FinishStateTransition((APP_HOST_SERVICE *)this, 7u, 6u);
      if ( started < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
          724,
          "APP_HOST_SERVICE::PauseServiceWorkItem",
          started,
          "Couldn't finish transition into the paused state\n");
LABEL_15:
      if ( started >= 0 )
        return (unsigned int)started;
      goto LABEL_16;
    case 4LL:
      started = APP_HOST_SERVICE::FinishStateTransition((APP_HOST_SERVICE *)this, 4u, 5u);
      if ( started < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
          776,
          "APP_HOST_SERVICE::ContinueServiceWorkItem",
          started,
          "Couldn't finish transition into the running state\n");
      goto LABEL_15;
  }
  started = -2147024809;
LABEL_16:
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
      555,
      "APP_HOST_SERVICE::ExecuteWorkItem",
      started,
      "Executing work item on APP_HOST_SERVICE failed\n");
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180005930  push    rbx
0x180005932  sub     rsp, 30h
0x180005936  mov     rax, [rdx+10h]
0x18000593a  sub     rax, 1
0x18000593e  jz      loc_1800059F0
0x180005944  sub     rax, 1
0x180005948  jz      loc_1800059E7
0x18000594e  sub     rax, 1
0x180005952  jz      short loc_180005997
0x180005954  cmp     rax, 1
0x180005958  jz      short loc_180005964
0x18000595a  mov     ebx, 80070057h
0x18000595f  jmp     loc_1800059FB
0x180005964  mov     edx, 4; unsigned int
0x180005969  lea     r8d, [rdx+1]; unsigned int
0x18000596d  call    ?FinishStateTransition@APP_HOST_SERVICE@@AEAAJKK@Z; APP_HOST_SERVICE::FinishStateTransition(ulong,ulong)
0x180005972  mov     ebx, eax
0x180005974  test    eax, eax
0x180005976  jns     short loc_1800059F7
0x180005978  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000597f  jz      short loc_1800059F7
0x180005981  lea     rax, aCouldnTFinishT_0; "Couldn't finish transition into the run"...
0x180005988  mov     r8d, 308h
0x18000598e  lea     r9, aAppHostService_11; "APP_HOST_SERVICE::ContinueServiceWorkIt"...
0x180005995  jmp     short loc_1800059C8
0x180005997  mov     edx, 7; unsigned int
0x18000599c  lea     r8d, [rdx-1]; unsigned int
0x1800059a0  call    ?FinishStateTransition@APP_HOST_SERVICE@@AEAAJKK@Z; APP_HOST_SERVICE::FinishStateTransition(ulong,ulong)
0x1800059a5  mov     ebx, eax
0x1800059a7  test    eax, eax
0x1800059a9  jns     short loc_1800059F7
0x1800059ab  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800059b2  jz      short loc_1800059F7
0x1800059b4  lea     rax, aCouldnTFinishT; "Couldn't finish transition into the pau"...
0x1800059bb  mov     r8d, 2D4h
0x1800059c1  lea     r9, aAppHostService_15; "APP_HOST_SERVICE::PauseServiceWorkItem"
0x1800059c8  mov     rcx, cs:g_pDebug
0x1800059cf  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800059d6  mov     [rsp+38h+var_10], rax
0x1800059db  mov     [rsp+38h+var_18], ebx
0x1800059df  call    cs:__imp_PuDbgPrintError
0x1800059e5  jmp     short loc_1800059F7
0x1800059e7  xor     ebx, ebx
0x1800059e9  call    ?StopServiceWorkItem@APP_HOST_SERVICE@@AEAAXXZ; APP_HOST_SERVICE::StopServiceWorkItem(void)
0x1800059ee  jmp     short loc_180005A35
0x1800059f0  call    ?StartServiceWorkItem@APP_HOST_SERVICE@@AEAAJXZ; APP_HOST_SERVICE::StartServiceWorkItem(void)
0x1800059f5  mov     ebx, eax
0x1800059f7  test    ebx, ebx
0x1800059f9  jns     short loc_180005A35
0x1800059fb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005a02  jz      short loc_180005A35
0x180005a04  mov     rcx, cs:g_pDebug
0x180005a0b  lea     rax, aExecutingWorkI_0; "Executing work item on APP_HOST_SERVICE"...
0x180005a12  mov     [rsp+38h+var_10], rax
0x180005a17  lea     r9, aAppHostService_18; "APP_HOST_SERVICE::ExecuteWorkItem"
0x180005a1e  mov     r8d, 22Bh
0x180005a24  mov     [rsp+38h+var_18], ebx
0x180005a28  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005a2f  call    cs:__imp_PuDbgPrintError
0x180005a35  mov     eax, ebx
0x180005a37  add     rsp, 30h
0x180005a3b  pop     rbx
0x180005a3c  retn
```
