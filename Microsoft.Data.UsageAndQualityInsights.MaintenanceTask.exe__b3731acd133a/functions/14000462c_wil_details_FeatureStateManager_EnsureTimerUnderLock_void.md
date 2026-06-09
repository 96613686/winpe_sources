# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14000462c`
- end: `0x140004700`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140006404`

## callees

- `0x14000462c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004679`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400046ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400046b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400046ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400046b7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140004667`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140004667`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400046a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400046a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000468c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400046e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000468c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400046e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000469a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000469a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
      v4 = pv[6];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[6] = v5;
      SetLastError(LastError);
    }
    v7 = pv[6];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x14000462c  mov     [rsp+arg_8], rbx
0x140004631  mov     [rsp+arg_10], rbp
0x140004636  push    rsi
0x140004637  push    rdi
0x140004638  push    r14
0x14000463a  sub     rsp, 20h
0x14000463e  cmp     byte ptr [rcx+41h], 0
0x140004642  mov     rdi, rcx
0x140004645  jnz     loc_1400046ED
0x14000464b  cmp     qword ptr [rcx+30h], 0
0x140004650  jnz     short loc_1400046BD
0x140004652  call    cs:__imp_GetLastError
0x140004658  xor     r8d, r8d; pcbe
0x14000465b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140004662  mov     rdx, rdi; pv
0x140004665  mov     ebp, eax
0x140004667  call    cs:__imp_CreateThreadpoolTimer
0x14000466d  mov     rsi, [rdi+30h]
0x140004671  mov     r14, rax
0x140004674  test    rsi, rsi
0x140004677  jz      short loc_1400046B1
0x140004679  call    cs:__imp_GetLastError
0x14000467f  xor     r9d, r9d; msWindowLength
0x140004682  xor     r8d, r8d; msPeriod
0x140004685  xor     edx, edx; pftDueTime
0x140004687  mov     rcx, rsi; pti
0x14000468a  mov     ebx, eax
0x14000468c  call    cs:__imp_SetThreadpoolTimer
0x140004692  mov     edx, 1; fCancelPendingCallbacks
0x140004697  mov     rcx, rsi; pti
0x14000469a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400046a0  mov     rcx, rsi; pti
0x1400046a3  call    cs:__imp_CloseThreadpoolTimer
0x1400046a9  mov     ecx, ebx; dwErrCode
0x1400046ab  call    cs:__imp_SetLastError
0x1400046b1  mov     ecx, ebp; dwErrCode
0x1400046b3  mov     [rdi+30h], r14
0x1400046b7  call    cs:__imp_SetLastError
0x1400046bd  mov     rcx, [rdi+30h]; pti
0x1400046c1  test    rcx, rcx
0x1400046c4  jz      short loc_1400046ED
0x1400046c6  mov     rax, 0FFFFFFFF4D2FA200h
0x1400046d0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1400046d5  mov     r9d, 124F8h; msWindowLength
0x1400046db  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1400046e0  xor     r8d, r8d; msPeriod
0x1400046e3  call    cs:__imp_SetThreadpoolTimer
0x1400046e9  mov     byte ptr [rdi+41h], 1
0x1400046ed  mov     rbx, [rsp+38h+arg_8]
0x1400046f2  mov     rbp, [rsp+38h+arg_10]
0x1400046f7  add     rsp, 20h
0x1400046fb  pop     r14
0x1400046fd  pop     rdi
0x1400046fe  pop     rsi
0x1400046ff  retn
```
