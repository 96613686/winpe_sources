# Windows::Internal::Management::Provision::SessionManager::GetUserSidFromUser(Windows::System::IUser *,HSTRING__ * *)

- ea: `0x18003d4c4`
- end: `0x18003d6d4`
- name: `?GetUserSidFromUser@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEAUIUser@System@5@PEAPEAUHSTRING__@@@Z`
- size: `528`
- prototype: `int(Windows::Internal::Management::Provision::SessionManager *__hidden this, struct Windows::System::IUser *, HSTRING *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003d7b0`
- `0x18003d870`

## callees

- `0x180004d50`
- `0x18000992c`
- `0x18000a2a4`
- `0x180014af0`
- `0x180017204`
- `0x1800176c4`
- `0x180019fb8`
- `0x18003b6f8`
- `0x18003b88c`
- `0x18003d4c4`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetUserSidFromToken` at `0x18003d630`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18003d630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d675`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d675`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18003d5e9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18003d5e9`

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
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-38h] BYREF
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
           (__int64)&v18);
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
           (__int64)&v15);
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
0x18003d4c4  mov     [rsp-18h+arg_0], rbx
0x18003d4c9  mov     [rsp-18h+arg_18], rsi
0x18003d4ce  push    rbp
0x18003d4cf  push    rdi
0x18003d4d0  push    r14
0x18003d4d2  mov     rbp, rsp
0x18003d4d5  sub     rsp, 70h
0x18003d4d9  mov     rax, cs:__security_cookie
0x18003d4e0  xor     rax, rsp
0x18003d4e3  mov     [rbp+var_8], rax
0x18003d4e7  mov     rdi, r8
0x18003d4ea  mov     rsi, rdx
0x18003d4ed  xor     r14d, r14d
0x18003d4f0  test    rdx, rdx
0x18003d4f3  jnz     short loc_18003D515
0x18003d4f5  lea     edx, [rsi+60h]; void *
0x18003d4f8  mov     ebx, 80070057h
0x18003d4fd  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003d504  mov     r9d, ebx; char *
0x18003d507  mov     rcx, [rbp+18h]; this
0x18003d50b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d510  jmp     loc_18003D6B1
0x18003d515  test    rdi, rdi
0x18003d518  jnz     short loc_18003D51F
0x18003d51a  lea     edx, [rdi+61h]
0x18003d51d  jmp     short loc_18003D4F8
0x18003d51f  mov     [r8], r14
0x18003d522  mov     [rbp+var_38], r14
0x18003d526  mov     [rbp+var_10], r14
0x18003d52a  mov     r9d, 23h ; '#'; unsigned int
0x18003d530  lea     r8d, [r9+1]; unsigned int
0x18003d534  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18003d53b  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18003d53f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003d544  lea     rdx, [rbp+var_38]
0x18003d548  mov     rcx, [rbp+var_10]
0x18003d54c  call    ??$GetActivationFactory@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>)
0x18003d551  mov     ebx, eax
0x18003d553  test    eax, eax
0x18003d555  jns     short loc_18003D574
0x18003d557  mov     rcx, [rbp+18h]; this
0x18003d55b  mov     r9d, eax; char *
0x18003d55e  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003d565  mov     edx, 68h ; 'h'; void *
0x18003d56a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d56f  jmp     loc_18003D6A8
0x18003d574  mov     [rbp+var_50], r14
0x18003d578  lea     rdx, [rbp+var_50]
0x18003d57c  lea     rcx, [rbp+var_38]
0x18003d580  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18003d585  mov     ebx, eax
0x18003d587  test    eax, eax
0x18003d589  jns     short loc_18003D5B2
0x18003d58b  mov     edx, 6Bh ; 'k'; void *
0x18003d590  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003d597  mov     r9d, eax; char *
0x18003d59a  mov     rcx, [rbp+18h]; this
0x18003d59e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d5a3  nop
0x18003d5a4  lea     rcx, [rbp+var_50]
0x18003d5a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d5ad  jmp     loc_18003D6A8
0x18003d5b2  mov     [rbp+var_30], r14
0x18003d5b6  mov     rcx, [rbp+var_50]
0x18003d5ba  mov     rax, [rcx]
0x18003d5bd  lea     r8, [rbp+var_30]
0x18003d5c1  mov     rdx, rsi
0x18003d5c4  mov     rax, [rax+88h]
0x18003d5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5d0  mov     ebx, eax
0x18003d5d2  test    eax, eax
0x18003d5d4  jns     short loc_18003D5DD
0x18003d5d6  mov     edx, 6Eh ; 'n'
0x18003d5db  jmp     short loc_18003D590
0x18003d5dd  mov     [rbp+var_40], r14
0x18003d5e1  lea     rdx, [rbp+var_40]
0x18003d5e5  mov     rcx, [rbp+var_30]
0x18003d5e9  call    cs:__imp_UMgrQueryUserToken
0x18003d5ef  mov     ebx, eax
0x18003d5f1  test    eax, eax
0x18003d5f3  jns     short loc_18003D619
0x18003d5f5  mov     rcx, [rbp+18h]; this
0x18003d5f9  mov     r9d, eax; char *
0x18003d5fc  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003d603  mov     edx, 71h ; 'q'; void *
0x18003d608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d60d  nop
0x18003d60e  lea     rcx, [rbp+var_40]
0x18003d612  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003d617  jmp     short loc_18003D5A4
0x18003d619  mov     [rbp+sourceString], r14
0x18003d61d  xor     edx, edx
0x18003d61f  lea     rcx, [rbp+sourceString]
0x18003d623  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003d628  lea     rdx, [rbp+sourceString]
0x18003d62c  mov     rcx, [rbp+var_40]
0x18003d630  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18003d636  mov     ebx, eax
0x18003d638  test    eax, eax
0x18003d63a  jns     short loc_18003D660
0x18003d63c  mov     edx, 74h ; 't'; void *
0x18003d641  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003d648  mov     r9d, eax; char *
0x18003d64b  mov     rcx, [rbp+18h]; this
0x18003d64f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d654  nop
0x18003d655  lea     rcx, [rbp+sourceString]
0x18003d659  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d65e  jmp     short loc_18003D60E
0x18003d660  mov     rcx, [rbp+sourceString]; sourceString
0x18003d664  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003d668  inc     rdx; length
0x18003d66b  cmp     [rcx+rdx*2], r14w
0x18003d670  jnz     short loc_18003D668
0x18003d672  mov     r8, rdi; string
0x18003d675  call    cs:__imp_WindowsCreateString
0x18003d67b  mov     ebx, eax
0x18003d67d  test    eax, eax
0x18003d67f  jns     short loc_18003D688
0x18003d681  mov     edx, 76h ; 'v'
0x18003d686  jmp     short loc_18003D641
0x18003d688  lea     rcx, [rbp+sourceString]
0x18003d68c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d691  nop
0x18003d692  lea     rcx, [rbp+var_40]
0x18003d696  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003d69b  nop
0x18003d69c  lea     rcx, [rbp+var_50]
0x18003d6a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d6a5  mov     ebx, r14d
0x18003d6a8  lea     rcx, [rbp+var_38]
0x18003d6ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d6b1  mov     eax, ebx
0x18003d6b3  mov     rcx, [rbp+var_8]
0x18003d6b7  xor     rcx, rsp; StackCookie
0x18003d6ba  call    __security_check_cookie
0x18003d6bf  lea     r11, [rsp+70h+var_s0]
0x18003d6c4  mov     rbx, [r11+20h]
0x18003d6c8  mov     rsi, [r11+38h]
0x18003d6cc  mov     rsp, r11
0x18003d6cf  pop     r14
0x18003d6d1  pop     rdi
0x18003d6d2  pop     rbp
0x18003d6d3  retn
```
