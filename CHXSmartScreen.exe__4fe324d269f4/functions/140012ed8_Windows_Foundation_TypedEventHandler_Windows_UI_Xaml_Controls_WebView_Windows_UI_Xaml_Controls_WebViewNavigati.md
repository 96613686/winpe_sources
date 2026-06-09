# Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>(CHXSmartScreen::MainPage *,void (CHXSmartScreen::MainPage::*)(Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *),Platform::CallbackContext,bool)

- ea: `0x140012ed8`
- end: `0x140012f7d`
- name: `??$?0VMainPage@CHXSmartScreen@@P801@E$AAAXPE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@3456@@Z@?$TypedEventHandler@PE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@2345@@Foundation@Windows@@QE$AAA@PE$AAVMainPage@CHXSmartScreen@@P834@E$AAAXPE$AAVWebView@Controls@Xaml@UI@2@PE$AAVWebViewNavigationCompletedEventArgs@6782@@ZW4CallbackContext@Platform@@_N@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017f94`

## callees

- `0x140012ed8`
- `0x140014ecc`
- `0x140035010`

## import_xrefs

- `wincorlib!??0Delegate@Platform@@QE$AAA@XZ` at `0x140012ef2`
- `wincorlib!??0Delegate@Platform@@QE$AAA@XZ` at `0x140012ef2`

## pseudocode

```c
_QWORD *__fastcall Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>(
        _QWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, char *, __int64 *),
        _OWORD *a3)
{
  __int64 v6; // rax
  _OWORD v8[3]; // [rsp+30h] [rbp-38h] BYREF

  Platform::Delegate::Delegate(a1 + 2);
  *a1 = &Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>::`vftable'{for `__abi_IUnknown'};
  a1[1] = &Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>::`vftable'{for `Platform::Object'};
  a1[2] = &Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>::`vftable';
  a1[4] = -1;
  if ( __abi_module )
    (**(void (__fastcall ***)(struct __abi_Module *))__abi_module)(__abi_module);
  a1[37] = a1 + 5;
  if ( a1 == (_QWORD *)-40LL )
  {
    v6 = 0;
  }
  else
  {
    v8[0] = *a3;
    v6 = `Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>'::`2'::__abi_PointerToMemberWeakRefCapture::__abi_PointerToMemberWeakRefCapture(
           (__int64)(a1 + 5),
           a2,
           v8);
  }
  a1[37] = v6;
  return a1;
}

```

## disassembly

```asm
0x140012ed8  mov     [rsp+arg_0], rcx
0x140012edd  push    rbx
0x140012ede  push    rbp
0x140012edf  push    rsi
0x140012ee0  push    rdi
0x140012ee1  sub     rsp, 48h
0x140012ee5  mov     rsi, r8
0x140012ee8  mov     rbp, rdx
0x140012eeb  mov     rdi, rcx
0x140012eee  add     rcx, 10h
0x140012ef2  call    cs:__imp_??0Delegate@Platform@@QE$AAA@XZ; Platform::Delegate::Delegate(void)
0x140012ef8  lea     rax, ??_7?$TypedEventHandler@PE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@2345@@Foundation@Windows@@6B__abi_IUnknown@@@; const Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>::`vftable'{for `__abi_IUnknown'}
0x140012eff  mov     [rdi], rax
0x140012f02  lea     rax, ??_7?$TypedEventHandler@PE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@2345@@Foundation@Windows@@6BObject@Platform@@@; const Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>::`vftable'{for `Platform::Object'}
0x140012f09  mov     [rdi+8], rax
0x140012f0d  lea     rax, ??_7?$TypedEventHandler@PE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@2345@@Foundation@Windows@@6B@; const Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>::`vftable'
0x140012f14  mov     [rdi+10h], rax
0x140012f18  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x140012f20  mov     rcx, cs:?__abi_module@@3PEAU__abi_Module@@EA; __abi_Module * __abi_module
0x140012f27  test    rcx, rcx
0x140012f2a  jz      short loc_140012F38
0x140012f2c  mov     rax, [rcx]
0x140012f2f  mov     rax, [rax]
0x140012f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f37  nop
0x140012f38  lea     rbx, [rdi+28h]
0x140012f3c  mov     [rbx+100h], rbx
0x140012f43  mov     [rsp+68h+var_48], rbx
0x140012f48  test    rbx, rbx
0x140012f4b  jz      short loc_140012F68
0x140012f4d  movaps  xmm0, xmmword ptr [rsi]
0x140012f50  movdqa  [rsp+68h+var_38], xmm0
0x140012f56  lea     r8, [rsp+68h+var_38]
0x140012f5b  mov     rdx, rbp
0x140012f5e  mov     rcx, rbx
0x140012f61  call    ??0__abi_PointerToMemberWeakRefCapture@?1???$?0VMainPage@CHXSmartScreen@@P801@E$AAAXPE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@3456@@Z@?$TypedEventHandler@PE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@2345@@Foundation@Windows@@QE$AAA@PE$AAVMainPage@CHXSmartScreen@@P845@E$AAAXPE$AAVWebView@Controls@Xaml@UI@3@PE$AAVWebViewNavigationCompletedEventArgs@7893@@ZW4CallbackContext@Platform@@_N@Z@QEAA@03@Z; `Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>(CHXSmartScreen::MainPage *,void (CHXSmartScreen::MainPage::*)(Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *),Platform::CallbackContext,bool)'::`2'::__abi_PointerToMemberWeakRefCapture::__abi_PointerToMemberWeakRefCapture(CHXSmartScreen::MainPage *,void (CHXSmartScreen::MainPage::*)(Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *))
0x140012f66  jmp     short loc_140012F6A
0x140012f68  xor     eax, eax
0x140012f6a  mov     [rbx+100h], rax
0x140012f71  mov     rax, rdi
0x140012f74  add     rsp, 48h
0x140012f78  pop     rdi
0x140012f79  pop     rsi
0x140012f7a  pop     rbp
0x140012f7b  pop     rbx
0x140012f7c  retn
```
