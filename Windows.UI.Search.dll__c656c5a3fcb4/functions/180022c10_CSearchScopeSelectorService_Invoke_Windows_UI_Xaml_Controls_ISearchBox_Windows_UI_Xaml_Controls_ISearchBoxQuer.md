# CSearchScopeSelectorService::Invoke(Windows::UI::Xaml::Controls::ISearchBox *,Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *)

- ea: `0x180022c10`
- end: `0x180022d52`
- name: `?Invoke@CSearchScopeSelectorService@@UEAAJPEAUISearchBox@Controls@Xaml@UI@Windows@@PEAUISearchBoxQuerySubmittedEventArgs@3456@@Z`
- size: `322`
- prototype: `int(CSearchScopeSelectorService *__hidden this, struct Windows::UI::Xaml::Controls::ISearchBox *, struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x180016ca0`
- `0x18001f574`
- `0x1800221c4`
- `0x180022c10`
- `0x18002625c`
- `0x180026454`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022cf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022cf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022c2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022c2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSearchScopeSelectorService::Invoke(
        HSTRING *this,
        struct Windows::UI::Xaml::Controls::ISearchBox *a2,
        struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *a3)
{
  int QueryWithLinguisticAlternativesFromSubmittedEventArgs; // ebx
  const WCHAR *StringRawBuffer; // rax
  __int64 (__fastcall *v7)(struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *, HSTRING *); // rbx
  struct IUnknown *v8; // rdx
  unsigned int v9; // r8d
  struct IQueryWithLinguisticAlternatives *v11; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v12[3]; // [rsp+28h] [rbp-18h] BYREF
  int v13; // [rsp+60h] [rbp+20h] BYREF
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF

  QueryWithLinguisticAlternativesFromSubmittedEventArgs = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(this[4], 0);
  if ( (unsigned int)IsAppScope(StringRawBuffer) )
  {
    v11 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v11);
    QueryWithLinguisticAlternativesFromSubmittedEventArgs = CSearchScopeSelectorService::s_GetQueryWithLinguisticAlternativesFromSubmittedEventArgs(
                                                              a3,
                                                              &v11);
    if ( QueryWithLinguisticAlternativesFromSubmittedEventArgs >= 0 )
    {
      string = 0;
      v7 = *(__int64 (__fastcall **)(struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      QueryWithLinguisticAlternativesFromSubmittedEventArgs = v7(a3, &string);
      if ( QueryWithLinguisticAlternativesFromSubmittedEventArgs >= 0 )
      {
        v13 = 0;
        QueryWithLinguisticAlternativesFromSubmittedEventArgs = (*(__int64 (__fastcall **)(struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *, int *))(*(_QWORD *)a3 + 72LL))(
                                                                  a3,
                                                                  &v13);
        if ( QueryWithLinguisticAlternativesFromSubmittedEventArgs >= 0 )
        {
          v12[0] = &v11;
          v12[1] = &string;
          v12[2] = &v13;
          QueryWithLinguisticAlternativesFromSubmittedEventArgs = CSearchScopeSelectorService::_InvokeOnBroker<_lambda_17a7cf700776dc0c366d6c144a7a9101_>(
                                                                    this - 8,
                                                                    (__int64)v12);
          if ( QueryWithLinguisticAlternativesFromSubmittedEventArgs >= 0 )
            Windows::Internal::IUnknown_TryToReturnActivation((Windows::Internal *)*(this - 6), v8, v9);
        }
      }
      WindowsDeleteString(string);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v11);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 22),
      11,
      &WPP_9ff13e183948381501d20d2536b3ba22_Traceguids,
      (unsigned int)QueryWithLinguisticAlternativesFromSubmittedEventArgs);
  }
  return 0;
}

```

## disassembly

```asm
0x180022c10  mov     [rsp-18h+arg_8], rbx
0x180022c15  push    rbp
0x180022c16  push    rsi
0x180022c17  push    rdi
0x180022c18  mov     rbp, rsp
0x180022c1b  sub     rsp, 40h
0x180022c1f  mov     rdi, r8
0x180022c22  mov     rsi, rcx
0x180022c25  xor     ebx, ebx
0x180022c27  xor     edx, edx; length
0x180022c29  mov     rcx, [rcx+20h]; string
0x180022c2d  call    cs:__imp_WindowsGetStringRawBuffer
0x180022c33  mov     rcx, rax; lpString1
0x180022c36  call    IsAppScope
0x180022c3b  test    eax, eax
0x180022c3d  jz      loc_180022D03
0x180022c43  mov     [rbp+var_20], rbx
0x180022c47  lea     rcx, [rbp+var_20]
0x180022c4b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180022c50  lea     rdx, [rbp+var_20]; struct IQueryWithLinguisticAlternatives **
0x180022c54  mov     rcx, rdi; struct Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *
0x180022c57  call    ?s_GetQueryWithLinguisticAlternativesFromSubmittedEventArgs@CSearchScopeSelectorService@@CAJPEAUISearchBoxQuerySubmittedEventArgs@Controls@Xaml@UI@Windows@@PEAPEAUIQueryWithLinguisticAlternatives@@@Z; CSearchScopeSelectorService::s_GetQueryWithLinguisticAlternativesFromSubmittedEventArgs(Windows::UI::Xaml::Controls::ISearchBoxQuerySubmittedEventArgs *,IQueryWithLinguisticAlternatives * *)
0x180022c5c  mov     ebx, eax
0x180022c5e  test    eax, eax
0x180022c60  js      loc_180022CFA
0x180022c66  mov     [rbp+string], 0
0x180022c6e  mov     rax, [rdi]
0x180022c71  mov     rbx, [rax+38h]
0x180022c75  xor     ecx, ecx; string
0x180022c77  call    cs:__imp_WindowsDeleteString
0x180022c7d  mov     [rbp+string], 0
0x180022c85  lea     rdx, [rbp+string]
0x180022c89  mov     rcx, rdi
0x180022c8c  mov     rax, rbx
0x180022c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c94  mov     ebx, eax
0x180022c96  test    eax, eax
0x180022c98  js      short loc_180022CEF
0x180022c9a  mov     [rbp+arg_0], 0
0x180022ca1  mov     rax, [rdi]
0x180022ca4  lea     rdx, [rbp+arg_0]
0x180022ca8  mov     rcx, rdi
0x180022cab  mov     rax, [rax+48h]
0x180022caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cb4  mov     ebx, eax
0x180022cb6  test    eax, eax
0x180022cb8  js      short loc_180022CEF
0x180022cba  lea     rax, [rbp+var_20]
0x180022cbe  mov     [rbp+var_18], rax
0x180022cc2  lea     rax, [rbp+string]
0x180022cc6  mov     [rbp+var_10], rax
0x180022cca  lea     rax, [rbp+arg_0]
0x180022cce  mov     [rbp+var_8], rax
0x180022cd2  lea     rcx, [rsi-40h]; this
0x180022cd6  lea     rdx, [rbp+var_18]
0x180022cda  call    ??$_InvokeOnBroker@V_lambda_17a7cf700776dc0c366d6c144a7a9101_@@@CSearchScopeSelectorService@@AEAAJAEBV_lambda_17a7cf700776dc0c366d6c144a7a9101_@@@Z; CSearchScopeSelectorService::_InvokeOnBroker<_lambda_17a7cf700776dc0c366d6c144a7a9101_>(_lambda_17a7cf700776dc0c366d6c144a7a9101_ const &)
0x180022cdf  mov     ebx, eax
0x180022ce1  test    eax, eax
0x180022ce3  js      short loc_180022CEF
0x180022ce5  mov     rcx, [rsi-30h]; this
0x180022ce9  call    ?IUnknown_TryToReturnActivation@Internal@Windows@@YAXPEAUIUnknown@@K@Z; Windows::Internal::IUnknown_TryToReturnActivation(IUnknown *,ulong)
0x180022cee  nop
0x180022cef  mov     rcx, [rbp+string]; string
0x180022cf3  call    cs:__imp_WindowsDeleteString
0x180022cf9  nop
0x180022cfa  lea     rcx, [rbp+var_20]
0x180022cfe  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180022d03  lea     rax, WPP_GLOBAL_Control
0x180022d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d11  cmp     rcx, rax
0x180022d14  jz      short loc_180022D43
0x180022d16  test    byte ptr [rcx+0BCh], 1
0x180022d1d  jz      short loc_180022D43
0x180022d1f  cmp     byte ptr [rcx+0B9h], 4
0x180022d26  jb      short loc_180022D43
0x180022d28  mov     edx, 0Bh
0x180022d2d  mov     r9d, ebx
0x180022d30  lea     r8, WPP_9ff13e183948381501d20d2536b3ba22_Traceguids
0x180022d37  mov     rcx, [rcx+0B0h]
0x180022d3e  call    WPP_SF_d
0x180022d43  xor     eax, eax
0x180022d45  mov     rbx, [rsp+40h+arg_8]
0x180022d4a  add     rsp, 40h
0x180022d4e  pop     rdi
0x180022d4f  pop     rsi
0x180022d50  pop     rbp
0x180022d51  retn
```
