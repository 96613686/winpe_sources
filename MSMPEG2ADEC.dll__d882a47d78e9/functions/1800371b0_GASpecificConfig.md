# GASpecificConfig

- ea: `0x1800371b0`
- end: `0x1800373a0`
- name: `GASpecificConfig`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180036c60`

## callees

- `0x1800021a8`
- `0x1800363f0`
- `0x1800371b0`
- `0x180037930`

## pseudocode

```c
__int64 __fastcall GASpecificConfig(int *a1, unsigned int *a2, int a3, unsigned int a4)
{
  bool v8; // zf
  int v9; // eax
  int v10; // eax

  memset_0(a2, 0, 0xE0u);
  if ( !*a1 )
    FillBitCache(a1, 1u);
  *a2 = ((unsigned int)a1[1] >> --*a1) & 1;
  if ( !*a1 )
    FillBitCache(a1, 1u);
  v8 = (((unsigned int)a1[1] >> --*a1) & 1) == 0;
  a2[1] = ((unsigned int)a1[1] >> *a1) & 1;
  if ( !v8 )
  {
    if ( (unsigned int)*a1 < 0xE )
      FillBitCache(a1, 0xEu);
    *a1 -= 14;
    a2[2] = ((unsigned int)a1[1] >> *a1) & 0x3FFF;
  }
  if ( !*a1 )
    FillBitCache(a1, 1u);
  a2[3] = ((unsigned int)a1[1] >> --*a1) & 1;
  if ( !a3 )
    CProgramCfg_Read((_BYTE *)a2 + 44, a1);
  if ( a4 == 6 || a4 == 20 )
  {
    if ( (unsigned int)*a1 < 3 )
      FillBitCache(a1, 3u);
    *a1 -= 3;
    a2[5] = ((unsigned int)a1[1] >> *a1) & 7;
  }
  if ( !a2[3] )
    return 0;
  if ( a4 == 22 )
  {
    if ( (unsigned int)*a1 < 5 )
      FillBitCache(a1, 5u);
    *a1 -= 5;
    a2[6] = ((unsigned int)a1[1] >> *a1) & 0x1F;
    if ( (unsigned int)*a1 < 0xB )
      FillBitCache(a1, 0xBu);
    *a1 -= 11;
    a2[7] = ((unsigned int)a1[1] >> *a1) & 0x7FF;
  }
  else if ( a4 <= 0x17 )
  {
    v9 = 10092544;
    if ( _bittest(&v9, a4) )
    {
      if ( !*a1 )
        FillBitCache(a1, 1u);
      a2[8] = ((unsigned int)a1[1] >> --*a1) & 1;
      if ( !*a1 )
        FillBitCache(a1, 1u);
      a2[9] = ((unsigned int)a1[1] >> --*a1) & 1;
      if ( !*a1 )
        FillBitCache(a1, 1u);
      a2[10] = ((unsigned int)a1[1] >> --*a1) & 1;
    }
  }
  if ( !*a1 )
    FillBitCache(a1, 1u);
  v10 = ((unsigned int)a1[1] >> --*a1) & 1;
  a2[4] = v10;
  return v10 != 0 ? 0xFFFFFFF3 : 0;
}

```

## disassembly

```asm
0x1800371b0  push    rbx
0x1800371b2  push    rbp
0x1800371b3  push    rsi
0x1800371b4  push    rdi
0x1800371b5  sub     rsp, 28h
0x1800371b9  mov     rdi, rdx
0x1800371bc  mov     ebp, r8d
0x1800371bf  mov     rbx, rcx
0x1800371c2  xor     edx, edx; Val
0x1800371c4  mov     rcx, rdi; void *
0x1800371c7  mov     r8d, 0E0h; Size
0x1800371cd  mov     esi, r9d
0x1800371d0  call    memset_0
0x1800371d5  cmp     dword ptr [rbx], 1
0x1800371d8  jnb     short loc_1800371E7
0x1800371da  mov     edx, 1
0x1800371df  mov     rcx, rbx
0x1800371e2  call    FillBitCache
0x1800371e7  dec     dword ptr [rbx]
0x1800371e9  mov     eax, [rbx+4]
0x1800371ec  mov     ecx, [rbx]
0x1800371ee  shr     eax, cl
0x1800371f0  and     eax, 1
0x1800371f3  mov     [rdi], eax
0x1800371f5  cmp     dword ptr [rbx], 1
0x1800371f8  jnb     short loc_180037207
0x1800371fa  mov     edx, 1
0x1800371ff  mov     rcx, rbx
0x180037202  call    FillBitCache
0x180037207  dec     dword ptr [rbx]
0x180037209  mov     eax, [rbx+4]
0x18003720c  mov     ecx, [rbx]
0x18003720e  shr     eax, cl
0x180037210  and     eax, 1
0x180037213  mov     [rdi+4], eax
0x180037216  jz      short loc_18003723C
0x180037218  cmp     dword ptr [rbx], 0Eh
0x18003721b  jnb     short loc_18003722A
0x18003721d  mov     edx, 0Eh
0x180037222  mov     rcx, rbx
0x180037225  call    FillBitCache
0x18003722a  add     dword ptr [rbx], 0FFFFFFF2h
0x18003722d  mov     eax, [rbx+4]
0x180037230  mov     ecx, [rbx]
0x180037232  shr     eax, cl
0x180037234  and     eax, 3FFFh
0x180037239  mov     [rdi+8], eax
0x18003723c  cmp     dword ptr [rbx], 1
0x18003723f  jnb     short loc_18003724E
0x180037241  mov     edx, 1
0x180037246  mov     rcx, rbx
0x180037249  call    FillBitCache
0x18003724e  dec     dword ptr [rbx]
0x180037250  mov     eax, [rbx+4]
0x180037253  mov     ecx, [rbx]
0x180037255  shr     eax, cl
0x180037257  and     eax, 1
0x18003725a  mov     [rdi+0Ch], eax
0x18003725d  test    ebp, ebp
0x18003725f  jnz     short loc_18003726D
0x180037261  lea     rcx, [rdi+2Ch]
0x180037265  mov     rdx, rbx
0x180037268  call    CProgramCfg_Read
0x18003726d  cmp     esi, 6
0x180037270  jz      short loc_180037277
0x180037272  cmp     esi, 14h
0x180037275  jnz     short loc_180037299
0x180037277  cmp     dword ptr [rbx], 3
0x18003727a  jnb     short loc_180037289
0x18003727c  mov     edx, 3
0x180037281  mov     rcx, rbx
0x180037284  call    FillBitCache
0x180037289  add     dword ptr [rbx], 0FFFFFFFDh
0x18003728c  mov     eax, [rbx+4]
0x18003728f  mov     ecx, [rbx]
0x180037291  shr     eax, cl
0x180037293  and     eax, 7
0x180037296  mov     [rdi+14h], eax
0x180037299  cmp     dword ptr [rdi+0Ch], 0
0x18003729d  jz      loc_180037394
0x1800372a3  cmp     esi, 16h
0x1800372a6  jnz     short loc_1800372F0
0x1800372a8  cmp     dword ptr [rbx], 5
0x1800372ab  jnb     short loc_1800372BA
0x1800372ad  mov     edx, 5
0x1800372b2  mov     rcx, rbx
0x1800372b5  call    FillBitCache
0x1800372ba  add     dword ptr [rbx], 0FFFFFFFBh
0x1800372bd  mov     eax, [rbx+4]
0x1800372c0  mov     ecx, [rbx]
0x1800372c2  shr     eax, cl
0x1800372c4  and     eax, 1Fh
0x1800372c7  mov     [rdi+18h], eax
0x1800372ca  cmp     dword ptr [rbx], 0Bh
0x1800372cd  jnb     short loc_1800372DC
0x1800372cf  mov     edx, 0Bh
0x1800372d4  mov     rcx, rbx
0x1800372d7  call    FillBitCache
0x1800372dc  add     dword ptr [rbx], 0FFFFFFF5h
0x1800372df  mov     eax, [rbx+4]
0x1800372e2  mov     ecx, [rbx]
0x1800372e4  shr     eax, cl
0x1800372e6  and     eax, 7FFh
0x1800372eb  mov     [rdi+1Ch], eax
0x1800372ee  jmp     short loc_180037362
0x1800372f0  cmp     esi, 17h
0x1800372f3  ja      short loc_180037362
0x1800372f5  mov     eax, 9A0000h
0x1800372fa  bt      eax, esi
0x1800372fd  jnb     short loc_180037362
0x1800372ff  cmp     dword ptr [rbx], 1
0x180037302  jnb     short loc_180037311
0x180037304  mov     edx, 1
0x180037309  mov     rcx, rbx
0x18003730c  call    FillBitCache
0x180037311  dec     dword ptr [rbx]
0x180037313  mov     eax, [rbx+4]
0x180037316  mov     ecx, [rbx]
0x180037318  shr     eax, cl
0x18003731a  and     eax, 1
0x18003731d  mov     [rdi+20h], eax
0x180037320  cmp     dword ptr [rbx], 1
0x180037323  jnb     short loc_180037332
0x180037325  mov     edx, 1
0x18003732a  mov     rcx, rbx
0x18003732d  call    FillBitCache
0x180037332  dec     dword ptr [rbx]
0x180037334  mov     eax, [rbx+4]
0x180037337  mov     ecx, [rbx]
0x180037339  shr     eax, cl
0x18003733b  and     eax, 1
0x18003733e  mov     [rdi+24h], eax
0x180037341  cmp     dword ptr [rbx], 1
0x180037344  jnb     short loc_180037353
0x180037346  mov     edx, 1
0x18003734b  mov     rcx, rbx
0x18003734e  call    FillBitCache
0x180037353  dec     dword ptr [rbx]
0x180037355  mov     eax, [rbx+4]
0x180037358  mov     ecx, [rbx]
0x18003735a  shr     eax, cl
0x18003735c  and     eax, 1
0x18003735f  mov     [rdi+28h], eax
0x180037362  cmp     dword ptr [rbx], 1
0x180037365  jnb     short loc_180037374
0x180037367  mov     edx, 1
0x18003736c  mov     rcx, rbx
0x18003736f  call    FillBitCache
0x180037374  dec     dword ptr [rbx]
0x180037376  mov     eax, [rbx+4]
0x180037379  mov     ecx, [rbx]
0x18003737b  shr     eax, cl
0x18003737d  and     eax, 1
0x180037380  mov     [rdi+10h], eax
0x180037383  neg     eax
0x180037385  sbb     eax, eax
0x180037387  and     eax, 0FFFFFFF3h
0x18003738a  add     rsp, 28h
0x18003738e  pop     rdi
0x18003738f  pop     rsi
0x180037390  pop     rbp
0x180037391  pop     rbx
0x180037392  retn
0x180037394  xor     eax, eax
0x180037396  add     rsp, 28h
0x18003739a  pop     rdi
0x18003739b  pop     rsi
0x18003739c  pop     rbp
0x18003739d  pop     rbx
0x18003739e  retn
```
