# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::emplace<std::pair<int const,Docking::VirtualInput::TouchInput>>(std::pair<int const,Docking::VirtualInput::TouchInput> &&)

- ea: `0x180016100`
- end: `0x18001630b`
- name: `??$emplace@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@1@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180019e78`

## callees

- `0x18000b810`
- `0x180015750`
- `0x180015870`
- `0x1800159c0`
- `0x180015ce0`
- `0x180016100`
- `0x180016bd0`
- `0x180018910`
- `0x180018960`
- `0x180018f40`
- `0x180018f70`
- `0x1800190d0`
- `0x1800191c0`
- `0x180019210`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::emplace<std::pair<int const,Docking::VirtualInput::TouchInput>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 inserted; // rax
  char v7; // [rsp+20h] [rbp-A8h] BYREF
  char v8[7]; // [rsp+21h] [rbp-A7h] BYREF
  __int64 v9; // [rsp+28h] [rbp-A0h]
  __int64 v10; // [rsp+30h] [rbp-98h]
  _QWORD v11[4]; // [rsp+38h] [rbp-90h] BYREF
  __int64 iter; // [rsp+58h] [rbp-70h]
  __int64 v13; // [rsp+60h] [rbp-68h]
  __int64 v14; // [rsp+68h] [rbp-60h]
  __int64 v15; // [rsp+70h] [rbp-58h]
  __int64 v16; // [rsp+78h] [rbp-50h]
  _BYTE v17[8]; // [rsp+80h] [rbp-48h] BYREF
  __int64 v18; // [rsp+88h] [rbp-40h]
  _BYTE v19[8]; // [rsp+90h] [rbp-38h] BYREF
  _BYTE v20[8]; // [rsp+98h] [rbp-30h] BYREF
  _BYTE v21[40]; // [rsp+A0h] [rbp-28h] BYREF

  v10 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
  v11[2] = a1;
  v9 = std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int>(a1, v10);
  std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find_last<int>(
    a1,
    v11,
    v10,
    v9);
  if ( v11[1] )
  {
    v11[3] = a1 + 8;
    iter = std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Make_iter(a1 + 8, v19, v11[1]);
    v7 = 0;
    std::pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,bool>::pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,bool>(
      a2,
      iter,
      &v7);
    return a2;
  }
  else
  {
    std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Check_max_size(a1);
    v13 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
    v14 = std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Getal(a1 + 8);
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>(
      v17,
      v14,
      v13);
    if ( (unsigned __int8)std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Rehash_for_1(a1);
      v4 = Microsoft::WRL::Details::Forward<std::nullptr_t>(v18 + 16);
      qmemcpy(
        v11,
        (const void *)std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find_last<int>(
                        a1,
                        v21,
                        v4,
                        v9),
        0x10u);
    }
    v15 = a1 + 8;
    v5 = std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>::_Release(v17);
    inserted = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Insert_new_node_before(
                 a1,
                 v9,
                 v11[0],
                 v5);
    v16 = std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Make_iter(v15, v20, inserted);
    v8[0] = 1;
    std::pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,bool>::pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,bool>(
      a2,
      v16,
      v8);
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>(v17);
    return a2;
  }
}

```

## disassembly

```asm
0x180016100  mov     [rsp+arg_10], r8
0x180016105  mov     [rsp+arg_8], rdx
0x18001610a  mov     [rsp+arg_0], rcx
0x18001610f  push    rsi
0x180016110  push    rdi
0x180016111  sub     rsp, 0B8h
0x180016118  mov     rcx, [rsp+0C8h+arg_10]
0x180016120  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180016125  mov     [rsp+0C8h+var_98], rax
0x18001612a  mov     rax, [rsp+0C8h+arg_0]
0x180016132  mov     [rsp+0C8h+var_80], rax
0x180016137  mov     rdx, [rsp+0C8h+var_98]
0x18001613c  mov     rcx, [rsp+0C8h+var_80]
0x180016141  call    ??$?RH@?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@QEBA_KAEBH@Z; std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int>(int const &)
0x180016146  mov     [rsp+0C8h+var_A0], rax
0x18001614b  mov     r9, [rsp+0C8h+var_A0]
0x180016150  mov     r8, [rsp+0C8h+var_98]
0x180016155  lea     rdx, [rsp+0C8h+var_90]
0x18001615a  mov     rcx, [rsp+0C8h+arg_0]
0x180016162  call    ??$_Find_last@H@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@1@AEBH_K@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find_last<int>(int const &,unsigned __int64)
0x180016167  nop
0x180016168  cmp     [rsp+0C8h+var_88], 0
0x18001616e  jz      short loc_1800161C7
0x180016170  mov     rax, [rsp+0C8h+arg_0]
0x180016178  add     rax, 8
0x18001617c  mov     [rsp+0C8h+var_78], rax
0x180016181  mov     r8, [rsp+0C8h+var_88]
0x180016186  lea     rdx, [rsp+0C8h+var_38]
0x18001618e  mov     rcx, [rsp+0C8h+var_78]
0x180016193  call    ?_Make_iter@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEBA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@@Z; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Make_iter(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *)
0x180016198  mov     [rsp+0C8h+var_70], rax
0x18001619d  mov     [rsp+0C8h+var_A8], 0
0x1800161a2  lea     r8, [rsp+0C8h+var_A8]
0x1800161a7  mov     rdx, [rsp+0C8h+var_70]
0x1800161ac  mov     rcx, [rsp+0C8h+arg_8]
0x1800161b4  call    ??$?0V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@_N$0A@@?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@_N@std@@QEAA@$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@1@$$QEA_N@Z; std::pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,bool>::pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,bool>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> &&,bool &&)
0x1800161b9  nop
0x1800161ba  mov     rax, [rsp+0C8h+arg_8]
0x1800161c2  jmp     loc_180016301
0x1800161c7  mov     rcx, [rsp+0C8h+arg_0]
0x1800161cf  call    ?_Check_max_size@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBAXXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Check_max_size(void)
0x1800161d4  mov     rcx, [rsp+0C8h+arg_10]
0x1800161dc  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x1800161e1  mov     [rsp+0C8h+var_68], rax
0x1800161e6  mov     rax, [rsp+0C8h+arg_0]
0x1800161ee  add     rax, 8
0x1800161f2  mov     rcx, rax
0x1800161f5  call    ?_Getal@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@AEBAAEBV?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@2@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Getal(void)
0x1800161fa  mov     [rsp+0C8h+var_60], rax
0x1800161ff  mov     r8, [rsp+0C8h+var_68]
0x180016204  mov     rdx, [rsp+0C8h+var_60]
0x180016209  lea     rcx, [rsp+0C8h+var_48]
0x180016211  call    ??$?0U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@1@$$QEAU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>(std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>> &,std::pair<int const,Docking::VirtualInput::TouchInput> &&)
0x180016216  nop
0x180016217  mov     rcx, [rsp+0C8h+arg_0]
0x18001621f  call    ?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA_NXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Check_rehash_required_1(void)
0x180016224  movzx   eax, al
0x180016227  test    eax, eax
0x180016229  jz      short loc_18001627C
0x18001622b  mov     rcx, [rsp+0C8h+arg_0]
0x180016233  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Rehash_for_1(void)
0x180016238  nop
0x180016239  mov     rax, [rsp+0C8h+var_40]
0x180016241  add     rax, 10h
0x180016245  mov     rcx, rax
0x180016248  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18001624d  mov     r9, [rsp+0C8h+var_A0]
0x180016252  mov     r8, rax
0x180016255  lea     rdx, [rsp+0C8h+var_28]
0x18001625d  mov     rcx, [rsp+0C8h+arg_0]
0x180016265  call    ??$_Find_last@H@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@1@AEBH_K@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find_last<int>(int const &,unsigned __int64)
0x18001626a  lea     rcx, [rsp+0C8h+var_90]
0x18001626f  mov     rdi, rcx
0x180016272  mov     rsi, rax
0x180016275  mov     ecx, 10h
0x18001627a  rep movsb
0x18001627c  mov     rax, [rsp+0C8h+arg_0]
0x180016284  add     rax, 8
0x180016288  mov     [rsp+0C8h+var_58], rax
0x18001628d  lea     rcx, [rsp+0C8h+var_48]
0x180016295  call    ?_Release@?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@std@@@std@@QEAAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>::_Release(void)
0x18001629a  mov     r9, rax
0x18001629d  mov     r8, [rsp+0C8h+var_90]
0x1800162a2  mov     rdx, [rsp+0C8h+var_A0]
0x1800162a7  mov     rcx, [rsp+0C8h+arg_0]
0x1800162af  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const)
0x1800162b4  mov     r8, rax
0x1800162b7  lea     rdx, [rsp+0C8h+var_30]
0x1800162bf  mov     rcx, [rsp+0C8h+var_58]
0x1800162c4  call    ?_Make_iter@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEBA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@@Z; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Make_iter(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *)
0x1800162c9  mov     [rsp+0C8h+var_50], rax
0x1800162ce  mov     [rsp+0C8h+var_A7], 1
0x1800162d3  lea     r8, [rsp+0C8h+var_A7]
0x1800162d8  mov     rdx, [rsp+0C8h+var_50]
0x1800162dd  mov     rcx, [rsp+0C8h+arg_8]
0x1800162e5  call    ??$?0V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@_N$0A@@?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@_N@std@@QEAA@$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@1@$$QEA_N@Z; std::pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,bool>::pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,bool>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> &&,bool &&)
0x1800162ea  nop
0x1800162eb  lea     rcx, [rsp+0C8h+var_48]
0x1800162f3  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>(void)
0x1800162f8  nop
0x1800162f9  mov     rax, [rsp+0C8h+arg_8]
0x180016301  add     rsp, 0B8h
0x180016308  pop     rdi
0x180016309  pop     rsi
0x18001630a  retn
```
