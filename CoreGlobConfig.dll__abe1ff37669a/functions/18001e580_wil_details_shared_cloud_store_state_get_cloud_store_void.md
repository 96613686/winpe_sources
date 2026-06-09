# wil::details::shared_cloud_store_state::get_cloud_store(void)

- ea: `0x18001e580`
- end: `0x18001e615`
- name: `?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ`
- size: `149`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000df9c`
- `0x18000e24c`
- `0x18001250c`

## callees

- `0x18001106c`
- `0x180011488`
- `0x180014160`
- `0x18001d564`
- `0x18001e0f0`
- `0x18001e580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e5cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e5cc`

## pseudocode

```c
_QWORD *__fastcall wil::details::shared_cloud_store_state::get_cloud_store(__int64 a1)
{
  _QWORD *v1; // rdi
  const WCHAR *v3; // rax
  RTL_SRWLOCK *v4; // rbx
  bool v5; // zf
  __int64 v6; // rdx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+48h] [rbp+10h] BYREF

  v1 = (_QWORD *)(a1 + 72);
  if ( !*(_QWORD *)(a1 + 72) )
  {
    v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    wil::details::CreateCloudStoreDefaultWithWaitTime(
      &v8,
      *(_DWORD *)a1,
      *(_QWORD *)(a1 + 8),
      *(const char **)(a1 + 16),
      v3);
    v4 = (RTL_SRWLOCK *)(a1 + 64);
    AcquireSRWLockExclusive(v4);
    v5 = *v1 == 0;
    v9 = v4;
    if ( v5 )
    {
      v6 = v8;
      v8 = 0;
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::attach(v1, v6);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v8);
  }
  return v1;
}

```

## disassembly

```asm
0x18001e580  mov     [rsp+arg_10], rbx
0x18001e585  push    rdi
0x18001e586  sub     rsp, 30h
0x18001e58a  lea     rdi, [rcx+48h]
0x18001e58e  mov     rbx, rcx
0x18001e591  cmp     qword ptr [rdi], 0
0x18001e595  jnz     short loc_18001E607
0x18001e597  add     rcx, 18h
0x18001e59b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e5a0  mov     r9, [rbx+10h]
0x18001e5a4  lea     rcx, [rsp+38h+arg_0]
0x18001e5a9  mov     r8, [rbx+8]
0x18001e5ad  mov     rdx, rax
0x18001e5b0  lea     rax, [rbx+38h]
0x18001e5b4  mov     [rsp+38h+var_10], rax
0x18001e5b9  mov     [rsp+38h+var_18], rdx
0x18001e5be  mov     edx, [rbx]
0x18001e5c0  call    ?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEBGAEBUWaitTimes@5678@@Z; wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &)
0x18001e5c5  add     rbx, 40h ; '@'
0x18001e5c9  mov     rcx, rbx; SRWLock
0x18001e5cc  call    cs:__imp_AcquireSRWLockExclusive
0x18001e5d2  cmp     qword ptr [rdi], 0
0x18001e5d6  mov     [rsp+38h+arg_8], rbx
0x18001e5db  jnz     short loc_18001E5F3
0x18001e5dd  mov     rdx, [rsp+38h+arg_0]
0x18001e5e2  mov     rcx, rdi
0x18001e5e5  mov     [rsp+38h+arg_0], 0
0x18001e5ee  call    ?attach@?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUICloudStore@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::ICloudStore *)
0x18001e5f3  lea     rcx, [rsp+38h+arg_8]
0x18001e5f8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e5fd  lea     rcx, [rsp+38h+arg_0]
0x18001e602  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18001e607  mov     rbx, [rsp+38h+arg_10]
0x18001e60c  mov     rax, rdi
0x18001e60f  add     rsp, 30h
0x18001e613  pop     rdi
0x18001e614  retn
```
