# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18001ca54`
- end: `0x18001cbac`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180031e80`

## callees

- `0x18001ca54`
- `0x18002032c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cb3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cb64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cb3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cb64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cb31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cb56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cb31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cb56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001caa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001caa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001ca9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001cb95`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001ca9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001cb95`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ca96`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001cb8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ca96`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001cb8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ca88`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001cb7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ca88`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001cb7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void (*v4)(void); // rax
  __int64 v5; // rdx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  struct _TP_TIMER *v10; // rbx

  *(_DWORD *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = 0;
  wil::details::EnabledStateManager::ProcessShutdown(this);
  if ( !*((_QWORD *)this + 13) )
  {
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_10;
  }
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_10;
    v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v4();
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_10:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_15;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_15;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_15:
  v6 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
}

```

## disassembly

```asm
0x18001ca54  mov     [rsp+arg_0], rbx
0x18001ca59  mov     [rsp+arg_8], rsi
0x18001ca5e  push    rdi
0x18001ca5f  sub     rsp, 20h
0x18001ca63  mov     rdi, rcx
0x18001ca66  mov     dword ptr [rcx], 0
0x18001ca6c  mov     rsi, [rcx+10h]
0x18001ca70  test    rsi, rsi
0x18001ca73  jz      short loc_18001CAAD
0x18001ca75  call    cs:__imp_GetLastError
0x18001ca7b  mov     ebx, eax
0x18001ca7d  xor     r9d, r9d; msWindowLength
0x18001ca80  xor     r8d, r8d; msPeriod
0x18001ca83  xor     edx, edx; pftDueTime
0x18001ca85  mov     rcx, rsi; pti
0x18001ca88  call    cs:__imp_SetThreadpoolTimer
0x18001ca8e  mov     edx, 1; fCancelPendingCallbacks
0x18001ca93  mov     rcx, rsi; pti
0x18001ca96  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ca9c  mov     rcx, rsi; pti
0x18001ca9f  call    cs:__imp_CloseThreadpoolTimer
0x18001caa5  mov     ecx, ebx; dwErrCode
0x18001caa7  call    cs:__imp_SetLastError
0x18001caad  mov     qword ptr [rdi+10h], 0
0x18001cab5  mov     rcx, rdi; this
0x18001cab8  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18001cabd  mov     rcx, [rdi+68h]
0x18001cac1  test    rcx, rcx
0x18001cac4  jz      short loc_18001CAF6
0x18001cac6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001cacd  test    rax, rax
0x18001cad0  jnz     short loc_18001CAE1
0x18001cad2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001cad9  test    rdx, rdx
0x18001cadc  jz      short loc_18001CAF4
0x18001cade  mov     rax, rdx
0x18001cae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cae6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001caed  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001caf4  jmp     short loc_18001CB04
0x18001caf6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001cafd  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001cb04  mov     rcx, [rdi+60h]
0x18001cb08  test    rcx, rcx
0x18001cb0b  jz      short loc_18001CB20
0x18001cb0d  test    rax, rax
0x18001cb10  jnz     short loc_18001CB1A
0x18001cb12  test    rdx, rdx
0x18001cb15  jz      short loc_18001CB20
0x18001cb17  mov     rax, rdx
0x18001cb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb1f  nop
0x18001cb20  mov     rbx, [rdi+58h]
0x18001cb24  mov     qword ptr [rdi+58h], 0
0x18001cb2c  test    rbx, rbx
0x18001cb2f  jz      short loc_18001CB45
0x18001cb31  call    cs:__imp_GetProcessHeap
0x18001cb37  mov     rcx, rax; hHeap
0x18001cb3a  mov     r8, rbx; lpMem
0x18001cb3d  xor     edx, edx; dwFlags
0x18001cb3f  call    cs:__imp_HeapFree
0x18001cb45  mov     rbx, [rdi+38h]
0x18001cb49  mov     qword ptr [rdi+38h], 0
0x18001cb51  test    rbx, rbx
0x18001cb54  jz      short loc_18001CB6A
0x18001cb56  call    cs:__imp_GetProcessHeap
0x18001cb5c  mov     rcx, rax; hHeap
0x18001cb5f  mov     r8, rbx; lpMem
0x18001cb62  xor     edx, edx; dwFlags
0x18001cb64  call    cs:__imp_HeapFree
0x18001cb6a  mov     rbx, [rdi+10h]
0x18001cb6e  test    rbx, rbx
0x18001cb71  jz      short loc_18001CB9C
0x18001cb73  xor     r9d, r9d; msWindowLength
0x18001cb76  xor     r8d, r8d; msPeriod
0x18001cb79  xor     edx, edx; pftDueTime
0x18001cb7b  mov     rcx, rbx; pti
0x18001cb7e  call    cs:__imp_SetThreadpoolTimer
0x18001cb84  mov     edx, 1; fCancelPendingCallbacks
0x18001cb89  mov     rcx, rbx; pti
0x18001cb8c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001cb92  mov     rcx, rbx; pti
0x18001cb95  call    cs:__imp_CloseThreadpoolTimer
0x18001cb9b  nop
0x18001cb9c  mov     rbx, [rsp+28h+arg_0]
0x18001cba1  mov     rsi, [rsp+28h+arg_8]
0x18001cba6  add     rsp, 20h
0x18001cbaa  pop     rdi
0x18001cbab  retn
```
