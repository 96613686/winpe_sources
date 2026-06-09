# CMetadataFilter::MergeCloseComputedPoints(void)

- ea: `0x100460560`
- end: `0x10046087c`
- name: `?MergeCloseComputedPoints@CMetadataFilter@@AEAAXXZ`
- size: `796`
- prototype: `void __fastcall(CMetadataFilter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1004602b0`

## callees

- `0x100460560`
- `0x100460b40`

## pseudocode

```c
void __fastcall CMetadataFilter::MergeCloseComputedPoints(CMetadataFilter *this)
{
  _QWORD *v1; // rdx
  CMetadataFilter *v2; // r8
  double *v3; // rax
  bool v4; // bp
  unsigned int v5; // r11d
  char v6; // bl
  __int64 v7; // r9
  unsigned int v8; // r10d
  unsigned int v9; // esi
  __int64 v10; // r14
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // r11
  __int64 v18; // rbx
  __int64 v19; // r10
  __int64 v20; // rcx
  __int64 v21; // r11
  _QWORD *v22; // rbx

  v1 = (_QWORD *)*((_QWORD *)this + 6);
  v2 = this;
  v4 = 0;
  if ( (unsigned __int8)BYTE4(*v1) != 1
    && !(unsigned __int8)BYTE6(*v1)
    && (!*((_BYTE *)this + 17)
     || (unsigned __int8)BYTE4(v1[*((_DWORD *)this + 7) - 1]) != 1
     && !(unsigned __int8)BYTE6(v1[*((_DWORD *)this + 7) - 1])) )
  {
    v3 = (double *)*((_QWORD *)this + 4);
    if ( COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*v3 - v3[2]) & _xmm) <= 0.00000001
      && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(v3[1] - v3[3]) & _xmm) <= 0.00000001 )
    {
      v4 = 1;
    }
  }
  v5 = *((_DWORD *)this + 7);
  v6 = v4;
  v7 = !v4;
  if ( v5 > 1 )
  {
    v8 = 2;
    do
    {
      v9 = v8;
      v10 = 8LL * (v8 - 1);
      v11 = v8 - 1;
      if ( (unsigned __int8)BYTE4(*(_QWORD *)(v10 + *((_QWORD *)v2 + 6))) == 1
        || (unsigned __int8)BYTE6(*(_QWORD *)(v10 + *((_QWORD *)v2 + 6)))
        || v8 == v5 && *((_BYTE *)v2 + 17) && CMetadataFilter::IsUntouchable(v2, 0)
        || (!(_DWORD)v7
         || (v12 = *((_QWORD *)v2 + 4),
             COERCE_DOUBLE(
               COERCE_UNSIGNED_INT64(*(double *)(v12 + 16LL * (unsigned int)(v7 - 1)) - *(double *)(v12 + 16 * v11))
             & _xmm) > 0.00000001)
         || COERCE_DOUBLE(
              COERCE_UNSIGNED_INT64(*(double *)(v12 + 16LL * (unsigned int)(v7 - 1) + 8) - *(double *)(v12 + 16 * v11 + 8))
            & _xmm) > 0.00000001)
        && (v8 >= v5
         || (v13 = *((_QWORD *)v2 + 4),
             COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(double *)(v13 + 16 * v11) - *(double *)(v13 + 16LL * v8)) & _xmm) > 0.00000001)
         || COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(double *)(v13 + 16 * v11 + 8) - *(double *)(v13 + 16LL * v8 + 8)) & _xmm) > 0.00000001) )
      {
        v6 = 0;
        *(_OWORD *)(*((_QWORD *)v2 + 4) + 16LL * (unsigned int)v7) = *(_OWORD *)(*((_QWORD *)v2 + 4) + 16 * v11);
        *(_QWORD *)(*((_QWORD *)v2 + 6) + 8 * v7) = *(_QWORD *)(*((_QWORD *)v2 + 6) + v10);
        v7 = (unsigned int)(v7 + 1);
      }
      else
      {
        v6 = 1;
      }
      v5 = *((_DWORD *)v2 + 7);
      ++v8;
    }
    while ( v9 < v5 );
  }
  v14 = v7;
  if ( *((_BYTE *)v2 + 17) )
  {
    if ( v4 )
    {
      v7 = (unsigned int)(v7 - 1);
      if ( v6 )
        v7 = v14;
LABEL_36:
      *(_OWORD *)(*((_QWORD *)v2 + 4) + 16LL * (unsigned int)v7) = *(_OWORD *)*((_QWORD *)v2 + 4);
      *(_QWORD *)(*((_QWORD *)v2 + 6) + 8 * v7) = **((_QWORD **)v2 + 6);
      LODWORD(v7) = v7 + 1;
      goto LABEL_46;
    }
    if ( v6 )
    {
      if ( (unsigned int)v7 > 1 )
      {
        v15 = 0;
        v16 = (unsigned int)(v7 - 1);
        v17 = 16;
        v18 = 0;
        v19 = 8;
        do
        {
          v15 += 8;
          v18 += 16;
          v17 += 16;
          v19 += 8;
          *(_OWORD *)(*((_QWORD *)v2 + 4) + v18 - 16) = *(_OWORD *)(*((_QWORD *)v2 + 4) + v17 - 16);
          *(_QWORD *)(*((_QWORD *)v2 + 6) + v15 - 8) = *(_QWORD *)(*((_QWORD *)v2 + 6) + v19 - 8);
          --v16;
        }
        while ( v16 );
      }
      v7 = (unsigned int)(v7 - 1);
      goto LABEL_36;
    }
  }
  else
  {
    v20 = *((_QWORD *)v2 + 4);
    v21 = (unsigned int)(v7 - 1);
    if ( COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(double *)v20 - *(double *)(v20 + 16 * v21)) & _xmm) <= 0.00000001
      && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(double *)(v20 + 8) - *(double *)(v20 + 16LL * (unsigned int)(v7 - 1) + 8)) & _xmm) <= 0.00000001 )
    {
      v22 = (_QWORD *)*((_QWORD *)v2 + 6);
      if ( (unsigned __int8)BYTE4(v22[*((_DWORD *)v2 + 11) - 1]) == 1
        || (unsigned __int8)BYTE6(v22[*((_DWORD *)v2 + 11) - 1]) )
      {
        if ( (unsigned __int8)BYTE4(*v22) == 1 || (unsigned __int8)BYTE6(*v22) )
          goto LABEL_46;
        *(_OWORD *)v20 = *(_OWORD *)(v20 + 16LL * (unsigned int)(v7 - 1));
        **((_QWORD **)v2 + 6) = *(_QWORD *)(*((_QWORD *)v2 + 6) + 8 * v21);
      }
      else
      {
        *(_OWORD *)(v20 + 16LL * (unsigned int)(v7 - 1)) = *(_OWORD *)v20;
        *(_QWORD *)(*((_QWORD *)v2 + 6) + 8 * v21) = **((_QWORD **)v2 + 6);
      }
      *((_BYTE *)v2 + 17) = 1;
    }
  }
LABEL_46:
  *((_DWORD *)v2 + 7) = v7;
  *((_DWORD *)v2 + 11) = v7;
}

```

## disassembly

```asm
0x100460560  mov     [rsp+arg_18], rbx
0x100460565  push    rbp
0x100460566  sub     rsp, 20h
0x10046056a  mov     rdx, [rcx+30h]
0x10046056e  mov     r8, rcx
0x100460571  movsd   xmm1, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x100460579  movsd   xmm2, cs:__real@3e45798ee2308c3a
0x100460581  mov     rcx, [rdx]
0x100460584  mov     rax, rcx
0x100460587  shr     rax, 20h
0x10046058b  cmp     al, 1
0x10046058d  jz      short loc_1004605E8
0x10046058f  shr     rcx, 30h
0x100460593  test    cl, cl
0x100460595  jnz     short loc_1004605E8
0x100460597  cmp     [r8+11h], cl
0x10046059b  jz      short loc_1004605BA
0x10046059d  mov     eax, [r8+1Ch]
0x1004605a1  dec     eax
0x1004605a3  mov     rcx, [rdx+rax*8]
0x1004605a7  mov     rax, rcx
0x1004605aa  shr     rax, 20h
0x1004605ae  cmp     al, 1
0x1004605b0  jz      short loc_1004605E8
0x1004605b2  shr     rcx, 30h
0x1004605b6  test    cl, cl
0x1004605b8  jnz     short loc_1004605E8
0x1004605ba  mov     rax, [r8+20h]
0x1004605be  movsd   xmm0, qword ptr [rax]
0x1004605c2  subsd   xmm0, qword ptr [rax+10h]
0x1004605c7  andps   xmm0, xmm1
0x1004605ca  comisd  xmm2, xmm0
0x1004605ce  jb      short loc_1004605E8
0x1004605d0  movsd   xmm0, qword ptr [rax+8]
0x1004605d5  subsd   xmm0, qword ptr [rax+18h]
0x1004605da  andps   xmm0, xmm1
0x1004605dd  comisd  xmm2, xmm0
0x1004605e1  jb      short loc_1004605E8
0x1004605e3  mov     bpl, 1
0x1004605e6  jmp     short loc_1004605EB
0x1004605e8  xor     bpl, bpl
0x1004605eb  mov     r11d, [r8+1Ch]
0x1004605ef  movzx   ebx, bpl
0x1004605f3  movzx   r9d, bpl
0x1004605f7  xor     r9d, 1
0x1004605fb  mov     [rsp+28h+arg_8], rdi
0x100460600  cmp     r11d, 1
0x100460604  jbe     loc_10046072C
0x10046060a  mov     [rsp+28h+arg_0], rsi
0x10046060f  mov     r10d, 2
0x100460615  mov     [rsp+28h+arg_10], r14
0x10046061a  nop     word ptr [rax+rax+00h]
0x100460620  lea     eax, [r10-1]
0x100460624  mov     esi, r10d
0x100460627  lea     r14, ds:0[rax*8]
0x10046062f  mov     edi, eax
0x100460631  mov     rax, [r8+30h]
0x100460635  mov     rcx, [r14+rax]
0x100460639  mov     rax, rcx
0x10046063c  shr     rax, 20h
0x100460640  cmp     al, 1
0x100460642  jz      loc_1004606EC
0x100460648  shr     rcx, 30h
0x10046064c  test    cl, cl
0x10046064e  jnz     loc_1004606EC
0x100460654  cmp     r10d, r11d
0x100460657  jnz     short loc_10046066D
0x100460659  cmp     [r8+11h], cl
0x10046065d  jz      short loc_10046066D
0x10046065f  xor     edx, edx; unsigned int
0x100460661  mov     rcx, r8; this
0x100460664  call    ?IsUntouchable@CMetadataFilter@@AEBA_NI@Z; CMetadataFilter::IsUntouchable(uint)
0x100460669  test    al, al
0x10046066b  jnz     short loc_1004606EC
0x10046066d  test    r9d, r9d
0x100460670  jz      short loc_1004606AB
0x100460672  mov     rcx, [r8+20h]
0x100460676  lea     edx, [r9-1]
0x10046067a  add     rdx, rdx
0x10046067d  mov     rax, rdi
0x100460680  add     rax, rax
0x100460683  movsd   xmm0, qword ptr [rcx+rdx*8]
0x100460688  subsd   xmm0, qword ptr [rcx+rax*8]
0x10046068d  andps   xmm0, xmm1
0x100460690  comisd  xmm2, xmm0
0x100460694  jb      short loc_1004606AB
0x100460696  movsd   xmm0, qword ptr [rcx+rdx*8+8]
0x10046069c  subsd   xmm0, qword ptr [rcx+rax*8+8]
0x1004606a2  andps   xmm0, xmm1
0x1004606a5  comisd  xmm2, xmm0
0x1004606a9  jnb     short loc_1004606E8
0x1004606ab  cmp     r10d, r11d
0x1004606ae  jnb     short loc_1004606EC
0x1004606b0  mov     rax, [r8+20h]
0x1004606b4  mov     rcx, rdi
0x1004606b7  add     rcx, rcx
0x1004606ba  mov     edx, r10d
0x1004606bd  add     rdx, rdx
0x1004606c0  movsd   xmm0, qword ptr [rax+rcx*8]
0x1004606c5  subsd   xmm0, qword ptr [rax+rdx*8]
0x1004606ca  andps   xmm0, xmm1
0x1004606cd  comisd  xmm2, xmm0
0x1004606d1  jb      short loc_1004606EC
0x1004606d3  movsd   xmm0, qword ptr [rax+rcx*8+8]
0x1004606d9  subsd   xmm0, qword ptr [rax+rdx*8+8]
0x1004606df  andps   xmm0, xmm1
0x1004606e2  comisd  xmm2, xmm0
0x1004606e6  jb      short loc_1004606EC
0x1004606e8  mov     bl, 1
0x1004606ea  jmp     short loc_100460712
0x1004606ec  mov     rcx, [r8+20h]
0x1004606f0  add     rdi, rdi
0x1004606f3  mov     eax, r9d
0x1004606f6  xor     bl, bl
0x1004606f8  add     rax, rax
0x1004606fb  movups  xmm0, xmmword ptr [rcx+rdi*8]
0x1004606ff  movups  xmmword ptr [rcx+rax*8], xmm0
0x100460703  mov     rcx, [r8+30h]
0x100460707  mov     rax, [rcx+r14]
0x10046070b  mov     [rcx+r9*8], rax
0x10046070f  inc     r9d
0x100460712  mov     r11d, [r8+1Ch]
0x100460716  inc     r10d
0x100460719  cmp     esi, r11d
0x10046071c  jb      loc_100460620
0x100460722  mov     r14, [rsp+28h+arg_10]
0x100460727  mov     rsi, [rsp+28h+arg_0]
0x10046072c  cmp     byte ptr [r8+11h], 0
0x100460731  mov     eax, r9d
0x100460734  jz      loc_1004607CA
0x10046073a  test    bpl, bpl
0x10046073d  jz      short loc_10046074A
0x10046073f  dec     r9d
0x100460742  test    bl, bl
0x100460744  cmovnz  r9d, eax
0x100460748  jmp     short loc_1004607A6
0x10046074a  test    bl, bl
0x10046074c  jz      loc_100460864
0x100460752  cmp     r9d, 1
0x100460756  jbe     short loc_1004607A3
0x100460758  xor     edx, edx
0x10046075a  lea     edi, [r9-1]
0x10046075e  mov     r11d, 10h
0x100460764  mov     ebx, edx
0x100460766  lea     r10d, [rdx+8]
0x10046076a  nop     word ptr [rax+rax+00h]
0x100460770  mov     rax, [r8+20h]
0x100460774  lea     rdx, [rdx+8]
0x100460778  lea     rbx, [rbx+10h]
0x10046077c  lea     r11, [r11+10h]
0x100460780  lea     r10, [r10+8]
0x100460784  movups  xmm0, xmmword ptr [rax+r11-10h]
0x10046078a  movups  xmmword ptr [rax+rbx-10h], xmm0
0x10046078f  mov     rcx, [r8+30h]
0x100460793  mov     rax, [rcx+r10-8]
0x100460798  mov     [rcx+rdx-8], rax
0x10046079d  sub     rdi, 1
0x1004607a1  jnz     short loc_100460770
0x1004607a3  dec     r9d
0x1004607a6  mov     rcx, [r8+20h]
0x1004607aa  mov     eax, r9d
0x1004607ad  add     rax, rax
0x1004607b0  movups  xmm0, xmmword ptr [rcx]
0x1004607b3  movups  xmmword ptr [rcx+rax*8], xmm0
0x1004607b7  mov     rcx, [r8+30h]
0x1004607bb  mov     rax, [rcx]
0x1004607be  mov     [rcx+r9*8], rax
0x1004607c2  inc     r9d
0x1004607c5  jmp     loc_100460864
0x1004607ca  mov     rcx, [r8+20h]
0x1004607ce  lea     eax, [r9-1]
0x1004607d2  mov     edx, eax
0x1004607d4  add     rdx, rdx
0x1004607d7  mov     r11d, eax
0x1004607da  movsd   xmm0, qword ptr [rcx]
0x1004607de  subsd   xmm0, qword ptr [rcx+rdx*8]
0x1004607e3  andps   xmm0, xmm1
0x1004607e6  comisd  xmm2, xmm0
0x1004607ea  jb      short loc_100460864
0x1004607ec  movsd   xmm0, qword ptr [rcx+8]
0x1004607f1  subsd   xmm0, qword ptr [rcx+rdx*8+8]
0x1004607f7  andps   xmm0, xmm1
0x1004607fa  comisd  xmm2, xmm0
0x1004607fe  jb      short loc_100460864
0x100460800  mov     eax, [r8+2Ch]
0x100460804  mov     rbx, [r8+30h]
0x100460808  dec     eax
0x10046080a  mov     r10, [rbx+rax*8]
0x10046080e  mov     rax, r10
0x100460811  shr     rax, 20h
0x100460815  cmp     al, 1
0x100460817  jz      short loc_100460836
0x100460819  shr     r10, 30h
0x10046081d  test    r10b, r10b
0x100460820  jnz     short loc_100460836
0x100460822  movups  xmm0, xmmword ptr [rcx]
0x100460825  movups  xmmword ptr [rcx+rdx*8], xmm0
0x100460829  mov     rcx, [r8+30h]
0x10046082d  mov     rax, [rcx]
0x100460830  mov     [rcx+r11*8], rax
0x100460834  jmp     short loc_10046085F
0x100460836  mov     r10, [rbx]
0x100460839  mov     rax, r10
0x10046083c  shr     rax, 20h
0x100460840  cmp     al, 1
0x100460842  jz      short loc_100460864
0x100460844  shr     r10, 30h
0x100460848  test    r10b, r10b
0x10046084b  jnz     short loc_100460864
0x10046084d  movups  xmm0, xmmword ptr [rcx+rdx*8]
0x100460851  movups  xmmword ptr [rcx], xmm0
0x100460854  mov     rcx, [r8+30h]
0x100460858  mov     rax, [rcx+r11*8]
0x10046085c  mov     [rcx], rax
0x10046085f  mov     byte ptr [r8+11h], 1
0x100460864  mov     rdi, [rsp+28h+arg_8]
0x100460869  mov     rbx, [rsp+28h+arg_18]
0x10046086e  mov     [r8+1Ch], r9d
0x100460872  mov     [r8+2Ch], r9d
0x100460876  add     rsp, 20h
0x10046087a  pop     rbp
0x10046087b  retn
```
