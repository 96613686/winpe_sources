# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::~_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>(void)

- ea: `0x18000b14c`
- end: `0x18000b1a2`
- name: `??1?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fc70`

## callees

- `0x180006288`
- `0x18000aaf8`
- `0x18000b14c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::~_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>(
        _QWORD *a1)
{
  __int64 v2; // rcx

  v2 = a1[3];
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (a1[5] - v2) & 0xFFFFFFFFFFFFFFF8uLL);
    a1[3] = 0;
    a1[4] = 0;
    a1[5] = 0;
  }
  std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(
    v2,
    a1[1]);
  return std::_Deallocate<16>(a1[1], 40);
}

```

## disassembly

```asm
0x18000b14c  push    rbx
0x18000b14e  sub     rsp, 20h
0x18000b152  mov     rbx, rcx
0x18000b155  mov     rcx, [rcx+18h]
0x18000b159  test    rcx, rcx
0x18000b15c  jz      short loc_18000B186
0x18000b15e  mov     rdx, [rbx+28h]
0x18000b162  sub     rdx, rcx
0x18000b165  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000b169  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b16e  mov     qword ptr [rbx+18h], 0
0x18000b176  mov     qword ptr [rbx+20h], 0
0x18000b17e  mov     qword ptr [rbx+28h], 0
0x18000b186  mov     rdx, [rbx+8]
0x18000b18a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>> &,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> *)
0x18000b18f  mov     rcx, [rbx+8]
0x18000b193  mov     edx, 28h ; '('
0x18000b198  add     rsp, 20h
0x18000b19c  pop     rbx
0x18000b19d  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
