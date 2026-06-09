# Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_IsEnabledFallback

- ea: `0x14000dac0`
- end: `0x14000dacc`
- name: `Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_IsEnabledFallback`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000da90`

## callees

- `0x14000e4b8`

## pseudocode

```c
__int64 __fastcall Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_IsEnabledFallback(
        __int64 a1,
        __int64 a2)
{
  return wil_details_IsEnabledFallback(
           a1,
           a2,
           Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_descriptor);
}

```

## disassembly

```asm
0x14000dac0  lea     r8, Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_descriptor
0x14000dac7  jmp     wil_details_IsEnabledFallback
```
