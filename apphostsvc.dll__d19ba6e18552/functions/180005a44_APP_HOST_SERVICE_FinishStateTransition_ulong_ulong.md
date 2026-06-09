# APP_HOST_SERVICE::FinishStateTransition(ulong,ulong)

- ea: `0x180005a44`
- end: `0x180005b41`
- name: `?FinishStateTransition@APP_HOST_SERVICE@@AEAAJKK@Z`
- size: `253`
- prototype: `__int64 __fastcall(APP_HOST_SERVICE *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005930`
- `0x180006274`

## callees

- `0x180005638`
- `0x180005a44`
- `0x180005ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ab9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ab9`
- `iisutil!PuDbgPrintError` at `0x180005aa4`
- `iisutil!PuDbgPrintError` at `0x180005b27`
- `iisutil!PuDbgPrintError` at `0x180005aa4`
- `iisutil!PuDbgPrintError` at `0x180005b27`

## string_xrefs

- `0x180005a9d`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180005b20`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180005a8c`: `APP_HOST_SERVICE::FinishStateTransition`
- `0x180005b0f`: `APP_HOST_SERVICE::FinishStateTransition`
- `0x180005b03`: `Could not update service status\n`

## pseudocode

```c
__int64 __fastcall APP_HOST_SERVICE::FinishStateTransition(APP_HOST_SERVICE *this, int a2, int a3)
{
  int v3; // edi

  v3 = 0;
  if ( *((_DWORD *)this + 53) == a3 )
  {
    v3 = APP_HOST_SERVICE::CancelPendingServiceStatusTimer(this);
    if ( v3 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
      *((_QWORD *)this + 27) = 7;
      *((_DWORD *)this + 53) = a2;
      *((_QWORD *)this + 28) = 0;
      *((_DWORD *)this + 58) = 0;
      v3 = APP_HOST_SERVICE::ReportServiceStatus(this);
      if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
          2140,
          "APP_HOST_SERVICE::FinishStateTransition",
          v3,
          "Could not update service status\n");
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        2107,
        "APP_HOST_SERVICE::FinishStateTransition",
        v3,
        "Could not cancel timer\n");
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180005a44  push    rbx
0x180005a46  push    rbp
0x180005a47  push    rsi
0x180005a48  push    rdi
0x180005a49  sub     rsp, 38h
0x180005a4d  xor     edi, edi
0x180005a4f  mov     ebp, edx
0x180005a51  mov     rbx, rcx
0x180005a54  cmp     [rcx+0D4h], r8d
0x180005a5b  jnz     loc_180005B36
0x180005a61  call    ?CancelPendingServiceStatusTimer@APP_HOST_SERVICE@@AEAAJXZ; APP_HOST_SERVICE::CancelPendingServiceStatusTimer(void)
0x180005a66  mov     edi, eax
0x180005a68  test    eax, eax
0x180005a6a  jns     short loc_180005AAF
0x180005a6c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005a73  jz      loc_180005B36
0x180005a79  mov     rcx, cs:g_pDebug
0x180005a80  lea     rax, aCouldNotCancel_0; "Could not cancel timer\n"
0x180005a87  mov     [rsp+58h+var_30], rax
0x180005a8c  lea     r9, aAppHostService_6; "APP_HOST_SERVICE::FinishStateTransition"
0x180005a93  mov     r8d, 83Bh
0x180005a99  mov     [rsp+58h+var_38], edi
0x180005a9d  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005aa4  call    cs:__imp_PuDbgPrintError
0x180005aaa  jmp     loc_180005B36
0x180005aaf  lea     rsi, [rbx+98h]
0x180005ab6  mov     rcx, rsi; lpCriticalSection
0x180005ab9  call    cs:__imp_EnterCriticalSection
0x180005abf  mov     rcx, rbx; this
0x180005ac2  mov     qword ptr [rbx+0D8h], 7
0x180005acd  mov     [rbx+0D4h], ebp
0x180005ad3  mov     qword ptr [rbx+0E0h], 0
0x180005ade  mov     dword ptr [rbx+0E8h], 0
0x180005ae8  call    ?ReportServiceStatus@APP_HOST_SERVICE@@AEAAJXZ; APP_HOST_SERVICE::ReportServiceStatus(void)
0x180005aed  mov     edi, eax
0x180005aef  test    eax, eax
0x180005af1  jns     short loc_180005B2D
0x180005af3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005afa  jz      short loc_180005B2D
0x180005afc  mov     rcx, cs:g_pDebug
0x180005b03  lea     rax, aCouldNotUpdate; "Could not update service status\n"
0x180005b0a  mov     [rsp+58h+var_30], rax
0x180005b0f  lea     r9, aAppHostService_6; "APP_HOST_SERVICE::FinishStateTransition"
0x180005b16  mov     r8d, 85Ch
0x180005b1c  mov     [rsp+58h+var_38], edi
0x180005b20  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005b27  call    cs:__imp_PuDbgPrintError
0x180005b2d  mov     rcx, rsi; lpCriticalSection
0x180005b30  call    cs:__imp_LeaveCriticalSection
0x180005b36  mov     eax, edi
0x180005b38  add     rsp, 38h
0x180005b3c  pop     rdi
0x180005b3d  pop     rsi
0x180005b3e  pop     rbp
0x180005b3f  pop     rbx
0x180005b40  retn
```
