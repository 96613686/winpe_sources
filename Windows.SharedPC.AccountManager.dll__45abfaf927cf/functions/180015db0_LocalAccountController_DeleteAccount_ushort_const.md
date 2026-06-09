# LocalAccountController::DeleteAccount(ushort const *)

- ea: `0x180015db0`
- end: `0x180015ed1`
- name: `?DeleteAccount@LocalAccountController@@UEAAJPEBG@Z`
- size: `289`
- prototype: `__int64 __fastcall(LocalAccountController *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015408`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000a584`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x18000cd50`
- `0x180015db0`
- `0x180016c08`
- `0x180017214`
- `0x180019874`
- `0x1800198d4`
- `0x1800237f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180015e7c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180015e7c`
- `samcli!NetUserDel` at `0x180015dca`
- `samcli!NetUserDel` at `0x180015dca`

## string_xrefs

- `0x180015e12`: `CreatedLocalAccounts\%s`
- `0x180015de3`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`
- `0x180015e2f`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`
- `0x180015e8e`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
__int64 __fastcall LocalAccountController::DeleteAccount(LocalAccountController *this, const unsigned __int16 *a2)
{
  DWORD v3; // eax
  int v4; // eax
  int v5; // eax
  HKEY SharedPCKeyIfExists; // rbx
  unsigned int v7; // eax
  unsigned int v9[2]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v10[3]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = NetUserDel(0, a2);
  v4 = NetpApiStatusToNtStatus(v3);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xB4,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)(unsigned int)v4,
      v9[0]);
  memset(v10, 0, sizeof(v10));
  v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         v10,
         L"CreatedLocalAccounts\\%s",
         a2);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)(unsigned int)v5,
      v9[0]);
  std::wstring::wstring(v11, v10[0]);
  SharedPCKeyIfExists = (HKEY)GetSharedPCKeyIfExists(v11);
  *(_QWORD *)v9 = SharedPCKeyIfExists;
  std::wstring::_Tidy_deallocate(v11);
  if ( SharedPCKeyIfExists )
  {
    v7 = RegDeleteKeyExW(SharedPCKeyIfExists, 0, 0, 0);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xBE,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
        (const char *)v7,
        v9[0]);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v9);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v10);
  return 0;
}

```

## disassembly

```asm
0x180015db0  push    rbx
0x180015db2  sub     rsp, 70h
0x180015db6  mov     rax, cs:__security_cookie
0x180015dbd  xor     rax, rsp
0x180015dc0  mov     [rsp+78h+var_18], rax
0x180015dc5  mov     rbx, rdx
0x180015dc8  xor     ecx, ecx; servername
0x180015dca  call    cs:__imp_NetUserDel
0x180015dd0  mov     ecx, eax
0x180015dd2  call    NetpApiStatusToNtStatus
0x180015dd7  mov     rcx, [rsp+78h]; this
0x180015ddc  test    eax, eax
0x180015dde  jns     short loc_180015DF4
0x180015de0  mov     r9d, eax; char *
0x180015de3  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015dea  mov     edx, 0B4h; void *
0x180015def  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180015df4  mov     [rsp+78h+var_50], 0
0x180015dfd  mov     [rsp+78h+var_48], 0
0x180015e06  mov     [rsp+78h+var_40], 0
0x180015e0f  mov     r8, rbx
0x180015e12  lea     rdx, aCreatedlocalac_0; "CreatedLocalAccounts\\%s"
0x180015e19  lea     rcx, [rsp+78h+var_50]
0x180015e1e  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180015e23  mov     rcx, [rsp+78h]; this
0x180015e28  test    eax, eax
0x180015e2a  jns     short loc_180015E40
0x180015e2c  mov     r9d, eax; char *
0x180015e2f  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015e36  mov     edx, 0B9h; void *
0x180015e3b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015e40  mov     rdx, [rsp+78h+var_50]
0x180015e45  lea     rcx, [rsp+78h+var_38]
0x180015e4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015e4f  nop
0x180015e50  lea     rcx, [rsp+78h+var_38]
0x180015e55  call    ?GetSharedPCKeyIfExists@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GetSharedPCKeyIfExists(std::wstring const &,ulong)
0x180015e5a  mov     rbx, rax
0x180015e5d  mov     qword ptr [rsp+78h+var_58], rax; unsigned int
0x180015e62  lea     rcx, [rsp+78h+var_38]
0x180015e67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015e6c  test    rbx, rbx
0x180015e6f  jz      short loc_180015EA0
0x180015e71  xor     r9d, r9d; Reserved
0x180015e74  xor     r8d, r8d; samDesired
0x180015e77  xor     edx, edx; lpSubKey
0x180015e79  mov     rcx, rbx; hKey
0x180015e7c  call    cs:__imp_RegDeleteKeyExW
0x180015e82  mov     rcx, [rsp+78h]; this
0x180015e87  test    eax, eax
0x180015e89  jz      short loc_180015EA0
0x180015e8b  mov     r9d, eax; char *
0x180015e8e  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015e95  mov     edx, 0BEh; void *
0x180015e9a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180015ea0  lea     rcx, [rsp+78h+var_58]
0x180015ea5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180015eaa  nop
0x180015eab  lea     rcx, [rsp+78h+var_50]
0x180015eb0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180015eb5  xor     eax, eax
0x180015eb7  jmp     short loc_180015EBD
0x180015eb9  mov     eax, [rsp+78h+var_58]
0x180015ebd  mov     rcx, [rsp+78h+var_18]
0x180015ec2  xor     rcx, rsp; StackCookie
0x180015ec5  call    __security_check_cookie
0x180015eca  add     rsp, 70h
0x180015ece  pop     rbx
0x180015ecf  retn
```
