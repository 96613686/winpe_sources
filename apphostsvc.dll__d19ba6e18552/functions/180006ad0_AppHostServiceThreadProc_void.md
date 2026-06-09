# AppHostServiceThreadProc(void *)

- ea: `0x180006ad0`
- end: `0x180006cf1`
- name: `?AppHostServiceThreadProc@@YAKPEAX@Z`
- size: `545`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180005290`
- `0x180005704`
- `0x180005b48`
- `0x180006ad0`
- `0x180007648`
- `0x180008c50`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b32`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006ca8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006ca8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006af4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006af4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006c2c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006cd4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006c2c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006cd4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006b23`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006b23`
- `iisutil!PuDbgPrintError` at `0x180006b7c`
- `iisutil!PuDbgPrintError` at `0x180006be9`
- `iisutil!PuDbgPrintError` at `0x180006b7c`
- `iisutil!PuDbgPrintError` at `0x180006be9`

## string_xrefs

- `0x180006b6e`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\main.cxx`
- `0x180006bdb`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\main.cxx`
- `0x180006b51`: `Failed to InitializeCfgWriter\n`
- `0x180006b61`: `AppHostServiceThreadProc`
- `0x180006bce`: `AppHostServiceThreadProc`
- `0x180006bba`: `Allocating APP_POOL_HELPER_SERVICE failed\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostServiceThreadProc(PVOID Parameter)
{
  unsigned int v1; // edi
  int v2; // esi
  signed int LastError; // eax
  bool v4; // sf
  APP_HOST_SERVICE *v5; // rax
  APP_HOST_SERVICE *v6; // rcx
  int v7; // eax
  APP_HOST_SERVICE *v8; // rcx
  APP_HOST_SERVICE *v9; // rcx
  SERVICE_STATUS_HANDLE v10; // rbx
  void *Thread; // [rsp+30h] [rbp-48h] BYREF
  DWORD ThreadId[2]; // [rsp+38h] [rbp-40h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-38h] BYREF

  v1 = 0;
  Thread = 0;
  if ( CoInitializeEx(0, 0) < 0 )
  {
    v2 = 0;
  }
  else
  {
    v2 = 1;
    ThreadId[0] = 0;
    Thread = CreateThread(0, 0, InitCfgWriterThread, 0, 0, ThreadId);
    if ( !Thread )
    {
      LastError = GetLastError();
      v4 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v4 = LastError < 0;
      }
      if ( v4 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\main.cxx",
          253,
          "AppHostServiceThreadProc",
          LastError,
          "Failed to InitializeCfgWriter\n",
          Thread);
    }
    v5 = (APP_HOST_SERVICE *)operator new(0x268u);
    *(_QWORD *)ThreadId = v5;
    if ( v5 )
      v5 = APP_HOST_SERVICE::APP_HOST_SERVICE(v5);
    g_pAppHostService = v5;
    if ( v5 )
    {
      v7 = APP_HOST_SERVICE::Initialize(v6);
      if ( v7 >= 0 )
      {
        APP_HOST_SERVICE::ExecuteService(v8);
        TerminateCfgWriter(&Thread);
        v2 = 0;
        CoUninitialize();
        v9 = g_pAppHostService;
        if ( g_RegisterServiceCalled )
        {
          v10 = (SERVICE_STATUS_HANDLE)*((_QWORD *)g_pAppHostService + 25);
          ServiceStatus = *(struct _SERVICE_STATUS *)((char *)g_pAppHostService + 208);
          *((_QWORD *)g_pAppHostService + 25) = 0;
          (*(void (__fastcall **)(APP_HOST_SERVICE *))(*(_QWORD *)v9 + 8LL))(v9);
          g_pAppHostService = 0;
          SetServiceStatus(v10, &ServiceStatus);
        }
        else
        {
          (*(void (__fastcall **)(APP_HOST_SERVICE *))(*(_QWORD *)g_pAppHostService + 8LL))(g_pAppHostService);
          g_pAppHostService = 0;
        }
      }
      else if ( (v7 & 0x1FFF0000) == 0x70000 )
      {
        v1 = (unsigned __int16)v7;
      }
      else
      {
        v1 = v7;
      }
    }
    else
    {
      v1 = 8;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\main.cxx",
          277,
          "AppHostServiceThreadProc",
          -2147024888,
          "Allocating APP_POOL_HELPER_SERVICE failed\n");
    }
  }
  TerminateCfgWriter(&Thread);
  if ( v2 )
    CoUninitialize();
  return v1;
}

```

## disassembly

```asm
0x180006ad0  push    rbp
0x180006ad2  push    rbx
0x180006ad3  push    rsi
0x180006ad4  push    rdi
0x180006ad5  mov     rbp, rsp
0x180006ad8  sub     rsp, 78h
0x180006adc  mov     rax, cs:__security_cookie
0x180006ae3  xor     rax, rsp
0x180006ae6  mov     [rbp+var_18], rax
0x180006aea  xor     edi, edi
0x180006aec  mov     [rbp+var_48], rdi
0x180006af0  xor     edx, edx; dwCoInit
0x180006af2  xor     ecx, ecx; pvReserved
0x180006af4  call    cs:__imp_CoInitializeEx
0x180006afa  test    eax, eax
0x180006afc  js      loc_180006CC5
0x180006b02  lea     esi, [rdi+1]
0x180006b05  mov     [rbp+ThreadId], edi
0x180006b08  lea     rax, [rbp+ThreadId]
0x180006b0c  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x180006b11  mov     [rsp+78h+dwCreationFlags], edi; dwCreationFlags
0x180006b15  xor     r9d, r9d; lpParameter
0x180006b18  lea     r8, ?InitCfgWriterThread@@YAKPEAX@Z; lpStartAddress
0x180006b1f  xor     edx, edx; dwStackSize
0x180006b21  xor     ecx, ecx; lpThreadAttributes
0x180006b23  call    cs:__imp_CreateThread
0x180006b29  mov     [rbp+var_48], rax
0x180006b2d  test    rax, rax
0x180006b30  jnz     short loc_180006B82
0x180006b32  call    cs:__imp_GetLastError
0x180006b38  test    eax, eax
0x180006b3a  jle     short loc_180006B46
0x180006b3c  movzx   eax, ax
0x180006b3f  or      eax, 80070000h
0x180006b44  test    eax, eax
0x180006b46  jns     short loc_180006B82
0x180006b48  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006b4f  jz      short loc_180006B82
0x180006b51  lea     rcx, aFailedToInitia; "Failed to InitializeCfgWriter\n"
0x180006b58  mov     [rsp+78h+lpThreadId], rcx
0x180006b5d  mov     [rsp+78h+dwCreationFlags], eax
0x180006b61  lea     r9, aApphostservice_1; "AppHostServiceThreadProc"
0x180006b68  mov     r8d, 0FDh
0x180006b6e  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006b75  mov     rcx, cs:g_pDebug
0x180006b7c  call    cs:__imp_PuDbgPrintError
0x180006b82  mov     ecx, 268h; Size
0x180006b87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006b8c  mov     qword ptr [rbp+ThreadId], rax
0x180006b90  test    rax, rax
0x180006b93  jz      short loc_180006B9E
0x180006b95  mov     rcx, rax; this
0x180006b98  call    ??0APP_HOST_SERVICE@@QEAA@XZ; APP_HOST_SERVICE::APP_HOST_SERVICE(void)
0x180006b9d  nop
0x180006b9e  mov     cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA, rax; APP_HOST_SERVICE * g_pAppHostService
0x180006ba5  test    rax, rax
0x180006ba8  jnz     short loc_180006BF4
0x180006baa  lea     edi, [rax+8]
0x180006bad  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006bb4  jz      loc_180006CC7
0x180006bba  lea     rax, aAllocatingAppP; "Allocating APP_POOL_HELPER_SERVICE fail"...
0x180006bc1  mov     [rsp+78h+lpThreadId], rax
0x180006bc6  mov     [rsp+78h+dwCreationFlags], 80070008h
0x180006bce  lea     r9, aApphostservice_1; "AppHostServiceThreadProc"
0x180006bd5  mov     r8d, 115h
0x180006bdb  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006be2  mov     rcx, cs:g_pDebug
0x180006be9  call    cs:__imp_PuDbgPrintError
0x180006bef  jmp     loc_180006CC7
0x180006bf4  call    ?Initialize@APP_HOST_SERVICE@@QEAAJXZ; APP_HOST_SERVICE::Initialize(void)
0x180006bf9  test    eax, eax
0x180006bfb  jns     short loc_180006C1C
0x180006bfd  mov     ecx, eax
0x180006bff  and     ecx, 1FFF0000h
0x180006c05  cmp     ecx, 70000h
0x180006c0b  jnz     short loc_180006C15
0x180006c0d  movzx   edi, ax
0x180006c10  jmp     loc_180006CC7
0x180006c15  mov     edi, eax
0x180006c17  jmp     loc_180006CC7
0x180006c1c  call    ?ExecuteService@APP_HOST_SERVICE@@QEAAXXZ; APP_HOST_SERVICE::ExecuteService(void)
0x180006c21  lea     rcx, [rbp+var_48]; void **
0x180006c25  call    ?TerminateCfgWriter@@YAXPEAPEAX@Z; TerminateCfgWriter(void * *)
0x180006c2a  xor     esi, esi
0x180006c2c  call    cs:__imp_CoUninitialize
0x180006c32  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x180006c39  cmp     cs:?g_RegisterServiceCalled@@3HA, esi; int g_RegisterServiceCalled
0x180006c3f  jz      short loc_180006CB0
0x180006c41  mov     rbx, [rcx+0C8h]
0x180006c48  mov     eax, [rcx+0D0h]
0x180006c4e  mov     [rbp+ServiceStatus.dwServiceType], eax
0x180006c51  mov     eax, [rcx+0D4h]
0x180006c57  mov     [rbp+ServiceStatus.dwCurrentState], eax
0x180006c5a  mov     eax, [rcx+0D8h]
0x180006c60  mov     [rbp+ServiceStatus.dwControlsAccepted], eax
0x180006c63  mov     eax, [rcx+0DCh]
0x180006c69  mov     [rbp+ServiceStatus.dwWin32ExitCode], eax
0x180006c6c  mov     eax, [rcx+0E0h]
0x180006c72  mov     [rbp+ServiceStatus.dwServiceSpecificExitCode], eax
0x180006c75  mov     eax, [rcx+0E4h]
0x180006c7b  mov     [rbp+ServiceStatus.dwCheckPoint], eax
0x180006c7e  mov     eax, [rcx+0E8h]
0x180006c84  mov     [rbp+ServiceStatus.dwWaitHint], eax
0x180006c87  mov     [rcx+0C8h], rsi
0x180006c8e  mov     rax, [rcx]
0x180006c91  mov     rax, [rax+8]
0x180006c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c9a  mov     cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA, rsi; APP_HOST_SERVICE * g_pAppHostService
0x180006ca1  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180006ca5  mov     rcx, rbx; hServiceStatus
0x180006ca8  call    cs:__imp_SetServiceStatus
0x180006cae  jmp     short loc_180006CC7
0x180006cb0  mov     rax, [rcx]
0x180006cb3  mov     rax, [rax+8]
0x180006cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cbc  mov     cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA, rsi; APP_HOST_SERVICE * g_pAppHostService
0x180006cc3  jmp     short loc_180006CC7
0x180006cc5  xor     esi, esi
0x180006cc7  lea     rcx, [rbp+var_48]; void **
0x180006ccb  call    ?TerminateCfgWriter@@YAXPEAPEAX@Z; TerminateCfgWriter(void * *)
0x180006cd0  test    esi, esi
0x180006cd2  jz      short loc_180006CDA
0x180006cd4  call    cs:__imp_CoUninitialize
0x180006cda  mov     eax, edi
0x180006cdc  mov     rcx, [rbp+var_18]
0x180006ce0  xor     rcx, rsp; StackCookie
0x180006ce3  call    __security_check_cookie
0x180006ce8  add     rsp, 78h
0x180006cec  pop     rdi
0x180006ced  pop     rsi
0x180006cee  pop     rbx
0x180006cef  pop     rbp
0x180006cf0  retn
```
