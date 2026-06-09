# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x18000b2fc`
- end: `0x18000b348`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `76`
- prototype: `void __fastcall(unsigned __int8, int, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a4e0`
- `0x18000b4a8`

## callees

- `0x18000b2fc`

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
0x18000b2fc  mov     r10, r8
0x18000b2ff  sub     edx, 3
0x18000b302  jz      short loc_18000B30F
0x18000b304  cmp     edx, 1
0x18000b307  jnz     short locret_18000B347
0x18000b309  lea     r9d, [rdx+1Fh]
0x18000b30d  jmp     short loc_18000B315
0x18000b30f  mov     r9d, 10h
0x18000b315  cmp     byte ptr [r10+1Eh], 0
0x18000b31a  mov     r8, [r8]
0x18000b31d  jnz     short loc_18000B343
0x18000b31f  cmp     byte ptr [r10+1Dh], 0
0x18000b324  jnz     short loc_18000B343
0x18000b326  mov     eax, [r8]
0x18000b329  test    al, 2
0x18000b32b  jz      short locret_18000B347
0x18000b32d  mov     edx, eax
0x18000b32f  xor     edx, ecx
0x18000b331  test    dl, 1
0x18000b334  jnz     short locret_18000B347
0x18000b336  mov     edx, r9d
0x18000b339  or      edx, eax
0x18000b33b  lock cmpxchg [r8], edx
0x18000b340  jnz     short loc_18000B329
0x18000b342  retn
0x18000b343  lock or [r8], r9d
0x18000b347  retn
```
