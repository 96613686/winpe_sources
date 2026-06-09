# CTSparseBlock<ulong,unsigned __int64,20,0>::RemoveValue(ulong)

- ea: `0x180029320`
- end: `0x180029499`
- name: `?RemoveValue@?$CTSparseBlock@K_K$0BE@$0A@@@QEAAJK@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029100`

## callees

- `0x180029320`
- `0x18002982c`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,unsigned __int64,20,0>::RemoveValue(__int64 a1, unsigned int a2)
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
      if ( (*(_BYTE *)(i + 24) & (unsigned __int8)CTSparseBlock<unsigned long,unsigned __int64,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,unsigned __int64,20,0>::SetValue(a1, v9 - 1, *(_QWORD *)(i + 32));
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
        *(_BYTE *)(v14 + 24) &= *((_BYTE *)&qword_18004A398 - v16);
        *(_BYTE *)(v14 + 24) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,unsigned __int64,20,0>::s_bLeftBitMasks + v16);
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
0x180029320  push    rbx
0x180029322  push    rbp
0x180029323  push    rsi
0x180029324  push    rdi
0x180029325  push    r12
0x180029327  push    r14
0x180029329  push    r15
0x18002932b  sub     rsp, 20h
0x18002932f  mov     ebp, edx
0x180029331  mov     rdi, rcx
0x180029334  mov     rbx, rcx
0x180029337  test    rcx, rcx
0x18002933a  jz      short loc_180029352
0x18002933c  mov     eax, [rbx+8]
0x18002933f  add     eax, 14h
0x180029342  cmp     ebp, eax
0x180029344  jb      short loc_180029352
0x180029346  mov     rbx, [rbx+0C0h]
0x18002934d  test    rbx, rbx
0x180029350  jnz     short loc_18002933C
0x180029352  mov     rax, [rcx+0C8h]
0x180029359  xor     r12d, r12d
0x18002935c  test    rax, rax
0x18002935f  jz      short loc_180029383
0x180029361  mov     edx, [rcx+0D0h]
0x180029367  mov     ecx, [rax+8]
0x18002936a  add     ecx, edx
0x18002936c  cmp     ebp, ecx
0x18002936e  jnb     short loc_180029383
0x180029370  test    edx, edx
0x180029372  jnz     short loc_18002937A
0x180029374  lea     r12d, [rdx+1]
0x180029378  jmp     short loc_180029383
0x18002937a  lea     eax, [rdx-1]
0x18002937d  mov     [rdi+0D0h], eax
0x180029383  xor     r14d, r14d
0x180029386  jmp     loc_18002947E
0x18002938b  mov     edx, [rbx+8]
0x18002938e  cmp     ebp, edx
0x180029390  jb      short loc_18002939E
0x180029392  mov     esi, ebp
0x180029394  mov     r15d, 1
0x18002939a  sub     esi, edx
0x18002939c  jmp     short loc_1800293C7
0x18002939e  mov     al, [rbx+18h]
0x1800293a1  xor     r15d, r15d
0x1800293a4  xor     esi, esi
0x1800293a6  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@K_K$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,unsigned __int64,20,0>::s_bSingleBitMasks
0x1800293ac  jz      short loc_1800293C7
0x1800293ae  mov     r8, [rbx+20h]
0x1800293b2  dec     edx
0x1800293b4  mov     rcx, rdi
0x1800293b7  call    ?SetValue@?$CTSparseBlock@K_K$0BE@$0A@@@QEAAJK_K@Z; CTSparseBlock<ulong,unsigned __int64,20,0>::SetValue(ulong,unsigned __int64)
0x1800293bc  mov     r14d, eax
0x1800293bf  test    eax, eax
0x1800293c1  js      loc_180029487
0x1800293c7  mov     r8d, 13h
0x1800293cd  mov     ecx, esi
0x1800293cf  add     rcx, 4
0x1800293d3  lea     edx, [rsi+1]
0x1800293d6  sub     r8d, esi
0x1800293d9  lea     rdx, [rdx+4]
0x1800293dd  shl     r8, 3; Size
0x1800293e1  lea     rdx, [rbx+rdx*8]; Src
0x1800293e5  lea     rcx, [rbx+rcx*8]; void *
0x1800293e9  call    memmove_0
0x1800293ee  mov     eax, esi
0x1800293f0  shr     eax, 3
0x1800293f3  mov     edx, eax
0x1800293f5  lea     r10, [rax+rbx]
0x1800293f9  mov     r11b, [r10+18h]
0x1800293fd  cmp     eax, 3
0x180029400  jnb     short loc_180029421
0x180029402  shl     byte ptr [rdx+rbx+18h], 1
0x180029406  cmp     edx, 2
0x180029409  jnb     short loc_18002941A
0x18002940b  lea     eax, [rdx+1]
0x18002940e  cmp     byte ptr [rax+rbx+18h], 0
0x180029413  jge     short loc_18002941A
0x180029415  or      byte ptr [rdx+rbx+18h], 1
0x18002941a  inc     edx
0x18002941c  cmp     edx, 3
0x18002941f  jb      short loc_180029402
0x180029421  test    r15d, r15d
0x180029424  jz      short loc_180029451
0x180029426  and     sil, 7
0x18002942a  jbe     short loc_180029451
0x18002942c  movzx   ecx, sil
0x180029430  lea     rax, qword_18004A398
0x180029437  sub     rax, rcx
0x18002943a  mov     al, [rax]
0x18002943c  and     [r10+18h], al
0x180029440  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@K_K$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,unsigned __int64,20,0>::s_bLeftBitMasks
0x180029447  mov     al, [rcx+rax]
0x18002944a  and     al, r11b
0x18002944d  or      [r10+18h], al
0x180029451  test    r12d, r12d
0x180029454  jz      short loc_180029477
0x180029456  mov     rax, [rdi+0C8h]
0x18002945d  cmp     [rbx+0C0h], rax
0x180029464  jnz     short loc_180029477
0x180029466  mov     [rdi+0C8h], rbx
0x18002946d  mov     dword ptr [rdi+0D0h], 13h
0x180029477  mov     rbx, [rbx+0C0h]
0x18002947e  test    rbx, rbx
0x180029481  jnz     loc_18002938B
0x180029487  mov     eax, r14d
0x18002948a  add     rsp, 20h
0x18002948e  pop     r15
0x180029490  pop     r14
0x180029492  pop     r12
0x180029494  pop     rdi
0x180029495  pop     rsi
0x180029496  pop     rbp
0x180029497  pop     rbx
0x180029498  retn
```
