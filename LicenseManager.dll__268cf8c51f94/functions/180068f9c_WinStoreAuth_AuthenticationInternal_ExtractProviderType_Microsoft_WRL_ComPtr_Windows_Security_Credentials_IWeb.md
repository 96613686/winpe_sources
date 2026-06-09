# WinStoreAuth::AuthenticationInternal::ExtractProviderType(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AccountProviderType &)

- ea: `0x180068f9c`
- end: `0x180069194`
- name: `?ExtractProviderType@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@AEAW4AccountProviderType@2@@Z`
- size: `504`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002ce2c`
- `0x18002d928`
- `0x1800a52ec`
- `0x1800a6840`

## callees

- `0x180004738`
- `0x18002cce0`
- `0x180042658`
- `0x180061c04`
- `0x180068f9c`
- `0x18006919c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068fe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800690af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800690ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069181`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068fe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800690af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800690ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069181`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinStoreAuth::AuthenticationInternal::ExtractProviderType(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        _DWORD *a2)
{
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  HSTRING string; // [rsp+58h] [rbp+38h] BYREF
  __int64 v19; // [rsp+60h] [rbp+40h] BYREF
  HSTRING v20; // [rsp+68h] [rbp+48h] BYREF

  *a2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix>::GetImpl'::`2'::impl)
    && !*a1 )
  {
    return 0;
  }
  v20 = 0;
  v5 = *a1;
  v6 = (**a1)[6];
  WindowsDeleteString(0);
  v20 = 0;
  v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))v6)(v5, &v20);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v19 = 0;
    v9 = *a1;
    v10 = ***a1;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
    v11 = v10(v9, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v19);
    v8 = v11;
    if ( v11 >= 0 )
    {
      v11 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v19);
      v8 = v11;
      if ( v11 >= 0 )
      {
        string = 0;
        v13 = v19;
        v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 56LL);
        WindowsDeleteString(0);
        string = 0;
        v15 = v14(v13, &string);
        v8 = v15;
        if ( v15 >= 0 )
        {
          if ( (unsigned __int8)Microsoft::WRL::Wrappers::operator==(&v20, &WinStoreAuth::g_pszMicrosoftProviderId)
            || (unsigned __int8)Microsoft::WRL::Wrappers::operator==(&v20, &WinStoreAuth::g_pszGoldenAccountProviderId) )
          {
            if ( (unsigned __int8)Microsoft::WRL::Wrappers::operator==(&string, &WinStoreAuth::g_pszMsaAuthority) )
            {
              *a2 = 1;
            }
            else if ( (unsigned __int8)Microsoft::WRL::Wrappers::operator==(&string, &WinStoreAuth::g_pszAadAuthority) )
            {
              *a2 = 2;
            }
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
          v8 = 0;
          goto LABEL_21;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA55,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v15,
          savedregs);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_9;
      }
      v12 = 2642;
    }
    else
    {
      v12 = 2641;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v11,
      savedregs);
LABEL_9:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA4E,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)(unsigned int)v7,
    savedregs);
LABEL_21:
  WindowsDeleteString(v20);
  return v8;
}

```

## disassembly

```asm
0x180068f9c  push    rbp
0x180068f9e  push    rbx
0x180068f9f  push    rsi
0x180068fa0  push    rdi
0x180068fa1  push    r14; int
0x180068fa3  mov     rbp, rsp
0x180068fa6  sub     rsp, 20h
0x180068faa  mov     rsi, rdx
0x180068fad  mov     r14, rcx
0x180068fb0  mov     dword ptr [rdx], 0
0x180068fb6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix> `wil::Feature<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix>::GetImpl(void)'::`2'::impl
0x180068fbd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix>::__private_IsEnabled(void)
0x180068fc2  test    al, al
0x180068fc4  jz      short loc_180068FD3
0x180068fc6  cmp     qword ptr [r14], 0
0x180068fca  jnz     short loc_180068FD3
0x180068fcc  xor     eax, eax
0x180068fce  jmp     loc_180069189
0x180068fd3  mov     [rbp+arg_18], 0
0x180068fdb  mov     rdi, [r14]
0x180068fde  mov     rax, [rdi]
0x180068fe1  mov     rbx, [rax+30h]
0x180068fe5  xor     ecx, ecx; string
0x180068fe7  call    cs:__imp_WindowsDeleteString
0x180068fed  mov     [rbp+arg_18], 0
0x180068ff5  lea     rdx, [rbp+arg_18]
0x180068ff9  mov     rcx, rdi
0x180068ffc  mov     rax, rbx
0x180068fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069004  mov     ebx, eax
0x180069006  test    eax, eax
0x180069008  jns     short loc_180069027
0x18006900a  mov     rcx, [rbp+28h]; this
0x18006900e  mov     r9d, eax; char *
0x180069011  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180069018  mov     edx, 0A4Eh; void *
0x18006901d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069022  jmp     loc_18006917D
0x180069027  mov     [rbp+arg_10], 0
0x18006902f  mov     rdi, [r14]
0x180069032  mov     rax, [rdi]
0x180069035  mov     rbx, [rax]
0x180069038  lea     rcx, [rbp+arg_10]
0x18006903c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180069041  lea     r8, [rbp+arg_10]
0x180069045  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x18006904c  mov     rcx, rdi
0x18006904f  mov     rax, rbx
0x180069052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069057  mov     ebx, eax
0x180069059  test    eax, eax
0x18006905b  jns     short loc_180069084
0x18006905d  mov     edx, 0A51h; void *
0x180069062  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180069069  mov     r9d, eax; char *
0x18006906c  mov     rcx, [rbp+28h]; this
0x180069070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069075  nop
0x180069076  lea     rcx, [rbp+arg_10]
0x18006907a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006907f  jmp     loc_18006917D
0x180069084  mov     rcx, [rbp+arg_10]
0x180069088  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18006908d  mov     ebx, eax
0x18006908f  test    eax, eax
0x180069091  jns     short loc_18006909A
0x180069093  mov     edx, 0A52h
0x180069098  jmp     short loc_180069062
0x18006909a  mov     [rbp+string], 0
0x1800690a2  mov     rdi, [rbp+arg_10]
0x1800690a6  mov     rax, [rdi]
0x1800690a9  mov     rbx, [rax+38h]
0x1800690ad  xor     ecx, ecx; string
0x1800690af  call    cs:__imp_WindowsDeleteString
0x1800690b5  mov     [rbp+string], 0
0x1800690bd  lea     rdx, [rbp+string]
0x1800690c1  mov     rcx, rdi
0x1800690c4  mov     rax, rbx
0x1800690c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690cc  mov     ebx, eax
0x1800690ce  test    eax, eax
0x1800690d0  jns     short loc_180069102
0x1800690d2  mov     rcx, [rbp+28h]; this
0x1800690d6  mov     r9d, eax; char *
0x1800690d9  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800690e0  mov     edx, 0A55h; void *
0x1800690e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800690ea  nop
0x1800690eb  mov     rcx, [rbp+string]; string
0x1800690ef  call    cs:__imp_WindowsDeleteString
0x1800690f5  mov     [rbp+string], 0
0x1800690fd  jmp     loc_180069076
0x180069102  lea     rdx, ?g_pszMicrosoftProviderId@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::HStringReference WinStoreAuth::g_pszMicrosoftProviderId
0x180069109  lea     rcx, [rbp+arg_18]
0x18006910d  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBVHString@012@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x180069112  test    al, al
0x180069114  jnz     short loc_18006912A
0x180069116  lea     rdx, ?g_pszGoldenAccountProviderId@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::HStringReference WinStoreAuth::g_pszGoldenAccountProviderId
0x18006911d  lea     rcx, [rbp+arg_18]
0x180069121  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBVHString@012@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x180069126  test    al, al
0x180069128  jz      short loc_180069160
0x18006912a  lea     rdx, ?g_pszMsaAuthority@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::HStringReference WinStoreAuth::g_pszMsaAuthority
0x180069131  lea     rcx, [rbp+string]
0x180069135  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBVHString@012@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x18006913a  test    al, al
0x18006913c  jz      short loc_180069146
0x18006913e  mov     dword ptr [rsi], 1
0x180069144  jmp     short loc_180069160
0x180069146  lea     rdx, ?g_pszAadAuthority@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::HStringReference WinStoreAuth::g_pszAadAuthority
0x18006914d  lea     rcx, [rbp+string]
0x180069151  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBVHString@012@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x180069156  test    al, al
0x180069158  jz      short loc_180069160
0x18006915a  mov     dword ptr [rsi], 2
0x180069160  mov     rcx, [rbp+string]; string
0x180069164  call    cs:__imp_WindowsDeleteString
0x18006916a  mov     [rbp+string], 0
0x180069172  lea     rcx, [rbp+arg_10]
0x180069176  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006917b  xor     ebx, ebx
0x18006917d  mov     rcx, [rbp+arg_18]; string
0x180069181  call    cs:__imp_WindowsDeleteString
0x180069187  mov     eax, ebx
0x180069189  add     rsp, 20h
0x18006918d  pop     r14
0x18006918f  pop     rdi
0x180069190  pop     rsi
0x180069191  pop     rbx
0x180069192  pop     rbp
0x180069193  retn
```
