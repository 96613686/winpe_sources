# Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__

- ea: `0x18000cf70`
- end: `0x18000cf8b`
- name: `Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__`
- size: `27`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000cf70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf80`

## pseudocode

```c
void Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__()
{
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x18000cf70  sub     rsp, 28h
0x18000cf74  mov     rcx, cs:pv; pv
0x18000cf7b  test    rcx, rcx
0x18000cf7e  jz      short loc_18000CF86
0x18000cf80  call    cs:__imp_CoTaskMemFree
0x18000cf86  add     rsp, 28h
0x18000cf8a  retn
```
