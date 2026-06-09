# CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::RemoveValue(ulong)

- ea: `0x1800095e8`
- end: `0x180009761`
- name: `?RemoveValue@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJK@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800094c0`

## callees

- `0x1800095e8`
- `0x180009854`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::RemoveValue(__int64 a1, unsigned int a2)
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

  for ( i = a1; i; i = *(_QWORD *)(i + 192) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 200);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 208);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 208) = v7 - 1;
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
      if ( (*(_BYTE *)(i + 24) & CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::s_bSingleBitMasks[0]) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::SetValue(a1, v9 - 1, *(_QWORD *)(i + 32));
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 8 * (v11 + 4LL)), (const void *)(i + 8 * (v11 + 1 + 4LL)), 8LL * (19 - v11));
    v12 = v11 >> 3;
    v13 = v12;
    v14 = v12 + i;
    for ( j = *(_BYTE *)(v12 + i + 24); (unsigned int)v13 < 3; v13 = (unsigned int)(v13 + 1) )
    {
      *(_BYTE *)(v13 + i + 24) *= 2;
      if ( (unsigned int)v13 < 2 && *(char *)((unsigned int)(v13 + 1) + i + 24) < 0 )
        *(_BYTE *)(v13 + i + 24) |= 1u;
    }
    if ( v10 )
    {
      v16 = v11 & 7;
      if ( v16 )
      {
        *(_BYTE *)(v14 + 24) &= *((_BYTE *)&qword_18004A180 - v16);
        *(_BYTE *)(v14 + 24) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::s_bLeftBitMasks
                                + v16);
      }
    }
    if ( v6 && *(_QWORD *)(i + 192) == *(_QWORD *)(a1 + 200) )
    {
      *(_QWORD *)(a1 + 200) = i;
      *(_DWORD *)(a1 + 208) = 19;
    }
    i = *(_QWORD *)(i + 192);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800095e8  push    rbx
0x1800095ea  push    rbp
0x1800095eb  push    rsi
0x1800095ec  push    rdi
0x1800095ed  push    r12
0x1800095ef  push    r14
0x1800095f1  push    r15
0x1800095f3  sub     rsp, 20h
0x1800095f7  mov     ebp, edx
0x1800095f9  mov     rdi, rcx
0x1800095fc  mov     rbx, rcx
0x1800095ff  test    rcx, rcx
0x180009602  jz      short loc_18000961A
0x180009604  mov     eax, [rbx+8]
0x180009607  add     eax, 14h
0x18000960a  cmp     ebp, eax
0x18000960c  jb      short loc_18000961A
0x18000960e  mov     rbx, [rbx+0C0h]
0x180009615  test    rbx, rbx
0x180009618  jnz     short loc_180009604
0x18000961a  mov     rax, [rcx+0C8h]
0x180009621  xor     r12d, r12d
0x180009624  test    rax, rax
0x180009627  jz      short loc_18000964B
0x180009629  mov     edx, [rcx+0D0h]
0x18000962f  mov     ecx, [rax+8]
0x180009632  add     ecx, edx
0x180009634  cmp     ebp, ecx
0x180009636  jnb     short loc_18000964B
0x180009638  test    edx, edx
0x18000963a  jnz     short loc_180009642
0x18000963c  lea     r12d, [rdx+1]
0x180009640  jmp     short loc_18000964B
0x180009642  lea     eax, [rdx-1]
0x180009645  mov     [rdi+0D0h], eax
0x18000964b  xor     r14d, r14d
0x18000964e  jmp     loc_180009746
0x180009653  mov     edx, [rbx+8]
0x180009656  cmp     ebp, edx
0x180009658  jb      short loc_180009666
0x18000965a  mov     esi, ebp
0x18000965c  mov     r15d, 1
0x180009662  sub     esi, edx
0x180009664  jmp     short loc_18000968F
0x180009666  mov     al, [rbx+18h]
0x180009669  xor     r15d, r15d
0x18000966c  xor     esi, esi
0x18000966e  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::s_bSingleBitMasks
0x180009674  jz      short loc_18000968F
0x180009676  mov     r8, [rbx+20h]
0x18000967a  dec     edx
0x18000967c  mov     rcx, rdi
0x18000967f  call    ?SetValue@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJKPEAUIASFReadWriteTracker@@@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::SetValue(ulong,IASFReadWriteTracker *)
0x180009684  mov     r14d, eax
0x180009687  test    eax, eax
0x180009689  js      loc_18000974F
0x18000968f  mov     r8d, 13h
0x180009695  mov     ecx, esi
0x180009697  add     rcx, 4
0x18000969b  lea     edx, [rsi+1]
0x18000969e  sub     r8d, esi
0x1800096a1  lea     rdx, [rdx+4]
0x1800096a5  shl     r8, 3; Size
0x1800096a9  lea     rdx, [rbx+rdx*8]; Src
0x1800096ad  lea     rcx, [rbx+rcx*8]; void *
0x1800096b1  call    memmove_0
0x1800096b6  mov     eax, esi
0x1800096b8  shr     eax, 3
0x1800096bb  mov     edx, eax
0x1800096bd  lea     r10, [rax+rbx]
0x1800096c1  mov     r11b, [r10+18h]
0x1800096c5  cmp     eax, 3
0x1800096c8  jnb     short loc_1800096E9
0x1800096ca  shl     byte ptr [rdx+rbx+18h], 1
0x1800096ce  cmp     edx, 2
0x1800096d1  jnb     short loc_1800096E2
0x1800096d3  lea     eax, [rdx+1]
0x1800096d6  cmp     byte ptr [rax+rbx+18h], 0
0x1800096db  jge     short loc_1800096E2
0x1800096dd  or      byte ptr [rdx+rbx+18h], 1
0x1800096e2  inc     edx
0x1800096e4  cmp     edx, 3
0x1800096e7  jb      short loc_1800096CA
0x1800096e9  test    r15d, r15d
0x1800096ec  jz      short loc_180009719
0x1800096ee  and     sil, 7
0x1800096f2  jbe     short loc_180009719
0x1800096f4  movzx   ecx, sil
0x1800096f8  lea     rax, qword_18004A180
0x1800096ff  sub     rax, rcx
0x180009702  mov     al, [rax]
0x180009704  and     [r10+18h], al
0x180009708  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::s_bLeftBitMasks
0x18000970f  mov     al, [rcx+rax]
0x180009712  and     al, r11b
0x180009715  or      [r10+18h], al
0x180009719  test    r12d, r12d
0x18000971c  jz      short loc_18000973F
0x18000971e  mov     rax, [rdi+0C8h]
0x180009725  cmp     [rbx+0C0h], rax
0x18000972c  jnz     short loc_18000973F
0x18000972e  mov     [rdi+0C8h], rbx
0x180009735  mov     dword ptr [rdi+0D0h], 13h
0x18000973f  mov     rbx, [rbx+0C0h]
0x180009746  test    rbx, rbx
0x180009749  jnz     loc_180009653
0x18000974f  mov     eax, r14d
0x180009752  add     rsp, 20h
0x180009756  pop     r15
0x180009758  pop     r14
0x18000975a  pop     r12
0x18000975c  pop     rdi
0x18000975d  pop     rsi
0x18000975e  pop     rbp
0x18000975f  pop     rbx
0x180009760  retn
```
