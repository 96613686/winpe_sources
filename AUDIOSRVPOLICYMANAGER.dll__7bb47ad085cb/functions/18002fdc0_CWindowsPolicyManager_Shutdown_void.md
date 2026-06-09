# CWindowsPolicyManager::Shutdown(void)

- ea: `0x18002fdc0`
- end: `0x180030012`
- name: `?Shutdown@CWindowsPolicyManager@@UEAAXXZ`
- size: `594`
- prototype: `void __fastcall(CWindowsPolicyManager *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f4e0`
- `0x18001d070`
- `0x18002fdc0`
- `0x180030018`
- `0x1800403e0`
- `0x1800438d4`
- `0x180044df0`
- `0x18004c010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18002fe9f`
- `msvcp_win!_Mtx_unlock` at `0x18002fe9f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002fe6e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002fe8a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002fe6e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002fe8a`
- `msvcp_win!_Mtx_lock` at `0x18002fe5f`
- `msvcp_win!_Mtx_lock` at `0x18002fe5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fde3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002feb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fde3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002feb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fdfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fec5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ff87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fdfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fec5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ff87`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ff00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ff00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ffc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ffc4`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18002fef1`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18002fef1`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18002fe1e`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18002fe1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWindowsPolicyManager::Shutdown(struct _RTL_CRITICAL_SECTION **this)
{
  struct CDuckingManager *v2; // rsi
  CApplicationManager *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  HANDLE v5; // rcx
  __int64 v6; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp+10h] BYREF
  LPCRITICAL_SECTION v10; // [rsp+40h] [rbp+18h] BYREF

  CWindowsPolicyManager::Lock(this, &lpCriticalSection);
  EnterCriticalSection(&stru_180064458);
  std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<TSSession>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<TSSession>>>,0>>::clear(&dword_180064480);
  LeaveCriticalSection(&stru_180064458);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( g_hLowPowerEpochNotificationHandle )
  {
    PowerSettingUnregisterNotification(g_hLowPowerEpochNotificationHandle);
    g_hLowPowerEpochNotificationHandle = 0;
  }
  g_bLowPowerEpoch = 0;
  g_bApmSuspended = 0;
  g_AppTypesBlockedTillConsoleUnlocked = 0;
  v2 = g_DuckingManager;
  *((_BYTE *)g_DuckingManager + 456) = 1;
  if ( _Mtx_lock((struct CDuckingManager *)((char *)v2 + 328)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v2 + 101) == 0x7FFFFFFF )
  {
    *((_DWORD *)v2 + 101) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  *((_BYTE *)v2 + 320) = 1;
  _Mtx_unlock((struct CDuckingManager *)((char *)v2 + 328));
  v3 = g_ApplicationManager;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)g_ApplicationManager + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_ApplicationManager + 32));
  *((_BYTE *)v3 + 24) = 1;
  if ( v4 )
    LeaveCriticalSection(v4);
  v5 = g_EventWorkerThreadHandle;
  if ( g_EventWorkerThreadHandle )
  {
    if ( g_WorkerEventPort )
    {
      PostQueuedCompletionStatus(g_WorkerEventPort, 0xFFFFFFFF, 0, 0);
      v5 = g_EventWorkerThreadHandle;
    }
    WaitForSingleObject(v5, 0xFFFFFFFF);
    if ( (char *)g_EventWorkerThreadHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(g_EventWorkerThreadHandle);
      g_EventWorkerThreadHandle = 0;
    }
  }
  v6 = g_StreamClassPolicyManager;
  g_StreamClassPolicyManager = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = this[4];
  this[4] = 0;
  if ( v7 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISessionInternalEvents>::Release();
  CWindowsPolicyManager::Lock(v7, &v10);
  v8 = this[5];
  this[5] = 0;
  lpCriticalSection = v8;
  if ( v10 )
    LeaveCriticalSection(v10);
  wil::com_ptr_t<CDuckingManager,wil::err_returncode_policy>::reset(&lpCriticalSection);
  if ( g_ApplicationManager )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(g_ApplicationManager);
    g_ApplicationManager = 0;
  }
  if ( (char *)g_WorkerEventPort - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_WorkerEventPort);
    g_WorkerEventPort = 0;
  }
  if ( g_DeviceEnumerator )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_DeviceEnumerator + 16LL))(g_DeviceEnumerator);
    g_DeviceEnumerator = 0;
  }
  wil::com_ptr_t<CDuckingManager,wil::err_returncode_policy>::~com_ptr_t<CDuckingManager,wil::err_returncode_policy>(&lpCriticalSection);
}

```

## disassembly

```asm
0x18002fdc0  mov     [rsp+arg_0], rbx
0x18002fdc5  mov     [rsp+arg_18], rsi
0x18002fdca  push    rdi
0x18002fdcb  sub     rsp, 20h
0x18002fdcf  mov     rdi, rcx
0x18002fdd2  lea     rdx, [rsp+28h+lpCriticalSection]
0x18002fdd7  call    ?Lock@CWindowsPolicyManager@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; CWindowsPolicyManager::Lock(void)
0x18002fddc  lea     rcx, stru_180064458; lpCriticalSection
0x18002fde3  call    cs:__imp_EnterCriticalSection
0x18002fde9  lea     rcx, dword_180064480
0x18002fdf0  call    ?clear@?$_Hash@V?$_Umap_traits@KV?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VTSSession@@U?$default_delete@VTSSession@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<ulong,std::unique_ptr<TSSession>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::unique_ptr<TSSession>>>,0>>::clear(void)
0x18002fdf5  lea     rcx, stru_180064458; lpCriticalSection
0x18002fdfc  call    cs:__imp_LeaveCriticalSection
0x18002fe02  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x18002fe07  test    rcx, rcx
0x18002fe0a  jz      short loc_18002FE12
0x18002fe0c  call    cs:__imp_LeaveCriticalSection
0x18002fe12  mov     rcx, cs:?g_hLowPowerEpochNotificationHandle@@3PEAXEA; RegistrationHandle
0x18002fe19  test    rcx, rcx
0x18002fe1c  jz      short loc_18002FE2F
0x18002fe1e  call    cs:__imp_PowerSettingUnregisterNotification
0x18002fe24  mov     cs:?g_hLowPowerEpochNotificationHandle@@3PEAXEA, 0; void * g_hLowPowerEpochNotificationHandle
0x18002fe2f  mov     cs:?g_bLowPowerEpoch@@3_NA, 0; bool g_bLowPowerEpoch
0x18002fe36  mov     cs:?g_bApmSuspended@@3_NA, 0; bool g_bApmSuspended
0x18002fe3d  mov     cs:?g_AppTypesBlockedTillConsoleUnlocked@@3W4AppTypesBlockedTillConsoleUnlocked@@A, 0; AppTypesBlockedTillConsoleUnlocked g_AppTypesBlockedTillConsoleUnlocked
0x18002fe47  mov     rsi, cs:?g_DuckingManager@@3PEAVCDuckingManager@@EA; CDuckingManager * g_DuckingManager
0x18002fe4e  mov     byte ptr [rsi+1C8h], 1
0x18002fe55  lea     rbx, [rsi+148h]
0x18002fe5c  mov     rcx, rbx; _Mtx_t
0x18002fe5f  call    cs:__imp__Mtx_lock
0x18002fe65  test    eax, eax
0x18002fe67  jz      short loc_18002FE75
0x18002fe69  mov     ecx, 5
0x18002fe6e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002fe74  int     3; Trap to Debugger
0x18002fe75  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18002fe7c  jnz     short loc_18002FE91
0x18002fe7e  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18002fe85  mov     ecx, 6
0x18002fe8a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002fe90  int     3; Trap to Debugger
0x18002fe91  mov     eax, 1
0x18002fe96  xchg    al, [rsi+140h]
0x18002fe9c  mov     rcx, rbx; _Mtx_t
0x18002fe9f  call    cs:__imp__Mtx_unlock
0x18002fea5  mov     rbx, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x18002feac  lea     rsi, [rbx+20h]
0x18002feb0  mov     rcx, rsi; lpCriticalSection
0x18002feb3  call    cs:__imp_EnterCriticalSection
0x18002feb9  mov     byte ptr [rbx+18h], 1
0x18002febd  test    rsi, rsi
0x18002fec0  jz      short loc_18002FECB
0x18002fec2  mov     rcx, rsi; lpCriticalSection
0x18002fec5  call    cs:__imp_LeaveCriticalSection
0x18002fecb  mov     rcx, cs:?g_EventWorkerThreadHandle@@3PEAXEA; void * g_EventWorkerThreadHandle
0x18002fed2  test    rcx, rcx
0x18002fed5  jz      short loc_18002FF28
0x18002fed7  or      ebx, 0FFFFFFFFh
0x18002feda  mov     rax, cs:?g_WorkerEventPort@@3PEAXEA; void * g_WorkerEventPort
0x18002fee1  test    rax, rax
0x18002fee4  jz      short loc_18002FEFE
0x18002fee6  xor     r9d, r9d; lpOverlapped
0x18002fee9  xor     r8d, r8d; dwCompletionKey
0x18002feec  mov     edx, ebx; dwNumberOfBytesTransferred
0x18002feee  mov     rcx, rax; CompletionPort
0x18002fef1  call    cs:__imp_PostQueuedCompletionStatus
0x18002fef7  mov     rcx, cs:?g_EventWorkerThreadHandle@@3PEAXEA; hHandle
0x18002fefe  mov     edx, ebx; dwMilliseconds
0x18002ff00  call    cs:__imp_WaitForSingleObject
0x18002ff06  mov     rcx, cs:?g_EventWorkerThreadHandle@@3PEAXEA; hObject
0x18002ff0d  lea     rax, [rcx-1]
0x18002ff11  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ff15  ja      short loc_18002FF28
0x18002ff17  call    cs:__imp_CloseHandle
0x18002ff1d  mov     cs:?g_EventWorkerThreadHandle@@3PEAXEA, 0; void * g_EventWorkerThreadHandle
0x18002ff28  mov     rcx, cs:?g_StreamClassPolicyManager@@3V?$com_ptr_t@VCStreamClassPolicyManager@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<CStreamClassPolicyManager,wil::err_returncode_policy> g_StreamClassPolicyManager
0x18002ff2f  mov     cs:?g_StreamClassPolicyManager@@3V?$com_ptr_t@VCStreamClassPolicyManager@@Uerr_returncode_policy@wil@@@wil@@A, 0; wil::com_ptr_t<CStreamClassPolicyManager,wil::err_returncode_policy> g_StreamClassPolicyManager
0x18002ff3a  test    rcx, rcx
0x18002ff3d  jz      short loc_18002FF4C
0x18002ff3f  mov     rax, [rcx]
0x18002ff42  mov     rax, [rax+10h]
0x18002ff46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff4b  nop
0x18002ff4c  mov     rcx, [rdi+20h]
0x18002ff50  mov     qword ptr [rdi+20h], 0
0x18002ff58  test    rcx, rcx
0x18002ff5b  jz      short loc_18002FF62
0x18002ff5d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISessionInternalEvents@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISessionInternalEvents>::Release(void)
0x18002ff62  lea     rdx, [rsp+28h+arg_10]
0x18002ff67  call    ?Lock@CWindowsPolicyManager@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; CWindowsPolicyManager::Lock(void)
0x18002ff6c  mov     rax, [rdi+28h]
0x18002ff70  mov     qword ptr [rdi+28h], 0
0x18002ff78  mov     [rsp+28h+lpCriticalSection], rax
0x18002ff7d  mov     rcx, [rsp+28h+arg_10]; lpCriticalSection
0x18002ff82  test    rcx, rcx
0x18002ff85  jz      short loc_18002FF8D
0x18002ff87  call    cs:__imp_LeaveCriticalSection
0x18002ff8d  lea     rcx, [rsp+28h+lpCriticalSection]
0x18002ff92  call    ?reset@?$com_ptr_t@VCDuckingManager@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CDuckingManager,wil::err_returncode_policy>::reset(void)
0x18002ff97  mov     rcx, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x18002ff9e  test    rcx, rcx
0x18002ffa1  jz      short loc_18002FFB3
0x18002ffa3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18002ffa8  mov     cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA, 0; CApplicationManager * g_ApplicationManager
0x18002ffb3  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; hObject
0x18002ffba  lea     rax, [rcx-1]
0x18002ffbe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ffc2  ja      short loc_18002FFD5
0x18002ffc4  call    cs:__imp_CloseHandle
0x18002ffca  mov     cs:?g_WorkerEventPort@@3PEAXEA, 0; void * g_WorkerEventPort
0x18002ffd5  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002ffdc  test    rcx, rcx
0x18002ffdf  jz      short loc_18002FFF8
0x18002ffe1  mov     rax, [rcx]
0x18002ffe4  mov     rax, [rax+10h]
0x18002ffe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffed  mov     cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA, 0; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002fff8  lea     rcx, [rsp+28h+lpCriticalSection]
0x18002fffd  call    ??1?$com_ptr_t@VCDuckingManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDuckingManager,wil::err_returncode_policy>::~com_ptr_t<CDuckingManager,wil::err_returncode_policy>(void)
0x180030002  mov     rbx, [rsp+28h+arg_0]
0x180030007  mov     rsi, [rsp+28h+arg_18]
0x18003000c  add     rsp, 20h
0x180030010  pop     rdi
0x180030011  retn
```
