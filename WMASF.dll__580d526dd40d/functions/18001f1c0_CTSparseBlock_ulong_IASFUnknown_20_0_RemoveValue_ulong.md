# CTSparseBlock<ulong,IASFUnknown *,20,0>::RemoveValue(ulong)

- ea: `0x18001f1c0`
- end: `0x18001f339`
- name: `?RemoveValue@?$CTSparseBlock@KPEAUIASFUnknown@@$0BE@$0A@@@QEAAJK@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ef88`

## callees

- `0x18001f1c0`
- `0x18001f340`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,IASFUnknown *,20,0>::RemoveValue(__int64 a1, unsigned int a2)
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
      if ( (*(_BYTE *)(i + 24) & (unsigned __int8)CTSparseBlock<unsigned long,IASFUnknown *,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,IASFUnknown *,20,0>::SetValue(a1, v9 - 1, *(_QWORD *)(i + 32));
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
        *(_BYTE *)(v14 + 24) &= *((_BYTE *)&qword_18004A210 - v16);
        *(_BYTE *)(v14 + 24) |= j & CTSparseBlock<unsigned long,IASFUnknown *,20,0>::s_bLeftBitMasks[v16];
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
0x18001f1c0  push    rbx
0x18001f1c2  push    rbp
0x18001f1c3  push    rsi
0x18001f1c4  push    rdi
0x18001f1c5  push    r12
0x18001f1c7  push    r14
0x18001f1c9  push    r15
0x18001f1cb  sub     rsp, 20h
0x18001f1cf  mov     ebp, edx
0x18001f1d1  mov     rdi, rcx
0x18001f1d4  mov     rbx, rcx
0x18001f1d7  test    rcx, rcx
0x18001f1da  jz      short loc_18001F1F2
0x18001f1dc  mov     eax, [rbx+8]
0x18001f1df  add     eax, 14h
0x18001f1e2  cmp     ebp, eax
0x18001f1e4  jb      short loc_18001F1F2
0x18001f1e6  mov     rbx, [rbx+0C0h]
0x18001f1ed  test    rbx, rbx
0x18001f1f0  jnz     short loc_18001F1DC
0x18001f1f2  mov     rax, [rcx+0C8h]
0x18001f1f9  xor     r12d, r12d
0x18001f1fc  test    rax, rax
0x18001f1ff  jz      short loc_18001F223
0x18001f201  mov     edx, [rcx+0D0h]
0x18001f207  mov     ecx, [rax+8]
0x18001f20a  add     ecx, edx
0x18001f20c  cmp     ebp, ecx
0x18001f20e  jnb     short loc_18001F223
0x18001f210  test    edx, edx
0x18001f212  jnz     short loc_18001F21A
0x18001f214  lea     r12d, [rdx+1]
0x18001f218  jmp     short loc_18001F223
0x18001f21a  lea     eax, [rdx-1]
0x18001f21d  mov     [rdi+0D0h], eax
0x18001f223  xor     r14d, r14d
0x18001f226  jmp     loc_18001F31E
0x18001f22b  mov     edx, [rbx+8]
0x18001f22e  cmp     ebp, edx
0x18001f230  jb      short loc_18001F23E
0x18001f232  mov     esi, ebp
0x18001f234  mov     r15d, 1
0x18001f23a  sub     esi, edx
0x18001f23c  jmp     short loc_18001F267
0x18001f23e  mov     al, [rbx+18h]
0x18001f241  xor     r15d, r15d
0x18001f244  xor     esi, esi
0x18001f246  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KPEAUIASFUnknown@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,IASFUnknown *,20,0>::s_bSingleBitMasks
0x18001f24c  jz      short loc_18001F267
0x18001f24e  mov     r8, [rbx+20h]
0x18001f252  dec     edx
0x18001f254  mov     rcx, rdi
0x18001f257  call    ?SetValue@?$CTSparseBlock@KPEAUIASFUnknown@@$0BE@$0A@@@QEAAJKPEAUIASFUnknown@@@Z; CTSparseBlock<ulong,IASFUnknown *,20,0>::SetValue(ulong,IASFUnknown *)
0x18001f25c  mov     r14d, eax
0x18001f25f  test    eax, eax
0x18001f261  js      loc_18001F327
0x18001f267  mov     r8d, 13h
0x18001f26d  mov     ecx, esi
0x18001f26f  add     rcx, 4
0x18001f273  lea     edx, [rsi+1]
0x18001f276  sub     r8d, esi
0x18001f279  lea     rdx, [rdx+4]
0x18001f27d  shl     r8, 3; Size
0x18001f281  lea     rdx, [rbx+rdx*8]; Src
0x18001f285  lea     rcx, [rbx+rcx*8]; void *
0x18001f289  call    memmove_0
0x18001f28e  mov     eax, esi
0x18001f290  shr     eax, 3
0x18001f293  mov     edx, eax
0x18001f295  lea     r10, [rax+rbx]
0x18001f299  mov     r11b, [r10+18h]
0x18001f29d  cmp     eax, 3
0x18001f2a0  jnb     short loc_18001F2C1
0x18001f2a2  shl     byte ptr [rdx+rbx+18h], 1
0x18001f2a6  cmp     edx, 2
0x18001f2a9  jnb     short loc_18001F2BA
0x18001f2ab  lea     eax, [rdx+1]
0x18001f2ae  cmp     byte ptr [rax+rbx+18h], 0
0x18001f2b3  jge     short loc_18001F2BA
0x18001f2b5  or      byte ptr [rdx+rbx+18h], 1
0x18001f2ba  inc     edx
0x18001f2bc  cmp     edx, 3
0x18001f2bf  jb      short loc_18001F2A2
0x18001f2c1  test    r15d, r15d
0x18001f2c4  jz      short loc_18001F2F1
0x18001f2c6  and     sil, 7
0x18001f2ca  jbe     short loc_18001F2F1
0x18001f2cc  movzx   ecx, sil
0x18001f2d0  lea     rax, qword_18004A210
0x18001f2d7  sub     rax, rcx
0x18001f2da  mov     al, [rax]
0x18001f2dc  and     [r10+18h], al
0x18001f2e0  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAUIASFUnknown@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,IASFUnknown *,20,0>::s_bLeftBitMasks
0x18001f2e7  mov     al, [rcx+rax]
0x18001f2ea  and     al, r11b
0x18001f2ed  or      [r10+18h], al
0x18001f2f1  test    r12d, r12d
0x18001f2f4  jz      short loc_18001F317
0x18001f2f6  mov     rax, [rdi+0C8h]
0x18001f2fd  cmp     [rbx+0C0h], rax
0x18001f304  jnz     short loc_18001F317
0x18001f306  mov     [rdi+0C8h], rbx
0x18001f30d  mov     dword ptr [rdi+0D0h], 13h
0x18001f317  mov     rbx, [rbx+0C0h]
0x18001f31e  test    rbx, rbx
0x18001f321  jnz     loc_18001F22B
0x18001f327  mov     eax, r14d
0x18001f32a  add     rsp, 20h
0x18001f32e  pop     r15
0x18001f330  pop     r14
0x18001f332  pop     r12
0x18001f334  pop     rdi
0x18001f335  pop     rsi
0x18001f336  pop     rbp
0x18001f337  pop     rbx
0x18001f338  retn
```
