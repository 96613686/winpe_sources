# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x1800538dc`
- end: `0x18005397f`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029980`

## callees

- `0x18000dae4`
- `0x180014aa0`
- `0x18001ff80`
- `0x1800538dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800538fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800538fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180053928`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180053928`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005395f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005395f`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  char *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  unsigned int v6; // edx
  char *v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = (char *)this + 152;
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
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v7);
}

```

## disassembly

```asm
0x1800538dc  mov     [rsp+arg_8], rbx
0x1800538e1  mov     [rsp+arg_10], rsi
0x1800538e6  push    rdi
0x1800538e7  sub     rsp, 20h
0x1800538eb  lea     rbx, [rcx+98h]
0x1800538f2  mov     rdi, rcx
0x1800538f5  mov     rcx, rbx; SRWLock
0x1800538f8  mov     sil, dl
0x1800538fb  call    cs:__imp_AcquireSRWLockExclusive
0x180053901  or      eax, 0FFFFFFFFh
0x180053904  mov     [rsp+28h+arg_0], rbx
0x180053909  lock xadd [rdi+94h], eax
0x180053911  cmp     eax, 1
0x180053914  jnz     short loc_180053949
0x180053916  mov     rcx, [rdi+88h]; pwa
0x18005391d  mov     qword ptr [rdi+88h], 0
0x180053928  call    cs:__imp_CloseThreadpoolWait
0x18005392e  xor     edx, edx
0x180053930  lea     rcx, [rsp+28h+arg_0]
0x180053935  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18005393a  test    rdi, rdi
0x18005393d  jz      short loc_180053965
0x18005393f  mov     rcx, rdi; this
0x180053942  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180053947  jmp     short loc_180053965
0x180053949  test    sil, sil
0x18005394c  jz      short loc_180053965
0x18005394e  mov     rdx, [rdi+80h]; h
0x180053955  xor     r8d, r8d; pftTimeout
0x180053958  mov     rcx, [rdi+88h]; pwa
0x18005395f  call    cs:__imp_SetThreadpoolWait
0x180053965  lea     rcx, [rsp+28h+arg_0]
0x18005396a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005396f  mov     rbx, [rsp+28h+arg_8]
0x180053974  mov     rsi, [rsp+28h+arg_10]
0x180053979  add     rsp, 20h
0x18005397d  pop     rdi
0x18005397e  retn
```
