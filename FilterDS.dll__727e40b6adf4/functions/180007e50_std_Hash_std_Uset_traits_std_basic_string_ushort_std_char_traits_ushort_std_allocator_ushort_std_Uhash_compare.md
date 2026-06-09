# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Insert<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0>)

- ea: `0x180007e50`
- end: `0x1800080de`
- name: `??$_Insert@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@@Z`
- size: `654`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800093d0`
- `0x18000c458`

## callees

- `0x180007e50`
- `0x18000c458`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007ffb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000801a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007ffb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000801a`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert<std::wstring const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD **a4)
{
  _QWORD *v5; // r9
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // r10
  unsigned __int64 v10; // rcx
  unsigned __int64 i; // rdx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  _WORD **v18; // rcx
  _WORD *v19; // r10
  unsigned __int64 v20; // rax
  _WORD *v21; // rdx
  int v22; // eax
  bool v23; // zf
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rax
  int v26; // eax
  __int64 result; // rax
  _QWORD *v28; // rdx
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  _QWORD *v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // rax
  _QWORD **v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rcx
  _QWORD *iter; // rax
  __int64 v39; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v41; // [rsp+70h] [rbp+18h] BYREF
  _QWORD **v42; // [rsp+78h] [rbp+20h]

  v42 = a4;
  v5 = a3;
  v8 = a3[2];
  v9 = 2 * v8;
  if ( a3[3] >= 8u )
    a3 = (_QWORD *)*a3;
  v10 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < v9; ++i )
    v10 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ v10);
  v12 = *(_QWORD *)(a1 + 40);
  v13 = v12 & (v10 ^ HIDWORD(v10));
  if ( *(_QWORD *)(a1 + 48) <= v13 )
    v13 = v13 - (v12 >> 1) - 1;
  v14 = 2 * v13;
  v15 = *(_QWORD *)(a1 + 16);
  v16 = *(_QWORD **)(v15 + 8 * v14);
  v41 = v16;
  if ( v16 == *(_QWORD **)a1 )
    v17 = *(_QWORD **)a1;
  else
    v17 = **(_QWORD ***)(v15 + 8 * v14 + 8);
  while ( v17 != v16 )
  {
    v17 = (_QWORD *)v17[1];
    v18 = (_WORD **)(v17 + 2);
    if ( v17[5] < 8u )
      v19 = v17 + 2;
    else
      v19 = *v18;
    v20 = v8;
    if ( v8 >= v17[4] )
      v20 = v17[4];
    if ( v5[3] < 8u )
      v21 = v5;
    else
      v21 = (_WORD *)*v5;
    if ( v20 )
    {
      while ( *v21 == *v19 )
      {
        ++v21;
        ++v19;
        if ( !--v20 )
          goto LABEL_22;
      }
      v22 = *v21 < *v19 ? -1 : 1;
    }
    else
    {
LABEL_22:
      if ( v8 >= v17[4] )
        v22 = v8 != v17[4];
      else
        v22 = -1;
    }
    v23 = v22 == 0;
    v16 = v41;
    if ( v23 )
    {
      if ( v5[3] >= 8u )
        v5 = (_QWORD *)*v5;
      v24 = v17[4];
      v25 = v24;
      if ( v24 >= v8 )
        v25 = v8;
      if ( v17[5] >= 8u )
        v18 = (_WORD **)*v18;
      if ( v25 )
      {
        while ( *(_WORD *)v18 == *(_WORD *)v5 )
        {
          v18 = (_WORD **)((char *)v18 + 2);
          v5 = (_QWORD *)((char *)v5 + 2);
          if ( !--v25 )
            goto LABEL_36;
        }
        v26 = *(_WORD *)v18 < *(_WORD *)v5 ? -1 : 1;
      }
      else
      {
LABEL_36:
        if ( v24 >= v8 )
          v26 = v24 != v8;
        else
          v26 = -1;
      }
      if ( !v26 )
      {
        if ( a4 != *(_QWORD ***)a1 )
        {
          *a4[1] = *a4;
          (*a4)[1] = a4[1];
          if ( (unsigned __int64)a4[5] >= 8 )
            operator delete(a4[2]);
          a4[5] = (_QWORD *)7;
          a4[4] = 0;
          *((_WORD *)a4 + 8) = 0;
          operator delete(a4);
          --*(_QWORD *)(a1 + 8);
        }
        *(_QWORD *)a2 = v17;
        *(_BYTE *)(a2 + 8) = 0;
        return a2;
      }
      v17 = (_QWORD *)*v17;
      break;
    }
  }
  v28 = *a4;
  if ( v17 != *a4 )
  {
    *a4[1] = v28;
    *(_QWORD *)v28[1] = v17;
    *(_QWORD *)v17[1] = a4;
    v29 = (_QWORD *)v17[1];
    v17[1] = v28[1];
    v28[1] = a4[1];
    a4[1] = v29;
  }
  v30 = *(_QWORD *)(a1 + 16);
  v31 = *(_QWORD **)(v30 + 8 * v14);
  if ( v31 == *(_QWORD **)a1 )
  {
    *(_QWORD *)(v30 + 8 * v14) = a4;
    v32 = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(v32 + 8 * v14 + 8) = a4;
  }
  else if ( v31 == v17 )
  {
    *(_QWORD *)(v30 + 8 * v14) = a4;
  }
  else
  {
    v33 = *(_QWORD **)(v30 + 8 * v14 + 8);
    v34 = (_QWORD **)*v33;
    *(_QWORD *)(v30 + 8 * v14 + 8) = *v33;
    if ( v34 != a4 )
    {
      v35 = *(_QWORD *)(a1 + 16);
      v36 = *(_QWORD *)(v35 + 8 * v14 + 8);
      *(_QWORD *)(v35 + 8 * v14 + 8) = *(_QWORD *)(v36 + 8);
    }
  }
  try
  {
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_size();
    *(_QWORD *)a2 = a4;
    *(_BYTE *)(a2 + 8) = 1;
    result = a2;
  }
  catch ( ... )
  {
    iter = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Make_iter(
                       v37,
                       &v41,
                       v42);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::erase(
      a1,
      &v39,
      *iter);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180007e50  mov     [rsp+arg_8], rbx
0x180007e55  mov     [rsp+arg_18], r9
0x180007e5a  mov     [rsp+arg_0], rcx
0x180007e5f  push    rsi
0x180007e60  push    rdi
0x180007e61  push    r12
0x180007e63  push    r14
0x180007e65  push    r15
0x180007e67  sub     rsp, 30h
0x180007e6b  mov     rbx, r9
0x180007e6e  mov     r9, r8
0x180007e71  mov     r14, rdx
0x180007e74  mov     rsi, rcx
0x180007e77  mov     r15, [r8+10h]
0x180007e7b  lea     r10, [r15+r15]
0x180007e7f  cmp     qword ptr [r8+18h], 8
0x180007e84  jb      short loc_180007E89
0x180007e86  mov     r8, [r8]
0x180007e89  mov     rcx, 0CBF29CE484222325h
0x180007e93  xor     edx, edx
0x180007e95  test    r10, r10
0x180007e98  jz      short loc_180007EB8
0x180007e9a  movzx   eax, byte ptr [rdx+r8]
0x180007e9f  xor     rcx, rax
0x180007ea2  mov     r11, 100000001B3h
0x180007eac  imul    rcx, r11
0x180007eb0  inc     rdx
0x180007eb3  cmp     rdx, r10
0x180007eb6  jb      short loc_180007E9A
0x180007eb8  mov     rax, [rsi+28h]
0x180007ebc  mov     r8, rcx
0x180007ebf  shr     r8, 20h
0x180007ec3  xor     r8, rcx
0x180007ec6  and     r8, rax
0x180007ec9  cmp     [rsi+30h], r8
0x180007ecd  ja      short loc_180007ED8
0x180007ecf  shr     rax, 1
0x180007ed2  sub     r8, rax
0x180007ed5  dec     r8
0x180007ed8  add     r8, r8
0x180007edb  mov     rdi, [rsi+10h]
0x180007edf  mov     rax, [rdi+r8*8]
0x180007ee3  mov     [rsp+58h+arg_10], rax
0x180007ee8  cmp     rax, [rsi]
0x180007eeb  jnz     short loc_180007EF2
0x180007eed  mov     rdi, [rsi]
0x180007ef0  jmp     short loc_180007EFA
0x180007ef2  mov     rdi, [rdi+r8*8+8]
0x180007ef7  mov     rdi, [rdi]
0x180007efa  cmp     rdi, rax
0x180007efd  jz      loc_180008037
0x180007f03  mov     rdi, [rdi+8]
0x180007f07  lea     rcx, [rdi+10h]
0x180007f0b  cmp     qword ptr [rdi+28h], 8
0x180007f10  jb      short loc_180007F17
0x180007f12  mov     r10, [rcx]
0x180007f15  jmp     short loc_180007F1A
0x180007f17  mov     r10, rcx
0x180007f1a  mov     rax, r15
0x180007f1d  cmp     r15, [rdi+20h]
0x180007f21  cmovnb  rax, [rdi+20h]
0x180007f26  cmp     qword ptr [r9+18h], 8
0x180007f2b  jb      short loc_180007F32
0x180007f2d  mov     rdx, [r9]
0x180007f30  jmp     short loc_180007F35
0x180007f32  mov     rdx, r9
0x180007f35  test    rax, rax
0x180007f38  jz      short loc_180007F52
0x180007f3a  movzx   r11d, word ptr [rdx]
0x180007f3e  cmp     r11w, [r10]
0x180007f42  jnz     short loc_180007F5D
0x180007f44  add     rdx, 2
0x180007f48  add     r10, 2
0x180007f4c  sub     rax, 1
0x180007f50  jnz     short loc_180007F3A
0x180007f52  cmp     r15, [rdi+20h]
0x180007f56  jnb     short loc_180007F66
0x180007f58  or      eax, 0FFFFFFFFh
0x180007f5b  jmp     short loc_180007F6F
0x180007f5d  sbb     eax, eax
0x180007f5f  and     eax, 0FFFFFFFEh
0x180007f62  inc     eax
0x180007f64  jmp     short loc_180007F6F
0x180007f66  xor     eax, eax
0x180007f68  cmp     r15, [rdi+20h]
0x180007f6c  setnz   al
0x180007f6f  test    eax, eax
0x180007f71  mov     rax, [rsp+58h+arg_10]
0x180007f76  jnz     short loc_180007EFA
0x180007f78  cmp     qword ptr [r9+18h], 8
0x180007f7d  jb      short loc_180007F82
0x180007f7f  mov     r9, [r9]
0x180007f82  mov     rdx, [rcx+10h]
0x180007f86  mov     rax, rdx
0x180007f89  cmp     rdx, r15
0x180007f8c  cmovnb  rax, r15
0x180007f90  cmp     qword ptr [rcx+18h], 8
0x180007f95  jb      short loc_180007F9A
0x180007f97  mov     rcx, [rcx]
0x180007f9a  test    rax, rax
0x180007f9d  jz      short loc_180007FB7
0x180007f9f  movzx   r10d, word ptr [rcx]
0x180007fa3  cmp     r10w, [r9]
0x180007fa7  jnz     short loc_180007FC1
0x180007fa9  add     rcx, 2
0x180007fad  add     r9, 2
0x180007fb1  sub     rax, 1
0x180007fb5  jnz     short loc_180007F9F
0x180007fb7  cmp     rdx, r15
0x180007fba  jnb     short loc_180007FCA
0x180007fbc  or      eax, 0FFFFFFFFh
0x180007fbf  jmp     short loc_180007FD2
0x180007fc1  sbb     eax, eax
0x180007fc3  and     eax, 0FFFFFFFEh
0x180007fc6  inc     eax
0x180007fc8  jmp     short loc_180007FD2
0x180007fca  xor     eax, eax
0x180007fcc  cmp     rdx, r15
0x180007fcf  setnz   al
0x180007fd2  test    eax, eax
0x180007fd4  jnz     short loc_180008034
0x180007fd6  cmp     rbx, [rsi]
0x180007fd9  jz      short loc_180008024
0x180007fdb  mov     rcx, [rbx+8]
0x180007fdf  mov     rax, [rbx]
0x180007fe2  mov     [rcx], rax
0x180007fe5  mov     rcx, [rbx]
0x180007fe8  mov     rax, [rbx+8]
0x180007fec  mov     [rcx+8], rax
0x180007ff0  cmp     qword ptr [rbx+28h], 8
0x180007ff5  jb      short loc_180008001
0x180007ff7  mov     rcx, [rbx+10h]
0x180007ffb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008001  mov     qword ptr [rbx+28h], 7
0x180008009  mov     qword ptr [rbx+20h], 0
0x180008011  xor     eax, eax
0x180008013  mov     [rbx+10h], ax
0x180008017  mov     rcx, rbx
0x18000801a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008020  dec     qword ptr [rsi+8]
0x180008024  mov     [r14], rdi
0x180008027  mov     byte ptr [r14+8], 0
0x18000802c  mov     rax, r14
0x18000802f  jmp     loc_1800080CB
0x180008034  mov     rdi, [rdi]
0x180008037  mov     rdx, [rbx]
0x18000803a  cmp     rdi, rdx
0x18000803d  jz      short loc_18000806C
0x18000803f  mov     rax, [rbx+8]
0x180008043  mov     [rax], rdx
0x180008046  mov     rax, [rdx+8]
0x18000804a  mov     [rax], rdi
0x18000804d  mov     rax, [rdi+8]
0x180008051  mov     [rax], rbx
0x180008054  mov     rcx, [rdi+8]
0x180008058  mov     rax, [rdx+8]
0x18000805c  mov     [rdi+8], rax
0x180008060  mov     rax, [rbx+8]
0x180008064  mov     [rdx+8], rax
0x180008068  mov     [rbx+8], rcx
0x18000806c  mov     rdx, [rsi+10h]
0x180008070  mov     rax, [rdx+r8*8]
0x180008074  cmp     rax, [rsi]
0x180008077  jnz     short loc_180008088
0x180008079  mov     [rdx+r8*8], rbx
0x18000807d  mov     rax, [rsi+10h]
0x180008081  mov     [rax+r8*8+8], rbx
0x180008086  jmp     short loc_1800080B7
0x180008088  cmp     rax, rdi
0x18000808b  jnz     short loc_180008093
0x18000808d  mov     [rdx+r8*8], rbx
0x180008091  jmp     short loc_1800080B7
0x180008093  mov     rax, [rdx+r8*8+8]
0x180008098  mov     rcx, [rax]
0x18000809b  mov     [rdx+r8*8+8], rcx
0x1800080a0  cmp     rcx, rbx
0x1800080a3  jz      short loc_1800080B7
0x1800080a5  mov     rdx, [rsi+10h]
0x1800080a9  mov     rax, [rdx+r8*8+8]
0x1800080ae  mov     rcx, [rax+8]
0x1800080b2  mov     [rdx+r8*8+8], rcx
0x1800080b7  mov     rcx, rsi
0x1800080ba  call    ?_Check_size@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_size(void)
0x1800080bf  nop
0x1800080c0  mov     [r14], rbx
0x1800080c3  mov     byte ptr [r14+8], 1
0x1800080c8  mov     rax, r14
0x1800080cb  mov     rbx, [rsp+58h+arg_8]
0x1800080d0  add     rsp, 30h
0x1800080d4  pop     r15
0x1800080d6  pop     r14
0x1800080d8  pop     r12
0x1800080da  pop     rdi
0x1800080db  pop     rsi
0x1800080dc  retn
```
