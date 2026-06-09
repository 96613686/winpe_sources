# std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>>,0>>::_Range_eraser::_Bump_erased(void)

- ea: `0x180010e64`
- end: `0x180010e8a`
- name: `?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011188`

## callees

- `0x18000fbf4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Range_eraser::_Bump_erased(
        _QWORD *a1)
{
  __int64 result; // rax

  a1[2] = *(_QWORD *)a1[2];
  std::_List_node<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>();
  result = *a1;
  --*(_QWORD *)(*a1 + 8LL);
  return result;
}

```

## disassembly

```asm
0x180010e64  push    rbx
0x180010e66  sub     rsp, 20h
0x180010e6a  mov     rdx, [rcx+10h]
0x180010e6e  mov     rbx, rcx
0x180010e71  mov     rax, [rdx]
0x180010e74  mov     [rcx+10h], rax
0x180010e78  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>(std::allocator<std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>> &,std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *> *)
0x180010e7d  mov     rax, [rbx]
0x180010e80  dec     qword ptr [rax+8]
0x180010e84  add     rsp, 20h
0x180010e88  pop     rbx
0x180010e89  retn
```
