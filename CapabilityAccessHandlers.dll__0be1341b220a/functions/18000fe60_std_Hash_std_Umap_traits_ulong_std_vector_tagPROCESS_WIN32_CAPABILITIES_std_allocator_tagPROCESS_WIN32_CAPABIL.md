# std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>>,0>>::_Try_emplace<ulong const &,>(ulong const &)

- ea: `0x18000fe60`
- end: `0x180010015`
- name: `??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z`
- size: `437`
- prototype: `__int64 __fastcall(float *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800103c0`

## callees

- `0x180005270`
- `0x18000f91c`
- `0x18000fb60`
- `0x18000fe60`
- `0x180010218`
- `0x180010f00`
- `0x180010fa4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fec7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fec7`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Try_emplace<unsigned long const &,>(
        float *a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 v6; // r12
  _DWORD *v7; // rdx
  _DWORD *v8; // rbx
  __int64 v9; // rdx
  float v10; // xmm0_4
  __int64 v11; // rcx
  float v12; // xmm1_4
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  _QWORD *v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  _QWORD *v21; // [rsp+20h] [rbp-58h] BYREF
  _DWORD *v22; // [rsp+28h] [rbp-50h]
  _OWORD v23[4]; // [rsp+30h] [rbp-48h] BYREF

  v6 = std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>::operator()<unsigned long>(
         (__int64)a1,
         (__int64)a3);
  std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Find_last<unsigned long>(
    a1,
    v23,
    v7,
    v6);
  if ( !*((_QWORD *)&v23[0] + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v21 = a1 + 2;
    v8 = operator new(0x30u);
    v22 = v8;
    v8[4] = *a3;
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 5) = 0;
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
      v14 = std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Forced_rehash(
        a1,
        v14);
      v23[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Find_last<unsigned long>(
                            a1,
                            v23,
                            v8 + 4,
                            v6);
    }
    v22 = 0;
    v15 = *(_QWORD *)&v23[0];
    v16 = *(_QWORD **)(*(_QWORD *)&v23[0] + 8LL);
    ++*((_QWORD *)a1 + 2);
    *(_QWORD *)v8 = v15;
    *((_QWORD *)v8 + 1) = v16;
    *v16 = v8;
    *(_QWORD *)(v15 + 8) = v8;
    v17 = 2 * (v6 & *((_QWORD *)a1 + 6));
    v18 = *((_QWORD *)a1 + 3);
    v19 = *(_QWORD *)(v18 + 16 * (v6 & *((_QWORD *)a1 + 6)));
    if ( v19 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v18 + 16 * (v6 & *((_QWORD *)a1 + 6))) = v8;
LABEL_18:
      *(_QWORD *)(v18 + 8 * v17 + 8) = v8;
      goto LABEL_19;
    }
    if ( v19 == v15 )
    {
      *(_QWORD *)(v18 + 16 * (v6 & *((_QWORD *)a1 + 6))) = v8;
    }
    else if ( *(_QWORD **)(v18 + 16 * (v6 & *((_QWORD *)a1 + 6)) + 8) == v16 )
    {
      goto LABEL_18;
    }
LABEL_19:
    *(_QWORD *)a2 = v8;
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>(&v21);
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v23[0] + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18000fe60  push    rbx
0x18000fe62  push    rbp
0x18000fe63  push    rsi
0x18000fe64  push    rdi
0x18000fe65  push    r12
0x18000fe67  push    r14
0x18000fe69  push    r15
0x18000fe6b  sub     rsp, 40h
0x18000fe6f  mov     r14, r8
0x18000fe72  mov     rdi, rdx
0x18000fe75  mov     rsi, rcx
0x18000fe78  mov     rdx, r8
0x18000fe7b  call    ??$?RK@?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@QEBA_KAEBK@Z; std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>::operator()<ulong>(ulong const &)
0x18000fe80  mov     r12, rax
0x18000fe83  mov     r9, rax
0x18000fe86  mov     r8, rdx
0x18000fe89  lea     rdx, [rsp+78h+var_48]
0x18000fe8e  mov     rcx, rsi
0x18000fe91  call    ??$_Find_last@K@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@1@AEBK_K@Z; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Find_last<ulong>(ulong const &,unsigned __int64)
0x18000fe96  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18000fe9b  test    rdx, rdx
0x18000fe9e  jz      short loc_18000FEAC
0x18000fea0  mov     [rdi], rdx
0x18000fea3  mov     byte ptr [rdi+8], 0
0x18000fea7  jmp     loc_180010003
0x18000feac  lea     rbp, [rsi+8]
0x18000feb0  mov     rax, 555555555555555h
0x18000feba  cmp     [rbp+8], rax
0x18000febe  jnz     short loc_18000FECE
0x18000fec0  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000fec7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000fece  mov     [rsp+78h+var_58], rbp
0x18000fed3  mov     [rsp+78h+var_50], 0
0x18000fedc  mov     ecx, 30h ; '0'; Size
0x18000fee1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fee6  mov     rbx, rax
0x18000fee9  mov     [rsp+78h+var_50], rax
0x18000feee  mov     ecx, [r14]
0x18000fef1  mov     [rax+10h], ecx
0x18000fef4  mov     qword ptr [rax+18h], 0
0x18000fefc  mov     qword ptr [rax+20h], 0
0x18000ff04  mov     qword ptr [rax+28h], 0
0x18000ff0c  mov     rdx, [rsi+10h]
0x18000ff10  add     rdx, 1
0x18000ff14  xorps   xmm0, xmm0
0x18000ff17  js      short loc_18000FF20
0x18000ff19  cvtsi2ss xmm0, rdx
0x18000ff1e  jmp     short loc_18000FF38
0x18000ff20  mov     rcx, rdx
0x18000ff23  shr     rcx, 1
0x18000ff26  mov     rax, rdx
0x18000ff29  and     eax, 1
0x18000ff2c  or      rcx, rax
0x18000ff2f  cvtsi2ss xmm0, rcx
0x18000ff34  addss   xmm0, xmm0
0x18000ff38  mov     rcx, [rsi+38h]
0x18000ff3c  xorps   xmm1, xmm1
0x18000ff3f  test    rcx, rcx
0x18000ff42  js      short loc_18000FF4B
0x18000ff44  cvtsi2ss xmm1, rcx
0x18000ff49  jmp     short loc_18000FF60
0x18000ff4b  mov     rax, rcx
0x18000ff4e  shr     rax, 1
0x18000ff51  and     ecx, 1
0x18000ff54  or      rax, rcx
0x18000ff57  cvtsi2ss xmm1, rax
0x18000ff5c  addss   xmm1, xmm1
0x18000ff60  divss   xmm0, xmm1
0x18000ff64  comiss  xmm0, dword ptr [rsi]
0x18000ff67  jbe     short loc_18000FF99
0x18000ff69  mov     rcx, rsi
0x18000ff6c  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000ff71  mov     rdx, rax
0x18000ff74  mov     rcx, rsi
0x18000ff77  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Forced_rehash(unsigned __int64)
0x18000ff7c  mov     r9, r12
0x18000ff7f  lea     r8, [rbx+10h]
0x18000ff83  lea     rdx, [rsp+78h+var_48]
0x18000ff88  mov     rcx, rsi
0x18000ff8b  call    ??$_Find_last@K@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@1@AEBK_K@Z; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Find_last<ulong>(ulong const &,unsigned __int64)
0x18000ff90  movups  xmm0, xmmword ptr [rax]
0x18000ff93  movdqu  [rsp+78h+var_48], xmm0
0x18000ff99  mov     [rsp+78h+var_50], 0
0x18000ffa2  mov     rdx, qword ptr [rsp+78h+var_48]
0x18000ffa7  mov     r8, [rdx+8]
0x18000ffab  inc     qword ptr [rsi+10h]
0x18000ffaf  mov     [rbx], rdx
0x18000ffb2  mov     [rbx+8], r8
0x18000ffb6  mov     [r8], rbx
0x18000ffb9  mov     [rdx+8], rbx
0x18000ffbd  mov     rax, [rsi+30h]
0x18000ffc1  and     rax, r12
0x18000ffc4  add     rax, rax
0x18000ffc7  mov     rcx, [rsi+18h]
0x18000ffcb  mov     r9, [rcx+rax*8]
0x18000ffcf  cmp     r9, [rbp+0]
0x18000ffd3  jnz     short loc_18000FFDB
0x18000ffd5  mov     [rcx+rax*8], rbx
0x18000ffd9  jmp     short loc_18000FFED
0x18000ffdb  cmp     r9, rdx
0x18000ffde  jnz     short loc_18000FFE6
0x18000ffe0  mov     [rcx+rax*8], rbx
0x18000ffe4  jmp     short loc_18000FFF2
0x18000ffe6  cmp     [rcx+rax*8+8], r8
0x18000ffeb  jnz     short loc_18000FFF2
0x18000ffed  mov     [rcx+rax*8+8], rbx
0x18000fff2  mov     [rdi], rbx
0x18000fff5  mov     byte ptr [rdi+8], 1
0x18000fff9  lea     rcx, [rsp+78h+var_58]
0x18000fffe  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>(void)
0x180010003  mov     rax, rdi
0x180010006  add     rsp, 40h
0x18001000a  pop     r15
0x18001000c  pop     r14
0x18001000e  pop     r12
0x180010010  pop     rdi
0x180010011  pop     rsi
0x180010012  pop     rbp
0x180010013  pop     rbx
0x180010014  retn
```
