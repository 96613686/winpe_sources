# computeJD

- ea: `0x18007c308`
- end: `0x18007c4a3`
- name: `computeJD`
- size: `411`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007c25c`
- `0x180081648`
- `0x1800882e0`
- `0x18008a824`
- `0x18008b220`
- `0x18009f8d0`
- `0x1800a09a0`
- `0x1800a0c74`
- `0x1800a1410`

## callees

- `0x18007c308`

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
  v9 = v7 / 100;
  if ( v4 > 2 )
    v8 = v4;
  result = (unsigned int)(v5 + 36525 * (v7 + 4716) / 100 + 306001 * (v8 + 1) / 10000 + v9 / 4 - v9 + 2);
  v10 = *(_BYTE *)(a1 + 42) == 0;
  v11 = (unsigned int)(int)(((double)(v5 + 36525 * (v7 + 4716) / 100 + 306001 * (v8 + 1) / 10000 + v9 / 4 - v9 + 2)
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
0x18007c308  mov     [rsp+arg_0], rbx
0x18007c30d  mov     [rsp+arg_8], rdi
0x18007c312  cmp     byte ptr [rcx+28h], 0
0x18007c316  mov     r11, rcx
0x18007c319  jnz     loc_18007C498
0x18007c31f  cmp     byte ptr [rcx+29h], 0
0x18007c323  jz      short loc_18007C343
0x18007c325  mov     ecx, [rcx+8]
0x18007c328  lea     eax, [rcx+1269h]
0x18007c32e  cmp     eax, 3978h
0x18007c333  ja      loc_18007C47F
0x18007c339  mov     r9d, [r11+0Ch]
0x18007c33d  mov     edi, [r11+10h]
0x18007c341  jmp     short loc_18007C350
0x18007c343  mov     edi, 1
0x18007c348  mov     ecx, 7D0h
0x18007c34d  mov     r9d, edi
0x18007c350  mov     ebx, [r11+2Ch]
0x18007c354  test    bl, 1
0x18007c357  jnz     loc_18007C47F
0x18007c35d  lea     r8d, [rcx-1]
0x18007c361  mov     byte ptr [r11+28h], 1
0x18007c366  cmp     r9d, 2
0x18007c36a  mov     eax, 51EB851Fh
0x18007c36f  cmovg   r8d, ecx
0x18007c373  lea     ecx, [r9+0Ch]
0x18007c377  imul    r8d
0x18007c37a  mov     r10d, edx
0x18007c37d  sar     r10d, 5
0x18007c381  mov     eax, r10d
0x18007c384  shr     eax, 1Fh
0x18007c387  add     r10d, eax
0x18007c38a  mov     eax, 68DB8BADh
0x18007c38f  cmp     r9d, 2
0x18007c393  cmovg   ecx, r9d
0x18007c397  inc     ecx
0x18007c399  imul    ecx, 4AB51h
0x18007c39f  imul    ecx
0x18007c3a1  mov     eax, 51EB851Fh
0x18007c3a6  mov     r9d, edx
0x18007c3a9  sar     r9d, 0Ch
0x18007c3ad  mov     ecx, r9d
0x18007c3b0  shr     ecx, 1Fh
0x18007c3b3  add     r9d, ecx
0x18007c3b6  lea     ecx, [r8+126Ch]
0x18007c3bd  imul    r8d, ecx, 8EADh
0x18007c3c4  imul    r8d
0x18007c3c7  mov     r8d, 4
0x18007c3cd  mov     eax, r10d
0x18007c3d0  sar     edx, 5
0x18007c3d3  mov     ecx, edx
0x18007c3d5  add     edx, r9d
0x18007c3d8  shr     ecx, 1Fh
0x18007c3db  add     ecx, edx
0x18007c3dd  cdq
0x18007c3de  idiv    r8d
0x18007c3e1  add     eax, ecx
0x18007c3e3  sub     eax, r10d
0x18007c3e6  add     eax, 2
0x18007c3e9  add     eax, edi
0x18007c3eb  cmp     byte ptr [r11+2Ah], 0
0x18007c3f0  movd    xmm0, eax
0x18007c3f4  cvtdq2pd xmm0, xmm0
0x18007c3f8  subsd   xmm0, cs:__real@4097d20000000000
0x18007c400  mulsd   xmm0, cs:__real@4194997000000000
0x18007c408  cvttsd2si r8, xmm0
0x18007c40d  mov     [r11], r8
0x18007c410  jz      loc_18007C498
0x18007c416  imul    eax, [r11+14h], 3Ch ; '<'
0x18007c41b  movsd   xmm0, qword ptr [r11+20h]
0x18007c421  mulsd   xmm0, cs:__real@408f400000000000
0x18007c429  add     eax, [r11+18h]
0x18007c42d  imul    eax, 0EA60h
0x18007c433  addsd   xmm0, cs:__real@3fe0000000000000
0x18007c43b  movsxd  rdx, eax
0x18007c43e  add     rdx, r8
0x18007c441  cvttsd2si rcx, xmm0
0x18007c446  add     rdx, rcx
0x18007c449  cmp     dword ptr [r11+1Ch], 0
0x18007c44e  mov     [r11], rdx
0x18007c451  jz      short loc_18007C498
0x18007c453  imul    eax, [r11+1Ch], 0EA60h
0x18007c45b  and     ebx, 0FFFFFFEFh
0x18007c45e  mov     word ptr [r11+29h], 0
0x18007c465  mov     dword ptr [r11+1Ch], 0
0x18007c46d  movsxd  rcx, eax
0x18007c470  sub     rdx, rcx
0x18007c473  or      ebx, 8
0x18007c476  mov     [r11], rdx
0x18007c479  mov     [r11+2Ch], ebx
0x18007c47d  jmp     short loc_18007C498
0x18007c47f  xorps   xmm0, xmm0
0x18007c482  movups  xmmword ptr [r11], xmm0
0x18007c486  movups  xmmword ptr [r11+10h], xmm0
0x18007c48b  movups  xmmword ptr [r11+20h], xmm0
0x18007c490  mov     dword ptr [r11+2Ch], 2
0x18007c498  mov     rbx, [rsp+arg_0]
0x18007c49d  mov     rdi, [rsp+arg_8]
0x18007c4a2  retn
```
