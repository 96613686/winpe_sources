# _ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor$3

- ea: `0x14000eece`
- end: `0x14000eeda`
- name: `_ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000d30c`

## pseudocode

```c
__int64 __fastcall ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wil::details::out_param_t<std::unique_ptr<IElement,ProvReleaser<IElement>>>::~out_param_t<std::unique_ptr<IElement,ProvReleaser<IElement>>>(a2 + 40);
}

```

## disassembly

```asm
0x14000eece  lea     rcx, [rdx+28h]
0x14000eed5  jmp     ??1?$out_param_t@V?$unique_ptr@UIElement@@U?$ProvReleaser@UIElement@@@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<IElement,ProvReleaser<IElement>>>::~out_param_t<std::unique_ptr<IElement,ProvReleaser<IElement>>>(void)
```
