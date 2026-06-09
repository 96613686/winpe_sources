# _dynamic_initializer_for__JobExecution::m_mapEnforcementCompleteJobList__

- ea: `0x140001a50`
- end: `0x140001a70`
- name: `_dynamic_initializer_for__JobExecution::m_mapEnforcementCompleteJobList__`
- size: `32`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001f94`
- `0x14001166c`

## pseudocode

```c
int dynamic_initializer_for__JobExecution::m_mapEnforcementCompleteJobList__()
{
  JobExecution::m_mapEnforcementCompleteJobList = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,unsigned long>>>::_Buyheadnode();
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__JobExecution::m_mapEnforcementCompleteJobList__);
}

```

## disassembly

```asm
0x140001a50  sub     rsp, 28h
0x140001a54  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,ulong>>>::_Buyheadnode(void)
0x140001a59  lea     rcx, _dynamic_atexit_destructor_for__JobExecution__m_mapEnforcementCompleteJobList__
0x140001a60  mov     cs:?m_mapEnforcementCompleteJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@A, rax; std::map<std::wstring,ulong> JobExecution::m_mapEnforcementCompleteJobList
0x140001a67  add     rsp, 28h
0x140001a6b  jmp     atexit
```
