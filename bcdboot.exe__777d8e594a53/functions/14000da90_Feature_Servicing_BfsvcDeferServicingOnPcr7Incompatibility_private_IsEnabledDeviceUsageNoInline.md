# Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_IsEnabledDeviceUsageNoInline

- ea: `0x14000da90`
- end: `0x14000daba`
- name: `Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_IsEnabledDeviceUsageNoInline`
- size: `42`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009fd4`

## callees

- `0x14000da90`
- `0x14000dac0`

## pseudocode

```c
__int64 Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_featureState & 0x10) != 0 )
    return Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_featureState & 1;
  else
    return Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_IsEnabledFallback(
             (unsigned int)Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_featureState,
             3);
}

```

## disassembly

```asm
0x14000da90  mov     eax, cs:Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_featureState
0x14000da96  mov     [rsp+arg_0], 0
0x14000da9f  mov     dword ptr [rsp+arg_0], eax
0x14000daa3  test    al, 10h
0x14000daa5  jz      short loc_14000DAAB
0x14000daa7  and     eax, 1
0x14000daaa  retn
0x14000daab  mov     rcx, [rsp+arg_0]
0x14000dab0  mov     edx, 3
0x14000dab5  jmp     Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_IsEnabledFallback
```
