# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000ca18`
- end: `0x18000cac0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f1c4`

## callees

- `0x18000ca18`
- `0x1800125b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca6e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ca55`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ca55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca9f`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v2; // rsi
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
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
0x18000ca18  mov     [rsp+arg_8], rbx
0x18000ca1d  mov     [rsp+arg_10], rsi
0x18000ca22  push    rdi
0x18000ca23  sub     rsp, 20h
0x18000ca27  cmp     byte ptr [rcx+41h], 0
0x18000ca2b  mov     rdi, rcx
0x18000ca2e  jnz     short loc_18000CAAF
0x18000ca30  lea     rsi, [rcx+30h]
0x18000ca34  cmp     qword ptr [rsi], 0
0x18000ca38  jnz     short loc_18000CA7A
0x18000ca3a  call    cs:__imp_GetLastError
0x18000ca41  nop     dword ptr [rax+rax+00h]
0x18000ca46  xor     r8d, r8d; pcbe
0x18000ca49  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ca50  mov     rdx, rdi; pv
0x18000ca53  mov     ebx, eax
0x18000ca55  call    cs:__imp_CreateThreadpoolTimer
0x18000ca5c  nop     dword ptr [rax+rax+00h]
0x18000ca61  mov     rdx, rax
0x18000ca64  mov     rcx, rsi
0x18000ca67  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000ca6c  mov     ecx, ebx; dwErrCode
0x18000ca6e  call    cs:__imp_SetLastError
0x18000ca75  nop     dword ptr [rax+rax+00h]
0x18000ca7a  mov     rcx, [rsi]; pti
0x18000ca7d  test    rcx, rcx
0x18000ca80  jz      short loc_18000CAAF
0x18000ca82  mov     rax, 0FFFFFFFF4D2FA200h
0x18000ca8c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000ca91  mov     r9d, 124F8h; msWindowLength
0x18000ca97  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000ca9c  xor     r8d, r8d; msPeriod
0x18000ca9f  call    cs:__imp_SetThreadpoolTimer
0x18000caa6  nop     dword ptr [rax+rax+00h]
0x18000caab  mov     byte ptr [rdi+41h], 1
0x18000caaf  mov     rbx, [rsp+28h+arg_8]
0x18000cab4  mov     rsi, [rsp+28h+arg_10]
0x18000cab9  add     rsp, 20h
0x18000cabd  pop     rdi
0x18000cabe  retn
```
