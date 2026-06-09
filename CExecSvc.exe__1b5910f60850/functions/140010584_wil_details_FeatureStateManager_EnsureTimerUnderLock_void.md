# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140010584`
- end: `0x140010674`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011334`

## callees

- `0x140002310`
- `0x140010584`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400105b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400105e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400105b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400105e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010612`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001061e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010612`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001061e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400105ce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400105ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400105f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001064a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400105f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001064a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001060a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001060a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010601`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010601`

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
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
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
0x140010584  mov     [rsp+arg_8], rbx
0x140010589  mov     [rsp+arg_10], rbp
0x14001058e  push    rsi
0x14001058f  push    rdi
0x140010590  push    r14
0x140010592  sub     rsp, 30h
0x140010596  mov     rax, cs:__security_cookie
0x14001059d  xor     rax, rsp
0x1400105a0  mov     [rsp+48h+var_20], rax
0x1400105a5  cmp     byte ptr [rcx+41h], 0
0x1400105a9  mov     rdi, rcx
0x1400105ac  jnz     loc_140010654
0x1400105b2  cmp     qword ptr [rcx+30h], 0
0x1400105b7  jnz     short loc_140010624
0x1400105b9  call    cs:__imp_GetLastError
0x1400105bf  xor     r8d, r8d; pcbe
0x1400105c2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400105c9  mov     rdx, rdi; pv
0x1400105cc  mov     ebp, eax
0x1400105ce  call    cs:__imp_CreateThreadpoolTimer
0x1400105d4  mov     rsi, [rdi+30h]
0x1400105d8  mov     r14, rax
0x1400105db  test    rsi, rsi
0x1400105de  jz      short loc_140010618
0x1400105e0  call    cs:__imp_GetLastError
0x1400105e6  xor     r9d, r9d; msWindowLength
0x1400105e9  xor     r8d, r8d; msPeriod
0x1400105ec  xor     edx, edx; pftDueTime
0x1400105ee  mov     rcx, rsi; pti
0x1400105f1  mov     ebx, eax
0x1400105f3  call    cs:__imp_SetThreadpoolTimer
0x1400105f9  mov     edx, 1; fCancelPendingCallbacks
0x1400105fe  mov     rcx, rsi; pti
0x140010601  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140010607  mov     rcx, rsi; pti
0x14001060a  call    cs:__imp_CloseThreadpoolTimer
0x140010610  mov     ecx, ebx; dwErrCode
0x140010612  call    cs:__imp_SetLastError
0x140010618  mov     ecx, ebp; dwErrCode
0x14001061a  mov     [rdi+30h], r14
0x14001061e  call    cs:__imp_SetLastError
0x140010624  mov     rcx, [rdi+30h]; pti
0x140010628  test    rcx, rcx
0x14001062b  jz      short loc_140010654
0x14001062d  mov     rax, 0FFFFFFFF4D2FA200h
0x140010637  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x14001063c  mov     r9d, 124F8h; msWindowLength
0x140010642  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x140010647  xor     r8d, r8d; msPeriod
0x14001064a  call    cs:__imp_SetThreadpoolTimer
0x140010650  mov     byte ptr [rdi+41h], 1
0x140010654  mov     rcx, [rsp+48h+var_20]
0x140010659  xor     rcx, rsp; StackCookie
0x14001065c  call    __security_check_cookie
0x140010661  mov     rbx, [rsp+48h+arg_8]
0x140010666  mov     rbp, [rsp+48h+arg_10]
0x14001066b  add     rsp, 30h
0x14001066f  pop     r14
0x140010671  pop     rdi
0x140010672  pop     rsi
0x140010673  retn
```
