# std::unordered_map<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::hash<uint>,std::equal_to<uint>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>::~unordered_map<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::hash<uint>,std::equal_to<uint>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>>(void)

- ea: `0x1400109e4`
- end: `0x140010a04`
- name: `??1?$unordered_map@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@U?$hash@I@std@@U?$equal_to@I@5@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@@std@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014f6e`
- `0x140015a38`

## callees

- `0x140001fac`
- `0x1400112f4`

## pseudocode

```c
void __fastcall std::unordered_map<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>::~unordered_map<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>(
        __int64 a1)
{
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(a1 + 24);
  std::list<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>::~list<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>((void **)(a1 + 8));
}

```

## disassembly

```asm
0x1400109e4  push    rbx
0x1400109e6  sub     rsp, 20h
0x1400109ea  mov     rbx, rcx
0x1400109ed  add     rcx, 18h
0x1400109f1  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(void)
0x1400109f6  lea     rcx, [rbx+8]
0x1400109fa  add     rsp, 20h
0x1400109fe  pop     rbx
0x1400109ff  jmp     ??1?$list@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>::~list<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>(void)
```
