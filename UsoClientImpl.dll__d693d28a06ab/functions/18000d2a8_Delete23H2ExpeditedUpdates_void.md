# Delete23H2ExpeditedUpdates(void)

- ea: `0x18000d2a8`
- end: `0x18000d576`
- name: `?Delete23H2ExpeditedUpdates@@YAXXZ`
- size: `718`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18000dd54`

## callees

- `0x180009380`
- `0x18000a1f8`
- `0x18000d2a8`
- `0x180018e0c`
- `0x18001932c`
- `0x1800194f8`
- `0x18001b11c`
- `0x18002d330`
- `0x180034170`
- `0x180056500`
- `0x18005ca20`

## string_xrefs

- `0x18000d379`: `Deleting existing OOBE update for {}`
- `0x18000d2e4`: `TFLUpdate`
- `0x18000d2f0`: `OutlookUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void Delete23H2ExpeditedUpdates(void)
{
  int v0; // r14d
  __int64 v1; // rbx
  _QWORD *v2; // r15
  _QWORD *v3; // rax
  std::_Format_arg_index *v4; // rbx
  __int64 v5; // rdi
  _QWORD *v6; // rax
  __int64 v7; // rcx
  _QWORD *i; // rsi
  const char *v9; // r9
  __int128 v10; // [rsp+20h] [rbp-108h] BYREF
  _QWORD v11[2]; // [rsp+30h] [rbp-F8h] BYREF
  _QWORD v12[4]; // [rsp+40h] [rbp-E8h] BYREF
  _QWORD Src[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int128 v14; // [rsp+70h] [rbp-B8h]
  __int64 v15; // [rsp+80h] [rbp-A8h]
  _QWORD *v16; // [rsp+88h] [rbp-A0h]
  __int128 v17; // [rsp+90h] [rbp-98h]
  __int64 v18; // [rsp+A0h] [rbp-88h]
  _QWORD *v19; // [rsp+A8h] [rbp-80h]
  __int128 v20; // [rsp+B0h] [rbp-78h] BYREF
  __int128 v21; // [rsp+C0h] [rbp-68h] BYREF
  __int128 v22; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-48h]
  _QWORD v24[4]; // [rsp+E8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v0 = 0;
  LODWORD(v10) = 0;
  Src[0] = L"TFLUpdate";
  Src[1] = L"OutlookUpdate";
  v22 = 0;
  v23 = 0;
  try
  {
    *(_QWORD *)&v22 = std::_Allocate<16,std::_Default_allocate_traits>(16);
    *((_QWORD *)&v22 + 1) = v22;
    v1 = v22 + 16;
    v23 = v22 + 16;
    memmove((void *)v22, Src, 0x10u);
    *((_QWORD *)&v22 + 1) = v1;
    *(_QWORD *)&v10 = 0;
    std::_Tidy_guard<std::vector<wchar_t const *>>::~_Tidy_guard<std::vector<wchar_t const *>>(&v10);
    v2 = (_QWORD *)*((_QWORD *)&v22 + 1);
    for ( i = (_QWORD *)v22; i != v2; ++i )
    {
      *(_QWORD *)&v14 = L"Deleting existing OOBE update for {}";
      *((_QWORD *)&v14 + 1) = 36;
      std::_Format_arg_index::_Format_arg_index((std::_Format_arg_index *)v11);
      v11[1] = *i;
      v11[0] = 0xB000000000000000uLL;
      v15 = 1;
      v16 = v11;
      v10 = v14;
      v3 = (_QWORD *)std::vformat<0>(v12);
      if ( v3[3] > 7u )
        v3 = (_QWORD *)*v3;
      *(_QWORD *)&v10 = v3;
      ClientTelemetry::Message<wchar_t const *>(&v10);
      std::wstring::~wstring(v12);
      v4 = (std::_Format_arg_index *)v12;
      v5 = 2;
      do
      {
        std::_Format_arg_index::_Format_arg_index(v4);
        v4 = (std::_Format_arg_index *)((char *)v4 + 8);
        --v5;
      }
      while ( v5 );
      v12[2] = SystemInterface::Registry::USO_USCHEDULER_ROOT;
      v12[0] = 0xB000000000000000uLL;
      v12[3] = *i;
      v12[1] = 0xB000000000000008uLL;
      *(_QWORD *)&v17 = L"{}\\{}";
      *((_QWORD *)&v17 + 1) = 5;
      v18 = 2;
      v19 = v12;
      v10 = v17;
      std::vformat<0>(v24);
      v0 |= 1u;
      v6 = v24;
      if ( v24[3] > 7u )
        v6 = (_QWORD *)v24[0];
      v7 = -1;
      do
        ++v7;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v7] );
      *(_QWORD *)&v20 = v6;
      *((_QWORD *)&v20 + 1) = v24[2];
      *(_QWORD *)&v21 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      *((_QWORD *)&v21 + 1) = v7;
      Windows::Registry::DeleteSystemKey((__int64)&v10, &v21, &v20);
      std::wstring::~wstring(v24);
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(&v22);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x70,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      v9);
  }
}

```

## disassembly

```asm
0x18000d2a8  mov     r11, rsp
0x18000d2ab  mov     [r11+8], rbx
0x18000d2af  mov     [r11+10h], rsi
0x18000d2b3  mov     [r11+18h], rdi
0x18000d2b7  push    r12
0x18000d2b9  push    r14
0x18000d2bb  push    r15
0x18000d2bd  sub     rsp, 110h
0x18000d2c4  mov     rax, cs:__security_cookie
0x18000d2cb  xor     rax, rsp
0x18000d2ce  mov     [rsp+128h+var_20], rax
0x18000d2d6  xor     r12d, r12d
0x18000d2d9  mov     r14d, r12d
0x18000d2dc  mov     dword ptr [rsp+128h+var_108], r12d
0x18000d2e1  xorps   xmm0, xmm0
0x18000d2e4  lea     rax, aTflupdate; "TFLUpdate"
0x18000d2eb  mov     [rsp+128h+Src], rax
0x18000d2f0  lea     rax, aOutlookupdate; "OutlookUpdate"
0x18000d2f7  mov     [rsp+128h+var_C0], rax
0x18000d2fc  movdqu  xmmword ptr [r11-58h], xmm0
0x18000d302  mov     [r11-48h], r12
0x18000d306  lea     edi, [r12+10h]
0x18000d30b  mov     ecx, edi
0x18000d30d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d312  mov     [rsp+128h+var_58], rax
0x18000d31a  mov     [rsp+128h+var_50], rax
0x18000d322  lea     rbx, [rax+10h]
0x18000d326  mov     [rsp+128h+var_48], rbx
0x18000d32e  mov     r8d, edi; Size
0x18000d331  lea     rdx, [rsp+128h+Src]; Src
0x18000d336  mov     rcx, rax; void *
0x18000d339  call    memmove
0x18000d33e  mov     [rsp+128h+var_50], rbx
0x18000d346  mov     qword ptr [rsp+128h+var_108], r12
0x18000d34b  lea     rcx, [rsp+128h+var_108]
0x18000d350  call    ??1?$_Tidy_guard@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<wchar_t const *>>::~_Tidy_guard<std::vector<wchar_t const *>>(void)
0x18000d355  nop
0x18000d356  mov     rsi, [rsp+128h+var_58]
0x18000d35e  mov     r15, [rsp+128h+var_50]
0x18000d366  mov     rbx, 0B000000000000000h
0x18000d370  cmp     rsi, r15
0x18000d373  jz      loc_18000D53A
0x18000d379  lea     rax, aDeletingExisti; "Deleting existing OOBE update for {}"
0x18000d380  mov     qword ptr [rsp+128h+var_B8], rax
0x18000d385  mov     qword ptr [rsp+128h+var_B8+8], 24h ; '$'
0x18000d38e  lea     rcx, [rsp+128h+var_F8]; this
0x18000d393  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x18000d398  mov     rax, [rsi]
0x18000d39b  mov     [rsp+128h+var_F0], rax
0x18000d3a0  mov     [rsp+128h+var_F8], rbx
0x18000d3a5  mov     [rsp+128h+var_A8], 1
0x18000d3b1  lea     rax, [rsp+128h+var_F8]
0x18000d3b6  mov     [rsp+128h+var_A0], rax
0x18000d3be  movaps  xmm0, [rsp+128h+var_B8]
0x18000d3c3  movdqa  [rsp+128h+var_108], xmm0
0x18000d3c9  lea     r8, [rsp+128h+var_A8]
0x18000d3d1  lea     rdx, [rsp+128h+var_108]
0x18000d3d6  lea     rcx, [rsp+128h+var_E8]; Src
0x18000d3db  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000d3e0  cmp     qword ptr [rax+18h], 7
0x18000d3e5  jbe     short loc_18000D3EA
0x18000d3e7  mov     rax, [rax]
0x18000d3ea  mov     qword ptr [rsp+128h+var_108], rax
0x18000d3ef  lea     rcx, [rsp+128h+var_108]
0x18000d3f4  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x18000d3f9  lea     rcx, [rsp+128h+var_E8]; void *
0x18000d3fe  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d403  nop
0x18000d404  lea     rbx, [rsp+128h+var_E8]
0x18000d409  mov     edi, 2
0x18000d40e  mov     rcx, rbx; this
0x18000d411  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x18000d416  add     rbx, 8
0x18000d41a  sub     rdi, 1
0x18000d41e  jnz     short loc_18000D40E
0x18000d420  mov     rax, cs:?USO_USCHEDULER_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_USCHEDULER_ROOT
0x18000d427  mov     [rsp+128h+var_D8], rax
0x18000d42c  mov     rbx, 0B000000000000000h
0x18000d436  mov     [rsp+128h+var_E8], rbx
0x18000d43b  mov     rax, [rsi]
0x18000d43e  mov     [rsp+128h+var_D0], rax
0x18000d443  mov     rax, 0B000000000000008h
0x18000d44d  mov     [rsp+128h+var_E0], rax
0x18000d452  lea     rax, asc_180067D50; "{}\\{}"
0x18000d459  mov     qword ptr [rsp+128h+var_98], rax
0x18000d461  mov     qword ptr [rsp+128h+var_98+8], 5
0x18000d46d  mov     [rsp+128h+var_88], 2
0x18000d479  lea     rax, [rsp+128h+var_E8]
0x18000d47e  mov     [rsp+128h+var_80], rax
0x18000d486  movaps  xmm0, [rsp+128h+var_98]
0x18000d48e  movdqa  [rsp+128h+var_108], xmm0
0x18000d494  lea     r8, [rsp+128h+var_88]
0x18000d49c  lea     rdx, [rsp+128h+var_108]
0x18000d4a1  lea     rcx, [rsp+128h+var_40]; Src
0x18000d4a9  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000d4ae  or      r14d, 1
0x18000d4b2  lea     rax, [rsp+128h+var_40]
0x18000d4ba  cmp     [rsp+128h+var_28], 7
0x18000d4c3  cmova   rax, [rsp+128h+var_40]
0x18000d4cc  mov     rdx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18000d4d3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d4d7  inc     rcx
0x18000d4da  cmp     [rdx+rcx*2], r12w
0x18000d4df  jnz     short loc_18000D4D7
0x18000d4e1  mov     [rsp+128h+var_78], rax
0x18000d4e9  mov     rax, [rsp+128h+var_30]
0x18000d4f1  mov     [rsp+128h+var_70], rax
0x18000d4f9  mov     [rsp+128h+var_68], rdx
0x18000d501  mov     [rsp+128h+var_60], rcx
0x18000d509  lea     r8, [rsp+128h+var_78]
0x18000d511  lea     rdx, [rsp+128h+var_68]
0x18000d519  lea     rcx, [rsp+128h+var_108]
0x18000d51e  call    ?DeleteSystemKey@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::DeleteSystemKey(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000d523  nop
0x18000d524  lea     rcx, [rsp+128h+var_40]; void *
0x18000d52c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d531  add     rsi, 8
0x18000d535  jmp     loc_18000D370
0x18000d53a  lea     rcx, [rsp+128h+var_58]
0x18000d542  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x18000d547  nop
0x18000d548  mov     rcx, [rsp+128h+var_20]
0x18000d550  xor     rcx, rsp; StackCookie
0x18000d553  call    __security_check_cookie
0x18000d558  lea     r11, [rsp+128h+var_18]
0x18000d560  mov     rbx, [r11+20h]
0x18000d564  mov     rsi, [r11+28h]
0x18000d568  mov     rdi, [r11+30h]
0x18000d56c  mov     rsp, r11
0x18000d56f  pop     r15
0x18000d571  pop     r14
0x18000d573  pop     r12
0x18000d575  retn
```
