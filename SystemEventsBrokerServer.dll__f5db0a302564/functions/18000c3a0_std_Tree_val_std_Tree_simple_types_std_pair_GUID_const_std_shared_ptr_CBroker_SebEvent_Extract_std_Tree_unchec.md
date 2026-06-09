# std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>,std::_Iterator_base0>)

- ea: `0x18000c3a0`
- end: `0x18000c900`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `1376`
- prototype: `_QWORD *__fastcall(__int64 **, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b3d0`
- `0x180014470`

## callees

- `0x18000c3a0`
- `0x180016c08`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>::_Extract(
        __int64 **a1,
        _QWORD *a2)
{
  _QWORD *v2; // r8
  _QWORD *v4; // r9
  _QWORD *v5; // r10
  _QWORD *v6; // rbp
  char v7; // r11
  _QWORD *v8; // rdi
  __int64 *v9; // rdx
  _QWORD *v10; // rax
  _QWORD **i; // rsi
  _QWORD *v12; // r9
  _QWORD *v13; // rcx
  __int64 *v14; // r11
  __int64 v15; // rax
  _QWORD *j; // rdx
  _BYTE *v17; // r11
  char v18; // dl
  __int64 *v19; // rcx
  _QWORD *result; // rax
  __int64 *v21; // rcx
  __int64 *v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 *v28; // rax
  __int64 v29; // rdx
  __int64 *v30; // rdx
  __int64 *v31; // rcx
  __int64 v32; // rax
  _QWORD *v33; // rax
  _QWORD *v34; // rax
  __int64 **v35; // rax
  _QWORD *v36; // rcx
  _QWORD *v37; // rax

  v2 = (_QWORD *)a2[2];
  v4 = a2;
  v5 = a2;
  v6 = a2;
  v7 = *((_BYTE *)v2 + 25);
  v8 = a2 + 2;
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
    i = (_QWORD **)(v6 + 1);
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
        if ( v10 == (_QWORD *)*v8 )
        {
          v12 = v10;
        }
        else
        {
          v12 = (_QWORD *)v10[1];
          if ( !*((_BYTE *)v2 + 25) )
            v2[1] = v12;
          *v12 = v2;
          v10[2] = *v8;
          *(_QWORD *)(*v8 + 8LL) = v10;
        }
        if ( (_QWORD *)(*a1)[1] == v5 )
        {
          (*a1)[1] = (__int64)v10;
        }
        else
        {
          v13 = *i;
          if ( (_QWORD *)**i == v5 )
            *v13 = v10;
          else
            v13[2] = v10;
        }
        v17 = v5 + 3;
        v10[1] = *i;
        v18 = *((_BYTE *)v10 + 24);
        *((_BYTE *)v10 + 24) = *((_BYTE *)v5 + 24);
        *((_BYTE *)v5 + 24) = v18;
        goto LABEL_34;
      }
    }
  }
  v12 = *i;
  if ( !*((_BYTE *)v2 + 25) )
    v2[1] = v12;
  if ( (_QWORD *)(*a1)[1] == v5 )
  {
    (*a1)[1] = (__int64)v2;
  }
  else if ( (_QWORD *)*v12 == v5 )
  {
    *v12 = v2;
  }
  else
  {
    v12[2] = v2;
  }
  v14 = *a1;
  if ( (_QWORD *)**a1 == v5 )
  {
    if ( *((_BYTE *)v2 + 25) )
      v15 = (__int64)v12;
    else
      v15 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Min(v2);
    *v14 = v15;
  }
  if ( (_QWORD *)(*a1)[2] == v5 )
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
    (*a1)[2] = (__int64)j;
  }
  v17 = v6 + 3;
LABEL_34:
  if ( *v17 != 1 )
    goto LABEL_35;
  while ( 1 )
  {
    if ( v2 == (_QWORD *)(*a1)[1] || *((_BYTE *)v2 + 24) != 1 )
      goto LABEL_94;
    v21 = (__int64 *)*v12;
    if ( v2 != (_QWORD *)*v12 )
    {
      if ( !*((_BYTE *)v21 + 24) )
      {
        *((_BYTE *)v21 + 24) = 1;
        v22 = (__int64 *)*v12;
        *((_BYTE *)v12 + 24) = 0;
        *v12 = v22[2];
        v23 = v22[2];
        if ( !*(_BYTE *)(v23 + 25) )
          *(_QWORD *)(v23 + 8) = v12;
        v22[1] = v12[1];
        if ( v12 == (_QWORD *)(*a1)[1] )
        {
          (*a1)[1] = (__int64)v22;
        }
        else
        {
          v24 = (_QWORD *)v12[1];
          if ( v12 == (_QWORD *)v24[2] )
            v24[2] = v22;
          else
            *v24 = v22;
        }
        v22[2] = (__int64)v12;
        v12[1] = v22;
        v21 = (__int64 *)*v12;
      }
      if ( *((_BYTE *)v21 + 25) )
        goto LABEL_49;
      v29 = v21[2];
      if ( *(_BYTE *)(v29 + 24) != 1 || *(_BYTE *)(*v21 + 24) != 1 )
      {
        if ( *(_BYTE *)(*v21 + 24) == 1 )
        {
          *(_BYTE *)(v29 + 24) = 1;
          v30 = (__int64 *)v21[2];
          *((_BYTE *)v21 + 24) = 0;
          v21[2] = *v30;
          if ( !*(_BYTE *)(*v30 + 25) )
            *(_QWORD *)(*v30 + 8) = v21;
          v30[1] = v21[1];
          if ( v21 == (__int64 *)(*a1)[1] )
          {
            (*a1)[1] = (__int64)v30;
          }
          else
          {
            v35 = (__int64 **)v21[1];
            if ( v21 == *v35 )
              *v35 = v30;
            else
              v35[2] = v30;
          }
          *v30 = (__int64)v21;
          v21[1] = (__int64)v30;
          v21 = (__int64 *)*v12;
        }
        *((_BYTE *)v21 + 24) = *((_BYTE *)v12 + 24);
        *((_BYTE *)v12 + 24) = 1;
        *(_BYTE *)(*v21 + 24) = 1;
        v31 = (__int64 *)*v12;
        *v12 = *(_QWORD *)(*v12 + 16LL);
        v32 = v31[2];
        if ( !*(_BYTE *)(v32 + 25) )
          *(_QWORD *)(v32 + 8) = v12;
        v31[1] = v12[1];
        if ( v12 != (_QWORD *)(*a1)[1] )
        {
          v33 = (_QWORD *)v12[1];
          if ( v12 == (_QWORD *)v33[2] )
            v33[2] = v31;
          else
            *v33 = v31;
          v31[2] = (__int64)v12;
          v12[1] = v31;
LABEL_94:
          *((_BYTE *)v2 + 24) = 1;
          goto LABEL_35;
        }
        (*a1)[1] = (__int64)v31;
        v31[2] = (__int64)v12;
        v12[1] = v31;
        *((_BYTE *)v2 + 24) = 1;
        goto LABEL_35;
      }
LABEL_112:
      *((_BYTE *)v21 + 24) = 0;
      goto LABEL_49;
    }
    v21 = (__int64 *)v12[2];
    if ( !*((_BYTE *)v21 + 24) )
    {
      *((_BYTE *)v21 + 24) = 1;
      v25 = (_QWORD *)v12[2];
      *((_BYTE *)v12 + 24) = 0;
      v12[2] = *v25;
      if ( !*(_BYTE *)(*v25 + 25LL) )
        *(_QWORD *)(*v25 + 8LL) = v12;
      v25[1] = v12[1];
      if ( v12 == (_QWORD *)(*a1)[1] )
      {
        (*a1)[1] = (__int64)v25;
      }
      else
      {
        v34 = (_QWORD *)v12[1];
        if ( v12 == (_QWORD *)*v34 )
          *v34 = v25;
        else
          v34[2] = v25;
      }
      *v25 = v12;
      v12[1] = v25;
      v21 = (__int64 *)v12[2];
    }
    if ( !*((_BYTE *)v21 + 25) )
      break;
LABEL_49:
    v2 = v12;
    v12 = (_QWORD *)v12[1];
  }
  if ( *(_BYTE *)(*v21 + 24) == 1 && *(_BYTE *)(v21[2] + 24) == 1 )
    goto LABEL_112;
  if ( *(_BYTE *)(v21[2] + 24) == 1 )
  {
    *(_BYTE *)(*v21 + 24) = 1;
    v26 = *v21;
    *((_BYTE *)v21 + 24) = 0;
    *v21 = *(_QWORD *)(v26 + 16);
    v27 = *(_QWORD *)(v26 + 16);
    if ( !*(_BYTE *)(v27 + 25) )
      *(_QWORD *)(v27 + 8) = v21;
    *(_QWORD *)(v26 + 8) = v21[1];
    if ( v21 == (__int64 *)(*a1)[1] )
    {
      (*a1)[1] = v26;
    }
    else
    {
      v28 = (__int64 *)v21[1];
      if ( v21 == (__int64 *)v28[2] )
        v28[2] = v26;
      else
        *v28 = v26;
    }
    *(_QWORD *)(v26 + 16) = v21;
    v21[1] = v26;
    v21 = (__int64 *)v12[2];
  }
  *((_BYTE *)v21 + 24) = *((_BYTE *)v12 + 24);
  *((_BYTE *)v12 + 24) = 1;
  *(_BYTE *)(v21[2] + 24) = 1;
  v36 = (_QWORD *)v12[2];
  v12[2] = *v36;
  if ( !*(_BYTE *)(*v36 + 25LL) )
    *(_QWORD *)(*v36 + 8LL) = v12;
  v36[1] = v12[1];
  if ( v12 == (_QWORD *)(*a1)[1] )
  {
    (*a1)[1] = (__int64)v36;
LABEL_101:
    *v36 = v12;
    v12[1] = v36;
    *((_BYTE *)v2 + 24) = 1;
    goto LABEL_35;
  }
  v37 = (_QWORD *)v12[1];
  if ( v12 != (_QWORD *)*v37 )
  {
    v37[2] = v36;
    goto LABEL_101;
  }
  *v37 = v36;
  *v36 = v12;
  v12[1] = v36;
  *((_BYTE *)v2 + 24) = 1;
LABEL_35:
  v19 = a1[1];
  result = v5;
  if ( v19 )
    a1[1] = (__int64 *)((char *)v19 - 1);
  return result;
}

```

## disassembly

```asm
0x18000c3a0  push    rbx
0x18000c3a2  sub     rsp, 20h
0x18000c3a6  mov     r8, [rdx+10h]
0x18000c3aa  mov     rbx, rcx
0x18000c3ad  mov     [rsp+28h+arg_0], rbp
0x18000c3b2  mov     r9, rdx
0x18000c3b5  mov     [rsp+28h+arg_8], rsi
0x18000c3ba  mov     r10, rdx
0x18000c3bd  mov     [rsp+28h+arg_10], rdi
0x18000c3c2  mov     rbp, rdx
0x18000c3c5  movzx   r11d, byte ptr [r8+19h]
0x18000c3ca  lea     rdi, [rdx+10h]
0x18000c3ce  test    r11b, r11b
0x18000c3d1  jnz     short loc_18000C446
0x18000c3d3  mov     rdx, [r8]
0x18000c3d6  cmp     [rdx+19h], r11b
0x18000c3da  jnz     loc_18000C469
0x18000c3e0  mov     rcx, [rdx]
0x18000c3e3  mov     rax, rdx
0x18000c3e6  mov     rdx, rcx
0x18000c3e9  cmp     byte ptr [rcx+19h], 0
0x18000c3ed  jz      short loc_18000C3E0
0x18000c3ef  lea     rsi, [rbp+8]
0x18000c3f3  mov     rcx, [r9]
0x18000c3f6  cmp     byte ptr [rcx+19h], 0
0x18000c3fa  jnz     short loc_18000C46E
0x18000c3fc  test    r11b, r11b
0x18000c3ff  jnz     loc_18000C8EF
0x18000c405  mov     r8, [rax+10h]
0x18000c409  cmp     rax, r10
0x18000c40c  jz      short loc_18000C46E
0x18000c40e  mov     [rcx+8], rax
0x18000c412  mov     rcx, [r9]
0x18000c415  mov     [rax], rcx
0x18000c418  cmp     rax, [rdi]
0x18000c41b  jnz     loc_18000C6C2
0x18000c421  mov     r9, rax
0x18000c424  mov     rcx, [rbx]
0x18000c427  cmp     [rcx+8], r10
0x18000c42b  jz      loc_18000C4CF
0x18000c431  mov     rcx, [rsi]
0x18000c434  cmp     [rcx], r10
0x18000c437  jz      loc_18000C6E7
0x18000c43d  mov     [rcx+10h], rax
0x18000c441  jmp     loc_18000C4D3
0x18000c446  mov     rax, [rdx+8]
0x18000c44a  lea     rsi, [rdx+8]
0x18000c44e  cmp     byte ptr [rax+19h], 0
0x18000c452  jnz     short loc_18000C3F3
0x18000c454  cmp     rdx, [rax+10h]
0x18000c458  jnz     short loc_18000C3F3
0x18000c45a  mov     rdx, rax
0x18000c45d  mov     rax, [rax+8]
0x18000c461  cmp     byte ptr [rax+19h], 0
0x18000c465  jz      short loc_18000C454
0x18000c467  jmp     short loc_18000C3F3
0x18000c469  mov     rax, r8
0x18000c46c  jmp     short loc_18000C3EF
0x18000c46e  cmp     byte ptr [r8+19h], 0
0x18000c473  mov     r9, [rsi]
0x18000c476  jz      loc_18000C676
0x18000c47c  mov     rax, [rbx]
0x18000c47f  cmp     [rax+8], r10
0x18000c483  jz      loc_18000C67F
0x18000c489  cmp     [r9], r10
0x18000c48c  jnz     loc_18000C688
0x18000c492  mov     [r9], r8
0x18000c495  mov     r11, [rbx]
0x18000c498  cmp     [r11], r10
0x18000c49b  jnz     short loc_18000C4AE
0x18000c49d  cmp     byte ptr [r8+19h], 0
0x18000c4a2  jz      loc_18000C691
0x18000c4a8  mov     rax, r9
0x18000c4ab  mov     [r11], rax
0x18000c4ae  mov     rcx, [rbx]
0x18000c4b1  cmp     [rcx+10h], r10
0x18000c4b5  jnz     short loc_18000C4C9
0x18000c4b7  cmp     byte ptr [r8+19h], 0
0x18000c4bc  jz      loc_18000C69E
0x18000c4c2  mov     rdx, r9
0x18000c4c5  mov     [rcx+10h], rdx
0x18000c4c9  lea     r11, [rbp+18h]
0x18000c4cd  jmp     short loc_18000C4EC
0x18000c4cf  mov     [rcx+8], rax
0x18000c4d3  mov     rcx, [rsi]
0x18000c4d6  lea     r11, [r10+18h]
0x18000c4da  mov     [rax+8], rcx
0x18000c4de  movzx   ecx, byte ptr [r11]
0x18000c4e2  movzx   edx, byte ptr [rax+18h]
0x18000c4e6  mov     [rax+18h], cl
0x18000c4e9  mov     [r11], dl
0x18000c4ec  cmp     byte ptr [r11], 1
0x18000c4f0  mov     rdi, [rsp+28h+arg_10]
0x18000c4f5  mov     rsi, [rsp+28h+arg_8]
0x18000c4fa  mov     rbp, [rsp+28h+arg_0]
0x18000c4ff  jz      short loc_18000C520
0x18000c501  mov     rcx, [rbx+8]
0x18000c505  mov     rax, r10
0x18000c508  test    rcx, rcx
0x18000c50b  jnz     loc_18000C7A2
0x18000c511  add     rsp, 20h
0x18000c515  pop     rbx
0x18000c516  retn
0x18000c520  mov     rax, [rbx]
0x18000c523  cmp     r8, [rax+8]
0x18000c527  jz      loc_18000C7E5
0x18000c52d  cmp     byte ptr [r8+18h], 1
0x18000c532  jnz     loc_18000C7E5
0x18000c538  mov     rcx, [r9]
0x18000c53b  cmp     r8, rcx
0x18000c53e  jz      short loc_18000C5AF
0x18000c540  cmp     byte ptr [rcx+18h], 0
0x18000c544  jnz     short loc_18000C599
0x18000c546  mov     byte ptr [rcx+18h], 1
0x18000c54a  mov     rcx, [r9]
0x18000c54d  mov     byte ptr [r9+18h], 0
0x18000c552  mov     rax, [rcx+10h]
0x18000c556  mov     [r9], rax
0x18000c559  mov     rax, [rcx+10h]
0x18000c55d  cmp     byte ptr [rax+19h], 0
0x18000c561  jz      loc_18000C86F
0x18000c567  mov     rax, [r9+8]
0x18000c56b  mov     [rcx+8], rax
0x18000c56f  mov     rax, [rbx]
0x18000c572  cmp     r9, [rax+8]
0x18000c576  jz      loc_18000C878
0x18000c57c  mov     rax, [r9+8]
0x18000c580  cmp     r9, [rax+10h]
0x18000c584  jnz     loc_18000C881
0x18000c58a  mov     [rax+10h], rcx
0x18000c58e  mov     [rcx+10h], r9
0x18000c592  mov     [r9+8], rcx
0x18000c596  mov     rcx, [r9]
0x18000c599  cmp     byte ptr [rcx+19h], 0
0x18000c59d  jz      loc_18000C6EF
0x18000c5a3  mov     r8, r9
0x18000c5a6  mov     r9, [r9+8]
0x18000c5aa  jmp     loc_18000C520
0x18000c5af  mov     rcx, [r9+10h]
0x18000c5b3  cmp     byte ptr [rcx+18h], 0
0x18000c5b7  jnz     short loc_18000C5FE
0x18000c5b9  mov     byte ptr [rcx+18h], 1
0x18000c5bd  mov     rcx, [r9+10h]
0x18000c5c1  mov     byte ptr [r9+18h], 0
0x18000c5c6  mov     rax, [rcx]
0x18000c5c9  mov     [r9+10h], rax
0x18000c5cd  mov     rax, [rcx]
0x18000c5d0  cmp     byte ptr [rax+19h], 0
0x18000c5d4  jz      loc_18000C8BA
0x18000c5da  mov     rax, [r9+8]
0x18000c5de  mov     [rcx+8], rax
0x18000c5e2  mov     rax, [rbx]
0x18000c5e5  cmp     r9, [rax+8]
0x18000c5e9  jnz     loc_18000C7AE
0x18000c5ef  mov     [rax+8], rcx
0x18000c5f3  mov     [rcx], r9
0x18000c5f6  mov     [r9+8], rcx
0x18000c5fa  mov     rcx, [r9+10h]
0x18000c5fe  cmp     byte ptr [rcx+19h], 0
0x18000c602  jnz     short loc_18000C5A3
0x18000c604  mov     r11, [rcx]
0x18000c607  cmp     byte ptr [r11+18h], 1
0x18000c60c  jnz     short loc_18000C61C
0x18000c60e  mov     rax, [rcx+10h]
0x18000c612  cmp     byte ptr [rax+18h], 1
0x18000c616  jz      loc_18000C8F7
0x18000c61c  mov     rax, [rcx+10h]
0x18000c620  cmp     byte ptr [rax+18h], 1
0x18000c624  jnz     loc_18000C7FF
0x18000c62a  mov     byte ptr [r11+18h], 1
0x18000c62f  mov     rdx, [rcx]
0x18000c632  mov     byte ptr [rcx+18h], 0
0x18000c636  mov     rax, [rdx+10h]
0x18000c63a  mov     [rcx], rax
0x18000c63d  mov     rax, [rdx+10h]
0x18000c641  cmp     byte ptr [rax+19h], 0
0x18000c645  jz      loc_18000C889
0x18000c64b  mov     rax, [rcx+8]
0x18000c64f  mov     [rdx+8], rax
0x18000c653  mov     rax, [rbx]
0x18000c656  cmp     rcx, [rax+8]
0x18000c65a  jz      loc_18000C892
0x18000c660  mov     rax, [rcx+8]
0x18000c664  cmp     rcx, [rax+10h]
0x18000c668  jz      loc_18000C7EF
0x18000c66e  mov     [rax], rdx
0x18000c671  jmp     loc_18000C7F3
0x18000c676  mov     [r8+8], r9
0x18000c67a  jmp     loc_18000C47C
0x18000c67f  mov     [rax+8], r8
0x18000c683  jmp     loc_18000C495
0x18000c688  mov     [r9+10h], r8
0x18000c68c  jmp     loc_18000C495
0x18000c691  mov     rcx, r8
0x18000c694  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Min(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x18000c699  jmp     loc_18000C4AB
0x18000c69e  mov     rax, [r8+10h]
0x18000c6a2  mov     rdx, r8
0x18000c6a5  cmp     byte ptr [rax+19h], 0
0x18000c6a9  jnz     loc_18000C4C5
0x18000c6af  mov     rdx, [rdx+10h]
0x18000c6b3  mov     rax, [rdx+10h]
0x18000c6b7  cmp     byte ptr [rax+19h], 0
0x18000c6bb  jz      short loc_18000C6AF
0x18000c6bd  jmp     loc_18000C4C5
0x18000c6c2  cmp     byte ptr [r8+19h], 0
0x18000c6c7  mov     r9, [rax+8]
0x18000c6cb  jnz     short loc_18000C6D1
0x18000c6cd  mov     [r8+8], r9
0x18000c6d1  mov     [r9], r8
0x18000c6d4  mov     rcx, [rdi]
0x18000c6d7  mov     [rax+10h], rcx
0x18000c6db  mov     rcx, [rdi]
0x18000c6de  mov     [rcx+8], rax
0x18000c6e2  jmp     loc_18000C424
0x18000c6e7  mov     [rcx], rax
0x18000c6ea  jmp     loc_18000C4D3
0x18000c6ef  mov     rdx, [rcx+10h]
0x18000c6f3  cmp     byte ptr [rdx+18h], 1
0x18000c6f7  jnz     short loc_18000C706
0x18000c6f9  mov     rax, [rcx]
0x18000c6fc  cmp     byte ptr [rax+18h], 1
0x18000c700  jz      loc_18000C8F7
0x18000c706  mov     rax, [rcx]
0x18000c709  cmp     byte ptr [rax+18h], 1
0x18000c70d  jnz     short loc_18000C752
0x18000c70f  mov     byte ptr [rdx+18h], 1
0x18000c713  mov     rdx, [rcx+10h]
0x18000c717  mov     byte ptr [rcx+18h], 0
0x18000c71b  mov     rax, [rdx]
0x18000c71e  mov     [rcx+10h], rax
0x18000c722  mov     rax, [rdx]
0x18000c725  cmp     byte ptr [rax+19h], 0
0x18000c729  jz      loc_18000C8DD
0x18000c72f  mov     rax, [rcx+8]
0x18000c733  mov     [rdx+8], rax
0x18000c737  mov     rax, [rbx]
0x18000c73a  cmp     rcx, [rax+8]
0x18000c73e  jnz     loc_18000C7C4
0x18000c744  mov     [rax+8], rdx
0x18000c748  mov     [rdx], rcx
0x18000c74b  mov     [rcx+8], rdx
0x18000c74f  mov     rcx, [r9]
0x18000c752  movzx   eax, byte ptr [r9+18h]
0x18000c757  mov     [rcx+18h], al
0x18000c75a  mov     byte ptr [r9+18h], 1
0x18000c75f  mov     rax, [rcx]
0x18000c762  mov     byte ptr [rax+18h], 1
0x18000c766  mov     rcx, [r9]
0x18000c769  mov     rax, [rcx+10h]
0x18000c76d  mov     [r9], rax
0x18000c770  mov     rax, [rcx+10h]
0x18000c774  cmp     byte ptr [rax+19h], 0
0x18000c778  jz      loc_18000C89B
0x18000c77e  mov     rax, [r9+8]
0x18000c782  mov     [rcx+8], rax
0x18000c786  mov     rax, [rbx]
0x18000c789  cmp     r9, [rax+8]
0x18000c78d  jz      loc_18000C8A4
0x18000c793  mov     rax, [r9+8]
0x18000c797  cmp     r9, [rax+10h]
0x18000c79b  jz      short loc_18000C7D9
0x18000c79d  mov     [rax], rcx
0x18000c7a0  jmp     short loc_18000C7DD
0x18000c7a2  dec     rcx
0x18000c7a5  mov     [rbx+8], rcx
0x18000c7a9  jmp     loc_18000C511
0x18000c7ae  mov     rax, [r9+8]
0x18000c7b2  cmp     r9, [rax]
0x18000c7b5  jz      loc_18000C8C3
0x18000c7bb  mov     [rax+10h], rcx
0x18000c7bf  jmp     loc_18000C5F3
0x18000c7c4  mov     rax, [rcx+8]
0x18000c7c8  cmp     rcx, [rax]
0x18000c7cb  jnz     loc_18000C8E6
0x18000c7d1  mov     [rax], rdx
0x18000c7d4  jmp     loc_18000C748
0x18000c7d9  mov     [rax+10h], rcx
0x18000c7dd  mov     [rcx+10h], r9
0x18000c7e1  mov     [r9+8], rcx
0x18000c7e5  mov     byte ptr [r8+18h], 1
0x18000c7ea  jmp     loc_18000C501
0x18000c7ef  mov     [rax+10h], rdx
0x18000c7f3  mov     [rdx+10h], rcx
0x18000c7f7  mov     [rcx+8], rdx
0x18000c7fb  mov     rcx, [r9+10h]
0x18000c7ff  movzx   eax, byte ptr [r9+18h]
0x18000c804  mov     [rcx+18h], al
0x18000c807  mov     byte ptr [r9+18h], 1
0x18000c80c  mov     rax, [rcx+10h]
0x18000c810  mov     byte ptr [rax+18h], 1
0x18000c814  mov     rcx, [r9+10h]
0x18000c818  mov     rax, [rcx]
0x18000c81b  mov     [r9+10h], rax
0x18000c81f  mov     rax, [rcx]
0x18000c822  cmp     byte ptr [rax+19h], 0
0x18000c826  jz      loc_18000C8CB
0x18000c82c  mov     rax, [r9+8]
0x18000c830  mov     [rcx+8], rax
0x18000c834  mov     rax, [rbx]
  ... truncated ...
```
