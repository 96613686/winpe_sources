# std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>>,std::_Iterator_base0>)

- ea: `0x1800117f0`
- end: `0x180011d54`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `1380`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800190b0`

## callees

- `0x1800117f0`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>>::_Extract(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v2; // r9
  _QWORD *v4; // r8
  _QWORD *v5; // rbx
  _QWORD *v6; // rsi
  char v7; // r11
  _QWORD *v8; // rbp
  __int64 *v9; // rdx
  _QWORD *v10; // rax
  _QWORD **i; // rdi
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  _BYTE *v14; // r11
  char v15; // r8
  _QWORD *v16; // r8
  _QWORD *j; // r8
  __int64 v18; // rcx
  _QWORD *result; // rax
  __int64 *v20; // rdx
  __int64 *v21; // rdx
  __int64 v22; // rax
  _QWORD *v23; // rax
  __int64 v24; // r8
  __int64 *v25; // r8
  __int64 **v26; // rax
  _QWORD *v27; // rdx
  _QWORD *v28; // rax
  __int64 *v29; // r11
  __int64 v30; // r8
  __int64 v31; // rax
  _QWORD *v32; // rax
  _QWORD *v33; // rdx
  _QWORD *v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rax

  v2 = (_QWORD *)a2[2];
  v4 = a2;
  v5 = a2;
  v6 = a2 + 2;
  v7 = *((_BYTE *)v2 + 25);
  v8 = a2;
  if ( v7 )
  {
    v10 = (_QWORD *)a2[1];
    for ( i = (_QWORD **)(a2 + 1); !*((_BYTE *)v10 + 25); v10 = (_QWORD *)v10[1] )
    {
      if ( a2 != (_QWORD *)v10[2] )
        break;
      a2 = v10;
    }
  }
  else
  {
    v9 = (__int64 *)*v2;
    if ( *(_BYTE *)(*v2 + 25LL) )
    {
      v10 = v2;
    }
    else
    {
      do
      {
        v10 = v9;
        v9 = (__int64 *)*v9;
      }
      while ( !*((_BYTE *)v9 + 25) );
    }
    i = (_QWORD **)(v8 + 1);
  }
  if ( !*(_BYTE *)(*v4 + 25LL) )
  {
    if ( v7 )
    {
      v2 = (_QWORD *)*v4;
    }
    else
    {
      v2 = (_QWORD *)v10[2];
      if ( v10 != v5 )
      {
        *(_QWORD *)(*v4 + 8LL) = v10;
        *v10 = *v4;
        if ( v10 == (_QWORD *)*v6 )
        {
          v12 = v10;
        }
        else
        {
          v12 = (_QWORD *)v10[1];
          if ( !*((_BYTE *)v2 + 25) )
            v2[1] = v12;
          *v12 = v2;
          v10[2] = *v6;
          *(_QWORD *)(*v6 + 8LL) = v10;
        }
        if ( *(_QWORD **)(*a1 + 8LL) == v5 )
        {
          *(_QWORD *)(*a1 + 8LL) = v10;
        }
        else
        {
          v13 = *i;
          if ( (_QWORD *)**i == v5 )
            *v13 = v10;
          else
            v13[2] = v10;
        }
        v14 = v5 + 3;
        v10[1] = *i;
        v15 = *((_BYTE *)v10 + 24);
        *((_BYTE *)v10 + 24) = *((_BYTE *)v5 + 24);
        *((_BYTE *)v5 + 24) = v15;
        goto LABEL_28;
      }
    }
  }
  v12 = *i;
  if ( !*((_BYTE *)v2 + 25) )
    v2[1] = v12;
  if ( *(_QWORD **)(*a1 + 8LL) == v5 )
  {
    *(_QWORD *)(*a1 + 8LL) = v2;
  }
  else if ( (_QWORD *)*v12 == v5 )
  {
    *v12 = v2;
  }
  else
  {
    v12[2] = v2;
  }
  if ( *(_QWORD **)*a1 == v5 )
  {
    if ( *((_BYTE *)v2 + 25) )
    {
      v16 = v12;
    }
    else
    {
      v29 = (__int64 *)*v2;
      if ( *(_BYTE *)(*v2 + 25LL) )
      {
        v16 = v2;
      }
      else
      {
        do
        {
          v16 = v29;
          v29 = (__int64 *)*v29;
        }
        while ( !*((_BYTE *)v29 + 25) );
      }
    }
    *(_QWORD *)*a1 = v16;
  }
  if ( *(_QWORD **)(*a1 + 16LL) == v5 )
  {
    if ( *((_BYTE *)v2 + 25) )
    {
      j = v12;
    }
    else
    {
      for ( j = v2; !*(_BYTE *)(j[2] + 25LL); j = (_QWORD *)j[2] )
        ;
    }
    *(_QWORD *)(*a1 + 16LL) = j;
  }
  v14 = v8 + 3;
LABEL_28:
  if ( *v14 != 1 )
    goto LABEL_29;
  while ( 1 )
  {
    if ( v2 == *(_QWORD **)(*a1 + 8LL) || *((_BYTE *)v2 + 24) != 1 )
      goto LABEL_93;
    v20 = (__int64 *)*v12;
    if ( v2 == (_QWORD *)*v12 )
      break;
    if ( !*((_BYTE *)v20 + 24) )
    {
      *((_BYTE *)v20 + 24) = 1;
      v21 = (__int64 *)*v12;
      *((_BYTE *)v12 + 24) = 0;
      *v12 = v21[2];
      v22 = v21[2];
      if ( !*(_BYTE *)(v22 + 25) )
        *(_QWORD *)(v22 + 8) = v12;
      v21[1] = v12[1];
      if ( v12 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v21;
      }
      else
      {
        v23 = (_QWORD *)v12[1];
        if ( v12 == (_QWORD *)v23[2] )
          v23[2] = v21;
        else
          *v23 = v21;
      }
      v21[2] = (__int64)v12;
      v12[1] = v21;
      v20 = (__int64 *)*v12;
    }
    if ( !*((_BYTE *)v20 + 25) )
    {
      v24 = v20[2];
      if ( *(_BYTE *)(v24 + 24) != 1 || *(_BYTE *)(*v20 + 24) != 1 )
      {
        if ( *(_BYTE *)(*v20 + 24) == 1 )
        {
          *(_BYTE *)(v24 + 24) = 1;
          v25 = (__int64 *)v20[2];
          *((_BYTE *)v20 + 24) = 0;
          v20[2] = *v25;
          if ( !*(_BYTE *)(*v25 + 25) )
            *(_QWORD *)(*v25 + 8) = v20;
          v25[1] = v20[1];
          if ( v20 == *(__int64 **)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v25;
          }
          else
          {
            v26 = (__int64 **)v20[1];
            if ( v20 == *v26 )
              *v26 = v25;
            else
              v26[2] = v25;
          }
          *v25 = (__int64)v20;
          v20[1] = (__int64)v25;
          v20 = (__int64 *)*v12;
        }
        *((_BYTE *)v20 + 24) = *((_BYTE *)v12 + 24);
        *((_BYTE *)v12 + 24) = 1;
        *(_BYTE *)(*v20 + 24) = 1;
        v33 = (_QWORD *)*v12;
        *v12 = *(_QWORD *)(*v12 + 16LL);
        v35 = v33[2];
        if ( !*(_BYTE *)(v35 + 25) )
          *(_QWORD *)(v35 + 8) = v12;
        v33[1] = v12[1];
        if ( v12 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v33;
          v33[2] = v12;
        }
        else
        {
          v36 = (_QWORD *)v12[1];
          if ( v12 == (_QWORD *)v36[2] )
            v36[2] = v33;
          else
            *v36 = v33;
          v33[2] = v12;
        }
        goto LABEL_92;
      }
      goto LABEL_115;
    }
LABEL_116:
    v2 = v12;
    v12 = (_QWORD *)v12[1];
  }
  v20 = (__int64 *)v12[2];
  if ( !*((_BYTE *)v20 + 24) )
  {
    *((_BYTE *)v20 + 24) = 1;
    v27 = (_QWORD *)v12[2];
    *((_BYTE *)v12 + 24) = 0;
    v12[2] = *v27;
    if ( !*(_BYTE *)(*v27 + 25LL) )
      *(_QWORD *)(*v27 + 8LL) = v12;
    v27[1] = v12[1];
    if ( v12 == *(_QWORD **)(*a1 + 8LL) )
    {
      *(_QWORD *)(*a1 + 8LL) = v27;
    }
    else
    {
      v28 = (_QWORD *)v12[1];
      if ( v12 == (_QWORD *)*v28 )
        *v28 = v27;
      else
        v28[2] = v27;
    }
    *v27 = v12;
    v12[1] = v27;
    v20 = (__int64 *)v12[2];
  }
  if ( *((_BYTE *)v20 + 25) )
    goto LABEL_116;
  if ( *(_BYTE *)(*v20 + 24) == 1 && *(_BYTE *)(v20[2] + 24) == 1 )
  {
LABEL_115:
    *((_BYTE *)v20 + 24) = 0;
    goto LABEL_116;
  }
  if ( *(_BYTE *)(v20[2] + 24) == 1 )
  {
    *(_BYTE *)(*v20 + 24) = 1;
    v30 = *v20;
    *((_BYTE *)v20 + 24) = 0;
    *v20 = *(_QWORD *)(v30 + 16);
    v31 = *(_QWORD *)(v30 + 16);
    if ( !*(_BYTE *)(v31 + 25) )
      *(_QWORD *)(v31 + 8) = v20;
    *(_QWORD *)(v30 + 8) = v20[1];
    if ( v20 == *(__int64 **)(*a1 + 8LL) )
    {
      *(_QWORD *)(*a1 + 8LL) = v30;
    }
    else
    {
      v32 = (_QWORD *)v20[1];
      if ( v20 == (__int64 *)v32[2] )
        v32[2] = v30;
      else
        *v32 = v30;
    }
    *(_QWORD *)(v30 + 16) = v20;
    v20[1] = v30;
    v20 = (__int64 *)v12[2];
  }
  *((_BYTE *)v20 + 24) = *((_BYTE *)v12 + 24);
  *((_BYTE *)v12 + 24) = 1;
  *(_BYTE *)(v20[2] + 24) = 1;
  v33 = (_QWORD *)v12[2];
  v12[2] = *v33;
  if ( !*(_BYTE *)(*v33 + 25LL) )
    *(_QWORD *)(*v33 + 8LL) = v12;
  v33[1] = v12[1];
  if ( v12 != *(_QWORD **)(*a1 + 8LL) )
  {
    v34 = (_QWORD *)v12[1];
    if ( v12 == (_QWORD *)*v34 )
      *v34 = v33;
    else
      v34[2] = v33;
    *v33 = v12;
LABEL_92:
    v12[1] = v33;
LABEL_93:
    *((_BYTE *)v2 + 24) = 1;
    goto LABEL_29;
  }
  *(_QWORD *)(*a1 + 8LL) = v33;
  *v33 = v12;
  v12[1] = v33;
  *((_BYTE *)v2 + 24) = 1;
LABEL_29:
  v18 = a1[1];
  result = v5;
  if ( v18 )
    a1[1] = v18 - 1;
  return result;
}

```

## disassembly

```asm
0x1800117f0  push    rbx
0x1800117f2  mov     r9, [rdx+10h]
0x1800117f6  mov     r10, rcx
0x1800117f9  mov     [rsp+8+arg_0], rbp
0x1800117fe  mov     r8, rdx
0x180011801  mov     [rsp+8+arg_8], rsi
0x180011806  mov     rbx, rdx
0x180011809  lea     rsi, [rdx+10h]
0x18001180d  mov     [rsp+8+arg_10], rdi
0x180011812  movzx   r11d, byte ptr [r9+19h]
0x180011817  mov     rbp, rdx
0x18001181a  test    r11b, r11b
0x18001181d  jnz     loc_180011D0C
0x180011823  mov     rdx, [r9]
0x180011826  cmp     [rdx+19h], r11b
0x18001182a  jnz     loc_180011935
0x180011830  mov     rcx, [rdx]
0x180011833  mov     rax, rdx
0x180011836  mov     rdx, rcx
0x180011839  cmp     byte ptr [rcx+19h], 0
0x18001183d  jz      short loc_180011830
0x18001183f  lea     rdi, [rbp+8]
0x180011843  mov     rcx, [r8]
0x180011846  cmp     byte ptr [rcx+19h], 0
0x18001184a  jnz     short loc_1800118AC
0x18001184c  test    r11b, r11b
0x18001184f  jnz     loc_180011D3C
0x180011855  mov     r9, [rax+10h]
0x180011859  cmp     rax, rbx
0x18001185c  jz      short loc_1800118AC
0x18001185e  mov     [rcx+8], rax
0x180011862  mov     rcx, [r8]
0x180011865  mov     [rax], rcx
0x180011868  cmp     rax, [rsi]
0x18001186b  jnz     loc_180011A40
0x180011871  mov     rcx, rax
0x180011874  mov     rdx, [r10]
0x180011877  cmp     [rdx+8], rbx
0x18001187b  jz      loc_180011A65
0x180011881  mov     rdx, [rdi]
0x180011884  cmp     [rdx], rbx
0x180011887  jnz     loc_180011B0B
0x18001188d  mov     [rdx], rax
0x180011890  mov     rdx, [rdi]
0x180011893  lea     r11, [rbx+18h]
0x180011897  mov     [rax+8], rdx
0x18001189b  movzx   edx, byte ptr [r11]
0x18001189f  movzx   r8d, byte ptr [rax+18h]
0x1800118a4  mov     [rax+18h], dl
0x1800118a7  mov     [r11], r8b
0x1800118aa  jmp     short loc_18001190B
0x1800118ac  cmp     byte ptr [r9+19h], 0
0x1800118b1  mov     rcx, [rdi]
0x1800118b4  jnz     short loc_1800118BA
0x1800118b6  mov     [r9+8], rcx
0x1800118ba  mov     rax, [r10]
0x1800118bd  cmp     [rax+8], rbx
0x1800118c1  jz      loc_180011A37
0x1800118c7  cmp     [rcx], rbx
0x1800118ca  jnz     loc_180011AC0
0x1800118d0  mov     [rcx], r9
0x1800118d3  mov     rdx, [r10]
0x1800118d6  cmp     [rdx], rbx
0x1800118d9  jnz     short loc_1800118EC
0x1800118db  cmp     byte ptr [r9+19h], 0
0x1800118e0  jz      loc_180011AC9
0x1800118e6  mov     r8, rcx
0x1800118e9  mov     [rdx], r8
0x1800118ec  mov     rdx, [r10]
0x1800118ef  cmp     [rdx+10h], rbx
0x1800118f3  jnz     short loc_180011907
0x1800118f5  cmp     byte ptr [r9+19h], 0
0x1800118fa  jz      loc_180011AE7
0x180011900  mov     r8, rcx
0x180011903  mov     [rdx+10h], r8
0x180011907  lea     r11, [rbp+18h]
0x18001190b  cmp     byte ptr [r11], 1
0x18001190f  mov     rdi, [rsp+8+arg_10]
0x180011914  mov     rsi, [rsp+8+arg_8]
0x180011919  mov     rbp, [rsp+8+arg_0]
0x18001191e  jz      short loc_180011940
0x180011920  mov     rcx, [r10+8]
0x180011924  mov     rax, rbx
0x180011927  test    rcx, rcx
0x18001192a  jz      short loc_180011933
0x18001192c  dec     rcx
0x18001192f  mov     [r10+8], rcx
0x180011933  pop     rbx
0x180011934  retn
0x180011935  mov     rax, r9
0x180011938  jmp     loc_18001183F
0x180011940  mov     rax, [r10]
0x180011943  cmp     r9, [rax+8]
0x180011947  jz      loc_180011C1B
0x18001194d  cmp     byte ptr [r9+18h], 1
0x180011952  jnz     loc_180011C1B
0x180011958  mov     rdx, [rcx]
0x18001195b  cmp     r9, rdx
0x18001195e  jz      loc_180011A6E
0x180011964  cmp     byte ptr [rdx+18h], 0
0x180011968  jnz     short loc_1800119BC
0x18001196a  mov     byte ptr [rdx+18h], 1
0x18001196e  mov     rdx, [rcx]
0x180011971  mov     byte ptr [rcx+18h], 0
0x180011975  mov     rax, [rdx+10h]
0x180011979  mov     [rcx], rax
0x18001197c  mov     rax, [rdx+10h]
0x180011980  cmp     byte ptr [rax+19h], 0
0x180011984  jz      loc_180011B14
0x18001198a  mov     rax, [rcx+8]
0x18001198e  mov     [rdx+8], rax
0x180011992  mov     rax, [r10]
0x180011995  cmp     rcx, [rax+8]
0x180011999  jz      loc_180011B1D
0x18001199f  mov     rax, [rcx+8]
0x1800119a3  cmp     rcx, [rax+10h]
0x1800119a7  jnz     loc_180011B26
0x1800119ad  mov     [rax+10h], rdx
0x1800119b1  mov     [rdx+10h], rcx
0x1800119b5  mov     [rcx+8], rdx
0x1800119b9  mov     rdx, [rcx]
0x1800119bc  cmp     byte ptr [rdx+19h], 0
0x1800119c0  jnz     loc_180011D48
0x1800119c6  mov     r8, [rdx+10h]
0x1800119ca  cmp     byte ptr [r8+18h], 1
0x1800119cf  jnz     short loc_1800119DE
0x1800119d1  mov     rax, [rdx]
0x1800119d4  cmp     byte ptr [rax+18h], 1
0x1800119d8  jz      loc_180011D44
0x1800119de  mov     rax, [rdx]
0x1800119e1  cmp     byte ptr [rax+18h], 1
0x1800119e5  jnz     loc_180011C32
0x1800119eb  mov     byte ptr [r8+18h], 1
0x1800119f0  mov     r8, [rdx+10h]
0x1800119f4  mov     byte ptr [rdx+18h], 0
0x1800119f8  mov     rax, [r8]
0x1800119fb  mov     [rdx+10h], rax
0x1800119ff  mov     rax, [r8]
0x180011a02  cmp     byte ptr [rax+19h], 0
0x180011a06  jz      loc_180011CDC
0x180011a0c  mov     rax, [rdx+8]
0x180011a10  mov     [r8+8], rax
0x180011a14  mov     rax, [r10]
0x180011a17  cmp     rdx, [rax+8]
0x180011a1b  jz      loc_180011CE5
0x180011a21  mov     rax, [rdx+8]
0x180011a25  cmp     rdx, [rax]
0x180011a28  jz      loc_180011C25
0x180011a2e  mov     [rax+10h], r8
0x180011a32  jmp     loc_180011C28
0x180011a37  mov     [rax+8], r9
0x180011a3b  jmp     loc_1800118D3
0x180011a40  cmp     byte ptr [r9+19h], 0
0x180011a45  mov     rcx, [rax+8]
0x180011a49  jnz     short loc_180011A4F
0x180011a4b  mov     [r9+8], rcx
0x180011a4f  mov     [rcx], r9
0x180011a52  mov     rdx, [rsi]
0x180011a55  mov     [rax+10h], rdx
0x180011a59  mov     rdx, [rsi]
0x180011a5c  mov     [rdx+8], rax
0x180011a60  jmp     loc_180011874
0x180011a65  mov     [rdx+8], rax
0x180011a69  jmp     loc_180011890
0x180011a6e  mov     rdx, [rcx+10h]
0x180011a72  cmp     byte ptr [rdx+18h], 0
0x180011a76  jnz     loc_180011B44
0x180011a7c  mov     byte ptr [rdx+18h], 1
0x180011a80  mov     rdx, [rcx+10h]
0x180011a84  mov     byte ptr [rcx+18h], 0
0x180011a88  mov     rax, [rdx]
0x180011a8b  mov     [rcx+10h], rax
0x180011a8f  mov     rax, [rdx]
0x180011a92  cmp     byte ptr [rax+19h], 0
0x180011a96  jz      loc_180011C89
0x180011a9c  mov     rax, [rcx+8]
0x180011aa0  mov     [rdx+8], rax
0x180011aa4  mov     rax, [r10]
0x180011aa7  cmp     rcx, [rax+8]
0x180011aab  jz      loc_180011C92
0x180011ab1  mov     rax, [rcx+8]
0x180011ab5  cmp     rcx, [rax]
0x180011ab8  jz      short loc_180011B36
0x180011aba  mov     [rax+10h], rdx
0x180011abe  jmp     short loc_180011B39
0x180011ac0  mov     [rcx+10h], r9
0x180011ac4  jmp     loc_1800118D3
0x180011ac9  mov     r11, [r9]
0x180011acc  cmp     byte ptr [r11+19h], 0
0x180011ad1  jnz     short loc_180011B2E
0x180011ad3  mov     rax, [r11]
0x180011ad6  mov     r8, r11
0x180011ad9  mov     r11, rax
0x180011adc  cmp     byte ptr [rax+19h], 0
0x180011ae0  jz      short loc_180011AD3
0x180011ae2  jmp     loc_1800118E9
0x180011ae7  mov     rax, [r9+10h]
0x180011aeb  mov     r8, r9
0x180011aee  cmp     byte ptr [rax+19h], 0
0x180011af2  jnz     loc_180011903
0x180011af8  mov     r8, [r8+10h]
0x180011afc  mov     rax, [r8+10h]
0x180011b00  cmp     byte ptr [rax+19h], 0
0x180011b04  jz      short loc_180011AF8
0x180011b06  jmp     loc_180011903
0x180011b0b  mov     [rdx+10h], rax
0x180011b0f  jmp     loc_180011890
0x180011b14  mov     [rax+8], rcx
0x180011b18  jmp     loc_18001198A
0x180011b1d  mov     [rax+8], rdx
0x180011b21  jmp     loc_1800119B1
0x180011b26  mov     [rax], rdx
0x180011b29  jmp     loc_1800119B1
0x180011b2e  mov     r8, r9
0x180011b31  jmp     loc_1800118E9
0x180011b36  mov     [rax], rdx
0x180011b39  mov     [rdx], rcx
0x180011b3c  mov     [rcx+8], rdx
0x180011b40  mov     rdx, [rcx+10h]
0x180011b44  cmp     byte ptr [rdx+19h], 0
0x180011b48  jnz     loc_180011D48
0x180011b4e  mov     r11, [rdx]
0x180011b51  cmp     byte ptr [r11+18h], 1
0x180011b56  jnz     short loc_180011B66
0x180011b58  mov     rax, [rdx+10h]
0x180011b5c  cmp     byte ptr [rax+18h], 1
0x180011b60  jz      loc_180011D44
0x180011b66  mov     rax, [rdx+10h]
0x180011b6a  cmp     byte ptr [rax+18h], 1
0x180011b6e  jnz     short loc_180011BC4
0x180011b70  mov     byte ptr [r11+18h], 1
0x180011b75  mov     r8, [rdx]
0x180011b78  mov     byte ptr [rdx+18h], 0
0x180011b7c  mov     rax, [r8+10h]
0x180011b80  mov     [rdx], rax
0x180011b83  mov     rax, [r8+10h]
0x180011b87  cmp     byte ptr [rax+19h], 0
0x180011b8b  jz      loc_180011C9B
0x180011b91  mov     rax, [rdx+8]
0x180011b95  mov     [r8+8], rax
0x180011b99  mov     rax, [r10]
0x180011b9c  cmp     rdx, [rax+8]
0x180011ba0  jz      loc_180011CA4
0x180011ba6  mov     rax, [rdx+8]
0x180011baa  cmp     rdx, [rax+10h]
0x180011bae  jnz     loc_180011CAD
0x180011bb4  mov     [rax+10h], r8
0x180011bb8  mov     [r8+10h], rdx
0x180011bbc  mov     [rdx+8], r8
0x180011bc0  mov     rdx, [rcx+10h]
0x180011bc4  movzx   eax, byte ptr [rcx+18h]
0x180011bc8  mov     [rdx+18h], al
0x180011bcb  mov     byte ptr [rcx+18h], 1
0x180011bcf  mov     rax, [rdx+10h]
0x180011bd3  mov     byte ptr [rax+18h], 1
0x180011bd7  mov     rdx, [rcx+10h]
0x180011bdb  mov     rax, [rdx]
0x180011bde  mov     [rcx+10h], rax
0x180011be2  mov     rax, [rdx]
0x180011be5  cmp     byte ptr [rax+19h], 0
0x180011be9  jz      loc_180011CB5
0x180011bef  mov     rax, [rcx+8]
0x180011bf3  mov     [rdx+8], rax
0x180011bf7  mov     rax, [r10]
0x180011bfa  cmp     rcx, [rax+8]
0x180011bfe  jz      loc_180011CBE
0x180011c04  mov     rax, [rcx+8]
0x180011c08  cmp     rcx, [rax]
0x180011c0b  jnz     loc_180011CD3
0x180011c11  mov     [rax], rdx
0x180011c14  mov     [rdx], rcx
0x180011c17  mov     [rcx+8], rdx
0x180011c1b  mov     byte ptr [r9+18h], 1
0x180011c20  jmp     loc_180011920
0x180011c25  mov     [rax], r8
0x180011c28  mov     [r8], rdx
0x180011c2b  mov     [rdx+8], r8
0x180011c2f  mov     rdx, [rcx]
0x180011c32  movzx   eax, byte ptr [rcx+18h]
0x180011c36  mov     [rdx+18h], al
0x180011c39  mov     byte ptr [rcx+18h], 1
0x180011c3d  mov     rax, [rdx]
0x180011c40  mov     byte ptr [rax+18h], 1
0x180011c44  mov     rdx, [rcx]
0x180011c47  mov     rax, [rdx+10h]
0x180011c4b  mov     [rcx], rax
0x180011c4e  mov     rax, [rdx+10h]
0x180011c52  cmp     byte ptr [rax+19h], 0
0x180011c56  jz      loc_180011CEE
0x180011c5c  mov     rax, [rcx+8]
0x180011c60  mov     [rdx+8], rax
0x180011c64  mov     rax, [r10]
0x180011c67  cmp     rcx, [rax+8]
0x180011c6b  jz      loc_180011CF7
0x180011c71  mov     rax, [rcx+8]
0x180011c75  cmp     rcx, [rax+10h]
0x180011c79  jnz     loc_180011D04
0x180011c7f  mov     [rax+10h], rdx
0x180011c83  mov     [rdx+10h], rcx
0x180011c87  jmp     short loc_180011C17
  ... truncated ...
```
