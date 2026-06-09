# Microsoft::Windows::DisplayEnhancement::Timer::TimerAdapter::StopAndWait(void)

- ea: `0x180076e70`
- end: `0x180076ede`
- name: `?StopAndWait@TimerAdapter@Timer@DisplayEnhancement@Windows@Microsoft@@UEAAXXZ`
- size: `110`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::Timer::TimerAdapter *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009a84`
- `0x180009f30`
- `0x180053a80`
- `0x180076304`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076ea1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076ea1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180076e94`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180076e94`

## pseudocode

```c
void __fastcall Microsoft::Windows::DisplayEnhancement::Timer::TimerAdapter::StopAndWait(
        Microsoft::Windows::DisplayEnhancement::Timer::TimerAdapter *this)
{
  __int64 v1; // rdi
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 1);
  wil::details::threadpool_timer_context::ClearTimeout(*(PTP_TIMER **)(v1 + 24));
  WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(*(_QWORD *)(v1 + 24) + 80LL), 1);
  AcquireSRWLockExclusive((PSRWLOCK)(v1 + 32));
  v2 = v1 + 32;
  wistd::function<void (void)>::operator=(v1 + 48);
  *(_BYTE *)(v1 + 40) = 0;
  Microsoft::Bluetooth::Foundation::Stopwatch::Stop((Microsoft::Bluetooth::Foundation::Stopwatch *)(v1 + 168));
  *(_BYTE *)(v1 + 41) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v2);
}

```

## disassembly

```asm
0x180076e70  mov     [rsp+arg_8], rbx
0x180076e75  push    rdi
0x180076e76  sub     rsp, 20h
0x180076e7a  mov     rdi, [rcx+8]
0x180076e7e  mov     rcx, [rdi+18h]; this
0x180076e82  call    ?ClearTimeout@threadpool_timer_context@details@wil@@QEAA_NXZ; wil::details::threadpool_timer_context::ClearTimeout(void)
0x180076e87  mov     rcx, [rdi+18h]
0x180076e8b  mov     edx, 1; fCancelPendingCallbacks
0x180076e90  mov     rcx, [rcx+50h]; pti
0x180076e94  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180076e9a  lea     rbx, [rdi+20h]
0x180076e9e  mov     rcx, rbx; SRWLock
0x180076ea1  call    cs:__imp_AcquireSRWLockExclusive
0x180076ea7  lea     rcx, [rdi+30h]
0x180076eab  mov     [rsp+28h+arg_0], rbx
0x180076eb0  call    ??4?$function@$$A6AXXZ@wistd@@QEAAAEAV01@$$T@Z; wistd::function<void (void)>::operator=(std::nullptr_t)
0x180076eb5  lea     rcx, [rdi+0A8h]; this
0x180076ebc  mov     byte ptr [rdi+28h], 0
0x180076ec0  call    ?Stop@Stopwatch@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::Stopwatch::Stop(void)
0x180076ec5  lea     rcx, [rsp+28h+arg_0]
0x180076eca  mov     byte ptr [rdi+29h], 1
0x180076ece  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180076ed3  mov     rbx, [rsp+28h+arg_8]
0x180076ed8  add     rsp, 20h
0x180076edc  pop     rdi
0x180076edd  retn
```
