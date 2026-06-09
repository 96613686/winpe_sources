# mbbcx_p::CalculateAndBldMbbSnssai

- ea: `0x140047394`
- end: `0x14004744e`
- name: `mbbcx_p::CalculateAndBldMbbSnssai`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c834`
- `0x14001cbb0`
- `0x14001d05c`
- `0x140022bc4`
- `0x140047688`

## callees

- `0x140047394`

## pseudocode

```c
__int64 __fastcall mbbcx_p::CalculateAndBldMbbSnssai(int *a1, unsigned __int8 *a2)
{
  _BYTE *v3; // r9
  int v4; // eax
  int v5; // r11d
  unsigned __int8 v6; // cl
  char v7; // al

  if ( (*a1 & 1) != 0 )
  {
    if ( a2 )
    {
      v3 = a2 + 2;
      a2[1] = *((_BYTE *)a1 + 4);
    }
    else
    {
      v3 = 0;
    }
    v4 = *a1;
    v5 = a1[2];
    v6 = 2;
    if ( (v4 & 2) != 0 )
    {
      if ( v5 == 0xFFFFFF )
      {
        if ( !a2 )
          return (unsigned int)v6 + 1;
        *v3 = *((_BYTE *)a1 + 6);
LABEL_22:
        *a2 = v6;
        return (unsigned int)v6 + 1;
      }
      if ( a2 )
      {
        *(_WORD *)v3 = *((_WORD *)a1 + 4);
        v3[2] = *((_BYTE *)a1 + 10);
        v3[3] = *((_BYTE *)a1 + 6);
        v3 += 4;
      }
      if ( a1[3] == 0xFFFFFF )
      {
        v6 = 5;
LABEL_17:
        if ( a2 )
          goto LABEL_22;
        return (unsigned int)v6 + 1;
      }
      v6 = 8;
      if ( !a2 )
        return (unsigned int)v6 + 1;
      *(_WORD *)v3 = *((_WORD *)a1 + 6);
      v7 = *((_BYTE *)a1 + 14);
    }
    else
    {
      if ( v5 == 0xFFFFFF )
      {
        v6 = 1;
        goto LABEL_17;
      }
      v6 = 4;
      if ( !a2 )
        return (unsigned int)v6 + 1;
      *(_WORD *)v3 = *((_WORD *)a1 + 4);
      v7 = *((_BYTE *)a1 + 10);
    }
    v3[2] = v7;
    goto LABEL_22;
  }
  return 0;
}

```

## disassembly

```asm
0x140047394  mov     eax, [rcx]
0x140047396  mov     r8, rcx
0x140047399  test    al, 1
0x14004739b  jz      loc_14004744B
0x1400473a1  test    rdx, rdx
0x1400473a4  jz      short loc_1400473B2
0x1400473a6  mov     al, [rcx+4]
0x1400473a9  lea     r9, [rdx+2]
0x1400473ad  mov     [rdx+1], al
0x1400473b0  jmp     short loc_1400473B5
0x1400473b2  mov     r9, rdx
0x1400473b5  mov     eax, [rcx]
0x1400473b7  mov     r10d, 0FFFFFFh
0x1400473bd  mov     r11d, [rcx+8]
0x1400473c1  mov     cl, 2
0x1400473c3  test    cl, al
0x1400473c5  jnz     short loc_1400473E6
0x1400473c7  cmp     r11d, r10d
0x1400473ca  jnz     short loc_1400473D0
0x1400473cc  mov     cl, 1
0x1400473ce  jmp     short loc_140047423
0x1400473d0  mov     cl, 4
0x1400473d2  test    rdx, rdx
0x1400473d5  jz      short loc_140047444
0x1400473d7  movzx   eax, word ptr [r8+8]
0x1400473dc  mov     [r9], ax
0x1400473e0  mov     al, [r8+0Ah]
0x1400473e4  jmp     short loc_14004743E
0x1400473e6  cmp     r11d, r10d
0x1400473e9  jnz     short loc_1400473F9
0x1400473eb  test    rdx, rdx
0x1400473ee  jz      short loc_140047444
0x1400473f0  mov     al, [r8+6]
0x1400473f4  mov     [r9], al
0x1400473f7  jmp     short loc_140047442
0x1400473f9  test    rdx, rdx
0x1400473fc  jz      short loc_14004741B
0x1400473fe  movzx   eax, word ptr [r8+8]
0x140047403  mov     [r9], ax
0x140047407  mov     al, [r8+0Ah]
0x14004740b  mov     [r9+2], al
0x14004740f  mov     al, [r8+6]
0x140047413  mov     [r9+3], al
0x140047417  add     r9, 4
0x14004741b  cmp     [r8+0Ch], r10d
0x14004741f  jnz     short loc_14004742A
0x140047421  mov     cl, 5
0x140047423  test    rdx, rdx
0x140047426  jz      short loc_140047444
0x140047428  jmp     short loc_140047442
0x14004742a  mov     cl, 8
0x14004742c  test    rdx, rdx
0x14004742f  jz      short loc_140047444
0x140047431  movzx   eax, word ptr [r8+0Ch]
0x140047436  mov     [r9], ax
0x14004743a  mov     al, [r8+0Eh]
0x14004743e  mov     [r9+2], al
0x140047442  mov     [rdx], cl
0x140047444  movzx   eax, cl
0x140047447  inc     eax
0x140047449  retn
0x14004744b  xor     eax, eax
0x14004744d  retn
```
