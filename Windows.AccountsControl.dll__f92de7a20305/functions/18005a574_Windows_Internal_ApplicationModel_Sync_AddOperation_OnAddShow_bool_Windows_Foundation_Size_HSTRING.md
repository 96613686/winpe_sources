# Windows::Internal::ApplicationModel::Sync::AddOperation::OnAddShow(bool *,Windows::Foundation::Size *,HSTRING__ * *)

- ea: `0x18005a574`
- end: `0x18005a827`
- name: `?OnAddShow@AddOperation@Sync@ApplicationModel@Internal@Windows@@AEAAJPEA_NPEAUSize@Foundation@5@PEAPEAUHSTRING__@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(Windows::Internal::ApplicationModel::Sync::AddOperation *__hidden this, bool *, struct Windows::Foundation::Size *, HSTRING *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18005ac40`

## callees

- `0x180004244`
- `0x180006eac`
- `0x180008d78`
- `0x18000e87c`
- `0x180011ffc`
- `0x18001908c`
- `0x18003f160`
- `0x18004ef9c`
- `0x1800569e8`
- `0x18005a574`
- `0x18005aca0`
- `0x18005d624`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a5ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a6e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a75c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a78b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a7af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a5ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a6e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a75c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a78b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a7af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005a733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005a733`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::OnAddShow(
        Windows::Internal::ApplicationModel::Sync::AddOperation *this,
        bool *a2,
        struct Windows::Foundation::Size *a3,
        HSTRING *a4)
{
  int UserDataAccountsProvider; // eax
  int LaunchContractArgs; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  struct IInspectable *v12; // rbx
  HSTRING v13; // rdi
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING, HSTRING *); // rbx
  HRESULT v17; // eax
  __int64 v18; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  __int64 v24; // [rsp+28h] [rbp-50h] BYREF
  struct IInspectable *v25; // [rsp+30h] [rbp-48h] BYREF
  HSTRING v26; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v28; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  *a4 = 0;
  WindowsDeleteString(0);
  v26 = 0;
  UserDataAccountsProvider = GetUserDataAccountsProvider(&v26);
  if ( UserDataAccountsProvider < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)UserDataAccountsProvider,
      (int)string);
  if ( !v26 )
  {
    v20 = Windows::Internal::ApplicationModel::Sync::AddOperation::PopulateAccountsControlData(
            (__int64)this,
            *((_DWORD *)this + 150),
            *((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 76));
    v10 = v20;
    if ( v20 >= 0 )
    {
      v22 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v25, this);
      v20 = RunInBrokerContext__lambda_e9a3d42ca74faf499d98b68a211f8402_(v22);
      v10 = v20;
      if ( v20 >= 0 )
        goto LABEL_19;
      v21 = 218;
    }
    else
    {
      v21 = 207;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v20,
      (int)string);
    goto LABEL_20;
  }
  *((_BYTE *)this + 640) = 1;
  v25 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  LaunchContractArgs = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetLaunchContractArgs(
                         this,
                         *((unsigned int *)this + 150),
                         &v25);
  v10 = LaunchContractArgs;
  if ( LaunchContractArgs >= 0 )
  {
    v12 = v25;
    v13 = v26;
    v28 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.UserDataAccountsProvider",
      0x21u,
      0x20u);
    LaunchContractArgs = ViewOperationBase::EnableContractLaunch(this, v28, v13, v12);
    v10 = LaunchContractArgs;
    if ( LaunchContractArgs < 0 )
    {
      v11 = 190;
      goto LABEL_8;
    }
    *a2 = 1;
    v24 = 0;
    v28 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.ApplicationModel.Sync.AccountsResourceHelper",
      0x3Eu,
      0x3Du);
    v14 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>(
            v28,
            &v24);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
        (const char *)(unsigned int)v14,
        (int)string);
LABEL_16:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
      goto LABEL_17;
    }
    string = 0;
    v15 = v24;
    v16 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v24 + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v28 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AddAccountWindowTitle", 0x16u, 0x15u);
    v17 = v16(v15, v28, &string);
    v10 = v17;
    if ( v17 < 0 )
    {
      v18 = 199;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
        (const char *)(unsigned int)v17,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_16;
    }
    v17 = WindowsDuplicateString(string, a4);
    v10 = v17;
    if ( v17 < 0 )
    {
      v18 = 200;
      goto LABEL_15;
    }
    *(_DWORD *)a3 = 1139015680;
    *((_DWORD *)a3 + 1) = 1139015680;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
LABEL_19:
    v10 = 0;
    goto LABEL_20;
  }
  v11 = 189;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
    (const char *)(unsigned int)LaunchContractArgs,
    (int)string);
LABEL_17:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
LABEL_20:
  WindowsDeleteString(v26);
  return v10;
}

```

## disassembly

```asm
0x18005a574  push    rbp
0x18005a576  push    rbx
0x18005a577  push    rsi
0x18005a578  push    rdi
0x18005a579  push    r12
0x18005a57b  push    r13
0x18005a57d  push    r14
0x18005a57f  push    r15
0x18005a581  mov     rbp, rsp
0x18005a584  sub     rsp, 78h
0x18005a588  mov     rax, cs:__security_cookie
0x18005a58f  xor     rax, rsp
0x18005a592  mov     [rbp+var_18], rax
0x18005a596  mov     r15, r9
0x18005a599  mov     r14, r8
0x18005a59c  mov     r12, rdx
0x18005a59f  mov     rsi, rcx
0x18005a5a2  xor     r13d, r13d
0x18005a5a5  mov     [r9], r13
0x18005a5a8  mov     [rbp+var_40], r13
0x18005a5ac  xor     ecx, ecx; string
0x18005a5ae  call    cs:__imp_WindowsDeleteString
0x18005a5b4  mov     [rbp+var_40], r13
0x18005a5b8  lea     rcx, [rbp+var_40]; HSTRING *
0x18005a5bc  call    ?GetUserDataAccountsProvider@@YAJPEAPEAUHSTRING__@@@Z; GetUserDataAccountsProvider(HSTRING__ * *)
0x18005a5c1  mov     rcx, [rbp+40h]; this
0x18005a5c5  lea     rdi, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005a5cc  test    eax, eax
0x18005a5ce  jns     short loc_18005A5E0
0x18005a5d0  mov     r9d, eax; char *
0x18005a5d3  mov     r8, rdi; unsigned int
0x18005a5d6  mov     edx, 0B7h; void *
0x18005a5db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a5e0  cmp     [rbp+var_40], r13
0x18005a5e4  jz      loc_18005A7D4
0x18005a5ea  mov     byte ptr [rsi+280h], 1
0x18005a5f1  mov     [rbp+var_48], r13
0x18005a5f5  lea     rcx, [rbp+var_48]
0x18005a5f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a5fe  lea     r8, [rbp+var_48]
0x18005a602  mov     edx, [rsi+258h]
0x18005a608  mov     rcx, rsi
0x18005a60b  call    ?s_GetLaunchContractArgs@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUIViewOperation@ApplicationSettings@UI@45@W4UserDataAccountContentKinds@UserDataAccounts@35@PEAPEAUIInspectable@@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetLaunchContractArgs(Windows::Internal::UI::ApplicationSettings::IViewOperation *,Windows::ApplicationModel::UserDataAccounts::UserDataAccountContentKinds,IInspectable * *)
0x18005a610  mov     ebx, eax
0x18005a612  test    eax, eax
0x18005a614  jns     short loc_18005A620
0x18005a616  mov     r8, rdi
0x18005a619  mov     edx, 0BDh
0x18005a61e  jmp     short loc_18005A66A
0x18005a620  mov     rbx, [rbp+var_48]
0x18005a624  mov     rdi, [rbp+var_40]
0x18005a628  mov     [rbp+var_20], r13
0x18005a62c  mov     r9d, 20h ; ' '; unsigned int
0x18005a632  lea     r8d, [r9+1]; unsigned int
0x18005a636  lea     rdx, aWindowsUserdat; "Windows.UserDataAccountsProvider"
0x18005a63d  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18005a641  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005a646  mov     r9, rbx; struct IInspectable *
0x18005a649  mov     r8, rdi; HSTRING
0x18005a64c  mov     rdx, [rbp+var_20]; HSTRING
0x18005a650  mov     rcx, rsi; this
0x18005a653  call    ?EnableContractLaunch@ViewOperationBase@@IEAAJPEAUHSTRING__@@0PEAUIInspectable@@@Z; ViewOperationBase::EnableContractLaunch(HSTRING__ *,HSTRING__ *,IInspectable *)
0x18005a658  mov     ebx, eax
0x18005a65a  test    eax, eax
0x18005a65c  jns     short loc_18005A67B
0x18005a65e  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005a665  mov     edx, 0BEh; void *
0x18005a66a  mov     r9d, eax; char *
0x18005a66d  mov     rcx, [rbp+40h]; this
0x18005a671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a676  jmp     loc_18005A770
0x18005a67b  mov     byte ptr [r12], 1
0x18005a680  mov     [rbp+var_50], r13
0x18005a684  mov     [rbp+var_20], r13
0x18005a688  mov     r9d, 3Dh ; '='; unsigned int
0x18005a68e  lea     r8d, [r9+1]; unsigned int
0x18005a692  lea     rdx, ?RuntimeClass_Windows_Internal_ApplicationModel_Sync_AccountsResourceHelper@@3QBGB; "Windows.Internal.ApplicationModel.Sync."...
0x18005a699  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18005a69d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005a6a2  lea     rdx, [rbp+var_50]
0x18005a6a6  mov     rcx, [rbp+var_20]
0x18005a6aa  call    ??$GetActivationFactory@V?$ComPtr@UIAccountsResourceHelperStatics@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAccountsResourceHelperStatics@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>)
0x18005a6af  mov     ebx, eax
0x18005a6b1  test    eax, eax
0x18005a6b3  jns     short loc_18005A6D2
0x18005a6b5  mov     rcx, [rbp+40h]; this
0x18005a6b9  mov     r9d, eax; char *
0x18005a6bc  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005a6c3  mov     edx, 0C4h; void *
0x18005a6c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a6cd  jmp     loc_18005A766
0x18005a6d2  mov     [rbp+string], r13
0x18005a6d6  mov     rdi, [rbp+var_50]
0x18005a6da  mov     rax, [rdi]
0x18005a6dd  mov     rbx, [rax+50h]
0x18005a6e1  xor     ecx, ecx; string
0x18005a6e3  call    cs:__imp_WindowsDeleteString
0x18005a6e9  mov     [rbp+string], r13
0x18005a6ed  mov     [rbp+var_20], r13
0x18005a6f1  mov     r9d, 15h; unsigned int
0x18005a6f7  lea     r8d, [r9+1]; unsigned int
0x18005a6fb  lea     rdx, aAddaccountwind; "AddAccountWindowTitle"
0x18005a702  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18005a706  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005a70b  nop
0x18005a70c  lea     r8, [rbp+string]
0x18005a710  mov     rdx, [rbp+var_20]
0x18005a714  mov     rcx, rdi
0x18005a717  mov     rax, rbx
0x18005a71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a71f  mov     ebx, eax
0x18005a721  test    eax, eax
0x18005a723  jns     short loc_18005A72C
0x18005a725  mov     edx, 0C7h
0x18005a72a  jmp     short loc_18005A744
0x18005a72c  mov     rdx, r15; newString
0x18005a72f  mov     rcx, [rbp+string]; string
0x18005a733  call    cs:__imp_WindowsDuplicateString
0x18005a739  mov     ebx, eax
0x18005a73b  test    eax, eax
0x18005a73d  jns     short loc_18005A77B
0x18005a73f  mov     edx, 0C8h; void *
0x18005a744  mov     r9d, eax; char *
0x18005a747  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005a74e  mov     rcx, [rbp+40h]; this
0x18005a752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a757  nop
0x18005a758  mov     rcx, [rbp+string]; string
0x18005a75c  call    cs:__imp_WindowsDeleteString
0x18005a762  mov     [rbp+string], r13
0x18005a766  lea     rcx, [rbp+var_50]
0x18005a76a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a76f  nop
0x18005a770  lea     rcx, [rbp+var_48]
0x18005a774  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a779  jmp     short loc_18005A7AB
0x18005a77b  mov     eax, 43E40000h
0x18005a780  mov     [r14], eax
0x18005a783  mov     [r14+4], eax
0x18005a787  mov     rcx, [rbp+string]; string
0x18005a78b  call    cs:__imp_WindowsDeleteString
0x18005a791  mov     [rbp+string], r13
0x18005a795  lea     rcx, [rbp+var_50]
0x18005a799  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a79e  nop
0x18005a79f  lea     rcx, [rbp+var_48]
0x18005a7a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a7a8  mov     ebx, r13d
0x18005a7ab  mov     rcx, [rbp+var_40]; string
0x18005a7af  call    cs:__imp_WindowsDeleteString
0x18005a7b5  mov     eax, ebx
0x18005a7b7  mov     rcx, [rbp+var_18]
0x18005a7bb  xor     rcx, rsp; StackCookie
0x18005a7be  call    __security_check_cookie
0x18005a7c3  add     rsp, 78h
0x18005a7c7  pop     r15
0x18005a7c9  pop     r14
0x18005a7cb  pop     r13
0x18005a7cd  pop     r12
0x18005a7cf  pop     rdi
0x18005a7d0  pop     rsi
0x18005a7d1  pop     rbx
0x18005a7d2  pop     rbp
0x18005a7d3  retn
0x18005a7d4  mov     r8, [rsi+260h]
0x18005a7db  mov     edx, [rsi+258h]
0x18005a7e1  mov     rcx, rsi
0x18005a7e4  call    ?PopulateAccountsControlData@AddOperation@Sync@ApplicationModel@Internal@Windows@@AEAAJW4UserDataAccountContentKinds@UserDataAccounts@35@PEAUIViewOperation@ApplicationSettings@UI@45@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::PopulateAccountsControlData(Windows::ApplicationModel::UserDataAccounts::UserDataAccountContentKinds,Windows::Internal::UI::ApplicationSettings::IViewOperation *)
0x18005a7e9  mov     ebx, eax
0x18005a7eb  test    eax, eax
0x18005a7ed  jns     short loc_18005A805
0x18005a7ef  mov     edx, 0CFh; void *
0x18005a7f4  mov     r8, rdi; unsigned int
0x18005a7f7  mov     r9d, eax; char *
0x18005a7fa  mov     rcx, [rbp+40h]; this
0x18005a7fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a803  jmp     short loc_18005A7AB
0x18005a805  mov     rdx, rsi
0x18005a808  lea     rcx, [rbp+var_48]
0x18005a80c  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18005a811  mov     rcx, rax
0x18005a814  call    RunInBrokerContext__lambda_e9a3d42ca74faf499d98b68a211f8402___; RunInBrokerContext__lambda_e9a3d42ca74faf499d98b68a211f8402_
0x18005a819  mov     ebx, eax
0x18005a81b  test    eax, eax
0x18005a81d  jns     short loc_18005A7A8
0x18005a81f  mov     edx, 0DAh
0x18005a824  jmp     short loc_18005A7F4
```
