# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::insert<0,0>(_EVENT_DESCRIPTOR const &)

- ea: `0x18002b0f0`
- end: `0x18002b243`
- name: `??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_EVENT_DESCRIPTOR@@@std@@@std@@@std@@_N@1@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002c210`

## callees

- `0x180001b84`
- `0x180010b08`
- `0x180010d94`
- `0x18002b0f0`

## pseudocode

```c
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
                 &v19);
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
0x18002b0f0  mov     [rsp+arg_8], rbx
0x18002b0f5  mov     [rsp+arg_10], rbp
0x18002b0fa  push    rsi
0x18002b0fb  push    rdi
0x18002b0fc  push    r12
0x18002b0fe  push    r14
0x18002b100  push    r15
0x18002b102  sub     rsp, 30h
0x18002b106  mov     rdi, r8
0x18002b109  mov     rsi, rdx
0x18002b10c  mov     r15, rcx
0x18002b10f  mov     r10, [rcx]
0x18002b112  mov     r12, [r10+8]
0x18002b116  xor     r14d, r14d
0x18002b119  xor     eax, eax
0x18002b11b  mov     [rsp+58h+arg_0], rax
0x18002b120  mov     r9, r12
0x18002b123  lea     ebp, [rax+1]
0x18002b126  cmp     [r12+19h], al
0x18002b12b  jnz     short loc_18002B177
0x18002b12d  movzx   ecx, word ptr [r8]
0x18002b131  mov     r12, r9
0x18002b134  cmp     [r9+20h], cx
0x18002b139  jb      short loc_18002B169
0x18002b13b  ja      short loc_18002B15E
0x18002b13d  mov     al, [r8+2]
0x18002b141  cmp     [r9+22h], al
0x18002b145  jb      short loc_18002B169
0x18002b147  ja      short loc_18002B15E
0x18002b149  mov     rax, [r8]
0x18002b14c  cmp     [r9+20h], rax
0x18002b150  jb      short loc_18002B169
0x18002b152  ja      short loc_18002B15E
0x18002b154  mov     rax, [r8+8]
0x18002b158  cmp     [r9+28h], rax
0x18002b15c  jb      short loc_18002B169
0x18002b15e  mov     r14d, ebp
0x18002b161  mov     r10, r9
0x18002b164  mov     r9, [r9]
0x18002b167  jmp     short loc_18002B170
0x18002b169  xor     r14d, r14d
0x18002b16c  mov     r9, [r9+10h]
0x18002b170  cmp     byte ptr [r9+19h], 0
0x18002b175  jz      short loc_18002B131
0x18002b177  cmp     byte ptr [r10+19h], 0
0x18002b17c  jnz     short loc_18002B1B1
0x18002b17e  movzx   eax, word ptr [r10+20h]
0x18002b183  cmp     [r8], ax
0x18002b187  jb      short loc_18002B1B1
0x18002b189  ja      short loc_18002B1AC
0x18002b18b  mov     al, [r10+22h]
0x18002b18f  cmp     [r8+2], al
0x18002b193  jb      short loc_18002B1B1
0x18002b195  ja      short loc_18002B1AC
0x18002b197  mov     rax, [r10+20h]
0x18002b19b  cmp     [r8], rax
0x18002b19e  jb      short loc_18002B1B1
0x18002b1a0  ja      short loc_18002B1AC
0x18002b1a2  mov     rax, [r10+28h]
0x18002b1a6  cmp     [r8+8], rax
0x18002b1aa  jb      short loc_18002B1B1
0x18002b1ac  xor     bpl, bpl
0x18002b1af  jmp     short loc_18002B21C
0x18002b1b1  mov     rax, 555555555555555h
0x18002b1bb  cmp     [r15+8], rax
0x18002b1bf  jz      short loc_18002B23D
0x18002b1c1  mov     rbx, [r15]
0x18002b1c4  mov     [rsp+58h+var_38], r15
0x18002b1c9  mov     [rsp+58h+var_30], 0
0x18002b1d2  mov     ecx, 30h ; '0'; Size
0x18002b1d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b1dc  nop
0x18002b1dd  movups  xmm0, xmmword ptr [rdi]
0x18002b1e0  movdqu  xmmword ptr [rax+20h], xmm0
0x18002b1e5  mov     [rax], rbx
0x18002b1e8  mov     [rax+8], rbx
0x18002b1ec  mov     [rax+10h], rbx
0x18002b1f0  mov     word ptr [rax+18h], 0
0x18002b1f6  mov     [rsp+58h+var_38], r12
0x18002b1fb  mov     dword ptr [rsp+58h+var_30], r14d
0x18002b200  mov     rcx, [rsp+58h+arg_0]
0x18002b205  mov     dword ptr [rsp+58h+var_30+4], ecx
0x18002b209  mov     r8, rax
0x18002b20c  lea     rdx, [rsp+58h+var_38]
0x18002b211  mov     rcx, r15
0x18002b214  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18002b219  mov     r10, rax
0x18002b21c  mov     [rsi], r10
0x18002b21f  mov     [rsi+8], bpl
0x18002b223  mov     rax, rsi
0x18002b226  mov     rbx, [rsp+58h+arg_8]
0x18002b22b  mov     rbp, [rsp+58h+arg_10]
0x18002b230  add     rsp, 30h
0x18002b234  pop     r15
0x18002b236  pop     r14
0x18002b238  pop     r12
0x18002b23a  pop     rdi
0x18002b23b  pop     rsi
0x18002b23c  retn
0x18002b23d  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
