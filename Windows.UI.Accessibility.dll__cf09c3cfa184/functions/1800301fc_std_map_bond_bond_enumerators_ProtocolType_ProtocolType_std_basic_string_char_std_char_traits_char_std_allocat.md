# std::map<bond::_bond_enumerators::ProtocolType::ProtocolType,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::less<bond::_bond_enumerators::ProtocolType::ProtocolType>,std::allocator<std::pair<bond::_bond_enumerators::ProtocolType::ProtocolType const,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>>::_Try_emplace<bond::_bond_enumerators::ProtocolType::ProtocolType const &,>(bond::_bond_enumerators::ProtocolType::ProtocolType const &)

- ea: `0x1800301fc`
- end: `0x18003033f`
- name: `??$_Try_emplace@AEBW4ProtocolType@1_bond_enumerators@bond@@$$V@?$map@W4ProtocolType@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4ProtocolType@1_bond_enumerators@bond@@@5@V?$allocator@U?$pair@$$CBW4ProtocolType@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4ProtocolType@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@_N@1@AEBW4ProtocolType@3_bond_enumerators@bond@@@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800307a0`

## callees

- `0x180010948`
- `0x180010d3c`
- `0x1800301fc`
- `0x1800303c4`
- `0x180030c88`
- `0x1800314dc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180030294`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180030294`

## pseudocode

```c
__int64 __fastcall std::map<enum bond::_bond_enumerators::ProtocolType::ProtocolType,std::string>::_Try_emplace<enum bond::_bond_enumerators::ProtocolType::ProtocolType const &,>(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // r9d
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int128 v11; // [rsp+30h] [rbp-30h] BYREF
  __int128 v12; // [rsp+40h] [rbp-20h]
  __int64 v13; // [rsp+80h] [rbp+20h] BYREF
  _DWORD *v14; // [rsp+98h] [rbp+38h] BYREF

  v13 = a1;
  v4 = *(_QWORD *)(bond::_bond_enumerators::ProtocolType::_value_to_name_ProtocolType + 8);
  v12 = (unsigned __int64)v4;
  v5 = bond::_bond_enumerators::ProtocolType::_value_to_name_ProtocolType;
  if ( !*(_BYTE *)(v4 + 25) )
  {
    v6 = *a3;
    do
    {
      *(_QWORD *)&v12 = v4;
      if ( *(_DWORD *)(v4 + 32) >= v6 )
      {
        DWORD2(v12) = 1;
        v5 = v4;
      }
      else
      {
        DWORD2(v12) = 0;
        v4 += 16;
      }
      v4 = *(_QWORD *)v4;
    }
    while ( !*(_BYTE *)(v4 + 25) );
  }
  if ( *(_BYTE *)(v5 + 25) || *a3 < *(_DWORD *)(v5 + 32) )
  {
    if ( qword_180047310 == 0x38E38E38E38E38ELL )
      std::_Xlength_error("map/set too long");
    v14 = a3;
    v13 = bond::_bond_enumerators::ProtocolType::_value_to_name_ProtocolType;
    *(_QWORD *)&v11 = &bond::_bond_enumerators::ProtocolType::_value_to_name_ProtocolType;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(72);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<enum bond::_bond_enumerators::Modifier::Modifier const,std::string>,void *>>>::construct<std::pair<enum bond::_bond_enumerators::Modifier::Modifier const,std::string>,std::piecewise_construct_t const &,std::tuple<enum bond::_bond_enumerators::Modifier::Modifier const &>,std::tuple<>>(
      v8,
      v7 + 32,
      v9,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(
      v7,
      &v13);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(
      v7 + 8,
      &v13);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,enum bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(
      v7 + 16,
      &v13);
    *(_WORD *)(v7 + 24) = 0;
    *((_QWORD *)&v11 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum bond::_bond_enumerators::Modifier::Modifier const,std::string>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum bond::_bond_enumerators::Modifier::Modifier const,std::string>,void *>>>(&v11);
    v11 = v12;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Insert_node(
                      &bond::_bond_enumerators::ProtocolType::_value_to_name_ProtocolType,
                      &v11,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v5;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800301fc  mov     [rsp-18h+arg_8], rbx
0x180030201  mov     [rsp-18h+arg_0], rcx
0x180030206  push    rbp
0x180030207  push    rsi
0x180030208  push    rdi
0x180030209  mov     rbp, rsp
0x18003020c  sub     rsp, 60h
0x180030210  mov     rdi, rdx
0x180030213  mov     rdx, cs:?_value_to_name_ProtocolType@ProtocolType@_bond_enumerators@bond@@3V?$map@W4ProtocolType@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4ProtocolType@1_bond_enumerators@bond@@@5@V?$allocator@U?$pair@$$CBW4ProtocolType@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@5@@std@@B; std::map<bond::_bond_enumerators::ProtocolType::ProtocolType,std::string> const bond::_bond_enumerators::ProtocolType::_value_to_name_ProtocolType
0x18003021a  mov     rax, [rdx+8]
0x18003021e  mov     qword ptr [rbp+var_20], rax
0x180030222  mov     qword ptr [rbp+var_20+8], 0
0x18003022a  mov     rcx, rdx
0x18003022d  cmp     byte ptr [rax+19h], 0
0x180030231  jnz     short loc_180030260
0x180030233  mov     r9d, [r8]
0x180030236  mov     qword ptr [rbp+var_20], rax
0x18003023a  cmp     [rax+20h], r9d
0x18003023e  jge     short loc_18003024D
0x180030240  mov     dword ptr [rbp+var_20+8], 0
0x180030247  add     rax, 10h
0x18003024b  jmp     short loc_180030257
0x18003024d  mov     dword ptr [rbp+var_20+8], 1
0x180030254  mov     rcx, rax
0x180030257  mov     rax, [rax]
0x18003025a  cmp     byte ptr [rax+19h], 0
0x18003025e  jz      short loc_180030236
0x180030260  cmp     byte ptr [rcx+19h], 0
0x180030264  jnz     short loc_18003027A
0x180030266  mov     eax, [rcx+20h]
0x180030269  cmp     [r8], eax
0x18003026c  jl      short loc_18003027A
0x18003026e  mov     [rdi], rcx
0x180030271  mov     byte ptr [rdi+8], 0
0x180030275  jmp     loc_18003032C
0x18003027a  mov     rax, 38E38E38E38E38Eh
0x180030284  cmp     cs:qword_180047310, rax
0x18003028b  jnz     short loc_18003029B
0x18003028d  lea     rcx, aMapSetTooLong; "map/set too long"
0x180030294  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18003029b  mov     [rbp+arg_18], r8
0x18003029f  mov     [rbp+arg_0], rdx
0x1800302a3  lea     rsi, ?_value_to_name_ProtocolType@ProtocolType@_bond_enumerators@bond@@3V?$map@W4ProtocolType@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4ProtocolType@1_bond_enumerators@bond@@@5@V?$allocator@U?$pair@$$CBW4ProtocolType@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@5@@std@@B; std::map<bond::_bond_enumerators::ProtocolType::ProtocolType,std::string> const bond::_bond_enumerators::ProtocolType::_value_to_name_ProtocolType
0x1800302aa  mov     qword ptr [rbp+var_30], rsi
0x1800302ae  mov     qword ptr [rbp+var_30+8], 0
0x1800302b6  mov     ecx, 48h ; 'H'
0x1800302bb  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800302c0  mov     rbx, rax
0x1800302c3  lea     rdx, [rax+20h]
0x1800302c7  lea     r9, [rbp+arg_18]
0x1800302cb  call    ??$construct@U?$pair@$$CBW4Modifier@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBW4Modifier@1_bond_enumerators@bond@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4Modifier@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4Modifier@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBW4Modifier@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBW4Modifier@1_bond_enumerators@bond@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<bond::_bond_enumerators::Modifier::Modifier const,std::string>,void *>>>::construct<std::pair<bond::_bond_enumerators::Modifier::Modifier const,std::string>,std::piecewise_construct_t const &,std::tuple<bond::_bond_enumerators::Modifier::Modifier const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<bond::_bond_enumerators::Modifier::Modifier const,std::string>,void *>> &,std::pair<bond::_bond_enumerators::Modifier::Modifier const,std::string> * const,std::piecewise_construct_t const &,std::tuple<bond::_bond_enumerators::Modifier::Modifier const &> &&,std::tuple<> &&)
0x1800302d0  lea     rdx, [rbp+arg_0]
0x1800302d4  mov     rcx, rbx
0x1800302d7  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &)
0x1800302dc  lea     rcx, [rbx+8]
0x1800302e0  lea     rdx, [rbp+arg_0]
0x1800302e4  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &)
0x1800302e9  lea     rcx, [rbx+10h]
0x1800302ed  lea     rdx, [rbp+arg_0]
0x1800302f1  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> *,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &>(std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &,std::_Tree_node<std::pair<std::string const,bond::_bond_enumerators::ProtocolType::ProtocolType>,void *> * &)
0x1800302f6  mov     word ptr [rbx+18h], 0
0x1800302fc  mov     qword ptr [rbp+var_30+8], 0
0x180030304  lea     rcx, [rbp+var_30]
0x180030308  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4Modifier@1_bond_enumerators@bond@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<bond::_bond_enumerators::Modifier::Modifier const,std::string>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<bond::_bond_enumerators::Modifier::Modifier const,std::string>,void *>>>(void)
0x18003030d  movups  xmm0, [rbp+var_20]
0x180030311  movdqu  [rbp+var_30], xmm0
0x180030316  mov     r8, rbx
0x180030319  lea     rdx, [rbp+var_30]
0x18003031d  mov     rcx, rsi
0x180030320  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::string>,void *> *>,std::_Tree_node<std::pair<std::string const,std::string>,void *> * const)
0x180030325  mov     [rdi], rax
0x180030328  mov     byte ptr [rdi+8], 1
0x18003032c  mov     rax, rdi
0x18003032f  mov     rbx, [rsp+60h+arg_8]
0x180030337  add     rsp, 60h
0x18003033b  pop     rdi
0x18003033c  pop     rsi
0x18003033d  pop     rbp
0x18003033e  retn
```
