# CspWriteCharacter

- ea: `0x1400212a4`
- end: `0x1400213b6`
- name: `CspWriteCharacter`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140021b8c`
- `0x140021be0`

## callees

- `0x14002123c`
- `0x1400212a4`

## pseudocode

```c
__int16 __fastcall CspWriteCharacter(__int64 a1, __int64 a2)
{
  __int64 v2; // r11
  __int16 *v3; // rbx
  __int16 v4; // ax
  __int16 v5; // ax
  __int64 v6; // r8
  int v7; // ecx
  int v8; // eax
  unsigned __int16 v9; // dx
  _WORD *v10; // rdx
  _WORD *v11; // rcx

  v2 = a1;
  if ( (unsigned __int16)a2 >= 0x20u )
  {
    CspUpdateCharacter(a1, a2);
    v3 = (__int16 *)(v2 + 28);
    ++*(_WORD *)(v2 + 28);
    goto LABEL_13;
  }
  if ( (_WORD)a2 == 8 )
  {
    v3 = (__int16 *)(a1 + 28);
    v4 = *(_WORD *)(a1 + 28);
    if ( v4 <= 0 )
    {
      v5 = *(_WORD *)(a1 + 30);
      if ( v5 <= 0 )
        goto LABEL_13;
      *(_WORD *)(a1 + 30) = v5 - 1;
      v4 = *(_WORD *)(a1 + 32);
    }
    *v3 = v4 - 1;
    CspUpdateCharacter(a1, 32);
  }
  else
  {
    if ( (_WORD)a2 == 10 )
    {
      ++*(_WORD *)(a1 + 30);
    }
    else if ( (_WORD)a2 != 13 )
    {
      v3 = (__int16 *)(a1 + 28);
      goto LABEL_13;
    }
    v3 = (__int16 *)(a1 + 28);
    *(_BYTE *)(a1 + 19) = 1;
    *(_WORD *)(a1 + 28) = 0;
  }
LABEL_13:
  v6 = *(unsigned __int16 *)(v2 + 32);
  if ( *v3 >= (int)v6 )
  {
    ++*(_WORD *)(v2 + 30);
    *v3 = 0;
  }
  v7 = *(unsigned __int16 *)(v2 + 34);
  v8 = *(__int16 *)(v2 + 30);
  if ( v8 >= v7 )
  {
    v9 = ((unsigned int)*(unsigned __int16 *)(v2 + 16) + 1) % v7;
    *(_WORD *)(v2 + 16) = v9;
    v10 = (_WORD *)(*(_QWORD *)(v2 + 48) + 4LL * (unsigned int)v6 * ((v7 + (unsigned int)v9 - 1) % v7));
    v11 = &v10[2 * v6];
    while ( v10 < v11 )
    {
      v10[1] = *(_WORD *)(v2 + 22);
      *v10 = 32;
      v10 += 2;
    }
    LOWORD(v8) = *(_WORD *)(v2 + 34) - 1;
    if ( *(__int16 *)(v2 + 24) > 0 )
      *(_WORD *)(v2 + 24) = 0;
    if ( (__int16)v8 > *(__int16 *)(v2 + 26) )
      *(_WORD *)(v2 + 26) = v8;
    *(_WORD *)(v2 + 30) = v8;
  }
  return v8;
}

```

## disassembly

```asm
0x1400212a4  push    rbx
0x1400212a6  push    rbp
0x1400212a7  push    rsi
0x1400212a8  push    rdi
0x1400212a9  sub     rsp, 28h
0x1400212ad  mov     edi, 1
0x1400212b2  xor     esi, esi
0x1400212b4  mov     r11, rcx
0x1400212b7  lea     ebp, [rdi+1Fh]
0x1400212ba  cmp     dx, bp
0x1400212bd  jb      short loc_1400212CD
0x1400212bf  call    CspUpdateCharacter
0x1400212c4  lea     rbx, [r11+1Ch]
0x1400212c8  add     [rbx], di
0x1400212cb  jmp     short loc_140021323
0x1400212cd  cmp     dx, 8
0x1400212d1  jz      short loc_1400212F6
0x1400212d3  cmp     dx, 0Ah
0x1400212d7  jz      short loc_1400212E5
0x1400212d9  cmp     dx, 0Dh
0x1400212dd  jz      short loc_1400212E9
0x1400212df  lea     rbx, [rcx+1Ch]
0x1400212e3  jmp     short loc_140021323
0x1400212e5  add     [rcx+1Eh], di
0x1400212e9  lea     rbx, [rcx+1Ch]
0x1400212ed  mov     [rcx+13h], dil
0x1400212f1  mov     [rbx], si
0x1400212f4  jmp     short loc_140021323
0x1400212f6  lea     rbx, [rcx+1Ch]
0x1400212fa  movzx   eax, word ptr [rbx]
0x1400212fd  test    ax, ax
0x140021300  jg      short loc_140021316
0x140021302  movzx   eax, word ptr [rcx+1Eh]
0x140021306  test    ax, ax
0x140021309  jle     short loc_140021323
0x14002130b  sub     ax, di
0x14002130e  mov     [rcx+1Eh], ax
0x140021312  movzx   eax, word ptr [rcx+20h]
0x140021316  sub     ax, di
0x140021319  mov     edx, ebp
0x14002131b  mov     [rbx], ax
0x14002131e  call    CspUpdateCharacter
0x140021323  movzx   r8d, word ptr [r11+20h]
0x140021328  movsx   eax, word ptr [rbx]
0x14002132b  cmp     eax, r8d
0x14002132e  jl      short loc_140021338
0x140021330  add     [r11+1Eh], di
0x140021335  mov     [rbx], si
0x140021338  movzx   ecx, word ptr [r11+22h]
0x14002133d  movsx   eax, word ptr [r11+1Eh]
0x140021342  cmp     eax, ecx
0x140021344  jl      short loc_1400213AD
0x140021346  movzx   eax, word ptr [r11+10h]
0x14002134b  xor     edx, edx
0x14002134d  add     eax, edi
0x14002134f  div     ecx
0x140021351  movzx   eax, dx
0x140021354  dec     eax
0x140021356  mov     [r11+10h], dx
0x14002135b  add     eax, ecx
0x14002135d  xor     edx, edx
0x14002135f  div     ecx
0x140021361  mov     rax, [r11+30h]
0x140021365  imul    edx, r8d
0x140021369  lea     rdx, [rax+rdx*4]
0x14002136d  lea     rcx, [rdx+r8*4]
0x140021371  jmp     short loc_140021383
0x140021373  movzx   eax, word ptr [r11+16h]
0x140021378  mov     [rdx+2], ax
0x14002137c  mov     [rdx], bp
0x14002137f  add     rdx, 4
0x140021383  cmp     rdx, rcx
0x140021386  jb      short loc_140021373
0x140021388  movzx   eax, word ptr [r11+22h]
0x14002138d  sub     ax, di
0x140021390  cmp     si, [r11+18h]
0x140021395  jge     short loc_14002139C
0x140021397  mov     [r11+18h], si
0x14002139c  cmp     ax, [r11+1Ah]
0x1400213a1  jle     short loc_1400213A8
0x1400213a3  mov     [r11+1Ah], ax
0x1400213a8  mov     [r11+1Eh], ax
0x1400213ad  add     rsp, 28h
0x1400213b1  pop     rdi
0x1400213b2  pop     rsi
0x1400213b3  pop     rbp
0x1400213b4  pop     rbx
0x1400213b5  retn
```
