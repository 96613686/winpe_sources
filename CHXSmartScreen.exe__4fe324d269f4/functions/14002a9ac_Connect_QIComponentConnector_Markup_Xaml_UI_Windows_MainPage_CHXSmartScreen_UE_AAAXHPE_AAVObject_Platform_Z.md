# ?Connect@?QIComponentConnector@Markup@Xaml@UI@Windows@@MainPage@CHXSmartScreen@@UE$AAAXHPE$AAVObject@Platform@@@Z

- ea: `0x14002a9ac`
- end: `0x14002ab2d`
- name: `?Connect@?QIComponentConnector@Markup@Xaml@UI@Windows@@MainPage@CHXSmartScreen@@UE$AAAXHPE$AAVObject@Platform@@@Z`
- size: `385`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011480`
- `0x140017320`

## callees

- `0x1400086b0`
- `0x140027e5c`
- `0x14002a9ac`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002aa53`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002aa53`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall _Connect__QIComponentConnector_Markup_Xaml_UI_Windows__MainPage_CHXSmartScreen__UE_AAAXHPE_AAVObject_Platform___Z(
        __int64 a1,
        int a2,
        __int64 (__fastcall ***a3)(_QWORD, __int64 *, __int64 *))
{
  __int64 (__fastcall ***v3)(_QWORD, __int64 *, _QWORD *); // r9
  __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rdi
  int v8; // eax
  __int64 v9; // rsi
  int v10; // eax
  __int64 (__fastcall *v11)(); // [rsp+30h] [rbp-50h] BYREF
  int v12; // [rsp+38h] [rbp-48h]
  __int64 v13; // [rsp+40h] [rbp-40h] BYREF
  void *v14; // [rsp+48h] [rbp-38h]
  __int64 v15; // [rsp+50h] [rbp-30h]
  __int64 v16; // [rsp+58h] [rbp-28h]
  __int64 v17; // [rsp+60h] [rbp-20h] BYREF
  __int64 v18; // [rsp+68h] [rbp-18h] BYREF

  v3 = a3;
  if ( a2 == 1 )
  {
    v5 = 0;
    v17 = 0;
    if ( a3 )
    {
      v6 = (**a3)(a3, _uuidof__AVUIElement_Xaml_UI_Windows__, &v17);
      if ( v6 < 0 )
        __abi_WinRTraiseException(v6);
      v5 = v17;
    }
    v15 = v5;
    v7 = 0;
    v18 = 0;
    if ( v5 )
    {
      v8 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *, __int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *)))v5)(
             v5,
             _uuidof__AUIUIElement5_Xaml_UI_Windows__,
             &v18,
             v3);
      if ( v8 < 0 )
        __abi_WinRTraiseException(v8);
      v7 = v18;
    }
    v16 = v7;
    v14 = Platform::Details::Heap::Allocate(0x18u, 0x130u);
    v11 = CHXSmartScreen::MainPage::onGettingFocus;
    v12 = 0;
    v9 = Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::UIElement __gc *,Windows::UI::Xaml::Input::GettingFocusEventArgs __gc *>::TypedEventHandler<Windows::UI::Xaml::UIElement __gc *,Windows::UI::Xaml::Input::GettingFocusEventArgs __gc *>(
           v14,
           a1,
           &v11);
    v14 = (void *)v9;
    v13 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v7 + 216LL))(v7, v9, &v13);
    if ( v10 < 0 )
      __abi_WinRTraiseException(v10);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  *(_BYTE *)(a1 + 368) = 1;
}

```

## disassembly

```asm
0x14002a9ac  mov     [rsp-18h+arg_8], rbx
0x14002a9b1  mov     [rsp-18h+arg_18], rsi
0x14002a9b6  push    rbp
0x14002a9b7  push    rdi
0x14002a9b8  push    r14
0x14002a9ba  mov     rbp, rsp
0x14002a9bd  sub     rsp, 80h
0x14002a9c4  mov     rax, cs:__security_cookie
0x14002a9cb  xor     rax, rsp
0x14002a9ce  mov     [rbp+var_10], rax
0x14002a9d2  mov     r9, r8
0x14002a9d5  mov     r14, rcx
0x14002a9d8  cmp     edx, 1
0x14002a9db  jnz     loc_14002AAE9
0x14002a9e1  xor     ebx, ebx
0x14002a9e3  mov     [rbp+var_20], rbx
0x14002a9e7  test    r8, r8
0x14002a9ea  jz      short loc_14002AA11
0x14002a9ec  mov     rax, [r8]
0x14002a9ef  lea     r8, [rbp+var_20]
0x14002a9f3  lea     rdx, __uuidof_?AVUIElement@Xaml@UI@Windows@@
0x14002a9fa  mov     rcx, r9
0x14002a9fd  mov     rax, [rax]
0x14002aa00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa05  test    eax, eax
0x14002aa07  js      loc_14002AB1D
0x14002aa0d  mov     rbx, [rbp+var_20]
0x14002aa11  mov     [rbp+var_30], rbx
0x14002aa15  xor     edi, edi
0x14002aa17  mov     [rbp+var_18], rdi
0x14002aa1b  test    rbx, rbx
0x14002aa1e  jz      short loc_14002AA45
0x14002aa20  mov     rax, [rbx]
0x14002aa23  lea     r8, [rbp+var_18]
0x14002aa27  lea     rdx, __uuidof_?AUIUIElement5@Xaml@UI@Windows@@
0x14002aa2e  mov     rcx, rbx
0x14002aa31  mov     rax, [rax]
0x14002aa34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa39  test    eax, eax
0x14002aa3b  js      loc_14002AB25
0x14002aa41  mov     rdi, [rbp+var_18]
0x14002aa45  mov     [rbp+var_28], rdi
0x14002aa49  mov     edx, 130h
0x14002aa4e  mov     ecx, 18h
0x14002aa53  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x14002aa59  mov     [rbp+var_38], rax
0x14002aa5d  lea     rcx, ?onGettingFocus@MainPage@CHXSmartScreen@@AE$AAAXPE$AAVUIElement@Xaml@UI@Windows@@PE$AAVGettingFocusEventArgs@Input@456@@Z; CHXSmartScreen::MainPage::onGettingFocus(Windows::UI::Xaml::UIElement *,Windows::UI::Xaml::Input::GettingFocusEventArgs *)
0x14002aa64  mov     [rbp+var_50], rcx
0x14002aa68  mov     [rbp+var_48], 0
0x14002aa6f  mov     ecx, [rbp+var_44]
0x14002aa72  mov     [rbp+var_44], ecx
0x14002aa75  lea     r8, [rbp+var_50]
0x14002aa79  mov     rdx, r14
0x14002aa7c  mov     rcx, rax
0x14002aa7f  call    ??$?0VMainPage@CHXSmartScreen@@P801@E$AAAXPE$AAVUIElement@Xaml@UI@Windows@@PE$AAVGettingFocusEventArgs@Input@345@@Z@?$TypedEventHandler@PE$AAVUIElement@Xaml@UI@Windows@@PE$AAVGettingFocusEventArgs@Input@234@@Foundation@Windows@@QE$AAA@PE$AAVMainPage@CHXSmartScreen@@P834@E$AAAXPE$AAVUIElement@Xaml@UI@2@PE$AAVGettingFocusEventArgs@Input@672@@ZW4CallbackContext@Platform@@_N@Z; Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::UIElement *,Windows::UI::Xaml::Input::GettingFocusEventArgs *>::TypedEventHandler<Windows::UI::Xaml::UIElement *,Windows::UI::Xaml::Input::GettingFocusEventArgs *>(CHXSmartScreen::MainPage *,void (CHXSmartScreen::MainPage::*)(Windows::UI::Xaml::UIElement *,Windows::UI::Xaml::Input::GettingFocusEventArgs *),Platform::CallbackContext,bool)
0x14002aa84  mov     rsi, rax
0x14002aa87  mov     [rbp+var_38], rax
0x14002aa8b  mov     [rbp+var_40], 0
0x14002aa93  mov     rcx, [rdi]
0x14002aa96  mov     rax, [rcx+0D8h]
0x14002aa9d  lea     r8, [rbp+var_40]
0x14002aaa1  mov     rdx, rsi
0x14002aaa4  mov     rcx, rdi
0x14002aaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aaac  test    eax, eax
0x14002aaae  js      short loc_14002AB15
0x14002aab0  test    rsi, rsi
0x14002aab3  jz      short loc_14002AAC5
0x14002aab5  mov     rax, [rsi]
0x14002aab8  mov     rcx, rsi
0x14002aabb  mov     rax, [rax+10h]
0x14002aabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aac4  nop
0x14002aac5  mov     rax, [rdi]
0x14002aac8  mov     rcx, rdi
0x14002aacb  mov     rax, [rax+10h]
0x14002aacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aad4  nop
0x14002aad5  test    rbx, rbx
0x14002aad8  jz      short loc_14002AAE9
0x14002aada  mov     rax, [rbx]
0x14002aadd  mov     rcx, rbx
0x14002aae0  mov     rax, [rax+10h]
0x14002aae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aae9  mov     byte ptr [r14+170h], 1
0x14002aaf1  mov     rcx, [rbp+var_10]
0x14002aaf5  xor     rcx, rsp; StackCookie
0x14002aaf8  call    __security_check_cookie
0x14002aafd  lea     r11, [rsp+80h+var_s0]
0x14002ab05  mov     rbx, [r11+28h]
0x14002ab09  mov     rsi, [r11+38h]
0x14002ab0d  mov     rsp, r11
0x14002ab10  pop     r14
0x14002ab12  pop     rdi
0x14002ab13  pop     rbp
0x14002ab14  retn
0x14002ab15  mov     ecx, eax; int
0x14002ab17  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002ab1d  mov     ecx, eax; int
0x14002ab1f  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002ab25  mov     ecx, eax; int
0x14002ab27  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
