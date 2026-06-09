# wherePathSolver

- ea: `0x18004eae8`
- end: `0x18004f27a`
- name: `wherePathSolver`
- size: `1938`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007ac0`

## callees

- `0x180011bcc`
- `0x180012200`
- `0x180015460`
- `0x180041bf0`
- `0x18004e838`
- `0x18004eae8`
- `0x18004f280`
- `0x180078968`
- `0x1800af620`

## pseudocode

```c
__int64 __fastcall wherePathSolver(__int64 a1, unsigned __int16 a2)
{
  __int64 v2; // r15
  unsigned int v3; // r14d
  __int64 *v4; // r8
  unsigned __int16 v5; // r13
  signed int v7; // r12d
  int *v8; // rax
  int v9; // esi
  __int64 v10; // rax
  int v11; // r10d
  __int64 v12; // rdx
  __int64 v13; // r11
  __int64 v14; // rax
  __int64 v15; // r9
  char *v16; // rcx
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // r8
  __int16 v20; // ax
  int v21; // eax
  int v22; // ecx
  __int64 v23; // rsi
  unsigned int v24; // edx
  __int64 *v25; // r12
  int v26; // r8d
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rax
  char *v31; // rbx
  __int64 v32; // r13
  _DWORD *v33; // r10
  __int16 v34; // r8
  char v35; // dl
  __int64 *v36; // rbx
  __int64 v37; // r8
  char v38; // al
  __int64 v39; // rax
  __int16 v41; // r9
  unsigned __int64 v42; // rdx
  char v43; // al
  int v44; // r10d
  unsigned __int8 v45; // r11
  __int16 v46; // dx
  signed __int16 v47; // bx
  int v48; // ecx
  __int64 v49; // rsi
  __int64 v50; // r13
  int v51; // edx
  __int64 v52; // r15
  __int64 v53; // rcx
  __int64 v54; // rdx
  unsigned __int16 v55; // ax
  __int16 v56; // bx
  __int64 v57; // r10
  __int64 v58; // r11
  __int64 v59; // rbx
  unsigned __int16 v60; // ax
  int v61; // eax
  void *v62; // rcx
  __int64 v63; // rax
  __int16 v64; // bx
  int v65; // ecx
  char v66; // al
  bool v67; // zf
  __int64 v68; // rax
  unsigned __int64 v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rax
  int v72; // [rsp+40h] [rbp-59h]
  int v73; // [rsp+44h] [rbp-55h]
  __int64 v74; // [rsp+48h] [rbp-51h]
  unsigned int v75; // [rsp+50h] [rbp-49h]
  int v76; // [rsp+54h] [rbp-45h]
  __int16 v77; // [rsp+58h] [rbp-41h]
  unsigned int v78; // [rsp+5Ch] [rbp-3Dh]
  int v79; // [rsp+60h] [rbp-39h]
  int v80; // [rsp+64h] [rbp-35h]
  __int64 v81; // [rsp+68h] [rbp-31h]
  int v82; // [rsp+70h] [rbp-29h]
  char *v83; // [rsp+78h] [rbp-21h]
  __int64 v84; // [rsp+80h] [rbp-19h] BYREF
  __int64 v85; // [rsp+88h] [rbp-11h]
  __int64 *v86; // [rsp+90h] [rbp-9h]
  __int64 v87; // [rsp+98h] [rbp-1h]
  __int64 v88; // [rsp+A0h] [rbp+7h]
  __int64 v89; // [rsp+100h] [rbp+67h] BYREF
  unsigned __int16 v90; // [rsp+108h] [rbp+6Fh]
  __int16 v91; // [rsp+110h] [rbp+77h]
  unsigned __int16 v92; // [rsp+118h] [rbp+7Fh]

  v90 = a2;
  v2 = *(unsigned __int8 *)(a1 + 64);
  v3 = 1;
  v4 = *(__int64 **)a1;
  v5 = a2;
  v86 = *(__int64 **)a1;
  v82 = v2;
  if ( (unsigned int)v2 > 1 )
  {
    v7 = 10;
    if ( (_DWORD)v2 == 2 )
      v7 = 5;
  }
  else
  {
    v7 = 1;
  }
  v8 = *(int **)(a1 + 16);
  if ( v8 && a2 )
    v9 = *v8;
  else
    v9 = 0;
  v72 = v9;
  v10 = sqlite3DbMallocRawNN(*v4, 2 * (v9 + 8 * v7 * ((int)v2 + 4)));
  v11 = 0;
  v88 = v10;
  v12 = v10;
  if ( !v10 )
    return 7;
  v13 = v10;
  v74 = v10;
  v14 = 32LL * (unsigned int)v7;
  v76 = 0;
  v78 = 0;
  v77 = 0;
  v15 = v14 + v12;
  v83 = 0;
  v16 = (char *)(v14 + v14 + v12);
  v85 = v15;
  v17 = v12;
  v81 = v2;
  *(_OWORD *)v15 = 0;
  v18 = 2 * v7;
  v19 = 8 * v2;
  *(_OWORD *)(v15 + 16) = 0;
  do
  {
    *(_QWORD *)(v17 + 24) = v16;
    v17 += 32;
    v16 += v19;
    --v18;
  }
  while ( v18 > 0 );
  if ( v9 )
  {
    v83 = v16;
    memset_0(v16, 0, 2LL * v9);
    v15 = v85;
    v11 = 0;
    v13 = v74;
  }
  v20 = *((_WORD *)v86 + 112);
  if ( v20 >= 48 )
    v20 = 48;
  *(_WORD *)(v15 + 16) = v20;
  v21 = 1;
  v79 = 1;
  if ( v9 )
  {
    v66 = v9;
    if ( (_BYTE)v2 )
      v66 = -1;
    *(_BYTE *)(v15 + 22) = v66;
    v21 = 1;
  }
  v22 = 0;
  v75 = 0;
  if ( !(_BYTE)v2 )
    goto LABEL_14;
  while ( 1 )
  {
    v73 = 0;
    v51 = 0;
    v80 = 0;
    if ( v21 > 0 )
    {
      v52 = v15;
      do
      {
        v50 = *(_QWORD *)(a1 + 88);
        if ( v50 )
        {
          while ( 1 )
          {
            if ( (~*(_QWORD *)v52 & *(_QWORD *)v50) != 0 )
              goto LABEL_82;
            if ( (*(_QWORD *)(v50 + 8) & *(_QWORD *)v52) != 0
              || (*(_DWORD *)(v50 + 56) & 0x4000) != 0 && *(__int16 *)(v52 + 16) < 3 )
            {
              v13 = v74;
LABEL_82:
              v11 = v73;
              goto LABEL_38;
            }
            v53 = *(unsigned __int16 *)(v50 + 18);
            v54 = (unsigned __int16)(*(_WORD *)(v50 + 20) + *(_WORD *)(v52 + 16));
            v91 = *(_WORD *)(v52 + 16);
            v55 = sqlite3LogEstAdd(v53, v54);
            v92 = sqlite3LogEstAdd(v55, *(unsigned __int16 *)(v52 + 20));
            v56 = v92;
            v87 = v57 | v58;
            v44 = 0;
            v45 = *(_BYTE *)(v52 + 22);
            v91 += *(_WORD *)(v50 + 22);
            LOBYTE(v89) = v45;
            if ( (v45 & 0x80u) != 0 )
            {
              v41 = *(_WORD *)(a1 + 60);
              v42 = *(_QWORD *)(a1 + 16);
              v84 = 0;
              v43 = wherePathSatisfiesOrderBy((__int64 **)a1, v42, v52, v41, v75, v50, &v84);
              v44 = 0;
              LOBYTE(v89) = v43;
              v45 = v43;
              if ( v43 < 0 )
                goto LABEL_33;
            }
            else
            {
              v84 = *(_QWORD *)(v52 + 8);
            }
            if ( v45 < v9 )
            {
              v59 = v45;
              v60 = *(_WORD *)&v83[2 * v45];
              if ( !v60 )
              {
                v60 = whereSortingCost(a1, v90, (unsigned int)v9);
                *(_WORD *)&v83[2 * v59] = v60;
              }
              v47 = v92;
              v46 = sqlite3LogEstAdd(v92, v60) + 3;
              goto LABEL_34;
            }
LABEL_33:
            v46 = v56;
            v47 = v56 - 2;
LABEL_34:
            v48 = v44;
            v11 = v73;
            v49 = v74;
            if ( v73 > 0 )
            {
              v19 = v87;
              while ( *(_QWORD *)v49 != v87 || ((*(_BYTE *)(v49 + 22) ^ v45) & 0x80u) != 0 )
              {
                ++v48;
                v49 += 32;
                if ( v48 >= v73 )
                  goto LABEL_35;
              }
              if ( *(__int16 *)(v49 + 18) >= v46
                && (*(_WORD *)(v49 + 18) != v46
                 || *(__int16 *)(v49 + 16) >= v91 && (*(_WORD *)(v49 + 16) != v91 || *(__int16 *)(v49 + 20) > v47)) )
              {
                goto LABEL_61;
              }
            }
            else
            {
LABEL_35:
              if ( v73 < v7 )
              {
                v61 = v73++;
LABEL_58:
                v49 = v74 + 32LL * v61;
LABEL_61:
                v62 = *(void **)(v49 + 24);
                *(_QWORD *)v49 = *(_QWORD *)(v50 + 8) | *(_QWORD *)v52;
                *(_QWORD *)(v49 + 8) = v84;
                *(_WORD *)(v49 + 16) = v91;
                *(_WORD *)(v49 + 20) = v47;
                *(_WORD *)(v49 + 18) = v46;
                *(_BYTE *)(v49 + 22) = v45;
                memcpy_0(v62, *(const void **)(v52 + 24), 8LL * v75);
                v11 = v73;
                v13 = v74;
                *(_QWORD *)(8LL * v75 + *(_QWORD *)(v49 + 24)) = v50;
                if ( v73 >= v7 )
                {
                  v19 = *(unsigned __int16 *)(v74 + 18);
                  v63 = v74 + 32;
                  v64 = *(_WORD *)(v74 + 16);
                  v65 = 1;
                  v78 = *(unsigned __int16 *)(v74 + 18);
                  v77 = v64;
                  v76 = 0;
                  if ( (unsigned int)v7 > 1 )
                  {
                    do
                    {
                      if ( *(__int16 *)(v63 + 18) > (__int16)v19
                        || *(_WORD *)(v63 + 18) == (_WORD)v19 && *(__int16 *)(v63 + 20) > v64 )
                      {
                        v19 = *(unsigned __int16 *)(v63 + 18);
                        v64 = *(_WORD *)(v63 + 20);
                        v76 = v65;
                      }
                      ++v65;
                      v63 += 32;
                    }
                    while ( v65 < v7 );
                    v77 = v64;
                    v78 = v19;
                  }
                }
                v9 = v72;
                goto LABEL_38;
              }
              v19 = v78;
              if ( v46 <= (__int16)v78 && (v46 != (_WORD)v78 || v47 < v77) )
              {
                v61 = v76;
                goto LABEL_58;
              }
            }
            v9 = v72;
            v13 = v74;
LABEL_38:
            v50 = *(_QWORD *)(v50 + 80);
            if ( !v50 )
            {
              v21 = v79;
              v51 = v80;
              break;
            }
          }
        }
        ++v51;
        v52 += 32;
        v80 = v51;
      }
      while ( v51 < v21 );
      LODWORD(v2) = v82;
      v15 = v85;
      v22 = v75;
    }
    v74 = v15;
    ++v22;
    v85 = v13;
    v75 = v22;
    v13 = v15;
    v15 = v85;
    v21 = v11;
    v79 = v11;
    if ( v22 >= (int)v2 )
      break;
    v11 = 0;
  }
  if ( v11 )
  {
    v5 = v90;
LABEL_14:
    v23 = v15;
    v24 = 1;
    if ( v21 > 1 )
    {
      do
      {
        if ( *(_WORD *)(v23 + 18) > *(_WORD *)(v15 + 32LL * v24 + 18) )
          v23 = v15 + 32LL * v24;
        ++v24;
      }
      while ( (int)v24 < v79 );
    }
    v25 = (__int64 *)(v23 + 24);
    v26 = 0;
    if ( (_BYTE)v2 )
    {
      do
      {
        v27 = (unsigned int)v26++;
        v28 = 112 * v27;
        v29 = *(_QWORD *)(*v25 + 8 * v27);
        *(_QWORD *)(v28 + a1 + 960) = v29;
        v30 = *(unsigned __int8 *)(v29 + 16);
        *(_BYTE *)(v28 + a1 + 928) = v30;
        *(_DWORD *)(v28 + a1 + 868) = *(_DWORD *)(104 * v30 + *(_QWORD *)(a1 + 8) + 76);
      }
      while ( v26 < (int)v2 );
    }
    v31 = (char *)(a1 + 60);
    if ( (*(_WORD *)(a1 + 60) & 0x100) == 0 || *v31 < 0 || *(_BYTE *)(a1 + 67) )
    {
      v32 = v81;
    }
    else
    {
      v67 = v5 == 0;
      v32 = v81;
      if ( !v67 )
      {
        v68 = *v25;
        v69 = *(_QWORD *)(a1 + 24);
        v89 = 0;
        if ( wherePathSatisfiesOrderBy((__int64 **)a1, v69, v23, 128, v2 - 1, *(_QWORD *)(v68 + 8 * v81 - 8), &v89) == **(_DWORD **)(a1 + 24) )
        {
          *(_BYTE *)(a1 + 67) = 2;
          v31 = (char *)(a1 + 60);
        }
      }
    }
    *(_DWORD *)(a1 + 68) &= ~4u;
    v33 = *(_DWORD **)(a1 + 16);
    if ( v33 )
    {
      v34 = *(_WORD *)v31;
      v35 = *(_BYTE *)(v23 + 22);
      *(_BYTE *)(a1 + 65) = v35;
      if ( (v34 & 0x80u) != 0 )
      {
        if ( *(char *)(v23 + 22) == *v33 )
          *(_BYTE *)(a1 + 67) = 2;
        v36 = (__int64 *)(a1 + 104);
      }
      else
      {
        v36 = (__int64 *)(a1 + 104);
        *(_QWORD *)(a1 + 104) = *(_QWORD *)(v23 + 8);
        if ( v35 > 0 )
        {
          if ( (_BYTE)v2 && v35 == 1 && (v34 & 3) != 0 )
            *(_DWORD *)(a1 + 68) |= 4u;
        }
        else
        {
          *(_BYTE *)(a1 + 65) = 0;
          if ( (_BYTE)v2 )
          {
            v37 = *(_QWORD *)(*(_QWORD *)(v23 + 24) + 8LL * (unsigned __int8)v2 - 8);
            if ( (((*(_DWORD *)(v37 + 56) & 0x104) != 260) & !_bittest((const signed __int32 *)(v37 + 56), 0xCu)) != 0 )
            {
              v89 = 0;
              v38 = wherePathSatisfiesOrderBy((__int64 **)a1, (unsigned __int64)v33, v23, 2048, v2 - 1, v37, &v89);
              v33 = *(_DWORD **)(a1 + 16);
              if ( v38 == *v33 )
              {
                v39 = v89;
                *(_DWORD *)(a1 + 68) |= 4u;
                *v36 = v39;
              }
            }
          }
        }
      }
      if ( (*(_WORD *)(a1 + 60) & 0x200) != 0 && *(char *)(a1 + 65) == *v33 && (_BYTE)v2 )
      {
        v70 = *v25;
        v89 = 0;
        if ( wherePathSatisfiesOrderBy(
               (__int64 **)a1,
               (unsigned __int64)v33,
               v23,
               0,
               v2 - 1,
               *(_QWORD *)(v70 + 8 * v32 - 8),
               &v89) == **(_DWORD **)(a1 + 16) )
        {
          v71 = v89;
          *(_DWORD *)(a1 + 68) |= 8u;
          *v36 = v71;
        }
      }
    }
    v3 = 0;
    *(_WORD *)(a1 + 72) = *(_WORD *)(v23 + 16);
    goto LABEL_31;
  }
  sqlite3ErrorMsg(v86, "no query solution", v19, v85);
LABEL_31:
  sqlite3DbFreeNN(*v86, v88);
  return v3;
}

```

## disassembly

```asm
0x18004eae8  mov     [rsp-8+arg_8], dx
0x18004eaed  push    rbp
0x18004eaee  push    rbx
0x18004eaef  push    rsi
0x18004eaf0  push    rdi
0x18004eaf1  push    r12
0x18004eaf3  push    r13
0x18004eaf5  push    r14
0x18004eaf7  push    r15
0x18004eaf9  lea     rbp, [rsp-1Fh]
0x18004eafe  sub     rsp, 0B8h
0x18004eb05  movzx   r15d, byte ptr [rcx+40h]
0x18004eb0a  mov     r14d, 1
0x18004eb10  mov     r8, [rcx]
0x18004eb13  movzx   r13d, dx
0x18004eb17  mov     [rbp+57h+var_60], r8
0x18004eb1b  mov     rdi, rcx
0x18004eb1e  mov     [rbp+57h+var_80], r15d
0x18004eb22  cmp     r15d, r14d
0x18004eb25  ja      loc_18004F07B
0x18004eb2b  mov     r12d, r14d
0x18004eb2e  mov     rax, [rcx+10h]
0x18004eb32  xor     ecx, ecx
0x18004eb34  test    rax, rax
0x18004eb37  jnz     loc_18004F091
0x18004eb3d  mov     esi, ecx
0x18004eb3f  lea     eax, [r15+4]
0x18004eb43  mov     [rbp+57h+var_B0], esi
0x18004eb46  imul    eax, r12d
0x18004eb4a  lea     ecx, [rsi+rax*8]
0x18004eb4d  add     ecx, ecx
0x18004eb4f  movsxd  rdx, ecx
0x18004eb52  mov     rcx, [r8]
0x18004eb55  call    sqlite3DbMallocRawNN
0x18004eb5a  xor     r10d, r10d
0x18004eb5d  mov     [rbp+57h+var_50], rax
0x18004eb61  mov     rdx, rax
0x18004eb64  test    rax, rax
0x18004eb67  jz      loc_18004ED38
0x18004eb6d  mov     r11, rax
0x18004eb70  mov     [rbp+57h+var_A8], rax
0x18004eb74  xorps   xmm0, xmm0
0x18004eb77  mov     eax, r12d
0x18004eb7a  shl     rax, 5
0x18004eb7e  mov     r8, r15
0x18004eb81  mov     [rbp+57h+var_9C], r10d
0x18004eb85  mov     [rbp+57h+var_94], r10d
0x18004eb89  mov     [rbp+57h+var_98], r10d
0x18004eb8d  lea     r9, [rax+rdx]
0x18004eb91  mov     [rbp+57h+var_78], r10
0x18004eb95  lea     rcx, [rax+r9]
0x18004eb99  mov     [rbp+57h+var_68], r9
0x18004eb9d  mov     rax, rdx
0x18004eba0  mov     [rbp+57h+var_88], r15
0x18004eba4  movups  xmmword ptr [r9], xmm0
0x18004eba8  lea     edx, [r12+r12]
0x18004ebac  shl     r8, 3
0x18004ebb0  movups  xmmword ptr [r9+10h], xmm0
0x18004ebb5  mov     [rax+18h], rcx
0x18004ebb9  lea     rax, [rax+20h]
0x18004ebbd  add     rcx, r8; void *
0x18004ebc0  sub     edx, r14d
0x18004ebc3  test    edx, edx
0x18004ebc5  jg      short loc_18004EBB5
0x18004ebc7  test    esi, esi
0x18004ebc9  jnz     loc_18004F022
0x18004ebcf  mov     rax, [rbp+57h+var_60]
0x18004ebd3  mov     ecx, 30h ; '0'
0x18004ebd8  movzx   eax, word ptr [rax+0E0h]
0x18004ebdf  cmp     ax, cx
0x18004ebe2  jge     loc_18004F0A1
0x18004ebe8  mov     [r9+10h], ax
0x18004ebed  mov     eax, r14d
0x18004ebf0  mov     [rbp+57h+var_90], eax
0x18004ebf3  test    esi, esi
0x18004ebf5  jnz     loc_18004F0A8
0x18004ebfb  mov     ecx, r10d
0x18004ebfe  mov     [rbp+57h+var_A0], ecx
0x18004ec01  test    r15b, r15b
0x18004ec04  jnz     loc_18004EE67
0x18004ec0a  mov     rsi, r9
0x18004ec0d  mov     edx, r14d
0x18004ec10  cmp     eax, r14d
0x18004ec13  jg      loc_18004F13D
0x18004ec19  lea     r12, [rsi+18h]
0x18004ec1d  mov     r8d, r10d
0x18004ec20  test    r15b, r15b
0x18004ec23  jz      short loc_18004EC62
0x18004ec25  mov     rax, [r12]
0x18004ec29  mov     ecx, r8d
0x18004ec2c  add     r8d, r14d
0x18004ec2f  imul    rdx, rcx, 70h ; 'p'
0x18004ec33  mov     rax, [rax+rcx*8]
0x18004ec37  mov     [rdx+rdi+3C0h], rax
0x18004ec3f  movzx   eax, byte ptr [rax+10h]
0x18004ec43  imul    rcx, rax, 68h ; 'h'
0x18004ec47  mov     [rdx+rdi+3A0h], al
0x18004ec4e  mov     rax, [rdi+8]
0x18004ec52  mov     ecx, [rcx+rax+4Ch]
0x18004ec56  mov     [rdx+rdi+364h], ecx
0x18004ec5d  cmp     r8d, r15d
0x18004ec60  jl      short loc_18004EC25
0x18004ec62  lea     rbx, [rdi+3Ch]
0x18004ec66  mov     eax, 100h
0x18004ec6b  test    [rbx], ax
0x18004ec6e  jnz     loc_18004F163
0x18004ec74  mov     r13, [rbp+57h+var_88]
0x18004ec78  and     dword ptr [rdi+44h], 0FFFFFFFBh
0x18004ec7c  xor     r9d, r9d
0x18004ec7f  mov     r10, [rdi+10h]
0x18004ec83  test    r10, r10
0x18004ec86  jz      loc_18004ED57
0x18004ec8c  movzx   r8d, word ptr [rbx]
0x18004ec90  mov     dl, [rsi+16h]
0x18004ec93  mov     [rdi+41h], dl
0x18004ec96  test    r8b, r8b
0x18004ec99  js      loc_18004F1DD
0x18004ec9f  mov     rax, [rsi+8]
0x18004eca3  lea     rbx, [rdi+68h]
0x18004eca7  mov     [rbx], rax
0x18004ecaa  test    dl, dl
0x18004ecac  jg      loc_18004ED3F
0x18004ecb2  mov     [rdi+41h], r9b
0x18004ecb6  test    r15b, r15b
0x18004ecb9  jz      loc_18004ED48
0x18004ecbf  mov     rax, [rsi+18h]
0x18004ecc3  movzx   ecx, r15b
0x18004ecc7  mov     r8, [rax+rcx*8-8]
0x18004eccc  mov     ecx, 104h
0x18004ecd1  mov     eax, [r8+38h]
0x18004ecd5  and     eax, ecx
0x18004ecd7  cmp     eax, ecx
0x18004ecd9  setnz   cl
0x18004ecdc  bt      dword ptr [r8+38h], 0Ch
0x18004ece2  setnb   al
0x18004ece5  test    al, cl
0x18004ece7  jz      short loc_18004ED48
0x18004ece9  lea     rcx, [rbp+57h+arg_0]
0x18004eced  mov     [rbp+57h+arg_0], r9
0x18004ecf1  mov     [rsp+0F0h+var_C0], rcx
0x18004ecf6  movzx   eax, r15w
0x18004ecfa  mov     [rsp+0F0h+var_C8], r8
0x18004ecff  sub     ax, r14w
0x18004ed03  mov     r8, rsi
0x18004ed06  mov     [rsp+0F0h+var_D0], ax
0x18004ed0b  mov     r9d, 800h
0x18004ed11  mov     rdx, r10
0x18004ed14  mov     rcx, rdi
0x18004ed17  call    wherePathSatisfiesOrderBy
0x18004ed1c  mov     r10, [rdi+10h]
0x18004ed20  movsx   ecx, al
0x18004ed23  cmp     ecx, [r10]
0x18004ed26  jnz     short loc_18004ED33
0x18004ed28  mov     rax, [rbp+57h+arg_0]
0x18004ed2c  or      dword ptr [rdi+44h], 4
0x18004ed30  mov     [rbx], rax
0x18004ed33  xor     r9d, r9d
0x18004ed36  jmp     short loc_18004ED48
0x18004ed38  mov     eax, 7
0x18004ed3d  jmp     short loc_18004ED75
0x18004ed3f  test    r15b, r15b
0x18004ed42  jnz     loc_18004F1F3
0x18004ed48  mov     eax, 200h
0x18004ed4d  test    [rdi+3Ch], ax
0x18004ed51  jnz     loc_18004F20F
0x18004ed57  movzx   eax, word ptr [rsi+10h]
0x18004ed5b  xor     r14d, r14d
0x18004ed5e  mov     [rdi+48h], ax
0x18004ed62  mov     rax, [rbp+57h+var_60]
0x18004ed66  mov     rdx, [rbp+57h+var_50]
0x18004ed6a  mov     rcx, [rax]
0x18004ed6d  call    sqlite3DbFreeNN
0x18004ed72  mov     eax, r14d
0x18004ed75  add     rsp, 0B8h
0x18004ed7c  pop     r15
0x18004ed7e  pop     r14
0x18004ed80  pop     r13
0x18004ed82  pop     r12
0x18004ed84  pop     rdi
0x18004ed85  pop     rsi
0x18004ed86  pop     rbx
0x18004ed87  pop     rbp
0x18004ed88  retn
0x18004ed89  movzx   r9d, word ptr [rdi+3Ch]
0x18004ed8e  lea     rax, [rbp+57h+var_70]
0x18004ed92  mov     rdx, [rdi+10h]
0x18004ed96  mov     r8, r15
0x18004ed99  mov     [rsp+0F0h+var_C0], rax
0x18004ed9e  mov     rcx, rdi
0x18004eda1  mov     eax, [rbp+57h+var_A0]
0x18004eda4  mov     [rsp+0F0h+var_C8], r13
0x18004eda9  mov     [rsp+0F0h+var_D0], ax
0x18004edae  mov     [rbp+57h+var_70], r10
0x18004edb2  call    wherePathSatisfiesOrderBy
0x18004edb7  xor     r10d, r10d
0x18004edba  mov     byte ptr [rbp+57h+arg_0], al
0x18004edbd  mov     r11b, al
0x18004edc0  test    al, al
0x18004edc2  jns     loc_18004EF11
0x18004edc8  movzx   edx, bx
0x18004edcb  sub     bx, 2
0x18004edcf  mov     r9, [rbp+57h+var_A8]
0x18004edd3  mov     ecx, r10d
0x18004edd6  mov     r10d, [rbp+57h+var_AC]
0x18004edda  mov     rsi, r9
0x18004eddd  test    r10d, r10d
0x18004ede0  jg      loc_18004F0E0
0x18004ede6  cmp     r10d, r12d
0x18004ede9  jl      loc_18004EF4A
0x18004edef  mov     r8d, [rbp+57h+var_94]
0x18004edf3  cmp     dx, r8w
0x18004edf7  jle     loc_18004F129
0x18004edfd  mov     esi, [rbp+57h+var_B0]
0x18004ee00  mov     r11, r9
0x18004ee03  mov     r13, [r13+50h]
0x18004ee07  test    r13, r13
0x18004ee0a  jnz     short loc_18004EE84
0x18004ee0c  mov     eax, [rbp+57h+var_90]
0x18004ee0f  mov     edx, [rbp+57h+var_8C]
0x18004ee12  add     edx, r14d
0x18004ee15  add     r15, 20h ; ' '
0x18004ee19  mov     [rbp+57h+var_8C], edx
0x18004ee1c  cmp     edx, eax
0x18004ee1e  jl      short loc_18004EE7B
0x18004ee20  mov     r15d, [rbp+57h+var_80]
0x18004ee24  mov     r9, [rbp+57h+var_68]
0x18004ee28  mov     ecx, [rbp+57h+var_A0]
0x18004ee2b  mov     rax, r11
0x18004ee2e  mov     [rbp+57h+var_A8], r9
0x18004ee32  add     ecx, r14d
0x18004ee35  mov     [rbp+57h+var_68], rax
0x18004ee39  mov     [rbp+57h+var_A0], ecx
0x18004ee3c  mov     r11, r9
0x18004ee3f  mov     r9, rax
0x18004ee42  mov     eax, r10d
0x18004ee45  mov     [rbp+57h+var_90], eax
0x18004ee48  cmp     ecx, r15d
0x18004ee4b  jl      loc_18004F0BF
0x18004ee51  test    r10d, r10d
0x18004ee54  jz      loc_18004F066
0x18004ee5a  movzx   r13d, [rbp+57h+arg_8]
0x18004ee5f  xor     r10d, r10d
0x18004ee62  jmp     loc_18004EC0A
0x18004ee67  xor     r13d, r13d
0x18004ee6a  mov     [rbp+57h+var_AC], r10d
0x18004ee6e  mov     edx, r13d
0x18004ee71  mov     [rbp+57h+var_8C], edx
0x18004ee74  test    eax, eax
0x18004ee76  jle     short loc_18004EE2B
0x18004ee78  mov     r15, r9
0x18004ee7b  mov     r13, [rdi+58h]
0x18004ee7f  test    r13, r13
0x18004ee82  jz      short loc_18004EE12
0x18004ee84  mov     r10, [r15]
0x18004ee87  mov     rax, r10
0x18004ee8a  not     rax
0x18004ee8d  test    [r13+0], rax
0x18004ee91  jnz     loc_18004F0D7
0x18004ee97  mov     r11, [r13+8]
0x18004ee9b  test    r10, r11
0x18004ee9e  jnz     loc_18004F0D3
0x18004eea4  test    dword ptr [r13+38h], 4000h
0x18004eeac  jnz     loc_18004F0C7
0x18004eeb2  movzx   eax, word ptr [r15+10h]
0x18004eeb7  movzx   ecx, word ptr [r13+12h]
0x18004eebc  movzx   edx, ax
0x18004eebf  add     dx, [r13+14h]
0x18004eec4  mov     [rbp+57h+arg_10], ax
0x18004eec8  call    sqlite3LogEstAdd
0x18004eecd  movzx   edx, word ptr [r15+14h]
0x18004eed2  movzx   ecx, ax
0x18004eed5  call    sqlite3LogEstAdd
0x18004eeda  or      r11, r10
0x18004eedd  mov     [rbp+57h+arg_18], ax
0x18004eee1  movzx   ebx, ax
0x18004eee4  mov     [rbp+57h+var_58], r11
0x18004eee8  movzx   eax, [rbp+57h+arg_10]
0x18004eeec  xor     r10d, r10d
0x18004eeef  add     ax, [r13+16h]
0x18004eef4  mov     r11b, [r15+16h]
0x18004eef8  mov     [rbp+57h+arg_10], ax
0x18004eefc  mov     byte ptr [rbp+57h+arg_0], r11b
0x18004ef00  test    r11b, r11b
0x18004ef03  js      loc_18004ED89
0x18004ef09  mov     rax, [r15+8]
0x18004ef0d  mov     [rbp+57h+var_70], rax
0x18004ef11  movzx   r9d, r11b
0x18004ef15  cmp     r9d, esi
0x18004ef18  jge     loc_18004EDC8
0x18004ef1e  mov     rax, [rbp+57h+var_78]
0x18004ef22  movzx   ebx, r11b
0x18004ef26  movzx   eax, word ptr [rax+rbx*2]
0x18004ef2a  test    ax, ax
0x18004ef2d  jz      loc_18004F043
0x18004ef33  movzx   ebx, [rbp+57h+arg_18]
0x18004ef37  movzx   edx, ax
0x18004ef3a  movzx   ecx, bx
0x18004ef3d  call    sqlite3LogEstAdd
0x18004ef42  lea     edx, [rax+3]
0x18004ef45  jmp     loc_18004EDCF
  ... truncated ...
```
