# std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>>>,std::_Iterator_base0>)

- ea: `0x1800116bc`
- end: `0x180011b19`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `1117`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f668`

## callees

- `0x1800116bc`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Extract(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v2; // r11
  _QWORD *v3; // r9
  _QWORD *v5; // rbx
  _QWORD *v6; // rbp
  _QWORD *v7; // rsi
  char v8; // r8
  _QWORD **v9; // r10
  _QWORD *i; // rax
  __int64 *v11; // rdx
  _QWORD *v12; // r8
  _QWORD *v13; // rdx
  __int64 *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  _BYTE *v17; // r10
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  char v20; // dl
  __int64 *v21; // rcx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 *v26; // rcx
  __int64 v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  _QWORD *v32; // rax
  __int64 *v33; // rdx
  __int64 **v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // rcx

  v2 = a2 + 2;
  v3 = (_QWORD *)a2[2];
  v5 = a2;
  v6 = a2;
  v7 = a2;
  v8 = *((_BYTE *)v3 + 25);
  if ( v8 )
  {
    v9 = (_QWORD **)(a2 + 1);
    for ( i = (_QWORD *)a2[1]; !*((_BYTE *)i + 25) && a2 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
      a2 = i;
  }
  else
  {
    v11 = (__int64 *)*v3;
    if ( *(_BYTE *)(*v3 + 25LL) )
    {
      i = v3;
    }
    else
    {
      do
      {
        i = v11;
        v11 = (__int64 *)*v11;
      }
      while ( !*((_BYTE *)v11 + 25) );
    }
    v9 = (_QWORD **)(v7 + 1);
  }
  if ( *(_BYTE *)(*v5 + 25LL) )
    goto LABEL_16;
  if ( v8 )
  {
    v3 = (_QWORD *)*v5;
LABEL_16:
    v12 = *v9;
    if ( !*((_BYTE *)v3 + 25) )
      v3[1] = v12;
    if ( *(_QWORD **)(*a1 + 8LL) == v6 )
    {
      *(_QWORD *)(*a1 + 8LL) = v3;
    }
    else if ( (_QWORD *)*v12 == v6 )
    {
      *v12 = v3;
    }
    else
    {
      v12[2] = v3;
    }
    if ( *(_QWORD **)*a1 == v6 )
    {
      if ( *((_BYTE *)v3 + 25) )
      {
        v13 = v12;
      }
      else
      {
        v14 = (__int64 *)*v3;
        if ( *(_BYTE *)(*v3 + 25LL) )
        {
          v13 = v3;
        }
        else
        {
          do
          {
            v13 = v14;
            v14 = (__int64 *)*v14;
          }
          while ( !*((_BYTE *)v14 + 25) );
        }
      }
      *(_QWORD *)*a1 = v13;
    }
    if ( *(_QWORD **)(*a1 + 16LL) == v6 )
    {
      if ( *((_BYTE *)v3 + 25) )
      {
        v15 = v12;
      }
      else
      {
        v16 = v3[2];
        v15 = v3;
        while ( !*(_BYTE *)(v16 + 25) )
        {
          v15 = (_QWORD *)v15[2];
          v16 = v15[2];
        }
      }
      *(_QWORD *)(*a1 + 16LL) = v15;
    }
    v17 = v7 + 3;
    goto LABEL_50;
  }
  v3 = (_QWORD *)i[2];
  if ( i == v6 )
    goto LABEL_16;
  *(_QWORD *)(*v5 + 8LL) = i;
  *i = *v5;
  if ( i == (_QWORD *)*v2 )
  {
    v12 = i;
  }
  else
  {
    v12 = (_QWORD *)i[1];
    if ( !*((_BYTE *)v3 + 25) )
      v3[1] = v12;
    *v12 = v3;
    i[2] = *v2;
    *(_QWORD *)(*v2 + 8LL) = i;
  }
  if ( *(_QWORD **)(*a1 + 8LL) == v6 )
  {
    *(_QWORD *)(*a1 + 8LL) = i;
  }
  else
  {
    v18 = *v9;
    if ( (_QWORD *)**v9 == v6 )
      *v18 = i;
    else
      v18[2] = i;
  }
  v19 = *v9;
  v17 = v6 + 3;
  v20 = *((_BYTE *)i + 24);
  i[1] = v19;
  *((_BYTE *)i + 24) = *((_BYTE *)v6 + 24);
  *((_BYTE *)v6 + 24) = v20;
LABEL_50:
  if ( *v17 != 1 )
    goto LABEL_118;
  while ( v3 != *(_QWORD **)(*a1 + 8LL) && *((_BYTE *)v3 + 24) == 1 )
  {
    v21 = (__int64 *)*v12;
    if ( v3 == (_QWORD *)*v12 )
    {
      v21 = (__int64 *)v12[2];
      if ( !*((_BYTE *)v21 + 24) )
      {
        *((_BYTE *)v21 + 24) = 1;
        v22 = (_QWORD *)v12[2];
        *((_BYTE *)v12 + 24) = 0;
        v12[2] = *v22;
        if ( !*(_BYTE *)(*v22 + 25LL) )
          *(_QWORD *)(*v22 + 8LL) = v12;
        v22[1] = v12[1];
        if ( v12 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v22;
        }
        else
        {
          v23 = (_QWORD *)v12[1];
          if ( v12 == (_QWORD *)*v23 )
            *v23 = v22;
          else
            v23[2] = v22;
        }
        *v22 = v12;
        v12[1] = v22;
        v21 = (__int64 *)v12[2];
      }
      if ( !*((_BYTE *)v21 + 25) )
      {
        if ( *(_BYTE *)(*v21 + 24) != 1 || *(_BYTE *)(v21[2] + 24) != 1 )
        {
          if ( *(_BYTE *)(v21[2] + 24) == 1 )
          {
            *(_BYTE *)(*v21 + 24) = 1;
            v24 = *v21;
            *((_BYTE *)v21 + 24) = 0;
            *v21 = *(_QWORD *)(v24 + 16);
            v25 = *(_QWORD *)(v24 + 16);
            if ( !*(_BYTE *)(v25 + 25) )
              *(_QWORD *)(v25 + 8) = v21;
            *(_QWORD *)(v24 + 8) = v21[1];
            if ( v21 == *(__int64 **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v24;
            }
            else
            {
              v30 = (_QWORD *)v21[1];
              if ( v21 == (__int64 *)v30[2] )
                v30[2] = v24;
              else
                *v30 = v24;
            }
            *(_QWORD *)(v24 + 16) = v21;
            v21[1] = v24;
            v21 = (__int64 *)v12[2];
          }
          *((_BYTE *)v21 + 24) = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = 1;
          *(_BYTE *)(v21[2] + 24) = 1;
          v31 = (_QWORD *)v12[2];
          v12[2] = *v31;
          if ( !*(_BYTE *)(*v31 + 25LL) )
            *(_QWORD *)(*v31 + 8LL) = v12;
          v31[1] = v12[1];
          if ( v12 == *(_QWORD **)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v31;
          }
          else
          {
            v32 = (_QWORD *)v12[1];
            if ( v12 == (_QWORD *)*v32 )
              *v32 = v31;
            else
              v32[2] = v31;
          }
          *v31 = v12;
LABEL_116:
          v12[1] = v31;
          break;
        }
LABEL_83:
        *((_BYTE *)v21 + 24) = 0;
      }
    }
    else
    {
      if ( !*((_BYTE *)v21 + 24) )
      {
        *((_BYTE *)v21 + 24) = 1;
        v26 = (__int64 *)*v12;
        *((_BYTE *)v12 + 24) = 0;
        *v12 = v26[2];
        v27 = v26[2];
        if ( !*(_BYTE *)(v27 + 25) )
          *(_QWORD *)(v27 + 8) = v12;
        v26[1] = v12[1];
        if ( v12 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v26;
        }
        else
        {
          v28 = (_QWORD *)v12[1];
          if ( v12 == (_QWORD *)v28[2] )
            v28[2] = v26;
          else
            *v28 = v26;
        }
        v26[2] = (__int64)v12;
        v12[1] = v26;
        v21 = (__int64 *)*v12;
      }
      if ( !*((_BYTE *)v21 + 25) )
      {
        v29 = v21[2];
        if ( *(_BYTE *)(v29 + 24) != 1 || *(_BYTE *)(*v21 + 24) != 1 )
        {
          if ( *(_BYTE *)(*v21 + 24) == 1 )
          {
            *(_BYTE *)(v29 + 24) = 1;
            v33 = (__int64 *)v21[2];
            *((_BYTE *)v21 + 24) = 0;
            v21[2] = *v33;
            if ( !*(_BYTE *)(*v33 + 25) )
              *(_QWORD *)(*v33 + 8) = v21;
            v33[1] = v21[1];
            if ( v21 == *(__int64 **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v33;
            }
            else
            {
              v34 = (__int64 **)v21[1];
              if ( v21 == *v34 )
                *v34 = v33;
              else
                v34[2] = v33;
            }
            *v33 = (__int64)v21;
            v21[1] = (__int64)v33;
            v21 = (__int64 *)*v12;
          }
          *((_BYTE *)v21 + 24) = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = 1;
          *(_BYTE *)(*v21 + 24) = 1;
          v31 = (_QWORD *)*v12;
          *v12 = *(_QWORD *)(*v12 + 16LL);
          v35 = v31[2];
          if ( !*(_BYTE *)(v35 + 25) )
            *(_QWORD *)(v35 + 8) = v12;
          v31[1] = v12[1];
          if ( v12 == *(_QWORD **)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v31;
          }
          else
          {
            v36 = (_QWORD *)v12[1];
            if ( v12 == (_QWORD *)v36[2] )
              v36[2] = v31;
            else
              *v36 = v31;
          }
          v31[2] = v12;
          goto LABEL_116;
        }
        goto LABEL_83;
      }
    }
    v3 = v12;
    v12 = (_QWORD *)v12[1];
  }
  *((_BYTE *)v3 + 24) = 1;
LABEL_118:
  v37 = a1[1];
  if ( v37 )
    a1[1] = v37 - 1;
  return v6;
}

```

## disassembly

```asm
0x1800116bc  push    rbx
0x1800116be  push    rbp
0x1800116bf  push    rsi
0x1800116c0  push    rdi
0x1800116c1  push    r14
0x1800116c3  lea     r11, [rdx+10h]
0x1800116c7  xor     r14d, r14d
0x1800116ca  mov     r9, [r11]
0x1800116cd  mov     rdi, rcx
0x1800116d0  mov     rbx, rdx
0x1800116d3  mov     rbp, rdx
0x1800116d6  mov     rsi, rdx
0x1800116d9  mov     r8b, [r9+19h]
0x1800116dd  test    r8b, r8b
0x1800116e0  jz      short loc_180011700
0x1800116e2  lea     r10, [rdx+8]
0x1800116e6  mov     rax, [r10]
0x1800116e9  jmp     short loc_1800116F8
0x1800116eb  cmp     rdx, [rax+10h]
0x1800116ef  jnz     short loc_180011721
0x1800116f1  mov     rdx, rax
0x1800116f4  mov     rax, [rax+8]
0x1800116f8  cmp     [rax+19h], r14b
0x1800116fc  jz      short loc_1800116EB
0x1800116fe  jmp     short loc_180011721
0x180011700  mov     rdx, [r9]
0x180011703  cmp     [rdx+19h], r14b
0x180011707  jnz     short loc_18001171A
0x180011709  mov     rcx, [rdx]
0x18001170c  mov     rax, rdx
0x18001170f  mov     rdx, rcx
0x180011712  cmp     [rcx+19h], r14b
0x180011716  jz      short loc_180011709
0x180011718  jmp     short loc_18001171D
0x18001171a  mov     rax, r9
0x18001171d  lea     r10, [rsi+8]
0x180011721  mov     rcx, [rbx]
0x180011724  cmp     [rcx+19h], r14b
0x180011728  jnz     short loc_180011741
0x18001172a  test    r8b, r8b
0x18001172d  jz      short loc_180011734
0x18001172f  mov     r9, rcx
0x180011732  jmp     short loc_180011741
0x180011734  mov     r9, [rax+10h]
0x180011738  cmp     rax, rbp
0x18001173b  jnz     loc_1800117D3
0x180011741  mov     r8, [r10]
0x180011744  cmp     [r9+19h], r14b
0x180011748  jnz     short loc_18001174E
0x18001174a  mov     [r9+8], r8
0x18001174e  mov     rax, [rdi]
0x180011751  cmp     [rax+8], rbp
0x180011755  jnz     short loc_18001175D
0x180011757  mov     [rax+8], r9
0x18001175b  jmp     short loc_18001176B
0x18001175d  cmp     [r8], rbp
0x180011760  jnz     short loc_180011767
0x180011762  mov     [r8], r9
0x180011765  jmp     short loc_18001176B
0x180011767  mov     [r8+10h], r9
0x18001176b  mov     r10, [rdi]
0x18001176e  cmp     [r10], rbp
0x180011771  jnz     short loc_18001179E
0x180011773  cmp     [r9+19h], r14b
0x180011777  jz      short loc_18001177E
0x180011779  mov     rdx, r8
0x18001177c  jmp     short loc_18001179B
0x18001177e  mov     rcx, [r9]
0x180011781  cmp     [rcx+19h], r14b
0x180011785  jnz     short loc_180011798
0x180011787  mov     rax, [rcx]
0x18001178a  mov     rdx, rcx
0x18001178d  mov     rcx, rax
0x180011790  cmp     [rax+19h], r14b
0x180011794  jz      short loc_180011787
0x180011796  jmp     short loc_18001179B
0x180011798  mov     rdx, r9
0x18001179b  mov     [r10], rdx
0x18001179e  mov     rdx, [rdi]
0x1800117a1  cmp     [rdx+10h], rbp
0x1800117a5  jnz     short loc_1800117CD
0x1800117a7  cmp     [r9+19h], r14b
0x1800117ab  jz      short loc_1800117B2
0x1800117ad  mov     rcx, r8
0x1800117b0  jmp     short loc_1800117C9
0x1800117b2  mov     rax, [r9+10h]
0x1800117b6  mov     rcx, r9
0x1800117b9  jmp     short loc_1800117C3
0x1800117bb  mov     rcx, [rcx+10h]
0x1800117bf  mov     rax, [rcx+10h]
0x1800117c3  cmp     [rax+19h], r14b
0x1800117c7  jz      short loc_1800117BB
0x1800117c9  mov     [rdx+10h], rcx
0x1800117cd  lea     r10, [rsi+18h]
0x1800117d1  jmp     short loc_18001183D
0x1800117d3  mov     [rcx+8], rax
0x1800117d7  mov     rcx, [rbx]
0x1800117da  mov     [rax], rcx
0x1800117dd  cmp     rax, [r11]
0x1800117e0  jnz     short loc_1800117E7
0x1800117e2  mov     r8, rax
0x1800117e5  jmp     short loc_180011806
0x1800117e7  mov     r8, [rax+8]
0x1800117eb  cmp     [r9+19h], r14b
0x1800117ef  jnz     short loc_1800117F5
0x1800117f1  mov     [r9+8], r8
0x1800117f5  mov     [r8], r9
0x1800117f8  mov     rcx, [r11]
0x1800117fb  mov     [rax+10h], rcx
0x1800117ff  mov     rcx, [r11]
0x180011802  mov     [rcx+8], rax
0x180011806  mov     rcx, [rdi]
0x180011809  cmp     [rcx+8], rbp
0x18001180d  jnz     short loc_180011815
0x18001180f  mov     [rcx+8], rax
0x180011813  jmp     short loc_180011826
0x180011815  mov     rcx, [r10]
0x180011818  cmp     [rcx], rbp
0x18001181b  jnz     short loc_180011822
0x18001181d  mov     [rcx], rax
0x180011820  jmp     short loc_180011826
0x180011822  mov     [rcx+10h], rax
0x180011826  mov     rcx, [r10]
0x180011829  lea     r10, [rbp+18h]
0x18001182d  mov     dl, [rax+18h]
0x180011830  mov     [rax+8], rcx
0x180011834  mov     cl, [r10]
0x180011837  mov     [rax+18h], cl
0x18001183a  mov     [r10], dl
0x18001183d  mov     r11b, 1
0x180011840  cmp     [r10], r11b
0x180011843  jnz     loc_180011AFF
0x180011849  jmp     loc_1800119B6
0x18001184e  cmp     [r9+18h], r11b
0x180011852  jnz     loc_180011AFB
0x180011858  mov     rcx, [r8]
0x18001185b  cmp     r9, rcx
0x18001185e  jnz     loc_18001192F
0x180011864  mov     rcx, [r8+10h]
0x180011868  cmp     [rcx+18h], r14b
0x18001186c  jnz     short loc_1800118C2
0x18001186e  mov     [rcx+18h], r11b
0x180011872  mov     rcx, [r8+10h]
0x180011876  mov     [r8+18h], r14b
0x18001187a  mov     rax, [rcx]
0x18001187d  mov     [r8+10h], rax
0x180011881  mov     rax, [rcx]
0x180011884  cmp     [rax+19h], r14b
0x180011888  jnz     short loc_18001188E
0x18001188a  mov     [rax+8], r8
0x18001188e  mov     rax, [r8+8]
0x180011892  mov     [rcx+8], rax
0x180011896  mov     rax, [rdi]
0x180011899  cmp     r8, [rax+8]
0x18001189d  jnz     short loc_1800118A5
0x18001189f  mov     [rax+8], rcx
0x1800118a3  jmp     short loc_1800118B7
0x1800118a5  mov     rax, [r8+8]
0x1800118a9  cmp     r8, [rax]
0x1800118ac  jnz     short loc_1800118B3
0x1800118ae  mov     [rax], rcx
0x1800118b1  jmp     short loc_1800118B7
0x1800118b3  mov     [rax+10h], rcx
0x1800118b7  mov     [rcx], r8
0x1800118ba  mov     [r8+8], rcx
0x1800118be  mov     rcx, [r8+10h]
0x1800118c2  cmp     [rcx+19h], r14b
0x1800118c6  jnz     loc_1800119AF
0x1800118cc  mov     r10, [rcx]
0x1800118cf  cmp     [r10+18h], r11b
0x1800118d3  jnz     short loc_1800118E3
0x1800118d5  mov     rax, [rcx+10h]
0x1800118d9  cmp     [rax+18h], r11b
0x1800118dd  jz      loc_1800119AB
0x1800118e3  mov     rax, [rcx+10h]
0x1800118e7  cmp     [rax+18h], r11b
0x1800118eb  jnz     loc_1800119E7
0x1800118f1  mov     [r10+18h], r11b
0x1800118f5  mov     rdx, [rcx]
0x1800118f8  mov     [rcx+18h], r14b
0x1800118fc  mov     rax, [rdx+10h]
0x180011900  mov     [rcx], rax
0x180011903  mov     rax, [rdx+10h]
0x180011907  cmp     [rax+19h], r14b
0x18001190b  jnz     short loc_180011911
0x18001190d  mov     [rax+8], rcx
0x180011911  mov     rax, [rcx+8]
0x180011915  mov     [rdx+8], rax
0x180011919  mov     rax, [rdi]
0x18001191c  cmp     rcx, [rax+8]
0x180011920  jnz     loc_1800119C8
0x180011926  mov     [rax+8], rdx
0x18001192a  jmp     loc_1800119DB
0x18001192f  cmp     [rcx+18h], r14b
0x180011933  jnz     short loc_18001198A
0x180011935  mov     [rcx+18h], r11b
0x180011939  mov     rcx, [r8]
0x18001193c  mov     [r8+18h], r14b
0x180011940  mov     rax, [rcx+10h]
0x180011944  mov     [r8], rax
0x180011947  mov     rax, [rcx+10h]
0x18001194b  cmp     [rax+19h], r14b
0x18001194f  jnz     short loc_180011955
0x180011951  mov     [rax+8], r8
0x180011955  mov     rax, [r8+8]
0x180011959  mov     [rcx+8], rax
0x18001195d  mov     rax, [rdi]
0x180011960  cmp     r8, [rax+8]
0x180011964  jnz     short loc_18001196C
0x180011966  mov     [rax+8], rcx
0x18001196a  jmp     short loc_18001197F
0x18001196c  mov     rax, [r8+8]
0x180011970  cmp     r8, [rax+10h]
0x180011974  jnz     short loc_18001197C
0x180011976  mov     [rax+10h], rcx
0x18001197a  jmp     short loc_18001197F
0x18001197c  mov     [rax], rcx
0x18001197f  mov     [rcx+10h], r8
0x180011983  mov     [r8+8], rcx
0x180011987  mov     rcx, [r8]
0x18001198a  cmp     [rcx+19h], r14b
0x18001198e  jnz     short loc_1800119AF
0x180011990  mov     rdx, [rcx+10h]
0x180011994  cmp     [rdx+18h], r11b
0x180011998  jnz     loc_180011A43
0x18001199e  mov     rax, [rcx]
0x1800119a1  cmp     [rax+18h], r11b
0x1800119a5  jnz     loc_180011A43
0x1800119ab  mov     [rcx+18h], r14b
0x1800119af  mov     r9, r8
0x1800119b2  mov     r8, [r8+8]
0x1800119b6  mov     rax, [rdi]
0x1800119b9  cmp     r9, [rax+8]
0x1800119bd  jnz     loc_18001184E
0x1800119c3  jmp     loc_180011AFB
0x1800119c8  mov     rax, [rcx+8]
0x1800119cc  cmp     rcx, [rax+10h]
0x1800119d0  jnz     short loc_1800119D8
0x1800119d2  mov     [rax+10h], rdx
0x1800119d6  jmp     short loc_1800119DB
0x1800119d8  mov     [rax], rdx
0x1800119db  mov     [rdx+10h], rcx
0x1800119df  mov     [rcx+8], rdx
0x1800119e3  mov     rcx, [r8+10h]
0x1800119e7  mov     al, [r8+18h]
0x1800119eb  mov     [rcx+18h], al
0x1800119ee  mov     [r8+18h], r11b
0x1800119f2  mov     rax, [rcx+10h]
0x1800119f6  mov     [rax+18h], r11b
0x1800119fa  mov     rcx, [r8+10h]
0x1800119fe  mov     rax, [rcx]
0x180011a01  mov     [r8+10h], rax
0x180011a05  mov     rax, [rcx]
0x180011a08  cmp     [rax+19h], r14b
0x180011a0c  jnz     short loc_180011A12
0x180011a0e  mov     [rax+8], r8
0x180011a12  mov     rax, [r8+8]
0x180011a16  mov     [rcx+8], rax
0x180011a1a  mov     rax, [rdi]
0x180011a1d  cmp     r8, [rax+8]
0x180011a21  jnz     short loc_180011A29
0x180011a23  mov     [rax+8], rcx
0x180011a27  jmp     short loc_180011A3B
0x180011a29  mov     rax, [r8+8]
0x180011a2d  cmp     r8, [rax]
0x180011a30  jnz     short loc_180011A37
0x180011a32  mov     [rax], rcx
0x180011a35  jmp     short loc_180011A3B
0x180011a37  mov     [rax+10h], rcx
0x180011a3b  mov     [rcx], r8
0x180011a3e  jmp     loc_180011AF7
0x180011a43  mov     rax, [rcx]
0x180011a46  cmp     [rax+18h], r11b
0x180011a4a  jnz     short loc_180011A9F
0x180011a4c  mov     [rdx+18h], r11b
0x180011a50  mov     rdx, [rcx+10h]
0x180011a54  mov     [rcx+18h], r14b
0x180011a58  mov     rax, [rdx]
0x180011a5b  mov     [rcx+10h], rax
0x180011a5f  mov     rax, [rdx]
0x180011a62  cmp     [rax+19h], r14b
0x180011a66  jnz     short loc_180011A6C
0x180011a68  mov     [rax+8], rcx
0x180011a6c  mov     rax, [rcx+8]
0x180011a70  mov     [rdx+8], rax
0x180011a74  mov     rax, [rdi]
0x180011a77  cmp     rcx, [rax+8]
0x180011a7b  jnz     short loc_180011A83
0x180011a7d  mov     [rax+8], rdx
0x180011a81  jmp     short loc_180011A95
0x180011a83  mov     rax, [rcx+8]
0x180011a87  cmp     rcx, [rax]
0x180011a8a  jnz     short loc_180011A91
0x180011a8c  mov     [rax], rdx
0x180011a8f  jmp     short loc_180011A95
0x180011a91  mov     [rax+10h], rdx
0x180011a95  mov     [rdx], rcx
0x180011a98  mov     [rcx+8], rdx
0x180011a9c  mov     rcx, [r8]
0x180011a9f  mov     al, [r8+18h]
  ... truncated ...
```
