# MakeWinUI2MetadataProvider(void)

- ea: `0x180030fc8`
- end: `0x18003109c`
- name: `?MakeWinUI2MetadataProvider@@YA?AUIXamlMetadataProvider@Markup@Xaml@UI@Windows@winrt@@XZ`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f800`

## callees

- `0x180002b20`
- `0x1800049ac`
- `0x18001047c`
- `0x18001c864`
- `0x18002eae4`
- `0x1800301b0`
- `0x180030fc8`
- `0x1800325dc`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003101c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003101c`

## string_xrefs

- `0x18003102d`: `pcshell\shell\uxframe\dll\SystemXamlApplication.cpp`

## pseudocode

```c
__int64 __fastcall MakeWinUI2MetadataProvider(__int64 a1)
{
  int v2; // eax
  void *v3; // r8
  __int64 v5[2]; // [rsp+20h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v7; // [rsp+48h] [rbp-18h]
  struct IUnknown *v8; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v8 = 0;
  v7 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Microsoft.UI.Xaml.XamlTypeInfo.XamlControlsXamlMetaDataProvider",
    0x40u,
    0x3Fu);
  v2 = RoActivateInstance(v7, &v8);
  if ( v2 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlApplication.cpp",
      (const char *)(unsigned int)v2,
      v5[0]);
  v5[0] = 0;
  winrt::copy_from_abi((winrt *)v5, v8, v3);
  winrt::impl::as<winrt::Windows::UI::Xaml::Markup::IXamlMetadataProvider,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    a1,
    v5[0]);
  if ( v5[0] )
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(v5);
  if ( v8 )
    winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(&v8);
  return a1;
}

```

## disassembly

```asm
0x180030fc8  mov     [rsp-8+arg_8], rbx
0x180030fcd  push    rbp
0x180030fce  mov     rbp, rsp
0x180030fd1  sub     rsp, 60h
0x180030fd5  mov     rax, cs:__security_cookie
0x180030fdc  xor     rax, rsp
0x180030fdf  mov     [rbp+var_8], rax
0x180030fe3  mov     rbx, rcx
0x180030fe6  mov     [rbp+var_10], rcx
0x180030fea  mov     [rbp+var_10], 0
0x180030ff2  mov     [rbp+var_18], 0
0x180030ffa  mov     r9d, 3Fh ; '?'; unsigned int
0x180031000  lea     r8d, [r9+1]; unsigned int
0x180031004  lea     rdx, aMicrosoftUiXam_1; "Microsoft.UI.Xaml.XamlTypeInfo.XamlCont"...
0x18003100b  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18003100f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180031014  lea     rdx, [rbp+var_10]
0x180031018  mov     rcx, [rbp+var_18]
0x18003101c  call    cs:__imp_RoActivateInstance
0x180031022  mov     rcx, [rbp+8]; this
0x180031026  test    eax, eax
0x180031028  jns     short loc_18003103F
0x18003102a  mov     r9d, eax; char *
0x18003102d  lea     r8, aPcshellShellUx_9; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x180031034  mov     edx, 27h ; '''; void *
0x180031039  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18003103f  mov     [rbp+var_40], 0
0x180031047  mov     rdx, [rbp+var_10]; struct IUnknown *
0x18003104b  lea     rcx, [rbp+var_40]; this
0x18003104f  call    ?copy_from_abi@winrt@@YAXAEAUIUnknown@Foundation@Windows@1@PEAX@Z; winrt::copy_from_abi(winrt::Windows::Foundation::IUnknown &,void *)
0x180031054  mov     rdx, [rbp+var_40]
0x180031058  mov     rcx, rbx
0x18003105b  call    ??$as@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@6@$0A@@impl@winrt@@YA?AUIXamlMetadataProvider@Markup@Xaml@UI@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::UI::Xaml::Markup::IXamlMetadataProvider,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180031060  nop
0x180031061  cmp     [rbp+var_40], 0
0x180031066  jz      short loc_180031072
0x180031068  lea     rcx, [rbp+var_40]
0x18003106c  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180031071  nop
0x180031072  cmp     [rbp+var_10], 0
0x180031077  jz      short loc_180031082
0x180031079  lea     rcx, [rbp+var_10]
0x18003107d  call    ?unconditional_release_ref@?$com_ptr@UIDesktopWindowXamlSourceNative@@@winrt@@AEAAXXZ; winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(void)
0x180031082  mov     rax, rbx
0x180031085  mov     rcx, [rbp+var_8]
0x180031089  xor     rcx, rsp; StackCookie
0x18003108c  call    __security_check_cookie
0x180031091  mov     rbx, [rsp+60h+arg_8]
0x180031096  add     rsp, 60h
0x18003109a  pop     rbp
0x18003109b  retn
```
