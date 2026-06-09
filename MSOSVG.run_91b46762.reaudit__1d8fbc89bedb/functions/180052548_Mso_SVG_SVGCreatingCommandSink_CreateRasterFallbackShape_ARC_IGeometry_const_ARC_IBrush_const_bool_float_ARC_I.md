# Mso::SVG::SVGCreatingCommandSink::CreateRasterFallbackShape(ARC::IGeometry const &,ARC::IBrush const &,bool,float,ARC::IStrokeStyle const *)

- ea: `0x180052548`
- end: `0x180052ba3`
- name: `?CreateRasterFallbackShape@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGRect@SVG@Mso@@@3@AEBUIGeometry@ARC@@AEBUIBrush@6@_NMPEBUIStrokeStyle@6@@Z`
- size: `1627`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1801408b4`
- `0x1801409f6`

## callees

- `0x180052548`
- `0x180054c0c`
- `0x180107870`
- `0x180129c34`
- `0x18013f7b8`
- `0x18013f7ee`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180052b8e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180052b9c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180052b8e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180052b9c`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1800525a9`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1800525a9`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x180052b4f`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x180052b4f`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1800525f0`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1800525f0`

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
  void (__fastcall *v21)(__int64, __int64 *, _DWORD *, __int64, int); // rdi
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
  __int64 *v53; // [rsp+1B8h] [rbp+B8h] BYREF

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
  (*(void (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v19 + 408LL))(v19, &v53);
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
  v21 = *(void (__fastcall **)(__int64, __int64 *, _DWORD *, __int64, int))(*(_QWORD *)v20 + 200LL);
  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 40LL))(v19, 0);
  v23 = v50;
  v21(v20, v53, v40, v50 + 12, v22);
  (*(void (__fastcall **)(__int64, __int64 **, __int64 *))(*(_QWORD *)v20 + 832LL))(v20, &v52, v53);
  v41 = *(__m128i *)v8;
  *(_QWORD *)v42 = *(_QWORD *)(v8 + 16);
  v24 = *(double *)si128.m128i_i64;
  *(float *)v42 = *(float *)v42 - v24;
  *(float *)&v42[4] = *(float *)&v42[4] - (float)*(double *)&si128.m128i_i64[1];
  (*(void (__fastcall **)(__int64 *))(*v52 + 160))(v52);
  (*(void (__fastcall **)(__int64 *, _QWORD))(*v52 + 96))(v52, *(unsigned int *)(v23 + 240));
  (*(void (__fastcall **)(__int64 *, _QWORD))(*v52 + 80))(v52, *(unsigned int *)(v23 + 232));
  (*(void (__fastcall **)(__int64 *, __m128i *))(*v52 + 64))(v52, &v41);
  v25 = *v52;
  v45 = 0;
  (*(void (__fastcall **)(__int64 *, __int128 *))(v25 + 184))(v52, &v45);
  v26 = *v52;
  if ( a5 )
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(v26 + 208))(v52, a3, a4);
  else
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(v26 + 216))(v52, a3, a4);
  (*(void (__fastcall **)(__int64 *))(*v52 + 168))(v52);
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
  Mso::SVG::SVGCreatingCommandSink::GetEmbeddedImageForBitmap(v23, &v52, v53, (float *)&v42[8], (__m64 *)&v41, 0, 1);
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
    JUMPOUT(0x180052BA2LL);
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
    (*(void (__fastcall **)(__int64 *))(*v53 + 8))(v53);
  GEL::PathBuilder::~PathBuilder((GEL::PathBuilder *)v48);
  return v36;
}

```

## disassembly

```asm
0x180052548  mov     rax, rsp
0x18005254b  mov     [rax+10h], rdx
0x18005254f  mov     [rax+8], rcx
0x180052553  push    rbp
0x180052554  push    rbx
0x180052555  push    rsi
0x180052556  push    rdi
0x180052557  push    r12
0x180052559  push    r14
0x18005255b  push    r15
0x18005255d  lea     rbp, [rsp-60h]
0x180052562  sub     rsp, 160h
0x180052569  movaps  xmmword ptr [rax-48h], xmm6
0x18005256d  movaps  xmmword ptr [rax-58h], xmm7
0x180052571  movaps  xmmword ptr [rax-68h], xmm8
0x180052576  movaps  xmmword ptr [rax-78h], xmm9
0x18005257b  movaps  xmmword ptr [rax-88h], xmm10
0x180052583  mov     r15, r9
0x180052586  mov     r14, r8
0x180052589  xor     edi, edi
0x18005258b  lea     rsi, [rcx+0A0h]
0x180052592  lea     rax, ??_7SVGGeometrySink@SVG@Mso@@6B@; const Mso::SVG::SVGGeometrySink::`vftable'
0x180052599  mov     [rbp+90h+var_E0], rax
0x18005259d  mov     [rbp+90h+var_D8], rdi
0x1800525a1  mov     [rbp+90h+var_D0], rdi
0x1800525a5  lea     rcx, [rbp+90h+var_C8]
0x1800525a9  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x1800525af  mov     [rbp+90h+var_88], edi
0x1800525b2  mov     rax, [r14]
0x1800525b5  xorps   xmm3, xmm3
0x1800525b8  mov     r8, rsi
0x1800525bb  lea     rdx, [rbp+90h+var_E0]
0x1800525bf  mov     rcx, r14
0x1800525c2  mov     rax, [rax+38h]
0x1800525c6  call    cs:__guard_dispatch_icall_fptr
0x1800525cc  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1800525d4  movups  [rsp+190h+var_150], xmm0
0x1800525d9  xorps   xmm0, xmm0
0x1800525dc  movups  [rsp+190h+var_140], xmm0
0x1800525e1  mov     r8d, [rbp+90h+var_88]
0x1800525e5  lea     rdx, [rbp+90h+arg_10]
0x1800525ec  lea     rcx, [rbp+90h+var_C8]
0x1800525f0  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x1800525f6  nop
0x1800525f7  mov     rcx, [rbp+90h+arg_10]
0x1800525fe  mov     rax, [rcx]
0x180052601  lea     rdx, [rsp+190h+var_150]
0x180052606  mov     rax, [rax+68h]
0x18005260a  call    cs:__guard_dispatch_icall_fptr
0x180052610  nop
0x180052611  mov     rcx, [rbp+90h+arg_10]
0x180052618  test    rcx, rcx
0x18005261b  jz      short loc_18005262A
0x18005261d  mov     rax, [rcx]
0x180052620  mov     rax, [rax+8]
0x180052624  call    cs:__guard_dispatch_icall_fptr
0x18005262a  cmp     [rbp+90h+arg_20], dil
0x180052631  jnz     loc_1800526E8
0x180052637  movss   xmm3, [rbp+90h+arg_28]
0x18005263f  mulss   xmm3, dword ptr [rsi+8]
0x180052644  movss   xmm0, [rbp+90h+arg_28]
0x18005264c  mulss   xmm0, dword ptr [rsi]
0x180052650  addss   xmm3, xmm0
0x180052654  movss   xmm2, [rbp+90h+arg_28]
0x18005265c  mulss   xmm2, dword ptr [rsi+0Ch]
0x180052661  movss   xmm1, [rbp+90h+arg_28]
0x180052669  mulss   xmm1, dword ptr [rsi+4]
0x18005266e  addss   xmm2, xmm1
0x180052672  mulss   xmm3, xmm3
0x180052676  mulss   xmm2, xmm2
0x18005267a  addss   xmm3, xmm2
0x18005267e  movaps  xmm0, xmm3; X
0x180052681  call    sqrtf_0
0x180052686  mulss   xmm0, cs:__real@3f000000
0x18005268e  movsd   xmm9, qword ptr [rsp+190h+var_150]
0x180052695  movsd   xmm6, qword ptr [rsp+190h+var_140]
0x18005269b  movsd   xmm7, qword ptr [rsp+190h+var_150+8]
0x1800526a1  movsd   xmm8, qword ptr [rsp+190h+var_140+8]
0x1800526a8  comisd  xmm9, xmm6
0x1800526ad  ja      short loc_180052702
0x1800526af  comisd  xmm7, xmm8
0x1800526b4  ja      short loc_180052702
0x1800526b6  cvtss2sd xmm0, xmm0
0x1800526ba  subsd   xmm9, xmm0
0x1800526bf  movsd   qword ptr [rsp+190h+var_150], xmm9
0x1800526c6  subsd   xmm7, xmm0
0x1800526ca  movsd   qword ptr [rsp+190h+var_150+8], xmm7
0x1800526d0  addsd   xmm6, xmm0
0x1800526d4  movsd   qword ptr [rsp+190h+var_140], xmm6
0x1800526da  addsd   xmm8, xmm0
0x1800526df  movsd   qword ptr [rsp+190h+var_140+8], xmm8
0x1800526e6  jmp     short loc_180052702
0x1800526e8  movsd   xmm8, qword ptr [rsp+190h+var_140+8]
0x1800526ef  movsd   xmm6, qword ptr [rsp+190h+var_140]
0x1800526f5  movsd   xmm7, qword ptr [rsp+190h+var_150+8]
0x1800526fb  movsd   xmm9, qword ptr [rsp+190h+var_150]
0x180052702  xorps   xmm10, xmm10
0x180052706  comisd  xmm9, xmm6
0x18005270b  ja      short loc_18005271E
0x18005270d  comisd  xmm7, xmm8
0x180052712  ja      short loc_18005271E
0x180052714  movaps  xmm0, xmm8
0x180052718  subsd   xmm0, xmm7
0x18005271c  jmp     short loc_180052721
0x18005271e  xorps   xmm0, xmm0; X
0x180052721  call    ceil_0
0x180052726  cvttsd2si rbx, xmm0
0x18005272b  comisd  xmm9, xmm6
0x180052730  ja      short loc_180052740
0x180052732  comisd  xmm7, xmm8
0x180052737  ja      short loc_180052740
0x180052739  subsd   xmm6, xmm9
0x18005273e  jmp     short loc_180052743
0x180052740  xorps   xmm6, xmm6
0x180052743  movaps  xmm0, xmm6; X
0x180052746  call    ceil_0
0x18005274b  cvttsd2si rax, xmm0
0x180052750  mov     [rsp+190h+var_130], eax
0x180052754  mov     [rsp+190h+var_12C], ebx
0x180052758  mov     rax, [r15]
0x18005275b  mov     rcx, r15
0x18005275e  mov     rax, [rax+18h]
0x180052762  call    cs:__guard_dispatch_icall_fptr
0x180052768  mov     r12, rax
0x18005276b  mov     rcx, [rax]
0x18005276e  mov     rax, [rcx+198h]
0x180052775  lea     rdx, [rbp+90h+arg_18]
0x18005277c  mov     rcx, r12
0x18005277f  call    cs:__guard_dispatch_icall_fptr
0x180052785  nop
0x180052786  mov     rcx, [r12]
0x18005278a  mov     rax, [rcx+0B0h]
0x180052791  mov     [rsp+190h+var_168], rdi
0x180052796  mov     [rsp+190h+var_170], rdi
0x18005279b  xor     r9d, r9d
0x18005279e  or      r8d, 0FFFFFFFFh
0x1800527a2  lea     rdx, [rbp+90h+var_F8]
0x1800527a6  mov     rcx, r12
0x1800527a9  call    cs:__guard_dispatch_icall_fptr
0x1800527af  mov     rbx, [rax]
0x1800527b2  mov     [rbp+90h+var_E8], rbx
0x1800527b6  mov     rax, [rbx]
0x1800527b9  mov     rcx, rbx
0x1800527bc  mov     rax, [rax]
0x1800527bf  call    cs:__guard_dispatch_icall_fptr
0x1800527c5  nop
0x1800527c6  mov     rcx, qword ptr [rbp+90h+var_F8]
0x1800527ca  test    rcx, rcx
0x1800527cd  jz      short loc_1800527DC
0x1800527cf  mov     rax, [rcx]
0x1800527d2  mov     rax, [rax+8]
0x1800527d6  call    cs:__guard_dispatch_icall_fptr
0x1800527dc  mov     rax, [rbx]
0x1800527df  mov     rdi, [rax+0C8h]
0x1800527e6  mov     rax, [r12]
0x1800527ea  xor     edx, edx
0x1800527ec  mov     rcx, r12
0x1800527ef  mov     rax, [rax+28h]
0x1800527f3  call    cs:__guard_dispatch_icall_fptr
0x1800527f9  mov     r12, [rbp+90h+arg_0]
0x180052800  lea     r9, [r12+0Ch]
0x180052805  mov     dword ptr [rsp+190h+var_170], eax
0x180052809  lea     r8, [rsp+190h+var_130]
0x18005280e  mov     rdx, [rbp+90h+arg_18]
0x180052815  mov     rcx, rbx
0x180052818  mov     rax, rdi
0x18005281b  call    cs:__guard_dispatch_icall_fptr
0x180052821  mov     rax, [rbx]
0x180052824  mov     r8, [rbp+90h+arg_18]
0x18005282b  lea     rdx, [rbp+90h+arg_10]
0x180052832  mov     rcx, rbx
0x180052835  mov     rax, [rax+340h]
0x18005283c  call    cs:__guard_dispatch_icall_fptr
0x180052842  nop
0x180052843  movups  xmm0, xmmword ptr [rsi]
0x180052846  movups  [rsp+190h+var_128], xmm0
0x18005284b  movsd   xmm1, qword ptr [rsi+10h]
0x180052850  movsd   [rsp+190h+var_118], xmm1
0x180052856  movsd   xmm0, qword ptr [rsp+190h+var_150]
0x18005285c  cvtpd2ps xmm0, xmm0
0x180052860  movss   xmm2, dword ptr [rsp+190h+var_118]
0x180052866  subss   xmm2, xmm0
0x18005286a  movss   dword ptr [rsp+190h+var_118], xmm2
0x180052870  movsd   xmm0, qword ptr [rsp+190h+var_150+8]
0x180052876  cvtpd2ps xmm0, xmm0
0x18005287a  movss   xmm1, dword ptr [rsp+190h+var_118+4]
0x180052880  subss   xmm1, xmm0
0x180052884  movss   dword ptr [rsp+190h+var_118+4], xmm1
0x18005288a  mov     rcx, [rbp+90h+arg_10]
0x180052891  mov     rax, [rcx]
0x180052894  mov     rax, [rax+0A0h]
0x18005289b  call    cs:__guard_dispatch_icall_fptr
0x1800528a1  mov     rcx, [rbp+90h+arg_10]
0x1800528a8  mov     rax, [rcx]
0x1800528ab  mov     edx, [r12+0F0h]
0x1800528b3  mov     rax, [rax+60h]
0x1800528b7  call    cs:__guard_dispatch_icall_fptr
0x1800528bd  mov     rcx, [rbp+90h+arg_10]
0x1800528c4  mov     rax, [rcx]
0x1800528c7  mov     edx, [r12+0E8h]
0x1800528cf  mov     rax, [rax+50h]
0x1800528d3  call    cs:__guard_dispatch_icall_fptr
0x1800528d9  mov     rcx, [rbp+90h+arg_10]
0x1800528e0  mov     rax, [rcx]
0x1800528e3  lea     rdx, [rsp+190h+var_128]
0x1800528e8  mov     rax, [rax+40h]
0x1800528ec  call    cs:__guard_dispatch_icall_fptr
0x1800528f2  mov     rcx, [rbp+90h+arg_10]
0x1800528f9  mov     rax, [rcx]
0x1800528fc  xorps   xmm0, xmm0
0x1800528ff  movups  [rbp+90h+var_F8], xmm0
0x180052903  lea     rdx, [rbp+90h+var_F8]
0x180052907  mov     rax, [rax+0B8h]
0x18005290e  call    cs:__guard_dispatch_icall_fptr
0x180052914  mov     rcx, [rbp+90h+arg_10]
0x18005291b  mov     r8, r15
0x18005291e  mov     rax, [rcx]
0x180052921  cmp     [rbp+90h+arg_20], 0
0x180052928  jz      short loc_18005293C
0x18005292a  mov     rdx, r14
0x18005292d  mov     rax, [rax+0D0h]
0x180052934  call    cs:__guard_dispatch_icall_fptr
0x18005293a  jmp     short loc_180052960
0x18005293c  mov     rdx, [rbp+90h+arg_30]
0x180052943  mov     [rsp+190h+var_170], rdx
0x180052948  movss   xmm3, [rbp+90h+arg_28]
0x180052950  mov     rdx, r14
0x180052953  mov     rax, [rax+0D8h]
0x18005295a  call    cs:__guard_dispatch_icall_fptr
0x180052960  mov     rcx, [rbp+90h+arg_10]
0x180052967  mov     rax, [rcx]
0x18005296a  mov     rax, [rax+0A8h]
0x180052971  call    cs:__guard_dispatch_icall_fptr
0x180052977  nop
0x180052978  mov     rcx, [rbp+90h+arg_10]
0x18005297f  test    rcx, rcx
0x180052982  jz      short loc_180052992
0x180052984  mov     rax, [rcx]
0x180052987  mov     rax, [rax+8]
0x18005298b  call    cs:__guard_dispatch_icall_fptr
0x180052991  nop
0x180052992  mov     rax, [rbx]
0x180052995  mov     rcx, rbx
0x180052998  mov     rax, [rax+8]
0x18005299c  call    cs:__guard_dispatch_icall_fptr
0x1800529a2  xor     ecx, ecx
0x1800529a4  lea     edx, [rcx+2]
0x1800529a7  mov     eax, [rsp+rcx+190h+var_130]
0x1800529ab  xorps   xmm0, xmm0
0x1800529ae  cvtsi2ss xmm0, rax
0x1800529b3  movss   dword ptr [rbp+rcx+90h+arg_0], xmm0
0x1800529bc  lea     rcx, [rcx+4]
0x1800529c0  sub     rdx, 1
0x1800529c4  jnz     short loc_1800529A7
0x1800529c6  mov     [rbp+90h+var_110], rdx
0x1800529ca  movss   xmm0, dword ptr [rbp+90h+arg_0]
0x1800529d2  movss   dword ptr [rbp+90h+var_108], xmm0
0x1800529d7  movss   xmm1, dword ptr [rbp+90h+arg_0+4]
0x1800529df  movss   dword ptr [rbp+90h+var_108+4], xmm1
0x1800529e4  movsd   xmm3, qword ptr [rsp+190h+var_150+8]
0x1800529ea  cvtpd2ps xmm3, xmm3
0x1800529ee  movsd   xmm2, qword ptr [rsp+190h+var_150]
0x1800529f4  cvtpd2ps xmm2, xmm2
0x1800529f8  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x180052a00  movups  [rsp+190h+var_128], xmm0
0x180052a05  movss   dword ptr [rsp+190h+var_118], xmm2
0x180052a0b  movss   dword ptr [rsp+190h+var_118+4], xmm3
0x180052a11  mov     dword ptr [rsp+190h+var_160], 1
0x180052a19  mov     [rsp+190h+var_168], rdx
0x180052a1e  lea     rax, [rsp+190h+var_128]
0x180052a23  mov     [rsp+190h+var_170], rax
0x180052a28  lea     r9, [rbp+90h+var_110]
0x180052a2c  mov     r8, [rbp+90h+arg_18]
0x180052a33  lea     rdx, [rbp+90h+arg_10]
0x180052a3a  mov     rcx, r12
0x180052a3d  call    ?GetEmbeddedImageForBitmap@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGEmbeddedImage@SVG@Mso@@@3@AEBUIBitmap@ARC@@AEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@Math@@AEBU?$TAffine3x3@M@8@PEBU98@W4InterpolationMode@6@@Z; Mso::SVG::SVGCreatingCommandSink::GetEmbeddedImageForBitmap(ARC::IBitmap const &,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const &,Math::TAffine3x3<float> const &,Math::TAffine3x3<float> const *,ARC::InterpolationMode)
0x180052a42  lea     rcx, [rbp+90h+arg_0]
0x180052a49  call    ?Create@ISVGStyleProps@SVG@Mso@@SA?AV?$TCntPtr@UISVGStyleProps@SVG@Mso@@@3@XZ; Mso::SVG::ISVGStyleProps::Create(void)
0x180052a4e  cmp     [rbp+90h+arg_20], 0
0x180052a55  jz      short loc_180052A73
0x180052a57  mov     rbx, [rbp+90h+arg_0]
0x180052a5e  test    rbx, rbx
0x180052a61  jz      loc_180052B95
0x180052a67  mov     rax, [rbx]
0x180052a6a  mov     rax, [rax+0B0h]
0x180052a71  jmp     short loc_180052A8D
0x180052a73  mov     rbx, [rbp+90h+arg_0]
0x180052a7a  test    rbx, rbx
0x180052a7d  jz      loc_180052B87
0x180052a83  mov     rax, [rbx]
0x180052a86  mov     rax, [rax+1B0h]
0x180052a8d  mov     rdi, [rbp+90h+arg_10]
0x180052a94  mov     rdx, rdi
0x180052a97  mov     rcx, rbx
0x180052a9a  call    cs:__guard_dispatch_icall_fptr
0x180052aa0  movsd   xmm4, qword ptr [rsp+190h+var_140+8]
0x180052aa6  movsd   xmm3, qword ptr [rsp+190h+var_150+8]
0x180052aac  movsd   xmm2, qword ptr [rsp+190h+var_150]
0x180052ab2  movsd   xmm0, qword ptr [rsp+190h+var_140]
0x180052ab8  comisd  xmm2, xmm0
  ... truncated ...
```
