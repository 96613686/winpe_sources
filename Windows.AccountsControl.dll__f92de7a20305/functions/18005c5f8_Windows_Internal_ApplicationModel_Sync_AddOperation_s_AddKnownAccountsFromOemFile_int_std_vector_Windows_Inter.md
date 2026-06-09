# Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddKnownAccountsFromOemFile(int,std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData,std::allocator<Windows::Internal::ApplicationModel::Sync::ProviderData>> *)

- ea: `0x18005c5f8`
- end: `0x18005c929`
- name: `?s_AddKnownAccountsFromOemFile@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJHPEAV?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@@Z`
- size: `817`
- prototype: `__int64 __fastcall(int, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18005aca0`

## callees

- `0x180006eac`
- `0x180007f68`
- `0x180011ffc`
- `0x180056540`
- `0x18005a098`
- `0x18005c5f8`
- `0x18005cc0c`
- `0x18006245c`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c77d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c7cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c826`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c88e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c77d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c7cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c826`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c88e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c8b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddKnownAccountsFromOemFile(
        int a1,
        char a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *v6; // rbx
  int AccountTypes; // eax
  __int64 v8; // rdx
  unsigned int i; // esi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-49h]
  HSTRING v24; // [rsp+40h] [rbp-29h] BYREF
  __int64 v25; // [rsp+48h] [rbp-21h] BYREF
  HSTRING string; // [rsp+50h] [rbp-19h] BYREF
  HSTRING v27; // [rsp+58h] [rbp-11h] BYREF
  __int64 v28; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v29; // [rsp+68h] [rbp-1h] BYREF
  int v30; // [rsp+6Ch] [rbp+3h] BYREF
  Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *v31; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v31 = 0;
  v25 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader) + 24);
  v4 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile,Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile,HSTRING__ *>(
         &v31,
         &v25);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v28 = 0;
    v6 = v31;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    AccountTypes = Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::LoadAccountTypes(v6);
    v5 = AccountTypes;
    if ( AccountTypes >= 0 )
    {
      if ( !v28 )
      {
LABEL_28:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
        v5 = 0;
        goto LABEL_29;
      }
      v29 = 0;
      AccountTypes = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 56LL))(v28, &v29);
      v5 = AccountTypes;
      if ( AccountTypes >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v29 )
            goto LABEL_28;
          v25 = 0;
          v10 = v28;
          v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
          v12 = v11(v10, i, &v25);
          v5 = v12;
          if ( v12 < 0 )
            break;
          v24 = 0;
          v13 = v25;
          v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 72LL);
          WindowsDeleteString(0);
          v24 = 0;
          v15 = v14(v13, &v24);
          v5 = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2AB,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)v15,
              v23);
            goto LABEL_25;
          }
          v30 = 0;
          string = 0;
          v27 = 0;
          v16 = v25;
          v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 48LL);
          WindowsDeleteString(0);
          v27 = 0;
          v18 = v17(v16, &v27);
          v5 = v18;
          if ( v18 < 0 )
          {
            v21 = 688;
LABEL_23:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v21,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)v18,
              v23);
            WindowsDeleteString(v27);
            v27 = 0;
            WindowsDeleteString(string);
            string = 0;
LABEL_25:
            WindowsDeleteString(v24);
            v24 = 0;
LABEL_27:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
            goto LABEL_6;
          }
          v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 64LL))(v25, &v30);
          v5 = v18;
          if ( v18 < 0 )
          {
            v21 = 689;
            goto LABEL_23;
          }
          v19 = v25;
          v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 80LL);
          WindowsDeleteString(string);
          string = 0;
          v18 = v20(v19, &string);
          v5 = v18;
          if ( v18 < 0 )
          {
            v21 = 690;
            goto LABEL_23;
          }
          v18 = Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddProviderToPriorityList(
                  v27,
                  v24,
                  a1,
                  v30,
                  a2);
          v5 = v18;
          if ( v18 < 0 )
          {
            v21 = 699;
            goto LABEL_23;
          }
          WindowsDeleteString(v27);
          v27 = 0;
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v24);
          v24 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A8,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v12,
          v23);
        goto LABEL_27;
      }
      v8 = 675;
    }
    else
    {
      v8 = 670;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)AccountTypes,
      v23);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v4,
      v23);
  }
LABEL_29:
  Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile>::InternalRelease(&v31);
  return v5;
}

```

## disassembly

```asm
0x18005c5f8  mov     [rsp-8+arg_10], rbx
0x18005c5fd  mov     [rsp-8+arg_18], rsi
0x18005c602  push    rbp
0x18005c603  push    rdi
0x18005c604  push    r12
0x18005c606  push    r14
0x18005c608  push    r15
0x18005c60a  lea     rbp, [rsp-37h]
0x18005c60f  sub     rsp, 0A0h
0x18005c616  mov     rax, cs:__security_cookie
0x18005c61d  xor     rax, rsp
0x18005c620  mov     [rbp+57h+var_28], rax
0x18005c624  mov     r15, rdx
0x18005c627  mov     r14d, ecx
0x18005c62a  xor     r12d, r12d
0x18005c62d  mov     [rbp+57h+var_50], r12
0x18005c631  lea     rdx, off_180089098; "KnownAccountsOem.xml"
0x18005c638  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005c63c  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18005c641  mov     rcx, [rax+18h]
0x18005c645  mov     [rbp+57h+var_78], rcx
0x18005c649  lea     rdx, [rbp+57h+var_78]
0x18005c64d  lea     rcx, [rbp+57h+var_50]
0x18005c651  call    ??$MakeAndInitialize@VKnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@V12345@PEAUHSTRING__@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VKnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@012@$$QEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile,Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile,HSTRING__ *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile>>,HSTRING__ * &&)
0x18005c656  mov     ebx, eax
0x18005c658  test    eax, eax
0x18005c65a  jns     short loc_18005C679
0x18005c65c  mov     rcx, [rbp+5Fh]; this
0x18005c660  mov     r9d, eax; char *
0x18005c663  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005c66a  mov     edx, 29Bh; void *
0x18005c66f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c674  jmp     loc_18005C8F6
0x18005c679  mov     [rbp+57h+var_60], r12
0x18005c67d  mov     rbx, [rbp+57h+var_50]
0x18005c681  lea     rcx, [rbp+57h+var_60]
0x18005c685  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005c68a  lea     rdx, [rbp+57h+var_60]
0x18005c68e  mov     rcx, rbx; this
0x18005c691  call    ?LoadAccountTypes@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@QEAAJPEAPEAU?$IVector@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@@Collections@Foundation@5@@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::LoadAccountTypes(Windows::Foundation::Collections::IVector<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *> * *)
0x18005c696  mov     ebx, eax
0x18005c698  test    eax, eax
0x18005c69a  jns     short loc_18005C6C3
0x18005c69c  mov     edx, 29Eh; void *
0x18005c6a1  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005c6a8  mov     r9d, eax; char *
0x18005c6ab  mov     rcx, [rbp+5Fh]; this
0x18005c6af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c6b4  nop
0x18005c6b5  lea     rcx, [rbp+57h+var_60]
0x18005c6b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005c6be  jmp     loc_18005C8F6
0x18005c6c3  mov     rcx, [rbp+57h+var_60]
0x18005c6c7  test    rcx, rcx
0x18005c6ca  jz      loc_18005C8EA
0x18005c6d0  mov     [rbp+57h+var_58], r12d
0x18005c6d4  mov     rax, [rcx]
0x18005c6d7  lea     rdx, [rbp+57h+var_58]
0x18005c6db  mov     rax, [rax+38h]
0x18005c6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c6e4  mov     ebx, eax
0x18005c6e6  test    eax, eax
0x18005c6e8  jns     short loc_18005C6F1
0x18005c6ea  mov     edx, 2A3h
0x18005c6ef  jmp     short loc_18005C6A1
0x18005c6f1  mov     esi, r12d
0x18005c6f4  cmp     esi, [rbp+57h+var_58]
0x18005c6f7  jnb     loc_18005C8EA
0x18005c6fd  mov     [rbp+57h+var_78], r12
0x18005c701  mov     rdi, [rbp+57h+var_60]
0x18005c705  mov     rax, [rdi]
0x18005c708  mov     rbx, [rax+30h]
0x18005c70c  lea     rcx, [rbp+57h+var_78]
0x18005c710  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005c715  lea     r8, [rbp+57h+var_78]
0x18005c719  mov     edx, esi
0x18005c71b  mov     rcx, rdi
0x18005c71e  mov     rax, rbx
0x18005c721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c726  mov     ebx, eax
0x18005c728  test    eax, eax
0x18005c72a  js      loc_18005C8C3
0x18005c730  mov     [rbp+57h+var_80], r12
0x18005c734  mov     rdi, [rbp+57h+var_78]
0x18005c738  mov     rax, [rdi]
0x18005c73b  mov     rbx, [rax+48h]
0x18005c73f  xor     ecx, ecx; string
0x18005c741  call    cs:__imp_WindowsDeleteString
0x18005c747  mov     [rbp+57h+var_80], r12
0x18005c74b  lea     rdx, [rbp+57h+var_80]
0x18005c74f  mov     rcx, rdi
0x18005c752  mov     rax, rbx
0x18005c755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c75a  mov     ebx, eax
0x18005c75c  test    eax, eax
0x18005c75e  js      loc_18005C89A
0x18005c764  mov     [rbp+57h+var_54], r12d
0x18005c768  mov     [rbp+57h+string], r12
0x18005c76c  mov     [rbp+57h+var_68], r12
0x18005c770  mov     rdi, [rbp+57h+var_78]
0x18005c774  mov     rax, [rdi]
0x18005c777  mov     rbx, [rax+30h]
0x18005c77b  xor     ecx, ecx; string
0x18005c77d  call    cs:__imp_WindowsDeleteString
0x18005c783  mov     [rbp+57h+var_68], r12
0x18005c787  lea     rdx, [rbp+57h+var_68]
0x18005c78b  mov     rcx, rdi
0x18005c78e  mov     rax, rbx
0x18005c791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c796  mov     ebx, eax
0x18005c798  test    eax, eax
0x18005c79a  js      loc_18005C863
0x18005c7a0  mov     rcx, [rbp+57h+var_78]
0x18005c7a4  mov     rax, [rcx]
0x18005c7a7  lea     rdx, [rbp+57h+var_54]
0x18005c7ab  mov     rax, [rax+40h]
0x18005c7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7b4  mov     ebx, eax
0x18005c7b6  test    eax, eax
0x18005c7b8  js      loc_18005C85C
0x18005c7be  mov     rdi, [rbp+57h+var_78]
0x18005c7c2  mov     rax, [rdi]
0x18005c7c5  mov     rbx, [rax+50h]
0x18005c7c9  mov     rcx, [rbp+57h+string]; string
0x18005c7cd  call    cs:__imp_WindowsDeleteString
0x18005c7d3  mov     [rbp+57h+string], r12
0x18005c7d7  lea     rdx, [rbp+57h+string]
0x18005c7db  mov     rcx, rdi
0x18005c7de  mov     rax, rbx
0x18005c7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7e6  mov     ebx, eax
0x18005c7e8  test    eax, eax
0x18005c7ea  js      short loc_18005C855
0x18005c7ec  mov     eax, [rbp+57h+var_54]
0x18005c7ef  mov     qword ptr [rsp+0C0h+var_90], r15; char
0x18005c7f4  mov     [rsp+0C0h+var_98], eax; int
0x18005c7f8  mov     [rsp+0C0h+var_A0], r14d; int
0x18005c7fd  mov     r9, [rbp+57h+string]
0x18005c801  mov     rdx, [rbp+57h+var_80]; HSTRING
0x18005c805  mov     rcx, [rbp+57h+var_68]; HSTRING
0x18005c809  call    ?s_AddProviderToPriorityList@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@000HIPEAV?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddProviderToPriorityList(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,int,uint,std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData> *)
0x18005c80e  mov     ebx, eax
0x18005c810  test    eax, eax
0x18005c812  js      short loc_18005C84E
0x18005c814  mov     rcx, [rbp+57h+var_68]; string
0x18005c818  call    cs:__imp_WindowsDeleteString
0x18005c81e  mov     [rbp+57h+var_68], r12
0x18005c822  mov     rcx, [rbp+57h+string]; string
0x18005c826  call    cs:__imp_WindowsDeleteString
0x18005c82c  mov     [rbp+57h+string], r12
0x18005c830  mov     rcx, [rbp+57h+var_80]; string
0x18005c834  call    cs:__imp_WindowsDeleteString
0x18005c83a  mov     [rbp+57h+var_80], r12
0x18005c83e  lea     rcx, [rbp+57h+var_78]
0x18005c842  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005c847  inc     esi
0x18005c849  jmp     loc_18005C6F4
0x18005c84e  mov     edx, 2BBh
0x18005c853  jmp     short loc_18005C868
0x18005c855  mov     edx, 2B2h
0x18005c85a  jmp     short loc_18005C868
0x18005c85c  mov     edx, 2B1h
0x18005c861  jmp     short loc_18005C868
0x18005c863  mov     edx, 2B0h; void *
0x18005c868  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005c86f  mov     r9d, eax; char *
0x18005c872  mov     rcx, [rbp+5Fh]; this
0x18005c876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c87b  nop
0x18005c87c  mov     rcx, [rbp+57h+var_68]; string
0x18005c880  call    cs:__imp_WindowsDeleteString
0x18005c886  mov     [rbp+57h+var_68], r12
0x18005c88a  mov     rcx, [rbp+57h+string]; string
0x18005c88e  call    cs:__imp_WindowsDeleteString
0x18005c894  mov     [rbp+57h+string], r12
0x18005c898  jmp     short loc_18005C8B3
0x18005c89a  mov     rcx, [rbp+5Fh]; this
0x18005c89e  mov     r9d, eax; char *
0x18005c8a1  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005c8a8  mov     edx, 2ABh; void *
0x18005c8ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c8b2  nop
0x18005c8b3  mov     rcx, [rbp+57h+var_80]; string
0x18005c8b7  call    cs:__imp_WindowsDeleteString
0x18005c8bd  mov     [rbp+57h+var_80], r12
0x18005c8c1  jmp     short loc_18005C8DC
0x18005c8c3  mov     rcx, [rbp+5Fh]; this
0x18005c8c7  mov     r9d, eax; char *
0x18005c8ca  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005c8d1  mov     edx, 2A8h; void *
0x18005c8d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c8db  nop
0x18005c8dc  lea     rcx, [rbp+57h+var_78]
0x18005c8e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005c8e5  jmp     loc_18005C6B5
0x18005c8ea  lea     rcx, [rbp+57h+var_60]
0x18005c8ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005c8f3  mov     ebx, r12d
0x18005c8f6  lea     rcx, [rbp+57h+var_50]
0x18005c8fa  call    ?InternalRelease@?$ComPtr@VKnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile>::InternalRelease(void)
0x18005c8ff  mov     eax, ebx
0x18005c901  mov     rcx, [rbp+57h+var_28]
0x18005c905  xor     rcx, rsp; StackCookie
0x18005c908  call    __security_check_cookie
0x18005c90d  lea     r11, [rsp+0C0h+var_20]
0x18005c915  mov     rbx, [r11+40h]
0x18005c919  mov     rsi, [r11+48h]
0x18005c91d  mov     rsp, r11
0x18005c920  pop     r15
0x18005c922  pop     r14
0x18005c924  pop     r12
0x18005c926  pop     rdi
0x18005c927  pop     rbp
0x18005c928  retn
```
