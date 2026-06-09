# std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bond::_bond_enumerators::ProtocolType::ProtocolType,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bond::_bond_enumerators::ProtocolType::ProtocolType>>,0>>::_Emplace_hint<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bond::_bond_enumerators::ProtocolType::ProtocolType> &>(std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * const,std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bond::_bond_enumerators::ProtocolType::ProtocolType> &)

- ea: `0x18002edc0`
- end: `0x18002eeb8`
- name: `??$_Emplace_hint@AEAU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@1@QEAU21@AEAU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@1@@Z`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180030520`

## callees

- `0x180010948`
- `0x180010d3c`
- `0x18002edc0`
- `0x18002f958`
- `0x180030390`
- `0x180030c58`
- `0x1800314dc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ee15`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ee15`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType,std::less<std::string>,std::allocator<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>,0>>::_Emplace_hint<std::pair<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType> &>(
        __int64 *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v4; // rax
  __int64 *v5; // rsi
  __int64 v6; // rbx
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 *v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+28h] [rbp-20h]
  __int64 v12; // [rsp+80h] [rbp+38h] BYREF

  v12 = (__int64)a1;
  v4 = std::_Tree<std::_Tmap_traits<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType,std::less<std::string>,std::allocator<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>,0>>::_Find_hint<std::string>(
         a1,
         (__int64)&v10,
         a2,
         a3);
  v5 = *(__int64 **)v4;
  v6 = *(_QWORD *)(v4 + 8);
  if ( *(_BYTE *)(v4 + 16) )
    return *(_QWORD *)v4;
  if ( qword_180048CD0 == 0x38E38E38E38E38ELL )
    std::_Xlength_error("map/set too long");
  v12 = bond::_bond_enumerators::ProtocolType::_name_to_value_ProtocolType;
  v10 = &bond::_bond_enumerators::ProtocolType::_name_to_value_ProtocolType;
  v11 = 0;
  v8 = std::_Allocate<16,std::_Default_allocate_traits>(72);
  v11 = v8;
  std::_Default_allocator_traits<std::allocator<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>>>::construct<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>,std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier> const &>(
    v9,
    v8 + 32,
    a3);
  std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(
    v8,
    &v12);
  std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(
    v8 + 8,
    &v12);
  std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(
    v8 + 16,
    &v12);
  *(_WORD *)(v8 + 24) = 0;
  v11 = 0;
  std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::BondDataType::BondDataType>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::BondDataType::BondDataType>,void *>>>(&v10);
  v10 = v5;
  v11 = v6;
  return std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Insert_node(
           &bond::_bond_enumerators::ProtocolType::_name_to_value_ProtocolType,
           &v10,
           v8);
}

```

## disassembly

```asm
0x18002edc0  mov     [rsp-30h+arg_0], rcx
0x18002edc5  push    rbp
0x18002edc6  push    rbx
0x18002edc7  push    rsi
0x18002edc8  push    rdi
0x18002edc9  push    r14
0x18002edcb  push    r15
0x18002edcd  mov     rbp, rsp
0x18002edd0  sub     rsp, 48h
0x18002edd4  mov     r14, r8
0x18002edd7  mov     r9, r8
0x18002edda  mov     r8, rdx
0x18002eddd  lea     rdx, [rbp+var_28]
0x18002ede1  call    ??$_Find_hint@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType,std::less<std::string>,std::allocator<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>>,0>>::_Find_hint<std::string>(std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * const,std::string const &)
0x18002ede6  mov     rsi, [rax]
0x18002ede9  mov     rbx, [rax+8]
0x18002eded  cmp     byte ptr [rax+10h], 0
0x18002edf1  jz      short loc_18002EDFB
0x18002edf3  mov     rax, rsi
0x18002edf6  jmp     loc_18002EEAB
0x18002edfb  mov     rax, 38E38E38E38E38Eh
0x18002ee05  cmp     cs:qword_180048CD0, rax
0x18002ee0c  jnz     short loc_18002EE1C
0x18002ee0e  lea     rcx, aMapSetTooLong; "map/set too long"
0x18002ee15  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002ee1c  mov     rax, cs:?_name_to_value_ProtocolType@ProtocolType@_bond_enumerators@bond@@3V?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@@std@@B; std::map<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType> const bond::_bond_enumerators::ProtocolType::_name_to_value_ProtocolType
0x18002ee23  mov     [rbp+arg_0], rax
0x18002ee27  lea     r15, ?_name_to_value_ProtocolType@ProtocolType@_bond_enumerators@bond@@3V?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@@std@@B; std::map<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType> const bond::_bond_enumerators::ProtocolType::_name_to_value_ProtocolType
0x18002ee2e  mov     [rbp+var_28], r15
0x18002ee32  mov     [rbp+var_20], 0
0x18002ee3a  mov     ecx, 48h ; 'H'
0x18002ee3f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002ee44  mov     rdi, rax
0x18002ee47  mov     [rbp+var_20], rax
0x18002ee4b  lea     rdx, [rax+20h]
0x18002ee4f  mov     r8, r14
0x18002ee52  call    ??$construct@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@std@@@std@@SAXAEAV?$allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@1@QEAU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@1@AEBU31@@Z; std::_Default_allocator_traits<std::allocator<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>>>::construct<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>,std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier> const &>(std::allocator<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>> &,std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier> * const,std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier> const &)
0x18002ee57  lea     rdx, [rbp+arg_0]
0x18002ee5b  mov     rcx, rdi
0x18002ee5e  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &)
0x18002ee63  lea     rcx, [rdi+8]
0x18002ee67  lea     rdx, [rbp+arg_0]
0x18002ee6b  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &)
0x18002ee70  lea     rcx, [rdi+10h]
0x18002ee74  lea     rdx, [rbp+arg_0]
0x18002ee78  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &)
0x18002ee7d  mov     word ptr [rdi+18h], 0
0x18002ee83  mov     [rbp+var_20], 0
0x18002ee8b  lea     rcx, [rbp+var_28]
0x18002ee8f  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4BondDataType@3_bond_enumerators@bond@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::BondDataType::BondDataType>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::BondDataType::BondDataType>,void *>>>(void)
0x18002ee94  mov     [rbp+var_28], rsi
0x18002ee98  mov     [rbp+var_20], rbx
0x18002ee9c  mov     r8, rdi
0x18002ee9f  lea     rdx, [rbp+var_28]
0x18002eea3  mov     rcx, r15
0x18002eea6  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::string>,void *> *>,std::_Tree_node<std::pair<std::string const,std::string>,void *> * const)
0x18002eeab  add     rsp, 48h
0x18002eeaf  pop     r15
0x18002eeb1  pop     r14
0x18002eeb3  pop     rdi
0x18002eeb4  pop     rsi
0x18002eeb5  pop     rbx
0x18002eeb6  pop     rbp
0x18002eeb7  retn
```
