# _dynamic_atexit_destructor_for__PackageCollector::s_registryCache__

- ea: `0x14000f000`
- end: `0x14000f00c`
- name: `_dynamic_atexit_destructor_for__PackageCollector::s_registryCache__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003a0c`

## pseudocode

```c
void dynamic_atexit_destructor_for__PackageCollector::s_registryCache__()
{
  std::vector<std::wstring>::_Tidy((__int64)&PackageCollector::s_registryCache);
}

```

## disassembly

```asm
0x14000f000  lea     rcx, ?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x14000f007  jmp     ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
```
