# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Erase<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000a9a8`
- end: `0x18000aa4f`
- name: `??$_Erase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@AEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ca20`

## callees

- `0x180007f08`
- `0x18000939c`
- `0x18000a9a8`
- `0x18000ab30`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Erase<std::wstring>(
        __int64 a1,
        unsigned __int8 *a2)
{
  __int64 v2; // rbx
  __int64 v3; // r11
  _QWORD *v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a2);
  v4 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                   &AppMon::PortManager::m_appPrinterEndPointTable,
                   v10,
                   v3,
                   v2)[1];
  if ( !v4 )
    return 0;
  v5 = qword_180016538;
  v6 = 2 * (v2 & qword_180016550);
  if ( *(_QWORD **)(qword_180016538 + 16 * (v2 & qword_180016550) + 8) == v4 )
  {
    if ( *(_QWORD **)(qword_180016538 + 16 * (v2 & qword_180016550)) == v4 )
    {
      v7 = qword_180016528;
      *(_QWORD *)(qword_180016538 + 16 * (v2 & qword_180016550)) = qword_180016528;
    }
    else
    {
      v7 = v4[1];
    }
    *(_QWORD *)(v5 + 8 * v6 + 8) = v7;
  }
  else if ( *(_QWORD **)(qword_180016538 + 16 * (v2 & qword_180016550)) == v4 )
  {
    *(_QWORD *)(qword_180016538 + 16 * (v2 & qword_180016550)) = *v4;
  }
  v8 = *v4;
  --qword_180016530;
  *(_QWORD *)v4[1] = v8;
  *(_QWORD *)(v8 + 8) = v4[1];
  std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>();
  return 1;
}

```

## disassembly

```asm
0x18000a9a8  push    rbx
0x18000a9aa  sub     rsp, 30h
0x18000a9ae  mov     rcx, rdx; unsigned __int8 *
0x18000a9b1  mov     r11, rdx
0x18000a9b4  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000a9b9  mov     r9, rax
0x18000a9bc  lea     rdx, [rsp+38h+var_18]
0x18000a9c1  mov     r8, r11
0x18000a9c4  lea     rcx, ?m_appPrinterEndPointTable@PortManager@AppMon@@0V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@@std@@A; std::unordered_map<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>> AppMon::PortManager::m_appPrinterEndPointTable
0x18000a9cb  mov     rbx, rax
0x18000a9ce  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000a9d3  mov     rdx, [rax+8]
0x18000a9d7  test    rdx, rdx
0x18000a9da  jz      short loc_18000AA47
0x18000a9dc  mov     rcx, cs:qword_180016550
0x18000a9e3  mov     r8, cs:qword_180016538
0x18000a9ea  and     rcx, rbx
0x18000a9ed  add     rcx, rcx
0x18000a9f0  cmp     [r8+rcx*8+8], rdx
0x18000a9f5  jnz     short loc_18000AA15
0x18000a9f7  cmp     [r8+rcx*8], rdx
0x18000a9fb  jnz     short loc_18000AA0A
0x18000a9fd  mov     rax, cs:qword_180016528
0x18000aa04  mov     [r8+rcx*8], rax
0x18000aa08  jmp     short loc_18000AA0E
0x18000aa0a  mov     rax, [rdx+8]
0x18000aa0e  mov     [r8+rcx*8+8], rax
0x18000aa13  jmp     short loc_18000AA22
0x18000aa15  cmp     [r8+rcx*8], rdx
0x18000aa19  jnz     short loc_18000AA22
0x18000aa1b  mov     rax, [rdx]
0x18000aa1e  mov     [r8+rcx*8], rax
0x18000aa22  mov     r8, [rdx]
0x18000aa25  dec     cs:qword_180016530
0x18000aa2c  mov     rcx, [rdx+8]
0x18000aa30  mov     [rcx], r8
0x18000aa33  mov     rcx, [rdx+8]
0x18000aa37  mov     [r8+8], rcx
0x18000aa3b  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>> &,std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *> *)
0x18000aa40  mov     eax, 1
0x18000aa45  jmp     short loc_18000AA49
0x18000aa47  xor     eax, eax
0x18000aa49  add     rsp, 30h
0x18000aa4d  pop     rbx
0x18000aa4e  retn
```
