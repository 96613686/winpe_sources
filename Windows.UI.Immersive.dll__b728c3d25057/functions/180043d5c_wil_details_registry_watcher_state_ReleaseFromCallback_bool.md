# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x180043d5c`
- end: `0x180043e08`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `172`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180029630`

## callees

- `0x180008000`
- `0x180043d5c`
- `0x18006b9b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043df2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043df2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043d7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043d7b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180043da8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180043da8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180043de4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180043de4`

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
0x180043d5c  mov     [rsp+arg_8], rbx
0x180043d61  mov     [rsp+arg_10], rsi
0x180043d66  push    rdi
0x180043d67  sub     rsp, 20h
0x180043d6b  lea     rbx, [rcx+98h]
0x180043d72  mov     rdi, rcx
0x180043d75  mov     rcx, rbx; SRWLock
0x180043d78  mov     sil, dl
0x180043d7b  call    cs:__imp_AcquireSRWLockExclusive
0x180043d81  or      eax, 0FFFFFFFFh
0x180043d84  mov     [rsp+28h+SRWLock], rbx
0x180043d89  lock xadd [rdi+94h], eax
0x180043d91  cmp     eax, 1
0x180043d94  jnz     short loc_180043DCE
0x180043d96  mov     rcx, [rdi+88h]; pwa
0x180043d9d  mov     qword ptr [rdi+88h], 0
0x180043da8  call    cs:__imp_CloseThreadpoolWait
0x180043dae  xor     edx, edx
0x180043db0  lea     rcx, [rsp+28h+SRWLock]
0x180043db5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180043dba  test    rdi, rdi
0x180043dbd  jz      short loc_180043DC7
0x180043dbf  mov     rcx, rdi; this
0x180043dc2  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180043dc7  mov     rbx, [rsp+28h+SRWLock]
0x180043dcc  jmp     short loc_180043DEA
0x180043dce  test    sil, sil
0x180043dd1  jz      short loc_180043DEA
0x180043dd3  mov     rdx, [rdi+80h]; h
0x180043dda  xor     r8d, r8d; pftTimeout
0x180043ddd  mov     rcx, [rdi+88h]; pwa
0x180043de4  call    cs:__imp_SetThreadpoolWait
0x180043dea  test    rbx, rbx
0x180043ded  jz      short loc_180043DF8
0x180043def  mov     rcx, rbx; SRWLock
0x180043df2  call    cs:__imp_ReleaseSRWLockExclusive
0x180043df8  mov     rbx, [rsp+28h+arg_8]
0x180043dfd  mov     rsi, [rsp+28h+arg_10]
0x180043e02  add     rsp, 20h
0x180043e06  pop     rdi
0x180043e07  retn
```
