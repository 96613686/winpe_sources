# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140004b90`
- end: `0x140004bdd`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002760`
- `0x140003560`

## callees

- `0x140004b90`

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
0x140004b90  mov     r10, r8
0x140004b93  sub     edx, 3
0x140004b96  jz      short loc_140004BA3
0x140004b98  cmp     edx, 1
0x140004b9b  jnz     short locret_140004BDC
0x140004b9d  lea     r9d, [rdx+1Fh]
0x140004ba1  jmp     short loc_140004BA9
0x140004ba3  mov     r9d, 10h
0x140004ba9  cmp     byte ptr [r10+1Eh], 0
0x140004bae  mov     r8, [r8]
0x140004bb1  jnz     short loc_140004BD8
0x140004bb3  cmp     byte ptr [r10+1Dh], 0
0x140004bb8  jnz     short loc_140004BD8
0x140004bba  mov     eax, [r8]
0x140004bbd  test    al, 2
0x140004bbf  jz      short locret_140004BDC
0x140004bc1  mov     edx, eax
0x140004bc3  xor     edx, ecx
0x140004bc5  test    dl, 1
0x140004bc8  jnz     short locret_140004BDC
0x140004bca  mov     edx, r9d
0x140004bcd  or      edx, eax
0x140004bcf  lock cmpxchg [r8], edx
0x140004bd4  jnz     short loc_140004BBD
0x140004bd6  retn
0x140004bd8  lock or [r8], r9d
0x140004bdc  retn
```
