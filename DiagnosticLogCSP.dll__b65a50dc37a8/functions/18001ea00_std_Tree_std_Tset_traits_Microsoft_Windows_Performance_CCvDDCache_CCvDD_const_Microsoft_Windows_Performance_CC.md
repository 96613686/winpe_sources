# std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert<0,0>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)

- ea: `0x18001ea00`
- end: `0x18001ebb8`
- name: `??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020a14`

## callees

- `0x180001bb4`
- `0x18001138c`
- `0x180011618`
- `0x18001ea00`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert<0,0>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v6; // r15
  __int64 v7; // r13
  unsigned int v8; // edi
  __int64 inserted; // r11
  __int64 v10; // r9
  char v11; // bp
  __int64 v12; // r10
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // eax
  char *v16; // rcx
  char *v17; // rax
  signed __int64 v18; // rcx
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // edx
  unsigned int v24; // edx
  char *v25; // rcx
  _QWORD *v26; // rax
  signed __int64 v27; // rcx
  int v28; // r8d
  int v29; // edx
  __int64 *v30; // rax
  __int64 *v32; // [rsp+20h] [rbp-38h] BYREF
  __int64 v33; // [rsp+28h] [rbp-30h]

  v6 = *a1;
  v7 = *(_QWORD *)(*a1 + 8);
  v8 = 0;
  inserted = *a1;
  v10 = v7;
  v11 = 1;
  if ( !*(_BYTE *)(v7 + 25) )
  {
    v12 = *a3;
    do
    {
      v7 = v10;
      v13 = *(_QWORD *)(v10 + 32);
      v14 = *(_DWORD *)(v13 + 132);
      if ( v14 < *(_DWORD *)(v12 + 132) )
        goto LABEL_16;
      if ( v14 > *(_DWORD *)(v12 + 132) )
        goto LABEL_15;
      v15 = *(_DWORD *)(v13 + 136);
      if ( v15 < *(_DWORD *)(v12 + 136) )
        goto LABEL_16;
      if ( v15 > *(_DWORD *)(v12 + 136) )
        goto LABEL_15;
      v16 = (char *)(v12 + 32);
      if ( *(_QWORD *)(v12 + 56) > 7u )
        v16 = *(char **)v16;
      v17 = (char *)(v13 + 32);
      if ( *(_QWORD *)(v13 + 56) > 7u )
        v17 = *(char **)v17;
      v18 = v16 - v17;
      do
      {
        v19 = *(unsigned __int16 *)&v17[v18];
        v20 = *(unsigned __int16 *)v17 - v19;
        if ( v20 )
          break;
        v17 += 2;
      }
      while ( v19 );
      if ( v20 < 0 )
      {
LABEL_16:
        v8 = 0;
        v10 = *(_QWORD *)(v10 + 16);
      }
      else
      {
LABEL_15:
        v8 = 1;
        inserted = v10;
        v10 = *(_QWORD *)v10;
      }
    }
    while ( !*(_BYTE *)(v10 + 25) );
  }
  if ( *(_BYTE *)(inserted + 25) )
    goto LABEL_32;
  v21 = *(_QWORD *)(inserted + 32);
  v22 = *a3;
  v23 = *(_DWORD *)(*a3 + 132);
  if ( v23 < *(_DWORD *)(v21 + 132) )
    goto LABEL_32;
  if ( v23 > *(_DWORD *)(v21 + 132) )
    goto LABEL_31;
  v24 = *(_DWORD *)(v22 + 136);
  if ( v24 < *(_DWORD *)(v21 + 136) )
    goto LABEL_32;
  if ( v24 > *(_DWORD *)(v21 + 136) )
    goto LABEL_31;
  v25 = (char *)(v21 + 32);
  if ( *((_QWORD *)v25 + 3) > 7u )
    v25 = *(char **)v25;
  v26 = (_QWORD *)(v22 + 32);
  if ( v26[3] > 7u )
    v26 = (_QWORD *)*v26;
  v27 = v25 - (char *)v26;
  do
  {
    v28 = *(unsigned __int16 *)((char *)v26 + v27);
    v29 = *(unsigned __int16 *)v26 - v28;
    if ( v29 )
      break;
    v26 = (_QWORD *)((char *)v26 + 2);
  }
  while ( v28 );
  if ( v29 < 0 )
  {
LABEL_32:
    if ( a1[1] == 0x666666666666666LL )
      std::_Throw_tree_length_error();
    v32 = a1;
    v33 = 0;
    v30 = (__int64 *)operator new(0x28u);
    v30[4] = *a3;
    *v30 = v6;
    v30[1] = v6;
    v30[2] = v6;
    *((_WORD *)v30 + 12) = 0;
    v32 = (__int64 *)v7;
    v33 = v8;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                 a1,
                 &v32,
                 v30);
  }
  else
  {
LABEL_31:
    v11 = 0;
  }
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v11;
  return a2;
}

```

## disassembly

```asm
0x18001ea00  mov     [rsp+arg_8], rbx
0x18001ea05  mov     [rsp+arg_10], rbp
0x18001ea0a  push    rdi
0x18001ea0b  push    r12
0x18001ea0d  push    r13
0x18001ea0f  push    r14
0x18001ea11  push    r15
0x18001ea13  sub     rsp, 30h
0x18001ea17  mov     r12, r8
0x18001ea1a  mov     rbx, rdx
0x18001ea1d  mov     r14, rcx
0x18001ea20  mov     r15, [rcx]
0x18001ea23  mov     r13, [r15+8]
0x18001ea27  xor     edi, edi
0x18001ea29  xor     eax, eax
0x18001ea2b  mov     [rsp+58h+arg_0], rax
0x18001ea30  mov     r11, r15
0x18001ea33  mov     r9, r13
0x18001ea36  lea     ebp, [rdi+1]
0x18001ea39  cmp     [r13+19h], al
0x18001ea3d  jnz     short loc_18001EABB
0x18001ea3f  mov     r10, [r8]
0x18001ea42  mov     r13, r9
0x18001ea45  mov     rdx, [r9+20h]
0x18001ea49  mov     eax, [rdx+84h]
0x18001ea4f  cmp     eax, [r10+84h]
0x18001ea56  jb      short loc_18001EAAE
0x18001ea58  ja      short loc_18001EAA4
0x18001ea5a  mov     eax, [rdx+88h]
0x18001ea60  cmp     eax, [r10+88h]
0x18001ea67  jb      short loc_18001EAAE
0x18001ea69  ja      short loc_18001EAA4
0x18001ea6b  lea     rcx, [r10+20h]
0x18001ea6f  cmp     qword ptr [rcx+18h], 7
0x18001ea74  jbe     short loc_18001EA79
0x18001ea76  mov     rcx, [rcx]
0x18001ea79  lea     rax, [rdx+20h]
0x18001ea7d  cmp     qword ptr [rax+18h], 7
0x18001ea82  jbe     short loc_18001EA87
0x18001ea84  mov     rax, [rax]
0x18001ea87  sub     rcx, rax
0x18001ea8a  movzx   r8d, word ptr [rax]
0x18001ea8e  movzx   edx, word ptr [rax+rcx]
0x18001ea92  sub     r8d, edx
0x18001ea95  jnz     short loc_18001EA9F
0x18001ea97  add     rax, 2
0x18001ea9b  test    edx, edx
0x18001ea9d  jnz     short loc_18001EA8A
0x18001ea9f  test    r8d, r8d
0x18001eaa2  js      short loc_18001EAAE
0x18001eaa4  mov     edi, ebp
0x18001eaa6  mov     r11, r9
0x18001eaa9  mov     r9, [r9]
0x18001eaac  jmp     short loc_18001EAB4
0x18001eaae  xor     edi, edi
0x18001eab0  mov     r9, [r9+10h]
0x18001eab4  cmp     byte ptr [r9+19h], 0
0x18001eab9  jz      short loc_18001EA42
0x18001eabb  cmp     byte ptr [r11+19h], 0
0x18001eac0  jnz     short loc_18001EB28
0x18001eac2  mov     rcx, [r11+20h]
0x18001eac6  mov     rax, [r12]
0x18001eaca  mov     edx, [rax+84h]
0x18001ead0  cmp     edx, [rcx+84h]
0x18001ead6  jb      short loc_18001EB28
0x18001ead8  ja      short loc_18001EB23
0x18001eada  mov     edx, [rax+88h]
0x18001eae0  cmp     edx, [rcx+88h]
0x18001eae6  jb      short loc_18001EB28
0x18001eae8  ja      short loc_18001EB23
0x18001eaea  add     rcx, 20h ; ' '
0x18001eaee  cmp     qword ptr [rcx+18h], 7
0x18001eaf3  jbe     short loc_18001EAF8
0x18001eaf5  mov     rcx, [rcx]
0x18001eaf8  add     rax, 20h ; ' '
0x18001eafc  cmp     qword ptr [rax+18h], 7
0x18001eb01  jbe     short loc_18001EB06
0x18001eb03  mov     rax, [rax]
0x18001eb06  sub     rcx, rax
0x18001eb09  movzx   edx, word ptr [rax]
0x18001eb0c  movzx   r8d, word ptr [rax+rcx]
0x18001eb11  sub     edx, r8d
0x18001eb14  jnz     short loc_18001EB1F
0x18001eb16  add     rax, 2
0x18001eb1a  test    r8d, r8d
0x18001eb1d  jnz     short loc_18001EB09
0x18001eb1f  test    edx, edx
0x18001eb21  js      short loc_18001EB28
0x18001eb23  xor     bpl, bpl
0x18001eb26  jmp     short loc_18001EB8F
0x18001eb28  mov     rax, 666666666666666h
0x18001eb32  cmp     [r14+8], rax
0x18001eb36  jz      short loc_18001EBB2
0x18001eb38  mov     [rsp+58h+var_38], r14
0x18001eb3d  mov     [rsp+58h+var_30], 0
0x18001eb46  mov     ecx, 28h ; '('; Size
0x18001eb4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001eb50  mov     r8, rax
0x18001eb53  mov     rax, [r12]
0x18001eb57  mov     [r8+20h], rax
0x18001eb5b  mov     [r8], r15
0x18001eb5e  mov     [r8+8], r15
0x18001eb62  mov     [r8+10h], r15
0x18001eb66  mov     word ptr [r8+18h], 0
0x18001eb6d  mov     [rsp+58h+var_38], r13
0x18001eb72  mov     dword ptr [rsp+58h+var_30], edi
0x18001eb76  mov     rax, [rsp+58h+arg_0]
0x18001eb7b  mov     dword ptr [rsp+58h+var_30+4], eax
0x18001eb7f  lea     rdx, [rsp+58h+var_38]
0x18001eb84  mov     rcx, r14
0x18001eb87  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18001eb8c  mov     r11, rax
0x18001eb8f  mov     [rbx], r11
0x18001eb92  mov     [rbx+8], bpl
0x18001eb96  mov     rax, rbx
0x18001eb99  mov     rbx, [rsp+58h+arg_8]
0x18001eb9e  mov     rbp, [rsp+58h+arg_10]
0x18001eba3  add     rsp, 30h
0x18001eba7  pop     r15
0x18001eba9  pop     r14
0x18001ebab  pop     r13
0x18001ebad  pop     r12
0x18001ebaf  pop     rdi
0x18001ebb0  retn
0x18001ebb2  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
