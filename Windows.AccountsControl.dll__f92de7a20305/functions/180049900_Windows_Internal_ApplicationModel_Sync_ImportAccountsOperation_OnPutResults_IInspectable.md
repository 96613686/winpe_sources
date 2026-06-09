# Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation::OnPutResults(IInspectable *)

- ea: `0x180049900`
- end: `0x180049c07`
- name: `?OnPutResults@ImportAccountsOperation@Sync@ApplicationModel@Internal@Windows@@UEAAJPEAUIInspectable@@@Z`
- size: `775`
- prototype: `__int64 __fastcall(Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation *__hidden this, struct IInspectable *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x180011ffc`
- `0x180048bfc`
- `0x180049900`
- `0x18005923c`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049a61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049b19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049a61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049b19`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation::OnPutResults(
        Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation *this,
        struct IInspectable *a2)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  unsigned int i; // esi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, struct Windows::Foundation::IPropertyValue **); // rbx
  int v15; // eax
  int FormattedUserDataAccountId; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64); // rbx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 v23; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+28h] [rbp-58h] BYREF
  struct Windows::Foundation::IPropertyValue *v25; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-40h] BYREF
  int v28; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v30; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v27 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  v5 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_a6487363_b074_5c60_ab16_866dce4ee54d,
         &v27);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 179;
LABEL_5:
    v8 = (unsigned int)v5;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\importaccountsoperation.cpp",
      (const char *)v8,
      v23);
LABEL_35:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    return v6;
  }
  v28 = 0;
  v26 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 75) + 56LL))(*((_QWORD *)this + 75), &v28);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 183;
    goto LABEL_5;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 56LL))(v27, &v26);
  v6 = v9;
  if ( v9 < 0 )
  {
    v8 = (unsigned int)v9;
    v7 = 184;
    goto LABEL_34;
  }
  if ( v26 != v28 )
  {
    v6 = -2147024809;
    v8 = 2147942487LL;
    v7 = 185;
    goto LABEL_34;
  }
  v23 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v11 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
          v10,
          &v23);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\importaccountsoperation.cpp",
      (const char *)(unsigned int)v11,
      v23);
LABEL_27:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    goto LABEL_35;
  }
  for ( i = 0; i < v26; ++i )
  {
    v25 = 0;
    v13 = v27;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)v27 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    v15 = v14(v13, 0, &v25);
    v6 = v15;
    if ( v15 < 0 )
    {
      v20 = 193;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\importaccountsoperation.cpp",
        (const char *)(unsigned int)v15,
        v23);
      goto LABEL_26;
    }
    if ( v25 )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      FormattedUserDataAccountId = GetFormattedUserDataAccountId(v25, &string);
      v6 = FormattedUserDataAccountId;
      if ( FormattedUserDataAccountId < 0 )
      {
        v19 = 198;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\importaccountsoperation.cpp",
          (const char *)(unsigned int)FormattedUserDataAccountId,
          v23);
        WindowsDeleteString(string);
        string = 0;
LABEL_26:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        goto LABEL_27;
      }
      FormattedUserDataAccountId = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v23 + 104LL))(v23, string);
      v6 = FormattedUserDataAccountId;
      if ( FormattedUserDataAccountId < 0 )
      {
        v19 = 199;
        goto LABEL_21;
      }
      WindowsDeleteString(string);
    }
    else
    {
      v17 = v23;
      v18 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 104LL);
      v30 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &word_18008CC90, 1u, 0);
      v15 = v18(v17, v30);
      v6 = v15;
      if ( v15 < 0 )
      {
        v20 = 203;
        goto LABEL_25;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  }
  v21 = v23;
  if ( *((_QWORD *)this + 76) != v23 )
  {
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
    string = (HSTRING)*((_QWORD *)this + 76);
    *((_QWORD *)this + 76) = v21;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  return 0;
}

```

## disassembly

```asm
0x180049900  mov     [rsp-18h+arg_10], rbx
0x180049905  mov     [rsp-18h+arg_18], rsi
0x18004990a  push    rbp
0x18004990b  push    rdi
0x18004990c  push    r14
0x18004990e  mov     rbp, rsp
0x180049911  sub     rsp, 80h
0x180049918  mov     rax, cs:__security_cookie
0x18004991f  xor     rax, rsp
0x180049922  mov     [rbp+var_10], rax
0x180049926  mov     rdi, rdx
0x180049929  mov     r14, rcx
0x18004992c  mov     [rbp+var_40], 0
0x180049934  mov     rax, [rdx]
0x180049937  mov     rbx, [rax]
0x18004993a  lea     rcx, [rbp+var_40]
0x18004993e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049943  lea     r8, [rbp+var_40]
0x180049947  lea     rdx, _GUID_a6487363_b074_5c60_ab16_866dce4ee54d
0x18004994e  mov     rcx, rdi
0x180049951  mov     rax, rbx
0x180049954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049959  mov     ebx, eax
0x18004995b  test    eax, eax
0x18004995d  jns     short loc_180049966
0x18004995f  mov     edx, 0B3h
0x180049964  jmp     short loc_180049996
0x180049966  mov     [rbp+var_38], 0
0x18004996d  mov     [rbp+var_48], 0
0x180049974  mov     rcx, [r14+258h]
0x18004997b  mov     rax, [rcx]
0x18004997e  lea     rdx, [rbp+var_38]
0x180049982  mov     rax, [rax+38h]
0x180049986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004998b  mov     ebx, eax
0x18004998d  test    eax, eax
0x18004998f  jns     short loc_18004999E
0x180049991  mov     edx, 0B7h
0x180049996  mov     r9d, eax
0x180049999  jmp     loc_180049BC7
0x18004999e  mov     rcx, [rbp+var_40]
0x1800499a2  mov     rax, [rcx]
0x1800499a5  lea     rdx, [rbp+var_48]
0x1800499a9  mov     rax, [rax+38h]
0x1800499ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499b2  mov     ebx, eax
0x1800499b4  test    eax, eax
0x1800499b6  jns     short loc_1800499C5
0x1800499b8  mov     r9d, eax
0x1800499bb  mov     edx, 0B8h
0x1800499c0  jmp     loc_180049BC7
0x1800499c5  mov     eax, [rbp+var_38]
0x1800499c8  cmp     [rbp+var_48], eax
0x1800499cb  jnz     loc_180049BBA
0x1800499d1  mov     [rbp+var_60], 0
0x1800499d9  lea     rcx, [rbp+var_60]
0x1800499dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800499e2  lea     rdx, [rbp+var_60]
0x1800499e6  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x1800499eb  mov     ebx, eax
0x1800499ed  test    eax, eax
0x1800499ef  jns     short loc_180049A0E
0x1800499f1  mov     rcx, [rbp+18h]; this
0x1800499f5  mov     r9d, eax; char *
0x1800499f8  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800499ff  mov     edx, 0BCh; void *
0x180049a04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049a09  jmp     loc_180049B5A
0x180049a0e  xor     esi, esi
0x180049a10  cmp     esi, [rbp+var_48]
0x180049a13  jnb     loc_180049B65
0x180049a19  mov     [rbp+var_50], 0
0x180049a21  mov     rdi, [rbp+var_40]
0x180049a25  mov     rax, [rdi]
0x180049a28  mov     rbx, [rax+30h]
0x180049a2c  lea     rcx, [rbp+var_50]
0x180049a30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049a35  lea     r8, [rbp+var_50]
0x180049a39  xor     edx, edx
0x180049a3b  mov     rcx, rdi
0x180049a3e  mov     rax, rbx
0x180049a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a46  mov     ebx, eax
0x180049a48  test    eax, eax
0x180049a4a  js      loc_180049B37
0x180049a50  cmp     [rbp+var_50], 0
0x180049a55  jz      short loc_180049AAC
0x180049a57  mov     [rbp+string], 0
0x180049a5f  xor     ecx, ecx; string
0x180049a61  call    cs:__imp_WindowsDeleteString
0x180049a67  mov     [rbp+string], 0
0x180049a6f  lea     rdx, [rbp+string]; HSTRING *
0x180049a73  mov     rcx, [rbp+var_50]; struct Windows::Foundation::IPropertyValue *
0x180049a77  call    ?GetFormattedUserDataAccountId@@YAJPEAUIPropertyValue@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; GetFormattedUserDataAccountId(Windows::Foundation::IPropertyValue *,HSTRING__ * *)
0x180049a7c  mov     ebx, eax
0x180049a7e  test    eax, eax
0x180049a80  js      loc_180049B29
0x180049a86  mov     rcx, [rbp+var_60]
0x180049a8a  mov     rax, [rcx]
0x180049a8d  mov     rdx, [rbp+string]
0x180049a91  mov     rax, [rax+68h]
0x180049a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a9a  mov     ebx, eax
0x180049a9c  test    eax, eax
0x180049a9e  js      short loc_180049AFC
0x180049aa0  mov     rcx, [rbp+string]; string
0x180049aa4  call    cs:__imp_WindowsDeleteString
0x180049aaa  jmp     short loc_180049AEC
0x180049aac  mov     rdi, [rbp+var_60]
0x180049ab0  mov     rax, [rdi]
0x180049ab3  mov     rbx, [rax+68h]
0x180049ab7  mov     [rbp+var_18], 0
0x180049abf  xor     r9d, r9d; unsigned int
0x180049ac2  lea     r8d, [r9+1]; unsigned int
0x180049ac6  lea     rdx, word_18008CC90; sourceString
0x180049acd  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180049ad1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180049ad6  nop
0x180049ad7  mov     rdx, [rbp+var_18]
0x180049adb  mov     rcx, rdi
0x180049ade  mov     rax, rbx
0x180049ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ae6  mov     ebx, eax
0x180049ae8  test    eax, eax
0x180049aea  js      short loc_180049B30
0x180049aec  lea     rcx, [rbp+var_50]
0x180049af0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049af5  inc     esi
0x180049af7  jmp     loc_180049A10
0x180049afc  mov     edx, 0C7h; void *
0x180049b01  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\accountscontrol\\api"...
0x180049b08  mov     r9d, eax; char *
0x180049b0b  mov     rcx, [rbp+18h]; this
0x180049b0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049b14  nop
0x180049b15  mov     rcx, [rbp+string]; string
0x180049b19  call    cs:__imp_WindowsDeleteString
0x180049b1f  mov     [rbp+string], 0
0x180049b27  jmp     short loc_180049B50
0x180049b29  mov     edx, 0C6h
0x180049b2e  jmp     short loc_180049B01
0x180049b30  mov     edx, 0CBh
0x180049b35  jmp     short loc_180049B3C
0x180049b37  mov     edx, 0C1h; void *
0x180049b3c  mov     r9d, eax; char *
0x180049b3f  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\accountscontrol\\api"...
0x180049b46  mov     rcx, [rbp+18h]; this
0x180049b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049b4f  nop
0x180049b50  lea     rcx, [rbp+var_50]
0x180049b54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049b59  nop
0x180049b5a  lea     rcx, [rbp+var_60]
0x180049b5e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049b63  jmp     short loc_180049BD8
0x180049b65  mov     rbx, [rbp+var_60]
0x180049b69  cmp     [r14+260h], rbx
0x180049b70  jz      short loc_180049BA3
0x180049b72  test    rbx, rbx
0x180049b75  jz      short loc_180049B87
0x180049b77  mov     rax, [rbx]
0x180049b7a  mov     rcx, rbx
0x180049b7d  mov     rax, [rax+8]
0x180049b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b86  nop
0x180049b87  mov     rax, [r14+260h]
0x180049b8e  mov     [rbp+string], rax
0x180049b92  mov     [r14+260h], rbx
0x180049b99  lea     rcx, [rbp+string]
0x180049b9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049ba2  nop
0x180049ba3  lea     rcx, [rbp+var_60]
0x180049ba7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049bac  nop
0x180049bad  lea     rcx, [rbp+var_40]
0x180049bb1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049bb6  xor     eax, eax
0x180049bb8  jmp     short loc_180049BE3
0x180049bba  mov     ebx, 80070057h
0x180049bbf  mov     r9d, ebx; char *
0x180049bc2  mov     edx, 0B9h; void *
0x180049bc7  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\accountscontrol\\api"...
0x180049bce  mov     rcx, [rbp+18h]; this
0x180049bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049bd7  nop
0x180049bd8  lea     rcx, [rbp+var_40]
0x180049bdc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049be1  mov     eax, ebx
0x180049be3  mov     rcx, [rbp+var_10]
0x180049be7  xor     rcx, rsp; StackCookie
0x180049bea  call    __security_check_cookie
0x180049bef  lea     r11, [rsp+80h+var_s0]
0x180049bf7  mov     rbx, [r11+30h]
0x180049bfb  mov     rsi, [r11+38h]
0x180049bff  mov     rsp, r11
0x180049c02  pop     r14
0x180049c04  pop     rdi
0x180049c05  pop     rbp
0x180049c06  retn
```
