# wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180016124`
- end: `0x180016214`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019878`

## callees

- `0x180003520`
- `0x180016124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800161b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800161be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800161b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800161be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016180`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800161aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800161aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001616e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001616e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016193`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800161ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016193`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800161ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800161a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800161a1`

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
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

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
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 24) = 1;
    }
  }
}

```

## disassembly

```asm
0x180016124  mov     [rsp+arg_8], rbx
0x180016129  mov     [rsp+arg_10], rbp
0x18001612e  push    rsi
0x18001612f  push    rdi
0x180016130  push    r14
0x180016132  sub     rsp, 30h
0x180016136  mov     rax, cs:__security_cookie
0x18001613d  xor     rax, rsp
0x180016140  mov     [rsp+48h+var_20], rax
0x180016145  cmp     byte ptr [rcx+18h], 0
0x180016149  mov     rdi, rcx
0x18001614c  jnz     loc_1800161F4
0x180016152  cmp     qword ptr [rcx+10h], 0
0x180016157  jnz     short loc_1800161C4
0x180016159  call    cs:__imp_GetLastError
0x18001615f  xor     r8d, r8d; pcbe
0x180016162  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180016169  mov     rdx, rdi; pv
0x18001616c  mov     ebp, eax
0x18001616e  call    cs:__imp_CreateThreadpoolTimer
0x180016174  mov     rsi, [rdi+10h]
0x180016178  mov     r14, rax
0x18001617b  test    rsi, rsi
0x18001617e  jz      short loc_1800161B8
0x180016180  call    cs:__imp_GetLastError
0x180016186  xor     r9d, r9d; msWindowLength
0x180016189  xor     r8d, r8d; msPeriod
0x18001618c  xor     edx, edx; pftDueTime
0x18001618e  mov     rcx, rsi; pti
0x180016191  mov     ebx, eax
0x180016193  call    cs:__imp_SetThreadpoolTimer
0x180016199  mov     edx, 1; fCancelPendingCallbacks
0x18001619e  mov     rcx, rsi; pti
0x1800161a1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800161a7  mov     rcx, rsi; pti
0x1800161aa  call    cs:__imp_CloseThreadpoolTimer
0x1800161b0  mov     ecx, ebx; dwErrCode
0x1800161b2  call    cs:__imp_SetLastError
0x1800161b8  mov     ecx, ebp; dwErrCode
0x1800161ba  mov     [rdi+10h], r14
0x1800161be  call    cs:__imp_SetLastError
0x1800161c4  mov     rcx, [rdi+10h]; pti
0x1800161c8  test    rcx, rcx
0x1800161cb  jz      short loc_1800161F4
0x1800161cd  mov     rax, 0FFFFFFFF4D2FA200h
0x1800161d7  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800161dc  mov     r9d, 124F8h; msWindowLength
0x1800161e2  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800161e7  xor     r8d, r8d; msPeriod
0x1800161ea  call    cs:__imp_SetThreadpoolTimer
0x1800161f0  mov     byte ptr [rdi+18h], 1
0x1800161f4  mov     rcx, [rsp+48h+var_20]
0x1800161f9  xor     rcx, rsp; StackCookie
0x1800161fc  call    __security_check_cookie
0x180016201  mov     rbx, [rsp+48h+arg_8]
0x180016206  mov     rbp, [rsp+48h+arg_10]
0x18001620b  add     rsp, 30h
0x18001620f  pop     r14
0x180016211  pop     rdi
0x180016212  pop     rsi
0x180016213  retn
```
