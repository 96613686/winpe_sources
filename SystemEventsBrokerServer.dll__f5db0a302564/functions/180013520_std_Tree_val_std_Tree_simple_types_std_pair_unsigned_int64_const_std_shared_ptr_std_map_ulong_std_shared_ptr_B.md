# std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>>>,std::_Iterator_base0>)

- ea: `0x180013520`
- end: `0x1800137ba`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `666`
- prototype: `__int64 *__fastcall(__int64 **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018d7c`

## callees

- `0x1800115f8`
- `0x180011648`
- `0x180013520`
- `0x1800137c0`
- `0x180016c08`

## pseudocode

```c
__int64 *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Extract(
        __int64 **a1,
        __int64 a2)
{
  __int64 *v3; // r9
  __int64 v4; // r10
  __int64 v5; // rdx
  __int64 v6; // r11
  __int64 *v7; // r8
  __int64 v8; // rax
  __int64 *v9; // rcx
  __int64 i; // rdx
  _QWORD *v11; // rax
  __int64 *v12; // rcx
  char v13; // cl
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 *result; // rax
  __int64 *v18; // [rsp+38h] [rbp+10h] BYREF

  v18 = (__int64 *)a2;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++((__int64 *)&v18);
  v4 = v3[2];
  if ( *(_BYTE *)(*v3 + 25) )
    goto LABEL_5;
  if ( *(_BYTE *)(v4 + 25) )
  {
    v4 = *v3;
LABEL_5:
    v6 = v3[1];
    if ( !*(_BYTE *)(v4 + 25) )
      *(_QWORD *)(v4 + 8) = v6;
    if ( (__int64 *)(*a1)[1] == v3 )
    {
      (*a1)[1] = v4;
    }
    else if ( *(__int64 **)v6 == v3 )
    {
      *(_QWORD *)v6 = v4;
    }
    else
    {
      *(_QWORD *)(v6 + 16) = v4;
    }
    v7 = *a1;
    if ( (__int64 *)**a1 == v3 )
    {
      if ( *(_BYTE *)(v4 + 25) )
        v8 = v6;
      else
        v8 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Min(v4);
      *v7 = v8;
    }
    v9 = *a1;
    if ( (__int64 *)(*a1)[2] == v3 )
    {
      if ( *(_BYTE *)(v4 + 25) )
      {
        v9[2] = v6;
      }
      else
      {
        for ( i = v4; !*(_BYTE *)(*(_QWORD *)(i + 16) + 25LL); i = *(_QWORD *)(i + 16) )
          ;
        v9[2] = i;
      }
    }
    goto LABEL_34;
  }
  v5 = (__int64)v18;
  v4 = v18[2];
  if ( v18 == v3 )
    goto LABEL_5;
  *(_QWORD *)(*v3 + 8) = v18;
  *(_QWORD *)v5 = *v3;
  if ( v5 == v3[2] )
  {
    v6 = v5;
  }
  else
  {
    v6 = *(_QWORD *)(v5 + 8);
    if ( !*(_BYTE *)(v4 + 25) )
      *(_QWORD *)(v4 + 8) = v6;
    *(_QWORD *)v6 = v4;
    *(_QWORD *)(v5 + 16) = v3[2];
    *(_QWORD *)(v3[2] + 8) = v5;
  }
  if ( (__int64 *)(*a1)[1] == v3 )
  {
    (*a1)[1] = v5;
    v11 = v3 + 1;
  }
  else
  {
    v12 = (__int64 *)v3[1];
    v11 = v3 + 1;
    if ( (__int64 *)*v12 == v3 )
      *v12 = v5;
    else
      v12[2] = v5;
  }
  *(_QWORD *)(v5 + 8) = *v11;
  v13 = *(_BYTE *)(v5 + 24);
  *(_BYTE *)(v5 + 24) = *((_BYTE *)v3 + 24);
  *((_BYTE *)v3 + 24) = v13;
LABEL_34:
  if ( *((_BYTE *)v3 + 24) != 1 )
    goto LABEL_57;
  while ( v4 != (*a1)[1] && *(_BYTE *)(v4 + 24) == 1 )
  {
    v14 = *(_QWORD *)v6;
    if ( v4 == *(_QWORD *)v6 )
    {
      v14 = *(_QWORD *)(v6 + 16);
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(a1);
        v14 = *(_QWORD *)(v6 + 16);
      }
      if ( !*(_BYTE *)(v14 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)v14 + 24LL) != 1 || *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
            *(_BYTE *)(v14 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(
              a1,
              v14);
            v14 = *(_QWORD *)(v6 + 16);
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(a1);
          break;
        }
LABEL_51:
        *(_BYTE *)(v14 + 24) = 0;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(
          a1,
          v6);
        v14 = *(_QWORD *)v6;
      }
      if ( !*(_BYTE *)(v14 + 25) )
      {
        v15 = *(_QWORD *)(v14 + 16);
        if ( *(_BYTE *)(v15 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v14 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v14 + 24LL) == 1 )
          {
            *(_BYTE *)(v15 + 24) = 1;
            *(_BYTE *)(v14 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(a1);
            v14 = *(_QWORD *)v6;
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(
            a1,
            v6);
          break;
        }
        goto LABEL_51;
      }
    }
    v4 = v6;
    v6 = *(_QWORD *)(v6 + 8);
  }
  *(_BYTE *)(v4 + 24) = 1;
LABEL_57:
  v16 = a1[1];
  result = v3;
  if ( v16 )
    a1[1] = (__int64 *)((char *)v16 - 1);
  return result;
}

```

## disassembly

```asm
0x180013520  mov     [rsp+arg_8], rdx
0x180013525  push    rbx
0x180013526  sub     rsp, 20h
0x18001352a  mov     rbx, rcx
0x18001352d  mov     r9, rdx
0x180013530  lea     rcx, [rsp+28h+arg_8]
0x180013535  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(void)
0x18001353a  mov     rcx, [r9]
0x18001353d  mov     r10, [r9+10h]
0x180013541  cmp     byte ptr [rcx+19h], 0
0x180013545  jnz     short loc_180013565
0x180013547  cmp     byte ptr [r10+19h], 0
0x18001354c  jz      short loc_180013553
0x18001354e  mov     r10, rcx
0x180013551  jmp     short loc_180013565
0x180013553  mov     rdx, [rsp+28h+arg_8]
0x180013558  mov     r10, [rdx+10h]
0x18001355c  cmp     rdx, r9
0x18001355f  jnz     loc_1800135F1
0x180013565  cmp     byte ptr [r10+19h], 0
0x18001356a  mov     r11, [r9+8]
0x18001356e  jnz     short loc_180013574
0x180013570  mov     [r10+8], r11
0x180013574  mov     rax, [rbx]
0x180013577  cmp     [rax+8], r9
0x18001357b  jnz     short loc_180013583
0x18001357d  mov     [rax+8], r10
0x180013581  jmp     short loc_180013591
0x180013583  cmp     [r11], r9
0x180013586  jnz     short loc_18001358D
0x180013588  mov     [r11], r10
0x18001358b  jmp     short loc_180013591
0x18001358d  mov     [r11+10h], r10
0x180013591  mov     r8, [rbx]
0x180013594  cmp     [r8], r9
0x180013597  jnz     short loc_1800135B0
0x180013599  cmp     byte ptr [r10+19h], 0
0x18001359e  jz      short loc_1800135A5
0x1800135a0  mov     rax, r11
0x1800135a3  jmp     short loc_1800135AD
0x1800135a5  mov     rcx, r10
0x1800135a8  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Min(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x1800135ad  mov     [r8], rax
0x1800135b0  mov     rcx, [rbx]
0x1800135b3  cmp     [rcx+10h], r9
0x1800135b7  jnz     loc_180013668
0x1800135bd  cmp     byte ptr [r10+19h], 0
0x1800135c2  jz      short loc_1800135D0
0x1800135c4  mov     rdx, r11
0x1800135c7  mov     [rcx+10h], rdx
0x1800135cb  jmp     loc_180013668
0x1800135d0  mov     rax, [r10+10h]
0x1800135d4  mov     rdx, r10
0x1800135d7  cmp     byte ptr [rax+19h], 0
0x1800135db  jnz     short loc_1800135EB
0x1800135dd  mov     rdx, [rdx+10h]
0x1800135e1  mov     rax, [rdx+10h]
0x1800135e5  cmp     byte ptr [rax+19h], 0
0x1800135e9  jz      short loc_1800135DD
0x1800135eb  mov     [rcx+10h], rdx
0x1800135ef  jmp     short loc_180013668
0x1800135f1  mov     [rcx+8], rdx
0x1800135f5  mov     rax, [r9]
0x1800135f8  mov     [rdx], rax
0x1800135fb  cmp     rdx, [r9+10h]
0x1800135ff  jnz     short loc_180013606
0x180013601  mov     r11, rdx
0x180013604  jmp     short loc_180013628
0x180013606  cmp     byte ptr [r10+19h], 0
0x18001360b  mov     r11, [rdx+8]
0x18001360f  jnz     short loc_180013615
0x180013611  mov     [r10+8], r11
0x180013615  mov     [r11], r10
0x180013618  mov     rax, [r9+10h]
0x18001361c  mov     [rdx+10h], rax
0x180013620  mov     rax, [r9+10h]
0x180013624  mov     [rax+8], rdx
0x180013628  mov     rax, [rbx]
0x18001362b  cmp     [rax+8], r9
0x18001362f  jnz     short loc_18001363B
0x180013631  mov     [rax+8], rdx
0x180013635  lea     rax, [r9+8]
0x180013639  jmp     short loc_180013651
0x18001363b  mov     rcx, [r9+8]
0x18001363f  lea     rax, [r9+8]
0x180013643  cmp     [rcx], r9
0x180013646  jnz     short loc_18001364D
0x180013648  mov     [rcx], rdx
0x18001364b  jmp     short loc_180013651
0x18001364d  mov     [rcx+10h], rdx
0x180013651  mov     rax, [rax]
0x180013654  mov     [rdx+8], rax
0x180013658  movzx   eax, byte ptr [r9+18h]
0x18001365d  movzx   ecx, byte ptr [rdx+18h]
0x180013661  mov     [rdx+18h], al
0x180013664  mov     [r9+18h], cl
0x180013668  cmp     byte ptr [r9+18h], 1
0x18001366d  jnz     loc_1800137A1
0x180013673  mov     rax, [rbx]
0x180013676  cmp     r10, [rax+8]
0x18001367a  jz      loc_18001379C
0x180013680  cmp     byte ptr [r10+18h], 1
0x180013685  jnz     loc_18001379C
0x18001368b  mov     rdx, [r11]
0x18001368e  cmp     r10, rdx
0x180013691  jnz     loc_18001371B
0x180013697  mov     rdx, [r11+10h]
0x18001369b  cmp     byte ptr [rdx+18h], 0
0x18001369f  jnz     short loc_1800136B9
0x1800136a1  mov     byte ptr [rdx+18h], 1
0x1800136a5  mov     rcx, rbx
0x1800136a8  mov     rdx, r11
0x1800136ab  mov     byte ptr [r11+18h], 0
0x1800136b0  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x1800136b5  mov     rdx, [r11+10h]
0x1800136b9  cmp     byte ptr [rdx+19h], 0
0x1800136bd  jnz     loc_180013755
0x1800136c3  mov     r8, [rdx]
0x1800136c6  cmp     byte ptr [r8+18h], 1
0x1800136cb  jnz     short loc_1800136D7
0x1800136cd  mov     rax, [rdx+10h]
0x1800136d1  cmp     byte ptr [rax+18h], 1
0x1800136d5  jz      short loc_180013751
0x1800136d7  mov     rax, [rdx+10h]
0x1800136db  cmp     byte ptr [rax+18h], 1
0x1800136df  jnz     short loc_1800136F6
0x1800136e1  mov     byte ptr [r8+18h], 1
0x1800136e6  mov     rcx, rbx
0x1800136e9  mov     byte ptr [rdx+18h], 0
0x1800136ed  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x1800136f2  mov     rdx, [r11+10h]
0x1800136f6  movzx   eax, byte ptr [r11+18h]
0x1800136fb  mov     rcx, rbx
0x1800136fe  mov     [rdx+18h], al
0x180013701  mov     byte ptr [r11+18h], 1
0x180013706  mov     rax, [rdx+10h]
0x18001370a  mov     rdx, r11
0x18001370d  mov     byte ptr [rax+18h], 1
0x180013711  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x180013716  jmp     loc_18001379C
0x18001371b  cmp     byte ptr [rdx+18h], 0
0x18001371f  jnz     short loc_180013738
0x180013721  mov     byte ptr [rdx+18h], 1
0x180013725  mov     rcx, rbx
0x180013728  mov     rdx, r11
0x18001372b  mov     byte ptr [r11+18h], 0
0x180013730  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x180013735  mov     rdx, [r11]
0x180013738  cmp     byte ptr [rdx+19h], 0
0x18001373c  jnz     short loc_180013755
0x18001373e  mov     rcx, [rdx+10h]
0x180013742  cmp     byte ptr [rcx+18h], 1
0x180013746  jnz     short loc_180013761
0x180013748  mov     rax, [rdx]
0x18001374b  cmp     byte ptr [rax+18h], 1
0x18001374f  jnz     short loc_180013761
0x180013751  mov     byte ptr [rdx+18h], 0
0x180013755  mov     r10, r11
0x180013758  mov     r11, [r11+8]
0x18001375c  jmp     loc_180013673
0x180013761  mov     rax, [rdx]
0x180013764  cmp     byte ptr [rax+18h], 1
0x180013768  jnz     short loc_18001377D
0x18001376a  mov     byte ptr [rcx+18h], 1
0x18001376e  mov     rcx, rbx
0x180013771  mov     byte ptr [rdx+18h], 0
0x180013775  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x18001377a  mov     rdx, [r11]
0x18001377d  movzx   eax, byte ptr [r11+18h]
0x180013782  mov     rcx, rbx
0x180013785  mov     [rdx+18h], al
0x180013788  mov     byte ptr [r11+18h], 1
0x18001378d  mov     rax, [rdx]
0x180013790  mov     rdx, r11
0x180013793  mov     byte ptr [rax+18h], 1
0x180013797  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x18001379c  mov     byte ptr [r10+18h], 1
0x1800137a1  mov     rcx, [rbx+8]
0x1800137a5  mov     rax, r9
0x1800137a8  test    rcx, rcx
0x1800137ab  jz      short loc_1800137B4
0x1800137ad  dec     rcx
0x1800137b0  mov     [rbx+8], rcx
0x1800137b4  add     rsp, 20h
0x1800137b8  pop     rbx
0x1800137b9  retn
```
