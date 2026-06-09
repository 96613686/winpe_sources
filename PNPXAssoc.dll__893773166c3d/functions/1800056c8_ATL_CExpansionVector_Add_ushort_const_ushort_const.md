# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x1800056c8`
- end: `0x18000589b`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `467`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005ab0`
- `0x1800088fc`
- `0x180008c1c`

## callees

- `0x1800019bc`
- `0x1800019c8`
- `0x180001fd0`
- `0x1800056c8`
- `0x180006764`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005771`
- `msvcrt!memcpy_s` at `0x1800057ab`
- `msvcrt!memcpy_s` at `0x180005771`
- `msvcrt!memcpy_s` at `0x1800057ab`

## pseudocode

```c
_BOOL8 __fastcall ATL::CExpansionVector::Add(void **this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // r12
  void *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r15
  void *v11; // rax
  void *v12; // rbx
  errno_t v13; // eax
  errno_t v14; // eax
  void *v15; // rax
  void *v16; // rcx
  void *v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  int v21; // esi

  if ( a2 && a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = 2 * v6 + 2;
    v8 = operator new[](saturated_mul(v7, 2u));
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2LL * ((int)v9 + 1);
    v11 = operator new[](saturated_mul(v10, 2u));
    v12 = v11;
    if ( !v8 || !v11 )
      goto LABEL_26;
    v13 = memcpy_s(v8, v7, a2, v7);
    if ( v13 )
    {
      if ( v13 == 12 )
        goto LABEL_29;
      if ( v13 == 22 || v13 == 34 )
        goto LABEL_31;
      if ( v13 != 80 )
        goto LABEL_30;
    }
    v14 = memcpy_s(v12, v10, a3, v10);
    if ( !v14 )
    {
LABEL_19:
      v15 = _recalloc(*this, *((_DWORD *)this + 4) + 1, 8u);
      if ( v15 )
      {
        v16 = this[1];
        *this = v15;
        v17 = _recalloc(v16, *((_DWORD *)this + 4) + 1, 8u);
        if ( v17 )
        {
          v18 = *((int *)this + 4);
          this[1] = v17;
          v19 = (char *)*this + 8 * v18;
          if ( v19 )
            *v19 = v8;
          v20 = (char *)this[1] + 8 * v18;
          if ( v20 )
            *v20 = v12;
          ++*((_DWORD *)this + 4);
          v8 = 0;
          v21 = 0;
          v12 = 0;
          goto LABEL_27;
        }
      }
LABEL_26:
      v21 = -2147024882;
LABEL_27:
      operator delete[](v12);
      operator delete[](v8);
      return v21 >= 0;
    }
    if ( v14 != 12 )
    {
      if ( v14 != 22 && v14 != 34 )
      {
        if ( v14 == 80 )
          goto LABEL_19;
LABEL_30:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_31:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_29:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 0;
}

```

## disassembly

```asm
0x1800056c8  push    rbx
0x1800056ca  push    rbp
0x1800056cb  push    rsi
0x1800056cc  push    rdi
0x1800056cd  push    r12
0x1800056cf  push    r13
0x1800056d1  push    r14
0x1800056d3  push    r15
0x1800056d5  sub     rsp, 28h
0x1800056d9  xor     r13d, r13d
0x1800056dc  mov     r14, r8
0x1800056df  mov     rbp, rdx
0x1800056e2  mov     rsi, rcx
0x1800056e5  test    rdx, rdx
0x1800056e8  jz      loc_180005867
0x1800056ee  test    r8, r8
0x1800056f1  jz      loc_180005867
0x1800056f7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800056fb  mov     rax, rbx
0x1800056fe  inc     rax
0x180005701  cmp     [rdx+rax*2], r13w
0x180005706  jnz     short loc_1800056FE
0x180005708  lea     r12, ds:2[rax*2]
0x180005710  mov     eax, 2
0x180005715  mul     r12
0x180005718  cmovb   rax, rbx
0x18000571c  mov     rcx, rax; unsigned __int64
0x18000571f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005724  mov     rdi, rax
0x180005727  mov     rcx, rbx
0x18000572a  inc     rcx
0x18000572d  cmp     [r14+rcx*2], r13w
0x180005732  jnz     short loc_18000572A
0x180005734  inc     ecx
0x180005736  mov     eax, 2
0x18000573b  movsxd  r15, ecx
0x18000573e  add     r15, r15
0x180005741  mul     r15
0x180005744  cmovb   rax, rbx
0x180005748  mov     rcx, rax; unsigned __int64
0x18000574b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005750  mov     rbx, rax
0x180005753  test    rdi, rdi
0x180005756  jz      loc_180005849
0x18000575c  test    rax, rax
0x18000575f  jz      loc_180005849
0x180005765  mov     r9, r12; SourceSize
0x180005768  mov     r8, rbp; Source
0x18000576b  mov     rdx, r12; DestinationSize
0x18000576e  mov     rcx, rdi; Destination
0x180005771  call    cs:__imp_memcpy_s
0x180005777  test    eax, eax
0x180005779  jz      short loc_18000579F
0x18000577b  cmp     eax, 0Ch
0x18000577e  jz      loc_18000587A
0x180005784  cmp     eax, 16h
0x180005787  jz      loc_180005890
0x18000578d  cmp     eax, 22h ; '"'
0x180005790  jz      loc_180005890
0x180005796  cmp     eax, 50h ; 'P'
0x180005799  jnz     loc_180005885
0x18000579f  mov     r9, r15; SourceSize
0x1800057a2  mov     r8, r14; Source
0x1800057a5  mov     rdx, r15; DestinationSize
0x1800057a8  mov     rcx, rbx; Destination
0x1800057ab  call    cs:__imp_memcpy_s
0x1800057b1  test    eax, eax
0x1800057b3  jz      short loc_1800057D9
0x1800057b5  cmp     eax, 0Ch
0x1800057b8  jz      loc_18000587A
0x1800057be  cmp     eax, 16h
0x1800057c1  jz      loc_180005890
0x1800057c7  cmp     eax, 22h ; '"'
0x1800057ca  jz      loc_180005890
0x1800057d0  cmp     eax, 50h ; 'P'
0x1800057d3  jnz     loc_180005885
0x1800057d9  mov     eax, [rsi+10h]
0x1800057dc  mov     ebp, 8
0x1800057e1  mov     rcx, [rsi]; Block
0x1800057e4  inc     eax
0x1800057e6  movsxd  rdx, eax; Count
0x1800057e9  mov     r8d, ebp; Size
0x1800057ec  call    cs:__imp__recalloc
0x1800057f2  test    rax, rax
0x1800057f5  jz      short loc_180005849
0x1800057f7  mov     rcx, [rsi+8]; Block
0x1800057fb  mov     r8d, ebp; Size
0x1800057fe  mov     [rsi], rax
0x180005801  mov     eax, [rsi+10h]
0x180005804  inc     eax
0x180005806  movsxd  rdx, eax; Count
0x180005809  call    cs:__imp__recalloc
0x18000580f  test    rax, rax
0x180005812  jz      short loc_180005849
0x180005814  movsxd  rdx, dword ptr [rsi+10h]
0x180005818  mov     [rsi+8], rax
0x18000581c  mov     rax, [rsi]
0x18000581f  lea     rcx, [rax+rdx*8]
0x180005823  test    rcx, rcx
0x180005826  jz      short loc_18000582B
0x180005828  mov     [rcx], rdi
0x18000582b  mov     rax, [rsi+8]
0x18000582f  lea     rcx, [rax+rdx*8]
0x180005833  test    rcx, rcx
0x180005836  jz      short loc_18000583B
0x180005838  mov     [rcx], rbx
0x18000583b  inc     dword ptr [rsi+10h]
0x18000583e  mov     rdi, r13
0x180005841  mov     esi, r13d
0x180005844  mov     rbx, r13
0x180005847  jmp     short loc_18000584E
0x180005849  mov     esi, 8007000Eh
0x18000584e  not     esi
0x180005850  mov     rcx, rbx; Block
0x180005853  shr     esi, 1Fh
0x180005856  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000585b  mov     rcx, rdi; Block
0x18000585e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005863  mov     eax, esi
0x180005865  jmp     short loc_180005869
0x180005867  xor     eax, eax
0x180005869  add     rsp, 28h
0x18000586d  pop     r15
0x18000586f  pop     r14
0x180005871  pop     r13
0x180005873  pop     r12
0x180005875  pop     rdi
0x180005876  pop     rsi
0x180005877  pop     rbp
0x180005878  pop     rbx
0x180005879  retn
0x18000587a  mov     ecx, 8007000Eh; int
0x18000587f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005885  mov     ecx, 80004005h; int
0x18000588a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005890  mov     ecx, 80070057h; int
0x180005895  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
