# sub_1807AFCA4

- ea: `0x1807afca4`
- end: `0x1807b04fb`
- name: `sub_1807AFCA4`
- size: `2135`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0x1807b27f0`

## callees

- `0x1800360b0`
- `0x180083ff0`
- `0x1800b8ed2`
- `0x1800b8ed8`
- `0x180107a90`
- `0x18010ccd0`
- `0x18010cff0`
- `0x18014fd70`
- `0x18015332c`
- `0x1801b40a0`
- `0x1801b4170`
- `0x1801b8328`
- `0x1801b83b4`
- `0x1801b87e0`
- `0x1801b8810`
- `0x180275d90`
- `0x180278e50`
- `0x180278e70`
- `0x180279050`
- `0x18027da6c`
- `0x18061d834`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`
- `0x1807afca4`

## import_xrefs

- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1807b0160`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1807b0160`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1807b03cb`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1807b03cb`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1807b01aa`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1807b01aa`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1807b00e9`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1807b00e9`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1807afe93`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1807afe93`
- `mso40uiWin32Client!mso40uiWin32Client_15794` at `0x1807b0082`
- `mso40uiWin32Client!mso40uiWin32Client_15794` at `0x1807b0102`
- `mso40uiWin32Client!mso40uiWin32Client_15794` at `0x1807b0082`
- `mso40uiWin32Client!mso40uiWin32Client_15794` at `0x1807b0102`

## pseudocode

```c
_QWORD *__fastcall sub_1807AFCA4(_QWORD *a1, _QWORD *a2, int a3, int a4, char a5, _DWORD *a6)
{
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rax
  double v18; // xmm8_8
  double v19; // xmm7_8
  double v20; // xmm9_8
  double v21; // xmm11_8
  __int64 v22; // rbx
  void (__fastcall *v23)(__int64, _QWORD); // rsi
  char v24; // di
  int v25; // eax
  int v26; // r9d
  int v27; // r8d
  _QWORD *v28; // rax
  __int64 v29; // r8
  __int64 *v30; // rax
  __int64 v31; // rsi
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rbx
  void (__fastcall *v35)(__int64, _QWORD); // rdi
  __int64 v36; // rax
  _QWORD *v37; // rax
  __int64 v38; // rbx
  void (__fastcall *v39)(__int64, _QWORD); // rdi
  _QWORD *v40; // rax
  int v41; // r15d
  int v42; // r15d
  int v43; // r15d
  int v44; // r15d
  double v45; // xmm9_8
  double v46; // xmm7_8
  double v47; // xmm8_8
  double v48; // xmm7_8
  double v49; // xmm0_8
  double v50; // xmm2_8
  unsigned int v51; // eax
  _QWORD *v52; // rbx
  void (__fastcall *v53)(_QWORD *, __int64, _OWORD *); // rdi
  __int64 v54; // rax
  __int64 v55; // rax
  unsigned int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // rcx
  unsigned int v59; // eax
  __int64 v60; // rcx
  __int64 v61; // r8
  unsigned int v62; // eax
  __int64 v63; // rdx
  __int64 v64; // r8
  int v65; // ecx
  int v66; // edx
  int v67; // r8d
  __int64 v69; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v70; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v71; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v72; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v73; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v74; // [rsp+78h] [rbp-90h]
  __m128i si128; // [rsp+88h] [rbp-80h] BYREF
  __m256i v76; // [rsp+98h] [rbp-70h] BYREF
  double v77; // [rsp+B8h] [rbp-50h]
  double v78; // [rsp+C0h] [rbp-48h]
  _QWORD *v79; // [rsp+C8h] [rbp-40h] BYREF
  double v80; // [rsp+D0h] [rbp-38h] BYREF
  float v81; // [rsp+D8h] [rbp-30h]
  int v82; // [rsp+DCh] [rbp-2Ch]
  __int64 v83; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v84; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v85; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v86; // [rsp+100h] [rbp-8h] BYREF
  int v87; // [rsp+110h] [rbp+8h]
  __int16 v88; // [rsp+114h] [rbp+Ch]
  __int64 v89; // [rsp+118h] [rbp+10h]
  __int64 v90; // [rsp+120h] [rbp+18h]
  _OWORD v91[2]; // [rsp+128h] [rbp+20h] BYREF
  _QWORD *v92; // [rsp+148h] [rbp+40h]
  __int64 v93; // [rsp+150h] [rbp+48h]
  _QWORD v94[22]; // [rsp+158h] [rbp+50h] BYREF
  __int64 v95; // [rsp+208h] [rbp+100h] BYREF

  v92 = a1;
  oart_22204((_DWORD)a1, (_DWORD)a2, 5, a3, a4, a5, 0);
  *a1 = off_180B94D98;
  v69 = sub_1806D19BC(*a2);
  v9 = sub_1806BC4F0(v69);
  v10 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v84 = sub_180278E50(*v10, v11, v12, v13);
  oart_27489_0(&v69);
  v69 = sub_1806D19BC(v84);
  v14 = sub_1806BC4F0(v69);
  v15 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 64LL))(v14);
  v83 = sub_1806D19BC(*v15);
  oart_27489_0(&v69);
  v73 = 0;
  v74 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v16 = (_QWORD *)oart_26408(a1);
  v71 = sub_1806D19BC(*v16);
  v17 = sub_1806BC4F0(v83);
  (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v17 + 8LL))(v17, &v71, &v73);
  sub_18015332C(&v73, &v85, &v86);
  v69 = oart_62603(0);
  v70 = v69;
  oart_32575(&v85, &v70, &v69);
  sub_1806BC4F0(v71);
  v69 = sub_1806D19BC(*a2);
  oart_51835(&v69, &v85);
  oart_27489_0(&v69);
  sub_180107A90(&v85, &v86, &v73);
  GEL::IEffectContainer::Create(&v72);
  si128 = _mm_load_si128((const __m128i *)&xmmword_180AC0110);
  oart_27023(&v80, &si128, &v71);
  v18 = v80;
  v19 = v18 + v18;
  v20 = v80 * 4.0;
  v21 = v80 * 5.0;
  v22 = v72;
  v23 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v72 + 144LL);
  v24 = sub_1801B87E0();
  sub_1801B8328(&v71);
  v25 = sub_1806BC4F0(v71);
  LOBYTE(v26) = a5;
  v28 = (_QWORD *)sub_1801B83B4((unsigned int)&v70, v25 + 160, v27, v26, v24, 2);
  v23(v22, *v28);
  if ( v70 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 8LL))(v70);
  v94[0] = 0x8000000000000000uLL;
  *(double *)&v94[1] = -v21;
  *(double *)&v94[2] = -v20;
  *(double *)&v94[3] = -v19;
  *(double *)&v94[4] = -v18;
  *(double *)&v94[5] = -v19;
  *(double *)&v94[6] = -v18;
  *(double *)&v94[7] = v18 + v18;
  *(double *)&v94[8] = -v20;
  *(double *)&v94[9] = v18 + v18;
  *(double *)&v94[10] = -v18;
  *(double *)&v94[11] = v21;
  *(double *)&v94[12] = v18;
  *(double *)&v94[13] = v21;
  *(double *)&v94[14] = v20;
  *(double *)&v94[15] = v18 + v18;
  *(double *)&v94[16] = v18;
  *(double *)&v94[17] = v18 + v18;
  *(double *)&v94[18] = v18;
  *(double *)&v94[19] = -v19;
  *(double *)&v94[20] = v20;
  *(double *)&v94[21] = -v19;
  si128.m128i_i64[0] = (__int64)v94;
  si128.m128i_i64[1] = (__int64)&v95;
  LOBYTE(v29) = 1;
  v30 = (__int64 *)sub_18061D834(&v70, &si128, v29);
  v31 = *v30;
  *v30 = 0;
  v93 = v31;
  if ( v70 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 8LL))(v70);
  v32 = mso40uiWin32Client_15794(1312);
  *(float *)&v80 = (float)(unsigned __int8)v32 / 255.0;
  *((float *)&v80 + 1) = (float)BYTE1(v32) / 255.0;
  v81 = (float)BYTE2(v32) / 255.0;
  v82 = 1065353216;
  GEL::IPen::Create(&v69, v33, &v80);
  v34 = v72;
  v35 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v72 + 144LL);
  v36 = mso40uiWin32Client_15794(1312);
  *(float *)si128.m128i_i32 = (float)(unsigned __int8)v36 / 255.0;
  *(float *)&si128.m128i_i32[1] = (float)BYTE1(v36) / 255.0;
  *(float *)&si128.m128i_i32[2] = (float)BYTE2(v36) / 255.0;
  si128.m128i_i32[3] = 1065353216;
  v37 = (_QWORD *)GEL::IEffectFilledPath::Create(&v70, v31, &si128);
  v35(v34, *v37);
  if ( v70 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 8LL))(v70);
  v38 = v72;
  v39 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v72 + 144LL);
  v40 = (_QWORD *)GEL::IEffectPennedPath::Create(&v70, v31, v69);
  v39(v38, *v40);
  if ( v70 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 8LL))(v70);
  if ( v69 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 8LL))(v69);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
  v41 = a3 - 5;
  if ( !v41 )
    goto LABEL_23;
  v42 = v41 - 1;
  if ( !v42 )
  {
    v47 = (double)(DWORD2(v74) + DWORD2(v73)) * 0.5;
    v48 = sin(-1.570796326794897);
    v76.m256i_i64[0] = cos(-1.570796326794897);
    v76.m256i_i64[3] = v76.m256i_i64[0];
    v49 = (double)(int)v74;
    goto LABEL_20;
  }
  v43 = v42 - 1;
  if ( !v43 )
  {
    v50 = (double)SDWORD2(v74);
    v76.m256i_i64[3] = 0x3FF0000000000000LL;
    v76.m256i_i64[0] = 0x3FF0000000000000LL;
    *(_OWORD *)&v76.m256i_u64[1] = 0;
LABEL_24:
    v78 = v50;
    goto LABEL_25;
  }
  v44 = v43 - 1;
  if ( !v44 )
  {
    v47 = (double)(DWORD2(v74) + DWORD2(v73)) * 0.5;
    v48 = sin(1.570796326794897);
    v76.m256i_i64[0] = cos(1.570796326794897);
    v76.m256i_i64[3] = v76.m256i_i64[0];
    v49 = (double)(int)v73;
LABEL_20:
    *(double *)&v76.m256i_i64[1] = v48;
    *(double *)&v76.m256i_i64[2] = -v48;
    v78 = v47;
    goto LABEL_26;
  }
  if ( v44 != 1 )
  {
LABEL_23:
    v50 = (double)SDWORD2(v73);
    *(__m128i *)v76.m256i_i8 = _mm_load_si128((const __m128i *)&xmmword_180B453E0);
    *(__m128i *)&v76.m256i_u64[2] = _mm_load_si128((const __m128i *)&xmmword_180C11F50);
    goto LABEL_24;
  }
  v45 = (double)(DWORD2(v74) + DWORD2(v73)) * 0.5;
  v46 = sin(1.570796326794897);
  v76.m256i_i64[0] = cos(1.570796326794897);
  *(double *)&v76.m256i_i64[1] = v46;
  *(double *)&v76.m256i_i64[2] = -v46;
  v76.m256i_i64[3] = v76.m256i_i64[0];
  v78 = v45;
LABEL_25:
  v49 = (double)((int)v74 + (int)v73) * 0.5;
LABEL_26:
  v77 = v49;
  v51 = oart_45867(a1);
  GEL::ITopLevelEffect::Create(&v79, v72, &v76, v51);
  memset(v91, 0, sizeof(v91));
  v52 = v79;
  v53 = *(void (__fastcall **)(_QWORD *, __int64, _OWORD *))(*v79 + 168LL);
  v54 = sub_1806BC4F0(v71);
  v55 = sub_18027DA6C(v54);
  v53(v52, v55, v91);
  v56 = ((__int64 (*)(void))sub_1800360B0)();
  v59 = sub_1800360B0(v58, v57, v56);
  v62 = sub_1800360B0(v60, v59, v61);
  *a6 = sub_1800360B0(v62, v63, v64);
  a6[1] = v65;
  a6[2] = v66;
  a6[3] = v67;
  oart_45877(a1, v79);
  if ( v79 )
    (*(void (__fastcall **)(_QWORD *))(v79[1] + 8LL))(v79 + 1);
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 8LL))(v72);
  oart_27489_0(&v71);
  oart_27489_0(&v83);
  sub_1806BC2A8(&v84);
  return a1;
}

```

## disassembly

```asm
0x1807afca4  mov     rax, rsp
0x1807afca7  mov     [rax+18h], rbx
0x1807afcab  push    rbp
0x1807afcac  push    rsi
0x1807afcad  push    rdi
0x1807afcae  push    r12
0x1807afcb0  push    r13
0x1807afcb2  push    r14
0x1807afcb4  push    r15
0x1807afcb6  lea     rbp, [rax-1A8h]
0x1807afcbd  sub     rsp, 270h
0x1807afcc4  movaps  xmmword ptr [rax-48h], xmm6
0x1807afcc8  movaps  xmmword ptr [rax-58h], xmm7
0x1807afccc  movaps  xmmword ptr [rax-68h], xmm8
0x1807afcd1  movaps  xmmword ptr [rax-78h], xmm9
0x1807afcd6  movaps  xmmword ptr [rax-88h], xmm10
0x1807afcde  movaps  xmmword ptr [rax-98h], xmm11
0x1807afce6  mov     rax, cs:__security_cookie
0x1807afced  xor     rax, rsp
0x1807afcf0  mov     [rbp+1A0h+var_A0], rax
0x1807afcf7  mov     r15d, r8d
0x1807afcfa  mov     rbx, rdx
0x1807afcfd  mov     r13, rcx
0x1807afd00  mov     [rbp+1A0h+var_160], rcx
0x1807afd04  mov     r14b, [rbp+1A0h+arg_20]
0x1807afd0b  mov     r12, [rbp+1A0h+arg_28]
0x1807afd12  xor     edi, edi
0x1807afd14  mov     [rsp+2A0h+var_270], dil
0x1807afd19  mov     [rsp+2A0h+var_278], r14b
0x1807afd1e  mov     [rsp+2A0h+var_280], r9d
0x1807afd23  mov     r9d, r8d
0x1807afd26  lea     r8d, [rdi+5]
0x1807afd2a  call    oart_22204
0x1807afd2f  lea     rax, off_180B94D98
0x1807afd36  mov     [r13+0], rax
0x1807afd3a  mov     rcx, [rbx]
0x1807afd3d  call    sub_1806D19BC
0x1807afd42  mov     [rsp+2A0h+var_260], rax
0x1807afd47  mov     rcx, rax
0x1807afd4a  call    sub_1806BC4F0
0x1807afd4f  mov     rcx, rax
0x1807afd52  mov     rax, [rax]
0x1807afd55  mov     rax, [rax+10h]
0x1807afd59  call    cs:__guard_dispatch_icall_fptr
0x1807afd5f  mov     rcx, [rax]
0x1807afd62  call    sub_180278E50
0x1807afd67  mov     [rbp+1A0h+var_1C0], rax
0x1807afd6b  lea     rcx, [rsp+2A0h+var_260]
0x1807afd70  call    oart_27489_0
0x1807afd75  mov     rcx, [rbp+1A0h+var_1C0]
0x1807afd79  call    sub_1806D19BC
0x1807afd7e  mov     [rsp+2A0h+var_260], rax
0x1807afd83  mov     rcx, rax
0x1807afd86  call    sub_1806BC4F0
0x1807afd8b  mov     rcx, rax
0x1807afd8e  mov     rax, [rax]
0x1807afd91  mov     rax, [rax+40h]
0x1807afd95  call    cs:__guard_dispatch_icall_fptr
0x1807afd9b  mov     rcx, [rax]
0x1807afd9e  call    sub_1806D19BC
0x1807afda3  mov     [rbp+1A0h+var_1C8], rax
0x1807afda7  lea     rcx, [rsp+2A0h+var_260]
0x1807afdac  call    oart_27489_0
0x1807afdb1  xorps   xmm0, xmm0
0x1807afdb4  movdqu  [rsp+2A0h+var_248+8], xmm0
0x1807afdba  xorps   xmm1, xmm1
0x1807afdbd  movdqu  [rsp+2A0h+var_238+8], xmm1
0x1807afdc3  movdqu  [rbp+1A0h+var_1B8], xmm0
0x1807afdc8  movdqu  [rbp+1A0h+var_1A8], xmm1
0x1807afdcd  mov     [rbp+1A0h+var_198], edi
0x1807afdd0  mov     [rbp+1A0h+var_194], di
0x1807afdd4  xor     eax, eax
0x1807afdd6  mov     [rbp+1A0h+var_190], rax
0x1807afdda  mov     [rbp+1A0h+var_188], rax
0x1807afdde  mov     rcx, r13
0x1807afde1  call    oart_26408
0x1807afde6  mov     rcx, [rax]
0x1807afde9  call    sub_1806D19BC
0x1807afdee  mov     [rsp+2A0h+var_250], rax
0x1807afdf3  mov     rcx, [rbp+1A0h+var_1C8]
0x1807afdf7  call    sub_1806BC4F0
0x1807afdfc  mov     rcx, rax
0x1807afdff  mov     rax, [rax]
0x1807afe02  lea     r8, [rsp+2A0h+var_248+8]
0x1807afe07  lea     rdx, [rsp+2A0h+var_250]
0x1807afe0c  mov     rax, [rax+8]
0x1807afe10  call    cs:__guard_dispatch_icall_fptr
0x1807afe16  lea     r8, [rbp+1A0h+var_1A8]
0x1807afe1a  lea     rdx, [rbp+1A0h+var_1B8]
0x1807afe1e  lea     rcx, [rsp+2A0h+var_248+8]
0x1807afe23  call    sub_18015332C
0x1807afe28  xor     ecx, ecx
0x1807afe2a  call    oart_62603
0x1807afe2f  mov     [rsp+2A0h+var_260], rax
0x1807afe34  mov     [rsp+2A0h+var_258], rax
0x1807afe39  lea     r8, [rsp+2A0h+var_260]
0x1807afe3e  lea     rdx, [rsp+2A0h+var_258]
0x1807afe43  lea     rcx, [rbp+1A0h+var_1B8]
0x1807afe47  call    oart_32575
0x1807afe4c  mov     rcx, [rsp+2A0h+var_250]
0x1807afe51  call    sub_1806BC4F0
0x1807afe56  mov     rcx, [rbx]
0x1807afe59  call    sub_1806D19BC
0x1807afe5e  mov     [rsp+2A0h+var_260], rax
0x1807afe63  lea     rdx, [rbp+1A0h+var_1B8]
0x1807afe67  lea     rcx, [rsp+2A0h+var_260]
0x1807afe6c  call    oart_51835
0x1807afe71  nop
0x1807afe72  lea     rcx, [rsp+2A0h+var_260]
0x1807afe77  call    oart_27489_0
0x1807afe7c  lea     r8, [rsp+2A0h+var_248+8]
0x1807afe81  lea     rdx, [rbp+1A0h+var_1A8]
0x1807afe85  lea     rcx, [rbp+1A0h+var_1B8]
0x1807afe89  call    sub_180107A90
0x1807afe8e  lea     rcx, [rsp+2A0h+var_248]
0x1807afe93  call    cs:?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1807afe99  nop
0x1807afe9a  movdqa  xmm0, cs:xmmword_180AC0110
0x1807afea2  movups  [rbp+1A0h+var_220], xmm0
0x1807afea6  lea     r8, [rsp+2A0h+var_250]
0x1807afeab  lea     rdx, [rbp+1A0h+var_220]
0x1807afeaf  lea     rcx, [rbp+1A0h+var_1D8]
0x1807afeb3  call    oart_27023
0x1807afeb8  movsd   xmm8, [rbp+1A0h+var_1D8]
0x1807afebe  movaps  xmm7, xmm8
0x1807afec2  addsd   xmm7, xmm8
0x1807afec7  movaps  xmm9, xmm8
0x1807afecb  mulsd   xmm9, cs:qword_180C14810
0x1807afed4  movaps  xmm11, xmm8
0x1807afed8  mulsd   xmm11, cs:qword_180C11F48
0x1807afee1  mov     rbx, qword ptr [rsp+2A0h+var_248]
0x1807afee6  mov     rax, [rbx]
0x1807afee9  mov     rsi, [rax+90h]
0x1807afef0  call    sub_1801B87E0
0x1807afef5  mov     dil, al
0x1807afef8  lea     rcx, [rsp+2A0h+var_250]
0x1807afefd  call    sub_1801B8328
0x1807aff02  movaps  xmm6, xmm0
0x1807aff05  mov     rcx, [rsp+2A0h+var_250]
0x1807aff0a  call    sub_1806BC4F0
0x1807aff0f  lea     rdx, [rax+0A0h]
0x1807aff16  mov     dword ptr [rsp+2A0h+var_278], 2
0x1807aff1e  mov     byte ptr [rsp+2A0h+var_280], dil
0x1807aff23  mov     r9b, r14b
0x1807aff26  movaps  xmm2, xmm6
0x1807aff29  lea     rcx, [rsp+2A0h+var_258]
0x1807aff2e  call    sub_1801B83B4
0x1807aff33  nop
0x1807aff34  mov     rdx, [rax]
0x1807aff37  mov     rcx, rbx
0x1807aff3a  mov     rax, rsi
0x1807aff3d  call    cs:__guard_dispatch_icall_fptr
0x1807aff43  nop
0x1807aff44  mov     rcx, [rsp+2A0h+var_258]
0x1807aff49  test    rcx, rcx
0x1807aff4c  jz      short loc_1807AFF5B
0x1807aff4e  mov     rax, [rcx]
0x1807aff51  mov     rax, [rax+8]
0x1807aff55  call    cs:__guard_dispatch_icall_fptr
0x1807aff5b  movsd   xmm0, cs:qword_180B4D270
0x1807aff63  movsd   [rbp+1A0h+var_150], xmm0
0x1807aff68  movaps  xmm1, xmm11
0x1807aff6c  movsd   xmm10, qword ptr cs:xmmword_180B46F10
0x1807aff75  xorps   xmm1, xmm10
0x1807aff79  movsd   [rbp+1A0h+var_148], xmm1
0x1807aff7e  movaps  xmm2, xmm9
0x1807aff82  xorps   xmm2, xmm10
0x1807aff86  movsd   [rbp+1A0h+var_140], xmm2
0x1807aff8b  movaps  xmm1, xmm7
0x1807aff8e  xorps   xmm1, xmm10
0x1807aff92  movsd   [rbp+1A0h+var_138], xmm1
0x1807aff97  movaps  xmm0, xmm8
0x1807aff9b  xorps   xmm0, xmm10
0x1807aff9f  movsd   [rbp+1A0h+var_130], xmm0
0x1807affa4  movsd   [rbp+1A0h+var_128], xmm1
0x1807affa9  movsd   [rbp+1A0h+var_120], xmm0
0x1807affb1  movsd   [rbp+1A0h+var_118], xmm7
0x1807affb9  movsd   [rbp+1A0h+var_110], xmm2
0x1807affc1  movsd   [rbp+1A0h+var_108], xmm7
0x1807affc9  movsd   [rbp+1A0h+var_100], xmm0
0x1807affd1  movsd   [rbp+1A0h+var_F8], xmm11
0x1807affda  movsd   [rbp+1A0h+var_F0], xmm8
0x1807affe3  movsd   [rbp+1A0h+var_E8], xmm11
0x1807affec  movsd   [rbp+1A0h+var_E0], xmm9
0x1807afff5  movsd   [rbp+1A0h+var_D8], xmm7
0x1807afffd  movsd   [rbp+1A0h+var_D0], xmm8
0x1807b0006  movsd   [rbp+1A0h+var_C8], xmm7
0x1807b000e  movsd   [rbp+1A0h+var_C0], xmm8
0x1807b0017  movsd   [rbp+1A0h+var_B8], xmm1
0x1807b001f  movsd   [rbp+1A0h+var_B0], xmm9
0x1807b0028  movsd   [rbp+1A0h+var_A8], xmm1
0x1807b0030  lea     rax, [rbp+1A0h+var_150]
0x1807b0034  mov     qword ptr [rbp+1A0h+var_220], rax
0x1807b0038  lea     rax, [rbp+1A0h+var_A0]
0x1807b003f  mov     qword ptr [rbp+1A0h+var_220+8], rax
0x1807b0043  mov     r8b, 1
0x1807b0046  lea     rdx, [rbp+1A0h+var_220]
0x1807b004a  lea     rcx, [rsp+2A0h+var_258]
0x1807b004f  call    sub_18061D834
0x1807b0054  mov     rsi, [rax]
0x1807b0057  mov     qword ptr [rax], 0
0x1807b005e  mov     [rbp+1A0h+var_158], rsi
0x1807b0062  mov     rcx, [rsp+2A0h+var_258]
0x1807b0067  test    rcx, rcx
0x1807b006a  jz      short loc_1807B0079
0x1807b006c  mov     rax, [rcx]
0x1807b006f  mov     rax, [rax+8]
0x1807b0073  call    cs:__guard_dispatch_icall_fptr
0x1807b0079  mov     r14d, 520h
0x1807b007f  mov     ecx, r14d
0x1807b0082  call    cs:mso40uiWin32Client_15794
0x1807b0088  mov     ecx, eax
0x1807b008a  shr     eax, 10h
0x1807b008d  movzx   eax, al
0x1807b0090  movd    xmm3, eax
0x1807b0094  cvtdq2ps xmm3, xmm3
0x1807b0097  movss   xmm6, cs:dword_180A9FCA8
0x1807b009f  divss   xmm3, xmm6
0x1807b00a3  movzx   eax, cx
0x1807b00a6  shr     ax, 8
0x1807b00aa  movzx   eax, ax
0x1807b00ad  movd    xmm2, eax
0x1807b00b1  cvtdq2ps xmm2, xmm2
0x1807b00b4  divss   xmm2, xmm6
0x1807b00b8  movzx   eax, cl
0x1807b00bb  movd    xmm0, eax
0x1807b00bf  cvtdq2ps xmm0, xmm0
0x1807b00c2  divss   xmm0, xmm6
0x1807b00c6  movss   dword ptr [rbp+1A0h+var_1D8], xmm0
0x1807b00cb  movss   dword ptr [rbp+1A0h+var_1D8+4], xmm2
0x1807b00d0  movss   [rbp+1A0h+var_1D0], xmm3
0x1807b00d5  mov     [rbp+1A0h+var_1CC], 3F800000h
0x1807b00dc  lea     r8, [rbp+1A0h+var_1D8]
0x1807b00e0  movaps  xmm1, xmm8
0x1807b00e4  lea     rcx, [rsp+2A0h+var_260]
0x1807b00e9  call    cs:?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z; GEL::IPen::Create(double,GEL::Color const &)
0x1807b00ef  nop
0x1807b00f0  mov     rbx, qword ptr [rsp+2A0h+var_248]
0x1807b00f5  mov     rax, [rbx]
0x1807b00f8  mov     rdi, [rax+90h]
0x1807b00ff  mov     ecx, r14d
0x1807b0102  call    cs:mso40uiWin32Client_15794
0x1807b0108  mov     ecx, eax
0x1807b010a  shr     eax, 10h
0x1807b010d  movzx   eax, al
0x1807b0110  movd    xmm2, eax
0x1807b0114  cvtdq2ps xmm2, xmm2
0x1807b0117  divss   xmm2, xmm6
0x1807b011b  movzx   eax, cx
0x1807b011e  shr     ax, 8
0x1807b0122  movzx   eax, ax
0x1807b0125  movd    xmm1, eax
0x1807b0129  cvtdq2ps xmm1, xmm1
0x1807b012c  divss   xmm1, xmm6
0x1807b0130  movzx   eax, cl
0x1807b0133  movd    xmm0, eax
0x1807b0137  cvtdq2ps xmm0, xmm0
0x1807b013a  divss   xmm0, xmm6
0x1807b013e  movss   dword ptr [rbp+1A0h+var_220], xmm0
0x1807b0143  movss   dword ptr [rbp+1A0h+var_220+4], xmm1
0x1807b0148  movss   dword ptr [rbp+1A0h+var_220+8], xmm2
0x1807b014d  mov     dword ptr [rbp+1A0h+var_220+0Ch], 3F800000h
0x1807b0154  lea     r8, [rbp+1A0h+var_220]
0x1807b0158  mov     rdx, rsi
0x1807b015b  lea     rcx, [rsp+2A0h+var_258]
0x1807b0160  call    cs:?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::Color const &)
0x1807b0166  nop
0x1807b0167  mov     rdx, [rax]
0x1807b016a  mov     rcx, rbx
0x1807b016d  mov     rax, rdi
0x1807b0170  call    cs:__guard_dispatch_icall_fptr
0x1807b0176  nop
0x1807b0177  mov     rcx, [rsp+2A0h+var_258]
0x1807b017c  test    rcx, rcx
0x1807b017f  jz      short loc_1807B018E
0x1807b0181  mov     rax, [rcx]
0x1807b0184  mov     rax, [rax+8]
0x1807b0188  call    cs:__guard_dispatch_icall_fptr
0x1807b018e  mov     rbx, qword ptr [rsp+2A0h+var_248]
0x1807b0193  mov     rax, [rbx]
0x1807b0196  mov     rdi, [rax+90h]
0x1807b019d  mov     r8, [rsp+2A0h+var_260]
0x1807b01a2  mov     rdx, rsi
0x1807b01a5  lea     rcx, [rsp+2A0h+var_258]
0x1807b01aa  call    cs:?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z; GEL::IEffectPennedPath::Create(GEL::IPath const &,GEL::IPen const &)
0x1807b01b0  nop
0x1807b01b1  mov     rdx, [rax]
0x1807b01b4  mov     rcx, rbx
0x1807b01b7  mov     rax, rdi
0x1807b01ba  call    cs:__guard_dispatch_icall_fptr
0x1807b01c0  nop
0x1807b01c1  mov     rcx, [rsp+2A0h+var_258]
0x1807b01c6  test    rcx, rcx
0x1807b01c9  jz      short loc_1807B01D9
0x1807b01cb  mov     rax, [rcx]
0x1807b01ce  mov     rax, [rax+8]
0x1807b01d2  call    cs:__guard_dispatch_icall_fptr
0x1807b01d8  nop
0x1807b01d9  mov     rcx, [rsp+2A0h+var_260]
0x1807b01de  test    rcx, rcx
  ... truncated ...
```
