# WinStoreAuth::AuthenticationInternal::CreateAuthenticationManager(Windows::Internal::Security::WebAuthentication::IAuthenticationManager * *,bool)

- ea: `0x180061a20`
- end: `0x180061b5b`
- name: `?CreateAuthenticationManager@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@_N@Z`
- size: `315`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::Internal::Security::WebAuthentication::IAuthenticationManager **, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800126ec`

## callees

- `0x180004738`
- `0x180061a20`
- `0x180061b64`
- `0x180061c04`
- `0x180075e60`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061a84`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061a84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061a6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061a6e`

## string_xrefs

- `0x180061a67`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateAuthenticationManager(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Internal::Security::WebAuthentication::IAuthenticationManager **a2)
{
  HRESULT v3; // eax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v8; // eax
  __int64 v9; // rax
  int v10[4]; // [rsp+20h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  *(_QWORD *)this = 0;
  *(_QWORD *)v10 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
         0x41u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>>(
         string,
         v10);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6AC,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v4,
      v10[0]);
    v6 = *(_QWORD *)v10;
    if ( *(_QWORD *)v10 )
    {
      *(_QWORD *)v10 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
  *(GUID *)&hstringHeader.Reserved.Reserved1 = WinStoreAuth::g_guidMsaClientId;
  v8 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(**(_QWORD **)v10 + 72LL))(*(_QWORD *)v10, &hstringHeader);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6AE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v8,
      v10[0]);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v10);
    return v5;
  }
  v9 = *(_QWORD *)v10;
  *(_QWORD *)v10 = 0;
  *(_QWORD *)this = v9;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v10);
  return 0;
}

```

## disassembly

```asm
0x180061a20  mov     [rsp-8+arg_8], rbx
0x180061a25  mov     [rsp-8+arg_10], rdi
0x180061a2a  push    rbp
0x180061a2b  mov     rbp, rsp
0x180061a2e  sub     rsp, 60h
0x180061a32  mov     rax, cs:__security_cookie
0x180061a39  xor     rax, rsp
0x180061a3c  mov     [rbp+var_10], rax
0x180061a40  mov     rdi, rcx
0x180061a43  mov     qword ptr [rcx], 0
0x180061a4a  mov     qword ptr [rbp+var_40], 0
0x180061a52  mov     [rbp+string], 0
0x180061a5a  lea     r9, [rbp+string]; string
0x180061a5e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180061a62  mov     edx, 41h ; 'A'; length
0x180061a67  lea     rcx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x180061a6e  call    cs:__imp_WindowsCreateStringReference
0x180061a74  test    eax, eax
0x180061a76  jns     short loc_180061A8B
0x180061a78  xor     r9d, r9d; lpArguments
0x180061a7b  xor     r8d, r8d; nNumberOfArguments
0x180061a7e  lea     edx, [r9+1]; dwExceptionFlags
0x180061a82  mov     ecx, eax; dwExceptionCode
0x180061a84  call    cs:__imp_RaiseException
0x180061a8a  int     3; Trap to Debugger
0x180061a8b  lea     rdx, [rbp+var_40]
0x180061a8f  mov     rcx, [rbp+string]
0x180061a93  call    ??$ActivateInstance@V?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>>)
0x180061a98  mov     ebx, eax
0x180061a9a  test    eax, eax
0x180061a9c  jns     short loc_180061AD9
0x180061a9e  mov     rcx, [rbp+8]; this
0x180061aa2  mov     r9d, eax; char *
0x180061aa5  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180061aac  mov     edx, 6ACh; void *
0x180061ab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061ab6  nop
0x180061ab7  mov     rcx, qword ptr [rbp+var_40]
0x180061abb  test    rcx, rcx
0x180061abe  jz      short loc_180061AD5
0x180061ac0  mov     qword ptr [rbp+var_40], 0
0x180061ac8  mov     rax, [rcx]
0x180061acb  mov     rax, [rax+10h]
0x180061acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ad4  nop
0x180061ad5  mov     eax, ebx
0x180061ad7  jmp     short loc_180061B3D
0x180061ad9  mov     rcx, qword ptr [rbp+var_40]
0x180061add  movups  xmm0, xmmword ptr cs:?g_guidMsaClientId@WinStoreAuth@@3U_GUID@@A.Data1; _GUID WinStoreAuth::g_guidMsaClientId ...
0x180061ae4  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x180061ae9  mov     rax, [rcx]
0x180061aec  lea     rdx, [rbp+hstringHeader]
0x180061af0  mov     rax, [rax+48h]
0x180061af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061af9  mov     ebx, eax
0x180061afb  test    eax, eax
0x180061afd  jns     short loc_180061B23
0x180061aff  mov     rcx, [rbp+8]; this
0x180061b03  mov     r9d, eax; char *
0x180061b06  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180061b0d  mov     edx, 6AEh; void *
0x180061b12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061b17  nop
0x180061b18  lea     rcx, [rbp+var_40]
0x180061b1c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180061b21  jmp     short loc_180061AD5
0x180061b23  mov     rax, qword ptr [rbp+var_40]
0x180061b27  mov     qword ptr [rbp+var_40], 0
0x180061b2f  mov     [rdi], rax
0x180061b32  lea     rcx, [rbp+var_40]
0x180061b36  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180061b3b  xor     eax, eax
0x180061b3d  mov     rcx, [rbp+var_10]
0x180061b41  xor     rcx, rsp; StackCookie
0x180061b44  call    __security_check_cookie
0x180061b49  lea     r11, [rsp+60h+var_s0]
0x180061b4e  mov     rbx, [r11+18h]
0x180061b52  mov     rdi, [r11+20h]
0x180061b56  mov     rsp, r11
0x180061b59  pop     rbp
0x180061b5a  retn
```
