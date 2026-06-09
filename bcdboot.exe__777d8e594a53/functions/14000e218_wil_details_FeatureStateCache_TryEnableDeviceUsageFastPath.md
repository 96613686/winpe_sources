# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x14000e218`
- end: `0x14000e266`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `78`
- prototype: `void __fastcall(unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000e4b8`

## callees

- `0x14000e218`

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
0x14000e218  mov     r10, r8
0x14000e21b  sub     edx, 3
0x14000e21e  jz      short loc_14000E22B
0x14000e220  cmp     edx, 1
0x14000e223  jnz     short locret_14000E265
0x14000e225  lea     r9d, [rdx+1Fh]
0x14000e229  jmp     short loc_14000E231
0x14000e22b  mov     r9d, 10h
0x14000e231  cmp     byte ptr [r10+1Eh], 0
0x14000e236  mov     r8, [r8]
0x14000e239  jnz     short loc_14000E261
0x14000e23b  cmp     byte ptr [r10+1Dh], 0
0x14000e240  jnz     short loc_14000E261
0x14000e242  mov     eax, [r8]
0x14000e245  jmp     short loc_14000E25C
0x14000e247  mov     edx, eax
0x14000e249  xor     edx, ecx
0x14000e24b  test    dl, 1
0x14000e24e  jnz     short locret_14000E265
0x14000e250  mov     edx, r9d
0x14000e253  or      edx, eax
0x14000e255  lock cmpxchg [r8], edx
0x14000e25a  jz      short locret_14000E265
0x14000e25c  test    al, 2
0x14000e25e  jnz     short loc_14000E247
0x14000e260  retn
0x14000e261  lock or [r8], r9d
0x14000e265  retn
```
