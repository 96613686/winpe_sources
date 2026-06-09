# ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(void)

- ea: `0x18001319c`
- end: `0x180013335`
- name: `?GenerateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@AEAAJXZ`
- size: `409`
- prototype: `HRESULT __fastcall(ConstrainedImpersonateLoggedOnUser *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013110`

## callees

- `0x180003820`
- `0x18001319c`
- `0x1800133b4`
- `0x180013428`
- `0x180021efc`
- `0x180026054`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013301`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013301`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001322b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001322b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800132c3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800132c3`

## string_xrefs

- `0x180013275`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`
- `0x180013318`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c
__int64 __fastcall ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(
        ConstrainedImpersonateLoggedOnUser *this)
{
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > *p_m_userTokenHandle; // rsi
  signed int v4; // eax
  HRESULT ConstrainedUserToken; // eax
  unsigned int v6; // ebx
  HRESULT v7; // eax
  Windows::System::Internal::ISignInStateManager *ptr; // rcx
  Windows::System::Internal::ISignInStateManager *v9; // rcx
  unsigned int v10; // edx
  Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager> signinMgr; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  void *retaddr; // [rsp+68h] [rbp+18h]

  if ( !this->m_userObject.ptr_ )
    return 0;
  p_m_userTokenHandle = &this->m_userTokenHandle;
  if ( (((unsigned __int64)this->m_userTokenHandle.m_ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
    || !IsUMgrGetConstrainedUserTokenPresent() )
  {
    return 0;
  }
  signinMgr.ptr_ = 0;
  string = 0;
  v4 = WindowsCreateStringReference(RuntimeClass_Windows_System_Internal_UserManager, 0x23u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  ConstrainedUserToken = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
                           string,
                           (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager> >)&signinMgr);
  v6 = ConstrainedUserToken;
  if ( ConstrainedUserToken < 0 )
  {
    v10 = 129;
  }
  else
  {
    v7 = signinMgr.ptr_->GetHandleForUser(signinMgr.ptr_, this->m_userObject.ptr_, &this->m_contextToken);
    v6 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x83u,
        "OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
        v7);
      ptr = signinMgr.ptr_;
      if ( signinMgr.ptr_ )
      {
        signinMgr.ptr_ = 0;
        ptr->Release(ptr);
      }
      return v6;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      p_m_userTokenHandle,
      0);
    ConstrainedUserToken = UMgrGetConstrainedUserToken(0, this->m_contextToken, 0, p_m_userTokenHandle);
    v6 = ConstrainedUserToken;
    if ( ConstrainedUserToken >= 0 )
    {
      v9 = signinMgr.ptr_;
      if ( signinMgr.ptr_ )
      {
        signinMgr.ptr_ = 0;
        v9->Release(v9);
      }
      return 0;
    }
    v10 = 133;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    v10,
    "OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
    ConstrainedUserToken);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&signinMgr);
  return v6;
}

```

## disassembly

```asm
0x18001319c  mov     [rsp-18h+arg_8], rbx
0x1800131a1  mov     [rsp-18h+arg_10], rsi
0x1800131a6  push    rbp
0x1800131a7  push    rdi
0x1800131a8  push    r14
0x1800131aa  mov     rbp, rsp
0x1800131ad  sub     rsp, 50h
0x1800131b1  mov     rax, cs:__security_cookie
0x1800131b8  xor     rax, rsp
0x1800131bb  mov     [rbp+var_8], rax
0x1800131bf  cmp     qword ptr [this+10h], 0
0x1800131c4  mov     rdi, this
0x1800131c7  jnz     short loc_1800131EC
0x1800131c9  xor     eax, eax
0x1800131cb  mov     this, [rbp+var_8]
0x1800131cf  xor     this, rsp; StackCookie
0x1800131d2  call    __security_check_cookie
0x1800131d7  lea     r11, [rsp+50h+var_s0]
0x1800131dc  mov     rbx, [r11+28h]
0x1800131e0  mov     rsi, [r11+30h]
0x1800131e4  mov     rsp, r11
0x1800131e7  pop     r14
0x1800131e9  pop     rdi
0x1800131ea  pop     rbp
0x1800131eb  retn
0x1800131ec  lea     rsi, [this+8]
0x1800131f0  mov     rax, [rsi]
0x1800131f3  inc     rax
0x1800131f6  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800131fc  jnz     short loc_1800131C9
0x1800131fe  call    IsUMgrGetConstrainedUserTokenPresent
0x180013203  test    al, al
0x180013205  jz      short loc_1800131C9
0x180013207  lea     r9, [rbp+string]; string
0x18001320b  mov     [rbp+signinMgr.ptr_], 0
0x180013213  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180013217  mov     [rbp+string], 0
0x18001321f  mov     edx, 23h ; '#'; length
0x180013224  lea     this, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; sourceString
0x18001322b  call    cs:__imp_WindowsCreateStringReference
0x180013231  test    eax, eax
0x180013233  js      loc_1800132F5
0x180013239  mov     this, [rbp+string]; activatableClassId
0x18001323d  lea     rdx, [rbp+signinMgr]; factory
0x180013241  call    ??$GetActivationFactory@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x180013246  mov     ebx, eax
0x180013248  test    eax, eax
0x18001324a  js      loc_180013308
0x180013250  mov     this, [rbp+signinMgr.ptr_]
0x180013254  lea     r8, [rdi+18h]
0x180013258  mov     rdx, [rdi+10h]
0x18001325c  mov     rax, [this]
0x18001325f  mov     rax, [rax+88h]
0x180013266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001326b  mov     ebx, eax
0x18001326d  test    eax, eax
0x18001326f  jns     short loc_1800132AD
0x180013271  mov     this, [rbp+18h]; callerReturnAddress
0x180013275  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001327c  mov     r9d, eax; hr
0x18001327f  mov     edx, 83h; lineNumber
0x180013284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013289  mov     this, [rbp+signinMgr.ptr_]
0x18001328d  test    this, this
0x180013290  jz      short loc_1800132A6
0x180013292  mov     [rbp+signinMgr.ptr_], 0
0x18001329a  mov     rax, [this]
0x18001329d  mov     rax, [rax+10h]
0x1800132a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132a6  mov     eax, ebx
0x1800132a8  jmp     loc_1800131CB
0x1800132ad  xor     edx, edx; ptr
0x1800132af  mov     this, rsi; this
0x1800132b2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800132b7  mov     rdx, [rdi+18h]
0x1800132bb  mov     r9, rsi
0x1800132be  xor     r8d, r8d
0x1800132c1  xor     ecx, ecx
0x1800132c3  call    cs:__imp_UMgrGetConstrainedUserToken
0x1800132c9  mov     ebx, eax
0x1800132cb  test    eax, eax
0x1800132cd  js      short loc_18001330F
0x1800132cf  mov     this, [rbp+signinMgr.ptr_]
0x1800132d3  test    this, this
0x1800132d6  jz      loc_1800131C9
0x1800132dc  mov     [rbp+signinMgr.ptr_], 0
0x1800132e4  mov     rax, [this]
0x1800132e7  mov     rax, [rax+10h]
0x1800132eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132f0  jmp     loc_1800131C9
0x1800132f5  xor     r9d, r9d; lpArguments
0x1800132f8  xor     r8d, r8d; nNumberOfArguments
0x1800132fb  mov     ecx, eax; dwExceptionCode
0x1800132fd  lea     edx, [r9+1]; dwExceptionFlags
0x180013301  call    cs:__imp_RaiseException
0x180013307  int     3; Trap to Debugger
0x180013308  mov     edx, 81h
0x18001330d  jmp     short loc_180013314
0x18001330f  mov     edx, 85h; lineNumber
0x180013314  mov     this, [rbp+18h]; callerReturnAddress
0x180013318  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001331f  mov     r9d, eax; hr
0x180013322  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013327  lea     this, [rbp+signinMgr]; this
0x18001332b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180013330  jmp     loc_1800132A6
```
