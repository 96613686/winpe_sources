# SystemXamlHostBehavior::OnWindowMessage(uint,unsigned __int64,__int64)

- ea: `0x180047790`
- end: `0x18004783f`
- name: `?OnWindowMessage@SystemXamlHostBehavior@@UEAA?AW4WindowMessageHandlingResult@@I_K_J@Z`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800041c4`
- `0x18001049c`
- `0x18003e32c`
- `0x180041928`
- `0x180045888`
- `0x180047790`
- `0x1800486e0`

## import_xrefs

- `USER32!SetFocus` at `0x1800477ea`
- `USER32!SetFocus` at `0x1800477ea`

## string_xrefs

- `0x1800477b1`: `pcshell\shell\uxframe\dll\SystemXamlHostBehavior.h`

## pseudocode

```c
__int64 __fastcall SystemXamlHostBehavior::OnWindowMessage(__int64 a1, int a2, __int64 a3, const char *a4)
{
  unsigned int v6; // edi
  __int64 v7; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-18h] BYREF
  _BYTE v10[16]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v12; // [rsp+40h] [rbp+8h] BYREF

  if ( !*(_QWORD *)(a1 + 56) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x43,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlHostBehavior.h",
      a4);
  v6 = 0;
  if ( a2 == 6 )
  {
    SystemXamlHostBehavior::FailFastIfMidInitialization((SystemXamlHostBehavior *)a1);
    if ( a3 && *(_QWORD *)(a1 + 72) )
    {
      SetFocus(*(HWND *)(a1 + 64));
      v6 = 1;
      v12 = 1;
      v7 = winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest::XamlSourceFocusNavigationRequest(
             (winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest *)v10,
             (const enum winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationReason *)&v12);
      winrt::impl::consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(
        a1 + 72,
        v9,
        v7);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)v9);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)v10);
    }
  }
  else if ( a2 == 71 )
  {
    SystemXamlHostBehavior::PositionXamlSourceWindow((SystemXamlHostBehavior *)a1);
  }
  return v6;
}

```

## disassembly

```asm
0x180047790  mov     [rsp+arg_8], rbx
0x180047795  mov     [rsp+arg_10], rsi
0x18004779a  push    rdi
0x18004779b  sub     rsp, 30h
0x18004779f  mov     rsi, r8
0x1800477a2  mov     rbx, rcx
0x1800477a5  cmp     qword ptr [rcx+38h], 0
0x1800477aa  jnz     short loc_1800477C3
0x1800477ac  mov     rcx, [rsp+38h]; this
0x1800477b1  lea     r8, aPcshellShellUx_3; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x1800477b8  mov     edx, 43h ; 'C'; void *
0x1800477bd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800477c3  xor     edi, edi
0x1800477c5  cmp     edx, 6
0x1800477c8  jz      short loc_1800477D6
0x1800477ca  cmp     edx, 47h ; 'G'
0x1800477cd  jnz     short loc_18004782D
0x1800477cf  call    ?PositionXamlSourceWindow@SystemXamlHostBehavior@@AEAAXXZ; SystemXamlHostBehavior::PositionXamlSourceWindow(void)
0x1800477d4  jmp     short loc_18004782D
0x1800477d6  call    ?FailFastIfMidInitialization@SystemXamlHostBehavior@@AEAAXXZ; SystemXamlHostBehavior::FailFastIfMidInitialization(void)
0x1800477db  test    rsi, rsi
0x1800477de  jz      short loc_18004782D
0x1800477e0  cmp     [rbx+48h], rdi
0x1800477e4  jz      short loc_18004782D
0x1800477e6  mov     rcx, [rbx+40h]; hWnd
0x1800477ea  call    cs:__imp_SetFocus
0x1800477f0  mov     edi, 1
0x1800477f5  mov     [rsp+38h+arg_0], edi
0x1800477f9  lea     rdx, [rsp+38h+arg_0]; enum winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationReason *
0x1800477fe  lea     rcx, [rsp+38h+var_10]; this
0x180047803  call    ??0XamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@QEAA@AEBW4XamlSourceFocusNavigationReason@12345@@Z; winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest::XamlSourceFocusNavigationRequest(winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationReason const &)
0x180047808  mov     r8, rax
0x18004780b  lea     rdx, [rsp+38h+var_18]
0x180047810  lea     rcx, [rbx+48h]
0x180047814  call    ?NavigateFocus@?$consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest const &)
0x180047819  lea     rcx, [rsp+38h+var_18]; this
0x18004781e  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180047823  lea     rcx, [rsp+38h+var_10]; this
0x180047828  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004782d  mov     eax, edi
0x18004782f  mov     rbx, [rsp+38h+arg_8]
0x180047834  mov     rsi, [rsp+38h+arg_10]
0x180047839  add     rsp, 30h
0x18004783d  pop     rdi
0x18004783e  retn
```
