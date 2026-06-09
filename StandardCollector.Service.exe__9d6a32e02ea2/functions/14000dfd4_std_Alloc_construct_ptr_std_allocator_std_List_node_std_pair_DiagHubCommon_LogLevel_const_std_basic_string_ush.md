# std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>>>(void)

- ea: `0x14000dfd4`
- end: `0x14000dff0`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400156ce`

## callees

- `0x14000dfd4`
- `0x14001382c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x14000dfd4  sub     rsp, 28h
0x14000dfd8  mov     rcx, [rcx+8]; Block
0x14000dfdc  test    rcx, rcx
0x14000dfdf  jz      short loc_14000DFEB
0x14000dfe1  mov     edx, 38h ; '8'
0x14000dfe6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000dfeb  add     rsp, 28h
0x14000dfef  retn
```
