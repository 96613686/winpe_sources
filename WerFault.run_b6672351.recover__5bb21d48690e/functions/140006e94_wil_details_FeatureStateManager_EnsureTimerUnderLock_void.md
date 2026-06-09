# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140006e94`
- end: `0x140006f3c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009544`

## callees

- `0x140006e94`
- `0x14000cec8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006eb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006eea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006eea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006ed1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006ed1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f1b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f1b`

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
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
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
0x140006e94  mov     [rsp+arg_8], rbx
0x140006e99  mov     [rsp+arg_10], rsi
0x140006e9e  push    rdi
0x140006e9f  sub     rsp, 20h
0x140006ea3  cmp     byte ptr [rcx+41h], 0
0x140006ea7  mov     rdi, rcx
0x140006eaa  jnz     short loc_140006F2B
0x140006eac  lea     rsi, [rcx+30h]
0x140006eb0  cmp     qword ptr [rsi], 0
0x140006eb4  jnz     short loc_140006EF6
0x140006eb6  call    cs:__imp_GetLastError
0x140006ebd  nop     dword ptr [rax+rax+00h]
0x140006ec2  xor     r8d, r8d; pcbe
0x140006ec5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140006ecc  mov     rdx, rdi; pv
0x140006ecf  mov     ebx, eax
0x140006ed1  call    cs:__imp_CreateThreadpoolTimer
0x140006ed8  nop     dword ptr [rax+rax+00h]
0x140006edd  mov     rdx, rax
0x140006ee0  mov     rcx, rsi
0x140006ee3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140006ee8  mov     ecx, ebx; dwErrCode
0x140006eea  call    cs:__imp_SetLastError
0x140006ef1  nop     dword ptr [rax+rax+00h]
0x140006ef6  mov     rcx, [rsi]; pti
0x140006ef9  test    rcx, rcx
0x140006efc  jz      short loc_140006F2B
0x140006efe  mov     rax, 0FFFFFFFF4D2FA200h
0x140006f08  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x140006f0d  mov     r9d, 124F8h; msWindowLength
0x140006f13  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x140006f18  xor     r8d, r8d; msPeriod
0x140006f1b  call    cs:__imp_SetThreadpoolTimer
0x140006f22  nop     dword ptr [rax+rax+00h]
0x140006f27  mov     byte ptr [rdi+41h], 1
0x140006f2b  mov     rbx, [rsp+28h+arg_8]
0x140006f30  mov     rsi, [rsp+28h+arg_10]
0x140006f35  add     rsp, 20h
0x140006f39  pop     rdi
0x140006f3a  retn
```
