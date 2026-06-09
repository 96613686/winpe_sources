# wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)

- ea: `0x140006b14`
- end: `0x140006b91`
- name: `?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z`
- size: `125`
- prototype: `void(wil::details_abi::SubscriptionList *__hidden this, struct wil::srwlock *, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140006b98`
- `0x140006ce0`

## callees

- `0x140001c44`
- `0x140003cc8`
- `0x140006b14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006b31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006b31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006b3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006b3f`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::Unsubscribe(
        struct _RTL_CRITICAL_SECTION *this,
        RTL_SRWLOCK *a2,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a3)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  unsigned __int64 v7; // rax
  RTL_SRWLOCK *v8; // [rsp+40h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION *v9; // [rsp+48h] [rbp+20h] BYREF

  if ( a3 )
  {
    EnterCriticalSection(this);
    v9 = this;
    AcquireSRWLockExclusive(a2);
    DebugInfo = this[1].DebugInfo;
    v7 = *(_QWORD *)&this[1].LockCount - (_QWORD)DebugInfo;
    v8 = a2;
    if ( (unsigned __int64)a3 - 1 < v7 >> 4 )
      *((_OWORD *)&DebugInfo->Type + (unsigned __int64)a3 - 1) = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x140006b14  test    r8, r8
0x140006b17  jz      short locret_140006B90
0x140006b19  mov     [rsp+arg_0], rbx
0x140006b1e  mov     [rsp+arg_8], rsi
0x140006b23  push    rdi
0x140006b24  sub     rsp, 20h
0x140006b28  mov     rdi, r8
0x140006b2b  mov     rsi, rdx
0x140006b2e  mov     rbx, rcx
0x140006b31  call    cs:__imp_EnterCriticalSection
0x140006b37  mov     rcx, rsi; SRWLock
0x140006b3a  mov     [rsp+28h+arg_18], rbx
0x140006b3f  call    cs:__imp_AcquireSRWLockExclusive
0x140006b45  mov     rcx, [rbx+28h]
0x140006b49  lea     rdx, [rdi-1]
0x140006b4d  mov     rax, [rbx+30h]
0x140006b51  sub     rax, rcx
0x140006b54  mov     [rsp+28h+arg_10], rsi
0x140006b59  shr     rax, 4
0x140006b5d  cmp     rdx, rax
0x140006b60  jnb     short loc_140006B6D
0x140006b62  add     rdx, rdx
0x140006b65  xorps   xmm0, xmm0
0x140006b68  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x140006b6d  lea     rcx, [rsp+28h+arg_10]
0x140006b72  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140006b77  lea     rcx, [rsp+28h+arg_18]
0x140006b7c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140006b81  mov     rbx, [rsp+28h+arg_0]
0x140006b86  mov     rsi, [rsp+28h+arg_8]
0x140006b8b  add     rsp, 20h
0x140006b8f  pop     rdi
0x140006b90  retn
```
