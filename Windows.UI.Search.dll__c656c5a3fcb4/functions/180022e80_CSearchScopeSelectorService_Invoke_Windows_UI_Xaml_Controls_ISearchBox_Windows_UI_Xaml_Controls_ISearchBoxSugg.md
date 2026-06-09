# CSearchScopeSelectorService::Invoke(Windows::UI::Xaml::Controls::ISearchBox *,Windows::UI::Xaml::Controls::ISearchBoxSuggestionsRequestedEventArgs *)

- ea: `0x180022e80`
- end: `0x180022ff3`
- name: `?Invoke@CSearchScopeSelectorService@@UEAAJPEAUISearchBox@Controls@Xaml@UI@Windows@@PEAUISearchBoxSuggestionsRequestedEventArgs@3456@@Z`
- size: `371`
- prototype: `__int64 __fastcall(CSearchScopeSelectorService *__hidden this, struct Windows::UI::Xaml::Controls::ISearchBox *, struct Windows::UI::Xaml::Controls::ISearchBoxSuggestionsRequestedEventArgs *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007b3c`
- `0x180015084`
- `0x180016ca0`
- `0x180022e80`
- `0x180025ca0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022ea6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022f45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022ea6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022f45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022fde`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSearchScopeSelectorService::Invoke(
        HSTRING *this,
        struct Windows::UI::Xaml::Controls::ISearchBox *a2,
        struct Windows::UI::Xaml::Controls::ISearchBoxSuggestionsRequestedEventArgs *a3)
{
  __int64 (__fastcall *v5)(struct Windows::UI::Xaml::Controls::ISearchBoxSuggestionsRequestedEventArgs *, HSTRING *); // rbx
  int updated; // ebx
  __int64 (__fastcall *v7)(struct Windows::UI::Xaml::Controls::ISearchBoxSuggestionsRequestedEventArgs *, __int64 (__fastcall ****)(_QWORD, GUID *, HSTRING *)); // rbx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, HSTRING *); // rdi
  HSTRING v10; // rbx
  __int64 v11; // rdx
  HSTRING v12; // rbx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, HSTRING *); // [rsp+20h] [rbp-10h] BYREF
  HSTRING v15; // [rsp+28h] [rbp-8h] BYREF
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF
  HSTRING v17; // [rsp+68h] [rbp+38h] BYREF

  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::UI::Xaml::Controls::ISearchBoxSuggestionsRequestedEventArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  updated = v5(a3, &string);
  if ( updated >= 0 )
  {
    v14 = 0;
    v7 = *(__int64 (__fastcall **)(struct Windows::UI::Xaml::Controls::ISearchBoxSuggestionsRequestedEventArgs *, __int64 (__fastcall ****)(_QWORD, GUID *, HSTRING *)))(*(_QWORD *)a3 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
    updated = v7(a3, &v14);
    if ( updated >= 0 )
    {
      v17 = 0;
      v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v14;
      v9 = **v14;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
      updated = v9(v8, &GUID_8ffa42ad_f8c4_44c9_b7d6_67f5f63b90d7, &v17);
      if ( updated >= 0 )
      {
        v10 = string;
        string = 0;
        WindowsDeleteString(this[6]);
        this[6] = v10;
        v12 = v17;
        if ( this[7] != v17 )
        {
          v15 = v17;
          Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v15, v11);
          v15 = this[7];
          this[7] = v12;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
        }
        updated = CSearchScopeSelectorService::_UpdateAppSuggestionsFromLastQuery((CSearchScopeSelectorService *)(this - 7));
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 22),
      10,
      &WPP_9ff13e183948381501d20d2536b3ba22_Traceguids,
      (unsigned int)updated);
  }
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180022e80  mov     [rsp-18h+arg_0], rbx
0x180022e85  push    rbp
0x180022e86  push    rsi
0x180022e87  push    rdi
0x180022e88  mov     rbp, rsp
0x180022e8b  sub     rsp, 30h
0x180022e8f  mov     rdi, r8
0x180022e92  mov     rsi, rcx
0x180022e95  mov     [rbp+string], 0
0x180022e9d  mov     rax, [r8]
0x180022ea0  mov     rbx, [rax+38h]
0x180022ea4  xor     ecx, ecx; string
0x180022ea6  call    cs:__imp_WindowsDeleteString
0x180022eac  mov     [rbp+string], 0
0x180022eb4  lea     rdx, [rbp+string]
0x180022eb8  mov     rcx, rdi
0x180022ebb  mov     rax, rbx
0x180022ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ec3  mov     ebx, eax
0x180022ec5  test    eax, eax
0x180022ec7  js      loc_180022F99
0x180022ecd  mov     [rbp+var_10], 0
0x180022ed5  mov     rax, [rdi]
0x180022ed8  mov     rbx, [rax+40h]
0x180022edc  lea     rcx, [rbp+var_10]
0x180022ee0  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180022ee5  lea     rdx, [rbp+var_10]
0x180022ee9  mov     rcx, rdi
0x180022eec  mov     rax, rbx
0x180022eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ef4  mov     ebx, eax
0x180022ef6  test    eax, eax
0x180022ef8  js      loc_180022F90
0x180022efe  mov     [rbp+arg_18], 0
0x180022f06  mov     rbx, [rbp+var_10]
0x180022f0a  mov     rax, [rbx]
0x180022f0d  mov     rdi, [rax]
0x180022f10  lea     rcx, [rbp+arg_18]
0x180022f14  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180022f19  lea     r8, [rbp+arg_18]
0x180022f1d  lea     rdx, _GUID_8ffa42ad_f8c4_44c9_b7d6_67f5f63b90d7
0x180022f24  mov     rcx, rbx
0x180022f27  mov     rax, rdi
0x180022f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f2f  mov     ebx, eax
0x180022f31  test    eax, eax
0x180022f33  js      short loc_180022F86
0x180022f35  mov     rbx, [rbp+string]
0x180022f39  mov     [rbp+string], 0
0x180022f41  mov     rcx, [rsi+30h]; string
0x180022f45  call    cs:__imp_WindowsDeleteString
0x180022f4b  mov     [rsi+30h], rbx
0x180022f4f  mov     rbx, [rbp+arg_18]
0x180022f53  cmp     [rsi+38h], rbx
0x180022f57  jz      short loc_180022F7B
0x180022f59  mov     [rbp+var_8], rbx
0x180022f5d  lea     rcx, [rbp+var_8]
0x180022f61  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180022f66  mov     rax, [rsi+38h]
0x180022f6a  mov     [rbp+var_8], rax
0x180022f6e  mov     [rsi+38h], rbx
0x180022f72  lea     rcx, [rbp+var_8]
0x180022f76  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180022f7b  lea     rcx, [rsi-38h]; this
0x180022f7f  call    ?_UpdateAppSuggestionsFromLastQuery@CSearchScopeSelectorService@@AEAAJXZ; CSearchScopeSelectorService::_UpdateAppSuggestionsFromLastQuery(void)
0x180022f84  mov     ebx, eax
0x180022f86  lea     rcx, [rbp+arg_18]
0x180022f8a  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180022f8f  nop
0x180022f90  lea     rcx, [rbp+var_10]
0x180022f94  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180022f99  lea     rax, WPP_GLOBAL_Control
0x180022fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fa7  cmp     rcx, rax
0x180022faa  jz      short loc_180022FDA
0x180022fac  test    byte ptr [rcx+0BCh], 1
0x180022fb3  jz      short loc_180022FDA
0x180022fb5  cmp     byte ptr [rcx+0B9h], 4
0x180022fbc  jb      short loc_180022FDA
0x180022fbe  mov     edx, 0Ah
0x180022fc3  mov     r9d, ebx
0x180022fc6  lea     r8, WPP_9ff13e183948381501d20d2536b3ba22_Traceguids
0x180022fcd  mov     rcx, [rcx+0B0h]
0x180022fd4  call    WPP_SF_d
0x180022fd9  nop
0x180022fda  mov     rcx, [rbp+string]; string
0x180022fde  call    cs:__imp_WindowsDeleteString
0x180022fe4  xor     eax, eax
0x180022fe6  mov     rbx, [rsp+30h+arg_0]
0x180022feb  add     rsp, 30h
0x180022fef  pop     rdi
0x180022ff0  pop     rsi
0x180022ff1  pop     rbp
0x180022ff2  retn
```
