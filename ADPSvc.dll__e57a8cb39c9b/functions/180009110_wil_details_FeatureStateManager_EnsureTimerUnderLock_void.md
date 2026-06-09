# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180009110`
- end: `0x1800091e4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009cd4`

## callees

- `0x180009110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000918f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000919b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000918f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000919b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000915d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000915d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009170`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800091c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009170`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800091c7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000914b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000914b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000917e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000917e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009187`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009187`

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
0x180009110  mov     [rsp+arg_8], rbx
0x180009115  mov     [rsp+arg_10], rbp
0x18000911a  push    rsi
0x18000911b  push    rdi
0x18000911c  push    r14
0x18000911e  sub     rsp, 20h
0x180009122  cmp     byte ptr [rcx+41h], 0
0x180009126  mov     rdi, rcx
0x180009129  jnz     loc_1800091D1
0x18000912f  cmp     qword ptr [rcx+30h], 0
0x180009134  jnz     short loc_1800091A1
0x180009136  call    cs:__imp_GetLastError
0x18000913c  xor     r8d, r8d; pcbe
0x18000913f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009146  mov     rdx, rdi; pv
0x180009149  mov     ebp, eax
0x18000914b  call    cs:__imp_CreateThreadpoolTimer
0x180009151  mov     rsi, [rdi+30h]
0x180009155  mov     r14, rax
0x180009158  test    rsi, rsi
0x18000915b  jz      short loc_180009195
0x18000915d  call    cs:__imp_GetLastError
0x180009163  xor     r9d, r9d; msWindowLength
0x180009166  xor     r8d, r8d; msPeriod
0x180009169  xor     edx, edx; pftDueTime
0x18000916b  mov     rcx, rsi; pti
0x18000916e  mov     ebx, eax
0x180009170  call    cs:__imp_SetThreadpoolTimer
0x180009176  mov     edx, 1; fCancelPendingCallbacks
0x18000917b  mov     rcx, rsi; pti
0x18000917e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009184  mov     rcx, rsi; pti
0x180009187  call    cs:__imp_CloseThreadpoolTimer
0x18000918d  mov     ecx, ebx; dwErrCode
0x18000918f  call    cs:__imp_SetLastError
0x180009195  mov     ecx, ebp; dwErrCode
0x180009197  mov     [rdi+30h], r14
0x18000919b  call    cs:__imp_SetLastError
0x1800091a1  mov     rcx, [rdi+30h]; pti
0x1800091a5  test    rcx, rcx
0x1800091a8  jz      short loc_1800091D1
0x1800091aa  mov     rax, 0FFFFFFFF4D2FA200h
0x1800091b4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800091b9  mov     r9d, 124F8h; msWindowLength
0x1800091bf  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800091c4  xor     r8d, r8d; msPeriod
0x1800091c7  call    cs:__imp_SetThreadpoolTimer
0x1800091cd  mov     byte ptr [rdi+41h], 1
0x1800091d1  mov     rbx, [rsp+38h+arg_8]
0x1800091d6  mov     rbp, [rsp+38h+arg_10]
0x1800091db  add     rsp, 20h
0x1800091df  pop     r14
0x1800091e1  pop     rdi
0x1800091e2  pop     rsi
0x1800091e3  retn
```
