# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180025068`
- end: `0x180025110`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180026d04`

## callees

- `0x180025068`
- `0x180028f24`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1800250a5`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800250a5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800250ef`
- `KERNEL32!SetThreadpoolTimer` at `0x1800250ef`
- `KERNEL32!SetLastError` at `0x1800250be`
- `KERNEL32!SetLastError` at `0x1800250be`
- `KERNEL32!GetLastError` at `0x18002508a`
- `KERNEL32!GetLastError` at `0x18002508a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    v2 = pv + 6;
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                          pv,
                          0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v2,
        ThreadpoolTimer);
      SetLastError(LastError);
    }
    v5 = *v2;
    if ( *v2 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v5, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180025068  mov     [rsp+arg_8], rbx
0x18002506d  mov     [rsp+arg_10], rsi
0x180025072  push    rdi
0x180025073  sub     rsp, 20h
0x180025077  cmp     byte ptr [rcx+41h], 0
0x18002507b  mov     rdi, rcx
0x18002507e  jnz     short loc_1800250FF
0x180025080  lea     rsi, [rcx+30h]
0x180025084  cmp     qword ptr [rsi], 0
0x180025088  jnz     short loc_1800250CA
0x18002508a  call    cs:__imp_GetLastError
0x180025091  nop     dword ptr [rax+rax+00h]
0x180025096  xor     r8d, r8d; pcbe
0x180025099  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800250a0  mov     rdx, rdi; pv
0x1800250a3  mov     ebx, eax
0x1800250a5  call    cs:__imp_CreateThreadpoolTimer
0x1800250ac  nop     dword ptr [rax+rax+00h]
0x1800250b1  mov     rdx, rax
0x1800250b4  mov     rcx, rsi
0x1800250b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800250bc  mov     ecx, ebx; dwErrCode
0x1800250be  call    cs:__imp_SetLastError
0x1800250c5  nop     dword ptr [rax+rax+00h]
0x1800250ca  mov     rcx, [rsi]; pti
0x1800250cd  test    rcx, rcx
0x1800250d0  jz      short loc_1800250FF
0x1800250d2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800250dc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800250e1  mov     r9d, 124F8h; msWindowLength
0x1800250e7  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x1800250ec  xor     r8d, r8d; msPeriod
0x1800250ef  call    cs:__imp_SetThreadpoolTimer
0x1800250f6  nop     dword ptr [rax+rax+00h]
0x1800250fb  mov     byte ptr [rdi+41h], 1
0x1800250ff  mov     rbx, [rsp+28h+arg_8]
0x180025104  mov     rsi, [rsp+28h+arg_10]
0x180025109  add     rsp, 20h
0x18002510d  pop     rdi
0x18002510e  retn
```
