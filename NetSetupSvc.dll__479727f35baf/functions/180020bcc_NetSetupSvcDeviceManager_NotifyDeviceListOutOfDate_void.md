# NetSetupSvcDeviceManager::NotifyDeviceListOutOfDate(void)

- ea: `0x180020bcc`
- end: `0x180020c20`
- name: `?NotifyDeviceListOutOfDate@NetSetupSvcDeviceManager@@QEAAXXZ`
- size: `84`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18000a6d4`
- `0x1800102bc`
- `0x180012714`
- `0x180025160`

## callees

- `0x180008eb8`
- `0x180020bcc`
- `0x180022e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020be0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020be0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180020c0f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180020c0f`

## pseudocode

```c
void __fastcall NetSetupSvcDeviceManager::NotifyDeviceListOutOfDate(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rbx
  wil::details *Ptr; // rcx
  void *v4; // rdx
  RTL_SRWLOCK *v5; // [rsp+20h] [rbp-18h] BYREF

  v1 = this + 4;
  AcquireSRWLockExclusive(this + 4);
  Ptr = (wil::details *)this[2].Ptr;
  v5 = v1;
  wil::details::ResetEvent(Ptr, v4);
  LODWORD(v1) = this[1].Ptr;
  LODWORD(this[1].Ptr) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
  if ( !(_DWORD)v1 )
    SubmitThreadpoolWork((PTP_WORK)this->Ptr);
}

```

## disassembly

```asm
0x180020bcc  mov     [rsp+arg_8], rbx
0x180020bd1  push    rdi
0x180020bd2  sub     rsp, 30h
0x180020bd6  lea     rbx, [rcx+20h]
0x180020bda  mov     rdi, rcx
0x180020bdd  mov     rcx, rbx; SRWLock
0x180020be0  call    cs:__imp_AcquireSRWLockExclusive
0x180020be6  mov     rcx, [rdi+10h]; this
0x180020bea  mov     [rsp+38h+var_18], rbx
0x180020bef  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x180020bf4  mov     ebx, [rdi+8]
0x180020bf7  lea     rcx, [rsp+38h+var_18]
0x180020bfc  mov     dword ptr [rdi+8], 1
0x180020c03  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180020c08  test    ebx, ebx
0x180020c0a  jnz     short loc_180020C15
0x180020c0c  mov     rcx, [rdi]; pwk
0x180020c0f  call    cs:__imp_SubmitThreadpoolWork
0x180020c15  mov     rbx, [rsp+38h+arg_8]
0x180020c1a  add     rsp, 30h
0x180020c1e  pop     rdi
0x180020c1f  retn
```
