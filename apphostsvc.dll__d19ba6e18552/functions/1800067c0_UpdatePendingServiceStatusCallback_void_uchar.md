# UpdatePendingServiceStatusCallback(void *,uchar)

- ea: `0x1800067c0`
- end: `0x1800068a7`
- name: `?UpdatePendingServiceStatusCallback@@YAXPEAXE@Z`
- size: `231`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005ecc`
- `0x1800067c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000684b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000684b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067db`
- `iisutil!PuDbgPrintError` at `0x18000683e`
- `iisutil!PuDbgPrintError` at `0x180006889`
- `iisutil!PuDbgPrintError` at `0x18000683e`
- `iisutil!PuDbgPrintError` at `0x180006889`

## string_xrefs

- `0x180006837`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180006882`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180006865`: `Updating pending service status failed\n`
- `0x180006871`: `UpdatePendingServiceStatusCallback`
- `0x18000681a`: `Could not report service status\n`
- `0x180006826`: `APP_HOST_SERVICE::UpdatePendingServiceStatus`

## pseudocode

```c
void __fastcall UpdatePendingServiceStatusCallback(PVOID a1)
{
  APP_HOST_SERVICE *v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  unsigned int v3; // eax
  int v4; // ebx

  v1 = g_pAppHostService;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pAppHostService + 152);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pAppHostService + 152));
  v3 = *((_DWORD *)v1 + 53);
  if ( v3 == 4 || v3 <= 1 || v3 >= 7 )
  {
    v4 = 0;
  }
  else
  {
    ++*((_DWORD *)v1 + 57);
    v4 = APP_HOST_SERVICE::ReportServiceStatus(v1);
    if ( v4 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        2246,
        "APP_HOST_SERVICE::UpdatePendingServiceStatus",
        v4,
        "Could not report service status\n");
  }
  LeaveCriticalSection(v2);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        208,
        "UpdatePendingServiceStatusCallback",
        v4,
        "Updating pending service status failed\n");
    *((_DWORD *)g_pAppHostService + 66) = v4;
  }
}

```

## disassembly

```asm
0x1800067c0  mov     [rsp+arg_0], rbx
0x1800067c5  push    rdi
0x1800067c6  sub     rsp, 30h
0x1800067ca  mov     rbx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x1800067d1  lea     rdi, [rbx+98h]
0x1800067d8  mov     rcx, rdi; lpCriticalSection
0x1800067db  call    cs:__imp_EnterCriticalSection
0x1800067e1  mov     eax, [rbx+0D4h]
0x1800067e7  cmp     eax, 4
0x1800067ea  jz      short loc_180006846
0x1800067ec  cmp     eax, 1
0x1800067ef  jbe     short loc_180006846
0x1800067f1  cmp     eax, 7
0x1800067f4  jnb     short loc_180006846
0x1800067f6  inc     dword ptr [rbx+0E4h]
0x1800067fc  mov     rcx, rbx; this
0x1800067ff  call    ?ReportServiceStatus@APP_HOST_SERVICE@@AEAAJXZ; APP_HOST_SERVICE::ReportServiceStatus(void)
0x180006804  mov     ebx, eax
0x180006806  test    eax, eax
0x180006808  jns     short loc_180006848
0x18000680a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006811  jz      short loc_180006848
0x180006813  mov     rcx, cs:g_pDebug
0x18000681a  lea     rax, aCouldNotReport; "Could not report service status\n"
0x180006821  mov     [rsp+38h+var_10], rax
0x180006826  lea     r9, aAppHostService_12; "APP_HOST_SERVICE::UpdatePendingServiceS"...
0x18000682d  mov     r8d, 8C6h
0x180006833  mov     [rsp+38h+var_18], ebx
0x180006837  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000683e  call    cs:__imp_PuDbgPrintError
0x180006844  jmp     short loc_180006848
0x180006846  xor     ebx, ebx
0x180006848  mov     rcx, rdi; lpCriticalSection
0x18000684b  call    cs:__imp_LeaveCriticalSection
0x180006851  test    ebx, ebx
0x180006853  jns     short loc_18000689C
0x180006855  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000685c  jz      short loc_18000688F
0x18000685e  mov     rcx, cs:g_pDebug
0x180006865  lea     rax, aUpdatingPendin; "Updating pending service status failed"...
0x18000686c  mov     [rsp+38h+var_10], rax
0x180006871  lea     r9, aUpdatependings; "UpdatePendingServiceStatusCallback"
0x180006878  mov     r8d, 0D0h
0x18000687e  mov     [rsp+38h+var_18], ebx
0x180006882  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006889  call    cs:__imp_PuDbgPrintError
0x18000688f  mov     rax, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x180006896  mov     [rax+108h], ebx
0x18000689c  mov     rbx, [rsp+38h+arg_0]
0x1800068a1  add     rsp, 30h
0x1800068a5  pop     rdi
0x1800068a6  retn
```
