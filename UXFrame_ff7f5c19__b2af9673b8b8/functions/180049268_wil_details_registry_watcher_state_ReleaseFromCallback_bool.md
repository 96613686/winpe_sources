# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x180049268`
- end: `0x18004930b`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004ee60`

## callees

- `0x18000e2a0`
- `0x18000f1d8`
- `0x18001a7d0`
- `0x180049268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049287`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049287`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800492b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800492b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800492eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800492eb`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  char *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  unsigned int v6; // edx
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = (char *)this + 152;
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  v7[0] = v2;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      v7,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'(this, v6);
  }
  else if ( a2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v7);
}

```

## disassembly

```asm
0x180049268  mov     [rsp+arg_8], rbx
0x18004926d  mov     [rsp+arg_10], rsi
0x180049272  push    rdi
0x180049273  sub     rsp, 30h
0x180049277  lea     rbx, [rcx+98h]
0x18004927e  mov     rdi, rcx
0x180049281  mov     rcx, rbx; SRWLock
0x180049284  mov     sil, dl
0x180049287  call    cs:__imp_AcquireSRWLockExclusive
0x18004928d  or      eax, 0FFFFFFFFh
0x180049290  mov     [rsp+38h+var_18], rbx
0x180049295  lock xadd [rdi+94h], eax
0x18004929d  cmp     eax, 1
0x1800492a0  jnz     short loc_1800492D5
0x1800492a2  mov     rcx, [rdi+88h]; pwa
0x1800492a9  mov     qword ptr [rdi+88h], 0
0x1800492b4  call    cs:__imp_CloseThreadpoolWait
0x1800492ba  xor     edx, edx
0x1800492bc  lea     rcx, [rsp+38h+var_18]
0x1800492c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x1800492c6  test    rdi, rdi
0x1800492c9  jz      short loc_1800492F1
0x1800492cb  mov     rcx, rdi; this
0x1800492ce  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1800492d3  jmp     short loc_1800492F1
0x1800492d5  test    sil, sil
0x1800492d8  jz      short loc_1800492F1
0x1800492da  mov     rdx, [rdi+80h]; h
0x1800492e1  xor     r8d, r8d; pftTimeout
0x1800492e4  mov     rcx, [rdi+88h]; pwa
0x1800492eb  call    cs:__imp_SetThreadpoolWait
0x1800492f1  lea     rcx, [rsp+38h+var_18]
0x1800492f6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800492fb  mov     rbx, [rsp+38h+arg_8]
0x180049300  mov     rsi, [rsp+38h+arg_10]
0x180049305  add     rsp, 30h
0x180049309  pop     rdi
0x18004930a  retn
```
