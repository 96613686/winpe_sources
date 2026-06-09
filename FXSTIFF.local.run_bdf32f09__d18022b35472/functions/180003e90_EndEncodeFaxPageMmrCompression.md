# EndEncodeFaxPageMmrCompression

- ea: `0x180003e90`
- end: `0x180004003`
- name: `EndEncodeFaxPageMmrCompression`
- size: `371`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800044f0`
- `0x180008230`

## callees

- `0x180003e90`

## pseudocode

```c
__int64 __fastcall EndEncodeFaxPageMmrCompression(__int64 a1)
{
  _BYTE *v2; // r9
  unsigned int v3; // ecx
  int v4; // edx
  unsigned int i; // eax
  int v6; // edx

  v2 = *(_BYTE **)(a1 + 1592);
  v3 = *(_DWORD *)(a1 + 1584) - (((unsigned __int8)*(_DWORD *)(a1 + 1584) - 4) & 7) - 12;
  *(_DWORD *)(a1 + 1580) |= 1 << v3;
  v4 = *(_DWORD *)(a1 + 1580);
  *(_DWORD *)(a1 + 1584) = v3;
  if ( v3 <= 0x10 )
  {
    *v2 = HIBYTE(v4);
    *(_BYTE *)++*(_QWORD *)(a1 + 1592) = *(_BYTE *)(a1 + 1582);
    ++*(_QWORD *)(a1 + 1592);
    *(_DWORD *)(a1 + 1580) <<= 16;
    v2 = *(_BYTE **)(a1 + 1592);
    v3 = *(_DWORD *)(a1 + 1584) + 16;
    v4 = *(_DWORD *)(a1 + 1580);
  }
  if ( *(_DWORD *)(a1 + 852) == 3 )
  {
    --v3;
    *(_DWORD *)(a1 + 1580) = v4;
    *(_DWORD *)(a1 + 1584) = v3;
    if ( v3 <= 0x10 )
    {
      *v2 = HIBYTE(v4);
      *(_BYTE *)++*(_QWORD *)(a1 + 1592) = *(_BYTE *)(a1 + 1582);
      ++*(_QWORD *)(a1 + 1592);
      *(_DWORD *)(a1 + 1580) <<= 16;
      v2 = *(_BYTE **)(a1 + 1592);
      v3 = *(_DWORD *)(a1 + 1584) + 16;
      v4 = *(_DWORD *)(a1 + 1580);
    }
  }
  if ( v3 < 0x20 )
  {
    for ( i = v3; i < 0x20; i = *(_DWORD *)(a1 + 1584) )
    {
      *(_DWORD *)(a1 + 1584) = i + 8;
      *v2 = HIBYTE(v4);
      v2 = (_BYTE *)(*(_QWORD *)(a1 + 1592) + 1LL);
      v4 = *(_DWORD *)(a1 + 1580) << 8;
      *(_QWORD *)(a1 + 1592) = v2;
      *(_DWORD *)(a1 + 1580) = v4;
    }
  }
  v6 = *(_DWORD *)(a1 + 1592) - *(_DWORD *)(a1 + 1600);
  *(_DWORD *)(a1 + 1580) = 0;
  *(_DWORD *)(a1 + 1584) = 32;
  *(_DWORD *)(a1 + 856) = v6;
  if ( v3 < 0x20 )
  {
    do
    {
      ++v6;
      v3 += 8;
    }
    while ( v3 < 0x20 );
    *(_DWORD *)(a1 + 856) = v6;
  }
  return 1;
}

```

## disassembly

```asm
0x180003e90  mov     edx, [rcx+630h]
0x180003e96  mov     r8, rcx
0x180003e99  mov     r11d, 1
0x180003e9f  mov     r9, [r8+638h]
0x180003ea6  lea     eax, [rdx-4]
0x180003ea9  and     eax, 7
0x180003eac  sub     edx, eax
0x180003eae  mov     eax, r11d
0x180003eb1  lea     ecx, [rdx-0Ch]
0x180003eb4  shl     eax, cl
0x180003eb6  or      [r8+62Ch], eax
0x180003ebd  mov     edx, [r8+62Ch]
0x180003ec4  mov     [r8+630h], ecx
0x180003ecb  cmp     ecx, 10h
0x180003ece  ja      short loc_180003F14
0x180003ed0  shr     edx, 18h
0x180003ed3  mov     [r9], dl
0x180003ed6  add     [r8+638h], r11
0x180003edd  mov     rcx, [r8+638h]
0x180003ee4  mov     al, [r8+62Eh]
0x180003eeb  mov     [rcx], al
0x180003eed  add     [r8+638h], r11
0x180003ef4  shl     dword ptr [r8+62Ch], 10h
0x180003efc  mov     ecx, [r8+630h]
0x180003f03  mov     r9, [r8+638h]
0x180003f0a  add     ecx, 10h
0x180003f0d  mov     edx, [r8+62Ch]
0x180003f14  cmp     dword ptr [r8+354h], 3
0x180003f1c  jnz     short loc_180003F77
0x180003f1e  dec     ecx
0x180003f20  mov     [r8+62Ch], edx
0x180003f27  mov     [r8+630h], ecx
0x180003f2e  cmp     ecx, 10h
0x180003f31  ja      short loc_180003F77
0x180003f33  shr     edx, 18h
0x180003f36  mov     [r9], dl
0x180003f39  add     [r8+638h], r11
0x180003f40  mov     rcx, [r8+638h]
0x180003f47  mov     al, [r8+62Eh]
0x180003f4e  mov     [rcx], al
0x180003f50  add     [r8+638h], r11
0x180003f57  shl     dword ptr [r8+62Ch], 10h
0x180003f5f  mov     ecx, [r8+630h]
0x180003f66  mov     r9, [r8+638h]
0x180003f6d  add     ecx, 10h
0x180003f70  mov     edx, [r8+62Ch]
0x180003f77  mov     r10d, 20h ; ' '
0x180003f7d  cmp     ecx, r10d
0x180003f80  jnb     short loc_180003FC2
0x180003f82  mov     eax, ecx
0x180003f84  shr     edx, 18h
0x180003f87  add     eax, 8
0x180003f8a  mov     [r8+630h], eax
0x180003f91  mov     [r9], dl
0x180003f94  mov     r9, [r8+638h]
0x180003f9b  mov     edx, [r8+62Ch]
0x180003fa2  inc     r9
0x180003fa5  shl     edx, 8
0x180003fa8  mov     [r8+638h], r9
0x180003faf  mov     [r8+62Ch], edx
0x180003fb6  mov     eax, [r8+630h]
0x180003fbd  cmp     eax, r10d
0x180003fc0  jb      short loc_180003F84
0x180003fc2  mov     edx, [r8+638h]
0x180003fc9  sub     edx, [r8+640h]
0x180003fd0  mov     dword ptr [r8+62Ch], 0
0x180003fdb  mov     [r8+630h], r10d
0x180003fe2  mov     [r8+358h], edx
0x180003fe9  cmp     ecx, r10d
0x180003fec  jnb     short loc_180003FFF
0x180003fee  inc     edx
0x180003ff0  add     ecx, 8
0x180003ff3  cmp     ecx, r10d
0x180003ff6  jb      short loc_180003FEE
0x180003ff8  mov     [r8+358h], edx
0x180003fff  mov     eax, r11d
0x180004002  retn
```
