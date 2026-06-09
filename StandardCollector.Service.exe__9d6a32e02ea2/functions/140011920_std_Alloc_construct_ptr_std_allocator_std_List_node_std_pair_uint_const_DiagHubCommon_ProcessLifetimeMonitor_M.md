# std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *>>>(void)

- ea: `0x140011920`
- end: `0x14001193c`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015a50`

## callees

- `0x140011920`
- `0x14001382c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *>>>(
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
0x140011920  sub     rsp, 28h
0x140011924  mov     rcx, [rcx+8]; Block
0x140011928  test    rcx, rcx
0x14001192b  jz      short loc_140011937
0x14001192d  mov     edx, 40h ; '@'
0x140011932  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011937  add     rsp, 28h
0x14001193b  retn
```
