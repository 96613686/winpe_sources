# SearchUI::SearchBoxControlBase::_SetFontLanguage(Platform::String *,Platform::String *)

- ea: `0x1800664e0`
- end: `0x180066693`
- name: `?_SetFontLanguage@SearchBoxControlBase@SearchUI@@AE$AAAXPE$AAVString@Platform@@0@Z`
- size: `435`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800557e0`
- `0x180065d58`

## callees

- `0x180003372`
- `0x1800033de`
- `0x180005024`
- `0x18000b818`
- `0x18000b8dc`
- `0x18000b908`
- `0x180060878`
- `0x1800664e0`
- `0x180075b00`
- `0x180076238`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800665ae`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800665ae`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066560`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066560`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SearchUI::SearchBoxControlBase::_SetFontLanguage(HSTRING *a1, HSTRING a2, HSTRING a3)
{
  unsigned __int16 *StringRawBuffer_0; // rbx
  unsigned __int16 *v7; // rax
  HSTRING *v8; // r12
  const WCHAR *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rbx
  HSTRING v13; // [rsp+30h] [rbp-128h]
  __int64 type_id; // [rsp+30h] [rbp-128h]
  __int64 v15; // [rsp+38h] [rbp-120h]
  __int64 v16; // [rsp+40h] [rbp-118h]
  __int64 v17; // [rsp+48h] [rbp-110h]
  __int64 DepthFirstDescendent; // [rsp+50h] [rbp-108h]
  WCHAR String2[88]; // [rsp+60h] [rbp-F8h] BYREF

  StringRawBuffer_0 = (unsigned __int16 *)WindowsGetStringRawBuffer_0(a3, 0);
  v7 = (unsigned __int16 *)WindowsGetStringRawBuffer_0(a2, 0);
  v8 = a1 + 53;
  if ( (int)GetQueryFontLocaleString(v7, StringRawBuffer_0, String2) < 0 )
  {
    __abi_winrt_ptrto_string_assign(a1 + 53, a3);
  }
  else
  {
    v9 = WindowsGetStringRawBuffer_0(*v8, 0);
    if ( CompareStringOrdinal(v9, -1, String2, -1, 1) != 2 )
    {
      v13 = (HSTRING)Platform::String::String(v10, String2);
      __abi_winrt_ptrto_string_assign(a1 + 53, v13);
      WindowsDeleteString_0(v13);
    }
  }
  type_id = __abi_make_type_id(&_abi_typedesc_SearchUI_SuggestionsListView);
  v16 = (*((__int64 (__fastcall **)(HSTRING *))*a1 + 14))(a1);
  v17 = __abi_winrt_cast_to(0, v16, _uuidof__AVFrameworkElement_Xaml_UI_Windows__);
  DepthFirstDescendent = FindDepthFirstDescendent(v17, type_id);
  v11 = __abi_winrt_cast_to(0, DepthFirstDescendent, _uuidof__AVSuggestionsListView_SearchUI__);
  v15 = __abi_winrt_ptr_ctor(v11);
  __abi_winrt_ptr_dtor(v11);
  __abi_winrt_ptr_dtor(DepthFirstDescendent);
  __abi_winrt_ptr_dtor(v17);
  __abi_winrt_ptr_dtor(v16);
  __abi_winrt_ptr_dtor(type_id);
  (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v15 + 72LL))(v15, *v8);
  return __abi_winrt_ptr_dtor(v15);
}

```

## disassembly

```asm
0x1800664e0  push    rbx
0x1800664e2  push    rbp
0x1800664e3  push    rsi
0x1800664e4  push    rdi
0x1800664e5  push    r12
0x1800664e7  push    r14
0x1800664e9  push    r15
0x1800664eb  sub     rsp, 120h
0x1800664f2  mov     rax, cs:__security_cookie
0x1800664f9  xor     rax, rsp
0x1800664fc  mov     [rsp+158h+var_48], rax
0x180066504  mov     rsi, r8
0x180066507  mov     rdi, rdx
0x18006650a  mov     r14, rcx
0x18006650d  xor     edx, edx; length
0x18006650f  mov     rcx, r8; string
0x180066512  call    WindowsGetStringRawBuffer_0
0x180066517  mov     rbx, rax
0x18006651a  xor     edx, edx; length
0x18006651c  mov     rcx, rdi; string
0x18006651f  call    WindowsGetStringRawBuffer_0
0x180066524  lea     r12, [r14+1A8h]
0x18006652b  lea     r8, [rsp+158h+String2]; lpName
0x180066530  mov     rdx, rbx; unsigned __int16 *
0x180066533  mov     rcx, rax; unsigned __int16 *
0x180066536  call    GetQueryFontLocaleString
0x18006653b  test    eax, eax
0x18006653d  js      short loc_18006659C
0x18006653f  xor     edx, edx; length
0x180066541  mov     rcx, [r12]; string
0x180066545  call    WindowsGetStringRawBuffer_0
0x18006654a  mov     [rsp+158h+bIgnoreCase], 1; bIgnoreCase
0x180066552  or      edx, 0FFFFFFFFh; cchCount1
0x180066555  mov     r9d, edx; cchCount2
0x180066558  lea     r8, [rsp+158h+String2]; lpString2
0x18006655d  mov     rcx, rax; lpString1
0x180066560  call    cs:__imp_CompareStringOrdinal
0x180066566  cmp     eax, 2
0x180066569  jz      short loc_1800665A7
0x18006656b  mov     [rsp+158h+var_128], 0
0x180066574  lea     rdx, [rsp+158h+String2]
0x180066579  call    ??0String@Platform@@QE$AAA@PEB_W@Z; Platform::String::String(wchar_t const *)
0x18006657e  mov     rbx, rax
0x180066581  mov     [rsp+158h+var_128], rax
0x180066586  mov     rdx, rax
0x180066589  mov     rcx, r12
0x18006658c  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x180066591  nop
0x180066592  mov     rcx, rbx; string
0x180066595  call    WindowsDeleteString_0
0x18006659a  jmp     short loc_1800665A7
0x18006659c  mov     rdx, rsi
0x18006659f  mov     rcx, r12
0x1800665a2  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1800665a7  lea     rcx, __abi_typedesc_SearchUI_SuggestionsListView
0x1800665ae  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x1800665b4  mov     r15, rax
0x1800665b7  mov     [rsp+158h+var_128], rax
0x1800665bc  mov     rdx, [r14]
0x1800665bf  mov     rcx, r14
0x1800665c2  mov     rax, [rdx+70h]
0x1800665c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665cb  mov     r14, rax
0x1800665ce  mov     [rsp+158h+var_118], rax
0x1800665d3  lea     r8, __uuidof_?AVFrameworkElement@Xaml@UI@Windows@@
0x1800665da  mov     rdx, rax
0x1800665dd  xor     ecx, ecx
0x1800665df  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800665e4  mov     rbp, rax
0x1800665e7  mov     [rsp+158h+var_110], rax
0x1800665ec  mov     rdx, r15
0x1800665ef  mov     rcx, rax
0x1800665f2  call    ?FindDepthFirstDescendent@@YAPE$AAVFrameworkElement@Xaml@UI@Windows@@PE$AAV1234@PE$AAVType@Platform@@@Z; FindDepthFirstDescendent(Windows::UI::Xaml::FrameworkElement *,Platform::Type *)
0x1800665f7  mov     rdi, rax
0x1800665fa  mov     [rsp+158h+var_108], rax
0x1800665ff  lea     r8, __uuidof_?AVSuggestionsListView@SearchUI@@
0x180066606  mov     rdx, rax
0x180066609  xor     ecx, ecx
0x18006660b  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180066610  mov     rbx, rax
0x180066613  mov     [rsp+158h+var_120], rax
0x180066618  mov     rcx, rax
0x18006661b  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180066620  mov     rsi, rax
0x180066623  mov     [rsp+158h+var_120], rax
0x180066628  mov     rcx, rbx
0x18006662b  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180066630  nop
0x180066631  mov     rcx, rdi
0x180066634  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180066639  nop
0x18006663a  mov     rcx, rbp
0x18006663d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180066642  nop
0x180066643  mov     rcx, r14
0x180066646  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18006664b  nop
0x18006664c  mov     rcx, r15
0x18006664f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180066654  nop
0x180066655  mov     rax, [rsi]
0x180066658  mov     rdx, [r12]
0x18006665c  mov     rcx, rsi
0x18006665f  mov     rax, [rax+48h]
0x180066663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066668  nop
0x180066669  mov     rcx, rsi
0x18006666c  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180066671  mov     rcx, [rsp+158h+var_48]
0x180066679  xor     rcx, rsp; StackCookie
0x18006667c  call    __security_check_cookie
0x180066681  add     rsp, 120h
0x180066688  pop     r15
0x18006668a  pop     r14
0x18006668c  pop     r12
0x18006668e  pop     rdi
0x18006668f  pop     rsi
0x180066690  pop     rbp
0x180066691  pop     rbx
0x180066692  retn
```
