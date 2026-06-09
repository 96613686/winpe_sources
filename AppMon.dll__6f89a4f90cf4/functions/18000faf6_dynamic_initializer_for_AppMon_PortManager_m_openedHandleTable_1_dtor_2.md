# __dynamic_initializer_for__AppMon::PortManager::m_openedHandleTable___::_1_::dtor$2

- ea: `0x18000faf6`
- end: `0x18000fb06`
- name: `__dynamic_initializer_for__AppMon::PortManager::m_openedHandleTable___::_1_::dtor$2`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b204`

## pseudocode

```c
__int64 _dynamic_initializer_for__AppMon::PortManager::m_openedHandleTable___::_1_::dtor_2()
{
  return std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&qword_180016588);
}

```

## disassembly

```asm
0x18000faf6  lea     rcx, ?m_openedHandleTable@PortManager@AppMon@@0V?$unordered_map@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@U?$hash@PEAX@2@U?$equal_to@PEAX@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@@std@@A; std::unordered_map<void *,std::shared_ptr<AppMon::AppPortEntry>> AppMon::PortManager::m_openedHandleTable
0x18000fafd  add     rcx, 18h
0x18000fb01  jmp     ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(void)
```
