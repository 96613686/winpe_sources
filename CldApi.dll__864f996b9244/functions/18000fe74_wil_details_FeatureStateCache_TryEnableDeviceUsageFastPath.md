# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x18000fe74`
- end: `0x18000feb0`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010104`

## callees

- `0x18000fe74`

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
  v4 = *Feature_57207774__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_57207774__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x18000fe74  sub     edx, 3
0x18000fe77  jz      short loc_18000FE84
0x18000fe79  cmp     edx, 1
0x18000fe7c  jnz     short locret_18000FEAF
0x18000fe7e  lea     r8d, [rdx+1Fh]
0x18000fe82  jmp     short loc_18000FE8A
0x18000fe84  mov     r8d, 10h
0x18000fe8a  mov     r9, cs:Feature_57207774__private_descriptor
0x18000fe91  mov     eax, [r9]
0x18000fe94  jmp     short loc_18000FEAB
0x18000fe96  mov     edx, eax
0x18000fe98  xor     edx, ecx
0x18000fe9a  test    dl, 1
0x18000fe9d  jnz     short locret_18000FEAF
0x18000fe9f  mov     edx, r8d
0x18000fea2  or      edx, eax
0x18000fea4  lock cmpxchg [r9], edx
0x18000fea9  jz      short locret_18000FEAF
0x18000feab  test    al, 2
0x18000fead  jnz     short loc_18000FE96
0x18000feaf  retn
```
