# std::_Hash<std::_Umap_traits<ushort,ushort,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,ushort>>,0>>::emplace<std::pair<ushort const,ushort> const &>(std::pair<ushort const,ushort> const &)

- ea: `0x18003b334`
- end: `0x18003b491`
- name: `??$emplace@AEBU?$pair@$$CBGG@std@@@?$_Hash@V?$_Umap_traits@GGV?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGG@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBGG@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBGG@1@@Z`
- size: `349`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008e00`

## callees

- `0x18000b7fc`
- `0x18000e3ac`
- `0x180010f94`
- `0x18003b24c`
- `0x18003b334`
- `0x18003b598`
- `0x18003b6dc`
- `0x18003b784`
- `0x18003b918`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003b390`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003b390`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned short,unsigned short,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,unsigned short>>,0>>::emplace<std::pair<unsigned short const,unsigned short> const &>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 v5; // rsi
  __int64 v6; // rcx
  size_t size_of; // rax
  _QWORD *v8; // rbp
  unsigned __int64 v9; // rdx
  float v10; // xmm0_4
  __int64 v11; // rcx
  float v12; // xmm1_4
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  _QWORD v17[2]; // [rsp+20h] [rbp-48h] BYREF
  _OWORD v18[3]; // [rsp+30h] [rbp-38h] BYREF

  v5 = std::_Conditionally_enabled_hash<unsigned short,1>::operator()(a3);
  std::_Hash<std::_Umap_traits<unsigned short,unsigned short,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,unsigned short>>,0>>::_Find_last<unsigned short>(
    v6,
    v18,
    a3,
    v5);
  if ( *((_QWORD *)&v18[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v18[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( qword_18007BEC0 == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v17[0] = &qword_18007BEB8;
    size_of = std::_Get_size_of_n<24>(1);
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v17[1] = v8;
    *((_DWORD *)v8 + 4) = *(_DWORD *)a3;
    v9 = qword_18007BEC0 + 1;
    if ( qword_18007BEC0 + 1 < 0 )
      v10 = (float)(int)(v9 & 1 | (v9 >> 1)) + (float)(int)(v9 & 1 | (v9 >> 1));
    else
      v10 = (float)(int)v9;
    v11 = qword_18007BEE8;
    if ( qword_18007BEE8 < 0 )
    {
      v11 = qword_18007BEE8 & 1;
      v12 = (float)(int)(v11 | ((unsigned __int64)qword_18007BEE8 >> 1))
          + (float)(int)(v11 | ((unsigned __int64)qword_18007BEE8 >> 1));
    }
    else
    {
      v12 = (float)(int)qword_18007BEE8;
    }
    if ( (float)(v10 / v12) > *(float *)&dword_18007BEB0 )
    {
      v13 = std::_Hash<std::_Umap_traits<unsigned short,unsigned short,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,unsigned short>>,0>>::_Desired_grow_bucket_count(
              v11,
              v9);
      std::_Hash<std::_Umap_traits<unsigned short,unsigned short,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,unsigned short>>,0>>::_Forced_rehash(
        v14,
        v13);
      v18[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<unsigned short,unsigned short,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,unsigned short>>,0>>::_Find_last<unsigned short>(
                            v15,
                            v18,
                            (_WORD *)v8 + 8,
                            v5);
    }
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<unsigned short,unsigned short,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,unsigned short>>,0>>::_Insert_new_node_before(
                      v11,
                      v5,
                      *(_QWORD *)&v18[0],
                      v8,
                      v17[0],
                      0);
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned int,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned int,void *>>>(v17);
  }
  return a2;
}

```

## disassembly

```asm
0x18003b334  push    rbx
0x18003b336  push    rbp
0x18003b337  push    rsi
0x18003b338  push    rdi
0x18003b339  push    r14
0x18003b33b  sub     rsp, 40h
0x18003b33f  mov     rdi, r8
0x18003b342  mov     rbx, rdx
0x18003b345  mov     rcx, r8; unsigned __int8 *
0x18003b348  call    ??R?$_Conditionally_enabled_hash@G$00@std@@SA_KAEBG@Z; std::_Conditionally_enabled_hash<ushort,1>::operator()(ushort const &)
0x18003b34d  mov     rsi, rax
0x18003b350  mov     r9, rax
0x18003b353  mov     r8, rdi
0x18003b356  lea     rdx, [rsp+68h+var_38]
0x18003b35b  call    ??$_Find_last@G@?$_Hash@V?$_Umap_traits@GGV?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGG@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBGG@std@@PEAX@std@@@1@AEBG_K@Z; std::_Hash<std::_Umap_traits<ushort,ushort,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,ushort>>,0>>::_Find_last<ushort>(ushort const &,unsigned __int64)
0x18003b360  mov     rdx, qword ptr [rsp+68h+var_38+8]
0x18003b365  test    rdx, rdx
0x18003b368  jz      short loc_18003B376
0x18003b36a  mov     [rbx], rdx
0x18003b36d  mov     byte ptr [rbx+8], 0
0x18003b371  jmp     loc_18003B483
0x18003b376  mov     rax, 0AAAAAAAAAAAAAAAh
0x18003b380  cmp     cs:qword_18007BEC0, rax
0x18003b387  jnz     short loc_18003B397
0x18003b389  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18003b390  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18003b397  lea     rax, qword_18007BEB8
0x18003b39e  mov     [rsp+68h+var_48], rax
0x18003b3a3  mov     [rsp+68h+var_40], 0
0x18003b3ac  mov     ecx, 1
0x18003b3b1  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x18003b3b6  mov     rcx, rax
0x18003b3b9  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003b3be  mov     rbp, rax
0x18003b3c1  mov     [rsp+68h+var_40], rax
0x18003b3c6  mov     ecx, [rdi]
0x18003b3c8  mov     [rax+10h], ecx
0x18003b3cb  mov     rdx, cs:qword_18007BEC0
0x18003b3d2  add     rdx, 1
0x18003b3d6  xorps   xmm0, xmm0
0x18003b3d9  js      short loc_18003B3E2
0x18003b3db  cvtsi2ss xmm0, rdx
0x18003b3e0  jmp     short loc_18003B3FA
0x18003b3e2  mov     rcx, rdx
0x18003b3e5  shr     rcx, 1
0x18003b3e8  mov     rax, rdx
0x18003b3eb  and     eax, 1
0x18003b3ee  or      rcx, rax
0x18003b3f1  cvtsi2ss xmm0, rcx
0x18003b3f6  addss   xmm0, xmm0
0x18003b3fa  mov     rcx, cs:qword_18007BEE8
0x18003b401  xorps   xmm1, xmm1
0x18003b404  test    rcx, rcx
0x18003b407  js      short loc_18003B410
0x18003b409  cvtsi2ss xmm1, rcx
0x18003b40e  jmp     short loc_18003B425
0x18003b410  mov     rax, rcx
0x18003b413  shr     rax, 1
0x18003b416  and     ecx, 1
0x18003b419  or      rax, rcx
0x18003b41c  cvtsi2ss xmm1, rax
0x18003b421  addss   xmm1, xmm1
0x18003b425  divss   xmm0, xmm1
0x18003b429  comiss  xmm0, cs:dword_18007BEB0
0x18003b430  jbe     short loc_18003B459
0x18003b432  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@GGV?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGG@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<ushort,ushort,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,ushort>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18003b437  mov     rdx, rax
0x18003b43a  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@GGV?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGG@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<ushort,ushort,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,ushort>>,0>>::_Forced_rehash(unsigned __int64)
0x18003b43f  mov     r9, rsi
0x18003b442  lea     r8, [rbp+10h]
0x18003b446  lea     rdx, [rsp+68h+var_38]
0x18003b44b  call    ??$_Find_last@G@?$_Hash@V?$_Umap_traits@GGV?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGG@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBGG@std@@PEAX@std@@@1@AEBG_K@Z; std::_Hash<std::_Umap_traits<ushort,ushort,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,ushort>>,0>>::_Find_last<ushort>(ushort const &,unsigned __int64)
0x18003b450  movups  xmm0, xmmword ptr [rax]
0x18003b453  movdqu  [rsp+68h+var_38], xmm0
0x18003b459  mov     [rsp+68h+var_40], 0
0x18003b462  mov     r9, rbp
0x18003b465  mov     r8, qword ptr [rsp+68h+var_38]
0x18003b46a  mov     rdx, rsi
0x18003b46d  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@GGV?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGG@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBGG@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<ushort,ushort,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,ushort>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<ushort const,ushort>,void *> * const,std::_List_node<std::pair<ushort const,ushort>,void *> * const)
0x18003b472  mov     [rbx], rax
0x18003b475  mov     byte ptr [rbx+8], 1
0x18003b479  lea     rcx, [rsp+68h+var_48]
0x18003b47e  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@IPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<uint,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<uint,void *>>>(void)
0x18003b483  mov     rax, rbx
0x18003b486  add     rsp, 40h
0x18003b48a  pop     r14
0x18003b48c  pop     rdi
0x18003b48d  pop     rsi
0x18003b48e  pop     rbp
0x18003b48f  pop     rbx
0x18003b490  retn
```
