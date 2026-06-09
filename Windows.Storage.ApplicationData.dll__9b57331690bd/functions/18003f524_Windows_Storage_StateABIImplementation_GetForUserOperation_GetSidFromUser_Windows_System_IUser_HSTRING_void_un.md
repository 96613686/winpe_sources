# Windows::Storage::StateABIImplementation::GetForUserOperation::GetSidFromUser(Windows::System::IUser *,HSTRING__ * *,void * *,unsigned __int64 *)

- ea: `0x18003f524`
- end: `0x18003f7d4`
- name: `?GetSidFromUser@GetForUserOperation@StateABIImplementation@Storage@Windows@@CAJPEAUIUser@System@4@PEAPEAUHSTRING__@@PEAPEAXPEA_K@Z`
- size: `688`
- prototype: `HRESULT __fastcall(Windows::System::IUser *userParam, HSTRING__ **userSidHString, void **token, unsigned __int64 *userContextToken)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f264`

## callees

- `0x180003820`
- `0x180009400`
- `0x180009778`
- `0x1800133b4`
- `0x180013428`
- `0x180019580`
- `0x18001c6d0`
- `0x180021efc`
- `0x180026054`
- `0x18003f524`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18003f737`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18003f737`

## string_xrefs

- `0x18003f66d`: `IsUMgrGetConstrainedUserTokenPresent`
- `0x18003f746`: `UMgrGetConstrainedUserToken %u %u`
- `0x18003f777`: `GetUserSidStringByToken %u %u`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::GetForUserOperation::GetSidFromUser(
        Windows::System::IUser *userParam,
        HSTRING__ **userSidHString,
        void **token,
        unsigned __int64 *userContextToken)
{
  unsigned int v8; // edx
  HRESULT ConstrainedUserToken; // ebx
  Windows::System::IUser_vtbl *v10; // rax
  Windows::System::UserType userType; // [rsp+40h] [rbp-19h] BYREF
  Windows::System::UserAuthenticationStatus userAuthentication; // [rsp+44h] [rbp-15h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > localToken; // [rsp+48h] [rbp-11h] BYREF
  Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager> signInStateManager; // [rsp+50h] [rbp-9h] BYREF
  Windows::Internal::StringReference UserManagerClassId; // [rsp+58h] [rbp-1h] BYREF
  void *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !userParam )
  {
    v8 = 132;
LABEL_3:
    ConstrainedUserToken = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v8,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
      -2147024809);
    return (unsigned int)ConstrainedUserToken;
  }
  if ( !userSidHString )
  {
    v8 = 133;
    goto LABEL_3;
  }
  if ( !token )
  {
    v8 = 134;
    goto LABEL_3;
  }
  if ( !userContextToken )
  {
    v8 = 135;
    goto LABEL_3;
  }
  *userContextToken = 0;
  localToken.m_ptr = 0;
  Windows::Internal::StringReference::StringReference(&UserManagerClassId, (const wchar_t (*)[36])userSidHString);
  v10 = userParam->__vftable;
  signInStateManager.ptr_ = 0;
  userType = UserType_LocalUser;
  userAuthentication = UserAuthenticationStatus_Unauthenticated;
  ConstrainedUserToken = v10->get_Type(userParam, &userType);
  if ( ConstrainedUserToken >= 0 )
  {
    if ( (unsigned int)(userType - 2) > 1 )
    {
      ConstrainedUserToken = userParam->get_AuthenticationStatus(userParam, &userAuthentication);
      if ( ConstrainedUserToken >= 0 )
      {
        if ( userAuthentication )
        {
          if ( IsUMgrGetConstrainedUserTokenPresent() )
          {
            ConstrainedUserToken = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
                                     UserManagerClassId._hstring,
                                     (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager> >)&signInStateManager);
            if ( ConstrainedUserToken >= 0 )
            {
              ConstrainedUserToken = signInStateManager.ptr_->GetHandleForUser(
                                       signInStateManager.ptr_,
                                       userParam,
                                       userContextToken);
              if ( ConstrainedUserToken >= 0 )
              {
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                  &localToken,
                  0);
                ConstrainedUserToken = UMgrGetConstrainedUserToken(0, *userContextToken, 0, &localToken);
                if ( ConstrainedUserToken >= 0 )
                {
                  ConstrainedUserToken = GetUserSidStringByToken(localToken.m_ptr, userSidHString);
                  if ( ConstrainedUserToken >= 0 )
                  {
                    ConstrainedUserToken = 0;
                    *token = localToken.m_ptr;
                    localToken.m_ptr = 0;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_HrMsg(
                      retaddr,
                      0xAAu,
                      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
                      ConstrainedUserToken,
                      "GetUserSidStringByToken %u %u",
                      userType,
                      userAuthentication);
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_HrMsg(
                    retaddr,
                    0xA7u,
                    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
                    ConstrainedUserToken,
                    "UMgrGetConstrainedUserToken %u %u",
                    userType,
                    userAuthentication);
                }
              }
              else
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  0xA2u,
                  "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
                  ConstrainedUserToken,
                  "GetHandleForUser %u %u",
                  userType,
                  userAuthentication);
              }
            }
            else
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                0x9Fu,
                "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
                ConstrainedUserToken,
                "GetActivationFactory %u %u",
                userType,
                userAuthentication);
            }
          }
          else
          {
            ConstrainedUserToken = -2147467263;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x9Bu,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
              -2147467263,
              "IsUMgrGetConstrainedUserTokenPresent");
          }
        }
        else
        {
          ConstrainedUserToken = -2147023652;
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x97u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
          ConstrainedUserToken,
          "get_AuthenticationStatus %u",
          userType);
      }
    }
    else
    {
      ConstrainedUserToken = -2147023651;
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x91u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
      ConstrainedUserToken,
      "get_Type");
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&signInStateManager);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&localToken);
  return (unsigned int)ConstrainedUserToken;
}

```

## disassembly

```asm
0x18003f524  push    rbp
0x18003f526  push    rbx
0x18003f527  push    rsi
0x18003f528  push    rdi
0x18003f529  push    r14
0x18003f52b  push    r15
0x18003f52d  lea     rbp, [rsp-2Fh]
0x18003f532  sub     rsp, 88h
0x18003f539  mov     rax, cs:__security_cookie
0x18003f540  xor     rax, rsp
0x18003f543  mov     [rbp+57h+var_38], rax
0x18003f547  mov     rsi, userContextToken
0x18003f54a  mov     r14, token
0x18003f54d  mov     r15, userSidHString
0x18003f550  mov     rdi, userParam
0x18003f553  test    userParam, userParam
0x18003f556  jnz     short loc_18003F57A
0x18003f558  mov     edx, 84h; lineNumber
0x18003f55d  mov     userParam, [rbp+5Fh]; callerReturnAddress
0x18003f561  lea     token, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003f568  mov     ebx, 80070057h
0x18003f56d  mov     r9d, ebx; hr
0x18003f570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f575  jmp     loc_18003F7B6
0x18003f57a  test    r15, r15
0x18003f57d  jnz     short loc_18003F586
0x18003f57f  mov     edx, 85h
0x18003f584  jmp     short loc_18003F55D
0x18003f586  test    r14, r14
0x18003f589  jnz     short loc_18003F592
0x18003f58b  mov     edx, 86h
0x18003f590  jmp     short loc_18003F55D
0x18003f592  test    rsi, rsi
0x18003f595  jnz     short loc_18003F59E
0x18003f597  mov     edx, 87h; wchar_t (*)[36]
0x18003f59c  jmp     short loc_18003F55D
0x18003f59e  lea     userParam, [rbp+57h+UserManagerClassId]; this
0x18003f5a2  mov     qword ptr [userContextToken], 0
0x18003f5a9  mov     [rbp+57h+localToken.m_ptr], 0
0x18003f5b1  call    ??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[36])
0x18003f5b6  mov     rax, [rdi]
0x18003f5b9  lea     userSidHString, [rbp+57h+userType]
0x18003f5bd  mov     userParam, rdi
0x18003f5c0  mov     [rbp+57h+signInStateManager.ptr_], 0
0x18003f5c8  mov     [rbp+57h+userType], 0
0x18003f5cf  mov     [rbp+57h+userAuthentication], 0
0x18003f5d6  mov     rax, [rax+40h]
0x18003f5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f5df  mov     ebx, eax
0x18003f5e1  test    eax, eax
0x18003f5e3  jns     short loc_18003F5F6
0x18003f5e5  lea     rax, aGetType; "get_Type"
0x18003f5ec  mov     edx, 91h
0x18003f5f1  jmp     loc_18003F67E
0x18003f5f6  mov     eax, [rbp+57h+userType]
0x18003f5f9  add     eax, 0FFFFFFFEh
0x18003f5fc  cmp     eax, 1
0x18003f5ff  ja      short loc_18003F60B
0x18003f601  mov     ebx, 800704DDh
0x18003f606  jmp     loc_18003F7A4
0x18003f60b  mov     rax, [rdi]
0x18003f60e  lea     userSidHString, [rbp+57h+userAuthentication]
0x18003f612  mov     userParam, rdi
0x18003f615  mov     rax, [rax+38h]
0x18003f619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f61e  mov     ebx, eax
0x18003f620  test    eax, eax
0x18003f622  jns     short loc_18003F654
0x18003f624  mov     edx, [rbp+57h+userType]
0x18003f627  lea     rax, aGetAuthenticat_0; "get_AuthenticationStatus %u"
0x18003f62e  mov     userParam, [rbp+5Fh]; callerReturnAddress
0x18003f632  lea     token, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003f639  mov     [rsp+0B0h+var_88], edx
0x18003f63d  mov     r9d, ebx; hr
0x18003f640  mov     edx, 97h; lineNumber
0x18003f645  mov     [rsp+0B0h+formatString], rax; formatString
0x18003f64a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f64f  jmp     loc_18003F7A4
0x18003f654  cmp     [rbp+57h+userAuthentication], 0
0x18003f658  jnz     short loc_18003F664
0x18003f65a  mov     ebx, 800704DCh
0x18003f65f  jmp     loc_18003F7A4
0x18003f664  call    IsUMgrGetConstrainedUserTokenPresent
0x18003f669  test    al, al
0x18003f66b  jnz     short loc_18003F69B
0x18003f66d  lea     rax, aIsumgrgetconst; "IsUMgrGetConstrainedUserTokenPresent"
0x18003f674  mov     ebx, 80004001h
0x18003f679  mov     edx, 9Bh; lineNumber
0x18003f67e  mov     userParam, [rbp+5Fh]; callerReturnAddress
0x18003f682  lea     token, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003f689  mov     r9d, ebx; hr
0x18003f68c  mov     [rsp+0B0h+formatString], rax; formatString
0x18003f691  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f696  jmp     loc_18003F7A4
0x18003f69b  mov     userParam, [rbp+57h+UserManagerClassId._hstring]; activatableClassId
0x18003f69f  lea     userSidHString, [rbp+57h+signInStateManager]; factory
0x18003f6a3  call    ??$GetActivationFactory@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18003f6a8  mov     ebx, eax
0x18003f6aa  test    eax, eax
0x18003f6ac  jns     short loc_18003F6E5
0x18003f6ae  mov     edx, [rbp+57h+userAuthentication]
0x18003f6b1  lea     rax, aGetactivationf; "GetActivationFactory %u %u"
0x18003f6b8  mov     [rsp+0B0h+var_80], edx
0x18003f6bc  mov     edx, [rbp+57h+userType]
0x18003f6bf  mov     [rsp+0B0h+var_88], edx
0x18003f6c3  mov     edx, 9Fh; lineNumber
0x18003f6c8  mov     userParam, [rbp+5Fh]; callerReturnAddress
0x18003f6cc  lea     token, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003f6d3  mov     r9d, ebx; hr
0x18003f6d6  mov     [rsp+0B0h+formatString], rax; formatString
0x18003f6db  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f6e0  jmp     loc_18003F7A4
0x18003f6e5  mov     userParam, [rbp+57h+signInStateManager.ptr_]
0x18003f6e9  mov     token, rsi
0x18003f6ec  mov     userSidHString, rdi
0x18003f6ef  mov     rax, [userParam]
0x18003f6f2  mov     rax, [rax+88h]
0x18003f6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6fe  mov     ebx, eax
0x18003f700  test    eax, eax
0x18003f702  jns     short loc_18003F720
0x18003f704  mov     edx, [rbp+57h+userAuthentication]
0x18003f707  lea     rax, aGethandleforus_0; "GetHandleForUser %u %u"
0x18003f70e  mov     [rsp+0B0h+var_80], edx
0x18003f712  mov     edx, [rbp+57h+userType]
0x18003f715  mov     [rsp+0B0h+var_88], edx
0x18003f719  mov     edx, 0A2h
0x18003f71e  jmp     short loc_18003F6C8
0x18003f720  xor     edx, edx; ptr
0x18003f722  lea     userParam, [rbp+57h+localToken]; this
0x18003f726  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003f72b  mov     userSidHString, [rsi]
0x18003f72e  lea     userContextToken, [rbp+57h+localToken]
0x18003f732  xor     r8d, r8d
0x18003f735  xor     ecx, ecx
0x18003f737  call    cs:__imp_UMgrGetConstrainedUserToken
0x18003f73d  mov     ebx, eax
0x18003f73f  test    eax, eax
0x18003f741  jns     short loc_18003F762
0x18003f743  mov     edx, [rbp+57h+userAuthentication]
0x18003f746  lea     rax, aUmgrgetconstra_0; "UMgrGetConstrainedUserToken %u %u"
0x18003f74d  mov     [rsp+0B0h+var_80], edx
0x18003f751  mov     edx, [rbp+57h+userType]
0x18003f754  mov     [rsp+0B0h+var_88], edx
0x18003f758  mov     edx, 0A7h
0x18003f75d  jmp     loc_18003F6C8
0x18003f762  mov     userParam, [rbp+57h+localToken.m_ptr]; token
0x18003f766  mov     userSidHString, r15; userSidHString
0x18003f769  call    ?GetUserSidStringByToken@@YAJQEAXPEAPEAUHSTRING__@@@Z; GetUserSidStringByToken(void * const,HSTRING__ * *)
0x18003f76e  mov     ebx, eax
0x18003f770  test    eax, eax
0x18003f772  jns     short loc_18003F793
0x18003f774  mov     edx, [rbp+57h+userAuthentication]
0x18003f777  lea     rax, aGetusersidstri; "GetUserSidStringByToken %u %u"
0x18003f77e  mov     [rsp+0B0h+var_80], edx
0x18003f782  mov     edx, [rbp+57h+userType]
0x18003f785  mov     [rsp+0B0h+var_88], edx
0x18003f789  mov     edx, 0AAh
0x18003f78e  jmp     loc_18003F6C8
0x18003f793  mov     rax, [rbp+57h+localToken.m_ptr]
0x18003f797  xor     ebx, ebx
0x18003f799  mov     [r14], rax
0x18003f79c  mov     [rbp+57h+localToken.m_ptr], 0
0x18003f7a4  lea     userParam, [rbp+57h+signInStateManager]; this
0x18003f7a8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f7ad  lea     userParam, [rbp+57h+localToken]; this
0x18003f7b1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f7b6  mov     eax, ebx
0x18003f7b8  mov     userParam, [rbp+57h+var_38]
0x18003f7bc  xor     userParam, rsp; StackCookie
0x18003f7bf  call    __security_check_cookie
0x18003f7c4  add     rsp, 88h
0x18003f7cb  pop     r15
0x18003f7cd  pop     r14
0x18003f7cf  pop     rdi
0x18003f7d0  pop     rsi
0x18003f7d1  pop     rbx
0x18003f7d2  pop     rbp
0x18003f7d3  retn
```
