# _dynamic_atexit_destructor_for__AgentManager2::s_cleanupTimer__

- ea: `0x180067470`
- end: `0x1800674b0`
- name: `_dynamic_atexit_destructor_for__AgentManager2::s_cleanupTimer__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180067470`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006748d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006748d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800674a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800674a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006749b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006749b`

## pseudocode

```c
void dynamic_atexit_destructor_for__AgentManager2::s_cleanupTimer__()
{
  struct _TP_TIMER *v0; // rbx

  v0 = AgentManager2::s_cleanupTimer;
  if ( AgentManager2::s_cleanupTimer )
  {
    SetThreadpoolTimer(AgentManager2::s_cleanupTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v0, 1);
    CloseThreadpoolTimer(v0);
  }
}

```

## disassembly

```asm
0x180067470  push    rbx
0x180067472  sub     rsp, 20h
0x180067476  mov     rbx, cs:?s_cleanupTimer@AgentManager2@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager2::s_cleanupTimer
0x18006747d  test    rbx, rbx
0x180067480  jz      short loc_1800674AA
0x180067482  xor     r9d, r9d; msWindowLength
0x180067485  xor     r8d, r8d; msPeriod
0x180067488  xor     edx, edx; pftDueTime
0x18006748a  mov     rcx, rbx; pti
0x18006748d  call    cs:__imp_SetThreadpoolTimer
0x180067493  mov     edx, 1; fCancelPendingCallbacks
0x180067498  mov     rcx, rbx; pti
0x18006749b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800674a1  mov     rcx, rbx; pti
0x1800674a4  call    cs:__imp_CloseThreadpoolTimer
0x1800674aa  add     rsp, 20h
0x1800674ae  pop     rbx
0x1800674af  retn
```
