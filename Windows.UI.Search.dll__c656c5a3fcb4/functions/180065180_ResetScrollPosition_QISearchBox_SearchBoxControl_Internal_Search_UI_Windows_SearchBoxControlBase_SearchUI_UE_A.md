# ?ResetScrollPosition@?QISearchBox@SearchBoxControl@Internal@Search@UI@Windows@@SearchBoxControlBase@SearchUI@@UE$AAAXXZ

- ea: `0x180065180`
- end: `0x180065312`
- name: `?ResetScrollPosition@?QISearchBox@SearchBoxControl@Internal@Search@UI@Windows@@SearchBoxControlBase@SearchUI@@UE$AAAXXZ`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180065320`

## callees

- `0x18000b818`
- `0x18000b8dc`
- `0x18000b908`
- `0x180065180`
- `0x180065334`
- `0x180076238`
- `0x18007b010`

## import_xrefs

- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180065197`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180065254`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180065197`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180065254`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall _ResetScrollPosition__QISearchBox_SearchBoxControl_Internal_Search_UI_Windows__SearchBoxControlBase_SearchUI__UE_AAAXXZ(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // r15
  __int64 v4; // rbx
  __int64 v5; // r14
  __int64 type_id; // [rsp+70h] [rbp+8h]
  __int64 v8; // [rsp+70h] [rbp+8h]
  __int64 v9; // [rsp+78h] [rbp+10h]
  __int64 v10; // [rsp+78h] [rbp+10h]
  __int64 v11; // [rsp+80h] [rbp+18h]
  __int64 v12; // [rsp+80h] [rbp+18h]
  __int64 DepthFirstDescendent; // [rsp+88h] [rbp+20h]

  type_id = __abi_make_type_id(&_abi_typedesc_SearchUI_SuggestionsListView);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 112LL))(a1);
  v11 = __abi_winrt_cast_to(0, v9, _uuidof__AVFrameworkElement_Xaml_UI_Windows__);
  DepthFirstDescendent = FindDepthFirstDescendent(v11, type_id);
  v2 = __abi_winrt_cast_to(0, DepthFirstDescendent, _uuidof__AVSuggestionsListView_SearchUI__);
  v3 = __abi_winrt_ptr_ctor(v2);
  __abi_winrt_ptr_dtor(v2);
  __abi_winrt_ptr_dtor(DepthFirstDescendent);
  __abi_winrt_ptr_dtor(v11);
  __abi_winrt_ptr_dtor(v9);
  __abi_winrt_ptr_dtor(type_id);
  if ( v3 )
  {
    v8 = __abi_make_type_id(&_abi_typedesc_Windows_UI_Xaml_Controls_ScrollViewer);
    v10 = __abi_winrt_cast_to(0, v3, _uuidof__AVFrameworkElement_Xaml_UI_Windows__);
    v12 = FindDepthFirstDescendent(v10, v8);
    v4 = __abi_winrt_cast_to(0, v12, _uuidof__AVScrollViewer_Controls_Xaml_UI_Windows__);
    v5 = __abi_winrt_ptr_ctor(v4);
    __abi_winrt_ptr_dtor(v4);
    __abi_winrt_ptr_dtor(v12);
    __abi_winrt_ptr_dtor(v10);
    __abi_winrt_ptr_dtor(v8);
    if ( v5 )
      Windows::UI::Xaml::Controls::IScrollViewer::ScrollToVerticalOffset(v5);
    __abi_winrt_ptr_dtor(v5);
  }
  return __abi_winrt_ptr_dtor(v3);
}

```

## disassembly

```asm
0x180065180  push    rbx
0x180065182  push    rbp
0x180065183  push    rsi
0x180065184  push    rdi
0x180065185  push    r14
0x180065187  push    r15
0x180065189  sub     rsp, 38h
0x18006518d  mov     rbx, rcx
0x180065190  lea     rcx, __abi_typedesc_SearchUI_SuggestionsListView
0x180065197  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x18006519d  mov     r14, rax
0x1800651a0  mov     [rsp+68h+arg_0], rax
0x1800651a5  mov     rdx, [rbx]
0x1800651a8  mov     rcx, rbx
0x1800651ab  mov     rax, [rdx+70h]
0x1800651af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651b4  mov     rbp, rax
0x1800651b7  mov     [rsp+68h+arg_8], rax
0x1800651bc  lea     r8, __uuidof_?AVFrameworkElement@Xaml@UI@Windows@@
0x1800651c3  mov     rdx, rax
0x1800651c6  xor     ecx, ecx
0x1800651c8  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800651cd  mov     rsi, rax
0x1800651d0  mov     [rsp+68h+arg_10], rax
0x1800651d8  mov     rdx, r14
0x1800651db  mov     rcx, rax
0x1800651de  call    ?FindDepthFirstDescendent@@YAPE$AAVFrameworkElement@Xaml@UI@Windows@@PE$AAV1234@PE$AAVType@Platform@@@Z; FindDepthFirstDescendent(Windows::UI::Xaml::FrameworkElement *,Platform::Type *)
0x1800651e3  mov     rdi, rax
0x1800651e6  mov     [rsp+68h+arg_18], rax
0x1800651ee  lea     r8, __uuidof_?AVSuggestionsListView@SearchUI@@
0x1800651f5  mov     rdx, rax
0x1800651f8  xor     ecx, ecx
0x1800651fa  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800651ff  mov     rbx, rax
0x180065202  mov     [rsp+68h+var_48], rax
0x180065207  mov     rcx, rax
0x18006520a  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18006520f  mov     r15, rax
0x180065212  mov     [rsp+68h+var_48], rax
0x180065217  mov     rcx, rbx
0x18006521a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18006521f  nop
0x180065220  mov     rcx, rdi
0x180065223  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065228  nop
0x180065229  mov     rcx, rsi
0x18006522c  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065231  nop
0x180065232  mov     rcx, rbp
0x180065235  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18006523a  nop
0x18006523b  mov     rcx, r14
0x18006523e  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065243  nop
0x180065244  test    r15, r15
0x180065247  jz      loc_1800652FE
0x18006524d  lea     rcx, __abi_typedesc_Windows_UI_Xaml_Controls_ScrollViewer
0x180065254  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x18006525a  mov     rbp, rax
0x18006525d  mov     [rsp+68h+arg_0], rax
0x180065262  lea     r8, __uuidof_?AVFrameworkElement@Xaml@UI@Windows@@
0x180065269  mov     rdx, r15
0x18006526c  xor     ecx, ecx
0x18006526e  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x180065273  mov     rsi, rax
0x180065276  mov     [rsp+68h+arg_8], rax
0x18006527b  mov     rdx, rbp
0x18006527e  mov     rcx, rax
0x180065281  call    ?FindDepthFirstDescendent@@YAPE$AAVFrameworkElement@Xaml@UI@Windows@@PE$AAV1234@PE$AAVType@Platform@@@Z; FindDepthFirstDescendent(Windows::UI::Xaml::FrameworkElement *,Platform::Type *)
0x180065286  mov     rdi, rax
0x180065289  mov     [rsp+68h+arg_10], rax
0x180065291  lea     r8, __uuidof_?AVScrollViewer@Controls@Xaml@UI@Windows@@
0x180065298  mov     rdx, rax
0x18006529b  xor     ecx, ecx
0x18006529d  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800652a2  mov     rbx, rax
0x1800652a5  mov     [rsp+68h+arg_18], rax
0x1800652ad  mov     rcx, rax
0x1800652b0  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800652b5  mov     r14, rax
0x1800652b8  mov     [rsp+68h+arg_18], rax
0x1800652c0  mov     rcx, rbx
0x1800652c3  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800652c8  nop
0x1800652c9  mov     rcx, rdi
0x1800652cc  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800652d1  nop
0x1800652d2  mov     rcx, rsi
0x1800652d5  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800652da  nop
0x1800652db  mov     rcx, rbp
0x1800652de  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800652e3  nop
0x1800652e4  test    r14, r14
0x1800652e7  jz      short loc_1800652F5
0x1800652e9  xorps   xmm1, xmm1
0x1800652ec  mov     rcx, r14
0x1800652ef  call    ?ScrollToVerticalOffset@IScrollViewer@Controls@Xaml@UI@Windows@@UE$AAAXN@Z; Windows::UI::Xaml::Controls::IScrollViewer::ScrollToVerticalOffset(double)
0x1800652f4  nop
0x1800652f5  mov     rcx, r14
0x1800652f8  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800652fd  nop
0x1800652fe  mov     rcx, r15
0x180065301  add     rsp, 38h
0x180065305  pop     r15
0x180065307  pop     r14
0x180065309  pop     rdi
0x18006530a  pop     rsi
0x18006530b  pop     rbp
0x18006530c  pop     rbx
0x18006530d  jmp     ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
```
