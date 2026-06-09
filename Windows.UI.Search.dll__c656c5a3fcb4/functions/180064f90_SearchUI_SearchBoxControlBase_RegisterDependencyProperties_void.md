# SearchUI::SearchBoxControlBase::RegisterDependencyProperties(void)

- ea: `0x180064f90`
- end: `0x180065178`
- name: `?RegisterDependencyProperties@SearchBoxControlBase@SearchUI@@SAXXZ`
- size: `488`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002f370`
- `0x1800551b4`

## callees

- `0x1800033d2`
- `0x1800033de`
- `0x18000b6b8`
- `0x18000b888`
- `0x18000b908`
- `0x180064e34`
- `0x180064f90`

## import_xrefs

- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180064fb4`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180064fd9`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x18006508b`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800650b0`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180064fb4`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180064fd9`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x18006508b`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800650b0`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x180064fc8`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x180064fed`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x18006509f`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x1800650c4`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x180064fc8`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x180064fed`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x18006509f`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x1800650c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void SearchUI::SearchBoxControlBase::RegisterDependencyProperties(void)
{
  __int64 type_id; // rdi
  __int128 v1; // xmm6
  __int64 v2; // rsi
  __int128 v3; // xmm7
  HRESULT v4; // eax
  HSTRING v5; // rbx
  __int64 v6; // rdi
  __int128 v7; // xmm6
  __int64 v8; // rsi
  __int128 v9; // xmm7
  HRESULT v10; // eax
  HSTRING v11; // rbx
  HSTRING v12[2]; // [rsp+28h] [rbp-39h] BYREF
  HSTRING v13[2]; // [rsp+38h] [rbp-29h] BYREF
  HSTRING v14[2]; // [rsp+48h] [rbp-19h] BYREF
  HSTRING v15[2]; // [rsp+58h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+7h] BYREF
  HSTRING string; // [rsp+C8h] [rbp+67h] BYREF
  __int64 v18; // [rsp+D0h] [rbp+6Fh]
  __int64 v19; // [rsp+D8h] [rbp+77h]

  type_id = __abi_make_type_id(&_abi_typedesc_SearchUI_SearchBoxControlBase);
  v18 = type_id;
  v1 = *(_OWORD *)Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(v15, type_id);
  v2 = __abi_make_type_id(&_abi_typedesc_Platform_String);
  v19 = v2;
  v3 = *(_OWORD *)Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(v14, v2);
  string = 0;
  v4 = WindowsCreateStringReference_0(L"CueText", 7u, &hstringHeader, &string);
  if ( v4 < 0 )
    __abi_WinRTraiseException(v4);
  *(_OWORD *)v12 = v1;
  *(_OWORD *)v13 = v3;
  v5 = (HSTRING)Windows::UI::Xaml::DependencyProperty::Register(string, v13, v12);
  string = v5;
  __abi_winrt_ptr_assign(&SearchUI::SearchBoxControlBase::s_cueTextProperty, v5);
  __abi_winrt_ptr_dtor(v5);
  WindowsDeleteString_0(v14[0]);
  __abi_winrt_ptr_dtor(v2);
  WindowsDeleteString_0(v15[0]);
  __abi_winrt_ptr_dtor(type_id);
  v6 = __abi_make_type_id(&_abi_typedesc_SearchUI_SearchBoxControlBase);
  v18 = v6;
  v7 = *(_OWORD *)Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(v12, v6);
  v8 = __abi_make_type_id(&_abi_typedesc_Platform_String);
  v19 = v8;
  v9 = *(_OWORD *)Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(v13, v8);
  string = 0;
  v10 = WindowsCreateStringReference_0(L"QueryText", 9u, &hstringHeader, &string);
  if ( v10 < 0 )
    __abi_WinRTraiseException(v10);
  *(_OWORD *)v15 = v7;
  *(_OWORD *)v14 = v9;
  v11 = (HSTRING)Windows::UI::Xaml::DependencyProperty::Register(string, v14, v15);
  string = v11;
  __abi_winrt_ptr_assign(&SearchUI::SearchBoxControlBase::s_queryTextProperty, v11);
  __abi_winrt_ptr_dtor(v11);
  WindowsDeleteString_0(v13[0]);
  __abi_winrt_ptr_dtor(v8);
  WindowsDeleteString_0(v12[0]);
  __abi_winrt_ptr_dtor(v6);
}

```

## disassembly

```asm
0x180064f90  mov     rax, rsp
0x180064f93  mov     [rax+20h], rbx
0x180064f97  push    rbp
0x180064f98  push    rsi
0x180064f99  push    rdi
0x180064f9a  lea     rbp, [rax-5Fh]
0x180064f9e  sub     rsp, 0A0h
0x180064fa5  movaps  xmmword ptr [rax-28h], xmm6
0x180064fa9  movaps  xmmword ptr [rax-38h], xmm7
0x180064fad  lea     rcx, __abi_typedesc_SearchUI_SearchBoxControlBase
0x180064fb4  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x180064fba  mov     rdi, rax
0x180064fbd  mov     [rbp+57h+arg_8], rax
0x180064fc1  mov     rdx, rax
0x180064fc4  lea     rcx, [rbp+57h+var_60]
0x180064fc8  call    cs:__imp_??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z; Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(Platform::Type *)
0x180064fce  nop
0x180064fcf  movups  xmm6, xmmword ptr [rax]
0x180064fd2  lea     rcx, __abi_typedesc_Platform_String
0x180064fd9  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x180064fdf  mov     rsi, rax
0x180064fe2  mov     [rbp+57h+arg_10], rax
0x180064fe6  mov     rdx, rax
0x180064fe9  lea     rcx, [rbp+57h+var_70]
0x180064fed  call    cs:__imp_??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z; Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(Platform::Type *)
0x180064ff3  nop
0x180064ff4  movups  xmm7, xmmword ptr [rax]
0x180064ff7  mov     [rbp+57h+string], 0
0x180064fff  lea     r9, [rbp+57h+string]; string
0x180065003  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180065007  mov     edx, 7; length
0x18006500c  lea     rcx, aCuetext; "CueText"
0x180065013  call    WindowsCreateStringReference_0
0x180065018  test    eax, eax
0x18006501a  jns     short loc_180065024
0x18006501c  mov     ecx, eax; int
0x18006501e  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180065024  movdqu  xmmword ptr [rbp+57h+var_90], xmm6
0x180065029  movdqu  xmmword ptr [rbp+57h+var_80], xmm7
0x18006502e  lea     r8, [rbp+57h+var_90]
0x180065032  lea     rdx, [rbp+57h+var_80]
0x180065036  mov     rcx, [rbp+57h+string]
0x18006503a  call    ?Register@DependencyProperty@Xaml@UI@Windows@@SAPE$AAV1234@PE$AAVString@Platform@@VTypeName@Interop@234@1PE$AAVPropertyMetadata@234@@Z; Windows::UI::Xaml::DependencyProperty::Register(Platform::String *,Windows::UI::Xaml::Interop::TypeName,Windows::UI::Xaml::Interop::TypeName,Windows::UI::Xaml::PropertyMetadata *)
0x18006503f  mov     rbx, rax
0x180065042  mov     [rbp+57h+string], rax
0x180065046  mov     rdx, rax
0x180065049  lea     rcx, ?s_cueTextProperty@SearchBoxControlBase@SearchUI@@0PE$AAVDependencyProperty@Xaml@UI@Windows@@E$AA; Windows::UI::Xaml::DependencyProperty * SearchUI::SearchBoxControlBase::s_cueTextProperty
0x180065050  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x180065055  nop
0x180065056  mov     rcx, rbx
0x180065059  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18006505e  nop
0x18006505f  mov     rcx, [rbp+57h+var_70]; string
0x180065063  call    WindowsDeleteString_0
0x180065068  nop
0x180065069  mov     rcx, rsi
0x18006506c  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065071  nop
0x180065072  mov     rcx, [rbp+57h+var_60]; string
0x180065076  call    WindowsDeleteString_0
0x18006507b  nop
0x18006507c  mov     rcx, rdi
0x18006507f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065084  lea     rcx, __abi_typedesc_SearchUI_SearchBoxControlBase
0x18006508b  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x180065091  mov     rdi, rax
0x180065094  mov     [rbp+57h+arg_8], rax
0x180065098  mov     rdx, rax
0x18006509b  lea     rcx, [rbp+57h+var_90]
0x18006509f  call    cs:__imp_??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z; Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(Platform::Type *)
0x1800650a5  nop
0x1800650a6  movups  xmm6, xmmword ptr [rax]
0x1800650a9  lea     rcx, __abi_typedesc_Platform_String
0x1800650b0  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x1800650b6  mov     rsi, rax
0x1800650b9  mov     [rbp+57h+arg_10], rax
0x1800650bd  mov     rdx, rax
0x1800650c0  lea     rcx, [rbp+57h+var_80]
0x1800650c4  call    cs:__imp_??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z; Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(Platform::Type *)
0x1800650ca  nop
0x1800650cb  movups  xmm7, xmmword ptr [rax]
0x1800650ce  mov     [rbp+57h+string], 0
0x1800650d6  lea     r9, [rbp+57h+string]; string
0x1800650da  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800650de  mov     edx, 9; length
0x1800650e3  lea     rcx, aQuerytext; "QueryText"
0x1800650ea  call    WindowsCreateStringReference_0
0x1800650ef  test    eax, eax
0x1800650f1  jns     short loc_1800650FB
0x1800650f3  mov     ecx, eax; int
0x1800650f5  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800650fb  movdqu  xmmword ptr [rbp+57h+var_60], xmm6
0x180065100  movdqu  xmmword ptr [rbp+57h+var_70], xmm7
0x180065105  lea     r8, [rbp+57h+var_60]
0x180065109  lea     rdx, [rbp+57h+var_70]
0x18006510d  mov     rcx, [rbp+57h+string]
0x180065111  call    ?Register@DependencyProperty@Xaml@UI@Windows@@SAPE$AAV1234@PE$AAVString@Platform@@VTypeName@Interop@234@1PE$AAVPropertyMetadata@234@@Z; Windows::UI::Xaml::DependencyProperty::Register(Platform::String *,Windows::UI::Xaml::Interop::TypeName,Windows::UI::Xaml::Interop::TypeName,Windows::UI::Xaml::PropertyMetadata *)
0x180065116  mov     rbx, rax
0x180065119  mov     [rbp+57h+string], rax
0x18006511d  mov     rdx, rax
0x180065120  lea     rcx, ?s_queryTextProperty@SearchBoxControlBase@SearchUI@@0PE$AAVDependencyProperty@Xaml@UI@Windows@@E$AA; Windows::UI::Xaml::DependencyProperty * SearchUI::SearchBoxControlBase::s_queryTextProperty
0x180065127  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x18006512c  nop
0x18006512d  mov     rcx, rbx
0x180065130  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065135  nop
0x180065136  mov     rcx, [rbp+57h+var_80]; string
0x18006513a  call    WindowsDeleteString_0
0x18006513f  nop
0x180065140  mov     rcx, rsi
0x180065143  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180065148  nop
0x180065149  mov     rcx, [rbp+57h+var_90]; string
0x18006514d  call    WindowsDeleteString_0
0x180065152  nop
0x180065153  mov     rcx, rdi
0x180065156  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18006515b  lea     r11, [rsp+0B0h+var_10]
0x180065163  mov     rbx, [r11+38h]
0x180065167  movaps  xmm6, xmmword ptr [r11-10h]
0x18006516c  movaps  xmm7, xmmword ptr [r11-20h]
0x180065171  mov     rsp, r11
0x180065174  pop     rdi
0x180065175  pop     rsi
0x180065176  pop     rbp
0x180065177  retn
```
