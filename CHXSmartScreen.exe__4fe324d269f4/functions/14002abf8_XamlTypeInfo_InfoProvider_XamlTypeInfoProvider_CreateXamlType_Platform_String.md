# XamlTypeInfo::InfoProvider::XamlTypeInfoProvider::CreateXamlType(Platform::String *)

- ea: `0x14002abf8`
- end: `0x14002aecf`
- name: `?CreateXamlType@XamlTypeInfoProvider@InfoProvider@XamlTypeInfo@@QE$AAAPE$AAUIXamlType@Markup@Xaml@UI@Windows@@PE$AAVString@Platform@@@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140025610`

## callees

- `0x140003986`
- `0x1400039aa`
- `0x1400086b0`
- `0x140024a40`
- `0x140024b24`
- `0x140025610`
- `0x14002abf8`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002ac6f`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002ad16`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002adad`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002ac6f`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002ad16`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002adad`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HSTRING __fastcall XamlTypeInfo::InfoProvider::XamlTypeInfoProvider::CreateXamlType(__int64 a1, HSTRING a2)
{
  HRESULT v4; // eax
  HSTRING v5; // rax
  HSTRING v6; // rdi
  HSTRING v7; // rbx
  HRESULT v9; // eax
  HSTRING v10; // rax
  HRESULT v11; // eax
  void *v12; // rsi
  HRESULT v13; // eax
  HSTRING XamlTypeByName; // rdi
  __int64 v15; // rax
  __int64 v16; // rbx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  INT32 result[2]; // [rsp+40h] [rbp-10h] BYREF

  string = 0;
  v4 = WindowsCreateStringReference_0(L"Windows.UI.Xaml.Controls.Page", 0x1Du, &hstringHeader, &string);
  if ( v4 < 0 )
    __abi_WinRTraiseException(v4);
  result[0] = 0;
  WindowsCompareStringOrdinal_0(a2, string, result);
  if ( !result[0] )
  {
    string = (HSTRING)Platform::Details::Heap::Allocate(0x30u, 0x48u);
    v5 = (HSTRING)XamlTypeInfo::InfoProvider::XamlSystemBaseType::XamlSystemBaseType(string, a2);
    v6 = v5;
    string = v5;
    if ( !v5 )
    {
      v7 = 0;
      goto LABEL_7;
    }
    v7 = v5 + 2;
    if ( v5 != (HSTRING)-8LL )
      goto LABEL_5;
    goto LABEL_7;
  }
  string = 0;
  v9 = WindowsCreateStringReference_0(L"Windows.UI.Xaml.Controls.UserControl", 0x24u, &hstringHeader, &string);
  if ( v9 < 0 )
    __abi_WinRTraiseException(v9);
  result[0] = 0;
  WindowsCompareStringOrdinal_0(a2, string, result);
  if ( !result[0] )
  {
    string = (HSTRING)Platform::Details::Heap::Allocate(0x30u, 0x48u);
    v10 = (HSTRING)XamlTypeInfo::InfoProvider::XamlSystemBaseType::XamlSystemBaseType(string, a2);
    v6 = v10;
    string = v10;
    if ( !v10 )
    {
      v7 = 0;
      goto LABEL_7;
    }
    v7 = v10 + 2;
    if ( v10 != (HSTRING)-8LL )
LABEL_5:
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v7 + 8LL))(v7);
LABEL_7:
    if ( v6 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
    return v7;
  }
  string = 0;
  v11 = WindowsCreateStringReference_0(L"CHXSmartScreen.MainPage", 0x17u, &hstringHeader, &string);
  if ( v11 < 0 )
    __abi_WinRTraiseException(v11);
  result[0] = 0;
  WindowsCompareStringOrdinal_0(a2, string, result);
  if ( result[0] )
    return 0;
  v12 = Platform::Details::Heap::Allocate(0xA8u, 0xC0u);
  *(_QWORD *)result = v12;
  string = 0;
  v13 = WindowsCreateStringReference_0(L"Windows.UI.Xaml.Controls.Page", 0x1Du, &hstringHeader, &string);
  if ( v13 < 0 )
    __abi_WinRTraiseException(v13);
  XamlTypeByName = (HSTRING)XamlTypeInfo::InfoProvider::XamlTypeInfoProvider::GetXamlTypeByName(a1, string);
  string = XamlTypeByName;
  v15 = XamlTypeInfo::InfoProvider::XamlUserType::XamlUserType(v12, a1, a2, XamlTypeByName);
  v16 = v15;
  *(_QWORD *)result = v15;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  *(_QWORD *)result = v16;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( XamlTypeByName )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)XamlTypeByName + 16LL))(XamlTypeByName);
  *(_DWORD *)(v16 + 64) = 2;
  *(_QWORD *)(v16 + 40) = lambda_f3f2cc067e13cd6d4088930fcfeb937c_::_lambda_invoker_cdecl_;
  *(_BYTE *)(v16 + 103) = 1;
  if ( v16 != -8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v16 + 8) + 8LL))(v16 + 8);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (HSTRING)(v16 + 8);
}

```

## disassembly

```asm
0x14002abf8  mov     [rsp-18h+arg_10], rbx
0x14002abfd  mov     [rsp-18h+arg_18], rsi
0x14002ac02  push    rbp
0x14002ac03  push    rdi
0x14002ac04  push    r14
0x14002ac06  mov     rbp, rsp
0x14002ac09  sub     rsp, 50h
0x14002ac0d  mov     rax, cs:__security_cookie
0x14002ac14  xor     rax, rsp
0x14002ac17  mov     [rbp+var_8], rax
0x14002ac1b  mov     rbx, rdx
0x14002ac1e  mov     r14, rcx
0x14002ac21  mov     [rbp+string], 0
0x14002ac29  lea     r9, [rbp+string]; string
0x14002ac2d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14002ac31  mov     edi, 1Dh
0x14002ac36  mov     edx, edi; length
0x14002ac38  lea     rcx, aWindowsUiXamlC_2; "Windows.UI.Xaml.Controls.Page"
0x14002ac3f  call    WindowsCreateStringReference_0
0x14002ac44  test    eax, eax
0x14002ac46  js      loc_14002AEB7
0x14002ac4c  mov     [rbp+result], 0
0x14002ac53  lea     r8, [rbp+result]; result
0x14002ac57  mov     rdx, [rbp+string]; string2
0x14002ac5b  mov     rcx, rbx; string1
0x14002ac5e  call    WindowsCompareStringOrdinal_0
0x14002ac63  cmp     [rbp+result], 0
0x14002ac67  jnz     short loc_14002ACC8
0x14002ac69  lea     edx, [rdi+2Bh]
0x14002ac6c  lea     ecx, [rdi+13h]
0x14002ac6f  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x14002ac75  mov     [rbp+string], rax
0x14002ac79  mov     rdx, rbx
0x14002ac7c  mov     rcx, rax
0x14002ac7f  call    ??0XamlSystemBaseType@InfoProvider@XamlTypeInfo@@QE$AAA@PE$AAVString@Platform@@@Z; XamlTypeInfo::InfoProvider::XamlSystemBaseType::XamlSystemBaseType(Platform::String *)
0x14002ac84  mov     rdi, rax
0x14002ac87  mov     [rbp+string], rax
0x14002ac8b  test    rax, rax
0x14002ac8e  jz      short loc_14002ACAA
0x14002ac90  lea     rbx, [rax+8]
0x14002ac94  test    rbx, rbx
0x14002ac97  jz      short loc_14002ACAC
0x14002ac99  mov     rcx, [rbx]
0x14002ac9c  mov     rax, [rcx+8]
0x14002aca0  mov     rcx, rbx
0x14002aca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aca8  jmp     short loc_14002ACAC
0x14002acaa  xor     ebx, ebx
0x14002acac  test    rdi, rdi
0x14002acaf  jz      short loc_14002ACC0
0x14002acb1  mov     rcx, [rdi]
0x14002acb4  mov     rax, [rcx+10h]
0x14002acb8  mov     rcx, rdi
0x14002acbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002acc0  mov     rax, rbx
0x14002acc3  jmp     loc_14002AE8E
0x14002acc8  mov     [rbp+string], 0
0x14002acd0  lea     r9, [rbp+string]; string
0x14002acd4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14002acd8  mov     edx, 24h ; '$'; length
0x14002acdd  lea     rcx, aWindowsUiXamlC_0; "Windows.UI.Xaml.Controls.UserControl"
0x14002ace4  call    WindowsCreateStringReference_0
0x14002ace9  test    eax, eax
0x14002aceb  js      loc_14002AEBF
0x14002acf1  mov     [rbp+result], 0
0x14002acf8  lea     r8, [rbp+result]; result
0x14002acfc  mov     rdx, [rbp+string]; string2
0x14002ad00  mov     rcx, rbx; string1
0x14002ad03  call    WindowsCompareStringOrdinal_0
0x14002ad08  cmp     [rbp+result], 0
0x14002ad0c  jnz     short loc_14002AD58
0x14002ad0e  mov     edx, 48h ; 'H'
0x14002ad13  lea     ecx, [rdx-18h]
0x14002ad16  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x14002ad1c  mov     [rbp+string], rax
0x14002ad20  mov     rdx, rbx
0x14002ad23  mov     rcx, rax
0x14002ad26  call    ??0XamlSystemBaseType@InfoProvider@XamlTypeInfo@@QE$AAA@PE$AAVString@Platform@@@Z; XamlTypeInfo::InfoProvider::XamlSystemBaseType::XamlSystemBaseType(Platform::String *)
0x14002ad2b  mov     rdi, rax
0x14002ad2e  mov     [rbp+string], rax
0x14002ad32  test    rax, rax
0x14002ad35  jz      short loc_14002AD51
0x14002ad37  lea     rbx, [rax+8]
0x14002ad3b  test    rbx, rbx
0x14002ad3e  jz      short loc_14002AD53
0x14002ad40  mov     rcx, [rbx]
0x14002ad43  mov     rax, [rcx+8]
0x14002ad47  mov     rcx, rbx
0x14002ad4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ad4f  jmp     short loc_14002AD53
0x14002ad51  xor     ebx, ebx
0x14002ad53  jmp     loc_14002ACAC
0x14002ad58  mov     [rbp+string], 0
0x14002ad60  lea     r9, [rbp+string]; string
0x14002ad64  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14002ad68  mov     edx, 17h; length
0x14002ad6d  lea     rcx, aChxsmartscreen_4; "CHXSmartScreen.MainPage"
0x14002ad74  call    WindowsCreateStringReference_0
0x14002ad79  test    eax, eax
0x14002ad7b  js      loc_14002AEC7
0x14002ad81  mov     [rbp+result], 0
0x14002ad88  lea     r8, [rbp+result]; result
0x14002ad8c  mov     rdx, [rbp+string]; string2
0x14002ad90  mov     rcx, rbx; string1
0x14002ad93  call    WindowsCompareStringOrdinal_0
0x14002ad98  cmp     [rbp+result], 0
0x14002ad9c  jz      short loc_14002ADA5
0x14002ad9e  xor     eax, eax
0x14002ada0  jmp     loc_14002AE8E
0x14002ada5  mov     edx, 0C0h
0x14002adaa  lea     ecx, [rdx-18h]
0x14002adad  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x14002adb3  mov     rsi, rax
0x14002adb6  mov     qword ptr [rbp+result], rax
0x14002adba  mov     [rbp+string], 0
0x14002adc2  lea     r9, [rbp+string]; string
0x14002adc6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14002adca  mov     edx, edi; length
0x14002adcc  lea     rcx, aWindowsUiXamlC_2; "Windows.UI.Xaml.Controls.Page"
0x14002add3  call    WindowsCreateStringReference_0
0x14002add8  test    eax, eax
0x14002adda  js      loc_14002AEAF
0x14002ade0  mov     rdx, [rbp+string]
0x14002ade4  mov     rcx, r14
0x14002ade7  call    ?GetXamlTypeByName@XamlTypeInfoProvider@InfoProvider@XamlTypeInfo@@QE$AAAPE$AAUIXamlType@Markup@Xaml@UI@Windows@@PE$AAVString@Platform@@@Z; XamlTypeInfo::InfoProvider::XamlTypeInfoProvider::GetXamlTypeByName(Platform::String *)
0x14002adec  mov     rdi, rax
0x14002adef  mov     [rbp+string], rax
0x14002adf3  mov     r9, rax
0x14002adf6  mov     r8, rbx
0x14002adf9  mov     rdx, r14
0x14002adfc  mov     rcx, rsi
0x14002adff  call    ??0XamlUserType@InfoProvider@XamlTypeInfo@@QE$AAA@PE$AAVXamlTypeInfoProvider@12@PE$AAVString@Platform@@PE$AAUIXamlType@Markup@Xaml@UI@Windows@@@Z; XamlTypeInfo::InfoProvider::XamlUserType::XamlUserType(XamlTypeInfo::InfoProvider::XamlTypeInfoProvider *,Platform::String *,Windows::UI::Xaml::Markup::IXamlType *)
0x14002ae04  mov     rbx, rax
0x14002ae07  mov     qword ptr [rbp+result], rax
0x14002ae0b  test    rax, rax
0x14002ae0e  jz      short loc_14002AE1F
0x14002ae10  mov     rcx, [rax]
0x14002ae13  mov     rax, [rcx+8]
0x14002ae17  mov     rcx, rbx
0x14002ae1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae1f  mov     qword ptr [rbp+result], rbx
0x14002ae23  test    rbx, rbx
0x14002ae26  jz      short loc_14002AE38
0x14002ae28  mov     rax, [rbx]
0x14002ae2b  mov     rcx, rbx
0x14002ae2e  mov     rax, [rax+10h]
0x14002ae32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae37  nop
0x14002ae38  test    rdi, rdi
0x14002ae3b  jz      short loc_14002AE4D
0x14002ae3d  mov     rax, [rdi]
0x14002ae40  mov     rcx, rdi
0x14002ae43  mov     rax, [rax+10h]
0x14002ae47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae4c  nop
0x14002ae4d  mov     dword ptr [rbx+40h], 2
0x14002ae54  lea     rax, _lambda_f3f2cc067e13cd6d4088930fcfeb937c____lambda_invoker_cdecl_
0x14002ae5b  mov     [rbx+28h], rax
0x14002ae5f  mov     byte ptr [rbx+67h], 1
0x14002ae63  lea     rdi, [rbx+8]
0x14002ae67  test    rdi, rdi
0x14002ae6a  jz      short loc_14002AE7C
0x14002ae6c  mov     rcx, [rdi]
0x14002ae6f  mov     rax, [rcx+8]
0x14002ae73  mov     rcx, rdi
0x14002ae76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae7b  nop
0x14002ae7c  mov     rcx, [rbx]
0x14002ae7f  mov     rax, [rcx+10h]
0x14002ae83  mov     rcx, rbx
0x14002ae86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae8b  mov     rax, rdi
0x14002ae8e  mov     rcx, [rbp+var_8]
0x14002ae92  xor     rcx, rsp; StackCookie
0x14002ae95  call    __security_check_cookie
0x14002ae9a  lea     r11, [rsp+50h+var_s0]
0x14002ae9f  mov     rbx, [r11+30h]
0x14002aea3  mov     rsi, [r11+38h]
0x14002aea7  mov     rsp, r11
0x14002aeaa  pop     r14
0x14002aeac  pop     rdi
0x14002aead  pop     rbp
0x14002aeae  retn
0x14002aeaf  mov     ecx, eax; int
0x14002aeb1  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002aeb7  mov     ecx, eax; int
0x14002aeb9  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002aebf  mov     ecx, eax; int
0x14002aec1  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002aec7  mov     ecx, eax; int
0x14002aec9  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
