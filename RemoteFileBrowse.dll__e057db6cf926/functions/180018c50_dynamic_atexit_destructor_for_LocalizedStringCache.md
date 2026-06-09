# _dynamic_atexit_destructor_for__LocalizedStringCache__

- ea: `0x180018c50`
- end: `0x180018c5c`
- name: `_dynamic_atexit_destructor_for__LocalizedStringCache__`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009c88`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__LocalizedStringCache__()
{
  return std::_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>(&LocalizedStringCache);
}

```

## disassembly

```asm
0x180018c50  lea     rcx, ?LocalizedStringCache@@3V?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@A; std::map<int,std::wstring> LocalizedStringCache
0x180018c57  jmp     ??1?$_Tree@V?$_Tmap_traits@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>(void)
```
