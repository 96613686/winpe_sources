# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x1800463a8`
- end: `0x18004644b`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800464a0`

## callees

- `0x18000b508`
- `0x1800460ac`
- `0x1800463a8`
- `0x180046748`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800463c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800463c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004642b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004642b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800463f4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800463f4`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  RTL_SRWLOCK *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  v6 = v2;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v6,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'((struct _TP_WAIT **)this);
  }
  else if ( a2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
}

```

## disassembly

```asm
0x1800463a8  mov     [rsp+arg_8], rbx
0x1800463ad  mov     [rsp+arg_10], rsi
0x1800463b2  push    rdi
0x1800463b3  sub     rsp, 20h
0x1800463b7  lea     rbx, [rcx+98h]
0x1800463be  mov     rdi, rcx
0x1800463c1  mov     rcx, rbx; SRWLock
0x1800463c4  mov     sil, dl
0x1800463c7  call    cs:__imp_AcquireSRWLockExclusive
0x1800463cd  or      eax, 0FFFFFFFFh
0x1800463d0  mov     [rsp+28h+arg_0], rbx
0x1800463d5  lock xadd [rdi+94h], eax
0x1800463dd  cmp     eax, 1
0x1800463e0  jnz     short loc_180046415
0x1800463e2  mov     rcx, [rdi+88h]; pwa
0x1800463e9  mov     qword ptr [rdi+88h], 0
0x1800463f4  call    cs:__imp_CloseThreadpoolWait
0x1800463fa  xor     edx, edx
0x1800463fc  lea     rcx, [rsp+28h+arg_0]
0x180046401  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180046406  test    rdi, rdi
0x180046409  jz      short loc_180046431
0x18004640b  mov     rcx, rdi; this
0x18004640e  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180046413  jmp     short loc_180046431
0x180046415  test    sil, sil
0x180046418  jz      short loc_180046431
0x18004641a  mov     rdx, [rdi+80h]; h
0x180046421  xor     r8d, r8d; pftTimeout
0x180046424  mov     rcx, [rdi+88h]; pwa
0x18004642b  call    cs:__imp_SetThreadpoolWait
0x180046431  lea     rcx, [rsp+28h+arg_0]
0x180046436  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004643b  mov     rbx, [rsp+28h+arg_8]
0x180046440  mov     rsi, [rsp+28h+arg_10]
0x180046445  add     rsp, 20h
0x180046449  pop     rdi
0x18004644a  retn
```
