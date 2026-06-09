# wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180005028`
- end: `0x180005118`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800089dc`

## callees

- `0x180005028`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000505d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000505d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005084`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005097`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800050ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005097`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800050ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005072`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005072`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800050ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800050ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800050a5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800050a5`

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
0x180005028  mov     [rsp+arg_8], rbx
0x18000502d  mov     [rsp+arg_10], rbp
0x180005032  push    rsi
0x180005033  push    rdi
0x180005034  push    r14
0x180005036  sub     rsp, 30h
0x18000503a  mov     rax, cs:__security_cookie
0x180005041  xor     rax, rsp
0x180005044  mov     [rsp+48h+var_20], rax
0x180005049  cmp     byte ptr [rcx+18h], 0
0x18000504d  mov     rdi, rcx
0x180005050  jnz     loc_1800050F8
0x180005056  cmp     qword ptr [rcx+10h], 0
0x18000505b  jnz     short loc_1800050C8
0x18000505d  call    cs:__imp_GetLastError
0x180005063  xor     r8d, r8d; pcbe
0x180005066  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000506d  mov     rdx, rdi; pv
0x180005070  mov     ebp, eax
0x180005072  call    cs:__imp_CreateThreadpoolTimer
0x180005078  mov     rsi, [rdi+10h]
0x18000507c  mov     r14, rax
0x18000507f  test    rsi, rsi
0x180005082  jz      short loc_1800050BC
0x180005084  call    cs:__imp_GetLastError
0x18000508a  xor     r9d, r9d; msWindowLength
0x18000508d  xor     r8d, r8d; msPeriod
0x180005090  xor     edx, edx; pftDueTime
0x180005092  mov     rcx, rsi; pti
0x180005095  mov     ebx, eax
0x180005097  call    cs:__imp_SetThreadpoolTimer
0x18000509d  mov     edx, 1; fCancelPendingCallbacks
0x1800050a2  mov     rcx, rsi; pti
0x1800050a5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800050ab  mov     rcx, rsi; pti
0x1800050ae  call    cs:__imp_CloseThreadpoolTimer
0x1800050b4  mov     ecx, ebx; dwErrCode
0x1800050b6  call    cs:__imp_SetLastError
0x1800050bc  mov     ecx, ebp; dwErrCode
0x1800050be  mov     [rdi+10h], r14
0x1800050c2  call    cs:__imp_SetLastError
0x1800050c8  mov     rcx, [rdi+10h]; pti
0x1800050cc  test    rcx, rcx
0x1800050cf  jz      short loc_1800050F8
0x1800050d1  mov     rax, 0FFFFFFFF4D2FA200h
0x1800050db  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800050e0  mov     r9d, 124F8h; msWindowLength
0x1800050e6  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800050eb  xor     r8d, r8d; msPeriod
0x1800050ee  call    cs:__imp_SetThreadpoolTimer
0x1800050f4  mov     byte ptr [rdi+18h], 1
0x1800050f8  mov     rcx, [rsp+48h+var_20]
0x1800050fd  xor     rcx, rsp; StackCookie
0x180005100  call    __security_check_cookie
0x180005105  mov     rbx, [rsp+48h+arg_8]
0x18000510a  mov     rbp, [rsp+48h+arg_10]
0x18000510f  add     rsp, 30h
0x180005113  pop     r14
0x180005115  pop     rdi
0x180005116  pop     rsi
0x180005117  retn
```
