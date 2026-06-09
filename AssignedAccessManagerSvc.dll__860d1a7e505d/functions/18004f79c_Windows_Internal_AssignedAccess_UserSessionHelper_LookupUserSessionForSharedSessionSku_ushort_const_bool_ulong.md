# Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSessionForSharedSessionSku(ushort const *,bool &,ulong &,unsigned __int64 &)

- ea: `0x18004f79c`
- end: `0x18004fc35`
- name: `?LookupUserSessionForSharedSessionSku@UserSessionHelper@AssignedAccess@Internal@Windows@@CAJPEBGAEA_NAEAKAEA_K@Z`
- size: `1177`
- prototype: `__int64 __fastcall(LPCWCH lpString2, bool *, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004f4d4`

## callees

- `0x180006640`
- `0x180006f2c`
- `0x180008db0`
- `0x18000b694`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010590`
- `0x180016c24`
- `0x180022cdc`
- `0x18004e934`
- `0x18004eaa8`
- `0x18004eca0`
- `0x18004f79c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004fa2f`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004fa2f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004f80d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004f8f0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004f80d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004f8f0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004f9f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004f9f3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004f9b1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004f9b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSessionForSharedSessionSku(
        LPCWCH lpString2,
        bool *a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  unsigned int v13; // edi
  __int64 **v14; // rax
  __int64 *v15; // rsi
  void *v16; // rcx
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  int token_information; // eax
  void *v27; // rbx
  const char *v28; // r9
  unsigned int LastError; // edi
  __int64 v31; // rdx
  int lpString2a; // [rsp+20h] [rbp-99h]
  __int64 v33; // [rsp+50h] [rbp-69h] BYREF
  __int64 v34; // [rsp+58h] [rbp-61h] BYREF
  __int64 v35; // [rsp+60h] [rbp-59h] BYREF
  __int64 *v36; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v37; // [rsp+70h] [rbp-49h] BYREF
  __int64 v38; // [rsp+78h] [rbp-41h] BYREF
  void *Block; // [rsp+80h] [rbp-39h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp-31h] BYREF
  __int64 v41; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int64 v42; // [rsp+98h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  if ( !(unsigned __int8)IsUMgrQueryUserTokenPresent() )
  {
    v9 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
      (const char *)0x80004001LL,
      lpString2a);
    return v9;
  }
  v41 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.System.User", 0x14u, 0x13u);
  ActivationFactory = RoGetActivationFactory(v44, &GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd, &v41);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      lpString2a);
    goto LABEL_42;
  }
  v33 = 0;
  v10 = v41;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  v12 = v11(v10, &v33);
  v9 = v12;
  v13 = 0;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
      (const char *)(unsigned int)v12,
      lpString2a);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    goto LABEL_42;
  }
  v14 = (__int64 **)wil::WaitForCompletion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(
                      &Block,
                      v33);
  v15 = *v14;
  *v14 = 0;
  v36 = v15;
  v16 = Block;
  if ( Block )
  {
    Block = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v34 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  v17 = v44;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  v18 = RoGetActivationFactory(v17, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v34);
  v9 = v18;
  if ( v18 < 0 )
  {
    v19 = (unsigned int)v18;
    v20 = 256;
    goto LABEL_39;
  }
  v37 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v15 + 56))(v15, &v37);
  v9 = v21;
  if ( v21 < 0 )
  {
    v19 = (unsigned int)v21;
    v20 = 259;
    goto LABEL_39;
  }
  v22 = v37;
  if ( !v37 )
  {
    v9 = -2147023728;
    v19 = 2147943568LL;
    v20 = 260;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
      (const char *)v19,
      lpString2a);
LABEL_40:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v36);
    goto LABEL_41;
  }
  while ( 1 )
  {
    if ( v13 >= v22 )
      goto LABEL_26;
    v35 = 0;
    v23 = *v15;
    v35 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v23 + 48))(v15, v13, &v35);
    v9 = v24;
    if ( v24 < 0 )
    {
      v31 = 265;
      goto LABEL_36;
    }
    v42 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64 *))(*(_QWORD *)v34 + 136LL))(v34, v35, &v42);
    v9 = v24;
    if ( v24 < 0 )
    {
      v31 = 268;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
        (const char *)(unsigned int)v24,
        lpString2a);
      goto LABEL_33;
    }
    v38 = 0;
    v25 = UMgrQueryUserToken(v42, &v38);
    v9 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
        (const char *)(unsigned int)v25,
        lpString2a);
LABEL_32:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
LABEL_33:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v35);
      goto LABEL_40;
    }
    Block = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, v38);
    v9 = token_information;
    if ( token_information < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x112,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
        (const char *)(unsigned int)token_information,
        lpString2a);
      if ( Block )
        operator delete(Block);
      goto LABEL_32;
    }
    StringSid = 0;
    v27 = Block;
    if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
      break;
    if ( CompareStringEx(&LocaleName, 1u, StringSid, -1, lpString2, -1, 0, 0, 0) == 2 )
    {
      *a2 = 1;
      *a3 = 0;
      *a4 = v42;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      if ( v27 )
        operator delete(v27);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v35);
LABEL_26:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v36);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v41);
      return 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    if ( v27 )
      operator delete(v27);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v35);
    ++v13;
    v22 = v37;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x115,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
                v28);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  if ( v27 )
    operator delete(v27);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v35);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v36);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  v9 = LastError;
LABEL_42:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v41);
  return v9;
}

```

## disassembly

```asm
0x18004f79c  push    rbp
0x18004f79e  push    rbx
0x18004f79f  push    rsi
0x18004f7a0  push    rdi
0x18004f7a1  push    r12
0x18004f7a3  push    r13
0x18004f7a5  push    r14
0x18004f7a7  push    r15
0x18004f7a9  lea     rbp, [rsp-1Fh]
0x18004f7ae  sub     rsp, 0D8h
0x18004f7b5  mov     rax, cs:__security_cookie
0x18004f7bc  xor     rax, rsp
0x18004f7bf  mov     [rbp+57h+var_50], rax
0x18004f7c3  mov     r12, r9
0x18004f7c6  mov     r15, r8
0x18004f7c9  mov     r14, rdx
0x18004f7cc  mov     r13, rcx
0x18004f7cf  call    IsUMgrQueryUserTokenPresent
0x18004f7d4  xor     edi, edi
0x18004f7d6  test    al, al
0x18004f7d8  jz      loc_18004FBF6
0x18004f7de  mov     [rbp+57h+var_80], rdi
0x18004f7e2  mov     [rbp+57h+var_58], rdi
0x18004f7e6  lea     r9d, [rdi+13h]; unsigned int
0x18004f7ea  lea     r8d, [rdi+14h]; unsigned int
0x18004f7ee  lea     rdx, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x18004f7f5  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004f7f9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004f7fe  lea     r8, [rbp+57h+var_80]
0x18004f802  lea     rdx, _GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd
0x18004f809  mov     rcx, [rbp+57h+var_58]
0x18004f80d  call    cs:__imp_RoGetActivationFactory
0x18004f813  mov     ebx, eax
0x18004f815  test    eax, eax
0x18004f817  jns     short loc_18004F836
0x18004f819  mov     rcx, [rbp+5Fh]; this
0x18004f81d  mov     r9d, eax; char *
0x18004f820  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004f827  mov     edx, 0F8h; void *
0x18004f82c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f831  jmp     loc_18004FBEB
0x18004f836  mov     [rbp+57h+var_C0], rdi
0x18004f83a  mov     rdi, [rbp+57h+var_80]
0x18004f83e  mov     rax, [rdi]
0x18004f841  mov     rbx, [rax+38h]
0x18004f845  lea     rcx, [rbp+57h+var_C0]
0x18004f849  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004f84e  lea     rdx, [rbp+57h+var_C0]
0x18004f852  mov     rcx, rdi
0x18004f855  mov     rax, rbx
0x18004f858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f85d  mov     ebx, eax
0x18004f85f  xor     edi, edi
0x18004f861  test    eax, eax
0x18004f863  jns     short loc_18004F882
0x18004f865  mov     rcx, [rbp+5Fh]; this
0x18004f869  mov     r9d, eax; char *
0x18004f86c  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004f873  mov     edx, 0FBh; void *
0x18004f878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f87d  jmp     loc_18004FBE1
0x18004f882  mov     rdx, [rbp+57h+var_C0]
0x18004f886  lea     rcx, [rbp+57h+Block]
0x18004f88a  call    ??$WaitForCompletion@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@V?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::WaitForCompletion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS)
0x18004f88f  mov     rsi, [rax]
0x18004f892  mov     [rax], rdi
0x18004f895  mov     [rbp+57h+var_A8], rsi
0x18004f899  mov     rcx, [rbp+57h+Block]
0x18004f89d  test    rcx, rcx
0x18004f8a0  jz      short loc_18004F8B3
0x18004f8a2  mov     [rbp+57h+Block], rdi
0x18004f8a6  mov     rax, [rcx]
0x18004f8a9  mov     rax, [rax+10h]
0x18004f8ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8b2  nop
0x18004f8b3  mov     [rbp+57h+var_B8], rdi
0x18004f8b7  mov     [rbp+57h+var_58], rdi
0x18004f8bb  mov     r9d, 23h ; '#'; unsigned int
0x18004f8c1  lea     r8d, [r9+1]; unsigned int
0x18004f8c5  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18004f8cc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004f8d0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004f8d5  mov     rbx, [rbp+57h+var_58]
0x18004f8d9  lea     rcx, [rbp+57h+var_B8]
0x18004f8dd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004f8e2  lea     r8, [rbp+57h+var_B8]
0x18004f8e6  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18004f8ed  mov     rcx, rbx
0x18004f8f0  call    cs:__imp_RoGetActivationFactory
0x18004f8f6  mov     ebx, eax
0x18004f8f8  test    eax, eax
0x18004f8fa  jns     short loc_18004F909
0x18004f8fc  mov     r9d, eax
0x18004f8ff  mov     edx, 100h
0x18004f904  jmp     loc_18004FBBC
0x18004f909  mov     [rbp+57h+var_A0], edi
0x18004f90c  mov     rax, [rsi]
0x18004f90f  lea     rdx, [rbp+57h+var_A0]
0x18004f913  mov     rcx, rsi
0x18004f916  mov     rax, [rax+38h]
0x18004f91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f91f  mov     ebx, eax
0x18004f921  test    eax, eax
0x18004f923  jns     short loc_18004F932
0x18004f925  mov     r9d, eax
0x18004f928  mov     edx, 103h
0x18004f92d  jmp     loc_18004FBBC
0x18004f932  mov     eax, [rbp+57h+var_A0]
0x18004f935  test    eax, eax
0x18004f937  jz      loc_18004FBAF
0x18004f93d  cmp     edi, eax
0x18004f93f  jnb     loc_18004FAA6
0x18004f945  mov     [rbp+57h+var_B0], 0
0x18004f94d  mov     rax, [rsi]
0x18004f950  mov     [rbp+57h+var_B0], 0
0x18004f958  lea     r8, [rbp+57h+var_B0]
0x18004f95c  mov     edx, edi
0x18004f95e  mov     rcx, rsi
0x18004f961  mov     rax, [rax+30h]
0x18004f965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f96a  mov     ebx, eax
0x18004f96c  test    eax, eax
0x18004f96e  js      loc_18004FBA8
0x18004f974  mov     [rbp+57h+var_78], 0
0x18004f97c  mov     rcx, [rbp+57h+var_B8]
0x18004f980  mov     rax, [rcx]
0x18004f983  lea     r8, [rbp+57h+var_78]
0x18004f987  mov     rdx, [rbp+57h+var_B0]
0x18004f98b  mov     rax, [rax+88h]
0x18004f992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f997  mov     ebx, eax
0x18004f999  test    eax, eax
0x18004f99b  js      loc_18004FB8E
0x18004f9a1  mov     [rbp+57h+var_98], 0
0x18004f9a9  lea     rdx, [rbp+57h+var_98]
0x18004f9ad  mov     rcx, [rbp+57h+var_78]
0x18004f9b1  call    cs:__imp_UMgrQueryUserToken
0x18004f9b7  mov     ebx, eax
0x18004f9b9  test    eax, eax
0x18004f9bb  js      loc_18004FB74
0x18004f9c1  mov     [rbp+57h+Block], 0
0x18004f9c9  mov     rdx, [rbp+57h+var_98]
0x18004f9cd  lea     rcx, [rbp+57h+Block]
0x18004f9d1  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18004f9d6  mov     ebx, eax
0x18004f9d8  test    eax, eax
0x18004f9da  js      loc_18004FB39
0x18004f9e0  mov     [rbp+57h+StringSid], 0
0x18004f9e8  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18004f9ec  mov     rbx, [rbp+57h+Block]
0x18004f9f0  mov     rcx, [rbx]; Sid
0x18004f9f3  call    cs:__imp_ConvertSidToStringSidW
0x18004f9f9  xor     ecx, ecx
0x18004f9fb  test    eax, eax
0x18004f9fd  jz      loc_18004FAD4
0x18004fa03  mov     [rsp+110h+lParam], rcx; lParam
0x18004fa08  mov     [rsp+110h+lpReserved], rcx; lpReserved
0x18004fa0d  mov     [rsp+110h+lpVersionInformation], rcx; lpVersionInformation
0x18004fa12  or      eax, 0FFFFFFFFh
0x18004fa15  mov     [rsp+110h+cchCount2], eax; cchCount2
0x18004fa19  mov     [rsp+110h+lpString2], r13; lpString2
0x18004fa1e  mov     r9d, eax; cchCount1
0x18004fa21  mov     r8, [rbp+57h+StringSid]; lpString1
0x18004fa25  lea     edx, [rcx+1]; dwCmpFlags
0x18004fa28  lea     rcx, LocaleName; lpLocaleName
0x18004fa2f  call    cs:__imp_CompareStringEx
0x18004fa35  lea     rcx, [rbp+57h+StringSid]
0x18004fa39  cmp     eax, 2
0x18004fa3c  jz      short loc_18004FA6D
0x18004fa3e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004fa43  test    rbx, rbx
0x18004fa46  jz      short loc_18004FA50
0x18004fa48  mov     rcx, rbx; Block
0x18004fa4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004fa50  lea     rcx, [rbp+57h+var_98]
0x18004fa54  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004fa59  nop
0x18004fa5a  lea     rcx, [rbp+57h+var_B0]
0x18004fa5e  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004fa63  inc     edi
0x18004fa65  mov     eax, [rbp+57h+var_A0]
0x18004fa68  jmp     loc_18004F93D
0x18004fa6d  mov     byte ptr [r14], 1
0x18004fa71  mov     dword ptr [r15], 0
0x18004fa78  mov     rax, [rbp+57h+var_78]
0x18004fa7c  mov     [r12], rax
0x18004fa80  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004fa85  test    rbx, rbx
0x18004fa88  jz      short loc_18004FA92
0x18004fa8a  mov     rcx, rbx; Block
0x18004fa8d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004fa92  lea     rcx, [rbp+57h+var_98]
0x18004fa96  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004fa9b  nop
0x18004fa9c  lea     rcx, [rbp+57h+var_B0]
0x18004faa0  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004faa5  nop
0x18004faa6  lea     rcx, [rbp+57h+var_B8]
0x18004faaa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004faaf  nop
0x18004fab0  lea     rcx, [rbp+57h+var_A8]
0x18004fab4  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004fab9  nop
0x18004faba  lea     rcx, [rbp+57h+var_C0]
0x18004fabe  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004fac3  nop
0x18004fac4  lea     rcx, [rbp+57h+var_80]
0x18004fac8  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004facd  xor     eax, eax
0x18004facf  jmp     loc_18004FC15
0x18004fad4  mov     rcx, [rbp+5Fh]; this
0x18004fad8  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004fadf  mov     edx, 115h; void *
0x18004fae4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004fae9  mov     edi, eax
0x18004faeb  lea     rcx, [rbp+57h+StringSid]
0x18004faef  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004faf4  test    rbx, rbx
0x18004faf7  jz      short loc_18004FB01
0x18004faf9  mov     rcx, rbx; Block
0x18004fafc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004fb01  lea     rcx, [rbp+57h+var_98]
0x18004fb05  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004fb0a  nop
0x18004fb0b  lea     rcx, [rbp+57h+var_B0]
0x18004fb0f  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004fb14  nop
0x18004fb15  lea     rcx, [rbp+57h+var_B8]
0x18004fb19  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004fb1e  nop
0x18004fb1f  lea     rcx, [rbp+57h+var_A8]
0x18004fb23  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004fb28  nop
0x18004fb29  lea     rcx, [rbp+57h+var_C0]
0x18004fb2d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004fb32  mov     ebx, edi
0x18004fb34  jmp     loc_18004FBEB
0x18004fb39  mov     rcx, [rbp+5Fh]; this
0x18004fb3d  mov     r9d, eax; char *
0x18004fb40  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004fb47  mov     edx, 112h; void *
0x18004fb4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fb51  mov     rcx, [rbp+57h+Block]; Block
0x18004fb55  test    rcx, rcx
0x18004fb58  jz      short loc_18004FB5F
0x18004fb5a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004fb5f  lea     rcx, [rbp+57h+var_98]
0x18004fb63  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004fb68  nop
0x18004fb69  lea     rcx, [rbp+57h+var_B0]
0x18004fb6d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004fb72  jmp     short loc_18004FBCD
0x18004fb74  mov     rcx, [rbp+5Fh]; this
0x18004fb78  mov     r9d, eax; char *
0x18004fb7b  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004fb82  mov     edx, 10Fh; void *
0x18004fb87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fb8c  jmp     short loc_18004FB5F
0x18004fb8e  mov     edx, 10Ch; void *
0x18004fb93  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004fb9a  mov     r9d, eax; char *
0x18004fb9d  mov     rcx, [rbp+5Fh]; this
0x18004fba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fba6  jmp     short loc_18004FB69
0x18004fba8  mov     edx, 109h
0x18004fbad  jmp     short loc_18004FB93
0x18004fbaf  mov     ebx, 80070490h
0x18004fbb4  mov     r9d, ebx; char *
0x18004fbb7  mov     edx, 104h; void *
0x18004fbbc  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004fbc3  mov     rcx, [rbp+5Fh]; this
0x18004fbc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fbcc  nop
0x18004fbcd  lea     rcx, [rbp+57h+var_B8]
0x18004fbd1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004fbd6  nop
0x18004fbd7  lea     rcx, [rbp+57h+var_A8]
0x18004fbdb  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004fbe0  nop
0x18004fbe1  lea     rcx, [rbp+57h+var_C0]
0x18004fbe5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004fbea  nop
0x18004fbeb  lea     rcx, [rbp+57h+var_80]
0x18004fbef  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004fbf4  jmp     short loc_18004FC13
0x18004fbf6  mov     rcx, [rbp+5Fh]; this
0x18004fbfa  mov     ebx, 80004001h
0x18004fbff  mov     r9d, ebx; char *
0x18004fc02  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004fc09  mov     edx, 0F5h; void *
0x18004fc0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fc13  mov     eax, ebx
0x18004fc15  mov     rcx, [rbp+57h+var_50]
0x18004fc19  xor     rcx, rsp; StackCookie
0x18004fc1c  call    __security_check_cookie
0x18004fc21  add     rsp, 0D8h
0x18004fc28  pop     r15
0x18004fc2a  pop     r14
0x18004fc2c  pop     r13
0x18004fc2e  pop     r12
  ... truncated ...
```
