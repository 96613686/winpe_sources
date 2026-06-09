# Windows::Internal::ApplicationModel::Sync::MailContactsCalendarSyncUIFactory::s_IsCurrentPlatformSupported(uchar *)

- ea: `0x180054a50`
- end: `0x180054bdb`
- name: `?s_IsCurrentPlatformSupported@MailContactsCalendarSyncUIFactory@Sync@ApplicationModel@Internal@Windows@@CAJPEAE@Z`
- size: `395`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004fcb0`
- `0x18004fdcc`
- `0x180053220`
- `0x180053540`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x180011ffc`
- `0x18001908c`
- `0x1800224a8`
- `0x18004a7c8`
- `0x18004ef9c`
- `0x180054a50`
- `0x180069730`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054b29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054b75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054b29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054b75`

## string_xrefs

- `0x180054a90`: `Windows.Internal.UI.ApplicationSettings.AccountsControlBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::MailContactsCalendarSyncUIFactory::s_IsCurrentPlatformSupported(
        unsigned __int8 *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int UserDataAccountsProvider; // eax
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 v8; // [rsp+28h] [rbp-38h] BYREF
  __int64 v9; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  __int64 v11; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  *a1 = 0;
  v9 = 0;
  v11 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.UI.ApplicationSettings.AccountsControlBroker",
    0x3Eu,
    0x3Du);
  v2 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IAccountsControlBrokerFactory>>(
         v11,
         &v9);
  v3 = v2;
  if ( v2 == -2147221164 )
    goto LABEL_12;
  if ( v2 >= 0 )
  {
    v8 = 0;
    v11 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"PhoneInternal.Experiences.Sync.AccountsManager",
      0x2Fu,
      0x2Eu);
    v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<PhoneInternal::Experiences::Sync::IAccountsManagerStatics>>(
           v11,
           &v8);
    v3 = v4;
    if ( v4 == -2147221164 )
    {
      WindowsDeleteString(0);
      string = 0;
      UserDataAccountsProvider = GetUserDataAccountsProvider(&string);
      if ( UserDataAccountsProvider < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1AC,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\mailcontactscalendarsyncui.cpp",
          (const char *)(unsigned int)UserDataAccountsProvider,
          (int)string);
      if ( !string )
      {
        WindowsDeleteString(0);
        string = 0;
LABEL_11:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
LABEL_12:
        v3 = 0;
        goto LABEL_13;
      }
      WindowsDeleteString(string);
    }
    else if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B1,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\mailcontactscalendarsyncui.cpp",
        (const char *)(unsigned int)v4,
        (int)string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
      goto LABEL_13;
    }
    *a1 = 1;
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A3,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\mailcontactscalendarsyncui.cpp",
    (const char *)(unsigned int)v2,
    (int)string);
LABEL_13:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  return v3;
}

```

## disassembly

```asm
0x180054a50  mov     [rsp-8+arg_8], rbx
0x180054a55  mov     [rsp-8+arg_10], rdi
0x180054a5a  push    rbp
0x180054a5b  mov     rbp, rsp
0x180054a5e  sub     rsp, 60h
0x180054a62  mov     rax, cs:__security_cookie
0x180054a69  xor     rax, rsp
0x180054a6c  mov     [rbp+var_8], rax
0x180054a70  mov     rdi, rcx
0x180054a73  mov     byte ptr [rcx], 0
0x180054a76  mov     [rbp+var_30], 0
0x180054a7e  mov     [rbp+var_10], 0
0x180054a86  mov     r9d, 3Dh ; '='; unsigned int
0x180054a8c  lea     r8d, [r9+1]; unsigned int
0x180054a90  lea     rdx, ?RuntimeClass_Windows_Internal_UI_ApplicationSettings_AccountsControlBroker@@3QBGB; "Windows.Internal.UI.ApplicationSettings"...
0x180054a97  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180054a9b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180054aa0  lea     rdx, [rbp+var_30]
0x180054aa4  mov     rcx, [rbp+var_10]
0x180054aa8  call    ??$GetActivationFactory@V?$ComPtr@UIAccountsControlBrokerFactory@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAccountsControlBrokerFactory@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IAccountsControlBrokerFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IAccountsControlBrokerFactory>>)
0x180054aad  mov     ebx, eax
0x180054aaf  cmp     eax, 80040154h
0x180054ab4  jz      loc_180054B87
0x180054aba  test    eax, eax
0x180054abc  jns     short loc_180054ADB
0x180054abe  mov     rcx, [rbp+8]; this
0x180054ac2  mov     r9d, eax; char *
0x180054ac5  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\accountscontrol\\api"...
0x180054acc  mov     edx, 1A3h; void *
0x180054ad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054ad6  jmp     loc_180054B89
0x180054adb  mov     [rbp+var_38], 0
0x180054ae3  mov     [rbp+var_10], 0
0x180054aeb  mov     r9d, 2Eh ; '.'; unsigned int
0x180054af1  lea     r8d, [r9+1]; unsigned int
0x180054af5  lea     rdx, ?RuntimeClass_PhoneInternal_Experiences_Sync_AccountsManager@@3QBGB; "PhoneInternal.Experiences.Sync.Accounts"...
0x180054afc  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180054b00  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180054b05  lea     rdx, [rbp+var_38]
0x180054b09  mov     rcx, [rbp+var_10]
0x180054b0d  call    ??$GetActivationFactory@V?$ComPtr@UIAccountsManagerStatics@Sync@Experiences@PhoneInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAccountsManagerStatics@Sync@Experiences@PhoneInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<PhoneInternal::Experiences::Sync::IAccountsManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<PhoneInternal::Experiences::Sync::IAccountsManagerStatics>>)
0x180054b12  mov     ebx, eax
0x180054b14  cmp     eax, 80040154h
0x180054b19  jnz     loc_180054BB2
0x180054b1f  mov     [rbp+string], 0
0x180054b27  xor     ecx, ecx; string
0x180054b29  call    cs:__imp_WindowsDeleteString
0x180054b2f  mov     [rbp+string], 0
0x180054b37  lea     rcx, [rbp+string]; HSTRING *
0x180054b3b  call    ?GetUserDataAccountsProvider@@YAJPEAPEAUHSTRING__@@@Z; GetUserDataAccountsProvider(HSTRING__ * *)
0x180054b40  mov     rcx, [rbp+8]; this
0x180054b44  test    eax, eax
0x180054b46  jns     short loc_180054B5C
0x180054b48  mov     r9d, eax; char *
0x180054b4b  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\accountscontrol\\api"...
0x180054b52  mov     edx, 1ACh; void *
0x180054b57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054b5c  mov     rcx, [rbp+string]; string
0x180054b60  test    rcx, rcx
0x180054b63  jnz     short loc_180054B75
0x180054b65  call    cs:__imp_WindowsDeleteString
0x180054b6b  mov     [rbp+string], 0
0x180054b73  jmp     short loc_180054B7E
0x180054b75  call    cs:__imp_WindowsDeleteString
0x180054b7b  mov     byte ptr [rdi], 1
0x180054b7e  lea     rcx, [rbp+var_38]
0x180054b82  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054b87  xor     ebx, ebx
0x180054b89  lea     rcx, [rbp+var_30]
0x180054b8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054b92  mov     eax, ebx
0x180054b94  mov     rcx, [rbp+var_8]
0x180054b98  xor     rcx, rsp; StackCookie
0x180054b9b  call    __security_check_cookie
0x180054ba0  lea     r11, [rsp+60h+var_s0]
0x180054ba5  mov     rbx, [r11+18h]
0x180054ba9  mov     rdi, [r11+20h]
0x180054bad  mov     rsp, r11
0x180054bb0  pop     rbp
0x180054bb1  retn
0x180054bb2  test    eax, eax
0x180054bb4  jns     short loc_180054B7B
0x180054bb6  mov     rcx, [rbp+8]; this
0x180054bba  mov     r9d, eax; char *
0x180054bbd  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\accountscontrol\\api"...
0x180054bc4  mov     edx, 1B1h; void *
0x180054bc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054bce  nop
0x180054bcf  lea     rcx, [rbp+var_38]
0x180054bd3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054bd8  jmp     short loc_180054B89
```
