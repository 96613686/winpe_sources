# Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline

- ea: `0x140001270`
- end: `0x1400012a9`
- name: `Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002760`
- `0x140002a30`

## callees

- `0x140001270`
- `0x140003540`

## pseudocode

```c
__int64 Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_AppSiloSmbNoTrackDelete__private_featureState & 0x10) != 0 )
    return Feature_AppSiloSmbNoTrackDelete__private_featureState & 1;
  else
    return Feature_AppSiloSmbNoTrackDelete__private_IsEnabledFallback(
             (unsigned int)Feature_AppSiloSmbNoTrackDelete__private_featureState,
             3);
}

```

## disassembly

```asm
0x140001270  sub     rsp, 28h
0x140001274  mov     eax, cs:Feature_AppSiloSmbNoTrackDelete__private_featureState
0x14000127a  mov     [rsp+28h+arg_0], 0
0x140001283  mov     dword ptr [rsp+28h+arg_0], eax
0x140001287  test    al, 10h
0x140001289  jnz     short loc_1400012A0
0x14000128b  mov     rcx, [rsp+28h+arg_0]
0x140001290  mov     edx, 3
0x140001295  call    Feature_AppSiloSmbNoTrackDelete__private_IsEnabledFallback
0x14000129a  add     rsp, 28h
0x14000129e  retn
0x1400012a0  and     eax, 1
0x1400012a3  add     rsp, 28h
0x1400012a7  retn
```
