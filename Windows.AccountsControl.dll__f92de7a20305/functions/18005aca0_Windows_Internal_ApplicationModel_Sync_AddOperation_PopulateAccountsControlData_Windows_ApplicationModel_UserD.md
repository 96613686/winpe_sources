# Windows::Internal::ApplicationModel::Sync::AddOperation::PopulateAccountsControlData(Windows::ApplicationModel::UserDataAccounts::UserDataAccountContentKinds,Windows::Internal::UI::ApplicationSettings::IViewOperation *)

- ea: `0x18005aca0`
- end: `0x18005b2f8`
- name: `?PopulateAccountsControlData@AddOperation@Sync@ApplicationModel@Internal@Windows@@AEAAJW4UserDataAccountContentKinds@UserDataAccounts@35@PEAUIViewOperation@ApplicationSettings@UI@45@@Z`
- size: `1624`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005a574`

## callees

- `0x180006eac`
- `0x180008d78`
- `0x18000e87c`
- `0x180011ffc`
- `0x18001908c`
- `0x180056744`
- `0x18005677c`
- `0x18005aca0`
- `0x18005c090`
- `0x18005c4b0`
- `0x18005c5f8`
- `0x18005c930`
- `0x18005ccfc`
- `0x18005cfcc`
- `0x18005f214`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b111`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b27a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005af5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b111`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b27a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005b09a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005b145`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005b226`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005b2ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005b09a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005b145`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005b226`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005b2ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::PopulateAccountsControlData(
        __int64 a1,
        unsigned int a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64 *))
{
  int AccountContentTypesForUdaContentKinds; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, HSTRING *); // rbx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rbx
  int v31; // eax
  unsigned int v32; // edi
  __int64 v33; // rcx
  int i; // edi
  int v35; // eax
  unsigned int v36; // r14d
  __int64 v37; // rcx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64 *); // rbx
  int v40; // eax
  int v41; // eax
  __int64 v42; // rcx
  __int64 v44; // rcx
  char v45[16]; // [rsp+20h] [rbp-59h] BYREF
  __int64 v46; // [rsp+30h] [rbp-49h]
  __int64 v47; // [rsp+38h] [rbp-41h] BYREF
  HSTRING string; // [rsp+40h] [rbp-39h] BYREF
  __int64 v49; // [rsp+48h] [rbp-31h] BYREF
  __int64 v50; // [rsp+50h] [rbp-29h] BYREF
  int v51; // [rsp+58h] [rbp-21h] BYREF
  __int64 v52; // [rsp+60h] [rbp-19h] BYREF
  __int64 v53; // [rsp+68h] [rbp-11h] BYREF
  __int64 v54; // [rsp+70h] [rbp-9h] BYREF
  __int64 v55; // [rsp+78h] [rbp-1h] BYREF
  char *v56; // [rsp+80h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v58; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v53 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  AccountContentTypesForUdaContentKinds = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountContentTypesForUdaContentKinds(
                                            a2,
                                            &v53);
  v6 = AccountContentTypesForUdaContentKinds;
  if ( AccountContentTypesForUdaContentKinds < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)AccountContentTypesForUdaContentKinds,
      *(int *)v45);
LABEL_63:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    return v6;
  }
  v49 = 0;
  v58 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.ApplicationModel.Sync.AccountsResourceHelper",
    0x3Eu,
    0x3Du);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>(
         v58,
         &v49);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = 309;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v7,
      *(int *)v45);
LABEL_62:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    goto LABEL_63;
  }
  v55 = 0;
  v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*a3)[7])(a3, &v55);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = 312;
    goto LABEL_5;
  }
  v51 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v49 + 72LL))(v49, (unsigned int)v55, &v51);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v9,
      *(int *)v45);
  *(_OWORD *)v45 = 0;
  v46 = 0;
  v10 = Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddWellKnownAccounts(v53, (unsigned int)v51, v45);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v10,
      *(int *)v45);
  v11 = Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddMsaProvider(v51, (__int64)v45);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v11,
      *(int *)v45);
  v12 = Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddAdvancedAccount(v51, (char)v45);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v12,
      *(int *)v45);
  v13 = Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddKnownAccountsFromOemFile(v51, (char)v45);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v13,
      *(int *)v45);
  v50 = 0;
  v14 = **a3;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v15 = v14(a3, &GUID_c88d8b7a_283f_4129_9c88_df59be5930d0, &v50);
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v15,
      *(int *)v45);
    goto LABEL_60;
  }
  v47 = 0;
  v16 = v50;
  v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  v18 = v17(v16, &v47);
  v6 = v18;
  if ( v18 < 0 )
  {
    v19 = 330;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v18,
      *(int *)v45);
LABEL_59:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
LABEL_60:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    if ( *(_QWORD *)v45 )
    {
      std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData>::_Destroy(
        v44,
        *(_QWORD *)v45,
        *(_QWORD *)&v45[8]);
      operator delete(*(void **)v45);
      *(_OWORD *)v45 = 0;
      v46 = 0;
    }
    goto LABEL_62;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 104LL))(v47, 0);
  v6 = v18;
  if ( v18 < 0 )
  {
    v19 = 332;
    goto LABEL_22;
  }
  LOBYTE(v20) = 1;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 152LL))(v47, v20);
  v6 = v18;
  if ( v18 < 0 )
  {
    v19 = 333;
    goto LABEL_22;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 136LL))(v47, (unsigned int)(32 * v51));
  v6 = v18;
  if ( v18 < 0 )
  {
    v19 = 334;
    goto LABEL_22;
  }
  string = 0;
  v21 = v49;
  v22 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v49 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v58 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AddAccountWindowTitle", 0x16u, 0x15u);
  v23 = v22(v21, v58, &string);
  v6 = v23;
  if ( v23 < 0 )
  {
    v24 = 336;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v23,
      *(int *)v45);
LABEL_58:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_59;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v47 + 168LL))(v47, string);
  v6 = v23;
  if ( v23 < 0 )
  {
    v24 = 337;
    goto LABEL_31;
  }
  v52 = 0;
  v25 = v47;
  v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  v27 = v26(v25, &v52);
  v6 = v27;
  if ( v27 < 0 )
  {
    v28 = (unsigned int)v27;
    v29 = 339;
    goto LABEL_56;
  }
  v30 = (__int64)(*(_QWORD *)&v45[8] - *(_QWORD *)v45) >> 4;
  if ( (int)v30 <= 0 )
  {
    v6 = -2147467260;
    v28 = 2147500036LL;
    v29 = 343;
LABEL_56:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)v28,
      *(int *)v45);
LABEL_57:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    goto LABEL_58;
  }
  v56 = v45;
  v31 = wil::ResultFromException__lambda_77e9f9c38579647db6cfd03e75b31dbd___(&v56);
  v32 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v31,
      *(int *)v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    if ( *(_QWORD *)v45 )
    {
      std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData>::_Destroy(
        v33,
        *(_QWORD *)v45,
        *(_QWORD *)&v45[8]);
      operator delete(*(void **)v45);
      *(_OWORD *)v45 = 0;
      v46 = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v6 = v32;
    goto LABEL_63;
  }
  for ( i = 0; i < (int)v30; ++i )
  {
    hstringHeader.Reserved.Reserved1 = v45;
    *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = i;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v52;
    v35 = wil::ResultFromException__lambda_cc3783646a81f19caa5139e86dbce08e___(&hstringHeader);
    v36 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
        (const char *)(unsigned int)v35,
        *(int *)v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      if ( *(_QWORD *)v45 )
      {
        std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData>::_Destroy(
          v37,
          *(_QWORD *)v45,
          *(_QWORD *)&v45[8]);
        operator delete(*(void **)v45);
        *(_OWORD *)v45 = 0;
        v46 = 0;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      v6 = v36;
      goto LABEL_63;
    }
  }
  v54 = 0;
  v38 = v47;
  v39 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  v40 = v39(v38, &v54);
  v6 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v40,
      *(int *)v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    goto LABEL_57;
  }
  v41 = Windows::Internal::ApplicationModel::Sync::AddOperation::s_PopulateKnownWebAccounts(v54);
  if ( v41 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v41,
      *(int *)v45);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  if ( *(_QWORD *)v45 )
  {
    std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData>::_Destroy(
      v42,
      *(_QWORD *)v45,
      *(_QWORD *)&v45[8]);
    operator delete(*(void **)v45);
    *(_OWORD *)v45 = 0;
    v46 = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  return 0;
}

```

## disassembly

```asm
0x18005aca0  mov     [rsp-8+arg_0], rbx
0x18005aca5  push    rbp
0x18005aca6  push    rsi
0x18005aca7  push    rdi
0x18005aca8  push    r14
0x18005acaa  push    r15
0x18005acac  lea     rbp, [rsp-37h]
0x18005acb1  sub     rsp, 0B0h
0x18005acb8  mov     rax, cs:__security_cookie
0x18005acbf  xor     rax, rsp
0x18005acc2  mov     [rbp+57h+var_28], rax
0x18005acc6  mov     rdi, r8
0x18005acc9  mov     ebx, edx
0x18005accb  xor     r15d, r15d
0x18005acce  mov     [rbp+57h+var_68], r15
0x18005acd2  lea     rcx, [rbp+57h+var_68]
0x18005acd6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005acdb  lea     rdx, [rbp+57h+var_68]
0x18005acdf  mov     ecx, ebx
0x18005ace1  call    ?s_GetAccountContentTypesForUdaContentKinds@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJW4UserDataAccountContentKinds@UserDataAccounts@35@PEAPEAU?$IIterable@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@Collections@Foundation@5@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountContentTypesForUdaContentKinds(Windows::ApplicationModel::UserDataAccounts::UserDataAccountContentKinds,Windows::Foundation::Collections::IIterable<PhoneInternal::Experiences::Sync::AccountSyncContentType> * *)
0x18005ace6  mov     ebx, eax
0x18005ace8  test    eax, eax
0x18005acea  jns     short loc_18005AD09
0x18005acec  mov     rcx, [rbp+5Fh]; this
0x18005acf0  mov     r9d, eax; char *
0x18005acf3  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005acfa  mov     edx, 130h; void *
0x18005acff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ad04  jmp     loc_18005B2CA
0x18005ad09  mov     [rbp+57h+var_88], r15
0x18005ad0d  mov     [rbp+57h+var_30], r15
0x18005ad11  mov     r9d, 3Dh ; '='; unsigned int
0x18005ad17  lea     r8d, [r9+1]; unsigned int
0x18005ad1b  lea     rdx, ?RuntimeClass_Windows_Internal_ApplicationModel_Sync_AccountsResourceHelper@@3QBGB; "Windows.Internal.ApplicationModel.Sync."...
0x18005ad22  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ad26  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005ad2b  lea     rdx, [rbp+57h+var_88]
0x18005ad2f  mov     rcx, [rbp+57h+var_30]
0x18005ad33  call    ??$GetActivationFactory@V?$ComPtr@UIAccountsResourceHelperStatics@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAccountsResourceHelperStatics@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>)
0x18005ad38  mov     ebx, eax
0x18005ad3a  test    eax, eax
0x18005ad3c  jns     short loc_18005AD5B
0x18005ad3e  mov     edx, 135h; void *
0x18005ad43  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005ad4a  mov     r9d, eax; char *
0x18005ad4d  mov     rcx, [rbp+5Fh]; this
0x18005ad51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ad56  jmp     loc_18005B2C0
0x18005ad5b  mov     [rbp+57h+var_58], r15
0x18005ad5f  mov     rax, [rdi]
0x18005ad62  lea     rdx, [rbp+57h+var_58]
0x18005ad66  mov     rcx, rdi
0x18005ad69  mov     rax, [rax+38h]
0x18005ad6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad72  mov     ebx, eax
0x18005ad74  test    eax, eax
0x18005ad76  jns     short loc_18005AD7F
0x18005ad78  mov     edx, 138h
0x18005ad7d  jmp     short loc_18005AD43
0x18005ad7f  mov     [rbp+57h+var_78], r15d
0x18005ad83  mov     rcx, [rbp+57h+var_88]
0x18005ad87  mov     rax, [rcx]
0x18005ad8a  lea     r8, [rbp+57h+var_78]
0x18005ad8e  mov     edx, dword ptr [rbp+57h+var_58]
0x18005ad91  mov     rax, [rax+48h]
0x18005ad95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad9a  mov     rcx, [rbp+5Fh]; this
0x18005ad9e  lea     rsi, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005ada5  test    eax, eax
0x18005ada7  jns     short loc_18005ADB9
0x18005ada9  mov     r9d, eax; char *
0x18005adac  mov     r8, rsi; unsigned int
0x18005adaf  mov     edx, 13Dh; void *
0x18005adb4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005adb9  xorps   xmm0, xmm0
0x18005adbc  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x18005adc1  mov     [rbp+57h+var_A0], r15
0x18005adc5  lea     r8, [rbp+57h+var_B0]
0x18005adc9  mov     edx, [rbp+57h+var_78]
0x18005adcc  mov     rcx, [rbp+57h+var_68]
0x18005add0  call    ?s_AddWellKnownAccounts@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAU?$IIterable@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@Collections@Foundation@5@HPEAV?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddWellKnownAccounts(Windows::Foundation::Collections::IIterable<PhoneInternal::Experiences::Sync::AccountSyncContentType> *,int,std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData> *)
0x18005add5  mov     rcx, [rbp+5Fh]; this
0x18005add9  test    eax, eax
0x18005addb  jns     short loc_18005ADED
0x18005addd  mov     r9d, eax; char *
0x18005ade0  mov     r8, rsi; unsigned int
0x18005ade3  mov     edx, 140h; void *
0x18005ade8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005aded  lea     rdx, [rbp+57h+var_B0]
0x18005adf1  mov     ecx, [rbp+57h+var_78]; int
0x18005adf4  call    ?s_AddMsaProvider@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJHPEAV?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddMsaProvider(int,std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData> *)
0x18005adf9  mov     rcx, [rbp+5Fh]; this
0x18005adfd  test    eax, eax
0x18005adff  jns     short loc_18005AE11
0x18005ae01  mov     r9d, eax; char *
0x18005ae04  mov     r8, rsi; unsigned int
0x18005ae07  mov     edx, 141h; void *
0x18005ae0c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ae11  lea     rdx, [rbp+57h+var_B0]; char
0x18005ae15  mov     ecx, [rbp+57h+var_78]; int
0x18005ae18  call    ?s_AddAdvancedAccount@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJHPEAV?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddAdvancedAccount(int,std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData> *)
0x18005ae1d  mov     rcx, [rbp+5Fh]; this
0x18005ae21  test    eax, eax
0x18005ae23  jns     short loc_18005AE35
0x18005ae25  mov     r9d, eax; char *
0x18005ae28  mov     r8, rsi; unsigned int
0x18005ae2b  mov     edx, 143h; void *
0x18005ae30  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ae35  lea     rdx, [rbp+57h+var_B0]; char
0x18005ae39  mov     ecx, [rbp+57h+var_78]; int
0x18005ae3c  call    ?s_AddKnownAccountsFromOemFile@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJHPEAV?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddKnownAccountsFromOemFile(int,std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData> *)
0x18005ae41  mov     rcx, [rbp+5Fh]; this
0x18005ae45  test    eax, eax
0x18005ae47  jns     short loc_18005AE59
0x18005ae49  mov     r9d, eax; char *
0x18005ae4c  mov     r8, rsi; unsigned int
0x18005ae4f  mov     edx, 144h; void *
0x18005ae54  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ae59  mov     [rbp+57h+var_80], r15
0x18005ae5d  mov     rax, [rdi]
0x18005ae60  mov     rbx, [rax]
0x18005ae63  lea     rcx, [rbp+57h+var_80]
0x18005ae67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ae6c  lea     r8, [rbp+57h+var_80]
0x18005ae70  lea     rdx, _GUID_c88d8b7a_283f_4129_9c88_df59be5930d0
0x18005ae77  mov     rcx, rdi
0x18005ae7a  mov     rax, rbx
0x18005ae7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae82  mov     ebx, eax
0x18005ae84  test    eax, eax
0x18005ae86  jns     short loc_18005AEA1
0x18005ae88  mov     rcx, [rbp+5Fh]; this
0x18005ae8c  mov     r9d, eax; char *
0x18005ae8f  mov     r8, rsi; unsigned int
0x18005ae92  mov     edx, 147h; void *
0x18005ae97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ae9c  jmp     loc_18005B28E
0x18005aea1  mov     [rbp+57h+var_98], r15
0x18005aea5  mov     rdi, [rbp+57h+var_80]
0x18005aea9  mov     rax, [rdi]
0x18005aeac  mov     rbx, [rax+30h]
0x18005aeb0  lea     rcx, [rbp+57h+var_98]
0x18005aeb4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005aeb9  lea     rdx, [rbp+57h+var_98]
0x18005aebd  mov     rcx, rdi
0x18005aec0  mov     rax, rbx
0x18005aec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aec8  mov     ebx, eax
0x18005aeca  test    eax, eax
0x18005aecc  jns     short loc_18005AEE7
0x18005aece  mov     edx, 14Ah; void *
0x18005aed3  mov     r8, rsi; unsigned int
0x18005aed6  mov     r9d, eax; char *
0x18005aed9  mov     rcx, [rbp+5Fh]; this
0x18005aedd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aee2  jmp     loc_18005B284
0x18005aee7  mov     rcx, [rbp+57h+var_98]
0x18005aeeb  mov     rax, [rcx]
0x18005aeee  xor     edx, edx
0x18005aef0  mov     rax, [rax+68h]
0x18005aef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aef9  mov     ebx, eax
0x18005aefb  test    eax, eax
0x18005aefd  jns     short loc_18005AF06
0x18005aeff  mov     edx, 14Ch
0x18005af04  jmp     short loc_18005AED3
0x18005af06  mov     rcx, [rbp+57h+var_98]
0x18005af0a  mov     rax, [rcx]
0x18005af0d  mov     dl, 1
0x18005af0f  mov     rax, [rax+98h]
0x18005af16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af1b  mov     ebx, eax
0x18005af1d  test    eax, eax
0x18005af1f  jns     short loc_18005AF28
0x18005af21  mov     edx, 14Dh
0x18005af26  jmp     short loc_18005AED3
0x18005af28  mov     rcx, [rbp+57h+var_98]
0x18005af2c  mov     rax, [rcx]
0x18005af2f  mov     edx, [rbp+57h+var_78]
0x18005af32  shl     edx, 5
0x18005af35  mov     rax, [rax+88h]
0x18005af3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af41  mov     ebx, eax
0x18005af43  test    eax, eax
0x18005af45  jns     short loc_18005AF4E
0x18005af47  mov     edx, 14Eh
0x18005af4c  jmp     short loc_18005AED3
0x18005af4e  mov     [rbp+57h+string], r15
0x18005af52  mov     rdi, [rbp+57h+var_88]
0x18005af56  mov     rax, [rdi]
0x18005af59  mov     rbx, [rax+50h]
0x18005af5d  xor     ecx, ecx; string
0x18005af5f  call    cs:__imp_WindowsDeleteString
0x18005af65  mov     [rbp+57h+string], r15
0x18005af69  mov     [rbp+57h+var_30], r15
0x18005af6d  mov     r9d, 15h; unsigned int
0x18005af73  lea     r8d, [r9+1]; unsigned int
0x18005af77  lea     rdx, aAddaccountwind; "AddAccountWindowTitle"
0x18005af7e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005af82  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005af87  nop
0x18005af88  lea     r8, [rbp+57h+string]
0x18005af8c  mov     rdx, [rbp+57h+var_30]
0x18005af90  mov     rcx, rdi
0x18005af93  mov     rax, rbx
0x18005af96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af9b  mov     ebx, eax
0x18005af9d  test    eax, eax
0x18005af9f  jns     short loc_18005AFBA
0x18005afa1  mov     edx, 150h; void *
0x18005afa6  mov     r8, rsi; unsigned int
0x18005afa9  mov     r9d, eax; char *
0x18005afac  mov     rcx, [rbp+5Fh]; this
0x18005afb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005afb5  jmp     loc_18005B276
0x18005afba  mov     rcx, [rbp+57h+var_98]
0x18005afbe  mov     rax, [rcx]
0x18005afc1  mov     rdx, [rbp+57h+string]
0x18005afc5  mov     rax, [rax+0A8h]
0x18005afcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005afd1  mov     ebx, eax
0x18005afd3  test    eax, eax
0x18005afd5  jns     short loc_18005AFDE
0x18005afd7  mov     edx, 151h
0x18005afdc  jmp     short loc_18005AFA6
0x18005afde  mov     [rbp+57h+var_70], r15
0x18005afe2  mov     rdi, [rbp+57h+var_98]
0x18005afe6  mov     rax, [rdi]
0x18005afe9  mov     rbx, [rax+30h]
0x18005afed  lea     rcx, [rbp+57h+var_70]
0x18005aff1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005aff6  lea     rdx, [rbp+57h+var_70]
0x18005affa  mov     rcx, rdi
0x18005affd  mov     rax, rbx
0x18005b000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b005  mov     ebx, eax
0x18005b007  test    eax, eax
0x18005b009  jns     short loc_18005B018
0x18005b00b  mov     r9d, eax
0x18005b00e  mov     edx, 153h
0x18005b013  jmp     loc_18005B25F
0x18005b018  mov     rbx, qword ptr [rbp+57h+var_B0+8]
0x18005b01c  sub     rbx, qword ptr [rbp+57h+var_B0]
0x18005b020  sar     rbx, 4
0x18005b024  test    ebx, ebx
0x18005b026  jle     loc_18005B252
0x18005b02c  lea     rax, [rbp+57h+var_B0]
0x18005b030  mov     [rbp+57h+var_50], rax
0x18005b034  lea     rcx, [rbp+57h+var_50]
0x18005b038  call    wil__ResultFromException__lambda_77e9f9c38579647db6cfd03e75b31dbd___
0x18005b03d  mov     edi, eax
0x18005b03f  test    eax, eax
0x18005b041  jns     short loc_18005B0BC
0x18005b043  mov     rcx, [rbp+5Fh]; this
0x18005b047  mov     r9d, eax; char *
0x18005b04a  mov     r8, rsi; unsigned int
0x18005b04d  mov     edx, 15Dh; void *
0x18005b052  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b057  nop
0x18005b058  lea     rcx, [rbp+57h+var_70]
0x18005b05c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b061  nop
0x18005b062  mov     rcx, [rbp+57h+string]; string
0x18005b066  call    cs:__imp_WindowsDeleteString
0x18005b06c  mov     [rbp+57h+string], r15
0x18005b070  lea     rcx, [rbp+57h+var_98]
0x18005b074  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b079  nop
0x18005b07a  lea     rcx, [rbp+57h+var_80]
0x18005b07e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b083  nop
0x18005b084  mov     rdx, qword ptr [rbp+57h+var_B0]
0x18005b088  test    rdx, rdx
0x18005b08b  jz      short loc_18005B0AC
0x18005b08d  mov     r8, qword ptr [rbp+57h+var_B0+8]
0x18005b091  call    ?_Destroy@?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@IEAAXPEAUProviderData@Sync@ApplicationModel@Internal@Windows@@0@Z; std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData>::_Destroy(Windows::Internal::ApplicationModel::Sync::ProviderData *,Windows::Internal::ApplicationModel::Sync::ProviderData *)
0x18005b096  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18005b09a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005b0a0  xorps   xmm0, xmm0
0x18005b0a3  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x18005b0a8  mov     [rbp+57h+var_A0], r15
0x18005b0ac  lea     rcx, [rbp+57h+var_88]
0x18005b0b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005b0b5  mov     ebx, edi
0x18005b0b7  jmp     loc_18005B2CA
0x18005b0bc  mov     edi, r15d
0x18005b0bf  cmp     edi, ebx
0x18005b0c1  jge     loc_18005B168
0x18005b0c7  lea     rax, [rbp+57h+var_B0]
0x18005b0cb  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18005b0cf  mov     dword ptr [rbp+57h+hstringHeader.Reserved+8], edi
0x18005b0d2  lea     rax, [rbp+57h+var_70]
0x18005b0d6  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x18005b0da  lea     rcx, [rbp+57h+hstringHeader]
0x18005b0de  call    wil__ResultFromException__lambda_cc3783646a81f19caa5139e86dbce08e___
0x18005b0e3  mov     r14d, eax
0x18005b0e6  test    eax, eax
0x18005b0e8  js      short loc_18005B0EE
0x18005b0ea  inc     edi
0x18005b0ec  jmp     short loc_18005B0BF
  ... truncated ...
```
