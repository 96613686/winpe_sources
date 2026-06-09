# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Insert<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>>>>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>>>)

- ea: `0x180011f40`
- end: `0x18001227b`
- name: `??$_Insert@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@2@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@1@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@1@@Z`
- size: `827`
- prototype: `__int64 __fastcall(__int64 **, __int64, _QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011f40`
- `0x18001347c`

## callees

- `0x18000c794`
- `0x180011f40`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800120eb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001210a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800120eb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001210a`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Insert<std::pair<std::wstring const,unsigned long> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,unsigned long>>>>>(
        __int64 **a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4)
{
  _QWORD *v5; // r9
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // r10
  unsigned __int64 v10; // rcx
  unsigned __int64 i; // rdx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r8
  __int64 v14; // r8
  __int64 *v15; // rdi
  __int64 *v16; // rax
  __int64 *v17; // rdi
  _WORD **v18; // rcx
  _WORD *v19; // r10
  unsigned __int64 v20; // rax
  _WORD *v21; // rdx
  int v22; // eax
  bool v23; // zf
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rax
  int v26; // eax
  _QWORD *v28; // rdx
  _QWORD *v29; // rcx
  __int64 *v30; // rdx
  __int64 *v31; // rax
  __int64 **v32; // rax
  __int64 *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  float v36; // xmm0_4
  __int64 v37; // rax
  float v38; // xmm1_4
  __int64 v39; // rcx
  __int64 *v40; // rax
  __int64 v41; // r14
  __int64 v42; // rdi
  _QWORD *iter; // rax
  _BYTE v44[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 *v46; // [rsp+70h] [rbp+18h] BYREF
  __int64 *v47; // [rsp+78h] [rbp+20h]

  v47 = a4;
  v5 = a3;
  v8 = a3[2];
  v9 = 2 * v8;
  if ( a3[3] >= 8u )
    a3 = (_QWORD *)*a3;
  v10 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < v9; ++i )
    v10 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ v10);
  v12 = (unsigned __int64)a1[5];
  v13 = v12 & (v10 ^ HIDWORD(v10));
  if ( (unsigned __int64)a1[6] <= v13 )
    v13 = v13 - (v12 >> 1) - 1;
  v14 = 2 * v13;
  v15 = a1[2];
  v16 = (__int64 *)v15[v14];
  v46 = v16;
  if ( v16 == *a1 )
    v17 = *a1;
  else
    v17 = *(__int64 **)v15[v14 + 1];
  while ( v17 != v16 )
  {
    v17 = (__int64 *)v17[1];
    v18 = (_WORD **)(v17 + 2);
    if ( (unsigned __int64)v17[5] < 8 )
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
    v16 = v46;
    if ( v23 )
    {
      if ( v5[3] >= 8u )
        v5 = (_QWORD *)*v5;
      v24 = v17[4];
      v25 = v24;
      if ( v24 >= v8 )
        v25 = v8;
      if ( (unsigned __int64)v17[5] >= 8 )
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
        if ( a4 != *a1 )
        {
          *(_QWORD *)a4[1] = *a4;
          *(_QWORD *)(*a4 + 8) = a4[1];
          if ( (unsigned __int64)a4[5] >= 8 )
            operator delete((void *)a4[2]);
          a4[5] = 7;
          a4[4] = 0;
          *((_WORD *)a4 + 8) = 0;
          operator delete(a4);
          a1[1] = (__int64 *)((char *)a1[1] - 1);
        }
        *(_QWORD *)a2 = v17;
        *(_BYTE *)(a2 + 8) = 0;
        return a2;
      }
      v17 = (__int64 *)*v17;
      break;
    }
  }
  v46 = a4;
  v28 = (_QWORD *)*a4;
  if ( v17 != (__int64 *)*a4 )
  {
    *(_QWORD *)a4[1] = v28;
    *(_QWORD *)v28[1] = v17;
    *(_QWORD *)v17[1] = a4;
    v29 = (_QWORD *)v17[1];
    v17[1] = v28[1];
    v28[1] = a4[1];
    a4[1] = (__int64)v29;
  }
  v30 = a1[2];
  v31 = (__int64 *)v30[v14];
  if ( v31 == *a1 )
  {
    v30[v14] = (__int64)a4;
    a1[2][v14 + 1] = (__int64)a4;
  }
  else if ( v31 == v17 )
  {
    v30[v14] = (__int64)a4;
  }
  else
  {
    v32 = (__int64 **)v30[v14 + 1];
    v33 = *v32;
    v30[v14 + 1] = (__int64)*v32;
    if ( v33 != a4 )
      a1[2][v14 + 1] = *(_QWORD *)(a1[2][v14 + 1] + 8);
  }
  v34 = (__int64)a1[6];
  v35 = (__int64)a1[1];
  if ( v35 < 0 )
  {
    v37 = (unsigned __int64)a1[1] & 1 | ((unsigned __int64)v35 >> 1);
    v36 = (float)(int)v37 + (float)(int)v37;
  }
  else
  {
    v36 = (float)(int)v35;
  }
  if ( v34 < 0 )
    v38 = (float)(int)((_DWORD)a1[6] & 1 | ((unsigned __int64)v34 >> 1))
        + (float)(int)((_DWORD)a1[6] & 1 | ((unsigned __int64)v34 >> 1));
  else
    v38 = (float)(int)v34;
  if ( (float)(v36 / v38) > *((float *)a1 + 14) )
  {
    try
    {
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init();
      v40 = *a1;
      if ( (__int64 *)*v40 != v40 )
      {
        v41 = v40[1];
        do
        {
          v42 = **a1;
          std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Insert<std::pair<std::wstring const,unsigned long> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,unsigned long>>>>>(
            a1,
            v44,
            v42 + 16,
            v42);
        }
        while ( v42 != v41 );
      }
    }
    catch ( ... )
    {
      iter = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Make_iter(
                         v39,
                         &v46,
                         v46);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::erase(
        a1,
        v44,
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
0x180011f40  mov     [rsp+arg_8], rbx
0x180011f45  mov     [rsp+arg_18], r9
0x180011f4a  mov     [rsp+arg_0], rcx
0x180011f4f  push    rsi
0x180011f50  push    rdi
0x180011f51  push    r12
0x180011f53  push    r14
0x180011f55  push    r15
0x180011f57  sub     rsp, 30h
0x180011f5b  mov     rbx, r9
0x180011f5e  mov     r9, r8
0x180011f61  mov     r15, rdx
0x180011f64  mov     rsi, rcx
0x180011f67  mov     r14, [r8+10h]
0x180011f6b  lea     r10, [r14+r14]
0x180011f6f  cmp     qword ptr [r8+18h], 8
0x180011f74  jb      short loc_180011F79
0x180011f76  mov     r8, [r8]
0x180011f79  mov     rcx, 0CBF29CE484222325h
0x180011f83  xor     edx, edx
0x180011f85  test    r10, r10
0x180011f88  jz      short loc_180011FA8
0x180011f8a  movzx   eax, byte ptr [r8+rdx]
0x180011f8f  xor     rcx, rax
0x180011f92  mov     r11, 100000001B3h
0x180011f9c  imul    rcx, r11
0x180011fa0  inc     rdx
0x180011fa3  cmp     rdx, r10
0x180011fa6  jb      short loc_180011F8A
0x180011fa8  mov     rax, [rsi+28h]
0x180011fac  mov     r8, rcx
0x180011faf  shr     r8, 20h
0x180011fb3  xor     r8, rcx
0x180011fb6  and     r8, rax
0x180011fb9  cmp     [rsi+30h], r8
0x180011fbd  ja      short loc_180011FC8
0x180011fbf  shr     rax, 1
0x180011fc2  sub     r8, rax
0x180011fc5  dec     r8
0x180011fc8  add     r8, r8
0x180011fcb  mov     rdi, [rsi+10h]
0x180011fcf  mov     rax, [rdi+r8*8]
0x180011fd3  mov     [rsp+58h+arg_10], rax
0x180011fd8  cmp     rax, [rsi]
0x180011fdb  jnz     short loc_180011FE2
0x180011fdd  mov     rdi, [rsi]
0x180011fe0  jmp     short loc_180011FEA
0x180011fe2  mov     rdi, [rdi+r8*8+8]
0x180011fe7  mov     rdi, [rdi]
0x180011fea  cmp     rdi, rax
0x180011fed  jz      loc_180012127
0x180011ff3  mov     rdi, [rdi+8]
0x180011ff7  lea     rcx, [rdi+10h]
0x180011ffb  cmp     qword ptr [rdi+28h], 8
0x180012000  jb      short loc_180012007
0x180012002  mov     r10, [rcx]
0x180012005  jmp     short loc_18001200A
0x180012007  mov     r10, rcx
0x18001200a  mov     rax, r14
0x18001200d  cmp     r14, [rdi+20h]
0x180012011  cmovnb  rax, [rdi+20h]
0x180012016  cmp     qword ptr [r9+18h], 8
0x18001201b  jb      short loc_180012022
0x18001201d  mov     rdx, [r9]
0x180012020  jmp     short loc_180012025
0x180012022  mov     rdx, r9
0x180012025  test    rax, rax
0x180012028  jz      short loc_180012042
0x18001202a  movzx   r11d, word ptr [rdx]
0x18001202e  cmp     r11w, [r10]
0x180012032  jnz     short loc_18001204D
0x180012034  add     rdx, 2
0x180012038  add     r10, 2
0x18001203c  sub     rax, 1
0x180012040  jnz     short loc_18001202A
0x180012042  cmp     r14, [rdi+20h]
0x180012046  jnb     short loc_180012056
0x180012048  or      eax, 0FFFFFFFFh
0x18001204b  jmp     short loc_18001205F
0x18001204d  sbb     eax, eax
0x18001204f  and     eax, 0FFFFFFFEh
0x180012052  inc     eax
0x180012054  jmp     short loc_18001205F
0x180012056  xor     eax, eax
0x180012058  cmp     r14, [rdi+20h]
0x18001205c  setnz   al
0x18001205f  test    eax, eax
0x180012061  mov     rax, [rsp+58h+arg_10]
0x180012066  jnz     short loc_180011FEA
0x180012068  cmp     qword ptr [r9+18h], 8
0x18001206d  jb      short loc_180012072
0x18001206f  mov     r9, [r9]
0x180012072  mov     rdx, [rcx+10h]
0x180012076  mov     rax, rdx
0x180012079  cmp     rdx, r14
0x18001207c  cmovnb  rax, r14
0x180012080  cmp     qword ptr [rcx+18h], 8
0x180012085  jb      short loc_18001208A
0x180012087  mov     rcx, [rcx]
0x18001208a  test    rax, rax
0x18001208d  jz      short loc_1800120A7
0x18001208f  movzx   r10d, word ptr [rcx]
0x180012093  cmp     r10w, [r9]
0x180012097  jnz     short loc_1800120B1
0x180012099  add     rcx, 2
0x18001209d  add     r9, 2
0x1800120a1  sub     rax, 1
0x1800120a5  jnz     short loc_18001208F
0x1800120a7  cmp     rdx, r14
0x1800120aa  jnb     short loc_1800120BA
0x1800120ac  or      eax, 0FFFFFFFFh
0x1800120af  jmp     short loc_1800120C2
0x1800120b1  sbb     eax, eax
0x1800120b3  and     eax, 0FFFFFFFEh
0x1800120b6  inc     eax
0x1800120b8  jmp     short loc_1800120C2
0x1800120ba  xor     eax, eax
0x1800120bc  cmp     rdx, r14
0x1800120bf  setnz   al
0x1800120c2  test    eax, eax
0x1800120c4  jnz     short loc_180012124
0x1800120c6  cmp     rbx, [rsi]
0x1800120c9  jz      short loc_180012114
0x1800120cb  mov     rcx, [rbx+8]
0x1800120cf  mov     rax, [rbx]
0x1800120d2  mov     [rcx], rax
0x1800120d5  mov     rcx, [rbx]
0x1800120d8  mov     rax, [rbx+8]
0x1800120dc  mov     [rcx+8], rax
0x1800120e0  cmp     qword ptr [rbx+28h], 8
0x1800120e5  jb      short loc_1800120F1
0x1800120e7  mov     rcx, [rbx+10h]
0x1800120eb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800120f1  mov     qword ptr [rbx+28h], 7
0x1800120f9  mov     qword ptr [rbx+20h], 0
0x180012101  xor     eax, eax
0x180012103  mov     [rbx+10h], ax
0x180012107  mov     rcx, rbx
0x18001210a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012110  dec     qword ptr [rsi+8]
0x180012114  mov     [r15], rdi
0x180012117  mov     byte ptr [r15+8], 0
0x18001211c  mov     rax, r15
0x18001211f  jmp     loc_180012268
0x180012124  mov     rdi, [rdi]
0x180012127  mov     [rsp+58h+arg_10], rbx
0x18001212c  mov     rdx, [rbx]
0x18001212f  cmp     rdi, rdx
0x180012132  jz      short loc_180012161
0x180012134  mov     rax, [rbx+8]
0x180012138  mov     [rax], rdx
0x18001213b  mov     rax, [rdx+8]
0x18001213f  mov     [rax], rdi
0x180012142  mov     rax, [rdi+8]
0x180012146  mov     [rax], rbx
0x180012149  mov     rcx, [rdi+8]
0x18001214d  mov     rax, [rdx+8]
0x180012151  mov     [rdi+8], rax
0x180012155  mov     rax, [rbx+8]
0x180012159  mov     [rdx+8], rax
0x18001215d  mov     [rbx+8], rcx
0x180012161  mov     rdx, [rsi+10h]
0x180012165  mov     rax, [rdx+r8*8]
0x180012169  cmp     rax, [rsi]
0x18001216c  jnz     short loc_18001217D
0x18001216e  mov     [rdx+r8*8], rbx
0x180012172  mov     rax, [rsi+10h]
0x180012176  mov     [rax+r8*8+8], rbx
0x18001217b  jmp     short loc_1800121AC
0x18001217d  cmp     rax, rdi
0x180012180  jnz     short loc_180012188
0x180012182  mov     [rdx+r8*8], rbx
0x180012186  jmp     short loc_1800121AC
0x180012188  mov     rax, [rdx+r8*8+8]
0x18001218d  mov     rcx, [rax]
0x180012190  mov     [rdx+r8*8+8], rcx
0x180012195  cmp     rcx, rbx
0x180012198  jz      short loc_1800121AC
0x18001219a  mov     rdx, [rsi+10h]
0x18001219e  mov     rax, [rdx+r8*8+8]
0x1800121a3  mov     rcx, [rax+8]
0x1800121a7  mov     [rdx+r8*8+8], rcx
0x1800121ac  mov     rdx, [rsi+30h]
0x1800121b0  mov     rcx, [rsi+8]
0x1800121b4  xorps   xmm0, xmm0
0x1800121b7  test    rcx, rcx
0x1800121ba  js      short loc_1800121C3
0x1800121bc  cvtsi2ss xmm0, rcx
0x1800121c1  jmp     short loc_1800121D8
0x1800121c3  mov     rax, rcx
0x1800121c6  shr     rax, 1
0x1800121c9  and     ecx, 1
0x1800121cc  or      rax, rcx
0x1800121cf  cvtsi2ss xmm0, rax
0x1800121d4  addss   xmm0, xmm0
0x1800121d8  xorps   xmm1, xmm1
0x1800121db  test    rdx, rdx
0x1800121de  js      short loc_1800121E7
0x1800121e0  cvtsi2ss xmm1, rdx
0x1800121e5  jmp     short loc_1800121FF
0x1800121e7  mov     rcx, rdx
0x1800121ea  shr     rcx, 1
0x1800121ed  mov     rax, rdx
0x1800121f0  and     eax, 1
0x1800121f3  or      rcx, rax
0x1800121f6  cvtsi2ss xmm1, rcx
0x1800121fb  addss   xmm1, xmm1
0x1800121ff  divss   xmm0, xmm1
0x180012203  comiss  xmm0, dword ptr [rsi+38h]
0x180012207  jbe     short loc_18001225D
0x180012209  cmp     rdx, 200h
0x180012210  jnb     short loc_180012218
0x180012212  shl     rdx, 3
0x180012216  jmp     short loc_18001222A
0x180012218  mov     rax, 0FFFFFFFFFFFFFFFh
0x180012222  cmp     rdx, rax
0x180012225  jnb     short loc_18001222A
0x180012227  add     rdx, rdx
0x18001222a  mov     rcx, rsi
0x18001222d  call    ?_Init@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(unsigned __int64)
0x180012232  mov     rax, [rsi]
0x180012235  cmp     [rax], rax
0x180012238  jz      short loc_18001225D
0x18001223a  mov     r14, [rax+8]
0x18001223e  mov     rdi, [rsi]
0x180012241  mov     rdi, [rdi]
0x180012244  lea     r8, [rdi+10h]
0x180012248  mov     r9, rdi
0x18001224b  lea     rdx, [rsp+58h+var_38]
0x180012250  mov     rcx, rsi
0x180012253  call    ??$_Insert@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@2@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@1@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Insert<std::pair<std::wstring const,ulong> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,ulong>>>>>(std::pair<std::wstring const,ulong> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,ulong>>>>)
0x180012258  cmp     rdi, r14
0x18001225b  jnz     short loc_18001223E
0x18001225d  mov     [r15], rbx
0x180012260  mov     byte ptr [r15+8], 1
0x180012265  mov     rax, r15
0x180012268  mov     rbx, [rsp+58h+arg_8]
0x18001226d  add     rsp, 30h
0x180012271  pop     r15
0x180012273  pop     r14
0x180012275  pop     r12
0x180012277  pop     rdi
0x180012278  pop     rsi
0x180012279  retn
```
