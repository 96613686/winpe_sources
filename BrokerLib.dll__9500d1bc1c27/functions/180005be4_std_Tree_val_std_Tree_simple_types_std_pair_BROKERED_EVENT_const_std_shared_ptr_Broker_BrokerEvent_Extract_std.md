# std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>)

- ea: `0x180005be4`
- end: `0x180005ed1`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `749`
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
- `0x180005be4`

## pseudocode

```c
__int64 *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(
        __int64 **a1,
        __int64 a2)
{
  __int64 *v3; // r11
  __int64 v4; // r10
  __int64 v5; // r9
  __int64 *v6; // r8
  __int64 *v7; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rax
  __int64 *v11; // rcx
  char v12; // cl
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 *v18; // [rsp+38h] [rbp+10h] BYREF

  v18 = (__int64 *)a2;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++((__int64 *)&v18);
  v4 = v3[2];
  if ( *(_BYTE *)(*v3 + 25) )
    goto LABEL_2;
  if ( *(_BYTE *)(v4 + 25) )
  {
    v4 = *v3;
    goto LABEL_2;
  }
  v9 = (__int64)v18;
  v4 = v18[2];
  if ( v18 == v3 )
  {
LABEL_2:
    v5 = v3[1];
    if ( !*(_BYTE *)(v4 + 25) )
      *(_QWORD *)(v4 + 8) = v5;
    if ( (__int64 *)(*a1)[1] == v3 )
    {
      (*a1)[1] = v4;
    }
    else if ( *(__int64 **)v5 == v3 )
    {
      *(_QWORD *)v5 = v4;
    }
    else
    {
      *(_QWORD *)(v5 + 16) = v4;
    }
    v6 = *a1;
    if ( (__int64 *)**a1 == v3 )
    {
      if ( *(_BYTE *)(v4 + 25) )
        v17 = v5;
      else
        v17 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>>::_Min(v4);
      *v6 = v17;
    }
    if ( (__int64 *)(*a1)[2] == v3 )
    {
      if ( *(_BYTE *)(v4 + 25) )
      {
        v14 = v5;
      }
      else
      {
        v16 = *(_QWORD *)(v4 + 16);
        v14 = v4;
        while ( !*(_BYTE *)(v16 + 25) )
        {
          v14 = *(_QWORD *)(v14 + 16);
          v16 = *(_QWORD *)(v14 + 16);
        }
      }
      (*a1)[2] = v14;
    }
    goto LABEL_9;
  }
  *(_QWORD *)(*v3 + 8) = v18;
  *(_QWORD *)v9 = *v3;
  if ( v9 == v3[2] )
  {
    v5 = v9;
  }
  else
  {
    v5 = *(_QWORD *)(v9 + 8);
    if ( !*(_BYTE *)(v4 + 25) )
      *(_QWORD *)(v4 + 8) = v5;
    *(_QWORD *)v5 = v4;
    *(_QWORD *)(v9 + 16) = v3[2];
    *(_QWORD *)(v3[2] + 8) = v9;
  }
  if ( (__int64 *)(*a1)[1] == v3 )
  {
    (*a1)[1] = v9;
    v10 = v3 + 1;
  }
  else
  {
    v10 = v3 + 1;
    v11 = (__int64 *)v3[1];
    if ( (__int64 *)*v11 == v3 )
      *v11 = v9;
    else
      v11[2] = v9;
  }
  *(_QWORD *)(v9 + 8) = *v10;
  v12 = *(_BYTE *)(v9 + 24);
  *(_BYTE *)(v9 + 24) = *((_BYTE *)v3 + 24);
  *((_BYTE *)v3 + 24) = v12;
LABEL_9:
  if ( *((_BYTE *)v3 + 24) != 1 )
    goto LABEL_10;
  while ( v4 != (*a1)[1] && *(_BYTE *)(v4 + 24) == 1 )
  {
    v13 = *(_QWORD *)v5;
    if ( v4 == *(_QWORD *)v5 )
    {
      v13 = *(_QWORD *)(v5 + 16);
      if ( !*(_BYTE *)(v13 + 24) )
      {
        *(_BYTE *)(v13 + 24) = 1;
        *(_BYTE *)(v5 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
          a1,
          v5);
        v13 = *(_QWORD *)(v5 + 16);
      }
      if ( !*(_BYTE *)(v13 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)v13 + 24LL) != 1 || *(_BYTE *)(*(_QWORD *)(v13 + 16) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v13 + 16) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v13 + 24LL) = 1;
            *(_BYTE *)(v13 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
            v13 = *(_QWORD *)(v5 + 16);
          }
          *(_BYTE *)(v13 + 24) = *(_BYTE *)(v5 + 24);
          *(_BYTE *)(v5 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v13 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
            a1,
            v5);
          break;
        }
        goto LABEL_38;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v13 + 24) )
      {
        *(_BYTE *)(v13 + 24) = 1;
        *(_BYTE *)(v5 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
        v13 = *(_QWORD *)v5;
      }
      if ( !*(_BYTE *)(v13 + 25) )
      {
        v15 = *(_QWORD *)(v13 + 16);
        if ( *(_BYTE *)(v15 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v13 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v13 + 24LL) == 1 )
          {
            *(_BYTE *)(v15 + 24) = 1;
            *(_BYTE *)(v13 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
              a1,
              v13);
            v13 = *(_QWORD *)v5;
          }
          *(_BYTE *)(v13 + 24) = *(_BYTE *)(v5 + 24);
          *(_BYTE *)(v5 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v13 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
          break;
        }
LABEL_38:
        *(_BYTE *)(v13 + 24) = 0;
      }
    }
    v4 = v5;
    v5 = *(_QWORD *)(v5 + 8);
  }
  *(_BYTE *)(v4 + 24) = 1;
LABEL_10:
  v7 = a1[1];
  if ( v7 )
    a1[1] = (__int64 *)((char *)v7 - 1);
  return v3;
}

```

## disassembly

```asm
0x180005be4  mov     [rsp+arg_0], rbx
0x180005be9  mov     [rsp+arg_8], rdx
0x180005bee  push    rsi
0x180005bef  sub     rsp, 20h
0x180005bf3  mov     rbx, rcx
0x180005bf6  mov     r11, rdx
0x180005bf9  lea     rcx, [rsp+28h+arg_8]
0x180005bfe  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)
0x180005c03  mov     rcx, [r11]
0x180005c06  xor     esi, esi
0x180005c08  mov     r10, [r11+10h]
0x180005c0c  cmp     [rcx+19h], sil
0x180005c10  jz      short loc_180005C7C
0x180005c12  mov     r9, [r11+8]
0x180005c16  cmp     [r10+19h], sil
0x180005c1a  jnz     short loc_180005C20
0x180005c1c  mov     [r10+8], r9
0x180005c20  mov     rax, [rbx]
0x180005c23  cmp     [rax+8], r11
0x180005c27  jz      loc_180005E28
0x180005c2d  cmp     [r9], r11
0x180005c30  jz      loc_180005D1F
0x180005c36  mov     [r9+10h], r10
0x180005c3a  mov     r8, [rbx]
0x180005c3d  cmp     [r8], r11
0x180005c40  jz      loc_180005E4D
0x180005c46  mov     rdx, [rbx]
0x180005c49  cmp     [rdx+10h], r11
0x180005c4d  jz      loc_180005D8C
0x180005c53  cmp     byte ptr [r11+18h], 1
0x180005c58  jz      loc_180005CEA
0x180005c5e  mov     rcx, [rbx+8]
0x180005c62  test    rcx, rcx
0x180005c65  jz      short loc_180005C6E
0x180005c67  dec     rcx
0x180005c6a  mov     [rbx+8], rcx
0x180005c6e  mov     rbx, [rsp+28h+arg_0]
0x180005c73  mov     rax, r11
0x180005c76  add     rsp, 20h
0x180005c7a  pop     rsi
0x180005c7b  retn
0x180005c7c  cmp     [r10+19h], sil
0x180005c80  jnz     loc_180005E20
0x180005c86  mov     rdx, [rsp+28h+arg_8]
0x180005c8b  mov     r10, [rdx+10h]
0x180005c8f  cmp     rdx, r11
0x180005c92  jz      loc_180005C12
0x180005c98  mov     [rcx+8], rdx
0x180005c9c  mov     rax, [r11]
0x180005c9f  mov     [rdx], rax
0x180005ca2  cmp     rdx, [r11+10h]
0x180005ca6  jnz     loc_180005DA2
0x180005cac  mov     r9, rdx
0x180005caf  mov     rax, [rbx]
0x180005cb2  cmp     [rax+8], r11
0x180005cb6  jz      loc_180005E13
0x180005cbc  lea     rax, [r11+8]
0x180005cc0  mov     rcx, [rax]
0x180005cc3  cmp     [rcx], r11
0x180005cc6  jz      loc_180005E0B
0x180005ccc  mov     [rcx+10h], rdx
0x180005cd0  mov     rax, [rax]
0x180005cd3  mov     [rdx+8], rax
0x180005cd7  mov     al, [r11+18h]
0x180005cdb  mov     cl, [rdx+18h]
0x180005cde  mov     [rdx+18h], al
0x180005ce1  mov     [r11+18h], cl
0x180005ce5  jmp     loc_180005C53
0x180005cea  mov     rax, [rbx]
0x180005ced  cmp     r10, [rax+8]
0x180005cf1  jz      short loc_180005D54
0x180005cf3  cmp     byte ptr [r10+18h], 1
0x180005cf8  jnz     short loc_180005D54
0x180005cfa  mov     rdx, [r9]
0x180005cfd  cmp     r10, rdx
0x180005d00  jz      short loc_180005D5E
0x180005d02  cmp     [rdx+18h], sil
0x180005d06  jz      loc_180005E9E
0x180005d0c  cmp     [rdx+19h], sil
0x180005d10  jz      loc_180005DC8
0x180005d16  mov     r10, r9
0x180005d19  mov     r9, [r9+8]
0x180005d1d  jmp     short loc_180005CEA
0x180005d1f  mov     [r9], r10
0x180005d22  jmp     loc_180005C3A
0x180005d27  mov     rax, [rdx+10h]
0x180005d2b  cmp     byte ptr [rax+18h], 1
0x180005d2f  jz      loc_180005E68
0x180005d35  mov     al, [r9+18h]
0x180005d39  mov     rcx, rbx
0x180005d3c  mov     [rdx+18h], al
0x180005d3f  mov     byte ptr [r9+18h], 1
0x180005d44  mov     rax, [rdx+10h]
0x180005d48  mov     rdx, r9
0x180005d4b  mov     byte ptr [rax+18h], 1
0x180005d4f  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180005d54  mov     byte ptr [r10+18h], 1
0x180005d59  jmp     loc_180005C5E
0x180005d5e  mov     rdx, [r9+10h]
0x180005d62  cmp     [rdx+18h], sil
0x180005d66  jz      loc_180005E82
0x180005d6c  cmp     [rdx+19h], sil
0x180005d70  jnz     short loc_180005D16
0x180005d72  mov     r8, [rdx]
0x180005d75  cmp     byte ptr [r8+18h], 1
0x180005d7a  jnz     short loc_180005D27
0x180005d7c  mov     rax, [rdx+10h]
0x180005d80  cmp     byte ptr [rax+18h], 1
0x180005d84  jnz     short loc_180005D27
0x180005d86  mov     [rdx+18h], sil
0x180005d8a  jmp     short loc_180005D16
0x180005d8c  cmp     [r10+19h], sil
0x180005d90  jz      loc_180005E31
0x180005d96  mov     rcx, r9
0x180005d99  mov     [rdx+10h], rcx
0x180005d9d  jmp     loc_180005C53
0x180005da2  mov     r9, [rdx+8]
0x180005da6  cmp     [r10+19h], sil
0x180005daa  jnz     short loc_180005DB0
0x180005dac  mov     [r10+8], r9
0x180005db0  mov     [r9], r10
0x180005db3  mov     rax, [r11+10h]
0x180005db7  mov     [rdx+10h], rax
0x180005dbb  mov     rax, [r11+10h]
0x180005dbf  mov     [rax+8], rdx
0x180005dc3  jmp     loc_180005CAF
0x180005dc8  mov     rcx, [rdx+10h]
0x180005dcc  cmp     byte ptr [rcx+18h], 1
0x180005dd0  jnz     short loc_180005DDB
0x180005dd2  mov     rax, [rdx]
0x180005dd5  cmp     byte ptr [rax+18h], 1
0x180005dd9  jz      short loc_180005D86
0x180005ddb  mov     rax, [rdx]
0x180005dde  cmp     byte ptr [rax+18h], 1
0x180005de2  jz      loc_180005EB9
0x180005de8  mov     al, [r9+18h]
0x180005dec  mov     rcx, rbx
0x180005def  mov     [rdx+18h], al
0x180005df2  mov     byte ptr [r9+18h], 1
0x180005df7  mov     rax, [rdx]
0x180005dfa  mov     rdx, r9
0x180005dfd  mov     byte ptr [rax+18h], 1
0x180005e01  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180005e06  jmp     loc_180005D54
0x180005e0b  mov     [rcx], rdx
0x180005e0e  jmp     loc_180005CD0
0x180005e13  mov     [rax+8], rdx
0x180005e17  lea     rax, [r11+8]
0x180005e1b  jmp     loc_180005CD0
0x180005e20  mov     r10, rcx
0x180005e23  jmp     loc_180005C12
0x180005e28  mov     [rax+8], r10
0x180005e2c  jmp     loc_180005C3A
0x180005e31  mov     rax, [r10+10h]
0x180005e35  mov     rcx, r10
0x180005e38  jmp     short loc_180005E42
0x180005e3a  mov     rcx, [rcx+10h]
0x180005e3e  mov     rax, [rcx+10h]
0x180005e42  cmp     [rax+19h], sil
0x180005e46  jz      short loc_180005E3A
0x180005e48  jmp     loc_180005D99
0x180005e4d  cmp     [r10+19h], sil
0x180005e51  jz      short loc_180005E5E
0x180005e53  mov     rax, r9
0x180005e56  mov     [r8], rax
0x180005e59  jmp     loc_180005C46
0x180005e5e  mov     rcx, r10
0x180005e61  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>>::_Min(std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *> *)
0x180005e66  jmp     short loc_180005E56
0x180005e68  mov     byte ptr [r8+18h], 1
0x180005e6d  mov     rcx, rbx
0x180005e70  mov     [rdx+18h], sil
0x180005e74  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180005e79  mov     rdx, [r9+10h]
0x180005e7d  jmp     loc_180005D35
0x180005e82  mov     byte ptr [rdx+18h], 1
0x180005e86  mov     rcx, rbx
0x180005e89  mov     rdx, r9
0x180005e8c  mov     [r9+18h], sil
0x180005e90  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180005e95  mov     rdx, [r9+10h]
0x180005e99  jmp     loc_180005D6C
0x180005e9e  mov     byte ptr [rdx+18h], 1
0x180005ea2  mov     rcx, rbx
0x180005ea5  mov     rdx, r9
0x180005ea8  mov     [r9+18h], sil
0x180005eac  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180005eb1  mov     rdx, [r9]
0x180005eb4  jmp     loc_180005D0C
0x180005eb9  mov     byte ptr [rcx+18h], 1
0x180005ebd  mov     rcx, rbx
0x180005ec0  mov     [rdx+18h], sil
0x180005ec4  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180005ec9  mov     rdx, [r9]
0x180005ecc  jmp     loc_180005DE8
```
