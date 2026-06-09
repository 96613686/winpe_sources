# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(void)

- ea: `0x14000f904`
- end: `0x14000f940`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(PTP_TIMER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400231fb`

## callees

- `0x14000f904`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000f91d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000f91d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000f934`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000f934`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000f92b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000f92b`

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
0x14000f904  push    rbx
0x14000f906  sub     rsp, 20h
0x14000f90a  mov     rbx, [rcx]
0x14000f90d  test    rbx, rbx
0x14000f910  jz      short loc_14000F93A
0x14000f912  xor     r9d, r9d; msWindowLength
0x14000f915  xor     r8d, r8d; msPeriod
0x14000f918  xor     edx, edx; pftDueTime
0x14000f91a  mov     rcx, rbx; pti
0x14000f91d  call    cs:__imp_SetThreadpoolTimer
0x14000f923  mov     edx, 1; fCancelPendingCallbacks
0x14000f928  mov     rcx, rbx; pti
0x14000f92b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000f931  mov     rcx, rbx; pti
0x14000f934  call    cs:__imp_CloseThreadpoolTimer
0x14000f93a  add     rsp, 20h
0x14000f93e  pop     rbx
0x14000f93f  retn
```
