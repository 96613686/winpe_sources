# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x18001fb5c`
- end: `0x18001fbff`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `163`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c7a0`

## callees

- `0x18000bdec`
- `0x180011904`
- `0x18001fb5c`
- `0x180022c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fb7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fb7b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001fbdf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001fbdf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001fba8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001fba8`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  char *v2; // rbx
  struct _TP_WAIT *v5; // rcx
  unsigned int v6; // edx
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = (char *)this + 152;
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  v7[0] = v2;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      v7,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'(this, v6);
  }
  else if ( a2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v7);
}

```

## disassembly

```asm
0x18001fb5c  mov     [rsp+arg_8], rbx
0x18001fb61  mov     [rsp+arg_10], rsi
0x18001fb66  push    rdi
0x18001fb67  sub     rsp, 30h
0x18001fb6b  lea     rbx, [rcx+98h]
0x18001fb72  mov     rdi, rcx
0x18001fb75  mov     rcx, rbx; SRWLock
0x18001fb78  mov     sil, dl
0x18001fb7b  call    cs:__imp_AcquireSRWLockExclusive
0x18001fb81  or      eax, 0FFFFFFFFh
0x18001fb84  mov     [rsp+38h+var_18], rbx
0x18001fb89  lock xadd [rdi+94h], eax
0x18001fb91  cmp     eax, 1
0x18001fb94  jnz     short loc_18001FBC9
0x18001fb96  mov     rcx, [rdi+88h]; pwa
0x18001fb9d  mov     qword ptr [rdi+88h], 0
0x18001fba8  call    cs:__imp_CloseThreadpoolWait
0x18001fbae  xor     edx, edx
0x18001fbb0  lea     rcx, [rsp+38h+var_18]
0x18001fbb5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18001fbba  test    rdi, rdi
0x18001fbbd  jz      short loc_18001FBE5
0x18001fbbf  mov     rcx, rdi; this
0x18001fbc2  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18001fbc7  jmp     short loc_18001FBE5
0x18001fbc9  test    sil, sil
0x18001fbcc  jz      short loc_18001FBE5
0x18001fbce  mov     rdx, [rdi+80h]; h
0x18001fbd5  xor     r8d, r8d; pftTimeout
0x18001fbd8  mov     rcx, [rdi+88h]; pwa
0x18001fbdf  call    cs:__imp_SetThreadpoolWait
0x18001fbe5  lea     rcx, [rsp+38h+var_18]
0x18001fbea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001fbef  mov     rbx, [rsp+38h+arg_8]
0x18001fbf4  mov     rsi, [rsp+38h+arg_10]
0x18001fbf9  add     rsp, 30h
0x18001fbfd  pop     rdi
0x18001fbfe  retn
```
