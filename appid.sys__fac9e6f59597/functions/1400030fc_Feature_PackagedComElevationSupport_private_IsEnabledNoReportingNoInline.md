# Feature_PackagedComElevationSupport__private_IsEnabledNoReportingNoInline

- ea: `0x1400030fc`
- end: `0x14000312e`
- name: `Feature_PackagedComElevationSupport__private_IsEnabledNoReportingNoInline`
- size: `50`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002fc8`

## callees

- `0x1400030e0`
- `0x1400030fc`

## pseudocode

```c
__int64 Feature_PackagedComElevationSupport__private_IsEnabledNoReportingNoInline()
{
  if ( (Feature_PackagedComElevationSupport__private_featureState & 2) != 0 )
    return Feature_PackagedComElevationSupport__private_featureState & 1;
  else
    return Feature_PackagedComElevationSupport__private_IsEnabledFallback(
             (unsigned int)Feature_PackagedComElevationSupport__private_featureState,
             0);
}

```

## disassembly

```asm
0x1400030fc  sub     rsp, 28h
0x140003100  mov     eax, cs:Feature_PackagedComElevationSupport__private_featureState
0x140003106  mov     [rsp+28h+arg_0], 0
0x14000310f  mov     dword ptr [rsp+28h+arg_0], eax
0x140003113  test    al, 2
0x140003115  jz      short loc_14000311C
0x140003117  and     eax, 1
0x14000311a  jmp     short loc_140003128
0x14000311c  mov     rcx, [rsp+28h+arg_0]
0x140003121  xor     edx, edx
0x140003123  call    Feature_PackagedComElevationSupport__private_IsEnabledFallback
0x140003128  add     rsp, 28h
0x14000312c  retn
```
