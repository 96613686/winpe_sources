# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x18000e984`
- end: `0x18000ea27`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010780`

## callees

- `0x180004b18`
- `0x18000dcfc`
- `0x18000e984`
- `0x180011440`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e9a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e9a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e9d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e9d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000ea07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000ea07`

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
0x18000e984  mov     [rsp+arg_8], rbx
0x18000e989  mov     [rsp+arg_10], rsi
0x18000e98e  push    rdi
0x18000e98f  sub     rsp, 20h
0x18000e993  lea     rbx, [rcx+98h]
0x18000e99a  mov     rdi, rcx
0x18000e99d  mov     rcx, rbx; SRWLock
0x18000e9a0  mov     sil, dl
0x18000e9a3  call    cs:__imp_AcquireSRWLockExclusive
0x18000e9a9  or      eax, 0FFFFFFFFh
0x18000e9ac  mov     [rsp+28h+arg_0], rbx
0x18000e9b1  lock xadd [rdi+94h], eax
0x18000e9b9  cmp     eax, 1
0x18000e9bc  jnz     short loc_18000E9F1
0x18000e9be  mov     rcx, [rdi+88h]; pwa
0x18000e9c5  mov     qword ptr [rdi+88h], 0
0x18000e9d0  call    cs:__imp_CloseThreadpoolWait
0x18000e9d6  xor     edx, edx
0x18000e9d8  lea     rcx, [rsp+28h+arg_0]
0x18000e9dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18000e9e2  test    rdi, rdi
0x18000e9e5  jz      short loc_18000EA0D
0x18000e9e7  mov     rcx, rdi; this
0x18000e9ea  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18000e9ef  jmp     short loc_18000EA0D
0x18000e9f1  test    sil, sil
0x18000e9f4  jz      short loc_18000EA0D
0x18000e9f6  mov     rdx, [rdi+80h]; h
0x18000e9fd  xor     r8d, r8d; pftTimeout
0x18000ea00  mov     rcx, [rdi+88h]; pwa
0x18000ea07  call    cs:__imp_SetThreadpoolWait
0x18000ea0d  lea     rcx, [rsp+28h+arg_0]
0x18000ea12  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ea17  mov     rbx, [rsp+28h+arg_8]
0x18000ea1c  mov     rsi, [rsp+28h+arg_10]
0x18000ea21  add     rsp, 20h
0x18000ea25  pop     rdi
0x18000ea26  retn
```
