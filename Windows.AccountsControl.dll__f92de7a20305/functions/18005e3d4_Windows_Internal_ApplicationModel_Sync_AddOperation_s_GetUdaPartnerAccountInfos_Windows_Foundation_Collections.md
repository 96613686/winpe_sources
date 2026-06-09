# Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetUdaPartnerAccountInfos(Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *> * *)

- ea: `0x18005e3d4`
- end: `0x18005e737`
- name: `?s_GetUdaPartnerAccountInfos@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAPEAU?$IVectorView@PEAVUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@@Collections@Foundation@5@@Z`
- size: `867`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18005d624`

## callees

- `0x180006eac`
- `0x180007f68`
- `0x180011ffc`
- `0x180055388`
- `0x180056540`
- `0x180056570`
- `0x18005a098`
- `0x18005e3d4`
- `0x18006245c`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e69d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e69d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetUdaPartnerAccountInfos(_QWORD *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *v4; // rbx
  int AccountTypes; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rdx
  unsigned int i; // esi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v24; // [rsp+20h] [rbp-49h] BYREF
  __int64 v25; // [rsp+28h] [rbp-41h] BYREF
  HSTRING string; // [rsp+30h] [rbp-39h] BYREF
  __int64 v27; // [rsp+38h] [rbp-31h] BYREF
  __int64 v28; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-21h] BYREF
  int v30; // [rsp+4Ch] [rbp-1Dh] BYREF
  int v31; // [rsp+50h] [rbp-19h] BYREF
  int v32; // [rsp+54h] [rbp-15h] BYREF
  Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *v33; // [rsp+58h] [rbp-11h] BYREF
  HSTRING v34; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a1 = 0;
  v33 = 0;
  v28 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader) + 24);
  v2 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile,Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile,HSTRING__ *>(
         &v33,
         &v28);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v24 = 0;
    v4 = v33;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    AccountTypes = Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::LoadAccountTypes(v4);
    v3 = AccountTypes;
    if ( AccountTypes >= 0 )
    {
      v29 = 0;
      AccountTypes = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 56LL))(v24, &v29);
      v3 = AccountTypes;
      if ( AccountTypes >= 0 )
      {
        v25 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        v8 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *>,0>>(
               v7,
               &v25);
        v3 = v8;
        if ( v8 >= 0 )
        {
          for ( i = 0; i < v29; ++i )
          {
            v27 = 0;
            v11 = v24;
            v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
            v13 = v12(v11, i, &v27);
            v3 = v13;
            if ( v13 < 0 )
            {
              v20 = 1289;
              goto LABEL_36;
            }
            v30 = 0;
            v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 56LL))(v27, &v30);
            v3 = v13;
            if ( v13 < 0 )
            {
              v20 = 1292;
LABEL_36:
              v19 = (unsigned int)v13;
              goto LABEL_37;
            }
            if ( v30 == 1 )
            {
              v14 = 0;
            }
            else
            {
              if ( v30 != 2 )
              {
                v3 = -2147418113;
                v19 = 2147549183LL;
                v20 = 1295;
LABEL_37:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v20,
                  (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
                  (const char *)v19,
                  v24);
                goto LABEL_38;
              }
              v14 = 1;
            }
            v32 = v14;
            string = 0;
            v15 = v27;
            v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 72LL);
            WindowsDeleteString(0);
            string = 0;
            v17 = v16(v15, &string);
            v3 = v17;
            if ( v17 < 0 )
            {
              v22 = 1298;
              goto LABEL_32;
            }
            v31 = 0;
            v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 64LL))(v27, &v31);
            v3 = v17;
            if ( v17 < 0 )
            {
              v22 = 1301;
LABEL_32:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v22,
                (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
                (const char *)(unsigned int)v17,
                v24);
              goto LABEL_33;
            }
            v28 = 0;
            v34 = string;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
            v18 = Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo,Windows::ApplicationModel::UserDataAccounts::Provider::IUserDataAccountPartnerAccountInfo,enum Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountProviderPartnerAccountKind &,HSTRING__ *,unsigned int &>(
                    &v28,
                    &v32,
                    &v34,
                    &v31);
            v3 = v18;
            if ( v18 < 0 )
            {
              v21 = 1308;
LABEL_29:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v21,
                (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
                (const char *)(unsigned int)v18,
                v24);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
LABEL_33:
              WindowsDeleteString(string);
              string = 0;
LABEL_38:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
              goto LABEL_12;
            }
            v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 104LL))(v25, v28);
            v3 = v18;
            if ( v18 < 0 )
            {
              v21 = 1310;
              goto LABEL_29;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
          }
          v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v25 + 64LL))(v25, a1);
          v3 = v8;
          if ( v8 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
            v3 = 0;
            goto LABEL_42;
          }
          v9 = 1313;
        }
        else
        {
          v9 = 1284;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v8,
          v24);
LABEL_12:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        goto LABEL_6;
      }
      v6 = 1281;
    }
    else
    {
      v6 = 1278;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)AccountTypes,
      v24);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    goto LABEL_42;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4FB,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
    (const char *)(unsigned int)v2,
    v24);
LABEL_42:
  Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile>::InternalRelease(&v33);
  return v3;
}

```

## disassembly

```asm
0x18005e3d4  push    rbp
0x18005e3d6  push    rbx
0x18005e3d7  push    rsi
0x18005e3d8  push    rdi
0x18005e3d9  push    r14
0x18005e3db  push    r15
0x18005e3dd  lea     rbp, [rsp-2Fh]
0x18005e3e2  sub     rsp, 98h
0x18005e3e9  mov     rax, cs:__security_cookie
0x18005e3f0  xor     rax, rsp
0x18005e3f3  mov     [rbp+57h+var_38], rax
0x18005e3f7  mov     r14, rcx
0x18005e3fa  xor     r15d, r15d
0x18005e3fd  mov     [rcx], r15
0x18005e400  mov     [rbp+57h+var_68], r15
0x18005e404  lea     rdx, off_180089098; "KnownAccountsOem.xml"
0x18005e40b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005e40f  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18005e414  mov     rcx, [rax+18h]
0x18005e418  mov     [rbp+57h+var_80], rcx
0x18005e41c  lea     rdx, [rbp+57h+var_80]
0x18005e420  lea     rcx, [rbp+57h+var_68]
0x18005e424  call    ??$MakeAndInitialize@VKnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@V12345@PEAUHSTRING__@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VKnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@012@$$QEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile,Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile,HSTRING__ *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile>>,HSTRING__ * &&)
0x18005e429  mov     ebx, eax
0x18005e42b  test    eax, eax
0x18005e42d  jns     short loc_18005E44C
0x18005e42f  mov     rcx, [rbp+5Fh]; this
0x18005e433  mov     r9d, eax; char *
0x18005e436  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e43d  mov     edx, 4FBh; void *
0x18005e442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e447  jmp     loc_18005E710
0x18005e44c  mov     [rbp+57h+var_A0], r15
0x18005e450  mov     rbx, [rbp+57h+var_68]
0x18005e454  lea     rcx, [rbp+57h+var_A0]
0x18005e458  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e45d  lea     rdx, [rbp+57h+var_A0]
0x18005e461  mov     rcx, rbx; this
0x18005e464  call    ?LoadAccountTypes@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@QEAAJPEAPEAU?$IVector@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@@Collections@Foundation@5@@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::LoadAccountTypes(Windows::Foundation::Collections::IVector<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *> * *)
0x18005e469  mov     ebx, eax
0x18005e46b  test    eax, eax
0x18005e46d  jns     short loc_18005E496
0x18005e46f  mov     edx, 4FEh; void *
0x18005e474  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e47b  mov     r9d, eax; char *
0x18005e47e  mov     rcx, [rbp+5Fh]; this
0x18005e482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e487  nop
0x18005e488  lea     rcx, [rbp+57h+var_A0]
0x18005e48c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e491  jmp     loc_18005E710
0x18005e496  mov     [rbp+57h+var_78], r15d
0x18005e49a  mov     rcx, [rbp+57h+var_A0]
0x18005e49e  mov     rax, [rcx]
0x18005e4a1  lea     rdx, [rbp+57h+var_78]
0x18005e4a5  mov     rax, [rax+38h]
0x18005e4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4ae  mov     ebx, eax
0x18005e4b0  test    eax, eax
0x18005e4b2  jns     short loc_18005E4BB
0x18005e4b4  mov     edx, 501h
0x18005e4b9  jmp     short loc_18005E474
0x18005e4bb  mov     [rbp+57h+var_98], r15
0x18005e4bf  lea     rcx, [rbp+57h+var_98]
0x18005e4c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e4c8  lea     rdx, [rbp+57h+var_98]
0x18005e4cc  call    ??$CreateExternalObjectVector@VUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@V?$AgileVector@PEAVUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@@7895@$0A@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@@7895@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo *>,0> * *)
0x18005e4d1  mov     ebx, eax
0x18005e4d3  test    eax, eax
0x18005e4d5  jns     short loc_18005E4FB
0x18005e4d7  mov     edx, 504h; void *
0x18005e4dc  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e4e3  mov     r9d, eax; char *
0x18005e4e6  mov     rcx, [rbp+5Fh]; this
0x18005e4ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e4ef  nop
0x18005e4f0  lea     rcx, [rbp+57h+var_98]
0x18005e4f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e4f9  jmp     short loc_18005E488
0x18005e4fb  mov     esi, r15d
0x18005e4fe  cmp     esi, [rbp+57h+var_78]
0x18005e501  jnb     loc_18005E6D7
0x18005e507  mov     [rbp+57h+var_88], r15
0x18005e50b  mov     rdi, [rbp+57h+var_A0]
0x18005e50f  mov     rax, [rdi]
0x18005e512  mov     rbx, [rax+30h]
0x18005e516  lea     rcx, [rbp+57h+var_88]
0x18005e51a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e51f  lea     r8, [rbp+57h+var_88]
0x18005e523  mov     edx, esi
0x18005e525  mov     rcx, rdi
0x18005e528  mov     rax, rbx
0x18005e52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e530  mov     ebx, eax
0x18005e532  test    eax, eax
0x18005e534  js      loc_18005E6B0
0x18005e53a  mov     [rbp+57h+var_74], r15d
0x18005e53e  mov     rcx, [rbp+57h+var_88]
0x18005e542  mov     rax, [rcx]
0x18005e545  lea     rdx, [rbp+57h+var_74]
0x18005e549  mov     rax, [rax+38h]
0x18005e54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e552  mov     ebx, eax
0x18005e554  test    eax, eax
0x18005e556  js      loc_18005E6A9
0x18005e55c  mov     ecx, [rbp+57h+var_74]
0x18005e55f  sub     ecx, 1
0x18005e562  jz      short loc_18005E571
0x18005e564  cmp     ecx, 1
0x18005e567  jnz     loc_18005E63F
0x18005e56d  mov     eax, ecx
0x18005e56f  jmp     short loc_18005E574
0x18005e571  mov     eax, r15d
0x18005e574  mov     [rbp+57h+var_6C], eax
0x18005e577  mov     [rbp+57h+string], r15
0x18005e57b  mov     rdi, [rbp+57h+var_88]
0x18005e57f  mov     rax, [rdi]
0x18005e582  mov     rbx, [rax+48h]
0x18005e586  xor     ecx, ecx; string
0x18005e588  call    cs:__imp_WindowsDeleteString
0x18005e58e  mov     [rbp+57h+string], r15
0x18005e592  lea     rdx, [rbp+57h+string]
0x18005e596  mov     rcx, rdi
0x18005e599  mov     rax, rbx
0x18005e59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5a1  mov     ebx, eax
0x18005e5a3  test    eax, eax
0x18005e5a5  js      loc_18005E680
0x18005e5ab  mov     [rbp+57h+var_70], r15d
0x18005e5af  mov     rcx, [rbp+57h+var_88]
0x18005e5b3  mov     rax, [rcx]
0x18005e5b6  lea     rdx, [rbp+57h+var_70]
0x18005e5ba  mov     rax, [rax+40h]
0x18005e5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5c3  mov     ebx, eax
0x18005e5c5  test    eax, eax
0x18005e5c7  js      loc_18005E679
0x18005e5cd  mov     [rbp+57h+var_80], r15
0x18005e5d1  mov     rax, [rbp+57h+string]
0x18005e5d5  mov     [rbp+57h+var_60], rax
0x18005e5d9  lea     rcx, [rbp+57h+var_80]
0x18005e5dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e5e2  lea     r9, [rbp+57h+var_70]
0x18005e5e6  lea     r8, [rbp+57h+var_60]
0x18005e5ea  lea     rdx, [rbp+57h+var_6C]
0x18005e5ee  lea     rcx, [rbp+57h+var_80]
0x18005e5f2  call    ??$MakeAndInitialize@VUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@UIUserDataAccountPartnerAccountInfo@2345@AEAW4UserDataAccountProviderPartnerAccountKind@2345@PEAUHSTRING__@@AEAI@Details@WRL@Microsoft@@YAJPEAPEAUIUserDataAccountPartnerAccountInfo@Provider@UserDataAccounts@ApplicationModel@Windows@@AEAW4UserDataAccountProviderPartnerAccountKind@4567@$$QEAPEAUHSTRING__@@AEAI@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountPartnerAccountInfo,Windows::ApplicationModel::UserDataAccounts::Provider::IUserDataAccountPartnerAccountInfo,Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountProviderPartnerAccountKind &,HSTRING__ *,uint &>(Windows::ApplicationModel::UserDataAccounts::Provider::IUserDataAccountPartnerAccountInfo * *,Windows::ApplicationModel::UserDataAccounts::Provider::UserDataAccountProviderPartnerAccountKind &,HSTRING__ * &&,uint &)
0x18005e5f7  mov     ebx, eax
0x18005e5f9  test    eax, eax
0x18005e5fb  js      short loc_18005E655
0x18005e5fd  mov     rcx, [rbp+57h+var_98]
0x18005e601  mov     rax, [rcx]
0x18005e604  mov     rdx, [rbp+57h+var_80]
0x18005e608  mov     rax, [rax+68h]
0x18005e60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e611  mov     ebx, eax
0x18005e613  test    eax, eax
0x18005e615  js      short loc_18005E64E
0x18005e617  lea     rcx, [rbp+57h+var_80]
0x18005e61b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e620  nop
0x18005e621  mov     rcx, [rbp+57h+string]; string
0x18005e625  call    cs:__imp_WindowsDeleteString
0x18005e62b  mov     [rbp+57h+string], r15
0x18005e62f  lea     rcx, [rbp+57h+var_88]
0x18005e633  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e638  inc     esi
0x18005e63a  jmp     loc_18005E4FE
0x18005e63f  mov     ebx, 8000FFFFh
0x18005e644  mov     r9d, ebx
0x18005e647  mov     edx, 50Fh
0x18005e64c  jmp     short loc_18005E6B8
0x18005e64e  mov     edx, 51Eh
0x18005e653  jmp     short loc_18005E65A
0x18005e655  mov     edx, 51Ch; void *
0x18005e65a  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e661  mov     r9d, eax; char *
0x18005e664  mov     rcx, [rbp+5Fh]; this
0x18005e668  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e66d  nop
0x18005e66e  lea     rcx, [rbp+57h+var_80]
0x18005e672  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e677  jmp     short loc_18005E699
0x18005e679  mov     edx, 515h
0x18005e67e  jmp     short loc_18005E685
0x18005e680  mov     edx, 512h; void *
0x18005e685  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e68c  mov     r9d, eax; char *
0x18005e68f  mov     rcx, [rbp+5Fh]; this
0x18005e693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e698  nop
0x18005e699  mov     rcx, [rbp+57h+string]; string
0x18005e69d  call    cs:__imp_WindowsDeleteString
0x18005e6a3  mov     [rbp+57h+string], r15
0x18005e6a7  jmp     short loc_18005E6C9
0x18005e6a9  mov     edx, 50Ch
0x18005e6ae  jmp     short loc_18005E6B5
0x18005e6b0  mov     edx, 509h; void *
0x18005e6b5  mov     r9d, eax; char *
0x18005e6b8  mov     rcx, [rbp+5Fh]; this
0x18005e6bc  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005e6c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e6c8  nop
0x18005e6c9  lea     rcx, [rbp+57h+var_88]
0x18005e6cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e6d2  jmp     loc_18005E4F0
0x18005e6d7  mov     rcx, [rbp+57h+var_98]
0x18005e6db  mov     rax, [rcx]
0x18005e6de  mov     rdx, r14
0x18005e6e1  mov     rax, [rax+40h]
0x18005e6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e6ea  mov     ebx, eax
0x18005e6ec  test    eax, eax
0x18005e6ee  jns     short loc_18005E6FA
0x18005e6f0  mov     edx, 521h
0x18005e6f5  jmp     loc_18005E4DC
0x18005e6fa  lea     rcx, [rbp+57h+var_98]
0x18005e6fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e703  nop
0x18005e704  lea     rcx, [rbp+57h+var_A0]
0x18005e708  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005e70d  mov     ebx, r15d
0x18005e710  lea     rcx, [rbp+57h+var_68]
0x18005e714  call    ?InternalRelease@?$ComPtr@VKnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile>::InternalRelease(void)
0x18005e719  mov     eax, ebx
0x18005e71b  mov     rcx, [rbp+57h+var_38]
0x18005e71f  xor     rcx, rsp; StackCookie
0x18005e722  call    __security_check_cookie
0x18005e727  add     rsp, 98h
0x18005e72e  pop     r15
0x18005e730  pop     r14
0x18005e732  pop     rdi
0x18005e733  pop     rsi
0x18005e734  pop     rbx
0x18005e735  pop     rbp
0x18005e736  retn
```
