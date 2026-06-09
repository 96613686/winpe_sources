# ASN1_Decode_Sequence

- ea: `0x1800574b0`
- end: `0x180057a31`
- name: `ASN1_Decode_Sequence`
- size: `1409`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180055ea8`
- `0x1800565ec`
- `0x180056a94`
- `0x1800572b8`
- `0x1800574b0`
- `0x180057f14`
- `0x180058354`
- `0x1800586c6`
- `0x18005e010`

## string_xrefs

- `0x180057581`: `onecore\ds\security\asn1\ntasn1\ntasn1obj\sequence.c`

## pseudocode

```c
__int64 __fastcall ASN1_Decode_Sequence(_QWORD *a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5, __int64 a6)
{
  _QWORD *v7; // r14
  __int64 v8; // rbx
  _BYTE *v9; // r11
  int v10; // r8d
  int v11; // r13d
  _QWORD *v12; // rdx
  _BYTE *v13; // rcx
  _BYTE *v14; // rdi
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // rcx
  _BYTE *v19; // rax
  unsigned __int64 v20; // rcx
  int v21; // ecx
  __int64 v22; // r10
  __int64 i; // rax
  __int64 v24; // r14
  int v25; // r12d
  int v26; // ecx
  int v27; // r12d
  __int64 (__fastcall *v28)(__int64, __int64, __int64, __int64); // rax
  unsigned __int64 v29; // r12
  int v30; // eax
  int v31; // eax
  int v32; // r8d
  int v33; // ecx
  PVOID *v34; // rcx
  PVOID v35; // rcx
  __int64 v36; // rax
  int v38; // [rsp+48h] [rbp-79h] BYREF
  __int64 v39; // [rsp+50h] [rbp-71h]
  unsigned __int64 v40; // [rsp+58h] [rbp-69h] BYREF
  int v41; // [rsp+60h] [rbp-61h]
  int v42; // [rsp+64h] [rbp-5Dh]
  _BYTE *v43; // [rsp+68h] [rbp-59h] BYREF
  unsigned __int64 v44; // [rsp+70h] [rbp-51h]
  _BYTE *v45; // [rsp+78h] [rbp-49h]
  _BYTE *v46; // [rsp+80h] [rbp-41h]
  __int64 v47; // [rsp+88h] [rbp-39h]
  __int64 v48; // [rsp+90h] [rbp-31h]
  __int128 v49; // [rsp+98h] [rbp-29h]
  _QWORD *v50; // [rsp+A8h] [rbp-19h]
  _QWORD v51[10]; // [rsp+B8h] [rbp-9h] BYREF
  int v53; // [rsp+120h] [rbp+5Fh] BYREF
  unsigned int v54; // [rsp+128h] [rbp+67h]
  __int64 v55; // [rsp+130h] [rbp+6Fh]

  v55 = a4;
  v54 = a3;
  v7 = a1;
  v8 = a4;
  memset_0(&v43, 0, 0x40u);
  v9 = *(_BYTE **)(a2 + 16);
  v10 = *((_DWORD *)v7 + 6);
  v11 = 0;
  v51[0] = v9;
  v40 = 0;
  v53 = 0;
  v41 = 0;
  v38 = 0;
  if ( v10 )
  {
    v15 = ASN1BER_DecExplicitTag(
            a2,
            0x80000000LL,
            v10,
            &v40,
            (_DWORD *)((unsigned __int64)&v38 & -(__int64)((v7[9] & 8) != 0)));
    v16 = v15;
    if ( v15 < 0 )
    {
      v17 = 363;
LABEL_5:
      v18 = (unsigned int)v15;
      goto LABEL_6;
    }
    v12 = (_QWORD *)(a2 + 24);
    v50 = (_QWORD *)(a2 + 24);
    v41 = v38;
    if ( v38 )
    {
      v19 = *(_BYTE **)(a2 + 16);
      v14 = v19 + 2;
      if ( (unsigned __int64)(v19 + 2) > *v12 )
      {
        v16 = -2146881278;
        v17 = 376;
LABEL_10:
        v18 = 2148086018LL;
        goto LABEL_6;
      }
      if ( *v19 || v19[1] )
      {
        v20 = v40;
        v14 = *(_BYTE **)(a2 + 16);
      }
      else
      {
        v20 = 0;
        *(_QWORD *)(a2 + 16) = v14;
        v40 = 0;
        v41 = 0;
      }
      v8 = v55;
      v46 = &v14[v20];
      v43 = v14;
      v45 = v14;
      v44 = v20;
      goto LABEL_18;
    }
    v14 = *(_BYTE **)(a2 + 16);
    v21 = v40;
    v8 = v55;
    HIDWORD(v44) = HIDWORD(v40);
    v43 = v14;
    v46 = &v14[v40];
    *(_QWORD *)(a2 + 16) = &v14[v40];
    v45 = v14;
    LODWORD(v44) = v21;
  }
  else
  {
    v12 = (_QWORD *)(a2 + 24);
    v43 = v9;
    v13 = *(_BYTE **)(a2 + 24);
    v14 = v9;
    v45 = v9;
    v46 = v13;
    v40 = v13 - v9;
    v44 = v13 - v9;
  }
  v50 = v12;
LABEL_18:
  v47 = 0;
  v49 = 0;
  v22 = 0;
  v48 = 0;
  v39 = 0;
  for ( i = 0; ; i = (unsigned int)(v42 + 1) )
  {
    v12 = (_QWORD *)v7[8];
    v42 = i;
    if ( (unsigned int)i >= *((_DWORD *)v12 + 6) )
    {
      if ( !*((_DWORD *)v7 + 6) )
      {
        *(_QWORD *)(a2 + 16) += &v14[-v51[0]];
        if ( *(_QWORD *)(a2 + 16) > *v50 )
        {
          v16 = -2146881278;
          v17 = 613;
          goto LABEL_10;
        }
        return 0;
      }
      if ( v41 )
      {
        v12 = v50;
        *(_QWORD *)(a2 + 16) = v14;
        v16 = *v12 < (unsigned __int64)v14 ? 0x80093102 : 0;
        if ( (__int64)(*v12 - (_QWORD)v14) < 2 )
        {
          v16 = -2146881278;
          goto LABEL_89;
        }
        if ( *v14 || v14[1] )
        {
          v16 = -2146881277;
          goto LABEL_89;
        }
        *(_QWORD *)(a2 + 16) = v14 + 2;
        if ( (unsigned __int64)v14 > *v12 )
        {
LABEL_89:
          v17 = 624;
          v18 = v16;
          goto LABEL_6;
        }
      }
      if ( v46 != v14 )
      {
        v17 = 639;
        goto LABEL_64;
      }
      return 0;
    }
    v38 = 0;
    v24 = v12[4] + 88 * i;
    v25 = *(_DWORD *)(v24 + 28);
    v26 = v25 & 0xE;
    if ( v8 )
    {
      if ( (*(_DWORD *)(v24 + 72) & 4) != 0 )
      {
        v22 = v8;
        v39 = v8;
      }
      else
      {
        v22 = v8 + *(_QWORD *)(v24 + 8);
        v39 = v22;
      }
    }
    v27 = v25 & 1;
    if ( !v26 )
      break;
    if ( v14 < v46 )
    {
      if ( !v11 )
      {
        v15 = ASN1DER_DecPeekTag((__int64)&v43, &v53);
        v16 = v15;
        if ( v15 < 0 )
        {
          v17 = 447;
          goto LABEL_5;
        }
        v14 = v45;
        v11 = v53;
        v8 = v55;
      }
      if ( v27 )
      {
        if ( v11 == *(_DWORD *)(v24 + 32) )
        {
          v11 = 0;
          v53 = 0;
          goto LABEL_43;
        }
      }
      else if ( *(_DWORD *)(v24 + 24) == v11 || !*(_DWORD *)(v24 + 24) )
      {
        v11 = 0;
        v53 = 0;
        goto LABEL_45;
      }
      v22 = v39;
    }
    if ( v22 )
    {
      v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v24 + 80);
      if ( v28 )
      {
        v15 = v28(v24, v22, a5, a6);
        v16 = v15;
        if ( v15 < 0 )
        {
          v17 = 483;
          goto LABEL_5;
        }
        v14 = v45;
        v8 = v55;
        goto LABEL_40;
      }
    }
LABEL_41:
    v7 = a1;
  }
  v53 = 0;
  v11 = 0;
  if ( !v27 )
    goto LABEL_45;
LABEL_43:
  v15 = ASN1BER_DecExplicitTag(
          (__int64)&v43,
          0,
          *(_DWORD *)(v24 + 32),
          &v40,
          (_DWORD *)((unsigned __int64)&v38 & -(__int64)((*(_DWORD *)(v24 + 32) & 0x20000000) != 0)));
  v16 = v15;
  if ( v15 < 0 )
  {
    v17 = 510;
    goto LABEL_5;
  }
  v14 = v45;
  if ( &v45[v40] > v46 )
  {
    v17 = 517;
LABEL_64:
    v16 = -2146881277;
    v18 = 2148086019LL;
    goto LABEL_6;
  }
LABEL_45:
  v29 = (unsigned int)v44;
  v30 = *(_DWORD *)(v24 + 72);
  v40 = (unsigned int)v44;
  if ( (v30 & 1) != 0 )
    v31 = ASN1_Decode_Pointer(v24, (unsigned int)&v43, v54, v39, a5, a6);
  else
    v31 = (*(__int64 (__fastcall **)(__int64, _BYTE **, _QWORD, __int64, __int64, __int64))(*(_QWORD *)(v24 + 64) + 16LL))(
            v24,
            &v43,
            v54,
            v39,
            a5,
            a6);
  v16 = v31;
  if ( v31 < 0 )
  {
    v34 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_ssqPD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v12, v32, *a1, *(_QWORD *)v24, (char)v14, v29, v31);
        v34 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 8) != 0 )
      {
        v35 = v34[2];
        v36 = 256;
        v51[0] = v14;
        if ( v29 < 0x100 )
          v36 = v29;
        v51[1] = v36;
        WPP_SF__HEX_(v35, 12, WPP_54c28acdadbf318fdf603a2d0ae0fcb3_Traceguids, v51);
      }
    }
    return v16;
  }
  v14 = v45;
  if ( !v38 )
    goto LABEL_56;
  v16 = 0;
  if ( v45 > v46 )
    v16 = -2146881278;
  if ( v46 - v45 >= 2 )
  {
    if ( *v45 || v45[1] )
    {
      v16 = -2146881277;
      v18 = 2148086019LL;
      goto LABEL_68;
    }
    v14 = v45 + 2;
    v18 = v16;
    v45 += 2;
    if ( (v16 & 0x80000000) != 0 )
      goto LABEL_68;
LABEL_56:
    v8 = v55;
    if ( !v55 )
      goto LABEL_40;
    v33 = *(_DWORD *)(v24 + 28);
    if ( (v33 & 4) != 0 )
    {
      *(_DWORD *)(v55 + *(_QWORD *)(v24 + 16)) = 1;
      v14 = v45;
LABEL_40:
      v22 = v39;
      goto LABEL_41;
    }
    v22 = v39;
    if ( (v33 & 8) != 0 )
    {
      *(_WORD *)(*(_QWORD *)(v24 + 16) + v55) |= *(_WORD *)(v24 + 56);
      v14 = v45;
    }
    goto LABEL_41;
  }
  v18 = 2148086018LL;
  v16 = -2146881278;
LABEL_68:
  v17 = 581;
LABEL_6:
  DebugTraceError(v18, v12, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1obj\\sequence.c", v17);
  return v16;
}

```

## disassembly

```asm
0x1800574b0  mov     rax, rsp
0x1800574b3  mov     [rax+20h], r9
0x1800574b7  mov     [rax+18h], r8d
0x1800574bb  mov     [rax+8], rcx
0x1800574bf  push    rbp
0x1800574c0  push    rbx
0x1800574c1  push    rsi
0x1800574c2  push    rdi
0x1800574c3  push    r12
0x1800574c5  push    r13
0x1800574c7  push    r14
0x1800574c9  push    r15
0x1800574cb  lea     rbp, [rax-4Fh]
0x1800574cf  sub     rsp, 0C8h
0x1800574d6  mov     rsi, rdx
0x1800574d9  mov     r14, rcx
0x1800574dc  xor     edx, edx; Val
0x1800574de  lea     rcx, [rbp+47h+var_A0]; void *
0x1800574e2  mov     rbx, r9
0x1800574e5  lea     r8d, [rdx+40h]; Size
0x1800574e9  call    memset_0
0x1800574ee  mov     r11, [rsi+10h]
0x1800574f2  xor     r9d, r9d
0x1800574f5  mov     r8d, [r14+18h]
0x1800574f9  xor     r13d, r13d
0x1800574fc  mov     [rbp+47h+var_50], r11
0x180057500  mov     [rbp+47h+var_B0], 0
0x180057508  mov     [rbp+47h+arg_8], r13d
0x18005750c  mov     [rbp+47h+var_A8], r9d
0x180057510  mov     [rbp+47h+var_C0], r9d
0x180057514  test    r8d, r8d
0x180057517  jnz     short loc_180057548
0x180057519  lea     rdx, [rsi+18h]
0x18005751d  mov     [rbp+47h+var_A0], r11
0x180057521  mov     rcx, [rdx]
0x180057524  mov     rdi, r11
0x180057527  mov     rax, rcx
0x18005752a  mov     [rbp+47h+var_90], r11
0x18005752e  sub     rax, r11
0x180057531  mov     [rbp+47h+var_88], rcx
0x180057535  mov     [rbp+47h+var_B0], rax
0x180057539  mov     dword ptr [rbp+47h+var_98], eax
0x18005753c  shr     rax, 20h
0x180057540  mov     dword ptr [rbp+47h+var_98+4], eax
0x180057543  jmp     loc_180057639
0x180057548  mov     eax, [r14+48h]
0x18005754c  lea     r9, [rbp+47h+var_B0]
0x180057550  and     al, 8
0x180057552  mov     edx, 80000000h
0x180057557  neg     al
0x180057559  lea     rax, [rbp+47h+var_C0]
0x18005755d  sbb     rcx, rcx
0x180057560  and     rcx, rax
0x180057563  mov     [rsp+100h+var_E0], rcx
0x180057568  mov     rcx, rsi
0x18005756b  call    ASN1BER_DecExplicitTag
0x180057570  xor     r9d, r9d
0x180057573  mov     ebx, eax
0x180057575  test    eax, eax
0x180057577  jns     short loc_180057592
0x180057579  mov     r9d, 16Bh
0x18005757f  mov     ecx, eax
0x180057581  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180057588  call    DebugTraceError
0x18005758d  jmp     loc_180057A1B
0x180057592  mov     r8d, [rbp+47h+var_C0]
0x180057596  lea     rdx, [rsi+18h]
0x18005759a  mov     [rbp+47h+var_60], rdx
0x18005759e  mov     [rbp+47h+var_A8], r8d
0x1800575a2  test    r8d, r8d
0x1800575a5  jz      short loc_18005760C
0x1800575a7  mov     rax, [rsi+10h]
0x1800575ab  lea     rdi, [rax+2]
0x1800575af  cmp     rdi, [rdx]
0x1800575b2  jbe     short loc_1800575C6
0x1800575b4  mov     ebx, 80093102h
0x1800575b9  mov     r9d, 178h
0x1800575bf  mov     ecx, 80093102h
0x1800575c4  jmp     short loc_180057581
0x1800575c6  cmp     [rax], r9b
0x1800575c9  jnz     short loc_1800575E2
0x1800575cb  cmp     [rax+1], r9b
0x1800575cf  jnz     short loc_1800575E2
0x1800575d1  mov     rcx, r9
0x1800575d4  mov     [rsi+10h], rdi
0x1800575d8  mov     [rbp+47h+var_B0], rcx
0x1800575dc  mov     [rbp+47h+var_A8], r9d
0x1800575e0  jmp     short loc_1800575E9
0x1800575e2  mov     rcx, [rbp+47h+var_B0]
0x1800575e6  mov     rdi, rax
0x1800575e9  mov     rbx, [rbp+47h+arg_18]
0x1800575ed  mov     rax, rcx
0x1800575f0  shr     rax, 20h
0x1800575f4  mov     dword ptr [rbp+47h+var_98+4], eax
0x1800575f7  lea     rax, [rdi+rcx]
0x1800575fb  mov     [rbp+47h+var_88], rax
0x1800575ff  mov     [rbp+47h+var_A0], rdi
0x180057603  mov     [rbp+47h+var_90], rdi
0x180057607  mov     dword ptr [rbp+47h+var_98], ecx
0x18005760a  jmp     short loc_18005763D
0x18005760c  mov     rdi, [rsi+10h]
0x180057610  mov     rcx, [rbp+47h+var_B0]
0x180057614  mov     rbx, [rbp+47h+arg_18]
0x180057618  mov     rax, rcx
0x18005761b  shr     rax, 20h
0x18005761f  mov     dword ptr [rbp+47h+var_98+4], eax
0x180057622  lea     rax, [rdi+rcx]
0x180057626  mov     [rbp+47h+var_A0], rdi
0x18005762a  mov     [rbp+47h+var_88], rax
0x18005762e  mov     [rsi+10h], rax
0x180057632  mov     [rbp+47h+var_90], rdi
0x180057636  mov     dword ptr [rbp+47h+var_98], ecx
0x180057639  mov     [rbp+47h+var_60], rdx
0x18005763d  xorps   xmm0, xmm0
0x180057640  mov     [rbp+47h+var_80], r9
0x180057644  movdqa  [rbp+47h+var_70], xmm0
0x180057649  mov     r10, r9
0x18005764c  mov     [rbp+47h+var_78], r9
0x180057650  mov     r15d, 80093102h
0x180057656  mov     [rbp+47h+var_B8], r9
0x18005765a  mov     eax, r9d
0x18005765d  mov     rdx, [r14+40h]
0x180057661  mov     [rbp+47h+var_A4], eax
0x180057664  cmp     eax, [rdx+18h]
0x180057667  jnb     loc_18005798D
0x18005766d  imul    r14, rax, 58h ; 'X'
0x180057671  mov     [rbp+47h+var_C0], r9d
0x180057675  add     r14, [rdx+20h]
0x180057679  mov     r12d, [r14+1Ch]
0x18005767d  mov     ecx, r12d
0x180057680  and     ecx, 0Eh
0x180057683  test    rbx, rbx
0x180057686  jz      short loc_1800576A4
0x180057688  mov     eax, [r14+48h]
0x18005768c  test    al, 4
0x18005768e  jnz     short loc_18005769D
0x180057690  mov     r10, [r14+8]
0x180057694  add     r10, rbx
0x180057697  mov     [rbp+47h+var_B8], r10
0x18005769b  jmp     short loc_1800576A4
0x18005769d  mov     r10, rbx
0x1800576a0  mov     [rbp+47h+var_B8], rbx
0x1800576a4  and     r12d, 1
0x1800576a8  test    ecx, ecx
0x1800576aa  jz      loc_180057759
0x1800576b0  cmp     rdi, [rbp+47h+var_88]
0x1800576b4  jnb     short loc_180057711
0x1800576b6  test    r13d, r13d
0x1800576b9  jnz     short loc_1800576E1
0x1800576bb  lea     rdx, [rbp+47h+arg_8]
0x1800576bf  lea     rcx, [rbp+47h+var_A0]
0x1800576c3  call    ASN1DER_DecPeekTag
0x1800576c8  xor     r9d, r9d
0x1800576cb  mov     ebx, eax
0x1800576cd  test    eax, eax
0x1800576cf  js      loc_1800578AE
0x1800576d5  mov     rdi, [rbp+47h+var_90]
0x1800576d9  mov     r13d, [rbp+47h+arg_8]
0x1800576dd  mov     rbx, [rbp+47h+arg_18]
0x1800576e1  test    r12d, r12d
0x1800576e4  jz      short loc_1800576F5
0x1800576e6  cmp     r13d, [r14+20h]
0x1800576ea  jnz     short loc_18005770D
0x1800576ec  mov     r13d, r9d
0x1800576ef  mov     [rbp+47h+arg_8], r9d
0x1800576f3  jmp     short loc_180057765
0x1800576f5  cmp     [r14+18h], r13d
0x1800576f9  jz      short loc_180057701
0x1800576fb  cmp     [r14+18h], r9d
0x1800576ff  jnz     short loc_18005770D
0x180057701  mov     r13d, r9d
0x180057704  mov     [rbp+47h+arg_8], r9d
0x180057708  jmp     loc_1800577B0
0x18005770d  mov     r10, [rbp+47h+var_B8]
0x180057711  test    r10, r10
0x180057714  jz      short loc_18005774B
0x180057716  mov     rax, [r14+50h]
0x18005771a  test    rax, rax
0x18005771d  jz      short loc_18005774B
0x18005771f  mov     r9, [rbp+47h+arg_28]
0x180057723  mov     rdx, r10
0x180057726  mov     r8, [rbp+47h+arg_20]
0x18005772a  mov     rcx, r14
0x18005772d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057732  xor     r9d, r9d
0x180057735  mov     ebx, eax
0x180057737  test    eax, eax
0x180057739  js      loc_1800578B9
0x18005773f  mov     rdi, [rbp+47h+var_90]
0x180057743  mov     rbx, [rbp+47h+arg_18]
0x180057747  mov     r10, [rbp+47h+var_B8]
0x18005774b  mov     eax, [rbp+47h+var_A4]
0x18005774e  mov     r14, [rbp+47h+arg_0]
0x180057752  inc     eax
0x180057754  jmp     loc_18005765D
0x180057759  mov     [rbp+47h+arg_8], r9d
0x18005775d  mov     r13d, r9d
0x180057760  test    r12d, r12d
0x180057763  jz      short loc_1800577B0
0x180057765  mov     r8d, [r14+20h]
0x180057769  lea     r9, [rbp+47h+var_B0]
0x18005776d  mov     eax, r8d
0x180057770  and     eax, 20000000h
0x180057775  neg     eax
0x180057777  lea     rax, [rbp+47h+var_C0]
0x18005777b  sbb     rcx, rcx
0x18005777e  xor     edx, edx
0x180057780  and     rcx, rax
0x180057783  mov     [rsp+100h+var_E0], rcx
0x180057788  lea     rcx, [rbp+47h+var_A0]
0x18005778c  call    ASN1BER_DecExplicitTag
0x180057791  mov     ebx, eax
0x180057793  test    eax, eax
0x180057795  js      loc_1800578D9
0x18005779b  mov     rdi, [rbp+47h+var_90]
0x18005779f  mov     rcx, [rbp+47h+var_B0]
0x1800577a3  add     rcx, rdi
0x1800577a6  cmp     rcx, [rbp+47h+var_88]
0x1800577aa  ja      loc_1800578C4
0x1800577b0  mov     r12d, dword ptr [rbp+47h+var_98]
0x1800577b4  lea     rdx, [rbp+47h+var_A0]
0x1800577b8  mov     eax, [r14+48h]
0x1800577bc  mov     r9, [rbp+47h+var_B8]
0x1800577c0  mov     r8d, [rbp+47h+arg_10]
0x1800577c4  mov     [rbp+47h+var_B0], r12
0x1800577c8  test    al, 1
0x1800577ca  jz      short loc_1800577E8
0x1800577cc  mov     rax, [rbp+47h+arg_28]
0x1800577d0  mov     rcx, r14
0x1800577d3  mov     [rsp+100h+var_D8], rax
0x1800577d8  mov     rax, [rbp+47h+arg_20]
0x1800577dc  mov     [rsp+100h+var_E0], rax
0x1800577e1  call    ASN1_Decode_Pointer
0x1800577e6  jmp     short loc_18005780A
0x1800577e8  mov     rcx, [rbp+47h+arg_28]
0x1800577ec  mov     rax, [r14+40h]
0x1800577f0  mov     [rsp+100h+var_D8], rcx
0x1800577f5  mov     rcx, [rbp+47h+arg_20]
0x1800577f9  mov     [rsp+100h+var_E0], rcx
0x1800577fe  mov     rcx, r14
0x180057801  mov     rax, [rax+10h]
0x180057805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005780a  xor     r9d, r9d
0x18005780d  mov     ebx, eax
0x18005780f  test    eax, eax
0x180057811  js      loc_1800578FE
0x180057817  mov     rdi, [rbp+47h+var_90]
0x18005781b  cmp     [rbp+47h+var_C0], r9d
0x18005781f  jz      short loc_180057861
0x180057821  mov     rax, [rbp+47h+var_88]
0x180057825  mov     ebx, r9d
0x180057828  cmp     rdi, rax
0x18005782b  cmova   ebx, r15d
0x18005782f  sub     rax, rdi
0x180057832  cmp     rax, 2
0x180057836  jl      loc_1800578ED
0x18005783c  cmp     [rdi], r9b
0x18005783f  jnz     loc_1800578E4
0x180057845  cmp     [rdi+1], r9b
0x180057849  jnz     loc_1800578E4
0x18005784f  add     rdi, 2
0x180057853  mov     ecx, ebx
0x180057855  mov     [rbp+47h+var_90], rdi
0x180057859  test    ebx, ebx
0x18005785b  js      loc_1800578F3
0x180057861  mov     rbx, [rbp+47h+arg_18]
0x180057865  test    rbx, rbx
0x180057868  jz      loc_180057747
0x18005786e  mov     ecx, [r14+1Ch]
0x180057872  test    cl, 4
0x180057875  jz      short loc_18005788B
0x180057877  mov     rax, [r14+10h]
0x18005787b  mov     dword ptr [rbx+rax], 1
0x180057882  mov     rdi, [rbp+47h+var_90]
0x180057886  jmp     loc_180057747
0x18005788b  mov     r10, [rbp+47h+var_B8]
0x18005788f  test    cl, 8
0x180057892  jz      loc_18005774B
0x180057898  mov     rcx, [r14+10h]
0x18005789c  movzx   eax, word ptr [r14+38h]
0x1800578a1  or      [rcx+rbx], ax
0x1800578a5  mov     rdi, [rbp+47h+var_90]
0x1800578a9  jmp     loc_18005774B
0x1800578ae  mov     r9d, 1BFh
0x1800578b4  jmp     loc_18005757F
0x1800578b9  mov     r9d, 1E3h
0x1800578bf  jmp     loc_18005757F
0x1800578c4  mov     r9d, 205h
0x1800578ca  mov     ebx, 80093103h
0x1800578cf  mov     ecx, 80093103h
0x1800578d4  jmp     loc_180057581
0x1800578d9  mov     r9d, 1FEh
0x1800578df  jmp     loc_18005757F
0x1800578e4  mov     ebx, 80093103h
0x1800578e9  mov     ecx, ebx
0x1800578eb  jmp     short loc_1800578F3
0x1800578ed  mov     ecx, r15d
0x1800578f0  mov     ebx, r15d
0x1800578f3  mov     r9d, 245h
0x1800578f9  jmp     loc_180057581
  ... truncated ...
```
