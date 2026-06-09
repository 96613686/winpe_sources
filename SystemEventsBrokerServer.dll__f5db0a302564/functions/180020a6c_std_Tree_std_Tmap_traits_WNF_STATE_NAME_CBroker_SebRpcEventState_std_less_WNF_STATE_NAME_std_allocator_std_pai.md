# std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::_Emplace<std::pair<_WNF_STATE_NAME,CBroker::SebRpcEventState *>>(std::pair<_WNF_STATE_NAME,CBroker::SebRpcEventState *> &&)

- ea: `0x180020a6c`
- end: `0x180020b5b`
- name: `??$_Emplace@U?$pair@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@U?$less@U_WNF_STATE_NAME@@@std@@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@1@@Z`
- size: `239`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180020d84`

## callees

- `0x180014210`
- `0x180015fb0`
- `0x180017a34`
- `0x18001cf74`
- `0x180020a6c`
- `0x180020b64`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180020ac8`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180020ac8`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::_Emplace<std::pair<_WNF_STATE_NAME,CBroker::SebRpcEventState *>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 lower; // rax
  __int128 v6; // xmm6
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 *v10; // rdi
  _OWORD v12[2]; // [rsp+20h] [rbp-58h] BYREF

  lower = std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::_Find_lower_bound<_WNF_STATE_NAME>(
            a1,
            v12);
  v6 = *(_OWORD *)lower;
  v7 = *(_QWORD *)(lower + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::_Lower_bound_duplicate<_WNF_STATE_NAME>(
                          v8,
                          v7,
                          a3) )
  {
    *(_QWORD *)a2 = v7;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( qword_180036E08 == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v9 = qword_180036E00;
    *(_QWORD *)&v12[0] = &qword_180036E00;
    *((_QWORD *)&v12[0] + 1) = 0;
    v10 = (__int64 *)operator new(0x30u);
    v10[4] = *a3;
    v10[5] = a3[1];
    *v10 = v9;
    v10[1] = v9;
    v10[2] = v9;
    *((_WORD *)v10 + 12) = 0;
    *((_QWORD *)&v12[0] + 1) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>,void *>>>(v12);
    v12[0] = v6;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>>::_Insert_node(
                      &qword_180036E00,
                      v12,
                      v10);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x180020a6c  push    rbx
0x180020a6e  push    rbp
0x180020a6f  push    rsi
0x180020a70  push    rdi
0x180020a71  push    r14
0x180020a73  sub     rsp, 50h
0x180020a77  movaps  [rsp+78h+var_38], xmm6
0x180020a7c  mov     r14, r8
0x180020a7f  mov     rsi, rdx
0x180020a82  lea     rdx, [rsp+78h+var_58]
0x180020a87  call    ??$_Find_lower_bound@U_WNF_STATE_NAME@@@?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@U?$less@U_WNF_STATE_NAME@@@std@@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@PEAX@std@@@1@AEBU_WNF_STATE_NAME@@@Z; std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::_Find_lower_bound<_WNF_STATE_NAME>(_WNF_STATE_NAME const &)
0x180020a8c  movups  xmm6, xmmword ptr [rax]
0x180020a8f  mov     rbx, [rax+10h]
0x180020a93  mov     r8, r14
0x180020a96  mov     rdx, rbx
0x180020a99  call    ??$_Lower_bound_duplicate@U_WNF_STATE_NAME@@@?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@U?$less@U_WNF_STATE_NAME@@@std@@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@5@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@PEAX@1@AEBU_WNF_STATE_NAME@@@Z; std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,CBroker::SebRpcEventState *,std::less<_WNF_STATE_NAME>,std::allocator<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>,0>>::_Lower_bound_duplicate<_WNF_STATE_NAME>(std::_Tree_node<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>,void *> * const,_WNF_STATE_NAME const &)
0x180020a9e  test    al, al
0x180020aa0  jz      short loc_180020AAE
0x180020aa2  mov     [rsi], rbx
0x180020aa5  mov     byte ptr [rsi+8], 0
0x180020aa9  jmp     loc_180020B48
0x180020aae  mov     rax, 555555555555555h
0x180020ab8  cmp     cs:qword_180036E08, rax
0x180020abf  jnz     short loc_180020ACF
0x180020ac1  lea     rcx, aMapSetTooLong; "map/set too long"
0x180020ac8  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180020acf  mov     rbx, cs:qword_180036E00
0x180020ad6  lea     rbp, qword_180036E00
0x180020add  mov     qword ptr [rsp+78h+var_58], rbp
0x180020ae2  mov     qword ptr [rsp+78h+var_58+8], 0
0x180020aeb  mov     ecx, 30h ; '0'; Size
0x180020af0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020af5  mov     rdi, rax
0x180020af8  mov     rcx, [r14]
0x180020afb  mov     [rax+20h], rcx
0x180020aff  mov     rdx, [r14+8]
0x180020b03  mov     [rax+28h], rdx
0x180020b07  mov     [rax], rbx
0x180020b0a  mov     [rax+8], rbx
0x180020b0e  mov     [rax+10h], rbx
0x180020b12  mov     word ptr [rax+18h], 0
0x180020b18  mov     qword ptr [rsp+78h+var_58+8], 0
0x180020b21  lea     rcx, [rsp+78h+var_58]
0x180020b26  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>,void *>>>(void)
0x180020b2b  movdqu  [rsp+78h+var_58], xmm6
0x180020b31  mov     r8, rdi
0x180020b34  lea     rdx, [rsp+78h+var_58]
0x180020b39  mov     rcx, rbp
0x180020b3c  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>,void *> *>,std::_Tree_node<std::pair<_WNF_STATE_NAME const,CBroker::SebRpcEventState *>,void *> * const)
0x180020b41  mov     [rsi], rax
0x180020b44  mov     byte ptr [rsi+8], 1
0x180020b48  mov     rax, rsi
0x180020b4b  movaps  xmm6, [rsp+78h+var_38]
0x180020b50  add     rsp, 50h
0x180020b54  pop     r14
0x180020b56  pop     rdi
0x180020b57  pop     rsi
0x180020b58  pop     rbp
0x180020b59  pop     rbx
0x180020b5a  retn
```
