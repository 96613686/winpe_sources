# MyServiceTerminate(void)

- ea: `0x180155310`
- end: `0x180155543`
- name: `?MyServiceTerminate@@YAXXZ`
- size: `563`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801549e0`

## callees

- `0x180155310`
- `0x180155584`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180155431`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180155431`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1801554b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1801554b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1801554a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1801554a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180155448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801554f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180155448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801554f2`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18015541f`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18015541f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180155323`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180155323`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18015552d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18015552d`
- `MMDevAPI!__imp_CleanupDeviceAPI` at `0x180155487`
- `MMDevAPI!__imp_CleanupDeviceAPI` at `0x180155487`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18015535a`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180155377`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180155394`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18015535a`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180155377`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180155394`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801553b1`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801553ce`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801553eb`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801553b1`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801553ce`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1801553eb`

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
0x180155310  mov     [rsp+arg_0], rbx
0x180155315  mov     [rsp+arg_8], rsi
0x18015531a  push    rdi
0x18015531b  sub     rsp, 20h
0x18015531f  xor     edx, edx; dwCoInit
0x180155321  xor     ecx, ecx; pvReserved
0x180155323  call    cs:__imp_CoInitializeEx
0x180155329  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180155330  mov     edi, eax
0x180155332  shr     edi, 1Fh
0x180155335  xor     dil, 1
0x180155339  mov     rdx, [rcx]
0x18015533c  mov     rax, [rdx+20h]
0x180155340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155345  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18015534c  xor     esi, esi
0x18015534e  mov     rax, [rcx+8]
0x180155352  test    rax, rax
0x180155355  jz      short loc_18015536B
0x180155357  mov     rcx, rax
0x18015535a  call    cs:__imp_CM_Unregister_Notification
0x180155360  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180155367  mov     [rcx+8], rsi
0x18015536b  mov     rax, [rcx+10h]
0x18015536f  test    rax, rax
0x180155372  jz      short loc_180155388
0x180155374  mov     rcx, rax
0x180155377  call    cs:__imp_CM_Unregister_Notification
0x18015537d  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180155384  mov     [rcx+10h], rsi
0x180155388  mov     rax, [rcx+18h]
0x18015538c  test    rax, rax
0x18015538f  jz      short loc_1801553A5
0x180155391  mov     rcx, rax
0x180155394  call    cs:__imp_CM_Unregister_Notification
0x18015539a  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801553a1  mov     [rcx+18h], rsi
0x1801553a5  mov     rax, [rcx+28h]
0x1801553a9  test    rax, rax
0x1801553ac  jz      short loc_1801553C2
0x1801553ae  mov     rcx, rax; RegistrationHandle
0x1801553b1  call    cs:__imp_PowerSettingUnregisterNotification
0x1801553b7  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801553be  mov     [rcx+28h], rsi
0x1801553c2  mov     rax, [rcx+20h]
0x1801553c6  test    rax, rax
0x1801553c9  jz      short loc_1801553DF
0x1801553cb  mov     rcx, rax; RegistrationHandle
0x1801553ce  call    cs:__imp_PowerSettingUnregisterNotification
0x1801553d4  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801553db  mov     [rcx+20h], rsi
0x1801553df  mov     rax, [rcx+30h]
0x1801553e3  test    rax, rax
0x1801553e6  jz      short loc_1801553FC
0x1801553e8  mov     rcx, rax; RegistrationHandle
0x1801553eb  call    cs:__imp_PowerSettingUnregisterNotification
0x1801553f1  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801553f8  mov     [rcx+30h], rsi
0x1801553fc  mov     rax, cs:?g_EventWorkerThreadHandle@@3PEAXEA; void * g_EventWorkerThreadHandle
0x180155403  test    rax, rax
0x180155406  jz      short loc_18015545C
0x180155408  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x18015540f  or      ebx, 0FFFFFFFFh
0x180155412  test    rcx, rcx
0x180155415  jz      short loc_18015542C
0x180155417  xor     r9d, r9d; lpOverlapped
0x18015541a  xor     r8d, r8d; dwCompletionKey
0x18015541d  mov     edx, ebx; dwNumberOfBytesTransferred
0x18015541f  call    cs:__imp_PostQueuedCompletionStatus
0x180155425  mov     rax, cs:?g_EventWorkerThreadHandle@@3PEAXEA; void * g_EventWorkerThreadHandle
0x18015542c  mov     edx, ebx; dwMilliseconds
0x18015542e  mov     rcx, rax; hHandle
0x180155431  call    cs:__imp_WaitForSingleObject
0x180155437  mov     rcx, cs:?g_EventWorkerThreadHandle@@3PEAXEA; hObject
0x18015543e  lea     rax, [rcx-1]
0x180155442  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180155446  ja      short loc_180155455
0x180155448  call    cs:__imp_CloseHandle
0x18015544e  mov     cs:?g_EventWorkerThreadHandle@@3PEAXEA, rsi; void * g_EventWorkerThreadHandle
0x180155455  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18015545c  mov     rax, [rcx]
0x18015545f  mov     rax, [rax+28h]
0x180155463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155468  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18015546f  test    rcx, rcx
0x180155472  jz      short loc_180155487
0x180155474  mov     rax, [rcx]
0x180155477  mov     rax, [rax+10h]
0x18015547b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155480  mov     cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA, rsi; IMMDeviceEnumerator * g_DeviceEnumerator
0x180155487  call    cs:__imp_CleanupDeviceAPI
0x18015548d  mov     rbx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x180155494  test    rbx, rbx
0x180155497  jz      short loc_1801554DA
0x180155499  mov     rcx, [rbx+50h]; ptpcg
0x18015549d  test    rcx, rcx
0x1801554a0  jz      short loc_1801554C2
0x1801554a2  xor     r8d, r8d; pvCleanupContext
0x1801554a5  xor     edx, edx; fCancelPendingCallbacks
0x1801554a7  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1801554ad  mov     rcx, [rbx+50h]; ptpcg
0x1801554b1  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1801554b7  mov     [rbx+50h], rsi
0x1801554bb  mov     rbx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x1801554c2  test    rbx, rbx
0x1801554c5  jz      short loc_1801554DA
0x1801554c7  mov     rax, [rbx]
0x1801554ca  mov     edx, 1
0x1801554cf  mov     rcx, rbx
0x1801554d2  mov     rax, [rax]
0x1801554d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801554da  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; hObject
0x1801554e1  mov     cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA, rsi; CAudioThreadPool * ThreadPool
0x1801554e8  lea     rax, [rcx-1]
0x1801554ec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801554f0  ja      short loc_1801554FF
0x1801554f2  call    cs:__imp_CloseHandle
0x1801554f8  mov     cs:?g_WorkerEventPort@@3PEAXEA, rsi; void * g_WorkerEventPort
0x1801554ff  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180155506  test    rcx, rcx
0x180155509  jz      short loc_18015551C
0x18015550b  mov     rax, [rcx]
0x18015550e  mov     edx, 1
0x180155513  mov     rax, [rax+70h]
0x180155517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015551c  mov     cs:?g_AudioService@@3PEAVIAudioService@@EA, rsi; IAudioService * g_AudioService
0x180155523  call    McGenEventUnregister_EtwEventUnregister
0x180155528  test    dil, dil
0x18015552b  jz      short loc_180155533
0x18015552d  call    cs:__imp_CoUninitialize
0x180155533  mov     rbx, [rsp+28h+arg_0]
0x180155538  mov     rsi, [rsp+28h+arg_8]
0x18015553d  add     rsp, 20h
0x180155541  pop     rdi
0x180155542  retn
```
