# std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert<0,0>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)

- ea: `0x18000cd80`
- end: `0x18000cf37`
- name: `??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000edc4`

## callees

- `0x1800018a0`
- `0x18000cd80`
- `0x180015920`
- `0x180015b50`

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
0x18000cd80  mov     [rsp+arg_8], rbx
0x18000cd85  mov     [rsp+arg_10], rbp
0x18000cd8a  push    rdi
0x18000cd8b  push    r12
0x18000cd8d  push    r13
0x18000cd8f  push    r14
0x18000cd91  push    r15
0x18000cd93  sub     rsp, 30h
0x18000cd97  mov     r12, r8
0x18000cd9a  mov     rbx, rdx
0x18000cd9d  mov     r14, rcx
0x18000cda0  mov     r15, [rcx]
0x18000cda3  mov     r13, [r15+8]
0x18000cda7  xor     edi, edi
0x18000cda9  xor     eax, eax
0x18000cdab  mov     [rsp+58h+arg_0], rax
0x18000cdb0  mov     r11, r15
0x18000cdb3  mov     r9, r13
0x18000cdb6  lea     ebp, [rdi+1]
0x18000cdb9  cmp     [r13+19h], al
0x18000cdbd  jnz     short loc_18000CE3B
0x18000cdbf  mov     r10, [r8]
0x18000cdc2  mov     r13, r9
0x18000cdc5  mov     rdx, [r9+20h]
0x18000cdc9  mov     eax, [rdx+84h]
0x18000cdcf  cmp     eax, [r10+84h]
0x18000cdd6  jb      short loc_18000CE2E
0x18000cdd8  ja      short loc_18000CE24
0x18000cdda  mov     eax, [rdx+88h]
0x18000cde0  cmp     eax, [r10+88h]
0x18000cde7  jb      short loc_18000CE2E
0x18000cde9  ja      short loc_18000CE24
0x18000cdeb  lea     rcx, [r10+20h]
0x18000cdef  cmp     qword ptr [rcx+18h], 7
0x18000cdf4  jbe     short loc_18000CDF9
0x18000cdf6  mov     rcx, [rcx]
0x18000cdf9  lea     rax, [rdx+20h]
0x18000cdfd  cmp     qword ptr [rax+18h], 7
0x18000ce02  jbe     short loc_18000CE07
0x18000ce04  mov     rax, [rax]
0x18000ce07  sub     rcx, rax
0x18000ce0a  movzx   r8d, word ptr [rax]
0x18000ce0e  movzx   edx, word ptr [rax+rcx]
0x18000ce12  sub     r8d, edx
0x18000ce15  jnz     short loc_18000CE1F
0x18000ce17  add     rax, 2
0x18000ce1b  test    edx, edx
0x18000ce1d  jnz     short loc_18000CE0A
0x18000ce1f  test    r8d, r8d
0x18000ce22  js      short loc_18000CE2E
0x18000ce24  mov     edi, ebp
0x18000ce26  mov     r11, r9
0x18000ce29  mov     r9, [r9]
0x18000ce2c  jmp     short loc_18000CE34
0x18000ce2e  xor     edi, edi
0x18000ce30  mov     r9, [r9+10h]
0x18000ce34  cmp     byte ptr [r9+19h], 0
0x18000ce39  jz      short loc_18000CDC2
0x18000ce3b  cmp     byte ptr [r11+19h], 0
0x18000ce40  jnz     short loc_18000CEA8
0x18000ce42  mov     rcx, [r11+20h]
0x18000ce46  mov     rax, [r12]
0x18000ce4a  mov     edx, [rax+84h]
0x18000ce50  cmp     edx, [rcx+84h]
0x18000ce56  jb      short loc_18000CEA8
0x18000ce58  ja      short loc_18000CEA3
0x18000ce5a  mov     edx, [rax+88h]
0x18000ce60  cmp     edx, [rcx+88h]
0x18000ce66  jb      short loc_18000CEA8
0x18000ce68  ja      short loc_18000CEA3
0x18000ce6a  add     rcx, 20h ; ' '
0x18000ce6e  cmp     qword ptr [rcx+18h], 7
0x18000ce73  jbe     short loc_18000CE78
0x18000ce75  mov     rcx, [rcx]
0x18000ce78  add     rax, 20h ; ' '
0x18000ce7c  cmp     qword ptr [rax+18h], 7
0x18000ce81  jbe     short loc_18000CE86
0x18000ce83  mov     rax, [rax]
0x18000ce86  sub     rcx, rax
0x18000ce89  movzx   edx, word ptr [rax]
0x18000ce8c  movzx   r8d, word ptr [rax+rcx]
0x18000ce91  sub     edx, r8d
0x18000ce94  jnz     short loc_18000CE9F
0x18000ce96  add     rax, 2
0x18000ce9a  test    r8d, r8d
0x18000ce9d  jnz     short loc_18000CE89
0x18000ce9f  test    edx, edx
0x18000cea1  js      short loc_18000CEA8
0x18000cea3  xor     bpl, bpl
0x18000cea6  jmp     short loc_18000CF0F
0x18000cea8  mov     rax, 666666666666666h
0x18000ceb2  cmp     [r14+8], rax
0x18000ceb6  jz      short loc_18000CF31
0x18000ceb8  mov     [rsp+58h+var_38], r14
0x18000cebd  mov     [rsp+58h+var_30], 0
0x18000cec6  mov     ecx, 28h ; '('; Size
0x18000cecb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ced0  mov     r8, rax
0x18000ced3  mov     rax, [r12]
0x18000ced7  mov     [r8+20h], rax
0x18000cedb  mov     [r8], r15
0x18000cede  mov     [r8+8], r15
0x18000cee2  mov     [r8+10h], r15
0x18000cee6  mov     word ptr [r8+18h], 0
0x18000ceed  mov     [rsp+58h+var_38], r13
0x18000cef2  mov     dword ptr [rsp+58h+var_30], edi
0x18000cef6  mov     rax, [rsp+58h+arg_0]
0x18000cefb  mov     dword ptr [rsp+58h+var_30+4], eax
0x18000ceff  lea     rdx, [rsp+58h+var_38]
0x18000cf04  mov     rcx, r14
0x18000cf07  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18000cf0c  mov     r11, rax
0x18000cf0f  mov     [rbx], r11
0x18000cf12  mov     [rbx+8], bpl
0x18000cf16  mov     rax, rbx
0x18000cf19  mov     rbx, [rsp+58h+arg_8]
0x18000cf1e  mov     rbp, [rsp+58h+arg_10]
0x18000cf23  add     rsp, 30h
0x18000cf27  pop     r15
0x18000cf29  pop     r14
0x18000cf2b  pop     r13
0x18000cf2d  pop     r12
0x18000cf2f  pop     rdi
0x18000cf30  retn
0x18000cf31  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
