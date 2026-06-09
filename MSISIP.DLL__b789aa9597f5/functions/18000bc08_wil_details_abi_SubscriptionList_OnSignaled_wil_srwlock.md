# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000bc08`
- end: `0x18000bcd1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `201`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800083b0`
- `0x1800088d0`
- `0x18000b02c`

## callees

- `0x1800084c8`
- `0x1800088f4`
- `0x18000adec`
- `0x18000bc08`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bc5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bc5b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000bc2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000bc2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bc69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bc69`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // rsi
  __int64 v7; // r15
  char *v8; // rdx
  PSRWLOCK v9; // [rsp+60h] [rbp+8h] BYREF
  LPCRITICAL_SECTION v10; // [rsp+68h] [rbp+10h] BYREF

  AcquireSRWLockShared(SRWLock);
  v9 = SRWLock;
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    v10 = lpCriticalSection;
    AcquireSRWLockExclusive(SRWLock);
    v9 = SRWLock;
    while ( v5 < v4 )
    {
      v8 = (char *)lpCriticalSection[1].DebugInfo + 16 * v5++;
      if ( *(_QWORD *)v8 )
      {
        v6 = *(void (__fastcall **)(__int64))v8;
        v7 = *((_QWORD *)v8 + 1);
        break;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    if ( v6 )
      v6(v7);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18000bc08  push    rbp
0x18000bc0a  push    rsi
0x18000bc0b  push    rdi
0x18000bc0c  push    r14
0x18000bc0e  push    r15
0x18000bc10  sub     rsp, 30h
0x18000bc14  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000bc1d  mov     [rsp+58h+arg_10], rbx
0x18000bc22  mov     r14, rdx
0x18000bc25  mov     rbp, rcx
0x18000bc28  mov     rcx, rdx; SRWLock
0x18000bc2b  call    cs:__imp_AcquireSRWLockShared
0x18000bc31  mov     [rsp+58h+arg_0], r14
0x18000bc36  mov     rdi, [rbp+30h]
0x18000bc3a  sub     rdi, [rbp+28h]
0x18000bc3e  shr     rdi, 4
0x18000bc42  lea     rcx, [rsp+58h+arg_0]
0x18000bc47  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bc4c  xor     ebx, ebx
0x18000bc4e  test    rdi, rdi
0x18000bc51  jz      short loc_18000BCC0
0x18000bc53  xor     esi, esi
0x18000bc55  xor     r15d, r15d
0x18000bc58  mov     rcx, rbp; lpCriticalSection
0x18000bc5b  call    cs:__imp_EnterCriticalSection
0x18000bc61  mov     [rsp+58h+arg_8], rbp
0x18000bc66  mov     rcx, r14; SRWLock
0x18000bc69  call    cs:__imp_AcquireSRWLockExclusive
0x18000bc6f  mov     [rsp+58h+arg_0], r14
0x18000bc74  cmp     rbx, rdi
0x18000bc77  jnb     short loc_18000BC97
0x18000bc79  lea     rcx, [rbx+1]
0x18000bc7d  shl     rbx, 4
0x18000bc81  mov     rdx, [rbp+28h]
0x18000bc85  add     rdx, rbx
0x18000bc88  mov     rbx, rcx
0x18000bc8b  cmp     [rdx], rsi
0x18000bc8e  jz      short loc_18000BC74
0x18000bc90  mov     rsi, [rdx]
0x18000bc93  mov     r15, [rdx+8]
0x18000bc97  lea     rcx, [rsp+58h+arg_0]
0x18000bc9c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bca1  test    rsi, rsi
0x18000bca4  jz      short loc_18000BCB1
0x18000bca6  mov     rcx, r15
0x18000bca9  mov     rax, rsi
0x18000bcac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcb1  lea     rcx, [rsp+58h+arg_8]
0x18000bcb6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000bcbb  cmp     rbx, rdi
0x18000bcbe  jb      short loc_18000BC53
0x18000bcc0  mov     rbx, [rsp+58h+arg_10]
0x18000bcc5  add     rsp, 30h
0x18000bcc9  pop     r15
0x18000bccb  pop     r14
0x18000bccd  pop     rdi
0x18000bcce  pop     rsi
0x18000bccf  pop     rbp
0x18000bcd0  retn
```
