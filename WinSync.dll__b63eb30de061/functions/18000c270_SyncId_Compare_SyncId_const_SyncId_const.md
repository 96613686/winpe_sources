# SyncId::Compare(SyncId const &,SyncId const &)

- ea: `0x18000c270`
- end: `0x18000c3de`
- name: `?Compare@SyncId@@SAJAEBV1@0@Z`
- size: `366`
- prototype: `__int64 __fastcall(const struct SyncId *, const struct SyncId *)`
- caller_count: `41`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003830`
- `0x180005f80`
- `0x1800076ac`
- `0x180008ad0`
- `0x18000a2b8`
- `0x18000aeb4`
- `0x18000b688`
- `0x18000d6e0`
- `0x18000ec2c`
- `0x18001a5f0`
- `0x18001b00c`
- `0x18001d9e4`
- `0x18001e614`
- `0x18001f1d4`
- `0x180022d90`
- `0x180024768`
- `0x180025024`
- `0x18002540c`
- `0x180084f20`
- `0x180088670`
- `0x18008999c`
- `0x180089a90`
- `0x180089c40`
- `0x180089cd4`
- `0x18008a268`
- `0x18008aeac`
- `0x18008b918`
- `0x18008bc9c`
- `0x18008bd3c`
- `0x18008c0c8`
- `0x18008c25c`
- `0x18008cc20`
- `0x18008cc60`
- `0x18008cca0`
- `0x18008ce54`
- `0x18008e4d0`
- `0x18008f6fc`
- `0x18008f9d8`
- `0x180090970`
- `0x180091018`
- `0x1800916fc`

## callees

- `0x18000c270`

## pseudocode

```c
__int64 __fastcall SyncId::Compare(const struct SyncId *a1, const struct SyncId *a2)
{
  __int64 v2; // rbp
  int v3; // r8d
  unsigned int *v4; // rax
  _WORD *v5; // r9
  int v6; // r11d
  int v7; // esi
  unsigned __int16 *v8; // rdi
  unsigned int *v9; // r10
  _WORD *v10; // rdx
  __int64 v11; // rbx
  unsigned int *v12; // r9
  unsigned int v13; // edx
  unsigned int v14; // r8d
  __int64 result; // rax
  unsigned int v16; // edx
  unsigned int v17; // r8d
  unsigned __int8 *v18; // r8
  unsigned __int8 *v19; // rax
  unsigned __int8 *v20; // rdx
  unsigned __int8 *v21; // r10
  int v22; // r11d
  int v23; // r9d

  v2 = *((_QWORD *)a1 + 1);
  v3 = *((_DWORD *)a1 + 1);
  v4 = (unsigned int *)v2;
  v5 = (_WORD *)*((_QWORD *)a2 + 1);
  v6 = *((_DWORD *)a2 + 1);
  v7 = v3 & 0x20000;
  v8 = (unsigned __int16 *)(v2 + 4);
  if ( (v3 & 0x20000) == 0 )
    v4 = (unsigned int *)(v2 + 4);
  v9 = (unsigned int *)*((_QWORD *)a2 + 1);
  v10 = v5 + 2;
  if ( (v6 & 0x20000) == 0 )
    v9 = (unsigned int *)(v5 + 2);
  if ( v4 == v9 )
    return 0;
  if ( (v3 & 0x10000) == 0 )
  {
    v11 = (unsigned __int16)v3;
    v12 = &v4[(unsigned __int64)(unsigned __int16)v3 >> 2];
    while ( v4 < v12 )
    {
      v13 = *v9;
      v14 = *v4;
      if ( *v4 != *v9 )
      {
        if ( (unsigned __int8)v14 > (unsigned __int8)v13 )
          return 1;
        if ( (unsigned __int8)v14 < (unsigned __int8)v13 || BYTE1(v14) < BYTE1(v13) )
          return 0xFFFFFFFFLL;
        if ( BYTE1(v14) > BYTE1(v13) || BYTE2(v14) > BYTE2(v13) )
          return 1;
        if ( BYTE2(v14) < BYTE2(v13) )
          return 0xFFFFFFFFLL;
        v16 = HIBYTE(v13);
        v17 = HIBYTE(v14);
        if ( (unsigned __int8)v17 > (unsigned __int8)v16 )
          return 1;
        if ( (unsigned __int8)v17 < (unsigned __int8)v16 )
          return 0xFFFFFFFFLL;
      }
      ++v4;
      ++v9;
    }
    if ( (v11 & 3) != 0 )
    {
      if ( v7 )
        v8 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
      while ( v4 < (unsigned int *)((char *)v8 + v11) )
      {
        if ( *(_BYTE *)v4 > *(_BYTE *)v9 )
          return 1;
        if ( *(_BYTE *)v4 < *(_BYTE *)v9 )
          return 0xFFFFFFFFLL;
        v4 = (unsigned int *)((char *)v4 + 1);
        v9 = (unsigned int *)((char *)v9 + 1);
      }
    }
    return 0;
  }
  if ( v7 )
    v8 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
  v18 = (unsigned __int8 *)v4 + *v8;
  if ( (v6 & 0x10000) != 0 )
  {
    if ( (v6 & 0x20000) != 0 )
      v10 = v5;
    LOWORD(v6) = *v10;
  }
  v19 = (unsigned __int8 *)v4 + 2;
  v20 = (unsigned __int8 *)v9 + (unsigned __int16)v6;
  v21 = (unsigned __int8 *)v9 + 2;
  while ( v19 < v18 )
  {
    if ( v21 >= v20 )
      return 1;
    v22 = *v21;
    v23 = *v19;
    if ( v23 != v22 )
    {
      result = 1;
      if ( (unsigned __int8)v23 <= (unsigned __int8)v22 )
        return 0xFFFFFFFFLL;
      return result;
    }
    ++v19;
    ++v21;
  }
  if ( v21 < v20 )
    return 0xFFFFFFFFLL;
  else
    return 0;
}

```

## disassembly

```asm
0x18000c270  push    rbx
0x18000c272  push    rbp
0x18000c273  push    rsi
0x18000c274  push    rdi
0x18000c275  mov     rbp, [rcx+8]
0x18000c279  mov     r8d, [rcx+4]
0x18000c27d  mov     rax, rbp
0x18000c280  mov     r9, [rdx+8]
0x18000c284  mov     esi, r8d
0x18000c287  mov     r11d, [rdx+4]
0x18000c28b  and     esi, 20000h
0x18000c291  lea     rdi, [rbp+4]
0x18000c295  mov     ecx, r11d
0x18000c298  cmovz   rax, rdi
0x18000c29c  mov     r10, r9
0x18000c29f  and     ecx, 20000h
0x18000c2a5  lea     rdx, [r9+4]
0x18000c2a9  cmovz   r10, rdx
0x18000c2ad  cmp     rax, r10
0x18000c2b0  jz      loc_18000C35C
0x18000c2b6  bt      r8d, 10h
0x18000c2bb  jb      loc_18000C360
0x18000c2c1  movzx   ebx, r8w
0x18000c2c5  mov     ecx, ebx
0x18000c2c7  shr     rcx, 2
0x18000c2cb  lea     r9, [rax+rcx*4]
0x18000c2cf  cmp     rax, r9
0x18000c2d2  jnb     short loc_18000C2E9
0x18000c2d4  mov     edx, [r10]
0x18000c2d7  mov     r8d, [rax]
0x18000c2da  cmp     r8d, edx
0x18000c2dd  jnz     short loc_18000C30F
0x18000c2df  add     rax, 4
0x18000c2e3  add     r10, 4
0x18000c2e7  jmp     short loc_18000C2CF
0x18000c2e9  test    bl, 3
0x18000c2ec  jz      short loc_18000C35C
0x18000c2ee  test    esi, esi
0x18000c2f0  cmovnz  rdi, rbp
0x18000c2f4  lea     r8, [rbx+rdi]
0x18000c2f8  cmp     rax, r8
0x18000c2fb  jnb     short loc_18000C35C
0x18000c2fd  movzx   ecx, byte ptr [r10]
0x18000c301  cmp     [rax], cl
0x18000c303  jbe     short loc_18000C34C
0x18000c305  mov     eax, 1
0x18000c30a  pop     rdi
0x18000c30b  pop     rsi
0x18000c30c  pop     rbp
0x18000c30d  pop     rbx
0x18000c30e  retn
0x18000c30f  cmp     r8b, dl
0x18000c312  ja      short loc_18000C305
0x18000c314  jb      short loc_18000C352
0x18000c316  mov     ecx, edx
0x18000c318  mov     r11d, r8d
0x18000c31b  shr     ecx, 8
0x18000c31e  shr     r11d, 8
0x18000c322  cmp     r11b, cl
0x18000c325  jb      short loc_18000C352
0x18000c327  ja      short loc_18000C305
0x18000c329  mov     ecx, edx
0x18000c32b  mov     r11d, r8d
0x18000c32e  shr     ecx, 10h
0x18000c331  shr     r11d, 10h
0x18000c335  cmp     r11b, cl
0x18000c338  ja      short loc_18000C305
0x18000c33a  jb      short loc_18000C352
0x18000c33c  shr     edx, 18h
0x18000c33f  shr     r8d, 18h
0x18000c343  cmp     r8b, dl
0x18000c346  ja      short loc_18000C305
0x18000c348  jnb     short loc_18000C2DF
0x18000c34a  jmp     short loc_18000C352
0x18000c34c  jnb     loc_18000C3D3
0x18000c352  mov     eax, 0FFFFFFFFh
0x18000c357  pop     rdi
0x18000c358  pop     rsi
0x18000c359  pop     rbp
0x18000c35a  pop     rbx
0x18000c35b  retn
0x18000c35c  xor     eax, eax
0x18000c35e  jmp     short loc_18000C30A
0x18000c360  test    esi, esi
0x18000c362  cmovnz  rdi, rbp
0x18000c366  movzx   r8d, word ptr [rdi]
0x18000c36a  add     r8, rax
0x18000c36d  bt      r11d, 10h
0x18000c372  jb      short loc_18000C3C7
0x18000c374  movzx   edx, r11w
0x18000c378  add     rax, 2
0x18000c37c  add     rdx, r10
0x18000c37f  add     r10, 2
0x18000c383  cmp     rax, r8
0x18000c386  jnb     short loc_18000C3BB
0x18000c388  cmp     r10, rdx
0x18000c38b  jnb     loc_18000C305
0x18000c391  movzx   r11d, byte ptr [r10]
0x18000c395  movzx   r9d, byte ptr [rax]
0x18000c399  cmp     r9d, r11d
0x18000c39c  jnz     short loc_18000C3A6
0x18000c39e  inc     rax
0x18000c3a1  inc     r10
0x18000c3a4  jmp     short loc_18000C383
0x18000c3a6  cmp     r9b, r11b
0x18000c3a9  mov     eax, 1
0x18000c3ae  mov     ecx, 0FFFFFFFFh
0x18000c3b3  cmovbe  eax, ecx
0x18000c3b6  pop     rdi
0x18000c3b7  pop     rsi
0x18000c3b8  pop     rbp
0x18000c3b9  pop     rbx
0x18000c3ba  retn
0x18000c3bb  cmp     r10, rdx
0x18000c3be  jb      short loc_18000C352
0x18000c3c0  xor     eax, eax
0x18000c3c2  jmp     loc_18000C30A
0x18000c3c7  test    ecx, ecx
0x18000c3c9  cmovnz  rdx, r9
0x18000c3cd  movzx   r11d, word ptr [rdx]
0x18000c3d1  jmp     short loc_18000C374
0x18000c3d3  inc     rax
0x18000c3d6  inc     r10
0x18000c3d9  jmp     loc_18000C2F8
```
