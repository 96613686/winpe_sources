# std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>,std::_Iterator_base0>)

- ea: `0x180007830`
- end: `0x180007c56`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `1062`
- prototype: `__int64 **__fastcall(__int64 **, __int64 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006070`
- `0x1800061e0`
- `0x1800074c0`
- `0x180008370`

## callees

- `0x180007830`
- `0x18000b960`
- `0x18000c400`
- `0x18000c460`

## pseudocode

```c
__int64 **__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(
        __int64 **a1,
        __int64 **a2)
{
  __int64 *v2; // r10
  __int64 **v3; // rsi
  __int64 **v4; // r11
  __int64 **v5; // r9
  __int64 **v6; // rbx
  __int64 **v7; // rbp
  char v8; // di
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 **i; // r8
  __int64 *v12; // r9
  __int64 *v13; // r8
  _BYTE *v14; // r8
  __int64 *v15; // rcx
  __int64 **result; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  __int64 **v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 *v22; // rcx
  char v23; // dl
  __int64 *j; // rcx
  __int64 *v25; // rcx
  __int64 v26; // rax
  __int64 **v27; // rax

  v2 = a2[2];
  v3 = a2 + 2;
  v4 = a1;
  v5 = a2;
  v6 = a2;
  v7 = a2;
  v8 = *((_BYTE *)v2 + 25);
  if ( v8 )
  {
    v10 = (__int64)a2[1];
    for ( i = a2 + 1; !*(_BYTE *)(v10 + 25); v10 = *(_QWORD *)(v10 + 8) )
    {
      if ( a2 != *(__int64 ***)(v10 + 16) )
        break;
      a2 = (__int64 **)v10;
    }
  }
  else
  {
    v9 = (__int64 *)*v2;
    if ( *(_BYTE *)(*v2 + 25) )
    {
      v10 = (__int64)a2[2];
    }
    else
    {
      do
      {
        v10 = (__int64)v9;
        v9 = (__int64 *)*v9;
      }
      while ( !*((_BYTE *)v9 + 25) );
    }
    i = a2 + 1;
  }
  if ( *((_BYTE *)*v5 + 25) )
    goto LABEL_6;
  if ( v8 )
  {
    v2 = *v5;
    goto LABEL_6;
  }
  v2 = *(__int64 **)(v10 + 16);
  if ( (__int64 **)v10 == v6 )
  {
LABEL_6:
    v12 = *i;
    if ( !*((_BYTE *)v2 + 25) )
      v2[1] = (__int64)v12;
    if ( (__int64 **)(*v4)[1] == v6 )
    {
      (*v4)[1] = (__int64)v2;
    }
    else if ( (__int64 **)*v12 == v6 )
    {
      *v12 = (__int64)v2;
    }
    else
    {
      v12[2] = (__int64)v2;
    }
    v13 = *v4;
    if ( (__int64 **)**v4 == v6 )
    {
      if ( *((_BYTE *)v2 + 25) )
        v20 = (__int64)v12;
      else
        v20 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Min(v2);
      *v13 = v20;
    }
    if ( (__int64 **)(*v4)[2] == v6 )
    {
      if ( *((_BYTE *)v2 + 25) )
      {
        j = v12;
      }
      else
      {
        for ( j = v2; !*(_BYTE *)(j[2] + 25); j = (__int64 *)j[2] )
          ;
      }
      (*v4)[2] = (__int64)j;
    }
    v14 = v7 + 3;
    goto LABEL_14;
  }
  (*v5)[1] = v10;
  *(_QWORD *)v10 = *v5;
  if ( (__int64 *)v10 == *v3 )
  {
    v12 = (__int64 *)v10;
  }
  else
  {
    v12 = *(__int64 **)(v10 + 8);
    if ( !*((_BYTE *)v2 + 25) )
      v2[1] = (__int64)v12;
    *v12 = (__int64)v2;
    *(_QWORD *)(v10 + 16) = *v3;
    (*v3)[1] = v10;
  }
  if ( (__int64 **)(*v4)[1] == v6 )
  {
    (*v4)[1] = v10;
  }
  else
  {
    v25 = *i;
    if ( (__int64 **)**i == v6 )
      *v25 = v10;
    else
      v25[2] = v10;
  }
  v22 = *i;
  v14 = v6 + 3;
  *(_QWORD *)(v10 + 8) = v22;
  v23 = *(_BYTE *)(v10 + 24);
  *(_BYTE *)(v10 + 24) = *((_BYTE *)v6 + 24);
  *((_BYTE *)v6 + 24) = v23;
LABEL_14:
  if ( *v14 != 1 )
    goto LABEL_15;
  while ( 1 )
  {
    if ( v2 == (__int64 *)(*v4)[1] || *((_BYTE *)v2 + 24) != 1 )
      goto LABEL_39;
    v17 = *v12;
    if ( v2 == (__int64 *)*v12 )
      break;
    if ( !*(_BYTE *)(v17 + 24) )
    {
      *(_BYTE *)(v17 + 24) = 1;
      *((_BYTE *)v12 + 24) = 0;
      std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Rrotate(
        v4,
        v12);
      v17 = *v12;
    }
    if ( !*(_BYTE *)(v17 + 25) )
    {
      v21 = *(_QWORD *)(v17 + 16);
      if ( *(_BYTE *)(v21 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v17 + 24LL) != 1 )
      {
        if ( *(_BYTE *)(*(_QWORD *)v17 + 24LL) == 1 )
        {
          *(_BYTE *)(v21 + 24) = 1;
          *(_BYTE *)(v17 + 24) = 0;
          std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Lrotate(v4);
          v17 = *v12;
        }
        *(_BYTE *)(v17 + 24) = *((_BYTE *)v12 + 24);
        *((_BYTE *)v12 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)v17 + 24LL) = 1;
        v18 = (__int64 *)*v12;
        *v12 = *(_QWORD *)(*v12 + 16);
        v26 = v18[2];
        if ( !*(_BYTE *)(v26 + 25) )
          *(_QWORD *)(v26 + 8) = v12;
        v18[1] = v12[1];
        if ( v12 == (__int64 *)(*v4)[1] )
        {
          (*v4)[1] = (__int64)v18;
          v18[2] = (__int64)v12;
        }
        else
        {
          v27 = (__int64 **)v12[1];
          if ( v12 == v27[2] )
            v27[2] = v18;
          else
            *v27 = v18;
          v18[2] = (__int64)v12;
        }
        goto LABEL_38;
      }
      goto LABEL_48;
    }
LABEL_49:
    v2 = v12;
    v12 = (__int64 *)v12[1];
  }
  v17 = v12[2];
  if ( !*(_BYTE *)(v17 + 24) )
  {
    *(_BYTE *)(v17 + 24) = 1;
    *((_BYTE *)v12 + 24) = 0;
    std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Lrotate(v4);
    v17 = v12[2];
  }
  if ( *(_BYTE *)(v17 + 25) )
    goto LABEL_49;
  if ( *(_BYTE *)(*(_QWORD *)v17 + 24LL) == 1 && *(_BYTE *)(*(_QWORD *)(v17 + 16) + 24LL) == 1 )
  {
LABEL_48:
    *(_BYTE *)(v17 + 24) = 0;
    goto LABEL_49;
  }
  if ( *(_BYTE *)(*(_QWORD *)(v17 + 16) + 24LL) == 1 )
  {
    *(_BYTE *)(*(_QWORD *)v17 + 24LL) = 1;
    *(_BYTE *)(v17 + 24) = 0;
    std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Rrotate(
      v4,
      v17);
    v17 = v12[2];
  }
  *(_BYTE *)(v17 + 24) = *((_BYTE *)v12 + 24);
  *((_BYTE *)v12 + 24) = 1;
  *(_BYTE *)(*(_QWORD *)(v17 + 16) + 24LL) = 1;
  v18 = (__int64 *)v12[2];
  v12[2] = *v18;
  if ( !*(_BYTE *)(*v18 + 25) )
    *(_QWORD *)(*v18 + 8) = v12;
  v18[1] = v12[1];
  if ( v12 != (__int64 *)(*v4)[1] )
  {
    v19 = (__int64 **)v12[1];
    if ( v12 == *v19 )
      *v19 = v18;
    else
      v19[2] = v18;
    *v18 = (__int64)v12;
LABEL_38:
    v12[1] = (__int64)v18;
LABEL_39:
    *((_BYTE *)v2 + 24) = 1;
    goto LABEL_15;
  }
  (*v4)[1] = (__int64)v18;
  *v18 = (__int64)v12;
  v12[1] = (__int64)v18;
  *((_BYTE *)v2 + 24) = 1;
LABEL_15:
  v15 = v4[1];
  result = v6;
  if ( v15 )
    v4[1] = (__int64 *)((char *)v15 - 1);
  return result;
}

```

## disassembly

```asm
0x180007830  push    rbx
0x180007832  push    rbp
0x180007833  push    rsi
0x180007834  push    rdi
0x180007835  sub     rsp, 28h
0x180007839  mov     r10, [rdx+10h]
0x18000783d  lea     rsi, [rdx+10h]
0x180007841  mov     r11, rcx
0x180007844  mov     r9, rdx
0x180007847  mov     rbx, rdx
0x18000784a  mov     rbp, rdx
0x18000784d  movzx   edi, byte ptr [r10+19h]
0x180007852  test    dil, dil
0x180007855  jnz     loc_1800078F6
0x18000785b  mov     rcx, [r10]
0x18000785e  cmp     [rcx+19h], dil
0x180007862  jnz     loc_180007BD3
0x180007868  nop     dword ptr [rax+rax+00000000h]
0x180007870  mov     rdx, [rcx]
0x180007873  mov     rax, rcx
0x180007876  mov     rcx, rdx
0x180007879  cmp     byte ptr [rdx+19h], 0
0x18000787d  jz      short loc_180007870
0x18000787f  lea     r8, [rbp+8]
0x180007883  mov     rcx, [r9]
0x180007886  cmp     byte ptr [rcx+19h], 0
0x18000788a  jz      loc_180007A46
0x180007890  cmp     byte ptr [r10+19h], 0
0x180007895  mov     r9, [r8]
0x180007898  jnz     short loc_18000789E
0x18000789a  mov     [r10+8], r9
0x18000789e  mov     rax, [r11]
0x1800078a1  cmp     [rax+8], rbx
0x1800078a5  jz      loc_180007B5F
0x1800078ab  cmp     [r9], rbx
0x1800078ae  jnz     loc_180007A9D
0x1800078b4  mov     [r9], r10
0x1800078b7  mov     r8, [r11]
0x1800078ba  cmp     [r8], rbx
0x1800078bd  jz      loc_1800079F5
0x1800078c3  mov     rdx, [r11]
0x1800078c6  cmp     [rdx+10h], rbx
0x1800078ca  jz      loc_180007AA6
0x1800078d0  lea     r8, [rbp+18h]
0x1800078d4  cmp     byte ptr [r8], 1
0x1800078d8  jz      short loc_180007930
0x1800078da  mov     rcx, [r11+8]
0x1800078de  mov     rax, rbx
0x1800078e1  test    rcx, rcx
0x1800078e4  jz      short loc_1800078ED
0x1800078e6  dec     rcx
0x1800078e9  mov     [r11+8], rcx
0x1800078ed  add     rsp, 28h
0x1800078f1  pop     rdi
0x1800078f2  pop     rsi
0x1800078f3  pop     rbp
0x1800078f4  pop     rbx
0x1800078f5  retn
0x1800078f6  mov     rax, [rdx+8]
0x1800078fa  lea     r8, [rdx+8]
0x1800078fe  cmp     byte ptr [rax+19h], 0
0x180007902  jnz     loc_180007883
0x180007908  cmp     rdx, [rax+10h]
0x18000790c  jnz     loc_180007883
0x180007912  mov     rdx, rax
0x180007915  mov     rax, [rax+8]
0x180007919  cmp     byte ptr [rax+19h], 0
0x18000791d  jz      short loc_180007908
0x18000791f  jmp     loc_180007883
0x180007930  mov     rax, [r11]
0x180007933  cmp     r10, [rax+8]
0x180007937  jz      loc_1800079EB
0x18000793d  cmp     byte ptr [r10+18h], 1
0x180007942  jnz     loc_1800079EB
0x180007948  mov     rdx, [r9]
0x18000794b  cmp     r10, rdx
0x18000794e  jnz     loc_180007A0B
0x180007954  mov     rdx, [r9+10h]
0x180007958  cmp     byte ptr [rdx+18h], 0
0x18000795c  jz      loc_180007BF5
0x180007962  cmp     byte ptr [rdx+19h], 0
0x180007966  jnz     loc_180007A3A
0x18000796c  mov     r8, [rdx]
0x18000796f  cmp     byte ptr [r8+18h], 1
0x180007974  jnz     short loc_180007984
0x180007976  mov     rax, [rdx+10h]
0x18000797a  cmp     byte ptr [rax+18h], 1
0x18000797e  jz      loc_180007A36
0x180007984  mov     rax, [rdx+10h]
0x180007988  cmp     byte ptr [rax+18h], 1
0x18000798c  jz      loc_180007BDB
0x180007992  movzx   eax, byte ptr [r9+18h]
0x180007997  mov     [rdx+18h], al
0x18000799a  mov     byte ptr [r9+18h], 1
0x18000799f  mov     rax, [rdx+10h]
0x1800079a3  mov     byte ptr [rax+18h], 1
0x1800079a7  mov     rcx, [r9+10h]
0x1800079ab  mov     rax, [rcx]
0x1800079ae  mov     [r9+10h], rax
0x1800079b2  mov     rax, [rcx]
0x1800079b5  cmp     byte ptr [rax+19h], 0
0x1800079b9  jnz     short loc_1800079BF
0x1800079bb  mov     [rax+8], r9
0x1800079bf  mov     rax, [r9+8]
0x1800079c3  mov     [rcx+8], rax
0x1800079c7  mov     rax, [r11]
0x1800079ca  cmp     r9, [rax+8]
0x1800079ce  jz      loc_180007B68
0x1800079d4  mov     rax, [r9+8]
0x1800079d8  cmp     r9, [rax]
0x1800079db  jnz     loc_180007B50
0x1800079e1  mov     [rax], rcx
0x1800079e4  mov     [rcx], r9
0x1800079e7  mov     [r9+8], rcx
0x1800079eb  mov     byte ptr [r10+18h], 1
0x1800079f0  jmp     loc_1800078DA
0x1800079f5  cmp     byte ptr [r10+19h], 0
0x1800079fa  jz      loc_180007B7D
0x180007a00  mov     rax, r9
0x180007a03  mov     [r8], rax
0x180007a06  jmp     loc_1800078C3
0x180007a0b  cmp     byte ptr [rdx+18h], 0
0x180007a0f  jz      loc_180007C1A
0x180007a15  cmp     byte ptr [rdx+19h], 0
0x180007a19  jnz     short loc_180007A3A
0x180007a1b  mov     rcx, [rdx+10h]
0x180007a1f  cmp     byte ptr [rcx+18h], 1
0x180007a23  jnz     loc_180007ACF
0x180007a29  mov     rax, [rdx]
0x180007a2c  cmp     byte ptr [rax+18h], 1
0x180007a30  jnz     loc_180007ACF
0x180007a36  mov     byte ptr [rdx+18h], 0
0x180007a3a  mov     r10, r9
0x180007a3d  mov     r9, [r9+8]
0x180007a41  jmp     loc_180007930
0x180007a46  test    dil, dil
0x180007a49  jnz     loc_180007C4E
0x180007a4f  mov     r10, [rax+10h]
0x180007a53  cmp     rax, rbx
0x180007a56  jz      loc_180007890
0x180007a5c  mov     [rcx+8], rax
0x180007a60  mov     rcx, [r9]
0x180007a63  mov     [rax], rcx
0x180007a66  cmp     rax, [rsi]
0x180007a69  jnz     loc_180007B2B
0x180007a6f  mov     r9, rax
0x180007a72  mov     rcx, [r11]
0x180007a75  cmp     [rcx+8], rbx
0x180007a79  jnz     short loc_180007ABD
0x180007a7b  mov     [rcx+8], rax
0x180007a7f  mov     rcx, [r8]
0x180007a82  lea     r8, [rbx+18h]
0x180007a86  mov     [rax+8], rcx
0x180007a8a  movzx   ecx, byte ptr [r8]
0x180007a8e  movzx   edx, byte ptr [rax+18h]
0x180007a92  mov     [rax+18h], cl
0x180007a95  mov     [r8], dl
0x180007a98  jmp     loc_1800078D4
0x180007a9d  mov     [r9+10h], r10
0x180007aa1  jmp     loc_1800078B7
0x180007aa6  cmp     byte ptr [r10+19h], 0
0x180007aab  jz      loc_180007BA4
0x180007ab1  mov     rcx, r9
0x180007ab4  mov     [rdx+10h], rcx
0x180007ab8  jmp     loc_1800078D0
0x180007abd  mov     rcx, [r8]
0x180007ac0  cmp     [rcx], rbx
0x180007ac3  jz      loc_180007C12
0x180007ac9  mov     [rcx+10h], rax
0x180007acd  jmp     short loc_180007A7F
0x180007acf  mov     rax, [rdx]
0x180007ad2  cmp     byte ptr [rax+18h], 1
0x180007ad6  jz      loc_180007C36
0x180007adc  movzx   eax, byte ptr [r9+18h]
0x180007ae1  mov     [rdx+18h], al
0x180007ae4  mov     byte ptr [r9+18h], 1
0x180007ae9  mov     rax, [rdx]
0x180007aec  mov     byte ptr [rax+18h], 1
0x180007af0  mov     rcx, [r9]
0x180007af3  mov     rax, [rcx+10h]
0x180007af7  mov     [r9], rax
0x180007afa  mov     rax, [rcx+10h]
0x180007afe  cmp     byte ptr [rax+19h], 0
0x180007b02  jz      short loc_180007B59
0x180007b04  mov     rax, [r9+8]
0x180007b08  mov     [rcx+8], rax
0x180007b0c  mov     rax, [r11]
0x180007b0f  cmp     r9, [rax+8]
0x180007b13  jz      short loc_180007B8A
0x180007b15  mov     rax, [r9+8]
0x180007b19  cmp     r9, [rax+10h]
0x180007b1d  jz      short loc_180007B97
0x180007b1f  mov     [rax], rcx
0x180007b22  mov     [rcx+10h], r9
0x180007b26  jmp     loc_1800079E7
0x180007b2b  cmp     byte ptr [r10+19h], 0
0x180007b30  mov     r9, [rax+8]
0x180007b34  jnz     short loc_180007B3A
0x180007b36  mov     [r10+8], r9
0x180007b3a  mov     [r9], r10
0x180007b3d  mov     rcx, [rsi]
0x180007b40  mov     [rax+10h], rcx
0x180007b44  mov     rcx, [rsi]
0x180007b47  mov     [rcx+8], rax
0x180007b4b  jmp     loc_180007A72
0x180007b50  mov     [rax+10h], rcx
0x180007b54  jmp     loc_1800079E4
0x180007b59  mov     [rax+8], r9
0x180007b5d  jmp     short loc_180007B04
0x180007b5f  mov     [rax+8], r10
0x180007b63  jmp     loc_1800078B7
0x180007b68  mov     [rax+8], rcx
0x180007b6c  mov     [rcx], r9
0x180007b6f  mov     [r9+8], rcx
0x180007b73  mov     byte ptr [r10+18h], 1
0x180007b78  jmp     loc_1800078DA
0x180007b7d  mov     rcx, r10
0x180007b80  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Min(std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180007b85  jmp     loc_180007A03
0x180007b8a  mov     [rax+8], rcx
0x180007b8e  mov     [rcx+10h], r9
0x180007b92  jmp     loc_1800079E7
0x180007b97  mov     [rax+10h], rcx
0x180007b9b  mov     [rcx+10h], r9
0x180007b9f  jmp     loc_1800079E7
0x180007ba4  mov     rax, [r10+10h]
0x180007ba8  mov     rcx, r10
0x180007bab  cmp     byte ptr [rax+19h], 0
0x180007baf  jnz     loc_180007AB4
0x180007bb5  nop     word ptr [rax+rax+00000000h]
0x180007bc0  mov     rcx, [rcx+10h]
0x180007bc4  mov     rax, [rcx+10h]
0x180007bc8  cmp     byte ptr [rax+19h], 0
0x180007bcc  jz      short loc_180007BC0
0x180007bce  jmp     loc_180007AB4
0x180007bd3  mov     rax, r10
0x180007bd6  jmp     loc_18000787F
0x180007bdb  mov     byte ptr [r8+18h], 1
0x180007be0  mov     rcx, r11
0x180007be3  mov     byte ptr [rdx+18h], 0
0x180007be7  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Rrotate(std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180007bec  mov     rdx, [r9+10h]
0x180007bf0  jmp     loc_180007992
0x180007bf5  mov     byte ptr [rdx+18h], 1
0x180007bf9  mov     rcx, r11
0x180007bfc  mov     rdx, r9
0x180007bff  mov     byte ptr [r9+18h], 0
0x180007c04  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Lrotate(std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180007c09  mov     rdx, [r9+10h]
0x180007c0d  jmp     loc_180007962
0x180007c12  mov     [rcx], rax
0x180007c15  jmp     loc_180007A7F
0x180007c1a  mov     byte ptr [rdx+18h], 1
0x180007c1e  mov     rcx, r11
0x180007c21  mov     rdx, r9
0x180007c24  mov     byte ptr [r9+18h], 0
0x180007c29  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Rrotate(std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180007c2e  mov     rdx, [r9]
0x180007c31  jmp     loc_180007A15
0x180007c36  mov     byte ptr [rcx+18h], 1
0x180007c3a  mov     rcx, r11
0x180007c3d  mov     byte ptr [rdx+18h], 0
0x180007c41  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Lrotate(std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180007c46  mov     rdx, [r9]
0x180007c49  jmp     loc_180007ADC
0x180007c4e  mov     r10, rcx
0x180007c51  jmp     loc_180007890
```
