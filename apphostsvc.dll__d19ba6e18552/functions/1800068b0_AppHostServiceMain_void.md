# AppHostServiceMain(void)

- ea: `0x1800068b0`
- end: `0x180006ac9`
- name: `?AppHostServiceMain@@YAXXZ`
- size: `537`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006d10`

## callees

- `0x1800068b0`
- `0x180008c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000690e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000690e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a3c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000696e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000696e`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180006a6e`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180006a6e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006aa7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006aa7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006900`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006900`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800069b0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800069b0`
- `iisutil!PuDbgPrintError` at `0x18000695b`
- `iisutil!PuDbgPrintError` at `0x180006a33`
- `iisutil!PuDbgPrintError` at `0x18000695b`
- `iisutil!PuDbgPrintError` at `0x180006a33`

## string_xrefs

- `0x180006954`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\main.cxx`
- `0x180006a28`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\main.cxx`
- `0x180006937`: `CreateThread() failed\n`
- `0x180006943`: `AppHostServiceMain`
- `0x180006a1c`: `AppHostServiceMain`
- `0x1800069d8`: `GetExitCodeThread() failed\n`
- `0x180006a08`: `AppHostServiceThreadProc() failed\n`

## pseudocode

```c
void AppHostServiceMain(void)
{
  HANDLE v0; // rax
  void *v1; // rdi
  signed int v2; // eax
  signed int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  SERVICE_STATUS_HANDLE v6; // rax
  DWORD ExitCode; // [rsp+30h] [rbp-30h] BYREF
  DWORD ThreadId; // [rsp+34h] [rbp-2Ch] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-28h] BYREF

  ExitCode = 0;
  ThreadId = 0;
  v0 = CreateThread(0, 0x8000u, AppHostServiceThreadProc, 0, 0, &ThreadId);
  v1 = v0;
  if ( v0 )
  {
    if ( WaitForSingleObject(v0, 0xFFFFFFFF) == -1 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\main.cxx",
          433,
          "AppHostServiceMain",
          v3,
          "WaitForSingleObject() failed\n");
    }
    else if ( GetExitCodeThread(v1, &ExitCode) )
    {
      v3 = 0;
      if ( ExitCode )
      {
        v3 = (int)ExitCode > 0 ? (unsigned __int16)ExitCode | 0x80070000 : ExitCode;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\main.cxx",
            470,
            "AppHostServiceMain",
            v3,
            "AppHostServiceThreadProc() failed\n");
      }
    }
    else
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\main.cxx",
          452,
          "AppHostServiceMain",
          v3,
          "GetExitCodeThread() failed\n");
    }
    CloseHandle(v1);
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\main.cxx",
        418,
        "AppHostServiceMain",
        v3,
        "CreateThread() failed\n");
  }
  if ( !g_RegisterServiceCalled )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( v3 >= 0 )
      v3 = -2147467259;
    v6 = RegisterServiceCtrlHandlerW(L"apphostsvc", guard_check_icall_nop);
    if ( v6 )
    {
      ServiceStatus.dwServiceType = 32;
      ServiceStatus.dwControlsAccepted = 7;
      ServiceStatus.dwCurrentState = 1;
      ServiceStatus.dwWin32ExitCode = 1066;
      ServiceStatus.dwServiceSpecificExitCode = v3;
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      SetServiceStatus(v6, &ServiceStatus);
    }
  }
}

```

## disassembly

```asm
0x1800068b0  mov     [rsp-8+arg_0], rbx
0x1800068b5  mov     [rsp-8+arg_8], rdi
0x1800068ba  push    rbp
0x1800068bb  mov     rbp, rsp
0x1800068be  sub     rsp, 60h
0x1800068c2  mov     rax, cs:__security_cookie
0x1800068c9  xor     rax, rsp
0x1800068cc  mov     [rbp+var_8], rax
0x1800068d0  lea     rax, [rbp+ThreadId]
0x1800068d4  mov     [rbp+ExitCode], 0
0x1800068db  mov     [rsp+60h+lpThreadId], rax; lpThreadId
0x1800068e0  lea     r8, ?AppHostServiceThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800068e7  xor     r9d, r9d; lpParameter
0x1800068ea  mov     [rsp+60h+dwCreationFlags], 0; dwCreationFlags
0x1800068f2  mov     edx, 8000h; dwStackSize
0x1800068f7  mov     [rbp+ThreadId], 0
0x1800068fe  xor     ecx, ecx; lpThreadAttributes
0x180006900  call    cs:__imp_CreateThread
0x180006906  mov     rdi, rax
0x180006909  test    rax, rax
0x18000690c  jnz     short loc_180006966
0x18000690e  call    cs:__imp_GetLastError
0x180006914  mov     ebx, eax
0x180006916  test    eax, eax
0x180006918  jle     short loc_180006923
0x18000691a  movzx   ebx, ax
0x18000691d  or      ebx, 80070000h
0x180006923  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000692a  jz      loc_180006A42
0x180006930  mov     rcx, cs:g_pDebug
0x180006937  lea     rax, aCreatethreadFa; "CreateThread() failed\n"
0x18000693e  mov     [rsp+60h+lpThreadId], rax
0x180006943  lea     r9, aApphostservice_0; "AppHostServiceMain"
0x18000694a  mov     r8d, 1A2h
0x180006950  mov     [rsp+60h+dwCreationFlags], ebx
0x180006954  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000695b  call    cs:__imp_PuDbgPrintError
0x180006961  jmp     loc_180006A42
0x180006966  or      ebx, 0FFFFFFFFh
0x180006969  mov     rcx, rdi; hHandle
0x18000696c  mov     edx, ebx; dwMilliseconds
0x18000696e  call    cs:__imp_WaitForSingleObject
0x180006974  cmp     eax, ebx
0x180006976  jnz     short loc_1800069A9
0x180006978  call    cs:__imp_GetLastError
0x18000697e  mov     ebx, eax
0x180006980  test    eax, eax
0x180006982  jle     short loc_18000698D
0x180006984  movzx   ebx, ax
0x180006987  or      ebx, 80070000h
0x18000698d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006994  jz      loc_180006A39
0x18000699a  lea     rax, aWaitforsingleo; "WaitForSingleObject() failed\n"
0x1800069a1  mov     r8d, 1B1h
0x1800069a7  jmp     short loc_180006A15
0x1800069a9  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1800069ad  mov     rcx, rdi; hThread
0x1800069b0  call    cs:__imp_GetExitCodeThread
0x1800069b6  test    eax, eax
0x1800069b8  jnz     short loc_1800069E7
0x1800069ba  call    cs:__imp_GetLastError
0x1800069c0  mov     ebx, eax
0x1800069c2  test    eax, eax
0x1800069c4  jle     short loc_1800069CF
0x1800069c6  movzx   ebx, ax
0x1800069c9  or      ebx, 80070000h
0x1800069cf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800069d6  jz      short loc_180006A39
0x1800069d8  lea     rax, aGetexitcodethr; "GetExitCodeThread() failed\n"
0x1800069df  mov     r8d, 1C4h
0x1800069e5  jmp     short loc_180006A15
0x1800069e7  mov     eax, [rbp+ExitCode]
0x1800069ea  xor     ebx, ebx
0x1800069ec  test    eax, eax
0x1800069ee  jz      short loc_180006A39
0x1800069f0  jg      short loc_1800069F6
0x1800069f2  mov     ebx, eax
0x1800069f4  jmp     short loc_1800069FF
0x1800069f6  movzx   ebx, ax
0x1800069f9  or      ebx, 80070000h
0x1800069ff  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006a06  jz      short loc_180006A39
0x180006a08  lea     rax, aApphostservice; "AppHostServiceThreadProc() failed\n"
0x180006a0f  mov     r8d, 1D6h
0x180006a15  mov     rcx, cs:g_pDebug
0x180006a1c  lea     r9, aApphostservice_0; "AppHostServiceMain"
0x180006a23  mov     [rsp+60h+lpThreadId], rax
0x180006a28  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006a2f  mov     [rsp+60h+dwCreationFlags], ebx
0x180006a33  call    cs:__imp_PuDbgPrintError
0x180006a39  mov     rcx, rdi; hObject
0x180006a3c  call    cs:__imp_CloseHandle
0x180006a42  cmp     cs:?g_RegisterServiceCalled@@3HA, 0; int g_RegisterServiceCalled
0x180006a49  jnz     short loc_180006AAD
0x180006a4b  xorps   xmm0, xmm0
0x180006a4e  lea     rdx, _guard_check_icall_nop; lpHandlerProc
0x180006a55  mov     eax, 80004005h
0x180006a5a  lea     rcx, aApphostsvc_1; "apphostsvc"
0x180006a61  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x180006a65  test    ebx, ebx
0x180006a67  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x180006a6b  cmovns  ebx, eax
0x180006a6e  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180006a74  test    rax, rax
0x180006a77  jz      short loc_180006AAD
0x180006a79  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180006a7d  mov     [rbp+ServiceStatus.dwServiceType], 20h ; ' '
0x180006a84  mov     rcx, rax; hServiceStatus
0x180006a87  mov     [rbp+ServiceStatus.dwControlsAccepted], 7
0x180006a8e  mov     [rbp+ServiceStatus.dwCurrentState], 1
0x180006a95  mov     [rbp+ServiceStatus.dwWin32ExitCode], 42Ah
0x180006a9c  mov     [rbp+ServiceStatus.dwServiceSpecificExitCode], ebx
0x180006a9f  mov     qword ptr [rbp+ServiceStatus.dwCheckPoint], 0
0x180006aa7  call    cs:__imp_SetServiceStatus
0x180006aad  mov     rcx, [rbp+var_8]
0x180006ab1  xor     rcx, rsp; StackCookie
0x180006ab4  call    __security_check_cookie
0x180006ab9  mov     rbx, [rsp+60h+arg_0]
0x180006abe  mov     rdi, [rsp+60h+arg_8]
0x180006ac3  add     rsp, 60h
0x180006ac7  pop     rbp
0x180006ac8  retn
```
