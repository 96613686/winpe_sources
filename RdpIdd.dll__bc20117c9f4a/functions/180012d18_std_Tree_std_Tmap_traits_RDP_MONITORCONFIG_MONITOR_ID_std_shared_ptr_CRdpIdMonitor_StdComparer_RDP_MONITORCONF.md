# std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Emplace<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>> &>(std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>> &)

- ea: `0x180012d18`
- end: `0x180012db8`
- name: `??$_Emplace@AEAU?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@_N@1@AEAU?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@1@@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fd78`

## callees

- `0x180012114`
- `0x180012d18`
- `0x1800130bc`
- `0x18001325c`
- `0x180014ab8`
- `0x180020560`
- `0x180020b5c`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Emplace<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>> &>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 lower; // rax
  __int64 v7; // rbx
  __int128 v8; // xmm6
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rbx
  _BYTE v13[16]; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v14[2]; // [rsp+30h] [rbp-58h] BYREF

  lower = std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Find_lower_bound<RDP_MONITORCONFIG_MONITOR_ID>(
            a1,
            v14);
  v7 = *(_QWORD *)(lower + 16);
  v8 = *(_OWORD *)lower;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Lower_bound_duplicate<RDP_MONITORCONFIG_MONITOR_ID>(
                          v9,
                          v7,
                          a3) )
  {
    *(_QWORD *)a2 = v7;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Check_grow_by_1(a1);
    v10 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(
            v13,
            a1,
            *a1,
            a3);
    v11 = *(_QWORD *)(v10 + 8);
    *(_QWORD *)(v10 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(v13);
    v14[0] = v8;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Insert_node(
                      a1,
                      v14,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x180012d18  push    rbx
0x180012d1a  push    rbp
0x180012d1b  push    rsi
0x180012d1c  push    rdi
0x180012d1d  sub     rsp, 68h
0x180012d21  mov     rdi, rdx
0x180012d24  movaps  [rsp+88h+var_38], xmm6
0x180012d29  lea     rdx, [rsp+88h+var_58]
0x180012d2e  mov     rbp, r8
0x180012d31  mov     rsi, rcx
0x180012d34  call    ??$_Find_lower_bound@URDP_MONITORCONFIG_MONITOR_ID@@@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@1@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Find_lower_bound<RDP_MONITORCONFIG_MONITOR_ID>(RDP_MONITORCONFIG_MONITOR_ID const &)
0x180012d39  mov     r8, rbp
0x180012d3c  mov     rbx, [rax+10h]
0x180012d40  movups  xmm6, xmmword ptr [rax]
0x180012d43  mov     rdx, rbx
0x180012d46  call    ??$_Lower_bound_duplicate@URDP_MONITORCONFIG_MONITOR_ID@@@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@1@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Lower_bound_duplicate<RDP_MONITORCONFIG_MONITOR_ID>(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> * const,RDP_MONITORCONFIG_MONITOR_ID const &)
0x180012d4b  test    al, al
0x180012d4d  jz      short loc_180012D58
0x180012d4f  mov     [rdi], rbx
0x180012d52  mov     byte ptr [rdi+8], 0
0x180012d56  jmp     short loc_180012DA6
0x180012d58  mov     rcx, rsi
0x180012d5b  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Check_grow_by_1(void)
0x180012d60  mov     r8, [rsi]
0x180012d63  lea     rcx, [rsp+88h+var_68]
0x180012d68  mov     r9, rbp
0x180012d6b  mov     rdx, rsi
0x180012d6e  call    ??$?0AEAU?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@1@AEAU?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>> &,std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *,std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>> &)
0x180012d73  lea     rcx, [rsp+88h+var_68]
0x180012d78  mov     rbx, [rax+8]
0x180012d7c  mov     qword ptr [rax+8], 0
0x180012d84  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(void)
0x180012d89  mov     r8, rbx
0x180012d8c  lea     rdx, [rsp+88h+var_58]
0x180012d91  mov     rcx, rsi
0x180012d94  movdqu  [rsp+88h+var_58], xmm6
0x180012d9a  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *>,std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> * const)
0x180012d9f  mov     [rdi], rax
0x180012da2  mov     byte ptr [rdi+8], 1
0x180012da6  movaps  xmm6, [rsp+88h+var_38]
0x180012dab  mov     rax, rdi
0x180012dae  add     rsp, 68h
0x180012db2  pop     rdi
0x180012db3  pop     rsi
0x180012db4  pop     rbp
0x180012db5  pop     rbx
0x180012db6  retn
```
