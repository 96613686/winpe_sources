# APP_HOST_SERVICE::StopServiceWorkItem(void)

- ea: `0x1800063a0`
- end: `0x18000648c`
- name: `?StopServiceWorkItem@APP_HOST_SERVICE@@AEAAXXZ`
- size: `236`
- prototype: `void __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005930`
- `0x180006274`

## callees

- `0x1800063a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000643c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000643c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000641f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000641f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800063b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800063b3`
- `iisutil!PuDbgPrintError` at `0x180006415`
- `iisutil!PuDbgPrintError` at `0x180006480`
- `iisutil!PuDbgPrintError` at `0x180006415`
- `iisutil!PuDbgPrintError` at `0x180006480`

## string_xrefs

- `0x18000640a`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180006475`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x1800063ea`: `Error while waiting for start to complete.\n`
- `0x1800063fc`: `APP_HOST_SERVICE::StopServiceWorkItem`
- `0x180006467`: `APP_HOST_SERVICE::StopServiceWorkItem`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::StopServiceWorkItem(HANDLE *this)
{
  signed int LastError; // eax
  signed int v3; // eax

  if ( WaitForSingleObject(this[30], 0xFFFFFFFF) == -1 && (g_dwDebugFlags & 0xF) != 0 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147467259;
    }
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
      676,
      "APP_HOST_SERVICE::StopServiceWorkItem",
      LastError,
      "Error while waiting for start to complete.\n");
  }
  if ( !SetEvent(this[2]) && (g_dwDebugFlags & 0xF) != 0 )
  {
    if ( GetLastError() )
    {
      v3 = GetLastError();
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
      685,
      "APP_HOST_SERVICE::StopServiceWorkItem",
      v3,
      "Error setting shutdown event.\n");
  }
}

```

## disassembly

```asm
0x1800063a0  push    rbx
0x1800063a2  sub     rsp, 30h
0x1800063a6  mov     rbx, rcx
0x1800063a9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800063ac  mov     rcx, [rcx+0F0h]; hHandle
0x1800063b3  call    cs:__imp_WaitForSingleObject
0x1800063b9  cmp     eax, 0FFFFFFFFh
0x1800063bc  jnz     short loc_18000641B
0x1800063be  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800063c5  jz      short loc_18000641B
0x1800063c7  call    cs:__imp_GetLastError
0x1800063cd  test    eax, eax
0x1800063cf  jz      short loc_1800063E5
0x1800063d1  call    cs:__imp_GetLastError
0x1800063d7  test    eax, eax
0x1800063d9  jle     short loc_1800063EA
0x1800063db  movzx   eax, ax
0x1800063de  or      eax, 80070000h
0x1800063e3  jmp     short loc_1800063EA
0x1800063e5  mov     eax, 80004005h
0x1800063ea  lea     rcx, aErrorWhileWait; "Error while waiting for start to comple"...
0x1800063f1  mov     r8d, 2A4h
0x1800063f7  mov     [rsp+38h+var_10], rcx
0x1800063fc  lea     r9, aAppHostService_3; "APP_HOST_SERVICE::StopServiceWorkItem"
0x180006403  mov     rcx, cs:g_pDebug
0x18000640a  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006411  mov     [rsp+38h+var_18], eax
0x180006415  call    cs:__imp_PuDbgPrintError
0x18000641b  mov     rcx, [rbx+10h]; hEvent
0x18000641f  call    cs:__imp_SetEvent
0x180006425  test    eax, eax
0x180006427  jnz     short loc_180006486
0x180006429  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006430  jz      short loc_180006486
0x180006432  call    cs:__imp_GetLastError
0x180006438  test    eax, eax
0x18000643a  jz      short loc_180006450
0x18000643c  call    cs:__imp_GetLastError
0x180006442  test    eax, eax
0x180006444  jle     short loc_180006455
0x180006446  movzx   eax, ax
0x180006449  or      eax, 80070000h
0x18000644e  jmp     short loc_180006455
0x180006450  mov     eax, 80004005h
0x180006455  lea     rcx, aErrorSettingSh; "Error setting shutdown event.\n"
0x18000645c  mov     r8d, 2ADh
0x180006462  mov     [rsp+38h+var_10], rcx
0x180006467  lea     r9, aAppHostService_3; "APP_HOST_SERVICE::StopServiceWorkItem"
0x18000646e  mov     rcx, cs:g_pDebug
0x180006475  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000647c  mov     [rsp+38h+var_18], eax
0x180006480  call    cs:__imp_PuDbgPrintError
0x180006486  add     rsp, 30h
0x18000648a  pop     rbx
0x18000648b  retn
```
