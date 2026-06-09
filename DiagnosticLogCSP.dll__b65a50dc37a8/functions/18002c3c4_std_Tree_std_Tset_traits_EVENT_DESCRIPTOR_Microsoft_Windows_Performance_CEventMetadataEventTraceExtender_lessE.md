# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::insert<0,0>(_EVENT_DESCRIPTOR const &)

- ea: `0x18002c3c4`
- end: `0x18002c518`
- name: `??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_EVENT_DESCRIPTOR@@@std@@@std@@@std@@_N@1@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002d540`

## callees

- `0x180001bb4`
- `0x18001138c`
- `0x180011618`
- `0x18002c3c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::insert<0,0>(
        __int64 *a1,
        __int64 a2,
        __int16 *a3)
{
  __int64 inserted; // r10
  __int64 v7; // r12
  unsigned int v8; // r14d
  __int64 v9; // r9
  char v10; // bp
  unsigned __int16 v11; // cx
  unsigned __int8 v12; // al
  unsigned __int16 v13; // ax
  unsigned __int8 v14; // al
  unsigned __int64 v15; // rax
  __int64 v16; // rbx
  _OWORD *v17; // rax
  __int64 *v19; // [rsp+20h] [rbp-38h] BYREF
  __int64 v20; // [rsp+28h] [rbp-30h]

  inserted = *a1;
  v7 = *(_QWORD *)(*a1 + 8);
  v8 = 0;
  v9 = v7;
  v10 = 1;
  if ( !*(_BYTE *)(v7 + 25) )
  {
    v11 = *a3;
    do
    {
      v7 = v9;
      if ( *(_WORD *)(v9 + 32) < v11
        || *(_WORD *)(v9 + 32) <= v11
        && ((v12 = *((_BYTE *)a3 + 2), *(_BYTE *)(v9 + 34) < v12)
         || *(_BYTE *)(v9 + 34) <= v12
         && (*(_QWORD *)(v9 + 32) < *(_QWORD *)a3
          || *(_QWORD *)(v9 + 32) <= *(_QWORD *)a3 && *(_QWORD *)(v9 + 40) < *((_QWORD *)a3 + 1))) )
      {
        v8 = 0;
        v9 = *(_QWORD *)(v9 + 16);
      }
      else
      {
        v8 = 1;
        inserted = v9;
        v9 = *(_QWORD *)v9;
      }
    }
    while ( !*(_BYTE *)(v9 + 25) );
  }
  if ( *(_BYTE *)(inserted + 25)
    || (v13 = *(_WORD *)(inserted + 32), (unsigned __int16)*a3 < v13)
    || (unsigned __int16)*a3 <= v13
    && ((v14 = *(_BYTE *)(inserted + 34), *((_BYTE *)a3 + 2) < v14)
     || *((_BYTE *)a3 + 2) <= v14
     && ((v15 = *(_QWORD *)(inserted + 32), *(_QWORD *)a3 < v15)
      || *(_QWORD *)a3 <= v15 && *((_QWORD *)a3 + 1) < *(_QWORD *)(inserted + 40))) )
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Throw_tree_length_error();
    v16 = *a1;
    v19 = a1;
    v20 = 0;
    v17 = operator new(0x30u);
    v17[2] = *(_OWORD *)a3;
    *(_QWORD *)v17 = v16;
    *((_QWORD *)v17 + 1) = v16;
    *((_QWORD *)v17 + 2) = v16;
    *((_WORD *)v17 + 12) = 0;
    v19 = (__int64 *)v7;
    v20 = v8;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                 a1,
                 &v19,
                 v17);
  }
  else
  {
    v10 = 0;
  }
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v10;
  return a2;
}

```

## disassembly

```asm
0x18002c3c4  mov     [rsp+arg_8], rbx
0x18002c3c9  mov     [rsp+arg_10], rbp
0x18002c3ce  push    rsi
0x18002c3cf  push    rdi
0x18002c3d0  push    r12
0x18002c3d2  push    r14
0x18002c3d4  push    r15
0x18002c3d6  sub     rsp, 30h
0x18002c3da  mov     rdi, r8
0x18002c3dd  mov     rsi, rdx
0x18002c3e0  mov     r15, rcx
0x18002c3e3  mov     r10, [rcx]
0x18002c3e6  mov     r12, [r10+8]
0x18002c3ea  xor     r14d, r14d
0x18002c3ed  xor     eax, eax
0x18002c3ef  mov     [rsp+58h+arg_0], rax
0x18002c3f4  mov     r9, r12
0x18002c3f7  lea     ebp, [rax+1]
0x18002c3fa  cmp     [r12+19h], al
0x18002c3ff  jnz     short loc_18002C44B
0x18002c401  movzx   ecx, word ptr [r8]
0x18002c405  mov     r12, r9
0x18002c408  cmp     [r9+20h], cx
0x18002c40d  jb      short loc_18002C43D
0x18002c40f  ja      short loc_18002C432
0x18002c411  mov     al, [r8+2]
0x18002c415  cmp     [r9+22h], al
0x18002c419  jb      short loc_18002C43D
0x18002c41b  ja      short loc_18002C432
0x18002c41d  mov     rax, [r8]
0x18002c420  cmp     [r9+20h], rax
0x18002c424  jb      short loc_18002C43D
0x18002c426  ja      short loc_18002C432
0x18002c428  mov     rax, [r8+8]
0x18002c42c  cmp     [r9+28h], rax
0x18002c430  jb      short loc_18002C43D
0x18002c432  mov     r14d, ebp
0x18002c435  mov     r10, r9
0x18002c438  mov     r9, [r9]
0x18002c43b  jmp     short loc_18002C444
0x18002c43d  xor     r14d, r14d
0x18002c440  mov     r9, [r9+10h]
0x18002c444  cmp     byte ptr [r9+19h], 0
0x18002c449  jz      short loc_18002C405
0x18002c44b  cmp     byte ptr [r10+19h], 0
0x18002c450  jnz     short loc_18002C485
0x18002c452  movzx   eax, word ptr [r10+20h]
0x18002c457  cmp     [r8], ax
0x18002c45b  jb      short loc_18002C485
0x18002c45d  ja      short loc_18002C480
0x18002c45f  mov     al, [r10+22h]
0x18002c463  cmp     [r8+2], al
0x18002c467  jb      short loc_18002C485
0x18002c469  ja      short loc_18002C480
0x18002c46b  mov     rax, [r10+20h]
0x18002c46f  cmp     [r8], rax
0x18002c472  jb      short loc_18002C485
0x18002c474  ja      short loc_18002C480
0x18002c476  mov     rax, [r10+28h]
0x18002c47a  cmp     [r8+8], rax
0x18002c47e  jb      short loc_18002C485
0x18002c480  xor     bpl, bpl
0x18002c483  jmp     short loc_18002C4F0
0x18002c485  mov     rax, 555555555555555h
0x18002c48f  cmp     [r15+8], rax
0x18002c493  jz      short loc_18002C512
0x18002c495  mov     rbx, [r15]
0x18002c498  mov     [rsp+58h+var_38], r15
0x18002c49d  mov     [rsp+58h+var_30], 0
0x18002c4a6  mov     ecx, 30h ; '0'; Size
0x18002c4ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c4b0  nop
0x18002c4b1  movups  xmm0, xmmword ptr [rdi]
0x18002c4b4  movdqu  xmmword ptr [rax+20h], xmm0
0x18002c4b9  mov     [rax], rbx
0x18002c4bc  mov     [rax+8], rbx
0x18002c4c0  mov     [rax+10h], rbx
0x18002c4c4  mov     word ptr [rax+18h], 0
0x18002c4ca  mov     [rsp+58h+var_38], r12
0x18002c4cf  mov     dword ptr [rsp+58h+var_30], r14d
0x18002c4d4  mov     rcx, [rsp+58h+arg_0]
0x18002c4d9  mov     dword ptr [rsp+58h+var_30+4], ecx
0x18002c4dd  mov     r8, rax
0x18002c4e0  lea     rdx, [rsp+58h+var_38]
0x18002c4e5  mov     rcx, r15
0x18002c4e8  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18002c4ed  mov     r10, rax
0x18002c4f0  mov     [rsi], r10
0x18002c4f3  mov     [rsi+8], bpl
0x18002c4f7  mov     rax, rsi
0x18002c4fa  mov     rbx, [rsp+58h+arg_8]
0x18002c4ff  mov     rbp, [rsp+58h+arg_10]
0x18002c504  add     rsp, 30h
0x18002c508  pop     r15
0x18002c50a  pop     r14
0x18002c50c  pop     r12
0x18002c50e  pop     rdi
0x18002c50f  pop     rsi
0x18002c510  retn
0x18002c512  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
