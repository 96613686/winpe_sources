# std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert<0,0>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)

- ea: `0x18001da68`
- end: `0x18001dc1f`
- name: `??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f9e4`

## callees

- `0x180001b84`
- `0x180010b08`
- `0x180010d94`
- `0x18001da68`

## pseudocode

```c
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
                 &v32);
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
0x18001da68  mov     [rsp+arg_8], rbx
0x18001da6d  mov     [rsp+arg_10], rbp
0x18001da72  push    rdi
0x18001da73  push    r12
0x18001da75  push    r13
0x18001da77  push    r14
0x18001da79  push    r15
0x18001da7b  sub     rsp, 30h
0x18001da7f  mov     r12, r8
0x18001da82  mov     rbx, rdx
0x18001da85  mov     r14, rcx
0x18001da88  mov     r15, [rcx]
0x18001da8b  mov     r13, [r15+8]
0x18001da8f  xor     edi, edi
0x18001da91  xor     eax, eax
0x18001da93  mov     [rsp+58h+arg_0], rax
0x18001da98  mov     r11, r15
0x18001da9b  mov     r9, r13
0x18001da9e  lea     ebp, [rdi+1]
0x18001daa1  cmp     [r13+19h], al
0x18001daa5  jnz     short loc_18001DB23
0x18001daa7  mov     r10, [r8]
0x18001daaa  mov     r13, r9
0x18001daad  mov     rdx, [r9+20h]
0x18001dab1  mov     eax, [rdx+84h]
0x18001dab7  cmp     eax, [r10+84h]
0x18001dabe  jb      short loc_18001DB16
0x18001dac0  ja      short loc_18001DB0C
0x18001dac2  mov     eax, [rdx+88h]
0x18001dac8  cmp     eax, [r10+88h]
0x18001dacf  jb      short loc_18001DB16
0x18001dad1  ja      short loc_18001DB0C
0x18001dad3  lea     rcx, [r10+20h]
0x18001dad7  cmp     qword ptr [rcx+18h], 7
0x18001dadc  jbe     short loc_18001DAE1
0x18001dade  mov     rcx, [rcx]
0x18001dae1  lea     rax, [rdx+20h]
0x18001dae5  cmp     qword ptr [rax+18h], 7
0x18001daea  jbe     short loc_18001DAEF
0x18001daec  mov     rax, [rax]
0x18001daef  sub     rcx, rax
0x18001daf2  movzx   r8d, word ptr [rax]
0x18001daf6  movzx   edx, word ptr [rax+rcx]
0x18001dafa  sub     r8d, edx
0x18001dafd  jnz     short loc_18001DB07
0x18001daff  add     rax, 2
0x18001db03  test    edx, edx
0x18001db05  jnz     short loc_18001DAF2
0x18001db07  test    r8d, r8d
0x18001db0a  js      short loc_18001DB16
0x18001db0c  mov     edi, ebp
0x18001db0e  mov     r11, r9
0x18001db11  mov     r9, [r9]
0x18001db14  jmp     short loc_18001DB1C
0x18001db16  xor     edi, edi
0x18001db18  mov     r9, [r9+10h]
0x18001db1c  cmp     byte ptr [r9+19h], 0
0x18001db21  jz      short loc_18001DAAA
0x18001db23  cmp     byte ptr [r11+19h], 0
0x18001db28  jnz     short loc_18001DB90
0x18001db2a  mov     rcx, [r11+20h]
0x18001db2e  mov     rax, [r12]
0x18001db32  mov     edx, [rax+84h]
0x18001db38  cmp     edx, [rcx+84h]
0x18001db3e  jb      short loc_18001DB90
0x18001db40  ja      short loc_18001DB8B
0x18001db42  mov     edx, [rax+88h]
0x18001db48  cmp     edx, [rcx+88h]
0x18001db4e  jb      short loc_18001DB90
0x18001db50  ja      short loc_18001DB8B
0x18001db52  add     rcx, 20h ; ' '
0x18001db56  cmp     qword ptr [rcx+18h], 7
0x18001db5b  jbe     short loc_18001DB60
0x18001db5d  mov     rcx, [rcx]
0x18001db60  add     rax, 20h ; ' '
0x18001db64  cmp     qword ptr [rax+18h], 7
0x18001db69  jbe     short loc_18001DB6E
0x18001db6b  mov     rax, [rax]
0x18001db6e  sub     rcx, rax
0x18001db71  movzx   edx, word ptr [rax]
0x18001db74  movzx   r8d, word ptr [rax+rcx]
0x18001db79  sub     edx, r8d
0x18001db7c  jnz     short loc_18001DB87
0x18001db7e  add     rax, 2
0x18001db82  test    r8d, r8d
0x18001db85  jnz     short loc_18001DB71
0x18001db87  test    edx, edx
0x18001db89  js      short loc_18001DB90
0x18001db8b  xor     bpl, bpl
0x18001db8e  jmp     short loc_18001DBF7
0x18001db90  mov     rax, 666666666666666h
0x18001db9a  cmp     [r14+8], rax
0x18001db9e  jz      short loc_18001DC19
0x18001dba0  mov     [rsp+58h+var_38], r14
0x18001dba5  mov     [rsp+58h+var_30], 0
0x18001dbae  mov     ecx, 28h ; '('; Size
0x18001dbb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dbb8  mov     r8, rax
0x18001dbbb  mov     rax, [r12]
0x18001dbbf  mov     [r8+20h], rax
0x18001dbc3  mov     [r8], r15
0x18001dbc6  mov     [r8+8], r15
0x18001dbca  mov     [r8+10h], r15
0x18001dbce  mov     word ptr [r8+18h], 0
0x18001dbd5  mov     [rsp+58h+var_38], r13
0x18001dbda  mov     dword ptr [rsp+58h+var_30], edi
0x18001dbde  mov     rax, [rsp+58h+arg_0]
0x18001dbe3  mov     dword ptr [rsp+58h+var_30+4], eax
0x18001dbe7  lea     rdx, [rsp+58h+var_38]
0x18001dbec  mov     rcx, r14
0x18001dbef  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18001dbf4  mov     r11, rax
0x18001dbf7  mov     [rbx], r11
0x18001dbfa  mov     [rbx+8], bpl
0x18001dbfe  mov     rax, rbx
0x18001dc01  mov     rbx, [rsp+58h+arg_8]
0x18001dc06  mov     rbp, [rsp+58h+arg_10]
0x18001dc0b  add     rsp, 30h
0x18001dc0f  pop     r15
0x18001dc11  pop     r14
0x18001dc13  pop     r13
0x18001dc15  pop     r12
0x18001dc17  pop     rdi
0x18001dc18  retn
0x18001dc19  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
