# std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Try_emplace<RDP_MONITORCONFIG_MONITOR_ID const &,>(RDP_MONITORCONFIG_MONITOR_ID const &)

- ea: `0x1800136b8`
- end: `0x180013763`
- name: `??$_Try_emplace@AEBURDP_MONITORCONFIG_MONITOR_ID@@$$V@?$map@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@_N@1@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001556c`

## callees

- `0x1800121f8`
- `0x1800130bc`
- `0x18001325c`
- `0x1800136b8`
- `0x180014ab8`
- `0x180020560`
- `0x180020b5c`

## pseudocode

```c
__int64 __fastcall std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Try_emplace<RDP_MONITORCONFIG_MONITOR_ID const &,>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // r9d
  __int64 v10; // rax
  __int64 v11; // rbx
  _BYTE v13[16]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v14; // [rsp+40h] [rbp-48h] BYREF
  __int64 v15; // [rsp+50h] [rbp-38h]
  __int64 v16; // [rsp+A8h] [rbp+20h] BYREF

  std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Find_lower_bound<RDP_MONITORCONFIG_MONITOR_ID>(
    a1,
    &v14);
  v6 = v15;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Lower_bound_duplicate<RDP_MONITORCONFIG_MONITOR_ID>(
                          v7,
                          v15,
                          a3) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Check_grow_by_1(a1);
    v8 = *a1;
    v16 = a3;
    v10 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(
            (unsigned int)v13,
            (_DWORD)a1,
            v8,
            v9,
            (__int64)&v16);
    v11 = *(_QWORD *)(v10 + 8);
    *(_QWORD *)(v10 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(v13);
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Insert_node(
                      a1,
                      &v14,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x1800136b8  push    rbx
0x1800136ba  push    rbp
0x1800136bb  push    rsi
0x1800136bc  push    rdi
0x1800136bd  sub     rsp, 68h
0x1800136c1  mov     rdi, rdx
0x1800136c4  mov     rbp, r8
0x1800136c7  lea     rdx, [rsp+88h+var_48]
0x1800136cc  mov     rsi, rcx
0x1800136cf  call    ??$_Find_lower_bound@URDP_MONITORCONFIG_MONITOR_ID@@@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@1@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Find_lower_bound<RDP_MONITORCONFIG_MONITOR_ID>(RDP_MONITORCONFIG_MONITOR_ID const &)
0x1800136d4  mov     rbx, [rsp+88h+var_38]
0x1800136d9  mov     r8, rbp
0x1800136dc  mov     rdx, rbx
0x1800136df  call    ??$_Lower_bound_duplicate@URDP_MONITORCONFIG_MONITOR_ID@@@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@1@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Lower_bound_duplicate<RDP_MONITORCONFIG_MONITOR_ID>(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> * const,RDP_MONITORCONFIG_MONITOR_ID const &)
0x1800136e4  test    al, al
0x1800136e6  jz      short loc_1800136F1
0x1800136e8  mov     [rdi], rbx
0x1800136eb  mov     byte ptr [rdi+8], 0
0x1800136ef  jmp     short loc_180013756
0x1800136f1  mov     rcx, rsi
0x1800136f4  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Check_grow_by_1(void)
0x1800136f9  mov     r8, [rsi]
0x1800136fc  lea     rax, [rsp+88h+arg_18]
0x180013704  mov     rdx, rsi
0x180013707  mov     [rsp+88h+var_68], rax
0x18001370c  lea     rcx, [rsp+88h+var_58]
0x180013711  mov     [rsp+88h+arg_18], rbp
0x180013719  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBURDP_MONITORCONFIG_MONITOR_ID@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBURDP_MONITORCONFIG_MONITOR_ID@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>> &,std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *,std::piecewise_construct_t const &,std::tuple<RDP_MONITORCONFIG_MONITOR_ID const &> &&,std::tuple<> &&)
0x18001371e  lea     rcx, [rsp+88h+var_58]
0x180013723  mov     rbx, [rax+8]
0x180013727  mov     qword ptr [rax+8], 0
0x18001372f  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(void)
0x180013734  movups  xmm0, [rsp+88h+var_48]
0x180013739  mov     r8, rbx
0x18001373c  lea     rdx, [rsp+88h+var_48]
0x180013741  mov     rcx, rsi
0x180013744  movdqu  [rsp+88h+var_48], xmm0
0x18001374a  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *>,std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> * const)
0x18001374f  mov     [rdi], rax
0x180013752  mov     byte ptr [rdi+8], 1
0x180013756  mov     rax, rdi
0x180013759  add     rsp, 68h
0x18001375d  pop     rdi
0x18001375e  pop     rsi
0x18001375f  pop     rbp
0x180013760  pop     rbx
0x180013761  retn
```
