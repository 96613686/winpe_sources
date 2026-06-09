# Platform::Details::CustomBox<Windows::UI::Xaml::Visibility>::ToStringInternal<1>(void)

- ea: `0x18004e1a4`
- end: `0x18004e2ca`
- name: `??$ToStringInternal@$00@?$CustomBox@W4Visibility@Xaml@UI@Windows@@@Details@Platform@@AE$AAAPE$AAVString@2@XZ`
- size: `294`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800553e0`

## callees

- `0x1800033d2`
- `0x1800033de`
- `0x18000b6b8`
- `0x18000b908`
- `0x18000b928`
- `0x18004e1a4`

## import_xrefs

- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x18004e276`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x18004e276`
- `wincorlib!?get@FullName@Type@Platform@@QE$AAAPE$AAVString@3@XZ` at `0x18004e286`
- `wincorlib!?get@FullName@Type@Platform@@QE$AAAPE$AAVString@3@XZ` at `0x18004e286`

## pseudocode

```c
__int64 __fastcall Platform::Details::CustomBox<enum Windows::UI::Xaml::Visibility>::ToStringInternal<1>(__int64 a1)
{
  int v1; // edx
  HRESULT v2; // eax
  HRESULT v3; // eax
  HRESULT v4; // eax
  HSTRING v5; // rbx
  HSTRING v6; // rdi
  __int64 v7; // rbx
  __int64 type_id; // rsi
  HSTRING v10; // rbx
  __int64 v11; // rdi
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-50h] BYREF
  HSTRING_HEADER v13; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER v14; // [rsp+50h] [rbp-20h] BYREF
  HSTRING string; // [rsp+90h] [rbp+20h] BYREF
  __int64 v16; // [rsp+98h] [rbp+28h]
  HSTRING v17; // [rsp+A0h] [rbp+30h]

  v1 = *(_DWORD *)(a1 + 48);
  string = 0;
  if ( v1 )
  {
    if ( v1 == 1 )
    {
      v3 = WindowsCreateStringReference_0(L"Collapsed", 9u, &v13, &string);
      if ( v3 < 0 )
        __abi_WinRTraiseException(v3);
    }
    else
    {
      v2 = WindowsCreateStringReference_0(L"Windows.UI.Xaml.Visibility", 0x1Au, &hstringHeader, &string);
      if ( v2 < 0 )
        __abi_WinRTraiseException(v2);
    }
  }
  else
  {
    v4 = WindowsCreateStringReference_0(L"Visible", 7u, &v14, &string);
    if ( v4 < 0 )
      __abi_WinRTraiseException(v4);
  }
  v5 = (HSTRING)__abi_winrt_ptrto_string_ctor(string);
  string = v5;
  v6 = (HSTRING)__abi_winrt_ptrto_string_ctor(v5);
  string = v6;
  WindowsDeleteString_0(v5);
  if ( v6 )
  {
    v7 = __abi_winrt_ptrto_string_ctor(v6);
    WindowsDeleteString_0(v6);
    return v7;
  }
  else
  {
    type_id = __abi_make_type_id(&_abi_typedesc_Windows_UI_Xaml_Visibility);
    v16 = type_id;
    v10 = (HSTRING)Platform::Type::FullName::get(type_id);
    v17 = v10;
    v11 = __abi_winrt_ptrto_string_ctor(v10);
    WindowsDeleteString_0(v10);
    __abi_winrt_ptr_dtor(type_id);
    WindowsDeleteString_0(0);
    return v11;
  }
}

```

## disassembly

```asm
0x18004e1a4  mov     [rsp-18h+arg_18], rbx
0x18004e1a9  push    rbp
0x18004e1aa  push    rsi
0x18004e1ab  push    rdi
0x18004e1ac  mov     rbp, rsp
0x18004e1af  sub     rsp, 70h
0x18004e1b3  mov     edx, [rcx+30h]
0x18004e1b6  xor     esi, esi
0x18004e1b8  mov     [rbp+string], rsi
0x18004e1bc  lea     r9, [rbp+string]; string
0x18004e1c0  test    edx, edx
0x18004e1c2  jz      short loc_18004E209
0x18004e1c4  cmp     edx, 1
0x18004e1c7  jz      short loc_18004E1E8
0x18004e1c9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004e1cd  lea     edx, [rsi+1Ah]; length
0x18004e1d0  lea     rcx, aWindowsUiXamlV; "Windows.UI.Xaml.Visibility"
0x18004e1d7  call    WindowsCreateStringReference_0
0x18004e1dc  test    eax, eax
0x18004e1de  jns     short loc_18004E22A
0x18004e1e0  mov     ecx, eax; int
0x18004e1e2  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18004e1e8  lea     r8, [rbp+var_38]; hstringHeader
0x18004e1ec  mov     edx, 9; length
0x18004e1f1  lea     rcx, aCollapsed; "Collapsed"
0x18004e1f8  call    WindowsCreateStringReference_0
0x18004e1fd  test    eax, eax
0x18004e1ff  jns     short loc_18004E22A
0x18004e201  mov     ecx, eax; int
0x18004e203  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18004e209  lea     r8, [rbp+var_20]; hstringHeader
0x18004e20d  mov     edx, 7; length
0x18004e212  lea     rcx, aVisible; "Visible"
0x18004e219  call    WindowsCreateStringReference_0
0x18004e21e  test    eax, eax
0x18004e220  jns     short loc_18004E22A
0x18004e222  mov     ecx, eax; int
0x18004e224  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18004e22a  mov     rcx, [rbp+string]
0x18004e22e  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18004e233  mov     rbx, rax
0x18004e236  mov     [rbp+string], rax
0x18004e23a  mov     rcx, rax
0x18004e23d  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18004e242  mov     rdi, rax
0x18004e245  mov     [rbp+string], rax
0x18004e249  mov     rcx, rbx; string
0x18004e24c  call    WindowsDeleteString_0
0x18004e251  nop
0x18004e252  test    rdi, rdi
0x18004e255  jz      short loc_18004E26F
0x18004e257  mov     rcx, rdi
0x18004e25a  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18004e25f  mov     rbx, rax
0x18004e262  mov     rcx, rdi; string
0x18004e265  call    WindowsDeleteString_0
0x18004e26a  mov     rax, rbx
0x18004e26d  jmp     short loc_18004E2BA
0x18004e26f  lea     rcx, __abi_typedesc_Windows_UI_Xaml_Visibility
0x18004e276  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x18004e27c  mov     rsi, rax
0x18004e27f  mov     [rbp+arg_8], rax
0x18004e283  mov     rcx, rax
0x18004e286  call    cs:__imp_?get@FullName@Type@Platform@@QE$AAAPE$AAVString@3@XZ; Platform::Type::FullName::get(void)
0x18004e28c  mov     rbx, rax
0x18004e28f  mov     [rbp+arg_10], rax
0x18004e293  mov     rcx, rax
0x18004e296  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18004e29b  mov     rdi, rax
0x18004e29e  mov     rcx, rbx; string
0x18004e2a1  call    WindowsDeleteString_0
0x18004e2a6  nop
0x18004e2a7  mov     rcx, rsi
0x18004e2aa  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004e2af  nop
0x18004e2b0  xor     ecx, ecx; string
0x18004e2b2  call    WindowsDeleteString_0
0x18004e2b7  mov     rax, rdi
0x18004e2ba  mov     rbx, [rsp+70h+arg_18]
0x18004e2c2  add     rsp, 70h
0x18004e2c6  pop     rdi
0x18004e2c7  pop     rsi
0x18004e2c8  pop     rbp
0x18004e2c9  retn
```
