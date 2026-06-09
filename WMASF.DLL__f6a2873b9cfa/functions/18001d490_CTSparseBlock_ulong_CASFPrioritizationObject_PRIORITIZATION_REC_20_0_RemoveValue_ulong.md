# CTSparseBlock<ulong,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::RemoveValue(ulong)

- ea: `0x18001d490`
- end: `0x18001d5ee`
- name: `?RemoveValue@?$CTSparseBlock@KUPRIORITIZATION_REC@CASFPrioritizationObject@@$0BE@$0A@@@QEAAJK@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d400`

## callees

- `0x18001d490`
- `0x18001d5f4`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::RemoveValue(
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
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r10
  char j; // r11
  unsigned __int8 v16; // si

  for ( i = a1; i; i = *(_QWORD *)(i + 104) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 112);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 120);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 120) = v7 - 1;
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
      if ( (*(_BYTE *)(i + 20)
          & CTSparseBlock<unsigned long,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::s_bSingleBitMasks[0]) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::SetValue(
               a1,
               v9 - 1,
               *(unsigned int *)(i + 24));
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 4 * (v11 + 6LL)), (const void *)(i + 4 * (v11 + 1 + 6LL)), 4LL * (19 - v11));
    v12 = v11 >> 3;
    v13 = v12;
    v14 = v12 + i;
    for ( j = *(_BYTE *)(v12 + i + 20); (unsigned int)v13 < 3; v13 = (unsigned int)(v13 + 1) )
    {
      *(_BYTE *)(v13 + i + 20) *= 2;
      if ( (unsigned int)v13 < 2 && *(char *)((unsigned int)(v13 + 1) + i + 20) < 0 )
        *(_BYTE *)(v13 + i + 20) |= 1u;
    }
    if ( v10 )
    {
      v16 = v11 & 7;
      if ( v16 )
      {
        *(_BYTE *)(v14 + 20) &= *((_BYTE *)&qword_18004A1E8 - v16);
        *(_BYTE *)(v14 + 20) |= j
                              & CTSparseBlock<unsigned long,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::s_bLeftBitMasks[v16];
      }
    }
    if ( v6 && *(_QWORD *)(i + 104) == *(_QWORD *)(a1 + 112) )
    {
      *(_QWORD *)(a1 + 112) = i;
      *(_DWORD *)(a1 + 120) = 19;
    }
    i = *(_QWORD *)(i + 104);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d490  push    rbx
0x18001d492  push    rbp
0x18001d493  push    rsi
0x18001d494  push    rdi
0x18001d495  push    r12
0x18001d497  push    r14
0x18001d499  push    r15
0x18001d49b  sub     rsp, 20h
0x18001d49f  mov     ebp, edx
0x18001d4a1  mov     rdi, rcx
0x18001d4a4  mov     rbx, rcx
0x18001d4a7  test    rcx, rcx
0x18001d4aa  jz      short loc_18001D4BF
0x18001d4ac  mov     eax, [rbx+8]
0x18001d4af  add     eax, 14h
0x18001d4b2  cmp     ebp, eax
0x18001d4b4  jb      short loc_18001D4BF
0x18001d4b6  mov     rbx, [rbx+68h]
0x18001d4ba  test    rbx, rbx
0x18001d4bd  jnz     short loc_18001D4AC
0x18001d4bf  mov     rax, [rcx+70h]
0x18001d4c3  xor     r12d, r12d
0x18001d4c6  test    rax, rax
0x18001d4c9  jz      short loc_18001D4E7
0x18001d4cb  mov     edx, [rcx+78h]
0x18001d4ce  mov     ecx, [rax+8]
0x18001d4d1  add     ecx, edx
0x18001d4d3  cmp     ebp, ecx
0x18001d4d5  jnb     short loc_18001D4E7
0x18001d4d7  test    edx, edx
0x18001d4d9  jnz     short loc_18001D4E1
0x18001d4db  lea     r12d, [rdx+1]
0x18001d4df  jmp     short loc_18001D4E7
0x18001d4e1  lea     eax, [rdx-1]
0x18001d4e4  mov     [rdi+78h], eax
0x18001d4e7  xor     r14d, r14d
0x18001d4ea  jmp     loc_18001D5D3
0x18001d4ef  mov     edx, [rbx+8]
0x18001d4f2  cmp     ebp, edx
0x18001d4f4  jb      short loc_18001D502
0x18001d4f6  mov     esi, ebp
0x18001d4f8  mov     r15d, 1
0x18001d4fe  sub     esi, edx
0x18001d500  jmp     short loc_18001D52B
0x18001d502  mov     al, [rbx+14h]
0x18001d505  xor     r15d, r15d
0x18001d508  xor     esi, esi
0x18001d50a  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUPRIORITIZATION_REC@CASFPrioritizationObject@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::s_bSingleBitMasks
0x18001d510  jz      short loc_18001D52B
0x18001d512  mov     r8d, [rbx+18h]
0x18001d516  dec     edx
0x18001d518  mov     rcx, rdi
0x18001d51b  call    ?SetValue@?$CTSparseBlock@KUPRIORITIZATION_REC@CASFPrioritizationObject@@$0BE@$0A@@@QEAAJKUPRIORITIZATION_REC@CASFPrioritizationObject@@@Z; CTSparseBlock<ulong,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::SetValue(ulong,CASFPrioritizationObject::PRIORITIZATION_REC)
0x18001d520  mov     r14d, eax
0x18001d523  test    eax, eax
0x18001d525  js      loc_18001D5DC
0x18001d52b  mov     r8d, 13h
0x18001d531  mov     ecx, esi
0x18001d533  add     rcx, 6
0x18001d537  lea     edx, [rsi+1]
0x18001d53a  sub     r8d, esi
0x18001d53d  lea     rdx, [rdx+6]
0x18001d541  shl     r8, 2; Size
0x18001d545  lea     rdx, [rbx+rdx*4]; Src
0x18001d549  lea     rcx, [rbx+rcx*4]; void *
0x18001d54d  call    memmove_0
0x18001d552  mov     eax, esi
0x18001d554  shr     eax, 3
0x18001d557  mov     edx, eax
0x18001d559  lea     r10, [rax+rbx]
0x18001d55d  mov     r11b, [r10+14h]
0x18001d561  cmp     eax, 3
0x18001d564  jnb     short loc_18001D585
0x18001d566  shl     byte ptr [rdx+rbx+14h], 1
0x18001d56a  cmp     edx, 2
0x18001d56d  jnb     short loc_18001D57E
0x18001d56f  lea     eax, [rdx+1]
0x18001d572  cmp     byte ptr [rax+rbx+14h], 0
0x18001d577  jge     short loc_18001D57E
0x18001d579  or      byte ptr [rdx+rbx+14h], 1
0x18001d57e  inc     edx
0x18001d580  cmp     edx, 3
0x18001d583  jb      short loc_18001D566
0x18001d585  test    r15d, r15d
0x18001d588  jz      short loc_18001D5B5
0x18001d58a  and     sil, 7
0x18001d58e  jbe     short loc_18001D5B5
0x18001d590  movzx   ecx, sil
0x18001d594  lea     rax, qword_18004A1E8
0x18001d59b  sub     rax, rcx
0x18001d59e  mov     al, [rax]
0x18001d5a0  and     [r10+14h], al
0x18001d5a4  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUPRIORITIZATION_REC@CASFPrioritizationObject@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFPrioritizationObject::PRIORITIZATION_REC,20,0>::s_bLeftBitMasks
0x18001d5ab  mov     al, [rcx+rax]
0x18001d5ae  and     al, r11b
0x18001d5b1  or      [r10+14h], al
0x18001d5b5  test    r12d, r12d
0x18001d5b8  jz      short loc_18001D5CF
0x18001d5ba  mov     rax, [rdi+70h]
0x18001d5be  cmp     [rbx+68h], rax
0x18001d5c2  jnz     short loc_18001D5CF
0x18001d5c4  mov     [rdi+70h], rbx
0x18001d5c8  mov     dword ptr [rdi+78h], 13h
0x18001d5cf  mov     rbx, [rbx+68h]
0x18001d5d3  test    rbx, rbx
0x18001d5d6  jnz     loc_18001D4EF
0x18001d5dc  mov     eax, r14d
0x18001d5df  add     rsp, 20h
0x18001d5e3  pop     r15
0x18001d5e5  pop     r14
0x18001d5e7  pop     r12
0x18001d5e9  pop     rdi
0x18001d5ea  pop     rsi
0x18001d5eb  pop     rbp
0x18001d5ec  pop     rbx
0x18001d5ed  retn
```
