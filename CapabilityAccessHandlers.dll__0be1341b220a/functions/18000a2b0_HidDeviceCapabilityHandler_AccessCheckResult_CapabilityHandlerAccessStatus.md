# HidDeviceCapabilityHandler::AccessCheckResult(CapabilityHandlerAccessStatus)

- ea: `0x18000a2b0`
- end: `0x18000a2b3`
- name: `?AccessCheckResult@HidDeviceCapabilityHandler@@UEAAJW4CapabilityHandlerAccessStatus@@@Z`
- size: `3`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004de0`

## pseudocode

```c
__int64 HidDeviceCapabilityHandler::AccessCheckResult()
{
  return 0;
}

```

## disassembly

```asm
0x18000a2b0  xor     eax, eax
0x18000a2b2  retn
```
