# ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(void)

- ea: `0x1800882b4`
- end: `0x180088407`
- name: `?GenerateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@AEAAJXZ`
- size: `339`
- prototype: `__int64 __fastcall(ConstrainedImpersonateLoggedOnUser *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800881d0`
- `0x180088ccc`

## callees

- `0x1800062a0`
- `0x180007870`
- `0x18000bac0`
- `0x18000c2ec`
- `0x1800101bc`
- `0x18001332c`
- `0x18001dd14`
- `0x1800872dc`
- `0x1800882b4`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008838a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008838a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800883ad`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x1800883ad`

## string_xrefs

- `0x1800883c1`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\constrainedimpersonationutil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(
        ConstrainedImpersonateLoggedOnUser *this)
{
  void **v2; // rdi
  int ConstrainedUserToken; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  void *v6; // rbx
  int v8[2]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v9[8]; // [rsp+28h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+48h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( *((_QWORD *)this + 2) )
  {
    v2 = (void **)((char *)this + 8);
    if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned __int8)IsUMgrGetConstrainedUserTokenPresent() )
      {
        *(_QWORD *)v8 = 0;
        v11 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.System.Internal.UserManager",
          0x24u,
          0x23u);
        ConstrainedUserToken = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
                                 v11,
                                 v8);
        v4 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          v5 = 129;
LABEL_12:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v5,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\constrainedimpersonationutil.h",
            (const char *)(unsigned int)ConstrainedUserToken,
            v8[0]);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v8);
          return v4;
        }
        ConstrainedUserToken = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**(_QWORD **)v8 + 136LL))(
                                 *(_QWORD *)v8,
                                 *((_QWORD *)this + 2),
                                 (char *)this + 24);
        v4 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          v5 = 131;
          goto LABEL_12;
        }
        v6 = *v2;
        if ( (char *)*v2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v9);
          CloseHandle(v6);
          wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
        }
        *v2 = 0;
        ConstrainedUserToken = UMgrGetConstrainedUserToken(0, *((_QWORD *)this + 3), 0, v2);
        v4 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          v5 = 133;
          goto LABEL_12;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v8);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800882b4  push    rbx
0x1800882b6  push    rsi
0x1800882b7  push    rdi
0x1800882b8  push    r14
0x1800882ba  sub     rsp, 68h
0x1800882be  mov     rax, cs:__security_cookie
0x1800882c5  xor     rax, rsp
0x1800882c8  mov     [rsp+88h+var_38], rax
0x1800882cd  mov     rsi, rcx
0x1800882d0  cmp     qword ptr [rcx+10h], 0
0x1800882d5  jz      loc_1800883EE
0x1800882db  lea     rdi, [rcx+8]
0x1800882df  mov     rax, [rdi]
0x1800882e2  inc     rax
0x1800882e5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800882eb  jnz     loc_1800883EE
0x1800882f1  call    IsUMgrGetConstrainedUserTokenPresent
0x1800882f6  test    al, al
0x1800882f8  jz      loc_1800883EE
0x1800882fe  mov     qword ptr [rsp+88h+var_68], 0; int
0x180088307  mov     [rsp+88h+var_40], 0
0x180088310  mov     r9d, 23h ; '#'; unsigned int
0x180088316  lea     r8d, [r9+1]; unsigned int
0x18008831a  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180088321  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x180088326  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008832b  lea     rdx, [rsp+88h+var_68]
0x180088330  mov     rcx, [rsp+88h+var_40]
0x180088335  call    ??$GetActivationFactory@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18008833a  mov     ebx, eax
0x18008833c  test    eax, eax
0x18008833e  jns     short loc_180088347
0x180088340  mov     edx, 81h
0x180088345  jmp     short loc_1800883BE
0x180088347  mov     rcx, qword ptr [rsp+88h+var_68]
0x18008834c  mov     rax, [rcx]
0x18008834f  lea     r8, [rsi+18h]
0x180088353  mov     rdx, [rsi+10h]
0x180088357  mov     rax, [rax+88h]
0x18008835e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088363  mov     ebx, eax
0x180088365  test    eax, eax
0x180088367  jns     short loc_180088370
0x180088369  mov     edx, 83h
0x18008836e  jmp     short loc_1800883BE
0x180088370  mov     rbx, [rdi]
0x180088373  lea     rax, [rbx-1]
0x180088377  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008837b  ja      short loc_18008839A
0x18008837d  lea     rcx, [rsp+88h+var_60]; this
0x180088382  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180088387  mov     rcx, rbx; hObject
0x18008838a  call    cs:__imp_CloseHandle
0x180088390  lea     rcx, [rsp+88h+var_60]; this
0x180088395  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18008839a  mov     qword ptr [rdi], 0
0x1800883a1  mov     r9, rdi
0x1800883a4  xor     r8d, r8d
0x1800883a7  mov     rdx, [rsi+18h]
0x1800883ab  xor     ecx, ecx
0x1800883ad  call    cs:__imp_UMgrGetConstrainedUserToken
0x1800883b3  mov     ebx, eax
0x1800883b5  test    eax, eax
0x1800883b7  jns     short loc_1800883E4
0x1800883b9  mov     edx, 85h; void *
0x1800883be  mov     r9d, eax; char *
0x1800883c1  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800883c8  mov     rcx, [rsp+88h]; this
0x1800883d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800883d5  nop
0x1800883d6  lea     rcx, [rsp+88h+var_68]
0x1800883db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800883e0  mov     eax, ebx
0x1800883e2  jmp     short loc_1800883F0
0x1800883e4  lea     rcx, [rsp+88h+var_68]
0x1800883e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800883ee  xor     eax, eax
0x1800883f0  mov     rcx, [rsp+88h+var_38]
0x1800883f5  xor     rcx, rsp; StackCookie
0x1800883f8  call    __security_check_cookie
0x1800883fd  add     rsp, 68h
0x180088401  pop     r14
0x180088403  pop     rdi
0x180088404  pop     rsi
0x180088405  pop     rbx
0x180088406  retn
```
