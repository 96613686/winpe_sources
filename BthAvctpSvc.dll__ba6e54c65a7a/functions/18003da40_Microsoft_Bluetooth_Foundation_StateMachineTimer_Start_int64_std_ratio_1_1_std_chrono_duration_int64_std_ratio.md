# Microsoft::Bluetooth::Foundation::StateMachineTimer::Start<__int64,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,1>> const &,wistd::function<void (void)> &&)

- ea: `0x18003da40`
- end: `0x18003db19`
- name: `??$Start@_JU?$ratio@$00$00@std@@@StateMachineTimer@Foundation@Bluetooth@Microsoft@@QEAAXAEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `217`
- prototype: `BOOL __fastcall(__int64, struct _FILETIME, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041708`

## callees

- `0x1800039c0`
- `0x180004060`
- `0x18000b604`
- `0x18002e8b0`
- `0x18003da40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003da61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003da61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18003dad3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18003dad3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003da8d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003da8d`

## string_xrefs

- `0x18003dafb`: `Cannot start if start already started.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
BOOL __fastcall Microsoft::Bluetooth::Foundation::StateMachineTimer::Start<__int64,std::ratio<1,1>>(
        __int64 a1,
        struct _FILETIME a2,
        __int64 a3)
{
  struct _FILETIME v5; // rbx
  unsigned int v7; // eax
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp+10h] BYREF

  pftDueTime = a2;
  v5 = (struct _FILETIME)(a1 + 32);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
  pftDueTime = v5;
  if ( *(_BYTE *)(a1 + 40) )
  {
    v7 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\StateMachines.h",
      (const char *)v7,
      (int)"Cannot start if start already started.",
      v8);
  }
  *(_BYTE *)(a1 + 40) = 1;
  *(_BYTE *)(a1 + 168) = 1;
  *(_QWORD *)(a1 + 184) = 0;
  QueryPerformanceCounter((LARGE_INTEGER *)(a1 + 176));
  wistd::function<void (void)>::operator=(a1 + 48, a3);
  *(_QWORD *)(a1 + 192) = 30000;
  *(_BYTE *)(a1 + 41) = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&pftDueTime);
  pftDueTime = (struct _FILETIME)-300000000LL;
  return SetThreadpoolTimerEx(*(PTP_TIMER *)(*(_QWORD *)(a1 + 24) + 80LL), &pftDueTime, 0, 0);
}

```

## disassembly

```asm
0x18003da40  mov     [rsp+arg_0], rbx
0x18003da45  mov     [rsp+arg_10], rsi
0x18003da4a  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], rdx
0x18003da4f  push    rdi
0x18003da50  sub     rsp, 30h
0x18003da54  mov     rsi, r8
0x18003da57  mov     rdi, rcx
0x18003da5a  lea     rbx, [rcx+20h]
0x18003da5e  mov     rcx, rbx; SRWLock
0x18003da61  call    cs:__imp_AcquireSRWLockExclusive
0x18003da67  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rbx
0x18003da6c  xor     ebx, ebx
0x18003da6e  cmp     [rdi+28h], bl
0x18003da71  jnz     short loc_18003DAE9
0x18003da73  lea     eax, [rbx+1]
0x18003da76  mov     [rdi+28h], al
0x18003da79  xchg    al, [rdi+0A8h]
0x18003da7f  mov     [rdi+0B8h], rbx
0x18003da86  lea     rcx, [rdi+0B0h]; lpPerformanceCount
0x18003da8d  call    cs:__imp_QueryPerformanceCounter
0x18003da93  lea     rcx, [rdi+30h]
0x18003da97  mov     rdx, rsi
0x18003da9a  call    ??4?$function@$$A6AXXZ@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::function<void (void)>::operator=(wistd::function<void (void)> &&)
0x18003da9f  mov     qword ptr [rdi+0C0h], 7530h
0x18003daaa  mov     [rdi+29h], bl
0x18003daad  lea     rcx, [rsp+38h+pftDueTime]
0x18003dab2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003dab7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x18003dac0  mov     rcx, [rdi+18h]
0x18003dac4  xor     r9d, r9d; msWindowLength
0x18003dac7  xor     r8d, r8d; msPeriod
0x18003daca  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18003dacf  mov     rcx, [rcx+50h]; pti
0x18003dad3  call    cs:__imp_SetThreadpoolTimerEx
0x18003dad9  mov     rbx, [rsp+38h+arg_0]
0x18003dade  mov     rsi, [rsp+38h+arg_10]
0x18003dae3  add     rsp, 30h
0x18003dae7  pop     rdi
0x18003dae8  retn
0x18003dae9  mov     ecx, 8000FFFFh
0x18003daee  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003daf3  mov     r9d, eax; char *
0x18003daf6  mov     rcx, [rsp+38h]; this
0x18003dafb  lea     rax, aCannotStartIfS; "Cannot start if start already started."
0x18003db02  mov     qword ptr [rsp+38h+var_18], rax; int
0x18003db07  lea     r8, aOnecorePrivate_1; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18003db0e  mov     edx, 3Ch ; '<'; void *
0x18003db13  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
