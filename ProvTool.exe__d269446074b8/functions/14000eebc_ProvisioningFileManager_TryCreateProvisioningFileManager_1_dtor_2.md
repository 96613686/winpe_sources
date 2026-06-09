# _ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor$2

- ea: `0x14000eebc`
- end: `0x14000eec8`
- name: `_ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000d350`

## pseudocode

```c
__int64 __fastcall ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wil::details::out_param_t<std::unique_ptr<IElementEnumerator,ProvReleaser<IElementEnumerator>>>::~out_param_t<std::unique_ptr<IElementEnumerator,ProvReleaser<IElementEnumerator>>>(a2 + 40);
}

```

## disassembly

```asm
0x14000eebc  lea     rcx, [rdx+28h]
0x14000eec3  jmp     ??1?$out_param_t@V?$unique_ptr@UIElementEnumerator@@U?$ProvReleaser@UIElementEnumerator@@@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<IElementEnumerator,ProvReleaser<IElementEnumerator>>>::~out_param_t<std::unique_ptr<IElementEnumerator,ProvReleaser<IElementEnumerator>>>(void)
```
