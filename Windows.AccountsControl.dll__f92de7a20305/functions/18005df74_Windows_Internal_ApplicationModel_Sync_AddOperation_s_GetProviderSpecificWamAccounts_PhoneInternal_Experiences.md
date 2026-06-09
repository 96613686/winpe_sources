# Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetProviderSpecificWamAccounts(PhoneInternal::Experiences::Sync::PartnershipType,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Foundation::Collections::IVector<Windows::Security::Credentials::WebAccount *> *)

- ea: `0x18005df74`
- end: `0x18005e3cb`
- name: `?s_GetProviderSpecificWamAccounts@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJW4PartnershipType@2Experiences@PhoneInternal@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@PEAU?$IVector@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@@Z`
- size: `1111`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005f214`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x180011ffc`
- `0x180037a04`
- `0x18004a7c8`
- `0x18005df74`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e06e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e0b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e15c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e2a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e2ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e352`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e377`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e06e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e0b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e15c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e2a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e2ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e352`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e377`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e1d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e1e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e1d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e1e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e201`
- `msvcrt!_wcsicmp` at `0x18005e210`
- `msvcrt!_wcsicmp` at `0x18005e220`
- `msvcrt!_wcsicmp` at `0x18005e210`
- `msvcrt!_wcsicmp` at `0x18005e220`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetProviderSpecificWamAccounts(
        unsigned int a1,
        __int64 a2,
        __int64 a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  unsigned int i; // esi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  int v27; // eax
  const wchar_t *StringRawBuffer; // rdi
  const wchar_t *v29; // rbx
  const wchar_t *v30; // r12
  const wchar_t *v31; // r13
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  HSTRING v34; // [rsp+28h] [rbp-51h] BYREF
  __int64 v35; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v36; // [rsp+38h] [rbp-41h] BYREF
  __int64 v37; // [rsp+40h] [rbp-39h] BYREF
  __int64 v38; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v39; // [rsp+50h] [rbp-29h] BYREF
  HSTRING v40; // [rsp+58h] [rbp-21h] BYREF
  __int64 v41; // [rsp+60h] [rbp-19h] BYREF
  __int64 v42; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v44; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v39 = 0;
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v39);
  if ( v39 )
  {
    v42 = 0;
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"PhoneInternal.Experiences.Sync.AccountsManager",
      0x2Fu,
      0x2Eu);
    v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<PhoneInternal::Experiences::Sync::IAccountsManagerStatics>>(
           v44,
           &v42);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45A,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
        (const char *)(unsigned int)v6,
        (int)string);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      return v7;
    }
    v35 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 112LL))(v42, a1, &v35);
    v7 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45D,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
        (const char *)(unsigned int)v8,
        (int)string);
LABEL_32:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      goto LABEL_33;
    }
    v34 = 0;
    string = 0;
    v9 = v35;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v35 + 56LL);
    WindowsDeleteString(0);
    v34 = 0;
    v11 = v10(v9, &v34);
    v7 = v11;
    if ( v11 < 0 )
    {
      v12 = 1122;
      goto LABEL_8;
    }
    v13 = v35;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v35 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    v11 = v14(v13, &string);
    v7 = v11;
    if ( v11 < 0 )
    {
      v12 = 1123;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
        (const char *)(unsigned int)v11,
        (int)string);
LABEL_31:
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v34);
      v34 = 0;
      goto LABEL_32;
    }
    for ( i = 0; i < v39; ++i )
    {
      v37 = 0;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      v17 = v16(a2, i, &v37);
      v7 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x468,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v17,
          (int)string);
        goto LABEL_30;
      }
      v38 = 0;
      v18 = v37;
      v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      v20 = v19(v18, &v38);
      v7 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46B,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v20,
          (int)string);
        goto LABEL_25;
      }
      v36 = 0;
      v21 = v38;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 48LL);
      WindowsDeleteString(0);
      v36 = 0;
      v23 = v22(v21, &v36);
      v7 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46E,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v23,
          (int)string);
        goto LABEL_24;
      }
      v41 = 0;
      v24 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(
              &v38,
              &v41);
      v7 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x471,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v24,
          (int)string);
LABEL_23:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_24:
        WindowsDeleteString(v36);
        v36 = 0;
LABEL_25:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
LABEL_30:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        goto LABEL_31;
      }
      v40 = 0;
      v25 = v41;
      v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 56LL);
      WindowsDeleteString(0);
      v40 = 0;
      v27 = v26(v25, &v40);
      v7 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x474,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v27,
          (int)string);
        WindowsDeleteString(v40);
        v40 = 0;
        goto LABEL_23;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(v34, 0);
      v29 = WindowsGetStringRawBuffer(v36, 0);
      v30 = WindowsGetStringRawBuffer(string, 0);
      v31 = WindowsGetStringRawBuffer(v40, 0);
      if ( !_wcsicmp(StringRawBuffer, v29) && !_wcsicmp(v30, v31) )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a3 + 104LL))(a3, v37);
      WindowsDeleteString(v40);
      v40 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      WindowsDeleteString(v36);
      v36 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    }
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v34);
    v34 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  }
  return 0;
}

```

## disassembly

```asm
0x18005df74  mov     [rsp-8+arg_18], rbx
0x18005df79  push    rbp
0x18005df7a  push    rsi
0x18005df7b  push    rdi
0x18005df7c  push    r12
0x18005df7e  push    r13
0x18005df80  push    r14
0x18005df82  push    r15
0x18005df84  lea     rbp, [rsp-27h]
0x18005df89  sub     rsp, 0A0h
0x18005df90  mov     rax, cs:__security_cookie
0x18005df97  xor     rax, rsp
0x18005df9a  mov     [rbp+57h+var_40], rax
0x18005df9e  mov     r15, r8
0x18005dfa1  mov     r14, rdx
0x18005dfa4  mov     edi, ecx
0x18005dfa6  xor     r12d, r12d
0x18005dfa9  mov     [rbp+57h+var_80], r12d
0x18005dfad  mov     rax, [rdx]
0x18005dfb0  lea     rdx, [rbp+57h+var_80]
0x18005dfb4  mov     rcx, r14
0x18005dfb7  mov     rax, [rax+38h]
0x18005dfbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dfc0  cmp     [rbp+57h+var_80], r12d
0x18005dfc4  jbe     loc_18005E3A2
0x18005dfca  mov     [rbp+57h+var_68], r12
0x18005dfce  mov     [rbp+57h+var_48], r12
0x18005dfd2  lea     r9d, [r12+2Eh]; unsigned int
0x18005dfd7  lea     r8d, [r12+2Fh]; unsigned int
0x18005dfdc  lea     rdx, ?RuntimeClass_PhoneInternal_Experiences_Sync_AccountsManager@@3QBGB; "PhoneInternal.Experiences.Sync.Accounts"...
0x18005dfe3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005dfe7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005dfec  lea     rdx, [rbp+57h+var_68]
0x18005dff0  mov     rcx, [rbp+57h+var_48]
0x18005dff4  call    ??$GetActivationFactory@V?$ComPtr@UIAccountsManagerStatics@Sync@Experiences@PhoneInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAccountsManagerStatics@Sync@Experiences@PhoneInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<PhoneInternal::Experiences::Sync::IAccountsManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<PhoneInternal::Experiences::Sync::IAccountsManagerStatics>>)
0x18005dff9  mov     ebx, eax
0x18005dffb  test    eax, eax
0x18005dffd  jns     short loc_18005E01C
0x18005dfff  mov     rcx, [rbp+5Fh]; this
0x18005e003  mov     r9d, eax; char *
0x18005e006  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e00d  mov     edx, 45Ah; void *
0x18005e012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e017  jmp     loc_18005E366
0x18005e01c  mov     [rbp+57h+var_A0], r12
0x18005e020  mov     rcx, [rbp+57h+var_68]
0x18005e024  mov     rax, [rcx]
0x18005e027  lea     r8, [rbp+57h+var_A0]
0x18005e02b  mov     edx, edi
0x18005e02d  mov     rax, [rax+70h]
0x18005e031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e036  mov     ebx, eax
0x18005e038  test    eax, eax
0x18005e03a  jns     short loc_18005E059
0x18005e03c  mov     rcx, [rbp+5Fh]; this
0x18005e040  mov     r9d, eax; char *
0x18005e043  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e04a  mov     edx, 45Dh; void *
0x18005e04f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e054  jmp     loc_18005E35C
0x18005e059  mov     [rbp+57h+var_A8], r12
0x18005e05d  mov     [rbp+57h+string], r12
0x18005e061  mov     rdi, [rbp+57h+var_A0]
0x18005e065  mov     rax, [rdi]
0x18005e068  mov     rbx, [rax+38h]
0x18005e06c  xor     ecx, ecx; string
0x18005e06e  call    cs:__imp_WindowsDeleteString
0x18005e074  mov     [rbp+57h+var_A8], r12
0x18005e078  lea     rdx, [rbp+57h+var_A8]
0x18005e07c  mov     rcx, rdi
0x18005e07f  mov     rax, rbx
0x18005e082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e087  mov     ebx, eax
0x18005e089  test    eax, eax
0x18005e08b  jns     short loc_18005E0AA
0x18005e08d  mov     edx, 462h; void *
0x18005e092  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e099  mov     r9d, eax; char *
0x18005e09c  mov     rcx, [rbp+5Fh]; this
0x18005e0a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e0a5  jmp     loc_18005E340
0x18005e0aa  mov     rdi, [rbp+57h+var_A0]
0x18005e0ae  mov     rax, [rdi]
0x18005e0b1  mov     rbx, [rax+30h]
0x18005e0b5  mov     rcx, [rbp+57h+string]; string
0x18005e0b9  call    cs:__imp_WindowsDeleteString
0x18005e0bf  mov     [rbp+57h+string], r12
0x18005e0c3  lea     rdx, [rbp+57h+string]
0x18005e0c7  mov     rcx, rdi
0x18005e0ca  mov     rax, rbx
0x18005e0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0d2  mov     ebx, eax
0x18005e0d4  test    eax, eax
0x18005e0d6  jns     short loc_18005E0DF
0x18005e0d8  mov     edx, 463h
0x18005e0dd  jmp     short loc_18005E092
0x18005e0df  mov     esi, r12d
0x18005e0e2  cmp     esi, [rbp+57h+var_80]
0x18005e0e5  jnb     loc_18005E373
0x18005e0eb  mov     [rbp+57h+var_90], r12
0x18005e0ef  mov     rax, [r14]
0x18005e0f2  mov     rbx, [rax+30h]
0x18005e0f6  lea     rcx, [rbp+57h+var_90]
0x18005e0fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e0ff  lea     r8, [rbp+57h+var_90]
0x18005e103  mov     edx, esi
0x18005e105  mov     rcx, r14
0x18005e108  mov     rax, rbx
0x18005e10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e110  mov     ebx, eax
0x18005e112  test    eax, eax
0x18005e114  js      loc_18005E31D
0x18005e11a  mov     [rbp+57h+var_88], r12
0x18005e11e  mov     rdi, [rbp+57h+var_90]
0x18005e122  mov     rax, [rdi]
0x18005e125  mov     rbx, [rax+30h]
0x18005e129  lea     rcx, [rbp+57h+var_88]
0x18005e12d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e132  lea     rdx, [rbp+57h+var_88]
0x18005e136  mov     rcx, rdi
0x18005e139  mov     rax, rbx
0x18005e13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e141  mov     ebx, eax
0x18005e143  test    eax, eax
0x18005e145  js      loc_18005E303
0x18005e14b  mov     [rbp+57h+var_98], r12
0x18005e14f  mov     rdi, [rbp+57h+var_88]
0x18005e153  mov     rax, [rdi]
0x18005e156  mov     rbx, [rax+30h]
0x18005e15a  xor     ecx, ecx; string
0x18005e15c  call    cs:__imp_WindowsDeleteString
0x18005e162  mov     [rbp+57h+var_98], r12
0x18005e166  lea     rdx, [rbp+57h+var_98]
0x18005e16a  mov     rcx, rdi
0x18005e16d  mov     rax, rbx
0x18005e170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e175  mov     ebx, eax
0x18005e177  test    eax, eax
0x18005e179  js      loc_18005E2E9
0x18005e17f  mov     [rbp+57h+var_70], r12
0x18005e183  lea     rdx, [rbp+57h+var_70]
0x18005e187  lea     rcx, [rbp+57h+var_88]
0x18005e18b  call    ??$As@UIWebAccountProvider2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProvider2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider2>>)
0x18005e190  mov     ebx, eax
0x18005e192  test    eax, eax
0x18005e194  js      loc_18005E2CF
0x18005e19a  mov     [rbp+57h+var_78], r12
0x18005e19e  mov     rdi, [rbp+57h+var_70]
0x18005e1a2  mov     rax, [rdi]
0x18005e1a5  mov     rbx, [rax+38h]
0x18005e1a9  xor     ecx, ecx; string
0x18005e1ab  call    cs:__imp_WindowsDeleteString
0x18005e1b1  mov     [rbp+57h+var_78], r12
0x18005e1b5  lea     rdx, [rbp+57h+var_78]
0x18005e1b9  mov     rcx, rdi
0x18005e1bc  mov     rax, rbx
0x18005e1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1c4  mov     ebx, eax
0x18005e1c6  test    eax, eax
0x18005e1c8  js      loc_18005E285
0x18005e1ce  xor     edx, edx; length
0x18005e1d0  mov     rcx, [rbp+57h+var_A8]; string
0x18005e1d4  call    cs:__imp_WindowsGetStringRawBuffer
0x18005e1da  mov     rdi, rax
0x18005e1dd  xor     edx, edx; length
0x18005e1df  mov     rcx, [rbp+57h+var_98]; string
0x18005e1e3  call    cs:__imp_WindowsGetStringRawBuffer
0x18005e1e9  mov     rbx, rax
0x18005e1ec  xor     edx, edx; length
0x18005e1ee  mov     rcx, [rbp+57h+string]; string
0x18005e1f2  call    cs:__imp_WindowsGetStringRawBuffer
0x18005e1f8  mov     r12, rax
0x18005e1fb  xor     edx, edx; length
0x18005e1fd  mov     rcx, [rbp+57h+var_78]; string
0x18005e201  call    cs:__imp_WindowsGetStringRawBuffer
0x18005e207  mov     r13, rax
0x18005e20a  mov     rdx, rbx; String2
0x18005e20d  mov     rcx, rdi; String1
0x18005e210  call    cs:__imp__wcsicmp
0x18005e216  test    eax, eax
0x18005e218  jnz     short loc_18005E242
0x18005e21a  mov     rdx, r13; String2
0x18005e21d  mov     rcx, r12; String1
0x18005e220  call    cs:__imp__wcsicmp
0x18005e226  xor     r12d, r12d
0x18005e229  test    eax, eax
0x18005e22b  jnz     short loc_18005E245
0x18005e22d  mov     rax, [r15]
0x18005e230  mov     rdx, [rbp+57h+var_90]
0x18005e234  mov     rcx, r15
0x18005e237  mov     rax, [rax+68h]
0x18005e23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e240  jmp     short loc_18005E245
0x18005e242  xor     r12d, r12d
0x18005e245  mov     rcx, [rbp+57h+var_78]; string
0x18005e249  call    cs:__imp_WindowsDeleteString
0x18005e24f  mov     [rbp+57h+var_78], r12
0x18005e253  lea     rcx, [rbp+57h+var_70]
0x18005e257  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e25c  nop
0x18005e25d  mov     rcx, [rbp+57h+var_98]; string
0x18005e261  call    cs:__imp_WindowsDeleteString
0x18005e267  mov     [rbp+57h+var_98], r12
0x18005e26b  lea     rcx, [rbp+57h+var_88]
0x18005e26f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e274  nop
0x18005e275  lea     rcx, [rbp+57h+var_90]
0x18005e279  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e27e  inc     esi
0x18005e280  jmp     loc_18005E0E2
0x18005e285  mov     rcx, [rbp+5Fh]; this
0x18005e289  mov     r9d, eax; char *
0x18005e28c  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e293  mov     edx, 474h; void *
0x18005e298  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e29d  nop
0x18005e29e  mov     rcx, [rbp+57h+var_78]; string
0x18005e2a2  call    cs:__imp_WindowsDeleteString
0x18005e2a8  mov     [rbp+57h+var_78], r12
0x18005e2ac  lea     rcx, [rbp+57h+var_70]
0x18005e2b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e2b5  nop
0x18005e2b6  mov     rcx, [rbp+57h+var_98]; string
0x18005e2ba  call    cs:__imp_WindowsDeleteString
0x18005e2c0  mov     [rbp+57h+var_98], r12
0x18005e2c4  lea     rcx, [rbp+57h+var_88]
0x18005e2c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e2cd  jmp     short loc_18005E336
0x18005e2cf  mov     rcx, [rbp+5Fh]; this
0x18005e2d3  mov     r9d, eax; char *
0x18005e2d6  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e2dd  mov     edx, 471h; void *
0x18005e2e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e2e7  jmp     short loc_18005E2AC
0x18005e2e9  mov     rcx, [rbp+5Fh]; this
0x18005e2ed  mov     r9d, eax; char *
0x18005e2f0  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e2f7  mov     edx, 46Eh; void *
0x18005e2fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e301  jmp     short loc_18005E2B6
0x18005e303  mov     rcx, [rbp+5Fh]; this
0x18005e307  mov     r9d, eax; char *
0x18005e30a  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e311  mov     edx, 46Bh; void *
0x18005e316  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e31b  jmp     short loc_18005E2C4
0x18005e31d  mov     rcx, [rbp+5Fh]; this
0x18005e321  mov     r9d, eax; char *
0x18005e324  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e32b  mov     edx, 468h; void *
0x18005e330  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e335  nop
0x18005e336  lea     rcx, [rbp+57h+var_90]
0x18005e33a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e33f  nop
0x18005e340  mov     rcx, [rbp+57h+string]; string
0x18005e344  call    cs:__imp_WindowsDeleteString
0x18005e34a  mov     [rbp+57h+string], r12
0x18005e34e  mov     rcx, [rbp+57h+var_A8]; string
0x18005e352  call    cs:__imp_WindowsDeleteString
0x18005e358  mov     [rbp+57h+var_A8], r12
0x18005e35c  lea     rcx, [rbp+57h+var_A0]
0x18005e360  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e365  nop
0x18005e366  lea     rcx, [rbp+57h+var_68]
0x18005e36a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e36f  mov     eax, ebx
0x18005e371  jmp     short loc_18005E3A4
0x18005e373  mov     rcx, [rbp+57h+string]; string
0x18005e377  call    cs:__imp_WindowsDeleteString
0x18005e37d  mov     [rbp+57h+string], r12
0x18005e381  mov     rcx, [rbp+57h+var_A8]; string
0x18005e385  call    cs:__imp_WindowsDeleteString
0x18005e38b  mov     [rbp+57h+var_A8], r12
0x18005e38f  lea     rcx, [rbp+57h+var_A0]
0x18005e393  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e398  nop
0x18005e399  lea     rcx, [rbp+57h+var_68]
0x18005e39d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e3a2  xor     eax, eax
0x18005e3a4  mov     rcx, [rbp+57h+var_40]
0x18005e3a8  xor     rcx, rsp; StackCookie
0x18005e3ab  call    __security_check_cookie
0x18005e3b0  mov     rbx, [rsp+0D0h+arg_18]
0x18005e3b8  add     rsp, 0A0h
0x18005e3bf  pop     r15
0x18005e3c1  pop     r14
0x18005e3c3  pop     r13
0x18005e3c5  pop     r12
0x18005e3c7  pop     rdi
0x18005e3c8  pop     rsi
0x18005e3c9  pop     rbp
0x18005e3ca  retn
```
