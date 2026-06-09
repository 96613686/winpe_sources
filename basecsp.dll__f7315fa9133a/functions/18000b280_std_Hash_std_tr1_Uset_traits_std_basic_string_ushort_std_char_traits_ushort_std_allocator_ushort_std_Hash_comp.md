# std::_Hash<std::tr1::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::insert<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x18000b280`
- end: `0x18000b2f5`
- name: `??$insert@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013fdc`

## callees

- `0x18000b150`
- `0x180018150`
- `0x1800181f0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert<std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rdi
  __int64 v5; // rbx

  v4 = *(_QWORD *)qword_18003C898;
  v5 = std::_List_val<std::wstring>::_Buynode<std::wstring>(
         a1,
         *(_QWORD *)qword_18003C898,
         *(_QWORD *)(*(_QWORD *)qword_18003C898 + 8LL),
         a3);
  std::list<std::wstring>::_Incsize(&qword_18003C898);
  *(_QWORD *)(v4 + 8) = v5;
  **(_QWORD **)(v5 + 8) = v5;
  std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert(
    (__int64)&word_18003C890,
    a2,
    *(_QWORD *)qword_18003C898 + 16LL,
    *(_QWORD ***)qword_18003C898);
  return a2;
}

```

## disassembly

```asm
0x18000b280  mov     [rsp+arg_0], rbx
0x18000b285  mov     [rsp+arg_8], rsi
0x18000b28a  push    rdi
0x18000b28b  sub     rsp, 20h
0x18000b28f  mov     rax, cs:qword_18003C898
0x18000b296  mov     rsi, rdx
0x18000b299  mov     r9, r8
0x18000b29c  mov     rdi, [rax]
0x18000b29f  mov     rdx, rdi
0x18000b2a2  mov     r8, [rdi+8]
0x18000b2a6  call    ??$_Buynode@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU_Node@?$_List_nod@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@PEAU231@0$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_List_val<std::wstring>::_Buynode<std::wstring>(std::_List_nod<std::wstring>::_Node *,std::_List_nod<std::wstring>::_Node *,std::wstring &&)
0x18000b2ab  lea     rcx, qword_18003C898
0x18000b2b2  mov     rbx, rax
0x18000b2b5  call    ?_Incsize@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX_K@Z; std::list<std::wstring>::_Incsize(unsigned __int64)
0x18000b2ba  mov     [rdi+8], rbx
0x18000b2be  mov     rdx, rsi
0x18000b2c1  mov     rcx, [rbx+8]
0x18000b2c5  mov     [rcx], rbx
0x18000b2c8  lea     rcx, word_18003C890
0x18000b2cf  mov     r9, cs:qword_18003C898
0x18000b2d6  mov     r9, [r9]
0x18000b2d9  lea     r8, [r9+10h]
0x18000b2dd  call    ?_Insert@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@_N@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert(std::wstring const &,std::_List_const_iterator<std::_List_val<std::wstring>>)
0x18000b2e2  mov     rbx, [rsp+28h+arg_0]
0x18000b2e7  mov     rax, rsi
0x18000b2ea  mov     rsi, [rsp+28h+arg_8]
0x18000b2ef  add     rsp, 20h
0x18000b2f3  pop     rdi
0x18000b2f4  retn
```
