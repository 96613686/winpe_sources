# Windows::Internal::SyncRootHelpers::_dynamic_initializer_for__s_syncRootManagerRegistryPath__

- ea: `0x180001a70`
- end: `0x180001a7c`
- name: `Windows::Internal::SyncRootHelpers::_dynamic_initializer_for__s_syncRootManagerRegistryPath__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021b4`

## pseudocode

```c
int Windows::Internal::SyncRootHelpers::_dynamic_initializer_for__s_syncRootManagerRegistryPath__()
{
  return atexit(Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__);
}

```

## disassembly

```asm
0x180001a70  lea     rcx, Windows__Internal__SyncRootHelpers___dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__
0x180001a77  jmp     atexit
```
