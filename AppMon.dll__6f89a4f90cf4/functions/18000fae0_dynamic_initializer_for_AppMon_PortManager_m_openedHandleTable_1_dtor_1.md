# __dynamic_initializer_for__AppMon::PortManager::m_openedHandleTable___::_1_::dtor$1

- ea: `0x18000fae0`
- end: `0x18000faf0`
- name: `__dynamic_initializer_for__AppMon::PortManager::m_openedHandleTable___::_1_::dtor$1`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b320`

## pseudocode

```c
__int64 _dynamic_initializer_for__AppMon::PortManager::m_openedHandleTable___::_1_::dtor_1()
{
  return std::list<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>::~list<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>(&qword_180016578);
}

```

## disassembly

```asm
0x18000fae0  lea     rcx, ?m_openedHandleTable@PortManager@AppMon@@0V?$unordered_map@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@U?$hash@PEAX@2@U?$equal_to@PEAX@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@@std@@A; std::unordered_map<void *,std::shared_ptr<AppMon::AppPortEntry>> AppMon::PortManager::m_openedHandleTable
0x18000fae7  add     rcx, 8
0x18000faeb  jmp     ??1?$list@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>::~list<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>(void)
```
