# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x14000293c`
- end: `0x140002989`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000223c`
- `0x140002aa8`
- `0x140025ba0`

## callees

- `0x14000293c`

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
0x14000293c  mov     r10, r8
0x14000293f  sub     edx, 3
0x140002942  jz      short loc_14000294F
0x140002944  cmp     edx, 1
0x140002947  jnz     short locret_140002988
0x140002949  lea     r9d, [rdx+1Fh]
0x14000294d  jmp     short loc_140002955
0x14000294f  mov     r9d, 10h
0x140002955  cmp     byte ptr [r10+1Eh], 0
0x14000295a  mov     r8, [r8]
0x14000295d  jnz     short loc_140002984
0x14000295f  cmp     byte ptr [r10+1Dh], 0
0x140002964  jnz     short loc_140002984
0x140002966  mov     eax, [r8]
0x140002969  test    al, 2
0x14000296b  jz      short locret_140002988
0x14000296d  mov     edx, eax
0x14000296f  xor     edx, ecx
0x140002971  test    dl, 1
0x140002974  jnz     short locret_140002988
0x140002976  mov     edx, r9d
0x140002979  or      edx, eax
0x14000297b  lock cmpxchg [r8], edx
0x140002980  jnz     short loc_140002969
0x140002982  retn
0x140002984  lock or [r8], r9d
0x140002988  retn
```
