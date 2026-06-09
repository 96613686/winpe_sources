# ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(void)

- ea: `0x1800276dc`
- end: `0x180027805`
- name: `?GenerateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@AEAAJXZ`
- size: `297`
- prototype: `__int64 __fastcall(ConstrainedImpersonateLoggedOnUser *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027310`

## callees

- `0x180004110`
- `0x180006eac`
- `0x18000e87c`
- `0x180011ffc`
- `0x180019e0c`
- `0x1800224e4`
- `0x1800276dc`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800277ae`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800277ae`

## string_xrefs

- `0x1800277c2`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(
        ConstrainedImpersonateLoggedOnUser *this)
{
  char *v2; // rsi
  int ConstrainedUserToken; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7[2]; // [rsp+20h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-50h] BYREF
  __int64 v9; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( *((_QWORD *)this + 2) )
  {
    v2 = (char *)this + 8;
    if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
      {
        *(_QWORD *)v7 = 0;
        v9 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.System.Internal.UserManager",
          0x24u,
          0x23u);
        ConstrainedUserToken = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
                                 v9,
                                 v7);
        v4 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          v5 = 129;
LABEL_10:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v5,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
            (const char *)(unsigned int)ConstrainedUserToken,
            v7[0]);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v7);
          return v4;
        }
        ConstrainedUserToken = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**(_QWORD **)v7 + 136LL))(
                                 *(_QWORD *)v7,
                                 *((_QWORD *)this + 2),
                                 (char *)this + 24);
        v4 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          v5 = 131;
          goto LABEL_10;
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          v2,
          0);
        ConstrainedUserToken = UMgrGetConstrainedUserToken(0, *((_QWORD *)this + 3), 0, v2);
        v4 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          v5 = 133;
          goto LABEL_10;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v7);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800276dc  push    rbx
0x1800276de  push    rsi
0x1800276df  push    rdi
0x1800276e0  push    r14
0x1800276e2  sub     rsp, 58h
0x1800276e6  mov     rax, cs:__security_cookie
0x1800276ed  xor     rax, rsp
0x1800276f0  mov     [rsp+78h+var_30], rax
0x1800276f5  mov     rdi, rcx
0x1800276f8  cmp     qword ptr [rcx+10h], 0
0x1800276fd  jz      loc_1800277EC
0x180027703  lea     rsi, [rcx+8]
0x180027707  mov     rax, [rsi]
0x18002770a  inc     rax
0x18002770d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180027713  jnz     loc_1800277EC
0x180027719  call    IsUMgrOpenProcessHandleForAccessPresent
0x18002771e  test    al, al
0x180027720  jz      loc_1800277EC
0x180027726  mov     qword ptr [rsp+78h+var_58], 0; int
0x18002772f  mov     [rsp+78h+var_38], 0
0x180027738  mov     r9d, 23h ; '#'; unsigned int
0x18002773e  lea     r8d, [r9+1]; unsigned int
0x180027742  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180027749  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x18002774e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027753  lea     rdx, [rsp+78h+var_58]
0x180027758  mov     rcx, [rsp+78h+var_38]
0x18002775d  call    ??$GetActivationFactory@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x180027762  mov     ebx, eax
0x180027764  test    eax, eax
0x180027766  jns     short loc_18002776F
0x180027768  mov     edx, 81h
0x18002776d  jmp     short loc_1800277BF
0x18002776f  mov     rcx, qword ptr [rsp+78h+var_58]
0x180027774  mov     rax, [rcx]
0x180027777  lea     r8, [rdi+18h]
0x18002777b  mov     rdx, [rdi+10h]
0x18002777f  mov     rax, [rax+88h]
0x180027786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002778b  mov     ebx, eax
0x18002778d  test    eax, eax
0x18002778f  jns     short loc_180027798
0x180027791  mov     edx, 83h
0x180027796  jmp     short loc_1800277BF
0x180027798  xor     edx, edx
0x18002779a  mov     rcx, rsi
0x18002779d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800277a2  mov     r9, rsi
0x1800277a5  xor     r8d, r8d
0x1800277a8  mov     rdx, [rdi+18h]
0x1800277ac  xor     ecx, ecx
0x1800277ae  call    cs:__imp_UMgrGetConstrainedUserToken
0x1800277b4  mov     ebx, eax
0x1800277b6  test    eax, eax
0x1800277b8  jns     short loc_1800277E2
0x1800277ba  mov     edx, 85h; void *
0x1800277bf  mov     r9d, eax; char *
0x1800277c2  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800277c9  mov     rcx, [rsp+78h]; this
0x1800277ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800277d3  nop
0x1800277d4  lea     rcx, [rsp+78h+var_58]
0x1800277d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800277de  mov     eax, ebx
0x1800277e0  jmp     short loc_1800277EE
0x1800277e2  lea     rcx, [rsp+78h+var_58]
0x1800277e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800277ec  xor     eax, eax
0x1800277ee  mov     rcx, [rsp+78h+var_30]
0x1800277f3  xor     rcx, rsp; StackCookie
0x1800277f6  call    __security_check_cookie
0x1800277fb  add     rsp, 58h
0x1800277ff  pop     r14
0x180027801  pop     rdi
0x180027802  pop     rsi
0x180027803  pop     rbx
0x180027804  retn
```
