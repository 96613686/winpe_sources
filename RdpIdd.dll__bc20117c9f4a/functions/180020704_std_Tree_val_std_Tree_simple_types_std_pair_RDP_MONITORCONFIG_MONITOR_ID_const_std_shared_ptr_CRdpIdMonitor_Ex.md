# std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>)

- ea: `0x180020704`
- end: `0x180020989`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180015a88`

## callees

- `0x18001534c`
- `0x180020704`
- `0x180020c8c`
- `0x180020cdc`
- `0x180020d20`

## pseudocode

```c
__int64 *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Extract(
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
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(&v18);
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
        v8 = std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Min(
               v5,
               v3,
               v7,
               v6);
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
        std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Lrotate(a1);
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
            std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Rrotate(
              a1,
              v14);
            v14 = *(_QWORD *)(v6 + 16);
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Lrotate(a1);
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
        std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Rrotate(
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
            std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Lrotate(a1);
            v14 = *(_QWORD *)v6;
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Rrotate(
            a1,
            v6);
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
0x180020704  mov     [rsp+arg_0], rbx
0x180020709  mov     [rsp+arg_8], rdx
0x18002070e  push    rsi
0x18002070f  sub     rsp, 20h
0x180020713  mov     rbx, rcx
0x180020716  mov     r11, rdx
0x180020719  lea     rcx, [rsp+28h+arg_8]
0x18002071e  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(void)
0x180020723  mov     r9, [r11]
0x180020726  xor     esi, esi
0x180020728  mov     r10, [r11+10h]
0x18002072c  cmp     [r9+19h], sil
0x180020730  jnz     short loc_18002074B
0x180020732  cmp     [r10+19h], sil
0x180020736  jz      short loc_18002073D
0x180020738  mov     r10, r9
0x18002073b  jmp     short loc_18002074B
0x18002073d  mov     rdx, [rsp+28h+arg_8]
0x180020742  mov     r10, [rdx+10h]
0x180020746  cmp     rdx, r11
0x180020749  jnz     short loc_1800207C9
0x18002074b  mov     r9, [r11+8]
0x18002074f  cmp     [r10+19h], sil
0x180020753  jnz     short loc_180020759
0x180020755  mov     [r10+8], r9
0x180020759  mov     rax, [rbx]
0x18002075c  cmp     [rax+8], r11
0x180020760  jnz     short loc_180020768
0x180020762  mov     [rax+8], r10
0x180020766  jmp     short loc_180020776
0x180020768  cmp     [r9], r11
0x18002076b  jnz     short loc_180020772
0x18002076d  mov     [r9], r10
0x180020770  jmp     short loc_180020776
0x180020772  mov     [r9+10h], r10
0x180020776  mov     r8, [rbx]
0x180020779  cmp     [r8], r11
0x18002077c  jnz     short loc_180020794
0x18002077e  cmp     [r10+19h], sil
0x180020782  jz      short loc_180020789
0x180020784  mov     rax, r9
0x180020787  jmp     short loc_180020791
0x180020789  mov     rcx, r10
0x18002078c  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Min(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x180020791  mov     [r8], rax
0x180020794  mov     rdx, [rbx]
0x180020797  cmp     [rdx+10h], r11
0x18002079b  jnz     loc_18002083C
0x1800207a1  cmp     [r10+19h], sil
0x1800207a5  jz      short loc_1800207AC
0x1800207a7  mov     rcx, r9
0x1800207aa  jmp     short loc_1800207C3
0x1800207ac  mov     rax, [r10+10h]
0x1800207b0  mov     rcx, r10
0x1800207b3  jmp     short loc_1800207BD
0x1800207b5  mov     rcx, [rcx+10h]
0x1800207b9  mov     rax, [rcx+10h]
0x1800207bd  cmp     [rax+19h], sil
0x1800207c1  jz      short loc_1800207B5
0x1800207c3  mov     [rdx+10h], rcx
0x1800207c7  jmp     short loc_18002083C
0x1800207c9  mov     [r9+8], rdx
0x1800207cd  mov     rax, [r11]
0x1800207d0  mov     [rdx], rax
0x1800207d3  cmp     rdx, [r11+10h]
0x1800207d7  jnz     short loc_1800207DE
0x1800207d9  mov     r9, rdx
0x1800207dc  jmp     short loc_1800207FF
0x1800207de  mov     r9, [rdx+8]
0x1800207e2  cmp     [r10+19h], sil
0x1800207e6  jnz     short loc_1800207EC
0x1800207e8  mov     [r10+8], r9
0x1800207ec  mov     [r9], r10
0x1800207ef  mov     rax, [r11+10h]
0x1800207f3  mov     [rdx+10h], rax
0x1800207f7  mov     rax, [r11+10h]
0x1800207fb  mov     [rax+8], rdx
0x1800207ff  mov     rax, [rbx]
0x180020802  cmp     [rax+8], r11
0x180020806  jnz     short loc_180020812
0x180020808  mov     [rax+8], rdx
0x18002080c  lea     rax, [r11+8]
0x180020810  jmp     short loc_180020827
0x180020812  lea     rax, [r11+8]
0x180020816  mov     rcx, [rax]
0x180020819  cmp     [rcx], r11
0x18002081c  jnz     short loc_180020823
0x18002081e  mov     [rcx], rdx
0x180020821  jmp     short loc_180020827
0x180020823  mov     [rcx+10h], rdx
0x180020827  mov     rax, [rax]
0x18002082a  mov     [rdx+8], rax
0x18002082e  mov     al, [r11+18h]
0x180020832  mov     cl, [rdx+18h]
0x180020835  mov     [rdx+18h], al
0x180020838  mov     [r11+18h], cl
0x18002083c  cmp     byte ptr [r11+18h], 1
0x180020841  jnz     loc_18002096A
0x180020847  mov     rax, [rbx]
0x18002084a  cmp     r10, [rax+8]
0x18002084e  jz      loc_180020965
0x180020854  cmp     byte ptr [r10+18h], 1
0x180020859  jnz     loc_180020965
0x18002085f  mov     rdx, [r9]
0x180020862  cmp     r10, rdx
0x180020865  jnz     short loc_1800208E6
0x180020867  mov     rdx, [r9+10h]
0x18002086b  cmp     [rdx+18h], sil
0x18002086f  jnz     short loc_180020888
0x180020871  mov     byte ptr [rdx+18h], 1
0x180020875  mov     rcx, rbx
0x180020878  mov     rdx, r9
0x18002087b  mov     [r9+18h], sil
0x18002087f  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Lrotate(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x180020884  mov     rdx, [r9+10h]
0x180020888  cmp     [rdx+19h], sil
0x18002088c  jnz     loc_18002091F
0x180020892  mov     r8, [rdx]
0x180020895  cmp     byte ptr [r8+18h], 1
0x18002089a  jnz     short loc_1800208A6
0x18002089c  mov     rax, [rdx+10h]
0x1800208a0  cmp     byte ptr [rax+18h], 1
0x1800208a4  jz      short loc_18002091B
0x1800208a6  mov     rax, [rdx+10h]
0x1800208aa  cmp     byte ptr [rax+18h], 1
0x1800208ae  jnz     short loc_1800208C5
0x1800208b0  mov     byte ptr [r8+18h], 1
0x1800208b5  mov     rcx, rbx
0x1800208b8  mov     [rdx+18h], sil
0x1800208bc  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Rrotate(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x1800208c1  mov     rdx, [r9+10h]
0x1800208c5  mov     al, [r9+18h]
0x1800208c9  mov     rcx, rbx
0x1800208cc  mov     [rdx+18h], al
0x1800208cf  mov     byte ptr [r9+18h], 1
0x1800208d4  mov     rax, [rdx+10h]
0x1800208d8  mov     rdx, r9
0x1800208db  mov     byte ptr [rax+18h], 1
0x1800208df  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Lrotate(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x1800208e4  jmp     short loc_180020965
0x1800208e6  cmp     [rdx+18h], sil
0x1800208ea  jnz     short loc_180020902
0x1800208ec  mov     byte ptr [rdx+18h], 1
0x1800208f0  mov     rcx, rbx
0x1800208f3  mov     rdx, r9
0x1800208f6  mov     [r9+18h], sil
0x1800208fa  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Rrotate(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x1800208ff  mov     rdx, [r9]
0x180020902  cmp     [rdx+19h], sil
0x180020906  jnz     short loc_18002091F
0x180020908  mov     rcx, [rdx+10h]
0x18002090c  cmp     byte ptr [rcx+18h], 1
0x180020910  jnz     short loc_18002092B
0x180020912  mov     rax, [rdx]
0x180020915  cmp     byte ptr [rax+18h], 1
0x180020919  jnz     short loc_18002092B
0x18002091b  mov     [rdx+18h], sil
0x18002091f  mov     r10, r9
0x180020922  mov     r9, [r9+8]
0x180020926  jmp     loc_180020847
0x18002092b  mov     rax, [rdx]
0x18002092e  cmp     byte ptr [rax+18h], 1
0x180020932  jnz     short loc_180020947
0x180020934  mov     byte ptr [rcx+18h], 1
0x180020938  mov     rcx, rbx
0x18002093b  mov     [rdx+18h], sil
0x18002093f  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Lrotate(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x180020944  mov     rdx, [r9]
0x180020947  mov     al, [r9+18h]
0x18002094b  mov     rcx, rbx
0x18002094e  mov     [rdx+18h], al
0x180020951  mov     byte ptr [r9+18h], 1
0x180020956  mov     rax, [rdx]
0x180020959  mov     rdx, r9
0x18002095c  mov     byte ptr [rax+18h], 1
0x180020960  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Rrotate(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x180020965  mov     byte ptr [r10+18h], 1
0x18002096a  mov     rcx, [rbx+8]
0x18002096e  test    rcx, rcx
0x180020971  jz      short loc_18002097A
0x180020973  dec     rcx
0x180020976  mov     [rbx+8], rcx
0x18002097a  mov     rbx, [rsp+28h+arg_0]
0x18002097f  mov     rax, r11
0x180020982  add     rsp, 20h
0x180020986  pop     rsi
0x180020987  retn
```
