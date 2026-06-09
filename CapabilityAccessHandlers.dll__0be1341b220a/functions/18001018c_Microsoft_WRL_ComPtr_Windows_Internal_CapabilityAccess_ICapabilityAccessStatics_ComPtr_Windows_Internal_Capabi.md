# Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::~ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>(void)

- ea: `0x18001018c`
- end: `0x180010191`
- name: `??1?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001386f`
- `0x180013881`
- `0x1800138d4`

## callees

- `0x18000f758`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::~ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(a1);
}

```

## disassembly

```asm
0x18001018c  jmp     ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
```
