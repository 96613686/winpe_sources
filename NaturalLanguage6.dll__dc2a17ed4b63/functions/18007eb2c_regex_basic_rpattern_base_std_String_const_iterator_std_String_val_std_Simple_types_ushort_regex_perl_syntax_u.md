# regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort>>::_common_init(regex::REGEX_FLAGS)

- ea: `0x18007eb2c`
- end: `0x18007edce`
- name: `?_common_init@?$basic_rpattern_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$perl_syntax@G@regex@@@regex@@IEAAXW4REGEX_FLAGS@2@@Z`
- size: `674`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800642b0`

## callees

- `0x18007d764`
- `0x18007eb2c`
- `0x18007fed0`
- `0x18008126c`
- `0x180081978`
- `0x180085dd8`
- `0x180089f90`
- `0x18008adf0`
- `0x18009e300`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18007ed94`
- `msvcrt!??3@YAXPEAX@Z` at `0x18007ed94`

## pseudocode

```c
void __fastcall regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_common_init(
        __int64 a1,
        int a2)
{
  __int64 **v3; // r14
  _QWORD *v4; // rax
  __int64 v5; // rbx
  _QWORD *next_group; // rsi
  _QWORD *v7; // rax
  __int64 *v8; // r10
  __int64 *v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // r10
  __int64 v14; // r9
  _QWORD *v15; // rax
  __int64 *v16; // r9
  __int64 v17; // r10
  __int64 v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // r9
  __int64 v22; // r10
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  int v26; // eax
  int v27; // eax
  int v28; // [rsp+38h] [rbp-39h] BYREF
  __int64 v29; // [rsp+40h] [rbp-31h] BYREF
  _QWORD v30[2]; // [rsp+48h] [rbp-29h] BYREF
  __int128 v31; // [rsp+58h] [rbp-19h] BYREF
  __int64 v32; // [rsp+68h] [rbp-9h]
  _QWORD v33[3]; // [rsp+70h] [rbp-1h] BYREF
  _QWORD v34[2]; // [rsp+88h] [rbp+17h] BYREF
  __int128 v35; // [rsp+98h] [rbp+27h]

  v33[1] = -2;
  v33[2] = a1;
  *(_QWORD *)(a1 + 24) = 0;
  v31 = 0;
  v32 = 0;
  v3 = (__int64 **)(a1 + 64);
  v4 = *(_QWORD **)(a1 + 64);
  if ( v4[3] < 8u )
    v4 = (_QWORD *)(a1 + 64);
  v33[0] = *v4;
  v28 = a2;
  v5 = a1 + 8;
  v29 = a1 + 8;
  next_group = (_QWORD *)regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_next_group(
                           a1,
                           (unsigned int)v33,
                           0,
                           (unsigned int)&v28,
                           (__int64)&v31);
  v7 = (_QWORD *)regex::detail::arena_allocator<char,std::allocator<char>>::allocate(v5, 16);
  v30[0] = v7;
  if ( v7 )
  {
    *v7 = &NaturalLanguage6::IKeyValuePair::`vftable';
    *v7 = &regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
    v7[1] = 0;
    *v7 = &regex::detail::end_of_pattern<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
  }
  next_group[1] = v7;
  v29 = 0;
  regex::detail::arena_guard::~arena_guard((regex::detail::arena_guard *)&v29);
  *(_QWORD *)(a1 + 96) = next_group;
  if ( next_group[5] == -1 && next_group[6] == -1 )
  {
    v34[0] = &v31;
    v34[1] = a1 + 104;
    v35 = xmmword_1800C6680;
    regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::width_this(
      next_group,
      v30,
      v34);
  }
  *(_OWORD *)(a1 + 48) = *(_OWORD *)(next_group + 5);
  *(_BYTE *)(a1 + 17) = 1;
  v8 = *v3;
  v9 = *v3;
  if ( (unsigned __int64)(*v3)[3] < 8 )
    v9 = (__int64 *)v3;
  v29 = *v9;
  if ( (*(_BYTE *)(a1 + 40) & 4) == 0 )
  {
    v10 = 0;
    v11 = next_group[3];
    if ( v11 )
    {
      do
      {
        v11 = *(_QWORD *)(v11 + 8);
        ++v10;
      }
      while ( v11 );
      if ( v10 == 1 )
      {
        v12 = (_QWORD *)std::wstring::end(v8, v30);
        if ( *v12 != v14 )
        {
          v15 = (_QWORD *)std::wstring::end(v13, v30);
          if ( (unsigned int)regex::perl_syntax<unsigned short>::reg_token(&v28, &v29, *v15) == 4 )
          {
            *(_DWORD *)(a1 + 40) &= ~0x10u;
            *(_BYTE *)(a1 + 17) = 0;
          }
        }
      }
    }
  }
  v16 = *v3;
  if ( (unsigned __int64)(*v3)[3] < 8 )
    v17 = (__int64)*v3;
  else
    v17 = *v16;
  v29 = v17;
  if ( (*(_DWORD *)(a1 + 40) & 0x18) == 8 )
  {
    v18 = 0;
    v19 = next_group[3];
    if ( v19 )
    {
      do
      {
        v19 = *(_QWORD *)(v19 + 8);
        ++v18;
      }
      while ( v19 );
      if ( v18 == 1 )
      {
        v20 = (_QWORD *)std::wstring::end(v16, v30);
        if ( *v20 != v22 )
        {
          v23 = (_QWORD *)std::wstring::end(v21, v30);
          if ( (unsigned int)regex::perl_syntax<unsigned short>::reg_token(&v28, &v29, *v23) == 7 )
          {
            v24 = (_QWORD *)std::wstring::end(*v3, v30);
            if ( *v24 != v29 )
            {
              v25 = (_QWORD *)std::wstring::end(*v3, v30);
              v26 = regex::perl_syntax<unsigned short>::quant_token(&v28, &v29, *v25) - 9;
              if ( !v26 || (v27 = v26 - 1) == 0 || (unsigned int)(v27 - 2) <= 1 )
                *(_BYTE *)(a1 + 17) = 0;
            }
          }
        }
      }
    }
  }
  if ( (_QWORD)v31 )
    operator delete((void *)v31);
}

```

## disassembly

```asm
0x18007eb2c  mov     rax, rsp
0x18007eb2f  mov     [rax+8], rcx
0x18007eb33  push    rbp
0x18007eb34  push    rdi
0x18007eb35  push    r14
0x18007eb37  lea     rbp, [rax-5Fh]
0x18007eb3b  sub     rsp, 0B0h
0x18007eb42  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x18007eb4a  mov     [rax+10h], rbx
0x18007eb4e  mov     [rax+18h], rsi
0x18007eb52  mov     rax, cs:__security_cookie
0x18007eb59  xor     rax, rsp
0x18007eb5c  mov     [rbp+57h+var_20], rax
0x18007eb60  mov     rdi, rcx
0x18007eb63  mov     [rbp+57h+var_48], rcx
0x18007eb67  mov     qword ptr [rcx+18h], 0
0x18007eb6f  xorps   xmm0, xmm0
0x18007eb72  movdqu  [rbp+57h+var_70], xmm0
0x18007eb77  mov     [rbp+57h+var_60], 0
0x18007eb7f  lea     r14, [rcx+40h]
0x18007eb83  mov     rax, [r14]
0x18007eb86  cmp     qword ptr [rax+18h], 8
0x18007eb8b  cmovb   rax, r14
0x18007eb8f  mov     rax, [rax]
0x18007eb92  mov     [rbp+57h+var_58], rax
0x18007eb96  mov     [rbp+57h+var_90], edx
0x18007eb99  lea     rbx, [rcx+8]
0x18007eb9d  mov     [rbp+57h+var_88], rbx
0x18007eba1  lea     rax, [rbp+57h+var_70]
0x18007eba5  mov     [rsp+0C0h+var_A0], rax
0x18007ebaa  lea     r9, [rbp+57h+var_90]
0x18007ebae  xor     r8d, r8d
0x18007ebb1  lea     rdx, [rbp+57h+var_58]
0x18007ebb5  call    ?_find_next_group@?$basic_rpattern_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$perl_syntax@G@regex@@@regex@@IEAAPEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAV342@AEAV?$perl_syntax@G@2@AEAV?$vector@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$allocator@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@@6@@Z; regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort>>::_find_next_group(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::perl_syntax<ushort> &,std::vector<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *>> &)
0x18007ebba  mov     rsi, rax
0x18007ebbd  mov     edx, 10h
0x18007ebc2  mov     rcx, rbx
0x18007ebc5  call    ?allocate@?$arena_allocator@DV?$allocator@D@std@@@detail@regex@@QEAAPEAD_KPEBX@Z; regex::detail::arena_allocator<char,std::allocator<char>>::allocate(unsigned __int64,void const *)
0x18007ebca  mov     [rbp+57h+var_80], rax
0x18007ebce  test    rax, rax
0x18007ebd1  jz      short loc_18007EBF9
0x18007ebd3  lea     rcx, ??_7IKeyValuePair@NaturalLanguage6@@6B@; const NaturalLanguage6::IKeyValuePair::`vftable'
0x18007ebda  mov     [rax], rcx
0x18007ebdd  lea     rcx, ??_7?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::`vftable'
0x18007ebe4  mov     [rax], rcx
0x18007ebe7  mov     qword ptr [rax+8], 0
0x18007ebef  lea     rcx, ??_7?$end_of_pattern@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::end_of_pattern<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::`vftable'
0x18007ebf6  mov     [rax], rcx
0x18007ebf9  mov     [rsi+8], rax
0x18007ebfd  mov     [rbp+57h+var_88], 0
0x18007ec05  lea     rcx, [rbp+57h+var_88]; this
0x18007ec09  call    ??1arena_guard@detail@regex@@QEAA@XZ; regex::detail::arena_guard::~arena_guard(void)
0x18007ec0e  mov     [rdi+60h], rsi
0x18007ec12  cmp     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x18007ec17  jnz     short loc_18007EC4C
0x18007ec19  cmp     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x18007ec1e  jnz     short loc_18007EC4C
0x18007ec20  lea     rax, [rbp+57h+var_70]
0x18007ec24  mov     [rbp+57h+var_40], rax
0x18007ec28  lea     rax, [rdi+68h]
0x18007ec2c  mov     [rbp+57h+var_38], rax
0x18007ec30  movups  xmm0, cs:xmmword_1800C6680
0x18007ec37  movdqu  [rbp+57h+var_30], xmm0
0x18007ec3c  lea     r8, [rbp+57h+var_40]
0x18007ec40  lea     rdx, [rbp+57h+var_80]
0x18007ec44  mov     rcx, rsi
0x18007ec47  call    ?width_this@?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@UEAA?AUwidth_type@3@AEAU?$width_param@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@23@@Z; regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::width_this(regex::detail::width_param<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &)
0x18007ec4c  movups  xmm0, xmmword ptr [rsi+28h]
0x18007ec50  movdqu  xmmword ptr [rdi+30h], xmm0
0x18007ec55  mov     byte ptr [rdi+11h], 1
0x18007ec59  mov     r10, [r14]
0x18007ec5c  mov     r9, r10
0x18007ec5f  cmp     qword ptr [r10+18h], 8
0x18007ec64  cmovb   r9, r14
0x18007ec68  mov     r9, [r9]
0x18007ec6b  mov     [rbp+57h+var_88], r9
0x18007ec6f  test    byte ptr [rdi+28h], 4
0x18007ec73  jnz     short loc_18007ECCC
0x18007ec75  xor     edx, edx
0x18007ec77  mov     rax, [rsi+18h]
0x18007ec7b  test    rax, rax
0x18007ec7e  jz      short loc_18007ECCC
0x18007ec80  mov     rax, [rax+8]
0x18007ec84  inc     rdx
0x18007ec87  test    rax, rax
0x18007ec8a  jnz     short loc_18007EC80
0x18007ec8c  cmp     rdx, 1
0x18007ec90  jnz     short loc_18007ECCC
0x18007ec92  lea     rdx, [rbp+57h+var_80]
0x18007ec96  mov     rcx, r10
0x18007ec99  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007ec9e  cmp     [rax], r9
0x18007eca1  jz      short loc_18007ECCC
0x18007eca3  lea     rdx, [rbp+57h+var_80]
0x18007eca7  mov     rcx, r10
0x18007ecaa  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007ecaf  mov     r8, [rax]
0x18007ecb2  lea     rdx, [rbp+57h+var_88]
0x18007ecb6  lea     rcx, [rbp+57h+var_90]
0x18007ecba  call    ?reg_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::reg_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18007ecbf  cmp     eax, 4
0x18007ecc2  jnz     short loc_18007ECCC
0x18007ecc4  and     dword ptr [rdi+28h], 0FFFFFFEFh
0x18007ecc8  mov     byte ptr [rdi+11h], 0
0x18007eccc  mov     r9, [r14]
0x18007eccf  cmp     qword ptr [r9+18h], 8
0x18007ecd4  jb      short loc_18007ECDB
0x18007ecd6  mov     r10, [r9]
0x18007ecd9  jmp     short loc_18007ECDE
0x18007ecdb  mov     r10, r9
0x18007ecde  mov     [rbp+57h+var_88], r10
0x18007ece2  mov     eax, [rdi+28h]
0x18007ece5  and     al, 18h
0x18007ece7  cmp     al, 8
0x18007ece9  jnz     loc_18007ED8B
0x18007ecef  xor     ecx, ecx
0x18007ecf1  mov     rax, [rsi+18h]
0x18007ecf5  test    rax, rax
0x18007ecf8  jz      loc_18007ED8B
0x18007ecfe  mov     rax, [rax+8]
0x18007ed02  inc     rcx
0x18007ed05  test    rax, rax
0x18007ed08  jnz     short loc_18007ECFE
0x18007ed0a  cmp     rcx, 1
0x18007ed0e  jnz     short loc_18007ED8B
0x18007ed10  lea     rdx, [rbp+57h+var_80]
0x18007ed14  mov     rcx, r9
0x18007ed17  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007ed1c  cmp     [rax], r10
0x18007ed1f  jz      short loc_18007ED8B
0x18007ed21  lea     rdx, [rbp+57h+var_80]
0x18007ed25  mov     rcx, r9
0x18007ed28  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007ed2d  mov     r8, [rax]
0x18007ed30  lea     rdx, [rbp+57h+var_88]
0x18007ed34  lea     rcx, [rbp+57h+var_90]
0x18007ed38  call    ?reg_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::reg_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18007ed3d  cmp     eax, 7
0x18007ed40  jnz     short loc_18007ED8B
0x18007ed42  lea     rdx, [rbp+57h+var_80]
0x18007ed46  mov     rcx, [r14]
0x18007ed49  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007ed4e  mov     rdx, [rbp+57h+var_88]
0x18007ed52  cmp     [rax], rdx
0x18007ed55  jz      short loc_18007ED8B
0x18007ed57  lea     rdx, [rbp+57h+var_80]
0x18007ed5b  mov     rcx, [r14]
0x18007ed5e  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007ed63  mov     r8, [rax]
0x18007ed66  lea     rdx, [rbp+57h+var_88]
0x18007ed6a  lea     rcx, [rbp+57h+var_90]
0x18007ed6e  call    ?quant_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::quant_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18007ed73  sub     eax, 9
0x18007ed76  jz      short loc_18007ED87
0x18007ed78  sub     eax, 1
0x18007ed7b  jz      short loc_18007ED87
0x18007ed7d  sub     eax, 2
0x18007ed80  jz      short loc_18007ED87
0x18007ed82  cmp     eax, 1
0x18007ed85  jnz     short loc_18007ED8B
0x18007ed87  mov     byte ptr [rdi+11h], 0
0x18007ed8b  mov     rcx, qword ptr [rbp+57h+var_70]
0x18007ed8f  test    rcx, rcx
0x18007ed92  jz      short loc_18007EDAA
0x18007ed94  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18007ed9a  xorps   xmm0, xmm0
0x18007ed9d  movdqu  [rbp+57h+var_70], xmm0
0x18007eda2  mov     [rbp+57h+var_60], 0
0x18007edaa  mov     rcx, [rbp+57h+var_20]
0x18007edae  xor     rcx, rsp; StackCookie
0x18007edb1  call    __security_check_cookie
0x18007edb6  lea     r11, [rsp+0C0h+var_10]
0x18007edbe  mov     rbx, [r11+28h]
0x18007edc2  mov     rsi, [r11+30h]
0x18007edc6  mov     rsp, r11
0x18007edc9  pop     r14
0x18007edcb  pop     rdi
0x18007edcc  pop     rbp
0x18007edcd  retn
```
