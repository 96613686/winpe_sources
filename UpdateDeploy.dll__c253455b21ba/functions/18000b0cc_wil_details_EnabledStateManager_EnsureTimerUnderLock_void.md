# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000b0cc`
- end: `0x18000b1bc`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b218`

## callees

- `0x18000b0cc`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b15a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b166`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b15a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b128`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b116`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b116`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b152`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b152`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b13b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b192`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b13b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b192`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b149`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b149`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 24) )
  {
    if ( !pv[2] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[2];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[2] = v5;
      SetLastError(LastError);
    }
    v7 = pv[2];
    if ( v7 )
    {
      pftDueTime = (_FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 24) = 1;
    }
  }
}

```

## disassembly

```asm
0x18000b0cc  mov     [rsp+arg_8], rbx
0x18000b0d1  mov     [rsp+arg_10], rbp
0x18000b0d6  push    rsi
0x18000b0d7  push    rdi
0x18000b0d8  push    r14
0x18000b0da  sub     rsp, 30h
0x18000b0de  mov     rax, cs:__security_cookie
0x18000b0e5  xor     rax, rsp
0x18000b0e8  mov     [rsp+48h+var_20], rax
0x18000b0ed  cmp     byte ptr [rcx+18h], 0
0x18000b0f1  mov     rdi, rcx
0x18000b0f4  jnz     loc_18000B19C
0x18000b0fa  cmp     qword ptr [rcx+10h], 0
0x18000b0ff  jnz     short loc_18000B16C
0x18000b101  call    cs:__imp_GetLastError
0x18000b107  xor     r8d, r8d; pcbe
0x18000b10a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b111  mov     rdx, rdi; pv
0x18000b114  mov     ebp, eax
0x18000b116  call    cs:__imp_CreateThreadpoolTimer
0x18000b11c  mov     rsi, [rdi+10h]
0x18000b120  mov     r14, rax
0x18000b123  test    rsi, rsi
0x18000b126  jz      short loc_18000B160
0x18000b128  call    cs:__imp_GetLastError
0x18000b12e  xor     r9d, r9d; msWindowLength
0x18000b131  xor     r8d, r8d; msPeriod
0x18000b134  xor     edx, edx; pftDueTime
0x18000b136  mov     rcx, rsi; pti
0x18000b139  mov     ebx, eax
0x18000b13b  call    cs:__imp_SetThreadpoolTimer
0x18000b141  mov     edx, 1; fCancelPendingCallbacks
0x18000b146  mov     rcx, rsi; pti
0x18000b149  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b14f  mov     rcx, rsi; pti
0x18000b152  call    cs:__imp_CloseThreadpoolTimer
0x18000b158  mov     ecx, ebx; dwErrCode
0x18000b15a  call    cs:__imp_SetLastError
0x18000b160  mov     ecx, ebp; dwErrCode
0x18000b162  mov     [rdi+10h], r14
0x18000b166  call    cs:__imp_SetLastError
0x18000b16c  mov     rcx, [rdi+10h]; pti
0x18000b170  test    rcx, rcx
0x18000b173  jz      short loc_18000B19C
0x18000b175  mov     rax, 0FFFFFFFF4D2FA200h
0x18000b17f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000b184  mov     r9d, 124F8h; msWindowLength
0x18000b18a  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18000b18f  xor     r8d, r8d; msPeriod
0x18000b192  call    cs:__imp_SetThreadpoolTimer
0x18000b198  mov     byte ptr [rdi+18h], 1
0x18000b19c  mov     rcx, [rsp+48h+var_20]
0x18000b1a1  xor     rcx, rsp; StackCookie
0x18000b1a4  call    __security_check_cookie
0x18000b1a9  mov     rbx, [rsp+48h+arg_8]
0x18000b1ae  mov     rbp, [rsp+48h+arg_10]
0x18000b1b3  add     rsp, 30h
0x18000b1b7  pop     r14
0x18000b1b9  pop     rdi
0x18000b1ba  pop     rsi
0x18000b1bb  retn
```
