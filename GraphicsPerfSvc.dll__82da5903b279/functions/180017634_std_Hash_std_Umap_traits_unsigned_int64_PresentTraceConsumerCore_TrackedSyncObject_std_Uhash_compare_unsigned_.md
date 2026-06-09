# std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>>>)

- ea: `0x180017634`
- end: `0x1800176cc`
- name: `??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@std@@@std@@@1@V21@@Z`
- size: `152`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018b78`

## callees

- `0x180016a50`
- `0x180017634`
- `0x18001baec`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>>>,0>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  unsigned __int64 appended; // rax
  __int64 v6; // rcx
  _QWORD *v7; // r11
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rbx

  appended = std::_Fnv1a_append_bytes((unsigned __int64)a1, (const unsigned __int8 *const)(a3 + 16), 8u);
  v8 = a1[3];
  v9 = 2 * (a1[6] & appended);
  if ( *(_QWORD **)(v8 + 16 * (a1[6] & appended) + 8) == v7 )
  {
    if ( *(_QWORD **)(v8 + 16 * (a1[6] & appended)) == v7 )
    {
      v10 = a1[1];
      *(_QWORD *)(v8 + 8 * v9) = v10;
    }
    else
    {
      v10 = v7[1];
    }
    *(_QWORD *)(v8 + 8 * v9 + 8) = v10;
  }
  else if ( *(_QWORD **)(v8 + 16 * (a1[6] & appended)) == v7 )
  {
    *(_QWORD *)(v8 + 16 * (a1[6] & appended)) = *v7;
  }
  v11 = *v7;
  --a1[2];
  *(_QWORD *)v7[1] = v11;
  *(_QWORD *)(v11 + 8) = v7[1];
  std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>(
    v6,
    v7);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x180017634  mov     [rsp+arg_0], rbx
0x180017639  mov     [rsp+arg_8], rsi
0x18001763e  push    rdi
0x18001763f  sub     rsp, 20h
0x180017643  mov     rsi, rdx
0x180017646  mov     r11, r8
0x180017649  lea     rdx, [r8+10h]; unsigned __int8 *
0x18001764d  mov     rdi, rcx
0x180017650  mov     r8d, 8; unsigned __int64
0x180017656  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001765b  mov     r9, [rdi+18h]
0x18001765f  mov     r8, rax
0x180017662  and     r8, [rdi+30h]
0x180017666  add     r8, r8
0x180017669  cmp     [r9+r8*8+8], r11
0x18001766e  jnz     short loc_18001768B
0x180017670  cmp     [r9+r8*8], r11
0x180017674  jnz     short loc_180017680
0x180017676  mov     rax, [rdi+8]
0x18001767a  mov     [r9+r8*8], rax
0x18001767e  jmp     short loc_180017684
0x180017680  mov     rax, [r11+8]
0x180017684  mov     [r9+r8*8+8], rax
0x180017689  jmp     short loc_180017698
0x18001768b  cmp     [r9+r8*8], r11
0x18001768f  jnz     short loc_180017698
0x180017691  mov     rax, [r11]
0x180017694  mov     [r9+r8*8], rax
0x180017698  mov     rbx, [r11]
0x18001769b  mov     rdx, r11
0x18001769e  dec     qword ptr [rdi+10h]
0x1800176a2  mov     rax, [r11+8]
0x1800176a6  mov     [rax], rbx
0x1800176a9  mov     rax, [r11+8]
0x1800176ad  mov     [rbx+8], rax
0x1800176b1  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>(std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>> &,std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *> *)
0x1800176b6  mov     [rsi], rbx
0x1800176b9  mov     rax, rsi
0x1800176bc  mov     rsi, [rsp+28h+arg_8]
0x1800176c1  mov     rbx, [rsp+28h+arg_0]
0x1800176c6  add     rsp, 20h
0x1800176ca  pop     rdi
0x1800176cb  retn
```
