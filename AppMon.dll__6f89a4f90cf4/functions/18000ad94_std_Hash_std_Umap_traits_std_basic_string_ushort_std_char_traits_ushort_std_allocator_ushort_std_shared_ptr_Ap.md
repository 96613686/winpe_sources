# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Try_emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x18000ad94`
- end: `0x18000aef5`
- name: `??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `353`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000b6a8`
- `0x18000bafc`

## callees

- `0x1800026fc`
- `0x180007f08`
- `0x18000939c`
- `0x180009a68`
- `0x180009d4c`
- `0x18000a078`
- `0x18000ad94`
- `0x18000b248`
- `0x18000d96c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000adfa`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000adfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Try_emplace<std::wstring,>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 v6; // r15
  char *v7; // r14
  __int64 v8; // rdx
  float v9; // xmm0_4
  __int64 v10; // rcx
  float v11; // xmm1_4
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v15; // [rsp+30h] [rbp-28h] BYREF
  char *v16; // [rsp+38h] [rbp-20h]
  __int128 v17; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int8 *v18; // [rsp+90h] [rbp+38h] BYREF

  v6 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a3);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
    a1,
    &v17,
    a3,
    v6);
  if ( *((_QWORD *)&v17 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v17 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 16) == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v15 = a1 + 8;
    v7 = (char *)operator new(0x40u);
    v16 = v7;
    v18 = a3;
    ____0V__tuple___QEAV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std__V__tuple___V_1__0A___Z_S___pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__shared_ptr_VAppPrinterEndPointBase_AppMon___2__std__AEAA_AEAV__tuple___QEAV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
      v7 + 16,
      &v18);
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
      std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Forced_rehash(
        a1,
        v13);
      v17 = *(_OWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                         a1,
                         &v17,
                         v7 + 16,
                         v6);
    }
    v16 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      v17,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(&v15);
  }
  return a2;
}

```

## disassembly

```asm
0x18000ad94  push    rbp
0x18000ad96  push    rbx
0x18000ad97  push    rsi
0x18000ad98  push    rdi
0x18000ad99  push    r14
0x18000ad9b  push    r15
0x18000ad9d  mov     rbp, rsp
0x18000ada0  sub     rsp, 58h
0x18000ada4  mov     rsi, r8
0x18000ada7  mov     rbx, rdx
0x18000adaa  mov     rdi, rcx
0x18000adad  mov     rcx, r8; unsigned __int8 *
0x18000adb0  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000adb5  mov     r15, rax
0x18000adb8  mov     r9, rax
0x18000adbb  mov     r8, rsi
0x18000adbe  lea     rdx, [rbp+var_18]
0x18000adc2  mov     rcx, rdi
0x18000adc5  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000adca  mov     rcx, qword ptr [rbp+var_18+8]
0x18000adce  test    rcx, rcx
0x18000add1  jz      short loc_18000ADDF
0x18000add3  mov     [rbx], rcx
0x18000add6  mov     byte ptr [rbx+8], 0
0x18000adda  jmp     loc_18000AEE5
0x18000addf  lea     rax, [rdi+8]
0x18000ade3  mov     rcx, 3FFFFFFFFFFFFFFh
0x18000aded  cmp     [rax+8], rcx
0x18000adf1  jnz     short loc_18000AE01
0x18000adf3  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000adfa  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000ae01  mov     [rbp+var_28], rax
0x18000ae05  mov     [rbp+var_20], 0
0x18000ae0d  mov     ecx, 40h ; '@'; Size
0x18000ae12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ae17  mov     r14, rax
0x18000ae1a  mov     [rbp+var_20], rax
0x18000ae1e  mov     [rbp+arg_0], rsi
0x18000ae22  lea     rdx, [rbp+arg_0]
0x18000ae26  lea     rcx, [rax+10h]
0x18000ae2a  call    ??$?0V?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$tuple@$$V@1@$0A@$$Z$S@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@AEAA@AEAV?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEAV?$tuple@$$V@1@U?$integer_sequence@_K$0A@@1@U?$integer_sequence@_K$S@1@@Z
0x18000ae2f  nop
0x18000ae30  mov     rdx, [rdi+10h]
0x18000ae34  add     rdx, 1
0x18000ae38  xorps   xmm0, xmm0
0x18000ae3b  js      short loc_18000AE44
0x18000ae3d  cvtsi2ss xmm0, rdx
0x18000ae42  jmp     short loc_18000AE5C
0x18000ae44  mov     rcx, rdx
0x18000ae47  shr     rcx, 1
0x18000ae4a  mov     rax, rdx
0x18000ae4d  and     eax, 1
0x18000ae50  or      rcx, rax
0x18000ae53  cvtsi2ss xmm0, rcx
0x18000ae58  addss   xmm0, xmm0
0x18000ae5c  mov     rcx, [rdi+38h]
0x18000ae60  xorps   xmm1, xmm1
0x18000ae63  test    rcx, rcx
0x18000ae66  js      short loc_18000AE6F
0x18000ae68  cvtsi2ss xmm1, rcx
0x18000ae6d  jmp     short loc_18000AE84
0x18000ae6f  mov     rax, rcx
0x18000ae72  shr     rax, 1
0x18000ae75  and     ecx, 1
0x18000ae78  or      rax, rcx
0x18000ae7b  cvtsi2ss xmm1, rax
0x18000ae80  addss   xmm1, xmm1
0x18000ae84  divss   xmm0, xmm1
0x18000ae88  comiss  xmm0, dword ptr [rdi]
0x18000ae8b  jbe     short loc_18000AEBB
0x18000ae8d  mov     rcx, rdi
0x18000ae90  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000ae95  mov     rdx, rax
0x18000ae98  mov     rcx, rdi
0x18000ae9b  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Forced_rehash(unsigned __int64)
0x18000aea0  mov     r9, r15
0x18000aea3  lea     r8, [r14+10h]
0x18000aea7  lea     rdx, [rbp+var_18]
0x18000aeab  mov     rcx, rdi
0x18000aeae  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000aeb3  movups  xmm0, xmmword ptr [rax]
0x18000aeb6  movdqu  [rbp+var_18], xmm0
0x18000aebb  mov     [rbp+var_20], 0
0x18000aec3  mov     r9, r14
0x18000aec6  mov     r8, qword ptr [rbp+var_18]
0x18000aeca  mov     rdx, r15
0x18000aecd  mov     rcx, rdi
0x18000aed0  call    ?_Insert_new_node_before@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::wstring,void *> * const,std::_List_node<std::wstring,void *> * const)
0x18000aed5  mov     [rbx], rax
0x18000aed8  mov     byte ptr [rbx+8], 1
0x18000aedc  lea     rcx, [rbp+var_28]
0x18000aee0  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(void)
0x18000aee5  mov     rax, rbx
0x18000aee8  add     rsp, 58h
0x18000aeec  pop     r15
0x18000aeee  pop     r14
0x18000aef0  pop     rdi
0x18000aef1  pop     rsi
0x18000aef2  pop     rbx
0x18000aef3  pop     rbp
0x18000aef4  retn
```
