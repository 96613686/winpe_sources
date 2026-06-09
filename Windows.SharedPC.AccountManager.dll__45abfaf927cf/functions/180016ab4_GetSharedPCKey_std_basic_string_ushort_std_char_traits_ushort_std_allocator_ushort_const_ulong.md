# GetSharedPCKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180016ab4`
- end: `0x180016c02`
- name: `?GetSharedPCKey@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015b40`
- `0x18001655c`
- `0x180016924`

## callees

- `0x180003530`
- `0x18000a584`
- `0x18000ccf4`
- `0x18000cd50`
- `0x18000cfc0`
- `0x180013dcc`
- `0x180016ab4`
- `0x180016d5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016b92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016b92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016b20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016b20`

## string_xrefs

- `0x180016b31`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`
- `0x180016ba3`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HKEY __fastcall GetSharedPCKey(__int64 a1, REGSAM a2)
{
  const WCHAR *v3; // rax
  unsigned int v4; // eax
  const WCHAR *v5; // rax
  unsigned int v6; // eax
  HKEY v7; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-19h]
  unsigned int phkResulta; // [rsp+20h] [rbp-19h]
  HKEY v11; // [rsp+50h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+1Fh] BYREF
  _BYTE v13[32]; // [rsp+60h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  GetSharedPCTargetPath((__int64)v13);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0xF003Fu, &hKey);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x42,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)v4,
      phkResult);
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v11,
    0);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v6 = RegCreateKeyExW(hKey, v5, 0, 0, 0, a2, 0, &v11, 0);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x45,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)v6,
      phkResulta);
  v7 = v11;
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate((__int64)v13);
  return v7;
}

```

## disassembly

```asm
0x180016ab4  mov     [rsp-8+arg_10], rbx
0x180016ab9  mov     [rsp-8+arg_18], rdi
0x180016abe  push    rbp
0x180016abf  lea     rbp, [rsp-57h]
0x180016ac4  sub     rsp, 90h
0x180016acb  mov     rax, cs:__security_cookie
0x180016ad2  xor     rax, rsp
0x180016ad5  mov     [rbp+57h+var_10], rax
0x180016ad9  mov     edi, edx
0x180016adb  mov     rbx, rcx
0x180016ade  lea     rcx, [rbp+57h+var_30]
0x180016ae2  call    ?GetSharedPCTargetPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetSharedPCTargetPath(void)
0x180016ae7  nop
0x180016ae8  mov     [rbp+57h+hKey], 0
0x180016af0  xor     edx, edx
0x180016af2  lea     rcx, [rbp+57h+hKey]
0x180016af6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180016afb  lea     rcx, [rbp+57h+var_30]
0x180016aff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016b04  mov     rdx, rax; lpSubKey
0x180016b07  lea     rax, [rbp+57h+hKey]
0x180016b0b  mov     [rsp+90h+phkResult], rax; unsigned int
0x180016b10  mov     r9d, 0F003Fh; samDesired
0x180016b16  xor     r8d, r8d; ulOptions
0x180016b19  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016b20  call    cs:__imp_RegOpenKeyExW
0x180016b26  mov     rcx, [rbp+5Fh]; this
0x180016b2a  test    eax, eax
0x180016b2c  jz      short loc_180016B43
0x180016b2e  mov     r9d, eax; char *
0x180016b31  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016b38  mov     edx, 42h ; 'B'; void *
0x180016b3d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180016b43  mov     [rbp+57h+var_40], 0
0x180016b4b  xor     edx, edx
0x180016b4d  lea     rcx, [rbp+57h+var_40]
0x180016b51  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180016b56  mov     rcx, rbx
0x180016b59  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016b5e  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x180016b67  lea     rcx, [rbp+57h+var_40]
0x180016b6b  mov     [rsp+90h+var_58], rcx; phkResult
0x180016b70  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180016b79  mov     [rsp+90h+samDesired], edi; samDesired
0x180016b7d  mov     dword ptr [rsp+90h+phkResult], 0; unsigned int
0x180016b85  xor     r9d, r9d; lpClass
0x180016b88  xor     r8d, r8d; Reserved
0x180016b8b  mov     rdx, rax; lpSubKey
0x180016b8e  mov     rcx, [rbp+57h+hKey]; hKey
0x180016b92  call    cs:__imp_RegCreateKeyExW
0x180016b98  mov     rcx, [rbp+5Fh]; this
0x180016b9c  test    eax, eax
0x180016b9e  jz      short loc_180016BB5
0x180016ba0  mov     r9d, eax; char *
0x180016ba3  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016baa  mov     edx, 45h ; 'E'; void *
0x180016baf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180016bb5  mov     rbx, [rbp+57h+var_40]
0x180016bb9  mov     [rbp+57h+var_40], 0
0x180016bc1  lea     rcx, [rbp+57h+var_40]
0x180016bc5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016bca  nop
0x180016bcb  lea     rcx, [rbp+57h+hKey]
0x180016bcf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016bd4  nop
0x180016bd5  lea     rcx, [rbp+57h+var_30]
0x180016bd9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016bde  mov     rax, rbx
0x180016be1  mov     rcx, [rbp+57h+var_10]
0x180016be5  xor     rcx, rsp; StackCookie
0x180016be8  call    __security_check_cookie
0x180016bed  lea     r11, [rsp+90h+var_s0]
0x180016bf5  mov     rbx, [r11+20h]
0x180016bf9  mov     rdi, [r11+28h]
0x180016bfd  mov     rsp, r11
0x180016c00  pop     rbp
0x180016c01  retn
```
