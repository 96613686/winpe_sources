# Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_IsEnabledDeviceUsageNoInline

- ea: `0x140007568`
- end: `0x14000759d`
- name: `Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400061b0`

## callees

- `0x140007568`
- `0x1400075a4`

## pseudocode

```c
__int64 Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_featureState & 0x10) != 0 )
    return Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_featureState & 1;
  else
    return Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_IsEnabledFallback(
             (unsigned int)Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_featureState,
             3);
}

```

## disassembly

```asm
0x140007568  sub     rsp, 28h
0x14000756c  mov     eax, cs:Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_featureState
0x140007572  mov     [rsp+28h+arg_0], 0
0x14000757b  mov     dword ptr [rsp+28h+arg_0], eax
0x14000757f  test    al, 10h
0x140007581  jz      short loc_140007588
0x140007583  and     eax, 1
0x140007586  jmp     short loc_140007597
0x140007588  mov     rcx, [rsp+28h+arg_0]
0x14000758d  mov     edx, 3
0x140007592  call    Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_IsEnabledFallback
0x140007597  add     rsp, 28h
0x14000759b  retn
```
