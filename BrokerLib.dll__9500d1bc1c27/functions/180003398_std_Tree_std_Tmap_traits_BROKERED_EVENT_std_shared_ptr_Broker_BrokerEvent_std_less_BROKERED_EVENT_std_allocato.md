# std::_Tree<std::_Tmap_traits<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>,std::less<_BROKERED_EVENT *>,std::allocator<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>>>(std::pair<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>> &&)

- ea: `0x180003398`
- end: `0x1800035ac`
- name: `??$_Emplace@U?$pair@PEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@PEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@U?$less@PEAU_BROKERED_EVENT@@@3@V?$allocator@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@PEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@1@@Z`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004570`

## callees

- `0x180002280`
- `0x180002810`
- `0x180003398`
- `0x180015b14`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003595`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003595`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tmap_traits<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>,std::less<_BROKERED_EVENT *>,std::allocator<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>>>(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 *v6; // r15
  __int64 *v7; // rax
  int v8; // ebp
  __int64 *v9; // rcx
  _QWORD *v10; // rdi
  _QWORD *v11; // rax
  _QWORD *v12; // r10
  _QWORD *v13; // r11
  _QWORD *v14; // r9
  __int64 i; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  __int64 v19; // rax

  v6 = (__int64 *)*a1;
  v7 = *(__int64 **)(*a1 + 8LL);
  v8 = 0;
  v9 = (__int64 *)*a1;
  if ( *((_BYTE *)v7 + 25) )
  {
    v10 = v7;
  }
  else
  {
    do
    {
      v10 = v7;
      if ( (unsigned __int64)v7[4] >= *a3 )
      {
        v8 = 1;
        v9 = v7;
        v7 = (__int64 *)*v7;
      }
      else
      {
        v8 = 0;
        v7 = (__int64 *)v7[2];
      }
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( !*((_BYTE *)v9 + 25) && *a3 >= (unsigned __int64)v9[4] )
  {
    *(_QWORD *)a2 = v9;
    *(_BYTE *)(a2 + 8) = 0;
    return a2;
  }
  if ( a1[1] == 0x492492492492492LL )
    std::_Xlength_error("map/set too long");
  v11 = operator new(0x38u);
  v12 = v11;
  v11[4] = *a3;
  v11[5] = 0;
  v11[6] = 0;
  v11[5] = a3[1];
  v11[6] = a3[2];
  a3[1] = 0;
  a3[2] = 0;
  *v11 = v6;
  v11[1] = v6;
  v11[2] = v6;
  *((_WORD *)v11 + 12) = 0;
  ++a1[1];
  v13 = (_QWORD *)*a1;
  v11[1] = v10;
  if ( v10 != v13 )
  {
    if ( v8 )
    {
      *v10 = v11;
      if ( v10 == (_QWORD *)*v13 )
        *v13 = v11;
    }
    else
    {
      v10[2] = v11;
      if ( v10 == (_QWORD *)v13[2] )
        v13[2] = v11;
    }
    v14 = v11;
    for ( i = v11[1]; ; i = v14[1] )
    {
      if ( *(_BYTE *)(i + 24) )
      {
        v11 = (_QWORD *)v13[1];
        goto LABEL_17;
      }
      v17 = v14[1];
      v18 = *(__int64 **)(v17 + 8);
      v19 = *v18;
      if ( v17 == *v18 )
      {
        v19 = v18[2];
        if ( !*(_BYTE *)(v19 + 24) )
        {
LABEL_21:
          *(_BYTE *)(v17 + 24) = 1;
          *(_BYTE *)(v19 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v14[1] + 8LL) + 24LL) = 0;
          v14 = *(_QWORD **)(v14[1] + 8LL);
          continue;
        }
        if ( v14 == *(_QWORD **)(v17 + 16) )
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
            a1,
            v17);
        *(_BYTE *)(v14[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(v14[1] + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
      }
      else
      {
        if ( !*(_BYTE *)(v19 + 24) )
          goto LABEL_21;
        if ( v14 == *(_QWORD **)v17 )
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
        *(_BYTE *)(v14[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(v14[1] + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
          a1,
          *(_QWORD *)(v14[1] + 8LL));
      }
    }
  }
  *v13 = v11;
  v13[1] = v11;
  v13[2] = v11;
LABEL_17:
  *((_BYTE *)v11 + 24) = 1;
  *(_QWORD *)a2 = v12;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x180003398  push    rbx
0x18000339a  push    rbp
0x18000339b  push    rsi
0x18000339c  push    rdi
0x18000339d  push    r12
0x18000339f  push    r14
0x1800033a1  push    r15
0x1800033a3  sub     rsp, 40h
0x1800033a7  mov     r14, r8
0x1800033aa  mov     rbx, rdx
0x1800033ad  mov     rsi, rcx
0x1800033b0  mov     r15, [rcx]
0x1800033b3  mov     rax, [r15+8]
0x1800033b7  xor     r12d, r12d
0x1800033ba  mov     ebp, r12d
0x1800033bd  xor     ecx, ecx
0x1800033bf  mov     [rsp+78h+var_4C], ecx
0x1800033c3  mov     rcx, r15
0x1800033c6  cmp     [rax+19h], r12b
0x1800033ca  jnz     loc_180003586
0x1800033d0  mov     rdx, [r8]
0x1800033d3  mov     rdi, rax
0x1800033d6  cmp     [rax+20h], rdx
0x1800033da  jnb     short loc_180003404
0x1800033dc  mov     ebp, r12d
0x1800033df  mov     rax, [rax+10h]
0x1800033e3  cmp     [rax+19h], r12b
0x1800033e7  jz      short loc_1800033D3
0x1800033e9  cmp     [rcx+19h], r12b
0x1800033ed  jnz     short loc_180003411
0x1800033ef  mov     rax, [rcx+20h]
0x1800033f3  cmp     [r8], rax
0x1800033f6  jb      short loc_180003411
0x1800033f8  mov     [rbx], rcx
0x1800033fb  mov     [rbx+8], r12b
0x1800033ff  jmp     loc_1800034B5
0x180003404  mov     ebp, 1
0x180003409  mov     rcx, rax
0x18000340c  mov     rax, [rax]
0x18000340f  jmp     short loc_1800033E3
0x180003411  mov     rax, 492492492492492h
0x18000341b  cmp     [rsi+8], rax
0x18000341f  jz      loc_18000358E
0x180003425  mov     [rsp+78h+var_58], rsi
0x18000342a  mov     [rsp+28h], r12
0x18000342f  mov     ecx, 38h ; '8'; Size
0x180003434  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003439  mov     r10, rax
0x18000343c  mov     rcx, [r14]
0x18000343f  mov     [rax+20h], rcx
0x180003443  mov     [rax+28h], r12
0x180003447  mov     [rax+30h], r12
0x18000344b  mov     rcx, [r14+8]
0x18000344f  mov     [rax+28h], rcx
0x180003453  mov     rcx, [r14+10h]
0x180003457  mov     [rax+30h], rcx
0x18000345b  mov     [r14+8], r12
0x18000345f  mov     [r14+10h], r12
0x180003463  mov     [rax], r15
0x180003466  mov     [rax+8], r15
0x18000346a  mov     [rax+10h], r15
0x18000346e  mov     [rax+18h], r12w
0x180003473  inc     qword ptr [rsi+8]
0x180003477  mov     r11, [rsi]
0x18000347a  mov     [rax+8], rdi
0x18000347e  cmp     rdi, r11
0x180003481  jz      loc_18000359C
0x180003487  test    ebp, ebp
0x180003489  jnz     short loc_1800034FF
0x18000348b  mov     [rdi+10h], rax
0x18000348f  cmp     rdi, [r11+10h]
0x180003493  jnz     short loc_180003499
0x180003495  mov     [r11+10h], rax
0x180003499  mov     r9, r10
0x18000349c  mov     rax, [rax+8]
0x1800034a0  cmp     [rax+18h], r12b
0x1800034a4  jz      short loc_1800034C7
0x1800034a6  mov     rax, [r11+8]
0x1800034aa  mov     byte ptr [rax+18h], 1
0x1800034ae  mov     [rbx], r10
0x1800034b1  mov     byte ptr [rbx+8], 1
0x1800034b5  mov     rax, rbx
0x1800034b8  add     rsp, 40h
0x1800034bc  pop     r15
0x1800034be  pop     r14
0x1800034c0  pop     r12
0x1800034c2  pop     rdi
0x1800034c3  pop     rsi
0x1800034c4  pop     rbp
0x1800034c5  pop     rbx
0x1800034c6  retn
0x1800034c7  mov     rdx, [r9+8]
0x1800034cb  mov     rcx, [rdx+8]
0x1800034cf  mov     rax, [rcx]
0x1800034d2  cmp     rdx, rax
0x1800034d5  jz      short loc_180003542
0x1800034d7  cmp     [rax+18h], r12b
0x1800034db  jnz     short loc_18000350C
0x1800034dd  mov     byte ptr [rdx+18h], 1
0x1800034e1  mov     byte ptr [rax+18h], 1
0x1800034e5  mov     rax, [r9+8]
0x1800034e9  mov     rcx, [rax+8]
0x1800034ed  mov     [rcx+18h], r12b
0x1800034f1  mov     rax, [r9+8]
0x1800034f5  mov     r9, [rax+8]
0x1800034f9  mov     rax, [r9+8]
0x1800034fd  jmp     short loc_1800034A0
0x1800034ff  mov     [rdi], r10
0x180003502  cmp     rdi, [r11]
0x180003505  jnz     short loc_180003499
0x180003507  mov     [r11], r10
0x18000350a  jmp     short loc_180003499
0x18000350c  cmp     r9, [rdx]
0x18000350f  jnz     short loc_18000351C
0x180003511  mov     r9, rdx
0x180003514  mov     rcx, rsi
0x180003517  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000351c  mov     rax, [r9+8]
0x180003520  mov     byte ptr [rax+18h], 1
0x180003524  mov     rax, [r9+8]
0x180003528  mov     rcx, [rax+8]
0x18000352c  mov     [rcx+18h], r12b
0x180003530  mov     rdx, [r9+8]
0x180003534  mov     rdx, [rdx+8]
0x180003538  mov     rcx, rsi
0x18000353b  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180003540  jmp     short loc_1800034F9
0x180003542  mov     rax, [rcx+10h]
0x180003546  cmp     [rax+18h], r12b
0x18000354a  jz      short loc_1800034DD
0x18000354c  cmp     r9, [rdx+10h]
0x180003550  jnz     short loc_18000355D
0x180003552  mov     r9, rdx
0x180003555  mov     rcx, rsi
0x180003558  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000355d  mov     rax, [r9+8]
0x180003561  mov     byte ptr [rax+18h], 1
0x180003565  mov     rax, [r9+8]
0x180003569  mov     rcx, [rax+8]
0x18000356d  mov     [rcx+18h], r12b
0x180003571  mov     rdx, [r9+8]
0x180003575  mov     rdx, [rdx+8]
0x180003579  mov     rcx, rsi
0x18000357c  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180003581  jmp     loc_1800034F9
0x180003586  mov     rdi, rax
0x180003589  jmp     loc_1800033E9
0x18000358e  lea     rcx, aMapSetTooLong; "map/set too long"
0x180003595  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000359c  mov     [r11], r10
0x18000359f  mov     [r11+8], r10
0x1800035a3  mov     [r11+10h], r10
0x1800035a7  jmp     loc_1800034AA
```
