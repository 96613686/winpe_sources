# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x1800233c8`
- end: `0x180023474`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `172`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180023310`
- `0x180059d70`
- `0x180059e30`

## callees

- `0x180003bd0`
- `0x180021f54`
- `0x1800233c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800233e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800233e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002345e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002345e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180023414`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180023414`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180023450`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180023450`

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
0x1800233c8  mov     [rsp+arg_8], rbx
0x1800233cd  mov     [rsp+arg_10], rsi
0x1800233d2  push    rdi
0x1800233d3  sub     rsp, 20h
0x1800233d7  lea     rbx, [rcx+98h]
0x1800233de  mov     rdi, rcx
0x1800233e1  mov     rcx, rbx; SRWLock
0x1800233e4  mov     sil, dl
0x1800233e7  call    cs:__imp_AcquireSRWLockExclusive
0x1800233ed  or      eax, 0FFFFFFFFh
0x1800233f0  mov     [rsp+28h+SRWLock], rbx
0x1800233f5  lock xadd [rdi+94h], eax
0x1800233fd  cmp     eax, 1
0x180023400  jnz     short loc_18002343A
0x180023402  mov     rcx, [rdi+88h]; pwa
0x180023409  mov     qword ptr [rdi+88h], 0
0x180023414  call    cs:__imp_CloseThreadpoolWait
0x18002341a  xor     edx, edx
0x18002341c  lea     rcx, [rsp+28h+SRWLock]
0x180023421  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180023426  test    rdi, rdi
0x180023429  jz      short loc_180023433
0x18002342b  mov     rcx, rdi; this
0x18002342e  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180023433  mov     rbx, [rsp+28h+SRWLock]
0x180023438  jmp     short loc_180023456
0x18002343a  test    sil, sil
0x18002343d  jz      short loc_180023456
0x18002343f  mov     rdx, [rdi+80h]; h
0x180023446  xor     r8d, r8d; pftTimeout
0x180023449  mov     rcx, [rdi+88h]; pwa
0x180023450  call    cs:__imp_SetThreadpoolWait
0x180023456  test    rbx, rbx
0x180023459  jz      short loc_180023464
0x18002345b  mov     rcx, rbx; SRWLock
0x18002345e  call    cs:__imp_ReleaseSRWLockExclusive
0x180023464  mov     rbx, [rsp+28h+arg_8]
0x180023469  mov     rsi, [rsp+28h+arg_10]
0x18002346e  add     rsp, 20h
0x180023472  pop     rdi
0x180023473  retn
```
