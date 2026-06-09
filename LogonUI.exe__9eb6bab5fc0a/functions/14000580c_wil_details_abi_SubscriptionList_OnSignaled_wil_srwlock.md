# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000580c`
- end: `0x1400058cb`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `191`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400033e0`
- `0x140003410`
- `0x1400045f4`

## callees

- `0x140001c44`
- `0x140003cc8`
- `0x140003ce8`
- `0x14000580c`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140005825`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140005825`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005855`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005855`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005863`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005863`

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
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  v9 = SRWLock;
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
0x14000580c  mov     [rsp+arg_10], rbx
0x140005811  push    rbp
0x140005812  push    rsi
0x140005813  push    rdi
0x140005814  push    r14
0x140005816  push    r15
0x140005818  sub     rsp, 20h
0x14000581c  mov     rbp, rcx
0x14000581f  mov     r14, rdx
0x140005822  mov     rcx, rdx; SRWLock
0x140005825  call    cs:__imp_AcquireSRWLockShared
0x14000582b  mov     rdi, [rbp+30h]
0x14000582f  lea     rcx, [rsp+48h+arg_0]
0x140005834  sub     rdi, [rbp+28h]
0x140005838  shr     rdi, 4
0x14000583c  mov     [rsp+48h+arg_0], r14
0x140005841  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140005846  xor     ebx, ebx
0x140005848  test    rdi, rdi
0x14000584b  jz      short loc_1400058BA
0x14000584d  mov     rcx, rbp; lpCriticalSection
0x140005850  xor     esi, esi
0x140005852  xor     r15d, r15d
0x140005855  call    cs:__imp_EnterCriticalSection
0x14000585b  mov     rcx, r14; SRWLock
0x14000585e  mov     [rsp+48h+arg_8], rbp
0x140005863  call    cs:__imp_AcquireSRWLockExclusive
0x140005869  mov     [rsp+48h+arg_0], r14
0x14000586e  cmp     rbx, rdi
0x140005871  jnb     short loc_140005891
0x140005873  mov     rdx, [rbp+28h]
0x140005877  lea     rcx, [rbx+1]
0x14000587b  shl     rbx, 4
0x14000587f  add     rdx, rbx
0x140005882  mov     rbx, rcx
0x140005885  cmp     [rdx], rsi
0x140005888  jz      short loc_14000586E
0x14000588a  mov     rsi, [rdx]
0x14000588d  mov     r15, [rdx+8]
0x140005891  lea     rcx, [rsp+48h+arg_0]
0x140005896  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000589b  test    rsi, rsi
0x14000589e  jz      short loc_1400058AB
0x1400058a0  mov     rcx, r15
0x1400058a3  mov     rax, rsi
0x1400058a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058ab  lea     rcx, [rsp+48h+arg_8]
0x1400058b0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1400058b5  cmp     rbx, rdi
0x1400058b8  jb      short loc_14000584D
0x1400058ba  mov     rbx, [rsp+48h+arg_10]
0x1400058bf  add     rsp, 20h
0x1400058c3  pop     r15
0x1400058c5  pop     r14
0x1400058c7  pop     rdi
0x1400058c8  pop     rsi
0x1400058c9  pop     rbp
0x1400058ca  retn
```
