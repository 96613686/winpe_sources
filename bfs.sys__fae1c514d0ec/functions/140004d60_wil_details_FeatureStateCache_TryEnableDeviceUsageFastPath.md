# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140004d60`
- end: `0x140004dad`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002350`
- `0x140003690`

## callees

- `0x140004d60`

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
0x140004d60  mov     r10, r8
0x140004d63  sub     edx, 3
0x140004d66  jz      short loc_140004D73
0x140004d68  cmp     edx, 1
0x140004d6b  jnz     short locret_140004DAC
0x140004d6d  lea     r9d, [rdx+1Fh]
0x140004d71  jmp     short loc_140004D79
0x140004d73  mov     r9d, 10h
0x140004d79  cmp     byte ptr [r10+1Eh], 0
0x140004d7e  mov     r8, [r8]
0x140004d81  jnz     short loc_140004DA8
0x140004d83  cmp     byte ptr [r10+1Dh], 0
0x140004d88  jnz     short loc_140004DA8
0x140004d8a  mov     eax, [r8]
0x140004d8d  test    al, 2
0x140004d8f  jz      short locret_140004DAC
0x140004d91  mov     edx, eax
0x140004d93  xor     edx, ecx
0x140004d95  test    dl, 1
0x140004d98  jnz     short locret_140004DAC
0x140004d9a  mov     edx, r9d
0x140004d9d  or      edx, eax
0x140004d9f  lock cmpxchg [r8], edx
0x140004da4  jnz     short loc_140004D8D
0x140004da6  retn
0x140004da8  lock or [r8], r9d
0x140004dac  retn
```
