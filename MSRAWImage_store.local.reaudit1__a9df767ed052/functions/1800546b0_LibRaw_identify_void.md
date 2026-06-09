# LibRaw::identify(void)

- ea: `0x1800546b0`
- end: `0x1800570d0`
- name: `?identify@LibRaw@@IEAAXXZ`
- size: `10784`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `1`
- callee_count: `54`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000adf0`

## callees

- `0x180002a00`
- `0x180003e4c`
- `0x180005d03`
- `0x180005d0f`
- `0x180005d4b`
- `0x180006150`
- `0x180009690`
- `0x180024c40`
- `0x180026500`
- `0x180027e20`
- `0x18002b870`
- `0x18002c2f0`
- `0x18002c350`
- `0x180044d60`
- `0x180044de0`
- `0x180048320`
- `0x1800546b0`
- `0x1800570e0`
- `0x18005a750`
- `0x180064040`
- `0x180065800`
- `0x1800731a0`
- `0x180073900`
- `0x180073a10`
- `0x1800757a0`
- `0x180075aa0`
- `0x180075b80`
- `0x180075cb0`
- `0x180075d90`
- `0x180075e70`
- `0x180075f80`
- `0x180076310`
- `0x180076530`
- `0x1800767d0`
- `0x180076920`
- `0x180076d30`
- `0x180077130`
- `0x180077350`
- `0x180077760`
- `0x180080840`
- `0x180082010`
- `0x180082a00`
- `0x180083900`
- `0x180094f8d`
- `0x180094fbd`
- `0x180094fc9`
- `0x180095059`
- `0x180095071`
- `0x180095170`
- `0x1800951c4`

## string_xrefs

- `0x1800557ae`: `Broadcom`
- `0x180055b9d`: `Broadcom`

## pseudocode

```c
void __fastcall LibRaw::identify(LibRaw *this)
{
  char **v1; // r9
  unsigned int v3; // r12d
  __int64 *v4; // r8
  unsigned int v5; // r9d
  int v6; // eax
  __int128 v7; // xmm1
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int128 v10; // xmm0
  char *v11; // r14
  _BYTE *v12; // r13
  int v13; // r12d
  __int64 v14; // rcx
  LibRaw *v15; // rdx
  __int64 v16; // rax
  float *v17; // rcx
  int v18; // edx
  float v19; // xmm0_4
  BOOL v20; // eax
  _WORD *v21; // rcx
  int i; // eax
  __int64 v23; // rsi
  __int64 v24; // rcx
  char *v25; // rdi
  __int16 v26; // ax
  __int64 v27; // rcx
  unsigned __int8 v28; // al
  int v29; // eax
  __int64 v30; // rcx
  unsigned __int8 v31; // al
  int v32; // eax
  unsigned __int16 v33; // ax
  __int64 v34; // rcx
  __int64 v35; // rdx
  __m128i v36; // xmm1
  char *v37; // rdi
  int v38; // esi
  char v39; // al
  unsigned int v40; // eax
  __int64 v41; // rcx
  int v42; // eax
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rdx
  unsigned int v46; // eax
  __int64 v47; // rcx
  unsigned __int8 v48; // al
  int v49; // eax
  int v50; // esi
  __int64 v51; // rcx
  unsigned __int8 v52; // al
  int v53; // eax
  __int64 v54; // rcx
  int v55; // edi
  int v56; // r8d
  int v57; // eax
  int v58; // r9d
  int v59; // ecx
  int v60; // eax
  int v61; // ecx
  void (__fastcall *v62)(LibRaw *__hidden); // rax
  unsigned int v63; // eax
  __int64 v64; // rcx
  unsigned __int8 v65; // al
  int v66; // eax
  __int64 v67; // rcx
  unsigned __int8 v68; // al
  int v69; // eax
  __int64 v70; // rcx
  unsigned __int8 v71; // al
  int v72; // eax
  bool v73; // cf
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // rax
  int v77; // eax
  __int16 v78; // dx
  int v79; // eax
  LibRaw *v80; // rcx
  int v81; // r8d
  unsigned int v82; // ecx
  __int64 v83; // rdi
  int v84; // r15d
  int v85; // edi
  __int64 v86; // r15
  unsigned int v87; // r12d
  unsigned int v88; // eax
  int v89; // r10d
  __int16 v90; // dx
  __int64 v91; // rsi
  __int16 v92; // r8
  __int16 v93; // ax
  __int16 v94; // cx
  __int16 v95; // ax
  __int16 v96; // cx
  int v97; // eax
  unsigned int v98; // r9d
  int v99; // r11d
  __int64 v100; // r10
  __int64 v101; // rax
  char v102; // r8
  int v103; // eax
  int v104; // ecx
  void (__fastcall *v105)(LibRaw *__hidden); // rax
  char v106; // al
  unsigned int v107; // edi
  int v108; // eax
  unsigned int v109; // eax
  int v110; // eax
  char *v111; // rax
  int v112; // eax
  __int64 v113; // rsi
  int v114; // edi
  size_t v115; // rax
  size_t v116; // rax
  char *v117; // rdx
  size_t v118; // r8
  char *v119; // rcx
  int v120; // eax
  size_t v121; // rax
  __int64 v122; // r9
  int v123; // r8d
  int v124; // ecx
  _DWORD *v125; // rdx
  int v126; // eax
  __int16 v127; // cx
  __int16 v128; // ax
  __int64 v129; // rcx
  int v130; // eax
  __int64 v131; // rcx
  __int16 v132; // ax
  int v133; // ecx
  int v134; // ecx
  int v135; // ecx
  int v136; // ecx
  unsigned int v137; // eax
  unsigned int v138; // eax
  void (__fastcall *v139)(LibRaw *__hidden); // rax
  int v140; // eax
  void (__fastcall __noreturn *v141)(LibRaw *__hidden); // rax
  unsigned int v142; // ecx
  int v143; // ecx
  int v144; // r10d
  int v145; // r8d
  float *v146; // r9
  __int64 v147; // rdx
  int v148; // eax
  float *v149; // rdx
  int v150; // r9d
  int v151; // eax
  double v152; // xmm1_8
  __int64 v153; // r8
  double v154; // xmm0_8
  int v155; // r9d
  __int64 v156; // rdx
  float *v157; // r8
  double v158; // xmm0_8
  double v159; // xmm1_8
  unsigned int v160; // ecx
  double v161; // xmm2_8
  double *v162; // rdx
  double v163; // xmm0_8
  int v164; // eax
  __int64 v165; // r9
  char v166; // cl
  __int16 *v167; // r8
  __int64 v168; // r11
  int v169; // r10d
  __int16 v170; // r9
  __int16 v171; // cx
  __int16 v172; // dx
  __int16 v173; // r9
  int v174; // eax
  int v175; // eax
  __int16 v176; // cx
  __int16 v177; // cx
  void (__fastcall __noreturn *v178)(LibRaw *__hidden); // rax
  unsigned int v179; // edx
  unsigned int v180; // ecx
  __int64 v181; // r9
  __int64 v182; // rdx
  unsigned int v183; // edx
  unsigned __int16 v184; // ax
  unsigned __int16 v185; // cx
  unsigned __int16 v186; // r10
  __int64 v187; // r9
  unsigned __int16 v188; // r8
  __int64 v189; // rdx
  unsigned int v190; // r10d
  unsigned int v191; // ecx
  int v192; // eax
  void (__fastcall __noreturn *v193)(LibRaw *__hidden); // rax
  unsigned __int16 v194; // cx
  unsigned __int16 v195; // ax
  double v196; // xmm1_8
  unsigned int v197; // eax
  const char *v198; // rdx
  unsigned int v199; // edx
  int v200; // eax
  __int16 v201; // dx
  char v202; // cl
  unsigned __int16 v203; // ax
  __int64 v204; // rcx
  unsigned int (__fastcall *v205)(_QWORD, __int64, __int64, __int64); // rax
  unsigned int (__fastcall *v206)(_QWORD, __int64, __int64, __int64); // rax
  int v207; // ecx
  int v208; // ecx
  int v209; // ecx
  int v210; // eax
  void (__fastcall *v211)(LibRaw *__hidden); // rax
  unsigned int (__fastcall *v212)(_QWORD, __int64, __int64, __int64); // rax
  int pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  int v214[2]; // [rsp+48h] [rbp-B8h]
  __int16 v215[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v216; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v217; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v218; // [rsp+60h] [rbp-A0h]
  char v219[8]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v220; // [rsp+78h] [rbp-88h]
  __int16 v221; // [rsp+7Ch] [rbp-84h]
  double v222[4]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v223[10976]; // [rsp+310h] [rbp+210h] BYREF
  char Str1[16]; // [rsp+2DF0h] [rbp+2CF0h] BYREF
  __m128i Buf1; // [rsp+2E00h] [rbp+2D00h] BYREF
  __int128 v226; // [rsp+2E20h] [rbp+2D20h]
  char v227[144]; // [rsp+2E30h] [rbp+2D30h] BYREF

  v1 = (char **)*((_QWORD *)this + 672);
  *(_OWORD *)Str1 = 0;
  memset(&Buf1, 0, 32);
  v226 = 0;
  v3 = LibRaw::parse_custom_cameras(this, 0x40u, (struct libraw_custom_camera_t *const)v223, v1);
  v4 = qword_1800CABD0;
  v5 = v3;
  do
  {
    v6 = *((_DWORD *)v4 + 12);
    v7 = *((_OWORD *)v4 + 1);
    v8 = v5++;
    v9 = 52 * v8;
    *(_OWORD *)&v223[v9] = *(_OWORD *)v4;
    v10 = *((_OWORD *)v4 + 2);
    v4 = (__int64 *)((char *)v4 + 52);
    *(_OWORD *)&v223[v9 + 16] = v7;
    *(_OWORD *)&v223[v9 + 32] = v10;
    *(_DWORD *)&v223[v9 + 48] = v6;
  }
  while ( (__int64)v4 < (__int64)"MMMM" );
  *((_DWORD *)this + 136) = -1;
  v11 = (char *)this + 268;
  *((_DWORD *)this + 12) = -1;
  v12 = (char *)this + 204;
  *((_DWORD *)this + 95349) = -1;
  *((_WORD *)this + 190709) = 0;
  *((_DWORD *)this + 95376) = 0;
  *((_WORD *)this + 190675) = 0;
  v13 = v3 + 147;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 38222) = 0;
  *((_BYTE *)this + 268) = 0;
  *((_BYTE *)this + 204) = 0;
  *((_BYTE *)this + 620) = 0;
  *((_BYTE *)this + 153312) = 0;
  *((_BYTE *)this + 193140) = 0;
  *((_BYTE *)this + 192628) = 0;
  *((_QWORD *)this + 47672) = 0;
  *((_DWORD *)this + 95348) = 0;
  *((_DWORD *)this + 131) = 0;
  *((_QWORD *)this + 24054) = 0;
  *((_QWORD *)this + 24053) = 0;
  *((_QWORD *)this + 47958) = 0;
  *((_QWORD *)this + 47959) = 0;
  *((_QWORD *)this + 47960) = 0;
  *((_WORD *)this + 1390) = 0;
  *((_BYTE *)this + 460) = 0;
  *((_BYTE *)this + 396) = 0;
  *((_DWORD *)this + 95915) = 0;
  memset((char *)this + 432944, 0, 0x8254u);
  memset((char *)this + 466312, 0, 0x496A8u);
  *((_WORD *)this + 191828) = 0;
  *((_QWORD *)this + 47956) = -1;
  v14 = 10;
  *(_QWORD *)((char *)this + 2596) = -1;
  v15 = this;
  *((_QWORD *)this + 47684) = -1;
  v16 = 0;
  *((_DWORD *)this + 954) = 1065353216;
  *((_DWORD *)this + 1154) = -998637568;
  *((_DWORD *)this + 1153) = -998637568;
  *((_DWORD *)this + 1152) = -998637568;
  *((_DWORD *)this + 1151) = -998637568;
  *((_DWORD *)this + 1150) = -998637568;
  *((_DWORD *)this + 1149) = -998637568;
  *((_DWORD *)this + 1148) = -998637568;
  *((_DWORD *)this + 48105) = 255;
  do
  {
    *(_WORD *)((char *)this + v16 + 433256) = -1;
    v15 = (LibRaw *)((char *)v15 + 33408);
    *(_WORD *)((char *)this + v16 + 433088) = -1;
    v16 += 33408;
    *((_DWORD *)v15 + 108225) = 1065353216;
    *(_DWORD *)((char *)this + v16 + 432904) = 1065353216;
    *(_DWORD *)((char *)this + v16 + 432908) = 1065353216;
    *(_DWORD *)((char *)this + v16 + 432912) = 1065353216;
    --v14;
  }
  while ( v14 );
  *(_OWORD *)((char *)this + 192452) = 0;
  *(_OWORD *)((char *)this + 192468) = 0;
  *(_OWORD *)((char *)this + 192484) = 0;
  *(_OWORD *)((char *)this + 192500) = 0;
  *(_OWORD *)((char *)this + 192516) = 0;
  *(_OWORD *)((char *)this + 192532) = 0;
  *(_OWORD *)((char *)this + 192548) = 0;
  *(_OWORD *)((char *)this + 192564) = 0;
  memset((char *)this + 136464, 0, 0x4020u);
  v17 = (float *)((char *)this + 153060);
  *(_OWORD *)((char *)this + 152916) = 0;
  v18 = 0;
  *(_OWORD *)((char *)this + 152932) = 0;
  *(_OWORD *)((char *)this + 152948) = 0;
  *(_OWORD *)((char *)this + 152964) = 0;
  *(_OWORD *)((char *)this + 152980) = 0;
  *(_OWORD *)((char *)this + 152996) = 0;
  *(_OWORD *)((char *)this + 153012) = 0;
  *(_OWORD *)((char *)this + 153028) = 0;
  *(_OWORD *)((char *)this + 52) = 0;
  *(_OWORD *)((char *)this + 68) = 0;
  *(_OWORD *)((char *)this + 84) = 0;
  *(_OWORD *)((char *)this + 100) = 0;
  *(_OWORD *)((char *)this + 116) = 0;
  *(_OWORD *)((char *)this + 132) = 0;
  *(_OWORD *)((char *)this + 148) = 0;
  *(_OWORD *)((char *)this + 164) = 0;
  *(_QWORD *)((char *)this + 193228) = 0;
  *((_QWORD *)this + 47664) = 0;
  *((_QWORD *)this + 95898) = 0;
  *((_DWORD *)this + 95375) = 4;
  *((_QWORD *)this + 47689) = 0;
  *((_DWORD *)this + 95371) = 0;
  *((_QWORD *)this + 47681) = 0;
  *((_QWORD *)this + 47680) = 0;
  *((_QWORD *)this + 47692) = 0;
  *(_QWORD *)((char *)this + 532) = 0;
  *(_QWORD *)((char *)this + 381524) = 0;
  *((_DWORD *)this + 95356) = 0;
  *((_DWORD *)this + 38220) = 0;
  *((_DWORD *)this + 95377) = 0;
  *((_DWORD *)this + 48112) = 0;
  *((_QWORD *)this + 24055) = 0;
  *(_QWORD *)((char *)this + 381340) = 1;
  *((_DWORD *)this + 38416) = 0;
  *((_DWORD *)this + 95334) = 0;
  *((_DWORD *)this + 132) = 1;
  *((_QWORD *)this + 5) = 0x3FF0000000000000LL;
  *((_DWORD *)this + 95383) = 0;
  *((_DWORD *)this + 95350) = 0;
  do
  {
    *(++v17 - 5) = (float)(v18 == 1);
    *(v17 - 1) = (float)((unsigned int)v18 < 3);
    v17[3] = 0.0;
    v17[7] = 0.0;
    v17[11] = 0.0;
    v17[27] = (float)(v18 == 0);
    v19 = (float)(v18 == 1);
    v20 = v18++ == 2;
    v17[31] = v19;
    v17[35] = (float)v20;
  }
  while ( v18 < 4 );
  *((_DWORD *)this + 135) = 3;
  v21 = (_WORD *)((char *)this + 5392);
  for ( i = 0; i < 0x10000; ++i )
    *v21++ = i;
  *((_WORD *)this + 190704) = LibRaw::get2(this);
  v23 = (int)LibRaw::get4(this);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(*((_QWORD *)this + 47659), 0, 0);
  if ( (*(int (__fastcall **)(_QWORD, char *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
         *((_QWORD *)this + 47659),
         Str1,
         1,
         64) < 64 )
  {
    pExceptionObject = 5;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  v24 = *((_QWORD *)this + 47659);
  *((_QWORD *)this + 47694) = 0;
  *((_DWORD *)this + 95390) = 0;
  (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v24 + 24LL))(v24, 0, 2);
  v218 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 32LL))(*((_QWORD *)this + 47659));
  if ( (unsigned __int64)v218 > 0x7FFFFFFF )
  {
    pExceptionObject = 10;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  *(_QWORD *)v214 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 32LL))(*((_QWORD *)this + 47659));
  pExceptionObject = v214[0];
  v25 = (char *)LibRaw::memmem(Str1, 0x20u, "MMMM", 4u);
  if ( v25 || (v25 = (char *)LibRaw::memmem(Str1, 0x20u, "IIII", 4u)) != 0 )
  {
    LibRaw::parse_phase_one(this, (_DWORD)v25 - (unsigned int)Str1);
    if ( v25 == Str1 )
      goto LABEL_120;
    v80 = this;
LABEL_118:
    if ( !(unsigned int)LibRaw::parse_tiff(v80, 0) )
      goto LABEL_120;
LABEL_119:
    LibRaw::apply_tiff(this);
    goto LABEL_120;
  }
  v26 = *((_WORD *)this + 190704);
  if ( v26 == 18761 || v26 == 19789 )
  {
    v79 = memcmp(&Str1[6], "HEAPCCDR", 8u);
    v80 = this;
    if ( !v79 )
    {
      v81 = v214[0] - v23;
      *((_QWORD *)this + 47680) = v23;
      LibRaw::parse_ciff(this, v23, v81, 0);
      *((_QWORD *)this + 95898) = LibRaw::canon_load_raw;
      goto LABEL_120;
    }
    goto LABEL_118;
  }
  v27 = 0;
  while ( 1 )
  {
    v28 = Str1[v27++];
    if ( v28 != *((_BYTE *)&dword_1800CC9CC + v27 - 1) )
      break;
    if ( v27 == 4 )
    {
      v29 = 0;
      goto LABEL_20;
    }
  }
  v29 = v28 < *((_BYTE *)&dword_1800CC9CC + v27 - 1) ? -1 : 1;
LABEL_20:
  if ( !v29 )
  {
    v30 = 0;
    while ( 1 )
    {
      v31 = Str1[v30++ + 6];
      if ( v31 != Str2[v30 - 1] )
        break;
      if ( v30 == 4 )
      {
        v32 = 0;
        goto LABEL_26;
      }
    }
    v32 = v31 < (unsigned int)Str2[v30 - 1] ? -1 : 1;
LABEL_26:
    if ( !v32 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
        *((_QWORD *)this + 47659),
        4,
        0);
      v33 = LibRaw::get2(this);
      v34 = *((_QWORD *)this + 47659);
      v35 = v33 + 4LL;
      *((_QWORD *)this + 47680) = v35;
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v34 + 24LL))(v34, v35, 0);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659)) != 255 )
        LibRaw::parse_tiff(this, 12);
      *((_QWORD *)this + 47664) = 0;
      goto LABEL_120;
    }
  }
  if ( memcmp((char *)&Buf1.m128i_u64[1] + 1, "ARECOYK", 7u) )
  {
    if ( !strcmp_0(Str1, "PXN") )
    {
      strcpy((char *)this + 204, "Logitech");
      strcpy(v11, "Fotoman Pixtura");
      goto LABEL_120;
    }
    if ( !strcmp_0(Str1, "qktk") )
    {
      strcpy((char *)this + 204, "Apple");
      strcpy((char *)this + 268, "QuickTake 100");
      *((_QWORD *)this + 95898) = LibRaw::quicktake_100_load_raw;
      goto LABEL_120;
    }
    if ( !strcmp_0(Str1, "qktn") )
    {
      strcpy((char *)this + 204, "Apple");
      strcpy((char *)this + 268, "QuickTake 150");
      *((_QWORD *)this + 95898) = LibRaw::kodak_radc_load_raw;
      goto LABEL_120;
    }
    if ( !memcmp(Str1, "FUJIFILM", 8u) )
    {
      v36 = Buf1;
      *(_QWORD *)((char *)this + 2782) = Buf1.m128i_i64[0];
      *(_DWORD *)((char *)this + 2790) = _mm_cvtsi128_si32(_mm_srli_si128(v36, 8));
      *((_BYTE *)this + 2794) = 0;
      *(_DWORD *)((char *)this + 2795) = *((_DWORD *)this + 697);
      *((_BYTE *)this + 2799) = 0;
      strncpy_0((char *)this + 268, &Buf1.m128i_i8[12], 0x20u);
      v37 = (char *)this + 2793;
      *((_BYTE *)this + 300) = 0;
      v38 = 11;
      if ( *((char *)this + 2793) > 0 )
      {
        v39 = *((_BYTE *)this + 2793);
        do
        {
          if ( !isdigit_0(v39) )
            break;
          if ( (__int64)&v37[-2782LL - (_QWORD)this] <= 0 )
            break;
          v39 = *--v37;
          --v38;
        }
        while ( v39 > 0 );
        if ( v38 < 11 )
          *((_QWORD *)this + 47672) = atoi_0((const char *)this + v38 + 2783);
      }
      *((_DWORD *)this + 700) = HIDWORD(v226);
      *((_BYTE *)this + 2804) = 0;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
        *((_QWORD *)this + 47659),
        84,
        0);
      *((_QWORD *)this + 47664) = LibRaw::get4(this);
      v40 = LibRaw::get4(this);
      v41 = *((_QWORD *)this + 47659);
      *((_DWORD *)this + 48308) = v40;
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v41 + 24LL))(v41, 92, 0);
      v42 = LibRaw::get4(this);
      LibRaw::parse_fuji(this, v42);
      if ( *((__int64 *)this + 47664) > 120 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
          *((_QWORD *)this + 47659),
          120,
          0);
        v43 = LibRaw::get4(this);
        *((_DWORD *)this + 132) += v43 != 0;
        if ( *((_DWORD *)this + 132) == 2 )
        {
          if ( *((_DWORD *)this + 1337) )
            LibRaw::parse_fuji(this, v43);
        }
      }
      v44 = *((_QWORD *)this + 47659);
      *((_QWORD *)this + 95898) = LibRaw::unpacked_load_raw;
      v45 = 100;
      if ( *((_DWORD *)this + 1337) )
        v45 = 128;
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v44 + 24LL))(v44, v45, 0);
      v46 = LibRaw::get4(this);
      *((_QWORD *)this + 47680) = v46;
      LibRaw::parse_tiff(this, v46);
      LibRaw::parse_tiff(this, *((_DWORD *)this + 95328) + 12);
      LibRaw::parse_fuji_thumbnail(this, *((_DWORD *)this + 95328));
      goto LABEL_119;
    }
    v47 = 0;
    while ( 1 )
    {
      v48 = Str1[v47++];
      if ( v48 != aRiff[v47 - 1] )
        break;
      if ( v47 == 4 )
      {
        v49 = 0;
        goto LABEL_58;
      }
    }
    v49 = v48 < (unsigned __int8)aRiff[v47 - 1] ? -1 : 1;
LABEL_58:
    if ( !v49 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
        *((_QWORD *)this + 47659),
        0,
        0);
      LibRaw::parse_riff(this, 100);
      goto LABEL_120;
    }
    if ( !memcmp(&Str1[4], "ftypqt   ", 9u) )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
        *((_QWORD *)this + 47659),
        0,
        0);
      v50 = v214[0];
      LibRaw::parse_qt(this, v214[0]);
      *((_DWORD *)this + 132) = 0;
      goto LABEL_121;
    }
    v51 = 0;
    while ( 1 )
    {
      v52 = Str1[v51++];
      if ( v52 != *((_BYTE *)&dword_1800CCA4C + v51 - 1) )
        break;
      if ( v51 == 6 )
      {
        v53 = 0;
        goto LABEL_67;
      }
    }
    v53 = v52 < *((_BYTE *)&dword_1800CCA4C + v51 - 1) ? -1 : 1;
LABEL_67:
    if ( !v53 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
        *((_QWORD *)this + 47659),
        6,
        0);
      (*(void (__fastcall **)(_QWORD, char *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
        *((_QWORD *)this + 47659),
        (char *)this + 204,
        1,
        8);
      (*(void (__fastcall **)(_QWORD, char *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
        *((_QWORD *)this + 47659),
        (char *)this + 268,
        1,
        8);
      (*(void (__fastcall **)(_QWORD, char *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
        *((_QWORD *)this + 47659),
        (char *)this + 153312,
        1,
        16);
      *((_QWORD *)this + 47680) = LibRaw::get2(this);
      LibRaw::get2(this);
      *((_WORD *)this + 9) = LibRaw::get2(this);
      *((_WORD *)this + 8) = LibRaw::get2(this);
      *((_QWORD *)this + 95898) = LibRaw::nokia_load_raw;
      *((_DWORD *)this + 136) = 1633771873;
      goto LABEL_120;
    }
    if ( memcmp(Str1, "NOKIARAW", 8u) )
    {
      if ( !memcmp(Str1, "DSC-Image", 9u) )
      {
        LibRaw::parse_rollei(this);
      }
      else
      {
        v64 = 0;
        while ( 1 )
        {
          v65 = Str1[v64++];
          if ( v65 != aPwad[v64 - 1] )
            break;
          if ( v64 == 4 )
          {
            v66 = 0;
            goto LABEL_88;
          }
        }
        v66 = v65 < (unsigned __int8)aPwad[v64 - 1] ? -1 : 1;
LABEL_88:
        if ( v66 )
        {
          v67 = 0;
          while ( 1 )
          {
            v68 = Str1[v67++];
            if ( v68 != *((_BYTE *)&dword_1800CCA84 + v67 - 1) )
              break;
            if ( v67 == 4 )
            {
              v69 = 0;
              goto LABEL_95;
            }
          }
          v69 = v68 < *((_BYTE *)&dword_1800CCA84 + v67 - 1) ? -1 : 1;
LABEL_95:
          if ( v69 )
          {
            v70 = 0;
            while ( 1 )
            {
              v71 = Str1[v70++];
              if ( v71 != aFovb[v70 - 1] )
                break;
              if ( v70 == 4 )
              {
                v72 = 0;
                goto LABEL_102;
              }
            }
            v72 = v71 < (unsigned __int8)aFovb[v70 - 1] ? -1 : 1;
LABEL_102:
            if ( v72 )
            {
              v73 = Str1[0] < 0x43u;
              if ( Str1[0] == 67 && (v73 = Str1[1] < 0x49u, Str1[1] == 73) )
                v74 = 0;
              else
                v74 = v73 ? -1 : 1;
              if ( v74 )
              {
                if ( !memcmp(&Str1[4], "ftypcrx ", 8u) )
                {
                  v75 = *((_QWORD *)this + 47659);
                  v216 = -1;
                  v215[0] = -1;
                  strcpy((char *)this + 204, "Canon");
                  v76 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v75 + 40LL))(v75);
                  v77 = LibRaw::parseCR3(this, 0, v76, &v216, v227, v215, &v217);
                  v78 = v215[0];
                  *((_DWORD *)this + 95913) = v215[0];
                  if ( (!v77 || v77 == -14) && v78 >= 0 )
                    LibRaw::selectCRXTrack(this);
                }
              }
              else
              {
                LibRaw::parse_cine(this);
              }
            }
          }
          else
          {
            LibRaw::parse_minolta(this, 0);
          }
        }
        else
        {
          LibRaw::parse_sinar_ia(this);
        }
      }
      goto LABEL_120;
    }
    v54 = *((_QWORD *)this + 47659);
    strcpy((char *)this + 204, "NOKIA");
    *((_WORD *)this + 190704) = 18761;
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v54 + 24LL))(v54, 300, 0);
    *((_QWORD *)this + 47680) = LibRaw::get4(this);
    v55 = LibRaw::get4(this);
    *((_WORD *)this + 11) = LibRaw::get2(this);
    v56 = LibRaw::get2(this);
    v57 = *((unsigned __int16 *)this + 11);
    *((_WORD *)this + 10) = v56;
    if ( (unsigned __int16)(v57 - 1) > 0x3E7Fu
      || (unsigned __int16)(v56 - 1) > 0x3E7Fu
      || (v58 = v57, v59 = v57 * v56, v55 < v57 * v56)
      || v55 > 2 * v59 )
    {
      pExceptionObject = 5;
      throw (LibRaw_exceptions *)&pExceptionObject;
    }
    v60 = 8 * v55 / v59;
    *((_DWORD *)this + 95378) = v60;
    v61 = v60;
    switch ( v60 )
    {
      case 0:
        pExceptionObject = 5;
        throw (LibRaw_exceptions *)&pExceptionObject;
      case 8:
        v62 = LibRaw::eight_bit_load_raw;
        break;
      case 10:
        v62 = LibRaw::nokia_load_raw;
        break;
      default:
LABEL_80:
        v63 = v55 / ((unsigned int)(v58 * v61) >> 3);
        *((_WORD *)this + 8) = v63;
        *((_WORD *)this + 12) = v63 - v56;
        *((_DWORD *)this + 16) = 1;
        *((_DWORD *)this + 136) = 1633771873;
        goto LABEL_120;
    }
    *((_QWORD *)this + 95898) = v62;
    goto LABEL_80;
  }
  strcpy((char *)this + 204, "Contax");
  strcpy((char *)this + 268, "N Digital");
  LibRaw::parse_kyocera(this);
LABEL_120:
  v50 = v214[0];
LABEL_121:
  if ( *v12 )
  {
    v84 = 0;
    goto LABEL_126;
  }
  v82 = 0;
  if ( v13 > 0 )
  {
    while ( 1 )
    {
      v83 = 52LL * v82;
      if ( v50 == *(_DWORD *)&v223[v83] )
        break;
      if ( (int)++v82 >= v13 )
        goto LABEL_125;
    }
    strcpy_0((char *)this + 204, &v223[v83 + 17]);
    strcpy_0((char *)this + 268, &v223[v83 + 27]);
    v86 = 0;
    v87 = *(unsigned __int16 *)&v223[v83 + 48];
    v88 = (unsigned __int8)v223[v83 + 16];
    v89 = *(unsigned __int16 *)&v223[v83 + 4];
    v90 = (unsigned __int8)v223[v83 + 8];
    v91 = *(unsigned __int16 *)&v223[v83 + 6];
    v92 = (unsigned __int8)v223[v83 + 9];
    *((_DWORD *)this + 12) = v88 >> 2;
    *((_DWORD *)this + 95336) = v88 & 2;
    v93 = (unsigned __int8)v223[v83 + 10];
    if ( (_WORD)v87 != 0xFFFF )
      v86 = v87;
    *((_WORD *)this + 9) = v89;
    v94 = v89 - v93;
    *((_QWORD *)this + 47680) = v86;
    v95 = (unsigned __int8)v223[v83 + 11];
    *((_WORD *)this + 11) = v94 - v90;
    v96 = v91 - v95;
    *((_WORD *)this + 8) = v91;
    v97 = (unsigned __int8)v223[v83 + 14];
    *((_WORD *)this + 10) = v96 - v92;
    *((_WORD *)this + 13) = v90;
    *((_WORD *)this + 12) = v92;
    *((_DWORD *)this + 136) = 16843009 * v97;
    *((_DWORD *)this + 135) = (((unsigned __int16)(257 * v97)
                              & (unsigned __int16)((unsigned int)(16843009 * v97) >> 1)
                              & 0x5555) != 0)
                            + 3;
    LOWORD(v97) = *(_WORD *)&v223[v83 + 12];
    v98 = (unsigned __int8)v97;
    *((_DWORD *)this + 95384) = (unsigned __int8)v97;
    if ( (v97 & 0x100) != 0 )
      *(_QWORD *)((char *)this + 540) = 1;
    v99 = v89;
    v100 = v214[0] - v86;
    v101 = 8 * v100 / (v99 * (int)v91);
    *((_DWORD *)this + 95378) = v101;
    v102 = v101;
    if ( (_DWORD)v101 == 6 )
    {
      *((_QWORD *)this + 95898) = LibRaw::minolta_rd175_load_raw;
      *((_WORD *)this + 677) = 25;
      goto LABEL_157;
    }
    if ( (_DWORD)v101 == 8 )
    {
      *((_QWORD *)this + 95898) = LibRaw::eight_bit_load_raw;
      goto LABEL_157;
    }
    if ( (_DWORD)v101 != 10 )
    {
      if ( (_DWORD)v101 != 12 )
      {
        if ( (_DWORD)v101 == 16 )
        {
          v103 = (v98 >> 1) & 7;
          *((_DWORD *)this + 95384) = v103;
          v104 = 16 - (v98 >> 4) - v103;
          *((_DWORD *)this + 95378) = v104;
          *((_WORD *)this + 190704) = (1028 * (v98 & 1)) | 0x4949;
          v105 = LibRaw::unpacked_load_raw;
          v102 = v104;
          if ( (_WORD)v87 == 0xFFFF )
            v105 = LibRaw::unpacked_load_raw_reversed;
          *((_QWORD *)this + 95898) = v105;
        }
        goto LABEL_157;
      }
      goto LABEL_154;
    }
    if ( 3 * (v100 / v91) < (unsigned int)(4 * v99) )
    {
      if ( (v98 & 1) == 0 )
      {
LABEL_154:
        *((_DWORD *)this + 95384) = v98 | 0x80;
        *((_QWORD *)this + 95898) = LibRaw::packed_load_raw;
        goto LABEL_157;
      }
      *((_QWORD *)this + 95898) = LibRaw::android_tight_load_raw;
    }
    else
    {
      *((_QWORD *)this + 95898) = LibRaw::android_loose_load_raw;
    }
LABEL_157:
    *((_DWORD *)this + 38222) = (1 << v102) - (1 << v223[v83 + 15]);
  }
LABEL_125:
  v84 = v214[0];
LABEL_126:
  if ( !*v12 )
  {
    if ( v218 < 25000000 )
      LibRaw::parse_smal(this, 0, pExceptionObject);
    if ( !*v12 )
    {
      LibRaw::parse_jpeg(this, 0);
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 47659) + 24LL))(
        *((_QWORD *)this + 47659),
        0,
        2);
      v85 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 32LL))(*((_QWORD *)this + 47659));
      if ( !strncmp_0((const char *)this + 268, "RP_imx219", 9u)
        && v85 >= 10270208
        && !(*(unsigned int (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 47659) + 24LL))(
              *((_QWORD *)this + 47659),
              -10270208,
              2)
        && (*(unsigned int (__fastcall **)(_QWORD, char *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
             *((_QWORD *)this + 47659),
             Str1,
             1,
             32)
        && !strncmp_0(Str1, "BRCM", 4u) )
      {
        strcpy((char *)this + 204, "Broadcom");
        strcpy((char *)this + 268, "RPi IMX219");
        if ( *((_WORD *)this + 8) > *((_WORD *)this + 9) )
          *((_DWORD *)this + 12) = 5;
        *((_QWORD *)this + 47680) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 32LL))(*((_QWORD *)this + 47659))
                                  + 32736;
        LibRaw::parse_broadcom(this);
        *((_DWORD *)this + 38220) = 66;
        *((_QWORD *)this + 95898) = LibRaw::broadcom_load_raw;
        *((_DWORD *)this + 48308) = v85 - 10270209;
        *((_DWORD *)this + 38222) = 1023;
        *((_QWORD *)this + 47664) = 0;
      }
      else if ( (!strncmp_0((const char *)this + 268, "ov5647", 6u)
              || !strncmp_0((const char *)this + 268, "RP_OV5647", 9u))
             && v85 >= 6404096
             && !(*(unsigned int (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 47659) + 24LL))(
                   *((_QWORD *)this + 47659),
                   -6404096,
                   2)
             && (*(unsigned int (__fastcall **)(_QWORD, char *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
                  *((_QWORD *)this + 47659),
                  Str1,
                  1,
                  32)
             && !strncmp_0(Str1, "BRCM", 4u) )
      {
        strcpy((char *)this + 204, "Broadcom");
        if ( !strncmp_0((const char *)this + 268, "ov5647", 6u) )
        {
          qmemcpy((char *)this + 268, "RPi OV5647 v.1", 14);
          v106 = aRpiOv5647V1[14];
        }
        else
        {
          qmemcpy((char *)this + 268, "RPi OV5647 v.2", 14);
          v106 = aRpiOv5647V2[14];
        }
        *((_BYTE *)this + 282) = v106;
        if ( *((_WORD *)this + 8) > *((_WORD *)this + 9) )
          *((_DWORD *)this + 12) = 5;
        *((_QWORD *)this + 47680) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 32LL))(*((_QWORD *)this + 47659))
                                  + 32736;
        LibRaw::parse_broadcom(this);
        *((_DWORD *)this + 38220) = 16;
        *((_QWORD *)this + 95898) = LibRaw::broadcom_load_raw;
        *((_DWORD *)this + 48308) = v85 - 6404097;
        *((_DWORD *)this + 38222) = 1023;
        *((_QWORD *)this + 47664) = 0;
      }
      else
      {
        *((_DWORD *)this + 132) = 0;
      }
    }
  }
  *((_BYTE *)this + 153375) = 0;
  *((_BYTE *)this + 331) = 0;
  v107 = 0;
  *((_BYTE *)this + 267) = 0;
  *((_BYTE *)this + 193203) = 0;
  *((_BYTE *)this + 193139) = 0;
  while ( !LibRaw::strcasestr((char *)this + 204, (const char *)qword_1800C2B40[2 * v107 + 1]) )
  {
    if ( (int)++v107 >= 78 )
      goto LABEL_177;
  }
  *((_DWORD *)this + 131) = qword_1800C2B40[2 * v107];
LABEL_177:
  v108 = *((_DWORD *)this + 131);
  if ( v108 != 75 )
  {
LABEL_181:
    if ( v108 == 28 )
    {
      if ( !strnicmp_0((const char *)this + 268, "Kodak", 5u) )
      {
        *((_DWORD *)this + 131) = 29;
        goto LABEL_188;
      }
      v108 = *((_DWORD *)this + 131);
    }
    if ( v108 == 56 && !strnicmp_0((const char *)this + 268, "PENTAX", 6u) )
      *((_DWORD *)this + 131) = 49;
    goto LABEL_188;
  }
  if ( strnicmp_0((const char *)this + 268, "Nokia", 5u) )
  {
    v108 = *((_DWORD *)this + 131);
    goto LABEL_181;
  }
  *((_DWORD *)this + 131) = 44;
LABEL_188:
  v109 = 0;
  while ( *((_DWORD *)this + 131) != LODWORD(qword_1800C2B40[2 * v109]) )
  {
    if ( (int)++v109 >= 78 )
      goto LABEL_193;
  }
  strcpy_0((char *)this + 204, (const char *)qword_1800C2B40[2 * v109 + 1]);
LABEL_193:
  v110 = *((_DWORD *)this + 131);
  if ( v110 == 29 || v110 == 32 )
  {
    v111 = LibRaw::strcasestr((char *)this + 268, " DIGITAL CAMERA");
    if ( v111 || (v111 = strstr((const char *)this + 268, "FILE VERSION")) != 0 )
      *v111 = 0;
  }
  LibRaw::remove_trailing_spaces((char *)this + 204, 0x40u);
  LibRaw::remove_trailing_spaces((char *)this + 268, 0x40u);
  v112 = LibRaw::strnlen((const char *)this + 204, 0x3Fu);
  v113 = v112;
  v114 = v112;
  if ( !strnicmp_0((const char *)this + 268, (const char *)this + 204, v112) && *((_BYTE *)this + v113 + 268) == 32 )
    memmove((char *)this + 268, (char *)this + v114 + 269, 64 - (v114 + 1));
  if ( *((_DWORD *)this + 131) == 18 && !strncmp_0((const char *)this + 268, "FinePix", 7u) )
  {
    v115 = strlen_0((const char *)this + 268);
    memmove((char *)this + 268, (char *)this + 275, v115 - 6);
    if ( *v11 != 32 )
      goto LABEL_210;
    v116 = strlen_0((const char *)this + 268);
    v117 = (char *)this + 269;
    v118 = v116;
    v119 = (char *)this + 268;
    goto LABEL_209;
  }
  v120 = *((_DWORD *)this + 131);
  if ( (v120 == 29 || v120 == 30) && !strncmp_0((const char *)this + 268, "Digital Camera ", 0xFu) )
  {
    v121 = strlen_0((const char *)this + 268);
    v117 = (char *)this + 283;
    v119 = (char *)this + 268;
    v118 = v121 - 14;
LABEL_209:
    memmove(v119, v117, v118);
  }
LABEL_210:
  *((_BYTE *)this + 153375) = 0;
  *((_BYTE *)this + 331) = 0;
  *((_BYTE *)this + 267) = 0;
  *((_BYTE *)this + 193203) = 0;
  *((_BYTE *)this + 193139) = 0;
  if ( !*((_DWORD *)this + 132) )
  {
LABEL_482:
    v207 = *((_DWORD *)this + 12);
    if ( v207 == -1 && (v207 = *((_DWORD *)this + 95349), *((_DWORD *)this + 12) = v207, v207 == -1) )
    {
      *((_DWORD *)this + 12) = 0;
    }
    else if ( (unsigned int)(v207 + 89) > 0xB2 )
    {
      v208 = (v207 + 3600) % 360 - 90;
      if ( v208 )
      {
        v209 = v208 - 90;
        if ( v209 )
        {
          if ( v209 == 90 )
            *((_DWORD *)this + 12) = 5;
        }
        else
        {
          *((_DWORD *)this + 12) = 3;
        }
      }
      else
      {
        *((_DWORD *)this + 12) = 6;
      }
    }
    v210 = *((_DWORD *)this + 95398);
    if ( !v210 )
    {
      v211 = (void (__fastcall *)(LibRaw *__hidden))*((_QWORD *)this + 95898);
      if ( v211 == LibRaw::phase_one_load_raw
        || v211 == LibRaw::phase_one_load_raw_s
        || v211 == LibRaw::phase_one_load_raw_c )
      {
        v210 = *((_DWORD *)this + 38317);
      }
      else
      {
        v210 = *((_DWORD *)this + 95378);
      }
    }
    *((_DWORD *)this + 48104) = v210;
    v212 = (unsigned int (__fastcall *)(_QWORD, __int64, __int64, __int64))*((_QWORD *)this + 95882);
    if ( v212 )
    {
      if ( v212(*((_QWORD *)this + 95883), 2, 1, 2) )
      {
        pExceptionObject = 6;
        throw (LibRaw_exceptions *)&pExceptionObject;
      }
    }
    return;
  }
  if ( !*((_WORD *)this + 10) )
    *((_WORD *)this + 10) = *((_WORD *)this + 8);
  if ( !*((_WORD *)this + 11) )
    *((_WORD *)this + 11) = *((_WORD *)this + 9);
  if ( !*((_DWORD *)this + 133) )
    goto LABEL_223;
  v122 = *((_QWORD *)this + 47680);
  if ( !v122 )
    goto LABEL_223;
  v123 = *((_DWORD *)this + 95348);
  v124 = 0;
  if ( v123 <= 0 )
    goto LABEL_223;
  v125 = (_DWORD *)((char *)this + 432964);
  while ( *v125 != v122 )
  {
    ++v124;
    v125 += 8352;
    if ( v124 >= v123 )
      goto LABEL_223;
  }
  if ( *((_DWORD *)this + 8352 * (unsigned int)v124 + 108240) != 34892 )
  {
LABEL_223:
    v126 = *((_DWORD *)this + 131);
    if ( v126 != 49 && v126 != 59 )
      goto LABEL_268;
    v127 = *((_WORD *)this + 10);
    if ( v127 == 2624 )
    {
      if ( *((_WORD *)this + 11) == 3936 )
        *((_DWORD *)this + 5) = 255330872;
    }
    else if ( v127 == 3136 && *((_WORD *)this + 11) == 4864 )
    {
      *((_DWORD *)this + 5) = 307235892;
      *((_DWORD *)this + 136) = 370546198;
    }
    if ( v126 == 49 )
    {
      v128 = *((_WORD *)this + 11);
      if ( v128 == 4352 )
      {
        v129 = *((_QWORD *)this + 47672);
        if ( v129 == 77420 || (v128 = 4352, v129 == 77310) )
        {
          *((_WORD *)this + 11) = 4309;
LABEL_236:
          *((_DWORD *)this + 136) = 370546198;
          goto LABEL_237;
        }
      }
      if ( (unsigned __int16)v128 >= 0x1360u )
      {
        v131 = *((_QWORD *)this + 47672);
        if ( v131 == 77430 || v131 == 77680 || v131 == 77681 )
        {
          *((_WORD *)this + 13) = 10;
          *((_WORD *)this + 11) = 4950;
          goto LABEL_236;
        }
      }
      if ( v128 == 6080 && (v128 = 6080, *((_QWORD *)this + 47672) == 78370) )
      {
        *((_DWORD *)this + 5) = 394530736;
        *((_DWORD *)this + 6) = 3932192;
      }
      else if ( v128 == 4736 && (v128 = 4736, *((_QWORD *)this + 47672) == 77240) )
      {
        *((_DWORD *)this + 5) = 306973746;
        *((_WORD *)this + 12) = 2;
        *((_DWORD *)this + 136) = 370546198;
      }
      else if ( v128 == 6080 && (v128 = 6080, *((_QWORD *)this + 47672) == 77980) )
      {
        *((_WORD *)this + 13) = 4;
        *((_WORD *)this + 11) = 6040;
      }
      else if ( v128 == 6304 && (v128 = 6304, *((_QWORD *)this + 47672) == 78420) )
      {
        *((_DWORD *)this + 6) = 1703970;
        *((_DWORD *)this + 5) = 407900224;
      }
      else if ( v128 == 6112 )
      {
        if ( *((_QWORD *)this + 47672) == 78380 )
        {
          v132 = *((_WORD *)this + 8) - 28;
          *((_DWORD *)this + 6) = 3538972;
          *((_WORD *)this + 10) = v132;
          *((_WORD *)this + 11) = 6028;
        }
      }
      else if ( v128 == 6080 )
      {
        if ( *((_QWORD *)this + 47672) == 77760 )
        {
          *((_WORD *)this + 13) = 4;
          *((_WORD *)this + 11) = 6040;
        }
      }
      else if ( v128 == 7424 && *((_QWORD *)this + 47672) == 77320 )
      {
        *((_DWORD *)this + 5) = 480253310;
        *((_DWORD *)this + 136) = 1633771873;
        *((_DWORD *)this + 6) = 3145757;
      }
    }
    else
    {
LABEL_268:
      if ( v126 == 56 && *((_WORD *)this + 10) == 3014 && *((_WORD *)this + 11) == 4096 )
        *((_WORD *)this + 11) = 4014;
    }
  }
LABEL_237:
  if ( *((_DWORD *)this + 133) )
  {
    v130 = *((_DWORD *)this + 136);
    if ( v130 == -1 )
    {
      *((_DWORD *)this + 136) = 0;
    }
    else if ( v130 )
    {
LABEL_272:
      v133 = *((_DWORD *)this + 95379);
      if ( v133 && (v134 = v133 - 1) != 0 )
      {
        v135 = v134 - 6;
        if ( v135 )
        {
          v136 = v135 - 1;
          if ( v136 )
          {
            if ( v136 == 34884 )
              *((_QWORD *)this + 95898) = guard_check_icall_nop;
            else
              *((_QWORD *)this + 95898) = 0;
            goto LABEL_292;
          }
          v137 = *((_DWORD *)this + 95380);
          if ( v137 == 3 )
          {
            v138 = *((_DWORD *)this + 95378);
            if ( v138 <= 8 || (v138 & 7) != 0 || v138 > 0x20 )
              goto LABEL_292;
LABEL_286:
            *((_QWORD *)this + 95898) = LibRaw::vc5_dng_load_raw_placeholder;
            goto LABEL_292;
          }
          if ( v137 <= 1 && (unsigned int)(*((_DWORD *)this + 95378) - 8) <= 8 )
            goto LABEL_286;
LABEL_292:
          LibRaw::GetNormalizedModel(this);
          v140 = *((_DWORD *)this + 131);
          if ( v140 == 32 )
          {
            if ( !strcmp_0((const char *)this + 268, "SL2") )
              *((_WORD *)this + 10) -= 3;
            if ( !strnicmp_0((const char *)this + 268, "Q2 MONO", 7u) )
              *((_WORD *)this + 10) -= 18;
          }
          else if ( v140 == 45
                 && *((_QWORD *)this + 47673) == 0x4434353732LL
                 && (strchr((const char *)this + 274, 115) || strchr((const char *)this + 274, 83)) )
          {
            *((_WORD *)this + 11) -= 16;
          }
          goto LABEL_302;
        }
        v139 = LibRaw::lossless_dng_load_raw;
      }
      else
      {
        if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::uncompressed_fp_dng_load_raw
          || *((_DWORD *)this + 95380) == 3 )
        {
          goto LABEL_292;
        }
        v139 = LibRaw::packed_dng_load_raw;
      }
      *((_QWORD *)this + 95898) = v139;
      goto LABEL_292;
    }
    *((_DWORD *)this + 135) = *((_DWORD *)this + 95377);
    goto LABEL_272;
  }
  if ( *((_DWORD *)this + 131) != 8 || v84 )
  {
    switch ( v84 )
    {
      case 4771840:
        if ( !*((_QWORD *)this + 24055) && (unsigned int)LibRaw::nikon_e995(this) )
          strcpy((char *)this + 268, "E995");
        break;
      case 2940928:
        if ( !*((_QWORD *)this + 24055) && !(unsigned int)LibRaw::nikon_e2100(this) )
          strcpy((char *)this + 268, "E2500");
        break;
      case 4775936:
        if ( !*((_QWORD *)this + 24055) )
          LibRaw::nikon_3700(this);
        break;
      default:
        if ( v84 == 5869568 && !*((_QWORD *)this + 24055) && (unsigned int)LibRaw::minolta_z2(this) )
        {
          *((_DWORD *)this + 131) = 40;
          strcpy((char *)this + 204, "Minolta");
          strcpy((char *)this + 268, "DiMAGE Z2");
        }
        break;
    }
  }
  else if ( *((_DWORD *)this + 95378) != 15 )
  {
    v166 = 0;
    if ( !*((_QWORD *)this + 95898) )
      *((_QWORD *)this + 95898) = LibRaw::lossless_jpeg_load_raw;
    v167 = word_1800CA742;
    v168 = 53;
    do
    {
      v169 = *((unsigned __int16 *)this + 9);
      if ( (_WORD)v169 == *(v167 - 1) )
      {
        v170 = *((_WORD *)this + 8);
        if ( v170 == *v167 )
        {
          v171 = v167[1];
          v172 = v167[2];
          v173 = v170 - v167[4];
          *((_WORD *)this + 11) = v169 - v167[3] - v171;
          v174 = (unsigned __int16)v167[5];
          *((_WORD *)this + 13) = v171;
          *((_WORD *)this + 12) = v172;
          *((_WORD *)this + 10) = v173 - v172;
          *((_DWORD *)this + 14) = v174;
          *((_DWORD *)this + 16) = -(unsigned __int16)v167[6];
          *((_DWORD *)this + 18) = (unsigned __int16)v167[7];
          *((_DWORD *)this + 20) = -(unsigned __int16)v167[8];
          v175 = (unsigned __int16)v167[9];
          if ( (_WORD)v175 )
            *((_DWORD *)this + 136) = 16843009 * v175;
          v166 = 1;
        }
      }
      v167 += 11;
      --v168;
    }
    while ( v168 );
    if ( (*((_QWORD *)this + 47672) | 0x20000LL) == 0x2720000 )
      *((_DWORD *)this + 6) = 524304;
    if ( !v166 )
    {
      if ( *((_DWORD *)this + 492) )
      {
        *((_DWORD *)this + 34116) = *((_DWORD *)this + 488);
        *((_DWORD *)this + 34117) = *((_DWORD *)this + 489);
        *((_DWORD *)this + 34118) = *((_DWORD *)this + 490);
        *((_DWORD *)this + 34119) = *((_DWORD *)this + 491);
        *((_QWORD *)this + 17060) = 0;
        *((_DWORD *)this + 38220) = 0;
        *((_DWORD *)this + 16) = 1;
        *((_DWORD *)this + 14) = 2;
        if ( *((__int16 *)this + 1008) == v169 && *((__int16 *)this + 1009) == *((unsigned __int16 *)this + 8) )
        {
          v176 = (*((_WORD *)this + 1031) + 1) & 0xFFFE;
          *((_WORD *)this + 13) = v176;
          *((_WORD *)this + 11) = *((_WORD *)this + 1033) - v176;
          v177 = (*((_WORD *)this + 1030) + 1) & 0xFFFE;
          *((_WORD *)this + 12) = v177;
          *((_WORD *)this + 10) = *((_WORD *)this + 1032) - v177;
        }
      }
    }
  }
  if ( !strcmp_0((const char *)this + 268, "KAI-0340") && LibRaw::find_green(this, 16, 16, 3840, 5120) < 25.0 )
  {
    *((_WORD *)this + 10) = 480;
    *((_DWORD *)this + 136) = 0;
    *((_WORD *)this + 12) = 0;
    strcpy((char *)this + 268, "C603");
  }
  LibRaw::GetNormalizedModel(this);
  LibRaw::identify_finetune_dcr(this, Str1, v84, pExceptionObject);
  v178 = (void (__fastcall __noreturn *)(LibRaw *__hidden))*((_QWORD *)this + 95898);
  if ( v178 )
  {
    v179 = *((unsigned __int16 *)this + 10);
    if ( v179 >= 0x16 )
    {
      v180 = *((unsigned __int16 *)this + 11);
      if ( v180 >= 0x16
        && (*((_DWORD *)this + 95378) <= 0x10u
         || v178 == LibRaw::vc5_dng_load_raw_placeholder
         || (char *)v178 == (char *)LibRaw::uncompressed_fp_dng_load_raw)
        && *((_DWORD *)this + 95377) <= 4u
        && (unsigned int)(*((_DWORD *)this + 135) - 1) <= 3
        && v180 + *((unsigned __int16 *)this + 13) <= 0xFFFF )
      {
        v181 = *((unsigned __int16 *)this + 10);
        if ( v179 + *((unsigned __int16 *)this + 12) <= 0xFFFF )
        {
          if ( !*((_BYTE *)this + 268) )
          {
            sprintf((char *const)this + 268, "%dx%d", v180, v181);
            strcpy_0((char *)this + 460, (const char *)this + 268);
          }
          if ( (*((_DWORD *)this + 1336) & 0x100) != 0 )
          {
            if ( *((_DWORD *)this + 136) != -1 )
              goto LABEL_401;
            if ( *((_DWORD *)this + 95348) && *((_DWORD *)this + 95377) == 1 )
            {
              *(_QWORD *)((char *)this + 540) = 1;
              goto LABEL_401;
            }
          }
          else if ( *((_DWORD *)this + 136) != -1 )
          {
LABEL_401:
            v182 = *((_QWORD *)this + 47664);
            if ( v182 )
            {
              if ( !*((_WORD *)this + 96615) )
              {
                (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**((_QWORD **)this + 47659) + 24LL))(
                  *((_QWORD *)this + 47659),
                  v182,
                  0,
                  v181);
                if ( (unsigned int)LibRaw::ljpeg_start(this, (struct jhead *)v219, 1) )
                {
                  *((_WORD *)this + 96614) = v221;
                  *((_WORD *)this + 96615) = v220;
                }
              }
            }
LABEL_302:
            if ( *((_DWORD *)this + 133) )
              LibRaw::identify_process_dng_fields(this);
            v141 = (void (__fastcall __noreturn *)(LibRaw *__hidden))*((_QWORD *)this + 95898);
            if ( !v141 || *((_WORD *)this + 10) < 0x16u || *((_WORD *)this + 11) < 0x16u )
              goto LABEL_476;
            v142 = *((_DWORD *)this + 95378);
            if ( v142 > 0x10 )
            {
              if ( v141 == LibRaw::vc5_dng_load_raw_placeholder )
              {
LABEL_312:
                if ( v142 - 16 <= 0x10 && (v142 & 7) == 0 )
                  goto LABEL_314;
LABEL_476:
                *((_DWORD *)this + 132) = 0;
                v205 = (unsigned int (__fastcall *)(_QWORD, __int64, __int64, __int64))*((_QWORD *)this + 95882);
                if ( v205 && v205(*((_QWORD *)this + 95883), 2, 1, 2) )
                {
                  pExceptionObject = 6;
                  throw (LibRaw_exceptions *)&pExceptionObject;
                }
                return;
              }
              if ( (char *)v141 != (char *)LibRaw::uncompressed_fp_dng_load_raw )
                goto LABEL_476;
            }
            if ( v141 != LibRaw::vc5_dng_load_raw_placeholder
              && (char *)v141 != (char *)LibRaw::uncompressed_fp_dng_load_raw )
            {
LABEL_314:
              if ( *((_DWORD *)this + 95377) <= 4u )
              {
                v143 = *((_DWORD *)this + 135);
                if ( (unsigned int)(v143 - 1) <= 3 )
                {
                  v144 = 1;
                  v145 = 0;
                  if ( v143 > 0 )
                  {
                    v146 = (float *)((char *)this + 153044);
                    v147 = 0;
                    do
                    {
                      if ( v147 >= 4 )
                        break;
                      v148 = 0;
                      if ( *v146 > 0.001 )
                        v148 = v144;
                      ++v145;
                      ++v147;
                      ++v146;
                      v144 = v148;
                    }
                    while ( v145 < v143 );
                  }
                  if ( !v144 )
                    goto LABEL_337;
                  v149 = (float *)((char *)this + 153044);
                  v150 = 0;
                  v151 = *((_DWORD *)this + 135);
                  v152 = *((float *)this + 38261);
                  if ( v143 > 0 )
                  {
                    v153 = 0;
                    do
                    {
                      v151 = *((_DWORD *)this + 135);
                      if ( v153 >= 4 )
                        break;
                      ++v150;
                      v154 = *v149;
                      ++v153;
                      ++v149;
                      v152 = fmin(v152, v154);
                    }
                    while ( v150 < v143 );
                  }
                  v155 = 0;
                  if ( v151 > 0 )
                  {
                    v156 = 0;
                    v157 = (float *)((char *)this + 153044);
                    do
                    {
                      v151 = v143;
                      if ( v156 >= 4 )
                        break;
                      ++v155;
                      v158 = *v157++;
                      v222[v156++] = v158 / v152;
                    }
                    while ( v155 < v143 );
                  }
                  v159 = v222[0];
                  v160 = 0;
                  v161 = v222[0];
                  if ( v151 > 0 )
                  {
                    v162 = v222;
                    do
                    {
                      if ( v160 >= 4 )
                        break;
                      v163 = *v162;
                      ++v160;
                      ++v162;
                      v159 = fmin(v159, v163);
                      v161 = fmin(v161, v163);
                    }
                    while ( (int)v160 < v151 );
                  }
                  if ( v159 <= 0.009999999776482582 || v161 > 100.0 )
                  {
LABEL_337:
                    if ( *((float *)this + 38261) > 0.0 )
                      *((_DWORD *)this + 38261) = 0;
                    *((_DWORD *)this + 38264) = 0;
                  }
                  if ( *((_DWORD *)this + 1296) || (v164 = 2, *((_DWORD *)this + 133)) )
                    v164 = 3;
                  if ( (v164 & *((_DWORD *)this + 1297)) != 0 && *((float *)this + 38269) > 0.125 )
                  {
                    *(_OWORD *)((char *)this + 153172) = *(_OWORD *)((char *)this + 153076);
                    *(_OWORD *)((char *)this + 153188) = *(_OWORD *)((char *)this + 153092);
                    *(_OWORD *)((char *)this + 153204) = *(_OWORD *)((char *)this + 153108);
                    *((_DWORD *)this + 95335) = 0;
                  }
                  if ( !*((_DWORD *)this + 95335) || *((_DWORD *)this + 95915) )
                  {
                    if ( *((float *)this + 38305) >= 0.01 || *((_DWORD *)this + 95915) )
                    {
LABEL_413:
                      if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::kodak_radc_load_raw
                        && *((_DWORD *)this + 95335)
                        && !*((_DWORD *)this + 95915) )
                      {
                        *((_DWORD *)this + 95915) = (*(__int64 (__fastcall **)(LibRaw *, __int64, const char *, _QWORD))(*(_QWORD *)this + 64LL))(
                                                      this,
                                                      3,
                                                      "Quicktake",
                                                      0);
                      }
                      v183 = *((_DWORD *)this + 131);
                      if ( v183 && *((_BYTE *)this + 460) )
                        LibRaw::SetStandardIlluminants(this, v183, (const char *)this + 460);
                      if ( *((_WORD *)this + 190675) )
                      {
                        if ( *((_DWORD *)this + 133) || (*((_DWORD *)this + 1347) & 0x10000) != 0 )
                        {
                          v200 = 1229539657;
                          v201 = *((_WORD *)this + 11) >> (*((_DWORD *)this + 95376) == 0);
                          v202 = *((_DWORD *)this + 95376);
                          *((_WORD *)this + 190675) = v201;
                          if ( (v201 & 1) != 0 )
                            v200 = -1802201964;
                          *((_DWORD *)this + 136) = v200;
                          v203 = v201 + (*((_WORD *)this + 10) >> v202);
                          v189 = *((unsigned __int16 *)this + 8);
                          v188 = v203;
                          v204 = v189 * *((unsigned __int16 *)this + 9);
                          *((_WORD *)this + 11) = v203;
                          v187 = (unsigned __int16)(v203 - 1);
                          *((_QWORD *)this + 5) = 0x3FF0000000000000LL;
                          *((_WORD *)this + 10) = v187;
                          if ( v187 * (unsigned __int64)v203 > 8 * v204 )
                          {
                            LOWORD(v189) = *((_WORD *)this + 8);
                            *((_DWORD *)this + 132) = 0;
                          }
                          goto LABEL_428;
                        }
                        *((_WORD *)this + 190675) = 0;
                      }
                      v184 = *((_WORD *)this + 10);
                      v185 = *((_WORD *)this + 8);
                      if ( v185 < v184 )
                      {
                        *((_WORD *)this + 8) = v184;
                        v185 = v184;
                      }
                      v186 = *((_WORD *)this + 11);
                      LOWORD(v187) = v184;
                      v188 = v186;
                      LOWORD(v189) = v185;
                      if ( *((_WORD *)this + 9) < v186 )
                        *((_WORD *)this + 9) = v186;
LABEL_428:
                      v190 = *((_DWORD *)this + 95378);
                      if ( !v190 )
                      {
                        *((_DWORD *)this + 95378) = 12;
                        v190 = 12;
                      }
                      v191 = *((_DWORD *)this + 38222);
                      if ( !v191 )
                      {
                        v191 = (1 << v190) - 1;
                        *((_DWORD *)this + 38222) = v191;
                        if ( v191 < 0x10000 )
                        {
                          v192 = *((unsigned __int16 *)this + v191 + 2696);
                          if ( (_WORD)v192 )
                          {
                            if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::sony_arw2_load_raw )
                            {
                              v191 = *((unsigned __int16 *)this + v191 + 2696);
                              *((_DWORD *)this + 38222) = v192;
                            }
                          }
                        }
                      }
                      if ( v191 > 0xFFFF )
                        *((_DWORD *)this + 38222) = 0xFFFF;
                      v193 = (void (__fastcall __noreturn *)(LibRaw *__hidden))*((_QWORD *)this + 95898);
                      if ( !v193
                        || (unsigned __int16)v187 < 0x16u
                        || v188 < 0x16u
                        || v190 > 0x10
                        && v193 != LibRaw::vc5_dng_load_raw_placeholder
                        && (char *)v193 != (char *)LibRaw::uncompressed_fp_dng_load_raw
                        || *((_DWORD *)this + 95377) > 6u
                        || *((int *)this + 135) > 4 )
                      {
                        *((_DWORD *)this + 132) = 0;
                      }
                      v194 = *((_WORD *)this + 9);
                      if ( (unsigned __int16)(v194 - 22) > 0xF9EAu
                        || (v195 = *((_WORD *)this + 8), LOWORD(v189) = v195, v195 < 0x16u)
                        || (v196 = *((double *)this + 5), v196 < 0.1)
                        || v196 > 10.0
                        || v195 > 0xFA00u )
                      {
                        *((_DWORD *)this + 132) = 0;
                        v195 = v189;
                      }
                      if ( v194 <= *((_WORD *)this + 13) || v195 <= *((_WORD *)this + 12) )
                        *((_DWORD *)this + 132) = 0;
                      if ( *((_DWORD *)this + 133) )
                      {
                        v197 = *((_DWORD *)this + 95377);
                        if ( !v197 || v197 > 4 )
                          *((_DWORD *)this + 132) = 0;
                      }
                      if ( *((__int64 (__fastcall **)())this + 95898) == guard_check_icall_nop )
                      {
                        *((_DWORD *)this + 132) = 0;
                        *((_DWORD *)this + 1347) |= 0x10u;
                      }
                      if ( !*((_BYTE *)this + 620) )
                      {
                        v198 = "GMCY";
                        if ( *((_DWORD *)this + 135) == 3 )
                          v198 = "RGBG";
                        strcpy_0((char *)this + 620, v198);
                      }
                      if ( !*((_WORD *)this + 8) )
                        *((_WORD *)this + 8) = *((_WORD *)this + 10);
                      if ( !*((_WORD *)this + 9) )
                        *((_WORD *)this + 9) = *((_WORD *)this + 11);
                      v199 = *((_DWORD *)this + 136);
                      if ( v199 > 0x3E7 && *((_DWORD *)this + 135) == 3 )
                        *((_DWORD *)this + 136) = v199
                                                | (2 * v199) & ((4 * (v199 & 0xE2222222)) | (v199 >> 2) & 0x22222222);
                      goto LABEL_482;
                    }
                    v165 = 1;
                  }
                  else
                  {
                    v165 = 0;
                  }
                  *((_DWORD *)this + 95915) = (*(__int64 (__fastcall **)(LibRaw *, _QWORD, char *, __int64))(*(_QWORD *)this + 64LL))(
                                                this,
                                                *((unsigned int *)this + 131),
                                                (char *)this + 460,
                                                v165);
                  goto LABEL_413;
                }
              }
              goto LABEL_476;
            }
            goto LABEL_312;
          }
          *((_DWORD *)this + 136) = -1802201964;
          goto LABEL_401;
        }
      }
    }
  }
  *((_DWORD *)this + 132) = 0;
  v206 = (unsigned int (__fastcall *)(_QWORD, __int64, __int64, __int64))*((_QWORD *)this + 95882);
  if ( v206 && v206(*((_QWORD *)this + 95883), 2, 1, 2) )
  {
    pExceptionObject = 6;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800546b0  mov     [rsp-8+arg_8], rbx
0x1800546b5  mov     [rsp-8+arg_10], rsi
0x1800546ba  mov     [rsp-8+arg_18], rdi
0x1800546bf  push    rbp
0x1800546c0  push    r12
0x1800546c2  push    r13
0x1800546c4  push    r14
0x1800546c6  push    r15
0x1800546c8  lea     rbp, [rsp-2DD0h]
0x1800546d0  mov     eax, 2ED0h
0x1800546d5  call    _alloca_probe
0x1800546da  sub     rsp, rax
0x1800546dd  mov     rax, cs:__security_cookie
0x1800546e4  xor     rax, rsp
0x1800546e7  mov     [rbp+2DF0h+var_30], rax
0x1800546ee  mov     r9, [rcx+1500h]; char **
0x1800546f5  lea     r8, [rbp+2DF0h+var_2BE0]; struct libraw_custom_camera_t *
0x1800546fc  xorps   xmm0, xmm0
0x1800546ff  mov     edi, 40h ; '@'
0x180054704  mov     edx, edi; unsigned int
0x180054706  mov     rbx, rcx
0x180054709  movups  xmmword ptr [rbp+2DF0h+Str1], xmm0
0x180054710  movups  [rbp+2DF0h+Buf1], xmm0
0x180054717  movups  [rbp+2DF0h+var_E0], xmm0
0x18005471e  movups  [rbp+2DF0h+var_D0], xmm0
0x180054725  call    ?parse_custom_cameras@LibRaw@@IEAAIIQEAUlibraw_custom_camera_t@@PEAPEAD@Z; LibRaw::parse_custom_cameras(uint,libraw_custom_camera_t * const,char * *)
0x18005472a  mov     r12d, eax
0x18005472d  lea     r8, qword_1800CABD0
0x180054734  mov     r9d, eax
0x180054737  lea     r10, aMmmm; "MMMM"
0x18005473e  xchg    ax, ax
0x180054740  movups  xmm0, xmmword ptr [r8]
0x180054744  mov     eax, [r8+30h]
0x180054748  movups  xmm1, xmmword ptr [r8+10h]
0x18005474d  mov     ecx, r9d
0x180054750  inc     r9d
0x180054753  imul    rdx, rcx, 34h ; '4'
0x180054757  movups  [rbp+rdx+2DF0h+var_2BE0], xmm0
0x18005475f  movups  xmm0, xmmword ptr [r8+20h]
0x180054764  add     r8, 34h ; '4'
0x180054768  movups  xmmword ptr [rbp+rdx+2DF0h+Source], xmm1
0x180054770  movups  [rbp+rdx+2DF0h+var_2BC0], xmm0
0x180054778  mov     [rbp+rdx+2DF0h+var_2BB0], eax
0x18005477f  cmp     r8, r10
0x180054782  jl      short loc_180054740
0x180054784  xor     esi, esi
0x180054786  mov     dword ptr [rbx+220h], 0FFFFFFFFh
0x180054790  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180054797  lea     r14, [rbx+10Ch]
0x18005479e  mov     [rbx+30h], eax
0x1800547a1  lea     r13, [rbx+0CCh]
0x1800547a8  mov     [rbx+5D1D4h], eax
0x1800547ae  lea     rcx, [rbx+69B30h]; void *
0x1800547b5  mov     [rbx+5D1EAh], si
0x1800547bc  xor     edx, edx; Val
0x1800547be  mov     [rbx+5D240h], esi
0x1800547c4  mov     r8d, 8254h; Size
0x1800547ca  mov     [rbx+5D1A6h], si
0x1800547d1  add     r12d, 93h
0x1800547d8  mov     [rbx+10h], rsi
0x1800547dc  mov     [rbx+18h], esi
0x1800547df  mov     [rbx+25538h], esi
0x1800547e5  mov     [r14], sil
0x1800547e8  mov     [r13+0], sil
0x1800547ec  mov     [rbx+26Ch], sil
0x1800547f3  mov     [rbx+256E0h], sil
0x1800547fa  mov     [rbx+2F274h], sil
0x180054801  mov     [rbx+2F074h], sil
0x180054808  mov     [rbx+5D1C0h], rsi
0x18005480f  mov     [rbx+5D1D0h], esi
0x180054815  mov     [rbx+20Ch], esi
0x18005481b  mov     [rbx+2EFB0h], rsi
0x180054822  mov     [rbx+2EFA8h], rsi
0x180054829  mov     [rbx+5DAB0h], rsi
0x180054830  mov     [rbx+5DAB8h], rsi
0x180054837  mov     [rbx+5DAC0h], rsi
0x18005483e  mov     [rbx+0ADCh], si
0x180054845  mov     [rbx+1CCh], sil
0x18005484c  mov     [rbx+18Ch], sil
0x180054853  mov     [rbx+5DAACh], esi
0x180054859  call    memset
0x18005485e  lea     rcx, [rbx+71D88h]; void *
0x180054865  xor     edx, edx; Val
0x180054867  mov     r8d, 496A8h; Size
0x18005486d  call    memset
0x180054872  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180054879  mov     [rbx+5DAA8h], si
0x180054880  mov     [rbx+5DAA0h], rax
0x180054887  mov     ecx, 0Ah
0x18005488c  mov     [rbx+0A24h], rax
0x180054893  mov     rdx, rbx
0x180054896  mov     [rbx+5D220h], rax
0x18005489d  mov     r8d, 0FFFFh
0x1800548a3  mov     eax, esi
0x1800548a5  mov     dword ptr [rbx+0EE8h], 3F800000h
0x1800548af  mov     dword ptr [rbx+1208h], 0C47A0000h
0x1800548b9  mov     dword ptr [rbx+1204h], 0C47A0000h
0x1800548c3  mov     dword ptr [rbx+1200h], 0C47A0000h
0x1800548cd  mov     dword ptr [rbx+11FCh], 0C47A0000h
0x1800548d7  mov     dword ptr [rbx+11F8h], 0C47A0000h
0x1800548e1  mov     dword ptr [rbx+11F4h], 0C47A0000h
0x1800548eb  mov     dword ptr [rbx+11F0h], 0C47A0000h
0x1800548f5  mov     dword ptr [rbx+2EFA4h], 0FFh
0x1800548ff  nop
0x180054900  mov     [rbx+rax+69C68h], r8w
0x180054909  lea     rdx, [rdx+8280h]
0x180054910  mov     [rbx+rax+69BC0h], r8w
0x180054919  lea     rax, [rax+8280h]
0x180054920  mov     dword ptr [rdx+69B04h], 3F800000h
0x18005492a  mov     dword ptr [rbx+rax+69B08h], 3F800000h
0x180054935  mov     dword ptr [rbx+rax+69B0Ch], 3F800000h
0x180054940  mov     dword ptr [rbx+rax+69B10h], 3F800000h
0x18005494b  sub     rcx, 1
0x18005494f  jnz     short loc_180054900
0x180054951  xorps   xmm0, xmm0
0x180054954  lea     rcx, [rbx+21510h]; void *
0x18005495b  movups  xmmword ptr [rbx+2EFC4h], xmm0
0x180054962  xor     edx, edx; Val
0x180054964  mov     r8d, 4020h; Size
0x18005496a  movups  xmmword ptr [rbx+2EFD4h], xmm0
0x180054971  movups  xmmword ptr [rbx+2EFE4h], xmm0
0x180054978  movups  xmmword ptr [rbx+2EFF4h], xmm0
0x18005497f  movups  xmmword ptr [rbx+2F004h], xmm0
0x180054986  movups  xmmword ptr [rbx+2F014h], xmm0
0x18005498d  movups  xmmword ptr [rbx+2F024h], xmm0
0x180054994  movups  xmmword ptr [rbx+2F034h], xmm0
0x18005499b  call    memset
0x1800549a0  xorps   xmm0, xmm0
0x1800549a3  lea     rcx, [rbx+255E4h]
0x1800549aa  movups  xmmword ptr [rbx+25554h], xmm0
0x1800549b1  mov     rax, 3FF0000000000000h
0x1800549bb  mov     edx, esi
0x1800549bd  movups  xmmword ptr [rbx+25564h], xmm0
0x1800549c4  movups  xmmword ptr [rbx+25574h], xmm0
0x1800549cb  movups  xmmword ptr [rbx+25584h], xmm0
0x1800549d2  movups  xmmword ptr [rbx+25594h], xmm0
0x1800549d9  movups  xmmword ptr [rbx+255A4h], xmm0
0x1800549e0  movups  xmmword ptr [rbx+255B4h], xmm0
0x1800549e7  movups  xmmword ptr [rbx+255C4h], xmm0
0x1800549ee  xorps   xmm1, xmm1
0x1800549f1  movups  xmmword ptr [rbx+34h], xmm1
0x1800549f5  movups  xmmword ptr [rbx+44h], xmm1
0x1800549f9  movups  xmmword ptr [rbx+54h], xmm1
0x1800549fd  movups  xmmword ptr [rbx+64h], xmm1
0x180054a01  movups  xmmword ptr [rbx+74h], xmm1
0x180054a05  movups  xmmword ptr [rbx+84h], xmm1
0x180054a0c  movups  xmmword ptr [rbx+94h], xmm1
0x180054a13  movups  xmmword ptr [rbx+0A4h], xmm1
0x180054a1a  mov     [rbx+2F2CCh], rsi
0x180054a21  mov     [rbx+5D180h], rsi
0x180054a28  mov     [rbx+0BB4D0h], rsi
0x180054a2f  mov     dword ptr [rbx+5D23Ch], 4
0x180054a39  mov     [rbx+5D248h], rsi
0x180054a40  mov     [rbx+5D22Ch], esi
0x180054a46  mov     [rbx+5D208h], rsi
0x180054a4d  mov     [rbx+5D200h], rsi
0x180054a54  mov     [rbx+5D260h], rsi
0x180054a5b  mov     [rbx+214h], rsi
0x180054a62  mov     [rbx+5D254h], rsi
0x180054a69  mov     [rbx+5D1F0h], esi
0x180054a6f  mov     [rbx+25530h], esi
0x180054a75  mov     [rbx+5D244h], esi
0x180054a7b  mov     [rbx+2EFC0h], esi
0x180054a81  mov     [rbx+2EFB8h], rsi
0x180054a88  mov     qword ptr [rbx+5D19Ch], 1
0x180054a93  mov     [rbx+25840h], esi
0x180054a99  mov     [rbx+5D198h], esi
0x180054a9f  mov     dword ptr [rbx+210h], 1
0x180054aa9  mov     [rbx+28h], rax
0x180054aad  mov     [rbx+5D25Ch], esi
0x180054ab3  mov     [rbx+5D1D8h], esi
0x180054ab9  nop     dword ptr [rax+00000000h]
0x180054ac0  cmp     edx, 1
0x180054ac3  lea     rcx, [rcx+4]
0x180054ac7  mov     eax, esi
0x180054ac9  setz    al
0x180054acc  cmp     edx, 3
0x180054acf  movd    xmm0, eax
0x180054ad3  mov     eax, esi
0x180054ad5  cvtdq2ps xmm0, xmm0
0x180054ad8  setb    al
0x180054adb  test    edx, edx
0x180054add  movss   dword ptr [rcx-14h], xmm0
0x180054ae2  movd    xmm0, eax
0x180054ae6  mov     eax, esi
0x180054ae8  cvtdq2ps xmm0, xmm0
0x180054aeb  setz    al
0x180054aee  cmp     edx, 1
0x180054af1  movss   dword ptr [rcx-4], xmm0
0x180054af6  mov     [rcx+0Ch], esi
0x180054af9  movd    xmm0, eax
0x180054afd  mov     eax, esi
0x180054aff  cvtdq2ps xmm0, xmm0
0x180054b02  setz    al
0x180054b05  mov     [rcx+1Ch], esi
0x180054b08  mov     [rcx+2Ch], esi
0x180054b0b  cmp     edx, 2
0x180054b0e  movss   dword ptr [rcx+6Ch], xmm0
0x180054b13  movd    xmm0, eax
0x180054b17  mov     eax, esi
0x180054b19  cvtdq2ps xmm0, xmm0
0x180054b1c  setz    al
0x180054b1f  inc     edx
0x180054b21  movss   dword ptr [rcx+7Ch], xmm0
0x180054b26  movd    xmm0, eax
0x180054b2a  cvtdq2ps xmm0, xmm0
0x180054b2d  movss   dword ptr [rcx+8Ch], xmm0
0x180054b35  cmp     edx, 4
0x180054b38  jl      short loc_180054AC0
0x180054b3a  mov     dword ptr [rbx+21Ch], 3
0x180054b44  lea     rcx, [rbx+1510h]
0x180054b4b  mov     eax, esi
0x180054b4d  nop     dword ptr [rax]
0x180054b50  mov     [rcx], ax
0x180054b53  lea     rcx, [rcx+2]
0x180054b57  inc     eax
0x180054b59  cmp     eax, 10000h
0x180054b5e  jl      short loc_180054B50
0x180054b60  mov     rcx, rbx; this
0x180054b63  call    ?get2@LibRaw@@IEAAGXZ; LibRaw::get2(void)
0x180054b68  mov     rcx, rbx; this
0x180054b6b  mov     [rbx+5D1E0h], ax
0x180054b72  call    ?get4@LibRaw@@IEAAIXZ; LibRaw::get4(void)
0x180054b77  mov     rcx, [rbx+5D158h]
0x180054b7e  xor     r8d, r8d
0x180054b81  movsxd  rsi, eax
0x180054b84  mov     rdx, [rcx]
0x180054b87  mov     rax, [rdx+18h]
0x180054b8b  xor     edx, edx
0x180054b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b92  mov     rcx, [rbx+5D158h]
0x180054b99  mov     r9, rdi
0x180054b9c  mov     r8d, 1
0x180054ba2  mov     rdx, [rcx]
0x180054ba5  mov     rax, [rdx+10h]
0x180054ba9  lea     rdx, [rbp+2DF0h+Str1]
0x180054bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bb5  cmp     eax, edi
0x180054bb7  jl      loc_180057019
0x180054bbd  mov     rcx, [rbx+5D158h]
0x180054bc4  xor     eax, eax
0x180054bc6  mov     [rbx+5D270h], rax
0x180054bcd  xor     edx, edx
0x180054bcf  mov     [rbx+5D278h], eax
0x180054bd5  mov     r8d, 2
0x180054bdb  mov     rax, [rcx]
0x180054bde  mov     rax, [rax+18h]
0x180054be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054be7  mov     rcx, [rbx+5D158h]
0x180054bee  mov     rax, [rcx]
0x180054bf1  mov     rax, [rax+20h]
0x180054bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bfa  mov     [rsp+2EF0h+var_2E90], rax
0x180054bff  cmp     rax, 7FFFFFFFh
0x180054c05  ja      loc_180057033
0x180054c0b  mov     rcx, [rbx+5D158h]
0x180054c12  mov     rax, [rcx]
0x180054c15  mov     rax, [rax+20h]
0x180054c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c1e  mov     r9d, 4; unsigned __int64
0x180054c24  mov     qword ptr [rsp+2EF0h+var_2EA8], rax
0x180054c29  lea     r8, aMmmm; "MMMM"
0x180054c30  mov     [rsp+2EF0h+pExceptionObject], eax
0x180054c34  mov     edx, 20h ; ' '; unsigned __int64
0x180054c39  lea     rcx, [rbp+2DF0h+Str1]; Buf1
0x180054c40  call    ?memmem@LibRaw@@KAPEAXPEAD_K01@Z; LibRaw::memmem(char *,unsigned __int64,char *,unsigned __int64)
0x180054c45  mov     rdi, rax
0x180054c48  test    rax, rax
0x180054c4b  jnz     loc_18005562E
0x180054c51  mov     r9d, 4; unsigned __int64
0x180054c57  lea     r8, aIiii; "IIII"
0x180054c5e  mov     edx, 20h ; ' '; unsigned __int64
0x180054c63  lea     rcx, [rbp+2DF0h+Str1]; Buf1
0x180054c6a  call    ?memmem@LibRaw@@KAPEAXPEAD_K01@Z; LibRaw::memmem(char *,unsigned __int64,char *,unsigned __int64)
0x180054c6f  mov     rdi, rax
0x180054c72  test    rax, rax
0x180054c75  jnz     loc_18005562E
0x180054c7b  movzx   eax, word ptr [rbx+5D1E0h]
0x180054c82  mov     ecx, 4949h
0x180054c87  cmp     ax, cx
0x180054c8a  jz      loc_1800555E5
0x180054c90  mov     ecx, 4D4Dh
0x180054c95  cmp     ax, cx
0x180054c98  jz      loc_1800555E5
0x180054c9e  xor     ecx, ecx
0x180054ca0  lea     rdx, [rbp+2DF0h+Str1]
0x180054ca7  lea     r8, dword_1800CC9CC
0x180054cae  mov     edi, 4
0x180054cb3  nop     dword ptr [rax+00h]
0x180054cb7  nop     word ptr [rax+rax+00000000h]
0x180054cc0  movzx   eax, byte ptr [rdx+rcx]
0x180054cc4  inc     rcx
0x180054cc7  cmp     al, [r8+rcx-1]
0x180054ccc  jnz     short loc_180054CD7
0x180054cce  cmp     rcx, rdi
0x180054cd1  jnz     short loc_180054CC0
0x180054cd3  xor     eax, eax
0x180054cd5  jmp     short loc_180054CDC
0x180054cd7  sbb     eax, eax
0x180054cd9  or      eax, 1
  ... truncated ...
```
