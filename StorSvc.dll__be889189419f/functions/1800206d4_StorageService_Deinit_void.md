# StorageService::Deinit(void)

- ea: `0x1800206d4`
- end: `0x1800209ce`
- name: `?Deinit@StorageService@@QEAAJXZ`
- size: `762`
- prototype: `__int64 __fastcall(StorageService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180037270`

## callees

- `0x1800030e0`
- `0x18000d400`
- `0x18001feb8`
- `0x1800206d4`
- `0x18002d02c`
- `0x180034edc`
- `0x18006db68`
- `0x18006f9dc`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800209a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800209a8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002083e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002084b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002083e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002084b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002085d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002088f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002085d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002088f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002077f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002077f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180020772`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180020772`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800206f9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002071a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800206f9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002071a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002070b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002070b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002096e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002096e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180020727`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180020727`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002095c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002095c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020798`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800207b1`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020798`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800207b1`
- `ntdll!RtlFreeHeap` at `0x1800208ed`
- `ntdll!RtlFreeHeap` at `0x180020912`
- `ntdll!RtlFreeHeap` at `0x1800208ed`
- `ntdll!RtlFreeHeap` at `0x180020912`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020740`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020740`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180020805`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18002081e`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180020805`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18002081e`

## pseudocode

```c
__int64 __fastcall StorageService::Deinit(StorageService *this)
{
  void *v1; // rbx

  HIDWORD(qword_1800C1140) = 1;
  if ( pwa )
  {
    WaitForThreadpoolWaitCallbacks(pwa, 1);
    SetThreadpoolWait(pwa, 0, 0);
    WaitForThreadpoolWaitCallbacks(pwa, 1);
    CloseThreadpoolWait(pwa);
    pwa = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( *(&hKey + 1) != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    CloseHandle(*(&hKey + 1));
    *(&hKey + 1) = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( pwk )
  {
    WaitForThreadpoolWorkCallbacks(pwk, 1);
    CloseThreadpoolWork(pwk);
    pwk = 0;
  }
  if ( (_QWORD)xmmword_1800C1150 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *(_QWORD *)&xmmword_1800C1150 = 0;
  }
  if ( *((_QWORD *)&xmmword_1800C1150 + 1) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)&xmmword_1800C1150 + 1) = 0;
  }
  StorageCleanup::Deinit((StorageCleanup *)qword_1800C0AD8);
  if ( HIDWORD(qword_1800C0ABC) && !(unsigned int)StorageService::CheckPresenceState(&g_StorageService, 1, 0, 2) )
    StorageCleanup::Deinit((StorageCleanup *)qword_1800C0DD0);
  if ( g_StorageService )
  {
    CM_Unregister_Notification();
    g_StorageService = 0;
  }
  if ( *(&g_StorageService + 1) )
  {
    CM_Unregister_Notification();
    *(&g_StorageService + 1) = 0;
  }
  McGenEventUnregister_EventUnregister(MDM_ENTERPRISE_DIAGNOSTICS_Context);
  DeleteCriticalSection(&stru_1800C10F8);
  DeleteCriticalSection(&stru_1800C10D0);
  if ( qword_1800C1188 )
  {
    CloseHandle(qword_1800C1188);
    qword_1800C1188 = 0;
  }
  if ( *(&hHandle + 1) )
  {
    CloseHandle(*(&hHandle + 1));
    *(&hHandle + 1) = 0;
  }
  if ( hHandle )
  {
    CloseHandle(hHandle);
    hHandle = 0;
  }
  if ( xmmword_1800C1130 )
  {
    CloseHandle(xmmword_1800C1130);
    xmmword_1800C1130 = 0;
  }
  if ( *(&xmmword_1800C1130 + 1) )
  {
    CloseHandle(*(&xmmword_1800C1130 + 1));
    *(&xmmword_1800C1130 + 1) = 0;
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( *(&P + 1) )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(&P + 1));
  if ( qword_1800C1218 )
  {
    DiskMonitor::StopMonitoringDisks(qword_1800C1218);
    if ( qword_1800C1218 )
      (**(void (__fastcall ***)(DiskMonitor *, __int64))qword_1800C1218)(qword_1800C1218, 1);
    McGenEventUnregister_EventUnregister(Microsoft_Windows_Storsvc_Context);
  }
  if ( pti )
  {
    WaitForThreadpoolTimerCallbacks(pti, 1);
    if ( pti )
    {
      CloseThreadpoolTimer(pti);
      pti = 0;
    }
  }
  v1 = *(&Block + 1);
  if ( *(&Block + 1) )
  {
    NVMeStorageHealthMonitor::~NVMeStorageHealthMonitor((NVMeStorageHealthMonitor *)*(&Block + 1));
    operator delete(v1, (const struct std::nothrow_t *)8);
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  TraceLoggingUnregister_EventUnregister(&dword_1800BF000);
  return 0;
}

```

## disassembly

```asm
0x1800206d4  mov     [rsp+arg_0], rbx
0x1800206d9  push    rdi
0x1800206da  sub     rsp, 20h
0x1800206de  mov     rcx, cs:pwa; pwa
0x1800206e5  xor     edi, edi
0x1800206e7  mov     ebx, 1
0x1800206ec  mov     dword ptr cs:qword_1800C1140+4, ebx
0x1800206f2  test    rcx, rcx
0x1800206f5  jz      short loc_180020734
0x1800206f7  mov     edx, ebx; fCancelPendingCallbacks
0x1800206f9  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800206ff  mov     rcx, cs:pwa; pwa
0x180020706  xor     r8d, r8d; pftTimeout
0x180020709  xor     edx, edx; h
0x18002070b  call    cs:__imp_SetThreadpoolWait
0x180020711  mov     rcx, cs:pwa; pwa
0x180020718  mov     edx, ebx; fCancelPendingCallbacks
0x18002071a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180020720  mov     rcx, cs:pwa; pwa
0x180020727  call    cs:__imp_CloseThreadpoolWait
0x18002072d  mov     cs:pwa, rdi
0x180020734  mov     rcx, qword ptr cs:hKey; hKey
0x18002073b  test    rcx, rcx
0x18002073e  jz      short loc_180020746
0x180020740  call    cs:__imp_RegCloseKey
0x180020746  mov     rcx, qword ptr cs:hKey+8; hObject
0x18002074d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180020751  jz      short loc_180020764
0x180020753  call    cs:__imp_CloseHandle
0x180020759  mov     qword ptr cs:hKey+8, 0FFFFFFFFFFFFFFFFh
0x180020764  mov     rcx, cs:pwk; pwk
0x18002076b  test    rcx, rcx
0x18002076e  jz      short loc_18002078C
0x180020770  mov     edx, ebx; fCancelPendingCallbacks
0x180020772  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180020778  mov     rcx, cs:pwk; pwk
0x18002077f  call    cs:__imp_CloseThreadpoolWork
0x180020785  mov     cs:pwk, rdi
0x18002078c  mov     rcx, qword ptr cs:xmmword_1800C1150
0x180020793  test    rcx, rcx
0x180020796  jz      short loc_1800207A5
0x180020798  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18002079e  mov     qword ptr cs:xmmword_1800C1150, rdi
0x1800207a5  mov     rcx, qword ptr cs:xmmword_1800C1150+8
0x1800207ac  test    rcx, rcx
0x1800207af  jz      short loc_1800207BE
0x1800207b1  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800207b7  mov     qword ptr cs:xmmword_1800C1150+8, rdi
0x1800207be  lea     rcx, qword_1800C0AD8; this
0x1800207c5  call    ?Deinit@StorageCleanup@@QEAAJXZ; StorageCleanup::Deinit(void)
0x1800207ca  cmp     dword ptr cs:qword_1800C0ABC+4, edi
0x1800207d0  jz      short loc_1800207F9
0x1800207d2  mov     r9d, 2
0x1800207d8  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x1800207df  xor     r8d, r8d
0x1800207e2  mov     edx, ebx
0x1800207e4  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x1800207e9  test    eax, eax
0x1800207eb  jnz     short loc_1800207F9
0x1800207ed  lea     rcx, qword_1800C0DD0; this
0x1800207f4  call    ?Deinit@StorageCleanup@@QEAAJXZ; StorageCleanup::Deinit(void)
0x1800207f9  mov     rcx, qword ptr cs:?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x180020800  test    rcx, rcx
0x180020803  jz      short loc_180020812
0x180020805  call    cs:__imp_CM_Unregister_Notification
0x18002080b  mov     qword ptr cs:?g_StorageService@@3VStorageService@@A, rdi; StorageService g_StorageService
0x180020812  mov     rcx, qword ptr cs:?g_StorageService@@3VStorageService@@A+8; StorageService g_StorageService
0x180020819  test    rcx, rcx
0x18002081c  jz      short loc_18002082B
0x18002081e  call    cs:__imp_CM_Unregister_Notification
0x180020824  mov     qword ptr cs:?g_StorageService@@3VStorageService@@A+8, rdi; StorageService g_StorageService
0x18002082b  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180020832  call    McGenEventUnregister_EventUnregister
0x180020837  lea     rcx, stru_1800C10F8; lpCriticalSection
0x18002083e  call    cs:__imp_DeleteCriticalSection
0x180020844  lea     rcx, stru_1800C10D0; lpCriticalSection
0x18002084b  call    cs:__imp_DeleteCriticalSection
0x180020851  mov     rcx, cs:qword_1800C1188; hObject
0x180020858  test    rcx, rcx
0x18002085b  jz      short loc_18002086A
0x18002085d  call    cs:__imp_CloseHandle
0x180020863  mov     cs:qword_1800C1188, rdi
0x18002086a  mov     rcx, qword ptr cs:hHandle+8; hObject
0x180020871  test    rcx, rcx
0x180020874  jz      short loc_180020883
0x180020876  call    cs:__imp_CloseHandle
0x18002087c  mov     qword ptr cs:hHandle+8, rdi
0x180020883  mov     rcx, qword ptr cs:hHandle; hObject
0x18002088a  test    rcx, rcx
0x18002088d  jz      short loc_18002089C
0x18002088f  call    cs:__imp_CloseHandle
0x180020895  mov     qword ptr cs:hHandle, rdi
0x18002089c  mov     rcx, qword ptr cs:xmmword_1800C1130; hObject
0x1800208a3  test    rcx, rcx
0x1800208a6  jz      short loc_1800208B5
0x1800208a8  call    cs:__imp_CloseHandle
0x1800208ae  mov     qword ptr cs:xmmword_1800C1130, rdi
0x1800208b5  mov     rcx, qword ptr cs:xmmword_1800C1130+8; hObject
0x1800208bc  test    rcx, rcx
0x1800208bf  jz      short loc_1800208CE
0x1800208c1  call    cs:__imp_CloseHandle
0x1800208c7  mov     qword ptr cs:xmmword_1800C1130+8, rdi
0x1800208ce  cmp     qword ptr cs:P, rdi
0x1800208d5  jz      short loc_1800208F3
0x1800208d7  mov     rcx, gs:60h
0x1800208e0  xor     edx, edx; Flags
0x1800208e2  mov     r8, qword ptr cs:P; P
0x1800208e9  mov     rcx, [rcx+30h]; HeapHandle
0x1800208ed  call    cs:__imp_RtlFreeHeap
0x1800208f3  cmp     qword ptr cs:P+8, rdi
0x1800208fa  jz      short loc_180020918
0x1800208fc  mov     rcx, gs:60h
0x180020905  xor     edx, edx; Flags
0x180020907  mov     r8, qword ptr cs:P+8; P
0x18002090e  mov     rcx, [rcx+30h]; HeapHandle
0x180020912  call    cs:__imp_RtlFreeHeap
0x180020918  mov     rcx, cs:qword_1800C1218; this
0x18002091f  test    rcx, rcx
0x180020922  jz      short loc_18002094E
0x180020924  call    ?StopMonitoringDisks@DiskMonitor@@QEAAXXZ; DiskMonitor::StopMonitoringDisks(void)
0x180020929  mov     rcx, cs:qword_1800C1218
0x180020930  test    rcx, rcx
0x180020933  jz      short loc_180020942
0x180020935  mov     rax, [rcx]
0x180020938  mov     edx, ebx
0x18002093a  mov     rax, [rax]
0x18002093d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020942  lea     rcx, Microsoft_Windows_Storsvc_Context
0x180020949  call    McGenEventUnregister_EventUnregister
0x18002094e  mov     rcx, cs:pti; pti
0x180020955  test    rcx, rcx
0x180020958  jz      short loc_18002097B
0x18002095a  mov     edx, ebx; fCancelPendingCallbacks
0x18002095c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020962  mov     rcx, cs:pti; pti
0x180020969  test    rcx, rcx
0x18002096c  jz      short loc_18002097B
0x18002096e  call    cs:__imp_CloseThreadpoolTimer
0x180020974  mov     cs:pti, rdi
0x18002097b  mov     rbx, qword ptr cs:Block+8
0x180020982  test    rbx, rbx
0x180020985  jz      short loc_18002099C
0x180020987  mov     rcx, rbx; this
0x18002098a  call    ??1NVMeStorageHealthMonitor@@QEAA@XZ; NVMeStorageHealthMonitor::~NVMeStorageHealthMonitor(void)
0x18002098f  mov     edx, 8; struct std::nothrow_t *
0x180020994  mov     rcx, rbx; void *
0x180020997  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002099c  mov     rcx, qword ptr cs:Block; Block
0x1800209a3  test    rcx, rcx
0x1800209a6  jz      short loc_1800209B5
0x1800209a8  call    cs:__imp_free
0x1800209ae  mov     qword ptr cs:Block, rdi
0x1800209b5  lea     rcx, dword_1800BF000
0x1800209bc  call    TraceLoggingUnregister_EventUnregister
0x1800209c1  mov     rbx, [rsp+28h+arg_0]
0x1800209c6  xor     eax, eax
0x1800209c8  add     rsp, 20h
0x1800209cc  pop     rdi
0x1800209cd  retn
```
