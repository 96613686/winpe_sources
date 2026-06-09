# EndEncodeFaxPageMmrCompression

- ea: `0x180003ed4`
- end: `0x180004047`
- name: `EndEncodeFaxPageMmrCompression`
- size: `371`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004540`
- `0x180008590`

## callees

- `0x180003ed4`

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
0x180003ed4  mov     edx, [rcx+630h]
0x180003eda  mov     r8, rcx
0x180003edd  mov     r11d, 1
0x180003ee3  mov     r9, [r8+638h]
0x180003eea  lea     eax, [rdx-4]
0x180003eed  and     eax, 7
0x180003ef0  sub     edx, eax
0x180003ef2  mov     eax, r11d
0x180003ef5  lea     ecx, [rdx-0Ch]
0x180003ef8  shl     eax, cl
0x180003efa  or      [r8+62Ch], eax
0x180003f01  mov     edx, [r8+62Ch]
0x180003f08  mov     [r8+630h], ecx
0x180003f0f  cmp     ecx, 10h
0x180003f12  ja      short loc_180003F58
0x180003f14  shr     edx, 18h
0x180003f17  mov     [r9], dl
0x180003f1a  add     [r8+638h], r11
0x180003f21  mov     rcx, [r8+638h]
0x180003f28  mov     al, [r8+62Eh]
0x180003f2f  mov     [rcx], al
0x180003f31  add     [r8+638h], r11
0x180003f38  shl     dword ptr [r8+62Ch], 10h
0x180003f40  mov     ecx, [r8+630h]
0x180003f47  mov     r9, [r8+638h]
0x180003f4e  add     ecx, 10h
0x180003f51  mov     edx, [r8+62Ch]
0x180003f58  cmp     dword ptr [r8+354h], 3
0x180003f60  jnz     short loc_180003FBB
0x180003f62  dec     ecx
0x180003f64  mov     [r8+62Ch], edx
0x180003f6b  mov     [r8+630h], ecx
0x180003f72  cmp     ecx, 10h
0x180003f75  ja      short loc_180003FBB
0x180003f77  shr     edx, 18h
0x180003f7a  mov     [r9], dl
0x180003f7d  add     [r8+638h], r11
0x180003f84  mov     rcx, [r8+638h]
0x180003f8b  mov     al, [r8+62Eh]
0x180003f92  mov     [rcx], al
0x180003f94  add     [r8+638h], r11
0x180003f9b  shl     dword ptr [r8+62Ch], 10h
0x180003fa3  mov     ecx, [r8+630h]
0x180003faa  mov     r9, [r8+638h]
0x180003fb1  add     ecx, 10h
0x180003fb4  mov     edx, [r8+62Ch]
0x180003fbb  mov     r10d, 20h ; ' '
0x180003fc1  cmp     ecx, r10d
0x180003fc4  jnb     short loc_180004006
0x180003fc6  mov     eax, ecx
0x180003fc8  shr     edx, 18h
0x180003fcb  add     eax, 8
0x180003fce  mov     [r8+630h], eax
0x180003fd5  mov     [r9], dl
0x180003fd8  mov     r9, [r8+638h]
0x180003fdf  mov     edx, [r8+62Ch]
0x180003fe6  inc     r9
0x180003fe9  shl     edx, 8
0x180003fec  mov     [r8+638h], r9
0x180003ff3  mov     [r8+62Ch], edx
0x180003ffa  mov     eax, [r8+630h]
0x180004001  cmp     eax, r10d
0x180004004  jb      short loc_180003FC8
0x180004006  mov     edx, [r8+638h]
0x18000400d  sub     edx, [r8+640h]
0x180004014  mov     dword ptr [r8+62Ch], 0
0x18000401f  mov     [r8+630h], r10d
0x180004026  mov     [r8+358h], edx
0x18000402d  cmp     ecx, r10d
0x180004030  jnb     short loc_180004043
0x180004032  inc     edx
0x180004034  add     ecx, 8
0x180004037  cmp     ecx, r10d
0x18000403a  jb      short loc_180004032
0x18000403c  mov     [r8+358h], edx
0x180004043  mov     eax, r11d
0x180004046  retn
```
