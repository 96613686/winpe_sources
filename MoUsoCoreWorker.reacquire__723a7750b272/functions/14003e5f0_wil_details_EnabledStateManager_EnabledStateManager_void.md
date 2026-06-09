# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x14003e5f0`
- end: `0x14003e748`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1403b1e90`

## callees

- `0x14003dd60`
- `0x14003e5f0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003e640`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003e640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e60e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e60e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e66a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e68f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e66a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e68f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e678`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e69d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e678`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e69d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14003e638`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14003e731`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14003e638`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14003e731`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14003e62f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14003e728`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14003e62f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14003e728`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14003e621`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14003e71a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14003e621`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14003e71a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax
  void (*v8)(void); // rax
  __int64 v9; // rdx
  struct _TP_TIMER *v10; // rbx

  *(_BYTE *)this = 0;
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
  *(_BYTE *)this = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  v4 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_14;
  }
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_14;
    v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v8();
  v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_14:
  if ( !*((_QWORD *)this + 4) )
    goto LABEL_19;
  if ( !v8 )
  {
    if ( !v9 )
      goto LABEL_19;
    v8 = (void (*)(void))v9;
  }
  v8();
LABEL_19:
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
0x14003e5f0  mov     [rsp+arg_0], rbx
0x14003e5f5  mov     [rsp+arg_8], rsi
0x14003e5fa  push    rdi
0x14003e5fb  sub     rsp, 20h
0x14003e5ff  mov     rdi, rcx
0x14003e602  mov     byte ptr [rcx], 0
0x14003e605  mov     rsi, [rcx+10h]
0x14003e609  test    rsi, rsi
0x14003e60c  jz      short loc_14003E646
0x14003e60e  call    cs:__imp_GetLastError
0x14003e614  mov     ebx, eax
0x14003e616  xor     r9d, r9d; msWindowLength
0x14003e619  xor     r8d, r8d; msPeriod
0x14003e61c  xor     edx, edx; pftDueTime
0x14003e61e  mov     rcx, rsi; pti
0x14003e621  call    cs:__imp_SetThreadpoolTimer
0x14003e627  mov     edx, 1; fCancelPendingCallbacks
0x14003e62c  mov     rcx, rsi; pti
0x14003e62f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14003e635  mov     rcx, rsi; pti
0x14003e638  call    cs:__imp_CloseThreadpoolTimer
0x14003e63e  mov     ecx, ebx; dwErrCode
0x14003e640  call    cs:__imp_SetLastError
0x14003e646  mov     qword ptr [rdi+10h], 0
0x14003e64e  mov     byte ptr [rdi], 0
0x14003e651  mov     rcx, rdi; this
0x14003e654  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x14003e659  mov     rbx, [rdi+68h]
0x14003e65d  mov     qword ptr [rdi+68h], 0
0x14003e665  test    rbx, rbx
0x14003e668  jz      short loc_14003E67E
0x14003e66a  call    cs:__imp_GetProcessHeap
0x14003e670  mov     rcx, rax; hHeap
0x14003e673  mov     r8, rbx; lpMem
0x14003e676  xor     edx, edx; dwFlags
0x14003e678  call    cs:__imp_HeapFree
0x14003e67e  mov     rbx, [rdi+48h]
0x14003e682  mov     qword ptr [rdi+48h], 0
0x14003e68a  test    rbx, rbx
0x14003e68d  jz      short loc_14003E6A3
0x14003e68f  call    cs:__imp_GetProcessHeap
0x14003e695  mov     rcx, rax; hHeap
0x14003e698  mov     r8, rbx; lpMem
0x14003e69b  xor     edx, edx; dwFlags
0x14003e69d  call    cs:__imp_HeapFree
0x14003e6a3  mov     rcx, [rdi+28h]
0x14003e6a7  test    rcx, rcx
0x14003e6aa  jz      short loc_14003E6DC
0x14003e6ac  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14003e6b3  test    rax, rax
0x14003e6b6  jnz     short loc_14003E6C7
0x14003e6b8  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14003e6bf  test    rdx, rdx
0x14003e6c2  jz      short loc_14003E6DA
0x14003e6c4  mov     rax, rdx
0x14003e6c7  call    _guard_dispatch_icall
0x14003e6cc  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14003e6d3  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14003e6da  jmp     short loc_14003E6EA
0x14003e6dc  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14003e6e3  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14003e6ea  mov     rcx, [rdi+20h]
0x14003e6ee  test    rcx, rcx
0x14003e6f1  jz      short loc_14003E706
0x14003e6f3  test    rax, rax
0x14003e6f6  jnz     short loc_14003E700
0x14003e6f8  test    rdx, rdx
0x14003e6fb  jz      short loc_14003E706
0x14003e6fd  mov     rax, rdx
0x14003e700  call    _guard_dispatch_icall
0x14003e705  nop
0x14003e706  mov     rbx, [rdi+10h]
0x14003e70a  test    rbx, rbx
0x14003e70d  jz      short loc_14003E738
0x14003e70f  xor     r9d, r9d; msWindowLength
0x14003e712  xor     r8d, r8d; msPeriod
0x14003e715  xor     edx, edx; pftDueTime
0x14003e717  mov     rcx, rbx; pti
0x14003e71a  call    cs:__imp_SetThreadpoolTimer
0x14003e720  mov     edx, 1; fCancelPendingCallbacks
0x14003e725  mov     rcx, rbx; pti
0x14003e728  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14003e72e  mov     rcx, rbx; pti
0x14003e731  call    cs:__imp_CloseThreadpoolTimer
0x14003e737  nop
0x14003e738  mov     rbx, [rsp+28h+arg_0]
0x14003e73d  mov     rsi, [rsp+28h+arg_8]
0x14003e742  add     rsp, 20h
0x14003e746  pop     rdi
0x14003e747  retn
```
