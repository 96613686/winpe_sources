# wil::details::threadpool_wait_context::RequestRelease(wil::details::threadpool_wait_context *)

- ea: `0x180054e98`
- end: `0x180054eff`
- name: `?RequestRelease@threadpool_wait_context@details@wil@@SAXPEAU123@@Z`
- size: `103`
- prototype: `void __fastcall(struct wil::details::threadpool_wait_context *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800528a0`
- `0x180055c80`

## callees

- `0x180004060`
- `0x18005339c`
- `0x180054e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054eb4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054eb4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180054ee1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180054ee1`

## pseudocode

```c
void __fastcall wil::details::threadpool_wait_context::RequestRelease(
        struct wil::details::threadpool_wait_context *this)
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
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 10), 0);
    wil::details::threadpool_wait_context::`scalar deleting destructor'(this, v5);
  }
}

```

## disassembly

```asm
0x180054e98  mov     [rsp+arg_8], rbx
0x180054e9d  mov     [rsp+arg_10], rsi
0x180054ea2  push    rdi
0x180054ea3  sub     rsp, 20h
0x180054ea7  lea     rbx, [rcx+58h]
0x180054eab  mov     rdi, rcx
0x180054eae  mov     rcx, rbx; SRWLock
0x180054eb1  mov     sil, 1
0x180054eb4  call    cs:__imp_AcquireSRWLockExclusive
0x180054eba  cmp     dword ptr [rdi+60h], 0
0x180054ebe  mov     [rsp+28h+arg_0], rbx
0x180054ec3  jz      short loc_180054ECC
0x180054ec5  mov     [rdi+64h], sil
0x180054ec9  xor     sil, sil
0x180054ecc  lea     rcx, [rsp+28h+arg_0]
0x180054ed1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180054ed6  test    sil, sil
0x180054ed9  jz      short loc_180054EEF
0x180054edb  mov     rcx, [rdi+50h]; pwa
0x180054edf  xor     edx, edx; fCancelPendingCallbacks
0x180054ee1  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180054ee7  mov     rcx, rdi; this
0x180054eea  call    ??_Gthreadpool_wait_context@details@wil@@QEAAPEAXI@Z; wil::details::threadpool_wait_context::`scalar deleting destructor'(uint)
0x180054eef  mov     rbx, [rsp+28h+arg_8]
0x180054ef4  mov     rsi, [rsp+28h+arg_10]
0x180054ef9  add     rsp, 20h
0x180054efd  pop     rdi
0x180054efe  retn
```
