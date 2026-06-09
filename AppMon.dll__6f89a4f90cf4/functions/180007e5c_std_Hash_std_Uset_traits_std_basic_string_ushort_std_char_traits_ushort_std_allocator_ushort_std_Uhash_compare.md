# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Erase<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180007e5c`
- end: `0x180007eff`
- name: `??$_Erase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@AEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007be0`

## callees

- `0x180007e5c`
- `0x180007f08`
- `0x180007fb8`
- `0x18000939c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Erase<std::wstring>(
        _QWORD *a1,
        unsigned __int8 *a2)
{
  __int64 v3; // rdi
  __int64 v4; // r11
  _QWORD *v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF

  v3 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a2);
  v5 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                   a1,
                   v11,
                   v4,
                   v3)[1];
  if ( !v5 )
    return 0;
  v6 = a1[3];
  v7 = 2 * (v3 & a1[6]);
  if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6]) + 8) == v5 )
  {
    if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6])) == v5 )
    {
      v8 = a1[1];
      *(_QWORD *)(v6 + 16 * (v3 & a1[6])) = v8;
    }
    else
    {
      v8 = v5[1];
    }
    *(_QWORD *)(v6 + 8 * v7 + 8) = v8;
  }
  else if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6])) == v5 )
  {
    *(_QWORD *)(v6 + 16 * (v3 & a1[6])) = *v5;
  }
  v9 = *v5;
  --a1[2];
  *(_QWORD *)v5[1] = v9;
  *(_QWORD *)(v9 + 8) = v5[1];
  std::_List_node<std::wstring,void *>::_Freenode<std::allocator<std::_List_node<std::wstring,void *>>>();
  return 1;
}

```

## disassembly

```asm
0x180007e5c  mov     [rsp+arg_0], rbx
0x180007e61  push    rdi
0x180007e62  sub     rsp, 30h
0x180007e66  mov     rbx, rcx
0x180007e69  mov     r11, rdx
0x180007e6c  mov     rcx, rdx; unsigned __int8 *
0x180007e6f  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180007e74  mov     r9, rax
0x180007e77  lea     rdx, [rsp+38h+var_18]
0x180007e7c  mov     r8, r11
0x180007e7f  mov     rcx, rbx
0x180007e82  mov     rdi, rax
0x180007e85  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180007e8a  mov     rdx, [rax+8]
0x180007e8e  test    rdx, rdx
0x180007e91  jz      short loc_180007EF2
0x180007e93  mov     rcx, [rbx+30h]
0x180007e97  mov     r8, [rbx+18h]
0x180007e9b  and     rcx, rdi
0x180007e9e  add     rcx, rcx
0x180007ea1  cmp     [r8+rcx*8+8], rdx
0x180007ea6  jnz     short loc_180007EC3
0x180007ea8  cmp     [r8+rcx*8], rdx
0x180007eac  jnz     short loc_180007EB8
0x180007eae  mov     rax, [rbx+8]
0x180007eb2  mov     [r8+rcx*8], rax
0x180007eb6  jmp     short loc_180007EBC
0x180007eb8  mov     rax, [rdx+8]
0x180007ebc  mov     [r8+rcx*8+8], rax
0x180007ec1  jmp     short loc_180007ED0
0x180007ec3  cmp     [r8+rcx*8], rdx
0x180007ec7  jnz     short loc_180007ED0
0x180007ec9  mov     rax, [rdx]
0x180007ecc  mov     [r8+rcx*8], rax
0x180007ed0  mov     rcx, [rdx]
0x180007ed3  dec     qword ptr [rbx+10h]
0x180007ed7  mov     rax, [rdx+8]
0x180007edb  mov     [rax], rcx
0x180007ede  mov     rax, [rdx+8]
0x180007ee2  mov     [rcx+8], rax
0x180007ee6  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Freenode<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180007eeb  mov     eax, 1
0x180007ef0  jmp     short loc_180007EF4
0x180007ef2  xor     eax, eax
0x180007ef4  mov     rbx, [rsp+38h+arg_0]
0x180007ef9  add     rsp, 30h
0x180007efd  pop     rdi
0x180007efe  retn
```
