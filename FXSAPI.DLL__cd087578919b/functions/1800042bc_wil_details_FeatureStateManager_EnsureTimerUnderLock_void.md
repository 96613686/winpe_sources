# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800042bc`
- end: `0x180004364`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006b54`

## callees

- `0x1800042bc`
- `0x18000981c`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1800042f9`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800042f9`
- `KERNEL32!SetThreadpoolTimer` at `0x180004343`
- `KERNEL32!SetThreadpoolTimer` at `0x180004343`
- `KERNEL32!SetLastError` at `0x180004312`
- `KERNEL32!SetLastError` at `0x180004312`
- `KERNEL32!GetLastError` at `0x1800042de`
- `KERNEL32!GetLastError` at `0x1800042de`

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
0x1800042bc  mov     [rsp+arg_8], rbx
0x1800042c1  mov     [rsp+arg_10], rsi
0x1800042c6  push    rdi
0x1800042c7  sub     rsp, 20h
0x1800042cb  cmp     byte ptr [rcx+41h], 0
0x1800042cf  mov     rdi, rcx
0x1800042d2  jnz     short loc_180004353
0x1800042d4  lea     rsi, [rcx+30h]
0x1800042d8  cmp     qword ptr [rsi], 0
0x1800042dc  jnz     short loc_18000431E
0x1800042de  call    cs:__imp_GetLastError
0x1800042e5  nop     dword ptr [rax+rax+00h]
0x1800042ea  xor     r8d, r8d; pcbe
0x1800042ed  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800042f4  mov     rdx, rdi; pv
0x1800042f7  mov     ebx, eax
0x1800042f9  call    cs:__imp_CreateThreadpoolTimer
0x180004300  nop     dword ptr [rax+rax+00h]
0x180004305  mov     rdx, rax
0x180004308  mov     rcx, rsi
0x18000430b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180004310  mov     ecx, ebx; dwErrCode
0x180004312  call    cs:__imp_SetLastError
0x180004319  nop     dword ptr [rax+rax+00h]
0x18000431e  mov     rcx, [rsi]; pti
0x180004321  test    rcx, rcx
0x180004324  jz      short loc_180004353
0x180004326  mov     rax, 0FFFFFFFF4D2FA200h
0x180004330  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180004335  mov     r9d, 124F8h; msWindowLength
0x18000433b  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180004340  xor     r8d, r8d; msPeriod
0x180004343  call    cs:__imp_SetThreadpoolTimer
0x18000434a  nop     dword ptr [rax+rax+00h]
0x18000434f  mov     byte ptr [rdi+41h], 1
0x180004353  mov     rbx, [rsp+28h+arg_8]
0x180004358  mov     rsi, [rsp+28h+arg_10]
0x18000435d  add     rsp, 20h
0x180004361  pop     rdi
0x180004362  retn
```
