# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(void)

- ea: `0x180011904`
- end: `0x180011940`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800ea9d3`

## callees

- `0x180011904`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001191d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001191d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011934`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011934`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001192b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001192b`

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
0x180011904  push    rbx
0x180011906  sub     rsp, 20h
0x18001190a  mov     rbx, [rcx]
0x18001190d  test    rbx, rbx
0x180011910  jz      short loc_18001193A
0x180011912  xor     r9d, r9d; msWindowLength
0x180011915  xor     r8d, r8d; msPeriod
0x180011918  xor     edx, edx; pftDueTime
0x18001191a  mov     rcx, rbx; pti
0x18001191d  call    cs:__imp_SetThreadpoolTimer
0x180011923  mov     edx, 1; fCancelPendingCallbacks
0x180011928  mov     rcx, rbx; pti
0x18001192b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011931  mov     rcx, rbx; pti
0x180011934  call    cs:__imp_CloseThreadpoolTimer
0x18001193a  add     rsp, 20h
0x18001193e  pop     rbx
0x18001193f  retn
```
