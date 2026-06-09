# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800043a0`
- end: `0x18000450c`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `364`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180020940`

## callees

- `0x1800043a0`
- `0x18000ac00`
- `0x18000cfe4`
- `0x18000dd50`
- `0x18000e400`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000448e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000448e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004461`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800044d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004461`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800044d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000440e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000440e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000441c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000441c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043df`

## string_xrefs

- `0x180004487`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  _TP_TIMER *m_ptr; // rsi
  DWORD LastError; // edi
  _TP_TIMER *v4; // rsi
  DWORD v5; // edi
  void *value; // rdi
  HANDLE ProcessHeap; // rax
  FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // rcx
  void *v9; // rsi
  HANDLE v10; // rax
  void *v11; // rdi
  FARPROC ProcAddress; // rax
  HMODULE NtDllModuleHandle; // rax
  void *v14; // rsi
  HANDLE v15; // rax
  _TP_TIMER *v16; // rcx
  _TP_TIMER *v17; // rcx
  wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> *m_data; // rcx

  this->m_fInitialized = 0;
  m_ptr = this->m_timer.m_ptr;
  if ( m_ptr )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(m_ptr);
    SetLastError(LastError);
  }
  this->m_timer.m_ptr = 0;
  v4 = this->m_SRUMtimer.m_ptr;
  if ( v4 )
  {
    v5 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    SetLastError(v5);
  }
  this->m_SRUMtimer.m_ptr = 0;
  value = this->m_cachedSRUMUsageTrackingData.m_data.allocation.__ptr_.__value_;
  this->m_cachedSRUMUsageTrackingData.m_data.allocation.__ptr_.__value_ = 0;
  if ( value )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, value);
  }
  v8 = this->m_processWideUsageFlushSubscription.m_ptr;
  if ( v8 )
    wil::details::UnsubscribeProcessWideUsageFlush(v8);
  v9 = this->m_usageFlushSubscriptions.m_subscriptions.m_data.allocation.__ptr_.__value_;
  this->m_usageFlushSubscriptions.m_subscriptions.m_data.allocation.__ptr_.__value_ = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection(&this->m_usageFlushSubscriptions.m_unsubscribeLock.m_cs);
  v11 = this->m_featureConfigurationChangeSubscription.m_ptr;
  if ( v11 )
  {
    ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllModuleHandle = wil_details_GetNtDllModuleHandle(),
          ProcAddress = GetProcAddress(NtDllModuleHandle, "RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (void (__fastcall *)(void *))ProcAddress) != 0) )
    {
      ((void (__fastcall *)(void *))ProcAddress)(v11);
    }
  }
  v14 = this->m_stateChangeSubscriptions.m_subscriptions.m_data.allocation.__ptr_.__value_;
  this->m_stateChangeSubscriptions.m_subscriptions.m_data.allocation.__ptr_.__value_ = 0;
  if ( v14 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
  }
  DeleteCriticalSection(&this->m_stateChangeSubscriptions.m_unsubscribeLock.m_cs);
  v16 = this->m_SRUMtimer.m_ptr;
  if ( v16 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v16);
  v17 = this->m_timer.m_ptr;
  if ( v17 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v17);
  m_data = this->m_dataStorage.m_data;
  if ( m_data )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(m_data);
}

```

## disassembly

```asm
0x1800043a0  push    rbx
0x1800043a2  push    rbp
0x1800043a3  push    rsi
0x1800043a4  push    rdi
0x1800043a5  sub     rsp, 28h
0x1800043a9  mov     byte ptr [this], 0
0x1800043ac  mov     rbx, this
0x1800043af  mov     rsi, [this+30h]
0x1800043b3  test    rsi, rsi
0x1800043b6  jz      short loc_1800043D0
0x1800043b8  call    cs:__imp_GetLastError
0x1800043be  mov     this, rsi; threadpoolTimer
0x1800043c1  mov     edi, eax
0x1800043c3  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800043c8  mov     ecx, edi; dwErrCode
0x1800043ca  call    cs:__imp_SetLastError
0x1800043d0  xor     ebp, ebp
0x1800043d2  mov     [rbx+30h], rbp
0x1800043d6  mov     rsi, [rbx+38h]
0x1800043da  test    rsi, rsi
0x1800043dd  jz      short loc_1800043F7
0x1800043df  call    cs:__imp_GetLastError
0x1800043e5  mov     this, rsi; threadpoolTimer
0x1800043e8  mov     edi, eax
0x1800043ea  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800043ef  mov     ecx, edi; dwErrCode
0x1800043f1  call    cs:__imp_SetLastError
0x1800043f7  mov     [rbx+38h], rbp
0x1800043fb  mov     rdi, [rbx+100h]
0x180004402  mov     [rbx+100h], rbp
0x180004409  test    rdi, rdi
0x18000440c  jz      short loc_180004422
0x18000440e  call    cs:__imp_GetProcessHeap
0x180004414  mov     r8, rdi; lpMem
0x180004417  xor     edx, edx; dwFlags
0x180004419  mov     this, rax; hHeap
0x18000441c  call    cs:__imp_HeapFree
0x180004422  mov     this, [rbx+0E0h]; subscription
0x180004429  test    this, this
0x18000442c  jz      short loc_180004433
0x18000442e  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180004433  mov     rsi, [rbx+0D8h]
0x18000443a  mov     [rbx+0D8h], rbp
0x180004441  test    rsi, rsi
0x180004444  jz      short loc_18000445A
0x180004446  call    cs:__imp_GetProcessHeap
0x18000444c  mov     r8, rsi; lpMem
0x18000444f  xor     edx, edx; dwFlags
0x180004451  mov     this, rax; hHeap
0x180004454  call    cs:__imp_HeapFree
0x18000445a  lea     this, [rbx+98h]; lpCriticalSection
0x180004461  call    cs:__imp_DeleteCriticalSection
0x180004467  mov     rdi, [rbx+90h]
0x18000446e  test    rdi, rdi
0x180004471  jz      short loc_1800044A8
0x180004473  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000447a  test    rax, rax
0x18000447d  jnz     short loc_1800044A0
0x18000447f  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180004484  mov     this, rax; hModule
0x180004487  lea     rdx, ProcName; "RtlUnregisterFeatureConfigurationChange"...
0x18000448e  call    cs:__imp_GetProcAddress
0x180004494  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000449b  test    rax, rax
0x18000449e  jz      short loc_1800044A8
0x1800044a0  mov     this, rdi
0x1800044a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a8  mov     rsi, [rbx+88h]
0x1800044af  mov     [rbx+88h], rbp
0x1800044b6  test    rsi, rsi
0x1800044b9  jz      short loc_1800044CF
0x1800044bb  call    cs:__imp_GetProcessHeap
0x1800044c1  mov     r8, rsi; lpMem
0x1800044c4  xor     edx, edx; dwFlags
0x1800044c6  mov     this, rax; hHeap
0x1800044c9  call    cs:__imp_HeapFree
0x1800044cf  lea     this, [rbx+48h]; lpCriticalSection
0x1800044d3  call    cs:__imp_DeleteCriticalSection
0x1800044d9  mov     this, [rbx+38h]; threadpoolTimer
0x1800044dd  test    this, this
0x1800044e0  jz      short loc_1800044E7
0x1800044e2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800044e7  mov     this, [rbx+30h]; threadpoolTimer
0x1800044eb  test    this, this
0x1800044ee  jz      short loc_1800044F5
0x1800044f0  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800044f5  mov     this, [rbx+10h]; this
0x1800044f9  test    this, this
0x1800044fc  jz      short loc_180004503
0x1800044fe  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180004503  add     rsp, 28h
0x180004507  pop     rdi
0x180004508  pop     rsi
0x180004509  pop     rbp
0x18000450a  pop     rbx
0x18000450b  retn
```
