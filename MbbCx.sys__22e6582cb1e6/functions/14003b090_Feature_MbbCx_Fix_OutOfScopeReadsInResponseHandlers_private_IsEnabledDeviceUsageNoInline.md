# Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_IsEnabledDeviceUsageNoInline

- ea: `0x14003b090`
- end: `0x14003b0c5`
- name: `Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14002a240`
- `0x14002ae5c`
- `0x14002c394`
- `0x140031550`

## callees

- `0x14003b090`
- `0x14003b0cc`

## pseudocode

```c
__int64 Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_featureState & 0x10) != 0 )
    return Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_featureState & 1;
  else
    return Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_IsEnabledFallback(
             (unsigned int)Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_featureState,
             3);
}

```

## disassembly

```asm
0x14003b090  sub     rsp, 28h
0x14003b094  mov     eax, cs:Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_featureState
0x14003b09a  mov     [rsp+28h+arg_0], 0
0x14003b0a3  mov     dword ptr [rsp+28h+arg_0], eax
0x14003b0a7  test    al, 10h
0x14003b0a9  jz      short loc_14003B0B0
0x14003b0ab  and     eax, 1
0x14003b0ae  jmp     short loc_14003B0BF
0x14003b0b0  mov     rcx, [rsp+28h+arg_0]
0x14003b0b5  mov     edx, 3
0x14003b0ba  call    Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_IsEnabledFallback
0x14003b0bf  add     rsp, 28h
0x14003b0c3  retn
```
