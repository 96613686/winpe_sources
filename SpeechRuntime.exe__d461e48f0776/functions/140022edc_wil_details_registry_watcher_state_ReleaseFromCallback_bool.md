# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x140022edc`
- end: `0x140022f7f`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140023cf0`

## callees

- `0x140007fa8`
- `0x14002207c`
- `0x140022edc`
- `0x140024204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140022efb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140022efb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140022f5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140022f5f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140022f28`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140022f28`

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
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
}

```

## disassembly

```asm
0x140022edc  mov     [rsp+arg_8], rbx
0x140022ee1  mov     [rsp+arg_10], rsi
0x140022ee6  push    rdi
0x140022ee7  sub     rsp, 20h
0x140022eeb  lea     rbx, [rcx+98h]
0x140022ef2  mov     rdi, rcx
0x140022ef5  mov     rcx, rbx; SRWLock
0x140022ef8  mov     sil, dl
0x140022efb  call    cs:__imp_AcquireSRWLockExclusive
0x140022f01  or      eax, 0FFFFFFFFh
0x140022f04  mov     [rsp+28h+arg_0], rbx
0x140022f09  lock xadd [rdi+94h], eax
0x140022f11  cmp     eax, 1
0x140022f14  jnz     short loc_140022F49
0x140022f16  mov     rcx, [rdi+88h]; pwa
0x140022f1d  mov     qword ptr [rdi+88h], 0
0x140022f28  call    cs:__imp_CloseThreadpoolWait
0x140022f2e  xor     edx, edx
0x140022f30  lea     rcx, [rsp+28h+arg_0]
0x140022f35  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x140022f3a  test    rdi, rdi
0x140022f3d  jz      short loc_140022F65
0x140022f3f  mov     rcx, rdi; this
0x140022f42  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x140022f47  jmp     short loc_140022F65
0x140022f49  test    sil, sil
0x140022f4c  jz      short loc_140022F65
0x140022f4e  mov     rdx, [rdi+80h]; h
0x140022f55  xor     r8d, r8d; pftTimeout
0x140022f58  mov     rcx, [rdi+88h]; pwa
0x140022f5f  call    cs:__imp_SetThreadpoolWait
0x140022f65  lea     rcx, [rsp+28h+arg_0]
0x140022f6a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140022f6f  mov     rbx, [rsp+28h+arg_8]
0x140022f74  mov     rsi, [rsp+28h+arg_10]
0x140022f79  add     rsp, 20h
0x140022f7d  pop     rdi
0x140022f7e  retn
```
