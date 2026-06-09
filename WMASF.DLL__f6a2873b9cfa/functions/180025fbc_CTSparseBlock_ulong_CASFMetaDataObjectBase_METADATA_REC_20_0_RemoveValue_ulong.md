# CTSparseBlock<ulong,CASFMetaDataObjectBase::METADATA_REC,20,0>::RemoveValue(ulong)

- ea: `0x180025fbc`
- end: `0x18002614e`
- name: `?RemoveValue@?$CTSparseBlock@KUMETADATA_REC@CASFMetaDataObjectBase@@$0BE@$0A@@@QEAAJK@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025f00`

## callees

- `0x18000e070`
- `0x180025fbc`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFMetaDataObjectBase::METADATA_REC,20,0>::RemoveValue(
        __int64 a1,
        unsigned int a2)
{
  __int64 i; // rbx
  __int64 v5; // rax
  int v6; // r12d
  int v7; // edx
  int v8; // r14d
  unsigned int v9; // edx
  int v10; // r15d
  unsigned int v11; // esi
  __int128 v12; // xmm1
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r10
  char j; // r11
  unsigned __int8 v17; // si
  _OWORD v19[5]; // [rsp+20h] [rbp-58h] BYREF

  for ( i = a1; i; i = *(_QWORD *)(i + 696) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 704);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 712);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 712) = v7 - 1;
      else
        v6 = 1;
    }
  }
  v8 = 0;
  while ( i )
  {
    v9 = *(_DWORD *)(i + 8);
    if ( a2 < v9 )
    {
      v10 = 0;
      v11 = 0;
      if ( (*(_BYTE *)(i + 48)
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFMetaDataObjectBase::METADATA_REC,20,0>::s_bSingleBitMasks) != 0 )
      {
        v12 = *(_OWORD *)(i + 72);
        v19[0] = *(_OWORD *)(i + 56);
        v19[1] = v12;
        v8 = CTSparseBlock<unsigned long,CASFMetaDataObjectBase::METADATA_REC,20,0>::SetValue(a1, v9 - 1, v19);
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 32LL * v11 + 56), (const void *)(i + 32LL * (v11 + 1) + 56), 32LL * (19 - v11));
    v13 = v11 >> 3;
    v14 = v13;
    v15 = v13 + i;
    for ( j = *(_BYTE *)(v13 + i + 48); (unsigned int)v14 < 3; v14 = (unsigned int)(v14 + 1) )
    {
      *(_BYTE *)(v14 + i + 48) *= 2;
      if ( (unsigned int)v14 < 2 && *(char *)((unsigned int)(v14 + 1) + i + 48) < 0 )
        *(_BYTE *)(v14 + i + 48) |= 1u;
    }
    if ( v10 )
    {
      v17 = v11 & 7;
      if ( v17 )
      {
        *(_BYTE *)(v15 + 48) &= *((_BYTE *)&qword_18004A308 - v17);
        *(_BYTE *)(v15 + 48) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFMetaDataObjectBase::METADATA_REC,20,0>::s_bLeftBitMasks
                                + v17);
      }
    }
    if ( v6 && *(_QWORD *)(i + 696) == *(_QWORD *)(a1 + 704) )
    {
      *(_QWORD *)(a1 + 704) = i;
      *(_DWORD *)(a1 + 712) = 19;
    }
    i = *(_QWORD *)(i + 696);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180025fbc  push    rbx
0x180025fbe  push    rbp
0x180025fbf  push    rsi
0x180025fc0  push    rdi
0x180025fc1  push    r12
0x180025fc3  push    r14
0x180025fc5  push    r15
0x180025fc7  sub     rsp, 40h
0x180025fcb  mov     ebp, edx
0x180025fcd  mov     rdi, rcx
0x180025fd0  mov     rbx, rcx
0x180025fd3  test    rcx, rcx
0x180025fd6  jz      short loc_180025FEE
0x180025fd8  mov     eax, [rbx+8]
0x180025fdb  add     eax, 14h
0x180025fde  cmp     ebp, eax
0x180025fe0  jb      short loc_180025FEE
0x180025fe2  mov     rbx, [rbx+2B8h]
0x180025fe9  test    rbx, rbx
0x180025fec  jnz     short loc_180025FD8
0x180025fee  mov     rax, [rcx+2C0h]
0x180025ff5  xor     r12d, r12d
0x180025ff8  test    rax, rax
0x180025ffb  jz      short loc_18002601F
0x180025ffd  mov     edx, [rcx+2C8h]
0x180026003  mov     ecx, [rax+8]
0x180026006  add     ecx, edx
0x180026008  cmp     ebp, ecx
0x18002600a  jnb     short loc_18002601F
0x18002600c  test    edx, edx
0x18002600e  jnz     short loc_180026016
0x180026010  lea     r12d, [rdx+1]
0x180026014  jmp     short loc_18002601F
0x180026016  lea     eax, [rdx-1]
0x180026019  mov     [rdi+2C8h], eax
0x18002601f  xor     r14d, r14d
0x180026022  jmp     loc_180026133
0x180026027  mov     edx, [rbx+8]
0x18002602a  cmp     ebp, edx
0x18002602c  jb      short loc_18002603A
0x18002602e  mov     esi, ebp
0x180026030  mov     r15d, 1
0x180026036  sub     esi, edx
0x180026038  jmp     short loc_180026076
0x18002603a  mov     al, [rbx+30h]
0x18002603d  xor     r15d, r15d
0x180026040  xor     esi, esi
0x180026042  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUMETADATA_REC@CASFMetaDataObjectBase@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFMetaDataObjectBase::METADATA_REC,20,0>::s_bSingleBitMasks
0x180026048  jz      short loc_180026076
0x18002604a  movups  xmm0, xmmword ptr [rbx+38h]
0x18002604e  dec     edx
0x180026050  lea     r8, [rsp+78h+var_58]
0x180026055  movups  xmm1, xmmword ptr [rbx+48h]
0x180026059  mov     rcx, rdi
0x18002605c  movaps  [rsp+78h+var_58], xmm0
0x180026061  movaps  [rsp+78h+var_48], xmm1
0x180026066  call    ?SetValue@?$CTSparseBlock@KUMETADATA_REC@CASFMetaDataObjectBase@@$0BE@$0A@@@QEAAJKUMETADATA_REC@CASFMetaDataObjectBase@@@Z; CTSparseBlock<ulong,CASFMetaDataObjectBase::METADATA_REC,20,0>::SetValue(ulong,CASFMetaDataObjectBase::METADATA_REC)
0x18002606b  mov     r14d, eax
0x18002606e  test    eax, eax
0x180026070  js      loc_18002613C
0x180026076  mov     r8d, 13h
0x18002607c  mov     ecx, esi
0x18002607e  shl     rcx, 5
0x180026082  lea     edx, [rsi+1]
0x180026085  shl     rdx, 5
0x180026089  add     rcx, 38h ; '8'
0x18002608d  add     rdx, 38h ; '8'
0x180026091  sub     r8d, esi
0x180026094  add     rdx, rbx; Src
0x180026097  shl     r8, 5; Size
0x18002609b  add     rcx, rbx; void *
0x18002609e  call    memmove_0
0x1800260a3  mov     eax, esi
0x1800260a5  shr     eax, 3
0x1800260a8  mov     edx, eax
0x1800260aa  lea     r10, [rax+rbx]
0x1800260ae  mov     r11b, [r10+30h]
0x1800260b2  cmp     eax, 3
0x1800260b5  jnb     short loc_1800260D6
0x1800260b7  shl     byte ptr [rdx+rbx+30h], 1
0x1800260bb  cmp     edx, 2
0x1800260be  jnb     short loc_1800260CF
0x1800260c0  lea     eax, [rdx+1]
0x1800260c3  cmp     byte ptr [rax+rbx+30h], 0
0x1800260c8  jge     short loc_1800260CF
0x1800260ca  or      byte ptr [rdx+rbx+30h], 1
0x1800260cf  inc     edx
0x1800260d1  cmp     edx, 3
0x1800260d4  jb      short loc_1800260B7
0x1800260d6  test    r15d, r15d
0x1800260d9  jz      short loc_180026106
0x1800260db  and     sil, 7
0x1800260df  jbe     short loc_180026106
0x1800260e1  movzx   ecx, sil
0x1800260e5  lea     rax, qword_18004A308
0x1800260ec  sub     rax, rcx
0x1800260ef  mov     al, [rax]
0x1800260f1  and     [r10+30h], al
0x1800260f5  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUMETADATA_REC@CASFMetaDataObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFMetaDataObjectBase::METADATA_REC,20,0>::s_bLeftBitMasks
0x1800260fc  mov     al, [rcx+rax]
0x1800260ff  and     al, r11b
0x180026102  or      [r10+30h], al
0x180026106  test    r12d, r12d
0x180026109  jz      short loc_18002612C
0x18002610b  mov     rax, [rdi+2C0h]
0x180026112  cmp     [rbx+2B8h], rax
0x180026119  jnz     short loc_18002612C
0x18002611b  mov     [rdi+2C0h], rbx
0x180026122  mov     dword ptr [rdi+2C8h], 13h
0x18002612c  mov     rbx, [rbx+2B8h]
0x180026133  test    rbx, rbx
0x180026136  jnz     loc_180026027
0x18002613c  mov     eax, r14d
0x18002613f  add     rsp, 40h
0x180026143  pop     r15
0x180026145  pop     r14
0x180026147  pop     r12
0x180026149  pop     rdi
0x18002614a  pop     rsi
0x18002614b  pop     rbp
0x18002614c  pop     rbx
0x18002614d  retn
```
