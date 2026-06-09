# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x18003c010`
- end: `0x18003c04c`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003c054`

## callees

- `0x18003c010`

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
0x18003c010  sub     edx, 3
0x18003c013  jz      short loc_18003C020
0x18003c015  cmp     edx, 1
0x18003c018  jnz     short locret_18003C04B
0x18003c01a  lea     r8d, [rdx+1Fh]
0x18003c01e  jmp     short loc_18003C026
0x18003c020  mov     r8d, 10h
0x18003c026  mov     r9, cs:Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_descriptor
0x18003c02d  mov     eax, [r9]
0x18003c030  jmp     short loc_18003C047
0x18003c032  mov     edx, eax
0x18003c034  xor     edx, ecx
0x18003c036  test    dl, 1
0x18003c039  jnz     short locret_18003C04B
0x18003c03b  mov     edx, r8d
0x18003c03e  or      edx, eax
0x18003c040  lock cmpxchg [r9], edx
0x18003c045  jz      short locret_18003C04B
0x18003c047  test    al, 2
0x18003c049  jnz     short loc_18003C032
0x18003c04b  retn
```
