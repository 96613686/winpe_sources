# WinStoreAuth::AuthenticationInternal::CreateAuthenticationManager(Windows::Internal::Security::WebAuthentication::IAuthenticationManager * *,bool)

- ea: `0x18003a548`
- end: `0x18003a706`
- name: `?CreateAuthenticationManager@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *this, struct Windows::Internal::Security::WebAuthentication::IAuthenticationManager **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800403c4`

## callees

- `0x1800026b0`
- `0x18000dc67`
- `0x180010b84`
- `0x18002fbb4`
- `0x18003a548`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a596`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a596`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003a5dd`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003a5dd`

## string_xrefs

- `0x18003a58f`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateAuthenticationManager(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Internal::Security::WebAuthentication::IAuthenticationManager **a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ebx
  __int64 v7; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-50h] BYREF
  GUID v12; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  *(_QWORD *)this = 0;
  v11 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
         0x41u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x18003A705LL);
  }
  v11 = 0;
  *(_QWORD *)&v12.Data1 = 0;
  v6 = RoActivateInstance(string, &v12);
  if ( v6 >= 0 )
  {
    if ( !memcmp_0(&GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v11 = *(_QWORD *)&v12.Data1;
    }
    else
    {
      v6 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v12.Data1)(
             *(_QWORD *)&v12.Data1,
             &GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb,
             &v11);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v12.Data1 + 16LL))(*(_QWORD *)&v12.Data1);
    }
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6AC,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v6,
      v11);
    v7 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return (unsigned int)v6;
  }
  v12 = WinStoreAuth::g_guidMsaClientId;
  v9 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v11 + 72LL))(v11, &v12);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6AE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v9,
      v11);
    v10 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return (unsigned int)v6;
  }
  *(_QWORD *)this = v11;
  return 0;
}

```

## disassembly

```asm
0x18003a548  mov     [rsp-8+arg_8], rbx
0x18003a54d  mov     [rsp-8+arg_10], rdi
0x18003a552  push    rbp
0x18003a553  mov     rbp, rsp
0x18003a556  sub     rsp, 70h
0x18003a55a  mov     rax, cs:__security_cookie
0x18003a561  xor     rax, rsp
0x18003a564  mov     [rbp+var_10], rax
0x18003a568  mov     rdi, rcx
0x18003a56b  mov     qword ptr [rcx], 0
0x18003a572  mov     [rbp+var_50], 0
0x18003a57a  mov     [rbp+string], 0
0x18003a582  lea     r9, [rbp+string]; string
0x18003a586  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003a58a  mov     edx, 41h ; 'A'; length
0x18003a58f  lea     rcx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x18003a596  call    cs:__imp_WindowsCreateStringReference
0x18003a59c  test    eax, eax
0x18003a59e  js      loc_18003A6FE
0x18003a5a4  mov     rbx, [rbp+string]
0x18003a5a8  mov     rcx, [rbp+var_50]
0x18003a5ac  test    rcx, rcx
0x18003a5af  jz      short loc_18003A5C6
0x18003a5b1  mov     [rbp+var_50], 0
0x18003a5b9  mov     rax, [rcx]
0x18003a5bc  mov     rax, [rax+10h]
0x18003a5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5c5  nop
0x18003a5c6  mov     [rbp+var_50], 0
0x18003a5ce  mov     qword ptr [rbp+var_40], 0
0x18003a5d6  lea     rdx, [rbp+var_40]
0x18003a5da  mov     rcx, rbx
0x18003a5dd  call    cs:__imp_RoActivateInstance
0x18003a5e3  mov     ebx, eax
0x18003a5e5  test    eax, eax
0x18003a5e7  js      short loc_18003A639
0x18003a5e9  mov     r8d, 10h; Size
0x18003a5ef  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18003a5f6  lea     rcx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb; Buf1
0x18003a5fd  call    memcmp_0
0x18003a602  mov     rcx, qword ptr [rbp+var_40]
0x18003a606  test    eax, eax
0x18003a608  jnz     short loc_18003A610
0x18003a60a  mov     [rbp+var_50], rcx
0x18003a60e  jmp     short loc_18003A639
0x18003a610  mov     rax, [rcx]
0x18003a613  lea     r8, [rbp+var_50]
0x18003a617  lea     rdx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb
0x18003a61e  mov     rax, [rax]
0x18003a621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a626  mov     ebx, eax
0x18003a628  mov     rcx, qword ptr [rbp+var_40]
0x18003a62c  mov     rax, [rcx]
0x18003a62f  mov     rax, [rax+10h]
0x18003a633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a638  nop
0x18003a639  test    ebx, ebx
0x18003a63b  jns     short loc_18003A678
0x18003a63d  mov     rcx, [rbp+8]; this
0x18003a641  mov     r9d, ebx; char *
0x18003a644  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003a64b  mov     edx, 6ACh; void *
0x18003a650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a655  nop
0x18003a656  mov     rcx, [rbp+var_50]
0x18003a65a  test    rcx, rcx
0x18003a65d  jz      short loc_18003A674
0x18003a65f  mov     [rbp+var_50], 0
0x18003a667  mov     rax, [rcx]
0x18003a66a  mov     rax, [rax+10h]
0x18003a66e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a673  nop
0x18003a674  mov     eax, ebx
0x18003a676  jmp     short loc_18003A6E0
0x18003a678  mov     rcx, [rbp+var_50]
0x18003a67c  movups  xmm0, xmmword ptr cs:?g_guidMsaClientId@WinStoreAuth@@3U_GUID@@A.Data1; _GUID WinStoreAuth::g_guidMsaClientId ...
0x18003a683  movdqu  [rbp+var_40], xmm0
0x18003a688  mov     rax, [rcx]
0x18003a68b  lea     rdx, [rbp+var_40]
0x18003a68f  mov     rax, [rax+48h]
0x18003a693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a698  mov     ebx, eax
0x18003a69a  test    eax, eax
0x18003a69c  jns     short loc_18003A6D7
0x18003a69e  mov     rcx, [rbp+8]; this
0x18003a6a2  mov     r9d, eax; char *
0x18003a6a5  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003a6ac  mov     edx, 6AEh; void *
0x18003a6b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a6b6  nop
0x18003a6b7  mov     rcx, [rbp+var_50]
0x18003a6bb  test    rcx, rcx
0x18003a6be  jz      short loc_18003A6D5
0x18003a6c0  mov     [rbp+var_50], 0
0x18003a6c8  mov     rax, [rcx]
0x18003a6cb  mov     rax, [rax+10h]
0x18003a6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6d4  nop
0x18003a6d5  jmp     short loc_18003A674
0x18003a6d7  mov     rax, [rbp+var_50]
0x18003a6db  mov     [rdi], rax
0x18003a6de  xor     eax, eax
0x18003a6e0  mov     rcx, [rbp+var_10]
0x18003a6e4  xor     rcx, rsp; StackCookie
0x18003a6e7  call    __security_check_cookie
0x18003a6ec  lea     r11, [rsp+70h+var_s0]
0x18003a6f1  mov     rbx, [r11+18h]
0x18003a6f5  mov     rdi, [r11+20h]
0x18003a6f9  mov     rsp, r11
0x18003a6fc  pop     rbp
0x18003a6fd  retn
0x18003a6fe  mov     ecx, eax; this
0x18003a700  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
