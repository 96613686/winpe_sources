# __rtcIRR

- ea: `0x18037ce9c`
- end: `0x18037d644`
- name: `__rtcIRR`
- size: `1960`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x18037b0a4`

## callees

- `0x180102a4c`
- `0x180212a34`
- `0x18024b300`
- `0x1802ece2c`
- `0x180379520`
- `0x18037ce9c`
- `0x18037dc54`
- `0x18037fbb0`
- `0x18037fbd0`
- `0x18037fc38`
- `0x18037fcc8`
- `0x18037fcf0`
- `0x18037fd80`
- `0x18037fda8`
- `0x18037fdc4`
- `0x18037fde0`
- `0x18037fdfc`
- `0x18037fef4`
- `0x18037ffc8`
- `0x18037fff0`
- `0x18038005c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18037cf62`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18037cf62`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18037cfa9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18037cfa9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18037cf84`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18037cf84`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18037d006`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18037d006`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d225`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d338`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d5b7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d618`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d225`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d338`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d5b7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d618`

## pseudocode

```c
__int64 __fastcall _rtcIRR(__int64 a1, SAFEARRAY **a2, VARIANTARG *a3)
{
  unsigned int LBound; // eax
  unsigned int v7; // eax
  unsigned int UBound; // eax
  unsigned int v9; // eax
  unsigned int v10; // esi
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rcx
  int v14; // r15d
  __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned __int64 *v17; // r8
  _BYTE *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rax
  int v26; // r15d
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  char v38; // al
  unsigned __int64 *v39; // r8
  char *v40; // rdx
  unsigned __int64 *v41; // rcx
  __int64 v42; // rax
  char v43; // al
  unsigned __int64 *v44; // rax
  unsigned __int64 v45; // rcx
  __int16 v46; // ax
  unsigned __int64 v47; // rdx
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  int v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+20h] [rbp-E0h]
  void *ppvData; // [rsp+30h] [rbp-D0h] BYREF
  LONG plUbound; // [rsp+38h] [rbp-C8h] BYREF
  LONG plLbound; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned __int64 v58; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v59; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v61; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v62; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v63; // [rsp+68h] [rbp-98h]
  unsigned __int64 v64; // [rsp+70h] [rbp-90h] BYREF
  __int16 v65; // [rsp+78h] [rbp-88h]
  unsigned __int64 v66; // [rsp+80h] [rbp-80h] BYREF
  __int16 v67; // [rsp+88h] [rbp-78h]
  _BYTE v68[16]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v69; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v70; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v71; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v72; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v73; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v74; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v75; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v76; // [rsp+D8h] [rbp-28h]
  _BYTE v77[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v78[16]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v79[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v80[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v81[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v82[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v83[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v84[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v85[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v86[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v87[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v88[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v89[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v90[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v91[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v92; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v93[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v94; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v95[16]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v96[16]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v97[16]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v98[16]; // [rsp+230h] [rbp+130h] BYREF

  PgenprojOfHproj((unsigned __int64)&v71);
  PgenprojOfHproj((unsigned __int64)&v60);
  PgenprojOfHproj((unsigned __int64)&v66);
  PgenprojOfHproj((unsigned __int64)&v62);
  PgenprojOfHproj((unsigned __int64)&v69);
  PgenprojOfHproj((unsigned __int64)v79);
  PgenprojOfHproj((unsigned __int64)&v75);
  if ( a3->vt != 10 || a3->lVal != -2147352572 )
    rtR8FromVar(a3);
  doubletodouble80trunc(&v64);
  double80trunc::operator=(&v75, v68, &v64);
  if ( !*a2 || SafeArrayGetDim(*a2) != 1 )
    EbRaiseExceptionCode(5);
  LBound = SafeArrayGetLBound(*a2, 1u, &plLbound);
  v7 = EberrOfScode(LBound);
  if ( v7 )
    EbRaiseExceptionCode(v7);
  UBound = SafeArrayGetUBound(*a2, 1u, &plUbound);
  v9 = EberrOfScode(UBound);
  if ( v9 )
    EbRaiseExceptionCode(v9);
  v10 = plUbound - plLbound + 1;
  doubletodouble80trunc(&v64);
  if ( (unsigned __int8)double80::operator<=(&v75, &v64) || (int)v10 <= 1 )
    EbRaiseExceptionCode(5);
  v11 = SafeArrayAccessData(*a2, &ppvData);
  v12 = EberrOfScode(v11);
  if ( v12 )
    EbRaiseExceptionCode(v12);
  doubletodouble80trunc(&v64);
  double80trunc::operator=(&v71, v68, &v64);
  v14 = 0;
  if ( plUbound - plLbound + 1 > 0 )
  {
    v15 = 0;
    while ( !(unsigned __int8)operator>(v13, &v71) )
    {
      if ( (unsigned __int8)operator>(v16, &v71) )
      {
        doubletodouble80trunc(&v73);
        v17 = &v73;
        v18 = v77;
        goto LABEL_22;
      }
LABEL_23:
      ++v14;
      v15 += 8;
      if ( v14 >= plUbound - plLbound + 1 )
        goto LABEL_24;
    }
    doubletodouble80trunc(&v64);
    v17 = &v64;
    v18 = v68;
LABEL_22:
    double80trunc::operator=(&v71, v18, v17);
    goto LABEL_23;
  }
LABEL_24:
  doubletodouble80trunc(&v73);
  doubletodouble80trunc(&v64);
  v19 = double80::operator*(&v71, v68, &v64);
  v20 = double80::operator*(v19, v77, &v73);
  double80trunc::operator=(v79, v78, v20);
  v60 = v75;
  v58 = v75;
  v61 = v76;
  v59 = v76;
  v21 = LDoNPV(v68, &v58, ppvData, v10, 0);
  v62 = *(_QWORD *)v21;
  v63 = *(_WORD *)(v21 + 8);
  doubletodouble80trunc(&v64);
  ((__int64 (__fastcall *)(unsigned __int64 *, unsigned __int64 *))double80::operator>)(&v62, &v64);
  doubletodouble80trunc(&v73);
  v22 = double80::operator+(&v60, v68, &v73);
  double80trunc::operator=(&v66, v77, v22);
  doubletodouble80trunc(&v64);
  if ( (unsigned __int8)double80::operator<=(&v66, &v64) )
  {
    v23 = SafeArrayUnaccessData(*a2);
    v24 = EberrOfScode(v23);
    if ( v24 )
      EbRaiseExceptionCode(v24);
    EbRaiseExceptionCode(5);
  }
  v58 = v66;
  LOWORD(v53) = 0;
  v59 = v67;
  v25 = LDoNPV(v68, &v58, ppvData, v10, v53);
  v26 = 0;
  v69 = *(_QWORD *)v25;
  v70 = *(_WORD *)(v25 + 8);
  while ( 1 )
  {
    if ( (unsigned __int8)double80::operator==(&v69, &v62) )
    {
      double80::operator>(&v66, &v60);
      doubletodouble80trunc(v82);
      double80::operator-=(&v60, v89, v82);
      v58 = v60;
      LOWORD(v54) = 0;
      v59 = v61;
      v27 = LDoNPV(v85, &v58, ppvData, v10, v54);
      v62 = *(_QWORD *)v27;
      v63 = *(_WORD *)(v27 + 8);
      if ( (unsigned __int8)double80::operator==(&v69, &v62) )
      {
        v28 = SafeArrayUnaccessData(*a2);
        v29 = EberrOfScode(v28);
        if ( v29 )
          EbRaiseExceptionCode(v29);
        EbRaiseExceptionCode(5);
      }
    }
    v30 = double80::operator-(&v69, v95, &v62);
    v31 = double80::operator-(&v66, v87, &v60);
    v32 = double80::operator*(v31, v93, &v69);
    v33 = double80::operator/(v32, v83, v30);
    v34 = double80::operator-(&v66, v97, v33);
    double80trunc::operator=(&v60, v91, v34);
    doubletodouble80trunc(v80);
    if ( (unsigned __int8)double80::operator<=(&v60, v80) )
    {
      doubletodouble80trunc(v78);
      doubletodouble80trunc(v81);
      v35 = double80::operator-(&v66, v84, v81);
      v36 = double80::operator*(v35, v86, v78);
      double80trunc::operator=(&v60, v88, v36);
    }
    v73 = v60;
    LOWORD(v54) = 0;
    v74 = v61;
    v37 = LDoNPV(v90, &v73, ppvData, v10, v54);
    v62 = *(_QWORD *)v37;
    v63 = *(_WORD *)(v37 + 8);
    double80::operator>(&v60, &v66);
    if ( v38 )
    {
      v39 = &v66;
      v40 = &v92;
      v41 = &v60;
    }
    else
    {
      v39 = &v60;
      v40 = &v94;
      v41 = &v66;
    }
    v42 = double80::operator-(v41, v40, v39);
    double80trunc::operator=(&v71, v96, v42);
    doubletodouble80trunc(v77);
    double80::operator>(&v62, v77);
    if ( v43 )
    {
      v64 = v62;
      v65 = v63;
      v44 = &v64;
    }
    else
    {
      v44 = (unsigned __int64 *)double80::operator-(&v62, v98);
    }
    if ( (unsigned __int8)double80::operator<(v44, v79) )
    {
      doubletodouble80trunc(v68);
      if ( (unsigned __int8)double80::operator<(&v71, v68) )
        break;
    }
    v45 = v62;
    v62 = v69;
    v46 = v70;
    v70 = v63;
    v47 = v60;
    v63 = v46;
    v60 = v66;
    v69 = v45;
    LOWORD(v45) = v61;
    ++v26;
    v71 = v47;
    v61 = v67;
    v66 = v47;
    v72 = v45;
    v67 = v45;
    if ( v26 >= 40 )
    {
      v48 = SafeArrayUnaccessData(*a2);
      v49 = EberrOfScode(v48);
      if ( v49 )
        EbRaiseExceptionCode(v49);
      EbRaiseExceptionCode(5);
    }
  }
  v51 = SafeArrayUnaccessData(*a2);
  v52 = EberrOfScode(v51);
  if ( v52 )
    EbRaiseExceptionCode(v52);
  *(_QWORD *)a1 = v60;
  *(_WORD *)(a1 + 8) = v61;
  return a1;
}

```

## disassembly

```asm
0x18037ce9c  push    rbp
0x18037ce9e  push    rbx
0x18037ce9f  push    rsi
0x18037cea0  push    rdi
0x18037cea1  push    r12
0x18037cea3  push    r14
0x18037cea5  push    r15
0x18037cea7  lea     rbp, [rsp-150h]
0x18037ceaf  sub     rsp, 250h
0x18037ceb6  mov     rax, cs:__security_cookie
0x18037cebd  xor     rax, rsp
0x18037cec0  mov     [rbp+180h+var_40], rax
0x18037cec7  mov     r14, rcx
0x18037ceca  lea     rcx, [rbp+180h+var_1D0]; unsigned __int64
0x18037cece  mov     rbx, r8
0x18037ced1  mov     rdi, rdx
0x18037ced4  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037ced9  lea     rcx, [rsp+280h+var_230]; unsigned __int64
0x18037cede  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037cee3  lea     rcx, [rbp+180h+var_200]; unsigned __int64
0x18037cee7  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037ceec  lea     rcx, [rsp+280h+var_220]; unsigned __int64
0x18037cef1  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037cef6  lea     rcx, [rbp+180h+var_1E0]; unsigned __int64
0x18037cefa  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037ceff  lea     rcx, [rbp+180h+var_180]; unsigned __int64
0x18037cf03  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037cf08  lea     rcx, [rbp+180h+var_1B0]; unsigned __int64
0x18037cf0c  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037cf11  mov     r11d, 0Ah
0x18037cf17  cmp     r11w, [rbx]
0x18037cf1b  jnz     short loc_18037CF30
0x18037cf1d  cmp     dword ptr [rbx+8], 80020004h
0x18037cf24  jnz     short loc_18037CF30
0x18037cf26  movsd   xmm1, cs:__real@3fb999999999999a
0x18037cf2e  jmp     short loc_18037CF3B
0x18037cf30  mov     rcx, rbx
0x18037cf33  call    rtR8FromVar
0x18037cf38  movaps  xmm1, xmm0
0x18037cf3b  lea     rcx, [rsp+280h+var_210]
0x18037cf40  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037cf45  lea     r8, [rsp+280h+var_210]
0x18037cf4a  lea     rdx, [rbp+180h+var_1F0]
0x18037cf4e  lea     rcx, [rbp+180h+var_1B0]
0x18037cf52  call    ??4double80trunc@@QEAA?AV0@AEBVdouble80@@@Z; double80trunc::operator=(double80 const &)
0x18037cf57  mov     rcx, [rdi]; psa
0x18037cf5a  xor     r12d, r12d
0x18037cf5d  test    rcx, rcx
0x18037cf60  jz      short loc_18037CF6D
0x18037cf62  call    cs:__imp_SafeArrayGetDim
0x18037cf68  cmp     eax, 1
0x18037cf6b  jz      short loc_18037CF77
0x18037cf6d  mov     ecx, 5
0x18037cf72  call    EbRaiseExceptionCode
0x18037cf77  mov     rcx, [rdi]; psa
0x18037cf7a  lea     r8, [rsp+280h+plLbound]; plLbound
0x18037cf7f  mov     edx, 1; nDim
0x18037cf84  call    cs:__imp_SafeArrayGetLBound
0x18037cf8a  mov     ecx, eax
0x18037cf8c  call    EberrOfScode
0x18037cf91  test    eax, eax
0x18037cf93  jz      short loc_18037CF9C
0x18037cf95  mov     ecx, eax
0x18037cf97  call    EbRaiseExceptionCode
0x18037cf9c  mov     rcx, [rdi]; psa
0x18037cf9f  lea     r8, [rsp+280h+plUbound]; plUbound
0x18037cfa4  mov     edx, 1; nDim
0x18037cfa9  call    cs:__imp_SafeArrayGetUBound
0x18037cfaf  mov     ecx, eax
0x18037cfb1  call    EberrOfScode
0x18037cfb6  test    eax, eax
0x18037cfb8  jz      short loc_18037CFC1
0x18037cfba  mov     ecx, eax
0x18037cfbc  call    EbRaiseExceptionCode
0x18037cfc1  mov     esi, [rsp+280h+plUbound]
0x18037cfc5  movsd   xmm1, cs:__real@bff0000000000000
0x18037cfcd  lea     rcx, [rsp+280h+var_210]
0x18037cfd2  sub     esi, [rsp+280h+plLbound]
0x18037cfd6  inc     esi
0x18037cfd8  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037cfdd  lea     rdx, [rsp+280h+var_210]
0x18037cfe2  lea     rcx, [rbp+180h+var_1B0]
0x18037cfe6  call    ??Ndouble80@@QEBA_NAEBV0@@Z; double80::operator<=(double80 const &)
0x18037cfeb  test    al, al
0x18037cfed  jnz     short loc_18037CFF4
0x18037cfef  cmp     esi, 1
0x18037cff2  jg      short loc_18037CFFE
0x18037cff4  mov     ecx, 5
0x18037cff9  call    EbRaiseExceptionCode
0x18037cffe  mov     rcx, [rdi]; psa
0x18037d001  lea     rdx, [rsp+280h+ppvData]; ppvData
0x18037d006  call    cs:__imp_SafeArrayAccessData
0x18037d00c  mov     ecx, eax
0x18037d00e  call    EberrOfScode
0x18037d013  test    eax, eax
0x18037d015  jz      short loc_18037D01E
0x18037d017  mov     ecx, eax
0x18037d019  call    EbRaiseExceptionCode
0x18037d01e  mov     rax, [rsp+280h+ppvData]
0x18037d023  movsd   xmm1, qword ptr [rax]
0x18037d027  comisd  xmm1, cs:__real@0000000000000000
0x18037d02f  ja      short loc_18037D039
0x18037d031  xorpd   xmm1, cs:__xmm@80000000000000008000000000000000
0x18037d039  lea     rcx, [rsp+280h+var_210]
0x18037d03e  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d043  lea     r8, [rsp+280h+var_210]
0x18037d048  lea     rdx, [rbp+180h+var_1F0]
0x18037d04c  lea     rcx, [rbp+180h+var_1D0]
0x18037d050  call    ??4double80trunc@@QEAA?AV0@AEBVdouble80@@@Z; double80trunc::operator=(double80 const &)
0x18037d055  mov     eax, [rsp+280h+plUbound]
0x18037d059  mov     r15d, r12d
0x18037d05c  sub     eax, [rsp+280h+plLbound]
0x18037d060  inc     eax
0x18037d062  test    eax, eax
0x18037d064  jle     loc_18037D103
0x18037d06a  mov     rbx, r12
0x18037d06d  mov     rax, [rsp+280h+ppvData]
0x18037d072  lea     rdx, [rbp+180h+var_1D0]
0x18037d076  movsd   xmm0, qword ptr [rbx+rax]
0x18037d07b  call    ??O@YA_NNAEBVdouble80@@@Z; operator>(double,double80 const &)
0x18037d080  test    al, al
0x18037d082  mov     rax, [rsp+280h+ppvData]
0x18037d087  jz      short loc_18037D0A3
0x18037d089  movsd   xmm1, qword ptr [rbx+rax]
0x18037d08e  lea     rcx, [rsp+280h+var_210]
0x18037d093  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d098  lea     r8, [rsp+280h+var_210]
0x18037d09d  lea     rdx, [rbp+180h+var_1F0]
0x18037d0a1  jmp     short loc_18037D0E0
0x18037d0a3  movsd   xmm0, qword ptr [rbx+rax]
0x18037d0a8  lea     rdx, [rbp+180h+var_1D0]
0x18037d0ac  xorpd   xmm0, cs:__xmm@80000000000000008000000000000000
0x18037d0b4  call    ??O@YA_NNAEBVdouble80@@@Z; operator>(double,double80 const &)
0x18037d0b9  test    al, al
0x18037d0bb  jz      short loc_18037D0E9
0x18037d0bd  mov     rax, [rsp+280h+ppvData]
0x18037d0c2  lea     rcx, [rbp+180h+var_1C0]
0x18037d0c6  movsd   xmm1, qword ptr [rbx+rax]
0x18037d0cb  xorpd   xmm1, cs:__xmm@80000000000000008000000000000000
0x18037d0d3  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d0d8  lea     r8, [rbp+180h+var_1C0]
0x18037d0dc  lea     rdx, [rbp+180h+var_1A0]
0x18037d0e0  lea     rcx, [rbp+180h+var_1D0]
0x18037d0e4  call    ??4double80trunc@@QEAA?AV0@AEBVdouble80@@@Z; double80trunc::operator=(double80 const &)
0x18037d0e9  mov     eax, [rsp+280h+plUbound]
0x18037d0ed  inc     r15d
0x18037d0f0  add     rbx, 8
0x18037d0f4  sub     eax, [rsp+280h+plLbound]
0x18037d0f8  inc     eax
0x18037d0fa  cmp     r15d, eax
0x18037d0fd  jl      loc_18037D06D
0x18037d103  movsd   xmm1, cs:__real@3f847ae147ae147b
0x18037d10b  lea     rcx, [rbp+180h+var_1C0]
0x18037d10f  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d114  movsd   xmm1, cs:__real@3e7ad7f29abcaf48
0x18037d11c  lea     rcx, [rsp+280h+var_210]
0x18037d121  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d126  lea     r8, [rsp+280h+var_210]
0x18037d12b  lea     rdx, [rbp+180h+var_1F0]
0x18037d12f  lea     rcx, [rbp+180h+var_1D0]
0x18037d133  call    ??Ddouble80@@QEBA?AV0@AEBV0@@Z; double80::operator*(double80 const &)
0x18037d138  lea     r8, [rbp+180h+var_1C0]
0x18037d13c  lea     rdx, [rbp+180h+var_1A0]
0x18037d140  mov     rcx, rax
0x18037d143  call    ??Ddouble80@@QEBA?AV0@AEBV0@@Z; double80::operator*(double80 const &)
0x18037d148  lea     rdx, [rbp+180h+var_190]
0x18037d14c  lea     rcx, [rbp+180h+var_180]
0x18037d150  mov     r8, rax
0x18037d153  call    ??4double80trunc@@QEAA?AV0@AEBVdouble80@@@Z; double80trunc::operator=(double80 const &)
0x18037d158  mov     rcx, [rbp+180h+var_1B0]
0x18037d15c  movzx   eax, [rbp+180h+var_1A8]
0x18037d160  mov     r8, [rsp+280h+ppvData]
0x18037d165  mov     [rsp+280h+var_230], rcx
0x18037d16a  mov     [rsp+280h+var_240], rcx
0x18037d16f  lea     rcx, [rbp+180h+var_1F0]
0x18037d173  lea     rdx, [rsp+280h+var_240]
0x18037d178  mov     r9d, esi
0x18037d17b  mov     [rsp+280h+var_228], ax
0x18037d180  mov     [rsp+280h+var_238], ax
0x18037d185  mov     word ptr [rsp+280h+var_260], r12w
0x18037d18b  call    ?LDoNPV@@YA?AVdouble80trunc@@V1@PEANJF@Z; LDoNPV(double80trunc,double *,long,short)
0x18037d190  xorps   xmm1, xmm1
0x18037d193  mov     rcx, [rax]
0x18037d196  mov     [rsp+280h+var_220], rcx
0x18037d19b  movzx   eax, word ptr [rax+8]
0x18037d19f  lea     rcx, [rsp+280h+var_210]
0x18037d1a4  mov     [rsp+280h+var_218], ax
0x18037d1a9  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d1ae  lea     rdx, [rsp+280h+var_210]
0x18037d1b3  lea     rcx, [rsp+280h+var_220]
0x18037d1b8  call    ??Odouble80@@QEBA_NAEBV0@@Z; double80::operator>(double80 const &)
0x18037d1bd  test    al, al
0x18037d1bf  jz      short loc_18037D1CB
0x18037d1c1  movsd   xmm1, cs:__real@3ee4f8b588e368f1
0x18037d1c9  jmp     short loc_18037D1D3
0x18037d1cb  movsd   xmm1, cs:__real@bee4f8b588e368f1
0x18037d1d3  lea     rcx, [rbp+180h+var_1C0]
0x18037d1d7  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d1dc  lea     r8, [rbp+180h+var_1C0]
0x18037d1e0  lea     rdx, [rbp+180h+var_1F0]
0x18037d1e4  lea     rcx, [rsp+280h+var_230]
0x18037d1e9  call    ??Hdouble80@@QEBA?AV0@AEBV0@@Z; double80::operator+(double80 const &)
0x18037d1ee  lea     rdx, [rbp+180h+var_1A0]
0x18037d1f2  lea     rcx, [rbp+180h+var_200]
0x18037d1f6  mov     r8, rax
0x18037d1f9  call    ??4double80trunc@@QEAA?AV0@AEBVdouble80@@@Z; double80trunc::operator=(double80 const &)
0x18037d1fe  lea     rcx, [rsp+280h+var_210]
0x18037d203  movsd   xmm1, cs:__real@bff0000000000000
0x18037d20b  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d210  lea     rdx, [rsp+280h+var_210]
0x18037d215  lea     rcx, [rbp+180h+var_200]
0x18037d219  call    ??Ndouble80@@QEBA_NAEBV0@@Z; double80::operator<=(double80 const &)
0x18037d21e  test    al, al
0x18037d220  jz      short loc_18037D247
0x18037d222  mov     rcx, [rdi]; psa
0x18037d225  call    cs:__imp_SafeArrayUnaccessData
0x18037d22b  mov     ecx, eax
0x18037d22d  call    EberrOfScode
0x18037d232  test    eax, eax
0x18037d234  jz      short loc_18037D23D
0x18037d236  mov     ecx, eax
0x18037d238  call    EbRaiseExceptionCode
0x18037d23d  mov     ecx, 5
0x18037d242  call    EbRaiseExceptionCode
0x18037d247  mov     rax, [rbp+180h+var_200]
0x18037d24b  mov     r8, [rsp+280h+ppvData]
0x18037d250  lea     rdx, [rsp+280h+var_240]
0x18037d255  mov     [rsp+280h+var_240], rax
0x18037d25a  movzx   eax, [rbp+180h+var_1F8]
0x18037d25e  lea     rcx, [rbp+180h+var_1F0]
0x18037d262  mov     r9d, esi
0x18037d265  mov     word ptr [rsp+280h+var_260], r12w
0x18037d26b  mov     [rsp+280h+var_238], ax
0x18037d270  call    ?LDoNPV@@YA?AVdouble80trunc@@V1@PEANJF@Z; LDoNPV(double80trunc,double *,long,short)
0x18037d275  mov     r15d, r12d
0x18037d278  mov     rcx, [rax]
0x18037d27b  mov     [rbp+180h+var_1E0], rcx
0x18037d27f  movzx   eax, word ptr [rax+8]
0x18037d283  mov     [rbp+180h+var_1D8], ax
0x18037d287  lea     rdx, [rsp+280h+var_220]
0x18037d28c  lea     rcx, [rbp+180h+var_1E0]
0x18037d290  call    ??8double80@@QEBA_NAEBV0@@Z; double80::operator==(double80 const &)
0x18037d295  test    al, al
0x18037d297  jz      loc_18037D35A
0x18037d29d  lea     rdx, [rsp+280h+var_230]
0x18037d2a2  lea     rcx, [rbp+180h+var_200]
0x18037d2a6  call    ??Odouble80@@QEBA_NAEBV0@@Z; double80::operator>(double80 const &)
0x18037d2ab  neg     al
0x18037d2ad  sbb     ecx, ecx
0x18037d2af  and     ecx, 2
0x18037d2b2  dec     ecx
0x18037d2b4  movd    xmm1, ecx
0x18037d2b8  lea     rcx, [rbp+180h+var_150]
0x18037d2bc  cvtdq2pd xmm1, xmm1
0x18037d2c0  mulsd   xmm1, cs:__real@3ee4f8b588e368f1
0x18037d2c8  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d2cd  lea     r8, [rbp+180h+var_150]
0x18037d2d1  lea     rdx, [rbp+180h+var_E0]
0x18037d2d8  lea     rcx, [rsp+280h+var_230]
0x18037d2dd  call    ??Zdouble80@@QEAA?AV0@AEBV0@@Z; double80::operator-=(double80 const &)
0x18037d2e2  mov     rax, [rsp+280h+var_230]
0x18037d2e7  mov     r8, [rsp+280h+ppvData]
0x18037d2ec  mov     [rsp+280h+var_240], rax
0x18037d2f1  movzx   eax, [rsp+280h+var_228]
0x18037d2f6  lea     rdx, [rsp+280h+var_240]
0x18037d2fb  lea     rcx, [rbp+180h+var_120]
0x18037d2ff  mov     r9d, esi
0x18037d302  mov     word ptr [rsp+280h+var_260], r12w
0x18037d308  mov     [rsp+280h+var_238], ax
0x18037d30d  call    ?LDoNPV@@YA?AVdouble80trunc@@V1@PEANJF@Z; LDoNPV(double80trunc,double *,long,short)
0x18037d312  lea     rdx, [rsp+280h+var_220]
0x18037d317  mov     rcx, [rax]
0x18037d31a  mov     [rsp+280h+var_220], rcx
0x18037d31f  movzx   eax, word ptr [rax+8]
0x18037d323  lea     rcx, [rbp+180h+var_1E0]
0x18037d327  mov     [rsp+280h+var_218], ax
0x18037d32c  call    ??8double80@@QEBA_NAEBV0@@Z; double80::operator==(double80 const &)
0x18037d331  test    al, al
0x18037d333  jz      short loc_18037D35A
0x18037d335  mov     rcx, [rdi]; psa
0x18037d338  call    cs:__imp_SafeArrayUnaccessData
0x18037d33e  mov     ecx, eax
0x18037d340  call    EberrOfScode
0x18037d345  test    eax, eax
0x18037d347  jz      short loc_18037D350
0x18037d349  mov     ecx, eax
0x18037d34b  call    EbRaiseExceptionCode
0x18037d350  mov     ecx, 5
0x18037d355  call    EbRaiseExceptionCode
0x18037d35a  lea     r8, [rsp+280h+var_220]
0x18037d35f  lea     rdx, [rbp+180h+var_80]
0x18037d366  lea     rcx, [rbp+180h+var_1E0]
0x18037d36a  call    ??Gdouble80@@QEBA?AV0@AEBV0@@Z; double80::operator-(double80 const &)
0x18037d36f  lea     r8, [rsp+280h+var_230]
0x18037d374  lea     rdx, [rbp+180h+var_100]
0x18037d37b  lea     rcx, [rbp+180h+var_200]
0x18037d37f  mov     rbx, rax
0x18037d382  call    ??Gdouble80@@QEBA?AV0@AEBV0@@Z; double80::operator-(double80 const &)
0x18037d387  lea     r8, [rbp+180h+var_1E0]
0x18037d38b  lea     rdx, [rbp+180h+var_A0]
  ... truncated ...
```
