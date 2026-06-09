# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140003edc`
- end: `0x140003f18`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003f20`

## callees

- `0x140003edc`

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
  v4 = *Feature_56664216__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_56664216__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x140003edc  sub     edx, 3
0x140003edf  jz      short loc_140003EEC
0x140003ee1  cmp     edx, 1
0x140003ee4  jnz     short locret_140003F17
0x140003ee6  lea     r8d, [rdx+1Fh]
0x140003eea  jmp     short loc_140003EF2
0x140003eec  mov     r8d, 10h
0x140003ef2  mov     r9, cs:Feature_56664216__private_descriptor
0x140003ef9  mov     eax, [r9]
0x140003efc  jmp     short loc_140003F13
0x140003efe  mov     edx, eax
0x140003f00  xor     edx, ecx
0x140003f02  test    dl, 1
0x140003f05  jnz     short locret_140003F17
0x140003f07  mov     edx, r8d
0x140003f0a  or      edx, eax
0x140003f0c  lock cmpxchg [r9], edx
0x140003f11  jz      short locret_140003F17
0x140003f13  test    al, 2
0x140003f15  jnz     short loc_140003EFE
0x140003f17  retn
```
