# MakeWinUI2ControlsResources(void)

- ea: `0x180030eec`
- end: `0x180030fc0`
- name: `?MakeWinUI2ControlsResources@@YA?AUResourceDictionary@Xaml@UI@Windows@winrt@@XZ`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800318d4`

## callees

- `0x180002b20`
- `0x1800049ac`
- `0x18001047c`
- `0x18001c864`
- `0x18002eb74`
- `0x1800301b0`
- `0x180030eec`
- `0x1800325dc`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180030f40`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180030f40`

## string_xrefs

- `0x180030f51`: `pcshell\shell\uxframe\dll\SystemXamlApplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MakeWinUI2ControlsResources(__int64 a1)
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
    L"Microsoft.UI.Xaml.Controls.XamlControlsResources",
    0x31u,
    0x30u);
  v2 = RoActivateInstance(v7, &v8);
  if ( v2 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlApplication.cpp",
      (const char *)(unsigned int)v2,
      v5[0]);
  v5[0] = 0;
  winrt::copy_from_abi((winrt *)v5, v8, v3);
  winrt::impl::as<winrt::Windows::UI::Xaml::ResourceDictionary,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
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
0x180030eec  mov     [rsp-8+arg_8], rbx
0x180030ef1  push    rbp
0x180030ef2  mov     rbp, rsp
0x180030ef5  sub     rsp, 60h
0x180030ef9  mov     rax, cs:__security_cookie
0x180030f00  xor     rax, rsp
0x180030f03  mov     [rbp+var_8], rax
0x180030f07  mov     rbx, rcx
0x180030f0a  mov     [rbp+var_10], rcx
0x180030f0e  mov     [rbp+var_10], 0
0x180030f16  mov     [rbp+var_18], 0
0x180030f1e  mov     r9d, 30h ; '0'; unsigned int
0x180030f24  lea     r8d, [r9+1]; unsigned int
0x180030f28  lea     rdx, sourceString; "Microsoft.UI.Xaml.Controls.XamlControls"...
0x180030f2f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180030f33  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180030f38  lea     rdx, [rbp+var_10]
0x180030f3c  mov     rcx, [rbp+var_18]
0x180030f40  call    cs:__imp_RoActivateInstance
0x180030f46  mov     rcx, [rbp+8]; this
0x180030f4a  test    eax, eax
0x180030f4c  jns     short loc_180030F63
0x180030f4e  mov     r9d, eax; char *
0x180030f51  lea     r8, aPcshellShellUx_9; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x180030f58  mov     edx, 19h; void *
0x180030f5d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180030f63  mov     [rbp+var_40], 0
0x180030f6b  mov     rdx, [rbp+var_10]; struct IUnknown *
0x180030f6f  lea     rcx, [rbp+var_40]; this
0x180030f73  call    ?copy_from_abi@winrt@@YAXAEAUIUnknown@Foundation@Windows@1@PEAX@Z; winrt::copy_from_abi(winrt::Windows::Foundation::IUnknown &,void *)
0x180030f78  mov     rdx, [rbp+var_40]
0x180030f7c  mov     rcx, rbx
0x180030f7f  call    ??$as@UResourceDictionary@Xaml@UI@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@5@$0A@@impl@winrt@@YA?AUResourceDictionary@Xaml@UI@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::UI::Xaml::ResourceDictionary,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180030f84  nop
0x180030f85  cmp     [rbp+var_40], 0
0x180030f8a  jz      short loc_180030F96
0x180030f8c  lea     rcx, [rbp+var_40]
0x180030f90  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180030f95  nop
0x180030f96  cmp     [rbp+var_10], 0
0x180030f9b  jz      short loc_180030FA6
0x180030f9d  lea     rcx, [rbp+var_10]
0x180030fa1  call    ?unconditional_release_ref@?$com_ptr@UIDesktopWindowXamlSourceNative@@@winrt@@AEAAXXZ; winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(void)
0x180030fa6  mov     rax, rbx
0x180030fa9  mov     rcx, [rbp+var_8]
0x180030fad  xor     rcx, rsp; StackCookie
0x180030fb0  call    __security_check_cookie
0x180030fb5  mov     rbx, [rsp+60h+arg_8]
0x180030fba  add     rsp, 60h
0x180030fbe  pop     rbp
0x180030fbf  retn
```
