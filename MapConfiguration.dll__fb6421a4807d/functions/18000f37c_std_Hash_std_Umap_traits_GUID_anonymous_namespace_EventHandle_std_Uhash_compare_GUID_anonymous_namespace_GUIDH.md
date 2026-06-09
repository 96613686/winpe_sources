# std::_Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___::emplace__GUID_const_&__GUID_const_&_

- ea: `0x18000f37c`
- end: `0x18000f4f6`
- name: `std::_Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___::emplace__GUID_const_&__GUID_const_&_`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800122e0`

## callees

- `0x18000b7fc`
- `0x18000e220`
- `0x18000f194`
- `0x18000f37c`
- `0x1800111a4`
- `0x180013e78`
- `0x180014400`
- `0x1800148fc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f3f4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f3f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___::emplace__GUID_const____GUID_const___(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4)
{
  unsigned __int64 v8; // rsi
  _QWORD *v9; // rbp
  __int64 v10; // rcx
  __int64 v11; // rdx
  float v12; // xmm0_4
  __int64 v13; // rcx
  float v14; // xmm1_4
  __int64 v15; // rax
  __int64 v16; // rax
  _QWORD v18[2]; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v19[4]; // [rsp+30h] [rbp-48h] BYREF

  v8 = *a3 ^ *((unsigned __int16 *)a3 + 2) ^ *((unsigned __int16 *)a3 + 3) ^ a3[2] ^ (unsigned __int64)a3[3];
  std::_Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___::_Find_last__GUID_(
    a1,
    v19,
    a3,
    v8);
  if ( *((_QWORD *)&v19[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v19[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 16) == 0x1FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v9 = std::_Allocate<16,std::_Default_allocate_traits>(0x80u);
    std::_Default_allocator_traits_std::allocator_std::_List_node_std::pair__GUID_const___anonymous_namespace_::EventHandle__void_______::construct_std::pair__GUID_const___anonymous_namespace_::EventHandle___GUID_const____GUID_const___(
      v10,
      v9 + 2,
      a3,
      a4,
      a1 + 8,
      v9);
    v11 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v11 < 0 )
      v12 = (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1))
          + (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1));
    else
      v12 = (float)(int)v11;
    v13 = *(_QWORD *)(a1 + 56);
    if ( v13 < 0 )
    {
      v15 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v13 >> 1);
      v14 = (float)(int)v15 + (float)(int)v15;
    }
    else
    {
      v14 = (float)(int)v13;
    }
    if ( (float)(v12 / v14) > *(float *)(a1 + 4) )
    {
      v16 = std::_Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___::_Desired_grow_bucket_count(a1);
      std::_Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___::_Forced_rehash(
        a1,
        v16);
      v19[0] = *(_OWORD *)std::_Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___::_Find_last__GUID_(
                            a1,
                            v19,
                            v9 + 2,
                            v8);
    }
    v18[1] = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(
                      a1,
                      v8,
                      *(_QWORD *)&v19[0],
                      v9);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2_std::allocator_std::_List_node_std::pair__GUID_const___anonymous_namespace_::EventHandle__void_______::__List_node_emplace_op2_std::allocator_std::_List_node_std::pair__GUID_const___anonymous_namespace_::EventHandle__void_______(v18);
  }
  return a2;
}

```

## disassembly

```asm
0x18000f37c  push    rbx
0x18000f37e  push    rbp
0x18000f37f  push    rsi
0x18000f380  push    rdi
0x18000f381  push    r14
0x18000f383  push    r15
0x18000f385  sub     rsp, 48h
0x18000f389  mov     r15, r9
0x18000f38c  mov     r14, r8
0x18000f38f  mov     rbx, rdx
0x18000f392  mov     rdi, rcx
0x18000f395  mov     esi, [r8+0Ch]
0x18000f399  mov     eax, [r8+8]
0x18000f39d  xor     rsi, rax
0x18000f3a0  movzx   eax, word ptr [r8+6]
0x18000f3a5  xor     rsi, rax
0x18000f3a8  movzx   eax, word ptr [r8+4]
0x18000f3ad  xor     rsi, rax
0x18000f3b0  mov     eax, [r8]
0x18000f3b3  xor     rsi, rax
0x18000f3b6  mov     r9, rsi
0x18000f3b9  lea     rdx, [rsp+78h+var_48]
0x18000f3be  call    std___Hash_std___Umap_traits__GUID__anonymous_namespace___EventHandle_std___Uhash_compare__GUID__anonymous_namespace___GUIDHasher_std__equal_to__GUID____std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle____0______Find_last__GUID_
0x18000f3c3  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18000f3c8  test    rdx, rdx
0x18000f3cb  jz      short loc_18000F3D9
0x18000f3cd  mov     [rbx], rdx
0x18000f3d0  mov     byte ptr [rbx+8], 0
0x18000f3d4  jmp     loc_18000F4E6
0x18000f3d9  lea     rax, [rdi+8]
0x18000f3dd  mov     rcx, 1FFFFFFFFFFFFFFh
0x18000f3e7  cmp     [rax+8], rcx
0x18000f3eb  jnz     short loc_18000F3FB
0x18000f3ed  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000f3f4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f3fb  mov     [rsp+78h+var_58], rax
0x18000f400  mov     [rsp+78h+var_50], 0
0x18000f409  mov     ecx, 80h
0x18000f40e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000f413  mov     rbp, rax
0x18000f416  mov     [rsp+78h+var_50], rax
0x18000f41b  lea     rdx, [rax+10h]
0x18000f41f  mov     r9, r15
0x18000f422  mov     r8, r14
0x18000f425  call    std___Default_allocator_traits_std__allocator_std___List_node_std__pair__GUID_const___anonymous_namespace___EventHandle__void_________construct_std__pair__GUID_const___anonymous_namespace___EventHandle___GUID_const____GUID_const___
0x18000f42a  nop
0x18000f42b  mov     rdx, [rdi+10h]
0x18000f42f  add     rdx, 1
0x18000f433  xorps   xmm0, xmm0
0x18000f436  js      short loc_18000F43F
0x18000f438  cvtsi2ss xmm0, rdx
0x18000f43d  jmp     short loc_18000F457
0x18000f43f  mov     rcx, rdx
0x18000f442  shr     rcx, 1
0x18000f445  mov     rax, rdx
0x18000f448  and     eax, 1
0x18000f44b  or      rcx, rax
0x18000f44e  cvtsi2ss xmm0, rcx
0x18000f453  addss   xmm0, xmm0
0x18000f457  mov     rcx, [rdi+38h]
0x18000f45b  xorps   xmm1, xmm1
0x18000f45e  test    rcx, rcx
0x18000f461  js      short loc_18000F46A
0x18000f463  cvtsi2ss xmm1, rcx
0x18000f468  jmp     short loc_18000F47F
0x18000f46a  mov     rax, rcx
0x18000f46d  shr     rax, 1
0x18000f470  and     ecx, 1
0x18000f473  or      rax, rcx
0x18000f476  cvtsi2ss xmm1, rax
0x18000f47b  addss   xmm1, xmm1
0x18000f47f  divss   xmm0, xmm1
0x18000f483  comiss  xmm0, dword ptr [rdi+4]
0x18000f487  jbe     short loc_18000F4B9
0x18000f489  mov     rcx, rdi
0x18000f48c  call    std___Hash_std___Umap_traits__GUID__anonymous_namespace___EventHandle_std___Uhash_compare__GUID__anonymous_namespace___GUIDHasher_std__equal_to__GUID____std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle____0______Desired_grow_bucket_count
0x18000f491  mov     rdx, rax
0x18000f494  mov     rcx, rdi
0x18000f497  call    std___Hash_std___Umap_traits__GUID__anonymous_namespace___EventHandle_std___Uhash_compare__GUID__anonymous_namespace___GUIDHasher_std__equal_to__GUID____std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle____0______Forced_rehash
0x18000f49c  lea     r8, [rbp+10h]
0x18000f4a0  mov     r9, rsi
0x18000f4a3  lea     rdx, [rsp+78h+var_48]
0x18000f4a8  mov     rcx, rdi
0x18000f4ab  call    std___Hash_std___Umap_traits__GUID__anonymous_namespace___EventHandle_std___Uhash_compare__GUID__anonymous_namespace___GUIDHasher_std__equal_to__GUID____std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle____0______Find_last__GUID_
0x18000f4b0  movups  xmm0, xmmword ptr [rax]
0x18000f4b3  movdqu  [rsp+78h+var_48], xmm0
0x18000f4b9  mov     [rsp+78h+var_50], 0
0x18000f4c2  mov     r9, rbp
0x18000f4c5  mov     r8, qword ptr [rsp+78h+var_48]
0x18000f4ca  mov     rdx, rsi
0x18000f4cd  mov     rcx, rdi
0x18000f4d0  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x18000f4d5  mov     [rbx], rax
0x18000f4d8  mov     byte ptr [rbx+8], 1
0x18000f4dc  lea     rcx, [rsp+78h+var_58]
0x18000f4e1  call    std___List_node_emplace_op2_std__allocator_std___List_node_std__pair__GUID_const___anonymous_namespace___EventHandle__void___________List_node_emplace_op2_std__allocator_std___List_node_std__pair__GUID_const___anonymous_namespace___EventHandle__void_______
0x18000f4e6  mov     rax, rbx
0x18000f4e9  add     rsp, 48h
0x18000f4ed  pop     r15
0x18000f4ef  pop     r14
0x18000f4f1  pop     rdi
0x18000f4f2  pop     rsi
0x18000f4f3  pop     rbp
0x18000f4f4  pop     rbx
0x18000f4f5  retn
```
