# MyServiceTerminate(void)

- ea: `0x180154600`
- end: `0x180154833`
- name: `?MyServiceTerminate@@YAXXZ`
- size: `563`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180153cd0`

## callees

- `0x180154600`
- `0x180154874`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180154721`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180154721`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1801547a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1801547a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180154797`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180154797`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801547e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801547e2`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18015470f`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18015470f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18015481d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18015481d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180154613`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180154613`
- `MMDevAPI!__imp_CleanupDeviceAPI` at `0x180154777`
- `MMDevAPI!__imp_CleanupDeviceAPI` at `0x180154777`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18015464a`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180154667`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180154684`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18015464a`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180154667`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180154684`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801546a1`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801546be`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801546db`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801546a1`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801546be`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801546db`

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
    ((void (__fastcall *)(struct IMMDeviceEnumerator *))g_DeviceEnumerator->lpVtbl->Release)(g_DeviceEnumerator);
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
0x180154600  mov     [rsp+arg_0], rbx
0x180154605  mov     [rsp+arg_8], rsi
0x18015460a  push    rdi
0x18015460b  sub     rsp, 20h
0x18015460f  xor     edx, edx; dwCoInit
0x180154611  xor     ecx, ecx; pvReserved
0x180154613  call    cs:__imp_CoInitializeEx
0x180154619  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180154620  mov     edi, eax
0x180154622  shr     edi, 1Fh
0x180154625  xor     dil, 1
0x180154629  mov     rdx, [rcx]
0x18015462c  mov     rax, [rdx+20h]
0x180154630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154635  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18015463c  xor     esi, esi
0x18015463e  mov     rax, [rcx+8]
0x180154642  test    rax, rax
0x180154645  jz      short loc_18015465B
0x180154647  mov     rcx, rax
0x18015464a  call    cs:__imp_CM_Unregister_Notification
0x180154650  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180154657  mov     [rcx+8], rsi
0x18015465b  mov     rax, [rcx+10h]
0x18015465f  test    rax, rax
0x180154662  jz      short loc_180154678
0x180154664  mov     rcx, rax
0x180154667  call    cs:__imp_CM_Unregister_Notification
0x18015466d  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180154674  mov     [rcx+10h], rsi
0x180154678  mov     rax, [rcx+18h]
0x18015467c  test    rax, rax
0x18015467f  jz      short loc_180154695
0x180154681  mov     rcx, rax
0x180154684  call    cs:__imp_CM_Unregister_Notification
0x18015468a  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180154691  mov     [rcx+18h], rsi
0x180154695  mov     rax, [rcx+28h]
0x180154699  test    rax, rax
0x18015469c  jz      short loc_1801546B2
0x18015469e  mov     rcx, rax; RegistrationHandle
0x1801546a1  call    cs:__imp_PowerSettingUnregisterNotification
0x1801546a7  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801546ae  mov     [rcx+28h], rsi
0x1801546b2  mov     rax, [rcx+20h]
0x1801546b6  test    rax, rax
0x1801546b9  jz      short loc_1801546CF
0x1801546bb  mov     rcx, rax; RegistrationHandle
0x1801546be  call    cs:__imp_PowerSettingUnregisterNotification
0x1801546c4  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801546cb  mov     [rcx+20h], rsi
0x1801546cf  mov     rax, [rcx+30h]
0x1801546d3  test    rax, rax
0x1801546d6  jz      short loc_1801546EC
0x1801546d8  mov     rcx, rax; RegistrationHandle
0x1801546db  call    cs:__imp_PowerSettingUnregisterNotification
0x1801546e1  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801546e8  mov     [rcx+30h], rsi
0x1801546ec  mov     rax, cs:?g_EventWorkerThreadHandle@@3PEAXEA; void * g_EventWorkerThreadHandle
0x1801546f3  test    rax, rax
0x1801546f6  jz      short loc_18015474C
0x1801546f8  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x1801546ff  or      ebx, 0FFFFFFFFh
0x180154702  test    rcx, rcx
0x180154705  jz      short loc_18015471C
0x180154707  xor     r9d, r9d; lpOverlapped
0x18015470a  xor     r8d, r8d; dwCompletionKey
0x18015470d  mov     edx, ebx; dwNumberOfBytesTransferred
0x18015470f  call    cs:__imp_PostQueuedCompletionStatus
0x180154715  mov     rax, cs:?g_EventWorkerThreadHandle@@3PEAXEA; void * g_EventWorkerThreadHandle
0x18015471c  mov     edx, ebx; dwMilliseconds
0x18015471e  mov     rcx, rax; hHandle
0x180154721  call    cs:__imp_WaitForSingleObject
0x180154727  mov     rcx, cs:?g_EventWorkerThreadHandle@@3PEAXEA; hObject
0x18015472e  lea     rax, [rcx-1]
0x180154732  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180154736  ja      short loc_180154745
0x180154738  call    cs:__imp_CloseHandle
0x18015473e  mov     cs:?g_EventWorkerThreadHandle@@3PEAXEA, rsi; void * g_EventWorkerThreadHandle
0x180154745  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18015474c  mov     rax, [rcx]
0x18015474f  mov     rax, [rax+28h]
0x180154753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154758  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18015475f  test    rcx, rcx
0x180154762  jz      short loc_180154777
0x180154764  mov     rax, [rcx]
0x180154767  mov     rax, [rax+10h]
0x18015476b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154770  mov     cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA, rsi; IMMDeviceEnumerator * g_DeviceEnumerator
0x180154777  call    cs:__imp_CleanupDeviceAPI
0x18015477d  mov     rbx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x180154784  test    rbx, rbx
0x180154787  jz      short loc_1801547CA
0x180154789  mov     rcx, [rbx+50h]; ptpcg
0x18015478d  test    rcx, rcx
0x180154790  jz      short loc_1801547B2
0x180154792  xor     r8d, r8d; pvCleanupContext
0x180154795  xor     edx, edx; fCancelPendingCallbacks
0x180154797  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18015479d  mov     rcx, [rbx+50h]; ptpcg
0x1801547a1  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1801547a7  mov     [rbx+50h], rsi
0x1801547ab  mov     rbx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x1801547b2  test    rbx, rbx
0x1801547b5  jz      short loc_1801547CA
0x1801547b7  mov     rax, [rbx]
0x1801547ba  mov     edx, 1
0x1801547bf  mov     rcx, rbx
0x1801547c2  mov     rax, [rax]
0x1801547c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801547ca  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; hObject
0x1801547d1  mov     cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA, rsi; CAudioThreadPool * ThreadPool
0x1801547d8  lea     rax, [rcx-1]
0x1801547dc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801547e0  ja      short loc_1801547EF
0x1801547e2  call    cs:__imp_CloseHandle
0x1801547e8  mov     cs:?g_WorkerEventPort@@3PEAXEA, rsi; void * g_WorkerEventPort
0x1801547ef  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801547f6  test    rcx, rcx
0x1801547f9  jz      short loc_18015480C
0x1801547fb  mov     rax, [rcx]
0x1801547fe  mov     edx, 1
0x180154803  mov     rax, [rax+70h]
0x180154807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015480c  mov     cs:?g_AudioService@@3PEAVIAudioService@@EA, rsi; IAudioService * g_AudioService
0x180154813  call    McGenEventUnregister_EtwEventUnregister
0x180154818  test    dil, dil
0x18015481b  jz      short loc_180154823
0x18015481d  call    cs:__imp_CoUninitialize
0x180154823  mov     rbx, [rsp+28h+arg_0]
0x180154828  mov     rsi, [rsp+28h+arg_8]
0x18015482d  add     rsp, 20h
0x180154831  pop     rdi
0x180154832  retn
```
