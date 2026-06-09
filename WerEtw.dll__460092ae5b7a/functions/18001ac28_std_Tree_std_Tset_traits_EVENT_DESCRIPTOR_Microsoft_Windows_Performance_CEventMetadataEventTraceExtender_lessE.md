# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::insert<0,0>(_EVENT_DESCRIPTOR const &)

- ea: `0x18001ac28`
- end: `0x18001ad7b`
- name: `??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_EVENT_DESCRIPTOR@@@std@@@std@@@std@@_N@1@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001da60`

## callees

- `0x1800018a0`
- `0x180015920`
- `0x180015b50`
- `0x18001ac28`

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
0x18001ac28  mov     [rsp+arg_8], rbx
0x18001ac2d  mov     [rsp+arg_10], rbp
0x18001ac32  push    rsi
0x18001ac33  push    rdi
0x18001ac34  push    r12
0x18001ac36  push    r14
0x18001ac38  push    r15
0x18001ac3a  sub     rsp, 30h
0x18001ac3e  mov     rdi, r8
0x18001ac41  mov     rsi, rdx
0x18001ac44  mov     r15, rcx
0x18001ac47  mov     r10, [rcx]
0x18001ac4a  mov     r12, [r10+8]
0x18001ac4e  xor     r14d, r14d
0x18001ac51  xor     eax, eax
0x18001ac53  mov     [rsp+58h+arg_0], rax
0x18001ac58  mov     r9, r12
0x18001ac5b  lea     ebp, [rax+1]
0x18001ac5e  cmp     [r12+19h], al
0x18001ac63  jnz     short loc_18001ACAF
0x18001ac65  movzx   ecx, word ptr [r8]
0x18001ac69  mov     r12, r9
0x18001ac6c  cmp     [r9+20h], cx
0x18001ac71  jb      short loc_18001ACA1
0x18001ac73  ja      short loc_18001AC96
0x18001ac75  mov     al, [r8+2]
0x18001ac79  cmp     [r9+22h], al
0x18001ac7d  jb      short loc_18001ACA1
0x18001ac7f  ja      short loc_18001AC96
0x18001ac81  mov     rax, [r8]
0x18001ac84  cmp     [r9+20h], rax
0x18001ac88  jb      short loc_18001ACA1
0x18001ac8a  ja      short loc_18001AC96
0x18001ac8c  mov     rax, [r8+8]
0x18001ac90  cmp     [r9+28h], rax
0x18001ac94  jb      short loc_18001ACA1
0x18001ac96  mov     r14d, ebp
0x18001ac99  mov     r10, r9
0x18001ac9c  mov     r9, [r9]
0x18001ac9f  jmp     short loc_18001ACA8
0x18001aca1  xor     r14d, r14d
0x18001aca4  mov     r9, [r9+10h]
0x18001aca8  cmp     byte ptr [r9+19h], 0
0x18001acad  jz      short loc_18001AC69
0x18001acaf  cmp     byte ptr [r10+19h], 0
0x18001acb4  jnz     short loc_18001ACE9
0x18001acb6  movzx   eax, word ptr [r10+20h]
0x18001acbb  cmp     [r8], ax
0x18001acbf  jb      short loc_18001ACE9
0x18001acc1  ja      short loc_18001ACE4
0x18001acc3  mov     al, [r10+22h]
0x18001acc7  cmp     [r8+2], al
0x18001accb  jb      short loc_18001ACE9
0x18001accd  ja      short loc_18001ACE4
0x18001accf  mov     rax, [r10+20h]
0x18001acd3  cmp     [r8], rax
0x18001acd6  jb      short loc_18001ACE9
0x18001acd8  ja      short loc_18001ACE4
0x18001acda  mov     rax, [r10+28h]
0x18001acde  cmp     [r8+8], rax
0x18001ace2  jb      short loc_18001ACE9
0x18001ace4  xor     bpl, bpl
0x18001ace7  jmp     short loc_18001AD54
0x18001ace9  mov     rax, 555555555555555h
0x18001acf3  cmp     [r15+8], rax
0x18001acf7  jz      short loc_18001AD75
0x18001acf9  mov     rbx, [r15]
0x18001acfc  mov     [rsp+58h+var_38], r15
0x18001ad01  mov     [rsp+58h+var_30], 0
0x18001ad0a  mov     ecx, 30h ; '0'; Size
0x18001ad0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ad14  nop
0x18001ad15  movups  xmm0, xmmword ptr [rdi]
0x18001ad18  movdqu  xmmword ptr [rax+20h], xmm0
0x18001ad1d  mov     [rax], rbx
0x18001ad20  mov     [rax+8], rbx
0x18001ad24  mov     [rax+10h], rbx
0x18001ad28  mov     word ptr [rax+18h], 0
0x18001ad2e  mov     [rsp+58h+var_38], r12
0x18001ad33  mov     dword ptr [rsp+58h+var_30], r14d
0x18001ad38  mov     rcx, [rsp+58h+arg_0]
0x18001ad3d  mov     dword ptr [rsp+58h+var_30+4], ecx
0x18001ad41  mov     r8, rax
0x18001ad44  lea     rdx, [rsp+58h+var_38]
0x18001ad49  mov     rcx, r15
0x18001ad4c  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18001ad51  mov     r10, rax
0x18001ad54  mov     [rsi], r10
0x18001ad57  mov     [rsi+8], bpl
0x18001ad5b  mov     rax, rsi
0x18001ad5e  mov     rbx, [rsp+58h+arg_8]
0x18001ad63  mov     rbp, [rsp+58h+arg_10]
0x18001ad68  add     rsp, 30h
0x18001ad6c  pop     r15
0x18001ad6e  pop     r14
0x18001ad70  pop     r12
0x18001ad72  pop     rdi
0x18001ad73  pop     rsi
0x18001ad74  retn
0x18001ad75  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
