# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x18001ba70`
- end: `0x18001bb26`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `182`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180020270`

## callees

- `0x18000468c`
- `0x180011ff0`
- `0x18001ba70`
- `0x180021dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ba8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ba8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001bac2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001bac2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001baff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001baff`

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
0x18001ba70  mov     [rsp+arg_8], rbx
0x18001ba75  mov     [rsp+arg_10], rsi
0x18001ba7a  push    rdi
0x18001ba7b  sub     rsp, 20h
0x18001ba7f  lea     rbx, [rcx+98h]
0x18001ba86  mov     rdi, rcx
0x18001ba89  mov     rcx, rbx; SRWLock
0x18001ba8c  mov     sil, dl
0x18001ba8f  call    cs:__imp_AcquireSRWLockExclusive
0x18001ba96  nop     dword ptr [rax+rax+00h]
0x18001ba9b  or      eax, 0FFFFFFFFh
0x18001ba9e  mov     [rsp+28h+arg_0], rbx
0x18001baa3  lock xadd [rdi+94h], eax
0x18001baab  cmp     eax, 1
0x18001baae  jnz     short loc_18001BAE9
0x18001bab0  mov     rcx, [rdi+88h]; pwa
0x18001bab7  mov     qword ptr [rdi+88h], 0
0x18001bac2  call    cs:__imp_CloseThreadpoolWait
0x18001bac9  nop     dword ptr [rax+rax+00h]
0x18001bace  xor     edx, edx
0x18001bad0  lea     rcx, [rsp+28h+arg_0]
0x18001bad5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18001bada  test    rdi, rdi
0x18001badd  jz      short loc_18001BB0B
0x18001badf  mov     rcx, rdi; this
0x18001bae2  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18001bae7  jmp     short loc_18001BB0B
0x18001bae9  test    sil, sil
0x18001baec  jz      short loc_18001BB0B
0x18001baee  mov     rdx, [rdi+80h]; h
0x18001baf5  xor     r8d, r8d; pftTimeout
0x18001baf8  mov     rcx, [rdi+88h]; pwa
0x18001baff  call    cs:__imp_SetThreadpoolWait
0x18001bb06  nop     dword ptr [rax+rax+00h]
0x18001bb0b  lea     rcx, [rsp+28h+arg_0]
0x18001bb10  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001bb15  mov     rbx, [rsp+28h+arg_8]
0x18001bb1a  mov     rsi, [rsp+28h+arg_10]
0x18001bb1f  add     rsp, 20h
0x18001bb23  pop     rdi
0x18001bb24  retn
```
