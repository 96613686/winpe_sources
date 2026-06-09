# DeleteExpeditedUpdates(void)

- ea: `0x18000cde8`
- end: `0x18000d27a`
- name: `?DeleteExpeditedUpdates@@YAXXZ`
- size: `1170`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000dd54`

## callees

- `0x180009380`
- `0x18000cde8`
- `0x1800181d4`
- `0x18001932c`
- `0x1800194f8`
- `0x18002d330`
- `0x180033f14`
- `0x180034170`
- `0x1800343ec`
- `0x1800344b8`
- `0x180036b10`
- `0x18003bf20`
- `0x18003c8dc`
- `0x180056500`

## string_xrefs

- `0x18000d0cb`: `Not deleting existing OOBE update for {} since it is not allowed to rerun`
- `0x18000d153`: `Deleting existing OOBE update for {}`
- `0x18000d267`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void DeleteExpeditedUpdates(void)
{
  __int64 v0; // rax
  __int64 v1; // rcx
  _QWORD *v2; // r14
  std::_Format_arg_index *v3; // rdi
  __int64 v4; // rsi
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rcx
  __int16 *traits_2_unsigned_short; // rax
  const char *v9; // r9
  __int64 v10; // rax
  _QWORD *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  _QWORD *v14; // rax
  _QWORD *i; // rbx
  __int64 v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rcx
  const char *v20; // r9
  unsigned __int128 v21; // [rsp+30h] [rbp-188h] BYREF
  unsigned __int128 v22; // [rsp+40h] [rbp-178h] BYREF
  _QWORD v23[8]; // [rsp+50h] [rbp-168h] BYREF
  __int128 v24; // [rsp+90h] [rbp-128h] BYREF
  __int128 v25; // [rsp+A0h] [rbp-118h] BYREF
  _QWORD v26[2]; // [rsp+B0h] [rbp-108h] BYREF
  _QWORD v27[2]; // [rsp+C0h] [rbp-F8h] BYREF
  _QWORD v28[10]; // [rsp+D0h] [rbp-E8h] BYREF
  __int128 v29; // [rsp+120h] [rbp-98h] BYREF
  __int128 v30; // [rsp+130h] [rbp-88h] BYREF
  _BYTE v31[24]; // [rsp+140h] [rbp-78h] BYREF
  void **v32; // [rsp+158h] [rbp-60h] BYREF
  _QWORD Src[2]; // [rsp+160h] [rbp-58h] BYREF
  __int64 v34; // [rsp+170h] [rbp-48h]
  unsigned __int64 v35; // [rsp+178h] [rbp-40h]
  __int128 v36; // [rsp+180h] [rbp-38h] BYREF
  __int64 v37; // [rsp+190h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v32 = &Windows::Registry::`vftable';
  v36 = 0;
  v37 = 0;
  v0 = -1;
  do
    ++v0;
  while ( SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT[v0] );
  v1 = -1;
  do
    ++v1;
  while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v1] );
  try
  {
    *(_QWORD *)&v21 = SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT;
    *((_QWORD *)&v21 + 1) = v0;
    v22 = __PAIR128__(v1, (unsigned __int64)SystemInterface::Registry::USOROOT_REDIRECTION_ID);
    Windows::Registry::GetSubKeyList(
      (__int64)&v32,
      (__int64)&v36,
      (__int64)SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT,
      &v22,
      &v21);
    v2 = (_QWORD *)*((_QWORD *)&v36 + 1);
    for ( i = (_QWORD *)v36; i != v2; i += 4 )
    {
      v3 = (std::_Format_arg_index *)v23;
      v4 = 2;
      do
      {
        std::_Format_arg_index::_Format_arg_index(v3);
        v3 = (std::_Format_arg_index *)((char *)v3 + 8);
        --v4;
      }
      while ( v4 );
      v23[2] = SystemInterface::Registry::USO_USCHEDULER_ROOT;
      v23[0] = 0xB000000000000000uLL;
      v5 = i;
      if ( i[3] > 7u )
        v5 = (_QWORD *)*i;
      v23[3] = v5;
      v23[4] = i[2];
      v23[1] = 0xC000000000000008uLL;
      *(_QWORD *)&v22 = L"{}\\{}";
      *((_QWORD *)&v22 + 1) = 5;
      v23[6] = 2;
      v23[7] = v23;
      v21 = v22;
      std::vformat<0>(Src);
      v6 = Src;
      if ( v35 > 7 )
        v6 = (_QWORD *)Src[0];
      v7 = -1;
      do
        ++v7;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v7] );
      *(_QWORD *)&v24 = v6;
      *((_QWORD *)&v24 + 1) = v34;
      *(_QWORD *)&v25 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      *((_QWORD *)&v25 + 1) = v7;
      if ( Windows::Registry::KeyExists(
             (__int64)&v32,
             (__int64)SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID,
             &v25,
             &v24) )
      {
        traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                               L"allowedToRerun",
                                               &word_180067D7E,
                                               0);
        if ( traits_2_unsigned_short == &word_180067D7E
          || (v10 = ((char *)traits_2_unsigned_short - (char *)L"allowedToRerun") >> 1, v10 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v9);
        }
        v11 = Src;
        if ( v35 > 7 )
          v11 = (_QWORD *)Src[0];
        v12 = -1;
        do
          ++v12;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v12] );
        v26[0] = L"allowedToRerun";
        v26[1] = v10;
        v27[0] = v11;
        v27[1] = v34;
        v28[0] = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        v28[1] = v12;
        if ( (unsigned __int8)SystemInterface::Registry::GetSystemBoolOrDefault(&v32, v28, v27, v26) )
        {
          v16 = std::make_wformat_args<std::wstring>(v31, i);
          v28[6] = 1;
          v28[7] = v16;
          v28[8] = L"Deleting existing OOBE update for {}";
          v28[9] = 36;
          v17 = (_QWORD *)std::vformat<0>(v23);
          if ( v17[3] > 7u )
            v17 = (_QWORD *)*v17;
          *(_QWORD *)&v21 = v17;
          ClientTelemetry::Message<wchar_t const *>(&v21);
          std::wstring::~wstring(v23);
          v18 = Src;
          if ( v35 > 7 )
            v18 = (_QWORD *)Src[0];
          v19 = -1;
          do
            ++v19;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v19] );
          *(_QWORD *)&v29 = v18;
          *((_QWORD *)&v29 + 1) = v34;
          *(_QWORD *)&v30 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          *((_QWORD *)&v30 + 1) = v19;
          Windows::Registry::DeleteSystemKey((__int64)&v32, &v30, &v29);
        }
        else
        {
          v13 = std::make_wformat_args<std::wstring>(v31, i);
          v28[2] = 1;
          v28[3] = v13;
          v28[4] = L"Not deleting existing OOBE update for {} since it is not allowed to rerun";
          v28[5] = 73;
          v14 = (_QWORD *)std::vformat<0>(v23);
          if ( v14[3] > 7u )
            v14 = (_QWORD *)*v14;
          *(_QWORD *)&v21 = v14;
          ClientTelemetry::Message<wchar_t const *>(&v21);
          std::wstring::~wstring(v23);
        }
      }
      std::wstring::~wstring(Src);
    }
    std::vector<std::wstring>::_Tidy(&v36);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x60,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      v20);
  }
}

```

## disassembly

```asm
0x18000cde8  mov     r11, rsp
0x18000cdeb  mov     [r11+8], rbx
0x18000cdef  mov     [r11+10h], rsi
0x18000cdf3  mov     [r11+18h], rdi
0x18000cdf7  push    r12
0x18000cdf9  push    r14
0x18000cdfb  push    r15
0x18000cdfd  sub     rsp, 1A0h
0x18000ce04  mov     rax, cs:__security_cookie
0x18000ce0b  xor     rax, rsp
0x18000ce0e  mov     [rsp+1B8h+var_20], rax
0x18000ce16  xor     r15d, r15d
0x18000ce19  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x18000ce20  mov     [r11-60h], rax
0x18000ce24  xorps   xmm0, xmm0
0x18000ce27  xor     eax, eax
0x18000ce29  movups  xmmword ptr [r11-38h], xmm0
0x18000ce2e  mov     [r11-28h], rax
0x18000ce32  mov     r8, cs:?USO_USCHEDULER_OOBE_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT
0x18000ce39  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000ce3d  mov     rax, r12
0x18000ce40  inc     rax
0x18000ce43  cmp     [r8+rax*2], r15w
0x18000ce48  jnz     short loc_18000CE40
0x18000ce4a  mov     rdx, cs:?USOROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOROOT_REDIRECTION_ID
0x18000ce51  mov     rcx, r12
0x18000ce54  inc     rcx
0x18000ce57  cmp     [rdx+rcx*2], r15w
0x18000ce5c  jnz     short loc_18000CE54
0x18000ce5e  mov     qword ptr [rsp+1B8h+var_188], r8
0x18000ce63  mov     qword ptr [rsp+1B8h+var_188+8], rax
0x18000ce68  mov     qword ptr [rsp+1B8h+var_178], rdx
0x18000ce6d  mov     qword ptr [rsp+1B8h+var_178+8], rcx
0x18000ce72  lea     rax, [rsp+1B8h+var_188]
0x18000ce77  mov     [rsp+1B8h+var_198], rax
0x18000ce7c  lea     r9, [rsp+1B8h+var_178]
0x18000ce81  lea     rdx, [rsp+1B8h+var_38]
0x18000ce89  lea     rcx, [rsp+1B8h+var_60]
0x18000ce91  call    ?GetSubKeyList@Registry@Windows@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z; Windows::Registry::GetSubKeyList(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000ce96  nop
0x18000ce97  mov     rbx, [rsp+1B8h+var_38]
0x18000ce9f  mov     r14, [rsp+1B8h+var_30]
0x18000cea7  cmp     rbx, r14
0x18000ceaa  jz      loc_18000D223
0x18000ceb0  lea     rdi, [rsp+1B8h+var_168]
0x18000ceb5  mov     esi, 2
0x18000ceba  mov     rcx, rdi; this
0x18000cebd  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x18000cec2  add     rdi, 8
0x18000cec6  sub     rsi, 1
0x18000ceca  jnz     short loc_18000CEBA
0x18000cecc  mov     rax, cs:?USO_USCHEDULER_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_USCHEDULER_ROOT
0x18000ced3  mov     [rsp+1B8h+var_158], rax
0x18000ced8  mov     rax, 0B000000000000000h
0x18000cee2  mov     [rsp+1B8h+var_168], rax
0x18000cee7  mov     rax, rbx
0x18000ceea  cmp     qword ptr [rbx+18h], 7
0x18000ceef  jbe     short loc_18000CEF4
0x18000cef1  mov     rax, [rbx]
0x18000cef4  mov     [rsp+1B8h+var_150], rax
0x18000cef9  mov     rax, [rbx+10h]
0x18000cefd  mov     [rsp+1B8h+var_148], rax
0x18000cf02  mov     rax, 0C000000000000008h
0x18000cf0c  mov     [rsp+1B8h+var_160], rax
0x18000cf11  lea     rax, asc_180067D50; "{}\\{}"
0x18000cf18  mov     qword ptr [rsp+1B8h+var_178], rax
0x18000cf1d  mov     qword ptr [rsp+1B8h+var_178+8], 5
0x18000cf26  mov     [rsp+1B8h+var_138], 2
0x18000cf32  lea     rax, [rsp+1B8h+var_168]
0x18000cf37  mov     [rsp+1B8h+var_130], rax
0x18000cf3f  movaps  xmm0, [rsp+1B8h+var_178]
0x18000cf44  movdqa  [rsp+1B8h+var_188], xmm0
0x18000cf4a  lea     r8, [rsp+1B8h+var_138]
0x18000cf52  lea     rdx, [rsp+1B8h+var_188]
0x18000cf57  lea     rcx, [rsp+1B8h+Src]; Src
0x18000cf5f  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000cf64  nop
0x18000cf65  lea     rax, [rsp+1B8h+Src]
0x18000cf6d  cmp     [rsp+1B8h+var_40], 7
0x18000cf76  cmova   rax, [rsp+1B8h+Src]
0x18000cf7f  mov     rdx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18000cf86  mov     rcx, r12
0x18000cf89  inc     rcx
0x18000cf8c  cmp     [rdx+rcx*2], r15w
0x18000cf91  jnz     short loc_18000CF89
0x18000cf93  mov     [rsp+1B8h+var_128], rax
0x18000cf9b  mov     rax, [rsp+1B8h+var_48]
0x18000cfa3  mov     [rsp+1B8h+var_120], rax
0x18000cfab  mov     [rsp+1B8h+var_118], rdx
0x18000cfb3  mov     [rsp+1B8h+var_110], rcx
0x18000cfbb  lea     r9, [rsp+1B8h+var_128]
0x18000cfc3  lea     r8, [rsp+1B8h+var_118]
0x18000cfcb  lea     rcx, [rsp+1B8h+var_60]
0x18000cfd3  call    ?KeyExists@Registry@Windows@@QEAA_NQEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z; Windows::Registry::KeyExists(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000cfd8  test    al, al
0x18000cfda  jz      loc_18000D124
0x18000cfe0  xor     r8d, r8d
0x18000cfe3  lea     rsi, word_180067D7E
0x18000cfea  mov     rdx, rsi
0x18000cfed  lea     rdi, aAllowedtorerun; "allowedToRerun"
0x18000cff4  mov     rcx, rdi
0x18000cff7  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000cffc  cmp     rax, rsi
0x18000cfff  jz      loc_18000D25F
0x18000d005  sub     rax, rdi
0x18000d008  sar     rax, 1
0x18000d00b  cmp     rax, r12
0x18000d00e  jz      loc_18000D25F
0x18000d014  lea     rdx, [rsp+1B8h+Src]
0x18000d01c  cmp     [rsp+1B8h+var_40], 7
0x18000d025  cmova   rdx, [rsp+1B8h+Src]
0x18000d02e  mov     r8, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18000d035  mov     rcx, r12
0x18000d038  inc     rcx
0x18000d03b  cmp     [r8+rcx*2], r15w
0x18000d040  jnz     short loc_18000D038
0x18000d042  mov     [rsp+1B8h+var_108], rdi
0x18000d04a  mov     [rsp+1B8h+var_100], rax
0x18000d052  mov     [rsp+1B8h+var_F8], rdx
0x18000d05a  mov     rax, [rsp+1B8h+var_48]
0x18000d062  mov     [rsp+1B8h+var_F0], rax
0x18000d06a  mov     [rsp+1B8h+var_E8], r8
0x18000d072  mov     [rsp+1B8h+var_E0], rcx
0x18000d07a  lea     r9, [rsp+1B8h+var_108]
0x18000d082  lea     r8, [rsp+1B8h+var_F8]
0x18000d08a  lea     rdx, [rsp+1B8h+var_E8]
0x18000d092  lea     rcx, [rsp+1B8h+var_60]
0x18000d09a  call    ?GetSystemBoolOrDefault@Registry@SystemInterface@@QEAA_NV?$basic_zstring_view@_W@wil@@00_N@Z; SystemInterface::Registry::GetSystemBoolOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,bool)
0x18000d09f  mov     rdx, rbx
0x18000d0a2  lea     rcx, [rsp+1B8h+var_78]
0x18000d0aa  test    al, al
0x18000d0ac  jnz     loc_18000D13A
0x18000d0b2  call    ??$make_wformat_args@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?A_PAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z
0x18000d0b7  mov     [rsp+1B8h+var_D8], 1
0x18000d0c3  mov     [rsp+1B8h+var_D0], rax
0x18000d0cb  lea     rax, aNotDeletingExi; "Not deleting existing OOBE update for {"...
0x18000d0d2  mov     [rsp+1B8h+var_C8], rax
0x18000d0da  mov     [rsp+1B8h+var_C0], 49h ; 'I'
0x18000d0e6  lea     r8, [rsp+1B8h+var_D8]
0x18000d0ee  lea     rdx, [rsp+1B8h+var_C8]
0x18000d0f6  lea     rcx, [rsp+1B8h+var_168]; Src
0x18000d0fb  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000d100  cmp     qword ptr [rax+18h], 7
0x18000d105  jbe     short loc_18000D10A
0x18000d107  mov     rax, [rax]
0x18000d10a  mov     qword ptr [rsp+1B8h+var_188], rax
0x18000d10f  lea     rcx, [rsp+1B8h+var_188]
0x18000d114  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x18000d119  lea     rcx, [rsp+1B8h+var_168]; void *
0x18000d11e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d123  nop
0x18000d124  lea     rcx, [rsp+1B8h+Src]; void *
0x18000d12c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d131  add     rbx, 20h ; ' '
0x18000d135  jmp     loc_18000CEA7
0x18000d13a  call    ??$make_wformat_args@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?A_PAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z
0x18000d13f  mov     [rsp+1B8h+var_B8], 1
0x18000d14b  mov     [rsp+1B8h+var_B0], rax
0x18000d153  lea     rax, aDeletingExisti; "Deleting existing OOBE update for {}"
0x18000d15a  mov     [rsp+1B8h+var_A8], rax
0x18000d162  mov     [rsp+1B8h+var_A0], 24h ; '$'
0x18000d16e  lea     r8, [rsp+1B8h+var_B8]
0x18000d176  lea     rdx, [rsp+1B8h+var_A8]
0x18000d17e  lea     rcx, [rsp+1B8h+var_168]; Src
0x18000d183  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000d188  cmp     qword ptr [rax+18h], 7
0x18000d18d  jbe     short loc_18000D192
0x18000d18f  mov     rax, [rax]
0x18000d192  mov     qword ptr [rsp+1B8h+var_188], rax
0x18000d197  lea     rcx, [rsp+1B8h+var_188]
0x18000d19c  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x18000d1a1  lea     rcx, [rsp+1B8h+var_168]; void *
0x18000d1a6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d1ab  lea     rax, [rsp+1B8h+Src]
0x18000d1b3  cmp     [rsp+1B8h+var_40], 7
0x18000d1bc  cmova   rax, [rsp+1B8h+Src]
0x18000d1c5  mov     rdx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18000d1cc  mov     rcx, r12
0x18000d1cf  inc     rcx
0x18000d1d2  cmp     [rdx+rcx*2], r15w
0x18000d1d7  jnz     short loc_18000D1CF
0x18000d1d9  mov     [rsp+1B8h+var_98], rax
0x18000d1e1  mov     rax, [rsp+1B8h+var_48]
0x18000d1e9  mov     [rsp+1B8h+var_90], rax
0x18000d1f1  mov     [rsp+1B8h+var_88], rdx
0x18000d1f9  mov     [rsp+1B8h+var_80], rcx
0x18000d201  lea     r8, [rsp+1B8h+var_98]
0x18000d209  lea     rdx, [rsp+1B8h+var_88]
0x18000d211  lea     rcx, [rsp+1B8h+var_60]
0x18000d219  call    ?DeleteSystemKey@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::DeleteSystemKey(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000d21e  jmp     loc_18000D124
0x18000d223  lea     rcx, [rsp+1B8h+var_38]
0x18000d22b  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000d230  nop
0x18000d231  mov     rcx, [rsp+1B8h+var_20]
0x18000d239  xor     rcx, rsp; StackCookie
0x18000d23c  call    __security_check_cookie
0x18000d241  lea     r11, [rsp+1B8h+var_18]
0x18000d249  mov     rbx, [r11+20h]
0x18000d24d  mov     rsi, [r11+28h]
0x18000d251  mov     rdi, [r11+30h]
0x18000d255  mov     rsp, r11
0x18000d258  pop     r15
0x18000d25a  pop     r14
0x18000d25c  pop     r12
0x18000d25e  retn
0x18000d25f  mov     rcx, [rsp+1B8h]; this
0x18000d267  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000d26e  mov     edx, 0C9h; void *
0x18000d273  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
