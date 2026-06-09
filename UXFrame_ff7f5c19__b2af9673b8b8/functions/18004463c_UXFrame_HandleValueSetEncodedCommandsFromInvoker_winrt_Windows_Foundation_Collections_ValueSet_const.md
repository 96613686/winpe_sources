# UXFrame::HandleValueSetEncodedCommandsFromInvoker(winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x18004463c`
- end: `0x18004472f`
- name: `?HandleValueSetEncodedCommandsFromInvoker@UXFrame@@AEAAXAEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `243`
- prototype: `void(UXFrame *__hidden this, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f494`
- `0x180047050`
- `0x18004dfd0`

## callees

- `0x1800043f4`
- `0x18000d0f0`
- `0x18000d810`
- `0x18001047c`
- `0x180017124`
- `0x180017164`
- `0x18002cad8`
- `0x18003cfe0`
- `0x18004463c`
- `0x180047cb0`
- `0x18004ff8c`
- `0x18005a010`

## string_xrefs

- `0x18004471d`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x180044688`: `LifecycleCommand`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UXFrame::HandleValueSetEncodedCommandsFromInvoker(
        UXFrame *this,
        const struct winrt::Windows::Foundation::Collections::ValueSet *a2)
{
  char IsEnabled; // si
  unsigned int v5; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v8; // [rsp+40h] [rbp+18h] BYREF
  int v9; // [rsp+48h] [rbp+20h] BYREF
  char v10; // [rsp+4Ch] [rbp+24h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59697564>::GetImpl'::`2'::impl)
    || UXFrame::s_VerifyLaunchPayloadIsAllowedForComponent(a2, (UXFrame *)((char *)this + 168)) )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
      goto LABEL_7;
    winrt::hstring::hstring((winrt::hstring *)&v8, L"LifecycleCommand");
    try_get_enum_from_valueset<enum UXFrameHelpers::PropertyKeys::Invocation::LifecycleCommandName>(&v9, &v8, a2);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v8);
    if ( !v10 )
      goto LABEL_7;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl);
    if ( v9 )
    {
      v5 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x5F2,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
        (const char *)v5,
        v6);
    }
    (*(void (__fastcall **)(char *, const struct winrt::Windows::Foundation::Collections::ValueSet *))(*((_QWORD *)this + 2) + 32LL))(
      (char *)this + 16,
      a2);
    if ( !IsEnabled )
LABEL_7:
      winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost::PassMessageToContent(
        *((winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost **)this + 38),
        a2);
  }
}

```

## disassembly

```asm
0x18004463c  mov     [rsp+arg_0], rbx
0x180044641  mov     [rsp+arg_8], rsi
0x180044646  push    rdi; int
0x180044647  sub     rsp, 20h
0x18004464b  mov     rbx, rdx
0x18004464e  mov     rdi, rcx
0x180044651  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59697564@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564> `wil::Feature<__WilFeatureTraits_Feature_59697564>::GetImpl(void)'::`2'::impl
0x180044658  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::__private_IsEnabled(void)
0x18004465d  test    al, al
0x18004465f  jz      short loc_180044678
0x180044661  lea     rdx, [rdi+0A8h]; struct winrt::Windows::Foundation::Collections::ValueSet *
0x180044668  mov     rcx, rbx; struct winrt::Windows::Foundation::Collections::ValueSet *
0x18004466b  call    ?s_VerifyLaunchPayloadIsAllowedForComponent@UXFrame@@CA_NAEBUValueSet@Collections@Foundation@Windows@winrt@@0@Z; UXFrame::s_VerifyLaunchPayloadIsAllowedForComponent(winrt::Windows::Foundation::Collections::ValueSet const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180044670  test    al, al
0x180044672  jz      loc_1800446FB
0x180044678  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18004467f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x180044684  test    al, al
0x180044686  jz      short loc_1800446EC
0x180044688  lea     rdx, aLifecyclecomma; "LifecycleCommand"
0x18004468f  lea     rcx, [rsp+28h+arg_10]; this
0x180044694  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180044699  nop
0x18004469a  mov     r8, rbx
0x18004469d  lea     rdx, [rsp+28h+arg_10]
0x1800446a2  lea     rcx, [rsp+28h+arg_18]
0x1800446a7  call    ??$try_get_enum_from_valueset@W4LifecycleCommandName@Invocation@PropertyKeys@UXFrameHelpers@@@@YA?AV?$optional@W4LifecycleCommandName@Invocation@PropertyKeys@UXFrameHelpers@@@std@@AEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; try_get_enum_from_valueset<UXFrameHelpers::PropertyKeys::Invocation::LifecycleCommandName>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x1800446ac  nop
0x1800446ad  lea     rcx, [rsp+28h+arg_10]
0x1800446b2  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800446b7  cmp     [rsp+28h+arg_1C], 0
0x1800446bc  jz      short loc_1800446EC
0x1800446be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x1800446c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x1800446ca  mov     sil, al
0x1800446cd  cmp     [rsp+28h+arg_18], 0
0x1800446d2  jnz     short loc_18004470B
0x1800446d4  lea     rcx, [rdi+10h]
0x1800446d8  mov     rax, [rcx]
0x1800446db  mov     rdx, rbx
0x1800446de  mov     rax, [rax+20h]
0x1800446e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446e7  test    sil, sil
0x1800446ea  jnz     short loc_1800446FB
0x1800446ec  mov     rdx, rbx; struct winrt::Windows::Foundation::Collections::ValueSet *
0x1800446ef  mov     rcx, [rdi+130h]; this
0x1800446f6  call    ?PassMessageToContent@ShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@QEAAXAEBUValueSet@Collections@Foundation@Windows@6@@Z; winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost::PassMessageToContent(winrt::Windows::Foundation::Collections::ValueSet const &)
0x1800446fb  mov     rbx, [rsp+28h+arg_0]
0x180044700  mov     rsi, [rsp+28h+arg_8]
0x180044705  add     rsp, 20h
0x180044709  pop     rdi
0x18004470a  retn
0x18004470b  mov     ecx, 80070057h
0x180044710  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180044715  mov     r9d, eax; char *
0x180044718  mov     rcx, [rsp+28h]; this
0x18004471d  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x180044724  mov     edx, 5F2h; void *
0x180044729  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
