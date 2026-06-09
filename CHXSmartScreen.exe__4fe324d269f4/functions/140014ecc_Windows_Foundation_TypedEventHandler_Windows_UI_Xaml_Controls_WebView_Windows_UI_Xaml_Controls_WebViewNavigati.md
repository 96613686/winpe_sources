# `Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>(CHXSmartScreen::MainPage *,void (CHXSmartScreen::MainPage::*)(Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *),Platform::CallbackContext,bool)'::`2'::__abi_PointerToMemberWeakRefCapture::__abi_PointerToMemberWeakRefCapture(CHXSmartScreen::MainPage *,void (CHXSmartScreen::MainPage::*)(Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *))

- ea: `0x140014ecc`
- end: `0x140014fb8`
- name: `??0__abi_PointerToMemberWeakRefCapture@?1???$?0VMainPage@CHXSmartScreen@@P801@E$AAAXPE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@3456@@Z@?$TypedEventHandler@PE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@2345@@Foundation@Windows@@QE$AAA@PE$AAVMainPage@CHXSmartScreen@@P845@E$AAAXPE$AAVWebView@Controls@Xaml@UI@3@PE$AAVWebViewNavigationCompletedEventArgs@7893@@ZW4CallbackContext@Platform@@_N@Z@QEAA@03@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012ed8`

## callees

- `0x1400086b0`
- `0x14000c4e0`
- `0x140014ecc`
- `0x140031960`
- `0x140035010`

## pseudocode

```c
__int64 __fastcall `Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>'::`2'::__abi_PointerToMemberWeakRefCapture::__abi_PointerToMemberWeakRefCapture(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, char *, __int64 *),
        _OWORD *a3)
{
  __int64 (__fastcall ***v4)(_QWORD, char *, _QWORD *); // r9
  __int64 v6; // rdi
  int v7; // eax
  __int64 WeakReference; // rax
  __int64 v9; // rbx
  __int64 v12; // [rsp+38h] [rbp-30h] BYREF

  v4 = a2;
  *(_QWORD *)a1 = `Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>'::`2'::__abi_PointerToMemberWeakRefCapture::`vftable';
  v6 = 0;
  v12 = 0;
  if ( a2 )
  {
    v7 = (**a2)(a2, _uuidof__AUIWeakReferenceSource_Details_Platform__, &v12);
    if ( v7 < 0 )
      __abi_WinRTraiseException(v7);
    v6 = v12;
  }
  WeakReference = Platform::Details::IWeakReferenceSource::GetWeakReference(v6, a2, a3, v4, a1, v6);
  v9 = WeakReference;
  if ( WeakReference )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)WeakReference + 8LL))(WeakReference);
  *(_QWORD *)(a1 + 8) = v9;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  *(_OWORD *)(a1 + 16) = *a3;
  return a1;
}

```

## disassembly

```asm
0x140014ecc  mov     r11, rsp
0x140014ecf  mov     [r11+18h], rbx
0x140014ed3  push    rbp
0x140014ed4  push    rsi
0x140014ed5  push    rdi
0x140014ed6  sub     rsp, 50h
0x140014eda  mov     rax, cs:__security_cookie
0x140014ee1  xor     rax, rsp
0x140014ee4  mov     [rsp+68h+var_28], rax
0x140014ee9  mov     rbp, r8
0x140014eec  mov     r9, rdx
0x140014eef  mov     rsi, rcx
0x140014ef2  mov     [r11-48h], rcx
0x140014ef6  lea     rax, ??_7__abi_PointerToMemberWeakRefCapture@?1???$?0VMainPage@CHXSmartScreen@@P801@E$AAAXPE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@3456@@Z@?$TypedEventHandler@PE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@2345@@Foundation@Windows@@QE$AAA@PE$AAVMainPage@CHXSmartScreen@@P845@E$AAAXPE$AAVWebView@Controls@Xaml@UI@3@PE$AAVWebViewNavigationCompletedEventArgs@7893@@ZW4CallbackContext@Platform@@_N@Z@6B@; const `Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>(CHXSmartScreen::MainPage *,void (CHXSmartScreen::MainPage::*)(Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *),Platform::CallbackContext,bool)'::`2'::__abi_PointerToMemberWeakRefCapture::`vftable'
0x140014efd  mov     [rcx], rax
0x140014f00  xor     edi, edi
0x140014f02  mov     [r11-30h], rdi
0x140014f06  test    rdx, rdx
0x140014f09  jz      short loc_140014F31
0x140014f0b  mov     rax, [rdx]
0x140014f0e  lea     r8, [r11-30h]
0x140014f12  lea     rdx, __uuidof_?AUIWeakReferenceSource@Details@Platform@@
0x140014f19  mov     rcx, r9
0x140014f1c  mov     rax, [rax]
0x140014f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f24  test    eax, eax
0x140014f26  js      loc_140014FB0
0x140014f2c  mov     rdi, [rsp+68h+var_30]
0x140014f31  mov     [rsp+68h+var_40], rdi
0x140014f36  mov     rcx, rdi
0x140014f39  call    ?GetWeakReference@IWeakReferenceSource@Details@Platform@@UE$AAAPE$AAUIWeakReference@23@XZ; Platform::Details::IWeakReferenceSource::GetWeakReference(void)
0x140014f3e  mov     rbx, rax
0x140014f41  mov     [rsp+68h+var_38], rax
0x140014f46  test    rax, rax
0x140014f49  jz      short loc_140014F5A
0x140014f4b  mov     rax, [rax]
0x140014f4e  mov     rcx, rbx
0x140014f51  mov     rax, [rax+8]
0x140014f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f5a  mov     [rsi+8], rbx
0x140014f5e  test    rbx, rbx
0x140014f61  jz      short loc_140014F73
0x140014f63  mov     rax, [rbx]
0x140014f66  mov     rcx, rbx
0x140014f69  mov     rax, [rax+10h]
0x140014f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f72  nop
0x140014f73  test    rdi, rdi
0x140014f76  jz      short loc_140014F87
0x140014f78  mov     rdx, [rdi]
0x140014f7b  mov     rcx, rdi
0x140014f7e  mov     rax, [rdx+10h]
0x140014f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f87  movaps  xmm0, xmmword ptr [rbp+0]
0x140014f8b  movdqu  xmmword ptr [rsi+10h], xmm0
0x140014f90  mov     rax, rsi
0x140014f93  mov     rcx, [rsp+68h+var_28]
0x140014f98  xor     rcx, rsp; StackCookie
0x140014f9b  call    __security_check_cookie
0x140014fa0  mov     rbx, [rsp+68h+arg_10]
0x140014fa8  add     rsp, 50h
0x140014fac  pop     rdi
0x140014fad  pop     rsi
0x140014fae  pop     rbp
0x140014faf  retn
0x140014fb0  mov     ecx, eax; int
0x140014fb2  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
