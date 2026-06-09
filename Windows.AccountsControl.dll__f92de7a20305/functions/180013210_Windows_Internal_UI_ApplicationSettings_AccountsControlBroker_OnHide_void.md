# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::OnHide(void)

- ea: `0x180013210`
- end: `0x18001378d`
- name: `?OnHide@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@EEAAJXZ`
- size: `1405`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006eac`
- `0x180008218`
- `0x180008f1c`
- `0x180008fb8`
- `0x180009058`
- `0x18000a0e4`
- `0x18000a220`
- `0x18000b6a4`
- `0x18000c284`
- `0x18000cf4c`
- `0x18000db14`
- `0x18000ded4`
- `0x18000e454`
- `0x18000e5f0`
- `0x18000e668`
- `0x18000e87c`
- `0x18000f5b0`
- `0x180011448`
- `0x180011ffc`
- `0x180013210`
- `0x18001745c`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013377`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800135ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013738`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013377`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800135ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013738`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001361b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001361b`

## string_xrefs

- `0x1800132c5`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013360`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013415`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013471`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800134de`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800135a1`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001339f`: `TokenBrokerAccount`
- `0x18001367f`: `TokenBrokerAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::OnHide(
        struct Windows::Foundation::Collections::IPropertySet **this)
{
  AccountsControlTelemetry::AccountsControlBrokerActivity *v2; // rsi
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING, char *); // rbx
  int v8; // eax
  HSTRING v9; // r8
  int v10; // eax
  int TokenBrokerProviderIndex; // eax
  int v12; // eax
  HSTRING v13; // r8
  int AADTokenBrokerProviderIndex; // eax
  __int64 v15; // rdx
  unsigned __int8 v16; // bl
  const unsigned __int16 *StringRawBuffer; // rax
  int string; // [rsp+20h] [rbp-99h]
  HSTRING stringa; // [rsp+20h] [rbp-99h]
  char v21; // [rsp+28h] [rbp-91h] BYREF
  unsigned __int8 v22; // [rsp+29h] [rbp-90h]
  HSTRING v23; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v24[8]; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-75h]
  __int64 v27; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v28[80]; // [rsp+50h] [rbp-69h] BYREF
  HSTRING_HEADER v29; // [rsp+A0h] [rbp-19h] BYREF
  HSTRING v30; // [rsp+B8h] [rbp-1h]
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp+7h] BYREF
  HSTRING v32; // [rsp+D8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = (AccountsControlTelemetry::AccountsControlBrokerActivity *)(this + 78);
  wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
    (struct wil::details::IFailureCallback *)(this + 78),
    (wil::ActivityThreadWatcher *)v28);
  v27 = 0;
  v3 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
         this + 122,
         &v27);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v21 = 1;
    v6 = v27;
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v27 + 64LL);
    v32 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ItemType", 9u, 8u);
    v3 = v7(v6, v32, &v21);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = 533;
      goto LABEL_5;
    }
    if ( !v21 )
    {
      AccountsControlTelemetry::AccountsControlBrokerActivity::CloseUIWithNoItemSelected(v2);
      wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(v2);
LABEL_35:
      v4 = 0;
      goto LABEL_36;
    }
    Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(
      (Windows::Internal::ShellHelpers::PropertySetHelper *)v24,
      this[122]);
    WindowsDeleteString(0);
    v32 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ItemType", 9u, 8u);
    v8 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
           (Windows::Internal::ShellHelpers::PropertySetHelper *)v24,
           v32);
    v4 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v8,
        0);
LABEL_10:
      WindowsDeleteString(stringa);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v24);
      goto LABEL_36;
    }
    v32 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TokenBrokerAccount", 0x13u, 0x12u);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(0, v32, v9) )
    {
      v30 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"BubbleHead", 0xBu, 0xAu);
      if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(0, v30, v13) )
      {
        v23 = 0;
        WindowsDeleteString(0);
        v23 = 0;
        v30 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"UPN", 4u, 3u);
        AADTokenBrokerProviderIndex = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
                                        (Windows::Internal::ShellHelpers::PropertySetHelper *)v24,
                                        v30);
        v4 = AADTokenBrokerProviderIndex;
        if ( AADTokenBrokerProviderIndex >= 0 )
        {
          v22 = 0;
          v30 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"IsAAD", 6u, 5u);
          AADTokenBrokerProviderIndex = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned char>(
                                          (Windows::Internal::ShellHelpers::PropertySetHelper *)v24,
                                          v30);
          v4 = AADTokenBrokerProviderIndex;
          if ( AADTokenBrokerProviderIndex >= 0 )
          {
            v16 = v22;
            StringRawBuffer = WindowsGetStringRawBuffer(v23, 0);
            AADTokenBrokerProviderIndex = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::AddTokenBrokerAccount(
                                            (Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *)(this - 4),
                                            StringRawBuffer,
                                            v16);
            v4 = AADTokenBrokerProviderIndex;
            if ( AADTokenBrokerProviderIndex >= 0 )
            {
              v25 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 123);
              AADTokenBrokerProviderIndex = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetAADTokenBrokerProviderIndex(
                                              (Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *)(this - 4),
                                              &v25,
                                              this + 123);
              v4 = AADTokenBrokerProviderIndex;
              if ( AADTokenBrokerProviderIndex >= 0 )
              {
                v30 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"TokenBrokerAccount", 0x13u, 0x12u);
                v32 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ItemType", 9u, 8u);
                AADTokenBrokerProviderIndex = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(
                                                (Windows::Internal::ShellHelpers::PropertySetHelper *)v24,
                                                v32);
                v4 = AADTokenBrokerProviderIndex;
                if ( AADTokenBrokerProviderIndex >= 0 )
                {
                  v30 = 0;
                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"Index", 6u, 5u);
                  AADTokenBrokerProviderIndex = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(
                                                  (Windows::Internal::ShellHelpers::PropertySetHelper *)v24,
                                                  v30);
                  v4 = AADTokenBrokerProviderIndex;
                  if ( AADTokenBrokerProviderIndex >= 0 )
                  {
                    AccountsControlTelemetry::AccountsControlBrokerActivity::BubbleHeadAccountAdded(v2);
                    WindowsDeleteString(v23);
                    goto LABEL_34;
                  }
                  v15 = 583;
                }
                else
                {
                  v15 = 582;
                }
              }
              else
              {
                v15 = 581;
              }
            }
            else
            {
              v15 = 577;
            }
          }
          else
          {
            v15 = 575;
          }
        }
        else
        {
          v15 = 573;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)AADTokenBrokerProviderIndex,
          0);
        WindowsDeleteString(v23);
        v23 = 0;
        goto LABEL_10;
      }
    }
    else
    {
      hstringHeader.Reserved.Reserved1 = &v27;
      hstringHeader.Reserved.Reserved2[8] = 1;
      v26 = 0;
      v30 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"Index", 6u, 5u);
      v10 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)v24,
              v30);
      v4 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x231,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v10,
          0);
        hstringHeader.Reserved.Reserved2[8] = 0;
        lambda_ad83d78e7e1263cf6e70f832f8caf15b_::operator()(&hstringHeader);
        goto LABEL_10;
      }
      v25 = 0;
      v23 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 123);
      TokenBrokerProviderIndex = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetTokenBrokerProviderIndex(
                                   (Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *)(this - 4),
                                   v26,
                                   &v25,
                                   this + 123);
      v4 = TokenBrokerProviderIndex;
      if ( TokenBrokerProviderIndex < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x235,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)TokenBrokerProviderIndex,
          0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        hstringHeader.Reserved.Reserved2[8] = 0;
        lambda_ad83d78e7e1263cf6e70f832f8caf15b_::operator()(&hstringHeader);
        goto LABEL_10;
      }
      v30 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"Index", 6u, 5u);
      v12 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)v24,
              v30);
      v4 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x237,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v12,
          0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        hstringHeader.Reserved.Reserved2[8] = 0;
        lambda_ad83d78e7e1263cf6e70f832f8caf15b_::operator()(&hstringHeader);
        goto LABEL_10;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    }
LABEL_34:
    wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(v2);
    WindowsDeleteString(0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v24);
    goto LABEL_35;
  }
  v5 = 530;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
    (const char *)(unsigned int)v3,
    string);
LABEL_36:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v28);
  return v4;
}

```

## disassembly

```asm
0x180013210  mov     [rsp-8+arg_8], rbx
0x180013215  mov     [rsp-8+arg_10], rsi
0x18001321a  push    rbp
0x18001321b  push    rdi
0x18001321c  push    r12
0x18001321e  push    r13
0x180013220  push    r14
0x180013222  lea     rbp, [rsp-37h]
0x180013227  sub     rsp, 0F0h
0x18001322e  mov     rax, cs:__security_cookie
0x180013235  xor     rax, rsp
0x180013238  mov     [rbp+57h+var_30], rax
0x18001323c  mov     r14, rcx
0x18001323f  lea     rsi, [rcx+270h]
0x180013246  lea     rdx, [rbp+57h+var_C0]; this
0x18001324a  mov     rcx, rsi; struct wil::details::IFailureCallback *
0x18001324d  call    ?ContinueOnCurrentThread@?$ActivityBase@VAccountsControlTelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x180013252  nop
0x180013253  xor     r12d, r12d
0x180013256  mov     [rbp+57h+var_C8], r12
0x18001325a  lea     rcx, [r14+3D0h]
0x180013261  lea     rdx, [rbp+57h+var_C8]
0x180013265  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18001326a  mov     ebx, eax
0x18001326c  test    eax, eax
0x18001326e  jns     short loc_180013277
0x180013270  mov     edx, 212h
0x180013275  jmp     short loc_1800132C5
0x180013277  mov     [rsp+110h+var_E8], 1
0x18001327c  mov     rdi, [rbp+57h+var_C8]
0x180013280  mov     rax, [rdi]
0x180013283  mov     rbx, [rax+40h]
0x180013287  mov     [rbp+57h+var_38], r12
0x18001328b  mov     r9d, 8; unsigned int
0x180013291  lea     r8d, [r9+1]; unsigned int
0x180013295  lea     rdx, aItemtype; "ItemType"
0x18001329c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800132a0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800132a5  nop
0x1800132a6  lea     r8, [rsp+110h+var_E8]
0x1800132ab  mov     rdx, [rbp+57h+var_38]
0x1800132af  mov     rcx, rdi
0x1800132b2  mov     rax, rbx
0x1800132b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132ba  mov     ebx, eax
0x1800132bc  test    eax, eax
0x1800132be  jns     short loc_1800132DD
0x1800132c0  mov     edx, 215h; void *
0x1800132c5  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800132cc  mov     r9d, eax; char *
0x1800132cf  mov     rcx, [rbp+5Fh]; this
0x1800132d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800132d8  jmp     loc_180013750
0x1800132dd  cmp     [rsp+110h+var_E8], r12b
0x1800132e2  jnz     short loc_1800132F9
0x1800132e4  mov     rcx, rsi; this
0x1800132e7  call    ?CloseUIWithNoItemSelected@AccountsControlBrokerActivity@AccountsControlTelemetry@@QEAAXXZ; AccountsControlTelemetry::AccountsControlBrokerActivity::CloseUIWithNoItemSelected(void)
0x1800132ec  mov     rcx, rsi
0x1800132ef  call    ?Stop@?$ActivityBase@VAccountsControlTelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800132f4  jmp     loc_18001374D
0x1800132f9  lea     r13, [r14-20h]
0x1800132fd  mov     rdx, [r13+3F0h]; struct Windows::Foundation::Collections::IPropertySet *
0x180013304  lea     rcx, [rsp+110h+var_D8]; this
0x180013309  call    ??0PropertySetHelper@ShellHelpers@Internal@Windows@@QEAA@PEAUIPropertySet@Collections@Foundation@3@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x18001330e  nop
0x18001330f  mov     [rsp+110h+string], r12
0x180013314  xor     ecx, ecx; string
0x180013316  call    cs:__imp_WindowsDeleteString
0x18001331c  mov     [rsp+110h+string], r12; int
0x180013321  mov     [rbp+57h+var_38], r12
0x180013325  mov     r9d, 8; unsigned int
0x18001332b  lea     r8d, [r9+1]; unsigned int
0x18001332f  lea     rdx, aItemtype; "ItemType"
0x180013336  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001333a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001333f  nop
0x180013340  lea     r9, [rsp+110h+string]
0x180013345  mov     rdx, [rbp+57h+var_38]; HSTRING
0x180013349  lea     rcx, [rsp+110h+var_D8]; this
0x18001334e  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180013353  mov     ebx, eax
0x180013355  test    eax, eax
0x180013357  jns     short loc_180013391
0x180013359  mov     rcx, [rbp+5Fh]; this
0x18001335d  mov     r9d, eax; char *
0x180013360  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180013367  mov     edx, 221h; void *
0x18001336c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013371  nop
0x180013372  mov     rcx, [rsp+110h+string]; string
0x180013377  call    cs:__imp_WindowsDeleteString
0x18001337d  mov     [rsp+110h+string], r12
0x180013382  lea     rcx, [rsp+110h+var_D8]
0x180013387  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001338c  jmp     loc_180013750
0x180013391  mov     [rbp+57h+var_38], r12
0x180013395  mov     r9d, 12h; unsigned int
0x18001339b  lea     r8d, [r9+1]; unsigned int
0x18001339f  lea     rdx, aTokenbrokeracc; "TokenBrokerAccount"
0x1800133a6  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800133aa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800133af  mov     rdx, [rbp+57h+var_38]; HSTRING
0x1800133b3  mov     rcx, [rsp+110h+string]; this
0x1800133b8  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800133bd  test    eax, eax
0x1800133bf  jnz     loc_18001351E
0x1800133c5  lea     rax, [rbp+57h+var_C8]
0x1800133c9  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800133cd  mov     byte ptr [rbp+57h+hstringHeader.Reserved+8], 1
0x1800133d1  mov     [rbp+57h+var_CC], r12d
0x1800133d5  mov     [rbp+57h+var_58], r12
0x1800133d9  mov     edi, 5
0x1800133de  mov     r9d, edi; unsigned int
0x1800133e1  lea     r8d, [rdi+1]; unsigned int
0x1800133e5  lea     rdx, aIndex; "Index"
0x1800133ec  lea     rcx, [rbp+57h+var_70]; hstringHeader
0x1800133f0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800133f5  nop
0x1800133f6  lea     r9, [rbp+57h+var_CC]
0x1800133fa  mov     rdx, [rbp+57h+var_58]; HSTRING
0x1800133fe  lea     rcx, [rsp+110h+var_D8]; this
0x180013403  call    ??$GetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAI@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uint *),uint *)
0x180013408  mov     ebx, eax
0x18001340a  test    eax, eax
0x18001340c  jns     short loc_18001343A
0x18001340e  mov     rcx, [rbp+5Fh]; this
0x180013412  mov     r9d, eax; char *
0x180013415  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001341c  mov     edx, 231h; void *
0x180013421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013426  nop
0x180013427  mov     byte ptr [rbp+57h+hstringHeader.Reserved+8], r12b
0x18001342b  lea     rcx, [rbp+57h+hstringHeader]
0x18001342f  call    _lambda_ad83d78e7e1263cf6e70f832f8caf15b___operator__
0x180013434  nop
0x180013435  jmp     loc_180013372
0x18001343a  mov     [rbp+57h+var_D0], r12d
0x18001343e  mov     [rsp+110h+var_E0], r12
0x180013443  lea     rbx, [r14+3D8h]
0x18001344a  mov     rcx, rbx
0x18001344d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013452  mov     r9, rbx; struct Windows::Security::Credentials::IWebAccountProvider **
0x180013455  lea     r8, [rbp+57h+var_D0]; unsigned int *
0x180013459  mov     edx, [rbp+57h+var_CC]; unsigned int
0x18001345c  mov     rcx, r13; this
0x18001345f  call    ?GetTokenBrokerProviderIndex@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJIPEAIPEAPEAUIWebAccountProvider@Credentials@Security@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetTokenBrokerProviderIndex(uint,uint *,Windows::Security::Credentials::IWebAccountProvider * *)
0x180013464  mov     ebx, eax
0x180013466  test    eax, eax
0x180013468  jns     short loc_1800134A1
0x18001346a  mov     rcx, [rbp+5Fh]; this
0x18001346e  mov     r9d, eax; char *
0x180013471  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180013478  mov     edx, 235h; void *
0x18001347d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013482  nop
0x180013483  lea     rcx, [rsp+110h+var_E0]
0x180013488  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001348d  nop
0x18001348e  mov     byte ptr [rbp+57h+hstringHeader.Reserved+8], r12b
0x180013492  lea     rcx, [rbp+57h+hstringHeader]
0x180013496  call    _lambda_ad83d78e7e1263cf6e70f832f8caf15b___operator__
0x18001349b  nop
0x18001349c  jmp     loc_180013372
0x1800134a1  mov     [rbp+57h+var_58], r12
0x1800134a5  mov     r9d, edi; unsigned int
0x1800134a8  mov     r8d, 6; unsigned int
0x1800134ae  lea     rdx, aIndex; "Index"
0x1800134b5  lea     rcx, [rbp+57h+var_70]; hstringHeader
0x1800134b9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800134be  nop
0x1800134bf  mov     r9d, [rbp+57h+var_D0]
0x1800134c3  mov     rdx, [rbp+57h+var_58]; HSTRING
0x1800134c7  lea     rcx, [rsp+110h+var_D8]; this
0x1800134cc  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x1800134d1  mov     ebx, eax
0x1800134d3  test    eax, eax
0x1800134d5  jns     short loc_18001350E
0x1800134d7  mov     rcx, [rbp+5Fh]; this
0x1800134db  mov     r9d, eax; char *
0x1800134de  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800134e5  mov     edx, 237h; void *
0x1800134ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134ef  nop
0x1800134f0  lea     rcx, [rsp+110h+var_E0]
0x1800134f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800134fa  nop
0x1800134fb  mov     byte ptr [rbp+57h+hstringHeader.Reserved+8], r12b
0x1800134ff  lea     rcx, [rbp+57h+hstringHeader]
0x180013503  call    _lambda_ad83d78e7e1263cf6e70f832f8caf15b___operator__
0x180013508  nop
0x180013509  jmp     loc_180013372
0x18001350e  lea     rcx, [rsp+110h+var_E0]
0x180013513  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013518  nop
0x180013519  jmp     loc_18001372A
0x18001351e  mov     [rbp+57h+var_58], r12
0x180013522  mov     r9d, 0Ah; unsigned int
0x180013528  lea     r8d, [r9+1]; unsigned int
0x18001352c  lea     rdx, aBubblehead; "BubbleHead"
0x180013533  lea     rcx, [rbp+57h+var_70]; hstringHeader
0x180013537  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001353c  mov     rdx, [rbp+57h+var_58]; HSTRING
0x180013540  mov     rcx, [rsp+110h+string]; this
0x180013545  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18001354a  test    eax, eax
0x18001354c  jnz     loc_18001372A
0x180013552  mov     [rsp+110h+var_E0], r12
0x180013557  xor     ecx, ecx; string
0x180013559  call    cs:__imp_WindowsDeleteString
0x18001355f  mov     [rsp+110h+var_E0], r12
0x180013564  mov     [rbp+57h+var_58], r12
0x180013568  mov     r9d, 3; unsigned int
0x18001356e  lea     r8d, [r9+1]; unsigned int
0x180013572  lea     rdx, aUpn; "UPN"
0x180013579  lea     rcx, [rbp+57h+var_70]; hstringHeader
0x18001357d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180013582  nop
0x180013583  lea     r9, [rsp+110h+var_E0]
0x180013588  mov     rdx, [rbp+57h+var_58]; HSTRING
0x18001358c  lea     rcx, [rsp+110h+var_D8]; this
0x180013591  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180013596  mov     ebx, eax
0x180013598  test    eax, eax
0x18001359a  jns     short loc_1800135CA
0x18001359c  mov     edx, 23Dh; void *
0x1800135a1  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800135a8  mov     r9d, eax; char *
0x1800135ab  mov     rcx, [rbp+5Fh]; this
0x1800135af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800135b4  nop
0x1800135b5  mov     rcx, [rsp+110h+var_E0]; string
0x1800135ba  call    cs:__imp_WindowsDeleteString
0x1800135c0  mov     [rsp+110h+var_E0], r12
0x1800135c5  jmp     loc_180013372
0x1800135ca  mov     [rsp+110h+var_E7], r12b
0x1800135cf  mov     [rbp+57h+var_58], r12
0x1800135d3  mov     edi, 5
0x1800135d8  mov     r9d, edi; unsigned int
0x1800135db  lea     r8d, [rdi+1]; unsigned int
0x1800135df  lea     rdx, aIsaad; "IsAAD"
0x1800135e6  lea     rcx, [rbp+57h+var_70]; hstringHeader
0x1800135ea  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800135ef  nop
0x1800135f0  lea     r9, [rsp+110h+var_E7]
0x1800135f5  mov     rdx, [rbp+57h+var_58]; HSTRING
0x1800135f9  lea     rcx, [rsp+110h+var_D8]; this
0x1800135fe  call    ??$GetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAE@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uchar *),uchar *)
0x180013603  mov     ebx, eax
0x180013605  test    eax, eax
0x180013607  jns     short loc_180013610
0x180013609  mov     edx, 23Fh
0x18001360e  jmp     short loc_1800135A1
0x180013610  mov     bl, [rsp+110h+var_E7]
0x180013614  xor     edx, edx; length
0x180013616  mov     rcx, [rsp+110h+var_E0]; string
0x18001361b  call    cs:__imp_WindowsGetStringRawBuffer
0x180013621  mov     r8b, bl; unsigned __int8
0x180013624  mov     rdx, rax; unsigned __int16 *
0x180013627  mov     rcx, r13; this
0x18001362a  call    ?AddTokenBrokerAccount@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEBGE@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::AddTokenBrokerAccount(ushort const *,uchar)
0x18001362f  mov     ebx, eax
0x180013631  test    eax, eax
0x180013633  jns     short loc_18001363F
0x180013635  mov     edx, 241h
0x18001363a  jmp     loc_1800135A1
0x18001363f  mov     [rbp+57h+var_D0], r12d
0x180013643  lea     rbx, [r14+3D8h]
0x18001364a  mov     rcx, rbx
0x18001364d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013652  mov     r8, rbx; struct Windows::Security::Credentials::IWebAccountProvider **
0x180013655  lea     rdx, [rbp+57h+var_D0]; unsigned int *
0x180013659  mov     rcx, r13; this
0x18001365c  call    ?GetAADTokenBrokerProviderIndex@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAIPEAPEAUIWebAccountProvider@Credentials@Security@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetAADTokenBrokerProviderIndex(uint *,Windows::Security::Credentials::IWebAccountProvider * *)
0x180013661  mov     ebx, eax
0x180013663  test    eax, eax
0x180013665  jns     short loc_180013671
0x180013667  mov     edx, 245h
0x18001366c  jmp     loc_1800135A1
0x180013671  mov     [rbp+57h+var_58], r12
0x180013675  mov     r9d, 12h; unsigned int
0x18001367b  lea     r8d, [r9+1]; unsigned int
0x18001367f  lea     rdx, aTokenbrokeracc; "TokenBrokerAccount"
0x180013686  lea     rcx, [rbp+57h+var_70]; hstringHeader
0x18001368a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001368f  nop
0x180013690  mov     rbx, [rbp+57h+var_58]
0x180013694  mov     [rbp+57h+var_38], r12
0x180013698  mov     r9d, 8; unsigned int
0x18001369e  lea     r8d, [r9+1]; unsigned int
0x1800136a2  lea     rdx, aItemtype; "ItemType"
0x1800136a9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800136ad  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800136b2  nop
0x1800136b3  mov     r9, rbx
0x1800136b6  mov     rdx, [rbp+57h+var_38]; HSTRING
0x1800136ba  lea     rcx, [rsp+110h+var_D8]; this
0x1800136bf  call    ??$SetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJ0PEAPEAUIInspectable@@@Z0@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(HSTRING__ *,IInspectable * *),HSTRING__ *)
0x1800136c4  mov     ebx, eax
0x1800136c6  test    eax, eax
0x1800136c8  jns     short loc_1800136D4
  ... truncated ...
```
