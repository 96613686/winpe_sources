# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x140003670`
- end: `0x140003760`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003a48`

## callees

- `0x140003670`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400036fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000370a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400036fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000370a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036cc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400036f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400036f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400036ed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400036ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400036df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003736`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400036df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003736`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400036ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400036ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
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
0x140003670  mov     [rsp+arg_8], rbx
0x140003675  mov     [rsp+arg_10], rbp
0x14000367a  push    rsi
0x14000367b  push    rdi
0x14000367c  push    r14
0x14000367e  sub     rsp, 30h
0x140003682  mov     rax, cs:__security_cookie
0x140003689  xor     rax, rsp
0x14000368c  mov     [rsp+48h+var_20], rax
0x140003691  cmp     byte ptr [rcx+18h], 0
0x140003695  mov     rdi, rcx
0x140003698  jnz     loc_140003740
0x14000369e  cmp     qword ptr [rcx+10h], 0
0x1400036a3  jnz     short loc_140003710
0x1400036a5  call    cs:__imp_GetLastError
0x1400036ab  xor     r8d, r8d; pcbe
0x1400036ae  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400036b5  mov     rdx, rdi; pv
0x1400036b8  mov     ebp, eax
0x1400036ba  call    cs:__imp_CreateThreadpoolTimer
0x1400036c0  mov     rsi, [rdi+10h]
0x1400036c4  mov     r14, rax
0x1400036c7  test    rsi, rsi
0x1400036ca  jz      short loc_140003704
0x1400036cc  call    cs:__imp_GetLastError
0x1400036d2  xor     r9d, r9d; msWindowLength
0x1400036d5  xor     r8d, r8d; msPeriod
0x1400036d8  xor     edx, edx; pftDueTime
0x1400036da  mov     rcx, rsi; pti
0x1400036dd  mov     ebx, eax
0x1400036df  call    cs:__imp_SetThreadpoolTimer
0x1400036e5  mov     edx, 1; fCancelPendingCallbacks
0x1400036ea  mov     rcx, rsi; pti
0x1400036ed  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400036f3  mov     rcx, rsi; pti
0x1400036f6  call    cs:__imp_CloseThreadpoolTimer
0x1400036fc  mov     ecx, ebx; dwErrCode
0x1400036fe  call    cs:__imp_SetLastError
0x140003704  mov     ecx, ebp; dwErrCode
0x140003706  mov     [rdi+10h], r14
0x14000370a  call    cs:__imp_SetLastError
0x140003710  mov     rcx, [rdi+10h]; pti
0x140003714  test    rcx, rcx
0x140003717  jz      short loc_140003740
0x140003719  mov     rax, 0FFFFFFFF4D2FA200h
0x140003723  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x140003728  mov     r9d, 124F8h; msWindowLength
0x14000372e  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x140003733  xor     r8d, r8d; msPeriod
0x140003736  call    cs:__imp_SetThreadpoolTimer
0x14000373c  mov     byte ptr [rdi+18h], 1
0x140003740  mov     rcx, [rsp+48h+var_20]
0x140003745  xor     rcx, rsp; StackCookie
0x140003748  call    __security_check_cookie
0x14000374d  mov     rbx, [rsp+48h+arg_8]
0x140003752  mov     rbp, [rsp+48h+arg_10]
0x140003757  add     rsp, 30h
0x14000375b  pop     r14
0x14000375d  pop     rdi
0x14000375e  pop     rsi
0x14000375f  retn
```
