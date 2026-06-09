# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180003630`
- end: `0x18000366c`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003674`

## callees

- `0x180003630`

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
  v4 = *Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_descriptor;
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(
           Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_descriptor,
           v4 | v3,
           v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x180003630  sub     edx, 3
0x180003633  jz      short loc_180003640
0x180003635  cmp     edx, 1
0x180003638  jnz     short locret_18000366B
0x18000363a  lea     r8d, [rdx+1Fh]
0x18000363e  jmp     short loc_180003646
0x180003640  mov     r8d, 10h
0x180003646  mov     r9, cs:Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_descriptor
0x18000364d  mov     eax, [r9]
0x180003650  jmp     short loc_180003667
0x180003652  mov     edx, eax
0x180003654  xor     edx, ecx
0x180003656  test    dl, 1
0x180003659  jnz     short locret_18000366B
0x18000365b  mov     edx, r8d
0x18000365e  or      edx, eax
0x180003660  lock cmpxchg [r9], edx
0x180003665  jz      short locret_18000366B
0x180003667  test    al, 2
0x180003669  jnz     short loc_180003652
0x18000366b  retn
```
