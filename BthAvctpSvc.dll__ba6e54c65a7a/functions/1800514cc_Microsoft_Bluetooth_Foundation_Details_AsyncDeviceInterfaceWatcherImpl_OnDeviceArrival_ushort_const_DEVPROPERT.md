# Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl::OnDeviceArrival(ushort const *,_DEVPROPERTY const *,ulong)

- ea: `0x1800514cc`
- end: `0x1800515e6`
- name: `?OnDeviceArrival@AsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@AEAAXPEBGPEBU_DEVPROPERTY@@K@Z`
- size: `282`
- prototype: `void(Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl *__hidden this, const unsigned __int16 *, const struct _DEVPROPERTY *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050cc8`

## callees

- `0x180001dd0`
- `0x180004060`
- `0x18000dcc4`
- `0x18000de78`
- `0x1800120e8`
- `0x1800151f4`
- `0x180019d20`
- `0x180019e08`
- `0x1800509a8`
- `0x1800514cc`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051506`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051506`

## string_xrefs

- `0x180051543`: `Device '%ws' already added!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl::OnDeviceArrival(
        RTL_SRWLOCK *this,
        const char *a2,
        const struct _DEVPROPERTY *a3,
        unsigned int a4)
{
  RTL_SRWLOCK *v8; // rbx
  PVOID *v9; // rax
  const char *v10; // [rsp+40h] [rbp-29h] BYREF
  __int64 v11; // [rsp+48h] [rbp-21h] BYREF
  std::_Ref_count_base *v12; // [rsp+50h] [rbp-19h]
  RTL_SRWLOCK *v13; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v14[32]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v10 = a2;
  v8 = this + 7;
  AcquireSRWLockExclusive(this + 7);
  v13 = v8;
  std::wstring::wstring((__int64)v14, (__int64)a2);
  v9 = (PVOID *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                  &this[8],
                  &v11,
                  v14);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x61,
    (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\asyncdevicewatcher.cpp",
    (const char *)0x8000FFFFLL,
    *v9 != this[8].Ptr,
    (bool)"Device '%ws' already added!",
    a2);
  std::wstring::_Tidy_deallocate(v14);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<unsigned short const * &>(
    &this[8],
    &v11,
    &v10);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>>::lock(
    &this[5],
    &v11);
  if ( v11 )
    (*(void (__fastcall **)(__int64, const char *, const struct _DEVPROPERTY *, _QWORD))(*(_QWORD *)v11 + 8LL))(
      v11,
      v10,
      a3,
      a4);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
}

```

## disassembly

```asm
0x1800514cc  push    rbp
0x1800514ce  push    rbx
0x1800514cf  push    rsi
0x1800514d0  push    rdi
0x1800514d1  push    r14
0x1800514d3  push    r15
0x1800514d5  lea     rbp, [rsp-2Fh]
0x1800514da  sub     rsp, 98h
0x1800514e1  mov     rax, cs:__security_cookie
0x1800514e8  xor     rax, rsp
0x1800514eb  mov     [rbp+57h+var_40], rax
0x1800514ef  mov     r15d, r9d
0x1800514f2  mov     r14, r8
0x1800514f5  mov     rdi, rdx
0x1800514f8  mov     rsi, rcx
0x1800514fb  mov     [rbp+57h+var_80], rdx
0x1800514ff  lea     rbx, [rcx+38h]
0x180051503  mov     rcx, rbx; SRWLock
0x180051506  call    cs:__imp_AcquireSRWLockExclusive
0x18005150c  mov     [rbp+57h+var_68], rbx
0x180051510  lea     rbx, [rsi+40h]
0x180051514  mov     rdx, rdi
0x180051517  lea     rcx, [rbp+57h+var_60]
0x18005151b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180051520  nop
0x180051521  lea     r8, [rbp+57h+var_60]
0x180051525  lea     rdx, [rbp+57h+var_78]
0x180051529  mov     rcx, rbx
0x18005152c  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180051531  mov     rcx, [rbx]
0x180051534  cmp     [rax], rcx
0x180051537  setnz   al
0x18005153a  mov     rcx, [rbp+5Fh]; this
0x18005153e  mov     [rsp+0C0h+var_90], rdi; char *
0x180051543  lea     rdx, aDeviceWsAlread; "Device '%ws' already added!"
0x18005154a  mov     qword ptr [rsp+0C0h+var_98], rdx; bool
0x18005154f  mov     [rsp+0C0h+var_A0], al; char
0x180051553  mov     r9d, 8000FFFFh; char *
0x180051559  lea     r8, aOnecoreDrivers_33; "onecore\\drivers\\bluetooth\\foundation"...
0x180051560  mov     edx, 61h ; 'a'; void *
0x180051565  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005156a  nop
0x18005156b  lea     rcx, [rbp+57h+var_60]
0x18005156f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180051574  lea     r8, [rbp+57h+var_80]
0x180051578  lea     rdx, [rbp+57h+var_78]
0x18005157c  mov     rcx, rbx
0x18005157f  call    ??$_Emplace@AEAPEBG@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@AEAPEBG@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<ushort const * &>(ushort const * &)
0x180051584  nop
0x180051585  lea     rcx, [rbp+57h+var_68]
0x180051589  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005158e  lea     rcx, [rsi+28h]
0x180051592  lea     rdx, [rbp+57h+var_78]
0x180051596  call    ?lock@?$weak_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@QEBA?AV?$shared_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@2@XZ; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>>::lock(void)
0x18005159b  nop
0x18005159c  mov     rcx, [rbp+57h+var_78]
0x1800515a0  test    rcx, rcx
0x1800515a3  jz      short loc_1800515BC
0x1800515a5  mov     rax, [rcx]
0x1800515a8  mov     r9d, r15d
0x1800515ab  mov     r8, r14
0x1800515ae  mov     rdx, [rbp+57h+var_80]
0x1800515b2  mov     rax, [rax+8]
0x1800515b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515bb  nop
0x1800515bc  mov     rcx, [rbp+57h+var_70]; this
0x1800515c0  test    rcx, rcx
0x1800515c3  jz      short loc_1800515CA
0x1800515c5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800515ca  mov     rcx, [rbp+57h+var_40]
0x1800515ce  xor     rcx, rsp; StackCookie
0x1800515d1  call    __security_check_cookie
0x1800515d6  add     rsp, 98h
0x1800515dd  pop     r15
0x1800515df  pop     r14
0x1800515e1  pop     rdi
0x1800515e2  pop     rsi
0x1800515e3  pop     rbx
0x1800515e4  pop     rbp
0x1800515e5  retn
```
