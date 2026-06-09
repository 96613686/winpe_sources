# std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>)

- ea: `0x180005ee0`
- end: `0x1800061fd`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `797`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004840`

## callees

- `0x180001bf0`
- `0x180002280`
- `0x1800022d8`
- `0x180005ee0`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Extract(
        __int64 **a1,
        _QWORD *a2)
{
  _QWORD *v2; // r10
  _QWORD *v3; // rdi
  __int64 **v4; // r9
  _QWORD **v5; // rsi
  _QWORD *v6; // r8
  _QWORD *v7; // rbx
  _QWORD *v8; // rbp
  char v9; // r11
  _QWORD *i; // rax
  _QWORD *v11; // r11
  __int64 *v12; // r8
  __int64 *v13; // rcx
  _BYTE *v14; // r8
  __int64 *v15; // rcx
  _QWORD *result; // rax
  _QWORD *v17; // rcx
  char v18; // dl
  _QWORD *v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r10
  __int64 v22; // rax
  _QWORD *j; // rdx

  v2 = (_QWORD *)a2[2];
  v3 = a2 + 2;
  v4 = a1;
  v5 = (_QWORD **)(a2 + 1);
  v6 = a2;
  v7 = a2;
  v8 = a2;
  v9 = *((_BYTE *)v2 + 25);
  if ( v9 )
  {
    for ( i = *v5; !*((_BYTE *)i + 25); i = (_QWORD *)i[1] )
    {
      if ( a2 != (_QWORD *)i[2] )
        break;
      a2 = i;
    }
  }
  else
  {
    i = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>>::_Min(a2[2]);
  }
  if ( *(_BYTE *)(*v6 + 25LL) )
    goto LABEL_4;
  if ( v9 )
  {
    v2 = (_QWORD *)*v6;
    goto LABEL_4;
  }
  v2 = (_QWORD *)i[2];
  if ( i == v7 )
  {
LABEL_4:
    v11 = *v5;
    if ( !*((_BYTE *)v2 + 25) )
      v2[1] = v11;
    if ( (_QWORD *)(*v4)[1] == v7 )
    {
      (*v4)[1] = (__int64)v2;
    }
    else if ( (_QWORD *)*v11 == v7 )
    {
      *v11 = v2;
    }
    else
    {
      v11[2] = v2;
    }
    v12 = *v4;
    if ( (_QWORD *)**v4 == v7 )
    {
      if ( *((_BYTE *)v2 + 25) )
        v22 = (__int64)v11;
      else
        v22 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>>::_Min(v2);
      *v12 = v22;
    }
    v13 = *v4;
    if ( (_QWORD *)(*v4)[2] == v7 )
    {
      if ( *((_BYTE *)v2 + 25) )
      {
        v13[2] = (__int64)v11;
      }
      else
      {
        for ( j = v2; !*(_BYTE *)(j[2] + 25LL); j = (_QWORD *)j[2] )
          ;
        v13[2] = (__int64)j;
      }
    }
    v14 = v8 + 3;
    goto LABEL_12;
  }
  *(_QWORD *)(*v6 + 8LL) = i;
  *i = *v6;
  if ( i == (_QWORD *)*v3 )
  {
    v11 = i;
  }
  else
  {
    v11 = (_QWORD *)i[1];
    if ( !*((_BYTE *)v2 + 25) )
      v2[1] = v11;
    *v11 = v2;
    i[2] = *v3;
    *(_QWORD *)(*v3 + 8LL) = i;
  }
  if ( (_QWORD *)(*v4)[1] == v7 )
  {
    (*v4)[1] = (__int64)i;
  }
  else
  {
    v17 = *v5;
    if ( (_QWORD *)**v5 == v7 )
      *v17 = i;
    else
      v17[2] = i;
  }
  v14 = v7 + 3;
  i[1] = *v5;
  v18 = *((_BYTE *)i + 24);
  *((_BYTE *)i + 24) = *((_BYTE *)v7 + 24);
  *((_BYTE *)v7 + 24) = v18;
LABEL_12:
  if ( *v14 != 1 )
    goto LABEL_13;
  while ( 1 )
  {
    if ( v2 == (_QWORD *)(*v4)[1] || *((_BYTE *)v2 + 24) != 1 )
      goto LABEL_40;
    v19 = (_QWORD *)*v11;
    if ( v2 == (_QWORD *)*v11 )
      break;
    if ( !*((_BYTE *)v19 + 24) )
    {
      *((_BYTE *)v19 + 24) = 1;
      *((_BYTE *)v11 + 24) = 0;
      std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(v4);
      v19 = (_QWORD *)*v11;
    }
    if ( !*((_BYTE *)v19 + 25) )
    {
      v20 = v19[2];
      if ( *(_BYTE *)(v20 + 24) != 1 || *(_BYTE *)(*v19 + 24LL) != 1 )
      {
        if ( *(_BYTE *)(*v19 + 24LL) == 1 )
        {
          *(_BYTE *)(v20 + 24) = 1;
          *((_BYTE *)v19 + 24) = 0;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
            v4,
            v19);
          v19 = (_QWORD *)*v11;
        }
        *((_BYTE *)v19 + 24) = *((_BYTE *)v11 + 24);
        *((_BYTE *)v11 + 24) = 1;
        *(_BYTE *)(*v19 + 24LL) = 1;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(v4);
LABEL_40:
        *((_BYTE *)v2 + 24) = 1;
        goto LABEL_13;
      }
      goto LABEL_46;
    }
LABEL_47:
    v2 = v11;
    v11 = (_QWORD *)v11[1];
  }
  v19 = (_QWORD *)v11[2];
  if ( !*((_BYTE *)v19 + 24) )
  {
    *((_BYTE *)v19 + 24) = 1;
    *((_BYTE *)v11 + 24) = 0;
    std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
      v4,
      v11);
    v19 = (_QWORD *)v11[2];
  }
  if ( *((_BYTE *)v19 + 25) )
    goto LABEL_47;
  if ( *(_BYTE *)(*v19 + 24LL) == 1 && *(_BYTE *)(v19[2] + 24LL) == 1 )
  {
LABEL_46:
    *((_BYTE *)v19 + 24) = 0;
    goto LABEL_47;
  }
  if ( *(_BYTE *)(v19[2] + 24LL) == 1 )
  {
    *(_BYTE *)(*v19 + 24LL) = 1;
    *((_BYTE *)v19 + 24) = 0;
    std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(v4);
    v19 = (_QWORD *)v11[2];
  }
  *((_BYTE *)v19 + 24) = *((_BYTE *)v11 + 24);
  *((_BYTE *)v11 + 24) = 1;
  *(_BYTE *)(v19[2] + 24LL) = 1;
  std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
    v4,
    v11);
  *(_BYTE *)(v21 + 24) = 1;
LABEL_13:
  v15 = v4[1];
  result = v7;
  if ( v15 )
    v4[1] = (__int64 *)((char *)v15 - 1);
  return result;
}

```

## disassembly

```asm
0x180005ee0  push    rbx
0x180005ee2  push    rbp
0x180005ee3  push    rsi
0x180005ee4  push    rdi
0x180005ee5  sub     rsp, 28h
0x180005ee9  mov     r10, [rdx+10h]
0x180005eed  lea     rdi, [rdx+10h]
0x180005ef1  mov     r9, rcx
0x180005ef4  lea     rsi, [rdx+8]
0x180005ef8  mov     r8, rdx
0x180005efb  mov     rbx, rdx
0x180005efe  mov     rbp, rdx
0x180005f01  movzx   r11d, byte ptr [r10+19h]
0x180005f06  test    r11b, r11b
0x180005f09  jnz     short loc_180005F87
0x180005f0b  mov     rcx, r10
0x180005f0e  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>>::_Min(std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *> *)
0x180005f13  mov     rcx, [r8]
0x180005f16  cmp     byte ptr [rcx+19h], 0
0x180005f1a  jz      loc_180005FB1
0x180005f20  cmp     byte ptr [r10+19h], 0
0x180005f25  mov     r11, [rsi]
0x180005f28  jnz     short loc_180005F2E
0x180005f2a  mov     [r10+8], r11
0x180005f2e  mov     rax, [r9]
0x180005f31  cmp     [rax+8], rbx
0x180005f35  jz      loc_1800060E1
0x180005f3b  cmp     [r11], rbx
0x180005f3e  jz      short loc_180005FAC
0x180005f40  mov     [r11+10h], r10
0x180005f44  mov     r8, [r9]
0x180005f47  cmp     [r8], rbx
0x180005f4a  jz      loc_18000612B
0x180005f50  mov     rcx, [r9]
0x180005f53  cmp     [rcx+10h], rbx
0x180005f57  jz      loc_18000613D
0x180005f5d  lea     r8, [rbp+18h]
0x180005f61  cmp     byte ptr [r8], 1
0x180005f65  jz      loc_180006017
0x180005f6b  mov     rcx, [r9+8]
0x180005f6f  mov     rax, rbx
0x180005f72  test    rcx, rcx
0x180005f75  jz      short loc_180005F7E
0x180005f77  dec     rcx
0x180005f7a  mov     [r9+8], rcx
0x180005f7e  add     rsp, 28h
0x180005f82  pop     rdi
0x180005f83  pop     rsi
0x180005f84  pop     rbp
0x180005f85  pop     rbx
0x180005f86  retn
0x180005f87  mov     rax, [rsi]
0x180005f8a  cmp     byte ptr [rax+19h], 0
0x180005f8e  jnz     short loc_180005F13
0x180005f90  cmp     rdx, [rax+10h]
0x180005f94  jnz     loc_180005F13
0x180005f9a  mov     rdx, rax
0x180005f9d  mov     rax, [rax+8]
0x180005fa1  cmp     byte ptr [rax+19h], 0
0x180005fa5  jz      short loc_180005F90
0x180005fa7  jmp     loc_180005F13
0x180005fac  mov     [r11], r10
0x180005faf  jmp     short loc_180005F44
0x180005fb1  test    r11b, r11b
0x180005fb4  jnz     loc_1800061A9
0x180005fba  mov     r10, [rax+10h]
0x180005fbe  cmp     rax, rbx
0x180005fc1  jz      loc_180005F20
0x180005fc7  mov     [rcx+8], rax
0x180005fcb  mov     rcx, [r8]
0x180005fce  mov     [rax], rcx
0x180005fd1  cmp     rax, [rdi]
0x180005fd4  jnz     loc_18000615A
0x180005fda  mov     r11, rax
0x180005fdd  mov     rcx, [r9]
0x180005fe0  cmp     [rcx+8], rbx
0x180005fe4  jz      loc_180006122
0x180005fea  mov     rcx, [rsi]
0x180005fed  cmp     [rcx], rbx
0x180005ff0  jnz     loc_1800060D8
0x180005ff6  mov     [rcx], rax
0x180005ff9  mov     rcx, [rsi]
0x180005ffc  lea     r8, [rbx+18h]
0x180006000  mov     [rax+8], rcx
0x180006004  movzx   ecx, byte ptr [r8]
0x180006008  movzx   edx, byte ptr [rax+18h]
0x18000600c  mov     [rax+18h], cl
0x18000600f  mov     [r8], dl
0x180006012  jmp     loc_180005F61
0x180006017  mov     rax, [r9]
0x18000601a  cmp     r10, [rax+8]
0x18000601e  jz      short loc_180006082
0x180006020  cmp     byte ptr [r10+18h], 1
0x180006025  jnz     short loc_180006082
0x180006027  mov     rdx, [r11]
0x18000602a  cmp     r10, rdx
0x18000602d  jz      short loc_18000608C
0x18000602f  cmp     byte ptr [rdx+18h], 0
0x180006033  jz      loc_1800061C7
0x180006039  cmp     byte ptr [rdx+19h], 0
0x18000603d  jnz     loc_1800060CC
0x180006043  mov     rcx, [rdx+10h]
0x180006047  cmp     byte ptr [rcx+18h], 1
0x18000604b  jnz     short loc_180006056
0x18000604d  mov     rax, [rdx]
0x180006050  cmp     byte ptr [rax+18h], 1
0x180006054  jz      short loc_1800060C8
0x180006056  mov     rax, [rdx]
0x180006059  cmp     byte ptr [rax+18h], 1
0x18000605d  jz      loc_180006191
0x180006063  movzx   eax, byte ptr [r11+18h]
0x180006068  mov     rcx, r9
0x18000606b  mov     [rdx+18h], al
0x18000606e  mov     byte ptr [r11+18h], 1
0x180006073  mov     rax, [rdx]
0x180006076  mov     rdx, r11
0x180006079  mov     byte ptr [rax+18h], 1
0x18000607d  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180006082  mov     byte ptr [r10+18h], 1
0x180006087  jmp     loc_180005F6B
0x18000608c  mov     rdx, [r11+10h]
0x180006090  cmp     byte ptr [rdx+18h], 0
0x180006094  jnz     short loc_1800060AE
0x180006096  mov     byte ptr [rdx+18h], 1
0x18000609a  mov     rcx, r9
0x18000609d  mov     rdx, r11
0x1800060a0  mov     byte ptr [r11+18h], 0
0x1800060a5  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x1800060aa  mov     rdx, [r11+10h]
0x1800060ae  cmp     byte ptr [rdx+19h], 0
0x1800060b2  jnz     short loc_1800060CC
0x1800060b4  mov     r8, [rdx]
0x1800060b7  cmp     byte ptr [r8+18h], 1
0x1800060bc  jnz     short loc_1800060EA
0x1800060be  mov     rax, [rdx+10h]
0x1800060c2  cmp     byte ptr [rax+18h], 1
0x1800060c6  jnz     short loc_1800060EA
0x1800060c8  mov     byte ptr [rdx+18h], 0
0x1800060cc  mov     r10, r11
0x1800060cf  mov     r11, [r11+8]
0x1800060d3  jmp     loc_180006017
0x1800060d8  mov     [rcx+10h], rax
0x1800060dc  jmp     loc_180005FF9
0x1800060e1  mov     [rax+8], r10
0x1800060e5  jmp     loc_180005F44
0x1800060ea  mov     rax, [rdx+10h]
0x1800060ee  cmp     byte ptr [rax+18h], 1
0x1800060f2  jz      loc_1800061E3
0x1800060f8  movzx   eax, byte ptr [r11+18h]
0x1800060fd  mov     rcx, r9
0x180006100  mov     [rdx+18h], al
0x180006103  mov     byte ptr [r11+18h], 1
0x180006108  mov     rax, [rdx+10h]
0x18000610c  mov     rdx, r11
0x18000610f  mov     byte ptr [rax+18h], 1
0x180006113  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180006118  mov     byte ptr [r10+18h], 1
0x18000611d  jmp     loc_180005F6B
0x180006122  mov     [rcx+8], rax
0x180006126  jmp     loc_180005FF9
0x18000612b  cmp     byte ptr [r10+19h], 0
0x180006130  jz      short loc_18000617B
0x180006132  mov     rax, r11
0x180006135  mov     [r8], rax
0x180006138  jmp     loc_180005F50
0x18000613d  cmp     byte ptr [r10+19h], 0
0x180006142  jnz     short loc_180006185
0x180006144  mov     rax, [r10+10h]
0x180006148  mov     rdx, r10
0x18000614b  cmp     byte ptr [rax+19h], 0
0x18000614f  jz      short loc_1800061B1
0x180006151  mov     [rcx+10h], rdx
0x180006155  jmp     loc_180005F5D
0x18000615a  cmp     byte ptr [r10+19h], 0
0x18000615f  mov     r11, [rax+8]
0x180006163  jz      short loc_1800061C1
0x180006165  mov     [r11], r10
0x180006168  mov     rcx, [rdi]
0x18000616b  mov     [rax+10h], rcx
0x18000616f  mov     rcx, [rdi]
0x180006172  mov     [rcx+8], rax
0x180006176  jmp     loc_180005FDD
0x18000617b  mov     rcx, r10
0x18000617e  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>>::_Min(std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *> *)
0x180006183  jmp     short loc_180006135
0x180006185  mov     rdx, r11
0x180006188  mov     [rcx+10h], rdx
0x18000618c  jmp     loc_180005F5D
0x180006191  mov     byte ptr [rcx+18h], 1
0x180006195  mov     rcx, r9
0x180006198  mov     byte ptr [rdx+18h], 0
0x18000619c  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x1800061a1  mov     rdx, [r11]
0x1800061a4  jmp     loc_180006063
0x1800061a9  mov     r10, rcx
0x1800061ac  jmp     loc_180005F20
0x1800061b1  mov     rdx, [rdx+10h]
0x1800061b5  mov     rax, [rdx+10h]
0x1800061b9  cmp     byte ptr [rax+19h], 0
0x1800061bd  jz      short loc_1800061B1
0x1800061bf  jmp     short loc_180006151
0x1800061c1  mov     [r10+8], r11
0x1800061c5  jmp     short loc_180006165
0x1800061c7  mov     byte ptr [rdx+18h], 1
0x1800061cb  mov     rcx, r9
0x1800061ce  mov     rdx, r11
0x1800061d1  mov     byte ptr [r11+18h], 0
0x1800061d6  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x1800061db  mov     rdx, [r11]
0x1800061de  jmp     loc_180006039
0x1800061e3  mov     byte ptr [r8+18h], 1
0x1800061e8  mov     rcx, r9
0x1800061eb  mov     byte ptr [rdx+18h], 0
0x1800061ef  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x1800061f4  mov     rdx, [r11+10h]
0x1800061f8  jmp     loc_1800060F8
```
