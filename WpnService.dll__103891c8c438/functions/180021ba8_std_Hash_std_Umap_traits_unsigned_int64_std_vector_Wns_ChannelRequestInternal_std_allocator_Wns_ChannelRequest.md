# std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal,std::allocator<Wns::ChannelRequestInternal>>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal,std::allocator<Wns::ChannelRequestInternal>>>>,0>>::emplace<unsigned __int64 &,std::vector<Wns::ChannelRequestInternal,std::allocator<Wns::ChannelRequestInternal>>>(unsigned __int64 &,std::vector<Wns::ChannelRequestInternal,std::allocator<Wns::ChannelRequestInternal>> &&)

- ea: `0x180021ba8`
- end: `0x180021d6e`
- name: `??$emplace@AEA_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@?$_Hash@V?$_Umap_traits@_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@AEA_K$$QEAV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@1@@Z`
- size: `454`
- prototype: `__int64 __fastcall(float *, __int64, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800217f4`

## callees

- `0x180015a54`
- `0x180016b3c`
- `0x180021ba8`
- `0x180021d74`
- `0x180026adc`
- `0x180031328`
- `0x180031544`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180021c10`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180021c10`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::emplace<unsigned __int64 &,std::vector<Wns::ChannelRequestInternal>>(
        float *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4)
{
  __int64 v8; // rbp
  _QWORD *v9; // rdx
  _QWORD *v10; // rbx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  float v15; // xmm0_4
  __int64 v16; // rcx
  float v17; // xmm1_4
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r9
  _QWORD *v26; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v27; // [rsp+28h] [rbp-60h]
  _OWORD v28[5]; // [rsp+30h] [rbp-58h] BYREF

  v8 = std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>::operator()<unsigned __int64>(
         (__int64)a1,
         (__int64)a3);
  std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Find_last<unsigned __int64>(
    a1,
    v28,
    v9,
    v8);
  if ( !*((_QWORD *)&v28[0] + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v26 = a1 + 2;
    v10 = operator new(0x30u);
    v27 = v10;
    v10[2] = *a3;
    v11 = a4[2];
    a4[2] = 0;
    v12 = a4[1];
    a4[1] = 0;
    v13 = *a4;
    *a4 = 0;
    v10[3] = v13;
    v10[4] = v12;
    v10[5] = v11;
    v14 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v14 < 0 )
      v15 = (float)(v14 & 1 | (unsigned int)((unsigned __int64)v14 >> 1))
          + (float)(v14 & 1 | (unsigned int)((unsigned __int64)v14 >> 1));
    else
      v15 = (float)(int)v14;
    v16 = *((_QWORD *)a1 + 7);
    if ( v16 < 0 )
    {
      v18 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v16 >> 1);
      v17 = (float)(int)v18 + (float)(int)v18;
    }
    else
    {
      v17 = (float)(int)v16;
    }
    if ( (float)(v15 / v17) > *a1 )
    {
      v19 = std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Forced_rehash(
        a1,
        v19);
      v28[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Find_last<unsigned __int64>(
                            a1,
                            v28,
                            v10 + 2,
                            v8);
    }
    v27 = 0;
    v20 = *(_QWORD *)&v28[0];
    v21 = *(_QWORD **)(*(_QWORD *)&v28[0] + 8LL);
    ++*((_QWORD *)a1 + 2);
    *v10 = v20;
    v10[1] = v21;
    *v21 = v10;
    *(_QWORD *)(v20 + 8) = v10;
    v22 = *((_QWORD *)a1 + 3);
    v23 = 2 * (v8 & *((_QWORD *)a1 + 6));
    v24 = *(_QWORD *)(v22 + 16 * (v8 & *((_QWORD *)a1 + 6)));
    if ( v24 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v22 + 16 * (v8 & *((_QWORD *)a1 + 6))) = v10;
LABEL_18:
      *(_QWORD *)(v22 + 8 * v23 + 8) = v10;
      goto LABEL_19;
    }
    if ( v24 == v20 )
    {
      *(_QWORD *)(v22 + 16 * (v8 & *((_QWORD *)a1 + 6))) = v10;
    }
    else if ( *(_QWORD **)(v22 + 16 * (v8 & *((_QWORD *)a1 + 6)) + 8) == v21 )
    {
      goto LABEL_18;
    }
LABEL_19:
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>,void *>>>(&v26);
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v28[0] + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180021ba8  push    rbx
0x180021baa  push    rbp
0x180021bab  push    rsi
0x180021bac  push    rdi
0x180021bad  push    r12
0x180021baf  push    r13
0x180021bb1  push    r14
0x180021bb3  push    r15
0x180021bb5  sub     rsp, 48h
0x180021bb9  mov     r14, r9
0x180021bbc  mov     r15, r8
0x180021bbf  mov     rdi, rdx
0x180021bc2  mov     rsi, rcx
0x180021bc5  mov     rdx, r8
0x180021bc8  call    ??$?R_K@?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@QEBA_KAEB_K@Z; std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>::operator()<unsigned __int64>(unsigned __int64 const &)
0x180021bcd  mov     rbp, rax
0x180021bd0  mov     r9, rax
0x180021bd3  mov     r8, rdx
0x180021bd6  lea     rdx, [rsp+88h+var_58]
0x180021bdb  mov     rcx, rsi
0x180021bde  call    ??$_Find_last@_K@?$_Hash@V?$_Umap_traits@_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@PEAX@std@@@1@AEB_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Find_last<unsigned __int64>(unsigned __int64 const &,unsigned __int64)
0x180021be3  mov     rdx, qword ptr [rsp+88h+var_58+8]
0x180021be8  test    rdx, rdx
0x180021beb  jz      short loc_180021BF9
0x180021bed  mov     [rdi], rdx
0x180021bf0  mov     byte ptr [rdi+8], 0
0x180021bf4  jmp     loc_180021D5A
0x180021bf9  mov     rax, 555555555555555h
0x180021c03  cmp     [rsi+10h], rax
0x180021c07  jnz     short loc_180021C17
0x180021c09  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180021c10  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180021c17  lea     r13, [rsi+8]
0x180021c1b  mov     [rsp+88h+var_68], r13
0x180021c20  mov     [rsp+88h+var_60], 0
0x180021c29  mov     ecx, 30h ; '0'; Size
0x180021c2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021c33  mov     rbx, rax
0x180021c36  mov     [rsp+88h+var_60], rax
0x180021c3b  mov     rcx, [r15]
0x180021c3e  mov     [rax+10h], rcx
0x180021c42  mov     r8, [r14+10h]
0x180021c46  xor     r15d, r15d
0x180021c49  mov     [r14+10h], r15
0x180021c4d  mov     rdx, [r14+8]
0x180021c51  mov     [r14+8], r15
0x180021c55  mov     rcx, [r14]
0x180021c58  mov     [r14], r15
0x180021c5b  mov     [rax+18h], rcx
0x180021c5f  mov     [rax+20h], rdx
0x180021c63  mov     [rax+28h], r8
0x180021c67  mov     rdx, [rsi+10h]
0x180021c6b  add     rdx, 1
0x180021c6f  xorps   xmm0, xmm0
0x180021c72  js      short loc_180021C7B
0x180021c74  cvtsi2ss xmm0, rdx
0x180021c79  jmp     short loc_180021C93
0x180021c7b  mov     rcx, rdx
0x180021c7e  shr     rcx, 1
0x180021c81  mov     rax, rdx
0x180021c84  and     eax, 1
0x180021c87  or      rcx, rax
0x180021c8a  cvtsi2ss xmm0, rcx
0x180021c8f  addss   xmm0, xmm0
0x180021c93  mov     rcx, [rsi+38h]
0x180021c97  xorps   xmm1, xmm1
0x180021c9a  test    rcx, rcx
0x180021c9d  js      short loc_180021CA6
0x180021c9f  cvtsi2ss xmm1, rcx
0x180021ca4  jmp     short loc_180021CBB
0x180021ca6  mov     rax, rcx
0x180021ca9  shr     rax, 1
0x180021cac  and     ecx, 1
0x180021caf  or      rax, rcx
0x180021cb2  cvtsi2ss xmm1, rax
0x180021cb7  addss   xmm1, xmm1
0x180021cbb  divss   xmm0, xmm1
0x180021cbf  comiss  xmm0, dword ptr [rsi]
0x180021cc2  jbe     short loc_180021CF4
0x180021cc4  mov     rcx, rsi
0x180021cc7  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180021ccc  mov     rdx, rax
0x180021ccf  mov     rcx, rsi
0x180021cd2  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Forced_rehash(unsigned __int64)
0x180021cd7  mov     r9, rbp
0x180021cda  lea     r8, [rbx+10h]
0x180021cde  lea     rdx, [rsp+88h+var_58]
0x180021ce3  mov     rcx, rsi
0x180021ce6  call    ??$_Find_last@_K@?$_Hash@V?$_Umap_traits@_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@PEAX@std@@@1@AEB_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Find_last<unsigned __int64>(unsigned __int64 const &,unsigned __int64)
0x180021ceb  movups  xmm0, xmmword ptr [rax]
0x180021cee  movdqu  [rsp+88h+var_58], xmm0
0x180021cf4  mov     [rsp+88h+var_60], r15
0x180021cf9  mov     rdx, qword ptr [rsp+88h+var_58]
0x180021cfe  mov     r8, [rdx+8]
0x180021d02  inc     qword ptr [rsi+10h]
0x180021d06  mov     [rbx], rdx
0x180021d09  mov     [rbx+8], r8
0x180021d0d  mov     [r8], rbx
0x180021d10  mov     [rdx+8], rbx
0x180021d14  mov     rcx, [rsi+18h]
0x180021d18  mov     rax, [rsi+30h]
0x180021d1c  and     rax, rbp
0x180021d1f  add     rax, rax
0x180021d22  mov     r9, [rcx+rax*8]
0x180021d26  cmp     r9, [r13+0]
0x180021d2a  jnz     short loc_180021D32
0x180021d2c  mov     [rcx+rax*8], rbx
0x180021d30  jmp     short loc_180021D44
0x180021d32  cmp     r9, rdx
0x180021d35  jnz     short loc_180021D3D
0x180021d37  mov     [rcx+rax*8], rbx
0x180021d3b  jmp     short loc_180021D49
0x180021d3d  cmp     [rcx+rax*8+8], r8
0x180021d42  jnz     short loc_180021D49
0x180021d44  mov     [rcx+rax*8+8], rbx
0x180021d49  mov     [rdi], rbx
0x180021d4c  mov     byte ptr [rdi+8], 1
0x180021d50  lea     rcx, [rsp+88h+var_68]
0x180021d55  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>,void *>>>(void)
0x180021d5a  mov     rax, rdi
0x180021d5d  add     rsp, 48h
0x180021d61  pop     r15
0x180021d63  pop     r14
0x180021d65  pop     r13
0x180021d67  pop     r12
0x180021d69  pop     rdi
0x180021d6a  pop     rsi
0x180021d6b  pop     rbp
0x180021d6c  pop     rbx
0x180021d6d  retn
```
