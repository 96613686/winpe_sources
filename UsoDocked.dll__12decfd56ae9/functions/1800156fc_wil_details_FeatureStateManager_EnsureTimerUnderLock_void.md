# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800156fc`
- end: `0x1800157ec`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017374`

## callees

- `0x180007660`
- `0x1800156fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015758`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001578a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015796`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001578a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015796`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015746`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015746`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015779`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015779`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015782`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015782`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001576b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800157c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001576b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800157c2`

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
0x1800156fc  mov     [rsp+arg_8], rbx
0x180015701  mov     [rsp+arg_10], rbp
0x180015706  push    rsi
0x180015707  push    rdi
0x180015708  push    r14
0x18001570a  sub     rsp, 30h
0x18001570e  mov     rax, cs:__security_cookie
0x180015715  xor     rax, rsp
0x180015718  mov     [rsp+48h+var_20], rax
0x18001571d  cmp     byte ptr [rcx+41h], 0
0x180015721  mov     rdi, rcx
0x180015724  jnz     loc_1800157CC
0x18001572a  cmp     qword ptr [rcx+30h], 0
0x18001572f  jnz     short loc_18001579C
0x180015731  call    cs:__imp_GetLastError
0x180015737  xor     r8d, r8d; pcbe
0x18001573a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180015741  mov     rdx, rdi; pv
0x180015744  mov     ebp, eax
0x180015746  call    cs:__imp_CreateThreadpoolTimer
0x18001574c  mov     rsi, [rdi+30h]
0x180015750  mov     r14, rax
0x180015753  test    rsi, rsi
0x180015756  jz      short loc_180015790
0x180015758  call    cs:__imp_GetLastError
0x18001575e  xor     r9d, r9d; msWindowLength
0x180015761  xor     r8d, r8d; msPeriod
0x180015764  xor     edx, edx; pftDueTime
0x180015766  mov     rcx, rsi; pti
0x180015769  mov     ebx, eax
0x18001576b  call    cs:__imp_SetThreadpoolTimer
0x180015771  mov     edx, 1; fCancelPendingCallbacks
0x180015776  mov     rcx, rsi; pti
0x180015779  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001577f  mov     rcx, rsi; pti
0x180015782  call    cs:__imp_CloseThreadpoolTimer
0x180015788  mov     ecx, ebx; dwErrCode
0x18001578a  call    cs:__imp_SetLastError
0x180015790  mov     ecx, ebp; dwErrCode
0x180015792  mov     [rdi+30h], r14
0x180015796  call    cs:__imp_SetLastError
0x18001579c  mov     rcx, [rdi+30h]; pti
0x1800157a0  test    rcx, rcx
0x1800157a3  jz      short loc_1800157CC
0x1800157a5  mov     rax, 0FFFFFFFF4D2FA200h
0x1800157af  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800157b4  mov     r9d, 124F8h; msWindowLength
0x1800157ba  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800157bf  xor     r8d, r8d; msPeriod
0x1800157c2  call    cs:__imp_SetThreadpoolTimer
0x1800157c8  mov     byte ptr [rdi+41h], 1
0x1800157cc  mov     rcx, [rsp+48h+var_20]
0x1800157d1  xor     rcx, rsp; StackCookie
0x1800157d4  call    __security_check_cookie
0x1800157d9  mov     rbx, [rsp+48h+arg_8]
0x1800157de  mov     rbp, [rsp+48h+arg_10]
0x1800157e3  add     rsp, 30h
0x1800157e7  pop     r14
0x1800157e9  pop     rdi
0x1800157ea  pop     rsi
0x1800157eb  retn
```
