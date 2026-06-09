# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Range_eraser::_Bump_erased(void)

- ea: `0x18000d534`
- end: `0x18000d55a`
- name: `?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000db9c`

## callees

- `0x18000ab5c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Range_eraser::_Bump_erased(
        _QWORD *a1)
{
  __int64 result; // rax

  a1[2] = *(_QWORD *)a1[2];
  std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>();
  result = *a1;
  --*(_QWORD *)(*a1 + 8LL);
  return result;
}

```

## disassembly

```asm
0x18000d534  push    rbx
0x18000d536  sub     rsp, 20h
0x18000d53a  mov     rdx, [rcx+10h]
0x18000d53e  mov     rbx, rcx
0x18000d541  mov     rax, [rdx]
0x18000d544  mov     [rcx+10h], rax
0x18000d548  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>> &,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> *)
0x18000d54d  mov     rax, [rbx]
0x18000d550  dec     qword ptr [rax+8]
0x18000d554  add     rsp, 20h
0x18000d558  pop     rbx
0x18000d559  retn
```
