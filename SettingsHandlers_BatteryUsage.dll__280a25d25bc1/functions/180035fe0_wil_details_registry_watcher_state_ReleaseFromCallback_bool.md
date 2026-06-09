# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x180035fe0`
- end: `0x180036083`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800366d0`

## callees

- `0x18000607c`
- `0x180035118`
- `0x180035fe0`
- `0x180036a88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035fff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035fff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18003602c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18003602c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180036063`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180036063`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  RTL_SRWLOCK *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  unsigned int v6; // edx
  RTL_SRWLOCK *v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  v7 = v2;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v7,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'(this, v6);
  }
  else if ( a2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
}

```

## disassembly

```asm
0x180035fe0  mov     [rsp+arg_8], rbx
0x180035fe5  mov     [rsp+arg_10], rsi
0x180035fea  push    rdi
0x180035feb  sub     rsp, 20h
0x180035fef  lea     rbx, [rcx+98h]
0x180035ff6  mov     rdi, rcx
0x180035ff9  mov     rcx, rbx; SRWLock
0x180035ffc  mov     sil, dl
0x180035fff  call    cs:__imp_AcquireSRWLockExclusive
0x180036005  or      eax, 0FFFFFFFFh
0x180036008  mov     [rsp+28h+arg_0], rbx
0x18003600d  lock xadd [rdi+94h], eax
0x180036015  cmp     eax, 1
0x180036018  jnz     short loc_18003604D
0x18003601a  mov     rcx, [rdi+88h]; pwa
0x180036021  mov     qword ptr [rdi+88h], 0
0x18003602c  call    cs:__imp_CloseThreadpoolWait
0x180036032  xor     edx, edx
0x180036034  lea     rcx, [rsp+28h+arg_0]
0x180036039  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18003603e  test    rdi, rdi
0x180036041  jz      short loc_180036069
0x180036043  mov     rcx, rdi; this
0x180036046  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18003604b  jmp     short loc_180036069
0x18003604d  test    sil, sil
0x180036050  jz      short loc_180036069
0x180036052  mov     rdx, [rdi+80h]; h
0x180036059  xor     r8d, r8d; pftTimeout
0x18003605c  mov     rcx, [rdi+88h]; pwa
0x180036063  call    cs:__imp_SetThreadpoolWait
0x180036069  lea     rcx, [rsp+28h+arg_0]
0x18003606e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180036073  mov     rbx, [rsp+28h+arg_8]
0x180036078  mov     rsi, [rsp+28h+arg_10]
0x18003607d  add     rsp, 20h
0x180036081  pop     rdi
0x180036082  retn
```
