# MyServiceTerminate(void)

- ea: `0x18005d4cc`
- end: `0x18005d6ff`
- name: `?MyServiceTerminate@@YAXXZ`
- size: `563`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005cca0`

## callees

- `0x18005d4cc`
- `0x18005d728`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d5ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d5ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d604`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d6ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d604`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d6ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005d66d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005d66d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005d663`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005d663`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18005d5db`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18005d5db`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18005d516`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18005d533`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18005d550`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18005d516`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18005d533`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18005d550`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18005d56d`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18005d58a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18005d5a7`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18005d56d`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18005d58a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18005d5a7`
- `MMDevAPI!__imp_CleanupDeviceAPI` at `0x18005d643`
- `MMDevAPI!__imp_CleanupDeviceAPI` at `0x18005d643`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005d4df`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005d4df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005d6e9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005d6e9`

## pseudocode

```c
void MyServiceTerminate(void)
{
  bool v0; // di
  struct IAudioService *v1; // rcx
  HANDLE v2; // rax
  struct CAudioThreadPool *v3; // rbx
  struct _TP_CLEANUP_GROUP *v4; // rcx

  v0 = CoInitializeEx(0, 0) >= 0;
  (*(void (__fastcall **)(struct IAudioService *))(*(_QWORD *)g_AudioService + 32LL))(g_AudioService);
  v1 = g_AudioService;
  if ( *((_QWORD *)g_AudioService + 1) )
  {
    CM_Unregister_Notification(*((_QWORD *)g_AudioService + 1));
    v1 = g_AudioService;
    *((_QWORD *)g_AudioService + 1) = 0;
  }
  if ( *((_QWORD *)v1 + 2) )
  {
    CM_Unregister_Notification(*((_QWORD *)v1 + 2));
    v1 = g_AudioService;
    *((_QWORD *)g_AudioService + 2) = 0;
  }
  if ( *((_QWORD *)v1 + 3) )
  {
    CM_Unregister_Notification(*((_QWORD *)v1 + 3));
    v1 = g_AudioService;
    *((_QWORD *)g_AudioService + 3) = 0;
  }
  if ( *((_QWORD *)v1 + 5) )
  {
    PowerSettingUnregisterNotification(*((HPOWERNOTIFY *)v1 + 5));
    v1 = g_AudioService;
    *((_QWORD *)g_AudioService + 5) = 0;
  }
  if ( *((_QWORD *)v1 + 4) )
  {
    PowerSettingUnregisterNotification(*((HPOWERNOTIFY *)v1 + 4));
    v1 = g_AudioService;
    *((_QWORD *)g_AudioService + 4) = 0;
  }
  if ( *((_QWORD *)v1 + 6) )
  {
    PowerSettingUnregisterNotification(*((HPOWERNOTIFY *)v1 + 6));
    v1 = g_AudioService;
    *((_QWORD *)g_AudioService + 6) = 0;
  }
  v2 = g_EventWorkerThreadHandle;
  if ( g_EventWorkerThreadHandle )
  {
    if ( g_WorkerEventPort )
    {
      PostQueuedCompletionStatus(g_WorkerEventPort, 0xFFFFFFFF, 0, 0);
      v2 = g_EventWorkerThreadHandle;
    }
    WaitForSingleObject(v2, 0xFFFFFFFF);
    if ( (char *)g_EventWorkerThreadHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(g_EventWorkerThreadHandle);
      g_EventWorkerThreadHandle = 0;
    }
    v1 = g_AudioService;
  }
  (*(void (__fastcall **)(struct IAudioService *))(*(_QWORD *)v1 + 40LL))(v1);
  if ( g_DeviceEnumerator )
  {
    ((void (__fastcall *)(struct IUnknown *))g_DeviceEnumerator->lpVtbl->Release)(g_DeviceEnumerator);
    g_DeviceEnumerator = 0;
  }
  CleanupDeviceAPI();
  v3 = ThreadPool;
  if ( ThreadPool )
  {
    v4 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)ThreadPool + 10);
    if ( v4 )
    {
      CloseThreadpoolCleanupGroupMembers(v4, 0, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)v3 + 10));
      *((_QWORD *)v3 + 10) = 0;
      v3 = ThreadPool;
    }
    if ( v3 )
      (**(void (__fastcall ***)(struct CAudioThreadPool *, __int64))v3)(v3, 1);
  }
  ThreadPool = 0;
  if ( (char *)g_WorkerEventPort - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_WorkerEventPort);
    g_WorkerEventPort = 0;
  }
  if ( g_AudioService )
    (*(void (__fastcall **)(struct IAudioService *, __int64))(*(_QWORD *)g_AudioService + 112LL))(g_AudioService, 1);
  g_AudioService = 0;
  McGenEventUnregister_EtwEventUnregister();
  if ( v0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18005d4cc  mov     [rsp+arg_0], rbx
0x18005d4d1  mov     [rsp+arg_8], rsi
0x18005d4d6  push    rdi
0x18005d4d7  sub     rsp, 20h
0x18005d4db  xor     edx, edx; dwCoInit
0x18005d4dd  xor     ecx, ecx; pvReserved
0x18005d4df  call    cs:__imp_CoInitializeEx
0x18005d4e5  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d4ec  mov     edi, eax
0x18005d4ee  shr     edi, 1Fh
0x18005d4f1  xor     dil, 1
0x18005d4f5  mov     rdx, [rcx]
0x18005d4f8  mov     rax, [rdx+20h]
0x18005d4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d501  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d508  xor     esi, esi
0x18005d50a  mov     rax, [rcx+8]
0x18005d50e  test    rax, rax
0x18005d511  jz      short loc_18005D527
0x18005d513  mov     rcx, rax
0x18005d516  call    cs:__imp_CM_Unregister_Notification
0x18005d51c  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d523  mov     [rcx+8], rsi
0x18005d527  mov     rax, [rcx+10h]
0x18005d52b  test    rax, rax
0x18005d52e  jz      short loc_18005D544
0x18005d530  mov     rcx, rax
0x18005d533  call    cs:__imp_CM_Unregister_Notification
0x18005d539  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d540  mov     [rcx+10h], rsi
0x18005d544  mov     rax, [rcx+18h]
0x18005d548  test    rax, rax
0x18005d54b  jz      short loc_18005D561
0x18005d54d  mov     rcx, rax
0x18005d550  call    cs:__imp_CM_Unregister_Notification
0x18005d556  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d55d  mov     [rcx+18h], rsi
0x18005d561  mov     rax, [rcx+28h]
0x18005d565  test    rax, rax
0x18005d568  jz      short loc_18005D57E
0x18005d56a  mov     rcx, rax; RegistrationHandle
0x18005d56d  call    cs:__imp_PowerSettingUnregisterNotification
0x18005d573  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d57a  mov     [rcx+28h], rsi
0x18005d57e  mov     rax, [rcx+20h]
0x18005d582  test    rax, rax
0x18005d585  jz      short loc_18005D59B
0x18005d587  mov     rcx, rax; RegistrationHandle
0x18005d58a  call    cs:__imp_PowerSettingUnregisterNotification
0x18005d590  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d597  mov     [rcx+20h], rsi
0x18005d59b  mov     rax, [rcx+30h]
0x18005d59f  test    rax, rax
0x18005d5a2  jz      short loc_18005D5B8
0x18005d5a4  mov     rcx, rax; RegistrationHandle
0x18005d5a7  call    cs:__imp_PowerSettingUnregisterNotification
0x18005d5ad  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d5b4  mov     [rcx+30h], rsi
0x18005d5b8  mov     rax, cs:?g_EventWorkerThreadHandle@@3PEAXEA; void * g_EventWorkerThreadHandle
0x18005d5bf  test    rax, rax
0x18005d5c2  jz      short loc_18005D618
0x18005d5c4  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x18005d5cb  or      ebx, 0FFFFFFFFh
0x18005d5ce  test    rcx, rcx
0x18005d5d1  jz      short loc_18005D5E8
0x18005d5d3  xor     r9d, r9d; lpOverlapped
0x18005d5d6  xor     r8d, r8d; dwCompletionKey
0x18005d5d9  mov     edx, ebx; dwNumberOfBytesTransferred
0x18005d5db  call    cs:__imp_PostQueuedCompletionStatus
0x18005d5e1  mov     rax, cs:?g_EventWorkerThreadHandle@@3PEAXEA; void * g_EventWorkerThreadHandle
0x18005d5e8  mov     edx, ebx; dwMilliseconds
0x18005d5ea  mov     rcx, rax; hHandle
0x18005d5ed  call    cs:__imp_WaitForSingleObject
0x18005d5f3  mov     rcx, cs:?g_EventWorkerThreadHandle@@3PEAXEA; hObject
0x18005d5fa  lea     rax, [rcx-1]
0x18005d5fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d602  ja      short loc_18005D611
0x18005d604  call    cs:__imp_CloseHandle
0x18005d60a  mov     cs:?g_EventWorkerThreadHandle@@3PEAXEA, rsi; void * g_EventWorkerThreadHandle
0x18005d611  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d618  mov     rax, [rcx]
0x18005d61b  mov     rax, [rax+28h]
0x18005d61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d624  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18005d62b  test    rcx, rcx
0x18005d62e  jz      short loc_18005D643
0x18005d630  mov     rax, [rcx]
0x18005d633  mov     rax, [rax+10h]
0x18005d637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d63c  mov     cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA, rsi; IMMDeviceEnumerator * g_DeviceEnumerator
0x18005d643  call    cs:__imp_CleanupDeviceAPI
0x18005d649  mov     rbx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x18005d650  test    rbx, rbx
0x18005d653  jz      short loc_18005D696
0x18005d655  mov     rcx, [rbx+50h]; ptpcg
0x18005d659  test    rcx, rcx
0x18005d65c  jz      short loc_18005D67E
0x18005d65e  xor     r8d, r8d; pvCleanupContext
0x18005d661  xor     edx, edx; fCancelPendingCallbacks
0x18005d663  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18005d669  mov     rcx, [rbx+50h]; ptpcg
0x18005d66d  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18005d673  mov     [rbx+50h], rsi
0x18005d677  mov     rbx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x18005d67e  test    rbx, rbx
0x18005d681  jz      short loc_18005D696
0x18005d683  mov     rax, [rbx]
0x18005d686  mov     edx, 1
0x18005d68b  mov     rcx, rbx
0x18005d68e  mov     rax, [rax]
0x18005d691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d696  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; hObject
0x18005d69d  mov     cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA, rsi; CAudioThreadPool * ThreadPool
0x18005d6a4  lea     rax, [rcx-1]
0x18005d6a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d6ac  ja      short loc_18005D6BB
0x18005d6ae  call    cs:__imp_CloseHandle
0x18005d6b4  mov     cs:?g_WorkerEventPort@@3PEAXEA, rsi; void * g_WorkerEventPort
0x18005d6bb  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d6c2  test    rcx, rcx
0x18005d6c5  jz      short loc_18005D6D8
0x18005d6c7  mov     rax, [rcx]
0x18005d6ca  mov     edx, 1
0x18005d6cf  mov     rax, [rax+70h]
0x18005d6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d6d8  mov     cs:?g_AudioService@@3PEAVIAudioService@@EA, rsi; IAudioService * g_AudioService
0x18005d6df  call    McGenEventUnregister_EtwEventUnregister
0x18005d6e4  test    dil, dil
0x18005d6e7  jz      short loc_18005D6EF
0x18005d6e9  call    cs:__imp_CoUninitialize
0x18005d6ef  mov     rbx, [rsp+28h+arg_0]
0x18005d6f4  mov     rsi, [rsp+28h+arg_8]
0x18005d6f9  add     rsp, 20h
0x18005d6fd  pop     rdi
0x18005d6fe  retn
```
