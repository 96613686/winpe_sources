# regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_do_try_match<std::allocator<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>>(regex::detail::basic_rpattern_base_impl<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> const &,regex::detail::match_param<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &,std::vector<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>,std::allocator<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>> &,bool)

- ea: `0x180063d34`
- end: `0x180063e72`
- name: `??$_do_try_match@V?$allocator@V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@regex@@@std@@@?$regex_access@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@SA_NAEBV?$basic_rpattern_base_impl@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@12@AEAU?$match_param@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@12@AEAV?$vector@V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@regex@@V?$allocator@V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@regex@@@std@@@std@@_N@Z`
- size: `318`
- prototype: `char __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180063ab0`

## callees

- `0x180063d34`
- `0x180063e78`
- `0x1800651a0`
- `0x18007f1d8`
- `0x18007f43c`
- `0x180080a94`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180063dae`
- `msvcrt!_resetstkoflw` at `0x180063dae`

## pseudocode

```c
char __fastcall regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_do_try_match<std::allocator<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  char matched; // al
  char v7; // bl

  std::vector<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::resize(
    a3,
    *(_QWORD *)(a1 + 24));
  *a2 = *a3;
  a2[3] = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a3[1] - *a3) >> 4);
  if ( (unsigned __int8)regex::detail::basic_rpattern_base_impl<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_ok_to_recurse(a1) )
    matched = regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_do_match_impl(
                a1,
                a2,
                0);
  else
    matched = regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_do_match_with_stack(
                a1,
                a2,
                0);
  v7 = matched;
  regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_fixup_backrefs<std::allocator<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,std::allocator<unsigned __int64>>(
    a3,
    a1 + 104);
  return v7;
}

```

## disassembly

```asm
0x180063d34  mov     [rsp+arg_10], r8
0x180063d39  mov     [rsp+arg_8], rdx
0x180063d3e  mov     [rsp+arg_0], rcx
0x180063d43  push    rbx
0x180063d44  push    rsi
0x180063d45  push    rdi
0x180063d46  sub     rsp, 30h
0x180063d4a  mov     rsi, r8
0x180063d4d  mov     rbx, rdx
0x180063d50  mov     rdi, rcx
0x180063d53  mov     rdx, [rcx+18h]
0x180063d57  mov     rcx, r8
0x180063d5a  call    ?resize@?$vector@V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@regex@@V?$allocator@V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@regex@@@std@@@std@@QEAAX_K@Z; std::vector<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::resize(unsigned __int64)
0x180063d5f  mov     rax, [rsi]
0x180063d62  mov     [rbx], rax
0x180063d65  mov     rax, [rsi+8]
0x180063d69  sub     rax, [rsi]
0x180063d6c  sar     rax, 4
0x180063d70  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180063d7a  imul    rax, rcx
0x180063d7e  mov     [rbx+18h], rax
0x180063d82  mov     rcx, rdi
0x180063d85  call    ?_ok_to_recurse@?$basic_rpattern_base_impl@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@IEBA_NXZ; regex::detail::basic_rpattern_base_impl<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_ok_to_recurse(void)
0x180063d8a  xor     r8d, r8d
0x180063d8d  mov     rdx, rbx
0x180063d90  mov     rcx, rdi
0x180063d93  test    al, al
0x180063d95  jz      short loc_180063D9E
0x180063d97  call    ?_do_match_impl@?$regex_access@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@SA_NAEBV?$basic_rpattern_base_impl@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@23@AEAU?$match_param@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@23@_N@Z; regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_do_match_impl(regex::detail::basic_rpattern_base_impl<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> const &,regex::detail::match_param<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &,bool)
0x180063d9c  jmp     short loc_180063DA3
0x180063d9e  call    ?_do_match_with_stack@?$regex_access@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@SA_NAEBV?$basic_rpattern_base_impl@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@23@AEAU?$match_param@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@23@_N@Z; regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_do_match_with_stack(regex::detail::basic_rpattern_base_impl<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> const &,regex::detail::match_param<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &,bool)
0x180063da3  mov     [rsp+48h+var_28], al
0x180063da7  mov     bl, al
0x180063da9  jmp     loc_180063E5C
0x180063dae  call    cs:__imp__resetstkoflw
0x180063db4  xor     r9d, r9d
0x180063db7  mov     r8, [rsp+48h+arg_8]
0x180063dbc  cmp     [r8+18h], r9
0x180063dc0  jbe     loc_180063E4C
0x180063dc6  lea     rdx, [r9+r9*4]
0x180063dca  add     rdx, rdx
0x180063dcd  mov     rcx, [r8]
0x180063dd0  mov     rax, cs:?value@?$static_init@V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@regex@@@detail@regex@@2V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@3@B; regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> const regex::detail::static_init<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::value
0x180063dd7  mov     [rcx+rdx*8], rax
0x180063ddb  mov     rax, cs:qword_1800FF9A8
0x180063de2  mov     [rcx+rdx*8+8], rax
0x180063de7  mov     al, cs:byte_1800FF9B0
0x180063ded  mov     [rcx+rdx*8+10h], al
0x180063df1  mov     rax, cs:qword_1800FF9B8
0x180063df8  mov     [rcx+rdx*8+18h], rax
0x180063dfd  mov     rax, cs:qword_1800FF9C0
0x180063e04  mov     [rcx+rdx*8+20h], rax
0x180063e09  mov     al, cs:byte_1800FF9C8
0x180063e0f  mov     [rcx+rdx*8+28h], al
0x180063e13  mov     rax, cs:qword_1800FF9D0
0x180063e1a  mov     [rcx+rdx*8+30h], rax
0x180063e1f  mov     al, cs:byte_1800FF9D8
0x180063e25  mov     [rcx+rdx*8+38h], al
0x180063e29  mov     rax, cs:qword_1800FF9E0
0x180063e30  mov     [rcx+rdx*8+40h], rax
0x180063e35  mov     al, cs:byte_1800FF9E8
0x180063e3b  mov     [rcx+rdx*8+48h], al
0x180063e3f  inc     r9
0x180063e42  cmp     r9, [r8+18h]
0x180063e46  jb      loc_180063DC6
0x180063e4c  xor     bl, bl
0x180063e4e  mov     [rsp+48h+var_28], bl
0x180063e52  mov     rsi, [rsp+48h+arg_10]
0x180063e57  mov     rdi, [rsp+48h+arg_0]
0x180063e5c  lea     rdx, [rdi+68h]
0x180063e60  mov     rcx, rsi
0x180063e63  call    ??$_fixup_backrefs@V?$allocator@V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@regex@@@std@@V?$allocator@_K@2@@?$regex_access@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@SAXAEAV?$vector@V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@regex@@V?$allocator@V?$backref_tag@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@regex@@@std@@@std@@AEBV?$list@_KV?$allocator@_K@std@@@4@@Z; regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_fixup_backrefs<std::allocator<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>,std::allocator<unsigned __int64>>(std::vector<regex::backref_tag<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &,std::list<unsigned __int64> const &)
0x180063e68  mov     al, bl
0x180063e6a  add     rsp, 30h
0x180063e6e  pop     rdi
0x180063e6f  pop     rsi
0x180063e70  pop     rbx
0x180063e71  retn
0x1800ad20a  push    rbp
0x1800ad20c  sub     rsp, 20h
0x1800ad210  mov     rbp, rdx
0x1800ad213  mov     rax, [rcx]
0x1800ad216  xor     ecx, ecx
0x1800ad218  cmp     dword ptr [rax], 0C00000FDh
0x1800ad21e  setz    cl
0x1800ad221  mov     eax, ecx
0x1800ad223  add     rsp, 20h
0x1800ad227  pop     rbp
0x1800ad228  retn
```
