# APP_HOST_SERVICE::ExecuteService(void)

- ea: `0x180005704`
- end: `0x18000591c`
- name: `?ExecuteService@APP_HOST_SERVICE@@QEAAXXZ`
- size: `536`
- prototype: `void __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006ad0`

## callees

- `0x180005704`
- `0x1800066e4`
- `0x180008464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800058a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800058a9`
- `iisutil!PuDbgPrintError` at `0x18000585a`
- `iisutil!PuDbgPrintError` at `0x180005898`
- `iisutil!PuDbgPrintError` at `0x1800058fc`
- `iisutil!PuDbgPrintError` at `0x18000585a`
- `iisutil!PuDbgPrintError` at `0x180005898`
- `iisutil!PuDbgPrintError` at `0x1800058fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180005786`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180005786`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000579b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000579b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000576f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000576f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180005795`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180005795`

## string_xrefs

- `0x18000584f`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180005891`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x1800058f5`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180005880`: `APP_HOST_SERVICE::ExecuteService`
- `0x1800058e4`: `APP_HOST_SERVICE::ExecuteService`
- `0x180005843`: `APP_HOST_SERVICE::StartWorkQueue`
- `0x18000582f`: `Couldn't queue start service work item\n`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::ExecuteService(APP_HOST_SERVICE *this)
{
  APP_HOST_SERVICE *v1; // rsi
  struct _TP_POOL *Threadpool; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int LastError; // eax
  signed int v5; // ebx
  signed int v6; // eax

  v1 = g_pAppHostService;
  *((_DWORD *)g_pAppHostService + 10) = 3;
  *((_QWORD *)v1 + 6) = 0;
  *((_QWORD *)v1 + 7) = 0;
  *((_QWORD *)v1 + 8) = 0;
  *((_QWORD *)v1 + 9) = 0;
  *((_QWORD *)v1 + 10) = 0;
  *((_QWORD *)v1 + 11) = 0;
  *((_DWORD *)v1 + 24) = 0;
  *((_DWORD *)v1 + 25) = 1;
  *((_DWORD *)v1 + 26) = 72;
  *((_DWORD *)v1 + 28) = 1;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)v1 + 15) = Threadpool;
  if ( Threadpool
    && (SetThreadpoolThreadMaximum(Threadpool, 0x32u),
        SetThreadpoolThreadMinimum(*((PTP_POOL *)v1 + 15), 1u),
        ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup(),
        (*((_QWORD *)v1 + 16) = ThreadpoolCleanupGroup) != 0) )
  {
    *((_QWORD *)v1 + 6) = *((_QWORD *)v1 + 15);
    *((_QWORD *)v1 + 7) = ThreadpoolCleanupGroup;
    *((_QWORD *)v1 + 8) = 0;
  }
  else
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return;
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        1372,
        "APP_HOST_SERVICE::StartWorkQueue",
        v5,
        "Couldn't initialize work queue\n");
LABEL_14:
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
          1295,
          "APP_HOST_SERVICE::ExecuteService",
          v5,
          "Could not start work queue\n");
      return;
    }
  }
  v5 = MULTI_WORK_QUEUE::GetAndQueueWorkItem((APP_HOST_SERVICE *)((char *)v1 + 24), v1, 1u);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      return;
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
      1390,
      "APP_HOST_SERVICE::StartWorkQueue",
      v5,
      "Couldn't queue start service work item\n");
    goto LABEL_14;
  }
  if ( WaitForSingleObject(*((HANDLE *)v1 + 2), 0xFFFFFFFF) == -1 )
  {
    v6 = GetLastError();
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        1315,
        "APP_HOST_SERVICE::ExecuteService",
        v5,
        "WaitForSingleObject() failed\n");
  }
  APP_HOST_SERVICE::TerminateServiceAndReportFinalStatus(v1, v5);
}

```

## disassembly

```asm
0x180005704  mov     [rsp+arg_0], rbx
0x180005709  mov     [rsp+arg_8], rsi
0x18000570e  push    rdi
0x18000570f  sub     rsp, 30h
0x180005713  mov     rsi, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x18000571a  xor     ecx, ecx; reserved
0x18000571c  mov     dword ptr [rsi+28h], 3
0x180005723  mov     qword ptr [rsi+30h], 0
0x18000572b  mov     qword ptr [rsi+38h], 0
0x180005733  mov     qword ptr [rsi+40h], 0
0x18000573b  mov     qword ptr [rsi+48h], 0
0x180005743  mov     qword ptr [rsi+50h], 0
0x18000574b  mov     qword ptr [rsi+58h], 0
0x180005753  mov     dword ptr [rsi+60h], 0
0x18000575a  mov     dword ptr [rsi+64h], 1
0x180005761  mov     dword ptr [rsi+68h], 48h ; 'H'
0x180005768  mov     dword ptr [rsi+70h], 1
0x18000576f  call    cs:__imp_CreateThreadpool
0x180005775  mov     [rsi+78h], rax
0x180005779  test    rax, rax
0x18000577c  jz      short loc_1800057B0
0x18000577e  mov     edx, 32h ; '2'; cthrdMost
0x180005783  mov     rcx, rax; ptpp
0x180005786  call    cs:__imp_SetThreadpoolThreadMaximum
0x18000578c  mov     rcx, [rsi+78h]; ptpp
0x180005790  mov     edx, 1; cthrdMic
0x180005795  call    cs:__imp_SetThreadpoolThreadMinimum
0x18000579b  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800057a1  mov     [rsi+80h], rax
0x1800057a8  mov     rcx, rax
0x1800057ab  test    rax, rax
0x1800057ae  jnz     short loc_1800057F6
0x1800057b0  call    cs:__imp_GetLastError
0x1800057b6  test    eax, eax
0x1800057b8  jz      short loc_1800057D1
0x1800057ba  call    cs:__imp_GetLastError
0x1800057c0  mov     ebx, eax
0x1800057c2  test    eax, eax
0x1800057c4  jle     short loc_1800057D6
0x1800057c6  movzx   ebx, ax
0x1800057c9  or      ebx, 80070000h
0x1800057cf  jmp     short loc_1800057D6
0x1800057d1  mov     ebx, 80004005h
0x1800057d6  test    ebx, ebx
0x1800057d8  jns     short loc_18000580A
0x1800057da  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800057e1  jz      loc_18000590C
0x1800057e7  lea     rax, aCouldnTInitial; "Couldn't initialize work queue\n"
0x1800057ee  mov     r8d, 55Ch
0x1800057f4  jmp     short loc_18000583C
0x1800057f6  mov     rax, [rsi+78h]
0x1800057fa  mov     [rsi+30h], rax
0x1800057fe  mov     [rsi+38h], rcx
0x180005802  mov     qword ptr [rsi+40h], 0
0x18000580a  mov     r8d, 1; unsigned __int64
0x180005810  lea     rcx, [rsi+18h]; this
0x180005814  mov     rdx, rsi; struct MULTI_WORK_DISPATCH *
0x180005817  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x18000581c  mov     ebx, eax
0x18000581e  test    eax, eax
0x180005820  jns     short loc_1800058A0
0x180005822  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005829  jz      loc_18000590C
0x18000582f  lea     rax, aCouldnTQueueSt_0; "Couldn't queue start service work item"...
0x180005836  mov     r8d, 56Eh
0x18000583c  mov     rcx, cs:g_pDebug
0x180005843  lea     r9, aAppHostService; "APP_HOST_SERVICE::StartWorkQueue"
0x18000584a  mov     [rsp+38h+var_10], rax
0x18000584f  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005856  mov     [rsp+38h+var_18], ebx
0x18000585a  call    cs:__imp_PuDbgPrintError
0x180005860  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005867  jz      loc_18000590C
0x18000586d  mov     rcx, cs:g_pDebug
0x180005874  lea     rax, aCouldNotStartW; "Could not start work queue\n"
0x18000587b  mov     [rsp+38h+var_10], rax
0x180005880  lea     r9, aAppHostService_9; "APP_HOST_SERVICE::ExecuteService"
0x180005887  mov     r8d, 50Fh
0x18000588d  mov     [rsp+38h+var_18], ebx
0x180005891  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005898  call    cs:__imp_PuDbgPrintError
0x18000589e  jmp     short loc_18000590C
0x1800058a0  mov     rcx, [rsi+10h]; hHandle
0x1800058a4  or      edi, 0FFFFFFFFh
0x1800058a7  mov     edx, edi; dwMilliseconds
0x1800058a9  call    cs:__imp_WaitForSingleObject
0x1800058af  cmp     eax, edi
0x1800058b1  jnz     short loc_180005902
0x1800058b3  call    cs:__imp_GetLastError
0x1800058b9  mov     ebx, eax
0x1800058bb  test    eax, eax
0x1800058bd  jle     short loc_1800058C8
0x1800058bf  movzx   ebx, ax
0x1800058c2  or      ebx, 80070000h
0x1800058c8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800058cf  jz      short loc_180005902
0x1800058d1  mov     rcx, cs:g_pDebug
0x1800058d8  lea     rax, aWaitforsingleo; "WaitForSingleObject() failed\n"
0x1800058df  mov     [rsp+38h+var_10], rax
0x1800058e4  lea     r9, aAppHostService_9; "APP_HOST_SERVICE::ExecuteService"
0x1800058eb  mov     r8d, 523h
0x1800058f1  mov     [rsp+38h+var_18], ebx
0x1800058f5  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800058fc  call    cs:__imp_PuDbgPrintError
0x180005902  mov     edx, ebx; int
0x180005904  mov     rcx, rsi; this
0x180005907  call    ?TerminateServiceAndReportFinalStatus@APP_HOST_SERVICE@@AEAAXJ@Z; APP_HOST_SERVICE::TerminateServiceAndReportFinalStatus(long)
0x18000590c  mov     rbx, [rsp+38h+arg_0]
0x180005911  mov     rsi, [rsp+38h+arg_8]
0x180005916  add     rsp, 30h
0x18000591a  pop     rdi
0x18000591b  retn
```
