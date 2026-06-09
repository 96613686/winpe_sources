# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180003664`
- end: `0x1800036a0`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800036a8`

## callees

- `0x180003664`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(unsigned __int8 a1, int a2)
{
  int v2; // edx
  int v3; // r8d
  signed __int32 v4; // eax
  signed __int32 v5; // ett

  v2 = a2 - 3;
  if ( v2 )
  {
    if ( v2 != 1 )
      return;
    v3 = 32;
  }
  else
  {
    v3 = 16;
  }
  v4 = *Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(
           Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_descriptor[0],
           v4 | v3,
           v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x180003664  sub     edx, 3
0x180003667  jz      short loc_180003674
0x180003669  cmp     edx, 1
0x18000366c  jnz     short locret_18000369F
0x18000366e  lea     r8d, [rdx+1Fh]
0x180003672  jmp     short loc_18000367A
0x180003674  mov     r8d, 10h
0x18000367a  mov     r9, cs:Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_descriptor
0x180003681  mov     eax, [r9]
0x180003684  jmp     short loc_18000369B
0x180003686  mov     edx, eax
0x180003688  xor     edx, ecx
0x18000368a  test    dl, 1
0x18000368d  jnz     short locret_18000369F
0x18000368f  mov     edx, r8d
0x180003692  or      edx, eax
0x180003694  lock cmpxchg [r9], edx
0x180003699  jz      short locret_18000369F
0x18000369b  test    al, 2
0x18000369d  jnz     short loc_180003686
0x18000369f  retn
```
