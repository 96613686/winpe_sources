# Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline

- ea: `0x1400034e4`
- end: `0x140003519`
- name: `Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001fb0`
- `0x140003140`
- `0x140003210`
- `0x1400055d8`
- `0x140006e14`
- `0x140009b9c`
- `0x140011b44`
- `0x14001e020`
- `0x14001f078`

## callees

- `0x1400034e4`
- `0x140003520`

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
0x1400034e4  sub     rsp, 28h
0x1400034e8  mov     eax, cs:Feature_AgenticAppContainerBfsSupport__private_featureState
0x1400034ee  mov     [rsp+28h+arg_0], 0
0x1400034f7  mov     dword ptr [rsp+28h+arg_0], eax
0x1400034fb  test    al, 10h
0x1400034fd  jz      short loc_140003504
0x1400034ff  and     eax, 1
0x140003502  jmp     short loc_140003513
0x140003504  mov     rcx, [rsp+28h+arg_0]
0x140003509  mov     edx, 3
0x14000350e  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledFallback
0x140003513  add     rsp, 28h
0x140003517  retn
```
