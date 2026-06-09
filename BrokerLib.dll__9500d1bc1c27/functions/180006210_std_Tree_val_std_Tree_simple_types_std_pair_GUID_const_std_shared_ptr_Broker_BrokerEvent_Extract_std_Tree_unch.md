# std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>)

- ea: `0x180006210`
- end: `0x180006538`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `808`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004840`

## callees

- `0x180001bf0`
- `0x180002280`
- `0x180002810`
- `0x180005070`
- `0x180006210`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9
  __int64 **v3; // r10
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r11
  __int64 *v7; // rcx
  _QWORD *v8; // rax
  char v9; // cl
  __int64 *v10; // rcx
  __int64 result; // rax
  __int64 *v12; // r8
  __int64 v13; // rax
  __int64 i; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // [rsp+38h] [rbp+10h] BYREF

  v20 = a2;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(&v20);
  v4 = *(_QWORD *)(v2 + 16);
  if ( !*(_BYTE *)(*(_QWORD *)v2 + 25LL) )
  {
    if ( *(_BYTE *)(v4 + 25) )
    {
      v4 = *(_QWORD *)v2;
    }
    else
    {
      v5 = v20;
      v4 = *(_QWORD *)(v20 + 16);
      if ( v20 != v2 )
      {
        *(_QWORD *)(*(_QWORD *)v2 + 8LL) = v20;
        *(_QWORD *)v5 = *(_QWORD *)v2;
        if ( v5 == *(_QWORD *)(v2 + 16) )
        {
          v6 = v5;
        }
        else
        {
          v6 = *(_QWORD *)(v5 + 8);
          if ( !*(_BYTE *)(v4 + 25) )
            *(_QWORD *)(v4 + 8) = v6;
          *(_QWORD *)v6 = v4;
          *(_QWORD *)(v5 + 16) = *(_QWORD *)(v2 + 16);
          *(_QWORD *)(*(_QWORD *)(v2 + 16) + 8LL) = v5;
        }
        if ( (*v3)[1] == v2 )
        {
          (*v3)[1] = v5;
          v8 = (_QWORD *)(v2 + 8);
        }
        else
        {
          v7 = *(__int64 **)(v2 + 8);
          v8 = (_QWORD *)(v2 + 8);
          if ( *v7 == v2 )
            *v7 = v5;
          else
            v7[2] = v5;
        }
        *(_QWORD *)(v5 + 8) = *v8;
        v9 = *(_BYTE *)(v5 + 24);
        *(_BYTE *)(v5 + 24) = *(_BYTE *)(v2 + 24);
        *(_BYTE *)(v2 + 24) = v9;
        goto LABEL_10;
      }
    }
  }
  v6 = *(_QWORD *)(v2 + 8);
  if ( !*(_BYTE *)(v4 + 25) )
    *(_QWORD *)(v4 + 8) = v6;
  if ( (*v3)[1] == v2 )
  {
    (*v3)[1] = v4;
  }
  else if ( *(_QWORD *)v6 == v2 )
  {
    *(_QWORD *)v6 = v4;
  }
  else
  {
    *(_QWORD *)(v6 + 16) = v4;
  }
  v12 = *v3;
  if ( **v3 == v2 )
  {
    if ( *(_BYTE *)(v4 + 25) )
      v13 = v6;
    else
      v13 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>>::_Min(v4);
    *v12 = v13;
  }
  if ( (*v3)[2] == v2 )
  {
    if ( *(_BYTE *)(v4 + 25) )
    {
      i = v6;
    }
    else
    {
      for ( i = v4; !*(_BYTE *)(*(_QWORD *)(i + 16) + 25LL); i = *(_QWORD *)(i + 16) )
        ;
    }
    (*v3)[2] = i;
  }
LABEL_10:
  if ( *(_BYTE *)(v2 + 24) != 1 )
    goto LABEL_11;
  while ( v4 != (*v3)[1] && *(_BYTE *)(v4 + 24) == 1 )
  {
    v15 = *(_QWORD *)v6;
    if ( v4 == *(_QWORD *)v6 )
    {
      v15 = *(_QWORD *)(v6 + 16);
      if ( !*(_BYTE *)(v15 + 24) )
      {
        *(_BYTE *)(v15 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
          v3,
          v6);
        v15 = *(_QWORD *)(v6 + 16);
      }
      if ( !*(_BYTE *)(v15 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)v15 + 24LL) != 1 || *(_BYTE *)(*(_QWORD *)(v15 + 16) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v15 + 16) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v15 + 24LL) = 1;
            *(_BYTE *)(v15 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(v3);
            v15 = *(_QWORD *)(v6 + 16);
          }
          *(_BYTE *)(v15 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v15 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
            v3,
            v6);
          break;
        }
        goto LABEL_66;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v15 + 24) )
      {
        *(_BYTE *)(v15 + 24) = 1;
        v16 = *(_QWORD *)v6;
        *(_BYTE *)(v6 + 24) = 0;
        *(_QWORD *)v6 = *(_QWORD *)(v16 + 16);
        v17 = *(_QWORD *)(v16 + 16);
        if ( !*(_BYTE *)(v17 + 25) )
          *(_QWORD *)(v17 + 8) = v6;
        *(_QWORD *)(v16 + 8) = *(_QWORD *)(v6 + 8);
        if ( v6 == (*v3)[1] )
        {
          (*v3)[1] = v16;
        }
        else
        {
          v18 = *(__int64 **)(v6 + 8);
          if ( v6 == v18[2] )
            v18[2] = v16;
          else
            *v18 = v16;
        }
        *(_QWORD *)(v16 + 16) = v6;
        v15 = *(_QWORD *)v6;
        *(_QWORD *)(v6 + 8) = v16;
      }
      if ( !*(_BYTE *)(v15 + 25) )
      {
        v19 = *(_QWORD *)(v15 + 16);
        if ( *(_BYTE *)(v19 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v15 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v15 + 24LL) == 1 )
          {
            *(_BYTE *)(v19 + 24) = 1;
            *(_BYTE *)(v15 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
              v3,
              v15);
            v15 = *(_QWORD *)v6;
          }
          *(_BYTE *)(v15 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v15 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(v3);
          break;
        }
LABEL_66:
        *(_BYTE *)(v15 + 24) = 0;
      }
    }
    v4 = v6;
    v6 = *(_QWORD *)(v6 + 8);
  }
  *(_BYTE *)(v4 + 24) = 1;
LABEL_11:
  v10 = v3[1];
  result = v2;
  if ( v10 )
    v3[1] = (__int64 *)((char *)v10 - 1);
  return result;
}

```

## disassembly

```asm
0x180006210  mov     [rsp+arg_8], rdx
0x180006215  push    rbx
0x180006216  sub     rsp, 20h
0x18000621a  mov     r10, rcx
0x18000621d  mov     r9, rdx
0x180006220  lea     rcx, [rsp+28h+arg_8]
0x180006225  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)
0x18000622a  mov     rcx, [r9]
0x18000622d  mov     rbx, [r9+10h]
0x180006231  cmp     byte ptr [rcx+19h], 0
0x180006235  jnz     loc_1800062C6
0x18000623b  cmp     byte ptr [rbx+19h], 0
0x18000623f  jnz     loc_180006520
0x180006245  mov     rdx, [rsp+28h+arg_8]
0x18000624a  mov     rbx, [rdx+10h]
0x18000624e  cmp     rdx, r9
0x180006251  jz      short loc_1800062C6
0x180006253  mov     [rcx+8], rdx
0x180006257  mov     rax, [r9]
0x18000625a  mov     [rdx], rax
0x18000625d  cmp     rdx, [r9+10h]
0x180006261  jnz     loc_1800064E0
0x180006267  mov     r11, rdx
0x18000626a  mov     rax, [r10]
0x18000626d  cmp     [rax+8], r9
0x180006271  jz      loc_1800064A9
0x180006277  mov     rcx, [r9+8]
0x18000627b  lea     rax, [r9+8]
0x18000627f  cmp     [rcx], r9
0x180006282  jnz     loc_180006506
0x180006288  mov     [rcx], rdx
0x18000628b  mov     rax, [rax]
0x18000628e  mov     [rdx+8], rax
0x180006292  movzx   eax, byte ptr [r9+18h]
0x180006297  movzx   ecx, byte ptr [rdx+18h]
0x18000629b  mov     [rdx+18h], al
0x18000629e  mov     [r9+18h], cl
0x1800062a2  cmp     byte ptr [r9+18h], 1
0x1800062a7  jz      loc_180006340
0x1800062ad  mov     rcx, [r10+8]
0x1800062b1  mov     rax, r9
0x1800062b4  test    rcx, rcx
0x1800062b7  jz      short loc_1800062C0
0x1800062b9  dec     rcx
0x1800062bc  mov     [r10+8], rcx
0x1800062c0  add     rsp, 20h
0x1800062c4  pop     rbx
0x1800062c5  retn
0x1800062c6  cmp     byte ptr [rbx+19h], 0
0x1800062ca  mov     r11, [r9+8]
0x1800062ce  jnz     short loc_1800062D4
0x1800062d0  mov     [rbx+8], r11
0x1800062d4  mov     rax, [r10]
0x1800062d7  cmp     [rax+8], r9
0x1800062db  jz      loc_1800064CA
0x1800062e1  cmp     [r11], r9
0x1800062e4  jz      loc_1800064B6
0x1800062ea  mov     [r11+10h], rbx
0x1800062ee  mov     r8, [r10]
0x1800062f1  cmp     [r8], r9
0x1800062f4  jnz     short loc_180006306
0x1800062f6  cmp     byte ptr [rbx+19h], 0
0x1800062fa  jz      loc_1800064D3
0x180006300  mov     rax, r11
0x180006303  mov     [r8], rax
0x180006306  mov     rcx, [r10]
0x180006309  cmp     [rcx+10h], r9
0x18000630d  jnz     short loc_1800062A2
0x18000630f  cmp     byte ptr [rbx+19h], 0
0x180006313  jnz     loc_1800064BE
0x180006319  mov     rax, [rbx+10h]
0x18000631d  mov     rdx, rbx
0x180006320  cmp     byte ptr [rax+19h], 0
0x180006324  jnz     loc_1800064C1
0x18000632a  mov     rdx, [rdx+10h]
0x18000632e  mov     rax, [rdx+10h]
0x180006332  cmp     byte ptr [rax+19h], 0
0x180006336  jnz     loc_1800064C1
0x18000633c  jmp     short loc_18000632A
0x180006340  mov     rax, [r10]
0x180006343  cmp     rbx, [rax+8]
0x180006347  jz      loc_1800064A0
0x18000634d  cmp     byte ptr [rbx+18h], 1
0x180006351  jnz     loc_1800064A0
0x180006357  mov     rdx, [r11]
0x18000635a  cmp     rbx, rdx
0x18000635d  jz      loc_18000641D
0x180006363  cmp     byte ptr [rdx+18h], 0
0x180006367  jnz     short loc_1800063BC
0x180006369  mov     byte ptr [rdx+18h], 1
0x18000636d  mov     rcx, [r11]
0x180006370  mov     byte ptr [r11+18h], 0
0x180006375  mov     rax, [rcx+10h]
0x180006379  mov     [r11], rax
0x18000637c  mov     rax, [rcx+10h]
0x180006380  cmp     byte ptr [rax+19h], 0
0x180006384  jnz     short loc_18000638A
0x180006386  mov     [rax+8], r11
0x18000638a  mov     rax, [r11+8]
0x18000638e  mov     [rcx+8], rax
0x180006392  mov     rax, [r10]
0x180006395  cmp     r11, [rax+8]
0x180006399  jz      loc_18000650F
0x18000639f  mov     rax, [r11+8]
0x1800063a3  cmp     r11, [rax+10h]
0x1800063a7  jnz     loc_180006518
0x1800063ad  mov     [rax+10h], rcx
0x1800063b1  mov     [rcx+10h], r11
0x1800063b5  mov     rdx, [r11]
0x1800063b8  mov     [r11+8], rcx
0x1800063bc  cmp     byte ptr [rdx+19h], 0
0x1800063c0  jnz     loc_18000652C
0x1800063c6  mov     rcx, [rdx+10h]
0x1800063ca  cmp     byte ptr [rcx+18h], 1
0x1800063ce  jnz     short loc_1800063DD
0x1800063d0  mov     rax, [rdx]
0x1800063d3  cmp     byte ptr [rax+18h], 1
0x1800063d7  jz      loc_180006528
0x1800063dd  mov     rax, [rdx]
0x1800063e0  cmp     byte ptr [rax+18h], 1
0x1800063e4  jnz     short loc_1800063F9
0x1800063e6  mov     byte ptr [rcx+18h], 1
0x1800063ea  mov     rcx, r10
0x1800063ed  mov     byte ptr [rdx+18h], 0
0x1800063f1  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x1800063f6  mov     rdx, [r11]
0x1800063f9  movzx   eax, byte ptr [r11+18h]
0x1800063fe  mov     rcx, r10
0x180006401  mov     [rdx+18h], al
0x180006404  mov     byte ptr [r11+18h], 1
0x180006409  mov     rax, [rdx]
0x18000640c  mov     rdx, r11
0x18000640f  mov     byte ptr [rax+18h], 1
0x180006413  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180006418  jmp     loc_1800064A0
0x18000641d  mov     rdx, [r11+10h]
0x180006421  cmp     byte ptr [rdx+18h], 0
0x180006425  jnz     short loc_18000643F
0x180006427  mov     byte ptr [rdx+18h], 1
0x18000642b  mov     rcx, r10
0x18000642e  mov     rdx, r11
0x180006431  mov     byte ptr [r11+18h], 0
0x180006436  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000643b  mov     rdx, [r11+10h]
0x18000643f  cmp     byte ptr [rdx+19h], 0
0x180006443  jnz     loc_18000652C
0x180006449  mov     r8, [rdx]
0x18000644c  cmp     byte ptr [r8+18h], 1
0x180006451  jnz     short loc_180006461
0x180006453  mov     rax, [rdx+10h]
0x180006457  cmp     byte ptr [rax+18h], 1
0x18000645b  jz      loc_180006528
0x180006461  mov     rax, [rdx+10h]
0x180006465  cmp     byte ptr [rax+18h], 1
0x180006469  jnz     short loc_180006480
0x18000646b  mov     byte ptr [r8+18h], 1
0x180006470  mov     rcx, r10
0x180006473  mov     byte ptr [rdx+18h], 0
0x180006477  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000647c  mov     rdx, [r11+10h]
0x180006480  movzx   eax, byte ptr [r11+18h]
0x180006485  mov     rcx, r10
0x180006488  mov     [rdx+18h], al
0x18000648b  mov     byte ptr [r11+18h], 1
0x180006490  mov     rax, [rdx+10h]
0x180006494  mov     rdx, r11
0x180006497  mov     byte ptr [rax+18h], 1
0x18000649b  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x1800064a0  mov     byte ptr [rbx+18h], 1
0x1800064a4  jmp     loc_1800062AD
0x1800064a9  mov     [rax+8], rdx
0x1800064ad  lea     rax, [r9+8]
0x1800064b1  jmp     loc_18000628B
0x1800064b6  mov     [r11], rbx
0x1800064b9  jmp     loc_1800062EE
0x1800064be  mov     rdx, r11
0x1800064c1  mov     [rcx+10h], rdx
0x1800064c5  jmp     loc_1800062A2
0x1800064ca  mov     [rax+8], rbx
0x1800064ce  jmp     loc_1800062EE
0x1800064d3  mov     rcx, rbx
0x1800064d6  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>>::_Min(std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *> *)
0x1800064db  jmp     loc_180006303
0x1800064e0  cmp     byte ptr [rbx+19h], 0
0x1800064e4  mov     r11, [rdx+8]
0x1800064e8  jnz     short loc_1800064EE
0x1800064ea  mov     [rbx+8], r11
0x1800064ee  mov     [r11], rbx
0x1800064f1  mov     rax, [r9+10h]
0x1800064f5  mov     [rdx+10h], rax
0x1800064f9  mov     rax, [r9+10h]
0x1800064fd  mov     [rax+8], rdx
0x180006501  jmp     loc_18000626A
0x180006506  mov     [rcx+10h], rdx
0x18000650a  jmp     loc_18000628B
0x18000650f  mov     [rax+8], rcx
0x180006513  jmp     loc_1800063B1
0x180006518  mov     [rax], rcx
0x18000651b  jmp     loc_1800063B1
0x180006520  mov     rbx, rcx
0x180006523  jmp     loc_1800062C6
0x180006528  mov     byte ptr [rdx+18h], 0
0x18000652c  mov     rbx, r11
0x18000652f  mov     r11, [r11+8]
0x180006533  jmp     loc_180006340
```
