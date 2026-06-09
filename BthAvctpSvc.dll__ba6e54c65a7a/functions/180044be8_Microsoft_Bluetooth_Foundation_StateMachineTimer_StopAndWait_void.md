# Microsoft::Bluetooth::Foundation::StateMachineTimer::StopAndWait(void)

- ea: `0x180044be8`
- end: `0x180044c62`
- name: `?StopAndWait@StateMachineTimer@Foundation@Bluetooth@Microsoft@@QEAAXXZ`
- size: `122`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::StateMachineTimer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f2bc`
- `0x18004209c`

## callees

- `0x180004060`
- `0x18000b664`
- `0x180044bc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180044c25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180044c25`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180044c18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180044c18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180044c05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180044c05`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::StateMachineTimer::StopAndWait(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // [rsp+30h] [rbp+8h] BYREF

  SetThreadpoolTimerEx(*((PTP_TIMER *)this[3].Ptr + 10), 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this[3].Ptr + 10), 1);
  AcquireSRWLockExclusive(this + 4);
  v2 = this + 4;
  wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBuffer<KSIDENTIFIER>,std::nullptr_t>)>::operator=(&this[6]);
  LOBYTE(this[5].Ptr) = 0;
  Microsoft::Bluetooth::Foundation::Stopwatch::Stop((Microsoft::Bluetooth::Foundation::Stopwatch *)&this[21]);
  BYTE1(this[5].Ptr) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v2);
}

```

## disassembly

```asm
0x180044be8  mov     [rsp+arg_8], rbx
0x180044bed  push    rdi
0x180044bee  sub     rsp, 20h
0x180044bf2  mov     rdi, rcx
0x180044bf5  xor     r9d, r9d; msWindowLength
0x180044bf8  mov     rcx, [rcx+18h]
0x180044bfc  xor     r8d, r8d; msPeriod
0x180044bff  xor     edx, edx; pftDueTime
0x180044c01  mov     rcx, [rcx+50h]; pti
0x180044c05  call    cs:__imp_SetThreadpoolTimerEx
0x180044c0b  mov     rcx, [rdi+18h]
0x180044c0f  mov     edx, 1; fCancelPendingCallbacks
0x180044c14  mov     rcx, [rcx+50h]; pti
0x180044c18  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180044c1e  lea     rbx, [rdi+20h]
0x180044c22  mov     rcx, rbx; SRWLock
0x180044c25  call    cs:__imp_AcquireSRWLockExclusive
0x180044c2b  lea     rcx, [rdi+30h]
0x180044c2f  mov     [rsp+28h+arg_0], rbx
0x180044c34  call    ??4?$function@$$A6AXU?$IoTargetIoctlResult@V?$RequestBuffer@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@Foundation@Bluetooth@Microsoft@@@Z@wistd@@QEAAAEAV01@$$T@Z; wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBuffer<KSIDENTIFIER>,std::nullptr_t>)>::operator=(std::nullptr_t)
0x180044c39  lea     rcx, [rdi+0A8h]; this
0x180044c40  mov     byte ptr [rdi+28h], 0
0x180044c44  call    ?Stop@Stopwatch@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::Stopwatch::Stop(void)
0x180044c49  lea     rcx, [rsp+28h+arg_0]
0x180044c4e  mov     byte ptr [rdi+29h], 1
0x180044c52  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180044c57  mov     rbx, [rsp+28h+arg_8]
0x180044c5c  add     rsp, 20h
0x180044c60  pop     rdi
0x180044c61  retn
```
