# CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)

- ea: `0x180007910`
- end: `0x180007975`
- name: `??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a20`
- `0x180007b70`
- `0x1800089d0`
- `0x180008d60`
- `0x180008e60`
- `0x180008f70`
- `0x180009070`
- `0x180009180`
- `0x1800094c0`
- `0x180009770`
- `0x180009960`
- `0x180009b10`

## callees

- `0x180007910`

## pseudocode

```c
__int64 __fastcall CTDynArray<IASFReadWriteTracker *,20>::operator[](__int64 a1, unsigned int a2)
{
  __int64 v2; // r10
  __int64 i; // r8
  unsigned int v5; // ecx
  unsigned int v6; // edx

  v2 = 0;
  if ( a2 < *(_DWORD *)(a1 + 216) )
  {
    for ( i = a1; i; i = *(_QWORD *)(i + 192) )
    {
      v5 = *(_DWORD *)(i + 8);
      if ( a2 >= v5 && a2 < v5 + 20 )
      {
        v6 = a2 - v5;
        if ( (*(_BYTE *)(((unsigned __int64)v6 >> 3) + i + 24)
            & (unsigned __int8)CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::s_bSingleBitMasks[v6 & 7]) != 0 )
          return *(_QWORD *)(i + 8LL * v6 + 32);
        break;
      }
    }
    if ( (*(_BYTE *)(a1 + 12) & 1) != 0 )
      return *(_QWORD *)(a1 + 16);
  }
  return v2;
}

```

## disassembly

```asm
0x180007910  xor     r10d, r10d
0x180007913  mov     r9, rcx
0x180007916  cmp     edx, [rcx+0D8h]
0x18000791c  jnb     short loc_180007971
0x18000791e  mov     r8, rcx
0x180007921  test    r8, r8
0x180007924  jz      short loc_180007966
0x180007926  mov     ecx, [r8+8]
0x18000792a  cmp     edx, ecx
0x18000792c  jb      short loc_180007935
0x18000792e  lea     eax, [rcx+14h]
0x180007931  cmp     edx, eax
0x180007933  jb      short loc_18000793E
0x180007935  mov     r8, [r8+0C0h]
0x18000793c  jmp     short loc_180007921
0x18000793e  sub     edx, ecx
0x180007940  mov     ecx, edx
0x180007942  mov     eax, edx
0x180007944  and     ecx, 7
0x180007947  shr     rax, 3
0x18000794b  mov     r11d, edx
0x18000794e  lea     rdx, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::s_bSingleBitMasks
0x180007955  mov     al, [rax+r8+18h]
0x18000795a  test    [rcx+rdx], al
0x18000795d  jz      short loc_180007966
0x18000795f  mov     r10, [r8+r11*8+20h]
0x180007964  jmp     short loc_180007971
0x180007966  test    byte ptr [r9+0Ch], 1
0x18000796b  jz      short loc_180007971
0x18000796d  mov     r10, [r9+10h]
0x180007971  mov     rax, r10
0x180007974  retn
```
