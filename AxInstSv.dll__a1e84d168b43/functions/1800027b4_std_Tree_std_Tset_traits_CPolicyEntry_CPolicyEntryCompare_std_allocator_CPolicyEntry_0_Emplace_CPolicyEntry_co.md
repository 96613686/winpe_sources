# std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Emplace<CPolicyEntry * const &>(CPolicyEntry * const &)

- ea: `0x1800027b4`
- end: `0x180002892`
- name: `??$_Emplace@AEBQEAVCPolicyEntry@@@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@std@@_N@1@AEBQEAVCPolicyEntry@@@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002e78`

## callees

- `0x18000177c`
- `0x1800027b4`
- `0x1800028f4`
- `0x180002978`
- `0x180002b14`
- `0x180004d88`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180002811`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180002811`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Emplace<CPolicyEntry * const &>(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 lower; // rax
  __int128 v7; // xmm6
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rbx
  _QWORD *v11; // rdi
  _OWORD v13[2]; // [rsp+20h] [rbp-58h] BYREF

  lower = std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Find_lower_bound<CPolicyEntry *>(
            a1,
            v13,
            a3);
  v7 = *(_OWORD *)lower;
  v8 = *(_QWORD *)(lower + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Lower_bound_duplicate<CPolicyEntry *>(
                          v9,
                          v8,
                          a3) )
  {
    *(_QWORD *)a2 = v8;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x666666666666666LL )
      std::_Xlength_error("map/set too long");
    v10 = *a1;
    v13[0] = (unsigned __int64)a1;
    v11 = operator new(0x28u);
    v11[4] = *a3;
    *v11 = v10;
    v11[1] = v10;
    v11[2] = v10;
    *((_WORD *)v11 + 12) = 0;
    *((_QWORD *)&v13[0] + 1) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CPolicyEntry *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CPolicyEntry *,void *>>>(v13);
    v13[0] = v7;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Insert_node(
                      a1,
                      v13,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x1800027b4  push    rbx
0x1800027b6  push    rsi
0x1800027b7  push    rdi
0x1800027b8  push    r14
0x1800027ba  push    r15
0x1800027bc  sub     rsp, 50h
0x1800027c0  movaps  [rsp+78h+var_38], xmm6
0x1800027c5  mov     r15, r8
0x1800027c8  mov     rsi, rdx
0x1800027cb  mov     r14, rcx
0x1800027ce  lea     rdx, [rsp+78h+var_58]
0x1800027d3  call    ??$_Find_lower_bound@PEAVCPolicyEntry@@@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@std@@@1@AEBQEAVCPolicyEntry@@@Z; std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Find_lower_bound<CPolicyEntry *>(CPolicyEntry * const &)
0x1800027d8  movups  xmm6, xmmword ptr [rax]
0x1800027db  mov     rbx, [rax+10h]
0x1800027df  mov     r8, r15
0x1800027e2  mov     rdx, rbx
0x1800027e5  call    ??$_Lower_bound_duplicate@PEAVCPolicyEntry@@@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@1@AEBQEAVCPolicyEntry@@@Z; std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Lower_bound_duplicate<CPolicyEntry *>(std::_Tree_node<CPolicyEntry *,void *> * const,CPolicyEntry * const &)
0x1800027ea  test    al, al
0x1800027ec  jz      short loc_1800027FA
0x1800027ee  mov     [rsi], rbx
0x1800027f1  mov     byte ptr [rsi+8], 0
0x1800027f5  jmp     loc_18000287E
0x1800027fa  mov     rax, 666666666666666h
0x180002804  cmp     [r14+8], rax
0x180002808  jnz     short loc_180002818
0x18000280a  lea     rcx, aMapSetTooLong; "map/set too long"
0x180002811  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180002818  mov     rbx, [r14]
0x18000281b  mov     qword ptr [rsp+78h+var_58], r14
0x180002820  mov     qword ptr [rsp+78h+var_58+8], 0
0x180002829  mov     ecx, 28h ; '('; Size
0x18000282e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002833  mov     rdi, rax
0x180002836  mov     rcx, [r15]
0x180002839  mov     [rax+20h], rcx
0x18000283d  mov     [rax], rbx
0x180002840  mov     [rax+8], rbx
0x180002844  mov     [rax+10h], rbx
0x180002848  mov     word ptr [rax+18h], 0
0x18000284e  mov     qword ptr [rsp+78h+var_58+8], 0
0x180002857  lea     rcx, [rsp+78h+var_58]
0x18000285c  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@PEAVCPolicyEntry@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CPolicyEntry *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CPolicyEntry *,void *>>>(void)
0x180002861  movdqu  [rsp+78h+var_58], xmm6
0x180002867  mov     r8, rdi
0x18000286a  lea     rdx, [rsp+78h+var_58]
0x18000286f  mov     rcx, r14
0x180002872  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *>,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> * const)
0x180002877  mov     [rsi], rax
0x18000287a  mov     byte ptr [rsi+8], 1
0x18000287e  mov     rax, rsi
0x180002881  movaps  xmm6, [rsp+78h+var_38]
0x180002886  add     rsp, 50h
0x18000288a  pop     r15
0x18000288c  pop     r14
0x18000288e  pop     rdi
0x18000288f  pop     rsi
0x180002890  pop     rbx
0x180002891  retn
```
