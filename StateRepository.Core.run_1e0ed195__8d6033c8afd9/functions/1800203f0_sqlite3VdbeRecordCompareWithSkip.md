# sqlite3VdbeRecordCompareWithSkip

- ea: `0x1800203f0`
- end: `0x1800209e1`
- name: `sqlite3VdbeRecordCompareWithSkip`
- size: `1521`
- prototype: ``
- caller_count: `9`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001e760`
- `0x1800200b0`
- `0x180020210`
- `0x180020220`
- `0x18002a050`
- `0x18005fc6c`
- `0x1800892dc`
- `0x180094330`
- `0x180094564`

## callees

- `0x1800203f0`
- `0x180020a94`
- `0x180020bf0`
- `0x180020d40`
- `0x180020d70`
- `0x180020d90`
- `0x180060134`
- `0x180072204`
- `0x18007f8f0`
- `0x180084768`
- `0x180099808`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeRecordCompareWithSkip(unsigned int a1, unsigned __int8 *a2, __int64 *a3, int a4)
{
  __int64 v4; // rsi
  unsigned int v7; // r10d
  __int64 v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // r14d
  int v11; // r8d
  unsigned int v12; // edx
  int v13; // r11d
  unsigned __int8 *v14; // rcx
  unsigned int v15; // ebx
  bool v16; // zf
  unsigned __int8 *v17; // r8
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  signed __int64 v20; // rdx
  int v21; // eax
  unsigned int v22; // r10d
  int v23; // eax
  int v24; // edx
  unsigned int v25; // edx
  char v26; // r8
  __int64 result; // rax
  unsigned int v28; // r12d
  __int64 v29; // r8
  unsigned int v30; // edx
  __int64 v31; // rcx
  signed int v32; // eax
  unsigned __int8 Varint32; // al
  int v34; // ecx
  unsigned __int8 v35; // al
  __int64 v36; // rdx
  unsigned __int8 *v37; // rcx
  int v38; // edx
  int v39; // eax
  unsigned int v40; // [rsp+20h] [rbp-48h]
  __int128 v41; // [rsp+28h] [rbp-40h] BYREF
  __int128 v42; // [rsp+38h] [rbp-30h]
  __int128 v43; // [rsp+48h] [rbp-20h]
  __int64 v44; // [rsp+58h] [rbp-10h]
  int v46; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v47; // [rsp+C0h] [rbp+58h] BYREF
  int v48; // [rsp+C8h] [rbp+60h]

  v4 = a3[1];
  v44 = 0;
  v7 = a1;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( a4 )
  {
    v8 = a2[1];
    v46 = v8;
    if ( (unsigned int)v8 >= 0x80 )
    {
      Varint32 = sqlite3GetVarint32(a2 + 1, &v46);
      v7 = a1;
      v34 = Varint32;
      v8 = (unsigned int)v46;
      v48 = v34 + 1;
    }
    else
    {
      v48 = 2;
    }
    v40 = *a2;
    if ( (unsigned int)v8 >= 0x80 )
      v9 = (unsigned int)(v8 - 12) >> 1;
    else
      v9 = *((unsigned __int8 *)qword_18009EF00 + v8);
    v10 = *a2 + v9;
    v11 = 1;
    v4 += 56;
  }
  else
  {
    v30 = *a2;
    v40 = v30;
    v46 = v30;
    if ( v30 >= 0x80 )
    {
      v35 = sqlite3GetVarint32(a2, &v46);
      v30 = v46;
      v7 = a1;
      v48 = v35;
      v40 = v46;
    }
    else
    {
      v48 = 1;
    }
    v10 = v30;
    v11 = 0;
  }
  v46 = v11;
  if ( v10 > v7 )
  {
    v36 = 89731;
LABEL_75:
    *((_BYTE *)a3 + 31) = sqlite3ReportError(11, v36, "database corruption");
    return 0;
  }
  v12 = v48;
  v13 = -1;
  while ( 1 )
  {
    v14 = &a2[v12];
    if ( (*(_BYTE *)(v4 + 20) & 0x24) != 0 )
    {
      v15 = *v14;
      v16 = v15 == 10;
      if ( v15 < 0xA )
      {
        if ( !*v14 )
          goto LABEL_25;
        v17 = &a2[v10];
        if ( v15 == 7 )
        {
          serialGet7(&a2[v10], &v41);
          v25 = -(int)sqlite3IntFloatCompare(*(_QWORD *)v4);
          goto LABEL_28;
        }
        if ( v15 == 1 )
        {
          v20 = (char)*v17;
        }
        else
        {
          switch ( v15 )
          {
            case 2u:
              v18 = (char)*v17 << 8;
              v19 = v17[1];
              break;
            case 3u:
              v19 = v17[2];
              v18 = ((char)*v17 << 16) | ((unsigned __int64)v17[1] << 8);
              break;
            case 4u:
              v20 = (*v17 << 24) | v17[3] | ((v17[2] | (v17[1] << 8)) << 8);
              goto LABEL_17;
            case 5u:
              v20 = ((v17[1] | (unsigned __int64)((char)*v17 << 8)) << 32)
                  + (v17[5] | ((v17[4] | ((v17[3] | ((unsigned __int64)v17[2] << 8)) << 8)) << 8));
              goto LABEL_17;
            case 6u:
              v19 = v17[7];
              v18 = (v17[6]
                   | ((v17[5]
                     | ((v17[4] | ((v17[3] | ((v17[2] | ((((unsigned __int64)*v17 << 8) | v17[1]) << 8)) << 8)) << 8)) << 8)) << 8)) << 8;
              break;
            default:
              v20 = v15 - 8;
              goto LABEL_17;
          }
          v20 = v19 | v18;
        }
LABEL_17:
        if ( v20 > *(_QWORD *)v4 )
        {
          v25 = 1;
          goto LABEL_28;
        }
        if ( v20 < *(_QWORD *)v4 )
          goto LABEL_25;
        goto LABEL_19;
      }
LABEL_76:
      v25 = v13;
      if ( !v16 )
        v25 = 1;
      goto LABEL_28;
    }
    if ( (*(_BYTE *)(v4 + 20) & 8) != 0 )
    {
      v15 = *v14;
      v16 = (_BYTE)v15 == 10;
      if ( (unsigned __int8)v15 < 0xAu )
      {
        if ( !(_BYTE)v15 )
          goto LABEL_25;
        v37 = &a2[v10];
        if ( (_BYTE)v15 != 7 )
        {
          sqlite3VdbeSerialGet(v37, v15, &v41);
          v25 = sqlite3IntFloatCompare(v41);
          goto LABEL_28;
        }
        if ( (unsigned int)serialGet7(v37, &v41) || *(double *)v4 > *(double *)&v41 )
          goto LABEL_25;
        if ( *(double *)&v41 > *(double *)v4 )
          goto LABEL_55;
        goto LABEL_19;
      }
      goto LABEL_76;
    }
    v16 = (*(_BYTE *)(v4 + 20) & 2) == 0;
    v15 = *v14;
    v47 = v15;
    if ( !v16 )
    {
      if ( v15 >= 0x80 )
      {
        sqlite3GetVarint32(v14, &v47);
        v7 = a1;
        v13 = -1;
        v15 = v47;
      }
      if ( v15 < 0xC )
      {
LABEL_25:
        v25 = v13;
        goto LABEL_29;
      }
      if ( (v15 & 1) == 0 )
        goto LABEL_55;
      v28 = (v15 - 12) >> 1;
      LODWORD(v42) = v28;
      if ( v28 + v10 > v7 || (v29 = *a3, *(unsigned __int16 *)(*a3 + 8) <= v46) )
      {
        v36 = 89812;
        goto LABEL_75;
      }
      if ( !*(_QWORD *)(v29 + 8LL * v46 + 32) )
      {
        v31 = v10;
        goto LABEL_63;
      }
      BYTE6(v42) = *(_BYTE *)(v29 + 4);
      *((_QWORD *)&v42 + 1) = *(_QWORD *)(v29 + 16);
      WORD2(v42) = 2;
      *((_QWORD *)&v41 + 1) = &a2[v10];
      v25 = vdbeCompareMemString(&v41, v4, *(_QWORD *)(v29 + 8LL * v46 + 32), (char *)a3 + 31);
LABEL_28:
      if ( v25 )
        goto LABEL_29;
LABEL_19:
      v11 = v46;
      goto LABEL_20;
    }
    if ( (*(_BYTE *)(v4 + 20) & 0x10) != 0 )
      break;
    if ( (_BYTE)v15 && (_BYTE)v15 != 10 )
    {
      if ( (_BYTE)v15 != 7 || !(unsigned int)serialGet7(&a2[v10], &v41) )
      {
LABEL_55:
        v25 = 1;
        goto LABEL_29;
      }
      goto LABEL_19;
    }
LABEL_20:
    v21 = *((unsigned __int16 *)a3 + 14);
    v46 = v11 + 1;
    if ( v11 + 1 == v21 || (v10 += sqlite3VdbeSerialTypeLen(v15), v10 > v22) )
    {
      result = (unsigned int)*((char *)a3 + 30);
      *((_BYTE *)a3 + 34) = 1;
      return result;
    }
    v23 = sqlite3VarintLen(v15);
    v12 = v23 + v24;
    v48 = v12;
    if ( v12 >= v40 )
    {
      v36 = 89893;
      goto LABEL_75;
    }
    v4 += 56;
  }
  if ( v15 >= 0x80 )
  {
    sqlite3GetVarint32(v14, &v47);
    v7 = a1;
    v13 = -1;
    v15 = v47;
  }
  if ( v15 < 0xC || (v15 & 1) != 0 )
  {
    v25 = v13;
    goto LABEL_28;
  }
  v28 = (v15 - 12) >> 1;
  if ( v28 + v10 > v7 )
  {
    v36 = 89842;
    goto LABEL_75;
  }
  v31 = v10;
  if ( (*(_WORD *)(v4 + 20) & 0x400) == 0 )
  {
LABEL_63:
    v32 = *(_DWORD *)(v4 + 16);
    if ( (int)v28 < v32 )
      v32 = v28;
    v25 = memcmp_0(&a2[v31], *(const void **)(v4 + 8), v32);
    if ( v25 )
      goto LABEL_29;
    v25 = v28 - *(_DWORD *)(v4 + 16);
    goto LABEL_28;
  }
  if ( (unsigned int)isAllZero(&a2[v10], v28) )
  {
    v25 = v38 - *(_DWORD *)v4;
    goto LABEL_28;
  }
  v25 = 1;
LABEL_29:
  v26 = *(_BYTE *)(*(_QWORD *)(*a3 + 24) + v46);
  if ( v26 )
  {
    if ( (v26 & 2) == 0 )
      return -v25;
    v39 = !v15 || (*(_BYTE *)(v4 + 20) & 1) != 0;
    if ( (v26 & 1) != v39 )
      return -v25;
  }
  return v25;
}

```

## disassembly

```asm
0x1800203f0  mov     [rsp-40h+arg_0], ecx
0x1800203f4  push    rbp
0x1800203f5  push    rbx
0x1800203f6  push    rsi
0x1800203f7  push    rdi
0x1800203f8  push    r12
0x1800203fa  push    r13
0x1800203fc  push    r14
0x1800203fe  push    r15
0x180020400  mov     rbp, rsp
0x180020403  sub     rsp, 68h
0x180020407  mov     rsi, [r8+8]
0x18002040b  xor     eax, eax
0x18002040d  mov     [rbp+var_10], rax
0x180020411  xorps   xmm0, xmm0
0x180020414  mov     r15, r8
0x180020417  mov     r13, rdx
0x18002041a  mov     r10d, ecx
0x18002041d  lea     ebx, [rax+2]
0x180020420  lea     r12d, [rbx+7Eh]
0x180020424  lea     edi, [rax+1]
0x180020427  movups  [rbp+var_40], xmm0
0x18002042b  movups  [rbp+var_30], xmm0
0x18002042f  movups  [rbp+var_20], xmm0
0x180020433  test    r9d, r9d
0x180020436  jz      loc_18002064C
0x18002043c  lea     rcx, [rdx+1]
0x180020440  movzx   eax, byte ptr [rcx]
0x180020443  mov     [rbp+arg_8], eax
0x180020446  cmp     eax, r12d
0x180020449  jnb     loc_180020865
0x18002044f  mov     [rbp+arg_18], ebx
0x180020452  movzx   edx, byte ptr [r13+0]
0x180020457  mov     [rbp+var_48], edx
0x18002045a  cmp     eax, r12d
0x18002045d  jnb     loc_18002054A
0x180020463  lea     rcx, qword_18009EF00
0x18002046a  movzx   eax, byte ptr [rax+rcx]
0x18002046e  lea     r14d, [rdx+rax]
0x180020472  mov     r8d, edi
0x180020475  add     rsi, 38h ; '8'
0x180020479  mov     [rbp+arg_8], r8d
0x18002047d  cmp     r14d, r10d
0x180020480  ja      loc_1800208A3
0x180020486  mov     edx, [rbp+arg_18]
0x180020489  or      r11d, 0FFFFFFFFh
0x18002048d  mov     ecx, edx
0x18002048f  add     rcx, r13
0x180020492  test    byte ptr [rsi+14h], 24h
0x180020496  jz      loc_18002059B
0x18002049c  movzx   ebx, byte ptr [rcx]
0x18002049f  cmp     ebx, 0Ah
0x1800204a2  jnb     loc_1800208CB
0x1800204a8  test    ebx, ebx
0x1800204aa  jz      loc_180020554
0x1800204b0  mov     r8d, r14d
0x1800204b3  add     r8, r13
0x1800204b6  cmp     ebx, 7
0x1800204b9  jz      loc_1800208D6
0x1800204bf  mov     eax, ebx
0x1800204c1  test    ebx, ebx
0x1800204c3  jz      loc_180020643
0x1800204c9  sub     eax, 1
0x1800204cc  jz      loc_180020643
0x1800204d2  sub     eax, 1
0x1800204d5  jnz     loc_18002066C
0x1800204db  movsx   eax, byte ptr [r8]
0x1800204df  shl     eax, 8
0x1800204e2  movsxd  rdx, eax
0x1800204e5  movzx   eax, byte ptr [r8+1]
0x1800204ea  or      rdx, rax
0x1800204ed  cmp     rdx, [rsi]
0x1800204f0  jg      short loc_18002055F
0x1800204f2  jl      short loc_180020554
0x1800204f4  mov     r8d, [rbp+arg_8]
0x1800204f8  mov     edx, [rbp+arg_18]
0x1800204fb  movzx   eax, word ptr [r15+1Ch]
0x180020500  add     r8d, edi
0x180020503  mov     [rbp+arg_8], r8d
0x180020507  cmp     r8d, eax
0x18002050a  jz      loc_1800206D2
0x180020510  mov     ecx, ebx
0x180020512  call    sqlite3VdbeSerialTypeLen
0x180020517  add     r14d, eax
0x18002051a  cmp     r14d, r10d
0x18002051d  ja      loc_1800206D2
0x180020523  mov     ecx, ebx
0x180020525  call    sqlite3VarintLen
0x18002052a  add     edx, eax
0x18002052c  mov     [rbp+arg_18], edx
0x18002052f  cmp     edx, [rbp+var_48]
0x180020532  jnb     loc_1800208AA
0x180020538  mov     ebx, 2
0x18002053d  add     rsi, 38h ; '8'
0x180020541  lea     r12d, [rbx+7Eh]
0x180020545  jmp     loc_18002048D
0x18002054a  add     eax, 0FFFFFFF4h
0x18002054d  shr     eax, 1
0x18002054f  jmp     loc_18002046E
0x180020554  mov     edx, r11d
0x180020557  mov     r12d, 2
0x18002055d  jmp     short loc_18002056F
0x18002055f  mov     edx, edi
0x180020561  mov     r12d, 2
0x180020567  test    edx, edx
0x180020569  jz      loc_180020991
0x18002056f  mov     rax, [r15]
0x180020572  movsxd  rcx, [rbp+arg_8]
0x180020576  mov     rax, [rax+18h]
0x18002057a  movzx   r8d, byte ptr [rax+rcx]
0x18002057f  test    r8d, r8d
0x180020582  jnz     loc_1800209B9
0x180020588  mov     eax, edx
0x18002058a  add     rsp, 68h
0x18002058e  pop     r15
0x180020590  pop     r14
0x180020592  pop     r13
0x180020594  pop     r12
0x180020596  pop     rdi
0x180020597  pop     rsi
0x180020598  pop     rbx
0x180020599  pop     rbp
0x18002059a  retn
0x18002059b  test    byte ptr [rsi+14h], 8
0x18002059f  jnz     loc_1800208F8
0x1800205a5  test    [rsi+14h], bl
0x1800205a8  movzx   ebx, byte ptr [rcx]
0x1800205ab  mov     [rbp+arg_10], ebx
0x1800205ae  jz      loc_180020698
0x1800205b4  cmp     ebx, r12d
0x1800205b7  jnb     loc_1800206E0
0x1800205bd  cmp     ebx, 0Ch
0x1800205c0  jb      short loc_180020554
0x1800205c2  test    dil, bl
0x1800205c5  jz      loc_1800206CB
0x1800205cb  lea     r12d, [rbx-0Ch]
0x1800205cf  shr     r12d, 1
0x1800205d2  mov     dword ptr [rbp+var_30], r12d
0x1800205d6  lea     eax, [r12+r14]
0x1800205da  cmp     eax, r10d
0x1800205dd  ja      loc_18002099E
0x1800205e3  mov     r8, [r15]
0x1800205e6  movsxd  rcx, [rbp+arg_8]
0x1800205ea  movzx   eax, word ptr [r8+8]
0x1800205ef  cmp     eax, ecx
0x1800205f1  jle     loc_18002099E
0x1800205f7  cmp     qword ptr [r8+rcx*8+20h], 0
0x1800205fd  jz      loc_180020965
0x180020603  mov     al, [r8+4]
0x180020607  lea     r9, [r15+1Fh]
0x18002060b  mov     byte ptr [rbp+var_30+6], al
0x18002060e  mov     r12d, 2
0x180020614  mov     rax, [r8+10h]
0x180020618  mov     rdx, rsi
0x18002061b  mov     qword ptr [rbp+var_30+8], rax
0x18002061f  mov     word ptr [rbp+var_30+4], r12w
0x180020624  mov     eax, r14d
0x180020627  add     rax, r13
0x18002062a  mov     qword ptr [rbp+var_40+8], rax
0x18002062e  mov     r8, [r8+rcx*8+20h]
0x180020633  lea     rcx, [rbp+var_40]
0x180020637  call    vdbeCompareMemString
0x18002063c  mov     edx, eax
0x18002063e  jmp     loc_180020567
0x180020643  movsx   rdx, byte ptr [r8]
0x180020647  jmp     loc_1800204ED
0x18002064c  movzx   edx, byte ptr [rdx]
0x18002064f  mov     [rbp+var_48], edx
0x180020652  mov     [rbp+arg_8], edx
0x180020655  cmp     edx, r12d
0x180020658  jnb     loc_180020882
0x18002065e  mov     [rbp+arg_18], edi
0x180020661  mov     r14d, edx
0x180020664  xor     r8d, r8d
0x180020667  jmp     loc_180020479
0x18002066c  sub     eax, 1
0x18002066f  jz      loc_18002077A
0x180020675  sub     eax, 1
0x180020678  jz      loc_18002083B
0x18002067e  sub     eax, 1
0x180020681  jz      loc_18002079A
0x180020687  cmp     eax, 1
0x18002068a  jz      loc_1800207E1
0x180020690  lea     edx, [rbx-8]
0x180020693  jmp     loc_1800204ED
0x180020698  test    byte ptr [rsi+14h], 10h
0x18002069c  jnz     short loc_1800206F9
0x18002069e  test    bl, bl
0x1800206a0  jz      loc_1800204FB
0x1800206a6  cmp     bl, 0Ah
0x1800206a9  jz      loc_1800204FB
0x1800206af  cmp     bl, 7
0x1800206b2  jnz     short loc_1800206CB
0x1800206b4  mov     ecx, r14d
0x1800206b7  lea     rdx, [rbp+var_40]
0x1800206bb  add     rcx, r13
0x1800206be  call    serialGet7
0x1800206c3  test    eax, eax
0x1800206c5  jnz     loc_1800204F4
0x1800206cb  mov     edx, edi
0x1800206cd  jmp     loc_180020557
0x1800206d2  movsx   eax, byte ptr [r15+1Eh]
0x1800206d7  mov     [r15+22h], dil
0x1800206db  jmp     loc_18002058A
0x1800206e0  lea     rdx, [rbp+arg_10]
0x1800206e4  call    sqlite3GetVarint32
0x1800206e9  mov     r10d, [rbp+arg_0]
0x1800206ed  or      r11d, 0FFFFFFFFh
0x1800206f1  mov     ebx, [rbp+arg_10]
0x1800206f4  jmp     loc_1800205BD
0x1800206f9  cmp     ebx, r12d
0x1800206fc  jnb     short loc_180020764
0x1800206fe  cmp     ebx, 0Ch
0x180020701  jb      loc_180020989
0x180020707  test    dil, bl
0x18002070a  jnz     loc_180020989
0x180020710  lea     r12d, [rbx-0Ch]
0x180020714  shr     r12d, 1
0x180020717  lea     eax, [r12+r14]
0x18002071b  cmp     eax, r10d
0x18002071e  ja      loc_1800209AF
0x180020724  mov     eax, 400h
0x180020729  mov     ecx, r14d
0x18002072c  test    [rsi+14h], ax
0x180020730  jnz     loc_18002096D
0x180020736  mov     eax, [rsi+10h]
0x180020739  cmp     r12d, eax
0x18002073c  mov     rdx, [rsi+8]; Buf2
0x180020740  cmovl   eax, r12d
0x180020744  add     rcx, r13; Buf1
0x180020747  movsxd  r8, eax; Size
0x18002074a  call    memcmp_0
0x18002074f  mov     edx, eax
0x180020751  test    eax, eax
0x180020753  jnz     loc_180020557
0x180020759  mov     edx, r12d
0x18002075c  sub     edx, [rsi+10h]
0x18002075f  jmp     loc_180020561
0x180020764  lea     rdx, [rbp+arg_10]
0x180020768  call    sqlite3GetVarint32
0x18002076d  mov     r10d, [rbp+arg_0]
0x180020771  or      r11d, 0FFFFFFFFh
0x180020775  mov     ebx, [rbp+arg_10]
0x180020778  jmp     short loc_1800206FE
0x18002077a  movsx   eax, byte ptr [r8]
0x18002077e  movzx   edx, byte ptr [r8+1]
0x180020783  shl     eax, 10h
0x180020786  movsxd  rcx, eax
0x180020789  movzx   eax, byte ptr [r8+2]
0x18002078e  shl     rdx, 8
0x180020792  or      rdx, rcx
0x180020795  jmp     loc_1800204EA
0x18002079a  movzx   eax, byte ptr [r8+3]
0x18002079f  movzx   edx, byte ptr [r8+2]
0x1800207a4  shl     rdx, 8
0x1800207a8  or      rdx, rax
0x1800207ab  movzx   eax, byte ptr [r8+4]
0x1800207b0  shl     rdx, 8
0x1800207b4  or      rdx, rax
0x1800207b7  movzx   eax, byte ptr [r8+5]
0x1800207bc  shl     rdx, 8
0x1800207c0  or      rdx, rax
0x1800207c3  movsx   eax, byte ptr [r8]
0x1800207c7  shl     eax, 8
0x1800207ca  movsxd  rcx, eax
0x1800207cd  movzx   eax, byte ptr [r8+1]
0x1800207d2  or      rcx, rax
0x1800207d5  shl     rcx, 20h
0x1800207d9  add     rdx, rcx
0x1800207dc  jmp     loc_1800204ED
0x1800207e1  movzx   eax, byte ptr [r8]
0x1800207e5  movzx   edx, byte ptr [r8+1]
0x1800207ea  shl     rax, 8
0x1800207ee  or      rdx, rax
0x1800207f1  movzx   eax, byte ptr [r8+2]
0x1800207f6  shl     rdx, 8
0x1800207fa  or      rdx, rax
0x1800207fd  movzx   eax, byte ptr [r8+3]
0x180020802  shl     rdx, 8
0x180020806  or      rdx, rax
0x180020809  movzx   eax, byte ptr [r8+4]
0x18002080e  shl     rdx, 8
0x180020812  or      rdx, rax
0x180020815  movzx   eax, byte ptr [r8+5]
0x18002081a  shl     rdx, 8
0x18002081e  or      rdx, rax
0x180020821  movzx   eax, byte ptr [r8+6]
0x180020826  shl     rdx, 8
0x18002082a  or      rdx, rax
0x18002082d  movzx   eax, byte ptr [r8+7]
0x180020832  shl     rdx, 8
0x180020836  jmp     loc_1800204EA
0x18002083b  movzx   eax, byte ptr [r8+2]
0x180020840  movzx   ecx, byte ptr [r8+1]
0x180020845  shl     ecx, 8
0x180020848  or      ecx, eax
0x18002084a  movzx   eax, byte ptr [r8+3]
0x18002084f  shl     ecx, 8
0x180020852  or      ecx, eax
0x180020854  movzx   eax, byte ptr [r8]
  ... truncated ...
```
