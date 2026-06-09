# std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ushort const *>>>)

- ea: `0x18000d0b8`
- end: `0x18000d37a`
- name: `?erase@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@2@V32@@Z`
- size: `706`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b214`
- `0x18000ce8c`
- `0x18000cfac`
- `0x180019890`

## callees

- `0x18000d0b8`
- `0x18000fb44`
- `0x1800197a4`
- `0x1800197f4`
- `0x18001983c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d34f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d34f`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::erase(
        __int64 **a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v5; // rsi
  _BYTE *v6; // r14
  _QWORD *v7; // r10
  _QWORD **v8; // r11
  _QWORD *v9; // rbp
  char v10; // r9
  _QWORD *i; // rbx
  _QWORD *v12; // r9
  __int64 *v13; // r8
  __int64 v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rax
  _BYTE *v17; // rdx
  _QWORD *v18; // rax
  char v19; // cl
  char v20; // r11
  _BYTE *v21; // rdx
  __int64 v22; // rcx
  __int64 *v23; // rax

  if ( *((_BYTE *)a3 + 25) )
    std::_Xout_of_range("invalid map/set<T> iterator");
  v5 = a3 + 2;
  v6 = a3;
  v7 = (_QWORD *)a3[2];
  v8 = (_QWORD **)(a3 + 1);
  v9 = a3;
  v10 = *((_BYTE *)v7 + 25);
  if ( v10 )
  {
    for ( i = *v8; !*((_BYTE *)i + 25) && a3 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
      a3 = i;
  }
  else
  {
    i = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<unsigned short const *>>::_Min(a3[2]);
  }
  if ( *(_BYTE *)(*(_QWORD *)v6 + 25LL) )
    goto LABEL_13;
  if ( v10 )
  {
    v7 = *(_QWORD **)v6;
LABEL_13:
    v12 = *v8;
    if ( !*((_BYTE *)v7 + 25) )
      v7[1] = v12;
    if ( (_BYTE *)(*a1)[1] == v6 )
    {
      (*a1)[1] = (__int64)v7;
    }
    else if ( (_BYTE *)*v12 == v6 )
    {
      *v12 = v7;
    }
    else
    {
      v12[2] = v7;
    }
    v13 = *a1;
    if ( (_BYTE *)**a1 == v6 )
    {
      if ( *((_BYTE *)v7 + 25) )
        v14 = (__int64)v12;
      else
        v14 = std::_Tree_val<std::_Tree_simple_types<unsigned short const *>>::_Min(v7);
      *v13 = v14;
    }
    if ( (_BYTE *)(*a1)[2] == v6 )
    {
      if ( *((_BYTE *)v7 + 25) )
      {
        v15 = v12;
      }
      else
      {
        v16 = v7[2];
        v15 = v7;
        while ( !*(_BYTE *)(v16 + 25) )
        {
          v15 = (_QWORD *)v15[2];
          v16 = v15[2];
        }
      }
      (*a1)[2] = (__int64)v15;
    }
    v17 = v9 + 3;
    goto LABEL_44;
  }
  v7 = (_QWORD *)i[2];
  if ( i == (_QWORD *)v6 )
    goto LABEL_13;
  *(_QWORD *)(*(_QWORD *)v6 + 8LL) = i;
  *i = *(_QWORD *)v6;
  if ( i == (_QWORD *)*v5 )
  {
    v12 = i;
  }
  else
  {
    v12 = (_QWORD *)i[1];
    if ( !*((_BYTE *)v7 + 25) )
      v7[1] = v12;
    *v12 = v7;
    i[2] = *v5;
    *(_QWORD *)(*v5 + 8LL) = i;
  }
  if ( (_BYTE *)(*a1)[1] == v6 )
  {
    (*a1)[1] = (__int64)i;
  }
  else
  {
    v18 = *v8;
    if ( (_BYTE *)**v8 == v6 )
      *v18 = i;
    else
      v18[2] = i;
  }
  v17 = v6 + 24;
  i[1] = *v8;
  v19 = *((_BYTE *)i + 24);
  *((_BYTE *)i + 24) = v6[24];
  v6[24] = v19;
LABEL_44:
  v20 = 1;
  if ( *v17 != 1 )
    goto LABEL_67;
  while ( v7 != (_QWORD *)(*a1)[1] && *((_BYTE *)v7 + 24) == v20 )
  {
    v21 = (_BYTE *)*v12;
    if ( v7 == (_QWORD *)*v12 )
    {
      v21 = (_BYTE *)v12[2];
      if ( !v21[24] )
      {
        v21[24] = v20;
        *((_BYTE *)v12 + 24) = 0;
        std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Lrotate(a1);
        v21 = (_BYTE *)v12[2];
      }
      if ( !v21[25] )
      {
        if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) != v20 || *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) != v20 )
        {
          if ( *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) == v20 )
          {
            *(_BYTE *)(*(_QWORD *)v21 + 24LL) = v20;
            v21[24] = 0;
            std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Rrotate(
              a1,
              v21);
            v21 = (_BYTE *)v12[2];
          }
          v21[24] = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = v20;
          *(_BYTE *)(*((_QWORD *)v21 + 2) + 24LL) = v20;
          std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Lrotate(a1);
          break;
        }
LABEL_61:
        v21[24] = 0;
      }
    }
    else
    {
      if ( !v21[24] )
      {
        v21[24] = v20;
        *((_BYTE *)v12 + 24) = 0;
        std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Rrotate(
          a1,
          v12);
        v21 = (_BYTE *)*v12;
      }
      if ( !v21[25] )
      {
        v22 = *((_QWORD *)v21 + 2);
        if ( *(_BYTE *)(v22 + 24) != v20 || *(_BYTE *)(*(_QWORD *)v21 + 24LL) != v20 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) == v20 )
          {
            *(_BYTE *)(v22 + 24) = v20;
            v21[24] = 0;
            std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Lrotate(a1);
            v21 = (_BYTE *)*v12;
          }
          v21[24] = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = v20;
          *(_BYTE *)(*(_QWORD *)v21 + 24LL) = v20;
          std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Rrotate(
            a1,
            v12);
          break;
        }
        goto LABEL_61;
      }
    }
    v7 = v12;
    v12 = (_QWORD *)v12[1];
  }
  *((_BYTE *)v7 + 24) = v20;
LABEL_67:
  CWin32DefaultArena::WbemMemFree(v6);
  v23 = a1[1];
  if ( v23 )
    a1[1] = (__int64 *)((char *)v23 - 1);
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x18000d0b8  push    rbx
0x18000d0ba  push    rbp
0x18000d0bb  push    rsi
0x18000d0bc  push    rdi
0x18000d0bd  push    r12
0x18000d0bf  push    r14
0x18000d0c1  push    r15
0x18000d0c3  sub     rsp, 20h
0x18000d0c7  xor     r12d, r12d
0x18000d0ca  mov     r15, rdx
0x18000d0cd  mov     rdi, rcx
0x18000d0d0  cmp     [r8+19h], r12b
0x18000d0d4  jz      short loc_18000D0E3
0x18000d0d6  lea     rcx, aInvalidMapSetT; "invalid map/set<T> iterator"
0x18000d0dd  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000d0e3  lea     rsi, [r8+10h]
0x18000d0e7  mov     r14, r8
0x18000d0ea  mov     r10, [rsi]
0x18000d0ed  lea     r11, [r8+8]
0x18000d0f1  mov     rbp, r8
0x18000d0f4  mov     r9b, [r10+19h]
0x18000d0f8  test    r9b, r9b
0x18000d0fb  jnz     short loc_18000D10A
0x18000d0fd  mov     rcx, r10
0x18000d100  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@SAPEAU?$_Tree_node@PEBGPEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ushort const *>>::_Min(std::_Tree_node<ushort const *,void *> *)
0x18000d105  mov     rbx, rax
0x18000d108  jmp     short loc_18000D122
0x18000d10a  mov     rbx, [r11]
0x18000d10d  jmp     short loc_18000D11C
0x18000d10f  cmp     r8, [rbx+10h]
0x18000d113  jnz     short loc_18000D122
0x18000d115  mov     r8, rbx
0x18000d118  mov     rbx, [rbx+8]
0x18000d11c  cmp     [rbx+19h], r12b
0x18000d120  jz      short loc_18000D10F
0x18000d122  mov     rax, [r14]
0x18000d125  cmp     [rax+19h], r12b
0x18000d129  jnz     short loc_18000D13E
0x18000d12b  test    r9b, r9b
0x18000d12e  jz      short loc_18000D135
0x18000d130  mov     r10, rax
0x18000d133  jmp     short loc_18000D13E
0x18000d135  mov     r10, [rbx+10h]
0x18000d139  cmp     rbx, r14
0x18000d13c  jnz     short loc_18000D1BB
0x18000d13e  mov     r9, [r11]
0x18000d141  cmp     [r10+19h], r12b
0x18000d145  jnz     short loc_18000D14B
0x18000d147  mov     [r10+8], r9
0x18000d14b  mov     rax, [rdi]
0x18000d14e  cmp     [rax+8], r14
0x18000d152  jnz     short loc_18000D15A
0x18000d154  mov     [rax+8], r10
0x18000d158  jmp     short loc_18000D168
0x18000d15a  cmp     [r9], r14
0x18000d15d  jnz     short loc_18000D164
0x18000d15f  mov     [r9], r10
0x18000d162  jmp     short loc_18000D168
0x18000d164  mov     [r9+10h], r10
0x18000d168  mov     r8, [rdi]
0x18000d16b  cmp     [r8], r14
0x18000d16e  jnz     short loc_18000D186
0x18000d170  cmp     [r10+19h], r12b
0x18000d174  jz      short loc_18000D17B
0x18000d176  mov     rax, r9
0x18000d179  jmp     short loc_18000D183
0x18000d17b  mov     rcx, r10
0x18000d17e  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@SAPEAU?$_Tree_node@PEBGPEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ushort const *>>::_Min(std::_Tree_node<ushort const *,void *> *)
0x18000d183  mov     [r8], rax
0x18000d186  mov     rdx, [rdi]
0x18000d189  cmp     [rdx+10h], r14
0x18000d18d  jnz     short loc_18000D1B5
0x18000d18f  cmp     [r10+19h], r12b
0x18000d193  jz      short loc_18000D19A
0x18000d195  mov     rcx, r9
0x18000d198  jmp     short loc_18000D1B1
0x18000d19a  mov     rax, [r10+10h]
0x18000d19e  mov     rcx, r10
0x18000d1a1  jmp     short loc_18000D1AB
0x18000d1a3  mov     rcx, [rcx+10h]
0x18000d1a7  mov     rax, [rcx+10h]
0x18000d1ab  cmp     [rax+19h], r12b
0x18000d1af  jz      short loc_18000D1A3
0x18000d1b1  mov     [rdx+10h], rcx
0x18000d1b5  lea     rdx, [rbp+18h]
0x18000d1b9  jmp     short loc_18000D223
0x18000d1bb  mov     [rax+8], rbx
0x18000d1bf  mov     rax, [r14]
0x18000d1c2  mov     [rbx], rax
0x18000d1c5  cmp     rbx, [rsi]
0x18000d1c8  jnz     short loc_18000D1CF
0x18000d1ca  mov     r9, rbx
0x18000d1cd  jmp     short loc_18000D1EE
0x18000d1cf  mov     r9, [rbx+8]
0x18000d1d3  cmp     [r10+19h], r12b
0x18000d1d7  jnz     short loc_18000D1DD
0x18000d1d9  mov     [r10+8], r9
0x18000d1dd  mov     [r9], r10
0x18000d1e0  mov     rax, [rsi]
0x18000d1e3  mov     [rbx+10h], rax
0x18000d1e7  mov     rax, [rsi]
0x18000d1ea  mov     [rax+8], rbx
0x18000d1ee  mov     rax, [rdi]
0x18000d1f1  cmp     [rax+8], r14
0x18000d1f5  jnz     short loc_18000D1FD
0x18000d1f7  mov     [rax+8], rbx
0x18000d1fb  jmp     short loc_18000D20E
0x18000d1fd  mov     rax, [r11]
0x18000d200  cmp     [rax], r14
0x18000d203  jnz     short loc_18000D20A
0x18000d205  mov     [rax], rbx
0x18000d208  jmp     short loc_18000D20E
0x18000d20a  mov     [rax+10h], rbx
0x18000d20e  mov     rax, [r11]
0x18000d211  lea     rdx, [r14+18h]
0x18000d215  mov     [rbx+8], rax
0x18000d219  mov     al, [rdx]
0x18000d21b  mov     cl, [rbx+18h]
0x18000d21e  mov     [rbx+18h], al
0x18000d221  mov     [rdx], cl
0x18000d223  mov     r11b, 1
0x18000d226  cmp     [rdx], r11b
0x18000d229  jnz     loc_18000D34C
0x18000d22f  mov     rax, [rdi]
0x18000d232  cmp     r10, [rax+8]
0x18000d236  jz      loc_18000D348
0x18000d23c  cmp     [r10+18h], r11b
0x18000d240  jnz     loc_18000D348
0x18000d246  mov     rdx, [r9]
0x18000d249  cmp     r10, rdx
0x18000d24c  jnz     short loc_18000D2CA
0x18000d24e  mov     rdx, [r9+10h]
0x18000d252  cmp     [rdx+18h], r12b
0x18000d256  jnz     short loc_18000D26F
0x18000d258  mov     [rdx+18h], r11b
0x18000d25c  mov     rcx, rdi
0x18000d25f  mov     rdx, r9
0x18000d262  mov     [r9+18h], r12b
0x18000d266  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Lrotate(std::_Tree_node<ushort const *,void *> *)
0x18000d26b  mov     rdx, [r9+10h]
0x18000d26f  cmp     [rdx+19h], r12b
0x18000d273  jnz     loc_18000D303
0x18000d279  mov     r8, [rdx]
0x18000d27c  cmp     [r8+18h], r11b
0x18000d280  jnz     short loc_18000D28C
0x18000d282  mov     rax, [rdx+10h]
0x18000d286  cmp     [rax+18h], r11b
0x18000d28a  jz      short loc_18000D2FF
0x18000d28c  mov     rax, [rdx+10h]
0x18000d290  cmp     [rax+18h], r11b
0x18000d294  jnz     short loc_18000D2AA
0x18000d296  mov     [r8+18h], r11b
0x18000d29a  mov     rcx, rdi
0x18000d29d  mov     [rdx+18h], r12b
0x18000d2a1  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Rrotate(std::_Tree_node<ushort const *,void *> *)
0x18000d2a6  mov     rdx, [r9+10h]
0x18000d2aa  mov     al, [r9+18h]
0x18000d2ae  mov     rcx, rdi
0x18000d2b1  mov     [rdx+18h], al
0x18000d2b4  mov     [r9+18h], r11b
0x18000d2b8  mov     rax, [rdx+10h]
0x18000d2bc  mov     rdx, r9
0x18000d2bf  mov     [rax+18h], r11b
0x18000d2c3  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Lrotate(std::_Tree_node<ushort const *,void *> *)
0x18000d2c8  jmp     short loc_18000D348
0x18000d2ca  cmp     [rdx+18h], r12b
0x18000d2ce  jnz     short loc_18000D2E6
0x18000d2d0  mov     [rdx+18h], r11b
0x18000d2d4  mov     rcx, rdi
0x18000d2d7  mov     rdx, r9
0x18000d2da  mov     [r9+18h], r12b
0x18000d2de  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Rrotate(std::_Tree_node<ushort const *,void *> *)
0x18000d2e3  mov     rdx, [r9]
0x18000d2e6  cmp     [rdx+19h], r12b
0x18000d2ea  jnz     short loc_18000D303
0x18000d2ec  mov     rcx, [rdx+10h]
0x18000d2f0  cmp     [rcx+18h], r11b
0x18000d2f4  jnz     short loc_18000D30F
0x18000d2f6  mov     rax, [rdx]
0x18000d2f9  cmp     [rax+18h], r11b
0x18000d2fd  jnz     short loc_18000D30F
0x18000d2ff  mov     [rdx+18h], r12b
0x18000d303  mov     r10, r9
0x18000d306  mov     r9, [r9+8]
0x18000d30a  jmp     loc_18000D22F
0x18000d30f  mov     rax, [rdx]
0x18000d312  cmp     [rax+18h], r11b
0x18000d316  jnz     short loc_18000D32B
0x18000d318  mov     [rcx+18h], r11b
0x18000d31c  mov     rcx, rdi
0x18000d31f  mov     [rdx+18h], r12b
0x18000d323  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Lrotate(std::_Tree_node<ushort const *,void *> *)
0x18000d328  mov     rdx, [r9]
0x18000d32b  mov     al, [r9+18h]
0x18000d32f  mov     rcx, rdi
0x18000d332  mov     [rdx+18h], al
0x18000d335  mov     [r9+18h], r11b
0x18000d339  mov     rax, [rdx]
0x18000d33c  mov     rdx, r9
0x18000d33f  mov     [rax+18h], r11b
0x18000d343  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Rrotate(std::_Tree_node<ushort const *,void *> *)
0x18000d348  mov     [r10+18h], r11b
0x18000d34c  mov     rcx, r14
0x18000d34f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000d355  mov     rax, [rdi+8]
0x18000d359  test    rax, rax
0x18000d35c  jz      short loc_18000D365
0x18000d35e  dec     rax
0x18000d361  mov     [rdi+8], rax
0x18000d365  mov     [r15], rbx
0x18000d368  mov     rax, r15
0x18000d36b  add     rsp, 20h
0x18000d36f  pop     r15
0x18000d371  pop     r14
0x18000d373  pop     r12
0x18000d375  pop     rdi
0x18000d376  pop     rsi
0x18000d377  pop     rbp
0x18000d378  pop     rbx
0x18000d379  retn
```
