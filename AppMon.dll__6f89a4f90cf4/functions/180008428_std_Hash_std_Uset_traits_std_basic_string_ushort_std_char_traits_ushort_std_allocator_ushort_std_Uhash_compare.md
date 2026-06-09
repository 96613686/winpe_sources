# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180008428`
- end: `0x18000858b`
- name: `??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800094a0`

## callees

- `0x1800026fc`
- `0x180007f08`
- `0x180008428`
- `0x180008604`
- `0x1800086d8`
- `0x18000939c`
- `0x180009a68`
- `0x180009b90`
- `0x180009d4c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000848d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000848d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 v6; // r14
  char *v7; // rbp
  __int64 v8; // rdx
  float v9; // xmm0_4
  __int64 v10; // rcx
  float v11; // xmm1_4
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v15; // [rsp+20h] [rbp-58h] BYREF
  char *v16; // [rsp+28h] [rbp-50h]
  _OWORD v17[4]; // [rsp+30h] [rbp-48h] BYREF

  v6 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a3);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
    a1,
    v17,
    a3,
    v6);
  if ( *((_QWORD *)&v17[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v17[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 16) == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v15 = a1 + 8;
    v7 = (char *)operator new(0x30u);
    v16 = v7;
    std::wstring::wstring(v7 + 16, a3);
    v8 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v8 < 0 )
      v9 = (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1))
         + (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1));
    else
      v9 = (float)(int)v8;
    v10 = *(_QWORD *)(a1 + 56);
    if ( v10 < 0 )
    {
      v12 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v10 >> 1);
      v11 = (float)(int)v12 + (float)(int)v12;
    }
    else
    {
      v11 = (float)(int)v10;
    }
    if ( (float)(v9 / v11) > *(float *)a1 )
    {
      v13 = std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Desired_grow_bucket_count(
              a1,
              v8);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        a1,
        v13);
      v17[0] = *(_OWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                            a1,
                            v17,
                            v7 + 16,
                            v6);
    }
    v16 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      *(_QWORD *)&v17[0],
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(&v15);
  }
  return a2;
}

```

## disassembly

```asm
0x180008428  push    rbx
0x18000842a  push    rbp
0x18000842b  push    rsi
0x18000842c  push    rdi
0x18000842d  push    r14
0x18000842f  push    r15
0x180008431  sub     rsp, 48h
0x180008435  mov     rsi, r8
0x180008438  mov     rbx, rdx
0x18000843b  mov     rdi, rcx
0x18000843e  mov     rcx, r8; unsigned __int8 *
0x180008441  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180008446  mov     r14, rax
0x180008449  mov     r9, rax
0x18000844c  mov     r8, rsi
0x18000844f  lea     rdx, [rsp+78h+var_48]
0x180008454  mov     rcx, rdi
0x180008457  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000845c  mov     rcx, qword ptr [rsp+78h+var_48+8]
0x180008461  test    rcx, rcx
0x180008464  jz      short loc_180008472
0x180008466  mov     [rbx], rcx
0x180008469  mov     byte ptr [rbx+8], 0
0x18000846d  jmp     loc_18000857B
0x180008472  lea     rax, [rdi+8]
0x180008476  mov     rcx, 555555555555555h
0x180008480  cmp     [rax+8], rcx
0x180008484  jnz     short loc_180008494
0x180008486  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000848d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180008494  mov     [rsp+78h+var_58], rax
0x180008499  mov     [rsp+78h+var_50], 0
0x1800084a2  mov     ecx, 30h ; '0'; Size
0x1800084a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800084ac  mov     rbp, rax
0x1800084af  mov     [rsp+78h+var_50], rax
0x1800084b4  mov     rdx, rsi
0x1800084b7  lea     rcx, [rax+10h]
0x1800084bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800084c0  nop
0x1800084c1  mov     rdx, [rdi+10h]
0x1800084c5  add     rdx, 1
0x1800084c9  xorps   xmm0, xmm0
0x1800084cc  js      short loc_1800084D5
0x1800084ce  cvtsi2ss xmm0, rdx
0x1800084d3  jmp     short loc_1800084ED
0x1800084d5  mov     rcx, rdx
0x1800084d8  shr     rcx, 1
0x1800084db  mov     rax, rdx
0x1800084de  and     eax, 1
0x1800084e1  or      rcx, rax
0x1800084e4  cvtsi2ss xmm0, rcx
0x1800084e9  addss   xmm0, xmm0
0x1800084ed  mov     rcx, [rdi+38h]
0x1800084f1  xorps   xmm1, xmm1
0x1800084f4  test    rcx, rcx
0x1800084f7  js      short loc_180008500
0x1800084f9  cvtsi2ss xmm1, rcx
0x1800084fe  jmp     short loc_180008515
0x180008500  mov     rax, rcx
0x180008503  shr     rax, 1
0x180008506  and     ecx, 1
0x180008509  or      rax, rcx
0x18000850c  cvtsi2ss xmm1, rax
0x180008511  addss   xmm1, xmm1
0x180008515  divss   xmm0, xmm1
0x180008519  comiss  xmm0, dword ptr [rdi]
0x18000851c  jbe     short loc_18000854E
0x18000851e  mov     rcx, rdi
0x180008521  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180008526  mov     rdx, rax
0x180008529  mov     rcx, rdi
0x18000852c  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(unsigned __int64)
0x180008531  mov     r9, r14
0x180008534  lea     r8, [rbp+10h]
0x180008538  lea     rdx, [rsp+78h+var_48]
0x18000853d  mov     rcx, rdi
0x180008540  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180008545  movups  xmm0, xmmword ptr [rax]
0x180008548  movdqu  [rsp+78h+var_48], xmm0
0x18000854e  mov     [rsp+78h+var_50], 0
0x180008557  mov     r9, rbp
0x18000855a  mov     r8, qword ptr [rsp+78h+var_48]
0x18000855f  mov     rdx, r14
0x180008562  mov     rcx, rdi
0x180008565  call    ?_Insert_new_node_before@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::wstring,void *> * const,std::_List_node<std::wstring,void *> * const)
0x18000856a  mov     [rbx], rax
0x18000856d  mov     byte ptr [rbx+8], 1
0x180008571  lea     rcx, [rsp+78h+var_58]
0x180008576  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(void)
0x18000857b  mov     rax, rbx
0x18000857e  add     rsp, 48h
0x180008582  pop     r15
0x180008584  pop     r14
0x180008586  pop     rdi
0x180008587  pop     rsi
0x180008588  pop     rbp
0x180008589  pop     rbx
0x18000858a  retn
```
