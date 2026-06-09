# std::_Tree<std::_Tmap_traits<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>,std::less<_CBROKERED_EVENT_ID>,std::allocator<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>>>(std::pair<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>> &&)

- ea: `0x180003148`
- end: `0x180003390`
- name: `??$_Emplace@U?$pair@U_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@U?$less@U_CBROKERED_EVENT_ID@@@3@V?$allocator@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@1@@Z`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004570`

## callees

- `0x180002280`
- `0x1800022d8`
- `0x180003148`
- `0x180015b14`
- `0x18001659e`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003379`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003379`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tmap_traits<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>,std::less<_CBROKERED_EVENT_ID>,std::allocator<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>>>(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 *v6; // r13
  __int64 *v7; // rbx
  int v8; // r15d
  __int64 *v9; // rbp
  _QWORD *v10; // rsi
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
    v10 = *(_QWORD **)(*a1 + 8LL);
  }
  else
  {
    do
    {
      v10 = v7;
      if ( memcmp_0(v7 + 4, a3, 8u) < 0 )
      {
        v8 = 0;
        v7 = (__int64 *)v7[2];
      }
      else
      {
        v8 = 1;
        v9 = v7;
        v7 = (__int64 *)*v7;
      }
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( *((_BYTE *)v9 + 25) || memcmp_0(a3, v9 + 4, 8u) < 0 )
  {
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
          goto LABEL_15;
        }
        v17 = v14[1];
        v18 = *(__int64 **)(v17 + 8);
        v19 = *v18;
        if ( v17 == *v18 )
        {
          v19 = v18[2];
          if ( !*(_BYTE *)(v19 + 24) )
          {
LABEL_20:
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
          std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
        }
        else
        {
          if ( !*(_BYTE *)(v19 + 24) )
            goto LABEL_20;
          if ( v14 == *(_QWORD **)v17 )
            std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(a1);
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
LABEL_15:
    *((_BYTE *)v11 + 24) = 1;
    *(_QWORD *)a2 = v12;
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v9;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180003148  push    rbx
0x18000314a  push    rbp
0x18000314b  push    rsi
0x18000314c  push    rdi
0x18000314d  push    r12
0x18000314f  push    r13
0x180003151  push    r14
0x180003153  push    r15
0x180003155  sub     rsp, 48h
0x180003159  mov     r12, r8
0x18000315c  mov     rdi, rdx
0x18000315f  mov     r14, rcx
0x180003162  mov     r13, [rcx]
0x180003165  mov     rbx, [r13+8]
0x180003169  xor     r15d, r15d
0x18000316c  xor     eax, eax
0x18000316e  mov     [rsp+88h+var_5C], eax
0x180003172  mov     rbp, r13
0x180003175  cmp     [rbx+19h], al
0x180003178  jnz     loc_180003362
0x18000317e  mov     rsi, rbx
0x180003181  lea     rcx, [rbx+20h]; Buf1
0x180003185  mov     r8d, 8; Size
0x18000318b  mov     rdx, r12; Buf2
0x18000318e  call    memcmp_0
0x180003193  test    eax, eax
0x180003195  js      loc_18000328A
0x18000319b  mov     r15d, 1
0x1800031a1  mov     rbp, rbx
0x1800031a4  mov     rbx, [rbx]
0x1800031a7  cmp     byte ptr [rbx+19h], 0
0x1800031ab  jz      short loc_18000317E
0x1800031ad  xor     ebx, ebx
0x1800031af  cmp     [rbp+19h], bl
0x1800031b2  jnz     short loc_1800031CC
0x1800031b4  lea     rdx, [rbp+20h]; Buf2
0x1800031b8  lea     r8d, [rbx+8]; Size
0x1800031bc  mov     rcx, r12; Buf1
0x1800031bf  call    memcmp_0
0x1800031c4  test    eax, eax
0x1800031c6  jns     loc_1800032CC
0x1800031cc  mov     rax, 492492492492492h
0x1800031d6  cmp     [r14+8], rax
0x1800031da  jz      loc_180003372
0x1800031e0  mov     [rsp+88h+var_68], r14
0x1800031e5  mov     [rsp+28h], rbx
0x1800031ea  mov     ecx, 38h ; '8'; Size
0x1800031ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800031f4  mov     r10, rax
0x1800031f7  mov     rcx, [r12]
0x1800031fb  mov     [rax+20h], rcx
0x1800031ff  mov     [rax+28h], rbx
0x180003203  mov     [rax+30h], rbx
0x180003207  mov     rcx, [r12+8]
0x18000320c  mov     [rax+28h], rcx
0x180003210  mov     rcx, [r12+10h]
0x180003215  mov     [rax+30h], rcx
0x180003219  mov     [r12+8], rbx
0x18000321e  mov     [r12+10h], rbx
0x180003223  mov     [rax], r13
0x180003226  mov     [rax+8], r13
0x18000322a  mov     [rax+10h], r13
0x18000322e  mov     [rax+18h], bx
0x180003232  inc     qword ptr [r14+8]
0x180003236  mov     r11, [r14]
0x180003239  mov     [rax+8], rsi
0x18000323d  cmp     rsi, r11
0x180003240  jz      loc_180003380
0x180003246  test    r15d, r15d
0x180003249  jz      loc_1800032D4
0x18000324f  mov     [rsi], rax
0x180003252  cmp     rsi, [r11]
0x180003255  jz      loc_18000336A
0x18000325b  mov     r9, r10
0x18000325e  mov     rax, [rax+8]
0x180003262  cmp     [rax+18h], bl
0x180003265  jz      short loc_180003296
0x180003267  mov     rax, [r11+8]
0x18000326b  mov     byte ptr [rax+18h], 1
0x18000326f  mov     [rdi], r10
0x180003272  mov     byte ptr [rdi+8], 1
0x180003276  mov     rax, rdi
0x180003279  add     rsp, 48h
0x18000327d  pop     r15
0x18000327f  pop     r14
0x180003281  pop     r13
0x180003283  pop     r12
0x180003285  pop     rdi
0x180003286  pop     rsi
0x180003287  pop     rbp
0x180003288  pop     rbx
0x180003289  retn
0x18000328a  xor     r15d, r15d
0x18000328d  mov     rbx, [rbx+10h]
0x180003291  jmp     loc_1800031A7
0x180003296  mov     rdx, [r9+8]
0x18000329a  mov     rcx, [rdx+8]
0x18000329e  mov     rax, [rcx]
0x1800032a1  cmp     rdx, rax
0x1800032a4  jz      short loc_1800032EB
0x1800032a6  cmp     [rax+18h], bl
0x1800032a9  jnz     short loc_18000332A
0x1800032ab  mov     byte ptr [rdx+18h], 1
0x1800032af  mov     byte ptr [rax+18h], 1
0x1800032b3  mov     rax, [r9+8]
0x1800032b7  mov     rcx, [rax+8]
0x1800032bb  mov     [rcx+18h], bl
0x1800032be  mov     rax, [r9+8]
0x1800032c2  mov     r9, [rax+8]
0x1800032c6  mov     rax, [r9+8]
0x1800032ca  jmp     short loc_180003262
0x1800032cc  mov     [rdi], rbp
0x1800032cf  mov     [rdi+8], bl
0x1800032d2  jmp     short loc_180003276
0x1800032d4  mov     [rsi+10h], r10
0x1800032d8  cmp     rsi, [r11+10h]
0x1800032dc  jnz     loc_18000325B
0x1800032e2  mov     [r11+10h], r10
0x1800032e6  jmp     loc_18000325B
0x1800032eb  mov     rax, [rcx+10h]
0x1800032ef  cmp     [rax+18h], bl
0x1800032f2  jz      short loc_1800032AB
0x1800032f4  cmp     r9, [rdx+10h]
0x1800032f8  jnz     short loc_180003305
0x1800032fa  mov     r9, rdx
0x1800032fd  mov     rcx, r14
0x180003300  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180003305  mov     rax, [r9+8]
0x180003309  mov     byte ptr [rax+18h], 1
0x18000330d  mov     rax, [r9+8]
0x180003311  mov     rcx, [rax+8]
0x180003315  mov     [rcx+18h], bl
0x180003318  mov     rdx, [r9+8]
0x18000331c  mov     rdx, [rdx+8]
0x180003320  mov     rcx, r14
0x180003323  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x180003328  jmp     short loc_1800032C6
0x18000332a  cmp     r9, [rdx]
0x18000332d  jnz     short loc_18000333A
0x18000332f  mov     r9, rdx
0x180003332  mov     rcx, r14
0x180003335  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Rrotate(std::_Tree_node<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000333a  mov     rax, [r9+8]
0x18000333e  mov     byte ptr [rax+18h], 1
0x180003342  mov     rax, [r9+8]
0x180003346  mov     rcx, [rax+8]
0x18000334a  mov     [rcx+18h], bl
0x18000334d  mov     rdx, [r9+8]
0x180003351  mov     rdx, [rdx+8]
0x180003355  mov     rcx, r14
0x180003358  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)
0x18000335d  jmp     loc_1800032C6
0x180003362  mov     rsi, rbx
0x180003365  jmp     loc_1800031AD
0x18000336a  mov     [r11], r10
0x18000336d  jmp     loc_18000325B
0x180003372  lea     rcx, aMapSetTooLong; "map/set too long"
0x180003379  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180003380  mov     [r11], r10
0x180003383  mov     [r11+8], r10
0x180003387  mov     [r11+10h], r10
0x18000338b  jmp     loc_18000326B
```
