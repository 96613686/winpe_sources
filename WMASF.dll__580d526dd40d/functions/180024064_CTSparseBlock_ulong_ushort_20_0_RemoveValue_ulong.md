# CTSparseBlock<ulong,ushort,20,0>::RemoveValue(ulong)

- ea: `0x180024064`
- end: `0x1800241c2`
- name: `?RemoveValue@?$CTSparseBlock@KG$0BE@$0A@@@QEAAJK@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023b18`

## callees

- `0x180024064`
- `0x180024598`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,unsigned short,20,0>::RemoveValue(__int64 a1, unsigned int a2)
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

  for ( i = a1; i; i = *(_QWORD *)(i + 64) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 72);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 80);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 80) = v7 - 1;
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
      if ( (*(_BYTE *)(i + 18) & (unsigned __int8)CTSparseBlock<unsigned long,unsigned short,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,unsigned short,20,0>::SetValue(a1, v9 - 1, *(unsigned __int16 *)(i + 22));
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 2 * (v11 + 11LL)), (const void *)(i + 2 * (v11 + 1 + 11LL)), 2LL * (19 - v11));
    v12 = v11 >> 3;
    v13 = v12;
    v14 = v12 + i;
    for ( j = *(_BYTE *)(v12 + i + 18); (unsigned int)v13 < 3; v13 = (unsigned int)(v13 + 1) )
    {
      *(_BYTE *)(v13 + i + 18) *= 2;
      if ( (unsigned int)v13 < 2 && *(char *)((unsigned int)(v13 + 1) + i + 18) < 0 )
        *(_BYTE *)(v13 + i + 18) |= 1u;
    }
    if ( v10 )
    {
      v16 = v11 & 7;
      if ( v16 )
      {
        *(_BYTE *)(v14 + 18) &= *((_BYTE *)&qword_18004A2E0 - v16);
        *(_BYTE *)(v14 + 18) |= j & *((_BYTE *)CTSparseBlock<unsigned long,unsigned short,20,0>::s_bLeftBitMasks + v16);
      }
    }
    if ( v6 && *(_QWORD *)(i + 64) == *(_QWORD *)(a1 + 72) )
    {
      *(_QWORD *)(a1 + 72) = i;
      *(_DWORD *)(a1 + 80) = 19;
    }
    i = *(_QWORD *)(i + 64);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180024064  push    rbx
0x180024066  push    rbp
0x180024067  push    rsi
0x180024068  push    rdi
0x180024069  push    r12
0x18002406b  push    r14
0x18002406d  push    r15
0x18002406f  sub     rsp, 20h
0x180024073  mov     ebp, edx
0x180024075  mov     rdi, rcx
0x180024078  mov     rbx, rcx
0x18002407b  test    rcx, rcx
0x18002407e  jz      short loc_180024093
0x180024080  mov     eax, [rbx+8]
0x180024083  add     eax, 14h
0x180024086  cmp     ebp, eax
0x180024088  jb      short loc_180024093
0x18002408a  mov     rbx, [rbx+40h]
0x18002408e  test    rbx, rbx
0x180024091  jnz     short loc_180024080
0x180024093  mov     rax, [rcx+48h]
0x180024097  xor     r12d, r12d
0x18002409a  test    rax, rax
0x18002409d  jz      short loc_1800240BB
0x18002409f  mov     edx, [rcx+50h]
0x1800240a2  mov     ecx, [rax+8]
0x1800240a5  add     ecx, edx
0x1800240a7  cmp     ebp, ecx
0x1800240a9  jnb     short loc_1800240BB
0x1800240ab  test    edx, edx
0x1800240ad  jnz     short loc_1800240B5
0x1800240af  lea     r12d, [rdx+1]
0x1800240b3  jmp     short loc_1800240BB
0x1800240b5  lea     eax, [rdx-1]
0x1800240b8  mov     [rdi+50h], eax
0x1800240bb  xor     r14d, r14d
0x1800240be  jmp     loc_1800241A7
0x1800240c3  mov     edx, [rbx+8]
0x1800240c6  cmp     ebp, edx
0x1800240c8  jb      short loc_1800240D6
0x1800240ca  mov     esi, ebp
0x1800240cc  mov     r15d, 1
0x1800240d2  sub     esi, edx
0x1800240d4  jmp     short loc_180024100
0x1800240d6  mov     al, [rbx+12h]
0x1800240d9  xor     r15d, r15d
0x1800240dc  xor     esi, esi
0x1800240de  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KG$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,ushort,20,0>::s_bSingleBitMasks
0x1800240e4  jz      short loc_180024100
0x1800240e6  movzx   r8d, word ptr [rbx+16h]
0x1800240eb  dec     edx
0x1800240ed  mov     rcx, rdi
0x1800240f0  call    ?SetValue@?$CTSparseBlock@KG$0BE@$0A@@@QEAAJKG@Z; CTSparseBlock<ulong,ushort,20,0>::SetValue(ulong,ushort)
0x1800240f5  mov     r14d, eax
0x1800240f8  test    eax, eax
0x1800240fa  js      loc_1800241B0
0x180024100  mov     r8d, 13h
0x180024106  mov     ecx, esi
0x180024108  add     rcx, 0Bh
0x18002410c  lea     edx, [rsi+1]
0x18002410f  sub     r8d, esi
0x180024112  lea     rdx, [rdx+0Bh]
0x180024116  add     r8, r8; Size
0x180024119  lea     rdx, [rbx+rdx*2]; Src
0x18002411d  lea     rcx, [rbx+rcx*2]; void *
0x180024121  call    memmove_0
0x180024126  mov     eax, esi
0x180024128  shr     eax, 3
0x18002412b  mov     edx, eax
0x18002412d  lea     r10, [rax+rbx]
0x180024131  mov     r11b, [r10+12h]
0x180024135  cmp     eax, 3
0x180024138  jnb     short loc_180024159
0x18002413a  shl     byte ptr [rdx+rbx+12h], 1
0x18002413e  cmp     edx, 2
0x180024141  jnb     short loc_180024152
0x180024143  lea     eax, [rdx+1]
0x180024146  cmp     byte ptr [rax+rbx+12h], 0
0x18002414b  jge     short loc_180024152
0x18002414d  or      byte ptr [rdx+rbx+12h], 1
0x180024152  inc     edx
0x180024154  cmp     edx, 3
0x180024157  jb      short loc_18002413A
0x180024159  test    r15d, r15d
0x18002415c  jz      short loc_180024189
0x18002415e  and     sil, 7
0x180024162  jbe     short loc_180024189
0x180024164  movzx   ecx, sil
0x180024168  lea     rax, qword_18004A2E0
0x18002416f  sub     rax, rcx
0x180024172  mov     al, [rax]
0x180024174  and     [r10+12h], al
0x180024178  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KG$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,ushort,20,0>::s_bLeftBitMasks
0x18002417f  mov     al, [rcx+rax]
0x180024182  and     al, r11b
0x180024185  or      [r10+12h], al
0x180024189  test    r12d, r12d
0x18002418c  jz      short loc_1800241A3
0x18002418e  mov     rax, [rdi+48h]
0x180024192  cmp     [rbx+40h], rax
0x180024196  jnz     short loc_1800241A3
0x180024198  mov     [rdi+48h], rbx
0x18002419c  mov     dword ptr [rdi+50h], 13h
0x1800241a3  mov     rbx, [rbx+40h]
0x1800241a7  test    rbx, rbx
0x1800241aa  jnz     loc_1800240C3
0x1800241b0  mov     eax, r14d
0x1800241b3  add     rsp, 20h
0x1800241b7  pop     r15
0x1800241b9  pop     r14
0x1800241bb  pop     r12
0x1800241bd  pop     rdi
0x1800241be  pop     rsi
0x1800241bf  pop     rbp
0x1800241c0  pop     rbx
0x1800241c1  retn
```
