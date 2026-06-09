# std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>>>)

- ea: `0x1800211a0`
- end: `0x180021644`
- name: `?erase@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@2@@Z`
- size: `1188`
- prototype: `char **__fastcall(_QWORD *, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020d5c`

## callees

- `0x180001c2c`
- `0x1800211a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800215f7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180021610`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800215f7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180021610`

## pseudocode

```c
char **__fastcall std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::erase(
        _QWORD *a1,
        char **a2,
        char *a3)
{
  char *v5; // r10
  char *v6; // rdi
  void **v7; // r9
  char *v8; // r11
  char v9; // dl
  char *v10; // rcx
  char *i; // rbx
  void ***v12; // rcx
  void **v13; // rdx
  void **v14; // r8
  void **v15; // rcx
  void **v16; // rcx
  _BYTE *v17; // rax
  _BYTE *v18; // r8
  void **v19; // rax
  void **v20; // rax
  char v21; // cl
  _BYTE *v22; // rcx
  void ***v23; // rcx
  void ***v24; // rax
  __int64 v25; // r8
  __int64 v26; // rax
  void *v27; // rcx
  __int64 v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // r8
  _QWORD *v31; // rax
  void **v32; // rcx
  void ***v33; // rax
  _QWORD *v34; // r8
  void **v35; // rax
  _QWORD *v36; // rax
  void ***v37; // rax
  __int64 v38; // rax

  if ( a3[25] )
    std::_Xout_of_range("invalid map/set<T> iterator");
  v5 = a3 + 16;
  v6 = a3;
  v7 = (void **)*((_QWORD *)a3 + 2);
  v8 = a3;
  v9 = *((_BYTE *)v7 + 25);
  if ( v9 )
  {
    v12 = (void ***)(a3 + 8);
    for ( i = (char *)*((_QWORD *)a3 + 1); !i[25] && a3 == *((char **)i + 2); i = (char *)*((_QWORD *)i + 1) )
      a3 = i;
  }
  else
  {
    v10 = (char *)*v7;
    if ( *((_BYTE *)*v7 + 25) )
    {
      i = (char *)*((_QWORD *)a3 + 2);
    }
    else
    {
      do
      {
        i = v10;
        v10 = *(char **)v10;
      }
      while ( !v10[25] );
    }
    v12 = (void ***)(a3 + 8);
  }
  if ( *(_BYTE *)(*(_QWORD *)v6 + 25LL) )
    goto LABEL_16;
  if ( v9 )
  {
    v7 = *(void ***)v6;
LABEL_16:
    v13 = *v12;
    if ( !*((_BYTE *)v7 + 25) )
      v7[1] = v13;
    if ( *(char **)(*a1 + 8LL) == v6 )
    {
      *(_QWORD *)(*a1 + 8LL) = v7;
    }
    else if ( *v13 == v6 )
    {
      *v13 = v7;
    }
    else
    {
      v13[2] = v7;
    }
    if ( *(char **)*a1 == v6 )
    {
      if ( *((_BYTE *)v7 + 25) )
      {
        v14 = v13;
      }
      else
      {
        v15 = (void **)*v7;
        if ( *((_BYTE *)*v7 + 25) )
        {
          v14 = v7;
        }
        else
        {
          do
          {
            v14 = v15;
            v15 = (void **)*v15;
          }
          while ( !*((_BYTE *)v15 + 25) );
        }
      }
      *(_QWORD *)*a1 = v14;
    }
    if ( *(char **)(*a1 + 16LL) == v6 )
    {
      if ( *((_BYTE *)v7 + 25) )
      {
        v16 = v13;
      }
      else
      {
        v17 = v7[2];
        v16 = v7;
        while ( !v17[25] )
        {
          v16 = (void **)v16[2];
          v17 = v16[2];
        }
      }
      *(_QWORD *)(*a1 + 16LL) = v16;
    }
    v18 = v8 + 24;
    goto LABEL_50;
  }
  v7 = (void **)*((_QWORD *)i + 2);
  if ( i == v6 )
    goto LABEL_16;
  *(_QWORD *)(*(_QWORD *)v6 + 8LL) = i;
  *(_QWORD *)i = *(_QWORD *)v6;
  if ( i == *(char **)v5 )
  {
    v13 = (void **)i;
  }
  else
  {
    v13 = (void **)*((_QWORD *)i + 1);
    if ( !*((_BYTE *)v7 + 25) )
      v7[1] = v13;
    *v13 = v7;
    *((_QWORD *)i + 2) = *(_QWORD *)v5;
    *(_QWORD *)(*(_QWORD *)v5 + 8LL) = i;
  }
  if ( *(char **)(*a1 + 8LL) == v6 )
  {
    *(_QWORD *)(*a1 + 8LL) = i;
  }
  else
  {
    v19 = *v12;
    if ( **v12 == v6 )
      *v19 = i;
    else
      v19[2] = i;
  }
  v20 = *v12;
  v18 = v6 + 24;
  v21 = i[24];
  *((_QWORD *)i + 1) = v20;
  i[24] = v6[24];
  v6[24] = v21;
LABEL_50:
  if ( *v18 != 1 )
    goto LABEL_118;
  while ( v7 != *(void ***)(*a1 + 8LL) && *((_BYTE *)v7 + 24) == 1 )
  {
    v22 = *v13;
    if ( v7 == *v13 )
    {
      v22 = v13[2];
      if ( !v22[24] )
      {
        v22[24] = 1;
        v23 = (void ***)v13[2];
        *((_BYTE *)v13 + 24) = 0;
        v13[2] = *v23;
        if ( !*((_BYTE *)*v23 + 25) )
          (*v23)[1] = v13;
        v23[1] = (void **)v13[1];
        if ( v13 == *(void ***)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v23;
        }
        else
        {
          v24 = (void ***)v13[1];
          if ( v13 == *v24 )
            *v24 = (void **)v23;
          else
            v24[2] = (void **)v23;
        }
        *v23 = v13;
        v13[1] = v23;
        v22 = v13[2];
      }
      if ( !v22[25] )
      {
        if ( *(_BYTE *)(*(_QWORD *)v22 + 24LL) != 1 || *(_BYTE *)(*((_QWORD *)v22 + 2) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*((_QWORD *)v22 + 2) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v22 + 24LL) = 1;
            v25 = *(_QWORD *)v22;
            v22[24] = 0;
            *(_QWORD *)v22 = *(_QWORD *)(v25 + 16);
            v26 = *(_QWORD *)(v25 + 16);
            if ( !*(_BYTE *)(v26 + 25) )
              *(_QWORD *)(v26 + 8) = v22;
            *(_QWORD *)(v25 + 8) = *((_QWORD *)v22 + 1);
            if ( v22 == *(_BYTE **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v25;
            }
            else
            {
              v31 = (_QWORD *)*((_QWORD *)v22 + 1);
              if ( v22 == (_BYTE *)v31[2] )
                v31[2] = v25;
              else
                *v31 = v25;
            }
            *(_QWORD *)(v25 + 16) = v22;
            *((_QWORD *)v22 + 1) = v25;
            v22 = v13[2];
          }
          v22[24] = *((_BYTE *)v13 + 24);
          *((_BYTE *)v13 + 24) = 1;
          *(_BYTE *)(*((_QWORD *)v22 + 2) + 24LL) = 1;
          v32 = (void **)v13[2];
          v13[2] = *v32;
          if ( !*((_BYTE *)*v32 + 25) )
            *((_QWORD *)*v32 + 1) = v13;
          v32[1] = v13[1];
          if ( v13 == *(void ***)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v32;
          }
          else
          {
            v33 = (void ***)v13[1];
            if ( v13 == *v33 )
              *v33 = v32;
            else
              v33[2] = v32;
          }
          *v32 = v13;
LABEL_116:
          v13[1] = v32;
          break;
        }
LABEL_83:
        v22[24] = 0;
      }
    }
    else
    {
      if ( !v22[24] )
      {
        v22[24] = 1;
        v27 = *v13;
        *((_BYTE *)v13 + 24) = 0;
        *v13 = (void *)*((_QWORD *)v27 + 2);
        v28 = *((_QWORD *)v27 + 2);
        if ( !*(_BYTE *)(v28 + 25) )
          *(_QWORD *)(v28 + 8) = v13;
        *((_QWORD *)v27 + 1) = v13[1];
        if ( v13 == *(void ***)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v27;
        }
        else
        {
          v29 = v13[1];
          if ( v13 == (void **)v29[2] )
            v29[2] = v27;
          else
            *v29 = v27;
        }
        *((_QWORD *)v27 + 2) = v13;
        v13[1] = v27;
        v22 = *v13;
      }
      if ( !v22[25] )
      {
        v30 = *((_QWORD *)v22 + 2);
        if ( *(_BYTE *)(v30 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v22 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v22 + 24LL) == 1 )
          {
            *(_BYTE *)(v30 + 24) = 1;
            v34 = (_QWORD *)*((_QWORD *)v22 + 2);
            v22[24] = 0;
            *((_QWORD *)v22 + 2) = *v34;
            if ( !*(_BYTE *)(*v34 + 25LL) )
              *(_QWORD *)(*v34 + 8LL) = v22;
            v34[1] = *((_QWORD *)v22 + 1);
            if ( v22 == *(_BYTE **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v34;
            }
            else
            {
              v35 = (void **)*((_QWORD *)v22 + 1);
              if ( v22 == *v35 )
                *v35 = v34;
              else
                v35[2] = v34;
            }
            *v34 = v22;
            *((_QWORD *)v22 + 1) = v34;
            v22 = *v13;
          }
          v22[24] = *((_BYTE *)v13 + 24);
          *((_BYTE *)v13 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v22 + 24LL) = 1;
          v32 = (void **)*v13;
          *v13 = (void *)*((_QWORD *)*v13 + 2);
          v36 = v32[2];
          if ( !*((_BYTE *)v36 + 25) )
            v36[1] = v13;
          v32[1] = v13[1];
          if ( v13 == *(void ***)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v32;
          }
          else
          {
            v37 = (void ***)v13[1];
            if ( v13 == v37[2] )
              v37[2] = v32;
            else
              *v37 = v32;
          }
          v32[2] = v13;
          goto LABEL_116;
        }
        goto LABEL_83;
      }
    }
    v7 = v13;
    v13 = (void **)v13[1];
  }
  *((_BYTE *)v7 + 24) = 1;
LABEL_118:
  if ( *((_QWORD *)v6 + 7) >= 8u )
    operator delete(*((void **)v6 + 4));
  *((_QWORD *)v6 + 7) = 7;
  *((_QWORD *)v6 + 6) = 0;
  *((_WORD *)v6 + 16) = 0;
  operator delete(v6);
  v38 = a1[1];
  if ( v38 )
    a1[1] = v38 - 1;
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x1800211a0  push    rbx
0x1800211a2  push    rbp
0x1800211a3  push    rsi
0x1800211a4  push    rdi
0x1800211a5  push    r14
0x1800211a7  sub     rsp, 20h
0x1800211ab  xor     ebp, ebp
0x1800211ad  mov     r14, rdx
0x1800211b0  mov     rsi, rcx
0x1800211b3  cmp     [r8+19h], bpl
0x1800211b7  jnz     loc_180021637
0x1800211bd  lea     r10, [r8+10h]
0x1800211c1  mov     rdi, r8
0x1800211c4  mov     r9, [r10]
0x1800211c7  mov     r11, r8
0x1800211ca  mov     dl, [r9+19h]
0x1800211ce  test    dl, dl
0x1800211d0  jnz     short loc_1800211F5
0x1800211d2  mov     rcx, [r9]
0x1800211d5  cmp     [rcx+19h], bpl
0x1800211d9  jnz     short loc_1800211EC
0x1800211db  mov     rax, [rcx]
0x1800211de  mov     rbx, rcx
0x1800211e1  mov     rcx, rax
0x1800211e4  cmp     [rax+19h], bpl
0x1800211e8  jz      short loc_1800211DB
0x1800211ea  jmp     short loc_1800211EF
0x1800211ec  mov     rbx, r9
0x1800211ef  lea     rcx, [r8+8]
0x1800211f3  jmp     short loc_180021211
0x1800211f5  lea     rcx, [r8+8]
0x1800211f9  mov     rbx, [rcx]
0x1800211fc  jmp     short loc_18002120B
0x1800211fe  cmp     r8, [rbx+10h]
0x180021202  jnz     short loc_180021211
0x180021204  mov     r8, rbx
0x180021207  mov     rbx, [rbx+8]
0x18002120b  cmp     [rbx+19h], bpl
0x18002120f  jz      short loc_1800211FE
0x180021211  mov     rax, [rdi]
0x180021214  cmp     [rax+19h], bpl
0x180021218  jnz     short loc_180021230
0x18002121a  test    dl, dl
0x18002121c  jz      short loc_180021223
0x18002121e  mov     r9, rax
0x180021221  jmp     short loc_180021230
0x180021223  mov     r9, [rbx+10h]
0x180021227  cmp     rbx, rdi
0x18002122a  jnz     loc_1800212C2
0x180021230  mov     rdx, [rcx]
0x180021233  cmp     [r9+19h], bpl
0x180021237  jnz     short loc_18002123D
0x180021239  mov     [r9+8], rdx
0x18002123d  mov     rax, [rsi]
0x180021240  cmp     [rax+8], rdi
0x180021244  jnz     short loc_18002124C
0x180021246  mov     [rax+8], r9
0x18002124a  jmp     short loc_18002125A
0x18002124c  cmp     [rdx], rdi
0x18002124f  jnz     short loc_180021256
0x180021251  mov     [rdx], r9
0x180021254  jmp     short loc_18002125A
0x180021256  mov     [rdx+10h], r9
0x18002125a  mov     r10, [rsi]
0x18002125d  cmp     [r10], rdi
0x180021260  jnz     short loc_18002128D
0x180021262  cmp     [r9+19h], bpl
0x180021266  jz      short loc_18002126D
0x180021268  mov     r8, rdx
0x18002126b  jmp     short loc_18002128A
0x18002126d  mov     rcx, [r9]
0x180021270  cmp     [rcx+19h], bpl
0x180021274  jnz     short loc_180021287
0x180021276  mov     rax, [rcx]
0x180021279  mov     r8, rcx
0x18002127c  mov     rcx, rax
0x18002127f  cmp     [rax+19h], bpl
0x180021283  jz      short loc_180021276
0x180021285  jmp     short loc_18002128A
0x180021287  mov     r8, r9
0x18002128a  mov     [r10], r8
0x18002128d  mov     r8, [rsi]
0x180021290  cmp     [r8+10h], rdi
0x180021294  jnz     short loc_1800212BC
0x180021296  cmp     [r9+19h], bpl
0x18002129a  jz      short loc_1800212A1
0x18002129c  mov     rcx, rdx
0x18002129f  jmp     short loc_1800212B8
0x1800212a1  mov     rax, [r9+10h]
0x1800212a5  mov     rcx, r9
0x1800212a8  jmp     short loc_1800212B2
0x1800212aa  mov     rcx, [rcx+10h]
0x1800212ae  mov     rax, [rcx+10h]
0x1800212b2  cmp     [rax+19h], bpl
0x1800212b6  jz      short loc_1800212AA
0x1800212b8  mov     [r8+10h], rcx
0x1800212bc  lea     r8, [r11+18h]
0x1800212c0  jmp     short loc_18002132C
0x1800212c2  mov     [rax+8], rbx
0x1800212c6  mov     rax, [rdi]
0x1800212c9  mov     [rbx], rax
0x1800212cc  cmp     rbx, [r10]
0x1800212cf  jnz     short loc_1800212D6
0x1800212d1  mov     rdx, rbx
0x1800212d4  jmp     short loc_1800212F5
0x1800212d6  mov     rdx, [rbx+8]
0x1800212da  cmp     [r9+19h], bpl
0x1800212de  jnz     short loc_1800212E4
0x1800212e0  mov     [r9+8], rdx
0x1800212e4  mov     [rdx], r9
0x1800212e7  mov     rax, [r10]
0x1800212ea  mov     [rbx+10h], rax
0x1800212ee  mov     rax, [r10]
0x1800212f1  mov     [rax+8], rbx
0x1800212f5  mov     rax, [rsi]
0x1800212f8  cmp     [rax+8], rdi
0x1800212fc  jnz     short loc_180021304
0x1800212fe  mov     [rax+8], rbx
0x180021302  jmp     short loc_180021315
0x180021304  mov     rax, [rcx]
0x180021307  cmp     [rax], rdi
0x18002130a  jnz     short loc_180021311
0x18002130c  mov     [rax], rbx
0x18002130f  jmp     short loc_180021315
0x180021311  mov     [rax+10h], rbx
0x180021315  mov     rax, [rcx]
0x180021318  lea     r8, [rdi+18h]
0x18002131c  mov     cl, [rbx+18h]
0x18002131f  mov     [rbx+8], rax
0x180021323  mov     al, [r8]
0x180021326  mov     [rbx+18h], al
0x180021329  mov     [r8], cl
0x18002132c  mov     r11b, 1
0x18002132f  cmp     [r8], r11b
0x180021332  jnz     loc_1800215EC
0x180021338  jmp     loc_1800214A5
0x18002133d  cmp     [r9+18h], r11b
0x180021341  jnz     loc_1800215E8
0x180021347  mov     rcx, [rdx]
0x18002134a  cmp     r9, rcx
0x18002134d  jnz     loc_18002141E
0x180021353  mov     rcx, [rdx+10h]
0x180021357  cmp     [rcx+18h], bpl
0x18002135b  jnz     short loc_1800213B1
0x18002135d  mov     [rcx+18h], r11b
0x180021361  mov     rcx, [rdx+10h]
0x180021365  mov     [rdx+18h], bpl
0x180021369  mov     rax, [rcx]
0x18002136c  mov     [rdx+10h], rax
0x180021370  mov     rax, [rcx]
0x180021373  cmp     [rax+19h], bpl
0x180021377  jnz     short loc_18002137D
0x180021379  mov     [rax+8], rdx
0x18002137d  mov     rax, [rdx+8]
0x180021381  mov     [rcx+8], rax
0x180021385  mov     rax, [rsi]
0x180021388  cmp     rdx, [rax+8]
0x18002138c  jnz     short loc_180021394
0x18002138e  mov     [rax+8], rcx
0x180021392  jmp     short loc_1800213A6
0x180021394  mov     rax, [rdx+8]
0x180021398  cmp     rdx, [rax]
0x18002139b  jnz     short loc_1800213A2
0x18002139d  mov     [rax], rcx
0x1800213a0  jmp     short loc_1800213A6
0x1800213a2  mov     [rax+10h], rcx
0x1800213a6  mov     [rcx], rdx
0x1800213a9  mov     [rdx+8], rcx
0x1800213ad  mov     rcx, [rdx+10h]
0x1800213b1  cmp     [rcx+19h], bpl
0x1800213b5  jnz     loc_18002149E
0x1800213bb  mov     r10, [rcx]
0x1800213be  cmp     [r10+18h], r11b
0x1800213c2  jnz     short loc_1800213D2
0x1800213c4  mov     rax, [rcx+10h]
0x1800213c8  cmp     [rax+18h], r11b
0x1800213cc  jz      loc_18002149A
0x1800213d2  mov     rax, [rcx+10h]
0x1800213d6  cmp     [rax+18h], r11b
0x1800213da  jnz     loc_1800214D6
0x1800213e0  mov     [r10+18h], r11b
0x1800213e4  mov     r8, [rcx]
0x1800213e7  mov     [rcx+18h], bpl
0x1800213eb  mov     rax, [r8+10h]
0x1800213ef  mov     [rcx], rax
0x1800213f2  mov     rax, [r8+10h]
0x1800213f6  cmp     [rax+19h], bpl
0x1800213fa  jnz     short loc_180021400
0x1800213fc  mov     [rax+8], rcx
0x180021400  mov     rax, [rcx+8]
0x180021404  mov     [r8+8], rax
0x180021408  mov     rax, [rsi]
0x18002140b  cmp     rcx, [rax+8]
0x18002140f  jnz     loc_1800214B7
0x180021415  mov     [rax+8], r8
0x180021419  jmp     loc_1800214CA
0x18002141e  cmp     [rcx+18h], bpl
0x180021422  jnz     short loc_180021479
0x180021424  mov     [rcx+18h], r11b
0x180021428  mov     rcx, [rdx]
0x18002142b  mov     [rdx+18h], bpl
0x18002142f  mov     rax, [rcx+10h]
0x180021433  mov     [rdx], rax
0x180021436  mov     rax, [rcx+10h]
0x18002143a  cmp     [rax+19h], bpl
0x18002143e  jnz     short loc_180021444
0x180021440  mov     [rax+8], rdx
0x180021444  mov     rax, [rdx+8]
0x180021448  mov     [rcx+8], rax
0x18002144c  mov     rax, [rsi]
0x18002144f  cmp     rdx, [rax+8]
0x180021453  jnz     short loc_18002145B
0x180021455  mov     [rax+8], rcx
0x180021459  jmp     short loc_18002146E
0x18002145b  mov     rax, [rdx+8]
0x18002145f  cmp     rdx, [rax+10h]
0x180021463  jnz     short loc_18002146B
0x180021465  mov     [rax+10h], rcx
0x180021469  jmp     short loc_18002146E
0x18002146b  mov     [rax], rcx
0x18002146e  mov     [rcx+10h], rdx
0x180021472  mov     [rdx+8], rcx
0x180021476  mov     rcx, [rdx]
0x180021479  cmp     [rcx+19h], bpl
0x18002147d  jnz     short loc_18002149E
0x18002147f  mov     r8, [rcx+10h]
0x180021483  cmp     [r8+18h], r11b
0x180021487  jnz     loc_180021531
0x18002148d  mov     rax, [rcx]
0x180021490  cmp     [rax+18h], r11b
0x180021494  jnz     loc_180021531
0x18002149a  mov     [rcx+18h], bpl
0x18002149e  mov     r9, rdx
0x1800214a1  mov     rdx, [rdx+8]
0x1800214a5  mov     rax, [rsi]
0x1800214a8  cmp     r9, [rax+8]
0x1800214ac  jnz     loc_18002133D
0x1800214b2  jmp     loc_1800215E8
0x1800214b7  mov     rax, [rcx+8]
0x1800214bb  cmp     rcx, [rax+10h]
0x1800214bf  jnz     short loc_1800214C7
0x1800214c1  mov     [rax+10h], r8
0x1800214c5  jmp     short loc_1800214CA
0x1800214c7  mov     [rax], r8
0x1800214ca  mov     [r8+10h], rcx
0x1800214ce  mov     [rcx+8], r8
0x1800214d2  mov     rcx, [rdx+10h]
0x1800214d6  mov     al, [rdx+18h]
0x1800214d9  mov     [rcx+18h], al
0x1800214dc  mov     [rdx+18h], r11b
0x1800214e0  mov     rax, [rcx+10h]
0x1800214e4  mov     [rax+18h], r11b
0x1800214e8  mov     rcx, [rdx+10h]
0x1800214ec  mov     rax, [rcx]
0x1800214ef  mov     [rdx+10h], rax
0x1800214f3  mov     rax, [rcx]
0x1800214f6  cmp     [rax+19h], bpl
0x1800214fa  jnz     short loc_180021500
0x1800214fc  mov     [rax+8], rdx
0x180021500  mov     rax, [rdx+8]
0x180021504  mov     [rcx+8], rax
0x180021508  mov     rax, [rsi]
0x18002150b  cmp     rdx, [rax+8]
0x18002150f  jnz     short loc_180021517
0x180021511  mov     [rax+8], rcx
0x180021515  jmp     short loc_180021529
0x180021517  mov     rax, [rdx+8]
0x18002151b  cmp     rdx, [rax]
0x18002151e  jnz     short loc_180021525
0x180021520  mov     [rax], rcx
0x180021523  jmp     short loc_180021529
0x180021525  mov     [rax+10h], rcx
0x180021529  mov     [rcx], rdx
0x18002152c  jmp     loc_1800215E4
0x180021531  mov     rax, [rcx]
0x180021534  cmp     [rax+18h], r11b
0x180021538  jnz     short loc_18002158D
0x18002153a  mov     [r8+18h], r11b
0x18002153e  mov     r8, [rcx+10h]
0x180021542  mov     [rcx+18h], bpl
0x180021546  mov     rax, [r8]
0x180021549  mov     [rcx+10h], rax
0x18002154d  mov     rax, [r8]
0x180021550  cmp     [rax+19h], bpl
0x180021554  jnz     short loc_18002155A
0x180021556  mov     [rax+8], rcx
0x18002155a  mov     rax, [rcx+8]
0x18002155e  mov     [r8+8], rax
0x180021562  mov     rax, [rsi]
0x180021565  cmp     rcx, [rax+8]
0x180021569  jnz     short loc_180021571
0x18002156b  mov     [rax+8], r8
0x18002156f  jmp     short loc_180021583
0x180021571  mov     rax, [rcx+8]
0x180021575  cmp     rcx, [rax]
0x180021578  jnz     short loc_18002157F
0x18002157a  mov     [rax], r8
0x18002157d  jmp     short loc_180021583
0x18002157f  mov     [rax+10h], r8
0x180021583  mov     [r8], rcx
  ... truncated ...
```
