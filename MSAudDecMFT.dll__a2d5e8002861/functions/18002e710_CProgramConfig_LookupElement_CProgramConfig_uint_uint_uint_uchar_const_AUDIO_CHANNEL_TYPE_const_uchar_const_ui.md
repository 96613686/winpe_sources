# CProgramConfig_LookupElement(CProgramConfig *,uint,uint,uint,uchar * const,AUDIO_CHANNEL_TYPE * const,uchar * const,uint,uchar *,MP4_ELEMENT_ID * const,MP4_ELEMENT_ID)

- ea: `0x18002e710`
- end: `0x18002efa6`
- name: `?CProgramConfig_LookupElement@@YAHPEAUCProgramConfig@@IIIQEAEQEAW4AUDIO_CHANNEL_TYPE@@1IPEAEQEAW4MP4_ELEMENT_ID@@W43@@Z`
- size: `2198`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c510`

## callees

- `0x18002e710`
- `0x18004d320`

## pseudocode

```c
__int64 __fastcall CProgramConfig_LookupElement(
        unsigned __int8 *a1,
        int a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        unsigned __int8 *a9,
        __int64 a10,
        unsigned int a11)
{
  __int64 v11; // r13
  __int64 v13; // r15
  int v14; // r11d
  unsigned __int8 *v15; // r12
  int v17; // eax
  int v18; // edx
  __int64 v19; // rcx
  int v21; // r11d
  int v22; // r11d
  int v23; // r11d
  unsigned int v24; // eax
  int v25; // r11d
  int v26; // r11d
  int v27; // r11d
  char v28; // al
  char v29; // r11
  bool v30; // cf
  unsigned __int8 v31; // al
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // r8
  int j; // edx
  int v36; // ebx
  int v37; // r11d
  __int64 v38; // rdx
  unsigned __int8 v39; // al
  int v40; // ebx
  __int64 v41; // r8
  __int64 v42; // rdx
  unsigned __int8 v43; // al
  int v44; // ebx
  __int64 v45; // r8
  __int64 v46; // rdx
  unsigned __int8 v47; // al
  unsigned __int8 v48; // dl
  int v49; // r8d
  int i; // edx
  int v51; // eax
  int v52; // r11d
  int v53; // ebx
  __int64 v54; // rcx
  int v55; // edx
  int v56; // ebx
  int v57; // r8d
  __int64 v58; // rsi
  int v59; // edi
  int v60; // r12d
  __int64 v61; // r11
  __int64 v62; // r11
  __int64 v63; // r11
  int v64; // edx
  int v65; // eax
  char v66; // cl
  int v67; // r13d
  int k; // r11d
  int v69; // ebx
  __int64 v70; // rcx
  int v71; // edx
  int v72; // ebx
  int v73; // r8d
  __int64 v74; // r12
  int v75; // edi
  int v76; // esi
  __int64 v77; // r11
  __int64 v78; // r11
  __int64 v79; // r11
  int v80; // edx
  int v81; // eax
  char v82; // cl
  int v83; // eax
  int v84; // r12d
  int m; // r11d
  int v86; // edi
  __int64 v87; // rbx
  __int64 v88; // rsi
  int v89; // edx
  __int64 v90; // r11
  __int64 v91; // r11
  __int64 v92; // r11
  unsigned __int8 v93; // cl
  int v94; // [rsp+0h] [rbp-80h]
  int v95; // [rsp+4h] [rbp-7Ch]
  __int64 v96; // [rsp+20h] [rbp-60h]
  int v97; // [rsp+28h] [rbp-58h]
  __int64 v98; // [rsp+30h] [rbp-50h]
  int v99; // [rsp+38h] [rbp-48h]
  __int64 v100; // [rsp+40h] [rbp-40h]
  int v101; // [rsp+48h] [rbp-38h]
  __int64 v102; // [rsp+50h] [rbp-30h]
  int v103; // [rsp+58h] [rbp-28h]
  __int64 v104; // [rsp+60h] [rbp-20h]
  int v105; // [rsp+68h] [rbp-18h]

  v11 = a5;
  v13 = a7;
  v14 = a2;
  v15 = a9;
  if ( a2 && a2 != 31 )
  {
    if ( a11 <= 0x12 )
    {
      v17 = 458763;
      if ( _bittest(&v17, a11) )
      {
        *a9 = a1[464];
        v18 = *(_DWORD *)(a10 + 4LL * a1[464]);
        if ( v18 == a11 || a11 - 16 <= 2 )
          goto LABEL_6;
        if ( v14 == 2 && !a11 )
        {
          v14 = 1;
          goto LABEL_6;
        }
        if ( v18 == 3 && !a11 )
        {
LABEL_6:
          if ( a4 < 3 )
          {
LABEL_7:
            *(_DWORD *)(a6 + 4LL * a4) = 1;
            *(_BYTE *)(a4 + a7) = a4;
LABEL_8:
            if ( ((a11 - 1) & 0xFFFFFFEF) == 0 )
            {
              v19 = a4 + 1;
              *(_DWORD *)(a6 + 4 * v19) = *(_DWORD *)(a6 + 4LL * a4);
              *(_BYTE *)(v19 + a7) = *(_BYTE *)(a4 + a7) + 1;
            }
            ++a1[464];
            return 1;
          }
          v21 = v14 - 4;
          if ( !v21 || (v22 = v21 - 1) == 0 || (v23 = v22 - 1) == 0 )
          {
            if ( a4 != 3 )
            {
              v24 = a4 - 4;
              if ( a4 != 4 )
              {
LABEL_17:
                if ( v24 != 1 )
                  goto LABEL_8;
LABEL_18:
                *(_DWORD *)(a6 + 4LL * a4) = 4;
                *(_BYTE *)(a4 + a7) = 0;
                goto LABEL_8;
              }
            }
            goto LABEL_35;
          }
          v25 = v23 - 1;
          if ( v25 )
          {
            v26 = v25 - 4;
            if ( v26 )
            {
              v27 = v26 - 1;
              if ( v27 )
              {
                if ( v27 != 2 )
                  goto LABEL_7;
                if ( a4 == 3 || a4 == 4 )
                {
LABEL_35:
                  *(_DWORD *)(a6 + 4LL * a4) = 3;
                  v28 = a4 - 3;
                  goto LABEL_36;
                }
                if ( a4 == 5 )
                  goto LABEL_18;
                if ( a4 - 6 > 1 )
                  goto LABEL_8;
                *(_DWORD *)(a6 + 4LL * a4) = 17;
                v28 = a4 - 6;
LABEL_36:
                *(_BYTE *)(a4 + a7) = v28;
                goto LABEL_8;
              }
              if ( a4 >= 7 )
                v29 = 0;
              else
                v29 = a4 - 3;
              v30 = a4 < 7;
            }
            else
            {
              if ( a4 >= 6 )
                v29 = 0;
              else
                v29 = a4 - 3;
              v30 = a4 < 6;
            }
            *(_DWORD *)(a6 + 4LL * a4) = 4 - v30;
            *(_BYTE *)(a4 + a7) = v29;
            goto LABEL_8;
          }
          if ( a4 == 3 || a4 == 4 )
            goto LABEL_7;
          if ( a4 != 5 )
          {
            v24 = a4 - 6;
            if ( a4 != 6 )
              goto LABEL_17;
          }
          *(_DWORD *)(a6 + 4LL * a4) = 3;
          v28 = a4 - 5;
          goto LABEL_36;
        }
        return 0;
      }
    }
    return 1;
  }
  v31 = a1[461];
  if ( !v31 || a1[462] > 8u )
  {
    if ( a11 - 16 > 2 )
    {
      if ( (a11 & 0xFFFFFFFC) != 0 || a11 == 2 )
        return 1;
      *(_DWORD *)(a10 + 4LL * a1[464]) = a11;
    }
    v93 = a1[464];
    a1[464] = v93 + 1;
    *a9 = v93;
    return 1;
  }
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  if ( v31 != 2
    || (a11 & 0xFFFFFFFC) != 0
    || a11 == 2
    || (v32 = a1[464], v33 = *(_DWORD *)(a10 + 4 * v32), a1[464] = v32 + 1, v33 == a11) )
  {
    v34 = 0;
    v95 = 0;
    if ( a11 )
    {
      if ( a11 != 1 )
      {
        switch ( a11 )
        {
          case 2u:
            for ( i = 0; i < a1[8]; ++i )
            {
              if ( a1[i + 188] == a3 )
                return 1;
            }
            break;
          case 3u:
            v36 = a1[3];
            v37 = 0;
            if ( a1[3] )
            {
              do
              {
                v38 = a1[v34 + 48];
                v39 = a1[v34 + 16];
                ++*((_DWORD *)&v96 + v38);
                v34 = (unsigned int)(v34 + 1);
                *((_DWORD *)&v98 + v38) += (v39 != 0) + 1;
              }
              while ( (int)v34 < v36 );
            }
            v40 = a1[4];
            v41 = 0;
            if ( a1[4] )
            {
              do
              {
                v42 = a1[v41 + 96];
                v43 = a1[v41 + 64];
                ++*((_DWORD *)&v96 + v42);
                v41 = (unsigned int)(v41 + 1);
                *((_DWORD *)&v98 + v42) += (v43 != 0) + 1;
              }
              while ( (int)v41 < v40 );
            }
            v44 = a1[5];
            v45 = 0;
            if ( a1[5] )
            {
              do
              {
                v46 = a1[v45 + 144];
                v47 = a1[v45 + 112];
                ++*((_DWORD *)&v96 + v46);
                v45 = (unsigned int)(v45 + 1);
                *((_DWORD *)&v98 + v46) += (v47 != 0) + 1;
              }
              while ( (int)v45 < v44 );
            }
            v48 = v96;
            v49 = v98;
            while ( v37 < a1[6] )
            {
              if ( a1[v37 + 160] == a3 )
              {
                *(_BYTE *)(v49 + a5) = a4;
                *a9 = v48;
                *(_DWORD *)(a6 + 4LL * v49) = 4;
                *(_BYTE *)(v49 + a7) = v37;
                return 1;
              }
              ++v48;
              ++v49;
              ++v37;
            }
            break;
          case 4u:
            for ( j = 0; j < a1[7]; ++j )
            {
              if ( a1[j + 164] == a3 )
                return 1;
            }
            break;
        }
        return 0;
      }
      LODWORD(v34) = 1;
      v95 = 1;
    }
    v51 = a1[3];
    v52 = 0;
    v94 = v51;
    while ( v52 < v51 )
    {
      v53 = a1[v52 + 16];
      v54 = a1[v52 + 48];
      if ( (_DWORD)v34 == v53 && a1[v52 + 32] == a3 )
      {
        v55 = *((_DWORD *)&v96 + v54);
        v56 = v54 - 1;
        v57 = *((_DWORD *)&v98 + v54);
        v58 = a1[v52 + 48];
        v59 = (16 * v54) | 1;
        if ( (int)v54 - 1 >= 0 )
        {
          v60 = a1[4];
          while ( 1 )
          {
            v61 = 0;
            if ( v94 )
            {
              do
              {
                if ( a1[v61 + 48] == v56 )
                {
                  ++v55;
                  v57 += (a1[v61 + 16] != 0) + 1;
                }
                v61 = (unsigned int)(v61 + 1);
              }
              while ( (int)v61 < v94 );
              v13 = a7;
            }
            v62 = 0;
            if ( (_BYTE)v60 )
            {
              do
              {
                if ( a1[v62 + 96] == v56 )
                {
                  ++v55;
                  v57 += (a1[v62 + 64] != 0) + 1;
                }
                v62 = (unsigned int)(v62 + 1);
              }
              while ( (int)v62 < v60 );
            }
            v63 = 0;
            if ( a1[5] )
            {
              do
              {
                if ( a1[v63 + 144] == v56 )
                {
                  ++v55;
                  v57 += (a1[v63 + 112] != 0) + 1;
                }
                v63 = (unsigned int)(v63 + 1);
              }
              while ( (int)v63 < a1[5] );
            }
            if ( !v56 )
              break;
            if ( --v56 < 0 )
              goto LABEL_106;
          }
          v65 = a1[6];
          LOBYTE(v55) = v65 + v55;
          v57 += v65;
LABEL_106:
          v11 = a5;
          v15 = a9;
        }
        v66 = *((_BYTE *)&v100 + 4 * v58);
        *(_BYTE *)(v57 + v11) = a4;
        *(_DWORD *)(a6 + 4LL * v57) = v59;
        *(_BYTE *)(v57 + v13) = v66;
        if ( v95 )
        {
          *(_BYTE *)(v57 + v11 + 1) = a4 + 1;
          *(_DWORD *)(a6 + 4LL * v57 + 4) = v59;
          *(_BYTE *)(v57 + v13 + 1) = v66 + 1;
        }
        *v15 = v55;
        return 1;
      }
      ++*((_DWORD *)&v96 + (int)v54);
      v64 = *((_DWORD *)&v100 + (int)v54) + ((_BYTE)v53 != 0) + 1;
      *((_DWORD *)&v98 + (int)v54) += ((_BYTE)v53 != 0) + 1;
      v51 = v94;
      ++v52;
      *((_DWORD *)&v100 + (int)v54) = v64;
      LODWORD(v34) = v95;
    }
    v67 = a1[4];
    for ( k = 0; k < v67; ++k )
    {
      v69 = a1[k + 64];
      v70 = a1[k + 96];
      if ( (_DWORD)v34 == v69 && a1[k + 80] == a3 )
      {
        v71 = *((_DWORD *)&v96 + v70);
        v72 = v70 - 1;
        v73 = *((_DWORD *)&v98 + v70);
        v74 = a1[k + 96];
        v75 = (16 * v70) | 2;
        if ( (int)v70 - 1 >= 0 )
        {
          v76 = a1[5];
          while ( 1 )
          {
            v77 = 0;
            if ( v94 )
            {
              do
              {
                if ( a1[v77 + 48] == v72 )
                {
                  ++v71;
                  v73 += (a1[v77 + 16] != 0) + 1;
                }
                v77 = (unsigned int)(v77 + 1);
              }
              while ( (int)v77 < v94 );
              v13 = a7;
            }
            v78 = 0;
            if ( v67 )
            {
              do
              {
                if ( a1[v78 + 96] == v72 )
                {
                  ++v71;
                  v73 += (a1[v78 + 64] != 0) + 1;
                }
                v78 = (unsigned int)(v78 + 1);
              }
              while ( (int)v78 < v67 );
            }
            v79 = 0;
            if ( (_BYTE)v76 )
            {
              do
              {
                if ( a1[v79 + 144] == v72 )
                {
                  ++v71;
                  v73 += (a1[v79 + 112] != 0) + 1;
                }
                v79 = (unsigned int)(v79 + 1);
              }
              while ( (int)v79 < v76 );
            }
            if ( !v72 )
              break;
            if ( --v72 < 0 )
              goto LABEL_134;
          }
          v81 = a1[6];
          LOBYTE(v71) = v81 + v71;
          v73 += v81;
        }
LABEL_134:
        v82 = *((_BYTE *)&v102 + 4 * v74);
LABEL_137:
        *(_BYTE *)(a5 + v73) = a4;
        *(_DWORD *)(a6 + 4LL * v73) = v75;
        *(_BYTE *)(v13 + v73) = v82;
        if ( v95 )
        {
          *(_BYTE *)(a5 + v73 + 1) = a4 + 1;
          *(_DWORD *)(a6 + 4LL * v73 + 4) = v75;
          *(_BYTE *)(v13 + v73 + 1) = v82 + 1;
        }
        *a9 = v71;
        return 1;
      }
      ++*((_DWORD *)&v96 + (int)v70);
      v80 = *((_DWORD *)&v102 + (int)v70) + ((_BYTE)v69 != 0) + 1;
      *((_DWORD *)&v98 + (int)v70) += ((_BYTE)v69 != 0) + 1;
      *((_DWORD *)&v102 + (int)v70) = v80;
      LODWORD(v34) = v95;
    }
    v84 = a1[5];
    for ( m = 0; m < v84; ++m )
    {
      v86 = a1[m + 112];
      v87 = a1[m + 144];
      if ( (_DWORD)v34 == v86 && a1[m + 128] == a3 )
      {
        v71 = *((_DWORD *)&v96 + v87);
        v73 = *((_DWORD *)&v98 + v87);
        v88 = a1[m + 144];
        v75 = (16 * v87) | 3;
        while ( 1 )
        {
          LODWORD(v87) = v87 - 1;
          if ( (int)v87 < 0 )
            break;
          v90 = 0;
          if ( v94 )
          {
            do
            {
              if ( a1[v90 + 48] == (_DWORD)v87 )
              {
                ++v71;
                v73 += (a1[v90 + 16] != 0) + 1;
              }
              v90 = (unsigned int)(v90 + 1);
            }
            while ( (int)v90 < v94 );
            v13 = a7;
          }
          v91 = 0;
          if ( v67 )
          {
            do
            {
              if ( a1[v91 + 96] == (_DWORD)v87 )
              {
                ++v71;
                v73 += (a1[v91 + 64] != 0) + 1;
              }
              v91 = (unsigned int)(v91 + 1);
            }
            while ( (int)v91 < v67 );
          }
          v92 = 0;
          if ( v84 )
          {
            do
            {
              if ( a1[v92 + 144] == (_DWORD)v87 )
              {
                ++v71;
                v73 += (a1[v92 + 112] != 0) + 1;
              }
              v92 = (unsigned int)(v92 + 1);
            }
            while ( (int)v92 < v84 );
          }
          if ( !(_DWORD)v87 )
          {
            v83 = a1[6];
            LOBYTE(v71) = v83 + v71;
            v73 += v83;
            break;
          }
        }
        v82 = *((_BYTE *)&v104 + 4 * v88);
        goto LABEL_137;
      }
      ++*((_DWORD *)&v96 + (int)v87);
      v89 = *((_DWORD *)&v104 + (int)v87) + ((_BYTE)v86 != 0) + 1;
      *((_DWORD *)&v98 + (int)v87) += ((_BYTE)v86 != 0) + 1;
      *((_DWORD *)&v104 + (int)v87) = v89;
      LODWORD(v34) = v95;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002e710  mov     [rsp-38h+arg_8], rbx
0x18002e715  push    rbp
0x18002e716  push    rsi
0x18002e717  push    rdi
0x18002e718  push    r12
0x18002e71a  push    r13
0x18002e71c  push    r14
0x18002e71e  push    r15
0x18002e720  mov     rbp, rsp
0x18002e723  sub     rsp, 80h
0x18002e72a  mov     rax, cs:__security_cookie
0x18002e731  xor     rax, rsp
0x18002e734  mov     [rbp+var_10], rax
0x18002e738  mov     r13, [rbp+arg_20]
0x18002e73c  mov     esi, r8d
0x18002e73f  mov     r15, [rbp+arg_30]
0x18002e743  mov     r11d, edx
0x18002e746  mov     r12, [rbp+arg_40]
0x18002e74d  mov     r10, rcx
0x18002e750  mov     r14, [rbp+arg_28]
0x18002e754  mov     rdi, [rbp+arg_48]
0x18002e75b  mov     [rbp+var_78], r13
0x18002e75f  mov     [rbp+var_68], r15
0x18002e763  mov     [rbp+var_70], r12
0x18002e767  test    edx, edx
0x18002e769  jz      loc_18002E956
0x18002e76f  cmp     edx, 1Fh
0x18002e772  jz      loc_18002E956
0x18002e778  mov     ebx, [rbp+arg_50]
0x18002e77e  cmp     ebx, 12h
0x18002e781  ja      short loc_18002E7E9
0x18002e783  mov     eax, 7000Bh
0x18002e788  bt      eax, ebx
0x18002e78b  jnb     short loc_18002E7E9
0x18002e78d  mov     al, [rcx+1D0h]
0x18002e793  mov     [r12], al
0x18002e797  movzx   eax, byte ptr [rcx+1D0h]
0x18002e79e  mov     ecx, 3
0x18002e7a3  mov     edx, [rdi+rax*4]
0x18002e7a6  cmp     edx, ebx
0x18002e7a8  jnz     loc_18002E8A8
0x18002e7ae  mov     edx, r9d
0x18002e7b1  cmp     r9d, ecx
0x18002e7b4  jnb     short loc_18002E816
0x18002e7b6  mov     dword ptr [r14+rdx*4], 1
0x18002e7be  mov     [rdx+r15], r9b
0x18002e7c2  lea     eax, [rbx-1]
0x18002e7c5  test    eax, 0FFFFFFEFh
0x18002e7ca  jnz     short loc_18002E7E2
0x18002e7cc  mov     eax, [r14+rdx*4]
0x18002e7d0  lea     ecx, [r9+1]
0x18002e7d4  mov     [r14+rcx*4], eax
0x18002e7d8  mov     al, [rdx+r15]
0x18002e7dc  inc     al
0x18002e7de  mov     [rcx+r15], al
0x18002e7e2  inc     byte ptr [r10+1D0h]
0x18002e7e9  mov     eax, 1
0x18002e7ee  mov     rcx, [rbp+var_10]
0x18002e7f2  xor     rcx, rsp; StackCookie
0x18002e7f5  call    __security_check_cookie
0x18002e7fa  mov     rbx, [rsp+80h+arg_8]
0x18002e802  add     rsp, 80h
0x18002e809  pop     r15
0x18002e80b  pop     r14
0x18002e80d  pop     r13
0x18002e80f  pop     r12
0x18002e811  pop     rdi
0x18002e812  pop     rsi
0x18002e813  pop     rbp
0x18002e814  retn
0x18002e816  mov     r8d, 4
0x18002e81c  sub     r11d, r8d
0x18002e81f  jz      short loc_18002E82D
0x18002e821  sub     r11d, 1
0x18002e825  jz      short loc_18002E82D
0x18002e827  sub     r11d, 1
0x18002e82b  jnz     short loc_18002E858
0x18002e82d  mov     eax, r9d
0x18002e830  sub     eax, ecx
0x18002e832  jz      loc_18002E8DA
0x18002e838  sub     eax, 1
0x18002e83b  jz      loc_18002E8DA
0x18002e841  cmp     eax, 1
0x18002e844  jnz     loc_18002E7C2
0x18002e84a  mov     [r14+rdx*4], r8d
0x18002e84e  mov     byte ptr [rdx+r15], 0
0x18002e853  jmp     loc_18002E7C2
0x18002e858  sub     r11d, 1
0x18002e85c  jz      loc_18002E92A
0x18002e862  sub     r11d, r8d
0x18002e865  jz      loc_18002E903
0x18002e86b  sub     r11d, 1
0x18002e86f  jz      short loc_18002E8EC
0x18002e871  cmp     r11d, 2
0x18002e875  jnz     loc_18002E7B6
0x18002e87b  mov     eax, r9d
0x18002e87e  sub     eax, ecx
0x18002e880  jz      short loc_18002E8DA
0x18002e882  sub     eax, 1
0x18002e885  jz      short loc_18002E8DA
0x18002e887  sub     eax, 1
0x18002e88a  jz      short loc_18002E84A
0x18002e88c  sub     eax, 1
0x18002e88f  jz      short loc_18002E89A
0x18002e891  cmp     eax, 1
0x18002e894  jnz     loc_18002E7C2
0x18002e89a  mov     dword ptr [r14+rdx*4], 11h
0x18002e8a2  lea     eax, [r9-6]
0x18002e8a6  jmp     short loc_18002E8E3
0x18002e8a8  lea     eax, [rbx-10h]
0x18002e8ab  cmp     eax, 2
0x18002e8ae  jbe     loc_18002E7AE
0x18002e8b4  cmp     r11d, 2
0x18002e8b8  jnz     short loc_18002E8C7
0x18002e8ba  test    ebx, ebx
0x18002e8bc  jnz     short loc_18002E8C7
0x18002e8be  lea     r11d, [rbx+1]
0x18002e8c2  jmp     loc_18002E7AE
0x18002e8c7  cmp     edx, ecx
0x18002e8c9  jnz     short loc_18002E8D3
0x18002e8cb  test    ebx, ebx
0x18002e8cd  jz      loc_18002E7AE
0x18002e8d3  xor     eax, eax
0x18002e8d5  jmp     loc_18002E7EE
0x18002e8da  mov     al, r9b
0x18002e8dd  mov     [r14+rdx*4], ecx
0x18002e8e1  sub     al, cl
0x18002e8e3  mov     [rdx+r15], al
0x18002e8e7  jmp     loc_18002E7C2
0x18002e8ec  cmp     r9d, 7
0x18002e8f0  jnb     short loc_18002E8FA
0x18002e8f2  mov     r11b, r9b
0x18002e8f5  sub     r11b, cl
0x18002e8f8  jmp     short loc_18002E8FD
0x18002e8fa  xor     r11b, r11b
0x18002e8fd  cmp     r9d, 7
0x18002e901  jmp     short loc_18002E918
0x18002e903  cmp     r9d, 6
0x18002e907  jnb     short loc_18002E911
0x18002e909  mov     r11b, r9b
0x18002e90c  sub     r11b, cl
0x18002e90f  jmp     short loc_18002E914
0x18002e911  xor     r11b, r11b
0x18002e914  cmp     r9d, 6
0x18002e918  sbb     eax, eax
0x18002e91a  add     eax, r8d
0x18002e91d  mov     [r14+rdx*4], eax
0x18002e921  mov     [rdx+r15], r11b
0x18002e925  jmp     loc_18002E7C2
0x18002e92a  mov     eax, r9d
0x18002e92d  sub     eax, ecx
0x18002e92f  jz      loc_18002E7B6
0x18002e935  sub     eax, 1
0x18002e938  jz      loc_18002E7B6
0x18002e93e  sub     eax, 1
0x18002e941  jz      short loc_18002E94C
0x18002e943  sub     eax, 1
0x18002e946  jnz     loc_18002E841
0x18002e94c  mov     [r14+rdx*4], ecx
0x18002e950  lea     eax, [r9-5]
0x18002e954  jmp     short loc_18002E8E3
0x18002e956  mov     al, [rcx+1CDh]
0x18002e95c  test    al, al
0x18002e95e  jz      loc_18002EF5E
0x18002e964  cmp     byte ptr [rcx+1CEh], 8
0x18002e96b  ja      loc_18002EF5E
0x18002e971  mov     edx, [rbp+arg_50]
0x18002e977  xor     ecx, ecx
0x18002e979  mov     [rbp+var_60], rcx
0x18002e97d  mov     [rbp+var_58], ecx
0x18002e980  mov     [rbp+var_50], rcx
0x18002e984  mov     [rbp+var_48], ecx
0x18002e987  mov     [rbp+var_40], rcx
0x18002e98b  mov     [rbp+var_38], ecx
0x18002e98e  mov     [rbp+var_30], rcx
0x18002e992  mov     [rbp+var_28], ecx
0x18002e995  mov     [rbp+var_20], rcx
0x18002e999  mov     [rbp+var_18], ecx
0x18002e99c  cmp     al, 2
0x18002e99e  jnz     short loc_18002E9C9
0x18002e9a0  test    edx, 0FFFFFFFCh
0x18002e9a6  jnz     short loc_18002E9C9
0x18002e9a8  cmp     edx, 2
0x18002e9ab  jz      short loc_18002E9C9
0x18002e9ad  movzx   ecx, byte ptr [r10+1D0h]
0x18002e9b5  mov     eax, [rdi+rcx*4]
0x18002e9b8  inc     cl
0x18002e9ba  mov     [r10+1D0h], cl
0x18002e9c1  cmp     eax, edx
0x18002e9c3  jnz     loc_18002E8D3
0x18002e9c9  xor     r8d, r8d
0x18002e9cc  mov     [rbp+var_7C], r8d
0x18002e9d0  test    edx, edx
0x18002e9d2  jz      loc_18002EB2D
0x18002e9d8  sub     edx, 1
0x18002e9db  jz      loc_18002EB23
0x18002e9e1  sub     edx, 1
0x18002e9e4  jz      loc_18002EAFB
0x18002e9ea  sub     edx, 1
0x18002e9ed  jz      short loc_18002EA20
0x18002e9ef  cmp     edx, 1
0x18002e9f2  jnz     loc_18002E8D3
0x18002e9f8  movzx   r8d, byte ptr [r10+7]
0x18002e9fd  xor     edx, edx
0x18002e9ff  cmp     edx, r8d
0x18002ea02  jge     loc_18002E8D3
0x18002ea08  movsxd  rax, edx
0x18002ea0b  movzx   ecx, byte ptr [rax+r10+0A4h]
0x18002ea14  cmp     ecx, esi
0x18002ea16  jz      loc_18002E7E9
0x18002ea1c  inc     edx
0x18002ea1e  jmp     short loc_18002E9FF
0x18002ea20  movzx   ebx, byte ptr [r10+3]
0x18002ea25  xor     r11d, r11d
0x18002ea28  test    ebx, ebx
0x18002ea2a  jz      short loc_18002EA4F
0x18002ea2c  movzx   edx, byte ptr [r8+r10+30h]
0x18002ea32  mov     al, [r8+r10+10h]
0x18002ea37  inc     dword ptr [rbp+rdx*4+var_60]
0x18002ea3b  neg     al
0x18002ea3d  sbb     ecx, ecx
0x18002ea3f  inc     r8d
0x18002ea42  neg     ecx
0x18002ea44  inc     ecx
0x18002ea46  add     dword ptr [rbp+rdx*4+var_50], ecx
0x18002ea4a  cmp     r8d, ebx
0x18002ea4d  jl      short loc_18002EA2C
0x18002ea4f  movzx   ebx, byte ptr [r10+4]
0x18002ea54  xor     r8d, r8d
0x18002ea57  test    ebx, ebx
0x18002ea59  jz      short loc_18002EA7E
0x18002ea5b  movzx   edx, byte ptr [r8+r10+60h]
0x18002ea61  mov     al, [r8+r10+40h]
0x18002ea66  inc     dword ptr [rbp+rdx*4+var_60]
0x18002ea6a  neg     al
0x18002ea6c  sbb     ecx, ecx
0x18002ea6e  inc     r8d
0x18002ea71  neg     ecx
0x18002ea73  inc     ecx
0x18002ea75  add     dword ptr [rbp+rdx*4+var_50], ecx
0x18002ea79  cmp     r8d, ebx
0x18002ea7c  jl      short loc_18002EA5B
0x18002ea7e  movzx   ebx, byte ptr [r10+5]
0x18002ea83  xor     r8d, r8d
0x18002ea86  test    ebx, ebx
0x18002ea88  jz      short loc_18002EAB0
0x18002ea8a  movzx   edx, byte ptr [r8+r10+90h]
0x18002ea93  mov     al, [r8+r10+70h]
0x18002ea98  inc     dword ptr [rbp+rdx*4+var_60]
0x18002ea9c  neg     al
0x18002ea9e  sbb     ecx, ecx
0x18002eaa0  inc     r8d
0x18002eaa3  neg     ecx
0x18002eaa5  inc     ecx
0x18002eaa7  add     dword ptr [rbp+rdx*4+var_50], ecx
0x18002eaab  cmp     r8d, ebx
0x18002eaae  jl      short loc_18002EA8A
0x18002eab0  movzx   ebx, byte ptr [r10+6]
0x18002eab5  mov     edx, dword ptr [rbp+var_60]
0x18002eab8  mov     r8d, dword ptr [rbp+var_50]
0x18002eabc  cmp     r11d, ebx
0x18002eabf  jge     loc_18002E8D3
0x18002eac5  movsxd  rax, r11d
0x18002eac8  movzx   ecx, byte ptr [rax+r10+0A0h]
0x18002ead1  cmp     ecx, esi
0x18002ead3  jz      short loc_18002EADF
0x18002ead5  inc     edx
0x18002ead7  inc     r8d
0x18002eada  inc     r11d
0x18002eadd  jmp     short loc_18002EABC
0x18002eadf  movsxd  rcx, r8d
0x18002eae2  mov     [rcx+r13], r9b
0x18002eae6  mov     [r12], dl
0x18002eaea  mov     dword ptr [r14+rcx*4], 4
0x18002eaf2  mov     [rcx+r15], r11b
0x18002eaf6  jmp     loc_18002E7E9
0x18002eafb  movzx   r8d, byte ptr [r10+8]
0x18002eb00  xor     edx, edx
0x18002eb02  cmp     edx, r8d
0x18002eb05  jge     loc_18002E8D3
0x18002eb0b  movsxd  rax, edx
0x18002eb0e  movzx   ecx, byte ptr [rax+r10+0BCh]
0x18002eb17  cmp     ecx, esi
0x18002eb19  jz      loc_18002E7E9
0x18002eb1f  inc     edx
0x18002eb21  jmp     short loc_18002EB02
0x18002eb23  mov     r8d, 1
0x18002eb29  mov     [rbp+var_7C], r8d
0x18002eb2d  movzx   eax, byte ptr [r10+3]
0x18002eb32  xor     r11d, r11d
0x18002eb35  mov     [rbp+var_80], eax
0x18002eb38  cmp     r11d, eax
0x18002eb3b  jge     loc_18002ECAF
0x18002eb41  movsxd  rax, r11d
0x18002eb44  movzx   ebx, byte ptr [rax+r10+10h]
0x18002eb4a  movzx   ecx, byte ptr [rax+r10+30h]
0x18002eb50  cmp     r8d, ebx
0x18002eb53  jnz     loc_18002EC2E
0x18002eb59  movzx   eax, byte ptr [rax+r10+20h]
0x18002eb5f  cmp     eax, esi
  ... truncated ...
```
