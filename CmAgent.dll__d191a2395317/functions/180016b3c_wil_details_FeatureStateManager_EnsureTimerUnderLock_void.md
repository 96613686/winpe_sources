# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180016b3c`
- end: `0x180016be4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019d60`

## callees

- `0x180016b3c`
- `0x180021b48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016b92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016b92`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016b79`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016b79`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016bc3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016bc3`

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
0x180016b3c  mov     [rsp+arg_8], rbx
0x180016b41  mov     [rsp+arg_10], rsi
0x180016b46  push    rdi
0x180016b47  sub     rsp, 20h
0x180016b4b  cmp     byte ptr [rcx+41h], 0
0x180016b4f  mov     rdi, rcx
0x180016b52  jnz     short loc_180016BD3
0x180016b54  lea     rsi, [rcx+30h]
0x180016b58  cmp     qword ptr [rsi], 0
0x180016b5c  jnz     short loc_180016B9E
0x180016b5e  call    cs:__imp_GetLastError
0x180016b65  nop     dword ptr [rax+rax+00h]
0x180016b6a  xor     r8d, r8d; pcbe
0x180016b6d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180016b74  mov     rdx, rdi; pv
0x180016b77  mov     ebx, eax
0x180016b79  call    cs:__imp_CreateThreadpoolTimer
0x180016b80  nop     dword ptr [rax+rax+00h]
0x180016b85  mov     rdx, rax
0x180016b88  mov     rcx, rsi
0x180016b8b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180016b90  mov     ecx, ebx; dwErrCode
0x180016b92  call    cs:__imp_SetLastError
0x180016b99  nop     dword ptr [rax+rax+00h]
0x180016b9e  mov     rcx, [rsi]; pti
0x180016ba1  test    rcx, rcx
0x180016ba4  jz      short loc_180016BD3
0x180016ba6  mov     rax, 0FFFFFFFF4D2FA200h
0x180016bb0  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180016bb5  mov     r9d, 124F8h; msWindowLength
0x180016bbb  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180016bc0  xor     r8d, r8d; msPeriod
0x180016bc3  call    cs:__imp_SetThreadpoolTimer
0x180016bca  nop     dword ptr [rax+rax+00h]
0x180016bcf  mov     byte ptr [rdi+41h], 1
0x180016bd3  mov     rbx, [rsp+28h+arg_8]
0x180016bd8  mov     rsi, [rsp+28h+arg_10]
0x180016bdd  add     rsp, 20h
0x180016be1  pop     rdi
0x180016be2  retn
```
