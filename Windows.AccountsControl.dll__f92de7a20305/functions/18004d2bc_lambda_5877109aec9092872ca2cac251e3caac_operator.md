# _lambda_5877109aec9092872ca2cac251e3caac_::operator()

- ea: `0x18004d2bc`
- end: `0x18004d5e0`
- name: `_lambda_5877109aec9092872ca2cac251e3caac_::operator()`
- size: `804`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004c9b8`

## callees

- `0x180006eac`
- `0x180007f68`
- `0x1800083a8`
- `0x180011ffc`
- `0x180048bfc`
- `0x18004d2bc`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d462`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d529`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d564`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d462`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d529`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d564`

## string_xrefs

- `0x18004d329`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\tokenbrokerhelperfactory.cpp`
- `0x18004d35d`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\tokenbrokerhelperfactory.cpp`
- `0x18004d3b1`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\tokenbrokerhelperfactory.cpp`
- `0x18004d3f1`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\tokenbrokerhelperfactory.cpp`
- `0x18004d49d`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\tokenbrokerhelperfactory.cpp`
- `0x18004d513`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\tokenbrokerhelperfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall lambda_5877109aec9092872ca2cac251e3caac_::operator()(__int64 a1)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, _BYTE *); // rbx
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  int v23; // [rsp+20h] [rbp-29h]
  _BYTE v24[8]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v25; // [rsp+38h] [rbp-11h] BYREF
  __int64 v26; // [rsp+40h] [rbp-9h] BYREF
  HSTRING string; // [rsp+48h] [rbp-1h] BYREF
  __int64 v28; // [rsp+50h] [rbp+7h] BYREF
  HSTRING v29; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v30; // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v30 = 0;
  v2 = *(_QWORD *)(*(_QWORD *)a1 + 96LL);
  v3 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v2 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  v4 = v3(v2, *(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), &v30);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v28 = 0;
    v6 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
           &v30,
           &v28);
    v5 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\tokenbrokerhelperfactory.cpp",
        (const char *)(unsigned int)v6,
        v23);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      goto LABEL_24;
    }
    v26 = 0;
    v7 = v28;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    v9 = v8(v7, &v26);
    v5 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\tokenbrokerhelperfactory.cpp",
        (const char *)(unsigned int)v9,
        v23);
LABEL_8:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      goto LABEL_5;
    }
    v25 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    v11 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
            v10,
            &v25);
    v5 = v11;
    if ( v11 < 0 )
      goto LABEL_10;
    v24[0] = 0;
    v12 = v26;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v26 + 64LL);
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader);
    v11 = v13(v12, *(_QWORD *)(v14 + 24), v24);
    v5 = v11;
    if ( v11 < 0 )
      goto LABEL_10;
    if ( v24[0] )
    {
      string = 0;
      v15 = v26;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v26 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader);
      v18 = v16(v15, *(_QWORD *)(v17 + 24), &string);
      v5 = v18;
      if ( v18 < 0
        || (v18 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v25 + 104LL))(v25, string), v5 = v18, v18 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\tokenbrokerhelperfactory.cpp",
          (const char *)(unsigned int)v18,
          v23);
      }
      else
      {
        v29 = 0;
        v19 = v30;
        v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 56LL);
        WindowsDeleteString(0);
        v29 = 0;
        v21 = v20(v19, &v29);
        v5 = v21;
        if ( v21 >= 0 )
        {
          v21 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v25 + 104LL))(v25, v29);
          v5 = v21;
          if ( v21 >= 0 )
          {
            WindowsDeleteString(v29);
            v29 = 0;
            WindowsDeleteString(string);
            goto LABEL_22;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\tokenbrokerhelperfactory.cpp",
          (const char *)(unsigned int)v21,
          v23);
        WindowsDeleteString(v29);
        v29 = 0;
      }
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_11;
    }
LABEL_22:
    v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD))v25)(
            v25,
            &GUID_98b9acc1_4b56_532e_ac73_03d5291cca90,
            **(_QWORD **)(a1 + 24));
    v5 = v11;
    if ( v11 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      v5 = 0;
      goto LABEL_24;
    }
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\tokenbrokerhelperfactory.cpp",
      (const char *)(unsigned int)v11,
      v23);
LABEL_11:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF8,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\tokenbrokerhelperfactory.cpp",
    (const char *)(unsigned int)v4,
    v23);
LABEL_24:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  return v5;
}

```

## disassembly

```asm
0x18004d2bc  mov     [rsp-8+arg_8], rbx
0x18004d2c1  mov     [rsp-8+arg_10], rsi
0x18004d2c6  push    rbp
0x18004d2c7  push    rdi
0x18004d2c8  push    r14
0x18004d2ca  lea     rbp, [rsp-47h]
0x18004d2cf  sub     rsp, 90h
0x18004d2d6  mov     rax, cs:__security_cookie
0x18004d2dd  xor     rax, rsp
0x18004d2e0  mov     [rbp+57h+var_18], rax
0x18004d2e4  mov     rsi, rcx
0x18004d2e7  xor     r14d, r14d
0x18004d2ea  mov     [rbp+57h+var_40], r14
0x18004d2ee  mov     rax, [rcx]
0x18004d2f1  mov     rdi, [rax+60h]
0x18004d2f5  mov     rax, [rdi]
0x18004d2f8  mov     rbx, [rax+48h]
0x18004d2fc  lea     rcx, [rbp+57h+var_40]
0x18004d300  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d305  lea     r9, [rbp+57h+var_40]
0x18004d309  mov     r8, [rsi+10h]
0x18004d30d  mov     rdx, [rsi+8]
0x18004d311  mov     rcx, rdi
0x18004d314  mov     rax, rbx
0x18004d317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d31c  mov     ebx, eax
0x18004d31e  test    eax, eax
0x18004d320  jns     short loc_18004D33F
0x18004d322  mov     rcx, [rbp+5Fh]; this
0x18004d326  mov     r9d, eax; char *
0x18004d329  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004d330  mov     edx, 0F8h; void *
0x18004d335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d33a  jmp     loc_18004D5B1
0x18004d33f  mov     [rbp+57h+var_50], r14
0x18004d343  lea     rdx, [rbp+57h+var_50]
0x18004d347  lea     rcx, [rbp+57h+var_40]
0x18004d34b  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x18004d350  mov     ebx, eax
0x18004d352  test    eax, eax
0x18004d354  jns     short loc_18004D37D
0x18004d356  mov     rcx, [rbp+5Fh]; this
0x18004d35a  mov     r9d, eax; char *
0x18004d35d  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004d364  mov     edx, 0F8h; void *
0x18004d369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d36e  nop
0x18004d36f  lea     rcx, [rbp+57h+var_50]
0x18004d373  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d378  jmp     loc_18004D5B1
0x18004d37d  mov     [rbp+57h+var_60], r14
0x18004d381  mov     rdi, [rbp+57h+var_50]
0x18004d385  mov     rax, [rdi]
0x18004d388  mov     rbx, [rax+38h]
0x18004d38c  lea     rcx, [rbp+57h+var_60]
0x18004d390  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d395  lea     rdx, [rbp+57h+var_60]
0x18004d399  mov     rcx, rdi
0x18004d39c  mov     rax, rbx
0x18004d39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3a4  mov     ebx, eax
0x18004d3a6  test    eax, eax
0x18004d3a8  jns     short loc_18004D3CE
0x18004d3aa  mov     rcx, [rbp+5Fh]; this
0x18004d3ae  mov     r9d, eax; char *
0x18004d3b1  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004d3b8  mov     edx, 0F8h; void *
0x18004d3bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d3c2  nop
0x18004d3c3  lea     rcx, [rbp+57h+var_60]
0x18004d3c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d3cc  jmp     short loc_18004D36F
0x18004d3ce  mov     [rbp+57h+var_68], r14
0x18004d3d2  lea     rcx, [rbp+57h+var_68]
0x18004d3d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d3db  lea     rdx, [rbp+57h+var_68]
0x18004d3df  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x18004d3e4  mov     ebx, eax
0x18004d3e6  test    eax, eax
0x18004d3e8  jns     short loc_18004D40E
0x18004d3ea  mov     rcx, [rbp+5Fh]; this
0x18004d3ee  mov     r9d, eax; char *
0x18004d3f1  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004d3f8  mov     edx, 0F8h; void *
0x18004d3fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d402  nop
0x18004d403  lea     rcx, [rbp+57h+var_68]
0x18004d407  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d40c  jmp     short loc_18004D3C3
0x18004d40e  mov     [rbp+57h+var_70], r14b
0x18004d412  mov     rdi, [rbp+57h+var_60]
0x18004d416  mov     rax, [rdi]
0x18004d419  mov     rbx, [rax+40h]
0x18004d41d  lea     rdx, off_180089090; "Authority"
0x18004d424  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004d428  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18004d42d  nop
0x18004d42e  lea     r8, [rbp+57h+var_70]
0x18004d432  mov     rdx, [rax+18h]
0x18004d436  mov     rcx, rdi
0x18004d439  mov     rax, rbx
0x18004d43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d441  mov     ebx, eax
0x18004d443  test    eax, eax
0x18004d445  js      short loc_18004D3EA
0x18004d447  cmp     [rbp+57h+var_70], r14b
0x18004d44b  jz      loc_18004D56A
0x18004d451  mov     [rbp+57h+string], r14
0x18004d455  mov     rdi, [rbp+57h+var_60]
0x18004d459  mov     rax, [rdi]
0x18004d45c  mov     rbx, [rax+30h]
0x18004d460  xor     ecx, ecx; string
0x18004d462  call    cs:__imp_WindowsDeleteString
0x18004d468  mov     [rbp+57h+string], r14
0x18004d46c  lea     rdx, off_180089090; "Authority"
0x18004d473  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004d477  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18004d47c  nop
0x18004d47d  lea     r8, [rbp+57h+string]
0x18004d481  mov     rdx, [rax+18h]
0x18004d485  mov     rcx, rdi
0x18004d488  mov     rax, rbx
0x18004d48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d490  mov     ebx, eax
0x18004d492  test    eax, eax
0x18004d494  jns     short loc_18004D4C2
0x18004d496  mov     rcx, [rbp+5Fh]; this
0x18004d49a  mov     r9d, eax; char *
0x18004d49d  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004d4a4  mov     edx, 0F8h; void *
0x18004d4a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d4ae  nop
0x18004d4af  mov     rcx, [rbp+57h+string]; string
0x18004d4b3  call    cs:__imp_WindowsDeleteString
0x18004d4b9  mov     [rbp+57h+string], r14
0x18004d4bd  jmp     loc_18004D403
0x18004d4c2  mov     rcx, [rbp+57h+var_68]
0x18004d4c6  mov     rax, [rcx]
0x18004d4c9  mov     rdx, [rbp+57h+string]
0x18004d4cd  mov     rax, [rax+68h]
0x18004d4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4d6  mov     ebx, eax
0x18004d4d8  test    eax, eax
0x18004d4da  js      short loc_18004D496
0x18004d4dc  mov     [rbp+57h+var_48], r14
0x18004d4e0  mov     rdi, [rbp+57h+var_40]
0x18004d4e4  mov     rax, [rdi]
0x18004d4e7  mov     rbx, [rax+38h]
0x18004d4eb  xor     ecx, ecx; string
0x18004d4ed  call    cs:__imp_WindowsDeleteString
0x18004d4f3  mov     [rbp+57h+var_48], r14
0x18004d4f7  lea     rdx, [rbp+57h+var_48]
0x18004d4fb  mov     rcx, rdi
0x18004d4fe  mov     rax, rbx
0x18004d501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d506  mov     ebx, eax
0x18004d508  test    eax, eax
0x18004d50a  jns     short loc_18004D538
0x18004d50c  mov     rcx, [rbp+5Fh]; this
0x18004d510  mov     r9d, eax; char *
0x18004d513  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004d51a  mov     edx, 0F8h; void *
0x18004d51f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d524  nop
0x18004d525  mov     rcx, [rbp+57h+var_48]; string
0x18004d529  call    cs:__imp_WindowsDeleteString
0x18004d52f  mov     [rbp+57h+var_48], r14
0x18004d533  jmp     loc_18004D4AF
0x18004d538  mov     rcx, [rbp+57h+var_68]
0x18004d53c  mov     rax, [rcx]
0x18004d53f  mov     rdx, [rbp+57h+var_48]
0x18004d543  mov     rax, [rax+68h]
0x18004d547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d54c  mov     ebx, eax
0x18004d54e  test    eax, eax
0x18004d550  js      short loc_18004D50C
0x18004d552  mov     rcx, [rbp+57h+var_48]; string
0x18004d556  call    cs:__imp_WindowsDeleteString
0x18004d55c  mov     [rbp+57h+var_48], r14
0x18004d560  mov     rcx, [rbp+57h+string]; string
0x18004d564  call    cs:__imp_WindowsDeleteString
0x18004d56a  mov     rax, [rsi+18h]
0x18004d56e  mov     r8, [rax]
0x18004d571  mov     rcx, [rbp+57h+var_68]
0x18004d575  mov     rax, [rcx]
0x18004d578  lea     rdx, _GUID_98b9acc1_4b56_532e_ac73_03d5291cca90
0x18004d57f  mov     rax, [rax]
0x18004d582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d587  mov     ebx, eax
0x18004d589  test    eax, eax
0x18004d58b  js      loc_18004D3EA
0x18004d591  lea     rcx, [rbp+57h+var_68]
0x18004d595  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d59a  nop
0x18004d59b  lea     rcx, [rbp+57h+var_60]
0x18004d59f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d5a4  nop
0x18004d5a5  lea     rcx, [rbp+57h+var_50]
0x18004d5a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d5ae  mov     ebx, r14d
0x18004d5b1  lea     rcx, [rbp+57h+var_40]
0x18004d5b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d5ba  mov     eax, ebx
0x18004d5bc  mov     rcx, [rbp+57h+var_18]
0x18004d5c0  xor     rcx, rsp; StackCookie
0x18004d5c3  call    __security_check_cookie
0x18004d5c8  lea     r11, [rsp+0A0h+var_10]
0x18004d5d0  mov     rbx, [r11+28h]
0x18004d5d4  mov     rsi, [r11+30h]
0x18004d5d8  mov     rsp, r11
0x18004d5db  pop     r14
0x18004d5dd  pop     rdi
0x18004d5de  pop     rbp
0x18004d5df  retn
```
