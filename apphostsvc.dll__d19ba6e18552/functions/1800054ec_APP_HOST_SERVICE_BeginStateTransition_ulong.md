# APP_HOST_SERVICE::BeginStateTransition(ulong)

- ea: `0x1800054ec`
- end: `0x180005632`
- name: `?BeginStateTransition@APP_HOST_SERVICE@@AEAAJK@Z`
- size: `326`
- prototype: `__int64 __fastcall(APP_HOST_SERVICE *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005f90`
- `0x180006274`

## callees

- `0x1800054ec`
- `0x180005ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005621`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005514`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005514`
- `ntdll!RtlCreateTimer` at `0x1800055ee`
- `ntdll!RtlCreateTimer` at `0x1800055ee`
- `iisutil!PuDbgPrintError` at `0x1800055a9`
- `iisutil!PuDbgPrintError` at `0x1800055a9`

## string_xrefs

- `0x18000559e`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x18000557e`: `couldn't set service status\n`
- `0x180005592`: `APP_HOST_SERVICE::BeginStateTransition`
- `0x180005607`: `Could not create timer\n`

## pseudocode

```c
__int64 __fastcall APP_HOST_SERVICE::BeginStateTransition(APP_HOST_SERVICE *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  int v7; // ecx
  int v8; // ebx
  void *v9; // rcx
  NTSTATUS Timer; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
  v4 = 180000;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
  if ( a2 != 2 )
    v4 = 20000;
  EnterCriticalSection(v5);
  v7 = *((_DWORD *)this + 53);
  if ( (unsigned int)(v7 - 2) <= 1 || (unsigned int)(v7 - 5) <= 1 )
  {
    v8 = -2147023835;
  }
  else
  {
    *((_QWORD *)this + 27) = 0;
    *((_DWORD *)this + 53) = a2;
    *((_DWORD *)this + 56) = 0;
    *((_DWORD *)this + 57) = 1;
    *((_DWORD *)this + 58) = v4;
    v8 = APP_HOST_SERVICE::ReportServiceStatus(this);
    if ( v8 >= 0 )
    {
      if ( !*((_QWORD *)this + 31) && a2 != 2 )
      {
        v9 = (void *)*((_QWORD *)this + 32);
        if ( v9 )
        {
          Timer = RtlCreateTimer(v9, (PHANDLE)this + 31, UpdatePendingServiceStatusCallback, this, 0x2710u, 0x2710u, 4u);
          if ( Timer < 0 )
          {
            v8 = Timer | 0x10000000;
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
                2032,
                "APP_HOST_SERVICE::BeginStateTransition",
                v8,
                "Could not create timer\n");
          }
        }
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        1973,
        "APP_HOST_SERVICE::BeginStateTransition",
        v8,
        "couldn't set service status\n");
    }
  }
  LeaveCriticalSection(v2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800054ec  push    rbx
0x1800054ee  push    rbp
0x1800054ef  push    rsi
0x1800054f0  push    rdi
0x1800054f1  sub     rsp, 48h
0x1800054f5  cmp     edx, 2
0x1800054f8  lea     rbp, [rcx+98h]
0x1800054ff  mov     rdi, rcx
0x180005502  mov     eax, 4E20h
0x180005507  mov     ebx, 2BF20h
0x18000550c  mov     rcx, rbp; lpCriticalSection
0x18000550f  cmovnz  ebx, eax
0x180005512  mov     esi, edx
0x180005514  call    cs:__imp_EnterCriticalSection
0x18000551a  mov     ecx, [rdi+0D4h]
0x180005520  lea     eax, [rcx-2]
0x180005523  cmp     eax, 1
0x180005526  jbe     loc_180005619
0x18000552c  lea     eax, [rcx-5]
0x18000552f  cmp     eax, 1
0x180005532  jbe     loc_180005619
0x180005538  mov     rcx, rdi; this
0x18000553b  mov     qword ptr [rdi+0D8h], 0
0x180005546  mov     [rdi+0D4h], esi
0x18000554c  mov     dword ptr [rdi+0E0h], 0
0x180005556  mov     dword ptr [rdi+0E4h], 1
0x180005560  mov     [rdi+0E8h], ebx
0x180005566  call    ?ReportServiceStatus@APP_HOST_SERVICE@@AEAAJXZ; APP_HOST_SERVICE::ReportServiceStatus(void)
0x18000556b  mov     ebx, eax
0x18000556d  test    eax, eax
0x18000556f  jns     short loc_1800055B1
0x180005571  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005578  jz      loc_18000561E
0x18000557e  lea     rax, aCouldnTSetServ; "couldn't set service status\n"
0x180005585  mov     r8d, 7B5h
0x18000558b  mov     rcx, cs:g_pDebug
0x180005592  lea     r9, aAppHostService_10; "APP_HOST_SERVICE::BeginStateTransition"
0x180005599  mov     qword ptr [rsp+68h+Period], rax
0x18000559e  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800055a5  mov     [rsp+68h+DueTime], ebx
0x1800055a9  call    cs:__imp_PuDbgPrintError
0x1800055af  jmp     short loc_18000561E
0x1800055b1  lea     rdx, [rdi+0F8h]; phNewTimer
0x1800055b8  cmp     qword ptr [rdx], 0
0x1800055bc  jnz     short loc_18000561E
0x1800055be  cmp     esi, 2
0x1800055c1  jz      short loc_18000561E
0x1800055c3  mov     rcx, [rdi+100h]; TimerQueue
0x1800055ca  test    rcx, rcx
0x1800055cd  jz      short loc_18000561E
0x1800055cf  mov     eax, 2710h
0x1800055d4  mov     [rsp+68h+Flags], 4; Flags
0x1800055dc  mov     [rsp+68h+Period], eax; Period
0x1800055e0  lea     r8, ?UpdatePendingServiceStatusCallback@@YAXPEAXE@Z; Callback
0x1800055e7  mov     r9, rdi; Parameter
0x1800055ea  mov     [rsp+68h+DueTime], eax; DueTime
0x1800055ee  call    cs:__imp_RtlCreateTimer
0x1800055f4  test    eax, eax
0x1800055f6  jns     short loc_18000561E
0x1800055f8  mov     ebx, eax
0x1800055fa  bts     ebx, 1Ch
0x1800055fe  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005605  jz      short loc_18000561E
0x180005607  lea     rax, aCouldNotCreate_0; "Could not create timer\n"
0x18000560e  mov     r8d, 7F0h
0x180005614  jmp     loc_18000558B
0x180005619  mov     ebx, 80070425h
0x18000561e  mov     rcx, rbp; lpCriticalSection
0x180005621  call    cs:__imp_LeaveCriticalSection
0x180005627  mov     eax, ebx
0x180005629  add     rsp, 48h
0x18000562d  pop     rdi
0x18000562e  pop     rsi
0x18000562f  pop     rbp
0x180005630  pop     rbx
0x180005631  retn
```
