# std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bond::_bond_enumerators::ProtocolType::ProtocolType,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bond::_bond_enumerators::ProtocolType::ProtocolType>>,0>>::_Find_hint<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>(std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * const,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18002f958`
- end: `0x18002fc6b`
- name: `??$_Find_hint@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002edc0`

## callees

- `0x1800050aa`
- `0x1800166b4`
- `0x18002f958`
- `0x18002fe64`
- `0x180030eec`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType,std::less<std::string>,std::allocator<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>,0>>::_Find_hint<std::string>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 v7; // rbx
  size_t *v8; // r14
  size_t v9; // rsi
  const void *v10; // rax
  size_t v11; // r8
  const void *v12; // r9
  int v13; // eax
  __int64 v14; // rcx
  __int64 *v15; // r15
  size_t v16; // rbx
  const void *v17; // rax
  size_t v18; // r8
  const void *v19; // r9
  int v20; // eax
  const void *v22; // rax
  size_t v23; // r8
  const void *v24; // r9
  int v25; // eax
  __int64 *v26; // rbx
  __int64 *v27; // rax
  const void *v28; // rax
  const void *v29; // rdx
  size_t v30; // r8
  int v31; // eax
  __int64 v32; // rax
  __int64 v33; // rbx
  size_t v34; // r15
  const void *v35; // rax
  const void *v36; // rdx
  size_t v37; // r8
  int v38; // eax
  bool v39; // zf
  size_t v40; // r15
  const void *v41; // rax
  const void *v42; // rdx
  size_t v43; // r8
  int v44; // eax
  __int64 v45; // rbx
  size_t v46; // rsi
  const void *v47; // rax
  size_t v48; // r8
  const void *v49; // r9
  int v50; // eax
  char v51; // al
  __int128 v52; // [rsp+20h] [rbp-48h] BYREF
  __int64 v53; // [rsp+30h] [rbp-38h]
  __int64 *v54; // [rsp+70h] [rbp+8h] BYREF

  v54 = a1;
  if ( *((_BYTE *)a3 + 25) )
  {
    v7 = bond::_bond_enumerators::ProtocolType::_name_to_value_ProtocolType + 16;
    if ( !*(_BYTE *)(*(_QWORD *)(bond::_bond_enumerators::ProtocolType::_name_to_value_ProtocolType + 8) + 25LL) )
    {
      v8 = (size_t *)(a4 + 16);
      v9 = *(_QWORD *)(*(_QWORD *)v7 + 48LL);
      std::_String_val<std::_Simple_types<char>>::_Myptr(*(_QWORD *)v7 + 32LL);
      v10 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a4);
      v13 = memcmp_0(v12, v10, v11);
      if ( v13 )
      {
        if ( v13 < 0 )
          goto LABEL_7;
LABEL_54:
        std::_Tree<std::_Tmap_traits<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType,std::less<std::string>,std::allocator<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>,0>>::_Find_lower_bound<std::string>(
          v14,
          &v52,
          a4);
        v45 = v53;
        if ( !*(_BYTE *)(v53 + 25) )
        {
          v46 = *(_QWORD *)(v53 + 48);
          std::_String_val<std::_Simple_types<char>>::_Myptr(a4);
          v47 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(v45 + 32);
          v50 = memcmp_0(v49, v47, v48);
          if ( v50 )
          {
            if ( v50 < 0 )
              goto LABEL_57;
          }
          else if ( *v8 < v46 )
          {
            goto LABEL_57;
          }
          v51 = 1;
          goto LABEL_58;
        }
LABEL_57:
        v51 = 0;
LABEL_58:
        if ( !v51 )
        {
          *(_OWORD *)a2 = v52;
          goto LABEL_13;
        }
        *(_QWORD *)a2 = v45;
        *(_QWORD *)(a2 + 8) = 2;
LABEL_34:
        *(_BYTE *)(a2 + 16) = 1;
        goto LABEL_14;
      }
      if ( v9 >= *v8 )
        goto LABEL_54;
    }
LABEL_7:
    *(_QWORD *)a2 = *(_QWORD *)v7;
LABEL_8:
    *(_QWORD *)(a2 + 8) = 0;
LABEL_13:
    *(_BYTE *)(a2 + 16) = 0;
    goto LABEL_14;
  }
  v15 = a3 + 4;
  v8 = (size_t *)(a4 + 16);
  v16 = a3[6];
  if ( a3 == *(__int64 **)bond::_bond_enumerators::ProtocolType::_name_to_value_ProtocolType )
  {
    std::_String_val<std::_Simple_types<char>>::_Myptr(a4);
    v17 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(v15);
    v20 = memcmp_0(v19, v17, v18);
    if ( v20 )
    {
      if ( v20 >= 0 )
        goto LABEL_54;
    }
    else if ( *v8 >= v16 )
    {
      goto LABEL_54;
    }
    goto LABEL_12;
  }
  std::_String_val<std::_Simple_types<char>>::_Myptr(a4);
  v22 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(v15);
  v25 = memcmp_0(v24, v22, v23);
  if ( v25 )
  {
    if ( v25 < 0 )
    {
LABEL_19:
      v26 = (__int64 *)*a3;
      if ( *(_BYTE *)(*a3 + 25) )
      {
        v26 = (__int64 *)a3[1];
        v27 = a3;
        while ( !*((_BYTE *)v26 + 25) && v27 == (__int64 *)*v26 )
        {
          v27 = v26;
          v26 = (__int64 *)v26[1];
        }
        if ( *((_BYTE *)v27 + 25) )
          v26 = v27;
      }
      else
      {
        while ( !*(_BYTE *)(v26[2] + 25) )
          v26 = (__int64 *)v26[2];
      }
      std::_String_val<std::_Simple_types<char>>::_Myptr(a4);
      v40 = v26[6];
      v41 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(v26 + 4);
      v43 = v40;
      if ( *v8 < v40 )
        v43 = *v8;
      v44 = memcmp_0(v41, v42, v43);
      if ( v44 )
      {
        if ( v44 >= 0 )
          goto LABEL_54;
      }
      else if ( v40 >= *v8 )
      {
        goto LABEL_54;
      }
      if ( *(_BYTE *)(v26[2] + 25) )
      {
        *(_QWORD *)a2 = v26;
        goto LABEL_8;
      }
LABEL_12:
      *(_QWORD *)(a2 + 8) = 1;
      *(_QWORD *)a2 = a3;
      goto LABEL_13;
    }
  }
  else if ( *v8 < v16 )
  {
    goto LABEL_19;
  }
  std::_String_val<std::_Simple_types<char>>::_Myptr(a4);
  v28 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(v15);
  v30 = v16;
  if ( *v8 < v16 )
    v30 = *v8;
  v31 = memcmp_0(v28, v29, v30);
  if ( v31 )
  {
    if ( v31 < 0 )
      goto LABEL_26;
LABEL_33:
    *(_QWORD *)a2 = a3;
    *(_QWORD *)(a2 + 8) = 0;
    goto LABEL_34;
  }
  if ( v16 >= *v8 )
    goto LABEL_33;
LABEL_26:
  v54 = a3;
  v32 = std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,enum bond::_bond_enumerators::Modifier::Modifier>>>,std::_Iterator_base0>::operator++(&v54);
  v33 = *(_QWORD *)v32;
  if ( !*(_BYTE *)(*(_QWORD *)v32 + 25LL) )
  {
    v34 = *(_QWORD *)(v33 + 48);
    std::_String_val<std::_Simple_types<char>>::_Myptr(v33 + 32);
    v35 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a4);
    v37 = *v8;
    if ( v34 < *v8 )
      v37 = v34;
    v38 = memcmp_0(v35, v36, v37);
    if ( v38 )
    {
      if ( v38 >= 0 )
        goto LABEL_54;
    }
    else if ( *v8 >= v34 )
    {
      goto LABEL_54;
    }
  }
  v39 = *(_BYTE *)(a3[2] + 25) == 0;
  *(_BYTE *)(a2 + 16) = 0;
  if ( v39 )
  {
    *(_QWORD *)a2 = v33;
    *(_QWORD *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = a3;
    *(_QWORD *)(a2 + 8) = 0;
  }
LABEL_14:
  *(_DWORD *)(a2 + 17) = 0;
  *(_WORD *)(a2 + 21) = 0;
  *(_BYTE *)(a2 + 23) = 0;
  return a2;
}

```

## disassembly

```asm
0x18002f958  mov     [rsp+arg_8], rbx
0x18002f95d  mov     [rsp+arg_10], rbp
0x18002f962  mov     [rsp+arg_0], rcx
0x18002f967  push    rsi
0x18002f968  push    rdi
0x18002f969  push    r12
0x18002f96b  push    r14
0x18002f96d  push    r15
0x18002f96f  sub     rsp, 40h
0x18002f973  mov     rax, cs:?_name_to_value_ProtocolType@ProtocolType@_bond_enumerators@bond@@3V?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@@std@@B; std::map<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType> const bond::_bond_enumerators::ProtocolType::_name_to_value_ProtocolType
0x18002f97a  xor     r12d, r12d
0x18002f97d  mov     rbp, r9
0x18002f980  mov     rsi, r8
0x18002f983  mov     rdi, rdx
0x18002f986  cmp     [r8+19h], r12b
0x18002f98a  jz      short loc_18002F9EF
0x18002f98c  lea     rbx, [rax+10h]
0x18002f990  mov     rax, [rax+8]
0x18002f994  cmp     [rax+19h], r12b
0x18002f998  jnz     short loc_18002F9E3
0x18002f99a  mov     rcx, [rbx]
0x18002f99d  lea     r14, [r9+10h]
0x18002f9a1  add     rcx, 20h ; ' '
0x18002f9a5  mov     rsi, [rcx+10h]
0x18002f9a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002f9ae  mov     r8, [r14]
0x18002f9b1  mov     rcx, rbp
0x18002f9b4  cmp     r8, rsi
0x18002f9b7  mov     r9, rax
0x18002f9ba  cmovnb  r8, rsi
0x18002f9be  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002f9c3  mov     rdx, rax; Buf2
0x18002f9c6  mov     rcx, r9; Buf1
0x18002f9c9  call    memcmp_0
0x18002f9ce  test    eax, eax
0x18002f9d0  jz      short loc_18002F9DA
0x18002f9d2  jns     loc_18002FBF2
0x18002f9d8  jmp     short loc_18002F9E3
0x18002f9da  cmp     rsi, [r14]
0x18002f9dd  jnb     loc_18002FBF2
0x18002f9e3  mov     rax, [rbx]
0x18002f9e6  mov     [rdi], rax
0x18002f9e9  mov     [rdi+8], r12
0x18002f9ed  jmp     short loc_18002FA3D
0x18002f9ef  lea     r15, [r8+20h]
0x18002f9f3  mov     rcx, rbp
0x18002f9f6  lea     r14, [r9+10h]
0x18002f9fa  mov     rbx, [r15+10h]
0x18002f9fe  cmp     rsi, [rax]
0x18002fa01  jnz     short loc_18002FA74
0x18002fa03  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fa08  cmp     rbx, [r14]
0x18002fa0b  mov     r8, rbx
0x18002fa0e  mov     rcx, r15
0x18002fa11  mov     r9, rax
0x18002fa14  cmovnb  r8, [r14]
0x18002fa18  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fa1d  mov     rdx, rax; Buf2
0x18002fa20  mov     rcx, r9; Buf1
0x18002fa23  call    memcmp_0
0x18002fa28  test    eax, eax
0x18002fa2a  jz      short loc_18002FA69
0x18002fa2c  jns     loc_18002FBF2
0x18002fa32  mov     qword ptr [rdi+8], 1
0x18002fa3a  mov     [rdi], rsi
0x18002fa3d  mov     [rdi+10h], r12b
0x18002fa41  xor     eax, eax
0x18002fa43  lea     r11, [rsp+68h+var_28]
0x18002fa48  mov     rbx, [r11+38h]
0x18002fa4c  mov     rbp, [r11+40h]
0x18002fa50  mov     [rdi+11h], eax
0x18002fa53  mov     [rdi+15h], ax
0x18002fa57  mov     [rdi+17h], al
0x18002fa5a  mov     rax, rdi
0x18002fa5d  mov     rsp, r11
0x18002fa60  pop     r15
0x18002fa62  pop     r14
0x18002fa64  pop     r12
0x18002fa66  pop     rdi
0x18002fa67  pop     rsi
0x18002fa68  retn
0x18002fa69  cmp     [r14], rbx
0x18002fa6c  jnb     loc_18002FBF2
0x18002fa72  jmp     short loc_18002FA32
0x18002fa74  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fa79  cmp     rbx, [r14]
0x18002fa7c  mov     r8, rbx
0x18002fa7f  mov     rcx, r15
0x18002fa82  mov     r9, rax
0x18002fa85  cmovnb  r8, [r14]
0x18002fa89  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fa8e  mov     rdx, rax; Buf2
0x18002fa91  mov     rcx, r9; Buf1
0x18002fa94  call    memcmp_0
0x18002fa99  test    eax, eax
0x18002fa9b  jz      short loc_18002FAB8
0x18002fa9d  jns     short loc_18002FABD
0x18002fa9f  mov     rbx, [rsi]
0x18002faa2  cmp     [rbx+19h], r12b
0x18002faa6  jz      loc_18002FB9D
0x18002faac  mov     rbx, [rsi+8]
0x18002fab0  mov     rax, rsi
0x18002fab3  jmp     loc_18002FB89
0x18002fab8  cmp     [r14], rbx
0x18002fabb  jb      short loc_18002FA9F
0x18002fabd  mov     rcx, rbp
0x18002fac0  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fac5  mov     rcx, r15
0x18002fac8  mov     rdx, rax
0x18002facb  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fad0  cmp     [r14], rbx
0x18002fad3  mov     r8, rbx
0x18002fad6  mov     rcx, rax; Buf1
0x18002fad9  cmovb   r8, [r14]; Size
0x18002fadd  call    memcmp_0
0x18002fae2  test    eax, eax
0x18002fae4  jz      short loc_18002FB35
0x18002fae6  jns     short loc_18002FB3A
0x18002fae8  lea     rcx, [rsp+68h+arg_0]
0x18002faed  mov     [rsp+68h+arg_0], rsi
0x18002faf2  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,bond::_bond_enumerators::Modifier::Modifier>>>,std::_Iterator_base0>::operator++(void)
0x18002faf7  mov     rbx, [rax]
0x18002fafa  cmp     [rbx+19h], r12b
0x18002fafe  jnz     short loc_18002FB53
0x18002fb00  lea     rcx, [rbx+20h]
0x18002fb04  mov     r15, [rcx+10h]
0x18002fb08  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fb0d  mov     rcx, rbp
0x18002fb10  mov     rdx, rax
0x18002fb13  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fb18  mov     r8, [r14]
0x18002fb1b  mov     rcx, rax; Buf1
0x18002fb1e  cmp     r15, r8
0x18002fb21  cmovb   r8, r15; Size
0x18002fb25  call    memcmp_0
0x18002fb2a  test    eax, eax
0x18002fb2c  jz      short loc_18002FB4A
0x18002fb2e  js      short loc_18002FB53
0x18002fb30  jmp     loc_18002FBF2
0x18002fb35  cmp     rbx, [r14]
0x18002fb38  jb      short loc_18002FAE8
0x18002fb3a  mov     [rdi], rsi
0x18002fb3d  mov     [rdi+8], r12
0x18002fb41  mov     byte ptr [rdi+10h], 1
0x18002fb45  jmp     loc_18002FA41
0x18002fb4a  cmp     [r14], r15
0x18002fb4d  jnb     loc_18002FBF2
0x18002fb53  mov     rax, [rsi+10h]
0x18002fb57  cmp     [rax+19h], r12b
0x18002fb5b  mov     [rdi+10h], r12b
0x18002fb5f  jz      short loc_18002FB6D
0x18002fb61  mov     [rdi], rsi
0x18002fb64  mov     [rdi+8], r12
0x18002fb68  jmp     loc_18002FA41
0x18002fb6d  mov     [rdi], rbx
0x18002fb70  mov     qword ptr [rdi+8], 1
0x18002fb78  jmp     loc_18002FA41
0x18002fb7d  cmp     rax, [rbx]
0x18002fb80  jnz     short loc_18002FB8F
0x18002fb82  mov     rax, rbx
0x18002fb85  mov     rbx, [rbx+8]
0x18002fb89  cmp     [rbx+19h], r12b
0x18002fb8d  jz      short loc_18002FB7D
0x18002fb8f  cmp     [rax+19h], r12b
0x18002fb93  cmovnz  rbx, rax
0x18002fb97  jmp     short loc_18002FBA7
0x18002fb99  mov     rbx, [rbx+10h]
0x18002fb9d  mov     rax, [rbx+10h]
0x18002fba1  cmp     [rax+19h], r12b
0x18002fba5  jz      short loc_18002FB99
0x18002fba7  mov     rcx, rbp
0x18002fbaa  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fbaf  mov     r15, [rbx+30h]
0x18002fbb3  lea     rcx, [rbx+20h]
0x18002fbb7  mov     rdx, rax
0x18002fbba  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fbbf  cmp     [r14], r15
0x18002fbc2  mov     r8, r15
0x18002fbc5  mov     rcx, rax; Buf1
0x18002fbc8  cmovb   r8, [r14]; Size
0x18002fbcc  call    memcmp_0
0x18002fbd1  test    eax, eax
0x18002fbd3  jz      short loc_18002FBED
0x18002fbd5  jns     short loc_18002FBF2
0x18002fbd7  mov     rax, [rbx+10h]
0x18002fbdb  cmp     [rax+19h], r12b
0x18002fbdf  jz      loc_18002FA32
0x18002fbe5  mov     [rdi], rbx
0x18002fbe8  jmp     loc_18002F9E9
0x18002fbed  cmp     r15, [r14]
0x18002fbf0  jb      short loc_18002FBD7
0x18002fbf2  mov     r8, rbp
0x18002fbf5  lea     rdx, [rsp+68h+var_48]
0x18002fbfa  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType,std::less<std::string>,std::allocator<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18002fbff  mov     rbx, [rsp+68h+var_38]
0x18002fc04  cmp     [rbx+19h], r12b
0x18002fc08  jnz     short loc_18002FC3D
0x18002fc0a  mov     rsi, [rbx+30h]
0x18002fc0e  mov     rcx, rbp
0x18002fc11  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fc16  cmp     rsi, [r14]
0x18002fc19  lea     rcx, [rbx+20h]
0x18002fc1d  mov     r8, rsi
0x18002fc20  mov     r9, rax
0x18002fc23  cmovnb  r8, [r14]
0x18002fc27  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002fc2c  mov     rdx, rax; Buf2
0x18002fc2f  mov     rcx, r9; Buf1
0x18002fc32  call    memcmp_0
0x18002fc37  test    eax, eax
0x18002fc39  jz      short loc_18002FC54
0x18002fc3b  jns     short loc_18002FC59
0x18002fc3d  mov     al, r12b
0x18002fc40  test    al, al
0x18002fc42  jz      short loc_18002FC5D
0x18002fc44  mov     [rdi], rbx
0x18002fc47  mov     qword ptr [rdi+8], 2
0x18002fc4f  jmp     loc_18002FB41
0x18002fc54  cmp     [r14], rsi
0x18002fc57  jb      short loc_18002FC3D
0x18002fc59  mov     al, 1
0x18002fc5b  jmp     short loc_18002FC40
0x18002fc5d  movups  xmm0, [rsp+68h+var_48]
0x18002fc62  movdqu  xmmword ptr [rdi], xmm0
0x18002fc66  jmp     loc_18002FA3D
```
