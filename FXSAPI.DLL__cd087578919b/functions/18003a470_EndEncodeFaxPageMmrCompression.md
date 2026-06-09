# EndEncodeFaxPageMmrCompression

- ea: `0x18003a470`
- end: `0x18003a5e3`
- name: `EndEncodeFaxPageMmrCompression`
- size: `371`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180035d78`

## callees

- `0x18003a470`

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
0x18003a470  mov     edx, [rcx+630h]
0x18003a476  mov     r8, rcx
0x18003a479  mov     r11d, 1
0x18003a47f  mov     r9, [r8+638h]
0x18003a486  lea     eax, [rdx-4]
0x18003a489  and     eax, 7
0x18003a48c  sub     edx, eax
0x18003a48e  mov     eax, r11d
0x18003a491  lea     ecx, [rdx-0Ch]
0x18003a494  shl     eax, cl
0x18003a496  or      [r8+62Ch], eax
0x18003a49d  mov     edx, [r8+62Ch]
0x18003a4a4  mov     [r8+630h], ecx
0x18003a4ab  cmp     ecx, 10h
0x18003a4ae  ja      short loc_18003A4F4
0x18003a4b0  shr     edx, 18h
0x18003a4b3  mov     [r9], dl
0x18003a4b6  add     [r8+638h], r11
0x18003a4bd  mov     rcx, [r8+638h]
0x18003a4c4  mov     al, [r8+62Eh]
0x18003a4cb  mov     [rcx], al
0x18003a4cd  add     [r8+638h], r11
0x18003a4d4  shl     dword ptr [r8+62Ch], 10h
0x18003a4dc  mov     ecx, [r8+630h]
0x18003a4e3  mov     r9, [r8+638h]
0x18003a4ea  add     ecx, 10h
0x18003a4ed  mov     edx, [r8+62Ch]
0x18003a4f4  cmp     dword ptr [r8+354h], 3
0x18003a4fc  jnz     short loc_18003A557
0x18003a4fe  dec     ecx
0x18003a500  mov     [r8+62Ch], edx
0x18003a507  mov     [r8+630h], ecx
0x18003a50e  cmp     ecx, 10h
0x18003a511  ja      short loc_18003A557
0x18003a513  shr     edx, 18h
0x18003a516  mov     [r9], dl
0x18003a519  add     [r8+638h], r11
0x18003a520  mov     rcx, [r8+638h]
0x18003a527  mov     al, [r8+62Eh]
0x18003a52e  mov     [rcx], al
0x18003a530  add     [r8+638h], r11
0x18003a537  shl     dword ptr [r8+62Ch], 10h
0x18003a53f  mov     ecx, [r8+630h]
0x18003a546  mov     r9, [r8+638h]
0x18003a54d  add     ecx, 10h
0x18003a550  mov     edx, [r8+62Ch]
0x18003a557  mov     r10d, 20h ; ' '
0x18003a55d  cmp     ecx, r10d
0x18003a560  jnb     short loc_18003A5A2
0x18003a562  mov     eax, ecx
0x18003a564  shr     edx, 18h
0x18003a567  add     eax, 8
0x18003a56a  mov     [r8+630h], eax
0x18003a571  mov     [r9], dl
0x18003a574  mov     r9, [r8+638h]
0x18003a57b  mov     edx, [r8+62Ch]
0x18003a582  inc     r9
0x18003a585  shl     edx, 8
0x18003a588  mov     [r8+638h], r9
0x18003a58f  mov     [r8+62Ch], edx
0x18003a596  mov     eax, [r8+630h]
0x18003a59d  cmp     eax, r10d
0x18003a5a0  jb      short loc_18003A564
0x18003a5a2  mov     edx, [r8+638h]
0x18003a5a9  sub     edx, [r8+640h]
0x18003a5b0  mov     dword ptr [r8+62Ch], 0
0x18003a5bb  mov     [r8+630h], r10d
0x18003a5c2  mov     [r8+358h], edx
0x18003a5c9  cmp     ecx, r10d
0x18003a5cc  jnb     short loc_18003A5DF
0x18003a5ce  inc     edx
0x18003a5d0  add     ecx, 8
0x18003a5d3  cmp     ecx, r10d
0x18003a5d6  jb      short loc_18003A5CE
0x18003a5d8  mov     [r8+358h], edx
0x18003a5df  mov     eax, r11d
0x18003a5e2  retn
```
