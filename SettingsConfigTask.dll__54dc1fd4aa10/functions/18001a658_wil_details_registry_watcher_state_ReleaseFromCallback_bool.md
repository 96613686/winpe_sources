# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x18001a658`
- end: `0x18001a6fb`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d240`

## callees

- `0x18000460c`
- `0x180013588`
- `0x18001a658`
- `0x180020104`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a677`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a677`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001a6db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001a6db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001a6a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001a6a4`

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
0x18001a658  mov     [rsp+arg_8], rbx
0x18001a65d  mov     [rsp+arg_10], rsi
0x18001a662  push    rdi
0x18001a663  sub     rsp, 20h
0x18001a667  lea     rbx, [rcx+98h]
0x18001a66e  mov     rdi, rcx
0x18001a671  mov     rcx, rbx; SRWLock
0x18001a674  mov     sil, dl
0x18001a677  call    cs:__imp_AcquireSRWLockExclusive
0x18001a67d  or      eax, 0FFFFFFFFh
0x18001a680  mov     [rsp+28h+arg_0], rbx
0x18001a685  lock xadd [rdi+94h], eax
0x18001a68d  cmp     eax, 1
0x18001a690  jnz     short loc_18001A6C5
0x18001a692  mov     rcx, [rdi+88h]; pwa
0x18001a699  mov     qword ptr [rdi+88h], 0
0x18001a6a4  call    cs:__imp_CloseThreadpoolWait
0x18001a6aa  xor     edx, edx
0x18001a6ac  lea     rcx, [rsp+28h+arg_0]
0x18001a6b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18001a6b6  test    rdi, rdi
0x18001a6b9  jz      short loc_18001A6E1
0x18001a6bb  mov     rcx, rdi; this
0x18001a6be  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18001a6c3  jmp     short loc_18001A6E1
0x18001a6c5  test    sil, sil
0x18001a6c8  jz      short loc_18001A6E1
0x18001a6ca  mov     rdx, [rdi+80h]; h
0x18001a6d1  xor     r8d, r8d; pftTimeout
0x18001a6d4  mov     rcx, [rdi+88h]; pwa
0x18001a6db  call    cs:__imp_SetThreadpoolWait
0x18001a6e1  lea     rcx, [rsp+28h+arg_0]
0x18001a6e6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001a6eb  mov     rbx, [rsp+28h+arg_8]
0x18001a6f0  mov     rsi, [rsp+28h+arg_10]
0x18001a6f5  add     rsp, 20h
0x18001a6f9  pop     rdi
0x18001a6fa  retn
```
