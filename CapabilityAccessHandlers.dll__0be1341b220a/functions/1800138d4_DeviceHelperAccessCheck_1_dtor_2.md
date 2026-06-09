# __DeviceHelperAccessCheck_::_1_::dtor$2

- ea: `0x1800138d4`
- end: `0x1800138e0`
- name: `__DeviceHelperAccessCheck_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001018c`

## pseudocode

```c
__int64 __fastcall _DeviceHelperAccessCheck_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::~ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>(a2 + 64);
}

```

## disassembly

```asm
0x1800138d4  lea     rcx, [rdx+40h]
0x1800138db  jmp     ??1?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::~ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>(void)
```
