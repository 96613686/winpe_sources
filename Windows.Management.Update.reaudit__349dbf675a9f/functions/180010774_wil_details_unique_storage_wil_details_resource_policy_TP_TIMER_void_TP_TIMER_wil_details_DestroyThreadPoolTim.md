# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180010774`
- end: `0x180010805`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009e7c`
- `0x18000a0b0`
- `0x18000b358`
- `0x18000d214`
- `0x18000d2c8`
- `0x18001d4bc`

## callees

- `0x180010774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010796`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800107e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800107e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800107c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800107c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800107d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800107d2`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180010774  mov     [rsp+arg_0], rbx
0x180010779  mov     [rsp+arg_8], rbp
0x18001077e  mov     [rsp+arg_10], rsi
0x180010783  push    rdi
0x180010784  sub     rsp, 20h
0x180010788  mov     rsi, [rcx]
0x18001078b  mov     rbp, rdx
0x18001078e  mov     rdi, rcx
0x180010791  test    rsi, rsi
0x180010794  jz      short loc_1800107EC
0x180010796  call    cs:__imp_GetLastError
0x18001079d  nop     dword ptr [rax+rax+00h]
0x1800107a2  xor     r9d, r9d; msWindowLength
0x1800107a5  xor     r8d, r8d; msPeriod
0x1800107a8  xor     edx, edx; pftDueTime
0x1800107aa  mov     rcx, rsi; pti
0x1800107ad  mov     ebx, eax
0x1800107af  call    cs:__imp_SetThreadpoolTimer
0x1800107b6  nop     dword ptr [rax+rax+00h]
0x1800107bb  mov     edx, 1; fCancelPendingCallbacks
0x1800107c0  mov     rcx, rsi; pti
0x1800107c3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800107ca  nop     dword ptr [rax+rax+00h]
0x1800107cf  mov     rcx, rsi; pti
0x1800107d2  call    cs:__imp_CloseThreadpoolTimer
0x1800107d9  nop     dword ptr [rax+rax+00h]
0x1800107de  mov     ecx, ebx; dwErrCode
0x1800107e0  call    cs:__imp_SetLastError
0x1800107e7  nop     dword ptr [rax+rax+00h]
0x1800107ec  mov     rbx, [rsp+28h+arg_0]
0x1800107f1  mov     rsi, [rsp+28h+arg_10]
0x1800107f6  mov     [rdi], rbp
0x1800107f9  mov     rbp, [rsp+28h+arg_8]
0x1800107fe  add     rsp, 20h
0x180010802  pop     rdi
0x180010803  retn
```
