# std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Insert<std::pair<_GUID const,ushort> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>(std::pair<_GUID const,ushort> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>)

- ea: `0x180008680`
- end: `0x180008892`
- name: `??$_Insert@AEAU?$pair@$$CBU_GUID@@G@std@@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@$$CBU_GUID@@G@1@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@1@@Z`
- size: `530`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008680`
- `0x18000aa6c`

## callees

- `0x180008680`
- `0x18000ce94`
- `0x18000cf28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000871f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000871f`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Insert<std::pair<_GUID const,unsigned short> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>>(
        __int64 **a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4)
{
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 *v10; // rdi
  __int64 *v11; // rdx
  __int64 *v12; // rdi
  __int64 *v13; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  __int64 *v17; // rdx
  __int64 *v18; // rax
  __int64 **v19; // rax
  __int64 *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  float v23; // xmm0_4
  __int64 v24; // rax
  float v25; // xmm1_4
  __int64 v26; // rcx
  __int64 *v27; // rax
  __int64 v28; // r15
  __int64 v29; // rdi
  _QWORD *iter; // rax
  __int64 *v31; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v32[48]; // [rsp+28h] [rbp-30h] BYREF

  v8 = std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Hashval(
         a1,
         a3);
  v9 = 2 * v8;
  v10 = a1[2];
  v11 = (__int64 *)v10[2 * v8];
  if ( v11 == *a1 )
    v12 = *a1;
  else
    v12 = *(__int64 **)v10[2 * v8 + 1];
  while ( v12 != v11 )
  {
    v13 = (__int64 *)v12[1];
    v12 = v13;
    if ( *a3 == v13[2] && a3[1] == v13[3] )
    {
      if ( v13[2] == *a3 && v13[3] == a3[1] )
      {
        if ( a4 != *a1 )
        {
          *(_QWORD *)a4[1] = *a4;
          *(_QWORD *)(*a4 + 8) = a4[1];
          operator delete(a4);
          a1[1] = (__int64 *)((char *)a1[1] - 1);
        }
        *(_QWORD *)a2 = v12;
        *(_BYTE *)(a2 + 8) = 0;
        return a2;
      }
      v12 = (__int64 *)*v13;
      break;
    }
  }
  v31 = a4;
  v15 = *a4;
  if ( v12 != (__int64 *)*a4 )
  {
    *(_QWORD *)a4[1] = v15;
    **(_QWORD **)(v15 + 8) = v12;
    *(_QWORD *)v12[1] = a4;
    v16 = (_QWORD *)v12[1];
    v12[1] = *(_QWORD *)(v15 + 8);
    *(_QWORD *)(v15 + 8) = a4[1];
    a4[1] = (__int64)v16;
  }
  v17 = a1[2];
  v18 = (__int64 *)v17[2 * v8];
  if ( v18 == *a1 )
  {
    v17[v9] = (__int64)a4;
    a1[2][v9 + 1] = (__int64)a4;
  }
  else if ( v18 == v12 )
  {
    v17[v9] = (__int64)a4;
  }
  else
  {
    v19 = (__int64 **)v17[v9 + 1];
    v20 = *v19;
    v17[v9 + 1] = (__int64)*v19;
    if ( v20 != a4 )
      a1[2][v9 + 1] = *(_QWORD *)(a1[2][v9 + 1] + 8);
  }
  v21 = (__int64)a1[6];
  v22 = (__int64)a1[1];
  if ( v22 < 0 )
  {
    v24 = (unsigned __int64)a1[1] & 1 | ((unsigned __int64)v22 >> 1);
    v23 = (float)(int)v24 + (float)(int)v24;
  }
  else
  {
    v23 = (float)(int)v22;
  }
  if ( v21 < 0 )
    v25 = (float)(int)((_DWORD)a1[6] & 1 | ((unsigned __int64)v21 >> 1))
        + (float)(int)((_DWORD)a1[6] & 1 | ((unsigned __int64)v21 >> 1));
  else
    v25 = (float)(int)v21;
  if ( (float)(v23 / v25) > *((float *)a1 + 14) )
  {
    try
    {
      std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Init();
      v27 = *a1;
      if ( (__int64 *)*v27 != v27 )
      {
        v28 = v27[1];
        do
        {
          v29 = **a1;
          std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Insert<std::pair<_GUID const,unsigned short> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>>(
            a1,
            v32,
            v29 + 16,
            v29);
        }
        while ( v29 != v28 );
      }
    }
    catch ( ... )
    {
      iter = (_QWORD *)std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Make_iter(
                         v26,
                         &v31,
                         v31);
      std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::erase(
        a1,
        v32,
        *iter);
      throw;
    }
  }
  *(_QWORD *)a2 = a4;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x180008680  mov     rax, rsp
0x180008683  mov     [rax+10h], rbx
0x180008687  mov     [rax+18h], rsi
0x18000868b  mov     [rax+20h], r9
0x18000868f  mov     [rax+8], rcx
0x180008693  push    rdi
0x180008694  push    r14
0x180008696  push    r15
0x180008698  sub     rsp, 40h
0x18000869c  mov     rbx, r9
0x18000869f  mov     r15, r8
0x1800086a2  mov     r14, rdx
0x1800086a5  mov     rsi, rcx
0x1800086a8  mov     rdx, r8
0x1800086ab  call    ?_Hashval@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEBA_KAEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Hashval(_GUID const &)
0x1800086b0  mov     r9, rax
0x1800086b3  add     r9, r9
0x1800086b6  mov     rdi, [rsi+10h]
0x1800086ba  mov     rdx, [rdi+r9*8]
0x1800086be  cmp     rdx, [rsi]
0x1800086c1  jnz     short loc_1800086C8
0x1800086c3  mov     rdi, [rsi]
0x1800086c6  jmp     short loc_1800086D0
0x1800086c8  mov     rdi, [rdi+r9*8+8]
0x1800086cd  mov     rdi, [rdi]
0x1800086d0  cmp     rdi, rdx
0x1800086d3  jz      short loc_18000873C
0x1800086d5  mov     rcx, [rdi+8]
0x1800086d9  mov     rdi, rcx
0x1800086dc  mov     rax, [r15]
0x1800086df  cmp     rax, [rcx+10h]
0x1800086e3  jnz     short loc_1800086D0
0x1800086e5  mov     rax, [r15+8]
0x1800086e9  cmp     rax, [rcx+18h]
0x1800086ed  jnz     short loc_1800086D0
0x1800086ef  mov     rax, [rcx+10h]
0x1800086f3  cmp     rax, [r15]
0x1800086f6  jnz     short loc_180008739
0x1800086f8  mov     rax, [rcx+18h]
0x1800086fc  cmp     rax, [r15+8]
0x180008700  jnz     short loc_180008739
0x180008702  cmp     rbx, [rsi]
0x180008705  jz      short loc_180008729
0x180008707  mov     rcx, [rbx+8]
0x18000870b  mov     rax, [rbx]
0x18000870e  mov     [rcx], rax
0x180008711  mov     rcx, [rbx]
0x180008714  mov     rax, [rbx+8]
0x180008718  mov     [rcx+8], rax
0x18000871c  mov     rcx, rbx
0x18000871f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008725  dec     qword ptr [rsi+8]
0x180008729  mov     [r14], rdi
0x18000872c  mov     byte ptr [r14+8], 0
0x180008731  mov     rax, r14
0x180008734  jmp     loc_18000887D
0x180008739  mov     rdi, [rcx]
0x18000873c  mov     [rsp+58h+var_38], rbx
0x180008741  mov     rdx, [rbx]
0x180008744  cmp     rdi, rdx
0x180008747  jz      short loc_180008776
0x180008749  mov     rax, [rbx+8]
0x18000874d  mov     [rax], rdx
0x180008750  mov     rax, [rdx+8]
0x180008754  mov     [rax], rdi
0x180008757  mov     rax, [rdi+8]
0x18000875b  mov     [rax], rbx
0x18000875e  mov     rcx, [rdi+8]
0x180008762  mov     rax, [rdx+8]
0x180008766  mov     [rdi+8], rax
0x18000876a  mov     rax, [rbx+8]
0x18000876e  mov     [rdx+8], rax
0x180008772  mov     [rbx+8], rcx
0x180008776  mov     rdx, [rsi+10h]
0x18000877a  mov     rax, [rdx+r9*8]
0x18000877e  cmp     rax, [rsi]
0x180008781  jnz     short loc_180008792
0x180008783  mov     [rdx+r9*8], rbx
0x180008787  mov     rax, [rsi+10h]
0x18000878b  mov     [rax+r9*8+8], rbx
0x180008790  jmp     short loc_1800087C1
0x180008792  cmp     rax, rdi
0x180008795  jnz     short loc_18000879D
0x180008797  mov     [rdx+r9*8], rbx
0x18000879b  jmp     short loc_1800087C1
0x18000879d  mov     rax, [rdx+r9*8+8]
0x1800087a2  mov     rcx, [rax]
0x1800087a5  mov     [rdx+r9*8+8], rcx
0x1800087aa  cmp     rcx, rbx
0x1800087ad  jz      short loc_1800087C1
0x1800087af  mov     rdx, [rsi+10h]
0x1800087b3  mov     rax, [rdx+r9*8+8]
0x1800087b8  mov     rcx, [rax+8]
0x1800087bc  mov     [rdx+r9*8+8], rcx
0x1800087c1  mov     rdx, [rsi+30h]
0x1800087c5  mov     rcx, [rsi+8]
0x1800087c9  xorps   xmm0, xmm0
0x1800087cc  test    rcx, rcx
0x1800087cf  js      short loc_1800087D8
0x1800087d1  cvtsi2ss xmm0, rcx
0x1800087d6  jmp     short loc_1800087ED
0x1800087d8  mov     rax, rcx
0x1800087db  shr     rax, 1
0x1800087de  and     ecx, 1
0x1800087e1  or      rax, rcx
0x1800087e4  cvtsi2ss xmm0, rax
0x1800087e9  addss   xmm0, xmm0
0x1800087ed  xorps   xmm1, xmm1
0x1800087f0  test    rdx, rdx
0x1800087f3  js      short loc_1800087FC
0x1800087f5  cvtsi2ss xmm1, rdx
0x1800087fa  jmp     short loc_180008814
0x1800087fc  mov     rcx, rdx
0x1800087ff  shr     rcx, 1
0x180008802  mov     rax, rdx
0x180008805  and     eax, 1
0x180008808  or      rcx, rax
0x18000880b  cvtsi2ss xmm1, rcx
0x180008810  addss   xmm1, xmm1
0x180008814  divss   xmm0, xmm1
0x180008818  comiss  xmm0, dword ptr [rsi+38h]
0x18000881c  jbe     short loc_180008872
0x18000881e  cmp     rdx, 200h
0x180008825  jnb     short loc_18000882D
0x180008827  shl     rdx, 3
0x18000882b  jmp     short loc_18000883F
0x18000882d  mov     rax, 0FFFFFFFFFFFFFFFh
0x180008837  cmp     rdx, rax
0x18000883a  jnb     short loc_18000883F
0x18000883c  add     rdx, rdx
0x18000883f  mov     rcx, rsi
0x180008842  call    ?_Init@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Init(unsigned __int64)
0x180008847  mov     rax, [rsi]
0x18000884a  cmp     [rax], rax
0x18000884d  jz      short loc_180008872
0x18000884f  mov     r15, [rax+8]
0x180008853  mov     rdi, [rsi]
0x180008856  mov     rdi, [rdi]
0x180008859  lea     r8, [rdi+10h]
0x18000885d  mov     r9, rdi
0x180008860  lea     rdx, [rsp+58h+var_30]
0x180008865  mov     rcx, rsi
0x180008868  call    ??$_Insert@AEAU?$pair@$$CBU_GUID@@G@std@@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@$$CBU_GUID@@G@1@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Insert<std::pair<_GUID const,ushort> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>(std::pair<_GUID const,ushort> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>)
0x18000886d  cmp     rdi, r15
0x180008870  jnz     short loc_180008853
0x180008872  mov     [r14], rbx
0x180008875  mov     byte ptr [r14+8], 1
0x18000887a  mov     rax, r14
0x18000887d  mov     rbx, [rsp+58h+arg_8]
0x180008882  mov     rsi, [rsp+58h+arg_10]
0x180008887  add     rsp, 40h
0x18000888b  pop     r15
0x18000888d  pop     r14
0x18000888f  pop     rdi
0x180008890  retn
```
