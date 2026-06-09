# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(void)

- ea: `0x18000cbd8`
- end: `0x18000cc14`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180081590`
- `0x180081cdf`

## callees

- `0x18000cbd8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cbff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cbff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cc08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cc08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cbf1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cbf1`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(
        PTP_TIMER *a1)
{
  struct _TP_TIMER *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    SetThreadpoolTimer(*a1, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v1, 1);
    CloseThreadpoolTimer(v1);
  }
}

```

## disassembly

```asm
0x18000cbd8  push    rbx
0x18000cbda  sub     rsp, 20h
0x18000cbde  mov     rbx, [rcx]
0x18000cbe1  test    rbx, rbx
0x18000cbe4  jz      short loc_18000CC0E
0x18000cbe6  xor     r9d, r9d; msWindowLength
0x18000cbe9  xor     r8d, r8d; msPeriod
0x18000cbec  xor     edx, edx; pftDueTime
0x18000cbee  mov     rcx, rbx; pti
0x18000cbf1  call    cs:__imp_SetThreadpoolTimer
0x18000cbf7  mov     edx, 1; fCancelPendingCallbacks
0x18000cbfc  mov     rcx, rbx; pti
0x18000cbff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cc05  mov     rcx, rbx; pti
0x18000cc08  call    cs:__imp_CloseThreadpoolTimer
0x18000cc0e  add     rsp, 20h
0x18000cc12  pop     rbx
0x18000cc13  retn
```
