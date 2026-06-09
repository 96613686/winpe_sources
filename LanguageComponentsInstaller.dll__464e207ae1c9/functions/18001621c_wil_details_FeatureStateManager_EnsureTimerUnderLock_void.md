# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18001621c`
- end: `0x18001630c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180019d68`

## callees

- `0x180003520`
- `0x18001621c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016278`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800162a2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800162a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016266`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016266`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001628b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800162e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001628b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800162e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016299`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016299`

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
0x18001621c  mov     [rsp+arg_8], rbx
0x180016221  mov     [rsp+arg_10], rbp
0x180016226  push    rsi
0x180016227  push    rdi
0x180016228  push    r14
0x18001622a  sub     rsp, 30h
0x18001622e  mov     rax, cs:__security_cookie
0x180016235  xor     rax, rsp
0x180016238  mov     [rsp+48h+var_20], rax
0x18001623d  cmp     byte ptr [rcx+41h], 0
0x180016241  mov     rdi, rcx
0x180016244  jnz     loc_1800162EC
0x18001624a  cmp     qword ptr [rcx+30h], 0
0x18001624f  jnz     short loc_1800162BC
0x180016251  call    cs:__imp_GetLastError
0x180016257  xor     r8d, r8d; pcbe
0x18001625a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180016261  mov     rdx, rdi; pv
0x180016264  mov     ebp, eax
0x180016266  call    cs:__imp_CreateThreadpoolTimer
0x18001626c  mov     rsi, [rdi+30h]
0x180016270  mov     r14, rax
0x180016273  test    rsi, rsi
0x180016276  jz      short loc_1800162B0
0x180016278  call    cs:__imp_GetLastError
0x18001627e  xor     r9d, r9d; msWindowLength
0x180016281  xor     r8d, r8d; msPeriod
0x180016284  xor     edx, edx; pftDueTime
0x180016286  mov     rcx, rsi; pti
0x180016289  mov     ebx, eax
0x18001628b  call    cs:__imp_SetThreadpoolTimer
0x180016291  mov     edx, 1; fCancelPendingCallbacks
0x180016296  mov     rcx, rsi; pti
0x180016299  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001629f  mov     rcx, rsi; pti
0x1800162a2  call    cs:__imp_CloseThreadpoolTimer
0x1800162a8  mov     ecx, ebx; dwErrCode
0x1800162aa  call    cs:__imp_SetLastError
0x1800162b0  mov     ecx, ebp; dwErrCode
0x1800162b2  mov     [rdi+30h], r14
0x1800162b6  call    cs:__imp_SetLastError
0x1800162bc  mov     rcx, [rdi+30h]; pti
0x1800162c0  test    rcx, rcx
0x1800162c3  jz      short loc_1800162EC
0x1800162c5  mov     rax, 0FFFFFFFF4D2FA200h
0x1800162cf  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800162d4  mov     r9d, 124F8h; msWindowLength
0x1800162da  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800162df  xor     r8d, r8d; msPeriod
0x1800162e2  call    cs:__imp_SetThreadpoolTimer
0x1800162e8  mov     byte ptr [rdi+41h], 1
0x1800162ec  mov     rcx, [rsp+48h+var_20]
0x1800162f1  xor     rcx, rsp; StackCookie
0x1800162f4  call    __security_check_cookie
0x1800162f9  mov     rbx, [rsp+48h+arg_8]
0x1800162fe  mov     rbp, [rsp+48h+arg_10]
0x180016303  add     rsp, 30h
0x180016307  pop     r14
0x180016309  pop     rdi
0x18001630a  pop     rsi
0x18001630b  retn
```
