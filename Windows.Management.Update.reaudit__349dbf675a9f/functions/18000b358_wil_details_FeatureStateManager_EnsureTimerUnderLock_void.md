# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000b358`
- end: `0x18000b400`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d854`

## callees

- `0x18000b358`
- `0x180010774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b37a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b3df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b3df`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b395`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b395`

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
0x18000b358  mov     [rsp+arg_8], rbx
0x18000b35d  mov     [rsp+arg_10], rsi
0x18000b362  push    rdi
0x18000b363  sub     rsp, 20h
0x18000b367  cmp     byte ptr [rcx+41h], 0
0x18000b36b  lea     rsi, [rcx+30h]
0x18000b36f  mov     rdi, rcx
0x18000b372  jnz     short loc_18000B3EF
0x18000b374  cmp     qword ptr [rsi], 0
0x18000b378  jnz     short loc_18000B3BA
0x18000b37a  call    cs:__imp_GetLastError
0x18000b381  nop     dword ptr [rax+rax+00h]
0x18000b386  xor     r8d, r8d; pcbe
0x18000b389  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b390  mov     rdx, rdi; pv
0x18000b393  mov     ebx, eax
0x18000b395  call    cs:__imp_CreateThreadpoolTimer
0x18000b39c  nop     dword ptr [rax+rax+00h]
0x18000b3a1  mov     rdx, rax
0x18000b3a4  mov     rcx, rsi
0x18000b3a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000b3ac  mov     ecx, ebx; dwErrCode
0x18000b3ae  call    cs:__imp_SetLastError
0x18000b3b5  nop     dword ptr [rax+rax+00h]
0x18000b3ba  mov     rcx, [rsi]; pti
0x18000b3bd  test    rcx, rcx
0x18000b3c0  jz      short loc_18000B3EF
0x18000b3c2  mov     rax, 0FFFFFFFF4D2FA200h
0x18000b3cc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000b3d1  mov     r9d, 124F8h; msWindowLength
0x18000b3d7  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000b3dc  xor     r8d, r8d; msPeriod
0x18000b3df  call    cs:__imp_SetThreadpoolTimer
0x18000b3e6  nop     dword ptr [rax+rax+00h]
0x18000b3eb  mov     byte ptr [rdi+41h], 1
0x18000b3ef  mov     rbx, [rsp+28h+arg_8]
0x18000b3f4  mov     rsi, [rsp+28h+arg_10]
0x18000b3f9  add     rsp, 20h
0x18000b3fd  pop     rdi
0x18000b3fe  retn
```
