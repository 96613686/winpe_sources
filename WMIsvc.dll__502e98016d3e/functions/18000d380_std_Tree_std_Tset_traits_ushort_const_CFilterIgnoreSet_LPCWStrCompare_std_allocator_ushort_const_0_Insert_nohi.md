# std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Insert_nohint<ushort const * const &,std::_Nil>(bool,ushort const * const &,std::_Nil)

- ea: `0x18000d380`
- end: `0x18000d4b2`
- name: `??$_Insert_nohint@AEBQEBGU_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@std@@_N@1@_NAEBQEBGU_Nil@1@@Z`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ce8c`
- `0x1800177b4`

## callees

- `0x18000d380`
- `0x18001718c`
- `0x1800174a4`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Insert_nohint<unsigned short const * const &,std::_Nil>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 **v6; // r14
  __int64 v7; // rdi
  char v8; // r15
  __int64 v9; // rbx
  __int64 i; // rbx
  __int64 result; // rax
  __int64 v12; // rax
  __int64 v13[8]; // [rsp+38h] [rbp-40h] BYREF

  v6 = (__int64 **)a1;
  try
  {
    v7 = *(_QWORD *)a1;
    v9 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
    v8 = 1;
    while ( !*(_BYTE *)(v9 + 25) )
    {
      v7 = v9;
      v8 = CFilterIgnoreSet::LPCWStrCompare::operator()(a1, *a4, *(_QWORD *)(v9 + 32));
      if ( v8 )
        v9 = *(_QWORD *)v9;
      else
        v9 = *(_QWORD *)(v9 + 16);
    }
    i = v7;
    if ( v8 )
    {
      a1 = **v6;
      v13[0] = a1;
      if ( v7 == a1 )
      {
        *(_QWORD *)a2 = *std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Insert_at<unsigned short const * const &,std::_Nil>(
                           v6,
                           v13,
                           1,
                           (__int64 *)v7,
                           (__int64)a4);
        *(_BYTE *)(a2 + 8) = 1;
        return a2;
      }
      if ( *(_BYTE *)(v7 + 25) )
      {
        i = *(_QWORD *)(v7 + 16);
      }
      else if ( *(_BYTE *)(*(_QWORD *)v7 + 25LL) )
      {
        while ( 1 )
        {
          v12 = *(_QWORD *)(i + 8);
          if ( *(_BYTE *)(v12 + 25) || i != *(_QWORD *)v12 )
            break;
          i = *(_QWORD *)(i + 8);
        }
        if ( !*(_BYTE *)(i + 25) )
          i = *(_QWORD *)(i + 8);
      }
      else
      {
        for ( i = *(_QWORD *)v7; !*(_BYTE *)(*(_QWORD *)(i + 16) + 25LL); i = *(_QWORD *)(i + 16) )
          ;
      }
    }
    if ( (unsigned __int8)CFilterIgnoreSet::LPCWStrCompare::operator()(a1, *(_QWORD *)(i + 32), *a4) )
    {
      *(_QWORD *)a2 = *std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Insert_at<unsigned short const * const &,std::_Nil>(
                         v6,
                         v13,
                         v8,
                         (__int64 *)v7,
                         (__int64)a4);
      *(_BYTE *)(a2 + 8) = 1;
    }
    else
    {
      *(_QWORD *)a2 = i;
      *(_BYTE *)(a2 + 8) = 0;
    }
    result = a2;
  }
  catch ( ... )
  {
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000d380  push    rbx
0x18000d382  push    rsi
0x18000d383  push    rdi
0x18000d384  push    r12
0x18000d386  push    r14
0x18000d388  push    r15
0x18000d38a  sub     rsp, 48h
0x18000d38e  mov     r12, r9
0x18000d391  mov     rsi, rdx
0x18000d394  mov     r14, rcx
0x18000d397  mov     rdi, [rcx]
0x18000d39a  mov     rbx, [rdi+8]
0x18000d39e  mov     r15b, 1
0x18000d3a1  cmp     byte ptr [rbx+19h], 0
0x18000d3a5  jnz     short loc_18000D3C9
0x18000d3a7  mov     rdi, rbx
0x18000d3aa  mov     r8, [rbx+20h]
0x18000d3ae  mov     rdx, [r12]
0x18000d3b2  call    ??RLPCWStrCompare@CFilterIgnoreSet@@QEBA_NPEBG0@Z; CFilterIgnoreSet::LPCWStrCompare::operator()(ushort const *,ushort const *)
0x18000d3b7  mov     r15b, al
0x18000d3ba  test    al, al
0x18000d3bc  jz      short loc_18000D3C3
0x18000d3be  mov     rbx, [rbx]
0x18000d3c1  jmp     short loc_18000D3C7
0x18000d3c3  mov     rbx, [rbx+10h]
0x18000d3c7  jmp     short loc_18000D3A1
0x18000d3c9  mov     rbx, rdi
0x18000d3cc  mov     [rsp+78h+var_48], rbx
0x18000d3d1  test    r15b, r15b
0x18000d3d4  jz      loc_18000D461
0x18000d3da  mov     rax, [r14]
0x18000d3dd  mov     rcx, [rax]
0x18000d3e0  mov     [rsp+78h+var_40], rcx
0x18000d3e5  cmp     rdi, rcx
0x18000d3e8  jnz     short loc_18000D414
0x18000d3ea  mov     [rsp+78h+var_58], r12
0x18000d3ef  mov     r9, rdi
0x18000d3f2  mov     r8b, 1
0x18000d3f5  lea     rdx, [rsp+78h+var_40]
0x18000d3fa  mov     rcx, r14
0x18000d3fd  call    ??$_Insert_at@AEBQEBGU_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@1@_NPEAU?$_Tree_node@PEBGPEAX@1@AEBQEBGU_Nil@1@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Insert_at<ushort const * const &,std::_Nil>(bool,std::_Tree_node<ushort const *,void *> *,ushort const * const &,std::_Nil)
0x18000d402  mov     rcx, [rax]
0x18000d405  mov     [rsi], rcx
0x18000d408  mov     byte ptr [rsi+8], 1
0x18000d40c  mov     rax, rsi
0x18000d40f  jmp     loc_18000D4A3
0x18000d414  cmp     byte ptr [rdi+19h], 0
0x18000d418  jz      short loc_18000D420
0x18000d41a  mov     rbx, [rdi+10h]
0x18000d41e  jmp     short loc_18000D45C
0x18000d420  mov     rax, [rdi]
0x18000d423  cmp     byte ptr [rax+19h], 0
0x18000d427  jnz     short loc_18000D43B
0x18000d429  mov     rbx, rax
0x18000d42c  mov     rax, [rbx+10h]
0x18000d430  cmp     byte ptr [rax+19h], 0
0x18000d434  jnz     short loc_18000D45C
0x18000d436  mov     rbx, rax
0x18000d439  jmp     short loc_18000D42C
0x18000d43b  mov     rax, [rbx+8]
0x18000d43f  cmp     byte ptr [rax+19h], 0
0x18000d443  jnz     short loc_18000D454
0x18000d445  cmp     rbx, [rax]
0x18000d448  jnz     short loc_18000D454
0x18000d44a  mov     rbx, rax
0x18000d44d  mov     [rsp+78h+var_48], rax
0x18000d452  jmp     short loc_18000D43B
0x18000d454  cmp     byte ptr [rbx+19h], 0
0x18000d458  cmovz   rbx, rax
0x18000d45c  mov     [rsp+78h+var_48], rbx
0x18000d461  mov     r8, [r12]
0x18000d465  mov     rdx, [rbx+20h]
0x18000d469  call    ??RLPCWStrCompare@CFilterIgnoreSet@@QEBA_NPEBG0@Z; CFilterIgnoreSet::LPCWStrCompare::operator()(ushort const *,ushort const *)
0x18000d46e  test    al, al
0x18000d470  jz      short loc_18000D499
0x18000d472  mov     [rsp+78h+var_58], r12
0x18000d477  mov     r9, rdi
0x18000d47a  mov     r8b, r15b
0x18000d47d  lea     rdx, [rsp+78h+var_40]
0x18000d482  mov     rcx, r14
0x18000d485  call    ??$_Insert_at@AEBQEBGU_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@@1@_NPEAU?$_Tree_node@PEBGPEAX@1@AEBQEBGU_Nil@1@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Insert_at<ushort const * const &,std::_Nil>(bool,std::_Tree_node<ushort const *,void *> *,ushort const * const &,std::_Nil)
0x18000d48a  mov     rcx, [rax]
0x18000d48d  mov     [rsi], rcx
0x18000d490  mov     byte ptr [rsi+8], 1
0x18000d494  mov     rax, rsi
0x18000d497  jmp     short loc_18000D4A3
0x18000d499  mov     [rsi], rbx
0x18000d49c  mov     byte ptr [rsi+8], 0
0x18000d4a0  mov     rax, rsi
0x18000d4a3  add     rsp, 48h
0x18000d4a7  pop     r15
0x18000d4a9  pop     r14
0x18000d4ab  pop     r12
0x18000d4ad  pop     rdi
0x18000d4ae  pop     rsi
0x18000d4af  pop     rbx
0x18000d4b0  retn
```
