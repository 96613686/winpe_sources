# APP_HOST_SERVICE::StartServiceWorkItem(void)

- ea: `0x180006274`
- end: `0x180006398`
- name: `?StartServiceWorkItem@APP_HOST_SERVICE@@AEAAJXZ`
- size: `292`
- prototype: `__int64 __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005930`

## callees

- `0x1800054ec`
- `0x180005a44`
- `0x180005c3c`
- `0x180006274`
- `0x1800063a0`
- `0x180008464`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006379`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006379`
- `iisutil!PuDbgPrintError` at `0x1800062c4`
- `iisutil!PuDbgPrintError` at `0x180006347`
- `iisutil!PuDbgPrintError` at `0x1800062c4`
- `iisutil!PuDbgPrintError` at `0x180006347`

## string_xrefs

- `0x1800062b9`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x18000633c`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180006299`: `Initializing internal components failed\n`
- `0x1800062ad`: `APP_HOST_SERVICE::StartServiceWorkItem`
- `0x18000632e`: `APP_HOST_SERVICE::StartServiceWorkItem`
- `0x1800062ef`: `couldn't transition to service start pending\n`

## pseudocode

```c
__int64 __fastcall APP_HOST_SERVICE::StartServiceWorkItem(HANDLE *this)
{
  int v2; // ebx
  int v3; // eax

  v2 = APP_HOST_SERVICE::InitializeInternalComponents((APP_HOST_SERVICE *)this);
  if ( v2 >= 0 )
  {
    v2 = APP_HOST_SERVICE::BeginStateTransition((APP_HOST_SERVICE *)this, 2);
    if ( v2 >= 0 )
    {
      v3 = APP_HOST_SERVICE::FinishStateTransition((APP_HOST_SERVICE *)this, 4u, 2u);
      if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
          621,
          "APP_HOST_SERVICE::StartServiceWorkItem",
          v3,
          "Couldn't finish transition into the running state\n");
      v2 = MULTI_WORK_QUEUE::GetAndQueueWorkItem(
             (MULTI_WORK_QUEUE *)(this + 3),
             (struct MULTI_WORK_DISPATCH *)((unsigned __int64)(this + 35)
                                          & ((unsigned __int128)-(__int128)(unsigned __int64)(this + 34) >> 64)),
             1);
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        609,
        "APP_HOST_SERVICE::StartServiceWorkItem",
        v2,
        "couldn't transition to service start pending\n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
      596,
      "APP_HOST_SERVICE::StartServiceWorkItem",
      v2,
      "Initializing internal components failed\n");
  }
  SetEvent(this[30]);
  if ( v2 < 0 )
    APP_HOST_SERVICE::StopServiceWorkItem((APP_HOST_SERVICE *)this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006274  mov     [rsp+arg_0], rbx
0x180006279  push    rdi
0x18000627a  sub     rsp, 30h
0x18000627e  mov     rdi, rcx
0x180006281  call    ?InitializeInternalComponents@APP_HOST_SERVICE@@AEAAJXZ; APP_HOST_SERVICE::InitializeInternalComponents(void)
0x180006286  mov     ebx, eax
0x180006288  test    eax, eax
0x18000628a  jns     short loc_1800062CF
0x18000628c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006293  jz      loc_180006372
0x180006299  lea     rax, aInitializingIn; "Initializing internal components failed"...
0x1800062a0  mov     r8d, 254h
0x1800062a6  mov     rcx, cs:g_pDebug
0x1800062ad  lea     r9, aAppHostService_16; "APP_HOST_SERVICE::StartServiceWorkItem"
0x1800062b4  mov     [rsp+38h+var_10], rax
0x1800062b9  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800062c0  mov     [rsp+38h+var_18], ebx
0x1800062c4  call    cs:__imp_PuDbgPrintError
0x1800062ca  jmp     loc_180006372
0x1800062cf  mov     edx, 2; unsigned int
0x1800062d4  mov     rcx, rdi; this
0x1800062d7  call    ?BeginStateTransition@APP_HOST_SERVICE@@AEAAJK@Z; APP_HOST_SERVICE::BeginStateTransition(ulong)
0x1800062dc  mov     ebx, eax
0x1800062de  test    eax, eax
0x1800062e0  jns     short loc_1800062FE
0x1800062e2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800062e9  jz      loc_180006372
0x1800062ef  lea     rax, aCouldnTTransit_1; "couldn't transition to service start pe"...
0x1800062f6  mov     r8d, 261h
0x1800062fc  jmp     short loc_1800062A6
0x1800062fe  mov     edx, 4; unsigned int
0x180006303  mov     rcx, rdi; this
0x180006306  lea     r8d, [rdx-2]; unsigned int
0x18000630a  call    ?FinishStateTransition@APP_HOST_SERVICE@@AEAAJKK@Z; APP_HOST_SERVICE::FinishStateTransition(ulong,ulong)
0x18000630f  test    eax, eax
0x180006311  jns     short loc_18000634D
0x180006313  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000631a  jz      short loc_18000634D
0x18000631c  lea     rcx, aCouldnTFinishT_0; "Couldn't finish transition into the run"...
0x180006323  mov     r8d, 26Dh
0x180006329  mov     [rsp+38h+var_10], rcx
0x18000632e  lea     r9, aAppHostService_16; "APP_HOST_SERVICE::StartServiceWorkItem"
0x180006335  mov     rcx, cs:g_pDebug
0x18000633c  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006343  mov     [rsp+38h+var_18], eax
0x180006347  call    cs:__imp_PuDbgPrintError
0x18000634d  lea     rax, [rdi+110h]
0x180006354  mov     r8d, 1; unsigned __int64
0x18000635a  lea     rcx, [rax+8]
0x18000635e  neg     rax
0x180006361  sbb     rdx, rdx
0x180006364  and     rdx, rcx; struct MULTI_WORK_DISPATCH *
0x180006367  lea     rcx, [rdi+18h]; this
0x18000636b  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x180006370  mov     ebx, eax
0x180006372  mov     rcx, [rdi+0F0h]; hEvent
0x180006379  call    cs:__imp_SetEvent
0x18000637f  test    ebx, ebx
0x180006381  jns     short loc_18000638B
0x180006383  mov     rcx, rdi; this
0x180006386  call    ?StopServiceWorkItem@APP_HOST_SERVICE@@AEAAXXZ; APP_HOST_SERVICE::StopServiceWorkItem(void)
0x18000638b  mov     eax, ebx
0x18000638d  mov     rbx, [rsp+38h+arg_0]
0x180006392  add     rsp, 30h
0x180006396  pop     rdi
0x180006397  retn
```
