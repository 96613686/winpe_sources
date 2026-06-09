# PopulateAllowedF12ExtensionsPaths(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18001d7a0`
- end: `0x18001dbe3`
- name: `?PopulateAllowedF12ExtensionsPaths@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `1091`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180002ce0`
- `0x180003170`
- `0x180007018`
- `0x18000a4d0`
- `0x18001bf70`
- `0x18001c0f4`
- `0x18001c308`
- `0x18001c374`
- `0x18001c6f0`
- `0x18001ca74`
- `0x18001d7a0`
- `0x18001e7f0`
- `0x18001e800`
- `0x18001e8c4`
- `0x18001e924`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18001dad3`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18001dad3`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x18001dae5`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x18001dae5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d801`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001da84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001da84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d9bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dabc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d9bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dabc`

## string_xrefs

- `0x18001d833`: `com.microsoft.edge.f12`
- `0x18001d7d6`: `Windows.ApplicationModel.AppExtensions.AppExtensionCatalog`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall PopulateAllowedF12ExtensionsPaths(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  unsigned int v3; // r14d
  HSTRING_HEADER *v4; // rax
  __int64 v5; // rdi
  int (__fastcall *v6)(__int64, __int64, const WCHAR **); // rbx
  const WCHAR *v7; // rdi
  int (__fastcall *v8)(const WCHAR *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rbx
  DWORD v10; // edx
  int v11; // r8d
  int v12; // eax
  unsigned int i; // esi
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  __int64 v16; // rdi
  int (__fastcall *v17)(__int64, __int64 *); // rbx
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, __int64 *); // rbx
  __int64 v20; // rdi
  int (__fastcall *v21)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rbx
  __int64 v25; // rdx
  char v26; // al
  const wchar_t *v27; // rdx
  const wchar_t *v28; // rcx
  size_t v29; // r8
  int (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v31)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v32; // rdi
  int (__fastcall *v33)(__int64, HSTRING *); // rbx
  void *v34; // rbx
  const WCHAR *v35; // rax
  HSTRING string; // [rsp+20h] [rbp-69h] BYREF
  __int64 v38; // [rsp+28h] [rbp-61h] BYREF
  __int64 v39; // [rsp+30h] [rbp-59h] BYREF
  __int64 v40; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v41; // [rsp+40h] [rbp-49h] BYREF
  HSTRING v42; // [rsp+48h] [rbp-41h] BYREF
  __int64 v43; // [rsp+50h] [rbp-39h] BYREF
  int (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-31h] BYREF
  const WCHAR *v45; // [rsp+60h] [rbp-29h] BYREF
  __int64 v46; // [rsp+68h] [rbp-21h] BYREF
  __int64 v47; // [rsp+70h] [rbp-19h] BYREF
  __int64 (__fastcall ***v48)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-11h] BYREF
  void *v49; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  __int64 v51; // [rsp+A0h] [rbp+17h]

  v3 = 0;
  v47 = 0;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v47);
  v45 = L"Windows.ApplicationModel.AppExtensions.AppExtensionCatalog";
  v47 = 0;
  v4 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v45);
  if ( (int)RoGetActivationFactory(v4[1].Reserved.Reserved1, &GUID_3c36668a_5f18_4f0b_9ce5_cab61d196f11, &v47) >= 0 )
  {
    v45 = 0;
    v5 = v47;
    v6 = *(int (__fastcall **)(__int64, __int64, const WCHAR **))(*(_QWORD *)v47 + 48LL);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v45);
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"com.microsoft.edge.f12", 0x17u, 0x16u);
    if ( v6(v5, v51, &v45) >= 0 )
    {
      v48 = 0;
      v7 = v45;
      v8 = *(int (__fastcall **)(const WCHAR *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v45 + 48LL);
      Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v48);
      if ( v8(v7, &v48) >= 0 )
      {
        v46 = 0;
        Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v46);
        v9 = v48;
        v12 = wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(
                v48,
                v10,
                v11);
        if ( v12 >= 0 )
          v12 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v9)[8])(
                  v9,
                  &v46);
        if ( v12 >= 0 )
        {
          v41 = 0;
          if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 56LL))(v46, &v41) >= 0 )
          {
            for ( i = 0; i < v41; ++i )
            {
              v39 = 0;
              v14 = v46;
              v15 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v46 + 48LL);
              Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v39);
              if ( v15(v14, i, &v39) >= 0 )
              {
                v38 = 0;
                v16 = v39;
                v17 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 72LL);
                Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v38);
                if ( v17(v16, &v38) >= 0 )
                {
                  v40 = 0;
                  v18 = v38;
                  v19 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL);
                  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v40);
                  if ( v19(v18, &v40) >= 0 )
                  {
                    string = 0;
                    v20 = v40;
                    v21 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 88LL);
                    WindowsDeleteString(0);
                    string = 0;
                    if ( v21(v20, &string) >= 0 )
                    {
                      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                      v23 = std::_WChar_traits<unsigned short>::length(StringRawBuffer, StringRawBuffer);
                      v24 = qword_18003FD40;
                      v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(&S1, v25);
                      v28 = (const wchar_t *)&S1;
                      if ( v26 )
                        v28 = S1;
                      v29 = v24;
                      if ( v23 < v24 )
                        v29 = v23;
                      if ( !std::_WChar_traits<unsigned short>::compare(v28, v27, v29) && v24 >= v23 && v24 <= v23 )
                      {
                        v44 = 0;
                        if ( (*(int (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v38 + 56LL))(
                               v38,
                               &v44) >= 0 )
                        {
                          v43 = 0;
                          v30 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
                          v31 = **v44;
                          Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v43);
                          if ( v31(v30, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v43) >= 0 )
                          {
                            v42 = 0;
                            v32 = v43;
                            v33 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 96LL);
                            WindowsDeleteString(0);
                            v42 = 0;
                            if ( v33(v32, &v42) >= 0 )
                            {
                              v34 = operator new[](0x10000u);
                              v49 = v34;
                              v35 = WindowsGetStringRawBuffer(v42, 0);
                              if ( PathCchCanonicalizeEx((PWSTR)v34, 0x8000u, v35, 0x21u) >= 0
                                && PathCchStripPrefix((PWSTR)v34, 0x8000u) >= 0 )
                              {
                                std::wstring::wstring(&hstringHeader, v34);
                                if ( *((_QWORD *)&LocalFileBroker::s_f12AllowedPaths + 1) == qword_18003FD28 )
                                {
                                  std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(
                                    *((_QWORD *)&LocalFileBroker::s_f12AllowedPaths + 1),
                                    *((_QWORD *)&LocalFileBroker::s_f12AllowedPaths + 1),
                                    &hstringHeader);
                                }
                                else
                                {
                                  std::_Construct_in_place<std::wstring,std::wstring>(
                                    *((_QWORD *)&LocalFileBroker::s_f12AllowedPaths + 1),
                                    &hstringHeader);
                                  *((_QWORD *)&LocalFileBroker::s_f12AllowedPaths + 1) += 32LL;
                                }
                                std::wstring::_Tidy_deallocate(&hstringHeader);
                                v3 = 1;
                              }
                              std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v49);
                            }
                            WindowsDeleteString(v42);
                            v42 = 0;
                          }
                          Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v43);
                        }
                        Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v44);
                      }
                    }
                    WindowsDeleteString(string);
                    string = 0;
                  }
                  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v40);
                }
                Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v38);
              }
              Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v39);
            }
          }
        }
        Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v46);
      }
      Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v48);
    }
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v45);
  }
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v47);
  return v3;
}

```

## disassembly

```asm
0x18001d7a0  push    rbp
0x18001d7a2  push    rbx
0x18001d7a3  push    rsi
0x18001d7a4  push    rdi
0x18001d7a5  push    r14
0x18001d7a7  push    r15
0x18001d7a9  lea     rbp, [rsp-2Fh]
0x18001d7ae  sub     rsp, 0B8h
0x18001d7b5  mov     rax, cs:__security_cookie
0x18001d7bc  xor     rax, rsp
0x18001d7bf  mov     [rbp+57h+var_38], rax
0x18001d7c3  xor     r15d, r15d
0x18001d7c6  mov     r14d, r15d
0x18001d7c9  mov     [rbp+57h+var_70], r15
0x18001d7cd  lea     rcx, [rbp+57h+var_70]
0x18001d7d1  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001d7d6  lea     rax, ?RuntimeClass_Windows_ApplicationModel_AppExtensions_AppExtensionCatalog@@3QBGB; "Windows.ApplicationModel.AppExtensions."...
0x18001d7dd  mov     [rbp+57h+var_80], rax
0x18001d7e1  mov     [rbp+57h+var_70], r15
0x18001d7e5  lea     rdx, [rbp+57h+var_80]
0x18001d7e9  lea     rcx, [rbp+57h+hstringHeader]
0x18001d7ed  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d7f2  lea     r8, [rbp+57h+var_70]
0x18001d7f6  lea     rdx, _GUID_3c36668a_5f18_4f0b_9ce5_cab61d196f11
0x18001d7fd  mov     rcx, [rax+18h]
0x18001d801  call    cs:__imp_RoGetActivationFactory
0x18001d807  test    eax, eax
0x18001d809  js      loc_18001DBBB
0x18001d80f  mov     [rbp+57h+var_80], r15
0x18001d813  mov     rdi, [rbp+57h+var_70]
0x18001d817  mov     rax, [rdi]
0x18001d81a  mov     rbx, [rax+30h]
0x18001d81e  lea     rcx, [rbp+57h+var_80]
0x18001d822  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001d827  mov     [rbp+57h+var_40], r15
0x18001d82b  lea     r9d, [r15+16h]; unsigned int
0x18001d82f  lea     r8d, [r15+17h]; unsigned int
0x18001d833  lea     rdx, sourceString; "com.microsoft.edge.f12"
0x18001d83a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001d83e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d843  nop
0x18001d844  lea     r8, [rbp+57h+var_80]
0x18001d848  mov     rdx, [rbp+57h+var_40]
0x18001d84c  mov     rcx, rdi
0x18001d84f  mov     rax, rbx
0x18001d852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d857  nop
0x18001d858  shr     eax, 1Fh
0x18001d85b  xor     al, 1
0x18001d85d  jz      loc_18001DBB1
0x18001d863  mov     [rbp+57h+var_68], r15
0x18001d867  mov     rdi, [rbp+57h+var_80]
0x18001d86b  mov     rax, [rdi]
0x18001d86e  mov     rbx, [rax+30h]
0x18001d872  lea     rcx, [rbp+57h+var_68]
0x18001d876  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001d87b  lea     rdx, [rbp+57h+var_68]
0x18001d87f  mov     rcx, rdi
0x18001d882  mov     rax, rbx
0x18001d885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d88a  test    eax, eax
0x18001d88c  js      loc_18001DBA7
0x18001d892  mov     [rbp+57h+var_78], r15
0x18001d896  lea     rcx, [rbp+57h+var_78]
0x18001d89a  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001d89f  mov     rbx, [rbp+57h+var_68]
0x18001d8a3  mov     rcx, rbx
0x18001d8a6  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18001d8ab  test    eax, eax
0x18001d8ad  js      short loc_18001D8C3
0x18001d8af  mov     rax, [rbx]
0x18001d8b2  lea     rdx, [rbp+57h+var_78]
0x18001d8b6  mov     rcx, rbx
0x18001d8b9  mov     rax, [rax+40h]
0x18001d8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8c2  nop
0x18001d8c3  test    eax, eax
0x18001d8c5  js      loc_18001DB9D
0x18001d8cb  mov     [rbp+57h+var_A0], r15d
0x18001d8cf  mov     rcx, [rbp+57h+var_78]
0x18001d8d3  mov     rax, [rcx]
0x18001d8d6  lea     rdx, [rbp+57h+var_A0]
0x18001d8da  mov     rax, [rax+38h]
0x18001d8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8e3  test    eax, eax
0x18001d8e5  js      loc_18001DB9D
0x18001d8eb  mov     esi, r15d
0x18001d8ee  cmp     [rbp+57h+var_A0], r15d
0x18001d8f2  jbe     loc_18001DB9D
0x18001d8f8  mov     [rbp+57h+var_B0], r15
0x18001d8fc  mov     rdi, [rbp+57h+var_78]
0x18001d900  mov     rax, [rdi]
0x18001d903  mov     rbx, [rax+30h]
0x18001d907  lea     rcx, [rbp+57h+var_B0]
0x18001d90b  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001d910  lea     r8, [rbp+57h+var_B0]
0x18001d914  mov     edx, esi
0x18001d916  mov     rcx, rdi
0x18001d919  mov     rax, rbx
0x18001d91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d921  test    eax, eax
0x18001d923  js      loc_18001DB89
0x18001d929  mov     [rbp+57h+var_B8], r15
0x18001d92d  mov     rdi, [rbp+57h+var_B0]
0x18001d931  mov     rax, [rdi]
0x18001d934  mov     rbx, [rax+48h]
0x18001d938  lea     rcx, [rbp+57h+var_B8]
0x18001d93c  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001d941  lea     rdx, [rbp+57h+var_B8]
0x18001d945  mov     rcx, rdi
0x18001d948  mov     rax, rbx
0x18001d94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d950  test    eax, eax
0x18001d952  js      loc_18001DB7F
0x18001d958  mov     [rbp+57h+var_A8], r15
0x18001d95c  mov     rdi, [rbp+57h+var_B8]
0x18001d960  mov     rax, [rdi]
0x18001d963  mov     rbx, [rax+30h]
0x18001d967  lea     rcx, [rbp+57h+var_A8]
0x18001d96b  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001d970  lea     rdx, [rbp+57h+var_A8]
0x18001d974  mov     rcx, rdi
0x18001d977  mov     rax, rbx
0x18001d97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d97f  test    eax, eax
0x18001d981  js      loc_18001DB75
0x18001d987  mov     [rbp+57h+string], r15
0x18001d98b  mov     rdi, [rbp+57h+var_A8]
0x18001d98f  mov     rax, [rdi]
0x18001d992  mov     rbx, [rax+58h]
0x18001d996  xor     ecx, ecx; string
0x18001d998  call    cs:__imp_WindowsDeleteString
0x18001d99e  mov     [rbp+57h+string], r15
0x18001d9a2  lea     rdx, [rbp+57h+string]
0x18001d9a6  mov     rcx, rdi
0x18001d9a9  mov     rax, rbx
0x18001d9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9b1  test    eax, eax
0x18001d9b3  js      loc_18001DB67
0x18001d9b9  xor     edx, edx; length
0x18001d9bb  mov     rcx, [rbp+57h+string]; string
0x18001d9bf  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d9c5  mov     rdx, rax
0x18001d9c8  mov     rcx, rax
0x18001d9cb  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001d9d0  mov     rdi, rax
0x18001d9d3  mov     rbx, cs:qword_18003FD40
0x18001d9da  lea     rcx, S1
0x18001d9e1  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x18001d9e6  lea     rcx, S1
0x18001d9ed  test    al, al
0x18001d9ef  cmovnz  rcx, cs:S1; S1
0x18001d9f7  mov     r8, rbx
0x18001d9fa  cmp     rdi, rbx
0x18001d9fd  cmovb   r8, rdi; N
0x18001da01  call    ?compare@?$_WChar_traits@G@std@@SAHQEBG0_K@Z; std::_WChar_traits<ushort>::compare(ushort const * const,ushort const * const,unsigned __int64)
0x18001da06  test    eax, eax
0x18001da08  jnz     loc_18001DB67
0x18001da0e  cmp     rbx, rdi
0x18001da11  jb      loc_18001DB67
0x18001da17  ja      loc_18001DB67
0x18001da1d  mov     [rbp+57h+var_88], r15
0x18001da21  mov     rcx, [rbp+57h+var_B8]
0x18001da25  mov     rax, [rcx]
0x18001da28  lea     rdx, [rbp+57h+var_88]
0x18001da2c  mov     rax, [rax+38h]
0x18001da30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da35  test    eax, eax
0x18001da37  js      loc_18001DB5D
0x18001da3d  mov     [rbp+57h+var_90], r15
0x18001da41  mov     rbx, [rbp+57h+var_88]
0x18001da45  mov     rax, [rbx]
0x18001da48  mov     rdi, [rax]
0x18001da4b  lea     rcx, [rbp+57h+var_90]
0x18001da4f  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001da54  lea     r8, [rbp+57h+var_90]
0x18001da58  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x18001da5f  mov     rcx, rbx
0x18001da62  mov     rax, rdi
0x18001da65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da6a  nop
0x18001da6b  test    eax, eax
0x18001da6d  js      loc_18001DB53
0x18001da73  mov     [rbp+57h+var_98], r15
0x18001da77  mov     rdi, [rbp+57h+var_90]
0x18001da7b  mov     rax, [rdi]
0x18001da7e  mov     rbx, [rax+60h]
0x18001da82  xor     ecx, ecx; string
0x18001da84  call    cs:__imp_WindowsDeleteString
0x18001da8a  mov     [rbp+57h+var_98], r15
0x18001da8e  lea     rdx, [rbp+57h+var_98]
0x18001da92  mov     rcx, rdi
0x18001da95  mov     rax, rbx
0x18001da98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da9d  test    eax, eax
0x18001da9f  js      loc_18001DB45
0x18001daa5  mov     ecx, 10000h; unsigned __int64
0x18001daaa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001daaf  mov     rbx, rax
0x18001dab2  mov     [rbp+57h+var_60], rax
0x18001dab6  xor     edx, edx; length
0x18001dab8  mov     rcx, [rbp+57h+var_98]; string
0x18001dabc  call    cs:__imp_WindowsGetStringRawBuffer
0x18001dac2  mov     r9d, 21h ; '!'; dwFlags
0x18001dac8  mov     r8, rax; pszPathIn
0x18001dacb  mov     edx, 8000h; cchPathOut
0x18001dad0  mov     rcx, rbx; pszPathOut
0x18001dad3  call    cs:__imp_PathCchCanonicalizeEx
0x18001dad9  test    eax, eax
0x18001dadb  js      short loc_18001DB3B
0x18001dadd  mov     edx, 8000h; cchPath
0x18001dae2  mov     rcx, rbx; pszPath
0x18001dae5  call    cs:__imp_PathCchStripPrefix
0x18001daeb  test    eax, eax
0x18001daed  js      short loc_18001DB3B
0x18001daef  mov     rdx, rbx
0x18001daf2  lea     rcx, [rbp+57h+hstringHeader]
0x18001daf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001dafb  nop
0x18001dafc  mov     rcx, qword ptr cs:?s_f12AllowedPaths@LocalFileBroker@@2V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A+8; std::vector<std::wstring> LocalFileBroker::s_f12AllowedPaths
0x18001db03  cmp     rcx, cs:qword_18003FD28
0x18001db0a  jz      short loc_18001DB1F
0x18001db0c  lea     rdx, [rbp+57h+hstringHeader]
0x18001db10  call    ??$_Construct_in_place@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@@Z; std::_Construct_in_place<std::wstring,std::wstring>(std::wstring &,std::wstring &&)
0x18001db15  add     qword ptr cs:?s_f12AllowedPaths@LocalFileBroker@@2V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A+8, 20h ; ' '; std::vector<std::wstring> LocalFileBroker::s_f12AllowedPaths
0x18001db1d  jmp     short loc_18001DB2C
0x18001db1f  lea     r8, [rbp+57h+hstringHeader]
0x18001db23  mov     rdx, rcx
0x18001db26  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18001db2b  nop
0x18001db2c  lea     rcx, [rbp+57h+hstringHeader]
0x18001db30  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001db35  mov     r14d, 1
0x18001db3b  lea     rcx, [rbp+57h+var_60]
0x18001db3f  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001db44  nop
0x18001db45  mov     rcx, [rbp+57h+var_98]; string
0x18001db49  call    cs:__imp_WindowsDeleteString
0x18001db4f  mov     [rbp+57h+var_98], r15
0x18001db53  lea     rcx, [rbp+57h+var_90]
0x18001db57  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001db5c  nop
0x18001db5d  lea     rcx, [rbp+57h+var_88]
0x18001db61  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001db66  nop
0x18001db67  mov     rcx, [rbp+57h+string]; string
0x18001db6b  call    cs:__imp_WindowsDeleteString
0x18001db71  mov     [rbp+57h+string], r15
0x18001db75  lea     rcx, [rbp+57h+var_A8]
0x18001db79  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001db7e  nop
0x18001db7f  lea     rcx, [rbp+57h+var_B8]
0x18001db83  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001db88  nop
0x18001db89  lea     rcx, [rbp+57h+var_B0]
0x18001db8d  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001db92  inc     esi
0x18001db94  cmp     esi, [rbp+57h+var_A0]
0x18001db97  jb      loc_18001D8F8
0x18001db9d  lea     rcx, [rbp+57h+var_78]
0x18001dba1  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001dba6  nop
0x18001dba7  lea     rcx, [rbp+57h+var_68]
0x18001dbab  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001dbb0  nop
0x18001dbb1  lea     rcx, [rbp+57h+var_80]
0x18001dbb5  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001dbba  nop
0x18001dbbb  lea     rcx, [rbp+57h+var_70]
0x18001dbbf  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001dbc4  mov     eax, r14d
0x18001dbc7  mov     rcx, [rbp+57h+var_38]
0x18001dbcb  xor     rcx, rsp; StackCookie
0x18001dbce  call    __security_check_cookie
0x18001dbd3  add     rsp, 0B8h
0x18001dbda  pop     r15
0x18001dbdc  pop     r14
0x18001dbde  pop     rdi
0x18001dbdf  pop     rsi
0x18001dbe0  pop     rbx
0x18001dbe1  pop     rbp
0x18001dbe2  retn
```
