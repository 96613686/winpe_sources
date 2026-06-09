# ServiceControlHandler(ulong)

- ea: `0x180005f90`
- end: `0x18000626d`
- name: `?ServiceControlHandler@@YAXK@Z`
- size: `733`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800054ec`
- `0x180005ecc`
- `0x180005f90`
- `0x180008464`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000606a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000606a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006019`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006019`
- `iisutil!PuDbgPrintError` at `0x180006061`
- `iisutil!PuDbgPrintError` at `0x180006201`
- `iisutil!PuDbgPrintError` at `0x18000624f`
- `iisutil!PuDbgPrintError` at `0x180006061`
- `iisutil!PuDbgPrintError` at `0x180006201`
- `iisutil!PuDbgPrintError` at `0x18000624f`
- `iisutil!PuDbgPrint` at `0x180005ffd`
- `iisutil!PuDbgPrint` at `0x180005ffd`

## string_xrefs

- `0x180005fd6`: `Service control ignored, OpCode: %lu\n`
- `0x180005fe4`: `ServiceControlHandler`
- `0x180006237`: `ServiceControlHandler`
- `0x180005ff6`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x18000605a`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x1800061f1`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180006248`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x18000622b`: `Service control operation failed\n`
- `0x18000603d`: `Couldn't report the service status\n`
- `0x180006049`: `APP_HOST_SERVICE::InterrogateService`
- `0x1800061a6`: `Couldn't transition to service stop pending\n`
- `0x1800061e3`: `APP_HOST_SERVICE::InitiateStopService`
- `0x1800061d6`: `Couldn't queue stop service work item\n`
- `0x18000611e`: `couldn't transition to service pause pending\n`
- `0x18000612b`: `APP_HOST_SERVICE::InitiatePauseService`
- `0x18000616d`: `APP_HOST_SERVICE::InitiatePauseService`
- `0x180006160`: `Couldn't queue pause service work item\n`
- `0x18000609c`: `couldn't transition to service continue pending\n`
- `0x1800060a9`: `APP_HOST_SERVICE::InitiateContinueService`
- `0x1800060eb`: `APP_HOST_SERVICE::InitiateContinueService`
- `0x1800060de`: `Couldn't queue continue service work item\n`

## pseudocode

```c
void __fastcall ServiceControlHandler(DWORD dwControl)
{
  APP_HOST_SERVICE *v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v3; // ebx
  APP_HOST_SERVICE *v4; // rdi
  APP_HOST_SERVICE *v5; // rdi
  APP_HOST_SERVICE *v6; // rdi
  const char *v7; // rax
  __int64 v8; // r8

  if ( dwControl != 1 )
  {
    switch ( dwControl )
    {
      case 2u:
        v5 = g_pAppHostService;
        v3 = APP_HOST_SERVICE::BeginStateTransition(g_pAppHostService, 6u);
        if ( v3 >= 0 )
        {
          v3 = MULTI_WORK_QUEUE::GetAndQueueWorkItem((APP_HOST_SERVICE *)((char *)v5 + 24), v5, 3u);
          if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
              1142,
              "APP_HOST_SERVICE::InitiatePauseService",
              v3,
              "Couldn't queue pause service work item\n");
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
            1124,
            "APP_HOST_SERVICE::InitiatePauseService",
            v3,
            "couldn't transition to service pause pending\n");
        }
        goto LABEL_33;
      case 3u:
        v4 = g_pAppHostService;
        v3 = APP_HOST_SERVICE::BeginStateTransition(g_pAppHostService, 5u);
        if ( v3 >= 0 )
        {
          v3 = MULTI_WORK_QUEUE::GetAndQueueWorkItem((APP_HOST_SERVICE *)((char *)v4 + 24), v4, 4u);
          if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
              1208,
              "APP_HOST_SERVICE::InitiateContinueService",
              v3,
              "Couldn't queue continue service work item\n");
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
            1190,
            "APP_HOST_SERVICE::InitiateContinueService",
            v3,
            "couldn't transition to service continue pending\n");
        }
        goto LABEL_33;
      case 4u:
        v1 = g_pAppHostService;
        v2 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pAppHostService + 152);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pAppHostService + 152));
        v3 = APP_HOST_SERVICE::ReportServiceStatus(v1);
        if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
            1006,
            "APP_HOST_SERVICE::InterrogateService",
            v3,
            "Couldn't report the service status\n");
        LeaveCriticalSection(v2);
        goto LABEL_33;
    }
    if ( dwControl != 5 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
          137,
          "ServiceControlHandler",
          "Service control ignored, OpCode: %lu\n",
          dwControl);
      return;
    }
  }
  v6 = g_pAppHostService;
  if ( *((_DWORD *)g_pAppHostService + 53) == 3 )
  {
    v3 = 0;
    goto LABEL_33;
  }
  v3 = APP_HOST_SERVICE::BeginStateTransition(g_pAppHostService, 3u);
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_33;
    v7 = "Couldn't transition to service stop pending\n";
    v8 = 1060;
LABEL_32:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
      v8,
      "APP_HOST_SERVICE::InitiateStopService",
      v3,
      v7);
    goto LABEL_33;
  }
  v3 = MULTI_WORK_QUEUE::GetAndQueueWorkItem((APP_HOST_SERVICE *)((char *)v6 + 24), v6, 2u);
  if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
  {
    v7 = "Couldn't queue stop service work item\n";
    v8 = 1077;
    goto LABEL_32;
  }
LABEL_33:
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147023835 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        155,
        "ServiceControlHandler",
        v3,
        "Service control operation failed\n");
    *((_DWORD *)g_pAppHostService + 66) = v3;
  }
}

```

## disassembly

```asm
0x180005f90  mov     [rsp+arg_0], rbx
0x180005f95  push    rdi
0x180005f96  sub     rsp, 30h
0x180005f9a  mov     eax, ecx
0x180005f9c  sub     eax, 1
0x180005f9f  jz      loc_180006176
0x180005fa5  sub     eax, 1
0x180005fa8  jz      loc_1800060F7
0x180005fae  sub     eax, 1
0x180005fb1  jz      loc_180006075
0x180005fb7  sub     eax, 1
0x180005fba  jz      short loc_180006008
0x180005fbc  cmp     eax, 1
0x180005fbf  jz      loc_180006176
0x180005fc5  test    byte ptr cs:g_dwDebugFlags, 3
0x180005fcc  jz      loc_180006262
0x180005fd2  mov     dword ptr [rsp+38h+var_10], ecx
0x180005fd6  lea     rax, aServiceControl_0; "Service control ignored, OpCode: %lu\n"
0x180005fdd  mov     rcx, cs:g_pDebug
0x180005fe4  lea     r9, aServicecontrol; "ServiceControlHandler"
0x180005feb  mov     r8d, 89h
0x180005ff1  mov     [rsp+38h+var_18], rax
0x180005ff6  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005ffd  call    cs:__imp_PuDbgPrint
0x180006003  jmp     loc_180006262
0x180006008  mov     rbx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x18000600f  lea     rdi, [rbx+98h]
0x180006016  mov     rcx, rdi; lpCriticalSection
0x180006019  call    cs:__imp_EnterCriticalSection
0x18000601f  mov     rcx, rbx; this
0x180006022  call    ?ReportServiceStatus@APP_HOST_SERVICE@@AEAAJXZ; APP_HOST_SERVICE::ReportServiceStatus(void)
0x180006027  mov     ebx, eax
0x180006029  test    eax, eax
0x18000602b  jns     short loc_180006067
0x18000602d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006034  jz      short loc_180006067
0x180006036  mov     rcx, cs:g_pDebug
0x18000603d  lea     rax, aCouldnTReportT; "Couldn't report the service status\n"
0x180006044  mov     [rsp+38h+var_10], rax
0x180006049  lea     r9, aAppHostService_14; "APP_HOST_SERVICE::InterrogateService"
0x180006050  mov     r8d, 3EEh
0x180006056  mov     dword ptr [rsp+38h+var_18], ebx
0x18000605a  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006061  call    cs:__imp_PuDbgPrintError
0x180006067  mov     rcx, rdi; lpCriticalSection
0x18000606a  call    cs:__imp_LeaveCriticalSection
0x180006070  jmp     loc_180006207
0x180006075  mov     rdi, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x18000607c  mov     edx, 5; unsigned int
0x180006081  mov     rcx, rdi; this
0x180006084  call    ?BeginStateTransition@APP_HOST_SERVICE@@AEAAJK@Z; APP_HOST_SERVICE::BeginStateTransition(ulong)
0x180006089  mov     ebx, eax
0x18000608b  test    eax, eax
0x18000608d  jns     short loc_1800060B5
0x18000608f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006096  jz      loc_180006207
0x18000609c  lea     rax, aCouldnTTransit_2; "couldn't transition to service continue"...
0x1800060a3  mov     r8d, 4A6h
0x1800060a9  lea     r9, aAppHostService_2; "APP_HOST_SERVICE::InitiateContinueServi"...
0x1800060b0  jmp     loc_1800061EA
0x1800060b5  lea     rcx, [rdi+18h]; this
0x1800060b9  mov     r8d, 4; unsigned __int64
0x1800060bf  mov     rdx, rdi; struct MULTI_WORK_DISPATCH *
0x1800060c2  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x1800060c7  mov     ebx, eax
0x1800060c9  test    eax, eax
0x1800060cb  jns     loc_180006207
0x1800060d1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800060d8  jz      loc_180006207
0x1800060de  lea     rax, aCouldnTQueueCo; "Couldn't queue continue service work it"...
0x1800060e5  mov     r8d, 4B8h
0x1800060eb  lea     r9, aAppHostService_2; "APP_HOST_SERVICE::InitiateContinueServi"...
0x1800060f2  jmp     loc_1800061EA
0x1800060f7  mov     rdi, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x1800060fe  mov     edx, 6; unsigned int
0x180006103  mov     rcx, rdi; this
0x180006106  call    ?BeginStateTransition@APP_HOST_SERVICE@@AEAAJK@Z; APP_HOST_SERVICE::BeginStateTransition(ulong)
0x18000610b  mov     ebx, eax
0x18000610d  test    eax, eax
0x18000610f  jns     short loc_180006137
0x180006111  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006118  jz      loc_180006207
0x18000611e  lea     rax, aCouldnTTransit; "couldn't transition to service pause pe"...
0x180006125  mov     r8d, 464h
0x18000612b  lea     r9, aAppHostService_8; "APP_HOST_SERVICE::InitiatePauseService"
0x180006132  jmp     loc_1800061EA
0x180006137  lea     rcx, [rdi+18h]; this
0x18000613b  mov     r8d, 3; unsigned __int64
0x180006141  mov     rdx, rdi; struct MULTI_WORK_DISPATCH *
0x180006144  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x180006149  mov     ebx, eax
0x18000614b  test    eax, eax
0x18000614d  jns     loc_180006207
0x180006153  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000615a  jz      loc_180006207
0x180006160  lea     rax, aCouldnTQueuePa; "Couldn't queue pause service work item"...
0x180006167  mov     r8d, 476h
0x18000616d  lea     r9, aAppHostService_8; "APP_HOST_SERVICE::InitiatePauseService"
0x180006174  jmp     short loc_1800061EA
0x180006176  mov     rdi, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x18000617d  cmp     dword ptr [rdi+0D4h], 3
0x180006184  jnz     short loc_18000618A
0x180006186  xor     ebx, ebx
0x180006188  jmp     short loc_180006207
0x18000618a  mov     edx, 3; unsigned int
0x18000618f  mov     rcx, rdi; this
0x180006192  call    ?BeginStateTransition@APP_HOST_SERVICE@@AEAAJK@Z; APP_HOST_SERVICE::BeginStateTransition(ulong)
0x180006197  mov     ebx, eax
0x180006199  test    eax, eax
0x18000619b  jns     short loc_1800061B5
0x18000619d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800061a4  jz      short loc_180006207
0x1800061a6  lea     rax, aCouldnTTransit_0; "Couldn't transition to service stop pen"...
0x1800061ad  mov     r8d, 424h
0x1800061b3  jmp     short loc_1800061E3
0x1800061b5  lea     rcx, [rdi+18h]; this
0x1800061b9  mov     r8d, 2; unsigned __int64
0x1800061bf  mov     rdx, rdi; struct MULTI_WORK_DISPATCH *
0x1800061c2  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x1800061c7  mov     ebx, eax
0x1800061c9  test    eax, eax
0x1800061cb  jns     short loc_180006207
0x1800061cd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800061d4  jz      short loc_180006207
0x1800061d6  lea     rax, aCouldnTQueueSt; "Couldn't queue stop service work item\n"
0x1800061dd  mov     r8d, 435h
0x1800061e3  lea     r9, aAppHostService_5; "APP_HOST_SERVICE::InitiateStopService"
0x1800061ea  mov     rcx, cs:g_pDebug
0x1800061f1  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800061f8  mov     [rsp+38h+var_10], rax
0x1800061fd  mov     dword ptr [rsp+38h+var_18], ebx
0x180006201  call    cs:__imp_PuDbgPrintError
0x180006207  mov     ecx, 80000000h
0x18000620c  lea     eax, [rbx+rcx]
0x18000620f  test    ecx, eax
0x180006211  jnz     short loc_180006262
0x180006213  cmp     ebx, 80070425h
0x180006219  jz      short loc_180006262
0x18000621b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006222  jz      short loc_180006255
0x180006224  mov     rcx, cs:g_pDebug
0x18000622b  lea     rax, aServiceControl; "Service control operation failed\n"
0x180006232  mov     [rsp+38h+var_10], rax
0x180006237  lea     r9, aServicecontrol; "ServiceControlHandler"
0x18000623e  mov     r8d, 9Bh
0x180006244  mov     dword ptr [rsp+38h+var_18], ebx
0x180006248  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000624f  call    cs:__imp_PuDbgPrintError
0x180006255  mov     rax, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x18000625c  mov     [rax+108h], ebx
0x180006262  mov     rbx, [rsp+38h+arg_0]
0x180006267  add     rsp, 30h
0x18000626b  pop     rdi
0x18000626c  retn
```
