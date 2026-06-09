# Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>::__abi_GetRuntimeClassName(HSTRING__ * *)

- ea: `0x14001f4c0`
- end: `0x14001f4d4`
- name: `?__abi_GetRuntimeClassName@?$TypedEventHandler@PE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@2345@@Foundation@Windows@@UE$AAAJPEAPEAUHSTRING__@@@Z`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001f4e0`
- `0x14001f4f0`

## callees

- `0x140002850`

## string_xrefs

- `0x14001f4c3`: `Windows.Foundation.TypedEventHandler`2<Windows.UI.Xaml.Controls.WebView, Windows.UI.Xaml.Controls.WebViewNavigationCompletedEventArgs>`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>::__abi_GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(
           L"Windows.Foundation.TypedEventHandler`2<Windows.UI.Xaml.Controls.WebView, Windows.UI.Xaml.Controls.WebViewNavi"
            "gationCompletedEventArgs>",
           0x86u,
           a2);
}

```

## disassembly

```asm
0x14001f4c0  mov     r8, rdx; string
0x14001f4c3  lea     rcx, aWindowsFoundat_10; "Windows.Foundation.TypedEventHandler`2<"...
0x14001f4ca  mov     edx, 86h; length
0x14001f4cf  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
