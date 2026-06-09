# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,MidiVirtualDeviceEndpointEntry>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,MidiVirtualDeviceEndpointEntry>,void *>>>(void)

- ea: `0x1800141e0`
- end: `0x1800141fc`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800201af`

## callees

- `0x180003914`
- `0x1800141e0`

## pseudocode

```c
void __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>,void *>>>(
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
0x1800141e0  sub     rsp, 28h
0x1800141e4  mov     rcx, [rcx+8]; Block
0x1800141e8  test    rcx, rcx
0x1800141eb  jz      short loc_1800141F7
0x1800141ed  mov     edx, 178h
0x1800141f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800141f7  add     rsp, 28h
0x1800141fb  retn
```
