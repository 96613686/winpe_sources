# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180003db0`
- end: `0x180003e58`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000595c`

## callees

- `0x180003db0`
- `0x18000897c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003dd2`
- `KERNEL32!GetLastError` at `0x180003dd2`
- `KERNEL32!SetLastError` at `0x180003e06`
- `KERNEL32!SetLastError` at `0x180003e06`
- `KERNEL32!SetThreadpoolTimer` at `0x180003e37`
- `KERNEL32!SetThreadpoolTimer` at `0x180003e37`
- `KERNEL32!CreateThreadpoolTimer` at `0x180003ded`
- `KERNEL32!CreateThreadpoolTimer` at `0x180003ded`

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
0x180003db0  mov     [rsp+arg_8], rbx
0x180003db5  mov     [rsp+arg_10], rsi
0x180003dba  push    rdi
0x180003dbb  sub     rsp, 20h
0x180003dbf  cmp     byte ptr [rcx+41h], 0
0x180003dc3  mov     rdi, rcx
0x180003dc6  jnz     short loc_180003E47
0x180003dc8  lea     rsi, [rcx+30h]
0x180003dcc  cmp     qword ptr [rsi], 0
0x180003dd0  jnz     short loc_180003E12
0x180003dd2  call    cs:__imp_GetLastError
0x180003dd9  nop     dword ptr [rax+rax+00h]
0x180003dde  xor     r8d, r8d; pcbe
0x180003de1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180003de8  mov     rdx, rdi; pv
0x180003deb  mov     ebx, eax
0x180003ded  call    cs:__imp_CreateThreadpoolTimer
0x180003df4  nop     dword ptr [rax+rax+00h]
0x180003df9  mov     rdx, rax
0x180003dfc  mov     rcx, rsi
0x180003dff  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180003e04  mov     ecx, ebx; dwErrCode
0x180003e06  call    cs:__imp_SetLastError
0x180003e0d  nop     dword ptr [rax+rax+00h]
0x180003e12  mov     rcx, [rsi]; pti
0x180003e15  test    rcx, rcx
0x180003e18  jz      short loc_180003E47
0x180003e1a  mov     rax, 0FFFFFFFF4D2FA200h
0x180003e24  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180003e29  mov     r9d, 124F8h; msWindowLength
0x180003e2f  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180003e34  xor     r8d, r8d; msPeriod
0x180003e37  call    cs:__imp_SetThreadpoolTimer
0x180003e3e  nop     dword ptr [rax+rax+00h]
0x180003e43  mov     byte ptr [rdi+41h], 1
0x180003e47  mov     rbx, [rsp+28h+arg_8]
0x180003e4c  mov     rsi, [rsp+28h+arg_10]
0x180003e51  add     rsp, 20h
0x180003e55  pop     rdi
0x180003e56  retn
```
