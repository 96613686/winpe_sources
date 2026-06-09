# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140001edc`
- end: `0x140001f16`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400015c0`

## callees

- `0x140001edc`

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
  v4 = *wil_details_featureDescriptors_a[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(wil_details_featureDescriptors_a[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x140001edc  sub     edx, 3
0x140001edf  jz      short loc_140001EEC
0x140001ee1  cmp     edx, 1
0x140001ee4  jnz     short locret_140001F15
0x140001ee6  lea     r8d, [rdx+1Fh]
0x140001eea  jmp     short loc_140001EF2
0x140001eec  mov     r8d, 10h
0x140001ef2  mov     r9, cs:wil_details_featureDescriptors_a
0x140001ef9  mov     eax, [r9]
0x140001efc  test    al, 2
0x140001efe  jz      short locret_140001F15
0x140001f00  mov     edx, eax
0x140001f02  xor     edx, ecx
0x140001f04  test    dl, 1
0x140001f07  jnz     short locret_140001F15
0x140001f09  mov     edx, r8d
0x140001f0c  or      edx, eax
0x140001f0e  lock cmpxchg [r9], edx
0x140001f13  jnz     short loc_140001EFC
0x140001f15  retn
```
