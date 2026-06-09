# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x18008541c`
- end: `0x1800854c8`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `172`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180068010`

## callees

- `0x18004f9dc`
- `0x180063024`
- `0x18008541c`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x1800854a4`
- `KERNEL32!SetThreadpoolWait` at `0x1800854a4`
- `KERNEL32!CloseThreadpoolWait` at `0x180085468`
- `KERNEL32!CloseThreadpoolWait` at `0x180085468`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800854b2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800854b2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18008543b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18008543b`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  RTL_SRWLOCK *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  unsigned int v6; // edx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  SRWLock = v2;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &SRWLock,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'(this, v6);
    v2 = SRWLock;
  }
  else if ( a2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x18008541c  mov     [rsp+arg_8], rbx
0x180085421  mov     [rsp+arg_10], rsi
0x180085426  push    rdi
0x180085427  sub     rsp, 20h
0x18008542b  lea     rbx, [rcx+98h]
0x180085432  mov     rdi, rcx
0x180085435  mov     rcx, rbx; SRWLock
0x180085438  mov     sil, dl
0x18008543b  call    cs:__imp_AcquireSRWLockExclusive
0x180085441  or      eax, 0FFFFFFFFh
0x180085444  mov     [rsp+28h+SRWLock], rbx
0x180085449  lock xadd [rdi+94h], eax
0x180085451  cmp     eax, 1
0x180085454  jnz     short loc_18008548E
0x180085456  mov     rcx, [rdi+88h]; pwa
0x18008545d  mov     qword ptr [rdi+88h], 0
0x180085468  call    cs:__imp_CloseThreadpoolWait
0x18008546e  xor     edx, edx
0x180085470  lea     rcx, [rsp+28h+SRWLock]
0x180085475  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18008547a  test    rdi, rdi
0x18008547d  jz      short loc_180085487
0x18008547f  mov     rcx, rdi; this
0x180085482  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180085487  mov     rbx, [rsp+28h+SRWLock]
0x18008548c  jmp     short loc_1800854AA
0x18008548e  test    sil, sil
0x180085491  jz      short loc_1800854AA
0x180085493  mov     rdx, [rdi+80h]; h
0x18008549a  xor     r8d, r8d; pftTimeout
0x18008549d  mov     rcx, [rdi+88h]; pwa
0x1800854a4  call    cs:__imp_SetThreadpoolWait
0x1800854aa  test    rbx, rbx
0x1800854ad  jz      short loc_1800854B8
0x1800854af  mov     rcx, rbx; SRWLock
0x1800854b2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800854b8  mov     rbx, [rsp+28h+arg_8]
0x1800854bd  mov     rsi, [rsp+28h+arg_10]
0x1800854c2  add     rsp, 20h
0x1800854c6  pop     rdi
0x1800854c7  retn
```
