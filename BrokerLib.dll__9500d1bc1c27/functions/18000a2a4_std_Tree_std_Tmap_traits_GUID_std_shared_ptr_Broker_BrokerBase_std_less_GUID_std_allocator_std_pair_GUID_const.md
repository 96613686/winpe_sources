# std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::_Emplace<std::pair<_GUID,std::shared_ptr<Broker::BrokerBase>>>(std::pair<_GUID,std::shared_ptr<Broker::BrokerBase>> &&)

- ea: `0x18000a2a4`
- end: `0x18000a399`
- name: `??$_Emplace@U?$pair@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@1@@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018004`

## callees

- `0x180004ae0`
- `0x180004e38`
- `0x18000a2a4`
- `0x18000a694`
- `0x18000a7e0`
- `0x18000a870`
- `0x18000a930`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a303`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a303`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::_Emplace<std::pair<_GUID,std::shared_ptr<Broker::BrokerBase>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 lower; // rax
  __int64 v6; // rdi
  __int128 v7; // xmm6
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rcx
  _BYTE v13[8]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v14; // [rsp+28h] [rbp-40h]
  _OWORD v15[2]; // [rsp+30h] [rbp-38h] BYREF

  lower = std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::_Find_lower_bound<_GUID>(
            a1,
            v15);
  v6 = *(_QWORD *)(lower + 16);
  v7 = *(_OWORD *)lower;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::_Lower_bound_duplicate<_GUID>(
                          v8,
                          v6,
                          a3) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( qword_180028988 == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("map/set too long");
    v9 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>>>(
           v13,
           &Broker::g_Brokers,
           Broker::g_Brokers,
           a3);
    v10 = *(_QWORD *)(v9 + 8);
    *(_QWORD *)(v9 + 8) = 0;
    v11 = v14;
    if ( v14 )
    {
      if ( *(_QWORD *)(v14 + 56) )
      {
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(v14 + 56));
        v11 = v14;
      }
      if ( v11 )
        std::_Deallocate<16>(v11, 64);
    }
    v15[0] = v7;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>>::_Insert_node(
                      &Broker::g_Brokers,
                      v15,
                      v10);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x18000a2a4  mov     rax, rsp
0x18000a2a7  mov     [rax+8], rbx
0x18000a2ab  mov     [rax+10h], rsi
0x18000a2af  push    rdi
0x18000a2b0  sub     rsp, 60h
0x18000a2b4  mov     rbx, rdx
0x18000a2b7  movaps  xmmword ptr [rax-18h], xmm6
0x18000a2bb  lea     rdx, [rax-38h]
0x18000a2bf  mov     rsi, r8
0x18000a2c2  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18000a2c7  mov     r8, rsi
0x18000a2ca  mov     rdi, [rax+10h]
0x18000a2ce  movups  xmm6, xmmword ptr [rax]
0x18000a2d1  mov     rdx, rdi
0x18000a2d4  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerBase>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *> * const,_GUID const &)
0x18000a2d9  test    al, al
0x18000a2db  jz      short loc_18000A2E9
0x18000a2dd  mov     [rbx], rdi
0x18000a2e0  mov     byte ptr [rbx+8], 0
0x18000a2e4  jmp     loc_18000A381
0x18000a2e9  mov     rax, 3FFFFFFFFFFFFFFh
0x18000a2f3  cmp     cs:qword_180028988, rax
0x18000a2fa  jnz     short loc_18000A30A
0x18000a2fc  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000a303  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a30a  mov     r8, cs:?g_Brokers@Broker@@3V?$map@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@@std@@A; std::map<_GUID,std::shared_ptr<Broker::BrokerBase>> Broker::g_Brokers
0x18000a311  lea     rdx, ?g_Brokers@Broker@@3V?$map@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@@std@@A; std::map<_GUID,std::shared_ptr<Broker::BrokerBase>> Broker::g_Brokers
0x18000a318  mov     r9, rsi
0x18000a31b  lea     rcx, [rsp+68h+var_48]
0x18000a320  call    ??$?0U?$pair@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@1@$$QEAU?$pair@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *>> &,std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *> *,std::pair<_GUID,std::shared_ptr<Broker::BrokerBase>> &&)
0x18000a325  mov     rdi, [rax+8]
0x18000a329  mov     qword ptr [rax+8], 0
0x18000a331  mov     rcx, [rsp+68h+var_40]
0x18000a336  test    rcx, rcx
0x18000a339  jz      short loc_18000A360
0x18000a33b  mov     rax, [rcx+38h]
0x18000a33f  test    rax, rax
0x18000a342  jz      short loc_18000A351
0x18000a344  mov     rcx, rax; this
0x18000a347  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a34c  mov     rcx, [rsp+68h+var_40]
0x18000a351  test    rcx, rcx
0x18000a354  jz      short loc_18000A360
0x18000a356  mov     edx, 40h ; '@'
0x18000a35b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a360  mov     r8, rdi
0x18000a363  lea     rdx, [rsp+68h+var_38]
0x18000a368  lea     rcx, ?g_Brokers@Broker@@3V?$map@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@@std@@A; std::map<_GUID,std::shared_ptr<Broker::BrokerBase>> Broker::g_Brokers
0x18000a36f  movdqu  [rsp+68h+var_38], xmm6
0x18000a375  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *> *>,std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerBase>>,void *> * const)
0x18000a37a  mov     [rbx], rax
0x18000a37d  mov     byte ptr [rbx+8], 1
0x18000a381  mov     rsi, [rsp+68h+arg_8]
0x18000a386  mov     rax, rbx
0x18000a389  mov     rbx, [rsp+68h+arg_0]
0x18000a38e  movaps  xmm6, [rsp+68h+var_18]
0x18000a393  add     rsp, 60h
0x18000a397  pop     rdi
0x18000a398  retn
```
