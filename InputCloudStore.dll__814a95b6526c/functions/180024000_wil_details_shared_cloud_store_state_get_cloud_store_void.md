# wil::details::shared_cloud_store_state::get_cloud_store(void)

- ea: `0x180024000`
- end: `0x180024095`
- name: `?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `23`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012abc`
- `0x180012ca4`
- `0x180012e8c`
- `0x180013074`
- `0x18001325c`
- `0x180013454`
- `0x18001363c`
- `0x180013824`
- `0x180013aa4`
- `0x180013d24`
- `0x180013fa4`
- `0x180014224`
- `0x1800144b8`
- `0x180014738`
- `0x1800149b8`
- `0x18001c7c8`
- `0x18001c934`
- `0x18001caa0`
- `0x18001cc0c`
- `0x18001cd78`
- `0x18001cee4`
- `0x18001d09c`
- `0x18001ec28`

## callees

- `0x18001b128`
- `0x18001b3fc`
- `0x18001f1f0`
- `0x180022b44`
- `0x180022d18`
- `0x180024000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002404c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002404c`

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
    v3 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 24);
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
0x180024000  mov     [rsp+arg_10], rbx
0x180024005  push    rdi
0x180024006  sub     rsp, 30h
0x18002400a  lea     rdi, [rcx+48h]
0x18002400e  mov     rbx, rcx
0x180024011  cmp     qword ptr [rdi], 0
0x180024015  jnz     short loc_180024087
0x180024017  add     rcx, 18h
0x18002401b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180024020  mov     r9, [rbx+10h]
0x180024024  lea     rcx, [rsp+38h+arg_0]
0x180024029  mov     r8, [rbx+8]
0x18002402d  mov     rdx, rax
0x180024030  lea     rax, [rbx+38h]
0x180024034  mov     [rsp+38h+var_10], rax
0x180024039  mov     [rsp+38h+var_18], rdx
0x18002403e  mov     edx, [rbx]
0x180024040  call    ?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEB_WAEBUWaitTimes@5678@@Z; wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,wchar_t const *,Windows::Internal::Storage::Cloud::WaitTimes const &)
0x180024045  add     rbx, 40h ; '@'
0x180024049  mov     rcx, rbx; SRWLock
0x18002404c  call    cs:__imp_AcquireSRWLockExclusive
0x180024052  cmp     qword ptr [rdi], 0
0x180024056  mov     [rsp+38h+arg_8], rbx
0x18002405b  jnz     short loc_180024073
0x18002405d  mov     rdx, [rsp+38h+arg_0]
0x180024062  mov     rcx, rdi
0x180024065  mov     [rsp+38h+arg_0], 0
0x18002406e  call    ?attach@?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUICloudStore@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::ICloudStore *)
0x180024073  lea     rcx, [rsp+38h+arg_8]
0x180024078  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002407d  lea     rcx, [rsp+38h+arg_0]
0x180024082  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180024087  mov     rbx, [rsp+38h+arg_10]
0x18002408c  mov     rax, rdi
0x18002408f  add     rsp, 30h
0x180024093  pop     rdi
0x180024094  retn
```
