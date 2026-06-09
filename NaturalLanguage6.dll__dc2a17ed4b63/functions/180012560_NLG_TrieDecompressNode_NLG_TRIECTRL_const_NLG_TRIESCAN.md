# NLG::TrieDecompressNode(NLG::TRIECTRL const *,NLG::TRIESCAN *)

- ea: `0x180012560`
- end: `0x180012d3c`
- name: `?TrieDecompressNode@NLG@@YAXPEBUTRIECTRL@1@PEAUTRIESCAN@1@@Z`
- size: `2012`
- prototype: `void __fastcall(NLG *__hidden this, const struct NLG::TRIECTRL *, struct NLG::TRIESCAN *)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011de0`
- `0x180011e50`
- `0x180011e90`
- `0x180011fe0`
- `0x180012030`
- `0x1800122b0`
- `0x18006f40c`

## callees

- `0x180012560`
- `0x180014030`
- `0x1800b0010`

## pseudocode

```c
void __fastcall NLG::TrieDecompressNode(NLG *this, const struct NLG::TRIECTRL *a2, struct NLG::TRIESCAN *a3)
{
  __int64 (__fastcall *v3)(unsigned __int64, _QWORD, struct NLG::TRIESCAN *); // rax
  unsigned int v6; // r12d
  unsigned __int8 *v7; // rdx
  int v8; // r15d
  __int64 v9; // r9
  __int16 v10; // r8
  int v11; // r10d
  unsigned __int16 v12; // cx
  __int16 v13; // ax
  unsigned __int8 *v14; // r11
  __int16 v15; // cx
  __int16 v16; // ax
  __int64 v17; // rcx
  unsigned __int8 *v18; // r10
  __int64 v19; // rax
  __int16 v20; // r8
  unsigned int v21; // r8d
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  unsigned int v26; // r8d
  unsigned int v27; // r8d
  __int16 v28; // si
  unsigned __int8 *v29; // r8
  __int16 v30; // cx
  unsigned __int16 *v31; // r9
  unsigned __int16 v32; // dx
  unsigned __int16 v33; // ax
  unsigned __int8 *v34; // r10
  unsigned __int8 *v35; // rax
  unsigned __int16 v36; // cx
  unsigned __int8 *v37; // rdx
  unsigned __int64 v38; // r8
  unsigned __int64 v39; // rcx
  __int64 v40; // rax
  char *v41; // rax
  char v42; // r8
  int i; // r10d
  unsigned __int8 *v44; // rcx
  __int16 v45; // si
  unsigned __int16 *v46; // r11
  int v47; // r14d
  unsigned __int16 v48; // dx
  unsigned __int16 v49; // ax
  unsigned __int8 *v50; // rbp
  __int16 v51; // dx
  __int16 v52; // ax
  __int64 v53; // rax
  char v54; // al
  unsigned __int8 *v55; // rdx
  __int16 v56; // r9
  unsigned __int16 *v57; // r8
  unsigned __int16 v58; // cx
  unsigned __int16 v59; // ax
  unsigned __int8 *v60; // r10
  unsigned __int8 *v61; // rdx
  char v62; // cl
  unsigned __int8 v63; // dl
  int v64; // ecx
  int v65; // eax
  char v66; // cl
  int v67; // edx
  int v68; // ecx
  unsigned __int8 *v69; // rax
  char v70; // cl
  int v71; // edx
  int v72; // ecx
  unsigned __int8 *v73; // rax
  char v74; // cl
  int v75; // edx
  int v76; // ecx
  unsigned __int8 *v77; // rax
  char v78; // cl
  int v79; // edx
  int v80; // ecx
  unsigned __int8 *v81; // rax
  char v82; // cl
  int v83; // edx
  int v84; // ecx
  const unsigned __int16 *v85; // rbp
  unsigned __int16 v86; // [rsp+50h] [rbp+8h] BYREF

  v3 = (__int64 (__fastcall *)(unsigned __int64, _QWORD, struct NLG::TRIESCAN *))*((_QWORD *)this + 10);
  if ( v3 )
  {
    v39 = *((_QWORD *)a2 + 2);
    if ( v39 < *((_QWORD *)this + 11) )
    {
      v40 = v3(v39, *((_QWORD *)this + 12), a3);
      if ( v40 )
      {
        *(_OWORD *)a2 = *(_OWORD *)v40;
        *((_OWORD *)a2 + 1) = *(_OWORD *)(v40 + 16);
        *((_OWORD *)a2 + 2) = *(_OWORD *)(v40 + 32);
        *((_OWORD *)a2 + 3) = *(_OWORD *)(v40 + 48);
        *((_OWORD *)a2 + 4) = *(_OWORD *)(v40 + 64);
        *((_QWORD *)a2 + 10) = *(_QWORD *)(v40 + 80);
        return;
      }
    }
  }
  v6 = 0;
  if ( !*((_WORD *)a2 + 1) )
  {
    *((_QWORD *)a2 + 5) = 0;
    *((_QWORD *)a2 + 2) = *((_QWORD *)this + 9);
  }
  v7 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
  v8 = 1;
  v9 = *((_QWORD *)this + 1);
  v10 = 0;
  v11 = 1;
  v12 = *v7;
  v13 = *(_WORD *)v9;
  if ( v12 >= *(_WORD *)v9 )
  {
    v14 = v7 + 1;
    do
    {
      v9 += 2;
      v10 += v13;
      v15 = v12 - v13;
      v16 = *v14++;
      ++v11;
      v12 = v16 + (v15 << 8);
      v13 = *(_WORD *)v9;
    }
    while ( v12 >= *(_WORD *)v9 );
  }
  v17 = (unsigned __int16)(v12 + v10);
  v18 = &v7[v11];
  *((_QWORD *)a2 + 2) = v18;
  v19 = *((_QWORD *)this + 5);
  v86 = v17;
  *(_WORD *)a2 = *(_WORD *)(4 * v17 + v19);
  v20 = *(_WORD *)(4 * v17 + *((_QWORD *)this + 5) + 2);
  *((_WORD *)a2 + 1) = v20;
  if ( (v20 & 0x400) != 0 )
  {
    v9 = *v18++;
    *((_QWORD *)a2 + 2) = v18;
    if ( (unsigned int)v9 < 0xC0 )
    {
      if ( (unsigned int)v9 < 0x80 )
      {
LABEL_70:
        *((_DWORD *)a2 + 3) = v9;
        goto LABEL_8;
      }
      v65 = *v18++;
      v9 = v65 | ((unsigned __int8)(v9 & 0x7F) << 8);
    }
    else
    {
      v63 = *v18;
      *((_QWORD *)a2 + 2) = v18 + 1;
      v64 = v18[1];
      v18 += 2;
      v9 = v64 | ((v63 & 0x7F | ((unsigned __int8)(v9 & 0x3F) << 7)) << 8);
    }
    *((_QWORD *)a2 + 2) = v18;
    goto LABEL_70;
  }
LABEL_8:
  if ( (v20 & 4) != 0 )
  {
    v21 = *v18;
    v9 = (__int64)(v18 + 1);
    *((_QWORD *)a2 + 2) = v18 + 1;
    if ( v21 >= 0xC0 )
    {
      v62 = *(_BYTE *)v9;
      *((_QWORD *)a2 + 2) = v18 + 2;
      v9 = (__int64)(v18 + 3);
      v21 = v18[2] | ((v62 & 0x7F | ((v21 & 0x3F) << 7)) << 8);
    }
    else
    {
      if ( v21 < 0x80 )
      {
LABEL_13:
        *((_DWORD *)a2 + 2) = v21;
        if ( (*(_BYTE *)(*(_QWORD *)this + 5LL) & 1) != 0 )
        {
          v23 = *(unsigned __int8 *)v9++;
          *((_QWORD *)a2 + 2) = v9;
          if ( v23 < 0xC0 )
          {
            if ( v23 >= 0x80 )
            {
              v68 = *(unsigned __int8 *)v9;
              *((_QWORD *)a2 + 2) = v9 + 1;
              v23 = v68 | ((v23 & 0x7F) << 8);
            }
          }
          else
          {
            v66 = *(_BYTE *)v9;
            *((_QWORD *)a2 + 2) = v9 + 1;
            v67 = *(unsigned __int8 *)(v9 + 1);
            *((_QWORD *)a2 + 2) = v9 + 2;
            v23 = v67 | ((v66 & 0x7F | ((v23 & 0x3F) << 7)) << 8);
          }
        }
        else
        {
          v23 = 0;
        }
        *((_DWORD *)a2 + 12) = v23;
        if ( (*(_BYTE *)(*(_QWORD *)this + 5LL) & 2) != 0 )
        {
          v69 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
          v24 = *v69;
          v9 = (__int64)(v69 + 1);
          *((_QWORD *)a2 + 2) = v69 + 1;
          if ( v24 < 0xC0 )
          {
            if ( v24 >= 0x80 )
            {
              v72 = *(unsigned __int8 *)v9;
              *((_QWORD *)a2 + 2) = v69 + 2;
              v24 = v72 | ((v24 & 0x7F) << 8);
            }
          }
          else
          {
            v70 = *(_BYTE *)v9;
            *((_QWORD *)a2 + 2) = v69 + 2;
            v71 = v69[2];
            *((_QWORD *)a2 + 2) = v69 + 3;
            v24 = v71 | ((v70 & 0x7F | ((v24 & 0x3F) << 7)) << 8);
          }
        }
        else
        {
          v24 = 0;
        }
        *((_DWORD *)a2 + 14) = v24;
        if ( (*(_BYTE *)(*(_QWORD *)this + 5LL) & 4) != 0 )
        {
          v73 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
          v25 = *v73;
          v9 = (__int64)(v73 + 1);
          *((_QWORD *)a2 + 2) = v73 + 1;
          if ( v25 < 0xC0 )
          {
            if ( v25 >= 0x80 )
            {
              v76 = *(unsigned __int8 *)v9;
              *((_QWORD *)a2 + 2) = v73 + 2;
              v25 = v76 | ((v25 & 0x7F) << 8);
            }
          }
          else
          {
            v74 = *(_BYTE *)v9;
            *((_QWORD *)a2 + 2) = v73 + 2;
            v75 = v73[2];
            *((_QWORD *)a2 + 2) = v73 + 3;
            v25 = v75 | ((v74 & 0x7F | ((v25 & 0x3F) << 7)) << 8);
          }
        }
        else
        {
          v25 = 0;
        }
        *((_DWORD *)a2 + 16) = v25;
        if ( (*(_BYTE *)(*(_QWORD *)this + 5LL) & 8) != 0 )
        {
          v77 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
          v26 = *v77;
          v9 = (__int64)(v77 + 1);
          *((_QWORD *)a2 + 2) = v77 + 1;
          if ( v26 < 0xC0 )
          {
            if ( v26 >= 0x80 )
            {
              v80 = *(unsigned __int8 *)v9;
              *((_QWORD *)a2 + 2) = v77 + 2;
              v26 = v80 | ((v26 & 0x7F) << 8);
            }
          }
          else
          {
            v78 = *(_BYTE *)v9;
            *((_QWORD *)a2 + 2) = v77 + 2;
            v79 = v77[2];
            *((_QWORD *)a2 + 2) = v77 + 3;
            v26 = v79 | ((v78 & 0x7F | ((v26 & 0x3F) << 7)) << 8);
          }
        }
        else
        {
          v26 = 0;
        }
        *((_DWORD *)a2 + 18) = v26;
        if ( (*(_BYTE *)(*(_QWORD *)this + 5LL) & 0x10) != 0 )
        {
          v81 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
          v27 = *v81;
          v9 = (__int64)(v81 + 1);
          *((_QWORD *)a2 + 2) = v81 + 1;
          if ( v27 < 0xC0 )
          {
            if ( v27 >= 0x80 )
            {
              v84 = *(unsigned __int8 *)v9;
              *((_QWORD *)a2 + 2) = v81 + 2;
              v27 = v84 | ((v27 & 0x7F) << 8);
            }
          }
          else
          {
            v82 = *(_BYTE *)v9;
            *((_QWORD *)a2 + 2) = v81 + 2;
            v83 = v81[2];
            *((_QWORD *)a2 + 2) = v81 + 3;
            v27 = v83 | ((v82 & 0x7F | ((v27 & 0x3F) << 7)) << 8);
          }
        }
        else
        {
          v27 = 0;
        }
        *((_DWORD *)a2 + 20) = v27;
        v20 = *((_WORD *)a2 + 1);
        goto LABEL_24;
      }
      v22 = *(unsigned __int8 *)v9;
      v9 = (__int64)(v18 + 2);
      v21 = v22 | ((v21 & 0x7F) << 8);
    }
    *((_QWORD *)a2 + 2) = v9;
    goto LABEL_13;
  }
  *((_DWORD *)a2 + 2) = 0;
LABEL_24:
  *((_WORD *)a2 + 2) = 0;
  if ( (v20 & 8) != 0 )
  {
    if ( *(_BYTE *)(*(_QWORD *)this + 7LL) == 1 )
    {
      v42 = *(_BYTE *)(*(_QWORD *)this + 6LL);
    }
    else
    {
      v41 = (char *)*((_QWORD *)a2 + 2);
      v42 = *v41;
      *((_QWORD *)a2 + 2) = v41 + 1;
    }
    v9 = 1;
    for ( i = 0; v42; v42 &= v54 )
    {
      if ( i >= 5 )
        break;
      if ( ((unsigned __int8)(v42 & *(_BYTE *)(*(_QWORD *)this + 6LL)) & (unsigned __int8)v9) != 0 )
      {
        v44 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
        v45 = 0;
        v46 = (unsigned __int16 *)*((_QWORD *)this + 2);
        v47 = 1;
        v48 = *v44;
        v49 = *v46;
        if ( v48 >= *v46 )
        {
          v50 = v44 + 1;
          do
          {
            ++v46;
            v45 += v49;
            v51 = v48 - v49;
            v52 = *v50++;
            ++v47;
            v48 = v52 + (v51 << 8);
            v49 = *v46;
          }
          while ( v48 >= *v46 );
        }
        *((_QWORD *)a2 + 2) = &v44[v47];
        v53 = *((_QWORD *)this + 6);
        v86 = v48 + v45;
        *((_DWORD *)a2 + 2 * i + 13) = *(_DWORD *)(v53 + 4LL * (unsigned __int16)(v48 + v45));
        *((_WORD *)a2 + 2) |= (unsigned __int8)v9;
      }
      ++i;
      v54 = ~(_BYTE)v9;
      LOBYTE(v9) = 2 * v9;
    }
  }
  v28 = *((_WORD *)a2 + 1);
  if ( (v28 & 0x20) != 0 )
  {
    v85 = (const unsigned __int16 *)*((_QWORD *)a2 + 2);
    if ( (v28 & 0x200) != 0 )
    {
      *((_QWORD *)a2 + 2) = (char *)v85
                          + (int)NLG::DecompressSymbol(
                                   (NLG *)&v86,
                                   *((unsigned __int16 **)this + 4),
                                   v85,
                                   (const unsigned __int8 *)v9);
      v6 = *(_DWORD *)(*((_QWORD *)this + 8) + 4LL * v86);
    }
    else
    {
      *((_QWORD *)a2 + 2) = (char *)v85
                          + (int)NLG::DecompressSymbol(
                                   (NLG *)&v86,
                                   *((unsigned __int16 **)this + 3),
                                   v85,
                                   (const unsigned __int8 *)v9);
      *((_QWORD *)a2 + 4) = *((_QWORD *)this + 9) + *(unsigned int *)(*((_QWORD *)this + 7) + 4LL * v86);
    }
  }
  else
  {
    *((_QWORD *)a2 + 4) = 0;
  }
  if ( (v28 & 0x100) != 0 )
  {
    v61 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
    v38 = *((_QWORD *)this + 9) + (v61[2] | ((((unsigned __int64)*v61 << 8) | v61[1]) << 8));
    *((_QWORD *)a2 + 2) = v61 + 3;
  }
  else if ( (v28 & 0x40) != 0 )
  {
    v38 = *((_QWORD *)a2 + 2);
    *((_QWORD *)a2 + 5) = v38;
  }
  else if ( (v28 & 0x80u) != 0 )
  {
    v55 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
    v56 = 0;
    v57 = (unsigned __int16 *)*((_QWORD *)this + 3);
    v58 = *v55;
    v59 = *v57;
    if ( v58 >= *v57 )
    {
      v60 = v55 + 1;
      do
      {
        ++v57;
        v56 += v59;
        ++v60;
        ++v8;
        v58 = *(v60 - 1) + ((v58 - v59) << 8);
        v59 = *v57;
      }
      while ( v58 >= *v57 );
    }
    *((_QWORD *)a2 + 2) = &v55[v8];
    v38 = *((_QWORD *)this + 9) + *(unsigned int *)(*((_QWORD *)this + 7) + 4LL * (unsigned __int16)(v58 + v56));
  }
  else if ( (v28 & 0x10) != 0 )
  {
    v29 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
    v30 = 0;
    v31 = (unsigned __int16 *)*((_QWORD *)this + 4);
    v32 = *v29;
    v33 = *v31;
    if ( v32 >= *v31 )
    {
      v34 = v29 + 1;
      do
      {
        ++v31;
        v30 += v33;
        ++v34;
        ++v8;
        v32 = *(v34 - 1) + ((v32 - v33) << 8);
        v33 = *v31;
      }
      while ( v32 >= *v31 );
    }
    v35 = (unsigned __int8 *)*((_QWORD *)a2 + 5);
    v36 = v32 + v30;
    v37 = &v29[v8];
    *((_QWORD *)a2 + 2) = v37;
    if ( v35 )
      v37 = v35;
    else
      *((_QWORD *)a2 + 5) = v37;
    v38 = (unsigned __int64)&v37[*(unsigned int *)(*((_QWORD *)this + 8) + 4LL * v36)];
    *((_QWORD *)a2 + 5) = v38;
  }
  else
  {
    v38 = 0;
  }
  *((_QWORD *)a2 + 3) = v38;
  if ( (v28 & 0x220) == 0x220 )
    *((_QWORD *)a2 + 4) = *((_QWORD *)a2 + 2) + v6;
}

```

## disassembly

```asm
0x180012560  push    rbx
0x180012562  push    rdi
0x180012563  sub     rsp, 38h
0x180012567  mov     rax, [rcx+50h]
0x18001256b  mov     rbx, rdx
0x18001256e  mov     rdi, rcx
0x180012571  test    rax, rax
0x180012574  jnz     loc_1800127EA
0x18001257a  mov     [rsp+48h+arg_10], rsi
0x18001257f  mov     [rsp+48h+arg_18], r12
0x180012584  mov     [rsp+48h+var_18], r13
0x180012589  xor     r13d, r13d
0x18001258c  mov     r12d, r13d
0x18001258f  mov     [rsp+48h+var_20], r14
0x180012594  mov     [rsp+48h+var_28], r15
0x180012599  cmp     [rbx+2], r12w
0x18001259e  jz      loc_180012A17
0x1800125a4  mov     rdx, [rbx+10h]
0x1800125a8  mov     r15d, 1
0x1800125ae  mov     r9, [rdi+8]
0x1800125b2  mov     r8d, r13d
0x1800125b5  mov     r10d, r15d
0x1800125b8  mov     r14d, 100h
0x1800125be  movzx   ecx, byte ptr [rdx]
0x1800125c1  movzx   eax, word ptr [r9]
0x1800125c5  cmp     cx, ax
0x1800125c8  jb      short loc_1800125F7
0x1800125ca  lea     r11, [rdx+1]
0x1800125ce  sub     cx, ax
0x1800125d1  lea     r9, [r9+2]
0x1800125d5  add     r8w, ax
0x1800125d9  movzx   ecx, cx
0x1800125dc  movzx   eax, byte ptr [r11]
0x1800125e0  lea     r11, [r11+1]
0x1800125e4  imul    ecx, r14d
0x1800125e8  inc     r10d
0x1800125eb  add     cx, ax
0x1800125ee  movzx   eax, word ptr [r9]
0x1800125f2  cmp     cx, ax
0x1800125f5  jnb     short loc_1800125CE
0x1800125f7  add     r8w, cx
0x1800125fb  movsxd  r10, r10d
0x1800125fe  movzx   ecx, r8w
0x180012602  add     r10, rdx
0x180012605  mov     [rbx+10h], r10
0x180012609  mov     rax, [rdi+28h]
0x18001260d  mov     [rsp+48h+arg_0], cx
0x180012612  lea     rdx, ds:0[rcx*4]
0x18001261a  movzx   ecx, word ptr [rdx+rax]
0x18001261e  mov     [rbx], cx
0x180012621  mov     rax, [rdi+28h]
0x180012625  movzx   r8d, word ptr [rdx+rax+2]
0x18001262b  bt      r8w, 0Ah
0x180012631  mov     [rbx+2], r8w
0x180012636  jb      loc_180012A28
0x18001263c  test    r8b, 4
0x180012640  jz      loc_180012920
0x180012646  movzx   r8d, byte ptr [r10]
0x18001264a  lea     r9, [r10+1]
0x18001264e  mov     [rbx+10h], r9
0x180012652  cmp     r8d, 0C0h
0x180012659  jnb     loc_1800129EA
0x18001265f  cmp     r8d, 80h
0x180012666  jb      short loc_18001267E
0x180012668  movzx   eax, byte ptr [r9]
0x18001266c  and     r8d, 7Fh
0x180012670  shl     r8d, 8
0x180012674  inc     r9; unsigned __int8 *
0x180012677  or      r8d, eax
0x18001267a  mov     [rbx+10h], r9
0x18001267e  mov     [rbx+8], r8d
0x180012682  mov     rax, [rdi]
0x180012685  test    [rax+5], r15b
0x180012689  jnz     loc_180012A8E
0x18001268f  mov     r8d, r13d
0x180012692  mov     [rbx+30h], r8d
0x180012696  mov     rax, [rdi]
0x180012699  test    byte ptr [rax+5], 2
0x18001269d  jnz     loc_180012AFC
0x1800126a3  mov     r8d, r13d
0x1800126a6  mov     [rbx+38h], r8d
0x1800126aa  mov     rax, [rdi]
0x1800126ad  test    byte ptr [rax+5], 4
0x1800126b1  jnz     loc_180012B6F
0x1800126b7  mov     r8d, r13d
0x1800126ba  mov     [rbx+40h], r8d
0x1800126be  mov     rax, [rdi]
0x1800126c1  test    byte ptr [rax+5], 8
0x1800126c5  jnz     loc_180012BE2
0x1800126cb  mov     r8d, r13d
0x1800126ce  mov     [rbx+48h], r8d
0x1800126d2  mov     rax, [rdi]
0x1800126d5  test    byte ptr [rax+5], 10h
0x1800126d9  jnz     loc_180012C55
0x1800126df  mov     r8d, r13d
0x1800126e2  mov     [rbx+50h], r8d
0x1800126e6  movzx   r8d, word ptr [rbx+2]
0x1800126eb  mov     [rsp+48h+arg_8], rbp
0x1800126f0  mov     [rbx+4], r13w
0x1800126f5  test    r8b, 8
0x1800126f9  jnz     loc_180012841
0x1800126ff  movzx   esi, word ptr [rbx+2]
0x180012703  test    sil, 20h
0x180012707  jnz     loc_180012CC8
0x18001270d  mov     [rbx+20h], r13
0x180012711  mov     rbp, [rsp+48h+arg_8]
0x180012716  test    r14w, si
0x18001271a  jnz     loc_18001299C
0x180012720  test    sil, 40h
0x180012724  jnz     loc_1800129D3
0x18001272a  test    sil, sil
0x18001272d  js      loc_180012931
0x180012733  test    sil, 10h
0x180012737  jz      loc_1800129CB
0x18001273d  mov     r8, [rbx+10h]
0x180012741  mov     ecx, r13d
0x180012744  mov     r9, [rdi+20h]
0x180012748  movzx   edx, byte ptr [r8]
0x18001274c  movzx   eax, word ptr [r9]
0x180012750  cmp     dx, ax
0x180012753  jb      short loc_180012785
0x180012755  lea     r10, [r8+1]
0x180012759  sub     dx, ax
0x18001275c  lea     r9, [r9+2]
0x180012760  add     cx, ax
0x180012763  movzx   edx, dx
0x180012766  movzx   eax, r14w
0x18001276a  lea     r10, [r10+1]
0x18001276e  imul    edx, eax
0x180012771  inc     r15d
0x180012774  movzx   eax, byte ptr [r10-1]
0x180012779  add     dx, ax
0x18001277c  movzx   eax, word ptr [r9]
0x180012780  cmp     dx, ax
0x180012783  jnb     short loc_180012759
0x180012785  mov     rax, [rbx+28h]
0x180012789  add     cx, dx
0x18001278c  movsxd  rdx, r15d
0x18001278f  add     rdx, r8
0x180012792  mov     [rbx+10h], rdx
0x180012796  test    rax, rax
0x180012799  jnz     loc_180012929
0x18001279f  mov     [rbx+28h], rdx
0x1800127a3  mov     rax, [rdi+40h]
0x1800127a7  movzx   ecx, cx
0x1800127aa  mov     r8d, [rax+rcx*4]
0x1800127ae  add     r8, rdx
0x1800127b1  mov     [rbx+28h], r8
0x1800127b5  mov     [rbx+18h], r8
0x1800127b9  mov     eax, 220h
0x1800127be  mov     r15, [rsp+48h+var_28]
0x1800127c3  and     si, ax
0x1800127c6  mov     r14, [rsp+48h+var_20]
0x1800127cb  cmp     si, ax
0x1800127ce  mov     rsi, [rsp+48h+arg_10]
0x1800127d3  mov     r13, [rsp+48h+var_18]
0x1800127d8  jz      loc_180012D2C
0x1800127de  mov     r12, [rsp+48h+arg_18]
0x1800127e3  add     rsp, 38h
0x1800127e7  pop     rdi
0x1800127e8  pop     rbx
0x1800127e9  retn
0x1800127ea  mov     rcx, [rdx+10h]
0x1800127ee  cmp     rcx, [rdi+58h]
0x1800127f2  jnb     loc_18001257A
0x1800127f8  mov     rdx, [rdi+60h]
0x1800127fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012801  test    rax, rax
0x180012804  jz      loc_18001257A
0x18001280a  movups  xmm0, xmmword ptr [rax]
0x18001280d  movups  xmmword ptr [rbx], xmm0
0x180012810  movups  xmm1, xmmword ptr [rax+10h]
0x180012814  movups  xmmword ptr [rbx+10h], xmm1
0x180012818  movups  xmm0, xmmword ptr [rax+20h]
0x18001281c  movups  xmmword ptr [rbx+20h], xmm0
0x180012820  movups  xmm1, xmmword ptr [rax+30h]
0x180012824  movups  xmmword ptr [rbx+30h], xmm1
0x180012828  movups  xmm0, xmmword ptr [rax+40h]
0x18001282c  movups  xmmword ptr [rbx+40h], xmm0
0x180012830  movsd   xmm1, qword ptr [rax+50h]
0x180012835  movsd   qword ptr [rbx+50h], xmm1
0x18001283a  add     rsp, 38h
0x18001283e  pop     rdi
0x18001283f  pop     rbx
0x180012840  retn
0x180012841  mov     r8, [rdi]
0x180012844  cmp     [r8+7], r15b
0x180012848  jz      loc_1800129E0
0x18001284e  mov     rax, [rbx+10h]
0x180012852  movzx   r8d, byte ptr [rax]
0x180012856  inc     rax
0x180012859  mov     [rbx+10h], rax
0x18001285d  movzx   r9d, r15b
0x180012861  mov     r10d, r13d
0x180012864  test    r8b, r8b
0x180012867  jz      loc_1800126FF
0x18001286d  cmp     r10d, 5
0x180012871  jge     loc_180012915
0x180012877  mov     rax, [rdi]
0x18001287a  movzx   ecx, byte ptr [rax+6]
0x18001287e  and     cl, r8b
0x180012881  test    r9b, cl
0x180012884  jz      short loc_180012900
0x180012886  mov     rcx, [rbx+10h]
0x18001288a  mov     esi, r13d
0x18001288d  mov     r11, [rdi+10h]
0x180012891  mov     r14d, r15d
0x180012894  movzx   edx, byte ptr [rcx]
0x180012897  movzx   eax, word ptr [r11]
0x18001289b  cmp     dx, ax
0x18001289e  jb      short loc_1800128D5
0x1800128a0  lea     rbp, [rcx+1]
0x1800128a4  mov     r13d, 100h
0x1800128aa  sub     dx, ax
0x1800128ad  lea     r11, [r11+2]
0x1800128b1  add     si, ax
0x1800128b4  movzx   edx, dx
0x1800128b7  movzx   eax, byte ptr [rbp+0]
0x1800128bb  lea     rbp, [rbp+1]
0x1800128bf  imul    edx, r13d
0x1800128c3  inc     r14d
0x1800128c6  add     dx, ax
0x1800128c9  movzx   eax, word ptr [r11]
0x1800128cd  cmp     dx, ax
0x1800128d0  jnb     short loc_1800128AA
0x1800128d2  xor     r13d, r13d
0x1800128d5  add     si, dx
0x1800128d8  movsxd  rax, r14d
0x1800128db  add     rax, rcx
0x1800128de  movzx   edx, si
0x1800128e1  mov     [rbx+10h], rax
0x1800128e5  mov     rax, [rdi+30h]
0x1800128e9  movsxd  rcx, r10d
0x1800128ec  mov     [rsp+48h+arg_0], dx
0x1800128f1  mov     eax, [rax+rdx*4]
0x1800128f4  mov     [rbx+rcx*8+34h], eax
0x1800128f8  movzx   eax, r9b
0x1800128fc  or      [rbx+4], ax
0x180012900  movzx   eax, r9b
0x180012904  inc     r10d
0x180012907  not     al
0x180012909  add     r9b, r9b
0x18001290c  and     r8b, al
0x18001290f  jnz     loc_18001286D
0x180012915  mov     r14d, 100h
0x18001291b  jmp     loc_1800126FF
0x180012920  mov     [rbx+8], r13d
0x180012924  jmp     loc_1800126EB
0x180012929  mov     rdx, rax
0x18001292c  jmp     loc_1800127A3
0x180012931  mov     rdx, [rbx+10h]
0x180012935  mov     r9d, r13d
0x180012938  mov     r8, [rdi+18h]
0x18001293c  movzx   ecx, byte ptr [rdx]
0x18001293f  movzx   eax, word ptr [r8]
0x180012943  cmp     cx, ax
0x180012946  jb      short loc_180012979
0x180012948  lea     r10, [rdx+1]
0x18001294c  sub     cx, ax
0x18001294f  lea     r8, [r8+2]
0x180012953  add     r9w, ax
0x180012957  movzx   ecx, cx
0x18001295a  movzx   eax, r14w
0x18001295e  lea     r10, [r10+1]
0x180012962  imul    ecx, eax
0x180012965  inc     r15d
0x180012968  movzx   eax, byte ptr [r10-1]
0x18001296d  add     cx, ax
0x180012970  movzx   eax, word ptr [r8]
0x180012974  cmp     cx, ax
0x180012977  jnb     short loc_18001294C
0x180012979  add     r9w, cx
0x18001297d  movsxd  rax, r15d
0x180012980  add     rax, rdx
0x180012983  movzx   ecx, r9w
0x180012987  mov     [rbx+10h], rax
0x18001298b  mov     rax, [rdi+38h]
0x18001298f  mov     r8d, [rax+rcx*4]
0x180012993  add     r8, [rdi+48h]
0x180012997  jmp     loc_1800127B5
0x18001299c  mov     rdx, [rbx+10h]
0x1800129a0  movzx   eax, byte ptr [rdx]
0x1800129a3  movzx   r8d, byte ptr [rdx+1]
0x1800129a8  shl     rax, 8
0x1800129ac  or      r8, rax
0x1800129af  movzx   eax, byte ptr [rdx+2]
0x1800129b3  shl     r8, 8
0x1800129b7  or      r8, rax
0x1800129ba  lea     rax, [rdx+3]
0x1800129be  add     r8, [rdi+48h]
0x1800129c2  mov     [rbx+10h], rax
0x1800129c6  jmp     loc_1800127B5
0x1800129cb  mov     r8, r13
0x1800129ce  jmp     loc_1800127B5
0x1800129d3  mov     r8, [rbx+10h]
0x1800129d7  mov     [rbx+28h], r8
0x1800129db  jmp     loc_1800127B5
0x1800129e0  movzx   r8d, byte ptr [r8+6]
0x1800129e5  jmp     loc_18001285D
0x1800129ea  movzx   ecx, byte ptr [r9]
  ... truncated ...
```
