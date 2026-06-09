# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::find(void * const &)

- ea: `0x18000de20`
- end: `0x18000de67`
- name: `?find@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@std@@@std@@@2@AEBQEAX@Z`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a1d8`
- `0x18000a2d4`

## callees

- `0x180009b54`
- `0x18000aa58`

## pseudocode

```c
__int64 *__fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::find(
        unsigned __int64 a1,
        __int64 *a2,
        const unsigned __int8 *a3)
{
  __int64 appended; // rax
  __int64 v5; // rcx
  _QWORD *v6; // r11
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 *result; // rax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF

  appended = std::_Fnv1a_append_bytes(a1, a3, 8u);
  v7 = std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(
         v5,
         v10,
         v6,
         appended);
  v8 = qword_180016578;
  if ( v7[1] )
    v8 = v7[1];
  result = a2;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x18000de20  push    rbx
0x18000de22  sub     rsp, 30h
0x18000de26  mov     r11, r8
0x18000de29  mov     rbx, rdx
0x18000de2c  mov     rdx, r11; unsigned __int8 *
0x18000de2f  mov     r8d, 8; unsigned __int64
0x18000de35  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18000de3a  mov     r9, rax
0x18000de3d  lea     rdx, [rsp+38h+var_18]
0x18000de42  mov     r8, r11
0x18000de45  call    ??$_Find_last@PEAX@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@1@AEBQEAX_K@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(void * const &,unsigned __int64)
0x18000de4a  mov     rcx, cs:qword_180016578
0x18000de51  cmp     qword ptr [rax+8], 0
0x18000de56  cmovnz  rcx, [rax+8]
0x18000de5b  mov     rax, rbx
0x18000de5e  mov     [rbx], rcx
0x18000de61  add     rsp, 30h
0x18000de65  pop     rbx
0x18000de66  retn
```
