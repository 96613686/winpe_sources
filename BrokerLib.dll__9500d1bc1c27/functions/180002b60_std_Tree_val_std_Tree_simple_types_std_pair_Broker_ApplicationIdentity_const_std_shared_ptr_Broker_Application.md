# std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>,std::_Iterator_base0>)

- ea: `0x180002b60`
- end: `0x180002e80`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `800`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000147c`

## callees

- `0x180001bf0`
- `0x180002224`
- `0x1800025c4`
- `0x180002b60`
- `0x180003920`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Extract(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r9
  __int64 **v4; // r10
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r11
  __int64 *v8; // rcx
  _QWORD *v9; // rax
  __int64 *v10; // r8
  __int64 v11; // rax
  __int64 i; // rdx
  char v13; // cl
  __int64 *v14; // rcx
  __int64 result; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // [rsp+38h] [rbp+10h] BYREF

  v21 = a2;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>,std::_Iterator_base0>::operator++(
    &v21,
    a2,
    a3,
    a2);
  v5 = *(_QWORD *)(v3 + 16);
  if ( !*(_BYTE *)(*(_QWORD *)v3 + 25LL) )
  {
    if ( *(_BYTE *)(v5 + 25) )
    {
      v5 = *(_QWORD *)v3;
    }
    else
    {
      v6 = v21;
      v5 = *(_QWORD *)(v21 + 16);
      if ( v21 != v3 )
      {
        *(_QWORD *)(*(_QWORD *)v3 + 8LL) = v21;
        *(_QWORD *)v6 = *(_QWORD *)v3;
        if ( v6 == *(_QWORD *)(v3 + 16) )
        {
          v7 = v6;
        }
        else
        {
          v7 = *(_QWORD *)(v6 + 8);
          if ( !*(_BYTE *)(v5 + 25) )
            *(_QWORD *)(v5 + 8) = v7;
          *(_QWORD *)v7 = v5;
          *(_QWORD *)(v6 + 16) = *(_QWORD *)(v3 + 16);
          *(_QWORD *)(*(_QWORD *)(v3 + 16) + 8LL) = v6;
        }
        if ( (*v4)[1] == v3 )
        {
          (*v4)[1] = v6;
          v9 = (_QWORD *)(v3 + 8);
        }
        else
        {
          v8 = *(__int64 **)(v3 + 8);
          v9 = (_QWORD *)(v3 + 8);
          if ( *v8 == v3 )
            *v8 = v6;
          else
            v8[2] = v6;
        }
        *(_QWORD *)(v6 + 8) = *v9;
        v13 = *(_BYTE *)(v6 + 24);
        *(_BYTE *)(v6 + 24) = *(_BYTE *)(v3 + 24);
        *(_BYTE *)(v3 + 24) = v13;
        goto LABEL_25;
      }
    }
  }
  v7 = *(_QWORD *)(v3 + 8);
  if ( !*(_BYTE *)(v5 + 25) )
    *(_QWORD *)(v5 + 8) = v7;
  if ( (*v4)[1] == v3 )
  {
    (*v4)[1] = v5;
  }
  else if ( *(_QWORD *)v7 == v3 )
  {
    *(_QWORD *)v7 = v5;
  }
  else
  {
    *(_QWORD *)(v7 + 16) = v5;
  }
  v10 = *v4;
  if ( **v4 == v3 )
  {
    if ( *(_BYTE *)(v5 + 25) )
      v11 = v7;
    else
      v11 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>>::_Min(v5);
    *v10 = v11;
  }
  if ( (*v4)[2] == v3 )
  {
    if ( *(_BYTE *)(v5 + 25) )
    {
      i = v7;
    }
    else
    {
      for ( i = v5; !*(_BYTE *)(*(_QWORD *)(i + 16) + 25LL); i = *(_QWORD *)(i + 16) )
        ;
    }
    (*v4)[2] = i;
  }
LABEL_25:
  if ( *(_BYTE *)(v3 + 24) != 1 )
    goto LABEL_26;
  while ( v5 != (*v4)[1] && *(_BYTE *)(v5 + 24) == 1 )
  {
    v16 = *(_QWORD *)v7;
    if ( v5 == *(_QWORD *)v7 )
    {
      v16 = *(_QWORD *)(v7 + 16);
      if ( !*(_BYTE *)(v16 + 24) )
      {
        *(_BYTE *)(v16 + 24) = 1;
        *(_BYTE *)(v7 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Lrotate(
          v4,
          v7);
        v16 = *(_QWORD *)(v7 + 16);
      }
      if ( !*(_BYTE *)(v16 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)v16 + 24LL) != 1 || *(_BYTE *)(*(_QWORD *)(v16 + 16) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v16 + 16) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v16 + 24LL) = 1;
            *(_BYTE *)(v16 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Rrotate(v4);
            v16 = *(_QWORD *)(v7 + 16);
          }
          *(_BYTE *)(v16 + 24) = *(_BYTE *)(v7 + 24);
          *(_BYTE *)(v7 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v16 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Lrotate(
            v4,
            v7);
          break;
        }
        goto LABEL_66;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v16 + 24) )
      {
        *(_BYTE *)(v16 + 24) = 1;
        v17 = *(_QWORD *)v7;
        *(_BYTE *)(v7 + 24) = 0;
        *(_QWORD *)v7 = *(_QWORD *)(v17 + 16);
        v18 = *(_QWORD *)(v17 + 16);
        if ( !*(_BYTE *)(v18 + 25) )
          *(_QWORD *)(v18 + 8) = v7;
        *(_QWORD *)(v17 + 8) = *(_QWORD *)(v7 + 8);
        if ( v7 == (*v4)[1] )
        {
          (*v4)[1] = v17;
        }
        else
        {
          v19 = *(__int64 **)(v7 + 8);
          if ( v7 == v19[2] )
            v19[2] = v17;
          else
            *v19 = v17;
        }
        *(_QWORD *)(v17 + 16) = v7;
        v16 = *(_QWORD *)v7;
        *(_QWORD *)(v7 + 8) = v17;
      }
      if ( !*(_BYTE *)(v16 + 25) )
      {
        v20 = *(_QWORD *)(v16 + 16);
        if ( *(_BYTE *)(v20 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v16 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v16 + 24LL) == 1 )
          {
            *(_BYTE *)(v20 + 24) = 1;
            *(_BYTE *)(v16 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Lrotate(
              v4,
              v16);
            v16 = *(_QWORD *)v7;
          }
          *(_BYTE *)(v16 + 24) = *(_BYTE *)(v7 + 24);
          *(_BYTE *)(v7 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v16 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Rrotate(v4);
          break;
        }
LABEL_66:
        *(_BYTE *)(v16 + 24) = 0;
      }
    }
    v5 = v7;
    v7 = *(_QWORD *)(v7 + 8);
  }
  *(_BYTE *)(v5 + 24) = 1;
LABEL_26:
  v14 = v4[1];
  result = v3;
  if ( v14 )
    v4[1] = (__int64 *)((char *)v14 - 1);
  return result;
}

```

## disassembly

```asm
0x180002b60  mov     [rsp+arg_8], rdx
0x180002b65  push    rbx
0x180002b66  sub     rsp, 20h
0x180002b6a  mov     r10, rcx
0x180002b6d  mov     r9, rdx
0x180002b70  lea     rcx, [rsp+28h+arg_8]
0x180002b75  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>,std::_Iterator_base0>::operator++(void)
0x180002b7a  mov     rcx, [r9]
0x180002b7d  mov     rbx, [r9+10h]
0x180002b81  cmp     byte ptr [rcx+19h], 0
0x180002b85  jnz     short loc_180002BD6
0x180002b87  cmp     byte ptr [rbx+19h], 0
0x180002b8b  jnz     loc_180002E68
0x180002b91  mov     rdx, [rsp+28h+arg_8]
0x180002b96  mov     rbx, [rdx+10h]
0x180002b9a  cmp     rdx, r9
0x180002b9d  jz      short loc_180002BD6
0x180002b9f  mov     [rcx+8], rdx
0x180002ba3  mov     rax, [r9]
0x180002ba6  mov     [rdx], rax
0x180002ba9  cmp     rdx, [r9+10h]
0x180002bad  jnz     loc_180002E24
0x180002bb3  mov     r11, rdx
0x180002bb6  mov     rax, [r10]
0x180002bb9  cmp     [rax+8], r9
0x180002bbd  jz      loc_180002E4A
0x180002bc3  mov     rcx, [r9+8]
0x180002bc7  lea     rax, [r9+8]
0x180002bcb  cmp     [rcx], r9
0x180002bce  jz      short loc_180002C4D
0x180002bd0  mov     [rcx+10h], rdx
0x180002bd4  jmp     short loc_180002C50
0x180002bd6  cmp     byte ptr [rbx+19h], 0
0x180002bda  mov     r11, [r9+8]
0x180002bde  jnz     short loc_180002BE4
0x180002be0  mov     [rbx+8], r11
0x180002be4  mov     rax, [r10]
0x180002be7  cmp     [rax+8], r9
0x180002beb  jz      loc_180002E05
0x180002bf1  cmp     [r11], r9
0x180002bf4  jnz     loc_180002E0E
0x180002bfa  mov     [r11], rbx
0x180002bfd  mov     r8, [r10]
0x180002c00  cmp     [r8], r9
0x180002c03  jnz     short loc_180002C15
0x180002c05  cmp     byte ptr [rbx+19h], 0
0x180002c09  jz      loc_180002E17
0x180002c0f  mov     rax, r11
0x180002c12  mov     [r8], rax
0x180002c15  mov     rcx, [r10]
0x180002c18  cmp     [rcx+10h], r9
0x180002c1c  jnz     short loc_180002C67
0x180002c1e  cmp     byte ptr [rbx+19h], 0
0x180002c22  jnz     loc_180002DF9
0x180002c28  mov     rax, [rbx+10h]
0x180002c2c  mov     rdx, rbx
0x180002c2f  cmp     byte ptr [rax+19h], 0
0x180002c33  jnz     loc_180002DFC
0x180002c39  mov     rdx, [rdx+10h]
0x180002c3d  mov     rax, [rdx+10h]
0x180002c41  cmp     byte ptr [rax+19h], 0
0x180002c45  jnz     loc_180002DFC
0x180002c4b  jmp     short loc_180002C39
0x180002c4d  mov     [rcx], rdx
0x180002c50  mov     rax, [rax]
0x180002c53  mov     [rdx+8], rax
0x180002c57  movzx   eax, byte ptr [r9+18h]
0x180002c5c  movzx   ecx, byte ptr [rdx+18h]
0x180002c60  mov     [rdx+18h], al
0x180002c63  mov     [r9+18h], cl
0x180002c67  cmp     byte ptr [r9+18h], 1
0x180002c6c  jz      short loc_180002C90
0x180002c6e  mov     rcx, [r10+8]
0x180002c72  mov     rax, r9
0x180002c75  test    rcx, rcx
0x180002c78  jz      short loc_180002C81
0x180002c7a  dec     rcx
0x180002c7d  mov     [r10+8], rcx
0x180002c81  add     rsp, 20h
0x180002c85  pop     rbx
0x180002c86  retn
0x180002c90  mov     rax, [r10]
0x180002c93  cmp     rbx, [rax+8]
0x180002c97  jz      loc_180002DF0
0x180002c9d  cmp     byte ptr [rbx+18h], 1
0x180002ca1  jnz     loc_180002DF0
0x180002ca7  mov     rdx, [r11]
0x180002caa  cmp     rbx, rdx
0x180002cad  jz      loc_180002D6D
0x180002cb3  cmp     byte ptr [rdx+18h], 0
0x180002cb7  jnz     short loc_180002D0C
0x180002cb9  mov     byte ptr [rdx+18h], 1
0x180002cbd  mov     rcx, [r11]
0x180002cc0  mov     byte ptr [r11+18h], 0
0x180002cc5  mov     rax, [rcx+10h]
0x180002cc9  mov     [r11], rax
0x180002ccc  mov     rax, [rcx+10h]
0x180002cd0  cmp     byte ptr [rax+19h], 0
0x180002cd4  jnz     short loc_180002CDA
0x180002cd6  mov     [rax+8], r11
0x180002cda  mov     rax, [r11+8]
0x180002cde  mov     [rcx+8], rax
0x180002ce2  mov     rax, [r10]
0x180002ce5  cmp     r11, [rax+8]
0x180002ce9  jz      loc_180002E57
0x180002cef  mov     rax, [r11+8]
0x180002cf3  cmp     r11, [rax+10h]
0x180002cf7  jnz     loc_180002E60
0x180002cfd  mov     [rax+10h], rcx
0x180002d01  mov     [rcx+10h], r11
0x180002d05  mov     rdx, [r11]
0x180002d08  mov     [r11+8], rcx
0x180002d0c  cmp     byte ptr [rdx+19h], 0
0x180002d10  jnz     loc_180002E74
0x180002d16  mov     rcx, [rdx+10h]
0x180002d1a  cmp     byte ptr [rcx+18h], 1
0x180002d1e  jnz     short loc_180002D2D
0x180002d20  mov     rax, [rdx]
0x180002d23  cmp     byte ptr [rax+18h], 1
0x180002d27  jz      loc_180002E70
0x180002d2d  mov     rax, [rdx]
0x180002d30  cmp     byte ptr [rax+18h], 1
0x180002d34  jnz     short loc_180002D49
0x180002d36  mov     byte ptr [rcx+18h], 1
0x180002d3a  mov     rcx, r10
0x180002d3d  mov     byte ptr [rdx+18h], 0
0x180002d41  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Lrotate(std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> *)
0x180002d46  mov     rdx, [r11]
0x180002d49  movzx   eax, byte ptr [r11+18h]
0x180002d4e  mov     rcx, r10
0x180002d51  mov     [rdx+18h], al
0x180002d54  mov     byte ptr [r11+18h], 1
0x180002d59  mov     rax, [rdx]
0x180002d5c  mov     rdx, r11
0x180002d5f  mov     byte ptr [rax+18h], 1
0x180002d63  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Rrotate(std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> *)
0x180002d68  jmp     loc_180002DF0
0x180002d6d  mov     rdx, [r11+10h]
0x180002d71  cmp     byte ptr [rdx+18h], 0
0x180002d75  jnz     short loc_180002D8F
0x180002d77  mov     byte ptr [rdx+18h], 1
0x180002d7b  mov     rcx, r10
0x180002d7e  mov     rdx, r11
0x180002d81  mov     byte ptr [r11+18h], 0
0x180002d86  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Lrotate(std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> *)
0x180002d8b  mov     rdx, [r11+10h]
0x180002d8f  cmp     byte ptr [rdx+19h], 0
0x180002d93  jnz     loc_180002E74
0x180002d99  mov     r8, [rdx]
0x180002d9c  cmp     byte ptr [r8+18h], 1
0x180002da1  jnz     short loc_180002DB1
0x180002da3  mov     rax, [rdx+10h]
0x180002da7  cmp     byte ptr [rax+18h], 1
0x180002dab  jz      loc_180002E70
0x180002db1  mov     rax, [rdx+10h]
0x180002db5  cmp     byte ptr [rax+18h], 1
0x180002db9  jnz     short loc_180002DD0
0x180002dbb  mov     byte ptr [r8+18h], 1
0x180002dc0  mov     rcx, r10
0x180002dc3  mov     byte ptr [rdx+18h], 0
0x180002dc7  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Rrotate(std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> *)
0x180002dcc  mov     rdx, [r11+10h]
0x180002dd0  movzx   eax, byte ptr [r11+18h]
0x180002dd5  mov     rcx, r10
0x180002dd8  mov     [rdx+18h], al
0x180002ddb  mov     byte ptr [r11+18h], 1
0x180002de0  mov     rax, [rdx+10h]
0x180002de4  mov     rdx, r11
0x180002de7  mov     byte ptr [rax+18h], 1
0x180002deb  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Lrotate(std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> *)
0x180002df0  mov     byte ptr [rbx+18h], 1
0x180002df4  jmp     loc_180002C6E
0x180002df9  mov     rdx, r11
0x180002dfc  mov     [rcx+10h], rdx
0x180002e00  jmp     loc_180002C67
0x180002e05  mov     [rax+8], rbx
0x180002e09  jmp     loc_180002BFD
0x180002e0e  mov     [r11+10h], rbx
0x180002e12  jmp     loc_180002BFD
0x180002e17  mov     rcx, rbx
0x180002e1a  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>>::_Min(std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *> *)
0x180002e1f  jmp     loc_180002C12
0x180002e24  cmp     byte ptr [rbx+19h], 0
0x180002e28  mov     r11, [rdx+8]
0x180002e2c  jnz     short loc_180002E32
0x180002e2e  mov     [rbx+8], r11
0x180002e32  mov     [r11], rbx
0x180002e35  mov     rax, [r9+10h]
0x180002e39  mov     [rdx+10h], rax
0x180002e3d  mov     rax, [r9+10h]
0x180002e41  mov     [rax+8], rdx
0x180002e45  jmp     loc_180002BB6
0x180002e4a  mov     [rax+8], rdx
0x180002e4e  lea     rax, [r9+8]
0x180002e52  jmp     loc_180002C50
0x180002e57  mov     [rax+8], rcx
0x180002e5b  jmp     loc_180002D01
0x180002e60  mov     [rax], rcx
0x180002e63  jmp     loc_180002D01
0x180002e68  mov     rbx, rcx
0x180002e6b  jmp     loc_180002BD6
0x180002e70  mov     byte ptr [rdx+18h], 0
0x180002e74  mov     rbx, r11
0x180002e77  mov     r11, [r11+8]
0x180002e7b  jmp     loc_180002C90
```
