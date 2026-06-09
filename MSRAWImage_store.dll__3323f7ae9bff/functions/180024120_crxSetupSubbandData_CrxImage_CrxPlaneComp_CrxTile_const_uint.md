# crxSetupSubbandData(CrxImage *,CrxPlaneComp *,CrxTile const *,uint)

- ea: `0x180024120`
- end: `0x18002455c`
- name: `?crxSetupSubbandData@@YAHPEAUCrxImage@@PEAUCrxPlaneComp@@PEBUCrxTile@@I@Z`
- size: `1084`
- prototype: `__int64 __fastcall(struct CrxImage *, struct CrxPlaneComp *, const struct CrxTile *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180021a40`

## callees

- `0x180009000`
- `0x180009520`
- `0x180020ab0`
- `0x180024120`

## pseudocode

```c
__int64 __fastcall crxSetupSubbandData(
        struct CrxImage *a1,
        struct CrxPlaneComp *a2,
        const struct CrxTile *a3,
        unsigned int a4)
{
  int v4; // r10d
  __int64 v5; // r13
  signed int v6; // r14d
  __int64 v7; // r12
  unsigned int v10; // eax
  bool v11; // zf
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  unsigned __int8 *v17; // rsi
  int v18; // eax
  int v19; // edx
  __int64 v20; // r9
  __int64 v21; // r8
  unsigned __int16 v22; // cx
  char *v23; // rax
  char *v24; // r8
  __int64 v25; // r10
  __int64 v26; // r9
  int *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  libraw_memmgr *v30; // r9
  int v31; // r11d
  __int64 v32; // rbx
  _QWORD *v33; // rdx
  unsigned __int8 v34; // cl
  _WORD *v35; // r9
  __int64 v36; // r14
  unsigned __int16 *v37; // r10
  __int16 v38; // cx
  unsigned __int16 *v39; // rax
  __int64 v40; // rax
  __int64 v41; // r8
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 i; // rdi
  __int64 v50; // rbx
  __int64 v51; // r14
  char v52; // si
  int v53; // ebp
  int v54; // edx
  __int64 v55; // rcx
  int v56; // r12d
  __int64 v57; // r13
  _QWORD *v58; // rax
  __int64 v59; // rdx
  unsigned int v61; // [rsp+20h] [rbp-68h]
  __int16 v62; // [rsp+20h] [rbp-68h]
  libraw_memmgr *v63; // [rsp+28h] [rbp-60h]
  __int64 v64; // [rsp+30h] [rbp-58h]
  __int64 v65; // [rsp+38h] [rbp-50h]
  __int64 v66; // [rsp+40h] [rbp-48h]
  int v68; // [rsp+98h] [rbp+10h]
  __int16 v69; // [rsp+98h] [rbp+10h]

  v4 = 0;
  v5 = *((_QWORD *)a2 + 1);
  v6 = 0;
  v7 = a4;
  v68 = 0;
  v10 = 3 * *((unsigned __int8 *)a1 + 9);
  v64 = v5;
  v11 = v10++ == -1;
  v13 = v10;
  v65 = v10;
  v61 = v10;
  if ( v11 )
  {
    v17 = (unsigned __int8 *)a1 + 9;
  }
  else
  {
    v14 = 0;
    v15 = v5 + 48;
    do
    {
      v16 = *(unsigned __int16 *)(v15 - 24);
      v15 += 88;
      v16 *= 4;
      ++v14;
      v4 += v16;
      *(_DWORD *)(v15 - 88) = v16;
    }
    while ( v14 < v13 );
    v17 = (unsigned __int8 *)a1 + 9;
  }
  v18 = *((unsigned __int8 *)a1 + 9);
  if ( (_BYTE)v18 )
  {
    v19 = 0;
    v6 = (v4 + 7) & 0xFFFFFFF8;
    v4 = v6 + 112 * v18;
    v68 = v4;
    v20 = *((unsigned __int8 *)a1 + 9);
    v21 = 0;
    do
    {
      if ( v19 >= v18 - 1 )
        v22 = *((_WORD *)a3 + 14);
      else
        v22 = *(_WORD *)(v21 + *((_QWORD *)a2 + 1) + 464);
      ++v19;
      v21 += 264;
      v4 += 32 * v22;
      --v20;
    }
    while ( v20 );
    v17 = (unsigned __int8 *)a1 + 9;
  }
  v63 = (struct CrxImage *)((char *)a1 + 88);
  v23 = (char *)libraw_memmgr::malloc((struct CrxImage *)((char *)a1 + 88), v4);
  *(_QWORD *)a2 = v23;
  v24 = v23;
  if ( !v23 )
    return 0xFFFFFFFFLL;
  v25 = *((_QWORD *)a1 + 3) + v7;
  if ( v13 )
  {
    v26 = 0;
    v27 = (int *)(v5 + 48);
    do
    {
      v28 = *v27;
      ++v26;
      v29 = *((_QWORD *)v27 + 2);
      *((_QWORD *)v27 - 4) = v24;
      v27 += 22;
      v24 += v28;
      *((_QWORD *)v27 - 16) = v25 + v29;
    }
    while ( v26 < v13 );
    v30 = (struct CrxImage *)((char *)a1 + 88);
    v63 = (struct CrxImage *)((char *)a1 + 88);
    v17 = (unsigned __int8 *)a1 + 9;
  }
  else
  {
    v30 = (struct CrxImage *)((char *)a1 + 88);
  }
  if ( *((_BYTE *)a1 + 9) )
  {
    v31 = 0;
    v32 = *(_QWORD *)a2 + v68;
    v33 = (_QWORD *)(*(_QWORD *)a2 + v6);
    *((_QWORD *)a2 + 2) = v33;
    v63 = v30;
    *v33 = *(_QWORD *)(v5 + 16);
    v34 = *v17;
    if ( *v17 )
    {
      v35 = (_WORD *)v33 + 51;
      v36 = v5;
      v37 = (unsigned __int16 *)(v5 + 464);
      do
      {
        if ( v31 < v34 - 1 )
        {
          v38 = *(v37 - 43);
          v39 = v37;
        }
        else
        {
          v38 = *((_WORD *)a3 + 15);
          v39 = (unsigned __int16 *)((char *)a3 + 28);
        }
        *v35 = v38;
        ++v31;
        v40 = *v39;
        v35[1] = v40;
        *(_QWORD *)(v35 - 35) = v32;
        v41 = 4 * v40;
        v42 = 4 * v40 + v32;
        *(_QWORD *)(v35 - 31) = v42;
        *(_QWORD *)(v35 - 27) = v42 + v41;
        v43 = v42 + v41 + v41;
        *(_QWORD *)(v35 - 23) = v43;
        *(_QWORD *)(v35 - 19) = v43 + v41;
        v44 = v43 + v41 + v41;
        *(_QWORD *)(v35 - 15) = v44;
        *(_QWORD *)(v35 - 11) = v44 + v41;
        v45 = v44 + v41 + v41;
        *(_QWORD *)(v35 - 7) = v45;
        v32 = v45 + v41;
        *(_DWORD *)(v35 - 3) = 0;
        *((_BYTE *)v35 - 2) = 0;
        v46 = *(_QWORD *)(v36 + 104);
        v36 += 264;
        *(_QWORD *)(v35 - 47) = v46;
        *(_QWORD *)(v35 - 43) = *((_QWORD *)v37 - 34);
        v47 = *((_QWORD *)v37 - 23);
        v37 += 132;
        *(_QWORD *)(v35 - 39) = v47;
        v35 += 56;
        v34 = *v17;
      }
      while ( v31 < *v17 );
      v30 = (struct CrxImage *)((char *)a1 + 88);
      v63 = (struct CrxImage *)((char *)a1 + 88);
    }
  }
  if ( v61 )
  {
    v48 = v65;
    for ( i = 0; i < v48; ++i )
    {
      v50 = 88 * i;
      v51 = *(_QWORD *)(88 * i + v5 + 56);
      if ( v51 )
      {
        v52 = 0;
        v53 = 0;
        if ( *((_BYTE *)a2 + 44) && !i )
        {
          v53 = *((_DWORD *)a2 + 12);
          v52 = 1;
        }
        v54 = *(unsigned __int16 *)(v50 + v5 + 24);
        v55 = 0;
        v69 = *(_WORD *)(v50 + v5 + 26);
        v66 = *(_QWORD *)(v50 + v5 + 8);
        if ( !v52 )
          v55 = (unsigned int)(4 * v54);
        v62 = *(_WORD *)(v50 + v5 + 24);
        v56 = v55;
        v57 = (unsigned int)(2 * v54 + 4);
        v58 = libraw_memmgr::calloc(v30, 1u, v55 + 4 * (v57 + 16412));
        if ( !v58 )
          return 0xFFFFFFFFLL;
        *(_QWORD *)(v50 + v64) = v58;
        v58[8203] = v58 + 8206;
        if ( v56 )
          v59 = *(_QWORD *)(*(_QWORD *)(v50 + v64) + 65624LL) + 4 * v57;
        else
          v59 = 0;
        v5 = v64;
        *(_QWORD *)(*(_QWORD *)(v50 + v64) + 65632LL) = v59;
        *(_WORD *)(*(_QWORD *)(v50 + v64) + 65576LL) = v62;
        *(_WORD *)(*(_QWORD *)(v50 + v64) + 65578LL) = v69;
        *(_DWORD *)(*(_QWORD *)(v50 + v64) + 65584LL) = 0;
        *(_WORD *)(*(_QWORD *)(v50 + v64) + 65588LL) = 0;
        *(_DWORD *)(*(_QWORD *)(v50 + v64) + 65580LL) = v53;
        *(_BYTE *)(*(_QWORD *)(v50 + v64) + 65640LL) = v52;
        *(_DWORD *)(*(_QWORD *)(v50 + v64) + 65560LL) = 0;
        *(_DWORD *)(*(_QWORD *)(v50 + v64) + 65564LL) = 0;
        *(_QWORD *)(*(_QWORD *)(v50 + v64) + 0x10000LL) = v51;
        *(_DWORD *)(*(_QWORD *)(v50 + v64) + 65552LL) = 0;
        *(_DWORD *)(*(_QWORD *)(v50 + v64) + 65556LL) = 0;
        *(_QWORD *)(*(_QWORD *)(v50 + v64) + 65544LL) = v66;
        *(_QWORD *)(*(_QWORD *)(v50 + v64) + 65568LL) = *((_QWORD *)a1 + 10);
        crxFillBuffer(*(_QWORD *)(v50 + v64));
        v48 = v65;
        v30 = v63;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180024120  mov     [rsp+arg_10], rbx
0x180024125  mov     [rsp+arg_0], rcx
0x18002412a  push    rbp
0x18002412b  push    rsi
0x18002412c  push    rdi
0x18002412d  push    r12
0x18002412f  push    r13
0x180024131  push    r14
0x180024133  push    r15
0x180024135  sub     rsp, 50h
0x180024139  movzx   eax, byte ptr [rcx+9]
0x18002413d  xor     r10d, r10d
0x180024140  mov     r13, [rdx+8]
0x180024144  xor     r14d, r14d
0x180024147  mov     r12d, r9d
0x18002414a  mov     rdi, r8
0x18002414d  mov     r15, rdx
0x180024150  mov     [rsp+88h+arg_8], r10d
0x180024158  lea     eax, [rax+rax*2]
0x18002415b  mov     [rsp+88h+var_58], r13
0x180024160  add     eax, 1
0x180024163  mov     rbp, rcx
0x180024166  mov     ebx, eax
0x180024168  mov     [rsp+88h+var_50], rbx
0x18002416d  mov     [rsp+88h+var_68], eax
0x180024171  jz      short loc_18002419F
0x180024173  xor     edx, edx
0x180024175  lea     rcx, [r13+30h]
0x180024179  nop     dword ptr [rax+00000000h]
0x180024180  movzx   eax, word ptr [rcx-18h]
0x180024184  lea     rcx, [rcx+58h]
0x180024188  shl     eax, 2
0x18002418b  inc     rdx
0x18002418e  add     r10d, eax
0x180024191  mov     [rcx-58h], eax
0x180024194  cmp     rdx, rbx
0x180024197  jl      short loc_180024180
0x180024199  lea     rsi, [rbp+9]
0x18002419d  jmp     short loc_1800241A3
0x18002419f  lea     rsi, [rcx+9]
0x1800241a3  movzx   eax, byte ptr [rbp+9]
0x1800241a7  test    al, al
0x1800241a9  jz      short loc_180024206
0x1800241ab  lea     r14d, [r10+7]
0x1800241af  xor     edx, edx
0x1800241b1  imul    r10d, eax, 70h ; 'p'
0x1800241b5  and     r14d, 0FFFFFFF8h
0x1800241b9  add     r10d, r14d
0x1800241bc  mov     [rsp+88h+arg_8], r10d
0x1800241c4  test    eax, eax
0x1800241c6  jz      short loc_180024206
0x1800241c8  mov     r9d, eax
0x1800241cb  lea     r11d, [rax-1]
0x1800241cf  xor     r8d, r8d
0x1800241d2  cmp     edx, r11d
0x1800241d5  jge     short loc_1800241E6
0x1800241d7  mov     rax, [r15+8]
0x1800241db  movzx   ecx, word ptr [r8+rax+1D0h]
0x1800241e4  jmp     short loc_1800241EA
0x1800241e6  movzx   ecx, word ptr [rdi+1Ch]
0x1800241ea  movzx   eax, cx
0x1800241ed  inc     edx
0x1800241ef  shl     eax, 5
0x1800241f2  add     r8, 108h
0x1800241f9  add     r10d, eax
0x1800241fc  sub     r9, 1
0x180024200  jnz     short loc_1800241D2
0x180024202  lea     rsi, [rbp+9]
0x180024206  lea     rcx, [rbp+58h]; this
0x18002420a  movsxd  rdx, r10d; unsigned __int64
0x18002420d  mov     [rsp+88h+var_60], rcx
0x180024212  call    ?malloc@libraw_memmgr@@QEAAPEAX_K@Z; libraw_memmgr::malloc(unsigned __int64)
0x180024217  mov     [r15], rax
0x18002421a  mov     r8, rax
0x18002421d  test    rax, rax
0x180024220  jz      loc_18002453F
0x180024226  mov     r10, r12
0x180024229  xor     r12d, r12d
0x18002422c  add     r10, [rbp+18h]
0x180024230  test    rbx, rbx
0x180024233  jz      short loc_180024270
0x180024235  mov     r9d, r12d
0x180024238  lea     rdx, [r13+30h]
0x18002423c  nop     dword ptr [rax+00h]
0x180024240  movsxd  rax, dword ptr [rdx]
0x180024243  inc     r9
0x180024246  mov     rcx, [rdx+10h]
0x18002424a  mov     [rdx-20h], r8
0x18002424e  lea     rdx, [rdx+58h]
0x180024252  add     rcx, r10
0x180024255  add     r8, rax
0x180024258  mov     [rdx-80h], rcx
0x18002425c  cmp     r9, rbx
0x18002425f  jl      short loc_180024240
0x180024261  lea     r9, [rbp+58h]
0x180024265  mov     [rsp+88h+var_60], r9
0x18002426a  lea     rsi, [rbp+9]
0x18002426e  jmp     short loc_180024275
0x180024270  mov     r9, [rsp+88h+var_60]
0x180024275  cmp     byte ptr [rbp+9], 0
0x180024279  jz      loc_18002438A
0x18002427f  movsxd  rbx, [rsp+88h+arg_8]
0x180024287  mov     r11d, r12d
0x18002428a  add     rbx, [r15]
0x18002428d  movsxd  rdx, r14d
0x180024290  add     rdx, [r15]
0x180024293  mov     [r15+10h], rdx
0x180024297  mov     rax, [r13+10h]
0x18002429b  mov     [rsp+88h+var_60], r9
0x1800242a0  mov     [rdx], rax
0x1800242a3  movzx   ecx, byte ptr [rsi]
0x1800242a6  test    cl, cl
0x1800242a8  jz      loc_18002438A
0x1800242ae  lea     r9, [rdx+66h]
0x1800242b2  mov     r14, r13
0x1800242b5  lea     r10, [r13+1D0h]
0x1800242bc  nop     dword ptr [rax+00h]
0x1800242c0  movzx   eax, cl
0x1800242c3  mov     rdx, r9
0x1800242c6  dec     eax
0x1800242c8  cmp     r11d, eax
0x1800242cb  jl      short loc_1800242D7
0x1800242cd  movzx   ecx, word ptr [rdi+1Eh]
0x1800242d1  lea     rax, [rdi+1Ch]
0x1800242d5  jmp     short loc_1800242DF
0x1800242d7  movzx   ecx, word ptr [r10-56h]
0x1800242dc  mov     rax, r10
0x1800242df  mov     [rdx], cx
0x1800242e2  inc     r11d
0x1800242e5  movzx   eax, word ptr [rax]
0x1800242e8  mov     [r9+2], ax
0x1800242ed  mov     [r9-46h], rbx
0x1800242f1  lea     r8, ds:0[rax*4]
0x1800242f9  lea     rax, [r8+rbx]
0x1800242fd  mov     [r9-3Eh], rax
0x180024301  lea     rcx, [rax+r8]
0x180024305  mov     [r9-36h], rcx
0x180024309  lea     rax, [rcx+r8]
0x18002430d  mov     [r9-2Eh], rax
0x180024311  lea     rcx, [rax+r8]
0x180024315  mov     [r9-26h], rcx
0x180024319  lea     rax, [rcx+r8]
0x18002431d  mov     [r9-1Eh], rax
0x180024321  lea     rcx, [rax+r8]
0x180024325  mov     [r9-16h], rcx
0x180024329  lea     rdx, [rcx+r8]
0x18002432d  mov     [r9-0Eh], rdx
0x180024331  lea     rbx, [rdx+r8]
0x180024335  mov     dword ptr [r9-6], 0
0x18002433d  mov     byte ptr [r9-2], 0
0x180024342  mov     rax, [r14+68h]
0x180024346  add     r14, 108h
0x18002434d  mov     [r9-5Eh], rax
0x180024351  mov     rax, [r10-110h]
0x180024358  mov     [r9-56h], rax
0x18002435c  mov     rax, [r10-0B8h]
0x180024363  add     r10, 108h
0x18002436a  mov     [r9-4Eh], rax
0x18002436e  add     r9, 70h ; 'p'
0x180024372  movzx   eax, byte ptr [rsi]
0x180024375  movzx   ecx, al
0x180024378  cmp     r11d, eax
0x18002437b  jl      loc_1800242C0
0x180024381  lea     r9, [rbp+58h]
0x180024385  mov     [rsp+88h+var_60], r9
0x18002438a  cmp     [rsp+88h+var_68], 0
0x18002438f  jbe     loc_18002453B
0x180024395  mov     rax, [rsp+88h+var_50]
0x18002439a  mov     rdi, r12
0x18002439d  nop     dword ptr [rax]
0x1800243a0  imul    rbx, rdi, 58h ; 'X'
0x1800243a4  mov     r14, [rbx+r13+38h]
0x1800243a9  test    r14, r14
0x1800243ac  jz      loc_18002452F
0x1800243b2  xor     sil, sil
0x1800243b5  mov     ebp, r12d
0x1800243b8  cmp     [r15+2Ch], sil
0x1800243bc  jz      short loc_1800243CA
0x1800243be  test    rdi, rdi
0x1800243c1  jnz     short loc_1800243CA
0x1800243c3  mov     ebp, [r15+30h]
0x1800243c7  mov     sil, 1
0x1800243ca  movzx   edx, word ptr [rbx+r13+18h]
0x1800243d0  mov     ecx, r12d
0x1800243d3  movzx   eax, word ptr [rbx+r13+1Ah]
0x1800243d9  test    sil, sil
0x1800243dc  mov     word ptr [rsp+88h+arg_8], ax
0x1800243e4  mov     rax, [rbx+r13+8]
0x1800243e9  mov     [rsp+88h+var_48], rax
0x1800243ee  lea     eax, ds:0[rdx*4]
0x1800243f5  cmovz   ecx, eax
0x1800243f8  mov     [rsp+88h+var_68], edx
0x1800243fc  lea     eax, ds:4[rdx*2]
0x180024403  mov     r12d, ecx
0x180024406  lea     r8, [rax+401Ch]
0x18002440d  mov     r13d, eax
0x180024410  mov     edx, 1; unsigned __int64
0x180024415  lea     r8, [rcx+r8*4]; unsigned __int64
0x180024419  mov     rcx, r9; this
0x18002441c  call    ?calloc@libraw_memmgr@@QEAAPEAX_K0@Z; libraw_memmgr::calloc(unsigned __int64,unsigned __int64)
0x180024421  test    rax, rax
0x180024424  jz      loc_18002453F
0x18002442a  mov     rdx, [rsp+88h+var_58]
0x18002442f  lea     rcx, [rax+10070h]
0x180024436  mov     [rbx+rdx], rax
0x18002443a  mov     [rax+10058h], rcx
0x180024441  test    r12d, r12d
0x180024444  jz      short loc_18002445A
0x180024446  mov     rax, [rbx+rdx]
0x18002444a  xor     r12d, r12d
0x18002444d  mov     rcx, [rax+10058h]
0x180024454  lea     rdx, [rcx+r13*4]
0x180024458  jmp     short loc_180024460
0x18002445a  xor     r12d, r12d
0x18002445d  mov     edx, r12d
0x180024460  mov     r13, [rsp+88h+var_58]
0x180024465  mov     ecx, [rsp+88h+var_68]
0x180024469  mov     rax, [rbx+r13]
0x18002446d  mov     [rax+10060h], rdx
0x180024474  mov     rax, [rbx+r13]
0x180024478  mov     [rax+10028h], cx
0x18002447f  mov     rax, [rbx+r13]
0x180024483  movzx   ecx, word ptr [rsp+88h+arg_8]
0x18002448b  mov     [rax+1002Ah], cx
0x180024492  mov     rax, [rbx+r13]
0x180024496  mov     rcx, [rsp+88h+var_48]
0x18002449b  mov     [rax+10030h], r12d
0x1800244a2  mov     rax, [rbx+r13]
0x1800244a6  mov     [rax+10034h], r12w
0x1800244ae  mov     rax, [rbx+r13]
0x1800244b2  mov     [rax+1002Ch], ebp
0x1800244b8  mov     rax, [rbx+r13]
0x1800244bc  mov     [rax+10068h], sil
0x1800244c3  mov     rax, [rbx+r13]
0x1800244c7  mov     [rax+10018h], r12d
0x1800244ce  mov     rax, [rbx+r13]
0x1800244d2  mov     [rax+1001Ch], r12d
0x1800244d9  mov     rax, [rbx+r13]
0x1800244dd  mov     [rax+10000h], r14
0x1800244e4  mov     rax, [rbx+r13]
0x1800244e8  mov     [rax+10010h], r12d
0x1800244ef  mov     rax, [rbx+r13]
0x1800244f3  mov     [rax+10014h], r12d
0x1800244fa  mov     rax, [rbx+r13]
0x1800244fe  mov     [rax+10008h], rcx
0x180024505  mov     rcx, [rbx+r13]
0x180024509  mov     rax, [rsp+88h+arg_0]
0x180024511  mov     rax, [rax+50h]
0x180024515  mov     [rcx+10020h], rax
0x18002451c  mov     rcx, [rbx+r13]
0x180024520  call    crxFillBuffer
0x180024525  mov     rax, [rsp+88h+var_50]
0x18002452a  mov     r9, [rsp+88h+var_60]
0x18002452f  inc     rdi
0x180024532  cmp     rdi, rax
0x180024535  jl      loc_1800243A0
0x18002453b  xor     eax, eax
0x18002453d  jmp     short loc_180024544
0x18002453f  mov     eax, 0FFFFFFFFh
0x180024544  mov     rbx, [rsp+88h+arg_10]
0x18002454c  add     rsp, 50h
0x180024550  pop     r15
0x180024552  pop     r14
0x180024554  pop     r13
0x180024556  pop     r12
0x180024558  pop     rdi
0x180024559  pop     rsi
0x18002455a  pop     rbp
0x18002455b  retn
```
