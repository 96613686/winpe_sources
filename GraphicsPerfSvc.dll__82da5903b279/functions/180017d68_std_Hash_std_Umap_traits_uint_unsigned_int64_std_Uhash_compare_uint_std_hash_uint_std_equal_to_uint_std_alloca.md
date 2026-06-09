# std::_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>(void)

- ea: `0x180017d68`
- end: `0x180017dbe`
- name: `??1?$_Hash@V?$_Umap_traits@I_KV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001828c`
- `0x18001857c`

## callees

- `0x18000b550`
- `0x18001698c`
- `0x180017d68`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>(
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
  std::_List_node<std::pair<unsigned __int64 const,unsigned int>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<unsigned __int64 const,unsigned int>,void *>>>(
    v2,
    *(_QWORD *)(a1 + 8));
  std::_Deallocate<16>(*(void **)(a1 + 8), 0x20u);
}

```

## disassembly

```asm
0x180017d68  push    rbx
0x180017d6a  sub     rsp, 20h
0x180017d6e  mov     rbx, rcx
0x180017d71  mov     rcx, [rcx+18h]
0x180017d75  test    rcx, rcx
0x180017d78  jz      short loc_180017DA2
0x180017d7a  mov     rdx, [rbx+28h]
0x180017d7e  sub     rdx, rcx
0x180017d81  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180017d85  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017d8a  mov     qword ptr [rbx+18h], 0
0x180017d92  mov     qword ptr [rbx+20h], 0
0x180017d9a  mov     qword ptr [rbx+28h], 0
0x180017da2  mov     rdx, [rbx+8]
0x180017da6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CB_KI@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CB_KI@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CB_KI@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<unsigned __int64 const,uint>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<unsigned __int64 const,uint>,void *>>>(std::allocator<std::_List_node<std::pair<unsigned __int64 const,uint>,void *>> &,std::_List_node<std::pair<unsigned __int64 const,uint>,void *> *)
0x180017dab  mov     rcx, [rbx+8]
0x180017daf  mov     edx, 20h ; ' '
0x180017db4  add     rsp, 20h
0x180017db8  pop     rbx
0x180017db9  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
