# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000670c`
- end: `0x180006904`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `504`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1801c1e50`

## callees

- `0x1800064a4`
- `0x18000670c`
- `0x18000af8c`
- `0x18000c5fc`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x18000675e`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800067a7`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800068ad`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800068de`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000675e`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800067a7`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800068ad`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800068de`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006755`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000679e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800068a4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800068d5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006755`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000679e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800068a4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800068d5`
- `KERNEL32!SetThreadpoolTimer` at `0x180006747`
- `KERNEL32!SetThreadpoolTimer` at `0x180006790`
- `KERNEL32!SetThreadpoolTimer` at `0x180006896`
- `KERNEL32!SetThreadpoolTimer` at `0x1800068c7`
- `KERNEL32!SetThreadpoolTimer` at `0x180006747`
- `KERNEL32!SetThreadpoolTimer` at `0x180006790`
- `KERNEL32!SetThreadpoolTimer` at `0x180006896`
- `KERNEL32!SetThreadpoolTimer` at `0x1800068c7`
- `KERNEL32!GetProcessHeap` at `0x1800067d4`
- `KERNEL32!GetProcessHeap` at `0x180006824`
- `KERNEL32!GetProcessHeap` at `0x180006864`
- `KERNEL32!GetProcessHeap` at `0x1800067d4`
- `KERNEL32!GetProcessHeap` at `0x180006824`
- `KERNEL32!GetProcessHeap` at `0x180006864`
- `KERNEL32!HeapFree` at `0x1800067e2`
- `KERNEL32!HeapFree` at `0x180006832`
- `KERNEL32!HeapFree` at `0x180006872`
- `KERNEL32!HeapFree` at `0x1800067e2`
- `KERNEL32!HeapFree` at `0x180006832`
- `KERNEL32!HeapFree` at `0x180006872`
- `KERNEL32!DeleteCriticalSection` at `0x18000683b`
- `KERNEL32!DeleteCriticalSection` at `0x18000687c`
- `KERNEL32!DeleteCriticalSection` at `0x18000683b`
- `KERNEL32!DeleteCriticalSection` at `0x18000687c`
- `KERNEL32!SetLastError` at `0x180006766`
- `KERNEL32!SetLastError` at `0x1800067af`
- `KERNEL32!SetLastError` at `0x180006766`
- `KERNEL32!SetLastError` at `0x1800067af`
- `KERNEL32!GetLastError` at `0x180006734`
- `KERNEL32!GetLastError` at `0x18000677d`
- `KERNEL32!GetLastError` at `0x180006734`
- `KERNEL32!GetLastError` at `0x18000677d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rsi
  DWORD v5; // ebx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // r8
  void *v9; // rsi
  HANDLE v10; // rax
  void *v11; // rsi
  HANDLE v12; // rax
  struct _TP_TIMER *v13; // rbx
  struct _TP_TIMER *v14; // rbx
  void *v15; // rcx

  *(_BYTE *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(v5);
  }
  *((_QWORD *)this + 7) = 0;
  v6 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v8 && qword_18028C7F8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18028C7F8[25], qword_18028C7F8, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
  v11 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (void *)*((_QWORD *)this + 2);
  if ( v15 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x18000670c  push    rdi
0x18000670e  sub     rsp, 30h
0x180006712  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000671b  mov     [rsp+38h+arg_0], rbx
0x180006720  mov     [rsp+38h+arg_8], rsi
0x180006725  mov     rdi, rcx
0x180006728  mov     byte ptr [rcx], 0
0x18000672b  mov     rsi, [rcx+30h]
0x18000672f  test    rsi, rsi
0x180006732  jz      short loc_18000676C
0x180006734  call    cs:__imp_GetLastError
0x18000673a  mov     ebx, eax
0x18000673c  xor     r9d, r9d; msWindowLength
0x18000673f  xor     r8d, r8d; msPeriod
0x180006742  xor     edx, edx; pftDueTime
0x180006744  mov     rcx, rsi; pti
0x180006747  call    cs:__imp_SetThreadpoolTimer
0x18000674d  mov     edx, 1; fCancelPendingCallbacks
0x180006752  mov     rcx, rsi; pti
0x180006755  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000675b  mov     rcx, rsi; pti
0x18000675e  call    cs:__imp_CloseThreadpoolTimer
0x180006764  mov     ecx, ebx; dwErrCode
0x180006766  call    cs:__imp_SetLastError
0x18000676c  mov     qword ptr [rdi+30h], 0
0x180006774  mov     rsi, [rdi+38h]
0x180006778  test    rsi, rsi
0x18000677b  jz      short loc_1800067B5
0x18000677d  call    cs:__imp_GetLastError
0x180006783  mov     ebx, eax
0x180006785  xor     r9d, r9d; msWindowLength
0x180006788  xor     r8d, r8d; msPeriod
0x18000678b  xor     edx, edx; pftDueTime
0x18000678d  mov     rcx, rsi; pti
0x180006790  call    cs:__imp_SetThreadpoolTimer
0x180006796  mov     edx, 1; fCancelPendingCallbacks
0x18000679b  mov     rcx, rsi; pti
0x18000679e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800067a4  mov     rcx, rsi; pti
0x1800067a7  call    cs:__imp_CloseThreadpoolTimer
0x1800067ad  mov     ecx, ebx; dwErrCode
0x1800067af  call    cs:__imp_SetLastError
0x1800067b5  mov     qword ptr [rdi+38h], 0
0x1800067bd  mov     rbx, [rdi+100h]
0x1800067c4  mov     qword ptr [rdi+100h], 0
0x1800067cf  test    rbx, rbx
0x1800067d2  jz      short loc_1800067E8
0x1800067d4  call    cs:__imp_GetProcessHeap
0x1800067da  mov     rcx, rax; hHeap
0x1800067dd  mov     r8, rbx; lpMem
0x1800067e0  xor     edx, edx; dwFlags
0x1800067e2  call    cs:__imp_HeapFree
0x1800067e8  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800067ef  test    r8, r8
0x1800067f2  jz      short loc_18000680C
0x1800067f4  mov     rdx, cs:qword_18028C7F8; SRWLock
0x1800067fb  test    rdx, rdx
0x1800067fe  jz      short loc_18000680C
0x180006800  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180006807  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000680c  lea     rbx, [rdi+98h]
0x180006813  mov     rsi, [rbx+40h]
0x180006817  mov     qword ptr [rbx+40h], 0
0x18000681f  test    rsi, rsi
0x180006822  jz      short loc_180006838
0x180006824  call    cs:__imp_GetProcessHeap
0x18000682a  mov     rcx, rax; hHeap
0x18000682d  mov     r8, rsi; lpMem
0x180006830  xor     edx, edx; dwFlags
0x180006832  call    cs:__imp_HeapFree
0x180006838  mov     rcx, rbx; lpCriticalSection
0x18000683b  call    cs:__imp_DeleteCriticalSection
0x180006841  lea     rcx, [rdi+90h]
0x180006848  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000684d  mov     rsi, [rdi+88h]
0x180006854  mov     qword ptr [rdi+88h], 0
0x18000685f  test    rsi, rsi
0x180006862  jz      short loc_180006878
0x180006864  call    cs:__imp_GetProcessHeap
0x18000686a  mov     rcx, rax; hHeap
0x18000686d  mov     r8, rsi; lpMem
0x180006870  xor     edx, edx; dwFlags
0x180006872  call    cs:__imp_HeapFree
0x180006878  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000687c  call    cs:__imp_DeleteCriticalSection
0x180006882  mov     rbx, [rdi+38h]
0x180006886  test    rbx, rbx
0x180006889  jz      short loc_1800068B3
0x18000688b  xor     r9d, r9d; msWindowLength
0x18000688e  xor     r8d, r8d; msPeriod
0x180006891  xor     edx, edx; pftDueTime
0x180006893  mov     rcx, rbx; pti
0x180006896  call    cs:__imp_SetThreadpoolTimer
0x18000689c  mov     edx, 1; fCancelPendingCallbacks
0x1800068a1  mov     rcx, rbx; pti
0x1800068a4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800068aa  mov     rcx, rbx; pti
0x1800068ad  call    cs:__imp_CloseThreadpoolTimer
0x1800068b3  mov     rbx, [rdi+30h]
0x1800068b7  test    rbx, rbx
0x1800068ba  jz      short loc_1800068E5
0x1800068bc  xor     r9d, r9d; msWindowLength
0x1800068bf  xor     r8d, r8d; msPeriod
0x1800068c2  xor     edx, edx; pftDueTime
0x1800068c4  mov     rcx, rbx; pti
0x1800068c7  call    cs:__imp_SetThreadpoolTimer
0x1800068cd  mov     edx, 1; fCancelPendingCallbacks
0x1800068d2  mov     rcx, rbx; pti
0x1800068d5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800068db  mov     rcx, rbx; pti
0x1800068de  call    cs:__imp_CloseThreadpoolTimer
0x1800068e4  nop
0x1800068e5  mov     rcx, [rdi+10h]; lpMem
0x1800068e9  test    rcx, rcx
0x1800068ec  jz      short loc_1800068F4
0x1800068ee  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800068f3  nop
0x1800068f4  mov     rbx, [rsp+38h+arg_0]
0x1800068f9  mov     rsi, [rsp+38h+arg_8]
0x1800068fe  add     rsp, 30h
0x180006902  pop     rdi
0x180006903  retn
```
