# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800127d0`
- end: `0x1800128a4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016a18`

## callees

- `0x1800127d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001281d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001281d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001284f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001285b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001284f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001285b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001280b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001280b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012847`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012847`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012830`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012887`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012830`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012887`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001283e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001283e`

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
0x1800127d0  mov     [rsp+arg_8], rbx
0x1800127d5  mov     [rsp+arg_10], rbp
0x1800127da  push    rsi
0x1800127db  push    rdi
0x1800127dc  push    r14
0x1800127de  sub     rsp, 20h
0x1800127e2  cmp     byte ptr [rcx+41h], 0
0x1800127e6  mov     rdi, rcx
0x1800127e9  jnz     loc_180012891
0x1800127ef  cmp     qword ptr [rcx+30h], 0
0x1800127f4  jnz     short loc_180012861
0x1800127f6  call    cs:__imp_GetLastError
0x1800127fc  xor     r8d, r8d; pcbe
0x1800127ff  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180012806  mov     rdx, rdi; pv
0x180012809  mov     ebp, eax
0x18001280b  call    cs:__imp_CreateThreadpoolTimer
0x180012811  mov     rsi, [rdi+30h]
0x180012815  mov     r14, rax
0x180012818  test    rsi, rsi
0x18001281b  jz      short loc_180012855
0x18001281d  call    cs:__imp_GetLastError
0x180012823  xor     r9d, r9d; msWindowLength
0x180012826  xor     r8d, r8d; msPeriod
0x180012829  xor     edx, edx; pftDueTime
0x18001282b  mov     rcx, rsi; pti
0x18001282e  mov     ebx, eax
0x180012830  call    cs:__imp_SetThreadpoolTimer
0x180012836  mov     edx, 1; fCancelPendingCallbacks
0x18001283b  mov     rcx, rsi; pti
0x18001283e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012844  mov     rcx, rsi; pti
0x180012847  call    cs:__imp_CloseThreadpoolTimer
0x18001284d  mov     ecx, ebx; dwErrCode
0x18001284f  call    cs:__imp_SetLastError
0x180012855  mov     ecx, ebp; dwErrCode
0x180012857  mov     [rdi+30h], r14
0x18001285b  call    cs:__imp_SetLastError
0x180012861  mov     rcx, [rdi+30h]; pti
0x180012865  test    rcx, rcx
0x180012868  jz      short loc_180012891
0x18001286a  mov     rax, 0FFFFFFFF4D2FA200h
0x180012874  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180012879  mov     r9d, 124F8h; msWindowLength
0x18001287f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180012884  xor     r8d, r8d; msPeriod
0x180012887  call    cs:__imp_SetThreadpoolTimer
0x18001288d  mov     byte ptr [rdi+41h], 1
0x180012891  mov     rbx, [rsp+38h+arg_8]
0x180012896  mov     rbp, [rsp+38h+arg_10]
0x18001289b  add     rsp, 20h
0x18001289f  pop     r14
0x1800128a1  pop     rdi
0x1800128a2  pop     rsi
0x1800128a3  retn
```
