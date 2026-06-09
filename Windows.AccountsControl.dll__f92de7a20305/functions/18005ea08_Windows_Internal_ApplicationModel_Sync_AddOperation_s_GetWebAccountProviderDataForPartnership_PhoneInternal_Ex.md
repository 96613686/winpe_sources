# Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetWebAccountProviderDataForPartnership(PhoneInternal::Experiences::Sync::PartnershipType,int,Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData * *)

- ea: `0x18005ea08`
- end: `0x18005ed72`
- name: `?s_GetWebAccountProviderDataForPartnership@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJW4PartnershipType@2Experiences@PhoneInternal@@HPEAPEAUIWebAccountProviderData@ApplicationSettings@UI@45@@Z`
- size: `874`
- prototype: `static int __high(enum PhoneInternal::Experiences::Sync::PartnershipType, int, struct Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ccfc`

## callees

- `0x180006eac`
- `0x180007f68`
- `0x18000e87c`
- `0x18005d3c4`
- `0x18005ea08`
- `0x18005ed78`
- `0x180069730`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ea86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eadd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eb34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eb8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ebd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ec34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ec7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ea86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eadd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eb34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eb8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ebd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ec34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ec7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed42`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetWebAccountProviderDataForPartnership(
        int a1,
        int a2,
        struct Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData **a3)
{
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int AccountString; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  const wchar_t *v12; // rax
  HSTRING v13; // rbx
  HSTRING v14; // rdi
  HSTRING v15; // rsi
  __int64 v16; // rax
  int v18; // [rsp+20h] [rbp-49h]
  HSTRING v19; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string; // [rsp+38h] [rbp-31h] BYREF
  const wchar_t *v21; // [rsp+40h] [rbp-29h]
  const wchar_t *v22; // [rsp+48h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-19h] BYREF
  HSTRING v24; // [rsp+68h] [rbp-1h]
  HSTRING_HEADER v25; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a3 = 0;
  v21 = 0;
  v22 = 0;
  v19 = 0;
  string = 0;
  v5 = a1 - 3;
  if ( !v5 )
  {
    v21 = L"Windows.Internal.ApplicationModel.Sync.Provider.ActiveSyncExchange";
    WindowsDeleteString(0);
    v19 = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"ExchangeActiveSyncAccountName",
      0x1Eu,
      0x1Du);
    AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v24, &v19);
    v10 = AccountString;
    if ( AccountString < 0 )
    {
      v11 = 521;
      goto LABEL_21;
    }
    WindowsDeleteString(string);
    string = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"ExchangeActiveSyncAccountPurpose",
      0x21u,
      0x20u);
    AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v24, &string);
    v10 = AccountString;
    if ( AccountString < 0 )
    {
      v11 = 522;
      goto LABEL_21;
    }
    v12 = L"Microsoft,Exchange";
    goto LABEL_23;
  }
  v6 = v5 - 3;
  if ( !v6 )
  {
    v21 = L"Windows.Internal.ApplicationModel.Sync.Provider.InternetMailPopImap";
    WindowsDeleteString(0);
    v19 = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"InternetMailPopImapAccountName",
      0x1Fu,
      0x1Eu);
    AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v24, &v19);
    v10 = AccountString;
    if ( AccountString < 0 )
    {
      v11 = 530;
      goto LABEL_21;
    }
    WindowsDeleteString(string);
    string = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"InternetMailPopImapAccountPurpose",
      0x22u,
      0x21u);
    AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v24, &string);
    v10 = AccountString;
    if ( AccountString < 0 )
    {
      v11 = 531;
      goto LABEL_21;
    }
LABEL_16:
    v12 = L"Microsoft,Generic";
LABEL_23:
    v22 = v12;
    goto LABEL_24;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v21 = L"Windows.Internal.ApplicationModel.Sync.Provider.InternetGoogle";
    WindowsDeleteString(0);
    v19 = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"InternetMailGoogleAccountName",
      0x1Eu,
      0x1Du);
    AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v24, &v19);
    v10 = AccountString;
    if ( AccountString < 0 )
    {
      v11 = 539;
      goto LABEL_21;
    }
    goto LABEL_16;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v21 = L"Windows.Internal.ApplicationModel.Sync.Provider.InternetIcloud";
    WindowsDeleteString(0);
    v19 = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"InternetMailICloudAccountName",
      0x1Eu,
      0x1Du);
    AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v24, &v19);
    v10 = AccountString;
    if ( AccountString < 0 )
    {
      v11 = 547;
      goto LABEL_21;
    }
    goto LABEL_16;
  }
  if ( v8 == 2 )
  {
    v21 = L"Windows.Internal.ApplicationModel.Sync.Provider.InternetYahoo";
    WindowsDeleteString(0);
    v19 = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"InternetYahooMailAccountName",
      0x1Du,
      0x1Cu);
    AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v24, &v19);
    v10 = AccountString;
    if ( AccountString < 0 )
    {
      v11 = 555;
      goto LABEL_21;
    }
    goto LABEL_16;
  }
LABEL_24:
  v13 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader) + 24);
  v14 = string;
  v15 = v19;
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v25);
  AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetWebAccountProviderDataFromProperties(
                    *(HSTRING *)(v16 + 24),
                    v15,
                    v14,
                    v13,
                    a2,
                    a3);
  v10 = AccountString;
  if ( AccountString >= 0 )
  {
    v10 = 0;
    goto LABEL_27;
  }
  v11 = 573;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
    (const char *)(unsigned int)AccountString,
    v18);
LABEL_27:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v19);
  return v10;
}

```

## disassembly

```asm
0x18005ea08  mov     [rsp-8+arg_0], rbx
0x18005ea0d  mov     [rsp-8+arg_18], rsi
0x18005ea12  push    rbp
0x18005ea13  push    rdi
0x18005ea14  push    r12
0x18005ea16  push    r14
0x18005ea18  push    r15
0x18005ea1a  lea     rbp, [rsp-37h]
0x18005ea1f  sub     rsp, 0A0h
0x18005ea26  mov     rax, cs:__security_cookie
0x18005ea2d  xor     rax, rsp
0x18005ea30  mov     [rbp+57h+var_30], rax
0x18005ea34  mov     r14, r8
0x18005ea37  mov     r15d, edx
0x18005ea3a  xor     r12d, r12d
0x18005ea3d  mov     [r8], r12
0x18005ea40  mov     [rbp+57h+var_80], r12
0x18005ea44  mov     [rbp+57h+var_78], r12
0x18005ea48  mov     [rbp+57h+var_90], r12
0x18005ea4c  mov     [rbp+57h+string], r12
0x18005ea50  sub     ecx, 3
0x18005ea53  jz      loc_18005EC27
0x18005ea59  sub     ecx, 3
0x18005ea5c  jz      loc_18005EB7E
0x18005ea62  sub     ecx, 1
0x18005ea65  jz      loc_18005EB27
0x18005ea6b  sub     ecx, 1
0x18005ea6e  jz      short loc_18005EAD0
0x18005ea70  cmp     ecx, 2
0x18005ea73  jnz     loc_18005ECDC
0x18005ea79  lea     rax, aWindowsInterna_0; "Windows.Internal.ApplicationModel.Sync."...
0x18005ea80  mov     [rbp+57h+var_80], rax
0x18005ea84  xor     ecx, ecx; string
0x18005ea86  call    cs:__imp_WindowsDeleteString
0x18005ea8c  mov     [rbp+57h+var_90], r12
0x18005ea90  mov     [rbp+57h+var_58], r12
0x18005ea94  lea     r9d, [r12+1Ch]; unsigned int
0x18005ea99  lea     r8d, [r12+1Dh]; unsigned int
0x18005ea9e  lea     rdx, aInternetyahoom; "InternetYahooMailAccountName"
0x18005eaa5  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005eaa9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005eaae  nop
0x18005eaaf  lea     rdx, [rbp+57h+var_90]; HSTRING *
0x18005eab3  mov     rcx, [rbp+57h+var_58]; HSTRING
0x18005eab7  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005eabc  mov     ebx, eax
0x18005eabe  test    eax, eax
0x18005eac0  jns     loc_18005EC1B
0x18005eac6  mov     edx, 22Bh
0x18005eacb  jmp     loc_18005ECBC
0x18005ead0  lea     rax, aWindowsInterna_16; "Windows.Internal.ApplicationModel.Sync."...
0x18005ead7  mov     [rbp+57h+var_80], rax
0x18005eadb  xor     ecx, ecx; string
0x18005eadd  call    cs:__imp_WindowsDeleteString
0x18005eae3  mov     [rbp+57h+var_90], r12
0x18005eae7  mov     [rbp+57h+var_58], r12
0x18005eaeb  mov     r9d, 1Dh; unsigned int
0x18005eaf1  lea     r8d, [r9+1]; unsigned int
0x18005eaf5  lea     rdx, aInternetmailic; "InternetMailICloudAccountName"
0x18005eafc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005eb00  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005eb05  nop
0x18005eb06  lea     rdx, [rbp+57h+var_90]; HSTRING *
0x18005eb0a  mov     rcx, [rbp+57h+var_58]; HSTRING
0x18005eb0e  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005eb13  mov     ebx, eax
0x18005eb15  test    eax, eax
0x18005eb17  jns     loc_18005EC1B
0x18005eb1d  mov     edx, 223h
0x18005eb22  jmp     loc_18005ECBC
0x18005eb27  lea     rax, aWindowsInterna_11; "Windows.Internal.ApplicationModel.Sync."...
0x18005eb2e  mov     [rbp+57h+var_80], rax
0x18005eb32  xor     ecx, ecx; string
0x18005eb34  call    cs:__imp_WindowsDeleteString
0x18005eb3a  mov     [rbp+57h+var_90], r12
0x18005eb3e  mov     [rbp+57h+var_58], r12
0x18005eb42  mov     r9d, 1Dh; unsigned int
0x18005eb48  lea     r8d, [r9+1]; unsigned int
0x18005eb4c  lea     rdx, aInternetmailgo; "InternetMailGoogleAccountName"
0x18005eb53  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005eb57  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005eb5c  nop
0x18005eb5d  lea     rdx, [rbp+57h+var_90]; HSTRING *
0x18005eb61  mov     rcx, [rbp+57h+var_58]; HSTRING
0x18005eb65  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005eb6a  mov     ebx, eax
0x18005eb6c  test    eax, eax
0x18005eb6e  jns     loc_18005EC1B
0x18005eb74  mov     edx, 21Bh
0x18005eb79  jmp     loc_18005ECBC
0x18005eb7e  lea     rax, aWindowsInterna_8; "Windows.Internal.ApplicationModel.Sync."...
0x18005eb85  mov     [rbp+57h+var_80], rax
0x18005eb89  xor     ecx, ecx; string
0x18005eb8b  call    cs:__imp_WindowsDeleteString
0x18005eb91  mov     [rbp+57h+var_90], r12
0x18005eb95  mov     [rbp+57h+var_58], r12
0x18005eb99  mov     r9d, 1Eh; unsigned int
0x18005eb9f  lea     r8d, [r9+1]; unsigned int
0x18005eba3  lea     rdx, aInternetmailpo_0; "InternetMailPopImapAccountName"
0x18005ebaa  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ebae  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005ebb3  nop
0x18005ebb4  lea     rdx, [rbp+57h+var_90]; HSTRING *
0x18005ebb8  mov     rcx, [rbp+57h+var_58]; HSTRING
0x18005ebbc  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005ebc1  mov     ebx, eax
0x18005ebc3  test    eax, eax
0x18005ebc5  jns     short loc_18005EBD1
0x18005ebc7  mov     edx, 212h
0x18005ebcc  jmp     loc_18005ECBC
0x18005ebd1  mov     rcx, [rbp+57h+string]; string
0x18005ebd5  call    cs:__imp_WindowsDeleteString
0x18005ebdb  mov     [rbp+57h+string], r12
0x18005ebdf  mov     [rbp+57h+var_58], r12
0x18005ebe3  mov     r9d, 21h ; '!'; unsigned int
0x18005ebe9  lea     r8d, [r9+1]; unsigned int
0x18005ebed  lea     rdx, aInternetmailpo; "InternetMailPopImapAccountPurpose"
0x18005ebf4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ebf8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005ebfd  nop
0x18005ebfe  lea     rdx, [rbp+57h+string]; HSTRING *
0x18005ec02  mov     rcx, [rbp+57h+var_58]; HSTRING
0x18005ec06  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005ec0b  mov     ebx, eax
0x18005ec0d  test    eax, eax
0x18005ec0f  jns     short loc_18005EC1B
0x18005ec11  mov     edx, 213h
0x18005ec16  jmp     loc_18005ECBC
0x18005ec1b  lea     rax, aMicrosoftGener; "Microsoft,Generic"
0x18005ec22  jmp     loc_18005ECD8
0x18005ec27  lea     rax, aWindowsInterna_2; "Windows.Internal.ApplicationModel.Sync."...
0x18005ec2e  mov     [rbp+57h+var_80], rax
0x18005ec32  xor     ecx, ecx; string
0x18005ec34  call    cs:__imp_WindowsDeleteString
0x18005ec3a  mov     [rbp+57h+var_90], r12
0x18005ec3e  mov     [rbp+57h+var_58], r12
0x18005ec42  mov     r9d, 1Dh; unsigned int
0x18005ec48  lea     r8d, [r9+1]; unsigned int
0x18005ec4c  lea     rdx, aExchangeactive; "ExchangeActiveSyncAccountName"
0x18005ec53  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ec57  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005ec5c  nop
0x18005ec5d  lea     rdx, [rbp+57h+var_90]; HSTRING *
0x18005ec61  mov     rcx, [rbp+57h+var_58]; HSTRING
0x18005ec65  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005ec6a  mov     ebx, eax
0x18005ec6c  test    eax, eax
0x18005ec6e  jns     short loc_18005EC77
0x18005ec70  mov     edx, 209h
0x18005ec75  jmp     short loc_18005ECBC
0x18005ec77  mov     rcx, [rbp+57h+string]; string
0x18005ec7b  call    cs:__imp_WindowsDeleteString
0x18005ec81  mov     [rbp+57h+string], r12
0x18005ec85  mov     [rbp+57h+var_58], r12
0x18005ec89  mov     r9d, 20h ; ' '; unsigned int
0x18005ec8f  lea     r8d, [r9+1]; unsigned int
0x18005ec93  lea     rdx, aExchangeactive_0; "ExchangeActiveSyncAccountPurpose"
0x18005ec9a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ec9e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005eca3  nop
0x18005eca4  lea     rdx, [rbp+57h+string]; HSTRING *
0x18005eca8  mov     rcx, [rbp+57h+var_58]; HSTRING
0x18005ecac  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005ecb1  mov     ebx, eax
0x18005ecb3  test    eax, eax
0x18005ecb5  jns     short loc_18005ECD1
0x18005ecb7  mov     edx, 20Ah; void *
0x18005ecbc  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005ecc3  mov     r9d, eax; char *
0x18005ecc6  mov     rcx, [rbp+5Fh]; this
0x18005ecca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eccf  jmp     short loc_18005ED30
0x18005ecd1  lea     rax, aMicrosoftExcha; "Microsoft,Exchange"
0x18005ecd8  mov     [rbp+57h+var_78], rax
0x18005ecdc  lea     rdx, [rbp+57h+var_78]
0x18005ece0  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ece4  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18005ece9  nop
0x18005ecea  mov     rbx, [rax+18h]
0x18005ecee  mov     rdi, [rbp+57h+string]
0x18005ecf2  mov     rsi, [rbp+57h+var_90]
0x18005ecf6  lea     rdx, [rbp+57h+var_80]
0x18005ecfa  lea     rcx, [rbp+57h+var_50]; hstringHeader
0x18005ecfe  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18005ed03  nop
0x18005ed04  mov     [rsp+0C0h+var_98], r14; struct Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData **
0x18005ed09  mov     [rsp+0C0h+var_A0], r15d; int
0x18005ed0e  mov     r9, rbx; HSTRING
0x18005ed11  mov     r8, rdi; HSTRING
0x18005ed14  mov     rdx, rsi; HSTRING
0x18005ed17  mov     rcx, [rax+18h]; HSTRING
0x18005ed1b  call    ?s_GetWebAccountProviderDataFromProperties@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@000HPEAPEAUIWebAccountProviderData@ApplicationSettings@UI@45@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetWebAccountProviderDataFromProperties(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,int,Windows::Internal::UI::ApplicationSettings::IWebAccountProviderData * *)
0x18005ed20  mov     ebx, eax
0x18005ed22  test    eax, eax
0x18005ed24  jns     short loc_18005ED2D
0x18005ed26  mov     edx, 23Dh
0x18005ed2b  jmp     short loc_18005ECBC
0x18005ed2d  mov     ebx, r12d
0x18005ed30  mov     rcx, [rbp+57h+string]; string
0x18005ed34  call    cs:__imp_WindowsDeleteString
0x18005ed3a  mov     [rbp+57h+string], r12
0x18005ed3e  mov     rcx, [rbp+57h+var_90]; string
0x18005ed42  call    cs:__imp_WindowsDeleteString
0x18005ed48  mov     eax, ebx
0x18005ed4a  mov     rcx, [rbp+57h+var_30]
0x18005ed4e  xor     rcx, rsp; StackCookie
0x18005ed51  call    __security_check_cookie
0x18005ed56  lea     r11, [rsp+0C0h+var_20]
0x18005ed5e  mov     rbx, [r11+30h]
0x18005ed62  mov     rsi, [r11+48h]
0x18005ed66  mov     rsp, r11
0x18005ed69  pop     r15
0x18005ed6b  pop     r14
0x18005ed6d  pop     r12
0x18005ed6f  pop     rdi
0x18005ed70  pop     rbp
0x18005ed71  retn
```
