# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x180085084`
- end: `0x180085127`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180085c30`

## callees

- `0x1800153a0`
- `0x1800847ac`
- `0x180085084`
- `0x180085f84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800850a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800850a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085107`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085107`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800850d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800850d0`

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
0x180085084  mov     [rsp+arg_8], rbx
0x180085089  mov     [rsp+arg_10], rsi
0x18008508e  push    rdi
0x18008508f  sub     rsp, 20h
0x180085093  lea     rbx, [rcx+98h]
0x18008509a  mov     rdi, rcx
0x18008509d  mov     rcx, rbx; SRWLock
0x1800850a0  mov     sil, dl
0x1800850a3  call    cs:__imp_AcquireSRWLockExclusive
0x1800850a9  or      eax, 0FFFFFFFFh
0x1800850ac  mov     [rsp+28h+arg_0], rbx
0x1800850b1  lock xadd [rdi+94h], eax
0x1800850b9  cmp     eax, 1
0x1800850bc  jnz     short loc_1800850F1
0x1800850be  mov     rcx, [rdi+88h]; pwa
0x1800850c5  mov     qword ptr [rdi+88h], 0
0x1800850d0  call    cs:__imp_CloseThreadpoolWait
0x1800850d6  xor     edx, edx
0x1800850d8  lea     rcx, [rsp+28h+arg_0]
0x1800850dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x1800850e2  test    rdi, rdi
0x1800850e5  jz      short loc_18008510D
0x1800850e7  mov     rcx, rdi; this
0x1800850ea  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1800850ef  jmp     short loc_18008510D
0x1800850f1  test    sil, sil
0x1800850f4  jz      short loc_18008510D
0x1800850f6  mov     rdx, [rdi+80h]; h
0x1800850fd  xor     r8d, r8d; pftTimeout
0x180085100  mov     rcx, [rdi+88h]; pwa
0x180085107  call    cs:__imp_SetThreadpoolWait
0x18008510d  lea     rcx, [rsp+28h+arg_0]
0x180085112  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180085117  mov     rbx, [rsp+28h+arg_8]
0x18008511c  mov     rsi, [rsp+28h+arg_10]
0x180085121  add     rsp, 20h
0x180085125  pop     rdi
0x180085126  retn
```
