# ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(void)

- ea: `0x180061324`
- end: `0x180061471`
- name: `?GenerateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@AEAAJXZ`
- size: `333`
- prototype: `__int64 __fastcall(ConstrainedImpersonateLoggedOnUser *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180061224`

## callees

- `0x180004738`
- `0x18003dab0`
- `0x180061324`
- `0x180061c04`
- `0x180075e60`
- `0x1800771b8`
- `0x1800a82d8`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800613b9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800613b9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18006141a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18006141a`

## string_xrefs

- `0x18006142e`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(
        ConstrainedImpersonateLoggedOnUser *this)
{
  HANDLE *v2; // rdi
  __int64 v3; // rbx
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8[2]; // [rsp+20h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-50h] BYREF
  __int64 v10; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( *((_QWORD *)this + 2) )
  {
    v2 = (HANDLE *)((char *)this + 8);
    if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned __int8)IsUMgrGetConstrainedUserTokenPresent() )
      {
        *(_QWORD *)v8 = 0;
        v10 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.System.Internal.UserManager",
          0x24u,
          0x23u);
        v3 = v10;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v8);
        ActivationFactory = RoGetActivationFactory(v3, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, v8);
        v5 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          v6 = 129;
LABEL_12:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v6,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
            (const char *)(unsigned int)ActivationFactory,
            v8[0]);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v8);
          return v5;
        }
        ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**(_QWORD **)v8 + 136LL))(
                              *(_QWORD *)v8,
                              *((_QWORD *)this + 2),
                              (char *)this + 24);
        v5 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          v6 = 131;
          goto LABEL_12;
        }
        if ( (char *)*v2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v2);
        *v2 = 0;
        ActivationFactory = UMgrGetConstrainedUserToken(0, *((_QWORD *)this + 3), 0, v2);
        v5 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          v6 = 133;
          goto LABEL_12;
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v8);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180061324  push    rbx
0x180061326  push    rsi
0x180061327  push    rdi
0x180061328  push    r14
0x18006132a  sub     rsp, 58h
0x18006132e  mov     rax, cs:__security_cookie
0x180061335  xor     rax, rsp
0x180061338  mov     [rsp+78h+var_30], rax
0x18006133d  mov     rsi, rcx
0x180061340  cmp     qword ptr [rcx+10h], 0
0x180061345  jz      loc_180061458
0x18006134b  lea     rdi, [rcx+8]
0x18006134f  mov     rax, [rdi]
0x180061352  inc     rax
0x180061355  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006135b  jnz     loc_180061458
0x180061361  call    IsUMgrGetConstrainedUserTokenPresent
0x180061366  test    al, al
0x180061368  jz      loc_180061458
0x18006136e  mov     qword ptr [rsp+78h+var_58], 0; int
0x180061377  mov     [rsp+78h+var_38], 0
0x180061380  mov     r9d, 23h ; '#'; unsigned int
0x180061386  lea     r8d, [r9+1]; unsigned int
0x18006138a  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180061391  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x180061396  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006139b  mov     rbx, [rsp+78h+var_38]
0x1800613a0  lea     rcx, [rsp+78h+var_58]
0x1800613a5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800613aa  lea     r8, [rsp+78h+var_58]
0x1800613af  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800613b6  mov     rcx, rbx
0x1800613b9  call    cs:__imp_RoGetActivationFactory
0x1800613bf  mov     ebx, eax
0x1800613c1  test    eax, eax
0x1800613c3  jns     short loc_1800613CC
0x1800613c5  mov     edx, 81h
0x1800613ca  jmp     short loc_18006142B
0x1800613cc  mov     rcx, qword ptr [rsp+78h+var_58]
0x1800613d1  mov     rax, [rcx]
0x1800613d4  lea     r8, [rsi+18h]
0x1800613d8  mov     rdx, [rsi+10h]
0x1800613dc  mov     rax, [rax+88h]
0x1800613e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800613e8  mov     ebx, eax
0x1800613ea  test    eax, eax
0x1800613ec  jns     short loc_1800613F5
0x1800613ee  mov     edx, 83h
0x1800613f3  jmp     short loc_18006142B
0x1800613f5  mov     rcx, [rdi]; hObject
0x1800613f8  lea     rax, [rcx-1]
0x1800613fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180061400  ja      short loc_180061407
0x180061402  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180061407  mov     qword ptr [rdi], 0
0x18006140e  mov     r9, rdi
0x180061411  xor     r8d, r8d
0x180061414  mov     rdx, [rsi+18h]
0x180061418  xor     ecx, ecx
0x18006141a  call    cs:__imp_UMgrGetConstrainedUserToken
0x180061420  mov     ebx, eax
0x180061422  test    eax, eax
0x180061424  jns     short loc_18006144E
0x180061426  mov     edx, 85h; void *
0x18006142b  mov     r9d, eax; char *
0x18006142e  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180061435  mov     rcx, [rsp+78h]; this
0x18006143a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006143f  nop
0x180061440  lea     rcx, [rsp+78h+var_58]
0x180061445  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006144a  mov     eax, ebx
0x18006144c  jmp     short loc_18006145A
0x18006144e  lea     rcx, [rsp+78h+var_58]
0x180061453  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180061458  xor     eax, eax
0x18006145a  mov     rcx, [rsp+78h+var_30]
0x18006145f  xor     rcx, rsp; StackCookie
0x180061462  call    __security_check_cookie
0x180061467  add     rsp, 58h
0x18006146b  pop     r14
0x18006146d  pop     rdi
0x18006146e  pop     rsi
0x18006146f  pop     rbx
0x180061470  retn
```
