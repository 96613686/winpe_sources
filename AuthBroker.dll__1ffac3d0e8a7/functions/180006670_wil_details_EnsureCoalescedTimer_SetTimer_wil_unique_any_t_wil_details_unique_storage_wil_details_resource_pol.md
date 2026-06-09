# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x180006670`
- end: `0x1800066ab`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: `void __fastcall(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (__cdecl*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy,wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t> > > *timer, bool *timerSet, __int64 delay)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006494`
- `0x180006588`

## callees

- `0x180006670`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000669c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000669c`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (__cdecl*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy,wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t> > > *timer,
        bool *timerSet,
        __int64 delay)
{
  _TP_TIMER *m_ptr; // rcx
  _FILETIME dueTime; // [rsp+30h] [rbp+8h] BYREF

  m_ptr = timer->m_ptr;
  if ( m_ptr )
  {
    dueTime = (_FILETIME)(-10000 * delay);
    SetThreadpoolTimer(m_ptr, &dueTime, 0, (unsigned int)delay >> 2);
    *timerSet = 1;
  }
}

```

## disassembly

```asm
0x180006670  push    rbx
0x180006672  sub     rsp, 20h
0x180006676  mov     timer, [timer]; pti
0x180006679  mov     rbx, timerSet
0x18000667c  test    timer, timer
0x18000667f  jz      short loc_1800066A5
0x180006681  imul    rax, delay, 0FFFFFFFFFFFFD8F0h
0x180006688  shr     r8d, 2
0x18000668c  lea     timerSet, [rsp+28h+dueTime]; pftDueTime
0x180006691  mov     r9d, r8d; msWindowLength
0x180006694  mov     qword ptr [rsp+28h+dueTime.dwLowDateTime], rax
0x180006699  xor     r8d, r8d; msPeriod
0x18000669c  call    cs:__imp_SetThreadpoolTimer
0x1800066a2  mov     byte ptr [rbx], 1
0x1800066a5  add     rsp, 20h
0x1800066a9  pop     rbx
0x1800066aa  retn
```
