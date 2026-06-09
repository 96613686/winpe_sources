# std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::~_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>(void)

- ea: `0x180017e20`
- end: `0x180017e76`
- name: `??1?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018298`
- `0x18001857c`

## callees

- `0x18000b550`
- `0x180016a18`
- `0x180017e20`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::~_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 24);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*(_QWORD *)(a1 + 40) - (_QWORD)v2) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
  }
  std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>(
    v2,
    *(_QWORD *)(a1 + 8));
  std::_Deallocate<16>(*(void **)(a1 + 8), 0x38u);
}

```

## disassembly

```asm
0x180017e20  push    rbx
0x180017e22  sub     rsp, 20h
0x180017e26  mov     rbx, rcx
0x180017e29  mov     rcx, [rcx+18h]
0x180017e2d  test    rcx, rcx
0x180017e30  jz      short loc_180017E5A
0x180017e32  mov     rdx, [rbx+28h]
0x180017e36  sub     rdx, rcx
0x180017e39  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180017e3d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017e42  mov     qword ptr [rbx+18h], 0
0x180017e4a  mov     qword ptr [rbx+20h], 0
0x180017e52  mov     qword ptr [rbx+28h], 0
0x180017e5a  mov     rdx, [rbx+8]
0x180017e5e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>>>(std::allocator<std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *>> &,std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *> *)
0x180017e63  mov     rcx, [rbx+8]
0x180017e67  mov     edx, 38h ; '8'
0x180017e6c  add     rsp, 20h
0x180017e70  pop     rbx
0x180017e71  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
