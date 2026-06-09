# HasOsBuildNumberIncreased(void)

- ea: `0x18000d948`
- end: `0x18000dd4d`
- name: `?HasOsBuildNumberIncreased@@YA_NXZ`
- size: `1029`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18000dd54`
- `0x18000e654`

## callees

- `0x180009380`
- `0x18000d948`
- `0x18001932c`
- `0x1800194f8`
- `0x18002d330`
- `0x1800337a4`
- `0x180033838`
- `0x1800339b0`
- `0x180033bf0`
- `0x180034304`
- `0x180056500`

## string_xrefs

- `0x18000da5b`: `CurrentBuildNumber unexpectedly reported empty.  Consider Build number unchanged`
- `0x18000dbac`: `LastKnownBuildNumber doesn't exist.  Consider Build number unchanged`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool HasOsBuildNumberIncreased(void)
{
  __int128 v0; // xmm1
  __int64 v1; // rbx
  __int64 v2; // rax
  __int64 v3; // rax
  _QWORD *v4; // rax
  __int128 *p_Src_8; // rcx
  unsigned int v7; // r14d
  __int64 v8; // rcx
  __int64 v9; // rax
  _QWORD *v10; // rax
  unsigned int v11; // esi
  std::_Format_arg_index *v12; // rbx
  __int64 v13; // rdi
  _QWORD *v14; // rax
  __int128 v15; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v16; // [rsp+48h] [rbp-C0h] BYREF
  __int128 Src_8; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v18[3]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v19; // [rsp+88h] [rbp-80h] BYREF
  __int64 v20; // [rsp+98h] [rbp-70h]
  __int64 v21; // [rsp+A0h] [rbp-68h]
  _QWORD v22[2]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v23; // [rsp+B8h] [rbp-50h]
  unsigned int v24; // [rsp+BCh] [rbp-4Ch]
  void **v25; // [rsp+C0h] [rbp-48h] BYREF
  _DWORD v26[8]; // [rsp+C8h] [rbp-40h] BYREF
  char v27; // [rsp+E8h] [rbp-20h]
  char v28; // [rsp+F0h] [rbp-18h]
  wchar_t String[8]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v30; // [rsp+108h] [rbp+0h]

  v25 = &Windows::Registry::`vftable';
  v0 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v22);
  v1 = -1;
  v2 = -1;
  do
    ++v2;
  while ( SystemInterface::Registry::CURRENTBUILDNUMBER[v2] );
  *(_QWORD *)&v16 = SystemInterface::Registry::CURRENTBUILDNUMBER;
  *((_QWORD *)&v16 + 1) = v2;
  v19 = 0;
  v20 = 0;
  v21 = 7;
  LOWORD(v19) = 0;
  *(_QWORD *)&Src_8 = &v19;
  *((_QWORD *)&Src_8 + 1) = 0;
  *(_QWORD *)&v15 = SystemInterface::Registry::WINNTCURRENTVERSIONROOT_REDIRECTION_ID;
  v3 = -1;
  do
    ++v3;
  while ( SystemInterface::Registry::WINNTCURRENTVERSIONROOT_REDIRECTION_ID[v3] );
  *((_QWORD *)&v15 + 1) = v3;
  *(_OWORD *)&v18[1] = v0;
  SystemInterface::Registry::GetSystemValueOrDefault(
    (unsigned int)&v25,
    (unsigned int)String,
    (unsigned int)&v15,
    (unsigned int)&Src_8,
    (__int64)&v16,
    (__int64)&v18[1]);
  std::wstring::~wstring(&v19);
  if ( !v30 )
  {
    *(_QWORD *)&Src_8 = L"CurrentBuildNumber unexpectedly reported empty.  Consider Build number unchanged";
    *((_QWORD *)&Src_8 + 1) = 80;
    *(_OWORD *)&v18[1] = 0u;
    v15 = Src_8;
    v4 = (_QWORD *)std::vformat<0>(&Src_8);
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    *(_QWORD *)&v16 = v4;
    ClientTelemetry::Message<wchar_t const *>(&v16);
    p_Src_8 = &Src_8;
    goto LABEL_9;
  }
  v7 = std::stoul(String);
  v8 = -1;
  do
    ++v8;
  while ( SystemInterface::Registry::LASTKNOWN_BUILDNUMBER[v8] );
  *(_QWORD *)&v15 = SystemInterface::Registry::LASTKNOWN_BUILDNUMBER;
  *((_QWORD *)&v15 + 1) = v8;
  v9 = -1;
  do
    ++v9;
  while ( SystemInterface::Registry::USO_USCHEDULER_ROOT[v9] );
  *(_QWORD *)&Src_8 = SystemInterface::Registry::USO_USCHEDULER_ROOT;
  *((_QWORD *)&Src_8 + 1) = v9;
  *(_QWORD *)&v16 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  do
    ++v1;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v1] );
  *((_QWORD *)&v16 + 1) = v1;
  *(_OWORD *)&v18[1] = v15;
  v15 = Src_8;
  Src_8 = v16;
  Windows::Registry::TryGetSystemValue(
    (unsigned int)&v25,
    (unsigned int)v26,
    (unsigned int)&Src_8,
    (unsigned int)&v15,
    (__int64)&v18[1]);
  if ( !v28 )
  {
    *(_QWORD *)&Src_8 = L"LastKnownBuildNumber doesn't exist.  Consider Build number unchanged";
    *((_QWORD *)&Src_8 + 1) = 68;
    *(_OWORD *)&v18[1] = 0u;
    v15 = Src_8;
    v10 = (_QWORD *)std::vformat<0>(&v19);
    if ( v10[3] > 7u )
      v10 = (_QWORD *)*v10;
    *(_QWORD *)&v16 = v10;
    ClientTelemetry::Message<wchar_t const *>(&v16);
    std::wstring::~wstring(&v19);
    if ( !v28 || v27 == -1 || !v27 || v27 == 1 )
      goto LABEL_10;
    p_Src_8 = (__int128 *)v26;
LABEL_9:
    std::wstring::~wstring(p_Src_8);
LABEL_10:
    std::wstring::~wstring(String);
    return 0;
  }
  if ( v27 )
    std::_Throw_bad_variant_access();
  v11 = v26[0];
  *(_QWORD *)&Src_8 = L"lastKnownBuildNumber: {}, currentBuildNumber: {}";
  *((_QWORD *)&Src_8 + 1) = 48;
  v12 = (std::_Format_arg_index *)v22;
  v13 = 2;
  do
  {
    std::_Format_arg_index::_Format_arg_index(v12);
    v12 = (std::_Format_arg_index *)((char *)v12 + 8);
    --v13;
  }
  while ( v13 );
  v23 = v11;
  v22[0] = 0x2000000000000000LL;
  v24 = v7;
  v22[1] = 0x2000000000000004LL;
  *(_QWORD *)&v15 = 2;
  *((_QWORD *)&v15 + 1) = v22;
  *(_OWORD *)&v18[1] = v15;
  v15 = Src_8;
  v14 = (_QWORD *)std::vformat<0>(&v19);
  if ( v14[3] > 7u )
    v14 = (_QWORD *)*v14;
  *(_QWORD *)&v16 = v14;
  ClientTelemetry::Message<wchar_t const *>(&v16);
  std::wstring::~wstring(&v19);
  if ( v28 && v27 != -1 && v27 && v27 != 1 )
    std::wstring::~wstring(v26);
  std::wstring::~wstring(String);
  return v7 > v11;
}

```

## disassembly

```asm
0x18000d948  mov     rax, rsp
0x18000d94b  mov     [rax+8], rbx
0x18000d94f  mov     [rax+10h], rsi
0x18000d953  mov     [rax+18h], rdi
0x18000d957  push    rbp
0x18000d958  push    r14
0x18000d95a  push    r15
0x18000d95c  lea     rbp, [rax-38h]
0x18000d960  sub     rsp, 120h
0x18000d967  mov     rax, cs:__security_cookie
0x18000d96e  xor     rax, rsp
0x18000d971  mov     [rbp+30h+var_20], rax
0x18000d975  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x18000d97c  mov     [rbp+30h+var_78], rax
0x18000d980  lea     rcx, [rbp+30h+var_90]
0x18000d984  call    ??$?0$00@?$basic_zstring_view@_W@wil@@QEAA@AEAY00$$CB_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t const (&)[1])
0x18000d989  movups  xmm1, xmmword ptr [rax]
0x18000d98c  mov     rcx, cs:?CURRENTBUILDNUMBER@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CURRENTBUILDNUMBER
0x18000d993  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d997  mov     rax, rbx
0x18000d99a  xor     r15d, r15d
0x18000d99d  inc     rax
0x18000d9a0  cmp     [rcx+rax*2], r15w
0x18000d9a5  jnz     short loc_18000D99D
0x18000d9a7  mov     qword ptr [rsp+130h+var_F8+8], rcx
0x18000d9ac  mov     qword ptr [rsp+130h+Src], rax
0x18000d9b1  xorps   xmm0, xmm0
0x18000d9b4  movups  [rbp+30h+var_B0], xmm0
0x18000d9b8  mov     [rbp+30h+var_A0], r15
0x18000d9bc  mov     [rbp+30h+var_98], 7
0x18000d9c4  mov     word ptr [rbp+30h+var_B0], r15w
0x18000d9c9  lea     rax, [rbp+30h+var_B0]
0x18000d9cd  mov     qword ptr [rsp+130h+Src+8], rax
0x18000d9d2  mov     [rsp+130h+var_D8], r15
0x18000d9d7  mov     rcx, cs:?WINNTCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::WINNTCURRENTVERSIONROOT_REDIRECTION_ID
0x18000d9de  mov     qword ptr [rsp+130h+var_108+8], rcx
0x18000d9e3  mov     rax, rbx
0x18000d9e6  inc     rax
0x18000d9e9  cmp     [rcx+rax*2], r15w
0x18000d9ee  jnz     short loc_18000D9E6
0x18000d9f0  mov     qword ptr [rsp+130h+var_F8], rax
0x18000d9f5  movdqu  xmmword ptr [rsp+130h+var_C8+8], xmm1
0x18000d9fb  movups  xmm0, [rsp+130h+var_F8+8]
0x18000da00  movdqu  [rsp+130h+var_F8+8], xmm0
0x18000da06  movups  xmm1, [rsp+130h+Src+8]
0x18000da0b  movdqu  [rsp+130h+Src+8], xmm1
0x18000da11  movaps  xmm0, [rsp+130h+var_108+8]
0x18000da16  movdqa  [rsp+130h+var_108+8], xmm0
0x18000da1c  lea     rax, [rsp+130h+var_C8+8]
0x18000da21  mov     qword ptr [rsp+130h+var_108], rax
0x18000da26  lea     rax, [rsp+130h+var_F8+8]
0x18000da2b  mov     [rsp+130h+var_110], rax
0x18000da30  lea     r9, [rsp+130h+Src+8]
0x18000da35  lea     r8, [rsp+130h+var_108+8]
0x18000da3a  lea     rdx, [rbp+30h+String]
0x18000da3e  lea     rcx, [rbp+30h+var_78]
0x18000da42  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@000@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000da47  nop
0x18000da48  lea     rcx, [rbp+30h+var_B0]; void *
0x18000da4c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000da51  cmp     [rbp+30h+var_30], r15
0x18000da55  jnz     loc_18000DAFC
0x18000da5b  lea     rax, aCurrentbuildnu; "CurrentBuildNumber unexpectedly reporte"...
0x18000da62  mov     qword ptr [rsp+130h+Src+8], rax
0x18000da67  mov     [rsp+130h+var_D8], 50h ; 'P'
0x18000da70  mov     qword ptr [rsp+130h+var_108+8], r15
0x18000da75  mov     qword ptr [rsp+130h+var_F8], r15
0x18000da7a  movaps  xmm0, [rsp+130h+var_108+8]
0x18000da7f  movdqa  xmmword ptr [rsp+130h+var_C8+8], xmm0
0x18000da85  movaps  xmm1, [rsp+130h+Src+8]
0x18000da8a  movdqa  [rsp+130h+var_108+8], xmm1
0x18000da90  lea     r8, [rsp+130h+var_C8+8]
0x18000da95  lea     rdx, [rsp+130h+var_108+8]
0x18000da9a  lea     rcx, [rsp+130h+Src+8]; Src
0x18000da9f  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000daa4  cmp     qword ptr [rax+18h], 7
0x18000daa9  jbe     short loc_18000DAAE
0x18000daab  mov     rax, [rax]
0x18000daae  mov     qword ptr [rsp+130h+var_F8+8], rax
0x18000dab3  lea     rcx, [rsp+130h+var_F8+8]
0x18000dab8  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x18000dabd  lea     rcx, [rsp+130h+Src+8]; void *
0x18000dac2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dac7  nop
0x18000dac8  lea     rcx, [rbp+30h+String]; void *
0x18000dacc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dad1  xor     al, al
0x18000dad3  mov     rcx, [rbp+30h+var_20]
0x18000dad7  xor     rcx, rsp; StackCookie
0x18000dada  call    __security_check_cookie
0x18000dadf  lea     r11, [rsp+130h+var_10]
0x18000dae7  mov     rbx, [r11+20h]
0x18000daeb  mov     rsi, [r11+28h]
0x18000daef  mov     rdi, [r11+30h]
0x18000daf3  mov     rsp, r11
0x18000daf6  pop     r15
0x18000daf8  pop     r14
0x18000dafa  pop     rbp
0x18000dafb  retn
0x18000dafc  lea     rcx, [rbp+30h+String]; String
0x18000db00  call    ?stoul@std@@YAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoul(std::wstring const &,unsigned __int64 *,int)
0x18000db05  mov     r14d, eax
0x18000db08  mov     rdx, cs:?LASTKNOWN_BUILDNUMBER@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::LASTKNOWN_BUILDNUMBER
0x18000db0f  mov     rcx, rbx
0x18000db12  inc     rcx
0x18000db15  cmp     [rdx+rcx*2], r15w
0x18000db1a  jnz     short loc_18000DB12
0x18000db1c  mov     qword ptr [rsp+130h+var_108+8], rdx
0x18000db21  mov     qword ptr [rsp+130h+var_F8], rcx
0x18000db26  mov     rcx, cs:?USO_USCHEDULER_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_USCHEDULER_ROOT
0x18000db2d  mov     rax, rbx
0x18000db30  inc     rax
0x18000db33  cmp     [rcx+rax*2], r15w
0x18000db38  jnz     short loc_18000DB30
0x18000db3a  mov     qword ptr [rsp+130h+Src+8], rcx
0x18000db3f  mov     [rsp+130h+var_D8], rax
0x18000db44  mov     rax, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18000db4b  mov     qword ptr [rsp+130h+var_F8+8], rax
0x18000db50  inc     rbx
0x18000db53  cmp     [rax+rbx*2], r15w
0x18000db58  jnz     short loc_18000DB50
0x18000db5a  mov     qword ptr [rsp+130h+Src], rbx
0x18000db5f  movups  xmm0, [rsp+130h+var_108+8]
0x18000db64  movdqu  xmmword ptr [rsp+130h+var_C8+8], xmm0
0x18000db6a  movups  xmm1, [rsp+130h+Src+8]
0x18000db6f  movdqu  [rsp+130h+var_108+8], xmm1
0x18000db75  movaps  xmm0, [rsp+130h+var_F8+8]
0x18000db7a  movdqa  [rsp+130h+Src+8], xmm0
0x18000db80  lea     rax, [rsp+130h+var_C8+8]
0x18000db85  mov     [rsp+130h+var_110], rax
0x18000db8a  lea     r9, [rsp+130h+var_108+8]
0x18000db8f  lea     r8, [rsp+130h+Src+8]
0x18000db94  lea     rdx, [rbp+30h+var_70]
0x18000db98  lea     rcx, [rbp+30h+var_78]
0x18000db9c  call    ?TryGetSystemValue@Registry@Windows@@UEAA?AV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@V?$basic_zstring_view@_W@wil@@00@Z; Windows::Registry::TryGetSystemValue(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000dba1  nop
0x18000dba2  cmp     [rbp+30h+var_48], r15b
0x18000dba6  jnz     loc_18000DC4D
0x18000dbac  lea     rax, aLastknownbuild_0; "LastKnownBuildNumber doesn't exist.  Co"...
0x18000dbb3  mov     qword ptr [rsp+130h+Src+8], rax
0x18000dbb8  mov     [rsp+130h+var_D8], 44h ; 'D'
0x18000dbc1  mov     qword ptr [rsp+130h+var_108+8], r15
0x18000dbc6  mov     qword ptr [rsp+130h+var_F8], r15
0x18000dbcb  movaps  xmm0, [rsp+130h+var_108+8]
0x18000dbd0  movdqa  xmmword ptr [rsp+130h+var_C8+8], xmm0
0x18000dbd6  movaps  xmm1, [rsp+130h+Src+8]
0x18000dbdb  movdqa  [rsp+130h+var_108+8], xmm1
0x18000dbe1  lea     r8, [rsp+130h+var_C8+8]
0x18000dbe6  lea     rdx, [rsp+130h+var_108+8]
0x18000dbeb  lea     rcx, [rbp+30h+var_B0]; Src
0x18000dbef  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000dbf4  cmp     qword ptr [rax+18h], 7
0x18000dbf9  jbe     short loc_18000DBFE
0x18000dbfb  mov     rax, [rax]
0x18000dbfe  mov     qword ptr [rsp+130h+var_F8+8], rax
0x18000dc03  lea     rcx, [rsp+130h+var_F8+8]
0x18000dc08  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x18000dc0d  lea     rcx, [rbp+30h+var_B0]; void *
0x18000dc11  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dc16  nop
0x18000dc17  cmp     [rbp+30h+var_48], r15b
0x18000dc1b  jz      loc_18000DAC8
0x18000dc21  movsx   rax, [rbp+30h+var_50]
0x18000dc26  add     rax, 1
0x18000dc2a  jz      loc_18000DAC8
0x18000dc30  sub     rax, 1
0x18000dc34  jz      loc_18000DAC8
0x18000dc3a  cmp     rax, 1
0x18000dc3e  jz      loc_18000DAC8
0x18000dc44  lea     rcx, [rbp+30h+var_70]
0x18000dc48  jmp     loc_18000DAC2
0x18000dc4d  cmp     [rbp+30h+var_50], r15b
0x18000dc51  jnz     loc_18000DD47
0x18000dc57  mov     esi, [rbp+30h+var_70]
0x18000dc5a  lea     rax, aLastknownbuild; "lastKnownBuildNumber: {}, currentBuildN"...
0x18000dc61  mov     qword ptr [rsp+130h+Src+8], rax
0x18000dc66  mov     [rsp+130h+var_D8], 30h ; '0'
0x18000dc6f  lea     rbx, [rbp+30h+var_90]
0x18000dc73  mov     edi, 2
0x18000dc78  mov     rcx, rbx; this
0x18000dc7b  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x18000dc80  add     rbx, 8
0x18000dc84  sub     rdi, 1
0x18000dc88  jnz     short loc_18000DC78
0x18000dc8a  mov     [rbp+30h+var_80], esi
0x18000dc8d  mov     rax, 2000000000000000h
0x18000dc97  mov     [rbp+30h+var_90], rax
0x18000dc9b  mov     [rbp+30h+var_7C], r14d
0x18000dc9f  mov     rax, 2000000000000004h
0x18000dca9  mov     [rbp+30h+var_88], rax
0x18000dcad  mov     qword ptr [rsp+130h+var_108+8], 2
0x18000dcb6  lea     rax, [rbp+30h+var_90]
0x18000dcba  mov     qword ptr [rsp+130h+var_F8], rax
0x18000dcbf  movaps  xmm0, [rsp+130h+var_108+8]
0x18000dcc4  movdqa  xmmword ptr [rsp+130h+var_C8+8], xmm0
0x18000dcca  movaps  xmm1, [rsp+130h+Src+8]
0x18000dccf  movdqa  [rsp+130h+var_108+8], xmm1
0x18000dcd5  lea     r8, [rsp+130h+var_C8+8]
0x18000dcda  lea     rdx, [rsp+130h+var_108+8]
0x18000dcdf  lea     rcx, [rbp+30h+var_B0]; Src
0x18000dce3  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000dce8  cmp     qword ptr [rax+18h], 7
0x18000dced  jbe     short loc_18000DCF2
0x18000dcef  mov     rax, [rax]
0x18000dcf2  mov     qword ptr [rsp+130h+var_F8+8], rax
0x18000dcf7  lea     rcx, [rsp+130h+var_F8+8]
0x18000dcfc  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x18000dd01  lea     rcx, [rbp+30h+var_B0]; void *
0x18000dd05  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dd0a  cmp     r14d, esi
0x18000dd0d  setnbe  bl
0x18000dd10  cmp     [rbp+30h+var_48], r15b
0x18000dd14  jz      short loc_18000DD37
0x18000dd16  movsx   rcx, [rbp+30h+var_50]
0x18000dd1b  add     rcx, 1
0x18000dd1f  jz      short loc_18000DD37
0x18000dd21  sub     rcx, 1
0x18000dd25  jz      short loc_18000DD37
0x18000dd27  cmp     rcx, 1
0x18000dd2b  jz      short loc_18000DD37
0x18000dd2d  lea     rcx, [rbp+30h+var_70]; void *
0x18000dd31  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dd36  nop
0x18000dd37  lea     rcx, [rbp+30h+String]; void *
0x18000dd3b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dd40  mov     al, bl
0x18000dd42  jmp     loc_18000DAD3
0x18000dd47  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
```
