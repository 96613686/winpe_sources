# UXFrame::OnContentLoaded(void)

- ea: `0x180045dd0`
- end: `0x180045e8d`
- name: `?OnContentLoaded@UXFrame@@UEAAXXZ`
- size: `189`
- prototype: `void __fastcall(UXFrame *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002b20`
- `0x1800043f4`
- `0x18000d810`
- `0x180017514`
- `0x180020cac`
- `0x18003828c`
- `0x1800408e0`
- `0x1800459a4`
- `0x180045dd0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180045e56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180045e56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UXFrame::OnContentLoaded(winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost **this)
{
  winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost *v2; // rcx
  const wchar_t *v3; // rax
  int v4; // edx
  UXFrame *v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+28h] [rbp-20h] BYREF

  v5 = (UXFrame *)this;
  UXFrameTelemetry::OnContentLoaded<UXFrame *>(&v5);
  v2 = this[26];
  if ( v2 )
    (*(void (__fastcall **)(winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost *))(*(_QWORD *)v2 + 120LL))(v2);
  winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost::ContentInitializationComplete(this[38]);
  winrt::hstring::hstring((winrt::hstring *)&v5, L"ShellUIHostName");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v6, &v5, this + 22);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v5);
  if ( v6 )
  {
    GetCurrentProcessId();
    v3 = winrt::hstring::c_str((winrt::hstring *)&v6);
    NotifyHostReadyWithProcessId(v3, v4);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v6);
}

```

## disassembly

```asm
0x180045dd0  push    rbx
0x180045dd2  sub     rsp, 40h
0x180045dd6  mov     rax, cs:__security_cookie
0x180045ddd  xor     rax, rsp
0x180045de0  mov     [rsp+48h+var_18], rax
0x180045de5  mov     rbx, rcx
0x180045de8  mov     [rsp+48h+var_28], rcx
0x180045ded  lea     rcx, [rsp+48h+var_28]
0x180045df2  call    ??$OnContentLoaded@PEAVUXFrame@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@@Z; UXFrameTelemetry::OnContentLoaded<UXFrame *>(UXFrame * &&)
0x180045df7  mov     rcx, [rbx+0D0h]
0x180045dfe  test    rcx, rcx
0x180045e01  jz      short loc_180045E0F
0x180045e03  mov     rax, [rcx]
0x180045e06  mov     rax, [rax+78h]
0x180045e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e0f  mov     rcx, [rbx+130h]; this
0x180045e16  call    ?ContentInitializationComplete@ShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@QEAAXXZ; winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost::ContentInitializationComplete(void)
0x180045e1b  lea     rdx, aShelluihostnam; "ShellUIHostName"
0x180045e22  lea     rcx, [rsp+48h+var_28]; this
0x180045e27  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180045e2c  nop
0x180045e2d  lea     r8, [rbx+0B0h]
0x180045e34  lea     rdx, [rsp+48h+var_28]
0x180045e39  lea     rcx, [rsp+48h+var_20]
0x180045e3e  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180045e43  nop
0x180045e44  lea     rcx, [rsp+48h+var_28]
0x180045e49  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180045e4e  cmp     [rsp+48h+var_20], 0
0x180045e54  jz      short loc_180045E70
0x180045e56  call    cs:__imp_GetCurrentProcessId
0x180045e5c  mov     edx, eax
0x180045e5e  lea     rcx, [rsp+48h+var_20]; this
0x180045e63  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180045e68  mov     rcx, rax; wchar_t *
0x180045e6b  call    ?NotifyHostReadyWithProcessId@@YA_NPEB_WK@Z; NotifyHostReadyWithProcessId(wchar_t const *,ulong)
0x180045e70  lea     rcx, [rsp+48h+var_20]
0x180045e75  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180045e7a  mov     rcx, [rsp+48h+var_18]
0x180045e7f  xor     rcx, rsp; StackCookie
0x180045e82  call    __security_check_cookie
0x180045e87  add     rsp, 40h
0x180045e8b  pop     rbx
0x180045e8c  retn
```
