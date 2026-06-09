# Mso::SVG::SVGCreatingCommandSink::CreateRasterFallbackShape(ARC::IGeometry const &,ARC::IBrush const &,bool,float,ARC::IStrokeStyle const *)

- ea: `0x180052528`
- end: `0x180052b83`
- name: `?CreateRasterFallbackShape@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGRect@SVG@Mso@@@3@AEBUIGeometry@ARC@@AEBUIBrush@6@_NMPEBUIStrokeStyle@6@@Z`
- size: `1627`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180140804`
- `0x180140946`

## callees

- `0x180052528`
- `0x180054bec`
- `0x180107840`
- `0x180129c04`
- `0x18013f708`
- `0x18013f73e`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180052b6e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180052b7c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180052b6e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180052b7c`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x180052589`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x180052589`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x180052b2f`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x180052b2f`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1800525d0`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1800525d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Mso::SVG::SVGCreatingCommandSink::CreateRasterFallbackShape(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        float a6)
{
  __int64 v8; // rsi
  float v9; // xmm3_4
  float v10; // xmm0_4
  double v11; // xmm9_8
  double v12; // xmm6_8
  double v13; // xmm7_8
  double v14; // xmm8_8
  double v15; // xmm0_8
  double v16; // xmm0_8
  int v17; // ebx
  double v18; // xmm6_8
  __int64 v19; // r12
  __int64 v20; // rbx
  void (__fastcall *v21)(__int64, __int64, _DWORD *, __int64, int); // rdi
  int v22; // eax
  __int64 v23; // r12
  float v24; // xmm0_4
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rbx
  void (__fastcall *v30)(__int64, __int64 *); // rax
  __int64 *v31; // rdi
  int v32; // r8d
  int v33; // r9d
  double v34; // xmm1_8
  double v35; // xmm0_8
  __int64 v36; // rsi
  __m128i si128; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v39; // [rsp+50h] [rbp-B0h]
  _DWORD v40[2]; // [rsp+60h] [rbp-A0h] BYREF
  __m128i v41; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v42[12]; // [rsp+78h] [rbp-88h] BYREF
  int v43; // [rsp+84h] [rbp-7Ch]
  __int64 v44; // [rsp+88h] [rbp-78h]
  __int128 v45; // [rsp+98h] [rbp-68h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-58h]
  _QWORD v47[3]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v48[64]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v49; // [rsp+108h] [rbp+8h]
  __int64 v50; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v51; // [rsp+1A8h] [rbp+A8h]
  __int64 *v52; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v53; // [rsp+1B8h] [rbp+B8h] BYREF

  v51 = a2;
  v50 = a1;
  v8 = a1 + 160;
  v47[0] = &Mso::SVG::SVGGeometrySink::`vftable';
  v47[1] = 0;
  v47[2] = 0;
  GEL::PathBuilder::PathBuilder((GEL::PathBuilder *)v48);
  v49 = 0;
  (*(void (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a3 + 56LL))(a3, v47, v8);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v39 = 0;
  GEL::PathBuilder::Finish(v48, &v52, v49);
  (*(void (__fastcall **)(__int64 *, __m128i *))(*v52 + 104))(v52, &si128);
  if ( v52 )
    (*(void (__fastcall **)(__int64 *))(*v52 + 8))(v52);
  if ( a5 )
  {
    v14 = *((double *)&v39 + 1);
    v12 = *(double *)&v39;
    v13 = *(double *)&si128.m128i_i64[1];
    v11 = *(double *)si128.m128i_i64;
  }
  else
  {
    v9 = (float)(a6 * *(float *)(v8 + 8)) + (float)(a6 * *(float *)v8);
    v10 = sqrtf_0(
            (float)(v9 * v9)
          + (float)((float)((float)(a6 * *(float *)(v8 + 12)) + (float)(a6 * *(float *)(v8 + 4)))
                  * (float)((float)(a6 * *(float *)(v8 + 12)) + (float)(a6 * *(float *)(v8 + 4)))))
        * 0.5;
    v11 = *(double *)si128.m128i_i64;
    v12 = *(double *)&v39;
    v13 = *(double *)&si128.m128i_i64[1];
    v14 = *((double *)&v39 + 1);
    if ( *(double *)si128.m128i_i64 <= *(double *)&v39 && *(double *)&si128.m128i_i64[1] <= *((double *)&v39 + 1) )
    {
      v15 = v10;
      v11 = *(double *)si128.m128i_i64 - v15;
      *(double *)si128.m128i_i64 = *(double *)si128.m128i_i64 - v15;
      v13 = *(double *)&si128.m128i_i64[1] - v15;
      *(double *)&si128.m128i_i64[1] = *(double *)&si128.m128i_i64[1] - v15;
      v12 = *(double *)&v39 + v15;
      *(double *)&v39 = *(double *)&v39 + v15;
      v14 = *((double *)&v39 + 1) + v15;
      *((double *)&v39 + 1) = *((double *)&v39 + 1) + v15;
    }
  }
  if ( v11 > v12 || v13 > v14 )
    v16 = 0.0;
  else
    v16 = v14 - v13;
  v17 = (int)ceil_0(v16);
  if ( v11 > v12 || v13 > v14 )
    v18 = 0.0;
  else
    v18 = v12 - v11;
  v40[0] = (int)ceil_0(v18);
  v40[1] = v17;
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 24LL))(a4);
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 408LL))(v19, &v53);
  v20 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v19 + 176LL))(
                     v19,
                     &v45,
                     0xFFFFFFFFLL,
                     0,
                     0,
                     0);
  v46 = v20;
  (**(void (__fastcall ***)(__int64))v20)(v20);
  if ( (_QWORD)v45 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v45 + 8LL))(v45);
  v21 = *(void (__fastcall **)(__int64, __int64, _DWORD *, __int64, int))(*(_QWORD *)v20 + 200LL);
  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 40LL))(v19, 0);
  v23 = v50;
  v21(v20, v53, v40, v50 + 12, v22);
  (*(void (__fastcall **)(__int64, __int64 **, __int64))(*(_QWORD *)v20 + 832LL))(v20, &v52, v53);
  v41 = *(__m128i *)v8;
  *(_QWORD *)v42 = *(_QWORD *)(v8 + 16);
  v24 = *(double *)si128.m128i_i64;
  *(float *)v42 = *(float *)v42 - v24;
  *(float *)&v42[4] = *(float *)&v42[4] - (float)*(double *)&si128.m128i_i64[1];
  (*(void (__fastcall **)(__int64 *))(*v52 + 168))(v52);
  (*(void (__fastcall **)(__int64 *, _QWORD))(*v52 + 104))(v52, *(unsigned int *)(v23 + 240));
  (*(void (__fastcall **)(__int64 *, _QWORD))(*v52 + 88))(v52, *(unsigned int *)(v23 + 232));
  (*(void (__fastcall **)(__int64 *, __m128i *))(*v52 + 72))(v52, &v41);
  v25 = *v52;
  v45 = 0;
  (*(void (__fastcall **)(__int64 *, __int128 *))(v25 + 192))(v52, &v45);
  v26 = *v52;
  if ( a5 )
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(v26 + 216))(v52, a3, a4);
  else
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(v26 + 224))(v52, a3, a4);
  (*(void (__fastcall **)(__int64 *))(*v52 + 176))(v52);
  if ( v52 )
    (*(void (__fastcall **)(__int64 *))(*v52 + 8))(v52);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  v27 = 0;
  v28 = 2;
  do
  {
    *(float *)((char *)&v50 + v27 * 4) = (float)(int)v40[v27];
    ++v27;
    --v28;
  }
  while ( v28 );
  v43 = 0;
  v44 = v50;
  v41 = _mm_load_si128((const __m128i *)&_xmm);
  *(float *)v42 = *(double *)si128.m128i_i64;
  *(_QWORD *)&v42[4] = COERCE_UNSIGNED_INT(*(double *)&si128.m128i_i64[1]);
  Mso::SVG::SVGCreatingCommandSink::GetEmbeddedImageForBitmap(
    v23,
    (unsigned int)&v52,
    v53,
    (unsigned int)&v42[8],
    (__int64)&v41,
    0,
    1);
  Mso::SVG::ISVGStyleProps::Create(&v50);
  if ( !a5 )
  {
    v29 = v50;
    if ( v50 )
    {
      v30 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 432LL);
      goto LABEL_30;
    }
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_44:
    CrashWithRecovery(0x1E3C3840u, 0);
    JUMPOUT(0x180052B82LL);
  }
  v29 = v50;
  if ( !v50 )
    goto LABEL_44;
  v30 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 176LL);
LABEL_30:
  v31 = v52;
  v30(v29, v52);
  if ( *(double *)si128.m128i_i64 > *(double *)&v39 || *(double *)&si128.m128i_i64[1] > *((double *)&v39 + 1) )
    v34 = 0.0;
  else
    v34 = *((double *)&v39 + 1) - *(double *)&si128.m128i_i64[1];
  if ( *(double *)si128.m128i_i64 > *(double *)&v39 || *(double *)&si128.m128i_i64[1] > *((double *)&v39 + 1) )
    v35 = 0.0;
  else
    v35 = *(double *)&v39 - *(double *)si128.m128i_i64;
  v36 = v51;
  Mso::SVG::ISVGRect::Create(v51, v29, v32, v33, *(__int64 *)&v35, *(__int64 *)&v34, 0, 0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  if ( v31 )
    (*(void (__fastcall **)(__int64 *))(*v31 + 8))(v31);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
  GEL::PathBuilder::~PathBuilder((GEL::PathBuilder *)v48);
  return v36;
}

```

## disassembly

```asm
0x180052528  mov     rax, rsp
0x18005252b  mov     [rax+10h], rdx
0x18005252f  mov     [rax+8], rcx
0x180052533  push    rbp
0x180052534  push    rbx
0x180052535  push    rsi
0x180052536  push    rdi
0x180052537  push    r12
0x180052539  push    r14
0x18005253b  push    r15
0x18005253d  lea     rbp, [rsp-60h]
0x180052542  sub     rsp, 160h
0x180052549  movaps  xmmword ptr [rax-48h], xmm6
0x18005254d  movaps  xmmword ptr [rax-58h], xmm7
0x180052551  movaps  xmmword ptr [rax-68h], xmm8
0x180052556  movaps  xmmword ptr [rax-78h], xmm9
0x18005255b  movaps  xmmword ptr [rax-88h], xmm10
0x180052563  mov     r15, r9
0x180052566  mov     r14, r8
0x180052569  xor     edi, edi
0x18005256b  lea     rsi, [rcx+0A0h]
0x180052572  lea     rax, ??_7SVGGeometrySink@SVG@Mso@@6B@; const Mso::SVG::SVGGeometrySink::`vftable'
0x180052579  mov     [rbp+90h+var_E0], rax
0x18005257d  mov     [rbp+90h+var_D8], rdi
0x180052581  mov     [rbp+90h+var_D0], rdi
0x180052585  lea     rcx, [rbp+90h+var_C8]
0x180052589  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x18005258f  mov     [rbp+90h+var_88], edi
0x180052592  mov     rax, [r14]
0x180052595  xorps   xmm3, xmm3
0x180052598  mov     r8, rsi
0x18005259b  lea     rdx, [rbp+90h+var_E0]
0x18005259f  mov     rcx, r14
0x1800525a2  mov     rax, [rax+38h]
0x1800525a6  call    cs:__guard_dispatch_icall_fptr
0x1800525ac  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1800525b4  movups  [rsp+190h+var_150], xmm0
0x1800525b9  xorps   xmm0, xmm0
0x1800525bc  movups  [rsp+190h+var_140], xmm0
0x1800525c1  mov     r8d, [rbp+90h+var_88]
0x1800525c5  lea     rdx, [rbp+90h+arg_10]
0x1800525cc  lea     rcx, [rbp+90h+var_C8]
0x1800525d0  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x1800525d6  nop
0x1800525d7  mov     rcx, [rbp+90h+arg_10]
0x1800525de  mov     rax, [rcx]
0x1800525e1  lea     rdx, [rsp+190h+var_150]
0x1800525e6  mov     rax, [rax+68h]
0x1800525ea  call    cs:__guard_dispatch_icall_fptr
0x1800525f0  nop
0x1800525f1  mov     rcx, [rbp+90h+arg_10]
0x1800525f8  test    rcx, rcx
0x1800525fb  jz      short loc_18005260A
0x1800525fd  mov     rax, [rcx]
0x180052600  mov     rax, [rax+8]
0x180052604  call    cs:__guard_dispatch_icall_fptr
0x18005260a  cmp     [rbp+90h+arg_20], dil
0x180052611  jnz     loc_1800526C8
0x180052617  movss   xmm3, [rbp+90h+arg_28]
0x18005261f  mulss   xmm3, dword ptr [rsi+8]
0x180052624  movss   xmm0, [rbp+90h+arg_28]
0x18005262c  mulss   xmm0, dword ptr [rsi]
0x180052630  addss   xmm3, xmm0
0x180052634  movss   xmm2, [rbp+90h+arg_28]
0x18005263c  mulss   xmm2, dword ptr [rsi+0Ch]
0x180052641  movss   xmm1, [rbp+90h+arg_28]
0x180052649  mulss   xmm1, dword ptr [rsi+4]
0x18005264e  addss   xmm2, xmm1
0x180052652  mulss   xmm3, xmm3
0x180052656  mulss   xmm2, xmm2
0x18005265a  addss   xmm3, xmm2
0x18005265e  movaps  xmm0, xmm3; X
0x180052661  call    sqrtf_0
0x180052666  mulss   xmm0, cs:__real@3f000000
0x18005266e  movsd   xmm9, qword ptr [rsp+190h+var_150]
0x180052675  movsd   xmm6, qword ptr [rsp+190h+var_140]
0x18005267b  movsd   xmm7, qword ptr [rsp+190h+var_150+8]
0x180052681  movsd   xmm8, qword ptr [rsp+190h+var_140+8]
0x180052688  comisd  xmm9, xmm6
0x18005268d  ja      short loc_1800526E2
0x18005268f  comisd  xmm7, xmm8
0x180052694  ja      short loc_1800526E2
0x180052696  cvtss2sd xmm0, xmm0
0x18005269a  subsd   xmm9, xmm0
0x18005269f  movsd   qword ptr [rsp+190h+var_150], xmm9
0x1800526a6  subsd   xmm7, xmm0
0x1800526aa  movsd   qword ptr [rsp+190h+var_150+8], xmm7
0x1800526b0  addsd   xmm6, xmm0
0x1800526b4  movsd   qword ptr [rsp+190h+var_140], xmm6
0x1800526ba  addsd   xmm8, xmm0
0x1800526bf  movsd   qword ptr [rsp+190h+var_140+8], xmm8
0x1800526c6  jmp     short loc_1800526E2
0x1800526c8  movsd   xmm8, qword ptr [rsp+190h+var_140+8]
0x1800526cf  movsd   xmm6, qword ptr [rsp+190h+var_140]
0x1800526d5  movsd   xmm7, qword ptr [rsp+190h+var_150+8]
0x1800526db  movsd   xmm9, qword ptr [rsp+190h+var_150]
0x1800526e2  xorps   xmm10, xmm10
0x1800526e6  comisd  xmm9, xmm6
0x1800526eb  ja      short loc_1800526FE
0x1800526ed  comisd  xmm7, xmm8
0x1800526f2  ja      short loc_1800526FE
0x1800526f4  movaps  xmm0, xmm8
0x1800526f8  subsd   xmm0, xmm7
0x1800526fc  jmp     short loc_180052701
0x1800526fe  xorps   xmm0, xmm0; X
0x180052701  call    ceil_0
0x180052706  cvttsd2si rbx, xmm0
0x18005270b  comisd  xmm9, xmm6
0x180052710  ja      short loc_180052720
0x180052712  comisd  xmm7, xmm8
0x180052717  ja      short loc_180052720
0x180052719  subsd   xmm6, xmm9
0x18005271e  jmp     short loc_180052723
0x180052720  xorps   xmm6, xmm6
0x180052723  movaps  xmm0, xmm6; X
0x180052726  call    ceil_0
0x18005272b  cvttsd2si rax, xmm0
0x180052730  mov     [rsp+190h+var_130], eax
0x180052734  mov     [rsp+190h+var_12C], ebx
0x180052738  mov     rax, [r15]
0x18005273b  mov     rcx, r15
0x18005273e  mov     rax, [rax+18h]
0x180052742  call    cs:__guard_dispatch_icall_fptr
0x180052748  mov     r12, rax
0x18005274b  mov     rcx, [rax]
0x18005274e  mov     rax, [rcx+198h]
0x180052755  lea     rdx, [rbp+90h+arg_18]
0x18005275c  mov     rcx, r12
0x18005275f  call    cs:__guard_dispatch_icall_fptr
0x180052765  nop
0x180052766  mov     rcx, [r12]
0x18005276a  mov     rax, [rcx+0B0h]
0x180052771  mov     [rsp+190h+var_168], rdi
0x180052776  mov     [rsp+190h+var_170], rdi
0x18005277b  xor     r9d, r9d
0x18005277e  or      r8d, 0FFFFFFFFh
0x180052782  lea     rdx, [rbp+90h+var_F8]
0x180052786  mov     rcx, r12
0x180052789  call    cs:__guard_dispatch_icall_fptr
0x18005278f  mov     rbx, [rax]
0x180052792  mov     [rbp+90h+var_E8], rbx
0x180052796  mov     rax, [rbx]
0x180052799  mov     rcx, rbx
0x18005279c  mov     rax, [rax]
0x18005279f  call    cs:__guard_dispatch_icall_fptr
0x1800527a5  nop
0x1800527a6  mov     rcx, qword ptr [rbp+90h+var_F8]
0x1800527aa  test    rcx, rcx
0x1800527ad  jz      short loc_1800527BC
0x1800527af  mov     rax, [rcx]
0x1800527b2  mov     rax, [rax+8]
0x1800527b6  call    cs:__guard_dispatch_icall_fptr
0x1800527bc  mov     rax, [rbx]
0x1800527bf  mov     rdi, [rax+0C8h]
0x1800527c6  mov     rax, [r12]
0x1800527ca  xor     edx, edx
0x1800527cc  mov     rcx, r12
0x1800527cf  mov     rax, [rax+28h]
0x1800527d3  call    cs:__guard_dispatch_icall_fptr
0x1800527d9  mov     r12, [rbp+90h+arg_0]
0x1800527e0  lea     r9, [r12+0Ch]
0x1800527e5  mov     dword ptr [rsp+190h+var_170], eax
0x1800527e9  lea     r8, [rsp+190h+var_130]
0x1800527ee  mov     rdx, [rbp+90h+arg_18]
0x1800527f5  mov     rcx, rbx
0x1800527f8  mov     rax, rdi
0x1800527fb  call    cs:__guard_dispatch_icall_fptr
0x180052801  mov     rax, [rbx]
0x180052804  mov     r8, [rbp+90h+arg_18]
0x18005280b  lea     rdx, [rbp+90h+arg_10]
0x180052812  mov     rcx, rbx
0x180052815  mov     rax, [rax+340h]
0x18005281c  call    cs:__guard_dispatch_icall_fptr
0x180052822  nop
0x180052823  movups  xmm0, xmmword ptr [rsi]
0x180052826  movups  [rsp+190h+var_128], xmm0
0x18005282b  movsd   xmm1, qword ptr [rsi+10h]
0x180052830  movsd   [rsp+190h+var_118], xmm1
0x180052836  movsd   xmm0, qword ptr [rsp+190h+var_150]
0x18005283c  cvtpd2ps xmm0, xmm0
0x180052840  movss   xmm2, dword ptr [rsp+190h+var_118]
0x180052846  subss   xmm2, xmm0
0x18005284a  movss   dword ptr [rsp+190h+var_118], xmm2
0x180052850  movsd   xmm0, qword ptr [rsp+190h+var_150+8]
0x180052856  cvtpd2ps xmm0, xmm0
0x18005285a  movss   xmm1, dword ptr [rsp+190h+var_118+4]
0x180052860  subss   xmm1, xmm0
0x180052864  movss   dword ptr [rsp+190h+var_118+4], xmm1
0x18005286a  mov     rcx, [rbp+90h+arg_10]
0x180052871  mov     rax, [rcx]
0x180052874  mov     rax, [rax+0A8h]
0x18005287b  call    cs:__guard_dispatch_icall_fptr
0x180052881  mov     rcx, [rbp+90h+arg_10]
0x180052888  mov     rax, [rcx]
0x18005288b  mov     edx, [r12+0F0h]
0x180052893  mov     rax, [rax+68h]
0x180052897  call    cs:__guard_dispatch_icall_fptr
0x18005289d  mov     rcx, [rbp+90h+arg_10]
0x1800528a4  mov     rax, [rcx]
0x1800528a7  mov     edx, [r12+0E8h]
0x1800528af  mov     rax, [rax+58h]
0x1800528b3  call    cs:__guard_dispatch_icall_fptr
0x1800528b9  mov     rcx, [rbp+90h+arg_10]
0x1800528c0  mov     rax, [rcx]
0x1800528c3  lea     rdx, [rsp+190h+var_128]
0x1800528c8  mov     rax, [rax+48h]
0x1800528cc  call    cs:__guard_dispatch_icall_fptr
0x1800528d2  mov     rcx, [rbp+90h+arg_10]
0x1800528d9  mov     rax, [rcx]
0x1800528dc  xorps   xmm0, xmm0
0x1800528df  movups  [rbp+90h+var_F8], xmm0
0x1800528e3  lea     rdx, [rbp+90h+var_F8]
0x1800528e7  mov     rax, [rax+0C0h]
0x1800528ee  call    cs:__guard_dispatch_icall_fptr
0x1800528f4  mov     rcx, [rbp+90h+arg_10]
0x1800528fb  mov     r8, r15
0x1800528fe  mov     rax, [rcx]
0x180052901  cmp     [rbp+90h+arg_20], 0
0x180052908  jz      short loc_18005291C
0x18005290a  mov     rdx, r14
0x18005290d  mov     rax, [rax+0D8h]
0x180052914  call    cs:__guard_dispatch_icall_fptr
0x18005291a  jmp     short loc_180052940
0x18005291c  mov     rdx, [rbp+90h+arg_30]
0x180052923  mov     [rsp+190h+var_170], rdx
0x180052928  movss   xmm3, [rbp+90h+arg_28]
0x180052930  mov     rdx, r14
0x180052933  mov     rax, [rax+0E0h]
0x18005293a  call    cs:__guard_dispatch_icall_fptr
0x180052940  mov     rcx, [rbp+90h+arg_10]
0x180052947  mov     rax, [rcx]
0x18005294a  mov     rax, [rax+0B0h]
0x180052951  call    cs:__guard_dispatch_icall_fptr
0x180052957  nop
0x180052958  mov     rcx, [rbp+90h+arg_10]
0x18005295f  test    rcx, rcx
0x180052962  jz      short loc_180052972
0x180052964  mov     rax, [rcx]
0x180052967  mov     rax, [rax+8]
0x18005296b  call    cs:__guard_dispatch_icall_fptr
0x180052971  nop
0x180052972  mov     rax, [rbx]
0x180052975  mov     rcx, rbx
0x180052978  mov     rax, [rax+8]
0x18005297c  call    cs:__guard_dispatch_icall_fptr
0x180052982  xor     ecx, ecx
0x180052984  lea     edx, [rcx+2]
0x180052987  mov     eax, [rsp+rcx+190h+var_130]
0x18005298b  xorps   xmm0, xmm0
0x18005298e  cvtsi2ss xmm0, rax
0x180052993  movss   dword ptr [rbp+rcx+90h+arg_0], xmm0
0x18005299c  lea     rcx, [rcx+4]
0x1800529a0  sub     rdx, 1
0x1800529a4  jnz     short loc_180052987
0x1800529a6  mov     [rbp+90h+var_110], rdx
0x1800529aa  movss   xmm0, dword ptr [rbp+90h+arg_0]
0x1800529b2  movss   dword ptr [rbp+90h+var_108], xmm0
0x1800529b7  movss   xmm1, dword ptr [rbp+90h+arg_0+4]
0x1800529bf  movss   dword ptr [rbp+90h+var_108+4], xmm1
0x1800529c4  movsd   xmm3, qword ptr [rsp+190h+var_150+8]
0x1800529ca  cvtpd2ps xmm3, xmm3
0x1800529ce  movsd   xmm2, qword ptr [rsp+190h+var_150]
0x1800529d4  cvtpd2ps xmm2, xmm2
0x1800529d8  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x1800529e0  movups  [rsp+190h+var_128], xmm0
0x1800529e5  movss   dword ptr [rsp+190h+var_118], xmm2
0x1800529eb  movss   dword ptr [rsp+190h+var_118+4], xmm3
0x1800529f1  mov     dword ptr [rsp+190h+var_160], 1
0x1800529f9  mov     [rsp+190h+var_168], rdx
0x1800529fe  lea     rax, [rsp+190h+var_128]
0x180052a03  mov     [rsp+190h+var_170], rax
0x180052a08  lea     r9, [rbp+90h+var_110]
0x180052a0c  mov     r8, [rbp+90h+arg_18]
0x180052a13  lea     rdx, [rbp+90h+arg_10]
0x180052a1a  mov     rcx, r12
0x180052a1d  call    ?GetEmbeddedImageForBitmap@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGEmbeddedImage@SVG@Mso@@@3@AEBUIBitmap@ARC@@AEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@Math@@AEBU?$TAffine3x3@M@8@PEBU98@W4InterpolationMode@6@@Z; Mso::SVG::SVGCreatingCommandSink::GetEmbeddedImageForBitmap(ARC::IBitmap const &,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const &,Math::TAffine3x3<float> const &,Math::TAffine3x3<float> const *,ARC::InterpolationMode)
0x180052a22  lea     rcx, [rbp+90h+arg_0]
0x180052a29  call    ?Create@ISVGStyleProps@SVG@Mso@@SA?AV?$TCntPtr@UISVGStyleProps@SVG@Mso@@@3@XZ; Mso::SVG::ISVGStyleProps::Create(void)
0x180052a2e  cmp     [rbp+90h+arg_20], 0
0x180052a35  jz      short loc_180052A53
0x180052a37  mov     rbx, [rbp+90h+arg_0]
0x180052a3e  test    rbx, rbx
0x180052a41  jz      loc_180052B75
0x180052a47  mov     rax, [rbx]
0x180052a4a  mov     rax, [rax+0B0h]
0x180052a51  jmp     short loc_180052A6D
0x180052a53  mov     rbx, [rbp+90h+arg_0]
0x180052a5a  test    rbx, rbx
0x180052a5d  jz      loc_180052B67
0x180052a63  mov     rax, [rbx]
0x180052a66  mov     rax, [rax+1B0h]
0x180052a6d  mov     rdi, [rbp+90h+arg_10]
0x180052a74  mov     rdx, rdi
0x180052a77  mov     rcx, rbx
0x180052a7a  call    cs:__guard_dispatch_icall_fptr
0x180052a80  movsd   xmm4, qword ptr [rsp+190h+var_140+8]
0x180052a86  movsd   xmm3, qword ptr [rsp+190h+var_150+8]
0x180052a8c  movsd   xmm2, qword ptr [rsp+190h+var_150]
0x180052a92  movsd   xmm0, qword ptr [rsp+190h+var_140]
0x180052a98  comisd  xmm2, xmm0
  ... truncated ...
```
