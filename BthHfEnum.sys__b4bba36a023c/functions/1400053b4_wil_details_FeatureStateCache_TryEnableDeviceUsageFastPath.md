# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x1400053b4`
- end: `0x140005403`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005524`

## callees

- `0x1400053b4`

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
0x1400053b4  mov     r10, r8
0x1400053b7  sub     edx, 3
0x1400053ba  jz      short loc_1400053C7
0x1400053bc  cmp     edx, 1
0x1400053bf  jnz     short locret_140005402
0x1400053c1  lea     r9d, [rdx+1Fh]
0x1400053c5  jmp     short loc_1400053CD
0x1400053c7  mov     r9d, 10h
0x1400053cd  cmp     byte ptr [r10+1Eh], 0
0x1400053d2  mov     r8, [r8]
0x1400053d5  jnz     short loc_1400053FE
0x1400053d7  cmp     byte ptr [r10+1Dh], 0
0x1400053dc  jnz     short loc_1400053FE
0x1400053de  mov     eax, [r8]
0x1400053e1  jmp     short loc_1400053F8
0x1400053e3  mov     edx, eax
0x1400053e5  xor     edx, ecx
0x1400053e7  test    dl, 1
0x1400053ea  jnz     short locret_140005402
0x1400053ec  mov     edx, r9d
0x1400053ef  or      edx, eax
0x1400053f1  lock cmpxchg [r8], edx
0x1400053f6  jz      short locret_140005402
0x1400053f8  test    al, 2
0x1400053fa  jnz     short loc_1400053E3
0x1400053fc  retn
0x1400053fe  lock or [r8], r9d
0x140005402  retn
```
