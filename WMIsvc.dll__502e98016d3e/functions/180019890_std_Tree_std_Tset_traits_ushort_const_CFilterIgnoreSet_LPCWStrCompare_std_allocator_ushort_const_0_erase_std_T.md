# std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ushort const *>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ushort const *>>>)

- ea: `0x180019890`
- end: `0x18001993f`
- name: `?erase@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@2@V32@0@Z`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001738c`

## callees

- `0x18000d0b8`
- `0x18001974c`
- `0x1800197f4`
- `0x180019890`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::erase(
        __int64 **a1,
        __int64 *a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 *v6; // rdx
  __int64 v7; // rbx
  __int64 *v9; // rax
  _QWORD *v10; // r8
  __int64 v11; // rcx
  __int64 i; // rax
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v6 = *a1;
  v7 = a3;
  if ( a3 == **a1 && a4 == v6 )
  {
    std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Erase(
      a1,
      v6[1]);
    (*a1)[1] = (__int64)*a1;
    **a1 = (__int64)*a1;
    (*a1)[2] = (__int64)*a1;
    v9 = *a1;
    a1[1] = 0;
    *a2 = *v9;
  }
  else
  {
    while ( (__int64 *)v7 != a4 )
    {
      v10 = (_QWORD *)v7;
      if ( !*(_BYTE *)(v7 + 25) )
      {
        v11 = *(_QWORD *)(v7 + 16);
        if ( *(_BYTE *)(v11 + 25) )
        {
          for ( i = *(_QWORD *)(v7 + 8); !*(_BYTE *)(i + 25) && v7 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v7 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<unsigned short const *>>::_Min(v11);
        }
        v7 = i;
      }
      std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::erase(
        a1,
        &v14,
        v10);
    }
    *a2 = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x180019890  push    rbx
0x180019892  push    rdi
0x180019893  push    r14
0x180019895  push    r15
0x180019897  sub     rsp, 28h
0x18001989b  mov     r15, rdx
0x18001989e  mov     rdi, r9
0x1800198a1  mov     rdx, [rcx]
0x1800198a4  mov     rbx, r8
0x1800198a7  mov     r14, rcx
0x1800198aa  cmp     r8, [rdx]
0x1800198ad  jnz     short loc_1800198E4
0x1800198af  cmp     r9, rdx
0x1800198b2  jnz     short loc_1800198E4
0x1800198b4  mov     rdx, [rdx+8]
0x1800198b8  call    ?_Erase@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Erase(std::_Tree_node<ushort const *,void *> *)
0x1800198bd  mov     rax, [r14]
0x1800198c0  mov     [rax+8], rax
0x1800198c4  mov     rax, [r14]
0x1800198c7  mov     [rax], rax
0x1800198ca  mov     rax, [r14]
0x1800198cd  mov     [rax+10h], rax
0x1800198d1  mov     rax, [r14]
0x1800198d4  mov     qword ptr [r14+8], 0
0x1800198dc  mov     rcx, [rax]
0x1800198df  mov     [r15], rcx
0x1800198e2  jmp     short loc_180019931
0x1800198e4  cmp     rbx, rdi
0x1800198e7  jz      short loc_18001992E
0x1800198e9  cmp     byte ptr [rbx+19h], 0
0x1800198ed  mov     r8, rbx
0x1800198f0  jnz     short loc_18001991F
0x1800198f2  mov     rcx, [rbx+10h]
0x1800198f6  cmp     byte ptr [rcx+19h], 0
0x1800198fa  jnz     short loc_180019903
0x1800198fc  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@SAPEAU?$_Tree_node@PEBGPEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ushort const *>>::_Min(std::_Tree_node<ushort const *,void *> *)
0x180019901  jmp     short loc_18001991C
0x180019903  mov     rax, [rbx+8]
0x180019907  jmp     short loc_180019916
0x180019909  cmp     rbx, [rax+10h]
0x18001990d  jnz     short loc_18001991C
0x18001990f  mov     rbx, rax
0x180019912  mov     rax, [rax+8]
0x180019916  cmp     byte ptr [rax+19h], 0
0x18001991a  jz      short loc_180019909
0x18001991c  mov     rbx, rax
0x18001991f  lea     rdx, [rsp+48h+arg_0]
0x180019924  mov     rcx, r14
0x180019927  call    ?erase@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@2@V32@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ushort const *>>>)
0x18001992c  jmp     short loc_1800198E4
0x18001992e  mov     [r15], rbx
0x180019931  mov     rax, r15
0x180019934  add     rsp, 28h
0x180019938  pop     r15
0x18001993a  pop     r14
0x18001993c  pop     rdi
0x18001993d  pop     rbx
0x18001993e  retn
```
