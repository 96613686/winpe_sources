# ContentManagement::AppManager::ConvertFromStoreRecords(Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *> *,Windows::Foundation::Collections::IVectorView<ContentManagement::AppInstallInfoRecord *> * *)

- ea: `0x180311b7c`
- end: `0x180311e66`
- name: `?ConvertFromStoreRecords@AppManager@ContentManagement@@AEAAJPEAU?$IVectorView@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@PEAPEAU?$IVectorView@PEAVAppInstallInfoRecord@ContentManagement@@@456@@Z`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1803136b0`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1801e6adc`
- `0x18020e780`
- `0x18020ecf0`
- `0x18021a0c0`
- `0x18021a120`
- `0x180311b7c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311d48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311df6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311d48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311df6`

## string_xrefs

- `0x180311bea`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`
- `0x180311d8a`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`
- `0x180311db5`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`
- `0x180311de0`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`
- `0x180311e09`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ContentManagement::AppManager::ConvertFromStoreRecords(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int i; // esi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  HSTRING string; // [rsp+20h] [rbp-20h] BYREF
  __int64 v23; // [rsp+28h] [rbp-18h] BYREF
  __int64 v24; // [rsp+30h] [rbp-10h] BYREF
  __int64 v25; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  __int64 v27; // [rsp+80h] [rbp+40h] BYREF
  int v28; // [rsp+90h] [rbp+50h] BYREF
  HSTRING v29; // [rsp+98h] [rbp+58h] BYREF

  v27 = a1;
  *a3 = 0;
  v25 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  v6 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<ContentManagement::AppInstallInfoRecord,Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>>(
         v5,
         &v25);
  v7 = v6;
  if ( v6 >= 0 )
  {
    LODWORD(v27) = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 56LL))(a2, &v27);
    v7 = v6;
    if ( v6 >= 0 )
    {
      for ( i = 0; i < (unsigned int)v27; ++i )
      {
        v23 = 0;
        v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        v11 = v10(a2, i, &v23);
        v7 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B8,
            (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
            (const char *)(unsigned int)v11,
            (int)string);
          goto LABEL_29;
        }
        v29 = 0;
        v12 = v23;
        v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 48LL);
        WindowsDeleteString(0);
        v29 = 0;
        v14 = v13(v12, &v29);
        v7 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BB,
            (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
            (const char *)(unsigned int)v14,
            (int)string);
          goto LABEL_27;
        }
        string = 0;
        v15 = v23;
        v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 96LL);
        WindowsDeleteString(0);
        string = 0;
        v17 = v16(v15, &string);
        v7 = v17;
        if ( v17 < 0 )
        {
          v20 = 446;
          goto LABEL_24;
        }
        v28 = 0;
        v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 120LL))(v23, &v28);
        v7 = v17;
        if ( v17 < 0 )
        {
          v20 = 449;
LABEL_24:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
            (const char *)(unsigned int)v17,
            (int)string);
          goto LABEL_25;
        }
        v24 = 0;
        v18 = Microsoft::WRL::Details::MakeAndInitialize<ContentManagement::AppInstallInfoRecordImpl,ContentManagement::AppInstallInfoRecordImpl,>(&v24);
        v7 = v18;
        if ( v18 < 0 )
        {
          v19 = 452;
LABEL_21:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
            (const char *)(unsigned int)v18,
            (int)string);
          Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(&v24);
LABEL_25:
          WindowsDeleteString(string);
          string = 0;
LABEL_27:
          WindowsDeleteString(v29);
          v29 = 0;
LABEL_29:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
          goto LABEL_33;
        }
        v18 = ContentManagement::AppInstallInfoRecordImpl::put_ProductId(
                (ContentManagement::AppInstallInfoRecordImpl *)(v24 + 48),
                v29);
        v7 = v18;
        if ( v18 < 0 )
        {
          v19 = 453;
          goto LABEL_21;
        }
        v18 = ContentManagement::AppInstallInfoRecordImpl::put_SkuId(
                (ContentManagement::AppInstallInfoRecordImpl *)(v24 + 48),
                string);
        v7 = v18;
        if ( v18 < 0 )
        {
          v19 = 454;
          goto LABEL_21;
        }
        *(_DWORD *)(v24 + 104) = v28;
        v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 104LL))(
                v25,
                (v24 + 48) & -(__int64)(v24 != 0));
        v7 = v18;
        if ( v18 < 0 )
        {
          v19 = 457;
          goto LABEL_21;
        }
        Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(&v24);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v29);
        v29 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      }
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v25 + 64LL))(v25, a3);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v7 = 0;
        goto LABEL_33;
      }
      v8 = 460;
    }
    else
    {
      v8 = 436;
    }
  }
  else
  {
    v8 = 433;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
    (const char *)(unsigned int)v6,
    (int)string);
LABEL_33:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  return v7;
}

```

## disassembly

```asm
0x180311b7c  mov     [rsp-38h+arg_0], rcx
0x180311b81  push    rbp
0x180311b82  push    rbx
0x180311b83  push    rsi
0x180311b84  push    rdi
0x180311b85  push    r12
0x180311b87  push    r14
0x180311b89  push    r15
0x180311b8b  mov     rbp, rsp
0x180311b8e  sub     rsp, 40h
0x180311b92  mov     r15, r8
0x180311b95  mov     r14, rdx
0x180311b98  xor     r12d, r12d
0x180311b9b  mov     [r8], r12
0x180311b9e  mov     [rbp+var_8], r12
0x180311ba2  lea     rcx, [rbp+var_8]
0x180311ba6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180311bab  lea     rdx, [rbp+var_8]
0x180311baf  call    ??$CreateExternalObjectVector@VAppInstallInfoRecord@ContentManagement@@V?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<ContentManagement::AppInstallInfoRecord,Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0> * *)
0x180311bb4  mov     ebx, eax
0x180311bb6  test    eax, eax
0x180311bb8  jns     short loc_180311BC1
0x180311bba  mov     edx, 1B1h
0x180311bbf  jmp     short loc_180311BE3
0x180311bc1  mov     dword ptr [rbp+arg_0], r12d
0x180311bc5  mov     rax, [r14]
0x180311bc8  lea     rdx, [rbp+arg_0]
0x180311bcc  mov     rcx, r14
0x180311bcf  mov     rax, [rax+38h]
0x180311bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311bd8  mov     ebx, eax
0x180311bda  test    eax, eax
0x180311bdc  jns     short loc_180311BFB
0x180311bde  mov     edx, 1B4h; void *
0x180311be3  mov     rcx, [rbp+38h]; this
0x180311be7  mov     r9d, eax; char *
0x180311bea  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x180311bf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180311bf6  jmp     loc_180311E4C
0x180311bfb  mov     esi, r12d
0x180311bfe  cmp     esi, dword ptr [rbp+arg_0]
0x180311c01  jnb     loc_180311E26
0x180311c07  mov     [rbp+var_18], r12
0x180311c0b  mov     rax, [r14]
0x180311c0e  mov     rbx, [rax+30h]
0x180311c12  lea     rcx, [rbp+var_18]
0x180311c16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180311c1b  lea     r8, [rbp+var_18]
0x180311c1f  mov     edx, esi
0x180311c21  mov     rcx, r14
0x180311c24  mov     rax, rbx
0x180311c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311c2c  mov     ebx, eax
0x180311c2e  test    eax, eax
0x180311c30  js      loc_180311E02
0x180311c36  mov     [rbp+arg_18], r12
0x180311c3a  mov     rdi, [rbp+var_18]
0x180311c3e  mov     rax, [rdi]
0x180311c41  mov     rbx, [rax+30h]
0x180311c45  xor     ecx, ecx; string
0x180311c47  call    cs:__imp_WindowsDeleteString
0x180311c4d  mov     [rbp+arg_18], r12
0x180311c51  lea     rdx, [rbp+arg_18]
0x180311c55  mov     rcx, rdi
0x180311c58  mov     rax, rbx
0x180311c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311c60  mov     ebx, eax
0x180311c62  test    eax, eax
0x180311c64  js      loc_180311DD9
0x180311c6a  mov     [rbp+string], r12
0x180311c6e  mov     rdi, [rbp+var_18]
0x180311c72  mov     rax, [rdi]
0x180311c75  mov     rbx, [rax+60h]
0x180311c79  xor     ecx, ecx; string
0x180311c7b  call    cs:__imp_WindowsDeleteString
0x180311c81  mov     [rbp+string], r12
0x180311c85  lea     rdx, [rbp+string]
0x180311c89  mov     rcx, rdi
0x180311c8c  mov     rax, rbx
0x180311c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311c94  mov     ebx, eax
0x180311c96  test    eax, eax
0x180311c98  js      loc_180311DB0
0x180311c9e  mov     [rbp+arg_10], r12d
0x180311ca2  mov     rcx, [rbp+var_18]
0x180311ca6  mov     rax, [rcx]
0x180311ca9  lea     rdx, [rbp+arg_10]
0x180311cad  mov     rax, [rax+78h]
0x180311cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311cb6  mov     ebx, eax
0x180311cb8  test    eax, eax
0x180311cba  js      loc_180311DA9
0x180311cc0  mov     [rbp+var_10], r12
0x180311cc4  lea     rcx, [rbp+var_10]
0x180311cc8  call    ??$MakeAndInitialize@VAppInstallInfoRecordImpl@ContentManagement@@V12@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppInstallInfoRecordImpl@ContentManagement@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<ContentManagement::AppInstallInfoRecordImpl,ContentManagement::AppInstallInfoRecordImpl,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>>)
0x180311ccd  mov     ebx, eax
0x180311ccf  test    eax, eax
0x180311cd1  js      loc_180311D85
0x180311cd7  mov     rcx, [rbp+var_10]
0x180311cdb  add     rcx, 30h ; '0'; this
0x180311cdf  mov     rdx, [rbp+arg_18]; HSTRING
0x180311ce3  call    ?put_ProductId@AppInstallInfoRecordImpl@ContentManagement@@UEAAJPEAUHSTRING__@@@Z; ContentManagement::AppInstallInfoRecordImpl::put_ProductId(HSTRING__ *)
0x180311ce8  mov     ebx, eax
0x180311cea  test    eax, eax
0x180311cec  js      loc_180311D7E
0x180311cf2  mov     rcx, [rbp+var_10]
0x180311cf6  add     rcx, 30h ; '0'; this
0x180311cfa  mov     rdx, [rbp+string]; HSTRING
0x180311cfe  call    ?put_SkuId@AppInstallInfoRecordImpl@ContentManagement@@UEAAJPEAUHSTRING__@@@Z; ContentManagement::AppInstallInfoRecordImpl::put_SkuId(HSTRING__ *)
0x180311d03  mov     ebx, eax
0x180311d05  test    eax, eax
0x180311d07  js      short loc_180311D77
0x180311d09  mov     ecx, [rbp+arg_10]
0x180311d0c  mov     rax, [rbp+var_10]
0x180311d10  mov     [rax+68h], ecx
0x180311d13  mov     rcx, [rbp+var_8]
0x180311d17  mov     rdx, [rbp+var_10]
0x180311d1b  mov     r8, [rcx]
0x180311d1e  lea     rax, [rdx+30h]
0x180311d22  neg     rdx
0x180311d25  sbb     rdx, rdx
0x180311d28  and     rdx, rax
0x180311d2b  mov     rax, [r8+68h]
0x180311d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311d34  mov     ebx, eax
0x180311d36  test    eax, eax
0x180311d38  js      short loc_180311D70
0x180311d3a  lea     rcx, [rbp+var_10]
0x180311d3e  call    ?InternalRelease@?$ComPtr@VAppInstallInfoRecordImpl@ContentManagement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(void)
0x180311d43  nop
0x180311d44  mov     rcx, [rbp+string]; string
0x180311d48  call    cs:__imp_WindowsDeleteString
0x180311d4e  mov     [rbp+string], r12
0x180311d52  mov     rcx, [rbp+arg_18]; string
0x180311d56  call    cs:__imp_WindowsDeleteString
0x180311d5c  mov     [rbp+arg_18], r12
0x180311d60  lea     rcx, [rbp+var_18]
0x180311d64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180311d69  inc     esi
0x180311d6b  jmp     loc_180311BFE
0x180311d70  mov     edx, 1C9h
0x180311d75  jmp     short loc_180311D8A
0x180311d77  mov     edx, 1C6h
0x180311d7c  jmp     short loc_180311D8A
0x180311d7e  mov     edx, 1C5h
0x180311d83  jmp     short loc_180311D8A
0x180311d85  mov     edx, 1C4h; void *
0x180311d8a  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x180311d91  mov     r9d, eax; char *
0x180311d94  mov     rcx, [rbp+38h]; this
0x180311d98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180311d9d  nop
0x180311d9e  lea     rcx, [rbp+var_10]
0x180311da2  call    ?InternalRelease@?$ComPtr@VAppInstallInfoRecordImpl@ContentManagement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ContentManagement::AppInstallInfoRecordImpl>::InternalRelease(void)
0x180311da7  jmp     short loc_180311DC9
0x180311da9  mov     edx, 1C1h
0x180311dae  jmp     short loc_180311DB5
0x180311db0  mov     edx, 1BEh; void *
0x180311db5  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x180311dbc  mov     r9d, eax; char *
0x180311dbf  mov     rcx, [rbp+38h]; this
0x180311dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180311dc8  nop
0x180311dc9  mov     rcx, [rbp+string]; string
0x180311dcd  call    cs:__imp_WindowsDeleteString
0x180311dd3  mov     [rbp+string], r12
0x180311dd7  jmp     short loc_180311DF2
0x180311dd9  mov     rcx, [rbp+38h]; this
0x180311ddd  mov     r9d, eax; char *
0x180311de0  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x180311de7  mov     edx, 1BBh; void *
0x180311dec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180311df1  nop
0x180311df2  mov     rcx, [rbp+arg_18]; string
0x180311df6  call    cs:__imp_WindowsDeleteString
0x180311dfc  mov     [rbp+arg_18], r12
0x180311e00  jmp     short loc_180311E1B
0x180311e02  mov     rcx, [rbp+38h]; this
0x180311e06  mov     r9d, eax; char *
0x180311e09  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x180311e10  mov     edx, 1B8h; void *
0x180311e15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180311e1a  nop
0x180311e1b  lea     rcx, [rbp+var_18]
0x180311e1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180311e24  jmp     short loc_180311E4C
0x180311e26  mov     rcx, [rbp+var_8]
0x180311e2a  mov     rax, [rcx]
0x180311e2d  mov     rdx, r15
0x180311e30  mov     rax, [rax+40h]
0x180311e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311e39  mov     ebx, eax
0x180311e3b  test    eax, eax
0x180311e3d  jns     short loc_180311E49
0x180311e3f  mov     edx, 1CCh
0x180311e44  jmp     loc_180311BE3
0x180311e49  mov     ebx, r12d
0x180311e4c  lea     rcx, [rbp+var_8]
0x180311e50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180311e55  mov     eax, ebx
0x180311e57  add     rsp, 40h
0x180311e5b  pop     r15
0x180311e5d  pop     r14
0x180311e5f  pop     r12
0x180311e61  pop     rdi
0x180311e62  pop     rsi
0x180311e63  pop     rbx
0x180311e64  pop     rbp
0x180311e65  retn
```
