# CTPtrArray<CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION,20>::operator[](ulong)

- ea: `0x180015184`
- end: `0x180015217`
- name: `??A?$CTPtrArray@U_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@$0BE@@@QEBAPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@K@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015058`
- `0x1800155a0`

## callees

- `0x180015184`

## pseudocode

```c
__int64 __fastcall CTPtrArray<CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION,20>::operator[](
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r8
  __int64 i; // r9
  int v6; // edx
  unsigned int v7; // ecx
  __int64 v8; // r10
  int v9; // ecx
  __int64 v10; // rax

  v2 = 0;
  if ( a2 >= *(_DWORD *)(a1 + 216) )
    goto LABEL_12;
  for ( i = a1; ; i = *(_QWORD *)(i + 192) )
  {
    v6 = 1;
    if ( !i )
      break;
    v7 = *(_DWORD *)(i + 8);
    if ( a2 >= v7 && a2 < v7 + 20 )
    {
      v8 = a2 - v7;
      if ( (*(_BYTE *)(((unsigned __int64)(unsigned int)v8 >> 3) + i + 24)
          & *((_BYTE *)&CTSparseBlock<unsigned long,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::s_bSingleBitMasks
            + (v8 & 7))) != 0 )
      {
        v2 = *(_QWORD *)(i + 8 * v8 + 32);
        v9 = 0;
        goto LABEL_9;
      }
      break;
    }
  }
  v9 = -2147467259;
  if ( (*(_BYTE *)(a1 + 12) & 1) != 0 )
  {
    v2 = *(_QWORD *)(a1 + 16);
    return v2 & -(__int64)(v6 != 0);
  }
LABEL_9:
  v10 = 0;
  if ( v9 >= 0 )
    v10 = v2;
  v2 = v10;
  if ( v9 < 0 )
LABEL_12:
    v6 = 0;
  return v2 & -(__int64)(v6 != 0);
}

```

## disassembly

```asm
0x180015184  mov     [rsp+arg_0], rbx
0x180015189  xor     r8d, r8d
0x18001518c  mov     r10d, edx
0x18001518f  mov     r11, rcx
0x180015192  cmp     edx, [rcx+0D8h]
0x180015198  jnb     short loc_1800151F6
0x18001519a  mov     r9, rcx
0x18001519d  mov     edx, 1
0x1800151a2  test    r9, r9
0x1800151a5  jz      short loc_180015206
0x1800151a7  mov     ecx, [r9+8]
0x1800151ab  cmp     r10d, ecx
0x1800151ae  jb      short loc_1800151B8
0x1800151b0  lea     eax, [rcx+14h]
0x1800151b3  cmp     r10d, eax
0x1800151b6  jb      short loc_1800151C1
0x1800151b8  mov     r9, [r9+0C0h]
0x1800151bf  jmp     short loc_18001519D
0x1800151c1  sub     r10d, ecx
0x1800151c4  lea     rbx, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::s_bSingleBitMasks
0x1800151cb  mov     ecx, r10d
0x1800151ce  mov     eax, r10d
0x1800151d1  shr     rax, 3
0x1800151d5  and     ecx, 7
0x1800151d8  mov     al, [rax+r9+18h]
0x1800151dd  test    [rcx+rbx], al
0x1800151e0  jz      short loc_180015206
0x1800151e2  mov     r8, [r9+r10*8+20h]
0x1800151e7  xor     ecx, ecx
0x1800151e9  xor     eax, eax
0x1800151eb  test    ecx, ecx
0x1800151ed  cmovns  rax, r8
0x1800151f1  mov     r8, rax
0x1800151f4  jns     short loc_1800151F8
0x1800151f6  xor     edx, edx
0x1800151f8  mov     rbx, [rsp+arg_0]
0x1800151fd  neg     edx
0x1800151ff  sbb     rax, rax
0x180015202  and     rax, r8
0x180015205  retn
0x180015206  mov     ecx, 80004005h
0x18001520b  test    [r11+0Ch], dl
0x18001520f  jz      short loc_1800151E9
0x180015211  mov     r8, [r11+10h]
0x180015215  jmp     short loc_1800151F8
```
