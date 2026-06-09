# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000518c`
- end: `0x140005252`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `198`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140002110`
- `0x140002140`
- `0x140003c24`

## callees

- `0x140002fb4`
- `0x140002fd4`
- `0x140002ff4`
- `0x14000518c`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400051e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400051e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400051d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400051d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400051a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400051a5`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // rbp
  __int64 v7; // r15
  unsigned __int64 v8; // rax
  WORD *v9; // rcx
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  LPCRITICAL_SECTION v11; // [rsp+58h] [rbp+10h] BYREF

  AcquireSRWLockShared(SRWLock);
  v10 = SRWLock;
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    v11 = lpCriticalSection;
    AcquireSRWLockExclusive(SRWLock);
    v10 = SRWLock;
    if ( v5 < v4 )
    {
      while ( 1 )
      {
        v8 = v5 + 1;
        v9 = &lpCriticalSection[1].DebugInfo->Type + 8 * v5++;
        if ( *(_QWORD *)v9 )
          break;
        if ( v8 >= v4 )
          goto LABEL_7;
      }
      v6 = *(void (__fastcall **)(__int64))v9;
      v7 = *((_QWORD *)v9 + 1);
    }
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    if ( v6 )
      v6(v7);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x14000518c  mov     [rsp+arg_10], rbx
0x140005191  push    rbp
0x140005192  push    rsi
0x140005193  push    rdi
0x140005194  push    r14
0x140005196  push    r15
0x140005198  sub     rsp, 20h
0x14000519c  mov     r14, rdx
0x14000519f  mov     rsi, rcx
0x1400051a2  mov     rcx, rdx; SRWLock
0x1400051a5  call    cs:__imp_AcquireSRWLockShared
0x1400051ab  mov     [rsp+48h+arg_0], r14
0x1400051b0  mov     rdi, [rsi+30h]
0x1400051b4  sub     rdi, [rsi+28h]
0x1400051b8  shr     rdi, 4
0x1400051bc  lea     rcx, [rsp+48h+arg_0]
0x1400051c1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400051c6  xor     ebx, ebx
0x1400051c8  test    rdi, rdi
0x1400051cb  jz      short loc_140005241
0x1400051cd  xor     ebp, ebp
0x1400051cf  xor     r15d, r15d
0x1400051d2  mov     rcx, rsi; lpCriticalSection
0x1400051d5  call    cs:__imp_EnterCriticalSection
0x1400051db  mov     [rsp+48h+arg_8], rsi
0x1400051e0  mov     rcx, r14; SRWLock
0x1400051e3  call    cs:__imp_AcquireSRWLockExclusive
0x1400051e9  mov     [rsp+48h+arg_0], r14
0x1400051ee  cmp     rbx, rdi
0x1400051f1  jnb     short loc_140005218
0x1400051f3  mov     rdx, [rsi+28h]
0x1400051f7  lea     rax, [rbx+1]
0x1400051fb  add     rbx, rbx
0x1400051fe  lea     rcx, [rdx+rbx*8]
0x140005202  mov     rbx, rax
0x140005205  cmp     [rcx], rbp
0x140005208  jnz     short loc_140005211
0x14000520a  cmp     rax, rdi
0x14000520d  jb      short loc_1400051F7
0x14000520f  jmp     short loc_140005218
0x140005211  mov     rbp, [rcx]
0x140005214  mov     r15, [rcx+8]
0x140005218  lea     rcx, [rsp+48h+arg_0]
0x14000521d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140005222  test    rbp, rbp
0x140005225  jz      short loc_140005232
0x140005227  mov     rcx, r15
0x14000522a  mov     rax, rbp
0x14000522d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005232  lea     rcx, [rsp+48h+arg_8]
0x140005237  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x14000523c  cmp     rbx, rdi
0x14000523f  jb      short loc_1400051CD
0x140005241  mov     rbx, [rsp+48h+arg_10]
0x140005246  add     rsp, 20h
0x14000524a  pop     r15
0x14000524c  pop     r14
0x14000524e  pop     rdi
0x14000524f  pop     rsi
0x140005250  pop     rbp
0x140005251  retn
```
