# AeComputeProgramIdentityHash

- ea: `0x1800535ec`
- end: `0x180053f10`
- name: `AeComputeProgramIdentityHash`
- size: `2340`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800e2500`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18000d62c`
- `0x180052798`
- `0x1800535ec`
- `0x180053f18`
- `0x180054974`
- `0x1800549f0`
- `0x180054a54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800539cd`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800539cd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180053a75`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180053a75`

## string_xrefs

- `0x180053e5f`: `AeComputeProgramIdentityHash`
- `0x180053ec4`: `AeComputeProgramIdentityHash`

## pseudocode

```c
__int64 __fastcall AeComputeProgramIdentityHash(unsigned __int16 **a1, _DWORD *a2)
{
  int v4; // r8d
  unsigned __int16 *v5; // rax
  unsigned __int64 v6; // r11
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned __int64 v9; // r8
  __int64 v10; // r15
  unsigned __int64 v11; // r12
  unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rax
  __int64 v14; // r9
  unsigned __int16 v15; // r11
  unsigned __int16 *v16; // r10
  __int64 v17; // rdx
  unsigned __int16 *v18; // rcx
  unsigned __int16 *v19; // rax
  __int64 v20; // r9
  unsigned __int16 v21; // r11
  unsigned __int16 *v22; // r10
  __int64 v23; // rdx
  unsigned __int16 *v24; // rcx
  unsigned __int16 *v25; // rax
  unsigned __int64 v26; // r9
  unsigned __int16 v27; // r11
  unsigned __int16 *v28; // r10
  unsigned __int64 v29; // rcx
  int v30; // eax
  _BYTE *v31; // rcx
  int v32; // edx
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  unsigned __int16 *v36; // rax
  __int64 v37; // r13
  unsigned int i; // ebx
  __int64 v39; // rcx
  int v40; // eax
  int v41; // edx
  int v42; // r13d
  const wchar_t *v43; // rbx
  const wchar_t *v44; // rax
  unsigned int v45; // eax
  int v46; // r9d
  _DWORD *v47; // r8
  unsigned int v48; // r13d
  unsigned __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  _QWORD *v52; // rcx
  unsigned __int16 *v54; // [rsp+20h] [rbp-E0h]
  _BYTE v55[22]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v57; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v58[784]; // [rsp+60h] [rbp-A0h] BYREF

  v57 = a2;
  memset_0(v58, 0, sizeof(v58));
  memset(v55, 0, sizeof(v55));
  if ( !a1 || !*a1 || !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v4, (unsigned int)"AeComputeProgramIdentityHash", 133);
    return (unsigned int)-2147024809;
  }
  v5 = AeTrimString(*a1);
  *a1 = v5;
  if ( !v5 )
  {
    v8 = -2147024809;
LABEL_99:
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v34 = 56;
    goto LABEL_102;
  }
  v7 = 0x7FFFFFFF;
  do
  {
    if ( *v5 == (_WORD)v6 )
      break;
    ++v5;
    --v7;
  }
  while ( v7 );
  v8 = v7 == 0 ? 0x80070057 : 0;
  v9 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
  if ( !v7 )
    goto LABEL_99;
  v10 = 260;
  v11 = v6;
  if ( v9 > 0x104 )
    (*a1)[260] = v6;
  v12 = a1[3];
  if ( v12 )
  {
    v13 = AeTrimString(v12);
    a1[3] = v13;
    v16 = v13;
    if ( v13 )
    {
      v17 = v14;
      do
      {
        if ( *v13 == v15 )
          break;
        ++v13;
        --v17;
      }
      while ( v17 );
      v8 = v17 == 0 ? 0x80070057 : 0;
      v11 = (v14 - v17) & -(__int64)(v17 != 0);
      if ( v17 )
      {
        if ( v11 > 0x104 )
          v16[260] = v15;
        goto LABEL_19;
      }
    }
    else
    {
      v8 = -2147024809;
    }
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v34 = 57;
LABEL_102:
    WPP_SF_sdD(v33[2], v34);
    return v8;
  }
LABEL_19:
  v18 = a1[2];
  if ( !v18 )
    goto LABEL_27;
  v19 = AeTrimString(v18);
  a1[2] = v19;
  v22 = v19;
  if ( !v19 )
  {
    v8 = -2147024809;
LABEL_46:
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v34 = 58;
    goto LABEL_102;
  }
  v23 = v20;
  do
  {
    if ( *v19 == v21 )
      break;
    ++v19;
    --v23;
  }
  while ( v23 );
  v8 = v23 == 0 ? 0x80070057 : 0;
  v9 = (v20 - v23) & -(__int64)(v23 != 0);
  if ( !v23 )
    goto LABEL_46;
  if ( v9 > 0x104 )
    v22[260] = v21;
LABEL_27:
  v24 = a1[1];
  if ( !v24 )
    goto LABEL_35;
  v25 = AeTrimString(v24);
  a1[1] = v25;
  v28 = v25;
  if ( !v25 )
  {
    v8 = -2147024809;
LABEL_50:
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v34 = 59;
    goto LABEL_102;
  }
  v29 = v26;
  do
  {
    if ( *v25 == v27 )
      break;
    ++v25;
    --v29;
  }
  while ( v29 );
  v8 = v29 == 0 ? 0x80070057 : 0;
  if ( !v29 )
    goto LABEL_50;
  if ( ((v26 - v29) & ((unsigned __int128)-(__int128)v29 >> 64)) > 0x104 )
    v28[260] = v27;
LABEL_35:
  if ( !*a1 )
  {
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, v9, (unsigned int)"FormatNPVString", 100);
      v31 = WPP_GLOBAL_Control;
    }
    v8 = -2147024809;
LABEL_93:
    if ( v31 != (_BYTE *)&WPP_GLOBAL_Control && (v31[28] & 1) != 0 )
    {
      LOBYTE(v40) = v8;
      v41 = 60;
      goto LABEL_96;
    }
    return v8;
  }
  v54 = a1[1];
  v30 = StringCchPrintfW(v58, 0x310u, L"p%s_%s_%s");
  v8 = v30;
  if ( v30 < 0 )
  {
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    v32 = 65;
LABEL_40:
    WPP_SF_sd(*((_QWORD *)v31 + 2), v32, v9, (unsigned int)"FormatNPVString", v30);
    v31 = WPP_GLOBAL_Control;
    goto LABEL_93;
  }
  v35 = 784;
  v36 = v58;
  do
  {
    if ( !*v36 )
      break;
    ++v36;
    --v35;
  }
  while ( v35 );
  EndPtr = (wchar_t *)(784 - v35);
  v8 = v35 == 0 ? 0x80070057 : 0;
  v37 = (784 - v35) & -(__int64)(v35 != 0);
  if ( !v35 )
  {
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    LOBYTE(v30) = v8;
    v32 = 66;
    goto LABEL_40;
  }
  for ( i = 0; i < (unsigned int)v37; ++i )
  {
    v39 = v58[i];
    if ( !BYTE1(v39) )
      v58[i] = _o_towlower(v39);
  }
  v40 = ComputeMd5Hash(v58, (unsigned int)(2 * v37), &v55[2]);
  v8 = v40;
  if ( v40 >= 0 )
  {
    v42 = -1;
    if ( !v11 )
    {
LABEL_78:
      v47 = v57;
      v48 = v42 << 16;
      v49 = (unsigned __int64)v55[2] >> 4;
      v50 = v55[2] & 0xF;
      *v57 = 3145776;
      v47[1] = 3145776;
      *((_WORD *)v47 + 4) = a0123456789abcd_0[v49];
      LOWORD(v49) = a0123456789abcd_0[v50];
      LODWORD(v50) = v55[3];
      *((_WORD *)v47 + 5) = v49;
      *((_WORD *)v47 + 6) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v50 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v50 & 0xF];
      LODWORD(v50) = v55[4];
      *((_WORD *)v47 + 7) = v49;
      *((_WORD *)v47 + 8) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v50 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v50 & 0xF];
      LODWORD(v50) = v55[5];
      *((_WORD *)v47 + 9) = v49;
      *((_WORD *)v47 + 10) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v50 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v50 & 0xF];
      LODWORD(v50) = v55[6];
      *((_WORD *)v47 + 11) = v49;
      *((_WORD *)v47 + 12) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v50 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v50 & 0xF];
      LODWORD(v50) = v55[7];
      *((_WORD *)v47 + 13) = v49;
      *((_WORD *)v47 + 14) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v50 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v50 & 0xF];
      LODWORD(v50) = v55[8];
      *((_WORD *)v47 + 15) = v49;
      *((_WORD *)v47 + 16) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v50 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v50 & 0xF];
      LODWORD(v50) = v55[9];
      *((_WORD *)v47 + 17) = v49;
      *((_WORD *)v47 + 18) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v50 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v50 & 0xF];
      LODWORD(v50) = v55[10];
      *((_WORD *)v47 + 19) = v49;
      *((_WORD *)v47 + 20) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v50 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v50 & 0xF];
      LODWORD(v50) = v55[11];
      *((_WORD *)v47 + 21) = v49;
      *((_WORD *)v47 + 22) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v50 >> 4];
      *((_WORD *)v47 + 23) = a0123456789abcd_0[v50 & 0xF];
      v51 = v55[12] & 0xF;
      *((_WORD *)v47 + 24) = a0123456789abcd_0[(unsigned __int64)v55[12] >> 4];
      LOWORD(v49) = a0123456789abcd_0[v51];
      LODWORD(v51) = v55[13];
      *((_WORD *)v47 + 25) = v49;
      *((_WORD *)v47 + 26) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v51 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v51 & 0xF];
      LODWORD(v51) = v55[14];
      *((_WORD *)v47 + 27) = v49;
      *((_WORD *)v47 + 28) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v51 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v51 & 0xF];
      LODWORD(v51) = v55[15];
      *((_WORD *)v47 + 29) = v49;
      *((_WORD *)v47 + 30) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v51 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v51 & 0xF];
      LODWORD(v51) = v55[16];
      *((_WORD *)v47 + 31) = v49;
      *((_WORD *)v47 + 32) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v51 >> 4];
      LOWORD(v49) = a0123456789abcd_0[v51 & 0xF];
      LODWORD(v51) = v55[17];
      *((_WORD *)v47 + 33) = v49;
      *((_WORD *)v47 + 34) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v51 >> 4];
      *((_WORD *)v47 + 35) = a0123456789abcd_0[v51 & 0xF];
      *((_WORD *)v47 + 36) = a0123456789abcd_0[(unsigned __int64)(unsigned __int8)v48 >> 4];
      *((_WORD *)v47 + 37) = a0123456789abcd_0[v48 & 0xF];
      *((_WORD *)v47 + 38) = a0123456789abcd_0[0];
      *((_WORD *)v47 + 39) = a0123456789abcd_0[0];
      *((_WORD *)v47 + 40) = a0123456789abcd_0[(unsigned __int64)BYTE2(v48) >> 4];
      *((_WORD *)v47 + 41) = a0123456789abcd_0[BYTE2(v48) & 0xF];
      *((_WORD *)v47 + 42) = a0123456789abcd_0[(unsigned __int64)v48 >> 28];
      v8 = 0;
      *(_DWORD *)((char *)v47 + 86) = a0123456789abcd_0[((unsigned __int64)v48 >> 24) & 0xF];
      return v8;
    }
    v43 = a1[3];
    EndPtr = 0;
    if ( !v43 )
      goto LABEL_82;
    v44 = v43;
    do
    {
      if ( !*v44 )
        break;
      ++v44;
      --v10;
    }
    while ( v10 );
    if ( v10 )
    {
      v45 = wcstoul(v43, &EndPtr, 10);
      if ( EndPtr && !*EndPtr && v45 != -1 )
      {
        v42 = v45;
        goto LABEL_78;
      }
      v52 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sdS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)EndPtr, v9, v46, (_DWORD)v54, (__int64)v43);
LABEL_85:
        v52 = WPP_GLOBAL_Control;
      }
    }
    else
    {
LABEL_82:
      v52 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, v9, (unsigned int)"StringToDword", 200);
        goto LABEL_85;
      }
    }
    v8 = -2147024809;
    if ( v52 != &WPP_GLOBAL_Control && (*((_BYTE *)v52 + 28) & 1) != 0 )
      WPP_SF_sd(v52[2], 62, v9, (unsigned int)"AeComputeProgramIdentityHash", 87);
    return v8;
  }
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v41 = 61;
LABEL_96:
    WPP_SF_sd(*((_QWORD *)v31 + 2), v41, v9, (unsigned int)"AeComputeProgramIdentityHash", v40);
  }
  return v8;
}

```

## disassembly

```asm
0x1800535ec  mov     [rsp-8+arg_10], rbx
0x1800535f1  mov     [rsp-8+arg_18], rdi
0x1800535f6  push    rbp
0x1800535f7  push    r12
0x1800535f9  push    r13
0x1800535fb  push    r14
0x1800535fd  push    r15
0x1800535ff  lea     rbp, [rsp-590h]
0x180053607  sub     rsp, 690h
0x18005360e  mov     rax, cs:__security_cookie
0x180053615  xor     rax, rsp
0x180053618  mov     [rbp+5B0h+var_30], rax
0x18005361f  mov     rbx, rdx
0x180053622  mov     [rsp+6B0h+var_660], rdx
0x180053627  mov     rdi, rcx
0x18005362a  xor     edx, edx; Val
0x18005362c  lea     rcx, [rsp+6B0h+var_650]; void *
0x180053631  mov     r8d, 620h; Size
0x180053637  call    memset_0
0x18005363c  xor     eax, eax
0x18005363e  xorps   xmm0, xmm0
0x180053641  xor     r11d, r11d
0x180053644  movups  [rsp+6B0h+var_680], xmm0
0x180053649  mov     qword ptr [rsp+6B0h+var_680+0Eh], rax
0x18005364e  test    rdi, rdi
0x180053651  jz      loc_180053EA7
0x180053657  mov     rcx, [rdi]; unsigned __int16 *
0x18005365a  test    rcx, rcx
0x18005365d  jz      loc_180053EA7
0x180053663  test    rbx, rbx
0x180053666  jz      loc_180053EA7
0x18005366c  call    ?AeTrimString@@YAPEAGPEAG@Z; AeTrimString(ushort *)
0x180053671  mov     [rdi], rax
0x180053674  test    rax, rax
0x180053677  jz      loc_180053E6D
0x18005367d  mov     r9d, 7FFFFFFFh
0x180053683  mov     edx, r9d
0x180053686  cmp     [rax], r11w
0x18005368a  jz      short loc_180053696
0x18005368c  add     rax, 2
0x180053690  sub     rdx, 1
0x180053694  jnz     short loc_180053686
0x180053696  mov     rax, rdx
0x180053699  mov     r14d, 80070057h
0x18005369f  neg     rax
0x1800536a2  mov     rcx, r9
0x1800536a5  mov     rax, rdx
0x1800536a8  sbb     ebx, ebx
0x1800536aa  sub     rcx, rdx
0x1800536ad  not     ebx
0x1800536af  and     ebx, r14d
0x1800536b2  neg     rax
0x1800536b5  sbb     r8, r8
0x1800536b8  and     r8, rcx
0x1800536bb  test    rdx, rdx
0x1800536be  jz      loc_180053E72
0x1800536c4  mov     r15d, 104h
0x1800536ca  mov     r12, r11
0x1800536cd  cmp     r8, r15
0x1800536d0  jbe     short loc_1800536DD
0x1800536d2  mov     rcx, [rdi]
0x1800536d5  mov     [rcx+208h], r11w
0x1800536dd  mov     rcx, [rdi+18h]; unsigned __int16 *
0x1800536e1  test    rcx, rcx
0x1800536e4  jz      short loc_180053743
0x1800536e6  call    ?AeTrimString@@YAPEAGPEAG@Z; AeTrimString(ushort *)
0x1800536eb  mov     [rdi+18h], rax
0x1800536ef  mov     r10, rax
0x1800536f2  test    rax, rax
0x1800536f5  jz      loc_180053899
0x1800536fb  mov     rdx, r9
0x1800536fe  cmp     [rax], r11w
0x180053702  jz      short loc_18005370E
0x180053704  add     rax, 2
0x180053708  sub     rdx, 1
0x18005370c  jnz     short loc_1800536FE
0x18005370e  mov     rax, rdx
0x180053711  mov     rcx, r9
0x180053714  neg     rax
0x180053717  mov     rax, rdx
0x18005371a  sbb     ebx, ebx
0x18005371c  sub     rcx, rdx
0x18005371f  not     ebx
0x180053721  and     ebx, r14d
0x180053724  neg     rax
0x180053727  sbb     r12, r12
0x18005372a  and     r12, rcx
0x18005372d  test    rdx, rdx
0x180053730  jz      loc_18005389C
0x180053736  cmp     r12, r15
0x180053739  jbe     short loc_180053743
0x18005373b  mov     [r10+208h], r11w
0x180053743  mov     rcx, [rdi+10h]; unsigned __int16 *
0x180053747  test    rcx, rcx
0x18005374a  jz      short loc_1800537A9
0x18005374c  call    ?AeTrimString@@YAPEAGPEAG@Z; AeTrimString(ushort *)
0x180053751  mov     [rdi+10h], rax
0x180053755  mov     r10, rax
0x180053758  test    rax, rax
0x18005375b  jz      loc_1800538D3
0x180053761  mov     rdx, r9
0x180053764  cmp     [rax], r11w
0x180053768  jz      short loc_180053774
0x18005376a  add     rax, 2
0x18005376e  sub     rdx, 1
0x180053772  jnz     short loc_180053764
0x180053774  mov     rax, rdx
0x180053777  mov     rcx, r9
0x18005377a  neg     rax
0x18005377d  mov     rax, rdx
0x180053780  sbb     ebx, ebx
0x180053782  sub     rcx, rdx
0x180053785  not     ebx
0x180053787  and     ebx, r14d
0x18005378a  neg     rax
0x18005378d  sbb     r8, r8
0x180053790  and     r8, rcx
0x180053793  test    rdx, rdx
0x180053796  jz      loc_1800538D6
0x18005379c  cmp     r8, r15
0x18005379f  jbe     short loc_1800537A9
0x1800537a1  mov     [r10+208h], r11w
0x1800537a9  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800537ad  test    rcx, rcx
0x1800537b0  jz      short loc_18005380C
0x1800537b2  call    ?AeTrimString@@YAPEAGPEAG@Z; AeTrimString(ushort *)
0x1800537b7  mov     [rdi+8], rax
0x1800537bb  mov     r10, rax
0x1800537be  test    rax, rax
0x1800537c1  jz      loc_18005390D
0x1800537c7  mov     rcx, r9
0x1800537ca  cmp     [rax], r11w
0x1800537ce  jz      short loc_1800537DA
0x1800537d0  add     rax, 2
0x1800537d4  sub     rcx, 1
0x1800537d8  jnz     short loc_1800537CA
0x1800537da  mov     rax, rcx
0x1800537dd  neg     rax
0x1800537e0  mov     rax, rcx
0x1800537e3  sbb     ebx, ebx
0x1800537e5  sub     r9, rcx
0x1800537e8  not     ebx
0x1800537ea  and     ebx, r14d
0x1800537ed  neg     rax
0x1800537f0  sbb     rdx, rdx
0x1800537f3  and     rdx, r9
0x1800537f6  test    rcx, rcx
0x1800537f9  jz      loc_180053910
0x1800537ff  cmp     rdx, r15
0x180053802  jbe     short loc_18005380C
0x180053804  mov     [r10+208h], r11w
0x18005380c  mov     r9, [rdi]
0x18005380f  test    r9, r9
0x180053812  jz      loc_180053DFC
0x180053818  mov     rax, [rdi+10h]
0x18005381c  lea     r8, aPSSS; "p%s_%s_%s"
0x180053823  mov     [rsp+6B0h+var_688], rax
0x180053828  lea     rcx, [rsp+6B0h+var_650]; unsigned __int16 *
0x18005382d  mov     rax, [rdi+8]
0x180053831  mov     r13d, 310h
0x180053837  mov     edx, r13d; unsigned __int64
0x18005383a  mov     [rsp+6B0h+var_690], rax
0x18005383f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180053844  xor     edx, edx
0x180053846  mov     ebx, eax
0x180053848  test    eax, eax
0x18005384a  jns     loc_180053947
0x180053850  mov     rcx, cs:WPP_GLOBAL_Control
0x180053857  lea     rdi, WPP_GLOBAL_Control
0x18005385e  cmp     rcx, rdi
0x180053861  jz      loc_180053EE2
0x180053867  test    byte ptr [rcx+1Ch], 1
0x18005386b  jz      loc_180053E3C
0x180053871  movzx   eax, ax
0x180053874  mov     edx, 41h ; 'A'
0x180053879  mov     rcx, [rcx+10h]
0x18005387d  lea     r9, aFormatnpvstrin; "FormatNPVString"
0x180053884  mov     dword ptr [rsp+6B0h+var_690], eax
0x180053888  call    WPP_SF_sd
0x18005388d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053894  jmp     loc_180053E3C
0x180053899  mov     ebx, r14d
0x18005389c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538a3  lea     rdi, WPP_GLOBAL_Control
0x1800538aa  cmp     rcx, rdi
0x1800538ad  jz      loc_180053EE2
0x1800538b3  test    byte ptr [rcx+1Ch], 1
0x1800538b7  jz      loc_180053EE2
0x1800538bd  mov     dword ptr [rsp+6B0h+var_688], ebx
0x1800538c1  mov     edx, 39h ; '9'
0x1800538c6  mov     dword ptr [rsp+6B0h+var_690], 5ACh
0x1800538ce  jmp     loc_180053E9C
0x1800538d3  mov     ebx, r14d
0x1800538d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538dd  lea     rdi, WPP_GLOBAL_Control
0x1800538e4  cmp     rcx, rdi
0x1800538e7  jz      loc_180053EE2
0x1800538ed  test    byte ptr [rcx+1Ch], 1
0x1800538f1  jz      loc_180053EE2
0x1800538f7  mov     dword ptr [rsp+6B0h+var_688], ebx
0x1800538fb  mov     edx, 3Ah ; ':'
0x180053900  mov     dword ptr [rsp+6B0h+var_690], 5C1h
0x180053908  jmp     loc_180053E9C
0x18005390d  mov     ebx, r14d
0x180053910  mov     rcx, cs:WPP_GLOBAL_Control
0x180053917  lea     rdi, WPP_GLOBAL_Control
0x18005391e  cmp     rcx, rdi
0x180053921  jz      loc_180053EE2
0x180053927  test    byte ptr [rcx+1Ch], 1
0x18005392b  jz      loc_180053EE2
0x180053931  mov     dword ptr [rsp+6B0h+var_688], ebx
0x180053935  mov     edx, 3Bh ; ';'
0x18005393a  mov     dword ptr [rsp+6B0h+var_690], 5D6h
0x180053942  jmp     loc_180053E9C
0x180053947  mov     rcx, r13
0x18005394a  lea     rax, [rsp+6B0h+var_650]
0x18005394f  cmp     [rax], dx
0x180053952  jz      short loc_18005395E
0x180053954  add     rax, 2
0x180053958  sub     rcx, 1
0x18005395c  jnz     short loc_18005394F
0x18005395e  mov     rax, rcx
0x180053961  neg     rax
0x180053964  mov     rax, rcx
0x180053967  sbb     ebx, ebx
0x180053969  sub     r13, rcx
0x18005396c  mov     [rsp+6B0h+EndPtr], r13
0x180053971  not     ebx
0x180053973  and     ebx, r14d
0x180053976  neg     rax
0x180053979  sbb     r13, r13
0x18005397c  and     r13, [rsp+6B0h+EndPtr]
0x180053981  test    rcx, rcx
0x180053984  jnz     short loc_1800539B4
0x180053986  mov     rcx, cs:WPP_GLOBAL_Control
0x18005398d  lea     rdi, WPP_GLOBAL_Control
0x180053994  cmp     rcx, rdi
0x180053997  jz      loc_180053EE2
0x18005399d  test    byte ptr [rcx+1Ch], 1
0x1800539a1  jz      loc_180053E3C
0x1800539a7  movzx   eax, bx
0x1800539aa  mov     edx, 42h ; 'B'
0x1800539af  jmp     loc_180053879
0x1800539b4  mov     ebx, edx
0x1800539b6  test    r13d, r13d
0x1800539b9  jz      short loc_1800539E3
0x1800539bb  mov     eax, ebx
0x1800539bd  movzx   ecx, [rsp+rax*2+6B0h+var_650]
0x1800539c2  movzx   eax, cx
0x1800539c5  shr     ax, 8
0x1800539c9  test    al, al
0x1800539cb  jnz     short loc_1800539DC
0x1800539cd  call    cs:__imp__o_towlower
0x1800539d3  mov     ecx, ebx
0x1800539d5  xor     edx, edx
0x1800539d7  mov     [rsp+rcx*2+6B0h+var_650], ax
0x1800539dc  inc     ebx
0x1800539de  cmp     ebx, r13d
0x1800539e1  jb      short loc_1800539BB
0x1800539e3  lea     edx, ds:0[r13*2]
0x1800539eb  lea     r8, [rsp+6B0h+var_680+2]
0x1800539f0  lea     rcx, [rsp+6B0h+var_650]
0x1800539f5  call    ComputeMd5Hash
0x1800539fa  xor     r11d, r11d
0x1800539fd  mov     ebx, eax
0x1800539ff  test    eax, eax
0x180053a01  jns     short loc_180053A30
0x180053a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a0a  lea     rdi, WPP_GLOBAL_Control
0x180053a11  cmp     rcx, rdi
0x180053a14  jz      loc_180053EE2
0x180053a1a  test    byte ptr [rcx+1Ch], 1
0x180053a1e  jz      loc_180053EE2
0x180053a24  movzx   eax, ax
0x180053a27  lea     edx, [r11+3Dh]
0x180053a2b  jmp     loc_180053E57
0x180053a30  or      r13d, 0FFFFFFFFh
0x180053a34  test    r12, r12
0x180053a37  jz      short loc_180053AA2
0x180053a39  mov     rbx, [rdi+18h]
0x180053a3d  mov     [rsp+6B0h+EndPtr], r11
0x180053a42  test    rbx, rbx
0x180053a45  jz      loc_180053D9A
0x180053a4b  mov     rax, rbx
0x180053a4e  cmp     [rax], r11w
0x180053a52  jz      short loc_180053A5E
0x180053a54  add     rax, 2
0x180053a58  sub     r15, 1
0x180053a5c  jnz     short loc_180053A4E
0x180053a5e  test    r15, r15
0x180053a61  jz      loc_180053D9A
0x180053a67  mov     r8d, 0Ah; Radix
0x180053a6d  lea     rdx, [rsp+6B0h+EndPtr]; EndPtr
0x180053a72  mov     rcx, rbx; String
0x180053a75  call    cs:__imp_wcstoul
0x180053a7b  mov     rdx, [rsp+6B0h+EndPtr]
0x180053a80  xor     r11d, r11d
0x180053a83  test    rdx, rdx
0x180053a86  jz      loc_180053D71
0x180053a8c  cmp     r11w, [rdx]
  ... truncated ...
```
