# Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline

- ea: `0x140003614`
- end: `0x140003649`
- name: `Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64()`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001ba0`
- `0x140003270`
- `0x140003340`
- `0x140005768`
- `0x140006fa4`
- `0x140009d2c`
- `0x140011cd4`
- `0x14001e020`
- `0x14001f078`

## callees

- `0x140003614`
- `0x140003650`

## pseudocode

```c
__int64 Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_AgenticAppContainerBfsSupport__private_featureState & 0x10) != 0 )
    return Feature_AgenticAppContainerBfsSupport__private_featureState & 1;
  else
    return Feature_AgenticAppContainerBfsSupport__private_IsEnabledFallback(
             (unsigned int)Feature_AgenticAppContainerBfsSupport__private_featureState,
             3);
}

```

## disassembly

```asm
0x140003614  sub     rsp, 28h
0x140003618  mov     eax, cs:Feature_AgenticAppContainerBfsSupport__private_featureState
0x14000361e  mov     [rsp+28h+arg_0], 0
0x140003627  mov     dword ptr [rsp+28h+arg_0], eax
0x14000362b  test    al, 10h
0x14000362d  jz      short loc_140003634
0x14000362f  and     eax, 1
0x140003632  jmp     short loc_140003643
0x140003634  mov     rcx, [rsp+28h+arg_0]
0x140003639  mov     edx, 3
0x14000363e  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledFallback
0x140003643  add     rsp, 28h
0x140003647  retn
```
