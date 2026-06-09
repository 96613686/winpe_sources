# LibRaw::write_ppm_tiff(void)

- ea: `0x1800276f0`
- end: `0x180027e0d`
- name: `?write_ppm_tiff@LibRaw@@IEAAXXZ`
- size: `1821`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x180002a00`
- `0x180002e18`
- `0x180006363`
- `0x180009460`
- `0x180009d40`
- `0x180026a10`
- `0x1800276f0`
- `0x180028f50`
- `0x180095005`
- `0x1800a4510`
- `0x1800af370`
- `0x1800b0b00`

## import_xrefs

- `WS2_32!__imp_htons` at `0x180027d1f`
- `WS2_32!__imp_htons` at `0x180027d1f`
- `WS2_32!__imp_ntohl` at `0x18002792a`
- `WS2_32!__imp_ntohl` at `0x18002792a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LibRaw::write_ppm_tiff(LibRaw *this)
{
  int v2; // r9d
  int v3; // ecx
  int v4; // r10d
  int v5; // eax
  __int64 v6; // r11
  __int64 v7; // rbx
  int v8; // ecx
  __int64 v9; // rdx
  int v10; // r8d
  _DWORD *v11; // rax
  __int64 v12; // rcx
  unsigned __int16 v13; // ax
  __int64 v14; // rdx
  int v15; // eax
  size_t v16; // rbx
  _BYTE *v17; // r13
  u_long *v18; // rcx
  FILE *v19; // rbx
  u_long v20; // eax
  int v21; // r10d
  int v22; // eax
  int v23; // esi
  int v24; // r11d
  int v25; // ebx
  int v26; // r10d
  int v27; // edx
  int v28; // eax
  unsigned int v29; // ecx
  int v30; // r12d
  int v31; // r14d
  int v32; // r8d
  int v33; // edx
  __int16 v34; // si
  int v35; // eax
  int v36; // esi
  int v37; // r9d
  int v38; // edx
  int v39; // r10d
  int v40; // esi
  int v41; // r14d
  _WORD *v42; // rbx
  int v43; // r10d
  __int64 v44; // r11
  int v45; // edx
  int v46; // r9d
  __int64 v47; // r8
  _BYTE *v48; // rax
  int v49; // [rsp+70h] [rbp-5D8h]
  int v50; // [rsp+74h] [rbp-5D4h]
  int v51; // [rsp+78h] [rbp-5D0h]
  int v52; // [rsp+7Ch] [rbp-5CCh] BYREF
  void *v53; // [rsp+80h] [rbp-5C8h]
  __int128 v54; // [rsp+88h] [rbp-5C0h]
  char *v55; // [rsp+98h] [rbp-5B0h]
  __int64 v56; // [rsp+A0h] [rbp-5A8h]
  _BYTE Buffer[1376]; // [rsp+B0h] [rbp-598h] BYREF

  v56 = -2;
  v2 = 0x2000;
  v3 = (int)(float)((float)(*((unsigned __int16 *)this + 10) * *((unsigned __int16 *)this + 11))
                  * *((float *)this + 1320));
  v4 = v3 / 2;
  if ( !*((_WORD *)this + 190675) )
    v4 = v3;
  if ( (*((_DWORD *)this + 1294) & 0xFFFFFFFD) == 0 && !*((_DWORD *)this + 1322) )
  {
    v2 = 0;
    v5 = *((_DWORD *)this + 135);
    if ( v5 > 0 )
    {
      v6 = *((_QWORD *)this + 47669) + 32764LL;
      v7 = (unsigned int)v5;
      do
      {
        v8 = 0;
        v9 = 0x1FFF;
        v10 = 0x1FFF;
        v11 = (_DWORD *)v6;
        do
        {
          v8 += *v11;
          if ( v8 > v4 )
            break;
          --v10;
          --v9;
          --v11;
        }
        while ( v9 > 32 );
        if ( v2 < v10 )
          v2 = v10;
        v6 += 0x8000;
        --v7;
      }
      while ( v7 );
    }
  }
  try
  {
    LibRaw::gamma_curve(
      this,
      *((double *)this + 637),
      *((double *)this + 638),
      2,
      (int)(float)((float)(8 * v2) / *((float *)this + 1290)));
    v12 = *((unsigned __int16 *)this + 10);
    *((_WORD *)this + 14) = v12;
    v13 = *((_WORD *)this + 11);
    *((_WORD *)this + 15) = v13;
    if ( (*((_BYTE *)this + 48) & 4) != 0 )
    {
      *((_WORD *)this + 11) = v12;
      *((_WORD *)this + 10) = v13;
      v13 = v12;
    }
    v14 = ((*((_DWORD *)this + 135) * *((_DWORD *)this + 1308) * v13) >> 31) & 7;
    v15 = *((_DWORD *)this + 135) * *((_DWORD *)this + 1308) * v13 / 8;
    v16 = v15;
    v54 = 0;
    v55 = 0;
    v53 = 0;
    if ( v15 )
    {
      if ( (unsigned __int64)v15 > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<unsigned int>::_Xlength(v12, v14);
      v53 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(v15);
      v17 = v53;
      *(_QWORD *)&v54 = v53;
      v55 = (char *)v53 + v16;
      memset(v53, 0, v16);
      *((_QWORD *)&v54 + 1) = (char *)v53 + v16;
    }
    else
    {
      v17 = (_BYTE *)v54;
    }
    if ( *((_DWORD *)this + 1309) )
    {
      LibRaw::tiff_head(this, (struct tiff_hdr *)Buffer, 1);
      fwrite_0(Buffer, 0x560u, 1u, *((FILE **)this + 47660));
      v18 = (u_long *)*((_QWORD *)this + 47670);
      if ( v18 )
      {
        v19 = (FILE *)*((_QWORD *)this + 47660);
        v20 = ntohl(*v18);
        fwrite_0(*((const void **)this + 47670), v20, 1u, v19);
      }
    }
    else
    {
      v21 = *((_DWORD *)this + 135);
      v22 = *((_DWORD *)this + 1310) & 1;
      v23 = (1 << *((_DWORD *)this + 1308)) - 1;
      v24 = *((unsigned __int16 *)this + 10);
      v25 = *((unsigned __int16 *)this + 11);
      if ( v21 <= 3 )
      {
        if ( v22 )
          fprintf(
            *((FILE *const *)this + 47660),
            "P%d\n"
            "# EXPTIME=%0.5f\n"
            "# TIMESTAMP=%d\n"
            "# ISOSPEED=%d\n"
            "# APERTURE=%0.1f\n"
            "# FOCALLEN=%0.1f\n"
            "# MAKE=%s\n"
            "# MODEL=%s\n"
            "%d %d\n"
            "%d\n",
            v21 / 2 + 5,
            *((float *)this + 48107),
            *((_DWORD *)this + 48110),
            (int)*((float *)this + 48106),
            *((float *)this + 48108),
            *((float *)this + 48109),
            (const char *)this + 204,
            (const char *)this + 268,
            v25,
            v24,
            v23);
        else
          fprintf(*((FILE *const *)this + 47660), "P%d\n%d %d\n%d\n", v21 / 2 + 5, v25, v24, v23);
      }
      else if ( v22 )
      {
        fprintf(
          *((FILE *const *)this + 47660),
          "P7\n"
          "# EXPTIME=%0.5f\n"
          "# TIMESTAMP=%d\n"
          "# ISOSPEED=%d\n"
          "# APERTURE=%0.1f\n"
          "# FOCALLEN=%0.1f\n"
          "# MAKE=%s\n"
          "# MODEL=%s\n"
          "WIDTH %d\n"
          "HEIGHT %d\n"
          "DEPTH %d\n"
          "MAXVAL %d\n"
          "TUPLTYPE %s\n"
          "ENDHDR\n",
          *((float *)this + 48107),
          *((_DWORD *)this + 48110),
          (int)*((float *)this + 48106),
          *((float *)this + 48108),
          *((float *)this + 48109),
          (const char *)this + 204,
          (const char *)this + 268,
          v25,
          v24,
          v21,
          v23,
          (const char *)this + 620);
      }
      else
      {
        fprintf(
          *((FILE *const *)this + 47660),
          "P7\nWIDTH %d\nHEIGHT %d\nDEPTH %d\nMAXVAL %d\nTUPLTYPE %s\nENDHDR\n",
          v25,
          v24,
          v21,
          v23,
          (const char *)this + 620);
      }
    }
    v26 = *((_DWORD *)this + 12);
    v27 = 0;
    if ( (v26 & 2) != 0 )
      v27 = *((unsigned __int16 *)this + 14) - 1;
    v28 = 0;
    if ( (v26 & 1) != 0 )
      v28 = *((unsigned __int16 *)this + 15) - 1;
    v29 = *((unsigned __int16 *)this + 15);
    v30 = v28 + v27 * v29;
    v31 = v26 & 4;
    v32 = v31 != 0;
    if ( (*((_DWORD *)this + 12) & 2) != 0 )
      v33 = *((unsigned __int16 *)this + 14) - v32 - 1;
    else
      v33 = (v26 & 4) != 0;
    v34 = v29;
    v35 = v31 == 0;
    if ( (v26 & 1) != 0 )
    {
      v35 = ((__PAIR64__(v29, v31) - 1) >> 32) - 1;
      v34 = *((_WORD *)this + 15);
    }
    v50 = v35 + v33 * v29 - v30;
    if ( (v26 & 4) != 0 )
      LOWORD(v29) = v34;
    if ( (v26 & 2) != 0 )
      v36 = ((__PAIR64__(*((unsigned __int16 *)this + 14), v31) - 1) >> 32) - 1;
    else
      v36 = v31 == 0;
    if ( (v26 & 1) != 0 )
      v32 = (unsigned __int16)v29 - v32 - 1;
    v37 = *((unsigned __int16 *)this + 11);
    if ( (*((_DWORD *)this + 12) & 4) == 0 )
      v37 = 0;
    v38 = 0;
    if ( (v26 & 4) == 0 )
      v38 = *((unsigned __int16 *)this + 11);
    v39 = *((_DWORD *)this + 12);
    if ( (v39 & 2) != 0 )
      v37 = *((unsigned __int16 *)this + 14) - v37 - 1;
    if ( (v39 & 1) != 0 )
      v38 = (unsigned __int16)v29 - v38 - 1;
    v40 = v32 + (unsigned __int16)v29 * (v36 - v37) - v38;
    v51 = v40;
    v41 = 0;
    v49 = 0;
    v42 = v53;
    while ( v41 < *((unsigned __int16 *)this + 10) )
    {
      v43 = 0;
      if ( *((_WORD *)this + 11) )
      {
        v44 = 4LL * v30;
        do
        {
          v45 = *((_DWORD *)this + 135);
          v46 = 0;
          v47 = 0;
          if ( *((_DWORD *)this + 1308) == 8 )
          {
            if ( v45 > 0 )
            {
              do
              {
                if ( v47 >= 4 )
                  break;
                v17[v46 + v43 * v45] = *((_BYTE *)this
                                       + 2 * *(unsigned __int16 *)(*((_QWORD *)this + 1) + 2 * (v47 + v44))
                                       + 5393);
                ++v46;
                ++v47;
                v45 = *((_DWORD *)this + 135);
              }
              while ( v46 < v45 );
            }
          }
          else if ( v45 > 0 )
          {
            do
            {
              if ( v47 >= 4 )
                break;
              v42[v46 + v43 * v45] = *((_WORD *)this
                                     + *(unsigned __int16 *)(*((_QWORD *)this + 1) + 2 * (v47 + v44))
                                     + 2696);
              ++v46;
              ++v47;
              v45 = *((_DWORD *)this + 135);
            }
            while ( v46 < v45 );
          }
          ++v43;
          v30 += v50;
          v44 += 4LL * v50;
        }
        while ( v43 < *((unsigned __int16 *)this + 11) );
        v40 = v51;
        v41 = v49;
      }
      if ( *((_DWORD *)this + 1308) == 16 && !*((_DWORD *)this + 1309) && htons(0x55AAu) != 21930 )
        LibRaw::libraw_swab(this, v42, 2 * *((_DWORD *)this + 135) * *((unsigned __int16 *)this + 11));
      fwrite_0(
        v17,
        *((_DWORD *)this + 135) * *((_DWORD *)this + 1308) / 8,
        *((unsigned __int16 *)this + 11),
        *((FILE **)this + 47660));
      v49 = ++v41;
      v30 += v40;
    }
    if ( v17 )
    {
      v48 = v17;
      if ( (unsigned __int64)(v55 - v17) >= 0x1000 )
      {
        v17 = (_BYTE *)*((_QWORD *)v17 - 1);
        if ( (unsigned __int64)(v48 - v17 - 8) > 0x1F )
          invoke_watson_0(0, 0, 0, 0, 0);
      }
      operator delete(v17);
    }
  }
  catch ( ... )
  {
    v52 = 1;
    throw (LibRaw_exceptions *)&v52;
  }
}

```

## disassembly

```asm
0x1800276f0  mov     rax, rsp
0x1800276f3  push    rdi
0x1800276f4  push    r12
0x1800276f6  push    r13
0x1800276f8  push    r14
0x1800276fa  push    r15
0x1800276fc  sub     rsp, 620h
0x180027703  mov     qword ptr [rax-5A8h], 0FFFFFFFFFFFFFFFEh
0x18002770e  mov     [rax+10h], rbx
0x180027712  mov     [rax+18h], rsi
0x180027716  mov     rax, cs:__security_cookie
0x18002771d  xor     rax, rsp
0x180027720  mov     [rsp+648h+var_38], rax
0x180027728  mov     rdi, rcx
0x18002772b  mov     r9d, 2000h
0x180027731  movzx   ecx, word ptr [rcx+16h]
0x180027735  movzx   eax, word ptr [rdi+14h]
0x180027739  imul    ecx, eax
0x18002773c  movd    xmm0, ecx
0x180027740  cvtdq2ps xmm0, xmm0
0x180027743  mulss   xmm0, dword ptr [rdi+14A0h]
0x18002774b  cvttss2si ecx, xmm0
0x18002774f  mov     eax, ecx
0x180027751  cdq
0x180027752  sub     eax, edx
0x180027754  sar     eax, 1
0x180027756  mov     r10d, eax
0x180027759  cmp     word ptr [rdi+5D1A6h], 0
0x180027761  cmovz   r10d, ecx
0x180027765  test    dword ptr [rdi+1438h], 0FFFFFFFDh
0x18002776f  jnz     short loc_1800277DD
0x180027771  cmp     dword ptr [rdi+14A8h], 0
0x180027778  jnz     short loc_1800277DD
0x18002777a  xor     r15d, r15d
0x18002777d  mov     r9d, r15d
0x180027780  mov     eax, [rdi+21Ch]
0x180027786  test    eax, eax
0x180027788  jle     short loc_1800277E0
0x18002778a  mov     r11, [rdi+5D1A8h]
0x180027791  add     r11, 7FFCh
0x180027798  mov     ebx, eax
0x18002779a  nop     word ptr [rax+rax+00h]
0x1800277a0  mov     ecx, r15d
0x1800277a3  mov     edx, 1FFFh
0x1800277a8  mov     r8d, edx
0x1800277ab  mov     rax, r11
0x1800277ae  xchg    ax, ax
0x1800277b0  add     ecx, [rax]
0x1800277b2  cmp     ecx, r10d
0x1800277b5  jg      short loc_1800277C7
0x1800277b7  dec     r8d
0x1800277ba  dec     rdx
0x1800277bd  sub     rax, 4
0x1800277c1  cmp     rdx, 20h ; ' '
0x1800277c5  jg      short loc_1800277B0
0x1800277c7  cmp     r9d, r8d
0x1800277ca  cmovl   r9d, r8d
0x1800277ce  add     r11, 8000h
0x1800277d5  sub     rbx, 1
0x1800277d9  jnz     short loc_1800277A0
0x1800277db  jmp     short loc_1800277E0
0x1800277dd  xor     r15d, r15d
0x1800277e0  lea     eax, ds:0[r9*8]
0x1800277e8  movd    xmm0, eax
0x1800277ec  cvtdq2ps xmm0, xmm0
0x1800277ef  divss   xmm0, dword ptr [rdi+1428h]
0x1800277f7  cvttss2si eax, xmm0
0x1800277fb  mov     dword ptr [rsp+648h+Reserved], eax; int
0x1800277ff  mov     r9d, 2; int
0x180027805  movsd   xmm2, qword ptr [rdi+13F0h]; double
0x18002780d  movsd   xmm1, qword ptr [rdi+13E8h]; double
0x180027815  mov     rcx, rdi; this
0x180027818  call    ?gamma_curve@LibRaw@@IEAAXNNHH@Z; LibRaw::gamma_curve(double,double,int,int)
0x18002781d  movzx   ecx, word ptr [rdi+14h]
0x180027821  mov     [rdi+1Ch], cx
0x180027825  movzx   eax, word ptr [rdi+16h]
0x180027829  mov     [rdi+1Eh], ax
0x18002782d  test    byte ptr [rdi+30h], 4
0x180027831  jz      short loc_18002783E
0x180027833  mov     [rdi+16h], cx
0x180027837  mov     [rdi+14h], ax
0x18002783b  movzx   eax, cx
0x18002783e  movzx   eax, ax
0x180027841  imul    eax, [rdi+1470h]
0x180027848  imul    eax, [rdi+21Ch]
0x18002784f  cdq
0x180027850  and     edx, 7
0x180027853  add     eax, edx
0x180027855  sar     eax, 3
0x180027858  movsxd  rbx, eax
0x18002785b  xorps   xmm0, xmm0
0x18002785e  movdqu  [rsp+648h+var_5C0], xmm0
0x180027867  mov     [rsp+648h+var_5B0], r15
0x18002786f  mov     [rsp+648h+var_5C8], r15
0x180027877  test    eax, eax
0x180027879  jz      short loc_1800278CC
0x18002787b  mov     rax, 7FFFFFFFFFFFFFFFh
0x180027885  cmp     rbx, rax
0x180027888  ja      loc_180027DF1
0x18002788e  mov     rcx, rbx
0x180027891  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180027896  mov     [rsp+648h+var_5C8], rax
0x18002789e  mov     r13, rax
0x1800278a1  mov     qword ptr [rsp+648h+var_5C0], rax
0x1800278a9  lea     r14, [rax+rbx]
0x1800278ad  mov     [rsp+648h+var_5B0], r14
0x1800278b5  mov     r8, rbx; Size
0x1800278b8  xor     edx, edx; Val
0x1800278ba  mov     rcx, rax; void *
0x1800278bd  call    memset
0x1800278c2  mov     qword ptr [rsp+648h+var_5C0+8], r14
0x1800278ca  jmp     short loc_1800278D4
0x1800278cc  mov     r13, qword ptr [rsp+648h+var_5C0]
0x1800278d4  mov     esi, 1
0x1800278d9  cmp     dword ptr [rdi+1474h], 0
0x1800278e0  jz      short loc_180027949
0x1800278e2  mov     r8d, esi; int
0x1800278e5  lea     rdx, [rsp+648h+Buffer]; struct tiff_hdr *
0x1800278ed  mov     rcx, rdi; this
0x1800278f0  call    ?tiff_head@LibRaw@@IEAAXPEAUtiff_hdr@@H@Z; LibRaw::tiff_head(tiff_hdr *,int)
0x1800278f5  mov     r9, [rdi+5D160h]; Stream
0x1800278fc  mov     r8d, esi; ElementCount
0x1800278ff  mov     edx, 560h; ElementSize
0x180027904  lea     rcx, [rsp+648h+Buffer]; Buffer
0x18002790c  call    fwrite_0
0x180027911  mov     rcx, [rdi+5D1B0h]
0x180027918  test    rcx, rcx
0x18002791b  jz      loc_180027AFC
0x180027921  mov     rbx, [rdi+5D160h]
0x180027928  mov     ecx, [rcx]; netlong
0x18002792a  call    cs:__imp_ntohl
0x180027930  mov     edx, eax; ElementSize
0x180027932  mov     r9, rbx; Stream
0x180027935  mov     r8d, esi; ElementCount
0x180027938  mov     rcx, [rdi+5D1B0h]; Buffer
0x18002793f  call    fwrite_0
0x180027944  jmp     loc_180027AFC
0x180027949  mov     r10d, [rdi+21Ch]
0x180027950  mov     eax, [rdi+1478h]
0x180027956  and     eax, 1
0x180027959  mov     ecx, [rdi+1470h]
0x18002795f  shl     esi, cl
0x180027961  dec     esi
0x180027963  movzx   r11d, word ptr [rdi+14h]
0x180027968  movzx   ebx, word ptr [rdi+16h]
0x18002796c  cmp     r10d, 3
0x180027970  jle     loc_180027A3D
0x180027976  lea     r8, [rdi+26Ch]
0x18002797d  test    eax, eax
0x18002797f  jz      loc_180027A11
0x180027985  lea     rax, [rdi+10Ch]
0x18002798c  lea     rcx, [rdi+0CCh]
0x180027993  movss   xmm0, dword ptr [rdi+2EFB4h]
0x18002799b  cvtps2pd xmm0, xmm0
0x18002799e  movss   xmm1, dword ptr [rdi+2EFB0h]
0x1800279a6  cvtps2pd xmm1, xmm1
0x1800279a9  cvttss2si edx, dword ptr [rdi+2EFA8h]
0x1800279b1  movss   xmm2, dword ptr [rdi+2EFACh]
0x1800279b9  cvtps2pd xmm2, xmm2
0x1800279bc  mov     [rsp+648h+var_5E0], r8
0x1800279c1  mov     [rsp+648h+var_5E8], esi
0x1800279c5  mov     [rsp+648h+var_5F0], r10d
0x1800279ca  mov     [rsp+648h+var_5F8], r11d
0x1800279cf  mov     dword ptr [rsp+648h+var_600], ebx
0x1800279d3  mov     [rsp+648h+var_608], rax
0x1800279d8  mov     [rsp+648h+var_610], rcx
0x1800279dd  movsd   [rsp+648h+var_618], xmm0
0x1800279e3  movsd   [rsp+648h+var_620], xmm1
0x1800279e9  mov     dword ptr [rsp+648h+Reserved], edx
0x1800279ed  mov     r9d, [rdi+2EFB8h]
0x1800279f4  movq    r8, xmm2
0x1800279f9  lea     rdx, aP7Exptime05fTi; "P7\n# EXPTIME=%0.5f\n# TIMESTAMP=%d\n# "...
0x180027a00  mov     rcx, [rdi+5D160h]; Stream
0x180027a07  call    fprintf
0x180027a0c  jmp     loc_180027AFC
0x180027a11  mov     [rsp+648h+var_618], r8
0x180027a16  mov     dword ptr [rsp+648h+var_620], esi
0x180027a1a  mov     dword ptr [rsp+648h+Reserved], r10d
0x180027a1f  mov     r9d, r11d
0x180027a22  mov     r8d, ebx
0x180027a25  lea     rdx, aP7WidthDHeight; "P7\nWIDTH %d\nHEIGHT %d\nDEPTH %d\nMAXV"...
0x180027a2c  mov     rcx, [rdi+5D160h]; Stream
0x180027a33  call    fprintf
0x180027a38  jmp     loc_180027AFC
0x180027a3d  test    eax, eax
0x180027a3f  mov     eax, r10d
0x180027a42  cdq
0x180027a43  jz      loc_180027AD5
0x180027a49  lea     rcx, [rdi+10Ch]
0x180027a50  lea     r8, [rdi+0CCh]
0x180027a57  movss   xmm0, dword ptr [rdi+2EFB4h]
0x180027a5f  cvtps2pd xmm0, xmm0
0x180027a62  movss   xmm1, dword ptr [rdi+2EFB0h]
0x180027a6a  cvtps2pd xmm1, xmm1
0x180027a6d  cvttss2si r9d, dword ptr [rdi+2EFA8h]
0x180027a76  movss   xmm3, dword ptr [rdi+2EFACh]
0x180027a7e  cvtps2pd xmm3, xmm3
0x180027a81  sub     eax, edx
0x180027a83  sar     eax, 1
0x180027a85  mov     [rsp+648h+var_5E8], esi
0x180027a89  mov     [rsp+648h+var_5F0], r11d
0x180027a8e  mov     [rsp+648h+var_5F8], ebx
0x180027a92  mov     [rsp+648h+var_600], rcx
0x180027a97  mov     [rsp+648h+var_608], r8
0x180027a9c  movsd   [rsp+648h+var_610], xmm0
0x180027aa2  movsd   [rsp+648h+var_618], xmm1
0x180027aa8  mov     dword ptr [rsp+648h+var_620], r9d
0x180027aad  mov     ecx, [rdi+2EFB8h]
0x180027ab3  mov     dword ptr [rsp+648h+Reserved], ecx
0x180027ab7  movq    r9, xmm3
0x180027abc  lea     r8d, [rax+5]
0x180027ac0  lea     rdx, aPDExptime05fTi; "P%d\n# EXPTIME=%0.5f\n# TIMESTAMP=%d\n#"...
0x180027ac7  mov     rcx, [rdi+5D160h]; Stream
0x180027ace  call    fprintf
0x180027ad3  jmp     short loc_180027AFC
0x180027ad5  sub     eax, edx
0x180027ad7  sar     eax, 1
0x180027ad9  lea     r8d, [rax+5]
0x180027add  mov     dword ptr [rsp+648h+var_620], esi
0x180027ae1  mov     dword ptr [rsp+648h+Reserved], r11d
0x180027ae6  mov     r9d, ebx
0x180027ae9  lea     rdx, aPDDDD; "P%d\n%d %d\n%d\n"
0x180027af0  mov     rcx, [rdi+5D160h]; Stream
0x180027af7  call    fprintf
0x180027afc  mov     r10d, [rdi+30h]
0x180027b00  mov     edx, r15d
0x180027b03  mov     ebx, r10d
0x180027b06  and     ebx, 2
0x180027b09  jz      short loc_180027B11
0x180027b0b  movzx   edx, word ptr [rdi+1Ch]
0x180027b0f  dec     edx
0x180027b11  mov     eax, r15d
0x180027b14  mov     r11d, r10d
0x180027b17  and     r11d, 1
0x180027b1b  jz      short loc_180027B23
0x180027b1d  movzx   eax, word ptr [rdi+1Eh]
0x180027b21  dec     eax
0x180027b23  movzx   ecx, word ptr [rdi+1Eh]
0x180027b27  mov     r12d, ecx
0x180027b2a  imul    r12d, edx
0x180027b2e  add     r12d, eax
0x180027b31  mov     r14d, r10d
0x180027b34  and     r14d, 4
0x180027b38  mov     r8d, r15d
0x180027b3b  setnz   r8b
0x180027b3f  mov     r9d, r15d
0x180027b42  test    r14d, r14d
0x180027b45  setz    r9b
0x180027b49  test    ebx, ebx
0x180027b4b  movzx   ebx, cx
0x180027b4e  jz      short loc_180027B5B
0x180027b50  movzx   edx, word ptr [rdi+1Ch]
0x180027b54  sub     edx, r8d
0x180027b57  dec     edx
0x180027b59  jmp     short loc_180027B5E
0x180027b5b  mov     edx, r8d
0x180027b5e  movzx   esi, cx
0x180027b61  mov     eax, r9d
0x180027b64  test    r11d, r11d
0x180027b67  jz      short loc_180027B73
0x180027b69  mov     eax, ecx
0x180027b6b  sub     eax, r9d
0x180027b6e  dec     eax
0x180027b70  movzx   esi, bx
0x180027b73  mov     r11d, ecx
0x180027b76  imul    r11d, edx
0x180027b7a  sub     r11d, r12d
0x180027b7d  add     r11d, eax
0x180027b80  mov     [rsp+648h+var_5D4], r11d
0x180027b85  test    r14d, r14d
0x180027b88  cmovnz  cx, si
0x180027b8c  test    r10b, 2
0x180027b90  jz      short loc_180027B9D
0x180027b92  movzx   esi, word ptr [rdi+1Ch]
0x180027b96  sub     esi, r9d
0x180027b99  dec     esi
0x180027b9b  jmp     short loc_180027BA0
0x180027b9d  mov     esi, r9d
0x180027ba0  test    r10b, 1
0x180027ba4  jz      short loc_180027BB0
0x180027ba6  movzx   eax, cx
0x180027ba9  sub     eax, r8d
0x180027bac  lea     r8d, [rax-1]
0x180027bb0  movzx   eax, word ptr [rdi+16h]
0x180027bb4  test    dword ptr [rdi+30h], 4
0x180027bbb  mov     r9d, eax
0x180027bbe  cmovz   r9d, r15d
0x180027bc2  mov     edx, r15d
0x180027bc5  bt      r10d, 2
0x180027bca  cmovnb  edx, eax
0x180027bcd  mov     r10d, [rdi+30h]
0x180027bd1  test    r10b, 2
0x180027bd5  jz      short loc_180027BE2
0x180027bd7  movzx   eax, word ptr [rdi+1Ch]
0x180027bdb  sub     eax, r9d
0x180027bde  lea     r9d, [rax-1]
0x180027be2  test    r10b, 1
0x180027be6  jz      short loc_180027BF0
0x180027be8  movzx   eax, cx
0x180027beb  sub     eax, edx
  ... truncated ...
```
