# std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>>,std::_Iterator_base0>)

- ea: `0x18000a3a0`
- end: `0x18000a68d`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `749`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001364c`

## callees

- `0x180001bf0`
- `0x180002280`
- `0x180002810`
- `0x180005070`
- `0x18000a3a0`

## pseudocode

```c
__int64 *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>>::_Extract(
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
  char v11; // cl
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 *v14; // rcx
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
        v16 = v5;
      else
        v16 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>>::_Min(v4);
      *v6 = v16;
    }
    if ( (__int64 *)(*a1)[2] == v3 )
    {
      if ( *(_BYTE *)(v4 + 25) )
      {
        v15 = v5;
      }
      else
      {
        v17 = *(_QWORD *)(v4 + 16);
        v15 = v4;
        while ( !*(_BYTE *)(v17 + 25) )
        {
          v15 = *(_QWORD *)(v15 + 16);
          v17 = *(_QWORD *)(v15 + 16);
        }
      }
      (*a1)[2] = v15;
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
    v14 = (__int64 *)v3[1];
    if ( (__int64 *)*v14 == v3 )
      *v14 = v9;
    else
      v14[2] = v9;
  }
  *(_QWORD *)(v9 + 8) = *v10;
  v11 = *(_BYTE *)(v9 + 24);
  *(_BYTE *)(v9 + 24) = *((_BYTE *)v3 + 24);
  *((_BYTE *)v3 + 24) = v11;
LABEL_9:
  if ( *((_BYTE *)v3 + 24) != 1 )
    goto LABEL_10;
  while ( v4 != (*a1)[1] && *(_BYTE *)(v4 + 24) == 1 )
  {
    v12 = *(_QWORD *)v5;
    if ( v4 == *(_QWORD *)v5 )
    {
      v12 = *(_QWORD *)(v5 + 16);
      if ( !*(_BYTE *)(v12 + 24) )
      {
        *(_BYTE *)(v12 + 24) = 1;
        *(_BYTE *)(v5 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
          a1,
          v5);
        v12 = *(_QWORD *)(v5 + 16);
      }
      if ( !*(_BYTE *)(v12 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)v12 + 24LL) != 1 || *(_BYTE *)(*(_QWORD *)(v12 + 16) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v12 + 16) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v12 + 24LL) = 1;
            *(_BYTE *)(v12 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
            v12 = *(_QWORD *)(v5 + 16);
          }
          *(_BYTE *)(v12 + 24) = *(_BYTE *)(v5 + 24);
          *(_BYTE *)(v5 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v12 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
            a1,
            v5);
          break;
        }
        goto LABEL_28;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v12 + 24) )
      {
        *(_BYTE *)(v12 + 24) = 1;
        *(_BYTE *)(v5 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
        v12 = *(_QWORD *)v5;
      }
      if ( !*(_BYTE *)(v12 + 25) )
      {
        v13 = *(_QWORD *)(v12 + 16);
        if ( *(_BYTE *)(v13 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v12 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v12 + 24LL) == 1 )
          {
            *(_BYTE *)(v13 + 24) = 1;
            *(_BYTE *)(v12 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
              a1,
              v12);
            v12 = *(_QWORD *)v5;
          }
          *(_BYTE *)(v12 + 24) = *(_BYTE *)(v5 + 24);
          *(_BYTE *)(v5 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v12 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
          break;
        }
LABEL_28:
        *(_BYTE *)(v12 + 24) = 0;
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
0x18000a3a0  mov     [rsp+arg_0], rbx
0x18000a3a5  mov     [rsp+arg_8], rdx
0x18000a3aa  push    rsi
0x18000a3ab  sub     rsp, 20h
0x18000a3af  mov     rbx, rcx
0x18000a3b2  mov     r11, rdx
0x18000a3b5  lea     rcx, [rsp+28h+arg_8]
0x18000a3ba  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)
0x18000a3bf  mov     rcx, [r11]
0x18000a3c2  xor     esi, esi
0x18000a3c4  mov     r10, [r11+10h]
0x18000a3c8  cmp     [rcx+19h], sil
0x18000a3cc  jz      short loc_18000A434
0x18000a3ce  mov     r9, [r11+8]
0x18000a3d2  cmp     [r10+19h], sil
0x18000a3d6  jnz     short loc_18000A3DC
0x18000a3d8  mov     [r10+8], r9
0x18000a3dc  mov     rax, [rbx]
0x18000a3df  cmp     [rax+8], r11
0x18000a3e3  jz      loc_18000A592
0x18000a3e9  cmp     [r9], r11
0x18000a3ec  jz      loc_18000A540
0x18000a3f2  mov     [r9+10h], r10
0x18000a3f6  mov     r8, [rbx]
0x18000a3f9  cmp     [r8], r11
0x18000a3fc  jz      loc_18000A5C0
0x18000a402  mov     rdx, [rbx]
0x18000a405  cmp     [rdx+10h], r11
0x18000a409  jz      loc_18000A5AE
0x18000a40f  cmp     byte ptr [r11+18h], 1
0x18000a414  jz      short loc_18000A48F
0x18000a416  mov     rcx, [rbx+8]
0x18000a41a  test    rcx, rcx
0x18000a41d  jz      short loc_18000A426
0x18000a41f  dec     rcx
0x18000a422  mov     [rbx+8], rcx
0x18000a426  mov     rbx, [rsp+28h+arg_0]
0x18000a42b  mov     rax, r11
0x18000a42e  add     rsp, 20h
0x18000a432  pop     rsi
0x18000a433  retn
0x18000a434  cmp     [r10+19h], sil
0x18000a438  jnz     loc_18000A67F
0x18000a43e  mov     rdx, [rsp+28h+arg_8]
0x18000a443  mov     r10, [rdx+10h]
0x18000a447  cmp     rdx, r11
0x18000a44a  jz      short loc_18000A3CE
0x18000a44c  mov     [rcx+8], rdx
0x18000a450  mov     rax, [r11]
0x18000a453  mov     [rdx], rax
0x18000a456  cmp     rdx, [r11+10h]
0x18000a45a  jnz     loc_18000A610
0x18000a460  mov     r9, rdx
0x18000a463  mov     rax, [rbx]
0x18000a466  cmp     [rax+8], r11
0x18000a46a  jnz     loc_18000A548
0x18000a470  mov     [rax+8], rdx
0x18000a474  lea     rax, [r11+8]
0x18000a478  mov     rax, [rax]
0x18000a47b  mov     [rdx+8], rax
0x18000a47f  mov     al, [r11+18h]
0x18000a483  mov     cl, [rdx+18h]
0x18000a486  mov     [rdx+18h], al
0x18000a489  mov     [r11+18h], cl
0x18000a48d  jmp     short loc_18000A40F
0x18000a48f  mov     rax, [rbx]
0x18000a492  cmp     r10, [rax+8]
0x18000a496  jz      loc_18000A536
0x18000a49c  cmp     byte ptr [r10+18h], 1
0x18000a4a1  jnz     loc_18000A536
0x18000a4a7  mov     rdx, [r9]
0x18000a4aa  cmp     r10, rdx
0x18000a4ad  jz      short loc_18000A4E7
0x18000a4af  cmp     [rdx+18h], sil
0x18000a4b3  jz      loc_18000A664
0x18000a4b9  cmp     [rdx+19h], sil
0x18000a4bd  jnz     short loc_18000A4DE
0x18000a4bf  mov     rcx, [rdx+10h]
0x18000a4c3  cmp     byte ptr [rcx+18h], 1
0x18000a4c7  jnz     loc_18000A55D
0x18000a4cd  mov     rax, [rdx]
0x18000a4d0  cmp     byte ptr [rax+18h], 1
0x18000a4d4  jnz     loc_18000A55D
0x18000a4da  mov     [rdx+18h], sil
0x18000a4de  mov     r10, r9
0x18000a4e1  mov     r9, [r9+8]
0x18000a4e5  jmp     short loc_18000A48F
0x18000a4e7  mov     rdx, [r9+10h]
0x18000a4eb  cmp     [rdx+18h], sil
0x18000a4ef  jz      loc_18000A5F4
0x18000a4f5  cmp     [rdx+19h], sil
0x18000a4f9  jnz     short loc_18000A4DE
0x18000a4fb  mov     r8, [rdx]
0x18000a4fe  cmp     byte ptr [r8+18h], 1
0x18000a503  jz      loc_18000A59B
0x18000a509  mov     rax, [rdx+10h]
0x18000a50d  cmp     byte ptr [rax+18h], 1
0x18000a511  jz      loc_18000A632
0x18000a517  mov     al, [r9+18h]
0x18000a51b  mov     rcx, rbx
0x18000a51e  mov     [rdx+18h], al
0x18000a521  mov     byte ptr [r9+18h], 1
0x18000a526  mov     rax, [rdx+10h]
0x18000a52a  mov     rdx, r9
0x18000a52d  mov     byte ptr [rax+18h], 1
0x18000a531  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000a536  mov     byte ptr [r10+18h], 1
0x18000a53b  jmp     loc_18000A416
0x18000a540  mov     [r9], r10
0x18000a543  jmp     loc_18000A3F6
0x18000a548  lea     rax, [r11+8]
0x18000a54c  mov     rcx, [rax]
0x18000a54f  cmp     [rcx], r11
0x18000a552  jz      short loc_18000A58A
0x18000a554  mov     [rcx+10h], rdx
0x18000a558  jmp     loc_18000A478
0x18000a55d  mov     rax, [rdx]
0x18000a560  cmp     byte ptr [rax+18h], 1
0x18000a564  jz      loc_18000A64C
0x18000a56a  mov     al, [r9+18h]
0x18000a56e  mov     rcx, rbx
0x18000a571  mov     [rdx+18h], al
0x18000a574  mov     byte ptr [r9+18h], 1
0x18000a579  mov     rax, [rdx]
0x18000a57c  mov     rdx, r9
0x18000a57f  mov     byte ptr [rax+18h], 1
0x18000a583  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000a588  jmp     short loc_18000A536
0x18000a58a  mov     [rcx], rdx
0x18000a58d  jmp     loc_18000A478
0x18000a592  mov     [rax+8], r10
0x18000a596  jmp     loc_18000A3F6
0x18000a59b  mov     rax, [rdx+10h]
0x18000a59f  cmp     byte ptr [rax+18h], 1
0x18000a5a3  jz      loc_18000A4DA
0x18000a5a9  jmp     loc_18000A509
0x18000a5ae  cmp     [r10+19h], sil
0x18000a5b2  jz      short loc_18000A5D1
0x18000a5b4  mov     rcx, r9
0x18000a5b7  mov     [rdx+10h], rcx
0x18000a5bb  jmp     loc_18000A40F
0x18000a5c0  cmp     [r10+19h], sil
0x18000a5c4  jz      short loc_18000A5EA
0x18000a5c6  mov     rax, r9
0x18000a5c9  mov     [r8], rax
0x18000a5cc  jmp     loc_18000A402
0x18000a5d1  mov     rax, [r10+10h]
0x18000a5d5  mov     rcx, r10
0x18000a5d8  jmp     short loc_18000A5E2
0x18000a5da  mov     rcx, [rcx+10h]
0x18000a5de  mov     rax, [rcx+10h]
0x18000a5e2  cmp     [rax+19h], sil
0x18000a5e6  jz      short loc_18000A5DA
0x18000a5e8  jmp     short loc_18000A5B7
0x18000a5ea  mov     rcx, r10
0x18000a5ed  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>>::_Min(std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *> *)
0x18000a5f2  jmp     short loc_18000A5C9
0x18000a5f4  mov     byte ptr [rdx+18h], 1
0x18000a5f8  mov     rcx, rbx
0x18000a5fb  mov     rdx, r9
0x18000a5fe  mov     [r9+18h], sil
0x18000a602  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000a607  mov     rdx, [r9+10h]
0x18000a60b  jmp     loc_18000A4F5
0x18000a610  mov     r9, [rdx+8]
0x18000a614  cmp     [r10+19h], sil
0x18000a618  jz      short loc_18000A687
0x18000a61a  mov     [r9], r10
0x18000a61d  mov     rax, [r11+10h]
0x18000a621  mov     [rdx+10h], rax
0x18000a625  mov     rax, [r11+10h]
0x18000a629  mov     [rax+8], rdx
0x18000a62d  jmp     loc_18000A463
0x18000a632  mov     byte ptr [r8+18h], 1
0x18000a637  mov     rcx, rbx
0x18000a63a  mov     [rdx+18h], sil
0x18000a63e  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000a643  mov     rdx, [r9+10h]
0x18000a647  jmp     loc_18000A517
0x18000a64c  mov     byte ptr [rcx+18h], 1
0x18000a650  mov     rcx, rbx
0x18000a653  mov     [rdx+18h], sil
0x18000a657  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000a65c  mov     rdx, [r9]
0x18000a65f  jmp     loc_18000A56A
0x18000a664  mov     byte ptr [rdx+18h], 1
0x18000a668  mov     rcx, rbx
0x18000a66b  mov     rdx, r9
0x18000a66e  mov     [r9+18h], sil
0x18000a672  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000a677  mov     rdx, [r9]
0x18000a67a  jmp     loc_18000A4B9
0x18000a67f  mov     r10, rcx
0x18000a682  jmp     loc_18000A3CE
0x18000a687  mov     [r10+8], r9
0x18000a68b  jmp     short loc_18000A61A
```
