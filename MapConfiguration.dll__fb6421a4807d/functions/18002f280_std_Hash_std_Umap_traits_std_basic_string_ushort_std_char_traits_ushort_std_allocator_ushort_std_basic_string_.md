# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::emplace<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &&)

- ea: `0x18002f280`
- end: `0x18002f3df`
- name: `??$emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z`
- size: `351`
- prototype: `__int64 __fastcall(float *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002f9d4`

## callees

- `0x18000b7fc`
- `0x1800148fc`
- `0x18001b42c`
- `0x180023f24`
- `0x18002ee1c`
- `0x18002f14c`
- `0x18002f280`
- `0x18002fd24`
- `0x180030ed0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002f2e3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002f2e3`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring,std::wstring>>(
        float *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r14
  _QWORD *v7; // rbp
  __int64 v8; // rcx
  __int64 v9; // rdx
  float v10; // xmm0_4
  __int64 v11; // rcx
  float v12; // xmm1_4
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v16; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v17; // [rsp+28h] [rbp-40h]
  _OWORD v18[3]; // [rsp+30h] [rbp-38h] BYREF

  v6 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a3);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
    a1,
    v18,
    a3,
    v6);
  if ( *((_QWORD *)&v18[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v18[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *((_QWORD *)a1 + 2) == 0x333333333333333LL )
      std::_Xlength_error("unordered_map/set too long");
    v16 = a1 + 2;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x50u);
    v17 = v7;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::construct<std::pair<std::wstring const,std::wstring>,std::pair<std::wstring,std::wstring>>(
      v8,
      v7 + 2,
      a3);
    v9 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v9 < 0 )
      v10 = (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1))
          + (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1));
    else
      v10 = (float)(int)v9;
    v11 = *((_QWORD *)a1 + 7);
    if ( v11 < 0 )
    {
      v13 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v11 >> 1);
      v12 = (float)(int)v13 + (float)(int)v13;
    }
    else
    {
      v12 = (float)(int)v11;
    }
    if ( (float)(v10 / v12) > *a1 )
    {
      v14 = std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<Pal::UntypedAsyncOperation>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<Pal::UntypedAsyncOperation>>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
        a1,
        v14);
      v18[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
                            a1,
                            v18,
                            (__int64)(v7 + 2),
                            v6);
    }
    v17 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      *(_QWORD *)&v18[0],
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(&v16);
  }
  return a2;
}

```

## disassembly

```asm
0x18002f280  push    rbx
0x18002f282  push    rbp
0x18002f283  push    rsi
0x18002f284  push    rdi
0x18002f285  push    r14
0x18002f287  sub     rsp, 40h
0x18002f28b  mov     rsi, r8
0x18002f28e  mov     rbx, rdx
0x18002f291  mov     rdi, rcx
0x18002f294  mov     rcx, r8
0x18002f297  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18002f29c  mov     r14, rax
0x18002f29f  mov     r9, rax
0x18002f2a2  mov     r8, rsi
0x18002f2a5  lea     rdx, [rsp+68h+var_38]
0x18002f2aa  mov     rcx, rdi
0x18002f2ad  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18002f2b2  mov     rcx, qword ptr [rsp+68h+var_38+8]
0x18002f2b7  test    rcx, rcx
0x18002f2ba  jz      short loc_18002F2C8
0x18002f2bc  mov     [rbx], rcx
0x18002f2bf  mov     byte ptr [rbx+8], 0
0x18002f2c3  jmp     loc_18002F3D1
0x18002f2c8  lea     rax, [rdi+8]
0x18002f2cc  mov     rcx, 333333333333333h
0x18002f2d6  cmp     [rax+8], rcx
0x18002f2da  jnz     short loc_18002F2EA
0x18002f2dc  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18002f2e3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002f2ea  mov     [rsp+68h+var_48], rax
0x18002f2ef  mov     [rsp+68h+var_40], 0
0x18002f2f8  mov     ecx, 50h ; 'P'
0x18002f2fd  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002f302  mov     rbp, rax
0x18002f305  mov     [rsp+68h+var_40], rax
0x18002f30a  lea     rdx, [rax+10h]
0x18002f30e  mov     r8, rsi
0x18002f311  call    ??$construct@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::construct<std::pair<std::wstring const,std::wstring>,std::pair<std::wstring,std::wstring>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::pair<std::wstring const,std::wstring> * const,std::pair<std::wstring,std::wstring> &&)
0x18002f316  nop
0x18002f317  mov     rdx, [rdi+10h]
0x18002f31b  add     rdx, 1
0x18002f31f  xorps   xmm0, xmm0
0x18002f322  js      short loc_18002F32B
0x18002f324  cvtsi2ss xmm0, rdx
0x18002f329  jmp     short loc_18002F343
0x18002f32b  mov     rcx, rdx
0x18002f32e  shr     rcx, 1
0x18002f331  mov     rax, rdx
0x18002f334  and     eax, 1
0x18002f337  or      rcx, rax
0x18002f33a  cvtsi2ss xmm0, rcx
0x18002f33f  addss   xmm0, xmm0
0x18002f343  mov     rcx, [rdi+38h]
0x18002f347  xorps   xmm1, xmm1
0x18002f34a  test    rcx, rcx
0x18002f34d  js      short loc_18002F356
0x18002f34f  cvtsi2ss xmm1, rcx
0x18002f354  jmp     short loc_18002F36B
0x18002f356  mov     rax, rcx
0x18002f359  shr     rax, 1
0x18002f35c  and     ecx, 1
0x18002f35f  or      rax, rcx
0x18002f362  cvtsi2ss xmm1, rax
0x18002f367  addss   xmm1, xmm1
0x18002f36b  divss   xmm0, xmm1
0x18002f36f  comiss  xmm0, dword ptr [rdi]
0x18002f372  jbe     short loc_18002F3A4
0x18002f374  mov     rcx, rdi
0x18002f377  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<Pal::UntypedAsyncOperation>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::UntypedAsyncOperation>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18002f37c  mov     rdx, rax
0x18002f37f  mov     rcx, rdi
0x18002f382  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(unsigned __int64)
0x18002f387  lea     r8, [rbp+10h]
0x18002f38b  mov     r9, r14
0x18002f38e  lea     rdx, [rsp+68h+var_38]
0x18002f393  mov     rcx, rdi
0x18002f396  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18002f39b  movups  xmm0, xmmword ptr [rax]
0x18002f39e  movdqu  [rsp+68h+var_38], xmm0
0x18002f3a4  mov     [rsp+68h+var_40], 0
0x18002f3ad  mov     r9, rbp
0x18002f3b0  mov     r8, qword ptr [rsp+68h+var_38]
0x18002f3b5  mov     rdx, r14
0x18002f3b8  mov     rcx, rdi
0x18002f3bb  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x18002f3c0  mov     [rbx], rax
0x18002f3c3  mov     byte ptr [rbx+8], 1
0x18002f3c7  lea     rcx, [rsp+68h+var_48]
0x18002f3cc  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(void)
0x18002f3d1  mov     rax, rbx
0x18002f3d4  add     rsp, 40h
0x18002f3d8  pop     r14
0x18002f3da  pop     rdi
0x18002f3db  pop     rsi
0x18002f3dc  pop     rbp
0x18002f3dd  pop     rbx
0x18002f3de  retn
```
