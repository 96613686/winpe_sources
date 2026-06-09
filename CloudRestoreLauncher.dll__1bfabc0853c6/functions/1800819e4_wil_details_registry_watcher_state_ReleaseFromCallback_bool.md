# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x1800819e4`
- end: `0x180081a87`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800823c0`

## callees

- `0x1800166e8`
- `0x18006dc7c`
- `0x180072ad4`
- `0x1800819e4`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180081a03`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180081a03`
- `KERNEL32!SetThreadpoolWait` at `0x180081a67`
- `KERNEL32!SetThreadpoolWait` at `0x180081a67`
- `KERNEL32!CloseThreadpoolWait` at `0x180081a30`
- `KERNEL32!CloseThreadpoolWait` at `0x180081a30`

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
0x1800819e4  mov     [rsp+arg_8], rbx
0x1800819e9  mov     [rsp+arg_10], rsi
0x1800819ee  push    rdi
0x1800819ef  sub     rsp, 20h
0x1800819f3  lea     rbx, [rcx+98h]
0x1800819fa  mov     rdi, rcx
0x1800819fd  mov     rcx, rbx; SRWLock
0x180081a00  mov     sil, dl
0x180081a03  call    cs:__imp_AcquireSRWLockExclusive
0x180081a09  or      eax, 0FFFFFFFFh
0x180081a0c  mov     [rsp+28h+arg_0], rbx
0x180081a11  lock xadd [rdi+94h], eax
0x180081a19  cmp     eax, 1
0x180081a1c  jnz     short loc_180081A51
0x180081a1e  mov     rcx, [rdi+88h]; pwa
0x180081a25  mov     qword ptr [rdi+88h], 0
0x180081a30  call    cs:__imp_CloseThreadpoolWait
0x180081a36  xor     edx, edx
0x180081a38  lea     rcx, [rsp+28h+arg_0]
0x180081a3d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180081a42  test    rdi, rdi
0x180081a45  jz      short loc_180081A6D
0x180081a47  mov     rcx, rdi; this
0x180081a4a  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180081a4f  jmp     short loc_180081A6D
0x180081a51  test    sil, sil
0x180081a54  jz      short loc_180081A6D
0x180081a56  mov     rdx, [rdi+80h]; h
0x180081a5d  xor     r8d, r8d; pftTimeout
0x180081a60  mov     rcx, [rdi+88h]; pwa
0x180081a67  call    cs:__imp_SetThreadpoolWait
0x180081a6d  lea     rcx, [rsp+28h+arg_0]
0x180081a72  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180081a77  mov     rbx, [rsp+28h+arg_8]
0x180081a7c  mov     rsi, [rsp+28h+arg_10]
0x180081a81  add     rsp, 20h
0x180081a85  pop     rdi
0x180081a86  retn
```
