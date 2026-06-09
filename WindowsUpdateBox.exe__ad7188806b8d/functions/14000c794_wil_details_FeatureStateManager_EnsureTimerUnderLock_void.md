# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14000c794`
- end: `0x14000c83c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001ba94`

## callees

- `0x14000c794`
- `0x140021310`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x14000c81b`
- `KERNEL32!SetThreadpoolTimer` at `0x14000c81b`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000c7d1`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000c7d1`
- `KERNEL32!GetLastError` at `0x14000c7b6`
- `KERNEL32!GetLastError` at `0x14000c7b6`
- `KERNEL32!SetLastError` at `0x14000c7ea`
- `KERNEL32!SetLastError` at `0x14000c7ea`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v1; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v1 = pv + 6;
  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !*v1 )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v1,
        ThreadpoolTimer);
      SetLastError(LastError);
    }
    v5 = *v1;
    if ( *v1 )
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
0x14000c794  mov     [rsp+arg_8], rbx
0x14000c799  mov     [rsp+arg_10], rsi
0x14000c79e  push    rdi
0x14000c79f  sub     rsp, 20h
0x14000c7a3  cmp     byte ptr [rcx+41h], 0
0x14000c7a7  lea     rsi, [rcx+30h]
0x14000c7ab  mov     rdi, rcx
0x14000c7ae  jnz     short loc_14000C82B
0x14000c7b0  cmp     qword ptr [rsi], 0
0x14000c7b4  jnz     short loc_14000C7F6
0x14000c7b6  call    cs:__imp_GetLastError
0x14000c7bd  nop     dword ptr [rax+rax+00h]
0x14000c7c2  xor     r8d, r8d; pcbe
0x14000c7c5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000c7cc  mov     rdx, rdi; pv
0x14000c7cf  mov     ebx, eax
0x14000c7d1  call    cs:__imp_CreateThreadpoolTimer
0x14000c7d8  nop     dword ptr [rax+rax+00h]
0x14000c7dd  mov     rdx, rax
0x14000c7e0  mov     rcx, rsi
0x14000c7e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000c7e8  mov     ecx, ebx; dwErrCode
0x14000c7ea  call    cs:__imp_SetLastError
0x14000c7f1  nop     dword ptr [rax+rax+00h]
0x14000c7f6  mov     rcx, [rsi]; pti
0x14000c7f9  test    rcx, rcx
0x14000c7fc  jz      short loc_14000C82B
0x14000c7fe  mov     rax, 0FFFFFFFF4D2FA200h
0x14000c808  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x14000c80d  mov     r9d, 124F8h; msWindowLength
0x14000c813  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x14000c818  xor     r8d, r8d; msPeriod
0x14000c81b  call    cs:__imp_SetThreadpoolTimer
0x14000c822  nop     dword ptr [rax+rax+00h]
0x14000c827  mov     byte ptr [rdi+41h], 1
0x14000c82b  mov     rbx, [rsp+28h+arg_8]
0x14000c830  mov     rsi, [rsp+28h+arg_10]
0x14000c835  add     rsp, 20h
0x14000c839  pop     rdi
0x14000c83a  retn
```
