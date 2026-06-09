# _dynamic_initializer_for__AppMon::PortManager::m_openedHandleTable__

- ea: `0x1800011c0`
- end: `0x180001220`
- name: `_dynamic_initializer_for__AppMon::PortManager::m_openedHandleTable__`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800019d0`
- `0x180006378`
- `0x180009960`
- `0x18000d508`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int dynamic_initializer_for__AppMon::PortManager::m_openedHandleTable__()
{
  __int64 v0; // rcx

  std::list<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>::_Alloc_sentinel_and_proxy(&qword_180016578);
  std::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>(&qword_180016588);
  qword_1800165A0 = 7;
  qword_1800165A8 = 8;
  AppMon::PortManager::m_openedHandleTable = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    v0,
    16,
    qword_180016578);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__AppMon::PortManager::m_openedHandleTable__);
}

```

## disassembly

```asm
0x1800011c0  sub     rsp, 28h
0x1800011c4  lea     rcx, qword_180016578
0x1800011cb  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>::_Alloc_sentinel_and_proxy(void)
0x1800011d0  nop
0x1800011d1  lea     rcx, qword_180016588
0x1800011d8  call    ??0?$vector@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@V?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>(void)
0x1800011dd  nop
0x1800011de  mov     cs:qword_1800165A0, 7
0x1800011e9  mov     cs:qword_1800165A8, 8
0x1800011f4  mov     cs:?m_openedHandleTable@PortManager@AppMon@@0V?$unordered_map@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@U?$hash@PEAX@2@U?$equal_to@PEAX@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@@std@@A, 3F800000h; std::unordered_map<void *,std::shared_ptr<AppMon::AppPortEntry>> AppMon::PortManager::m_openedHandleTable
0x1800011fe  mov     r8, cs:qword_180016578
0x180001205  mov     edx, 10h
0x18000120a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18000120f  nop
0x180001210  lea     rcx, _dynamic_atexit_destructor_for__AppMon__PortManager__m_openedHandleTable__
0x180001217  add     rsp, 28h
0x18000121b  jmp     atexit
```
