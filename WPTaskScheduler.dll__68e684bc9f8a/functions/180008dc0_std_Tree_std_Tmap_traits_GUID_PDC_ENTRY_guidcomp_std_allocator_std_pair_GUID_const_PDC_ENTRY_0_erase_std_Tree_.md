# std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,PDC_ENTRY *>>>>)

- ea: `0x180008dc0`
- end: `0x18000934d`
- name: `?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVPDC_ENTRY@@Uguidcomp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@@std@@@2@@Z`
- size: `1421`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _BYTE **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008d00`

## callees

- `0x180008dc0`
- `0x18000fb2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008ee2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008ee2`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::erase(
        _QWORD *a1,
        _QWORD *a2,
        _BYTE **a3)
{
  __int64 *v5; // r8
  _BYTE **v6; // rbx
  _QWORD **i; // r11
  _BYTE **v8; // r9
  _BYTE **v9; // rax
  _QWORD *v10; // rcx
  __int64 *v11; // r11
  _BYTE **v12; // r8
  _BYTE **j; // r8
  _BYTE *v14; // r8
  __int64 v15; // rax
  _BYTE *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // r8
  _QWORD *v22; // r8
  _QWORD *v23; // rcx
  char v24; // dl
  _QWORD *v25; // rdx
  _QWORD *v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  _QWORD *v30; // rdx
  _QWORD *v31; // rcx
  __int64 v32; // rcx
  _QWORD *v33; // rcx
  _BYTE **v34; // rdx
  _BYTE *v35; // r10
  _BYTE **v36; // rbp
  char v37; // cl

  if ( *((_BYTE *)a3 + 25) )
    std::_Xout_of_range("invalid map/set<T> iterator");
  v8 = (_BYTE **)a3[2];
  v34 = a3 + 2;
  v35 = a3;
  v36 = a3;
  v37 = *((_BYTE *)v8 + 25);
  if ( v37 )
  {
    v6 = (_BYTE **)a3[1];
    for ( i = (_QWORD **)(a3 + 1); !*((_BYTE *)v6 + 25); v6 = (_BYTE **)v6[1] )
    {
      if ( a3 != (_BYTE **)v6[2] )
        break;
      a3 = v6;
    }
  }
  else
  {
    v5 = (__int64 *)*v8;
    if ( (*v8)[25] )
    {
      v6 = v8;
    }
    else
    {
      do
      {
        v6 = (_BYTE **)v5;
        v5 = (__int64 *)*v5;
      }
      while ( !*((_BYTE *)v5 + 25) );
    }
    i = (_QWORD **)(v36 + 1);
  }
  if ( !*(_BYTE *)(*(_QWORD *)v35 + 25LL) )
  {
    if ( v37 )
    {
      v8 = *(_BYTE ***)v35;
    }
    else
    {
      v8 = (_BYTE **)v6[2];
      if ( v6 != (_BYTE **)v35 )
      {
        *(_QWORD *)(*(_QWORD *)v35 + 8LL) = v6;
        *v6 = *(_BYTE **)v35;
        if ( v6 == (_BYTE **)*v34 )
        {
          v9 = v6;
        }
        else
        {
          v9 = (_BYTE **)v6[1];
          if ( !*((_BYTE *)v8 + 25) )
            v8[1] = v9;
          *v9 = v8;
          v6[2] = *v34;
          *((_QWORD *)*v34 + 1) = v6;
        }
        if ( *(_BYTE **)(*a1 + 8LL) == v35 )
        {
          *(_QWORD *)(*a1 + 8LL) = v6;
        }
        else
        {
          v10 = *i;
          if ( (_BYTE *)**i == v35 )
            *v10 = v6;
          else
            v10[2] = v6;
        }
        v14 = v35 + 24;
        v6[1] = *i;
        v24 = *((_BYTE *)v6 + 24);
        *((_BYTE *)v6 + 24) = v35[24];
        v35[24] = v24;
        goto LABEL_29;
      }
    }
  }
  v9 = (_BYTE **)*i;
  if ( !*((_BYTE *)v8 + 25) )
    v8[1] = v9;
  if ( *(_BYTE **)(*a1 + 8LL) == v35 )
  {
    *(_QWORD *)(*a1 + 8LL) = v8;
  }
  else if ( *v9 == v35 )
  {
    *v9 = v8;
  }
  else
  {
    v9[2] = v8;
  }
  if ( *(_BYTE **)*a1 == v35 )
  {
    if ( *((_BYTE *)v8 + 25) )
    {
      v12 = v9;
    }
    else
    {
      v11 = (__int64 *)*v8;
      if ( (*v8)[25] )
      {
        v12 = v8;
      }
      else
      {
        do
        {
          v12 = (_BYTE **)v11;
          v11 = (__int64 *)*v11;
        }
        while ( !*((_BYTE *)v11 + 25) );
      }
    }
    *(_QWORD *)*a1 = v12;
  }
  if ( *(_BYTE **)(*a1 + 16LL) == v35 )
  {
    if ( *((_BYTE *)v8 + 25) )
    {
      j = v9;
    }
    else
    {
      for ( j = v8; !j[2][25]; j = (_BYTE **)j[2] )
        ;
    }
    *(_QWORD *)(*a1 + 16LL) = j;
  }
  v14 = v36 + 3;
LABEL_29:
  if ( *v14 != 1 )
    goto LABEL_30;
  while ( 1 )
  {
    if ( v8 == *(_BYTE ***)(*a1 + 8LL) || *((_BYTE *)v8 + 24) != 1 )
      goto LABEL_91;
    v17 = *v9;
    if ( v8 == (_BYTE **)*v9 )
      break;
    if ( !v17[24] )
    {
      v17[24] = 1;
      v18 = (__int64)*v9;
      *((_BYTE *)v9 + 24) = 0;
      *v9 = *(_BYTE **)(v18 + 16);
      v19 = *(_QWORD *)(v18 + 16);
      if ( !*(_BYTE *)(v19 + 25) )
        *(_QWORD *)(v19 + 8) = v9;
      *(_QWORD *)(v18 + 8) = v9[1];
      if ( v9 == *(_BYTE ***)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v20 = v9[1];
        if ( v9 == (_BYTE **)v20[2] )
          v20[2] = v18;
        else
          *v20 = v18;
      }
      *(_QWORD *)(v18 + 16) = v9;
      v9[1] = (_BYTE *)v18;
      v17 = *v9;
    }
    if ( !v17[25] )
    {
      v21 = *((_QWORD *)v17 + 2);
      if ( *(_BYTE *)(v21 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v17 + 24LL) != 1 )
      {
        if ( *(_BYTE *)(*(_QWORD *)v17 + 24LL) == 1 )
        {
          *(_BYTE *)(v21 + 24) = 1;
          v22 = (_QWORD *)*((_QWORD *)v17 + 2);
          v17[24] = 0;
          *((_QWORD *)v17 + 2) = *v22;
          if ( !*(_BYTE *)(*v22 + 25LL) )
            *(_QWORD *)(*v22 + 8LL) = v17;
          v22[1] = *((_QWORD *)v17 + 1);
          if ( v17 == *(_BYTE **)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v22;
          }
          else
          {
            v23 = (_QWORD *)*((_QWORD *)v17 + 1);
            if ( v17 == (_BYTE *)*v23 )
              *v23 = v22;
            else
              v23[2] = v22;
          }
          *v22 = v17;
          *((_QWORD *)v17 + 1) = v22;
          v17 = *v9;
        }
        v17[24] = *((_BYTE *)v9 + 24);
        *((_BYTE *)v9 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)v17 + 24LL) = 1;
        v30 = *v9;
        *v9 = (_BYTE *)*((_QWORD *)*v9 + 2);
        v32 = v30[2];
        if ( !*(_BYTE *)(v32 + 25) )
          *(_QWORD *)(v32 + 8) = v9;
        v30[1] = v9[1];
        if ( v9 == *(_BYTE ***)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v30;
          v30[2] = v9;
        }
        else
        {
          v33 = v9[1];
          if ( v9 == (_BYTE **)v33[2] )
            v33[2] = v30;
          else
            *v33 = v30;
          v30[2] = v9;
        }
        goto LABEL_90;
      }
      goto LABEL_116;
    }
LABEL_117:
    v8 = v9;
    v9 = (_BYTE **)v9[1];
  }
  v17 = v9[2];
  if ( !v17[24] )
  {
    v17[24] = 1;
    v25 = v9[2];
    *((_BYTE *)v9 + 24) = 0;
    v9[2] = (_BYTE *)*v25;
    if ( !*(_BYTE *)(*v25 + 25LL) )
      *(_QWORD *)(*v25 + 8LL) = v9;
    v25[1] = v9[1];
    if ( v9 == *(_BYTE ***)(*a1 + 8LL) )
    {
      *(_QWORD *)(*a1 + 8LL) = v25;
    }
    else
    {
      v26 = v9[1];
      if ( v9 == (_BYTE **)*v26 )
        *v26 = v25;
      else
        v26[2] = v25;
    }
    *v25 = v9;
    v9[1] = v25;
    v17 = v9[2];
  }
  if ( v17[25] )
    goto LABEL_117;
  if ( *(_BYTE *)(*(_QWORD *)v17 + 24LL) == 1 && *(_BYTE *)(*((_QWORD *)v17 + 2) + 24LL) == 1 )
  {
LABEL_116:
    v17[24] = 0;
    goto LABEL_117;
  }
  if ( *(_BYTE *)(*((_QWORD *)v17 + 2) + 24LL) == 1 )
  {
    *(_BYTE *)(*(_QWORD *)v17 + 24LL) = 1;
    v27 = *(_QWORD *)v17;
    v17[24] = 0;
    *(_QWORD *)v17 = *(_QWORD *)(v27 + 16);
    v28 = *(_QWORD *)(v27 + 16);
    if ( !*(_BYTE *)(v28 + 25) )
      *(_QWORD *)(v28 + 8) = v17;
    *(_QWORD *)(v27 + 8) = *((_QWORD *)v17 + 1);
    if ( v17 == *(_BYTE **)(*a1 + 8LL) )
    {
      *(_QWORD *)(*a1 + 8LL) = v27;
    }
    else
    {
      v29 = (_QWORD *)*((_QWORD *)v17 + 1);
      if ( v17 == (_BYTE *)v29[2] )
        v29[2] = v27;
      else
        *v29 = v27;
    }
    *(_QWORD *)(v27 + 16) = v17;
    *((_QWORD *)v17 + 1) = v27;
    v17 = v9[2];
  }
  v17[24] = *((_BYTE *)v9 + 24);
  *((_BYTE *)v9 + 24) = 1;
  *(_BYTE *)(*((_QWORD *)v17 + 2) + 24LL) = 1;
  v30 = v9[2];
  v9[2] = (_BYTE *)*v30;
  if ( !*(_BYTE *)(*v30 + 25LL) )
    *(_QWORD *)(*v30 + 8LL) = v9;
  v30[1] = v9[1];
  if ( v9 != *(_BYTE ***)(*a1 + 8LL) )
  {
    v31 = v9[1];
    if ( v9 == (_BYTE **)*v31 )
      *v31 = v30;
    else
      v31[2] = v30;
    *v30 = v9;
LABEL_90:
    v9[1] = v30;
LABEL_91:
    *((_BYTE *)v8 + 24) = 1;
    goto LABEL_30;
  }
  *(_QWORD *)(*a1 + 8LL) = v30;
  *v30 = v9;
  v9[1] = v30;
  *((_BYTE *)v8 + 24) = 1;
LABEL_30:
  operator delete(v35);
  v15 = a1[1];
  if ( v15 )
    a1[1] = v15 - 1;
  *a2 = v6;
  return a2;
}

```

## disassembly

```asm
0x180008dc0  mov     [rsp+arg_10], rsi
0x180008dc5  push    rdi
0x180008dc6  sub     rsp, 20h
0x180008dca  cmp     byte ptr [r8+19h], 0
0x180008dcf  mov     rsi, rdx
0x180008dd2  mov     rdi, rcx
0x180008dd5  jz      loc_1800092D2
0x180008ddb  lea     rcx, aInvalidMapSetT; "invalid map/set<T> iterator"
0x180008de2  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180008de8  mov     r8, [r9]
0x180008deb  cmp     byte ptr [r8+19h], 0
0x180008df0  jnz     loc_180009325
0x180008df6  mov     rax, [r8]
0x180008df9  mov     rbx, r8
0x180008dfc  mov     r8, rax
0x180008dff  cmp     byte ptr [rax+19h], 0
0x180008e03  jz      short loc_180008DF6
0x180008e05  lea     r11, [rbp+8]
0x180008e09  mov     rax, [r10]
0x180008e0c  cmp     byte ptr [rax+19h], 0
0x180008e10  jnz     short loc_180008E5B
0x180008e12  test    cl, cl
0x180008e14  jnz     loc_18000932D
0x180008e1a  mov     r9, [rbx+10h]
0x180008e1e  cmp     rbx, r10
0x180008e21  jz      short loc_180008E5B
0x180008e23  mov     [rax+8], rbx
0x180008e27  mov     rax, [r10]
0x180008e2a  mov     [rbx], rax
0x180008e2d  cmp     rbx, [rdx]
0x180008e30  jnz     loc_180009066
0x180008e36  mov     rax, rbx
0x180008e39  mov     rcx, [rdi]
0x180008e3c  cmp     [rcx+8], r10
0x180008e40  jz      loc_18000908B
0x180008e46  mov     rcx, [r11]
0x180008e49  cmp     [rcx], r10
0x180008e4c  jz      loc_180009007
0x180008e52  mov     [rcx+10h], rbx
0x180008e56  jmp     loc_18000900A
0x180008e5b  cmp     byte ptr [r9+19h], 0
0x180008e60  mov     rax, [r11]
0x180008e63  jnz     short loc_180008E69
0x180008e65  mov     [r9+8], rax
0x180008e69  mov     rcx, [rdi]
0x180008e6c  cmp     [rcx+8], r10
0x180008e70  jz      loc_180009028
0x180008e76  cmp     [rax], r10
0x180008e79  jnz     loc_180009031
0x180008e7f  mov     [rax], r9
0x180008e82  mov     rdx, [rdi]
0x180008e85  cmp     [rdx], r10
0x180008e88  jnz     short loc_180008EB5
0x180008e8a  cmp     byte ptr [r9+19h], 0
0x180008e8f  jnz     loc_18000903A
0x180008e95  mov     r11, [r9]
0x180008e98  cmp     byte ptr [r11+19h], 0
0x180008e9d  jnz     loc_180009335
0x180008ea3  mov     rcx, [r11]
0x180008ea6  mov     r8, r11
0x180008ea9  mov     r11, rcx
0x180008eac  cmp     byte ptr [rcx+19h], 0
0x180008eb0  jz      short loc_180008EA3
0x180008eb2  mov     [rdx], r8
0x180008eb5  mov     rdx, [rdi]
0x180008eb8  cmp     [rdx+10h], r10
0x180008ebc  jnz     short loc_180008ED0
0x180008ebe  cmp     byte ptr [r9+19h], 0
0x180008ec3  jz      loc_180009042
0x180008ec9  mov     r8, rax
0x180008ecc  mov     [rdx+10h], r8
0x180008ed0  lea     r8, [rbp+18h]
0x180008ed4  cmp     byte ptr [r8], 1
0x180008ed8  mov     rbp, [rsp+28h+arg_8]
0x180008edd  jz      short loc_180008F10
0x180008edf  mov     rcx, r10
0x180008ee2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008ee8  mov     rax, [rdi+8]
0x180008eec  test    rax, rax
0x180008eef  jz      short loc_180008EF8
0x180008ef1  dec     rax
0x180008ef4  mov     [rdi+8], rax
0x180008ef8  mov     [rsi], rbx
0x180008efb  mov     rax, rsi
0x180008efe  mov     rbx, [rsp+28h+arg_0]
0x180008f03  mov     rsi, [rsp+28h+arg_10]
0x180008f08  add     rsp, 20h
0x180008f0c  pop     rdi
0x180008f0d  retn
0x180008f10  mov     rcx, [rdi]
0x180008f13  cmp     r9, [rcx+8]
0x180008f17  jz      loc_1800091E1
0x180008f1d  cmp     byte ptr [r9+18h], 1
0x180008f22  jnz     loc_1800091E1
0x180008f28  mov     rdx, [rax]
0x180008f2b  cmp     r9, rdx
0x180008f2e  jz      loc_180009094
0x180008f34  cmp     byte ptr [rdx+18h], 0
0x180008f38  jnz     short loc_180008F8C
0x180008f3a  mov     byte ptr [rdx+18h], 1
0x180008f3e  mov     rdx, [rax]
0x180008f41  mov     byte ptr [rax+18h], 0
0x180008f45  mov     rcx, [rdx+10h]
0x180008f49  mov     [rax], rcx
0x180008f4c  mov     rcx, [rdx+10h]
0x180008f50  cmp     byte ptr [rcx+19h], 0
0x180008f54  jz      loc_1800090E2
0x180008f5a  mov     rcx, [rax+8]
0x180008f5e  mov     [rdx+8], rcx
0x180008f62  mov     rcx, [rdi]
0x180008f65  cmp     rax, [rcx+8]
0x180008f69  jz      loc_1800090EB
0x180008f6f  mov     rcx, [rax+8]
0x180008f73  cmp     rax, [rcx+10h]
0x180008f77  jnz     loc_1800090F4
0x180008f7d  mov     [rcx+10h], rdx
0x180008f81  mov     [rdx+10h], rax
0x180008f85  mov     [rax+8], rdx
0x180008f89  mov     rdx, [rax]
0x180008f8c  cmp     byte ptr [rdx+19h], 0
0x180008f90  jnz     loc_180009341
0x180008f96  mov     r8, [rdx+10h]
0x180008f9a  cmp     byte ptr [r8+18h], 1
0x180008f9f  jnz     short loc_180008FAE
0x180008fa1  mov     rcx, [rdx]
0x180008fa4  cmp     byte ptr [rcx+18h], 1
0x180008fa8  jz      loc_18000933D
0x180008fae  mov     rcx, [rdx]
0x180008fb1  cmp     byte ptr [rcx+18h], 1
0x180008fb5  jnz     loc_1800091F8
0x180008fbb  mov     byte ptr [r8+18h], 1
0x180008fc0  mov     r8, [rdx+10h]
0x180008fc4  mov     byte ptr [rdx+18h], 0
0x180008fc8  mov     rcx, [r8]
0x180008fcb  mov     [rdx+10h], rcx
0x180008fcf  mov     rcx, [r8]
0x180008fd2  cmp     byte ptr [rcx+19h], 0
0x180008fd6  jz      loc_1800092A2
0x180008fdc  mov     rcx, [rdx+8]
0x180008fe0  mov     [r8+8], rcx
0x180008fe4  mov     rcx, [rdi]
0x180008fe7  cmp     rdx, [rcx+8]
0x180008feb  jz      loc_1800092AB
0x180008ff1  mov     rcx, [rdx+8]
0x180008ff5  cmp     rdx, [rcx]
0x180008ff8  jz      loc_1800091EB
0x180008ffe  mov     [rcx+10h], r8
0x180009002  jmp     loc_1800091EE
0x180009007  mov     [rcx], rbx
0x18000900a  mov     rcx, [r11]
0x18000900d  lea     r8, [r10+18h]
0x180009011  mov     [rbx+8], rcx
0x180009015  movzx   ecx, byte ptr [r8]
0x180009019  movzx   edx, byte ptr [rbx+18h]
0x18000901d  mov     [rbx+18h], cl
0x180009020  mov     [r8], dl
0x180009023  jmp     loc_180008ED4
0x180009028  mov     [rcx+8], r9
0x18000902c  jmp     loc_180008E82
0x180009031  mov     [rax+10h], r9
0x180009035  jmp     loc_180008E82
0x18000903a  mov     r8, rax
0x18000903d  jmp     loc_180008EB2
0x180009042  mov     rcx, [r9+10h]
0x180009046  mov     r8, r9
0x180009049  cmp     byte ptr [rcx+19h], 0
0x18000904d  jnz     loc_180008ECC
0x180009053  mov     r8, [r8+10h]
0x180009057  mov     rcx, [r8+10h]
0x18000905b  cmp     byte ptr [rcx+19h], 0
0x18000905f  jz      short loc_180009053
0x180009061  jmp     loc_180008ECC
0x180009066  cmp     byte ptr [r9+19h], 0
0x18000906b  mov     rax, [rbx+8]
0x18000906f  jnz     short loc_180009075
0x180009071  mov     [r9+8], rax
0x180009075  mov     [rax], r9
0x180009078  mov     rcx, [rdx]
0x18000907b  mov     [rbx+10h], rcx
0x18000907f  mov     rcx, [rdx]
0x180009082  mov     [rcx+8], rbx
0x180009086  jmp     loc_180008E39
0x18000908b  mov     [rcx+8], rbx
0x18000908f  jmp     loc_18000900A
0x180009094  mov     rdx, [rax+10h]
0x180009098  cmp     byte ptr [rdx+18h], 0
0x18000909c  jnz     short loc_18000910A
0x18000909e  mov     byte ptr [rdx+18h], 1
0x1800090a2  mov     rdx, [rax+10h]
0x1800090a6  mov     byte ptr [rax+18h], 0
0x1800090aa  mov     rcx, [rdx]
0x1800090ad  mov     [rax+10h], rcx
0x1800090b1  mov     rcx, [rdx]
0x1800090b4  cmp     byte ptr [rcx+19h], 0
0x1800090b8  jz      loc_18000924F
0x1800090be  mov     rcx, [rax+8]
0x1800090c2  mov     [rdx+8], rcx
0x1800090c6  mov     rcx, [rdi]
0x1800090c9  cmp     rax, [rcx+8]
0x1800090cd  jz      loc_180009258
0x1800090d3  mov     rcx, [rax+8]
0x1800090d7  cmp     rax, [rcx]
0x1800090da  jz      short loc_1800090FC
0x1800090dc  mov     [rcx+10h], rdx
0x1800090e0  jmp     short loc_1800090FF
0x1800090e2  mov     [rcx+8], rax
0x1800090e6  jmp     loc_180008F5A
0x1800090eb  mov     [rcx+8], rdx
0x1800090ef  jmp     loc_180008F81
0x1800090f4  mov     [rcx], rdx
0x1800090f7  jmp     loc_180008F81
0x1800090fc  mov     [rcx], rdx
0x1800090ff  mov     [rdx], rax
0x180009102  mov     [rax+8], rdx
0x180009106  mov     rdx, [rax+10h]
0x18000910a  cmp     byte ptr [rdx+19h], 0
0x18000910e  jnz     loc_180009341
0x180009114  mov     r11, [rdx]
0x180009117  cmp     byte ptr [r11+18h], 1
0x18000911c  jnz     short loc_18000912C
0x18000911e  mov     rcx, [rdx+10h]
0x180009122  cmp     byte ptr [rcx+18h], 1
0x180009126  jz      loc_18000933D
0x18000912c  mov     rcx, [rdx+10h]
0x180009130  cmp     byte ptr [rcx+18h], 1
0x180009134  jnz     short loc_18000918A
0x180009136  mov     byte ptr [r11+18h], 1
0x18000913b  mov     r8, [rdx]
0x18000913e  mov     byte ptr [rdx+18h], 0
0x180009142  mov     rcx, [r8+10h]
0x180009146  mov     [rdx], rcx
0x180009149  mov     rcx, [r8+10h]
0x18000914d  cmp     byte ptr [rcx+19h], 0
0x180009151  jz      loc_180009261
0x180009157  mov     rcx, [rdx+8]
0x18000915b  mov     [r8+8], rcx
0x18000915f  mov     rcx, [rdi]
0x180009162  cmp     rdx, [rcx+8]
0x180009166  jz      loc_18000926A
0x18000916c  mov     rcx, [rdx+8]
0x180009170  cmp     rdx, [rcx+10h]
0x180009174  jnz     loc_180009273
0x18000917a  mov     [rcx+10h], r8
0x18000917e  mov     [r8+10h], rdx
0x180009182  mov     [rdx+8], r8
0x180009186  mov     rdx, [rax+10h]
0x18000918a  movzx   ecx, byte ptr [rax+18h]
0x18000918e  mov     [rdx+18h], cl
0x180009191  mov     byte ptr [rax+18h], 1
0x180009195  mov     rcx, [rdx+10h]
0x180009199  mov     byte ptr [rcx+18h], 1
0x18000919d  mov     rdx, [rax+10h]
0x1800091a1  mov     rcx, [rdx]
0x1800091a4  mov     [rax+10h], rcx
0x1800091a8  mov     rcx, [rdx]
0x1800091ab  cmp     byte ptr [rcx+19h], 0
0x1800091af  jz      loc_18000927B
0x1800091b5  mov     rcx, [rax+8]
0x1800091b9  mov     [rdx+8], rcx
0x1800091bd  mov     rcx, [rdi]
0x1800091c0  cmp     rax, [rcx+8]
0x1800091c4  jz      loc_180009284
0x1800091ca  mov     rcx, [rax+8]
0x1800091ce  cmp     rax, [rcx]
0x1800091d1  jnz     loc_180009299
0x1800091d7  mov     [rcx], rdx
0x1800091da  mov     [rdx], rax
0x1800091dd  mov     [rax+8], rdx
0x1800091e1  mov     byte ptr [r9+18h], 1
0x1800091e6  jmp     loc_180008EDF
0x1800091eb  mov     [rcx], r8
0x1800091ee  mov     [r8], rdx
0x1800091f1  mov     [rdx+8], r8
0x1800091f5  mov     rdx, [rax]
0x1800091f8  movzx   ecx, byte ptr [rax+18h]
0x1800091fc  mov     [rdx+18h], cl
0x1800091ff  mov     byte ptr [rax+18h], 1
0x180009203  mov     rcx, [rdx]
0x180009206  mov     byte ptr [rcx+18h], 1
0x18000920a  mov     rdx, [rax]
0x18000920d  mov     rcx, [rdx+10h]
0x180009211  mov     [rax], rcx
0x180009214  mov     rcx, [rdx+10h]
0x180009218  cmp     byte ptr [rcx+19h], 0
0x18000921c  jz      loc_1800092B4
0x180009222  mov     rcx, [rax+8]
0x180009226  mov     [rdx+8], rcx
0x18000922a  mov     rcx, [rdi]
0x18000922d  cmp     rax, [rcx+8]
0x180009231  jz      loc_1800092BD
0x180009237  mov     rcx, [rax+8]
0x18000923b  cmp     rax, [rcx+10h]
0x18000923f  jnz     loc_1800092CA
0x180009245  mov     [rcx+10h], rdx
0x180009249  mov     [rdx+10h], rax
0x18000924d  jmp     short loc_1800091DD
0x18000924f  mov     [rcx+8], rax
0x180009253  jmp     loc_1800090BE
0x180009258  mov     [rcx+8], rdx
0x18000925c  jmp     loc_1800090FF
  ... truncated ...
```
