# __DeviceHelperAccessCheck_::_1_::dtor$0

- ea: `0x18001386f`
- end: `0x18001387b`
- name: `__DeviceHelperAccessCheck_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001018c`

## pseudocode

```c
__int64 __fastcall _DeviceHelperAccessCheck_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::~ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>(a2 + 80);
}

```

## disassembly

```asm
0x18001386f  lea     rcx, [rdx+50h]
0x180013876  jmp     ??1?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::~ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>(void)
```
