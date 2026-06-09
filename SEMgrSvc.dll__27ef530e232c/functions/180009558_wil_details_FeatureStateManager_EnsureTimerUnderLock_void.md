# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180009558`
- end: `0x18000962c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b724`

## callees

- `0x180009558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000957e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000957e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009593`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009593`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000960f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000960f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095cf`

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
                          `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x180009558  mov     [rsp+arg_8], rbx
0x18000955d  mov     [rsp+arg_10], rbp
0x180009562  push    rsi
0x180009563  push    rdi
0x180009564  push    r14
0x180009566  sub     rsp, 20h
0x18000956a  cmp     byte ptr [rcx+41h], 0
0x18000956e  mov     rdi, rcx
0x180009571  jnz     loc_180009619
0x180009577  cmp     qword ptr [rcx+30h], 0
0x18000957c  jnz     short loc_1800095E9
0x18000957e  call    cs:__imp_GetLastError
0x180009584  xor     r8d, r8d; pcbe
0x180009587  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000958e  mov     rdx, rdi; pv
0x180009591  mov     ebp, eax
0x180009593  call    cs:__imp_CreateThreadpoolTimer
0x180009599  mov     rsi, [rdi+30h]
0x18000959d  mov     r14, rax
0x1800095a0  test    rsi, rsi
0x1800095a3  jz      short loc_1800095DD
0x1800095a5  call    cs:__imp_GetLastError
0x1800095ab  xor     r9d, r9d; msWindowLength
0x1800095ae  xor     r8d, r8d; msPeriod
0x1800095b1  xor     edx, edx; pftDueTime
0x1800095b3  mov     rcx, rsi; pti
0x1800095b6  mov     ebx, eax
0x1800095b8  call    cs:__imp_SetThreadpoolTimer
0x1800095be  mov     edx, 1; fCancelPendingCallbacks
0x1800095c3  mov     rcx, rsi; pti
0x1800095c6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800095cc  mov     rcx, rsi; pti
0x1800095cf  call    cs:__imp_CloseThreadpoolTimer
0x1800095d5  mov     ecx, ebx; dwErrCode
0x1800095d7  call    cs:__imp_SetLastError
0x1800095dd  mov     ecx, ebp; dwErrCode
0x1800095df  mov     [rdi+30h], r14
0x1800095e3  call    cs:__imp_SetLastError
0x1800095e9  mov     rcx, [rdi+30h]; pti
0x1800095ed  test    rcx, rcx
0x1800095f0  jz      short loc_180009619
0x1800095f2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800095fc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180009601  mov     r9d, 124F8h; msWindowLength
0x180009607  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000960c  xor     r8d, r8d; msPeriod
0x18000960f  call    cs:__imp_SetThreadpoolTimer
0x180009615  mov     byte ptr [rdi+41h], 1
0x180009619  mov     rbx, [rsp+38h+arg_8]
0x18000961e  mov     rbp, [rsp+38h+arg_10]
0x180009623  add     rsp, 20h
0x180009627  pop     r14
0x180009629  pop     rdi
0x18000962a  pop     rsi
0x18000962b  retn
```
