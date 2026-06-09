# CSearchScopeSelectorService::s_GetQueryWithLinguisticAlternativesFromSubmittedEventArgs(Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *,IQueryWithLinguisticAlternatives * *)

- ea: `0x18002625c`
- end: `0x18002635a`
- name: `?s_GetQueryWithLinguisticAlternativesFromSubmittedEventArgs@CSearchScopeSelectorService@@CAJPEAUISearchBoxQuerySubmittedEventArgs@Controls@Xaml@UI@Windows@@PEAPEAUIQueryWithLinguisticAlternatives@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *, struct IQueryWithLinguisticAlternatives **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180022c10`

## callees

- `0x180007b3c`
- `0x18001e758`
- `0x18002625c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026345`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026345`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSearchScopeSelectorService::s_GetQueryWithLinguisticAlternativesFromSubmittedEventArgs(
        struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *a1,
        struct IQueryWithLinguisticAlternatives **a2)
{
  __int64 (__fastcall *v4)(struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *, HSTRING *); // rbx
  int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  __int64 v8; // [rsp+40h] [rbp+20h] BYREF
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp+28h] BYREF
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF

  *a2 = 0;
  string = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *, HSTRING *))(*(_QWORD *)a1 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a1, &string);
  if ( v5 >= 0 )
  {
    v9 = 0;
    v6 = *(__int64 (__fastcall **)(struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)a1 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v9);
    v5 = v6(a1, &v9);
    if ( v5 >= 0 )
    {
      v8 = 0;
      v5 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Search::ISearchQueryLinguisticDetails>::As<ISearchQueryLinguisticDetailsPriv>(
             &v9,
             (__int64)&v8);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v8 + 24LL))(v8, string);
        if ( v5 >= 0 )
          v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IQueryWithLinguisticAlternatives **))v8)(
                 v8,
                 &GUID_8ffa42ad_f8c4_44c9_b7d6_67f5f63b90d7,
                 a2);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v8);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v9);
  }
  WindowsDeleteString(string);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002625c  mov     [rsp-18h+arg_18], rbx
0x180026261  push    rbp
0x180026262  push    rsi
0x180026263  push    rdi
0x180026264  mov     rbp, rsp
0x180026267  sub     rsp, 20h
0x18002626b  mov     rsi, rdx
0x18002626e  mov     rdi, rcx
0x180026271  mov     qword ptr [rdx], 0
0x180026278  mov     [rbp+string], 0
0x180026280  mov     rax, [rcx]
0x180026283  mov     rbx, [rax+30h]
0x180026287  xor     ecx, ecx; string
0x180026289  call    cs:__imp_WindowsDeleteString
0x18002628f  mov     [rbp+string], 0
0x180026297  lea     rdx, [rbp+string]
0x18002629b  mov     rcx, rdi
0x18002629e  mov     rax, rbx
0x1800262a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262a6  mov     ebx, eax
0x1800262a8  test    eax, eax
0x1800262aa  js      loc_180026341
0x1800262b0  mov     [rbp+arg_8], 0
0x1800262b8  mov     rax, [rdi]
0x1800262bb  mov     rbx, [rax+40h]
0x1800262bf  lea     rcx, [rbp+arg_8]
0x1800262c3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800262c8  lea     rdx, [rbp+arg_8]
0x1800262cc  mov     rcx, rdi
0x1800262cf  mov     rax, rbx
0x1800262d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262d7  mov     ebx, eax
0x1800262d9  test    eax, eax
0x1800262db  js      short loc_180026337
0x1800262dd  mov     [rbp+arg_0], 0
0x1800262e5  lea     rdx, [rbp+arg_0]
0x1800262e9  lea     rcx, [rbp+arg_8]
0x1800262ed  call    ??$As@UISearchQueryLinguisticDetailsPriv@@@?$ComPtr@UISearchQueryLinguisticDetails@Search@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISearchQueryLinguisticDetailsPriv@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Search::ISearchQueryLinguisticDetails>::As<ISearchQueryLinguisticDetailsPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISearchQueryLinguisticDetailsPriv>>)
0x1800262f2  mov     ebx, eax
0x1800262f4  test    eax, eax
0x1800262f6  js      short loc_18002632D
0x1800262f8  mov     rcx, [rbp+arg_0]
0x1800262fc  mov     rax, [rcx]
0x1800262ff  mov     rdx, [rbp+string]
0x180026303  mov     rax, [rax+18h]
0x180026307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002630c  mov     ebx, eax
0x18002630e  test    eax, eax
0x180026310  js      short loc_18002632D
0x180026312  mov     rcx, [rbp+arg_0]
0x180026316  mov     rax, [rcx]
0x180026319  mov     r8, rsi
0x18002631c  lea     rdx, _GUID_8ffa42ad_f8c4_44c9_b7d6_67f5f63b90d7
0x180026323  mov     rax, [rax]
0x180026326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002632b  mov     ebx, eax
0x18002632d  lea     rcx, [rbp+arg_0]
0x180026331  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180026336  nop
0x180026337  lea     rcx, [rbp+arg_8]
0x18002633b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180026340  nop
0x180026341  mov     rcx, [rbp+string]; string
0x180026345  call    cs:__imp_WindowsDeleteString
0x18002634b  mov     eax, ebx
0x18002634d  mov     rbx, [rsp+20h+arg_18]
0x180026352  add     rsp, 20h
0x180026356  pop     rdi
0x180026357  pop     rsi
0x180026358  pop     rbp
0x180026359  retn
```
