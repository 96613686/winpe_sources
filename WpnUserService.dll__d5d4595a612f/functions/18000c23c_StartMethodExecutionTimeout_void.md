# StartMethodExecutionTimeout(void)

- ea: `0x18000c23c`
- end: `0x18000c301`
- name: `?StartMethodExecutionTimeout@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `197`
- prototype: `struct _TP_TIMER **__fastcall(struct _TP_TIMER **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cad4`

## callees

- `0x18000c23c`
- `0x18000ce88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c2bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c2bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c289`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c266`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c2b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c2b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c29c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c2e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c29c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c2e5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c278`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c278`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c2aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c2aa`

## pseudocode

```c
struct _TP_TIMER **__fastcall StartMethodExecutionTimeout(struct _TP_TIMER **a1)
{
  DWORD CurrentThreadId; // eax
  void *v3; // rdx
  struct _TP_TIMER *ThreadpoolTimer; // rsi
  unsigned int v5; // r8d
  const char *v6; // r9
  struct _TP_TIMER *v7; // rbp
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+10h] BYREF

  *a1 = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadpoolTimer = CreateThreadpoolTimer(
                      (PTP_TIMER_CALLBACK)_lambda_f099cc1d2f1f8f886aed5df943340db4_::_lambda_invoker_cdecl_,
                      (PVOID)CurrentThreadId,
                      0);
  v7 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v7, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v7, 1);
    CloseThreadpoolTimer(v7);
    SetLastError(LastError);
  }
  *a1 = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v3, v5, v6);
  pftDueTime = (struct _FILETIME)-600000000LL;
  SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
  return a1;
}

```

## disassembly

```asm
0x18000c23c  mov     rax, rsp
0x18000c23f  mov     [rax+18h], rbx
0x18000c243  mov     [rax+8], rcx
0x18000c247  push    rbp
0x18000c248  push    rsi
0x18000c249  push    rdi
0x18000c24a  sub     rsp, 30h
0x18000c24e  mov     rdi, rcx
0x18000c251  mov     dword ptr [rax-28h], 0
0x18000c258  mov     qword ptr [rcx], 0
0x18000c25f  mov     dword ptr [rax-28h], 1
0x18000c266  call    cs:__imp_GetCurrentThreadId
0x18000c26c  mov     edx, eax; pv
0x18000c26e  xor     r8d, r8d; pcbe
0x18000c271  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_f099cc1d2f1f8f886aed5df943340db4_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c278  call    cs:__imp_CreateThreadpoolTimer
0x18000c27e  mov     rsi, rax
0x18000c281  mov     rbp, [rdi]
0x18000c284  test    rbp, rbp
0x18000c287  jz      short loc_18000C2C1
0x18000c289  call    cs:__imp_GetLastError
0x18000c28f  mov     ebx, eax
0x18000c291  xor     r9d, r9d; msWindowLength
0x18000c294  xor     r8d, r8d; msPeriod
0x18000c297  xor     edx, edx; pftDueTime
0x18000c299  mov     rcx, rbp; pti
0x18000c29c  call    cs:__imp_SetThreadpoolTimer
0x18000c2a2  mov     edx, 1; fCancelPendingCallbacks
0x18000c2a7  mov     rcx, rbp; pti
0x18000c2aa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c2b0  mov     rcx, rbp; pti
0x18000c2b3  call    cs:__imp_CloseThreadpoolTimer
0x18000c2b9  mov     ecx, ebx; dwErrCode
0x18000c2bb  call    cs:__imp_SetLastError
0x18000c2c1  mov     [rdi], rsi
0x18000c2c4  mov     rcx, [rsp+48h]; this
0x18000c2c9  test    rsi, rsi
0x18000c2cc  jz      short loc_18000C2FB
0x18000c2ce  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFDC3CBA00h
0x18000c2d7  xor     r9d, r9d; msWindowLength
0x18000c2da  xor     r8d, r8d; msPeriod
0x18000c2dd  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000c2e2  mov     rcx, rsi; pti
0x18000c2e5  call    cs:__imp_SetThreadpoolTimer
0x18000c2eb  mov     rax, rdi
0x18000c2ee  mov     rbx, [rsp+48h+arg_10]
0x18000c2f3  add     rsp, 30h
0x18000c2f7  pop     rdi
0x18000c2f8  pop     rsi
0x18000c2f9  pop     rbp
0x18000c2fa  retn
0x18000c2fb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
