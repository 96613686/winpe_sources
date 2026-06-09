# APP_HOST_SERVICE::ReportServiceStatus(void)

- ea: `0x180005ecc`
- end: `0x180005f88`
- name: `?ReportServiceStatus@APP_HOST_SERVICE@@AEAAJXZ`
- size: `188`
- prototype: `__int64 __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800054ec`
- `0x180005a44`
- `0x180005f90`
- `0x1800067c0`

## callees

- `0x180005ecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f31`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005f27`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005f27`
- `iisutil!PuDbgPrintError` at `0x180005f7a`
- `iisutil!PuDbgPrintError` at `0x180005f7a`
- `iisutil!PuDbgPrint` at `0x180005f0e`
- `iisutil!PuDbgPrint` at `0x180005f0e`

## string_xrefs

- `0x180005f07`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180005f73`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180005eee`: `Can't report service status because m_ServiceStatusHandle is null\n`
- `0x180005ef5`: `APP_HOST_SERVICE::ReportServiceStatus`
- `0x180005f62`: `APP_HOST_SERVICE::ReportServiceStatus`
- `0x180005f56`: `Setting service state failed\n`

## pseudocode

```c
__int64 __fastcall APP_HOST_SERVICE::ReportServiceStatus(APP_HOST_SERVICE *this)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  if ( *((_QWORD *)this + 25) )
  {
    v1 = 0;
    if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 25), (LPSERVICE_STATUS)((char *)this + 208)) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
          1727,
          "APP_HOST_SERVICE::ReportServiceStatus",
          v1,
          "Setting service state failed\n");
    }
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        1689,
        "APP_HOST_SERVICE::ReportServiceStatus",
        "Can't report service status because m_ServiceStatusHandle is null\n");
    return (unsigned int)-2147024890;
  }
  return v1;
}

```

## disassembly

```asm
0x180005ecc  push    rbx
0x180005ece  sub     rsp, 30h
0x180005ed2  mov     rax, [rcx+0C8h]
0x180005ed9  test    rax, rax
0x180005edc  jnz     short loc_180005F1B
0x180005ede  test    byte ptr cs:g_dwDebugFlags, 3
0x180005ee5  jz      short loc_180005F14
0x180005ee7  mov     rcx, cs:g_pDebug
0x180005eee  lea     rax, aCanTReportServ; "Can't report service status because m_S"...
0x180005ef5  lea     r9, aAppHostService_4; "APP_HOST_SERVICE::ReportServiceStatus"
0x180005efc  mov     [rsp+38h+var_18], rax
0x180005f01  mov     r8d, 699h
0x180005f07  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005f0e  call    cs:__imp_PuDbgPrint
0x180005f14  mov     ebx, 80070006h
0x180005f19  jmp     short loc_180005F80
0x180005f1b  lea     rdx, [rcx+0D0h]; lpServiceStatus
0x180005f22  xor     ebx, ebx
0x180005f24  mov     rcx, rax; hServiceStatus
0x180005f27  call    cs:__imp_SetServiceStatus
0x180005f2d  test    eax, eax
0x180005f2f  jnz     short loc_180005F80
0x180005f31  call    cs:__imp_GetLastError
0x180005f37  mov     ebx, eax
0x180005f39  test    eax, eax
0x180005f3b  jle     short loc_180005F46
0x180005f3d  movzx   ebx, ax
0x180005f40  or      ebx, 80070000h
0x180005f46  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005f4d  jz      short loc_180005F80
0x180005f4f  mov     rcx, cs:g_pDebug
0x180005f56  lea     rax, aSettingService; "Setting service state failed\n"
0x180005f5d  mov     [rsp+38h+var_10], rax
0x180005f62  lea     r9, aAppHostService_4; "APP_HOST_SERVICE::ReportServiceStatus"
0x180005f69  mov     r8d, 6BFh
0x180005f6f  mov     dword ptr [rsp+38h+var_18], ebx
0x180005f73  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005f7a  call    cs:__imp_PuDbgPrintError
0x180005f80  mov     eax, ebx
0x180005f82  add     rsp, 30h
0x180005f86  pop     rbx
0x180005f87  retn
```
