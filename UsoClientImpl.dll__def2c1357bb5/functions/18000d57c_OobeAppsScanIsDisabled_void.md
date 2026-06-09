# OobeAppsScanIsDisabled(void)

- ea: `0x18000d57c`
- end: `0x18000d6a1`
- name: `?OobeAppsScanIsDisabled@@YA_NXZ`
- size: `293`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e654`

## callees

- `0x180009380`
- `0x18000d57c`
- `0x18001932c`
- `0x1800194f8`
- `0x180033f14`
- `0x1800343ec`
- `0x180036b10`

## string_xrefs

- `0x18000d598`: `DisableOobeAppsScan registry value is set`
- `0x18000d62b`: `DisableOobeAppsScan registry value is set`
- `0x18000d68f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
char OobeAppsScanIsDisabled(void)
{
  __int64 traits_2_unsigned_short; // rax
  const char *v1; // r9
  __int64 v2; // r11
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rdx
  char SystemBoolOrDefault; // bl
  void **v7; // rax
  _QWORD Src[4]; // [rsp+30h] [rbp-40h] BYREF
  const wchar_t *v10; // [rsp+50h] [rbp-20h] BYREF
  __int64 v11; // [rsp+58h] [rbp-18h]
  const wchar_t *v12; // [rsp+60h] [rbp-10h] BYREF
  __int64 v13; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  void **v15; // [rsp+80h] [rbp+10h] BYREF

  v15 = &Windows::Registry::`vftable';
  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"DisableOobeAppsScan",
                              L"DisableOobeAppsScan registry value is set",
                              0);
  if ( traits_2_unsigned_short == v2
    || (v3 = -1, v4 = (traits_2_unsigned_short - (__int64)L"DisableOobeAppsScan") >> 1, v4 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v1);
  }
  v5 = -1;
  do
    ++v5;
  while ( SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT[v5] );
  do
    ++v3;
  while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v3] );
  v10 = SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT;
  v11 = v5;
  v12 = SystemInterface::Registry::USOROOT_REDIRECTION_ID;
  v13 = v3;
  Src[0] = L"DisableOobeAppsScan";
  Src[1] = v4;
  SystemBoolOrDefault = SystemInterface::Registry::GetSystemBoolOrDefault(&v15, &v12, &v10, Src);
  if ( SystemBoolOrDefault )
  {
    v12 = 0;
    v10 = L"DisableOobeAppsScan registry value is set";
    v13 = 0;
    v11 = 41;
    v7 = (void **)std::vformat<0>(Src);
    if ( (unsigned __int64)v7[3] > 7 )
      v7 = (void **)*v7;
    v15 = v7;
    ClientTelemetry::Message<wchar_t const *>(&v15);
    std::wstring::~wstring(Src);
  }
  return SystemBoolOrDefault;
}

```

## disassembly

```asm
0x18000d57c  mov     [rsp-8+arg_8], rbx
0x18000d581  mov     [rsp-8+arg_10], rdi
0x18000d586  push    rbp
0x18000d587  mov     rbp, rsp
0x18000d58a  sub     rsp, 70h
0x18000d58e  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x18000d595  xor     r8d, r8d
0x18000d598  lea     r11, aDisableoobeapp; "DisableOobeAppsScan registry value is s"...
0x18000d59f  mov     [rbp+arg_0], rax
0x18000d5a3  lea     rbx, aDisableoobeapp_0; "DisableOobeAppsScan"
0x18000d5aa  mov     rdx, r11
0x18000d5ad  mov     rcx, rbx
0x18000d5b0  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000d5b5  cmp     rax, r11
0x18000d5b8  jz      loc_18000D68B
0x18000d5be  sub     rax, rbx
0x18000d5c1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d5c5  sar     rax, 1
0x18000d5c8  cmp     rax, rcx
0x18000d5cb  jz      loc_18000D68B
0x18000d5d1  mov     r8, cs:?USO_USCHEDULER_OOBE_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT
0x18000d5d8  mov     rdx, rcx
0x18000d5db  xor     edi, edi
0x18000d5dd  inc     rdx
0x18000d5e0  cmp     [r8+rdx*2], di
0x18000d5e5  jnz     short loc_18000D5DD
0x18000d5e7  mov     r9, cs:?USOROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOROOT_REDIRECTION_ID
0x18000d5ee  inc     rcx
0x18000d5f1  cmp     [r9+rcx*2], di
0x18000d5f6  jnz     short loc_18000D5EE
0x18000d5f8  mov     [rbp+var_20], r8
0x18000d5fc  lea     r8, [rbp+var_20]
0x18000d600  mov     [rbp+var_18], rdx
0x18000d604  lea     rdx, [rbp+var_10]
0x18000d608  mov     [rbp+var_10], r9
0x18000d60c  lea     r9, [rbp+Src]
0x18000d610  mov     [rbp+var_8], rcx
0x18000d614  lea     rcx, [rbp+arg_0]
0x18000d618  mov     [rbp+Src], rbx
0x18000d61c  mov     [rbp+var_38], rax
0x18000d620  call    ?GetSystemBoolOrDefault@Registry@SystemInterface@@QEAA_NV?$basic_zstring_view@_W@wil@@00_N@Z; SystemInterface::Registry::GetSystemBoolOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,bool)
0x18000d625  mov     bl, al
0x18000d627  test    al, al
0x18000d629  jz      short loc_18000D677
0x18000d62b  lea     rax, aDisableoobeapp; "DisableOobeAppsScan registry value is s"...
0x18000d632  mov     [rbp+var_10], rdi
0x18000d636  lea     r8, [rbp+var_10]
0x18000d63a  mov     [rbp+var_20], rax
0x18000d63e  lea     rdx, [rbp+var_20]
0x18000d642  mov     [rbp+var_8], rdi
0x18000d646  lea     rcx, [rbp+Src]; Src
0x18000d64a  mov     [rbp+var_18], 29h ; ')'
0x18000d652  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000d657  cmp     qword ptr [rax+18h], 7
0x18000d65c  jbe     short loc_18000D661
0x18000d65e  mov     rax, [rax]
0x18000d661  lea     rcx, [rbp+arg_0]
0x18000d665  mov     [rbp+arg_0], rax
0x18000d669  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x18000d66e  lea     rcx, [rbp+Src]; void *
0x18000d672  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d677  lea     r11, [rsp+70h+var_s0]
0x18000d67c  mov     al, bl
0x18000d67e  mov     rbx, [r11+18h]
0x18000d682  mov     rdi, [r11+20h]
0x18000d686  mov     rsp, r11
0x18000d689  pop     rbp
0x18000d68a  retn
0x18000d68b  mov     rcx, [rbp+8]; this
0x18000d68f  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000d696  mov     edx, 0C9h; void *
0x18000d69b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
