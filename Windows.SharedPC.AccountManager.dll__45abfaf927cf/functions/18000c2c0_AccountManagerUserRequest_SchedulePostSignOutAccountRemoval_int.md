# AccountManagerUserRequest::SchedulePostSignOutAccountRemoval(int)

- ea: `0x18000c2c0`
- end: `0x18000c487`
- name: `?SchedulePostSignOutAccountRemoval@AccountManagerUserRequest@@UEAAJH@Z`
- size: `455`
- prototype: `__int64 __fastcall(AccountManagerUserRequest *__hidden this, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000a548`
- `0x18000a584`
- `0x18000af0c`
- `0x18000c2c0`
- `0x18000c974`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x18000cd50`
- `0x18000cfc0`
- `0x1800223cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c3d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c3d4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000c44c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000c44c`

## string_xrefs

- `0x18000c2f8`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountmanageruserrequest.cpp`
- `0x18000c32c`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountmanageruserrequest.cpp`
- `0x18000c3e9`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountmanageruserrequest.cpp`
- `0x18000c474`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountmanageruserrequest.cpp`
- `0x18000c349`: `RequestedDeletes\User`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AccountManagerUserRequest::SchedulePostSignOutAccountRemoval(
        AccountManagerUserRequest *this,
        int a2)
{
  int CallerSIDString; // eax
  HKEY SharedPCRegistryKey; // rbx
  unsigned int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  int v8; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-78h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-78h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-40h] BYREF
  HKEY v13; // [rsp+60h] [rbp-38h] BYREF
  _BYTE v14[32]; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    if ( !UserRequestedDeletesEnabled() )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountmanageruserrequest.cpp",
        (const char *)0x80070032LL,
        dwOptions);
    lpSubKey = 0;
    CallerSIDString = CImpersonateCaller::GetCallerSIDString((unsigned __int16 **)&lpSubKey);
    if ( CallerSIDString < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x20,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountmanageruserrequest.cpp",
        (const char *)(unsigned int)CallerSIDString,
        dwOptions);
    std::wstring::wstring((__int64)v14, (__int64)L"RequestedDeletes\\User");
    SharedPCRegistryKey = EnsureAndGetSharedPCRegistryKey((__int64)v14, a2 != 0 ? 12 : 65544);
    v13 = SharedPCRegistryKey;
    std::wstring::_Tidy_deallocate((__int64)v14);
    if ( a2 )
    {
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v5 = RegCreateKeyExW(SharedPCRegistryKey, lpSubKey, 0, 0, 0, 0x20019u, 0, &phkResult, 0);
      if ( v5 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x29,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountmanageruserrequest.cpp",
          (const char *)v5,
          dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    else
    {
      v8 = RegDeleteKeyW(SharedPCRegistryKey, lpSubKey);
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 != -2147024894 && v8 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x30,
          (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountmanageruserrequest.cpp",
          (const char *)(unsigned int)v8,
          dwOptions);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x36,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountmanageruserrequest.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000c2c0  mov     [rsp+arg_0], rbx
0x18000c2c5  push    rdi
0x18000c2c6  sub     rsp, 90h
0x18000c2cd  mov     rax, cs:__security_cookie
0x18000c2d4  xor     rax, rsp
0x18000c2d7  mov     [rsp+98h+var_10], rax
0x18000c2df  mov     edi, edx
0x18000c2e1  call    ?UserRequestedDeletesEnabled@@YA_NXZ; UserRequestedDeletesEnabled(void)
0x18000c2e6  mov     rcx, [rsp+98h]; this
0x18000c2ee  test    al, al
0x18000c2f0  jnz     short loc_18000C30A
0x18000c2f2  mov     r9d, 80070032h; char *
0x18000c2f8  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000c2ff  mov     edx, 1Dh; void *
0x18000c304  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c30a  mov     [rsp+98h+lpSubKey], 0
0x18000c313  lea     rcx, [rsp+98h+lpSubKey]; unsigned __int16 **
0x18000c318  call    ?GetCallerSIDString@CImpersonateCaller@@SAJPEAPEAG@Z; CImpersonateCaller::GetCallerSIDString(ushort * *)
0x18000c31d  mov     rcx, [rsp+98h]; this
0x18000c325  test    eax, eax
0x18000c327  jns     short loc_18000C33D
0x18000c329  mov     r9d, eax; char *
0x18000c32c  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000c333  mov     edx, 20h ; ' '; void *
0x18000c338  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c33d  mov     eax, edi
0x18000c33f  neg     eax
0x18000c341  sbb     ebx, ebx
0x18000c343  and     ebx, 0FFFF0004h
0x18000c349  lea     rdx, aRequesteddelet; "RequestedDeletes\\User"
0x18000c350  lea     rcx, [rsp+98h+var_30]
0x18000c355  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c35a  nop
0x18000c35b  lea     edx, [rbx+10008h]
0x18000c361  lea     rcx, [rsp+98h+var_30]
0x18000c366  call    ?EnsureAndGetSharedPCRegistryKey@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; EnsureAndGetSharedPCRegistryKey(std::wstring const &,ulong)
0x18000c36b  mov     rbx, rax
0x18000c36e  mov     [rsp+98h+var_38], rax
0x18000c373  lea     rcx, [rsp+98h+var_30]
0x18000c378  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c37d  test    edi, edi
0x18000c37f  jz      loc_18000C444
0x18000c385  mov     [rsp+98h+var_40], 0
0x18000c38e  xor     edx, edx
0x18000c390  lea     rcx, [rsp+98h+var_40]
0x18000c395  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000c39a  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x18000c3a3  lea     rax, [rsp+98h+var_40]
0x18000c3a8  mov     [rsp+98h+phkResult], rax; phkResult
0x18000c3ad  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000c3b6  mov     [rsp+98h+samDesired], 20019h; samDesired
0x18000c3be  mov     [rsp+98h+dwOptions], 0; unsigned int
0x18000c3c6  xor     r9d, r9d; lpClass
0x18000c3c9  xor     r8d, r8d; Reserved
0x18000c3cc  mov     rdx, [rsp+98h+lpSubKey]; lpSubKey
0x18000c3d1  mov     rcx, rbx; hKey
0x18000c3d4  call    cs:__imp_RegCreateKeyExW
0x18000c3da  mov     rcx, [rsp+98h]; this
0x18000c3e2  test    eax, eax
0x18000c3e4  jz      short loc_18000C3FB
0x18000c3e6  mov     r9d, eax; char *
0x18000c3e9  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000c3f0  mov     edx, 29h ; ')'; void *
0x18000c3f5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000c3fb  lea     rcx, [rsp+98h+var_40]
0x18000c400  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000c405  nop
0x18000c406  lea     rcx, [rsp+98h+var_38]
0x18000c40b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000c410  nop
0x18000c411  lea     rcx, [rsp+98h+lpSubKey]
0x18000c416  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000c41b  xor     eax, eax
0x18000c41d  jmp     short loc_18000C423
0x18000c41f  mov     eax, dword ptr [rsp+98h+lpSubKey]
0x18000c423  mov     rcx, [rsp+98h+var_10]
0x18000c42b  xor     rcx, rsp; StackCookie
0x18000c42e  call    __security_check_cookie
0x18000c433  mov     rbx, [rsp+98h+arg_0]
0x18000c43b  add     rsp, 90h
0x18000c442  pop     rdi
0x18000c443  retn
0x18000c444  mov     rdx, [rsp+98h+lpSubKey]; lpSubKey
0x18000c449  mov     rcx, rbx; hKey
0x18000c44c  call    cs:__imp_RegDeleteKeyW
0x18000c452  test    eax, eax
0x18000c454  jle     short loc_18000C45E
0x18000c456  movzx   eax, ax
0x18000c459  or      eax, 80070000h
0x18000c45e  cmp     eax, 80070002h
0x18000c463  jz      short loc_18000C406
0x18000c465  mov     rcx, [rsp+98h]; this
0x18000c46d  test    eax, eax
0x18000c46f  jns     short loc_18000C406
0x18000c471  mov     r9d, eax; char *
0x18000c474  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000c47b  mov     edx, 30h ; '0'; void *
0x18000c480  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
