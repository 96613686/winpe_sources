# SystemSettings::WorkAccess::WorkAccountList::IsWorkAccount(Windows::Security::Credentials::IWebAccount *,bool *)

- ea: `0x18001d5c0`
- end: `0x18001d8a3`
- name: `?IsWorkAccount@WorkAccountList@WorkAccess@SystemSettings@@AEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z`
- size: `739`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::WorkAccountList *__hidden this, struct Windows::Security::Credentials::IWebAccount *, bool *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bb3c`
- `0x18001d088`
- `0x18001e100`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x18001197c`
- `0x18001bf44`
- `0x18001cb1c`
- `0x18001d274`
- `0x18001d5c0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d6cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d7db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d7f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d84e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d86c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d6cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d7db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d7f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d84e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d86c`

## string_xrefs

- `0x18001d63c`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d64f`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d6a4`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d6f7`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d775`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d7c5`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d71b`: `https://login.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::IsWorkAccount(
        SystemSettings::WorkAccess::WorkAccountList *this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        bool *a3)
{
  char v6; // di
  int WebAccountType; // ebx
  __int64 v8; // rdx
  __int64 (__fastcall *v10)(struct Windows::Security::Credentials::IWebAccount *, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  HSTRING v15; // r8
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  HSTRING v20; // r8
  int v21; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v22; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  __int64 v24; // [rsp+38h] [rbp-38h] BYREF
  __int64 v25; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING v27; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  *a3 = 0;
  v6 = 0;
  LOBYTE(v21) = 0;
  LODWORD(v22) = 0;
  WebAccountType = SystemSettings::WorkAccess::WorkAccountList::GetWebAccountType(
                     this,
                     a2,
                     (enum _LSA_USER_ACCOUNT_TYPE *)&v22);
  if ( WebAccountType < 0 )
  {
    v8 = 626;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)WebAccountType,
      v21);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)WebAccountType,
      v21);
    return (unsigned int)WebAccountType;
  }
  if ( (unsigned int)((_DWORD)v22 - 2) <= 1 )
  {
    WebAccountType = SystemSettings::WorkAccess::WorkAccountList::IsDefaultSignInAccount(this, a2, (bool *)&v21);
    if ( WebAccountType < 0 )
    {
      v8 = 629;
      goto LABEL_6;
    }
    v6 = v21;
  }
  if ( !v6 )
  {
    v25 = 0;
    v10 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, __int64 *))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v11 = v10(a2, &v25);
    WebAccountType = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24A,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v11,
        v21);
LABEL_21:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      return (unsigned int)WebAccountType;
    }
    v22 = 0;
    v12 = v25;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 48LL);
    WindowsDeleteString(0);
    v22 = 0;
    v14 = v13(v12, &v22);
    WebAccountType = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24D,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v14,
        v21);
LABEL_20:
      WindowsDeleteString(v22);
      v22 = 0;
      goto LABEL_21;
    }
    v27 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"https://login.microsoft.com",
      0x1Cu,
      0x1Bu);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                          (Microsoft::WRL::Wrappers::Details *)v22,
                          v27,
                          v15) )
    {
      v24 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v25)(
              v25,
              &GUID_4a01eb05_4e42_41d4_b518_e008a5163614,
              &v24);
      WebAccountType = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x252,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
          (const char *)(unsigned int)v16,
          v21);
LABEL_19:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        goto LABEL_20;
      }
      string = 0;
      v17 = v24;
      v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v19 = v18(v17, &string);
      WebAccountType = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x255,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
          (const char *)(unsigned int)v19,
          v21);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_19;
      }
      v27 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"organizations", 0xEu, 0xDu);
      *a3 = (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                            (Microsoft::WRL::Wrappers::Details *)string,
                            v27,
                            v20) == 0;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    }
    WindowsDeleteString(v22);
    v22 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  }
  return 0;
}

```

## disassembly

```asm
0x18001d5c0  push    rbp
0x18001d5c2  push    rbx
0x18001d5c3  push    rsi
0x18001d5c4  push    rdi
0x18001d5c5  push    r12
0x18001d5c7  push    r14
0x18001d5c9  push    r15
0x18001d5cb  mov     rbp, rsp
0x18001d5ce  sub     rsp, 70h
0x18001d5d2  mov     rax, cs:__security_cookie
0x18001d5d9  xor     rax, rsp
0x18001d5dc  mov     [rbp+var_8], rax
0x18001d5e0  mov     r15, r8
0x18001d5e3  mov     rsi, rdx
0x18001d5e6  mov     r14, rcx
0x18001d5e9  xor     r12d, r12d
0x18001d5ec  mov     [r8], r12b
0x18001d5ef  mov     dil, r12b
0x18001d5f2  mov     byte ptr [rbp+var_50], r12b
0x18001d5f6  mov     dword ptr [rbp+var_48], r12d
0x18001d5fa  lea     r8, [rbp+var_48]; enum _LSA_USER_ACCOUNT_TYPE *
0x18001d5fe  call    ?GetWebAccountType@WorkAccountList@WorkAccess@SystemSettings@@AEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEAW4_LSA_USER_ACCOUNT_TYPE@@@Z; SystemSettings::WorkAccess::WorkAccountList::GetWebAccountType(Windows::Security::Credentials::IWebAccount *,_LSA_USER_ACCOUNT_TYPE *)
0x18001d603  mov     ebx, eax
0x18001d605  test    eax, eax
0x18001d607  jns     short loc_18001D610
0x18001d609  mov     edx, 272h
0x18001d60e  jmp     short loc_18001D635
0x18001d610  mov     eax, dword ptr [rbp+var_48]
0x18001d613  add     eax, 0FFFFFFFEh
0x18001d616  cmp     eax, 1
0x18001d619  ja      short loc_18001D66B
0x18001d61b  lea     r8, [rbp+var_50]; bool *
0x18001d61f  mov     rdx, rsi; struct Windows::Security::Credentials::IWebAccount *
0x18001d622  mov     rcx, r14; this
0x18001d625  call    ?IsDefaultSignInAccount@WorkAccountList@WorkAccess@SystemSettings@@AEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z; SystemSettings::WorkAccess::WorkAccountList::IsDefaultSignInAccount(Windows::Security::Credentials::IWebAccount *,bool *)
0x18001d62a  mov     ebx, eax
0x18001d62c  test    eax, eax
0x18001d62e  jns     short loc_18001D667
0x18001d630  mov     edx, 275h; void *
0x18001d635  mov     r9d, ebx; char *
0x18001d638  mov     rcx, [rbp+38h]; this
0x18001d63c  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d643  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d648  mov     rcx, [rbp+38h]; this
0x18001d64c  mov     r9d, ebx; char *
0x18001d64f  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d656  mov     edx, 244h; void *
0x18001d65b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d660  mov     eax, ebx
0x18001d662  jmp     loc_18001D887
0x18001d667  mov     dil, byte ptr [rbp+var_50]
0x18001d66b  test    dil, dil
0x18001d66e  jnz     loc_18001D885
0x18001d674  mov     [rbp+var_30], r12
0x18001d678  mov     rax, [rsi]
0x18001d67b  mov     rbx, [rax+30h]
0x18001d67f  lea     rcx, [rbp+var_30]
0x18001d683  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d688  lea     rdx, [rbp+var_30]
0x18001d68c  mov     rcx, rsi
0x18001d68f  mov     rax, rbx
0x18001d692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d697  mov     ebx, eax
0x18001d699  test    eax, eax
0x18001d69b  jns     short loc_18001D6BA
0x18001d69d  mov     rcx, [rbp+38h]; this
0x18001d6a1  mov     r9d, eax; char *
0x18001d6a4  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d6ab  mov     edx, 24Ah; void *
0x18001d6b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d6b5  jmp     loc_18001D809
0x18001d6ba  mov     [rbp+var_48], r12
0x18001d6be  mov     rdi, [rbp+var_30]
0x18001d6c2  mov     rax, [rdi]
0x18001d6c5  mov     rbx, [rax+30h]
0x18001d6c9  xor     ecx, ecx; string
0x18001d6cb  call    cs:__imp_WindowsDeleteString
0x18001d6d2  nop     dword ptr [rax+rax+00h]
0x18001d6d7  mov     [rbp+var_48], r12
0x18001d6db  lea     rdx, [rbp+var_48]
0x18001d6df  mov     rcx, rdi
0x18001d6e2  mov     rax, rbx
0x18001d6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6ea  mov     ebx, eax
0x18001d6ec  test    eax, eax
0x18001d6ee  jns     short loc_18001D70D
0x18001d6f0  mov     rcx, [rbp+38h]; this
0x18001d6f4  mov     r9d, eax; char *
0x18001d6f7  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d6fe  mov     edx, 24Dh; void *
0x18001d703  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d708  jmp     loc_18001D7F5
0x18001d70d  mov     [rbp+var_10], r12
0x18001d711  mov     r9d, 1Bh; unsigned int
0x18001d717  lea     r8d, [r9+1]; unsigned int
0x18001d71b  lea     rdx, aHttpsLoginMicr; "https://login.microsoft.com"
0x18001d722  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001d726  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d72b  mov     rdx, [rbp+var_10]; HSTRING
0x18001d72f  mov     rcx, [rbp+var_48]; this
0x18001d733  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18001d738  test    eax, eax
0x18001d73a  jnz     loc_18001D868
0x18001d740  mov     [rbp+var_38], r12
0x18001d744  lea     rcx, [rbp+var_38]
0x18001d748  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d74d  nop
0x18001d74e  mov     rcx, [rbp+var_30]
0x18001d752  mov     rax, [rcx]
0x18001d755  lea     r8, [rbp+var_38]
0x18001d759  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x18001d760  mov     rax, [rax]
0x18001d763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d768  mov     ebx, eax
0x18001d76a  test    eax, eax
0x18001d76c  jns     short loc_18001D788
0x18001d76e  mov     rcx, [rbp+38h]; this
0x18001d772  mov     r9d, eax; char *
0x18001d775  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d77c  mov     edx, 252h; void *
0x18001d781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d786  jmp     short loc_18001D7EB
0x18001d788  mov     [rbp+string], r12
0x18001d78c  mov     rdi, [rbp+var_38]
0x18001d790  mov     rax, [rdi]
0x18001d793  mov     rbx, [rax+38h]
0x18001d797  xor     ecx, ecx; string
0x18001d799  call    cs:__imp_WindowsDeleteString
0x18001d7a0  nop     dword ptr [rax+rax+00h]
0x18001d7a5  mov     [rbp+string], r12
0x18001d7a9  lea     rdx, [rbp+string]
0x18001d7ad  mov     rcx, rdi
0x18001d7b0  mov     rax, rbx
0x18001d7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7b8  mov     ebx, eax
0x18001d7ba  test    eax, eax
0x18001d7bc  jns     short loc_18001D817
0x18001d7be  mov     rcx, [rbp+38h]; this
0x18001d7c2  mov     r9d, eax; char *
0x18001d7c5  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d7cc  mov     edx, 255h; void *
0x18001d7d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7d6  nop
0x18001d7d7  mov     rcx, [rbp+string]; string
0x18001d7db  call    cs:__imp_WindowsDeleteString
0x18001d7e2  nop     dword ptr [rax+rax+00h]
0x18001d7e7  mov     [rbp+string], r12
0x18001d7eb  lea     rcx, [rbp+var_38]
0x18001d7ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d7f4  nop
0x18001d7f5  mov     rcx, [rbp+var_48]; string
0x18001d7f9  call    cs:__imp_WindowsDeleteString
0x18001d800  nop     dword ptr [rax+rax+00h]
0x18001d805  mov     [rbp+var_48], r12
0x18001d809  lea     rcx, [rbp+var_30]
0x18001d80d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d812  jmp     loc_18001D660
0x18001d817  mov     [rbp+var_10], r12
0x18001d81b  mov     r9d, 0Dh; unsigned int
0x18001d821  lea     r8d, [r9+1]; unsigned int
0x18001d825  lea     rdx, aOrganizations; "organizations"
0x18001d82c  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001d830  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d835  mov     rdx, [rbp+var_10]; HSTRING
0x18001d839  mov     rcx, [rbp+string]; this
0x18001d83d  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18001d842  test    eax, eax
0x18001d844  setz    al
0x18001d847  mov     [r15], al
0x18001d84a  mov     rcx, [rbp+string]; string
0x18001d84e  call    cs:__imp_WindowsDeleteString
0x18001d855  nop     dword ptr [rax+rax+00h]
0x18001d85a  mov     [rbp+string], r12
0x18001d85e  lea     rcx, [rbp+var_38]
0x18001d862  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d867  nop
0x18001d868  mov     rcx, [rbp+var_48]; string
0x18001d86c  call    cs:__imp_WindowsDeleteString
0x18001d873  nop     dword ptr [rax+rax+00h]
0x18001d878  mov     [rbp+var_48], r12
0x18001d87c  lea     rcx, [rbp+var_30]
0x18001d880  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d885  xor     eax, eax
0x18001d887  mov     rcx, [rbp+var_8]
0x18001d88b  xor     rcx, rsp; StackCookie
0x18001d88e  call    __security_check_cookie
0x18001d893  add     rsp, 70h
0x18001d897  pop     r15
0x18001d899  pop     r14
0x18001d89b  pop     r12
0x18001d89d  pop     rdi
0x18001d89e  pop     rsi
0x18001d89f  pop     rbx
0x18001d8a0  pop     rbp
0x18001d8a1  retn
```
