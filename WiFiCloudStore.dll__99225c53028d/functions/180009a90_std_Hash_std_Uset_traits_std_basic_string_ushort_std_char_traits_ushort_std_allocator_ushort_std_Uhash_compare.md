# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x180009a90`
- end: `0x180009c25`
- name: `??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `405`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000a2c8`

## callees

- `0x1800097f4`
- `0x180009a90`
- `0x18000a188`
- `0x18000a1a8`
- `0x18001956c`
- `0x18001b634`
- `0x1800291fc`
- `0x18003bb10`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009be9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009be9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r15
  __int64 v7; // rcx
  _QWORD *v8; // rbx
  _QWORD *v9; // rsi
  _QWORD *v10; // rsi
  const wchar_t *v11; // rdx
  size_t v12; // r8
  const wchar_t *v13; // rcx
  _QWORD *v14; // rbx
  _QWORD *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // r8
  _QWORD v20[9]; // [rsp+20h] [rbp-48h] BYREF

  v6 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((unsigned __int8 *)a3);
  v7 = a1[3];
  v8 = *(_QWORD **)(v7 + 16 * (a1[6] & v6) + 8);
  v9 = (_QWORD *)a1[1];
  if ( v8 == v9 )
  {
LABEL_10:
    if ( a1[2] == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v20[0] = a1 + 1;
    v14 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    v20[1] = v14;
    std::wstring::wstring(v14 + 2, a3);
    if ( (unsigned __int8)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Rehash_for_1(a1);
      v9 = (_QWORD *)*std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                        a1,
                        v20,
                        v14 + 2,
                        v6);
    }
    v15 = (_QWORD *)v9[1];
    ++a1[2];
    *v14 = v9;
    v14[1] = v15;
    *v15 = v14;
    v9[1] = v14;
    v16 = 2 * (v6 & a1[6]);
    v17 = a1[3];
    v18 = *(_QWORD **)(v17 + 16 * (v6 & a1[6]));
    if ( v18 == (_QWORD *)a1[1] )
    {
      *(_QWORD *)(v17 + 16 * (v6 & a1[6])) = v14;
    }
    else
    {
      if ( v18 == v9 )
      {
        *(_QWORD *)(v17 + 16 * (v6 & a1[6])) = v14;
        goto LABEL_16;
      }
      if ( *(_QWORD **)(v17 + 16 * (v6 & a1[6]) + 8) != v15 )
        goto LABEL_16;
    }
    *(_QWORD *)(v17 + 8 * v16 + 8) = v14;
LABEL_16:
    *(_QWORD *)a2 = v14;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  v10 = *(_QWORD **)(v7 + 16 * (a1[6] & v6));
  while ( 1 )
  {
    v11 = (const wchar_t *)(v8 + 2);
    if ( v8[5] > 7u )
      v11 = *(const wchar_t **)v11;
    v12 = *(_QWORD *)(a3 + 16);
    v13 = *(_QWORD *)(a3 + 24) <= 7u ? (const wchar_t *)a3 : *(const wchar_t **)a3;
    if ( v12 == v8[4] && (!v12 || !wmemcmp(v13, v11, v12)) )
      break;
    if ( v8 == v10 )
    {
      v9 = v8;
      goto LABEL_10;
    }
    v8 = (_QWORD *)v8[1];
  }
  *(_QWORD *)a2 = v8;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180009a90  push    rbx
0x180009a92  push    rbp
0x180009a93  push    rsi
0x180009a94  push    rdi
0x180009a95  push    r12
0x180009a97  push    r14
0x180009a99  push    r15
0x180009a9b  sub     rsp, 30h
0x180009a9f  mov     r14, r8
0x180009aa2  mov     rdi, rdx
0x180009aa5  mov     rbp, rcx
0x180009aa8  mov     rcx, r8; unsigned __int8 *
0x180009aab  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180009ab0  mov     r15, rax
0x180009ab3  and     rax, [rbp+30h]
0x180009ab7  add     rax, rax
0x180009aba  mov     rcx, [rbp+18h]
0x180009abe  mov     rbx, [rcx+rax*8+8]
0x180009ac3  lea     r12, [rbp+8]
0x180009ac7  mov     rsi, [r12]
0x180009acb  cmp     rbx, rsi
0x180009ace  jz      short loc_180009B0A
0x180009ad0  mov     rsi, [rcx+rax*8]
0x180009ad4  lea     rdx, [rbx+10h]
0x180009ad8  cmp     qword ptr [rbx+28h], 7
0x180009add  jbe     short loc_180009AE2
0x180009adf  mov     rdx, [rdx]; S2
0x180009ae2  mov     r8, [r14+10h]; N
0x180009ae6  cmp     qword ptr [r14+18h], 7
0x180009aeb  jbe     loc_180009BAB
0x180009af1  mov     rcx, [r14]; S1
0x180009af4  cmp     r8, [rbx+20h]
0x180009af8  jz      loc_180009BC7
0x180009afe  cmp     rbx, rsi
0x180009b01  jnz     loc_180009BB3
0x180009b07  mov     rsi, rbx
0x180009b0a  mov     rax, 555555555555555h
0x180009b14  cmp     [rbp+10h], rax
0x180009b18  jz      loc_180009BE2
0x180009b1e  mov     [rsp+68h+var_48], r12
0x180009b23  mov     [rsp+68h+var_40], 0
0x180009b2c  mov     ecx, 30h ; '0'
0x180009b31  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009b36  mov     rbx, rax
0x180009b39  mov     [rsp+68h+var_40], rax
0x180009b3e  lea     rcx, [rax+10h]
0x180009b42  mov     rdx, r14
0x180009b45  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180009b4a  nop
0x180009b4b  mov     rcx, rbp
0x180009b4e  call    ?_Check_rehash_required_1@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_NXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_rehash_required_1(void)
0x180009b53  test    al, al
0x180009b55  jnz     loc_180009BF0
0x180009b5b  mov     rdx, [rsi+8]
0x180009b5f  inc     qword ptr [rbp+10h]
0x180009b63  mov     [rbx], rsi
0x180009b66  mov     [rbx+8], rdx
0x180009b6a  mov     [rdx], rbx
0x180009b6d  mov     [rsi+8], rbx
0x180009b71  mov     rax, [rbp+30h]
0x180009b75  and     rax, r15
0x180009b78  add     rax, rax
0x180009b7b  mov     rcx, [rbp+18h]
0x180009b7f  mov     r8, [rcx+rax*8]
0x180009b83  cmp     r8, [r12]
0x180009b87  jnz     short loc_180009BBC
0x180009b89  mov     [rcx+rax*8], rbx
0x180009b8d  mov     [rcx+rax*8+8], rbx
0x180009b92  mov     [rdi], rbx
0x180009b95  mov     byte ptr [rdi+8], 1
0x180009b99  mov     rax, rdi
0x180009b9c  add     rsp, 30h
0x180009ba0  pop     r15
0x180009ba2  pop     r14
0x180009ba4  pop     r12
0x180009ba6  pop     rdi
0x180009ba7  pop     rsi
0x180009ba8  pop     rbp
0x180009ba9  pop     rbx
0x180009baa  retn
0x180009bab  mov     rcx, r14
0x180009bae  jmp     loc_180009AF4
0x180009bb3  mov     rbx, [rbx+8]
0x180009bb7  jmp     loc_180009AD4
0x180009bbc  cmp     r8, rsi
0x180009bbf  jnz     short loc_180009C14
0x180009bc1  mov     [rcx+rax*8], rbx
0x180009bc5  jmp     short loc_180009B92
0x180009bc7  test    r8, r8
0x180009bca  jz      short loc_180009BD9
0x180009bcc  call    wmemcmp
0x180009bd1  test    eax, eax
0x180009bd3  jnz     loc_180009AFE
0x180009bd9  mov     [rdi], rbx
0x180009bdc  mov     byte ptr [rdi+8], 0
0x180009be0  jmp     short loc_180009B99
0x180009be2  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180009be9  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180009bf0  mov     rcx, rbp
0x180009bf3  call    ?_Rehash_for_1@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Rehash_for_1(void)
0x180009bf8  lea     r8, [rbx+10h]
0x180009bfc  mov     r9, r15
0x180009bff  lea     rdx, [rsp+68h+var_48]
0x180009c04  mov     rcx, rbp
0x180009c07  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180009c0c  mov     rsi, [rax]
0x180009c0f  jmp     loc_180009B5B
0x180009c14  cmp     [rcx+rax*8+8], rdx
0x180009c19  jnz     loc_180009B92
0x180009c1f  jmp     loc_180009B8D
```
