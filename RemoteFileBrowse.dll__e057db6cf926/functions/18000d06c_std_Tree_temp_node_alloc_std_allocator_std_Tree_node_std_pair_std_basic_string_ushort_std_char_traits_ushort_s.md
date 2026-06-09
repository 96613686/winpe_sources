# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<RfbServer>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<RfbServer>>,void *>>>(void)

- ea: `0x18000d06c`
- end: `0x18000d088`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VRfbServer@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180017de8`

## callees

- `0x180002054`
- `0x18000d06c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<RfbServer>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<RfbServer>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, 0x50u);
}

```

## disassembly

```asm
0x18000d06c  sub     rsp, 28h
0x18000d070  mov     rcx, [rcx+8]; void *
0x18000d074  test    rcx, rcx
0x18000d077  jz      short loc_18000D083
0x18000d079  mov     edx, 50h ; 'P'; unsigned __int64
0x18000d07e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d083  add     rsp, 28h
0x18000d087  retn
```
