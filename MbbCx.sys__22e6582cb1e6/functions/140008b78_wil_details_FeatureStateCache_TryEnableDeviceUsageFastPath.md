# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140008b78`
- end: `0x140008bc7`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008bd0`

## callees

- `0x140008b78`

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
0x140008b78  mov     r10, r8
0x140008b7b  sub     edx, 3
0x140008b7e  jz      short loc_140008B8B
0x140008b80  cmp     edx, 1
0x140008b83  jnz     short locret_140008BC6
0x140008b85  lea     r9d, [rdx+1Fh]
0x140008b89  jmp     short loc_140008B91
0x140008b8b  mov     r9d, 10h
0x140008b91  cmp     byte ptr [r10+1Eh], 0
0x140008b96  mov     r8, [r8]
0x140008b99  jnz     short loc_140008BC2
0x140008b9b  cmp     byte ptr [r10+1Dh], 0
0x140008ba0  jnz     short loc_140008BC2
0x140008ba2  mov     eax, [r8]
0x140008ba5  jmp     short loc_140008BBC
0x140008ba7  mov     edx, eax
0x140008ba9  xor     edx, ecx
0x140008bab  test    dl, 1
0x140008bae  jnz     short locret_140008BC6
0x140008bb0  mov     edx, r9d
0x140008bb3  or      edx, eax
0x140008bb5  lock cmpxchg [r8], edx
0x140008bba  jz      short locret_140008BC6
0x140008bbc  test    al, 2
0x140008bbe  jnz     short loc_140008BA7
0x140008bc0  retn
0x140008bc2  lock or [r8], r9d
0x140008bc6  retn
```
