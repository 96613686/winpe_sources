# APP_HOST_SERVICE::Terminate(void)

- ea: `0x180006494`
- end: `0x1800066dd`
- name: `?Terminate@APP_HOST_SERVICE@@AEAAXXZ`
- size: `585`
- prototype: `void __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800066e4`

## callees

- `0x180001048`
- `0x180005638`
- `0x180006494`
- `0x18000a010`

## import_xrefs

- `ntdll!RtlDeleteTimerQueueEx` at `0x180006644`
- `ntdll!RtlDeleteTimerQueueEx` at `0x180006644`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800064b9`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006523`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800064b9`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006523`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800064f3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000656f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800064f3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000656f`
- `iisutil!PuDbgPrintError` at `0x18000662e`
- `iisutil!PuDbgPrintError` at `0x180006686`
- `iisutil!PuDbgPrintError` at `0x18000662e`
- `iisutil!PuDbgPrintError` at `0x180006686`
- `iisutil!TerminateIISUtil` at `0x1800066d6`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800066ae`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800066ae`
- `nativerd!TerminateNativeConfiguration` at `0x180006699`
- `nativerd!TerminateNativeConfiguration` at `0x180006699`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x1800064c4`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x18000652e`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x1800064c4`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x18000652e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800065ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800065ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800065b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800065b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800065d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800065d3`

## string_xrefs

- `0x180006623`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180006675`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180006603`: `Could not cancel pending service status timer\n`
- `0x180006615`: `APP_HOST_SERVICE::Terminate`
- `0x180006657`: `Could not delete timer queue\n`
- `0x180006667`: `APP_HOST_SERVICE::DeleteTimerQueue`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::Terminate(APP_HOST_SERVICE *this)
{
  CReaderWriterLock3 *v1; // rsi
  __int64 v3; // rcx
  struct _TP_CLEANUP_GROUP *v4; // rcx
  struct _TP_POOL *v5; // rcx
  int v6; // eax
  void *v7; // rcx
  NTSTATUS v8; // eax
  void *v9; // rbx
  struct INativeConfigurationSystem *v10; // [rsp+40h] [rbp+8h] BYREF

  v1 = (APP_HOST_SERVICE *)((char *)this + 456);
  v10 = 0;
  CReaderWriterLock3::WriteLock((APP_HOST_SERVICE *)((char *)this + 456));
  if ( (int)GetDefaultNativeConfigurationSystem(&v10) >= 0 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *, char *))(*(_QWORD *)v10 + 48LL))(
      v10,
      (char *)this + 272);
    *((_DWORD *)this + 116) = 1;
  }
  CReaderWriterLock3::WriteUnlock(v1);
  if ( v10 )
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v10 + 16LL))(v10);
  v10 = 0;
  CReaderWriterLock3::WriteLock((APP_HOST_SERVICE *)((char *)this + 496));
  if ( (int)GetDefaultNativeConfigurationSystem(&v10) >= 0 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *, char *))(*(_QWORD *)v10 + 48LL))(
      v10,
      (char *)this + 472);
    v3 = *((_QWORD *)this + 63);
    if ( v3 )
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v3 + 48LL))(v3, (char *)this + 472);
    *((_DWORD *)this + 149) = 1;
  }
  CReaderWriterLock3::WriteUnlock((APP_HOST_SERVICE *)((char *)this + 496));
  if ( v10 )
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( *((_DWORD *)this + 9) != 1 )
  {
    _InterlockedExchange((volatile __int32 *)this + 9, 1);
    v4 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 16);
    if ( v4 )
    {
      CloseThreadpoolCleanupGroupMembers(v4, 1, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 16));
      *((_QWORD *)this + 16) = 0;
    }
    v5 = (struct _TP_POOL *)*((_QWORD *)this + 15);
    if ( v5 )
    {
      CloseThreadpool(v5);
      *((_QWORD *)this + 15) = 0;
    }
    if ( *((_DWORD *)this + 28) )
      *((_DWORD *)this + 28) = 0;
  }
  v6 = APP_HOST_SERVICE::CancelPendingServiceStatusTimer(this);
  if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
      1572,
      "APP_HOST_SERVICE::Terminate",
      v6,
      "Could not cancel pending service status timer\n");
  v7 = (void *)*((_QWORD *)this + 32);
  if ( v7 )
  {
    v8 = RtlDeleteTimerQueueEx(v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( v8 >= 0 )
    {
      *((_QWORD *)this + 32) = 0;
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        1843,
        "APP_HOST_SERVICE::DeleteTimerQueue",
        v8 | 0x10000000,
        "Could not delete timer queue\n");
    }
  }
  TerminateNativeConfiguration();
  v9 = MULTI_WORK_ITEM::sm_pAllocCacheHandler;
  if ( MULTI_WORK_ITEM::sm_pAllocCacheHandler )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)MULTI_WORK_ITEM::sm_pAllocCacheHandler);
    operator delete(v9);
    MULTI_WORK_ITEM::sm_pAllocCacheHandler = 0;
  }
  TerminateIISUtil();
}

```

## disassembly

```asm
0x180006494  mov     [rsp+arg_8], rbx
0x180006499  mov     [rsp+arg_10], rsi
0x18000649e  push    rdi
0x18000649f  sub     rsp, 30h
0x1800064a3  lea     rsi, [rcx+1C8h]
0x1800064aa  mov     [rsp+38h+arg_0], 0
0x1800064b3  mov     rbx, rcx
0x1800064b6  mov     rcx, rsi
0x1800064b9  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800064bf  lea     rcx, [rsp+38h+arg_0]
0x1800064c4  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x1800064ca  test    eax, eax
0x1800064cc  js      short loc_1800064F0
0x1800064ce  mov     rcx, [rsp+38h+arg_0]
0x1800064d3  lea     rdx, [rbx+110h]
0x1800064da  mov     rax, [rcx]
0x1800064dd  mov     rax, [rax+30h]
0x1800064e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e6  mov     dword ptr [rbx+1D0h], 1
0x1800064f0  mov     rcx, rsi
0x1800064f3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800064f9  mov     rcx, [rsp+38h+arg_0]
0x1800064fe  test    rcx, rcx
0x180006501  jz      short loc_18000650F
0x180006503  mov     rax, [rcx]
0x180006506  mov     rax, [rax+10h]
0x18000650a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650f  lea     rdi, [rbx+1D8h]
0x180006516  mov     [rsp+38h+arg_0], 0
0x18000651f  lea     rcx, [rdi+18h]
0x180006523  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180006529  lea     rcx, [rsp+38h+arg_0]
0x18000652e  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x180006534  test    eax, eax
0x180006536  js      short loc_18000656B
0x180006538  mov     rcx, [rsp+38h+arg_0]
0x18000653d  mov     rdx, rdi
0x180006540  mov     rax, [rcx]
0x180006543  mov     rax, [rax+30h]
0x180006547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654c  mov     rcx, [rdi+20h]
0x180006550  test    rcx, rcx
0x180006553  jz      short loc_180006564
0x180006555  mov     rax, [rcx]
0x180006558  mov     rdx, rdi
0x18000655b  mov     rax, [rax+30h]
0x18000655f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006564  mov     dword ptr [rdi+7Ch], 1
0x18000656b  lea     rcx, [rdi+18h]
0x18000656f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180006575  mov     rcx, [rsp+38h+arg_0]
0x18000657a  test    rcx, rcx
0x18000657d  jz      short loc_18000658B
0x18000657f  mov     rax, [rcx]
0x180006582  mov     rax, [rax+10h]
0x180006586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000658b  cmp     dword ptr [rbx+24h], 1
0x18000658f  jz      short loc_1800065EE
0x180006591  mov     eax, 1
0x180006596  xchg    eax, [rbx+24h]
0x180006599  mov     rcx, [rbx+80h]; ptpcg
0x1800065a0  test    rcx, rcx
0x1800065a3  jz      short loc_1800065CA
0x1800065a5  xor     r8d, r8d; pvCleanupContext
0x1800065a8  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800065ac  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800065b2  mov     rcx, [rbx+80h]; ptpcg
0x1800065b9  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800065bf  mov     qword ptr [rbx+80h], 0
0x1800065ca  mov     rcx, [rbx+78h]; ptpp
0x1800065ce  test    rcx, rcx
0x1800065d1  jz      short loc_1800065E1
0x1800065d3  call    cs:__imp_CloseThreadpool
0x1800065d9  mov     qword ptr [rbx+78h], 0
0x1800065e1  cmp     dword ptr [rbx+70h], 0
0x1800065e5  jz      short loc_1800065EE
0x1800065e7  mov     dword ptr [rbx+70h], 0
0x1800065ee  mov     rcx, rbx; this
0x1800065f1  call    ?CancelPendingServiceStatusTimer@APP_HOST_SERVICE@@AEAAJXZ; APP_HOST_SERVICE::CancelPendingServiceStatusTimer(void)
0x1800065f6  test    eax, eax
0x1800065f8  jns     short loc_180006634
0x1800065fa  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006601  jz      short loc_180006634
0x180006603  lea     rcx, aCouldNotCancel; "Could not cancel pending service status"...
0x18000660a  mov     r8d, 624h
0x180006610  mov     [rsp+38h+var_10], rcx
0x180006615  lea     r9, aAppHostService_0; "APP_HOST_SERVICE::Terminate"
0x18000661c  mov     rcx, cs:g_pDebug
0x180006623  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000662a  mov     [rsp+38h+var_18], eax
0x18000662e  call    cs:__imp_PuDbgPrintError
0x180006634  mov     rcx, [rbx+100h]; TimerQueue
0x18000663b  test    rcx, rcx
0x18000663e  jz      short loc_180006699
0x180006640  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180006644  call    cs:__imp_RtlDeleteTimerQueueEx
0x18000664a  test    eax, eax
0x18000664c  jns     short loc_18000668E
0x18000664e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006655  jz      short loc_180006699
0x180006657  lea     rcx, aCouldNotDelete; "Could not delete timer queue\n"
0x18000665e  bts     eax, 1Ch
0x180006662  mov     [rsp+38h+var_10], rcx
0x180006667  lea     r9, aAppHostService_17; "APP_HOST_SERVICE::DeleteTimerQueue"
0x18000666e  mov     rcx, cs:g_pDebug
0x180006675  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000667c  mov     r8d, 733h
0x180006682  mov     [rsp+38h+var_18], eax
0x180006686  call    cs:__imp_PuDbgPrintError
0x18000668c  jmp     short loc_180006699
0x18000668e  mov     qword ptr [rbx+100h], 0
0x180006699  call    cs:__imp_?TerminateNativeConfiguration@@YAXXZ; TerminateNativeConfiguration(void)
0x18000669f  mov     rbx, cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x1800066a6  test    rbx, rbx
0x1800066a9  jz      short loc_1800066C7
0x1800066ab  mov     rcx, rbx
0x1800066ae  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x1800066b4  mov     rcx, rbx; Block
0x1800066b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800066bc  mov     cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x1800066c7  mov     rbx, [rsp+38h+arg_8]
0x1800066cc  mov     rsi, [rsp+38h+arg_10]
0x1800066d1  add     rsp, 30h
0x1800066d5  pop     rdi
0x1800066d6  jmp     cs:__imp_TerminateIISUtil
```
