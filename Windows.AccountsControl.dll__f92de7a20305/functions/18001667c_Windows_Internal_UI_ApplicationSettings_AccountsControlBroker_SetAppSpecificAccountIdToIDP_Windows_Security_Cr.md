# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::SetAppSpecificAccountIdToIDP(Windows::Security::Credentials::IWebAccount *)

- ea: `0x18001667c`
- end: `0x180016a28`
- name: `?SetAppSpecificAccountIdToIDP@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIWebAccount@Credentials@Security@5@@Z`
- size: `940`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, struct Windows::Security::Credentials::IWebAccount *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f5b0`
- `0x180011448`

## callees

- `0x180006eac`
- `0x1800083a8`
- `0x1800083f8`
- `0x180008e2c`
- `0x180009f38`
- `0x18000aa04`
- `0x18000e5f0`
- `0x18000e87c`
- `0x180011f64`
- `0x180011ffc`
- `0x1800165e4`
- `0x18001667c`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800168cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800169d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800169e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800168cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800169d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800169e3`

## string_xrefs

- `0x1800166dd`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180016727`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001677e`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800167f6`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180016864`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001689d`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180016931`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001696e`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800167cc`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::SetAppSpecificAccountIdToIDP(
        Microsoft::WRL::Wrappers::Details **this,
        struct Windows::Security::Credentials::IWebAccount *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Security::Credentials::IWebAccount *, __int64 *); // rbx
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  HSTRING v10; // r8
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  HSTRING v16; // rdi
  __int64 (__fastcall *v17)(HSTRING, HSTRING *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  int v22; // [rsp+20h] [rbp-39h]
  HSTRING string; // [rsp+30h] [rbp-29h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-21h] BYREF
  __int64 v25; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v26; // [rsp+48h] [rbp-11h] BYREF
  __int64 v27; // [rsp+50h] [rbp-9h] BYREF
  __int64 v28; // [rsp+58h] [rbp-1h] BYREF
  __int64 v29; // [rsp+60h] [rbp+7h] BYREF
  __int64 v30; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF
  __int64 v32; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v30 = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  v5 = v4(a2, &v30);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v25 = 0;
    v26 = (HSTRING)a2;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v26);
    v6 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
           &v26,
           &v25);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4EA,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v6,
        v22);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      goto LABEL_33;
    }
    string = 0;
    v7 = v25;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v9 = v8(v7, &string);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4EC,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v9,
        v22);
LABEL_8:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_5;
    }
    newString = 0;
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(this[80], 0, v10) )
    {
      v27 = 0;
      v32 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
        0x41u,
        0x40u);
      v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
              v32,
              &v27);
      v6 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F5,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v11,
          v22);
LABEL_12:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
LABEL_13:
        WindowsDeleteString(newString);
        newString = 0;
        goto LABEL_8;
      }
      v29 = 0;
      v12 = _lambda_ea3c615d7b6ac0412bf00512c875ea32_::_lambda_ea3c615d7b6ac0412bf00512c875ea32_(
              (unsigned int)&hstringHeader,
              (unsigned int)&v27,
              (unsigned int)&v30,
              (_DWORD)this,
              (__int64)&string,
              (__int64)&v29);
      v13 = RunInBrokerContext__lambda_e879236fc8692b73dc210f965e1e4972_(v12);
      v6 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4FC,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v13,
          v22);
LABEL_16:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        goto LABEL_12;
      }
      v26 = 0;
      v14 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
              &v29,
              &v26);
      v6 = v14;
      if ( v14 < 0 )
      {
        v15 = 1280;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v14,
          v22);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
        goto LABEL_16;
      }
      v16 = v26;
      v17 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v26 + 48LL);
      WindowsDeleteString(newString);
      newString = 0;
      v14 = v17(v16, &newString);
      v6 = v14;
      if ( v14 < 0 )
      {
        v15 = 1281;
        goto LABEL_19;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    }
    else
    {
      v26 = string;
      v20 = Microsoft::WRL::Wrappers::HString::Set(&newString, &v26);
      v6 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x505,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v20,
          v22);
        goto LABEL_13;
      }
    }
    v28 = 0;
    v18 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderSystemInformation>(
            &v30,
            &v28);
    v6 = v18;
    if ( v18 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 72LL))(v28, 0);
      v6 = v18;
      if ( v18 >= 0 )
      {
        v18 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v28 + 56LL))(v28, newString);
        v6 = v18;
        if ( v18 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
          WindowsDeleteString(newString);
          newString = 0;
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
          v6 = 0;
          goto LABEL_33;
        }
        v19 = 1294;
      }
      else
      {
        v19 = 1291;
      }
    }
    else
    {
      v19 = 1290;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v18,
      v22);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4E6,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
    (const char *)(unsigned int)v5,
    v22);
LABEL_33:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001667c  mov     [rsp-8+arg_10], rbx
0x180016681  mov     [rsp-8+arg_18], rsi
0x180016686  push    rbp
0x180016687  push    rdi
0x180016688  push    r14
0x18001668a  lea     rbp, [rsp-47h]
0x18001668f  sub     rsp, 0A0h
0x180016696  mov     rax, cs:__security_cookie
0x18001669d  xor     rax, rsp
0x1800166a0  mov     [rbp+57h+var_18], rax
0x1800166a4  mov     rdi, rdx
0x1800166a7  mov     rsi, rcx
0x1800166aa  xor     r14d, r14d
0x1800166ad  mov     [rbp+57h+var_48], r14
0x1800166b1  mov     rax, [rdx]
0x1800166b4  mov     rbx, [rax+30h]
0x1800166b8  lea     rcx, [rbp+57h+var_48]
0x1800166bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800166c1  lea     rdx, [rbp+57h+var_48]
0x1800166c5  mov     rcx, rdi
0x1800166c8  mov     rax, rbx
0x1800166cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166d0  mov     ebx, eax
0x1800166d2  test    eax, eax
0x1800166d4  jns     short loc_1800166F3
0x1800166d6  mov     rcx, [rbp+5Fh]; this
0x1800166da  mov     r9d, eax; char *
0x1800166dd  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800166e4  mov     edx, 4E6h; void *
0x1800166e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800166ee  jmp     loc_1800169F9
0x1800166f3  mov     [rbp+57h+var_70], r14
0x1800166f7  mov     [rbp+57h+var_68], rdi
0x1800166fb  lea     rcx, [rbp+57h+var_68]
0x1800166ff  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180016704  lea     rdx, [rbp+57h+var_70]
0x180016708  lea     rcx, [rbp+57h+var_68]
0x18001670c  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x180016711  mov     ebx, eax
0x180016713  lea     rcx, [rbp+57h+var_68]
0x180016717  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001671c  test    ebx, ebx
0x18001671e  jns     short loc_180016747
0x180016720  mov     rcx, [rbp+5Fh]; this
0x180016724  mov     r9d, ebx; char *
0x180016727  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001672e  mov     edx, 4EAh; void *
0x180016733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016738  nop
0x180016739  lea     rcx, [rbp+57h+var_70]
0x18001673d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016742  jmp     loc_1800169F9
0x180016747  mov     [rbp+57h+string], r14
0x18001674b  mov     rdi, [rbp+57h+var_70]
0x18001674f  mov     rax, [rdi]
0x180016752  mov     rbx, [rax+30h]
0x180016756  xor     ecx, ecx; string
0x180016758  call    cs:__imp_WindowsDeleteString
0x18001675e  mov     [rbp+57h+string], r14
0x180016762  lea     rdx, [rbp+57h+string]
0x180016766  mov     rcx, rdi
0x180016769  mov     rax, rbx
0x18001676c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016771  mov     ebx, eax
0x180016773  test    eax, eax
0x180016775  jns     short loc_1800167A0
0x180016777  mov     rcx, [rbp+5Fh]; this
0x18001677b  mov     r9d, eax; char *
0x18001677e  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180016785  mov     edx, 4ECh; void *
0x18001678a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001678f  nop
0x180016790  mov     rcx, [rbp+57h+string]; string
0x180016794  call    cs:__imp_WindowsDeleteString
0x18001679a  mov     [rbp+57h+string], r14
0x18001679e  jmp     short loc_180016739
0x1800167a0  mov     [rbp+57h+newString], r14
0x1800167a4  xor     edx, edx; HSTRING
0x1800167a6  mov     rcx, [rsi+280h]; this
0x1800167ad  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800167b2  test    eax, eax
0x1800167b4  jz      loc_18001694C
0x1800167ba  mov     [rbp+57h+var_60], r14
0x1800167be  mov     [rbp+57h+var_28], r14
0x1800167c2  mov     r9d, 40h ; '@'; unsigned int
0x1800167c8  lea     r8d, [r9+1]; unsigned int
0x1800167cc  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x1800167d3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800167d7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800167dc  lea     rdx, [rbp+57h+var_60]
0x1800167e0  mov     rcx, [rbp+57h+var_28]
0x1800167e4  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x1800167e9  mov     ebx, eax
0x1800167eb  test    eax, eax
0x1800167ed  jns     short loc_180016825
0x1800167ef  mov     rcx, [rbp+5Fh]; this
0x1800167f3  mov     r9d, eax; char *
0x1800167f6  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800167fd  mov     edx, 4F5h; void *
0x180016802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016807  nop
0x180016808  lea     rcx, [rbp+57h+var_60]
0x18001680c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016811  nop
0x180016812  mov     rcx, [rbp+57h+newString]; string
0x180016816  call    cs:__imp_WindowsDeleteString
0x18001681c  mov     [rbp+57h+newString], r14
0x180016820  jmp     loc_180016790
0x180016825  mov     [rbp+57h+var_50], r14
0x180016829  lea     rax, [rbp+57h+var_50]
0x18001682d  mov     [rsp+0B0h+var_88], rax
0x180016832  lea     rax, [rbp+57h+string]
0x180016836  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18001683b  mov     r9, rsi
0x18001683e  lea     r8, [rbp+57h+var_48]
0x180016842  lea     rdx, [rbp+57h+var_60]
0x180016846  lea     rcx, [rbp+57h+hstringHeader]
0x18001684a  call    ??0_lambda_ea3c615d7b6ac0412bf00512c875ea32_@@QEAA@PEAV?$SimpleVectorIterator@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@V?$Vector@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@U?$DefaultEqualityPredicate@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@6789@U?$VectorOptions@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@$0A@$00$0A@@6789@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@6789@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAIAEAPEAW4AccountSyncContentType@Sync@Experiences@PhoneInternal@@AEAPEAIAEAV_lambda_393af4cc79259440c365c842be03dec3_@@@Z; _lambda_ea3c615d7b6ac0412bf00512c875ea32_::_lambda_ea3c615d7b6ac0412bf00512c875ea32_(Windows::Foundation::Collections::Internal::SimpleVectorIterator<PhoneInternal::Experiences::Sync::AccountSyncContentType,Windows::Foundation::Collections::Internal::Vector<PhoneInternal::Experiences::Sync::AccountSyncContentType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<PhoneInternal::Experiences::Sync::AccountSyncContentType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<PhoneInternal::Experiences::Sync::AccountSyncContentType>,Windows::Foundation::Collections::Internal::VectorOptions<PhoneInternal::Experiences::Sync::AccountSyncContentType,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<PhoneInternal::Experiences::Sync::AccountSyncContentType>,XWinRT::IntVersionTag,1> *,uint &,PhoneInternal::Experiences::Sync::AccountSyncContentType * &,uint * &,_lambda_393af4cc79259440c365c842be03dec3_ &)
0x18001684f  mov     rcx, rax
0x180016852  call    RunInBrokerContext__lambda_e879236fc8692b73dc210f965e1e4972___; RunInBrokerContext__lambda_e879236fc8692b73dc210f965e1e4972_
0x180016857  mov     ebx, eax
0x180016859  test    eax, eax
0x18001685b  jns     short loc_180016881
0x18001685d  mov     rcx, [rbp+5Fh]; this
0x180016861  mov     r9d, eax; char *
0x180016864  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001686b  mov     edx, 4FCh; void *
0x180016870  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016875  nop
0x180016876  lea     rcx, [rbp+57h+var_50]
0x18001687a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001687f  jmp     short loc_180016808
0x180016881  mov     [rbp+57h+var_68], r14
0x180016885  lea     rdx, [rbp+57h+var_68]
0x180016889  lea     rcx, [rbp+57h+var_50]
0x18001688d  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x180016892  mov     ebx, eax
0x180016894  test    eax, eax
0x180016896  jns     short loc_1800168BC
0x180016898  mov     edx, 500h; void *
0x18001689d  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800168a4  mov     r9d, eax; char *
0x1800168a7  mov     rcx, [rbp+5Fh]; this
0x1800168ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168b0  nop
0x1800168b1  lea     rcx, [rbp+57h+var_68]
0x1800168b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800168ba  jmp     short loc_180016876
0x1800168bc  mov     rdi, [rbp+57h+var_68]
0x1800168c0  mov     rax, [rdi]
0x1800168c3  mov     rbx, [rax+30h]
0x1800168c7  mov     rcx, [rbp+57h+newString]; string
0x1800168cb  call    cs:__imp_WindowsDeleteString
0x1800168d1  mov     [rbp+57h+newString], r14
0x1800168d5  lea     rdx, [rbp+57h+newString]
0x1800168d9  mov     rcx, rdi
0x1800168dc  mov     rax, rbx
0x1800168df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e4  mov     ebx, eax
0x1800168e6  test    eax, eax
0x1800168e8  jns     short loc_1800168F1
0x1800168ea  mov     edx, 501h
0x1800168ef  jmp     short loc_18001689D
0x1800168f1  lea     rcx, [rbp+57h+var_68]
0x1800168f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800168fa  nop
0x1800168fb  lea     rcx, [rbp+57h+var_50]
0x1800168ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016904  nop
0x180016905  lea     rcx, [rbp+57h+var_60]
0x180016909  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001690e  mov     [rbp+57h+var_58], r14
0x180016912  lea     rdx, [rbp+57h+var_58]
0x180016916  lea     rcx, [rbp+57h+var_48]
0x18001691a  call    ??$As@UIWebAccountProviderSystemInformation@Credentials@Security@Internal@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProviderSystemInformation@Credentials@Security@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderSystemInformation>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountProviderSystemInformation>>)
0x18001691f  mov     ebx, eax
0x180016921  test    eax, eax
0x180016923  jns     short loc_180016984
0x180016925  mov     edx, 50Ah; void *
0x18001692a  mov     rcx, [rbp+5Fh]; this
0x18001692e  mov     r9d, eax; char *
0x180016931  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180016938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001693d  nop
0x18001693e  lea     rcx, [rbp+57h+var_58]
0x180016942  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016947  jmp     loc_180016812
0x18001694c  mov     rax, [rbp+57h+string]
0x180016950  mov     [rbp+57h+var_68], rax
0x180016954  lea     rdx, [rbp+57h+var_68]; HSTRING *
0x180016958  lea     rcx, [rbp+57h+newString]; newString
0x18001695c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180016961  mov     ebx, eax
0x180016963  test    eax, eax
0x180016965  jns     short loc_18001690E
0x180016967  mov     rcx, [rbp+5Fh]; this
0x18001696b  mov     r9d, eax; char *
0x18001696e  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180016975  mov     edx, 505h; void *
0x18001697a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001697f  jmp     loc_180016812
0x180016984  mov     rcx, [rbp+57h+var_58]
0x180016988  mov     rax, [rcx]
0x18001698b  xor     edx, edx
0x18001698d  mov     rax, [rax+48h]
0x180016991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016996  mov     ebx, eax
0x180016998  test    eax, eax
0x18001699a  jns     short loc_1800169A3
0x18001699c  mov     edx, 50Bh
0x1800169a1  jmp     short loc_18001692A
0x1800169a3  mov     rcx, [rbp+57h+var_58]
0x1800169a7  mov     rax, [rcx]
0x1800169aa  mov     rdx, [rbp+57h+newString]
0x1800169ae  mov     rax, [rax+38h]
0x1800169b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169b7  mov     ebx, eax
0x1800169b9  test    eax, eax
0x1800169bb  jns     short loc_1800169C7
0x1800169bd  mov     edx, 50Eh
0x1800169c2  jmp     loc_18001692A
0x1800169c7  lea     rcx, [rbp+57h+var_58]
0x1800169cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800169d0  nop
0x1800169d1  mov     rcx, [rbp+57h+newString]; string
0x1800169d5  call    cs:__imp_WindowsDeleteString
0x1800169db  mov     [rbp+57h+newString], r14
0x1800169df  mov     rcx, [rbp+57h+string]; string
0x1800169e3  call    cs:__imp_WindowsDeleteString
0x1800169e9  mov     [rbp+57h+string], r14
0x1800169ed  lea     rcx, [rbp+57h+var_70]
0x1800169f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800169f6  mov     ebx, r14d
0x1800169f9  lea     rcx, [rbp+57h+var_48]
0x1800169fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016a02  mov     eax, ebx
0x180016a04  mov     rcx, [rbp+57h+var_18]
0x180016a08  xor     rcx, rsp; StackCookie
0x180016a0b  call    __security_check_cookie
0x180016a10  lea     r11, [rsp+0B0h+var_10]
0x180016a18  mov     rbx, [r11+30h]
0x180016a1c  mov     rsi, [r11+38h]
0x180016a20  mov     rsp, r11
0x180016a23  pop     r14
0x180016a25  pop     rdi
0x180016a26  pop     rbp
0x180016a27  retn
```
