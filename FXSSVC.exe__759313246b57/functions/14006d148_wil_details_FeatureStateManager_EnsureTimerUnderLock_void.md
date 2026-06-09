# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14006d148`
- end: `0x14006d1f0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14006eeb4`

## callees

- `0x14006d148`
- `0x1400717b8`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14006d185`
- `KERNEL32!CreateThreadpoolTimer` at `0x14006d185`
- `KERNEL32!SetThreadpoolTimer` at `0x14006d1cf`
- `KERNEL32!SetThreadpoolTimer` at `0x14006d1cf`
- `KERNEL32!GetLastError` at `0x14006d16a`
- `KERNEL32!GetLastError` at `0x14006d16a`
- `KERNEL32!SetLastError` at `0x14006d19e`
- `KERNEL32!SetLastError` at `0x14006d19e`

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
0x14006d148  mov     [rsp+arg_8], rbx
0x14006d14d  mov     [rsp+arg_10], rsi
0x14006d152  push    rdi
0x14006d153  sub     rsp, 20h
0x14006d157  cmp     byte ptr [rcx+41h], 0
0x14006d15b  mov     rdi, rcx
0x14006d15e  jnz     short loc_14006D1DF
0x14006d160  lea     rsi, [rcx+30h]
0x14006d164  cmp     qword ptr [rsi], 0
0x14006d168  jnz     short loc_14006D1AA
0x14006d16a  call    cs:__imp_GetLastError
0x14006d171  nop     dword ptr [rax+rax+00h]
0x14006d176  xor     r8d, r8d; pcbe
0x14006d179  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14006d180  mov     rdx, rdi; pv
0x14006d183  mov     ebx, eax
0x14006d185  call    cs:__imp_CreateThreadpoolTimer
0x14006d18c  nop     dword ptr [rax+rax+00h]
0x14006d191  mov     rdx, rax
0x14006d194  mov     rcx, rsi
0x14006d197  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14006d19c  mov     ecx, ebx; dwErrCode
0x14006d19e  call    cs:__imp_SetLastError
0x14006d1a5  nop     dword ptr [rax+rax+00h]
0x14006d1aa  mov     rcx, [rsi]; pti
0x14006d1ad  test    rcx, rcx
0x14006d1b0  jz      short loc_14006D1DF
0x14006d1b2  mov     rax, 0FFFFFFFF4D2FA200h
0x14006d1bc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x14006d1c1  mov     r9d, 124F8h; msWindowLength
0x14006d1c7  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x14006d1cc  xor     r8d, r8d; msPeriod
0x14006d1cf  call    cs:__imp_SetThreadpoolTimer
0x14006d1d6  nop     dword ptr [rax+rax+00h]
0x14006d1db  mov     byte ptr [rdi+41h], 1
0x14006d1df  mov     rbx, [rsp+28h+arg_8]
0x14006d1e4  mov     rsi, [rsp+28h+arg_10]
0x14006d1e9  add     rsp, 20h
0x14006d1ed  pop     rdi
0x14006d1ee  retn
```
