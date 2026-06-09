# Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline

- ea: `0x140001814`
- end: `0x140001849`
- name: `Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b260`
- `0x14000c474`
- `0x14000f460`
- `0x1400110d8`
- `0x140016078`

## callees

- `0x1400015a8`
- `0x140001814`

## pseudocode

```c
__int64 Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_UserPresenceThrottling__private_featureState & 0x10) != 0 )
    return Feature_UserPresenceThrottling__private_featureState & 1;
  else
    return Feature_UserPresenceThrottling__private_IsEnabledFallback(
             (unsigned int)Feature_UserPresenceThrottling__private_featureState,
             3);
}

```

## disassembly

```asm
0x140001814  sub     rsp, 28h
0x140001818  mov     eax, cs:Feature_UserPresenceThrottling__private_featureState
0x14000181e  mov     [rsp+28h+arg_0], 0
0x140001827  mov     dword ptr [rsp+28h+arg_0], eax
0x14000182b  test    al, 10h
0x14000182d  jz      short loc_140001834
0x14000182f  and     eax, 1
0x140001832  jmp     short loc_140001843
0x140001834  mov     rcx, [rsp+28h+arg_0]
0x140001839  mov     edx, 3
0x14000183e  call    Feature_UserPresenceThrottling__private_IsEnabledFallback
0x140001843  add     rsp, 28h
0x140001847  retn
```
