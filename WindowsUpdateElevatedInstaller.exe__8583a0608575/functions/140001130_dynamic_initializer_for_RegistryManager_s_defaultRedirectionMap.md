# _dynamic_initializer_for__RegistryManager::s_defaultRedirectionMap__

- ea: `0x140001130`
- end: `0x140001149`
- name: `_dynamic_initializer_for__RegistryManager::s_defaultRedirectionMap__`
- size: `25`
- prototype: `int __fastcall(const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400016f4`
- `0x1400065a8`

## pseudocode

```c
int __fastcall dynamic_initializer_for__RegistryManager::s_defaultRedirectionMap__(const wchar_t *a1)
{
  RegistryManager::CreateRedirectionMap(a1);
  return atexit(dynamic_atexit_destructor_for__RegistryManager::s_defaultRedirectionMap__);
}

```

## disassembly

```asm
0x140001130  sub     rsp, 28h
0x140001134  call    ?CreateRedirectionMap@RegistryManager@@CA?AV?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@XZ; RegistryManager::CreateRedirectionMap(void)
0x140001139  lea     rcx, _dynamic_atexit_destructor_for__RegistryManager__s_defaultRedirectionMap__
0x140001140  add     rsp, 28h
0x140001144  jmp     atexit
```
