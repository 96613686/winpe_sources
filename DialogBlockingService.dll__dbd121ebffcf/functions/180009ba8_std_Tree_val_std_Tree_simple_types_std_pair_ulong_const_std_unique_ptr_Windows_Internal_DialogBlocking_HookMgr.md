# std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>>>,std::_Iterator_base0>)

- ea: `0x180009ba8`
- end: `0x18000a005`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `1117`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a328`

## callees

- `0x180009ba8`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Extract(
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
0x180009ba8  push    rbx
0x180009baa  push    rbp
0x180009bab  push    rsi
0x180009bac  push    rdi
0x180009bad  push    r14
0x180009baf  lea     r11, [rdx+10h]
0x180009bb3  xor     r14d, r14d
0x180009bb6  mov     r9, [r11]
0x180009bb9  mov     rdi, rcx
0x180009bbc  mov     rbx, rdx
0x180009bbf  mov     rbp, rdx
0x180009bc2  mov     rsi, rdx
0x180009bc5  mov     r8b, [r9+19h]
0x180009bc9  test    r8b, r8b
0x180009bcc  jz      short loc_180009BEC
0x180009bce  lea     r10, [rdx+8]
0x180009bd2  mov     rax, [r10]
0x180009bd5  jmp     short loc_180009BE4
0x180009bd7  cmp     rdx, [rax+10h]
0x180009bdb  jnz     short loc_180009C0D
0x180009bdd  mov     rdx, rax
0x180009be0  mov     rax, [rax+8]
0x180009be4  cmp     [rax+19h], r14b
0x180009be8  jz      short loc_180009BD7
0x180009bea  jmp     short loc_180009C0D
0x180009bec  mov     rdx, [r9]
0x180009bef  cmp     [rdx+19h], r14b
0x180009bf3  jnz     short loc_180009C06
0x180009bf5  mov     rcx, [rdx]
0x180009bf8  mov     rax, rdx
0x180009bfb  mov     rdx, rcx
0x180009bfe  cmp     [rcx+19h], r14b
0x180009c02  jz      short loc_180009BF5
0x180009c04  jmp     short loc_180009C09
0x180009c06  mov     rax, r9
0x180009c09  lea     r10, [rsi+8]
0x180009c0d  mov     rcx, [rbx]
0x180009c10  cmp     [rcx+19h], r14b
0x180009c14  jnz     short loc_180009C2D
0x180009c16  test    r8b, r8b
0x180009c19  jz      short loc_180009C20
0x180009c1b  mov     r9, rcx
0x180009c1e  jmp     short loc_180009C2D
0x180009c20  mov     r9, [rax+10h]
0x180009c24  cmp     rax, rbp
0x180009c27  jnz     loc_180009CBF
0x180009c2d  mov     r8, [r10]
0x180009c30  cmp     [r9+19h], r14b
0x180009c34  jnz     short loc_180009C3A
0x180009c36  mov     [r9+8], r8
0x180009c3a  mov     rax, [rdi]
0x180009c3d  cmp     [rax+8], rbp
0x180009c41  jnz     short loc_180009C49
0x180009c43  mov     [rax+8], r9
0x180009c47  jmp     short loc_180009C57
0x180009c49  cmp     [r8], rbp
0x180009c4c  jnz     short loc_180009C53
0x180009c4e  mov     [r8], r9
0x180009c51  jmp     short loc_180009C57
0x180009c53  mov     [r8+10h], r9
0x180009c57  mov     r10, [rdi]
0x180009c5a  cmp     [r10], rbp
0x180009c5d  jnz     short loc_180009C8A
0x180009c5f  cmp     [r9+19h], r14b
0x180009c63  jz      short loc_180009C6A
0x180009c65  mov     rdx, r8
0x180009c68  jmp     short loc_180009C87
0x180009c6a  mov     rcx, [r9]
0x180009c6d  cmp     [rcx+19h], r14b
0x180009c71  jnz     short loc_180009C84
0x180009c73  mov     rax, [rcx]
0x180009c76  mov     rdx, rcx
0x180009c79  mov     rcx, rax
0x180009c7c  cmp     [rax+19h], r14b
0x180009c80  jz      short loc_180009C73
0x180009c82  jmp     short loc_180009C87
0x180009c84  mov     rdx, r9
0x180009c87  mov     [r10], rdx
0x180009c8a  mov     rdx, [rdi]
0x180009c8d  cmp     [rdx+10h], rbp
0x180009c91  jnz     short loc_180009CB9
0x180009c93  cmp     [r9+19h], r14b
0x180009c97  jz      short loc_180009C9E
0x180009c99  mov     rcx, r8
0x180009c9c  jmp     short loc_180009CB5
0x180009c9e  mov     rax, [r9+10h]
0x180009ca2  mov     rcx, r9
0x180009ca5  jmp     short loc_180009CAF
0x180009ca7  mov     rcx, [rcx+10h]
0x180009cab  mov     rax, [rcx+10h]
0x180009caf  cmp     [rax+19h], r14b
0x180009cb3  jz      short loc_180009CA7
0x180009cb5  mov     [rdx+10h], rcx
0x180009cb9  lea     r10, [rsi+18h]
0x180009cbd  jmp     short loc_180009D29
0x180009cbf  mov     [rcx+8], rax
0x180009cc3  mov     rcx, [rbx]
0x180009cc6  mov     [rax], rcx
0x180009cc9  cmp     rax, [r11]
0x180009ccc  jnz     short loc_180009CD3
0x180009cce  mov     r8, rax
0x180009cd1  jmp     short loc_180009CF2
0x180009cd3  mov     r8, [rax+8]
0x180009cd7  cmp     [r9+19h], r14b
0x180009cdb  jnz     short loc_180009CE1
0x180009cdd  mov     [r9+8], r8
0x180009ce1  mov     [r8], r9
0x180009ce4  mov     rcx, [r11]
0x180009ce7  mov     [rax+10h], rcx
0x180009ceb  mov     rcx, [r11]
0x180009cee  mov     [rcx+8], rax
0x180009cf2  mov     rcx, [rdi]
0x180009cf5  cmp     [rcx+8], rbp
0x180009cf9  jnz     short loc_180009D01
0x180009cfb  mov     [rcx+8], rax
0x180009cff  jmp     short loc_180009D12
0x180009d01  mov     rcx, [r10]
0x180009d04  cmp     [rcx], rbp
0x180009d07  jnz     short loc_180009D0E
0x180009d09  mov     [rcx], rax
0x180009d0c  jmp     short loc_180009D12
0x180009d0e  mov     [rcx+10h], rax
0x180009d12  mov     rcx, [r10]
0x180009d15  lea     r10, [rbp+18h]
0x180009d19  mov     dl, [rax+18h]
0x180009d1c  mov     [rax+8], rcx
0x180009d20  mov     cl, [r10]
0x180009d23  mov     [rax+18h], cl
0x180009d26  mov     [r10], dl
0x180009d29  mov     r11b, 1
0x180009d2c  cmp     [r10], r11b
0x180009d2f  jnz     loc_180009FEB
0x180009d35  jmp     loc_180009EA2
0x180009d3a  cmp     [r9+18h], r11b
0x180009d3e  jnz     loc_180009FE7
0x180009d44  mov     rcx, [r8]
0x180009d47  cmp     r9, rcx
0x180009d4a  jnz     loc_180009E1B
0x180009d50  mov     rcx, [r8+10h]
0x180009d54  cmp     [rcx+18h], r14b
0x180009d58  jnz     short loc_180009DAE
0x180009d5a  mov     [rcx+18h], r11b
0x180009d5e  mov     rcx, [r8+10h]
0x180009d62  mov     [r8+18h], r14b
0x180009d66  mov     rax, [rcx]
0x180009d69  mov     [r8+10h], rax
0x180009d6d  mov     rax, [rcx]
0x180009d70  cmp     [rax+19h], r14b
0x180009d74  jnz     short loc_180009D7A
0x180009d76  mov     [rax+8], r8
0x180009d7a  mov     rax, [r8+8]
0x180009d7e  mov     [rcx+8], rax
0x180009d82  mov     rax, [rdi]
0x180009d85  cmp     r8, [rax+8]
0x180009d89  jnz     short loc_180009D91
0x180009d8b  mov     [rax+8], rcx
0x180009d8f  jmp     short loc_180009DA3
0x180009d91  mov     rax, [r8+8]
0x180009d95  cmp     r8, [rax]
0x180009d98  jnz     short loc_180009D9F
0x180009d9a  mov     [rax], rcx
0x180009d9d  jmp     short loc_180009DA3
0x180009d9f  mov     [rax+10h], rcx
0x180009da3  mov     [rcx], r8
0x180009da6  mov     [r8+8], rcx
0x180009daa  mov     rcx, [r8+10h]
0x180009dae  cmp     [rcx+19h], r14b
0x180009db2  jnz     loc_180009E9B
0x180009db8  mov     r10, [rcx]
0x180009dbb  cmp     [r10+18h], r11b
0x180009dbf  jnz     short loc_180009DCF
0x180009dc1  mov     rax, [rcx+10h]
0x180009dc5  cmp     [rax+18h], r11b
0x180009dc9  jz      loc_180009E97
0x180009dcf  mov     rax, [rcx+10h]
0x180009dd3  cmp     [rax+18h], r11b
0x180009dd7  jnz     loc_180009ED3
0x180009ddd  mov     [r10+18h], r11b
0x180009de1  mov     rdx, [rcx]
0x180009de4  mov     [rcx+18h], r14b
0x180009de8  mov     rax, [rdx+10h]
0x180009dec  mov     [rcx], rax
0x180009def  mov     rax, [rdx+10h]
0x180009df3  cmp     [rax+19h], r14b
0x180009df7  jnz     short loc_180009DFD
0x180009df9  mov     [rax+8], rcx
0x180009dfd  mov     rax, [rcx+8]
0x180009e01  mov     [rdx+8], rax
0x180009e05  mov     rax, [rdi]
0x180009e08  cmp     rcx, [rax+8]
0x180009e0c  jnz     loc_180009EB4
0x180009e12  mov     [rax+8], rdx
0x180009e16  jmp     loc_180009EC7
0x180009e1b  cmp     [rcx+18h], r14b
0x180009e1f  jnz     short loc_180009E76
0x180009e21  mov     [rcx+18h], r11b
0x180009e25  mov     rcx, [r8]
0x180009e28  mov     [r8+18h], r14b
0x180009e2c  mov     rax, [rcx+10h]
0x180009e30  mov     [r8], rax
0x180009e33  mov     rax, [rcx+10h]
0x180009e37  cmp     [rax+19h], r14b
0x180009e3b  jnz     short loc_180009E41
0x180009e3d  mov     [rax+8], r8
0x180009e41  mov     rax, [r8+8]
0x180009e45  mov     [rcx+8], rax
0x180009e49  mov     rax, [rdi]
0x180009e4c  cmp     r8, [rax+8]
0x180009e50  jnz     short loc_180009E58
0x180009e52  mov     [rax+8], rcx
0x180009e56  jmp     short loc_180009E6B
0x180009e58  mov     rax, [r8+8]
0x180009e5c  cmp     r8, [rax+10h]
0x180009e60  jnz     short loc_180009E68
0x180009e62  mov     [rax+10h], rcx
0x180009e66  jmp     short loc_180009E6B
0x180009e68  mov     [rax], rcx
0x180009e6b  mov     [rcx+10h], r8
0x180009e6f  mov     [r8+8], rcx
0x180009e73  mov     rcx, [r8]
0x180009e76  cmp     [rcx+19h], r14b
0x180009e7a  jnz     short loc_180009E9B
0x180009e7c  mov     rdx, [rcx+10h]
0x180009e80  cmp     [rdx+18h], r11b
0x180009e84  jnz     loc_180009F2F
0x180009e8a  mov     rax, [rcx]
0x180009e8d  cmp     [rax+18h], r11b
0x180009e91  jnz     loc_180009F2F
0x180009e97  mov     [rcx+18h], r14b
0x180009e9b  mov     r9, r8
0x180009e9e  mov     r8, [r8+8]
0x180009ea2  mov     rax, [rdi]
0x180009ea5  cmp     r9, [rax+8]
0x180009ea9  jnz     loc_180009D3A
0x180009eaf  jmp     loc_180009FE7
0x180009eb4  mov     rax, [rcx+8]
0x180009eb8  cmp     rcx, [rax+10h]
0x180009ebc  jnz     short loc_180009EC4
0x180009ebe  mov     [rax+10h], rdx
0x180009ec2  jmp     short loc_180009EC7
0x180009ec4  mov     [rax], rdx
0x180009ec7  mov     [rdx+10h], rcx
0x180009ecb  mov     [rcx+8], rdx
0x180009ecf  mov     rcx, [r8+10h]
0x180009ed3  mov     al, [r8+18h]
0x180009ed7  mov     [rcx+18h], al
0x180009eda  mov     [r8+18h], r11b
0x180009ede  mov     rax, [rcx+10h]
0x180009ee2  mov     [rax+18h], r11b
0x180009ee6  mov     rcx, [r8+10h]
0x180009eea  mov     rax, [rcx]
0x180009eed  mov     [r8+10h], rax
0x180009ef1  mov     rax, [rcx]
0x180009ef4  cmp     [rax+19h], r14b
0x180009ef8  jnz     short loc_180009EFE
0x180009efa  mov     [rax+8], r8
0x180009efe  mov     rax, [r8+8]
0x180009f02  mov     [rcx+8], rax
0x180009f06  mov     rax, [rdi]
0x180009f09  cmp     r8, [rax+8]
0x180009f0d  jnz     short loc_180009F15
0x180009f0f  mov     [rax+8], rcx
0x180009f13  jmp     short loc_180009F27
0x180009f15  mov     rax, [r8+8]
0x180009f19  cmp     r8, [rax]
0x180009f1c  jnz     short loc_180009F23
0x180009f1e  mov     [rax], rcx
0x180009f21  jmp     short loc_180009F27
0x180009f23  mov     [rax+10h], rcx
0x180009f27  mov     [rcx], r8
0x180009f2a  jmp     loc_180009FE3
0x180009f2f  mov     rax, [rcx]
0x180009f32  cmp     [rax+18h], r11b
0x180009f36  jnz     short loc_180009F8B
0x180009f38  mov     [rdx+18h], r11b
0x180009f3c  mov     rdx, [rcx+10h]
0x180009f40  mov     [rcx+18h], r14b
0x180009f44  mov     rax, [rdx]
0x180009f47  mov     [rcx+10h], rax
0x180009f4b  mov     rax, [rdx]
0x180009f4e  cmp     [rax+19h], r14b
0x180009f52  jnz     short loc_180009F58
0x180009f54  mov     [rax+8], rcx
0x180009f58  mov     rax, [rcx+8]
0x180009f5c  mov     [rdx+8], rax
0x180009f60  mov     rax, [rdi]
0x180009f63  cmp     rcx, [rax+8]
0x180009f67  jnz     short loc_180009F6F
0x180009f69  mov     [rax+8], rdx
0x180009f6d  jmp     short loc_180009F81
0x180009f6f  mov     rax, [rcx+8]
0x180009f73  cmp     rcx, [rax]
0x180009f76  jnz     short loc_180009F7D
0x180009f78  mov     [rax], rdx
0x180009f7b  jmp     short loc_180009F81
0x180009f7d  mov     [rax+10h], rdx
0x180009f81  mov     [rdx], rcx
0x180009f84  mov     [rcx+8], rdx
0x180009f88  mov     rcx, [r8]
0x180009f8b  mov     al, [r8+18h]
  ... truncated ...
```
