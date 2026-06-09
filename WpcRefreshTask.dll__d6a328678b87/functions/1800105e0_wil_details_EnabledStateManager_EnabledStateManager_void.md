# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800105e0`
- end: `0x180010738`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800abde0`

## callees

- `0x1800105e0`
- `0x180011bfc`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800106bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800106e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800106bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800106e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800106cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800106f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800106cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800106f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010633`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010601`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001062b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010721`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001062b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010721`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010622`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010718`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010622`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010718`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010614`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001070a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010614`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001070a`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
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
0x1800105e0  mov     [rsp+arg_0], rbx
0x1800105e5  mov     [rsp+arg_8], rsi
0x1800105ea  push    rdi
0x1800105eb  sub     rsp, 20h
0x1800105ef  mov     rdi, rcx
0x1800105f2  mov     dword ptr [rcx], 0
0x1800105f8  mov     rsi, [rcx+10h]
0x1800105fc  test    rsi, rsi
0x1800105ff  jz      short loc_180010639
0x180010601  call    cs:__imp_GetLastError
0x180010607  mov     ebx, eax
0x180010609  xor     r9d, r9d; msWindowLength
0x18001060c  xor     r8d, r8d; msPeriod
0x18001060f  xor     edx, edx; pftDueTime
0x180010611  mov     rcx, rsi; pti
0x180010614  call    cs:__imp_SetThreadpoolTimer
0x18001061a  mov     edx, 1; fCancelPendingCallbacks
0x18001061f  mov     rcx, rsi; pti
0x180010622  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010628  mov     rcx, rsi; pti
0x18001062b  call    cs:__imp_CloseThreadpoolTimer
0x180010631  mov     ecx, ebx; dwErrCode
0x180010633  call    cs:__imp_SetLastError
0x180010639  mov     qword ptr [rdi+10h], 0
0x180010641  mov     rcx, rdi; this
0x180010644  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180010649  mov     rcx, [rdi+68h]
0x18001064d  test    rcx, rcx
0x180010650  jz      short loc_180010682
0x180010652  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010659  test    rax, rax
0x18001065c  jnz     short loc_18001066D
0x18001065e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010665  test    rdx, rdx
0x180010668  jz      short loc_180010680
0x18001066a  mov     rax, rdx
0x18001066d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010672  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010679  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010680  jmp     short loc_180010690
0x180010682  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010689  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010690  mov     rcx, [rdi+60h]
0x180010694  test    rcx, rcx
0x180010697  jz      short loc_1800106AC
0x180010699  test    rax, rax
0x18001069c  jnz     short loc_1800106A6
0x18001069e  test    rdx, rdx
0x1800106a1  jz      short loc_1800106AC
0x1800106a3  mov     rax, rdx
0x1800106a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106ab  nop
0x1800106ac  mov     rbx, [rdi+58h]
0x1800106b0  mov     qword ptr [rdi+58h], 0
0x1800106b8  test    rbx, rbx
0x1800106bb  jz      short loc_1800106D1
0x1800106bd  call    cs:__imp_GetProcessHeap
0x1800106c3  mov     rcx, rax; hHeap
0x1800106c6  mov     r8, rbx; lpMem
0x1800106c9  xor     edx, edx; dwFlags
0x1800106cb  call    cs:__imp_HeapFree
0x1800106d1  mov     rbx, [rdi+38h]
0x1800106d5  mov     qword ptr [rdi+38h], 0
0x1800106dd  test    rbx, rbx
0x1800106e0  jz      short loc_1800106F6
0x1800106e2  call    cs:__imp_GetProcessHeap
0x1800106e8  mov     rcx, rax; hHeap
0x1800106eb  mov     r8, rbx; lpMem
0x1800106ee  xor     edx, edx; dwFlags
0x1800106f0  call    cs:__imp_HeapFree
0x1800106f6  mov     rbx, [rdi+10h]
0x1800106fa  test    rbx, rbx
0x1800106fd  jz      short loc_180010728
0x1800106ff  xor     r9d, r9d; msWindowLength
0x180010702  xor     r8d, r8d; msPeriod
0x180010705  xor     edx, edx; pftDueTime
0x180010707  mov     rcx, rbx; pti
0x18001070a  call    cs:__imp_SetThreadpoolTimer
0x180010710  mov     edx, 1; fCancelPendingCallbacks
0x180010715  mov     rcx, rbx; pti
0x180010718  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001071e  mov     rcx, rbx; pti
0x180010721  call    cs:__imp_CloseThreadpoolTimer
0x180010727  nop
0x180010728  mov     rbx, [rsp+28h+arg_0]
0x18001072d  mov     rsi, [rsp+28h+arg_8]
0x180010732  add     rsp, 20h
0x180010736  pop     rdi
0x180010737  retn
```
