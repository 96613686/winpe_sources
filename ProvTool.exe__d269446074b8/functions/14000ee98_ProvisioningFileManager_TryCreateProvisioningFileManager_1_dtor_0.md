# _ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor$0

- ea: `0x14000ee98`
- end: `0x14000eea4`
- name: `_ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000c298`

## pseudocode

```c
__int64 __fastcall ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::unique_ptr<IElement,ProvReleaser<IElement>>::~unique_ptr<IElement,ProvReleaser<IElement>>(a2 + 32);
}

```

## disassembly

```asm
0x14000ee98  lea     rcx, [rdx+20h]
0x14000ee9f  jmp     ??1?$unique_ptr@UIElement@@U?$ProvReleaser@UIElement@@@@@std@@QEAA@XZ; std::unique_ptr<IElement,ProvReleaser<IElement>>::~unique_ptr<IElement,ProvReleaser<IElement>>(void)
```
