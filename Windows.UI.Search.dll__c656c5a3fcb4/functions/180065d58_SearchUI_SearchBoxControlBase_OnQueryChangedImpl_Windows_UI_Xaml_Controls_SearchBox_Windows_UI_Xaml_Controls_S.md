# SearchUI::SearchBoxControlBase::_OnQueryChangedImpl(Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxQueryChangedEventArgs *)

- ea: `0x180065d58`
- end: `0x180066067`
- name: `?_OnQueryChangedImpl@SearchBoxControlBase@SearchUI@@IE$AAAXPE$AAVSearchBox@Controls@Xaml@UI@Windows@@PE$AAVSearchBoxQueryChangedEventArgs@4567@@Z`
- size: `783`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800557c0`

## callees

- `0x180003372`
- `0x1800033de`
- `0x18000b908`
- `0x1800127ac`
- `0x18005137c`
- `0x180060878`
- `0x1800655f8`
- `0x1800657a0`
- `0x180065d58`
- `0x1800664e0`
- `0x18006830c`
- `0x180068360`
- `0x18006845c`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065e37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065e45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065e37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065e45`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180065e74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180065e74`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HRESULT __fastcall SearchUI::SearchBoxControlBase::_OnQueryChangedImpl(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // r15
  __int64 v6; // rcx
  char IsImeCompositionInProgress; // di
  _BYTE *v8; // rax
  _BYTE *v9; // r12
  __int64 v10; // rbx
  __int64 v11; // rcx
  char v12; // r14
  HSTRING v13; // rbx
  HSTRING v14; // rsi
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v16; // rax
  const WCHAR *v17; // rcx
  const WCHAR *v18; // r8
  HSTRING v19; // rbx
  char v20; // di
  HSTRING v21; // rbx
  PCWSTR StringRawBuffer_0; // rax
  __int64 v23; // r8
  __int64 v24; // rcx
  int v25; // ecx
  HSTRING stringa; // [rsp+30h] [rbp-50h]
  HSTRING string; // [rsp+30h] [rbp-50h]
  HSTRING stringb; // [rsp+30h] [rbp-50h]
  HSTRING v30; // [rsp+38h] [rbp-48h]
  int v31; // [rsp+40h] [rbp-40h]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+50h] [rbp-30h] BYREF
  PCWSTR v34; // [rsp+60h] [rbp-20h]
  int v35; // [rsp+68h] [rbp-18h]
  int v36; // [rsp+6Ch] [rbp-14h]

  v5 = 0;
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 344) + 296LL))(a1 + 344, 0);
  stringa = (HSTRING)Windows::UI::Xaml::Controls::ISearchBoxQueryChangedEventArgs::LinguisticDetails::get(a3);
  IsImeCompositionInProgress = SearchUI::SearchBoxControlBase::_IsImeCompositionInProgress(v6, stringa);
  __abi_winrt_ptr_dtor(stringa);
  v8 = (_BYTE *)(a1 + 457);
  v9 = (_BYTE *)(a1 + 456);
  if ( IsImeCompositionInProgress )
  {
    *v8 = 0;
    *v9 = 0;
  }
  if ( !*v9 && !*v8 )
    *(_BYTE *)(a1 + 432) = 1;
  v10 = Windows::UI::Xaml::Controls::ISearchBoxQueryChangedEventArgs::LinguisticDetails::get(a3);
  v12 = SearchUI::SearchBoxControlBase::_IsImeCompositionInProgress(v11, v10);
  __abi_winrt_ptr_dtor(v10);
  v13 = *(HSTRING *)(a1 + 440);
  v14 = (HSTRING)Windows::UI::Xaml::Controls::ITextBox::Text::get(a3);
  StringRawBuffer = WindowsGetStringRawBuffer(v14, 0);
  v16 = WindowsGetStringRawBuffer(v13, 0);
  v17 = &pszDefault;
  v18 = &pszDefault;
  if ( v16 )
    v18 = v16;
  if ( StringRawBuffer )
    v17 = StringRawBuffer;
  v31 = CompareStringOrdinal(v17, -1, v18, -1, 0);
  WindowsDeleteString_0(v14);
  string = (HSTRING)Windows::UI::Xaml::Controls::ISearchBoxSuggestionsRequestedEventArgs::Language::get(a3);
  v30 = (HSTRING)Windows::UI::Xaml::Controls::ITextBox::Text::get(a3);
  SearchUI::SearchBoxControlBase::_SetFontLanguage((HSTRING *)a1, v30, string);
  WindowsDeleteString_0(v30);
  WindowsDeleteString_0(string);
  if ( v12 )
  {
    v19 = (HSTRING)a1;
  }
  else
  {
    v19 = (HSTRING)Windows::UI::Xaml::Controls::ITextBox::Text::get(a3);
    v5 = 1;
    if ( !(unsigned __int8)Platform::String::operator==(v19, 0) )
    {
      if ( *v9
        || (string = (HSTRING)Windows::UI::Xaml::Controls::ITextBox::Text::get(a3),
            v5 = 3,
            SearchUI::SearchBoxControlBase::_IsAutoCompletionTextChange(a1, string)) )
      {
        v20 = 0;
        goto LABEL_17;
      }
    }
  }
  v20 = 1;
LABEL_17:
  if ( (v5 & 2) != 0 )
  {
    v5 &= ~2u;
    WindowsDeleteString_0(string);
  }
  if ( (v5 & 1) != 0 )
  {
    v5 &= ~1u;
    WindowsDeleteString_0(v19);
  }
  if ( v20 )
  {
    if ( v31 != 2 )
    {
      string = (HSTRING)Windows::UI::Xaml::Controls::ITextBox::Text::get(a3);
      __abi_winrt_ptrto_string_assign(a1 + 440, string);
      WindowsDeleteString_0(string);
    }
    if ( (Microsoft_Windows_UI_SearchEnableBits & 1) != 0 )
    {
      v21 = (HSTRING)Windows::UI::Xaml::Controls::ITextBox::Text::get(a3);
      v5 |= 4u;
      StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v21, 0);
      if ( StringRawBuffer_0 )
      {
        v24 = -1;
        do
          ++v24;
        while ( StringRawBuffer_0[v24] );
        v25 = 2 * v24 + 2;
      }
      else
      {
        StringRawBuffer_0 = L"NULL";
        v25 = 10;
      }
      v34 = StringRawBuffer_0;
      v35 = v25;
      v36 = 0;
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_SEARCHUI_PUBLISHER_Context,
        (const EVENT_DESCRIPTOR *)SearchPane_QueryChanged,
        v23,
        2u,
        &v33);
    }
    else
    {
      v21 = string;
    }
    if ( (v5 & 4) != 0 )
      WindowsDeleteString_0(v21);
  }
  stringb = (HSTRING)Windows::UI::Xaml::Controls::ITextBox::Text::get(a3);
  __abi_winrt_ptrto_string_assign(a1 + 448, stringb);
  return WindowsDeleteString_0(stringb);
}

```

## disassembly

```asm
0x180065d58  mov     [rsp-38h+arg_8], rbx
0x180065d5d  push    rbp
0x180065d5e  push    rsi
0x180065d5f  push    rdi
0x180065d60  push    r12
0x180065d62  push    r13
0x180065d64  push    r14
0x180065d66  push    r15
0x180065d68  mov     rbp, rsp
0x180065d6b  sub     rsp, 80h
0x180065d72  mov     rax, cs:__security_cookie
0x180065d79  xor     rax, rsp
0x180065d7c  mov     [rbp+var_10], rax
0x180065d80  mov     r13, r8
0x180065d83  mov     rsi, rcx
0x180065d86  mov     [rbp+var_38], rcx
0x180065d8a  xor     r14d, r14d
0x180065d8d  mov     r15d, r14d
0x180065d90  mov     dword ptr [rbp+var_48], r14d
0x180065d94  add     rcx, 158h
0x180065d9b  mov     rax, [rcx]
0x180065d9e  xor     edx, edx
0x180065da0  mov     rax, [rax+128h]
0x180065da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065dac  mov     rcx, r13
0x180065daf  call    ?get@LinguisticDetails@ISearchBoxQueryChangedEventArgs@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVSearchQueryLinguisticDetails@Search@ApplicationModel@6@XZ; Windows::UI::Xaml::Controls::ISearchBoxQueryChangedEventArgs::LinguisticDetails::get(void)
0x180065db4  mov     rbx, rax
0x180065db7  mov     [rbp+string], rax
0x180065dbb  mov     rdx, rax
0x180065dbe  call    ?_IsImeCompositionInProgress@SearchBoxControlBase@SearchUI@@AE$AAA_NPE$AAVSearchQueryLinguisticDetails@Search@ApplicationModel@Windows@@@Z; SearchUI::SearchBoxControlBase::_IsImeCompositionInProgress(Windows::ApplicationModel::Search::SearchQueryLinguisticDetails *)
0x180065dc3  mov     dil, al
0x180065dc6  mov     rcx, rbx
0x180065dc9  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065dce  lea     rax, [rsi+1C9h]
0x180065dd5  lea     r12, [rsi+1C8h]
0x180065ddc  test    dil, dil
0x180065ddf  jz      short loc_180065DE8
0x180065de1  mov     [rax], r14b
0x180065de4  mov     [r12], r14b
0x180065de8  cmp     [r12], r14b
0x180065dec  jnz     short loc_180065DFA
0x180065dee  cmp     [rax], r14b
0x180065df1  jnz     short loc_180065DFA
0x180065df3  mov     byte ptr [rsi+1B0h], 1
0x180065dfa  mov     rcx, r13
0x180065dfd  call    ?get@LinguisticDetails@ISearchBoxQueryChangedEventArgs@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVSearchQueryLinguisticDetails@Search@ApplicationModel@6@XZ; Windows::UI::Xaml::Controls::ISearchBoxQueryChangedEventArgs::LinguisticDetails::get(void)
0x180065e02  mov     rbx, rax
0x180065e05  mov     [rbp+string], rax
0x180065e09  mov     rdx, rax
0x180065e0c  call    ?_IsImeCompositionInProgress@SearchBoxControlBase@SearchUI@@AE$AAA_NPE$AAVSearchQueryLinguisticDetails@Search@ApplicationModel@Windows@@@Z; SearchUI::SearchBoxControlBase::_IsImeCompositionInProgress(Windows::ApplicationModel::Search::SearchQueryLinguisticDetails *)
0x180065e11  mov     r14b, al
0x180065e14  mov     rcx, rbx
0x180065e17  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065e1c  mov     rbx, [rsi+1B8h]
0x180065e23  mov     rcx, r13
0x180065e26  call    ?get@Text@ITextBox@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::UI::Xaml::Controls::ITextBox::Text::get(void)
0x180065e2b  mov     rsi, rax
0x180065e2e  mov     [rbp+string], rax
0x180065e32  xor     edx, edx; length
0x180065e34  mov     rcx, rax; string
0x180065e37  call    cs:__imp_WindowsGetStringRawBuffer
0x180065e3d  mov     rdi, rax
0x180065e40  xor     edx, edx; length
0x180065e42  mov     rcx, rbx; string
0x180065e45  call    cs:__imp_WindowsGetStringRawBuffer
0x180065e4b  lea     rcx, pszDefault
0x180065e52  mov     r8, rcx
0x180065e55  test    rax, rax
0x180065e58  cmovnz  r8, rax; lpString2
0x180065e5c  test    rdi, rdi
0x180065e5f  cmovnz  rcx, rdi; lpString1
0x180065e63  mov     [rsp+80h+bIgnoreCase], 0; bIgnoreCase
0x180065e6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180065e6f  mov     r9d, eax; cchCount2
0x180065e72  mov     edx, eax; cchCount1
0x180065e74  call    cs:__imp_CompareStringOrdinal
0x180065e7a  mov     [rbp+var_40], eax
0x180065e7d  mov     rcx, rsi; string
0x180065e80  call    WindowsDeleteString_0
0x180065e85  mov     rcx, r13
0x180065e88  call    ?get@Language@ISearchBoxSuggestionsRequestedEventArgs@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::UI::Xaml::Controls::ISearchBoxSuggestionsRequestedEventArgs::Language::get(void)
0x180065e8d  mov     rdi, rax
0x180065e90  mov     [rbp+string], rax
0x180065e94  mov     rcx, r13
0x180065e97  call    ?get@Text@ITextBox@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::UI::Xaml::Controls::ITextBox::Text::get(void)
0x180065e9c  mov     rbx, rax
0x180065e9f  mov     [rbp+var_48], rax
0x180065ea3  mov     r8, rdi
0x180065ea6  mov     rdx, rax
0x180065ea9  mov     rsi, [rbp+var_38]
0x180065ead  mov     rcx, rsi
0x180065eb0  call    ?_SetFontLanguage@SearchBoxControlBase@SearchUI@@AE$AAAXPE$AAVString@Platform@@0@Z; SearchUI::SearchBoxControlBase::_SetFontLanguage(Platform::String *,Platform::String *)
0x180065eb5  nop
0x180065eb6  mov     rcx, rbx; string
0x180065eb9  call    WindowsDeleteString_0
0x180065ebe  nop
0x180065ebf  mov     rcx, rdi; string
0x180065ec2  call    WindowsDeleteString_0
0x180065ec7  test    r14b, r14b
0x180065eca  jnz     short loc_180065F24
0x180065ecc  mov     rcx, r13
0x180065ecf  call    ?get@Text@ITextBox@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::UI::Xaml::Controls::ITextBox::Text::get(void)
0x180065ed4  mov     rbx, rax
0x180065ed7  mov     [rbp+var_38], rax
0x180065edb  mov     r15d, 1
0x180065ee1  mov     dword ptr [rbp+var_48], r15d
0x180065ee5  xor     edx, edx
0x180065ee7  mov     rcx, rax
0x180065eea  call    ??8String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator==(Platform::String *,Platform::String *)
0x180065eef  xor     r14d, r14d
0x180065ef2  test    al, al
0x180065ef4  jnz     short loc_180065F2B
0x180065ef6  cmp     [r12], r14b
0x180065efa  jnz     short loc_180065F1F
0x180065efc  mov     rcx, r13
0x180065eff  call    ?get@Text@ITextBox@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::UI::Xaml::Controls::ITextBox::Text::get(void)
0x180065f04  mov     [rbp+string], rax
0x180065f08  lea     r15d, [r14+3]
0x180065f0c  mov     dword ptr [rbp+var_48], r15d
0x180065f10  mov     rdx, rax
0x180065f13  mov     rcx, rsi
0x180065f16  call    ?_IsAutoCompletionTextChange@SearchBoxControlBase@SearchUI@@AE$AAA_NPE$AAVString@Platform@@@Z; SearchUI::SearchBoxControlBase::_IsAutoCompletionTextChange(Platform::String *)
0x180065f1b  test    al, al
0x180065f1d  jz      short loc_180065F2B
0x180065f1f  mov     dil, r14b
0x180065f22  jmp     short loc_180065F2E
0x180065f24  mov     rbx, [rbp+var_38]
0x180065f28  xor     r14d, r14d
0x180065f2b  mov     dil, 1
0x180065f2e  test    r15b, 2
0x180065f32  jz      short loc_180065F42
0x180065f34  and     r15d, 0FFFFFFFDh
0x180065f38  mov     rcx, [rbp+string]; string
0x180065f3c  call    WindowsDeleteString_0
0x180065f41  nop
0x180065f42  test    r15b, 1
0x180065f46  jz      short loc_180065F54
0x180065f48  and     r15d, 0FFFFFFFEh
0x180065f4c  mov     rcx, rbx; string
0x180065f4f  call    WindowsDeleteString_0
0x180065f54  test    dil, dil
0x180065f57  jz      loc_180066019
0x180065f5d  cmp     [rbp+var_40], 2
0x180065f61  jz      short loc_180065F8A
0x180065f63  mov     rcx, r13
0x180065f66  call    ?get@Text@ITextBox@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::UI::Xaml::Controls::ITextBox::Text::get(void)
0x180065f6b  mov     rbx, rax
0x180065f6e  mov     [rbp+string], rax
0x180065f72  mov     rdx, rax
0x180065f75  lea     rcx, [rsi+1B8h]
0x180065f7c  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x180065f81  nop
0x180065f82  mov     rcx, rbx; string
0x180065f85  call    WindowsDeleteString_0
0x180065f8a  test    byte ptr cs:Microsoft_Windows_UI_SearchEnableBits, 1
0x180065f91  jz      short loc_180066007
0x180065f93  mov     rcx, r13
0x180065f96  call    ?get@Text@ITextBox@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::UI::Xaml::Controls::ITextBox::Text::get(void)
0x180065f9b  mov     rbx, rax
0x180065f9e  mov     [rbp+string], rax
0x180065fa2  or      r15d, 4
0x180065fa6  xor     edx, edx; length
0x180065fa8  mov     rcx, rax; string
0x180065fab  call    WindowsGetStringRawBuffer_0
0x180065fb0  test    rax, rax
0x180065fb3  jz      short loc_180065FCC
0x180065fb5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180065fb9  inc     rcx
0x180065fbc  cmp     [rax+rcx*2], r14w
0x180065fc1  jnz     short loc_180065FB9
0x180065fc3  lea     ecx, ds:2[rcx*2]
0x180065fca  jmp     short loc_180065FD8
0x180065fcc  lea     rax, aNull_0; "NULL"
0x180065fd3  mov     ecx, 0Ah
0x180065fd8  mov     [rbp+var_20], rax
0x180065fdc  mov     [rbp+var_18], ecx
0x180065fdf  mov     [rbp+var_14], r14d
0x180065fe3  lea     rax, [rbp+var_30]
0x180065fe7  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x180065fec  mov     r9d, 2
0x180065ff2  lea     rdx, SearchPane_QueryChanged
0x180065ff9  lea     rcx, MICROSOFT_SEARCHUI_PUBLISHER_Context
0x180066000  call    McGenEventWrite_EventWriteTransfer
0x180066005  jmp     short loc_18006600B
0x180066007  mov     rbx, [rbp+string]
0x18006600b  test    r15b, 4
0x18006600f  jz      short loc_180066019
0x180066011  mov     rcx, rbx; string
0x180066014  call    WindowsDeleteString_0
0x180066019  mov     rcx, r13
0x18006601c  call    ?get@Text@ITextBox@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::UI::Xaml::Controls::ITextBox::Text::get(void)
0x180066021  mov     rbx, rax
0x180066024  mov     [rbp+string], rax
0x180066028  lea     rcx, [rsi+1C0h]
0x18006602f  mov     rdx, rax
0x180066032  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x180066037  nop
0x180066038  mov     rcx, rbx; string
0x18006603b  call    WindowsDeleteString_0
0x180066040  mov     rcx, [rbp+var_10]
0x180066044  xor     rcx, rsp; StackCookie
0x180066047  call    __security_check_cookie
0x18006604c  mov     rbx, [rsp+80h+arg_8]
0x180066054  add     rsp, 80h
0x18006605b  pop     r15
0x18006605d  pop     r14
0x18006605f  pop     r13
0x180066061  pop     r12
0x180066063  pop     rdi
0x180066064  pop     rsi
0x180066065  pop     rbp
0x180066066  retn
```
