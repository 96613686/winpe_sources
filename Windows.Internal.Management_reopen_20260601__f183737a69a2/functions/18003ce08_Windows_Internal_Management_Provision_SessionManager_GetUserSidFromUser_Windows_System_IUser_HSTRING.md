# Windows::Internal::Management::Provision::SessionManager::GetUserSidFromUser(Windows::System::IUser *,HSTRING__ * *)

- ea: `0x18003ce08`
- end: `0x18003d02b`
- name: `?GetUserSidFromUser@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEAUIUser@System@5@PEAPEAUHSTRING__@@@Z`
- size: `547`
- prototype: `int(Windows::Internal::Management::Provision::SessionManager *__hidden this, struct Windows::System::IUser *, HSTRING *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003d110`
- `0x18003d1d0`

## callees

- `0x180004eb0`
- `0x180009be4`
- `0x18000a5c4`
- `0x1800151e0`
- `0x1800179f8`
- `0x180017ed0`
- `0x1800187d4`
- `0x18003ae88`
- `0x18003b01c`
- `0x18003ce08`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetUserSidFromToken` at `0x18003cf7a`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18003cf7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003cfc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003cfc5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18003cf2d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18003cf2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Management::Provision::SessionManager::GetUserSidFromUser(
        Windows::Internal::Management::Provision::SessionManager *this,
        struct Windows::System::IUser *a2,
        HSTRING *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  HRESULT UserSidFromToken; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v15; // [rsp+20h] [rbp-50h] BYREF
  PCNZWCH sourceString; // [rsp+28h] [rbp-48h] BYREF
  void *v17; // [rsp+30h] [rbp-40h] BYREF
  __int64 v18; // [rsp+38h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v21; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( a2 )
  {
    if ( !a3 )
    {
      v5 = 97;
      goto LABEL_3;
    }
    *a3 = 0;
    v18 = 0;
    v21 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(
           v21,
           &v18);
    v6 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
        (const char *)(unsigned int)v7,
        v15);
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
      return v6;
    }
    v15 = 0;
    v8 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(
           &v18,
           &v15);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v19 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, __int64 *))(*(_QWORD *)v15 + 136LL))(
             v15,
             a2,
             &v19);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v17 = 0;
        v10 = UMgrQueryUserToken(v19, &v17);
        v6 = v10;
        if ( v10 >= 0 )
        {
          sourceString = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &sourceString,
            0);
          UserSidFromToken = DmGetUserSidFromToken(v17, (unsigned __int16 **)&sourceString);
          v6 = UserSidFromToken;
          if ( UserSidFromToken >= 0 )
          {
            v13 = -1;
            do
              ++v13;
            while ( sourceString[v13] );
            UserSidFromToken = WindowsCreateString(sourceString, v13, a3);
            v6 = UserSidFromToken;
            if ( UserSidFromToken >= 0 )
            {
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
              v6 = 0;
              goto LABEL_25;
            }
            v12 = 118;
          }
          else
          {
            v12 = 116;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v12,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
            (const char *)(unsigned int)UserSidFromToken,
            v15);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x71,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
            (const char *)(unsigned int)v10,
            v15);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
        goto LABEL_11;
      }
      v9 = 110;
    }
    else
    {
      v9 = 107;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
      (const char *)(unsigned int)v8,
      v15);
LABEL_11:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    goto LABEL_25;
  }
  v5 = 96;
LABEL_3:
  v6 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
    (const char *)0x80070057LL,
    v15);
  return v6;
}

```

## disassembly

```asm
0x18003ce08  mov     [rsp-18h+arg_0], rbx
0x18003ce0d  mov     [rsp-18h+arg_18], rsi
0x18003ce12  push    rbp
0x18003ce13  push    rdi
0x18003ce14  push    r14
0x18003ce16  mov     rbp, rsp
0x18003ce19  sub     rsp, 70h
0x18003ce1d  mov     rax, cs:__security_cookie
0x18003ce24  xor     rax, rsp
0x18003ce27  mov     [rbp+var_8], rax
0x18003ce2b  mov     rdi, r8
0x18003ce2e  mov     rsi, rdx
0x18003ce31  xor     r14d, r14d
0x18003ce34  test    rdx, rdx
0x18003ce37  jnz     short loc_18003CE59
0x18003ce39  lea     edx, [rsi+60h]; void *
0x18003ce3c  mov     ebx, 80070057h
0x18003ce41  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003ce48  mov     r9d, ebx; char *
0x18003ce4b  mov     rcx, [rbp+18h]; this
0x18003ce4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ce54  jmp     loc_18003D007
0x18003ce59  test    rdi, rdi
0x18003ce5c  jnz     short loc_18003CE63
0x18003ce5e  lea     edx, [rdi+61h]
0x18003ce61  jmp     short loc_18003CE3C
0x18003ce63  mov     [r8], r14
0x18003ce66  mov     [rbp+var_38], r14
0x18003ce6a  mov     [rbp+var_10], r14
0x18003ce6e  mov     r9d, 23h ; '#'; unsigned int
0x18003ce74  lea     r8d, [r9+1]; unsigned int
0x18003ce78  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18003ce7f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18003ce83  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003ce88  lea     rdx, [rbp+var_38]
0x18003ce8c  mov     rcx, [rbp+var_10]
0x18003ce90  call    ??$GetActivationFactory@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>)
0x18003ce95  mov     ebx, eax
0x18003ce97  test    eax, eax
0x18003ce99  jns     short loc_18003CEB8
0x18003ce9b  mov     rcx, [rbp+18h]; this
0x18003ce9f  mov     r9d, eax; char *
0x18003cea2  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cea9  mov     edx, 68h ; 'h'; void *
0x18003ceae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ceb3  jmp     loc_18003CFFE
0x18003ceb8  mov     [rbp+var_50], r14
0x18003cebc  lea     rdx, [rbp+var_50]
0x18003cec0  lea     rcx, [rbp+var_38]
0x18003cec4  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18003cec9  mov     ebx, eax
0x18003cecb  test    eax, eax
0x18003cecd  jns     short loc_18003CEF6
0x18003cecf  mov     edx, 6Bh ; 'k'; void *
0x18003ced4  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cedb  mov     r9d, eax; char *
0x18003cede  mov     rcx, [rbp+18h]; this
0x18003cee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cee7  nop
0x18003cee8  lea     rcx, [rbp+var_50]
0x18003ceec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003cef1  jmp     loc_18003CFFE
0x18003cef6  mov     [rbp+var_30], r14
0x18003cefa  mov     rcx, [rbp+var_50]
0x18003cefe  mov     rax, [rcx]
0x18003cf01  lea     r8, [rbp+var_30]
0x18003cf05  mov     rdx, rsi
0x18003cf08  mov     rax, [rax+88h]
0x18003cf0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf14  mov     ebx, eax
0x18003cf16  test    eax, eax
0x18003cf18  jns     short loc_18003CF21
0x18003cf1a  mov     edx, 6Eh ; 'n'
0x18003cf1f  jmp     short loc_18003CED4
0x18003cf21  mov     [rbp+var_40], r14
0x18003cf25  lea     rdx, [rbp+var_40]
0x18003cf29  mov     rcx, [rbp+var_30]
0x18003cf2d  call    cs:__imp_UMgrQueryUserToken
0x18003cf34  nop     dword ptr [rax+rax+00h]
0x18003cf39  mov     ebx, eax
0x18003cf3b  test    eax, eax
0x18003cf3d  jns     short loc_18003CF63
0x18003cf3f  mov     rcx, [rbp+18h]; this
0x18003cf43  mov     r9d, eax; char *
0x18003cf46  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cf4d  mov     edx, 71h ; 'q'; void *
0x18003cf52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cf57  nop
0x18003cf58  lea     rcx, [rbp+var_40]
0x18003cf5c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003cf61  jmp     short loc_18003CEE8
0x18003cf63  mov     [rbp+sourceString], r14
0x18003cf67  xor     edx, edx
0x18003cf69  lea     rcx, [rbp+sourceString]
0x18003cf6d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003cf72  lea     rdx, [rbp+sourceString]
0x18003cf76  mov     rcx, [rbp+var_40]
0x18003cf7a  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18003cf81  nop     dword ptr [rax+rax+00h]
0x18003cf86  mov     ebx, eax
0x18003cf88  test    eax, eax
0x18003cf8a  jns     short loc_18003CFB0
0x18003cf8c  mov     edx, 74h ; 't'; void *
0x18003cf91  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cf98  mov     r9d, eax; char *
0x18003cf9b  mov     rcx, [rbp+18h]; this
0x18003cf9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cfa4  nop
0x18003cfa5  lea     rcx, [rbp+sourceString]
0x18003cfa9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cfae  jmp     short loc_18003CF58
0x18003cfb0  mov     rcx, [rbp+sourceString]; sourceString
0x18003cfb4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003cfb8  inc     rdx; length
0x18003cfbb  cmp     [rcx+rdx*2], r14w
0x18003cfc0  jnz     short loc_18003CFB8
0x18003cfc2  mov     r8, rdi; string
0x18003cfc5  call    cs:__imp_WindowsCreateString
0x18003cfcc  nop     dword ptr [rax+rax+00h]
0x18003cfd1  mov     ebx, eax
0x18003cfd3  test    eax, eax
0x18003cfd5  jns     short loc_18003CFDE
0x18003cfd7  mov     edx, 76h ; 'v'
0x18003cfdc  jmp     short loc_18003CF91
0x18003cfde  lea     rcx, [rbp+sourceString]
0x18003cfe2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cfe7  nop
0x18003cfe8  lea     rcx, [rbp+var_40]
0x18003cfec  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003cff1  nop
0x18003cff2  lea     rcx, [rbp+var_50]
0x18003cff6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003cffb  mov     ebx, r14d
0x18003cffe  lea     rcx, [rbp+var_38]
0x18003d002  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d007  mov     eax, ebx
0x18003d009  mov     rcx, [rbp+var_8]
0x18003d00d  xor     rcx, rsp; StackCookie
0x18003d010  call    __security_check_cookie
0x18003d015  lea     r11, [rsp+70h+var_s0]
0x18003d01a  mov     rbx, [r11+20h]
0x18003d01e  mov     rsi, [r11+38h]
0x18003d022  mov     rsp, r11
0x18003d025  pop     r14
0x18003d027  pop     rdi
0x18003d028  pop     rbp
0x18003d029  retn
```
