# SearchUI::SearchBoxControlBase::_OnLoadedImpl(Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::RoutedEventArgs *)

- ea: `0x180065874`
- end: `0x180065d51`
- name: `?_OnLoadedImpl@SearchBoxControlBase@SearchUI@@IE$AAAXPE$AAVSearchBox@Controls@Xaml@UI@Windows@@PE$AAVRoutedEventArgs@567@@Z`
- size: `1245`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting`

## callers

- `0x180055790`

## callees

- `0x1800033d2`
- `0x1800033de`
- `0x18000b6b8`
- `0x18000b818`
- `0x18000b8dc`
- `0x18000b908`
- `0x18000b928`
- `0x180063fb0`
- `0x180064564`
- `0x180064608`
- `0x1800648ac`
- `0x1800648d8`
- `0x1800654a4`
- `0x180065874`
- `0x180067da8`
- `0x180068258`
- `0x1800688f4`
- `0x180068e14`
- `0x180076238`
- `0x1800767ac`
- `0x18007b010`

## import_xrefs

- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800658a4`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800659fd`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180065bfc`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800658a4`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800659fd`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180065bfc`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x180065ade`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x180065b27`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x180065ade`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x180065b27`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall SearchUI::SearchBoxControlBase::_OnLoadedImpl(HSTRING a1, __int64 a2, HSTRING a3)
{
  HSTRING type_id; // r15
  __int64 v5; // r14
  __int64 v6; // rbx
  __int64 v7; // r13
  HRESULT v8; // eax
  HSTRING ResourceStringById; // rbx
  HSTRING v10; // r12
  HSTRING v11; // rdi
  HSTRING v12; // r15
  __int64 v13; // r14
  __int64 v14; // rbx
  __int64 v15; // r13
  HSTRING v16; // rbx
  HSTRING v17; // r15
  __int64 v18; // r14
  void *v19; // rax
  __int64 v20; // rsi
  __int64 v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // r9
  __int64 v24; // rcx
  HSTRING v25; // rsi
  __int64 QIItemsControl2_Controls_Xaml_UI_Windows__ItemsPanelRoot_ItemsControl_2345_UE_AAAPE_AAVPanel_2345_XZ; // rdi
  __int64 v27; // rbx
  __int64 v28; // r15
  HSTRING v29; // r14
  __int64 v30; // rsi
  HSTRING v31; // rbx
  HSTRING v32; // rsi
  HRESULT v33; // eax
  HSTRING v34; // rdi
  __int64 v35; // rbx
  __int64 DepthFirstDescendent; // [rsp+38h] [rbp-59h]
  __int64 v38; // [rsp+38h] [rbp-59h]
  __int64 v39; // [rsp+38h] [rbp-59h]
  __int64 (__fastcall *v40)(); // [rsp+48h] [rbp-49h] BYREF
  int v41; // [rsp+50h] [rbp-41h]
  void *v42; // [rsp+58h] [rbp-39h]
  __int64 v43; // [rsp+60h] [rbp-31h]
  __int64 v44; // [rsp+68h] [rbp-29h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-21h] BYREF
  HSTRING_HEADER v46; // [rsp+88h] [rbp-9h] BYREF
  HSTRING v47; // [rsp+F8h] [rbp+67h] BYREF
  __int64 v48; // [rsp+100h] [rbp+6Fh]
  HSTRING string; // [rsp+108h] [rbp+77h] BYREF
  __int64 v50; // [rsp+110h] [rbp+7Fh]

  string = a3;
  v48 = a2;
  v47 = a1;
  type_id = (HSTRING)__abi_make_type_id(&_abi_typedesc_Windows_UI_Xaml_Controls_TextBox);
  string = type_id;
  v5 = (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)a1 + 112LL))(a1);
  v50 = v5;
  v42 = (void *)__abi_winrt_cast_to(0, v5, _uuidof__AVFrameworkElement_Xaml_UI_Windows__);
  DepthFirstDescendent = FindDepthFirstDescendent(v42, type_id);
  v6 = __abi_winrt_cast_to(0, DepthFirstDescendent, _uuidof__AVTextBox_Controls_Xaml_UI_Windows__);
  v48 = v6;
  v7 = __abi_winrt_ptr_ctor(v6);
  v48 = v7;
  __abi_winrt_ptr_dtor(v6);
  __abi_winrt_ptr_dtor(DepthFirstDescendent);
  __abi_winrt_ptr_dtor(v42);
  __abi_winrt_ptr_dtor(v5);
  __abi_winrt_ptr_dtor(type_id);
  string = 0;
  v8 = WindowsCreateStringReference_0(L"ScopeButton/FontFamily", 0x16u, &hstringHeader, &string);
  if ( v8 < 0 )
    __abi_WinRTraiseException(v8);
  ResourceStringById = (HSTRING)LoadResourceStringById(string);
  string = ResourceStringById;
  v10 = (HSTRING)__abi_winrt_ptrto_string_ctor(ResourceStringById);
  v50 = (__int64)v10;
  WindowsDeleteString_0(ResourceStringById);
  if ( (unsigned __int8)Platform::String::operator!=(v10, 0) )
  {
    v11 = (HSTRING)__abi_winrt_cast_to(0, v7, _uuidof__AUIControl_Controls_Xaml_UI_Windows__);
    string = v11;
    v38 = Windows::UI::Xaml::Media::FontFamily::FontFamily(0, v10);
    _set__QIControl_Controls_Xaml_UI_Windows__FontFamily_Control_2345_UE_AAAXPE_AAV6Media_345__Z(v11, v38);
    __abi_winrt_ptr_dtor(v38);
    __abi_winrt_ptr_dtor(v11);
  }
  v12 = (HSTRING)__abi_make_type_id(&_abi_typedesc_SearchUI_SuggestionsListView);
  string = v12;
  v13 = (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)v47 + 112LL))(v47);
  v42 = (void *)__abi_winrt_cast_to(0, v13, _uuidof__AVFrameworkElement_Xaml_UI_Windows__);
  v43 = FindDepthFirstDescendent(v42, v12);
  v14 = __abi_winrt_cast_to(0, v43, _uuidof__AVSuggestionsListView_SearchUI__);
  v15 = __abi_winrt_ptr_ctor(v14);
  v44 = v15;
  __abi_winrt_ptr_dtor(v14);
  __abi_winrt_ptr_dtor(v43);
  __abi_winrt_ptr_dtor(v42);
  __abi_winrt_ptr_dtor(v13);
  __abi_winrt_ptr_dtor(v12);
  v16 = v47;
  v17 = (HSTRING)(*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)v47 + 112LL))(v47);
  string = v17;
  v18 = __abi_winrt_cast_to(0, v17, _uuidof__AUIUIElement_Xaml_UI_Windows__);
  v43 = v18;
  v19 = Platform::Details::Heap::Allocate(0x18u, 0x130u);
  v40 = SearchUI::SearchBoxControlBase::_OnHandledKeyDown;
  v41 = 0;
  v20 = Windows::UI::Xaml::Input::KeyEventHandler::KeyEventHandler(v19, v16, &v40);
  if ( v20 )
  {
    v42 = Platform::Details::Heap::Allocate(0x38u, 0x50u);
    v21 = Platform::Details::CustomBox<Windows::UI::Xaml::Input::KeyEventHandler __gc *>::CustomBox<Windows::UI::Xaml::Input::KeyEventHandler __gc *>(
            v42,
            v20);
  }
  else
  {
    v21 = 0;
  }
  v42 = (void *)v21;
  v22 = Windows::UI::Xaml::UIElement::KeyDownEvent::get();
  v40 = (__int64 (__fastcall *)())v22;
  LOBYTE(v23) = 1;
  _AddHandler__QIUIElement_Xaml_UI_Windows__UIElement_234_UE_AAAXPE_AAVRoutedEvent_234_PE_AAVObject_Platform___N_Z(
    v18,
    v22,
    v21,
    v23);
  __abi_winrt_ptr_dtor(v22);
  __abi_winrt_ptr_dtor(v21);
  __abi_winrt_ptr_dtor(v20);
  __abi_winrt_ptr_dtor(v18);
  __abi_winrt_ptr_dtor(v17);
  if ( v15 )
    v24 = *(_QWORD *)(v15 + 88);
  else
    v24 = 0;
  v25 = (HSTRING)__abi_winrt_ptr_ctor(v24);
  string = v25;
  QIItemsControl2_Controls_Xaml_UI_Windows__ItemsPanelRoot_ItemsControl_2345_UE_AAAPE_AAVPanel_2345_XZ = _get__QIItemsControl2_Controls_Xaml_UI_Windows__ItemsPanelRoot_ItemsControl_2345_UE_AAAPE_AAVPanel_2345_XZ(v25);
  v40 = (__int64 (__fastcall *)())QIItemsControl2_Controls_Xaml_UI_Windows__ItemsPanelRoot_ItemsControl_2345_UE_AAAPE_AAVPanel_2345_XZ;
  v27 = __abi_winrt_cast_to(
          0,
          QIItemsControl2_Controls_Xaml_UI_Windows__ItemsPanelRoot_ItemsControl_2345_UE_AAAPE_AAVPanel_2345_XZ,
          _uuidof__AUIUIElement_Xaml_UI_Windows__);
  v43 = v27;
  _set__QIUIElement_Xaml_UI_Windows__ManipulationMode_UIElement_234_UE_AAAXW4ManipulationModes_Input_234__Z(v27, 65537);
  __abi_winrt_ptr_dtor(v27);
  __abi_winrt_ptr_dtor(QIItemsControl2_Controls_Xaml_UI_Windows__ItemsPanelRoot_ItemsControl_2345_UE_AAAPE_AAVPanel_2345_XZ);
  __abi_winrt_ptr_dtor(v25);
  v28 = __abi_make_type_id(&_abi_typedesc_Windows_UI_Xaml_Controls_Button);
  v40 = (__int64 (__fastcall *)())v28;
  v29 = (HSTRING)(*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)v47 + 112LL))(v47);
  v47 = v29;
  v30 = __abi_winrt_cast_to(0, v29, _uuidof__AVFrameworkElement_Xaml_UI_Windows__);
  v43 = v30;
  v39 = FindDepthFirstDescendent(v30, v28);
  v31 = (HSTRING)__abi_winrt_cast_to(0, v39, _uuidof__AVButton_Controls_Xaml_UI_Windows__);
  string = v31;
  string = (HSTRING)__abi_winrt_ptr_ctor(v31);
  __abi_winrt_ptr_dtor(v31);
  __abi_winrt_ptr_dtor(v39);
  __abi_winrt_ptr_dtor(v30);
  __abi_winrt_ptr_dtor(v29);
  __abi_winrt_ptr_dtor(v28);
  v32 = string;
  if ( string )
  {
    v47 = 0;
    v33 = WindowsCreateStringReference_0(L"SearchPaneHeader/Text", 0x15u, &v46, &v47);
    if ( v33 < 0 )
      __abi_WinRTraiseException(v33);
    v34 = (HSTRING)LoadResourceStringById(v47);
    v47 = v34;
    v35 = __abi_winrt_cast_to(0, v32, _uuidof__AVDependencyObject_Xaml_UI_Windows__);
    v40 = (__int64 (__fastcall *)())v35;
    Windows::UI::Xaml::Automation::AutomationProperties::SetName(v35, v34);
    __abi_winrt_ptr_dtor(v35);
    WindowsDeleteString_0(v34);
  }
  __abi_winrt_ptr_dtor(v32);
  __abi_winrt_ptr_dtor(v15);
  WindowsDeleteString_0(v10);
  return __abi_winrt_ptr_dtor(v48);
}

```

## disassembly

```asm
0x180065874  mov     rax, rsp
0x180065877  mov     [rax+18h], r8
0x18006587b  mov     [rax+10h], rdx
0x18006587f  mov     [rax+8], rcx
0x180065883  push    rbp
0x180065884  push    rbx
0x180065885  push    rsi
0x180065886  push    rdi
0x180065887  push    r12
0x180065889  push    r13
0x18006588b  push    r14
0x18006588d  push    r15
0x18006588f  lea     rbp, [rax-5Fh]
0x180065893  sub     rsp, 0A8h
0x18006589a  mov     rbx, rcx
0x18006589d  lea     rcx, __abi_typedesc_Windows_UI_Xaml_Controls_TextBox
0x1800658a4  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x1800658aa  mov     r15, rax
0x1800658ad  mov     [rbp+57h+string], rax
0x1800658b1  mov     rdx, [rbx]
0x1800658b4  mov     rcx, rbx
0x1800658b7  mov     rax, [rdx+70h]
0x1800658bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800658c0  mov     r14, rax
0x1800658c3  mov     [rbp+57h+arg_18], rax
0x1800658c7  lea     r8, __uuidof_?AVFrameworkElement@Xaml@UI@Windows@@
0x1800658ce  mov     rdx, rax
0x1800658d1  xor     ecx, ecx
0x1800658d3  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800658d8  mov     rsi, rax
0x1800658db  mov     [rbp+57h+var_90], rax
0x1800658df  mov     rdx, r15
0x1800658e2  mov     rcx, rax
0x1800658e5  call    ?FindDepthFirstDescendent@@YAPE$AAVFrameworkElement@Xaml@UI@Windows@@PE$AAV1234@PE$AAVType@Platform@@@Z; FindDepthFirstDescendent(Windows::UI::Xaml::FrameworkElement *,Platform::Type *)
0x1800658ea  mov     rdi, rax
0x1800658ed  mov     [rbp+57h+var_B0], rax
0x1800658f1  lea     r8, __uuidof_?AVTextBox@Controls@Xaml@UI@Windows@@
0x1800658f8  mov     rdx, rax
0x1800658fb  xor     ecx, ecx
0x1800658fd  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180065902  mov     rbx, rax
0x180065905  mov     [rbp+57h+arg_8], rax
0x180065909  mov     rcx, rax
0x18006590c  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180065911  mov     r13, rax
0x180065914  mov     [rbp+57h+arg_8], rax
0x180065918  mov     rcx, rbx
0x18006591b  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065920  nop
0x180065921  mov     rcx, rdi
0x180065924  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065929  nop
0x18006592a  mov     rcx, rsi
0x18006592d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065932  nop
0x180065933  mov     rcx, r14
0x180065936  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18006593b  nop
0x18006593c  mov     rcx, r15
0x18006593f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065944  nop
0x180065945  mov     [rbp+57h+string], 0
0x18006594d  lea     r9, [rbp+57h+string]; string
0x180065951  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180065955  mov     edx, 16h; length
0x18006595a  lea     rcx, aScopebuttonFon; "ScopeButton/FontFamily"
0x180065961  call    WindowsCreateStringReference_0
0x180065966  test    eax, eax
0x180065968  jns     short loc_180065972
0x18006596a  mov     ecx, eax; int
0x18006596c  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180065972  mov     rcx, [rbp+57h+string]
0x180065976  call    ?LoadResourceStringById@@YAPE$AAVString@Platform@@PE$AAV12@@Z; LoadResourceStringById(Platform::String *)
0x18006597b  mov     rbx, rax
0x18006597e  mov     [rbp+57h+string], rax
0x180065982  mov     rcx, rax
0x180065985  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18006598a  mov     r12, rax
0x18006598d  mov     [rbp+57h+arg_18], rax
0x180065991  mov     rcx, rbx; string
0x180065994  call    WindowsDeleteString_0
0x180065999  nop
0x18006599a  xor     edx, edx
0x18006599c  mov     rcx, r12
0x18006599f  call    ??9String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator!=(Platform::String *,Platform::String *)
0x1800659a4  test    al, al
0x1800659a6  jz      short loc_1800659F6
0x1800659a8  lea     r8, __uuidof_?AUIControl@Controls@Xaml@UI@Windows@@
0x1800659af  mov     rdx, r13
0x1800659b2  xor     ecx, ecx
0x1800659b4  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800659b9  mov     rdi, rax
0x1800659bc  mov     [rbp+57h+string], rax
0x1800659c0  mov     [rbp+57h+var_B0], 0
0x1800659c8  mov     rdx, r12
0x1800659cb  xor     ecx, ecx
0x1800659cd  call    ??0FontFamily@Media@Xaml@UI@Windows@@QE$AAA@PE$AAVString@Platform@@@Z; Windows::UI::Xaml::Media::FontFamily::FontFamily(Platform::String *)
0x1800659d2  mov     rbx, rax
0x1800659d5  mov     [rbp+57h+var_B0], rax
0x1800659d9  mov     rdx, rax
0x1800659dc  mov     rcx, rdi
0x1800659df  call    ?set@?QIControl@Controls@Xaml@UI@Windows@@FontFamily@Control@2345@UE$AAAXPE$AAV6Media@345@@Z
0x1800659e4  nop
0x1800659e5  mov     rcx, rbx
0x1800659e8  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800659ed  nop
0x1800659ee  mov     rcx, rdi
0x1800659f1  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800659f6  lea     rcx, __abi_typedesc_SearchUI_SuggestionsListView
0x1800659fd  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x180065a03  mov     r15, rax
0x180065a06  mov     [rbp+57h+string], rax
0x180065a0a  mov     rdx, [rbp+57h+arg_0]
0x180065a0e  mov     rcx, [rdx]
0x180065a11  mov     rax, [rcx+70h]
0x180065a15  mov     rcx, rdx
0x180065a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065a1d  mov     r14, rax
0x180065a20  mov     [rbp+57h+var_B0], rax
0x180065a24  lea     r8, __uuidof_?AVFrameworkElement@Xaml@UI@Windows@@
0x180065a2b  mov     rdx, rax
0x180065a2e  xor     ecx, ecx
0x180065a30  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180065a35  mov     rsi, rax
0x180065a38  mov     [rbp+57h+var_90], rax
0x180065a3c  mov     rdx, r15
0x180065a3f  mov     rcx, rax
0x180065a42  call    ?FindDepthFirstDescendent@@YAPE$AAVFrameworkElement@Xaml@UI@Windows@@PE$AAV1234@PE$AAVType@Platform@@@Z; FindDepthFirstDescendent(Windows::UI::Xaml::FrameworkElement *,Platform::Type *)
0x180065a47  mov     rdi, rax
0x180065a4a  mov     [rbp+57h+var_88], rax
0x180065a4e  lea     r8, __uuidof_?AVSuggestionsListView@SearchUI@@
0x180065a55  mov     rdx, rax
0x180065a58  xor     ecx, ecx
0x180065a5a  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180065a5f  mov     rbx, rax
0x180065a62  mov     [rbp+57h+var_80], rax
0x180065a66  mov     rcx, rax
0x180065a69  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180065a6e  mov     r13, rax
0x180065a71  mov     [rbp+57h+var_80], rax
0x180065a75  mov     rcx, rbx
0x180065a78  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065a7d  nop
0x180065a7e  mov     rcx, rdi
0x180065a81  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065a86  nop
0x180065a87  mov     rcx, rsi
0x180065a8a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065a8f  nop
0x180065a90  mov     rcx, r14
0x180065a93  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065a98  nop
0x180065a99  mov     rcx, r15
0x180065a9c  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065aa1  nop
0x180065aa2  mov     rbx, [rbp+57h+arg_0]
0x180065aa6  mov     rax, [rbx]
0x180065aa9  mov     rcx, rbx
0x180065aac  mov     rax, [rax+70h]
0x180065ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ab5  mov     r15, rax
0x180065ab8  mov     [rbp+57h+string], rax
0x180065abc  lea     r8, __uuidof_?AUIUIElement@Xaml@UI@Windows@@
0x180065ac3  mov     rdx, rax
0x180065ac6  xor     ecx, ecx
0x180065ac8  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180065acd  mov     r14, rax
0x180065ad0  mov     [rbp+57h+var_88], rax
0x180065ad4  mov     edx, 130h
0x180065ad9  mov     ecx, 18h
0x180065ade  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x180065ae4  mov     [rbp+57h+var_B0], rax
0x180065ae8  lea     rcx, ?_OnHandledKeyDown@SearchBoxControlBase@SearchUI@@AE$AAAXPE$AAVObject@Platform@@PE$AAVKeyRoutedEventArgs@Input@Xaml@UI@Windows@@@Z; SearchUI::SearchBoxControlBase::_OnHandledKeyDown(Platform::Object *,Windows::UI::Xaml::Input::KeyRoutedEventArgs *)
0x180065aef  mov     [rbp+57h+var_A0], rcx
0x180065af3  mov     [rbp+57h+var_98], 0
0x180065afa  mov     ecx, [rbp+57h+var_94]
0x180065afd  mov     [rbp+57h+var_94], ecx
0x180065b00  lea     r8, [rbp+57h+var_A0]
0x180065b04  mov     rdx, rbx
0x180065b07  mov     rcx, rax
0x180065b0a  call    ??$?0VSearchBoxControlBase@SearchUI@@P801@E$AAAXPE$AAVObject@Platform@@PE$AAVKeyRoutedEventArgs@Input@Xaml@UI@Windows@@@Z@KeyEventHandler@Input@Xaml@UI@Windows@@QE$AAA@PE$AAVSearchBoxControlBase@SearchUI@@P856@E$AAAXPE$AAVObject@Platform@@PE$AAVKeyRoutedEventArgs@1234@@ZW4CallbackContext@8@_N@Z; Windows::UI::Xaml::Input::KeyEventHandler::KeyEventHandler(SearchUI::SearchBoxControlBase *,void (SearchUI::SearchBoxControlBase::*)(Platform::Object *,Windows::UI::Xaml::Input::KeyRoutedEventArgs *),Platform::CallbackContext,bool)
0x180065b0f  mov     rsi, rax
0x180065b12  mov     [rbp+57h+var_B0], rax
0x180065b16  test    rax, rax
0x180065b19  jnz     short loc_180065B1F
0x180065b1b  xor     edi, edi
0x180065b1d  jmp     short loc_180065B3F
0x180065b1f  mov     edx, 50h ; 'P'
0x180065b24  lea     ecx, [rdx-18h]
0x180065b27  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x180065b2d  mov     [rbp+57h+var_90], rax
0x180065b31  mov     rdx, rsi
0x180065b34  mov     rcx, rax
0x180065b37  call    ??0?$CustomBox@PE$AAVKeyEventHandler@Input@Xaml@UI@Windows@@@Details@Platform@@QE$AAA@PE$AAVKeyEventHandler@Input@Xaml@UI@Windows@@@Z; Platform::Details::CustomBox<Windows::UI::Xaml::Input::KeyEventHandler *>::CustomBox<Windows::UI::Xaml::Input::KeyEventHandler *>(Windows::UI::Xaml::Input::KeyEventHandler *)
0x180065b3c  mov     rdi, rax
0x180065b3f  mov     [rbp+57h+var_90], rdi
0x180065b43  call    ?get@KeyDownEvent@UIElement@Xaml@UI@Windows@@SAPE$AAVRoutedEvent@345@XZ; Windows::UI::Xaml::UIElement::KeyDownEvent::get(void)
0x180065b48  mov     rbx, rax
0x180065b4b  mov     [rbp+57h+var_A0], rax
0x180065b4f  mov     r9b, 1
0x180065b52  mov     r8, rdi
0x180065b55  mov     rdx, rax
0x180065b58  mov     rcx, r14
0x180065b5b  call    ?AddHandler@?QIUIElement@Xaml@UI@Windows@@UIElement@234@UE$AAAXPE$AAVRoutedEvent@234@PE$AAVObject@Platform@@_N@Z
0x180065b60  nop
0x180065b61  mov     rcx, rbx
0x180065b64  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065b69  nop
0x180065b6a  mov     rcx, rdi
0x180065b6d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065b72  nop
0x180065b73  mov     rcx, rsi
0x180065b76  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065b7b  nop
0x180065b7c  mov     rcx, r14
0x180065b7f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065b84  nop
0x180065b85  mov     rcx, r15
0x180065b88  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065b8d  test    r13, r13
0x180065b90  jnz     short loc_180065B96
0x180065b92  xor     ecx, ecx
0x180065b94  jmp     short loc_180065B9A
0x180065b96  mov     rcx, [r13+58h]
0x180065b9a  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180065b9f  mov     rsi, rax
0x180065ba2  mov     [rbp+57h+string], rax
0x180065ba6  mov     rcx, rax
0x180065ba9  call    ?get@?QIItemsControl2@Controls@Xaml@UI@Windows@@ItemsPanelRoot@ItemsControl@2345@UE$AAAPE$AAVPanel@2345@XZ
0x180065bae  mov     rdi, rax
0x180065bb1  mov     [rbp+57h+var_A0], rax
0x180065bb5  lea     r8, __uuidof_?AUIUIElement@Xaml@UI@Windows@@
0x180065bbc  mov     rdx, rax
0x180065bbf  xor     ecx, ecx
0x180065bc1  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180065bc6  mov     rbx, rax
0x180065bc9  mov     [rbp+57h+var_88], rax
0x180065bcd  mov     edx, 10001h
0x180065bd2  mov     rcx, rax
0x180065bd5  call    ?set@?QIUIElement@Xaml@UI@Windows@@ManipulationMode@UIElement@234@UE$AAAXW4ManipulationModes@Input@234@@Z
0x180065bda  nop
0x180065bdb  mov     rcx, rbx
0x180065bde  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065be3  nop
0x180065be4  mov     rcx, rdi
0x180065be7  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065bec  nop
0x180065bed  mov     rcx, rsi
0x180065bf0  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065bf5  lea     rcx, __abi_typedesc_Windows_UI_Xaml_Controls_Button
0x180065bfc  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x180065c02  mov     r15, rax
0x180065c05  mov     [rbp+57h+var_A0], rax
0x180065c09  mov     rdx, [rbp+57h+arg_0]
0x180065c0d  mov     rcx, [rdx]
0x180065c10  mov     rax, [rcx+70h]
0x180065c14  mov     rcx, rdx
0x180065c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c1c  mov     r14, rax
0x180065c1f  mov     [rbp+57h+arg_0], rax
0x180065c23  lea     r8, __uuidof_?AVFrameworkElement@Xaml@UI@Windows@@
0x180065c2a  mov     rdx, rax
0x180065c2d  xor     ecx, ecx
0x180065c2f  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180065c34  mov     rsi, rax
0x180065c37  mov     [rbp+57h+var_88], rax
0x180065c3b  mov     rdx, r15
0x180065c3e  mov     rcx, rax
0x180065c41  call    ?FindDepthFirstDescendent@@YAPE$AAVFrameworkElement@Xaml@UI@Windows@@PE$AAV1234@PE$AAVType@Platform@@@Z; FindDepthFirstDescendent(Windows::UI::Xaml::FrameworkElement *,Platform::Type *)
0x180065c46  mov     rdi, rax
0x180065c49  mov     [rbp+57h+var_B0], rax
0x180065c4d  lea     r8, __uuidof_?AVButton@Controls@Xaml@UI@Windows@@
0x180065c54  mov     rdx, rax
0x180065c57  xor     ecx, ecx
0x180065c59  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180065c5e  mov     rbx, rax
0x180065c61  mov     [rbp+57h+string], rax
0x180065c65  mov     rcx, rax
0x180065c68  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180065c6d  mov     [rbp+57h+string], rax
0x180065c71  mov     rcx, rbx
0x180065c74  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065c79  nop
0x180065c7a  mov     rcx, rdi
0x180065c7d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065c82  nop
0x180065c83  mov     rcx, rsi
0x180065c86  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065c8b  nop
0x180065c8c  mov     rcx, r14
0x180065c8f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065c94  nop
0x180065c95  mov     rcx, r15
0x180065c98  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065c9d  nop
0x180065c9e  mov     rsi, [rbp+57h+string]
0x180065ca2  test    rsi, rsi
0x180065ca5  jz      short loc_180065D1A
0x180065ca7  mov     [rbp+57h+arg_0], 0
0x180065caf  lea     r9, [rbp+57h+arg_0]; string
  ... truncated ...
```
