# std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Insert_nohint<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *>(bool,std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)

- ea: `0x180020694`
- end: `0x180020809`
- name: `??$_Insert_nohint@AEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@1@@Z`
- size: `373`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020810`

## callees

- `0x1800203f8`
- `0x180020694`
- `0x180020eb0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800207cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800207ee`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800207cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800207ee`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Insert_nohint<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>,void *> *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD *v7; // rax
  __int64 v8; // r11
  __int64 v9; // rbx
  char v10; // al
  __int64 *v11; // r11
  char v12; // si
  __int64 v13; // r11
  __int64 v14; // rcx
  __int64 result; // rax
  __int64 j; // rax
  __int64 i; // rax
  __int64 v18; // rcx
  _QWORD *v19; // r11
  __int64 v20; // rsi
  int v21; // [rsp+20h] [rbp-38h]
  __int64 v22; // [rsp+60h] [rbp+8h] BYREF

  v22 = a1;
  try
  {
    v7 = (_QWORD *)CommonFileMapping::m_mapSingleton;
    v8 = *(_QWORD *)(CommonFileMapping::m_mapSingleton + 8);
    if ( *(_BYTE *)(v8 + 25) )
    {
      v12 = 1;
      v13 = CommonFileMapping::m_mapSingleton;
      v9 = CommonFileMapping::m_mapSingleton;
    }
    else
    {
      do
      {
        v9 = v8;
        v10 = std::less<tagSFILENAMEwithATTRIBUTE>::operator()(a1, a4, v8 + 32);
        v12 = v10;
        if ( v10 )
          v8 = *v11;
        else
          v8 = v11[2];
      }
      while ( !*(_BYTE *)(v8 + 25) );
      v13 = v9;
      if ( !v10 )
      {
LABEL_25:
        if ( (unsigned __int8)std::less<tagSFILENAMEwithATTRIBUTE>::operator()(a1, v9 + 32, a4) )
        {
          *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Insert_at<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>,void *> *>(
                             v18,
                             &v22,
                             v12,
                             v19,
                             v21,
                             a5);
          *(_BYTE *)(a2 + 8) = 1;
          return a2;
        }
        else
        {
          v20 = a5;
          if ( *(_QWORD *)(a5 + 56) >= 8u )
            operator delete(*(void **)(a5 + 32));
          *(_QWORD *)(v20 + 56) = 7;
          *(_QWORD *)(v20 + 48) = 0;
          *(_WORD *)(v20 + 32) = 0;
          operator delete((void *)v20);
          *(_QWORD *)a2 = v9;
          *(_BYTE *)(a2 + 8) = 0;
          return a2;
        }
      }
      v7 = (_QWORD *)CommonFileMapping::m_mapSingleton;
    }
    if ( v13 == *v7 )
    {
      *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Insert_at<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>,void *> *>(
                         a1,
                         &v22,
                         1,
                         (_QWORD *)v13,
                         v21,
                         a5);
      *(_BYTE *)(a2 + 8) = 1;
      return a2;
    }
    if ( *(_BYTE *)(v13 + 25) )
    {
      v9 = *(_QWORD *)(v13 + 16);
    }
    else if ( *(_BYTE *)(*(_QWORD *)v13 + 25LL) )
    {
      for ( i = *(_QWORD *)(v13 + 8); !*(_BYTE *)(i + 25) && v9 == *(_QWORD *)i; i = *(_QWORD *)(i + 8) )
        v9 = i;
      if ( !*(_BYTE *)(v9 + 25) )
        v9 = i;
    }
    else
    {
      v9 = *(_QWORD *)v13;
      for ( j = *(_QWORD *)(*(_QWORD *)v13 + 16LL); !*(_BYTE *)(j + 25); j = *(_QWORD *)(v9 + 16) )
        v9 = *(_QWORD *)(v9 + 16);
    }
    goto LABEL_25;
  }
  catch ( ... )
  {
    std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Destroy_if_not_nil(
      v14,
      a5);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180020694  mov     [rsp+arg_0], rcx
0x180020699  push    rbx
0x18002069a  push    rsi
0x18002069b  push    rdi
0x18002069c  push    r14
0x18002069e  sub     rsp, 38h
0x1800206a2  mov     r14, r9
0x1800206a5  mov     rdi, rdx
0x1800206a8  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800206af  mov     r11, [rax+8]
0x1800206b3  cmp     byte ptr [r11+19h], 0
0x1800206b8  jnz     short loc_1800206F4
0x1800206ba  mov     rbx, r11
0x1800206bd  lea     r8, [r11+20h]
0x1800206c1  mov     rdx, r14
0x1800206c4  call    ??R?$less@UtagSFILENAMEwithATTRIBUTE@@@std@@QEBA_NAEBUtagSFILENAMEwithATTRIBUTE@@0@Z; std::less<tagSFILENAMEwithATTRIBUTE>::operator()(tagSFILENAMEwithATTRIBUTE const &,tagSFILENAMEwithATTRIBUTE const &)
0x1800206c9  mov     sil, al
0x1800206cc  test    al, al
0x1800206ce  jz      short loc_1800206D5
0x1800206d0  mov     r11, [r11]
0x1800206d3  jmp     short loc_1800206D9
0x1800206d5  mov     r11, [r11+10h]
0x1800206d9  cmp     byte ptr [r11+19h], 0
0x1800206de  jz      short loc_1800206BA
0x1800206e0  mov     r11, rbx
0x1800206e3  test    al, al
0x1800206e5  jz      loc_180020780
0x1800206eb  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800206f2  jmp     short loc_1800206FD
0x1800206f4  mov     sil, 1
0x1800206f7  mov     r11, rax
0x1800206fa  mov     rbx, rax
0x1800206fd  cmp     r11, [rax]
0x180020700  jnz     short loc_180020731
0x180020702  mov     rax, [rsp+58h+arg_20]
0x18002070a  mov     [rsp+58h+var_30], rax
0x18002070f  mov     r9, r11
0x180020712  mov     r8b, 1
0x180020715  lea     rdx, [rsp+58h+arg_0]
0x18002071a  call    ??$_Insert_at@AEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@1@AEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@1@1@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Insert_at<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *>(bool,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *,std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)
0x18002071f  mov     rax, [rax]
0x180020722  mov     [rdi], rax
0x180020725  mov     byte ptr [rdi+8], 1
0x180020729  mov     rax, rdi
0x18002072c  jmp     loc_1800207FE
0x180020731  cmp     byte ptr [r11+19h], 0
0x180020736  jz      short loc_18002073E
0x180020738  mov     rbx, [r11+10h]
0x18002073c  jmp     short loc_180020780
0x18002073e  mov     rax, [r11]
0x180020741  cmp     byte ptr [rax+19h], 0
0x180020745  jnz     short loc_180020760
0x180020747  mov     rbx, rax
0x18002074a  mov     rax, [rax+10h]
0x18002074e  jmp     short loc_180020758
0x180020750  mov     rbx, [rbx+10h]
0x180020754  mov     rax, [rbx+10h]
0x180020758  cmp     byte ptr [rax+19h], 0
0x18002075c  jz      short loc_180020750
0x18002075e  jmp     short loc_180020780
0x180020760  mov     rax, [r11+8]
0x180020764  jmp     short loc_180020772
0x180020766  cmp     rbx, [rax]
0x180020769  jnz     short loc_180020778
0x18002076b  mov     rbx, rax
0x18002076e  mov     rax, [rax+8]
0x180020772  cmp     byte ptr [rax+19h], 0
0x180020776  jz      short loc_180020766
0x180020778  cmp     byte ptr [rbx+19h], 0
0x18002077c  cmovz   rbx, rax
0x180020780  lea     rdx, [rbx+20h]
0x180020784  mov     r8, r14
0x180020787  call    ??R?$less@UtagSFILENAMEwithATTRIBUTE@@@std@@QEBA_NAEBUtagSFILENAMEwithATTRIBUTE@@0@Z; std::less<tagSFILENAMEwithATTRIBUTE>::operator()(tagSFILENAMEwithATTRIBUTE const &,tagSFILENAMEwithATTRIBUTE const &)
0x18002078c  test    al, al
0x18002078e  jz      short loc_1800207BC
0x180020790  mov     rax, [rsp+58h+arg_20]
0x180020798  mov     [rsp+58h+var_30], rax
0x18002079d  mov     r9, r11
0x1800207a0  mov     r8b, sil
0x1800207a3  lea     rdx, [rsp+58h+arg_0]
0x1800207a8  call    ??$_Insert_at@AEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@1@AEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@1@1@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Insert_at<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *>(bool,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *,std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)
0x1800207ad  mov     rax, [rax]
0x1800207b0  mov     [rdi], rax
0x1800207b3  mov     byte ptr [rdi+8], 1
0x1800207b7  mov     rax, rdi
0x1800207ba  jmp     short loc_1800207FE
0x1800207bc  mov     rsi, [rsp+58h+arg_20]
0x1800207c4  cmp     qword ptr [rsi+38h], 8
0x1800207c9  jb      short loc_1800207D5
0x1800207cb  mov     rcx, [rsi+20h]
0x1800207cf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800207d5  mov     qword ptr [rsi+38h], 7
0x1800207dd  mov     qword ptr [rsi+30h], 0
0x1800207e5  xor     eax, eax
0x1800207e7  mov     [rsi+20h], ax
0x1800207eb  mov     rcx, rsi
0x1800207ee  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800207f4  mov     [rdi], rbx
0x1800207f7  mov     byte ptr [rdi+8], 0
0x1800207fb  mov     rax, rdi
0x1800207fe  add     rsp, 38h
0x180020802  pop     r14
0x180020804  pop     rdi
0x180020805  pop     rsi
0x180020806  pop     rbx
0x180020807  retn
```
