# Windows::Internal::AssignedAccess::AssignedAccessKioskAppUtilityPrivileged::GetKioskModeAppUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180027b8c`
- end: `0x180027d74`
- name: `?GetKioskModeAppUserSid@AssignedAccessKioskAppUtilityPrivileged@AssignedAccess@Internal@Windows@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800280e8`
- `0x1800281ac`
- `0x180028bac`
- `0x180028c74`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180016c24`
- `0x18002074c`
- `0x1800215b4`
- `0x1800221e0`
- `0x1800261a8`
- `0x1800271e4`
- `0x180027b8c`
- `0x18002901c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027d18`

## string_xrefs

- `0x180027bc3`: `Windows.Internal.AssignedAccess.AssignedAccessManager`
- `0x180027bee`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesskioskapputilityprivileged.cpp`
- `0x180027c35`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesskioskapputilityprivileged.cpp`
- `0x180027c77`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesskioskapputilityprivileged.cpp`
- `0x180027cf2`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesskioskapputilityprivileged.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessKioskAppUtilityPrivileged::GetKioskModeAppUserSid(
        __int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rcx
  int UserInfoIf__lambda_246e624a1980e386c1f6892b2913bb44; // eax
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rdi
  int v12; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v17; // [rsp+20h] [rbp-58h] BYREF
  __int64 v18; // [rsp+28h] [rbp-50h] BYREF
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  __int64 v22; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v20 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.AssignedAccess.AssignedAccessManager",
    0x36u,
    0x35u);
  v2 = Windows::Foundation::ActivateInstance<Windows::Internal::AssignedAccess::IAssignedAccessManager>(v22, &v20);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v17 = 0;
    v4 = *v20;
    v17 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 56))(v20, &v17);
    v3 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesskioskapputilityprivileged.cpp",
        (const char *)(unsigned int)v5,
        v17);
LABEL_5:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v17);
      goto LABEL_15;
    }
    v18 = 0;
    UserInfoIf__lambda_246e624a1980e386c1f6892b2913bb44 = Windows::Internal::AssignedAccess::AssignedAccessConfigurationHelper::FindUserInfoIf__lambda_246e624a1980e386c1f6892b2913bb44___(
                                                            v6,
                                                            v17,
                                                            &v18);
    v3 = UserInfoIf__lambda_246e624a1980e386c1f6892b2913bb44;
    if ( UserInfoIf__lambda_246e624a1980e386c1f6892b2913bb44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesskioskapputilityprivileged.cpp",
        (const char *)(unsigned int)UserInfoIf__lambda_246e624a1980e386c1f6892b2913bb44,
        v17);
LABEL_8:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v18);
      goto LABEL_5;
    }
    v8 = v18;
    if ( v18 )
    {
      string = 0;
      v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 48LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v12 = v11(v8, &string);
      v3 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x84,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesskioskapputilityprivileged.cpp",
          (const char *)(unsigned int)v12,
          v17);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        goto LABEL_8;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v14 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
      std::wstring::_Assign<unsigned short>(a1, v15, v14);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    }
    else
    {
      v9 = std::_WChar_traits<unsigned short>::length(&LocaleName);
      std::wstring::_Assign<unsigned short>(a1, v10, v9);
    }
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v18);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v17);
    v3 = 0;
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x74,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesskioskapputilityprivileged.cpp",
    (const char *)(unsigned int)v2,
    v17);
LABEL_15:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v20);
  return v3;
}

```

## disassembly

```asm
0x180027b8c  push    rbp
0x180027b8e  push    rbx
0x180027b8f  push    rsi
0x180027b90  push    rdi
0x180027b91  mov     rbp, rsp
0x180027b94  sub     rsp, 78h
0x180027b98  mov     rax, cs:__security_cookie
0x180027b9f  xor     rax, rsp
0x180027ba2  mov     [rbp+var_18], rax
0x180027ba6  mov     rsi, rcx
0x180027ba9  mov     [rbp+var_40], 0
0x180027bb1  mov     [rbp+var_20], 0
0x180027bb9  mov     r9d, 35h ; '5'; unsigned int
0x180027bbf  lea     r8d, [r9+1]; unsigned int
0x180027bc3  lea     rdx, ?RuntimeClass_Windows_Internal_AssignedAccess_AssignedAccessManager@@3QBGB; "Windows.Internal.AssignedAccess.Assigne"...
0x180027bca  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180027bce  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027bd3  nop
0x180027bd4  lea     rdx, [rbp+var_40]
0x180027bd8  mov     rcx, [rbp+var_20]
0x180027bdc  call    ??$ActivateInstance@UIAssignedAccessManager@AssignedAccess@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAssignedAccessManager@AssignedAccess@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::AssignedAccess::IAssignedAccessManager>(HSTRING__ *,Windows::Internal::AssignedAccess::IAssignedAccessManager * *)
0x180027be1  mov     ebx, eax
0x180027be3  test    eax, eax
0x180027be5  jns     short loc_180027C04
0x180027be7  mov     rcx, [rbp+20h]; this
0x180027beb  mov     r9d, eax; char *
0x180027bee  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180027bf5  mov     edx, 74h ; 't'; void *
0x180027bfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027bff  jmp     loc_180027D54
0x180027c04  mov     [rbp+var_58], 0
0x180027c0c  mov     rcx, [rbp+var_40]
0x180027c10  mov     rax, [rcx]
0x180027c13  mov     [rbp+var_58], 0
0x180027c1b  lea     rdx, [rbp+var_58]
0x180027c1f  mov     rax, [rax+38h]
0x180027c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c28  mov     ebx, eax
0x180027c2a  test    eax, eax
0x180027c2c  jns     short loc_180027C55
0x180027c2e  mov     rcx, [rbp+20h]; this
0x180027c32  mov     r9d, eax; char *
0x180027c35  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180027c3c  mov     edx, 76h ; 'v'; void *
0x180027c41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c46  nop
0x180027c47  lea     rcx, [rbp+var_58]
0x180027c4b  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180027c50  jmp     loc_180027D54
0x180027c55  mov     [rbp+var_50], 0
0x180027c5d  lea     r8, [rbp+var_50]
0x180027c61  mov     rdx, [rbp+var_58]
0x180027c65  call    Windows__Internal__AssignedAccess__AssignedAccessConfigurationHelper__FindUserInfoIf__lambda_246e624a1980e386c1f6892b2913bb44___
0x180027c6a  mov     ebx, eax
0x180027c6c  test    eax, eax
0x180027c6e  jns     short loc_180027C94
0x180027c70  mov     rcx, [rbp+20h]; this
0x180027c74  mov     r9d, eax; char *
0x180027c77  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180027c7e  mov     edx, 7Dh ; '}'; void *
0x180027c83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c88  nop
0x180027c89  lea     rcx, [rbp+var_50]
0x180027c8d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180027c92  jmp     short loc_180027C47
0x180027c94  mov     rbx, [rbp+var_50]
0x180027c98  test    rbx, rbx
0x180027c9b  jnz     short loc_180027CBC
0x180027c9d  lea     rcx, LocaleName
0x180027ca4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180027ca9  mov     r8, rax
0x180027cac  mov     rdx, rcx
0x180027caf  mov     rcx, rsi
0x180027cb2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180027cb7  jmp     loc_180027D3F
0x180027cbc  mov     [rbp+string], 0
0x180027cc4  mov     rax, [rbx]
0x180027cc7  mov     rdi, [rax+30h]
0x180027ccb  xor     edx, edx
0x180027ccd  lea     rcx, [rbp+string]
0x180027cd1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180027cd6  lea     rdx, [rbp+string]
0x180027cda  mov     rcx, rbx
0x180027cdd  mov     rax, rdi
0x180027ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ce5  mov     ebx, eax
0x180027ce7  test    eax, eax
0x180027ce9  jns     short loc_180027D12
0x180027ceb  mov     rcx, [rbp+20h]; this
0x180027cef  mov     r9d, eax; char *
0x180027cf2  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180027cf9  mov     edx, 84h; void *
0x180027cfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027d03  nop
0x180027d04  lea     rcx, [rbp+string]
0x180027d08  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180027d0d  jmp     loc_180027C89
0x180027d12  xor     edx, edx; length
0x180027d14  mov     rcx, [rbp+string]; string
0x180027d18  call    cs:__imp_WindowsGetStringRawBuffer
0x180027d1e  mov     rcx, rax
0x180027d21  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180027d26  mov     r8, rax
0x180027d29  mov     rdx, rcx
0x180027d2c  mov     rcx, rsi
0x180027d2f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180027d34  nop
0x180027d35  lea     rcx, [rbp+string]
0x180027d39  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180027d3e  nop
0x180027d3f  lea     rcx, [rbp+var_50]
0x180027d43  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180027d48  nop
0x180027d49  lea     rcx, [rbp+var_58]
0x180027d4d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180027d52  xor     ebx, ebx
0x180027d54  lea     rcx, [rbp+var_40]
0x180027d58  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180027d5d  mov     eax, ebx
0x180027d5f  mov     rcx, [rbp+var_18]
0x180027d63  xor     rcx, rsp; StackCookie
0x180027d66  call    __security_check_cookie
0x180027d6b  add     rsp, 78h
0x180027d6f  pop     rdi
0x180027d70  pop     rsi
0x180027d71  pop     rbx
0x180027d72  pop     rbp
0x180027d73  retn
```
