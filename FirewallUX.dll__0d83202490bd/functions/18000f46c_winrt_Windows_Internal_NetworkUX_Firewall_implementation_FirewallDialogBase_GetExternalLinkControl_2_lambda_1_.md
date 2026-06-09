# _winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::GetExternalLinkControl_::_2_::_lambda_1_::operator()

- ea: `0x18000f46c`
- end: `0x18000f657`
- name: `_winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::GetExternalLinkControl_::_2_::_lambda_1_::operator()`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012be0`

## callees

- `0x18000b24c`
- `0x18000b5d0`
- `0x18000cfe4`
- `0x18000d800`
- `0x18000f46c`
- `0x180010430`
- `0x180012c04`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f4e4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f4e4`

## string_xrefs

- `0x18000f639`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::GetExternalLinkControl_::_2_::_lambda_1_::operator()(
        _DWORD *a1,
        _QWORD *a2,
        signed __int64 a3)
{
  int v4; // eax
  const wchar_t *v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  _QWORD *v9; // rbx
  const char *v11; // [rsp+20h] [rbp-40h] BYREF
  __int128 v12; // [rsp+28h] [rbp-38h]
  _DWORD *v13; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v14[4]; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v15; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  __int64 *v17; // [rsp+80h] [rbp+20h] BYREF
  _QWORD *v18; // [rsp+88h] [rbp+28h] BYREF
  _QWORD *v19; // [rsp+90h] [rbp+30h] BYREF
  __int64 *v20; // [rsp+98h] [rbp+38h]

  v19 = (_QWORD *)a3;
  v18 = a2;
  if ( a1[2] )
  {
    if ( a1[2] != 1 )
      wil::details::in1diag3::FailFast_UnexpectedMsg(
        retaddr,
        (void *)0x3B,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
        "Unexpected dialog type",
        v11);
    v4 = 1;
  }
  else
  {
    v4 = 0;
  }
  LODWORD(v19) = 16;
  HIDWORD(v19) = v4;
  NetworkingTriageScenario::FirewallUX::LinkClicked((const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v19);
  if ( *(_QWORD *)a1 )
    v5 = *(const wchar_t **)(*(_QWORD *)a1 + 16LL);
  else
    v5 = &szFile;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  if ( (_DWORD)v6 )
  {
    if ( v5[(unsigned int)v6] )
      abort();
    v14[0] = 1;
    v14[1] = v6;
    v15 = v5;
    v13 = v14;
  }
  else
  {
    v13 = 0;
  }
  v18 = &v13;
  v17 = &qword_18003C238;
  _InterlockedIncrement64(&qword_18003C238);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> )
  {
    v18 = 0;
    LODWORD(v11) = 0;
    v12 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
                                                                 + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
           v13,
           &v18);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v11);
    v19 = v18;
    _InterlockedDecrement64(&qword_18003C238);
  }
  else
  {
    _InterlockedDecrement64(&qword_18003C238);
    ___call_AEAV_lambda_216____0___0Uri_Foundation_Windows_winrt__QEAA_AEBUhstring_param_5__Z____factory_cache_entry_UUri_Foundation_Windows_winrt__UIUriRuntimeClassFactory_234__impl_winrt__QEAA_A_PAEAV_lambda_216____0___0Uri_Foundation_Windows_2_QEAA_AEBUhstring_param_2__Z__Z(
      0,
      (signed __int64 *)&v19,
      &v18);
  }
  v17 = (__int64 *)&v19;
  v20 = &qword_18003C258;
  _InterlockedIncrement64(&qword_18003C258);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics> )
  {
    v18 = 0;
    LODWORD(v11) = 0;
    v12 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>
                                                                 + 64LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>,
           v19,
           &v18);
    if ( v8 < 0 )
      winrt::throw_hresult((unsigned int)v8, &v11);
    v9 = v18;
    _InterlockedDecrement64(&qword_18003C258);
  }
  else
  {
    _InterlockedDecrement64(&qword_18003C258);
    ___call_AEAV_lambda_1___1__LaunchUriAsync_Launcher_System_Windows_winrt__SA_AEBUUri_Foundation_56__Z____factory_cache_entry_ULauncher_System_Windows_winrt__UILauncherStatics_234__impl_winrt__QEAA_A_PAEAV_lambda_1___1__LaunchUriAsync_Launcher_System_Windows_2_SA_AEBUUri_Foundation_72__Z__Z(
      0,
      (signed __int64 *)&v18,
      &v17);
    v9 = v18;
  }
  if ( v19 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v19);
  if ( !v9 )
    return 2147500037LL;
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v18);
  return 0;
}

```

## disassembly

```asm
0x18000f46c  mov     [rsp-18h+arg_10], r8
0x18000f471  mov     [rsp-18h+arg_8], rdx
0x18000f476  push    rbp
0x18000f477  push    rbx
0x18000f478  push    rdi
0x18000f479  mov     rbp, rsp
0x18000f47c  sub     rsp, 60h
0x18000f480  mov     rbx, rcx
0x18000f483  xor     edi, edi
0x18000f485  cmp     [rcx+8], edi
0x18000f488  jnz     short loc_18000F48E
0x18000f48a  mov     eax, edi
0x18000f48c  jmp     short loc_18000F49D
0x18000f48e  cmp     dword ptr [rcx+8], 1
0x18000f492  jnz     loc_18000F62E
0x18000f498  mov     eax, 1
0x18000f49d  mov     dword ptr [rbp+arg_10], 10h
0x18000f4a4  mov     dword ptr [rbp+arg_10+4], eax
0x18000f4a7  lea     rcx, [rbp+arg_10]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x18000f4ab  call    ?LinkClicked@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@@Z; NetworkingTriageScenario::FirewallUX::LinkClicked(NetworkingTriageScenario::FirewallUX::RequiredFields const &)
0x18000f4b0  mov     rdx, [rbx]
0x18000f4b3  test    rdx, rdx
0x18000f4b6  jz      short loc_18000F4BE
0x18000f4b8  mov     rdx, [rdx+10h]
0x18000f4bc  jmp     short loc_18000F4C5
0x18000f4be  lea     rdx, szFile
0x18000f4c5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000f4c9  inc     rcx
0x18000f4cc  cmp     [rdx+rcx*2], di
0x18000f4d0  jnz     short loc_18000F4C9
0x18000f4d2  test    ecx, ecx
0x18000f4d4  jnz     short loc_18000F4DC
0x18000f4d6  mov     [rbp+var_28], rdi
0x18000f4da  jmp     short loc_18000F501
0x18000f4dc  mov     eax, ecx
0x18000f4de  cmp     [rdx+rax*2], di
0x18000f4e2  jz      short loc_18000F4EB
0x18000f4e4  call    cs:__imp_abort
0x18000f4eb  mov     [rbp+var_20], 1
0x18000f4f2  mov     [rbp+var_1C], ecx
0x18000f4f5  mov     [rbp+var_10], rdx
0x18000f4f9  lea     rax, [rbp+var_20]
0x18000f4fd  mov     [rbp+var_28], rax
0x18000f501  lea     rax, [rbp+var_28]
0x18000f505  mov     [rbp+arg_8], rax
0x18000f509  lea     rax, qword_18003C238
0x18000f510  mov     [rbp+arg_0], rax
0x18000f514  lock inc cs:qword_18003C238
0x18000f51c  mov     rcx, cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18000f523  test    rcx, rcx
0x18000f526  jz      short loc_18000F565
0x18000f528  mov     [rbp+arg_8], rdi
0x18000f52c  mov     dword ptr [rbp+var_40], edi
0x18000f52f  xorps   xmm0, xmm0
0x18000f532  movdqu  [rbp+var_38], xmm0
0x18000f537  mov     rax, [rcx]
0x18000f53a  lea     r8, [rbp+arg_8]
0x18000f53e  mov     rdx, [rbp+var_28]
0x18000f542  mov     rax, [rax+30h]
0x18000f546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f54b  test    eax, eax
0x18000f54d  js      loc_18000F64B
0x18000f553  mov     rax, [rbp+arg_8]
0x18000f557  mov     [rbp+arg_10], rax
0x18000f55b  lock dec cs:qword_18003C238
0x18000f563  jmp     short loc_18000F57B
0x18000f565  lock dec cs:qword_18003C238
0x18000f56d  lea     r8, [rbp+arg_8]
0x18000f571  lea     rdx, [rbp+arg_10]
0x18000f575  call    ??$call@AEAV_lambda_216__@?0???0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@5@@Z@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_216__@?0???0Uri@Foundation@Windows@2@QEAA@AEBUhstring@param@2@@Z@@Z
0x18000f57a  nop
0x18000f57b  lea     rax, [rbp+arg_10]
0x18000f57f  mov     [rbp+arg_0], rax
0x18000f583  lea     rax, qword_18003C258
0x18000f58a  mov     [rbp+arg_18], rax
0x18000f58e  lock inc cs:qword_18003C258
0x18000f596  mov     rcx, cs:??$factory_cache_entry_v@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@impl@winrt@@3U?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@12@A; factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>::winrt::factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>
0x18000f59d  test    rcx, rcx
0x18000f5a0  jz      short loc_18000F5DB
0x18000f5a2  mov     [rbp+arg_8], rdi
0x18000f5a6  mov     dword ptr [rbp+var_40], edi
0x18000f5a9  xorps   xmm0, xmm0
0x18000f5ac  movdqu  [rbp+var_38], xmm0
0x18000f5b1  mov     rax, [rcx]
0x18000f5b4  lea     r8, [rbp+arg_8]
0x18000f5b8  mov     rdx, [rbp+arg_10]
0x18000f5bc  mov     rax, [rax+40h]
0x18000f5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5c5  test    eax, eax
0x18000f5c7  js      short loc_18000F622
0x18000f5c9  mov     rbx, [rbp+arg_8]
0x18000f5cd  mov     [rbp+arg_8], rbx
0x18000f5d1  lock dec cs:qword_18003C258
0x18000f5d9  jmp     short loc_18000F5F4
0x18000f5db  lock dec cs:qword_18003C258
0x18000f5e3  lea     r8, [rbp+arg_0]
0x18000f5e7  lea     rdx, [rbp+arg_8]
0x18000f5eb  call    ??$call@AEAV_lambda_1_@?1??LaunchUriAsync@Launcher@System@Windows@winrt@@SA@AEBUUri@Foundation@56@@Z@@?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??LaunchUriAsync@Launcher@System@Windows@2@SA@AEBUUri@Foundation@72@@Z@@Z
0x18000f5f0  mov     rbx, [rbp+arg_8]
0x18000f5f4  cmp     [rbp+arg_10], rdi
0x18000f5f8  jz      short loc_18000F603
0x18000f5fa  lea     rcx, [rbp+arg_10]
0x18000f5fe  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000f603  test    rbx, rbx
0x18000f606  jnz     short loc_18000F615
0x18000f608  mov     eax, 80004005h
0x18000f60d  add     rsp, 60h
0x18000f611  pop     rdi
0x18000f612  pop     rbx
0x18000f613  pop     rbp
0x18000f614  retn
0x18000f615  lea     rcx, [rbp+arg_8]
0x18000f619  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000f61e  xor     eax, eax
0x18000f620  jmp     short loc_18000F60D
0x18000f622  lea     rdx, [rbp+var_40]
0x18000f626  mov     ecx, eax
0x18000f628  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000f62e  mov     rcx, [rbp+18h]; this
0x18000f632  lea     r9, aUnexpectedDial; "Unexpected dialog type"
0x18000f639  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\networkux\\firewall"...
0x18000f640  mov     edx, 3Bh ; ';'; void *
0x18000f645  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x18000f64b  lea     rdx, [rbp+var_40]
0x18000f64f  mov     ecx, eax
0x18000f651  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
