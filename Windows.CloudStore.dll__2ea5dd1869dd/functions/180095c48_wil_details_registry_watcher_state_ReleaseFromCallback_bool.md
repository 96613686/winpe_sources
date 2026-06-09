# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x180095c48`
- end: `0x180095cf4`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `172`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180095b90`
- `0x18010d360`

## callees

- `0x1800426a8`
- `0x180095c48`
- `0x1800ac31c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolWait` at `0x180095cce`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolWait` at `0x180095cce`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolWait` at `0x180095c98`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolWait` at `0x180095c98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180095c67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180095c67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095ca6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180095ca6`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  RTL_SRWLOCK *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  unsigned int v6; // edx
  RTL_SRWLOCK *v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
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
    v2 = v7;
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
0x180095c48  mov     [rsp+arg_8], rbx
0x180095c4d  mov     [rsp+arg_10], rsi
0x180095c52  push    rdi
0x180095c53  sub     rsp, 20h
0x180095c57  lea     rbx, [rcx+98h]
0x180095c5e  mov     rdi, rcx
0x180095c61  mov     rcx, rbx; SRWLock
0x180095c64  mov     sil, dl
0x180095c67  call    cs:__imp_AcquireSRWLockExclusive
0x180095c6d  or      eax, 0FFFFFFFFh
0x180095c70  mov     [rsp+28h+arg_0], rbx
0x180095c75  lock xadd [rdi+94h], eax
0x180095c7d  cmp     eax, 1
0x180095c80  jz      short loc_180095CBC
0x180095c82  test    sil, sil
0x180095c85  jz      short loc_180095C9E
0x180095c87  mov     rdx, [rdi+80h]; h
0x180095c8e  xor     r8d, r8d; pftTimeout
0x180095c91  mov     rcx, [rdi+88h]; pwa
0x180095c98  call    cs:__imp_SetThreadpoolWait
0x180095c9e  test    rbx, rbx
0x180095ca1  jz      short loc_180095CAC
0x180095ca3  mov     rcx, rbx; SRWLock
0x180095ca6  call    cs:__imp_ReleaseSRWLockExclusive
0x180095cac  mov     rbx, [rsp+28h+arg_8]
0x180095cb1  mov     rsi, [rsp+28h+arg_10]
0x180095cb6  add     rsp, 20h
0x180095cba  pop     rdi
0x180095cbb  retn
0x180095cbc  mov     rcx, [rdi+88h]; pwa
0x180095cc3  mov     qword ptr [rdi+88h], 0
0x180095cce  call    cs:__imp_CloseThreadpoolWait
0x180095cd4  xor     edx, edx
0x180095cd6  lea     rcx, [rsp+28h+arg_0]
0x180095cdb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180095ce0  test    rdi, rdi
0x180095ce3  jz      short loc_180095CED
0x180095ce5  mov     rcx, rdi; this
0x180095ce8  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180095ced  mov     rbx, [rsp+28h+arg_0]
0x180095cf2  jmp     short loc_180095C9E
```
