# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000614c`
- end: `0x18000620b`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `191`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002940`
- `0x180002970`
- `0x180004b20`

## callees

- `0x180003678`
- `0x180003698`
- `0x1800036b8`
- `0x18000614c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006165`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006165`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006195`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006195`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061a3`

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
0x18000614c  mov     [rsp+arg_10], rbx
0x180006151  push    rbp
0x180006152  push    rsi
0x180006153  push    rdi
0x180006154  push    r14
0x180006156  push    r15
0x180006158  sub     rsp, 20h
0x18000615c  mov     r14, rdx
0x18000615f  mov     rbp, rcx
0x180006162  mov     rcx, rdx; SRWLock
0x180006165  call    cs:__imp_AcquireSRWLockShared
0x18000616b  mov     [rsp+48h+arg_0], r14
0x180006170  mov     rdi, [rbp+30h]
0x180006174  sub     rdi, [rbp+28h]
0x180006178  shr     rdi, 4
0x18000617c  lea     rcx, [rsp+48h+arg_0]
0x180006181  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180006186  xor     ebx, ebx
0x180006188  test    rdi, rdi
0x18000618b  jz      short loc_1800061FA
0x18000618d  xor     esi, esi
0x18000618f  xor     r15d, r15d
0x180006192  mov     rcx, rbp; lpCriticalSection
0x180006195  call    cs:__imp_EnterCriticalSection
0x18000619b  mov     [rsp+48h+arg_8], rbp
0x1800061a0  mov     rcx, r14; SRWLock
0x1800061a3  call    cs:__imp_AcquireSRWLockExclusive
0x1800061a9  mov     [rsp+48h+arg_0], r14
0x1800061ae  cmp     rbx, rdi
0x1800061b1  jnb     short loc_1800061D1
0x1800061b3  lea     rcx, [rbx+1]
0x1800061b7  shl     rbx, 4
0x1800061bb  mov     rdx, [rbp+28h]
0x1800061bf  add     rdx, rbx
0x1800061c2  mov     rbx, rcx
0x1800061c5  cmp     [rdx], rsi
0x1800061c8  jz      short loc_1800061AE
0x1800061ca  mov     rsi, [rdx]
0x1800061cd  mov     r15, [rdx+8]
0x1800061d1  lea     rcx, [rsp+48h+arg_0]
0x1800061d6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800061db  test    rsi, rsi
0x1800061de  jz      short loc_1800061EB
0x1800061e0  mov     rcx, r15
0x1800061e3  mov     rax, rsi
0x1800061e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061eb  lea     rcx, [rsp+48h+arg_8]
0x1800061f0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800061f5  cmp     rbx, rdi
0x1800061f8  jb      short loc_18000618D
0x1800061fa  mov     rbx, [rsp+48h+arg_10]
0x1800061ff  add     rsp, 20h
0x180006203  pop     r15
0x180006205  pop     r14
0x180006207  pop     rdi
0x180006208  pop     rsi
0x180006209  pop     rbp
0x18000620a  retn
```
