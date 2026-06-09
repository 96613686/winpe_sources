# TsiUninitialize(void)

- ea: `0x180015b08`
- end: `0x180015c1e`
- name: `?TsiUninitialize@@YAJXZ`
- size: `278`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016120`
- `0x1800161d0`

## callees

- `0x18000ea40`
- `0x18000ef3c`
- `0x18000f418`
- `0x180015b08`
- `0x180017340`
- `0x180020c30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180015baa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015bc7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015baa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015bc7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015bd9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015bd9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180015b65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180015b65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180015b82`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180015b82`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180015b58`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180015b58`

## pseudocode

```c
__int64 __fastcall TsiUninitialize(CScheduleMgr *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r8
  PdcManager *v4; // rbx
  HMODULE v5; // rcx
  _BYTE v7[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, ServiceUninitializeStarted, a3, 1, v7);
  CScheduleMgr::Deinitialize(a1);
  if ( ThreadpoolCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(ThreadpoolCleanupGroup, 0, 0);
    CloseThreadpoolCleanupGroup(ThreadpoolCleanupGroup);
    ThreadpoolCleanupGroup = 0;
  }
  if ( ThreadPool )
  {
    CloseThreadpool(ThreadPool);
    ThreadPool = 0;
  }
  v4 = g_PdcManager;
  if ( g_PdcManager )
  {
    PdcManager::~PdcManager(g_PdcManager);
    operator delete(v4);
  }
  g_PdcManager = 0;
  if ( ActionExtensionFunctionTable )
    operator delete(ActionExtensionFunctionTable);
  v5 = g_hModuleWptsExtensions;
  if ( g_hModuleWptsExtensions )
    FreeLibrary(g_hModuleWptsExtensions);
  if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v5, ServiceUninitializeCompleted, v3, 1, v7);
  McGenEventUnregister_EventUnregister();
  return 0;
}

```

## disassembly

```asm
0x180015b08  push    rbx
0x180015b0a  sub     rsp, 50h
0x180015b0e  mov     rax, cs:__security_cookie
0x180015b15  xor     rax, rsp
0x180015b18  mov     [rsp+58h+var_18], rax
0x180015b1d  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 8
0x180015b24  jz      short loc_180015B42
0x180015b26  lea     rax, [rsp+58h+var_28]
0x180015b2b  mov     r9d, 1
0x180015b31  lea     rdx, ServiceUninitializeStarted
0x180015b38  mov     [rsp+58h+var_38], rax
0x180015b3d  call    McGenEventWrite_EventWriteTransfer
0x180015b42  call    ?Deinitialize@CScheduleMgr@@QEAAXXZ; CScheduleMgr::Deinitialize(void)
0x180015b47  mov     rcx, cs:?ThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180015b4e  test    rcx, rcx
0x180015b51  jz      short loc_180015B76
0x180015b53  xor     r8d, r8d; pvCleanupContext
0x180015b56  xor     edx, edx; fCancelPendingCallbacks
0x180015b58  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180015b5e  mov     rcx, cs:?ThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180015b65  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180015b6b  mov     cs:?ThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, 0; _TP_CLEANUP_GROUP * ThreadpoolCleanupGroup
0x180015b76  mov     rcx, cs:?ThreadPool@@3PEAU_TP_POOL@@EA; ptpp
0x180015b7d  test    rcx, rcx
0x180015b80  jz      short loc_180015B93
0x180015b82  call    cs:__imp_CloseThreadpool
0x180015b88  mov     cs:?ThreadPool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * ThreadPool
0x180015b93  mov     rbx, cs:?g_PdcManager@@3PEAVPdcManager@@EA; PdcManager * g_PdcManager
0x180015b9a  test    rbx, rbx
0x180015b9d  jz      short loc_180015BB0
0x180015b9f  mov     rcx, rbx; this
0x180015ba2  call    ??1PdcManager@@QEAA@XZ; PdcManager::~PdcManager(void)
0x180015ba7  mov     rcx, rbx
0x180015baa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015bb0  mov     rcx, cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA; _ActionExtFunctions * ActionExtensionFunctionTable
0x180015bb7  mov     cs:?g_PdcManager@@3PEAVPdcManager@@EA, 0; PdcManager * g_PdcManager
0x180015bc2  test    rcx, rcx
0x180015bc5  jz      short loc_180015BCD
0x180015bc7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015bcd  mov     rcx, cs:?g_hModuleWptsExtensions@@3PEAUHINSTANCE__@@EA; hLibModule
0x180015bd4  test    rcx, rcx
0x180015bd7  jz      short loc_180015BDF
0x180015bd9  call    cs:__imp_FreeLibrary
0x180015bdf  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 8
0x180015be6  jz      short loc_180015C04
0x180015be8  lea     rax, [rsp+58h+var_28]
0x180015bed  mov     r9d, 1
0x180015bf3  lea     rdx, ServiceUninitializeCompleted
0x180015bfa  mov     [rsp+58h+var_38], rax
0x180015bff  call    McGenEventWrite_EventWriteTransfer
0x180015c04  call    McGenEventUnregister_EventUnregister
0x180015c09  xor     eax, eax
0x180015c0b  mov     rcx, [rsp+58h+var_18]
0x180015c10  xor     rcx, rsp; StackCookie
0x180015c13  call    __security_check_cookie
0x180015c18  add     rsp, 50h
0x180015c1c  pop     rbx
0x180015c1d  retn
```
