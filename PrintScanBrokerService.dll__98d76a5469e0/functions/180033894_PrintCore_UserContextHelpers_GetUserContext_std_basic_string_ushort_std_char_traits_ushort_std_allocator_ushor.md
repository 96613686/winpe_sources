# PrintCore::UserContextHelpers::GetUserContext(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64 *)

- ea: `0x180033894`
- end: `0x180033aa0`
- name: `?GetUserContext@UserContextHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_K@Z`
- size: `524`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180033484`
- `0x180034ae0`

## callees

- `0x180002d40`
- `0x18000f8a8`
- `0x18001255c`
- `0x18001c5dc`
- `0x18001cfd4`
- `0x18001d058`
- `0x180023264`
- `0x180028758`
- `0x1800331a4`
- `0x180033894`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180033961`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180033961`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800338e4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800338e4`

## string_xrefs

- `0x1800339bb`: `Failed to get the SID attached to the token!`
- `0x18003396f`: `UMgrQueryUserToken failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall PrintCore::UserContextHelpers::GetUserContext(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  char v6; // si
  __m128i si128; // xmm6
  unsigned int v8; // eax
  unsigned int UserSidFromToken; // eax
  const char *v11; // [rsp+28h] [rbp-70h]
  const char *v12; // [rsp+28h] [rbp-70h]
  const char *v13; // [rsp+28h] [rbp-70h]
  char *v14; // [rsp+30h] [rbp-68h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-60h] BYREF
  __int64 v16; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v17[2]; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *a2 = 0;
  LODWORD(v14) = 0;
  v16 = 0;
  v4 = UMgrEnumerateSessionUsers(&v14, &v16);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x41,
    (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\usercontexthelpers.h",
    (const char *)v4,
    (int)"UMgrEnumerateSessionUsers failed!",
    v11);
  v5 = 0;
  v6 = 1;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v5 < (unsigned int)v14 )
  {
    if ( *(_DWORD *)(v16 + 16LL * v5 + 8) )
    {
      TokenHandle = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      v8 = UMgrQueryUserToken(*(_QWORD *)(v16 + 16LL * v5), &TokenHandle);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4B,
        (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\usercontexthelpers.h",
        (const char *)v8,
        (int)"UMgrQueryUserToken failed!",
        v12);
      v17[0] = 0;
      v17[1] = si128;
      LOWORD(v17[0]) = 0;
      UserSidFromToken = PrintCore::TokenHelpers::GetUserSidFromToken(TokenHandle, v17);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4F,
        (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\usercontexthelpers.h",
        (const char *)UserSidFromToken,
        (int)"Failed to get the SID attached to the token!",
        v13);
      if ( (unsigned __int8)PrintCore::StringHelpers::IEquals(a1, v17) )
      {
        *a2 = *(_QWORD *)(v16 + 16LL * v5);
        std::wstring::_Tidy_deallocate(v17);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        v6 = 0;
        break;
      }
      std::wstring::_Tidy_deallocate(v17);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    ++v5;
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x5B,
    (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\usercontexthelpers.h",
    (const char *)0x80070057LL,
    v6,
    (bool)"Failed to find the active user's context!",
    v14);
  wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v16);
  return 0;
}

```

## disassembly

```asm
0x180033894  mov     r11, rsp
0x180033897  mov     [r11+18h], rbx
0x18003389b  mov     [r11+20h], rsi
0x18003389f  push    rdi
0x1800338a0  push    r14
0x1800338a2  push    r15
0x1800338a4  sub     rsp, 80h
0x1800338ab  movaps  [rsp+98h+var_28], xmm6
0x1800338b0  mov     rax, cs:__security_cookie
0x1800338b7  xor     rax, rsp
0x1800338ba  mov     [rsp+98h+var_30], rax
0x1800338bf  mov     r14, rdx
0x1800338c2  mov     r15, rcx
0x1800338c5  mov     qword ptr [rdx], 0
0x1800338cc  mov     dword ptr [rsp+98h+var_68], 0; char *
0x1800338d4  mov     qword ptr [r11-58h], 0
0x1800338dc  lea     rdx, [r11-58h]
0x1800338e0  lea     rcx, [r11-68h]
0x1800338e4  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800338ea  mov     rcx, [rsp+98h]; this
0x1800338f2  lea     rdx, aUmgrenumerates_0; "UMgrEnumerateSessionUsers failed!"
0x1800338f9  mov     qword ptr [rsp+98h+var_78], rdx; int
0x1800338fe  mov     r9d, eax; char *
0x180033901  lea     r8, aOnecoreuapInte_1; "OneCoreUap\\Internal\\Printscan\\inc\\u"...
0x180033908  mov     edx, 41h ; 'A'; void *
0x18003390d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033912  xor     ebx, ebx
0x180033914  lea     esi, [rbx+1]
0x180033917  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003391f  cmp     ebx, dword ptr [rsp+98h+var_68]
0x180033923  jnb     loc_180033A14
0x180033929  mov     edi, ebx
0x18003392b  add     rdi, rdi
0x18003392e  mov     rax, [rsp+98h+var_58]
0x180033933  cmp     dword ptr [rax+rdi*8+8], 0
0x180033938  jz      loc_180033A97
0x18003393e  mov     [rsp+98h+TokenHandle], 0
0x180033947  xor     edx, edx
0x180033949  lea     rcx, [rsp+98h+TokenHandle]
0x18003394e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180033953  lea     rdx, [rsp+98h+TokenHandle]
0x180033958  mov     rcx, [rsp+98h+var_58]
0x18003395d  mov     rcx, [rcx+rdi*8]
0x180033961  call    cs:__imp_UMgrQueryUserToken
0x180033967  mov     rcx, [rsp+98h]; this
0x18003396f  lea     rdx, aUmgrqueryusert_0; "UMgrQueryUserToken failed!"
0x180033976  mov     qword ptr [rsp+98h+var_78], rdx; int
0x18003397b  mov     r9d, eax; char *
0x18003397e  lea     r8, aOnecoreuapInte_1; "OneCoreUap\\Internal\\Printscan\\inc\\u"...
0x180033985  mov     edx, 4Bh ; 'K'; void *
0x18003398a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003398f  xorps   xmm0, xmm0
0x180033992  movups  [rsp+98h+var_50], xmm0
0x180033997  movdqu  [rsp+98h+var_40], xmm6
0x18003399d  xor     eax, eax
0x18003399f  mov     word ptr [rsp+98h+var_50], ax
0x1800339a4  lea     rdx, [rsp+98h+var_50]
0x1800339a9  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x1800339ae  call    ?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::wstring &)
0x1800339b3  mov     rcx, [rsp+98h]; this
0x1800339bb  lea     rdx, aFailedToGetThe_3; "Failed to get the SID attached to the t"...
0x1800339c2  mov     qword ptr [rsp+98h+var_78], rdx; int
0x1800339c7  mov     r9d, eax; char *
0x1800339ca  lea     r8, aOnecoreuapInte_1; "OneCoreUap\\Internal\\Printscan\\inc\\u"...
0x1800339d1  mov     edx, 4Fh ; 'O'; void *
0x1800339d6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800339db  lea     rdx, [rsp+98h+var_50]
0x1800339e0  mov     rcx, r15
0x1800339e3  call    ?IEquals@StringHelpers@PrintCore@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::StringHelpers::IEquals(std::wstring const &,std::wstring const &)
0x1800339e8  test    al, al
0x1800339ea  jz      loc_180033A82
0x1800339f0  mov     rax, [rsp+98h+var_58]
0x1800339f5  mov     rcx, [rax+rdi*8]
0x1800339f9  mov     [r14], rcx
0x1800339fc  lea     rcx, [rsp+98h+var_50]
0x180033a01  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033a06  nop
0x180033a07  lea     rcx, [rsp+98h+TokenHandle]
0x180033a0c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180033a11  xor     sil, sil
0x180033a14  mov     rcx, [rsp+98h]; this
0x180033a1c  lea     rax, aFailedToFindTh; "Failed to find the active user's contex"...
0x180033a23  mov     qword ptr [rsp+98h+var_70], rax; bool
0x180033a28  mov     [rsp+98h+var_78], sil; char
0x180033a2d  mov     r9d, 80070057h; char *
0x180033a33  lea     r8, aOnecoreuapInte_1; "OneCoreUap\\Internal\\Printscan\\inc\\u"...
0x180033a3a  mov     edx, 5Bh ; '['; void *
0x180033a3f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180033a44  nop
0x180033a45  lea     rcx, [rsp+98h+var_58]
0x180033a4a  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x180033a4f  xor     eax, eax
0x180033a51  jmp     short loc_180033A57
0x180033a53  mov     eax, dword ptr [rsp+98h+var_68]
0x180033a57  mov     rcx, [rsp+98h+var_30]
0x180033a5c  xor     rcx, rsp; StackCookie
0x180033a5f  call    __security_check_cookie
0x180033a64  lea     r11, [rsp+98h+var_18]
0x180033a6c  mov     rbx, [r11+30h]
0x180033a70  mov     rsi, [r11+38h]
0x180033a74  movaps  xmm6, [rsp+98h+var_28]
0x180033a79  mov     rsp, r11
0x180033a7c  pop     r15
0x180033a7e  pop     r14
0x180033a80  pop     rdi
0x180033a81  retn
0x180033a82  lea     rcx, [rsp+98h+var_50]
0x180033a87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033a8c  nop
0x180033a8d  lea     rcx, [rsp+98h+TokenHandle]
0x180033a92  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180033a97  add     ebx, esi
0x180033a99  jmp     loc_18003391F
```
