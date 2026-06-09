# FocusSingletonAccessor::GetFocusSessionThemeManager(void)

- ea: `0x180027cec`
- end: `0x180027da5`
- name: `?GetFocusSessionThemeManager@FocusSingletonAccessor@@QEAA?AUFocusSessionThemeManager@Shell@Internal@Windows@winrt@@XZ`
- size: `185`
- prototype: `struct winrt::Windows::Internal::Shell::FocusSessionThemeManager __high(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027990`
- `0x180027f4c`
- `0x1800281bc`
- `0x18002e55c`

## callees

- `0x180008fa8`
- `0x18000dfc0`
- `0x180025c38`
- `0x18002636c`
- `0x180027cec`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027d06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027d54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027d06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027d54`

## pseudocode

```c
winrt::Windows::Foundation::IUnknown *__fastcall FocusSingletonAccessor::GetFocusSessionThemeManager(
        RTL_SRWLOCK *a1,
        winrt::Windows::Foundation::IUnknown *a2)
{
  RTL_SRWLOCK *v2; // rsi
  RTL_SRWLOCK *v5; // rdi
  PVOID Ptr; // rax
  bool v7; // zf
  RTL_SRWLOCK *v9; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v2 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  v5 = a1 + 3;
  v9 = v2;
  Ptr = a1[3].Ptr;
  if ( Ptr )
  {
    *(_QWORD *)a2 = Ptr;
    winrt::Windows::Foundation::IUnknown::add_ref(a2);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    (**(void (__fastcall ***)(PVOID, __int64 *))a1->Ptr)(a1->Ptr, &v10);
    AcquireSRWLockExclusive(v2);
    v7 = v5->Ptr == 0;
    v9 = v2;
    if ( v7 )
      winrt::Windows::Foundation::IUnknown::operator=((winrt::Windows::Foundation::IUnknown *)&a1[3]);
    *(RTL_SRWLOCK *)a2 = (RTL_SRWLOCK)v5->Ptr;
    winrt::Windows::Foundation::IUnknown::add_ref(a2);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v10);
  }
  return a2;
}

```

## disassembly

```asm
0x180027cec  mov     [rsp+arg_8], rbx
0x180027cf1  push    rsi
0x180027cf2  push    rdi
0x180027cf3  push    r14
0x180027cf5  sub     rsp, 30h
0x180027cf9  lea     rsi, [rcx+10h]
0x180027cfd  mov     r14, rcx
0x180027d00  mov     rcx, rsi; SRWLock
0x180027d03  mov     rbx, rdx
0x180027d06  call    cs:__imp_AcquireSRWLockExclusive
0x180027d0c  lea     rdi, [r14+18h]
0x180027d10  mov     [rsp+48h+arg_0], rsi
0x180027d15  mov     rax, [rdi]
0x180027d18  test    rax, rax
0x180027d1b  jz      short loc_180027D34
0x180027d1d  mov     rcx, rbx; this
0x180027d20  mov     [rbx], rax
0x180027d23  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180027d28  lea     rcx, [rsp+48h+arg_0]
0x180027d2d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180027d32  jmp     short loc_180027D94
0x180027d34  lea     rcx, [rsp+48h+arg_0]
0x180027d39  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180027d3e  mov     rcx, [r14]
0x180027d41  lea     rdx, [rsp+48h+arg_10]
0x180027d46  mov     rax, [rcx]
0x180027d49  mov     rax, [rax]
0x180027d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d51  mov     rcx, rsi; SRWLock
0x180027d54  call    cs:__imp_AcquireSRWLockExclusive
0x180027d5a  cmp     qword ptr [rdi], 0
0x180027d5e  mov     [rsp+48h+arg_0], rsi
0x180027d63  jnz     short loc_180027D72
0x180027d65  lea     rdx, [rsp+48h+arg_10]
0x180027d6a  mov     rcx, rdi; this
0x180027d6d  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x180027d72  mov     rax, [rdi]
0x180027d75  mov     rcx, rbx; this
0x180027d78  mov     [rbx], rax
0x180027d7b  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180027d80  lea     rcx, [rsp+48h+arg_0]
0x180027d85  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180027d8a  lea     rcx, [rsp+48h+arg_10]
0x180027d8f  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180027d94  mov     rax, rbx
0x180027d97  mov     rbx, [rsp+48h+arg_8]
0x180027d9c  add     rsp, 30h
0x180027da0  pop     r14
0x180027da2  pop     rdi
0x180027da3  pop     rsi
0x180027da4  retn
```
