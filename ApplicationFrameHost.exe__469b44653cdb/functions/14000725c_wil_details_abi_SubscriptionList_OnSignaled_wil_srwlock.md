# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000725c`
- end: `0x14000731b`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `191`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140004140`
- `0x140004170`
- `0x140005e84`

## callees

- `0x140004ea8`
- `0x140004ec8`
- `0x140004ee8`
- `0x14000725c`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400072a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400072a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140007275`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140007275`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400072b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400072b3`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // rsi
  __int64 v7; // r15
  char *v8; // rdx
  RTL_SRWLOCK *v9; // [rsp+50h] [rbp+8h] BYREF
  LPCRITICAL_SECTION v10; // [rsp+58h] [rbp+10h] BYREF

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
0x14000725c  mov     [rsp+arg_10], rbx
0x140007261  push    rbp
0x140007262  push    rsi
0x140007263  push    rdi
0x140007264  push    r14
0x140007266  push    r15
0x140007268  sub     rsp, 20h
0x14000726c  mov     r14, rdx
0x14000726f  mov     rbp, rcx
0x140007272  mov     rcx, rdx; SRWLock
0x140007275  call    cs:__imp_AcquireSRWLockShared
0x14000727b  mov     [rsp+48h+arg_0], r14
0x140007280  mov     rdi, [rbp+30h]
0x140007284  sub     rdi, [rbp+28h]
0x140007288  shr     rdi, 4
0x14000728c  lea     rcx, [rsp+48h+arg_0]
0x140007291  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140007296  xor     ebx, ebx
0x140007298  test    rdi, rdi
0x14000729b  jz      short loc_14000730A
0x14000729d  xor     esi, esi
0x14000729f  xor     r15d, r15d
0x1400072a2  mov     rcx, rbp; lpCriticalSection
0x1400072a5  call    cs:__imp_EnterCriticalSection
0x1400072ab  mov     [rsp+48h+arg_8], rbp
0x1400072b0  mov     rcx, r14; SRWLock
0x1400072b3  call    cs:__imp_AcquireSRWLockExclusive
0x1400072b9  mov     [rsp+48h+arg_0], r14
0x1400072be  cmp     rbx, rdi
0x1400072c1  jnb     short loc_1400072E1
0x1400072c3  lea     rcx, [rbx+1]
0x1400072c7  shl     rbx, 4
0x1400072cb  mov     rdx, [rbp+28h]
0x1400072cf  add     rdx, rbx
0x1400072d2  mov     rbx, rcx
0x1400072d5  cmp     [rdx], rsi
0x1400072d8  jz      short loc_1400072BE
0x1400072da  mov     rsi, [rdx]
0x1400072dd  mov     r15, [rdx+8]
0x1400072e1  lea     rcx, [rsp+48h+arg_0]
0x1400072e6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400072eb  test    rsi, rsi
0x1400072ee  jz      short loc_1400072FB
0x1400072f0  mov     rcx, r15
0x1400072f3  mov     rax, rsi
0x1400072f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400072fb  lea     rcx, [rsp+48h+arg_8]
0x140007300  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140007305  cmp     rbx, rdi
0x140007308  jb      short loc_14000729D
0x14000730a  mov     rbx, [rsp+48h+arg_10]
0x14000730f  add     rsp, 20h
0x140007313  pop     r15
0x140007315  pop     r14
0x140007317  pop     rdi
0x140007318  pop     rsi
0x140007319  pop     rbp
0x14000731a  retn
```
