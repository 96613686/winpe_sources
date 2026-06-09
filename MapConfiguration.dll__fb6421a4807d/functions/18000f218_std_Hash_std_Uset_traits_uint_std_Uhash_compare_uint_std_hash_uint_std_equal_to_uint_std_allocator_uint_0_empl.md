# std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::emplace<uint const &>(uint const &)

- ea: `0x18000f218`
- end: `0x18000f375`
- name: `??$emplace@AEBI@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@@std@@_N@1@AEBI@Z`
- size: `349`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180001c20`

## callees

- `0x18000b7fc`
- `0x18000e1b8`
- `0x18000e3ac`
- `0x18000f218`
- `0x180010f94`
- `0x180012424`
- `0x180013f1c`
- `0x1800145ac`
- `0x180014954`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f274`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f274`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::emplace<unsigned int const &>(
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
  __int64 *v17; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v18; // [rsp+28h] [rbp-40h]
  _OWORD v19[3]; // [rsp+30h] [rbp-38h] BYREF

  v5 = std::_Conditionally_enabled_hash<unsigned int,1>::operator()(a3);
  std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Find_last<unsigned int>(
    v6,
    v19,
    a3,
    v5);
  if ( *((_QWORD *)&v19[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v19[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( qword_18007BD70 == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v17 = &qword_18007BD68;
    size_of = std::_Get_size_of_n<24>(1);
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v18 = v8;
    *((_DWORD *)v8 + 4) = *(_DWORD *)a3;
    v9 = qword_18007BD70 + 1;
    if ( qword_18007BD70 + 1 < 0 )
      v10 = (float)(int)(v9 & 1 | (v9 >> 1)) + (float)(int)(v9 & 1 | (v9 >> 1));
    else
      v10 = (float)(int)v9;
    v11 = qword_18007BD98;
    if ( qword_18007BD98 < 0 )
    {
      v11 = qword_18007BD98 & 1;
      v12 = (float)(int)(v11 | ((unsigned __int64)qword_18007BD98 >> 1))
          + (float)(int)(v11 | ((unsigned __int64)qword_18007BD98 >> 1));
    }
    else
    {
      v12 = (float)(int)qword_18007BD98;
    }
    if ( (float)(v10 / v12) > *(float *)&dword_18007BD60 )
    {
      v13 = std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Desired_grow_bucket_count();
      std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Forced_rehash(
        v14,
        v13);
      v19[0] = *(_OWORD *)std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Find_last<unsigned int>(
                            v15,
                            v19,
                            (_DWORD *)v8 + 4,
                            v5);
    }
    v18 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Insert_new_node_before(
                      v11,
                      v5,
                      *(_QWORD *)&v19[0],
                      v8);
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned int,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned int,void *>>>(&v17);
  }
  return a2;
}

```

## disassembly

```asm
0x18000f218  push    rbx
0x18000f21a  push    rbp
0x18000f21b  push    rsi
0x18000f21c  push    rdi
0x18000f21d  push    r14
0x18000f21f  sub     rsp, 40h
0x18000f223  mov     rdi, r8
0x18000f226  mov     rbx, rdx
0x18000f229  mov     rcx, r8; unsigned __int8 *
0x18000f22c  call    ??R?$_Conditionally_enabled_hash@I$00@std@@SA_KAEBI@Z; std::_Conditionally_enabled_hash<uint,1>::operator()(uint const &)
0x18000f231  mov     rsi, rax
0x18000f234  mov     r9, rax
0x18000f237  mov     r8, rdi
0x18000f23a  lea     rdx, [rsp+68h+var_38]
0x18000f23f  call    ??$_Find_last@I@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@IPEAX@std@@@1@AEBI_K@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::_Find_last<uint>(uint const &,unsigned __int64)
0x18000f244  mov     rdx, qword ptr [rsp+68h+var_38+8]
0x18000f249  test    rdx, rdx
0x18000f24c  jz      short loc_18000F25A
0x18000f24e  mov     [rbx], rdx
0x18000f251  mov     byte ptr [rbx+8], 0
0x18000f255  jmp     loc_18000F367
0x18000f25a  mov     rax, 0AAAAAAAAAAAAAAAh
0x18000f264  cmp     cs:qword_18007BD70, rax
0x18000f26b  jnz     short loc_18000F27B
0x18000f26d  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000f274  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f27b  lea     rax, qword_18007BD68
0x18000f282  mov     [rsp+68h+var_48], rax
0x18000f287  mov     [rsp+68h+var_40], 0
0x18000f290  mov     ecx, 1
0x18000f295  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x18000f29a  mov     rcx, rax
0x18000f29d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000f2a2  mov     rbp, rax
0x18000f2a5  mov     [rsp+68h+var_40], rax
0x18000f2aa  mov     ecx, [rdi]
0x18000f2ac  mov     [rax+10h], ecx
0x18000f2af  mov     rdx, cs:qword_18007BD70
0x18000f2b6  add     rdx, 1
0x18000f2ba  xorps   xmm0, xmm0
0x18000f2bd  js      short loc_18000F2C6
0x18000f2bf  cvtsi2ss xmm0, rdx
0x18000f2c4  jmp     short loc_18000F2DE
0x18000f2c6  mov     rcx, rdx
0x18000f2c9  shr     rcx, 1
0x18000f2cc  mov     rax, rdx
0x18000f2cf  and     eax, 1
0x18000f2d2  or      rcx, rax
0x18000f2d5  cvtsi2ss xmm0, rcx
0x18000f2da  addss   xmm0, xmm0
0x18000f2de  mov     rcx, cs:qword_18007BD98
0x18000f2e5  xorps   xmm1, xmm1
0x18000f2e8  test    rcx, rcx
0x18000f2eb  js      short loc_18000F2F4
0x18000f2ed  cvtsi2ss xmm1, rcx
0x18000f2f2  jmp     short loc_18000F309
0x18000f2f4  mov     rax, rcx
0x18000f2f7  shr     rax, 1
0x18000f2fa  and     ecx, 1
0x18000f2fd  or      rax, rcx
0x18000f300  cvtsi2ss xmm1, rax
0x18000f305  addss   xmm1, xmm1
0x18000f309  divss   xmm0, xmm1
0x18000f30d  comiss  xmm0, cs:dword_18007BD60
0x18000f314  jbe     short loc_18000F33D
0x18000f316  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000f31b  mov     rdx, rax
0x18000f31e  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::_Forced_rehash(unsigned __int64)
0x18000f323  mov     r9, rsi
0x18000f326  lea     r8, [rbp+10h]
0x18000f32a  lea     rdx, [rsp+68h+var_38]
0x18000f32f  call    ??$_Find_last@I@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@IPEAX@std@@@1@AEBI_K@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::_Find_last<uint>(uint const &,unsigned __int64)
0x18000f334  movups  xmm0, xmmword ptr [rax]
0x18000f337  movdqu  [rsp+68h+var_38], xmm0
0x18000f33d  mov     [rsp+68h+var_40], 0
0x18000f346  mov     r9, rbp
0x18000f349  mov     r8, qword ptr [rsp+68h+var_38]
0x18000f34e  mov     rdx, rsi
0x18000f351  call    ?_Insert_new_node_before@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@IPEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<uint,void *> * const,std::_List_node<uint,void *> * const)
0x18000f356  mov     [rbx], rax
0x18000f359  mov     byte ptr [rbx+8], 1
0x18000f35d  lea     rcx, [rsp+68h+var_48]
0x18000f362  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@IPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<uint,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<uint,void *>>>(void)
0x18000f367  mov     rax, rbx
0x18000f36a  add     rsp, 40h
0x18000f36e  pop     r14
0x18000f370  pop     rdi
0x18000f371  pop     rsi
0x18000f372  pop     rbp
0x18000f373  pop     rbx
0x18000f374  retn
```
