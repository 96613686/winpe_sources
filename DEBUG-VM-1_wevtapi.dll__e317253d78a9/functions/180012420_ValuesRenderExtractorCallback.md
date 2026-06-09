# ValuesRenderExtractorCallback

- ea: `0x180012420`
- end: `0x180012ca2`
- name: `ValuesRenderExtractorCallback`
- size: `2178`
- prototype: `void(void *, unsigned int, struct BinXmlVariant *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180009e80`
- `0x18000ab80`
- `0x18000b6a0`
- `0x180012420`
- `0x180012cb0`
- `0x18001e070`
- `0x180023548`
- `0x18002ddbc`
- `0x180038fb4`
- `0x18003c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ValuesRenderExtractorCallback(char **a1, unsigned int a2, __m128i *a3)
{
  __m128i v6; // xmm1
  unsigned __int64 v7; // xmm0_8
  unsigned int v8; // edi
  unsigned int *v9; // r9
  void *v10; // r12
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  char v16; // r13
  unsigned int v17; // r8d
  __int64 *v18; // rdx
  Buffer *v19; // rcx
  Buffer *v20; // rcx
  unsigned int v21; // ebx
  char **v22; // rcx
  char **v23; // rdx
  char *v24; // rax
  __int64 v25; // r8
  char **v26; // rax
  char **v27; // rdx
  char *v28; // rcx
  __int64 v29; // r8
  unsigned int v30; // eax
  unsigned __int64 v31; // rbx
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  __int64 v36; // rax
  __int64 v37; // r15
  unsigned int v38; // r12d
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // rbx
  Buffer *v42; // r15
  unsigned int *v43; // r14
  unsigned int *v44; // rdi
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  __int64 v48; // r8
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  void *v56[2]; // [rsp+20h] [rbp-108h] BYREF
  void *v57; // [rsp+30h] [rbp-F8h] BYREF
  int v58; // [rsp+38h] [rbp-F0h]
  int v59; // [rsp+3Ch] [rbp-ECh]
  _QWORD v60[2]; // [rsp+40h] [rbp-E8h] BYREF
  __int128 v61; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v62; // [rsp+60h] [rbp-C8h]
  int v63; // [rsp+68h] [rbp-C0h]
  int v64; // [rsp+6Ch] [rbp-BCh]
  int v65; // [rsp+70h] [rbp-B8h]
  __int128 v66; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v67; // [rsp+88h] [rbp-A0h]
  int v68; // [rsp+90h] [rbp-98h]
  int v69; // [rsp+94h] [rbp-94h]
  int v70; // [rsp+98h] [rbp-90h]
  __int128 pExceptionObject; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v72; // [rsp+B0h] [rbp-78h]
  int v73; // [rsp+B8h] [rbp-70h]
  int v74; // [rsp+BCh] [rbp-6Ch]
  int v75; // [rsp+C0h] [rbp-68h]
  __int128 v76; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-50h]
  int v78; // [rsp+E0h] [rbp-48h]
  int v79; // [rsp+E4h] [rbp-44h]
  int v80; // [rsp+E8h] [rbp-40h]
  __int64 v81; // [rsp+130h] [rbp+8h] BYREF
  unsigned int v82; // [rsp+138h] [rbp+10h] BYREF
  __int64 v83; // [rsp+140h] [rbp+18h] BYREF

  if ( (a2 & 0x80000000) != 0 )
    return;
  v82 = a2;
  try
  {
    v6 = *a3;
    *(__m128i *)v56 = v6;
    v7 = _mm_srli_si128(v6, 8).m128i_u64[0];
    if ( HIDWORD(v7) == 21 && a2 == 512 )
    {
      a1[7] = (char *)v6.m128i_i64[0];
      return;
    }
    v8 = 0;
    LOWORD(v83) = 0;
    v9 = (unsigned int *)a1[1];
    v10 = (void *)v9[4];
    LOBYTE(v81) = 1;
    if ( (v7 & 0x8000000000LL) == 0 )
    {
      if ( a2 != 256 )
      {
        v26 = a1 + 3;
        if ( a1[5] != (char *)(a1 + 3) )
        {
          v27 = a1 + 3;
          v28 = *v26;
          do
          {
            if ( *((_DWORD *)v28 + 6) < a2 )
            {
              v29 = 16;
            }
            else
            {
              v27 = (char **)v28;
              v29 = 8;
            }
            v28 = *(char **)&v28[v29];
          }
          while ( v28 != (char *)&utl::_TreeSentinel );
          if ( v27 != v26 && a2 >= *((_DWORD *)v27 + 6) )
          {
            v38 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)*a1 + 24LL))(*a1);
            (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)*a1 + 32LL))(*a1, 16 * a2);
            v39 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)*a1 + 56LL))(*a1);
            v41 = v39;
            if ( v39 && *(_DWORD *)(v39 + 12) )
            {
              utl::_Tree<unsigned long,utl::pair<unsigned long const,utl::pair<Buffer,Buffer>>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,utl::pair<Buffer,Buffer>>>,0>::_TryEmplace<unsigned long const &,>(
                a1[2],
                v60,
                v40,
                &v82);
              if ( !v60[0] )
              {
                if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    10,
                    &WPP_25784448a5fb32d0e97b496fe73d429b_Traceguids,
                    14);
                }
                v61 = 0;
                v62 = 0;
                v63 = 14;
                v64 = -1;
                v65 = 98;
                throw (EvtException *)&v61;
              }
              v42 = (Buffer *)(v60[0] + 32LL);
              v43 = (unsigned int *)(v60[0] + 64LL);
              v57 = 0;
              v58 = -1;
              v59 = 0;
              if ( *(char *)(v41 + 12) < 0 )
              {
                v44 = (unsigned int *)(v60[0] + 80LL);
              }
              else
              {
                BinXmlVariantHolder::InitToString((BinXmlVariantHolder *)&v57, (const struct BinXmlVariant *)v41);
                v44 = v43 + 4;
                v81 = v43[4];
                Buffer::Write(v42, &v81, 8u);
                Buffer::Write((Buffer *)v43, v57, 2 * v58);
                *(_DWORD *)(v41 + 12) = 129;
                *(_DWORD *)(v41 + 8) = 1;
                *(_QWORD *)v41 = 0;
              }
              BinXmlVariantHolder::InitToString((BinXmlVariantHolder *)&v57, (const struct BinXmlVariant *)a3);
              v81 = *v44;
              Buffer::Write(v42, &v81, 8u);
              Buffer::Write((Buffer *)v43, v57, 2 * v58);
              ++*(_DWORD *)(v41 + 8);
              BinXmlVariantHolder::Clear((BinXmlVariantHolder *)&v57);
            }
            if ( (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)*a1 + 24LL))(*a1) < v38 )
              (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)*a1 + 32LL))(*a1, v38);
            return;
          }
        }
      }
      v11 = _mm_cvtsi128_si32(_mm_srli_si128(v6, 12)) - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 12;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( !v14 || (v15 = v14 - 3) == 0 )
            {
              Buffer::Write((Buffer *)v9, v56[0], 0x10u);
              LODWORD(v56[1]) = 0;
              goto LABEL_16;
            }
            if ( v15 != 1 )
            {
              LODWORD(v56[1]) = 0;
              v16 = v81;
LABEL_18:
              v20 = (Buffer *)a1[1];
              if ( (*((_DWORD *)v20 + 4) & 7) != 0 )
                Buffer::Advance(v20, 8 - (*((_DWORD *)v20 + 4) & 7));
              if ( v16 )
              {
                v21 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)*a1 + 24LL))(*a1);
                if ( a2 != 256 )
                {
                  v22 = a1 + 3;
                  if ( a1[5] != (char *)(a1 + 3) )
                  {
                    v23 = a1 + 3;
                    v24 = *v22;
                    do
                    {
                      if ( *((_DWORD *)v24 + 6) < a2 )
                      {
                        v25 = 16;
                      }
                      else
                      {
                        v23 = (char **)v24;
                        v25 = 8;
                      }
                      v24 = *(char **)&v24[v25];
                    }
                    while ( v24 != (char *)&utl::_TreeSentinel );
                    if ( v23 != v22 && a2 >= *((_DWORD *)v23 + 6) )
                    {
                      utl::_Tree<unsigned long,unsigned long,utl::less<unsigned long>,utl::allocator<unsigned long>,0>::_InsertImpl<unsigned long const &>(
                        v22,
                        v60,
                        v25,
                        &v82);
                      if ( !v60[0] )
                      {
                        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          WPP_SF_D(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            13,
                            &WPP_25784448a5fb32d0e97b496fe73d429b_Traceguids,
                            14);
                        }
                        pExceptionObject = 0;
                        v72 = 0;
                        v73 = 14;
                        v74 = -1;
                        v75 = 318;
                        throw (EvtException *)&pExceptionObject;
                      }
                    }
                  }
                  (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)*a1 + 32LL))(*a1, 16 * a2);
                }
                (*(void (__fastcall **)(char *, void **, __int64))(*(_QWORD *)*a1 + 8LL))(*a1, v56, 16);
                if ( (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)*a1 + 24LL))(*a1) < v21 )
                  (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)*a1 + 32LL))(*a1, v21);
              }
              return;
            }
          }
          v17 = (unsigned int)v56[1];
          v18 = (__int64 *)v56[0];
          v19 = (Buffer *)v9;
LABEL_15:
          Buffer::Write(v19, v18, v17);
LABEL_16:
          v16 = v81;
LABEL_17:
          v56[0] = v10;
          goto LABEL_18;
        }
        Buffer::Write((Buffer *)v9, v56[0], (unsigned int)v56[1]);
        v17 = 1;
      }
      else
      {
        Buffer::Write((Buffer *)v9, v56[0], 2 * LODWORD(v56[1]));
        v17 = 2;
      }
      v18 = &v83;
      v19 = (Buffer *)a1[1];
      goto LABEL_15;
    }
    v30 = _mm_cvtsi128_si32(_mm_srli_si128(v6, 12)) & 0xFFFFFF7F;
    v31 = 0;
    if ( v30 > 0xA )
    {
      v49 = v30 - 11;
      if ( !v49 )
        goto LABEL_87;
      v50 = v49 - 1;
      if ( !v50 )
      {
LABEL_110:
        v31 = 8LL * (unsigned int)v7;
        goto LABEL_52;
      }
      v51 = v50 - 1;
      if ( !v51 )
        goto LABEL_87;
      v52 = v51 - 2;
      if ( !v52 )
        goto LABEL_109;
      v53 = v52 - 2;
      if ( !v53 )
        goto LABEL_110;
      v54 = v53 - 1;
      if ( !v54 )
      {
LABEL_109:
        v31 = 16LL * (unsigned int)v7;
        goto LABEL_52;
      }
      v47 = v54 - 1;
      if ( !v47 )
      {
        while ( v8 < LODWORD(v56[1]) )
        {
          v83 = (__int64)v10 + 8 * LODWORD(v56[1]) + v31;
          v31 += 4LL * *((unsigned __int8 *)v56[0] + v31 + 1) + 8;
          Buffer::Write((Buffer *)a1[1], &v83, 8u);
          ++v8;
        }
        goto LABEL_52;
      }
    }
    else
    {
      if ( v30 == 10 )
        goto LABEL_110;
      v32 = v30 - 1;
      if ( !v32 )
      {
        v16 = v81;
        while ( v8 < LODWORD(v56[1]) )
        {
          v36 = -1;
          do
            ++v36;
          while ( *(_WORD *)((char *)v56[0] + 2 * v36 + v31) );
          v37 = v36 + 1;
          v81 = (__int64)v10 + 8 * LODWORD(v56[1]) + v31;
          Buffer::Write((Buffer *)a1[1], &v81, 8u);
          if ( ((unsigned __int64)a1[7] & 0x80000000000000LL) != 0 )
          {
            v59 = 1;
            v57 = (void *)v81;
            v58 = v37;
            (*(void (__fastcall **)(char *, void **, __int64))(*(_QWORD *)*a1 + 8LL))(*a1, &v57, 16);
            v16 = 0;
          }
          v31 += 2 * v37;
          ++v8;
        }
        goto LABEL_53;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        while ( v8 < LODWORD(v56[1]) )
        {
          v48 = -1;
          do
            ++v48;
          while ( *((_BYTE *)v56[0] + v31 + v48) );
          v83 = (__int64)v10 + 8 * LODWORD(v56[1]) + v31;
          v31 += v48 + 1;
          Buffer::Write((Buffer *)a1[1], &v83, 8u);
          ++v8;
        }
        goto LABEL_52;
      }
      v34 = v33 - 1;
      if ( !v34 || (v35 = v34 - 1) == 0 )
      {
        v31 = (unsigned int)v7;
LABEL_52:
        v16 = v81;
LABEL_53:
        if ( v31 > 0xFFFFFFFF )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_25784448a5fb32d0e97b496fe73d429b_Traceguids, 13);
          }
          v76 = 0;
          v77 = 0;
          v78 = 13;
          v79 = -1;
          v80 = 286;
          throw (EvtException *)&v76;
        }
        Buffer::Write((Buffer *)a1[1], v56[0], v31);
        goto LABEL_17;
      }
      v45 = v35 - 1;
      if ( !v45 || (v46 = v45 - 1) == 0 )
      {
        v31 = 2LL * (unsigned int)v7;
        goto LABEL_52;
      }
      v47 = v46 - 1;
      if ( !v47 )
      {
LABEL_87:
        v31 = 4LL * (unsigned int)v7;
        goto LABEL_52;
      }
    }
    v55 = v47 - 1;
    if ( !v55 )
      goto LABEL_87;
    if ( v55 != 1 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_25784448a5fb32d0e97b496fe73d429b_Traceguids, 13);
      }
      v66 = 0;
      v67 = 0;
      v68 = 13;
      v69 = -1;
      v70 = 280;
      throw (EvtException *)&v66;
    }
    goto LABEL_110;
  }
  catch ( EvtException )
  {
  }
}

```

## disassembly

```asm
0x180012420  test    edx, edx
0x180012422  js      locret_1800125B3
0x180012428  mov     [rsp+arg_8], edx
0x18001242c  push    rbx
0x18001242d  push    rsi
0x18001242e  push    rdi
0x18001242f  push    r12
0x180012431  push    r13
0x180012433  push    r14
0x180012435  push    r15
0x180012437  sub     rsp, 0F0h
0x18001243e  mov     r13, r8
0x180012441  mov     r14d, edx
0x180012444  mov     rsi, rcx
0x180012447  movups  xmm1, xmmword ptr [r8]
0x18001244b  movups  xmmword ptr [rsp+128h+var_108], xmm1
0x180012450  movdqa  xmm0, xmm1
0x180012454  psrldq  xmm0, 8
0x180012459  movq    rdx, xmm0
0x18001245e  mov     rcx, rdx
0x180012461  shr     rcx, 20h
0x180012465  cmp     ecx, 15h
0x180012468  jz      loc_1800125E7
0x18001246e  xor     edi, edi
0x180012470  mov     word ptr [rsp+128h+arg_10], di
0x180012478  mov     r9, [rsi+8]
0x18001247c  mov     r12d, [r9+10h]
0x180012480  mov     byte ptr [rsp+128h+arg_0], 1
0x180012488  test    cl, cl
0x18001248a  js      loc_180012718
0x180012490  cmp     r14d, 100h
0x180012497  jnz     loc_1800126E5
0x18001249d  lea     r15, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800124a4  psrldq  xmm1, 0Ch
0x1800124a9  movd    eax, xmm1
0x1800124ad  sub     eax, 1
0x1800124b0  jz      short loc_1800124F2
0x1800124b2  sub     eax, 1
0x1800124b5  jz      loc_180012A57
0x1800124bb  sub     eax, 0Ch
0x1800124be  jz      loc_180012788
0x1800124c4  sub     eax, 1
0x1800124c7  jz      loc_1800125FB
0x1800124cd  sub     eax, 3
0x1800124d0  jz      loc_1800125FB
0x1800124d6  cmp     eax, 1
0x1800124d9  jz      loc_180012788
0x1800124df  mov     dword ptr [rsp+128h+var_108+8], edi
0x1800124e3  mov     edi, 0FFFFFFFFh
0x1800124e8  mov     r13b, byte ptr [rsp+128h+arg_0]
0x1800124f0  jmp     short loc_180012530
0x1800124f2  mov     r8d, dword ptr [rsp+128h+var_108+8]
0x1800124f7  add     r8d, r8d; unsigned int
0x1800124fa  mov     rdx, [rsp+128h+var_108]; void *
0x1800124ff  mov     rcx, r9; this
0x180012502  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x180012507  mov     r8d, 2; unsigned int
0x18001250d  lea     rdx, [rsp+128h+arg_10]; void *
0x180012515  mov     rcx, [rsi+8]; this
0x180012519  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x18001251e  mov     edi, 0FFFFFFFFh
0x180012523  mov     r13b, byte ptr [rsp+128h+arg_0]
0x18001252b  mov     [rsp+128h+var_108], r12
0x180012530  mov     rcx, [rsi+8]; this
0x180012534  mov     eax, [rcx+10h]
0x180012537  and     eax, 7
0x18001253a  jnz     loc_1800125D6
0x180012540  xor     r12d, r12d
0x180012543  test    r13b, r13b
0x180012546  jz      short loc_1800125A1
0x180012548  mov     rcx, [rsi]
0x18001254b  mov     rax, [rcx]
0x18001254e  mov     rax, [rax+18h]
0x180012552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012557  mov     ebx, eax
0x180012559  cmp     r14d, 100h
0x180012560  jnz     short loc_1800125B4
0x180012562  mov     rcx, [rsi]
0x180012565  mov     rax, [rcx]
0x180012568  mov     r8d, 10h
0x18001256e  lea     rdx, [rsp+128h+var_108]
0x180012573  mov     rax, [rax+8]
0x180012577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001257c  mov     rcx, [rsi]
0x18001257f  mov     rax, [rcx]
0x180012582  mov     rax, [rax+18h]
0x180012586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001258b  cmp     eax, ebx
0x18001258d  jnb     short loc_1800125A1
0x18001258f  mov     rcx, [rsi]
0x180012592  mov     rax, [rcx]
0x180012595  mov     edx, ebx
0x180012597  mov     rax, [rax+20h]
0x18001259b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125a0  nop
0x1800125a1  add     rsp, 0F0h
0x1800125a8  pop     r15
0x1800125aa  pop     r14
0x1800125ac  pop     r13
0x1800125ae  pop     r12
0x1800125b0  pop     rdi
0x1800125b1  pop     rsi
0x1800125b2  pop     rbx
0x1800125b3  retn
0x1800125b4  lea     rcx, [rsi+18h]
0x1800125b8  cmp     [rcx+10h], rcx
0x1800125bc  jnz     short loc_180012617
0x1800125be  mov     rcx, [rsi]
0x1800125c1  mov     rax, [rcx]
0x1800125c4  shl     r14d, 4
0x1800125c8  mov     edx, r14d
0x1800125cb  mov     rax, [rax+20h]
0x1800125cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125d4  jmp     short loc_180012562
0x1800125d6  mov     edx, 8
0x1800125db  sub     edx, eax; unsigned int
0x1800125dd  call    ?Advance@Buffer@@UEAAXK@Z; Buffer::Advance(ulong)
0x1800125e2  jmp     loc_180012540
0x1800125e7  cmp     r14d, 200h
0x1800125ee  jnz     loc_18001246E
0x1800125f4  movsd   qword ptr [rsi+38h], xmm1
0x1800125f9  jmp     short loc_1800125A1
0x1800125fb  mov     r8d, 10h; unsigned int
0x180012601  mov     rdx, [rsp+128h+var_108]; void *
0x180012606  mov     rcx, r9; this
0x180012609  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x18001260e  mov     dword ptr [rsp+128h+var_108+8], edi
0x180012612  jmp     loc_18001251E
0x180012617  mov     rdx, rcx
0x18001261a  mov     rax, [rcx]
0x18001261d  cmp     [rax+18h], r14d
0x180012621  jb      loc_18001279A
0x180012627  mov     rdx, rax
0x18001262a  mov     r8d, 8
0x180012630  mov     rax, [rax+r8]
0x180012634  cmp     rax, r15
0x180012637  jnz     short loc_18001261D
0x180012639  cmp     rdx, rcx
0x18001263c  jz      short loc_1800125BE
0x18001263e  cmp     r14d, [rdx+18h]
0x180012642  jb      loc_1800125BE
0x180012648  lea     r9, [rsp+128h+arg_8]
0x180012650  lea     rdx, [rsp+128h+var_E8]
0x180012655  call    ??$_InsertImpl@AEBK@?$_Tree@KKU?$less@K@utl@@V?$allocator@K@2@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@K@utl@@_N@1@PEAU?$_TreeNode@K@1@AEBK@Z; utl::_Tree<ulong,ulong,utl::less<ulong>,utl::allocator<ulong>,0>::_InsertImpl<ulong const &>(utl::_TreeNode<ulong> *,ulong const &)
0x18001265a  cmp     [rsp+128h+var_E8], r12
0x18001265f  jnz     loc_1800125BE
0x180012665  lea     rax, WPP_GLOBAL_Control
0x18001266c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012673  cmp     rcx, rax
0x180012676  jz      short loc_1800126A0
0x180012678  test    dword ptr [rcx+1Ch], 40000h
0x18001267f  jz      short loc_1800126A0
0x180012681  cmp     byte ptr [rcx+19h], 2
0x180012685  jb      short loc_1800126A0
0x180012687  mov     edx, 0Dh
0x18001268c  lea     r9d, [rdx+1]
0x180012690  lea     r8, WPP_25784448a5fb32d0e97b496fe73d429b_Traceguids
0x180012697  mov     rcx, [rcx+10h]
0x18001269b  call    WPP_SF_D
0x1800126a0  xorps   xmm0, xmm0
0x1800126a3  movdqu  [rsp+128h+pExceptionObject], xmm0
0x1800126ac  mov     [rsp+128h+var_78], r12
0x1800126b4  mov     [rsp+128h+var_70], 0Eh
0x1800126bf  mov     [rsp+128h+var_6C], edi
0x1800126c6  mov     [rsp+128h+var_68], 13Eh
0x1800126d1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800126d8  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x1800126e0  call    _CxxThrowException_0
0x1800126e5  lea     rax, [rsi+18h]
0x1800126e9  cmp     [rax+10h], rax
0x1800126ed  jz      loc_18001249D
0x1800126f3  mov     rdx, rax
0x1800126f6  mov     rcx, [rax]
0x1800126f9  lea     r15, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180012700  cmp     [rcx+18h], r14d
0x180012704  jb      loc_18001284A
0x18001270a  mov     rdx, rcx
0x18001270d  mov     r8d, 8
0x180012713  jmp     loc_180012850
0x180012718  psrldq  xmm1, 0Ch
0x18001271d  movd    eax, xmm1
0x180012721  btr     eax, 7
0x180012725  mov     rbx, rdi
0x180012728  cmp     eax, 0Ah
0x18001272b  ja      loc_180012AF1
0x180012731  jz      loc_180012C0F
0x180012737  sub     eax, 1
0x18001273a  jz      short loc_1800127A5
0x18001273c  sub     eax, 1
0x18001273f  jz      loc_180012A9C
0x180012745  sub     eax, 1
0x180012748  jz      short loc_180012753
0x18001274a  sub     eax, 1
0x18001274d  jnz     loc_180012A74
0x180012753  mov     ebx, edx
0x180012755  mov     r13b, byte ptr [rsp+128h+arg_0]
0x18001275d  mov     edi, 0FFFFFFFFh
0x180012762  cmp     rbx, rdi
0x180012765  ja      loc_180012C1A
0x18001276b  mov     r8d, ebx; unsigned int
0x18001276e  mov     rdx, [rsp+128h+var_108]; void *
0x180012773  mov     rcx, [rsi+8]; this
0x180012777  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x18001277c  lea     r15, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180012783  jmp     loc_18001252B
0x180012788  mov     r8d, dword ptr [rsp+128h+var_108+8]
0x18001278d  mov     rdx, [rsp+128h+var_108]
0x180012792  mov     rcx, r9
0x180012795  jmp     loc_180012519
0x18001279a  mov     r8d, 10h
0x1800127a0  jmp     loc_180012630
0x1800127a5  mov     r13b, byte ptr [rsp+128h+arg_0]
0x1800127ad  cmp     edi, dword ptr [rsp+128h+var_108+8]
0x1800127b1  jnb     short loc_18001275D
0x1800127b3  mov     rcx, [rsp+128h+var_108]
0x1800127b8  add     rcx, rbx
0x1800127bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800127bf  xor     edx, edx
0x1800127c1  inc     rax
0x1800127c4  cmp     [rcx+rax*2], dx
0x1800127c8  jnz     short loc_1800127C1
0x1800127ca  lea     r15, [rax+1]
0x1800127ce  mov     edx, dword ptr [rsp+128h+var_108+8]
0x1800127d2  lea     rcx, [rbx+r12]
0x1800127d6  lea     rax, [rcx+rdx*8]
0x1800127da  mov     [rsp+128h+arg_0], rax
0x1800127e2  mov     r8d, 8; unsigned int
0x1800127e8  lea     rdx, [rsp+128h+arg_0]; void *
0x1800127f0  mov     rcx, [rsi+8]; this
0x1800127f4  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x1800127f9  mov     rax, 80000000000000h
0x180012803  test    [rsi+38h], rax
0x180012807  jnz     short loc_180012811
0x180012809  lea     rbx, [rbx+r15*2]
0x18001280d  inc     edi
0x18001280f  jmp     short loc_1800127AD
0x180012811  mov     [rsp+128h+var_EC], 1
0x180012819  mov     rax, [rsp+128h+arg_0]
0x180012821  mov     [rsp+128h+var_F8], rax
0x180012826  mov     [rsp+128h+var_F0], r15d
0x18001282b  mov     rcx, [rsi]
0x18001282e  mov     rax, [rcx]
0x180012831  mov     r8d, 10h
0x180012837  lea     rdx, [rsp+128h+var_F8]
0x18001283c  mov     rax, [rax+8]
0x180012840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012845  xor     r13b, r13b
0x180012848  jmp     short loc_180012809
0x18001284a  mov     r8d, 10h
0x180012850  mov     rcx, [rcx+r8]
0x180012854  cmp     rcx, r15
0x180012857  jnz     loc_180012700
0x18001285d  cmp     rdx, rax
0x180012860  jz      loc_1800124A4
0x180012866  cmp     r14d, [rdx+18h]
0x18001286a  jb      loc_1800124A4
0x180012870  mov     rcx, [rsi]
0x180012873  mov     rax, [rcx]
0x180012876  mov     rax, [rax+18h]
0x18001287a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001287f  mov     r12d, eax
0x180012882  mov     rcx, [rsi]
0x180012885  mov     rdx, [rcx]
0x180012888  shl     r14d, 4
0x18001288c  mov     rax, [rdx+20h]
0x180012890  mov     edx, r14d
0x180012893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012898  mov     rcx, [rsi]
0x18001289b  mov     rax, [rcx]
0x18001289e  mov     rax, [rax+38h]
0x1800128a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128a7  mov     rbx, rax
0x1800128aa  test    rax, rax
0x1800128ad  jz      loc_180012A2C
0x1800128b3  cmp     [rax+0Ch], edi
0x1800128b6  jz      loc_180012A2C
0x1800128bc  lea     r9, [rsp+128h+arg_8]
0x1800128c4  lea     rdx, [rsp+128h+var_E8]
0x1800128c9  mov     rcx, [rsi+10h]
0x1800128cd  call    ??$_TryEmplace@AEBK$$V@?$_Tree@KU?$pair@$$CBKU?$pair@VBuffer@@V1@@utl@@@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKU?$pair@VBuffer@@V1@@utl@@@utl@@@2@$0A@@utl@@IEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKU?$pair@VBuffer@@V1@@utl@@@utl@@@utl@@_N@1@PEAU?$_TreeNode@U?$pair@$$CBKU?$pair@VBuffer@@V1@@utl@@@utl@@@1@AEBK@Z; utl::_Tree<ulong,utl::pair<ulong const,utl::pair<Buffer,Buffer>>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,utl::pair<Buffer,Buffer>>>,0>::_TryEmplace<ulong const &,>(utl::_TreeNode<utl::pair<ulong const,utl::pair<Buffer,Buffer>>> *,ulong const &)
0x1800128d2  mov     rax, [rsp+128h+var_E8]
0x1800128d7  test    rax, rax
0x1800128da  jz      loc_180012965
0x1800128e0  lea     r15, [rax+20h]
0x1800128e4  lea     r14, [rax+40h]
0x1800128e8  mov     [rsp+128h+var_F8], rdi
0x1800128ed  mov     edi, 0FFFFFFFFh
0x1800128f2  mov     [rsp+128h+var_F0], edi
0x1800128f6  mov     [rsp+128h+var_EC], 0
0x1800128fe  test    byte ptr [rbx+0Ch], 80h
0x180012902  jnz     loc_1800129D9
0x180012908  mov     rdx, rbx; struct BinXmlVariant *
0x18001290b  lea     rcx, [rsp+128h+var_F8]; this
0x180012910  call    ?InitToString@BinXmlVariantHolder@@QEAA_NAEBUBinXmlVariant@@@Z; BinXmlVariantHolder::InitToString(BinXmlVariant const &)
0x180012915  lea     rdi, [r14+10h]
0x180012919  mov     eax, [rdi]
0x18001291b  mov     [rsp+128h+arg_0], rax
0x180012923  mov     r8d, 8; unsigned int
0x180012929  lea     rdx, [rsp+128h+arg_0]; void *
0x180012931  mov     rcx, r15; this
  ... truncated ...
```
