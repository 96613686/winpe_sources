# computeJD

- ea: `0x18006bf88`
- end: `0x18006c129`
- name: `computeJD`
- size: `417`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006bedc`
- `0x1800722a0`
- `0x1800790d0`
- `0x18007b7ec`
- `0x18007c0d4`
- `0x180091530`
- `0x180092600`
- `0x180092de0`

## callees

- `0x18006bf88`

## pseudocode

```c
__int64 __fastcall computeJD(__int64 a1)
{
  int v2; // ecx
  __int64 result; // rax
  int v4; // r9d
  int v5; // edi
  int v6; // ebx
  int v7; // r8d
  int v8; // ecx
  int v9; // r10d
  bool v10; // zf
  __int64 v11; // r8
  __int64 v12; // rdx

  if ( *(_BYTE *)(a1 + 40) )
    return result;
  if ( *(_BYTE *)(a1 + 41) )
  {
    v2 = *(_DWORD *)(a1 + 8);
    result = (unsigned int)(v2 + 4713);
    if ( (unsigned int)result > 0x3978 )
    {
LABEL_14:
      *(_OWORD *)a1 = 0;
      *(_OWORD *)(a1 + 16) = 0;
      *(_OWORD *)(a1 + 32) = 0;
      *(_DWORD *)(a1 + 44) = 2;
      return result;
    }
    v4 = *(_DWORD *)(a1 + 12);
    v5 = *(_DWORD *)(a1 + 16);
  }
  else
  {
    v5 = 1;
    v2 = 2000;
    v4 = 1;
  }
  v6 = *(_DWORD *)(a1 + 44);
  if ( (v6 & 1) != 0 )
    goto LABEL_14;
  v7 = v2 - 1;
  *(_BYTE *)(a1 + 40) = 1;
  if ( v4 > 2 )
    v7 = v2;
  v8 = v4 + 12;
  v9 = (v7 + 4800) / 100;
  if ( v4 > 2 )
    v8 = v4;
  result = (unsigned int)(v5 + 36525 * (v7 + 4716) / 100 + 306001 * (v8 + 1) / 10000 + v9 / 4 - v9 + 38);
  v10 = *(_BYTE *)(a1 + 42) == 0;
  v11 = (unsigned int)(int)(((double)(v5 + 36525 * (v7 + 4716) / 100 + 306001 * (v8 + 1) / 10000 + v9 / 4 - v9 + 38)
                           - 1524.5)
                          * 86400000.0);
  *(_QWORD *)a1 = v11;
  if ( !v10 )
  {
    result = (unsigned int)(60000 * (*(_DWORD *)(a1 + 24) + 60 * *(_DWORD *)(a1 + 20)));
    v12 = (unsigned int)(int)(*(double *)(a1 + 32) * 1000.0 + 0.5) + v11 + (int)result;
    v10 = *(_DWORD *)(a1 + 28) == 0;
    *(_QWORD *)a1 = v12;
    if ( !v10 )
    {
      result = (unsigned int)(60000 * *(_DWORD *)(a1 + 28));
      *(_WORD *)(a1 + 41) = 0;
      *(_DWORD *)(a1 + 28) = 0;
      *(_QWORD *)a1 = v12 - (int)result;
      *(_DWORD *)(a1 + 44) = v6 & 0xFFFFFFE7 | 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006bf88  mov     [rsp+arg_0], rbx
0x18006bf8d  mov     [rsp+arg_8], rdi
0x18006bf92  cmp     byte ptr [rcx+28h], 0
0x18006bf96  mov     r11, rcx
0x18006bf99  jnz     loc_18006C11E
0x18006bf9f  cmp     byte ptr [rcx+29h], 0
0x18006bfa3  jz      short loc_18006BFC3
0x18006bfa5  mov     ecx, [rcx+8]
0x18006bfa8  lea     eax, [rcx+1269h]
0x18006bfae  cmp     eax, 3978h
0x18006bfb3  ja      loc_18006C105
0x18006bfb9  mov     r9d, [r11+0Ch]
0x18006bfbd  mov     edi, [r11+10h]
0x18006bfc1  jmp     short loc_18006BFD0
0x18006bfc3  mov     edi, 1
0x18006bfc8  mov     ecx, 7D0h
0x18006bfcd  mov     r9d, edi
0x18006bfd0  mov     ebx, [r11+2Ch]
0x18006bfd4  test    bl, 1
0x18006bfd7  jnz     loc_18006C105
0x18006bfdd  lea     r8d, [rcx-1]
0x18006bfe1  mov     byte ptr [r11+28h], 1
0x18006bfe6  cmp     r9d, 2
0x18006bfea  mov     eax, 51EB851Fh
0x18006bfef  cmovg   r8d, ecx
0x18006bff3  lea     ecx, [r8+12C0h]
0x18006bffa  imul    ecx
0x18006bffc  lea     ecx, [r9+0Ch]
0x18006c000  mov     r10d, edx
0x18006c003  sar     r10d, 5
0x18006c007  mov     eax, r10d
0x18006c00a  shr     eax, 1Fh
0x18006c00d  add     r10d, eax
0x18006c010  mov     eax, 68DB8BADh
0x18006c015  cmp     r9d, 2
0x18006c019  cmovg   ecx, r9d
0x18006c01d  inc     ecx
0x18006c01f  imul    ecx, 4AB51h
0x18006c025  imul    ecx
0x18006c027  mov     eax, 51EB851Fh
0x18006c02c  mov     r9d, edx
0x18006c02f  sar     r9d, 0Ch
0x18006c033  mov     ecx, r9d
0x18006c036  shr     ecx, 1Fh
0x18006c039  add     r9d, ecx
0x18006c03c  lea     ecx, [r8+126Ch]
0x18006c043  imul    r8d, ecx, 8EADh
0x18006c04a  imul    r8d
0x18006c04d  mov     r8d, 4
0x18006c053  mov     eax, r10d
0x18006c056  sar     edx, 5
0x18006c059  mov     ecx, edx
0x18006c05b  add     edx, r9d
0x18006c05e  shr     ecx, 1Fh
0x18006c061  add     ecx, edx
0x18006c063  cdq
0x18006c064  idiv    r8d
0x18006c067  add     eax, ecx
0x18006c069  sub     eax, r10d
0x18006c06c  add     eax, 26h ; '&'
0x18006c06f  add     eax, edi
0x18006c071  cmp     byte ptr [r11+2Ah], 0
0x18006c076  movd    xmm0, eax
0x18006c07a  cvtdq2pd xmm0, xmm0
0x18006c07e  subsd   xmm0, cs:__real@4097d20000000000
0x18006c086  mulsd   xmm0, cs:__real@4194997000000000
0x18006c08e  cvttsd2si r8, xmm0
0x18006c093  mov     [r11], r8
0x18006c096  jz      loc_18006C11E
0x18006c09c  imul    eax, [r11+14h], 3Ch ; '<'
0x18006c0a1  movsd   xmm0, qword ptr [r11+20h]
0x18006c0a7  mulsd   xmm0, cs:__real@408f400000000000
0x18006c0af  add     eax, [r11+18h]
0x18006c0b3  imul    eax, 0EA60h
0x18006c0b9  addsd   xmm0, cs:__real@3fe0000000000000
0x18006c0c1  movsxd  rdx, eax
0x18006c0c4  add     rdx, r8
0x18006c0c7  cvttsd2si rcx, xmm0
0x18006c0cc  add     rdx, rcx
0x18006c0cf  cmp     dword ptr [r11+1Ch], 0
0x18006c0d4  mov     [r11], rdx
0x18006c0d7  jz      short loc_18006C11E
0x18006c0d9  imul    eax, [r11+1Ch], 0EA60h
0x18006c0e1  and     ebx, 0FFFFFFEFh
0x18006c0e4  mov     word ptr [r11+29h], 0
0x18006c0eb  mov     dword ptr [r11+1Ch], 0
0x18006c0f3  movsxd  rcx, eax
0x18006c0f6  sub     rdx, rcx
0x18006c0f9  or      ebx, 8
0x18006c0fc  mov     [r11], rdx
0x18006c0ff  mov     [r11+2Ch], ebx
0x18006c103  jmp     short loc_18006C11E
0x18006c105  xorps   xmm0, xmm0
0x18006c108  movups  xmmword ptr [r11], xmm0
0x18006c10c  movups  xmmword ptr [r11+10h], xmm0
0x18006c111  movups  xmmword ptr [r11+20h], xmm0
0x18006c116  mov     dword ptr [r11+2Ch], 2
0x18006c11e  mov     rbx, [rsp+arg_0]
0x18006c123  mov     rdi, [rsp+arg_8]
0x18006c128  retn
```
