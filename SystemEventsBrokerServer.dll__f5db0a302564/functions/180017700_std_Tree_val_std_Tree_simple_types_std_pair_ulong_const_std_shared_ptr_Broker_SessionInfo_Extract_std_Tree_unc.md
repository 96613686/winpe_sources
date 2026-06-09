# std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>)

- ea: `0x180017700`
- end: `0x180017984`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `644`
- prototype: `__int64 *__fastcall(__int64 **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018c3c`

## callees

- `0x180006d90`
- `0x1800115f8`
- `0x180011648`
- `0x180016c08`
- `0x180017700`

## pseudocode

```c
__int64 *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>::_Extract(
        __int64 **a1,
        __int64 a2)
{
  __int64 *v3; // r11
  __int64 v4; // r10
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 *v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  _QWORD *v11; // rax
  __int64 *v12; // rcx
  char v13; // cl
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 *v18; // [rsp+38h] [rbp+10h] BYREF

  v18 = (__int64 *)a2;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++((__int64 *)&v18);
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
    if ( (__int64 *)(*a1)[2] == v3 )
    {
      if ( *(_BYTE *)(v4 + 25) )
      {
        v9 = v6;
      }
      else
      {
        v10 = *(_QWORD *)(v4 + 16);
        v9 = v4;
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
    v11 = v3 + 1;
    v12 = (__int64 *)v3[1];
    if ( (__int64 *)*v12 == v3 )
      *v12 = v5;
    else
      v12[2] = v5;
  }
  *(_QWORD *)(v5 + 8) = *v11;
  v13 = *(_BYTE *)(v5 + 24);
  *(_BYTE *)(v5 + 24) = *((_BYTE *)v3 + 24);
  *((_BYTE *)v3 + 24) = v13;
LABEL_35:
  if ( *((_BYTE *)v3 + 24) != 1 )
    goto LABEL_58;
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
        goto LABEL_52;
      }
    }
    v4 = v6;
    v6 = *(_QWORD *)(v6 + 8);
  }
  *(_BYTE *)(v4 + 24) = 1;
LABEL_58:
  v16 = a1[1];
  if ( v16 )
    a1[1] = (__int64 *)((char *)v16 - 1);
  return v3;
}

```

## disassembly

```asm
0x180017700  mov     [rsp+arg_0], rbx
0x180017705  mov     [rsp+arg_8], rdx
0x18001770a  push    rsi
0x18001770b  sub     rsp, 20h
0x18001770f  mov     rbx, rcx
0x180017712  mov     r11, rdx
0x180017715  lea     rcx, [rsp+28h+arg_8]
0x18001771a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x18001771f  mov     rax, [r11]
0x180017722  xor     esi, esi
0x180017724  mov     r10, [r11+10h]
0x180017728  cmp     [rax+19h], sil
0x18001772c  jnz     short loc_180017747
0x18001772e  cmp     [r10+19h], sil
0x180017732  jz      short loc_180017739
0x180017734  mov     r10, rax
0x180017737  jmp     short loc_180017747
0x180017739  mov     rdx, [rsp+28h+arg_8]
0x18001773e  mov     r10, [rdx+10h]
0x180017742  cmp     rdx, r11
0x180017745  jnz     short loc_1800177C5
0x180017747  mov     r9, [r11+8]
0x18001774b  cmp     [r10+19h], sil
0x18001774f  jnz     short loc_180017755
0x180017751  mov     [r10+8], r9
0x180017755  mov     rax, [rbx]
0x180017758  cmp     [rax+8], r11
0x18001775c  jnz     short loc_180017764
0x18001775e  mov     [rax+8], r10
0x180017762  jmp     short loc_180017772
0x180017764  cmp     [r9], r11
0x180017767  jnz     short loc_18001776E
0x180017769  mov     [r9], r10
0x18001776c  jmp     short loc_180017772
0x18001776e  mov     [r9+10h], r10
0x180017772  mov     r8, [rbx]
0x180017775  cmp     [r8], r11
0x180017778  jnz     short loc_180017790
0x18001777a  cmp     [r10+19h], sil
0x18001777e  jz      short loc_180017785
0x180017780  mov     rax, r9
0x180017783  jmp     short loc_18001778D
0x180017785  mov     rcx, r10
0x180017788  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Min(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x18001778d  mov     [r8], rax
0x180017790  mov     rdx, [rbx]
0x180017793  cmp     [rdx+10h], r11
0x180017797  jnz     loc_180017838
0x18001779d  cmp     [r10+19h], sil
0x1800177a1  jz      short loc_1800177A8
0x1800177a3  mov     rcx, r9
0x1800177a6  jmp     short loc_1800177BF
0x1800177a8  mov     rax, [r10+10h]
0x1800177ac  mov     rcx, r10
0x1800177af  jmp     short loc_1800177B9
0x1800177b1  mov     rcx, [rcx+10h]
0x1800177b5  mov     rax, [rcx+10h]
0x1800177b9  cmp     [rax+19h], sil
0x1800177bd  jz      short loc_1800177B1
0x1800177bf  mov     [rdx+10h], rcx
0x1800177c3  jmp     short loc_180017838
0x1800177c5  mov     [rax+8], rdx
0x1800177c9  mov     rax, [r11]
0x1800177cc  mov     [rdx], rax
0x1800177cf  cmp     rdx, [r11+10h]
0x1800177d3  jnz     short loc_1800177DA
0x1800177d5  mov     r9, rdx
0x1800177d8  jmp     short loc_1800177FB
0x1800177da  mov     r9, [rdx+8]
0x1800177de  cmp     [r10+19h], sil
0x1800177e2  jnz     short loc_1800177E8
0x1800177e4  mov     [r10+8], r9
0x1800177e8  mov     [r9], r10
0x1800177eb  mov     rax, [r11+10h]
0x1800177ef  mov     [rdx+10h], rax
0x1800177f3  mov     rax, [r11+10h]
0x1800177f7  mov     [rax+8], rdx
0x1800177fb  mov     rax, [rbx]
0x1800177fe  cmp     [rax+8], r11
0x180017802  jnz     short loc_18001780E
0x180017804  mov     [rax+8], rdx
0x180017808  lea     rax, [r11+8]
0x18001780c  jmp     short loc_180017823
0x18001780e  lea     rax, [r11+8]
0x180017812  mov     rcx, [rax]
0x180017815  cmp     [rcx], r11
0x180017818  jnz     short loc_18001781F
0x18001781a  mov     [rcx], rdx
0x18001781d  jmp     short loc_180017823
0x18001781f  mov     [rcx+10h], rdx
0x180017823  mov     rax, [rax]
0x180017826  mov     [rdx+8], rax
0x18001782a  mov     al, [r11+18h]
0x18001782e  mov     cl, [rdx+18h]
0x180017831  mov     [rdx+18h], al
0x180017834  mov     [r11+18h], cl
0x180017838  cmp     byte ptr [r11+18h], 1
0x18001783d  jnz     loc_180017966
0x180017843  mov     rax, [rbx]
0x180017846  cmp     r10, [rax+8]
0x18001784a  jz      loc_180017961
0x180017850  cmp     byte ptr [r10+18h], 1
0x180017855  jnz     loc_180017961
0x18001785b  mov     rdx, [r9]
0x18001785e  cmp     r10, rdx
0x180017861  jnz     short loc_1800178E2
0x180017863  mov     rdx, [r9+10h]
0x180017867  cmp     [rdx+18h], sil
0x18001786b  jnz     short loc_180017884
0x18001786d  mov     byte ptr [rdx+18h], 1
0x180017871  mov     rcx, rbx
0x180017874  mov     rdx, r9
0x180017877  mov     [r9+18h], sil
0x18001787b  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x180017880  mov     rdx, [r9+10h]
0x180017884  cmp     [rdx+19h], sil
0x180017888  jnz     loc_18001791B
0x18001788e  mov     r8, [rdx]
0x180017891  cmp     byte ptr [r8+18h], 1
0x180017896  jnz     short loc_1800178A2
0x180017898  mov     rax, [rdx+10h]
0x18001789c  cmp     byte ptr [rax+18h], 1
0x1800178a0  jz      short loc_180017917
0x1800178a2  mov     rax, [rdx+10h]
0x1800178a6  cmp     byte ptr [rax+18h], 1
0x1800178aa  jnz     short loc_1800178C1
0x1800178ac  mov     byte ptr [r8+18h], 1
0x1800178b1  mov     rcx, rbx
0x1800178b4  mov     [rdx+18h], sil
0x1800178b8  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x1800178bd  mov     rdx, [r9+10h]
0x1800178c1  mov     al, [r9+18h]
0x1800178c5  mov     rcx, rbx
0x1800178c8  mov     [rdx+18h], al
0x1800178cb  mov     byte ptr [r9+18h], 1
0x1800178d0  mov     rax, [rdx+10h]
0x1800178d4  mov     rdx, r9
0x1800178d7  mov     byte ptr [rax+18h], 1
0x1800178db  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x1800178e0  jmp     short loc_180017961
0x1800178e2  cmp     [rdx+18h], sil
0x1800178e6  jnz     short loc_1800178FE
0x1800178e8  mov     byte ptr [rdx+18h], 1
0x1800178ec  mov     rcx, rbx
0x1800178ef  mov     rdx, r9
0x1800178f2  mov     [r9+18h], sil
0x1800178f6  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x1800178fb  mov     rdx, [r9]
0x1800178fe  cmp     [rdx+19h], sil
0x180017902  jnz     short loc_18001791B
0x180017904  mov     rcx, [rdx+10h]
0x180017908  cmp     byte ptr [rcx+18h], 1
0x18001790c  jnz     short loc_180017927
0x18001790e  mov     rax, [rdx]
0x180017911  cmp     byte ptr [rax+18h], 1
0x180017915  jnz     short loc_180017927
0x180017917  mov     [rdx+18h], sil
0x18001791b  mov     r10, r9
0x18001791e  mov     r9, [r9+8]
0x180017922  jmp     loc_180017843
0x180017927  mov     rax, [rdx]
0x18001792a  cmp     byte ptr [rax+18h], 1
0x18001792e  jnz     short loc_180017943
0x180017930  mov     byte ptr [rcx+18h], 1
0x180017934  mov     rcx, rbx
0x180017937  mov     [rdx+18h], sil
0x18001793b  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x180017940  mov     rdx, [r9]
0x180017943  mov     al, [r9+18h]
0x180017947  mov     rcx, rbx
0x18001794a  mov     [rdx+18h], al
0x18001794d  mov     byte ptr [r9+18h], 1
0x180017952  mov     rax, [rdx]
0x180017955  mov     rdx, r9
0x180017958  mov     byte ptr [rax+18h], 1
0x18001795c  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x180017961  mov     byte ptr [r10+18h], 1
0x180017966  mov     rcx, [rbx+8]
0x18001796a  test    rcx, rcx
0x18001796d  jz      short loc_180017976
0x18001796f  dec     rcx
0x180017972  mov     [rbx+8], rcx
0x180017976  mov     rbx, [rsp+28h+arg_0]
0x18001797b  mov     rax, r11
0x18001797e  add     rsp, 20h
0x180017982  pop     rsi
0x180017983  retn
```
