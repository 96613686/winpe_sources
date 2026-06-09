# _dynamic_atexit_destructor_for__AgentManager::s_cleanupTimer__

- ea: `0x180067330`
- end: `0x180067370`
- name: `_dynamic_atexit_destructor_for__AgentManager::s_cleanupTimer__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180067330`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006734d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006734d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180067364`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180067364`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006735b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006735b`

## pseudocode

```c
void dynamic_atexit_destructor_for__AgentManager::s_cleanupTimer__()
{
  struct _TP_TIMER *v0; // rbx

  v0 = AgentManager::s_cleanupTimer;
  if ( AgentManager::s_cleanupTimer )
  {
    SetThreadpoolTimer(AgentManager::s_cleanupTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v0, 1);
    CloseThreadpoolTimer(v0);
  }
}

```

## disassembly

```asm
0x180067330  push    rbx
0x180067332  sub     rsp, 20h
0x180067336  mov     rbx, cs:?s_cleanupTimer@AgentManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager::s_cleanupTimer
0x18006733d  test    rbx, rbx
0x180067340  jz      short loc_18006736A
0x180067342  xor     r9d, r9d; msWindowLength
0x180067345  xor     r8d, r8d; msPeriod
0x180067348  xor     edx, edx; pftDueTime
0x18006734a  mov     rcx, rbx; pti
0x18006734d  call    cs:__imp_SetThreadpoolTimer
0x180067353  mov     edx, 1; fCancelPendingCallbacks
0x180067358  mov     rcx, rbx; pti
0x18006735b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180067361  mov     rcx, rbx; pti
0x180067364  call    cs:__imp_CloseThreadpoolTimer
0x18006736a  add     rsp, 20h
0x18006736e  pop     rbx
0x18006736f  retn
```
