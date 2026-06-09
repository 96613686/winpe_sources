# wil::details::threadpool_timer_context::RequestRelease(wil::details::threadpool_timer_context *)

- ea: `0x180076b3c`
- end: `0x180076ba6`
- name: `?RequestRelease@threadpool_timer_context@details@wil@@SAXPEAU123@@Z`
- size: `106`
- prototype: `void __fastcall(struct wil::details::threadpool_timer_context *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180075c3c`
- `0x1800766a4`

## callees

- `0x180009a84`
- `0x1800761d4`
- `0x180076b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076b58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076b58`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180076b88`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180076b88`

## pseudocode

```c
void __fastcall wil::details::threadpool_timer_context::RequestRelease(
        struct wil::details::threadpool_timer_context *this)
{
  char *v1; // rbx
  char v3; // si
  bool v4; // zf
  unsigned int v5; // edx
  char *v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (char *)this + 88;
  v3 = 1;
  AcquireSRWLockExclusive((PSRWLOCK)this + 11);
  v4 = *((_DWORD *)this + 24) == 0;
  v6 = v1;
  if ( !v4 )
  {
    *((_BYTE *)this + 100) = 1;
    v3 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  if ( v3 )
  {
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 10), 1);
    wil::details::threadpool_timer_context::`scalar deleting destructor'(this, v5);
  }
}

```

## disassembly

```asm
0x180076b3c  mov     [rsp+arg_8], rbx
0x180076b41  mov     [rsp+arg_10], rsi
0x180076b46  push    rdi
0x180076b47  sub     rsp, 20h
0x180076b4b  lea     rbx, [rcx+58h]
0x180076b4f  mov     rdi, rcx
0x180076b52  mov     rcx, rbx; SRWLock
0x180076b55  mov     sil, 1
0x180076b58  call    cs:__imp_AcquireSRWLockExclusive
0x180076b5e  cmp     dword ptr [rdi+60h], 0
0x180076b62  mov     [rsp+28h+arg_0], rbx
0x180076b67  jz      short loc_180076B70
0x180076b69  mov     [rdi+64h], sil
0x180076b6d  xor     sil, sil
0x180076b70  lea     rcx, [rsp+28h+arg_0]
0x180076b75  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180076b7a  test    sil, sil
0x180076b7d  jz      short loc_180076B96
0x180076b7f  mov     rcx, [rdi+50h]; pti
0x180076b83  mov     edx, 1; fCancelPendingCallbacks
0x180076b88  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180076b8e  mov     rcx, rdi; this
0x180076b91  call    ??_Gthreadpool_timer_context@details@wil@@QEAAPEAXI@Z; wil::details::threadpool_timer_context::`scalar deleting destructor'(uint)
0x180076b96  mov     rbx, [rsp+28h+arg_8]
0x180076b9b  mov     rsi, [rsp+28h+arg_10]
0x180076ba0  add     rsp, 20h
0x180076ba4  pop     rdi
0x180076ba5  retn
```
