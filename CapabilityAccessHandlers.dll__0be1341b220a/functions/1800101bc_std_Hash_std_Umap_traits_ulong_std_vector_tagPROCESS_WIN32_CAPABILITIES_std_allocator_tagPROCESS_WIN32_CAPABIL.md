# std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>>,0>>::~_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>>,0>>(void)

- ea: `0x1800101bc`
- end: `0x180010212`
- name: `??1?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800103c0`

## callees

- `0x180006d38`
- `0x18000fbbc`
- `0x1800101bc`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::~_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>(
        _QWORD *a1)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)a1[3];
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (a1[5] - (_QWORD)v2) & 0xFFFFFFFFFFFFFFF8uLL);
    a1[3] = 0;
    a1[4] = 0;
    a1[5] = 0;
  }
  std::_List_node<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>(
    v2,
    a1[1]);
  std::_Deallocate<16>((_QWORD *)a1[1], 0x30u);
}

```

## disassembly

```asm
0x1800101bc  push    rbx
0x1800101be  sub     rsp, 20h
0x1800101c2  mov     rbx, rcx
0x1800101c5  mov     rcx, [rcx+18h]
0x1800101c9  test    rcx, rcx
0x1800101cc  jz      short loc_1800101F6
0x1800101ce  mov     rdx, [rbx+28h]
0x1800101d2  sub     rdx, rcx
0x1800101d5  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800101d9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800101de  mov     qword ptr [rbx+18h], 0
0x1800101e6  mov     qword ptr [rbx+20h], 0
0x1800101ee  mov     qword ptr [rbx+28h], 0
0x1800101f6  mov     rdx, [rbx+8]
0x1800101fa  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>(std::allocator<std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>> &,std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *> *)
0x1800101ff  mov     rcx, [rbx+8]
0x180010203  mov     edx, 30h ; '0'
0x180010208  add     rsp, 20h
0x18001020c  pop     rbx
0x18001020d  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
