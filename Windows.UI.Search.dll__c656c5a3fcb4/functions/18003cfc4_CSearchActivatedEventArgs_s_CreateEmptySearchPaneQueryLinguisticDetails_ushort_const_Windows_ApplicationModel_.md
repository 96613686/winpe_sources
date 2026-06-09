# CSearchActivatedEventArgs::s_CreateEmptySearchPaneQueryLinguisticDetails(ushort const *,Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails * *)

- ea: `0x18003cfc4`
- end: `0x18003d196`
- name: `?s_CreateEmptySearchPaneQueryLinguisticDetails@CSearchActivatedEventArgs@@CAJPEBGPEAPEAUISearchPaneQueryLinguisticDetails@Search@ApplicationModel@Windows@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(PCWSTR sourceString, struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ce14`

## callees

- `0x180007b3c`
- `0x180015ab8`
- `0x18001e758`
- `0x18001e9dc`
- `0x18003cfc4`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d024`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d0d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d024`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d0d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d00b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d0e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d00b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d0e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSearchActivatedEventArgs::s_CreateEmptySearchPaneQueryLinguisticDetails(
        PCWSTR sourceString,
        struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails **a2)
{
  int LinguisticDetails; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, HSTRING); // rdi
  unsigned __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, UINT32 *); // rbx
  UINT32 length[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v14; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF

  *a2 = 0;
  v16 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.ApplicationModel.Search.SearchQueryLinguisticDetails",
         0x3Cu,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  LinguisticDetails = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Search::ISearchQueryLinguisticDetailsFactory>>(
                        (__int64)string,
                        (__int64)&v16);
  if ( LinguisticDetails >= 0 )
  {
    v15 = 0;
    v5 = v16;
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v16 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
    LinguisticDetails = v6(v5, 0, 0, 0, &v15);
    if ( LinguisticDetails >= 0 )
    {
      v14 = 0;
      LinguisticDetails = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Search::ISearchQueryLinguisticDetails>::As<ISearchQueryLinguisticDetailsPriv>(
                            &v15,
                            (__int64)&v14);
      if ( LinguisticDetails >= 0 )
      {
        v7 = v14;
        v8 = *(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 24LL);
        length[0] = 0;
        v9 = -1;
        do
          ++v9;
        while ( sourceString[v9] );
        if ( (int)ULongLongToULong(v9, length) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        WindowsCreateStringReference(sourceString, length[0], &hstringHeader, &string);
        LinguisticDetails = v8(v7, string);
        if ( LinguisticDetails >= 0 )
        {
          *(_QWORD *)length = 0;
          v10 = v14;
          v11 = *(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v14 + 64LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(length);
          LinguisticDetails = v11(v10, length);
          if ( LinguisticDetails >= 0 )
            LinguisticDetails = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails **))length)(
                                  *(_QWORD *)length,
                                  &GUID_82fb460e_0940_4b6d_b8d0_642b30989e15,
                                  a2);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(length);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
  return (unsigned int)LinguisticDetails;
}

```

## disassembly

```asm
0x18003cfc4  mov     [rsp-28h+arg_10], rbx
0x18003cfc9  push    rbp
0x18003cfca  push    rsi
0x18003cfcb  push    rdi
0x18003cfcc  push    r14
0x18003cfce  push    r15
0x18003cfd0  mov     rbp, rsp
0x18003cfd3  sub     rsp, 80h
0x18003cfda  mov     rax, cs:__security_cookie
0x18003cfe1  xor     rax, rsp
0x18003cfe4  mov     [rbp+var_10], rax
0x18003cfe8  mov     r14, rdx
0x18003cfeb  mov     rsi, rcx
0x18003cfee  xor     r15d, r15d
0x18003cff1  mov     [rdx], r15
0x18003cff4  mov     [rbp+var_38], r15
0x18003cff8  lea     r9, [rbp+string]; string
0x18003cffc  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003d000  lea     edx, [r15+3Ch]; length
0x18003d004  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Search_SearchQueryLinguisticDetails@@3QBGB; "Windows.ApplicationModel.Search.SearchQ"...
0x18003d00b  call    cs:__imp_WindowsCreateStringReference
0x18003d011  test    eax, eax
0x18003d013  jns     short loc_18003D02A
0x18003d015  xor     r9d, r9d; lpArguments
0x18003d018  xor     r8d, r8d; nNumberOfArguments
0x18003d01b  lea     edx, [r15+1]; dwExceptionFlags
0x18003d01f  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003d024  call    cs:__imp_RaiseException
0x18003d02a  lea     rdx, [rbp+var_38]
0x18003d02e  mov     rcx, [rbp+string]
0x18003d032  call    ??$GetActivationFactory@V?$ComPtr@UISearchQueryLinguisticDetailsFactory@Search@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISearchQueryLinguisticDetailsFactory@Search@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Search::ISearchQueryLinguisticDetailsFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Search::ISearchQueryLinguisticDetailsFactory>>)
0x18003d037  mov     ebx, eax
0x18003d039  test    eax, eax
0x18003d03b  js      loc_18003D168
0x18003d041  mov     [rbp+var_40], r15
0x18003d045  mov     rdi, [rbp+var_38]
0x18003d049  mov     rax, [rdi]
0x18003d04c  mov     rbx, [rax+30h]
0x18003d050  lea     rcx, [rbp+var_40]
0x18003d054  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d059  lea     rax, [rbp+var_40]
0x18003d05d  mov     [rsp+80h+var_60], rax
0x18003d062  xor     r9d, r9d
0x18003d065  xor     r8d, r8d
0x18003d068  xor     edx, edx
0x18003d06a  mov     rcx, rdi
0x18003d06d  mov     rax, rbx
0x18003d070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d075  mov     ebx, eax
0x18003d077  test    eax, eax
0x18003d079  js      loc_18003D15E
0x18003d07f  mov     [rbp+var_48], r15
0x18003d083  lea     rdx, [rbp+var_48]
0x18003d087  lea     rcx, [rbp+var_40]
0x18003d08b  call    ??$As@UISearchQueryLinguisticDetailsPriv@@@?$ComPtr@UISearchQueryLinguisticDetails@Search@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISearchQueryLinguisticDetailsPriv@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Search::ISearchQueryLinguisticDetails>::As<ISearchQueryLinguisticDetailsPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISearchQueryLinguisticDetailsPriv>>)
0x18003d090  mov     ebx, eax
0x18003d092  test    eax, eax
0x18003d094  js      loc_18003D154
0x18003d09a  mov     rbx, [rbp+var_48]
0x18003d09e  mov     rax, [rbx]
0x18003d0a1  mov     rdi, [rax+18h]
0x18003d0a5  mov     [rbp+length], r15d
0x18003d0a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003d0ad  inc     rcx; unsigned __int64
0x18003d0b0  cmp     [rsi+rcx*2], r15w
0x18003d0b5  jnz     short loc_18003D0AD
0x18003d0b7  lea     rdx, [rbp+length]; unsigned int *
0x18003d0bb  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003d0c0  test    eax, eax
0x18003d0c2  jns     short loc_18003D0D9
0x18003d0c4  xor     r9d, r9d; lpArguments
0x18003d0c7  xor     r8d, r8d; nNumberOfArguments
0x18003d0ca  lea     edx, [r9+1]; dwExceptionFlags
0x18003d0ce  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003d0d3  call    cs:__imp_RaiseException
0x18003d0d9  lea     r9, [rbp+string]; string
0x18003d0dd  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003d0e1  mov     edx, [rbp+length]; length
0x18003d0e4  mov     rcx, rsi; sourceString
0x18003d0e7  call    cs:__imp_WindowsCreateStringReference
0x18003d0ed  mov     rdx, [rbp+string]
0x18003d0f1  mov     rcx, rbx
0x18003d0f4  mov     rax, rdi
0x18003d0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0fc  mov     ebx, eax
0x18003d0fe  test    eax, eax
0x18003d100  js      short loc_18003D154
0x18003d102  mov     qword ptr [rbp+length], r15
0x18003d106  mov     rdi, [rbp+var_48]
0x18003d10a  mov     rax, [rdi]
0x18003d10d  mov     rbx, [rax+40h]
0x18003d111  lea     rcx, [rbp+length]
0x18003d115  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d11a  lea     rdx, [rbp+length]
0x18003d11e  mov     rcx, rdi
0x18003d121  mov     rax, rbx
0x18003d124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d129  mov     ebx, eax
0x18003d12b  test    eax, eax
0x18003d12d  js      short loc_18003D14A
0x18003d12f  mov     rcx, qword ptr [rbp+length]
0x18003d133  mov     rax, [rcx]
0x18003d136  mov     r8, r14
0x18003d139  lea     rdx, _GUID_82fb460e_0940_4b6d_b8d0_642b30989e15
0x18003d140  mov     rax, [rax]
0x18003d143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d148  mov     ebx, eax
0x18003d14a  lea     rcx, [rbp+length]
0x18003d14e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d153  nop
0x18003d154  lea     rcx, [rbp+var_48]
0x18003d158  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d15d  nop
0x18003d15e  lea     rcx, [rbp+var_40]
0x18003d162  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d167  nop
0x18003d168  lea     rcx, [rbp+var_38]
0x18003d16c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d171  mov     eax, ebx
0x18003d173  mov     rcx, [rbp+var_10]
0x18003d177  xor     rcx, rsp; StackCookie
0x18003d17a  call    __security_check_cookie
0x18003d17f  mov     rbx, [rsp+80h+arg_10]
0x18003d187  add     rsp, 80h
0x18003d18e  pop     r15
0x18003d190  pop     r14
0x18003d192  pop     rdi
0x18003d193  pop     rsi
0x18003d194  pop     rbp
0x18003d195  retn
```
