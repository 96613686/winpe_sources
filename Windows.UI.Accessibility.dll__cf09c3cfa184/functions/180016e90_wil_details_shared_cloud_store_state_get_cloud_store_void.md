# wil::details::shared_cloud_store_state::get_cloud_store(void)

- ea: `0x180016e90`
- end: `0x180016f25`
- name: `?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ`
- size: `149`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800114fc`
- `0x1800116e4`
- `0x180013afc`
- `0x180018838`
- `0x180018a20`
- `0x180019904`
- `0x18001dfb0`
- `0x18001e198`
- `0x1800209ec`

## callees

- `0x180008ebc`
- `0x180008fa8`
- `0x1800097ec`
- `0x18000d044`
- `0x1800166d4`
- `0x180016e90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016edc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016edc`

## pseudocode

```c
_QWORD *__fastcall wil::details::shared_cloud_store_state::get_cloud_store(__int64 a1)
{
  _QWORD *v1; // rdi
  __int64 v3; // rax
  RTL_SRWLOCK *v4; // rbx
  bool v5; // zf
  __int64 v6; // rdx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+48h] [rbp+10h] BYREF

  v1 = (_QWORD *)(a1 + 72);
  if ( !*(_QWORD *)(a1 + 72) )
  {
    v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 24);
    wil::details::CreateCloudStoreDefaultWithWaitTime(
      (unsigned int)&v8,
      *(_DWORD *)a1,
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 16),
      v3,
      a1 + 56);
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
0x180016e90  mov     [rsp+arg_10], rbx
0x180016e95  push    rdi
0x180016e96  sub     rsp, 30h
0x180016e9a  lea     rdi, [rcx+48h]
0x180016e9e  mov     rbx, rcx
0x180016ea1  cmp     qword ptr [rdi], 0
0x180016ea5  jnz     short loc_180016F17
0x180016ea7  add     rcx, 18h
0x180016eab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016eb0  mov     r9, [rbx+10h]
0x180016eb4  lea     rcx, [rsp+38h+arg_0]
0x180016eb9  mov     r8, [rbx+8]
0x180016ebd  mov     rdx, rax
0x180016ec0  lea     rax, [rbx+38h]
0x180016ec4  mov     [rsp+38h+var_10], rax
0x180016ec9  mov     [rsp+38h+var_18], rdx
0x180016ece  mov     edx, [rbx]
0x180016ed0  call    ?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEBGAEBUWaitTimes@5678@@Z; wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &)
0x180016ed5  add     rbx, 40h ; '@'
0x180016ed9  mov     rcx, rbx; SRWLock
0x180016edc  call    cs:__imp_AcquireSRWLockExclusive
0x180016ee2  cmp     qword ptr [rdi], 0
0x180016ee6  mov     [rsp+38h+arg_8], rbx
0x180016eeb  jnz     short loc_180016F03
0x180016eed  mov     rdx, [rsp+38h+arg_0]
0x180016ef2  mov     rcx, rdi
0x180016ef5  mov     [rsp+38h+arg_0], 0
0x180016efe  call    ?attach@?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUICloudStore@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::ICloudStore *)
0x180016f03  lea     rcx, [rsp+38h+arg_8]
0x180016f08  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016f0d  lea     rcx, [rsp+38h+arg_0]
0x180016f12  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180016f17  mov     rbx, [rsp+38h+arg_10]
0x180016f1c  mov     rax, rdi
0x180016f1f  add     rsp, 30h
0x180016f23  pop     rdi
0x180016f24  retn
```
