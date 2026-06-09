# std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::emplace<long &,Wns::ChannelRequestContext &>(long &,Wns::ChannelRequestContext &)

- ea: `0x180003bb8`
- end: `0x180003d60`
- name: `??$emplace@AEAJAEAUChannelRequestContext@Wns@@@?$_Hash@V?$_Umap_traits@JUChannelRequestContext@Wns@@V?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@std@@@std@@@std@@_N@1@AEAJAEAUChannelRequestContext@Wns@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(float *, __int64, _DWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800048b0`

## callees

- `0x180003bb8`
- `0x180016340`
- `0x180017678`
- `0x1800180c8`
- `0x180026adc`
- `0x180031328`
- `0x1800313cc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003c5a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003c5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::emplace<long &,Wns::ChannelRequestContext &>(
        float *a1,
        __int64 a2,
        _DWORD *a3,
        _OWORD *a4)
{
  __int64 v8; // rsi
  unsigned __int64 i; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rbp
  char *v13; // r15
  __int64 v14; // rdx
  float v15; // xmm0_4
  __int64 v16; // rcx
  float v17; // xmm1_4
  __int64 v18; // rax
  __int64 v19; // rax
  _QWORD v21[2]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v22[11]; // [rsp+30h] [rbp-58h] BYREF

  v8 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v8 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ (unsigned __int64)v8);
  v10 = *((_QWORD *)a1 + 3);
  v11 = *(_QWORD *)(v10 + 16 * (*((_QWORD *)a1 + 6) & v8) + 8);
  v12 = *((_QWORD *)a1 + 1);
  if ( v11 == v12 )
  {
LABEL_8:
    if ( *((_QWORD *)a1 + 2) == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v21[0] = a1 + 2;
    v13 = (char *)operator new(0x28u);
    v21[1] = v13;
    *((_DWORD *)v13 + 4) = *a3;
    *(_OWORD *)(v13 + 24) = *a4;
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
      std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::_Forced_rehash(
        a1,
        v19);
      v12 = *std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::_Find_last<long>(
               a1,
               v22,
               (_DWORD *)v13 + 4,
               v8);
    }
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::_Insert_new_node_before(
                      a1,
                      v8,
                      v12,
                      v13,
                      v21[0],
                      0);
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<long const,Wns::ChannelRequestContext>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<long const,Wns::ChannelRequestContext>,void *>>>(v21);
  }
  else
  {
    while ( *a3 != *(_DWORD *)(v11 + 16) )
    {
      if ( v11 == *(_QWORD *)(v10 + 16 * (*((_QWORD *)a1 + 6) & v8)) )
      {
        v12 = v11;
        goto LABEL_8;
      }
      v11 = *(_QWORD *)(v11 + 8);
    }
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180003bb8  push    rbx
0x180003bba  push    rbp
0x180003bbb  push    rsi
0x180003bbc  push    rdi
0x180003bbd  push    r12
0x180003bbf  push    r13
0x180003bc1  push    r14
0x180003bc3  push    r15
0x180003bc5  sub     rsp, 48h
0x180003bc9  mov     r13, r9
0x180003bcc  mov     r14, r8
0x180003bcf  mov     rdi, rdx
0x180003bd2  mov     rbx, rcx
0x180003bd5  mov     rsi, 0CBF29CE484222325h
0x180003bdf  xor     ecx, ecx
0x180003be1  movzx   eax, byte ptr [r8+rcx]
0x180003be6  xor     rsi, rax
0x180003be9  mov     rdx, 100000001B3h
0x180003bf3  imul    rsi, rdx
0x180003bf7  inc     rcx
0x180003bfa  cmp     rcx, 4
0x180003bfe  jb      short loc_180003BE1
0x180003c00  mov     rdx, rsi
0x180003c03  and     rdx, [rbx+30h]
0x180003c07  mov     r8, [rbx+18h]
0x180003c0b  mov     rax, rdx
0x180003c0e  add     rax, rax
0x180003c11  mov     rcx, [r8+rax*8+8]
0x180003c16  lea     r9, [rbx+8]
0x180003c1a  mov     rbp, [r9]
0x180003c1d  cmp     rcx, rbp
0x180003c20  jz      short loc_180003C43
0x180003c22  add     rdx, rdx
0x180003c25  mov     rax, [r8+rdx*8]
0x180003c29  mov     edx, [r14]
0x180003c2c  cmp     edx, [rcx+10h]
0x180003c2f  jz      loc_180003D45
0x180003c35  cmp     rcx, rax
0x180003c38  jz      short loc_180003C40
0x180003c3a  mov     rcx, [rcx+8]
0x180003c3e  jmp     short loc_180003C2C
0x180003c40  mov     rbp, rcx
0x180003c43  mov     rax, 666666666666666h
0x180003c4d  cmp     [rbx+10h], rax
0x180003c51  jnz     short loc_180003C61
0x180003c53  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180003c5a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180003c61  mov     [rsp+88h+var_68], r9
0x180003c66  mov     [rsp+88h+var_60], 0
0x180003c6f  mov     ecx, 28h ; '('; Size
0x180003c74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c79  mov     r15, rax
0x180003c7c  mov     [rsp+88h+var_60], rax
0x180003c81  mov     ecx, [r14]
0x180003c84  mov     [rax+10h], ecx
0x180003c87  movups  xmm0, xmmword ptr [r13+0]
0x180003c8c  movdqu  xmmword ptr [rax+18h], xmm0
0x180003c91  mov     rdx, [rbx+10h]
0x180003c95  add     rdx, 1
0x180003c99  xorps   xmm0, xmm0
0x180003c9c  js      short loc_180003CA5
0x180003c9e  cvtsi2ss xmm0, rdx
0x180003ca3  jmp     short loc_180003CBD
0x180003ca5  mov     rcx, rdx
0x180003ca8  shr     rcx, 1
0x180003cab  mov     rax, rdx
0x180003cae  and     eax, 1
0x180003cb1  or      rcx, rax
0x180003cb4  cvtsi2ss xmm0, rcx
0x180003cb9  addss   xmm0, xmm0
0x180003cbd  mov     rcx, [rbx+38h]
0x180003cc1  xorps   xmm1, xmm1
0x180003cc4  test    rcx, rcx
0x180003cc7  js      short loc_180003CD0
0x180003cc9  cvtsi2ss xmm1, rcx
0x180003cce  jmp     short loc_180003CE5
0x180003cd0  mov     rax, rcx
0x180003cd3  shr     rax, 1
0x180003cd6  and     ecx, 1
0x180003cd9  or      rax, rcx
0x180003cdc  cvtsi2ss xmm1, rax
0x180003ce1  addss   xmm1, xmm1
0x180003ce5  divss   xmm0, xmm1
0x180003ce9  comiss  xmm0, dword ptr [rbx]
0x180003cec  jbe     short loc_180003D18
0x180003cee  mov     rcx, rbx
0x180003cf1  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180003cf6  mov     rdx, rax
0x180003cf9  mov     rcx, rbx
0x180003cfc  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@JUChannelRequestContext@Wns@@V?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@4@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::_Forced_rehash(unsigned __int64)
0x180003d01  mov     r9, rsi
0x180003d04  lea     r8, [r15+10h]
0x180003d08  lea     rdx, [rsp+88h+var_58]
0x180003d0d  mov     rcx, rbx
0x180003d10  call    ??$_Find_last@J@?$_Hash@V?$_Umap_traits@JUChannelRequestContext@Wns@@V?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@PEAX@std@@@1@AEBJ_K@Z; std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::_Find_last<long>(long const &,unsigned __int64)
0x180003d15  mov     rbp, [rax]
0x180003d18  mov     [rsp+88h+var_60], 0
0x180003d21  mov     r9, r15
0x180003d24  mov     r8, rbp
0x180003d27  mov     rdx, rsi
0x180003d2a  mov     rcx, rbx
0x180003d2d  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@JUChannelRequestContext@Wns@@V?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@4@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<long const,Wns::ChannelRequestContext>,void *> * const,std::_List_node<std::pair<long const,Wns::ChannelRequestContext>,void *> * const)
0x180003d32  mov     [rdi], rax
0x180003d35  mov     byte ptr [rdi+8], 1
0x180003d39  lea     rcx, [rsp+88h+var_68]
0x180003d3e  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<long const,Wns::ChannelRequestContext>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<long const,Wns::ChannelRequestContext>,void *>>>(void)
0x180003d43  jmp     short loc_180003D4C
0x180003d45  mov     [rdi], rcx
0x180003d48  mov     byte ptr [rdi+8], 0
0x180003d4c  mov     rax, rdi
0x180003d4f  add     rsp, 48h
0x180003d53  pop     r15
0x180003d55  pop     r14
0x180003d57  pop     r13
0x180003d59  pop     r12
0x180003d5b  pop     rdi
0x180003d5c  pop     rsi
0x180003d5d  pop     rbp
0x180003d5e  pop     rbx
0x180003d5f  retn
```
