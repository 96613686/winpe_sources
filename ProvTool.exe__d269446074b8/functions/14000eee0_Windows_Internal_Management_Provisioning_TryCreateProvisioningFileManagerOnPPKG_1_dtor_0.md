# _Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG_::_1_::dtor$0

- ea: `0x14000eee0`
- end: `0x14000eeec`
- name: `_Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000c2e0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>::~unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>((__int64 *)(a2 + 112));
}

```

## disassembly

```asm
0x14000eee0  lea     rcx, [rdx+70h]
0x14000eee7  jmp     ??1?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@QEAA@XZ; std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>::~unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>(void)
```
