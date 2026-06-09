# wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18001bc5c`
- end: `0x18001bd4c`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `240`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e54c`

## callees

- `0x180007660`
- `0x18001bc5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bcea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bcf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bcea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bcf6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001bca6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001bca6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bcd9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bcd9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bce2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bce2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bccb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bd22`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bccb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bd22`

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
0x18001bc5c  mov     [rsp+arg_8], rbx
0x18001bc61  mov     [rsp+arg_10], rbp
0x18001bc66  push    rsi
0x18001bc67  push    rdi
0x18001bc68  push    r14
0x18001bc6a  sub     rsp, 30h
0x18001bc6e  mov     rax, cs:__security_cookie
0x18001bc75  xor     rax, rsp
0x18001bc78  mov     [rsp+48h+var_20], rax
0x18001bc7d  cmp     byte ptr [rcx+18h], 0
0x18001bc81  mov     rdi, rcx
0x18001bc84  jnz     loc_18001BD2C
0x18001bc8a  cmp     qword ptr [rcx+10h], 0
0x18001bc8f  jnz     short loc_18001BCFC
0x18001bc91  call    cs:__imp_GetLastError
0x18001bc97  xor     r8d, r8d; pcbe
0x18001bc9a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001bca1  mov     rdx, rdi; pv
0x18001bca4  mov     ebp, eax
0x18001bca6  call    cs:__imp_CreateThreadpoolTimer
0x18001bcac  mov     rsi, [rdi+10h]
0x18001bcb0  mov     r14, rax
0x18001bcb3  test    rsi, rsi
0x18001bcb6  jz      short loc_18001BCF0
0x18001bcb8  call    cs:__imp_GetLastError
0x18001bcbe  xor     r9d, r9d; msWindowLength
0x18001bcc1  xor     r8d, r8d; msPeriod
0x18001bcc4  xor     edx, edx; pftDueTime
0x18001bcc6  mov     rcx, rsi; pti
0x18001bcc9  mov     ebx, eax
0x18001bccb  call    cs:__imp_SetThreadpoolTimer
0x18001bcd1  mov     edx, 1; fCancelPendingCallbacks
0x18001bcd6  mov     rcx, rsi; pti
0x18001bcd9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001bcdf  mov     rcx, rsi; pti
0x18001bce2  call    cs:__imp_CloseThreadpoolTimer
0x18001bce8  mov     ecx, ebx; dwErrCode
0x18001bcea  call    cs:__imp_SetLastError
0x18001bcf0  mov     ecx, ebp; dwErrCode
0x18001bcf2  mov     [rdi+10h], r14
0x18001bcf6  call    cs:__imp_SetLastError
0x18001bcfc  mov     rcx, [rdi+10h]; pti
0x18001bd00  test    rcx, rcx
0x18001bd03  jz      short loc_18001BD2C
0x18001bd05  mov     rax, 0FFFFFFFF4D2FA200h
0x18001bd0f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001bd14  mov     r9d, 124F8h; msWindowLength
0x18001bd1a  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18001bd1f  xor     r8d, r8d; msPeriod
0x18001bd22  call    cs:__imp_SetThreadpoolTimer
0x18001bd28  mov     byte ptr [rdi+18h], 1
0x18001bd2c  mov     rcx, [rsp+48h+var_20]
0x18001bd31  xor     rcx, rsp; StackCookie
0x18001bd34  call    __security_check_cookie
0x18001bd39  mov     rbx, [rsp+48h+arg_8]
0x18001bd3e  mov     rbp, [rsp+48h+arg_10]
0x18001bd43  add     rsp, 30h
0x18001bd47  pop     r14
0x18001bd49  pop     rdi
0x18001bd4a  pop     rsi
0x18001bd4b  retn
```
