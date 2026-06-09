# std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>)

- ea: `0x180004afc`
- end: `0x180004d80`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `644`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004f80`
- `0x180012034`

## callees

- `0x180002c5c`
- `0x180004afc`
- `0x180004eb8`
- `0x180004f08`
- `0x180004f2c`

## pseudocode

```c
__int64 *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Extract(
        __int64 **a1,
        __int64 *a2)
{
  __int64 *v3; // rdx
  __int64 *v4; // r11
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 *v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 *v11; // rax
  __int64 **v12; // rcx
  char v13; // cl
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 *v18; // [rsp+38h] [rbp+10h] BYREF

  v18 = a2;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(&v18);
  v5 = v4[2];
  if ( *(_BYTE *)(*v4 + 25) )
    goto LABEL_5;
  if ( *(_BYTE *)(v5 + 25) )
  {
    v5 = *v4;
LABEL_5:
    v6 = v4[1];
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v6;
    if ( (__int64 *)(*a1)[1] == v4 )
    {
      (*a1)[1] = v5;
    }
    else if ( *(__int64 **)v6 == v4 )
    {
      *(_QWORD *)v6 = v5;
    }
    else
    {
      *(_QWORD *)(v6 + 16) = v5;
    }
    v7 = *a1;
    if ( (__int64 *)**a1 == v4 )
    {
      if ( *(_BYTE *)(v5 + 25) )
        v8 = v6;
      else
        v8 = std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Min(v5, v3, v7, v6);
      *v7 = v8;
    }
    if ( (__int64 *)(*a1)[2] == v4 )
    {
      if ( *(_BYTE *)(v5 + 25) )
      {
        v9 = v6;
      }
      else
      {
        v10 = *(_QWORD *)(v5 + 16);
        v9 = v5;
        while ( !*(_BYTE *)(v10 + 25) )
        {
          v9 = *(_QWORD *)(v9 + 16);
          v10 = *(_QWORD *)(v9 + 16);
        }
      }
      (*a1)[2] = v9;
    }
    goto LABEL_35;
  }
  v3 = v18;
  v5 = v18[2];
  if ( v18 == v4 )
    goto LABEL_5;
  *(_QWORD *)(*v4 + 8) = v18;
  *v3 = *v4;
  if ( v3 == (__int64 *)v4[2] )
  {
    v6 = (__int64)v3;
  }
  else
  {
    v6 = v3[1];
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v6;
    *(_QWORD *)v6 = v5;
    v3[2] = v4[2];
    *(_QWORD *)(v4[2] + 8) = v3;
  }
  if ( (__int64 *)(*a1)[1] == v4 )
  {
    (*a1)[1] = (__int64)v3;
    v11 = v4 + 1;
  }
  else
  {
    v11 = v4 + 1;
    v12 = (__int64 **)v4[1];
    if ( *v12 == v4 )
      *v12 = v3;
    else
      v12[2] = v3;
  }
  v3[1] = *v11;
  v13 = *((_BYTE *)v3 + 24);
  *((_BYTE *)v3 + 24) = *((_BYTE *)v4 + 24);
  *((_BYTE *)v4 + 24) = v13;
LABEL_35:
  if ( *((_BYTE *)v4 + 24) != 1 )
    goto LABEL_58;
  while ( v5 != (*a1)[1] && *(_BYTE *)(v5 + 24) == 1 )
  {
    v14 = *(_QWORD *)v6;
    if ( v5 == *(_QWORD *)v6 )
    {
      v14 = *(_QWORD *)(v6 + 16);
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(a1);
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
            std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(a1, v14);
            v14 = *(_QWORD *)(v6 + 16);
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(a1);
          break;
        }
LABEL_52:
        *(_BYTE *)(v14 + 24) = 0;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(a1, v6);
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
            std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(a1);
            v14 = *(_QWORD *)v6;
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(a1, v6);
          break;
        }
        goto LABEL_52;
      }
    }
    v5 = v6;
    v6 = *(_QWORD *)(v6 + 8);
  }
  *(_BYTE *)(v5 + 24) = 1;
LABEL_58:
  v16 = a1[1];
  if ( v16 )
    a1[1] = (__int64 *)((char *)v16 - 1);
  return v4;
}

```

## disassembly

```asm
0x180004afc  mov     [rsp+arg_0], rbx
0x180004b01  mov     [rsp+arg_8], rdx
0x180004b06  push    rsi
0x180004b07  sub     rsp, 20h
0x180004b0b  mov     rbx, rcx
0x180004b0e  mov     r11, rdx
0x180004b11  lea     rcx, [rsp+28h+arg_8]
0x180004b16  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(void)
0x180004b1b  mov     r9, [r11]
0x180004b1e  xor     esi, esi
0x180004b20  mov     r10, [r11+10h]
0x180004b24  cmp     [r9+19h], sil
0x180004b28  jnz     short loc_180004B43
0x180004b2a  cmp     [r10+19h], sil
0x180004b2e  jz      short loc_180004B35
0x180004b30  mov     r10, r9
0x180004b33  jmp     short loc_180004B43
0x180004b35  mov     rdx, [rsp+28h+arg_8]
0x180004b3a  mov     r10, [rdx+10h]
0x180004b3e  cmp     rdx, r11
0x180004b41  jnz     short loc_180004BC1
0x180004b43  mov     r9, [r11+8]
0x180004b47  cmp     [r10+19h], sil
0x180004b4b  jnz     short loc_180004B51
0x180004b4d  mov     [r10+8], r9
0x180004b51  mov     rax, [rbx]
0x180004b54  cmp     [rax+8], r11
0x180004b58  jnz     short loc_180004B60
0x180004b5a  mov     [rax+8], r10
0x180004b5e  jmp     short loc_180004B6E
0x180004b60  cmp     [r9], r11
0x180004b63  jnz     short loc_180004B6A
0x180004b65  mov     [r9], r10
0x180004b68  jmp     short loc_180004B6E
0x180004b6a  mov     [r9+10h], r10
0x180004b6e  mov     r8, [rbx]
0x180004b71  cmp     [r8], r11
0x180004b74  jnz     short loc_180004B8C
0x180004b76  cmp     [r10+19h], sil
0x180004b7a  jz      short loc_180004B81
0x180004b7c  mov     rax, r9
0x180004b7f  jmp     short loc_180004B89
0x180004b81  mov     rcx, r10
0x180004b84  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@SAPEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Min(std::_Tree_node<CPolicyEntry *,void *> *)
0x180004b89  mov     [r8], rax
0x180004b8c  mov     rdx, [rbx]
0x180004b8f  cmp     [rdx+10h], r11
0x180004b93  jnz     loc_180004C34
0x180004b99  cmp     [r10+19h], sil
0x180004b9d  jz      short loc_180004BA4
0x180004b9f  mov     rcx, r9
0x180004ba2  jmp     short loc_180004BBB
0x180004ba4  mov     rax, [r10+10h]
0x180004ba8  mov     rcx, r10
0x180004bab  jmp     short loc_180004BB5
0x180004bad  mov     rcx, [rcx+10h]
0x180004bb1  mov     rax, [rcx+10h]
0x180004bb5  cmp     [rax+19h], sil
0x180004bb9  jz      short loc_180004BAD
0x180004bbb  mov     [rdx+10h], rcx
0x180004bbf  jmp     short loc_180004C34
0x180004bc1  mov     [r9+8], rdx
0x180004bc5  mov     rax, [r11]
0x180004bc8  mov     [rdx], rax
0x180004bcb  cmp     rdx, [r11+10h]
0x180004bcf  jnz     short loc_180004BD6
0x180004bd1  mov     r9, rdx
0x180004bd4  jmp     short loc_180004BF7
0x180004bd6  mov     r9, [rdx+8]
0x180004bda  cmp     [r10+19h], sil
0x180004bde  jnz     short loc_180004BE4
0x180004be0  mov     [r10+8], r9
0x180004be4  mov     [r9], r10
0x180004be7  mov     rax, [r11+10h]
0x180004beb  mov     [rdx+10h], rax
0x180004bef  mov     rax, [r11+10h]
0x180004bf3  mov     [rax+8], rdx
0x180004bf7  mov     rax, [rbx]
0x180004bfa  cmp     [rax+8], r11
0x180004bfe  jnz     short loc_180004C0A
0x180004c00  mov     [rax+8], rdx
0x180004c04  lea     rax, [r11+8]
0x180004c08  jmp     short loc_180004C1F
0x180004c0a  lea     rax, [r11+8]
0x180004c0e  mov     rcx, [rax]
0x180004c11  cmp     [rcx], r11
0x180004c14  jnz     short loc_180004C1B
0x180004c16  mov     [rcx], rdx
0x180004c19  jmp     short loc_180004C1F
0x180004c1b  mov     [rcx+10h], rdx
0x180004c1f  mov     rax, [rax]
0x180004c22  mov     [rdx+8], rax
0x180004c26  mov     al, [r11+18h]
0x180004c2a  mov     cl, [rdx+18h]
0x180004c2d  mov     [rdx+18h], al
0x180004c30  mov     [r11+18h], cl
0x180004c34  cmp     byte ptr [r11+18h], 1
0x180004c39  jnz     loc_180004D62
0x180004c3f  mov     rax, [rbx]
0x180004c42  cmp     r10, [rax+8]
0x180004c46  jz      loc_180004D5D
0x180004c4c  cmp     byte ptr [r10+18h], 1
0x180004c51  jnz     loc_180004D5D
0x180004c57  mov     rdx, [r9]
0x180004c5a  cmp     r10, rdx
0x180004c5d  jnz     short loc_180004CDE
0x180004c5f  mov     rdx, [r9+10h]
0x180004c63  cmp     [rdx+18h], sil
0x180004c67  jnz     short loc_180004C80
0x180004c69  mov     byte ptr [rdx+18h], 1
0x180004c6d  mov     rcx, rbx
0x180004c70  mov     rdx, r9
0x180004c73  mov     [r9+18h], sil
0x180004c77  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x180004c7c  mov     rdx, [r9+10h]
0x180004c80  cmp     [rdx+19h], sil
0x180004c84  jnz     loc_180004D17
0x180004c8a  mov     r8, [rdx]
0x180004c8d  cmp     byte ptr [r8+18h], 1
0x180004c92  jnz     short loc_180004C9E
0x180004c94  mov     rax, [rdx+10h]
0x180004c98  cmp     byte ptr [rax+18h], 1
0x180004c9c  jz      short loc_180004D13
0x180004c9e  mov     rax, [rdx+10h]
0x180004ca2  cmp     byte ptr [rax+18h], 1
0x180004ca6  jnz     short loc_180004CBD
0x180004ca8  mov     byte ptr [r8+18h], 1
0x180004cad  mov     rcx, rbx
0x180004cb0  mov     [rdx+18h], sil
0x180004cb4  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@QEAAXPEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(std::_Tree_node<CPolicyEntry *,void *> *)
0x180004cb9  mov     rdx, [r9+10h]
0x180004cbd  mov     al, [r9+18h]
0x180004cc1  mov     rcx, rbx
0x180004cc4  mov     [rdx+18h], al
0x180004cc7  mov     byte ptr [r9+18h], 1
0x180004ccc  mov     rax, [rdx+10h]
0x180004cd0  mov     rdx, r9
0x180004cd3  mov     byte ptr [rax+18h], 1
0x180004cd7  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x180004cdc  jmp     short loc_180004D5D
0x180004cde  cmp     [rdx+18h], sil
0x180004ce2  jnz     short loc_180004CFA
0x180004ce4  mov     byte ptr [rdx+18h], 1
0x180004ce8  mov     rcx, rbx
0x180004ceb  mov     rdx, r9
0x180004cee  mov     [r9+18h], sil
0x180004cf2  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@QEAAXPEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(std::_Tree_node<CPolicyEntry *,void *> *)
0x180004cf7  mov     rdx, [r9]
0x180004cfa  cmp     [rdx+19h], sil
0x180004cfe  jnz     short loc_180004D17
0x180004d00  mov     rcx, [rdx+10h]
0x180004d04  cmp     byte ptr [rcx+18h], 1
0x180004d08  jnz     short loc_180004D23
0x180004d0a  mov     rax, [rdx]
0x180004d0d  cmp     byte ptr [rax+18h], 1
0x180004d11  jnz     short loc_180004D23
0x180004d13  mov     [rdx+18h], sil
0x180004d17  mov     r10, r9
0x180004d1a  mov     r9, [r9+8]
0x180004d1e  jmp     loc_180004C3F
0x180004d23  mov     rax, [rdx]
0x180004d26  cmp     byte ptr [rax+18h], 1
0x180004d2a  jnz     short loc_180004D3F
0x180004d2c  mov     byte ptr [rcx+18h], 1
0x180004d30  mov     rcx, rbx
0x180004d33  mov     [rdx+18h], sil
0x180004d37  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x180004d3c  mov     rdx, [r9]
0x180004d3f  mov     al, [r9+18h]
0x180004d43  mov     rcx, rbx
0x180004d46  mov     [rdx+18h], al
0x180004d49  mov     byte ptr [r9+18h], 1
0x180004d4e  mov     rax, [rdx]
0x180004d51  mov     rdx, r9
0x180004d54  mov     byte ptr [rax+18h], 1
0x180004d58  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@QEAAXPEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(std::_Tree_node<CPolicyEntry *,void *> *)
0x180004d5d  mov     byte ptr [r10+18h], 1
0x180004d62  mov     rcx, [rbx+8]
0x180004d66  test    rcx, rcx
0x180004d69  jz      short loc_180004D72
0x180004d6b  dec     rcx
0x180004d6e  mov     [rbx+8], rcx
0x180004d72  mov     rbx, [rsp+28h+arg_0]
0x180004d77  mov     rax, r11
0x180004d7a  add     rsp, 20h
0x180004d7e  pop     rsi
0x180004d7f  retn
```
