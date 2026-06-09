# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180007eb8`
- end: `0x180007f06`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008064`

## callees

- `0x180007eb8`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(unsigned __int8 a1, int a2, __int64 a3)
{
  int v4; // edx
  unsigned int v5; // r9d
  volatile signed __int32 *v6; // r8
  signed __int32 v7; // eax
  signed __int32 v8; // ett

  v4 = a2 - 3;
  if ( v4 )
  {
    if ( v4 != 1 )
      return;
    v5 = 32;
  }
  else
  {
    v5 = 16;
  }
  v6 = *(volatile signed __int32 **)a3;
  if ( *(_BYTE *)(a3 + 30) || *(_BYTE *)(a3 + 29) )
  {
    _InterlockedOr(v6, v5);
  }
  else
  {
    v7 = *v6;
    do
    {
      if ( (v7 & 2) == 0 )
        break;
      if ( ((a1 ^ (unsigned __int8)v7) & 1) != 0 )
        break;
      v8 = v7;
      v7 = _InterlockedCompareExchange(v6, v7 | v5, v7);
    }
    while ( v8 != v7 );
  }
}

```

## disassembly

```asm
0x180007eb8  mov     r10, r8
0x180007ebb  sub     edx, 3
0x180007ebe  jz      short loc_180007ECB
0x180007ec0  cmp     edx, 1
0x180007ec3  jnz     short locret_180007F05
0x180007ec5  lea     r9d, [rdx+1Fh]
0x180007ec9  jmp     short loc_180007ED1
0x180007ecb  mov     r9d, 10h
0x180007ed1  cmp     byte ptr [r10+1Eh], 0
0x180007ed6  mov     r8, [r8]
0x180007ed9  jnz     short loc_180007F01
0x180007edb  cmp     byte ptr [r10+1Dh], 0
0x180007ee0  jnz     short loc_180007F01
0x180007ee2  mov     eax, [r8]
0x180007ee5  jmp     short loc_180007EFC
0x180007ee7  mov     edx, eax
0x180007ee9  xor     edx, ecx
0x180007eeb  test    dl, 1
0x180007eee  jnz     short locret_180007F05
0x180007ef0  mov     edx, r9d
0x180007ef3  or      edx, eax
0x180007ef5  lock cmpxchg [r8], edx
0x180007efa  jz      short locret_180007F05
0x180007efc  test    al, 2
0x180007efe  jnz     short loc_180007EE7
0x180007f00  retn
0x180007f01  lock or [r8], r9d
0x180007f05  retn
```
