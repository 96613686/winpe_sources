# LKRhash::CLKRLinearHashTable::_SetSegVars(LKRhash::LK_TABLESIZE,ulong)

- ea: `0x18000a330`
- end: `0x18000a4ad`
- name: `?_SetSegVars@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@W4LK_TABLESIZE@2@K@Z`
- size: `381`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800089a4`
- `0x180009e84`

## callees

- `0x1800086f0`
- `0x18000882c`
- `0x180009af0`
- `0x180009b54`
- `0x18000a330`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable::_SetSegVars(__int64 a1, int a2, unsigned int a3)
{
  unsigned int v4; // ebx
  int v5; // edx
  int v6; // edx
  int v7; // ecx
  unsigned int v8; // eax
  int v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  struct LKRhash::CDirEntry *SegmentDirectory; // rax
  unsigned int *v13; // r14
  int v14; // ecx
  __int64 v15; // rsi
  unsigned int v16; // ebx
  struct LKRhash::CSegment *Segment; // rax
  int v18; // eax
  __int64 v19; // rcx

  *(_DWORD *)(a1 + 20) = 0;
  v4 = 8;
  v5 = a2 - 1;
  if ( v5 )
  {
    if ( v5 == 2 )
    {
      *(_DWORD *)(a1 + 64) = 3;
      v6 = 511;
      v7 = 9;
      *(_DWORD *)(a1 + 72) = 512;
    }
    else
    {
      *(_DWORD *)(a1 + 64) = 2;
      v7 = 6;
      *(_DWORD *)(a1 + 72) = 64;
      v6 = 63;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 64) = 1;
    v7 = 3;
    *(_DWORD *)(a1 + 72) = 8;
    v6 = 7;
  }
  *(_DWORD *)(a1 + 68) = v7;
  v8 = a3 >> v7;
  *(_DWORD *)(a1 + 76) = v6;
  *(_DWORD *)(a1 + 88) = v6;
  *(_DWORD *)(a1 + 112) = v7;
  *(_DWORD *)(a1 + 124) = a3;
  if ( a3 >> v7 > 1 )
  {
    do
    {
      v8 >>= 1;
      v6 = (2 * v6) | 1;
      ++v7;
    }
    while ( v8 > 1 );
    *(_DWORD *)(a1 + 88) = v6;
    *(_DWORD *)(a1 + 112) = v7;
  }
  v9 = 2 * v6;
  v10 = a3 & v6;
  v11 = a3 >> *(_DWORD *)(a1 + 68);
  *(_DWORD *)(a1 + 92) = v9 | 1;
  *(_DWORD *)(a1 + 96) = v10;
  if ( v11 > 8 )
  {
    do
      v4 *= 2;
    while ( v4 < v11 );
    if ( v4 >= 0x100000 )
      v4 = 0x100000;
  }
  SegmentDirectory = LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory((LKRhash::CLKRLinearHashTable *)a1, v4);
  *(_QWORD *)(a1 + 104) = SegmentDirectory;
  v13 = (unsigned int *)(a1 + 116);
  if ( !SegmentDirectory )
  {
LABEL_21:
    *(_DWORD *)(a1 + 20) = -98;
    goto LABEL_22;
  }
  v14 = *(_DWORD *)(a1 + 72);
  v15 = 0;
  *v13 = v4;
  v16 = (unsigned int)(v14 - 1 + *(_DWORD *)(a1 + 124)) >> *(_DWORD *)(a1 + 68);
  if ( v16 )
  {
    while ( 1 )
    {
      Segment = LKRhash::CLKRLinearHashTable::_AllocateSegment((LKRhash::CLKRLinearHashTable *)a1);
      if ( !Segment )
        break;
      *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * v15) = Segment;
      v15 = (unsigned int)(v15 + 1);
      if ( (unsigned int)v15 >= v16 )
        goto LABEL_22;
    }
    while ( (_DWORD)v15 )
    {
      LODWORD(v15) = v15 - 1;
      LKRhash::CLKRLinearHashTable::_FreeSegment(
        (LKRhash::CLKRLinearHashTable *)a1,
        *(struct LKRhash::CSegment **)(*(_QWORD *)(a1 + 104) + 8LL * (unsigned int)v15));
      *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * (unsigned int)v15) = 0;
    }
    LKRhash::CLKRLinearHashTable::_FreeSegmentDirectory((LKRhash::CLKRLinearHashTable *)a1);
    goto LABEL_21;
  }
LABEL_22:
  v18 = *(_DWORD *)(a1 + 20);
  if ( v18 )
  {
    v19 = *(_QWORD *)(a1 + 136);
    *(_QWORD *)(a1 + 104) = 0;
    *(_DWORD *)(a1 + 96) = 0;
    *(_DWORD *)(a1 + 124) = 0;
    *v13 = 0;
    if ( v19 )
      *(_DWORD *)(v19 + 48) = v18;
  }
  return *(unsigned int *)(a1 + 20);
}

```

## disassembly

```asm
0x18000a330  push    rbx
0x18000a332  push    rsi
0x18000a333  push    rdi
0x18000a334  push    r14
0x18000a336  sub     rsp, 28h
0x18000a33a  mov     dword ptr [rcx+14h], 0
0x18000a341  mov     rdi, rcx
0x18000a344  mov     ebx, 8
0x18000a349  sub     edx, 1
0x18000a34c  jz      short loc_18000A388
0x18000a34e  sub     edx, 1
0x18000a351  jz      short loc_18000A370
0x18000a353  cmp     edx, 1
0x18000a356  jnz     short loc_18000A370
0x18000a358  mov     dword ptr [rcx+40h], 3
0x18000a35f  mov     edx, 1FFh
0x18000a364  lea     ecx, [rbx+1]
0x18000a367  mov     dword ptr [rdi+48h], 200h
0x18000a36e  jmp     short loc_18000A39A
0x18000a370  mov     dword ptr [rcx+40h], 2
0x18000a377  mov     ecx, 6
0x18000a37c  mov     dword ptr [rdi+48h], 40h ; '@'
0x18000a383  lea     edx, [rcx+39h]
0x18000a386  jmp     short loc_18000A39A
0x18000a388  mov     dword ptr [rcx+40h], 1
0x18000a38f  mov     ecx, 3
0x18000a394  mov     [rdi+48h], ebx
0x18000a397  lea     edx, [rcx+4]
0x18000a39a  mov     eax, r8d
0x18000a39d  mov     [rdi+44h], ecx
0x18000a3a0  shr     eax, cl
0x18000a3a2  mov     [rdi+4Ch], edx
0x18000a3a5  mov     [rdi+58h], edx
0x18000a3a8  mov     [rdi+70h], ecx
0x18000a3ab  mov     [rdi+7Ch], r8d
0x18000a3af  cmp     eax, 1
0x18000a3b2  jbe     short loc_18000A3C8
0x18000a3b4  add     edx, edx
0x18000a3b6  shr     eax, 1
0x18000a3b8  or      edx, 1
0x18000a3bb  inc     ecx
0x18000a3bd  cmp     eax, 1
0x18000a3c0  ja      short loc_18000A3B4
0x18000a3c2  mov     [rdi+58h], edx
0x18000a3c5  mov     [rdi+70h], ecx
0x18000a3c8  mov     ecx, [rdi+44h]
0x18000a3cb  lea     eax, [rdx+rdx]
0x18000a3ce  and     edx, r8d
0x18000a3d1  or      eax, 1
0x18000a3d4  shr     r8d, cl
0x18000a3d7  mov     [rdi+5Ch], eax
0x18000a3da  mov     [rdi+60h], edx
0x18000a3dd  cmp     r8d, ebx
0x18000a3e0  jbe     short loc_18000A3F3
0x18000a3e2  add     ebx, ebx
0x18000a3e4  cmp     ebx, r8d
0x18000a3e7  jb      short loc_18000A3E2
0x18000a3e9  mov     eax, 100000h
0x18000a3ee  cmp     ebx, eax
0x18000a3f0  cmovnb  ebx, eax
0x18000a3f3  mov     edx, ebx; unsigned __int64
0x18000a3f5  mov     rcx, rdi; this
0x18000a3f8  call    ?_AllocateSegmentDirectory@CLKRLinearHashTable@LKRhash@@AEAAQEAVCDirEntry@2@_K@Z; LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory(unsigned __int64)
0x18000a3fd  mov     [rdi+68h], rax
0x18000a401  lea     r14, [rdi+74h]
0x18000a405  test    rax, rax
0x18000a408  jz      short loc_18000A466
0x18000a40a  mov     ecx, [rdi+48h]
0x18000a40d  xor     esi, esi
0x18000a40f  mov     [r14], ebx
0x18000a412  dec     ecx
0x18000a414  mov     ebx, [rdi+7Ch]
0x18000a417  add     ebx, ecx
0x18000a419  mov     ecx, [rdi+44h]
0x18000a41c  shr     ebx, cl
0x18000a41e  test    ebx, ebx
0x18000a420  jz      short loc_18000A46D
0x18000a422  mov     rcx, rdi; this
0x18000a425  call    ?_AllocateSegment@CLKRLinearHashTable@LKRhash@@AEBAQEAVCSegment@2@XZ; LKRhash::CLKRLinearHashTable::_AllocateSegment(void)
0x18000a42a  test    rax, rax
0x18000a42d  jz      short loc_18000A45A
0x18000a42f  mov     rcx, [rdi+68h]
0x18000a433  mov     [rcx+rsi*8], rax
0x18000a437  inc     esi
0x18000a439  cmp     esi, ebx
0x18000a43b  jb      short loc_18000A422
0x18000a43d  jmp     short loc_18000A46D
0x18000a43f  mov     rdx, [rdi+68h]
0x18000a443  dec     esi
0x18000a445  mov     rdx, [rdx+rsi*8]; struct LKRhash::CSegment *
0x18000a449  call    ?_FreeSegment@CLKRLinearHashTable@LKRhash@@AEBA_NPEAVCSegment@2@@Z; LKRhash::CLKRLinearHashTable::_FreeSegment(LKRhash::CSegment *)
0x18000a44e  mov     rax, [rdi+68h]
0x18000a452  mov     qword ptr [rax+rsi*8], 0
0x18000a45a  mov     rcx, rdi; this
0x18000a45d  test    esi, esi
0x18000a45f  jnz     short loc_18000A43F
0x18000a461  call    ?_FreeSegmentDirectory@CLKRLinearHashTable@LKRhash@@AEAA_NXZ; LKRhash::CLKRLinearHashTable::_FreeSegmentDirectory(void)
0x18000a466  mov     dword ptr [rdi+14h], 0FFFFFF9Eh
0x18000a46d  mov     eax, [rdi+14h]
0x18000a470  test    eax, eax
0x18000a472  jz      short loc_18000A4A0
0x18000a474  mov     rcx, [rdi+88h]
0x18000a47b  mov     qword ptr [rdi+68h], 0
0x18000a483  mov     dword ptr [rdi+60h], 0
0x18000a48a  mov     dword ptr [rdi+7Ch], 0
0x18000a491  mov     dword ptr [r14], 0
0x18000a498  test    rcx, rcx
0x18000a49b  jz      short loc_18000A4A0
0x18000a49d  mov     [rcx+30h], eax
0x18000a4a0  mov     eax, [rdi+14h]
0x18000a4a3  add     rsp, 28h
0x18000a4a7  pop     r14
0x18000a4a9  pop     rdi
0x18000a4aa  pop     rsi
0x18000a4ab  pop     rbx
0x18000a4ac  retn
```
