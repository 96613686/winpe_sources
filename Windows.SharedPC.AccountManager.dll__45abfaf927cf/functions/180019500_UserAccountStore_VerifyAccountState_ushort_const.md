# UserAccountStore::VerifyAccountState(ushort const *)

- ea: `0x180019500`
- end: `0x180019614`
- name: `?VerifyAccountState@UserAccountStore@@AEAA?AW4AccountDeleteState@@PEBG@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015ee0`

## callees

- `0x180003530`
- `0x18000a584`
- `0x18000ccd4`
- `0x18000cd50`
- `0x18000cfc0`
- `0x1800123d4`
- `0x180016eb8`
- `0x180017214`
- `0x180019500`
- `0x180019874`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800195a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800195a3`

## string_xrefs

- `0x18001955c`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`

## pseudocode

```c
__int64 __fastcall UserAccountStore::VerifyAccountState(__int64 a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  int phkResult; // [rsp+20h] [rbp-60h]
  int v8; // [rsp+30h] [rbp-50h] BYREF
  HKEY v9; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v11[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  memset(lpSubKey, 0, sizeof(lpSubKey));
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\%s",
         a2);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      (const char *)(unsigned int)v3,
      phkResult);
  v4 = 2;
  v9 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v9,
    0);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &v9) )
  {
    v8 = 0;
    std::wstring::wstring(v11);
    UserAccountStore::GetUserAccountInfo(v5, a2, &v8, v11);
    if ( v8 )
      v4 = 1;
    std::wstring::_Tidy_deallocate(v11);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v9);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  return v4;
}

```

## disassembly

```asm
0x180019500  mov     [rsp-8+arg_0], rbx
0x180019505  mov     [rsp-8+arg_10], rdi
0x18001950a  push    rbp
0x18001950b  mov     rbp, rsp
0x18001950e  sub     rsp, 80h
0x180019515  mov     rax, cs:__security_cookie
0x18001951c  xor     rax, rsp
0x18001951f  mov     [rbp+var_8], rax
0x180019523  mov     rdi, rdx
0x180019526  mov     [rbp+lpSubKey], 0
0x18001952e  mov     [rbp+var_38], 0
0x180019536  mov     [rbp+var_30], 0
0x18001953e  mov     r8, rdx
0x180019541  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180019548  lea     rcx, [rbp+lpSubKey]
0x18001954c  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180019551  mov     rcx, [rbp+8]; this
0x180019555  test    eax, eax
0x180019557  jns     short loc_18001956E
0x180019559  mov     r9d, eax; char *
0x18001955c  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180019563  mov     edx, 11Dh; void *
0x180019568  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001956e  mov     ebx, 2
0x180019573  mov     [rbp+var_48], 0
0x18001957b  xor     edx, edx
0x18001957d  lea     rcx, [rbp+var_48]
0x180019581  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180019586  lea     rax, [rbp+var_48]
0x18001958a  mov     qword ptr [rsp+80h+phkResult], rax; phkResult
0x18001958f  mov     r9d, 20019h; samDesired
0x180019595  xor     r8d, r8d; ulOptions
0x180019598  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001959c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800195a3  call    cs:__imp_RegOpenKeyExW
0x1800195a9  test    eax, eax
0x1800195ab  jnz     short loc_1800195DE
0x1800195ad  mov     [rbp+var_50], eax
0x1800195b0  lea     rcx, [rbp+var_28]
0x1800195b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800195b9  nop
0x1800195ba  lea     r9, [rbp+var_28]
0x1800195be  lea     r8, [rbp+var_50]
0x1800195c2  mov     rdx, rdi
0x1800195c5  call    ?GetUserAccountInfo@UserAccountStore@@AEAAXPEBGAEAW4AccountType@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UserAccountStore::GetUserAccountInfo(ushort const *,AccountType &,std::wstring &)
0x1800195ca  lea     eax, [rbx-1]
0x1800195cd  cmp     [rbp+var_50], 0
0x1800195d1  cmovnz  ebx, eax
0x1800195d4  lea     rcx, [rbp+var_28]
0x1800195d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800195dd  nop
0x1800195de  lea     rcx, [rbp+var_48]
0x1800195e2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800195e7  nop
0x1800195e8  lea     rcx, [rbp+lpSubKey]
0x1800195ec  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800195f1  mov     eax, ebx
0x1800195f3  mov     rcx, [rbp+var_8]
0x1800195f7  xor     rcx, rsp; StackCookie
0x1800195fa  call    __security_check_cookie
0x1800195ff  lea     r11, [rsp+80h+var_s0]
0x180019607  mov     rbx, [r11+10h]
0x18001960b  mov     rdi, [r11+20h]
0x18001960f  mov     rsp, r11
0x180019612  pop     rbp
0x180019613  retn
```
