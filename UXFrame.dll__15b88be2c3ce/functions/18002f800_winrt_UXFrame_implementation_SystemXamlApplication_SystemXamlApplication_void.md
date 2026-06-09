# winrt::UXFrame::implementation::SystemXamlApplication::SystemXamlApplication(void)

- ea: `0x18002f800`
- end: `0x18002f8bb`
- name: `??0SystemXamlApplication@implementation@UXFrame@winrt@@QEAA@XZ`
- size: `187`
- prototype: `_QWORD(winrt::UXFrame::implementation::SystemXamlApplication *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f038`

## callees

- `0x1800041c4`
- `0x180017024`
- `0x18002e754`
- `0x18002f3d8`
- `0x18002f798`
- `0x18002f800`
- `0x1800303b8`
- `0x180030fc8`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-7!AddDependencyToProcessPackageGraph` at `0x18002f843`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!AddDependencyToProcessPackageGraph` at `0x18002f843`

## string_xrefs

- `0x18002f855`: `pcshell\shell\uxframe\dll\SystemXamlApplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
winrt::UXFrame::implementation::SystemXamlApplication *__fastcall winrt::UXFrame::implementation::SystemXamlApplication::SystemXamlApplication(
        winrt::UXFrame::implementation::SystemXamlApplication *this)
{
  int v2; // eax
  __int64 *WinUI2MetadataProvider; // rax
  _QWORD *v4; // rdx
  __int64 v5; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v9; // [rsp+38h] [rbp+10h] BYREF

  winrt::UXFrame::implementation::SystemXamlApplication_base<winrt::UXFrame::implementation::SystemXamlApplication,>::SystemXamlApplication_base<winrt::UXFrame::implementation::SystemXamlApplication,>();
  *(_QWORD *)this = &winrt::impl::heap_implements<winrt::UXFrame::implementation::SystemXamlApplication>::`vftable';
  *((_QWORD *)this + 7) = 0;
  std::vector<DirectLaunch::SchemeRegistrationToken>::vector<DirectLaunch::SchemeRegistrationToken>((char *)this + 64);
  v2 = AddDependencyToProcessPackageGraph(L"Microsoft.UI.Xaml.CBS_8wekyb3d8bbwe", 0, 0, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlApplication.cpp",
      (const char *)(unsigned int)v2,
      v7);
  winrt::UXFrame::implementation::SystemXamlApplication::EnableSystemResourceManagerForCurrentProcess(retaddr);
  WinUI2MetadataProvider = (__int64 *)MakeWinUI2MetadataProvider(&v9);
  v4 = (_QWORD *)*((_QWORD *)this + 9);
  if ( v4 == *((_QWORD **)this + 10) )
  {
    std::vector<winrt::Windows::UI::Xaml::Markup::IXamlMetadataProvider>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Markup::IXamlMetadataProvider>(
      (char *)this + 64,
      v4,
      WinUI2MetadataProvider);
  }
  else
  {
    v5 = *WinUI2MetadataProvider;
    *WinUI2MetadataProvider = 0;
    *v4 = v5;
    *((_QWORD *)this + 9) += 8LL;
  }
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v9);
  return this;
}

```

## disassembly

```asm
0x18002f800  mov     [rsp+arg_10], rbx
0x18002f805  mov     [rsp+arg_0], rcx
0x18002f80a  push    rdi; int
0x18002f80b  sub     rsp, 20h
0x18002f80f  mov     rdi, rcx
0x18002f812  call    ??0?$SystemXamlApplication_base@USystemXamlApplication@implementation@UXFrame@winrt@@$$V@implementation@UXFrame@winrt@@QEAA@XZ; winrt::UXFrame::implementation::SystemXamlApplication_base<winrt::UXFrame::implementation::SystemXamlApplication,>::SystemXamlApplication_base<winrt::UXFrame::implementation::SystemXamlApplication,>(void)
0x18002f817  nop
0x18002f818  lea     rax, ??_7?$heap_implements@USystemXamlApplication@implementation@UXFrame@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::UXFrame::implementation::SystemXamlApplication>::`vftable'
0x18002f81f  mov     [rdi], rax
0x18002f822  mov     qword ptr [rdi+38h], 0
0x18002f82a  lea     rcx, [rdi+40h]
0x18002f82e  call    ??0?$vector@VSchemeRegistrationToken@DirectLaunch@@V?$allocator@VSchemeRegistrationToken@DirectLaunch@@@std@@@std@@QEAA@XZ; std::vector<DirectLaunch::SchemeRegistrationToken>::vector<DirectLaunch::SchemeRegistrationToken>(void)
0x18002f833  nop
0x18002f834  xor     r9d, r9d
0x18002f837  xor     r8d, r8d
0x18002f83a  xor     edx, edx
0x18002f83c  lea     rcx, aMicrosoftUiXam_3; "Microsoft.UI.Xaml.CBS_8wekyb3d8bbwe"
0x18002f843  call    cs:__imp_AddDependencyToProcessPackageGraph
0x18002f849  mov     rcx, [rsp+28h]; this
0x18002f84e  test    eax, eax
0x18002f850  jns     short loc_18002F867
0x18002f852  mov     r9d, eax; char *
0x18002f855  lea     r8, aPcshellShellUx_9; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x18002f85c  mov     edx, 8Fh; void *
0x18002f861  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002f867  call    ?EnableSystemResourceManagerForCurrentProcess@SystemXamlApplication@implementation@UXFrame@winrt@@AEAAXXZ; winrt::UXFrame::implementation::SystemXamlApplication::EnableSystemResourceManagerForCurrentProcess(void)
0x18002f86c  lea     rcx, [rsp+28h+arg_8]
0x18002f871  call    ?MakeWinUI2MetadataProvider@@YA?AUIXamlMetadataProvider@Markup@Xaml@UI@Windows@winrt@@XZ; MakeWinUI2MetadataProvider(void)
0x18002f876  nop
0x18002f877  mov     rdx, [rdi+48h]
0x18002f87b  cmp     rdx, [rdi+50h]
0x18002f87f  jz      short loc_18002F895
0x18002f881  mov     rcx, [rax]
0x18002f884  mov     qword ptr [rax], 0
0x18002f88b  mov     [rdx], rcx
0x18002f88e  add     qword ptr [rdi+48h], 8
0x18002f893  jmp     short loc_18002F8A2
0x18002f895  mov     r8, rax
0x18002f898  lea     rcx, [rdi+40h]
0x18002f89c  call    ??$_Emplace_reallocate@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@winrt@@@?$vector@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@winrt@@V?$allocator@UIXamlMetadataProvider@Markup@Xaml@UI@Windows@winrt@@@std@@@std@@AEAAPEAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@winrt@@QEAU234567@$$QEAU234567@@Z; std::vector<winrt::Windows::UI::Xaml::Markup::IXamlMetadataProvider>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Markup::IXamlMetadataProvider>(winrt::Windows::UI::Xaml::Markup::IXamlMetadataProvider * const,winrt::Windows::UI::Xaml::Markup::IXamlMetadataProvider &&)
0x18002f8a1  nop
0x18002f8a2  lea     rcx, [rsp+28h+arg_8]; this
0x18002f8a7  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18002f8ac  nop
0x18002f8ad  mov     rax, rdi
0x18002f8b0  mov     rbx, [rsp+28h+arg_10]
0x18002f8b5  add     rsp, 20h
0x18002f8b9  pop     rdi
0x18002f8ba  retn
```
