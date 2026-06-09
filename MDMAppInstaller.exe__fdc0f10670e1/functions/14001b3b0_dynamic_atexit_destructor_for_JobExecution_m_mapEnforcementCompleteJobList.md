# _dynamic_atexit_destructor_for__JobExecution::m_mapEnforcementCompleteJobList__

- ea: `0x14001b3b0`
- end: `0x14001b3bc`
- name: `_dynamic_atexit_destructor_for__JobExecution::m_mapEnforcementCompleteJobList__`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009150`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__JobExecution::m_mapEnforcementCompleteJobList__()
{
  return std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(&JobExecution::m_mapEnforcementCompleteJobList);
}

```

## disassembly

```asm
0x14001b3b0  lea     rcx, ?m_mapEnforcementCompleteJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@A; std::map<std::wstring,ulong> JobExecution::m_mapEnforcementCompleteJobList
0x14001b3b7  jmp     ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(void)
```
