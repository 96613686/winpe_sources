# Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddMsaProvider(int,std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData,std::allocator<Windows::Internal::ApplicationModel::Sync::ProviderData>> *)

- ea: `0x18005c930`
- end: `0x18005cc03`
- name: `?s_AddMsaProvider@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJHPEAV?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005aca0`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x180011ffc`
- `0x180056718`
- `0x180058518`
- `0x18005c930`
- `0x18005d3c4`
- `0x18005e740`
- `0x18005efd8`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c967`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c9c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ca1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ca79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cbae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cbc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cbd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c967`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c9c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ca1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ca79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cbae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cbc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cbd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddMsaProvider(int a1, __int64 a2)
{
  int AccountString; // eax
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rcx
  int WebAuthSettings; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  int WebAccountProviderDataForIDP; // eax
  int v12; // eax
  int v14; // [rsp+28h] [rbp-29h]
  int v15; // [rsp+28h] [rbp-29h]
  HSTRING string; // [rsp+38h] [rbp-19h] BYREF
  HSTRING v17; // [rsp+40h] [rbp-11h] BYREF
  __int64 v18; // [rsp+48h] [rbp-9h] BYREF
  struct Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData *v19; // [rsp+50h] [rbp-1h] BYREF
  HSTRING v20; // [rsp+58h] [rbp+7h] BYREF
  int v21; // [rsp+60h] [rbp+Fh] BYREF
  __int64 v22; // [rsp+68h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+1Fh] BYREF
  HSTRING v24; // [rsp+88h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]
  __int64 v26; // [rsp+C0h] [rbp+6Fh] BYREF

  v26 = a2;
  v20 = 0;
  WindowsDeleteString(0);
  v20 = 0;
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"MsaIdpAccountPurpose", 0x15u, 0x14u);
  AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v24, &v20);
  v4 = AccountString;
  if ( AccountString >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"MsaIdpLabel", 0xCu, 0xBu);
    v5 = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v24, &string);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v18 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
      WebAuthSettings = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetWebAuthSettings(v6, &v18);
      v4 = WebAuthSettings;
      if ( WebAuthSettings >= 0 )
      {
        v17 = 0;
        v8 = v18;
        v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 56LL);
        WindowsDeleteString(0);
        v17 = 0;
        v10 = v9(v8, &v17);
        v4 = v10;
        if ( v10 >= 0 )
        {
          v19 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
          v24 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Microsoft,Outlook",
            0x12u,
            0x11u);
          WebAccountProviderDataForIDP = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetWebAccountProviderDataForIDP(
                                           v17,
                                           string,
                                           v20,
                                           v24,
                                           a1,
                                           &v19);
          v4 = WebAccountProviderDataForIDP;
          if ( WebAccountProviderDataForIDP >= 0 )
          {
            v22 = 0;
            Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData>::operator=(
              &v22,
              &v19);
            v21 = 1;
            hstringHeader.Reserved.Reserved1 = &v26;
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v21;
            v12 = wil::ResultFromException__lambda_9736115e85b466b4debac98248661267___(&hstringHeader);
            v4 = v12;
            if ( v12 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
              WindowsDeleteString(v17);
              v17 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
              WindowsDeleteString(string);
              v4 = 0;
              goto LABEL_18;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x290,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)v12,
              v15);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x287,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)WebAccountProviderDataForIDP,
              v15);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x279,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
            (const char *)(unsigned int)v10,
            v14);
        }
        WindowsDeleteString(v17);
        v17 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x276,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)WebAuthSettings,
          v14);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x273,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
        (const char *)(unsigned int)v5,
        v14);
    }
    WindowsDeleteString(string);
LABEL_18:
    string = 0;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x270,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
    (const char *)(unsigned int)AccountString,
    v14);
LABEL_19:
  WindowsDeleteString(v20);
  return v4;
}

```

## disassembly

```asm
0x18005c930  mov     rax, rsp
0x18005c933  mov     [rax+18h], rbx
0x18005c937  mov     [rax+20h], rsi
0x18005c93b  mov     [rax+10h], rdx
0x18005c93f  push    rbp
0x18005c940  push    rdi
0x18005c941  push    r14
0x18005c943  lea     rbp, [rax-5Fh]
0x18005c947  sub     rsp, 90h
0x18005c94e  mov     rax, cs:__security_cookie
0x18005c955  xor     rax, rsp
0x18005c958  mov     [rbp+57h+var_18], rax
0x18005c95c  mov     esi, ecx
0x18005c95e  xor     r14d, r14d
0x18005c961  mov     [rbp+57h+var_50], r14
0x18005c965  xor     ecx, ecx; string
0x18005c967  call    cs:__imp_WindowsDeleteString
0x18005c96d  mov     [rbp+57h+var_50], r14
0x18005c971  mov     [rbp+57h+var_20], r14
0x18005c975  lea     r9d, [r14+14h]; unsigned int
0x18005c979  lea     r8d, [r14+15h]; unsigned int
0x18005c97d  lea     rdx, aMsaidpaccountp; "MsaIdpAccountPurpose"
0x18005c984  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005c988  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005c98d  nop
0x18005c98e  lea     rdx, [rbp+57h+var_50]; HSTRING *
0x18005c992  mov     rcx, [rbp+57h+var_20]; HSTRING
0x18005c996  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005c99b  mov     ebx, eax
0x18005c99d  test    eax, eax
0x18005c99f  jns     short loc_18005C9BE
0x18005c9a1  mov     rcx, [rbp+5Fh]; this
0x18005c9a5  mov     r9d, eax; char *
0x18005c9a8  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005c9af  mov     edx, 270h; void *
0x18005c9b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c9b9  jmp     loc_18005CBD3
0x18005c9be  mov     [rbp+57h+string], r14
0x18005c9c2  xor     ecx, ecx; string
0x18005c9c4  call    cs:__imp_WindowsDeleteString
0x18005c9ca  mov     [rbp+57h+string], r14
0x18005c9ce  mov     [rbp+57h+var_20], r14
0x18005c9d2  mov     r9d, 0Bh; unsigned int
0x18005c9d8  lea     r8d, [r9+1]; unsigned int
0x18005c9dc  lea     rdx, aMsaidplabel; "MsaIdpLabel"
0x18005c9e3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005c9e7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005c9ec  nop
0x18005c9ed  lea     rdx, [rbp+57h+string]; HSTRING *
0x18005c9f1  mov     rcx, [rbp+57h+var_20]; HSTRING
0x18005c9f5  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005c9fa  mov     ebx, eax
0x18005c9fc  test    eax, eax
0x18005c9fe  jns     short loc_18005CA28
0x18005ca00  mov     rcx, [rbp+5Fh]; this
0x18005ca04  mov     r9d, eax; char *
0x18005ca07  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005ca0e  mov     edx, 273h; void *
0x18005ca13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ca18  nop
0x18005ca19  mov     rcx, [rbp+57h+string]; string
0x18005ca1d  call    cs:__imp_WindowsDeleteString
0x18005ca23  jmp     loc_18005CBCF
0x18005ca28  mov     [rbp+57h+var_60], r14
0x18005ca2c  lea     rcx, [rbp+57h+var_60]
0x18005ca30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ca35  lea     rdx, [rbp+57h+var_60]
0x18005ca39  call    ?s_GetWebAuthSettings@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJW4PartnershipType@2Experiences@PhoneInternal@@PEAPEAUIWebAuthSettings@278@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetWebAuthSettings(PhoneInternal::Experiences::Sync::PartnershipType,PhoneInternal::Experiences::Sync::IWebAuthSettings * *)
0x18005ca3e  mov     ebx, eax
0x18005ca40  test    eax, eax
0x18005ca42  jns     short loc_18005CA68
0x18005ca44  mov     rcx, [rbp+5Fh]; this
0x18005ca48  mov     r9d, eax; char *
0x18005ca4b  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005ca52  mov     edx, 276h; void *
0x18005ca57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ca5c  nop
0x18005ca5d  lea     rcx, [rbp+57h+var_60]
0x18005ca61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ca66  jmp     short loc_18005CA19
0x18005ca68  mov     [rbp+57h+var_68], r14
0x18005ca6c  mov     rdi, [rbp+57h+var_60]
0x18005ca70  mov     rax, [rdi]
0x18005ca73  mov     rbx, [rax+38h]
0x18005ca77  xor     ecx, ecx; string
0x18005ca79  call    cs:__imp_WindowsDeleteString
0x18005ca7f  mov     [rbp+57h+var_68], r14
0x18005ca83  lea     rdx, [rbp+57h+var_68]
0x18005ca87  mov     rcx, rdi
0x18005ca8a  mov     rax, rbx
0x18005ca8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca92  mov     ebx, eax
0x18005ca94  test    eax, eax
0x18005ca96  jns     short loc_18005CAC1
0x18005ca98  mov     rcx, [rbp+5Fh]; this
0x18005ca9c  mov     r9d, eax; char *
0x18005ca9f  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005caa6  mov     edx, 279h; void *
0x18005caab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cab0  nop
0x18005cab1  mov     rcx, [rbp+57h+var_68]; string
0x18005cab5  call    cs:__imp_WindowsDeleteString
0x18005cabb  mov     [rbp+57h+var_68], r14
0x18005cabf  jmp     short loc_18005CA5D
0x18005cac1  mov     [rbp+57h+var_58], r14
0x18005cac5  lea     rcx, [rbp+57h+var_58]
0x18005cac9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cace  mov     [rbp+57h+var_20], r14
0x18005cad2  mov     r9d, 11h; unsigned int
0x18005cad8  lea     r8d, [r9+1]; unsigned int
0x18005cadc  lea     rdx, aMicrosoftOutlo; "Microsoft,Outlook"
0x18005cae3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005cae7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005caec  nop
0x18005caed  lea     rax, [rbp+57h+var_58]
0x18005caf1  mov     [rsp+0A0h+var_78], rax; struct Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData **
0x18005caf6  mov     [rsp+0A0h+var_80], esi; int
0x18005cafa  mov     r9, [rbp+57h+var_20]; HSTRING
0x18005cafe  mov     r8, [rbp+57h+var_50]; HSTRING
0x18005cb02  mov     rdx, [rbp+57h+string]; HSTRING
0x18005cb06  mov     rcx, [rbp+57h+var_68]; HSTRING
0x18005cb0a  call    ?s_GetWebAccountProviderDataForIDP@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJQEAUHSTRING__@@00PEAU6@HPEAPEAUIWebAccountProviderData@ApplicationSettings@UI@45@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetWebAccountProviderDataForIDP(HSTRING__ * const,HSTRING__ * const,HSTRING__ * const,HSTRING__ *,int,Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData * *)
0x18005cb0f  mov     ebx, eax
0x18005cb11  test    eax, eax
0x18005cb13  jns     short loc_18005CB3C
0x18005cb15  mov     rcx, [rbp+5Fh]; this
0x18005cb19  mov     r9d, eax; char *
0x18005cb1c  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005cb23  mov     edx, 287h; void *
0x18005cb28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cb2d  nop
0x18005cb2e  lea     rcx, [rbp+57h+var_58]
0x18005cb32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cb37  jmp     loc_18005CAB1
0x18005cb3c  mov     [rbp+57h+var_40], r14
0x18005cb40  lea     rdx, [rbp+57h+var_58]
0x18005cb44  lea     rcx, [rbp+57h+var_40]
0x18005cb48  call    ??4?$ComPtr@UIWebAccountProviderData@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData> const &)
0x18005cb4d  mov     [rbp+57h+var_48], 1
0x18005cb54  lea     rax, [rbp+57h+arg_8]
0x18005cb58  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18005cb5c  lea     rax, [rbp+57h+var_48]
0x18005cb60  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x18005cb64  lea     rcx, [rbp+57h+hstringHeader]
0x18005cb68  call    wil__ResultFromException__lambda_9736115e85b466b4debac98248661267___
0x18005cb6d  mov     ebx, eax
0x18005cb6f  test    eax, eax
0x18005cb71  jns     short loc_18005CB96
0x18005cb73  mov     rcx, [rbp+5Fh]; this
0x18005cb77  mov     r9d, eax; char *
0x18005cb7a  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005cb81  mov     edx, 290h; void *
0x18005cb86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cb8b  lea     rcx, [rbp+57h+var_40]
0x18005cb8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cb94  jmp     short loc_18005CB2E
0x18005cb96  lea     rcx, [rbp+57h+var_40]
0x18005cb9a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cb9f  nop
0x18005cba0  lea     rcx, [rbp+57h+var_58]
0x18005cba4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cba9  nop
0x18005cbaa  mov     rcx, [rbp+57h+var_68]; string
0x18005cbae  call    cs:__imp_WindowsDeleteString
0x18005cbb4  mov     [rbp+57h+var_68], r14
0x18005cbb8  lea     rcx, [rbp+57h+var_60]
0x18005cbbc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cbc1  nop
0x18005cbc2  mov     rcx, [rbp+57h+string]; string
0x18005cbc6  call    cs:__imp_WindowsDeleteString
0x18005cbcc  mov     ebx, r14d
0x18005cbcf  mov     [rbp+57h+string], r14
0x18005cbd3  mov     rcx, [rbp+57h+var_50]; string
0x18005cbd7  call    cs:__imp_WindowsDeleteString
0x18005cbdd  mov     eax, ebx
0x18005cbdf  mov     rcx, [rbp+57h+var_18]
0x18005cbe3  xor     rcx, rsp; StackCookie
0x18005cbe6  call    __security_check_cookie
0x18005cbeb  lea     r11, [rsp+0A0h+var_10]
0x18005cbf3  mov     rbx, [r11+30h]
0x18005cbf7  mov     rsi, [r11+38h]
0x18005cbfb  mov     rsp, r11
0x18005cbfe  pop     r14
0x18005cc00  pop     rdi
0x18005cc01  pop     rbp
0x18005cc02  retn
```
